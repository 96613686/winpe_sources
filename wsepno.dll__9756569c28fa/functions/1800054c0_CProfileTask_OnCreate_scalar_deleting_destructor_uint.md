# CProfileTask_OnCreate::`scalar deleting destructor'(uint)

- ea: `0x1800054c0`
- end: `0x180005508`
- name: `??_GCProfileTask_OnCreate@@UEAAPEAXI@Z`
- size: `72`
- prototype: `void *__fastcall(CProfileTask_OnCreate *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task`

## callees

- `0x180001794`
- `0x1800054c0`

## pseudocode

```c
CProfileTask_OnCreate *__fastcall CProfileTask_OnCreate::`scalar deleting destructor'(
        CProfileTask_OnCreate *this,
        char a2)
{
  void *v4; // rcx

  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
    operator delete(v4);
  *(_QWORD *)this = &CProfileTask::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800054c0  mov     [rsp+arg_0], rbx
0x1800054c5  push    rdi
0x1800054c6  sub     rsp, 20h
0x1800054ca  mov     rbx, rcx
0x1800054cd  mov     edi, edx
0x1800054cf  mov     rcx, [rcx+8]; Block
0x1800054d3  test    rcx, rcx
0x1800054d6  jz      short loc_1800054DD
0x1800054d8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800054dd  lea     rax, ??_7CProfileTask@@6B@; const CProfileTask::`vftable'
0x1800054e4  mov     [rbx], rax
0x1800054e7  test    dil, 1
0x1800054eb  jz      short loc_1800054FA
0x1800054ed  mov     edx, 10h
0x1800054f2  mov     rcx, rbx; Block
0x1800054f5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800054fa  mov     rax, rbx
0x1800054fd  mov     rbx, [rsp+28h+arg_0]
0x180005502  add     rsp, 20h
0x180005506  pop     rdi
0x180005507  retn
```
