# WFDSConMgr::CMiracastHelper::~CMiracastHelper(void)

- ea: `0x180042484`
- end: `0x1800425a5`
- name: `??1CMiracastHelper@WFDSConMgr@@QEAA@XZ`
- size: `289`
- prototype: `void __fastcall(WFDSConMgr::CMiracastHelper *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180043f20`

## callees

- `0x18000475c`
- `0x180004794`
- `0x180006740`
- `0x18001a21c`
- `0x180042468`
- `0x180042484`
- `0x18004263c`
- `0x180043a9c`
- `0x180043b1c`
- `0x18005dca0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004253f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004253f`

## pseudocode

```c
void __fastcall WFDSConMgr::CMiracastHelper::~CMiracastHelper(WFDSConMgr::CMiracastHelper *this)
{
  __int64 v2; // rdx
  std::_Ref_count_base *v3; // rcx
  std::_Ref_count_base *v4; // rcx
  std::_Ref_count_base *v5; // rcx
  std::_Ref_count_base *v6; // rcx
  std::_Ref_count_base *v7; // rcx
  std::_Ref_count_base *v8; // rcx

  *(_QWORD *)this = &WFDSConMgr::CMiracastHelper::`vftable';
  WFDSConMgr::CMiracastHelper::UnregisterDisplayStateChangeUpdates(this);
  if ( *((_BYTE *)this + 257) )
    WFDSConMgr::CMiracastHelper::StopMiracastDeviceNoThrow(this);
  v2 = *((_QWORD *)this + 37);
  *((_QWORD *)this + 37) = 0;
  if ( v2 )
    std::default_delete<WFDSConMgr::CWnfSubscription>::operator()();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_6cc5b45fc4293079b9a0068da4d853bc_Traceguids, this);
  }
  std::unique_ptr<WFDSConMgr::CWnfSubscription>::~unique_ptr<WFDSConMgr::CWnfSubscription>((_QWORD *)this + 37);
  std::wstring::_Tidy_deallocate((char *)this + 224);
  std::wstring::_Tidy_deallocate((char *)this + 192);
  std::wstring::_Tidy_deallocate((char *)this + 160);
  WFDSConMgr::CEventWrapper::~CEventWrapper((void **)this + 19);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 12);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  v4 = (std::_Ref_count_base *)*((_QWORD *)this + 10);
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
  v5 = (std::_Ref_count_base *)*((_QWORD *)this + 8);
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
  v6 = (std::_Ref_count_base *)*((_QWORD *)this + 6);
  if ( v6 )
    std::_Ref_count_base::_Decref(v6);
  v7 = (std::_Ref_count_base *)*((_QWORD *)this + 4);
  if ( v7 )
    std::_Ref_count_base::_Decref(v7);
  v8 = (std::_Ref_count_base *)*((_QWORD *)this + 2);
  if ( v8 )
    std::_Ref_count_base::_Decwref(v8);
}

```

## disassembly

```asm
0x180042484  mov     [rsp+arg_0], rbx
0x180042489  push    rdi
0x18004248a  sub     rsp, 20h
0x18004248e  mov     rbx, rcx
0x180042491  lea     rax, ??_7CMiracastHelper@WFDSConMgr@@6B@; const WFDSConMgr::CMiracastHelper::`vftable'
0x180042498  mov     [rcx], rax
0x18004249b  call    ?UnregisterDisplayStateChangeUpdates@CMiracastHelper@WFDSConMgr@@AEAAXXZ; WFDSConMgr::CMiracastHelper::UnregisterDisplayStateChangeUpdates(void)
0x1800424a0  cmp     byte ptr [rbx+101h], 0
0x1800424a7  jz      short loc_1800424B1
0x1800424a9  mov     rcx, rbx; this
0x1800424ac  call    ?StopMiracastDeviceNoThrow@CMiracastHelper@WFDSConMgr@@QEAAKXZ; WFDSConMgr::CMiracastHelper::StopMiracastDeviceNoThrow(void)
0x1800424b1  lea     rdi, [rbx+128h]
0x1800424b8  mov     rdx, [rdi]
0x1800424bb  mov     qword ptr [rdi], 0
0x1800424c2  test    rdx, rdx
0x1800424c5  jz      short loc_1800424CC
0x1800424c7  call    ??R?$default_delete@VCWnfSubscription@WFDSConMgr@@@std@@QEBAXPEAVCWnfSubscription@WFDSConMgr@@@Z; std::default_delete<WFDSConMgr::CWnfSubscription>::operator()(WFDSConMgr::CWnfSubscription *)
0x1800424cc  lea     rax, WPP_GLOBAL_Control
0x1800424d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800424da  cmp     rcx, rax
0x1800424dd  jz      short loc_180042503
0x1800424df  cmp     byte ptr [rcx+19h], 4
0x1800424e3  jb      short loc_180042503
0x1800424e5  test    byte ptr [rcx+1Ch], 1
0x1800424e9  jz      short loc_180042503
0x1800424eb  mov     edx, 0Ah
0x1800424f0  mov     r9, rbx
0x1800424f3  lea     r8, WPP_6cc5b45fc4293079b9a0068da4d853bc_Traceguids
0x1800424fa  mov     rcx, [rcx+10h]
0x1800424fe  call    WPP_SF_q
0x180042503  mov     rcx, rdi
0x180042506  call    ??1?$unique_ptr@VCWnfSubscription@WFDSConMgr@@U?$default_delete@VCWnfSubscription@WFDSConMgr@@@std@@@std@@QEAA@XZ; std::unique_ptr<WFDSConMgr::CWnfSubscription>::~unique_ptr<WFDSConMgr::CWnfSubscription>(void)
0x18004250b  lea     rcx, [rbx+0E0h]
0x180042512  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042517  lea     rcx, [rbx+0C0h]
0x18004251e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042523  lea     rcx, [rbx+0A0h]
0x18004252a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004252f  lea     rcx, [rbx+98h]; this
0x180042536  call    ??1CEventWrapper@WFDSConMgr@@QEAA@XZ; WFDSConMgr::CEventWrapper::~CEventWrapper(void)
0x18004253b  lea     rcx, [rbx+68h]; lpCriticalSection
0x18004253f  call    cs:__imp_DeleteCriticalSection
0x180042545  mov     rcx, [rbx+60h]; this
0x180042549  test    rcx, rcx
0x18004254c  jz      short loc_180042553
0x18004254e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180042553  mov     rcx, [rbx+50h]; this
0x180042557  test    rcx, rcx
0x18004255a  jz      short loc_180042561
0x18004255c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180042561  mov     rcx, [rbx+40h]; this
0x180042565  test    rcx, rcx
0x180042568  jz      short loc_18004256F
0x18004256a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004256f  mov     rcx, [rbx+30h]; this
0x180042573  test    rcx, rcx
0x180042576  jz      short loc_18004257D
0x180042578  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004257d  mov     rcx, [rbx+20h]; this
0x180042581  test    rcx, rcx
0x180042584  jz      short loc_18004258B
0x180042586  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004258b  mov     rcx, [rbx+10h]; this
0x18004258f  test    rcx, rcx
0x180042592  jz      short loc_18004259A
0x180042594  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180042599  nop
0x18004259a  mov     rbx, [rsp+28h+arg_0]
0x18004259f  add     rsp, 20h
0x1800425a3  pop     rdi
0x1800425a4  retn
```
