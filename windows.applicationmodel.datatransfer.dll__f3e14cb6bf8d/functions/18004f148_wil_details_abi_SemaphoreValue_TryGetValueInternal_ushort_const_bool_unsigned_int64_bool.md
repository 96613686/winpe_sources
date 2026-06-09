# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18004f148`
- end: `0x18004f40a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `706`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18001d998`
- `0x18001dd6c`

## callees

- `0x180002ad0`
- `0x180035198`
- `0x180048934`
- `0x180048954`
- `0x18004e9f8`
- `0x18004f148`
- `0x180052f28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18004f1df`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18004f261`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18004f1df`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18004f261`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f32e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f32e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f22c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f2a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f2b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f2cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f2f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f31f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f22c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f2a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f2b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f2cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f2f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f31f`

## string_xrefs

- `0x18004f37b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18004f394`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18004f3ad`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18004f3c6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18004f3df`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18004f3f8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned int LastError; // edi
  const char *v13; // r9
  HANDLE v15; // rax
  const char *v16; // r9
  void *v17; // rdi
  int v18; // eax
  unsigned int v19; // esi
  const char *v20; // r9
  const char *v21; // r9
  const char *v22; // r9
  const char *v23; // r9
  const char *v24; // r9
  const char *v25; // r9
  int v26; // [rsp+20h] [rbp-E0h] BYREF
  int v27[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v5 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v5;
  }
  while ( v5 );
  v8 = v4 - 1;
  if ( v5 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v25);
    return 0;
  }
  v27[0] = 0;
  v26 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v27);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v26);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v13);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v15 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v17 = v15;
  if ( !v15 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v16);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v24);
    return LastError;
  }
  v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v15, &v26);
  v19 = v18;
  if ( v18 >= 0 )
  {
    if ( !CloseHandle(v17) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v22);
    *a3 = v27[0] | (unsigned __int64)((__int64)v26 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v23);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v18, v26);
  if ( !CloseHandle(v17) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v20);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v21);
  return v19;
}

