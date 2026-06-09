# CIndexCache::Empty(void)

- ea: `0x18000a5ec`
- end: `0x18000a649`
- name: `?Empty@CIndexCache@@QEAAXXZ`
- size: `93`
- prototype: `void __fastcall(CIndexCache *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b9ac`
- `0x1800108c0`
- `0x180010ae0`

## callees

- `0x18000a5ec`
- `0x180017010`

## import_xrefs

- `wbemcomn!?Empty@CFlexArray@@QEAAXXZ` at `0x18000a633`
- `wbemcomn!?Empty@CFlexArray@@QEAAXXZ` at `0x18000a633`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18000a60c`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18000a60c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CIndexCache::Empty(CIndexCache *this)
{
  CFlexArray *v1; // rdi
  int v2; // ebx
  int v3; // esi
  void (__fastcall ***v4)(void *, __int64); // rax

  v1 = (CIndexCache *)((char *)this + 8);
  v2 = 0;
  v3 = *((_DWORD *)this + 2);
  if ( v3 > 0 )
  {
    do
    {
      v4 = (void (__fastcall ***)(void *, __int64))CFlexArray::GetAt(v1, v2);
      if ( v4 )
        (**v4)(v4, 1);
      ++v2;
    }
    while ( v2 < v3 );
    CFlexArray::Empty(v1);
  }
}

```

## disassembly

```asm
0x18000a5ec  mov     [rsp+arg_0], rbx
0x18000a5f1  mov     [rsp+arg_8], rsi
0x18000a5f6  push    rdi
0x18000a5f7  sub     rsp, 20h
0x18000a5fb  lea     rdi, [rcx+8]
0x18000a5ff  xor     ebx, ebx
0x18000a601  mov     esi, [rdi]
0x18000a603  test    esi, esi
0x18000a605  jle     short loc_18000A639
0x18000a607  mov     edx, ebx
0x18000a609  mov     rcx, rdi
0x18000a60c  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18000a612  mov     rcx, rax
0x18000a615  test    rax, rax
0x18000a618  jz      short loc_18000A62A
0x18000a61a  mov     rdx, [rax]
0x18000a61d  mov     rax, [rdx]
0x18000a620  mov     edx, 1
0x18000a625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a62a  inc     ebx
0x18000a62c  cmp     ebx, esi
0x18000a62e  jl      short loc_18000A607
0x18000a630  mov     rcx, rdi
0x18000a633  call    cs:__imp_?Empty@CFlexArray@@QEAAXXZ; CFlexArray::Empty(void)
0x18000a639  mov     rbx, [rsp+28h+arg_0]
0x18000a63e  mov     rsi, [rsp+28h+arg_8]
0x18000a643  add     rsp, 20h
0x18000a647  pop     rdi
0x18000a648  retn
```
