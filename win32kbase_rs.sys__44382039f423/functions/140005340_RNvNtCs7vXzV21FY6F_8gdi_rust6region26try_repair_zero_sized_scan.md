# _RNvNtCs7vXzV21FY6F_8gdi_rust6region26try_repair_zero_sized_scan

- ea: `0x140005340`
- end: `0x14000557e`
- name: `_RNvNtCs7vXzV21FY6F_8gdi_rust6region26try_repair_zero_sized_scan`
- size: `574`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140004da0`

## callees

- `0x140005340`
- `0x14000be40`
- `0x14000c1a0`
- `0x14000f3a0`
- `0x14000fca0`
- `0x140012b60`
- `0x140017a10`
- `0x140017b00`
- `0x140017f00`
- `0x1400187f0`

## pseudocode

```c
__int64 __fastcall RNvNtCs7vXzV21FY6F_8gdi_rust6region26try_repair_zero_sized_scan(unsigned __int64 *a1, __int64 a2)
{
  unsigned __int64 v3; // r14
  char *v4; // r13
  __int64 result; // rax
  __int64 v6; // r15
  int v7; // ebp
  __int64 v8; // r12
  int v9; // eax
  unsigned __int64 v10; // rcx
  bool v11; // cf
  int v12; // edx
  char *v13; // r9
  signed int v14; // edi
  __int64 v15; // r11
  signed int v16; // ebx
  unsigned __int64 v17; // r8
  unsigned __int64 v18; // rax
  void *v19; // r9
  unsigned __int64 v20; // rbx
  __int64 v21; // rcx
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rdx
  unsigned int v24; // esi
  __int64 v25; // rdx
  __int64 v26; // [rsp+0h] [rbp-98h] BYREF
  __int64 v27; // [rsp+30h] [rbp-68h]
  void *v28; // [rsp+38h] [rbp-60h]
  __int64 v29; // [rsp+40h] [rbp-58h] BYREF
  __int64 v30; // [rsp+48h] [rbp-50h]
  __int64 v31; // [rsp+50h] [rbp-48h]

  v3 = *a1;
  v4 = (char *)a1[1];
  RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore23clear_scans_and_reserve(&v29, a2, *a1);
  if ( (_DWORD)v29 == 1 )
  {
    result = HIDWORD(v29);
  }
  else
  {
    v27 = v30;
    v29 = v30;
    v6 = *((unsigned int *)a1 + 6);
    v7 = 0x80000000;
    v8 = 0;
    v28 = v4;
    while ( v8 != v6 )
    {
      v9 = 87;
      if ( v3 < 4 )
        goto LABEL_22;
      v10 = *(unsigned int *)v4;
      if ( (v10 & 0x80000000) != 0LL )
        goto LABEL_22;
      v11 = v3 < v10 + 4;
      v3 -= v10 + 4;
      if ( v11 )
        goto LABEL_22;
      if ( (v10 & 1) != 0 )
        goto LABEL_22;
      v12 = *((_DWORD *)v4 + 1);
      if ( v7 > v12 )
        goto LABEL_22;
      v7 = *((_DWORD *)v4 + 2);
      if ( v12 >= v7 )
        goto LABEL_22;
      v13 = v4 + 12;
      if ( *(_DWORD *)v4 )
      {
        v14 = 0x80000000;
        v15 = 0;
        do
        {
          v16 = v14;
          v14 = *(_DWORD *)&v13[v15];
          if ( v16 > v14 )
            goto LABEL_22;
          v15 += 4;
        }
        while ( 4 * v10 != v15 );
      }
      ++v8;
      v4 += 4 * v10 + 16;
      v9 = RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11append_scan(
             v27,
             v12,
             v7,
             v13,
             v10);
      if ( v9 )
        goto LABEL_22;
    }
    v17 = *(_QWORD *)(v27 + 16);
    v18 = a1[2];
    if ( v17 >= v18 )
    {
      v19 = v28;
      if ( v17 <= v18 )
      {
        v23 = *(_QWORD *)(v27 + 16);
        v22 = a1[2];
      }
      else
      {
        v20 = *(_QWORD *)(v27 + 16);
        v21 = RNvMs2_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11try_reserveCs7vXzV21FY6F_8gdi_rust(
                (_DWORD)a1,
                v18,
                (int)v17 - (int)v18,
                4,
                4);
        v9 = 14;
        if ( v21 != 0x8000000000000001uLL )
        {
LABEL_22:
          v24 = v9;
          RNvXCsdcpJtfrLhSH_7rgncoreNtB2_11RegionGuardNtNtNtCs9MWeMO1rkJG_4core3ops4drop4Drop4drop(&v29);
          result = v24;
          goto LABEL_23;
        }
        memset((void *)(a1[1] + 4 * a1[2]), 0, 4 * (v20 - a1[2]));
        v22 = v20;
        a1[2] = v20;
        v19 = (void *)a1[1];
        v23 = *(_QWORD *)(v27 + 16);
      }
      if ( v22 != v23 )
        RNvNvNtCs9MWeMO1rkJG_4core5slice20copy_from_slice_impl17len_mismatch_fail(v22, v23, &off_14001B150, v19);
      v17 = v23;
    }
    else
    {
      a1[2] = v17;
      v19 = v28;
    }
    memmove(v19, *(const void **)(v27 + 8), 4 * v17);
    RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore20tighten_bounding_box(a1, v25);
    RNvXCsdcpJtfrLhSH_7rgncoreNtB2_11RegionGuardNtNtNtCs9MWeMO1rkJG_4core3ops4drop4Drop4drop(&v29);
    result = 0;
  }
LABEL_23:
  if ( _security_cookie != ((unsigned __int64)&v26 ^ v31) )
    JUMPOUT(0x14000557DLL);
  return result;
}

