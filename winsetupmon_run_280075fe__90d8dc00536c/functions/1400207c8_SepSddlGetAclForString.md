# SepSddlGetAclForString

- ea: `0x1400207c8`
- end: `0x140020b7f`
- name: `SepSddlGetAclForString`
- size: `951`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400206e4`

## callees

- `0x14000fd40`
- `0x1400205f0`
- `0x1400207c8`
- `0x140020b88`
- `0x140020c3c`

## import_xrefs

- `ntoskrnl!wcschr` at `0x1400207f3`
- `ntoskrnl!wcschr` at `0x1400207f3`
- `ntoskrnl!_wcsnicmp` at `0x140020986`
- `ntoskrnl!_wcsnicmp` at `0x1400209f6`
- `ntoskrnl!_wcsnicmp` at `0x140020986`
- `ntoskrnl!_wcsnicmp` at `0x1400209f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020b4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020b4b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400208aa`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400208ef`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400208aa`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400208ef`

## pseudocode

```c
__int64 __fastcall SepSddlGetAclForString(wchar_t *Str1, _QWORD *a2, wchar_t **a3)
{
  wchar_t *v5; // rsi
  wchar_t *v6; // rax
  unsigned int v8; // r8d
  __int64 v9; // rax
  wchar_t *v10; // rax
  wchar_t *v11; // rcx
  int i; // r9d
  unsigned int v13; // r13d
  unsigned int SidForString; // ebx
  _QWORD *PoolWithTag; // rax
  unsigned int v16; // r15d
  _WORD *v17; // rax
  _WORD *v18; // rdi
  const wchar_t *v19; // rdi
  const wchar_t *j; // rdi
  wchar_t v21; // ax
  unsigned int k; // esi
  __int64 v23; // r12
  wchar_t *v24; // rcx
  int v25; // edx
  _WORD *v26; // rsi
  int v27; // edi
  _WORD *v28; // rax
  _WORD *v29; // [rsp+A0h] [rbp+48h] BYREF
  int v30; // [rsp+A8h] [rbp+50h]
  int v31; // [rsp+B0h] [rbp+58h]
  const wchar_t *v32; // [rsp+B8h] [rbp+60h] BYREF

  *a2 = 0;
  v5 = Str1;
  v6 = wcschr(Str1, 0x3Au);
  *a3 = v6;
  if ( v6 == v5 )
    return 3221225485LL;
  v8 = 0;
  if ( v6 )
  {
    v10 = v6 - 1;
  }
  else
  {
    v9 = -1;
    do
      ++v9;
    while ( v5[v9] );
    v10 = &v5[v9];
  }
  *a3 = v10;
  v11 = v5;
  for ( i = 0; v11 < v10; ++v11 )
  {
    if ( *v11 == 59 )
    {
      ++v8;
    }
    else if ( *v11 != 32 )
    {
      i = 1;
    }
  }
  v13 = v8 / 5;
  if ( v8 != 5 * (v8 / 5) || !v8 && i )
    return (unsigned int)-1073741811;
  SidForString = 0;
  if ( !v13 )
  {
    PoolWithTag = ExAllocatePoolWithTag(PagedPool, 8u, 0x6C416553u);
    *a2 = PoolWithTag;
    if ( PoolWithTag )
    {
      *PoolWithTag = 524290;
      return SidForString;
    }
    return (unsigned int)-1073741670;
  }
  v16 = 48 * v13 + 8;
  if ( v16 > 0xFFFF )
    v16 = 0xFFFF;
  v17 = ExAllocatePoolWithTag(PagedPool, v16, 0x6C416553u);
  *a2 = v17;
  v18 = v17;
  if ( !v17 )
    return (unsigned int)-1073741670;
  v31 = 8;
  memset(v17, 0, v16);
  *v18 = 2;
  v18[1] = v16;
  *((_DWORD *)v18 + 1) = 0;
  v30 = 0;
  do
  {
    LODWORD(v29) = 0;
    while ( *v5 == 32 )
      ++v5;
    v19 = v5 + 1;
    if ( *v5 != 40 )
      v19 = v5;
    while ( *v19 == 32 )
      ++v19;
    if ( _wcsnicmp(v19, L"A", 1u) )
      goto LABEL_69;
    for ( j = v19 + 2; *j == 32; ++j )
      ;
    if ( *j != 59 )
    {
LABEL_69:
      SidForString = -1073741811;
      goto LABEL_70;
    }
    do
      v21 = *++j;
    while ( *j == 32 );
    if ( v21 != 59 )
    {
      do
      {
        if ( v21 == 32 )
        {
          do
            ++j;
          while ( *j == 32 );
        }
        for ( k = 0; k < 8; ++k )
        {
          v23 = 2LL * k;
          if ( !_wcsnicmp(j, (&off_140019040)[v23], *((unsigned int *)&off_140019040 + 2 * v23 + 2)) )
          {
            LODWORD(v29) = *((_DWORD *)&off_140019040 + 2 * v23 + 3) | (unsigned int)v29;
            j += *((unsigned int *)&off_140019040 + 2 * v23 + 2);
            goto LABEL_48;
          }
        }
        v32 = j;
        SepSddlParseWideStringUlong(j, &v32, &v29);
        if ( v32 == j )
          goto LABEL_69;
        j = v32;
LABEL_48:
        v21 = *j;
      }
      while ( *j != 59 );
    }
    v24 = (wchar_t *)(j + 1);
    v25 = 2;
    do
    {
      while ( *v24 == 32 )
        ++v24;
      if ( *v24 != 59 )
        SidForString = -1073741811;
      ++v24;
      --v25;
    }
    while ( v25 );
    if ( SidForString )
      goto LABEL_70;
    while ( *v24 == 32 )
      ++v24;
    v29 = 0;
    SidForString = SepSddlGetSidForString(v24);
    if ( SidForString )
      break;
    v26 = v29;
    if ( !v29 )
      goto LABEL_61;
    while ( *v26 == 32 )
      ++v26;
    if ( *v26 != 41 )
    {
LABEL_61:
      SidForString = -1073741705;
LABEL_70:
      v28 = (_WORD *)*a2;
LABEL_72:
      ExFreePoolWithTag(v28, 0);
      *a2 = 0;
      return SidForString;
    }
    v27 = v30;
    v5 = v26 + 1;
    if ( *v5 == 40 )
      ++v5;
    ++v30;
  }
  while ( v27 + 1 < v13 );
  v28 = (_WORD *)*a2;
  if ( SidForString )
    goto LABEL_72;
  v28[1] = v31;
  return SidForString;
}

```

