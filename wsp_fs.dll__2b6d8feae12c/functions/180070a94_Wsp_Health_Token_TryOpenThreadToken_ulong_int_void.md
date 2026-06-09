# Wsp::Health::Token::TryOpenThreadToken(ulong,int,void *)

- ea: `0x180070a94`
- end: `0x180070ae3`
- name: `?TryOpenThreadToken@Token@Health@Wsp@@QEAAKKHPEAX@Z`
- size: `79`
- prototype: `unsigned int(Wsp::Health::Token *__hidden this, unsigned int, int, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18006f18c`
- `0x18006fe74`

## callees

- `0x18006f70c`
- `0x180070a94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070ac9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070ac9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180070abf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180070abf`

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
0x180070a94  mov     [rsp+arg_0], rbx
0x180070a99  mov     [rsp+arg_8], rsi
0x180070a9e  push    rdi
0x180070a9f  sub     rsp, 20h
0x180070aa3  mov     rsi, r9
0x180070aa6  mov     edi, edx
0x180070aa8  mov     rbx, rcx
0x180070aab  call    ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
0x180070ab0  lea     r9, [rbx+8]; TokenHandle
0x180070ab4  mov     r8d, 1; OpenAsSelf
0x180070aba  mov     edx, edi; DesiredAccess
0x180070abc  mov     rcx, rsi; ThreadHandle
0x180070abf  call    cs:__imp_OpenThreadToken
0x180070ac5  test    eax, eax
0x180070ac7  jnz     short loc_180070AD1
0x180070ac9  call    cs:__imp_GetLastError
0x180070acf  jmp     short loc_180070AD3
0x180070ad1  xor     eax, eax
0x180070ad3  mov     rbx, [rsp+28h+arg_0]
0x180070ad8  mov     rsi, [rsp+28h+arg_8]
0x180070add  add     rsp, 20h
0x180070ae1  pop     rdi
0x180070ae2  retn
```
