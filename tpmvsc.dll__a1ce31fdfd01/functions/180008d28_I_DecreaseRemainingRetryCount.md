# I_DecreaseRemainingRetryCount

- ea: `0x180008d28`
- end: `0x18000914c`
- name: `I_DecreaseRemainingRetryCount`
- size: `1060`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007bcc`
- `0x1800085b8`

## callees

- `0x1800010f8`
- `0x18000115c`
- `0x1800011ec`
- `0x180001ec0`
- `0x180002a90`
- `0x1800065e4`
- `0x1800066d0`
- `0x180006858`
- `0x180006dc0`
- `0x180006f48`
- `0x18000794c`
- `0x180008d28`
- `0x18000bc48`
- `0x18000c064`
- `0x18000c198`
- `0x180012580`
- `0x18001280c`
- `0x1800128c4`
- `0x180013814`
- `0x1800201f0`
- `0x1800348a0`

## string_xrefs

- `0x180008ffb`: `Unable to update PIN map record`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall I_DecreaseRemainingRetryCount(struct VCARD_DATA *a1, unsigned int a2)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  _DWORD *v4; // r9
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rcx
  unsigned int v18; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v19; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v21; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v22; // [rsp+58h] [rbp-A8h] BYREF
  struct VCARD_DATA *v23; // [rsp+60h] [rbp-A0h] BYREF
  int v24; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v25; // [rsp+6Ch] [rbp-94h] BYREF
  int v26; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v27; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v28; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v29[3]; // [rsp+88h] [rbp-78h] BYREF
  __int16 v30; // [rsp+A0h] [rbp-60h]
  _QWORD v31[3]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v32[3]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v33[5]; // [rsp+D8h] [rbp-28h] BYREF
  int v34; // [rsp+100h] [rbp+0h] BYREF
  char v35; // [rsp+104h] [rbp+4h]
  char v36[16]; // [rsp+108h] [rbp+8h] BYREF
  _DWORD v37[6]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v38[88]; // [rsp+130h] [rbp+30h] BYREF
  unsigned int v39; // [rsp+188h] [rbp+88h]
  unsigned __int16 v40[44]; // [rsp+190h] [rbp+90h] BYREF
  int v41; // [rsp+1E8h] [rbp+E8h]
  char v42[32]; // [rsp+1F0h] [rbp+F0h] BYREF

  v23 = a1;
  v19 = a2;
  v18 = 0;
  v20 = 0;
  v21 = 0;
  v24 = 0;
  strcpy(v42, "I_DecreaseRemainingRetryCount");
  v31[0] = v42;
  v31[1] = &v24;
  v31[2] = &v18;
  lambda_5b1f020a0bcd8f3494dc24fabf843cea_::operator()(v31);
  v24 = 1;
  v28 = v31;
  v34 = 0;
  v35 = 0;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart((__int64)&v34);
  if ( (unsigned int)dword_180048098 > 5 )
  {
    v25 = v21;
    v26 = v20;
    LODWORD(v27) = v19;
    v22 = v18;
    if ( v35 && (v37[0] || v37[1] || v37[2] || v37[3]) )
      v4 = v37;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)&dword_180048098,
      (__int64)byte_18003ED41,
      (__int64)v36,
      (__int64)v4,
      (__int64)&v22,
      (__int64)&v27,
      (__int64)&v26,
      (__int64)&v25);
  }
  v33[0] = &v34;
  v33[1] = &v18;
  v33[2] = &v19;
  v33[3] = &v20;
  v33[4] = &v21;
  v27 = v33;
  if ( !v23 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v3, v2);
  v5 = v19;
  if ( v19 - 1 > 1 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v3, v2);
    v5 = v19;
  }
  memset_0(v40, 0, 0x5Cu);
  I_PinMapGetRecord((__int64)v23, v5, v40);
  v20 = v41;
  if ( !I_PinMapIsActive((const struct PIN_MAP_RECORD *)v40) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7, v6);
  if ( I_PinMapIsBlocked((const struct PIN_MAP_RECORD *)v40) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  if ( v41 >= 0 )
  {
    memset_0(v38, 0, 0x5Cu);
    I_PinMapGetRecord((__int64)v23, v19, v38);
    --v39;
    if ( I_PinMapIsBlocked((const struct PIN_MAP_RECORD *)v38) )
    {
      memset_0(v38, 0, 0x50u);
      if ( (unsigned int)dword_180048098 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_180048098, 0x200000000000LL, v11, v12) )
        {
          v22 = v19;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            v13,
            (__int64)byte_18003ED1D,
            v14,
            v15,
            (__int64)&v22);
        }
      }
    }
    v18 = I_PinMapSetRecord(v23, v19, v38);
    v21 = v39;
    if ( v18 )
    {
      WppTraceIndent(v39, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sDs(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          49,
          (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
          (_DWORD)WPP_pszIndent,
          v18,
          (__int64)"Unable to update PIN map record");
      }
      v10 = v18;
    }
    else
    {
      v29[0] = &v23;
      v29[1] = &v19;
      v29[2] = v40;
      v30 = 258;
      v32[0] = &v23;
      v32[1] = &v19;
      v32[2] = v38;
      v18 = lambda_4151db1353c7c1ea51d3518dbed218c3_::operator()(v32);
      if ( v18 )
      {
        WppTraceIndent(v16, 2u);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sDs(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            52,
            (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
            (_DWORD)WPP_pszIndent,
            v18,
            (__int64)"Updating PIN map failed");
        }
      }
      else
      {
        HIBYTE(v30) = 0;
        if ( I_PinMapIsBlocked((const struct PIN_MAP_RECORD *)v38) )
          I_DeleteKspKey(v23, v40);
      }
      v10 = v18;
      wil::details::ScopeExitFnGuard__lambda_f38f1c235d4bbfc7af7b18896877faaa___::operator()(v29);
    }
  }
  else
  {
    v18 = 0;
    v10 = 0;
  }
  ScTraceUnwinder__lambda_627c111035fb335143fe45036d0c4a7d____::_ScTraceUnwinder__lambda_627c111035fb335143fe45036d0c4a7d____(&v27);
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>((__int64)&v34);
  WppTraceUnwinder__lambda_5b1f020a0bcd8f3494dc24fabf843cea____::_WppTraceUnwinder__lambda_5b1f020a0bcd8f3494dc24fabf843cea____(&v28);
  return v10;
}

```

