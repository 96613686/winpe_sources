# WFDSConMgr::CInfraCastHelper::BeginConnectBackchannel(WFDSConMgr::IInfraCastBackchannelDisconnectListener *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,bool,bool,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1800478d4`
- end: `0x180047b69`
- name: `?BeginConnectBackchannel@CInfraCastHelper@WFDSConMgr@@QEAAXPEAVIInfraCastBackchannelDisconnectListener@2@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N21@Z`
- size: `661`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, char, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18005b5f0`

## callees

- `0x180002600`
- `0x180004f38`
- `0x1800059c0`
- `0x18000665c`
- `0x180006740`
- `0x18001a21c`
- `0x180030324`
- `0x1800478d4`
- `0x1800488fc`
- `0x18005c888`
- `0x18005df7c`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047a87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047a87`

## string_xrefs

- `0x18004792d`: `Attempted to create connector multiple times`
- `0x1800479cb`: `CreateInfraCastSourceConnector failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WFDSConMgr::CInfraCastHelper::BeginConnectBackchannel(
        int *a1,
        __int64 a2,
        struct _RTL_CRITICAL_SECTION *a3,
        char a4,
        char a5,
        struct _RTL_CRITICAL_SECTION *a6)
{
  __int64 v10; // rax
  __int64 v11; // r8
  int v12; // edx
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // r9
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // r10
  __int64 (__fastcall *v19)(__int64, __int64, __int64, __int64, __int64); // r11
  int v20; // eax
  int v21; // ecx
  __int64 v23; // [rsp+40h] [rbp-30h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[3]; // [rsp+48h] [rbp-28h] BYREF

  lpCriticalSection[1] = a3;
  lpCriticalSection[2] = a6;
  WFDSConMgr::CriticalSection::Lock(a1 + 18, lpCriticalSection);
  if ( *((_QWORD *)a1 + 21) )
    WFDSConMgr::CException::Throw(
      218,
      "WFDSConMgr::CInfraCastHelper::BeginConnectBackchannel",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\infracasthelper.cpp",
      142,
      L"Attempted to create connector multiple times",
      a1);
  *((_QWORD *)a1 + 8) = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
    WPP_SF_qSll(*(_QWORD *)(v11 + 16), v12, v11, (_DWORD)a1, v10, a4, a5);
  }
  v23 = 0;
  v13 = (*(__int64 (__fastcall **)(_QWORD, int *, __int64 *))(**((_QWORD **)a1 + 1) + 8LL))(
          *((_QWORD *)a1 + 1),
          a1,
          &v23);
  if ( v13 < 0 )
    WFDSConMgr::CException::Throw(
      v13,
      "WFDSConMgr::CInfraCastHelper::BeginConnectBackchannel",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\infracasthelper.cpp",
      157,
      L"CreateInfraCastSourceConnector failed",
      a1);
  if ( a6->OwningThread )
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a6);
  v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
  LOBYTE(v15) = a5;
  LOBYTE(v16) = a4;
  v20 = v19(v18, v14, v16, v15, v17);
  if ( v20 < 0 )
    WFDSConMgr::CException::Throw(
      v20,
      "WFDSConMgr::CInfraCastHelper::BeginConnectBackchannel",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\infracasthelper.cpp",
      161,
      L"BeginConnectionAsync failed synchronously",
      a1);
  std::swap<WFDSConMgr::CSessionStateMachine::StateMachineWorkQueue,std::default_delete<WFDSConMgr::CSessionStateMachine::StateMachineWorkQueue>,0>();
  std::unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>::~unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>(&v23);
  if ( lpCriticalSection[0] )
    LeaveCriticalSection(lpCriticalSection[0]);
  WFDSConMgr::WaitMultipleEvents(lpCriticalSection, 0xFFFFFFFFLL, a1 + 30, a1 + 28);
  if ( HIDWORD(lpCriticalSection[0]) == 1 )
    WFDSConMgr::CException::Throw(
      199,
      "WFDSConMgr::CInfraCastHelper::BeginConnectBackchannel",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\infracasthelper.cpp",
      171,
      L"BeginConnectBackchannel operation canceled",
      a1);
  v21 = a1[32];
  if ( v21 < 0 )
    WFDSConMgr::CException::Throw(
      v21,
      "WFDSConMgr::CInfraCastHelper::BeginConnectBackchannel",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\infracasthelper.cpp",
      174,
      L"BeginConnectionAsync failed",
      a1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_33bb0ed83718306762e11ffebbba55a0_Traceguids, a1);
  }
  std::wstring::_Tidy_deallocate(a3);
  return std::wstring::_Tidy_deallocate(a6);
}

```

## disassembly

