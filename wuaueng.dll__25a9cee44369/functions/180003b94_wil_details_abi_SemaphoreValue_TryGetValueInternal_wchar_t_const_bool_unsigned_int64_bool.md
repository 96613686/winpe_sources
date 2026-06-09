# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180003b94`
- end: `0x180003dc9`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `565`
- prototype: `__int64 __fastcall(const wchar_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180004dfc`

## callees

- `0x180001b54`
- `0x180003760`
- `0x180003784`
- `0x1800037a4`
- `0x180003a20`
- `0x180003b94`
- `0x18000fc90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180003c33`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180003cf6`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180003c33`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180003cf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d84`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rdx
  signed __int64 v5; // rcx
  __int64 v7; // r9
  WCHAR v8; // ax
  WCHAR *v9; // rax
  HANDLE v10; // rax
  void *v11; // rsi
  const char *v12; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v15; // rdx
  HANDLE v17; // rax
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  __int64 v21; // r8
  const char *v22; // r9
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r8
  const char *v26; // r9
  int v27; // [rsp+28h] [rbp-E0h] BYREF
  int v28[3]; // [rsp+2Ch] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+38h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+270h] [rbp+168h]

  *a3 = 0;
  v4 = Name;
  v5 = (char *)a1 - (char *)Name;
  v7 = 260;
  do
  {
    if ( v7 == -2147483386 )
      break;
    v8 = *(WCHAR *)((char *)v4 + v5);
    if ( !v8 )
      break;
    *v4++ = v8;
    --v7;
  }
  while ( v7 );
  v9 = v4 - 1;
  if ( v7 )
    v9 = v4;
  *v9 = 0;
  StringCchCatW(Name, (unsigned __int64)v4, L"_p0");
  v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v11 = v10;
  if ( !v10 )
  {
    if ( GetLastError() == 2 )
      LastError = 0;
    else
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, (int)"wil", v12);
LABEL_13:
    if ( !v11 )
      return LastError;
    goto LABEL_22;
  }
  v27 = 0;
  v28[0] = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v27);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD3, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    goto LABEL_13;
  }
  StringCchCatW(Name, v15, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( v17 )
  {
    v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, v28);
    LastError = v20;
    if ( v20 >= 0 )
    {
      if ( !CloseHandle(v19) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v23, v24);
      LastError = 0;
      *a3 = v27 | (unsigned __int64)((__int64)v28[0] << 31);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDB, (int)"wil", (const char *)(unsigned int)v20);
      if ( !CloseHandle(v19) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v21, v22);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, (int)"wil", v18);
  }
LABEL_22:
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v25, v26);
  return LastError;
}

```

## disassembly

