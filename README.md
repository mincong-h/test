# Test

Test gh-pages

## Test 1 - Simple File

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

## Test 2 - mincong.io

```sh
# Under directory mincong-h.github.io, generate the entire site
./docker-serve.sh

# Copy content to test
cp -r _site/ ../test/_site

# Go to test site, commit and deploy
cd ../test/_site
git add .
git commit -m "Generate content"
git push
```

Visit <https://mincong.io/test/> to see the result.

## References

- [MrPowerScripts, How to get around the jekyll-pagination-v2 limitation of GitHub pages with CircleCI](https://mrpowerscripts.com/github-pages-circleci-jekyll-paginate-v2/)
- [Sangsoo Nam, Using Git Worktree to Deploy GitHub Pages](https://sangsoonam.github.io/2019/02/08/using-git-worktree-to-deploy-github-pages.html)
