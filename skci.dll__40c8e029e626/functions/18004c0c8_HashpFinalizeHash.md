# HashpFinalizeHash

- ea: `0x18004c0c8`
- end: `0x18004c12b`
- name: `HashpFinalizeHash`
- size: `99`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x180012580`
- `0x18001cec8`
- `0x18004bab4`
- `0x18004bd44`
- `0x18004be0c`
- `0x18004f3e8`

## callees

- `0x180006dd0`
- `0x1800071f0`
- `0x180021ce4`
- `0x180021e4c`
- `0x1800229e0`
- `0x18004c0c8`

## pseudocode

```c
__int64 __fastcall HashpFinalizeHash(_DWORD *a1, __int64 a2)
{
  __int64 result; // rax

  switch ( *a1 )
  {
    case 0x8003:
      return SymCryptMd5Result(a1 + 4, a2, (unsigned int)(*a1 - 32771));
    case 0x8004:
      return SymCryptSha1Result(a1 + 4);
    case 0x800C:
      return SymCryptSha256Result(a1 + 4);
    case 0x800D:
      return SymCryptSha384Result(a1 + 4);
    case 0x800E:
      return SymCryptSha512Result(a1 + 4);
  }
  return result;
}

```

## disassembly

```asm
0x18004c0c8  sub     rsp, 28h
0x18004c0cc  mov     r8d, [rcx]
0x18004c0cf  sub     r8d, 8003h
0x18004c0d6  jz      short loc_18004C11C
0x18004c0d8  sub     r8d, 1
0x18004c0dc  jz      short loc_18004C111
0x18004c0de  sub     r8d, 8
0x18004c0e2  jz      short loc_18004C106
0x18004c0e4  sub     r8d, 1
0x18004c0e8  jz      short loc_18004C0FB
0x18004c0ea  cmp     r8d, 1
0x18004c0ee  jnz     short loc_18004C125
0x18004c0f0  add     rcx, 10h
0x18004c0f4  call    SymCryptSha512Result
0x18004c0f9  jmp     short loc_18004C125
0x18004c0fb  add     rcx, 10h
0x18004c0ff  call    SymCryptSha384Result
0x18004c104  jmp     short loc_18004C125
0x18004c106  add     rcx, 10h
0x18004c10a  call    SymCryptSha256Result
0x18004c10f  jmp     short loc_18004C125
0x18004c111  add     rcx, 10h
0x18004c115  call    SymCryptSha1Result
0x18004c11a  jmp     short loc_18004C125
0x18004c11c  add     rcx, 10h
0x18004c120  call    SymCryptMd5Result
0x18004c125  add     rsp, 28h
0x18004c129  retn
```
