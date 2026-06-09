# CImpReg::MethodAsync(ushort *,ushort *,long,IWbemContext *,IWbemClassObject *,IWbemObjectSink *)

- ea: `0x1800043c0`
- end: `0x1800064d0`
- name: `?MethodAsync@CImpReg@@UEAAJPEAG0JPEAUIWbemContext@@PEAUIWbemClassObject@@PEAUIWbemObjectSink@@@Z`
- size: `8464`
- prototype: `__int64 __fastcall(CImpReg *this, unsigned __int16 *, unsigned __int16 *, __int64, struct IWbemContext *, struct IWbemClassObject *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `27`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180002e10`
- `0x1800042f0`
- `0x180004390`
- `0x1800043c0`
- `0x1800064e0`
- `0x180006524`
- `0x180006fe0`
- `0x180007ca8`
- `0x180007d10`
- `0x180009774`
- `0x18000999c`
- `0x18000babc`
- `0x18000e3c0`
- `0x1800129d8`
- `0x180012a18`
- `0x180012a48`
- `0x180012a94`
- `0x180012ee8`
- `0x180012fe0`
- `0x180013138`
- `0x1800132f4`
- `0x18001345c`
- `0x1800136b4`
- `0x1800136f0`
- `0x180013838`
- `0x180015680`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800046d4`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800046d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006040`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006040`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800048ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000563e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006052`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800048ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000563e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006052`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800048df`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800048df`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180005628`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180005628`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800048c1`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800048c1`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800056e7`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800056e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000645d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000645d`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800055b8`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005603`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000567c`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800056c7`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005728`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005773`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800057be`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005809`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005854`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000589f`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800058ea`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005935`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005980`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800059cb`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005a59`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005aa4`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005aef`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005b3a`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005b85`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005bd0`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005c3d`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005c88`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005cd3`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005d1e`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005d69`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005db4`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005dff`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005e4a`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800055b8`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005603`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000567c`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800056c7`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005728`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005773`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800057be`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005809`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005854`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000589f`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800058ea`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005935`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005980`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800059cb`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005a59`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005aa4`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005aef`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005b3a`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005b85`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005bd0`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005c3d`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005c88`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005cd3`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005d1e`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005d69`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005db4`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005dff`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180005e4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006417`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800047bc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180004834`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800060bd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800047bc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180004834`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800060bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006150`
- `wbemcomn!ReadUI64` at `0x180005f5b`
- `wbemcomn!ReadUI64` at `0x180005f5b`
- `wbemcomn!?SetQWORD@Registry@@QEAAHPEBG_K@Z` at `0x180005f9a`
- `wbemcomn!?SetQWORD@Registry@@QEAAHPEBG_K@Z` at `0x180005f9a`
- `wbemcomn!??0CNtSecurityDescriptor@@QEAA@PEAX@Z` at `0x18000616b`
- `wbemcomn!??0CNtSecurityDescriptor@@QEAA@PEAX@Z` at `0x18000616b`
- `wbemcomn!??1CNtSecurityDescriptor@@QEAA@XZ` at `0x180006194`
- `wbemcomn!??1CNtSecurityDescriptor@@QEAA@XZ` at `0x180006194`
- `wbemcomn!BuildSecurityDescriptorParameter` at `0x180006187`
- `wbemcomn!BuildSecurityDescriptorParameter` at `0x180006187`
- `wbemcomn!GetSecurityDescriptorFromParameters` at `0x180006216`
- `wbemcomn!GetSecurityDescriptorFromParameters` at `0x180006216`
- `wbemcomn!?GetOwner@CNtSecurityDescriptor@@QEAAPEAVCNtSid@@XZ` at `0x180006236`
- `wbemcomn!?GetOwner@CNtSecurityDescriptor@@QEAAPEAVCNtSid@@XZ` at `0x180006236`
- `wbemcomn!?GetGroup@CNtSecurityDescriptor@@QEAAPEAVCNtSid@@XZ` at `0x180006248`
- `wbemcomn!?GetGroup@CNtSecurityDescriptor@@QEAAPEAVCNtSid@@XZ` at `0x180006248`
- `wbemcomn!?GetDacl@CNtSecurityDescriptor@@QEAAPEAVCNtAcl@@XZ` at `0x18000625a`
- `wbemcomn!?GetDacl@CNtSecurityDescriptor@@QEAAPEAVCNtAcl@@XZ` at `0x18000625a`
- `wbemcomn!?GetSacl@CNtSecurityDescriptor@@QEAAPEAVCNtAcl@@XZ` at `0x18000626d`
- `wbemcomn!?GetSacl@CNtSecurityDescriptor@@QEAAPEAVCNtAcl@@XZ` at `0x18000626d`
- `wbemcomn!?GetQWORD@Registry@@QEAAHPEBGPEA_K@Z` at `0x180005e6f`
- `wbemcomn!?GetQWORD@Registry@@QEAAHPEBGPEA_K@Z` at `0x180005e6f`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x180004f6d`
- `wbemcomn!?SetDWORD@Registry@@QEAAHPEBGK@Z` at `0x180004f6d`
- `wbemcomn!?GetStr@Registry@@QEAAHPEBGPEAPEAG@Z` at `0x180004a8b`
- `wbemcomn!?GetStr@Registry@@QEAAHPEBGPEAPEAG@Z` at `0x180004a8b`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180004abe`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180004f7b`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x1800050bf`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180005149`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x1800052da`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x1800059f6`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180005a15`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180005fa8`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180004abe`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180004f7b`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x1800050bf`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180005149`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x1800052da`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x1800059f6`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180005a15`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180005fa8`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z` at `0x180004a5f`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z` at `0x180004f4d`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z` at `0x180004ff4`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z` at `0x180005082`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z` at `0x180005f78`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z` at `0x180004a5f`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z` at `0x180004f4d`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z` at `0x180004ff4`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z` at `0x180005082`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z` at `0x180005f78`
- `wbemcomn!?GetType@Registry@@QEAAHPEBGPEAK@Z` at `0x180004aac`
- `wbemcomn!?GetType@Registry@@QEAAHPEBGPEAK@Z` at `0x180005027`
- `wbemcomn!?GetType@Registry@@QEAAHPEBGPEAK@Z` at `0x1800050ac`
- `wbemcomn!?GetType@Registry@@QEAAHPEBGPEAK@Z` at `0x180004aac`
- `wbemcomn!?GetType@Registry@@QEAAHPEBGPEAK@Z` at `0x180005027`
- `wbemcomn!?GetType@Registry@@QEAAHPEBGPEAK@Z` at `0x1800050ac`
- `wbemcomn!GetMemLogObject` at `0x180005215`
- `wbemcomn!GetMemLogObject` at `0x1800053ba`
- `wbemcomn!GetMemLogObject` at `0x180005414`
- `wbemcomn!GetMemLogObject` at `0x180005475`
- `wbemcomn!GetMemLogObject` at `0x1800054c9`
- `wbemcomn!GetMemLogObject` at `0x180005533`
- `wbemcomn!GetMemLogObject` at `0x18000633e`
- `wbemcomn!GetMemLogObject` at `0x18000639c`
- `wbemcomn!GetMemLogObject` at `0x180006475`
- `wbemcomn!GetMemLogObject` at `0x180005215`
- `wbemcomn!GetMemLogObject` at `0x1800053ba`
- `wbemcomn!GetMemLogObject` at `0x180005414`
- `wbemcomn!GetMemLogObject` at `0x180005475`
- `wbemcomn!GetMemLogObject` at `0x1800054c9`
- `wbemcomn!GetMemLogObject` at `0x180005533`
- `wbemcomn!GetMemLogObject` at `0x18000633e`
- `wbemcomn!GetMemLogObject` at `0x18000639c`
- `wbemcomn!GetMemLogObject` at `0x180006475`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180005220`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800053c8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180005420`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180005480`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800054d4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000553e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000634a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800063a8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180006483`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180005220`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800053c8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180005420`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180005480`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800054d4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000553e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000634a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800063a8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180006483`
- `wbemcomn!ErrorTrace` at `0x180006430`
- `wbemcomn!ErrorTrace` at `0x180006452`
- `wbemcomn!ErrorTrace` at `0x180006430`
- `wbemcomn!ErrorTrace` at `0x180006452`
- `wbemcomn!DebugTrace` at `0x18000640f`
- `wbemcomn!DebugTrace` at `0x18000640f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180004b6f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180004b79`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800051ca`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180005a0a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800061a9`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180004b6f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180004b79`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800051ca`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180005a0a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800061a9`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800045d1`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000468b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800045d1`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000468b`
- `wbemcomn!?GetDWORD@Registry@@QEAAHPEBGPEAK@Z` at `0x180005299`

## string_xrefs

- `0x18000484e`: `DeleteValue`
- `0x1800047d6`: `DeleteKey`
- `0x18000472b`: `CreateKey`
- `0x180006446`: `Registry event provider unable to CoImpersonateClient hr2= 0x%x.\n`
- `0x180005fd5`: `CheckAccess`
- `0x1800060a3`: `GetSecurityDescriptor`
- `0x1800061b4`: `SetSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall CImpReg::MethodAsync(
        CImpReg *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        __int64 a4,
        struct IWbemContext *a5,
        struct IWbemClassObject *a6,
        struct IWbemObjectSink *a7)
{
  OLECHAR *v9; // rax
  OLECHAR *v10; // r12
  int v11; // ebx
  struct IWbemClassObject *v12; // rdi
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // rax
  unsigned int v16; // ebx
  unsigned __int16 *v17; // rax
  WCHAR *v18; // r13
  WCHAR *v19; // rsi
  __int64 v20; // rax
  unsigned int v21; // ebx
  WCHAR *v22; // rax
  HRESULT SecurityDescriptorFromParameters; // r12d
  ACL *v24; // r15
  const wchar_t *v25; // r14
  LPCWSTR i; // rsi
  WCHAR v27; // bx
  WCHAR v28; // cx
  const wchar_t *v29; // r14
  LPCWSTR j; // rsi
  WCHAR v31; // bx
  WCHAR v32; // cx
  const wchar_t *v33; // r14
  LPCWSTR k; // rsi
  WCHAR v35; // bx
  WCHAR v36; // cx
  unsigned __int16 *v37; // r14
  const wchar_t *v38; // r14
  LPCWSTR v39; // rsi
  WCHAR v40; // bx
  WCHAR v41; // cx
  const wchar_t *v42; // r14
  LPCWSTR v43; // rsi
  WCHAR v44; // bx
  WCHAR v45; // cx
  const wchar_t *v46; // r14
  LPCWSTR v47; // rsi
  WCHAR v48; // bx
  WCHAR v49; // cx
  struct IWbemClassObject *v50; // rsi
  struct IWbemObjectSink *v51; // rbx
  int v52; // eax
  const wchar_t *v54; // rsi
  LPCWSTR m; // r14
  WCHAR v56; // bx
  WCHAR v57; // cx
  const wchar_t *v58; // rsi
  LPCWSTR n; // r14
  WCHAR v60; // bx
  WCHAR v61; // cx
  const wchar_t *v62; // rsi
  LPCWSTR ii; // r14
  WCHAR v64; // bx
  WCHAR v65; // cx
  const wchar_t *v66; // rsi
  LPCWSTR jj; // r14
  WCHAR v68; // bx
  WCHAR v69; // cx
  const wchar_t *v70; // rsi
  LPCWSTR kk; // r14
  WCHAR v72; // bx
  WCHAR v73; // cx
  int BinaryValue; // eax
  const wchar_t *v75; // rsi
  LPCWSTR mm; // r14
  WCHAR v77; // bx
  WCHAR v78; // cx
  const wchar_t *v79; // rsi
  LPCWSTR nn; // r14
  WCHAR v81; // bx
  WCHAR v82; // cx
  LONG lVal; // ebx
  const wchar_t *v84; // rsi
  LPCWSTR i1; // r14
  WCHAR v86; // bx
  WCHAR v87; // cx
  int v88; // eax
  const unsigned __int16 *v89; // rbx
  int v90; // eax
  HKEY v91; // rbx
  __int64 v92; // r8
  CMemoryLog *v93; // rax
  OLECHAR *v94; // rcx
  CMemoryLog *MemLogObject; // rax
  __int64 v96; // r8
  _QWORD *v97; // rcx
  __int64 v98; // rdx
  CMemoryLog *v99; // rax
  __int64 v100; // r8
  CMemoryLog *v101; // rax
  __int64 v102; // r8
  CMemoryLog *v103; // rax
  __int64 v104; // r8
  __int64 v105; // r8
  CMemoryLog *v106; // rax
  int v107; // eax
  int v108; // eax
  int v109; // eax
  int v110; // eax
  int v111; // eax
  int v112; // eax
  int v113; // eax
  int v114; // eax
  int v115; // eax
  int v116; // eax
  int v117; // eax
  int v118; // eax
  int v119; // eax
  int v120; // eax
  int v121; // eax
  int v122; // eax
  int v123; // eax
  int v124; // eax
  int v125; // eax
  int v126; // eax
  int v127; // eax
  int v128; // eax
  int v129; // eax
  int v130; // eax
  int v131; // eax
  int v132; // eax
  int v133; // eax
  int v134; // eax
  int v135; // eax
  WCHAR *v136; // rbx
  int v137; // eax
  SECURITY_INFORMATION v138; // r8d
  void *v139; // r12
  ACL *v140; // r13
  void **Owner; // rbx
  void **Group; // r14
  HKEY Dacl; // rsi
  ACL **Sacl; // rdx
  int v145; // ecx
  void *v146; // r9
  int v147; // eax
  SECURITY_INFORMATION v148; // r8d
  CMemoryLog *v149; // rax
  __int64 v150; // r8
  CMemoryLog *v151; // rax
  __int64 v152; // r8
  DWORD LastError; // eax
  int v154; // eax
  CMemoryLog *v155; // rax
  int lpDestStr; // [rsp+20h] [rbp-E0h]
  WCHAR DestStr; // [rsp+40h] [rbp-C0h] BYREF
  void *ppInterface; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpValueName; // [rsp+58h] [rbp-A8h]
  LPCWSTR pObjectName; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  struct IWbemClassObject *v163; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG v164; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-70h] BYREF
  struct IWbemClassObject *v166; // [rsp+A8h] [rbp-58h]
  int v167; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE hToken[2]; // [rsp+B8h] [rbp-48h]
  BSTR bstrString; // [rsp+C8h] [rbp-38h]
  LPWSTR v170; // [rsp+D0h] [rbp-30h] BYREF
  VARIANTARG v171; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v172; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v173; // [rsp+F8h] [rbp-8h] BYREF
  CImpReg *v174; // [rsp+100h] [rbp+0h] BYREF
  void *v175; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v176[8]; // [rsp+110h] [rbp+10h] BYREF
  void (*v177)(void); // [rsp+118h] [rbp+18h]
  unsigned __int16 *v178; // [rsp+120h] [rbp+20h]
  struct IWbemObjectSink *v179; // [rsp+128h] [rbp+28h]
  _BYTE v180[20]; // [rsp+130h] [rbp+30h] BYREF
  int v181; // [rsp+144h] [rbp+44h]
  _QWORD v182[2]; // [rsp+148h] [rbp+48h] BYREF
  _QWORD v183[4]; // [rsp+158h] [rbp+58h] BYREF
  VARIANTARG v184; // [rsp+178h] [rbp+78h] BYREF

  pObjectName = a3;
  v174 = this;
  v170 = (LPWSTR)a5;
  phkResult = (HKEY)a6;
  v179 = a7;
  v173 = 0;
  v172 = 0;
  v163 = 0;
  v167 = 0;
  *(_OWORD *)hToken = 0;
  if ( !a7 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217400);
    v97 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_448;
    }
    v98 = 21;
    goto LABEL_447;
  }
  if ( !a2 || !a3 || !a6 )
  {
    SetStatusAndReturn(-2147217400, a7);
    v155 = GetMemLogObject();
    CMemoryLog::Write(v155, -2147217400);
    v97 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_448;
    }
    v98 = 22;
