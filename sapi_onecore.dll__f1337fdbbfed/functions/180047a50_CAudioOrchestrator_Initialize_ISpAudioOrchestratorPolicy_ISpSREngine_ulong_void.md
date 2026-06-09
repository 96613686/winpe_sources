# CAudioOrchestrator::Initialize(ISpAudioOrchestratorPolicy *,ISpSREngine *,ulong,void * *)

- ea: `0x180047a50`
- end: `0x1800483ff`
- name: `?Initialize@CAudioOrchestrator@@UEAAJPEAUISpAudioOrchestratorPolicy@@PEAUISpSREngine@@KPEAPEAX@Z`
- size: `2479`
- prototype: `__int64 __usercall@<rax>(CAudioOrchestrator *__hidden this@<rcx>, struct IUnknown *@<rdx>, struct ISpSREngine *@<r8>, unsigned int@<r9d>, void **)`
- caller_count: `0`
- callee_count: `36`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000a590`
- `0x18000bec4`
- `0x18000e518`
- `0x180013ec0`
- `0x18001f27c`
- `0x1800243e8`
- `0x18002895c`
- `0x18003d7c4`
- `0x180047a50`
- `0x180048408`
- `0x1800484f0`
- `0x180048540`
- `0x180049bfc`
- `0x18004c1e8`
- `0x180056e28`
- `0x180058bc0`
- `0x180079e30`
- `0x180094190`
- `0x1800a773c`
- `0x1800ab1a0`
- `0x1800ab8a4`
- `0x1800ac024`
- `0x1800ac304`
- `0x1800ae134`
- `0x1800ae190`
- `0x1800ae234`
- `0x1800ae300`
- `0x1800aeca0`
- `0x1800afb9c`
- `0x1800b0340`
- `0x1800b47b8`
- `0x1800b6dc8`
- `0x1800c88e4`
- `0x1800cb284`
- `0x1800e4950`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180048042`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180048055`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004806f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180048042`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180048055`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004806f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047aa6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047aa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004826d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004826d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180047cab`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180047cab`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180048255`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180048255`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180047b57`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180047b57`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x180048028`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x180048028`

## string_xrefs

- `0x180047ff2`: `[%s] AAR: posting message to create VA`
- `0x180048276`: `Latency test: Cannot open file! %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CAudioOrchestrator::Initialize(
        CAudioOrchestrator *this,
        struct IUnknown *a2,
        struct IUnknown *a3,
        int a4,
        void **a5)
{
  struct _SECURITY_ATTRIBUTES *v9; // rdx
  unsigned int v10; // ebx
  int v11; // eax
  enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001 v12; // edx
  unsigned int v13; // r9d
  BOOL v14; // eax
  HRESULT RDC; // esi
  char *v16; // rdx
  HANDLE *v17; // r14
  HANDLE *v18; // r15
  int v19; // r12d
  _QWORD *v20; // rbx
  int Policy_MaskOutMicrophoneAudio; // eax
  int v22; // eax
  OneSettingsPolicyWrapper **v23; // rax
  int DWORDValue; // eax
  OneSettingsPolicyWrapper **v25; // rax
  int v26; // eax
  struct _SECURITY_ATTRIBUTES *v27; // rdx
  int v28; // eax
  int v29; // ebx
  HWND v30; // rax
  HANDLE v31; // r9
  int ShouldVAStartInLowPower; // ebx
  int CanVAStartInLowPower; // eax
  struct ISpAudioOrchestratorPolicy **v34; // rbx
  int v35; // eax
  HANDLE FileW; // rax
  DWORD LastError; // eax
  struct ISpAudioOrchestratorPolicy *v38; // rcx
  int v39; // eax
  LPVOID *ppv; // [rsp+20h] [rbp-A1h]
  LPVOID *ppva; // [rsp+20h] [rbp-A1h]
  unsigned int v43; // [rsp+40h] [rbp-81h] BYREF
  unsigned int v44; // [rsp+44h] [rbp-7Dh] BYREF
  SpeechAudioEndpointSelector *v45; // [rsp+48h] [rbp-79h] BYREF
  struct IMMDevice *v46; // [rsp+50h] [rbp-71h] BYREF
  std::_Ref_count_base *v47; // [rsp+58h] [rbp-69h]
  LPCWSTR lpFileName; // [rsp+60h] [rbp-61h] BYREF
  LPVOID v49; // [rsp+68h] [rbp-59h] BYREF
  char *v50; // [rsp+70h] [rbp-51h] BYREF
  int v51; // [rsp+78h] [rbp-49h]
  _BYTE pv[64]; // [rsp+80h] [rbp-41h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+57h]

  WatchdogTimer::WatchdogTimer(pv, "CAudioOrchestrator::Initialize");
  v50 = (char *)this + 160;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 4);
  v51 = 0;
  DoTraceMessage(8, "[%s] enter, dwFlags = %d", "CAudioOrchestrator::Initialize", a4);
  if ( (unsigned int)(a4 - 1) <= 2 && a2 && !*((_QWORD *)this + 32) && !*((_DWORD *)this + 66) )
  {
    ATL::AtlComPtrAssign((struct IUnknown **)this + 32, a2);
    if ( *((struct IUnknown **)this + 34) != a3 )
      ATL::AtlComPtrAssign((struct IUnknown **)this + 34, a3);
    *((_DWORD *)this + 66) = a4;
    *((_DWORD *)this + 234) = CAudioOrchestrator::IsSystemAoAc(this);
    if ( CSpAutoEvent::InitEvent((CAudioOrchestrator *)((char *)this + 792), v9, 0, 0, (const unsigned __int16 *)ppv) >= 0 )
    {
      RtlGetDeviceFamilyInfoEnum(0, (char *)this + 952, 0);
      *((_DWORD *)this + 235) = *((_DWORD *)this + 238) == 5;
      v46 = 0;
      v45 = 0;
      v44 = 0;
      if ( (int)Microsoft::WRL::Details::MakeAndInitialize<SpeechAudioEndpointSelector,SpeechAudioEndpointSelector,>(&v45) >= 0 )
      {
        v43 = 0;
        if ( SpeechAudioEndpointSelector::IsHardwareVoiceActivationSupported(v45, &v43) >= 0 )
        {
          *((_DWORD *)this + 237) = 1;
          v10 = v43;
          *((_DWORD *)this + 239) = v43;
          if ( v10 != CAudioOrchestrator::GetPolicy_MVATargetVersion(this) || (v11 = 1, *((_DWORD *)this + 238) != 10) )
            v11 = 0;
          *((_DWORD *)this + 236) = v11;
        }
        DoTraceMessage(
          8,
          "[%s] - HWKWS system - %d - version - %d",
          "CAudioOrchestrator::Initialize",
          *((_DWORD *)this + 237),
          *((_DWORD *)this + 239));
        if ( *((_DWORD *)this + 237) == 1 )
          SpLogEvent("CAudioOrchestrator::Initialize", 0, L"Voice Activation - Hardware-offload Supported");
        if ( (int)SpeechAudioEndpointSelector::GetDefaultIntegratedEndpoint(v45, v12, &v46, &v44) >= 0 )
        {
          if ( v46 )
          {
            v13 = v44;
            v14 = v44 >= 0x2D;
            *((_DWORD *)this + 231) = v14;
            DoTraceMessage(
              8,
              "[%s] - Integrated Mic Found - max buffer duration %u ms - LPA %d - HWKWS",
              "CAudioOrchestrator::Initialize",
              v13,
              v14);
            if ( *((_DWORD *)this + 231) == 1 )
              SpLogEvent("CAudioOrchestrator::Initialize", 0, L"Voice Activation - Big Buffer Capture Supported");
          }
        }
      }
      ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v45);
      ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v46);
    }
  }
  v49 = 0;
  RDC = CoCreateInstance(&CLSID_SpResourceManager, 0, 0x17u, &GUID_2baeef81_2ca3_4331_98f3_26ec5abefb03, &v49);
  if ( RDC >= 0 )
  {
    v16 = (char *)this + 72;
    if ( !this )
      v16 = 0;
    ppva = (LPVOID *)((char *)this + 240);
    RDC = (*(__int64 (__fastcall **)(LPVOID, char *, _QWORD, _QWORD))(*(_QWORD *)v49 + 56LL))(v49, v16, 0, 0);
    if ( RDC >= 0 )
    {
      v46 = 0;
      RDC = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IMMDevice **))(**((_QWORD **)this + 30) + 32LL))(
              *((_QWORD *)this + 30),
              0,
              &v46);
      if ( RDC >= 0 )
      {
        v44 = 0;
        RDC = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, unsigned int *))(**((_QWORD **)this + 32) + 56LL))(
                *((_QWORD *)this + 32),
                L"DebugAudioInputFile_PostMec",
                &v44);
        *((_BYTE *)this + 492) = v44 == 1;
      }
    }
  }
  if ( RDC >= 0 )
  {
    v17 = (HANDLE *)((char *)this + 496);
    v18 = (HANDLE *)((char *)this + 512);
    if ( (unsigned int)(*((_DWORD *)this + 66) - 2) > 1 )
    {
      *v17 = CreateEventW(0, 0, 0, 0);
      *v18 = CreateEventW(0, 0, 0, 0);
      v20 = (_QWORD *)((char *)this + 520);
      *((_QWORD *)this + 65) = CreateEventW(0, 0, 0, 0);
    }
    else
    {
      RDC = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, char *))(**((_QWORD **)this + 32) + 72LL))(
              *((_QWORD *)this + 32),
              L"DebugAudioInputFile_PostMec",
              (char *)this + 496);
      v19 = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *, char *))(**((_QWORD **)this + 32) + 72LL))(
              *((_QWORD *)this + 32),
              L"DisableSpeechInput",
              (char *)this + 512);
      if ( RDC < 0 )
        goto LABEL_33;
      v20 = (_QWORD *)((char *)this + 520);
      RDC = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, char *))(**((_QWORD **)this + 32) + 72LL))(
              *((_QWORD *)this + 32),
              L"AarStart",
              (char *)this + 520);
      if ( RDC < 0 )
        goto LABEL_33;
      if ( v19 < 0 )
      {
        RDC = v19;
        goto LABEL_33;
      }
    }
    v31 = *v17;
    if ( !*v17
      || v31 == (HANDLE)-1LL
      || (v20 = (_QWORD *)((char *)this + 520),
          (unsigned __int64)(*((_QWORD *)this + 64) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL
       || (unsigned __int64)(*((_QWORD *)this + 65) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL) )
    {
      DoTraceMessage(
        2,
        "[%s] AudioOrchestrator: handles for execution are invalid 0x%x, 0x%x, 0x%x",
        "CAudioOrchestrator::Initialize",
        (_DWORD)v31,
        (unsigned int)*v18,
        *v20);
      RDC = -2147200979;
    }
    else if ( !v31 )
    {
      DoTraceMessage(
        2,
        "[%s] WAV File handle required for proper operation - failing initialize",
        "CAudioOrchestrator::Initialize");
      RDC = -2147200965;
    }
  }
LABEL_33:
  *((_WORD *)this + 255) = 0;
  Policy_MaskOutMicrophoneAudio = CAudioOrchestrator::GetPolicy_MaskOutMicrophoneAudio(this);
  *((_DWORD *)this + 126) = Policy_MaskOutMicrophoneAudio;
  if ( RDC >= 0 )
  {
    if ( Policy_MaskOutMicrophoneAudio )
      DoTraceMessage(
        8,
        "[%s] Test: audio buffers from the microphone have content set to zero",
        "CAudioOrchestrator::Initialize");
    if ( !(unsigned int)CAudioOrchestrator::GetPolicy_RDCEnabled(this)
      || (RDC = CAudioOrchestrator::CreateRDC(this), RDC >= 0) )
    {
      byte_1803B9EE8 = 1;
      RDC = PowerNotificationProxy::Initialize(
              (CAudioOrchestrator *)((char *)this + 1248),
              (CAudioOrchestrator *)((char *)this + 80),
              *((struct ISpAudioOrchestratorPolicy **)this + 32));
      if ( RDC >= 0
        && (unsigned int)(*((_DWORD *)this + 66) - 2) <= 1
        && !(unsigned int)CAudioOrchestrator::IsCortanaScreenRestrictedSupported(this) )
      {
        v22 = CAudioOrchestrator::SubscribeToInputSuppression(this);
        if ( v22 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x3C1,
            (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\audioex\\audioorchestrator.cpp",
            (const char *)(unsigned int)v22,
            (int)ppva);
      }
    }
  }
  v43 = 1;
  v23 = (OneSettingsPolicyWrapper **)SRCloudPolicy::Instance(&v46);
  DWORDValue = OneSettingsPolicyWrapper::GetDWORDValue(*v23, L"S3SystemHWKWSScreenOffAC", &v43);
  if ( DWORDValue < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3C5,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\audioex\\audioorchestrator.cpp",
      (const char *)(unsigned int)DWORDValue,
      (int)ppva);
  if ( v47 )
    std::_Ref_count_base::_Decref(v47);
  *((_DWORD *)this + 232) = v43 != 0;
  v43 = 1;
  v25 = (OneSettingsPolicyWrapper **)SRCloudPolicy::Instance(&v46);
  v26 = OneSettingsPolicyWrapper::GetDWORDValue(*v25, L"S3SystemHWKWSScreenOffDC", &v43);
  if ( v26 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3C9,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\audioex\\audioorchestrator.cpp",
      (const char *)(unsigned int)v26,
      (int)ppva);
  if ( v47 )
    std::_Ref_count_base::_Decref(v47);
  *((_DWORD *)this + 233) = v43 != 0;
  if ( RDC >= 0 )
  {
    RDC = CSpAutoEvent::InitEvent((CAudioOrchestrator *)((char *)this + 584), v27, 0, 0, (const unsigned __int16 *)ppva);
    if ( RDC >= 0 )
    {
      if ( (unsigned int)CAudioOrchestrator::GetPolicy_VAEnabled(this) )
      {
        v28 = CAudioOrchestrator::EnsureSetInput(this);
        RDC = v28;
        if ( v28 < 0 )
        {
          DoTraceMessage(
            8,
            "[%s] input initialization failure 0x%x - ignoring\n",
            "CAudioOrchestrator::Initialize",
            (unsigned int)v28);
        }
        else
        {
          v29 = *((_DWORD *)this + 239);
          if ( v29 == CAudioOrchestrator::GetPolicy_MVATargetVersion(this)
            && (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 80LL))(*((_QWORD *)this + 30))
            && !*((_DWORD *)this + 236) )
          {
            DoTraceMessage(8, "[%s] AAR: posting message to create VA", "CAudioOrchestrator::Initialize");
            v30 = (HWND)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 80LL))(*((_QWORD *)this + 30));
            PostMessageW(v30, 0x8000u, 1u, 4);
            goto LABEL_75;
          }
          RDC = CAudioOrchestrator::EnsureCreateVAMaster(this);
          if ( RDC >= 0 )
          {
            ShouldVAStartInLowPower = CAudioOrchestrator::ShouldVAStartInLowPower(this);
            CanVAStartInLowPower = CAudioOrchestrator::CanVAStartInLowPower(this);
            DoTraceMessage(
              8,
              "[%s] - KWS WoV -- CanVAStartInLowPower(): %d, ShouldVAStartInLowPower(): %d - 0x%x",
              "CAudioOrchestrator::Initialize",
              CanVAStartInLowPower,
              ShouldVAStartInLowPower,
              RDC);
            if ( (unsigned int)CAudioOrchestrator::ShouldVAStartInLowPower(this) == 1 )
              SpLogEvent("CAudioOrchestrator::Initialize", 0, L"Voice Activation - Wake on Voice Supported");
            goto LABEL_75;
          }
          if ( *((_QWORD *)this + 35) )
          {
            DoTraceMessage(2, "[%s] VA initializatation failure 0x%x - fatal", "CAudioOrchestrator::Initialize", RDC);
            goto LABEL_75;
          }
          DoTraceMessage(
            8,
            "[%s] VA initialization failure 0x%x - ignoring\n",
            "CAudioOrchestrator::Initialize",
            (unsigned int)RDC);
        }
        RDC = 0;
      }
    }
  }
