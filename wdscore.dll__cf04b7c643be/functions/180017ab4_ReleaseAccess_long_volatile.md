# ReleaseAccess(long volatile *)

- ea: `0x180017ab4`
- end: `0x180017ac5`
- name: `?ReleaseAccess@@YAXPECJ@Z`
- size: `17`
- prototype: `void __fastcall(volatile int *)`
- caller_count: `24`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f798`
- `0x18000fa70`
- `0x18000fcf0`
- `0x1800107c4`
- `0x180011064`
- `0x180011aa0`
- `0x18001229c`
- `0x1800149c4`
- `0x1800179a4`
- `0x180017af0`
- `0x180017b7c`
- `0x180017c2c`
- `0x1800189d0`
- `0x180018ac0`
- `0x180018dc0`
- `0x180018ee0`
- `0x180019180`
- `0x1800192f0`
- `0x1800194f0`
- `0x180019680`
- `0x1800197c0`
- `0x1800198d0`
- `0x1800199e0`
- `0x180019be0`

## callees

- `0x180017ab4`

## pseudocode

```c
void __fastcall ReleaseAccess(volatile int *a1)
{
  if ( _InterlockedCompareExchange(a1, 0, -1) != -1 )
    _InterlockedDecrement(a1);
}

```

## disassembly

```asm
0x180017ab4  xor     edx, edx
0x180017ab6  or      eax, 0FFFFFFFFh
0x180017ab9  lock cmpxchg [rcx], edx
0x180017abd  jz      short locret_180017AC4
0x180017abf  mov     eax, [rcx]
0x180017ac1  lock dec dword ptr [rcx]
0x180017ac4  retn
```