## disassembly

```asm
0x1400207c8  push    rbp
0x1400207ca  push    rbx
0x1400207cb  push    rsi
0x1400207cc  push    rdi
0x1400207cd  push    r12
0x1400207cf  push    r13
0x1400207d1  push    r14
0x1400207d3  push    r15
0x1400207d5  mov     rbp, rsp
0x1400207d8  sub     rsp, 58h
0x1400207dc  xor     r15d, r15d
0x1400207df  mov     r14, rdx
0x1400207e2  mov     [rdx], r15
0x1400207e5  mov     rbx, r8
0x1400207e8  mov     rsi, rcx
0x1400207eb  mov     [rbp+var_18], r15
0x1400207ef  lea     edx, [r15+3Ah]; Ch
0x1400207f3  call    cs:__imp_wcschr
0x1400207fa  nop     dword ptr [rax+rax+00h]
0x1400207ff  mov     [rbx], rax
0x140020802  cmp     rax, rsi
0x140020805  jnz     short loc_140020811
0x140020807  mov     eax, 0C000000Dh
0x14002080c  jmp     loc_140020B6D
0x140020811  mov     r8d, r15d
0x140020814  test    rax, rax
0x140020817  jnz     short loc_14002082D
0x140020819  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002081d  inc     rax
0x140020820  cmp     [rsi+rax*2], r15w
0x140020825  jnz     short loc_14002081D
0x140020827  lea     rax, [rsi+rax*2]
0x14002082b  jmp     short loc_140020831
0x14002082d  add     rax, 0FFFFFFFFFFFFFFFEh
0x140020831  mov     [rbx], rax
0x140020834  mov     rcx, rsi
0x140020837  mov     r9d, r15d
0x14002083a  mov     r10d, 1
0x140020840  cmp     rsi, rax
0x140020843  jnb     short loc_140020864
0x140020845  movzx   edx, word ptr [rcx]
0x140020848  cmp     dx, 3Bh ; ';'
0x14002084c  jnz     short loc_140020853
0x14002084e  add     r8d, r10d
0x140020851  jmp     short loc_14002085B
0x140020853  cmp     dx, 20h ; ' '
0x140020857  cmovnz  r9d, r10d
0x14002085b  add     rcx, 2
0x14002085f  cmp     rcx, rax
0x140020862  jb      short loc_140020845
0x140020864  mov     eax, 0CCCCCCCDh
0x140020869  mul     r8d
0x14002086c  mov     r13d, edx
0x14002086f  shr     r13d, 2
0x140020873  lea     ecx, ds:0[r13*4]
0x14002087b  add     ecx, r13d
0x14002087e  cmp     r8d, ecx
0x140020881  jnz     loc_140020B66
0x140020887  test    r8d, r8d
0x14002088a  jnz     short loc_140020895
0x14002088c  test    r9d, r9d
0x14002088f  jnz     loc_140020B66
0x140020895  mov     ebx, r15d
0x140020898  mov     r8d, 6C416553h; Tag
0x14002089e  mov     ecx, r10d; PoolType
0x1400208a1  test    r13d, r13d
0x1400208a4  jnz     short loc_1400208CA
0x1400208a6  lea     edx, [r13+8]; NumberOfBytes
0x1400208aa  call    cs:__imp_ExAllocatePoolWithTag
0x1400208b1  nop     dword ptr [rax+rax+00h]
0x1400208b6  mov     [r14], rax
0x1400208b9  test    rax, rax
0x1400208bc  jz      short loc_140020906
0x1400208be  mov     qword ptr [rax], 80002h
0x1400208c5  jmp     loc_140020B6B
0x1400208ca  mov     eax, 0FFFFh
0x1400208cf  lea     r15d, ds:0[r13*2]
0x1400208d7  add     r15d, r13d
0x1400208da  shl     r15d, 4
0x1400208de  add     r15d, 8
0x1400208e2  cmp     r15d, eax
0x1400208e5  cmova   r15d, eax
0x1400208e9  mov     edx, r15d; NumberOfBytes
0x1400208ec  mov     r12d, r15d
0x1400208ef  call    cs:__imp_ExAllocatePoolWithTag
0x1400208f6  nop     dword ptr [rax+rax+00h]
0x1400208fb  mov     [r14], rax
0x1400208fe  mov     rdi, rax
0x140020901  test    rax, rax
0x140020904  jnz     short loc_140020910
0x140020906  mov     ebx, 0C000009Ah
0x14002090b  jmp     loc_140020B6B
0x140020910  mov     r8, r12; Size
0x140020913  mov     [rbp+arg_10], 8
0x14002091a  xor     edx, edx; Val
0x14002091c  mov     rcx, rdi; void *
0x14002091f  call    memset
0x140020924  xor     eax, eax
0x140020926  mov     word ptr [rdi], 2
0x14002092b  mov     [rdi+2], r15w
0x140020930  mov     [rdi+4], eax
0x140020933  mov     [rbp+arg_8], eax
0x140020936  test    r13d, r13d
0x140020939  jz      loc_140020B3A
0x14002093f  mov     r15d, 0C000000Dh
0x140020945  xor     r12d, r12d
0x140020948  mov     dword ptr [rbp+arg_0], r12d
0x14002094c  jmp     short loc_140020952
0x14002094e  add     rsi, 2
0x140020952  movzx   eax, word ptr [rsi]
0x140020955  cmp     ax, 20h ; ' '
0x140020959  jz      short loc_14002094E
0x14002095b  lea     rdi, [rsi+2]
0x14002095f  cmp     ax, 28h ; '('
0x140020963  cmovnz  rdi, rsi
0x140020967  mov     si, 20h ; ' '
0x14002096b  jmp     short loc_140020971
0x14002096d  add     rdi, 2
0x140020971  cmp     [rdi], si
0x140020974  jz      short loc_14002096D
0x140020976  mov     r8d, 1; MaxCount
0x14002097c  lea     rdx, aA; "A"
0x140020983  mov     rcx, rdi; Str1
0x140020986  call    cs:__imp__wcsnicmp
0x14002098d  nop     dword ptr [rax+rax+00h]
0x140020992  test    eax, eax
0x140020994  jnz     loc_140020B32
0x14002099a  add     rdi, 4
0x14002099e  jmp     short loc_1400209A4
0x1400209a0  add     rdi, 2
0x1400209a4  movzx   eax, word ptr [rdi]
0x1400209a7  cmp     ax, si
0x1400209aa  jz      short loc_1400209A0
0x1400209ac  cmp     ax, 3Bh ; ';'
0x1400209b0  jnz     loc_140020B32
0x1400209b6  add     rdi, 2
0x1400209ba  movzx   eax, word ptr [rdi]
0x1400209bd  cmp     ax, si
0x1400209c0  jz      short loc_1400209B6
0x1400209c2  cmp     ax, 3Bh ; ';'
0x1400209c6  jz      loc_140020A61
0x1400209cc  cmp     ax, si
0x1400209cf  jnz     short loc_1400209DA
0x1400209d1  add     rdi, 2
0x1400209d5  cmp     [rdi], si
0x1400209d8  jz      short loc_1400209D1
0x1400209da  xor     esi, esi
0x1400209dc  lea     rax, off_140019040; "RC"
0x1400209e3  mov     r12d, esi
0x1400209e6  shl     r12, 4
0x1400209ea  mov     rcx, rdi; Str1
0x1400209ed  mov     r8d, [r12+rax+8]; MaxCount
0x1400209f2  mov     rdx, [r12+rax]; Str2
0x1400209f6  call    cs:__imp__wcsnicmp
0x1400209fd  nop     dword ptr [rax+rax+00h]
0x140020a02  test    eax, eax
0x140020a04  jz      short loc_140020A31
0x140020a06  inc     esi
0x140020a08  cmp     esi, 8
0x140020a0b  jb      short loc_1400209DC
0x140020a0d  lea     r8, [rbp+arg_0]
0x140020a11  mov     [rbp+arg_18], rdi
0x140020a15  lea     rdx, [rbp+arg_18]
0x140020a19  mov     rcx, rdi
0x140020a1c  call    SepSddlParseWideStringUlong
0x140020a21  cmp     [rbp+arg_18], rdi
0x140020a25  jz      loc_140020B32
0x140020a2b  mov     rdi, [rbp+arg_18]
0x140020a2f  jmp     short loc_140020A4C
0x140020a31  mov     eax, dword ptr [rbp+arg_0]
0x140020a34  lea     rcx, off_140019040; "RC"
0x140020a3b  or      eax, [r12+rcx+0Ch]
0x140020a40  mov     dword ptr [rbp+arg_0], eax
0x140020a43  mov     eax, [r12+rcx+8]
0x140020a48  lea     rdi, [rdi+rax*2]
0x140020a4c  movzx   eax, word ptr [rdi]
0x140020a4f  mov     si, 20h ; ' '
0x140020a53  cmp     ax, 3Bh ; ';'
0x140020a57  jnz     loc_1400209CC
0x140020a5d  mov     r12d, dword ptr [rbp+arg_0]
0x140020a61  lea     rcx, [rdi+2]
0x140020a65  test    ebx, ebx
0x140020a67  jnz     loc_140020B35
0x140020a6d  lea     edx, [rbx+2]
0x140020a70  jmp     short loc_140020A76
0x140020a72  add     rcx, 2
0x140020a76  movzx   eax, word ptr [rcx]
0x140020a79  cmp     ax, si
0x140020a7c  jz      short loc_140020A72
0x140020a7e  cmp     ax, 3Bh ; ';'
0x140020a82  cmovnz  ebx, r15d
0x140020a86  add     rcx, 2
0x140020a8a  sub     edx, 1
0x140020a8d  jnz     short loc_140020A76
0x140020a8f  test    ebx, ebx
0x140020a91  jnz     loc_140020B35
0x140020a97  jmp     short loc_140020A9D
0x140020a99  add     rcx, 2; Str1
0x140020a9d  cmp     [rcx], si
0x140020aa0  jz      short loc_140020A99
0x140020aa2  lea     r8, [rbp+arg_0]
0x140020aa6  mov     [rbp+arg_0], 0
0x140020aae  lea     rdx, [rbp+var_18]
0x140020ab2  call    SepSddlGetSidForString
0x140020ab7  mov     ebx, eax
0x140020ab9  test    eax, eax
0x140020abb  jnz     short loc_140020B2D
0x140020abd  mov     rsi, [rbp+arg_0]
0x140020ac1  test    rsi, rsi
0x140020ac4  jnz     short loc_140020AD1
0x140020ac6  mov     ebx, 0C0000077h
0x140020acb  jmp     short loc_140020B35
0x140020acd  add     rsi, 2
0x140020ad1  movzx   eax, word ptr [rsi]
0x140020ad4  cmp     ax, 20h ; ' '
0x140020ad8  jz      short loc_140020ACD
0x140020ada  cmp     ax, 29h ; ')'
0x140020ade  jnz     short loc_140020AC6
0x140020ae0  mov     rcx, [rbp+var_18]
0x140020ae4  mov     edi, [rbp+arg_8]
0x140020ae7  test    rcx, rcx
0x140020aea  jz      short loc_140020B11
0x140020aec  mov     [rsp+58h+Sid], rcx; Sid
0x140020af1  lea     rdx, [rbp+arg_10]; int
0x140020af5  mov     eax, r13d
0x140020af8  mov     rcx, r14; int
0x140020afb  sub     eax, edi
0x140020afd  mov     [rsp+58h+var_30], eax; int
0x140020b01  mov     [rsp+58h+AccessMask], r12d; AccessMask
0x140020b06  call    SepSddlAddAceToAcl
0x140020b0b  mov     ebx, eax
0x140020b0d  test    eax, eax
0x140020b0f  jnz     short loc_140020B35
0x140020b11  add     rsi, 2
0x140020b15  cmp     word ptr [rsi], 28h ; '('
0x140020b19  jnz     short loc_140020B1F
0x140020b1b  add     rsi, 2
0x140020b1f  inc     edi
0x140020b21  mov     [rbp+arg_8], edi
0x140020b24  cmp     edi, r13d
0x140020b27  jb      loc_140020945
0x140020b2d  mov     ecx, [rbp+arg_10]
0x140020b30  jmp     short loc_140020B3F
0x140020b32  mov     ebx, r15d
0x140020b35  mov     rax, [r14]
0x140020b38  jmp     short loc_140020B46
0x140020b3a  mov     ecx, 8
0x140020b3f  mov     rax, [r14]
0x140020b42  test    ebx, ebx
0x140020b44  jz      short loc_140020B60
0x140020b46  xor     edx, edx; Tag
0x140020b48  mov     rcx, rax; P
0x140020b4b  call    cs:__imp_ExFreePoolWithTag
0x140020b52  nop     dword ptr [rax+rax+00h]
0x140020b57  mov     qword ptr [r14], 0
0x140020b5e  jmp     short loc_140020B6B
0x140020b60  mov     [rax+2], cx
0x140020b64  jmp     short loc_140020B6B
0x140020b66  mov     ebx, 0C000000Dh
0x140020b6b  mov     eax, ebx
0x140020b6d  add     rsp, 58h
0x140020b71  pop     r15
0x140020b73  pop     r14
0x140020b75  pop     r13
0x140020b77  pop     r12
0x140020b79  pop     rdi
0x140020b7a  pop     rsi
0x140020b7b  pop     rbx
0x140020b7c  pop     rbp
0x140020b7d  retn
```
