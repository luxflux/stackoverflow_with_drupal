# stackoverflow_with_drupal
This will be a sample project with Drupal to introduce new members with Drupal and also to get experiences

## Development Setup

```bash
# Start it using ddev
ddev start

# Install the dependencies
ddev composer install

# Install the basic site
ddev exec drush site-install --account-name=admin --account-pass=admin -y

# Set the site UUID
ddev exec drush cset system.site uuid "0658b3a3-3a93-4697-b4d2-d35ee938dd15" -y

# Remove conflicting entities
ddev exec drush eval \'\\Drupal\:\:entityManager\(\)\-\>getStorage\(\"shortcut_set\"\)\-\>load\(\"default\"\)\-\>delete\(\)\;\'

# Load the database structure
ddev exec drush config-import --source=config-export -y

# Rebuild cache
ddev exec drush cache-rebuild
```
