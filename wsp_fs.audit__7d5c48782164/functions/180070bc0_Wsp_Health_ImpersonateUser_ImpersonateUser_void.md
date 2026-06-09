# Wsp::Health::ImpersonateUser::~ImpersonateUser(void)

- ea: `0x180070bc0`
- end: `0x180070bf2`
- name: `??1ImpersonateUser@Health@Wsp@@QEAA@XZ`
- size: `50`
- prototype: `void __fastcall(Wsp::Health::ImpersonateUser *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180070a6c`

## callees

- `0x18007105c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180070bcf`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180070bcf`

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
0x180070bc0  push    rbx
0x180070bc2  sub     rsp, 20h
0x180070bc6  mov     rdx, [rcx+8]; Token
0x180070bca  mov     rbx, rcx
0x180070bcd  xor     ecx, ecx; Thread
0x180070bcf  call    cs:__imp_SetThreadToken
0x180070bd6  nop     dword ptr [rax+rax+00h]
0x180070bdb  lea     rax, ??_7Token@Health@Wsp@@6B@; const Wsp::Health::Token::`vftable'
0x180070be2  mov     rcx, rbx; this
0x180070be5  mov     [rbx], rax
0x180070be8  add     rsp, 20h
0x180070bec  pop     rbx
0x180070bed  jmp     ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
```
