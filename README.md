# Install

## Get the package



    composer require kevinberg/laravel-role-perms



## Extend the user class



Import the Roles trait in the User.php file:



    use kevinberg\LaravelRolePerms\Traits\Roles;



Inside the user class use the trait:



    use Roles;



## Seeds



    php artisan db:seed --class=kevinberg\LaravelRolePerms\Database\Seeds



By default the following seeder creates the admin role and some permission. If there is a user with the name admin, then by default he gets the role admin.



# Usage



## Functions



### User Model

To check if a user model has a permission or a role you can use this:

    $user->hasPermission('permissionName'); // true || false
    $user->hasRole('roleName'); // true || false

The user function results will be cached!
Use `RolePerms::clearPermissionCache();` or `RolePerms::clearRoleCache();` to clean up if needed.

### Facade

Include the Facade to use the following functions.

    use kevinberg\LaravelRolePerms\Facades\RolePerms;

Now you can use the following functions:

    RolePerms::userHasRole(User  $user, String  $roleName); // true || false

    RolePerms::userHasPermission(User  $user, String  $permissionName); // true || false

	RolePerms::roleHasPermission(String  $roleName, String  $permissionName); // true || false

	RolePerms::grantRole(User  $user, String  $roleName); // true || false

	RolePerms::grantPermission(String  $roleName, String  $permissionName); // true || false

	RolePerms::revokeRole(User  $user, String  $roleName); // true || false

	RolePerms::revokePermission(String  $roleName, String  $permissionName); // true || false

	RolePerms::clearRoleCache(); // true || false

	RolePerms::clearPermissionCache(); // true || false

	RolePerms::createRole(String  $roleName); // Role || false

	RolePerms::createPermission(String  $permissionName); // Permission || false

	RolePerms::deleteRole(String  $roleName); // true || false

	RolePerms::deletePermission(String  $permissionName); // true || false