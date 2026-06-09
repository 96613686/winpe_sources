# CRegistryEventRequest::IsSameAs(CRegistryEventRequest *)

- ea: `0x180006f50`
- end: `0x180006fcf`
- name: `?IsSameAs@CRegistryEventRequest@@UEAAHPEAV1@@Z`
- size: `127`
- prototype: `_BOOL8 __fastcall(const unsigned __int16 **this, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800140a0`

## callees

- `0x180006f50`
- `0x180006fe0`
- `0x180017010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_BOOL8 __fastcall CRegistryEventRequest::IsSameAs(const unsigned __int16 **this, const unsigned __int16 **a2)
{
  unsigned int (__fastcall *v4)(struct CRegistryEventRequest *); // rdi
  int v5; // ebx

  v4 = (unsigned int (__fastcall *)(struct CRegistryEventRequest *))*((_QWORD *)*a2 + 3);
  v5 = (*((__int64 (__fastcall **)(const unsigned __int16 **))*this + 3))(this);
  return v5 == v4((struct CRegistryEventRequest *)a2)
      && this[15] == a2[15]
      && !(unsigned int)wbem_wcsicmp(this[16], a2[16])
      && !(unsigned int)wbem_wcsicmp(this[17], a2[17]);
}

```

## disassembly

```asm
0x180006f50  push    rbx
0x180006f52  push    rsi
0x180006f53  push    rdi
0x180006f54  push    r14
0x180006f56  sub     rsp, 28h
0x180006f5a  mov     rax, [rdx]
0x180006f5d  mov     rsi, rdx
0x180006f60  mov     r14, rcx
0x180006f63  mov     rdi, [rax+18h]
0x180006f67  mov     rax, [rcx]
0x180006f6a  mov     rax, [rax+18h]
0x180006f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f73  mov     ebx, eax
0x180006f75  mov     rcx, rsi
0x180006f78  mov     rax, rdi
0x180006f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f80  cmp     ebx, eax
0x180006f82  jnz     short loc_180006FC3
0x180006f84  mov     rax, [rsi+78h]
0x180006f88  cmp     [r14+78h], rax
0x180006f8c  jnz     short loc_180006FC3
0x180006f8e  mov     rdx, [rsi+80h]; unsigned __int16 *
0x180006f95  mov     rcx, [r14+80h]; unsigned __int16 *
0x180006f9c  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180006fa1  test    eax, eax
0x180006fa3  jnz     short loc_180006FC3
0x180006fa5  mov     rdx, [rsi+88h]; unsigned __int16 *
0x180006fac  mov     rcx, [r14+88h]; unsigned __int16 *
0x180006fb3  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180006fb8  test    eax, eax
0x180006fba  jnz     short loc_180006FC3
0x180006fbc  mov     eax, 1
0x180006fc1  jmp     short loc_180006FC5
0x180006fc3  xor     eax, eax
0x180006fc5  add     rsp, 28h
0x180006fc9  pop     r14
0x180006fcb  pop     rdi
0x180006fcc  pop     rsi
0x180006fcd  pop     rbx
0x180006fce  retn
```
