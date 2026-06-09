# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x180006ddc`
- end: `0x180006e18`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `60`
- prototype: `void __fastcall(wil::details::shared_buffer *__hidden this, int *, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003d14`
- `0x180003d80`
- `0x180005fdc`
- `0x180006f60`

## callees

- `0x180006ddc`
- `0x180006f00`

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
0x180006ddc  mov     [rsp+arg_0], rbx
0x180006de1  mov     [rsp+arg_8], rsi
0x180006de6  push    rdi
0x180006de7  sub     rsp, 20h
0x180006deb  mov     rsi, r8
0x180006dee  mov     rbx, rdx
0x180006df1  mov     rdi, rcx
0x180006df4  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x180006df9  test    rbx, rbx
0x180006dfc  jz      short loc_180006E08
0x180006dfe  mov     [rdi], rbx
0x180006e01  mov     [rdi+8], rsi
0x180006e05  lock inc dword ptr [rbx]
0x180006e08  mov     rbx, [rsp+28h+arg_0]
0x180006e0d  mov     rsi, [rsp+28h+arg_8]
0x180006e12  add     rsp, 20h
0x180006e16  pop     rdi
0x180006e17  retn
```
