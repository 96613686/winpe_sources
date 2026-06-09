# SpoolerUserInit(USER_INFO *)

- ea: `0x14006a910`
- end: `0x14006ab59`
- name: `?SpoolerUserInit@@YAXPEAUUSER_INFO@@@Z`
- size: `585`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `18`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14006abd0`

## callees

- `0x14000d520`
- `0x14000fa4c`
- `0x140011ebc`
- `0x14001246c`
- `0x140013d64`
- `0x1400140cc`
- `0x140015afc`
- `0x140015c30`
- `0x140016520`
- `0x14001678c`
- `0x140017604`
- `0x140069688`
- `0x140069778`
- `0x140069910`
- `0x140069f68`
- `0x14006a350`
- `0x14006a3dc`
- `0x14006a910`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006ab48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006ab48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006ab2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006ab2e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14006aac1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14006aac1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14006ab03`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14006ab03`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14006a973`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14006a973`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14006ab20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14006ab20`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14006aa6e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14006aa6e`
- `IppCommon!InstallVirtualPrintersForSessionId` at `0x14006ab16`
- `IppCommon!InstallVirtualPrintersForSessionId` at `0x14006ab16`

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
      if ( (int)NSecurityLibrary::TSidUserContext::GetSidAsString(v7, (struct NCoreLibrary::TString *)&phkResult) < 0
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
0x14006a910  push    rbp
0x14006a912  push    rbx
0x14006a913  push    rsi
0x14006a914  push    rdi
0x14006a915  push    r14
0x14006a917  mov     rbp, rsp
0x14006a91a  sub     rsp, 60h
0x14006a91e  xor     r14d, r14d
0x14006a921  lea     rsi, [rcx+8]
0x14006a925  mov     rdi, rcx
0x14006a928  mov     [rbp+TokenInformation], r14d
0x14006a92c  mov     rcx, [rsi]; HKEY
0x14006a92f  lea     rdx, szPrinters; "Printers"
0x14006a936  mov     [rbp+ReturnLength], r14d
0x14006a93a  mov     [rbp+arg_10], r14
0x14006a93e  call    ?DeleteSymbolicLink@@YAHPEAUHKEY__@@PEBG@Z; DeleteSymbolicLink(HKEY__ *,ushort const *)
0x14006a943  mov     rcx, [rsi]; hKey
0x14006a946  lea     rax, [rbp+arg_10]
0x14006a94a  mov     [rsp+60h+lpdwDisposition], r14; lpdwDisposition
0x14006a94f  lea     rdx, szPrinters; "Printers"
0x14006a956  mov     [rsp+60h+phkResult], rax; phkResult
0x14006a95b  xor     r9d, r9d; lpClass
0x14006a95e  mov     [rsp+60h+lpSecurityAttributes], r14; lpSecurityAttributes
0x14006a963  xor     r8d, r8d; Reserved
0x14006a966  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x14006a96e  mov     [rsp+60h+dwOptions], r14d; dwOptions
0x14006a973  call    cs:__imp_RegCreateKeyExW
0x14006a979  mov     [rbp+ReturnLength], eax
0x14006a97c  test    eax, eax
0x14006a97e  jnz     short loc_14006A990
0x14006a980  mov     rcx, [rbp+arg_10]; HKEY
0x14006a984  call    ?SetPermissionsForAppContainer@@YAKPEAUHKEY__@@_N@Z; SetPermissionsForAppContainer(HKEY__ *,bool)
0x14006a989  mov     [rbp+ReturnLength], eax
0x14006a98c  test    eax, eax
0x14006a98e  jz      short loc_14006A9A6
0x14006a990  mov     r8d, eax
0x14006a993  lea     rdx, aFailedToCheckO; "Failed to check or set AppContainer per"...
0x14006a99a  lea     rcx, aSpooleruserini; "SpoolerUserInit"
0x14006a9a1  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006a9a6  lea     rcx, [rbp+arg_10]
0x14006a9aa  call    ?Reset@?$TGenericSP@PEAUHKEY__@@VTAutoHandleHKEY@NCoreLibrary@@PEAU1@$0A@PEBQEAU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<HKEY__ *,NCoreLibrary::TAutoHandleHKEY,HKEY__ *,0,HKEY__ * const *>::Reset(void)
0x14006a9af  cmp     cs:?Initialized@@3HA, r14d; int Initialized
0x14006a9b6  jnz     short loc_14006A9CB
0x14006a9b8  mov     edx, 1D4C0h; struct NCoreLibrary::TAutoHandle *
0x14006a9bd  call    ?WaitForAutoEventHandle@NCoreLibrary@@YAJPEAVTAutoHandle@1@K@Z; NCoreLibrary::WaitForAutoEventHandle(NCoreLibrary::TAutoHandle *,ulong)
0x14006a9c2  test    eax, eax
0x14006a9c4  jns     short loc_14006A9CB
0x14006a9c6  call    WaitForSpoolerInitialization
0x14006a9cb  mov     rcx, [rdi]; TokenHandle
0x14006a9ce  call    DoesSessionSidKeyExists
0x14006a9d3  test    eax, eax
0x14006a9d5  jnz     loc_14006AB26
0x14006a9db  mov     rdx, rsi; struct INIT_REG_USER *
0x14006a9de  xor     ecx, ecx; unsigned __int16 *
0x14006a9e0  call    ?InitializeRegUser@@YAHPEAGPEAUINIT_REG_USER@@@Z; InitializeRegUser(ushort *,INIT_REG_USER *)
0x14006a9e5  test    eax, eax
0x14006a9e7  jz      short loc_14006AA3F
0x14006a9e9  mov     edx, 1; unsigned int
0x14006a9ee  mov     rcx, rsi; struct INIT_REG_USER *
0x14006a9f1  call    ?SetupRegForUsers@@YAHPEAUINIT_REG_USER@@K@Z; SetupRegForUsers(INIT_REG_USER *,ulong)
0x14006a9f6  mov     rcx, [rdi]; TokenHandle
0x14006a9f9  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x14006aa00  lea     rdx, [rbp+arg_10]; this
0x14006aa04  mov     [rbp+arg_10], rax
0x14006aa08  call    ?GetSidAsString@TSidUserContext@NSecurityLibrary@@SAJPEAXAEAVTString@NCoreLibrary@@@Z; NSecurityLibrary::TSidUserContext::GetSidAsString(void *,NCoreLibrary::TString &)
0x14006aa0d  test    eax, eax
0x14006aa0f  js      short loc_14006AA33
0x14006aa11  lea     rdx, aClasses; "_Classes"
0x14006aa18  lea     rcx, [rbp+arg_10]; this
0x14006aa1c  call    ?Cat@TString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TString::Cat(ushort const *)
0x14006aa21  test    eax, eax
0x14006aa23  js      short loc_14006AA33
0x14006aa25  mov     rbx, [rbp+arg_10]
0x14006aa29  mov     rcx, rbx; unsigned __int16 *
0x14006aa2c  call    ?CleanupUserPropertyBags@@YAXPEBG@Z; CleanupUserPropertyBags(ushort const *)
0x14006aa31  jmp     short loc_14006AA37
0x14006aa33  mov     rbx, [rbp+arg_10]
0x14006aa37  mov     rdx, rbx; void *
0x14006aa3a  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x14006aa3f  xor     edx, edx; unsigned int
0x14006aa41  mov     qword ptr [rsp+60h+dwOptions], r14; __int64
0x14006aa46  xor     r9d, r9d; unsigned __int64
0x14006aa49  xor     r8d, r8d; unsigned int
0x14006aa4c  lea     ecx, [rdx+3]; unsigned int
0x14006aa4f  call    RouterBroadcastMessage
0x14006aa54  mov     rcx, [rdi]; TokenHandle
0x14006aa57  lea     rax, [rbp+ReturnLength]
0x14006aa5b  mov     r9d, 4; TokenInformationLength
0x14006aa61  mov     qword ptr [rsp+60h+dwOptions], rax; ReturnLength
0x14006aa66  lea     r8, [rbp+TokenInformation]; TokenInformation
0x14006aa6a  lea     edx, [r9+8]; TokenInformationClass
0x14006aa6e  call    cs:__imp_GetTokenInformation
0x14006aa74  test    eax, eax
0x14006aa76  jz      short loc_14006AA8B
0x14006aa78  mov     r8d, [rbp+TokenInformation]
0x14006aa7c  mov     edx, 1
0x14006aa81  mov     ecx, edx
0x14006aa83  mov     r9, rdi
0x14006aa86  call    UpdateUserInfo
0x14006aa8b  mov     dl, 1
0x14006aa8d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements> `wil::Feature<__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements>::GetImpl(void)'::`2'::impl
0x14006aa94  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14006aa99  lea     rax, [rbp+hKey]
0x14006aa9d  mov     [rbp+hKey], r14
0x14006aaa1  mov     r9d, 1; samDesired
0x14006aaa7  mov     qword ptr [rsp+60h+dwOptions], rax; phkResult
0x14006aaac  xor     r8d, r8d; ulOptions
0x14006aaaf  mov     dword ptr [rbp+arg_10], r14d
0x14006aab3  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Control\\Pri"...
0x14006aaba  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14006aac1  call    cs:__imp_RegOpenKeyExW
0x14006aac7  test    eax, eax
0x14006aac9  jnz     short loc_14006AB26
0x14006aacb  mov     rcx, [rbp+hKey]; hKey
0x14006aacf  lea     rax, [rbp+arg_10]
0x14006aad3  mov     [rsp+60h+lpftLastWriteTime], r14; lpftLastWriteTime
0x14006aad8  xor     r9d, r9d; lpReserved
0x14006aadb  mov     [rsp+60h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x14006aae0  xor     r8d, r8d; lpcchClass
0x14006aae3  mov     [rsp+60h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x14006aae8  xor     edx, edx; lpClass
0x14006aaea  mov     [rsp+60h+lpdwDisposition], r14; lpcbMaxValueNameLen
0x14006aaef  mov     [rsp+60h+phkResult], r14; lpcValues
0x14006aaf4  mov     [rsp+60h+lpSecurityAttributes], r14; lpcbMaxClassLen
0x14006aaf9  mov     qword ptr [rsp+60h+samDesired], r14; lpcbMaxSubKeyLen
0x14006aafe  mov     qword ptr [rsp+60h+dwOptions], rax; lpcSubKeys
0x14006ab03  call    cs:__imp_RegQueryInfoKeyW
0x14006ab09  test    eax, eax
0x14006ab0b  jnz     short loc_14006AB1C
0x14006ab0d  cmp     dword ptr [rbp+arg_10], r14d
0x14006ab11  jz      short loc_14006AB1C
0x14006ab13  mov     ecx, [rbp+TokenInformation]
0x14006ab16  call    cs:__imp_InstallVirtualPrintersForSessionId
0x14006ab1c  mov     rcx, [rbp+hKey]; hKey
0x14006ab20  call    cs:__imp_RegCloseKey
0x14006ab26  mov     rcx, [rdi]; hObject
0x14006ab29  test    rcx, rcx
0x14006ab2c  jz      short loc_14006AB34
0x14006ab2e  call    cs:__imp_CloseHandle
0x14006ab34  mov     rcx, rsi; struct INIT_REG_USER *
0x14006ab37  call    ?FreeRegUser@@YAXPEAUINIT_REG_USER@@@Z; FreeRegUser(INIT_REG_USER *)
0x14006ab3c  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14006ab43  mov     r8, rdi; lpMem
0x14006ab46  xor     edx, edx; dwFlags
0x14006ab48  call    cs:__imp_HeapFree
0x14006ab4e  add     rsp, 60h
0x14006ab52  pop     r14
0x14006ab54  pop     rdi
0x14006ab55  pop     rsi
0x14006ab56  pop     rbx
0x14006ab57  pop     rbp
0x14006ab58  retn
```
