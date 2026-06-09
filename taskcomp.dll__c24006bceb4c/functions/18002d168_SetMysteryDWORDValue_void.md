# SetMysteryDWORDValue(void)

- ea: `0x18002d168`
- end: `0x18002d206`
- name: `?SetMysteryDWORDValue@@YAXXZ`
- size: `158`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002cfcc`

## callees

- `0x18002d168`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d173`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d173`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d1ff`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002d18d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002d18d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002d1b2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002d1b2`

## pseudocode

```c
void SetMysteryDWORDValue(void)
{
  PUCHAR SidSubAuthorityCount; // rax
  int v1; // edx
  PDWORD SidSubAuthority; // rax
  int v3; // ecx

  EnterCriticalSection(&gcsSSCritSection);
  if ( !gdwKeyElement )
  {
    SidSubAuthorityCount = GetSidSubAuthorityCount(*((PSID *)gpDomainInfo + 2));
    v1 = 2;
    if ( SidSubAuthorityCount && *SidSubAuthorityCount > 2u )
      v1 = *SidSubAuthorityCount;
    SidSubAuthority = GetSidSubAuthority(*((PSID *)gpDomainInfo + 2), v1 - 2);
    if ( !SidSubAuthority || (v3 = 626736992, (*(_BYTE *)SidSubAuthority & 1) == 0) )
      v3 = 344708384;
    gdwKeyElement = v3 & ((gwszComputerName & 0x100) != 0 ? -1069583933 : -481267149);
  }
  LeaveCriticalSection(&gcsSSCritSection);
}

```

## disassembly

```asm
0x18002d168  sub     rsp, 28h
0x18002d16c  lea     rcx, ?gcsSSCritSection@@3VCStaticCritSec@@A; lpCriticalSection
0x18002d173  call    cs:__imp_EnterCriticalSection
0x18002d179  cmp     cs:?gdwKeyElement@@3KA, 0; ulong gdwKeyElement
0x18002d180  jnz     short loc_18002D1F4
0x18002d182  mov     rcx, cs:?gpDomainInfo@@3PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@EA; _POLICY_ACCOUNT_DOMAIN_INFO * gpDomainInfo
0x18002d189  mov     rcx, [rcx+10h]; pSid
0x18002d18d  call    cs:__imp_GetSidSubAuthorityCount
0x18002d193  mov     edx, 2
0x18002d198  test    rax, rax
0x18002d19b  jz      short loc_18002D1A4
0x18002d19d  cmp     [rax], dl
0x18002d19f  jbe     short loc_18002D1A4
0x18002d1a1  movzx   edx, byte ptr [rax]
0x18002d1a4  mov     rcx, cs:?gpDomainInfo@@3PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@EA; _POLICY_ACCOUNT_DOMAIN_INFO * gpDomainInfo
0x18002d1ab  add     edx, 0FFFFFFFEh; nSubAuthority
0x18002d1ae  mov     rcx, [rcx+10h]; pSid
0x18002d1b2  call    cs:__imp_GetSidSubAuthority
0x18002d1b8  test    rax, rax
0x18002d1bb  jz      short loc_18002D1C7
0x18002d1bd  test    byte ptr [rax], 1
0x18002d1c0  mov     ecx, 255B3F60h
0x18002d1c5  jnz     short loc_18002D1CC
0x18002d1c7  mov     ecx, 148BD520h
0x18002d1cc  movzx   eax, cs:?gwszComputerName@@3PAGA; ushort near * gwszComputerName
0x18002d1d3  mov     edx, 100h
0x18002d1d8  and     ax, dx
0x18002d1db  neg     ax
0x18002d1de  sbb     edx, edx
0x18002d1e0  and     edx, 0DCEEFF90h
0x18002d1e6  add     edx, 0E3507233h
0x18002d1ec  and     edx, ecx
0x18002d1ee  mov     cs:?gdwKeyElement@@3KA, edx; ulong gdwKeyElement
0x18002d1f4  lea     rcx, ?gcsSSCritSection@@3VCStaticCritSec@@A; CStaticCritSec gcsSSCritSection
0x18002d1fb  add     rsp, 28h
0x18002d1ff  jmp     cs:__imp_LeaveCriticalSection
```
