# Wsp::Health::Token::GetInformation(_TOKEN_INFORMATION_CLASS,void *,ulong,ulong *)

- ea: `0x18006fd98`
- end: `0x18006fdcb`
- name: `?GetInformation@Token@Health@Wsp@@QEAAKW4_TOKEN_INFORMATION_CLASS@@PEAXKPEAK@Z`
- size: `51`
- prototype: `unsigned int __fastcall(Wsp::Health::Token *__hidden this, enum _TOKEN_INFORMATION_CLASS, void *, unsigned int, PDWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18006fdd4`

## callees

- `0x18006fd98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fdbd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006fdaf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006fdaf`

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
0x18006fd98  sub     rsp, 38h
0x18006fd9c  mov     rax, [rsp+38h+arg_20]
0x18006fda1  mov     edx, 1; TokenInformationClass
0x18006fda6  mov     rcx, [rcx+8]; TokenHandle
0x18006fdaa  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18006fdaf  call    cs:__imp_GetTokenInformation
0x18006fdb5  test    eax, eax
0x18006fdb7  jnz     short loc_18006FDC4
0x18006fdb9  add     rsp, 38h
0x18006fdbd  jmp     cs:__imp_GetLastError
0x18006fdc4  xor     eax, eax
0x18006fdc6  add     rsp, 38h
0x18006fdca  retn
```
