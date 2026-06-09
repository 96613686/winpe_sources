# CTpTransport::DoExchange(CTpRequestMessage *,IWerByteStream *,CTpResponseMessage *,long (*const *)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *),ITpCallbacks *,ulong,wchar_t const *,void *,void *,CTpLogger *,wchar_t const *,ISequentialStream *,wchar_t const *,WINHTTP_TIMEOUTS *,ulong)

- ea: `0x18003e2b4`
- end: `0x18003ed35`
- name: `?DoExchange@CTpTransport@@SAJPEAVCTpRequestMessage@@PEAUIWerByteStream@@PEAVCTpResponseMessage@@PEBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZPEAUITpCallbacks@@K3PEAX7PEAVCTpLogger@@3PEAUISequentialStream@@3PEAUWINHTTP_TIMEOUTS@@K@Z`
- size: `2689`
- prototype: `__int64 __usercall@<rax>(struct CTpRequestMessage *this@<rcx>, struct ITpCallbacks *, int, int, __int64, __int64, __int64, __int64, int, __int64, __int64, int)`
- caller_count: `5`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024840`
- `0x18008799c`
- `0x18008808c`
- `0x1800898d8`
- `0x18008cd48`

## callees

- `0x18000cf50`
- `0x18000da00`
- `0x18000db80`
- `0x1800170b0`
- `0x18001c38c`
- `0x180020680`
- `0x1800221e4`
- `0x180028320`
- `0x180031884`
- `0x18003de9c`
- `0x18003e17c`
- `0x18003e2b4`
- `0x180045388`
- `0x18004d4ec`
- `0x18004e744`
- `0x18004e9dc`
- `0x18004ecb0`
- `0x180053d3c`
- `0x180054568`
- `0x180099e7c`
- `0x1800a497c`
- `0x1800a59c0`
- `0x1800a653c`
- `0x1800a663c`
- `0x1800a6670`
- `0x1800af070`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003e8a2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003e8eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003e92b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003eab8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003e8a2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003e8eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003e92b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003eab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e71f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e71f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003e69c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003e69c`
- `ext-ms-win-wer-xbox-l1-1-0!XerTpUpload` at `0x18003e8c1`
- `ext-ms-win-wer-xbox-l1-1-0!XerTpUpload` at `0x18003e8c1`
- `ext-ms-win-wer-xbox-l1-1-0!XerTpCompleteUpload` at `0x18003eca5`
- `ext-ms-win-wer-xbox-l1-1-0!XerTpCompleteUpload` at `0x18003eca5`
- `XmlLite!CreateXmlReader` at `0x18003e962`
- `XmlLite!CreateXmlReader` at `0x18003e962`

## string_xrefs

