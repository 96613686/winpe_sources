# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000af60`
- end: `0x18000b19e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `574`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000bd6c`

## callees

- `0x180008c2c`
- `0x18000ad5c`
- `0x18000ad80`
- `0x18000ada0`
- `0x18000adec`
- `0x18000af60`
- `0x18008fe00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b010`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b010`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b002`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b0cb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b002`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b0cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b126`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b135`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b159`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b126`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b135`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b159`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  __int64 v4; // r9
  WCHAR *v5; // rdx
  signed __int64 v6; // rcx
  WCHAR v8; // ax
  WCHAR *v9; // rax
  HANDLE v10; // rax
  void *v11; // rsi
  const char *v12; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // r8d
  const char *v21; // r9
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned int v24; // r8d
  const char *v25; // r9
  int v26; // [rsp+28h] [rbp-E0h] BYREF
  int v27[3]; // [rsp+2Ch] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+38h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+270h] [rbp+168h]

  *a3 = 0;
  v4 = 260;
  v5 = Name;
  v6 = (char *)a1 - (char *)Name;
  do
  {
    if ( v4 == -2147483386 )
      break;
    v8 = *(WCHAR *)((char *)v5 + v6);
    if ( !v8 )
      break;
    *v5++ = v8;
    --v4;
  }
  while ( v4 );
  v9 = v5 - 1;
  if ( v4 )
    v9 = v5;
  *v9 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
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
  v26 = 0;
  v27[0] = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v26);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v26);
    goto LABEL_13;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( v16 )
  {
    v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, v27);
    LastError = v19;
    if ( v19 >= 0 )
    {
      if ( !CloseHandle(v18) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v22, v23);
      LastError = 0;
      *a3 = v26 | (unsigned __int64)((__int64)v27[0] << 31);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDB,
        (unsigned int)"wil",
        (const char *)(unsigned int)v19,
        v26);
      if ( !CloseHandle(v18) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v20, v21);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, (unsigned int)"wil", v17);
  }
LABEL_22:
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v24, v25);
  return LastError;
}

```

## disassembly

