# ?SendDuplexRepliesDuringAsyncSequence@VmMigrationTcpTransport@@IEAAJPEAXV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@1@Z

- ea: `0x14007ec20`
- end: `0x14007f297`
- name: `?SendDuplexRepliesDuringAsyncSequence@VmMigrationTcpTransport@@IEAAJPEAXV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@1@Z`
- size: `1655`
- prototype: `__int64 __fastcall(VmMigrationTcpTransport *this)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400644a0`
- `0x140064f4c`
- `0x140066eec`
- `0x140078628`
- `0x14007ea68`
- `0x14007eb38`
- `0x14007ec20`
- `0x14007f2a0`
- `0x14007f764`
- `0x14008ff18`
- `0x14009061c`
- `0x14011ea40`
- `0x140171f80`
- `0x1401cca58`
- `0x1401cf37c`
- `0x1401d05e8`
- `0x1401d081c`
- `0x1402cb010`

## string_xrefs

- `0x14007ec74`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14007ec9f`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14007eccd`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14007ecfb`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14007ed2e`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14007ed5c`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14007eea8`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14007ef10`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14007ef2f`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14007ef95`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14007efc3`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14007eff8`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14007f065`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14007f0f7`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14007f13b`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14007f17c`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14007f19c`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14007f1e2`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14007f201`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14007f220`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14007f23f`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall VmMigrationTcpTransport::SendDuplexRepliesDuringAsyncSequence(
        VmMigrationTcpTransport *this,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4)
{
  wil::details::in1diag3 *v7; // r10
  wil::details::in1diag3 *v8; // r10
  __int64 v9; // r11
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 *v13; // rax
  __int64 v14; // rdx
  _QWORD *v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rcx
  char v18; // r12
  bool v19; // di
  char v20; // r15
  VmMigrationSettings *v21; // rcx
  unsigned int MigrationMessageDefaultTimeout; // eax
  const char *v23; // rax
  struct VmMigrationTcpTransport::_TRANSPORT_BUFFER *v24; // rax
  const char *IsSet; // rax
  const char *v26; // r9
  const char *v27; // rax
  int v28; // eax
  const char *v29; // r9
  __int64 result; // rax
  int v31; // [rsp+20h] [rbp-128h]
  int v32; // [rsp+20h] [rbp-128h]
  char *v33; // [rsp+30h] [rbp-118h]
  char *v34; // [rsp+30h] [rbp-118h]
  _QWORD v35[2]; // [rsp+60h] [rbp-E8h] BYREF
  _QWORD v36[2]; // [rsp+70h] [rbp-D8h] BYREF
  _QWORD v37[2]; // [rsp+80h] [rbp-C8h] BYREF
  struct VmMigrationTcpTransport::_TRANSPORT_BUFFER *v38; // [rsp+90h] [rbp-B8h] BYREF
  void *v39; // [rsp+98h] [rbp-B0h]
  void *v40; // [rsp+A0h] [rbp-A8h]
  _QWORD v41[3]; // [rsp+A8h] [rbp-A0h] BYREF
  _QWORD v42[3]; // [rsp+C0h] [rbp-88h] BYREF
  _QWORD v43[4]; // [rsp+D8h] [rbp-70h] BYREF
  __int128 v44; // [rsp+F8h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  try
  {
    v39 = a3;
    v40 = a4;
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x425,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        (const char *)0x80070057LL,
        v31);
    if ( !(unsigned __int8)_is_valid___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEBA_NXZ(a3) )
      wil::details::in1diag3::Throw_Hr(
        v7,
        (void *)0x426,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        (const char *)0x80070057LL,
        v31);
    if ( !(unsigned __int8)_is_valid___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEBA_NXZ(a4) )
      wil::details::in1diag3::Throw_Hr(
        v8,
        (void *)0x427,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        (const char *)0x80070057LL,
        v31);
    v10 = *((_QWORD *)this + 91);
    if ( !v10 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x429,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        (const char *)0x8007139FLL,
        v31);
    v11 = *((_QWORD *)this + 100);
    if ( !v11 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x42A,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        (const char *)0x8007139FLL,
        v31);
    v12 = *((_QWORD *)this + 81);
    if ( !v12 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x42B,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        (const char *)0x8007139FLL,
        v31);
    v43[0] = *((_QWORD *)this + 91);
    v13 = (__int64 *)*a4;
    if ( *a4 )
      v14 = *v13;
    else
      v14 = 0;
    v43[1] = v14;
    v15 = (_QWORD *)*a3;
    if ( *a3 )
      v15 = (_QWORD *)*v15;
    v43[2] = v15;
    v43[3] = v11;
    v41[0] = v10;
    if ( v13 )
      v16 = *v13;
    else
      v16 = 0;
    v41[1] = v16;
    v41[2] = v12;
    v42[0] = v10;
    if ( v13 )
      v17 = *v13;
    else
      v17 = 0;
    v42[1] = v17;
    v42[2] = v9;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v44 = 0;
    VmMigrationSettings::VmMigrationSettings((VmMigrationSettings *)&v44, v16);
    while ( 1 )
    {
      v38 = 0;
      if ( v18 )
      {
        v36[0] = 3;
        v36[1] = v41;
        IsSet = (const char *)WaitUntilAnObjectIsSet(v36, 30000);
        if ( !IsSet )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x489,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            (const char *)0x80004004LL,
            v31);
        if ( IsSet == (const char *)1 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x48E,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            (const char *)0x80004005LL,
            v31);
        if ( IsSet != (const char *)2 )
          wil::details::in1diag3::FailFast_UnexpectedMsg(
            retaddr,
            (void *)0x498,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            "indexOfSetObject: %zu.",
            IsSet);
        if ( !(unsigned int)VmMigrationTcpTransport::LookupNextUnusedBuffer(this, &v38) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x494,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            v26);
        v24 = v38;
      }
      else
      {
        MigrationMessageDefaultTimeout = VmMigrationSettings::GetMigrationMessageDefaultTimeout(v21);
        v35[0] = 4;
        v35[1] = v43;
        v23 = (const char *)WaitUntilAnObjectIsSet(v35, MigrationMessageDefaultTimeout);
        if ( !v23 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x45F,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            (const char *)0x80004004LL,
            v31);
        if ( v23 == (const char *)1 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x464,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            (const char *)0x80004005LL,
            v31);
        if ( v23 == (const char *)2 )
        {
          v18 = 1;
          VmMigrationTcpTransport::UnreserveTransportBufferForDuplexReplies(this);
          v20 = 1;
          if ( v38 )
            (*(void (__fastcall **)(VmMigrationTcpTransport *))(*(_QWORD *)this + 448LL))(this);
          goto LABEL_55;
        }
        if ( v23 != (const char *)3 )
          wil::details::in1diag3::FailFast_UnexpectedMsg(
            retaddr,
            (void *)0x47C,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            "indexOfSetObject: %zu.",
            v23);
        v24 = VmMigrationTcpTransport::TakeReservedDuplexReplyBufferOwnership(this);
        v38 = v24;
      }
      do
      {
        if ( !v24 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x4A5,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            (const char *)0x8007054FLL,
            v31);
        v37[0] = 3;
        v37[1] = v42;
        v27 = (const char *)WaitUntilAnObjectIsSet(v37, 0xFFFFFFFFLL);
        if ( !v27 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x4AF,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            (const char *)0x80004004LL,
            v31);
        if ( v27 == (const char *)1 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x4B4,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            (const char *)0x80004005LL,
            v31);
        if ( v27 != (const char *)2 )
          wil::details::in1diag3::FailFast_UnexpectedMsg(
            retaddr,
            (void *)0x4BE,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            "indexOfSetObject: %zu.",
            v27);
        v19 = VmMigrationTcpTransport::OfferReplyBuffer(this, &v38);
        v24 = v38;
      }
      while ( v38 && !v19 );
      if ( v38 )
      {
        (*(void (__fastcall **)(VmMigrationTcpTransport *))(*(_QWORD *)this + 448LL))(this);
        v38 = 0;
      }
LABEL_55:
      if ( v19 )
      {
        if ( !v20 )
          VmMigrationTcpTransport::UnreserveTransportBufferForDuplexReplies(this);
        v28 = VmMigrationTcpTransport::FlushPendingSends(this, 0x7530u);
        if ( v28 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x4CE,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            (const char *)(unsigned int)v28,
            v31);
        if ( v28 )
        {
          LODWORD(v33) = v28;
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0x4D4,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            (const char *)0x8007054FLL,
            v28 != 294977,
            (bool)"flushPendingSendsResult: 0x%08X.",
            v33);
          LODWORD(v34) = *((_DWORD *)this + 139);
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0x4D8,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            (const char *)0x8007054FLL,
            (int)v34 >= 0,
            (bool)"m_OverlappedSendResult: 0x%08X.",
            v34);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x4DA,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            (const char *)*((unsigned int *)this + 139),
            v32);
        }
        Vml::VmRegistryKey::Close((Vml::VmRegistryKey *)((char *)&v44 + 8));
        std::shared_ptr<IMigrationTransferTransportAdapterSource>::~shared_ptr<IMigrationTransferTransportAdapterSource>(a3);
        std::shared_ptr<IMigrationTransferTransportAdapterSource>::~shared_ptr<IMigrationTransferTransportAdapterSource>(a4);
        return 0;
      }
    }
  }
  catch ( ... )
  {
    LODWORD(v38) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x4DF,
                     (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
                     v29);
    std::shared_ptr<IMigrationTransferTransportAdapterSource>::~shared_ptr<IMigrationTransferTransportAdapterSource>(v39);
    std::shared_ptr<IMigrationTransferTransportAdapterSource>::~shared_ptr<IMigrationTransferTransportAdapterSource>(v40);
    return (unsigned int)v38;
  }
  return result;
}

