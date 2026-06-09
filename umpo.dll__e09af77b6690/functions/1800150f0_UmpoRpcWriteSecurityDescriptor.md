# UmpoRpcWriteSecurityDescriptor

- ea: `0x1800150f0`
- end: `0x180015143`
- name: `UmpoRpcWriteSecurityDescriptor`
- size: `83`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180014440`
- `0x180014b38`
- `0x1800150f0`

## pseudocode

```c
__int64 __fastcall UmpoRpcWriteSecurityDescriptor(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, unsigned int a5)
{
  __int64 result; // rax

  if ( !UmpoPowerPolicyInitialized )
    return 21;
  result = UmpoRpcIsAdministrator();
  if ( !(_DWORD)result )
    return UmpoWriteSecurityDescriptor(a2, a3, a4, a5);
  return result;
}

```

## disassembly

```asm
0x1800150f0  mov     [rsp+arg_0], rbx
0x1800150f5  mov     [rsp+arg_8], rsi
0x1800150fa  push    rdi
0x1800150fb  sub     rsp, 20h
0x1800150ff  mov     al, cs:UmpoPowerPolicyInitialized
0x180015105  mov     rbx, r9
0x180015108  mov     rdi, r8
0x18001510b  mov     esi, edx
0x18001510d  test    al, al
0x18001510f  jnz     short loc_180015118
0x180015111  mov     eax, 15h
0x180015116  jmp     short loc_180015133
0x180015118  call    UmpoRpcIsAdministrator
0x18001511d  test    eax, eax
0x18001511f  jnz     short loc_180015133
0x180015121  mov     r9d, [rsp+28h+arg_20]
0x180015126  mov     r8, rbx
0x180015129  mov     rdx, rdi
0x18001512c  mov     ecx, esi
0x18001512e  call    UmpoWriteSecurityDescriptor
0x180015133  mov     rbx, [rsp+28h+arg_0]
0x180015138  mov     rsi, [rsp+28h+arg_8]
0x18001513d  add     rsp, 20h
0x180015141  pop     rdi
0x180015142  retn
```
