# UmpoRpcReplaceDefaultPowerSchemes

- ea: `0x180014d60`
- end: `0x180014dc8`
- name: `UmpoRpcReplaceDefaultPowerSchemes`
- size: `104`
- prototype: `DWORD()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callees

- `0x1800036f0`
- `0x180004b80`
- `0x180014d60`
- `0x180019010`

## pseudocode

```c
DWORD UmpoRpcReplaceDefaultPowerSchemes()
{
  DWORD result; // eax

  if ( !qword_1800246C8 )
    return 50;
  if ( !UmpoIsClientLocal() )
    return 5;
  if ( !UmpoPowerPolicyInitialized )
    return 21;
  result = UmpoRpcSettingAccessCheck(0, 0x14u, 0, 0x20006u);
  if ( !result )
    return ((__int64 (*)(void))qword_1800246C8)();
  return result;
}

```

## disassembly

```asm
0x180014d60  sub     rsp, 28h
0x180014d64  cmp     cs:qword_1800246C8, 0
0x180014d6c  jnz     short loc_180014D78
0x180014d6e  mov     eax, 32h ; '2'
0x180014d73  add     rsp, 28h
0x180014d77  retn
0x180014d78  call    UmpoIsClientLocal
0x180014d7d  test    eax, eax
0x180014d7f  jnz     short loc_180014D8B
0x180014d81  mov     eax, 5
0x180014d86  add     rsp, 28h
0x180014d8a  retn
0x180014d8b  mov     al, cs:UmpoPowerPolicyInitialized
0x180014d91  test    al, al
0x180014d93  jnz     short loc_180014D9F
0x180014d95  mov     eax, 15h
0x180014d9a  add     rsp, 28h
0x180014d9e  retn
0x180014d9f  xor     r8d, r8d
0x180014da2  mov     r9d, 20006h
0x180014da8  xor     ecx, ecx
0x180014daa  lea     edx, [r8+14h]
0x180014dae  call    UmpoRpcSettingAccessCheck
0x180014db3  test    eax, eax
0x180014db5  jnz     short loc_180014DC3
0x180014db7  mov     rax, cs:qword_1800246C8
0x180014dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dc3  add     rsp, 28h
0x180014dc7  retn
```
