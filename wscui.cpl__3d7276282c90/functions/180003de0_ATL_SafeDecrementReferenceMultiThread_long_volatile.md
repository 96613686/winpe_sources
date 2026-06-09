# ATL::SafeDecrementReferenceMultiThread(long volatile *)

- ea: `0x180003de0`
- end: `0x180003e02`
- name: `?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `34`
- prototype: `unsigned int __fastcall(volatile int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003d90`

## callees

- `0x180003de0`

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
0x180003de0  mov     r9d, 7FFFFFFFh
0x180003de6  jmp     short loc_180003DF5
0x180003de8  lea     edx, [r8-1]
0x180003dec  mov     eax, r8d
0x180003def  lock cmpxchg [rcx], edx
0x180003df3  jz      short loc_180003DFD
0x180003df5  mov     r8d, [rcx]
0x180003df8  cmp     r8d, r9d
0x180003dfb  jnz     short loc_180003DE8
0x180003dfd  lea     eax, [r8-1]
0x180003e01  retn
```
