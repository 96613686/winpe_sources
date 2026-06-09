# Wsp::Health::Token::GetInformation(_TOKEN_INFORMATION_CLASS,void *,ulong,ulong *)

- ea: `0x18007ac80`
- end: `0x18007acbf`
- name: `?GetInformation@Token@Health@Wsp@@QEAAKW4_TOKEN_INFORMATION_CLASS@@PEAXKPEAK@Z`
- size: `63`
- prototype: `unsigned int __fastcall(Wsp::Health::Token *__hidden this, enum _TOKEN_INFORMATION_CLASS, void *, unsigned int, PDWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18007acc8`

## callees

- `0x18007ac80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007acab`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007ac97`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007ac97`

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
0x18007ac80  sub     rsp, 38h
0x18007ac84  mov     rax, [rsp+38h+arg_20]
0x18007ac89  mov     edx, 1; TokenInformationClass
0x18007ac8e  mov     rcx, [rcx+8]; TokenHandle
0x18007ac92  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18007ac97  call    cs:__imp_GetTokenInformation
0x18007ac9e  nop     dword ptr [rax+rax+00h]
0x18007aca3  test    eax, eax
0x18007aca5  jnz     short loc_18007ACB7
0x18007aca7  add     rsp, 38h
0x18007acab  jmp     cs:__imp_GetLastError
0x18007acb7  xor     eax, eax
0x18007acb9  add     rsp, 38h
0x18007acbd  retn
```
