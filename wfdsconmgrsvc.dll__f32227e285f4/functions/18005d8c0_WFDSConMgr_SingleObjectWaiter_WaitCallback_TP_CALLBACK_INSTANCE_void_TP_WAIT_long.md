# WFDSConMgr::SingleObjectWaiter::WaitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x18005d8c0`
- end: `0x18005db82`
- name: `?WaitCallback@SingleObjectWaiter@WFDSConMgr@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `706`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180002600`
- `0x180005498`
- `0x180006740`
- `0x180009b5c`
- `0x18005d8c0`
- `0x18005f684`
- `0x18005f76c`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005da5d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005da5d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005dae3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005dae3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005da7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005da7f`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18005da91`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18005da91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005daf4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005daf4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WFDSConMgr::SingleObjectWaiter::WaitCallback(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  __int64 v6; // rcx
  RTL_SRWLOCK *v7; // rdi
  char v8; // si
  PVOID *v9; // rcx
  struct _FILETIME *v10; // r8
  struct _RTL_CRITICAL_SECTION *v11; // rdi
  _BYTE v12[8]; // [rsp+30h] [rbp-58h] BYREF
  PSRWLOCK SRWLock[2]; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v14[24]; // [rsp+48h] [rbp-40h] BYREF

  v12[0] = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids, Context);
  }
  WFDSConMgr::CSwapActivity::CSwapActivity((WFDSConMgr::CSwapActivity *)v14, (const struct _GUID *)(Context + 8));
  if ( WaitResult == 258 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids, Context);
    }
    (*(void (__fastcall **)(char *, _BYTE *))(*(_QWORD *)Context + 40LL))(Context, v12);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids, Context);
    }
    (*(void (__fastcall **)(char *, _BYTE *))(*(_QWORD *)Context + 32LL))(Context, v12);
  }
  if ( v12[0] )
  {
    v6 = *((_QWORD *)Context + 3);
    if ( v6 )
    {
      WFDSConMgr::CThreadpoolEnvironmentBase::AcquireLockQueueShared(v6, SRWLock);
      v7 = SRWLock[0];
      v8 = 1;
      if ( *(_BYTE *)(*((_QWORD *)Context + 3) + 88LL) )
      {
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
LABEL_33:
          if ( v7 )
          {
            ReleaseSRWLockShared(v7);
LABEL_49:
            v9 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_50;
          }
          goto LABEL_50;
        }
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids, Context);
LABEL_32:
        v9 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_33;
      }
    }
    else
    {
      v7 = 0;
      v8 = 0;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids, Context);
    }
    if ( Context[48] )
      v10 = 0;
    else
      v10 = (struct _FILETIME *)(Context + 52);
    SetThreadpoolWait(*((PTP_WAIT *)Context + 4), *((HANDLE *)Context + 5), v10);
    if ( !v8 )
      goto LABEL_49;
    goto LABEL_32;
  }
  v11 = (struct _RTL_CRITICAL_SECTION *)(Context + 72);
  if ( !TryEnterCriticalSection((LPCRITICAL_SECTION)(Context + 72)) )
    v11 = 0;
  if ( v11 )
  {
    if ( *((_QWORD *)Context + 4) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          40,
          WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids,
          Context,
          *((_QWORD *)Context + 4));
      }
      CloseThreadpoolWait(*((PTP_WAIT *)Context + 4));
      *((_QWORD *)Context + 4) = 0;
    }
    LeaveCriticalSection(v11);
    goto LABEL_49;
  }
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_54;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids, Context);
    goto LABEL_49;
  }
LABEL_50:
  if ( v9 != &WPP_GLOBAL_Control && *((_BYTE *)v9 + 25) >= 4u && (*((_BYTE *)v9 + 28) & 1) != 0 )
    WPP_SF_q(v9[2], 42, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids, Context);
LABEL_54:
  WFDSConMgr::CSwapActivity::~CSwapActivity((WFDSConMgr::CSwapActivity *)v14);
}

