# _lambda_ea9c6a719f4a9bb818bf1c421ccbcdfc_::operator()(void)

- ea: `0x1800348f8`
- end: `0x180034a6b`
- name: `??R_lambda_ea9c6a719f4a9bb818bf1c421ccbcdfc_@@QEBA@XZ`
- size: `371`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180009960`
- `0x180025108`

## callees

- `0x1800034f8`
- `0x18000bfd8`
- `0x18001d64c`
- `0x18001f73c`
- `0x18002d4f8`
- `0x1800348f8`
- `0x180035830`
- `0x1800409bc`
- `0x180041438`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800349a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800349a6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180034a12`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180034a12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034972`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034972`

## pseudocode

```c
__int64 __fastcall _lambda_ea9c6a719f4a9bb818bf1c421ccbcdfc_::operator()(bool **a1, const unsigned __int16 **a2)
{
  int SyncRootManagerRegistryLocation; // eax
  unsigned int v4; // ebx
  HKEY v5; // rbx
  unsigned int v6; // eax
  unsigned int v7; // r8d
  __int64 v8; // rdx
  int phkResult; // [rsp+20h] [rbp-19h]
  unsigned int phkResulta; // [rsp+20h] [rbp-19h]
  LPCWSTR lpSubKey; // [rsp+60h] [rbp+27h] BYREF
  _BYTE v13[8]; // [rsp+68h] [rbp+2Fh] BYREF
  DWORD cSubKeys; // [rsp+70h] [rbp+37h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+3Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  lpSubKey = 0;
  SyncRootManagerRegistryLocation = Windows::Internal::SyncRootHelpers::GetSyncRootManagerRegistryLocation(
                                      (Windows::Internal::SyncRootHelpers *)&lpSubKey,
                                      a2);
  v4 = SyncRootManagerRegistryLocation;
  if ( SyncRootManagerRegistryLocation >= 0 )
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&hKey);
    v5 = hKey;
    if ( hKey )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v13);
      RegCloseKey(v5);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v13);
    }
    hKey = 0;
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, &hKey);
    if ( v6 )
    {
      v8 = 62;
    }
    else
    {
      cSubKeys = 0;
      v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
      if ( !v6 )
      {
        v4 = 0;
        **a1 = cSubKeys != 0;
        goto LABEL_11;
      }
      v8 = 66;
    }
    v4 = wil::details::in1diag3::Return_Win32(retaddr, (void *)v8, v7, (const char *)v6, phkResulta);
LABEL_11:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v4;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3B,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\StateSepUtil.h",
    (const char *)(unsigned int)SyncRootManagerRegistryLocation,
    phkResult);
  return v4;
}

```

## disassembly

```asm
0x1800348f8  mov     [rsp-8+arg_8], rbx
0x1800348fd  mov     [rsp-8+arg_10], rdi
0x180034902  push    rbp
0x180034903  lea     rbp, [rsp-57h]
0x180034908  sub     rsp, 90h
0x18003490f  mov     rax, cs:__security_cookie
0x180034916  xor     rax, rsp
0x180034919  mov     [rbp+57h+var_10], rax
0x18003491d  mov     rdi, rcx
0x180034920  mov     [rbp+57h+lpSubKey], 0
0x180034928  lea     rcx, [rbp+57h+lpSubKey]; this
0x18003492c  call    ?GetSyncRootManagerRegistryLocation@SyncRootHelpers@Internal@Windows@@YAJPEAPEBG@Z; Windows::Internal::SyncRootHelpers::GetSyncRootManagerRegistryLocation(ushort const * *)
0x180034931  mov     ebx, eax
0x180034933  test    eax, eax
0x180034935  jns     short loc_180034954
0x180034937  mov     rcx, [rbp+5Fh]; this
0x18003493b  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180034942  mov     r9d, eax; char *
0x180034945  mov     edx, 3Bh ; ';'; void *
0x18003494a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003494f  jmp     loc_180034A48
0x180034954  lea     rcx, [rbp+57h+hKey]
0x180034958  call    ??0?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18003495d  mov     rbx, [rbp+57h+hKey]
0x180034961  test    rbx, rbx
0x180034964  jz      short loc_180034981
0x180034966  lea     rcx, [rbp+57h+var_28]; this
0x18003496a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003496f  mov     rcx, rbx; hKey
0x180034972  call    cs:__imp_RegCloseKey
0x180034978  lea     rcx, [rbp+57h+var_28]; this
0x18003497c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180034981  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180034985  lea     rax, [rbp+57h+hKey]
0x180034989  mov     r9d, 20119h; samDesired
0x18003498f  mov     [rsp+90h+phkResult], rax; phkResult
0x180034994  xor     r8d, r8d; ulOptions
0x180034997  mov     [rbp+57h+hKey], 0
0x18003499f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800349a6  call    cs:__imp_RegOpenKeyExW
0x1800349ac  test    eax, eax
0x1800349ae  jz      short loc_1800349B7
0x1800349b0  mov     edx, 3Eh ; '>'
0x1800349b5  jmp     short loc_180034A21
0x1800349b7  mov     rcx, [rbp+57h+hKey]; hKey
0x1800349bb  lea     rax, [rbp+57h+cSubKeys]
0x1800349bf  mov     [rsp+90h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800349c8  xor     r9d, r9d; lpReserved
0x1800349cb  mov     [rsp+90h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x1800349d4  xor     r8d, r8d; lpcchClass
0x1800349d7  mov     [rsp+90h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x1800349e0  xor     edx, edx; lpClass
0x1800349e2  mov     [rsp+90h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x1800349eb  mov     [rsp+90h+lpcValues], 0; lpcValues
0x1800349f4  mov     [rsp+90h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x1800349fd  mov     [rsp+90h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x180034a06  mov     [rsp+90h+phkResult], rax; unsigned int
0x180034a0b  mov     [rbp+57h+cSubKeys], 0
0x180034a12  call    cs:__imp_RegQueryInfoKeyW
0x180034a18  test    eax, eax
0x180034a1a  jz      short loc_180034A31
0x180034a1c  mov     edx, 42h ; 'B'; void *
0x180034a21  mov     rcx, [rbp+5Fh]; this
0x180034a25  mov     r9d, eax; char *
0x180034a28  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180034a2d  mov     ebx, eax
0x180034a2f  jmp     short loc_180034A3F
0x180034a31  cmp     [rbp+57h+cSubKeys], 0
0x180034a35  mov     rax, [rdi]
0x180034a38  setnbe  cl
0x180034a3b  xor     ebx, ebx
0x180034a3d  mov     [rax], cl
0x180034a3f  lea     rcx, [rbp+57h+hKey]
0x180034a43  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180034a48  mov     eax, ebx
0x180034a4a  mov     rcx, [rbp+57h+var_10]
0x180034a4e  xor     rcx, rsp; StackCookie
0x180034a51  call    __security_check_cookie
0x180034a56  lea     r11, [rsp+90h+var_s0]
0x180034a5e  mov     rbx, [r11+18h]
0x180034a62  mov     rdi, [r11+20h]
0x180034a66  mov     rsp, r11
0x180034a69  pop     rbp
0x180034a6a  retn
```
