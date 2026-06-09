# _com_error::_com_error(_com_error const &)

- ea: `0x14000a130`
- end: `0x14000a173`
- name: `??0_com_error@@QEAA@AEBV0@@Z`
- size: `67`
- prototype: `_com_error *__fastcall(_com_error *__hidden this, const struct _com_error *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000a130`
- `0x14000c010`

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
0x14000a130  push    rbx
0x14000a132  sub     rsp, 20h
0x14000a136  mov     rbx, rcx
0x14000a139  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x14000a140  mov     [rcx], rax
0x14000a143  mov     eax, [rdx+8]
0x14000a146  mov     [rcx+8], eax
0x14000a149  mov     rcx, [rdx+10h]
0x14000a14d  mov     [rbx+10h], rcx
0x14000a151  mov     qword ptr [rbx+18h], 0
0x14000a159  test    rcx, rcx
0x14000a15c  jz      short loc_14000A16A
0x14000a15e  mov     rax, [rcx]
0x14000a161  mov     rax, [rax+8]
0x14000a165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a16a  mov     rax, rbx
0x14000a16d  add     rsp, 20h
0x14000a171  pop     rbx
0x14000a172  retn
```
