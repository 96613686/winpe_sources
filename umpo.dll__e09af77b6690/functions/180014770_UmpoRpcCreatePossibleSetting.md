# UmpoRpcCreatePossibleSetting

- ea: `0x180014770`
- end: `0x180014785`
- name: `UmpoRpcCreatePossibleSetting`
- size: `21`
- prototype: `__int64 __fastcall(__int64, UUID *, UUID *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800128e4`
- `0x180014770`

## pseudocode

```c
__int64 __fastcall UmpoRpcCreatePossibleSetting(__int64 a1, UUID *a2, UUID *a3, unsigned int a4)
{
  if ( UmpoPowerPolicyInitialized )
    return UmpoInternalCreatePossibleSetting(a1, a2, a3, a4);
  else
    return 21;
}

```

## disassembly

```asm
0x180014770  mov     al, cs:UmpoPowerPolicyInitialized
0x180014776  test    al, al
0x180014778  jnz     short loc_180014780
0x18001477a  mov     eax, 15h
0x18001477f  retn
0x180014780  jmp     UmpoInternalCreatePossibleSetting
```
