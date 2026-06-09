# WFDSConMgr::CDevQueryHelper::CResultWaiter::OnSignaled(bool *)

- ea: `0x1800286d0`
- end: `0x18002886c`
- name: `?OnSignaled@CResultWaiter@CDevQueryHelper@WFDSConMgr@@EEAAXPEA_N@Z`
- size: `412`
- prototype: `void __fastcall(WFDSConMgr::CDevQueryHelper::CResultWaiter *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000421c`
- `0x1800059c0`
- `0x180006740`
- `0x180006780`
- `0x18002406c`
- `0x1800286d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800287df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800287df`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800287d5`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800287d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002876c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800287a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002884d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002876c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800287a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002884d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WFDSConMgr::CDevQueryHelper::CResultWaiter::OnSignaled(
        WFDSConMgr::CDevQueryHelper::CResultWaiter *this,
        bool *a2)
{
  __int64 v3; // rbx
  int v4; // esi
  __int64 v5; // rbx
  char v6; // bl
  _DWORD *v7; // rax
  DWORD LastError; // eax
  const WFDSConMgr::CException *v9; // [rsp+30h] [rbp-38h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+80h] [rbp+18h] BYREF
  LPCRITICAL_SECTION v13; // [rsp+88h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids, this);
  }
  WFDSConMgr::CriticalSection::Lock((char *)this + 112, &v13);
  if ( *((_QWORD *)this + 20) )
  {
    v3 = *((_QWORD *)this + 19);
    WFDSConMgr::CriticalSection::Lock(v3 + 176, &lpCriticalSection);
    v4 = *(_DWORD *)(v3 + 356);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    v5 = *((_QWORD *)this + 19);
    WFDSConMgr::CriticalSection::Lock(v5 + 176, &lpCriticalSection);
    v6 = *(_BYTE *)(v5 + 360);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    try
    {
      v7 = operator new(0x10u);
      *(_QWORD *)v7 = *((_QWORD *)this + 20);
      v7[2] = v4;
      *((_BYTE *)v7 + 12) = v6;
      lpCriticalSection = (LPCRITICAL_SECTION)v7;
      if ( TrySubmitThreadpoolCallback(WFDSConMgr::CDevQueryHelper::CResultWaiter::OnDevQueryCompleteCallback, v7, 0) )
      {
        lpCriticalSection = 0;
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
            72,
            &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids,
            this,
            LastError);
        }
      }
      *((_QWORD *)this + 20) = 0;
      std::unique_ptr<WFDSConMgr::CDevQueryHelper::CResultWaiter::NotifyCallbackContext>::~unique_ptr<WFDSConMgr::CDevQueryHelper::CResultWaiter::NotifyCallbackContext>((void **)&lpCriticalSection);
    }
    catch ( std::bad_alloc )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids, this);
      }
      goto LABEL_19;
    }
    catch ( const WFDSConMgr::CException *v9 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          74,
          &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids,
          this,
          *(_DWORD *)v9);
      }
      goto LABEL_19;
    }
    catch ( ... )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids, this);
      }
      goto LABEL_19;
    }
  }
  if ( v13 )
    LeaveCriticalSection(v13);
LABEL_19:
  *a2 = 0;
}

```

## disassembly

