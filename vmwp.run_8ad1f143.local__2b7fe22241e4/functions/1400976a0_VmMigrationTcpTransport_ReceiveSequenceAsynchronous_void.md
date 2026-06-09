# VmMigrationTcpTransport::ReceiveSequenceAsynchronous(void *)

- ea: `0x1400976a0`
- end: `0x140097c1d`
- name: `?ReceiveSequenceAsynchronous@VmMigrationTcpTransport@@UEAAJPEAX@Z`
- size: `1405`
- prototype: `__int64 __fastcall(VmMigrationTcpTransport *__hidden this, void *)`
- caller_count: `0`
- callee_count: `30`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x14006af58`
- `0x14006fd4c`
- `0x140078cb8`
- `0x140095d8c`
- `0x140095e04`
- `0x140095e74`
- `0x140096ad4`
- `0x1400976a0`
- `0x140097c24`
- `0x1400988f0`
- `0x14009fa0c`
- `0x1400a00bc`
- `0x1400a0174`
- `0x1400a0608`
- `0x1400c2204`
- `0x1400d7960`
- `0x14011d720`
- `0x14011d814`
- `0x14011d840`
- `0x14012bec0`
- `0x140132960`
- `0x140132d0c`
- `0x14013361c`
- `0x14013fab8`
- `0x14014c9e8`
- `0x14015e868`
- `0x1401ddc6c`
- `0x1401de71c`
- `0x1401e1764`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400979ff`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400979ff`

## string_xrefs

- `0x1400976e6`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140097711`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140097739`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140097761`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140097789`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400977b1`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400977d9`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140097a5d`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140097ac3`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140097ae1`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140097b12`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140097ba1`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall VmMigrationTcpTransport::ReceiveSequenceAsynchronous(VmMigrationTcpTransport *this, void *a2)
{
  struct VmMigrationTcpTransport::_TRANSPORT_BUFFER *v4; // rbx
  __int64 future; // rbx
  __int64 v6; // rax
  DWORD v7; // eax
  void *v8; // rdx
  unsigned int v9; // r8d
  const char *v10; // r9
  const char *v11; // r9
  int v12; // eax
  __int64 v13; // r9
  __int64 v14; // rdx
  signed int v15; // ebx
  int LastError; // eax
  int v17; // eax
  signed int v18; // esi
  void *v19; // rdx
  wil::details *v20; // rcx
  int v21; // eax
  signed int v22; // edi
  int v24; // [rsp+20h] [rbp-F8h]
  struct VmMigrationTcpTransport::_TRANSPORT_BUFFER *v25; // [rsp+30h] [rbp-E8h] BYREF
  _QWORD v26[2]; // [rsp+38h] [rbp-E0h] BYREF
  _QWORD v27[2]; // [rsp+48h] [rbp-D0h] BYREF
  char v28; // [rsp+58h] [rbp-C0h]
  __int64 (__fastcall *v29)(VmMigrationTcpTransport *, __int64, _QWORD *, _QWORD *); // [rsp+60h] [rbp-B8h] BYREF
  _BYTE v30[16]; // [rsp+68h] [rbp-B0h] BYREF
  _BYTE v31[16]; // [rsp+78h] [rbp-A0h] BYREF
  void *v32; // [rsp+88h] [rbp-90h]
  VmMigrationTcpTransport *v33; // [rsp+90h] [rbp-88h]
  __int128 v34; // [rsp+98h] [rbp-80h] BYREF
  __int128 v35; // [rsp+A8h] [rbp-70h] BYREF
  __int128 v36; // [rsp+B8h] [rbp-60h] BYREF
  __int128 v37; // [rsp+C8h] [rbp-50h] BYREF
  __int64 v38; // [rsp+D8h] [rbp-40h]
  HANDLE Handles[3]; // [rsp+E0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  if ( *((_QWORD *)this + 65) == -1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4EE,
      (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
      (const char *)0x8007139FLL,
      v24);
  if ( !*((_DWORD *)this + 138) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4EF,
      (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
      (const char *)0x8007139FLL,
      v24);
  if ( !*((_QWORD *)this + 72) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4F0,
      (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
      (const char *)0x8007139FLL,
      v24);
  if ( !*((_QWORD *)this + 71) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4F1,
      (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
      (const char *)0x8007139FLL,
      v24);
  if ( !*((_QWORD *)this + 81) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4FD,
      (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
      (const char *)0x8007139FLL,
      v24);
  if ( !*((_QWORD *)this + 91) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4FE,
      (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
      (const char *)0x8007139FLL,
      v24);
  if ( !*((_QWORD *)this + 73) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4FF,
      (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
      (const char *)0x8007139FLL,
      v24);
  v34 = 0u;
  v35 = 0;
  v36 = 0;
  v27[0] = &v34;
  v27[1] = &v36;
  v28 = 1;
  if ( a2 )
  {
    _create___event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      &v35,
      1);
    _create___event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      &v36,
      1);
    v37 = 0;
    v38 = 0;
    v29 = VmMigrationTcpTransport::SendDuplexRepliesDuringAsyncSequence;
    std::shared_ptr<MuxMigrationReply::IReplyProcessor>::shared_ptr<MuxMigrationReply::IReplyProcessor>(v30, &v36);
    std::shared_ptr<MuxMigrationReply::IReplyProcessor>::shared_ptr<MuxMigrationReply::IReplyProcessor>(v31, &v35);
    v32 = a2;
    v33 = this;
    v4 = (struct VmMigrationTcpTransport::_TRANSPORT_BUFFER *)operator new(0x110u);
    v25 = v4;
    memset_0(v4, 0, 0x110u);
    std::_Associated_state<long>::_Associated_state<long>(v4);
    *(_QWORD *)v4 = &std::_Packaged_state<long (void)>::`vftable';
    v26[0] = (char *)v4 + 208;
    *((_QWORD *)v4 + 33) = 0;
    *((_QWORD *)v4 + 33) = ____Global_new_V___Func_impl_no_alloc_V___Binder_U_Unforced_std__P8VmMigrationTcpTransport__EAAJPEAXV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__1__EPEAV3_AEAPEAXAEAV45_AEAV45__std__J__V_std__V___Binder_U_Unforced_std__P8VmMigrationTcpTransport__EAAJPEAXV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__1__EPEAV3_AEAPEAXAEAV45_AEAV45__2__std__YAPEAV___Func_impl_no_alloc_V___Binder_U_Unforced_std__P8VmMigrationTcpTransport__EAAJPEAXV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__1__EPEAV3_AEAPEAXAEAV45_AEAV45__std__J__V_0___QEAV___Binder_U_Unforced_std__P8VmMigrationTcpTransport__EAAJPEAXV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__1__EPEAV3_AEAPEAXAEAV45_AEAV45__0__Z(&v29);
    *(_QWORD *)&v37 = v4;
    BYTE8(v37) = 0;
    LOBYTE(v38) = 0;
    __1__tuple_V__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__V12__std__QEAA_XZ(v30);
    future = std::packaged_task<long (void)>::get_future(&v37, v26);
    if ( &v34 != (__int128 *)future )
    {
      if ( (_QWORD)v34 )
        std::_Associated_state<int>::_Release();
      v6 = *(_QWORD *)future;
      *(_QWORD *)future = 0;
      *(_QWORD *)&v34 = v6;
      BYTE8(v34) = *(_BYTE *)(future + 8);
    }
    std::_State_manager<int>::~_State_manager<int>(v26);
    std::thread::_Start<std::packaged_task<long (void)>,>(v26, &v37);
    std::thread::detach((std::thread *)v26);
    std::thread::~thread((std::thread *)v26);
    std::packaged_task<long (std::future<long>,std::future<long>)>::~packaged_task<long (std::future<long>,std::future<long>)>(&v37);
  }
  Handles[0] = *((HANDLE *)this + 91);
  Handles[1] = *((HANDLE *)this + 73);
  Handles[2] = *((HANDLE *)this + 81);
  while ( 1 )
  {
    v7 = WaitForMultipleObjects(3u, Handles, 0, 0x7530u);
    if ( !v7 )
    {
      v13 = 2147500036LL;
      v14 = 1329;
      goto LABEL_37;
    }
    if ( v7 == 1 )
    {
      v15 = *((_DWORD *)this + 148);
      if ( v15 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x538,
          (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
          (const char *)(unsigned int)v15,
          v24);
      goto LABEL_38;
    }
    if ( v7 != 2 )
      break;
    v25 = 0;
    if ( !(unsigned int)VmMigrationTcpTransport::LookupNextUnusedBuffer(this, &v25) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x543,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        v11);
    v12 = VmMigrationTcpTransport::PostReceiveBuffer(this, v25);
    if ( v12 < 0 )
    {
      v13 = (unsigned int)v12;
      v14 = 1358;
LABEL_37:
      v15 = wil::details::in1diag3::Log_Hr(
              retaddr,
              (void *)v14,
              (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
              (const char *)v13,
              v24);
      goto LABEL_38;
    }
  }
  if ( v7 == 258 )
  {
    v13 = 2147943860LL;
    v14 = 1363;
    goto LABEL_37;
  }
  v15 = -2147418113;
  if ( v7 == -1 )
  {
    LastError = wil::details::in1diag3::Log_GetLastError(retaddr, v8, v9, v10);
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_38:
  v17 = VmMigrationTcpTransport::FlushPendingReceives(this, 0x7530u);
  v18 = v17;
  if ( v17 >= 0 )
  {
    if ( (unsigned __int8)_is_valid___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEBA_NXZ(&v35) )
    {
      if ( (_QWORD)v35 )
        v20 = *(wil::details **)v35;
      else
        v20 = 0;
      wil::details::SetEvent(v20, v19);
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 71) + 16LL))(*((_QWORD *)this + 71));
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x569,
      (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
      (const char *)(unsigned int)v17,
      v24);
    if ( v15 >= 0 )
      v15 = v18;
  }
  if ( a2 )
  {
    if ( v15 >= 0 )
      v28 = 0;
    else
      wil::details::lambda_call__lambda_ac9bedc8f8020e36458987a4993f965e___::reset(v27);
    v21 = std::future<long>::get(&v34);
    v22 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x58B,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        (const char *)(unsigned int)v21,
        v24);
      if ( v15 >= 0 )
        v15 = v22;
    }
  }
  wil::details::lambda_call__lambda_ac9bedc8f8020e36458987a4993f965e___::reset(v27);
  std::shared_ptr<IMigrationTransferTransportAdapterSource>::~shared_ptr<IMigrationTransferTransportAdapterSource>(&v36);
  std::shared_ptr<IMigrationTransferTransportAdapterSource>::~shared_ptr<IMigrationTransferTransportAdapterSource>(&v35);
  std::_State_manager<int>::~_State_manager<int>(&v34);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1400976a0  mov     [rsp+arg_8], rbx
0x1400976a5  mov     [rsp+arg_10], rsi
0x1400976aa  push    rdi
0x1400976ab  push    r14
0x1400976ad  push    r15
0x1400976af  sub     rsp, 100h
0x1400976b6  mov     rax, cs:__security_cookie
0x1400976bd  xor     rax, rsp
0x1400976c0  mov     [rsp+118h+var_20], rax
0x1400976c8  mov     r14, rdx
0x1400976cb  mov     rdi, rcx
0x1400976ce  mov     rcx, [rsp+118h]; this
0x1400976d6  cmp     qword ptr [rdi+208h], 0FFFFFFFFFFFFFFFFh
0x1400976de  jnz     short loc_1400976F7
0x1400976e0  mov     r9d, 8007139Fh; char *
0x1400976e6  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400976ed  mov     edx, 4EEh; void *
0x1400976f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400976f7  mov     rcx, [rsp+118h]; this
0x1400976ff  xor     r15d, r15d
0x140097702  cmp     [rdi+228h], r15d
0x140097709  jnz     short loc_140097722
0x14009770b  mov     r9d, 8007139Fh; char *
0x140097711  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140097718  mov     edx, 4EFh; void *
0x14009771d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140097722  mov     rcx, [rsp+118h]; this
0x14009772a  cmp     [rdi+240h], r15
0x140097731  jnz     short loc_14009774A
0x140097733  mov     r9d, 8007139Fh; char *
0x140097739  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140097740  mov     edx, 4F0h; void *
0x140097745  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009774a  mov     rcx, [rsp+118h]; this
0x140097752  cmp     [rdi+238h], r15
0x140097759  jnz     short loc_140097772
0x14009775b  mov     r9d, 8007139Fh; char *
0x140097761  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140097768  mov     edx, 4F1h; void *
0x14009776d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140097772  mov     rcx, [rsp+118h]; this
0x14009777a  cmp     [rdi+288h], r15
0x140097781  jnz     short loc_14009779A
0x140097783  mov     r9d, 8007139Fh; char *
0x140097789  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140097790  mov     edx, 4FDh; void *
0x140097795  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009779a  mov     rcx, [rsp+118h]; this
0x1400977a2  cmp     [rdi+2D8h], r15
0x1400977a9  jnz     short loc_1400977C2
0x1400977ab  mov     r9d, 8007139Fh; char *
0x1400977b1  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400977b8  mov     edx, 4FEh; void *
0x1400977bd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400977c2  mov     rcx, [rsp+118h]; this
0x1400977ca  cmp     [rdi+248h], r15
0x1400977d1  jnz     short loc_1400977EA
0x1400977d3  mov     r9d, 8007139Fh; char *
0x1400977d9  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400977e0  mov     edx, 4FFh; void *
0x1400977e5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400977ea  xorps   xmm0, xmm0
0x1400977ed  movups  [rsp+118h+var_80], xmm0
0x1400977f5  mov     qword ptr [rsp+118h+var_80], r15
0x1400977fd  mov     byte ptr [rsp+118h+var_80+8], r15b
0x140097805  xorps   xmm1, xmm1
0x140097808  movdqu  [rsp+118h+var_70], xmm1
0x140097811  movdqu  [rsp+118h+var_60], xmm1
0x14009781a  lea     rax, [rsp+118h+var_80]
0x140097822  mov     [rsp+118h+var_D0], rax
0x140097827  lea     rax, [rsp+118h+var_60]
0x14009782f  mov     [rsp+118h+var_C8], rax
0x140097834  mov     [rsp+118h+var_C0], 1
0x140097839  test    r14, r14
0x14009783c  jz      loc_1400979BB
0x140097842  mov     edx, 1
0x140097847  lea     rcx, [rsp+118h+var_70]
0x14009784f  call    ?create@?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140097854  mov     edx, 1
0x140097859  lea     rcx, [rsp+118h+var_60]
0x140097861  call    ?create@?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140097866  xorps   xmm0, xmm0
0x140097869  xor     eax, eax
0x14009786b  movups  [rsp+118h+var_50], xmm0
0x140097873  mov     [rsp+118h+var_40], rax
0x14009787b  lea     rax, ?SendDuplexRepliesDuringAsyncSequence@VmMigrationTcpTransport@@IEAAJPEAXV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@1@Z
0x140097882  mov     [rsp+118h+var_B8], rax
0x140097887  lea     rdx, [rsp+118h+var_60]
0x14009788f  lea     rcx, [rsp+118h+var_B0]
0x140097894  call    ??0?$shared_ptr@VIReplyProcessor@MuxMigrationReply@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<MuxMigrationReply::IReplyProcessor>::shared_ptr<MuxMigrationReply::IReplyProcessor>(std::shared_ptr<MuxMigrationReply::IReplyProcessor> const &)
0x140097899  lea     rdx, [rsp+118h+var_70]
0x1400978a1  lea     rcx, [rsp+118h+var_A0]
0x1400978a6  call    ??0?$shared_ptr@VIReplyProcessor@MuxMigrationReply@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<MuxMigrationReply::IReplyProcessor>::shared_ptr<MuxMigrationReply::IReplyProcessor>(std::shared_ptr<MuxMigrationReply::IReplyProcessor> const &)
0x1400978ab  mov     [rsp+118h+var_90], r14
0x1400978b3  mov     [rsp+118h+var_88], rdi
0x1400978bb  mov     esi, 110h
0x1400978c0  mov     ecx, esi; Size
0x1400978c2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400978c7  mov     rbx, rax
0x1400978ca  mov     [rsp+118h+var_E8], rax
0x1400978cf  mov     r8d, esi; Size
0x1400978d2  xor     edx, edx; Val
0x1400978d4  mov     rcx, rax; void *
0x1400978d7  call    memset_0
0x1400978dc  mov     rcx, rbx
0x1400978df  call    ??0?$_Associated_state@J@std@@QEAA@PEAU?$_Deleter_base@J@1@@Z; std::_Associated_state<long>::_Associated_state<long>(std::_Deleter_base<long> *)
0x1400978e4  nop
0x1400978e5  lea     rax, ??_7?$_Packaged_state@$$A6AJXZ@std@@6B@; const std::_Packaged_state<long (void)>::`vftable'
0x1400978ec  mov     [rbx], rax
0x1400978ef  lea     rsi, [rbx+0D0h]
0x1400978f6  mov     [rsp+118h+var_E0], rsi
0x1400978fb  mov     [rsi+38h], r15
0x1400978ff  lea     rcx, [rsp+118h+var_B8]
0x140097904  call    ??$_Global_new@V?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8VmMigrationTcpTransport@@EAAJPEAXV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@1@_EPEAV3@AEAPEAXAEAV45@AEAV45@@std@@J$$V@std@@V?$_Binder@U_Unforced@std@@P8VmMigrationTcpTransport@@EAAJPEAXV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@1@_EPEAV3@AEAPEAXAEAV45@AEAV45@@2@@std@@YAPEAV?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8VmMigrationTcpTransport@@EAAJPEAXV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@1@_EPEAV3@AEAPEAXAEAV45@AEAV45@@std@@J$$V@0@$$QEAV?$_Binder@U_Unforced@std@@P8VmMigrationTcpTransport@@EAAJPEAXV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@1@_EPEAV3@AEAPEAXAEAV45@AEAV45@@0@@Z
0x140097909  mov     [rsi+38h], rax
0x14009790d  mov     qword ptr [rsp+118h+var_50], rbx
0x140097915  mov     byte ptr [rsp+118h+var_50+8], r15b
0x14009791d  mov     byte ptr [rsp+118h+var_40], r15b
0x140097925  lea     rcx, [rsp+118h+var_B0]; void *
0x14009792a  call    ??1?$tuple@V?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@V12@@std@@QEAA@XZ
0x14009792f  lea     rdx, [rsp+118h+var_E0]
0x140097934  lea     rcx, [rsp+118h+var_50]
0x14009793c  call    ?get_future@?$packaged_task@$$A6AJXZ@std@@QEAA?AV?$future@J@2@XZ; std::packaged_task<long (void)>::get_future(void)
0x140097941  mov     rbx, rax
0x140097944  lea     rax, [rsp+118h+var_80]
0x14009794c  cmp     rax, rbx
0x14009794f  jz      short loc_14009797B
0x140097951  mov     rcx, qword ptr [rsp+118h+var_80]
0x140097959  test    rcx, rcx
0x14009795c  jz      short loc_140097963
0x14009795e  call    ?_Release@?$_Associated_state@H@std@@QEAAXXZ; std::_Associated_state<int>::_Release(void)
0x140097963  mov     rax, [rbx]
0x140097966  mov     [rbx], r15
0x140097969  mov     qword ptr [rsp+118h+var_80], rax
0x140097971  mov     al, [rbx+8]
0x140097974  mov     byte ptr [rsp+118h+var_80+8], al
0x14009797b  lea     rcx, [rsp+118h+var_E0]
0x140097980  call    ??1?$_State_manager@H@std@@QEAA@XZ; std::_State_manager<int>::~_State_manager<int>(void)
0x140097985  lea     rdx, [rsp+118h+var_50]
0x14009798d  lea     rcx, [rsp+118h+var_E0]
0x140097992  call    ??$_Start@V?$packaged_task@$$A6AJXZ@std@@$$V@thread@std@@AEAAX$$QEAV?$packaged_task@$$A6AJXZ@1@@Z; std::thread::_Start<std::packaged_task<long (void)>,>(std::packaged_task<long (void)> &&)
0x140097997  nop
0x140097998  lea     rcx, [rsp+118h+var_E0]; this
0x14009799d  call    ?detach@thread@std@@QEAAXXZ; std::thread::detach(void)
0x1400979a2  nop
0x1400979a3  lea     rcx, [rsp+118h+var_E0]; this
0x1400979a8  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x1400979ad  nop
0x1400979ae  lea     rcx, [rsp+118h+var_50]
0x1400979b6  call    ??1?$packaged_task@$$A6AJV?$future@J@std@@0@Z@std@@QEAA@XZ; std::packaged_task<long (std::future<long>,std::future<long>)>::~packaged_task<long (std::future<long>,std::future<long>)>(void)
0x1400979bb  mov     rax, [rdi+2D8h]
0x1400979c2  mov     [rsp+118h+Handles], rax
0x1400979ca  mov     rax, [rdi+248h]
0x1400979d1  mov     [rsp+118h+var_30], rax
0x1400979d9  mov     rax, [rdi+288h]
0x1400979e0  mov     [rsp+118h+var_28], rax
0x1400979e8  mov     esi, 7530h
0x1400979ed  mov     r9d, esi; dwMilliseconds
0x1400979f0  xor     r8d, r8d; bWaitAll
0x1400979f3  lea     rdx, [rsp+118h+Handles]; lpHandles
0x1400979fb  lea     ecx, [r8+3]; nCount
0x1400979ff  call    cs:__imp_WaitForMultipleObjects
0x140097a06  nop     dword ptr [rax+rax+00h]
0x140097a0b  test    eax, eax
0x140097a0d  jz      loc_140097AD6
0x140097a13  cmp     eax, 1
0x140097a16  jz      loc_140097AAE
0x140097a1c  cmp     eax, 2
0x140097a1f  jnz     short loc_140097A72
0x140097a21  mov     [rsp+118h+var_E8], r15
0x140097a26  mov     rbx, [rsp+118h]
0x140097a2e  lea     rdx, [rsp+118h+var_E8]; struct VmMigrationTcpTransport::_TRANSPORT_BUFFER **
0x140097a33  mov     rcx, rdi; this
0x140097a36  call    ?LookupNextUnusedBuffer@VmMigrationTcpTransport@@IEAAHPEAPEAU_TRANSPORT_BUFFER@1@@Z; VmMigrationTcpTransport::LookupNextUnusedBuffer(VmMigrationTcpTransport::_TRANSPORT_BUFFER * *)
0x140097a3b  test    eax, eax
0x140097a3d  jz      short loc_140097A5D
0x140097a3f  mov     rdx, [rsp+118h+var_E8]; struct VmMigrationTcpTransport::_TRANSPORT_BUFFER *
0x140097a44  mov     rcx, rdi; this
0x140097a47  call    ?PostReceiveBuffer@VmMigrationTcpTransport@@IEAAJPEAU_TRANSPORT_BUFFER@1@@Z; VmMigrationTcpTransport::PostReceiveBuffer(VmMigrationTcpTransport::_TRANSPORT_BUFFER *)
0x140097a4c  test    eax, eax
0x140097a4e  jns     short loc_1400979ED
0x140097a50  mov     r9d, eax
0x140097a53  mov     edx, 54Eh
0x140097a58  jmp     loc_140097AE1
0x140097a5d  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140097a64  mov     edx, 543h; void *
0x140097a69  mov     rcx, rbx; this
0x140097a6c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140097a72  cmp     eax, 102h
0x140097a77  jz      short loc_140097AA1
0x140097a79  mov     ebx, 8000FFFFh
0x140097a7e  cmp     eax, 0FFFFFFFFh
0x140097a81  jnz     short loc_140097AF7
0x140097a83  mov     rcx, [rsp+118h]; this
0x140097a8b  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x140097a90  mov     ebx, eax
0x140097a92  test    eax, eax
0x140097a94  jle     short loc_140097AF7
0x140097a96  movzx   ebx, ax
0x140097a99  or      ebx, 80070000h
0x140097a9f  jmp     short loc_140097AF7
0x140097aa1  mov     r9d, 800705B4h
0x140097aa7  mov     edx, 553h
0x140097aac  jmp     short loc_140097AE1
0x140097aae  mov     ebx, [rdi+250h]
0x140097ab4  mov     rcx, [rsp+118h]; this
0x140097abc  test    ebx, ebx
0x140097abe  jns     short loc_140097AF7
0x140097ac0  mov     r9d, ebx; char *
0x140097ac3  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140097aca  mov     edx, 538h; void *
0x140097acf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140097ad4  jmp     short loc_140097AF7
0x140097ad6  mov     r9d, 80004004h; char *
0x140097adc  mov     edx, 531h; void *
0x140097ae1  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140097ae8  mov     rcx, [rsp+118h]; this
0x140097af0  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x140097af5  mov     ebx, eax
0x140097af7  mov     edx, esi; unsigned int
0x140097af9  mov     rcx, rdi; this
0x140097afc  call    ?FlushPendingReceives@VmMigrationTcpTransport@@IEAAJK@Z; VmMigrationTcpTransport::FlushPendingReceives(ulong)
0x140097b01  mov     esi, eax
0x140097b03  mov     rcx, [rsp+118h]; this
0x140097b0b  test    eax, eax
0x140097b0d  jns     short loc_140097B2B
0x140097b0f  mov     r9d, eax; char *
0x140097b12  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140097b19  mov     edx, 569h; void *
0x140097b1e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140097b23  test    ebx, ebx
0x140097b25  js      short loc_140097B69
0x140097b27  mov     ebx, esi
0x140097b29  jmp     short loc_140097B69
0x140097b2b  lea     rcx, [rsp+118h+var_70]
0x140097b33  call    ?is_valid@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEBA_NXZ
0x140097b38  test    al, al
0x140097b3a  jz      short loc_140097B56
0x140097b3c  mov     rax, qword ptr [rsp+118h+var_70]
0x140097b44  test    rax, rax
0x140097b47  jz      short loc_140097B4E
0x140097b49  mov     rcx, [rax]
0x140097b4c  jmp     short loc_140097B51
0x140097b4e  mov     rcx, r15; this
0x140097b51  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x140097b56  mov     rcx, [rdi+238h]
0x140097b5d  mov     rax, [rcx]
0x140097b60  mov     rax, [rax+10h]
0x140097b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140097b69  test    r14, r14
0x140097b6c  jz      short loc_140097BB7
0x140097b6e  test    ebx, ebx
0x140097b70  jns     short loc_140097B7E
0x140097b72  lea     rcx, [rsp+118h+var_D0]
0x140097b77  call    wil__details__lambda_call__lambda_ac9bedc8f8020e36458987a4993f965e_____reset
0x140097b7c  jmp     short loc_140097B83
0x140097b7e  mov     [rsp+118h+var_C0], r15b
0x140097b83  lea     rcx, [rsp+118h+var_80]
0x140097b8b  call    ?get@?$future@J@std@@QEAAJXZ; std::future<long>::get(void)
0x140097b90  mov     edi, eax
0x140097b92  mov     rcx, [rsp+118h]; this
0x140097b9a  test    eax, eax
0x140097b9c  jns     short loc_140097BB7
0x140097b9e  mov     r9d, eax; char *
0x140097ba1  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140097ba8  mov     edx, 58Bh; void *
0x140097bad  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140097bb2  test    ebx, ebx
0x140097bb4  cmovns  ebx, edi
0x140097bb7  lea     rcx, [rsp+118h+var_D0]
0x140097bbc  call    wil__details__lambda_call__lambda_ac9bedc8f8020e36458987a4993f965e_____reset
0x140097bc1  nop
0x140097bc2  lea     rcx, [rsp+118h+var_60]; void *
0x140097bca  call    ??1?$shared_ptr@VIMigrationTransferTransportAdapterSource@@@std@@QEAA@XZ; std::shared_ptr<IMigrationTransferTransportAdapterSource>::~shared_ptr<IMigrationTransferTransportAdapterSource>(void)
0x140097bcf  nop
0x140097bd0  lea     rcx, [rsp+118h+var_70]; void *
0x140097bd8  call    ??1?$shared_ptr@VIMigrationTransferTransportAdapterSource@@@std@@QEAA@XZ; std::shared_ptr<IMigrationTransferTransportAdapterSource>::~shared_ptr<IMigrationTransferTransportAdapterSource>(void)
0x140097bdd  nop
0x140097bde  lea     rcx, [rsp+118h+var_80]
0x140097be6  call    ??1?$_State_manager@H@std@@QEAA@XZ; std::_State_manager<int>::~_State_manager<int>(void)
0x140097beb  mov     eax, ebx
0x140097bed  jmp     short loc_140097BF3
0x140097bef  mov     eax, dword ptr [rsp+118h+var_E8]
0x140097bf3  mov     rcx, [rsp+118h+var_20]
0x140097bfb  xor     rcx, rsp; StackCookie
0x140097bfe  call    __security_check_cookie
0x140097c03  lea     r11, [rsp+118h+var_18]
0x140097c0b  mov     rbx, [r11+28h]
0x140097c0f  mov     rsi, [r11+30h]
0x140097c13  mov     rsp, r11
0x140097c16  pop     r15
0x140097c18  pop     r14
0x140097c1a  pop     rdi
0x140097c1b  retn
```
