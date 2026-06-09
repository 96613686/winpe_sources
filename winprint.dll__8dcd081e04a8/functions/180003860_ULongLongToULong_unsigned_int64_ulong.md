# ULongLongToULong(unsigned __int64,ulong *)

- ea: `0x180003860`
- end: `0x180003883`
- name: `?ULongLongToULong@@YAJ_KPEAK@Z`
- size: `35`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800045d0`
- `0x1800065e8`
- `0x180006770`

## pseudocode

```c
__int64 __fastcall ULongLongToULong(unsigned __int64 a1, unsigned int *a2)
{
  unsigned int v2; // r8d
  __int64 result; // rax

  v2 = -1;
  if ( a1 <= 0xFFFFFFFF )
    v2 = a1;
  result = 0;
  *a2 = v2;
  if ( a1 > 0xFFFFFFFF )
    return 2147942934LL;
  return result;
}

```

## disassembly

```asm
0x180003860  mov     r10d, 0FFFFFFFFh
0x180003866  mov     r9d, 80070216h
0x18000386c  cmp     rcx, r10
0x18000386f  mov     r8d, r10d
0x180003872  cmovbe  r8d, ecx
0x180003876  xor     eax, eax
0x180003878  cmp     rcx, r10
0x18000387b  mov     [rdx], r8d
0x18000387e  cmova   eax, r9d
0x180003882  retn
```
