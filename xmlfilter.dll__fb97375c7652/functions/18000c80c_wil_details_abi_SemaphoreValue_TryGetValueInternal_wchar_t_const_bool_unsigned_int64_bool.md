# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000c80c`
- end: `0x18000ca9b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180005198`
- `0x180005568`

## callees

- `0x1800020e0`
- `0x1800086f4`
- `0x18000b724`
- `0x18000b744`
- `0x18000c2b4`
- `0x18000c80c`
- `0x18000d20c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c9e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c9e9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c8a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c91c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c8a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c91c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c8ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c95f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c970`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c988`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c9ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c9da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c8ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c95f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c970`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c988`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c9ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c9da`

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
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
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
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h] BYREF
  int v34[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v32);
    return 0;
  }
  v34[0] = 0;
  v33 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v34);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v33);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v34[0] | (unsigned __int64)((__int64)v33 << 31);
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
0x18000c80c  push    rbp
0x18000c80e  push    rbx
0x18000c80f  push    rsi
0x18000c810  push    rdi
0x18000c811  push    r14
0x18000c813  push    r15
0x18000c815  lea     rbp, [rsp-158h]
0x18000c81d  sub     rsp, 258h
0x18000c824  mov     rax, cs:__security_cookie
0x18000c82b  xor     rax, rsp
0x18000c82e  mov     [rbp+180h+var_40], rax
0x18000c835  xor     r15d, r15d
0x18000c838  lea     rax, [rsp+280h+Name]
0x18000c83d  mov     [r8], r15
0x18000c840  mov     r14, r8
0x18000c843  mov     edx, 104h
0x18000c848  mov     r9d, 7FFFFFFEh
0x18000c84e  test    r9, r9
0x18000c851  jz      short loc_18000C872
0x18000c853  movzx   r8d, word ptr [rcx]
0x18000c857  test    r8w, r8w
0x18000c85b  jz      short loc_18000C872
0x18000c85d  mov     [rax], r8w
0x18000c861  add     rcx, 2
0x18000c865  add     rax, 2
0x18000c869  dec     r9
0x18000c86c  sub     rdx, 1; unsigned __int64
0x18000c870  jnz     short loc_18000C84E
0x18000c872  test    rdx, rdx
0x18000c875  lea     rcx, [rax-2]
0x18000c879  lea     r8, aP0; "_p0"
0x18000c880  cmovnz  rcx, rax
0x18000c884  mov     [rcx], r15w
0x18000c888  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000c88d  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000c892  mov     esi, 1F0003h
0x18000c897  lea     r8, [rsp+280h+Name]; lpName
0x18000c89c  mov     ecx, esi; dwDesiredAccess
0x18000c89e  xor     edx, edx; bInheritHandle
0x18000c8a0  call    cs:__imp_OpenSemaphoreW
0x18000c8a6  mov     rbx, rax
0x18000c8a9  test    rax, rax
0x18000c8ac  jz      loc_18000C9E9
0x18000c8b2  lea     rdx, [rsp+280h+var_25C]; int *
0x18000c8b7  mov     [rsp+280h+var_25C], r15d
0x18000c8bc  mov     rcx, rax; hHandle
0x18000c8bf  mov     [rsp+280h+var_260], r15d; int
0x18000c8c4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c8c9  mov     edi, eax
0x18000c8cb  test    eax, eax
0x18000c8cd  jns     short loc_18000C902
0x18000c8cf  mov     rcx, [rbp+188h]; this
0x18000c8d6  lea     r8, aWil; "wil"
0x18000c8dd  mov     r9d, eax; char *
0x18000c8e0  mov     edx, 0D6h; void *
0x18000c8e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c8ea  mov     rcx, rbx; hObject
0x18000c8ed  call    cs:__imp_CloseHandle
0x18000c8f3  test    eax, eax
0x18000c8f5  jz      loc_18000CA65
0x18000c8fb  mov     eax, edi
0x18000c8fd  jmp     loc_18000CA10
0x18000c902  lea     r8, asc_180019780; "h"
0x18000c909  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000c90e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000c913  lea     r8, [rsp+280h+Name]; lpName
0x18000c918  xor     edx, edx; bInheritHandle
0x18000c91a  mov     ecx, esi; dwDesiredAccess
0x18000c91c  call    cs:__imp_OpenSemaphoreW
0x18000c922  mov     rdi, rax
0x18000c925  test    rax, rax
0x18000c928  jz      loc_18000C9BD
0x18000c92e  lea     rdx, [rsp+280h+var_260]; int *
0x18000c933  mov     rcx, rax; hHandle
0x18000c936  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c93b  mov     esi, eax
0x18000c93d  test    eax, eax
0x18000c93f  jns     short loc_18000C985
0x18000c941  mov     rcx, [rbp+188h]; this
0x18000c948  lea     r8, aWil; "wil"
0x18000c94f  mov     r9d, eax; char *
0x18000c952  mov     edx, 0DEh; void *
0x18000c957  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c95c  mov     rcx, rdi; hObject
0x18000c95f  call    cs:__imp_CloseHandle
0x18000c965  test    eax, eax
0x18000c967  jz      loc_18000CA77
0x18000c96d  mov     rcx, rbx; hObject
0x18000c970  call    cs:__imp_CloseHandle
0x18000c976  test    eax, eax
0x18000c978  jz      loc_18000CA89
0x18000c97e  mov     eax, esi
0x18000c980  jmp     loc_18000CA10
0x18000c985  mov     rcx, rdi; hObject
0x18000c988  call    cs:__imp_CloseHandle
0x18000c98e  test    eax, eax
0x18000c990  jz      loc_18000CA2F
0x18000c996  movsxd  rax, [rsp+280h+var_25C]
0x18000c99b  movsxd  rcx, [rsp+280h+var_260]
0x18000c9a0  shl     rcx, 1Fh
0x18000c9a4  or      rcx, rax
0x18000c9a7  mov     [r14], rcx
0x18000c9aa  mov     rcx, rbx; hObject
0x18000c9ad  call    cs:__imp_CloseHandle
0x18000c9b3  test    eax, eax
0x18000c9b5  jz      loc_18000CA41
0x18000c9bb  jmp     short loc_18000C9F4
0x18000c9bd  mov     rcx, [rbp+188h]; this
0x18000c9c4  lea     r8, aWil; "wil"
0x18000c9cb  mov     edx, 0DCh; void *
0x18000c9d0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c9d5  mov     rcx, rbx; hObject
0x18000c9d8  mov     edi, eax
0x18000c9da  call    cs:__imp_CloseHandle
0x18000c9e0  test    eax, eax
0x18000c9e2  jz      short loc_18000CA53
0x18000c9e4  jmp     loc_18000C8FB
0x18000c9e9  call    cs:__imp_GetLastError
0x18000c9ef  cmp     eax, 2
0x18000c9f2  jnz     short loc_18000C9F8
0x18000c9f4  xor     eax, eax
0x18000c9f6  jmp     short loc_18000CA10
0x18000c9f8  mov     rcx, [rbp+188h]; this
0x18000c9ff  lea     r8, aWil; "wil"
0x18000ca06  mov     edx, 0D0h; void *
0x18000ca0b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ca10  mov     rcx, [rbp+180h+var_40]
0x18000ca17  xor     rcx, rsp; StackCookie
0x18000ca1a  call    __security_check_cookie
0x18000ca1f  add     rsp, 258h
0x18000ca26  pop     r15
0x18000ca28  pop     r14
0x18000ca2a  pop     rdi
0x18000ca2b  pop     rsi
0x18000ca2c  pop     rbx
0x18000ca2d  pop     rbp
0x18000ca2e  retn
0x18000ca2f  mov     rcx, [rbp+188h]; this
0x18000ca36  mov     edx, 0A0Bh; void *
0x18000ca3b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ca41  mov     rcx, [rbp+188h]; this
0x18000ca48  mov     edx, 0A0Bh; void *
0x18000ca4d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ca53  mov     rcx, [rbp+188h]; this
0x18000ca5a  mov     edx, 0A0Bh; void *
0x18000ca5f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ca65  mov     rcx, [rbp+188h]; this
0x18000ca6c  mov     edx, 0A0Bh; void *
0x18000ca71  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ca77  mov     rcx, [rbp+188h]; this
0x18000ca7e  mov     edx, 0A0Bh; void *
0x18000ca83  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ca89  mov     rcx, [rbp+188h]; this
0x18000ca90  mov     edx, 0A0Bh; void *
0x18000ca95  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
