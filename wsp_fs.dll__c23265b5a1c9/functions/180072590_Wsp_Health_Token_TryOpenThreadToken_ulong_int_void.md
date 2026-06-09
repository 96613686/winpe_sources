# Wsp::Health::Token::TryOpenThreadToken(ulong,int,void *)

- ea: `0x180072590`
- end: `0x1800725ec`
- name: `?TryOpenThreadToken@Token@Health@Wsp@@QEAAKKHPEAX@Z`
- size: `92`
- prototype: `unsigned int(Wsp::Health::Token *__hidden this, unsigned int, int, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180070a6c`
- `0x180071830`

## callees

- `0x18007105c`
- `0x180072590`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800725cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800725cb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800725bb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800725bb`

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
0x180072590  mov     [rsp+arg_0], rbx
0x180072595  mov     [rsp+arg_8], rsi
0x18007259a  push    rdi
0x18007259b  sub     rsp, 20h
0x18007259f  mov     rsi, r9
0x1800725a2  mov     edi, edx
0x1800725a4  mov     rbx, rcx
0x1800725a7  call    ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
0x1800725ac  lea     r9, [rbx+8]; TokenHandle
0x1800725b0  mov     r8d, 1; OpenAsSelf
0x1800725b6  mov     edx, edi; DesiredAccess
0x1800725b8  mov     rcx, rsi; ThreadHandle
0x1800725bb  call    cs:__imp_OpenThreadToken
0x1800725c2  nop     dword ptr [rax+rax+00h]
0x1800725c7  test    eax, eax
0x1800725c9  jnz     short loc_1800725D9
0x1800725cb  call    cs:__imp_GetLastError
0x1800725d2  nop     dword ptr [rax+rax+00h]
0x1800725d7  jmp     short loc_1800725DB
0x1800725d9  xor     eax, eax
0x1800725db  mov     rbx, [rsp+28h+arg_0]
0x1800725e0  mov     rsi, [rsp+28h+arg_8]
0x1800725e5  add     rsp, 20h
0x1800725e9  pop     rdi
0x1800725ea  retn
```
