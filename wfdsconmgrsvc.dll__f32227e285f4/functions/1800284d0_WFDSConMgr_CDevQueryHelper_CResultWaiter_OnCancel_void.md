# WFDSConMgr::CDevQueryHelper::CResultWaiter::OnCancel(void)

- ea: `0x1800284d0`
- end: `0x1800285ec`
- name: `?OnCancel@CResultWaiter@CDevQueryHelper@WFDSConMgr@@EEAAXXZ`
- size: `284`
- prototype: `void __fastcall(WFDSConMgr::CDevQueryHelper::CResultWaiter *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800059c0`
- `0x180006740`
- `0x180006780`
- `0x1800236d8`
- `0x18002406c`
- `0x1800284d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028575`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028575`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18002856b`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18002856b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800285d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800285d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WFDSConMgr::CDevQueryHelper::CResultWaiter::OnCancel(WFDSConMgr::CDevQueryHelper::CResultWaiter *this)
{
  DWORD LastError; // eax
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp-28h] BYREF
  const WFDSConMgr::CException *v4; // [rsp+38h] [rbp-20h] BYREF
  char v6; // [rsp+68h] [rbp+10h] BYREF
  int v7; // [rsp+70h] [rbp+18h] BYREF
  PVOID pv; // [rsp+78h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids, this);
  }
  WFDSConMgr::CriticalSection::Lock((char *)this + 112, &lpCriticalSection);
  try
  {
    if ( *((_QWORD *)this + 20) )
    {
      v6 = 0;
      v7 = 1223;
      std::make_unique<WFDSConMgr::CDevQueryHelper::CResultWaiter::NotifyCallbackContext,WFDSConMgr::IDevQueryCompleteListener * &,long,bool,0>(
        &pv,
        (_QWORD *)this + 20,
        &v7,
        &v6);
      if ( TrySubmitThreadpoolCallback(WFDSConMgr::CDevQueryHelper::CResultWaiter::OnDevQueryCompleteCallback, pv, 0) )
      {
        pv = 0;
      }
      else
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25)
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            82,
            &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids,
            this,
            LastError);
        }
      }
      *((_QWORD *)this + 20) = 0;
      std::unique_ptr<WFDSConMgr::CDevQueryHelper::CResultWaiter::NotifyCallbackContext>::~unique_ptr<WFDSConMgr::CDevQueryHelper::CResultWaiter::NotifyCallbackContext>(&pv);
    }
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
  }
  catch ( std::bad_alloc )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids, this);
    }
    return;
  }
  catch ( const WFDSConMgr::CException *v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        84,
        &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids,
        this,
        *(_DWORD *)v4);
    }
    return;
  }
  catch ( ... )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids, this);
    }
  }
}

