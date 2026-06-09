# ATL::SafeDecrementReferenceMultiThread(long volatile *)

- ea: `0x180002f14`
- end: `0x180002f36`
- name: `?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `34`
- prototype: `unsigned int __fastcall(volatile int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002f08`

## callees

- `0x180002f14`

## pseudocode

```c
__int64 __fastcall ATL::SafeDecrementReferenceMultiThread(volatile int *a1)
{
  signed __int32 v1; // r8d

  do
    v1 = *a1;
  while ( *a1 != 0x7FFFFFFF && v1 != _InterlockedCompareExchange(a1, v1 - 1, v1) );
  return (unsigned int)(v1 - 1);
}

```

## disassembly

```asm
0x180002f14  mov     r9d, 7FFFFFFFh
0x180002f1a  jmp     short loc_180002F29
0x180002f1c  lea     edx, [r8-1]
0x180002f20  mov     eax, r8d
0x180002f23  lock cmpxchg [rcx], edx
0x180002f27  jz      short loc_180002F31
0x180002f29  mov     r8d, [rcx]
0x180002f2c  cmp     r8d, r9d
0x180002f2f  jnz     short loc_180002F1C
0x180002f31  lea     eax, [r8-1]
0x180002f35  retn
```
