# iOSWizard101

Ready for some information?? :)

## Updating the code

As we are installing the Library with CocoaPods, we have to follow a few steps to make sure it will update in our project(s).

### Editing the Library

**Important:** Before beginning, make sure you are working on the **MASTER** branch.

Make sure you open the project in the following path:

```ruby
AwesomeLocalization/Example/AwesomeRepository.xcworkspace
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

## Author

- Evandro Harrison Hoffmann, evandro@itsdayoff.com
- Leonardo Kaminski Ferreira, leonardo.kaminski.ferreira@gmail.com
- Antônio Carlos, ton1n8o

## License

AwesomeRepository is available under the MIT license. See the LICENSE file for more info.