LABEL_447:
    WPP_SF_D(v97[2], v98, v96, 2147749896LL);
LABEL_448:
    AutoProfile::~AutoProfile((AutoProfile *)&v167);
    return 2147749896LL;
  }
  v9 = SysAllocString(L"StdRegProv");
  v10 = v9;
  bstrString = v9;
  if ( !v9 )
  {
    SetStatusAndReturn(-2147217402, a7);
    v99 = GetMemLogObject();
    CMemoryLog::Write(v99, -2147217402);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v100, 2147749894LL);
    }
    AutoProfile::~AutoProfile((AutoProfile *)&v167);
    return 2147749894LL;
  }
  v183[3] = v9;
  v11 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, _QWORD, struct IWbemContext *, __int64 *, _QWORD))(**((_QWORD **)this + 3) + 48LL))(
          *((_QWORD *)this + 3),
          v9,
          0,
          a5,
          &v173,
          0);
  if ( !v11 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v173 + 152LL))(
            v173,
            a3,
            0,
            0,
            &v172);
    if ( !v11 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IWbemClassObject **))(*(_QWORD *)v172 + 120LL))(
              v172,
              0,
              &v163);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v172 + 16LL))(v172);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v173 + 16LL))(v173);
  }
  if ( v11 < 0 )
  {
    SetStatusAndReturn(v11, a7);
    v101 = GetMemLogObject();
    CMemoryLog::Write(v101, v11);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, v102, (unsigned int)v11);
    }
    v94 = v10;
    goto LABEL_260;
  }
  v12 = v163;
  v166 = v163;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v13 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a6->lpVtbl->Get)(
          a6,
          L"hDefKey",
          0,
          &pvarg,
          0,
          0);
  v14 = v13;
  if ( v13 < 0 )
  {
    SetStatusAndReturn(v13, a7);
    v103 = GetMemLogObject();
    CMemoryLog::Write(v103, v14);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v104, v14);
    }
    if ( v12 )
      ((void (__fastcall *)(struct IWbemClassObject *))v12->lpVtbl->Release)(v12);
    goto LABEL_247;
  }
  hKey = (HKEY)pvarg.lVal;
  v178 = 0;
  memset(&v171, 0, sizeof(v171));
  VariantInit(&v171);
  if ( ((unsigned int (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a6->lpVtbl->Get)(
         a6,
         L"sSubKeyName",
         0,
         &v171,
         0,
         0) )
  {
    goto LABEL_239;
  }
  if ( v171.vt != 8 )
    goto LABEL_239;
  v15 = -1;
  do
    ++v15;
  while ( *(_WORD *)(v171.llVal + 2 * v15) );
  v16 = v15 + 1;
  v17 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)(v15 + 1), 2u));
  v18 = v17;
  v178 = v17;
  if ( !v17 )
  {
LABEL_239:
    VariantClear(&v171);
    v14 = SetStatusAndReturn(-2147217400, a7);
    if ( (v14 & 0x80000000) != 0 )
    {
      v93 = GetMemLogObject();
      CMemoryLog::Write(v93, v14);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v92, v14);
    }
    if ( v12 )
      ((void (__fastcall *)(struct IWbemClassObject *))v12->lpVtbl->Release)(v12);
