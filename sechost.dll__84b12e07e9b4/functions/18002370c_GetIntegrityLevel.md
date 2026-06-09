# GetIntegrityLevel

- ea: `0x18002370c`
- end: `0x1800237d0`
- name: `GetIntegrityLevel`
- size: `196`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180017ce0`

## callees

- `0x180012290`
- `0x1800125c8`
- `0x18002370c`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18002374a`
- `ntdll!NtQueryInformationToken` at `0x18002378b`
- `ntdll!NtQueryInformationToken` at `0x18002374a`
- `ntdll!NtQueryInformationToken` at `0x18002378b`
- `ntdll!RtlSubAuthoritySid` at `0x1800237aa`
- `ntdll!RtlSubAuthoritySid` at `0x1800237aa`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002379a`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002379a`

## pseudocode

```c
__int64 __fastcall GetIntegrityLevel(HANDLE TokenHandle, ULONG *a2)
{
  unsigned int v4; // ebx
  PSID *v5; // rdi
  PUCHAR v6; // rax
  ULONG TokenInformationLength; // [rsp+60h] [rbp+8h] BYREF

  TokenInformationLength = 0;
  if ( TokenHandle && a2 )
  {
    v4 = NtQueryInformationToken(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength);
    if ( v4 == -1073741789 )
    {
      v5 = (PSID *)AccessHlprAlloc(TokenInformationLength);
      if ( v5 )
      {
        v4 = NtQueryInformationToken(
               TokenHandle,
               TokenIntegrityLevel,
               v5,
               TokenInformationLength,
               &TokenInformationLength);
        if ( !v4 )
        {
          v6 = RtlSubAuthorityCountSid(*v5);
          *a2 = *RtlSubAuthoritySid(*v5, (unsigned __int8)(*v6 - 1));
        }
        FreeTransientObjectSecurityDescriptor(v5);
      }
      else
      {
        return (unsigned int)-1073741801;
      }
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return v4;
}

```

## disassembly

```asm
0x18002370c  push    rbx
0x18002370e  push    rsi
0x18002370f  push    rdi
0x180023710  push    r14
0x180023712  sub     rsp, 38h
0x180023716  mov     [rsp+58h+TokenInformationLength], 0
0x18002371e  mov     r14, rdx
0x180023721  mov     rsi, rcx
0x180023724  test    rcx, rcx
0x180023727  jz      loc_1800237BF
0x18002372d  test    rdx, rdx
0x180023730  jz      loc_1800237BF
0x180023736  xor     r9d, r9d; TokenInformationLength
0x180023739  lea     rax, [rsp+58h+TokenInformationLength]
0x18002373e  xor     r8d, r8d; TokenInformation
0x180023741  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180023746  lea     edx, [r9+19h]; TokenInformationClass
0x18002374a  call    cs:__imp_NtQueryInformationToken
0x180023750  mov     ebx, eax
0x180023752  cmp     eax, 0C0000023h
0x180023757  jnz     short loc_1800237C4
0x180023759  mov     ecx, [rsp+58h+TokenInformationLength]
0x18002375d  call    AccessHlprAlloc
0x180023762  mov     rdi, rax
0x180023765  test    rax, rax
0x180023768  jnz     short loc_180023771
0x18002376a  mov     ebx, 0C0000017h
0x18002376f  jmp     short loc_1800237C4
0x180023771  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x180023776  lea     rax, [rsp+58h+TokenInformationLength]
0x18002377b  mov     r8, rdi; TokenInformation
0x18002377e  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180023783  mov     edx, 19h; TokenInformationClass
0x180023788  mov     rcx, rsi; TokenHandle
0x18002378b  call    cs:__imp_NtQueryInformationToken
0x180023791  mov     ebx, eax
0x180023793  test    eax, eax
0x180023795  jnz     short loc_1800237B5
0x180023797  mov     rcx, [rdi]; Sid
0x18002379a  call    cs:__imp_RtlSubAuthorityCountSid
0x1800237a0  mov     rcx, [rdi]; Sid
0x1800237a3  mov     dl, [rax]
0x1800237a5  dec     dl
0x1800237a7  movzx   edx, dl; SubAuthority
0x1800237aa  call    cs:__imp_RtlSubAuthoritySid
0x1800237b0  mov     edx, [rax]
0x1800237b2  mov     [r14], edx
0x1800237b5  mov     rcx, rdi
0x1800237b8  call    FreeTransientObjectSecurityDescriptor
0x1800237bd  jmp     short loc_1800237C4
0x1800237bf  mov     ebx, 0C000000Dh
0x1800237c4  mov     eax, ebx
0x1800237c6  add     rsp, 38h
0x1800237ca  pop     r14
0x1800237cc  pop     rdi
0x1800237cd  pop     rsi
0x1800237ce  pop     rbx
0x1800237cf  retn
```
