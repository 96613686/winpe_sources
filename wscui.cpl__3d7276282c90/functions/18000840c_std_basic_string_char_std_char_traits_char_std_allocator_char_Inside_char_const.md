# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Inside(char const *)

- ea: `0x18000840c`
- end: `0x180008445`
- name: `?_Inside@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA_NPEBD@Z`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180008598`

## callees

- `0x18000840c`

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
0x18000840c  test    rdx, rdx
0x18000840f  jz      short loc_180008442
0x180008411  cmp     qword ptr [rcx+18h], 10h
0x180008416  jb      short loc_18000841D
0x180008418  mov     rax, [rcx]
0x18000841b  jmp     short loc_180008420
0x18000841d  mov     rax, rcx
0x180008420  cmp     rdx, rax
0x180008423  jb      short loc_180008442
0x180008425  cmp     qword ptr [rcx+18h], 10h
0x18000842a  jb      short loc_180008431
0x18000842c  mov     r8, [rcx]
0x18000842f  jmp     short loc_180008434
0x180008431  mov     r8, rcx
0x180008434  mov     rcx, [rcx+10h]
0x180008438  add     rcx, r8
0x18000843b  cmp     rcx, rdx
0x18000843e  setnbe  al
0x180008441  retn
0x180008442  xor     al, al
0x180008444  retn
```
