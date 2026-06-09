# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007b34`
- end: `0x180007da9`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `629`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003a3c`
- `0x180003de0`

## callees

- `0x180005330`
- `0x1800071e4`
- `0x180007204`
- `0x180007620`
- `0x180007b34`
- `0x1800083fc`
- `0x180021740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007bcb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007c46`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007bcb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007c46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007cfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007cfe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ca8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ccd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007cef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ca8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ccd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007cef`

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
  int v12; // r8d
  unsigned int LastError; // edi
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  int v22; // r8d
  unsigned int v23; // esi
  __int64 v24; // r8
  const char *v25; // r9
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  int v36; // [rsp+20h] [rbp-E0h] BYREF
  int v37[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v34, v35);
    return 0;
  }
  v37[0] = 0;
  v36 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v37);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v36);
  v23 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    *a3 = v37[0] | (unsigned __int64)((__int64)v36 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v22, (const char *)(unsigned int)v21);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
  return v23;
}

```

## disassembly

```asm
0x180007b34  push    rbp
0x180007b36  push    rbx
0x180007b37  push    rsi
0x180007b38  push    rdi
0x180007b39  push    r14
0x180007b3b  push    r15
0x180007b3d  lea     rbp, [rsp-158h]
0x180007b45  sub     rsp, 258h
0x180007b4c  mov     rax, cs:__security_cookie
0x180007b53  xor     rax, rsp
0x180007b56  mov     [rbp+180h+var_40], rax
0x180007b5d  xor     r15d, r15d
0x180007b60  lea     rax, [rsp+280h+Name]
0x180007b65  mov     esi, 104h
0x180007b6a  mov     [r8], r15
0x180007b6d  mov     edx, esi
0x180007b6f  mov     r14, r8
0x180007b72  mov     r9d, 7FFFFFFEh
0x180007b78  test    r9, r9
0x180007b7b  jz      short loc_180007B9C
0x180007b7d  movzx   r8d, word ptr [rcx]
0x180007b81  test    r8w, r8w
0x180007b85  jz      short loc_180007B9C
0x180007b87  mov     [rax], r8w
0x180007b8b  add     rcx, 2
0x180007b8f  add     rax, 2
0x180007b93  dec     r9
0x180007b96  sub     rdx, 1
0x180007b9a  jnz     short loc_180007B78
0x180007b9c  test    rdx, rdx
0x180007b9f  lea     rcx, [rax-2]
0x180007ba3  lea     r8, aP0; "_p0"
0x180007baa  mov     rdx, rsi; unsigned __int64
0x180007bad  cmovnz  rcx, rax
0x180007bb1  mov     [rcx], r15w
0x180007bb5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007bba  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007bbf  lea     r8, [rsp+280h+Name]; lpName
0x180007bc4  xor     edx, edx; bInheritHandle
0x180007bc6  mov     ecx, 1F0003h; dwDesiredAccess
0x180007bcb  call    cs:__imp_OpenSemaphoreW
0x180007bd1  mov     rbx, rax
0x180007bd4  test    rax, rax
0x180007bd7  jz      loc_180007CFE
0x180007bdd  lea     rdx, [rsp+280h+var_25C]; int *
0x180007be2  mov     [rsp+280h+var_25C], r15d
0x180007be7  mov     rcx, rax; hHandle
0x180007bea  mov     [rsp+280h+var_260], r15d; int
0x180007bef  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007bf4  mov     edi, eax
0x180007bf6  test    eax, eax
0x180007bf8  jns     short loc_180007C26
0x180007bfa  mov     rcx, [rbp+188h]; this
0x180007c01  mov     r9d, eax; char *
0x180007c04  mov     edx, 0D6h; void *
0x180007c09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007c0e  mov     rcx, rbx; hObject
0x180007c11  call    cs:__imp_CloseHandle
0x180007c17  test    eax, eax
0x180007c19  jz      loc_180007D73
0x180007c1f  mov     eax, edi
0x180007c21  jmp     loc_180007D1E
0x180007c26  lea     r8, asc_180024A40; "h"
0x180007c2d  mov     rdx, rsi; unsigned __int64
0x180007c30  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007c35  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007c3a  lea     r8, [rsp+280h+Name]; lpName
0x180007c3f  xor     edx, edx; bInheritHandle
0x180007c41  mov     ecx, 1F0003h; dwDesiredAccess
0x180007c46  call    cs:__imp_OpenSemaphoreW
0x180007c4c  mov     rdi, rax
0x180007c4f  test    rax, rax
0x180007c52  jz      loc_180007CD9
0x180007c58  lea     rdx, [rsp+280h+var_260]; int *
0x180007c5d  mov     rcx, rax; hHandle
0x180007c60  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007c65  mov     esi, eax
0x180007c67  test    eax, eax
0x180007c69  jns     short loc_180007CA5
0x180007c6b  mov     rcx, [rbp+188h]; this
0x180007c72  mov     r9d, eax; char *
0x180007c75  mov     edx, 0DEh; void *
0x180007c7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007c7f  mov     rcx, rdi; hObject
0x180007c82  call    cs:__imp_CloseHandle
0x180007c88  test    eax, eax
0x180007c8a  jz      loc_180007D85
0x180007c90  mov     rcx, rbx; hObject
0x180007c93  call    cs:__imp_CloseHandle
0x180007c99  test    eax, eax
0x180007c9b  jz      loc_180007D97
0x180007ca1  mov     eax, esi
0x180007ca3  jmp     short loc_180007D1E
0x180007ca5  mov     rcx, rdi; hObject
0x180007ca8  call    cs:__imp_CloseHandle
0x180007cae  test    eax, eax
0x180007cb0  jz      loc_180007D3D
0x180007cb6  movsxd  rax, [rsp+280h+var_25C]
0x180007cbb  movsxd  rcx, [rsp+280h+var_260]
0x180007cc0  shl     rcx, 1Fh
0x180007cc4  or      rcx, rax
0x180007cc7  mov     [r14], rcx
0x180007cca  mov     rcx, rbx; hObject
0x180007ccd  call    cs:__imp_CloseHandle
0x180007cd3  test    eax, eax
0x180007cd5  jz      short loc_180007D4F
0x180007cd7  jmp     short loc_180007D09
0x180007cd9  mov     rcx, [rbp+188h]; this
0x180007ce0  mov     edx, 0DCh; void *
0x180007ce5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007cea  mov     rcx, rbx; hObject
0x180007ced  mov     edi, eax
0x180007cef  call    cs:__imp_CloseHandle
0x180007cf5  test    eax, eax
0x180007cf7  jz      short loc_180007D61
0x180007cf9  jmp     loc_180007C1F
0x180007cfe  call    cs:__imp_GetLastError
0x180007d04  cmp     eax, 2
0x180007d07  jnz     short loc_180007D0D
0x180007d09  xor     eax, eax
0x180007d0b  jmp     short loc_180007D1E
0x180007d0d  mov     rcx, [rbp+188h]; this
0x180007d14  mov     edx, 0D0h; void *
0x180007d19  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007d1e  mov     rcx, [rbp+180h+var_40]
0x180007d25  xor     rcx, rsp; StackCookie
0x180007d28  call    __security_check_cookie
0x180007d2d  add     rsp, 258h
0x180007d34  pop     r15
0x180007d36  pop     r14
0x180007d38  pop     rdi
0x180007d39  pop     rsi
0x180007d3a  pop     rbx
0x180007d3b  pop     rbp
0x180007d3c  retn
0x180007d3d  mov     rcx, [rbp+188h]; this
0x180007d44  mov     edx, 0A0Bh; void *
0x180007d49  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007d4f  mov     rcx, [rbp+188h]; this
0x180007d56  mov     edx, 0A0Bh; void *
0x180007d5b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007d61  mov     rcx, [rbp+188h]; this
0x180007d68  mov     edx, 0A0Bh; void *
0x180007d6d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007d73  mov     rcx, [rbp+188h]; this
0x180007d7a  mov     edx, 0A0Bh; void *
0x180007d7f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007d85  mov     rcx, [rbp+188h]; this
0x180007d8c  mov     edx, 0A0Bh; void *
0x180007d91  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007d97  mov     rcx, [rbp+188h]; this
0x180007d9e  mov     edx, 0A0Bh; void *
0x180007da3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
