# TODO Plan for Adding PATCH and DELETE Routes to NewsletterByID

## Task Summary

Add `patch()` and `delete()` methods to the `NewsletterByID` Resource class in `server/app.py` to support updating and deleting individual newsletter records.

## Implementation Plan

### File: server/app.py

1. **Add `patch(self, id)` method to `NewsletterByID` class** ✓ COMPLETED

   - Retrieve the newsletter record by id using `Newsletter.query.filter_by(id=id).first()`
   - Loop through `request.form` data using `setattr()` to update record attributes
   - Add the updated record to the session and commit
   - Return the updated record as a dictionary with 200 status

2. **Add `delete(self, id)` method to `NewsletterByID` class** ✓ COMPLETED
   - Retrieve the newsletter record by id using `Newsletter.query.filter_by(id=id).first()`
   - Delete the record from the session and commit
   - Return a success message with 200 status

## Expected Result

After implementation:

- PATCH `/newsletters/<int:id>` - Updates an existing newsletter record
- DELETE `/newsletters/<int:id>` - Deletes an existing newsletter record

## Files to Modify

- `server/app.py` - Add patch() and delete() methods to NewsletterByID class ✓ DONE
