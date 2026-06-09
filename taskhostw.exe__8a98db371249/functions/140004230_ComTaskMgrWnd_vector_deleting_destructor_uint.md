# ComTaskMgrWnd::`vector deleting destructor'(uint)

- ea: `0x140004230`
- end: `0x140004260`
- name: `??_EComTaskMgrWnd@@UEAAPEAXI@Z`
- size: `48`
- prototype: `ComTaskMgrWnd *__fastcall(ComTaskMgrWnd *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x140004230`
- `0x140004268`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000424c`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000424c`

## pseudocode

```c
ComTaskMgrWnd *__fastcall ComTaskMgrWnd::`vector deleting destructor'(ComTaskMgrWnd *this, char a2)
{
  ComTaskMgrWnd::~ComTaskMgrWnd(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140004230  mov     [rsp+arg_0], rbx
0x140004235  push    rdi
0x140004236  sub     rsp, 20h
0x14000423a  mov     ebx, edx
0x14000423c  mov     rdi, rcx
0x14000423f  call    ??1ComTaskMgrWnd@@UEAA@XZ; ComTaskMgrWnd::~ComTaskMgrWnd(void)
0x140004244  test    bl, 1
0x140004247  jz      short loc_140004252
0x140004249  mov     rcx, rdi
0x14000424c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140004252  mov     rbx, [rsp+28h+arg_0]
0x140004257  mov     rax, rdi
0x14000425a  add     rsp, 20h
0x14000425e  pop     rdi
0x14000425f  retn
```
