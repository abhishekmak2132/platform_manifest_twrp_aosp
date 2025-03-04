Here is the full configuration for the GitHub Actions workflow you need to set up for your `platform_manifest_twrp_aosp` repository:

1. **Create the Workflow File**:
   - In the root of your repository, create a directory named `.github/workflows` if it doesn't already exist.
   - Inside the `.github/workflows` directory, create a new file named `build-twrp.yml`.

2. **Add Configuration to the Workflow File**:
   - Open the `build-twrp.yml` file and add the following configuration:

```yaml
name: Build TWRP

on:
  push:
    branches:
      - twrp-12.1
  pull_request:
    branches:
      - twrp-12.1

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout repository
      uses: actions/checkout@v2

    - name: Set up JDK 11
      uses: actions/setup-java@v2
      with:
        java-version: '11'

    - name: Set up Repo
      run: |
        sudo apt-get update
        sudo apt-get install -y repo

    - name: Initialize Repo
      run: repo init -u https://github.com/abhishekmak2132/platform_manifest_twrp_aosp.git -b twrp-12.1

    - name: Sync Repo
      run: repo sync

    - name: Setup build environment
      run: |
        export ALLOW_MISSING_DEPENDENCIES=true
        . build/envsetup.sh
        lunch twrp_SM-A236E-eng

    - name: Build recovery image
      run: mka recoveryimage
```

3. **Commit and Push the Changes**:
   - Add, commit, and push the changes to the `twrp-12.1` branch of the `abhishekmak2132/platform_manifest_twrp_aosp` repository.

```sh
git add .github/workflows/build-twrp.yml
git commit -m "Add GitHub Actions workflow for building TWRP"
git push origin twrp-12.1
```