```asm
0x180003b94  mov     rax, rsp
0x180003b97  mov     [rax+8], rbx
0x180003b9b  mov     [rax+10h], rsi
0x180003b9f  mov     [rax+20h], rdi
0x180003ba3  push    rbp
0x180003ba4  push    r14
0x180003ba6  push    r15
0x180003ba8  lea     rbp, [rax-168h]
0x180003baf  sub     rsp, 250h
0x180003bb6  mov     rax, cs:__security_cookie
0x180003bbd  xor     rax, rsp
0x180003bc0  mov     [rbp+160h+var_20], rax
0x180003bc7  xor     r15d, r15d
0x180003bca  lea     rax, [rsp+260h+Name]
0x180003bcf  mov     [r8], r15
0x180003bd2  lea     rdx, [rsp+260h+Name]
0x180003bd7  sub     rcx, rax
0x180003bda  mov     r14, r8
0x180003bdd  mov     r9d, 104h
0x180003be3  lea     rax, [r9+7FFFFEFAh]
0x180003bea  test    rax, rax
0x180003bed  jz      short loc_180003C05
0x180003bef  movzx   eax, word ptr [rdx+rcx]
0x180003bf3  test    ax, ax
0x180003bf6  jz      short loc_180003C05
0x180003bf8  mov     [rdx], ax
0x180003bfb  add     rdx, 2; unsigned __int64
0x180003bff  sub     r9, 1
0x180003c03  jnz     short loc_180003BE3
0x180003c05  test    r9, r9
0x180003c08  lea     rax, [rdx-2]
0x180003c0c  lea     r8, aP0; "_p0"
0x180003c13  cmovnz  rax, rdx
0x180003c17  lea     rcx, [rsp+260h+Name]; wchar_t *
0x180003c1c  mov     [rax], r15w
0x180003c20  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180003c25  mov     edi, 1F0003h
0x180003c2a  lea     r8, [rsp+260h+Name]; lpName
0x180003c2f  mov     ecx, edi; dwDesiredAccess
0x180003c31  xor     edx, edx; bInheritHandle
0x180003c33  call    cs:__imp_OpenSemaphoreW
0x180003c39  mov     rsi, rax
0x180003c3c  test    rax, rax
0x180003c3f  jnz     short loc_180003C6D
0x180003c41  call    cs:__imp_GetLastError
0x180003c47  cmp     eax, 2
0x180003c4a  jnz     short loc_180003C51
0x180003c4c  mov     ebx, r15d
0x180003c4f  jmp     short loc_180003CA5
0x180003c51  mov     rcx, [rbp+168h]; this
0x180003c58  lea     r8, aWil; "wil"
0x180003c5f  mov     edx, 0CDh; void *
0x180003c64  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180003c69  mov     ebx, eax
0x180003c6b  jmp     short loc_180003CA5
0x180003c6d  lea     rdx, [rsp+260h+var_240]; int *
0x180003c72  mov     [rsp+260h+var_240], r15d; int
0x180003c77  mov     rcx, rsi; hHandle
0x180003c7a  mov     [rsp+260h+var_23C], r15d
0x180003c7f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180003c84  mov     ebx, eax
0x180003c86  test    eax, eax
0x180003c88  jns     short loc_180003CDC
0x180003c8a  mov     rcx, [rbp+168h]; this
0x180003c91  lea     r8, aWil; "wil"
0x180003c98  mov     r9d, eax; char *
0x180003c9b  mov     edx, 0D3h; void *
0x180003ca0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ca5  test    rsi, rsi
0x180003ca8  jnz     loc_180003D81
0x180003cae  mov     eax, ebx
0x180003cb0  mov     rcx, [rbp+160h+var_20]
0x180003cb7  xor     rcx, rsp; StackCookie
0x180003cba  call    __security_check_cookie
0x180003cbf  lea     r11, [rsp+260h+var_10]
0x180003cc7  mov     rbx, [r11+20h]
0x180003ccb  mov     rsi, [r11+28h]
0x180003ccf  mov     rdi, [r11+38h]
0x180003cd3  mov     rsp, r11
0x180003cd6  pop     r15
0x180003cd8  pop     r14
0x180003cda  pop     rbp
0x180003cdb  retn
0x180003cdc  lea     r8, asc_180018C88; "h"
0x180003ce3  lea     rcx, [rsp+260h+Name]; wchar_t *
0x180003ce8  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180003ced  lea     r8, [rsp+260h+Name]; lpName
0x180003cf2  xor     edx, edx; bInheritHandle
0x180003cf4  mov     ecx, edi; dwDesiredAccess
0x180003cf6  call    cs:__imp_OpenSemaphoreW
0x180003cfc  mov     rdi, rax
0x180003cff  test    rax, rax
0x180003d02  jnz     short loc_180003D20
0x180003d04  mov     rcx, [rbp+168h]; this
0x180003d0b  lea     r8, aWil; "wil"
0x180003d12  mov     edx, 0D9h; void *
0x180003d17  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180003d1c  mov     ebx, eax
0x180003d1e  jmp     short loc_180003D81
0x180003d20  lea     rdx, [rsp+260h+var_23C]; int *
0x180003d25  mov     rcx, rdi; hHandle
0x180003d28  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180003d2d  mov     ebx, eax
0x180003d2f  test    eax, eax
0x180003d31  jns     short loc_180003D5D
0x180003d33  mov     rcx, [rbp+168h]; this
0x180003d3a  lea     r8, aWil; "wil"
0x180003d41  mov     r9d, eax; char *
0x180003d44  mov     edx, 0DBh; void *
0x180003d49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d4e  mov     rcx, rdi; hObject
0x180003d51  call    cs:__imp_CloseHandle
0x180003d57  test    eax, eax
0x180003d59  jz      short loc_180003DA5
0x180003d5b  jmp     short loc_180003D81
0x180003d5d  mov     rcx, rdi; hObject
0x180003d60  call    cs:__imp_CloseHandle
0x180003d66  test    eax, eax
0x180003d68  jz      short loc_180003D93
0x180003d6a  movsxd  rcx, [rsp+260h+var_23C]
0x180003d6f  mov     ebx, r15d
0x180003d72  movsxd  rax, [rsp+260h+var_240]
0x180003d77  shl     rcx, 1Fh
0x180003d7b  or      rcx, rax
0x180003d7e  mov     [r14], rcx
0x180003d81  mov     rcx, rsi; hObject
0x180003d84  call    cs:__imp_CloseHandle
0x180003d8a  test    eax, eax
0x180003d8c  jz      short loc_180003DB7
0x180003d8e  jmp     loc_180003CAE
0x180003d93  mov     rcx, [rbp+168h]; this
0x180003d9a  mov     edx, 9D1h; void *
0x180003d9f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003da5  mov     rcx, [rbp+168h]; this
0x180003dac  mov     edx, 9D1h; void *
0x180003db1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003db7  mov     rcx, [rbp+168h]; this
0x180003dbe  mov     edx, 9D1h; void *
0x180003dc3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
