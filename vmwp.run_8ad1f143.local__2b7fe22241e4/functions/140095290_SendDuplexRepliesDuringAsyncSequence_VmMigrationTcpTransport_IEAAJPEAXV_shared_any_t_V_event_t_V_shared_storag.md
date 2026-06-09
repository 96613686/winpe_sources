# ?SendDuplexRepliesDuringAsyncSequence@VmMigrationTcpTransport@@IEAAJPEAXV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@1@Z

- ea: `0x140095290`
- end: `0x140095907`
- name: `?SendDuplexRepliesDuringAsyncSequence@VmMigrationTcpTransport@@IEAAJPEAXV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@1@Z`
- size: `1655`
- prototype: `__int64 __fastcall(VmMigrationTcpTransport *this)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14006af58`
- `0x14007e5a0`
- `0x14007f46c`
- `0x1400950e0`
- `0x1400951b0`
- `0x140095290`
- `0x140095d8c`
- `0x140096ad4`
- `0x1400988f0`
- `0x14009fa0c`
- `0x1400c5a3c`
- `0x140132960`
- `0x140184d70`
- `0x1401dd548`
- `0x1401dfccc`
- `0x1401e0f38`
- `0x1401e116c`
- `0x1402c2010`

## string_xrefs

- `0x1400952e4`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14009530f`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14009533d`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14009536b`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14009539e`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400953cc`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140095518`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140095580`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14009559f`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140095605`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140095633`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140095668`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400956d5`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140095767`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400957ab`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400957ec`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14009580c`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140095852`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140095871`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140095890`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400958af`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`

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
0x140095290  push    rbx
0x140095292  push    rsi
0x140095293  push    rdi
0x140095294  push    r12
0x140095296  push    r13
0x140095298  push    r14
0x14009529a  push    r15
0x14009529c  sub     rsp, 110h
0x1400952a3  mov     rax, cs:__security_cookie
0x1400952aa  xor     rax, rsp
0x1400952ad  mov     [rsp+148h+var_40], rax
0x1400952b5  mov     rsi, r9
0x1400952b8  mov     r14, r8
0x1400952bb  mov     r11, rdx
0x1400952be  mov     rbx, rcx
0x1400952c1  mov     [rsp+148h+var_B0], r8
0x1400952c9  mov     [rsp+148h+var_A8], r9
0x1400952d1  mov     rcx, [rsp+148h]; this
0x1400952d9  test    rdx, rdx
0x1400952dc  jnz     short loc_1400952F5
0x1400952de  mov     r9d, 80070057h; char *
0x1400952e4  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400952eb  mov     edx, 425h; void *
0x1400952f0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400952f5  mov     r10, [rsp+148h]
0x1400952fd  mov     rcx, r14
0x140095300  call    ?is_valid@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEBA_NXZ
0x140095305  test    al, al
0x140095307  jnz     short loc_140095323
0x140095309  mov     r9d, 80070057h; char *
0x14009530f  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140095316  mov     edx, 426h; void *
0x14009531b  mov     rcx, r10; this
0x14009531e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140095323  mov     r10, [rsp+148h]
0x14009532b  mov     rcx, rsi
0x14009532e  call    ?is_valid@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEBA_NXZ
0x140095333  test    al, al
0x140095335  jnz     short loc_140095351
0x140095337  mov     r9d, 80070057h; char *
0x14009533d  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140095344  mov     edx, 427h; void *
0x140095349  mov     rcx, r10; this
0x14009534c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140095351  mov     rcx, [rbx+2D8h]
0x140095358  mov     rax, [rsp+148h]
0x140095360  test    rcx, rcx
0x140095363  jnz     short loc_14009537F
0x140095365  mov     r9d, 8007139Fh; char *
0x14009536b  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140095372  mov     edx, 429h; void *
0x140095377  mov     rcx, rax; this
0x14009537a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009537f  mov     r8, [rbx+320h]
0x140095386  test    r8, r8
0x140095389  setz    al
0x14009538c  mov     r10, [rsp+148h]
0x140095394  test    al, al
0x140095396  jz      short loc_1400953B2
0x140095398  mov     r9d, 8007139Fh; char *
0x14009539e  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400953a5  mov     edx, 42Ah; void *
0x1400953aa  mov     rcx, r10; this
0x1400953ad  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400953b2  mov     r9, [rbx+288h]
0x1400953b9  mov     rax, [rsp+148h]
0x1400953c1  test    r9, r9
0x1400953c4  jnz     short loc_1400953E0
0x1400953c6  mov     r9d, 8007139Fh; char *
0x1400953cc  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400953d3  mov     edx, 42Bh; void *
0x1400953d8  mov     rcx, rax; this
0x1400953db  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400953e0  mov     [rsp+148h+var_70], rcx
0x1400953e8  mov     rax, [rsi]
0x1400953eb  test    rax, rax
0x1400953ee  jz      short loc_1400953F5
0x1400953f0  mov     rdx, [rax]
0x1400953f3  jmp     short loc_1400953F7
0x1400953f5  xor     edx, edx
0x1400953f7  mov     [rsp+148h+var_68], rdx
0x1400953ff  mov     rdx, [r14]
0x140095402  test    rdx, rdx
0x140095405  jz      short loc_14009540A
0x140095407  mov     rdx, [rdx]
0x14009540a  mov     [rsp+148h+var_60], rdx
0x140095412  mov     [rsp+148h+var_58], r8
0x14009541a  mov     [rsp+148h+var_A0], rcx
0x140095422  test    rax, rax
0x140095425  jz      short loc_14009542C
0x140095427  mov     rdx, [rax]
0x14009542a  jmp     short loc_14009542E
0x14009542c  xor     edx, edx; bool
0x14009542e  mov     [rsp+148h+var_98], rdx
0x140095436  mov     [rsp+148h+var_90], r9
0x14009543e  mov     [rsp+148h+var_88], rcx
0x140095446  test    rax, rax
0x140095449  jz      short loc_140095450
0x14009544b  mov     rcx, [rax]
0x14009544e  jmp     short loc_140095452
0x140095450  xor     ecx, ecx
0x140095452  mov     [rsp+148h+var_80], rcx
0x14009545a  mov     [rsp+148h+var_78], r11
0x140095462  xor     r12b, r12b
0x140095465  xor     dil, dil
0x140095468  xor     r15b, r15b
0x14009546b  xorps   xmm0, xmm0
0x14009546e  movups  [rsp+148h+var_50], xmm0
0x140095476  lea     rcx, [rsp+148h+var_50]; this
0x14009547e  call    ??0VmMigrationSettings@@QEAA@_N@Z; VmMigrationSettings::VmMigrationSettings(bool)
0x140095483  nop
0x140095484  mov     [rsp+148h+var_B8], 0
0x140095490  xorps   xmm0, xmm0
0x140095493  xor     eax, eax
0x140095495  movups  [rsp+148h+var_108], xmm0
0x14009549a  mov     [rsp+148h+var_F8], rax
0x14009549f  mov     qword ptr [rsp+148h+var_108], rbx
0x1400954a4  lea     r13, [rsp+148h+var_B8]
0x1400954ac  mov     qword ptr [rsp+148h+var_108+8], r13
0x1400954b1  mov     byte ptr [rsp+148h+var_F8], 1
0x1400954b6  test    r12b, r12b
0x1400954b9  jnz     loc_1400955B0
0x1400954bf  call    ?GetMigrationMessageDefaultTimeout@VmMigrationSettings@@QEBAIXZ; VmMigrationSettings::GetMigrationMessageDefaultTimeout(void)
0x1400954c4  mov     [rsp+148h+var_E8], 4
0x1400954cd  lea     rcx, [rsp+148h+var_70]
0x1400954d5  mov     [rsp+148h+var_E0], rcx
0x1400954da  mov     edx, eax
0x1400954dc  lea     rcx, [rsp+148h+var_E8]
0x1400954e1  call    WaitUntilAnObjectIsSet
0x1400954e6  mov     rcx, rax
0x1400954e9  test    rax, rax
0x1400954ec  jz      loc_140095591
0x1400954f2  sub     rcx, 1
0x1400954f6  jz      short loc_140095572
0x1400954f8  sub     rcx, 1
0x1400954fc  jz      short loc_14009553F
0x1400954fe  cmp     rcx, 1
0x140095502  jz      short loc_14009552A
0x140095504  mov     rcx, [rsp+148h]; this
0x14009550c  mov     [rsp+148h+var_128], rax; char *
0x140095511  lea     r9, aIndexofsetobje; "indexOfSetObject: %zu."
0x140095518  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x14009551f  mov     edx, 47Ch; void *
0x140095524  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
0x14009552a  mov     rcx, rbx; this
0x14009552d  call    ?TakeReservedDuplexReplyBufferOwnership@VmMigrationTcpTransport@@IEAAPEAU_TRANSPORT_BUFFER@1@XZ; VmMigrationTcpTransport::TakeReservedDuplexReplyBufferOwnership(void)
0x140095532  mov     [rsp+148h+var_B8], rax
0x14009553a  jmp     loc_140095650
0x14009553f  mov     r12b, 1
0x140095542  mov     rcx, rbx; this
0x140095545  call    ?UnreserveTransportBufferForDuplexReplies@VmMigrationTcpTransport@@IEAAXXZ; VmMigrationTcpTransport::UnreserveTransportBufferForDuplexReplies(void)
0x14009554a  mov     r15b, r12b
0x14009554d  mov     rdx, [rsp+148h+var_B8]
0x140095555  test    rdx, rdx
0x140095558  jz      short loc_14009556D
0x14009555a  mov     rax, [rbx]
0x14009555d  mov     rcx, rbx
0x140095560  mov     rax, [rax+1C0h]
0x140095567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009556c  nop
0x14009556d  jmp     loc_140095733
0x140095572  mov     rcx, [rsp+148h]; this
0x14009557a  mov     r9d, 80004005h; char *
0x140095580  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140095587  mov     edx, 464h; void *
0x14009558c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140095591  mov     rcx, [rsp+148h]; this
0x140095599  mov     r9d, 80004004h; char *
0x14009559f  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400955a6  mov     edx, 45Fh; void *
0x1400955ab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400955b0  mov     [rsp+148h+var_D8], 3
0x1400955b9  lea     rax, [rsp+148h+var_A0]
0x1400955c1  mov     [rsp+148h+var_D0], rax
0x1400955c6  mov     edx, 7530h
0x1400955cb  lea     rcx, [rsp+148h+var_D8]
0x1400955d0  call    WaitUntilAnObjectIsSet
0x1400955d5  mov     rcx, rax
0x1400955d8  test    rax, rax
0x1400955db  jz      loc_1400958A1
0x1400955e1  sub     rcx, 1
0x1400955e5  jz      loc_140095882
0x1400955eb  cmp     rcx, 1
0x1400955ef  jz      short loc_140095617
0x1400955f1  mov     rcx, [rsp+148h]; this
0x1400955f9  mov     [rsp+148h+var_128], rax; char *
0x1400955fe  lea     r9, aIndexofsetobje; "indexOfSetObject: %zu."
0x140095605  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x14009560c  mov     edx, 498h; void *
0x140095611  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
0x140095617  mov     rdi, [rsp+148h]
0x14009561f  lea     rdx, [rsp+148h+var_B8]; struct VmMigrationTcpTransport::_TRANSPORT_BUFFER **
0x140095627  mov     rcx, rbx; this
0x14009562a  call    ?LookupNextUnusedBuffer@VmMigrationTcpTransport@@IEAAHPEAPEAU_TRANSPORT_BUFFER@1@@Z; VmMigrationTcpTransport::LookupNextUnusedBuffer(VmMigrationTcpTransport::_TRANSPORT_BUFFER * *)
0x14009562f  test    eax, eax
0x140095631  jnz     short loc_140095648
0x140095633  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x14009563a  mov     edx, 494h; void *
0x14009563f  mov     rcx, rdi; this
0x140095642  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140095648  mov     rax, [rsp+148h+var_B8]
0x140095650  test    rax, rax
0x140095653  setz    al
0x140095656  mov     rcx, [rsp+148h]; this
0x14009565e  test    al, al
0x140095660  jz      short loc_140095679
0x140095662  mov     r9d, 8007054Fh; char *
0x140095668  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x14009566f  mov     edx, 4A5h; void *
0x140095674  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140095679  mov     [rsp+148h+var_C8], 3
0x140095685  lea     rax, [rsp+148h+var_88]
0x14009568d  mov     [rsp+148h+var_C0], rax
0x140095695  or      edx, 0FFFFFFFFh
0x140095698  lea     rcx, [rsp+148h+var_C8]
0x1400956a0  call    WaitUntilAnObjectIsSet
0x1400956a5  mov     rcx, rax
0x1400956a8  test    rax, rax
0x1400956ab  jz      loc_140095863
0x1400956b1  sub     rcx, 1
0x1400956b5  jz      loc_140095844
0x1400956bb  cmp     rcx, 1
0x1400956bf  jz      short loc_1400956E7
0x1400956c1  mov     rcx, [rsp+148h]; this
0x1400956c9  mov     [rsp+148h+var_128], rax; char *
0x1400956ce  lea     r9, aIndexofsetobje; "indexOfSetObject: %zu."
0x1400956d5  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400956dc  mov     edx, 4BEh; void *
0x1400956e1  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
0x1400956e7  lea     rdx, [rsp+148h+var_B8]; struct VmMigrationTcpTransport::_TRANSPORT_BUFFER **
0x1400956ef  mov     rcx, rbx; this
0x1400956f2  call    ?OfferReplyBuffer@VmMigrationTcpTransport@@IEAA_NPEAPEAU_TRANSPORT_BUFFER@1@@Z; VmMigrationTcpTransport::OfferReplyBuffer(VmMigrationTcpTransport::_TRANSPORT_BUFFER * *)
0x1400956f7  mov     dil, al
0x1400956fa  mov     rax, [rsp+148h+var_B8]
0x140095702  test    rax, rax
0x140095705  jz      short loc_140095710
0x140095707  test    dil, dil
0x14009570a  jz      loc_140095650
0x140095710  mov     rdx, [r13+0]
0x140095714  test    rdx, rdx
0x140095717  jz      short loc_140095733
0x140095719  mov     rax, [rbx]
0x14009571c  mov     rcx, rbx
0x14009571f  mov     rax, [rax+1C0h]
0x140095726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009572b  mov     qword ptr [r13+0], 0
0x140095733  test    dil, dil
0x140095736  jz      loc_140095484
0x14009573c  test    r15b, r15b
0x14009573f  jnz     short loc_140095749
0x140095741  mov     rcx, rbx; this
0x140095744  call    ?UnreserveTransportBufferForDuplexReplies@VmMigrationTcpTransport@@IEAAXXZ; VmMigrationTcpTransport::UnreserveTransportBufferForDuplexReplies(void)
0x140095749  mov     edx, 7530h; unsigned int
0x14009574e  mov     rcx, rbx; this
0x140095751  call    ?FlushPendingSends@VmMigrationTcpTransport@@IEAAJK@Z; VmMigrationTcpTransport::FlushPendingSends(ulong)
0x140095756  mov     edx, eax
0x140095758  mov     rcx, [rsp+148h]; this
0x140095760  test    eax, eax
0x140095762  jns     short loc_140095778
0x140095764  mov     r9d, eax; char *
0x140095767  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x14009576e  mov     edx, 4CEh; void *
0x140095773  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140095778  test    edx, edx
0x14009577a  jz      loc_14009581E
0x140095780  cmp     edx, 48041h
0x140095786  setnz   al
0x140095789  mov     rcx, [rsp+148h]; this
0x140095791  mov     dword ptr [rsp+148h+var_118], edx; char *
0x140095795  lea     rdx, aFlushpendingse; "flushPendingSendsResult: 0x%08X."
0x14009579c  mov     qword ptr [rsp+148h+var_120], rdx; bool
0x1400957a1  mov     byte ptr [rsp+148h+var_128], al; char
0x1400957a5  mov     r9d, 8007054Fh; char *
0x1400957ab  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400957b2  mov     edx, 4D4h; void *
0x1400957b7  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1400957bc  mov     eax, [rbx+22Ch]
0x1400957c2  mov     edx, eax
0x1400957c4  shr     edx, 1Fh
0x1400957c7  xor     dl, 1
0x1400957ca  mov     rcx, [rsp+148h]; this
0x1400957d2  mov     dword ptr [rsp+148h+var_118], eax; char *
0x1400957d6  lea     rax, aMOverlappedsen; "m_OverlappedSendResult: 0x%08X."
0x1400957dd  mov     qword ptr [rsp+148h+var_120], rax; bool
0x1400957e2  mov     byte ptr [rsp+148h+var_128], dl; int
0x1400957e6  mov     r9d, 8007054Fh; char *
0x1400957ec  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400957f3  mov     edx, 4D8h; void *
0x1400957f8  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1400957fd  mov     rcx, [rsp+148h]; this
0x140095805  mov     r9d, [rbx+22Ch]; char *
0x14009580c  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140095813  mov     edx, 4DAh; void *
0x140095818  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009581e  lea     rcx, [rsp+148h+var_50+8]; this
0x140095826  call    ?Close@VmRegistryKey@Vml@@QEAAXXZ; Vml::VmRegistryKey::Close(void)
0x14009582b  nop
0x14009582c  mov     rcx, r14; void *
0x14009582f  call    ??1?$shared_ptr@VIMigrationTransferTransportAdapterSource@@@std@@QEAA@XZ; std::shared_ptr<IMigrationTransferTransportAdapterSource>::~shared_ptr<IMigrationTransferTransportAdapterSource>(void)
0x140095834  nop
  ... truncated ...
```