## disassembly

```asm
0x180008d28  mov     [rsp-8+arg_10], rbx
0x180008d2d  mov     [rsp-8+arg_18], rdi
0x180008d32  push    rbp
0x180008d33  lea     rbp, [rsp-120h]
0x180008d3b  sub     rsp, 220h
0x180008d42  mov     rax, cs:__security_cookie
0x180008d49  xor     rax, rsp
0x180008d4c  mov     [rbp+120h+var_10], rax
0x180008d53  mov     [rsp+220h+var_1C0], rcx
0x180008d58  mov     [rsp+220h+var_1D8], edx
0x180008d5c  xor     edi, edi
0x180008d5e  mov     [rsp+220h+var_1E0], edi
0x180008d62  mov     [rsp+220h+var_1D0], edi
0x180008d66  mov     [rsp+220h+var_1CC], edi
0x180008d6a  mov     [rsp+220h+var_1B8], edi
0x180008d6e  movups  xmm0, xmmword ptr cs:aIDecreaseremai; "I_DecreaseRemainingRetryCount"
0x180008d75  movups  xmmword ptr [rbp+120h+var_30], xmm0
0x180008d7c  movups  xmm1, xmmword ptr cs:aIDecreaseremai+0Eh; "iningRetryCount"
0x180008d83  movups  xmmword ptr [rbp+120h+var_30+0Eh], xmm1
0x180008d8a  lea     rax, [rbp+120h+var_30]
0x180008d91  mov     [rbp+120h+var_178], rax
0x180008d95  lea     rax, [rsp+220h+var_1B8]
0x180008d9a  mov     [rbp+120h+var_170], rax
0x180008d9e  lea     rax, [rsp+220h+var_1E0]
0x180008da3  mov     [rbp+120h+var_168], rax
0x180008da7  lea     rcx, [rbp+120h+var_178]
0x180008dab  call    _lambda_5b1f020a0bcd8f3494dc24fabf843cea___operator__
0x180008db0  mov     [rsp+220h+var_1B8], 1
0x180008db8  lea     rax, [rbp+120h+var_178]
0x180008dbc  mov     [rbp+120h+var_1A0], rax
0x180008dc0  mov     [rbp+120h+var_120], edi
0x180008dc3  mov     [rbp+120h+var_11C], dil
0x180008dc7  lea     rcx, [rbp+120h+var_120]
0x180008dcb  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x180008dd0  mov     eax, cs:dword_180048098
0x180008dd6  cmp     eax, 5
0x180008dd9  jbe     loc_180008E61
0x180008ddf  mov     eax, [rsp+220h+var_1CC]
0x180008de3  mov     [rsp+220h+var_1B4], eax
0x180008de7  mov     eax, [rsp+220h+var_1D0]
0x180008deb  mov     [rsp+220h+var_1B0], eax
0x180008def  mov     eax, [rsp+220h+var_1D8]
0x180008df3  mov     dword ptr [rsp+220h+var_1A8], eax
0x180008df7  mov     eax, [rsp+220h+var_1E0]
0x180008dfb  mov     [rsp+220h+var_1C8], eax
0x180008dff  cmp     [rbp+120h+var_11C], dil
0x180008e03  jz      short loc_180008E1F
0x180008e05  cmp     [rbp+120h+var_108], edi
0x180008e08  jnz     short loc_180008E19
0x180008e0a  cmp     [rbp+120h+var_104], edi
0x180008e0d  jnz     short loc_180008E19
0x180008e0f  cmp     [rbp+120h+var_100], edi
0x180008e12  jnz     short loc_180008E19
0x180008e14  cmp     [rbp+120h+var_FC], edi
0x180008e17  jz      short loc_180008E1F
0x180008e19  lea     r9, [rbp+120h+var_108]
0x180008e1d  jmp     short loc_180008E22
0x180008e1f  mov     r9, rdi
0x180008e22  lea     rax, [rsp+220h+var_1B4]
0x180008e27  mov     [rsp+220h+var_1E8], rax
0x180008e2c  lea     rax, [rsp+220h+var_1B0]
0x180008e31  mov     [rsp+220h+var_1F0], rax
0x180008e36  lea     rax, [rsp+220h+var_1A8]
0x180008e3b  mov     [rsp+220h+var_1F8], rax
0x180008e40  lea     rax, [rsp+220h+var_1C8]
0x180008e45  mov     [rsp+220h+var_200], rax
0x180008e4a  lea     r8, [rbp+120h+var_118]
0x180008e4e  lea     rdx, byte_18003ED41
0x180008e55  lea     rcx, dword_180048098
0x180008e5c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180008e61  lea     rax, [rbp+120h+var_120]
0x180008e65  mov     [rbp+120h+var_148], rax
0x180008e69  lea     rax, [rsp+220h+var_1E0]
0x180008e6e  mov     [rbp+120h+var_140], rax
0x180008e72  lea     rax, [rsp+220h+var_1D8]
0x180008e77  mov     [rbp+120h+var_138], rax
0x180008e7b  lea     rax, [rsp+220h+var_1D0]
0x180008e80  mov     [rbp+120h+var_130], rax
0x180008e84  lea     rax, [rsp+220h+var_1CC]
0x180008e89  mov     [rbp+120h+var_128], rax
0x180008e8d  lea     rax, [rbp+120h+var_148]
0x180008e91  mov     [rsp+220h+var_1A8], rax
0x180008e96  cmp     [rsp+220h+var_1C0], rdi
0x180008e9b  jnz     short loc_180008EA2
0x180008e9d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008ea2  mov     ebx, [rsp+220h+var_1D8]
0x180008ea6  lea     eax, [rbx-1]
0x180008ea9  cmp     eax, 1
0x180008eac  jbe     short loc_180008EB7
0x180008eae  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008eb3  mov     ebx, [rsp+220h+var_1D8]
0x180008eb7  xor     edx, edx; Val
0x180008eb9  lea     r8d, [rdx+5Ch]; Size
0x180008ebd  lea     rcx, [rbp+120h+var_90]; void *
0x180008ec4  call    memset_0
0x180008ec9  lea     r8, [rbp+120h+var_90]
0x180008ed0  mov     edx, ebx
0x180008ed2  mov     rcx, [rsp+220h+var_1C0]
0x180008ed7  call    ?I_PinMapGetRecord@@YAXPEBUVCARD_DATA@@W4_CARD_ROLE@@PEAUPIN_MAP_RECORD@@@Z; I_PinMapGetRecord(VCARD_DATA const *,_CARD_ROLE,PIN_MAP_RECORD *)
0x180008edc  mov     eax, [rbp+120h+var_38]
0x180008ee2  mov     [rsp+220h+var_1D0], eax
0x180008ee6  lea     rcx, [rbp+120h+var_90]; struct PIN_MAP_RECORD *
0x180008eed  call    ?I_PinMapIsActive@@YAHPEBUPIN_MAP_RECORD@@@Z; I_PinMapIsActive(PIN_MAP_RECORD const *)
0x180008ef2  test    eax, eax
0x180008ef4  jnz     short loc_180008EFB
0x180008ef6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008efb  lea     rcx, [rbp+120h+var_90]; struct PIN_MAP_RECORD *
0x180008f02  call    ?I_PinMapIsBlocked@@YAHPEBUPIN_MAP_RECORD@@@Z; I_PinMapIsBlocked(PIN_MAP_RECORD const *)
0x180008f07  test    eax, eax
0x180008f09  jz      short loc_180008F10
0x180008f0b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008f10  cmp     [rbp+120h+var_38], edi
0x180008f16  jge     short loc_180008F23
0x180008f18  mov     [rsp+220h+var_1E0], edi
0x180008f1c  mov     ebx, edi
0x180008f1e  jmp     loc_180009108
0x180008f23  xor     edx, edx; Val
0x180008f25  lea     r8d, [rdx+5Ch]; Size
0x180008f29  lea     rcx, [rbp+120h+var_F0]; void *
0x180008f2d  call    memset_0
0x180008f32  lea     r8, [rbp+120h+var_F0]
0x180008f36  mov     edx, [rsp+220h+var_1D8]
0x180008f3a  mov     rcx, [rsp+220h+var_1C0]
0x180008f3f  call    ?I_PinMapGetRecord@@YAXPEBUVCARD_DATA@@W4_CARD_ROLE@@PEAUPIN_MAP_RECORD@@@Z; I_PinMapGetRecord(VCARD_DATA const *,_CARD_ROLE,PIN_MAP_RECORD *)
0x180008f44  dec     [rbp+120h+var_98]
0x180008f4a  lea     rcx, [rbp+120h+var_F0]; struct PIN_MAP_RECORD *
0x180008f4e  call    ?I_PinMapIsBlocked@@YAHPEBUPIN_MAP_RECORD@@@Z; I_PinMapIsBlocked(PIN_MAP_RECORD const *)
0x180008f53  test    eax, eax
0x180008f55  jz      short loc_180008FA9
0x180008f57  xor     edx, edx; Val
0x180008f59  lea     r8d, [rdx+50h]; Size
0x180008f5d  lea     rcx, [rbp+120h+var_F0]; void *
0x180008f61  call    memset_0
0x180008f66  mov     eax, cs:dword_180048098
0x180008f6c  cmp     eax, 5
0x180008f6f  jbe     short loc_180008FA9
0x180008f71  mov     rdx, 200000000000h
0x180008f7b  lea     rcx, dword_180048098
0x180008f82  call    _tlgKeywordOn
0x180008f87  test    al, al
0x180008f89  jz      short loc_180008FA9
0x180008f8b  mov     eax, [rsp+220h+var_1D8]
0x180008f8f  mov     [rsp+220h+var_1C8], eax
0x180008f93  lea     rax, [rsp+220h+var_1C8]
0x180008f98  mov     [rsp+220h+var_200], rax
0x180008f9d  lea     rdx, byte_18003ED1D
0x180008fa4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180008fa9  lea     r8, [rbp+120h+var_F0]
0x180008fad  mov     edx, [rsp+220h+var_1D8]
0x180008fb1  mov     rcx, [rsp+220h+var_1C0]
0x180008fb6  call    ?I_PinMapSetRecord@@YAKPEBUVCARD_DATA@@W4_CARD_ROLE@@PEBUPIN_MAP_RECORD@@@Z; I_PinMapSetRecord(VCARD_DATA const *,_CARD_ROLE,PIN_MAP_RECORD const *)
0x180008fbb  mov     [rsp+220h+var_1E0], eax
0x180008fbf  mov     ecx, [rbp+120h+var_98]
0x180008fc5  mov     [rsp+220h+var_1CC], ecx
0x180008fc9  test    eax, eax
0x180008fcb  jz      short loc_18000902F
0x180008fcd  mov     edx, 2
0x180008fd2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180008fd7  lea     rax, WPP_GLOBAL_Control
0x180008fde  mov     rcx, cs:WPP_GLOBAL_Control
0x180008fe5  cmp     rcx, rax
0x180008fe8  jz      short loc_180009026
0x180008fea  test    byte ptr [rcx+1Ch], 1
0x180008fee  jz      short loc_180009026
0x180008ff0  cmp     byte ptr [rcx+19h], 2
0x180008ff4  jb      short loc_180009026
0x180008ff6  mov     edx, 31h ; '1'
0x180008ffb  lea     rax, aUnableToUpdate; "Unable to update PIN map record"
0x180009002  mov     [rsp+220h+var_1F8], rax
0x180009007  mov     eax, [rsp+220h+var_1E0]
0x18000900b  mov     dword ptr [rsp+220h+var_200], eax
0x18000900f  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180009016  lea     r8, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids
0x18000901d  mov     rcx, [rcx+10h]
0x180009021  call    WPP_SF_sDs
0x180009026  mov     ebx, [rsp+220h+var_1E0]
0x18000902a  jmp     loc_180009108
0x18000902f  lea     rax, [rsp+220h+var_1C0]
0x180009034  mov     [rbp+120h+var_198], rax
0x180009038  lea     rax, [rsp+220h+var_1D8]
0x18000903d  mov     [rbp+120h+var_190], rax
0x180009041  lea     rax, [rbp+120h+var_90]
0x180009048  mov     [rbp+120h+var_188], rax
0x18000904c  mov     [rbp+120h+var_180], 102h
0x180009052  lea     rax, [rsp+220h+var_1C0]
0x180009057  mov     [rbp+120h+var_160], rax
0x18000905b  lea     rax, [rsp+220h+var_1D8]
0x180009060  mov     [rbp+120h+var_158], rax
0x180009064  lea     rax, [rbp+120h+var_F0]
0x180009068  mov     [rbp+120h+var_150], rax
0x18000906c  lea     rcx, [rbp+120h+var_160]
0x180009070  call    _lambda_4151db1353c7c1ea51d3518dbed218c3___operator__
0x180009075  mov     [rsp+220h+var_1E0], eax
0x180009079  test    eax, eax
0x18000907b  jz      short loc_1800090D8
0x18000907d  mov     edx, 2
0x180009082  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180009087  lea     rax, WPP_GLOBAL_Control
0x18000908e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009095  cmp     rcx, rax
0x180009098  jz      short loc_1800090FA
0x18000909a  test    byte ptr [rcx+1Ch], 1
0x18000909e  jz      short loc_1800090FA
0x1800090a0  cmp     byte ptr [rcx+19h], 2
0x1800090a4  jb      short loc_1800090FA
0x1800090a6  mov     edx, 34h ; '4'
0x1800090ab  lea     rax, aUpdatingPinMap; "Updating PIN map failed"
0x1800090b2  mov     [rsp+220h+var_1F8], rax
0x1800090b7  mov     eax, [rsp+220h+var_1E0]
0x1800090bb  mov     dword ptr [rsp+220h+var_200], eax
0x1800090bf  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800090c6  lea     r8, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids
0x1800090cd  mov     rcx, [rcx+10h]
0x1800090d1  call    WPP_SF_sDs
0x1800090d6  jmp     short loc_1800090FA
0x1800090d8  mov     byte ptr [rbp+120h+var_180+1], dil
0x1800090dc  lea     rcx, [rbp+120h+var_F0]; struct PIN_MAP_RECORD *
0x1800090e0  call    ?I_PinMapIsBlocked@@YAHPEBUPIN_MAP_RECORD@@@Z; I_PinMapIsBlocked(PIN_MAP_RECORD const *)
0x1800090e5  test    eax, eax
0x1800090e7  jz      short loc_1800090FA
0x1800090e9  lea     rdx, [rbp+120h+var_90]; unsigned __int16 *
0x1800090f0  mov     rcx, [rsp+220h+var_1C0]; struct VCARD_DATA *
0x1800090f5  call    ?I_DeleteKspKey@@YAKPEBUVCARD_DATA@@PEBG@Z; I_DeleteKspKey(VCARD_DATA const *,ushort const *)
0x1800090fa  mov     ebx, [rsp+220h+var_1E0]
0x1800090fe  lea     rcx, [rbp+120h+var_198]
0x180009102  call    wil__details__ScopeExitFnGuard__lambda_f38f1c235d4bbfc7af7b18896877faaa_____operator__
0x180009107  nop
0x180009108  lea     rcx, [rsp+220h+var_1A8]
0x18000910d  call    ScTraceUnwinder__lambda_627c111035fb335143fe45036d0c4a7d_______ScTraceUnwinder__lambda_627c111035fb335143fe45036d0c4a7d____
0x180009112  nop
0x180009113  lea     rcx, [rbp+120h+var_120]
0x180009117  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x18000911c  nop
0x18000911d  lea     rcx, [rbp+120h+var_1A0]
0x180009121  call    WppTraceUnwinder__lambda_5b1f020a0bcd8f3494dc24fabf843cea_______WppTraceUnwinder__lambda_5b1f020a0bcd8f3494dc24fabf843cea____
0x180009126  mov     eax, ebx
0x180009128  mov     rcx, [rbp+120h+var_10]
0x18000912f  xor     rcx, rsp; StackCookie
0x180009132  call    __security_check_cookie
0x180009137  lea     r11, [rsp+220h+var_s0]
0x18000913f  mov     rbx, [r11+20h]
0x180009143  mov     rdi, [r11+28h]
0x180009147  mov     rsp, r11
0x18000914a  pop     rbp
0x18000914b  retn
```
