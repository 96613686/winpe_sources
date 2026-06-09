# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000d250`
- end: `0x18000d512`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `706`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180009110`
- `0x180009508`

## callees

- `0x18000a9f0`
- `0x18000c768`
- `0x18000c788`
- `0x18000cd48`
- `0x18000d250`
- `0x18000da78`
- `0x18002f3e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d306`
- `KERNEL32!GetLastError` at `0x18000d306`
- `KERNEL32!CloseHandle` at `0x18000d365`
- `KERNEL32!CloseHandle` at `0x18000d3ca`
- `KERNEL32!CloseHandle` at `0x18000d40a`
- `KERNEL32!CloseHandle` at `0x18000d421`
- `KERNEL32!CloseHandle` at `0x18000d43c`
- `KERNEL32!CloseHandle` at `0x18000d467`
- `KERNEL32!CloseHandle` at `0x18000d365`
- `KERNEL32!CloseHandle` at `0x18000d3ca`
- `KERNEL32!CloseHandle` at `0x18000d40a`
- `KERNEL32!CloseHandle` at `0x18000d421`
- `KERNEL32!CloseHandle` at `0x18000d43c`
- `KERNEL32!CloseHandle` at `0x18000d467`
- `KERNEL32!OpenSemaphoreW` at `0x18000d2f2`
- `KERNEL32!OpenSemaphoreW` at `0x18000d3a0`
- `KERNEL32!OpenSemaphoreW` at `0x18000d2f2`
- `KERNEL32!OpenSemaphoreW` at `0x18000d3a0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        char *a1,
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
  void *v11; // rbx
  unsigned int v12; // r8d
  const char *v13; // r9
  int ValueFromSemaphore; // eax
  unsigned int v16; // r8d
  unsigned int LastError; // edi
  unsigned int v18; // r8d
  const char *v19; // r9
  HANDLE v20; // rax
  unsigned int v21; // r8d
  const char *v22; // r9
  void *v23; // rdi
  unsigned int v24; // r8d
  const char *v25; // r9
  int v26; // eax
  unsigned int v27; // r8d
  unsigned int v28; // esi
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  unsigned int v35; // r8d
  const char *v36; // r9
  int v37; // [rsp+28h] [rbp-E0h] BYREF
  int v38[3]; // [rsp+2Ch] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+38h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+270h] [rbp+168h]

  *a3 = 0;
  v4 = 260;
  v5 = Name;
  v6 = a1 - (char *)Name;
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
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, v12, v13);
    return 0;
  }
  v38[0] = 0;
  v37 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, v38);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD3, v16, (const char *)(unsigned int)ValueFromSemaphore, v37);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v18, v19);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v20 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v23 = v20;
  if ( !v20 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, v21, v22);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v24, v25);
    return LastError;
  }
  v26 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v20, &v37);
  v28 = v26;
  if ( v26 >= 0 )
  {
    if ( !CloseHandle(v23) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v33, v34);
    *a3 = v38[0] | (unsigned __int64)((__int64)v37 << 31);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v35, v36);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDB, v27, (const char *)(unsigned int)v26, v37);
  if ( !CloseHandle(v23) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v29, v30);
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v31, v32);
  return v28;
}

