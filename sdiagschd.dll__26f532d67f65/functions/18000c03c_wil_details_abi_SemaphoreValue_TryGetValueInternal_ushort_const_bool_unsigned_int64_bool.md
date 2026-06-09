# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000c03c`
- end: `0x18000c30b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `719`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180009600`

## callees

- `0x18000a228`
- `0x18000afd4`
- `0x18000aff4`
- `0x18000bf5c`
- `0x18000c03c`
- `0x18000c478`
- `0x18000c860`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x18000c0db`
- `KERNEL32!OpenSemaphoreW` at `0x18000c169`
- `KERNEL32!OpenSemaphoreW` at `0x18000c0db`
- `KERNEL32!OpenSemaphoreW` at `0x18000c169`
- `KERNEL32!CloseHandle` at `0x18000c12d`
- `KERNEL32!CloseHandle` at `0x18000c1b1`
- `KERNEL32!CloseHandle` at `0x18000c1cf`
- `KERNEL32!CloseHandle` at `0x18000c1f4`
- `KERNEL32!CloseHandle` at `0x18000c226`
- `KERNEL32!CloseHandle` at `0x18000c259`
- `KERNEL32!CloseHandle` at `0x18000c12d`
- `KERNEL32!CloseHandle` at `0x18000c1b1`
- `KERNEL32!CloseHandle` at `0x18000c1cf`
- `KERNEL32!CloseHandle` at `0x18000c1f4`
- `KERNEL32!CloseHandle` at `0x18000c226`
- `KERNEL32!CloseHandle` at `0x18000c259`
- `KERNEL32!GetLastError` at `0x18000c275`
- `KERNEL32!GetLastError` at `0x18000c275`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        char *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  __int64 v5; // r9
  WCHAR *v6; // rdx
  signed __int64 v7; // rcx
  WCHAR v8; // ax
  WCHAR *v9; // rax
  HANDLE v10; // rax
  void *v11; // rbx
  int ValueFromSemaphore; // eax
  unsigned __int64 v13; // rdx
  unsigned int v14; // r8d
  unsigned int LastError; // edi
  unsigned int v16; // r8d
  const char *v17; // r9
  HANDLE v19; // rax
  unsigned int v20; // r8d
  const char *v21; // r9
  void *v22; // rdi
  int v23; // eax
  unsigned int v24; // r8d
  unsigned int v25; // esi
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  unsigned int v36; // r8d
  const char *v37; // r9
  int v38[2]; // [rsp+28h] [rbp-E0h] BYREF
  HANDLE v39; // [rsp+30h] [rbp-D8h]
  HANDLE v40; // [rsp+38h] [rbp-D0h]
  WCHAR Name[264]; // [rsp+48h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+280h] [rbp+178h]

  *a3 = 0;
  v5 = 260;
  v6 = Name;
  v7 = a1 - (char *)Name;
  do
  {
    if ( v5 == -2147483386 )
      break;
    v8 = *(WCHAR *)((char *)v6 + v7);
    if ( !v8 )
      break;
    *v6++ = v8;
    --v5;
  }
  while ( v5 );
  v9 = v6 - 1;
  if ( v5 )
    v9 = v6;
  *v9 = 0;
  StringCchCatW(Name, (unsigned __int64)v6, L"_p0");
  v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v11 = v10;
  v39 = v10;
  if ( !v10 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, v36, v37);
    return 0;
  }
  v38[1] = 0;
  v38[0] = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v38[1]);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3,
      v14,
      (const char *)(unsigned int)ValueFromSemaphore,
      v38[0]);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v16, v17);
    return LastError;
  }
  StringCchCatW(Name, v13, L"h");
  v19 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v22 = v19;
  v40 = v19;
  if ( !v19 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, v20, v21);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v34, v35);
    return LastError;
  }
  v23 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, v38);
  v25 = v23;
  if ( v23 >= 0 )
  {
    if ( !CloseHandle(v22) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v30, v31);
    *a3 = ((__int64)v38[0] << 31) | v38[1];
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v32, v33);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDB, v24, (const char *)(unsigned int)v23, v38[0]);
  if ( !CloseHandle(v22) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v26, v27);
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v28, v29);
  return v25;
}

```

## disassembly

