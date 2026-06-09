# ATL::SafeIncrementReferenceMultiThread(long volatile *)

- ea: `0x180026c38`
- end: `0x180026c5f`
- name: `?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `39`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800260a0`

## callees

- `0x180026c38`

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
0x180026c38  mov     r9d, 7FFFFFFFh
0x180026c3e  jmp     short loc_180026C4D
0x180026c40  lea     edx, [r8+1]
0x180026c44  mov     eax, r8d
0x180026c47  lock cmpxchg [rcx], edx
0x180026c4b  jz      short loc_180026C57
0x180026c4d  mov     r8d, [rcx]
0x180026c50  cmp     r8d, r9d
0x180026c53  jnz     short loc_180026C40
0x180026c55  jmp     short loc_180026C5B
0x180026c57  lea     r9d, [r8+1]
0x180026c5b  mov     eax, r9d
0x180026c5e  retn
```
