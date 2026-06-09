# CapturedCallerContext::GetStateRegKey(ushort const *,ulong,HKEY__ * *)

- ea: `0x1801bd540`
- end: `0x1801bdab1`
- name: `?GetStateRegKey@CapturedCallerContext@@UEAAJPEBGKPEAPEAUHKEY__@@@Z`
- size: `1393`
- prototype: `int(CapturedCallerContext *__hidden this, const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180038f50`
- `0x18004e06c`
- `0x180063050`
- `0x180080c40`
- `0x1800b5d60`
- `0x1801bd540`
- `0x1801bdab8`
- `0x1801bdc30`
- `0x1801bdff4`
- `0x180370e34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801bd65d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801bd65d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801bd63a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801bd63a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bd64f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bd6fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bd786`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bd7fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bd928`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bd981`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bd9da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bd9ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bda48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bda5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bdaa0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bd64f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bd6fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bd786`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bd7fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bd928`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bd981`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bd9da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bd9ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bda48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bda5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bdaa0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801bd6dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180670e3e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801bd6dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180670e3e`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1801bd676`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1801bd676`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180670e78`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180670e78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bd710`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bd79c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bd814`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bd8e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bd93e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bd997`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bda05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bda73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bd710`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bd79c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bd814`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bd8e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bd93e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bd997`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bda05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bda73`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x1801bd735`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x1801bd7c5`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x1801bd86b`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x1801bd8b0`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x1801bd735`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x1801bd7c5`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x1801bd86b`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x1801bd8b0`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x1801bd5b0`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x1801bd611`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x1801bd5b0`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x1801bd611`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CapturedCallerContext::GetStateRegKey(HANDLE *this, const unsigned __int16 *a2, REGSAM a3, HKEY *a4)
{
  int Error; // edi
  int v9; // eax
  unsigned int v10; // ebx
  HKEY v11; // rbx
  int v12; // edx
  int v13; // ecx
  int v14; // eax
  LPCWSTR v15; // rdi
  HKEY v16; // rcx
  DWORD LastError; // esi
  unsigned int v18; // eax
  unsigned int i; // eax
  unsigned int v20; // eax
  void *v21; // rdx
  int v23; // eax
  void *v24; // rdx
  HANDLE v25; // rcx
  unsigned int v26; // eax
  unsigned int Key; // eax
  unsigned int v28; // [rsp+20h] [rbp-58h]
  unsigned int v29; // [rsp+20h] [rbp-58h]
  unsigned int v30; // [rsp+20h] [rbp-58h]
  unsigned int v31; // [rsp+20h] [rbp-58h]
  HKEY phkResult; // [rsp+50h] [rbp-28h] BYREF
  LPCWSTR lpSubKey; // [rsp+58h] [rbp-20h] BYREF
  HANDLE Token; // [rsp+60h] [rbp-18h]
  HKEY hKey[2]; // [rsp+68h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]
  unsigned int v37; // [rsp+D8h] [rbp+60h] BYREF

  *a4 = 0;
  hKey[0] = 0;
  Error = CapturedCallerContext::OpenStateHandle((CapturedCallerContext *)this, (void **)hKey);
  if ( Error < 0 )
  {
    if ( hKey[0] )
      CloseState(hKey[0]);
    return (unsigned int)Error;
  }
  v37 = 0;
  Token = (HANDLE)-1LL;
  v9 = wil::impersonate_token_nothrow(this[8]);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23D,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\capturedcallercontextlib\\capturedcallercontext.cpp",
      (const char *)(unsigned int)v9,
      v28);
    if ( hKey[0] )
      CloseState(hKey[0]);
    return v10;
  }
  v11 = hKey[0];
  if ( (unsigned int)GetSystemAppDataKey(hKey[0], 0, 0, &v37) )
  {
    Error = -2147418113;
LABEL_43:
    if ( Error < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x241,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\capturedcallercontextlib\\capturedcallercontext.cpp",
        (const char *)(unsigned int)Error,
        v28);
    goto LABEL_34;
  }
  Error = ResultFromKnownLastError();
  if ( Error != -2147024774 )
    goto LABEL_43;
  lpSubKey = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&lpSubKey);
  v14 = _AllocStringWorker<CTCoAllocPolicy>(v13, v12, 0, v37);
  Error = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x244,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\capturedcallercontextlib\\capturedcallercontext.cpp",
      (const char *)(unsigned int)v14,
      v28);
    if ( lpSubKey )
      CoTaskMemFree((LPVOID)lpSubKey);
    v25 = Token;
    if ( Token != (HANDLE)-1LL )
      goto LABEL_33;
    goto LABEL_34;
  }
  phkResult = 0;
  if ( !(unsigned int)GetSystemAppDataKey(v11, &phkResult, lpSubKey, &v37) )
  {
    v23 = ResultFromKnownLastError();
    Error = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x248,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\capturedcallercontextlib\\capturedcallercontext.cpp",
        (const char *)(unsigned int)v23,
        v28);
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( lpSubKey )
        CoTaskMemFree((LPVOID)lpSubKey);
      v25 = Token;
      if ( Token != (HANDLE)-1LL )
