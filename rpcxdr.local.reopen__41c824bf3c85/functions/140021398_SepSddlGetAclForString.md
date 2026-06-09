# SepSddlGetAclForString

- ea: `0x140021398`
- end: `0x14002174c`
- name: `SepSddlGetAclForString`
- size: `948`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400212b4`

## callees

- `0x140015b40`
- `0x1400211c0`
- `0x140021398`
- `0x140021754`
- `0x14002180c`

## import_xrefs

- `ntoskrnl!wcschr` at `0x1400213c3`
- `ntoskrnl!wcschr` at `0x1400213c3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002147a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400214bf`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002147a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400214bf`
- `ntoskrnl!_wcsnicmp` at `0x14002155c`
- `ntoskrnl!_wcsnicmp` at `0x1400215d5`
- `ntoskrnl!_wcsnicmp` at `0x14002155c`
- `ntoskrnl!_wcsnicmp` at `0x1400215d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021714`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021714`

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
  _QWORD *v15; // rax
  unsigned int v16; // r15d
  _WORD *PoolWithTag; // rax
  _WORD *v18; // rdi
  unsigned int v19; // r12d
  const wchar_t *v20; // rdi
  const wchar_t *j; // rdi
  unsigned int k; // esi
  __int64 v23; // r12
  wchar_t *v24; // rcx
  int v25; // edx
  const wchar_t *v26; // rsi
  _WORD *v27; // rcx
  ACCESS_MASK v28; // [rsp+A0h] [rbp+48h] BYREF
  unsigned int v29; // [rsp+A8h] [rbp+50h]
  int v30; // [rsp+B0h] [rbp+58h]
  const wchar_t *v31; // [rsp+B8h] [rbp+60h] BYREF

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
  if ( v13 )
  {
    v16 = 48 * v13 + 8;
    if ( v16 > 0xFFFF )
      v16 = 0xFFFF;
    PoolWithTag = ExAllocatePoolWithTag(PagedPool, v16, 0x6C416553u);
    *a2 = PoolWithTag;
    v18 = PoolWithTag;
    if ( PoolWithTag )
    {
      v30 = 8;
      memset(PoolWithTag, 0, v16);
      *v18 = 2;
      v18[1] = v16;
      v19 = 0;
      *((_DWORD *)v18 + 1) = 0;
      while ( 1 )
      {
        v29 = v19;
        if ( v19 >= v13 )
          break;
        v28 = 0;
        while ( *v5 == 32 )
          ++v5;
        v20 = v5 + 1;
        if ( *v5 != 40 )
          v20 = v5;
        while ( *v20 == 32 )
          ++v20;
        if ( _wcsnicmp(v20, L"A", 1u) )
          goto LABEL_69;
        for ( j = v20 + 2; *j == 32; ++j )
          ;
        if ( *j != 59 )
        {
LABEL_69:
          SidForString = -1073741811;
LABEL_70:
          v27 = (_WORD *)*a2;
LABEL_72:
          ExFreePoolWithTag(v27, 0);
          *a2 = 0;
          return SidForString;
        }
        do
          ++j;
        while ( *j == 32 );
LABEL_40:
        while ( *j != 59 )
        {
          for ( ; *j == 32; ++j )
            ;
          for ( k = 0; k < 8; ++k )
          {
            v23 = 2LL * k;
            if ( !_wcsnicmp(j, (&off_14001A060)[v23], *((unsigned int *)&off_14001A060 + 2 * v23 + 2)) )
            {
              v28 |= *((_DWORD *)&off_14001A060 + 2 * v23 + 3);
              j += *((unsigned int *)&off_14001A060 + 2 * v23 + 2);
              goto LABEL_40;
            }
          }
          v31 = j;
          SepSddlParseWideStringUlong(j, &v31, &v28);
          if ( v31 == j )
            goto LABEL_69;
          j = v31;
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
        v31 = 0;
        SidForString = SepSddlGetSidForString(v24);
        if ( SidForString )
          break;
        v26 = v31;
        if ( !v31 )
          goto LABEL_62;
        while ( *v26 == 32 )
          ++v26;
        if ( *v26 != 41 )
        {
LABEL_62:
          SidForString = -1073741705;
          goto LABEL_70;
        }
        v5 = (wchar_t *)(v26 + 1);
        if ( *v5 == 40 )
          ++v5;
        v19 = v29 + 1;
      }
      v27 = (_WORD *)*a2;
      if ( SidForString )
        goto LABEL_72;
      v27[1] = v30;
      return SidForString;
    }
    return (unsigned int)-1073741670;
  }
  v15 = ExAllocatePoolWithTag(PagedPool, 8u, 0x6C416553u);
  *a2 = v15;
  if ( !v15 )
    return (unsigned int)-1073741670;
  *v15 = 524290;
  return SidForString;
}

```

