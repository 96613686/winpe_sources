# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000b008`
- end: `0x18000b2c1`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `697`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003b34`
- `0x180003f2c`

## callees

- `0x180006a64`
- `0x1800099e4`
- `0x180009a04`
- `0x18000ab24`
- `0x18000b008`
- `0x18000b828`
- `0x18000d700`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000b0bb`
- `KERNEL32!GetLastError` at `0x18000b0bb`
- `KERNEL32!OpenSemaphoreW` at `0x18000b0a7`
- `KERNEL32!OpenSemaphoreW` at `0x18000b14f`
- `KERNEL32!OpenSemaphoreW` at `0x18000b0a7`
- `KERNEL32!OpenSemaphoreW` at `0x18000b14f`
- `KERNEL32!CloseHandle` at `0x18000b11a`
- `KERNEL32!CloseHandle` at `0x18000b179`
- `KERNEL32!CloseHandle` at `0x18000b1b9`
- `KERNEL32!CloseHandle` at `0x18000b1d0`
- `KERNEL32!CloseHandle` at `0x18000b1eb`
- `KERNEL32!CloseHandle` at `0x18000b216`
- `KERNEL32!CloseHandle` at `0x18000b11a`
- `KERNEL32!CloseHandle` at `0x18000b179`
- `KERNEL32!CloseHandle` at `0x18000b1b9`
- `KERNEL32!CloseHandle` at `0x18000b1d0`
- `KERNEL32!CloseHandle` at `0x18000b1eb`
- `KERNEL32!CloseHandle` at `0x18000b216`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        char *a1,
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
  void *v11; // rbx
  unsigned int v12; // r8d
  const char *v13; // r9
  int ValueFromSemaphore; // eax
  unsigned __int64 v16; // rdx
  unsigned int v17; // r8d
  unsigned int LastError; // edi
  unsigned int v19; // r8d
  const char *v20; // r9
  HANDLE v21; // rax
  unsigned int v22; // r8d
  const char *v23; // r9
  void *v24; // rdi
  unsigned int v25; // r8d
  const char *v26; // r9
  int v27; // eax
  unsigned int v28; // r8d
  unsigned int v29; // esi
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  unsigned int v36; // r8d
  const char *v37; // r9
  int v38; // [rsp+28h] [rbp-E0h] BYREF
  int v39[3]; // [rsp+2Ch] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+38h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+270h] [rbp+168h]

  *a3 = 0;
  v4 = Name;
  v5 = a1 - (char *)Name;
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
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, v12, v13);
    return 0;
  }
  v39[0] = 0;
  v38 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, v39);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD3, v17, (const char *)(unsigned int)ValueFromSemaphore, v38);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v19, v20);
    return LastError;
  }
  StringCchCatW(Name, v16, L"h");
  v21 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v24 = v21;
  if ( !v21 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, v22, v23);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v25, v26);
    return LastError;
  }
  v27 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v21, &v38);
  v29 = v27;
  if ( v27 >= 0 )
  {
    if ( !CloseHandle(v24) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v34, v35);
    *a3 = v39[0] | (unsigned __int64)((__int64)v38 << 31);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v36, v37);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDB, v28, (const char *)(unsigned int)v27, v38);
  if ( !CloseHandle(v24) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v30, v31);
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v32, v33);
  return v29;
}

