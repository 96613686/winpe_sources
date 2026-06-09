# ATL::SafeDecrementReferenceMultiThread(long volatile *)

- ea: `0x18000867c`
- end: `0x18000869e`
- name: `?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `34`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000618c`
- `0x1800082e0`
- `0x180008370`
- `0x1800083e0`

## callees

- `0x18000867c`

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
0x18000867c  mov     r9d, 7FFFFFFFh
0x180008682  jmp     short loc_180008691
0x180008684  lea     edx, [r8-1]
0x180008688  mov     eax, r8d
0x18000868b  lock cmpxchg [rcx], edx
0x18000868f  jz      short loc_180008699
0x180008691  mov     r8d, [rcx]
0x180008694  cmp     r8d, r9d
0x180008697  jnz     short loc_180008684
0x180008699  lea     eax, [r8-1]
0x18000869d  retn
```
