# WFDSConMgr::CDevQueryHelper::CResultWaiter::OnTimeout(bool *)

- ea: `0x180028880`
- end: `0x1800289b3`
- name: `?OnTimeout@CResultWaiter@CDevQueryHelper@WFDSConMgr@@EEAAXPEA_N@Z`
- size: `307`
- prototype: `void __fastcall(WFDSConMgr::CDevQueryHelper::CResultWaiter *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800059c0`
- `0x180006740`
- `0x180006780`
- `0x1800236d8`
- `0x18002406c`
- `0x180028880`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028935`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028935`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18002892b`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18002892b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028996`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028996`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WFDSConMgr::CDevQueryHelper::CResultWaiter::OnTimeout(
        WFDSConMgr::CDevQueryHelper::CResultWaiter *this,
        bool *a2)
{
  DWORD LastError; // eax
  PVOID pv; // [rsp+30h] [rbp-38h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+38h] [rbp-30h] BYREF
  const WFDSConMgr::CException *v6; // [rsp+40h] [rbp-28h] BYREF
  char v9; // [rsp+80h] [rbp+18h] BYREF
  int v10; // [rsp+88h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids, this);
  }
  WFDSConMgr::CriticalSection::Lock((char *)this + 112, &lpCriticalSection);
  try
  {
    if ( *((_QWORD *)this + 20) )
    {
      v9 = 0;
      v10 = 1460;
      std::make_unique<WFDSConMgr::CDevQueryHelper::CResultWaiter::NotifyCallbackContext,WFDSConMgr::IDevQueryCompleteListener * &,long,bool,0>(
        &pv,
        (_QWORD *)this + 20,
        &v10,
        &v9);
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
            77,
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
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids, this);
    }
  }
  catch ( const WFDSConMgr::CException *v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        79,
        &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids,
        this,
        *(_DWORD *)v6);
    }
  }
  catch ( ... )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids, this);
    }
  }
  *a2 = 0;
}

```

## disassembly

```asm
0x180028880  mov     [rsp+arg_8], rdx
0x180028885  mov     [rsp+arg_0], rcx
0x18002888a  push    rbx
0x18002888b  push    rsi
0x18002888c  push    rdi
0x18002888d  sub     rsp, 50h
0x180028891  mov     rbx, rcx
0x180028894  lea     rsi, WPP_GLOBAL_Control
0x18002889b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800288a2  cmp     rcx, rsi
0x1800288a5  jz      short loc_1800288CC
0x1800288a7  cmp     byte ptr [rcx+19h], 4
0x1800288ab  jb      short loc_1800288CC
0x1800288ad  test    byte ptr [rcx+1Ch], 1
0x1800288b1  jz      short loc_1800288CC
0x1800288b3  mov     edx, 4Ch ; 'L'
0x1800288b8  mov     r9, rbx
0x1800288bb  lea     r8, WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids
0x1800288c2  mov     rcx, [rcx+10h]
0x1800288c6  call    WPP_SF_q
0x1800288cb  nop
0x1800288cc  lea     rcx, [rbx+70h]
0x1800288d0  lea     rdx, [rsp+68h+lpCriticalSection]
0x1800288d5  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x1800288da  nop
0x1800288db  lea     rdi, [rbx+0A0h]
0x1800288e2  cmp     qword ptr [rdi], 0
0x1800288e6  jz      loc_18002898C
0x1800288ec  mov     [rsp+68h+arg_10], 0
0x1800288f4  mov     [rsp+68h+arg_18], 5B4h
0x1800288ff  lea     r9, [rsp+68h+arg_10]
0x180028907  lea     r8, [rsp+68h+arg_18]
0x18002890f  mov     rdx, rdi
0x180028912  lea     rcx, [rsp+68h+pv]
0x180028917  call    ??$make_unique@UNotifyCallbackContext@CResultWaiter@CDevQueryHelper@WFDSConMgr@@AEAPEAVIDevQueryCompleteListener@4@J_N$0A@@std@@YA?AV?$unique_ptr@UNotifyCallbackContext@CResultWaiter@CDevQueryHelper@WFDSConMgr@@U?$default_delete@UNotifyCallbackContext@CResultWaiter@CDevQueryHelper@WFDSConMgr@@@std@@@0@AEAPEAVIDevQueryCompleteListener@WFDSConMgr@@$$QEAJ$$QEA_N@Z; std::make_unique<WFDSConMgr::CDevQueryHelper::CResultWaiter::NotifyCallbackContext,WFDSConMgr::IDevQueryCompleteListener * &,long,bool,0>(WFDSConMgr::IDevQueryCompleteListener * &,long &&,bool &&)
0x18002891c  xor     r8d, r8d; pcbe
0x18002891f  mov     rdx, [rsp+68h+pv]; pv
0x180028924  lea     rcx, ?OnDevQueryCompleteCallback@CResultWaiter@CDevQueryHelper@WFDSConMgr@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18002892b  call    cs:__imp_TrySubmitThreadpoolCallback
0x180028931  test    eax, eax
0x180028933  jnz     short loc_180028971
0x180028935  call    cs:__imp_GetLastError
0x18002893b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028942  cmp     rcx, rsi
0x180028945  jz      short loc_18002897A
0x180028947  cmp     byte ptr [rcx+19h], 1
0x18002894b  jb      short loc_18002897A
0x18002894d  test    byte ptr [rcx+1Ch], 1
0x180028951  jz      short loc_18002897A
0x180028953  mov     edx, 4Dh ; 'M'
0x180028958  mov     [rsp+68h+var_48], eax
0x18002895c  mov     r9, rbx
0x18002895f  lea     r8, WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids
0x180028966  mov     rcx, [rcx+10h]
0x18002896a  call    WPP_SF_qD
0x18002896f  jmp     short loc_18002897A
0x180028971  mov     [rsp+68h+pv], 0
0x18002897a  mov     qword ptr [rdi], 0
0x180028981  lea     rcx, [rsp+68h+pv]
0x180028986  call    ??1?$unique_ptr@UNotifyCallbackContext@CResultWaiter@CDevQueryHelper@WFDSConMgr@@U?$default_delete@UNotifyCallbackContext@CResultWaiter@CDevQueryHelper@WFDSConMgr@@@std@@@std@@QEAA@XZ; std::unique_ptr<WFDSConMgr::CDevQueryHelper::CResultWaiter::NotifyCallbackContext>::~unique_ptr<WFDSConMgr::CDevQueryHelper::CResultWaiter::NotifyCallbackContext>(void)
0x18002898b  nop
0x18002898c  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x180028991  test    rcx, rcx
0x180028994  jz      short loc_18002899D
0x180028996  call    cs:__imp_LeaveCriticalSection
0x18002899c  nop
0x18002899d  jmp     short loc_1800289A3
0x18002899f  jmp     short loc_1800289A3
0x1800289a1  jmp     short $+2
0x1800289a3  mov     rax, [rsp+68h+arg_8]
0x1800289a8  mov     byte ptr [rax], 0
0x1800289ab  add     rsp, 50h
0x1800289af  pop     rdi
0x1800289b0  pop     rsi
0x1800289b1  pop     rbx
0x1800289b2  retn
```
