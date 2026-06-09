# VmMigrationTcpTransport::ReceiveSequenceAsynchronous(void *)

- ea: `0x140080360`
- end: `0x1400808ed`
- name: `?ReceiveSequenceAsynchronous@VmMigrationTcpTransport@@UEAAJPEAX@Z`
- size: `1421`
- prototype: `__int64 __fastcall(VmMigrationTcpTransport *__hidden this, void *)`
- caller_count: `0`
- callee_count: `30`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1400644a0`
- `0x140064f4c`
- `0x140078628`
- `0x14007cee4`
- `0x14007f2a0`
- `0x14007f318`
- `0x14007f388`
- `0x14007f764`
- `0x140080360`
- `0x1400808f4`
- `0x140082334`
- `0x1400823ec`
- `0x140082878`
- `0x14008a328`
- `0x14009801c`
- `0x1400b3cb8`
- `0x1400c6ac0`
- `0x14011ea40`
- `0x14011edec`
- `0x14011f6fc`
- `0x14012bb98`
- `0x140138ce8`
- `0x14014b190`
- `0x14016152c`
- `0x1401cd22c`
- `0x1401cd568`
- `0x1401cdda0`
- `0x1401cddcc`
- `0x1401d0e14`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400806bf`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400806bf`

## string_xrefs

- `0x1400803a6`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400803d1`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400803f9`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140080421`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140080449`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140080471`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140080499`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14008071d`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14008074f`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140080793`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400807b1`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400807e2`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140080871`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall VmMigrationTcpTransport::ReceiveSequenceAsynchronous(VmMigrationTcpTransport *this, void *a2)
{
  struct VmMigrationTcpTransport::_TRANSPORT_BUFFER *v4; // rbx
  __int64 future; // rbx
  __int64 v6; // rax
  DWORD v7; // eax
  const char *v8; // r9
  const char *v9; // r9
  int v10; // eax
  __int64 v11; // r9
  __int64 v12; // rdx
  signed int v13; // ebx
  int v14; // eax
  int v15; // eax
  signed int v16; // esi
  void *v17; // rdx
  wil::details *v18; // rcx
  int v19; // eax
  signed int v20; // edi
  int v22; // [rsp+20h] [rbp-F8h]
  struct VmMigrationTcpTransport::_TRANSPORT_BUFFER *v23; // [rsp+30h] [rbp-E8h] BYREF
  _QWORD v24[2]; // [rsp+38h] [rbp-E0h] BYREF
  _QWORD v25[2]; // [rsp+48h] [rbp-D0h] BYREF
  char v26; // [rsp+58h] [rbp-C0h]
  __int64 (__fastcall *v27)(VmMigrationTcpTransport *, __int64, _QWORD *, _QWORD *); // [rsp+60h] [rbp-B8h] BYREF
  _BYTE v28[16]; // [rsp+68h] [rbp-B0h] BYREF
  _BYTE v29[16]; // [rsp+78h] [rbp-A0h] BYREF
  void *v30; // [rsp+88h] [rbp-90h]
  VmMigrationTcpTransport *v31; // [rsp+90h] [rbp-88h]
  __int128 v32; // [rsp+98h] [rbp-80h] BYREF
  __int128 v33; // [rsp+A8h] [rbp-70h] BYREF
  __int128 v34; // [rsp+B8h] [rbp-60h] BYREF
  __int128 v35; // [rsp+C8h] [rbp-50h] BYREF
  __int64 v36; // [rsp+D8h] [rbp-40h]
  HANDLE Handles[3]; // [rsp+E0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  if ( *((_QWORD *)this + 65) == -1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4EE,
      (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
      (const char *)0x8007139FLL,
      v22);
  if ( !*((_DWORD *)this + 138) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4EF,
      (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
      (const char *)0x8007139FLL,
      v22);
  if ( !*((_QWORD *)this + 72) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4F0,
      (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
      (const char *)0x8007139FLL,
      v22);
  if ( !*((_QWORD *)this + 71) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4F1,
      (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
      (const char *)0x8007139FLL,
      v22);
  if ( !*((_QWORD *)this + 81) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4FD,
      (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
      (const char *)0x8007139FLL,
      v22);
  if ( !*((_QWORD *)this + 91) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4FE,
      (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
      (const char *)0x8007139FLL,
      v22);
  if ( !*((_QWORD *)this + 73) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4FF,
      (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
      (const char *)0x8007139FLL,
      v22);
  v32 = 0u;
  v33 = 0;
  v34 = 0;
  v25[0] = &v32;
  v25[1] = &v34;
  v26 = 1;
  if ( a2 )
  {
    _create___event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      &v33,
      1);
    _create___event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      &v34,
      1);
    v35 = 0;
    v36 = 0;
    v27 = VmMigrationTcpTransport::SendDuplexRepliesDuringAsyncSequence;
    std::shared_ptr<MuxMigrationReply::IReplyProcessor>::shared_ptr<MuxMigrationReply::IReplyProcessor>(v28, &v34);
    std::shared_ptr<MuxMigrationReply::IReplyProcessor>::shared_ptr<MuxMigrationReply::IReplyProcessor>(v29, &v33);
    v30 = a2;
    v31 = this;
    v4 = (struct VmMigrationTcpTransport::_TRANSPORT_BUFFER *)operator new(0x110u);
    v23 = v4;
    memset_0(v4, 0, 0x110u);
    std::_Associated_state<long>::_Associated_state<long>(v4);
    *(_QWORD *)v4 = &std::_Packaged_state<long (void)>::`vftable';
    v24[0] = (char *)v4 + 208;
    *((_QWORD *)v4 + 33) = 0;
    *((_QWORD *)v4 + 33) = ____Global_new_V___Func_impl_no_alloc_V___Binder_U_Unforced_std__P8VmMigrationTcpTransport__EAAJPEAXV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__1__EPEAV3_AEAPEAXAEAV45_AEAV45__std__J__V_std__V___Binder_U_Unforced_std__P8VmMigrationTcpTransport__EAAJPEAXV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__1__EPEAV3_AEAPEAXAEAV45_AEAV45__2__std__YAPEAV___Func_impl_no_alloc_V___Binder_U_Unforced_std__P8VmMigrationTcpTransport__EAAJPEAXV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__1__EPEAV3_AEAPEAXAEAV45_AEAV45__std__J__V_0___QEAV___Binder_U_Unforced_std__P8VmMigrationTcpTransport__EAAJPEAXV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__1__EPEAV3_AEAPEAXAEAV45_AEAV45__0__Z(&v27);
    *(_QWORD *)&v35 = v4;
    BYTE8(v35) = 0;
    LOBYTE(v36) = 0;
    __1__tuple_V__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__V12__std__QEAA_XZ(v28);
    future = std::packaged_task<long (void)>::get_future(&v35, v24);
    if ( &v32 != (__int128 *)future )
    {
      if ( (_QWORD)v32 )
        std::_Associated_state<int>::_Release();
      v6 = *(_QWORD *)future;
      *(_QWORD *)future = 0;
      *(_QWORD *)&v32 = v6;
      BYTE8(v32) = *(_BYTE *)(future + 8);
    }
    std::_State_manager<int>::~_State_manager<int>(v24);
    std::thread::_Start<std::packaged_task<long (void)>,>(v24, &v35);
    std::thread::detach((std::thread *)v24);
    std::thread::~thread((std::thread *)v24);
    std::packaged_task<long (std::future<long>,std::future<long>)>::~packaged_task<long (std::future<long>,std::future<long>)>(&v35);
  }
  Handles[0] = *((HANDLE *)this + 91);
  Handles[1] = *((HANDLE *)this + 73);
  Handles[2] = *((HANDLE *)this + 81);
  while ( 1 )
  {
    v7 = WaitForMultipleObjects(3u, Handles, 0, 0x7530u);
    if ( !v7 )
    {
      v11 = 2147500036LL;
      v12 = 1329;
      goto LABEL_37;
    }
    if ( v7 == 1 )
    {
      v13 = *((_DWORD *)this + 148);
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x538,
          (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
          (const char *)(unsigned int)v13,
          v22);
      goto LABEL_38;
    }
    if ( v7 != 2 )
      break;
    v23 = 0;
    if ( !(unsigned int)VmMigrationTcpTransport::LookupNextUnusedBuffer(this, &v23) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x543,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        v9);
    v10 = VmMigrationTcpTransport::PostReceiveBuffer(this, v23);
    if ( v10 < 0 )
    {
      v11 = (unsigned int)v10;
      v12 = 1358;
LABEL_37:
      v13 = wil::details::in1diag3::Log_Hr(
              retaddr,
              (void *)v12,
              (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
              (const char *)v11,
              v22);
      goto LABEL_38;
    }
  }
  if ( v7 == 258 )
  {
    v11 = 2147943860LL;
    v12 = 1363;
    goto LABEL_37;
  }
  v13 = -2147418113;
  if ( v7 == -1 )
  {
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x557,
      (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
      v8);
    v13 = v14;
    if ( v14 > 0 )
      v13 = (unsigned __int16)v14 | 0x80070000;
  }
LABEL_38:
  v15 = VmMigrationTcpTransport::FlushPendingReceives(this, 0x7530u);
  v16 = v15;
  if ( v15 >= 0 )
  {
    if ( (unsigned __int8)_is_valid___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEBA_NXZ(&v33) )
    {
      if ( (_QWORD)v33 )
        v18 = *(wil::details **)v33;
      else
        v18 = 0;
      wil::details::SetEvent(v18, v17);
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 71) + 16LL))(*((_QWORD *)this + 71));
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x569,
      (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
      (const char *)(unsigned int)v15,
      v22);
    if ( v13 >= 0 )
      v13 = v16;
  }
  if ( a2 )
  {
    if ( v13 >= 0 )
      v26 = 0;
    else
      wil::details::lambda_call__lambda_ac9bedc8f8020e36458987a4993f965e___::reset(v25);
    v19 = std::future<long>::get(&v32);
    v20 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x58B,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        (const char *)(unsigned int)v19,
        v22);
      if ( v13 >= 0 )
        v13 = v20;
    }
  }
  wil::details::lambda_call__lambda_ac9bedc8f8020e36458987a4993f965e___::reset(v25);
  std::shared_ptr<IMigrationTransferTransportAdapterSource>::~shared_ptr<IMigrationTransferTransportAdapterSource>(&v34);
  std::shared_ptr<IMigrationTransferTransportAdapterSource>::~shared_ptr<IMigrationTransferTransportAdapterSource>(&v33);
  std::_State_manager<int>::~_State_manager<int>(&v32);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140080360  mov     [rsp+arg_8], rbx
