# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Inside(char const *)

- ea: `0x180001fac`
- end: `0x180001fe5`
- name: `?_Inside@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA_NPEBD@Z`
- size: `57`
- prototype: `bool __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180002138`

## callees

- `0x180001fac`

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
0x180001fac  test    rdx, rdx
0x180001faf  jz      short loc_180001FE2
0x180001fb1  cmp     qword ptr [rcx+18h], 10h
0x180001fb6  jb      short loc_180001FBD
0x180001fb8  mov     rax, [rcx]
0x180001fbb  jmp     short loc_180001FC0
0x180001fbd  mov     rax, rcx
0x180001fc0  cmp     rdx, rax
0x180001fc3  jb      short loc_180001FE2
0x180001fc5  cmp     qword ptr [rcx+18h], 10h
0x180001fca  jb      short loc_180001FD1
0x180001fcc  mov     r8, [rcx]
0x180001fcf  jmp     short loc_180001FD4
0x180001fd1  mov     r8, rcx
0x180001fd4  mov     rcx, [rcx+10h]
0x180001fd8  add     rcx, r8
0x180001fdb  cmp     rcx, rdx
0x180001fde  setnbe  al
0x180001fe1  retn
0x180001fe2  xor     al, al
0x180001fe4  retn
```