- `0x18003e4b1`: `telemetry.microsoft.com`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CTpTransport::DoExchange(
        struct CTpRequestMessage *this,
        struct IWerByteStream *a2,
        CTpResponseMessage *a3,
        __int64 a4,
        struct ITpCallbacks *a5,
        int a6,
        int a7,
        __int64 a8,
        void *a9,
        CTpLogger *a10,
        wchar_t *a11,
        int a12,
        wchar_t *a13,
        struct WINHTTP_TIMEOUTS *a14,
        int a15)
{
  int v16; // r12d
  unsigned __int16 v17; // si
  unsigned int v18; // r15d
  const wchar_t *v19; // rdi
  const wchar_t *v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  unsigned int v25; // esi
  wchar_t *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // r9
  int FinalServerName; // eax
  wchar_t *v30; // rcx
  unsigned int v31; // r15d
  HRESULT appended; // eax
  HANDLE v33; // r13
  DWORD v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r8
  signed int LastError; // eax
  bool v39; // zf
  DWORD TickCount; // esi
  DWORD v41; // r15d
  void *v42; // rcx
  _BYTE *v43; // rdx
  void (__fastcall *v44)(struct ITpCallbacks *, _QWORD, _QWORD, _QWORD, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, int, int, DWORD, unsigned __int64, wchar_t *, _QWORD, unsigned int); // rdi
  wchar_t *v45; // rbx
  unsigned __int64 Size; // rax
  wchar_t *v47; // r15
  unsigned int v48; // ebx
  void *v49; // rcx
  unsigned int v51[2]; // [rsp+70h] [rbp-C0h]
  unsigned __int16 v52; // [rsp+B0h] [rbp-80h]
  unsigned int v53; // [rsp+B4h] [rbp-7Ch]
  void *ppvObject; // [rsp+B8h] [rbp-78h] BYREF
  unsigned int v55; // [rsp+C0h] [rbp-70h]
  unsigned int v56; // [rsp+C4h] [rbp-6Ch] BYREF
  int v57; // [rsp+C8h] [rbp-68h]
  unsigned int v58; // [rsp+CCh] [rbp-64h] BYREF
  DWORD v59; // [rsp+D0h] [rbp-60h]
  int v60; // [rsp+D4h] [rbp-5Ch]
  int v61; // [rsp+D8h] [rbp-58h] BYREF
  _BYTE *v62; // [rsp+E0h] [rbp-50h] BYREF
  struct WINHTTP_TIMEOUTS *v63; // [rsp+E8h] [rbp-48h]
  wchar_t *v64; // [rsp+F0h] [rbp-40h]
  struct IWerByteStream *v65; // [rsp+F8h] [rbp-38h]
  __int128 v66; // [rsp+100h] [rbp-30h] BYREF
  __int64 v67; // [rsp+110h] [rbp-20h]
  void **v68; // [rsp+118h] [rbp-18h] BYREF
  void *v69[2]; // [rsp+120h] [rbp-10h]
  unsigned int v70[2]; // [rsp+130h] [rbp+0h]
  int v71; // [rsp+138h] [rbp+8h]
  HANDLE hHandle; // [rsp+140h] [rbp+10h]
  wchar_t *v73; // [rsp+148h] [rbp+18h]
  __int64 v74; // [rsp+150h] [rbp+20h]
  __int64 v75; // [rsp+158h] [rbp+28h]
  CTpResponseMessage *v76; // [rsp+160h] [rbp+30h]
  CTpLogger *v77; // [rsp+168h] [rbp+38h]
  wchar_t *v78[4]; // [rsp+170h] [rbp+40h] BYREF
  _QWORD v79[3]; // [rsp+190h] [rbp+60h] BYREF
  unsigned __int16 v80; // [rsp+1A8h] [rbp+78h]
  __int128 *v81; // [rsp+1B0h] [rbp+80h]
  unsigned int v82; // [rsp+1B8h] [rbp+88h]
  int v83; // [rsp+1BCh] [rbp+8Ch]
  int v84; // [rsp+1C0h] [rbp+90h]
  int v85; // [rsp+1D8h] [rbp+A8h]
  wchar_t *v86; // [rsp+1E0h] [rbp+B0h]
  HANDLE v87; // [rsp+1E8h] [rbp+B8h]
  __int64 v88; // [rsp+1F0h] [rbp+C0h]
  struct ITpCallbacks *v89; // [rsp+1F8h] [rbp+C8h]
  __int64 v90; // [rsp+200h] [rbp+D0h]
  int v91; // [rsp+208h] [rbp+D8h]
  unsigned int v92; // [rsp+20Ch] [rbp+DCh]
  unsigned int v93; // [rsp+210h] [rbp+E0h]
  unsigned int v94; // [rsp+214h] [rbp+E4h]
  unsigned int v95; // [rsp+218h] [rbp+E8h]
  unsigned int v96; // [rsp+21Ch] [rbp+ECh]
  unsigned int v97; // [rsp+220h] [rbp+F0h]
  int v98; // [rsp+224h] [rbp+F4h]
  void *v99; // [rsp+228h] [rbp+F8h]
  unsigned int v100; // [rsp+230h] [rbp+100h]
  int v101; // [rsp+234h] [rbp+104h]
  wchar_t *v102[4]; // [rsp+240h] [rbp+110h] BYREF
  void **v103; // [rsp+260h] [rbp+130h] BYREF
  __int128 v104; // [rsp+268h] [rbp+138h]
  __int64 v105; // [rsp+278h] [rbp+148h]
  int v106; // [rsp+280h] [rbp+150h]
  void **v107; // [rsp+288h] [rbp+158h] BYREF
  __int128 v108; // [rsp+290h] [rbp+160h]
  __int64 v109; // [rsp+2A0h] [rbp+170h]
  int v110; // [rsp+2A8h] [rbp+178h]
  _BYTE v111[32]; // [rsp+2B0h] [rbp+180h] BYREF
  _BYTE v112[40]; // [rsp+2D0h] [rbp+1A0h] BYREF
  __int64 v113; // [rsp+2F8h] [rbp+1C8h]
  void *v114; // [rsp+338h] [rbp+208h]
  unsigned int v115; // [rsp+358h] [rbp+228h]
  int v116; // [rsp+35Ch] [rbp+22Ch]
  unsigned int v117; // [rsp+360h] [rbp+230h]
  unsigned __int16 v118; // [rsp+364h] [rbp+234h]
  int v119; // [rsp+368h] [rbp+238h]
  _QWORD v120[2]; // [rsp+380h] [rbp+250h] BYREF
  _BYTE v121[320]; // [rsp+390h] [rbp+260h] BYREF

  v75 = a4;
  v76 = a3;
  v65 = a2;
  v74 = a8;
  hHandle = a9;
  v77 = a10;
  v64 = a11;
  v73 = a13;
  v63 = a14;
  CTpSettings::CTpSettings((CTpSettings *)v112);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v78);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v102);
  v61 = 0;
  v60 = 0;
  v16 = 0;
  v56 = 0;
  v55 = 0;
  v59 = 0;
  v67 = 0;
  v58 = 0;
  v68 = &CMemoryByteStream::`vftable';
  *(_OWORD *)v69 = 0;
  *(_QWORD *)v70 = 0;
  v71 = 0;
  v107 = &CMemoryByteStream::`vftable';
  v108 = 0;
  v109 = 0;
  v110 = 0;
  v120[0] = &CCompoundStream::`vftable';
  v120[1] = 0;
  memset_0(v121, 0, 0x100u);
  v103 = &CMemoryByteStream::`vftable';
  v104 = 0;
  v105 = 0;
  v106 = 0;
  CIStreamAdapter::CIStreamAdapter((CIStreamAdapter *)v111, (struct IWerByteStream *)&v103);
  v62 = 0;
  ppvObject = 0;
  memset_0(v79, 0, 0xB0u);
  v57 = 1;
  v66 = (unsigned __int64)a5;
  CTpSettings::Initialize((CTpSettings *)v112);
  v78[1] = v78[0];
  *v78[0] = 0;
  if ( v114 )
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v78, v114);
  v53 = v115;
  v17 = v118;
  v52 = v118;
  v18 = v117;
  if ( !v117 )
  {
    if ( a5 )
    {
      LODWORD(v19) = v113;
      v20 = (const wchar_t *)(*(__int64 (__fastcall **)(struct ITpCallbacks *))(*(_QWORD *)a5 + 120LL))(a5);
    }
    else
    {
      v21 = *((_QWORD *)this + 1);
      if ( v21 == *((_QWORD *)this + 2) )
        v20 = 0;
      else
        v20 = *(const wchar_t **)(*(_QWORD *)v21 + 16LL);
      v19 = L"telemetry.microsoft.com";
      if ( wcscmp_0(v20, L"watson") )
        MicrosoftTelemetryAssertTriggeredNoArgs(v23, v22, v24);
    }
    if ( !v20 )
    {
      v25 = -2147024843;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_108;
      v27 = 13;
      v28 = 2147942453LL;
      goto LABEL_15;
    }
    FinalServerName = CTpTransport::GetFinalServerName(
                        (unsigned int)v112,
                        (_DWORD)v19,
                        (_DWORD)v20,
                        *((_DWORD *)this + 134),
                        (__int64)v102);
    v25 = FinalServerName;
    if ( FinalServerName < 0 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_108;
      v27 = 14;
      v28 = (unsigned int)FinalServerName;
      goto LABEL_15;
    }
    v17 = v52;
  }
  if ( a5 )
    (**(void (__fastcall ***)(struct ITpCallbacks *, _QWORD))a5)(a5, v18);
  v30 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
    goto LABEL_35;
  if ( (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_23254a82e49430a3085a8c6bb5d92414_Traceguids, v102[0]);
    v30 = WPP_GLOBAL_Control;
  }
  if ( v30 == (wchar_t *)&WPP_GLOBAL_Control )
    goto LABEL_35;
  if ( (v30[14] & 4) != 0 )
  {
    WPP_SF_S(*((_QWORD *)v30 + 2), 16, WPP_23254a82e49430a3085a8c6bb5d92414_Traceguids, v78[0]);
    v30 = WPP_GLOBAL_Control;
  }
  if ( v30 == (wchar_t *)&WPP_GLOBAL_Control )
  {
LABEL_35:
    v31 = v53;
  }
  else
  {
    v31 = v53;
    if ( (v30[14] & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v30 + 2), 17, WPP_23254a82e49430a3085a8c6bb5d92414_Traceguids, v53);
      v30 = WPP_GLOBAL_Control;
    }
    if ( v30 != (wchar_t *)&WPP_GLOBAL_Control && (v30[14] & 4) != 0 )
      WPP_SF_d(*((_QWORD *)v30 + 2), 18, WPP_23254a82e49430a3085a8c6bb5d92414_Traceguids, v17);
  }
  appended = CTpTransport::BuildRequestXML(this, a5, (struct CMemoryByteStream *)&v68, &v61, &v56);
  v25 = appended;
  if ( appended < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_108;
    v27 = 19;
    goto LABEL_40;
  }
  v33 = hHandle;
  if ( hHandle )
  {
    v34 = WaitForSingleObject(hHandle, 0);
    if ( !v34 )
      goto LABEL_53;
    if ( v34 == 258 )
      goto LABEL_46;
    if ( v34 != -1 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v36, v35, v37);
      goto LABEL_46;
    }
    MicrosoftTelemetryAssertTriggeredNoArgs(v36, v35, v37);
    LastError = GetLastError();
    v39 = LastError == 0;
    if ( LastError > 0 )
      v39 = 0;
    if ( v39 )
    {
LABEL_53:
      v25 = -2147467260;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_108;
      v27 = 20;
      goto LABEL_56;
    }
  }