LABEL_247:
    v166 = 0;
    SysFreeString(v10);
    AutoProfile::~AutoProfile((AutoProfile *)&v167);
    return v14;
  }
  StringCchCopyW(v17, v16, v171.bstrVal);
  VariantClear(&v171);
  v183[0] = v18;
  v183[1] = 0;
  v19 = 0;
  lpValueName = 0;
  memset(&v184, 0, sizeof(v184));
  VariantInit(&v184);
  if ( !((unsigned int (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a6->lpVtbl->Get)(
          a6,
          L"sValueName",
          0,
          &v184,
          0,
          0)
    && v184.vt == 8 )
  {
    v20 = -1;
    do
      ++v20;
    while ( *(_WORD *)(v184.llVal + 2 * v20) );
    v21 = v20 + 1;
    v22 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)(v20 + 1), 2u));
    v19 = v22;
    lpValueName = v22;
    if ( v22 )
      StringCchCopyW(v22, v21, v184.bstrVal);
  }
  VariantClear(&v184);
  v182[0] = v19;
  v182[1] = 0;
  ppInterface = 0;
  SecurityDescriptorFromParameters = CoGetCallContext(&IID_IServerSecurity, &ppInterface);
  if ( !SecurityDescriptorFromParameters )
  {
    SecurityDescriptorFromParameters = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 16LL))(ppInterface);
  }
  if ( SecurityDescriptorFromParameters < 0 )
  {
    v11 = SetStatusAndReturn(SecurityDescriptorFromParameters, a7);
    if ( v11 < 0 )
    {
      v106 = GetMemLogObject();
      CMemoryLog::Write(v106, v11);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, v105, (unsigned int)v11);
    }
    CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v182);
    CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v183);
    if ( v12 )
      ((void (__fastcall *)(struct IWbemClassObject *))v12->lpVtbl->Release)(v12);
    v166 = 0;
    v94 = bstrString;
LABEL_260:
    SysFreeString(v94);
    AutoProfile::~AutoProfile((AutoProfile *)&v167);
    return (unsigned int)v11;
  }
  MakeGuard<long (*)(void)>(v176);
  if ( hKey == HKEY_CURRENT_USER )
  {
    v90 = AutoProfile::LoadProfile((AutoProfile *)&v167, &hKey);
    SecurityDescriptorFromParameters = v90;
    if ( v90 < 0 )
    {
      SetStatusAndReturn(v90, a7);
      if ( !v176[0] )
        v177();
      CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v182);
      CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v183);
      if ( v12 )
        ((void (__fastcall *)(struct IWbemClassObject *))v12->lpVtbl->Release)(v12);
      v166 = 0;
      SysFreeString(bstrString);
      AutoProfile::~AutoProfile((AutoProfile *)&v167);
      return 0;
    }
  }
  v24 = 0;
  v25 = L"CreateKey";
  for ( i = pObjectName; ; ++i )
  {
    v27 = *i;
    if ( *i )
    {
      if ( v27 > 0x7Fu )
      {
        LOWORD(ppInterface) = *i;
        DestStr = 0;
        v107 = LCMapStringW(0x7Fu, 0x100u, (LPCWSTR)&ppInterface, 1, &DestStr, 1);
        v27 = DestStr;
        if ( !v107 )
          v27 = (unsigned __int16)ppInterface;
      }
      else if ( (unsigned __int16)(v27 - 65) <= 0x19u )
      {
        v27 += 32;
      }
    }
    else if ( !*v25 )
    {
      phkResult = 0;
      if ( lstrlenW(v18) < 1 )
      {
        SecurityDescriptorFromParameters = -2147217400;
        goto LABEL_429;
      }
      LODWORD(v24) = RegCreateKeyW(hKey, v18, &phkResult);
      if ( !(_DWORD)v24 )
        RegCloseKey(phkResult);
      goto LABEL_235;
    }
    v28 = *v25;
    if ( *v25 > 0x7Fu )
    {
      DestStr = *v25;
      LOWORD(ppInterface) = 0;
      v108 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
      v28 = (unsigned __int16)ppInterface;
      if ( !v108 )
        v28 = DestStr;
    }
    else if ( (unsigned __int16)(v28 - 65) <= 0x19u )
    {
      v28 += 32;
    }
    if ( v27 != v28 )
      break;
    ++v25;
  }
  v29 = L"DeleteKey";
  for ( j = pObjectName; ; ++j )
  {
    v31 = *j;
    if ( *j )
    {
      if ( v31 > 0x7Fu )
      {
        DestStr = *j;
        LOWORD(ppInterface) = 0;
        v109 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
        v31 = (unsigned __int16)ppInterface;
        if ( !v109 )
          v31 = DestStr;
      }
      else if ( (unsigned __int16)(v31 - 65) <= 0x19u )
      {
        v31 += 32;
      }
    }
    else if ( !*v29 )
    {
      if ( lstrlenW(v18) < 1 )
      {
        SecurityDescriptorFromParameters = -2147217400;
        goto LABEL_429;
      }
      LODWORD(v24) = RegDeleteKeyW(hKey, v18);
      goto LABEL_235;
    }
    v32 = *v29;
    if ( *v29 > 0x7Fu )
    {
      DestStr = *v29;
      LOWORD(ppInterface) = 0;
      v110 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
      v32 = (unsigned __int16)ppInterface;
      if ( !v110 )
        v32 = DestStr;
    }
    else if ( (unsigned __int16)(v32 - 65) <= 0x19u )
    {
      v32 += 32;
    }
    if ( v31 != v32 )
      break;
    ++v29;
  }
  v33 = L"DeleteValue";
  for ( k = pObjectName; ; ++k )
  {
    v35 = *k;
    if ( *k )
    {
      if ( v35 > 0x7Fu )
      {
        DestStr = *k;
        LOWORD(ppInterface) = 0;
        v111 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
        v35 = (unsigned __int16)ppInterface;
        if ( !v111 )
          v35 = DestStr;
      }
      else if ( (unsigned __int16)(v35 - 65) <= 0x19u )
      {
        v35 += 32;
      }
    }
    else if ( !*v33 )
    {
      phkResult = 0;
      LODWORD(v24) = RegOpenKeyW(hKey, v18, &phkResult);
      if ( !(_DWORD)v24 )
      {
        v37 = (unsigned __int16 *)lpValueName;
        LODWORD(v24) = RegDeleteValueW(phkResult, lpValueName);
        RegCloseKey(phkResult);
        goto LABEL_105;
      }
      goto LABEL_235;
    }
    v36 = *v33;
    if ( *v33 > 0x7Fu )
    {
      DestStr = *v33;
      LOWORD(ppInterface) = 0;
      v112 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
      v36 = (unsigned __int16)ppInterface;
      if ( !v112 )
        v36 = DestStr;
    }
    else if ( (unsigned __int16)(v36 - 65) <= 0x19u )
    {
      v36 += 32;
    }
    if ( v35 != v36 )
      break;
    ++v33;
  }
  v38 = L"EnumKey";
  v39 = pObjectName;
  while ( 2 )
  {
    v40 = *v39;
    if ( !*v39 )
    {
      if ( *v38 )
        goto LABEL_71;
      LODWORD(v24) = EnumKey(hKey, v18, v163);
      goto LABEL_235;
    }
    if ( v40 > 0x7Fu )
    {
      DestStr = *v39;
      LOWORD(ppInterface) = 0;
      v113 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
      v40 = (unsigned __int16)ppInterface;
      if ( !v113 )
        v40 = DestStr;
    }
    else if ( (unsigned __int16)(v40 - 65) <= 0x19u )
    {
      v40 += 32;
    }
LABEL_71:
    v41 = *v38;
    if ( *v38 > 0x7Fu )
    {
      DestStr = *v38;
      LOWORD(ppInterface) = 0;
      v114 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
      v41 = (unsigned __int16)ppInterface;
      if ( !v114 )
        v41 = DestStr;
    }
    else if ( (unsigned __int16)(v41 - 65) <= 0x19u )
    {
      v41 += 32;
    }
    if ( v40 == v41 )
    {
      ++v39;
      ++v38;
      continue;
    }
    break;
  }
  v42 = L"EnumValues";
  v43 = pObjectName;
  while ( 2 )
  {
    v44 = *v43;
    if ( !*v43 )
    {
      if ( *v42 )
        goto LABEL_83;
      LODWORD(v24) = EnumValue(hKey, v18, v163);
LABEL_235:
      v37 = (unsigned __int16 *)lpValueName;
      goto LABEL_105;
    }
    if ( v44 > 0x7Fu )
    {
      DestStr = *v43;
      LOWORD(ppInterface) = 0;
      v115 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
      v44 = (unsigned __int16)ppInterface;
      if ( !v115 )
        v44 = DestStr;
    }
    else if ( (unsigned __int16)(v44 - 65) <= 0x19u )
    {
      v44 += 32;
    }
LABEL_83:
    v45 = *v42;
    if ( *v42 > 0x7Fu )
    {
      DestStr = *v42;
      LOWORD(ppInterface) = 0;
      v116 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
      v45 = (unsigned __int16)ppInterface;
      if ( !v116 )
        v45 = DestStr;
    }
    else if ( (unsigned __int16)(v45 - 65) <= 0x19u )
    {
      v45 += 32;
    }
    if ( v44 == v45 )
    {
      ++v43;
      ++v42;
      continue;
    }
    break;
  }
  v46 = L"GetStringValue";
  v47 = pObjectName;
  while ( 2 )
  {
    v48 = *v47;
    if ( !*v47 )
    {
      if ( *v46 )
        goto LABEL_95;
LABEL_101:
      v50 = v163;
      Registry::Registry((Registry *)v180, hKey, 1u, v18);
      LODWORD(v24) = v181;
      if ( !v181 )
      {
        phkResult = 0;
        v37 = (unsigned __int16 *)lpValueName;
        LODWORD(v24) = Registry::GetStr((Registry *)v180, lpValueName, (unsigned __int16 **)&phkResult);
        if ( (_DWORD)v24 )
        {
          LODWORD(ppInterface) = 0;
          if ( !Registry::GetType((Registry *)v180, v37, (unsigned int *)&ppInterface)
            && (unsigned int)((_DWORD)ppInterface - 1) > 1 )
          {
            Registry::~Registry((Registry *)v180);
            LODWORD(v24) = -2147217403;
            goto LABEL_105;
          }
        }
        else
        {
          v91 = phkResult;
          v175 = phkResult;
          memset(&v164, 0, sizeof(v164));
          v164.llVal = (LONGLONG)SysAllocString((const OLECHAR *)phkResult);
          v164.vt = 8;
          if ( !v164.llVal )
          {
            CWin32DefaultArena::WbemMemFree(v91);
            Registry::~Registry((Registry *)v180);
            LODWORD(v24) = -2147217402;
LABEL_105:
            if ( SecurityDescriptorFromParameters < 0 )
              goto LABEL_430;
            goto LABEL_106;
          }
          LODWORD(v24) = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))v50->lpVtbl->Put)(
                           v50,
                           L"sValue",
                           0,
                           &v164,
                           0);
          VariantClear(&v164);
          CWin32DefaultArena::WbemMemFree(v91);
        }
        Registry::~Registry((Registry *)v180);
        goto LABEL_105;
      }
      Registry::~Registry((Registry *)v180);
      goto LABEL_235;
    }
    if ( v48 > 0x7Fu )
    {
      DestStr = *v47;
      LOWORD(ppInterface) = 0;
      v117 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
      v48 = (unsigned __int16)ppInterface;
      if ( !v117 )
        v48 = DestStr;
    }
    else if ( (unsigned __int16)(v48 - 65) <= 0x19u )
    {
      v48 += 32;
    }
