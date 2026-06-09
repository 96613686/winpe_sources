# ATL::SafeDecrementReferenceMultiThread(long volatile *)

- ea: `0x18000b914`
- end: `0x18000b936`
- name: `?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `34`
- prototype: `unsigned int __fastcall(volatile int *)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b4f0`
- `0x18000b580`
- `0x18000b5f0`
- `0x18000b660`
- `0x18000b750`
- `0x18000b7c0`
- `0x180011040`
- `0x1800131b0`
- `0x180013f70`

## callees

- `0x18000b914`

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
0x18000b914  mov     r9d, 7FFFFFFFh
0x18000b91a  jmp     short loc_18000B929
0x18000b91c  lea     edx, [r8-1]
0x18000b920  mov     eax, r8d
0x18000b923  lock cmpxchg [rcx], edx
0x18000b927  jz      short loc_18000B931
0x18000b929  mov     r8d, [rcx]
0x18000b92c  cmp     r8d, r9d
0x18000b92f  jnz     short loc_18000B91C
0x18000b931  lea     eax, [r8-1]
0x18000b935  retn
```
