# ParseCommaSeparatedStringToArray(ushort const *,STRU * *,ulong *,AUTH_RULE_HINT *)

- ea: `0x180019854`
- end: `0x180019a29`
- name: `?ParseCommaSeparatedStringToArray@@YAJPEBGPEAPEAVSTRU@@PEAKPEAVAUTH_RULE_HINT@@@Z`
- size: `469`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct STRU **, unsigned int *, struct AUTH_RULE_HINT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001f84`

## callees

- `0x1800011d4`
- `0x180001214`
- `0x180019854`
- `0x180023010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x1800198ef`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800199e0`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800199b2`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800199b2`

## pseudocode

```c
__int64 __fastcall ParseCommaSeparatedStringToArray(
        const unsigned __int16 *a1,
        struct STRU **a2,
        unsigned int *a3,
        struct AUTH_RULE_HINT *a4)
{
  const unsigned __int16 *v7; // rbx
  unsigned __int16 v8; // cx
  unsigned __int64 v9; // r8
  const unsigned __int16 *v10; // rdx
  bool v11; // zf
  unsigned int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rdi
  bool v15; // cf
  size_t v16; // rax
  _QWORD *v17; // rax
  struct STRU *v18; // rsi
  _QWORD *i; // rbp
  unsigned __int16 v20; // ax
  unsigned int v21; // edi
  int v22; // ebp
  const unsigned __int16 *v23; // rdx
  const unsigned __int16 *v24; // r8
  const unsigned __int16 *v25; // rax
  __int64 v26; // rbx
  char *j; // rdi

  *a2 = 0;
  *a3 = 0;
  v7 = a1;
  if ( !a1 )
    return 0;
  v8 = *a1;
  if ( !v8 )
    return 0;
  LODWORD(v9) = 1;
  v10 = v7;
  do
  {
    v11 = v8 == 44;
    v12 = v9 + 1;
    v8 = *++v10;
    if ( !v11 )
      v12 = v9;
    v9 = v12;
  }
  while ( v8 );
  v13 = 56LL * v12;
  v14 = (unsigned int)v9;
  if ( !is_mul_ok(v9, 0x38u) )
    v13 = -1;
  v15 = __CFADD__(v13, 8);
  v16 = v13 + 8;
  if ( v15 )
    v16 = -1;
  v17 = operator new(v16);
  if ( !v17 )
    return 2147942408LL;
  *v17 = v14;
  v18 = (struct STRU *)(v17 + 1);
  for ( i = v17 + 1; v14; --v14 )
  {
    ((void (__fastcall *)(_QWORD *))STRU::STRU)(i);
    i += 7;
  }
  if ( !v18 )
    return 2147942408LL;
  v20 = *v7;
  v21 = 0;
  v22 = 0;
  if ( !*v7 )
  {
LABEL_41:
    *a2 = v18;
    *a3 = v21;
    return (unsigned int)v22;
  }
  while ( 1 )
  {
    if ( v20 == 32 )
    {
      do
        ++v7;
      while ( *v7 == 32 );
    }
    v23 = v7;
    while ( *v7 != 44 && *v7 )
      ++v7;
    v24 = v7;
    if ( *v7 == 44 )
      ++v7;
    if ( v23 == v24 )
      goto LABEL_36;
    do
    {
      v25 = v24 - 1;
      if ( *(v24 - 1) != 32 )
        break;
      --v24;
    }
    while ( v23 != v25 );
    if ( v23 == v24 )
      goto LABEL_36;
    if ( !a4 || (char *)v24 - (char *)v23 != 2 )
      break;
    if ( *v23 == 42 )
    {
      *((_DWORD *)a4 + 1) = 1;
    }
    else
    {
      if ( *v23 != 63 )
        break;
      *(_DWORD *)a4 = 1;
    }
LABEL_36:
    v20 = *v7;
    if ( !*v7 )
      goto LABEL_41;
  }
  v22 = STRU::Copy((struct STRU *)((char *)v18 + 56 * v21), v23, v24 - v23);
  if ( v22 >= 0 )
  {
    ++v21;
    goto LABEL_36;
  }
  v26 = *((_QWORD *)v18 - 1);
  for ( j = (char *)v18 + 56 * v26; v26; --v26 )
  {
    j -= 56;
    ((void (__fastcall *)(char *))STRU::~STRU)(j);
  }
  operator delete((char *)v18 - 8);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x180019854  push    rbx
0x180019856  push    rbp
0x180019857  push    rsi
0x180019858  push    rdi
0x180019859  push    r12
0x18001985b  push    r13
0x18001985d  push    r14
0x18001985f  push    r15
0x180019861  sub     rsp, 28h
0x180019865  xor     r13d, r13d
0x180019868  mov     r14, r9
0x18001986b  mov     [rdx], r13
0x18001986e  mov     r15, r8
0x180019871  mov     [r8], r13d
0x180019874  mov     r12, rdx
0x180019877  mov     rbx, rcx
0x18001987a  test    rcx, rcx
0x18001987d  jz      loc_180019A16
0x180019883  movzx   ecx, word ptr [rcx]
0x180019886  test    cx, cx
0x180019889  jz      loc_180019A16
0x18001988f  lea     r8d, [r13+1]
0x180019893  mov     rdx, rbx
0x180019896  cmp     cx, 2Ch ; ','
0x18001989a  lea     eax, [r8+1]
0x18001989e  lea     rdx, [rdx+2]
0x1800198a2  movzx   ecx, word ptr [rdx]
0x1800198a5  cmovnz  eax, r8d
0x1800198a9  mov     r8d, eax
0x1800198ac  test    cx, cx
0x1800198af  jnz     short loc_180019896
0x1800198b1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800198b8  mov     eax, 38h ; '8'
0x1800198bd  mul     r8
0x1800198c0  mov     edi, r8d
0x1800198c3  cmovb   rax, rcx
0x1800198c7  add     rax, 8
0x1800198cb  cmovb   rax, rcx
0x1800198cf  mov     rcx, rax; Size
0x1800198d2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800198d7  test    rax, rax
0x1800198da  jz      loc_180019A0F
0x1800198e0  mov     [rax], rdi
0x1800198e3  lea     rsi, [rax+8]
0x1800198e7  mov     rbp, rsi
0x1800198ea  test    rdi, rdi
0x1800198ed  jz      short loc_180019908
0x1800198ef  mov     rax, cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800198f6  mov     rcx, rbp
0x1800198f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198fe  add     rbp, 38h ; '8'
0x180019902  sub     rdi, 1
0x180019906  jnz     short loc_1800198EF
0x180019908  test    rsi, rsi
0x18001990b  jz      loc_180019A0F
0x180019911  movzx   eax, word ptr [rbx]
0x180019914  mov     edi, r13d
0x180019917  mov     ebp, r13d
0x18001991a  test    ax, ax
0x18001991d  jz      loc_180019A04
0x180019923  cmp     ax, 20h ; ' '
0x180019927  jnz     short loc_180019933
0x180019929  add     rbx, 2
0x18001992d  cmp     word ptr [rbx], 20h ; ' '
0x180019931  jz      short loc_180019929
0x180019933  mov     rdx, rbx
0x180019936  jmp     short loc_180019941
0x180019938  test    ax, ax
0x18001993b  jz      short loc_18001994A
0x18001993d  add     rbx, 2
0x180019941  movzx   eax, word ptr [rbx]
0x180019944  cmp     ax, 2Ch ; ','
0x180019948  jnz     short loc_180019938
0x18001994a  cmp     word ptr [rbx], 2Ch ; ','
0x18001994e  mov     r8, rbx
0x180019951  jnz     short loc_180019957
0x180019953  add     rbx, 2
0x180019957  cmp     rdx, r8
0x18001995a  jz      short loc_1800199C0
0x18001995c  lea     rax, [r8-2]
0x180019960  cmp     word ptr [rax], 20h ; ' '
0x180019964  jnz     short loc_18001996E
0x180019966  mov     r8, rax
0x180019969  cmp     rdx, rax
0x18001996c  jnz     short loc_18001995C
0x18001996e  cmp     rdx, r8
0x180019971  jz      short loc_1800199C0
0x180019973  test    r14, r14
0x180019976  jz      short loc_1800199A3
0x180019978  mov     rax, r8
0x18001997b  sub     rax, rdx
0x18001997e  cmp     rax, 2
0x180019982  jnz     short loc_1800199A3
0x180019984  cmp     word ptr [rdx], 2Ah ; '*'
0x180019988  jnz     short loc_180019994
0x18001998a  mov     dword ptr [r14+4], 1
0x180019992  jmp     short loc_1800199C0
0x180019994  cmp     word ptr [rdx], 3Fh ; '?'
0x180019998  jnz     short loc_1800199A3
0x18001999a  mov     dword ptr [r14], 1
0x1800199a1  jmp     short loc_1800199C0
0x1800199a3  mov     eax, edi
0x1800199a5  sub     r8, rdx
0x1800199a8  imul    rcx, rax, 38h ; '8'
0x1800199ac  sar     r8, 1
0x1800199af  add     rcx, rsi
0x1800199b2  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800199b8  mov     ebp, eax
0x1800199ba  test    eax, eax
0x1800199bc  js      short loc_1800199D0
0x1800199be  inc     edi
0x1800199c0  movzx   eax, word ptr [rbx]
0x1800199c3  test    ax, ax
0x1800199c6  jnz     loc_180019923
0x1800199cc  test    ebp, ebp
0x1800199ce  jns     short loc_180019A04
0x1800199d0  mov     rbx, [rsi-8]
0x1800199d4  imul    rdi, rbx, 38h ; '8'
0x1800199d8  add     rdi, rsi
0x1800199db  test    rbx, rbx
0x1800199de  jz      short loc_1800199F9
0x1800199e0  mov     rax, cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800199e7  sub     rdi, 38h ; '8'
0x1800199eb  mov     rcx, rdi
0x1800199ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199f3  sub     rbx, 1
0x1800199f7  jnz     short loc_1800199E0
0x1800199f9  lea     rcx, [rsi-8]; Block
0x1800199fd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019a02  jmp     short loc_180019A0B
0x180019a04  mov     [r12], rsi
0x180019a08  mov     [r15], edi
0x180019a0b  mov     eax, ebp
0x180019a0d  jmp     short loc_180019A18
0x180019a0f  mov     eax, 80070008h
0x180019a14  jmp     short loc_180019A18
0x180019a16  xor     eax, eax
0x180019a18  add     rsp, 28h
0x180019a1c  pop     r15
0x180019a1e  pop     r14
0x180019a20  pop     r13
0x180019a22  pop     r12
0x180019a24  pop     rdi
0x180019a25  pop     rsi
0x180019a26  pop     rbp
0x180019a27  pop     rbx
0x180019a28  retn
```