LABEL_95:
    v49 = *v46;
    if ( *v46 > 0x7Fu )
    {
      DestStr = *v46;
      LOWORD(ppInterface) = 0;
      v118 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
      v49 = (unsigned __int16)ppInterface;
      if ( !v118 )
        v49 = DestStr;
    }
    else if ( (unsigned __int16)(v49 - 65) <= 0x19u )
    {
      v49 += 32;
    }
    if ( v48 == v49 )
    {
      ++v47;
      ++v46;
      continue;
    }
    break;
  }
  v54 = L"GetExpandedStringValue";
  for ( m = pObjectName; ; ++m )
  {
    v56 = *m;
    if ( *m )
    {
      if ( v56 > 0x7Fu )
      {
        DestStr = *m;
        LOWORD(ppInterface) = 0;
        v119 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
        v56 = (unsigned __int16)ppInterface;
        if ( !v119 )
          v56 = DestStr;
      }
      else if ( (unsigned __int16)(v56 - 65) <= 0x19u )
      {
        v56 += 32;
      }
    }
    else if ( !*v54 )
    {
      goto LABEL_101;
    }
    v57 = *v54;
    if ( *v54 > 0x7Fu )
    {
      DestStr = *v54;
      LOWORD(ppInterface) = 0;
      v120 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
      v57 = (unsigned __int16)ppInterface;
      if ( !v120 )
        v57 = DestStr;
    }
    else if ( (unsigned __int16)(v57 - 65) <= 0x19u )
    {
      v57 += 32;
    }
    if ( v56 != v57 )
      break;
    ++v54;
  }
  v58 = L"SetMultiStringValue";
  for ( n = pObjectName; ; ++n )
  {
    v60 = *n;
    if ( *n )
    {
      if ( v60 > 0x7Fu )
      {
        DestStr = *n;
        LOWORD(ppInterface) = 0;
        v121 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
        v60 = (unsigned __int16)ppInterface;
        if ( !v121 )
          v60 = DestStr;
      }
      else if ( (unsigned __int16)(v60 - 65) <= 0x19u )
      {
        v60 += 32;
      }
    }
    else if ( !*v58 )
    {
      v37 = (unsigned __int16 *)lpValueName;
      LODWORD(v24) = SetMultiStrValue(hKey, v18, (unsigned __int16 *)lpValueName, (struct IWbemClassObject *)phkResult);
      goto LABEL_105;
    }
    v61 = *v58;
    if ( *v58 > 0x7Fu )
    {
      DestStr = *v58;
      LOWORD(ppInterface) = 0;
      v122 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
      v61 = (unsigned __int16)ppInterface;
      if ( !v122 )
        v61 = DestStr;
    }
    else if ( (unsigned __int16)(v61 - 65) <= 0x19u )
    {
      v61 += 32;
    }
    if ( v60 != v61 )
      break;
    ++v58;
  }
  v62 = L"GetMultiStringValue";
  for ( ii = pObjectName; ; ++ii )
  {
    v64 = *ii;
    if ( *ii )
    {
      if ( v64 > 0x7Fu )
      {
        DestStr = *ii;
        LOWORD(ppInterface) = 0;
        v123 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
        v64 = (unsigned __int16)ppInterface;
        if ( !v123 )
          v64 = DestStr;
      }
      else if ( (unsigned __int16)(v64 - 65) <= 0x19u )
      {
        v64 += 32;
      }
    }
    else if ( !*v62 )
    {
      v37 = (unsigned __int16 *)lpValueName;
      LODWORD(v24) = GetMultiStrValue(hKey, v18, (unsigned __int16 *)lpValueName, v163);
      goto LABEL_105;
    }
    v65 = *v62;
    if ( *v62 > 0x7Fu )
    {
      DestStr = *v62;
      LOWORD(ppInterface) = 0;
      v124 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
      v65 = (unsigned __int16)ppInterface;
      if ( !v124 )
        v65 = DestStr;
    }
    else if ( (unsigned __int16)(v65 - 65) <= 0x19u )
    {
      v65 += 32;
    }
    if ( v64 != v65 )
      break;
    ++v62;
  }
  v66 = L"SetExpandedStringValue";
  for ( jj = pObjectName; ; ++jj )
  {
    v68 = *jj;
    if ( *jj )
    {
      if ( v68 > 0x7Fu )
      {
        DestStr = *jj;
        LOWORD(ppInterface) = 0;
        v125 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
        v68 = (unsigned __int16)ppInterface;
        if ( !v125 )
          v68 = DestStr;
      }
      else if ( (unsigned __int16)(v68 - 65) <= 0x19u )
      {
        v68 += 32;
      }
    }
    else if ( !*v66 )
    {
      lpDestStr = 1;
LABEL_180:
      v37 = (unsigned __int16 *)lpValueName;
      BinaryValue = SetStringValue(hKey, v18, lpValueName, phkResult, lpDestStr);
LABEL_356:
      LODWORD(v24) = BinaryValue;
      goto LABEL_105;
    }
    v69 = *v66;
    if ( *v66 > 0x7Fu )
    {
      DestStr = *v66;
      LOWORD(ppInterface) = 0;
      v126 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
      v69 = (unsigned __int16)ppInterface;
      if ( !v126 )
        v69 = DestStr;
    }
    else if ( (unsigned __int16)(v69 - 65) <= 0x19u )
    {
      v69 += 32;
    }
    if ( v68 != v69 )
      break;
    ++v66;
  }
  v70 = L"SetStringValue";
  for ( kk = pObjectName; ; ++kk )
  {
    v72 = *kk;
    if ( *kk )
    {
      if ( v72 > 0x7Fu )
      {
        DestStr = *kk;
        LOWORD(ppInterface) = 0;
        v127 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
        v72 = (unsigned __int16)ppInterface;
        if ( !v127 )
          v72 = DestStr;
      }
      else if ( (unsigned __int16)(v72 - 65) <= 0x19u )
      {
        v72 += 32;
      }
    }
    else if ( !*v70 )
    {
      lpDestStr = 0;
      goto LABEL_180;
    }
    v73 = *v70;
    if ( *v70 > 0x7Fu )
    {
      DestStr = *v70;
      LOWORD(ppInterface) = 0;
      v128 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
      v73 = (unsigned __int16)ppInterface;
      if ( !v128 )
        v73 = DestStr;
    }
    else if ( (unsigned __int16)(v73 - 65) <= 0x19u )
    {
      v73 += 32;
    }
    if ( v72 != v73 )
      break;
    ++v70;
  }
  v75 = L"SetBinaryValue";
  for ( mm = pObjectName; ; ++mm )
  {
    v77 = *mm;
    if ( *mm )
    {
      if ( v77 > 0x7Fu )
      {
        DestStr = *mm;
        LOWORD(ppInterface) = 0;
        v129 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
        v77 = (unsigned __int16)ppInterface;
        if ( !v129 )
          v77 = DestStr;
      }
      else if ( (unsigned __int16)(v77 - 65) <= 0x19u )
      {
        v77 += 32;
      }
    }
    else if ( !*v75 )
    {
      v37 = (unsigned __int16 *)lpValueName;
      BinaryValue = SetBinaryValue(hKey, v18, (unsigned __int16 *)lpValueName, (struct IWbemClassObject *)phkResult);
      goto LABEL_356;
    }
    v78 = *v75;
    if ( *v75 > 0x7Fu )
    {
      DestStr = *v75;
      LOWORD(ppInterface) = 0;
      v130 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
      v78 = (unsigned __int16)ppInterface;
      if ( !v130 )
        v78 = DestStr;
    }
    else if ( (unsigned __int16)(v78 - 65) <= 0x19u )
    {
      v78 += 32;
    }
    if ( v77 != v78 )
      break;
    ++v75;
  }
  v79 = L"SetDWORDValue";
  for ( nn = pObjectName; ; ++nn )
  {
    v81 = *nn;
    if ( *nn )
    {
      if ( v81 > 0x7Fu )
      {
        DestStr = *nn;
        LOWORD(ppInterface) = 0;
        v131 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
        v81 = (unsigned __int16)ppInterface;
        if ( !v131 )
          v81 = DestStr;
      }
      else if ( (unsigned __int16)(v81 - 65) <= 0x19u )
      {
        v81 += 32;
      }
    }
    else if ( !*v79 )
    {
      LODWORD(v24) = (*(__int64 (__fastcall **)(HKEY, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)phkResult + 32LL))(
                       phkResult,
                       L"uValue",
                       0,
                       &pvarg,
                       0,
                       0);
      if ( (_DWORD)v24 )
        goto LABEL_235;
      lVal = pvarg.lVal;
      Registry::Registry((Registry *)&v164, hKey, 2u, v18);
      LODWORD(v24) = *((_DWORD *)&v164.decVal + 5);
      v37 = (unsigned __int16 *)lpValueName;
      if ( !*((_DWORD *)&v164.decVal + 5) )
        LODWORD(v24) = Registry::SetDWORD((Registry *)&v164, lpValueName, lVal);
      goto LABEL_251;
    }
    v82 = *v79;
    if ( *v79 > 0x7Fu )
    {
      DestStr = *v79;
      LOWORD(ppInterface) = 0;
      v132 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
      v82 = (unsigned __int16)ppInterface;
      if ( !v132 )
        v82 = DestStr;
    }
    else if ( (unsigned __int16)(v82 - 65) <= 0x19u )
    {
      v82 += 32;
    }
    if ( v81 != v82 )
      break;
    ++v79;
  }
  v84 = L"GetDWORDValue";
  for ( i1 = pObjectName; ; ++i1 )
  {
    v86 = *i1;
    if ( *i1 )
    {
      if ( v86 > 0x7Fu )
      {
        DestStr = *i1;
        LOWORD(ppInterface) = 0;
        v133 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
        v86 = (unsigned __int16)ppInterface;
        if ( !v133 )
          v86 = DestStr;
      }
      else if ( (unsigned __int16)(v86 - 65) <= 0x19u )
      {
        v86 += 32;
      }
    }
    else if ( !*v84 )
    {
      Registry::Registry((Registry *)&v164, hKey, 1u, v18);
      LODWORD(v24) = *((_DWORD *)&v164.decVal + 5);
      v37 = (unsigned __int16 *)lpValueName;
      if ( *((_DWORD *)&v164.decVal + 5)
        || (LODWORD(v24) = Registry::GetDWORD((Registry *)&v164, lpValueName, (unsigned int *)&pvarg.cyVal), (_DWORD)v24) )
      {
        LODWORD(ppInterface) = 0;
        if ( Registry::GetType((Registry *)&v164, v37, (unsigned int *)&ppInterface) )
          goto LABEL_251;
        v88 = (int)v24;
        if ( (_DWORD)ppInterface != 4 )
          v88 = -2147217403;
      }
      else
      {
        pvarg.vt = 3;
        v88 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))v163->lpVtbl->Put)(
                v163,
                L"uValue",
                0,
                &pvarg,
                0);
      }
      LODWORD(v24) = v88;
      goto LABEL_251;
    }
    v87 = *v84;
    if ( *v84 > 0x7Fu )
    {
      DestStr = *v84;
      LOWORD(ppInterface) = 0;
      v134 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, (LPWSTR)&ppInterface, 1);
      v87 = (unsigned __int16)ppInterface;
      if ( !v134 )
        v87 = DestStr;
    }
    else if ( (unsigned __int16)(v87 - 65) <= 0x19u )
    {
      v87 += 32;
    }
    if ( v86 != v87 )
      break;
    ++v84;
  }
  v89 = pObjectName;
  if ( !(unsigned int)wbem_wcsicmp(pObjectName, L"GetQWORDValue") )
  {
    phkResult = 0;
    Registry::Registry((Registry *)&v164, hKey, 1u, v18);
    LODWORD(v24) = *((_DWORD *)&v164.decVal + 5);
    v37 = (unsigned __int16 *)lpValueName;
    if ( *((_DWORD *)&v164.decVal + 5)
      || (LODWORD(v24) = Registry::GetQWORD((Registry *)&v164, lpValueName, (unsigned __int64 *)&phkResult), (_DWORD)v24) )
    {
      LODWORD(ppInterface) = 0;
      if ( Registry::GetType((Registry *)&v164, v37, (unsigned int *)&ppInterface) )
        goto LABEL_251;
      v135 = (int)v24;
      if ( (_DWORD)ppInterface != 11 )
        v135 = -2147217403;
    }
    else
    {
      StringCchPrintfW(&v184.vt, 0x16u, L"%I64u", phkResult);
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)SysAllocString(&v184.vt);
      if ( !pvarg.llVal )
      {
        LODWORD(v24) = -2147217402;
        goto LABEL_251;
      }
      v135 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))v163->lpVtbl->Put)(
               v163,
               L"uValue",
               0,
               &pvarg,
               0);
    }
    LODWORD(v24) = v135;