LABEL_33:
        wil::details::RevertImpersonateToken(v25, v24);
LABEL_34:
      if ( v11 )
      {
        CloseState(v11);
        return (unsigned int)Error;
      }
      return (unsigned int)Error;
    }
  }
  v15 = lpSubKey;
  v16 = phkResult;
  if ( phkResult == HKEY_USERS )
  {
    LastError = GetLastError();
    RegCloseKey(HKEY_USERS);
    SetLastError(LastError);
    phkResult = 0;
    v18 = RegOpenCurrentUser(0x2000000u, &phkResult);
    if ( v18 )
    {
      Error = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x252,
                (unsigned int)"onecoreuap\\shell\\windows.storage\\capturedcallercontextlib\\capturedcallercontext.cpp",
                (const char *)v18,
                v28);
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( lpSubKey )
        CoTaskMemFree((LPVOID)lpSubKey);
      v25 = Token;
      if ( Token != (HANDLE)-1LL )
        goto LABEL_33;
      goto LABEL_34;
    }
    for ( i = 0; i < v37; ++v15 )
    {
      if ( *v15 == 92 )
        break;
      if ( !*v15 )
        break;
      ++i;
    }
    if ( i == v37 || *v15 != 92 )
    {
      Error = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x259,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\capturedcallercontextlib\\capturedcallercontext.cpp",
        (const char *)0x8000FFFFLL,
        v28);
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( lpSubKey )
        CoTaskMemFree((LPVOID)lpSubKey);
      v25 = Token;
      if ( Token != (HANDLE)-1LL )
        goto LABEL_33;
      goto LABEL_34;
    }
    ++v15;
    v16 = phkResult;
  }
  if ( a2 )
  {
    hKey[0] = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      hKey,
      0);
    v26 = RegOpenKeyExW(phkResult, v15, 0, 0x2001Fu, hKey);
    if ( v26 )
    {
      Error = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x266,
                (unsigned int)"onecoreuap\\shell\\windows.storage\\capturedcallercontextlib\\capturedcallercontext.cpp",
                (const char *)v26,
                v30);
      if ( hKey[0] )
        RegCloseKey(hKey[0]);
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( lpSubKey )
        CoTaskMemFree((LPVOID)lpSubKey);
      v25 = Token;
      if ( Token != (HANDLE)-1LL )
        goto LABEL_33;
      goto LABEL_34;
    }
    Key = RegCreateKeyExW(hKey[0], a2, 0, 0, 0, a3, 0, a4, 0);
    if ( Key )
    {
      Error = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x267,
                (unsigned int)"onecoreuap\\shell\\windows.storage\\capturedcallercontextlib\\capturedcallercontext.cpp",
                (const char *)Key,
                v31);
      if ( hKey[0] )
        RegCloseKey(hKey[0]);
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( lpSubKey )
        CoTaskMemFree((LPVOID)lpSubKey);
      v25 = Token;
      if ( Token != (HANDLE)-1LL )
        goto LABEL_33;
      goto LABEL_34;
    }
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
  }
  else
  {
    v20 = RegOpenKeyExW(v16, v15, 0, a3, a4);
    if ( v20 )
    {
      Error = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x261,
                (unsigned int)"onecoreuap\\shell\\windows.storage\\capturedcallercontextlib\\capturedcallercontext.cpp",
                (const char *)v20,
                v29);
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( lpSubKey )
        CoTaskMemFree((LPVOID)lpSubKey);
      v25 = Token;
      if ( Token != (HANDLE)-1LL )
        goto LABEL_33;
      goto LABEL_34;
    }
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( lpSubKey )
    CoTaskMemFree((LPVOID)lpSubKey);
  if ( Token != (HANDLE)-1LL )
    wil::details::RevertImpersonateToken(Token, v21);
  if ( v11 )
    CloseState(v11);
  return 0;
}

