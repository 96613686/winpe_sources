# SampMatchDomainPrefix(void *,void *)

- ea: `0x1800259ec`
- end: `0x180025a8b`
- name: `?SampMatchDomainPrefix@@YAEPEAX0@Z`
- size: `159`
- prototype: `unsigned __int8 __fastcall(PSID Sid, PSID)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18008fcac`
- `0x18009642c`
- `0x18009c6d4`

## callees

- `0x1800259ec`
- `0x1800bb77c`

## import_xrefs

- `ntdll!RtlIdentifierAuthoritySid` at `0x180025a1c`
- `ntdll!RtlIdentifierAuthoritySid` at `0x180025a28`
- `ntdll!RtlIdentifierAuthoritySid` at `0x180025a1c`
- `ntdll!RtlIdentifierAuthoritySid` at `0x180025a28`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800259fb`
- `ntdll!RtlSubAuthorityCountSid` at `0x180025a07`
- `ntdll!RtlSubAuthorityCountSid` at `0x180025a45`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800259fb`
- `ntdll!RtlSubAuthorityCountSid` at `0x180025a07`
- `ntdll!RtlSubAuthorityCountSid` at `0x180025a45`
- `ntdll!RtlSubAuthoritySid` at `0x180025a57`
- `ntdll!RtlSubAuthoritySid` at `0x180025a65`
- `ntdll!RtlSubAuthoritySid` at `0x180025a57`
- `ntdll!RtlSubAuthoritySid` at `0x180025a65`

## pseudocode

```c
bool __fastcall SampMatchDomainPrefix(PSID Sid, PSID a2)
{
  int v4; // ebx
  PSID_IDENTIFIER_AUTHORITY v5; // rbx
  PSID_IDENTIFIER_AUTHORITY v6; // rax
  int v7; // ecx
  size_t v8; // rdi
  PULONG v9; // rbx
  PULONG v10; // rax

  v4 = *RtlSubAuthorityCountSid(Sid);
  if ( *RtlSubAuthorityCountSid(a2) + 1 != v4 )
    return 0;
  v5 = RtlIdentifierAuthoritySid(Sid);
  v6 = RtlIdentifierAuthoritySid(a2);
  v7 = *(_DWORD *)v6->Value - *(_DWORD *)v5->Value;
  if ( *(_DWORD *)v6->Value == *(_DWORD *)v5->Value )
    v7 = *(unsigned __int16 *)&v6->Value[4] - *(unsigned __int16 *)&v5->Value[4];
  if ( v7 )
    return 0;
  v8 = 4LL * *RtlSubAuthorityCountSid(a2);
  v9 = RtlSubAuthoritySid(Sid, 0);
  v10 = RtlSubAuthoritySid(a2, 0);
  return memcmp_0(v10, v9, v8) == 0;
}

```

## disassembly

```asm
0x1800259ec  push    rbx
0x1800259ee  push    rbp
0x1800259ef  push    rsi
0x1800259f0  push    rdi
0x1800259f1  sub     rsp, 28h
0x1800259f5  mov     rsi, rdx
0x1800259f8  mov     rbp, rcx
0x1800259fb  call    cs:__imp_RtlSubAuthorityCountSid
0x180025a01  mov     rcx, rsi; Sid
0x180025a04  movzx   ebx, byte ptr [rax]
0x180025a07  call    cs:__imp_RtlSubAuthorityCountSid
0x180025a0d  movzx   r8d, byte ptr [rax]
0x180025a11  inc     r8d
0x180025a14  cmp     r8d, ebx
0x180025a17  jnz     short loc_180025A80
0x180025a19  mov     rcx, rbp; Sid
0x180025a1c  call    cs:__imp_RtlIdentifierAuthoritySid
0x180025a22  mov     rcx, rsi; Sid
0x180025a25  mov     rbx, rax
0x180025a28  call    cs:__imp_RtlIdentifierAuthoritySid
0x180025a2e  mov     ecx, [rax]
0x180025a30  sub     ecx, [rbx]
0x180025a32  jnz     short loc_180025A3E
0x180025a34  movzx   ecx, word ptr [rax+4]
0x180025a38  movzx   eax, word ptr [rbx+4]
0x180025a3c  sub     ecx, eax
0x180025a3e  test    ecx, ecx
0x180025a40  jnz     short loc_180025A80
0x180025a42  mov     rcx, rsi; Sid
0x180025a45  call    cs:__imp_RtlSubAuthorityCountSid
0x180025a4b  xor     edx, edx; SubAuthority
0x180025a4d  mov     rcx, rbp; Sid
0x180025a50  movzx   edi, byte ptr [rax]
0x180025a53  shl     rdi, 2
0x180025a57  call    cs:__imp_RtlSubAuthoritySid
0x180025a5d  xor     edx, edx; SubAuthority
0x180025a5f  mov     rcx, rsi; Sid
0x180025a62  mov     rbx, rax
0x180025a65  call    cs:__imp_RtlSubAuthoritySid
0x180025a6b  mov     r8, rdi; Size
0x180025a6e  mov     rdx, rbx; Buf2
0x180025a71  mov     rcx, rax; Buf1
0x180025a74  call    memcmp_0
0x180025a79  test    eax, eax
0x180025a7b  setz    al
0x180025a7e  jmp     short loc_180025A82
0x180025a80  xor     al, al
0x180025a82  add     rsp, 28h
0x180025a86  pop     rdi
0x180025a87  pop     rsi
0x180025a88  pop     rbp
0x180025a89  pop     rbx
0x180025a8a  retn
```
