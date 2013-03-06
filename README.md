CHKeychain
==========

a tool to read and write info to ios keychain

this repo is write by http://blog.csdn.net/bl1988530/article/details/6887946 

i move it to github and fix some bugs.

### first define some const

NSString * const KEY_USERNAME_PASSWORD = @"com.company.app.usernamepassword";
NSString * const KEY_USERNAME = @"com.company.app.username";
NSString * const KEY_PASSWORD = @"com.company.app.password";

### write info to keychain

```
NSMutableDictionary *usernamepasswordKVPairs = [NSMutableDictionary dictionary];
[usernamepasswordKVPairs setObject:@"***" forKey:KEY_USERNAME];
[usernamepasswordKVPairs setObject:@"***" forKey:KEY_PASSWORD];
[CHKeychain save:KEY_USERNAME_PASSWORD data:usernamepasswordKVPairs];
            
```

### read info from keychain

```
NSMutableDictionary *usernamepasswordKVPairs = (NSMutableDictionary *)[CHKeychain load:KEY_USERNAME_PASSWORD];
NSString *username=[usernamepasswordKVPairs objectForKey:KEY_USERNAME];
NSString *password=[usernamepasswordKVPairs objectForKey:KEY_PASSWORD];
    
```
