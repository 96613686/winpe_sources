# Wsp::Health::Token::TryOpenThreadToken(ulong,int,void *)

- ea: `0x180079e54`
- end: `0x180079ea3`
- name: `?TryOpenThreadToken@Token@Health@Wsp@@QEAAKKHPEAX@Z`
- size: `79`
- prototype: `unsigned int(Wsp::Health::Token *__hidden this, unsigned int, int, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180077e7c`
- `0x1800791b8`

## callees

- `0x18007872c`
- `0x180079e54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079e89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079e89`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180079e7f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180079e7f`

## pseudocode

```c
DWORD __fastcall Wsp::Health::Token::TryOpenThreadToken(void **this, DWORD a2, __int64 a3, void *a4)
{
  Wsp::Health::Token::Clear((Wsp::Health::Token *)this);
  if ( OpenThreadToken(a4, a2, 1, this + 1) )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180079e54  mov     [rsp+arg_0], rbx
0x180079e59  mov     [rsp+arg_8], rsi
0x180079e5e  push    rdi
0x180079e5f  sub     rsp, 20h
0x180079e63  mov     rsi, r9
0x180079e66  mov     edi, edx
0x180079e68  mov     rbx, rcx
0x180079e6b  call    ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
0x180079e70  lea     r9, [rbx+8]; TokenHandle
0x180079e74  mov     r8d, 1; OpenAsSelf
0x180079e7a  mov     edx, edi; DesiredAccess
0x180079e7c  mov     rcx, rsi; ThreadHandle
0x180079e7f  call    cs:__imp_OpenThreadToken
0x180079e85  test    eax, eax
0x180079e87  jnz     short loc_180079E91
0x180079e89  call    cs:__imp_GetLastError
0x180079e8f  jmp     short loc_180079E93
0x180079e91  xor     eax, eax
0x180079e93  mov     rbx, [rsp+28h+arg_0]
0x180079e98  mov     rsi, [rsp+28h+arg_8]
0x180079e9d  add     rsp, 20h
0x180079ea1  pop     rdi
0x180079ea2  retn
```
