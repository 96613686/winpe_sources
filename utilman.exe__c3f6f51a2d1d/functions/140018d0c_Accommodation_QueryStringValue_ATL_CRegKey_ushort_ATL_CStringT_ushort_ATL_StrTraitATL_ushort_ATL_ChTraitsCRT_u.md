# Accommodation::QueryStringValue(ATL::CRegKey &,ushort *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x140018d0c`
- end: `0x140018ed1`
- name: `?QueryStringValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z`
- size: `453`
- prototype: `__int64 __fastcall(ATL::CRegKey *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140018ac8`

## callees

- `0x140002480`
- `0x140002714`
- `0x14000347c`
- `0x14000ecdc`
- `0x140013d84`
- `0x1400171ec`
- `0x140018d0c`

## import_xrefs

- `ADVAPI32!RegLoadMUIStringW` at `0x140018e41`
- `ADVAPI32!RegLoadMUIStringW` at `0x140018e41`

## pseudocode

```c
__int64 __fastcall Accommodation::QueryStringValue(ATL::CRegKey *this, unsigned __int16 *a2, char **a3)
{
  __int64 v6; // r14
  _WORD *v7; // rdi
  __int64 v8; // r8
  unsigned int v10; // [rsp+40h] [rbp-888h] BYREF
  _WORD *v11; // [rsp+48h] [rbp-880h]
  ATL::CRegKey *v12; // [rsp+50h] [rbp-878h]
  unsigned __int16 *v13; // [rsp+58h] [rbp-870h]
  char **v14; // [rsp+60h] [rbp-868h]
  WCHAR pszOutBuf[1036]; // [rsp+70h] [rbp-858h] BYREF

  v12 = this;
  v13 = a2;
  v14 = a3;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    a3,
    &byte_14002C58F);
  v10 = 0;
  if ( (unsigned int)ATL::CRegKey::QueryStringValue(this, a2, 0, &v10) || !v10 )
    return 1;
  v6 = -1;
  v7 = operator new[](saturated_mul(v10, 2u));
  v11 = v7;
  *v7 = 0;
  if ( !(unsigned int)ATL::CRegKey::QueryStringValue(this, a2, v7, &v10) && v10 )
  {
    if ( v10 > 0x400 )
      v7[1023] = 0;
    v8 = -1;
    do
      ++v8;
    while ( v7[v8] );
    ATL::CSimpleStringT<unsigned short,0>::SetString(a3, v7, v8);
  }
  if ( *v7 == 64 )
  {
    if ( RegLoadMUIStringW(*(HKEY *)this, a2, pszOutBuf, 0x400u, 0, 1u, 0) )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        a3,
        &byte_14002C58F);
    }
    else
    {
      pszOutBuf[1023] = 0;
      do
        ++v6;
      while ( pszOutBuf[v6] );
      ATL::CSimpleStringT<unsigned short,0>::SetString(a3, pszOutBuf, v6);
    }
  }
  operator delete(v7);
  return 1;
}

```

## disassembly