```asm
0x1800286d0  mov     [rsp+arg_8], rdx
0x1800286d5  mov     [rsp+arg_0], rcx
0x1800286da  push    rbx
0x1800286db  push    rsi
0x1800286dc  push    rdi
0x1800286dd  push    r14
0x1800286df  sub     rsp, 48h
0x1800286e3  mov     rdi, rcx
0x1800286e6  lea     r14, WPP_GLOBAL_Control
0x1800286ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800286f4  cmp     rcx, r14
0x1800286f7  jz      short loc_18002871E
0x1800286f9  cmp     byte ptr [rcx+19h], 4
0x1800286fd  jb      short loc_18002871E
0x1800286ff  test    byte ptr [rcx+1Ch], 1
0x180028703  jz      short loc_18002871E
0x180028705  mov     edx, 47h ; 'G'
0x18002870a  mov     r9, rdi
0x18002870d  lea     r8, WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids
0x180028714  mov     rcx, [rcx+10h]
0x180028718  call    WPP_SF_q
0x18002871d  nop
0x18002871e  lea     rcx, [rdi+70h]
0x180028722  lea     rdx, [rsp+68h+arg_18]
0x18002872a  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x18002872f  nop
0x180028730  cmp     qword ptr [rdi+0A0h], 0
0x180028738  jz      loc_180028840
0x18002873e  mov     rbx, [rdi+98h]
0x180028745  lea     rcx, [rbx+0B0h]
0x18002874c  lea     rdx, [rsp+68h+lpCriticalSection]
0x180028754  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x180028759  mov     esi, [rbx+164h]
0x18002875f  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x180028767  test    rcx, rcx
0x18002876a  jz      short loc_180028772
0x18002876c  call    cs:__imp_LeaveCriticalSection
0x180028772  mov     rbx, [rdi+98h]
0x180028779  lea     rcx, [rbx+0B0h]
0x180028780  lea     rdx, [rsp+68h+lpCriticalSection]
0x180028788  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x18002878d  mov     bl, [rbx+168h]
0x180028793  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x18002879b  test    rcx, rcx
0x18002879e  jz      short loc_1800287A6
0x1800287a0  call    cs:__imp_LeaveCriticalSection
0x1800287a6  mov     ecx, 10h; Size
0x1800287ab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800287b0  mov     rcx, [rdi+0A0h]
0x1800287b7  mov     [rax], rcx
0x1800287ba  mov     [rax+8], esi
0x1800287bd  mov     [rax+0Ch], bl
0x1800287c0  mov     [rsp+68h+lpCriticalSection], rax
0x1800287c8  xor     r8d, r8d; pcbe
0x1800287cb  mov     rdx, rax; pv
0x1800287ce  lea     rcx, ?OnDevQueryCompleteCallback@CResultWaiter@CDevQueryHelper@WFDSConMgr@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x1800287d5  call    cs:__imp_TrySubmitThreadpoolCallback
0x1800287db  test    eax, eax
0x1800287dd  jnz     short loc_18002881B
0x1800287df  call    cs:__imp_GetLastError
0x1800287e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800287ec  cmp     rcx, r14
0x1800287ef  jz      short loc_180028827
0x1800287f1  cmp     byte ptr [rcx+19h], 1
0x1800287f5  jb      short loc_180028827
0x1800287f7  test    byte ptr [rcx+1Ch], 1
0x1800287fb  jz      short loc_180028827
0x1800287fd  mov     edx, 48h ; 'H'
0x180028802  mov     [rsp+68h+var_48], eax
0x180028806  mov     r9, rdi
0x180028809  lea     r8, WPP_28a7e1ffd8f83f2d5765982095b2a01e_Traceguids
0x180028810  mov     rcx, [rcx+10h]
0x180028814  call    WPP_SF_qD
0x180028819  jmp     short loc_180028827
0x18002881b  mov     [rsp+68h+lpCriticalSection], 0
0x180028827  mov     qword ptr [rdi+0A0h], 0
0x180028832  lea     rcx, [rsp+68h+lpCriticalSection]
0x18002883a  call    ??1?$unique_ptr@UNotifyCallbackContext@CResultWaiter@CDevQueryHelper@WFDSConMgr@@U?$default_delete@UNotifyCallbackContext@CResultWaiter@CDevQueryHelper@WFDSConMgr@@@std@@@std@@QEAA@XZ; std::unique_ptr<WFDSConMgr::CDevQueryHelper::CResultWaiter::NotifyCallbackContext>::~unique_ptr<WFDSConMgr::CDevQueryHelper::CResultWaiter::NotifyCallbackContext>(void)
0x18002883f  nop
0x180028840  mov     rcx, [rsp+68h+arg_18]; lpCriticalSection
0x180028848  test    rcx, rcx
0x18002884b  jz      short loc_180028854
0x18002884d  call    cs:__imp_LeaveCriticalSection
0x180028853  nop
0x180028854  jmp     short loc_18002885A
0x180028856  jmp     short loc_18002885A
0x180028858  jmp     short $+2
0x18002885a  mov     rax, [rsp+68h+arg_8]
0x18002885f  mov     byte ptr [rax], 0
0x180028862  add     rsp, 48h
0x180028866  pop     r14
0x180028868  pop     rdi
0x180028869  pop     rsi
0x18002886a  pop     rbx
0x18002886b  retn
```
