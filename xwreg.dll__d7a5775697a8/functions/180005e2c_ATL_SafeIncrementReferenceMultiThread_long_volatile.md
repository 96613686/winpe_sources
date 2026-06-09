# ATL::SafeIncrementReferenceMultiThread(long volatile *)

- ea: `0x180005e2c`
- end: `0x180005e53`
- name: `?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `39`
- prototype: `unsigned int __fastcall(volatile int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800032b0`
- `0x1800032e0`

## callees

- `0x180005e2c`

## pseudocode

```c
__int64 __fastcall ATL::SafeIncrementReferenceMultiThread(volatile int *a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *a1;
    if ( *a1 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange(a1, v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x180005e2c  mov     r9d, 7FFFFFFFh
0x180005e32  jmp     short loc_180005E41
0x180005e34  lea     edx, [r8+1]
0x180005e38  mov     eax, r8d
0x180005e3b  lock cmpxchg [rcx], edx
0x180005e3f  jz      short loc_180005E4B
0x180005e41  mov     r8d, [rcx]
0x180005e44  cmp     r8d, r9d
0x180005e47  jnz     short loc_180005E34
0x180005e49  jmp     short loc_180005E4F
0x180005e4b  lea     r9d, [r8+1]
0x180005e4f  mov     eax, r9d
0x180005e52  retn
```
