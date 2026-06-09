# Wsp::Health::ImpersonateUser::~ImpersonateUser(void)

- ea: `0x180079e90`
- end: `0x180079ec2`
- name: `??1ImpersonateUser@Health@Wsp@@QEAA@XZ`
- size: `50`
- prototype: `void __fastcall(Wsp::Health::ImpersonateUser *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180079d68`

## callees

- `0x18007a67c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180079e9f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180079e9f`

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
0x180079e90  push    rbx
0x180079e92  sub     rsp, 20h
0x180079e96  mov     rdx, [rcx+8]; Token
0x180079e9a  mov     rbx, rcx
0x180079e9d  xor     ecx, ecx; Thread
0x180079e9f  call    cs:__imp_SetThreadToken
0x180079ea6  nop     dword ptr [rax+rax+00h]
0x180079eab  lea     rax, ??_7Token@Health@Wsp@@6B@; const Wsp::Health::Token::`vftable'
0x180079eb2  mov     rcx, rbx; this
0x180079eb5  mov     [rbx], rax
0x180079eb8  add     rsp, 20h
0x180079ebc  pop     rbx
0x180079ebd  jmp     ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
```
