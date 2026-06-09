# ComTaskMgrWnd::~ComTaskMgrWnd(void)

- ea: `0x140004268`
- end: `0x140004294`
- name: `??1ComTaskMgrWnd@@UEAA@XZ`
- size: `44`
- prototype: `void __fastcall(ComTaskMgrWnd *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x140004230`

## callees

- `0x1400042a0`

## pseudocode

```c
void __fastcall ComTaskMgrWnd::~ComTaskMgrWnd(ComTaskMgrWnd *this)
{
  *(_QWORD *)this = &ComTaskMgrWnd::`vftable';
  ComTaskMgrWnd::CleanupSet::~CleanupSet((ComTaskMgrWnd *)((char *)this + 72));
  *(_QWORD *)this = &ComTaskMgrBase::`vftable';
}

```

## disassembly

```asm
0x140004268  push    rbx
0x14000426a  sub     rsp, 20h
0x14000426e  lea     rax, ??_7ComTaskMgrWnd@@6B@; const ComTaskMgrWnd::`vftable'
0x140004275  mov     rbx, rcx
0x140004278  mov     [rcx], rax
0x14000427b  add     rcx, 48h ; 'H'; this
0x14000427f  call    ??1CleanupSet@ComTaskMgrWnd@@QEAA@XZ; ComTaskMgrWnd::CleanupSet::~CleanupSet(void)
0x140004284  lea     rax, ??_7ComTaskMgrBase@@6B@; const ComTaskMgrBase::`vftable'
0x14000428b  mov     [rbx], rax
0x14000428e  add     rsp, 20h
0x140004292  pop     rbx
0x140004293  retn
```
