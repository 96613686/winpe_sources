# CSingleViewShellExperience::OnEventQueued(Windows::Internal::Shell::Experience::IShellExperienceViewStateChangedEventArgs *)

- ea: `0x1800486b0`
- end: `0x180048a87`
- name: `?OnEventQueued@CSingleViewShellExperience@@AEAAJPEAUIShellExperienceViewStateChangedEventArgs@Experience@Shell@Internal@Windows@@@Z`
- size: `983`
- prototype: `__int64 __fastcall(CSingleViewShellExperience *__hidden this, struct Windows::Internal::Shell::Experience::IShellExperienceViewStateChangedEventArgs *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180048d14`

## callees

- `0x1800134f8`
- `0x1800237c8`
- `0x18002d790`
- `0x1800486b0`
- `0x180048a90`
- `0x180048b58`
- `0x180048bb8`
- `0x180048c5c`
- `0x180048c90`
- `0x1800d1d78`
- `0x180356360`
- `0x180356edc`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800487bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800488c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004896e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800489e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048a51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800487bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800488c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004896e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800489e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048a51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800486ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800486fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800487eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800487fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004880d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800486ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800486fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800487eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800487fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004880d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CSingleViewShellExperience::OnEventQueued(
        HSTRING *this,
        struct Windows::Internal::Shell::Experience::IShellExperienceViewStateChangedEventArgs *a2)
{
  const unsigned __int16 *StringRawBuffer; // rsi
  const unsigned __int16 *v5; // rdi
  __int64 (__fastcall *v6)(struct Windows::Internal::Shell::Experience::IShellExperienceViewStateChangedEventArgs *, HSTRING *); // rdi
  int v7; // eax
  unsigned int v8; // edi
  __int64 (__fastcall *v9)(struct Windows::Internal::Shell::Experience::IShellExperienceViewStateChangedEventArgs *, __int64 *); // rdi
  int v10; // eax
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v17; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  PCWSTR v20; // [rsp+40h] [rbp-C0h] BYREF
  PCWSTR v21; // [rsp+48h] [rbp-B8h] BYREF
  PCWSTR v22[2]; // [rsp+50h] [rbp-B0h] BYREF
  void **v23; // [rsp+60h] [rbp-A0h] BYREF
  int v24; // [rsp+68h] [rbp-98h] BYREF
  char v25; // [rsp+6Ch] [rbp-94h]
  int v26; // [rsp+90h] [rbp-70h] BYREF
  const char *v27; // [rsp+98h] [rbp-68h]
  __int64 v28; // [rsp+A0h] [rbp-60h]
  char v29; // [rsp+A8h] [rbp-58h]
  int v30; // [rsp+B0h] [rbp-50h]
  _BYTE v31[152]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v32; // [rsp+150h] [rbp+50h]
  int v33; // [rsp+160h] [rbp+60h]
  __int64 v34; // [rsp+168h] [rbp+68h]
  int *v35; // [rsp+170h] [rbp+70h]
  __int64 v36; // [rsp+178h] [rbp+78h] BYREF
  _QWORD v37[3]; // [rsp+180h] [rbp+80h] BYREF
  int v38; // [rsp+198h] [rbp+98h]
  int *v39; // [rsp+1A0h] [rbp+A0h]
  char v40; // [rsp+1A8h] [rbp+A8h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  StringRawBuffer = WindowsGetStringRawBuffer(this[2], 0);
  v5 = WindowsGetStringRawBuffer(this[1], 0);
  v24 = 0;
  v25 = 0;
  v29 = 0;
  v26 = 0;
  v27 = "OnEventQueued";
  v28 = 0;
  v30 = 0;
  v32 = 0;
  memset_0(v31, 0, sizeof(v31));
  v33 = 1;
  v34 = 0;
  v35 = &v24;
  v36 = 0;
  v37[0] = 0;
  v37[1] = &v23;
  v37[2] = 0;
  v38 = 0;
  v39 = &v26;
  v40 = 0;
  v23 = &SingleViewExperienceTelemetry::OnEventQueued::`vftable';
  SingleViewExperienceTelemetry::OnEventQueued::StartActivity(
    (SingleViewExperienceTelemetry::OnEventQueued *)&v23,
    v5,
    StringRawBuffer);
  string = 0;
  v6 = *(__int64 (__fastcall **)(struct Windows::Internal::Shell::Experience::IShellExperienceViewStateChangedEventArgs *, HSTRING *))(*(_QWORD *)a2 + 64LL);
  WindowsDeleteString(0);
  string = 0;
  v7 = v6(a2, &string);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x296,
      (unsigned int)"shell\\twinui\\experiencemanagers\\corelib\\singleviewexperience.cpp",
      (const char *)(unsigned int)v7,
      v17);
    WindowsDeleteString(string);
    string = 0;
    v23 = &SingleViewExperienceTelemetry::OnEventQueued::`vftable';
    wil::ActivityBase<SingleViewExperienceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v23);
    if ( v38 )
      wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v37);
    goto LABEL_13;
  }
  v20 = WindowsGetStringRawBuffer(string, 0);
  v21 = WindowsGetStringRawBuffer(this[2], 0);
  v22[0] = WindowsGetStringRawBuffer(this[1], 0);
  SingleViewExperienceTelemetry::OnEventQueued::OnEventQueued_EventName<unsigned short const *,unsigned short const *,unsigned short const *>(
    v22,
    &v21,
    &v20);
  v19 = 0;
  v9 = *(__int64 (__fastcall **)(struct Windows::Internal::Shell::Experience::IShellExperienceViewStateChangedEventArgs *, __int64 *))(*(_QWORD *)a2 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  v10 = v9(a2, &v19);
  v8 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29B,
      (unsigned int)"shell\\twinui\\experiencemanagers\\corelib\\singleviewexperience.cpp",
      (const char *)(unsigned int)v10,
      v17);
    v15 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    WindowsDeleteString(string);
    string = 0;
    v23 = &SingleViewExperienceTelemetry::OnEventQueued::`vftable';
    wil::ActivityBase<SingleViewExperienceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v23);
    if ( v38 )
      wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v37);
LABEL_13:
    wil::details::shared_object<wil::ActivityBase<SingleViewExperienceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<SingleViewExperienceLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&v36);
    wil::ActivityBase<SingleViewExperienceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<SingleViewExperienceLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<SingleViewExperienceLogging,_TlgReflectorTag_Param0IsProviderType>(&v24);
    return v8;
  }
  v11 = (*(__int64 (__fastcall **)(HSTRING, HSTRING *, HSTRING, __int64))(*(_QWORD *)this[11] + 88LL))(
          this[11],
          this,
          string,
          v19);
  v12 = v11;
  if ( v11 >= 0 )
  {
    wil::ActivityBase<SingleViewExperienceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v23);
    v16 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    WindowsDeleteString(string);
    string = 0;
    v23 = &SingleViewExperienceTelemetry::OnEventQueued::`vftable';
    wil::ActivityBase<SingleViewExperienceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v23);
    if ( v38 )
      wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v37);
    wil::details::shared_object<wil::ActivityBase<SingleViewExperienceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<SingleViewExperienceLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&v36);
    wil::ActivityBase<SingleViewExperienceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<SingleViewExperienceLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<SingleViewExperienceLogging,_TlgReflectorTag_Param0IsProviderType>(&v24);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29C,
      (unsigned int)"shell\\twinui\\experiencemanagers\\corelib\\singleviewexperience.cpp",
      (const char *)(unsigned int)v11,
      v17);
    v13 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    WindowsDeleteString(string);
    string = 0;
    v23 = &SingleViewExperienceTelemetry::OnEventQueued::`vftable';
    wil::ActivityBase<SingleViewExperienceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v23);
    if ( v38 )
      wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v37);
    wil::details::shared_object<wil::ActivityBase<SingleViewExperienceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<SingleViewExperienceLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&v36);
    wil::ActivityBase<SingleViewExperienceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<SingleViewExperienceLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<SingleViewExperienceLogging,_TlgReflectorTag_Param0IsProviderType>(&v24);
    return v12;
  }
}

```

