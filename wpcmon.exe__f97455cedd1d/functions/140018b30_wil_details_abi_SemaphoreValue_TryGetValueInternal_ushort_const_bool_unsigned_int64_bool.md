# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140018b30`
- end: `0x140018daa`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x14000fc78`
- `0x14001004c`

## callees

- `0x140005530`
- `0x1400127c0`
- `0x140016834`
- `0x140016854`
- `0x1400185d0`
- `0x140018b30`
- `0x14001b510`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140018c11`
- `KERNEL32!CloseHandle` at `0x140018c83`
- `KERNEL32!CloseHandle` at `0x140018c94`
- `KERNEL32!CloseHandle` at `0x140018ca9`
- `KERNEL32!CloseHandle` at `0x140018cce`
- `KERNEL32!CloseHandle` at `0x140018cf0`
- `KERNEL32!CloseHandle` at `0x140018c11`
- `KERNEL32!CloseHandle` at `0x140018c83`
- `KERNEL32!CloseHandle` at `0x140018c94`
- `KERNEL32!CloseHandle` at `0x140018ca9`
- `KERNEL32!CloseHandle` at `0x140018cce`
- `KERNEL32!CloseHandle` at `0x140018cf0`
- `KERNEL32!OpenSemaphoreW` at `0x140018bc4`
- `KERNEL32!OpenSemaphoreW` at `0x140018c40`
- `KERNEL32!OpenSemaphoreW` at `0x140018bc4`
- `KERNEL32!OpenSemaphoreW` at `0x140018c40`
- `KERNEL32!GetLastError` at `0x140018cff`
- `KERNEL32!GetLastError` at `0x140018cff`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  unsigned int LastError; // edi
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  int v35; // [rsp+20h] [rbp-E0h] BYREF
  int v36[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v6 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v6;
  }
  while ( v6 );
  v8 = v4 - 1;
  if ( v6 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, v6, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v33, v34);
    return 0;
  }
  v36[0] = 0;
  v35 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v36);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v35);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v35);
  v22 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    *a3 = v36[0] | (unsigned __int64)((__int64)v35 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v21, v35);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x140018b30  push    rbp
