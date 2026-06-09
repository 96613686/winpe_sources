# TpmTaskTrigger::~TpmTaskTrigger(void)

- ea: `0x14001d0e0`
- end: `0x14001d145`
- name: `??1TpmTaskTrigger@@QEAA@XZ`
- size: `101`
- prototype: `void __fastcall(TpmTaskTrigger *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14001d940`

## callees

- `0x14001d04c`
- `0x14001d0e0`
- `0x140044e50`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001d11c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001d11c`
- `ntoskrnl!KeSetEvent` at `0x14001d0fc`
- `ntoskrnl!KeSetEvent` at `0x14001d0fc`

## pseudocode

```c
void __fastcall TpmTaskTrigger::~TpmTaskTrigger(PRKEVENT *this)
{
  if ( *this )
  {
    KeSetEvent(this[1], 0, 0);
    KeWaitForSingleObject(*this, Executive, 0, 0, 0);
  }
  SyncObject::Cleanup((SyncObject *)(this + 1));
  Thread::~Thread((Thread *)this);
}

```

## disassembly

```asm
0x14001d0e0  mov     [rsp+arg_0], rbx
0x14001d0e5  push    rdi
0x14001d0e6  sub     rsp, 30h
0x14001d0ea  cmp     qword ptr [rcx], 0
0x14001d0ee  mov     rbx, rcx
0x14001d0f1  jz      short loc_14001D128
0x14001d0f3  mov     rcx, [rcx+8]; Event
0x14001d0f7  xor     r8d, r8d; Wait
0x14001d0fa  xor     edx, edx; Increment
0x14001d0fc  call    cs:__imp_KeSetEvent
0x14001d103  nop     dword ptr [rax+rax+00h]
0x14001d108  mov     rcx, [rbx]; Object
0x14001d10b  xor     r9d, r9d; Alertable
0x14001d10e  xor     r8d, r8d; WaitMode
0x14001d111  mov     [rsp+38h+Timeout], 0; Timeout
0x14001d11a  xor     edx, edx; WaitReason
0x14001d11c  call    cs:__imp_KeWaitForSingleObject
0x14001d123  nop     dword ptr [rax+rax+00h]
0x14001d128  lea     rcx, [rbx+8]; this
0x14001d12c  call    ?Cleanup@SyncObject@@QEAAXXZ; SyncObject::Cleanup(void)
0x14001d131  mov     rcx, rbx; this
0x14001d134  call    ??1Thread@@QEAA@XZ; Thread::~Thread(void)
0x14001d139  mov     rbx, [rsp+38h+arg_0]
0x14001d13e  add     rsp, 30h
0x14001d142  pop     rdi
0x14001d143  retn
```
