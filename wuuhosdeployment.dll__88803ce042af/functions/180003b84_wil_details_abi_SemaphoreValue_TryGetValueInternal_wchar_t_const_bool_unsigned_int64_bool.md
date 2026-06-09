# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180003b84`
- end: `0x180003db9`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `565`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180005754`

## callees

- `0x180001d38`
- `0x180003950`
- `0x180003974`
- `0x180003994`
- `0x180003a10`
- `0x180003b84`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180003c23`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180003ce6`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180003c23`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180003ce6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d74`

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
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
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
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, (unsigned int)"wil", v12);
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
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v27);
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
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDB,
        (unsigned int)"wil",
        (const char *)(unsigned int)v20,
        v27);
      if ( !CloseHandle(v19) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v21, v22);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, (unsigned int)"wil", v18);
  }
LABEL_22:
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v25, v26);
  return LastError;
}

```

## disassembly

```asm
0x180003b84  mov     rax, rsp
0x180003b87  mov     [rax+8], rbx
0x180003b8b  mov     [rax+10h], rsi
0x180003b8f  mov     [rax+20h], rdi
0x180003b93  push    rbp
0x180003b94  push    r14
0x180003b96  push    r15
0x180003b98  lea     rbp, [rax-168h]
0x180003b9f  sub     rsp, 250h
0x180003ba6  mov     rax, cs:__security_cookie
0x180003bad  xor     rax, rsp
0x180003bb0  mov     [rbp+160h+var_20], rax
0x180003bb7  xor     r15d, r15d
0x180003bba  lea     rax, [rsp+260h+Name]
0x180003bbf  mov     [r8], r15
0x180003bc2  lea     rdx, [rsp+260h+Name]
0x180003bc7  sub     rcx, rax
0x180003bca  mov     r14, r8
0x180003bcd  mov     r9d, 104h
0x180003bd3  lea     rax, [r9+7FFFFEFAh]
0x180003bda  test    rax, rax
0x180003bdd  jz      short loc_180003BF5
0x180003bdf  movzx   eax, word ptr [rdx+rcx]
0x180003be3  test    ax, ax
0x180003be6  jz      short loc_180003BF5
0x180003be8  mov     [rdx], ax
0x180003beb  add     rdx, 2; unsigned __int64
0x180003bef  sub     r9, 1
0x180003bf3  jnz     short loc_180003BD3
0x180003bf5  test    r9, r9
0x180003bf8  lea     rax, [rdx-2]
0x180003bfc  lea     r8, aP0; "_p0"
0x180003c03  cmovnz  rax, rdx
0x180003c07  lea     rcx, [rsp+260h+Name]; wchar_t *
0x180003c0c  mov     [rax], r15w
0x180003c10  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180003c15  mov     edi, 1F0003h
0x180003c1a  lea     r8, [rsp+260h+Name]; lpName
0x180003c1f  mov     ecx, edi; dwDesiredAccess
0x180003c21  xor     edx, edx; bInheritHandle
0x180003c23  call    cs:__imp_OpenSemaphoreW
0x180003c29  mov     rsi, rax
0x180003c2c  test    rax, rax
0x180003c2f  jnz     short loc_180003C5D
0x180003c31  call    cs:__imp_GetLastError
0x180003c37  cmp     eax, 2
0x180003c3a  jnz     short loc_180003C41
0x180003c3c  mov     ebx, r15d
0x180003c3f  jmp     short loc_180003C95
0x180003c41  mov     rcx, [rbp+168h]; this
0x180003c48  lea     r8, aWil; "wil"
0x180003c4f  mov     edx, 0CDh; void *
0x180003c54  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180003c59  mov     ebx, eax
0x180003c5b  jmp     short loc_180003C95
0x180003c5d  lea     rdx, [rsp+260h+var_240]; int *
0x180003c62  mov     [rsp+260h+var_240], r15d; int
0x180003c67  mov     rcx, rsi; hHandle
0x180003c6a  mov     [rsp+260h+var_23C], r15d
0x180003c6f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180003c74  mov     ebx, eax
0x180003c76  test    eax, eax
0x180003c78  jns     short loc_180003CCC
0x180003c7a  mov     rcx, [rbp+168h]; this
0x180003c81  lea     r8, aWil; "wil"
0x180003c88  mov     r9d, eax; char *
0x180003c8b  mov     edx, 0D3h; void *
0x180003c90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c95  test    rsi, rsi
0x180003c98  jnz     loc_180003D71
0x180003c9e  mov     eax, ebx
0x180003ca0  mov     rcx, [rbp+160h+var_20]
0x180003ca7  xor     rcx, rsp; StackCookie
0x180003caa  call    __security_check_cookie
0x180003caf  lea     r11, [rsp+260h+var_10]
0x180003cb7  mov     rbx, [r11+20h]
0x180003cbb  mov     rsi, [r11+28h]
0x180003cbf  mov     rdi, [r11+38h]
0x180003cc3  mov     rsp, r11
0x180003cc6  pop     r15
0x180003cc8  pop     r14
0x180003cca  pop     rbp
0x180003ccb  retn
0x180003ccc  lea     r8, asc_18004D9F8; "h"
0x180003cd3  lea     rcx, [rsp+260h+Name]; wchar_t *
0x180003cd8  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180003cdd  lea     r8, [rsp+260h+Name]; lpName
0x180003ce2  xor     edx, edx; bInheritHandle
0x180003ce4  mov     ecx, edi; dwDesiredAccess
0x180003ce6  call    cs:__imp_OpenSemaphoreW
0x180003cec  mov     rdi, rax
0x180003cef  test    rax, rax
0x180003cf2  jnz     short loc_180003D10
0x180003cf4  mov     rcx, [rbp+168h]; this
0x180003cfb  lea     r8, aWil; "wil"
0x180003d02  mov     edx, 0D9h; void *
0x180003d07  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180003d0c  mov     ebx, eax
0x180003d0e  jmp     short loc_180003D71
0x180003d10  lea     rdx, [rsp+260h+var_23C]; int *
0x180003d15  mov     rcx, rdi; hHandle
0x180003d18  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180003d1d  mov     ebx, eax
0x180003d1f  test    eax, eax
0x180003d21  jns     short loc_180003D4D
0x180003d23  mov     rcx, [rbp+168h]; this
0x180003d2a  lea     r8, aWil; "wil"
0x180003d31  mov     r9d, eax; char *
0x180003d34  mov     edx, 0DBh; void *
0x180003d39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d3e  mov     rcx, rdi; hObject
0x180003d41  call    cs:__imp_CloseHandle
0x180003d47  test    eax, eax
0x180003d49  jz      short loc_180003D95
0x180003d4b  jmp     short loc_180003D71
0x180003d4d  mov     rcx, rdi; hObject
0x180003d50  call    cs:__imp_CloseHandle
0x180003d56  test    eax, eax
0x180003d58  jz      short loc_180003D83
0x180003d5a  movsxd  rcx, [rsp+260h+var_23C]
0x180003d5f  mov     ebx, r15d
0x180003d62  movsxd  rax, [rsp+260h+var_240]
0x180003d67  shl     rcx, 1Fh
0x180003d6b  or      rcx, rax
0x180003d6e  mov     [r14], rcx
0x180003d71  mov     rcx, rsi; hObject
0x180003d74  call    cs:__imp_CloseHandle
0x180003d7a  test    eax, eax
0x180003d7c  jz      short loc_180003DA7
0x180003d7e  jmp     loc_180003C9E
0x180003d83  mov     rcx, [rbp+168h]; this
0x180003d8a  mov     edx, 9D1h; void *
0x180003d8f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003d95  mov     rcx, [rbp+168h]; this
0x180003d9c  mov     edx, 9D1h; void *
0x180003da1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003da7  mov     rcx, [rbp+168h]; this
0x180003dae  mov     edx, 9D1h; void *
0x180003db3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
