# SIPolicyQueryOneSecurityPolicy

- ea: `0x18001bfb4`
- end: `0x18001c207`
- name: `SIPolicyQueryOneSecurityPolicy`
- size: `595`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ba48`
- `0x18003aa48`

## callees

- `0x18001bfb4`
- `0x1800229b0`
- `0x1800229f8`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x18001bfff`
- `ntdll!RtlEqualUnicodeString` at `0x18001c016`
- `ntdll!RtlEqualUnicodeString` at `0x18001bfff`
- `ntdll!RtlEqualUnicodeString` at `0x18001c016`

## pseudocode

```c
__int64 __fastcall SIPolicyQueryOneSecurityPolicy(
        __int64 a1,
        const UNICODE_STRING *a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5,
        _BYTE *a6,
        unsigned int *a7)
{
  int v8; // eax
  __int128 v9; // rdi
  unsigned int v11; // ebx
  size_t v12; // r8
  const void *v13; // rdx
  size_t v14; // r8
  const void *v15; // rdx
  size_t v16; // r8
  const void *v17; // rdx
  int v18; // edx
  __int64 v19; // rdx
  int v20; // eax
  size_t v21; // rdx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  __int128 Key; // [rsp+30h] [rbp-28h] BYREF
  __int128 v27; // [rsp+40h] [rbp-18h]

  v8 = *(_DWORD *)(a1 + 768) & 1;
  *((_QWORD *)&v9 + 1) = a3;
  *(_QWORD *)&v9 = a2;
  Key = 0;
  v27 = 0;
  if ( !(_BYTE)v8
    && RtlEqualUnicodeString(a2, &stru_180043120, 1u)
    && RtlEqualUnicodeString(*((PCUNICODE_STRING *)&v9 + 1), &stru_180043150, 1u) )
  {
    return (unsigned int)-1073741275;
  }
  v12 = *(unsigned int *)(a1 + 688);
  v13 = *(const void **)(a1 + 696);
  Key = v9;
  *(_QWORD *)&v27 = a4;
  *(_QWORD *)&v9 = bsearch(
                     &Key,
                     v13,
                     v12,
                     0x48u,
                     (_CoreCrtNonSecureSearchSortCompareFunction)SIPolicySecureSettingSearchCompare);
  if ( !(_QWORD)v9 )
  {
    v14 = *(unsigned int *)(a1 + 688);
    v15 = *(const void **)(a1 + 696);
    *(_QWORD *)&v27 = a4;
    *((_QWORD *)&Key + 1) = &g_AnyFileWildCardString;
    *(_QWORD *)&v9 = bsearch(
                       &Key,
                       v15,
                       v14,
                       0x48u,
                       (_CoreCrtNonSecureSearchSortCompareFunction)SIPolicySecureSettingSearchCompare);
    if ( !(_QWORD)v9 )
    {
      v16 = *(unsigned int *)(a1 + 688);
      v17 = *(const void **)(a1 + 696);
      *((_QWORD *)&Key + 1) = *((_QWORD *)&v9 + 1);
      *(_QWORD *)&v27 = &g_AnyFileWildCardString;
      *(_QWORD *)&v9 = bsearch(
                         &Key,
                         v17,
                         v16,
                         0x48u,
                         (_CoreCrtNonSecureSearchSortCompareFunction)SIPolicySecureSettingSearchCompare);
      if ( !(_QWORD)v9 )
        return (unsigned int)-1073741275;
    }
  }
  v18 = *(_DWORD *)v9;
  v11 = 0;
  switch ( *(_DWORD *)v9 )
  {
    case 0:
      *a5 = 0;
      if ( !a6 )
      {
        *a7 = 1;
        return v11;
      }
      v24 = *a7;
      *a7 = 1;
      if ( v24 )
      {
        *a6 = *(_BYTE *)(v9 + 56);
        return v11;
      }
      return (unsigned int)-1073741789;
    case 1:
      *a5 = v18;
      if ( !a6 )
      {
        *a7 = 4;
        return v11;
      }
      v23 = *a7;
      *a7 = 4;
      if ( v23 >= 4 )
      {
        *(_DWORD *)a6 = *(_DWORD *)(v9 + 56);
        return v11;
      }
      return (unsigned int)-1073741789;
    case 2:
      *a5 = v18;
      v21 = *(unsigned int *)(v9 + 56);
      if ( !a6 )
      {
        *a7 = v21;
        return v11;
      }
      v22 = *a7;
      *a7 = v21;
      if ( v22 >= (unsigned int)v21 )
      {
        memcpy_0(a6, *(const void **)(v9 + 64), v21);
        return v11;
      }
      return (unsigned int)-1073741789;
    case 3:
      *a5 = v18;
      v19 = *(unsigned __int16 *)(v9 + 56);
      if ( a6 )
      {
        *((_QWORD *)&v9 + 1) = *(unsigned __int16 *)(v9 + 56);
        if ( *a7 >= (unsigned __int64)(v19 + 2) )
        {
          memcpy_0(a6, *(const void **)(v9 + 64), *((size_t *)&v9 + 1));
          *(_WORD *)&a6[2 * (*((_QWORD *)&v9 + 1) >> 1)] = 0;
          v20 = *(unsigned __int16 *)(v9 + 56) + 2;
        }
        else
        {
          v11 = -1073741789;
          v20 = v19 + 2;
        }
        *a7 = v20;
      }
      else
      {
        *a7 = v19 + 2;
      }
      break;
    default:
      return (unsigned int)-1058471933;
  }
  return v11;
}

```

