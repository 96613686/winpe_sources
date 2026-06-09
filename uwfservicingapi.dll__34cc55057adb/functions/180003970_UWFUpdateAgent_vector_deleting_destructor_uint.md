# UWFUpdateAgent::`vector deleting destructor'(uint)

- ea: `0x180003970`
- end: `0x180003996`
- name: `??_EUWFUpdateAgent@@UEAAPEAXI@Z`
- size: `38`
- prototype: `UWFUpdateAgent *__fastcall(UWFUpdateAgent *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, installer_update`

## callees

- `0x180001536`
- `0x180003970`

## pseudocode

```c
UWFUpdateAgent *__fastcall UWFUpdateAgent::`vector deleting destructor'(UWFUpdateAgent *this, char a2)
{
  *(_QWORD *)this = &UWFUpdateAgent::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003970  push    rbx
0x180003972  sub     rsp, 20h
0x180003976  lea     rax, ??_7UWFUpdateAgent@@6B@; const UWFUpdateAgent::`vftable'
0x18000397d  mov     rbx, rcx
0x180003980  mov     [rcx], rax
0x180003983  test    dl, 1
0x180003986  jz      short loc_18000398D
0x180003988  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x18000398d  mov     rax, rbx
0x180003990  add     rsp, 20h
0x180003994  pop     rbx
0x180003995  retn
```
