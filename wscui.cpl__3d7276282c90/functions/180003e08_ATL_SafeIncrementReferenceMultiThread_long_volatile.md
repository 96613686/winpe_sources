# ATL::SafeIncrementReferenceMultiThread(long volatile *)

- ea: `0x180003e08`
- end: `0x180003e2f`
- name: `?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `39`
- prototype: `unsigned int __fastcall(volatile int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003710`

## callees

- `0x180003e08`

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
0x180003e08  mov     r9d, 7FFFFFFFh
0x180003e0e  jmp     short loc_180003E1D
0x180003e10  lea     edx, [r8+1]
0x180003e14  mov     eax, r8d
0x180003e17  lock cmpxchg [rcx], edx
0x180003e1b  jz      short loc_180003E27
0x180003e1d  mov     r8d, [rcx]
0x180003e20  cmp     r8d, r9d
0x180003e23  jnz     short loc_180003E10
0x180003e25  jmp     short loc_180003E2B
0x180003e27  lea     r9d, [r8+1]
0x180003e2b  mov     eax, r9d
0x180003e2e  retn
```
