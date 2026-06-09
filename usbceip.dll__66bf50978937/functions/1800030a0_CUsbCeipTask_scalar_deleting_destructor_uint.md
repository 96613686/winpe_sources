# CUsbCeipTask::`scalar deleting destructor'(uint)

- ea: `0x1800030a0`
- end: `0x1800030de`
- name: `??_GCUsbCeipTask@@UEAAPEAXI@Z`
- size: `62`
- prototype: `CUsbCeipTask *__fastcall(CUsbCeipTask *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180002434`
- `0x180002fec`
- `0x1800030a0`

## pseudocode

```c
CUsbCeipTask *__fastcall CUsbCeipTask::`scalar deleting destructor'(CUsbCeipTask *this, char a2)
{
  *(_QWORD *)this = &CUsbCeipTask::`vftable';
  CWinTaskHandler::~CWinTaskHandler(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800030a0  mov     [rsp+arg_0], rbx
0x1800030a5  push    rdi
0x1800030a6  sub     rsp, 20h
0x1800030aa  lea     rax, ??_7CUsbCeipTask@@6B@; const CUsbCeipTask::`vftable'
0x1800030b1  mov     ebx, edx
0x1800030b3  mov     [rcx], rax
0x1800030b6  mov     rdi, rcx
0x1800030b9  call    ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
0x1800030be  test    bl, 1
0x1800030c1  jz      short loc_1800030D0
0x1800030c3  mov     edx, 38h ; '8'
0x1800030c8  mov     rcx, rdi; Block
0x1800030cb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800030d0  mov     rbx, [rsp+28h+arg_0]
0x1800030d5  mov     rax, rdi
0x1800030d8  add     rsp, 20h
0x1800030dc  pop     rdi
0x1800030dd  retn
```