```

## disassembly

```asm
0x1801bd540  push    rbp
0x1801bd542  push    rbx
0x1801bd543  push    rsi
0x1801bd544  push    rdi
0x1801bd545  push    r12
0x1801bd547  push    r13
0x1801bd549  push    r14
0x1801bd54b  push    r15
0x1801bd54d  mov     rbp, rsp
0x1801bd550  sub     rsp, 78h
0x1801bd554  mov     r14, r9
0x1801bd557  mov     r12d, r8d
0x1801bd55a  mov     r15, rdx
0x1801bd55d  mov     rbx, rcx
0x1801bd560  xor     r13d, r13d
0x1801bd563  mov     [r9], r13
0x1801bd566  mov     [rbp+hKey], r13
0x1801bd56a  lea     rdx, [rbp+hKey]; void **
0x1801bd56e  call    ?OpenStateHandle@CapturedCallerContext@@UEAAJPEAPEAX@Z; CapturedCallerContext::OpenStateHandle(void * *)
0x1801bd573  mov     edi, eax
0x1801bd575  test    eax, eax
0x1801bd577  js      loc_1801BD862
0x1801bd57d  mov     [rbp+arg_18], r13d
0x1801bd581  mov     [rbp+Token], 0FFFFFFFFFFFFFFFFh
0x1801bd589  lea     rdx, [rbp+Token]
0x1801bd58d  mov     rcx, [rbx+40h]; Token
0x1801bd591  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x1801bd596  mov     ebx, eax
0x1801bd598  test    eax, eax
0x1801bd59a  js      loc_1801BD87E
0x1801bd5a0  lea     r9, [rbp+arg_18]
0x1801bd5a4  xor     r8d, r8d
0x1801bd5a7  xor     edx, edx
0x1801bd5a9  mov     rbx, [rbp+hKey]
0x1801bd5ad  mov     rcx, rbx
0x1801bd5b0  call    cs:__imp_GetSystemAppDataKey
0x1801bd5b7  nop     dword ptr [rax+rax+00h]
0x1801bd5bc  test    eax, eax
0x1801bd5be  jnz     loc_1801BD82D
0x1801bd5c4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1801bd5c9  mov     edi, eax
0x1801bd5cb  cmp     eax, 8007007Ah
0x1801bd5d0  jnz     loc_1801BD832
0x1801bd5d6  mov     [rbp+lpSubKey], r13
0x1801bd5da  lea     rcx, [rbp+lpSubKey]
0x1801bd5de  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1801bd5e3  mov     r9d, [rbp+arg_18]
0x1801bd5e7  mov     qword ptr [rsp+78h+samDesired], rax
0x1801bd5ec  xor     r8d, r8d
0x1801bd5ef  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1801bd5f4  mov     edi, eax
0x1801bd5f6  test    eax, eax
0x1801bd5f8  js      loc_1801BD8C3
0x1801bd5fe  mov     [rbp+phkResult], r13
0x1801bd602  lea     r9, [rbp+arg_18]
0x1801bd606  mov     r8, [rbp+lpSubKey]
0x1801bd60a  lea     rdx, [rbp+phkResult]
0x1801bd60e  mov     rcx, rbx
0x1801bd611  call    cs:__imp_GetSystemAppDataKey
0x1801bd618  nop     dword ptr [rax+rax+00h]
0x1801bd61d  test    eax, eax
0x1801bd61f  jz      loc_1801BD755
0x1801bd625  mov     rdi, [rbp+lpSubKey]
0x1801bd629  mov     rcx, [rbp+phkResult]
0x1801bd62d  cmp     rcx, 0FFFFFFFF80000003h
0x1801bd634  jnz     loc_1801BD6C6
0x1801bd63a  call    cs:__imp_GetLastError
0x1801bd641  nop     dword ptr [rax+rax+00h]
0x1801bd646  mov     esi, eax
0x1801bd648  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1801bd64f  call    cs:__imp_RegCloseKey
0x1801bd656  nop     dword ptr [rax+rax+00h]
0x1801bd65b  mov     ecx, esi; dwErrCode
0x1801bd65d  call    cs:__imp_SetLastError
0x1801bd664  nop     dword ptr [rax+rax+00h]
0x1801bd669  mov     [rbp+phkResult], r13
0x1801bd66d  lea     rdx, [rbp+phkResult]; phkResult
0x1801bd671  mov     ecx, 2000000h; samDesired
0x1801bd676  call    cs:__imp_RegOpenCurrentUser
0x1801bd67d  nop     dword ptr [rax+rax+00h]
0x1801bd682  test    eax, eax
0x1801bd684  jnz     loc_1801BD905
0x1801bd68a  mov     eax, r13d
0x1801bd68d  mov     edx, [rbp+arg_18]
0x1801bd690  test    edx, edx
0x1801bd692  jz      short loc_1801BD6AC
0x1801bd694  movzx   ecx, word ptr [rdi]
0x1801bd697  cmp     cx, 5Ch ; '\'
0x1801bd69b  jz      short loc_1801BD6AC
0x1801bd69d  test    cx, cx
0x1801bd6a0  jz      short loc_1801BD6AC
0x1801bd6a2  inc     eax
0x1801bd6a4  add     rdi, 2
0x1801bd6a8  cmp     eax, edx
0x1801bd6aa  jb      short loc_1801BD694
0x1801bd6ac  cmp     eax, edx
0x1801bd6ae  jz      loc_1801BD7D8
0x1801bd6b4  cmp     word ptr [rdi], 5Ch ; '\'
0x1801bd6b8  jnz     loc_1801BD7D8
0x1801bd6be  add     rdi, 2
0x1801bd6c2  mov     rcx, [rbp+phkResult]; hKey
0x1801bd6c6  test    r15, r15
0x1801bd6c9  jnz     loc_180670E16
0x1801bd6cf  mov     [rsp+78h+var_58], r14; unsigned int
0x1801bd6d4  mov     r9d, r12d; samDesired
0x1801bd6d7  xor     r8d, r8d; ulOptions
0x1801bd6da  mov     rdx, rdi; lpSubKey
0x1801bd6dd  call    cs:__imp_RegOpenKeyExW
0x1801bd6e4  nop     dword ptr [rax+rax+00h]
0x1801bd6e9  test    eax, eax
0x1801bd6eb  jnz     loc_1801BD95E
0x1801bd6f1  mov     rcx, [rbp+phkResult]; hKey
0x1801bd6f5  test    rcx, rcx
0x1801bd6f8  jz      short loc_1801BD707
0x1801bd6fa  call    cs:__imp_RegCloseKey
0x1801bd701  nop     dword ptr [rax+rax+00h]
0x1801bd706  nop
0x1801bd707  mov     rcx, [rbp+lpSubKey]; pv
0x1801bd70b  test    rcx, rcx
0x1801bd70e  jz      short loc_1801BD71D
0x1801bd710  call    cs:__imp_CoTaskMemFree
0x1801bd717  nop     dword ptr [rax+rax+00h]
0x1801bd71c  nop
0x1801bd71d  mov     rcx, [rbp+Token]; Token
0x1801bd721  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801bd725  jz      short loc_1801BD72D
0x1801bd727  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x1801bd72c  nop
0x1801bd72d  test    rbx, rbx
0x1801bd730  jz      short loc_1801BD741
0x1801bd732  mov     rcx, rbx
0x1801bd735  call    cs:__imp_CloseState
0x1801bd73c  nop     dword ptr [rax+rax+00h]
0x1801bd741  xor     eax, eax
0x1801bd743  add     rsp, 78h
0x1801bd747  pop     r15
0x1801bd749  pop     r14
0x1801bd74b  pop     r13
0x1801bd74d  pop     r12
0x1801bd74f  pop     rdi
0x1801bd750  pop     rsi
0x1801bd751  pop     rbx
0x1801bd752  pop     rbp
0x1801bd753  retn
0x1801bd755  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1801bd75a  nop
0x1801bd75b  mov     edi, eax
0x1801bd75d  test    eax, eax
0x1801bd75f  jns     loc_1801BD625
0x1801bd765  mov     rcx, [rbp+40h]; this
0x1801bd769  mov     r9d, eax; char *
0x1801bd76c  lea     r8, aOnecoreuapShel_57; "onecoreuap\\shell\\windows.storage\\cap"...
0x1801bd773  mov     edx, 248h; void *
0x1801bd778  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bd77d  mov     rcx, [rbp+phkResult]; hKey
0x1801bd781  test    rcx, rcx
0x1801bd784  jz      short loc_1801BD793
0x1801bd786  call    cs:__imp_RegCloseKey
0x1801bd78d  nop     dword ptr [rax+rax+00h]
0x1801bd792  nop
0x1801bd793  mov     rcx, [rbp+lpSubKey]; pv
0x1801bd797  test    rcx, rcx
0x1801bd79a  jz      short loc_1801BD7A9
0x1801bd79c  call    cs:__imp_CoTaskMemFree
0x1801bd7a3  nop     dword ptr [rax+rax+00h]
0x1801bd7a8  nop
0x1801bd7a9  mov     rcx, [rbp+Token]; Token
0x1801bd7ad  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801bd7b1  jz      short loc_1801BD7B9
0x1801bd7b3  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x1801bd7b8  nop
0x1801bd7b9  test    rbx, rbx
0x1801bd7bc  jz      loc_1801BD877
0x1801bd7c2  mov     rcx, rbx
0x1801bd7c5  call    cs:__imp_CloseState
0x1801bd7cc  nop     dword ptr [rax+rax+00h]
0x1801bd7d1  mov     eax, edi
0x1801bd7d3  jmp     loc_1801BD743
0x1801bd7d8  mov     rcx, [rbp+40h]; this
0x1801bd7dc  mov     edi, 8000FFFFh
0x1801bd7e1  mov     r9d, edi; char *
0x1801bd7e4  lea     r8, aOnecoreuapShel_57; "onecoreuap\\shell\\windows.storage\\cap"...
0x1801bd7eb  mov     edx, 259h; void *
0x1801bd7f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bd7f5  mov     rcx, [rbp+phkResult]; hKey
0x1801bd7f9  test    rcx, rcx
0x1801bd7fc  jz      short loc_1801BD80B
0x1801bd7fe  call    cs:__imp_RegCloseKey
0x1801bd805  nop     dword ptr [rax+rax+00h]
0x1801bd80a  nop
0x1801bd80b  mov     rcx, [rbp+lpSubKey]; pv
0x1801bd80f  test    rcx, rcx
0x1801bd812  jz      short loc_1801BD821
0x1801bd814  call    cs:__imp_CoTaskMemFree
0x1801bd81b  nop     dword ptr [rax+rax+00h]
0x1801bd820  nop
0x1801bd821  mov     rcx, [rbp+Token]
0x1801bd825  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801bd829  jz      short loc_1801BD7B9
0x1801bd82b  jmp     short loc_1801BD7B3
0x1801bd82d  mov     edi, 8000FFFFh
0x1801bd832  test    edi, edi
0x1801bd834  jns     short loc_1801BD84F
0x1801bd836  mov     rcx, [rbp+40h]; this
0x1801bd83a  mov     r9d, edi; char *
0x1801bd83d  lea     r8, aOnecoreuapShel_57; "onecoreuap\\shell\\windows.storage\\cap"...
0x1801bd844  mov     edx, 241h; void *
0x1801bd849  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bd84e  nop
0x1801bd84f  mov     rcx, [rbp+Token]
0x1801bd853  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801bd857  jz      loc_1801BD7B9
0x1801bd85d  jmp     loc_1801BD7B3
0x1801bd862  mov     rcx, [rbp+hKey]
0x1801bd866  test    rcx, rcx
0x1801bd869  jz      short loc_1801BD877
0x1801bd86b  call    cs:__imp_CloseState
0x1801bd872  nop     dword ptr [rax+rax+00h]
0x1801bd877  mov     eax, edi
0x1801bd879  jmp     loc_1801BD743
0x1801bd87e  mov     rcx, [rbp+40h]; this
0x1801bd882  mov     r9d, ebx; char *
0x1801bd885  lea     r8, aOnecoreuapShel_57; "onecoreuap\\shell\\windows.storage\\cap"...
0x1801bd88c  mov     edx, 23Dh; void *
0x1801bd891  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bd896  nop
0x1801bd897  mov     rcx, [rbp+Token]; Token
0x1801bd89b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801bd89f  jz      short loc_1801BD8A7
0x1801bd8a1  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x1801bd8a6  nop
0x1801bd8a7  mov     rcx, [rbp+hKey]
0x1801bd8ab  test    rcx, rcx
0x1801bd8ae  jz      short loc_1801BD8BC
0x1801bd8b0  call    cs:__imp_CloseState
0x1801bd8b7  nop     dword ptr [rax+rax+00h]
0x1801bd8bc  mov     eax, ebx
0x1801bd8be  jmp     loc_1801BD743
0x1801bd8c3  mov     rcx, [rbp+40h]; this
0x1801bd8c7  mov     r9d, edi; char *
0x1801bd8ca  lea     r8, aOnecoreuapShel_57; "onecoreuap\\shell\\windows.storage\\cap"...
0x1801bd8d1  mov     edx, 244h; void *
0x1801bd8d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bd8db  nop
0x1801bd8dc  mov     rcx, [rbp+lpSubKey]; pv
0x1801bd8e0  test    rcx, rcx
0x1801bd8e3  jz      short loc_1801BD8F2
0x1801bd8e5  call    cs:__imp_CoTaskMemFree
0x1801bd8ec  nop     dword ptr [rax+rax+00h]
0x1801bd8f1  nop
0x1801bd8f2  mov     rcx, [rbp+Token]
0x1801bd8f6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801bd8fa  jz      loc_1801BD7B9
0x1801bd900  jmp     loc_1801BD7B3
0x1801bd905  mov     rcx, [rbp+40h]; this
0x1801bd909  mov     r9d, eax; char *
0x1801bd90c  lea     r8, aOnecoreuapShel_57; "onecoreuap\\shell\\windows.storage\\cap"...
0x1801bd913  mov     edx, 252h; void *
0x1801bd918  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801bd91d  mov     edi, eax
0x1801bd91f  mov     rcx, [rbp+phkResult]; hKey
0x1801bd923  test    rcx, rcx
0x1801bd926  jz      short loc_1801BD935
0x1801bd928  call    cs:__imp_RegCloseKey
0x1801bd92f  nop     dword ptr [rax+rax+00h]
0x1801bd934  nop
0x1801bd935  mov     rcx, [rbp+lpSubKey]; pv
0x1801bd939  test    rcx, rcx
0x1801bd93c  jz      short loc_1801BD94B
0x1801bd93e  call    cs:__imp_CoTaskMemFree
0x1801bd945  nop     dword ptr [rax+rax+00h]
0x1801bd94a  nop
0x1801bd94b  mov     rcx, [rbp+Token]
0x1801bd94f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801bd953  jz      loc_1801BD7B9
0x1801bd959  jmp     loc_1801BD7B3
0x1801bd95e  mov     rcx, [rbp+40h]; this
0x1801bd962  mov     r9d, eax; char *
0x1801bd965  lea     r8, aOnecoreuapShel_57; "onecoreuap\\shell\\windows.storage\\cap"...
0x1801bd96c  mov     edx, 261h; void *
0x1801bd971  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801bd976  mov     edi, eax
0x1801bd978  mov     rcx, [rbp+phkResult]; hKey
0x1801bd97c  test    rcx, rcx
0x1801bd97f  jz      short loc_1801BD98E
0x1801bd981  call    cs:__imp_RegCloseKey
0x1801bd988  nop     dword ptr [rax+rax+00h]
0x1801bd98d  nop
0x1801bd98e  mov     rcx, [rbp+lpSubKey]; pv
0x1801bd992  test    rcx, rcx
0x1801bd995  jz      short loc_1801BD9A4
0x1801bd997  call    cs:__imp_CoTaskMemFree
0x1801bd99e  nop     dword ptr [rax+rax+00h]
0x1801bd9a3  nop
0x1801bd9a4  mov     rcx, [rbp+Token]
0x1801bd9a8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801bd9ac  jz      loc_1801BD7B9
0x1801bd9b2  jmp     loc_1801BD7B3
0x1801bd9b7  mov     rcx, [rbp+40h]; this
0x1801bd9bb  mov     r9d, eax; char *
  ... truncated ...
```
