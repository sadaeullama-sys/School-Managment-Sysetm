Firebase Spark (Free) Cloud Sync update

Added in this source update:
- On the approved Principal account's device, core school module records sync to Firestore under:
  schools/{schoolId}/appData/{module}
- Synced modules: students, fees, attendance, marks, transport, salaries, expenses,
  notices, syllabus, date sheet, stock items, and stock issues.
- Local SharedPreferences remains the offline cache. Local writes are kept if the
  device is offline or Firestore sync fails; see debug log for sync errors.
- On load, if a cloud document exists it is downloaded into the local cache; if it
  does not exist, the local records are uploaded as the initial cloud copy.
- Existing Firestore rules already scope school subcollection access to the signed-in
  approved school owner. Keep those rules in place for this principal-only sync path.

Important limitations (do not treat as fully completed multi-role sync):
- Staff and Parent accounts and their credentials remain local only. They are
  intentionally excluded from cloud upload because the current app stores passwords
  in local records; uploading those passwords would be unsafe.
- Staff/Parent Firebase Authentication provisioning, per-module server-enforced
  permissions, and parent-only-child Firestore access are not implemented here.
  These need a separate secure account provisioning design and corresponding rules.
- This uses one Firestore document per module. Large school datasets may exceed
  Firestore document size limits; a production rollout should migrate records to
  individual documents/subcollections and add conflict/version handling.
- This update has not been compiled or device-tested here. Run `flutter pub get`,
  `flutter analyze`, and `flutter build apk --release` in GitHub Actions before use.
- Existing Spark plan quotas apply. Sync operations can consume Firestore reads/writes.
