# CWNPNet::OnServerPNG(unsigned __int64,uchar *)

- ea: `0x18003deb4`
- end: `0x18003e5d6`
- name: `?OnServerPNG@CWNPNet@@IEAAX_KPEAE@Z`
- size: `1826`
- prototype: `void __fastcall(CWNPNet *__hidden this, unsigned __int64, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003fb38`

## callees

- `0x180007440`
- `0x18000ba54`
- `0x18000d06c`
- `0x18000fe0c`
- `0x18001c06c`
- `0x18001c1ac`
- `0x18001d108`
- `0x180032394`
- `0x180033254`
- `0x18003715c`
- `0x180038a10`
- `0x18003deb4`
- `0x18004548c`
- `0x180045830`
- `0x18004603c`
- `0x18005c02c`
- `0x180060a78`
- `0x180060a90`
- `0x180061670`
- `0x18009163c`
- `0x180096010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18003e10e`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18003e10e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003e273`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003e273`

## string_xrefs

- `0x18003e3f4`: `TempDisconnected`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWNPNet::OnServerPNG(CWNPNet *this, unsigned __int64 a2, unsigned __int8 *a3)
{
  char v6; // r15
  unsigned int v7; // r12d
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // eax
  bool v12; // r13
  char v13; // r14
  __int64 v14; // rsi
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  __int64 v20; // r8
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // edi
  __int64 v25; // rdi
  ULONGLONG TickCount64; // rax
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rdx
  int v30; // r8d
  __int64 v31; // rdx
  const wchar_t *v32; // rax
  size_t v33; // r8
  __int64 v34; // rdx
  const wchar_t *v35; // rax
  __int64 v36; // rcx
  size_t v37; // r8
  __int64 v38; // r9
  const wchar_t *v39; // rax
  const wchar_t *v40; // rdx
  size_t v41; // r8
  __int64 v42; // r9
  __int64 v43; // r9
  const wchar_t *v44; // rax
  const wchar_t *v45; // rdx
  size_t v46; // r8
  __int64 v47; // r9
  const wchar_t *v48; // rax
  __int64 v49; // rcx
  size_t v50; // r8
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // r9
  const char *v54; // r9
  int v55; // [rsp+20h] [rbp-D8h]
  unsigned int MaxCount; // [rsp+30h] [rbp-C8h] BYREF
  int MaxCount_4; // [rsp+34h] [rbp-C4h] BYREF
  int IsLongRunning; // [rsp+38h] [rbp-C0h] BYREF
  struct IXmlReader *v59; // [rsp+40h] [rbp-B8h] BYREF
  struct IWNPNetEvents *v60; // [rsp+48h] [rbp-B0h] BYREF
  wchar_t *String1; // [rsp+50h] [rbp-A8h] BYREF
  int v62; // [rsp+58h] [rbp-A0h] BYREF
  unsigned int v63; // [rsp+5Ch] [rbp-9Ch] BYREF
  int v64; // [rsp+60h] [rbp-98h] BYREF
  CWNPNet *v65; // [rsp+68h] [rbp-90h]
  char v66; // [rsp+70h] [rbp-88h]
  _BYTE v67[4]; // [rsp+78h] [rbp-80h] BYREF
  char v68; // [rsp+7Ch] [rbp-7Ch] BYREF
  _BYTE v69[16]; // [rsp+90h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  try
  {
    v6 = 0;
    if ( a2 )
    {
      if ( a3 )
        goto LABEL_7;
    }
    else if ( !a3 )
    {
      goto LABEL_7;
    }
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
LABEL_7:
    v64 = 0;
    v59 = 0;
    v62 = 0;
    v7 = 0;
    v63 = 0;
    std::wstring::wstring(v69, L"Connected");
    MaxCount_4 = 0;
    v65 = this;
    v66 = 1;
    if ( a2 && a3 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59, v8, v9, v10);
      v11 = CXmlLiteWrapper::CreateReader(a3, a2, &v59);
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x114A,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
          (const char *)(unsigned int)v11,
          v55);
      v12 = 0;
      v13 = 0;
      v14 = -1;
      while ( !v12 )
      {
        String1 = 0;
        MaxCount = 0;
        v60 = 0;
        IsLongRunning = 0;
        v15 = ((__int64 (__fastcall *)(struct IXmlReader *, int *))v59->lpVtbl->Read)(v59, &v62);
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1155,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
            (const char *)(unsigned int)v15,
            v55);
        if ( v15 == 1 )
          break;
        switch ( v62 )
        {
          case 1:
            v21 = ((__int64 (__fastcall *)(struct IXmlReader *, wchar_t **, unsigned int *))v59->lpVtbl->GetLocalName)(
                    v59,
                    &String1,
                    &MaxCount);
            if ( v21 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1160,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
                (const char *)(unsigned int)v21,
                v55);
            v22 = ((__int64 (__fastcall *)(struct IXmlReader *, int *))v59->lpVtbl->GetDepth)(v59, &MaxCount_4);
            if ( v22 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1161,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
                (const char *)(unsigned int)v22,
                v55);
            v23 = wcsncmp_0(String1, L"wait", MaxCount);
            v24 = MaxCount_4;
            if ( v23 || MaxCount_4 != 1 )
            {
              if ( !wcsncmp_0(String1, (const wchar_t *)"c", MaxCount) && v24 == 1 )
                v6 = 1;
            }
            else
            {
              v13 = 1;
            }
            break;
          case 3:
            if ( v13 && MaxCount_4 == 1 )
            {
              v18 = ((__int64 (__fastcall *)(struct IXmlReader *, struct IWNPNetEvents **, int *))v59->lpVtbl->GetValue)(
                      v59,
                      &v60,
                      &IsLongRunning);
              if ( v18 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x1170,
                  (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
                  (const char *)(unsigned int)v18,
                  v55);
              if ( v60 && IsLongRunning )
              {
                v7 = _o__wtoi(v60);
                v63 = v7;
              }
            }
            else if ( v6 && MaxCount_4 == 1 )
            {
              v19 = ((__int64 (__fastcall *)(struct IXmlReader *, struct IWNPNetEvents **, int *))v59->lpVtbl->GetValue)(
                      v59,
                      &v60,
                      &IsLongRunning);
              if ( v19 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x1178,
                  (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
                  (const char *)(unsigned int)v19,
                  v55);
              if ( v60 && IsLongRunning )
              {
                v20 = -1;
                do
                  ++v20;
                while ( *((_WORD *)v60 + v20) );
                std::wstring::_Assign<unsigned short>(v69);
              }
            }
            break;
          case 15:
            v16 = ((__int64 (__fastcall *)(struct IXmlReader *, wchar_t **, unsigned int *))v59->lpVtbl->GetLocalName)(
                    v59,
                    &String1,
                    &MaxCount);
            if ( v16 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1181,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
                (const char *)(unsigned int)v16,
                v55);
            v17 = ((__int64 (__fastcall *)(struct IXmlReader *, int *))v59->lpVtbl->GetDepth)(v59, &MaxCount_4);
            if ( v17 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1182,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
                (const char *)(unsigned int)v17,
                v55);
            if ( MaxCount_4 == 1 )
            {
              v12 = wcsncmp_0(String1, L"ping-response", MaxCount) == 0;
            }
            else if ( MaxCount_4 == 2 )
            {
              if ( !wcsncmp_0(String1, L"wait", MaxCount) )
              {
                v13 = 0;
              }
              else if ( !wcsncmp_0(String1, (const wchar_t *)"c", MaxCount) )
              {
                v6 = 0;
              }
            }
            break;
        }
      }
    }
    else
    {
      v14 = -1;
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteWakeTimer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      (char *)this + 528,
      0);
    *((_BYTE *)this + 500) = 0;
    v25 = *((_QWORD *)this + 63);
    TickCount64 = GetTickCount64();
    v27 = ((TickCount64 - v25) * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
    *((_QWORD *)this + 64) = (v27 + ((TickCount64 - v25 - v27) >> 1)) >> 9;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v28 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v69);
      WPP_SF_dS(*(_QWORD *)(v29 + 16), v29, v30, v7, v28);
    }
    v31 = -1;
    do
      ++v31;
    while ( aConnected[v31] );
    v32 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v69);
    if ( v33 != v34 || v33 && wmemcmp(v32, L"Connected", v33) )
    {
      CAbstractConnection::GetPrecommandRetryProperties(this, v67);
      IsLongRunning = CAbstractConnection::GetIsLongRunning(this);
      MaxCount = *((_DWORD *)this + 48);
      WpnprvTelemetry::LogProcessedPngForDisconnectedStatus<unsigned long &,std::wstring &,long &,_GUID &,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0008,int>(
        (unsigned int)&v63,
        (unsigned int)v69,
        (unsigned int)&v64,
        (unsigned int)&v68,
        (__int64)&MaxCount,
        (__int64)&IsLongRunning);
    }
    v60 = 0;
    if ( CWNPNet::GetEvents(this, &v60) )
    {
      if ( (unsigned int)CAbstractConnection::GetIsLongRunning(this) )
      {
        v38 = -1;
        do
          ++v38;
        while ( aTempdisconnect[v38] );
        v39 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v69);
        if ( v41 == v42 && (!v41 || !wmemcmp(v39, v40, v41)) )
          goto LABEL_85;
        v43 = -1;
        do
          ++v43;
        while ( aDisconnected[v43] );
        v44 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v69);
        if ( v46 == v47 && (!v46 || !wmemcmp(v44, v45, v46)) )
        {
LABEL_85:
          CWNPNet::DisconnectInternal(this, 2147549183LL, 22);
        }
        else
        {
          do
            ++v14;
          while ( aConnected[v14] );
          v48 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v69);
          if ( v50 != v14 || v50 && wmemcmp(v48, L"Connected", v50) )
            MicrosoftTelemetryAssertTriggeredNoArgs(v49);
          (*(void (__fastcall **)(struct IWNPNetEvents *))(*(_QWORD *)v60 + 48LL))(v60);
        }
      }
      else
      {
        do
          ++v14;
        while ( aConnected[v14] );
        v35 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v69);
        if ( v37 != v14 || v37 && wmemcmp(v35, L"Connected", v37) )
          MicrosoftTelemetryAssertTriggeredNoArgs(v36);
        if ( !*((_BYTE *)this + 520) )
          (*(void (__fastcall **)(struct IWNPNetEvents *, _QWORD))(*(_QWORD *)v60 + 40LL))(v60, v7);
      }
    }
    PdcTimerHelper::Reset((LPCRITICAL_SECTION)((char *)this + 1632));
    std::wstring::_Tidy_deallocate(v69);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59, v51, v52, v53);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x11CF,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
      v54);
  }
}

