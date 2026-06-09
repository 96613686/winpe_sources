# HashpHashBytes

- ea: `0x18004c134`
- end: `0x18004c1a6`
- name: `HashpHashBytes`
- size: `114`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `6`
- tags: ``

## callers

- `0x180012580`
- `0x180013590`
- `0x18001cec8`
- `0x1800460f8`
- `0x180046350`
- `0x18004bd44`
- `0x18004c00c`
- `0x18004c254`
- `0x18004f3e8`

## callees

- `0x180006f80`
- `0x180007070`
- `0x180021c80`
- `0x180022020`
- `0x180022050`
- `0x18004c134`

## pseudocode

```c
__int64 __fastcall HashpHashBytes(_DWORD *a1, __int64 a2, unsigned int a3)
{
  __int64 result; // rax

  switch ( *a1 )
  {
    case 0x8003:
      return SymCryptMd5Append(a1 + 4, a2, a3, (unsigned int)(*a1 - 32771));
    case 0x8004:
      return SymCryptSha1Append(a1 + 4, a2, a3);
    case 0x800C:
      return SymCryptSha256Append(a1 + 4, a2, a3);
    case 0x800D:
      return SymCryptSha384Append(a1 + 4, a2, a3);
    case 0x800E:
      return SymCryptSha512Append(a1 + 4, a2, a3);
  }
  return result;
}

```

## disassembly

```asm
0x18004c134  sub     rsp, 28h
0x18004c138  mov     r9d, [rcx]
0x18004c13b  sub     r9d, 8003h
0x18004c142  jz      short loc_18004C194
0x18004c144  sub     r9d, 1
0x18004c148  jz      short loc_18004C186
0x18004c14a  sub     r9d, 8
0x18004c14e  jz      short loc_18004C178
0x18004c150  sub     r9d, 1
0x18004c154  jz      short loc_18004C16A
0x18004c156  cmp     r9d, 1
0x18004c15a  jnz     short loc_18004C1A0
0x18004c15c  mov     r8d, r8d
0x18004c15f  add     rcx, 10h
0x18004c163  call    SymCryptSha512Append
0x18004c168  jmp     short loc_18004C1A0
0x18004c16a  mov     r8d, r8d
0x18004c16d  add     rcx, 10h
0x18004c171  call    SymCryptSha384Append
0x18004c176  jmp     short loc_18004C1A0
0x18004c178  mov     r8d, r8d
0x18004c17b  add     rcx, 10h
0x18004c17f  call    SymCryptSha256Append
0x18004c184  jmp     short loc_18004C1A0
0x18004c186  mov     r8d, r8d
0x18004c189  add     rcx, 10h
0x18004c18d  call    SymCryptSha1Append
0x18004c192  jmp     short loc_18004C1A0
0x18004c194  mov     r8d, r8d
0x18004c197  add     rcx, 10h
0x18004c19b  call    SymCryptMd5Append
0x18004c1a0  add     rsp, 28h
0x18004c1a4  retn
```
