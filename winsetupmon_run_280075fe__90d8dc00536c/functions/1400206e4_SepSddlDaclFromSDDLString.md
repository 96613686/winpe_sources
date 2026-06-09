# SepSddlDaclFromSDDLString

- ea: `0x1400206e4`
- end: `0x1400207c1`
- name: `SepSddlDaclFromSDDLString`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140020d14`

## callees

- `0x1400206e4`
- `0x1400207c8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002078c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002078c`

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
0x1400206e4  mov     rax, rsp
0x1400206e7  mov     [rax+10h], rbx
0x1400206eb  mov     [rax+20h], rbp
0x1400206ef  push    rsi
0x1400206f0  push    rdi
0x1400206f1  push    r14
0x1400206f3  sub     rsp, 20h
0x1400206f7  xor     r14d, r14d
0x1400206fa  mov     rdi, r9
0x1400206fd  mov     [rax+8], r14
0x140020701  mov     rsi, r8
0x140020704  mov     [rax+18h], r14
0x140020708  mov     [r9], r14
0x14002070b  mov     [r8], r14d
0x14002070e  jmp     short loc_140020714
0x140020710  add     rcx, 2
0x140020714  movzx   eax, word ptr [rcx]
0x140020717  cmp     ax, 20h ; ' '
0x14002071b  jz      short loc_140020710
0x14002071d  cmp     ax, 44h ; 'D'
0x140020721  jnz     loc_1400207A8
0x140020727  lea     r9, [rcx+2]
0x14002072b  cmp     word ptr [r9], 3Ah ; ':'
0x140020730  jnz     short loc_1400207A8
0x140020732  cmp     word ptr [r9+2], 50h ; 'P'
0x140020738  lea     r8, [rsp+38h+arg_10]
0x14002073d  mov     edx, 8
0x140020742  mov     ebp, 1008h
0x140020747  cmovnz  r9, rcx
0x14002074b  cmovnz  ebp, edx
0x14002074e  lea     rdx, [rsp+38h+P]; int
0x140020753  lea     rcx, [r9+4]; Str1
0x140020757  call    SepSddlGetAclForString
0x14002075c  mov     ebx, eax
0x14002075e  test    eax, eax
0x140020760  jnz     short loc_140020780
0x140020762  mov     rcx, [rsp+38h+arg_10]
0x140020767  jmp     short loc_14002076D
0x140020769  lea     rcx, [rcx+2]
0x14002076d  movzx   eax, word ptr [rcx]
0x140020770  cmp     ax, 20h ; ' '
0x140020774  jz      short loc_140020769
0x140020776  test    ax, ax
0x140020779  jz      short loc_14002079C
0x14002077b  mov     ebx, 0C000000Dh
0x140020780  mov     rcx, [rsp+38h+P]; P
0x140020785  test    rcx, rcx
0x140020788  jz      short loc_140020798
0x14002078a  xor     edx, edx; Tag
0x14002078c  call    cs:__imp_ExFreePoolWithTag
0x140020793  nop     dword ptr [rax+rax+00h]
0x140020798  mov     eax, ebx
0x14002079a  jmp     short loc_1400207AD
0x14002079c  mov     rax, [rsp+38h+P]
0x1400207a1  mov     [rdi], rax
0x1400207a4  mov     [rsi], ebp
0x1400207a6  jmp     short loc_140020798
0x1400207a8  mov     eax, 0C000000Dh
0x1400207ad  mov     rbx, [rsp+38h+arg_8]
0x1400207b2  mov     rbp, [rsp+38h+arg_18]
0x1400207b7  add     rsp, 20h
0x1400207bb  pop     r14
0x1400207bd  pop     rdi
0x1400207be  pop     rsi
0x1400207bf  retn
```
