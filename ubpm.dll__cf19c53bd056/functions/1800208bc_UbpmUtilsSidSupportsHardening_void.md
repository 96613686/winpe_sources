# UbpmUtilsSidSupportsHardening(void *)

- ea: `0x1800208bc`
- end: `0x1800208f4`
- name: `?UbpmUtilsSidSupportsHardening@@YAEPEAX@Z`
- size: `56`
- prototype: `unsigned __int8 __fastcall(PSID pSid1)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018ef0`
- `0x180019480`
- `0x1800203d0`
- `0x180020900`
- `0x180021060`

## callees

- `0x1800208bc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800208cc`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800208e0`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800208cc`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800208e0`

## pseudocode

```c
bool __fastcall UbpmUtilsSidSupportsHardening(PSID pSid1)
{
  BOOL v2; // eax

  if ( EqualSid(pSid1, ::pSid1) || (v2 = EqualSid(pSid1, pSid2)) )
    LOBYTE(v2) = 1;
  return v2;
}

```

## disassembly

```asm
0x1800208bc  push    rbx
0x1800208be  sub     rsp, 20h
0x1800208c2  mov     rdx, cs:pSid1; pSid2
0x1800208c9  mov     rbx, rcx
0x1800208cc  call    cs:__imp_EqualSid
0x1800208d2  test    eax, eax
0x1800208d4  jnz     short loc_1800208F0
0x1800208d6  mov     rdx, cs:pSid2; pSid2
0x1800208dd  mov     rcx, rbx; pSid1
0x1800208e0  call    cs:__imp_EqualSid
0x1800208e6  test    eax, eax
0x1800208e8  jnz     short loc_1800208F0
0x1800208ea  add     rsp, 20h
0x1800208ee  pop     rbx
0x1800208ef  retn
0x1800208f0  mov     al, 1
0x1800208f2  jmp     short loc_1800208EA
```
