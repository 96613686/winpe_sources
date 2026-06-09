# Windows::Internal::Security::Authentication::TokenBroker::GetCallingProcessImageName(IUnknown *,HSTRING__ * *)

- ea: `0x18000b070`
- end: `0x18000b538`
- name: `?GetCallingProcessImageName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEAPEAUHSTRING__@@@Z`
- size: `1224`
- prototype: `__int64 __fastcall(Windows::Internal::Security::Authentication::TokenBroker *__hidden this, struct IUnknown *, HSTRING *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000d2b0`
- `0x1800afd50`

## callees

- `0x18000b070`
- `0x18000bd40`
- `0x18000d250`
- `0x180041050`
- `0x1800565a0`
- `0x18007c220`
- `0x18008e690`
- `0x18008f234`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b157`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b157`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b4f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b4f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b250`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b459`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b250`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b459`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000b23d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000b23d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b261`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b327`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b261`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b327`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3fc`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000b506`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000b506`
- `combase!__imp_CoGetCallContextOfObject` at `0x18000b139`
- `combase!__imp_CoGetCallContextOfObject` at `0x18000b139`
- `combase!__imp_CoGetCallLocality` at `0x18000b0c3`
- `combase!__imp_CoGetCallLocality` at `0x18000b105`
- `combase!__imp_CoGetCallLocality` at `0x18000b0c3`
- `combase!__imp_CoGetCallLocality` at `0x18000b105`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18000b1c8`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18000b1c8`

## string_xrefs

- `0x18000b213`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18000b30c`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18000b337`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18000b35a`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18000b375`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18000b397`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18000b3b2`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18000b3dd`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18000b414`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18000b439`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18000b4ab`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::GetCallingProcessImageName(
        Windows::Internal::Security::Authentication::TokenBroker *this,
        struct IUnknown *a2,
        HSTRING *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  unsigned int LastError; // ebx
  int v9; // eax
  __int64 v10; // r9
  HANDLE CurrentProcess; // rbx
  HANDLE v12; // rdi
  const char *v13; // r9
  unsigned __int64 v14; // rdx
  struct IUnknownVtbl *v15; // rbx
  __int64 (__fastcall *v17)(__int64, __int64, HANDLE *); // rbx
  int v18; // eax
  HANDLE v19; // rcx
  int v20; // eax
  DWORD CurrentProcessId; // eax
  HANDLE v22; // rax
  int v23[2]; // [rsp+20h] [rbp-E0h] BYREF
  HANDLE hProcess; // [rsp+28h] [rbp-D8h] BYREF
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  DWORD dwSize; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v27; // [rsp+40h] [rbp-C0h]
  WCHAR ExeName[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  if ( !this )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x797,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)0x80070057LL,
      v23[0]);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x798,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)0x80070057LL,
      v23[0]);
    return 2147942487LL;
  }
  v23[0] = 1;
  v5 = CoGetCallLocality(this, v23);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x748,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)(unsigned int)v5,
      v23[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x79B,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)v6,
      v23[0]);
    return v6;
  }
  string = 0;
  if ( v23[0] == 2 )
  {
    v20 = Windows::Internal::String::Initialize((Windows::Internal::String *)&string, L"VAIL_CALLER_IMAGE", 0x11u);
    LastError = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A0,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
        (const char *)(unsigned int)v20,
        v23[0]);
      if ( !string )
        return LastError;
      WindowsDeleteString(string);
      return LastError;
    }
    else
    {
      a2->lpVtbl = (struct IUnknownVtbl *)string;
      return 0;
    }
  }
  v27 = 0;
  hProcess = 0;
  v23[0] = 1;
  v7 = CoGetCallLocality(this, v23);
  LastError = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x748,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)(unsigned int)v7,
      v23[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x84C,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)LastError,
      v23[0]);
    v19 = hProcess;
    if ( !hProcess )
      goto LABEL_35;
    goto LABEL_34;
  }
  if ( v23[0] != 2 )
  {
    *(_QWORD *)v23 = 0;
    v9 = CoGetCallContextOfObject(this, &GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, v23);
    LastError = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C1,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
        (const char *)(unsigned int)v9,
        v23[0]);
      if ( *(_QWORD *)v23 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v23 + 16LL))(*(_QWORD *)v23);
    }
    else
    {
      v10 = *(_QWORD *)v23;
      if ( !*(_QWORD *)v23 )
      {
        CurrentProcess = GetCurrentProcess();
        if ( hProcess )
          wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(hProcess);
        hProcess = CurrentProcess;
LABEL_12:
        if ( *(_QWORD *)v23 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v23 + 16LL))(*(_QWORD *)v23);
        LastError = 0;
        goto LABEL_15;
      }
      v17 = *(__int64 (__fastcall **)(__int64, __int64, HANDLE *))(**(_QWORD **)v23 + 24LL);
      if ( hProcess )
      {
        wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(hProcess);
        v10 = *(_QWORD *)v23;
      }
      hProcess = 0;
      v18 = v17(v10, 4096, &hProcess);
      LastError = v18;
      if ( v18 >= 0 )
        goto LABEL_12;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C4,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
        (const char *)(unsigned int)v18,
        v23[0]);
      if ( *(_QWORD *)v23 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v23 + 16LL))(*(_QWORD *)v23);
    }
LABEL_15:
    if ( (LastError & 0x80000000) == 0 )
      goto LABEL_16;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x85B,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)LastError,
      v23[0]);
    v19 = hProcess;
    if ( !hProcess )
    {
LABEL_35:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A9,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
        (const char *)LastError,
        v23[0]);
      return LastError;
    }
LABEL_34:
    CloseHandle(v19);
    goto LABEL_35;
  }
  CurrentProcessId = GetCurrentProcessId();
  v22 = OpenProcess(0x101000u, 0, CurrentProcessId);
  wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hProcess,
    v22);
LABEL_16:
  v12 = hProcess;
  v27 = hProcess;
  memset_0(ExeName, 0, 0x208u);
  dwSize = 260;
  if ( !QueryFullProcessImageNameW(v12, 0, ExeName, &dwSize) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x7B1,
                  (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
                  v13);
    if ( v12 )
LABEL_41:
      CloseHandle(v12);
    return LastError;
  }
  string = 0;
  v14 = -1;
  do
    ++v14;
  while ( ExeName[v14] );
  if ( v14 > 0xFFFFFFFF )
  {
    LastError = -2147024362;
    goto LABEL_21;
  }
  LastError = WindowsCreateString(ExeName, v14, &string);
  if ( (LastError & 0x80000000) != 0 )
  {
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7B3,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)LastError,
      v23[0]);
    if ( !v12 )
      return LastError;
    goto LABEL_41;
  }
  v15 = (struct IUnknownVtbl *)string;
  WindowsDeleteString(0);
  a2->lpVtbl = v15;
  if ( v12 )
    CloseHandle(v12);
  return 0;
}

```

