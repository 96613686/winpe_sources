# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000dd90`
- end: `0x18000e052`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `706`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180009c54`
- `0x18000a04c`

## callees

- `0x18000b530`
- `0x18000d2a8`
- `0x18000d2c8`
- `0x18000d888`
- `0x18000dd90`
- `0x18000e5b8`
- `0x180030390`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000de46`
- `KERNEL32!GetLastError` at `0x18000de46`
- `KERNEL32!CloseHandle` at `0x18000dea5`
- `KERNEL32!CloseHandle` at `0x18000df0a`
- `KERNEL32!CloseHandle` at `0x18000df4a`
- `KERNEL32!CloseHandle` at `0x18000df61`
- `KERNEL32!CloseHandle` at `0x18000df7c`
- `KERNEL32!CloseHandle` at `0x18000dfa7`
- `KERNEL32!CloseHandle` at `0x18000dea5`
- `KERNEL32!CloseHandle` at `0x18000df0a`
- `KERNEL32!CloseHandle` at `0x18000df4a`
- `KERNEL32!CloseHandle` at `0x18000df61`
- `KERNEL32!CloseHandle` at `0x18000df7c`
- `KERNEL32!CloseHandle` at `0x18000dfa7`
- `KERNEL32!OpenSemaphoreW` at `0x18000de32`
- `KERNEL32!OpenSemaphoreW` at `0x18000dee0`
- `KERNEL32!OpenSemaphoreW` at `0x18000de32`
- `KERNEL32!OpenSemaphoreW` at `0x18000dee0`

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
0x18000dd90  mov     rax, rsp
0x18000dd93  mov     [rax+8], rbx
0x18000dd97  mov     [rax+10h], rsi
0x18000dd9b  mov     [rax+20h], rdi
0x18000dd9f  push    rbp
0x18000dda0  push    r14
0x18000dda2  push    r15
0x18000dda4  lea     rbp, [rax-168h]
0x18000ddab  sub     rsp, 250h
0x18000ddb2  mov     rax, cs:__security_cookie
0x18000ddb9  xor     rax, rsp
0x18000ddbc  mov     [rbp+160h+var_20], rax
0x18000ddc3  xor     r15d, r15d
0x18000ddc6  lea     rax, [rsp+260h+Name]
0x18000ddcb  mov     esi, 104h
0x18000ddd0  mov     [r8], r15
0x18000ddd3  mov     r9d, esi
0x18000ddd6  lea     rdx, [rsp+260h+Name]
0x18000dddb  sub     rcx, rax
0x18000ddde  mov     r14, r8
0x18000dde1  lea     rax, [r9+7FFFFEFAh]
0x18000dde8  test    rax, rax
0x18000ddeb  jz      short loc_18000DE03
0x18000dded  movzx   eax, word ptr [rcx+rdx]
0x18000ddf1  test    ax, ax
0x18000ddf4  jz      short loc_18000DE03
0x18000ddf6  mov     [rdx], ax
0x18000ddf9  add     rdx, 2
0x18000ddfd  sub     r9, 1
0x18000de01  jnz     short loc_18000DDE1
0x18000de03  lea     rax, [rdx-2]
0x18000de07  test    r9, r9
0x18000de0a  lea     r8, aP0; "_p0"
0x18000de11  cmovnz  rax, rdx
0x18000de15  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000de1a  mov     rdx, rsi; unsigned __int64
0x18000de1d  mov     [rax], r15w
0x18000de21  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000de26  lea     r8, [rsp+260h+Name]; lpName
0x18000de2b  xor     edx, edx; bInheritHandle
0x18000de2d  mov     ecx, 1F0003h; dwDesiredAccess
0x18000de32  call    cs:__imp_OpenSemaphoreW
0x18000de39  nop     dword ptr [rax+rax+00h]
0x18000de3e  mov     rbx, rax
0x18000de41  test    rax, rax
0x18000de44  jnz     short loc_18000DE71
0x18000de46  call    cs:__imp_GetLastError
0x18000de4d  nop     dword ptr [rax+rax+00h]
0x18000de52  cmp     eax, 2
0x18000de55  jz      loc_18000DFB7
0x18000de5b  mov     rcx, [rbp+168h]; this
0x18000de62  mov     edx, 0CDh; void *
0x18000de67  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000de6c  jmp     loc_18000DFB9
0x18000de71  lea     rdx, [rsp+260h+var_23C]; int *
0x18000de76  mov     [rsp+260h+var_23C], r15d
0x18000de7b  mov     rcx, rbx; hHandle
0x18000de7e  mov     [rsp+260h+var_240], r15d; int
0x18000de83  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000de88  mov     edi, eax
0x18000de8a  test    eax, eax
0x18000de8c  jns     short loc_18000DEC0
0x18000de8e  mov     rcx, [rbp+168h]; this
0x18000de95  mov     r9d, eax; char *
0x18000de98  mov     edx, 0D3h; void *
0x18000de9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dea2  mov     rcx, rbx; hObject
0x18000dea5  call    cs:__imp_CloseHandle
0x18000deac  nop     dword ptr [rax+rax+00h]
0x18000deb1  test    eax, eax
0x18000deb3  jz      loc_18000E00A
0x18000deb9  mov     eax, edi
0x18000debb  jmp     loc_18000DFB9
0x18000dec0  lea     r8, asc_180035DC8; "h"
0x18000dec7  mov     rdx, rsi; unsigned __int64
0x18000deca  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000decf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ded4  lea     r8, [rsp+260h+Name]; lpName
0x18000ded9  xor     edx, edx; bInheritHandle
0x18000dedb  mov     ecx, 1F0003h; dwDesiredAccess
0x18000dee0  call    cs:__imp_OpenSemaphoreW
0x18000dee7  nop     dword ptr [rax+rax+00h]
0x18000deec  mov     rdi, rax
0x18000deef  test    rax, rax
0x18000def2  jnz     short loc_18000DF20
0x18000def4  mov     rcx, [rbp+168h]; this
0x18000defb  mov     edx, 0D9h; void *
0x18000df00  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000df05  mov     rcx, rbx; hObject
0x18000df08  mov     edi, eax
0x18000df0a  call    cs:__imp_CloseHandle
0x18000df11  nop     dword ptr [rax+rax+00h]
0x18000df16  test    eax, eax
0x18000df18  jz      loc_18000DFF8
0x18000df1e  jmp     short loc_18000DEB9
0x18000df20  lea     rdx, [rsp+260h+var_240]; int *
0x18000df25  mov     rcx, rdi; hHandle
0x18000df28  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000df2d  mov     esi, eax
0x18000df2f  test    eax, eax
0x18000df31  jns     short loc_18000DF79
0x18000df33  mov     rcx, [rbp+168h]; this
0x18000df3a  mov     r9d, eax; char *
0x18000df3d  mov     edx, 0DBh; void *
0x18000df42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000df47  mov     rcx, rdi; hObject
0x18000df4a  call    cs:__imp_CloseHandle
0x18000df51  nop     dword ptr [rax+rax+00h]
0x18000df56  test    eax, eax
0x18000df58  jz      loc_18000E01C
0x18000df5e  mov     rcx, rbx; hObject
0x18000df61  call    cs:__imp_CloseHandle
0x18000df68  nop     dword ptr [rax+rax+00h]
0x18000df6d  test    eax, eax
0x18000df6f  jz      loc_18000E02E
0x18000df75  mov     eax, esi
0x18000df77  jmp     short loc_18000DFB9
0x18000df79  mov     rcx, rdi; hObject
0x18000df7c  call    cs:__imp_CloseHandle
0x18000df83  nop     dword ptr [rax+rax+00h]
0x18000df88  test    eax, eax
0x18000df8a  jz      loc_18000E040
0x18000df90  movsxd  rax, [rsp+260h+var_23C]
0x18000df95  movsxd  rcx, [rsp+260h+var_240]
0x18000df9a  shl     rcx, 1Fh
0x18000df9e  or      rcx, rax
0x18000dfa1  mov     [r14], rcx
0x18000dfa4  mov     rcx, rbx; hObject
0x18000dfa7  call    cs:__imp_CloseHandle
0x18000dfae  nop     dword ptr [rax+rax+00h]
0x18000dfb3  test    eax, eax
0x18000dfb5  jz      short loc_18000DFE6
0x18000dfb7  xor     eax, eax
0x18000dfb9  mov     rcx, [rbp+160h+var_20]
0x18000dfc0  xor     rcx, rsp; StackCookie
0x18000dfc3  call    __security_check_cookie
0x18000dfc8  lea     r11, [rsp+260h+var_10]
0x18000dfd0  mov     rbx, [r11+20h]
0x18000dfd4  mov     rsi, [r11+28h]
0x18000dfd8  mov     rdi, [r11+38h]
0x18000dfdc  mov     rsp, r11
0x18000dfdf  pop     r15
0x18000dfe1  pop     r14
0x18000dfe3  pop     rbp
0x18000dfe4  retn
0x18000dfe6  mov     rcx, [rbp+168h]; this
0x18000dfed  mov     edx, 9CDh; void *
0x18000dff2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000dff8  mov     rcx, [rbp+168h]; this
0x18000dfff  mov     edx, 9CDh; void *
0x18000e004  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e00a  mov     rcx, [rbp+168h]; this
0x18000e011  mov     edx, 9CDh; void *
0x18000e016  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e01c  mov     rcx, [rbp+168h]; this
0x18000e023  mov     edx, 9CDh; void *
0x18000e028  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e02e  mov     rcx, [rbp+168h]; this
0x18000e035  mov     edx, 9CDh; void *
0x18000e03a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e040  mov     rcx, [rbp+168h]; this
0x18000e047  mov     edx, 9CDh; void *
0x18000e04c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
