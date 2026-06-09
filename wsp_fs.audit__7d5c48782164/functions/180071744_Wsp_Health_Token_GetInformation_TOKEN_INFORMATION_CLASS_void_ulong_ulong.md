# Wsp::Health::Token::GetInformation(_TOKEN_INFORMATION_CLASS,void *,ulong,ulong *)

- ea: `0x180071744`
- end: `0x180071783`
- name: `?GetInformation@Token@Health@Wsp@@QEAAKW4_TOKEN_INFORMATION_CLASS@@PEAXKPEAK@Z`
- size: `63`
- prototype: `unsigned int __fastcall(Wsp::Health::Token *__hidden this, enum _TOKEN_INFORMATION_CLASS, void *, unsigned int, PDWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18007178c`

## callees

- `0x180071744`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007176f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007175b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007175b`

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
0x180071744  sub     rsp, 38h
0x180071748  mov     rax, [rsp+38h+arg_20]
0x18007174d  mov     edx, 1; TokenInformationClass
0x180071752  mov     rcx, [rcx+8]; TokenHandle
0x180071756  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18007175b  call    cs:__imp_GetTokenInformation
0x180071762  nop     dword ptr [rax+rax+00h]
0x180071767  test    eax, eax
0x180071769  jnz     short loc_18007177B
0x18007176b  add     rsp, 38h
0x18007176f  jmp     cs:__imp_GetLastError
0x18007177b  xor     eax, eax
0x18007177d  add     rsp, 38h
0x180071781  retn
```
