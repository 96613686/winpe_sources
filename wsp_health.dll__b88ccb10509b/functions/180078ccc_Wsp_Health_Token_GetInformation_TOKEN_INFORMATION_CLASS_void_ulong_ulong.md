# Wsp::Health::Token::GetInformation(_TOKEN_INFORMATION_CLASS,void *,ulong,ulong *)

- ea: `0x180078ccc`
- end: `0x180078cff`
- name: `?GetInformation@Token@Health@Wsp@@QEAAKW4_TOKEN_INFORMATION_CLASS@@PEAXKPEAK@Z`
- size: `51`
- prototype: `unsigned int __fastcall(Wsp::Health::Token *__hidden this, enum _TOKEN_INFORMATION_CLASS, void *, unsigned int, PDWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180078d08`

## callees

- `0x180078ccc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078cf1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180078ce3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180078ce3`

## pseudocode

```c
DWORD __fastcall Wsp::Health::Token::GetInformation(
        HANDLE *this,
        enum _TOKEN_INFORMATION_CLASS a2,
        void *a3,
        DWORD a4,
        PDWORD ReturnLength)
{
  if ( GetTokenInformation(this[1], TokenUser, a3, a4, ReturnLength) )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180078ccc  sub     rsp, 38h
0x180078cd0  mov     rax, [rsp+38h+arg_20]
0x180078cd5  mov     edx, 1; TokenInformationClass
0x180078cda  mov     rcx, [rcx+8]; TokenHandle
0x180078cde  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180078ce3  call    cs:__imp_GetTokenInformation
0x180078ce9  test    eax, eax
0x180078ceb  jnz     short loc_180078CF8
0x180078ced  add     rsp, 38h
0x180078cf1  jmp     cs:__imp_GetLastError
0x180078cf8  xor     eax, eax
0x180078cfa  add     rsp, 38h
0x180078cfe  retn
```