```

## disassembly

```asm
0x18000b008  mov     rax, rsp
0x18000b00b  mov     [rax+8], rbx
0x18000b00f  mov     [rax+10h], rsi
0x18000b013  mov     [rax+20h], rdi
0x18000b017  push    rbp
0x18000b018  push    r14
0x18000b01a  push    r15
0x18000b01c  lea     rbp, [rax-168h]
0x18000b023  sub     rsp, 250h
0x18000b02a  mov     rax, cs:__security_cookie
0x18000b031  xor     rax, rsp
0x18000b034  mov     [rbp+160h+var_20], rax
0x18000b03b  xor     r15d, r15d
0x18000b03e  lea     rax, [rsp+260h+Name]
0x18000b043  mov     [r8], r15
0x18000b046  lea     rdx, [rsp+260h+Name]
0x18000b04b  sub     rcx, rax
0x18000b04e  mov     r14, r8
0x18000b051  mov     r9d, 104h
0x18000b057  lea     rax, [r9+7FFFFEFAh]
0x18000b05e  test    rax, rax
0x18000b061  jz      short loc_18000B079
0x18000b063  movzx   eax, word ptr [rcx+rdx]
0x18000b067  test    ax, ax
0x18000b06a  jz      short loc_18000B079
0x18000b06c  mov     [rdx], ax
0x18000b06f  add     rdx, 2; unsigned __int64
0x18000b073  sub     r9, 1
0x18000b077  jnz     short loc_18000B057
0x18000b079  test    r9, r9
0x18000b07c  lea     rax, [rdx-2]
0x18000b080  lea     r8, aP0; "_p0"
0x18000b087  cmovnz  rax, rdx
0x18000b08b  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000b090  mov     [rax], r15w
0x18000b094  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b099  mov     esi, 1F0003h
0x18000b09e  lea     r8, [rsp+260h+Name]; lpName
0x18000b0a3  mov     ecx, esi; dwDesiredAccess
0x18000b0a5  xor     edx, edx; bInheritHandle
0x18000b0a7  call    cs:__imp_OpenSemaphoreW
0x18000b0ae  nop     dword ptr [rax+rax+00h]
0x18000b0b3  mov     rbx, rax
0x18000b0b6  test    rax, rax
0x18000b0b9  jnz     short loc_18000B0E6
0x18000b0bb  call    cs:__imp_GetLastError
0x18000b0c2  nop     dword ptr [rax+rax+00h]
0x18000b0c7  cmp     eax, 2
0x18000b0ca  jz      loc_18000B226
0x18000b0d0  mov     rcx, [rbp+168h]; this
0x18000b0d7  mov     edx, 0CDh; void *
0x18000b0dc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b0e1  jmp     loc_18000B228
0x18000b0e6  lea     rdx, [rsp+260h+var_23C]; int *
0x18000b0eb  mov     [rsp+260h+var_23C], r15d
0x18000b0f0  mov     rcx, rbx; hHandle
0x18000b0f3  mov     [rsp+260h+var_240], r15d; int
0x18000b0f8  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b0fd  mov     edi, eax
0x18000b0ff  test    eax, eax
0x18000b101  jns     short loc_18000B135
0x18000b103  mov     rcx, [rbp+168h]; this
0x18000b10a  mov     r9d, eax; char *
0x18000b10d  mov     edx, 0D3h; void *
0x18000b112  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b117  mov     rcx, rbx; hObject
0x18000b11a  call    cs:__imp_CloseHandle
0x18000b121  nop     dword ptr [rax+rax+00h]
0x18000b126  test    eax, eax
0x18000b128  jz      loc_18000B279
0x18000b12e  mov     eax, edi
0x18000b130  jmp     loc_18000B228
0x18000b135  lea     r8, asc_180011420; "h"
0x18000b13c  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000b141  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b146  lea     r8, [rsp+260h+Name]; lpName
0x18000b14b  xor     edx, edx; bInheritHandle
0x18000b14d  mov     ecx, esi; dwDesiredAccess
0x18000b14f  call    cs:__imp_OpenSemaphoreW
0x18000b156  nop     dword ptr [rax+rax+00h]
0x18000b15b  mov     rdi, rax
0x18000b15e  test    rax, rax
0x18000b161  jnz     short loc_18000B18F
0x18000b163  mov     rcx, [rbp+168h]; this
0x18000b16a  mov     edx, 0D9h; void *
0x18000b16f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b174  mov     rcx, rbx; hObject
0x18000b177  mov     edi, eax
0x18000b179  call    cs:__imp_CloseHandle
0x18000b180  nop     dword ptr [rax+rax+00h]
0x18000b185  test    eax, eax
0x18000b187  jz      loc_18000B267
0x18000b18d  jmp     short loc_18000B12E
0x18000b18f  lea     rdx, [rsp+260h+var_240]; int *
0x18000b194  mov     rcx, rdi; hHandle
0x18000b197  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b19c  mov     esi, eax
0x18000b19e  test    eax, eax
0x18000b1a0  jns     short loc_18000B1E8
0x18000b1a2  mov     rcx, [rbp+168h]; this
0x18000b1a9  mov     r9d, eax; char *
0x18000b1ac  mov     edx, 0DBh; void *
0x18000b1b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b1b6  mov     rcx, rdi; hObject
0x18000b1b9  call    cs:__imp_CloseHandle
0x18000b1c0  nop     dword ptr [rax+rax+00h]
0x18000b1c5  test    eax, eax
0x18000b1c7  jz      loc_18000B28B
0x18000b1cd  mov     rcx, rbx; hObject
0x18000b1d0  call    cs:__imp_CloseHandle
0x18000b1d7  nop     dword ptr [rax+rax+00h]
0x18000b1dc  test    eax, eax
0x18000b1de  jz      loc_18000B29D
0x18000b1e4  mov     eax, esi
0x18000b1e6  jmp     short loc_18000B228
0x18000b1e8  mov     rcx, rdi; hObject
0x18000b1eb  call    cs:__imp_CloseHandle
0x18000b1f2  nop     dword ptr [rax+rax+00h]
0x18000b1f7  test    eax, eax
0x18000b1f9  jz      loc_18000B2AF
0x18000b1ff  movsxd  rax, [rsp+260h+var_23C]
0x18000b204  movsxd  rcx, [rsp+260h+var_240]
0x18000b209  shl     rcx, 1Fh
0x18000b20d  or      rcx, rax
0x18000b210  mov     [r14], rcx
0x18000b213  mov     rcx, rbx; hObject
0x18000b216  call    cs:__imp_CloseHandle
0x18000b21d  nop     dword ptr [rax+rax+00h]
0x18000b222  test    eax, eax
0x18000b224  jz      short loc_18000B255
0x18000b226  xor     eax, eax
0x18000b228  mov     rcx, [rbp+160h+var_20]
0x18000b22f  xor     rcx, rsp; StackCookie
0x18000b232  call    __security_check_cookie
0x18000b237  lea     r11, [rsp+260h+var_10]
0x18000b23f  mov     rbx, [r11+20h]
0x18000b243  mov     rsi, [r11+28h]
0x18000b247  mov     rdi, [r11+38h]
0x18000b24b  mov     rsp, r11
0x18000b24e  pop     r15
0x18000b250  pop     r14
0x18000b252  pop     rbp
0x18000b253  retn
0x18000b255  mov     rcx, [rbp+168h]; this
0x18000b25c  mov     edx, 9CDh; void *
0x18000b261  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b267  mov     rcx, [rbp+168h]; this
0x18000b26e  mov     edx, 9CDh; void *
0x18000b273  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b279  mov     rcx, [rbp+168h]; this
0x18000b280  mov     edx, 9CDh; void *
0x18000b285  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b28b  mov     rcx, [rbp+168h]; this
0x18000b292  mov     edx, 9CDh; void *
0x18000b297  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b29d  mov     rcx, [rbp+168h]; this
0x18000b2a4  mov     edx, 9CDh; void *
0x18000b2a9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b2af  mov     rcx, [rbp+168h]; this
0x18000b2b6  mov     edx, 9CDh; void *
0x18000b2bb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
