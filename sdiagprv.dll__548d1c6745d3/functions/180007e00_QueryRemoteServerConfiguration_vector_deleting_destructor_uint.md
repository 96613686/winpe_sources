# QueryRemoteServerConfiguration::`vector deleting destructor'(uint)

- ea: `0x180007e00`
- end: `0x180007e26`
- name: `??_EQueryRemoteServerConfiguration@@UEAAPEAXI@Z`
- size: `38`
- prototype: `QueryRemoteServerConfiguration *__fastcall(QueryRemoteServerConfiguration *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x1800010b4`
- `0x180007e00`

## pseudocode

```c
QueryRemoteServerConfiguration *__fastcall QueryRemoteServerConfiguration::`vector deleting destructor'(
        QueryRemoteServerConfiguration *this,
        char a2)
{
  *(_QWORD *)this = &QueryRemoteServerConfiguration::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180007e00  push    rbx
0x180007e02  sub     rsp, 20h
0x180007e06  lea     rax, ??_7QueryRemoteServerConfiguration@@6B@; const QueryRemoteServerConfiguration::`vftable'
0x180007e0d  mov     rbx, rcx
0x180007e10  mov     [rcx], rax
0x180007e13  test    dl, 1
0x180007e16  jz      short loc_180007E1D
0x180007e18  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007e1d  mov     rax, rbx
0x180007e20  add     rsp, 20h
0x180007e24  pop     rbx
0x180007e25  retn
```
