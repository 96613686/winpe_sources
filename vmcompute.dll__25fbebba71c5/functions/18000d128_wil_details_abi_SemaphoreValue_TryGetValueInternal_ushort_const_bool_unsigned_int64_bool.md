# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000d128`
- end: `0x18000d425`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `765`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000704c`
- `0x180007474`

## callees

- `0x180002f50`
- `0x180009e58`
- `0x18000c274`
- `0x18000c294`
- `0x18000cb6c`
- `0x18000d128`
- `0x18000e648`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d1bf`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d24d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d1bf`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d24d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d342`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d342`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d212`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d296`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d2ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d2cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d2f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d329`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d212`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d296`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d2ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d2cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d2f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d329`

## string_xrefs

- `0x18000d396`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000d3af`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000d3c8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000d3e1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000d3fa`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000d413`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000d128  push    rbp
0x18000d12a  push    rbx
0x18000d12b  push    rsi
0x18000d12c  push    rdi
0x18000d12d  push    r14
0x18000d12f  push    r15
0x18000d131  lea     rbp, [rsp-158h]
0x18000d139  sub     rsp, 258h
0x18000d140  mov     rax, cs:__security_cookie
0x18000d147  xor     rax, rsp
0x18000d14a  mov     [rbp+180h+var_40], rax
0x18000d151  xor     r15d, r15d
0x18000d154  lea     rax, [rsp+280h+Name]
0x18000d159  mov     esi, 104h
0x18000d15e  mov     [r8], r15
0x18000d161  mov     edx, esi
0x18000d163  mov     r14, r8
0x18000d166  mov     r9d, 7FFFFFFEh
0x18000d16c  test    r9, r9
0x18000d16f  jz      short loc_18000D190
0x18000d171  movzx   r8d, word ptr [rcx]
0x18000d175  test    r8w, r8w
0x18000d179  jz      short loc_18000D190
0x18000d17b  mov     [rax], r8w
0x18000d17f  add     rcx, 2
0x18000d183  add     rax, 2
0x18000d187  dec     r9
0x18000d18a  sub     rdx, 1
0x18000d18e  jnz     short loc_18000D16C
0x18000d190  test    rdx, rdx
0x18000d193  lea     rcx, [rax-2]
0x18000d197  lea     r8, aP0; "_p0"
0x18000d19e  mov     rdx, rsi; unsigned __int64
0x18000d1a1  cmovnz  rcx, rax
0x18000d1a5  mov     [rcx], r15w
0x18000d1a9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000d1ae  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d1b3  lea     r8, [rsp+280h+Name]; lpName
0x18000d1b8  xor     edx, edx; bInheritHandle
0x18000d1ba  mov     ecx, 1F0003h; dwDesiredAccess
0x18000d1bf  call    cs:__imp_OpenSemaphoreW
0x18000d1c6  nop     dword ptr [rax+rax+00h]
0x18000d1cb  mov     rbx, rax
0x18000d1ce  test    rax, rax
0x18000d1d1  jz      loc_18000D342
0x18000d1d7  lea     rdx, [rsp+280h+var_25C]; int *
0x18000d1dc  mov     [rsp+280h+var_25C], r15d
0x18000d1e1  mov     rcx, rax; hHandle
0x18000d1e4  mov     [rsp+280h+var_260], r15d; int
0x18000d1e9  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000d1ee  mov     edi, eax
0x18000d1f0  test    eax, eax
0x18000d1f2  jns     short loc_18000D22D
0x18000d1f4  mov     rcx, [rbp+188h]; this
0x18000d1fb  lea     r8, aWil; "wil"
0x18000d202  mov     r9d, eax; char *
0x18000d205  mov     edx, 0D6h; void *
0x18000d20a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d20f  mov     rcx, rbx; hObject
0x18000d212  call    cs:__imp_CloseHandle
0x18000d219  nop     dword ptr [rax+rax+00h]
0x18000d21e  test    eax, eax
0x18000d220  jz      loc_18000D3DA
0x18000d226  mov     eax, edi
0x18000d228  jmp     loc_18000D36F
0x18000d22d  lea     r8, asc_18008E420; "h"
0x18000d234  mov     rdx, rsi; unsigned __int64
0x18000d237  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000d23c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d241  lea     r8, [rsp+280h+Name]; lpName
0x18000d246  xor     edx, edx; bInheritHandle
0x18000d248  mov     ecx, 1F0003h; dwDesiredAccess
0x18000d24d  call    cs:__imp_OpenSemaphoreW
0x18000d254  nop     dword ptr [rax+rax+00h]
0x18000d259  mov     rdi, rax
0x18000d25c  test    rax, rax
0x18000d25f  jz      loc_18000D30C
0x18000d265  lea     rdx, [rsp+280h+var_260]; int *
0x18000d26a  mov     rcx, rax; hHandle
0x18000d26d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000d272  mov     esi, eax
0x18000d274  test    eax, eax
0x18000d276  jns     short loc_18000D2C8
0x18000d278  mov     rcx, [rbp+188h]; this
0x18000d27f  lea     r8, aWil; "wil"
0x18000d286  mov     r9d, eax; char *
0x18000d289  mov     edx, 0DEh; void *
0x18000d28e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d293  mov     rcx, rdi; hObject
0x18000d296  call    cs:__imp_CloseHandle
0x18000d29d  nop     dword ptr [rax+rax+00h]
0x18000d2a2  test    eax, eax
0x18000d2a4  jz      loc_18000D3F3
0x18000d2aa  mov     rcx, rbx; hObject
0x18000d2ad  call    cs:__imp_CloseHandle
0x18000d2b4  nop     dword ptr [rax+rax+00h]
0x18000d2b9  test    eax, eax
0x18000d2bb  jz      loc_18000D40C
0x18000d2c1  mov     eax, esi
0x18000d2c3  jmp     loc_18000D36F
0x18000d2c8  mov     rcx, rdi; hObject
0x18000d2cb  call    cs:__imp_CloseHandle
0x18000d2d2  nop     dword ptr [rax+rax+00h]
0x18000d2d7  test    eax, eax
0x18000d2d9  jz      loc_18000D38F
0x18000d2df  movsxd  rax, [rsp+280h+var_25C]
0x18000d2e4  movsxd  rcx, [rsp+280h+var_260]
0x18000d2e9  shl     rcx, 1Fh
0x18000d2ed  or      rcx, rax
0x18000d2f0  mov     [r14], rcx
0x18000d2f3  mov     rcx, rbx; hObject
0x18000d2f6  call    cs:__imp_CloseHandle
0x18000d2fd  nop     dword ptr [rax+rax+00h]
0x18000d302  test    eax, eax
0x18000d304  jz      loc_18000D3A8
0x18000d30a  jmp     short loc_18000D353
0x18000d30c  mov     rcx, [rbp+188h]; this
0x18000d313  lea     r8, aWil; "wil"
0x18000d31a  mov     edx, 0DCh; void *
0x18000d31f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000d324  mov     rcx, rbx; hObject
0x18000d327  mov     edi, eax
0x18000d329  call    cs:__imp_CloseHandle
0x18000d330  nop     dword ptr [rax+rax+00h]
0x18000d335  test    eax, eax
0x18000d337  jz      loc_18000D3C1
0x18000d33d  jmp     loc_18000D226
0x18000d342  call    cs:__imp_GetLastError
0x18000d349  nop     dword ptr [rax+rax+00h]
0x18000d34e  cmp     eax, 2
0x18000d351  jnz     short loc_18000D357
0x18000d353  xor     eax, eax
0x18000d355  jmp     short loc_18000D36F
0x18000d357  mov     rcx, [rbp+188h]; this
0x18000d35e  lea     r8, aWil; "wil"
0x18000d365  mov     edx, 0D0h; void *
0x18000d36a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000d36f  mov     rcx, [rbp+180h+var_40]
0x18000d376  xor     rcx, rsp; StackCookie
0x18000d379  call    __security_check_cookie
0x18000d37e  add     rsp, 258h
0x18000d385  pop     r15
0x18000d387  pop     r14
0x18000d389  pop     rdi
0x18000d38a  pop     rsi
0x18000d38b  pop     rbx
0x18000d38c  pop     rbp
0x18000d38d  retn
0x18000d38f  mov     rcx, [rbp+188h]; this
0x18000d396  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d39d  mov     edx, 0A0Bh; void *
0x18000d3a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d3a8  mov     rcx, [rbp+188h]; this
0x18000d3af  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d3b6  mov     edx, 0A0Bh; void *
0x18000d3bb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d3c1  mov     rcx, [rbp+188h]; this
0x18000d3c8  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d3cf  mov     edx, 0A0Bh; void *
0x18000d3d4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d3da  mov     rcx, [rbp+188h]; this
0x18000d3e1  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d3e8  mov     edx, 0A0Bh; void *
0x18000d3ed  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d3f3  mov     rcx, [rbp+188h]; this
0x18000d3fa  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d401  mov     edx, 0A0Bh; void *
0x18000d406  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d40c  mov     rcx, [rbp+188h]; this
0x18000d413  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d41a  mov     edx, 0A0Bh; void *
0x18000d41f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
