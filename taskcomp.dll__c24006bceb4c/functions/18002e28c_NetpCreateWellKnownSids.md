# NetpCreateWellKnownSids

- ea: `0x18002e28c`
- end: `0x18002e38c`
- name: `NetpCreateWellKnownSids`
- size: `256`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002d308`

## callees

- `0x18002e28c`
- `0x18002e394`
- `0x18002e4bc`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x18002e306`
- `ntdll!RtlSubAuthoritySid` at `0x18002e331`
- `ntdll!RtlSubAuthoritySid` at `0x18002e306`
- `ntdll!RtlSubAuthoritySid` at `0x18002e331`
- `ntdll!RtlLengthRequiredSid` at `0x18002e2ca`
- `ntdll!RtlLengthRequiredSid` at `0x18002e2ca`
- `ntdll!RtlInitializeSid` at `0x18002e2f3`
- `ntdll!RtlInitializeSid` at `0x18002e2f3`

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
    v3 = *(_DWORD *)&byte_18005D248[v2];
    if ( v3 > 2 )
      return 3221225485LL;
    v4 = (&SidData)[v2 / 8];
    v5 = RtlLengthRequiredSid(v3);
    v6 = (void *)NetpMemoryAllocate(v5);
    *v4 = (__int64)v6;
    if ( !v6 )
      return 3221225495LL;
    RtlInitializeSid(v6, (PSID_IDENTIFIER_AUTHORITY)&dword_18005D24C[v2 / 4], v3);
    v7 = RtlSubAuthoritySid((PSID)*(&SidData)[v2 / 8], 0);
    a1 = *(unsigned int *)&algn_18005D250[v2 + 4];
    *v7 = a1;
    if ( *(_DWORD *)&byte_18005D248[v2] == 2 )
    {
      v8 = RtlSubAuthoritySid((PSID)*(&SidData)[v2 / 8], 1u);
      a1 = *(unsigned int *)&algn_18005D250[v2 + 8];
      *v8 = a1;
    }
  }
  for ( j = 0; j < 9; ++j )
  {
    if ( (unsigned int)NetpDomainIdToSid(a1, dword_18005D1B8[4 * j], (PSID *)(&BuiltinDomainSidData)[2 * j]) )
      return 3221225495LL;
  }
  return 0;
}

```

## disassembly

```asm
0x18002e28c  push    rbx
0x18002e28e  push    rbp
0x18002e28f  push    rsi
0x18002e290  push    rdi
0x18002e291  push    r14
0x18002e293  sub     rsp, 20h
0x18002e297  xor     esi, esi
0x18002e299  lea     r14, __ImageBase
0x18002e2a0  cmp     esi, 0Bh
0x18002e2a3  jnb     loc_18002E34F
0x18002e2a9  mov     edi, esi
0x18002e2ab  shl     rdi, 5
0x18002e2af  mov     ebp, [rdi+r14+5D248h]
0x18002e2b7  cmp     ebp, 2
0x18002e2ba  ja      loc_18002E348
0x18002e2c0  mov     rbx, [rdi+r14+5D240h]
0x18002e2c8  mov     ecx, ebp; SubAuthorityCount
0x18002e2ca  call    cs:__imp_RtlLengthRequiredSid
0x18002e2d0  mov     ecx, eax
0x18002e2d2  call    NetpMemoryAllocate
0x18002e2d7  mov     [rbx], rax
0x18002e2da  test    rax, rax
0x18002e2dd  jz      loc_18002E378
0x18002e2e3  lea     rdx, rva dword_18005D24C[r14]
0x18002e2ea  mov     r8b, bpl; SubAuthorityCount
0x18002e2ed  add     rdx, rdi; IdentifierAuthority
0x18002e2f0  mov     rcx, rax; Sid
0x18002e2f3  call    cs:__imp_RtlInitializeSid
0x18002e2f9  mov     rcx, [rdi+r14+5D240h]
0x18002e301  xor     edx, edx; SubAuthority
0x18002e303  mov     rcx, [rcx]; Sid
0x18002e306  call    cs:__imp_RtlSubAuthoritySid
0x18002e30c  mov     ecx, [rdi+r14+5D254h]
0x18002e314  mov     [rax], ecx
0x18002e316  cmp     dword ptr [rdi+r14+5D248h], 2
0x18002e31f  jnz     short loc_18002E341
0x18002e321  mov     rcx, [rdi+r14+5D240h]
0x18002e329  mov     edx, 1; SubAuthority
0x18002e32e  mov     rcx, [rcx]; Sid
0x18002e331  call    cs:__imp_RtlSubAuthoritySid
0x18002e337  mov     ecx, [rdi+r14+5D258h]
0x18002e33f  mov     [rax], ecx
0x18002e341  inc     esi
0x18002e343  jmp     loc_18002E2A0
0x18002e348  mov     eax, 0C000000Dh
0x18002e34d  jmp     short loc_18002E381
0x18002e34f  xor     ebx, ebx
0x18002e351  cmp     ebx, 9
0x18002e354  jnb     short loc_18002E37F
0x18002e356  mov     edx, ebx
0x18002e358  add     rdx, rdx
0x18002e35b  mov     r8, rva BuiltinDomainSidData[r14+rdx*8]
0x18002e363  mov     edx, rva dword_18005D1B8[r14+rdx*8]
0x18002e36b  call    NetpDomainIdToSid
0x18002e370  test    eax, eax
0x18002e372  jnz     short loc_18002E378
0x18002e374  inc     ebx
0x18002e376  jmp     short loc_18002E351
0x18002e378  mov     eax, 0C0000017h
0x18002e37d  jmp     short loc_18002E381
0x18002e37f  xor     eax, eax
0x18002e381  add     rsp, 20h
0x18002e385  pop     r14
0x18002e387  pop     rdi
0x18002e388  pop     rsi
0x18002e389  pop     rbp
0x18002e38a  pop     rbx
0x18002e38b  retn
```
