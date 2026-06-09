# ATL::SafeIncrementReferenceMultiThread(long volatile *)

- ea: `0x180002f48`
- end: `0x180002f6f`
- name: `?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `39`
- prototype: `unsigned int __fastcall(volatile int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001c20`
- `0x180002f3c`
- `0x180006b88`

## callees

- `0x180002f48`

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
0x180002f48  mov     r9d, 7FFFFFFFh
0x180002f4e  jmp     short loc_180002F5D
0x180002f50  lea     edx, [r8+1]
0x180002f54  mov     eax, r8d
0x180002f57  lock cmpxchg [rcx], edx
0x180002f5b  jz      short loc_180002F67
0x180002f5d  mov     r8d, [rcx]
0x180002f60  cmp     r8d, r9d
0x180002f63  jnz     short loc_180002F50
0x180002f65  jmp     short loc_180002F6B
0x180002f67  lea     r9d, [r8+1]
0x180002f6b  mov     eax, r9d
0x180002f6e  retn
```
