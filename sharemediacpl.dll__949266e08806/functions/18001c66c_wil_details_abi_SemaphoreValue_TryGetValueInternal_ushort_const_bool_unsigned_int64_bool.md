# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001c66c`
- end: `0x18001c8e1`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `629`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180019cb8`

## callees

- `0x180001d60`
- `0x1800187c0`
- `0x18001af10`
- `0x18001c2c0`
- `0x18001c2e0`
- `0x18001c66c`
- `0x18001cb98`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001c749`
- `KERNEL32!CloseHandle` at `0x18001c7ba`
- `KERNEL32!CloseHandle` at `0x18001c7cb`
- `KERNEL32!CloseHandle` at `0x18001c7e0`
- `KERNEL32!CloseHandle` at `0x18001c805`
- `KERNEL32!CloseHandle` at `0x18001c827`
- `KERNEL32!CloseHandle` at `0x18001c749`
- `KERNEL32!CloseHandle` at `0x18001c7ba`
- `KERNEL32!CloseHandle` at `0x18001c7cb`
- `KERNEL32!CloseHandle` at `0x18001c7e0`
- `KERNEL32!CloseHandle` at `0x18001c805`
- `KERNEL32!CloseHandle` at `0x18001c827`
- `KERNEL32!OpenSemaphoreW` at `0x18001c703`
- `KERNEL32!OpenSemaphoreW` at `0x18001c77e`
- `KERNEL32!OpenSemaphoreW` at `0x18001c703`
- `KERNEL32!OpenSemaphoreW` at `0x18001c77e`
- `KERNEL32!GetLastError` at `0x18001c836`
- `KERNEL32!GetLastError` at `0x18001c836`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned int v12; // r8d
  unsigned int LastError; // edi
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // r8d
  unsigned int v23; // esi
  unsigned int v24; // r8d
  const char *v25; // r9
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
  int v36; // [rsp+20h] [rbp-E0h] BYREF
  int v37[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v5 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v5;
  }
  while ( v5 );
  v8 = v4 - 1;
  if ( v5 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v34, v35);
    return 0;
  }
  v37[0] = 0;
  v36 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v37);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v36);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v36);
  v23 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    *a3 = v37[0] | (unsigned __int64)((__int64)v36 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v22, (const char *)(unsigned int)v21, v36);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
  return v23;
}

