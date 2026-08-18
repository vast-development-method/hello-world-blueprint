### JCB! Joomla Module
# Site Redirect (v5.0.0)
## SiteRedirect

To Redirect your Site Page to any other part of the admin area in your Joomla for a selected group of users

### Module Settings
| Setting     | Value          |
|-------------|----------------|
| Target Area | ![Site](https://img.shields.io/badge/Site-blue?style=flat-square)  |
| Add README  | ![no](https://img.shields.io/badge/no-blue?style=flat-square)   |

## Default Template:
```html
<h1><?php echo Joomla___ba6326ef_cb79_4348_80f4_ab086082e3c5___Power::_('Site Redirect'); ?></h1>
<p><?php echo Joomla___ba6326ef_cb79_4348_80f4_ab086082e3c5___Power::_('Setup your redirect in the site model <b>Site Redirect</b> or change this models <b>Access</b> to not target this users access level.'); ?></p>
```

<details>
<summary>Dispatcher getLayoutData Method (J4+)</summary>

```php
		// get the set values form cpanel redirect module
		$redirect = $data['params']->get('redirect',null);

		// redirect if the user is in given selected group
		if ($redirect && is_object($redirect) && count((array)$redirect) > 0)
		{
			// set the user object
			$user = $data['app']->getIdentity();
			// get user groups
			$groups = (array) $user->getAuthorisedGroups();
			// loop over the set values
			foreach ($redirect as $go)
			{
				if (is_object($go))
				{
					if (is_array($go->groups) && count($go->groups))
					{
						if (array_intersect($go->groups, $groups))
						{
							// match found - redirect
							$data['app']->redirect($go->url);
							break;

						}
					}
				}
			}
		}
```

</details>

<details>
<summary>Module Code (J3)</summary>

```php
// get the set values form cpanel redirect module
$redirect = $params->get('redirect',null);

// redirect if the user is in given selected group
if ($redirect && is_object($redirect) && count((array)$redirect) > 0)
{
	// get application
	$app = Joomla___39403062_84fb_46e0_bac4_0023f766e827___Power::getApplication();
	// set the user object
	$user = Joomla___39403062_84fb_46e0_bac4_0023f766e827___Power::getUser();
	// get user groups
	$groups = (array) $user->getAuthorisedGroups();
	// loop over the set values
	foreach ($redirect as $go)
	{
		if (is_object($go))
		{
			if (is_array($go->groups) && count($go->groups))
			{
				if (array_intersect($go->groups, $groups))
				{
					// match found - redirect
					$app->redirect($go->url);
					break;

				}
			}
		}
	}
}

// get the module class sfx (local)
$moduleclass_sfx = htmlspecialchars($params->get('moduleclass_sfx', ''), ENT_COMPAT, 'UTF-8');

// load the default Tmpl
require Joomla___f15d556d_33dd_4ee3_a0f7_0653e4a7a1e4___Power::getLayoutPath('mod_[[[module]]]', $params->get('layout', 'default'));
```

</details>

> Display reusable content or functionality anywhere on your site with this flexible, position-ready Joomla Module built for seamless use in JCB.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![GitHub](https://img.shields.io/badge/-Git-181717?logo=git)](https://github.com/joomengine "Build premium Joomla extensions with JoomEngine on GitHub: Help us raise Joomla extension standards!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/r/octoleo/joomengine "JoomEngine on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")