LABEL_46:
  v58 = v70[0];
  CMemoryByteStream::OpenForReadOnly((CMemoryByteStream *)&v107, &v58, 4u);
  appended = CCompoundStream::AppendStream((CCompoundStream *)v120, (struct IWerByteStream *)&v107);
  v25 = appended;
  if ( appended < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_108;
    v27 = 21;
    goto LABEL_40;
  }
  appended = CCompoundStream::AppendStream((CCompoundStream *)v120, (struct IWerByteStream *)&v68);
  v25 = appended;
  if ( appended < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_108;
    v27 = 22;
    goto LABEL_40;
  }
  if ( v65 )
  {
    appended = CCompoundStream::AppendStream((CCompoundStream *)v120, v65);
    v25 = appended;
    if ( appended < 0 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_108;
      v27 = 23;
      goto LABEL_40;
    }
  }
  *((_QWORD *)&v66 + 1) = CCompoundStream::GetSize((CCompoundStream *)v120);
  v79[0] = v102[0];
  v79[1] = v78[0];
  v79[2] = v120;
  v80 = v52;
  v81 = &v66;
  v82 = v31;
  v83 = v119;
  if ( (a6 & 1) != 0 || (v84 = 1, v116) )
    v84 = 0;
  v85 = a6;
  v86 = v73;
  v87 = v33;
  v88 = v74;
  v89 = a5;
  v90 = 0;
  v91 = a15;
  TickCount = GetTickCount();
  if ( (unsigned __int8)IsXerGetMachineIdPresent() )
  {
    v57 = 0;
    v16 = XerTpUpload(v79);
    if ( v16 != -2147467263 )
      goto LABEL_73;
    v57 = 1;
  }
  v16 = TpUpload((struct _WER_TP_UPLOAD_STATE *)v79, v63);
