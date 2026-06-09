# NetpCreateWellKnownSids

- ea: `0x180030394`
- end: `0x1800304ad`
- name: `NetpCreateWellKnownSids`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002f27c`

## callees

- `0x180030394`
- `0x1800304b4`
- `0x1800305fc`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x18003041a`
- `ntdll!RtlSubAuthoritySid` at `0x18003044b`
- `ntdll!RtlSubAuthoritySid` at `0x18003041a`
- `ntdll!RtlSubAuthoritySid` at `0x18003044b`
- `ntdll!RtlLengthRequiredSid` at `0x1800303d2`
- `ntdll!RtlLengthRequiredSid` at `0x1800303d2`
- `ntdll!RtlInitializeSid` at `0x180030401`
- `ntdll!RtlInitializeSid` at `0x180030401`

## pseudocode

```c
__int64 __fastcall NetpCreateWellKnownSids(__int64 a1)
{
  unsigned int i; // esi
  unsigned __int64 v2; // rdi
  ULONG v3; // ebp
  __int64 *v4; // rbx
  ULONG v5; // eax
  void *v6; // rax
  PULONG v7; // rax
  PULONG v8; // rax
  unsigned int j; // ebx

  for ( i = 0; i < 0xB; ++i )
  {
    v2 = 32LL * i;
    v3 = *(_DWORD *)&byte_18005F1B8[v2];
    if ( v3 > 2 )
      return 3221225485LL;
    v4 = (&SidData)[v2 / 8];
    v5 = RtlLengthRequiredSid(v3);
    v6 = (void *)NetpMemoryAllocate(v5);
    *v4 = (__int64)v6;
    if ( !v6 )
      return 3221225495LL;
    RtlInitializeSid(v6, (PSID_IDENTIFIER_AUTHORITY)&dword_18005F1BC[v2 / 4], v3);
    v7 = RtlSubAuthoritySid((PSID)*(&SidData)[v2 / 8], 0);
    a1 = HIDWORD(qword_18005F1C0[v2 / 8]);
    *v7 = a1;
    if ( *(_DWORD *)&byte_18005F1B8[v2] == 2 )
    {
      v8 = RtlSubAuthoritySid((PSID)*(&SidData)[v2 / 8], 1u);
      a1 = LODWORD(qword_18005F1C0[v2 / 8 + 1]);
      *v8 = a1;
    }
  }
  for ( j = 0; j < 9; ++j )
  {
    if ( (unsigned int)NetpDomainIdToSid(a1, dword_18005F318[4 * j], (PSID *)(&BuiltinDomainSidData)[2 * j]) )
      return 3221225495LL;
  }
  return 0;
}

```

## disassembly

```asm
0x180030394  push    rbx
0x180030396  push    rbp
0x180030397  push    rsi
0x180030398  push    rdi
0x180030399  push    r14
0x18003039b  sub     rsp, 20h
0x18003039f  xor     esi, esi
0x1800303a1  lea     r14, __ImageBase
0x1800303a8  cmp     esi, 0Bh
0x1800303ab  jnb     loc_18003046F
0x1800303b1  mov     edi, esi
0x1800303b3  shl     rdi, 5
0x1800303b7  mov     ebp, [rdi+r14+5F1B8h]
0x1800303bf  cmp     ebp, 2
0x1800303c2  ja      loc_180030468
0x1800303c8  mov     rbx, [rdi+r14+5F1B0h]
0x1800303d0  mov     ecx, ebp; SubAuthorityCount
0x1800303d2  call    cs:__imp_RtlLengthRequiredSid
0x1800303d9  nop     dword ptr [rax+rax+00h]
0x1800303de  mov     ecx, eax
0x1800303e0  call    NetpMemoryAllocate
0x1800303e5  mov     [rbx], rax
0x1800303e8  test    rax, rax
0x1800303eb  jz      loc_180030498
0x1800303f1  lea     rdx, rva dword_18005F1BC[r14]
0x1800303f8  mov     r8b, bpl; SubAuthorityCount
0x1800303fb  add     rdx, rdi; IdentifierAuthority
0x1800303fe  mov     rcx, rax; Sid
0x180030401  call    cs:__imp_RtlInitializeSid
0x180030408  nop     dword ptr [rax+rax+00h]
0x18003040d  mov     rcx, [rdi+r14+5F1B0h]
0x180030415  xor     edx, edx; SubAuthority
0x180030417  mov     rcx, [rcx]; Sid
0x18003041a  call    cs:__imp_RtlSubAuthoritySid
0x180030421  nop     dword ptr [rax+rax+00h]
0x180030426  mov     ecx, [rdi+r14+5F1C4h]
0x18003042e  mov     [rax], ecx
0x180030430  cmp     dword ptr [rdi+r14+5F1B8h], 2
0x180030439  jnz     short loc_180030461
0x18003043b  mov     rcx, [rdi+r14+5F1B0h]
0x180030443  mov     edx, 1; SubAuthority
0x180030448  mov     rcx, [rcx]; Sid
0x18003044b  call    cs:__imp_RtlSubAuthoritySid
0x180030452  nop     dword ptr [rax+rax+00h]
0x180030457  mov     ecx, [rdi+r14+5F1C8h]
0x18003045f  mov     [rax], ecx
0x180030461  inc     esi
0x180030463  jmp     loc_1800303A8
0x180030468  mov     eax, 0C000000Dh
0x18003046d  jmp     short loc_1800304A1
0x18003046f  xor     ebx, ebx
0x180030471  cmp     ebx, 9
0x180030474  jnb     short loc_18003049F
0x180030476  mov     edx, ebx
0x180030478  add     rdx, rdx
0x18003047b  mov     r8, rva BuiltinDomainSidData[r14+rdx*8]
0x180030483  mov     edx, rva dword_18005F318[r14+rdx*8]
0x18003048b  call    NetpDomainIdToSid
0x180030490  test    eax, eax
0x180030492  jnz     short loc_180030498
0x180030494  inc     ebx
0x180030496  jmp     short loc_180030471
0x180030498  mov     eax, 0C0000017h
0x18003049d  jmp     short loc_1800304A1
0x18003049f  xor     eax, eax
0x1800304a1  add     rsp, 20h
0x1800304a5  pop     r14
0x1800304a7  pop     rdi
0x1800304a8  pop     rsi
0x1800304a9  pop     rbp
0x1800304aa  pop     rbx
0x1800304ab  retn
```