LABEL_251:
    Registry::~Registry((Registry *)&v164);
    goto LABEL_105;
  }
  if ( !(unsigned int)wbem_wcsicmp(v89, L"SetQWORDValue") )
  {
    LODWORD(v24) = (*(__int64 (__fastcall **)(HKEY, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)phkResult + 32LL))(
                     phkResult,
                     L"uValue",
                     0,
                     &pvarg,
                     0,
                     0);
    if ( (_DWORD)v24 )
      goto LABEL_235;
    phkResult = 0;
    if ( !ReadUI64(pvarg.bstrVal, (unsigned __int64 *)&phkResult) )
    {
      LODWORD(v24) = -2147217400;
      goto LABEL_235;
    }
    Registry::Registry((Registry *)&v164, hKey, 2u, v18);
    LODWORD(v24) = *((_DWORD *)&v164.decVal + 5);
    v37 = (unsigned __int16 *)lpValueName;
    if ( !*((_DWORD *)&v164.decVal + 5) )
      LODWORD(v24) = Registry::SetQWORD((Registry *)&v164, lpValueName, (unsigned __int64)phkResult);
    goto LABEL_251;
  }
  if ( !(unsigned int)wbem_wcsicmp(v89, L"GetBinaryValue") )
  {
    v37 = (unsigned __int16 *)lpValueName;
    BinaryValue = GetBinaryValue(hKey, v18, (unsigned __int16 *)lpValueName, v163);
    goto LABEL_356;
  }
  if ( !(unsigned int)wbem_wcsicmp(v89, L"CheckAccess") )
  {
    LODWORD(v24) = (*(__int64 (__fastcall **)(HKEY, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)phkResult + 32LL))(
                     phkResult,
                     L"uRequired",
                     0,
                     &pvarg,
                     0,
                     0);
    if ( !(_DWORD)v24 )
    {
      phkResult = 0;
      LODWORD(v24) = RegOpenKeyExW(hKey, v18, 0, pvarg.cyVal.Lo, &phkResult);
      if ( (_DWORD)v24 )
      {
        pvarg.vt = 11;
        pvarg.iVal = 0;
      }
      else
      {
        RegCloseKey(phkResult);
        pvarg.vt = 11;
        pvarg.iVal = -1;
      }
      ((void (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))v163->lpVtbl->Put)(
        v163,
        L"bGranted",
        0,
        &pvarg,
        0);
    }
    goto LABEL_235;
  }
  if ( (unsigned int)wbem_wcsicmp(v89, L"GetSecurityDescriptor") )
  {
    if ( (unsigned int)wbem_wcsicmp(v89, L"SetSecurityDescriptor") )
    {
      SecurityDescriptorFromParameters = -2147217362;
      goto LABEL_429;
    }
    LOBYTE(DestStr) = 0;
    v170 = 0;
    pObjectName = 0;
    LODWORD(ppInterface) = 0;
    SecurityDescriptorFromParameters = BuildKeyNameString(hKey, v18, &v170);
    if ( SecurityDescriptorFromParameters >= 0 )
    {
      SecurityDescriptorFromParameters = GetSecurityDescriptorFromParameters(
                                           0,
                                           (struct IWbemClassObject *)phkResult,
                                           (bool *)&DestStr,
                                           (struct CNtSecurityDescriptor **)&pObjectName,
                                           (unsigned int *)&ppInterface);
      LODWORD(hKey) = SecurityDescriptorFromParameters;
      if ( SecurityDescriptorFromParameters >= 0 )
      {
        v139 = 0;
        v140 = 0;
        Owner = (void **)CNtSecurityDescriptor::GetOwner((CNtSecurityDescriptor *)pObjectName);
        v175 = Owner;
        Group = (void **)CNtSecurityDescriptor::GetGroup((CNtSecurityDescriptor *)pObjectName);
        *(_QWORD *)&v171.vt = Group;
        Dacl = (HKEY)CNtSecurityDescriptor::GetDacl((CNtSecurityDescriptor *)pObjectName);
        phkResult = Dacl;
        Sacl = (ACL **)CNtSecurityDescriptor::GetSacl((CNtSecurityDescriptor *)pObjectName);
        v174 = (CImpReg *)Sacl;
        if ( Owner )
          v139 = *Owner;
        v145 = Owner != 0;
        if ( Group )
        {
          v146 = *Group;
          v145 |= 2u;
        }
        else
        {
          v146 = 0;
        }
        if ( Dacl )
          v140 = *(ACL **)Dacl;
        v147 = v145 | 4;
        if ( !Dacl )
          v147 = v145;
        if ( Sacl )
          v24 = *Sacl;
        v148 = v147 | 8;
        if ( !Sacl )
          v148 = v147;
        LODWORD(v24) = SetNamedSecurityInfoW(v170, SE_REGISTRY_KEY, v148, v139, v146, v140, v24);
        CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&v174);
        CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&phkResult);
        CDeleteMe<CNtSid>::~CDeleteMe<CNtSid>(&v171);
        CDeleteMe<CNtSid>::~CDeleteMe<CNtSid>(&v175);
        SecurityDescriptorFromParameters = (int)hKey;
        v18 = v178;
        v37 = (unsigned __int16 *)lpValueName;
        goto LABEL_106;
      }
    }
  }
  else
  {
    if ( !lstrlenW(v18) )
    {
      SecurityDescriptorFromParameters = -2147217400;
      goto LABEL_429;
    }
    pObjectName = 0;
    phkResult = 0;
    SecurityDescriptorFromParameters = BuildKeyNameString(hKey, v18, (unsigned __int16 **)&pObjectName);
    if ( SecurityDescriptorFromParameters >= 0 )
    {
      v136 = (WCHAR *)pObjectName;
      v175 = (void *)pObjectName;
      v137 = CheckForSaclPriv();
      v138 = 7;
      if ( v137 >= 0 )
        v138 = 15;
      LODWORD(v24) = GetNamedSecurityInfoW(v136, SE_REGISTRY_KEY, v138, 0, 0, 0, 0, (PSECURITY_DESCRIPTOR *)&phkResult);
      if ( !(_DWORD)v24 )
      {
        MakeGuard<void * (*)(void *),void *>(&v164, LocalFree, phkResult);
        CNtSecurityDescriptor::CNtSecurityDescriptor((CNtSecurityDescriptor *)&v171, phkResult);
        SecurityDescriptorFromParameters = BuildSecurityDescriptorParameter(
                                             *((struct IWbemServices **)v174 + 3),
                                             (struct IWbemContext *)v170,
                                             (struct CNtSecurityDescriptor *)&v171,
                                             v163);
        CNtSecurityDescriptor::~CNtSecurityDescriptor((CNtSecurityDescriptor *)&v171);
        ScopeGuardImpl1<void (*)(CCacheEntry const *),CCacheEntry *>::~ScopeGuardImpl1<void (*)(CCacheEntry const *),CCacheEntry *>(&v164);
      }
      CWin32DefaultArena::WbemMemFree(v136);
      goto LABEL_235;
    }
  }
