# UmpoRpcRemoveSetting

- ea: `0x180014d30`
- end: `0x180014d4e`
- name: `UmpoRpcRemoveSetting`
- size: `30`
- prototype: `__int64 __fastcall(__int64, UUID *, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180013808`
- `0x180014d30`

## pseudocode

```c
__int64 __fastcall UmpoRpcRemoveSetting(__int64 a1, UUID *a2, __int64 a3)
{
  if ( UmpoPowerPolicyInitialized )
    return UmpoInternalRemoveSetting(a2, a3);
  else
    return 21;
}

```

## disassembly

```asm
0x180014d30  mov     al, cs:UmpoPowerPolicyInitialized
0x180014d36  mov     r9, rdx
0x180014d39  test    al, al
0x180014d3b  jnz     short loc_180014D43
0x180014d3d  mov     eax, 15h
0x180014d42  retn
0x180014d43  mov     rdx, r8
0x180014d46  mov     rcx, r9; Uuid2
0x180014d49  jmp     UmpoInternalRemoveSetting
```
