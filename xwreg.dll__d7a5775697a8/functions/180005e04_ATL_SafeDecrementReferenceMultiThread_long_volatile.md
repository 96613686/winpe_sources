# ATL::SafeDecrementReferenceMultiThread(long volatile *)

- ea: `0x180005e04`
- end: `0x180005e26`
- name: `?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `34`
- prototype: `unsigned int __fastcall(volatile int *)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005b80`
- `0x180005c10`
- `0x180005c80`
- `0x180005cf0`
- `0x180005d60`

## callees

- `0x180005e04`

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
0x180005e04  mov     r9d, 7FFFFFFFh
0x180005e0a  jmp     short loc_180005E19
0x180005e0c  lea     edx, [r8-1]
0x180005e10  mov     eax, r8d
0x180005e13  lock cmpxchg [rcx], edx
0x180005e17  jz      short loc_180005E21
0x180005e19  mov     r8d, [rcx]
0x180005e1c  cmp     r8d, r9d
0x180005e1f  jnz     short loc_180005E0C
0x180005e21  lea     eax, [r8-1]
0x180005e25  retn
```