LABEL_429:
  v37 = (unsigned __int16 *)lpValueName;
LABEL_430:
  v149 = GetMemLogObject();
  CMemoryLog::Write(v149, SecurityDescriptorFromParameters);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v150, (unsigned int)SecurityDescriptorFromParameters);
  }
LABEL_106:
  if ( !v163 )
  {
    v51 = v179;
    goto LABEL_110;
  }
  pvarg.vt = 3;
  if ( SecurityDescriptorFromParameters >= 0 )
    SecurityDescriptorFromParameters = (int)v24;
  pvarg.lVal = SecurityDescriptorFromParameters;
  ((void (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))v163->lpVtbl->Put)(
    v163,
    L"ReturnValue",
    0,
    &pvarg,
    0);
  v51 = v179;
  v52 = ((__int64 (__fastcall *)(struct IWbemObjectSink *, __int64, struct IWbemClassObject **))v179->lpVtbl->Indicate)(
          v179,
          1,
          &v163);
  SecurityDescriptorFromParameters = v52;
  if ( v52 < 0 )
  {
    SetStatusAndReturn(v52, v51);
    v151 = GetMemLogObject();
    CMemoryLog::Write(v151, SecurityDescriptorFromParameters);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, v152, (unsigned int)SecurityDescriptorFromParameters);
    }
    if ( !v176[0] )
      v177();
    CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v182);
    CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v183);
    if ( v12 )
      ((void (__fastcall *)(struct IWbemClassObject *))v12->lpVtbl->Release)(v12);
    v166 = 0;
    SysFreeString(bstrString);
    AutoProfile::~AutoProfile((AutoProfile *)&v167);
    return (unsigned int)SecurityDescriptorFromParameters;
  }
  else
  {
LABEL_110:
    ((void (__fastcall *)(struct IWbemObjectSink *, _QWORD, _QWORD, _QWORD, _QWORD))v51->lpVtbl->SetStatus)(
      v51,
      0,
      (unsigned int)SecurityDescriptorFromParameters,
      0,
      0);
    if ( !v176[0] )
      v177();
    if ( v37 )
      CWin32DefaultArena::WbemMemFree(v37);
    CWin32DefaultArena::WbemMemFree(v18);
    if ( v12 )
      ((void (__fastcall *)(struct IWbemClassObject *))v12->lpVtbl->Release)(v12);
    v166 = 0;
    SysFreeString(bstrString);
    if ( v167 )
    {
      WbemCoRevertToSelf();
      if ( UnloadUserProfile(hToken[0], hToken[1]) )
      {
        DebugTrace(9, "Profile@0x%x unload.\n", (unsigned int)&v167);
      }
      else
      {
        LastError = GetLastError();
        ErrorTrace(9, "Profile@0x%x failed to unload 0x%x.\n", (unsigned int)&v167, LastError);
      }
      v154 = WbemCoImpersonateClient();
      if ( v154 < 0 )
        ErrorTrace(9, "Registry event provider unable to CoImpersonateClient hr2= 0x%x.\n", v154);
    }
    if ( hToken[0] )
      CloseHandle(hToken[0]);
    return 0;
  }
}