0x140080365  mov     [rsp+arg_10], rsi
0x14008036a  push    rdi
0x14008036b  push    r14
0x14008036d  push    r15
0x14008036f  sub     rsp, 100h
0x140080376  mov     rax, cs:__security_cookie
0x14008037d  xor     rax, rsp
0x140080380  mov     [rsp+118h+var_20], rax
0x140080388  mov     r14, rdx
0x14008038b  mov     rdi, rcx
0x14008038e  mov     rcx, [rsp+118h]; this
0x140080396  cmp     qword ptr [rdi+208h], 0FFFFFFFFFFFFFFFFh
0x14008039e  jnz     short loc_1400803B7
0x1400803a0  mov     r9d, 8007139Fh; char *
0x1400803a6  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400803ad  mov     edx, 4EEh; void *
0x1400803b2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400803b7  mov     rcx, [rsp+118h]; this
0x1400803bf  xor     r15d, r15d
0x1400803c2  cmp     [rdi+228h], r15d
0x1400803c9  jnz     short loc_1400803E2
0x1400803cb  mov     r9d, 8007139Fh; char *
0x1400803d1  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400803d8  mov     edx, 4EFh; void *
0x1400803dd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400803e2  mov     rcx, [rsp+118h]; this
0x1400803ea  cmp     [rdi+240h], r15
0x1400803f1  jnz     short loc_14008040A
0x1400803f3  mov     r9d, 8007139Fh; char *
0x1400803f9  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x140080400  mov     edx, 4F0h; void *
0x140080405  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008040a  mov     rcx, [rsp+118h]; this
0x140080412  cmp     [rdi+238h], r15
0x140080419  jnz     short loc_140080432
0x14008041b  mov     r9d, 8007139Fh; char *
0x140080421  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x140080428  mov     edx, 4F1h; void *
0x14008042d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140080432  mov     rcx, [rsp+118h]; this
0x14008043a  cmp     [rdi+288h], r15
0x140080441  jnz     short loc_14008045A
0x140080443  mov     r9d, 8007139Fh; char *
0x140080449  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x140080450  mov     edx, 4FDh; void *
0x140080455  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008045a  mov     rcx, [rsp+118h]; this
0x140080462  cmp     [rdi+2D8h], r15
0x140080469  jnz     short loc_140080482
0x14008046b  mov     r9d, 8007139Fh; char *
0x140080471  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x140080478  mov     edx, 4FEh; void *
0x14008047d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140080482  mov     rcx, [rsp+118h]; this
0x14008048a  cmp     [rdi+248h], r15
0x140080491  jnz     short loc_1400804AA
0x140080493  mov     r9d, 8007139Fh; char *
0x140080499  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400804a0  mov     edx, 4FFh; void *
0x1400804a5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400804aa  xorps   xmm0, xmm0
0x1400804ad  movups  [rsp+118h+var_80], xmm0
0x1400804b5  mov     qword ptr [rsp+118h+var_80], r15
0x1400804bd  mov     byte ptr [rsp+118h+var_80+8], r15b
0x1400804c5  xorps   xmm1, xmm1
0x1400804c8  movdqu  [rsp+118h+var_70], xmm1
0x1400804d1  movdqu  [rsp+118h+var_60], xmm1
0x1400804da  lea     rax, [rsp+118h+var_80]
0x1400804e2  mov     [rsp+118h+var_D0], rax
0x1400804e7  lea     rax, [rsp+118h+var_60]
0x1400804ef  mov     [rsp+118h+var_C8], rax
0x1400804f4  mov     [rsp+118h+var_C0], 1
0x1400804f9  test    r14, r14
0x1400804fc  jz      loc_14008067B
0x140080502  mov     edx, 1
0x140080507  lea     rcx, [rsp+118h+var_70]
0x14008050f  call    ?create@?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140080514  mov     edx, 1
0x140080519  lea     rcx, [rsp+118h+var_60]
0x140080521  call    ?create@?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140080526  xorps   xmm0, xmm0
0x140080529  xor     eax, eax
0x14008052b  movups  [rsp+118h+var_50], xmm0
0x140080533  mov     [rsp+118h+var_40], rax
0x14008053b  lea     rax, ?SendDuplexRepliesDuringAsyncSequence@VmMigrationTcpTransport@@IEAAJPEAXV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@1@Z
0x140080542  mov     [rsp+118h+var_B8], rax
0x140080547  lea     rdx, [rsp+118h+var_60]
0x14008054f  lea     rcx, [rsp+118h+var_B0]
0x140080554  call    ??0?$shared_ptr@VIReplyProcessor@MuxMigrationReply@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<MuxMigrationReply::IReplyProcessor>::shared_ptr<MuxMigrationReply::IReplyProcessor>(std::shared_ptr<MuxMigrationReply::IReplyProcessor> const &)
0x140080559  lea     rdx, [rsp+118h+var_70]
0x140080561  lea     rcx, [rsp+118h+var_A0]
0x140080566  call    ??0?$shared_ptr@VIReplyProcessor@MuxMigrationReply@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<MuxMigrationReply::IReplyProcessor>::shared_ptr<MuxMigrationReply::IReplyProcessor>(std::shared_ptr<MuxMigrationReply::IReplyProcessor> const &)
0x14008056b  mov     [rsp+118h+var_90], r14
0x140080573  mov     [rsp+118h+var_88], rdi
0x14008057b  mov     esi, 110h
0x140080580  mov     ecx, esi; Size
0x140080582  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140080587  mov     rbx, rax
0x14008058a  mov     [rsp+118h+var_E8], rax
0x14008058f  mov     r8d, esi; Size
0x140080592  xor     edx, edx; Val
0x140080594  mov     rcx, rax; void *
0x140080597  call    memset_0
0x14008059c  mov     rcx, rbx
0x14008059f  call    ??0?$_Associated_state@J@std@@QEAA@PEAU?$_Deleter_base@J@1@@Z; std::_Associated_state<long>::_Associated_state<long>(std::_Deleter_base<long> *)
0x1400805a4  nop
0x1400805a5  lea     rax, ??_7?$_Packaged_state@$$A6AJXZ@std@@6B@; const std::_Packaged_state<long (void)>::`vftable'
0x1400805ac  mov     [rbx], rax
0x1400805af  lea     rsi, [rbx+0D0h]
0x1400805b6  mov     [rsp+118h+var_E0], rsi
0x1400805bb  mov     [rsi+38h], r15
0x1400805bf  lea     rcx, [rsp+118h+var_B8]
0x1400805c4  call    ??$_Global_new@V?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8VmMigrationTcpTransport@@EAAJPEAXV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@1@_EPEAV3@AEAPEAXAEAV45@AEAV45@@std@@J$$V@std@@V?$_Binder@U_Unforced@std@@P8VmMigrationTcpTransport@@EAAJPEAXV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@1@_EPEAV3@AEAPEAXAEAV45@AEAV45@@2@@std@@YAPEAV?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8VmMigrationTcpTransport@@EAAJPEAXV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@1@_EPEAV3@AEAPEAXAEAV45@AEAV45@@std@@J$$V@0@$$QEAV?$_Binder@U_Unforced@std@@P8VmMigrationTcpTransport@@EAAJPEAXV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@1@_EPEAV3@AEAPEAXAEAV45@AEAV45@@0@@Z
0x1400805c9  mov     [rsi+38h], rax
0x1400805cd  mov     qword ptr [rsp+118h+var_50], rbx
0x1400805d5  mov     byte ptr [rsp+118h+var_50+8], r15b
0x1400805dd  mov     byte ptr [rsp+118h+var_40], r15b
0x1400805e5  lea     rcx, [rsp+118h+var_B0]; void *
0x1400805ea  call    ??1?$tuple@V?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@V12@@std@@QEAA@XZ
0x1400805ef  lea     rdx, [rsp+118h+var_E0]
0x1400805f4  lea     rcx, [rsp+118h+var_50]
0x1400805fc  call    ?get_future@?$packaged_task@$$A6AJXZ@std@@QEAA?AV?$future@J@2@XZ; std::packaged_task<long (void)>::get_future(void)
0x140080601  mov     rbx, rax
0x140080604  lea     rax, [rsp+118h+var_80]
0x14008060c  cmp     rax, rbx
0x14008060f  jz      short loc_14008063B
0x140080611  mov     rcx, qword ptr [rsp+118h+var_80]
0x140080619  test    rcx, rcx
0x14008061c  jz      short loc_140080623
0x14008061e  call    ?_Release@?$_Associated_state@H@std@@QEAAXXZ; std::_Associated_state<int>::_Release(void)
0x140080623  mov     rax, [rbx]
0x140080626  mov     [rbx], r15
0x140080629  mov     qword ptr [rsp+118h+var_80], rax
0x140080631  mov     al, [rbx+8]
0x140080634  mov     byte ptr [rsp+118h+var_80+8], al
0x14008063b  lea     rcx, [rsp+118h+var_E0]
0x140080640  call    ??1?$_State_manager@H@std@@QEAA@XZ; std::_State_manager<int>::~_State_manager<int>(void)
0x140080645  lea     rdx, [rsp+118h+var_50]
0x14008064d  lea     rcx, [rsp+118h+var_E0]
0x140080652  call    ??$_Start@V?$packaged_task@$$A6AJXZ@std@@$$V@thread@std@@AEAAX$$QEAV?$packaged_task@$$A6AJXZ@1@@Z; std::thread::_Start<std::packaged_task<long (void)>,>(std::packaged_task<long (void)> &&)
0x140080657  nop
0x140080658  lea     rcx, [rsp+118h+var_E0]; this
0x14008065d  call    ?detach@thread@std@@QEAAXXZ; std::thread::detach(void)
0x140080662  nop
0x140080663  lea     rcx, [rsp+118h+var_E0]; this
0x140080668  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x14008066d  nop
0x14008066e  lea     rcx, [rsp+118h+var_50]
0x140080676  call    ??1?$packaged_task@$$A6AJV?$future@J@std@@0@Z@std@@QEAA@XZ; std::packaged_task<long (std::future<long>,std::future<long>)>::~packaged_task<long (std::future<long>,std::future<long>)>(void)
0x14008067b  mov     rax, [rdi+2D8h]
0x140080682  mov     [rsp+118h+Handles], rax
0x14008068a  mov     rax, [rdi+248h]
0x140080691  mov     [rsp+118h+var_30], rax
0x140080699  mov     rax, [rdi+288h]
0x1400806a0  mov     [rsp+118h+var_28], rax
0x1400806a8  mov     esi, 7530h
0x1400806ad  mov     r9d, esi; dwMilliseconds
0x1400806b0  xor     r8d, r8d; bWaitAll
0x1400806b3  lea     rdx, [rsp+118h+Handles]; lpHandles
0x1400806bb  lea     ecx, [r8+3]; nCount
0x1400806bf  call    cs:__imp_WaitForMultipleObjects
0x1400806c6  nop     dword ptr [rax+rax+00h]
0x1400806cb  test    eax, eax
0x1400806cd  jz      loc_1400807A6
0x1400806d3  cmp     eax, 1
0x1400806d6  jz      loc_14008077E
0x1400806dc  cmp     eax, 2
0x1400806df  jnz     short loc_140080732
0x1400806e1  mov     [rsp+118h+var_E8], r15
0x1400806e6  mov     rbx, [rsp+118h]
0x1400806ee  lea     rdx, [rsp+118h+var_E8]; struct VmMigrationTcpTransport::_TRANSPORT_BUFFER **
0x1400806f3  mov     rcx, rdi; this
0x1400806f6  call    ?LookupNextUnusedBuffer@VmMigrationTcpTransport@@IEAAHPEAPEAU_TRANSPORT_BUFFER@1@@Z; VmMigrationTcpTransport::LookupNextUnusedBuffer(VmMigrationTcpTransport::_TRANSPORT_BUFFER * *)
0x1400806fb  test    eax, eax
0x1400806fd  jz      short loc_14008071D
0x1400806ff  mov     rdx, [rsp+118h+var_E8]; struct VmMigrationTcpTransport::_TRANSPORT_BUFFER *
0x140080704  mov     rcx, rdi; this
0x140080707  call    ?PostReceiveBuffer@VmMigrationTcpTransport@@IEAAJPEAU_TRANSPORT_BUFFER@1@@Z; VmMigrationTcpTransport::PostReceiveBuffer(VmMigrationTcpTransport::_TRANSPORT_BUFFER *)
0x14008070c  test    eax, eax
0x14008070e  jns     short loc_1400806AD
0x140080710  mov     r9d, eax
0x140080713  mov     edx, 54Eh
0x140080718  jmp     loc_1400807B1
0x14008071d  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x140080724  mov     edx, 543h; void *
0x140080729  mov     rcx, rbx; this
0x14008072c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140080732  cmp     eax, 102h
0x140080737  jz      short loc_140080771
0x140080739  mov     ebx, 8000FFFFh
0x14008073e  cmp     eax, 0FFFFFFFFh
0x140080741  jnz     loc_1400807C7
0x140080747  mov     rcx, [rsp+118h]; this
0x14008074f  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x140080756  mov     edx, 557h; void *
0x14008075b  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x140080760  mov     ebx, eax
0x140080762  test    eax, eax
0x140080764  jle     short loc_1400807C7
0x140080766  movzx   ebx, ax
0x140080769  or      ebx, 80070000h
0x14008076f  jmp     short loc_1400807C7
0x140080771  mov     r9d, 800705B4h
0x140080777  mov     edx, 553h
0x14008077c  jmp     short loc_1400807B1
0x14008077e  mov     ebx, [rdi+250h]
0x140080784  mov     rcx, [rsp+118h]; this
0x14008078c  test    ebx, ebx
0x14008078e  jns     short loc_1400807C7
0x140080790  mov     r9d, ebx; char *
0x140080793  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x14008079a  mov     edx, 538h; void *
0x14008079f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400807a4  jmp     short loc_1400807C7
0x1400807a6  mov     r9d, 80004004h; char *
0x1400807ac  mov     edx, 531h; void *
0x1400807b1  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400807b8  mov     rcx, [rsp+118h]; this
0x1400807c0  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1400807c5  mov     ebx, eax
0x1400807c7  mov     edx, esi; unsigned int
0x1400807c9  mov     rcx, rdi; this
0x1400807cc  call    ?FlushPendingReceives@VmMigrationTcpTransport@@IEAAJK@Z; VmMigrationTcpTransport::FlushPendingReceives(ulong)
0x1400807d1  mov     esi, eax
0x1400807d3  mov     rcx, [rsp+118h]; this
0x1400807db  test    eax, eax
0x1400807dd  jns     short loc_1400807FB
0x1400807df  mov     r9d, eax; char *
0x1400807e2  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400807e9  mov     edx, 569h; void *
0x1400807ee  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400807f3  test    ebx, ebx
0x1400807f5  js      short loc_140080839
0x1400807f7  mov     ebx, esi
0x1400807f9  jmp     short loc_140080839
0x1400807fb  lea     rcx, [rsp+118h+var_70]
0x140080803  call    ?is_valid@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEBA_NXZ
0x140080808  test    al, al
0x14008080a  jz      short loc_140080826
0x14008080c  mov     rax, qword ptr [rsp+118h+var_70]
0x140080814  test    rax, rax
0x140080817  jz      short loc_14008081E
0x140080819  mov     rcx, [rax]
0x14008081c  jmp     short loc_140080821
0x14008081e  mov     rcx, r15; this
0x140080821  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x140080826  mov     rcx, [rdi+238h]
0x14008082d  mov     rax, [rcx]
0x140080830  mov     rax, [rax+10h]
0x140080834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140080839  test    r14, r14
0x14008083c  jz      short loc_140080887
0x14008083e  test    ebx, ebx
0x140080840  jns     short loc_14008084E
0x140080842  lea     rcx, [rsp+118h+var_D0]
0x140080847  call    wil__details__lambda_call__lambda_ac9bedc8f8020e36458987a4993f965e_____reset
0x14008084c  jmp     short loc_140080853
0x14008084e  mov     [rsp+118h+var_C0], r15b
0x140080853  lea     rcx, [rsp+118h+var_80]
0x14008085b  call    ?get@?$future@J@std@@QEAAJXZ; std::future<long>::get(void)
0x140080860  mov     edi, eax
0x140080862  mov     rcx, [rsp+118h]; this
0x14008086a  test    eax, eax
0x14008086c  jns     short loc_140080887
0x14008086e  mov     r9d, eax; char *
0x140080871  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x140080878  mov     edx, 58Bh; void *
0x14008087d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140080882  test    ebx, ebx
0x140080884  cmovns  ebx, edi
0x140080887  lea     rcx, [rsp+118h+var_D0]
0x14008088c  call    wil__details__lambda_call__lambda_ac9bedc8f8020e36458987a4993f965e_____reset
0x140080891  nop
0x140080892  lea     rcx, [rsp+118h+var_60]; void *
0x14008089a  call    ??1?$shared_ptr@VIMigrationTransferTransportAdapterSource@@@std@@QEAA@XZ; std::shared_ptr<IMigrationTransferTransportAdapterSource>::~shared_ptr<IMigrationTransferTransportAdapterSource>(void)
0x14008089f  nop
0x1400808a0  lea     rcx, [rsp+118h+var_70]; void *
0x1400808a8  call    ??1?$shared_ptr@VIMigrationTransferTransportAdapterSource@@@std@@QEAA@XZ; std::shared_ptr<IMigrationTransferTransportAdapterSource>::~shared_ptr<IMigrationTransferTransportAdapterSource>(void)
0x1400808ad  nop
0x1400808ae  lea     rcx, [rsp+118h+var_80]
0x1400808b6  call    ??1?$_State_manager@H@std@@QEAA@XZ; std::_State_manager<int>::~_State_manager<int>(void)
0x1400808bb  mov     eax, ebx
0x1400808bd  jmp     short loc_1400808C3
0x1400808bf  mov     eax, dword ptr [rsp+118h+var_E8]
0x1400808c3  mov     rcx, [rsp+118h+var_20]
0x1400808cb  xor     rcx, rsp; StackCookie
0x1400808ce  call    __security_check_cookie
0x1400808d3  lea     r11, [rsp+118h+var_18]
0x1400808db  mov     rbx, [r11+28h]
0x1400808df  mov     rsi, [r11+30h]
0x1400808e3  mov     rsp, r11
0x1400808e6  pop     r15
0x1400808e8  pop     r14
0x1400808ea  pop     rdi
0x1400808eb  retn
```