```

## disassembly

```asm
0x18001c66c  push    rbp
0x18001c66e  push    rbx
0x18001c66f  push    rsi
0x18001c670  push    rdi
0x18001c671  push    r14
0x18001c673  push    r15
0x18001c675  lea     rbp, [rsp-158h]
0x18001c67d  sub     rsp, 258h
0x18001c684  mov     rax, cs:__security_cookie
0x18001c68b  xor     rax, rsp
0x18001c68e  mov     [rbp+180h+var_40], rax
0x18001c695  xor     r15d, r15d
0x18001c698  lea     rax, [rsp+280h+Name]
0x18001c69d  mov     esi, 104h
0x18001c6a2  mov     [r8], r15
0x18001c6a5  mov     edx, esi
0x18001c6a7  mov     r14, r8
0x18001c6aa  mov     r9d, 7FFFFFFEh
0x18001c6b0  test    r9, r9
0x18001c6b3  jz      short loc_18001C6D4
0x18001c6b5  movzx   r8d, word ptr [rcx]
0x18001c6b9  test    r8w, r8w
0x18001c6bd  jz      short loc_18001C6D4
0x18001c6bf  mov     [rax], r8w
0x18001c6c3  add     rcx, 2
0x18001c6c7  add     rax, 2
0x18001c6cb  dec     r9
0x18001c6ce  sub     rdx, 1
0x18001c6d2  jnz     short loc_18001C6B0
0x18001c6d4  test    rdx, rdx
0x18001c6d7  lea     rcx, [rax-2]
0x18001c6db  lea     r8, aP0; "_p0"
0x18001c6e2  mov     rdx, rsi; unsigned __int64
0x18001c6e5  cmovnz  rcx, rax
0x18001c6e9  mov     [rcx], r15w
0x18001c6ed  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001c6f2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001c6f7  lea     r8, [rsp+280h+Name]; lpName
0x18001c6fc  xor     edx, edx; bInheritHandle
0x18001c6fe  mov     ecx, 1F0003h; dwDesiredAccess
0x18001c703  call    cs:__imp_OpenSemaphoreW
0x18001c709  mov     rbx, rax
0x18001c70c  test    rax, rax
0x18001c70f  jz      loc_18001C836
0x18001c715  lea     rdx, [rsp+280h+var_25C]; int *
0x18001c71a  mov     [rsp+280h+var_25C], r15d
0x18001c71f  mov     rcx, rax; hHandle
0x18001c722  mov     [rsp+280h+var_260], r15d; int
0x18001c727  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001c72c  mov     edi, eax
0x18001c72e  test    eax, eax
0x18001c730  jns     short loc_18001C75E
0x18001c732  mov     rcx, [rbp+188h]; this
0x18001c739  mov     r9d, eax; char *
0x18001c73c  mov     edx, 0D6h; void *
0x18001c741  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c746  mov     rcx, rbx; hObject
0x18001c749  call    cs:__imp_CloseHandle
0x18001c74f  test    eax, eax
0x18001c751  jz      loc_18001C8AB
0x18001c757  mov     eax, edi
0x18001c759  jmp     loc_18001C856
0x18001c75e  lea     r8, asc_180023B30; "h"
0x18001c765  mov     rdx, rsi; unsigned __int64
0x18001c768  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001c76d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001c772  lea     r8, [rsp+280h+Name]; lpName
0x18001c777  xor     edx, edx; bInheritHandle
0x18001c779  mov     ecx, 1F0003h; dwDesiredAccess
0x18001c77e  call    cs:__imp_OpenSemaphoreW
0x18001c784  mov     rdi, rax
0x18001c787  test    rax, rax
0x18001c78a  jz      loc_18001C811
0x18001c790  lea     rdx, [rsp+280h+var_260]; int *
0x18001c795  mov     rcx, rax; hHandle
0x18001c798  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001c79d  mov     esi, eax
0x18001c79f  test    eax, eax
0x18001c7a1  jns     short loc_18001C7DD
0x18001c7a3  mov     rcx, [rbp+188h]; this
0x18001c7aa  mov     r9d, eax; char *
0x18001c7ad  mov     edx, 0DEh; void *
0x18001c7b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c7b7  mov     rcx, rdi; hObject
0x18001c7ba  call    cs:__imp_CloseHandle
0x18001c7c0  test    eax, eax
0x18001c7c2  jz      loc_18001C8BD
0x18001c7c8  mov     rcx, rbx; hObject
0x18001c7cb  call    cs:__imp_CloseHandle
0x18001c7d1  test    eax, eax
0x18001c7d3  jz      loc_18001C8CF
0x18001c7d9  mov     eax, esi
0x18001c7db  jmp     short loc_18001C856
0x18001c7dd  mov     rcx, rdi; hObject
0x18001c7e0  call    cs:__imp_CloseHandle
0x18001c7e6  test    eax, eax
0x18001c7e8  jz      loc_18001C875
0x18001c7ee  movsxd  rax, [rsp+280h+var_25C]
0x18001c7f3  movsxd  rcx, [rsp+280h+var_260]
0x18001c7f8  shl     rcx, 1Fh
0x18001c7fc  or      rcx, rax
0x18001c7ff  mov     [r14], rcx
0x18001c802  mov     rcx, rbx; hObject
0x18001c805  call    cs:__imp_CloseHandle
0x18001c80b  test    eax, eax
0x18001c80d  jz      short loc_18001C887
0x18001c80f  jmp     short loc_18001C841
0x18001c811  mov     rcx, [rbp+188h]; this
0x18001c818  mov     edx, 0DCh; void *
0x18001c81d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001c822  mov     rcx, rbx; hObject
0x18001c825  mov     edi, eax
0x18001c827  call    cs:__imp_CloseHandle
0x18001c82d  test    eax, eax
0x18001c82f  jz      short loc_18001C899
0x18001c831  jmp     loc_18001C757
0x18001c836  call    cs:__imp_GetLastError
0x18001c83c  cmp     eax, 2
0x18001c83f  jnz     short loc_18001C845
0x18001c841  xor     eax, eax
0x18001c843  jmp     short loc_18001C856
0x18001c845  mov     rcx, [rbp+188h]; this
0x18001c84c  mov     edx, 0D0h; void *
0x18001c851  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001c856  mov     rcx, [rbp+180h+var_40]
0x18001c85d  xor     rcx, rsp; StackCookie
0x18001c860  call    __security_check_cookie
0x18001c865  add     rsp, 258h
0x18001c86c  pop     r15
0x18001c86e  pop     r14
0x18001c870  pop     rdi
0x18001c871  pop     rsi
0x18001c872  pop     rbx
0x18001c873  pop     rbp
0x18001c874  retn
0x18001c875  mov     rcx, [rbp+188h]; this
0x18001c87c  mov     edx, 0A0Bh; void *
0x18001c881  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001c887  mov     rcx, [rbp+188h]; this
0x18001c88e  mov     edx, 0A0Bh; void *
0x18001c893  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001c899  mov     rcx, [rbp+188h]; this
0x18001c8a0  mov     edx, 0A0Bh; void *
0x18001c8a5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001c8ab  mov     rcx, [rbp+188h]; this
0x18001c8b2  mov     edx, 0A0Bh; void *
0x18001c8b7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001c8bd  mov     rcx, [rbp+188h]; this
0x18001c8c4  mov     edx, 0A0Bh; void *
0x18001c8c9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001c8cf  mov     rcx, [rbp+188h]; this
0x18001c8d6  mov     edx, 0A0Bh; void *
0x18001c8db  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
