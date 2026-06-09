# SpoolerUserInit(USER_INFO *)

- ea: `0x140071470`
- end: `0x1400716ea`
- name: `?SpoolerUserInit@@YAXPEAUUSER_INFO@@@Z`
- size: `634`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `18`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140071760`

## callees

- `0x14000e700`
- `0x140010c4c`
- `0x140012c48`
- `0x140013318`
- `0x140015004`
- `0x140015378`
- `0x140016e60`
- `0x1400170f8`
- `0x140017970`
- `0x140017c20`
- `0x140018a8c`
- `0x140070048`
- `0x14007013c`
- `0x1400702f8`
- `0x1400709e0`
- `0x140070e2c`
- `0x140070ebc`
- `0x140071470`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400716d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400716d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400716b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400716b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14007162d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14007162d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140071675`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140071675`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400714d3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400714d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14007169e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14007169e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400715d4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400715d4`
- `IppCommon!InstallVirtualPrintersForSessionId` at `0x14007168e`
- `IppCommon!InstallVirtualPrintersForSessionId` at `0x14007168e`

## pseudocode

```c
BOOL __fastcall SpoolerUserInit(_QWORD *Parameter)
{
  HKEY *v1; // rsi
  HKEY v3; // rcx
  DWORD v4; // eax
  NCoreLibrary *v5; // rcx
  unsigned int v6; // r8d
  HANDLE v7; // rcx
  NCoreLibrary::TString *v8; // rcx
  HKEY v9; // rbx
  __int64 v10; // rdx
  DWORD ReturnLength; // [rsp+90h] [rbp+30h] BYREF
  unsigned int TokenInformation; // [rsp+98h] [rbp+38h] BYREF
  HKEY phkResult; // [rsp+A0h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+48h] BYREF

  v1 = (HKEY *)(Parameter + 1);
  TokenInformation = 0;
  v3 = (HKEY)Parameter[1];
  ReturnLength = 0;
  phkResult = 0;
  DeleteSymbolicLink(v3, L"Printers");
  v4 = RegCreateKeyExW(*v1, L"Printers", 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  ReturnLength = v4;
  if ( v4 || (v4 = SetPermissionsForAppContainer(phkResult), (ReturnLength = v4) != 0) )
    PrvSpoolssTelemetry::WriteDbgTraceError(
      "SpoolerUserInit",
      L"Failed to check or set AppContainer permissions. Error %d",
      v4);
  NCoreLibrary::TGenericSP<HKEY__ *,NCoreLibrary::TAutoHandleHKEY,HKEY__ *,0,HKEY__ * const *>::Reset(&phkResult);
  if ( !Initialized
    && (int)NCoreLibrary::WaitForAutoEventHandle(v5, (struct NCoreLibrary::TAutoHandle *)0x1D4C0, v6) < 0 )
  {
    WaitForSpoolerInitialization();
  }
  if ( !(unsigned int)DoesSessionSidKeyExists((HANDLE)*Parameter) )
  {
    if ( (unsigned int)InitializeRegUser(0, v1) )
    {
      SetupRegForUsers((struct INIT_REG_USER *)v1, 1u);
      v7 = (HANDLE)*Parameter;
      phkResult = (HKEY)&NCoreLibrary::TString::gszNullState;
      if ( NSecurityLibrary::TSidUserContext::GetSidAsString(v7, (struct NCoreLibrary::TString *)&phkResult) < 0
        || NCoreLibrary::TString::Cat((NCoreLibrary::TString *)&phkResult, L"_Classes") < 0 )
      {
        v9 = phkResult;
      }
      else
      {
        v9 = phkResult;
        CleanupUserPropertyBags((const unsigned __int16 *)phkResult);
      }
      NCoreLibrary::TString::vFree(v8, v9);
    }
    RouterBroadcastMessage(3u, 0, 0, 0, 0);
    if ( GetTokenInformation((HANDLE)*Parameter, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
      UpdateUserInfo(1, 1, TokenInformation, Parameter);
    LOBYTE(v10) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements>::GetImpl'::`2'::impl,
      v10);
    hKey = 0;
    LODWORD(phkResult) = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Control\\Print\\Actions\\PerUserLogon\\AllUserVirtualPrinters",
            0,
            1u,
            &hKey) )
    {
      if ( !RegQueryInfoKeyW(hKey, 0, 0, 0, (LPDWORD)&phkResult, 0, 0, 0, 0, 0, 0, 0) && (_DWORD)phkResult )
        InstallVirtualPrintersForSessionId(TokenInformation);
      RegCloseKey(hKey);
    }
  }
  if ( *Parameter )
    CloseHandle((HANDLE)*Parameter);
  FreeRegUser((struct INIT_REG_USER *)v1);
  return HeapFree(g_hSpoolssHeap, 0, Parameter);
}

