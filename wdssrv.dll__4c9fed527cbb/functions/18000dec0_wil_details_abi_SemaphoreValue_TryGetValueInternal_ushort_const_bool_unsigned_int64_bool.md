# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000dec0`
- end: `0x18000e179`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `697`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000794c`
- `0x180007d44`

## callees

- `0x180009994`
- `0x18000caec`
- `0x18000cb0c`
- `0x18000d934`
- `0x18000dec0`
- `0x18000eac4`
- `0x18001c150`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000df73`
- `KERNEL32!GetLastError` at `0x18000df73`
- `KERNEL32!CloseHandle` at `0x18000dfd2`
- `KERNEL32!CloseHandle` at `0x18000e031`
- `KERNEL32!CloseHandle` at `0x18000e071`
- `KERNEL32!CloseHandle` at `0x18000e088`
- `KERNEL32!CloseHandle` at `0x18000e0a3`
- `KERNEL32!CloseHandle` at `0x18000e0ce`
- `KERNEL32!CloseHandle` at `0x18000dfd2`
- `KERNEL32!CloseHandle` at `0x18000e031`
- `KERNEL32!CloseHandle` at `0x18000e071`
- `KERNEL32!CloseHandle` at `0x18000e088`
- `KERNEL32!CloseHandle` at `0x18000e0a3`
- `KERNEL32!CloseHandle` at `0x18000e0ce`
- `KERNEL32!OpenSemaphoreW` at `0x18000df5f`
- `KERNEL32!OpenSemaphoreW` at `0x18000e007`
- `KERNEL32!OpenSemaphoreW` at `0x18000df5f`
- `KERNEL32!OpenSemaphoreW` at `0x18000e007`

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
0x18000dec0  mov     rax, rsp
0x18000dec3  mov     [rax+8], rbx
0x18000dec7  mov     [rax+10h], rsi
0x18000decb  mov     [rax+20h], rdi
0x18000decf  push    rbp
0x18000ded0  push    r14
0x18000ded2  push    r15
0x18000ded4  lea     rbp, [rax-168h]
0x18000dedb  sub     rsp, 250h
0x18000dee2  mov     rax, cs:__security_cookie
0x18000dee9  xor     rax, rsp
0x18000deec  mov     [rbp+160h+var_20], rax
0x18000def3  xor     r15d, r15d
0x18000def6  lea     rax, [rsp+260h+Name]
0x18000defb  mov     [r8], r15
0x18000defe  lea     rdx, [rsp+260h+Name]
0x18000df03  sub     rcx, rax
0x18000df06  mov     r14, r8
0x18000df09  mov     r9d, 104h
0x18000df0f  lea     rax, [r9+7FFFFEFAh]
0x18000df16  test    rax, rax
0x18000df19  jz      short loc_18000DF31
0x18000df1b  movzx   eax, word ptr [rcx+rdx]
0x18000df1f  test    ax, ax
0x18000df22  jz      short loc_18000DF31
0x18000df24  mov     [rdx], ax
0x18000df27  add     rdx, 2; unsigned __int64
0x18000df2b  sub     r9, 1
0x18000df2f  jnz     short loc_18000DF0F
0x18000df31  test    r9, r9
0x18000df34  lea     rax, [rdx-2]
0x18000df38  lea     r8, aP0; "_p0"
0x18000df3f  cmovnz  rax, rdx
0x18000df43  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000df48  mov     [rax], r15w
0x18000df4c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000df51  mov     esi, 1F0003h
0x18000df56  lea     r8, [rsp+260h+Name]; lpName
0x18000df5b  mov     ecx, esi; dwDesiredAccess
0x18000df5d  xor     edx, edx; bInheritHandle
0x18000df5f  call    cs:__imp_OpenSemaphoreW
0x18000df66  nop     dword ptr [rax+rax+00h]
0x18000df6b  mov     rbx, rax
0x18000df6e  test    rax, rax
0x18000df71  jnz     short loc_18000DF9E
0x18000df73  call    cs:__imp_GetLastError
0x18000df7a  nop     dword ptr [rax+rax+00h]
0x18000df7f  cmp     eax, 2
0x18000df82  jz      loc_18000E0DE
0x18000df88  mov     rcx, [rbp+168h]; this
0x18000df8f  mov     edx, 0CDh; void *
0x18000df94  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000df99  jmp     loc_18000E0E0
0x18000df9e  lea     rdx, [rsp+260h+var_23C]; int *
0x18000dfa3  mov     [rsp+260h+var_23C], r15d
0x18000dfa8  mov     rcx, rbx; hHandle
0x18000dfab  mov     [rsp+260h+var_240], r15d; int
0x18000dfb0  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000dfb5  mov     edi, eax
0x18000dfb7  test    eax, eax
0x18000dfb9  jns     short loc_18000DFED
0x18000dfbb  mov     rcx, [rbp+168h]; this
0x18000dfc2  mov     r9d, eax; char *
0x18000dfc5  mov     edx, 0D3h; void *
0x18000dfca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dfcf  mov     rcx, rbx; hObject
0x18000dfd2  call    cs:__imp_CloseHandle
0x18000dfd9  nop     dword ptr [rax+rax+00h]
0x18000dfde  test    eax, eax
0x18000dfe0  jz      loc_18000E131
0x18000dfe6  mov     eax, edi
0x18000dfe8  jmp     loc_18000E0E0
0x18000dfed  lea     r8, asc_180020AB8; "h"
0x18000dff4  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000dff9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000dffe  lea     r8, [rsp+260h+Name]; lpName
0x18000e003  xor     edx, edx; bInheritHandle
0x18000e005  mov     ecx, esi; dwDesiredAccess
0x18000e007  call    cs:__imp_OpenSemaphoreW
0x18000e00e  nop     dword ptr [rax+rax+00h]
0x18000e013  mov     rdi, rax
0x18000e016  test    rax, rax
0x18000e019  jnz     short loc_18000E047
0x18000e01b  mov     rcx, [rbp+168h]; this
0x18000e022  mov     edx, 0D9h; void *
0x18000e027  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e02c  mov     rcx, rbx; hObject
0x18000e02f  mov     edi, eax
0x18000e031  call    cs:__imp_CloseHandle
0x18000e038  nop     dword ptr [rax+rax+00h]
0x18000e03d  test    eax, eax
0x18000e03f  jz      loc_18000E11F
0x18000e045  jmp     short loc_18000DFE6
0x18000e047  lea     rdx, [rsp+260h+var_240]; int *
0x18000e04c  mov     rcx, rdi; hHandle
0x18000e04f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000e054  mov     esi, eax
0x18000e056  test    eax, eax
0x18000e058  jns     short loc_18000E0A0
0x18000e05a  mov     rcx, [rbp+168h]; this
0x18000e061  mov     r9d, eax; char *
0x18000e064  mov     edx, 0DBh; void *
0x18000e069  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e06e  mov     rcx, rdi; hObject
0x18000e071  call    cs:__imp_CloseHandle
0x18000e078  nop     dword ptr [rax+rax+00h]
0x18000e07d  test    eax, eax
0x18000e07f  jz      loc_18000E143
0x18000e085  mov     rcx, rbx; hObject
0x18000e088  call    cs:__imp_CloseHandle
0x18000e08f  nop     dword ptr [rax+rax+00h]
0x18000e094  test    eax, eax
0x18000e096  jz      loc_18000E155
0x18000e09c  mov     eax, esi
0x18000e09e  jmp     short loc_18000E0E0
0x18000e0a0  mov     rcx, rdi; hObject
0x18000e0a3  call    cs:__imp_CloseHandle
0x18000e0aa  nop     dword ptr [rax+rax+00h]
0x18000e0af  test    eax, eax
0x18000e0b1  jz      loc_18000E167
0x18000e0b7  movsxd  rax, [rsp+260h+var_23C]
0x18000e0bc  movsxd  rcx, [rsp+260h+var_240]
0x18000e0c1  shl     rcx, 1Fh
0x18000e0c5  or      rcx, rax
0x18000e0c8  mov     [r14], rcx
0x18000e0cb  mov     rcx, rbx; hObject
0x18000e0ce  call    cs:__imp_CloseHandle
0x18000e0d5  nop     dword ptr [rax+rax+00h]
0x18000e0da  test    eax, eax
0x18000e0dc  jz      short loc_18000E10D
0x18000e0de  xor     eax, eax
0x18000e0e0  mov     rcx, [rbp+160h+var_20]
0x18000e0e7  xor     rcx, rsp; StackCookie
0x18000e0ea  call    __security_check_cookie
0x18000e0ef  lea     r11, [rsp+260h+var_10]
0x18000e0f7  mov     rbx, [r11+20h]
0x18000e0fb  mov     rsi, [r11+28h]
0x18000e0ff  mov     rdi, [r11+38h]
0x18000e103  mov     rsp, r11
0x18000e106  pop     r15
0x18000e108  pop     r14
0x18000e10a  pop     rbp
0x18000e10b  retn
0x18000e10d  mov     rcx, [rbp+168h]; this
0x18000e114  mov     edx, 9CDh; void *
0x18000e119  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e11f  mov     rcx, [rbp+168h]; this
0x18000e126  mov     edx, 9CDh; void *
0x18000e12b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e131  mov     rcx, [rbp+168h]; this
0x18000e138  mov     edx, 9CDh; void *
0x18000e13d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e143  mov     rcx, [rbp+168h]; this
0x18000e14a  mov     edx, 9CDh; void *
0x18000e14f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e155  mov     rcx, [rbp+168h]; this
0x18000e15c  mov     edx, 9CDh; void *
0x18000e161  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e167  mov     rcx, [rbp+168h]; this
0x18000e16e  mov     edx, 9CDh; void *
0x18000e173  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
