# Windows::Internal::Notifications::CToastActivator_Background::Activate(HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *,Windows::Foundation::Collections::IVectorView<HSTRING__ *> *)

- ea: `0x18001c270`
- end: `0x18001c5b9`
- name: `?Activate@CToastActivator_Background@Notifications@Internal@Windows@@UEAAJPEAUHSTRING__@@00PEAUIPropertySet@Collections@Foundation@4@PEAU?$IVectorView@PEAUHSTRING__@@@784@@Z`
- size: `841`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x180004868`
- `0x180005670`
- `0x18000d7d8`
- `0x1800143f0`
- `0x180016744`
- `0x1800180cc`
- `0x180018ad0`
- `0x180018b78`
- `0x18001b848`
- `0x18001c270`
- `0x18001c5c0`
- `0x18001cb74`
- `0x18001ff00`
- `0x180026998`
- `0x180026ac0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c309`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c319`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c404`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c4b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c4bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c539`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c549`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c309`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c319`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c404`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c4b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c4bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c539`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c549`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c3c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c440`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c3c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001c440`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Internal::Notifications::CToastActivator_Background::Activate(
        __int64 a1,
        HSTRING a2,
        HSTRING a3,
        WCHAR *a4,
        __int64 a5,
        __int64 a6)
{
  HSTRING v6; // r12
  HSTRING v7; // r13
  Windows::Internal::Notifications::CToastActivator_Background *v9; // rcx
  HSTRING v10; // r9
  int v12; // eax
  unsigned int i; // edi
  __int64 (__fastcall *v14)(__int64, _QWORD, HSTRING *); // rbx
  int v15; // eax
  PCWSTR v16; // rax
  int v17; // eax
  struct IWpnPresentationEndpoint *v18; // r15
  __int64 (__fastcall *v19)(struct IWpnPresentationEndpoint *, PCWSTR, PCWSTR, wil *); // r14
  wil *v20; // rsi
  __int64 v21; // rdi
  PCWSTR v22; // rbx
  PCWSTR v23; // rax
  int v24; // eax
  wil *v25; // rcx
  int v26; // [rsp+20h] [rbp-C8h]
  unsigned int v27; // [rsp+30h] [rbp-B8h] BYREF
  unsigned int v28; // [rsp+34h] [rbp-B4h] BYREF
  HSTRING string; // [rsp+38h] [rbp-B0h] BYREF
  PCWSTR StringRawBuffer; // [rsp+40h] [rbp-A8h] BYREF
  struct IWpnPresentationEndpoint *v31; // [rsp+48h] [rbp-A0h] BYREF
  wil *v32; // [rsp+50h] [rbp-98h] BYREF
  PCWSTR *v33; // [rsp+58h] [rbp-90h]
  char *v34; // [rsp+60h] [rbp-88h]
  HSTRING v35; // [rsp+68h] [rbp-80h] BYREF
  PCWSTR v36; // [rsp+70h] [rbp-78h] BYREF
  HSTRING v37; // [rsp+78h] [rbp-70h] BYREF
  _BYTE v38[32]; // [rsp+80h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v6 = (HSTRING)a4;
  v35 = a3;
  v7 = a2;
  v37 = a3;
  v36 = a4;
  v28 = 0;
  v27 = 0;
  std::string::string(v38, a2, a3);
  if ( Windows::Internal::Notifications::CToastActivator_Background::CanActivate(v9, v10) )
  {
    WpnClientTelemetry::GetCorrelationVector(v38);
    string = (HSTRING)WindowsGetStringRawBuffer(v6, 0);
    StringRawBuffer = WindowsGetStringRawBuffer(v7, 0);
    WpnClientTelemetry::ToastActivationStart<unsigned short const *,unsigned short const *,std::string &>(
      &StringRawBuffer,
      &string,
      v38);
    try
    {
      v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a6 + 56LL))(a6, &v27);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x58,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_background.cpp",
          (const char *)(unsigned int)v12,
          v26);
      std::vector<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord>::vector<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord>(&v32);
      StringRawBuffer = (PCWSTR)v27;
      if ( v27 > (unsigned __int64)((v34 - (char *)v32) >> 3) )
        std::vector<unsigned short const *>::_Reallocate<0>(&v32, &StringRawBuffer);
      for ( i = 0; i < v27; ++i )
      {
        string = 0;
        v14 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)a6 + 48LL);
        WindowsDeleteString(0);
        string = 0;
        v15 = v14(a6, i, &string);
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x60,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_background.cpp",
            (const char *)(unsigned int)v15,
            v26);
        v16 = WindowsGetStringRawBuffer(string, 0);
        StringRawBuffer = v16;
        if ( v33 == (PCWSTR *)v34 )
          std::vector<unsigned short const *>::_Emplace_reallocate<unsigned short const *>(&v32, v33, &StringRawBuffer);
        else
          *v33++ = v16;
        if ( string )
          WindowsDeleteString(string);
      }
      v31 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
      v17 = Windows::Internal::Notifications::CToastActivator_Background::EnsurePresentationEndpoint(
              (Windows::Internal::Notifications::CToastActivator_Background *)(a1 - 48),
              &v31);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x65,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_background.cpp",
          (const char *)(unsigned int)v17,
          v26);
      v18 = v31;
      v19 = *(__int64 (__fastcall **)(struct IWpnPresentationEndpoint *, PCWSTR, PCWSTR, wil *))(*(_QWORD *)v31 + 152LL);
      v20 = v32;
      v21 = ((char *)v33 - (char *)v32) >> 3;
      v22 = WindowsGetStringRawBuffer(v35, 0);
      v23 = WindowsGetStringRawBuffer(v7, 0);
      v24 = v19(v18, v23, v22, v20);
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6B,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_background.cpp",
          (const char *)(unsigned int)v24,
          v21);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
      v25 = v32;
      if ( v32 )
        std::_Deallocate<16>(v32, (v34 - (char *)v32) & 0xFFFFFFFFFFFFFFF8uLL);
    }
    catch ( ... )
    {
      v28 = wil::ResultFromCaughtException(v25);
      v7 = a2;
      v6 = (HSTRING)v36;
    }
    v36 = WindowsGetStringRawBuffer(v6, 0);
    v35 = (HSTRING)WindowsGetStringRawBuffer(v7, 0);
    WpnClientTelemetry::ToastActivationStop<unsigned short const *,unsigned short const *,HSTRING__ * &,unsigned int &,long &,std::string &>(
      (unsigned int)&v35,
      (unsigned int)&v36,
      (unsigned int)&v37,
      (unsigned int)&v27,
      (__int64)&v28,
      (__int64)v38);
    std::string::~string(v38);
    return v28;
  }
  else
  {
    std::string::~string(v38);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x18001c270  mov     r11, rsp
0x18001c273  mov     [r11+10h], rdx
0x18001c277  push    rbx
0x18001c278  push    rsi
0x18001c279  push    rdi
0x18001c27a  push    r12
0x18001c27c  push    r13
0x18001c27e  push    r14
0x18001c280  push    r15
0x18001c282  sub     rsp, 0B0h
0x18001c289  mov     rax, cs:__security_cookie
0x18001c290  xor     rax, rsp
0x18001c293  mov     [rsp+0E8h+var_48], rax
0x18001c29b  mov     r12, r9
0x18001c29e  mov     rbx, r8
0x18001c2a1  mov     [rsp+0E8h+var_80], rbx
0x18001c2a6  mov     r13, rdx
0x18001c2a9  mov     r14, rcx
0x18001c2ac  mov     [r11-70h], rbx
0x18001c2b0  mov     [rsp+0E8h+var_78], r9
0x18001c2b5  mov     rsi, [rsp+0E8h+arg_28]
0x18001c2bd  xor     r15d, r15d
0x18001c2c0  mov     [rsp+0E8h+var_B4], r15d
0x18001c2c5  mov     [rsp+0E8h+var_B8], r15d
0x18001c2ca  lea     rcx, [r11-68h]
0x18001c2ce  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18001c2d3  nop
0x18001c2d4  mov     rdx, r9; HSTRING
0x18001c2d7  call    ?CanActivate@CToastActivator_Background@Notifications@Internal@Windows@@AEAA_NPEAUHSTRING__@@@Z; Windows::Internal::Notifications::CToastActivator_Background::CanActivate(HSTRING__ *)
0x18001c2dc  test    al, al
0x18001c2de  jnz     short loc_18001C2F7
0x18001c2e0  lea     rcx, [rsp+0E8h+var_68]
0x18001c2e8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001c2ed  mov     eax, 80004001h
0x18001c2f2  jmp     loc_18001C596
0x18001c2f7  lea     rcx, [rsp+0E8h+var_68]
0x18001c2ff  call    ?GetCorrelationVector@WpnClientTelemetry@@SAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; WpnClientTelemetry::GetCorrelationVector(std::string &)
0x18001c304  xor     edx, edx; length
0x18001c306  mov     rcx, r12; string
0x18001c309  call    cs:__imp_WindowsGetStringRawBuffer
0x18001c30f  mov     [rsp+0E8h+string], rax
0x18001c314  xor     edx, edx; length
0x18001c316  mov     rcx, r13; string
0x18001c319  call    cs:__imp_WindowsGetStringRawBuffer
0x18001c31f  mov     [rsp+0E8h+var_A8], rax
0x18001c324  lea     r8, [rsp+0E8h+var_68]
0x18001c32c  lea     rdx, [rsp+0E8h+string]
0x18001c331  lea     rcx, [rsp+0E8h+var_A8]
0x18001c336  call    ??$ToastActivationStart@PEBGPEBGAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@WpnClientTelemetry@@SAX$$QEAPEBG0AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; WpnClientTelemetry::ToastActivationStart<ushort const *,ushort const *,std::string &>(ushort const * &&,ushort const * &&,std::string &)
0x18001c33b  mov     rax, [rsi]
0x18001c33e  lea     rdx, [rsp+0E8h+var_B8]
0x18001c343  mov     rcx, rsi
0x18001c346  mov     rax, [rax+38h]
0x18001c34a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c34f  mov     rcx, [rsp+0E8h]; this
0x18001c357  test    eax, eax
0x18001c359  jns     short loc_18001C36F
0x18001c35b  mov     r9d, eax; char *
0x18001c35e  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001c365  mov     edx, 58h ; 'X'; void *
0x18001c36a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001c36f  lea     rcx, [rsp+0E8h+var_98]
0x18001c374  call    ??0?$vector@UAppInfoRecord@CAppInfoAggregator@Notifications@Internal@Windows@@V?$allocator@UAppInfoRecord@CAppInfoAggregator@Notifications@Internal@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord>::vector<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord>(void)
0x18001c379  nop
0x18001c37a  mov     ecx, [rsp+0E8h+var_B8]
0x18001c37e  mov     [rsp+0E8h+var_A8], rcx
0x18001c383  mov     rax, [rsp+0E8h+var_88]
0x18001c388  sub     rax, [rsp+0E8h+var_98]
0x18001c38d  sar     rax, 3
0x18001c391  cmp     rcx, rax
0x18001c394  jbe     short loc_18001C3A5
0x18001c396  lea     rdx, [rsp+0E8h+var_A8]
0x18001c39b  lea     rcx, [rsp+0E8h+var_98]
0x18001c3a0  call    ??$_Reallocate@$0A@@?$vector@PEBGV?$allocator@PEBG@std@@@std@@AEAAXAEA_K@Z; std::vector<ushort const *>::_Reallocate<0>(unsigned __int64 &)
0x18001c3a5  mov     edi, r15d
0x18001c3a8  cmp     edi, [rsp+0E8h+var_B8]
0x18001c3ac  jnb     loc_18001C44D
0x18001c3b2  mov     [rsp+0E8h+string], r15
0x18001c3b7  mov     rax, [rsi]
0x18001c3ba  mov     rbx, [rax+30h]
0x18001c3be  xor     ecx, ecx; string
0x18001c3c0  call    cs:__imp_WindowsDeleteString
0x18001c3c6  mov     [rsp+0E8h+string], r15
0x18001c3cb  lea     r8, [rsp+0E8h+string]
0x18001c3d0  mov     edx, edi
0x18001c3d2  mov     rcx, rsi
0x18001c3d5  mov     rax, rbx
0x18001c3d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3dd  mov     rcx, [rsp+0E8h]; this
0x18001c3e5  test    eax, eax
0x18001c3e7  jns     short loc_18001C3FD
0x18001c3e9  mov     r9d, eax; char *
0x18001c3ec  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001c3f3  mov     edx, 60h ; '`'; void *
0x18001c3f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001c3fd  xor     edx, edx; length
0x18001c3ff  mov     rcx, [rsp+0E8h+string]; string
0x18001c404  call    cs:__imp_WindowsGetStringRawBuffer
0x18001c40a  mov     [rsp+0E8h+var_A8], rax
0x18001c40f  mov     rdx, [rsp+0E8h+var_90]
0x18001c414  cmp     rdx, [rsp+0E8h+var_88]
0x18001c419  jz      short loc_18001C426
0x18001c41b  mov     [rdx], rax
0x18001c41e  add     [rsp+0E8h+var_90], 8
0x18001c424  jmp     short loc_18001C436
0x18001c426  lea     r8, [rsp+0E8h+var_A8]
0x18001c42b  lea     rcx, [rsp+0E8h+var_98]
0x18001c430  call    ??$_Emplace_reallocate@PEBG@?$vector@PEBGV?$allocator@PEBG@std@@@std@@AEAAPEAPEBGQEAPEBG$$QEAPEBG@Z; std::vector<ushort const *>::_Emplace_reallocate<ushort const *>(ushort const * * const,ushort const * &&)
0x18001c435  nop
0x18001c436  mov     rcx, [rsp+0E8h+string]; string
0x18001c43b  test    rcx, rcx
0x18001c43e  jz      short loc_18001C446
0x18001c440  call    cs:__imp_WindowsDeleteString
0x18001c446  inc     edi
0x18001c448  jmp     loc_18001C3A8
0x18001c44d  mov     [rsp+0E8h+var_A0], r15
0x18001c452  lea     rcx, [rsp+0E8h+var_A0]
0x18001c457  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c45c  lea     rcx, [r14-30h]; this
0x18001c460  lea     rdx, [rsp+0E8h+var_A0]; struct IWpnPresentationEndpoint **
0x18001c465  call    ?EnsurePresentationEndpoint@CToastActivator_Background@Notifications@Internal@Windows@@AEAAJPEAPEAUIWpnPresentationEndpoint@@@Z; Windows::Internal::Notifications::CToastActivator_Background::EnsurePresentationEndpoint(IWpnPresentationEndpoint * *)
0x18001c46a  mov     rcx, [rsp+0E8h]; this
0x18001c472  test    eax, eax
0x18001c474  jns     short loc_18001C48A
0x18001c476  mov     r9d, eax; char *
0x18001c479  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001c480  mov     edx, 65h ; 'e'; void *
0x18001c485  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001c48a  mov     r15, [rsp+0E8h+var_A0]
0x18001c48f  mov     rax, [r15]
0x18001c492  mov     r14, [rax+98h]
0x18001c499  mov     rsi, [rsp+0E8h+var_98]
0x18001c49e  mov     rdi, [rsp+0E8h+var_90]
0x18001c4a3  sub     rdi, rsi
0x18001c4a6  sar     rdi, 3
0x18001c4aa  xor     edx, edx; length
0x18001c4ac  mov     rcx, [rsp+0E8h+var_80]; string
0x18001c4b1  call    cs:__imp_WindowsGetStringRawBuffer
0x18001c4b7  mov     rbx, rax
0x18001c4ba  xor     edx, edx; length
0x18001c4bc  mov     rcx, r13; string
0x18001c4bf  call    cs:__imp_WindowsGetStringRawBuffer
0x18001c4c5  mov     [rsp+0E8h+var_C8], edi; int
0x18001c4c9  mov     r9, rsi
0x18001c4cc  mov     r8, rbx
0x18001c4cf  mov     rdx, rax
0x18001c4d2  mov     rcx, r15
0x18001c4d5  mov     rax, r14
0x18001c4d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4dd  mov     rcx, [rsp+0E8h]; this
0x18001c4e5  test    eax, eax
0x18001c4e7  jns     short loc_18001C4FE
0x18001c4e9  mov     r9d, eax; char *
0x18001c4ec  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001c4f3  mov     edx, 6Bh ; 'k'; void *
0x18001c4f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001c4fe  lea     rcx, [rsp+0E8h+var_A0]
0x18001c503  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c508  nop
0x18001c509  mov     rcx, [rsp+0E8h+var_98]
0x18001c50e  test    rcx, rcx
0x18001c511  jz      short loc_18001C525
0x18001c513  mov     rdx, [rsp+0E8h+var_88]
0x18001c518  sub     rdx, rcx
0x18001c51b  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001c51f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001c524  nop
0x18001c525  jmp     short loc_18001C534
0x18001c527  mov     r13, [rsp+0E8h+arg_8]
0x18001c52f  mov     r12, [rsp+0E8h+var_78]
0x18001c534  xor     edx, edx; length
0x18001c536  mov     rcx, r12; string
0x18001c539  call    cs:__imp_WindowsGetStringRawBuffer
0x18001c53f  mov     [rsp+0E8h+var_78], rax
0x18001c544  xor     edx, edx; length
0x18001c546  mov     rcx, r13; string
0x18001c549  call    cs:__imp_WindowsGetStringRawBuffer
0x18001c54f  mov     [rsp+0E8h+var_80], rax
0x18001c554  lea     rax, [rsp+0E8h+var_68]
0x18001c55c  mov     [rsp+0E8h+var_C0], rax
0x18001c561  lea     rax, [rsp+0E8h+var_B4]
0x18001c566  mov     qword ptr [rsp+0E8h+var_C8], rax
0x18001c56b  lea     r9, [rsp+0E8h+var_B8]
0x18001c570  lea     r8, [rsp+0E8h+var_70]
0x18001c575  lea     rdx, [rsp+0E8h+var_78]
0x18001c57a  lea     rcx, [rsp+0E8h+var_80]
0x18001c57f  call    ??$ToastActivationStop@PEBGPEBGAEAPEAUHSTRING__@@AEAIAEAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@WpnClientTelemetry@@SAX$$QEAPEBG0AEAPEAUHSTRING__@@AEAIAEAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; WpnClientTelemetry::ToastActivationStop<ushort const *,ushort const *,HSTRING__ * &,uint &,long &,std::string &>(ushort const * &&,ushort const * &&,HSTRING__ * &,uint &,long &,std::string &)
0x18001c584  nop
0x18001c585  lea     rcx, [rsp+0E8h+var_68]
0x18001c58d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001c592  mov     eax, [rsp+0E8h+var_B4]
0x18001c596  mov     rcx, [rsp+0E8h+var_48]
0x18001c59e  xor     rcx, rsp; StackCookie
0x18001c5a1  call    __security_check_cookie
0x18001c5a6  add     rsp, 0B0h
0x18001c5ad  pop     r15
0x18001c5af  pop     r14
0x18001c5b1  pop     r13
0x18001c5b3  pop     r12
0x18001c5b5  pop     rdi
0x18001c5b6  pop     rsi
0x18001c5b7  pop     rbx
0x18001c5b8  retn
```