## disassembly

```asm
0x18001bfb4  push    rbp
0x18001bfb6  push    rbx
0x18001bfb7  push    rsi
0x18001bfb8  push    rdi
0x18001bfb9  push    r12
0x18001bfbb  push    r13
0x18001bfbd  push    r14
0x18001bfbf  push    r15
0x18001bfc1  mov     rbp, rsp
0x18001bfc4  sub     rsp, 58h
0x18001bfc8  mov     eax, [rcx+300h]
0x18001bfce  xorps   xmm0, xmm0
0x18001bfd1  mov     r15d, 1
0x18001bfd7  mov     r14, r9
0x18001bfda  and     eax, r15d
0x18001bfdd  mov     rsi, r8
0x18001bfe0  mov     rdi, rdx
0x18001bfe3  mov     rbx, rcx
0x18001bfe6  movups  [rbp+Key], xmm0
0x18001bfea  movups  [rbp+var_18], xmm0
0x18001bfee  test    al, al
0x18001bff0  jnz     short loc_18001C02A
0x18001bff2  mov     r8b, r15b; CaseInsensitive
0x18001bff5  lea     rdx, stru_180043120; String2
0x18001bffc  mov     rcx, rdi; String1
0x18001bfff  call    cs:__imp_RtlEqualUnicodeString
0x18001c005  test    al, al
0x18001c007  jz      short loc_18001C02A
0x18001c009  mov     r8b, r15b; CaseInsensitive
0x18001c00c  lea     rdx, stru_180043150; String2
0x18001c013  mov     rcx, rsi; String1
0x18001c016  call    cs:__imp_RtlEqualUnicodeString
0x18001c01c  test    al, al
0x18001c01e  jz      short loc_18001C02A
0x18001c020  mov     ebx, 0C0000225h
0x18001c025  jmp     loc_18001C1F4
0x18001c02a  mov     r8d, [rbx+2B0h]; NumOfElements
0x18001c031  lea     r13, SIPolicySecureSettingSearchCompare
0x18001c038  mov     rdx, [rbx+2B8h]; Base
0x18001c03f  lea     rcx, [rbp+Key]; Key
0x18001c043  mov     r12d, 48h ; 'H'
0x18001c049  mov     qword ptr [rbp+Key], rdi
0x18001c04d  mov     r9d, r12d; SizeOfElements
0x18001c050  mov     qword ptr [rbp+Key+8], rsi
0x18001c054  mov     qword ptr [rbp+var_18], r14
0x18001c058  mov     [rsp+58h+CompareFunction], r13; CompareFunction
0x18001c05d  call    bsearch
0x18001c062  mov     rdi, rax
0x18001c065  test    rax, rax
0x18001c068  jnz     short loc_18001C0D3
0x18001c06a  mov     r8d, [rbx+2B0h]; NumOfElements
0x18001c071  lea     rcx, [rbp+Key]; Key
0x18001c075  mov     rdx, [rbx+2B8h]; Base
0x18001c07c  mov     r9d, r12d; SizeOfElements
0x18001c07f  mov     qword ptr [rbp+var_18], r14
0x18001c083  lea     r14, g_AnyFileWildCardString
0x18001c08a  mov     qword ptr [rbp+Key+8], r14
0x18001c08e  mov     [rsp+58h+CompareFunction], r13; CompareFunction
0x18001c093  call    bsearch
0x18001c098  mov     rdi, rax
0x18001c09b  test    rax, rax
0x18001c09e  jnz     short loc_18001C0D3
0x18001c0a0  mov     r8d, [rbx+2B0h]; NumOfElements
0x18001c0a7  lea     rcx, [rbp+Key]; Key
0x18001c0ab  mov     rdx, [rbx+2B8h]; Base
0x18001c0b2  mov     r9d, r12d; SizeOfElements
0x18001c0b5  mov     qword ptr [rbp+Key+8], rsi
0x18001c0b9  mov     qword ptr [rbp+var_18], r14
0x18001c0bd  mov     [rsp+58h+CompareFunction], r13; CompareFunction
0x18001c0c2  call    bsearch
0x18001c0c7  mov     rdi, rax
0x18001c0ca  test    rax, rax
0x18001c0cd  jz      loc_18001C020
0x18001c0d3  mov     edx, [rdi]
0x18001c0d5  xor     ebx, ebx
0x18001c0d7  mov     ecx, edx
0x18001c0d9  test    edx, edx
0x18001c0db  jz      loc_18001C1C6
0x18001c0e1  sub     ecx, r15d
0x18001c0e4  jz      loc_18001C197
0x18001c0ea  sub     ecx, r15d
0x18001c0ed  jz      short loc_18001C164
0x18001c0ef  cmp     ecx, r15d
0x18001c0f2  jz      short loc_18001C0FE
0x18001c0f4  mov     ebx, 0C0E90003h
0x18001c0f9  jmp     loc_18001C1F4
0x18001c0fe  mov     rax, [rbp+arg_20]
0x18001c102  mov     r15, [rbp+arg_28]
0x18001c106  mov     [rax], edx
0x18001c108  movzx   edx, word ptr [rdi+38h]
0x18001c10c  test    r15, r15
0x18001c10f  jnz     short loc_18001C11F
0x18001c111  mov     rax, [rbp+arg_30]
0x18001c115  lea     ecx, [rdx+2]
0x18001c118  mov     [rax], ecx
0x18001c11a  jmp     loc_18001C1F4
0x18001c11f  mov     r14, [rbp+arg_30]
0x18001c123  lea     rcx, [rdx+2]
0x18001c127  mov     rsi, rdx
0x18001c12a  mov     eax, [r14]
0x18001c12d  cmp     rax, rcx
0x18001c130  jnb     short loc_18001C142
0x18001c132  mov     ebx, 0C0000023h
0x18001c137  lea     eax, [rdx+2]
0x18001c13a  mov     [r14], eax
0x18001c13d  jmp     loc_18001C1F4
0x18001c142  mov     rdx, [rdi+40h]; Src
0x18001c146  mov     r8, rsi; Size
0x18001c149  mov     rcx, r15; void *
0x18001c14c  call    memcpy_0
0x18001c151  xor     eax, eax
0x18001c153  shr     rsi, 1
0x18001c156  mov     [r15+rsi*2], ax
0x18001c15b  movzx   eax, word ptr [rdi+38h]
0x18001c15f  add     eax, 2
0x18001c162  jmp     short loc_18001C13A
0x18001c164  mov     rax, [rbp+arg_20]
0x18001c168  mov     r9, [rbp+arg_28]
0x18001c16c  mov     [rax], edx
0x18001c16e  mov     edx, [rdi+38h]
0x18001c171  mov     rax, [rbp+arg_30]
0x18001c175  test    r9, r9
0x18001c178  jnz     short loc_18001C17E
0x18001c17a  mov     [rax], edx
0x18001c17c  jmp     short loc_18001C1F4
0x18001c17e  mov     ecx, [rax]
0x18001c180  mov     [rax], edx
0x18001c182  cmp     ecx, edx
0x18001c184  jb      short loc_18001C1E8
0x18001c186  mov     r8, rdx; Size
0x18001c189  mov     rcx, r9; void *
0x18001c18c  mov     rdx, [rdi+40h]; Src
0x18001c190  call    memcpy_0
0x18001c195  jmp     short loc_18001C1F4
0x18001c197  mov     rax, [rbp+arg_20]
0x18001c19b  mov     [rax], edx
0x18001c19d  mov     rdx, [rbp+arg_28]
0x18001c1a1  mov     rax, [rbp+arg_30]
0x18001c1a5  test    rdx, rdx
0x18001c1a8  jnz     short loc_18001C1B2
0x18001c1aa  mov     dword ptr [rax], 4
0x18001c1b0  jmp     short loc_18001C1F4
0x18001c1b2  mov     ecx, [rax]
0x18001c1b4  mov     dword ptr [rax], 4
0x18001c1ba  cmp     ecx, 4
0x18001c1bd  jb      short loc_18001C1E8
0x18001c1bf  mov     eax, [rdi+38h]
0x18001c1c2  mov     [rdx], eax
0x18001c1c4  jmp     short loc_18001C1F4
0x18001c1c6  mov     rax, [rbp+arg_20]
0x18001c1ca  mov     [rax], edx
0x18001c1cc  mov     rdx, [rbp+arg_28]
0x18001c1d0  mov     rax, [rbp+arg_30]
0x18001c1d4  test    rdx, rdx
0x18001c1d7  jnz     short loc_18001C1DE
0x18001c1d9  mov     [rax], r15d
0x18001c1dc  jmp     short loc_18001C1F4
0x18001c1de  mov     ecx, [rax]
0x18001c1e0  mov     [rax], r15d
0x18001c1e3  cmp     ecx, r15d
0x18001c1e6  jnb     short loc_18001C1EF
0x18001c1e8  mov     ebx, 0C0000023h
0x18001c1ed  jmp     short loc_18001C1F4
0x18001c1ef  mov     cl, [rdi+38h]
0x18001c1f2  mov     [rdx], cl
0x18001c1f4  mov     eax, ebx
0x18001c1f6  add     rsp, 58h
0x18001c1fa  pop     r15
0x18001c1fc  pop     r14
0x18001c1fe  pop     r13
0x18001c200  pop     r12
0x18001c202  pop     rdi
0x18001c203  pop     rsi
0x18001c204  pop     rbx
0x18001c205  pop     rbp
0x18001c206  retn
```
