# WFDSConMgr::CInfraCastHelper::CompleteBackchannelConnection(bool)

- ea: `0x180047f54`
- end: `0x180048103`
- name: `?CompleteBackchannelConnection@CInfraCastHelper@WFDSConMgr@@QEAAX_N@Z`
- size: `431`
- prototype: `void __fastcall(WFDSConMgr::CInfraCastHelper *__hidden this, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180056980`

## callees

- `0x1800059c0`
- `0x180006740`
- `0x180006780`
- `0x180047f54`
- `0x18005c888`
- `0x18005df7c`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048039`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048039`

## string_xrefs

- `0x180047fdd`: `WFDSConMgr::CInfraCastHelper::CompleteBackchannelConnection`
- `0x180048020`: `WFDSConMgr::CInfraCastHelper::CompleteBackchannelConnection`
- `0x18004807c`: `WFDSConMgr::CInfraCastHelper::CompleteBackchannelConnection`
- `0x1800480b6`: `WFDSConMgr::CInfraCastHelper::CompleteBackchannelConnection`
- `0x180048007`: `CompleteConnectionAsync failed synchronously`
- `0x180048063`: `CompleteBackchannelConnection operation canceled`
- `0x18004809d`: `CompleteConnectionAsync failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WFDSConMgr::CInfraCastHelper::CompleteBackchannelConnection(
        WFDSConMgr::CInfraCastHelper *this,
        unsigned __int8 a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  int v6; // eax
  int v7; // ecx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+40h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_33bb0ed83718306762e11ffebbba55a0_Traceguids, this, a2);
  }
  WFDSConMgr::CriticalSection::Lock((char *)this + 72, &lpCriticalSection);
  v5 = *((_QWORD *)this + 21);
  if ( !v5 )
    WFDSConMgr::CException::Throw(
      21,
      "WFDSConMgr::CInfraCastHelper::CompleteBackchannelConnection",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\infracasthelper.cpp",
      213,
      L"No connector object to provide PIN",
      this);
  LOBYTE(v4) = a2;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 24LL))(v5, v4);
  if ( v6 < 0 )
    WFDSConMgr::CException::Throw(
      v6,
      "WFDSConMgr::CInfraCastHelper::CompleteBackchannelConnection",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\infracasthelper.cpp",
      217,
      L"CompleteConnectionAsync failed synchronously",
      this);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  WFDSConMgr::WaitMultipleEvents(&lpCriticalSection, 0xFFFFFFFFLL, (char *)this + 152, (char *)this + 112);
  if ( HIDWORD(lpCriticalSection) == 1 )
    WFDSConMgr::CException::Throw(
      199,
      "WFDSConMgr::CInfraCastHelper::CompleteBackchannelConnection",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\infracasthelper.cpp",
      225,
      L"CompleteBackchannelConnection operation canceled",
      this);
  v7 = *((_DWORD *)this + 40);
  if ( v7 < 0 )
    WFDSConMgr::CException::Throw(
      v7,
      "WFDSConMgr::CInfraCastHelper::CompleteBackchannelConnection",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\infracasthelper.cpp",
      228,
      L"CompleteConnectionAsync failed",
      this);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_33bb0ed83718306762e11ffebbba55a0_Traceguids, this);
  }
}

```

## disassembly