```asm
0x18000c03c  mov     rax, rsp
0x18000c03f  mov     [rax+8], rbx
0x18000c043  mov     [rax+10h], rsi
0x18000c047  mov     [rax+20h], rdi
0x18000c04b  push    rbp
0x18000c04c  push    r14
0x18000c04e  push    r15
0x18000c050  lea     rbp, [rax-178h]
0x18000c057  sub     rsp, 260h
0x18000c05e  mov     rax, cs:__security_cookie
0x18000c065  xor     rax, rsp
0x18000c068  mov     [rbp+170h+var_20], rax
0x18000c06f  mov     r14, r8
0x18000c072  xor     r15d, r15d
0x18000c075  mov     [r8], r15
0x18000c078  mov     r9d, 104h
0x18000c07e  lea     rdx, [rsp+270h+Name]
0x18000c083  lea     rax, [rsp+270h+Name]
0x18000c088  sub     rcx, rax
0x18000c08b  lea     rax, [r9+7FFFFEFAh]
0x18000c092  test    rax, rax
0x18000c095  jz      short loc_18000C0AD
0x18000c097  movzx   eax, word ptr [rcx+rdx]
0x18000c09b  test    ax, ax
0x18000c09e  jz      short loc_18000C0AD
0x18000c0a0  mov     [rdx], ax
0x18000c0a3  add     rdx, 2; unsigned __int64
0x18000c0a7  sub     r9, 1
0x18000c0ab  jnz     short loc_18000C08B
0x18000c0ad  lea     rax, [rdx-2]
0x18000c0b1  test    r9, r9
0x18000c0b4  cmovnz  rax, rdx
0x18000c0b8  mov     [rax], r15w
0x18000c0bc  lea     r8, aP0; "_p0"
0x18000c0c3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c0c8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c0cd  lea     r8, [rsp+270h+Name]; lpName
0x18000c0d2  xor     edx, edx; bInheritHandle
0x18000c0d4  mov     esi, 1F0003h
0x18000c0d9  mov     ecx, esi; dwDesiredAccess
0x18000c0db  call    cs:__imp_OpenSemaphoreW
0x18000c0e2  nop     dword ptr [rax+rax+00h]
0x18000c0e7  mov     rbx, rax
0x18000c0ea  mov     [rsp+270h+var_248], rax
0x18000c0ef  test    rax, rax
0x18000c0f2  jz      loc_18000C275
0x18000c0f8  mov     [rsp+270h+var_250+4], r15d
0x18000c0fd  mov     [rsp+270h+var_250], r15d; int
0x18000c102  lea     rdx, [rsp+270h+var_250+4]; int *
0x18000c107  mov     rcx, rax; hHandle
0x18000c10a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c10f  mov     edi, eax
0x18000c111  test    eax, eax
0x18000c113  jns     short loc_18000C14F
0x18000c115  mov     rcx, [rbp+178h]; this
0x18000c11c  mov     r9d, eax; char *
0x18000c11f  mov     edx, 0D3h; void *
0x18000c124  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c129  nop
0x18000c12a  mov     rcx, rbx; hObject
0x18000c12d  call    cs:__imp_CloseHandle
0x18000c134  nop     dword ptr [rax+rax+00h]
0x18000c139  mov     rcx, [rbp+178h]; this
0x18000c140  test    eax, eax
0x18000c142  jz      loc_18000C2DF
0x18000c148  mov     eax, edi
0x18000c14a  jmp     loc_18000C29C
0x18000c14f  lea     r8, asc_180011490; "h"
0x18000c156  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c15b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c160  lea     r8, [rsp+270h+Name]; lpName
0x18000c165  xor     edx, edx; bInheritHandle
0x18000c167  mov     ecx, esi; dwDesiredAccess
0x18000c169  call    cs:__imp_OpenSemaphoreW
0x18000c170  nop     dword ptr [rax+rax+00h]
0x18000c175  mov     rdi, rax
0x18000c178  mov     [rsp+270h+var_240], rax
0x18000c17d  test    rax, rax
0x18000c180  jz      loc_18000C243
0x18000c186  lea     rdx, [rsp+270h+var_250]; int *
0x18000c18b  mov     rcx, rax; hHandle
0x18000c18e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c193  mov     esi, eax
0x18000c195  test    eax, eax
0x18000c197  jns     short loc_18000C1F1
0x18000c199  mov     rcx, [rbp+178h]; this
0x18000c1a0  mov     r9d, eax; char *
0x18000c1a3  mov     edx, 0DBh; void *
0x18000c1a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c1ad  nop
0x18000c1ae  mov     rcx, rdi; hObject
0x18000c1b1  call    cs:__imp_CloseHandle
0x18000c1b8  nop     dword ptr [rax+rax+00h]
0x18000c1bd  mov     rcx, [rbp+178h]; this
0x18000c1c4  test    eax, eax
0x18000c1c6  jz      loc_18000C2EA
0x18000c1cc  mov     rcx, rbx; hObject
0x18000c1cf  call    cs:__imp_CloseHandle
0x18000c1d6  nop     dword ptr [rax+rax+00h]
0x18000c1db  mov     rcx, [rbp+178h]; this
0x18000c1e2  test    eax, eax
0x18000c1e4  jz      loc_18000C2F5
0x18000c1ea  mov     eax, esi
0x18000c1ec  jmp     loc_18000C29C
0x18000c1f1  mov     rcx, rdi; hObject
0x18000c1f4  call    cs:__imp_CloseHandle
0x18000c1fb  nop     dword ptr [rax+rax+00h]
0x18000c200  mov     rcx, [rbp+178h]; this
0x18000c207  test    eax, eax
0x18000c209  jz      loc_18000C300
0x18000c20f  movsxd  rcx, [rsp+270h+var_250]
0x18000c214  shl     rcx, 1Fh
0x18000c218  movsxd  rax, [rsp+270h+var_250+4]
0x18000c21d  or      rax, rcx
0x18000c220  mov     [r14], rax
0x18000c223  mov     rcx, rbx; hObject
0x18000c226  call    cs:__imp_CloseHandle
0x18000c22d  nop     dword ptr [rax+rax+00h]
0x18000c232  mov     rcx, [rbp+178h]; this
0x18000c239  test    eax, eax
0x18000c23b  jz      loc_18000C2D4
0x18000c241  jmp     short loc_18000C286
0x18000c243  mov     rcx, [rbp+178h]; this
0x18000c24a  mov     edx, 0D9h; void *
0x18000c24f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c254  mov     edi, eax
0x18000c256  mov     rcx, rbx; hObject
0x18000c259  call    cs:__imp_CloseHandle
0x18000c260  nop     dword ptr [rax+rax+00h]
0x18000c265  mov     rcx, [rbp+178h]; this
0x18000c26c  test    eax, eax
0x18000c26e  jz      short loc_18000C2C9
0x18000c270  jmp     loc_18000C148
0x18000c275  call    cs:__imp_GetLastError
0x18000c27c  nop     dword ptr [rax+rax+00h]
0x18000c281  cmp     eax, 2
0x18000c284  jnz     short loc_18000C28A
0x18000c286  xor     eax, eax
0x18000c288  jmp     short loc_18000C29C
0x18000c28a  mov     rcx, [rbp+178h]; this
0x18000c291  mov     edx, 0CDh; void *
0x18000c296  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c29b  nop
0x18000c29c  mov     rcx, [rbp+170h+var_20]
0x18000c2a3  xor     rcx, rsp; StackCookie
0x18000c2a6  call    __security_check_cookie
0x18000c2ab  lea     r11, [rsp+270h+var_10]
0x18000c2b3  mov     rbx, [r11+20h]
0x18000c2b7  mov     rsi, [r11+28h]
0x18000c2bb  mov     rdi, [r11+38h]
0x18000c2bf  mov     rsp, r11
0x18000c2c2  pop     r15
0x18000c2c4  pop     r14
0x18000c2c6  pop     rbp
0x18000c2c7  retn
0x18000c2c9  mov     edx, 9DDh; void *
0x18000c2ce  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c2d4  mov     edx, 9DDh; void *
0x18000c2d9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c2df  mov     edx, 9DDh; void *
0x18000c2e4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c2ea  mov     edx, 9DDh; void *
0x18000c2ef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c2f5  mov     edx, 9DDh; void *
0x18000c2fa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c300  mov     edx, 9DDh; void *
0x18000c305  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
