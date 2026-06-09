# SetMysteryDWORDValue(void)

- ea: `0x18002f0a4`
- end: `0x18002f159`
- name: `?SetMysteryDWORDValue@@YAXXZ`
- size: `181`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002eed8`

## callees

- `0x18002f0a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f0af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f0af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f14d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002f0cf`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002f0cf`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002f0fa`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002f0fa`

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
0x18002f0a4  sub     rsp, 28h
0x18002f0a8  lea     rcx, ?gcsSSCritSection@@3VCStaticCritSec@@A; lpCriticalSection
0x18002f0af  call    cs:__imp_EnterCriticalSection
0x18002f0b6  nop     dword ptr [rax+rax+00h]
0x18002f0bb  cmp     cs:?gdwKeyElement@@3KA, 0; ulong gdwKeyElement
0x18002f0c2  jnz     short loc_18002F142
0x18002f0c4  mov     rcx, cs:?gpDomainInfo@@3PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@EA; _POLICY_ACCOUNT_DOMAIN_INFO * gpDomainInfo
0x18002f0cb  mov     rcx, [rcx+10h]; pSid
0x18002f0cf  call    cs:__imp_GetSidSubAuthorityCount
0x18002f0d6  nop     dword ptr [rax+rax+00h]
0x18002f0db  mov     edx, 2
0x18002f0e0  test    rax, rax
0x18002f0e3  jz      short loc_18002F0EC
0x18002f0e5  cmp     [rax], dl
0x18002f0e7  jbe     short loc_18002F0EC
0x18002f0e9  movzx   edx, byte ptr [rax]
0x18002f0ec  mov     rcx, cs:?gpDomainInfo@@3PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@EA; _POLICY_ACCOUNT_DOMAIN_INFO * gpDomainInfo
0x18002f0f3  add     edx, 0FFFFFFFEh; nSubAuthority
0x18002f0f6  mov     rcx, [rcx+10h]; pSid
0x18002f0fa  call    cs:__imp_GetSidSubAuthority
0x18002f101  nop     dword ptr [rax+rax+00h]
0x18002f106  test    rax, rax
0x18002f109  jz      short loc_18002F115
0x18002f10b  test    byte ptr [rax], 1
0x18002f10e  mov     ecx, 255B3F60h
0x18002f113  jnz     short loc_18002F11A
0x18002f115  mov     ecx, 148BD520h
0x18002f11a  movzx   eax, cs:?gwszComputerName@@3PAGA; ushort near * gwszComputerName
0x18002f121  mov     edx, 100h
0x18002f126  and     ax, dx
0x18002f129  neg     ax
0x18002f12c  sbb     edx, edx
0x18002f12e  and     edx, 0DCEEFF90h
0x18002f134  add     edx, 0E3507233h
0x18002f13a  and     edx, ecx
0x18002f13c  mov     cs:?gdwKeyElement@@3KA, edx; ulong gdwKeyElement
0x18002f142  lea     rcx, ?gcsSSCritSection@@3VCStaticCritSec@@A; CStaticCritSec gcsSSCritSection
0x18002f149  add     rsp, 28h
0x18002f14d  jmp     cs:__imp_LeaveCriticalSection
```
