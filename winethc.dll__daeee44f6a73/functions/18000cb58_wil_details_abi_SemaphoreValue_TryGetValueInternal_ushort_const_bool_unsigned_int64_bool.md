# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000cb58`
- end: `0x18000ce02`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `682`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003548`

## callees

- `0x180007e18`
- `0x18000c304`
- `0x18000c324`
- `0x18000c8e8`
- `0x18000cb58`
- `0x18000d7c4`
- `0x180012db0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000cd50`
- `KERNEL32!GetLastError` at `0x18000cd50`
- `KERNEL32!CloseHandle` at `0x18000cc38`
- `KERNEL32!CloseHandle` at `0x18000ccaf`
- `KERNEL32!CloseHandle` at `0x18000ccc6`
- `KERNEL32!CloseHandle` at `0x18000cce4`
- `KERNEL32!CloseHandle` at `0x18000cd0f`
- `KERNEL32!CloseHandle` at `0x18000cd3b`
- `KERNEL32!CloseHandle` at `0x18000cc38`
- `KERNEL32!CloseHandle` at `0x18000ccaf`
- `KERNEL32!CloseHandle` at `0x18000ccc6`
- `KERNEL32!CloseHandle` at `0x18000cce4`
- `KERNEL32!CloseHandle` at `0x18000cd0f`
- `KERNEL32!CloseHandle` at `0x18000cd3b`
- `KERNEL32!OpenSemaphoreW` at `0x18000cbec`
- `KERNEL32!OpenSemaphoreW` at `0x18000cc6d`
- `KERNEL32!OpenSemaphoreW` at `0x18000cbec`
- `KERNEL32!OpenSemaphoreW` at `0x18000cc6d`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  unsigned int v13; // r8d
  unsigned int LastError; // edi
  unsigned int v15; // r8d
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  unsigned int v23; // r8d
  unsigned int v24; // esi
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  unsigned int v35; // r8d
  const char *v36; // r9
  int v37; // [rsp+20h] [rbp-E0h] BYREF
  int v38[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v6 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v6;
  }
  while ( v6 );
  v8 = v4 - 1;
  if ( v6 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, v6, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v35, v36);
    return 0;
  }
  v38[0] = 0;
  v37 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v38);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore, v37);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v15, v16);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v18 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v18;
  if ( !v18 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v19, v20);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return LastError;
  }
  v22 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v37);
  v24 = v22;
  if ( v22 >= 0 )
  {
    if ( !CloseHandle(v21) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    *a3 = v38[0] | (unsigned __int64)((__int64)v37 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22, v37);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x18000cb58  push    rbp
0x18000cb5a  push    rbx
0x18000cb5b  push    rsi
0x18000cb5c  push    rdi
0x18000cb5d  push    r14
0x18000cb5f  push    r15
0x18000cb61  lea     rbp, [rsp-158h]
0x18000cb69  sub     rsp, 258h
0x18000cb70  mov     rax, cs:__security_cookie
0x18000cb77  xor     rax, rsp
0x18000cb7a  mov     [rbp+180h+var_40], rax
0x18000cb81  xor     r15d, r15d
0x18000cb84  lea     rax, [rsp+280h+Name]
0x18000cb89  mov     [r8], r15
0x18000cb8c  mov     r14, r8
0x18000cb8f  mov     edx, 104h
0x18000cb94  mov     r9d, 7FFFFFFEh
0x18000cb9a  test    r9, r9
0x18000cb9d  jz      short loc_18000CBBE
0x18000cb9f  movzx   r8d, word ptr [rcx]
0x18000cba3  test    r8w, r8w
0x18000cba7  jz      short loc_18000CBBE
0x18000cba9  mov     [rax], r8w
0x18000cbad  add     rcx, 2
0x18000cbb1  add     rax, 2
0x18000cbb5  dec     r9
0x18000cbb8  sub     rdx, 1; unsigned __int64
0x18000cbbc  jnz     short loc_18000CB9A
0x18000cbbe  test    rdx, rdx
0x18000cbc1  lea     rcx, [rax-2]
0x18000cbc5  lea     r8, aP0; "_p0"
0x18000cbcc  cmovnz  rcx, rax
0x18000cbd0  mov     [rcx], r15w
0x18000cbd4  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000cbd9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cbde  mov     esi, 1F0003h
0x18000cbe3  lea     r8, [rsp+280h+Name]; lpName
0x18000cbe8  mov     ecx, esi; dwDesiredAccess
0x18000cbea  xor     edx, edx; bInheritHandle
0x18000cbec  call    cs:__imp_OpenSemaphoreW
0x18000cbf3  nop     dword ptr [rax+rax+00h]
0x18000cbf8  mov     rbx, rax
0x18000cbfb  test    rax, rax
0x18000cbfe  jz      loc_18000CD50
0x18000cc04  lea     rdx, [rsp+280h+var_25C]; int *
0x18000cc09  mov     [rsp+280h+var_25C], r15d
0x18000cc0e  mov     rcx, rax; hHandle
0x18000cc11  mov     [rsp+280h+var_260], r15d; int
0x18000cc16  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000cc1b  mov     edi, eax
0x18000cc1d  test    eax, eax
0x18000cc1f  jns     short loc_18000CC53
0x18000cc21  mov     rcx, [rbp+188h]; this
0x18000cc28  mov     r9d, eax; char *
0x18000cc2b  mov     edx, 0D6h; void *
0x18000cc30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cc35  mov     rcx, rbx; hObject
0x18000cc38  call    cs:__imp_CloseHandle
0x18000cc3f  nop     dword ptr [rax+rax+00h]
0x18000cc44  test    eax, eax
0x18000cc46  jz      loc_18000CDCC
0x18000cc4c  mov     eax, edi
0x18000cc4e  jmp     loc_18000CD76
0x18000cc53  lea     r8, asc_1800162E0; "h"
0x18000cc5a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000cc5f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cc64  lea     r8, [rsp+280h+Name]; lpName
0x18000cc69  xor     edx, edx; bInheritHandle
0x18000cc6b  mov     ecx, esi; dwDesiredAccess
0x18000cc6d  call    cs:__imp_OpenSemaphoreW
0x18000cc74  nop     dword ptr [rax+rax+00h]
0x18000cc79  mov     rdi, rax
0x18000cc7c  test    rax, rax
0x18000cc7f  jz      loc_18000CD25
0x18000cc85  lea     rdx, [rsp+280h+var_260]; int *
0x18000cc8a  mov     rcx, rax; hHandle
0x18000cc8d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000cc92  mov     esi, eax
0x18000cc94  test    eax, eax
0x18000cc96  jns     short loc_18000CCE1
0x18000cc98  mov     rcx, [rbp+188h]; this
0x18000cc9f  mov     r9d, eax; char *
0x18000cca2  mov     edx, 0DEh; void *
0x18000cca7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ccac  mov     rcx, rdi; hObject
0x18000ccaf  call    cs:__imp_CloseHandle
0x18000ccb6  nop     dword ptr [rax+rax+00h]
0x18000ccbb  test    eax, eax
0x18000ccbd  jz      loc_18000CDDE
0x18000ccc3  mov     rcx, rbx; hObject
0x18000ccc6  call    cs:__imp_CloseHandle
0x18000cccd  nop     dword ptr [rax+rax+00h]
0x18000ccd2  test    eax, eax
0x18000ccd4  jz      loc_18000CDF0
0x18000ccda  mov     eax, esi
0x18000ccdc  jmp     loc_18000CD76
0x18000cce1  mov     rcx, rdi; hObject
0x18000cce4  call    cs:__imp_CloseHandle
0x18000cceb  nop     dword ptr [rax+rax+00h]
0x18000ccf0  test    eax, eax
0x18000ccf2  jz      loc_18000CD96
0x18000ccf8  movsxd  rax, [rsp+280h+var_25C]
0x18000ccfd  movsxd  rcx, [rsp+280h+var_260]
0x18000cd02  shl     rcx, 1Fh
0x18000cd06  or      rcx, rax
0x18000cd09  mov     [r14], rcx
0x18000cd0c  mov     rcx, rbx; hObject
0x18000cd0f  call    cs:__imp_CloseHandle
0x18000cd16  nop     dword ptr [rax+rax+00h]
0x18000cd1b  test    eax, eax
0x18000cd1d  jz      loc_18000CDA8
0x18000cd23  jmp     short loc_18000CD61
0x18000cd25  mov     rcx, [rbp+188h]; this
0x18000cd2c  mov     edx, 0DCh; void *
0x18000cd31  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000cd36  mov     rcx, rbx; hObject
0x18000cd39  mov     edi, eax
0x18000cd3b  call    cs:__imp_CloseHandle
0x18000cd42  nop     dword ptr [rax+rax+00h]
0x18000cd47  test    eax, eax
0x18000cd49  jz      short loc_18000CDBA
0x18000cd4b  jmp     loc_18000CC4C
0x18000cd50  call    cs:__imp_GetLastError
0x18000cd57  nop     dword ptr [rax+rax+00h]
0x18000cd5c  cmp     eax, 2
0x18000cd5f  jnz     short loc_18000CD65
0x18000cd61  xor     eax, eax
0x18000cd63  jmp     short loc_18000CD76
0x18000cd65  mov     rcx, [rbp+188h]; this
0x18000cd6c  mov     edx, 0D0h; void *
0x18000cd71  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000cd76  mov     rcx, [rbp+180h+var_40]
0x18000cd7d  xor     rcx, rsp; StackCookie
0x18000cd80  call    __security_check_cookie
0x18000cd85  add     rsp, 258h
0x18000cd8c  pop     r15
0x18000cd8e  pop     r14
0x18000cd90  pop     rdi
0x18000cd91  pop     rsi
0x18000cd92  pop     rbx
0x18000cd93  pop     rbp
0x18000cd94  retn
0x18000cd96  mov     rcx, [rbp+188h]; this
0x18000cd9d  mov     edx, 0A0Bh; void *
0x18000cda2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000cda8  mov     rcx, [rbp+188h]; this
0x18000cdaf  mov     edx, 0A0Bh; void *
0x18000cdb4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000cdba  mov     rcx, [rbp+188h]; this
0x18000cdc1  mov     edx, 0A0Bh; void *
0x18000cdc6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000cdcc  mov     rcx, [rbp+188h]; this
0x18000cdd3  mov     edx, 0A0Bh; void *
0x18000cdd8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000cdde  mov     rcx, [rbp+188h]; this
0x18000cde5  mov     edx, 0A0Bh; void *
0x18000cdea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000cdf0  mov     rcx, [rbp+188h]; this
0x18000cdf7  mov     edx, 0A0Bh; void *
0x18000cdfc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