```

## disassembly

```asm
0x1800043c0  mov     [rsp-8+arg_8], rbx
0x1800043c5  push    rbp
0x1800043c6  push    rsi
0x1800043c7  push    rdi
0x1800043c8  push    r12
0x1800043ca  push    r13
0x1800043cc  push    r14
0x1800043ce  push    r15
0x1800043d0  lea     rbp, [rsp-0B0h]
0x1800043d8  sub     rsp, 1B0h
0x1800043df  mov     rax, cs:__security_cookie
0x1800043e6  xor     rax, rsp
0x1800043e9  mov     [rbp+0E0h+var_38], rax
0x1800043f0  mov     rdi, r8
0x1800043f3  mov     [rsp+1E0h+pObjectName], r8
0x1800043f8  mov     rbx, rcx
0x1800043fb  mov     [rbp+0E0h+var_E0], rcx
0x1800043ff  mov     rsi, [rbp+0E0h+arg_20]
0x180004406  mov     [rbp+0E0h+var_110], rsi
0x18000440a  mov     r14, [rbp+0E0h+arg_28]
0x180004411  mov     [rsp+1E0h+phkResult], r14
0x180004416  mov     r15, [rbp+0E0h+arg_30]
0x18000441d  mov     [rbp+0E0h+var_B8], r15
0x180004421  xor     r13d, r13d
0x180004424  mov     [rbp+0E0h+var_E8], r13
0x180004428  mov     [rbp+0E0h+var_F0], r13
0x18000442c  mov     [rsp+1E0h+var_170], r13
0x180004431  mov     [rbp+0E0h+var_130], r13d
0x180004435  xorps   xmm0, xmm0
0x180004438  movdqu  xmmword ptr [rbp+0E0h+hToken], xmm0
0x18000443d  test    r15, r15
0x180004440  jz      loc_1800053BA
0x180004446  test    rdx, rdx
0x180004449  jz      loc_180006468
0x18000444f  test    r8, r8
0x180004452  jz      loc_180006468
0x180004458  test    r14, r14
0x18000445b  jz      loc_180006468
0x180004461  lea     rcx, psz; "StdRegProv"
0x180004468  call    cs:__imp_SysAllocString
0x18000446e  mov     r12, rax
0x180004471  mov     [rbp+0E0h+bstrString], rax
0x180004475  test    rax, rax
0x180004478  jz      loc_180005403
0x18000447e  mov     [rbp+0E0h+var_70], rax
0x180004482  mov     rcx, [rbx+18h]
0x180004486  mov     rax, [rcx]
0x180004489  mov     qword ptr [rsp+1E0h+cchDest], r13
0x18000448e  lea     rdx, [rbp+0E0h+var_E8]
0x180004492  mov     [rsp+1E0h+lpDestStr], rdx
0x180004497  mov     r9, rsi
0x18000449a  xor     r8d, r8d
0x18000449d  mov     rdx, r12
0x1800044a0  mov     rax, [rax+30h]
0x1800044a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044a9  mov     ebx, eax
0x1800044ab  test    eax, eax
0x1800044ad  jnz     short loc_1800044EE
0x1800044af  mov     rcx, [rbp+0E0h+var_E8]
0x1800044b3  mov     rax, [rcx]
0x1800044b6  lea     rdx, [rbp+0E0h+var_F0]
0x1800044ba  mov     [rsp+1E0h+lpDestStr], rdx
0x1800044bf  xor     r9d, r9d
0x1800044c2  xor     r8d, r8d
0x1800044c5  mov     rdx, rdi
0x1800044c8  mov     rax, [rax+98h]
0x1800044cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044d4  mov     ebx, eax
0x1800044d6  test    eax, eax
0x1800044d8  jz      loc_180004780
0x1800044de  mov     rcx, [rbp+0E0h+var_E8]
0x1800044e2  mov     rax, [rcx]
0x1800044e5  mov     rax, [rax+10h]
0x1800044e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044ee  test    ebx, ebx
0x1800044f0  js      loc_18000546B
0x1800044f6  mov     rdi, [rsp+1E0h+var_170]
0x1800044fb  mov     [rbp+0E0h+var_138], rdi
0x1800044ff  xorps   xmm0, xmm0
0x180004502  xor     eax, eax
0x180004504  movups  xmmword ptr [rbp+0E0h+pvarg], xmm0
0x180004508  mov     qword ptr [rbp+0E0h+pvarg+10h], rax
0x18000450c  lea     rcx, [rbp+0E0h+pvarg]; pvarg
0x180004510  call    cs:__imp_VariantInit
0x180004516  mov     rax, [r14]
0x180004519  mov     qword ptr [rsp+1E0h+cchDest], r13
0x18000451e  mov     [rsp+1E0h+lpDestStr], r13
0x180004523  lea     r9, [rbp+0E0h+pvarg]
0x180004527  xor     r8d, r8d
0x18000452a  lea     rdx, aHdefkey; "hDefKey"
0x180004531  mov     rcx, r14
0x180004534  mov     rax, [rax+20h]
0x180004538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000453d  mov     ebx, eax
0x18000453f  test    eax, eax
0x180004541  js      loc_1800054BF
0x180004547  movsxd  rcx, dword ptr [rbp+0E0h+pvarg+8]
0x18000454b  mov     [rsp+1E0h+hKey], rcx
0x180004550  mov     [rbp+0E0h+var_C0], r13
0x180004554  xorps   xmm0, xmm0
0x180004557  xor     eax, eax
0x180004559  movups  xmmword ptr [rbp+0E0h+var_108], xmm0
0x18000455d  mov     qword ptr [rbp+0E0h+var_108+10h], rax
0x180004561  lea     rcx, [rbp+0E0h+var_108]; pvarg
0x180004565  call    cs:__imp_VariantInit
0x18000456b  mov     rax, [r14]
0x18000456e  xor     ebx, ebx
0x180004570  mov     qword ptr [rsp+1E0h+cchDest], rbx
0x180004575  mov     [rsp+1E0h+lpDestStr], rbx
0x18000457a  lea     r9, [rbp+0E0h+var_108]
0x18000457e  xor     r8d, r8d
0x180004581  lea     rdx, aSsubkeyname; "sSubKeyName"
0x180004588  mov     rcx, r14
0x18000458b  mov     rax, [rax+20h]
0x18000458f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004594  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000459b  test    eax, eax
0x18000459d  jnz     loc_1800051EF
0x1800045a3  cmp     word ptr [rbp+0E0h+var_108], 8
0x1800045a8  jnz     loc_1800051EF
0x1800045ae  mov     rcx, qword ptr [rbp+0E0h+var_108+8]
0x1800045b2  mov     rax, r8
0x1800045b5  lea     rax, [rax+1]
0x1800045b9  cmp     [rcx+rax*2], bx
0x1800045bd  jnz     short loc_1800045B5
0x1800045bf  lea     ebx, [rax+1]
0x1800045c2  mov     eax, 2
0x1800045c7  mul     rbx
0x1800045ca  cmovb   rax, r8
0x1800045ce  mov     rcx, rax
0x1800045d1  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800045d7  mov     r13, rax
0x1800045da  mov     [rbp+0E0h+var_C0], rax
0x1800045de  test    rax, rax
0x1800045e1  jz      loc_18000551B
0x1800045e7  mov     r8, qword ptr [rbp+0E0h+var_108+8]; unsigned __int16 *
0x1800045eb  mov     edx, ebx; unsigned __int64
0x1800045ed  mov     rcx, rax; unsigned __int16 *
0x1800045f0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800045f5  lea     rcx, [rbp+0E0h+var_108]; pvarg
0x1800045f9  call    cs:__imp_VariantClear
0x1800045ff  xor     ebx, ebx
0x180004601  mov     [rbp+0E0h+var_88], r13
0x180004605  mov     [rbp+0E0h+var_80], rbx
0x180004609  mov     rsi, rbx
0x18000460c  mov     [rsp+1E0h+lpValueName], rbx
0x180004611  xorps   xmm0, xmm0
0x180004614  xor     eax, eax
0x180004616  movups  xmmword ptr [rbp+0E0h+var_68], xmm0
0x18000461a  mov     qword ptr [rbp+0E0h+var_68+10h], rax
0x180004621  lea     rcx, [rbp+0E0h+var_68]; pvarg
0x180004625  call    cs:__imp_VariantInit
0x18000462b  mov     rax, [r14]
0x18000462e  mov     qword ptr [rsp+1E0h+cchDest], rbx
0x180004633  mov     [rsp+1E0h+lpDestStr], rbx
0x180004638  lea     r9, [rbp+0E0h+var_68]
0x18000463c  xor     r8d, r8d
0x18000463f  lea     rdx, aSvaluename; "sValueName"
0x180004646  mov     rcx, r14
0x180004649  mov     rax, [rax+20h]
0x18000464d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004652  test    eax, eax
0x180004654  jnz     short loc_1800046B1
0x180004656  cmp     word ptr [rbp+0E0h+var_68], 8
0x18000465b  jnz     short loc_1800046B1
0x18000465d  mov     rcx, qword ptr [rbp+0E0h+var_68+8]
0x180004664  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000466b  mov     rax, r8
0x18000466e  lea     rax, [rax+1]
0x180004672  cmp     word ptr [rcx+rax*2], 0
0x180004677  jnz     short loc_18000466E
0x180004679  lea     ebx, [rax+1]
0x18000467c  mov     eax, 2
0x180004681  mul     rbx
0x180004684  cmovb   rax, r8
0x180004688  mov     rcx, rax
0x18000468b  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180004691  mov     rsi, rax
0x180004694  mov     [rsp+1E0h+lpValueName], rax
0x180004699  test    rax, rax
0x18000469c  jz      short loc_1800046AF
0x18000469e  mov     r8, qword ptr [rbp+0E0h+var_68+8]; unsigned __int16 *
0x1800046a5  mov     edx, ebx; unsigned __int64
0x1800046a7  mov     rcx, rax; unsigned __int16 *
0x1800046aa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800046af  xor     ebx, ebx
0x1800046b1  lea     rcx, [rbp+0E0h+var_68]; pvarg
0x1800046b5  call    cs:__imp_VariantClear
0x1800046bb  mov     [rbp+0E0h+var_98], rsi
0x1800046bf  mov     [rbp+0E0h+var_90], rbx
0x1800046c3  mov     [rsp+1E0h+ppInterface], rbx
0x1800046c8  lea     rdx, [rsp+1E0h+ppInterface]; ppInterface
0x1800046cd  lea     rcx, IID_IServerSecurity; riid
0x1800046d4  call    cs:__imp_CoGetCallContext
0x1800046da  mov     r12d, eax
0x1800046dd  test    eax, eax
0x1800046df  jnz     short loc_180004706
0x1800046e1  mov     rcx, [rsp+1E0h+ppInterface]
0x1800046e6  mov     rax, [rcx]
0x1800046e9  mov     rax, [rax+20h]
0x1800046ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046f2  mov     r12d, eax
0x1800046f5  mov     rcx, [rsp+1E0h+ppInterface]
0x1800046fa  mov     rax, [rcx]
0x1800046fd  mov     rax, [rax+10h]
0x180004701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004706  test    r12d, r12d
0x180004709  js      loc_180005522
0x18000470f  lea     rcx, [rbp+0E0h+var_D0]
0x180004713  call    ??$MakeGuard@P6AJXZ@@YA?AV?$ScopeGuardImpl0@P6AJXZ@@P6AJXZ@Z; MakeGuard<long (*)(void)>(long (*)(void))
0x180004718  nop
0x180004719  cmp     [rsp+1E0h+hKey], 0FFFFFFFF80000001h
0x180004722  jz      loc_1800050CA
0x180004728  xor     r15d, r15d
0x18000472b  lea     r14, aCreatekey; "CreateKey"
0x180004732  mov     rsi, [rsp+1E0h+pObjectName]
0x180004737  movzx   ebx, word ptr [rsi]
0x18000473a  test    bx, bx
0x18000473d  jz      short loc_1800047AE
0x18000473f  cmp     bx, 7Fh
0x180004743  ja      loc_180005585
0x180004749  lea     eax, [rbx-41h]
0x18000474c  cmp     ax, 19h
0x180004750  ja      short loc_180004756
0x180004752  add     bx, 20h ; ' '
0x180004756  movzx   ecx, word ptr [r14]
0x18000475a  cmp     cx, 7Fh
0x18000475e  ja      loc_1800055D0
0x180004764  lea     eax, [rcx-41h]
0x180004767  cmp     ax, 19h
0x18000476b  ja      short loc_180004771
0x18000476d  add     cx, 20h ; ' '
0x180004771  cmp     bx, cx
0x180004774  jnz     short loc_1800047D6
0x180004776  add     rsi, 2
0x18000477a  add     r14, 2
0x18000477e  jmp     short loc_180004737
0x180004780  mov     rcx, [rbp+0E0h+var_F0]
0x180004784  mov     rax, [rcx]
0x180004787  lea     r8, [rsp+1E0h+var_170]
0x18000478c  xor     edx, edx
0x18000478e  mov     rax, [rax+78h]
0x180004792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004797  mov     ebx, eax
0x180004799  mov     rcx, [rbp+0E0h+var_F0]
0x18000479d  mov     rax, [rcx]
0x1800047a0  mov     rax, [rax+10h]
0x1800047a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047a9  jmp     loc_1800044DE
0x1800047ae  cmp     [r14], r15w
0x1800047b2  jnz     short loc_180004756
0x1800047b4  mov     [rsp+1E0h+phkResult], r15
0x1800047b9  mov     rcx, r13; lpString
0x1800047bc  call    cs:__imp_lstrlenW
0x1800047c2  cmp     eax, 1
0x1800047c5  jge     loc_18000561B
0x1800047cb  mov     r12d, 80041008h
0x1800047d1  jmp     loc_180006334
0x1800047d6  lea     r14, aDeletekey; "DeleteKey"
0x1800047dd  mov     rsi, [rsp+1E0h+pObjectName]
0x1800047e2  movzx   ebx, word ptr [rsi]
0x1800047e5  test    bx, bx
0x1800047e8  jz      short loc_18000482B
0x1800047ea  cmp     bx, 7Fh
0x1800047ee  ja      loc_180005649
0x1800047f4  lea     eax, [rbx-41h]
0x1800047f7  cmp     ax, 19h
0x1800047fb  ja      short loc_180004801
0x1800047fd  add     bx, 20h ; ' '
0x180004801  movzx   ecx, word ptr [r14]
0x180004805  cmp     cx, 7Fh
0x180004809  ja      loc_180005694
0x18000480f  lea     eax, [rcx-41h]
0x180004812  cmp     ax, 19h
0x180004816  ja      short loc_18000481C
0x180004818  add     cx, 20h ; ' '
0x18000481c  cmp     bx, cx
0x18000481f  jnz     short loc_18000484E
0x180004821  add     rsi, 2
0x180004825  add     r14, 2
0x180004829  jmp     short loc_1800047E2
0x18000482b  cmp     [r14], r15w
0x18000482f  jnz     short loc_180004801
0x180004831  mov     rcx, r13; lpString
0x180004834  call    cs:__imp_lstrlenW
0x18000483a  cmp     eax, 1
0x18000483d  jge     loc_1800056DF
0x180004843  mov     r12d, 80041008h
0x180004849  jmp     loc_180006334
0x18000484e  lea     r14, aDeletevalue; "DeleteValue"
0x180004855  mov     rsi, [rsp+1E0h+pObjectName]
0x18000485a  nop     word ptr [rax+rax+00h]
0x180004860  movzx   ebx, word ptr [rsi]
0x180004863  test    bx, bx
0x180004866  jz      short loc_1800048A9
0x180004868  cmp     bx, 7Fh
0x18000486c  ja      loc_1800056F5
0x180004872  lea     eax, [rbx-41h]
0x180004875  cmp     ax, 19h
0x180004879  ja      short loc_18000487F
  ... truncated ...
```