## disassembly

```asm
0x1800486b0  mov     [rsp-8+arg_10], rbx
0x1800486b5  mov     [rsp-8+arg_18], rsi
0x1800486ba  push    rbp
0x1800486bb  push    rdi
0x1800486bc  push    r12
0x1800486be  push    r14
0x1800486c0  push    r15
0x1800486c2  lea     rbp, [rsp-0C0h]
0x1800486ca  sub     rsp, 1C0h
0x1800486d1  mov     rax, cs:__security_cookie
0x1800486d8  xor     rax, rsp
0x1800486db  mov     [rbp+0E0h+var_30], rax
0x1800486e2  mov     r14, rdx
0x1800486e5  mov     rbx, rcx
0x1800486e8  xor     edx, edx; length
0x1800486ea  mov     rcx, [rcx+10h]; string
0x1800486ee  call    cs:__imp_WindowsGetStringRawBuffer
0x1800486f4  mov     rsi, rax
0x1800486f7  xor     edx, edx; length
0x1800486f9  mov     rcx, [rbx+8]; string
0x1800486fd  call    cs:__imp_WindowsGetStringRawBuffer
0x180048703  mov     rdi, rax
0x180048706  xor     r15d, r15d
0x180048709  mov     [rsp+1E0h+var_178], r15d
0x18004870e  mov     [rsp+1E0h+var_174], r15b
0x180048713  mov     [rbp+0E0h+var_138], r15b
0x180048717  mov     [rbp+0E0h+var_150], r15d
0x18004871b  lea     rax, aOneventqueued; "OnEventQueued"
0x180048722  mov     [rbp+0E0h+var_148], rax
0x180048726  mov     [rbp+0E0h+var_140], r15
0x18004872a  mov     [rbp+0E0h+var_130], r15d
0x18004872e  xorps   xmm0, xmm0
0x180048731  movdqa  [rbp+0E0h+var_90], xmm0
0x180048736  xor     edx, edx; Val
0x180048738  mov     r8d, 98h; Size
0x18004873e  lea     rcx, [rbp+0E0h+var_128]; void *
0x180048742  call    memset_0
0x180048747  mov     [rbp+0E0h+var_80], 1
0x18004874e  xor     eax, eax
0x180048750  mov     [rbp+0E0h+var_78], rax
0x180048754  lea     rax, [rsp+1E0h+var_178]
0x180048759  mov     [rbp+0E0h+var_70], rax
0x18004875d  mov     [rbp+0E0h+var_68], r15
0x180048761  mov     [rbp+0E0h+var_60], r15
0x180048768  lea     rax, [rsp+1E0h+var_180]
0x18004876d  mov     [rbp+0E0h+var_58], rax
0x180048774  mov     [rbp+0E0h+var_50], r15
0x18004877b  mov     [rbp+0E0h+var_48], r15d
0x180048782  lea     rax, [rbp+0E0h+var_150]
0x180048786  mov     [rbp+0E0h+var_40], rax
0x18004878d  mov     [rbp+0E0h+var_38], r15b
0x180048794  lea     r12, ??_7OnEventQueued@SingleViewExperienceTelemetry@@6B@; const SingleViewExperienceTelemetry::OnEventQueued::`vftable'
0x18004879b  mov     [rsp+1E0h+var_180], r12
0x1800487a0  mov     r8, rsi; unsigned __int16 *
0x1800487a3  mov     rdx, rdi; unsigned __int16 *
0x1800487a6  lea     rcx, [rsp+1E0h+var_180]; this
0x1800487ab  call    ?StartActivity@OnEventQueued@SingleViewExperienceTelemetry@@QEAAXPEBG0@Z; SingleViewExperienceTelemetry::OnEventQueued::StartActivity(ushort const *,ushort const *)
0x1800487b0  nop
0x1800487b1  mov     [rsp+1E0h+string], r15
0x1800487b6  mov     rax, [r14]
0x1800487b9  mov     rdi, [rax+40h]
0x1800487bd  xor     ecx, ecx; string
0x1800487bf  call    cs:__imp_WindowsDeleteString
0x1800487c5  mov     [rsp+1E0h+string], r15
0x1800487ca  lea     rdx, [rsp+1E0h+string]
0x1800487cf  mov     rcx, r14
0x1800487d2  mov     rax, rdi
0x1800487d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800487da  mov     edi, eax
0x1800487dc  test    eax, eax
0x1800487de  js      loc_180048A30
0x1800487e4  xor     edx, edx; length
0x1800487e6  mov     rcx, [rsp+1E0h+string]; string
0x1800487eb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800487f1  mov     [rsp+1E0h+var_1A0], rax
0x1800487f6  xor     edx, edx; length
0x1800487f8  mov     rcx, [rbx+10h]; string
0x1800487fc  call    cs:__imp_WindowsGetStringRawBuffer
0x180048802  mov     [rsp+1E0h+var_198], rax
0x180048807  xor     edx, edx; length
0x180048809  mov     rcx, [rbx+8]; string
0x18004880d  call    cs:__imp_WindowsGetStringRawBuffer
0x180048813  mov     [rsp+1E0h+var_190], rax
0x180048818  lea     r8, [rsp+1E0h+var_1A0]
0x18004881d  lea     rdx, [rsp+1E0h+var_198]
0x180048822  lea     rcx, [rsp+1E0h+var_190]
0x180048827  call    ??$OnEventQueued_EventName@PEBGPEBGPEBG@OnEventQueued@SingleViewExperienceTelemetry@@SAX$$QEAPEBG00@Z; SingleViewExperienceTelemetry::OnEventQueued::OnEventQueued_EventName<ushort const *,ushort const *,ushort const *>(ushort const * &&,ushort const * &&,ushort const * &&)
0x18004882c  mov     [rsp+1E0h+var_1A8], r15
0x180048831  mov     rax, [r14]
0x180048834  mov     rdi, [rax+48h]
0x180048838  lea     rcx, [rsp+1E0h+var_1A8]
0x18004883d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048842  lea     rdx, [rsp+1E0h+var_1A8]
0x180048847  mov     rcx, r14
0x18004884a  mov     rax, rdi
0x18004884d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048852  mov     edi, eax
0x180048854  test    eax, eax
0x180048856  js      loc_180048931
0x18004885c  mov     rcx, [rbx+58h]
0x180048860  mov     rax, [rcx]
0x180048863  mov     r9, [rsp+1E0h+var_1A8]
0x180048868  mov     r8, [rsp+1E0h+string]
0x18004886d  mov     rdx, rbx
0x180048870  mov     rax, [rax+58h]
0x180048874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048879  mov     ebx, eax
0x18004887b  test    eax, eax
0x18004887d  jns     loc_1800489B9
0x180048883  mov     rcx, [rbp+0E8h]; this
0x18004888a  mov     r9d, eax; char *
0x18004888d  lea     r8, aShellTwinuiExp_0; "shell\\twinui\\experiencemanagers\\core"...
0x180048894  mov     edx, 29Ch; void *
0x180048899  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004889e  nop
0x18004889f  mov     rcx, [rsp+1E0h+var_1A8]
0x1800488a4  test    rcx, rcx
0x1800488a7  jz      short loc_1800488BB
0x1800488a9  mov     [rsp+1E0h+var_1A8], r15
0x1800488ae  mov     rax, [rcx]
0x1800488b1  mov     rax, [rax+10h]
0x1800488b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800488ba  nop
0x1800488bb  mov     rcx, [rsp+1E0h+string]; string
0x1800488c0  call    cs:__imp_WindowsDeleteString
0x1800488c6  mov     [rsp+1E0h+string], r15
0x1800488cb  mov     [rsp+1E0h+var_180], r12
0x1800488d0  lea     rcx, [rsp+1E0h+var_180]
0x1800488d5  call    ?Destroy@?$ActivityBase@VSingleViewExperienceLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<SingleViewExperienceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800488da  nop
0x1800488db  cmp     [rbp+0E0h+var_48], 0
0x1800488e2  jz      short loc_1800488F1
0x1800488e4  lea     rcx, [rbp+0E0h+var_60]; this
0x1800488eb  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800488f0  nop
0x1800488f1  lea     rcx, [rbp+0E0h+var_68]
0x1800488f5  call    ?reset@?$shared_object@V?$ActivityData@VSingleViewExperienceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VSingleViewExperienceLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<SingleViewExperienceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<SingleViewExperienceLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x1800488fa  lea     rcx, [rsp+1E0h+var_178]
0x1800488ff  call    ??1?$ActivityData@VSingleViewExperienceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VSingleViewExperienceLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<SingleViewExperienceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<SingleViewExperienceLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<SingleViewExperienceLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x180048904  mov     eax, ebx
0x180048906  mov     rcx, [rbp+0E0h+var_30]
0x18004890d  xor     rcx, rsp; StackCookie
0x180048910  call    __security_check_cookie
0x180048915  lea     r11, [rsp+1E0h+var_20]
0x18004891d  mov     rbx, [r11+40h]
0x180048921  mov     rsi, [r11+48h]
0x180048925  mov     rsp, r11
0x180048928  pop     r15
0x18004892a  pop     r14
0x18004892c  pop     r12
0x18004892e  pop     rdi
0x18004892f  pop     rbp
0x180048930  retn
0x180048931  mov     rcx, [rbp+0E8h]; this
0x180048938  mov     r9d, edi; char *
0x18004893b  lea     r8, aShellTwinuiExp_0; "shell\\twinui\\experiencemanagers\\core"...
0x180048942  mov     edx, 29Bh; void *
0x180048947  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004894c  nop
0x18004894d  mov     rcx, [rsp+1E0h+var_1A8]
0x180048952  test    rcx, rcx
0x180048955  jz      short loc_180048969
0x180048957  mov     [rsp+1E0h+var_1A8], r15
0x18004895c  mov     rax, [rcx]
0x18004895f  mov     rax, [rax+10h]
0x180048963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048968  nop
0x180048969  mov     rcx, [rsp+1E0h+string]; string
0x18004896e  call    cs:__imp_WindowsDeleteString
0x180048974  mov     [rsp+1E0h+string], r15
0x180048979  mov     [rsp+1E0h+var_180], r12
0x18004897e  lea     rcx, [rsp+1E0h+var_180]
0x180048983  call    ?Destroy@?$ActivityBase@VSingleViewExperienceLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<SingleViewExperienceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180048988  nop
0x180048989  cmp     [rbp+0E0h+var_48], 0
0x180048990  jz      short loc_18004899F
0x180048992  lea     rcx, [rbp+0E0h+var_60]; this
0x180048999  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18004899e  nop
0x18004899f  lea     rcx, [rbp+0E0h+var_68]
0x1800489a3  call    ?reset@?$shared_object@V?$ActivityData@VSingleViewExperienceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VSingleViewExperienceLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<SingleViewExperienceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<SingleViewExperienceLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x1800489a8  lea     rcx, [rsp+1E0h+var_178]
0x1800489ad  call    ??1?$ActivityData@VSingleViewExperienceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VSingleViewExperienceLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<SingleViewExperienceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<SingleViewExperienceLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<SingleViewExperienceLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800489b2  mov     eax, edi
0x1800489b4  jmp     loc_180048906
0x1800489b9  lea     rcx, [rsp+1E0h+var_180]
0x1800489be  call    ?Stop@?$ActivityBase@VSingleViewExperienceLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SingleViewExperienceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800489c3  nop
0x1800489c4  mov     rcx, [rsp+1E0h+var_1A8]
0x1800489c9  test    rcx, rcx
0x1800489cc  jz      short loc_1800489E0
0x1800489ce  mov     [rsp+1E0h+var_1A8], r15
0x1800489d3  mov     rax, [rcx]
0x1800489d6  mov     rax, [rax+10h]
0x1800489da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489df  nop
0x1800489e0  mov     rcx, [rsp+1E0h+string]; string
0x1800489e5  call    cs:__imp_WindowsDeleteString
0x1800489eb  mov     [rsp+1E0h+string], r15
0x1800489f0  mov     [rsp+1E0h+var_180], r12
0x1800489f5  lea     rcx, [rsp+1E0h+var_180]
0x1800489fa  call    ?Destroy@?$ActivityBase@VSingleViewExperienceLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<SingleViewExperienceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800489ff  nop
0x180048a00  cmp     [rbp+0E0h+var_48], 0
0x180048a07  jz      short loc_180048A16
0x180048a09  lea     rcx, [rbp+0E0h+var_60]; this
0x180048a10  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180048a15  nop
0x180048a16  lea     rcx, [rbp+0E0h+var_68]
0x180048a1a  call    ?reset@?$shared_object@V?$ActivityData@VSingleViewExperienceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VSingleViewExperienceLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<SingleViewExperienceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<SingleViewExperienceLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180048a1f  lea     rcx, [rsp+1E0h+var_178]
0x180048a24  call    ??1?$ActivityData@VSingleViewExperienceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VSingleViewExperienceLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<SingleViewExperienceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<SingleViewExperienceLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<SingleViewExperienceLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x180048a29  xor     eax, eax
0x180048a2b  jmp     loc_180048906
0x180048a30  mov     rcx, [rbp+0E8h]; this
0x180048a37  mov     r9d, edi; char *
0x180048a3a  lea     r8, aShellTwinuiExp_0; "shell\\twinui\\experiencemanagers\\core"...
0x180048a41  mov     edx, 296h; void *
0x180048a46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048a4b  nop
0x180048a4c  mov     rcx, [rsp+1E0h+string]; string
0x180048a51  call    cs:__imp_WindowsDeleteString
0x180048a57  mov     [rsp+1E0h+string], r15
0x180048a5c  mov     [rsp+1E0h+var_180], r12
0x180048a61  lea     rcx, [rsp+1E0h+var_180]
0x180048a66  call    ?Destroy@?$ActivityBase@VSingleViewExperienceLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<SingleViewExperienceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180048a6b  nop
0x180048a6c  cmp     [rbp+0E0h+var_48], 0
0x180048a73  jz      short loc_180048A82
0x180048a75  lea     rcx, [rbp+0E0h+var_60]; this
0x180048a7c  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180048a81  nop
0x180048a82  jmp     loc_18004899F
```