0x140018b32  push    rbx
0x140018b33  push    rsi
0x140018b34  push    rdi
0x140018b35  push    r14
0x140018b37  push    r15
0x140018b39  lea     rbp, [rsp-158h]
0x140018b41  sub     rsp, 258h
0x140018b48  mov     rax, cs:__security_cookie
0x140018b4f  xor     rax, rsp
0x140018b52  mov     [rbp+180h+var_40], rax
0x140018b59  xor     r15d, r15d
0x140018b5c  lea     rax, [rsp+280h+Name]
0x140018b61  mov     [r8], r15
0x140018b64  mov     r14, r8
0x140018b67  mov     edx, 104h
0x140018b6c  mov     r9d, 7FFFFFFEh
0x140018b72  test    r9, r9
0x140018b75  jz      short loc_140018B96
0x140018b77  movzx   r8d, word ptr [rcx]
0x140018b7b  test    r8w, r8w
0x140018b7f  jz      short loc_140018B96
0x140018b81  mov     [rax], r8w
0x140018b85  add     rcx, 2
0x140018b89  add     rax, 2
0x140018b8d  dec     r9
0x140018b90  sub     rdx, 1; unsigned __int64
0x140018b94  jnz     short loc_140018B72
0x140018b96  test    rdx, rdx
0x140018b99  lea     rcx, [rax-2]
0x140018b9d  lea     r8, aP0; "_p0"
0x140018ba4  cmovnz  rcx, rax
0x140018ba8  mov     [rcx], r15w
0x140018bac  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140018bb1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140018bb6  mov     esi, 1F0003h
0x140018bbb  lea     r8, [rsp+280h+Name]; lpName
0x140018bc0  mov     ecx, esi; dwDesiredAccess
0x140018bc2  xor     edx, edx; bInheritHandle
0x140018bc4  call    cs:__imp_OpenSemaphoreW
0x140018bca  mov     rbx, rax
0x140018bcd  test    rax, rax
0x140018bd0  jz      loc_140018CFF
0x140018bd6  lea     rdx, [rsp+280h+var_25C]; int *
0x140018bdb  mov     [rsp+280h+var_25C], r15d
0x140018be0  mov     rcx, rax; hHandle
0x140018be3  mov     [rsp+280h+var_260], r15d; int
0x140018be8  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140018bed  mov     edi, eax
0x140018bef  test    eax, eax
0x140018bf1  jns     short loc_140018C26
0x140018bf3  mov     rcx, [rbp+188h]; this
0x140018bfa  lea     r8, aWil; "wil"
0x140018c01  mov     r9d, eax; char *
0x140018c04  mov     edx, 0D6h; void *
0x140018c09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018c0e  mov     rcx, rbx; hObject
0x140018c11  call    cs:__imp_CloseHandle
0x140018c17  test    eax, eax
0x140018c19  jz      loc_140018D74
0x140018c1f  mov     eax, edi
0x140018c21  jmp     loc_140018D1F
0x140018c26  lea     r8, asc_1400B3FD8; "h"
0x140018c2d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140018c32  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140018c37  lea     r8, [rsp+280h+Name]; lpName
0x140018c3c  xor     edx, edx; bInheritHandle
0x140018c3e  mov     ecx, esi; dwDesiredAccess
0x140018c40  call    cs:__imp_OpenSemaphoreW
0x140018c46  mov     rdi, rax
0x140018c49  test    rax, rax
0x140018c4c  jz      loc_140018CDA
0x140018c52  lea     rdx, [rsp+280h+var_260]; int *
0x140018c57  mov     rcx, rax; hHandle
0x140018c5a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140018c5f  mov     esi, eax
0x140018c61  test    eax, eax
0x140018c63  jns     short loc_140018CA6
0x140018c65  mov     rcx, [rbp+188h]; this
0x140018c6c  lea     r8, aWil; "wil"
0x140018c73  mov     r9d, eax; char *
0x140018c76  mov     edx, 0DEh; void *
0x140018c7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018c80  mov     rcx, rdi; hObject
0x140018c83  call    cs:__imp_CloseHandle
0x140018c89  test    eax, eax
0x140018c8b  jz      loc_140018D86
0x140018c91  mov     rcx, rbx; hObject
0x140018c94  call    cs:__imp_CloseHandle
0x140018c9a  test    eax, eax
0x140018c9c  jz      loc_140018D98
0x140018ca2  mov     eax, esi
0x140018ca4  jmp     short loc_140018D1F
0x140018ca6  mov     rcx, rdi; hObject
0x140018ca9  call    cs:__imp_CloseHandle
0x140018caf  test    eax, eax
0x140018cb1  jz      loc_140018D3E
0x140018cb7  movsxd  rax, [rsp+280h+var_25C]
0x140018cbc  movsxd  rcx, [rsp+280h+var_260]
0x140018cc1  shl     rcx, 1Fh
0x140018cc5  or      rcx, rax
0x140018cc8  mov     [r14], rcx
0x140018ccb  mov     rcx, rbx; hObject
0x140018cce  call    cs:__imp_CloseHandle
0x140018cd4  test    eax, eax
0x140018cd6  jz      short loc_140018D50
0x140018cd8  jmp     short loc_140018D0A
0x140018cda  mov     rcx, [rbp+188h]; this
0x140018ce1  mov     edx, 0DCh; void *
0x140018ce6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140018ceb  mov     rcx, rbx; hObject
0x140018cee  mov     edi, eax
0x140018cf0  call    cs:__imp_CloseHandle
0x140018cf6  test    eax, eax
0x140018cf8  jz      short loc_140018D62
0x140018cfa  jmp     loc_140018C1F
0x140018cff  call    cs:__imp_GetLastError
0x140018d05  cmp     eax, 2
0x140018d08  jnz     short loc_140018D0E
0x140018d0a  xor     eax, eax
0x140018d0c  jmp     short loc_140018D1F
0x140018d0e  mov     rcx, [rbp+188h]; this
0x140018d15  mov     edx, 0D0h; void *
0x140018d1a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140018d1f  mov     rcx, [rbp+180h+var_40]
0x140018d26  xor     rcx, rsp; StackCookie
0x140018d29  call    __security_check_cookie
0x140018d2e  add     rsp, 258h
0x140018d35  pop     r15
0x140018d37  pop     r14
0x140018d39  pop     rdi
0x140018d3a  pop     rsi
0x140018d3b  pop     rbx
0x140018d3c  pop     rbp
0x140018d3d  retn
0x140018d3e  mov     rcx, [rbp+188h]; this
0x140018d45  mov     edx, 0A0Bh; void *
0x140018d4a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140018d50  mov     rcx, [rbp+188h]; this
0x140018d57  mov     edx, 0A0Bh; void *
0x140018d5c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140018d62  mov     rcx, [rbp+188h]; this
0x140018d69  mov     edx, 0A0Bh; void *
0x140018d6e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140018d74  mov     rcx, [rbp+188h]; this
0x140018d7b  mov     edx, 0A0Bh; void *
0x140018d80  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140018d86  mov     rcx, [rbp+188h]; this
0x140018d8d  mov     edx, 0A0Bh; void *
0x140018d92  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140018d98  mov     rcx, [rbp+188h]; this
0x140018d9f  mov     edx, 0A0Bh; void *
0x140018da4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
