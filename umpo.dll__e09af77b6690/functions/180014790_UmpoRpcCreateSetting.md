# UmpoRpcCreateSetting

- ea: `0x180014790`
- end: `0x1800147a5`
- name: `UmpoRpcCreateSetting`
- size: `21`
- prototype: `__int64 __fastcall(__int64, UUID *, UUID *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180012a7c`
- `0x180014790`

## pseudocode

```c
__int64 __fastcall UmpoRpcCreateSetting(__int64 a1, UUID *a2, UUID *a3)
{
  if ( UmpoPowerPolicyInitialized )
    return UmpoInternalCreateSetting(a1, a2, a3);
  else
    return 21;
}

```

## disassembly

```asm
0x180014790  mov     al, cs:UmpoPowerPolicyInitialized
0x180014796  test    al, al
0x180014798  jnz     short loc_1800147A0
0x18001479a  mov     eax, 15h
0x18001479f  retn
0x1800147a0  jmp     UmpoInternalCreateSetting
```
