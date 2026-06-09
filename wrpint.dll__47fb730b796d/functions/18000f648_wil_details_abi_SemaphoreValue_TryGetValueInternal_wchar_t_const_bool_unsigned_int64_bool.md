# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000f648`
- end: `0x18000f8cb`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `643`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000b794`
- `0x18000bb64`

## callees

- `0x18000d140`
- `0x18000ed54`
- `0x18000ed74`
- `0x18000f1ac`
- `0x18000f648`
- `0x18000ff1c`
- `0x18001b7b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f820`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f820`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f72c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f7a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f7b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f7ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f7ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f811`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f72c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f7a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f7b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f7ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f7ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f811`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f6df`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f761`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f6df`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f761`

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
  __int64 v13; // r8
  const char *v14; // r9
  HANDLE v16; // rax
  unsigned int v17; // r8d
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  __int64 v22; // r8
  const char *v23; // r9
  __int64 v24; // r8
  const char *v25; // r9
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  __int64 v30; // r8
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h] BYREF
  int v35[3]; // [rsp+24h] [rbp-DCh] BYREF
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
  StringCchCatW(Name, 260, (wchar_t *)L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v32, v33);
    return 0;
  }
  v35[0] = 0;
  v34 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v35);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 260, (wchar_t *)L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v17, v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v34);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v35[0] | (unsigned __int64)((__int64)v34 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v20);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x18000f648  push    rbp
