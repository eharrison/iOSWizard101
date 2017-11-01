# iOSWizard101

Ready for some information?? :)

## Updating the code

As we are installing the Library with CocoaPods, we have to follow a few steps to make sure it will update in our project(s).

### Editing the Library

**Important:** Before beginning, make sure you are working on the **MASTER** branch.

Make sure you open the project in the following path:

```ruby
AwesomeRepository/Example/AwesomeRepository.xcworkspace
```

XCode will open with 2 projects:
- **AwesomeRepository** (your project configuration and usage example)
- **Pods** (your pod file classes)

All of the files that will be imported to our projects with cocoapods are in the following path

```ruby
Pods/Development Pods/AwesomeRepository/AwesomeRepository/Classes
```

Pick yours, edit it and be happy. Oh well, before being too happy, move to **Creating a new version for the Pod file** session to create a new version of the code.

### Testing the Library

Sometimes, you need to test your code before deploying a new version.
For any test, you can use the **Example for AwesomeRepository**.
All of the files created here will not be imported to our projects, so don't worry, be free to test it as if it was one of our projects.

### Creating a new version for the Pod file

Ok, so for starters, you have to work on the changes you wanted to make, right? Otherwise there is no point in creating a new version! ;)
*(Only proceed once you are ready to deploy)*

1. Navigate to file:

```ruby
AwesomeLocalization/Podspec Metadata/AwesomeRepository.podspec
```

2. Change the **s.version** by summing 1 to the end:

```ruby
//if version 0.1.3, the new version should be 0.1.4
//if version 0.1.9, the new version should be 0.2.0
```

3. Edit the **README.md** file with the new version:

```ruby
//update tag to match the current version
pod 'AwesomeRepository', git: 'https://github.com/iOSWizards/AwesomeRepository.git', tag: '0.1.0'
```

4. Commit your changes to **MASTER**
5. Create a new branch with the new version name. Push the new branch.
6. In your project, update the Podfile to match the new AwesomeLocalization version.
7. Run **pod install** and be happy :)

### Deploying the library to CocoaPods repository

If it's the first time that you're trying to deploy the pod to `trunk`, maybe there will be a few more steps to follow:

1. Go to the project directory where you have the **.podspec** file, run `pod lib lint`, and see if everything goes on the track!

1.1 If your library is not in the same Swift version of the CocoaPods, it will ask you to add a `.swift-version` file including your Swift version inside, simple as **4.0**. That's it!

Library validated, and no more warnings, we can go ahead. 

2. If it's the first time, you will need to register your machine as a trunk session, you can get it done by simple doing it: `pod trunk register leonardo@cocoapods.org 'Leonardo Ferreira' --description='macbook pro 15'` and then they are going to send a confirmation email for you, just click on the link and it's done.

3. Everything ok, changes commited to your repository, you need to create a tag on GitHub for your library. Go to GitHub's page and create the tag corresponding to your latest `.podspec` library version.

All good!

4. Time to effectively push your lib to CocoaPods. For public libraries, run this command: `pod trunk push YOU_LIB_NAME.podspec` or for private repositories you can do: `pod repo push REPO YOU_LIB_NAME.podspec`.

5. That's all. :tada::rocket: If everything went right, you are going to see a screen like this one:

<br />![alt text](https://github.com/iOSWizards/iOSWizard101/blob/master/pod-push-trunk.jpg)

#### Tips

- It might take some time to upload your lib to the repository, around 24h. It's normal, the first time is always a pain.

## Author

- Evandro Harrison Hoffmann, evandro@itsdayoff.com
- Leonardo Kaminski Ferreira, leonardo.kaminski.ferreira@gmail.com
- Antônio Carlos, ton1n8o

## License

AwesomeRepository is available under the MIT license. See the LICENSE file for more info.
