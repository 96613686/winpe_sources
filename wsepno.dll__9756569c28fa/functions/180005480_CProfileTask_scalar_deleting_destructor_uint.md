# CProfileTask::`scalar deleting destructor'(uint)

- ea: `0x180005480`
- end: `0x1800054ab`
- name: `??_GCProfileTask@@UEAAPEAXI@Z`
- size: `43`
- prototype: `void *__fastcall(CProfileTask *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task`

## callees

- `0x180001794`
- `0x180005480`

## pseudocode

```c
CProfileTask *__fastcall CProfileTask::`scalar deleting destructor'(CProfileTask *this, char a2)
{
  *(_QWORD *)this = &CProfileTask::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180005480  push    rbx
0x180005482  sub     rsp, 20h
0x180005486  lea     rax, ??_7CProfileTask@@6B@; const CProfileTask::`vftable'
0x18000548d  mov     rbx, rcx
0x180005490  mov     [rcx], rax
0x180005493  test    dl, 1
0x180005496  jz      short loc_1800054A2
0x180005498  mov     edx, 8
0x18000549d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800054a2  mov     rax, rbx
0x1800054a5  add     rsp, 20h
0x1800054a9  pop     rbx
0x1800054aa  retn
```
