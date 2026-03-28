---
title: "Hugo Website Manual Deployment to SourceHut Pages"
date: 2024-03-26
math: true
---

## Here is my script used in Hugo Website deployment to SourceHut Pages

Be sure to check the configuration format or file location correctly!

{{< code language="bash" >}}

#!/bin/bash

# Simple Hugo to SourceHut Pages Deploy Script
# Deploys from ~/websites/blog to SourceHut Pages

# Configuration
SITE_NAME="mhabib12345"          # Your site name (without .srht.site)
HUGO_DIR="$HOME/blog" # Hugo project directory
PUBLIC_DIR="public"           # Hugo output directory
TARBALL="/tmp/site.tar.gz"    # Temporary tarball path

# Colors for output
RED='\033[0;31m'
GREEN='\033[0;32m'
YELLOW='\033[1;33m'
NC='\033[0m' # No Color

# Check for required commands
check_dependency() {
    if ! command -v $1 &> /dev/null; then
        echo -e "${RED}Error: $1 not found.${NC}" >&2
        echo -e "${YELLOW}Please install it first:${NC}" >&2
        if [ "$1" == "hugo" ]; then
            echo "https://gohugo.io/installation/"
        else
            echo "pip install hut"
        fi
        exit 1
    fi
}

check_dependency hugo
check_dependency hut

# Build Hugo site
echo -e "${GREEN}Building Hugo site from ${HUGO_DIR}...${NC}"
cd "$HUGO_DIR" || { echo -e "${RED}Error: Could not enter Hugo directory${NC}"; exit 1; }

hugo --minify --cleanDestinationDir

if [ $? -ne 0 ]; then
    echo -e "${RED}Error: Hugo build failed${NC}"
    exit 1
fi

# Create tarball
echo -e "${GREEN}Creating deployment tarball...${NC}"
tar -C "$PUBLIC_DIR" -cvzf "$TARBALL" . || {
    echo -e "${RED}Error: Failed to create tarball${NC}"
    exit 1
}

# Check hut authentication
#if ! hut config get auth.token &> /dev/null; then
#    echo -e "${YELLOW}hut authentication not configured.${NC}"
#    echo "Please set up your access token:"
#    echo "1. Get a token from https://meta.sr.ht/oauth2"
#    echo "2. Run: hut config set auth.token YOUR_TOKEN"
#    exit 1
#fi

# Deploy to SourceHut Pages
echo -e "${GREEN}Deploying to SourceHut Pages...${NC}"
hut pages publish -d "$SITE_NAME.srht.site" "$TARBALL" || {
    echo -e "${RED}Error: Deployment failed${NC}"
    exit 1
}

# Cleanup
rm "$TARBALL"

echo -e "${GREEN}Deployment complete!${NC}"
echo -e "Your site should be available at: ${YELLOW}https://$SITE_NAME.srht.site${NC}"

{{< /code >}}