0x18000f64a  push    rbx
0x18000f64b  push    rsi
0x18000f64c  push    rdi
0x18000f64d  push    r14
0x18000f64f  push    r15
0x18000f651  lea     rbp, [rsp-158h]
0x18000f659  sub     rsp, 258h
0x18000f660  mov     rax, cs:__security_cookie
0x18000f667  xor     rax, rsp
0x18000f66a  mov     [rbp+180h+var_40], rax
0x18000f671  xor     r15d, r15d
0x18000f674  lea     rax, [rsp+280h+Name]
0x18000f679  mov     esi, 104h
0x18000f67e  mov     [r8], r15
0x18000f681  mov     edx, esi
0x18000f683  mov     r14, r8
0x18000f686  mov     r9d, 7FFFFFFEh
0x18000f68c  test    r9, r9
0x18000f68f  jz      short loc_18000F6B0
0x18000f691  movzx   r8d, word ptr [rcx]
0x18000f695  test    r8w, r8w
0x18000f699  jz      short loc_18000F6B0
0x18000f69b  mov     [rax], r8w
0x18000f69f  add     rcx, 2
0x18000f6a3  add     rax, 2
0x18000f6a7  dec     r9
0x18000f6aa  sub     rdx, 1
0x18000f6ae  jnz     short loc_18000F68C
0x18000f6b0  test    rdx, rdx
0x18000f6b3  lea     rcx, [rax-2]
0x18000f6b7  lea     r8, aP0; "_p0"
0x18000f6be  mov     rdx, rsi; unsigned __int64
0x18000f6c1  cmovnz  rcx, rax
0x18000f6c5  mov     [rcx], r15w
0x18000f6c9  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000f6ce  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000f6d3  lea     r8, [rsp+280h+Name]; lpName
0x18000f6d8  xor     edx, edx; bInheritHandle
0x18000f6da  mov     ecx, 1F0003h; dwDesiredAccess
0x18000f6df  call    cs:__imp_OpenSemaphoreW
0x18000f6e5  mov     rbx, rax
0x18000f6e8  test    rax, rax
0x18000f6eb  jz      loc_18000F820
0x18000f6f1  lea     rdx, [rsp+280h+var_25C]; int *
0x18000f6f6  mov     [rsp+280h+var_25C], r15d
0x18000f6fb  mov     rcx, rax; hHandle
0x18000f6fe  mov     [rsp+280h+var_260], r15d; int
0x18000f703  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000f708  mov     edi, eax
0x18000f70a  test    eax, eax
0x18000f70c  jns     short loc_18000F741
0x18000f70e  mov     rcx, [rbp+188h]; this
0x18000f715  lea     r8, aWil; "wil"
0x18000f71c  mov     r9d, eax; char *
0x18000f71f  mov     edx, 0D6h; void *
0x18000f724  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f729  mov     rcx, rbx; hObject
0x18000f72c  call    cs:__imp_CloseHandle
0x18000f732  test    eax, eax
0x18000f734  jz      loc_18000F895
0x18000f73a  mov     eax, edi
0x18000f73c  jmp     loc_18000F840
0x18000f741  lea     r8, asc_180023288; "h"
0x18000f748  mov     rdx, rsi; unsigned __int64
0x18000f74b  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000f750  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000f755  lea     r8, [rsp+280h+Name]; lpName
0x18000f75a  xor     edx, edx; bInheritHandle
0x18000f75c  mov     ecx, 1F0003h; dwDesiredAccess
0x18000f761  call    cs:__imp_OpenSemaphoreW
0x18000f767  mov     rdi, rax
0x18000f76a  test    rax, rax
0x18000f76d  jz      loc_18000F7FB
0x18000f773  lea     rdx, [rsp+280h+var_260]; int *
0x18000f778  mov     rcx, rax; hHandle
0x18000f77b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000f780  mov     esi, eax
0x18000f782  test    eax, eax
0x18000f784  jns     short loc_18000F7C7
0x18000f786  mov     rcx, [rbp+188h]; this
0x18000f78d  lea     r8, aWil; "wil"
0x18000f794  mov     r9d, eax; char *
0x18000f797  mov     edx, 0DEh; void *
0x18000f79c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f7a1  mov     rcx, rdi; hObject
0x18000f7a4  call    cs:__imp_CloseHandle
0x18000f7aa  test    eax, eax
0x18000f7ac  jz      loc_18000F8A7
0x18000f7b2  mov     rcx, rbx; hObject
0x18000f7b5  call    cs:__imp_CloseHandle
0x18000f7bb  test    eax, eax
0x18000f7bd  jz      loc_18000F8B9
0x18000f7c3  mov     eax, esi
0x18000f7c5  jmp     short loc_18000F840
0x18000f7c7  mov     rcx, rdi; hObject
0x18000f7ca  call    cs:__imp_CloseHandle
0x18000f7d0  test    eax, eax
0x18000f7d2  jz      loc_18000F85F
0x18000f7d8  movsxd  rax, [rsp+280h+var_25C]
0x18000f7dd  movsxd  rcx, [rsp+280h+var_260]
0x18000f7e2  shl     rcx, 1Fh
0x18000f7e6  or      rcx, rax
0x18000f7e9  mov     [r14], rcx
0x18000f7ec  mov     rcx, rbx; hObject
0x18000f7ef  call    cs:__imp_CloseHandle
0x18000f7f5  test    eax, eax
0x18000f7f7  jz      short loc_18000F871
0x18000f7f9  jmp     short loc_18000F82B
0x18000f7fb  mov     rcx, [rbp+188h]; this
0x18000f802  mov     edx, 0DCh; void *
0x18000f807  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f80c  mov     rcx, rbx; hObject
0x18000f80f  mov     edi, eax
0x18000f811  call    cs:__imp_CloseHandle
0x18000f817  test    eax, eax
0x18000f819  jz      short loc_18000F883
0x18000f81b  jmp     loc_18000F73A
0x18000f820  call    cs:__imp_GetLastError
0x18000f826  cmp     eax, 2
0x18000f829  jnz     short loc_18000F82F
0x18000f82b  xor     eax, eax
0x18000f82d  jmp     short loc_18000F840
0x18000f82f  mov     rcx, [rbp+188h]; this
0x18000f836  mov     edx, 0D0h; void *
0x18000f83b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f840  mov     rcx, [rbp+180h+var_40]
0x18000f847  xor     rcx, rsp; StackCookie
0x18000f84a  call    __security_check_cookie
0x18000f84f  add     rsp, 258h
0x18000f856  pop     r15
0x18000f858  pop     r14
0x18000f85a  pop     rdi
0x18000f85b  pop     rsi
0x18000f85c  pop     rbx
0x18000f85d  pop     rbp
0x18000f85e  retn
0x18000f85f  mov     rcx, [rbp+188h]; this
0x18000f866  mov     edx, 0A0Bh; void *
0x18000f86b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f871  mov     rcx, [rbp+188h]; this
0x18000f878  mov     edx, 0A0Bh; void *
0x18000f87d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f883  mov     rcx, [rbp+188h]; this
0x18000f88a  mov     edx, 0A0Bh; void *
0x18000f88f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f895  mov     rcx, [rbp+188h]; this
0x18000f89c  mov     edx, 0A0Bh; void *
0x18000f8a1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f8a7  mov     rcx, [rbp+188h]; this
0x18000f8ae  mov     edx, 0A0Bh; void *
0x18000f8b3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f8b9  mov     rcx, [rbp+188h]; this
0x18000f8c0  mov     edx, 0A0Bh; void *
0x18000f8c5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
