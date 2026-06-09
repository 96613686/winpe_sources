# NtCreateSystemSid

- ea: `0x18000ea2c`
- end: `0x18000eab0`
- name: `NtCreateSystemSid`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18000e9ec`

## callees

- `0x18000ea2c`
- `0x18002fe40`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x18000ea84`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000ea84`

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
0x18000ea2c  mov     r11, rsp
0x18000ea2f  push    rbx
0x18000ea30  sub     rsp, 80h
0x18000ea37  mov     rax, cs:__security_cookie
0x18000ea3e  xor     rax, rsp
0x18000ea41  mov     [rsp+88h+var_18], rax
0x18000ea46  xor     ebx, ebx
0x18000ea48  mov     [rsp+88h+var_1C], 500h
0x18000ea4f  lea     rax, [r11-28h]
0x18000ea53  mov     [r11-28h], rbx
0x18000ea57  mov     [r11-38h], rax
0x18000ea5b  lea     rcx, [r11-20h]; IdentifierAuthority
0x18000ea5f  mov     [rsp+88h+SubAuthority7], ebx; SubAuthority7
0x18000ea63  xor     r9d, r9d; SubAuthority1
0x18000ea66  mov     [rsp+88h+SubAuthority6], ebx; SubAuthority6
0x18000ea6a  lea     r8d, [rbx+12h]; SubAuthority0
0x18000ea6e  mov     [rsp+88h+SubAuthority5], ebx; SubAuthority5
0x18000ea72  mov     dl, 1; SubAuthorityCount
0x18000ea74  mov     [rsp+88h+SubAuthority4], ebx; SubAuthority4
0x18000ea78  mov     [rsp+88h+SubAuthority3], ebx; SubAuthority3
0x18000ea7c  mov     [rsp+88h+SubAuthority2], ebx; SubAuthority2
0x18000ea80  mov     [rsp+88h+var_20], ebx
0x18000ea84  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000ea8a  test    eax, eax
0x18000ea8c  js      short loc_18000EA9A
0x18000ea8e  mov     rcx, [rsp+88h+var_28]
0x18000ea93  mov     cs:?pSystemSid@CPublicBinding@@1PEAXEA, rcx; void * CPublicBinding::pSystemSid
0x18000ea9a  mov     rcx, [rsp+88h+var_18]
0x18000ea9f  xor     rcx, rsp; StackCookie
0x18000eaa2  call    __security_check_cookie
0x18000eaa7  add     rsp, 80h
0x18000eaae  pop     rbx
0x18000eaaf  retn
```