4. **Verify the Workflow**:
   - Go to the [Actions tab](https://github.com/abhishekmak2132/platform_manifest_twrp_aosp/actions) in your repository to see if the workflow is triggered.












git add .github/workflows/build-twrp.yml
git commit -m "Add GitHub Actions workflow for building TWRP"
git push origin twrp-12.1steps:
- name: Checkout repository
  uses: actions/checkout@v2

- name: Set up JDK 11
  uses: actions/setup-java@v2
  with:
    java-version: '11'

- name: Set up Repo
  run: |
    sudo apt-get update
    sudo apt-get install -y repo

- name: Initialize Repo
  run: repo init -u https://github.com/abhishekmak2132/platform_manifest_twrp_aosp.git -b twrp-12.1

- name: Sync Repo
  run: repo sync

- name: Setup build environment
  run: |
    export ALLOW_MISSING_DEPENDENCIES=true
    . build/envsetup.sh
    lunch twrp_SM-A236E-eng

- name: Build recovery image
  run: mka recoveryimagegit add .github/workflows/build-twrp.yml
git commit -m "Add GitHub Actions workflow for building TWRP"
git push origin twrp-12.1name: Build TWRP

on:
  push:
    branches:
      - twrp-12.1
  pull_request:
    branches:
      - twrp-12.1

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout repository
      uses: actions/checkout@v2

    - name: Set up JDK 11
      uses: actions/setup-java@v2
      with:
        java-version: '11'

    - name: Set up Repo
      run: |
        sudo apt-get update
        sudo apt-get install -y repo

    - name: Initialize Repo
      run: repo init -u https://github.com/abhishekmak2132/platform_manifest_twrp_aosp.git -b twrp-12.1

    - name: Sync Repo
      run: repo sync

    - name: Setup build environment
      run: |
        export ALLOW_MISSING_DEPENDENCIES=true
        . build/envsetup.sh
        lunch twrp_SM-A236E-eng

    - name: Build recovery image
      run: mka recoveryimageIt looks like you are trying to commit changes to your repository, and you have two options for the repository: `twrp` and `abhishekmak`. To ensure your changes are committed to the correct repository and branch, follow these steps:

1. **Select the Correct Repository**:
   - Make sure you are working in the `abhishekmak2132/platform_manifest_twrp_aosp` repository.

2. **Create the Workflow File**:
   - In the root of your repository, create a directory named `.github/workflows` if it doesn't already exist.
   - Inside the `.github/workflows` directory, create a new file named `build-twrp.yml`.

3. **Add Configuration to the Workflow File**:
   - Open the `build-twrp.yml` file and add the following configuration:

```yaml
name: Build TWRP

on:
  push:
    branches:
      - twrp-12.1
  pull_request:
    branches:
      - twrp-12.1

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout repository
      uses: actions/checkout@v2

    - name: Set up JDK 11
      uses: actions/setup-java@v2
      with:
        java-version: '11'

    - name: Build TWRP
      run: |
        echo "Building TWRP..."
        # Add your build commands here
        # Example:
        # ./gradlew build
```

4. **Commit and Push the Changes**:
   - Add, commit, and push the changes to the `twrp-12.1` branch of the `abhishekmak2132/platform_manifest_twrp_aosp` repository.

```sh
git add .github/workflows/build-twrp.yml
git commit -m "Add GitHub Actions workflow for building TWRP"
git push origin twrp-12.1
```

5. **Verify the Workflow**:
   - Go to the [Actions tab](https://github.com/abhishekmak2132/platform_manifest_twrp_aosp/actions) in your repository to see if the workflow is triggered. You should see a new workflow run listed.

This setup will trigger the workflow on every push or pull request to the `twrp-12.1` branch. Adjust the build commands as per your project's requirements.To create and configure a GitHub Actions workflow for your repository, follow these steps:

1. **Create the Workflow File**:
   - Create a new directory `.github/workflows` in the root of your repository if it doesn't already exist.
   - Inside the `.github/workflows` directory, create a new file named `build-twrp.yml`.

2. **Add Configuration to the Workflow File**:
   - Open the `build-twrp.yml` file and add the following configuration:

```yaml
name: Build TWRP

on:
  push:
    branches:
      - twrp-12.1
  pull_request:
    branches:
      - twrp-12.1

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout repository
      uses: actions/checkout@v2

    - name: Set up JDK 11
      uses: actions/setup-java@v2
      with:
        java-version: '11'

    - name: Build TWRP
      run: |
        echo "Building TWRP..."
        # Add your build commands here
        # Example:
        # ./gradlew build
```

3. **Push the Changes**:
   - Commit and push the changes to the `twrp-12.1` branch.

```sh
git add .github/workflows/build-twrp.yml
git commit -m "Add GitHub Actions workflow for building TWRP"
git push origin twrp-12.1
```

4. **Verify the Workflow**:
   - Go to the [Actions tab](https://github.com/abhishekmak2132/platform_manifest_twrp_aosp/actions) in your repository to see if the workflow is triggered.
   - You should see a new workflow run listed. Click on it to see the details and logs.

This setup will trigger the workflow on every push or pull request to the `twrp-12.1` branch. Adjust the build commands as per your project's requirements.name: Build TWRP

on:
  push:
    branches:
      - twrp-12.1
  pull_request:
    branches:
      - twrp-12.1

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout repository
      uses: actions/checkout@v2

    - name: Set up JDK 11
      uses: actions/setup-java@v2
      with:
        java-version: '11'

    - name: Build TWRP
      run: |
        echo "Building TWRP..."
        # Add your build commands here
        # Example:
        # ./gradlew buildLet's verify the content of the workflow file and check the repository settings to ensure that everything is correctly configured. I'll start by fetching the `.github/workflows/build-twrp.yml` file from your repository.It seems I am unable to fetch the workflow file. Please manually verify that the `.github/workflows/build-twrp.yml` file exists in your repository and is correctly formatted. You can check this in the "Code" tab of your repository under `.github/workflows`. If the file exists and is correctly set up, try pushing a new commit to the `twrp-12.1` branch to trigger the workflow.It seems there was an issue fetching the jobs for the given workflow run ID. To troubleshoot further, please:

1. Verify the `.github/workflows/build-twrp.yml` file exists in your repository.
2. Ensure the file is correctly formatted and contains the appropriate content.
3. Visit the [Actions tab](https://github.com/abhishekmak2132/platform_manifest_twrp_aosp/actions) to check if any workflow runs are listed.

If the workflow file exists and everything seems correct, try pushing a new commit to the `twrp-12.1` branch to trigger the workflow again.It seems there was an issue fetching the jobs for the given workflow run ID. To troubleshoot further, please:

1. Verify the `.github/workflows/build-twrp.yml` file exists in your repository.
2. Ensure the file is correctly formatted and contains the appropriate content.
3. Visit the [Actions tab](https://github.com/abhishekmak2132/platform_manifest_twrp_aosp/actions) to check if any workflow runs are listed.

If the workflow file exists and everything seems correct, try pushing a new commit to the `twrp-12.1` branch to trigger the workflow again.It looks like you've made a commit to your repository. Let's go through the necessary steps to ensure the GitHub Actions workflow is triggered correctly:

1. Verify the workflow file exists:
   - Go to the `.github/workflows` directory in your repository.
   - Ensure the `build-twrp.yml` file is present.

2. Check the workflow file content:
   - Make sure the content of `build-twrp.yml` is correct and properly formatted.

3. Trigger the workflow:
   - You can trigger the workflow by pushing a new commit to the `twrp-12.1` branch.

To verify if the workflow is running, visit the [Actions tab](https://github.com/abhishekmak2132/platform_manifest_twrp_aosp/actions) in your repository. If there are no runs listed, you might need to double-check the file and branch configurations.It seems there are no visible workflow runs. Let's troubleshoot the workflow setup to ensure it's configured correctly.

1. Check that the `.github/workflows/build-twrp.yml` file exists and is correctly formatted.
2. Ensure that the `twrp-12.1` branch is up to date with the latest commit containing the workflow file.
3. Try pushing a new commit to the `twrp-12.1` branch to trigger the workflow.

If the workflow file exists and everything seems correct, you can create an empty commit to trigger the workflow:

```bash
git commit --allow-empty -m "Trigger workflow"
git push origin twrp-12.1
```

After pushing, check the "Actions" tab again to see if the workflow runs are triggered.git commit --allow-empty -m "Trigger workflow"
git push origin twrp-12.1Let's verify if the workflow file exists and is correctly set up in your repository.

1. Navigate to the `.github/workflows` directory in your `twrp-12.1` branch.
2. Confirm that the `build-twrp.yml` file exists with the correct content.

If the file exists and is correctly set up, try pushing a new commit to the `twrp-12.1` branch to trigger the workflow. You can create an empty commit with the following command:

```bash
git commit --allow-empty -m "Trigger workflow"
git push origin twrp-12.1
```

This should trigger the workflow, and you can monitor the progress in the "Actions" tab of your repository. the workflow file was created and committed correctly.

1. Verify that the `.github/workflows/build-twrp.yml` file exists in your repository.
2. Make sure it contains the correct content and is properly formatted.

You can check this directly in your repository under the "Code" tab and navigating to `.github/workflows`. If everything looks correct and you still don't see any runs, try pushing a new commit to the `twrp-12.1` branch to trigger the workflow again.# Initialize the repository
repo init -u https://github.com/abhishekmak2132/platform_manifest_twrp_aosp.git -b twrp-12.1

# Synchronize the repository
repo sync

# Setup the build environment
cd twrp
export ALLOW_MISSING_DEPENDENCIES=true
. build/envsetup.sh
lunch twrp_SM-A236E-eng

# Build the recovery image
mka recoveryimagecd <twrp>
export ALLOW_MISSING_DEPENDENCIES=true
. build/envsetup.sh
lunch twrp_SM-A236E-eng## Submitting Patches ##
Our project is open source, and patches are always welcome!
You can send patches by using:

Pull request, right here on git.

Contact us at https://rebrand.ly/teamwin-recovery-zulip-community

## Maintaining Authorship ##
Maintaining authorship is a very important aspect of working with Open Source code. If you wish to submit a patch/fix
from anywhere else (another ROM, project, etc.), it is imperative that you maintain the ownership of the person whose
work you are seeking to include. Doing so will ensure that credit is given where it is deserved, and
the [principles of open source](http://opensource.org/docs/osd)
are upheld. Your contribution to the project will still be recognized as you will forever be listed as the committer.

If you manually cherry pick a patch/fix then you will need to add the original author prior to pushing to
our [gerrit](https://gerrit.twrp.me). This is a very easy task to perform, and is usually done after you commit a
patch/fix locally. This is accomplished after you type in `git commit -a` , type in the commit message and save. You
would then do the following:

```bash
git commit --amend --author "Author <email@address.com>"
```

So it should look like this once you get all of the author's information:

```bash
git commit --amend --author "Spencer McGillicuddy <spencer.the.bestest@gmail.com>"
```

Alternatively, adding as part of the original `git commit` message is preferred and done like the following:

```bash
git commit --author="Author <email@address.com>" -m "[commit message]"
```

This saves time, and when part of your normal routine, prevents the infamous "ermahgerd I forgot to add authorship - let
me fix it because I was found out!" message.


## Getting Started ##
To get started with AOSP sources to build TWRP, you'll need to get familiar
with [Git and Repo](https://source.android.com/source/using-repo.html).

To initialize your local repository using the AOSP trees to build TWRP, use a command like this:

    repo init -u https://github.com/minimal-manifest-twrp/platform_manifest_twrp_aosp.git -b twrp-12.1

To initialize a shallow clone, which will save even more space, use a command like this:

    repo init --depth=1 -u https://github.com/minimal-manifest-twrp/platform_manifest_twrp_aosp.git -b twrp-12.1

Then to sync up:

    repo sync

Then to setup the build:

     cd <twrp>; export ALLOW_MISSING_DEPENDENCIES=true; . build/envsetup.sh; lunch twrp_< SM-A236E/DS>-eng

The build target is dependent on the device, and should reflect the location of stock recovery on the device. Issue the build command that applies to your device:
- Recovery partition: `mka recoveryimage`
- Boot image ramdisk: `mka bootimage`
- Vendor_boot image ramdisk: `mka vendorbootimage`

### Special Notes for this branch
- Device makefile in the device tree and dependencies file should use the "twrp" prefix.
- FDE decryption is not presently supported in this branch.# Initialize the repository
repo init -u https://github.com/abhishekmak2132/platform_manifest_twrp_aosp.git -b twrp-12.1

# Synchronize the repository
repo sync

# Setup the build environment
cd twrp
export ALLOW_MISSING_DEPENDENCIES=true
. build/envsetup.sh
lunch twrp_SM-A236E-eng

# Build the recovery image
mka recoveryimage# Initialize the repository
repo init -u https://github.com/abhishekmak2132/platform_manifest_twrp_aosp.git -b twrp-12.1

# Synchronize the repository
repo sync

# Setup the build environment
cd twrp
export ALLOW_MISSING_DEPENDENCIES=true
. build/envsetup.sh
lunch twrp_SM-A236E-eng

# Build the recovery image
mka recoveryimage
name: Build TWRP

on:
  push:
    branches:
      - twrp-12.1
  pull_request:
    branches:
      - twrp-12.1

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout repository
      uses: actions/checkout@v2

    - name: Set up Repo
      run: |
        sudo apt-get update
        sudo apt-get install -y repo

    - name: Initialize Repo
      run: repo init -u https://github.com/abhishekmak2132/platform_manifest_twrp_aosp.git -b twrp-12.1

    - name: Sync Repo
      run: repo sync

    - name: Setup build environment
      run: |
        export ALLOW_MISSING_DEPENDENCIES=true
        . build/envsetup.sh
        lunch twrp_SM-A236E-eng

    - name: Build recovery image
      run: mka recoveryimage