```

## disassembly

```asm
0x18005d8c0  mov     [rsp+arg_0], rbx
0x18005d8c5  mov     [rsp+arg_10], rsi
0x18005d8ca  push    rdi
0x18005d8cb  push    r12
0x18005d8cd  push    r13
0x18005d8cf  sub     rsp, 70h
0x18005d8d3  mov     rax, cs:__security_cookie
0x18005d8da  xor     rax, rsp
0x18005d8dd  mov     [rsp+88h+var_28], rax
0x18005d8e2  mov     edi, r9d
0x18005d8e5  mov     rbx, rdx
0x18005d8e8  mov     [rsp+88h+var_58], 0
0x18005d8ed  lea     r12, WPP_GLOBAL_Control
0x18005d8f4  lea     r13, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids
0x18005d8fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d902  cmp     rcx, r12
0x18005d905  jz      short loc_18005D927
0x18005d907  cmp     byte ptr [rcx+19h], 4
0x18005d90b  jb      short loc_18005D927
0x18005d90d  test    byte ptr [rcx+1Ch], 1
0x18005d911  jz      short loc_18005D927
0x18005d913  mov     edx, 23h ; '#'
0x18005d918  mov     r9, rbx
0x18005d91b  mov     r8, r13
0x18005d91e  mov     rcx, [rcx+10h]
0x18005d922  call    WPP_SF_q
0x18005d927  lea     rdx, [rbx+8]; struct _GUID *
0x18005d92b  lea     rcx, [rsp+88h+var_40]; this
0x18005d930  call    ??0CSwapActivity@WFDSConMgr@@QEAA@AEBU_GUID@@@Z; WFDSConMgr::CSwapActivity::CSwapActivity(_GUID const &)
0x18005d935  nop
0x18005d936  cmp     edi, 102h
0x18005d93c  jnz     short loc_18005D973
0x18005d93e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d945  cmp     rcx, r12
0x18005d948  jz      short loc_18005D96A
0x18005d94a  cmp     byte ptr [rcx+19h], 4
0x18005d94e  jb      short loc_18005D96A
0x18005d950  test    byte ptr [rcx+1Ch], 1
0x18005d954  jz      short loc_18005D96A
0x18005d956  mov     edx, 24h ; '$'
0x18005d95b  mov     r9, rbx
0x18005d95e  mov     r8, r13
0x18005d961  mov     rcx, [rcx+10h]
0x18005d965  call    WPP_SF_q
0x18005d96a  mov     rax, [rbx]
0x18005d96d  mov     rax, [rax+28h]
0x18005d971  jmp     short loc_18005D9A6
0x18005d973  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d97a  cmp     rcx, r12
0x18005d97d  jz      short loc_18005D99F
0x18005d97f  cmp     byte ptr [rcx+19h], 4
0x18005d983  jb      short loc_18005D99F
0x18005d985  test    byte ptr [rcx+1Ch], 1
0x18005d989  jz      short loc_18005D99F
0x18005d98b  mov     edx, 25h ; '%'
0x18005d990  mov     r9, rbx
0x18005d993  mov     r8, r13
0x18005d996  mov     rcx, [rcx+10h]
0x18005d99a  call    WPP_SF_q
0x18005d99f  mov     rax, [rbx]
0x18005d9a2  mov     rax, [rax+20h]
0x18005d9a6  lea     rdx, [rsp+88h+var_58]
0x18005d9ab  mov     rcx, rbx
0x18005d9ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d9b3  cmp     [rsp+88h+var_58], 0
0x18005d9b8  jz      loc_18005DA8A
0x18005d9be  mov     rcx, [rbx+18h]
0x18005d9c2  test    rcx, rcx
0x18005d9c5  jz      short loc_18005DA15
0x18005d9c7  lea     rdx, [rsp+88h+SRWLock]
0x18005d9cc  call    ?AcquireLockQueueShared@CThreadpoolEnvironmentBase@WFDSConMgr@@QEAA?AV?$LockSentry@VReadersWriterLock@WFDSConMgr@@$00@2@XZ; WFDSConMgr::CThreadpoolEnvironmentBase::AcquireLockQueueShared(void)
0x18005d9d1  mov     rdi, [rsp+88h+SRWLock]
0x18005d9d6  mov     sil, 1
0x18005d9d9  mov     rax, [rbx+18h]
0x18005d9dd  cmp     byte ptr [rax+58h], 0
0x18005d9e1  jz      short loc_18005DA1A
0x18005d9e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d9ea  cmp     rcx, r12
0x18005d9ed  jz      loc_18005DA73
0x18005d9f3  cmp     byte ptr [rcx+19h], 4
0x18005d9f7  jb      short loc_18005DA73
0x18005d9f9  test    [rcx+1Ch], sil
0x18005d9fd  jz      short loc_18005DA73
0x18005d9ff  mov     edx, 27h ; '''
0x18005da04  mov     r9, rbx
0x18005da07  mov     r8, r13
0x18005da0a  mov     rcx, [rcx+10h]
0x18005da0e  call    WPP_SF_q
0x18005da13  jmp     short loc_18005DA6C
0x18005da15  xor     edi, edi
0x18005da17  xor     sil, sil
0x18005da1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005da21  cmp     rcx, r12
0x18005da24  jz      short loc_18005DA46
0x18005da26  cmp     byte ptr [rcx+19h], 4
0x18005da2a  jb      short loc_18005DA46
0x18005da2c  test    byte ptr [rcx+1Ch], 1
0x18005da30  jz      short loc_18005DA46
0x18005da32  mov     edx, 26h ; '&'
0x18005da37  mov     r9, rbx
0x18005da3a  mov     r8, r13
0x18005da3d  mov     rcx, [rcx+10h]
0x18005da41  call    WPP_SF_q
0x18005da46  cmp     byte ptr [rbx+30h], 0
0x18005da4a  jz      short loc_18005DA51
0x18005da4c  xor     r8d, r8d
0x18005da4f  jmp     short loc_18005DA55
0x18005da51  lea     r8, [rbx+34h]; pftTimeout
0x18005da55  mov     rdx, [rbx+28h]; h
0x18005da59  mov     rcx, [rbx+20h]; pwa
0x18005da5d  call    cs:__imp_SetThreadpoolWait
0x18005da63  test    sil, sil
0x18005da66  jz      loc_18005DB28
0x18005da6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005da73  test    rdi, rdi
0x18005da76  jz      loc_18005DB2F
0x18005da7c  mov     rcx, rdi; SRWLock
0x18005da7f  call    cs:__imp_ReleaseSRWLockShared
0x18005da85  jmp     loc_18005DB28
0x18005da8a  lea     rdi, [rbx+48h]
0x18005da8e  mov     rcx, rdi; lpCriticalSection
0x18005da91  call    cs:__imp_TryEnterCriticalSection
0x18005da97  xor     ecx, ecx
0x18005da99  cmp     eax, 1
0x18005da9c  cmovnz  rdi, rcx
0x18005daa0  test    rdi, rdi
0x18005daa3  jz      short loc_18005DAFC
0x18005daa5  mov     rax, [rbx+20h]
0x18005daa9  test    rax, rax
0x18005daac  jz      short loc_18005DAF1
0x18005daae  mov     rcx, cs:WPP_GLOBAL_Control
0x18005dab5  cmp     rcx, r12
0x18005dab8  jz      short loc_18005DADF
0x18005daba  cmp     byte ptr [rcx+19h], 4
0x18005dabe  jb      short loc_18005DADF
0x18005dac0  test    byte ptr [rcx+1Ch], 1
0x18005dac4  jz      short loc_18005DADF
0x18005dac6  mov     edx, 28h ; '('
0x18005dacb  mov     [rsp+88h+var_68], rax
0x18005dad0  mov     r9, rbx
0x18005dad3  mov     r8, r13
0x18005dad6  mov     rcx, [rcx+10h]
0x18005dada  call    WPP_SF_qq
0x18005dadf  mov     rcx, [rbx+20h]; pwa
0x18005dae3  call    cs:__imp_CloseThreadpoolWait
0x18005dae9  mov     qword ptr [rbx+20h], 0
0x18005daf1  mov     rcx, rdi; lpCriticalSection
0x18005daf4  call    cs:__imp_LeaveCriticalSection
0x18005dafa  jmp     short loc_18005DB28
0x18005dafc  mov     rcx, cs:WPP_GLOBAL_Control
0x18005db03  cmp     rcx, r12
0x18005db06  jz      short loc_18005DB55
0x18005db08  cmp     byte ptr [rcx+19h], 4
0x18005db0c  jb      short loc_18005DB2F
0x18005db0e  test    byte ptr [rcx+1Ch], 1
0x18005db12  jz      short loc_18005DB2F
0x18005db14  mov     edx, 29h ; ')'
0x18005db19  mov     r9, rbx
0x18005db1c  mov     r8, r13
0x18005db1f  mov     rcx, [rcx+10h]
0x18005db23  call    WPP_SF_q
0x18005db28  mov     rcx, cs:WPP_GLOBAL_Control
0x18005db2f  cmp     rcx, r12
0x18005db32  jz      short loc_18005DB55
0x18005db34  cmp     byte ptr [rcx+19h], 4
0x18005db38  jb      short loc_18005DB55
0x18005db3a  test    byte ptr [rcx+1Ch], 1
0x18005db3e  jz      short loc_18005DB55
0x18005db40  mov     edx, 2Ah ; '*'
0x18005db45  mov     r9, rbx
0x18005db48  mov     r8, r13
0x18005db4b  mov     rcx, [rcx+10h]
0x18005db4f  call    WPP_SF_q
0x18005db54  nop
0x18005db55  lea     rcx, [rsp+88h+var_40]; this
0x18005db5a  call    ??1CSwapActivity@WFDSConMgr@@QEAA@XZ; WFDSConMgr::CSwapActivity::~CSwapActivity(void)
0x18005db5f  mov     rcx, [rsp+88h+var_28]
0x18005db64  xor     rcx, rsp; StackCookie
0x18005db67  call    __security_check_cookie
0x18005db6c  lea     r11, [rsp+88h+var_18]
0x18005db71  mov     rbx, [r11+20h]
0x18005db75  mov     rsi, [r11+30h]
0x18005db79  mov     rsp, r11
0x18005db7c  pop     r13
0x18005db7e  pop     r12
0x18005db80  pop     rdi
0x18005db81  retn
```
