# RpcpIsWellKnownSid(void *)

- ea: `0x18003408c`
- end: `0x1800340db`
- name: `?RpcpIsWellKnownSid@@YAHPEAX@Z`
- size: `79`
- prototype: `__int64 __fastcall(PSID pSid1)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180033100`
- `0x180035da0`

## callees

- `0x18003408c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003409c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800340bb`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800340cf`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003409c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800340bb`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800340cf`

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
0x18003408c  push    rbx
0x18003408e  sub     rsp, 20h
0x180034092  lea     rdx, ?LocalSystem@@3U_SID@@B; pSid2
0x180034099  mov     rbx, rcx
0x18003409c  call    cs:__imp_EqualSid
0x1800340a2  test    eax, eax
0x1800340a4  jz      short loc_1800340B1
0x1800340a6  mov     eax, 1
0x1800340ab  add     rsp, 20h
0x1800340af  pop     rbx
0x1800340b0  retn
0x1800340b1  lea     rdx, ?LocalService@@3U_SID@@B; pSid2
0x1800340b8  mov     rcx, rbx; pSid1
0x1800340bb  call    cs:__imp_EqualSid
0x1800340c1  test    eax, eax
0x1800340c3  jnz     short loc_1800340A6
0x1800340c5  lea     rdx, ?NetworkService@@3U_SID@@B; pSid2
0x1800340cc  mov     rcx, rbx; pSid1
0x1800340cf  call    cs:__imp_EqualSid
0x1800340d5  test    eax, eax
0x1800340d7  jnz     short loc_1800340A6
0x1800340d9  jmp     short loc_1800340AB
```