LABEL_73:
  v59 = GetTickCount() - TickCount;
  if ( v16 < 0 )
  {
    v25 = v16;
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_108;
    v27 = 24;
    v28 = (unsigned int)v16;
    goto LABEL_15;
  }
  v41 = GetTickCount();
  v42 = ppvObject;
  ppvObject = 0;
  if ( v42 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v42 + 16LL))(v42);
  appended = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v25 = appended;
  if ( appended < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_108;
    v27 = 25;
    goto LABEL_40;
  }
  appended = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 2);
  v25 = appended;
  if ( appended < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_108;
    v27 = 26;
    goto LABEL_40;
  }
  appended = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 1, 2);
  v25 = appended;
  if ( appended < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_108;
    v27 = 27;
    goto LABEL_40;
  }
  v62 = 0;
  if ( !a5
    || ((*(int (__fastcall **)(struct ITpCallbacks *, _BYTE **))(*(_QWORD *)a5 + 88LL))(a5, &v62) >= 0
      ? (v43 = v62)
      : (v43 = 0, v62 = 0),
        !v43) )
  {
    CMemoryByteStream::OpenForReadOnly((CMemoryByteStream *)&v103, v99, v100);
    v62 = v111;
  }
  appended = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 24LL))(ppvObject);
  v25 = appended;
  if ( appended < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_108;
    v27 = 28;
LABEL_40:
    v28 = (unsigned int)appended;
LABEL_15:
    WPP_SF_d(*((_QWORD *)v26 + 2), v27, WPP_23254a82e49430a3085a8c6bb5d92414_Traceguids, v28);
    goto LABEL_108;
  }
  v25 = CTpResponseMessage::Parse(v76);
  v55 = GetTickCount() - v41;
  v60 = v25;
  if ( (v25 & 0x80000000) == 0 )
  {
    v25 = 0;
  }
  else
  {
    if ( a5 )
      (*(void (__fastcall **)(struct ITpCallbacks *, _QWORD))(*(_QWORD *)a5 + 96LL))(a5, v25);
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v27 = 29;
LABEL_56:
      v28 = v25;
      goto LABEL_15;
    }
  }
