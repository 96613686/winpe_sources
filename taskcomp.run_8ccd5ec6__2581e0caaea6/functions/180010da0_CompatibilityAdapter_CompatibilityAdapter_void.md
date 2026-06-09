# CompatibilityAdapter::~CompatibilityAdapter(void)

- ea: `0x180010da0`
- end: `0x180010e39`
- name: `??1CompatibilityAdapter@@QEAA@XZ`
- size: `153`
- prototype: `void __fastcall(CompatibilityAdapter *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006498`

## callees

- `0x180005094`
- `0x180010cdc`
- `0x180010da0`
- `0x180011028`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010e15`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010e15`

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
0x180010da0  mov     [rsp+arg_0], rbx
0x180010da5  mov     [rsp+arg_8], rsi
0x180010daa  push    rdi
0x180010dab  sub     rsp, 20h
0x180010daf  lea     rax, ??_7CompatibilityAdapter@@6B@; const CompatibilityAdapter::`vftable'
0x180010db6  mov     rsi, rcx
0x180010db9  mov     [rcx], rax
0x180010dbc  mov     rcx, [rcx+8]; this
0x180010dc0  test    rcx, rcx
0x180010dc3  jz      short loc_180010DCA
0x180010dc5  call    ??_GCSchedule@@QEAAPEAXI@Z; CSchedule::`scalar deleting destructor'(uint)
0x180010dca  lea     rdi, [rsi+50h]
0x180010dce  mov     qword ptr [rsi+8], 0
0x180010dd6  mov     rcx, rdi; this
0x180010dd9  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180010dde  lea     rbx, [rsi+58h]
0x180010de2  mov     qword ptr [rdi], 0
0x180010de9  mov     rcx, rbx; this
0x180010dec  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180010df1  mov     rcx, rbx; this
0x180010df4  mov     qword ptr [rbx], 0
0x180010dfb  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180010e00  mov     rcx, rdi; this
0x180010e03  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x180010e08  lea     rcx, [rsi+40h]
0x180010e0c  call    ??1?$list@PEAUJOB_STATE_CHANGE_INFO@@V?$t_allocator@PEAUJOB_STATE_CHANGE_INFO@@@@@std@@QEAA@XZ; std::list<JOB_STATE_CHANGE_INFO *,t_allocator<JOB_STATE_CHANGE_INFO *>>::~list<JOB_STATE_CHANGE_INFO *,t_allocator<JOB_STATE_CHANGE_INFO *>>(void)
0x180010e11  lea     rcx, [rsi+18h]; lpCriticalSection
0x180010e15  call    cs:__imp_DeleteCriticalSection
0x180010e1c  nop     dword ptr [rax+rax+00h]
0x180010e21  lea     rcx, [rsi+10h]; this
0x180010e25  mov     rbx, [rsp+28h+arg_0]
0x180010e2a  mov     rsi, [rsp+28h+arg_8]
0x180010e2f  add     rsp, 20h
0x180010e33  pop     rdi
0x180010e34  jmp     ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
```
