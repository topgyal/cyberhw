# codepath_homework

## Week 7 & 8 Assignment

# Project 7 - WordPress Pentesting

Time spent: **6** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

### 1. Title: WordPress 4.1-4.2.1 - Unauthenticated Genericons Cross-Site Scripting (XSS)
  - [ ] Summary: WordPress 4.1.5 and 4.2.2 removes the Genericons example file which came bundled with the twentyfifteen theme which is vulnerable to DOM based Cross-Site Scripting (XSS).
    - Vulnerability types: XSS
    - Tested in version: 4.2.1
    - Fixed in version: 4.2.2
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](wp-admin/js/editor-expand.js)
    - [Link 2](wp-admin/about.php)
    - [Link 3](wp-admin/includes/file.php)
    - [Link 4](wp-admin/includes/upgrade.php)
    - [Link 5](wp-includes/version.php)
    - [Link 6](wp-includes/post.php)

### 2. Title: WordPress <= 4.2.3 - wp_untrash_post_comments SQL Injection 
  - [ ] Summary: SQL injection vulnerability in the wp_untrash_post_comments function in wp-includes/post.php in WordPress before 4.2.4 allows remote attackers to execute arbitrary SQL commands via a comment that is mishandled after retrieval from the trash.
    - Vulnerability types: SQLI
    - Tested in version: 4.2.3
    - Fixed in version: 4.2.4
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: added $status = 0 when 'post-trashed'==$status and fixed $comments_in = implode( ', ', array_map( 'intval', $comments ) );
		$wpdb->query( $wpdb->prepare( "UPDATE $wpdb->comments SET comment_approved = %s WHERE comment_ID IN ($comments_in)", $status ) ); in  wp-includes/post.php file
  - [ ] Affected source code:
    - [Link 1](wp-admin/post.php)
### 3. Title: WordPress 2.8-4.7 - Accessibility Mode Cross-Site Request Forgery (CSRF)
  - [ ] Summary: Cross-site request forgery (CSRF) vulnerability in the widget-editing accessibility-mode feature in WordPress before 4.7.1 allows remote attackers to hijack the authentication of unspecified victims for requests that perform a widgets-access action, related to wp-admin/includes/class-wp-screen.php and wp-admin/widgets.php.
    - Vulnerability types: CSRF
    - Tested in version: 4.2.9
    - Fixed in version: 4.2.11
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: added $nonce = wp_create_nonce( 'widgets-access' ); to class-wp-screen.php file, added check_admin_referer( 'widgets-access' ); to widgets.php file
  - [ ] Affected source code:
    - [Link 1](wp-admin/includes/class-wp-screen.php)
    - [Link 2](wp-admin/widgets.php)
    
References

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [2020] [Topgyal Gurung]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