LABEL_108:
  if ( a5 )
  {
    v44 = *(void (__fastcall **)(struct ITpCallbacks *, _QWORD, _QWORD, _QWORD, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, int, int, DWORD, unsigned __int64, wchar_t *, _QWORD, unsigned int))(*(_QWORD *)a5 + 112LL);
    v45 = v102[0];
    Size = CCompoundStream::GetSize((CCompoundStream *)v120);
    *(_QWORD *)v51 = v45;
    v47 = v64;
    v48 = v55;
    v44(a5, v56, v55, v92, v93, v94, v95, v96, v97, v98, v16, v59, Size, v64, *(_QWORD *)v51, v25);
  }
  else
  {
    v48 = v55;
    v47 = v64;
  }
  if ( v77 )
    CTpLogger::LogExchange(
      v77,
      v102[0],
      v78[0],
      v47,
      v93,
      v92,
      v61,
      v56,
      v69[1],
      v70[0],
      v65,
      v94,
      v60,
      v48,
      v96,
      v101,
      v97,
      v99,
      v100,
      v95,
      v86);
  v49 = ppvObject;
  ppvObject = 0;
  if ( v49 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v49 + 16LL))(v49);
  if ( v57 )
    TpCompleteUpload((struct _WER_TP_UPLOAD_STATE *)v79);
  else
    XerTpCompleteUpload(v79);
  utl::unique_ptr<IXmlWriter,tlx::release_delete>::~unique_ptr<IXmlWriter,tlx::release_delete>(&ppvObject);
  CIStreamAdapter::~CIStreamAdapter((CIStreamAdapter *)v111);
  CMemoryByteStream::~CMemoryByteStream((CMemoryByteStream *)&v103);
  v120[0] = &CCompoundStream::`vftable';
  CMemoryByteStream::~CMemoryByteStream((CMemoryByteStream *)&v107);
  CMemoryByteStream::~CMemoryByteStream((CMemoryByteStream *)&v68);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v102);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v78);
  CTpSettings::~CTpSettings((CTpSettings *)v112);
  return v25;
}

```

## disassembly

