# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x180005a30`
- end: `0x180005a6c`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `60`
- prototype: `void __fastcall(wil::details::shared_buffer *this, int *, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800031f8`
- `0x180003264`
- `0x180005178`
- `0x180005b80`

## callees

- `0x180005a30`
- `0x180005b20`

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
0x180005a30  mov     [rsp+arg_0], rbx
0x180005a35  mov     [rsp+arg_8], rsi
0x180005a3a  push    rdi
0x180005a3b  sub     rsp, 20h
0x180005a3f  mov     rsi, r8
0x180005a42  mov     rbx, rdx
0x180005a45  mov     rdi, rcx
0x180005a48  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x180005a4d  test    rbx, rbx
0x180005a50  jz      short loc_180005A5C
0x180005a52  mov     [rdi], rbx
0x180005a55  mov     [rdi+8], rsi
0x180005a59  lock inc dword ptr [rbx]
0x180005a5c  mov     rbx, [rsp+28h+arg_0]
0x180005a61  mov     rsi, [rsp+28h+arg_8]
0x180005a66  add     rsp, 20h
0x180005a6a  pop     rdi
0x180005a6b  retn
```
