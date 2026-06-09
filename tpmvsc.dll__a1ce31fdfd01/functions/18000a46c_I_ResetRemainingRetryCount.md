# I_ResetRemainingRetryCount

- ea: `0x18000a46c`
- end: `0x18000a815`
- name: `I_ResetRemainingRetryCount`
- size: `937`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007bcc`

## callees

- `0x18000115c`
- `0x180001ec0`
- `0x180002a90`
- `0x180006038`
- `0x1800065cc`
- `0x1800066ec`
- `0x180006858`
- `0x180007100`
- `0x18000794c`
- `0x18000a46c`
- `0x18000bc48`
- `0x18000c064`
- `0x18000c198`
- `0x1800123c4`
- `0x180012580`
- `0x18001280c`
- `0x1800128c4`
- `0x180013814`
- `0x1800348a0`

## string_xrefs

- `0x18000a6e4`: `Unable to update PIN map record`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall I_ResetRemainingRetryCount(__int64 a1, unsigned int a2)
{
  _DWORD *v2; // r9
  unsigned int v3; // ebx
  int InitialRetryCount; // ebx
  unsigned int v5; // ebx
  __int64 v6; // rcx
  unsigned int v8; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v9; // [rsp+48h] [rbp-B8h] BYREF
  int v10; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v11; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v12; // [rsp+58h] [rbp-A8h] BYREF
  int v13; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v14; // [rsp+64h] [rbp-9Ch] BYREF
  int v15; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v16; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v17; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v18; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v19[3]; // [rsp+88h] [rbp-78h] BYREF
  __int16 v20; // [rsp+A0h] [rbp-60h]
  _QWORD v21[3]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v22[5]; // [rsp+C0h] [rbp-40h] BYREF
  int v23; // [rsp+E8h] [rbp-18h] BYREF
  char v24; // [rsp+ECh] [rbp-14h]
  char v25[16]; // [rsp+F0h] [rbp-10h] BYREF
  _DWORD v26[4]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v27[88]; // [rsp+110h] [rbp+10h] BYREF
  int v28; // [rsp+168h] [rbp+68h]
  _BYTE v29[88]; // [rsp+170h] [rbp+70h] BYREF
  unsigned int v30; // [rsp+1C8h] [rbp+C8h]
  char v31[32]; // [rsp+1D0h] [rbp+D0h] BYREF

  v12 = a1;
  v9 = a2;
  v8 = 0;
  v10 = 0;
  v11 = 0;
  v13 = 0;
  strcpy(v31, "I_ResetRemainingRetryCount");
  v21[0] = v31;
  v21[1] = &v13;
  v21[2] = &v8;
  lambda_7a3b4007214c0065a9c35894c6942308_::operator()(v21);
  v13 = 1;
  v18 = v21;
  v23 = 0;
  v24 = 0;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart((__int64)&v23);
  if ( (unsigned int)dword_180048098 > 5 )
  {
    v14 = v11;
    v15 = v10;
    LODWORD(v16) = v9;
    LODWORD(v17) = v8;
    if ( v24 && (v26[0] || v26[1] || v26[2] || v26[3]) )
      v2 = v26;
    else
      v2 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)&dword_180048098,
      (__int64)byte_18003EE2B,
      (__int64)v25,
      (__int64)v2,
      (__int64)&v17,
      (__int64)&v16,
      (__int64)&v15,
      (__int64)&v14);
  }
  v22[0] = &v23;
  v22[1] = &v8;
  v22[2] = &v9;
  v22[3] = &v10;
  v22[4] = &v11;
  v16 = v22;
  if ( !v12 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v3 = v9;
  if ( v9 - 1 > 1 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v3 = v9;
  }
  memset_0(v27, 0, 0x5Cu);
  I_PinMapGetRecord(v12, v3, v27);
  v10 = v28;
  if ( !I_PinMapIsActive((const struct PIN_MAP_RECORD *)v27) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( I_PinMapIsBlocked((const struct PIN_MAP_RECORD *)v27) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( v28 < 0 )
    goto LABEL_35;
  InitialRetryCount = I_PinMapGetInitialRetryCount(v9);
  if ( InitialRetryCount <= 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( InitialRetryCount == v28 )
  {
LABEL_35:
    v8 = 0;
    goto LABEL_36;
  }
  memset_0(v29, 0, 0x5Cu);
  I_PinMapGetRecord(v12, v9, v29);
  v30 = InitialRetryCount;
  v8 = I_PinMapSetRecord(v12, v9, v29);
  v11 = v30;
  if ( v8 )
  {
    WppTraceIndent(v30, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
        (_DWORD)WPP_pszIndent,
        v8,
        (__int64)"Unable to update PIN map record");
    }
    v5 = v8;
    goto LABEL_37;
  }
  v19[0] = &v12;
  v19[1] = &v9;
  v19[2] = v27;
  v20 = 258;
  v17 = &v12;
  v8 = VCardTransact__lambda_218541274aab36691794216282319b30_(v30, &v17);
  if ( !v8 )
  {
    HIBYTE(v20) = 0;
    wil::details::ScopeExitFnGuard__lambda_f38f1c235d4bbfc7af7b18896877faaa___::operator()(v19);
LABEL_36:
    v5 = 0;
    goto LABEL_37;
  }
  WppTraceIndent(v6, 2u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sDs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      47,
      (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
      (_DWORD)WPP_pszIndent,
      v8,
      (__int64)"Updating PIN map failed");
  }
  v5 = v8;
  wil::details::ScopeExitFnGuard__lambda_f38f1c235d4bbfc7af7b18896877faaa___::operator()(v19);
LABEL_37:
  ScTraceUnwinder__lambda_2e014271ef1dde70694a50dccb011f90____::_ScTraceUnwinder__lambda_2e014271ef1dde70694a50dccb011f90____(&v16);
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>((__int64)&v23);
  WppTraceUnwinder__lambda_7a3b4007214c0065a9c35894c6942308____::_WppTraceUnwinder__lambda_7a3b4007214c0065a9c35894c6942308____(&v18);
  return v5;
}

```

