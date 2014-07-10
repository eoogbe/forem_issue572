forem_issue572
==============

Demonstrates the problem in [issue #572](https://github.com/radar/forem/issues/572)
of [forem](https://github.com/radar/forem).

###I'm Using
Ruby    2.0.0  
Rails   4.1.1  
"rails4" branch of Forem  

##Summary

When trying to delete a category or forum, an error occurs and they are not deleted.
Deleting a group doesn't cause an error, but also doesn't delete the group.

The error happens through the admin interface.
###Paths
category -    /forums/admin/categories  
forum -       /forums/admin/forums  
group -       /forums/admin/groups  
Navigating to any of these pages and click the delete button/link will cause the error.

##Delete Category Error
Unknown action
The action 'show' could not be found for Forem::Admin::CategoriesController

###Full stack trace
````
AbstractController::ActionNotFound (The action 'show' could not be found for For
em::Admin::CategoriesController):
  actionpack (4.1.1) lib/abstract_controller/base.rb:131:in `process'
  actionview (4.1.1) lib/action_view/rendering.rb:30:in `process'
  actionpack (4.1.1) lib/action_controller/metal.rb:195:in `dispatch'
  actionpack (4.1.1) lib/action_controller/metal/rack_delegation.rb:13:in `dispa
tch'
  actionpack (4.1.1) lib/action_controller/metal.rb:231:in `block in action'
  actionpack (4.1.1) lib/action_dispatch/routing/route_set.rb:80:in `call'
  actionpack (4.1.1) lib/action_dispatch/routing/route_set.rb:80:in `dispatch'
  actionpack (4.1.1) lib/action_dispatch/routing/route_set.rb:48:in `call'
  actionpack (4.1.1) lib/action_dispatch/journey/router.rb:71:in `block in call'

  actionpack (4.1.1) lib/action_dispatch/journey/router.rb:59:in `each'
  actionpack (4.1.1) lib/action_dispatch/journey/router.rb:59:in `call'
  actionpack (4.1.1) lib/action_dispatch/routing/route_set.rb:676:in `call'
  railties (4.1.1) lib/rails/engine.rb:514:in `call'
  railties (4.1.1) lib/rails/railtie.rb:194:in `public_send'
  railties (4.1.1) lib/rails/railtie.rb:194:in `method_missing'
  actionpack (4.1.1) lib/action_dispatch/journey/router.rb:71:in `block in call'

  actionpack (4.1.1) lib/action_dispatch/journey/router.rb:59:in `each'
  actionpack (4.1.1) lib/action_dispatch/journey/router.rb:59:in `call'
  actionpack (4.1.1) lib/action_dispatch/routing/route_set.rb:676:in `call'
  warden (1.2.3) lib/warden/manager.rb:35:in `block in call'
  warden (1.2.3) lib/warden/manager.rb:34:in `catch'
  warden (1.2.3) lib/warden/manager.rb:34:in `call'
  rack (1.5.2) lib/rack/etag.rb:23:in `call'
  rack (1.5.2) lib/rack/conditionalget.rb:25:in `call'
  rack (1.5.2) lib/rack/head.rb:11:in `call'
  actionpack (4.1.1) lib/action_dispatch/middleware/params_parser.rb:27:in `call
'
  actionpack (4.1.1) lib/action_dispatch/middleware/flash.rb:254:in `call'
  rack (1.5.2) lib/rack/session/abstract/id.rb:225:in `context'
  rack (1.5.2) lib/rack/session/abstract/id.rb:220:in `call'
  actionpack (4.1.1) lib/action_dispatch/middleware/cookies.rb:560:in `call'
  activerecord (4.1.1) lib/active_record/query_cache.rb:36:in `call'
  activerecord (4.1.1) lib/active_record/connection_adapters/abstract/connection
_pool.rb:621:in `call'
  activerecord (4.1.1) lib/active_record/migration.rb:380:in `call'
  actionpack (4.1.1) lib/action_dispatch/middleware/callbacks.rb:29:in `block in
 call'
  activesupport (4.1.1) lib/active_support/callbacks.rb:82:in `run_callbacks'
  actionpack (4.1.1) lib/action_dispatch/middleware/callbacks.rb:27:in `call'
  actionpack (4.1.1) lib/action_dispatch/middleware/reloader.rb:73:in `call'
  actionpack (4.1.1) lib/action_dispatch/middleware/remote_ip.rb:76:in `call'
  actionpack (4.1.1) lib/action_dispatch/middleware/debug_exceptions.rb:17:in `c
all'
  actionpack (4.1.1) lib/action_dispatch/middleware/show_exceptions.rb:30:in `ca
ll'
  railties (4.1.1) lib/rails/rack/logger.rb:38:in `call_app'
  railties (4.1.1) lib/rails/rack/logger.rb:20:in `block in call'
  activesupport (4.1.1) lib/active_support/tagged_logging.rb:68:in `block in tag
ged'
  activesupport (4.1.1) lib/active_support/tagged_logging.rb:26:in `tagged'
  activesupport (4.1.1) lib/active_support/tagged_logging.rb:68:in `tagged'
  railties (4.1.1) lib/rails/rack/logger.rb:20:in `call'
  actionpack (4.1.1) lib/action_dispatch/middleware/request_id.rb:21:in `call'
  rack (1.5.2) lib/rack/methodoverride.rb:21:in `call'
  rack (1.5.2) lib/rack/runtime.rb:17:in `call'
  activesupport (4.1.1) lib/active_support/cache/strategy/local_cache_middleware
.rb:26:in `call'
  rack (1.5.2) lib/rack/lock.rb:17:in `call'
  actionpack (4.1.1) lib/action_dispatch/middleware/static.rb:64:in `call'
  rack (1.5.2) lib/rack/sendfile.rb:112:in `call'
  railties (4.1.1) lib/rails/engine.rb:514:in `call'
  railties (4.1.1) lib/rails/application.rb:144:in `call'
  rack (1.5.2) lib/rack/lock.rb:17:in `call'
  rack (1.5.2) lib/rack/content_length.rb:14:in `call'
  rack (1.5.2) lib/rack/handler/webrick.rb:60:in `service'
  c:/RailsInstaller/Ruby2.0.0/lib/ruby/2.0.0/webrick/httpserver.rb:138:in `servi
ce'
  c:/RailsInstaller/Ruby2.0.0/lib/ruby/2.0.0/webrick/httpserver.rb:94:in `run'
  c:/RailsInstaller/Ruby2.0.0/lib/ruby/2.0.0/webrick/server.rb:295:in `block in
start_thread'


  Rendered c:/RailsInstaller/Ruby2.0.0/lib/ruby/gems/2.0.0/gems/actionpack-4.1.1
/lib/action_dispatch/middleware/templates/rescues/unknown_action.html.erb within
 rescues/layout (1.0ms)
 ````

##Attempted Solutions
As claimed by [vcavallo](https://github.com/vcavallo), adding a show.html.erb
to the forem/admin/categories/ or forem/admin/forums/ folder will stop the error,
but the item will not be deleted.