LABEL_75:
  lpFileName = 0;
  if ( RDC < 0 )
    goto LABEL_98;
  v34 = (struct ISpAudioOrchestratorPolicy **)((char *)this + 256);
  if ( (unsigned int)(*((_DWORD *)this + 66) - 2) <= 1 )
  {
    v35 = (*(__int64 (__fastcall **)(struct ISpAudioOrchestratorPolicy *, const wchar_t *, LPCWSTR *))(*(_QWORD *)*v34 + 24LL))(
            *v34,
            L"LatencyMetricsFile",
            &lpFileName);
    if ( v35 < 0 )
      DoTraceMessage(
        2,
        "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
        (const wchar_t *)&NLInternal::s_tracingPrefix,
        L"CAudioOrchestrator::Initialize",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\audioex\\audioorchestrator.cpp(1028)",
        v35);
    if ( lpFileName )
    {
      FileW = CreateFileW(lpFileName, 0x40000000u, 1u, 0, 2u, 0x80u, 0);
      *((_QWORD *)this + 97) = FileW;
      if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        LastError = GetLastError();
        DoTraceMessage(8, "Latency test: Cannot open file! %d\n", LastError);
      }
    }
  }
  if ( a5 )
  {
    RDC = CSpAutoEvent::InitEvent((CAudioOrchestrator *)((char *)this + 568), v27, 0, 0, (const unsigned __int16 *)ppva);
    if ( RDC >= 0 )
    {
      *a5 = (void *)*((_QWORD *)this + 72);
      goto LABEL_85;
    }
LABEL_98:
    DoTraceMessage(8, "[%s] failed, hr: 0x%x", "CAudioOrchestrator::Initialize", RDC);
    goto LABEL_99;
  }
