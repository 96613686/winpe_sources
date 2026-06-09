# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009080`
- end: `0x1800092b5`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `565`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000a854`

## callees

- `0x180007608`
- `0x180008e64`
- `0x180008e88`
- `0x180008ea8`
- `0x180008f00`
- `0x180009080`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000911f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800091e2`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000911f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800091e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000912d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000912d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000923d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000924c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009270`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000923d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000924c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009270`

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
0x180009080  mov     rax, rsp
0x180009083  mov     [rax+8], rbx
0x180009087  mov     [rax+10h], rsi
0x18000908b  mov     [rax+20h], rdi
0x18000908f  push    rbp
0x180009090  push    r14
0x180009092  push    r15
0x180009094  lea     rbp, [rax-168h]
0x18000909b  sub     rsp, 250h
0x1800090a2  mov     rax, cs:__security_cookie
0x1800090a9  xor     rax, rsp
0x1800090ac  mov     [rbp+160h+var_20], rax
0x1800090b3  xor     r15d, r15d
0x1800090b6  lea     rax, [rsp+260h+Name]
0x1800090bb  mov     [r8], r15
0x1800090be  lea     rdx, [rsp+260h+Name]
0x1800090c3  sub     rcx, rax
0x1800090c6  mov     r14, r8
0x1800090c9  mov     r9d, 104h
0x1800090cf  lea     rax, [r9+7FFFFEFAh]
0x1800090d6  test    rax, rax
0x1800090d9  jz      short loc_1800090F1
0x1800090db  movzx   eax, word ptr [rdx+rcx]
0x1800090df  test    ax, ax
0x1800090e2  jz      short loc_1800090F1
0x1800090e4  mov     [rdx], ax
0x1800090e7  add     rdx, 2; unsigned __int64
0x1800090eb  sub     r9, 1
0x1800090ef  jnz     short loc_1800090CF
0x1800090f1  test    r9, r9
0x1800090f4  lea     rax, [rdx-2]
0x1800090f8  lea     r8, aP0; "_p0"
0x1800090ff  cmovnz  rax, rdx
0x180009103  lea     rcx, [rsp+260h+Name]; wchar_t *
0x180009108  mov     [rax], r15w
0x18000910c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180009111  mov     edi, 1F0003h
0x180009116  lea     r8, [rsp+260h+Name]; lpName
0x18000911b  mov     ecx, edi; dwDesiredAccess
0x18000911d  xor     edx, edx; bInheritHandle
0x18000911f  call    cs:__imp_OpenSemaphoreW
0x180009125  mov     rsi, rax
0x180009128  test    rax, rax
0x18000912b  jnz     short loc_180009159
0x18000912d  call    cs:__imp_GetLastError
0x180009133  cmp     eax, 2
0x180009136  jnz     short loc_18000913D
0x180009138  mov     ebx, r15d
0x18000913b  jmp     short loc_180009191
0x18000913d  mov     rcx, [rbp+168h]; this
0x180009144  lea     r8, aWil; "wil"
0x18000914b  mov     edx, 0CDh; void *
0x180009150  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009155  mov     ebx, eax
0x180009157  jmp     short loc_180009191
0x180009159  lea     rdx, [rsp+260h+var_240]; int *
0x18000915e  mov     [rsp+260h+var_240], r15d; int
0x180009163  mov     rcx, rsi; hHandle
0x180009166  mov     [rsp+260h+var_23C], r15d
0x18000916b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009170  mov     ebx, eax
0x180009172  test    eax, eax
0x180009174  jns     short loc_1800091C8
0x180009176  mov     rcx, [rbp+168h]; this
0x18000917d  lea     r8, aWil; "wil"
0x180009184  mov     r9d, eax; char *
0x180009187  mov     edx, 0D3h; void *
0x18000918c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009191  test    rsi, rsi
0x180009194  jnz     loc_18000926D
0x18000919a  mov     eax, ebx
0x18000919c  mov     rcx, [rbp+160h+var_20]
0x1800091a3  xor     rcx, rsp; StackCookie
0x1800091a6  call    __security_check_cookie
0x1800091ab  lea     r11, [rsp+260h+var_10]
0x1800091b3  mov     rbx, [r11+20h]
0x1800091b7  mov     rsi, [r11+28h]
0x1800091bb  mov     rdi, [r11+38h]
0x1800091bf  mov     rsp, r11
0x1800091c2  pop     r15
0x1800091c4  pop     r14
0x1800091c6  pop     rbp
0x1800091c7  retn
0x1800091c8  lea     r8, asc_1800F57E8; "h"
0x1800091cf  lea     rcx, [rsp+260h+Name]; wchar_t *
0x1800091d4  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800091d9  lea     r8, [rsp+260h+Name]; lpName
0x1800091de  xor     edx, edx; bInheritHandle
0x1800091e0  mov     ecx, edi; dwDesiredAccess
0x1800091e2  call    cs:__imp_OpenSemaphoreW
0x1800091e8  mov     rdi, rax
0x1800091eb  test    rax, rax
0x1800091ee  jnz     short loc_18000920C
0x1800091f0  mov     rcx, [rbp+168h]; this
0x1800091f7  lea     r8, aWil; "wil"
0x1800091fe  mov     edx, 0D9h; void *
0x180009203  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009208  mov     ebx, eax
0x18000920a  jmp     short loc_18000926D
0x18000920c  lea     rdx, [rsp+260h+var_23C]; int *
0x180009211  mov     rcx, rdi; hHandle
0x180009214  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009219  mov     ebx, eax
0x18000921b  test    eax, eax
0x18000921d  jns     short loc_180009249
0x18000921f  mov     rcx, [rbp+168h]; this
0x180009226  lea     r8, aWil; "wil"
0x18000922d  mov     r9d, eax; char *
0x180009230  mov     edx, 0DBh; void *
0x180009235  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000923a  mov     rcx, rdi; hObject
0x18000923d  call    cs:__imp_CloseHandle
0x180009243  test    eax, eax
0x180009245  jz      short loc_180009291
0x180009247  jmp     short loc_18000926D
0x180009249  mov     rcx, rdi; hObject
0x18000924c  call    cs:__imp_CloseHandle
0x180009252  test    eax, eax
0x180009254  jz      short loc_18000927F
0x180009256  movsxd  rcx, [rsp+260h+var_23C]
0x18000925b  mov     ebx, r15d
0x18000925e  movsxd  rax, [rsp+260h+var_240]
0x180009263  shl     rcx, 1Fh
0x180009267  or      rcx, rax
0x18000926a  mov     [r14], rcx
0x18000926d  mov     rcx, rsi; hObject
0x180009270  call    cs:__imp_CloseHandle
0x180009276  test    eax, eax
0x180009278  jz      short loc_1800092A3
0x18000927a  jmp     loc_18000919A
0x18000927f  mov     rcx, [rbp+168h]; this
0x180009286  mov     edx, 9D1h; void *
0x18000928b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009291  mov     rcx, [rbp+168h]; this
0x180009298  mov     edx, 9D1h; void *
0x18000929d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800092a3  mov     rcx, [rbp+168h]; this
0x1800092aa  mov     edx, 9D1h; void *
0x1800092af  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
