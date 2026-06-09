# CErrorReportingManager::InitErrorLog(int)

- ea: `0x101673fb0`
- end: `0x101674de1`
- name: `?InitErrorLog@CErrorReportingManager@@UEAAXH@Z`
- size: `3633`
- prototype: `void __fastcall(CErrorReportingManager *__hidden this, int)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x10167b6a0`
- `0x10167bd10`

## callees

- `0x100401070`
- `0x100401090`
- `0x100401433`
- `0x1004022e0`
- `0x1004076a0`
- `0x100425020`
- `0x100430960`
- `0x100430d60`
- `0x100430e10`
- `0x10055a5d0`
- `0x100757460`
- `0x100758550`
- `0x1007d40d0`
- `0x10083a060`
- `0x101673fb0`
- `0x101678770`
- `0x101e88ac0`
- `0x101e88b50`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1016743b7`
- `KERNEL32!GetLastError` at `0x101674969`
- `KERNEL32!GetLastError` at `0x101674a79`
- `KERNEL32!GetLastError` at `0x1016743b7`
- `KERNEL32!GetLastError` at `0x101674969`
- `KERNEL32!GetLastError` at `0x101674a79`
- `KERNEL32!CloseHandle` at `0x1016742ba`
- `KERNEL32!CloseHandle` at `0x1016744d2`
- `KERNEL32!CloseHandle` at `0x101674b26`
- `KERNEL32!CloseHandle` at `0x1016742ba`
- `KERNEL32!CloseHandle` at `0x1016744d2`
- `KERNEL32!CloseHandle` at `0x101674b26`
- `KERNEL32!Sleep` at `0x10167420a`
- `KERNEL32!Sleep` at `0x1016743eb`
- `KERNEL32!Sleep` at `0x101674ab0`
- `KERNEL32!Sleep` at `0x10167420a`
- `KERNEL32!Sleep` at `0x1016743eb`
- `KERNEL32!Sleep` at `0x101674ab0`
- `KERNEL32!WriteFile` at `0x101674bd0`
- `KERNEL32!WriteFile` at `0x101674bd0`
- `KERNEL32!MoveFileExW` at `0x10167495f`
- `KERNEL32!MoveFileExW` at `0x10167495f`
- `KERNEL32!SetFilePointer` at `0x101674ba0`
- `KERNEL32!SetFilePointer` at `0x101674ba0`
- `KERNEL32!DeleteFileW` at `0x101674840`
- `KERNEL32!DeleteFileW` at `0x101674840`
- `KERNEL32!GetFileType` at `0x101674b18`
- `KERNEL32!GetFileType` at `0x101674b18`
- `svl!SvlPathGetDirectory` at `0x1016746a5`
- `svl!SvlPathGetDirectory` at `0x1016746a5`
- `svl!SvlPathParse` at `0x1016745d1`
- `svl!SvlPathParse` at `0x1016745d1`
- `svl!SvlPathNormalizeAndSet` at `0x1016746bf`
- `svl!SvlPathNormalizeAndSet` at `0x1016746d9`
- `svl!SvlPathNormalizeAndSet` at `0x101674818`
- `svl!SvlPathNormalizeAndSet` at `0x1016746bf`
- `svl!SvlPathNormalizeAndSet` at `0x1016746d9`
- `svl!SvlPathNormalizeAndSet` at `0x101674818`
- `svl!SvlPathReplaceFileName` at `0x1016747e4`
- `svl!SvlPathReplaceFileName` at `0x1016747fd`
- `svl!SvlPathReplaceFileName` at `0x1016747e4`
- `svl!SvlPathReplaceFileName` at `0x1016747fd`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x101674121`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x101674137`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x101674151`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x101674ba8`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x101674c4a`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x101674c5b`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x101674baf`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x101674baf`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101674703`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101674745`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1016747a0`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101674703`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101674745`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1016747a0`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101674345`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x1016743cc`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101674a8e`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101674b3d`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101674d19`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101674345`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x1016743cc`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101674a8e`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101674b3d`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101674d19`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x1016748c5`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x1016748c5`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x101674c51`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x101674c51`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10167443d`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101674b0f`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101674b63`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10167443d`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101674b0f`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101674b63`
- `sqldk!SystemThread_TlsIndex` at `0x101674019`
- `sqldk!SystemThread_TlsIndex` at `0x101674233`
- `sqldk!SystemThread_TlsIndex` at `0x101674264`
- `sqldk!SystemThread_TlsIndex` at `0x10167444c`
- `sqldk!SystemThread_TlsIndex` at `0x10167447d`
- `sqldk!SystemThread_TlsIndex` at `0x101674884`
- `sqldk!SystemThread_TlsIndex` at `0x1016748da`
- `sqldk!SystemThread_TlsOffset` at `0x101674022`
- `sqldk!SystemThread_TlsOffset` at `0x10167423c`
- `sqldk!SystemThread_TlsOffset` at `0x10167426d`
- `sqldk!SystemThread_TlsOffset` at `0x101674455`
- `sqldk!SystemThread_TlsOffset` at `0x101674486`
- `sqldk!SystemThread_TlsOffset` at `0x10167488d`
- `sqldk!SystemThread_TlsOffset` at `0x1016748e3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101674042`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101674255`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101674288`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10167446e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016744a1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016748a8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016748fe`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101674042`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101674255`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101674288`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10167446e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016744a1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016748a8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016748fe`
- `sqldk!?GetLanguageVersion@OsInfo@@QEBA?BGXZ` at `0x101674c62`
- `sqldk!?GetLanguageVersion@OsInfo@@QEBA?BGXZ` at `0x101674c62`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x101674c92`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x101674c92`
- `sqlTsEs!?FGetCollationName@@YA_NKPEA_WPEAH@Z` at `0x101674ca6`
- `sqlTsEs!?FGetCollationName@@YA_NKPEA_WPEAH@Z` at `0x101674ca6`
- `sqlTsEs!?GetLangInfoByLCID@@YAPEAUCLangInfo@@K@Z` at `0x101674c7c`
- `sqlTsEs!?GetLangInfoByLCID@@YAPEAUCLangInfo@@K@Z` at `0x101674c7c`
- `sqlmin!?FailAndExit@StartUp@@SAXPEBD@Z` at `0x1016740d0`
- `sqlmin!?FailAndExit@StartUp@@SAXPEBD@Z` at `0x10167410a`
- `sqlmin!?FailAndExit@StartUp@@SAXPEBD@Z` at `0x1016740d0`
- `sqlmin!?FailAndExit@StartUp@@SAXPEBD@Z` at `0x10167410a`
- `sqlmin!?DBCreateFileW@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXPEBUFCBFileDirectives@@@Z` at `0x10167439f`
- `sqlmin!?DBCreateFileW@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXPEBUFCBFileDirectives@@@Z` at `0x10167441c`
- `sqlmin!?DBCreateFileW@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXPEBUFCBFileDirectives@@@Z` at `0x101674a58`
- `sqlmin!?DBCreateFileW@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXPEBUFCBFileDirectives@@@Z` at `0x101674ae0`
- `sqlmin!?DBCreateFileW@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXPEBUFCBFileDirectives@@@Z` at `0x10167439f`
- `sqlmin!?DBCreateFileW@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXPEBUFCBFileDirectives@@@Z` at `0x10167441c`
- `sqlmin!?DBCreateFileW@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXPEBUFCBFileDirectives@@@Z` at `0x101674a58`
- `sqlmin!?DBCreateFileW@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXPEBUFCBFileDirectives@@@Z` at `0x101674ae0`
- `sqlmin!?DBGetFileAttributesW@@YAKPEB_WPEBUFCBFileBaseDirectives@@@Z` at `0x10167482e`
- `sqlmin!?DBGetFileAttributesW@@YAKPEB_WPEBUFCBFileBaseDirectives@@@Z` at `0x10167482e`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
void __fastcall CErrorReportingManager::InitErrorLog(HINSTANCE *this, int a2)
{
  int v2; // esi
  __int64 v4; // rdi
  __int64 v5; // r14
  int v6; // ecx
  int v7; // eax
  int v8; // edi
  CErrorReportingManager *v9; // rcx
  int v10; // eax
  int v11; // edi
  unsigned int v12; // r13d
  __int64 v13; // rdi
  __int64 v14; // rax
  wchar_t *v15; // rax
  int v16; // edi
  char *v17; // rsi
  void *v18; // rsi
  DWORD LastError; // eax
  wchar_t *OSErrString; // rax
  __int64 v21; // rdi
  __int64 v22; // rax
  __int64 v23; // r9
  __int64 v24; // rdx
  _WORD *v25; // rcx
  __int64 v26; // r8
  __int16 v27; // ax
  _WORD *v28; // rax
  __int64 v29; // r9
  __int64 v30; // rdx
  _WORD *v31; // rcx
  __int64 v32; // r8
  __int16 v33; // ax
  _WORD *v34; // rax
  BOOL v35; // r12d
  int v36; // edi
  DWORD v37; // r15d
  bool i; // cc
  int v39; // esi
  struct __crt_locale_pointers *DefaultLocale; // r9
  struct __crt_locale_pointers *v41; // rax
  struct __crt_locale_pointers *v42; // rax
  __int64 v43; // rdi
  __int64 v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rdi
  __int64 v47; // rdx
  unsigned int v48; // ecx
  char v49; // r12
  int v50; // esi
  HINSTANCE v51; // rdi
  DWORD v52; // eax
  wchar_t *v53; // rax
  wchar_t *v54; // rax
  signed __int16 LanguageVersion; // ax
  int v56; // r14d
  __int64 v57; // rcx
  struct CLangInfo *LangInfoByLCID; // r15
  unsigned int *v59; // rax
  unsigned __int64 v60; // rcx
  wchar_t *v61; // rax
  bool v62; // zf
  __int64 v63; // [rsp+28h] [rbp-D8h]
  __int64 v64; // [rsp+28h] [rbp-D8h]
  __int64 v65; // [rsp+28h] [rbp-D8h]
  __int64 v66; // [rsp+28h] [rbp-D8h]
  int v67; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v68; // [rsp+44h] [rbp-BCh] BYREF
  __int16 Buffer; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v70; // [rsp+50h] [rbp-B0h]
  char *v71; // [rsp+58h] [rbp-A8h]
  int v72; // [rsp+60h] [rbp-A0h]
  int *v73; // [rsp+68h] [rbp-98h]
  int v74; // [rsp+70h] [rbp-90h] BYREF
  __int64 v75; // [rsp+78h] [rbp-88h]
  int v76; // [rsp+80h] [rbp-80h] BYREF
  int v77; // [rsp+84h] [rbp-7Ch]
  __int64 v78; // [rsp+88h] [rbp-78h]
  int v79; // [rsp+90h] [rbp-70h] BYREF
  __int64 v80; // [rsp+98h] [rbp-68h]
  __int64 v81; // [rsp+A0h] [rbp-60h]
  __int64 v82; // [rsp+A8h] [rbp-58h]
  __int64 v83; // [rsp+B0h] [rbp-50h]
  bool v84; // [rsp+C0h] [rbp-40h]
  DWORD NumberOfBytesWritten; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v86[2]; // [rsp+D8h] [rbp-28h] BYREF
  int v87; // [rsp+E8h] [rbp-18h]
  __int64 v88; // [rsp+F0h] [rbp-10h]
  int v89; // [rsp+100h] [rbp+0h] BYREF
  __int64 v90; // [rsp+108h] [rbp+8h]
  int v91; // [rsp+110h] [rbp+10h] BYREF
  int v92; // [rsp+114h] [rbp+14h]
  __int64 v93; // [rsp+118h] [rbp+18h]
  _BYTE v94[64]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v95; // [rsp+160h] [rbp+60h]
  _BYTE v96[16]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v97[24]; // [rsp+178h] [rbp+78h] BYREF
  _OWORD v98[5]; // [rsp+190h] [rbp+90h] BYREF
  __int128 v99; // [rsp+1E0h] [rbp+E0h]
  __int128 v100; // [rsp+1F0h] [rbp+F0h]
  wchar_t v101[2048]; // [rsp+200h] [rbp+100h] BYREF
  wchar_t v102[2048]; // [rsp+1200h] [rbp+1100h] BYREF
  _BYTE v103[4096]; // [rsp+2200h] [rbp+2100h] BYREF
  _BYTE v104[4096]; // [rsp+3200h] [rbp+3100h] BYREF
  _BYTE v105[528]; // [rsp+4200h] [rbp+4100h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+4410h] [rbp+4310h] BYREF
  WCHAR FileName[264]; // [rsp+4620h] [rbp+4520h] BYREF
  _BYTE v108[528]; // [rsp+4830h] [rbp+4730h] BYREF
  _BYTE v109[528]; // [rsp+4A40h] [rbp+4940h] BYREF
  wchar_t v110[264]; // [rsp+4C50h] [rbp+4B50h] BYREF

  v95 = -2;
  v2 = a2;
  v67 = a2;
  v87 = 0;
  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v5 = *(_QWORD *)(v4 + 256);
  v70 = v5;
  if ( !v5 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v5 = *(_QWORD *)(v4 + 256);
    v70 = v5;
  }
  v88 = v5;
  v6 = *(_DWORD *)(v5 + 616);
  v87 = !(*(_BYTE *)(v5 + 616) & 1);
  *(_DWORD *)(v5 + 616) = v6 | 1;
  v7 = g_fHideUserDataInErrorMessage;
  if ( (*((_BYTE *)qword_102ECFB10 + 453) & 2) != 0 )
    v7 = 1;
  g_fHideUserDataInErrorMessage = v7;
  v8 = 6;
  if ( v2 )
  {
    (*((void (__fastcall **)(HINSTANCE *, char *))*this + 8))(this, (char *)this + 336);
    if ( !CErrorReportingManager::FGetStringResource(v9, this + 43, *((_WORD *)this + 168)) )
      StartUp::FailAndExit("Error setting up default language resource file.");
    v68 = (*((__int64 (__fastcall **)(HINSTANCE *, __int64))*this + 15))(this, 1);
    if ( *((_WORD *)this + 168) != v68 && !(*((__int64 (__fastcall **)(HINSTANCE *, __int16 *))*this + 8))(this, &v68) )
      StartUp::FailAndExit("Error setting up English language resource file.");
    *((_DWORD *)this + 219) = 6;
    v2 = v67;
  }
  *((_DWORD *)this + 220) = 0;
  if ( (*(int (__fastcall **)(struct IServerConfiguration *, __int64))(*(_QWORD *)s_pServerConf + 72LL))(
         s_pServerConf,
         6) >= 6 )
    v8 = (*(__int64 (__fastcall **)(struct IServerConfiguration *, __int64))(*(_QWORD *)s_pServerConf + 72LL))(
           s_pServerConf,
           6);
  *((_DWORD *)this + 219) = v8;
  v10 = (*(__int64 (__fastcall **)(struct IServerConfiguration *, _QWORD))(*(_QWORD *)s_pServerConf + 80LL))(
          s_pServerConf,
          0);
  *((_DWORD *)this + 220) = v10;
  if ( (unsigned int)(v10 - 1) <= 8 )
    *((_DWORD *)this + 220) = 10;
  v71 = (char *)(this + 116);
  v72 = 0;
  v72 = SOS_Mutex::Wait(this + 116, 0xFFFFFFFFLL, this + 123, 0) == 0;
  v11 = 0;
  v12 = ((*((char *)qword_102ECFB10 + 457) >> 31) & 0x7FFFFF80) + 128;
  if ( v2 )
  {
    v18 = DBCreateFileW((const wchar_t *)this + 176, 0x40000000u, 1u, 0, 4u, v12, 0, 0);
    if ( v18 == (void *)-1LL )
    {
      while ( v11 < 10 )
      {
        LastError = GetLastError();
        OSErrString = GetOSErrString(LastError, (struct ErrorStringHolder *)v103, 0, 0);
        scierrlog(0x42A2u, this + 44, OSErrString);
        Sleep(0x12Cu);
        ++v11;
        v18 = DBCreateFileW((const wchar_t *)this + 176, 0x40000000u, 1u, 0, 4u, v12, 0, 0);
        if ( v18 != (void *)-1LL )
          goto LABEL_36;
      }
      SQLExit(254, 17058, 1066);
    }
LABEL_36:
    if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                    + SystemThread_TlsOffset
                    + 256LL) )
      SystemThread::MakeMiniSOSThread(0);
    v21 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v22 = *(_QWORD *)(v21 + 256);
    if ( !v22 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v22 = *(_QWORD *)(v21 + 256);
    }
    SOS_Task::AutoSwitchPreemptive::AutoSwitchPreemptive(&v89, 536871474, (*(_DWORD *)(v22 + 616) & 0x40) == 0);
    CloseHandle(v18);
    v73 = &v91;
    if ( v91 )
    {
      if ( v92 )
        *(_DWORD *)(v93 + 800) |= 0x800u;
      else
        (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v93 + 608) + 16LL))(
          *(_QWORD *)(v93 + 608),
          v93,
          1);
    }
  }
  else
  {
    scierrlogreinit(1, (struct IErrorReportingManager *)this, 0x431Fu);
    (*((void (__fastcall **)(HINSTANCE *, _QWORD))*this + 31))(this, 0);
    for ( ; *((int *)this + 223) > 0; ++v11 )
    {
      if ( v11 >= 10 )
        break;
      Sleep(0x12Cu);
    }
    if ( *((_DWORD *)this + 223) )
    {
      (*((void (__fastcall **)(HINSTANCE *, __int64))*this + 31))(this, 1);
      v15 = GetOSErrString(0xAAu, (struct ErrorStringHolder *)v102, 0, 0);
      scierrlogreinit(1, (struct IErrorReportingManager *)this, 0x42A2u, this + 44, v15);
      v16 = v72;
      v17 = v71;
      goto LABEL_119;
    }
    if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                    + SystemThread_TlsOffset
                    + 256LL) )
      SystemThread::MakeMiniSOSThread(0);
    v13 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v14 = *(_QWORD *)(v13 + 256);
    if ( !v14 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v14 = *(_QWORD *)(v13 + 256);
    }
    SOS_Task::AutoSwitchPreemptive::AutoSwitchPreemptive(&v89, 536871474, (*(_DWORD *)(v14 + 616) & 0x40) == 0);
    CloseHandle(this[1]);
    CErrorReportingManager::AutoSpinLock::AutoSpinLock(
      (CErrorReportingManager::AutoSpinLock *)v86,
      (struct CErrorReportingManager *)this);
    this[1] = (HINSTANCE)-1LL;
    SpinlockHolder<437,1,258>::~SpinlockHolder<437,1,258>(v86);
    v73 = &v91;
    if ( v91 )
    {
      if ( v92 )
        *(_DWORD *)(v93 + 800) |= 0x800u;
      else
        (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v93 + 608) + 16LL))(
          *(_QWORD *)(v93 + 608),
          v93,
          1);
    }
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)v94);
  *(_DWORD *)(v90 + 616) &= ~v89;
  memset_0(v105, 0, 0x20Au);
  memset_0(v108, 0, 0x20Au);
  memset(v98, 0, sizeof(v98));
  v99 = 0;
  v100 = 0;
  memset_0(FileName, 0, 0x20Au);
  memset_0(ExistingFileName, 0, 0x20Au);
  memset_0(v109, 0, 0x20Au);
  SvlPathParse(this + 44, v98);
  v23 = *((_QWORD *)&v99 + 1);
  if ( *((_QWORD *)&v99 + 1) <= 0x7FFFFFFEu )
  {
    v24 = 261;
    v25 = v105;
    v26 = v99 - (_QWORD)v105;
    do
    {
      if ( !(v24 + v23 - 261) )
        break;
      v27 = *(_WORD *)((char *)v25 + v26);
      if ( !v27 )
        break;
      *v25++ = v27;
      --v24;
    }
    while ( v24 );
    v28 = v25 - 1;
    if ( v24 )
      v28 = v25;
    *v28 = 0;
  }
  v29 = *((_QWORD *)&v100 + 1);
  if ( *((_QWORD *)&v100 + 1) <= 0x7FFFFFFEu )
  {
    v30 = 261;
    v31 = v108;
    v32 = v100 - (_QWORD)v108;
    do
    {
      if ( !(v30 + v29 - 261) )
        break;
      v33 = *(_WORD *)((char *)v31 + v32);
      if ( !v33 )
        break;
      *v31++ = v33;
      --v30;
    }
    while ( v30 );
    v34 = v31 - 1;
    if ( v30 )
      v34 = v31;
    *v34 = 0;
  }
  SvlPathGetDirectory(this + 44, v109, 261);
  SvlPathNormalizeAndSet(v109, FileName, 261);
  SvlPathNormalizeAndSet(v109, ExistingFileName, 261);
  v35 = *((_QWORD *)&v100 + 1) != 0;
  v36 = *((_DWORD *)this + 219);
  v37 = v67;
  for ( i = v36 <= 0; ; i = v39 <= 0 )
  {
    if ( i )
    {
      v49 = 0;
      goto LABEL_93;
    }
    v39 = v36 - 1;
    DefaultLocale = GetDefaultLocale();
    LODWORD(v63) = v36;
    if ( v35 )
    {
      StringCchPrintf_lW(v110, 0x101u, L"%ls%-d%ls", DefaultLocale, v105, v63, v108);
      v41 = GetDefaultLocale();
      LODWORD(v64) = v36 - 1;
      StringCchPrintf_lW(v102, 0x101u, L"%ls%-d%ls", v41, v105, v64, v108);
    }
    else
    {
      StringCchPrintf_lW(v110, 0x101u, L"%ls.%-d", DefaultLocale, v105, v63);
      v42 = GetDefaultLocale();
      LODWORD(v65) = v36 - 1;
      StringCchPrintf_lW(v102, 0x101u, L"%ls.%-d", v42, v105, v65);
    }
    SvlPathReplaceFileName(FileName, 261, v110);
    SvlPathReplaceFileName(ExistingFileName, 261, v102);
    if ( v36 == 1 )
    {
      SvlPathNormalizeAndSet(this + 44, ExistingFileName, 261);
    }
    else if ( v36 == 6 && DBGetFileAttributesW(ExistingFileName, 0) != -1 )
    {
      DeleteFileW(FileName);
    }
    Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v74, 1);
    v73 = &v76;
    v79 = 536871490;
    v80 = 0;
    v82 = 0;
    v81 = 0;
    v83 = 0;
    v84 = 0;
    v43 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v44 = *(_QWORD *)(v43 + 256);
    if ( !v44 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v44 = *(_QWORD *)(v43 + 256);
    }
    v45 = *(_QWORD *)(v44 + 600);
    if ( v45 )
      v84 = (unsigned int)SOS_Task::PushWait(v45, &v79) == 0;
    v46 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v47 = *(_QWORD *)(v46 + 256);
    if ( !v47 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v47 = *(_QWORD *)(v46 + 256);
    }
    v78 = v47;
    v48 = *(_DWORD *)(v47 + 800);
    v77 = (v48 >> 11) & 1;
    if ( (v48 & 0x800) != 0 || (*(_BYTE *)(v47 + 800) & 4) == 0 )
    {
      v76 = 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v47 + 608) + 8LL))(*(_QWORD *)(v47 + 608));
    }
    else
    {
      v76 = 0;
    }
    if ( !MoveFileExW(ExistingFileName, FileName, 3u) )
    {
      v37 = GetLastError();
      if ( v37 != 2 )
        break;
    }
    v86[0] = &v76;
    if ( v76 )
    {
      if ( v77 )
        *(_DWORD *)(v78 + 800) |= 0x800u;
      else
        (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v78 + 608) + 16LL))(
          *(_QWORD *)(v78 + 608),
          v78,
          1);
    }
    SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v79);
    *(_DWORD *)(v75 + 616) &= ~v74;
    v36 = v39;
  }
  v49 = 1;
  v86[0] = &v76;
  if ( v76 )
  {
    if ( v77 )
      *(_DWORD *)(v78 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v78 + 608) + 16LL))(
        *(_QWORD *)(v78 + 608),
        v78,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v79);
  *(_DWORD *)(v75 + 616) &= ~v74;
