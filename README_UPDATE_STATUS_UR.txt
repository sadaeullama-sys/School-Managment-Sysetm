School Management System — Update notes

Applied in this source update:
1. Professional neutral charcoal/emerald/gold theme replaces the blue-heavy palette.
2. Staff account form now saves a selected permissions list, including view modules and explicit edit-permission labels.
3. Staff login displays the modules and permissions assigned to that Staff ID.
4. Parent login opens a read-only child record page and filters local fee, attendance, and marks records by the linked student ID.
5. PDF actions use Printing.sharePdf(bytes: ..., filename: ...) so Android's share/save sheet can be used instead of forcing the failing Print Preview.
6. Student Date of Birth is selected with the native calendar date picker.
7. Syllabus and Date Sheet class entry uses the class dropdown, defaulting to the first class.

Important limitations:
- Staff permissions are stored and displayed, but this update does NOT yet connect each Staff permission to every existing dashboard module's edit/save/delete callbacks. Do not treat this as a complete security boundary.
- Parent view-only page reads local SharedPreferences data. It is not yet synchronized across separate phones.
- Principal/Staff/Parent cross-device authentication and secure multi-device sync require Firebase Auth provisioning, Firestore data migration, and security rules. This update does not claim those are completed.
- PDF share sheet can offer Save/Print depending on installed Android apps; physical-device verification is still required.
- This project has not been compiled in this environment because Flutter/Dart SDK is unavailable. Run flutter analyze and flutter build apk --release in GitHub Actions before distribution.
