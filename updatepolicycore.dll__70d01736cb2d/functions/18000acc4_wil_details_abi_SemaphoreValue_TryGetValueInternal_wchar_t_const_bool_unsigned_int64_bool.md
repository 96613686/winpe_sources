# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000acc4`
- end: `0x18000af02`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `574`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000c208`

## callees

- `0x180008f38`
- `0x18000aac0`
- `0x18000aae4`
- `0x18000ab04`
- `0x18000ab50`
- `0x18000acc4`
- `0x18002ffd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ad66`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ae2f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ad66`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ae2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aebd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aebd`

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
  __int64 v20; // r8
  const char *v21; // r9
  __int64 v22; // r8
  const char *v23; // r9
  __int64 v24; // r8
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
0x18000acc4  mov     rax, rsp
0x18000acc7  mov     [rax+8], rbx
0x18000accb  mov     [rax+10h], rsi
0x18000accf  mov     [rax+20h], rdi
0x18000acd3  push    rbp
0x18000acd4  push    r14
0x18000acd6  push    r15
0x18000acd8  lea     rbp, [rax-168h]
0x18000acdf  sub     rsp, 250h
0x18000ace6  mov     rax, cs:__security_cookie
0x18000aced  xor     rax, rsp
0x18000acf0  mov     [rbp+160h+var_20], rax
0x18000acf7  xor     r15d, r15d
0x18000acfa  lea     rax, [rsp+260h+Name]
0x18000acff  mov     edi, 104h
0x18000ad04  mov     [r8], r15
0x18000ad07  mov     r9d, edi
0x18000ad0a  lea     rdx, [rsp+260h+Name]
0x18000ad0f  sub     rcx, rax
0x18000ad12  mov     r14, r8
0x18000ad15  lea     rax, [r9+7FFFFEFAh]
0x18000ad1c  test    rax, rax
0x18000ad1f  jz      short loc_18000AD37
0x18000ad21  movzx   eax, word ptr [rdx+rcx]
0x18000ad25  test    ax, ax
0x18000ad28  jz      short loc_18000AD37
0x18000ad2a  mov     [rdx], ax
0x18000ad2d  add     rdx, 2
0x18000ad31  sub     r9, 1
0x18000ad35  jnz     short loc_18000AD15
0x18000ad37  lea     rax, [rdx-2]
0x18000ad3b  test    r9, r9
0x18000ad3e  lea     r8, aP0; "_p0"
0x18000ad45  cmovnz  rax, rdx
0x18000ad49  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18000ad4e  mov     rdx, rdi; unsigned __int64
0x18000ad51  mov     [rax], r15w
0x18000ad55  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000ad5a  lea     r8, [rsp+260h+Name]; lpName
0x18000ad5f  xor     edx, edx; bInheritHandle
0x18000ad61  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ad66  call    cs:__imp_OpenSemaphoreW
0x18000ad6c  mov     rsi, rax
0x18000ad6f  test    rax, rax
0x18000ad72  jnz     short loc_18000ADA0
0x18000ad74  call    cs:__imp_GetLastError
0x18000ad7a  cmp     eax, 2
0x18000ad7d  jnz     short loc_18000AD84
0x18000ad7f  mov     ebx, r15d
0x18000ad82  jmp     short loc_18000ADD8
0x18000ad84  mov     rcx, [rbp+168h]; this
0x18000ad8b  lea     r8, aWil; "wil"
0x18000ad92  mov     edx, 0CDh; void *
0x18000ad97  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ad9c  mov     ebx, eax
0x18000ad9e  jmp     short loc_18000ADD8
0x18000ada0  lea     rdx, [rsp+260h+var_240]; int *
0x18000ada5  mov     [rsp+260h+var_240], r15d; int
0x18000adaa  mov     rcx, rsi; hHandle
0x18000adad  mov     [rsp+260h+var_23C], r15d
0x18000adb2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000adb7  mov     ebx, eax
0x18000adb9  test    eax, eax
0x18000adbb  jns     short loc_18000AE0F
0x18000adbd  mov     rcx, [rbp+168h]; this
0x18000adc4  lea     r8, aWil; "wil"
0x18000adcb  mov     r9d, eax; char *
0x18000adce  mov     edx, 0D3h; void *
0x18000add3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000add8  test    rsi, rsi
0x18000addb  jnz     loc_18000AEBA
0x18000ade1  mov     eax, ebx
0x18000ade3  mov     rcx, [rbp+160h+var_20]
0x18000adea  xor     rcx, rsp; StackCookie
0x18000aded  call    __security_check_cookie
0x18000adf2  lea     r11, [rsp+260h+var_10]
0x18000adfa  mov     rbx, [r11+20h]
0x18000adfe  mov     rsi, [r11+28h]
0x18000ae02  mov     rdi, [r11+38h]
0x18000ae06  mov     rsp, r11
0x18000ae09  pop     r15
0x18000ae0b  pop     r14
0x18000ae0d  pop     rbp
0x18000ae0e  retn
0x18000ae0f  lea     r8, asc_18003C568; "h"
0x18000ae16  mov     rdx, rdi; unsigned __int64
0x18000ae19  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18000ae1e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000ae23  lea     r8, [rsp+260h+Name]; lpName
0x18000ae28  xor     edx, edx; bInheritHandle
0x18000ae2a  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ae2f  call    cs:__imp_OpenSemaphoreW
0x18000ae35  mov     rdi, rax
0x18000ae38  test    rax, rax
0x18000ae3b  jnz     short loc_18000AE59
0x18000ae3d  mov     rcx, [rbp+168h]; this
0x18000ae44  lea     r8, aWil; "wil"
0x18000ae4b  mov     edx, 0D9h; void *
0x18000ae50  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ae55  mov     ebx, eax
0x18000ae57  jmp     short loc_18000AEBA
0x18000ae59  lea     rdx, [rsp+260h+var_23C]; int *
0x18000ae5e  mov     rcx, rdi; hHandle
0x18000ae61  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000ae66  mov     ebx, eax
0x18000ae68  test    eax, eax
0x18000ae6a  jns     short loc_18000AE96
0x18000ae6c  mov     rcx, [rbp+168h]; this
0x18000ae73  lea     r8, aWil; "wil"
0x18000ae7a  mov     r9d, eax; char *
0x18000ae7d  mov     edx, 0DBh; void *
0x18000ae82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ae87  mov     rcx, rdi; hObject
0x18000ae8a  call    cs:__imp_CloseHandle
0x18000ae90  test    eax, eax
0x18000ae92  jz      short loc_18000AEDE
0x18000ae94  jmp     short loc_18000AEBA
0x18000ae96  mov     rcx, rdi; hObject
0x18000ae99  call    cs:__imp_CloseHandle
0x18000ae9f  test    eax, eax
0x18000aea1  jz      short loc_18000AECC
0x18000aea3  movsxd  rcx, [rsp+260h+var_23C]
0x18000aea8  mov     ebx, r15d
0x18000aeab  movsxd  rax, [rsp+260h+var_240]
0x18000aeb0  shl     rcx, 1Fh
0x18000aeb4  or      rcx, rax
0x18000aeb7  mov     [r14], rcx
0x18000aeba  mov     rcx, rsi; hObject
0x18000aebd  call    cs:__imp_CloseHandle
0x18000aec3  test    eax, eax
0x18000aec5  jz      short loc_18000AEF0
0x18000aec7  jmp     loc_18000ADE1
0x18000aecc  mov     rcx, [rbp+168h]; this
0x18000aed3  mov     edx, 9D1h; void *
0x18000aed8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000aede  mov     rcx, [rbp+168h]; this
0x18000aee5  mov     edx, 9D1h; void *
0x18000aeea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000aef0  mov     rcx, [rbp+168h]; this
0x18000aef7  mov     edx, 9D1h; void *
0x18000aefc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
