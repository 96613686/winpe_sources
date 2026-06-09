# SrvLibCreateAclForSid

- ea: `0x140028f78`
- end: `0x14002901c`
- name: `SrvLibCreateAclForSid`
- size: `164`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140029030`

## callees

- `0x140007c60`
- `0x140028f78`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x140028f84`
- `ntoskrnl!RtlLengthSid` at `0x140028f84`
- `ntoskrnl!RtlCreateAcl` at `0x140028fbd`
- `ntoskrnl!RtlCreateAcl` at `0x140028fbd`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140028fda`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140028fda`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140028feb`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140028feb`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140029003`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140029003`

## pseudocode

```c
struct _ACL *__fastcall SrvLibCreateAclForSid(PSID Sid)
{
  ULONG v2; // eax
  ULONG v3; // ebp
  struct _ACL *result; // rax
  struct _ACL *v5; // rdi
  struct _ACL *v6; // rbx

  v2 = RtlLengthSid(Sid);
  v3 = v2 + 20;
  result = (struct _ACL *)SrvNetAllocatePoolWithTag(258, v2 + 60, 1651266380);
  v5 = result;
  if ( result )
  {
    v6 = result + 5;
    RtlCreateAcl(result + 5, v3, 2u);
    RtlAddAccessAllowedAce(v6, 2u, 1u, Sid);
    RtlCreateSecurityDescriptor(v5, 1u);
    RtlSetDaclSecurityDescriptor(v5, 1u, v6, 0);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x140028f78  push    rbx
0x140028f7a  push    rbp
0x140028f7b  push    rsi
0x140028f7c  push    rdi
0x140028f7d  sub     rsp, 28h
0x140028f81  mov     rsi, rcx
0x140028f84  call    cs:__imp_RtlLengthSid
0x140028f8b  nop     dword ptr [rax+rax+00h]
0x140028f90  mov     ecx, 102h
0x140028f95  mov     r8d, 626C534Ch
0x140028f9b  lea     ebp, [rax+14h]
0x140028f9e  lea     edx, [rbp+28h]
0x140028fa1  call    SrvNetAllocatePoolWithTag
0x140028fa6  mov     rdi, rax
0x140028fa9  test    rax, rax
0x140028fac  jz      short loc_140029012
0x140028fae  lea     rbx, [rax+28h]
0x140028fb2  mov     r8d, 2; AclRevision
0x140028fb8  mov     rcx, rbx; Acl
0x140028fbb  mov     edx, ebp; AclLength
0x140028fbd  call    cs:__imp_RtlCreateAcl
0x140028fc4  nop     dword ptr [rax+rax+00h]
0x140028fc9  mov     r9, rsi; Sid
0x140028fcc  mov     rcx, rbx; Acl
0x140028fcf  mov     esi, 1
0x140028fd4  mov     r8d, esi; AccessMask
0x140028fd7  lea     edx, [rsi+1]; AceRevision
0x140028fda  call    cs:__imp_RtlAddAccessAllowedAce
0x140028fe1  nop     dword ptr [rax+rax+00h]
0x140028fe6  mov     edx, esi; Revision
0x140028fe8  mov     rcx, rdi; SecurityDescriptor
0x140028feb  call    cs:__imp_RtlCreateSecurityDescriptor
0x140028ff2  nop     dword ptr [rax+rax+00h]
0x140028ff7  xor     r9d, r9d; DaclDefaulted
0x140028ffa  mov     r8, rbx; Dacl
0x140028ffd  mov     dl, sil; DaclPresent
0x140029000  mov     rcx, rdi; SecurityDescriptor
0x140029003  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14002900a  nop     dword ptr [rax+rax+00h]
0x14002900f  mov     rax, rdi
0x140029012  add     rsp, 28h
0x140029016  pop     rdi
0x140029017  pop     rsi
0x140029018  pop     rbp
0x140029019  pop     rbx
0x14002901a  retn
```
