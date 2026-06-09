# WFDSConMgr::CThreadpoolEnvironmentBase::CThreadpoolEnvironmentBase(bool,void (*)(void *,void *))

- ea: `0x18005cbcc`
- end: `0x18005ccea`
- name: `??0CThreadpoolEnvironmentBase@WFDSConMgr@@QEAA@_NP6AXPEAX1@Z@Z`
- size: `286`
- prototype: `WFDSConMgr::CThreadpoolEnvironmentBase *__fastcall(WFDSConMgr::CThreadpoolEnvironmentBase *this, __int64, void (*)(void *, void *))`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18005cb94`

## callees

- `0x180006740`
- `0x18005c800`
- `0x18005cbcc`
- `0x18005ce90`
- `0x18005e4a0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18005cc85`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18005cc85`

## string_xrefs

- `0x18005cca6`: `onecoreuap\net\wlan\wfdsconmgr\util\src\threadpool.cpp`
- `0x18005cc94`: `CreateThreadpoolCleanupGroup failed`
- `0x18005ccad`: `WFDSConMgr::CThreadpoolEnvironmentBase::CThreadpoolEnvironmentBase`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
WFDSConMgr::CThreadpoolEnvironmentBase *__fastcall WFDSConMgr::CThreadpoolEnvironmentBase::CThreadpoolEnvironmentBase(
        WFDSConMgr::CThreadpoolEnvironmentBase *this,
        __int64 a2,
        void (*a3)(void *, void *))
{
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  void (*v6)(void *, void *); // [rsp+50h] [rbp+18h] BYREF

  v6 = a3;
  *(_QWORD *)this = &WFDSConMgr::CThreadpoolEnvironmentBase::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_BYTE *)this + 88) = 0;
  WFDSConMgr::ReadersWriterLock::ReadersWriterLock((WFDSConMgr::CThreadpoolEnvironmentBase *)((char *)this + 96));
  v6 = (void (*)(void *, void *))((char *)this + 16);
  *((_DWORD *)this + 4) = 3;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_DWORD *)this + 19) = 1;
  *((_DWORD *)this + 20) = 72;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids,
      (char *)this + 16);
  }
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *((_QWORD *)this + 1) = ThreadpoolCleanupGroup;
  if ( !ThreadpoolCleanupGroup )
    WFDSConMgr::CException::Throw(
      -2147467259,
      "WFDSConMgr::CThreadpoolEnvironmentBase::CThreadpoolEnvironmentBase",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\util\\src\\threadpool.cpp",
      112,
      L"CreateThreadpoolCleanupGroup failed");
  *((_QWORD *)this + 4) = ThreadpoolCleanupGroup;
  *((_QWORD *)this + 5) = WFDSConMgr::CThreadpoolTask::CancelRoutine;
  v6 = 0;
  WFDSConMgr::CThreadpoolEnvironmentBase::CThreadpoolEnvironmentBase_::_2_::TpEnviron::_TpEnviron(&v6);
  return this;
}

```

## disassembly

```asm
0x18005cbcc  mov     [rsp+arg_10], r8
0x18005cbd1  push    rbx
0x18005cbd2  sub     rsp, 30h
0x18005cbd6  mov     rbx, rcx
0x18005cbd9  lea     rax, ??_7CThreadpoolEnvironmentBase@WFDSConMgr@@6B@; const WFDSConMgr::CThreadpoolEnvironmentBase::`vftable'
0x18005cbe0  mov     [rcx], rax
0x18005cbe3  mov     qword ptr [rcx+8], 0
0x18005cbeb  mov     byte ptr [rcx+58h], 0
0x18005cbef  add     rcx, 60h ; '`'; this
0x18005cbf3  call    ??0ReadersWriterLock@WFDSConMgr@@QEAA@XZ; WFDSConMgr::ReadersWriterLock::ReadersWriterLock(void)
0x18005cbf8  lea     r9, [rbx+10h]
0x18005cbfc  mov     [rsp+38h+arg_10], r9
0x18005cc01  mov     dword ptr [r9], 3
0x18005cc08  mov     qword ptr [r9+8], 0
0x18005cc10  mov     qword ptr [r9+10h], 0
0x18005cc18  mov     qword ptr [r9+18h], 0
0x18005cc20  mov     qword ptr [r9+20h], 0
0x18005cc28  mov     qword ptr [r9+28h], 0
0x18005cc30  mov     qword ptr [r9+30h], 0
0x18005cc38  mov     dword ptr [r9+38h], 0
0x18005cc40  mov     dword ptr [r9+3Ch], 1
0x18005cc48  mov     dword ptr [r9+40h], 48h ; 'H'
0x18005cc50  lea     rax, WPP_GLOBAL_Control
0x18005cc57  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cc5e  cmp     rcx, rax
0x18005cc61  jz      short loc_18005CC85
0x18005cc63  cmp     byte ptr [rcx+19h], 4
0x18005cc67  jb      short loc_18005CC85
0x18005cc69  test    byte ptr [rcx+1Ch], 1
0x18005cc6d  jz      short loc_18005CC85
0x18005cc6f  mov     edx, 0Ch
0x18005cc74  lea     r8, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids
0x18005cc7b  mov     rcx, [rcx+10h]
0x18005cc7f  call    WPP_SF_q
0x18005cc84  nop
0x18005cc85  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18005cc8b  mov     [rbx+8], rax
0x18005cc8f  test    rax, rax
0x18005cc92  jnz     short loc_18005CCBF
0x18005cc94  lea     rax, aCreatethreadpo_2; "CreateThreadpoolCleanupGroup failed"
0x18005cc9b  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x18005cca0  mov     r9d, 70h ; 'p'; char
0x18005cca6  lea     r8, aOnecoreuapNetW_22; "onecoreuap\\net\\wlan\\wfdsconmgr\\util"...
0x18005ccad  lea     rdx, aWfdsconmgrCthr_2; "WFDSConMgr::CThreadpoolEnvironmentBase:"...
0x18005ccb4  mov     ecx, 80004005h; int
0x18005ccb9  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBG@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *)
0x18005ccbf  mov     [rbx+20h], rax
0x18005ccc3  lea     rax, ?CancelRoutine@CThreadpoolTask@WFDSConMgr@@CAXPEAV12@PEAX@Z; WFDSConMgr::CThreadpoolTask::CancelRoutine(WFDSConMgr::CThreadpoolTask *,void *)
0x18005ccca  mov     [rbx+28h], rax
0x18005ccce  mov     [rsp+38h+arg_10], 0
0x18005ccd7  lea     rcx, [rsp+38h+arg_10]
0x18005ccdc  call    _WFDSConMgr__CThreadpoolEnvironmentBase__CThreadpoolEnvironmentBase____2___TpEnviron___TpEnviron
0x18005cce1  mov     rax, rbx
0x18005cce4  add     rsp, 30h
0x18005cce8  pop     rbx
0x18005cce9  retn
```