```asm
0x18003e2b4  push    rbp
0x18003e2b6  push    rbx
0x18003e2b7  push    rsi
0x18003e2b8  push    rdi
0x18003e2b9  push    r12
0x18003e2bb  push    r13
0x18003e2bd  push    r14
0x18003e2bf  push    r15
0x18003e2c1  lea     rbp, [rsp-368h]
0x18003e2c9  sub     rsp, 498h
0x18003e2d0  mov     [rbp+3A0h+var_378], r9
0x18003e2d4  mov     [rbp+3A0h+var_370], r8
0x18003e2d8  mov     [rbp+3A0h+var_3D8], rdx
0x18003e2dc  mov     r13, rcx
0x18003e2df  mov     r14, [rbp+3A0h+arg_20]
0x18003e2e6  mov     rax, [rbp+3A0h+arg_38]
0x18003e2ed  mov     [rbp+3A0h+var_380], rax
0x18003e2f1  mov     rax, [rbp+3A0h+arg_40]
0x18003e2f8  mov     [rbp+3A0h+hHandle], rax
0x18003e2fc  mov     rax, [rbp+3A0h+arg_48]
0x18003e303  mov     [rbp+3A0h+var_368], rax
0x18003e307  mov     rax, [rbp+3A0h+arg_50]
0x18003e30e  mov     [rbp+3A0h+var_3E0], rax
0x18003e312  mov     rax, [rbp+3A0h+arg_60]
0x18003e319  mov     [rbp+3A0h+var_388], rax
0x18003e31d  mov     rax, [rbp+3A0h+arg_68]
0x18003e324  mov     [rbp+3A0h+var_3E8], rax
0x18003e328  lea     rcx, [rbp+3A0h+var_200]; this
0x18003e32f  call    ??0CTpSettings@@QEAA@XZ; CTpSettings::CTpSettings(void)
0x18003e334  nop
0x18003e335  lea     rcx, [rbp+3A0h+var_360]; void *
0x18003e339  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18003e33e  nop
0x18003e33f  lea     rcx, [rbp+3A0h+var_290]; void *
0x18003e346  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18003e34b  nop
0x18003e34c  xor     esi, esi
0x18003e34e  mov     [rbp+3A0h+var_3F8], esi
0x18003e351  mov     [rbp+3A0h+var_3FC], esi
0x18003e354  mov     r12d, esi
0x18003e357  mov     [rbp+3A0h+var_40C], esi
0x18003e35a  mov     [rbp+3A0h+var_410], esi
0x18003e35d  mov     [rbp+3A0h+var_400], esi
0x18003e360  xorps   xmm0, xmm0
0x18003e363  xor     eax, eax
0x18003e365  movups  [rbp+3A0h+var_3D0], xmm0
0x18003e369  mov     [rbp+3A0h+var_3C0], rax
0x18003e36d  mov     [rbp+3A0h+var_404], esi
0x18003e370  lea     rbx, ??_7CMemoryByteStream@@6B@; const CMemoryByteStream::`vftable'
0x18003e377  mov     [rbp+3A0h+var_3B8], rbx
0x18003e37b  movdqu  xmmword ptr [rbp+3A0h+var_3B0], xmm0
0x18003e380  mov     qword ptr [rbp+3A0h+var_3A0], rsi
0x18003e384  mov     [rbp+3A0h+var_398], esi
0x18003e387  mov     [rbp+3A0h+var_248], rbx
0x18003e38e  movdqu  [rbp+3A0h+var_240], xmm0
0x18003e396  mov     [rbp+3A0h+var_230], rsi
0x18003e39d  mov     [rbp+3A0h+var_228], esi
0x18003e3a3  lea     rax, ??_7CCompoundStream@@6B@; const CCompoundStream::`vftable'
0x18003e3aa  mov     [rbp+3A0h+var_150], rax
0x18003e3b1  mov     [rbp+3A0h+var_148], rsi
0x18003e3b8  xor     edx, edx; Val
0x18003e3ba  mov     r8d, 100h; Size
0x18003e3c0  lea     rcx, [rbp+3A0h+var_140]; void *
0x18003e3c7  call    memset_0
0x18003e3cc  nop
0x18003e3cd  mov     [rbp+3A0h+var_270], rbx
0x18003e3d4  xorps   xmm0, xmm0
0x18003e3d7  movdqu  [rbp+3A0h+var_268], xmm0
0x18003e3df  mov     [rbp+3A0h+var_258], rsi
0x18003e3e6  mov     [rbp+3A0h+var_250], esi
0x18003e3ec  lea     rdx, [rbp+3A0h+var_270]; struct IWerByteStream *
0x18003e3f3  lea     rcx, [rbp+3A0h+var_220]; this
0x18003e3fa  call    ??0CIStreamAdapter@@QEAA@PEAUIWerByteStream@@@Z; CIStreamAdapter::CIStreamAdapter(IWerByteStream *)
0x18003e3ff  nop
0x18003e400  mov     [rbp+3A0h+var_3F0], rsi
0x18003e404  mov     [rbp+3A0h+ppvObject], rsi
0x18003e408  xor     edx, edx; Val
0x18003e40a  mov     r8d, 0B0h; Size
0x18003e410  lea     rcx, [rbp+3A0h+var_340]; void *
0x18003e414  call    memset_0
0x18003e419  mov     [rbp+3A0h+var_408], 1
0x18003e420  mov     qword ptr [rbp+3A0h+var_3D0], r14
0x18003e424  mov     qword ptr [rbp+3A0h+var_3D0+8], rsi
0x18003e428  mov     byte ptr [rbp+3A0h+var_3C0], sil
0x18003e42c  lea     rcx, [rbp+3A0h+var_200]; this
0x18003e433  call    ?Initialize@CTpSettings@@QEAAXXZ; CTpSettings::Initialize(void)
0x18003e438  mov     rcx, [rbp+3A0h+var_360]
0x18003e43c  mov     [rbp+3A0h+var_358], rcx
0x18003e440  mov     [rcx], si
0x18003e443  mov     rdx, [rbp+3A0h+var_198]
0x18003e44a  test    rdx, rdx
0x18003e44d  jz      short loc_18003E458
0x18003e44f  lea     rcx, [rbp+3A0h+var_360]
0x18003e453  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18003e458  mov     eax, [rbp+3A0h+var_178]
0x18003e45e  mov     [rbp+3A0h+var_41C], eax
0x18003e461  movzx   esi, [rbp+3A0h+var_16C]
0x18003e468  mov     [rbp+3A0h+var_420], si
0x18003e46c  mov     r15d, [rbp+3A0h+var_170]
0x18003e473  test    r15d, r15d
0x18003e476  jnz     loc_18003E572
0x18003e47c  test    r14, r14
0x18003e47f  jz      short loc_18003E49C
0x18003e481  mov     rdi, [rbp+3A0h+var_1D8]
0x18003e488  mov     rax, [r14]
0x18003e48b  mov     rcx, r14
0x18003e48e  mov     rax, [rax+78h]
0x18003e492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e497  mov     rbx, rax
0x18003e49a  jmp     short loc_18003E4D0
0x18003e49c  mov     rax, [r13+8]
0x18003e4a0  cmp     rax, [r13+10h]
0x18003e4a4  jnz     short loc_18003E4AA
0x18003e4a6  xor     ebx, ebx
0x18003e4a8  jmp     short loc_18003E4B1
0x18003e4aa  mov     rax, [rax]
0x18003e4ad  mov     rbx, [rax+10h]
0x18003e4b1  lea     rdi, aTelemetryMicro; "telemetry.microsoft.com"
0x18003e4b8  lea     rdx, aWatson_0; "watson"
0x18003e4bf  mov     rcx, rbx; String1
0x18003e4c2  call    wcscmp_0
0x18003e4c7  test    eax, eax
0x18003e4c9  jz      short loc_18003E4D0
0x18003e4cb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003e4d0  test    rbx, rbx
0x18003e4d3  jnz     short loc_18003E518
0x18003e4d5  mov     esi, 80070035h
0x18003e4da  lea     rbx, WPP_GLOBAL_Control
0x18003e4e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e4e8  cmp     rcx, rbx
0x18003e4eb  jz      loc_18003EB06
0x18003e4f1  test    byte ptr [rcx+1Ch], 1
0x18003e4f5  jz      loc_18003EB06
0x18003e4fb  mov     edx, 0Dh
0x18003e500  mov     r9d, esi
0x18003e503  lea     r8, WPP_23254a82e49430a3085a8c6bb5d92414_Traceguids
0x18003e50a  mov     rcx, [rcx+10h]
0x18003e50e  call    WPP_SF_d
0x18003e513  jmp     loc_18003EB06
0x18003e518  lea     rax, [rbp+3A0h+var_290]
0x18003e51f  mov     [rsp+4D0h+var_4B0], rax
0x18003e524  mov     r9d, [r13+218h]
0x18003e52b  mov     r8, rbx
0x18003e52e  mov     rdx, rdi
0x18003e531  lea     rcx, [rbp+3A0h+var_200]
0x18003e538  call    ?GetFinalServerName@CTpTransport@@SAJAEBVCTpSettings@@PEB_W1HAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CTpTransport::GetFinalServerName(CTpSettings const &,wchar_t const *,wchar_t const *,int,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18003e53d  mov     esi, eax
0x18003e53f  test    eax, eax
0x18003e541  jns     short loc_18003E56E
0x18003e543  lea     rbx, WPP_GLOBAL_Control
0x18003e54a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e551  cmp     rcx, rbx
0x18003e554  jz      loc_18003EB06
0x18003e55a  test    byte ptr [rcx+1Ch], 1
0x18003e55e  jz      loc_18003EB06
0x18003e564  mov     edx, 0Eh
0x18003e569  mov     r9d, eax
0x18003e56c  jmp     short loc_18003E503
0x18003e56e  movzx   esi, [rbp+3A0h+var_420]
0x18003e572  test    r14, r14
0x18003e575  jz      short loc_18003E588
0x18003e577  mov     rax, [r14]
0x18003e57a  mov     edx, r15d
0x18003e57d  mov     rcx, r14
0x18003e580  mov     rax, [rax]
0x18003e583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e588  lea     rbx, WPP_GLOBAL_Control
0x18003e58f  lea     rdi, WPP_23254a82e49430a3085a8c6bb5d92414_Traceguids
0x18003e596  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e59d  cmp     rcx, rbx
0x18003e5a0  jz      loc_18003E63E
0x18003e5a6  test    byte ptr [rcx+1Ch], 4
0x18003e5aa  jz      short loc_18003E5CB
0x18003e5ac  mov     edx, 0Fh
0x18003e5b1  mov     r9, [rbp+3A0h+var_290]
0x18003e5b8  mov     r8, rdi
0x18003e5bb  mov     rcx, [rcx+10h]
0x18003e5bf  call    WPP_SF_S
0x18003e5c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e5cb  cmp     rcx, rbx
0x18003e5ce  jz      short loc_18003E63E
0x18003e5d0  test    byte ptr [rcx+1Ch], 4
0x18003e5d4  jz      short loc_18003E5F2
0x18003e5d6  mov     edx, 10h
0x18003e5db  mov     r9, [rbp+3A0h+var_360]
0x18003e5df  mov     r8, rdi
0x18003e5e2  mov     rcx, [rcx+10h]
0x18003e5e6  call    WPP_SF_S
0x18003e5eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e5f2  cmp     rcx, rbx
0x18003e5f5  jz      short loc_18003E63E
0x18003e5f7  mov     r15d, [rbp+3A0h+var_41C]
0x18003e5fb  test    byte ptr [rcx+1Ch], 4
0x18003e5ff  jz      short loc_18003E61C
0x18003e601  mov     edx, 11h
0x18003e606  mov     r9d, r15d
0x18003e609  mov     r8, rdi
0x18003e60c  mov     rcx, [rcx+10h]
0x18003e610  call    WPP_SF_d
0x18003e615  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e61c  cmp     rcx, rbx
0x18003e61f  jz      short loc_18003E642
0x18003e621  test    byte ptr [rcx+1Ch], 4
0x18003e625  jz      short loc_18003E642
0x18003e627  movzx   r9d, si
0x18003e62b  mov     edx, 12h
0x18003e630  mov     r8, rdi
0x18003e633  mov     rcx, [rcx+10h]
0x18003e637  call    WPP_SF_d
0x18003e63c  jmp     short loc_18003E642
0x18003e63e  mov     r15d, [rbp+3A0h+var_41C]
0x18003e642  lea     rax, [rbp+3A0h+var_40C]
0x18003e646  mov     [rsp+4D0h+var_4B0], rax; unsigned int *
0x18003e64b  lea     r9, [rbp+3A0h+var_3F8]; int *
0x18003e64f  lea     r8, [rbp+3A0h+var_3B8]; struct CMemoryByteStream *
0x18003e653  mov     rdx, r14; struct ITpCallbacks *
0x18003e656  mov     rcx, r13; this
0x18003e659  call    ?BuildRequestXML@CTpTransport@@SAJPEAVCTpRequestMessage@@PEAUITpCallbacks@@AEAVCMemoryByteStream@@AEAJAEAK@Z; CTpTransport::BuildRequestXML(CTpRequestMessage *,ITpCallbacks *,CMemoryByteStream &,long &,ulong &)
0x18003e65e  mov     esi, eax
0x18003e660  test    eax, eax
0x18003e662  jns     short loc_18003E68E
0x18003e664  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e66b  cmp     rcx, rbx
0x18003e66e  jz      loc_18003EB06
0x18003e674  test    byte ptr [rcx+1Ch], 1
0x18003e678  jz      loc_18003EB06
0x18003e67e  mov     edx, 13h
0x18003e683  mov     r9d, eax
0x18003e686  mov     r8, rdi
0x18003e689  jmp     loc_18003E50A
0x18003e68e  mov     r13, [rbp+3A0h+hHandle]
0x18003e692  test    r13, r13
0x18003e695  jz      short loc_18003E6C1
0x18003e697  xor     edx, edx; dwMilliseconds
0x18003e699  mov     rcx, r13; hHandle
0x18003e69c  call    cs:__imp_WaitForSingleObject
0x18003e6a3  nop     dword ptr [rax+rax+00h]
0x18003e6a8  test    eax, eax
0x18003e6aa  jz      loc_18003E73B
0x18003e6b0  cmp     eax, 102h
0x18003e6b5  jz      short loc_18003E6C1
0x18003e6b7  cmp     eax, 0FFFFFFFFh
0x18003e6ba  jz      short loc_18003E71A
0x18003e6bc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003e6c1  mov     eax, [rbp+3A0h+var_3A0]
0x18003e6c4  mov     [rbp+3A0h+var_404], eax
0x18003e6c7  mov     r8d, 4; unsigned int
0x18003e6cd  lea     rdx, [rbp+3A0h+var_404]; void *
0x18003e6d1  lea     rcx, [rbp+3A0h+var_248]; this
0x18003e6d8  call    ?OpenForReadOnly@CMemoryByteStream@@QEAAXPEBXK@Z; CMemoryByteStream::OpenForReadOnly(void const *,ulong)
0x18003e6dd  lea     rdx, [rbp+3A0h+var_248]; struct IWerByteStream *
0x18003e6e4  lea     rcx, [rbp+3A0h+var_150]; this
0x18003e6eb  call    ?AppendStream@CCompoundStream@@QEAAJPEAUIWerByteStream@@@Z; CCompoundStream::AppendStream(IWerByteStream *)
0x18003e6f0  mov     esi, eax
0x18003e6f2  test    eax, eax
0x18003e6f4  jns     short loc_18003E767
0x18003e6f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e6fd  cmp     rcx, rbx
0x18003e700  jz      loc_18003EB06
0x18003e706  test    byte ptr [rcx+1Ch], 1
0x18003e70a  jz      loc_18003EB06
0x18003e710  mov     edx, 15h
0x18003e715  jmp     loc_18003E683
0x18003e71a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003e71f  call    cs:__imp_GetLastError
0x18003e726  nop     dword ptr [rax+rax+00h]
0x18003e72b  test    eax, eax
0x18003e72d  jle     short loc_18003E739
0x18003e72f  movzx   eax, ax
0x18003e732  or      eax, 80070000h
0x18003e737  test    eax, eax
0x18003e739  jnz     short loc_18003E6C1
0x18003e73b  mov     esi, 80004004h
0x18003e740  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e747  cmp     rcx, rbx
0x18003e74a  jz      loc_18003EB06
0x18003e750  test    byte ptr [rcx+1Ch], 1
0x18003e754  jz      loc_18003EB06
0x18003e75a  mov     edx, 14h
0x18003e75f  mov     r9d, esi
0x18003e762  jmp     loc_18003E686
0x18003e767  lea     rdx, [rbp+3A0h+var_3B8]; struct IWerByteStream *
0x18003e76b  lea     rcx, [rbp+3A0h+var_150]; this
0x18003e772  call    ?AppendStream@CCompoundStream@@QEAAJPEAUIWerByteStream@@@Z; CCompoundStream::AppendStream(IWerByteStream *)
0x18003e777  mov     esi, eax
0x18003e779  test    eax, eax
0x18003e77b  jns     short loc_18003E7A1
0x18003e77d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e784  cmp     rcx, rbx
0x18003e787  jz      loc_18003EB06
0x18003e78d  test    byte ptr [rcx+1Ch], 1
0x18003e791  jz      loc_18003EB06
0x18003e797  mov     edx, 16h
0x18003e79c  jmp     loc_18003E683
0x18003e7a1  mov     rax, [rbp+3A0h+var_3D8]
0x18003e7a5  test    rax, rax
0x18003e7a8  jz      short loc_18003E7E3
0x18003e7aa  mov     rdx, rax; struct IWerByteStream *
0x18003e7ad  lea     rcx, [rbp+3A0h+var_150]; this
0x18003e7b4  call    ?AppendStream@CCompoundStream@@QEAAJPEAUIWerByteStream@@@Z; CCompoundStream::AppendStream(IWerByteStream *)
  ... truncated ...
```