## disassembly

```asm
0x18000a46c  mov     [rsp-8+arg_10], rbx
0x18000a471  mov     [rsp-8+arg_18], rdi
0x18000a476  push    rbp
0x18000a477  lea     rbp, [rsp-100h]
0x18000a47f  sub     rsp, 200h
0x18000a486  mov     rax, cs:__security_cookie
0x18000a48d  xor     rax, rsp
0x18000a490  mov     [rbp+100h+var_10], rax
0x18000a497  mov     [rsp+200h+var_1A8], rcx
0x18000a49c  mov     [rsp+200h+var_1B8], edx
0x18000a4a0  xor     edi, edi
0x18000a4a2  mov     [rsp+200h+var_1C0], edi
0x18000a4a6  mov     [rsp+200h+var_1B0], edi
0x18000a4aa  mov     [rsp+200h+var_1AC], edi
0x18000a4ae  mov     [rsp+200h+var_1A0], edi
0x18000a4b2  movups  xmm0, xmmword ptr cs:aIResetremainin; "I_ResetRemainingRetryCount"
0x18000a4b9  movups  xmmword ptr [rbp+100h+var_30], xmm0
0x18000a4c0  movups  xmm1, xmmword ptr cs:aIResetremainin+0Bh; "iningRetryCount"
0x18000a4c7  movups  xmmword ptr [rbp+100h+var_30+0Bh], xmm1
0x18000a4ce  lea     rax, [rbp+100h+var_30]
0x18000a4d5  mov     [rbp+100h+var_158], rax
0x18000a4d9  lea     rax, [rsp+200h+var_1A0]
0x18000a4de  mov     [rbp+100h+var_150], rax
0x18000a4e2  lea     rax, [rsp+200h+var_1C0]
0x18000a4e7  mov     [rbp+100h+var_148], rax
0x18000a4eb  lea     rcx, [rbp+100h+var_158]
0x18000a4ef  call    _lambda_7a3b4007214c0065a9c35894c6942308___operator__
0x18000a4f4  mov     [rsp+200h+var_1A0], 1
0x18000a4fc  lea     rax, [rbp+100h+var_158]
0x18000a500  mov     [rbp+100h+var_180], rax
0x18000a504  mov     [rbp+100h+var_118], edi
0x18000a507  mov     [rbp+100h+var_114], dil
0x18000a50b  lea     rcx, [rbp+100h+var_118]
0x18000a50f  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x18000a514  mov     eax, cs:dword_180048098
0x18000a51a  cmp     eax, 5
0x18000a51d  jbe     loc_18000A5A5
0x18000a523  mov     eax, [rsp+200h+var_1AC]
0x18000a527  mov     [rsp+200h+var_19C], eax
0x18000a52b  mov     eax, [rsp+200h+var_1B0]
0x18000a52f  mov     [rsp+200h+var_198], eax
0x18000a533  mov     eax, [rsp+200h+var_1B8]
0x18000a537  mov     dword ptr [rsp+200h+var_190], eax
0x18000a53b  mov     eax, [rsp+200h+var_1C0]
0x18000a53f  mov     dword ptr [rsp+200h+var_188], eax
0x18000a543  cmp     [rbp+100h+var_114], dil
0x18000a547  jz      short loc_18000A563
0x18000a549  cmp     [rbp+100h+var_100], edi
0x18000a54c  jnz     short loc_18000A55D
0x18000a54e  cmp     [rbp+100h+var_FC], edi
0x18000a551  jnz     short loc_18000A55D
0x18000a553  cmp     [rbp+100h+var_F8], edi
0x18000a556  jnz     short loc_18000A55D
0x18000a558  cmp     [rbp+100h+var_F4], edi
0x18000a55b  jz      short loc_18000A563
0x18000a55d  lea     r9, [rbp+100h+var_100]
0x18000a561  jmp     short loc_18000A566
0x18000a563  mov     r9, rdi
0x18000a566  lea     rax, [rsp+200h+var_19C]
0x18000a56b  mov     [rsp+200h+var_1C8], rax
0x18000a570  lea     rax, [rsp+200h+var_198]
0x18000a575  mov     [rsp+200h+var_1D0], rax
0x18000a57a  lea     rax, [rsp+200h+var_190]
0x18000a57f  mov     [rsp+200h+var_1D8], rax
0x18000a584  lea     rax, [rsp+200h+var_188]
0x18000a589  mov     [rsp+200h+var_1E0], rax
0x18000a58e  lea     r8, [rbp+100h+var_110]
0x18000a592  lea     rdx, byte_18003EE2B
0x18000a599  lea     rcx, dword_180048098
0x18000a5a0  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000a5a5  lea     rax, [rbp+100h+var_118]
0x18000a5a9  mov     [rbp+100h+var_140], rax
0x18000a5ad  lea     rax, [rsp+200h+var_1C0]
0x18000a5b2  mov     [rbp+100h+var_138], rax
0x18000a5b6  lea     rax, [rsp+200h+var_1B8]
0x18000a5bb  mov     [rbp+100h+var_130], rax
0x18000a5bf  lea     rax, [rsp+200h+var_1B0]
0x18000a5c4  mov     [rbp+100h+var_128], rax
0x18000a5c8  lea     rax, [rsp+200h+var_1AC]
0x18000a5cd  mov     [rbp+100h+var_120], rax
0x18000a5d1  lea     rax, [rbp+100h+var_140]
0x18000a5d5  mov     [rsp+200h+var_190], rax
0x18000a5da  cmp     [rsp+200h+var_1A8], rdi
0x18000a5df  jnz     short loc_18000A5E6
0x18000a5e1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a5e6  mov     ebx, [rsp+200h+var_1B8]
0x18000a5ea  lea     eax, [rbx-1]
0x18000a5ed  cmp     eax, 1
0x18000a5f0  jbe     short loc_18000A5FB
0x18000a5f2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a5f7  mov     ebx, [rsp+200h+var_1B8]
0x18000a5fb  xor     edx, edx; Val
0x18000a5fd  lea     r8d, [rdx+5Ch]; Size
0x18000a601  lea     rcx, [rbp+100h+var_F0]; void *
0x18000a605  call    memset_0
0x18000a60a  lea     r8, [rbp+100h+var_F0]
0x18000a60e  mov     edx, ebx
0x18000a610  mov     rcx, [rsp+200h+var_1A8]
0x18000a615  call    ?I_PinMapGetRecord@@YAXPEBUVCARD_DATA@@W4_CARD_ROLE@@PEAUPIN_MAP_RECORD@@@Z; I_PinMapGetRecord(VCARD_DATA const *,_CARD_ROLE,PIN_MAP_RECORD *)
0x18000a61a  mov     eax, [rbp+100h+var_98]
0x18000a61d  mov     [rsp+200h+var_1B0], eax
0x18000a621  lea     rcx, [rbp+100h+var_F0]; struct PIN_MAP_RECORD *
0x18000a625  call    ?I_PinMapIsActive@@YAHPEBUPIN_MAP_RECORD@@@Z; I_PinMapIsActive(PIN_MAP_RECORD const *)
0x18000a62a  test    eax, eax
0x18000a62c  jnz     short loc_18000A633
0x18000a62e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a633  lea     rcx, [rbp+100h+var_F0]; struct PIN_MAP_RECORD *
0x18000a637  call    ?I_PinMapIsBlocked@@YAHPEBUPIN_MAP_RECORD@@@Z; I_PinMapIsBlocked(PIN_MAP_RECORD const *)
0x18000a63c  test    eax, eax
0x18000a63e  jz      short loc_18000A645
0x18000a640  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a645  cmp     [rbp+100h+var_98], edi
0x18000a648  jl      loc_18000A7CB
0x18000a64e  mov     ecx, [rsp+200h+var_1B8]
0x18000a652  call    ?I_PinMapGetInitialRetryCount@@YAJW4_CARD_ROLE@@@Z; I_PinMapGetInitialRetryCount(_CARD_ROLE)
0x18000a657  mov     ebx, eax
0x18000a659  test    eax, eax
0x18000a65b  jg      short loc_18000A662
0x18000a65d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a662  cmp     ebx, [rbp+100h+var_98]
0x18000a665  jz      loc_18000A7CB
0x18000a66b  xor     edx, edx; Val
0x18000a66d  lea     r8d, [rdx+5Ch]; Size
0x18000a671  lea     rcx, [rbp+100h+var_90]; void *
0x18000a675  call    memset_0
0x18000a67a  lea     r8, [rbp+100h+var_90]
0x18000a67e  mov     edx, [rsp+200h+var_1B8]
0x18000a682  mov     rcx, [rsp+200h+var_1A8]
0x18000a687  call    ?I_PinMapGetRecord@@YAXPEBUVCARD_DATA@@W4_CARD_ROLE@@PEAUPIN_MAP_RECORD@@@Z; I_PinMapGetRecord(VCARD_DATA const *,_CARD_ROLE,PIN_MAP_RECORD *)
0x18000a68c  mov     [rbp+100h+var_38], ebx
0x18000a692  lea     r8, [rbp+100h+var_90]
0x18000a696  mov     edx, [rsp+200h+var_1B8]
0x18000a69a  mov     rcx, [rsp+200h+var_1A8]
0x18000a69f  call    ?I_PinMapSetRecord@@YAKPEBUVCARD_DATA@@W4_CARD_ROLE@@PEBUPIN_MAP_RECORD@@@Z; I_PinMapSetRecord(VCARD_DATA const *,_CARD_ROLE,PIN_MAP_RECORD const *)
0x18000a6a4  mov     [rsp+200h+var_1C0], eax
0x18000a6a8  mov     ecx, [rbp+100h+var_38]
0x18000a6ae  mov     [rsp+200h+var_1AC], ecx
0x18000a6b2  test    eax, eax
0x18000a6b4  jz      short loc_18000A718
0x18000a6b6  mov     edx, 2
0x18000a6bb  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000a6c0  lea     rax, WPP_GLOBAL_Control
0x18000a6c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6ce  cmp     rcx, rax
0x18000a6d1  jz      short loc_18000A70F
0x18000a6d3  test    byte ptr [rcx+1Ch], 1
0x18000a6d7  jz      short loc_18000A70F
0x18000a6d9  cmp     byte ptr [rcx+19h], 2
0x18000a6dd  jb      short loc_18000A70F
0x18000a6df  mov     edx, 2Dh ; '-'
0x18000a6e4  lea     rax, aUnableToUpdate; "Unable to update PIN map record"
0x18000a6eb  mov     [rsp+200h+var_1D8], rax
0x18000a6f0  mov     eax, [rsp+200h+var_1C0]
0x18000a6f4  mov     dword ptr [rsp+200h+var_1E0], eax
0x18000a6f8  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000a6ff  lea     r8, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids
0x18000a706  mov     rcx, [rcx+10h]
0x18000a70a  call    WPP_SF_sDs
0x18000a70f  mov     ebx, [rsp+200h+var_1C0]
0x18000a713  jmp     loc_18000A7D1
0x18000a718  lea     rax, [rsp+200h+var_1A8]
0x18000a71d  mov     [rbp+100h+var_178], rax
0x18000a721  lea     rax, [rsp+200h+var_1B8]
0x18000a726  mov     [rbp+100h+var_170], rax
0x18000a72a  lea     rax, [rbp+100h+var_F0]
0x18000a72e  mov     [rbp+100h+var_168], rax
0x18000a732  mov     [rbp+100h+var_160], 102h
0x18000a738  lea     rax, [rsp+200h+var_1A8]
0x18000a73d  mov     [rsp+200h+var_188], rax
0x18000a742  lea     rdx, [rsp+200h+var_188]
0x18000a747  call    VCardTransact__lambda_218541274aab36691794216282319b30___; VCardTransact__lambda_218541274aab36691794216282319b30_
0x18000a74c  mov     [rsp+200h+var_1C0], eax
0x18000a750  test    eax, eax
0x18000a752  jz      short loc_18000A7BC
0x18000a754  mov     edx, 2
0x18000a759  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000a75e  lea     rax, WPP_GLOBAL_Control
0x18000a765  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a76c  cmp     rcx, rax
0x18000a76f  jz      short loc_18000A7AD
0x18000a771  test    byte ptr [rcx+1Ch], 1
0x18000a775  jz      short loc_18000A7AD
0x18000a777  cmp     byte ptr [rcx+19h], 2
0x18000a77b  jb      short loc_18000A7AD
0x18000a77d  mov     edx, 2Fh ; '/'
0x18000a782  lea     rax, aUpdatingPinMap; "Updating PIN map failed"
0x18000a789  mov     [rsp+200h+var_1D8], rax
0x18000a78e  mov     eax, [rsp+200h+var_1C0]
0x18000a792  mov     dword ptr [rsp+200h+var_1E0], eax
0x18000a796  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000a79d  lea     r8, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids
0x18000a7a4  mov     rcx, [rcx+10h]
0x18000a7a8  call    WPP_SF_sDs
0x18000a7ad  mov     ebx, [rsp+200h+var_1C0]
0x18000a7b1  lea     rcx, [rbp+100h+var_178]
0x18000a7b5  call    wil__details__ScopeExitFnGuard__lambda_f38f1c235d4bbfc7af7b18896877faaa_____operator__
0x18000a7ba  jmp     short loc_18000A7D1
0x18000a7bc  mov     byte ptr [rbp+100h+var_160+1], dil
0x18000a7c0  lea     rcx, [rbp+100h+var_178]
0x18000a7c4  call    wil__details__ScopeExitFnGuard__lambda_f38f1c235d4bbfc7af7b18896877faaa_____operator__
0x18000a7c9  jmp     short loc_18000A7CF
0x18000a7cb  mov     [rsp+200h+var_1C0], edi
0x18000a7cf  mov     ebx, edi
0x18000a7d1  lea     rcx, [rsp+200h+var_190]
0x18000a7d6  call    ScTraceUnwinder__lambda_2e014271ef1dde70694a50dccb011f90_______ScTraceUnwinder__lambda_2e014271ef1dde70694a50dccb011f90____
0x18000a7db  nop
0x18000a7dc  lea     rcx, [rbp+100h+var_118]
0x18000a7e0  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18000a7e5  nop
0x18000a7e6  lea     rcx, [rbp+100h+var_180]
0x18000a7ea  call    WppTraceUnwinder__lambda_7a3b4007214c0065a9c35894c6942308_______WppTraceUnwinder__lambda_7a3b4007214c0065a9c35894c6942308____
0x18000a7ef  mov     eax, ebx
0x18000a7f1  mov     rcx, [rbp+100h+var_10]
0x18000a7f8  xor     rcx, rsp; StackCookie
0x18000a7fb  call    __security_check_cookie
0x18000a800  lea     r11, [rsp+200h+var_s0]
0x18000a808  mov     rbx, [r11+20h]
0x18000a80c  mov     rdi, [r11+28h]
0x18000a810  mov     rsp, r11
0x18000a813  pop     rbp
0x18000a814  retn
```
