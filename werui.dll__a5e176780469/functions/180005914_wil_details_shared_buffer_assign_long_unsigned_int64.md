# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x180005914`
- end: `0x180005950`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `60`
- prototype: `void __fastcall(wil::details::shared_buffer *__hidden this, int *, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180004acc`
- `0x180004b38`
- `0x1800054bc`
- `0x1800059b0`

## callees

- `0x180005914`
- `0x180005958`

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
0x180005914  mov     [rsp+arg_0], rbx
0x180005919  mov     [rsp+arg_8], rsi
0x18000591e  push    rdi
0x18000591f  sub     rsp, 20h
0x180005923  mov     rsi, r8
0x180005926  mov     rbx, rdx
0x180005929  mov     rdi, rcx
0x18000592c  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x180005931  test    rbx, rbx
0x180005934  jz      short loc_180005940
0x180005936  mov     [rdi], rbx
0x180005939  mov     [rdi+8], rsi
0x18000593d  lock inc dword ptr [rbx]
0x180005940  mov     rbx, [rsp+28h+arg_0]
0x180005945  mov     rsi, [rsp+28h+arg_8]
0x18000594a  add     rsp, 20h
0x18000594e  pop     rdi
0x18000594f  retn
```
