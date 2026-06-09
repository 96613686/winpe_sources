# SepSddlGetAclForString

- ea: `0x14004eddc`
- end: `0x14004f182`
- name: `SepSddlGetAclForString`
- size: `934`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14004ed00`

## callees

- `0x14001ad12`
- `0x140039b40`
- `0x14004ec0c`
- `0x14004eddc`
- `0x14004f188`
- `0x14004f238`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004f14a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f14a`
- `ntoskrnl!wcschr` at `0x14004ee07`
- `ntoskrnl!wcschr` at `0x14004ee07`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004eebe`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004ef03`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004eebe`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004ef03`

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
        if ( wcsnicmp_0(v20, L"A", 1u) )
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
            if ( !wcsnicmp_0(j, (&off_140047360)[v23], *((unsigned int *)&off_140047360 + 2 * v23 + 2)) )
            {
              v28 |= *((_DWORD *)&off_140047360 + 2 * v23 + 3);
              j += *((unsigned int *)&off_140047360 + 2 * v23 + 2);
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
0x14004eddc  push    rbp
0x14004edde  push    rbx
0x14004eddf  push    rsi
0x14004ede0  push    rdi
0x14004ede1  push    r12
0x14004ede3  push    r13
0x14004ede5  push    r14
0x14004ede7  push    r15
0x14004ede9  mov     rbp, rsp
0x14004edec  sub     rsp, 58h
0x14004edf0  xor     r15d, r15d
0x14004edf3  mov     r14, rdx
0x14004edf6  mov     [rdx], r15
0x14004edf9  mov     rbx, r8
0x14004edfc  mov     rsi, rcx
0x14004edff  mov     [rbp+var_18], r15
0x14004ee03  lea     edx, [r15+3Ah]; Ch
0x14004ee07  call    cs:__imp_wcschr
0x14004ee0e  nop     dword ptr [rax+rax+00h]
0x14004ee13  mov     [rbx], rax
0x14004ee16  cmp     rax, rsi
0x14004ee19  jnz     short loc_14004EE25
0x14004ee1b  mov     eax, 0C000000Dh
0x14004ee20  jmp     loc_14004F170
0x14004ee25  mov     r8d, r15d
0x14004ee28  test    rax, rax
0x14004ee2b  jnz     short loc_14004EE41
0x14004ee2d  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004ee31  inc     rax
0x14004ee34  cmp     [rsi+rax*2], r15w
0x14004ee39  jnz     short loc_14004EE31
0x14004ee3b  lea     rax, [rsi+rax*2]
0x14004ee3f  jmp     short loc_14004EE45
0x14004ee41  add     rax, 0FFFFFFFFFFFFFFFEh
0x14004ee45  mov     [rbx], rax
0x14004ee48  mov     rcx, rsi
0x14004ee4b  mov     r9d, r15d
0x14004ee4e  mov     r10d, 1
0x14004ee54  cmp     rsi, rax
0x14004ee57  jnb     short loc_14004EE78
0x14004ee59  movzx   edx, word ptr [rcx]
0x14004ee5c  cmp     dx, 3Bh ; ';'
0x14004ee60  jnz     short loc_14004EE67
0x14004ee62  add     r8d, r10d
0x14004ee65  jmp     short loc_14004EE6F
0x14004ee67  cmp     dx, 20h ; ' '
0x14004ee6b  cmovnz  r9d, r10d
0x14004ee6f  add     rcx, 2
0x14004ee73  cmp     rcx, rax
0x14004ee76  jb      short loc_14004EE59
0x14004ee78  mov     eax, 0CCCCCCCDh
0x14004ee7d  mul     r8d
0x14004ee80  mov     r13d, edx
0x14004ee83  shr     r13d, 2
0x14004ee87  lea     ecx, ds:0[r13*4]
0x14004ee8f  add     ecx, r13d
0x14004ee92  cmp     r8d, ecx
0x14004ee95  jnz     loc_14004F169
0x14004ee9b  test    r8d, r8d
0x14004ee9e  jnz     short loc_14004EEA9
0x14004eea0  test    r9d, r9d
0x14004eea3  jnz     loc_14004F169
0x14004eea9  mov     ebx, r15d
0x14004eeac  mov     r8d, 6C416553h; Tag
0x14004eeb2  mov     ecx, r10d; PoolType
0x14004eeb5  test    r13d, r13d
0x14004eeb8  jnz     short loc_14004EEDE
0x14004eeba  lea     edx, [r13+8]; NumberOfBytes
0x14004eebe  call    cs:__imp_ExAllocatePoolWithTag
0x14004eec5  nop     dword ptr [rax+rax+00h]
0x14004eeca  mov     [r14], rax
0x14004eecd  test    rax, rax
0x14004eed0  jz      short loc_14004EF1A
0x14004eed2  mov     qword ptr [rax], 80002h
0x14004eed9  jmp     loc_14004F16E
0x14004eede  mov     eax, 0FFFFh
0x14004eee3  lea     r15d, ds:0[r13*2]
0x14004eeeb  add     r15d, r13d
0x14004eeee  shl     r15d, 4
0x14004eef2  add     r15d, 8
0x14004eef6  cmp     r15d, eax
0x14004eef9  cmova   r15d, eax
0x14004eefd  mov     edx, r15d; NumberOfBytes
0x14004ef00  mov     r12d, r15d
0x14004ef03  call    cs:__imp_ExAllocatePoolWithTag
0x14004ef0a  nop     dword ptr [rax+rax+00h]
0x14004ef0f  mov     [r14], rax
0x14004ef12  mov     rdi, rax
0x14004ef15  test    rax, rax
0x14004ef18  jnz     short loc_14004EF24
0x14004ef1a  mov     ebx, 0C000009Ah
0x14004ef1f  jmp     loc_14004F16E
0x14004ef24  mov     r8, r12; Size
0x14004ef27  mov     [rbp+arg_10], 8
0x14004ef2e  xor     edx, edx; Val
0x14004ef30  mov     rcx, rdi; void *
0x14004ef33  call    memset
0x14004ef38  xor     eax, eax
0x14004ef3a  mov     word ptr [rdi], 2
0x14004ef3f  mov     [rdi+2], r15w
0x14004ef44  xor     r12d, r12d
0x14004ef47  mov     [rdi+4], eax
0x14004ef4a  mov     r15d, 0C000000Dh
0x14004ef50  mov     [rbp+arg_8], r12d
0x14004ef54  cmp     r12d, r13d
0x14004ef57  jnb     loc_14004F141
0x14004ef5d  mov     [rbp+arg_0], 0
0x14004ef64  mov     r12w, 20h ; ' '
0x14004ef69  jmp     short loc_14004EF6F
0x14004ef6b  add     rsi, 2
0x14004ef6f  movzx   eax, word ptr [rsi]
0x14004ef72  cmp     ax, r12w
0x14004ef76  jz      short loc_14004EF6B
0x14004ef78  cmp     ax, 28h ; '('
0x14004ef7c  lea     rdi, [rsi+2]
0x14004ef80  cmovnz  rdi, rsi
0x14004ef84  jmp     short loc_14004EF8A
0x14004ef86  add     rdi, 2
0x14004ef8a  cmp     [rdi], r12w
0x14004ef8e  jz      short loc_14004EF86
0x14004ef90  mov     r8d, 1; MaxCount
0x14004ef96  lea     rdx, aA; "A"
0x14004ef9d  mov     rcx, rdi; Str1
0x14004efa0  call    _wcsnicmp_0
0x14004efa5  test    eax, eax
0x14004efa7  jnz     loc_14004F139
0x14004efad  add     rdi, 4
0x14004efb1  jmp     short loc_14004EFB7
0x14004efb3  add     rdi, 2
0x14004efb7  movzx   eax, word ptr [rdi]
0x14004efba  cmp     ax, r12w
0x14004efbe  jz      short loc_14004EFB3
0x14004efc0  cmp     ax, 3Bh ; ';'
0x14004efc4  jnz     loc_14004F139
0x14004efca  add     rdi, 2
0x14004efce  cmp     [rdi], r12w
0x14004efd2  jz      short loc_14004EFCA
0x14004efd4  lea     rcx, off_140047360; "RC"
0x14004efdb  movzx   eax, word ptr [rdi]
0x14004efde  cmp     ax, 3Bh ; ';'
0x14004efe2  jz      loc_14004F06D
0x14004efe8  cmp     ax, r12w
0x14004efec  jnz     short loc_14004EFF8
0x14004efee  add     rdi, 2
0x14004eff2  cmp     [rdi], r12w
0x14004eff6  jz      short loc_14004EFEE
0x14004eff8  xor     esi, esi
0x14004effa  cmp     esi, 8
0x14004effd  jnb     short loc_14004F041
0x14004efff  mov     r12d, esi
0x14004f002  shl     r12, 4
0x14004f006  mov     r8d, [r12+rcx+8]; MaxCount
0x14004f00b  mov     rdx, [r12+rcx]; Str2
0x14004f00f  mov     rcx, rdi; Str1
0x14004f012  call    _wcsnicmp_0
0x14004f017  lea     rcx, off_140047360; "RC"
0x14004f01e  test    eax, eax
0x14004f020  jz      short loc_14004F026
0x14004f022  inc     esi
0x14004f024  jmp     short loc_14004EFFA
0x14004f026  mov     eax, [rbp+arg_0]
0x14004f029  or      eax, [r12+rcx+0Ch]
0x14004f02e  mov     [rbp+arg_0], eax
0x14004f031  mov     eax, [r12+rcx+8]
0x14004f036  mov     r12w, 20h ; ' '
0x14004f03b  lea     rdi, [rdi+rax*2]
0x14004f03f  jmp     short loc_14004EFDB
0x14004f041  lea     r8, [rbp+arg_0]
0x14004f045  mov     [rbp+arg_18], rdi
0x14004f049  lea     rdx, [rbp+arg_18]
0x14004f04d  mov     rcx, rdi
0x14004f050  call    SepSddlParseWideStringUlong
0x14004f055  cmp     [rbp+arg_18], rdi
0x14004f059  jz      loc_14004F139
0x14004f05f  mov     rdi, [rbp+arg_18]
0x14004f063  mov     r12w, 20h ; ' '
0x14004f068  jmp     loc_14004EFD4
0x14004f06d  lea     rcx, [rdi+2]
0x14004f071  test    ebx, ebx
0x14004f073  jnz     loc_14004F13C
0x14004f079  lea     edx, [rbx+2]
0x14004f07c  jmp     short loc_14004F082
0x14004f07e  add     rcx, 2
0x14004f082  movzx   eax, word ptr [rcx]
0x14004f085  cmp     ax, r12w
0x14004f089  jz      short loc_14004F07E
0x14004f08b  cmp     ax, 3Bh ; ';'
0x14004f08f  cmovnz  ebx, r15d
0x14004f093  add     rcx, 2
0x14004f097  sub     edx, 1
0x14004f09a  jnz     short loc_14004F082
0x14004f09c  test    ebx, ebx
0x14004f09e  jnz     loc_14004F13C
0x14004f0a4  jmp     short loc_14004F0AA
0x14004f0a6  add     rcx, 2; Str1
0x14004f0aa  cmp     [rcx], r12w
0x14004f0ae  jz      short loc_14004F0A6
0x14004f0b0  lea     r8, [rbp+arg_18]
0x14004f0b4  mov     [rbp+arg_18], 0
0x14004f0bc  lea     rdx, [rbp+var_18]
0x14004f0c0  call    SepSddlGetSidForString
0x14004f0c5  mov     ebx, eax
0x14004f0c7  test    eax, eax
0x14004f0c9  jnz     short loc_14004F141
0x14004f0cb  mov     rsi, [rbp+arg_18]
0x14004f0cf  test    rsi, rsi
0x14004f0d2  jnz     short loc_14004F0DF
0x14004f0d4  mov     ebx, 0C0000077h
0x14004f0d9  jmp     short loc_14004F13C
0x14004f0db  add     rsi, 2
0x14004f0df  movzx   eax, word ptr [rsi]
0x14004f0e2  cmp     ax, r12w
0x14004f0e6  jz      short loc_14004F0DB
0x14004f0e8  cmp     ax, 29h ; ')'
0x14004f0ec  jnz     short loc_14004F0D4
0x14004f0ee  mov     rcx, [rbp+var_18]
0x14004f0f2  mov     r12d, [rbp+arg_8]
0x14004f0f6  test    rcx, rcx
0x14004f0f9  jz      short loc_14004F123
0x14004f0fb  mov     [rsp+58h+Sid], rcx; Sid
0x14004f100  lea     rdx, [rbp+arg_10]; int
0x14004f104  mov     eax, r13d
0x14004f107  mov     rcx, r14; int
0x14004f10a  sub     eax, r12d
0x14004f10d  mov     [rsp+58h+var_30], eax; int
0x14004f111  mov     eax, [rbp+arg_0]
0x14004f114  mov     [rsp+58h+AccessMask], eax; AccessMask
0x14004f118  call    SepSddlAddAceToAcl
0x14004f11d  mov     ebx, eax
0x14004f11f  test    eax, eax
0x14004f121  jnz     short loc_14004F13C
0x14004f123  add     rsi, 2
0x14004f127  cmp     word ptr [rsi], 28h ; '('
0x14004f12b  jnz     short loc_14004F131
0x14004f12d  add     rsi, 2
0x14004f131  inc     r12d
0x14004f134  jmp     loc_14004EF50
0x14004f139  mov     ebx, r15d
0x14004f13c  mov     rcx, [r14]
0x14004f13f  jmp     short loc_14004F148
0x14004f141  mov     rcx, [r14]; P
0x14004f144  test    ebx, ebx
0x14004f146  jz      short loc_14004F15F
0x14004f148  xor     edx, edx; Tag
0x14004f14a  call    cs:__imp_ExFreePoolWithTag
0x14004f151  nop     dword ptr [rax+rax+00h]
0x14004f156  mov     qword ptr [r14], 0
0x14004f15d  jmp     short loc_14004F16E
0x14004f15f  movzx   eax, word ptr [rbp+arg_10]
0x14004f163  mov     [rcx+2], ax
0x14004f167  jmp     short loc_14004F16E
0x14004f169  mov     ebx, 0C000000Dh
0x14004f16e  mov     eax, ebx
0x14004f170  add     rsp, 58h
0x14004f174  pop     r15
0x14004f176  pop     r14
0x14004f178  pop     r13
0x14004f17a  pop     r12
0x14004f17c  pop     rdi
0x14004f17d  pop     rsi
0x14004f17e  pop     rbx
0x14004f17f  pop     rbp
0x14004f180  retn
```