```asm
0x180047f54  mov     [rsp+arg_8], rbx
0x180047f59  mov     [rsp+arg_10], rsi
0x180047f5e  push    rdi
0x180047f5f  sub     rsp, 30h
0x180047f63  movzx   edi, dl
0x180047f66  mov     rbx, rcx
0x180047f69  lea     rsi, WPP_GLOBAL_Control
0x180047f70  mov     rcx, cs:WPP_GLOBAL_Control
0x180047f77  cmp     rcx, rsi
0x180047f7a  jz      short loc_180047FA4
0x180047f7c  cmp     byte ptr [rcx+19h], 4
0x180047f80  jb      short loc_180047FA4
0x180047f82  test    byte ptr [rcx+1Ch], 1
0x180047f86  jz      short loc_180047FA4
0x180047f88  mov     edx, 10h
0x180047f8d  mov     dword ptr [rsp+38h+var_18], edi
0x180047f91  mov     r9, rbx
0x180047f94  lea     r8, WPP_33bb0ed83718306762e11ffebbba55a0_Traceguids
0x180047f9b  mov     rcx, [rcx+10h]
0x180047f9f  call    WPP_SF_qD
0x180047fa4  lea     rcx, [rbx+48h]
0x180047fa8  lea     rdx, [rsp+38h+lpCriticalSection]
0x180047fad  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x180047fb2  nop
0x180047fb3  mov     rcx, [rbx+0A8h]
0x180047fba  test    rcx, rcx
0x180047fbd  jnz     short loc_180047FEF
0x180047fbf  mov     [rsp+38h+var_10], rbx; void *
0x180047fc4  lea     rax, aNoConnectorObj_0; "No connector object to provide PIN"
0x180047fcb  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x180047fd0  mov     r9d, 0D5h; char
0x180047fd6  lea     r8, aOnecoreuapNetW_5; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180047fdd  lea     rdx, aWfdsconmgrCinf_2; "WFDSConMgr::CInfraCastHelper::CompleteB"...
0x180047fe4  mov     ecx, 80070015h; char
0x180047fe9  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180047fef  mov     rax, [rcx]
0x180047ff2  mov     dl, dil
0x180047ff5  mov     rax, [rax+18h]
0x180047ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ffe  test    eax, eax
0x180048000  jns     short loc_18004802F
0x180048002  mov     [rsp+38h+var_10], rbx; void *
0x180048007  lea     rcx, aCompleteconnec_0; "CompleteConnectionAsync failed synchron"...
0x18004800e  mov     [rsp+38h+var_18], rcx; unsigned __int16 *
0x180048013  mov     r9d, 0D9h; char
0x180048019  lea     r8, aOnecoreuapNetW_5; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180048020  lea     rdx, aWfdsconmgrCinf_2; "WFDSConMgr::CInfraCastHelper::CompleteB"...
0x180048027  mov     ecx, eax; char
0x180048029  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004802f  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x180048034  test    rcx, rcx
0x180048037  jz      short loc_18004803F
0x180048039  call    cs:__imp_LeaveCriticalSection
0x18004803f  lea     r9, [rbx+70h]
0x180048043  lea     r8, [rbx+98h]
0x18004804a  or      edx, 0FFFFFFFFh
0x18004804d  lea     rcx, [rsp+38h+lpCriticalSection]
0x180048052  call    ?WaitMultipleEvents@WFDSConMgr@@YA?AVCWaitResult@1@KAEBVCEventWrapper@1@0@Z; WFDSConMgr::WaitMultipleEvents(ulong,WFDSConMgr::CEventWrapper const &,WFDSConMgr::CEventWrapper const &)
0x180048057  cmp     dword ptr [rsp+38h+lpCriticalSection+4], 1
0x18004805c  jnz     short loc_18004808E
0x18004805e  mov     [rsp+38h+var_10], rbx; void *
0x180048063  lea     rax, aCompletebackch; "CompleteBackchannelConnection operation"...
0x18004806a  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x18004806f  mov     r9d, 0E1h; char
0x180048075  lea     r8, aOnecoreuapNetW_5; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004807c  lea     rdx, aWfdsconmgrCinf_2; "WFDSConMgr::CInfraCastHelper::CompleteB"...
0x180048083  mov     ecx, 800704C7h; char
0x180048088  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004808e  mov     ecx, [rbx+0A0h]; char
0x180048094  test    ecx, ecx
0x180048096  jns     short loc_1800480C3
0x180048098  mov     [rsp+38h+var_10], rbx; void *
0x18004809d  lea     rax, aCompleteconnec; "CompleteConnectionAsync failed"
0x1800480a4  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x1800480a9  mov     r9d, 0E4h; char
0x1800480af  lea     r8, aOnecoreuapNetW_5; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x1800480b6  lea     rdx, aWfdsconmgrCinf_2; "WFDSConMgr::CInfraCastHelper::CompleteB"...
0x1800480bd  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800480c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800480ca  cmp     rcx, rsi
0x1800480cd  jz      short loc_1800480F3
0x1800480cf  cmp     byte ptr [rcx+19h], 4
0x1800480d3  jb      short loc_1800480F3
0x1800480d5  test    byte ptr [rcx+1Ch], 1
0x1800480d9  jz      short loc_1800480F3
0x1800480db  mov     edx, 11h
0x1800480e0  mov     r9, rbx
0x1800480e3  lea     r8, WPP_33bb0ed83718306762e11ffebbba55a0_Traceguids
0x1800480ea  mov     rcx, [rcx+10h]
0x1800480ee  call    WPP_SF_q
0x1800480f3  mov     rbx, [rsp+38h+arg_8]
0x1800480f8  mov     rsi, [rsp+38h+arg_10]
0x1800480fd  add     rsp, 30h
0x180048101  pop     rdi
0x180048102  retn
```
