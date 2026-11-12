اپڈیٹ نوٹ — Staff / Parent / PDF Print

اس ZIP میں اصل موجودہ پروجیکٹ اور اس کے تمام موجودہ Modules برقرار رکھے گئے ہیں۔

اس اپڈیٹ میں:
1) PDF کے چار مقامات پر sharePdf کو layoutPdf سے تبدیل کیا گیا ہے تاکہ Print Slip / متعلقہ PDF ایک Print Preview / print dialog کھولے۔
2) Staff Management، Parent Management اور ان کے موجودہ Local Login / approval / linked-child logic کو حذف یا تبدیل نہیں کیا گیا۔
3) باقی Dashboard، Students، Fees، Attendance، Exams، Stock، Syllabus، Date Sheet اور دوسرے موجودہ حصوں کو برقرار رکھا گیا ہے۔

اہم حد:
- یہ اپڈیٹ Staff/Parent کے موجودہ Local Storage طریقہ کو برقرار رکھتی ہے؛ اسے Firebase Cloud Sync میں تبدیل نہیں کیا گیا۔
- اس لیے مختلف موبائلز پر Staff/Parent اکاؤنٹس اور اسکول کا تمام ڈیٹا Sync ہونے کا دعویٰ نہیں ہے۔ اس کے لیے الگ Firebase implementation اور درست Firestore data model درکار ہے۔
- Flutter SDK اس ماحول میں دستیاب نہ ہونے کی وجہ سے APK build/test نہیں کیا گیا۔ GitHub Actions سے APK بنائیں اور Android پر Print Preview چیک کریں۔

Build: GitHub Actions > Actions > متعلقہ workflow > Run workflow
