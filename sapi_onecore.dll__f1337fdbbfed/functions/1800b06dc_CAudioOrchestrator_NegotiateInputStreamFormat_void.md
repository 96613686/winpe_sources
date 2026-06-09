# CAudioOrchestrator::NegotiateInputStreamFormat(void)

- ea: `0x1800b06dc`
- end: `0x1800b0c83`
- name: `?NegotiateInputStreamFormat@CAudioOrchestrator@@AEAAJXZ`
- size: `1447`
- prototype: `__int64 __fastcall(CAudioOrchestrator *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800b3b38`

## callees

- `0x18000be70`
- `0x18000bec4`
- `0x180049bfc`
- `0x180052af4`
- `0x180062eec`
- `0x18007379c`
- `0x1800741c8`
- `0x180079e30`
- `0x1800a156c`
- `0x1800a5bc4`
- `0x1800aa9c0`
- `0x1800ab484`
- `0x1800ad210`
- `0x1800adcdc`
- `0x1800ae134`
- `0x1800ae2cc`
- `0x1800ae300`
- `0x1800b06dc`
- `0x1800b39b8`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b0712`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b0712`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0c19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0c24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0c45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0c50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0c19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0c24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0c45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0c50`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CAudioOrchestrator::NegotiateInputStreamFormat(CAudioOrchestrator *this)
{
  CAudioOrchestrator *v2; // rcx
  int CurrentInputFamily; // esi
  unsigned __int16 v4; // r8
  int v5; // r15d
  GUID v6; // xmm0
  struct ISpAudio *v7; // rdi
  int v8; // ebx
  CAudioOrchestrator *v9; // rcx
  int v10; // r15d
  CAudioOrchestrator *v11; // rcx
  CAudioOrchestrator *v12; // rcx
  int (__fastcall ***v13)(_QWORD, GUID *, char *); // rbx
  _QWORD *v14; // r12
  _QWORD *v15; // rdi
  struct ISpStreamFormat *v16; // rdi
  char *v17; // rbx
  int v19[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct ISpStreamFormat *v20; // [rsp+48h] [rbp-B8h] BYREF
  struct ISpStreamFormat *v21; // [rsp+50h] [rbp-B0h] BYREF
  struct ISpAudio *v22; // [rsp+58h] [rbp-A8h] BYREF
  char *v23; // [rsp+60h] [rbp-A0h] BYREF
  int v24; // [rsp+68h] [rbp-98h]
  GUID v25; // [rsp+70h] [rbp-90h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-80h]
  int v27; // [rsp+88h] [rbp-78h]
  GUID v28; // [rsp+90h] [rbp-70h] BYREF
  LPVOID v29; // [rsp+A0h] [rbp-60h]
  int v30; // [rsp+A8h] [rbp-58h]
  struct _GUID v31; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID v32; // [rsp+C0h] [rbp-40h]
  int v33; // [rsp+C8h] [rbp-38h]
  GUID v34; // [rsp+D0h] [rbp-30h] BYREF
  LPVOID v35; // [rsp+E0h] [rbp-20h]
  int v36; // [rsp+E8h] [rbp-18h]

  v23 = (char *)this + 160;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 4);
  v24 = 0;
  v28 = GUID_NULL;
  v29 = 0;
  v30 = 0;
  v34 = GUID_NULL;
  v35 = 0;
  v36 = 0;
  v21 = 0;
  v22 = 0;
  CurrentInputFamily = CAudioOrchestratorInput::GetCurrentInputFamily(
                         (CAudioOrchestrator *)((char *)this + 600),
                         &v21,
                         &v22,
                         0,
                         0);
  if ( CurrentInputFamily >= 0 )
  {
    CurrentInputFamily = CAudioOrchestrator::Get32bitFloat16KhzFormat(v2, (struct CSpStreamFormat *)&v34, v4);
    if ( CurrentInputFamily >= 0 )
    {
      CurrentInputFamily = CSpStreamFormat::AssignFormat((CSpStreamFormat *)&v28, v21);
      if ( CurrentInputFamily >= 0 )
        CAudioOrchestrator::AudioFormatTraceMessage(
          v2,
          "Original input stream format is [%S]",
          (struct CSpStreamFormat *)&v28);
    }
  }
  v5 = 1;
  v6 = GUID_NULL;
  v31 = GUID_NULL;
  v32 = 0;
  v33 = 0;
  v19[0] = 0;
  v7 = v22;
  if ( CurrentInputFamily >= 0 && (unsigned int)(*((_DWORD *)this + 66) - 2) <= 1 )
  {
    if ( (unsigned int)CAudioOrchestrator::GetPolicy_VAEnabled(this)
      && (unsigned int)CAudioOrchestrator::GetPolicy_SoftwareVAInSKU(this)
      && (v8 = *((_DWORD *)this + 239), v8 != CAudioOrchestrator::GetPolicy_MVATargetVersion(this))
      || *((_DWORD *)this + 230) )
    {
      CAudioOrchestrator::AudioFormatTraceMessage(v2, "VA Master format is [%S]", (struct CSpStreamFormat *)&v34);
      CurrentInputFamily = CSpStreamFormat::CopyTo((CSpStreamFormat *)&v34, (struct _GUID *)this + 24);
      if ( CurrentInputFamily >= 0 )
      {
        CAudioOrchestrator::AudioFormatTraceMessage(
          v2,
          "TO-BE-NEGOTIATED input stream format (for VA Master) is [%S]",
          (struct CSpStreamFormat *)&v34);
        CurrentInputFamily = CSpStreamFormat::CopyTo((CSpStreamFormat *)&v34, &v31);
        if ( CurrentInputFamily >= 0 && v7 && *((_DWORD *)this + 121) )
          CurrentInputFamily = CAudioOrchestrator::SetInputStreamAudioFormat(
                                 this,
                                 (CAudioOrchestrator *)((char *)this + 384),
                                 (struct CSpStreamFormat *)&v28,
                                 v19);
      }
      v5 = 0;
    }
    v6 = GUID_NULL;
  }
  v25 = v6;
  pv = 0;
  v27 = 0;
  if ( CurrentInputFamily >= 0 )
  {
    if ( v7 && *((_DWORD *)this + 121) && v5 )
    {
      CurrentInputFamily = CAudioOrchestrator::GetSREngineFormat(this, (struct CSpStreamFormat *)&v25, 0);
      if ( CurrentInputFamily >= 0 )
      {
        CAudioOrchestrator::AudioFormatTraceMessage(v2, "Default engine format is [%S]", (struct CSpStreamFormat *)&v25);
        CurrentInputFamily = CAudioOrchestrator::SetInputStreamAudioFormat(
                               this,
                               (struct CSpStreamFormat *)&v25,
                               (struct CSpStreamFormat *)&v28,
                               v19);
        if ( CurrentInputFamily >= 0 )
        {
          if ( v19[0]
            || (CurrentInputFamily = CAudioOrchestrator::GetSREngineFormat(
                                       this,
                                       (struct CSpStreamFormat *)&v25,
                                       (struct CSpStreamFormat *)&v28),
                CurrentInputFamily >= 0) )
          {
            CAudioOrchestrator::AudioFormatTraceMessage(
              v2,
              "TO-BE-NEGOTIATED input stream format (for SR engine) is [%S]",
              (struct CSpStreamFormat *)&v25);
LABEL_29:
            CurrentInputFamily = CSpStreamFormat::CopyTo((CSpStreamFormat *)&v25, &v31);
          }
        }
      }
    }
    else
    {
      CurrentInputFamily = CAudioOrchestrator::GetSREngineFormat(
                             this,
                             (struct CSpStreamFormat *)&v25,
                             (struct CSpStreamFormat *)&v28);
      if ( CurrentInputFamily >= 0 )
      {
        CAudioOrchestrator::AudioFormatTraceMessage(
          v2,
          "Closest engine format {given input stream format} is [%S]",
          (struct CSpStreamFormat *)&v25);
        CAudioOrchestrator::AudioFormatTraceMessage(
          v9,
          "TO-BE-NEGOTIATED input stream format (for SR engine) is [%S]",
          (struct CSpStreamFormat *)&v25);
        if ( v5 )
          goto LABEL_29;
      }
    }
  }
  v10 = 0;
  v19[0] = 0;
  v20 = 0;
  if ( CurrentInputFamily >= 0 )
  {
    CurrentInputFamily = CAudioOrchestrator::ConvertInputStreamFormat(
                           v2,
                           v21,
                           (struct CSpStreamFormat *)&v28,
                           (struct CSpStreamFormat *)&v31,
                           *((_DWORD *)this + 120),
                           v19,
                           &v20);
    if ( CurrentInputFamily >= 0 )
    {
      CAudioOrchestrator::AudioFormatTraceMessage(
        v11,
        "Set-up format converter: Converting from input stream format [%S]",
        (struct CSpStreamFormat *)&v28);
      CAudioOrchestrator::AudioFormatTraceMessage(
        v12,
        "Set-up format converter: Converting to NEGOTIATED format [%S]",
        (struct CSpStreamFormat *)&v31);
    }
    v10 = v19[0];
  }
  *(_QWORD *)v19 = 0;
  if ( CurrentInputFamily >= 0 )
  {
    CurrentInputFamily = CAudioOrchestratorInput::GetInputFamily((char *)this + 600, 3, 0, v19, 0, 0);
    if ( CurrentInputFamily >= 0 )
    {
      v13 = *(int (__fastcall ****)(_QWORD, GUID *, char *))v19;
      if ( !*(_QWORD *)v19
        || (CurrentInputFamily = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *, LPVOID))(**(_QWORD **)v19 + 128LL))(
                                   *(_QWORD *)v19,
                                   &v31,
                                   v32),
            CurrentInputFamily >= 0) )
      {
        CurrentInputFamily = CSpStreamFormat::CopyTo((CSpStreamFormat *)&v28, (struct _GUID *)this + 20);
        if ( CurrentInputFamily >= 0
          && (CurrentInputFamily = CSpStreamFormat::CopyTo((CSpStreamFormat *)&v25, (struct _GUID *)this + 22),
              CurrentInputFamily >= 0)
          && (CurrentInputFamily = CSpStreamFormat::CopyTo((CSpStreamFormat *)&v31, (struct _GUID *)this + 26),
              CurrentInputFamily >= 0) )
        {
          if ( v7 )
          {
            v14 = (_QWORD *)((char *)this + 1024);
            if ( ((__int64 (__fastcall *)(struct ISpAudio *, GUID *, char *))v7->lpVtbl->QueryInterface)(
                   v7,
                   &GUID_be7a9cce_5f9e_11d2_960f_00c04f8ee628,
                   (char *)this + 1024) >= 0 )
            {
              CurrentInputFamily = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v14 + 24LL))(
                                     *v14,
                                     *((_QWORD *)this + 131));
              if ( CurrentInputFamily < 0 )
                goto LABEL_60;
              CurrentInputFamily = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v14 + 80LL))(
                                     *v14,
                                     *((_QWORD *)this + 132),
                                     *((_QWORD *)this + 132));
            }
            if ( CurrentInputFamily < 0 )
              goto LABEL_60;
          }
          if ( !v13
            || (v15 = (_QWORD *)((char *)this + 1032),
                (**v13)(v13, &GUID_be7a9cce_5f9e_11d2_960f_00c04f8ee628, (char *)this + 1032) < 0)
            || (CurrentInputFamily = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v15 + 24LL))(
                                       *v15,
                                       *((_QWORD *)this + 131)),
                CurrentInputFamily >= 0)
            && (CurrentInputFamily = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v15 + 80LL))(
                                       *v15,
                                       *((_QWORD *)this + 132),
                                       *((_QWORD *)this + 132)),
                CurrentInputFamily >= 0) )
          {
            *((_DWORD *)this + 136) = v10;
            if ( v10 )
            {
              v16 = v20;
              v20 = 0;
              if ( v16 )
              {
                switch ( *((_DWORD *)this + 152) )
                {
                  case 1:
                    v17 = (char *)this + 632;
                    break;
                  case 2:
                    v17 = (char *)this + 616;
                    break;
                  case 3:
                    v17 = (char *)this + 664;
                    break;
                  default:
                    goto LABEL_60;
                }
                ATL::CComPtrBase<ISpCFGInterpreter>::Release(v17);
                ATL::CComPtrBase<ISpStreamFormat>::Attach(v17, v16);
              }
            }
          }
        }
        else
        {
          CSpStreamFormat::Clear((CAudioOrchestrator *)((char *)this + 320));
          CSpStreamFormat::Clear((CAudioOrchestrator *)((char *)this + 352));
          CSpStreamFormat::Clear((CAudioOrchestrator *)((char *)this + 384));
          CSpStreamFormat::Clear((CAudioOrchestrator *)((char *)this + 416));
        }
      }
    }
  }
LABEL_60:
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(v19);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v20);
  CoTaskMemFree(pv);
  CoTaskMemFree(v32);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v22);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v21);
  CoTaskMemFree(v35);
  CoTaskMemFree(v29);
  CSPAutoCritSecLock::~CSPAutoCritSecLock((CSPAutoCritSecLock *)&v23);
  return (unsigned int)CurrentInputFamily;
}

```

