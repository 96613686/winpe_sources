# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x180009b04`
- end: `0x180009b40`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `60`
- prototype: `void __fastcall(wil::details::shared_buffer *__hidden this, int *, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007410`
- `0x18000747c`
- `0x180009238`
- `0x180009c50`

## callees

- `0x180009b04`
- `0x180009bf4`

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
0x180009b04  mov     [rsp+arg_0], rbx
0x180009b09  mov     [rsp+arg_8], rsi
0x180009b0e  push    rdi
0x180009b0f  sub     rsp, 20h
0x180009b13  mov     rsi, r8
0x180009b16  mov     rbx, rdx
0x180009b19  mov     rdi, rcx
0x180009b1c  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x180009b21  test    rbx, rbx
0x180009b24  jz      short loc_180009B30
0x180009b26  mov     [rdi], rbx
0x180009b29  mov     [rdi+8], rsi
0x180009b2d  lock inc dword ptr [rbx]
0x180009b30  mov     rbx, [rsp+28h+arg_0]
0x180009b35  mov     rsi, [rsp+28h+arg_8]
0x180009b3a  add     rsp, 20h
0x180009b3e  pop     rdi
0x180009b3f  retn
```
