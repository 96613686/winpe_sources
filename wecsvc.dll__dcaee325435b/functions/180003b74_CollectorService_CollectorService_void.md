# CollectorService::~CollectorService(void)

- ea: `0x180003b74`
- end: `0x180003be0`
- name: `??1CollectorService@@QEAA@XZ`
- size: `108`
- prototype: `void __fastcall(CollectorService *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180002b78`

## callees

- `0x180003b0c`
- `0x180003e3c`
- `0x18000526c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003bad`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003bb7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003bad`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003bb7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CollectorService::~CollectorService(CollectorService *this)
{
  wmi::AutoRef<AbstractEventProcessor>::Release(this);
  *(_QWORD *)this = 0;
  wmi::AutoRef<AbstractEventProcessor>::Release((char *)this + 8);
  *((_QWORD *)this + 1) = 0;
  wmi::AutoHandle::Close((CollectorService *)((char *)this + 112));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  std::auto_ptr<AbstractEventReporter>::~auto_ptr<AbstractEventReporter>((char *)this + 16);
  wmi::AutoRef<AbstractEventProcessor>::Release((char *)this + 8);
  wmi::AutoRef<AbstractEventProcessor>::Release(this);
}

```

## disassembly

```asm
0x180003b74  mov     [rsp+arg_0], rbx
0x180003b79  push    rdi
0x180003b7a  sub     rsp, 20h
0x180003b7e  mov     rdi, rcx
0x180003b81  call    ?Release@?$AutoRef@VAbstractEventProcessor@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractEventProcessor>::Release(void)
0x180003b86  lea     rbx, [rdi+8]
0x180003b8a  mov     qword ptr [rdi], 0
0x180003b91  mov     rcx, rbx
0x180003b94  call    ?Release@?$AutoRef@VAbstractEventProcessor@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractEventProcessor>::Release(void)
0x180003b99  lea     rcx, [rdi+70h]; this
0x180003b9d  mov     qword ptr [rbx], 0
0x180003ba4  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180003ba9  lea     rcx, [rdi+40h]; lpCriticalSection
0x180003bad  call    cs:__imp_DeleteCriticalSection
0x180003bb3  lea     rcx, [rdi+18h]; lpCriticalSection
0x180003bb7  call    cs:__imp_DeleteCriticalSection
0x180003bbd  lea     rcx, [rdi+10h]
0x180003bc1  call    ??1?$auto_ptr@VAbstractEventReporter@@@std@@QEAA@XZ; std::auto_ptr<AbstractEventReporter>::~auto_ptr<AbstractEventReporter>(void)
0x180003bc6  mov     rcx, rbx
0x180003bc9  call    ?Release@?$AutoRef@VAbstractEventProcessor@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractEventProcessor>::Release(void)
0x180003bce  mov     rcx, rdi
0x180003bd1  mov     rbx, [rsp+28h+arg_0]
0x180003bd6  add     rsp, 20h
0x180003bda  pop     rdi
0x180003bdb  jmp     ?Release@?$AutoRef@VAbstractEventProcessor@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractEventProcessor>::Release(void)
```