```asm
0x1800478d4  push    rbp
0x1800478d6  push    rbx
0x1800478d7  push    rsi
0x1800478d8  push    rdi
0x1800478d9  push    r12
0x1800478db  push    r14
0x1800478dd  push    r15
0x1800478df  mov     rbp, rsp
0x1800478e2  sub     rsp, 70h
0x1800478e6  mov     rax, cs:__security_cookie
0x1800478ed  xor     rax, rsp
0x1800478f0  mov     [rbp+var_10], rax
0x1800478f4  movzx   r12d, r9b
0x1800478f8  mov     rsi, r8
0x1800478fb  mov     r14, rdx
0x1800478fe  mov     rbx, rcx
0x180047901  mov     [rbp+var_20], r8
0x180047905  mov     rdi, [rbp+arg_28]
0x180047909  mov     [rbp+var_18], rdi
0x18004790d  add     rcx, 48h ; 'H'
0x180047911  lea     rdx, [rbp+lpCriticalSection]
0x180047915  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x18004791a  nop
0x18004791b  lea     r15, [rbx+0A8h]
0x180047922  cmp     qword ptr [r15], 0
0x180047926  jz      short loc_180047958
0x180047928  mov     [rsp+70h+var_48], rbx; void *
0x18004792d  lea     rax, aAttemptedToCre; "Attempted to create connector multiple "...
0x180047934  mov     [rsp+70h+var_50], rax; unsigned __int16 *
0x180047939  mov     r9d, 8Eh; char
0x18004793f  lea     r8, aOnecoreuapNetW_5; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180047946  lea     rdx, aWfdsconmgrCinf_0; "WFDSConMgr::CInfraCastHelper::BeginConn"...
0x18004794d  mov     ecx, 800704DAh; char
0x180047952  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180047958  mov     [rbx+40h], r14
0x18004795c  lea     r14, WPP_GLOBAL_Control
0x180047963  mov     r8, cs:WPP_GLOBAL_Control
0x18004796a  cmp     r8, r14
0x18004796d  jz      short loc_1800479A3
0x18004796f  cmp     byte ptr [r8+19h], 4
0x180047974  jb      short loc_1800479A3
0x180047976  test    byte ptr [r8+1Ch], 1
0x18004797b  jz      short loc_1800479A3
0x18004797d  mov     rcx, rsi
0x180047980  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180047985  movzx   ecx, [rbp+arg_20]
0x180047989  mov     [rsp+70h+var_40], ecx
0x18004798d  mov     dword ptr [rsp+70h+var_48], r12d
0x180047992  mov     [rsp+70h+var_50], rax
0x180047997  mov     r9, rbx
0x18004799a  mov     rcx, [r8+10h]
0x18004799e  call    WPP_SF_qSll
0x1800479a3  mov     [rbp+var_30], 0
0x1800479ab  mov     rcx, [rbx+8]
0x1800479af  mov     rax, [rcx]
0x1800479b2  lea     r8, [rbp+var_30]
0x1800479b6  mov     rdx, rbx
0x1800479b9  mov     rax, [rax+8]
0x1800479bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800479c2  test    eax, eax
0x1800479c4  jns     short loc_1800479F3
0x1800479c6  mov     [rsp+70h+var_48], rbx; void *
0x1800479cb  lea     rcx, aCreateinfracas_0; "CreateInfraCastSourceConnector failed"
0x1800479d2  mov     [rsp+70h+var_50], rcx; unsigned __int16 *
0x1800479d7  mov     r9d, 9Dh; char
0x1800479dd  lea     r8, aOnecoreuapNetW_5; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x1800479e4  lea     rdx, aWfdsconmgrCinf_0; "WFDSConMgr::CInfraCastHelper::BeginConn"...
0x1800479eb  mov     ecx, eax; char
0x1800479ed  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800479f3  mov     r10, [rbp+var_30]
0x1800479f7  mov     rax, [r10]
0x1800479fa  mov     r11, [rax+8]
0x1800479fe  cmp     qword ptr [rdi+10h], 0
0x180047a03  jz      short loc_180047A12
0x180047a05  mov     rcx, rdi
0x180047a08  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180047a0d  mov     rdx, rax
0x180047a10  jmp     short loc_180047A14
0x180047a12  xor     edx, edx
0x180047a14  mov     rcx, rsi
0x180047a17  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180047a1c  mov     [rsp+70h+var_50], rdx
0x180047a21  mov     r9b, [rbp+arg_20]
0x180047a25  mov     r8b, r12b
0x180047a28  mov     rdx, rax
0x180047a2b  mov     rcx, r10
0x180047a2e  mov     rax, r11
0x180047a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047a36  test    eax, eax
0x180047a38  jns     short loc_180047A67
0x180047a3a  mov     [rsp+70h+var_48], rbx; void *
0x180047a3f  lea     rcx, aBeginconnectio; "BeginConnectionAsync failed synchronous"...
0x180047a46  mov     [rsp+70h+var_50], rcx; unsigned __int16 *
0x180047a4b  mov     r9d, 0A1h; char
0x180047a51  lea     r8, aOnecoreuapNetW_5; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180047a58  lea     rdx, aWfdsconmgrCinf_0; "WFDSConMgr::CInfraCastHelper::BeginConn"...
0x180047a5f  mov     ecx, eax; char
0x180047a61  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180047a67  mov     rdx, r15
0x180047a6a  lea     rcx, [rbp+var_30]
0x180047a6e  call    ??$swap@VStateMachineWorkQueue@CSessionStateMachine@WFDSConMgr@@U?$default_delete@VStateMachineWorkQueue@CSessionStateMachine@WFDSConMgr@@@std@@$0A@@std@@YAXAEAV?$unique_ptr@VStateMachineWorkQueue@CSessionStateMachine@WFDSConMgr@@U?$default_delete@VStateMachineWorkQueue@CSessionStateMachine@WFDSConMgr@@@std@@@0@0@Z; std::swap<WFDSConMgr::CSessionStateMachine::StateMachineWorkQueue,std::default_delete<WFDSConMgr::CSessionStateMachine::StateMachineWorkQueue>,0>(std::unique_ptr<WFDSConMgr::CSessionStateMachine::StateMachineWorkQueue> &,std::unique_ptr<WFDSConMgr::CSessionStateMachine::StateMachineWorkQueue> &)
0x180047a73  nop
0x180047a74  lea     rcx, [rbp+var_30]
0x180047a78  call    ??1?$unique_ptr@VCMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@U?$default_delete@VCMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@@std@@@std@@QEAA@XZ; std::unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>::~unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>(void)
0x180047a7d  nop
0x180047a7e  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180047a82  test    rcx, rcx
0x180047a85  jz      short loc_180047A8D
0x180047a87  call    cs:__imp_LeaveCriticalSection
0x180047a8d  lea     r9, [rbx+70h]
0x180047a91  lea     r8, [rbx+78h]
0x180047a95  or      edx, 0FFFFFFFFh
0x180047a98  lea     rcx, [rbp+lpCriticalSection]
0x180047a9c  call    ?WaitMultipleEvents@WFDSConMgr@@YA?AVCWaitResult@1@KAEBVCEventWrapper@1@0@Z; WFDSConMgr::WaitMultipleEvents(ulong,WFDSConMgr::CEventWrapper const &,WFDSConMgr::CEventWrapper const &)
0x180047aa1  cmp     dword ptr [rbp+lpCriticalSection+4], 1
0x180047aa5  jnz     short loc_180047AD7
0x180047aa7  mov     [rsp+70h+var_48], rbx; void *
0x180047aac  lea     rax, aBeginconnectba; "BeginConnectBackchannel operation cance"...
0x180047ab3  mov     [rsp+70h+var_50], rax; unsigned __int16 *
0x180047ab8  mov     r9d, 0ABh; char
0x180047abe  lea     r8, aOnecoreuapNetW_5; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180047ac5  lea     rdx, aWfdsconmgrCinf_0; "WFDSConMgr::CInfraCastHelper::BeginConn"...
0x180047acc  mov     ecx, 800704C7h; char
0x180047ad1  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180047ad7  mov     ecx, [rbx+80h]; char
0x180047add  test    ecx, ecx
0x180047adf  jns     short loc_180047B0C
0x180047ae1  mov     [rsp+70h+var_48], rbx; void *
0x180047ae6  lea     rax, aBeginconnectio_0; "BeginConnectionAsync failed"
0x180047aed  mov     [rsp+70h+var_50], rax; unsigned __int16 *
0x180047af2  mov     r9d, 0AEh; char
0x180047af8  lea     r8, aOnecoreuapNetW_5; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180047aff  lea     rdx, aWfdsconmgrCinf_0; "WFDSConMgr::CInfraCastHelper::BeginConn"...
0x180047b06  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180047b0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180047b13  cmp     rcx, r14
0x180047b16  jz      short loc_180047B3D
0x180047b18  cmp     byte ptr [rcx+19h], 4
0x180047b1c  jb      short loc_180047B3D
0x180047b1e  test    byte ptr [rcx+1Ch], 1
0x180047b22  jz      short loc_180047B3D
0x180047b24  mov     edx, 0Fh
0x180047b29  mov     r9, rbx
0x180047b2c  lea     r8, WPP_33bb0ed83718306762e11ffebbba55a0_Traceguids
0x180047b33  mov     rcx, [rcx+10h]
0x180047b37  call    WPP_SF_q
0x180047b3c  nop
0x180047b3d  mov     rcx, rsi
0x180047b40  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180047b45  nop
0x180047b46  mov     rcx, rdi
0x180047b49  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180047b4e  mov     rcx, [rbp+var_10]
0x180047b52  xor     rcx, rsp; StackCookie
0x180047b55  call    __security_check_cookie
0x180047b5a  add     rsp, 70h
0x180047b5e  pop     r15
0x180047b60  pop     r14
0x180047b62  pop     r12
0x180047b64  pop     rdi
0x180047b65  pop     rsi
0x180047b66  pop     rbx
0x180047b67  pop     rbp
0x180047b68  retn
```
