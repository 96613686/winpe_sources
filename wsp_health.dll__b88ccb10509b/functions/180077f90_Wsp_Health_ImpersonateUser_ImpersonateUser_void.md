# Wsp::Health::ImpersonateUser::~ImpersonateUser(void)

- ea: `0x180077f90`
- end: `0x180077fbc`
- name: `??1ImpersonateUser@Health@Wsp@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(Wsp::Health::ImpersonateUser *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180077e7c`

## callees

- `0x18007872c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180077f9f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180077f9f`

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
0x180077f90  push    rbx
0x180077f92  sub     rsp, 20h
0x180077f96  mov     rdx, [rcx+8]; Token
0x180077f9a  mov     rbx, rcx
0x180077f9d  xor     ecx, ecx; Thread
0x180077f9f  call    cs:__imp_SetThreadToken
0x180077fa5  lea     rax, ??_7Token@Health@Wsp@@6B@; const Wsp::Health::Token::`vftable'
0x180077fac  mov     rcx, rbx; this
0x180077faf  mov     [rbx], rax
0x180077fb2  add     rsp, 20h
0x180077fb6  pop     rbx
0x180077fb7  jmp     ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
```