```

## disassembly

```asm
0x140071470  push    rbp
0x140071472  push    rbx
0x140071473  push    rsi
0x140071474  push    rdi
0x140071475  push    r14
0x140071477  mov     rbp, rsp
0x14007147a  sub     rsp, 60h
0x14007147e  xor     r14d, r14d
0x140071481  lea     rsi, [rcx+8]
0x140071485  mov     rdi, rcx
0x140071488  mov     [rbp+TokenInformation], r14d
0x14007148c  mov     rcx, [rsi]; HKEY
0x14007148f  lea     rdx, szPrinters; "Printers"
0x140071496  mov     [rbp+ReturnLength], r14d
0x14007149a  mov     [rbp+arg_10], r14
0x14007149e  call    ?DeleteSymbolicLink@@YAHPEAUHKEY__@@PEBG@Z; DeleteSymbolicLink(HKEY__ *,ushort const *)
0x1400714a3  mov     rcx, [rsi]; hKey
0x1400714a6  lea     rax, [rbp+arg_10]
0x1400714aa  mov     [rsp+60h+lpdwDisposition], r14; lpdwDisposition
0x1400714af  lea     rdx, szPrinters; "Printers"
0x1400714b6  mov     [rsp+60h+phkResult], rax; phkResult
0x1400714bb  xor     r9d, r9d; lpClass
0x1400714be  mov     [rsp+60h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1400714c3  xor     r8d, r8d; Reserved
0x1400714c6  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x1400714ce  mov     [rsp+60h+dwOptions], r14d; dwOptions
0x1400714d3  call    cs:__imp_RegCreateKeyExW
0x1400714da  nop     dword ptr [rax+rax+00h]
0x1400714df  mov     [rbp+ReturnLength], eax
0x1400714e2  test    eax, eax
0x1400714e4  jnz     short loc_1400714F6
0x1400714e6  mov     rcx, [rbp+arg_10]; HKEY
0x1400714ea  call    ?SetPermissionsForAppContainer@@YAKPEAUHKEY__@@_N@Z; SetPermissionsForAppContainer(HKEY__ *,bool)
0x1400714ef  mov     [rbp+ReturnLength], eax
0x1400714f2  test    eax, eax
0x1400714f4  jz      short loc_14007150C
0x1400714f6  mov     r8d, eax
0x1400714f9  lea     rdx, aFailedToCheckO; "Failed to check or set AppContainer per"...
0x140071500  lea     rcx, aSpooleruserini; "SpoolerUserInit"
0x140071507  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14007150c  lea     rcx, [rbp+arg_10]
0x140071510  call    ?Reset@?$TGenericSP@PEAUHKEY__@@VTAutoHandleHKEY@NCoreLibrary@@PEAU1@$0A@PEBQEAU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<HKEY__ *,NCoreLibrary::TAutoHandleHKEY,HKEY__ *,0,HKEY__ * const *>::Reset(void)
0x140071515  cmp     cs:?Initialized@@3HA, r14d; int Initialized
0x14007151c  jnz     short loc_140071531
0x14007151e  mov     edx, 1D4C0h; struct NCoreLibrary::TAutoHandle *
0x140071523  call    ?WaitForAutoEventHandle@NCoreLibrary@@YAJPEAVTAutoHandle@1@K@Z; NCoreLibrary::WaitForAutoEventHandle(NCoreLibrary::TAutoHandle *,ulong)
0x140071528  test    eax, eax
0x14007152a  jns     short loc_140071531
0x14007152c  call    WaitForSpoolerInitialization
0x140071531  mov     rcx, [rdi]; TokenHandle
0x140071534  call    DoesSessionSidKeyExists
0x140071539  test    eax, eax
0x14007153b  jnz     loc_1400716AA
0x140071541  mov     rdx, rsi; struct INIT_REG_USER *
0x140071544  xor     ecx, ecx; unsigned __int16 *
0x140071546  call    ?InitializeRegUser@@YAHPEAGPEAUINIT_REG_USER@@@Z; InitializeRegUser(ushort *,INIT_REG_USER *)
0x14007154b  test    eax, eax
0x14007154d  jz      short loc_1400715A5
0x14007154f  mov     edx, 1; unsigned int
0x140071554  mov     rcx, rsi; struct INIT_REG_USER *
0x140071557  call    ?SetupRegForUsers@@YAHPEAUINIT_REG_USER@@K@Z; SetupRegForUsers(INIT_REG_USER *,ulong)
0x14007155c  mov     rcx, [rdi]; void *
0x14007155f  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x140071566  lea     rdx, [rbp+arg_10]; struct NCoreLibrary::TString *
0x14007156a  mov     [rbp+arg_10], rax
0x14007156e  call    ?GetSidAsString@TSidUserContext@NSecurityLibrary@@SAJPEAXAEAVTString@NCoreLibrary@@@Z; NSecurityLibrary::TSidUserContext::GetSidAsString(void *,NCoreLibrary::TString &)
0x140071573  test    eax, eax
0x140071575  js      short loc_140071599
0x140071577  lea     rdx, aClasses; "_Classes"
0x14007157e  lea     rcx, [rbp+arg_10]; this
0x140071582  call    ?Cat@TString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TString::Cat(ushort const *)
0x140071587  test    eax, eax
0x140071589  js      short loc_140071599
0x14007158b  mov     rbx, [rbp+arg_10]
0x14007158f  mov     rcx, rbx; unsigned __int16 *
0x140071592  call    ?CleanupUserPropertyBags@@YAXPEBG@Z; CleanupUserPropertyBags(ushort const *)
0x140071597  jmp     short loc_14007159D
0x140071599  mov     rbx, [rbp+arg_10]
0x14007159d  mov     rdx, rbx; void *
0x1400715a0  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x1400715a5  xor     edx, edx; unsigned int
0x1400715a7  mov     qword ptr [rsp+60h+dwOptions], r14; __int64
0x1400715ac  xor     r9d, r9d; unsigned __int64
0x1400715af  xor     r8d, r8d; unsigned int
0x1400715b2  lea     ecx, [rdx+3]; unsigned int
0x1400715b5  call    RouterBroadcastMessage
0x1400715ba  mov     rcx, [rdi]; TokenHandle
0x1400715bd  lea     rax, [rbp+ReturnLength]
0x1400715c1  mov     r9d, 4; TokenInformationLength
0x1400715c7  mov     qword ptr [rsp+60h+dwOptions], rax; ReturnLength
0x1400715cc  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1400715d0  lea     edx, [r9+8]; TokenInformationClass
0x1400715d4  call    cs:__imp_GetTokenInformation
0x1400715db  nop     dword ptr [rax+rax+00h]
0x1400715e0  test    eax, eax
0x1400715e2  jz      short loc_1400715F7
0x1400715e4  mov     r8d, [rbp+TokenInformation]
0x1400715e8  mov     edx, 1
0x1400715ed  mov     ecx, edx
0x1400715ef  mov     r9, rdi
0x1400715f2  call    UpdateUserInfo
0x1400715f7  mov     dl, 1
0x1400715f9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements> `wil::Feature<__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements>::GetImpl(void)'::`2'::impl
0x140071600  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x140071605  lea     rax, [rbp+hKey]
0x140071609  mov     [rbp+hKey], r14
0x14007160d  mov     r9d, 1; samDesired
0x140071613  mov     qword ptr [rsp+60h+dwOptions], rax; phkResult
0x140071618  xor     r8d, r8d; ulOptions
0x14007161b  mov     dword ptr [rbp+arg_10], r14d
0x14007161f  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Control\\Pri"...
0x140071626  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14007162d  call    cs:__imp_RegOpenKeyExW
0x140071634  nop     dword ptr [rax+rax+00h]
0x140071639  test    eax, eax
0x14007163b  jnz     short loc_1400716AA
0x14007163d  mov     rcx, [rbp+hKey]; hKey
0x140071641  lea     rax, [rbp+arg_10]
0x140071645  mov     [rsp+60h+lpftLastWriteTime], r14; lpftLastWriteTime
0x14007164a  xor     r9d, r9d; lpReserved
0x14007164d  mov     [rsp+60h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x140071652  xor     r8d, r8d; lpcchClass
0x140071655  mov     [rsp+60h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x14007165a  xor     edx, edx; lpClass
0x14007165c  mov     [rsp+60h+lpdwDisposition], r14; lpcbMaxValueNameLen
0x140071661  mov     [rsp+60h+phkResult], r14; lpcValues
0x140071666  mov     [rsp+60h+lpSecurityAttributes], r14; lpcbMaxClassLen
0x14007166b  mov     qword ptr [rsp+60h+samDesired], r14; lpcbMaxSubKeyLen
0x140071670  mov     qword ptr [rsp+60h+dwOptions], rax; lpcSubKeys
0x140071675  call    cs:__imp_RegQueryInfoKeyW
0x14007167c  nop     dword ptr [rax+rax+00h]
0x140071681  test    eax, eax
0x140071683  jnz     short loc_14007169A
0x140071685  cmp     dword ptr [rbp+arg_10], r14d
0x140071689  jz      short loc_14007169A
0x14007168b  mov     ecx, [rbp+TokenInformation]
0x14007168e  call    cs:__imp_InstallVirtualPrintersForSessionId
0x140071695  nop     dword ptr [rax+rax+00h]
0x14007169a  mov     rcx, [rbp+hKey]; hKey
0x14007169e  call    cs:__imp_RegCloseKey
0x1400716a5  nop     dword ptr [rax+rax+00h]
0x1400716aa  mov     rcx, [rdi]; hObject
0x1400716ad  test    rcx, rcx
0x1400716b0  jz      short loc_1400716BE
0x1400716b2  call    cs:__imp_CloseHandle
0x1400716b9  nop     dword ptr [rax+rax+00h]
0x1400716be  mov     rcx, rsi; struct INIT_REG_USER *
0x1400716c1  call    ?FreeRegUser@@YAXPEAUINIT_REG_USER@@@Z; FreeRegUser(INIT_REG_USER *)
0x1400716c6  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x1400716cd  mov     r8, rdi; lpMem
0x1400716d0  xor     edx, edx; dwFlags
0x1400716d2  call    cs:__imp_HeapFree
0x1400716d9  nop     dword ptr [rax+rax+00h]
0x1400716de  add     rsp, 60h
0x1400716e2  pop     r14
0x1400716e4  pop     rdi
0x1400716e5  pop     rsi
0x1400716e6  pop     rbx
0x1400716e7  pop     rbp
0x1400716e8  retn
```
