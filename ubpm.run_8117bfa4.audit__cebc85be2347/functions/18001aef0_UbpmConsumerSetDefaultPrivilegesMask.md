# UbpmConsumerSetDefaultPrivilegesMask

- ea: `0x18001aef0`
- end: `0x18001af5e`
- name: `UbpmConsumerSetDefaultPrivilegesMask`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019d70`

## callees

- `0x18001aef0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001af11`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001af47`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001af11`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001af47`

## pseudocode

```c
__int64 __fastcall UbpmConsumerSetDefaultPrivilegesMask(__int64 a1, _QWORD *a2)
{
  if ( *a2 || !EqualSid(pSid2, *(PSID *)(a1 + 8)) && !EqualSid(qword_18004FF68, *(PSID *)(a1 + 8)) )
    return 87;
  *a2 = 0x8000000000000000uLL;
  return 0;
}

```

## disassembly

```asm
0x18001aef0  mov     [rsp+arg_0], rbx
0x18001aef5  push    rdi
0x18001aef6  sub     rsp, 20h
0x18001aefa  cmp     qword ptr [rdx], 0
0x18001aefe  mov     rbx, rdx
0x18001af01  mov     rdi, rcx
0x18001af04  jnz     short loc_18001AF57
0x18001af06  mov     rdx, [rcx+8]; pSid2
0x18001af0a  mov     rcx, cs:pSid2; pSid1
0x18001af11  call    cs:__imp_EqualSid
0x18001af18  nop     dword ptr [rax+rax+00h]
0x18001af1d  test    eax, eax
0x18001af1f  jz      short loc_18001AF3C
0x18001af21  mov     rax, 8000000000000000h
0x18001af2b  mov     [rbx], rax
0x18001af2e  xor     eax, eax
0x18001af30  mov     rbx, [rsp+28h+arg_0]
0x18001af35  add     rsp, 20h
0x18001af39  pop     rdi
0x18001af3a  retn
0x18001af3c  mov     rdx, [rdi+8]; pSid2
0x18001af40  mov     rcx, cs:qword_18004FF68; pSid1
0x18001af47  call    cs:__imp_EqualSid
0x18001af4e  nop     dword ptr [rax+rax+00h]
0x18001af53  test    eax, eax
0x18001af55  jnz     short loc_18001AF21
0x18001af57  mov     eax, 57h ; 'W'
0x18001af5c  jmp     short loc_18001AF30
```