LABEL_85:
  RDC = CAudioOrchestrator::InitDeviceDisambiguation(this);
  if ( RDC < 0 )
    goto LABEL_98;
  v38 = *v34;
  if ( this == (CAudioOrchestrator *)-88LL || !v38 )
  {
    DoTraceMessage(
      8,
      "[%s] invalid arguments: %d, %d",
      "PDCActivation::Initialize",
      (CAudioOrchestrator *)((char *)this + 88) == 0,
      *v34 == 0);
    RDC = -2147467261;
    goto LABEL_98;
  }
  *((_QWORD *)this + 188) = (char *)this + 88;
  *((_QWORD *)this + 189) = v38;
  if ( *((_DWORD *)this + 234) )
  {
    if ( (unsigned int)(*((_DWORD *)this + 66) - 2) <= 1 )
    {
      RDC = PDCActivation::RegisterPDCSignal((CAudioOrchestrator *)((char *)this + 1448));
      if ( RDC < 0 )
        goto LABEL_98;
    }
  }
  RDC = 0;
  if ( !*((_QWORD *)this + 70) )
    RDC = CMMNotificationClientProxy::CreateProxy(
            (struct IMMNotificationClient *)this + 8,
            (struct CMMNotificationClientProxy **)this + 70,
            *v34);
  if ( RDC < 0 )
    goto LABEL_98;
  if ( (unsigned int)(*((_DWORD *)this + 66) - 2) <= 1 )
  {
    v39 = CAudioOrchestrator::CheckAndSubscribeAgentState(this);
    if ( v39 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x43D,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\audioex\\audioorchestrator.cpp",
        (const char *)(unsigned int)v39,
        (int)ppva);
  }
