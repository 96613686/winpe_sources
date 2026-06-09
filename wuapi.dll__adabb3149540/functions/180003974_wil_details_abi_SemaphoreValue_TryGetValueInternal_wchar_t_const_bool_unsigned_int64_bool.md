# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180003974`
- end: `0x180003ba9`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `565`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
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
- `0x180003800`
- `0x180003974`
- `0x18000fce0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180003a13`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180003ad6`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180003a13`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180003ad6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b64`

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
0x180003974  mov     rax, rsp
0x180003977  mov     [rax+8], rbx
0x18000397b  mov     [rax+10h], rsi
0x18000397f  mov     [rax+20h], rdi
0x180003983  push    rbp
0x180003984  push    r14
0x180003986  push    r15
0x180003988  lea     rbp, [rax-168h]
0x18000398f  sub     rsp, 250h
0x180003996  mov     rax, cs:__security_cookie
0x18000399d  xor     rax, rsp
0x1800039a0  mov     [rbp+160h+var_20], rax
0x1800039a7  xor     r15d, r15d
0x1800039aa  lea     rax, [rsp+260h+Name]
0x1800039af  mov     [r8], r15
0x1800039b2  lea     rdx, [rsp+260h+Name]
0x1800039b7  sub     rcx, rax
0x1800039ba  mov     r14, r8
0x1800039bd  mov     r9d, 104h
0x1800039c3  lea     rax, [r9+7FFFFEFAh]
0x1800039ca  test    rax, rax
0x1800039cd  jz      short loc_1800039E5
0x1800039cf  movzx   eax, word ptr [rdx+rcx]
0x1800039d3  test    ax, ax
0x1800039d6  jz      short loc_1800039E5
0x1800039d8  mov     [rdx], ax
0x1800039db  add     rdx, 2; unsigned __int64
0x1800039df  sub     r9, 1
0x1800039e3  jnz     short loc_1800039C3
0x1800039e5  test    r9, r9
0x1800039e8  lea     rax, [rdx-2]
0x1800039ec  lea     r8, aP0; "_p0"
0x1800039f3  cmovnz  rax, rdx
0x1800039f7  lea     rcx, [rsp+260h+Name]; wchar_t *
0x1800039fc  mov     [rax], r15w
0x180003a00  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180003a05  mov     edi, 1F0003h
0x180003a0a  lea     r8, [rsp+260h+Name]; lpName
0x180003a0f  mov     ecx, edi; dwDesiredAccess
0x180003a11  xor     edx, edx; bInheritHandle
0x180003a13  call    cs:__imp_OpenSemaphoreW
0x180003a19  mov     rsi, rax
0x180003a1c  test    rax, rax
0x180003a1f  jnz     short loc_180003A4D
0x180003a21  call    cs:__imp_GetLastError
0x180003a27  cmp     eax, 2
0x180003a2a  jnz     short loc_180003A31
0x180003a2c  mov     ebx, r15d
0x180003a2f  jmp     short loc_180003A85
0x180003a31  mov     rcx, [rbp+168h]; this
0x180003a38  lea     r8, aWil; "wil"
0x180003a3f  mov     edx, 0CDh; void *
0x180003a44  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180003a49  mov     ebx, eax
0x180003a4b  jmp     short loc_180003A85
0x180003a4d  lea     rdx, [rsp+260h+var_240]; int *
0x180003a52  mov     [rsp+260h+var_240], r15d; int
0x180003a57  mov     rcx, rsi; hHandle
0x180003a5a  mov     [rsp+260h+var_23C], r15d
0x180003a5f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180003a64  mov     ebx, eax
0x180003a66  test    eax, eax
0x180003a68  jns     short loc_180003ABC
0x180003a6a  mov     rcx, [rbp+168h]; this
0x180003a71  lea     r8, aWil; "wil"
0x180003a78  mov     r9d, eax; char *
0x180003a7b  mov     edx, 0D3h; void *
0x180003a80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a85  test    rsi, rsi
0x180003a88  jnz     loc_180003B61
0x180003a8e  mov     eax, ebx
0x180003a90  mov     rcx, [rbp+160h+var_20]
0x180003a97  xor     rcx, rsp; StackCookie
0x180003a9a  call    __security_check_cookie
0x180003a9f  lea     r11, [rsp+260h+var_10]
0x180003aa7  mov     rbx, [r11+20h]
0x180003aab  mov     rsi, [r11+28h]
0x180003aaf  mov     rdi, [r11+38h]
0x180003ab3  mov     rsp, r11
0x180003ab6  pop     r15
0x180003ab8  pop     r14
0x180003aba  pop     rbp
0x180003abb  retn
0x180003abc  lea     r8, asc_180018C48; "h"
0x180003ac3  lea     rcx, [rsp+260h+Name]; wchar_t *
0x180003ac8  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180003acd  lea     r8, [rsp+260h+Name]; lpName
0x180003ad2  xor     edx, edx; bInheritHandle
0x180003ad4  mov     ecx, edi; dwDesiredAccess
0x180003ad6  call    cs:__imp_OpenSemaphoreW
0x180003adc  mov     rdi, rax
0x180003adf  test    rax, rax
0x180003ae2  jnz     short loc_180003B00
0x180003ae4  mov     rcx, [rbp+168h]; this
0x180003aeb  lea     r8, aWil; "wil"
0x180003af2  mov     edx, 0D9h; void *
0x180003af7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180003afc  mov     ebx, eax
0x180003afe  jmp     short loc_180003B61
0x180003b00  lea     rdx, [rsp+260h+var_23C]; int *
0x180003b05  mov     rcx, rdi; hHandle
0x180003b08  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180003b0d  mov     ebx, eax
0x180003b0f  test    eax, eax
0x180003b11  jns     short loc_180003B3D
0x180003b13  mov     rcx, [rbp+168h]; this
0x180003b1a  lea     r8, aWil; "wil"
0x180003b21  mov     r9d, eax; char *
0x180003b24  mov     edx, 0DBh; void *
0x180003b29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b2e  mov     rcx, rdi; hObject
0x180003b31  call    cs:__imp_CloseHandle
0x180003b37  test    eax, eax
0x180003b39  jz      short loc_180003B85
0x180003b3b  jmp     short loc_180003B61
0x180003b3d  mov     rcx, rdi; hObject
0x180003b40  call    cs:__imp_CloseHandle
0x180003b46  test    eax, eax
0x180003b48  jz      short loc_180003B73
0x180003b4a  movsxd  rcx, [rsp+260h+var_23C]
0x180003b4f  mov     ebx, r15d
0x180003b52  movsxd  rax, [rsp+260h+var_240]
0x180003b57  shl     rcx, 1Fh
0x180003b5b  or      rcx, rax
0x180003b5e  mov     [r14], rcx
0x180003b61  mov     rcx, rsi; hObject
0x180003b64  call    cs:__imp_CloseHandle
0x180003b6a  test    eax, eax
0x180003b6c  jz      short loc_180003B97
0x180003b6e  jmp     loc_180003A8E
0x180003b73  mov     rcx, [rbp+168h]; this
0x180003b7a  mov     edx, 9D1h; void *
0x180003b7f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b85  mov     rcx, [rbp+168h]; this
0x180003b8c  mov     edx, 9D1h; void *
0x180003b91  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003b97  mov     rcx, [rbp+168h]; this
0x180003b9e  mov     edx, 9D1h; void *
0x180003ba3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
