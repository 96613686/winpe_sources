# _RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore7combine

- ea: `0x14000ca10`
- end: `0x14000cc03`
- name: `_RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore7combine`
- size: `499`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004da0`
- `0x14000acb0`

## callees

- `0x14000b710`
- `0x14000b860`
- `0x14000c2a0`
- `0x14000ca10`
- `0x14000e9d0`
- `0x140014460`
- `0x140017a10`
- `0x140018650`

## pseudocode

```c
__int64 __fastcall RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore7combine(__int64 *a1, __int64 a2, __int64 a3, int a4)
{
  unsigned int v5; // ecx
  __int64 v6; // r10
  int v7; // r11d
  int v8; // eax
  __int64 result; // rax
  int v10; // ecx
  int v11; // r9d
  __int64 v12; // rdx
  int v13; // r8d
  __int64 v14; // rdi
  unsigned __int64 v15; // r8
  __int64 v16; // [rsp+0h] [rbp-58h] BYREF
  _DWORD v17[4]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v18; // [rsp+40h] [rbp-18h]

  v5 = a4 - 1;
  if ( (unsigned int)(a4 - 1) > 1 )
  {
LABEL_13:
    if ( v5 >= 4 )
      RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt(
        anon_c9360f58bbc394745aa7882ed1343abe_3_llvm_18110786352924170244,
        51,
        &anon_c9360f58bbc394745aa7882ed1343abe_5_llvm_18110786352924170244);
    if ( (unsigned int)RNvMs_NtCsdcpJtfrLhSH_7rgncore5mergeNtB6_10RegionCore5merge(a1, a2, a3, 0x4060E08u >> (8 * v5)) )
    {
      result = 1;
      goto LABEL_38;
    }
    goto LABEL_37;
  }
  v6 = *(_QWORD *)(a2 + 16);
  if ( v6 == 14
    && *(_DWORD *)(a2 + 28) <= *(_DWORD *)(a3 + 28)
    && *(_DWORD *)(a2 + 36) >= *(_DWORD *)(a3 + 36)
    && *(_DWORD *)(a2 + 32) <= *(_DWORD *)(a3 + 32)
    && *(_DWORD *)(a2 + 40) >= *(_DWORD *)(a3 + 40) )
  {
    if ( a4 == 1 )
      a2 = a3;
    v14 = a2;
    v15 = *(_QWORD *)(a2 + 16);
    goto LABEL_35;
  }
  if ( *(_QWORD *)(a3 + 16) != 14 )
    goto LABEL_13;
  v7 = *(_DWORD *)(a3 + 28);
  v8 = *(_DWORD *)(a2 + 28);
  if ( v7 <= v8
    && *(_DWORD *)(a3 + 36) >= *(_DWORD *)(a2 + 36)
    && *(_DWORD *)(a3 + 32) <= *(_DWORD *)(a2 + 32)
    && *(_DWORD *)(a3 + 40) >= *(_DWORD *)(a2 + 40) )
  {
    if ( a4 == 1 )
      a3 = a2;
    v14 = a3;
    v15 = *(_QWORD *)(a3 + 16);
LABEL_35:
    if ( RNvMs2_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11try_reserveCsdcpJtfrLhSH_7rgncore(
           (unsigned __int64 *)a1,
           a1[2],
           v15,
           4,
           4u) == 0x8000000000000001uLL )
    {
      RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore27set_to_scans_from_no_resize(a1, v14);
LABEL_37:
      result = 0;
      goto LABEL_38;
    }
    result = 1;
    goto LABEL_38;
  }
  if ( v6 != 14 || a4 != 1 )
    goto LABEL_13;
  if ( v7 > v8 )
    v8 = *(_DWORD *)(a3 + 28);
  v10 = *(_DWORD *)(a2 + 32);
  v11 = *(_DWORD *)(a2 + 36);
  if ( *(_DWORD *)(a3 + 36) < v11 )
    v11 = *(_DWORD *)(a3 + 36);
  if ( *(_DWORD *)(a3 + 32) > v10 )
    v10 = *(_DWORD *)(a3 + 32);
  v12 = *(unsigned int *)(a2 + 40);
  v13 = *(_DWORD *)(a3 + 40);
  if ( v13 < (int)v12 )
    v12 = (unsigned int)v13;
  v17[0] = v8;
  v17[1] = v10;
  v17[2] = v11;
  v17[3] = v12;
  if ( v8 >= v11 || v10 >= (int)v12 )
    RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore16set_to_null_scan(a1, v12);
  else
    RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore16set_to_rectangle(a1, v17);
  result = 0;
LABEL_38:
  if ( _security_cookie != ((unsigned __int64)&v16 ^ v18) )
    JUMPOUT(0x14000CC02LL);
  return result;
}

