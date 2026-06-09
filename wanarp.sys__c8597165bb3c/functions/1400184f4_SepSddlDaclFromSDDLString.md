# SepSddlDaclFromSDDLString

- ea: `0x1400184f4`
- end: `0x1400185d1`
- name: `SepSddlDaclFromSDDLString`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140018b14`

## callees

- `0x1400184f4`
- `0x1400185d8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001859c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001859c`

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
0x1400184f4  mov     rax, rsp
0x1400184f7  mov     [rax+10h], rbx
0x1400184fb  mov     [rax+20h], rbp
0x1400184ff  push    rsi
0x140018500  push    rdi
0x140018501  push    r14
0x140018503  sub     rsp, 20h
0x140018507  xor     r14d, r14d
0x14001850a  mov     rdi, r9
0x14001850d  mov     [rax+8], r14
0x140018511  mov     rsi, r8
0x140018514  mov     [rax+18h], r14
0x140018518  mov     [r9], r14
0x14001851b  mov     [r8], r14d
0x14001851e  jmp     short loc_140018524
0x140018520  add     rcx, 2
0x140018524  movzx   eax, word ptr [rcx]
0x140018527  cmp     ax, 20h ; ' '
0x14001852b  jz      short loc_140018520
0x14001852d  cmp     ax, 44h ; 'D'
0x140018531  jnz     loc_1400185B8
0x140018537  lea     r9, [rcx+2]
0x14001853b  cmp     word ptr [r9], 3Ah ; ':'
0x140018540  jnz     short loc_1400185B8
0x140018542  cmp     word ptr [r9+2], 50h ; 'P'
0x140018548  lea     r8, [rsp+38h+arg_10]
0x14001854d  mov     edx, 8
0x140018552  mov     ebp, 1008h
0x140018557  cmovnz  r9, rcx
0x14001855b  cmovnz  ebp, edx
0x14001855e  lea     rdx, [rsp+38h+P]; int
0x140018563  lea     rcx, [r9+4]; Str1
0x140018567  call    SepSddlGetAclForString
0x14001856c  mov     ebx, eax
0x14001856e  test    eax, eax
0x140018570  jnz     short loc_140018590
0x140018572  mov     rcx, [rsp+38h+arg_10]
0x140018577  jmp     short loc_14001857D
0x140018579  lea     rcx, [rcx+2]
0x14001857d  movzx   eax, word ptr [rcx]
0x140018580  cmp     ax, 20h ; ' '
0x140018584  jz      short loc_140018579
0x140018586  test    ax, ax
0x140018589  jz      short loc_1400185AC
0x14001858b  mov     ebx, 0C000000Dh
0x140018590  mov     rcx, [rsp+38h+P]; P
0x140018595  test    rcx, rcx
0x140018598  jz      short loc_1400185A8
0x14001859a  xor     edx, edx; Tag
0x14001859c  call    cs:__imp_ExFreePoolWithTag
0x1400185a3  nop     dword ptr [rax+rax+00h]
0x1400185a8  mov     eax, ebx
0x1400185aa  jmp     short loc_1400185BD
0x1400185ac  mov     rax, [rsp+38h+P]
0x1400185b1  mov     [rdi], rax
0x1400185b4  mov     [rsi], ebp
0x1400185b6  jmp     short loc_1400185A8
0x1400185b8  mov     eax, 0C000000Dh
0x1400185bd  mov     rbx, [rsp+38h+arg_8]
0x1400185c2  mov     rbp, [rsp+38h+arg_18]
0x1400185c7  add     rsp, 20h
0x1400185cb  pop     r14
0x1400185cd  pop     rdi
0x1400185ce  pop     rsi
0x1400185cf  retn
```
