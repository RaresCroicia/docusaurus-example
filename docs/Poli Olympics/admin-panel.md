---
sidebar_position: 3
---

# Admin Panel

*Only admins and managers have access to admin panel*.
## **Components**

### Users

- Shows a list with all the users. Uses helper component *UserRow*.

- **Only the manager**, can change the role of other users or delete users.


### Faculties

- Shows a list with all the faculties. Uses helper component *FacultyRow*.

- Admins can add or delete faculties and change their score.

### Matches
   
- Only one page for all the sports. You can select of what sport do you want to see the matches.

- In this page, admins can create new matches, delete matches and edit their score and status. More details [here](https://docs.google.com/document/d/1JXFGVIkrJaPcl7wpjPVXy3B_p-eKggXhRrQKiDgqD0g/edit?usp=sharing).

- Uses helper component *MatchRow*, that uses *MatchUpdateSockets*, component that uses websockets to update the live scores.