# Wsp::Health::ImpersonateUser::~ImpersonateUser(void)

- ea: `0x18006f2c4`
- end: `0x18006f2f0`
- name: `??1ImpersonateUser@Health@Wsp@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(Wsp::Health::ImpersonateUser *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18006f18c`

## callees

- `0x18006f70c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18006f2d3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18006f2d3`

## pseudocode

```c
void __fastcall Wsp::Health::ImpersonateUser::~ImpersonateUser(HANDLE *this)
{
  SetThreadToken(0, this[1]);
  *this = &Wsp::Health::Token::`vftable';
  Wsp::Health::Token::Clear((Wsp::Health::Token *)this);
}

```

## disassembly

```asm
0x18006f2c4  push    rbx
0x18006f2c6  sub     rsp, 20h
0x18006f2ca  mov     rdx, [rcx+8]; Token
0x18006f2ce  mov     rbx, rcx
0x18006f2d1  xor     ecx, ecx; Thread
0x18006f2d3  call    cs:__imp_SetThreadToken
0x18006f2d9  lea     rax, ??_7Token@Health@Wsp@@6B@; const Wsp::Health::Token::`vftable'
0x18006f2e0  mov     rcx, rbx; this
0x18006f2e3  mov     [rbx], rax
0x18006f2e6  add     rsp, 20h
0x18006f2ea  pop     rbx
0x18006f2eb  jmp     ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
```