## disassembly

```asm
0x140021398  push    rbp
0x14002139a  push    rbx
0x14002139b  push    rsi
0x14002139c  push    rdi
0x14002139d  push    r12
0x14002139f  push    r13
0x1400213a1  push    r14
0x1400213a3  push    r15
0x1400213a5  mov     rbp, rsp
0x1400213a8  sub     rsp, 58h
0x1400213ac  xor     r15d, r15d
0x1400213af  mov     r14, rdx
0x1400213b2  mov     [rdx], r15
0x1400213b5  mov     rbx, r8
0x1400213b8  mov     rsi, rcx
0x1400213bb  mov     [rbp+var_18], r15
0x1400213bf  lea     edx, [r15+3Ah]; Ch
0x1400213c3  call    cs:__imp_wcschr
0x1400213ca  nop     dword ptr [rax+rax+00h]
0x1400213cf  mov     [rbx], rax
0x1400213d2  cmp     rax, rsi
0x1400213d5  jnz     short loc_1400213E1
0x1400213d7  mov     eax, 0C000000Dh
0x1400213dc  jmp     loc_14002173A
0x1400213e1  mov     r8d, r15d
0x1400213e4  test    rax, rax
0x1400213e7  jnz     short loc_1400213FD
0x1400213e9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400213ed  inc     rax
0x1400213f0  cmp     [rsi+rax*2], r15w
0x1400213f5  jnz     short loc_1400213ED
0x1400213f7  lea     rax, [rsi+rax*2]
0x1400213fb  jmp     short loc_140021401
0x1400213fd  add     rax, 0FFFFFFFFFFFFFFFEh
0x140021401  mov     [rbx], rax
0x140021404  mov     rcx, rsi
0x140021407  mov     r9d, r15d
0x14002140a  mov     r10d, 1
0x140021410  cmp     rsi, rax
0x140021413  jnb     short loc_140021434
0x140021415  movzx   edx, word ptr [rcx]
0x140021418  cmp     dx, 3Bh ; ';'
0x14002141c  jnz     short loc_140021423
0x14002141e  add     r8d, r10d
0x140021421  jmp     short loc_14002142B
0x140021423  cmp     dx, 20h ; ' '
0x140021427  cmovnz  r9d, r10d
0x14002142b  add     rcx, 2
0x14002142f  cmp     rcx, rax
0x140021432  jb      short loc_140021415
0x140021434  mov     eax, 0CCCCCCCDh
0x140021439  mul     r8d
0x14002143c  mov     r13d, edx
0x14002143f  shr     r13d, 2
0x140021443  lea     ecx, ds:0[r13*4]
0x14002144b  add     ecx, r13d
0x14002144e  cmp     r8d, ecx
0x140021451  jnz     loc_140021733
0x140021457  test    r8d, r8d
0x14002145a  jnz     short loc_140021465
0x14002145c  test    r9d, r9d
0x14002145f  jnz     loc_140021733
0x140021465  mov     ebx, r15d
0x140021468  mov     r8d, 6C416553h; Tag
0x14002146e  mov     ecx, r10d; PoolType
0x140021471  test    r13d, r13d
0x140021474  jnz     short loc_14002149A
0x140021476  lea     edx, [r13+8]; NumberOfBytes
0x14002147a  call    cs:__imp_ExAllocatePoolWithTag
0x140021481  nop     dword ptr [rax+rax+00h]
0x140021486  mov     [r14], rax
0x140021489  test    rax, rax
0x14002148c  jz      short loc_1400214D6
0x14002148e  mov     qword ptr [rax], 80002h
0x140021495  jmp     loc_140021738
0x14002149a  mov     eax, 0FFFFh
0x14002149f  lea     r15d, ds:0[r13*2]
0x1400214a7  add     r15d, r13d
0x1400214aa  shl     r15d, 4
0x1400214ae  add     r15d, 8
0x1400214b2  cmp     r15d, eax
0x1400214b5  cmova   r15d, eax
0x1400214b9  mov     edx, r15d; NumberOfBytes
0x1400214bc  mov     r12d, r15d
0x1400214bf  call    cs:__imp_ExAllocatePoolWithTag
0x1400214c6  nop     dword ptr [rax+rax+00h]
0x1400214cb  mov     [r14], rax
0x1400214ce  mov     rdi, rax
0x1400214d1  test    rax, rax
0x1400214d4  jnz     short loc_1400214E0
0x1400214d6  mov     ebx, 0C000009Ah
0x1400214db  jmp     loc_140021738
0x1400214e0  mov     r8, r12; Size
0x1400214e3  mov     [rbp+arg_10], 8
0x1400214ea  xor     edx, edx; Val
0x1400214ec  mov     rcx, rdi; void *
0x1400214ef  call    memset
0x1400214f4  xor     eax, eax
0x1400214f6  mov     word ptr [rdi], 2
0x1400214fb  mov     [rdi+2], r15w
0x140021500  xor     r12d, r12d
0x140021503  mov     [rdi+4], eax
0x140021506  mov     r15d, 0C000000Dh
0x14002150c  mov     [rbp+arg_8], r12d
0x140021510  cmp     r12d, r13d
0x140021513  jnb     loc_14002170B
0x140021519  mov     [rbp+arg_0], 0
0x140021520  mov     r12w, 20h ; ' '
0x140021525  jmp     short loc_14002152B
0x140021527  add     rsi, 2
0x14002152b  movzx   eax, word ptr [rsi]
0x14002152e  cmp     ax, r12w
0x140021532  jz      short loc_140021527
0x140021534  cmp     ax, 28h ; '('
0x140021538  lea     rdi, [rsi+2]
0x14002153c  cmovnz  rdi, rsi
0x140021540  jmp     short loc_140021546
0x140021542  add     rdi, 2
0x140021546  cmp     [rdi], r12w
0x14002154a  jz      short loc_140021542
0x14002154c  mov     r8d, 1; MaxCount
0x140021552  lea     rdx, aA; "A"
0x140021559  mov     rcx, rdi; Str1
0x14002155c  call    cs:__imp__wcsnicmp
0x140021563  nop     dword ptr [rax+rax+00h]
0x140021568  test    eax, eax
0x14002156a  jnz     loc_140021703
0x140021570  add     rdi, 4
0x140021574  jmp     short loc_14002157A
0x140021576  add     rdi, 2
0x14002157a  movzx   eax, word ptr [rdi]
0x14002157d  cmp     ax, r12w
0x140021581  jz      short loc_140021576
0x140021583  cmp     ax, 3Bh ; ';'
0x140021587  jnz     loc_140021703
0x14002158d  add     rdi, 2
0x140021591  cmp     [rdi], r12w
0x140021595  jz      short loc_14002158D
0x140021597  lea     rcx, off_14001A060; "RC"
0x14002159e  movzx   eax, word ptr [rdi]
0x1400215a1  cmp     ax, 3Bh ; ';'
0x1400215a5  jz      loc_140021637
0x1400215ab  cmp     ax, r12w
0x1400215af  jnz     short loc_1400215BB
0x1400215b1  add     rdi, 2
0x1400215b5  cmp     [rdi], r12w
0x1400215b9  jz      short loc_1400215B1
0x1400215bb  xor     esi, esi
0x1400215bd  cmp     esi, 8
0x1400215c0  jnb     short loc_14002160B
0x1400215c2  mov     r12d, esi
0x1400215c5  shl     r12, 4
0x1400215c9  mov     r8d, [r12+rcx+8]; MaxCount
0x1400215ce  mov     rdx, [r12+rcx]; Str2
0x1400215d2  mov     rcx, rdi; Str1
0x1400215d5  call    cs:__imp__wcsnicmp
0x1400215dc  nop     dword ptr [rax+rax+00h]
0x1400215e1  lea     rcx, off_14001A060; "RC"
0x1400215e8  test    eax, eax
0x1400215ea  jz      short loc_1400215F0
0x1400215ec  inc     esi
0x1400215ee  jmp     short loc_1400215BD
0x1400215f0  mov     eax, [rbp+arg_0]
0x1400215f3  or      eax, [r12+rcx+0Ch]
0x1400215f8  mov     [rbp+arg_0], eax
0x1400215fb  mov     eax, [r12+rcx+8]
0x140021600  mov     r12w, 20h ; ' '
0x140021605  lea     rdi, [rdi+rax*2]
0x140021609  jmp     short loc_14002159E
0x14002160b  lea     r8, [rbp+arg_0]
0x14002160f  mov     [rbp+arg_18], rdi
0x140021613  lea     rdx, [rbp+arg_18]
0x140021617  mov     rcx, rdi
0x14002161a  call    SepSddlParseWideStringUlong
0x14002161f  cmp     [rbp+arg_18], rdi
0x140021623  jz      loc_140021703
0x140021629  mov     rdi, [rbp+arg_18]
0x14002162d  mov     r12w, 20h ; ' '
0x140021632  jmp     loc_140021597
0x140021637  lea     rcx, [rdi+2]
0x14002163b  test    ebx, ebx
0x14002163d  jnz     loc_140021706
0x140021643  lea     edx, [rbx+2]
0x140021646  jmp     short loc_14002164C
0x140021648  add     rcx, 2
0x14002164c  movzx   eax, word ptr [rcx]
0x14002164f  cmp     ax, r12w
0x140021653  jz      short loc_140021648
0x140021655  cmp     ax, 3Bh ; ';'
0x140021659  cmovnz  ebx, r15d
0x14002165d  add     rcx, 2
0x140021661  sub     edx, 1
0x140021664  jnz     short loc_14002164C
0x140021666  test    ebx, ebx
0x140021668  jnz     loc_140021706
0x14002166e  jmp     short loc_140021674
0x140021670  add     rcx, 2; Str1
0x140021674  cmp     [rcx], r12w
0x140021678  jz      short loc_140021670
0x14002167a  lea     r8, [rbp+arg_18]
0x14002167e  mov     [rbp+arg_18], 0
0x140021686  lea     rdx, [rbp+var_18]
0x14002168a  call    SepSddlGetSidForString
0x14002168f  mov     ebx, eax
0x140021691  test    eax, eax
0x140021693  jnz     short loc_14002170B
0x140021695  mov     rsi, [rbp+arg_18]
0x140021699  test    rsi, rsi
0x14002169c  jnz     short loc_1400216A9
0x14002169e  mov     ebx, 0C0000077h
0x1400216a3  jmp     short loc_140021706
0x1400216a5  add     rsi, 2
0x1400216a9  movzx   eax, word ptr [rsi]
0x1400216ac  cmp     ax, r12w
0x1400216b0  jz      short loc_1400216A5
0x1400216b2  cmp     ax, 29h ; ')'
0x1400216b6  jnz     short loc_14002169E
0x1400216b8  mov     rcx, [rbp+var_18]
0x1400216bc  mov     r12d, [rbp+arg_8]
0x1400216c0  test    rcx, rcx
0x1400216c3  jz      short loc_1400216ED
0x1400216c5  mov     [rsp+58h+Sid], rcx; Sid
0x1400216ca  lea     rdx, [rbp+arg_10]; int
0x1400216ce  mov     eax, r13d
0x1400216d1  mov     rcx, r14; int
0x1400216d4  sub     eax, r12d
0x1400216d7  mov     [rsp+58h+var_30], eax; int
0x1400216db  mov     eax, [rbp+arg_0]
0x1400216de  mov     [rsp+58h+AccessMask], eax; AccessMask
0x1400216e2  call    SepSddlAddAceToAcl
0x1400216e7  mov     ebx, eax
0x1400216e9  test    eax, eax
0x1400216eb  jnz     short loc_140021706
0x1400216ed  add     rsi, 2
0x1400216f1  cmp     word ptr [rsi], 28h ; '('
0x1400216f5  jnz     short loc_1400216FB
0x1400216f7  add     rsi, 2
0x1400216fb  inc     r12d
0x1400216fe  jmp     loc_14002150C
0x140021703  mov     ebx, r15d
0x140021706  mov     rcx, [r14]
0x140021709  jmp     short loc_140021712
0x14002170b  mov     rcx, [r14]; P
0x14002170e  test    ebx, ebx
0x140021710  jz      short loc_140021729
0x140021712  xor     edx, edx; Tag
0x140021714  call    cs:__imp_ExFreePoolWithTag
0x14002171b  nop     dword ptr [rax+rax+00h]
0x140021720  mov     qword ptr [r14], 0
0x140021727  jmp     short loc_140021738
0x140021729  movzx   eax, word ptr [rbp+arg_10]
0x14002172d  mov     [rcx+2], ax
0x140021731  jmp     short loc_140021738
0x140021733  mov     ebx, 0C000000Dh
0x140021738  mov     eax, ebx
0x14002173a  add     rsp, 58h
0x14002173e  pop     r15
0x140021740  pop     r14
0x140021742  pop     r13
0x140021744  pop     r12
0x140021746  pop     rdi
0x140021747  pop     rsi
0x140021748  pop     rbx
0x140021749  pop     rbp
0x14002174a  retn
```
