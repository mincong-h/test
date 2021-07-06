# Test

Test gh-pages

## Steps

Prepare file:

```sh
# Create a new branch "gh-pages" without any commit history from the main branch
git checkout --orphan gh-pages

# Remove existing content
git reset --hard

# Create a file for test
echo "Welcome to gp-pages test." > index.txt

# Commit and trigger the build
git commit -m "Initialize gh-pages"
git push -u origin gh-pages
```

Test deployment:

```sh
curl https://mincong.io/test/index.txt
```
```
Welcome to gp-pages test.
```
