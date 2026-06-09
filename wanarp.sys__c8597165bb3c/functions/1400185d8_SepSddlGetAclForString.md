# SepSddlGetAclForString

- ea: `0x1400185d8`
- end: `0x14001898c`
- name: `SepSddlGetAclForString`
- size: `948`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400184f4`

## callees

- `0x1400054c0`
- `0x140018400`
- `0x1400185d8`
- `0x140018994`
- `0x140018a4c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140018954`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018954`
- `ntoskrnl!wcschr` at `0x140018603`
- `ntoskrnl!wcschr` at `0x140018603`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400186ba`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400186ff`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400186ba`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400186ff`
- `ntoskrnl!_wcsnicmp` at `0x14001879c`
- `ntoskrnl!_wcsnicmp` at `0x140018815`
- `ntoskrnl!_wcsnicmp` at `0x14001879c`
- `ntoskrnl!_wcsnicmp` at `0x140018815`

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
            if ( !_wcsnicmp(j, (&off_1400094A0)[v23], *((unsigned int *)&off_1400094A0 + 2 * v23 + 2)) )
            {
              v28 |= *((_DWORD *)&off_1400094A0 + 2 * v23 + 3);
              j += *((unsigned int *)&off_1400094A0 + 2 * v23 + 2);
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
0x1400185d8  push    rbp
0x1400185da  push    rbx
0x1400185db  push    rsi
0x1400185dc  push    rdi
0x1400185dd  push    r12
0x1400185df  push    r13
0x1400185e1  push    r14
0x1400185e3  push    r15
0x1400185e5  mov     rbp, rsp
0x1400185e8  sub     rsp, 58h
0x1400185ec  xor     r15d, r15d
0x1400185ef  mov     r14, rdx
0x1400185f2  mov     [rdx], r15
0x1400185f5  mov     rbx, r8
0x1400185f8  mov     rsi, rcx
0x1400185fb  mov     [rbp+var_18], r15
0x1400185ff  lea     edx, [r15+3Ah]; Ch
0x140018603  call    cs:__imp_wcschr
0x14001860a  nop     dword ptr [rax+rax+00h]
0x14001860f  mov     [rbx], rax
0x140018612  cmp     rax, rsi
0x140018615  jnz     short loc_140018621
0x140018617  mov     eax, 0C000000Dh
0x14001861c  jmp     loc_14001897A
0x140018621  mov     r8d, r15d
0x140018624  test    rax, rax
0x140018627  jnz     short loc_14001863D
0x140018629  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001862d  inc     rax
0x140018630  cmp     [rsi+rax*2], r15w
0x140018635  jnz     short loc_14001862D
0x140018637  lea     rax, [rsi+rax*2]
0x14001863b  jmp     short loc_140018641
0x14001863d  add     rax, 0FFFFFFFFFFFFFFFEh
0x140018641  mov     [rbx], rax
0x140018644  mov     rcx, rsi
0x140018647  mov     r9d, r15d
0x14001864a  mov     r10d, 1
0x140018650  cmp     rsi, rax
0x140018653  jnb     short loc_140018674
0x140018655  movzx   edx, word ptr [rcx]
0x140018658  cmp     dx, 3Bh ; ';'
0x14001865c  jnz     short loc_140018663
0x14001865e  add     r8d, r10d
0x140018661  jmp     short loc_14001866B
0x140018663  cmp     dx, 20h ; ' '
0x140018667  cmovnz  r9d, r10d
0x14001866b  add     rcx, 2
0x14001866f  cmp     rcx, rax
0x140018672  jb      short loc_140018655
0x140018674  mov     eax, 0CCCCCCCDh
0x140018679  mul     r8d
0x14001867c  mov     r13d, edx
0x14001867f  shr     r13d, 2
0x140018683  lea     ecx, ds:0[r13*4]
0x14001868b  add     ecx, r13d
0x14001868e  cmp     r8d, ecx
0x140018691  jnz     loc_140018973
0x140018697  test    r8d, r8d
0x14001869a  jnz     short loc_1400186A5
0x14001869c  test    r9d, r9d
0x14001869f  jnz     loc_140018973
0x1400186a5  mov     ebx, r15d
0x1400186a8  mov     r8d, 6C416553h; Tag
0x1400186ae  mov     ecx, r10d; PoolType
0x1400186b1  test    r13d, r13d
0x1400186b4  jnz     short loc_1400186DA
0x1400186b6  lea     edx, [r13+8]; NumberOfBytes
0x1400186ba  call    cs:__imp_ExAllocatePoolWithTag
0x1400186c1  nop     dword ptr [rax+rax+00h]
0x1400186c6  mov     [r14], rax
0x1400186c9  test    rax, rax
0x1400186cc  jz      short loc_140018716
0x1400186ce  mov     qword ptr [rax], 80002h
0x1400186d5  jmp     loc_140018978
0x1400186da  mov     eax, 0FFFFh
0x1400186df  lea     r15d, ds:0[r13*2]
0x1400186e7  add     r15d, r13d
0x1400186ea  shl     r15d, 4
0x1400186ee  add     r15d, 8
0x1400186f2  cmp     r15d, eax
0x1400186f5  cmova   r15d, eax
0x1400186f9  mov     edx, r15d; NumberOfBytes
0x1400186fc  mov     r12d, r15d
0x1400186ff  call    cs:__imp_ExAllocatePoolWithTag
0x140018706  nop     dword ptr [rax+rax+00h]
0x14001870b  mov     [r14], rax
0x14001870e  mov     rdi, rax
0x140018711  test    rax, rax
0x140018714  jnz     short loc_140018720
0x140018716  mov     ebx, 0C000009Ah
0x14001871b  jmp     loc_140018978
0x140018720  mov     r8, r12; Size
0x140018723  mov     [rbp+arg_10], 8
0x14001872a  xor     edx, edx; Val
0x14001872c  mov     rcx, rdi; void *
0x14001872f  call    memset
0x140018734  xor     eax, eax
0x140018736  mov     word ptr [rdi], 2
0x14001873b  mov     [rdi+2], r15w
0x140018740  xor     r12d, r12d
0x140018743  mov     [rdi+4], eax
0x140018746  mov     r15d, 0C000000Dh
0x14001874c  mov     [rbp+arg_8], r12d
0x140018750  cmp     r12d, r13d
0x140018753  jnb     loc_14001894B
0x140018759  mov     [rbp+arg_0], 0
0x140018760  mov     r12w, 20h ; ' '
0x140018765  jmp     short loc_14001876B
0x140018767  add     rsi, 2
0x14001876b  movzx   eax, word ptr [rsi]
0x14001876e  cmp     ax, r12w
0x140018772  jz      short loc_140018767
0x140018774  cmp     ax, 28h ; '('
0x140018778  lea     rdi, [rsi+2]
0x14001877c  cmovnz  rdi, rsi
0x140018780  jmp     short loc_140018786
0x140018782  add     rdi, 2
0x140018786  cmp     [rdi], r12w
0x14001878a  jz      short loc_140018782
0x14001878c  mov     r8d, 1; MaxCount
0x140018792  lea     rdx, aA; "A"
0x140018799  mov     rcx, rdi; Str1
0x14001879c  call    cs:__imp__wcsnicmp
0x1400187a3  nop     dword ptr [rax+rax+00h]
0x1400187a8  test    eax, eax
0x1400187aa  jnz     loc_140018943
0x1400187b0  add     rdi, 4
0x1400187b4  jmp     short loc_1400187BA
0x1400187b6  add     rdi, 2
0x1400187ba  movzx   eax, word ptr [rdi]
0x1400187bd  cmp     ax, r12w
0x1400187c1  jz      short loc_1400187B6
0x1400187c3  cmp     ax, 3Bh ; ';'
0x1400187c7  jnz     loc_140018943
0x1400187cd  add     rdi, 2
0x1400187d1  cmp     [rdi], r12w
0x1400187d5  jz      short loc_1400187CD
0x1400187d7  lea     rcx, off_1400094A0; "RC"
0x1400187de  movzx   eax, word ptr [rdi]
0x1400187e1  cmp     ax, 3Bh ; ';'
0x1400187e5  jz      loc_140018877
0x1400187eb  cmp     ax, r12w
0x1400187ef  jnz     short loc_1400187FB
0x1400187f1  add     rdi, 2
0x1400187f5  cmp     [rdi], r12w
0x1400187f9  jz      short loc_1400187F1
0x1400187fb  xor     esi, esi
0x1400187fd  cmp     esi, 8
0x140018800  jnb     short loc_14001884B
0x140018802  mov     r12d, esi
0x140018805  shl     r12, 4
0x140018809  mov     r8d, [r12+rcx+8]; MaxCount
0x14001880e  mov     rdx, [r12+rcx]; Str2
0x140018812  mov     rcx, rdi; Str1
0x140018815  call    cs:__imp__wcsnicmp
0x14001881c  nop     dword ptr [rax+rax+00h]
0x140018821  lea     rcx, off_1400094A0; "RC"
0x140018828  test    eax, eax
0x14001882a  jz      short loc_140018830
0x14001882c  inc     esi
0x14001882e  jmp     short loc_1400187FD
0x140018830  mov     eax, [rbp+arg_0]
0x140018833  or      eax, [r12+rcx+0Ch]
0x140018838  mov     [rbp+arg_0], eax
0x14001883b  mov     eax, [r12+rcx+8]
0x140018840  mov     r12w, 20h ; ' '
0x140018845  lea     rdi, [rdi+rax*2]
0x140018849  jmp     short loc_1400187DE
0x14001884b  lea     r8, [rbp+arg_0]
0x14001884f  mov     [rbp+arg_18], rdi
0x140018853  lea     rdx, [rbp+arg_18]
0x140018857  mov     rcx, rdi
0x14001885a  call    SepSddlParseWideStringUlong
0x14001885f  cmp     [rbp+arg_18], rdi
0x140018863  jz      loc_140018943
0x140018869  mov     rdi, [rbp+arg_18]
0x14001886d  mov     r12w, 20h ; ' '
0x140018872  jmp     loc_1400187D7
0x140018877  lea     rcx, [rdi+2]
0x14001887b  test    ebx, ebx
0x14001887d  jnz     loc_140018946
0x140018883  lea     edx, [rbx+2]
0x140018886  jmp     short loc_14001888C
0x140018888  add     rcx, 2
0x14001888c  movzx   eax, word ptr [rcx]
0x14001888f  cmp     ax, r12w
0x140018893  jz      short loc_140018888
0x140018895  cmp     ax, 3Bh ; ';'
0x140018899  cmovnz  ebx, r15d
0x14001889d  add     rcx, 2
0x1400188a1  sub     edx, 1
0x1400188a4  jnz     short loc_14001888C
0x1400188a6  test    ebx, ebx
0x1400188a8  jnz     loc_140018946
0x1400188ae  jmp     short loc_1400188B4
0x1400188b0  add     rcx, 2; Str1
0x1400188b4  cmp     [rcx], r12w
0x1400188b8  jz      short loc_1400188B0
0x1400188ba  lea     r8, [rbp+arg_18]
0x1400188be  mov     [rbp+arg_18], 0
0x1400188c6  lea     rdx, [rbp+var_18]
0x1400188ca  call    SepSddlGetSidForString
0x1400188cf  mov     ebx, eax
0x1400188d1  test    eax, eax
0x1400188d3  jnz     short loc_14001894B
0x1400188d5  mov     rsi, [rbp+arg_18]
0x1400188d9  test    rsi, rsi
0x1400188dc  jnz     short loc_1400188E9
0x1400188de  mov     ebx, 0C0000077h
0x1400188e3  jmp     short loc_140018946
0x1400188e5  add     rsi, 2
0x1400188e9  movzx   eax, word ptr [rsi]
0x1400188ec  cmp     ax, r12w
0x1400188f0  jz      short loc_1400188E5
0x1400188f2  cmp     ax, 29h ; ')'
0x1400188f6  jnz     short loc_1400188DE
0x1400188f8  mov     rcx, [rbp+var_18]
0x1400188fc  mov     r12d, [rbp+arg_8]
0x140018900  test    rcx, rcx
0x140018903  jz      short loc_14001892D
0x140018905  mov     [rsp+58h+Sid], rcx; Sid
0x14001890a  lea     rdx, [rbp+arg_10]; int
0x14001890e  mov     eax, r13d
0x140018911  mov     rcx, r14; int
0x140018914  sub     eax, r12d
0x140018917  mov     [rsp+58h+var_30], eax; int
0x14001891b  mov     eax, [rbp+arg_0]
0x14001891e  mov     [rsp+58h+AccessMask], eax; AccessMask
0x140018922  call    SepSddlAddAceToAcl
0x140018927  mov     ebx, eax
0x140018929  test    eax, eax
0x14001892b  jnz     short loc_140018946
0x14001892d  add     rsi, 2
0x140018931  cmp     word ptr [rsi], 28h ; '('
0x140018935  jnz     short loc_14001893B
0x140018937  add     rsi, 2
0x14001893b  inc     r12d
0x14001893e  jmp     loc_14001874C
0x140018943  mov     ebx, r15d
0x140018946  mov     rcx, [r14]
0x140018949  jmp     short loc_140018952
0x14001894b  mov     rcx, [r14]; P
0x14001894e  test    ebx, ebx
0x140018950  jz      short loc_140018969
0x140018952  xor     edx, edx; Tag
0x140018954  call    cs:__imp_ExFreePoolWithTag
0x14001895b  nop     dword ptr [rax+rax+00h]
0x140018960  mov     qword ptr [r14], 0
0x140018967  jmp     short loc_140018978
0x140018969  movzx   eax, word ptr [rbp+arg_10]
0x14001896d  mov     [rcx+2], ax
0x140018971  jmp     short loc_140018978
0x140018973  mov     ebx, 0C000000Dh
0x140018978  mov     eax, ebx
0x14001897a  add     rsp, 58h
0x14001897e  pop     r15
0x140018980  pop     r14
0x140018982  pop     r13
0x140018984  pop     r12
0x140018986  pop     rdi
0x140018987  pop     rsi
0x140018988  pop     rbx
0x140018989  pop     rbp
0x14001898a  retn
```
