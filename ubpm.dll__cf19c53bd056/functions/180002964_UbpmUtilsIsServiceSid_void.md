# UbpmUtilsIsServiceSid(void *)

- ea: `0x180002964`
- end: `0x1800029d2`
- name: `?UbpmUtilsIsServiceSid@@YAEPEAX@Z`
- size: `110`
- prototype: `unsigned __int8 __fastcall(PSID pSid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180001fb0`

## callees

- `0x180002964`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800029b6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800029b6`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18000296d`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18000296d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800029a1`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800029a1`

## pseudocode

```c
bool __fastcall UbpmUtilsIsServiceSid(PSID pSid)
{
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rax
  int v3; // ecx
  PUCHAR SidSubAuthorityCount; // rax
  PDWORD SidSubAuthority; // rax

  SidIdentifierAuthority = GetSidIdentifierAuthority(pSid);
  if ( !SidIdentifierAuthority )
    return 0;
  v3 = *(_DWORD *)SidIdentifierAuthority->Value;
  if ( !*(_DWORD *)SidIdentifierAuthority->Value )
    v3 = *(unsigned __int16 *)&SidIdentifierAuthority->Value[4] - 1280;
  return !v3
      && (SidSubAuthorityCount = GetSidSubAuthorityCount(pSid)) != 0
      && *SidSubAuthorityCount == 6
      && (SidSubAuthority = GetSidSubAuthority(pSid, 0)) != 0
      && *SidSubAuthority == 80;
}

```

## disassembly

```asm
0x180002964  push    rbx
0x180002966  sub     rsp, 20h
0x18000296a  mov     rbx, rcx
0x18000296d  call    cs:__imp_GetSidIdentifierAuthority
0x180002973  test    rax, rax
0x180002976  jz      short loc_1800029CA
0x180002978  mov     ecx, [rax]
0x18000297a  mov     [rsp+28h+arg_8], 0
0x180002982  mov     [rsp+28h+arg_C], 500h
0x180002989  sub     ecx, [rsp+28h+arg_8]
0x18000298d  jnz     short loc_18000299A
0x18000298f  movzx   ecx, word ptr [rax+4]
0x180002993  movzx   eax, [rsp+28h+arg_C]
0x180002998  sub     ecx, eax
0x18000299a  test    ecx, ecx
0x18000299c  jnz     short loc_1800029CA
0x18000299e  mov     rcx, rbx; pSid
0x1800029a1  call    cs:__imp_GetSidSubAuthorityCount
0x1800029a7  test    rax, rax
0x1800029aa  jz      short loc_1800029CA
0x1800029ac  cmp     byte ptr [rax], 6
0x1800029af  jnz     short loc_1800029CA
0x1800029b1  xor     edx, edx; nSubAuthority
0x1800029b3  mov     rcx, rbx; pSid
0x1800029b6  call    cs:__imp_GetSidSubAuthority
0x1800029bc  test    rax, rax
0x1800029bf  jz      short loc_1800029CA
0x1800029c1  cmp     dword ptr [rax], 50h ; 'P'
0x1800029c4  jnz     short loc_1800029CA
0x1800029c6  mov     al, 1
0x1800029c8  jmp     short loc_1800029CC
0x1800029ca  xor     al, al
0x1800029cc  add     rsp, 20h
0x1800029d0  pop     rbx
0x1800029d1  retn
```