LABEL_93:
  v50 = 0;
  v51 = (HINSTANCE)DBCreateFileW((const wchar_t *)this + 176, 0x40000000u, 1u, 0, 4u, v12, 0, 0);
  if ( v51 == (HINSTANCE)-1LL )
  {
    while ( v50 < 10 )
    {
      v52 = GetLastError();
      v53 = GetOSErrString(v52, (struct ErrorStringHolder *)v103, 0, 0);
      scierrlog(0x42A2u, this + 44, v53);
      if ( !v67 )
      {
        v16 = v72;
        v17 = v71;
        goto LABEL_118;
      }
      Sleep(0x12Cu);
      ++v50;
      v51 = (HINSTANCE)DBCreateFileW((const wchar_t *)this + 176, 0x40000000u, 1u, 0, 4u, v12, 0, 0);
      if ( v51 != (HINSTANCE)-1LL )
        goto LABEL_100;
    }
    SQLExit(255, 17058, 1066);
  }
LABEL_100:
  if ( GetFileType(v51) != 1 )
  {
    CloseHandle(v51);
    v54 = GetOSErrString(0x32u, (struct ErrorStringHolder *)v104, 0, 0);
    scierrlog(0x42A2u, this + 44, v54);
    SQLExit(256, 17058, 1066);
  }
  CErrorReportingManager::AutoSpinLock::AutoSpinLock(
    (CErrorReportingManager::AutoSpinLock *)v96,
    (struct CErrorReportingManager *)this);
  this[1] = v51;
  SpinlockHolder<437,1,258>::~SpinlockHolder<437,1,258>(v96);
  Buffer = -257;
  if ( v49 )
  {
    SetFilePointer(v51, 0, 0, 2u);
  }
  else if ( !OsInfo::IsLinux(SOS_OS_OsInfo) )
  {
    WriteFile(v51, &Buffer, 2u, &NumberOfBytesWritten, 0);
  }
  (*((void (__fastcall **)(HINSTANCE *, __int64))*this + 31))(this, 1);
  CErrorReportingManager::AutoSpinLock::AutoSpinLock(
    (CErrorReportingManager::AutoSpinLock *)v97,
    (struct CErrorReportingManager *)this);
  *((_DWORD *)this + 228) = 1;
  SpinlockHolder<437,1,258>::~SpinlockHolder<437,1,258>(v97);
  *((_DWORD *)this + 221) = 0;
  v17 = v71;
  *((_QWORD *)v71 + 6) = 0;
  EventAutoInternal<SuspendQueueSLock>::Signal(v17, 0);
  v16 = --v72;
  if ( v67 )
  {
    if ( *((_DWORD *)this + 230) )
      scierrlog(0x4304u, qword_102ECFB00 + 46388);
  }
  else if ( v49 )
  {
    v61 = GetOSErrString(v37, (struct ErrorStringHolder *)v101, 0, 0);
    ex_callprint(17049, 16, 1, ExistingFileName, FileName, v61);
  }
  else
  {
    CErrorReportingManager::LogStartupMessages((CErrorReportingManager *)this, 1);
    if ( OsInfo::IsXPlatInstance(SOS_OS_OsInfo) )
      LanguageVersion = OsInfo::GetLanguageVersion(SOS_OS_OsInfo);
    else
      LanguageVersion = (*((__int64 (__fastcall **)(HINSTANCE *, _QWORD))*this + 15))(this, 0);
    v56 = LanguageVersion;
    LangInfoByLCID = GetLangInfoByLCID(LanguageVersion);
    if ( LangInfoByLCID )
    {
      v67 = 256;
      v59 = (unsigned int *)CDefaultCollation::PDCServer(v57);
      FGetCollationName(*v59, v101, &v67);
      v60 = v67 & 0xFFFFFFFFFFFFFFFEuLL;
      if ( v60 >= 0x102 )
        _report_rangecheckfailure();
      *(wchar_t *)((char *)v101 + v60) = 0;
      LODWORD(v66) = v56;
      scierrlogreinit(1, (struct IErrorReportingManager *)this, 0xC2FDu, v101, *((_QWORD *)LangInfoByLCID + 1), v66);
    }
    scierrlogreinit(1, (struct IErrorReportingManager *)this, 0x4320u);
  }
