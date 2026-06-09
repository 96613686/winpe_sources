# UbpmConsumerSetDefaultPrivilegesMask

- ea: `0x18001e98c`
- end: `0x18001e9ed`
- name: `UbpmConsumerSetDefaultPrivilegesMask`
- size: `97`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001d830`

## callees

- `0x18001e98c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001e9ad`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001e9dc`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001e9ad`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001e9dc`

## pseudocode

```c
__int64 __fastcall UbpmConsumerSetDefaultPrivilegesMask(__int64 a1, _QWORD *a2)
{
  if ( *a2 || !EqualSid(pSid1, *(PSID *)(a1 + 8)) && !EqualSid(pSid2, *(PSID *)(a1 + 8)) )
    return 87;
  *a2 = 0x8000000000000000uLL;
  return 0;
}

```

## disassembly

```asm
0x18001e98c  mov     [rsp+arg_0], rbx
0x18001e991  push    rdi
0x18001e992  sub     rsp, 20h
0x18001e996  cmp     qword ptr [rdx], 0
0x18001e99a  mov     rbx, rdx
0x18001e99d  mov     rdi, rcx
0x18001e9a0  jnz     short loc_18001E9E6
0x18001e9a2  mov     rdx, [rcx+8]; pSid2
0x18001e9a6  mov     rcx, cs:pSid1; pSid1
0x18001e9ad  call    cs:__imp_EqualSid
0x18001e9b3  test    eax, eax
0x18001e9b5  jz      short loc_18001E9D1
0x18001e9b7  mov     rax, 8000000000000000h
0x18001e9c1  mov     [rbx], rax
0x18001e9c4  xor     eax, eax
0x18001e9c6  mov     rbx, [rsp+28h+arg_0]
0x18001e9cb  add     rsp, 20h
0x18001e9cf  pop     rdi
0x18001e9d0  retn
0x18001e9d1  mov     rdx, [rdi+8]; pSid2
0x18001e9d5  mov     rcx, cs:pSid2; pSid1
0x18001e9dc  call    cs:__imp_EqualSid
0x18001e9e2  test    eax, eax
0x18001e9e4  jnz     short loc_18001E9B7
0x18001e9e6  mov     eax, 57h ; 'W'
0x18001e9eb  jmp     short loc_18001E9C6
```
