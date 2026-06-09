# CRegKey::GetValueExpSz(ushort const *,ushort * *)

- ea: `0x180022328`
- end: `0x1800224cc`
- name: `?GetValueExpSz@CRegKey@@QEAAKPEBGPEAPEAG@Z`
- size: `420`
- prototype: `unsigned int __fastcall(CRegKey *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18000aa44`

## callees

- `0x18001a9a8`
- `0x18002218c`
- `0x180022328`
- `0x180026694`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180022436`
- `KERNEL32!GetLastError` at `0x18002248a`
- `KERNEL32!GetLastError` at `0x180022436`
- `KERNEL32!GetLastError` at `0x18002248a`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180022428`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002247c`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180022428`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002247c`
- `ADVAPI32!RegQueryValueExW` at `0x18002236a`
- `ADVAPI32!RegQueryValueExW` at `0x1800223aa`
- `ADVAPI32!RegQueryValueExW` at `0x18002236a`
- `ADVAPI32!RegQueryValueExW` at `0x1800223aa`

## string_xrefs

- `0x180022347`: `ProviderDll`
- `0x180022398`: `ProviderDll`
- `0x1800223f5`: `ProviderDll`

## pseudocode

```c
__int64 __fastcall CRegKey::GetValueExpSz(HKEY *this, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  HKEY v5; // rcx
  WCHAR *v6; // rsi
  unsigned int Value; // ebx
  unsigned __int64 v8; // rax
  _WORD *v9; // rdi
  DWORD v10; // eax
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // kr00_8
  WCHAR *v13; // rax
  DWORD v15; // [rsp+60h] [rbp+8h] BYREF
  const unsigned __int16 *cbData; // [rsp+68h] [rbp+10h] BYREF

  cbData = a2;
  *a3 = 0;
  v15 = 0;
  v5 = *this;
  LODWORD(cbData) = 0;
  v6 = 0;
  Value = RegQueryValueExW(v5, L"ProviderDll", 0, &v15, 0, 0);
  if ( Value )
    return Value;
  if ( v15 != 2 )
    return 1804;
  Value = RegQueryValueExW(*this, L"ProviderDll", 0, 0, 0, (LPDWORD)&cbData);
  if ( Value )
    return Value;
  v8 = 2 * ((unsigned __int64)(unsigned int)cbData >> 1);
  if ( !is_mul_ok((unsigned __int64)(unsigned int)cbData >> 1, 2u) )
    v8 = -1;
  v9 = operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v9 )
    return 8;
  Value = CRegKey::GetValue((CRegKey *)this, L"ProviderDll", 2u, v9, (unsigned int)cbData);
  if ( !Value )
  {
    if ( !*v9 )
    {
      *a3 = v9;
      v9 = 0;
LABEL_21:
      if ( v6 )
        operator delete(v6);
      goto LABEL_23;
    }
    v10 = ExpandEnvironmentStringsW(v9, 0, 0);
    LODWORD(cbData) = v10;
    if ( !v10 )
    {
      Value = GetLastError();
      goto LABEL_23;
    }
    v12 = v10;
    v11 = 2LL * v10;
    if ( !is_mul_ok(v12, 2u) )
      v11 = -1;
    v13 = (WCHAR *)operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
    v6 = v13;
    if ( !v13 )
    {
      Value = 8;
      goto LABEL_23;
    }
    LODWORD(cbData) = ExpandEnvironmentStringsW(v9, v13, (DWORD)cbData);
    if ( !(_DWORD)cbData )
    {
      Value = GetLastError();
      goto LABEL_21;
    }
    *a3 = v6;
  }
LABEL_23:
  if ( v9 )
    operator delete(v9);
  return Value;
}

