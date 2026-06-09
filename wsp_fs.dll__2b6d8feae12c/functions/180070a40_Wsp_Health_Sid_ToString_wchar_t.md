# Wsp::Health::Sid::ToString(wchar_t * *)

- ea: `0x180070a40`
- end: `0x180070a8b`
- name: `?ToString@Sid@Health@Wsp@@QEAAKPEAPEA_W@Z`
- size: `75`
- prototype: `unsigned int(Wsp::Health::Sid *__hidden this, wchar_t **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180070724`

## callees

- `0x180070a40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070a76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070a76`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180070a54`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180070a54`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180070a6c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180070a6c`

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
0x180070a40  mov     [rsp+arg_0], rbx
0x180070a45  push    rdi
0x180070a46  sub     rsp, 20h
0x180070a4a  mov     rbx, rcx
0x180070a4d  mov     rdi, rdx
0x180070a50  mov     rcx, [rcx+8]; pSid
0x180070a54  call    cs:__imp_IsValidSid
0x180070a5a  test    eax, eax
0x180070a5c  jnz     short loc_180070A65
0x180070a5e  mov     eax, 539h
0x180070a63  jmp     short loc_180070A80
0x180070a65  mov     rcx, [rbx+8]; Sid
0x180070a69  mov     rdx, rdi; StringSid
0x180070a6c  call    cs:__imp_ConvertSidToStringSidW
0x180070a72  test    eax, eax
0x180070a74  jnz     short loc_180070A7E
0x180070a76  call    cs:__imp_GetLastError
0x180070a7c  jmp     short loc_180070A80
0x180070a7e  xor     eax, eax
0x180070a80  mov     rbx, [rsp+28h+arg_0]
0x180070a85  add     rsp, 20h
0x180070a89  pop     rdi
0x180070a8a  retn
```
