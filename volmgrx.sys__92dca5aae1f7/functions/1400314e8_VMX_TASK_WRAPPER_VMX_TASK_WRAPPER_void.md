# VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER(void)

- ea: `0x1400314e8`
- end: `0x140031524`
- name: `??1VMX_TASK_WRAPPER@@QEAA@XZ`
- size: `60`
- prototype: `void __fastcall(VMX_TASK_WRAPPER *__hidden this)`
- caller_count: `34`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002b964`
- `0x14002fec0`
- `0x140030110`
- `0x1400302dc`
- `0x140030680`
- `0x140030a04`
- `0x140031180`
- `0x140031390`
- `0x140031530`
- `0x140035180`
- `0x140035544`
- `0x140035e3c`
- `0x1400362a8`
- `0x14003677c`
- `0x140036bac`
- `0x140036e70`
- `0x140037fe4`
- `0x140038468`
- `0x140038d44`
- `0x1400397a0`
- `0x140039820`
- `0x140039d00`
- `0x140039f10`
- `0x14003ae9c`
- `0x14003aefc`
- `0x14003b094`
- `0x14003b350`
- `0x14003b600`
- `0x14003bc30`
- `0x14003bd90`
- `0x14003c660`
- `0x14003c870`
- `0x14003ccc0`
- `0x14005b250`

## callees

- `0x14001b9a0`
- `0x14002b7bc`
- `0x1400314e8`

## pseudocode

```c
void __fastcall VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER(VMX_TASK_WRAPPER *this)
{
  VMX_NOTIFICATION_QUEUE::CompleteTaskNotifications(*((VMX_NOTIFICATION_QUEUE **)Global + 36));
  if ( *(_BYTE *)this )
    (*((void (__fastcall **)(_QWORD))Global + 6))(*((_QWORD *)Global + 1));
}

```

## disassembly

```asm
0x1400314e8  push    rbx
0x1400314ea  sub     rsp, 20h
0x1400314ee  mov     rbx, rcx
0x1400314f1  mov     rcx, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x1400314f8  mov     rcx, [rcx+120h]; this
0x1400314ff  call    ?CompleteTaskNotifications@VMX_NOTIFICATION_QUEUE@@QEAAXXZ; VMX_NOTIFICATION_QUEUE::CompleteTaskNotifications(void)
0x140031504  cmp     byte ptr [rbx], 0
0x140031507  jz      short loc_14003151D
0x140031509  mov     rcx, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x140031510  mov     rax, [rcx+30h]
0x140031514  mov     rcx, [rcx+8]
0x140031518  call    _guard_dispatch_icall
0x14003151d  add     rsp, 20h
0x140031521  pop     rbx
0x140031522  retn
```
