# UmpoRpcGetPowerConfiguration

- ea: `0x180014a90`
- end: `0x180014abb`
- name: `UmpoRpcGetPowerConfiguration`
- size: `43`
- prototype: `__int64 __fastcall(__int64, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180004b80`
- `0x1800088b0`
- `0x180014a90`

## pseudocode

```c
__int64 __fastcall UmpoRpcGetPowerConfiguration(__int64 a1, int *a2)
{
  if ( UmpoIsClientLocal() )
    return UmpoGetSystemConfiguration(a2);
  else
    return 5;
}

```

## disassembly

```asm
0x180014a90  push    rbx
0x180014a92  sub     rsp, 20h
0x180014a96  mov     rbx, rdx
0x180014a99  call    UmpoIsClientLocal
0x180014a9e  test    eax, eax
0x180014aa0  jnz     short loc_180014AAD
0x180014aa2  mov     eax, 5
0x180014aa7  add     rsp, 20h
0x180014aab  pop     rbx
0x180014aac  retn
0x180014aad  mov     rcx, rbx
0x180014ab0  call    UmpoGetSystemConfiguration
0x180014ab5  add     rsp, 20h
0x180014ab9  pop     rbx
0x180014aba  retn
```