```

## disassembly

```asm
0x14000ca10  push    rsi
0x14000ca11  push    rdi
0x14000ca12  sub     rsp, 48h
0x14000ca16  mov     rsi, rcx
0x14000ca19  mov     rax, cs:__security_cookie
0x14000ca20  xor     rax, rsp
0x14000ca23  mov     [rsp+58h+var_18], rax
0x14000ca28  lea     ecx, [r9-1]
0x14000ca2c  cmp     ecx, 1
0x14000ca2f  ja      short loc_14000CAAA
0x14000ca31  mov     r10, [rdx+10h]
0x14000ca35  cmp     r10, 0Eh
0x14000ca39  jnz     short loc_14000CA63
0x14000ca3b  mov     eax, [rdx+1Ch]
0x14000ca3e  cmp     eax, [r8+1Ch]
0x14000ca42  jg      short loc_14000CA63
0x14000ca44  mov     eax, [rdx+24h]
0x14000ca47  cmp     eax, [r8+24h]
0x14000ca4b  jl      short loc_14000CA63
0x14000ca4d  mov     eax, [rdx+20h]
0x14000ca50  cmp     eax, [r8+20h]
0x14000ca54  jg      short loc_14000CA63
0x14000ca56  mov     eax, [rdx+28h]
0x14000ca59  cmp     eax, [r8+28h]
0x14000ca5d  jge     loc_14000CB47
0x14000ca63  cmp     qword ptr [r8+10h], 0Eh
0x14000ca68  jnz     short loc_14000CAAA
0x14000ca6a  mov     r11d, [r8+1Ch]
0x14000ca6e  mov     eax, [rdx+1Ch]
0x14000ca71  cmp     r11d, eax
0x14000ca74  jg      short loc_14000CA95
0x14000ca76  mov     edi, [r8+24h]
0x14000ca7a  cmp     edi, [rdx+24h]
0x14000ca7d  jl      short loc_14000CA95
0x14000ca7f  mov     edi, [r8+20h]
0x14000ca83  cmp     edi, [rdx+20h]
0x14000ca86  jg      short loc_14000CA95
0x14000ca88  mov     edi, [r8+28h]
0x14000ca8c  cmp     edi, [rdx+28h]
0x14000ca8f  jge     loc_14000CB58
0x14000ca95  cmp     r10, 0Eh
0x14000ca99  setnz   r10b
0x14000ca9d  cmp     r9d, 1
0x14000caa1  setnz   r9b
0x14000caa5  or      r9b, r10b
0x14000caa8  jz      short loc_14000CADB
0x14000caaa  cmp     ecx, 4
0x14000caad  jnb     loc_14000CBDD
0x14000cab3  shl     ecx, 3
0x14000cab6  mov     r9d, 4060E08h
0x14000cabc  shr     r9d, cl
0x14000cabf  mov     rcx, rsi
0x14000cac2  call    _RNvMs_NtCsdcpJtfrLhSH_7rgncore5mergeNtB6_10RegionCore5merge
0x14000cac7  test    eax, eax
0x14000cac9  jz      loc_14000CB9C
0x14000cacf  mov     edx, eax
0x14000cad1  mov     eax, 1
0x14000cad6  jmp     loc_14000CBB6
0x14000cadb  cmp     r11d, eax
0x14000cade  cmovg   eax, r11d
0x14000cae2  mov     ecx, [rdx+20h]
0x14000cae5  mov     r9d, [rdx+24h]
0x14000cae9  mov     r10d, [r8+20h]
0x14000caed  mov     r11d, [r8+24h]
0x14000caf1  cmp     r11d, r9d
0x14000caf4  cmovl   r9d, r11d
0x14000caf8  cmp     r10d, ecx
0x14000cafb  cmovg   ecx, r10d
0x14000caff  mov     edx, [rdx+28h]
0x14000cb02  mov     r8d, [r8+28h]
0x14000cb06  cmp     r8d, edx
0x14000cb09  cmovl   edx, r8d
0x14000cb0d  mov     [rsp+58h+var_28], eax
0x14000cb11  mov     [rsp+58h+var_24], ecx
0x14000cb15  mov     [rsp+58h+var_20], r9d
0x14000cb1a  mov     [rsp+58h+var_1C], edx
0x14000cb1e  cmp     eax, r9d
0x14000cb21  jge     short loc_14000CB36
0x14000cb23  cmp     ecx, edx
0x14000cb25  jge     short loc_14000CB36
0x14000cb27  lea     rdx, [rsp+58h+var_28]
0x14000cb2c  mov     rcx, rsi
0x14000cb2f  call    _RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore16set_to_rectangle
0x14000cb34  jmp     short loc_14000CB3E
0x14000cb36  mov     rcx, rsi
0x14000cb39  call    _RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore16set_to_null_scan
0x14000cb3e  xor     eax, eax
0x14000cb40  mov     edx, 2
0x14000cb45  jmp     short loc_14000CBB6
0x14000cb47  cmp     r9d, 1
0x14000cb4b  cmovz   rdx, r8
0x14000cb4f  mov     rdi, rdx
0x14000cb52  mov     r8, [rdx+10h]
0x14000cb56  jmp     short loc_14000CB67
0x14000cb58  cmp     r9d, 1
0x14000cb5c  cmovz   r8, rdx
0x14000cb60  mov     rdi, r8
0x14000cb63  mov     r8, [r8+10h]
0x14000cb67  mov     rdx, [rsi+10h]
0x14000cb6b  mov     [rsp+58h+var_38], 4
0x14000cb74  mov     r9d, 4
0x14000cb7a  mov     rcx, rsi
0x14000cb7d  call    _RNvMs2_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11try_reserveCsdcpJtfrLhSH_7rgncore
0x14000cb82  mov     rcx, 8000000000000001h
0x14000cb8c  cmp     rax, rcx
0x14000cb8f  jnz     short loc_14000CBD1
0x14000cb91  mov     rcx, rsi
0x14000cb94  mov     rdx, rdi
0x14000cb97  call    _RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore27set_to_scans_from_no_resize
0x14000cb9c  xor     eax, eax
0x14000cb9e  mov     edx, 1
0x14000cba3  cmp     dword ptr [rsi+18h], 1
0x14000cba7  jz      short loc_14000CBB6
0x14000cba9  cmp     qword ptr [rsi+10h], 0Fh
0x14000cbae  mov     edx, 3
0x14000cbb3  sbb     edx, 0
0x14000cbb6  mov     rcx, [rsp+58h+var_18]
0x14000cbbb  xor     rcx, rsp
0x14000cbbe  mov     r8, cs:__security_cookie
0x14000cbc5  cmp     r8, rcx
0x14000cbc8  jnz     short loc_14000CBF5
0x14000cbca  add     rsp, 48h
0x14000cbce  pop     rdi
0x14000cbcf  pop     rsi
0x14000cbd0  retn
0x14000cbd1  mov     eax, 1
0x14000cbd6  mov     edx, 0Eh
0x14000cbdb  jmp     short loc_14000CBB6
0x14000cbdd  lea     rcx, anon_c9360f58bbc394745aa7882ed1343abe_3_llvm_18110786352924170244
0x14000cbe4  lea     r8, anon_c9360f58bbc394745aa7882ed1343abe_5_llvm_18110786352924170244
0x14000cbeb  mov     edx, 33h ; '3'
0x14000cbf0  call    _RNvNtCs9MWeMO1rkJG_4core9panicking9panic_fmt
0x14000cbf5  mov     rcx, [rsp+58h+var_18]
0x14000cbfa  xor     rcx, rsp; StackCookie
0x14000cbfd  call    __security_check_cookie
```
