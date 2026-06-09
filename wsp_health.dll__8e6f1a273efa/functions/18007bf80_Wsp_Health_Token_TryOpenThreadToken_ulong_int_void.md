# Wsp::Health::Token::TryOpenThreadToken(ulong,int,void *)

- ea: `0x18007bf80`
- end: `0x18007bfdc`
- name: `?TryOpenThreadToken@Token@Health@Wsp@@QEAAKKHPEAX@Z`
- size: `92`
- prototype: `unsigned int(Wsp::Health::Token *__hidden this, unsigned int, int, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180079d68`
- `0x18007b1a8`

## callees

- `0x18007a67c`
- `0x18007bf80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007bfbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007bfbb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007bfab`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007bfab`

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
0x18007bf80  mov     [rsp+arg_0], rbx
0x18007bf85  mov     [rsp+arg_8], rsi
0x18007bf8a  push    rdi
0x18007bf8b  sub     rsp, 20h
0x18007bf8f  mov     rsi, r9
0x18007bf92  mov     edi, edx
0x18007bf94  mov     rbx, rcx
0x18007bf97  call    ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
0x18007bf9c  lea     r9, [rbx+8]; TokenHandle
0x18007bfa0  mov     r8d, 1; OpenAsSelf
0x18007bfa6  mov     edx, edi; DesiredAccess
0x18007bfa8  mov     rcx, rsi; ThreadHandle
0x18007bfab  call    cs:__imp_OpenThreadToken
0x18007bfb2  nop     dword ptr [rax+rax+00h]
0x18007bfb7  test    eax, eax
0x18007bfb9  jnz     short loc_18007BFC9
0x18007bfbb  call    cs:__imp_GetLastError
0x18007bfc2  nop     dword ptr [rax+rax+00h]
0x18007bfc7  jmp     short loc_18007BFCB
0x18007bfc9  xor     eax, eax
0x18007bfcb  mov     rbx, [rsp+28h+arg_0]
0x18007bfd0  mov     rsi, [rsp+28h+arg_8]
0x18007bfd5  add     rsp, 20h
0x18007bfd9  pop     rdi
0x18007bfda  retn
```
