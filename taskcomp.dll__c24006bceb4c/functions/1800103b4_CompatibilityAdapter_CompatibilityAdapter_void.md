# CompatibilityAdapter::~CompatibilityAdapter(void)

- ea: `0x1800103b4`
- end: `0x180010447`
- name: `??1CompatibilityAdapter@@QEAA@XZ`
- size: `147`
- prototype: `void __fastcall(CompatibilityAdapter *this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800060e0`

## callees

- `0x180004e1c`
- `0x1800102f0`
- `0x1800103b4`
- `0x180010628`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010429`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010429`

## pseudocode

```c
void __fastcall CompatibilityAdapter::~CompatibilityAdapter(CompatibilityAdapter *this, unsigned int a2)
{
  CSchedule *v3; // rcx

  *(_QWORD *)this = &CompatibilityAdapter::`vftable';
  v3 = (CSchedule *)*((_QWORD *)this + 1);
  if ( v3 )
    CSchedule::`scalar deleting destructor'(v3, a2);
  *((_QWORD *)this + 1) = 0;
  wmi::AutoHandle::Close((CompatibilityAdapter *)((char *)this + 80));
  *((_QWORD *)this + 10) = 0;
  wmi::AutoHandle::Close((CompatibilityAdapter *)((char *)this + 88));
  *((_QWORD *)this + 11) = 0;
  wmi::AutoHandle::Close((CompatibilityAdapter *)((char *)this + 88));
  wmi::AutoHandle::Close((CompatibilityAdapter *)((char *)this + 80));
  std::list<JOB_STATE_CHANGE_INFO *,t_allocator<JOB_STATE_CHANGE_INFO *>>::~list<JOB_STATE_CHANGE_INFO *,t_allocator<JOB_STATE_CHANGE_INFO *>>((char *)this + 64);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  wmi::AutoHandle::Close((CompatibilityAdapter *)((char *)this + 16));
}

```

## disassembly

```asm
0x1800103b4  mov     [rsp+arg_0], rbx
0x1800103b9  mov     [rsp+arg_8], rsi
0x1800103be  push    rdi
0x1800103bf  sub     rsp, 20h
0x1800103c3  lea     rax, ??_7CompatibilityAdapter@@6B@; const CompatibilityAdapter::`vftable'
0x1800103ca  mov     rsi, rcx
0x1800103cd  mov     [rcx], rax
0x1800103d0  mov     rcx, [rcx+8]; this
0x1800103d4  test    rcx, rcx
0x1800103d7  jz      short loc_1800103DE
0x1800103d9  call    ??_GCSchedule@@QEAAPEAXI@Z; CSchedule::`scalar deleting destructor'(uint)
0x1800103de  lea     rdi, [rsi+50h]
0x1800103e2  mov     qword ptr [rsi+8], 0
0x1800103ea  mov     rcx, rdi; this
0x1800103ed  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x1800103f2  lea     rbx, [rsi+58h]
0x1800103f6  mov     qword ptr [rdi], 0
0x1800103fd  mov     rcx, rbx; this
0x180010400  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180010405  mov     rcx, rbx; this
0x180010408  mov     qword ptr [rbx], 0
0x18001040f  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180010414  mov     rcx, rdi; this
0x180010417  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x18001041c  lea     rcx, [rsi+40h]
0x180010420  call    ??1?$list@PEAUJOB_STATE_CHANGE_INFO@@V?$t_allocator@PEAUJOB_STATE_CHANGE_INFO@@@@@std@@QEAA@XZ; std::list<JOB_STATE_CHANGE_INFO *,t_allocator<JOB_STATE_CHANGE_INFO *>>::~list<JOB_STATE_CHANGE_INFO *,t_allocator<JOB_STATE_CHANGE_INFO *>>(void)
0x180010425  lea     rcx, [rsi+18h]; lpCriticalSection
0x180010429  call    cs:__imp_DeleteCriticalSection
0x18001042f  lea     rcx, [rsi+10h]; this
0x180010433  mov     rbx, [rsp+28h+arg_0]
0x180010438  mov     rsi, [rsp+28h+arg_8]
0x18001043d  add     rsp, 20h
0x180010441  pop     rdi
0x180010442  jmp     ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
```