```asm
0x140018d0c  push    rbx
0x140018d0e  push    rsi
0x140018d0f  push    rdi
0x140018d10  push    r12
0x140018d12  push    r13
0x140018d14  push    r14
0x140018d16  push    r15
0x140018d18  sub     rsp, 890h
0x140018d1f  mov     rax, cs:__security_cookie
0x140018d26  xor     rax, rsp
0x140018d29  mov     [rsp+8C8h+var_40], rax
0x140018d31  mov     rsi, r8
0x140018d34  mov     r12, rdx
0x140018d37  mov     r15, rcx
0x140018d3a  mov     [rsp+8C8h+var_878], rcx
0x140018d3f  mov     [rsp+8C8h+var_870], rdx
0x140018d44  mov     [rsp+8C8h+var_868], r8
0x140018d49  lea     rdx, byte_14002C58F
0x140018d50  mov     rcx, r8
0x140018d53  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x140018d58  nop
0x140018d59  xor     ebx, ebx
0x140018d5b  mov     [rsp+8C8h+var_888], ebx
0x140018d5f  lea     r9, [rsp+8C8h+var_888]; unsigned int *
0x140018d64  xor     r8d, r8d; unsigned __int16 *
0x140018d67  mov     rdx, r12; unsigned __int16 *
0x140018d6a  mov     rcx, r15; this
0x140018d6d  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x140018d72  test    eax, eax
0x140018d74  jnz     loc_140018EA4
0x140018d7a  cmp     [rsp+8C8h+var_888], ebx
0x140018d7e  jz      loc_140018EA4
0x140018d84  lea     r13d, [rbx+1]
0x140018d88  mov     ecx, [rsp+8C8h+var_888]
0x140018d8c  lea     eax, [rbx+2]
0x140018d8f  mul     rcx
0x140018d92  lea     r14, [rbx-1]
0x140018d96  cmovb   rax, r14
0x140018d9a  mov     rcx, rax; unsigned __int64
0x140018d9d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140018da2  mov     rdi, rax
0x140018da5  mov     [rsp+8C8h+var_880], rax
0x140018daa  mov     [rax], bx
0x140018dad  lea     r9, [rsp+8C8h+var_888]; unsigned int *
0x140018db2  mov     r8, rax; unsigned __int16 *
0x140018db5  mov     rdx, r12; unsigned __int16 *
0x140018db8  mov     rcx, r15; this
0x140018dbb  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x140018dc0  test    eax, eax
0x140018dc2  jnz     short loc_140018E13
0x140018dc4  cmp     [rsp+8C8h+var_888], ebx
0x140018dc8  jbe     short loc_140018E13
0x140018dca  cmp     [rsp+8C8h+var_888], 400h
0x140018dd2  jbe     short loc_140018DDB
0x140018dd4  mov     [rdi+7FEh], bx
0x140018ddb  mov     r8, r14
0x140018dde  inc     r8
0x140018de1  cmp     [rdi+r8*2], bx
0x140018de6  jnz     short loc_140018DDE
0x140018de8  mov     rdx, rdi
0x140018deb  mov     rcx, rsi
0x140018dee  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140018df3  nop
0x140018df4  jmp     short loc_140018E13
0x140018df6  xor     ebx, ebx
0x140018df8  or      r14, 0FFFFFFFFFFFFFFFFh
0x140018dfc  mov     r13d, ebx
0x140018dff  mov     rdi, [rsp+8C8h+var_880]
0x140018e04  mov     r15, [rsp+8C8h+var_878]
0x140018e09  mov     r12, [rsp+8C8h+var_870]
0x140018e0e  mov     rsi, [rsp+8C8h+var_868]
0x140018e13  cmp     word ptr [rdi], 40h ; '@'
0x140018e17  jnz     short loc_140018E97
0x140018e19  test    r13d, r13d
0x140018e1c  jz      short loc_140018E97
0x140018e1e  mov     [rsp+8C8h+pszDirectory], rbx; pszDirectory
0x140018e23  mov     [rsp+8C8h+Flags], 1; Flags
0x140018e2b  mov     [rsp+8C8h+pcbData], rbx; pcbData
0x140018e30  mov     r9d, 400h; cbOutBuf
0x140018e36  lea     r8, [rsp+8C8h+pszOutBuf]; pszOutBuf
0x140018e3b  mov     rdx, r12; pszValue
0x140018e3e  mov     rcx, [r15]; hKey
0x140018e41  call    cs:__imp_RegLoadMUIStringW
0x140018e48  nop     dword ptr [rax+rax+00h]
0x140018e4d  nop
0x140018e4e  test    eax, eax
0x140018e50  jnz     short loc_140018E7B
0x140018e52  mov     [rsp+8C8h+var_5A], bx
0x140018e5a  lea     rax, [rsp+8C8h+pszOutBuf]
0x140018e5f  inc     r14
0x140018e62  cmp     [rax+r14*2], bx
0x140018e67  jnz     short loc_140018E5F
0x140018e69  mov     r8d, r14d
0x140018e6c  lea     rdx, [rsp+8C8h+pszOutBuf]
0x140018e71  mov     rcx, rsi
0x140018e74  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140018e79  jmp     short loc_140018E8B
0x140018e7b  lea     rdx, byte_14002C58F
0x140018e82  mov     rcx, rsi
0x140018e85  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x140018e8a  nop
0x140018e8b  jmp     short loc_140018E97
0x140018e8d  mov     r13d, [rsp+8C8h+var_888]
0x140018e92  mov     rdi, [rsp+8C8h+var_880]
0x140018e97  mov     rcx, rdi; Block
0x140018e9a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140018e9f  mov     eax, r13d
0x140018ea2  jmp     short loc_140018EAD
0x140018ea4  mov     eax, 1
0x140018ea9  jmp     short loc_140018EAD
0x140018eab  xor     eax, eax
0x140018ead  mov     rcx, [rsp+8C8h+var_40]
0x140018eb5  xor     rcx, rsp; StackCookie
0x140018eb8  call    __security_check_cookie
0x140018ebd  add     rsp, 890h
0x140018ec4  pop     r15
0x140018ec6  pop     r14
0x140018ec8  pop     r13
0x140018eca  pop     r12
0x140018ecc  pop     rdi
0x140018ecd  pop     rsi
0x140018ece  pop     rbx
0x140018ecf  retn
```