LABEL_118:
  v5 = v70;
LABEL_119:
  if ( v16 )
  {
    do
    {
      *((_QWORD *)v17 + 6) = 0;
      EventAutoInternal<SuspendQueueSLock>::Signal(v17, 0);
      v62 = v16-- == 1;
      v72 = v16;
    }
    while ( !v62 );
  }
  *(_DWORD *)(v5 + 616) &= ~v87;
}

```

## disassembly

```asm
0x101673fb0  push    rbp
0x101673fb2  push    r12
0x101673fb4  push    r13
0x101673fb6  push    r14
0x101673fb8  push    r15
0x101673fba  lea     rbp, [rsp-4D70h]
0x101673fc2  mov     eax, 4E70h
0x101673fc7  call    _alloca_probe
0x101673fcc  sub     rsp, rax
0x101673fcf  mov     [rbp+4D90h+var_4D30], 0FFFFFFFFFFFFFFFEh
0x101673fd7  mov     [rsp+4E90h+arg_8], rbx
0x101673fdf  mov     [rsp+4E90h+arg_10], rsi
0x101673fe7  mov     [rsp+4E90h+arg_18], rdi
0x101673fef  mov     rax, cs:__security_cookie
0x101673ff6  xor     rax, rsp
0x101673ff9  mov     [rbp+4D90h+var_30], rax
0x101674000  mov     esi, edx
0x101674002  mov     [rsp+4E90h+var_4E50], edx
0x101674006  mov     rbx, rcx
0x101674009  xor     r15d, r15d
0x10167400c  mov     [rbp+4D90h+var_4DA8], r15d
0x101674010  mov     r8, gs:58h
0x101674019  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101674020  mov     ecx, [rax]
0x101674022  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101674029  mov     edi, [rax]
0x10167402b  add     rdi, [r8+rcx*8]
0x10167402f  mov     r14, [rdi+100h]
0x101674036  mov     [rsp+4E90h+var_4E40], r14
0x10167403b  test    r14, r14
0x10167403e  jnz     short loc_101674054
0x101674040  xor     ecx, ecx
0x101674042  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101674048  mov     r14, [rdi+100h]
0x10167404f  mov     [rsp+4E90h+var_4E40], r14
0x101674054  mov     [rbp+4D90h+var_4DA0], r14
0x101674058  mov     ecx, [r14+268h]
0x10167405f  mov     eax, ecx
0x101674061  and     eax, 1
0x101674064  xor     eax, 1
0x101674067  mov     [rbp+4D90h+var_4DA8], eax
0x10167406a  or      ecx, 1
0x10167406d  mov     [r14+268h], ecx
0x101674074  mov     rax, cs:qword_102ECFB10
0x10167407b  test    byte ptr [rax+1C5h], 2
0x101674082  mov     eax, cs:?g_fHideUserDataInErrorMessage@@3HA; int g_fHideUserDataInErrorMessage
0x101674088  mov     r12d, 1
0x10167408e  cmovnz  eax, r12d
0x101674092  mov     cs:?g_fHideUserDataInErrorMessage@@3HA, eax; int g_fHideUserDataInErrorMessage
0x101674098  lea     edi, [r12+5]
0x10167409d  test    esi, esi
0x10167409f  jz      short loc_10167411A
0x1016740a1  mov     rax, [rbx]
0x1016740a4  lea     rdx, [rbx+150h]
0x1016740ab  mov     rcx, rbx
0x1016740ae  call    qword ptr [rax+40h]
0x1016740b1  lea     rdx, [rbx+158h]; HINSTANCE *
0x1016740b8  movzx   r8d, word ptr [rbx+150h]; __int16
0x1016740c0  call    ?FGetStringResource@CErrorReportingManager@@AEAA_NPEAPEAUHINSTANCE__@@F@Z; CErrorReportingManager::FGetStringResource(HINSTANCE__ * *,short)
0x1016740c5  test    al, al
0x1016740c7  jnz     short loc_1016740D6
0x1016740c9  lea     rcx, aErrorSettingUp; "Error setting up default language resou"...
0x1016740d0  call    cs:__imp_?FailAndExit@StartUp@@SAXPEBD@Z; StartUp::FailAndExit(char const *)
0x1016740d6  mov     rax, [rbx]
0x1016740d9  mov     edx, r12d
0x1016740dc  mov     rcx, rbx
0x1016740df  call    qword ptr [rax+78h]
0x1016740e2  mov     [rsp+4E90h+var_4E4C], ax
0x1016740e7  cmp     [rbx+150h], ax
0x1016740ee  jz      short loc_101674110
0x1016740f0  mov     rax, [rbx]
0x1016740f3  lea     rdx, [rsp+4E90h+var_4E4C]
0x1016740f8  mov     rcx, rbx
0x1016740fb  call    qword ptr [rax+40h]
0x1016740fe  test    rax, rax
0x101674101  jnz     short loc_101674110
0x101674103  lea     rcx, aErrorSettingUp_0; "Error setting up English language resou"...
0x10167410a  call    cs:__imp_?FailAndExit@StartUp@@SAXPEBD@Z; StartUp::FailAndExit(char const *)
0x101674110  mov     [rbx+36Ch], edi
0x101674116  mov     esi, [rsp+4E90h+var_4E50]
0x10167411a  mov     [rbx+370h], r15d
0x101674121  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x101674128  mov     rcx, [rax]
0x10167412b  mov     rax, [rcx]
0x10167412e  mov     edx, edi
0x101674130  call    qword ptr [rax+48h]
0x101674133  cmp     eax, edi
0x101674135  jl      short loc_10167414B
0x101674137  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x10167413e  mov     rcx, [rax]
0x101674141  mov     rax, [rcx]
0x101674144  mov     edx, edi
0x101674146  call    qword ptr [rax+48h]
0x101674149  mov     edi, eax
0x10167414b  mov     [rbx+36Ch], edi
0x101674151  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x101674158  mov     rcx, [rax]
0x10167415b  mov     rax, [rcx]
0x10167415e  xor     edx, edx
0x101674160  call    qword ptr [rax+50h]
0x101674163  mov     [rbx+370h], eax
0x101674169  dec     eax
0x10167416b  cmp     eax, 8
0x10167416e  ja      short loc_10167417A
0x101674170  mov     dword ptr [rbx+370h], 0Ah
0x10167417a  lea     rcx, [rbx+3A0h]
0x101674181  mov     [rsp+4E90h+var_4E38], rcx
0x101674186  mov     [rsp+4E90h+var_4E30], r15d
0x10167418b  lea     r8, [rbx+3D8h]
0x101674192  xor     r9d, r9d
0x101674195  mov     edx, 0FFFFFFFFh
0x10167419a  call    ?Wait@SOS_Mutex@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@@Z; SOS_Mutex::Wait(ulong,SOS_WaitInfo const *,SOS_SYNC_WAIT_OPTIONS)
0x10167419f  mov     ecx, r15d
0x1016741a2  test    eax, eax
0x1016741a4  cmovz   ecx, r12d
0x1016741a8  mov     [rsp+4E90h+var_4E30], ecx
0x1016741ac  mov     edi, r15d
0x1016741af  mov     rax, cs:qword_102ECFB10
0x1016741b6  movsx   r13d, byte ptr [rax+1C9h]
0x1016741be  sar     r13d, 1Fh
0x1016741c2  and     r13d, 7FFFFF80h
0x1016741c9  sub     r13d, 0FFFFFF80h
0x1016741cd  test    esi, esi
0x1016741cf  jnz     loc_101674376
0x1016741d5  mov     r8d, 431Fh; unsigned int
0x1016741db  mov     rdx, rbx; struct IErrorReportingManager *
0x1016741de  mov     ecx, r12d; bool
0x1016741e1  call    ?scierrlogreinit@@YAX_NPEAVIErrorReportingManager@@KZZ; scierrlogreinit(bool,IErrorReportingManager *,ulong,...)
0x1016741e6  mov     rax, [rbx]
0x1016741e9  xor     edx, edx
0x1016741eb  mov     rcx, rbx
0x1016741ee  call    qword ptr [rax+0F8h]
0x1016741f4  mov     eax, [rbx+37Ch]
0x1016741fa  test    eax, eax
0x1016741fc  jle     short loc_10167421C
0x1016741fe  nop
0x1016741ff  nop
0x101674200  cmp     edi, 0Ah
0x101674203  jge     short loc_10167421C
0x101674205  mov     ecx, 12Ch; dwMilliseconds
0x10167420a  call    cs:__imp_Sleep
0x101674210  inc     edi
0x101674212  mov     eax, [rbx+37Ch]
0x101674218  test    eax, eax
0x10167421a  jg      short loc_101674200
0x10167421c  mov     eax, [rbx+37Ch]
0x101674222  test    eax, eax
0x101674224  jnz     loc_101674324
0x10167422a  mov     r8, gs:58h
0x101674233  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10167423a  mov     ecx, [rax]
0x10167423c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101674243  mov     edx, [rax]
0x101674245  add     rdx, [r8+rcx*8]
0x101674249  cmp     qword ptr [rdx+100h], 0
0x101674251  jnz     short loc_10167425B
0x101674253  xor     ecx, ecx
0x101674255  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10167425b  mov     rdx, gs:58h
0x101674264  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10167426b  mov     ecx, [rax]
0x10167426d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101674274  mov     edi, [rax]
0x101674276  add     rdi, [rdx+rcx*8]
0x10167427a  mov     rax, [rdi+100h]
0x101674281  test    rax, rax
0x101674284  jnz     short loc_101674295
0x101674286  xor     ecx, ecx
0x101674288  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10167428e  mov     rax, [rdi+100h]
0x101674295  mov     r8d, [rax+268h]
0x10167429c  shr     r8d, 6
0x1016742a0  not     r8d
0x1016742a3  and     r8d, 1
0x1016742a7  mov     edx, 20000232h
0x1016742ac  lea     rcx, [rbp+4D90h+var_4D90]
0x1016742b0  call    ??0AutoSwitchPreemptive@SOS_Task@@QEAA@W4PWAIT_enum@@H@Z; SOS_Task::AutoSwitchPreemptive::AutoSwitchPreemptive(PWAIT_enum,int)
0x1016742b5  nop
0x1016742b6  mov     rcx, [rbx+8]; hObject
0x1016742ba  call    cs:__imp_CloseHandle
0x1016742c0  mov     rdx, rbx; struct CErrorReportingManager *
0x1016742c3  lea     rcx, [rbp+4D90h+var_4DB8]; this
0x1016742c7  call    ??0AutoSpinLock@CErrorReportingManager@@QEAA@PEAV1@@Z; CErrorReportingManager::AutoSpinLock::AutoSpinLock(CErrorReportingManager *)
0x1016742cc  nop
0x1016742cd  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x1016742d5  lea     rcx, [rbp+4D90h+var_4DB8]
0x1016742d9  call    ??1?$SpinlockHolder@$0BLF@$00$0BAC@@@QEAA@XZ; SpinlockHolder<437,1,258>::~SpinlockHolder<437,1,258>(void)
0x1016742de  nop
0x1016742df  lea     rax, [rbp+4D90h+var_4D80]
0x1016742e3  mov     [rsp+4E90h+var_4E28], rax
0x1016742e8  cmp     [rbp+4D90h+var_4D80], 0
0x1016742ec  jz      short loc_101674315
0x1016742ee  mov     rdx, [rbp+4D90h+var_4D78]
0x1016742f2  mov     rcx, [rdx+260h]
0x1016742f9  cmp     [rbp+4D90h+var_4D7C], 0
0x1016742fd  jz      short loc_10167430B
0x1016742ff  or      dword ptr [rdx+320h], 800h
0x101674309  jmp     short loc_101674315
0x10167430b  mov     rax, [rcx]
0x10167430e  mov     r8d, r12d
0x101674311  call    qword ptr [rax+10h]
0x101674314  nop
0x101674315  lea     rcx, [rbp+4D90h+var_4D70]; this
0x101674319  call    ??1SOS_ExternalAutoWait@@QEAA@XZ; SOS_ExternalAutoWait::~SOS_ExternalAutoWait(void)
0x10167431e  nop
0x10167431f  jmp     loc_101674519
0x101674324  mov     rax, [rbx]
0x101674327  mov     edx, r12d
0x10167432a  mov     rcx, rbx
0x10167432d  call    qword ptr [rax+0F8h]
0x101674333  xor     r9d, r9d
0x101674336  xor     r8d, r8d
0x101674339  lea     rdx, [rbp+4D90h+var_3C90]
0x101674340  mov     ecx, 0AAh
0x101674345  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x10167434b  lea     r9, [rbx+160h]
0x101674352  mov     [rsp+4E90h+lpOverlapped], rax
0x101674357  mov     r8d, 42A2h; unsigned int
0x10167435d  mov     rdx, rbx; struct IErrorReportingManager *
0x101674360  mov     ecx, r12d; bool
0x101674363  call    ?scierrlogreinit@@YAX_NPEAVIErrorReportingManager@@KZZ; scierrlogreinit(bool,IErrorReportingManager *,ulong,...)
0x101674368  mov     edi, [rsp+4E90h+var_4E30]
0x10167436c  mov     rsi, [rsp+4E90h+var_4E38]
0x101674371  jmp     loc_101674D78
0x101674376  mov     [rsp+4E90h+var_4E58], r15
0x10167437b  mov     [rsp+4E90h+var_4E60], r15
0x101674380  mov     dword ptr [rsp+4E90h+var_4E68], r13d
0x101674385  mov     dword ptr [rsp+4E90h+lpOverlapped], 4
0x10167438d  xor     r9d, r9d
0x101674390  mov     r8d, r12d
0x101674393  mov     edx, 40000000h
0x101674398  lea     rcx, [rbx+160h]
0x10167439f  call    cs:__imp_?DBCreateFileW@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXPEBUFCBFileDirectives@@@Z; DBCreateFileW(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,FCBFileDirectives const *)
0x1016743a5  mov     rsi, rax
0x1016743a8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1016743ac  jnz     loc_101674443
0x1016743b2  cmp     edi, 0Ah
0x1016743b5  jge     short loc_10167442D
0x1016743b7  call    cs:__imp_GetLastError
0x1016743bd  mov     ecx, eax
0x1016743bf  xor     r9d, r9d
0x1016743c2  xor     r8d, r8d
0x1016743c5  lea     rdx, [rbp+4D90h+var_2C90]
0x1016743cc  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x1016743d2  mov     r8, rax
0x1016743d5  lea     rdx, [rbx+160h]
0x1016743dc  mov     ecx, 42A2h; unsigned int
0x1016743e1  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x1016743e6  mov     ecx, 12Ch; dwMilliseconds
0x1016743eb  call    cs:__imp_Sleep
0x1016743f1  inc     edi
0x1016743f3  mov     [rsp+4E90h+var_4E58], r15
0x1016743f8  mov     [rsp+4E90h+var_4E60], r15
0x1016743fd  mov     dword ptr [rsp+4E90h+var_4E68], r13d
0x101674402  mov     dword ptr [rsp+4E90h+lpOverlapped], 4
0x10167440a  xor     r9d, r9d
0x10167440d  mov     r8d, r12d
0x101674410  mov     edx, 40000000h
0x101674415  lea     rcx, [rbx+160h]
0x10167441c  call    cs:__imp_?DBCreateFileW@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXPEBUFCBFileDirectives@@@Z; DBCreateFileW(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,FCBFileDirectives const *)
0x101674422  mov     rsi, rax
0x101674425  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x101674429  jz      short loc_1016743B2
0x10167442b  jmp     short loc_101674443
0x10167442d  mov     edx, 42A2h
0x101674432  mov     ecx, 0FEh
0x101674437  mov     r8d, 42Ah
0x10167443d  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x101674443  mov     r8, gs:58h
0x10167444c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101674453  mov     ecx, [rax]
0x101674455  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10167445c  mov     edx, [rax]
0x10167445e  add     rdx, [r8+rcx*8]
0x101674462  cmp     qword ptr [rdx+100h], 0
0x10167446a  jnz     short loc_101674474
0x10167446c  xor     ecx, ecx
0x10167446e  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101674474  mov     rdx, gs:58h
0x10167447d  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101674484  mov     ecx, [rax]
0x101674486  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10167448d  mov     edi, [rax]
0x10167448f  add     rdi, [rdx+rcx*8]
0x101674493  mov     rax, [rdi+100h]
0x10167449a  test    rax, rax
0x10167449d  jnz     short loc_1016744AE
0x10167449f  xor     ecx, ecx
0x1016744a1  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1016744a7  mov     rax, [rdi+100h]
0x1016744ae  mov     r8d, [rax+268h]
0x1016744b5  shr     r8d, 6
0x1016744b9  not     r8d
0x1016744bc  and     r8d, 1
0x1016744c0  mov     edx, 20000232h
0x1016744c5  lea     rcx, [rbp+4D90h+var_4D90]
0x1016744c9  call    ??0AutoSwitchPreemptive@SOS_Task@@QEAA@W4PWAIT_enum@@H@Z; SOS_Task::AutoSwitchPreemptive::AutoSwitchPreemptive(PWAIT_enum,int)
0x1016744ce  nop
0x1016744cf  mov     rcx, rsi; hObject
0x1016744d2  call    cs:__imp_CloseHandle
  ... truncated ...
```