```

## disassembly

```asm
0x180022328  mov     rax, rsp
0x18002232b  mov     [rax+18h], rbx
0x18002232f  mov     [rax+10h], rdx
0x180022333  push    rbp
0x180022334  push    rsi
0x180022335  push    rdi
0x180022336  push    r14
0x180022338  push    r15
0x18002233a  sub     rsp, 30h
0x18002233e  xor     ebp, ebp
0x180022340  lea     r9, [rax+8]; lpType
0x180022344  mov     [r8], rbp
0x180022347  lea     rdx, ValueName; "ProviderDll"
0x18002234e  mov     r14, r8
0x180022351  mov     [rax-30h], rbp
0x180022355  mov     r15, rcx
0x180022358  mov     [rax+8], ebp
0x18002235b  mov     rcx, [rcx]; hKey
0x18002235e  xor     r8d, r8d; lpReserved
0x180022361  mov     [rax+10h], ebp
0x180022364  mov     esi, ebp
0x180022366  mov     [rax-38h], rbp
0x18002236a  call    cs:__imp_RegQueryValueExW
0x180022370  mov     ebx, eax
0x180022372  test    eax, eax
0x180022374  jnz     loc_1800224B9
0x18002237a  cmp     [rsp+58h+arg_0], 2
0x18002237f  jz      short loc_18002238B
0x180022381  mov     ebx, 70Ch
0x180022386  jmp     loc_1800224B9
0x18002238b  mov     rcx, [r15]; hKey
0x18002238e  lea     rax, [rsp+58h+cbData]
0x180022393  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180022398  lea     rdx, ValueName; "ProviderDll"
0x18002239f  xor     r9d, r9d; lpType
0x1800223a2  mov     [rsp+58h+lpData], rbp; lpData
0x1800223a7  xor     r8d, r8d; lpReserved
0x1800223aa  call    cs:__imp_RegQueryValueExW
0x1800223b0  mov     ebx, eax
0x1800223b2  test    eax, eax
0x1800223b4  jnz     loc_1800224B9
0x1800223ba  mov     ecx, dword ptr [rsp+58h+cbData]
0x1800223be  lea     eax, [rbx+2]
0x1800223c1  shr     rcx, 1
0x1800223c4  mul     rcx
0x1800223c7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800223ce  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800223d5  cmovo   rax, rcx
0x1800223d9  mov     rcx, rax; unsigned __int64
0x1800223dc  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800223e1  mov     rdi, rax
0x1800223e4  test    rax, rax
0x1800223e7  jnz     short loc_1800223F1
0x1800223e9  lea     ebx, [rax+8]
0x1800223ec  jmp     loc_1800224B9
0x1800223f1  mov     eax, dword ptr [rsp+58h+cbData]
0x1800223f5  lea     rdx, ValueName; "ProviderDll"
0x1800223fc  mov     r9, rdi; void *
0x1800223ff  mov     dword ptr [rsp+58h+lpData], eax; unsigned int
0x180022403  mov     r8d, 2; unsigned int
0x180022409  mov     rcx, r15; this
0x18002240c  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x180022411  mov     ebx, eax
0x180022413  test    eax, eax
0x180022415  jnz     loc_1800224AC
0x18002241b  cmp     [rdi], bp
0x18002241e  jz      short loc_180022499
0x180022420  xor     r8d, r8d; nSize
0x180022423  xor     edx, edx; lpDst
0x180022425  mov     rcx, rdi; lpSrc
0x180022428  call    cs:__imp_ExpandEnvironmentStringsW
0x18002242e  mov     dword ptr [rsp+58h+cbData], eax
0x180022432  test    eax, eax
0x180022434  jnz     short loc_180022440
0x180022436  call    cs:__imp_GetLastError
0x18002243c  mov     ebx, eax
0x18002243e  jmp     short loc_1800224AC
0x180022440  mov     ecx, eax
0x180022442  mov     eax, 2
0x180022447  mul     rcx
0x18002244a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180022451  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180022458  cmovo   rax, rcx
0x18002245c  mov     rcx, rax; unsigned __int64
0x18002245f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180022464  mov     rsi, rax
0x180022467  test    rax, rax
0x18002246a  jnz     short loc_180022471
0x18002246c  lea     ebx, [rax+8]
0x18002246f  jmp     short loc_1800224AC
0x180022471  mov     r8d, dword ptr [rsp+58h+cbData]; nSize
0x180022476  mov     rdx, rsi; lpDst
0x180022479  mov     rcx, rdi; lpSrc
0x18002247c  call    cs:__imp_ExpandEnvironmentStringsW
0x180022482  mov     dword ptr [rsp+58h+cbData], eax
0x180022486  test    eax, eax
0x180022488  jnz     short loc_180022494
0x18002248a  call    cs:__imp_GetLastError
0x180022490  mov     ebx, eax
0x180022492  jmp     short loc_18002249F
0x180022494  mov     [r14], rsi
0x180022497  jmp     short loc_1800224AC
0x180022499  mov     [r14], rdi
0x18002249c  mov     rdi, rbp
0x18002249f  test    rsi, rsi
0x1800224a2  jz      short loc_1800224AC
0x1800224a4  mov     rcx, rsi; void *
0x1800224a7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800224ac  test    rdi, rdi
0x1800224af  jz      short loc_1800224B9
0x1800224b1  mov     rcx, rdi; void *
0x1800224b4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800224b9  mov     eax, ebx
0x1800224bb  mov     rbx, [rsp+58h+arg_10]
0x1800224c0  add     rsp, 30h
0x1800224c4  pop     r15
0x1800224c6  pop     r14
0x1800224c8  pop     rdi
0x1800224c9  pop     rsi
0x1800224ca  pop     rbp
0x1800224cb  retn
```