```

## disassembly

```asm
0x14007ec20  push    rbx
0x14007ec22  push    rsi
0x14007ec23  push    rdi
0x14007ec24  push    r12
0x14007ec26  push    r13
0x14007ec28  push    r14
0x14007ec2a  push    r15
0x14007ec2c  sub     rsp, 110h
0x14007ec33  mov     rax, cs:__security_cookie
0x14007ec3a  xor     rax, rsp
0x14007ec3d  mov     [rsp+148h+var_40], rax
0x14007ec45  mov     rsi, r9
0x14007ec48  mov     r14, r8
0x14007ec4b  mov     r11, rdx
0x14007ec4e  mov     rbx, rcx
0x14007ec51  mov     [rsp+148h+var_B0], r8
0x14007ec59  mov     [rsp+148h+var_A8], r9
0x14007ec61  mov     rcx, [rsp+148h]; this
0x14007ec69  test    rdx, rdx
0x14007ec6c  jnz     short loc_14007EC85
0x14007ec6e  mov     r9d, 80070057h; char *
0x14007ec74  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x14007ec7b  mov     edx, 425h; void *
0x14007ec80  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007ec85  mov     r10, [rsp+148h]
0x14007ec8d  mov     rcx, r14
0x14007ec90  call    ?is_valid@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEBA_NXZ
0x14007ec95  test    al, al
0x14007ec97  jnz     short loc_14007ECB3
0x14007ec99  mov     r9d, 80070057h; char *
0x14007ec9f  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x14007eca6  mov     edx, 426h; void *
0x14007ecab  mov     rcx, r10; this
0x14007ecae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007ecb3  mov     r10, [rsp+148h]
0x14007ecbb  mov     rcx, rsi
0x14007ecbe  call    ?is_valid@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEBA_NXZ
0x14007ecc3  test    al, al
0x14007ecc5  jnz     short loc_14007ECE1
0x14007ecc7  mov     r9d, 80070057h; char *
0x14007eccd  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x14007ecd4  mov     edx, 427h; void *
0x14007ecd9  mov     rcx, r10; this
0x14007ecdc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007ece1  mov     rcx, [rbx+2D8h]
0x14007ece8  mov     rax, [rsp+148h]
0x14007ecf0  test    rcx, rcx
0x14007ecf3  jnz     short loc_14007ED0F
0x14007ecf5  mov     r9d, 8007139Fh; char *
0x14007ecfb  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x14007ed02  mov     edx, 429h; void *
0x14007ed07  mov     rcx, rax; this
0x14007ed0a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007ed0f  mov     r8, [rbx+320h]
0x14007ed16  test    r8, r8
0x14007ed19  setz    al
0x14007ed1c  mov     r10, [rsp+148h]
0x14007ed24  test    al, al
0x14007ed26  jz      short loc_14007ED42
0x14007ed28  mov     r9d, 8007139Fh; char *
0x14007ed2e  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x14007ed35  mov     edx, 42Ah; void *
0x14007ed3a  mov     rcx, r10; this
0x14007ed3d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007ed42  mov     r9, [rbx+288h]
0x14007ed49  mov     rax, [rsp+148h]
0x14007ed51  test    r9, r9
0x14007ed54  jnz     short loc_14007ED70
0x14007ed56  mov     r9d, 8007139Fh; char *
0x14007ed5c  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x14007ed63  mov     edx, 42Bh; void *
0x14007ed68  mov     rcx, rax; this
0x14007ed6b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007ed70  mov     [rsp+148h+var_70], rcx
0x14007ed78  mov     rax, [rsi]
0x14007ed7b  test    rax, rax
0x14007ed7e  jz      short loc_14007ED85
0x14007ed80  mov     rdx, [rax]
0x14007ed83  jmp     short loc_14007ED87
0x14007ed85  xor     edx, edx
0x14007ed87  mov     [rsp+148h+var_68], rdx
0x14007ed8f  mov     rdx, [r14]
0x14007ed92  test    rdx, rdx
0x14007ed95  jz      short loc_14007ED9A
0x14007ed97  mov     rdx, [rdx]
0x14007ed9a  mov     [rsp+148h+var_60], rdx
0x14007eda2  mov     [rsp+148h+var_58], r8
0x14007edaa  mov     [rsp+148h+var_A0], rcx
0x14007edb2  test    rax, rax
0x14007edb5  jz      short loc_14007EDBC
0x14007edb7  mov     rdx, [rax]
0x14007edba  jmp     short loc_14007EDBE
0x14007edbc  xor     edx, edx; bool
0x14007edbe  mov     [rsp+148h+var_98], rdx
0x14007edc6  mov     [rsp+148h+var_90], r9
0x14007edce  mov     [rsp+148h+var_88], rcx
0x14007edd6  test    rax, rax
0x14007edd9  jz      short loc_14007EDE0
0x14007eddb  mov     rcx, [rax]
0x14007edde  jmp     short loc_14007EDE2
0x14007ede0  xor     ecx, ecx
0x14007ede2  mov     [rsp+148h+var_80], rcx
0x14007edea  mov     [rsp+148h+var_78], r11
0x14007edf2  xor     r12b, r12b
0x14007edf5  xor     dil, dil
0x14007edf8  xor     r15b, r15b
0x14007edfb  xorps   xmm0, xmm0
0x14007edfe  movups  [rsp+148h+var_50], xmm0
0x14007ee06  lea     rcx, [rsp+148h+var_50]; this
0x14007ee0e  call    ??0VmMigrationSettings@@QEAA@_N@Z; VmMigrationSettings::VmMigrationSettings(bool)
0x14007ee13  nop
0x14007ee14  mov     [rsp+148h+var_B8], 0
0x14007ee20  xorps   xmm0, xmm0
0x14007ee23  xor     eax, eax
0x14007ee25  movups  [rsp+148h+var_108], xmm0
0x14007ee2a  mov     [rsp+148h+var_F8], rax
0x14007ee2f  mov     qword ptr [rsp+148h+var_108], rbx
0x14007ee34  lea     r13, [rsp+148h+var_B8]
0x14007ee3c  mov     qword ptr [rsp+148h+var_108+8], r13
0x14007ee41  mov     byte ptr [rsp+148h+var_F8], 1
0x14007ee46  test    r12b, r12b
0x14007ee49  jnz     loc_14007EF40
0x14007ee4f  call    ?GetMigrationMessageDefaultTimeout@VmMigrationSettings@@QEBAIXZ; VmMigrationSettings::GetMigrationMessageDefaultTimeout(void)
0x14007ee54  mov     [rsp+148h+var_E8], 4
0x14007ee5d  lea     rcx, [rsp+148h+var_70]
0x14007ee65  mov     [rsp+148h+var_E0], rcx
0x14007ee6a  mov     edx, eax
0x14007ee6c  lea     rcx, [rsp+148h+var_E8]
0x14007ee71  call    WaitUntilAnObjectIsSet
0x14007ee76  mov     rcx, rax
0x14007ee79  test    rax, rax
0x14007ee7c  jz      loc_14007EF21
0x14007ee82  sub     rcx, 1
0x14007ee86  jz      short loc_14007EF02
0x14007ee88  sub     rcx, 1
0x14007ee8c  jz      short loc_14007EECF
0x14007ee8e  cmp     rcx, 1
0x14007ee92  jz      short loc_14007EEBA
0x14007ee94  mov     rcx, [rsp+148h]; this
0x14007ee9c  mov     [rsp+148h+var_128], rax; char *
0x14007eea1  lea     r9, aIndexofsetobje; "indexOfSetObject: %zu."
0x14007eea8  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x14007eeaf  mov     edx, 47Ch; void *
0x14007eeb4  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
0x14007eeba  mov     rcx, rbx; this
0x14007eebd  call    ?TakeReservedDuplexReplyBufferOwnership@VmMigrationTcpTransport@@IEAAPEAU_TRANSPORT_BUFFER@1@XZ; VmMigrationTcpTransport::TakeReservedDuplexReplyBufferOwnership(void)
0x14007eec2  mov     [rsp+148h+var_B8], rax
0x14007eeca  jmp     loc_14007EFE0
0x14007eecf  mov     r12b, 1
0x14007eed2  mov     rcx, rbx; this
0x14007eed5  call    ?UnreserveTransportBufferForDuplexReplies@VmMigrationTcpTransport@@IEAAXXZ; VmMigrationTcpTransport::UnreserveTransportBufferForDuplexReplies(void)
0x14007eeda  mov     r15b, r12b
0x14007eedd  mov     rdx, [rsp+148h+var_B8]
0x14007eee5  test    rdx, rdx
0x14007eee8  jz      short loc_14007EEFD
0x14007eeea  mov     rax, [rbx]
0x14007eeed  mov     rcx, rbx
0x14007eef0  mov     rax, [rax+1C0h]
0x14007eef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007eefc  nop
0x14007eefd  jmp     loc_14007F0C3
0x14007ef02  mov     rcx, [rsp+148h]; this
0x14007ef0a  mov     r9d, 80004005h; char *
0x14007ef10  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x14007ef17  mov     edx, 464h; void *
0x14007ef1c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007ef21  mov     rcx, [rsp+148h]; this
0x14007ef29  mov     r9d, 80004004h; char *
0x14007ef2f  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x14007ef36  mov     edx, 45Fh; void *
0x14007ef3b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007ef40  mov     [rsp+148h+var_D8], 3
0x14007ef49  lea     rax, [rsp+148h+var_A0]
0x14007ef51  mov     [rsp+148h+var_D0], rax
0x14007ef56  mov     edx, 7530h
0x14007ef5b  lea     rcx, [rsp+148h+var_D8]
0x14007ef60  call    WaitUntilAnObjectIsSet
0x14007ef65  mov     rcx, rax
0x14007ef68  test    rax, rax
0x14007ef6b  jz      loc_14007F231
0x14007ef71  sub     rcx, 1
0x14007ef75  jz      loc_14007F212
0x14007ef7b  cmp     rcx, 1
0x14007ef7f  jz      short loc_14007EFA7
0x14007ef81  mov     rcx, [rsp+148h]; this
0x14007ef89  mov     [rsp+148h+var_128], rax; char *
0x14007ef8e  lea     r9, aIndexofsetobje; "indexOfSetObject: %zu."
0x14007ef95  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x14007ef9c  mov     edx, 498h; void *
0x14007efa1  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
0x14007efa7  mov     rdi, [rsp+148h]
0x14007efaf  lea     rdx, [rsp+148h+var_B8]; struct VmMigrationTcpTransport::_TRANSPORT_BUFFER **
0x14007efb7  mov     rcx, rbx; this
0x14007efba  call    ?LookupNextUnusedBuffer@VmMigrationTcpTransport@@IEAAHPEAPEAU_TRANSPORT_BUFFER@1@@Z; VmMigrationTcpTransport::LookupNextUnusedBuffer(VmMigrationTcpTransport::_TRANSPORT_BUFFER * *)
0x14007efbf  test    eax, eax
0x14007efc1  jnz     short loc_14007EFD8
0x14007efc3  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x14007efca  mov     edx, 494h; void *
0x14007efcf  mov     rcx, rdi; this
0x14007efd2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14007efd8  mov     rax, [rsp+148h+var_B8]
0x14007efe0  test    rax, rax
0x14007efe3  setz    al
0x14007efe6  mov     rcx, [rsp+148h]; this
0x14007efee  test    al, al
0x14007eff0  jz      short loc_14007F009
0x14007eff2  mov     r9d, 8007054Fh; char *
0x14007eff8  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x14007efff  mov     edx, 4A5h; void *
0x14007f004  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007f009  mov     [rsp+148h+var_C8], 3
0x14007f015  lea     rax, [rsp+148h+var_88]
0x14007f01d  mov     [rsp+148h+var_C0], rax
0x14007f025  or      edx, 0FFFFFFFFh
0x14007f028  lea     rcx, [rsp+148h+var_C8]
0x14007f030  call    WaitUntilAnObjectIsSet
0x14007f035  mov     rcx, rax
0x14007f038  test    rax, rax
0x14007f03b  jz      loc_14007F1F3
0x14007f041  sub     rcx, 1
0x14007f045  jz      loc_14007F1D4
0x14007f04b  cmp     rcx, 1
0x14007f04f  jz      short loc_14007F077
0x14007f051  mov     rcx, [rsp+148h]; this
0x14007f059  mov     [rsp+148h+var_128], rax; char *
0x14007f05e  lea     r9, aIndexofsetobje; "indexOfSetObject: %zu."
0x14007f065  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x14007f06c  mov     edx, 4BEh; void *
0x14007f071  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
0x14007f077  lea     rdx, [rsp+148h+var_B8]; struct VmMigrationTcpTransport::_TRANSPORT_BUFFER **
0x14007f07f  mov     rcx, rbx; this
0x14007f082  call    ?OfferReplyBuffer@VmMigrationTcpTransport@@IEAA_NPEAPEAU_TRANSPORT_BUFFER@1@@Z; VmMigrationTcpTransport::OfferReplyBuffer(VmMigrationTcpTransport::_TRANSPORT_BUFFER * *)
0x14007f087  mov     dil, al
0x14007f08a  mov     rax, [rsp+148h+var_B8]
0x14007f092  test    rax, rax
0x14007f095  jz      short loc_14007F0A0
0x14007f097  test    dil, dil
0x14007f09a  jz      loc_14007EFE0
0x14007f0a0  mov     rdx, [r13+0]
0x14007f0a4  test    rdx, rdx
0x14007f0a7  jz      short loc_14007F0C3
0x14007f0a9  mov     rax, [rbx]
0x14007f0ac  mov     rcx, rbx
0x14007f0af  mov     rax, [rax+1C0h]
0x14007f0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007f0bb  mov     qword ptr [r13+0], 0
0x14007f0c3  test    dil, dil
0x14007f0c6  jz      loc_14007EE14
0x14007f0cc  test    r15b, r15b
0x14007f0cf  jnz     short loc_14007F0D9
0x14007f0d1  mov     rcx, rbx; this
0x14007f0d4  call    ?UnreserveTransportBufferForDuplexReplies@VmMigrationTcpTransport@@IEAAXXZ; VmMigrationTcpTransport::UnreserveTransportBufferForDuplexReplies(void)
0x14007f0d9  mov     edx, 7530h; unsigned int
0x14007f0de  mov     rcx, rbx; this
0x14007f0e1  call    ?FlushPendingSends@VmMigrationTcpTransport@@IEAAJK@Z; VmMigrationTcpTransport::FlushPendingSends(ulong)
0x14007f0e6  mov     edx, eax
0x14007f0e8  mov     rcx, [rsp+148h]; this
0x14007f0f0  test    eax, eax
0x14007f0f2  jns     short loc_14007F108
0x14007f0f4  mov     r9d, eax; char *
0x14007f0f7  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x14007f0fe  mov     edx, 4CEh; void *
0x14007f103  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007f108  test    edx, edx
0x14007f10a  jz      loc_14007F1AE
0x14007f110  cmp     edx, 48041h
0x14007f116  setnz   al
0x14007f119  mov     rcx, [rsp+148h]; this
0x14007f121  mov     dword ptr [rsp+148h+var_118], edx; char *
0x14007f125  lea     rdx, aFlushpendingse; "flushPendingSendsResult: 0x%08X."
0x14007f12c  mov     qword ptr [rsp+148h+var_120], rdx; bool
0x14007f131  mov     byte ptr [rsp+148h+var_128], al; char
0x14007f135  mov     r9d, 8007054Fh; char *
0x14007f13b  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x14007f142  mov     edx, 4D4h; void *
0x14007f147  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x14007f14c  mov     eax, [rbx+22Ch]
0x14007f152  mov     edx, eax
0x14007f154  shr     edx, 1Fh
0x14007f157  xor     dl, 1
0x14007f15a  mov     rcx, [rsp+148h]; this
0x14007f162  mov     dword ptr [rsp+148h+var_118], eax; char *
0x14007f166  lea     rax, aMOverlappedsen; "m_OverlappedSendResult: 0x%08X."
0x14007f16d  mov     qword ptr [rsp+148h+var_120], rax; bool
0x14007f172  mov     byte ptr [rsp+148h+var_128], dl; int
0x14007f176  mov     r9d, 8007054Fh; char *
0x14007f17c  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x14007f183  mov     edx, 4D8h; void *
0x14007f188  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x14007f18d  mov     rcx, [rsp+148h]; this
0x14007f195  mov     r9d, [rbx+22Ch]; char *
0x14007f19c  lea     r8, aOnecoreVmCommo_43; "onecore\\vm\\common\\migration\\vmmigra"...
0x14007f1a3  mov     edx, 4DAh; void *
0x14007f1a8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007f1ae  lea     rcx, [rsp+148h+var_50+8]; this
0x14007f1b6  call    ?Close@VmRegistryKey@Vml@@QEAAXXZ; Vml::VmRegistryKey::Close(void)
0x14007f1bb  nop
0x14007f1bc  mov     rcx, r14; void *
0x14007f1bf  call    ??1?$shared_ptr@VIMigrationTransferTransportAdapterSource@@@std@@QEAA@XZ; std::shared_ptr<IMigrationTransferTransportAdapterSource>::~shared_ptr<IMigrationTransferTransportAdapterSource>(void)
0x14007f1c4  nop
  ... truncated ...
```