```

## disassembly

```asm
0x18004f148  push    rbp
0x18004f14a  push    rbx
0x18004f14b  push    rsi
0x18004f14c  push    rdi
0x18004f14d  push    r14
0x18004f14f  push    r15
0x18004f151  lea     rbp, [rsp-158h]
0x18004f159  sub     rsp, 258h
0x18004f160  mov     rax, cs:__security_cookie
0x18004f167  xor     rax, rsp
0x18004f16a  mov     [rbp+180h+var_40], rax
0x18004f171  xor     r15d, r15d
0x18004f174  lea     rax, [rsp+280h+Name]
0x18004f179  mov     esi, 104h
0x18004f17e  mov     [r8], r15
0x18004f181  mov     edx, esi
0x18004f183  mov     r14, r8
0x18004f186  mov     r9d, 7FFFFFFEh
0x18004f18c  test    r9, r9
0x18004f18f  jz      short loc_18004F1B0
0x18004f191  movzx   r8d, word ptr [rcx]
0x18004f195  test    r8w, r8w
0x18004f199  jz      short loc_18004F1B0
0x18004f19b  mov     [rax], r8w
0x18004f19f  add     rcx, 2
0x18004f1a3  add     rax, 2
0x18004f1a7  dec     r9
0x18004f1aa  sub     rdx, 1
0x18004f1ae  jnz     short loc_18004F18C
0x18004f1b0  test    rdx, rdx
0x18004f1b3  lea     rcx, [rax-2]
0x18004f1b7  lea     r8, aP0; "_p0"
0x18004f1be  mov     rdx, rsi; unsigned __int64
0x18004f1c1  cmovnz  rcx, rax
0x18004f1c5  mov     [rcx], r15w
0x18004f1c9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18004f1ce  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004f1d3  lea     r8, [rsp+280h+Name]; lpName
0x18004f1d8  xor     edx, edx; bInheritHandle
0x18004f1da  mov     ecx, 1F0003h; dwDesiredAccess
0x18004f1df  call    cs:__imp_OpenSemaphoreW
0x18004f1e5  mov     rbx, rax
0x18004f1e8  test    rax, rax
0x18004f1eb  jz      loc_18004F32E
0x18004f1f1  lea     rdx, [rsp+280h+var_25C]; int *
0x18004f1f6  mov     [rsp+280h+var_25C], r15d
0x18004f1fb  mov     rcx, rax; hHandle
0x18004f1fe  mov     [rsp+280h+var_260], r15d; int
0x18004f203  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18004f208  mov     edi, eax
0x18004f20a  test    eax, eax
0x18004f20c  jns     short loc_18004F241
0x18004f20e  mov     rcx, [rbp+188h]; this
0x18004f215  lea     r8, aWil; "wil"
0x18004f21c  mov     r9d, eax; char *
0x18004f21f  mov     edx, 0D6h; void *
0x18004f224  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f229  mov     rcx, rbx; hObject
0x18004f22c  call    cs:__imp_CloseHandle
0x18004f232  test    eax, eax
0x18004f234  jz      loc_18004F3BF
0x18004f23a  mov     eax, edi
0x18004f23c  jmp     loc_18004F355
0x18004f241  lea     r8, asc_180094808; "h"
0x18004f248  mov     rdx, rsi; unsigned __int64
0x18004f24b  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18004f250  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004f255  lea     r8, [rsp+280h+Name]; lpName
0x18004f25a  xor     edx, edx; bInheritHandle
0x18004f25c  mov     ecx, 1F0003h; dwDesiredAccess
0x18004f261  call    cs:__imp_OpenSemaphoreW
0x18004f267  mov     rdi, rax
0x18004f26a  test    rax, rax
0x18004f26d  jz      loc_18004F302
0x18004f273  lea     rdx, [rsp+280h+var_260]; int *
0x18004f278  mov     rcx, rax; hHandle
0x18004f27b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18004f280  mov     esi, eax
0x18004f282  test    eax, eax
0x18004f284  jns     short loc_18004F2CA
0x18004f286  mov     rcx, [rbp+188h]; this
0x18004f28d  lea     r8, aWil; "wil"
0x18004f294  mov     r9d, eax; char *
0x18004f297  mov     edx, 0DEh; void *
0x18004f29c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f2a1  mov     rcx, rdi; hObject
0x18004f2a4  call    cs:__imp_CloseHandle
0x18004f2aa  test    eax, eax
0x18004f2ac  jz      loc_18004F3D8
0x18004f2b2  mov     rcx, rbx; hObject
0x18004f2b5  call    cs:__imp_CloseHandle
0x18004f2bb  test    eax, eax
0x18004f2bd  jz      loc_18004F3F1
0x18004f2c3  mov     eax, esi
0x18004f2c5  jmp     loc_18004F355
0x18004f2ca  mov     rcx, rdi; hObject
0x18004f2cd  call    cs:__imp_CloseHandle
0x18004f2d3  test    eax, eax
0x18004f2d5  jz      loc_18004F374
0x18004f2db  movsxd  rax, [rsp+280h+var_25C]
0x18004f2e0  movsxd  rcx, [rsp+280h+var_260]
0x18004f2e5  shl     rcx, 1Fh
0x18004f2e9  or      rcx, rax
0x18004f2ec  mov     [r14], rcx
0x18004f2ef  mov     rcx, rbx; hObject
0x18004f2f2  call    cs:__imp_CloseHandle
0x18004f2f8  test    eax, eax
0x18004f2fa  jz      loc_18004F38D
0x18004f300  jmp     short loc_18004F339
0x18004f302  mov     rcx, [rbp+188h]; this
0x18004f309  lea     r8, aWil; "wil"
0x18004f310  mov     edx, 0DCh; void *
0x18004f315  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004f31a  mov     rcx, rbx; hObject
0x18004f31d  mov     edi, eax
0x18004f31f  call    cs:__imp_CloseHandle
0x18004f325  test    eax, eax
0x18004f327  jz      short loc_18004F3A6
0x18004f329  jmp     loc_18004F23A
0x18004f32e  call    cs:__imp_GetLastError
0x18004f334  cmp     eax, 2
0x18004f337  jnz     short loc_18004F33D
0x18004f339  xor     eax, eax
0x18004f33b  jmp     short loc_18004F355
0x18004f33d  mov     rcx, [rbp+188h]; this
0x18004f344  lea     r8, aWil; "wil"
0x18004f34b  mov     edx, 0D0h; void *
0x18004f350  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004f355  mov     rcx, [rbp+180h+var_40]
0x18004f35c  xor     rcx, rsp; StackCookie
0x18004f35f  call    __security_check_cookie
0x18004f364  add     rsp, 258h
0x18004f36b  pop     r15
0x18004f36d  pop     r14
0x18004f36f  pop     rdi
0x18004f370  pop     rsi
0x18004f371  pop     rbx
0x18004f372  pop     rbp
0x18004f373  retn
0x18004f374  mov     rcx, [rbp+188h]; this
0x18004f37b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004f382  mov     edx, 0A0Bh; void *
0x18004f387  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18004f38d  mov     rcx, [rbp+188h]; this
0x18004f394  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004f39b  mov     edx, 0A0Bh; void *
0x18004f3a0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18004f3a6  mov     rcx, [rbp+188h]; this
0x18004f3ad  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004f3b4  mov     edx, 0A0Bh; void *
0x18004f3b9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18004f3bf  mov     rcx, [rbp+188h]; this
0x18004f3c6  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004f3cd  mov     edx, 0A0Bh; void *
0x18004f3d2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18004f3d8  mov     rcx, [rbp+188h]; this
0x18004f3df  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004f3e6  mov     edx, 0A0Bh; void *
0x18004f3eb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18004f3f1  mov     rcx, [rbp+188h]; this
0x18004f3f8  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004f3ff  mov     edx, 0A0Bh; void *
0x18004f404  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
