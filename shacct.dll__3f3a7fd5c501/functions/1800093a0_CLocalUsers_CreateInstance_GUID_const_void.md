# CLocalUsers_CreateInstance(_GUID const &,void * *)

- ea: `0x1800093a0`
- end: `0x180009426`
- name: `?CLocalUsers_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `134`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180009900`

## callees

- `0x1800093a0`
- `0x18000d740`
- `0x18000f080`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall CLocalUsers_CreateInstance(const struct _GUID *a1, void **a2)
{
  CLocalAccounts *v4; // rax
  CLocalAccounts *v5; // rbx
  unsigned int v6; // edi

  *a2 = 0;
  v4 = (CLocalAccounts *)operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( !v4 )
    return 2147942414LL;
  CLocalAccounts::CLocalAccounts(v4);
  *(_QWORD *)v5 = &CLocalUsers::`vftable';
  v6 = ((__int64 (__fastcall *)(CLocalAccounts *, const struct _GUID *, void **))CLocalUsers::`vftable')(v5, a1, a2);
  (*(void (__fastcall **)(CLocalAccounts *))(*(_QWORD *)v5 + 16LL))(v5);
  return v6;
}

```

## disassembly

```asm
0x1800093a0  mov     [rsp+arg_0], rbx
0x1800093a5  mov     [rsp+arg_8], rsi
0x1800093aa  push    rdi
0x1800093ab  sub     rsp, 20h
0x1800093af  mov     rdi, rdx
0x1800093b2  mov     qword ptr [rdx], 0
0x1800093b9  mov     rsi, rcx
0x1800093bc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800093c3  mov     ecx, 70h ; 'p'; unsigned __int64
0x1800093c8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800093cd  mov     rbx, rax
0x1800093d0  test    rax, rax
0x1800093d3  jz      short loc_180009411
0x1800093d5  mov     rcx, rax; this
0x1800093d8  call    ??0CLocalAccounts@@QEAA@XZ; CLocalAccounts::CLocalAccounts(void)
0x1800093dd  lea     rax, ??_7CLocalUsers@@6B@; const CLocalUsers::`vftable'
0x1800093e4  mov     r8, rdi
0x1800093e7  mov     [rbx], rax
0x1800093ea  mov     rdx, rsi
0x1800093ed  mov     rax, cs:??_7CLocalUsers@@6B@; const CLocalUsers::`vftable'
0x1800093f4  mov     rcx, rbx
0x1800093f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093fc  mov     rcx, [rbx]
0x1800093ff  mov     edi, eax
0x180009401  mov     rax, [rcx+10h]
0x180009405  mov     rcx, rbx
0x180009408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000940d  mov     eax, edi
0x18000940f  jmp     short loc_180009416
0x180009411  mov     eax, 8007000Eh
0x180009416  mov     rbx, [rsp+28h+arg_0]
0x18000941b  mov     rsi, [rsp+28h+arg_8]
0x180009420  add     rsp, 20h
0x180009424  pop     rdi
0x180009425  retn
```