```

## disassembly

```asm
0x140005340  push    r15
0x140005342  push    r14
0x140005344  push    r13
0x140005346  push    r12
0x140005348  push    rsi
0x140005349  push    rdi
0x14000534a  push    rbp
0x14000534b  push    rbx
0x14000534c  sub     rsp, 58h
0x140005350  mov     rsi, rcx
0x140005353  mov     rax, cs:__security_cookie
0x14000535a  xor     rax, rsp
0x14000535d  mov     [rsp+98h+var_48], rax
0x140005362  mov     r14, [rcx]
0x140005365  mov     r13, [rcx+8]
0x140005369  lea     rcx, [rsp+98h+var_58]
0x14000536e  mov     r8, r14
0x140005371  call    _RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore23clear_scans_and_reserve
0x140005376  cmp     dword ptr [rsp+98h+var_58], 1
0x14000537b  jnz     short loc_140005386
0x14000537d  mov     eax, dword ptr [rsp+98h+var_58+4]
0x140005381  jmp     loc_140005506
0x140005386  mov     rax, [rsp+98h+var_50]
0x14000538b  mov     [rsp+98h+var_68], rax
0x140005390  mov     [rsp+98h+var_58], rax
0x140005395  mov     r15d, [rsi+18h]
0x140005399  mov     ebp, 80000000h
0x14000539e  xor     r12d, r12d
0x1400053a1  mov     [rsp+98h+var_60], r13
0x1400053a6  jmp     short loc_1400053D2
0x1400053b0  inc     r12
0x1400053b3  lea     r13, [r13+r8*4+0]
0x1400053b8  mov     [rsp+98h+var_78], rcx
0x1400053bd  mov     rcx, [rsp+98h+var_68]
0x1400053c2  mov     r8d, ebp
0x1400053c5  call    _RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11append_scan
0x1400053ca  test    eax, eax
0x1400053cc  jnz     loc_1400054F8
0x1400053d2  cmp     r12, r15
0x1400053d5  jz      loc_14000545C
0x1400053db  mov     eax, 57h ; 'W'
0x1400053e0  cmp     r14, 4
0x1400053e4  jb      loc_1400054F8
0x1400053ea  mov     ecx, [r13+0]
0x1400053ee  test    ecx, ecx
0x1400053f0  js      loc_1400054F8
0x1400053f6  lea     r8, [rcx+4]
0x1400053fa  sub     r14, r8
0x1400053fd  jb      loc_1400054F8
0x140005403  test    cl, 1
0x140005406  jnz     loc_1400054F8
0x14000540c  mov     edx, [r13+4]
0x140005410  cmp     ebp, edx
0x140005412  jg      loc_1400054F8
0x140005418  mov     ebp, [r13+8]
0x14000541c  cmp     edx, ebp
0x14000541e  jge     loc_1400054F8
0x140005424  lea     r9, [r13+0Ch]
0x140005428  test    rcx, rcx
0x14000542b  jz      short loc_1400053B0
0x14000542d  lea     r10, ds:0[rcx*4]
0x140005435  mov     edi, 80000000h
0x14000543a  xor     r11d, r11d
0x14000543d  nop     dword ptr [rax]
0x140005440  mov     ebx, edi
0x140005442  mov     edi, [r9+r11]
0x140005446  cmp     ebx, edi
0x140005448  jg      loc_1400054F8
0x14000544e  add     r11, 4
0x140005452  cmp     r10, r11
0x140005455  jnz     short loc_140005440
0x140005457  jmp     loc_1400053B0
0x14000545c  mov     rax, [rsp+98h+var_68]
0x140005461  mov     r8, [rax+10h]
0x140005465  mov     rax, [rsi+10h]
0x140005469  mov     r10, r8
0x14000546c  sub     r10, rax
0x14000546f  jnb     short loc_14000547F
0x140005471  mov     [rsi+10h], r8
0x140005475  mov     r9, [rsp+98h+var_60]
0x14000547a  jmp     loc_140005539
0x14000547f  mov     r9, [rsp+98h+var_60]
0x140005484  jbe     loc_14000552B
0x14000548a  mov     rbx, r8
0x14000548d  mov     [rsp+98h+var_78], 4
0x140005496  mov     r9d, 4
0x14000549c  mov     rcx, rsi
0x14000549f  mov     rdx, rax
0x1400054a2  mov     r8, r10
0x1400054a5  call    _RNvMs2_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11try_reserveCs7vXzV21FY6F_8gdi_rust
0x1400054aa  mov     rcx, rax
0x1400054ad  mov     eax, 0Eh
0x1400054b2  mov     rdx, 8000000000000001h
0x1400054bc  cmp     rcx, rdx
0x1400054bf  jnz     short loc_1400054F8
0x1400054c1  mov     rax, [rsi+10h]
0x1400054c5  lea     rcx, ds:0[rax*4]
0x1400054cd  add     rcx, [rsi+8]; void *
0x1400054d1  mov     r8, rbx
0x1400054d4  sub     r8, rax
0x1400054d7  shl     r8, 2; Size
0x1400054db  xor     edx, edx; Val
0x1400054dd  call    memset
0x1400054e2  mov     rcx, rbx
0x1400054e5  mov     [rsi+10h], rbx
0x1400054e9  mov     r9, [rsi+8]
0x1400054ed  mov     rax, [rsp+98h+var_68]
0x1400054f2  mov     rdx, [rax+10h]
0x1400054f6  jmp     short loc_140005531
0x1400054f8  lea     rcx, [rsp+98h+var_58]
0x1400054fd  mov     esi, eax
0x1400054ff  call    _RNvXCsdcpJtfrLhSH_7rgncoreNtB2_11RegionGuardNtNtNtCs9MWeMO1rkJG_4core3ops4drop4Drop4drop
0x140005504  mov     eax, esi
0x140005506  mov     rcx, [rsp+98h+var_48]
0x14000550b  xor     rcx, rsp
0x14000550e  mov     rdx, cs:__security_cookie
0x140005515  cmp     rdx, rcx
0x140005518  jnz     short loc_140005570
0x14000551a  add     rsp, 58h
0x14000551e  pop     rbx
0x14000551f  pop     rbp
0x140005520  pop     rdi
0x140005521  pop     rsi
0x140005522  pop     r12
0x140005524  pop     r13
0x140005526  pop     r14
0x140005528  pop     r15
0x14000552a  retn
0x14000552b  mov     rdx, r8
0x14000552e  mov     rcx, rax
0x140005531  cmp     rcx, rdx
0x140005534  jnz     short loc_140005564
0x140005536  mov     r8, rdx
0x140005539  mov     rax, [rsp+98h+var_68]
0x14000553e  mov     rdx, [rax+8]; Src
0x140005542  shl     r8, 2; Size
0x140005546  mov     rcx, r9; void *
0x140005549  call    memmove
0x14000554e  mov     rcx, rsi
0x140005551  call    _RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore20tighten_bounding_box
0x140005556  lea     rcx, [rsp+98h+var_58]
0x14000555b  call    _RNvXCsdcpJtfrLhSH_7rgncoreNtB2_11RegionGuardNtNtNtCs9MWeMO1rkJG_4core3ops4drop4Drop4drop
0x140005560  xor     eax, eax
0x140005562  jmp     short loc_140005506
0x140005564  lea     r8, off_14001B150; "gdi_rust\\src\\region.rs"
0x14000556b  call    _RNvNvNtCs9MWeMO1rkJG_4core5slice20copy_from_slice_impl17len_mismatch_fail
0x140005570  mov     rcx, [rsp+98h+var_48]
0x140005575  xor     rcx, rsp; StackCookie
0x140005578  call    __security_check_cookie
```