```

## disassembly

```asm
0x1800284d0  mov     [rsp+arg_0], rcx
0x1800284d5  push    rbx
0x1800284d6  push    rdi
0x1800284d7  push    r14
0x1800284d9  sub     rsp, 40h
0x1800284dd  mov     rbx, rcx
0x1800284e0  lea     r14, WPP_GLOBAL_Control
0x1800284e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800284ee  cmp     rcx, r14
0x1800284f1  jz      short loc_180028518
0x1800284f3  cmp     byte ptr [rcx+19h], 4
0x1800284f7  jb      short loc_180028518
0x1800284f9  test    byte ptr [rcx+1Ch], 1
0x1800284fd  jz      short loc_180028518
0x1800284ff  mov     edx, 51h ; 'Q'
0x180028504  mov     r9, rbx
0x180028507  lea     r8, WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids
0x18002850e  mov     rcx, [rcx+10h]
0x180028512  call    WPP_SF_q
0x180028517  nop
0x180028518  lea     rcx, [rbx+70h]
0x18002851c  lea     rdx, [rsp+58h+lpCriticalSection]
0x180028521  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x180028526  nop
0x180028527  lea     rdi, [rbx+0A0h]
0x18002852e  cmp     qword ptr [rdi], 0
0x180028532  jz      loc_1800285CC
0x180028538  mov     [rsp+58h+arg_8], 0
0x18002853d  mov     [rsp+58h+arg_10], 4C7h
0x180028545  lea     r9, [rsp+58h+arg_8]
0x18002854a  lea     r8, [rsp+58h+arg_10]
0x18002854f  mov     rdx, rdi
0x180028552  lea     rcx, [rsp+58h+pv]
0x180028557  call    ??$make_unique@UNotifyCallbackContext@CResultWaiter@CDevQueryHelper@WFDSConMgr@@AEAPEAVIDevQueryCompleteListener@4@J_N$0A@@std@@YA?AV?$unique_ptr@UNotifyCallbackContext@CResultWaiter@CDevQueryHelper@WFDSConMgr@@U?$default_delete@UNotifyCallbackContext@CResultWaiter@CDevQueryHelper@WFDSConMgr@@@std@@@0@AEAPEAVIDevQueryCompleteListener@WFDSConMgr@@$$QEAJ$$QEA_N@Z; std::make_unique<WFDSConMgr::CDevQueryHelper::CResultWaiter::NotifyCallbackContext,WFDSConMgr::IDevQueryCompleteListener * &,long,bool,0>(WFDSConMgr::IDevQueryCompleteListener * &,long &&,bool &&)
0x18002855c  xor     r8d, r8d; pcbe
0x18002855f  mov     rdx, [rsp+58h+pv]; pv
0x180028564  lea     rcx, ?OnDevQueryCompleteCallback@CResultWaiter@CDevQueryHelper@WFDSConMgr@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18002856b  call    cs:__imp_TrySubmitThreadpoolCallback
0x180028571  test    eax, eax
0x180028573  jnz     short loc_1800285B1
0x180028575  call    cs:__imp_GetLastError
0x18002857b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028582  cmp     rcx, r14
0x180028585  jz      short loc_1800285BA
0x180028587  cmp     byte ptr [rcx+19h], 1
0x18002858b  jb      short loc_1800285BA
0x18002858d  test    byte ptr [rcx+1Ch], 1
0x180028591  jz      short loc_1800285BA
0x180028593  mov     edx, 52h ; 'R'
0x180028598  mov     [rsp+58h+var_38], eax
0x18002859c  mov     r9, rbx
0x18002859f  lea     r8, WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids
0x1800285a6  mov     rcx, [rcx+10h]
0x1800285aa  call    WPP_SF_qD
0x1800285af  jmp     short loc_1800285BA
0x1800285b1  mov     [rsp+58h+pv], 0
0x1800285ba  mov     qword ptr [rdi], 0
0x1800285c1  lea     rcx, [rsp+58h+pv]
0x1800285c6  call    ??1?$unique_ptr@UNotifyCallbackContext@CResultWaiter@CDevQueryHelper@WFDSConMgr@@U?$default_delete@UNotifyCallbackContext@CResultWaiter@CDevQueryHelper@WFDSConMgr@@@std@@@std@@QEAA@XZ; std::unique_ptr<WFDSConMgr::CDevQueryHelper::CResultWaiter::NotifyCallbackContext>::~unique_ptr<WFDSConMgr::CDevQueryHelper::CResultWaiter::NotifyCallbackContext>(void)
0x1800285cb  nop
0x1800285cc  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800285d1  test    rcx, rcx
0x1800285d4  jz      short loc_1800285DD
0x1800285d6  call    cs:__imp_LeaveCriticalSection
0x1800285dc  nop
0x1800285dd  jmp     short loc_1800285E3
0x1800285df  jmp     short loc_1800285E3
0x1800285e1  jmp     short $+2
0x1800285e3  add     rsp, 40h
0x1800285e7  pop     r14
0x1800285e9  pop     rdi
0x1800285ea  pop     rbx
0x1800285eb  retn
```
