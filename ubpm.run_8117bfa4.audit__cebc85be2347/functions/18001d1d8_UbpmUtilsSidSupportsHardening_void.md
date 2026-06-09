# UbpmUtilsSidSupportsHardening(void *)

- ea: `0x18001d1d8`
- end: `0x18001d21d`
- name: `?UbpmUtilsSidSupportsHardening@@YAEPEAX@Z`
- size: `69`
- prototype: `unsigned __int8 __fastcall(PSID pSid1)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ec90`
- `0x18000f284`
- `0x18001cb40`
- `0x18001d230`
- `0x18001da20`

## callees

- `0x18001d1d8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001d1e8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001d202`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001d1e8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001d202`

## pseudocode

```c
bool __fastcall UbpmUtilsSidSupportsHardening(PSID pSid1)
{
  BOOL v2; // eax

  if ( EqualSid(pSid1, pSid2) || (v2 = EqualSid(pSid1, qword_18004FF68)) )
    LOBYTE(v2) = 1;
  return v2;
}

```

## disassembly

```asm
0x18001d1d8  push    rbx
0x18001d1da  sub     rsp, 20h
0x18001d1de  mov     rdx, cs:pSid2; pSid2
0x18001d1e5  mov     rbx, rcx
0x18001d1e8  call    cs:__imp_EqualSid
0x18001d1ef  nop     dword ptr [rax+rax+00h]
0x18001d1f4  test    eax, eax
0x18001d1f6  jnz     short loc_18001D219
0x18001d1f8  mov     rdx, cs:qword_18004FF68; pSid2
0x18001d1ff  mov     rcx, rbx; pSid1
0x18001d202  call    cs:__imp_EqualSid
0x18001d209  nop     dword ptr [rax+rax+00h]
0x18001d20e  test    eax, eax
0x18001d210  jnz     short loc_18001D219
0x18001d212  add     rsp, 20h
0x18001d216  pop     rbx
0x18001d217  retn
0x18001d219  mov     al, 1
0x18001d21b  jmp     short loc_18001D212
```