```

## disassembly

```asm
0x18000d250  mov     rax, rsp
0x18000d253  mov     [rax+8], rbx
0x18000d257  mov     [rax+10h], rsi
0x18000d25b  mov     [rax+20h], rdi
0x18000d25f  push    rbp
0x18000d260  push    r14
0x18000d262  push    r15
0x18000d264  lea     rbp, [rax-168h]
0x18000d26b  sub     rsp, 250h
0x18000d272  mov     rax, cs:__security_cookie
0x18000d279  xor     rax, rsp
0x18000d27c  mov     [rbp+160h+var_20], rax
0x18000d283  xor     r15d, r15d
0x18000d286  lea     rax, [rsp+260h+Name]
0x18000d28b  mov     esi, 104h
0x18000d290  mov     [r8], r15
0x18000d293  mov     r9d, esi
0x18000d296  lea     rdx, [rsp+260h+Name]
0x18000d29b  sub     rcx, rax
0x18000d29e  mov     r14, r8
0x18000d2a1  lea     rax, [r9+7FFFFEFAh]
0x18000d2a8  test    rax, rax
0x18000d2ab  jz      short loc_18000D2C3
0x18000d2ad  movzx   eax, word ptr [rcx+rdx]
0x18000d2b1  test    ax, ax
0x18000d2b4  jz      short loc_18000D2C3
0x18000d2b6  mov     [rdx], ax
0x18000d2b9  add     rdx, 2
0x18000d2bd  sub     r9, 1
0x18000d2c1  jnz     short loc_18000D2A1
0x18000d2c3  lea     rax, [rdx-2]
0x18000d2c7  test    r9, r9
0x18000d2ca  lea     r8, aP0; "_p0"
0x18000d2d1  cmovnz  rax, rdx
0x18000d2d5  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000d2da  mov     rdx, rsi; unsigned __int64
0x18000d2dd  mov     [rax], r15w
0x18000d2e1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d2e6  lea     r8, [rsp+260h+Name]; lpName
0x18000d2eb  xor     edx, edx; bInheritHandle
0x18000d2ed  mov     ecx, 1F0003h; dwDesiredAccess
0x18000d2f2  call    cs:__imp_OpenSemaphoreW
0x18000d2f9  nop     dword ptr [rax+rax+00h]
0x18000d2fe  mov     rbx, rax
0x18000d301  test    rax, rax
0x18000d304  jnz     short loc_18000D331
0x18000d306  call    cs:__imp_GetLastError
0x18000d30d  nop     dword ptr [rax+rax+00h]
0x18000d312  cmp     eax, 2
0x18000d315  jz      loc_18000D477
0x18000d31b  mov     rcx, [rbp+168h]; this
0x18000d322  mov     edx, 0CDh; void *
0x18000d327  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000d32c  jmp     loc_18000D479
0x18000d331  lea     rdx, [rsp+260h+var_23C]; int *
0x18000d336  mov     [rsp+260h+var_23C], r15d
0x18000d33b  mov     rcx, rbx; hHandle
0x18000d33e  mov     [rsp+260h+var_240], r15d; int
0x18000d343  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000d348  mov     edi, eax
0x18000d34a  test    eax, eax
0x18000d34c  jns     short loc_18000D380
0x18000d34e  mov     rcx, [rbp+168h]; this
0x18000d355  mov     r9d, eax; char *
0x18000d358  mov     edx, 0D3h; void *
0x18000d35d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d362  mov     rcx, rbx; hObject
0x18000d365  call    cs:__imp_CloseHandle
0x18000d36c  nop     dword ptr [rax+rax+00h]
0x18000d371  test    eax, eax
0x18000d373  jz      loc_18000D4CA
0x18000d379  mov     eax, edi
0x18000d37b  jmp     loc_18000D479
0x18000d380  lea     r8, asc_180033858; "h"
0x18000d387  mov     rdx, rsi; unsigned __int64
0x18000d38a  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000d38f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d394  lea     r8, [rsp+260h+Name]; lpName
0x18000d399  xor     edx, edx; bInheritHandle
0x18000d39b  mov     ecx, 1F0003h; dwDesiredAccess
0x18000d3a0  call    cs:__imp_OpenSemaphoreW
0x18000d3a7  nop     dword ptr [rax+rax+00h]
0x18000d3ac  mov     rdi, rax
0x18000d3af  test    rax, rax
0x18000d3b2  jnz     short loc_18000D3E0
0x18000d3b4  mov     rcx, [rbp+168h]; this
0x18000d3bb  mov     edx, 0D9h; void *
0x18000d3c0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000d3c5  mov     rcx, rbx; hObject
0x18000d3c8  mov     edi, eax
0x18000d3ca  call    cs:__imp_CloseHandle
0x18000d3d1  nop     dword ptr [rax+rax+00h]
0x18000d3d6  test    eax, eax
0x18000d3d8  jz      loc_18000D4B8
0x18000d3de  jmp     short loc_18000D379
0x18000d3e0  lea     rdx, [rsp+260h+var_240]; int *
0x18000d3e5  mov     rcx, rdi; hHandle
0x18000d3e8  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000d3ed  mov     esi, eax
0x18000d3ef  test    eax, eax
0x18000d3f1  jns     short loc_18000D439
0x18000d3f3  mov     rcx, [rbp+168h]; this
0x18000d3fa  mov     r9d, eax; char *
0x18000d3fd  mov     edx, 0DBh; void *
0x18000d402  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d407  mov     rcx, rdi; hObject
0x18000d40a  call    cs:__imp_CloseHandle
0x18000d411  nop     dword ptr [rax+rax+00h]
0x18000d416  test    eax, eax
0x18000d418  jz      loc_18000D4DC
0x18000d41e  mov     rcx, rbx; hObject
0x18000d421  call    cs:__imp_CloseHandle
0x18000d428  nop     dword ptr [rax+rax+00h]
0x18000d42d  test    eax, eax
0x18000d42f  jz      loc_18000D4EE
0x18000d435  mov     eax, esi
0x18000d437  jmp     short loc_18000D479
0x18000d439  mov     rcx, rdi; hObject
0x18000d43c  call    cs:__imp_CloseHandle
0x18000d443  nop     dword ptr [rax+rax+00h]
0x18000d448  test    eax, eax
0x18000d44a  jz      loc_18000D500
0x18000d450  movsxd  rax, [rsp+260h+var_23C]
0x18000d455  movsxd  rcx, [rsp+260h+var_240]
0x18000d45a  shl     rcx, 1Fh
0x18000d45e  or      rcx, rax
0x18000d461  mov     [r14], rcx
0x18000d464  mov     rcx, rbx; hObject
0x18000d467  call    cs:__imp_CloseHandle
0x18000d46e  nop     dword ptr [rax+rax+00h]
0x18000d473  test    eax, eax
0x18000d475  jz      short loc_18000D4A6
0x18000d477  xor     eax, eax
0x18000d479  mov     rcx, [rbp+160h+var_20]
0x18000d480  xor     rcx, rsp; StackCookie
0x18000d483  call    __security_check_cookie
0x18000d488  lea     r11, [rsp+260h+var_10]
0x18000d490  mov     rbx, [r11+20h]
0x18000d494  mov     rsi, [r11+28h]
0x18000d498  mov     rdi, [r11+38h]
0x18000d49c  mov     rsp, r11
0x18000d49f  pop     r15
0x18000d4a1  pop     r14
0x18000d4a3  pop     rbp
0x18000d4a4  retn
0x18000d4a6  mov     rcx, [rbp+168h]; this
0x18000d4ad  mov     edx, 9CDh; void *
0x18000d4b2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d4b8  mov     rcx, [rbp+168h]; this
0x18000d4bf  mov     edx, 9CDh; void *
0x18000d4c4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d4ca  mov     rcx, [rbp+168h]; this
0x18000d4d1  mov     edx, 9CDh; void *
0x18000d4d6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d4dc  mov     rcx, [rbp+168h]; this
0x18000d4e3  mov     edx, 9CDh; void *
0x18000d4e8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d4ee  mov     rcx, [rbp+168h]; this
0x18000d4f5  mov     edx, 9CDh; void *
0x18000d4fa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d500  mov     rcx, [rbp+168h]; this
0x18000d507  mov     edx, 9CDh; void *
0x18000d50c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
