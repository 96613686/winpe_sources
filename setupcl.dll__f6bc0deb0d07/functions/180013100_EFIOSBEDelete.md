# EFIOSBEDelete

- ea: `0x180013100`
- end: `0x18001312c`
- name: `EFIOSBEDelete`
- size: `44`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180012d4c`
- `0x180013100`

## pseudocode

```c
__int64 __fastcall EFIOSBEDelete(__int64 a1)
{
  __int64 v2; // rcx
  __int64 result; // rax

  if ( a1 )
  {
    v2 = *(_QWORD *)(a1 + 3168);
    if ( v2 )
      SBE_FREE(v2);
    return SBE_FREE(a1);
  }
  return result;
}

```

## disassembly

```asm
0x180013100  test    rcx, rcx
0x180013103  jz      short locret_18001312B
0x180013105  push    rbx
0x180013106  sub     rsp, 20h
0x18001310a  mov     rbx, rcx
0x18001310d  mov     rcx, [rcx+0C60h]
0x180013114  test    rcx, rcx
0x180013117  jz      short loc_18001311E
0x180013119  call    SBE_FREE
0x18001311e  mov     rcx, rbx
0x180013121  call    SBE_FREE
0x180013126  add     rsp, 20h
0x18001312a  pop     rbx
0x18001312b  retn
```
