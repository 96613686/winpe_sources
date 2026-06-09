# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800059f4`
- end: `0x180005c69`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `629`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003bd0`

## callees

- `0x180002230`
- `0x180004b20`
- `0x180005564`
- `0x180005584`
- `0x180005830`
- `0x1800059f4`
- `0x180005dbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005a8b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005b06`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005a8b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005b06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ad1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005baf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ad1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005baf`

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
  StringCchCatW(Name, 260, L"_p0");
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
  StringCchCatW(Name, 260, L"h");
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
0x1800059f4  push    rbp
0x1800059f6  push    rbx
0x1800059f7  push    rsi
0x1800059f8  push    rdi
0x1800059f9  push    r14
0x1800059fb  push    r15
0x1800059fd  lea     rbp, [rsp-158h]
0x180005a05  sub     rsp, 258h
0x180005a0c  mov     rax, cs:__security_cookie
0x180005a13  xor     rax, rsp
0x180005a16  mov     [rbp+180h+var_40], rax
0x180005a1d  xor     r15d, r15d
0x180005a20  lea     rax, [rsp+280h+Name]
0x180005a25  mov     esi, 104h
0x180005a2a  mov     [r8], r15
0x180005a2d  mov     edx, esi
0x180005a2f  mov     r14, r8
0x180005a32  mov     r9d, 7FFFFFFEh
0x180005a38  test    r9, r9
0x180005a3b  jz      short loc_180005A5C
0x180005a3d  movzx   r8d, word ptr [rcx]
0x180005a41  test    r8w, r8w
0x180005a45  jz      short loc_180005A5C
0x180005a47  mov     [rax], r8w
0x180005a4b  add     rcx, 2
0x180005a4f  add     rax, 2
0x180005a53  dec     r9
0x180005a56  sub     rdx, 1
0x180005a5a  jnz     short loc_180005A38
0x180005a5c  test    rdx, rdx
0x180005a5f  lea     rcx, [rax-2]
0x180005a63  lea     r8, aP0; "_p0"
0x180005a6a  mov     rdx, rsi; unsigned __int64
0x180005a6d  cmovnz  rcx, rax
0x180005a71  mov     [rcx], r15w
0x180005a75  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005a7a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005a7f  lea     r8, [rsp+280h+Name]; lpName
0x180005a84  xor     edx, edx; bInheritHandle
0x180005a86  mov     ecx, 1F0003h; dwDesiredAccess
0x180005a8b  call    cs:__imp_OpenSemaphoreW
0x180005a91  mov     rbx, rax
0x180005a94  test    rax, rax
0x180005a97  jz      loc_180005BBE
0x180005a9d  lea     rdx, [rsp+280h+var_25C]; int *
0x180005aa2  mov     [rsp+280h+var_25C], r15d
0x180005aa7  mov     rcx, rax; hHandle
0x180005aaa  mov     [rsp+280h+var_260], r15d; int
0x180005aaf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005ab4  mov     edi, eax
0x180005ab6  test    eax, eax
0x180005ab8  jns     short loc_180005AE6
0x180005aba  mov     rcx, [rbp+188h]; this
0x180005ac1  mov     r9d, eax; char *
0x180005ac4  mov     edx, 0D6h; void *
0x180005ac9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005ace  mov     rcx, rbx; hObject
0x180005ad1  call    cs:__imp_CloseHandle
0x180005ad7  test    eax, eax
0x180005ad9  jz      loc_180005C33
0x180005adf  mov     eax, edi
0x180005ae1  jmp     loc_180005BDE
0x180005ae6  lea     r8, asc_18000C028; "h"
0x180005aed  mov     rdx, rsi; unsigned __int64
0x180005af0  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005af5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005afa  lea     r8, [rsp+280h+Name]; lpName
0x180005aff  xor     edx, edx; bInheritHandle
0x180005b01  mov     ecx, 1F0003h; dwDesiredAccess
0x180005b06  call    cs:__imp_OpenSemaphoreW
0x180005b0c  mov     rdi, rax
0x180005b0f  test    rax, rax
0x180005b12  jz      loc_180005B99
0x180005b18  lea     rdx, [rsp+280h+var_260]; int *
0x180005b1d  mov     rcx, rax; hHandle
0x180005b20  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005b25  mov     esi, eax
0x180005b27  test    eax, eax
0x180005b29  jns     short loc_180005B65
0x180005b2b  mov     rcx, [rbp+188h]; this
0x180005b32  mov     r9d, eax; char *
0x180005b35  mov     edx, 0DEh; void *
0x180005b3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005b3f  mov     rcx, rdi; hObject
0x180005b42  call    cs:__imp_CloseHandle
0x180005b48  test    eax, eax
0x180005b4a  jz      loc_180005C45
0x180005b50  mov     rcx, rbx; hObject
0x180005b53  call    cs:__imp_CloseHandle
0x180005b59  test    eax, eax
0x180005b5b  jz      loc_180005C57
0x180005b61  mov     eax, esi
0x180005b63  jmp     short loc_180005BDE
0x180005b65  mov     rcx, rdi; hObject
0x180005b68  call    cs:__imp_CloseHandle
0x180005b6e  test    eax, eax
0x180005b70  jz      loc_180005BFD
0x180005b76  movsxd  rax, [rsp+280h+var_25C]
0x180005b7b  movsxd  rcx, [rsp+280h+var_260]
0x180005b80  shl     rcx, 1Fh
0x180005b84  or      rcx, rax
0x180005b87  mov     [r14], rcx
0x180005b8a  mov     rcx, rbx; hObject
0x180005b8d  call    cs:__imp_CloseHandle
0x180005b93  test    eax, eax
0x180005b95  jz      short loc_180005C0F
0x180005b97  jmp     short loc_180005BC9
0x180005b99  mov     rcx, [rbp+188h]; this
0x180005ba0  mov     edx, 0DCh; void *
0x180005ba5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005baa  mov     rcx, rbx; hObject
0x180005bad  mov     edi, eax
0x180005baf  call    cs:__imp_CloseHandle
0x180005bb5  test    eax, eax
0x180005bb7  jz      short loc_180005C21
0x180005bb9  jmp     loc_180005ADF
0x180005bbe  call    cs:__imp_GetLastError
0x180005bc4  cmp     eax, 2
0x180005bc7  jnz     short loc_180005BCD
0x180005bc9  xor     eax, eax
0x180005bcb  jmp     short loc_180005BDE
0x180005bcd  mov     rcx, [rbp+188h]; this
0x180005bd4  mov     edx, 0D0h; void *
0x180005bd9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005bde  mov     rcx, [rbp+180h+var_40]
0x180005be5  xor     rcx, rsp; StackCookie
0x180005be8  call    __security_check_cookie
0x180005bed  add     rsp, 258h
0x180005bf4  pop     r15
0x180005bf6  pop     r14
0x180005bf8  pop     rdi
0x180005bf9  pop     rsi
0x180005bfa  pop     rbx
0x180005bfb  pop     rbp
0x180005bfc  retn
0x180005bfd  mov     rcx, [rbp+188h]; this
0x180005c04  mov     edx, 0A0Bh; void *
0x180005c09  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005c0f  mov     rcx, [rbp+188h]; this
0x180005c16  mov     edx, 0A0Bh; void *
0x180005c1b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005c21  mov     rcx, [rbp+188h]; this
0x180005c28  mov     edx, 0A0Bh; void *
0x180005c2d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005c33  mov     rcx, [rbp+188h]; this
0x180005c3a  mov     edx, 0A0Bh; void *
0x180005c3f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005c45  mov     rcx, [rbp+188h]; this
0x180005c4c  mov     edx, 0A0Bh; void *
0x180005c51  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005c57  mov     rcx, [rbp+188h]; this
0x180005c5e  mov     edx, 0A0Bh; void *
0x180005c63  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
