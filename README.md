# SwiftPacakge
How to properly import Swift Packages in your project
# Step by Step 
1. $ cd <projectName>
1. $ swift package init --typw executable
1. $ swift build 
1. copy paste the last line 
1. copy paste this lines in your Package.swift
    ```swift
      ,
    dependencies: [
        .Package(
            url: "https://github.com/SwiftyJSON/SwiftyJSON.git",
            "4.0.0"
        ),
        .Package(url: "https://github.com/Alamofire/Alamofire.git", majorVersion: 4),
        ]

    ```
 1. replace the `url` by the url of the packages you want to install 
 1. $ swift package update 
 1. $ swift package generate-xcodeproj
 1. $ swift package generate-xcodeproj
 1. $ open AppName.xcodeproj to test and see if everything is good. 
 
 # Error Handlering 
 1. Error: target specifies product type 'com.apple.product-type.bundle.ui-testing', but there's no such product type for the 'iphonesimulator' platform
    ## Solution Steps 
    1. Open `AppName.xcodeproj/project.pbxproj`, replace all `com.apple.product-type.*` (there are 3 of them) with                    `com.apple.product-type.application` solved the problem.
        It seems apple changed the type name in Xcode 7.