## disassembly

```asm
0x1800b06dc  push    rbp
0x1800b06de  push    rbx
0x1800b06df  push    rsi
0x1800b06e0  push    rdi
0x1800b06e1  push    r12
0x1800b06e3  push    r13
0x1800b06e5  push    r14
0x1800b06e7  push    r15
0x1800b06e9  lea     rbp, [rsp-8]
0x1800b06ee  sub     rsp, 108h
0x1800b06f5  mov     rax, cs:__security_cookie
0x1800b06fc  xor     rax, rsp
0x1800b06ff  mov     [rbp+40h+var_50], rax
0x1800b0703  mov     r14, rcx
0x1800b0706  add     rcx, 0A0h; lpCriticalSection
0x1800b070d  mov     [rsp+140h+var_E0], rcx
0x1800b0712  call    cs:__imp_EnterCriticalSection
0x1800b0718  xor     r13d, r13d
0x1800b071b  mov     [rsp+140h+var_D8], r13d
0x1800b0720  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800b0727  movdqu  [rbp+40h+var_B0], xmm0
0x1800b072c  mov     [rbp+40h+var_A0], r13
0x1800b0730  mov     [rbp+40h+var_98], r13d
0x1800b0734  movdqu  [rbp+40h+var_70], xmm0
0x1800b0739  mov     [rbp+40h+var_60], r13
0x1800b073d  mov     [rbp+40h+var_58], r13d
0x1800b0741  mov     [rsp+140h+var_F0], r13
0x1800b0746  mov     [rsp+140h+var_E8], r13
0x1800b074b  lea     r12, [r14+258h]
0x1800b0752  mov     [rsp+140h+var_120], r13; struct ISpInputDeviceSupport **
0x1800b0757  xor     r9d, r9d; struct ISpAudioStream **
0x1800b075a  lea     r8, [rsp+140h+var_E8]; struct ISpAudio **
0x1800b075f  lea     rdx, [rsp+140h+var_F0]; struct ISpStreamFormat **
0x1800b0764  mov     rcx, r12; this
0x1800b0767  call    ?GetCurrentInputFamily@CAudioOrchestratorInput@@QEAAJPEAPEAUISpStreamFormat@@PEAPEAUISpAudio@@PEAPEAUISpAudioStream@@PEAPEAUISpInputDeviceSupport@@@Z; CAudioOrchestratorInput::GetCurrentInputFamily(ISpStreamFormat * *,ISpAudio * *,ISpAudioStream * *,ISpInputDeviceSupport * *)
0x1800b076c  mov     esi, eax
0x1800b076e  test    eax, eax
0x1800b0770  js      short loc_1800B07A5
0x1800b0772  lea     rdx, [rbp+40h+var_70]; struct CSpStreamFormat *
0x1800b0776  call    ?Get32bitFloat16KhzFormat@CAudioOrchestrator@@AEAAJPEAVCSpStreamFormat@@G@Z; CAudioOrchestrator::Get32bitFloat16KhzFormat(CSpStreamFormat *,ushort)
0x1800b077b  mov     esi, eax
0x1800b077d  test    eax, eax
0x1800b077f  js      short loc_1800B07A5
0x1800b0781  mov     rdx, [rsp+140h+var_F0]; struct ISpStreamFormat *
0x1800b0786  lea     rcx, [rbp+40h+var_B0]; this
0x1800b078a  call    ?AssignFormat@CSpStreamFormat@@QEAAJPEAUISpStreamFormat@@@Z; CSpStreamFormat::AssignFormat(ISpStreamFormat *)
0x1800b078f  mov     esi, eax
0x1800b0791  test    eax, eax
0x1800b0793  js      short loc_1800B07A5
0x1800b0795  lea     r8, [rbp+40h+var_B0]; struct CSpStreamFormat *
0x1800b0799  lea     rdx, aOriginalInputS; "Original input stream format is [%S]"
0x1800b07a0  call    ?AudioFormatTraceMessage@CAudioOrchestrator@@AEAAXPEADAEAVCSpStreamFormat@@@Z; CAudioOrchestrator::AudioFormatTraceMessage(char *,CSpStreamFormat &)
0x1800b07a5  mov     r15d, 1
0x1800b07ab  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800b07b2  movdqu  xmmword ptr [rbp+40h+var_90.Data1], xmm0
0x1800b07b7  mov     [rbp+40h+var_80], r13
0x1800b07bb  mov     [rbp+40h+var_78], r13d
0x1800b07bf  mov     [rsp+140h+var_100], r13d
0x1800b07c4  mov     rdi, [rsp+140h+var_E8]
0x1800b07c9  test    esi, esi
0x1800b07cb  js      loc_1800B0892
0x1800b07d1  mov     eax, [r14+108h]
0x1800b07d8  sub     eax, 2
0x1800b07db  cmp     eax, r15d
0x1800b07de  ja      loc_1800B0892
0x1800b07e4  mov     rcx, r14; this
0x1800b07e7  call    ?GetPolicy_VAEnabled@CAudioOrchestrator@@AEAAHXZ; CAudioOrchestrator::GetPolicy_VAEnabled(void)
0x1800b07ec  test    eax, eax
0x1800b07ee  jz      short loc_1800B080F
0x1800b07f0  mov     rcx, r14; this
0x1800b07f3  call    ?GetPolicy_SoftwareVAInSKU@CAudioOrchestrator@@AEAAHXZ; CAudioOrchestrator::GetPolicy_SoftwareVAInSKU(void)
0x1800b07f8  test    eax, eax
0x1800b07fa  jz      short loc_1800B080F
0x1800b07fc  mov     ebx, [r14+3BCh]
0x1800b0803  mov     rcx, r14; this
0x1800b0806  call    ?GetPolicy_MVATargetVersion@CAudioOrchestrator@@AEAAKXZ; CAudioOrchestrator::GetPolicy_MVATargetVersion(void)
0x1800b080b  cmp     ebx, eax
0x1800b080d  jnz     short loc_1800B0818
0x1800b080f  cmp     [r14+398h], r13d
0x1800b0816  jz      short loc_1800B088B
0x1800b0818  lea     r8, [rbp+40h+var_70]; struct CSpStreamFormat *
0x1800b081c  lea     rdx, aVaMasterFormat; "VA Master format is [%S]"
0x1800b0823  call    ?AudioFormatTraceMessage@CAudioOrchestrator@@AEAAXPEADAEAVCSpStreamFormat@@@Z; CAudioOrchestrator::AudioFormatTraceMessage(char *,CSpStreamFormat &)
0x1800b0828  lea     rbx, [r14+180h]
0x1800b082f  mov     rdx, rbx; struct _GUID *
0x1800b0832  lea     rcx, [rbp+40h+var_70]; this
0x1800b0836  call    ?CopyTo@CSpStreamFormat@@QEBAJAEAV1@@Z; CSpStreamFormat::CopyTo(CSpStreamFormat &)
0x1800b083b  mov     esi, eax
0x1800b083d  test    eax, eax
0x1800b083f  js      short loc_1800B0888
0x1800b0841  lea     r8, [rbp+40h+var_70]; struct CSpStreamFormat *
0x1800b0845  lea     rdx, aToBeNegotiated; "TO-BE-NEGOTIATED input stream format (f"...
0x1800b084c  call    ?AudioFormatTraceMessage@CAudioOrchestrator@@AEAAXPEADAEAVCSpStreamFormat@@@Z; CAudioOrchestrator::AudioFormatTraceMessage(char *,CSpStreamFormat &)
0x1800b0851  lea     rdx, [rbp+40h+var_90]; struct _GUID *
0x1800b0855  lea     rcx, [rbp+40h+var_70]; this
0x1800b0859  call    ?CopyTo@CSpStreamFormat@@QEBAJAEAV1@@Z; CSpStreamFormat::CopyTo(CSpStreamFormat &)
0x1800b085e  mov     esi, eax
0x1800b0860  test    eax, eax
0x1800b0862  js      short loc_1800B0888
0x1800b0864  test    rdi, rdi
0x1800b0867  jz      short loc_1800B0888
0x1800b0869  cmp     [r14+1E4h], r13d
0x1800b0870  jz      short loc_1800B0888
0x1800b0872  lea     r9, [rsp+140h+var_100]; int *
0x1800b0877  lea     r8, [rbp+40h+var_B0]; struct CSpStreamFormat *
0x1800b087b  mov     rdx, rbx; struct CSpStreamFormat *
0x1800b087e  mov     rcx, r14; this
0x1800b0881  call    ?SetInputStreamAudioFormat@CAudioOrchestrator@@AEAAJPEAVCSpStreamFormat@@0PEAH@Z; CAudioOrchestrator::SetInputStreamAudioFormat(CSpStreamFormat *,CSpStreamFormat *,int *)
0x1800b0886  mov     esi, eax
0x1800b0888  mov     r15d, r13d
0x1800b088b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800b0892  movdqu  [rsp+140h+var_D0], xmm0
0x1800b0898  mov     [rbp+40h+pv], r13
0x1800b089c  mov     [rbp+40h+var_B8], r13d
0x1800b08a0  test    esi, esi
0x1800b08a2  js      loc_1800B0985
0x1800b08a8  test    rdi, rdi
0x1800b08ab  jz      loc_1800B0937
0x1800b08b1  cmp     [r14+1E4h], r13d
0x1800b08b8  jz      short loc_1800B0937
0x1800b08ba  test    r15d, r15d
0x1800b08bd  jz      short loc_1800B0937
0x1800b08bf  xor     r8d, r8d; struct CSpStreamFormat *
0x1800b08c2  lea     rdx, [rsp+140h+var_D0]; struct CSpStreamFormat *
0x1800b08c7  mov     rcx, r14; this
0x1800b08ca  call    ?GetSREngineFormat@CAudioOrchestrator@@AEAAJPEAVCSpStreamFormat@@0@Z; CAudioOrchestrator::GetSREngineFormat(CSpStreamFormat *,CSpStreamFormat *)
0x1800b08cf  mov     esi, eax
0x1800b08d1  test    eax, eax
0x1800b08d3  js      loc_1800B0985
0x1800b08d9  lea     r8, [rsp+140h+var_D0]; struct CSpStreamFormat *
0x1800b08de  lea     rdx, aDefaultEngineF; "Default engine format is [%S]"
0x1800b08e5  call    ?AudioFormatTraceMessage@CAudioOrchestrator@@AEAAXPEADAEAVCSpStreamFormat@@@Z; CAudioOrchestrator::AudioFormatTraceMessage(char *,CSpStreamFormat &)
0x1800b08ea  lea     r9, [rsp+140h+var_100]; int *
0x1800b08ef  lea     r8, [rbp+40h+var_B0]; struct CSpStreamFormat *
0x1800b08f3  lea     rdx, [rsp+140h+var_D0]; struct CSpStreamFormat *
0x1800b08f8  mov     rcx, r14; this
0x1800b08fb  call    ?SetInputStreamAudioFormat@CAudioOrchestrator@@AEAAJPEAVCSpStreamFormat@@0PEAH@Z; CAudioOrchestrator::SetInputStreamAudioFormat(CSpStreamFormat *,CSpStreamFormat *,int *)
0x1800b0900  mov     esi, eax
0x1800b0902  test    eax, eax
0x1800b0904  js      short loc_1800B0985
0x1800b0906  cmp     [rsp+140h+var_100], r13d
0x1800b090b  jnz     short loc_1800B0924
0x1800b090d  lea     r8, [rbp+40h+var_B0]; struct CSpStreamFormat *
0x1800b0911  lea     rdx, [rsp+140h+var_D0]; struct CSpStreamFormat *
0x1800b0916  mov     rcx, r14; this
0x1800b0919  call    ?GetSREngineFormat@CAudioOrchestrator@@AEAAJPEAVCSpStreamFormat@@0@Z; CAudioOrchestrator::GetSREngineFormat(CSpStreamFormat *,CSpStreamFormat *)
0x1800b091e  mov     esi, eax
0x1800b0920  test    eax, eax
0x1800b0922  js      short loc_1800B0985
0x1800b0924  lea     r8, [rsp+140h+var_D0]; struct CSpStreamFormat *
0x1800b0929  lea     rdx, aToBeNegotiated_0; "TO-BE-NEGOTIATED input stream format (f"...
0x1800b0930  call    ?AudioFormatTraceMessage@CAudioOrchestrator@@AEAAXPEADAEAVCSpStreamFormat@@@Z; CAudioOrchestrator::AudioFormatTraceMessage(char *,CSpStreamFormat &)
0x1800b0935  jmp     short loc_1800B0975
0x1800b0937  lea     r8, [rbp+40h+var_B0]; struct CSpStreamFormat *
0x1800b093b  lea     rdx, [rsp+140h+var_D0]; struct CSpStreamFormat *
0x1800b0940  mov     rcx, r14; this
0x1800b0943  call    ?GetSREngineFormat@CAudioOrchestrator@@AEAAJPEAVCSpStreamFormat@@0@Z; CAudioOrchestrator::GetSREngineFormat(CSpStreamFormat *,CSpStreamFormat *)
0x1800b0948  mov     esi, eax
0x1800b094a  test    eax, eax
0x1800b094c  js      short loc_1800B0985
0x1800b094e  lea     r8, [rsp+140h+var_D0]; struct CSpStreamFormat *
0x1800b0953  lea     rdx, aClosestEngineF; "Closest engine format {given input stre"...
0x1800b095a  call    ?AudioFormatTraceMessage@CAudioOrchestrator@@AEAAXPEADAEAVCSpStreamFormat@@@Z; CAudioOrchestrator::AudioFormatTraceMessage(char *,CSpStreamFormat &)
0x1800b095f  lea     r8, [rsp+140h+var_D0]; struct CSpStreamFormat *
0x1800b0964  lea     rdx, aToBeNegotiated_0; "TO-BE-NEGOTIATED input stream format (f"...
0x1800b096b  call    ?AudioFormatTraceMessage@CAudioOrchestrator@@AEAAXPEADAEAVCSpStreamFormat@@@Z; CAudioOrchestrator::AudioFormatTraceMessage(char *,CSpStreamFormat &)
0x1800b0970  test    r15d, r15d
0x1800b0973  jz      short loc_1800B0985
0x1800b0975  lea     rdx, [rbp+40h+var_90]; struct _GUID *
0x1800b0979  lea     rcx, [rsp+140h+var_D0]; this
0x1800b097e  call    ?CopyTo@CSpStreamFormat@@QEBAJAEAV1@@Z; CSpStreamFormat::CopyTo(CSpStreamFormat &)
0x1800b0983  mov     esi, eax
0x1800b0985  mov     r15d, r13d
0x1800b0988  mov     [rsp+140h+var_100], r13d
0x1800b098d  mov     [rsp+140h+var_F8], r13
0x1800b0992  test    esi, esi
0x1800b0994  js      short loc_1800B09F2
0x1800b0996  lea     rax, [rsp+140h+var_F8]
0x1800b099b  mov     [rsp+140h+var_110], rax; struct ISpStreamFormat **
0x1800b09a0  lea     rax, [rsp+140h+var_100]
0x1800b09a5  mov     [rsp+140h+var_118], rax; int *
0x1800b09aa  mov     eax, [r14+1E0h]
0x1800b09b1  mov     dword ptr [rsp+140h+var_120], eax; int
0x1800b09b5  lea     r9, [rbp+40h+var_90]; struct CSpStreamFormat *
0x1800b09b9  lea     r8, [rbp+40h+var_B0]; struct CSpStreamFormat *
0x1800b09bd  mov     rdx, [rsp+140h+var_F0]; struct ISpStreamFormat *
0x1800b09c2  call    ?ConvertInputStreamFormat@CAudioOrchestrator@@AEAAJPEAUISpStreamFormat@@AEAVCSpStreamFormat@@1HPEAHPEAPEAU2@@Z; CAudioOrchestrator::ConvertInputStreamFormat(ISpStreamFormat *,CSpStreamFormat &,CSpStreamFormat &,int,int *,ISpStreamFormat * *)
0x1800b09c7  mov     esi, eax
0x1800b09c9  test    eax, eax
0x1800b09cb  js      short loc_1800B09ED
0x1800b09cd  lea     r8, [rbp+40h+var_B0]; struct CSpStreamFormat *
0x1800b09d1  lea     rdx, aSetUpFormatCon_0; "Set-up format converter: Converting fro"...
0x1800b09d8  call    ?AudioFormatTraceMessage@CAudioOrchestrator@@AEAAXPEADAEAVCSpStreamFormat@@@Z; CAudioOrchestrator::AudioFormatTraceMessage(char *,CSpStreamFormat &)
0x1800b09dd  lea     r8, [rbp+40h+var_90]; struct CSpStreamFormat *
0x1800b09e1  lea     rdx, aSetUpFormatCon; "Set-up format converter: Converting to "...
0x1800b09e8  call    ?AudioFormatTraceMessage@CAudioOrchestrator@@AEAAXPEADAEAVCSpStreamFormat@@@Z; CAudioOrchestrator::AudioFormatTraceMessage(char *,CSpStreamFormat &)
0x1800b09ed  mov     r15d, [rsp+140h+var_100]
0x1800b09f2  mov     qword ptr [rsp+140h+var_100], r13
0x1800b09f7  test    esi, esi
0x1800b09f9  js      loc_1800B0BFF
0x1800b09ff  mov     [rsp+140h+var_118], r13
0x1800b0a04  mov     [rsp+140h+var_120], r13
0x1800b0a09  lea     r9, [rsp+140h+var_100]
0x1800b0a0e  xor     r8d, r8d
0x1800b0a11  lea     edx, [r8+3]
0x1800b0a15  mov     rcx, r12
0x1800b0a18  call    ?GetInputFamily@CAudioOrchestratorInput@@QEAAJW4SPSTREAMSOURCE@@PEAPEAUISpStreamFormat@@PEAPEAUISpAudio@@PEAPEAUISpAudioStream@@PEAPEAUISpInputDeviceSupport@@@Z; CAudioOrchestratorInput::GetInputFamily(SPSTREAMSOURCE,ISpStreamFormat * *,ISpAudio * *,ISpAudioStream * *,ISpInputDeviceSupport * *)
0x1800b0a1d  mov     esi, eax
0x1800b0a1f  test    eax, eax
0x1800b0a21  js      loc_1800B0BFF
0x1800b0a27  mov     rbx, qword ptr [rsp+140h+var_100]
0x1800b0a2c  test    rbx, rbx
0x1800b0a2f  jz      short loc_1800B0A55
0x1800b0a31  mov     rax, [rbx]
0x1800b0a34  mov     r8, [rbp+40h+var_80]
0x1800b0a38  lea     rdx, [rbp+40h+var_90]
0x1800b0a3c  mov     rcx, rbx
0x1800b0a3f  mov     rax, [rax+80h]
0x1800b0a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0a4b  mov     esi, eax
0x1800b0a4d  test    eax, eax
0x1800b0a4f  js      loc_1800B0BFF
0x1800b0a55  lea     r12, [r14+140h]
0x1800b0a5c  mov     rdx, r12; struct _GUID *
0x1800b0a5f  lea     rcx, [rbp+40h+var_B0]; this
0x1800b0a63  call    ?CopyTo@CSpStreamFormat@@QEBAJAEAV1@@Z; CSpStreamFormat::CopyTo(CSpStreamFormat &)
0x1800b0a68  mov     esi, eax
0x1800b0a6a  test    eax, eax
0x1800b0a6c  js      short loc_1800B0A9B
0x1800b0a6e  lea     rdx, [r14+160h]; struct _GUID *
0x1800b0a75  lea     rcx, [rsp+140h+var_D0]; this
0x1800b0a7a  call    ?CopyTo@CSpStreamFormat@@QEBAJAEAV1@@Z; CSpStreamFormat::CopyTo(CSpStreamFormat &)
0x1800b0a7f  mov     esi, eax
0x1800b0a81  test    eax, eax
0x1800b0a83  js      short loc_1800B0A9B
0x1800b0a85  lea     rdx, [r14+1A0h]; struct _GUID *
0x1800b0a8c  lea     rcx, [rbp+40h+var_90]; this
0x1800b0a90  call    ?CopyTo@CSpStreamFormat@@QEBAJAEAV1@@Z; CSpStreamFormat::CopyTo(CSpStreamFormat &)
0x1800b0a95  mov     esi, eax
0x1800b0a97  test    eax, eax
0x1800b0a99  jns     short loc_1800B0ACF
0x1800b0a9b  mov     rcx, r12; this
0x1800b0a9e  call    ?Clear@CSpStreamFormat@@QEAAXXZ; CSpStreamFormat::Clear(void)
0x1800b0aa3  lea     rcx, [r14+160h]; this
0x1800b0aaa  call    ?Clear@CSpStreamFormat@@QEAAXXZ; CSpStreamFormat::Clear(void)
0x1800b0aaf  lea     rcx, [r14+180h]; this
0x1800b0ab6  call    ?Clear@CSpStreamFormat@@QEAAXXZ; CSpStreamFormat::Clear(void)
0x1800b0abb  lea     rcx, [r14+1A0h]; this
0x1800b0ac2  call    ?Clear@CSpStreamFormat@@QEAAXXZ; CSpStreamFormat::Clear(void)
0x1800b0ac7  test    esi, esi
0x1800b0ac9  js      loc_1800B0BFF
0x1800b0acf  test    rdi, rdi
0x1800b0ad2  jz      short loc_1800B0B3D
0x1800b0ad4  lea     r12, [r14+400h]
0x1800b0adb  mov     rax, [rdi]
0x1800b0ade  mov     r8, r12
0x1800b0ae1  lea     rdx, _GUID_be7a9cce_5f9e_11d2_960f_00c04f8ee628
0x1800b0ae8  mov     rcx, rdi
0x1800b0aeb  mov     rax, [rax]
0x1800b0aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0af3  nop
0x1800b0af4  test    eax, eax
0x1800b0af6  js      short loc_1800B0B35
0x1800b0af8  mov     rcx, [r12]
0x1800b0afc  mov     rax, [rcx]
0x1800b0aff  mov     rdx, [r14+418h]
0x1800b0b06  mov     rax, [rax+18h]
0x1800b0b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0b0f  mov     esi, eax
0x1800b0b11  test    eax, eax
0x1800b0b13  js      loc_1800B0BFF
0x1800b0b19  mov     rcx, [r12]
0x1800b0b1d  mov     rdx, [r14+420h]
0x1800b0b24  mov     rax, [rcx]
0x1800b0b27  mov     r8, rdx
0x1800b0b2a  mov     rax, [rax+50h]
0x1800b0b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0b33  mov     esi, eax
0x1800b0b35  test    esi, esi
0x1800b0b37  js      loc_1800B0BFF
0x1800b0b3d  test    rbx, rbx
0x1800b0b40  jz      short loc_1800B0BA1
0x1800b0b42  lea     rdi, [r14+408h]
0x1800b0b49  mov     rax, [rbx]
0x1800b0b4c  mov     r8, rdi
0x1800b0b4f  lea     rdx, _GUID_be7a9cce_5f9e_11d2_960f_00c04f8ee628
0x1800b0b56  mov     rcx, rbx
0x1800b0b59  mov     rax, [rax]
0x1800b0b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0b61  nop
0x1800b0b62  test    eax, eax
0x1800b0b64  js      short loc_1800B0BA1
0x1800b0b66  mov     rcx, [rdi]
0x1800b0b69  mov     rax, [rcx]
0x1800b0b6c  mov     rdx, [r14+418h]
0x1800b0b73  mov     rax, [rax+18h]
0x1800b0b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0b7c  mov     esi, eax
0x1800b0b7e  test    eax, eax
0x1800b0b80  js      short loc_1800B0BFF
  ... truncated ...
```
