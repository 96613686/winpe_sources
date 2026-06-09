# InitializeServiceSid

- ea: `0x14000abb4`
- end: `0x14000aca6`
- name: `InitializeServiceSid`
- size: `242`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task`

## callers

- `0x14000acac`

## callees

- `0x1400030f0`

## import_xrefs

- `ntoskrnl!RtlInitializeSid` at `0x14000abe8`
- `ntoskrnl!RtlInitializeSid` at `0x14000abe8`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000abf9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000ac13`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000ac2b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000ac46`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000ac61`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000ac7c`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000abf9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000ac13`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000ac2b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000ac46`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000ac61`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000ac7c`

## pseudocode

```c
PULONG __fastcall InitializeServiceSid(PSID Sid, ULONG *a2)
{
  PULONG result; // rax
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+20h] [rbp-18h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  RtlInitializeSid(Sid, &IdentifierAuthority, 6u);
  *RtlSubAuthoritySid(Sid, 0) = 80;
  *RtlSubAuthoritySid(Sid, 1u) = *a2;
  *RtlSubAuthoritySid(Sid, 2u) = a2[1];
  *RtlSubAuthoritySid(Sid, 3u) = a2[2];
  *RtlSubAuthoritySid(Sid, 4u) = a2[3];
  result = RtlSubAuthoritySid(Sid, 5u);
  *result = a2[4];
  return result;
}

```

## disassembly

```asm
0x14000abb4  mov     [rsp+arg_8], rbx
0x14000abb9  push    rdi
0x14000abba  sub     rsp, 30h
0x14000abbe  mov     rax, cs:__security_cookie
0x14000abc5  xor     rax, rsp
0x14000abc8  mov     [rsp+38h+var_10], rax
0x14000abcd  mov     rdi, rdx
0x14000abd0  mov     word ptr [rsp+38h+IdentifierAuthority.Value+4], 500h
0x14000abd7  xor     eax, eax
0x14000abd9  lea     rdx, [rsp+38h+IdentifierAuthority]; IdentifierAuthority
0x14000abde  mov     r8b, 6; SubAuthorityCount
0x14000abe1  mov     dword ptr [rsp+38h+IdentifierAuthority.Value], eax
0x14000abe5  mov     rbx, rcx
0x14000abe8  call    cs:__imp_RtlInitializeSid
0x14000abef  nop     dword ptr [rax+rax+00h]
0x14000abf4  xor     edx, edx; SubAuthority
0x14000abf6  mov     rcx, rbx; Sid
0x14000abf9  call    cs:__imp_RtlSubAuthoritySid
0x14000ac00  nop     dword ptr [rax+rax+00h]
0x14000ac05  mov     edx, 1; SubAuthority
0x14000ac0a  mov     rcx, rbx; Sid
0x14000ac0d  mov     dword ptr [rax], 50h ; 'P'
0x14000ac13  call    cs:__imp_RtlSubAuthoritySid
0x14000ac1a  nop     dword ptr [rax+rax+00h]
0x14000ac1f  mov     ecx, [rdi]
0x14000ac21  mov     edx, 2; SubAuthority
0x14000ac26  mov     [rax], ecx
0x14000ac28  mov     rcx, rbx; Sid
0x14000ac2b  call    cs:__imp_RtlSubAuthoritySid
0x14000ac32  nop     dword ptr [rax+rax+00h]
0x14000ac37  mov     r8d, [rdi+4]
0x14000ac3b  mov     edx, 3; SubAuthority
0x14000ac40  mov     rcx, rbx; Sid
0x14000ac43  mov     [rax], r8d
0x14000ac46  call    cs:__imp_RtlSubAuthoritySid
0x14000ac4d  nop     dword ptr [rax+rax+00h]
0x14000ac52  mov     r8d, [rdi+8]
0x14000ac56  mov     edx, 4; SubAuthority
0x14000ac5b  mov     rcx, rbx; Sid
0x14000ac5e  mov     [rax], r8d
0x14000ac61  call    cs:__imp_RtlSubAuthoritySid
0x14000ac68  nop     dword ptr [rax+rax+00h]
0x14000ac6d  mov     r8d, [rdi+0Ch]
0x14000ac71  mov     edx, 5; SubAuthority
0x14000ac76  mov     rcx, rbx; Sid
0x14000ac79  mov     [rax], r8d
0x14000ac7c  call    cs:__imp_RtlSubAuthoritySid
0x14000ac83  nop     dword ptr [rax+rax+00h]
0x14000ac88  mov     ecx, [rdi+10h]
0x14000ac8b  mov     [rax], ecx
0x14000ac8d  mov     rcx, [rsp+38h+var_10]
0x14000ac92  xor     rcx, rsp; StackCookie
0x14000ac95  call    __security_check_cookie
0x14000ac9a  mov     rbx, [rsp+38h+arg_8]
0x14000ac9f  add     rsp, 30h
0x14000aca3  pop     rdi
0x14000aca4  retn
```