```

## disassembly

```asm
0x18003deb4  push    rbx
0x18003deb6  push    rsi
0x18003deb7  push    rdi
0x18003deb8  push    r12
0x18003deba  push    r13
0x18003debc  push    r14
0x18003debe  push    r15
0x18003dec0  sub     rsp, 0C0h
0x18003dec7  mov     rax, cs:__security_cookie
0x18003dece  xor     rax, rsp
0x18003ded1  mov     [rsp+0F8h+var_48], rax
0x18003ded9  mov     rdi, r8
0x18003dedc  mov     rsi, rdx
0x18003dedf  mov     rbx, rcx
0x18003dee2  xor     r15d, r15d
0x18003dee5  test    rdx, rdx
0x18003dee8  jz      short loc_18003DEF1
0x18003deea  test    r8, r8
0x18003deed  jnz     short loc_18003DEFB
0x18003deef  jmp     short loc_18003DEF6
0x18003def1  test    rdi, rdi
0x18003def4  jz      short loc_18003DEFB
0x18003def6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003defb  mov     [rsp+0F8h+var_98], r15d
0x18003df00  mov     [rsp+0F8h+var_B8], r15
0x18003df05  mov     [rsp+0F8h+var_A0], r15d
0x18003df0a  mov     r12d, r15d
0x18003df0d  mov     [rsp+0F8h+var_9C], r15d
0x18003df12  lea     r14, aConnected; "Connected"
0x18003df19  mov     rdx, r14
0x18003df1c  lea     rcx, [rsp+0F8h+var_68]
0x18003df24  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003df29  nop
0x18003df2a  mov     dword ptr [rsp+0F8h+MaxCount+4], r15d
0x18003df2f  mov     [rsp+0F8h+var_90], rbx
0x18003df34  mov     [rsp+0F8h+var_88], 1
0x18003df39  test    rsi, rsi
0x18003df3c  jz      loc_18003E247
0x18003df42  test    rdi, rdi
0x18003df45  jz      loc_18003E247
0x18003df4b  lea     rcx, [rsp+0F8h+var_B8]
0x18003df50  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003df55  lea     r8, [rsp+0F8h+var_B8]; struct IXmlReader **
0x18003df5a  mov     rdx, rsi; unsigned __int64
0x18003df5d  mov     rcx, rdi; unsigned __int8 *
0x18003df60  call    ?CreateReader@CXmlLiteWrapper@@SAJPEBE_KPEAPEAUIXmlReader@@@Z; CXmlLiteWrapper::CreateReader(uchar const *,unsigned __int64,IXmlReader * *)
0x18003df65  mov     rcx, [rsp+0F8h]; this
0x18003df6d  test    eax, eax
0x18003df6f  js      loc_18003E534
0x18003df75  mov     r13b, r15b
0x18003df78  mov     r14b, r15b
0x18003df7b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003df7f  xor     edi, edi
0x18003df81  test    r13b, r13b
0x18003df84  jnz     loc_18003E24D
0x18003df8a  mov     [rsp+0F8h+String1], rdi
0x18003df8f  mov     dword ptr [rsp+0F8h+MaxCount], edi
0x18003df93  mov     [rsp+0F8h+var_B0], rdi
0x18003df98  mov     [rsp+0F8h+var_C0], edi
0x18003df9c  mov     rcx, [rsp+0F8h+var_B8]
0x18003dfa1  mov     rax, [rcx]
0x18003dfa4  lea     rdx, [rsp+0F8h+var_A0]
0x18003dfa9  mov     rax, [rax+30h]
0x18003dfad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dfb2  mov     rcx, [rsp+0F8h]; this
0x18003dfba  test    eax, eax
0x18003dfbc  js      loc_18003E548
0x18003dfc2  cmp     eax, 1
0x18003dfc5  jz      loc_18003E24D
0x18003dfcb  mov     ecx, [rsp+0F8h+var_A0]
0x18003dfcf  sub     ecx, 1
0x18003dfd2  jz      loc_18003E197
0x18003dfd8  sub     ecx, 2
0x18003dfdb  jz      loc_18003E0BA
0x18003dfe1  cmp     ecx, 0Ch
0x18003dfe4  jnz     short loc_18003DF81
0x18003dfe6  mov     rcx, [rsp+0F8h+var_B8]
0x18003dfeb  mov     rax, [rcx]
0x18003dfee  lea     r8, [rsp+0F8h+MaxCount]
0x18003dff3  lea     rdx, [rsp+0F8h+String1]
0x18003dff8  mov     rax, [rax+70h]
0x18003dffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e001  mov     rcx, [rsp+0F8h]; this
0x18003e009  test    eax, eax
0x18003e00b  js      loc_18003E55C
0x18003e011  mov     rcx, [rsp+0F8h+var_B8]
0x18003e016  mov     rax, [rcx]
0x18003e019  lea     rdx, [rsp+0F8h+MaxCount+4]
0x18003e01e  mov     rax, [rax+0C0h]
0x18003e025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e02a  mov     rcx, [rsp+0F8h]; this
0x18003e032  test    eax, eax
0x18003e034  js      loc_18003E570
0x18003e03a  cmp     dword ptr [rsp+0F8h+MaxCount+4], 1
0x18003e03f  jnz     short loc_18003E067
0x18003e041  mov     r8d, dword ptr [rsp+0F8h+MaxCount]; MaxCount
0x18003e046  lea     rdx, aPingResponse; "ping-response"
0x18003e04d  mov     rcx, [rsp+0F8h+String1]; String1
0x18003e052  call    wcsncmp_0
0x18003e057  test    eax, eax
0x18003e059  jnz     loc_18003DF81
0x18003e05f  mov     r13b, 1
0x18003e062  jmp     loc_18003DF81
0x18003e067  cmp     dword ptr [rsp+0F8h+MaxCount+4], 2
0x18003e06c  jnz     loc_18003DF81
0x18003e072  mov     r8d, dword ptr [rsp+0F8h+MaxCount]; MaxCount
0x18003e077  lea     rdx, aWait; "wait"
0x18003e07e  mov     rcx, [rsp+0F8h+String1]; String1
0x18003e083  call    wcsncmp_0
0x18003e088  test    eax, eax
0x18003e08a  jnz     short loc_18003E094
0x18003e08c  mov     r14b, dil
0x18003e08f  jmp     loc_18003DF81
0x18003e094  mov     r8d, dword ptr [rsp+0F8h+MaxCount]; MaxCount
0x18003e099  lea     rdx, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB+40h; String2
0x18003e0a0  mov     rcx, [rsp+0F8h+String1]; String1
0x18003e0a5  call    wcsncmp_0
0x18003e0aa  test    eax, eax
0x18003e0ac  jnz     loc_18003DF81
0x18003e0b2  mov     r15b, dil
0x18003e0b5  jmp     loc_18003DF81
0x18003e0ba  mov     eax, dword ptr [rsp+0F8h+MaxCount+4]
0x18003e0be  test    r14b, r14b
0x18003e0c1  jz      short loc_18003E120
0x18003e0c3  cmp     eax, 1
0x18003e0c6  jnz     short loc_18003E120
0x18003e0c8  mov     rcx, [rsp+0F8h+var_B8]
0x18003e0cd  mov     rax, [rcx]
0x18003e0d0  lea     r8, [rsp+0F8h+var_C0]
0x18003e0d5  lea     rdx, [rsp+0F8h+var_B0]
0x18003e0da  mov     rax, [rax+80h]
0x18003e0e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e0e6  mov     rcx, [rsp+0F8h]; this
0x18003e0ee  test    eax, eax
0x18003e0f0  js      loc_18003E584
0x18003e0f6  mov     rcx, [rsp+0F8h+var_B0]
0x18003e0fb  test    rcx, rcx
0x18003e0fe  jz      loc_18003DF81
0x18003e104  cmp     [rsp+0F8h+var_C0], edi
0x18003e108  jz      loc_18003DF81
0x18003e10e  call    cs:__imp__o__wtoi
0x18003e114  mov     r12d, eax
0x18003e117  mov     [rsp+0F8h+var_9C], eax
0x18003e11b  jmp     loc_18003DF81
0x18003e120  test    r15b, r15b
0x18003e123  jz      loc_18003DF81
0x18003e129  cmp     eax, 1
0x18003e12c  jnz     loc_18003DF81
0x18003e132  mov     rcx, [rsp+0F8h+var_B8]
0x18003e137  mov     rax, [rcx]
0x18003e13a  lea     r8, [rsp+0F8h+var_C0]
0x18003e13f  lea     rdx, [rsp+0F8h+var_B0]
0x18003e144  mov     rax, [rax+80h]
0x18003e14b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e150  mov     rcx, [rsp+0F8h]; this
0x18003e158  test    eax, eax
0x18003e15a  js      loc_18003E598
0x18003e160  mov     rdx, [rsp+0F8h+var_B0]
0x18003e165  test    rdx, rdx
0x18003e168  jz      loc_18003DF81
0x18003e16e  cmp     [rsp+0F8h+var_C0], edi
0x18003e172  jz      loc_18003DF81
0x18003e178  mov     r8, rsi
0x18003e17b  inc     r8
0x18003e17e  cmp     [rdx+r8*2], di
0x18003e183  jnz     short loc_18003E17B
0x18003e185  lea     rcx, [rsp+0F8h+var_68]
0x18003e18d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18003e192  jmp     loc_18003DF81
0x18003e197  mov     rcx, [rsp+0F8h+var_B8]
0x18003e19c  mov     rax, [rcx]
0x18003e19f  lea     r8, [rsp+0F8h+MaxCount]
0x18003e1a4  lea     rdx, [rsp+0F8h+String1]
0x18003e1a9  mov     rax, [rax+70h]
0x18003e1ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e1b2  mov     rcx, [rsp+0F8h]; this
0x18003e1ba  test    eax, eax
0x18003e1bc  js      loc_18003E5AC
0x18003e1c2  mov     rcx, [rsp+0F8h+var_B8]
0x18003e1c7  mov     rax, [rcx]
0x18003e1ca  lea     rdx, [rsp+0F8h+MaxCount+4]
0x18003e1cf  mov     rax, [rax+0C0h]
0x18003e1d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e1db  mov     rcx, [rsp+0F8h]; this
0x18003e1e3  test    eax, eax
0x18003e1e5  js      loc_18003E5C0
0x18003e1eb  mov     r8d, dword ptr [rsp+0F8h+MaxCount]; MaxCount
0x18003e1f0  lea     rdx, aWait; "wait"
0x18003e1f7  mov     rcx, [rsp+0F8h+String1]; String1
0x18003e1fc  call    wcsncmp_0
0x18003e201  mov     edi, dword ptr [rsp+0F8h+MaxCount+4]
0x18003e205  test    eax, eax
0x18003e207  jnz     short loc_18003E216
0x18003e209  cmp     edi, 1
0x18003e20c  jnz     short loc_18003E216
0x18003e20e  mov     r14b, dil
0x18003e211  jmp     loc_18003DF7F
0x18003e216  mov     r8d, dword ptr [rsp+0F8h+MaxCount]; MaxCount
0x18003e21b  lea     rdx, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB+40h; String2
0x18003e222  mov     rcx, [rsp+0F8h+String1]; String1
0x18003e227  call    wcsncmp_0
0x18003e22c  test    eax, eax
0x18003e22e  jnz     loc_18003DF7F
0x18003e234  cmp     edi, 1
0x18003e237  mov     edi, eax
0x18003e239  jnz     loc_18003DF81
0x18003e23f  mov     r15b, 1
0x18003e242  jmp     loc_18003DF81
0x18003e247  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003e24b  jmp     short loc_18003E257
0x18003e24d  lea     r14, aConnected; "Connected"
0x18003e254  xor     r15d, r15d
0x18003e257  lea     rcx, [rbx+210h]
0x18003e25e  xor     edx, edx
0x18003e260  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?DeleteWakeTimer@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteWakeTimer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18003e265  mov     [rbx+1F4h], r15b
0x18003e26c  mov     rdi, [rbx+1F8h]
0x18003e273  call    cs:__imp_GetTickCount64
0x18003e279  mov     rcx, rax
0x18003e27c  sub     rcx, rdi
0x18003e27f  mov     rax, 624DD2F1A9FBE77h
0x18003e289  mul     rcx
0x18003e28c  sub     rcx, rdx
0x18003e28f  shr     rcx, 1
0x18003e292  add     rcx, rdx
0x18003e295  shr     rcx, 9
0x18003e299  mov     [rbx+200h], rcx
0x18003e2a0  lea     rax, WPP_GLOBAL_Control
0x18003e2a7  mov     rdx, cs:WPP_GLOBAL_Control
0x18003e2ae  cmp     rdx, rax
0x18003e2b1  jz      short loc_18003E2DD
0x18003e2b3  test    byte ptr [rdx+1Ch], 4
0x18003e2b7  jz      short loc_18003E2DD
0x18003e2b9  cmp     byte ptr [rdx+19h], 5
0x18003e2bd  jb      short loc_18003E2DD
0x18003e2bf  lea     rcx, [rsp+0F8h+var_68]
0x18003e2c7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003e2cc  mov     [rsp+0F8h+var_D8], rax
0x18003e2d1  mov     r9d, r12d
0x18003e2d4  mov     rcx, [rdx+10h]
0x18003e2d8  call    WPP_SF_dS
0x18003e2dd  mov     rdx, rsi
0x18003e2e0  inc     rdx
0x18003e2e3  cmp     [r14+rdx*2], r15w
0x18003e2e8  jnz     short loc_18003E2E0
0x18003e2ea  mov     r8, [rsp+0F8h+var_58]
0x18003e2f2  lea     rcx, [rsp+0F8h+var_68]
0x18003e2fa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003e2ff  cmp     r8, rdx
0x18003e302  jnz     short loc_18003E318
0x18003e304  test    r8, r8
0x18003e307  jz      short loc_18003E36B
0x18003e309  mov     rdx, r14; S2
0x18003e30c  mov     rcx, rax; S1
0x18003e30f  call    wmemcmp
0x18003e314  test    eax, eax
0x18003e316  jz      short loc_18003E36B
0x18003e318  lea     rdx, [rsp+0F8h+var_80]
0x18003e31d  mov     rcx, rbx
0x18003e320  call    ?GetPrecommandRetryProperties@CAbstractConnection@@QEAA?AUPrecommandRetryProperties@@XZ; CAbstractConnection::GetPrecommandRetryProperties(void)
0x18003e325  mov     rcx, rbx; this
0x18003e328  call    ?GetIsLongRunning@CAbstractConnection@@QEAAHXZ; CAbstractConnection::GetIsLongRunning(void)
0x18003e32d  mov     [rsp+0F8h+var_C0], eax
0x18003e331  mov     eax, [rbx+0C0h]
0x18003e337  mov     dword ptr [rsp+0F8h+MaxCount], eax
0x18003e33b  lea     rax, [rsp+0F8h+var_C0]
0x18003e340  mov     [rsp+0F8h+var_D0], rax
0x18003e345  lea     rax, [rsp+0F8h+MaxCount]
0x18003e34a  mov     [rsp+0F8h+var_D8], rax
0x18003e34f  lea     r9, [rsp+0F8h+var_7C]
0x18003e354  lea     r8, [rsp+0F8h+var_98]
0x18003e359  lea     rdx, [rsp+0F8h+var_68]
0x18003e361  lea     rcx, [rsp+0F8h+var_9C]
0x18003e366  call    ??$LogProcessedPngForDisconnectedStatus@AEAKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAJAEAU_GUID@@W4__MIDL___MIDL_itf_wpntypes_0000_0000_0008@@H@WpnprvTelemetry@@SAXAEAKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAJAEAU_GUID@@$$QEAW4__MIDL___MIDL_itf_wpntypes_0000_0000_0008@@$$QEAH@Z; WpnprvTelemetry::LogProcessedPngForDisconnectedStatus<ulong &,std::wstring &,long &,_GUID &,__MIDL___MIDL_itf_wpntypes_0000_0000_0008,int>(ulong &,std::wstring &,long &,_GUID &,__MIDL___MIDL_itf_wpntypes_0000_0000_0008 &&,int &&)
0x18003e36b  mov     [rsp+0F8h+var_B0], r15
0x18003e370  lea     rdx, [rsp+0F8h+var_B0]; struct IWNPNetEvents **
0x18003e375  mov     rcx, rbx; this
0x18003e378  call    ?GetEvents@CWNPNet@@IEAA_NPEAPEAVIWNPNetEvents@@@Z; CWNPNet::GetEvents(IWNPNetEvents * *)
0x18003e37d  test    al, al
0x18003e37f  jz      loc_18003E4D1
0x18003e385  mov     rcx, rbx; this
0x18003e388  call    ?GetIsLongRunning@CAbstractConnection@@QEAAHXZ; CAbstractConnection::GetIsLongRunning(void)
0x18003e38d  test    eax, eax
0x18003e38f  jnz     short loc_18003E3F4
0x18003e391  inc     rsi
0x18003e394  cmp     [r14+rsi*2], r15w
0x18003e399  jnz     short loc_18003E391
0x18003e39b  mov     r8, [rsp+0F8h+var_58]
0x18003e3a3  lea     rcx, [rsp+0F8h+var_68]
0x18003e3ab  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003e3b0  cmp     r8, rsi
0x18003e3b3  jnz     short loc_18003E3C9
0x18003e3b5  test    r8, r8
0x18003e3b8  jz      short loc_18003E3CE
0x18003e3ba  mov     rdx, r14; S2
0x18003e3bd  mov     rcx, rax; S1
0x18003e3c0  call    wmemcmp
0x18003e3c5  test    eax, eax
0x18003e3c7  jz      short loc_18003E3CE
0x18003e3c9  call    MicrosoftTelemetryAssertTriggeredNoArgs
  ... truncated ...
```
