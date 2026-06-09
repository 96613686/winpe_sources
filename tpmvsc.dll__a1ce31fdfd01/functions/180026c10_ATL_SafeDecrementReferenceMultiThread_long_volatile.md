# ATL::SafeDecrementReferenceMultiThread(long volatile *)

- ea: `0x180026c10`
- end: `0x180026c32`
- name: `?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z`
- size: `34`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180026bc0`

## callees

- `0x180026c10`

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
0x180026c10  mov     r9d, 7FFFFFFFh
0x180026c16  jmp     short loc_180026C25
0x180026c18  lea     edx, [r8-1]
0x180026c1c  mov     eax, r8d
0x180026c1f  lock cmpxchg [rcx], edx
0x180026c23  jz      short loc_180026C2D
0x180026c25  mov     r8d, [rcx]
0x180026c28  cmp     r8d, r9d
0x180026c2b  jnz     short loc_180026C18
0x180026c2d  lea     eax, [r8-1]
0x180026c31  retn
```
