# _DPACompareSids(_SID *,_SID *,__int64)

- ea: `0x180009310`
- end: `0x18000938f`
- name: `?_DPACompareSids@@YAHPEAU_SID@@0_J@Z`
- size: `127`
- prototype: `int __stdcall(void *p1, void *p2, LPARAM lParam)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180009310`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000932c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000934c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000932c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000934c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000933a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000935a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000933a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000935a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000936c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000936c`

## pseudocode

```c
__int64 __fastcall _DPACompareSids(void *p1, void *p2, LPARAM lParam)
{
  DWORD v3; // esi
  PUCHAR SidSubAuthorityCount; // rax
  DWORD v7; // eax
  PUCHAR v8; // rax

  v3 = 0;
  if ( p1 )
  {
    SidSubAuthorityCount = GetSidSubAuthorityCount(p1);
    v3 = *GetSidSubAuthority(p1, (unsigned int)*SidSubAuthorityCount - 1);
  }
  v7 = 0;
  if ( p2 )
  {
    v8 = GetSidSubAuthorityCount(p2);
    v7 = *GetSidSubAuthority(p2, (unsigned int)*v8 - 1);
  }
  if ( v3 == v7 && EqualSid(p1, p2) )
    return 0;
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180009310  mov     [rsp+arg_0], rbx
0x180009315  mov     [rsp+arg_8], rsi
0x18000931a  push    rdi
0x18000931b  sub     rsp, 20h
0x18000931f  xor     esi, esi
0x180009321  mov     rbx, rdx
0x180009324  mov     rdi, rcx
0x180009327  test    rcx, rcx
0x18000932a  jz      short loc_180009342
0x18000932c  call    cs:__imp_GetSidSubAuthorityCount
0x180009332  mov     rcx, rdi; pSid
0x180009335  movzx   edx, byte ptr [rax]
0x180009338  dec     edx; nSubAuthority
0x18000933a  call    cs:__imp_GetSidSubAuthority
0x180009340  mov     esi, [rax]
0x180009342  xor     eax, eax
0x180009344  test    rbx, rbx
0x180009347  jz      short loc_180009362
0x180009349  mov     rcx, rbx; pSid
0x18000934c  call    cs:__imp_GetSidSubAuthorityCount
0x180009352  mov     rcx, rbx; pSid
0x180009355  movzx   edx, byte ptr [rax]
0x180009358  dec     edx; nSubAuthority
0x18000935a  call    cs:__imp_GetSidSubAuthority
0x180009360  mov     eax, [rax]
0x180009362  cmp     esi, eax
0x180009364  jnz     short loc_18000937A
0x180009366  mov     rdx, rbx; pSid2
0x180009369  mov     rcx, rdi; pSid1
0x18000936c  call    cs:__imp_EqualSid
0x180009372  test    eax, eax
0x180009374  jz      short loc_18000937A
0x180009376  xor     eax, eax
0x180009378  jmp     short loc_18000937F
0x18000937a  mov     eax, 0FFFFFFFFh
0x18000937f  mov     rbx, [rsp+28h+arg_0]
0x180009384  mov     rsi, [rsp+28h+arg_8]
0x180009389  add     rsp, 20h
0x18000938d  pop     rdi
0x18000938e  retn
```
