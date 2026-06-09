# SepSddlDaclFromSDDLString

- ea: `0x1400212b4`
- end: `0x140021391`
- name: `SepSddlDaclFromSDDLString`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400218d4`

## callees

- `0x1400212b4`
- `0x140021398`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002135c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002135c`

## pseudocode

```c
__int64 __fastcall SepSddlDaclFromSDDLString(_WORD *a1, __int64 a2, int *a3, PVOID *a4)
{
  _WORD *v6; // r9
  int v7; // ebp
  unsigned int AclForString; // ebx
  wchar_t *i; // rcx
  PVOID P; // [rsp+40h] [rbp+8h] BYREF
  wchar_t *v12; // [rsp+50h] [rbp+18h] BYREF

  P = 0;
  v12 = 0;
  *a4 = 0;
  *a3 = 0;
  while ( *a1 == 32 )
    ++a1;
  if ( *a1 == 68 )
  {
    v6 = a1 + 1;
    if ( a1[1] == 58 )
    {
      v7 = 4104;
      if ( a1[2] != 80 )
      {
        v6 = a1;
        v7 = 8;
      }
      AclForString = SepSddlGetAclForString(v6 + 2, &P, &v12);
      if ( !AclForString )
      {
        for ( i = v12; *i == 32; ++i )
          ;
        if ( !*i )
        {
          *a4 = P;
          *a3 = v7;
          return AclForString;
        }
        AclForString = -1073741811;
      }
      if ( P )
        ExFreePoolWithTag(P, 0);
      return AclForString;
    }
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x1400212b4  mov     rax, rsp
0x1400212b7  mov     [rax+10h], rbx
0x1400212bb  mov     [rax+20h], rbp
0x1400212bf  push    rsi
0x1400212c0  push    rdi
0x1400212c1  push    r14
0x1400212c3  sub     rsp, 20h
0x1400212c7  xor     r14d, r14d
0x1400212ca  mov     rdi, r9
0x1400212cd  mov     [rax+8], r14
0x1400212d1  mov     rsi, r8
0x1400212d4  mov     [rax+18h], r14
0x1400212d8  mov     [r9], r14
0x1400212db  mov     [r8], r14d
0x1400212de  jmp     short loc_1400212E4
0x1400212e0  add     rcx, 2
0x1400212e4  movzx   eax, word ptr [rcx]
0x1400212e7  cmp     ax, 20h ; ' '
0x1400212eb  jz      short loc_1400212E0
0x1400212ed  cmp     ax, 44h ; 'D'
0x1400212f1  jnz     loc_140021378
0x1400212f7  lea     r9, [rcx+2]
0x1400212fb  cmp     word ptr [r9], 3Ah ; ':'
0x140021300  jnz     short loc_140021378
0x140021302  cmp     word ptr [r9+2], 50h ; 'P'
0x140021308  lea     r8, [rsp+38h+arg_10]
0x14002130d  mov     edx, 8
0x140021312  mov     ebp, 1008h
0x140021317  cmovnz  r9, rcx
0x14002131b  cmovnz  ebp, edx
0x14002131e  lea     rdx, [rsp+38h+P]; int
0x140021323  lea     rcx, [r9+4]; Str1
0x140021327  call    SepSddlGetAclForString
0x14002132c  mov     ebx, eax
0x14002132e  test    eax, eax
0x140021330  jnz     short loc_140021350
0x140021332  mov     rcx, [rsp+38h+arg_10]
0x140021337  jmp     short loc_14002133D
0x140021339  lea     rcx, [rcx+2]
0x14002133d  movzx   eax, word ptr [rcx]
0x140021340  cmp     ax, 20h ; ' '
0x140021344  jz      short loc_140021339
0x140021346  test    ax, ax
0x140021349  jz      short loc_14002136C
0x14002134b  mov     ebx, 0C000000Dh
0x140021350  mov     rcx, [rsp+38h+P]; P
0x140021355  test    rcx, rcx
0x140021358  jz      short loc_140021368
0x14002135a  xor     edx, edx; Tag
0x14002135c  call    cs:__imp_ExFreePoolWithTag
0x140021363  nop     dword ptr [rax+rax+00h]
0x140021368  mov     eax, ebx
0x14002136a  jmp     short loc_14002137D
0x14002136c  mov     rax, [rsp+38h+P]
0x140021371  mov     [rdi], rax
0x140021374  mov     [rsi], ebp
0x140021376  jmp     short loc_140021368
0x140021378  mov     eax, 0C000000Dh
0x14002137d  mov     rbx, [rsp+38h+arg_8]
0x140021382  mov     rbp, [rsp+38h+arg_18]
0x140021387  add     rsp, 20h
0x14002138b  pop     r14
0x14002138d  pop     rdi
0x14002138e  pop     rsi
0x14002138f  retn
```
