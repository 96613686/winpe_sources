# ULongLongToULong(unsigned __int64,ulong *)

- ea: `0x18000cad8`
- end: `0x18000caf6`
- name: `?ULongLongToULong@@YAJ_KPEAK@Z`
- size: `30`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c618`
- `0x18000cee0`
- `0x18000f0ec`
- `0x180015834`

## callees

- `0x18000cad8`

## pseudocode

```c
__int64 __fastcall ULongLongToULong(unsigned __int64 a1, unsigned int *a2)
{
  unsigned int v2; // r8d

  v2 = a1;
  if ( a1 > 0xFFFFFFFF )
    v2 = -1;
  *a2 = v2;
  return a1 > 0xFFFFFFFF ? 0x80070216 : 0;
}

```

## disassembly

```asm
0x18000cad8  mov     eax, 0FFFFFFFFh
0x18000cadd  mov     r8d, ecx
0x18000cae0  cmp     rcx, rax
0x18000cae3  jbe     short loc_18000CAE8
0x18000cae5  mov     r8d, eax
0x18000cae8  cmp     rax, rcx
0x18000caeb  mov     [rdx], r8d
0x18000caee  sbb     eax, eax
0x18000caf0  and     eax, 80070216h
0x18000caf5  retn
```
