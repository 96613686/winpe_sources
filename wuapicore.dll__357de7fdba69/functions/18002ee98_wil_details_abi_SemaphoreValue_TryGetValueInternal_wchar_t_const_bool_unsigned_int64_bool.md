# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18002ee98`
- end: `0x18002f0d6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `574`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002fe54`

## callees

- `0x180006ac4`
- `0x180007d34`
- `0x18002ded8`
- `0x18002ece8`
- `0x18002ed24`
- `0x18002ee98`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002ef3a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002f003`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002ef3a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002f003`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ef48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ef48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f05e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f06d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f091`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f05e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f06d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f091`

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
0x18002ee98  mov     rax, rsp
0x18002ee9b  mov     [rax+8], rbx
0x18002ee9f  mov     [rax+10h], rsi
0x18002eea3  mov     [rax+20h], rdi
0x18002eea7  push    rbp
0x18002eea8  push    r14
0x18002eeaa  push    r15
0x18002eeac  lea     rbp, [rax-168h]
0x18002eeb3  sub     rsp, 250h
0x18002eeba  mov     rax, cs:__security_cookie
0x18002eec1  xor     rax, rsp
0x18002eec4  mov     [rbp+160h+var_20], rax
0x18002eecb  xor     r15d, r15d
0x18002eece  lea     rax, [rsp+260h+Name]
0x18002eed3  mov     edi, 104h
0x18002eed8  mov     [r8], r15
0x18002eedb  mov     r9d, edi
0x18002eede  lea     rdx, [rsp+260h+Name]
0x18002eee3  sub     rcx, rax
0x18002eee6  mov     r14, r8
0x18002eee9  lea     rax, [r9+7FFFFEFAh]
0x18002eef0  test    rax, rax
0x18002eef3  jz      short loc_18002EF0B
0x18002eef5  movzx   eax, word ptr [rdx+rcx]
0x18002eef9  test    ax, ax
0x18002eefc  jz      short loc_18002EF0B
0x18002eefe  mov     [rdx], ax
0x18002ef01  add     rdx, 2
0x18002ef05  sub     r9, 1
0x18002ef09  jnz     short loc_18002EEE9
0x18002ef0b  lea     rax, [rdx-2]
0x18002ef0f  test    r9, r9
0x18002ef12  lea     r8, aP0; "_p0"
0x18002ef19  cmovnz  rax, rdx
0x18002ef1d  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18002ef22  mov     rdx, rdi; unsigned __int64
0x18002ef25  mov     [rax], r15w
0x18002ef29  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18002ef2e  lea     r8, [rsp+260h+Name]; lpName
0x18002ef33  xor     edx, edx; bInheritHandle
0x18002ef35  mov     ecx, 1F0003h; dwDesiredAccess
0x18002ef3a  call    cs:__imp_OpenSemaphoreW
0x18002ef40  mov     rsi, rax
0x18002ef43  test    rax, rax
0x18002ef46  jnz     short loc_18002EF74
0x18002ef48  call    cs:__imp_GetLastError
0x18002ef4e  cmp     eax, 2
0x18002ef51  jnz     short loc_18002EF58
0x18002ef53  mov     ebx, r15d
0x18002ef56  jmp     short loc_18002EFAC
0x18002ef58  mov     rcx, [rbp+168h]; this
0x18002ef5f  lea     r8, aWil; "wil"
0x18002ef66  mov     edx, 0CDh; void *
0x18002ef6b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002ef70  mov     ebx, eax
0x18002ef72  jmp     short loc_18002EFAC
0x18002ef74  lea     rdx, [rsp+260h+var_240]; int *
0x18002ef79  mov     [rsp+260h+var_240], r15d; int
0x18002ef7e  mov     rcx, rsi; hHandle
0x18002ef81  mov     [rsp+260h+var_23C], r15d
0x18002ef86  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002ef8b  mov     ebx, eax
0x18002ef8d  test    eax, eax
0x18002ef8f  jns     short loc_18002EFE3
0x18002ef91  mov     rcx, [rbp+168h]; this
0x18002ef98  lea     r8, aWil; "wil"
0x18002ef9f  mov     r9d, eax; char *
0x18002efa2  mov     edx, 0D3h; void *
0x18002efa7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002efac  test    rsi, rsi
0x18002efaf  jnz     loc_18002F08E
0x18002efb5  mov     eax, ebx
0x18002efb7  mov     rcx, [rbp+160h+var_20]
0x18002efbe  xor     rcx, rsp; StackCookie
0x18002efc1  call    __security_check_cookie
0x18002efc6  lea     r11, [rsp+260h+var_10]
0x18002efce  mov     rbx, [r11+20h]
0x18002efd2  mov     rsi, [r11+28h]
0x18002efd6  mov     rdi, [r11+38h]
0x18002efda  mov     rsp, r11
0x18002efdd  pop     r15
0x18002efdf  pop     r14
0x18002efe1  pop     rbp
0x18002efe2  retn
0x18002efe3  lea     r8, asc_1800B5EB8; "h"
0x18002efea  mov     rdx, rdi; unsigned __int64
0x18002efed  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18002eff2  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18002eff7  lea     r8, [rsp+260h+Name]; lpName
0x18002effc  xor     edx, edx; bInheritHandle
0x18002effe  mov     ecx, 1F0003h; dwDesiredAccess
0x18002f003  call    cs:__imp_OpenSemaphoreW
0x18002f009  mov     rdi, rax
0x18002f00c  test    rax, rax
0x18002f00f  jnz     short loc_18002F02D
0x18002f011  mov     rcx, [rbp+168h]; this
0x18002f018  lea     r8, aWil; "wil"
0x18002f01f  mov     edx, 0D9h; void *
0x18002f024  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002f029  mov     ebx, eax
0x18002f02b  jmp     short loc_18002F08E
0x18002f02d  lea     rdx, [rsp+260h+var_23C]; int *
0x18002f032  mov     rcx, rdi; hHandle
0x18002f035  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002f03a  mov     ebx, eax
0x18002f03c  test    eax, eax
0x18002f03e  jns     short loc_18002F06A
0x18002f040  mov     rcx, [rbp+168h]; this
0x18002f047  lea     r8, aWil; "wil"
0x18002f04e  mov     r9d, eax; char *
0x18002f051  mov     edx, 0DBh; void *
0x18002f056  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f05b  mov     rcx, rdi; hObject
0x18002f05e  call    cs:__imp_CloseHandle
0x18002f064  test    eax, eax
0x18002f066  jz      short loc_18002F0B2
0x18002f068  jmp     short loc_18002F08E
0x18002f06a  mov     rcx, rdi; hObject
0x18002f06d  call    cs:__imp_CloseHandle
0x18002f073  test    eax, eax
0x18002f075  jz      short loc_18002F0A0
0x18002f077  movsxd  rcx, [rsp+260h+var_23C]
0x18002f07c  mov     ebx, r15d
0x18002f07f  movsxd  rax, [rsp+260h+var_240]
0x18002f084  shl     rcx, 1Fh
0x18002f088  or      rcx, rax
0x18002f08b  mov     [r14], rcx
0x18002f08e  mov     rcx, rsi; hObject
0x18002f091  call    cs:__imp_CloseHandle
0x18002f097  test    eax, eax
0x18002f099  jz      short loc_18002F0C4
0x18002f09b  jmp     loc_18002EFB5
0x18002f0a0  mov     rcx, [rbp+168h]; this
0x18002f0a7  mov     edx, 9D1h; void *
0x18002f0ac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002f0b2  mov     rcx, [rbp+168h]; this
0x18002f0b9  mov     edx, 9D1h; void *
0x18002f0be  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002f0c4  mov     rcx, [rbp+168h]; this
0x18002f0cb  mov     edx, 9D1h; void *
0x18002f0d0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
