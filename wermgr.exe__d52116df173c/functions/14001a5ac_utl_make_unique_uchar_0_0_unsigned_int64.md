# utl::make_unique<uchar [0],0>(unsigned __int64)

- ea: `0x14001a5ac`
- end: `0x14001a5ff`
- name: `??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z`
- size: `83`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001a608`

## callees

- `0x140002fbc`
- `0x140003254`
- `0x14001a5ac`

## pseudocode

```c
_QWORD *__fastcall utl::make_unique<unsigned char [0],0>(_QWORD *a1, unsigned __int64 a2)
{
  void *v4; // rax
  void *v5; // rbx
  _QWORD *result; // rax

  v4 = operator new[](a2, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( v4 )
    memset_0(v4, 0, a2);
  else
    v5 = 0;
  result = a1;
  *a1 = v5;
  return result;
}

```

## disassembly

```asm
0x14001a5ac  mov     [rsp+arg_0], rbx
0x14001a5b1  mov     [rsp+arg_8], rsi
0x14001a5b6  push    rdi
0x14001a5b7  sub     rsp, 20h
0x14001a5bb  mov     rsi, rdx
0x14001a5be  mov     rdi, rcx
0x14001a5c1  mov     rcx, rsi; unsigned __int64
0x14001a5c4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001a5cb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14001a5d0  mov     rbx, rax
0x14001a5d3  test    rax, rax
0x14001a5d6  jz      short loc_14001A5E7
0x14001a5d8  mov     r8, rsi; Size
0x14001a5db  xor     edx, edx; Val
0x14001a5dd  mov     rcx, rax; void *
0x14001a5e0  call    memset_0
0x14001a5e5  jmp     short loc_14001A5E9
0x14001a5e7  xor     ebx, ebx
0x14001a5e9  mov     rsi, [rsp+28h+arg_8]
0x14001a5ee  mov     rax, rdi
0x14001a5f1  mov     [rdi], rbx
0x14001a5f4  mov     rbx, [rsp+28h+arg_0]
0x14001a5f9  add     rsp, 20h
0x14001a5fd  pop     rdi
0x14001a5fe  retn
```