```asm
0x18000af60  mov     rax, rsp
0x18000af63  mov     [rax+8], rbx
0x18000af67  mov     [rax+10h], rsi
0x18000af6b  mov     [rax+20h], rdi
0x18000af6f  push    rbp
0x18000af70  push    r14
0x18000af72  push    r15
0x18000af74  lea     rbp, [rax-168h]
0x18000af7b  sub     rsp, 250h
0x18000af82  mov     rax, cs:__security_cookie
0x18000af89  xor     rax, rsp
0x18000af8c  mov     [rbp+160h+var_20], rax
0x18000af93  xor     r15d, r15d
0x18000af96  lea     rax, [rsp+260h+Name]
0x18000af9b  mov     edi, 104h
0x18000afa0  mov     [r8], r15
0x18000afa3  mov     r9d, edi
0x18000afa6  lea     rdx, [rsp+260h+Name]
0x18000afab  sub     rcx, rax
0x18000afae  mov     r14, r8
0x18000afb1  lea     rax, [r9+7FFFFEFAh]
0x18000afb8  test    rax, rax
0x18000afbb  jz      short loc_18000AFD3
0x18000afbd  movzx   eax, word ptr [rdx+rcx]
0x18000afc1  test    ax, ax
0x18000afc4  jz      short loc_18000AFD3
0x18000afc6  mov     [rdx], ax
0x18000afc9  add     rdx, 2
0x18000afcd  sub     r9, 1
0x18000afd1  jnz     short loc_18000AFB1
0x18000afd3  lea     rax, [rdx-2]
0x18000afd7  test    r9, r9
0x18000afda  lea     r8, aP0; "_p0"
0x18000afe1  cmovnz  rax, rdx
0x18000afe5  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18000afea  mov     rdx, rdi; unsigned __int64
0x18000afed  mov     [rax], r15w
0x18000aff1  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000aff6  lea     r8, [rsp+260h+Name]; lpName
0x18000affb  xor     edx, edx; bInheritHandle
0x18000affd  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b002  call    cs:__imp_OpenSemaphoreW
0x18000b008  mov     rsi, rax
0x18000b00b  test    rax, rax
0x18000b00e  jnz     short loc_18000B03C
0x18000b010  call    cs:__imp_GetLastError
0x18000b016  cmp     eax, 2
0x18000b019  jnz     short loc_18000B020
0x18000b01b  mov     ebx, r15d
0x18000b01e  jmp     short loc_18000B074
0x18000b020  mov     rcx, [rbp+168h]; this
0x18000b027  lea     r8, aWil; "wil"
0x18000b02e  mov     edx, 0CDh; void *
0x18000b033  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b038  mov     ebx, eax
0x18000b03a  jmp     short loc_18000B074
0x18000b03c  lea     rdx, [rsp+260h+var_240]; int *
0x18000b041  mov     [rsp+260h+var_240], r15d; int
0x18000b046  mov     rcx, rsi; hHandle
0x18000b049  mov     [rsp+260h+var_23C], r15d
0x18000b04e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b053  mov     ebx, eax
0x18000b055  test    eax, eax
0x18000b057  jns     short loc_18000B0AB
0x18000b059  mov     rcx, [rbp+168h]; this
0x18000b060  lea     r8, aWil; "wil"
0x18000b067  mov     r9d, eax; char *
0x18000b06a  mov     edx, 0D3h; void *
0x18000b06f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b074  test    rsi, rsi
0x18000b077  jnz     loc_18000B156
0x18000b07d  mov     eax, ebx
0x18000b07f  mov     rcx, [rbp+160h+var_20]
0x18000b086  xor     rcx, rsp; StackCookie
0x18000b089  call    __security_check_cookie
0x18000b08e  lea     r11, [rsp+260h+var_10]
0x18000b096  mov     rbx, [r11+20h]
0x18000b09a  mov     rsi, [r11+28h]
0x18000b09e  mov     rdi, [r11+38h]
0x18000b0a2  mov     rsp, r11
0x18000b0a5  pop     r15
0x18000b0a7  pop     r14
0x18000b0a9  pop     rbp
0x18000b0aa  retn
0x18000b0ab  lea     r8, asc_1800A2D98; "h"
0x18000b0b2  mov     rdx, rdi; unsigned __int64
0x18000b0b5  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18000b0ba  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000b0bf  lea     r8, [rsp+260h+Name]; lpName
0x18000b0c4  xor     edx, edx; bInheritHandle
0x18000b0c6  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b0cb  call    cs:__imp_OpenSemaphoreW
0x18000b0d1  mov     rdi, rax
0x18000b0d4  test    rax, rax
0x18000b0d7  jnz     short loc_18000B0F5
0x18000b0d9  mov     rcx, [rbp+168h]; this
0x18000b0e0  lea     r8, aWil; "wil"
0x18000b0e7  mov     edx, 0D9h; void *
0x18000b0ec  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b0f1  mov     ebx, eax
0x18000b0f3  jmp     short loc_18000B156
0x18000b0f5  lea     rdx, [rsp+260h+var_23C]; int *
0x18000b0fa  mov     rcx, rdi; hHandle
0x18000b0fd  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b102  mov     ebx, eax
0x18000b104  test    eax, eax
0x18000b106  jns     short loc_18000B132
0x18000b108  mov     rcx, [rbp+168h]; this
0x18000b10f  lea     r8, aWil; "wil"
0x18000b116  mov     r9d, eax; char *
0x18000b119  mov     edx, 0DBh; void *
0x18000b11e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b123  mov     rcx, rdi; hObject
0x18000b126  call    cs:__imp_CloseHandle
0x18000b12c  test    eax, eax
0x18000b12e  jz      short loc_18000B17A
0x18000b130  jmp     short loc_18000B156
0x18000b132  mov     rcx, rdi; hObject
0x18000b135  call    cs:__imp_CloseHandle
0x18000b13b  test    eax, eax
0x18000b13d  jz      short loc_18000B168
0x18000b13f  movsxd  rcx, [rsp+260h+var_23C]
0x18000b144  mov     ebx, r15d
0x18000b147  movsxd  rax, [rsp+260h+var_240]
0x18000b14c  shl     rcx, 1Fh
0x18000b150  or      rcx, rax
0x18000b153  mov     [r14], rcx
0x18000b156  mov     rcx, rsi; hObject
0x18000b159  call    cs:__imp_CloseHandle
0x18000b15f  test    eax, eax
0x18000b161  jz      short loc_18000B18C
0x18000b163  jmp     loc_18000B07D
0x18000b168  mov     rcx, [rbp+168h]; this
0x18000b16f  mov     edx, 9D1h; void *
0x18000b174  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b17a  mov     rcx, [rbp+168h]; this
0x18000b181  mov     edx, 9D1h; void *
0x18000b186  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b18c  mov     rcx, [rbp+168h]; this
0x18000b193  mov     edx, 9D1h; void *
0x18000b198  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
