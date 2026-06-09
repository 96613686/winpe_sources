# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Inside(char const *)

- ea: `0x18000ae24`
- end: `0x18000ae5d`
- name: `?_Inside@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA_NPEBD@Z`
- size: `57`
- prototype: `bool __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000b0dc`

## callees

- `0x18000ae24`

## pseudocode

```c
bool __fastcall std::string::_Inside(_QWORD *a1, unsigned __int64 a2)
{
  _QWORD *v2; // rax
  _QWORD *v3; // r8

  if ( !a2 )
    return 0;
  v2 = a1[3] < 0x10u ? a1 : (_QWORD *)*a1;
  if ( a2 < (unsigned __int64)v2 )
    return 0;
  if ( a1[3] < 0x10u )
    v3 = a1;
  else
    v3 = (_QWORD *)*a1;
  return (unsigned __int64)v3 + a1[2] > a2;
}

```

## disassembly

```asm
0x18000ae24  test    rdx, rdx
0x18000ae27  jz      short loc_18000AE5A
0x18000ae29  cmp     qword ptr [rcx+18h], 10h
0x18000ae2e  jb      short loc_18000AE35
0x18000ae30  mov     rax, [rcx]
0x18000ae33  jmp     short loc_18000AE38
0x18000ae35  mov     rax, rcx
0x18000ae38  cmp     rdx, rax
0x18000ae3b  jb      short loc_18000AE5A
0x18000ae3d  cmp     qword ptr [rcx+18h], 10h
0x18000ae42  jb      short loc_18000AE49
0x18000ae44  mov     r8, [rcx]
0x18000ae47  jmp     short loc_18000AE4C
0x18000ae49  mov     r8, rcx
0x18000ae4c  mov     rcx, [rcx+10h]
0x18000ae50  add     rcx, r8
0x18000ae53  cmp     rcx, rdx
0x18000ae56  setnbe  al
0x18000ae59  retn
0x18000ae5a  xor     al, al
0x18000ae5c  retn
```
