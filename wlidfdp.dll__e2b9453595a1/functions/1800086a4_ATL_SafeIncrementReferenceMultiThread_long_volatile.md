# ATL::SafeIncrementReferenceMultiThread(long volatile *)

- ea: `0x1800086a4`
- end: `0x1800086cb`
- name: `?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `39`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005ba0`
- `0x180005bd0`
- `0x18000618c`

## callees

- `0x1800086a4`

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
0x1800086a4  mov     r9d, 7FFFFFFFh
0x1800086aa  jmp     short loc_1800086B9
0x1800086ac  lea     edx, [r8+1]
0x1800086b0  mov     eax, r8d
0x1800086b3  lock cmpxchg [rcx], edx
0x1800086b7  jz      short loc_1800086C3
0x1800086b9  mov     r8d, [rcx]
0x1800086bc  cmp     r8d, r9d
0x1800086bf  jnz     short loc_1800086AC
0x1800086c1  jmp     short loc_1800086C7
0x1800086c3  lea     r9d, [r8+1]
0x1800086c7  mov     eax, r9d
0x1800086ca  retn
```
