# NtCreateSystemSid

- ea: `0x18000ece0`
- end: `0x18000ed6b`
- name: `NtCreateSystemSid`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18000ec8c`

## callees

- `0x18000ece0`
- `0x180032c20`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x18000ed38`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000ed38`

## pseudocode

```c
NTSTATUS NtCreateSystemSid()
{
  NTSTATUS result; // eax
  PSID v1; // [rsp+60h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v2; // [rsp+68h] [rbp-20h] BYREF

  *(_WORD *)&v2.Value[4] = 1280;
  v1 = 0;
  *(_DWORD *)v2.Value = 0;
  result = RtlAllocateAndInitializeSid(&v2, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &v1);
  if ( result >= 0 )
    CPublicBinding::pSystemSid = v1;
  return result;
}

```

## disassembly

```asm
0x18000ece0  mov     r11, rsp
0x18000ece3  push    rbx
0x18000ece4  sub     rsp, 80h
0x18000eceb  mov     rax, cs:__security_cookie
0x18000ecf2  xor     rax, rsp
0x18000ecf5  mov     [rsp+88h+var_18], rax
0x18000ecfa  xor     ebx, ebx
0x18000ecfc  mov     [rsp+88h+var_1C], 500h
0x18000ed03  lea     rax, [r11-28h]
0x18000ed07  mov     [r11-28h], rbx
0x18000ed0b  mov     [r11-38h], rax
0x18000ed0f  lea     rcx, [r11-20h]; IdentifierAuthority
0x18000ed13  mov     [rsp+88h+SubAuthority7], ebx; SubAuthority7
0x18000ed17  xor     r9d, r9d; SubAuthority1
0x18000ed1a  mov     [rsp+88h+SubAuthority6], ebx; SubAuthority6
0x18000ed1e  lea     r8d, [rbx+12h]; SubAuthority0
0x18000ed22  mov     [rsp+88h+SubAuthority5], ebx; SubAuthority5
0x18000ed26  mov     dl, 1; SubAuthorityCount
0x18000ed28  mov     [rsp+88h+SubAuthority4], ebx; SubAuthority4
0x18000ed2c  mov     [rsp+88h+SubAuthority3], ebx; SubAuthority3
0x18000ed30  mov     [rsp+88h+SubAuthority2], ebx; SubAuthority2
0x18000ed34  mov     [rsp+88h+var_20], ebx
0x18000ed38  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000ed3f  nop     dword ptr [rax+rax+00h]
0x18000ed44  test    eax, eax
0x18000ed46  js      short loc_18000ED54
0x18000ed48  mov     rcx, [rsp+88h+var_28]
0x18000ed4d  mov     cs:?pSystemSid@CPublicBinding@@1PEAXEA, rcx; void * CPublicBinding::pSystemSid
0x18000ed54  mov     rcx, [rsp+88h+var_18]
0x18000ed59  xor     rcx, rsp; StackCookie
0x18000ed5c  call    __security_check_cookie
0x18000ed61  add     rsp, 80h
0x18000ed68  pop     rbx
0x18000ed69  retn
```
