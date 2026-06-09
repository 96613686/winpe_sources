# RIDFromSID(void * const)

- ea: `0x180008230`
- end: `0x180008262`
- name: `?RIDFromSID@@YAKQEAX@Z`
- size: `50`
- prototype: `unsigned int __fastcall(PSID pSid)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800063b0`
- `0x18000ddc0`
- `0x18000de40`
- `0x1800100e4`

## callees

- `0x180008230`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000823e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000823e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000824c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000824c`

## pseudocode

```c
__int64 __fastcall RIDFromSID(PSID pSid)
{
  PUCHAR SidSubAuthorityCount; // rax

  if ( !pSid )
    return 0;
  SidSubAuthorityCount = GetSidSubAuthorityCount(pSid);
  return *GetSidSubAuthority(pSid, (unsigned int)*SidSubAuthorityCount - 1);
}

```

## disassembly

```asm
0x180008230  push    rbx
0x180008232  sub     rsp, 20h
0x180008236  mov     rbx, rcx
0x180008239  test    rcx, rcx
0x18000823c  jz      short loc_18000825A
0x18000823e  call    cs:__imp_GetSidSubAuthorityCount
0x180008244  mov     rcx, rbx; pSid
0x180008247  movzx   edx, byte ptr [rax]
0x18000824a  dec     edx; nSubAuthority
0x18000824c  call    cs:__imp_GetSidSubAuthority
0x180008252  mov     eax, [rax]
0x180008254  add     rsp, 20h
0x180008258  pop     rbx
0x180008259  retn
0x18000825a  xor     eax, eax
0x18000825c  add     rsp, 20h
0x180008260  pop     rbx
0x180008261  retn
```
