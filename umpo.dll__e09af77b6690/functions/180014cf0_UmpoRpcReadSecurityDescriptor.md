# UmpoRpcReadSecurityDescriptor

- ea: `0x180014cf0`
- end: `0x180014d25`
- name: `UmpoRpcReadSecurityDescriptor`
- size: `53`
- prototype: `__int64 __fastcall(__int64, int, __int64, wchar_t *, DWORD, DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003a00`
- `0x180014cf0`

## pseudocode

```c
__int64 __fastcall UmpoRpcReadSecurityDescriptor(__int64 a1, int a2, __int64 a3, wchar_t *a4, DWORD a5, DWORD *a6)
{
  if ( !UmpoPowerPolicyInitialized )
    return 21;
  *a6 = a5;
  return UmpoReadSecurityDescriptor(a2, a3, a4, a6);
}

```

## disassembly

```asm
0x180014cf0  push    rbx
0x180014cf2  mov     al, cs:UmpoPowerPolicyInitialized
0x180014cf8  mov     r10, r9
0x180014cfb  mov     r11, r8
0x180014cfe  mov     ebx, edx
0x180014d00  test    al, al
0x180014d02  jnz     short loc_180014D0B
0x180014d04  mov     eax, 15h
0x180014d09  pop     rbx
0x180014d0a  retn
0x180014d0b  mov     r9, [rsp+8+arg_28]
0x180014d10  mov     r8, r10
0x180014d13  mov     eax, [rsp+8+arg_20]
0x180014d17  mov     rdx, r11
0x180014d1a  mov     ecx, ebx
0x180014d1c  mov     [r9], eax
0x180014d1f  pop     rbx
0x180014d20  jmp     UmpoReadSecurityDescriptor
```
