Viewing Documentation
=====================
```
npm install
npm run view
npm run publish
```

Publishing Documentation to Confluence
======================================
Create API key and set CONFLUENCE_USERNAME in .env as email used to login and CONFLUENCE_PASSWORD as the key.
```
npm run publish
```

Creating new documentation
==========================
1. Fork arc42 repo into a new repo
2. Edit name and title in antora.yml
3. Add as new source to antora-playbook.yml (relative path or another git URL)

Initial Setup
=============
This project was initialised using the following which created the initial arc42 template with antora setup.
```
curl -Lo dtcw https://doctoolchain.org/dtcw
chmod +x dtcw
./dtcw downloadTemplate
node -e "fs.writeFileSync('package.json', '{}')"
npm i -D -E antora
```

I then moved src/docs/arc42 into a separate folder (../arc42) and made it a git repo.

```
git init .
touch .gitignore
git add .gitignore
git commit -m 'initialize repository'
```

and then use the directory as the source in antora-playbook.yml (can be relative or a git URL)

```
  sources:
    - url: ../arc42
      branches: HEAD
```