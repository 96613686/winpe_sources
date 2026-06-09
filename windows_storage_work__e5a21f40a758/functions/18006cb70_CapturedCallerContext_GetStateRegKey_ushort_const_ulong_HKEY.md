# CapturedCallerContext::GetStateRegKey(ushort const *,ulong,HKEY__ * *)

- ea: `0x18006cb70`
- end: `0x18006d02f`
- name: `?GetStateRegKey@CapturedCallerContext@@UEAAJPEBGKPEAPEAUHKEY__@@@Z`
- size: `1215`
- prototype: `int(CapturedCallerContext *__hidden this, const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800432f0`
- `0x18004a030`
- `0x18006cb70`
- `0x18006d038`
- `0x18006d190`
- `0x18006dd40`
- `0x18006e168`
- `0x18009d164`
- `0x1800d13a0`
- `0x18033b5a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006cc71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006cc71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cc5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cc5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cc69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cd00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cd79`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cddc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cee8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cf35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cf82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cf91`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cfde`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cfed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d024`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cc69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cd00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cd79`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cddc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cee8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cf35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cf82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cf91`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cfde`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cfed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d024`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006cce9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1806405de`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006cce9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1806405de`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18006cc84`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18006cc84`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180640612`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180640612`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006cd10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006cd89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006cdec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ceab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006cef8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006cf45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006cfa1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006cffd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006cd10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006cd89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006cdec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ceab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006cef8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006cf45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006cfa1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006cffd`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18006cd2f`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18006cdac`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18006ce3d`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18006ce7c`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18006cd2f`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18006cdac`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18006ce3d`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18006ce7c`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18006cbe0`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18006cc3b`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18006cbe0`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18006cc3b`

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
0x18006cb70  push    rbp
0x18006cb72  push    rbx
0x18006cb73  push    rsi
0x18006cb74  push    rdi
0x18006cb75  push    r12
0x18006cb77  push    r13
0x18006cb79  push    r14
0x18006cb7b  push    r15
0x18006cb7d  mov     rbp, rsp
0x18006cb80  sub     rsp, 78h
0x18006cb84  mov     r14, r9
0x18006cb87  mov     r12d, r8d
0x18006cb8a  mov     r15, rdx
0x18006cb8d  mov     rbx, rcx
0x18006cb90  xor     r13d, r13d
0x18006cb93  mov     [r9], r13
0x18006cb96  mov     [rbp+hKey], r13
0x18006cb9a  lea     rdx, [rbp+hKey]; void **
0x18006cb9e  call    ?OpenStateHandle@CapturedCallerContext@@UEAAJPEAPEAX@Z; CapturedCallerContext::OpenStateHandle(void * *)
0x18006cba3  mov     edi, eax
0x18006cba5  test    eax, eax
0x18006cba7  js      loc_18006CE34
0x18006cbad  mov     [rbp+arg_18], r13d
0x18006cbb1  mov     [rbp+Token], 0FFFFFFFFFFFFFFFFh
0x18006cbb9  lea     rdx, [rbp+Token]
0x18006cbbd  mov     rcx, [rbx+40h]; Token
0x18006cbc1  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x18006cbc6  mov     ebx, eax
0x18006cbc8  test    eax, eax
0x18006cbca  js      loc_18006CE4A
0x18006cbd0  lea     r9, [rbp+arg_18]
0x18006cbd4  xor     r8d, r8d
0x18006cbd7  xor     edx, edx
0x18006cbd9  mov     rbx, [rbp+hKey]
0x18006cbdd  mov     rcx, rbx
0x18006cbe0  call    cs:__imp_GetSystemAppDataKey
0x18006cbe6  test    eax, eax
0x18006cbe8  jnz     loc_18006CDFF
0x18006cbee  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006cbf3  mov     edi, eax
0x18006cbf5  cmp     eax, 8007007Ah
0x18006cbfa  jnz     loc_18006CE04
0x18006cc00  mov     [rbp+lpSubKey], r13
0x18006cc04  lea     rcx, [rbp+lpSubKey]
0x18006cc08  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18006cc0d  mov     r9d, [rbp+arg_18]
0x18006cc11  mov     qword ptr [rsp+78h+samDesired], rax
0x18006cc16  xor     r8d, r8d
0x18006cc19  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18006cc1e  mov     edi, eax
0x18006cc20  test    eax, eax
0x18006cc22  js      loc_18006CE89
0x18006cc28  mov     [rbp+phkResult], r13
0x18006cc2c  lea     r9, [rbp+arg_18]
0x18006cc30  mov     r8, [rbp+lpSubKey]
0x18006cc34  lea     rdx, [rbp+phkResult]
0x18006cc38  mov     rcx, rbx
0x18006cc3b  call    cs:__imp_GetSystemAppDataKey
0x18006cc41  test    eax, eax
0x18006cc43  jz      loc_18006CD48
0x18006cc49  mov     rdi, [rbp+lpSubKey]
0x18006cc4d  mov     rcx, [rbp+phkResult]
0x18006cc51  cmp     rcx, 0FFFFFFFF80000003h
0x18006cc58  jnz     short loc_18006CCD2
0x18006cc5a  call    cs:__imp_GetLastError
0x18006cc60  mov     esi, eax
0x18006cc62  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18006cc69  call    cs:__imp_RegCloseKey
0x18006cc6f  mov     ecx, esi; dwErrCode
0x18006cc71  call    cs:__imp_SetLastError
0x18006cc77  mov     [rbp+phkResult], r13
0x18006cc7b  lea     rdx, [rbp+phkResult]; phkResult
0x18006cc7f  mov     ecx, 2000000h; samDesired
0x18006cc84  call    cs:__imp_RegOpenCurrentUser
0x18006cc8a  test    eax, eax
0x18006cc8c  jnz     loc_18006CEC5
0x18006cc92  mov     eax, r13d
0x18006cc95  mov     edx, [rbp+arg_18]
0x18006cc98  test    edx, edx
0x18006cc9a  jz      short loc_18006CCB8
0x18006cc9c  nop     dword ptr [rax+00h]
0x18006cca0  movzx   ecx, word ptr [rdi]
0x18006cca3  cmp     cx, 5Ch ; '\'
0x18006cca7  jz      short loc_18006CCB8
0x18006cca9  test    cx, cx
0x18006ccac  jz      short loc_18006CCB8
0x18006ccae  inc     eax
0x18006ccb0  add     rdi, 2
0x18006ccb4  cmp     eax, edx
0x18006ccb6  jb      short loc_18006CCA0
0x18006ccb8  cmp     eax, edx
0x18006ccba  jz      loc_18006CDB6
0x18006ccc0  cmp     word ptr [rdi], 5Ch ; '\'
0x18006ccc4  jnz     loc_18006CDB6
0x18006ccca  add     rdi, 2
0x18006ccce  mov     rcx, [rbp+phkResult]; hKey
0x18006ccd2  test    r15, r15
0x18006ccd5  jnz     loc_1806405B6
0x18006ccdb  mov     [rsp+78h+var_58], r14; unsigned int
0x18006cce0  mov     r9d, r12d; samDesired
0x18006cce3  xor     r8d, r8d; ulOptions
0x18006cce6  mov     rdx, rdi; lpSubKey
0x18006cce9  call    cs:__imp_RegOpenKeyExW
0x18006ccef  test    eax, eax
0x18006ccf1  jnz     loc_18006CF12
0x18006ccf7  mov     rcx, [rbp+phkResult]; hKey
0x18006ccfb  test    rcx, rcx
0x18006ccfe  jz      short loc_18006CD07
0x18006cd00  call    cs:__imp_RegCloseKey
0x18006cd06  nop
0x18006cd07  mov     rcx, [rbp+lpSubKey]; pv
0x18006cd0b  test    rcx, rcx
0x18006cd0e  jz      short loc_18006CD17
0x18006cd10  call    cs:__imp_CoTaskMemFree
0x18006cd16  nop
0x18006cd17  mov     rcx, [rbp+Token]; Token
0x18006cd1b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006cd1f  jz      short loc_18006CD27
0x18006cd21  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x18006cd26  nop
0x18006cd27  test    rbx, rbx
0x18006cd2a  jz      short loc_18006CD35
0x18006cd2c  mov     rcx, rbx
0x18006cd2f  call    cs:__imp_CloseState
0x18006cd35  xor     eax, eax
0x18006cd37  add     rsp, 78h
0x18006cd3b  pop     r15
0x18006cd3d  pop     r14
0x18006cd3f  pop     r13
0x18006cd41  pop     r12
0x18006cd43  pop     rdi
0x18006cd44  pop     rsi
0x18006cd45  pop     rbx
0x18006cd46  pop     rbp
0x18006cd47  retn
0x18006cd48  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006cd4d  nop
0x18006cd4e  mov     edi, eax
0x18006cd50  test    eax, eax
0x18006cd52  jns     loc_18006CC49
0x18006cd58  mov     rcx, [rbp+40h]; this
0x18006cd5c  mov     r9d, eax; char *
0x18006cd5f  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\windows.storage\\cap"...
0x18006cd66  mov     edx, 248h; void *
0x18006cd6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006cd70  mov     rcx, [rbp+phkResult]; hKey
0x18006cd74  test    rcx, rcx
0x18006cd77  jz      short loc_18006CD80
0x18006cd79  call    cs:__imp_RegCloseKey
0x18006cd7f  nop
0x18006cd80  mov     rcx, [rbp+lpSubKey]; pv
0x18006cd84  test    rcx, rcx
0x18006cd87  jz      short loc_18006CD90
0x18006cd89  call    cs:__imp_CoTaskMemFree
0x18006cd8f  nop
0x18006cd90  mov     rcx, [rbp+Token]; Token
0x18006cd94  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006cd98  jz      short loc_18006CDA0
0x18006cd9a  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x18006cd9f  nop
0x18006cda0  test    rbx, rbx
0x18006cda3  jz      loc_18006CE43
0x18006cda9  mov     rcx, rbx
0x18006cdac  call    cs:__imp_CloseState
0x18006cdb2  mov     eax, edi
0x18006cdb4  jmp     short loc_18006CD37
0x18006cdb6  mov     rcx, [rbp+40h]; this
0x18006cdba  mov     edi, 8000FFFFh
0x18006cdbf  mov     r9d, edi; char *
0x18006cdc2  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\windows.storage\\cap"...
0x18006cdc9  mov     edx, 259h; void *
0x18006cdce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006cdd3  mov     rcx, [rbp+phkResult]; hKey
0x18006cdd7  test    rcx, rcx
0x18006cdda  jz      short loc_18006CDE3
0x18006cddc  call    cs:__imp_RegCloseKey
0x18006cde2  nop
0x18006cde3  mov     rcx, [rbp+lpSubKey]; pv
0x18006cde7  test    rcx, rcx
0x18006cdea  jz      short loc_18006CDF3
0x18006cdec  call    cs:__imp_CoTaskMemFree
0x18006cdf2  nop
0x18006cdf3  mov     rcx, [rbp+Token]
0x18006cdf7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006cdfb  jz      short loc_18006CDA0
0x18006cdfd  jmp     short loc_18006CD9A
0x18006cdff  mov     edi, 8000FFFFh
0x18006ce04  test    edi, edi
0x18006ce06  jns     short loc_18006CE21
0x18006ce08  mov     rcx, [rbp+40h]; this
0x18006ce0c  mov     r9d, edi; char *
0x18006ce0f  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\windows.storage\\cap"...
0x18006ce16  mov     edx, 241h; void *
0x18006ce1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ce20  nop
0x18006ce21  mov     rcx, [rbp+Token]
0x18006ce25  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006ce29  jz      loc_18006CDA0
0x18006ce2f  jmp     loc_18006CD9A
0x18006ce34  mov     rcx, [rbp+hKey]
0x18006ce38  test    rcx, rcx
0x18006ce3b  jz      short loc_18006CE43
0x18006ce3d  call    cs:__imp_CloseState
0x18006ce43  mov     eax, edi
0x18006ce45  jmp     loc_18006CD37
0x18006ce4a  mov     rcx, [rbp+40h]; this
0x18006ce4e  mov     r9d, ebx; char *
0x18006ce51  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\windows.storage\\cap"...
0x18006ce58  mov     edx, 23Dh; void *
0x18006ce5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ce62  nop
0x18006ce63  mov     rcx, [rbp+Token]; Token
0x18006ce67  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006ce6b  jz      short loc_18006CE73
0x18006ce6d  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x18006ce72  nop
0x18006ce73  mov     rcx, [rbp+hKey]
0x18006ce77  test    rcx, rcx
0x18006ce7a  jz      short loc_18006CE82
0x18006ce7c  call    cs:__imp_CloseState
0x18006ce82  mov     eax, ebx
0x18006ce84  jmp     loc_18006CD37
0x18006ce89  mov     rcx, [rbp+40h]; this
0x18006ce8d  mov     r9d, edi; char *
0x18006ce90  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\windows.storage\\cap"...
0x18006ce97  mov     edx, 244h; void *
0x18006ce9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006cea1  nop
0x18006cea2  mov     rcx, [rbp+lpSubKey]; pv
0x18006cea6  test    rcx, rcx
0x18006cea9  jz      short loc_18006CEB2
0x18006ceab  call    cs:__imp_CoTaskMemFree
0x18006ceb1  nop
0x18006ceb2  mov     rcx, [rbp+Token]
0x18006ceb6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006ceba  jz      loc_18006CDA0
0x18006cec0  jmp     loc_18006CD9A
0x18006cec5  mov     rcx, [rbp+40h]; this
0x18006cec9  mov     r9d, eax; char *
0x18006cecc  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\windows.storage\\cap"...
0x18006ced3  mov     edx, 252h; void *
0x18006ced8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006cedd  mov     edi, eax
0x18006cedf  mov     rcx, [rbp+phkResult]; hKey
0x18006cee3  test    rcx, rcx
0x18006cee6  jz      short loc_18006CEEF
0x18006cee8  call    cs:__imp_RegCloseKey
0x18006ceee  nop
0x18006ceef  mov     rcx, [rbp+lpSubKey]; pv
0x18006cef3  test    rcx, rcx
0x18006cef6  jz      short loc_18006CEFF
0x18006cef8  call    cs:__imp_CoTaskMemFree
0x18006cefe  nop
0x18006ceff  mov     rcx, [rbp+Token]
0x18006cf03  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006cf07  jz      loc_18006CDA0
0x18006cf0d  jmp     loc_18006CD9A
0x18006cf12  mov     rcx, [rbp+40h]; this
0x18006cf16  mov     r9d, eax; char *
0x18006cf19  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\windows.storage\\cap"...
0x18006cf20  mov     edx, 261h; void *
0x18006cf25  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006cf2a  mov     edi, eax
0x18006cf2c  mov     rcx, [rbp+phkResult]; hKey
0x18006cf30  test    rcx, rcx
0x18006cf33  jz      short loc_18006CF3C
0x18006cf35  call    cs:__imp_RegCloseKey
0x18006cf3b  nop
0x18006cf3c  mov     rcx, [rbp+lpSubKey]; pv
0x18006cf40  test    rcx, rcx
0x18006cf43  jz      short loc_18006CF4C
0x18006cf45  call    cs:__imp_CoTaskMemFree
0x18006cf4b  nop
0x18006cf4c  mov     rcx, [rbp+Token]
0x18006cf50  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006cf54  jz      loc_18006CDA0
0x18006cf5a  jmp     loc_18006CD9A
0x18006cf5f  mov     rcx, [rbp+40h]; this
0x18006cf63  mov     r9d, eax; char *
0x18006cf66  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\windows.storage\\cap"...
0x18006cf6d  mov     edx, 266h; void *
0x18006cf72  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006cf77  mov     edi, eax
0x18006cf79  mov     rcx, [rbp+hKey]; hKey
0x18006cf7d  test    rcx, rcx
0x18006cf80  jz      short loc_18006CF88
0x18006cf82  call    cs:__imp_RegCloseKey
0x18006cf88  mov     rcx, [rbp+phkResult]; hKey
0x18006cf8c  test    rcx, rcx
0x18006cf8f  jz      short loc_18006CF98
0x18006cf91  call    cs:__imp_RegCloseKey
0x18006cf97  nop
0x18006cf98  mov     rcx, [rbp+lpSubKey]; pv
0x18006cf9c  test    rcx, rcx
0x18006cf9f  jz      short loc_18006CFA8
0x18006cfa1  call    cs:__imp_CoTaskMemFree
0x18006cfa7  nop
0x18006cfa8  mov     rcx, [rbp+Token]
0x18006cfac  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006cfb0  jz      loc_18006CDA0
  ... truncated ...
```
