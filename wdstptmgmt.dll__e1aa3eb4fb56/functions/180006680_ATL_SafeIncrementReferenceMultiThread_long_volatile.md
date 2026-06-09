# ATL::SafeIncrementReferenceMultiThread(long volatile *)

- ea: `0x180006680`
- end: `0x1800066a7`
- name: `?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `39`
- prototype: `unsigned int __fastcall(volatile int *)`
- caller_count: `15`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006000`
- `0x1800061fc`
- `0x180006cc4`
- `0x180007f30`
- `0x1800080b0`
- `0x180008a30`
- `0x180011128`
- `0x180011220`
- `0x180011344`
- `0x1800148c0`
- `0x180015530`
- `0x1800162d0`
- `0x180018310`
- `0x180018410`
- `0x180018db0`

## callees

- `0x180006680`

## pseudocode

```c
__int64 __fastcall ATL::SafeIncrementReferenceMultiThread(volatile int *a1)
{
  signed __int32 v1; // r8d

  do
  {
    v1 = *a1;
    if ( *a1 == 0x7FFFFFFF )
      return 0x7FFFFFFF;
  }
  while ( v1 != _InterlockedCompareExchange(a1, v1 + 1, v1) );
  return (unsigned int)(v1 + 1);
}

```

## disassembly

```asm
0x180006680  mov     r9d, 7FFFFFFFh
0x180006686  jmp     short loc_180006695
0x180006688  lea     edx, [r8+1]
0x18000668c  mov     eax, r8d
0x18000668f  lock cmpxchg [rcx], edx
0x180006693  jz      short loc_1800066A2
0x180006695  mov     r8d, [rcx]
0x180006698  cmp     r8d, r9d
0x18000669b  jnz     short loc_180006688
0x18000669d  mov     eax, r9d
0x1800066a0  retn
0x1800066a2  lea     eax, [r8+1]
0x1800066a6  retn
```
