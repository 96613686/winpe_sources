# RtlULongLongToULong

- ea: `0x180010a88`
- end: `0x180010aa6`
- name: `RtlULongLongToULong`
- size: `30`
- prototype: `NTSTATUS __stdcall(ULONGLONG ullOperand, ULONG *pulResult)`
- caller_count: `28`
- callee_count: `1`
- tags: ``

## callers

- `0x1800124a0`
- `0x180019300`
- `0x180019720`
- `0x18001c380`
- `0x18001cd1c`
- `0x18001e0b8`
- `0x18001e244`
- `0x18001e3a8`
- `0x18001e674`
- `0x18001ef1c`
- `0x18001f33c`
- `0x18001f624`
- `0x18001f800`
- `0x18001f960`
- `0x18001fb08`
- `0x18001fd8c`
- `0x18001ff54`
- `0x180044fe4`
- `0x18004640c`
- `0x180046aa0`
- `0x180047128`
- `0x180047228`
- `0x1800472cc`
- `0x18004762c`
- `0x180047a80`
- `0x180048c50`
- `0x18004a97c`
- `0x18004c2e0`

## callees

- `0x180010a88`

## pseudocode

```c
NTSTATUS __stdcall RtlULongLongToULong(ULONGLONG ullOperand, ULONG *pulResult)
{
  ULONG v2; // r8d

  v2 = ullOperand;
  if ( ullOperand > 0xFFFFFFFF )
    v2 = -1;
  *pulResult = v2;
  return ullOperand > 0xFFFFFFFF ? 0xC0000095 : 0;
}

```

## disassembly

```asm
0x180010a88  mov     eax, 0FFFFFFFFh
0x180010a8d  mov     r8d, ecx
0x180010a90  cmp     rcx, rax
0x180010a93  jbe     short loc_180010A98
0x180010a95  mov     r8d, eax
0x180010a98  cmp     rax, rcx
0x180010a9b  mov     [rdx], r8d
0x180010a9e  sbb     eax, eax
0x180010aa0  and     eax, 0C0000095h
0x180010aa5  retn
```