## disassembly

```asm
0x18000b070  mov     [rsp-8+arg_10], rbx
0x18000b075  mov     [rsp-8+arg_18], rsi
0x18000b07a  push    rbp
0x18000b07b  push    rdi
0x18000b07c  push    r14
0x18000b07e  lea     rbp, [rsp-170h]
0x18000b086  sub     rsp, 270h
0x18000b08d  mov     rax, cs:__security_cookie
0x18000b094  xor     rax, rsp
0x18000b097  mov     [rbp+180h+var_20], rax
0x18000b09e  mov     rsi, rdx
0x18000b0a1  mov     rdi, rcx
0x18000b0a4  test    rcx, rcx
0x18000b0a7  jz      loc_18000B407
0x18000b0ad  test    rdx, rdx
0x18000b0b0  jz      loc_18000B49E
0x18000b0b6  mov     [rsp+280h+var_260], 1; int
0x18000b0be  lea     rdx, [rsp+280h+var_260]
0x18000b0c3  call    cs:__imp_CoGetCallLocality
0x18000b0c9  mov     ebx, eax
0x18000b0cb  test    eax, eax
0x18000b0cd  js      loc_18000B350
0x18000b0d3  cmp     [rsp+280h+var_260], 2
0x18000b0d8  setz    al
0x18000b0db  xor     r14d, r14d
0x18000b0de  mov     [rsp+280h+string], r14
0x18000b0e3  test    al, al
0x18000b0e5  jnz     loc_18000B4C6
0x18000b0eb  mov     [rsp+280h+var_240], r14
0x18000b0f0  mov     [rsp+280h+hProcess], r14
0x18000b0f5  mov     [rsp+280h+var_260], 1; int
0x18000b0fd  lea     rdx, [rsp+280h+var_260]
0x18000b102  mov     rcx, rdi
0x18000b105  call    cs:__imp_CoGetCallLocality
0x18000b10b  mov     ebx, eax
0x18000b10d  test    eax, eax
0x18000b10f  js      loc_18000B38D
0x18000b115  cmp     [rsp+280h+var_260], 2
0x18000b11a  setz    al
0x18000b11d  test    al, al
0x18000b11f  jnz     loc_18000B4F6
0x18000b125  mov     qword ptr [rsp+280h+var_260], r14; int
0x18000b12a  lea     r8, [rsp+280h+var_260]
0x18000b12f  lea     rdx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541
0x18000b136  mov     rcx, rdi
0x18000b139  call    cs:__imp_CoGetCallContextOfObject
0x18000b13f  mov     ebx, eax
0x18000b141  test    eax, eax
0x18000b143  js      loc_18000B466
0x18000b149  mov     r9, qword ptr [rsp+280h+var_260]
0x18000b14e  test    r9, r9
0x18000b151  jnz     loc_18000B291
0x18000b157  call    cs:__imp_GetCurrentProcess
0x18000b15d  mov     rbx, rax
0x18000b160  mov     rcx, [rsp+280h+hProcess]; hObject
0x18000b165  test    rcx, rcx
0x18000b168  jnz     loc_18000B52D
0x18000b16e  mov     [rsp+280h+hProcess], rbx
0x18000b173  mov     rcx, qword ptr [rsp+280h+var_260]
0x18000b178  test    rcx, rcx
0x18000b17b  jz      short loc_18000B18A
0x18000b17d  mov     rax, [rcx]
0x18000b180  mov     rax, [rax+10h]
0x18000b184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b189  nop
0x18000b18a  mov     ebx, r14d
0x18000b18d  test    ebx, ebx
0x18000b18f  js      loc_18000B302
0x18000b195  mov     rdi, [rsp+280h+hProcess]
0x18000b19a  mov     [rsp+280h+var_240], rdi
0x18000b19f  xor     edx, edx; Val
0x18000b1a1  mov     r8d, 208h; Size
0x18000b1a7  lea     rcx, [rsp+280h+ExeName]; void *
0x18000b1ac  call    memset_0
0x18000b1b1  mov     [rsp+280h+dwSize], 104h
0x18000b1b9  lea     r9, [rsp+280h+dwSize]; lpdwSize
0x18000b1be  lea     r8, [rsp+280h+ExeName]; lpExeName
0x18000b1c3  xor     edx, edx; dwFlags
0x18000b1c5  mov     rcx, rdi; hProcess
0x18000b1c8  call    cs:__imp_QueryFullProcessImageNameW
0x18000b1ce  test    eax, eax
0x18000b1d0  jz      loc_18000B3D6
0x18000b1d6  mov     [rsp+280h+string], r14
0x18000b1db  lea     rax, [rsp+280h+ExeName]
0x18000b1e0  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18000b1e7  nop     word ptr [rax+rax+00000000h]
0x18000b1f0  inc     rdx; length
0x18000b1f3  cmp     word ptr [rax+rdx*2], 0
0x18000b1f8  jnz     short loc_18000B1F0
0x18000b1fa  mov     eax, 0FFFFFFFFh
0x18000b1ff  cmp     rdx, rax
0x18000b202  jbe     short loc_18000B233
0x18000b204  mov     ebx, 80070216h
0x18000b209  mov     rcx, [rbp+188h]; this
0x18000b210  mov     r9d, ebx; char *
0x18000b213  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000b21a  mov     edx, 7B3h; void *
0x18000b21f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b224  nop
0x18000b225  test    rdi, rdi
0x18000b228  jnz     loc_18000B3F9
0x18000b22e  jmp     loc_18000B349
0x18000b233  lea     r8, [rsp+280h+string]; string
0x18000b238  lea     rcx, [rsp+280h+ExeName]; sourceString
0x18000b23d  call    cs:__imp_WindowsCreateString
0x18000b243  mov     ebx, eax
0x18000b245  test    eax, eax
0x18000b247  js      short loc_18000B209
0x18000b249  mov     rbx, [rsp+280h+string]
0x18000b24e  xor     ecx, ecx; string
0x18000b250  call    cs:__imp_WindowsDeleteString
0x18000b256  mov     [rsi], rbx
0x18000b259  test    rdi, rdi
0x18000b25c  jz      short loc_18000B268
0x18000b25e  mov     rcx, rdi; hObject
0x18000b261  call    cs:__imp_CloseHandle
0x18000b267  nop
0x18000b268  xor     eax, eax
0x18000b26a  mov     rcx, [rbp+180h+var_20]
0x18000b271  xor     rcx, rsp; StackCookie
0x18000b274  call    __security_check_cookie
0x18000b279  lea     r11, [rsp+280h+var_10]
0x18000b281  mov     rbx, [r11+30h]
0x18000b285  mov     rsi, [r11+38h]
0x18000b289  mov     rsp, r11
0x18000b28c  pop     r14
0x18000b28e  pop     rdi
0x18000b28f  pop     rbp
0x18000b290  retn
0x18000b291  mov     rax, [r9]
0x18000b294  mov     rbx, [rax+18h]
0x18000b298  mov     rcx, [rsp+280h+hProcess]; hObject
0x18000b29d  test    rcx, rcx
0x18000b2a0  jnz     loc_18000B51E
0x18000b2a6  mov     [rsp+280h+hProcess], r14
0x18000b2ab  lea     r8, [rsp+280h+hProcess]
0x18000b2b0  mov     edx, 1000h
0x18000b2b5  mov     rcx, r9
0x18000b2b8  mov     rax, rbx
0x18000b2bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2c0  mov     ebx, eax
0x18000b2c2  test    eax, eax
0x18000b2c4  jns     loc_18000B173
0x18000b2ca  mov     rcx, [rbp+188h]; this
0x18000b2d1  mov     r9d, eax; char *
0x18000b2d4  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18000b2db  mov     edx, 1C4h; void *
0x18000b2e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b2e5  nop
0x18000b2e6  mov     rcx, qword ptr [rsp+280h+var_260]
0x18000b2eb  test    rcx, rcx
0x18000b2ee  jz      short loc_18000B2FD
0x18000b2f0  mov     rax, [rcx]
0x18000b2f3  mov     rax, [rax+10h]
0x18000b2f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2fc  nop
0x18000b2fd  jmp     loc_18000B18D
0x18000b302  mov     rcx, [rbp+188h]; this
0x18000b309  mov     r9d, ebx; char *
0x18000b30c  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000b313  mov     edx, 85Bh; void *
0x18000b318  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b31d  mov     rcx, [rsp+280h+hProcess]; hObject
0x18000b322  test    rcx, rcx
0x18000b325  jz      short loc_18000B32D
0x18000b327  call    cs:__imp_CloseHandle
0x18000b32d  mov     rcx, [rbp+188h]; this
0x18000b334  mov     r9d, ebx; char *
0x18000b337  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000b33e  mov     edx, 7A9h; void *
0x18000b343  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b348  nop
0x18000b349  mov     eax, ebx
0x18000b34b  jmp     loc_18000B26A
0x18000b350  mov     rcx, [rbp+188h]; this
0x18000b357  mov     r9d, ebx; char *
0x18000b35a  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000b361  mov     edx, 748h; void *
0x18000b366  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b36b  mov     rcx, [rbp+188h]; this
0x18000b372  mov     r9d, ebx; char *
0x18000b375  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000b37c  mov     edx, 79Bh; void *
0x18000b381  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b386  mov     eax, ebx
0x18000b388  jmp     loc_18000B26A
0x18000b38d  mov     rcx, [rbp+188h]; this
0x18000b394  mov     r9d, ebx; char *
0x18000b397  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000b39e  mov     edx, 748h; void *
0x18000b3a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b3a8  mov     rcx, [rbp+188h]; this
0x18000b3af  mov     r9d, ebx; char *
0x18000b3b2  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000b3b9  mov     edx, 84Ch; void *
0x18000b3be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b3c3  mov     rcx, [rsp+280h+hProcess]
0x18000b3c8  test    rcx, rcx
0x18000b3cb  jz      loc_18000B32D
0x18000b3d1  jmp     loc_18000B327
0x18000b3d6  mov     rcx, [rbp+188h]; this
0x18000b3dd  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000b3e4  mov     edx, 7B1h; void *
0x18000b3e9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b3ee  mov     ebx, eax
0x18000b3f0  test    rdi, rdi
0x18000b3f3  jz      loc_18000B349
0x18000b3f9  mov     rcx, rdi; hObject
0x18000b3fc  call    cs:__imp_CloseHandle
0x18000b402  jmp     loc_18000B349
0x18000b407  mov     rcx, [rbp+188h]; this
0x18000b40e  mov     r9d, 80070057h; char *
0x18000b414  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000b41b  mov     edx, 797h; void *
0x18000b420  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b425  mov     eax, 80070057h
0x18000b42a  jmp     loc_18000B26A
0x18000b42f  mov     rcx, [rbp+188h]; this
0x18000b436  mov     r9d, ebx; char *
0x18000b439  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000b440  mov     edx, 7A0h; void *
0x18000b445  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b44a  nop
0x18000b44b  mov     rcx, [rsp+280h+string]; string
0x18000b450  test    rcx, rcx
0x18000b453  jz      loc_18000B349
0x18000b459  call    cs:__imp_WindowsDeleteString
0x18000b45f  mov     eax, ebx
0x18000b461  jmp     loc_18000B26A
0x18000b466  mov     rcx, [rbp+188h]; this
0x18000b46d  mov     r9d, eax; char *
0x18000b470  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18000b477  mov     edx, 1C1h; void *
0x18000b47c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b481  nop
0x18000b482  mov     rcx, qword ptr [rsp+280h+var_260]
0x18000b487  test    rcx, rcx
0x18000b48a  jz      short loc_18000B499
0x18000b48c  mov     rax, [rcx]
0x18000b48f  mov     rax, [rax+10h]
0x18000b493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b498  nop
0x18000b499  jmp     loc_18000B18D
0x18000b49e  mov     rcx, [rbp+188h]; this
0x18000b4a5  mov     r9d, 80070057h; char *
0x18000b4ab  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000b4b2  mov     edx, 798h; void *
0x18000b4b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b4bc  mov     eax, 80070057h
0x18000b4c1  jmp     loc_18000B26A
0x18000b4c6  mov     r8d, 11h; unsigned int
0x18000b4cc  lea     rdx, aVailCallerImag; "VAIL_CALLER_IMAGE"
0x18000b4d3  lea     rcx, [rsp+280h+string]; this
0x18000b4d8  call    ?Initialize@String@Internal@Windows@@QEAAJPEBGI@Z; Windows::Internal::String::Initialize(ushort const *,uint)
0x18000b4dd  mov     ebx, eax
0x18000b4df  test    eax, eax
0x18000b4e1  js      loc_18000B42F
0x18000b4e7  mov     rax, [rsp+280h+string]
0x18000b4ec  mov     [rsi], rax
0x18000b4ef  xor     eax, eax
0x18000b4f1  jmp     loc_18000B26A
0x18000b4f6  call    cs:__imp_GetCurrentProcessId
0x18000b4fc  mov     r8d, eax; dwProcessId
0x18000b4ff  xor     edx, edx; bInheritHandle
0x18000b501  mov     ecx, 101000h; dwDesiredAccess
0x18000b506  call    cs:__imp_OpenProcess
0x18000b50c  mov     rdx, rax
0x18000b50f  lea     rcx, [rsp+280h+hProcess]
0x18000b514  call    ?reset@?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000b519  jmp     loc_18000B195
0x18000b51e  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18000b523  mov     r9, qword ptr [rsp+280h+var_260]
0x18000b528  jmp     loc_18000B2A6
0x18000b52d  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18000b532  jmp     loc_18000B16E
```
