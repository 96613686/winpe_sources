# Wsp::Health::Sid::ToString(wchar_t * *)

- ea: `0x180079e00`
- end: `0x180079e4b`
- name: `?ToString@Sid@Health@Wsp@@QEAAKPEAPEA_W@Z`
- size: `75`
- prototype: `unsigned int(Wsp::Health::Sid *__hidden this, wchar_t **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180078ec8`
- `0x180079abc`

## callees

- `0x180079e00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079e36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079e36`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180079e14`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180079e14`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180079e2c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180079e2c`

## pseudocode

```c
DWORD __fastcall Wsp::Health::Sid::ToString(PSID *this, wchar_t **a2)
{
  if ( !IsValidSid(this[1]) )
    return 1337;
  if ( ConvertSidToStringSidW(this[1], a2) )
    return 0;
  return GetLastError();
}

```

## disassembly

```asm
0x180079e00  mov     [rsp+arg_0], rbx
0x180079e05  push    rdi
0x180079e06  sub     rsp, 20h
0x180079e0a  mov     rbx, rcx
0x180079e0d  mov     rdi, rdx
0x180079e10  mov     rcx, [rcx+8]; pSid
0x180079e14  call    cs:__imp_IsValidSid
0x180079e1a  test    eax, eax
0x180079e1c  jnz     short loc_180079E25
0x180079e1e  mov     eax, 539h
0x180079e23  jmp     short loc_180079E40
0x180079e25  mov     rcx, [rbx+8]; Sid
0x180079e29  mov     rdx, rdi; StringSid
0x180079e2c  call    cs:__imp_ConvertSidToStringSidW
0x180079e32  test    eax, eax
0x180079e34  jnz     short loc_180079E3E
0x180079e36  call    cs:__imp_GetLastError
0x180079e3c  jmp     short loc_180079E40
0x180079e3e  xor     eax, eax
0x180079e40  mov     rbx, [rsp+28h+arg_0]
0x180079e45  add     rsp, 20h
0x180079e49  pop     rdi
0x180079e4a  retn
```
