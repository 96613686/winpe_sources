# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x180009ce0`
- end: `0x180009d1d`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `61`
- prototype: `void __fastcall(wil::details::shared_buffer *__hidden this, int *, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007434`
- `0x1800074a0`
- `0x1800093b8`
- `0x180009e50`

## callees

- `0x180009ce0`
- `0x180009de0`

## pseudocode

```c
void __fastcall wil::details::shared_buffer::assign(wil::details::shared_buffer *this, int *a2, __int64 a3)
{
  wil::details::shared_buffer::reset(this);
  if ( a2 )
  {
    *(_QWORD *)this = a2;
    *((_QWORD *)this + 1) = a3;
    _InterlockedIncrement(a2);
  }
}

```

## disassembly

```asm
0x180009ce0  mov     [rsp+arg_0], rbx
0x180009ce5  mov     [rsp+arg_8], rsi
0x180009cea  push    rdi
0x180009ceb  sub     rsp, 20h
0x180009cef  mov     rsi, r8
0x180009cf2  mov     rbx, rdx
0x180009cf5  mov     rdi, rcx
0x180009cf8  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x180009cfd  test    rbx, rbx
0x180009d00  jz      short loc_180009D0C
0x180009d02  mov     [rdi], rbx
0x180009d05  mov     [rdi+8], rsi
0x180009d09  lock inc dword ptr [rbx]
0x180009d0c  mov     rbx, [rsp+28h+arg_0]
0x180009d11  mov     rsi, [rsp+28h+arg_8]
0x180009d16  add     rsp, 20h
0x180009d1a  pop     rdi
0x180009d1b  retn
```
