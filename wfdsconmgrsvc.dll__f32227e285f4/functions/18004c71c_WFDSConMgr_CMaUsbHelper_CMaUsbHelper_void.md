# WFDSConMgr::CMaUsbHelper::~CMaUsbHelper(void)

- ea: `0x18004c71c`
- end: `0x18004c8ff`
- name: `??1CMaUsbHelper@WFDSConMgr@@QEAA@XZ`
- size: `483`
- prototype: `void __fastcall(WFDSConMgr::CMaUsbHelper *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180038a20`

## callees

- `0x18000475c`
- `0x180004f38`
- `0x1800059c0`
- `0x180006740`
- `0x180006780`
- `0x18001a21c`
- `0x180029f8c`
- `0x18004c71c`
- `0x18004f4c0`
- `0x18004f4ec`
- `0x18005cd7c`
- `0x18005d27c`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c789`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c789`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004c8f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall WFDSConMgr::CMaUsbHelper::~CMaUsbHelper(WFDSConMgr::CMaUsbHelper *this)
{
  char v2; // di
  unsigned int v3; // eax
  __int64 v4; // rdx
  int v5; // eax
  std::_Ref_count_base *v6; // rcx
  std::_Ref_count_base *v7; // rcx
  std::_Ref_count_base *v8; // rcx
  std::_Ref_count_base *v9; // rcx
  std::_Ref_count_base *v10; // rcx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp+8h] BYREF

  *(_QWORD *)this = &WFDSConMgr::CMaUsbHelper::`vftable';
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids, this);
  }
  WFDSConMgr::CriticalSection::Lock((char *)this + 8, &lpCriticalSection);
  v2 = *((_BYTE *)this + 369);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  if ( v2 )
  {
    v3 = WFDSConMgr::CMaUsbHelper::StopIpSessionNoThrow(this);
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids, this, v3);
      }
    }
  }
  WFDSConMgr::CMaUsbHelper::UnregisterForPnpRemoveNotification(this);
  v4 = *((_QWORD *)this + 33);
  if ( v4 )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 24LL))(*((_QWORD *)this + 6));
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids, this, v5);
      }
    }
  }
  WFDSConMgr::CThreadpoolEnvironment::CleanupGroupMembers((WFDSConMgr::CMaUsbHelper *)((char *)this + 112), v4);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids, this);
  }
  std::wstring::_Tidy_deallocate((char *)this + 312);
  std::wstring::_Tidy_deallocate((char *)this + 280);
  v6 = (std::_Ref_count_base *)*((_QWORD *)this + 34);
  if ( v6 )
    std::_Ref_count_base::_Decref(v6);
  std::unique_ptr<DAF_ASSOCIATION_HANDLE__ *,WFDSConMgr::DafAssociationContextDeleter>::~unique_ptr<DAF_ASSOCIATION_HANDLE__ *,WFDSConMgr::DafAssociationContextDeleter>((_QWORD *)this + 30);
  std::unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>::~unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>((_QWORD *)this + 29);
  WFDSConMgr::CThreadpoolEnvironment::~CThreadpoolEnvironment((WFDSConMgr::CMaUsbHelper *)((char *)this + 112));
  v7 = (std::_Ref_count_base *)*((_QWORD *)this + 13);
  if ( v7 )
    std::_Ref_count_base::_Decref(v7);
  v8 = (std::_Ref_count_base *)*((_QWORD *)this + 11);
  if ( v8 )
    std::_Ref_count_base::_Decref(v8);
  v9 = (std::_Ref_count_base *)*((_QWORD *)this + 9);
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
  v10 = (std::_Ref_count_base *)*((_QWORD *)this + 7);
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x18004c71c  push    rbx
0x18004c71e  push    rsi
0x18004c71f  push    rdi
0x18004c720  push    r14
0x18004c722  sub     rsp, 38h
0x18004c726  mov     rbx, rcx
0x18004c729  lea     rax, ??_7CMaUsbHelper@WFDSConMgr@@6B@; const WFDSConMgr::CMaUsbHelper::`vftable'
0x18004c730  mov     [rcx], rax
0x18004c733  lea     r14, WPP_GLOBAL_Control
0x18004c73a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c741  cmp     rcx, r14
0x18004c744  jz      short loc_18004C76A
0x18004c746  cmp     byte ptr [rcx+19h], 4
0x18004c74a  jb      short loc_18004C76A
0x18004c74c  test    byte ptr [rcx+1Ch], 1
0x18004c750  jz      short loc_18004C76A
0x18004c752  mov     edx, 0Fh
0x18004c757  mov     r9, rbx
0x18004c75a  lea     r8, WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids
0x18004c761  mov     rcx, [rcx+10h]
0x18004c765  call    WPP_SF_q
0x18004c76a  lea     rdx, [rsp+58h+lpCriticalSection]
0x18004c76f  lea     rcx, [rbx+8]
0x18004c773  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x18004c778  mov     dil, [rbx+171h]
0x18004c77f  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x18004c784  test    rcx, rcx
0x18004c787  jz      short loc_18004C78F
0x18004c789  call    cs:__imp_LeaveCriticalSection
0x18004c78f  test    dil, dil
0x18004c792  jz      short loc_18004C7D4
0x18004c794  mov     rcx, rbx; this
0x18004c797  call    ?StopIpSessionNoThrow@CMaUsbHelper@WFDSConMgr@@QEAAKXZ; WFDSConMgr::CMaUsbHelper::StopIpSessionNoThrow(void)
0x18004c79c  test    eax, eax
0x18004c79e  jz      short loc_18004C7D4
0x18004c7a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c7a7  cmp     rcx, r14
0x18004c7aa  jz      short loc_18004C7D4
0x18004c7ac  cmp     byte ptr [rcx+19h], 1
0x18004c7b0  jb      short loc_18004C7D4
0x18004c7b2  test    byte ptr [rcx+1Ch], 1
0x18004c7b6  jz      short loc_18004C7D4
0x18004c7b8  mov     edx, 10h
0x18004c7bd  mov     [rsp+58h+var_38], eax
0x18004c7c1  mov     r9, rbx
0x18004c7c4  lea     r8, WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids
0x18004c7cb  mov     rcx, [rcx+10h]
0x18004c7cf  call    WPP_SF_qD
0x18004c7d4  mov     rcx, rbx; this
0x18004c7d7  call    ?UnregisterForPnpRemoveNotification@CMaUsbHelper@WFDSConMgr@@AEAAXXZ; WFDSConMgr::CMaUsbHelper::UnregisterForPnpRemoveNotification(void)
0x18004c7dc  mov     rdx, [rbx+108h]
0x18004c7e3  test    rdx, rdx
0x18004c7e6  jz      short loc_18004C830
0x18004c7e8  mov     rcx, [rbx+30h]
0x18004c7ec  mov     rax, [rcx]
0x18004c7ef  mov     rax, [rax+18h]
0x18004c7f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c7f8  test    eax, eax
0x18004c7fa  jz      short loc_18004C830
0x18004c7fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c803  cmp     rcx, r14
0x18004c806  jz      short loc_18004C830
0x18004c808  cmp     byte ptr [rcx+19h], 1
0x18004c80c  jb      short loc_18004C830
0x18004c80e  test    byte ptr [rcx+1Ch], 1
0x18004c812  jz      short loc_18004C830
0x18004c814  mov     edx, 11h
0x18004c819  mov     [rsp+58h+var_38], eax
0x18004c81d  mov     r9, rbx
0x18004c820  lea     r8, WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids
0x18004c827  mov     rcx, [rcx+10h]
0x18004c82b  call    WPP_SF_qD
0x18004c830  lea     rcx, [rbx+70h]; this
0x18004c834  call    ?CleanupGroupMembers@CThreadpoolEnvironment@WFDSConMgr@@QEAAX_N@Z; WFDSConMgr::CThreadpoolEnvironment::CleanupGroupMembers(bool)
0x18004c839  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c840  cmp     rcx, r14
0x18004c843  jz      short loc_18004C869
0x18004c845  cmp     byte ptr [rcx+19h], 4
0x18004c849  jb      short loc_18004C869
0x18004c84b  test    byte ptr [rcx+1Ch], 1
0x18004c84f  jz      short loc_18004C869
0x18004c851  mov     edx, 12h
0x18004c856  mov     r9, rbx
0x18004c859  lea     r8, WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids
0x18004c860  mov     rcx, [rcx+10h]
0x18004c864  call    WPP_SF_q
0x18004c869  lea     rcx, [rbx+138h]
0x18004c870  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004c875  lea     rcx, [rbx+118h]
0x18004c87c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004c881  mov     rcx, [rbx+110h]; this
0x18004c888  test    rcx, rcx
0x18004c88b  jz      short loc_18004C892
0x18004c88d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004c892  lea     rcx, [rbx+0F0h]
0x18004c899  call    ??1?$unique_ptr@PEAUDAF_ASSOCIATION_HANDLE__@@UDafAssociationContextDeleter@WFDSConMgr@@@std@@QEAA@XZ; std::unique_ptr<DAF_ASSOCIATION_HANDLE__ *,WFDSConMgr::DafAssociationContextDeleter>::~unique_ptr<DAF_ASSOCIATION_HANDLE__ *,WFDSConMgr::DafAssociationContextDeleter>(void)
0x18004c89e  lea     rcx, [rbx+0E8h]
0x18004c8a5  call    ??1?$unique_ptr@VCMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@U?$default_delete@VCMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@@std@@@std@@QEAA@XZ; std::unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>::~unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>(void)
0x18004c8aa  lea     rcx, [rbx+70h]; this
0x18004c8ae  call    ??1CThreadpoolEnvironment@WFDSConMgr@@UEAA@XZ; WFDSConMgr::CThreadpoolEnvironment::~CThreadpoolEnvironment(void)
0x18004c8b3  mov     rcx, [rbx+68h]; this
0x18004c8b7  test    rcx, rcx
0x18004c8ba  jz      short loc_18004C8C1
0x18004c8bc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004c8c1  mov     rcx, [rbx+58h]; this
0x18004c8c5  test    rcx, rcx
0x18004c8c8  jz      short loc_18004C8CF
0x18004c8ca  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004c8cf  mov     rcx, [rbx+48h]; this
0x18004c8d3  test    rcx, rcx
0x18004c8d6  jz      short loc_18004C8DD
0x18004c8d8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004c8dd  mov     rcx, [rbx+38h]; this
0x18004c8e1  test    rcx, rcx
0x18004c8e4  jz      short loc_18004C8EB
0x18004c8e6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004c8eb  lea     rcx, [rbx+8]
0x18004c8ef  add     rsp, 38h
0x18004c8f3  pop     r14
0x18004c8f5  pop     rdi
0x18004c8f6  pop     rsi
0x18004c8f7  pop     rbx
0x18004c8f8  jmp     cs:__imp_DeleteCriticalSection
```