LABEL_99:
  SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&lpFileName);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v49);
  CSPAutoCritSecLock::~CSPAutoCritSecLock((CSPAutoCritSecLock *)&v50);
  WatchdogTimer::~WatchdogTimer((WatchdogTimer *)pv);
  return (unsigned int)RDC;
}

```

## disassembly

```asm
0x180047a50  push    rbp
0x180047a52  push    rbx
0x180047a53  push    rsi
0x180047a54  push    rdi
0x180047a55  push    r12
0x180047a57  push    r13
0x180047a59  push    r14
0x180047a5b  push    r15
0x180047a5d  lea     rbp, [rsp-17h]
0x180047a62  sub     rsp, 0D8h
0x180047a69  mov     rax, cs:__security_cookie
0x180047a70  xor     rax, rsp
0x180047a73  mov     [rbp+4Fh+var_50], rax
0x180047a77  mov     r14d, r9d
0x180047a7a  mov     rsi, r8
0x180047a7d  mov     rbx, rdx
0x180047a80  mov     rdi, rcx
0x180047a83  mov     r13, [rbp+4Fh+arg_20]
0x180047a87  lea     r15, aCaudioorchestr_118; "CAudioOrchestrator::Initialize"
0x180047a8e  mov     rdx, r15; char *
0x180047a91  lea     rcx, [rbp+4Fh+pv]; pv
0x180047a95  call    ??0WatchdogTimer@@QEAA@PEBD@Z; WatchdogTimer::WatchdogTimer(char const *)
0x180047a9a  nop
0x180047a9b  lea     rcx, [rdi+0A0h]; lpCriticalSection
0x180047aa2  mov     [rbp+4Fh+var_A0], rcx
0x180047aa6  call    cs:__imp_EnterCriticalSection
0x180047aac  xor     r12d, r12d
0x180047aaf  mov     [rbp+4Fh+var_98], r12d
0x180047ab3  mov     r9d, r14d
0x180047ab6  mov     r8, r15
0x180047ab9  lea     rdx, aSEnterDwflagsD; "[%s] enter, dwFlags = %d"
0x180047ac0  lea     ecx, [r12+8]; int
0x180047ac5  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x180047aca  lea     eax, [r14-1]
0x180047ace  cmp     eax, 2
0x180047ad1  ja      loc_180047C8A
0x180047ad7  test    rbx, rbx
0x180047ada  jz      loc_180047C8A
0x180047ae0  lea     rcx, [rdi+100h]; struct IUnknown **
0x180047ae7  cmp     [rcx], r12
0x180047aea  jnz     loc_180047C8A
0x180047af0  cmp     [rdi+108h], r12d
0x180047af7  jnz     loc_180047C8A
0x180047afd  mov     rdx, rbx; struct IUnknown *
0x180047b00  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180047b05  lea     rcx, [rdi+110h]; struct IUnknown **
0x180047b0c  cmp     [rcx], rsi
0x180047b0f  jz      short loc_180047B19
0x180047b11  mov     rdx, rsi; struct IUnknown *
0x180047b14  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180047b19  mov     [rdi+108h], r14d
0x180047b20  mov     rcx, rdi; this
0x180047b23  call    ?IsSystemAoAc@CAudioOrchestrator@@AEAAHXZ; CAudioOrchestrator::IsSystemAoAc(void)
0x180047b28  mov     [rdi+3A8h], eax
0x180047b2e  lea     rcx, [rdi+318h]; this
0x180047b35  xor     r9d, r9d; int
0x180047b38  xor     r8d, r8d; int
0x180047b3b  call    ?InitEvent@CSpAutoEvent@@QEAAJPEAU_SECURITY_ATTRIBUTES@@HHPEBG@Z; CSpAutoEvent::InitEvent(_SECURITY_ATTRIBUTES *,int,int,ushort const *)
0x180047b40  test    eax, eax
0x180047b42  js      loc_180047C8A
0x180047b48  lea     rsi, [rdi+3B8h]
0x180047b4f  xor     r8d, r8d
0x180047b52  mov     rdx, rsi
0x180047b55  xor     ecx, ecx
0x180047b57  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180047b5d  mov     eax, r12d
0x180047b60  cmp     dword ptr [rsi], 5
0x180047b63  setz    al
0x180047b66  mov     [rdi+3ACh], eax
0x180047b6c  mov     [rbp+4Fh+var_C0], r12
0x180047b70  mov     [rbp+4Fh+var_C8], r12
0x180047b74  mov     [rbp+4Fh+var_CC], r12d
0x180047b78  lea     rcx, [rbp+4Fh+var_C8]
0x180047b7c  call    ??$MakeAndInitialize@VSpeechAudioEndpointSelector@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVSpeechAudioEndpointSelector@@@Z; Microsoft::WRL::Details::MakeAndInitialize<SpeechAudioEndpointSelector,SpeechAudioEndpointSelector,>(SpeechAudioEndpointSelector * *)
0x180047b81  test    eax, eax
0x180047b83  js      loc_180047C77
0x180047b89  mov     [rsp+110h+var_D0], r12d
0x180047b8e  lea     rdx, [rsp+110h+var_D0]; unsigned int *
0x180047b93  mov     rcx, [rbp+4Fh+var_C8]; this
0x180047b97  call    ?IsHardwareVoiceActivationSupported@SpeechAudioEndpointSelector@@QEAAJPEAK@Z; SpeechAudioEndpointSelector::IsHardwareVoiceActivationSupported(ulong *)
0x180047b9c  test    eax, eax
0x180047b9e  js      short loc_180047BD3
0x180047ba0  mov     dword ptr [rdi+3B4h], 1
0x180047baa  mov     ebx, [rsp+110h+var_D0]
0x180047bae  mov     [rdi+3BCh], ebx
0x180047bb4  mov     rcx, rdi; this
0x180047bb7  call    ?GetPolicy_MVATargetVersion@CAudioOrchestrator@@AEAAKXZ; CAudioOrchestrator::GetPolicy_MVATargetVersion(void)
0x180047bbc  cmp     ebx, eax
0x180047bbe  jnz     short loc_180047BCA
0x180047bc0  cmp     dword ptr [rsi], 0Ah
0x180047bc3  mov     eax, 1
0x180047bc8  jz      short loc_180047BCD
0x180047bca  mov     eax, r12d
0x180047bcd  mov     [rdi+3B0h], eax
0x180047bd3  mov     eax, [rdi+3BCh]
0x180047bd9  mov     dword ptr [rsp+110h+ppv], eax
0x180047bdd  mov     r9d, [rdi+3B4h]
0x180047be4  mov     r8, r15
0x180047be7  lea     rdx, aSHwkwsSystemDV; "[%s] - HWKWS system - %d - version - %d"
0x180047bee  mov     ebx, 8
0x180047bf3  mov     ecx, ebx; int
0x180047bf5  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x180047bfa  cmp     dword ptr [rdi+3B4h], 1
0x180047c01  jnz     short loc_180047C16
0x180047c03  lea     r8, aVoiceActivatio_7; "Voice Activation - Hardware-offload Sup"...
0x180047c0a  movzx   edx, r12w; unsigned __int16
0x180047c0e  mov     rcx, r15; char *
0x180047c11  call    ?SpLogEvent@@YAXPEBDGPEBGZZ; SpLogEvent(char const *,ushort,ushort const *,...)
0x180047c16  lea     r9, [rbp+4Fh+var_CC]; unsigned int *
0x180047c1a  lea     r8, [rbp+4Fh+var_C0]; struct IMMDevice **
0x180047c1e  mov     rcx, [rbp+4Fh+var_C8]; this
0x180047c22  call    ?GetDefaultIntegratedEndpoint@SpeechAudioEndpointSelector@@QEAAJW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@PEAPEAUIMMDevice@@PEAK@Z; SpeechAudioEndpointSelector::GetDefaultIntegratedEndpoint(__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,IMMDevice * *,ulong *)
0x180047c27  test    eax, eax
0x180047c29  js      short loc_180047C77
0x180047c2b  cmp     [rbp+4Fh+var_C0], r12
0x180047c2f  jz      short loc_180047C77
0x180047c31  mov     eax, r12d
0x180047c34  mov     r9d, [rbp+4Fh+var_CC]
0x180047c38  cmp     r9d, 2Dh ; '-'
0x180047c3c  setnb   al
0x180047c3f  mov     [rdi+39Ch], eax
0x180047c45  mov     dword ptr [rsp+110h+ppv], eax
0x180047c49  mov     r8, r15
0x180047c4c  lea     rdx, aSIntegratedMic; "[%s] - Integrated Mic Found - max buffe"...
0x180047c53  mov     ecx, ebx; int
0x180047c55  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x180047c5a  cmp     dword ptr [rdi+39Ch], 1
0x180047c61  jnz     short loc_180047C77
0x180047c63  lea     r8, aVoiceActivatio; "Voice Activation - Big Buffer Capture S"...
0x180047c6a  movzx   edx, r12w; unsigned __int16
0x180047c6e  mov     rcx, r15; char *
0x180047c71  call    ?SpLogEvent@@YAXPEBDGPEBGZZ; SpLogEvent(char const *,ushort,ushort const *,...)
0x180047c76  nop
0x180047c77  lea     rcx, [rbp+4Fh+var_C8]
0x180047c7b  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x180047c80  nop
0x180047c81  lea     rcx, [rbp+4Fh+var_C0]
0x180047c85  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x180047c8a  mov     [rbp+4Fh+var_A8], r12
0x180047c8e  lea     rax, [rbp+4Fh+var_A8]
0x180047c92  mov     [rsp+110h+ppv], rax; ppv
0x180047c97  lea     r9, _GUID_2baeef81_2ca3_4331_98f3_26ec5abefb03; riid
0x180047c9e  xor     edx, edx; pUnkOuter
0x180047ca0  lea     r8d, [rdx+17h]; dwClsContext
0x180047ca4  lea     rcx, CLSID_SpResourceManager; rclsid
0x180047cab  call    cs:__imp_CoCreateInstance
0x180047cb1  mov     esi, eax
0x180047cb3  test    eax, eax
0x180047cb5  js      loc_180047D3F
0x180047cbb  mov     rcx, [rbp+4Fh+var_A8]
0x180047cbf  mov     rax, [rcx]
0x180047cc2  test    rdi, rdi
0x180047cc5  lea     rdx, [rdi+48h]
0x180047cc9  jnz     short loc_180047CCE
0x180047ccb  mov     rdx, r12
0x180047cce  lea     rbx, [rdi+0F0h]
0x180047cd5  mov     [rsp+110h+ppv], rbx; unsigned __int16 *
0x180047cda  xor     r9d, r9d
0x180047cdd  xor     r8d, r8d
0x180047ce0  mov     rax, [rax+38h]
0x180047ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ce9  mov     esi, eax
0x180047ceb  test    eax, eax
0x180047ced  js      short loc_180047D3F
0x180047cef  mov     [rbp+4Fh+var_C0], r12
0x180047cf3  mov     rcx, [rbx]
0x180047cf6  mov     rax, [rcx]
0x180047cf9  lea     r8, [rbp+4Fh+var_C0]
0x180047cfd  xor     edx, edx
0x180047cff  mov     rax, [rax+20h]
0x180047d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d08  mov     esi, eax
0x180047d0a  test    eax, eax
0x180047d0c  js      short loc_180047D3F
0x180047d0e  mov     [rbp+4Fh+var_CC], r12d
0x180047d12  mov     rcx, [rdi+100h]
0x180047d19  mov     rax, [rcx]
0x180047d1c  lea     r8, [rbp+4Fh+var_CC]
0x180047d20  lea     rdx, aDebugaudioinpu_0; "DebugAudioInputFile_PostMec"
0x180047d27  mov     rax, [rax+38h]
0x180047d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d30  mov     esi, eax
0x180047d32  cmp     [rbp+4Fh+var_CC], 1
0x180047d36  setz    al
0x180047d39  xchg    al, [rdi+1ECh]
0x180047d3f  test    esi, esi
0x180047d41  js      loc_180047DF5
0x180047d47  mov     eax, [rdi+108h]
0x180047d4d  sub     eax, 2
0x180047d50  mov     ecx, r12d
0x180047d53  cmp     eax, 1
0x180047d56  setbe   cl
0x180047d59  lea     r14, [rdi+1F0h]
0x180047d60  lea     r15, [rdi+200h]
0x180047d67  test    ecx, ecx
0x180047d69  jz      loc_180048038
0x180047d6f  mov     rcx, [rdi+100h]
0x180047d76  mov     rax, [rcx]
0x180047d79  mov     r8, r14
0x180047d7c  lea     rdx, aDebugaudioinpu_0; "DebugAudioInputFile_PostMec"
0x180047d83  mov     rax, [rax+48h]
0x180047d87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d8c  mov     esi, eax
0x180047d8e  mov     rcx, [rdi+100h]
0x180047d95  mov     rax, [rcx]
0x180047d98  mov     r8, r15
0x180047d9b  lea     rdx, aDisablespeechi; "DisableSpeechInput"
0x180047da2  mov     rax, [rax+48h]
0x180047da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047dab  mov     r12d, eax
0x180047dae  test    esi, esi
0x180047db0  js      short loc_180047DEB
0x180047db2  mov     r9, [rdi+100h]
0x180047db9  lea     rbx, [rdi+208h]
0x180047dc0  mov     rcx, [r9]
0x180047dc3  mov     rax, [rcx+48h]
0x180047dc7  mov     r8, rbx
0x180047dca  lea     rdx, aAarstart; "AarStart"
0x180047dd1  mov     rcx, r9
0x180047dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047dd9  mov     esi, eax
0x180047ddb  test    eax, eax
0x180047ddd  js      short loc_180047DEB
0x180047ddf  test    r12d, r12d
0x180047de2  jns     loc_180048033
0x180047de8  mov     esi, r12d
0x180047deb  xor     r12d, r12d
0x180047dee  lea     r15, aCaudioorchestr_118; "CAudioOrchestrator::Initialize"
0x180047df5  mov     [rdi+1FEh], r12w
0x180047dfd  mov     rcx, rdi; this
0x180047e00  call    ?GetPolicy_MaskOutMicrophoneAudio@CAudioOrchestrator@@AEAAHXZ; CAudioOrchestrator::GetPolicy_MaskOutMicrophoneAudio(void)
0x180047e05  mov     [rdi+1F8h], eax
0x180047e0b  lea     r14, aOnecoreuapEndu_136; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180047e12  test    esi, esi
0x180047e14  js      loc_180047EAE
0x180047e1a  test    eax, eax
0x180047e1c  jz      short loc_180047E32
0x180047e1e  mov     r8, r15
0x180047e21  lea     rdx, aSTestAudioBuff; "[%s] Test: audio buffers from the micro"...
0x180047e28  mov     ecx, 8; int
0x180047e2d  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x180047e32  mov     rcx, rdi; this
0x180047e35  call    ?GetPolicy_RDCEnabled@CAudioOrchestrator@@AEAAHXZ; CAudioOrchestrator::GetPolicy_RDCEnabled(void)
0x180047e3a  test    eax, eax
0x180047e3c  jz      short loc_180047E4C
0x180047e3e  mov     rcx, rdi; this
0x180047e41  call    ?CreateRDC@CAudioOrchestrator@@AEAAJXZ; CAudioOrchestrator::CreateRDC(void)
0x180047e46  mov     esi, eax
0x180047e48  test    eax, eax
0x180047e4a  js      short loc_180047EAE
0x180047e4c  mov     eax, 1
0x180047e51  xchg    al, cs:byte_1803B9EE8
0x180047e57  lea     rdx, [rdi+50h]; struct IPowerNotificationClient *
0x180047e5b  lea     rcx, [rdi+4E0h]; this
0x180047e62  mov     r8, [rdi+100h]; struct ISpAudioOrchestratorPolicy *
0x180047e69  call    ?Initialize@PowerNotificationProxy@@QEAAJPEAVIPowerNotificationClient@@PEAUISpAudioOrchestratorPolicy@@@Z; PowerNotificationProxy::Initialize(IPowerNotificationClient *,ISpAudioOrchestratorPolicy *)
0x180047e6e  mov     esi, eax
0x180047e70  test    eax, eax
0x180047e72  js      short loc_180047EAE
0x180047e74  mov     eax, [rdi+108h]
0x180047e7a  sub     eax, 2
0x180047e7d  cmp     eax, 1
0x180047e80  ja      short loc_180047EAE
0x180047e82  mov     rcx, rdi; this
0x180047e85  call    ?IsCortanaScreenRestrictedSupported@CAudioOrchestrator@@AEAAHXZ; CAudioOrchestrator::IsCortanaScreenRestrictedSupported(void)
0x180047e8a  test    eax, eax
0x180047e8c  jnz     short loc_180047EAE
0x180047e8e  mov     rcx, rdi; this
0x180047e91  call    ?SubscribeToInputSuppression@CAudioOrchestrator@@AEAAJXZ; CAudioOrchestrator::SubscribeToInputSuppression(void)
0x180047e96  mov     rcx, [rbp+57h]; this
0x180047e9a  test    eax, eax
0x180047e9c  jns     short loc_180047EAE
0x180047e9e  mov     r9d, eax; char *
0x180047ea1  mov     r8, r14; unsigned int
0x180047ea4  mov     edx, 3C1h; void *
0x180047ea9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180047eae  mov     [rsp+110h+var_D0], 1
0x180047eb6  lea     rcx, [rbp+4Fh+var_C0]
0x180047eba  call    ?Instance@SRCloudPolicy@@SA?AV?$shared_ptr@VOneSettingsPolicyWrapper@@@std@@XZ; SRCloudPolicy::Instance(void)
0x180047ebf  nop
0x180047ec0  lea     r8, [rsp+110h+var_D0]; unsigned int *
0x180047ec5  lea     rdx, aS3systemhwkwss; "S3SystemHWKWSScreenOffAC"
0x180047ecc  mov     rcx, [rax]; this
0x180047ecf  call    ?GetDWORDValue@OneSettingsPolicyWrapper@@QEAAJPEBGPEAK@Z; OneSettingsPolicyWrapper::GetDWORDValue(ushort const *,ulong *)
0x180047ed4  mov     rcx, [rbp+57h]; this
0x180047ed8  test    eax, eax
0x180047eda  jns     short loc_180047EED
0x180047edc  mov     r9d, eax; char *
0x180047edf  mov     r8, r14; unsigned int
0x180047ee2  mov     edx, 3C5h; void *
0x180047ee7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180047eec  nop
0x180047eed  mov     rcx, [rbp+4Fh+var_B8]; this
0x180047ef1  test    rcx, rcx
0x180047ef4  jz      short loc_180047EFB
0x180047ef6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180047efb  mov     eax, r12d
0x180047efe  cmp     [rsp+110h+var_D0], r12d
0x180047f03  setnbe  al
0x180047f06  mov     [rdi+3A0h], eax
  ... truncated ...
```
