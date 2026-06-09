# _com_error::_com_error(_com_error const &)

- ea: `0x180015f04`
- end: `0x180015f47`
- name: `??0_com_error@@QEAA@AEBV0@@Z`
- size: `67`
- prototype: `_com_error *__fastcall(_com_error *__hidden this, const struct _com_error *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180015f04`
- `0x180020010`

## pseudocode

```c
_com_error *__fastcall _com_error::_com_error(_com_error *this, const struct _com_error *a2)
{
  __int64 v3; // rcx

  *(_QWORD *)this = &_com_error::`vftable';
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  v3 = *((_QWORD *)a2 + 2);
  *((_QWORD *)this + 2) = v3;
  *((_QWORD *)this + 3) = 0;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  return this;
}

```

## disassembly

```asm
0x180015f04  push    rbx
0x180015f06  sub     rsp, 20h
0x180015f0a  mov     rbx, rcx
0x180015f0d  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180015f14  mov     [rcx], rax
0x180015f17  mov     eax, [rdx+8]
0x180015f1a  mov     [rcx+8], eax
0x180015f1d  mov     rcx, [rdx+10h]
0x180015f21  mov     [rbx+10h], rcx
0x180015f25  mov     qword ptr [rbx+18h], 0
0x180015f2d  test    rcx, rcx
0x180015f30  jz      short loc_180015F3E
0x180015f32  mov     rax, [rcx]
0x180015f35  mov     rax, [rax+8]
0x180015f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f3e  mov     rax, rbx
0x180015f41  add     rsp, 20h
0x180015f45  pop     rbx
0x180015f46  retn
```
