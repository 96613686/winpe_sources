# _RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore23clear_scans_and_reserve

- ea: `0x14000c1a0`
- end: `0x14000c290`
- name: `_RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore23clear_scans_and_reserve`
- size: `240`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140005340`
- `0x14000cc10`
- `0x1400101f0`
- `0x140011120`

## callees

- `0x14000c1a0`
- `0x140017a10`
- `0x1400193b0`

## pseudocode

```c
__int64 __fastcall RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore23clear_scans_and_reserve(
        __int64 a1,
        unsigned __int64 *a2,
        unsigned __int64 a3)
{
  __int64 v3; // rax
  unsigned __int64 v4; // r9
  int v5; // eax
  __int64 v6; // rdi
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rsi
  unsigned __int64 *v9; // rbx
  __int64 v11; // [rsp+0h] [rbp-68h] BYREF
  __int64 v12[7]; // [rsp+30h] [rbp-38h] BYREF

  v3 = *a2;
  if ( a3 > *a2 )
  {
    v4 = a2[2];
    if ( a3 - v4 > v3 - v4 )
    {
      if ( a3 < v4 )
      {
LABEL_4:
        *(_DWORD *)(a1 + 4) = 14;
        v5 = 1;
        goto LABEL_13;
      }
      v6 = a1;
      v7 = 2 * v3;
      if ( a3 > 2 * v3 )
        v7 = a3;
      v8 = 4;
      if ( v7 >= 5 )
        v8 = v7;
      v9 = a2;
      RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
        v12,
        v3,
        (const void *)a2[1],
        v8,
        4u,
        4u);
      if ( LODWORD(v12[0]) == 1 )
      {
        a1 = v6;
        goto LABEL_4;
      }
      a2 = v9;
      v9[1] = v12[1];
      *v9 = v8;
      a1 = v6;
    }
  }
  a2[2] = 0;
  *((_DWORD *)a2 + 6) = 0;
  *(_QWORD *)(a1 + 8) = a2;
  v5 = 0;
LABEL_13:
  *(_DWORD *)a1 = v5;
  if ( _security_cookie != ((unsigned __int64)&v11 ^ v12[3]) )
    JUMPOUT(0x14000C28FLL);
  return a1;
}

```

## disassembly

```asm
0x14000c1a0  push    rsi
0x14000c1a1  push    rdi
0x14000c1a2  push    rbx
0x14000c1a3  sub     rsp, 50h
0x14000c1a7  mov     rax, cs:__security_cookie
0x14000c1ae  xor     rax, rsp
0x14000c1b1  mov     [rsp+68h+var_20], rax
0x14000c1b6  mov     rax, [rdx]
0x14000c1b9  cmp     r8, rax
0x14000c1bc  jbe     loc_14000C24C
0x14000c1c2  mov     r9, [rdx+10h]
0x14000c1c6  mov     r10, r8
0x14000c1c9  sub     r10, r9
0x14000c1cc  mov     r11, rax
0x14000c1cf  sub     r11, r9
0x14000c1d2  cmp     r10, r11
0x14000c1d5  jbe     short loc_14000C24C
0x14000c1d7  cmp     r8, r9
0x14000c1da  jnb     short loc_14000C1EA
0x14000c1dc  mov     dword ptr [rcx+4], 0Eh
0x14000c1e3  mov     eax, 1
0x14000c1e8  jmp     short loc_14000C261
0x14000c1ea  mov     rdi, rcx
0x14000c1ed  lea     rcx, [rax+rax]
0x14000c1f1  cmp     r8, rcx
0x14000c1f4  cmova   rcx, r8
0x14000c1f8  cmp     rcx, 5
0x14000c1fc  mov     esi, 4
0x14000c201  cmovnb  rsi, rcx
0x14000c205  mov     rbx, rdx
0x14000c208  mov     r8, [rdx+8]
0x14000c20c  mov     [rsp+68h+var_40], 4
0x14000c215  mov     [rsp+68h+var_48], 4
0x14000c21e  lea     rcx, [rsp+68h+var_38]
0x14000c223  mov     rdx, rax
0x14000c226  mov     r9, rsi
0x14000c229  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244
0x14000c22e  cmp     [rsp+68h+var_38], 1
0x14000c233  jnz     short loc_14000C23A
0x14000c235  mov     rcx, rdi
0x14000c238  jmp     short loc_14000C1DC
0x14000c23a  mov     rax, [rsp+68h+var_30]
0x14000c23f  mov     rdx, rbx
0x14000c242  mov     [rbx+8], rax
0x14000c246  mov     [rbx], rsi
0x14000c249  mov     rcx, rdi
0x14000c24c  mov     qword ptr [rdx+10h], 0
0x14000c254  mov     dword ptr [rdx+18h], 0
0x14000c25b  mov     [rcx+8], rdx
0x14000c25f  xor     eax, eax
0x14000c261  mov     [rcx], eax
0x14000c263  mov     rax, [rsp+68h+var_20]
0x14000c268  xor     rax, rsp
0x14000c26b  mov     rdx, cs:__security_cookie
0x14000c272  cmp     rdx, rax
0x14000c275  jnz     short loc_14000C282
0x14000c277  mov     rax, rcx
0x14000c27a  add     rsp, 50h
0x14000c27e  pop     rbx
0x14000c27f  pop     rdi
0x14000c280  pop     rsi
0x14000c281  retn
0x14000c282  mov     rcx, [rsp+68h+var_20]
0x14000c287  xor     rcx, rsp; StackCookie
0x14000c28a  call    __security_check_cookie
```
