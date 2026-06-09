# RpcpIsWellKnownSid(void *)

- ea: `0x180034c58`
- end: `0x180034cba`
- name: `?RpcpIsWellKnownSid@@YAHPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(PSID pSid1)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800345ac`
- `0x1800360bc`

## callees

- `0x180034c58`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180034c68`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180034c8e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180034ca8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180034c68`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180034c8e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180034ca8`

## pseudocode

```c
BOOL __fastcall RpcpIsWellKnownSid(PSID pSid1)
{
  BOOL result; // eax

  if ( EqualSid(pSid1, &LocalSystem) )
    return 1;
  if ( EqualSid(pSid1, &LocalService) )
    return 1;
  result = EqualSid(pSid1, &NetworkService);
  if ( result )
    return 1;
  return result;
}

```

## disassembly

```asm
0x180034c58  push    rbx
0x180034c5a  sub     rsp, 20h
0x180034c5e  lea     rdx, ?LocalSystem@@3U_SID@@B; pSid2
0x180034c65  mov     rbx, rcx
0x180034c68  call    cs:__imp_EqualSid
0x180034c6f  nop     dword ptr [rax+rax+00h]
0x180034c74  test    eax, eax
0x180034c76  jz      short loc_180034C84
0x180034c78  mov     eax, 1
0x180034c7d  add     rsp, 20h
0x180034c81  pop     rbx
0x180034c82  retn
0x180034c84  lea     rdx, ?LocalService@@3U_SID@@B; pSid2
0x180034c8b  mov     rcx, rbx; pSid1
0x180034c8e  call    cs:__imp_EqualSid
0x180034c95  nop     dword ptr [rax+rax+00h]
0x180034c9a  test    eax, eax
0x180034c9c  jnz     short loc_180034C78
0x180034c9e  lea     rdx, ?NetworkService@@3U_SID@@B; pSid2
0x180034ca5  mov     rcx, rbx; pSid1
0x180034ca8  call    cs:__imp_EqualSid
0x180034caf  nop     dword ptr [rax+rax+00h]
0x180034cb4  test    eax, eax
0x180034cb6  jnz     short loc_180034C78
0x180034cb8  jmp     short loc_180034C7D
```
