# CTpTransport::DoExchange(CTpRequestMessage *,IWerByteStream *,CTpResponseMessage *,long (*const *)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *),ITpCallbacks *,ulong,wchar_t const *,void *,void *,CTpLogger *,wchar_t const *,ISequentialStream *,wchar_t const *,WINHTTP_TIMEOUTS *,ulong)

- ea: `0x18003c24c`
- end: `0x18003cc96`
- name: `?DoExchange@CTpTransport@@SAJPEAVCTpRequestMessage@@PEAUIWerByteStream@@PEAVCTpResponseMessage@@PEBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZPEAUITpCallbacks@@K3PEAX7PEAVCTpLogger@@3PEAUISequentialStream@@3PEAUWINHTTP_TIMEOUTS@@K@Z`
- size: `2634`
- prototype: `__int64 __usercall@<rax>(struct CTpRequestMessage *this@<rcx>, struct ITpCallbacks *, int, int, __int64, __int64, __int64, __int64, int, __int64, __int64, int)`
- caller_count: `5`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024998`
- `0x180083cfc`
- `0x1800843d0`
- `0x180085b88`
- `0x180088ef8`

## callees

- `0x18000bc10`
- `0x18000c390`
- `0x18000dad0`
- `0x180013730`
- `0x18001919c`
- `0x18001fe24`
- `0x180021678`
- `0x1800272f0`
- `0x18002ff40`
- `0x18003bf14`
- `0x18003c1e4`
- `0x18003c24c`
- `0x180043d04`
- `0x18004b204`
- `0x18004c614`
- `0x18004c634`
- `0x18004c8ec`
- `0x1800517cc`
- `0x180051ff8`
- `0x180095be8`
- `0x18009fecc`
- `0x1800a0ec8`
- `0x1800a19f4`
- `0x1800a1af0`
- `0x1800a1b20`
- `0x1800aa060`
- `0x1800ad010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003c82e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003c86b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003c8a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003ca26`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003c82e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003c86b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003c8a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003ca26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c6b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c6b1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003c634`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003c634`
- `ext-ms-win-wer-xbox-l1-1-0!XerTpUpload` at `0x18003c847`
- `ext-ms-win-wer-xbox-l1-1-0!XerTpUpload` at `0x18003c847`
- `ext-ms-win-wer-xbox-l1-1-0!XerTpCompleteUpload` at `0x18003cc0d`
- `ext-ms-win-wer-xbox-l1-1-0!XerTpCompleteUpload` at `0x18003cc0d`
- `XmlLite!CreateXmlReader` at `0x18003c8d6`
- `XmlLite!CreateXmlReader` at `0x18003c8d6`

## string_xrefs

- `0x18003c449`: `telemetry.microsoft.com`

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
  unsigned int v22; // esi
  wchar_t *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r9
  int FinalServerName; // eax
  wchar_t *v27; // rcx
  unsigned int v28; // r15d
  HRESULT appended; // eax
  HANDLE v30; // r13
  DWORD v31; // eax
  signed int LastError; // eax
  bool v33; // zf
  DWORD TickCount; // esi
  __int64 v35; // rcx
  DWORD v36; // r15d
  void *v37; // rcx
  _BYTE *v38; // rdx
  void (__fastcall *v39)(struct ITpCallbacks *, _QWORD, _QWORD, _QWORD, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, int, int, DWORD, unsigned __int64, wchar_t *, _QWORD, unsigned int); // rdi
  wchar_t *v40; // rbx
  unsigned __int64 Size; // rax
  wchar_t *v42; // r15
  unsigned int v43; // ebx
  void *v44; // rcx
  unsigned int v46[2]; // [rsp+70h] [rbp-C0h]
  unsigned __int16 v47; // [rsp+B0h] [rbp-80h]
  unsigned int v48; // [rsp+B4h] [rbp-7Ch]
  void *ppvObject; // [rsp+B8h] [rbp-78h] BYREF
  unsigned int v50; // [rsp+C0h] [rbp-70h]
  unsigned int v51; // [rsp+C4h] [rbp-6Ch] BYREF
  int v52; // [rsp+C8h] [rbp-68h]
  unsigned int v53; // [rsp+CCh] [rbp-64h] BYREF
  DWORD v54; // [rsp+D0h] [rbp-60h]
  int v55; // [rsp+D4h] [rbp-5Ch]
  int v56; // [rsp+D8h] [rbp-58h] BYREF
  _BYTE *v57; // [rsp+E0h] [rbp-50h] BYREF
  struct WINHTTP_TIMEOUTS *v58; // [rsp+E8h] [rbp-48h]
  wchar_t *v59; // [rsp+F0h] [rbp-40h]
  struct IWerByteStream *v60; // [rsp+F8h] [rbp-38h]
  __int128 v61; // [rsp+100h] [rbp-30h] BYREF
  __int64 v62; // [rsp+110h] [rbp-20h]
  void **v63; // [rsp+118h] [rbp-18h] BYREF
  void *v64[2]; // [rsp+120h] [rbp-10h]
  unsigned int v65[2]; // [rsp+130h] [rbp+0h]
  int v66; // [rsp+138h] [rbp+8h]
  HANDLE hHandle; // [rsp+140h] [rbp+10h]
  wchar_t *v68; // [rsp+148h] [rbp+18h]
  __int64 v69; // [rsp+150h] [rbp+20h]
  __int64 v70; // [rsp+158h] [rbp+28h]
  CTpResponseMessage *v71; // [rsp+160h] [rbp+30h]
  CTpLogger *v72; // [rsp+168h] [rbp+38h]
  wchar_t *v73[4]; // [rsp+170h] [rbp+40h] BYREF
  _QWORD v74[3]; // [rsp+190h] [rbp+60h] BYREF
  unsigned __int16 v75; // [rsp+1A8h] [rbp+78h]
  __int128 *v76; // [rsp+1B0h] [rbp+80h]
  unsigned int v77; // [rsp+1B8h] [rbp+88h]
  int v78; // [rsp+1BCh] [rbp+8Ch]
  int v79; // [rsp+1C0h] [rbp+90h]
  int v80; // [rsp+1D8h] [rbp+A8h]
  wchar_t *v81; // [rsp+1E0h] [rbp+B0h]
  HANDLE v82; // [rsp+1E8h] [rbp+B8h]
  __int64 v83; // [rsp+1F0h] [rbp+C0h]
  struct ITpCallbacks *v84; // [rsp+1F8h] [rbp+C8h]
  __int64 v85; // [rsp+200h] [rbp+D0h]
  int v86; // [rsp+208h] [rbp+D8h]
  unsigned int v87; // [rsp+20Ch] [rbp+DCh]
  unsigned int v88; // [rsp+210h] [rbp+E0h]
  unsigned int v89; // [rsp+214h] [rbp+E4h]
  unsigned int v90; // [rsp+218h] [rbp+E8h]
  unsigned int v91; // [rsp+21Ch] [rbp+ECh]
  unsigned int v92; // [rsp+220h] [rbp+F0h]
  int v93; // [rsp+224h] [rbp+F4h]
  void *v94; // [rsp+228h] [rbp+F8h]
  unsigned int v95; // [rsp+230h] [rbp+100h]
  int v96; // [rsp+234h] [rbp+104h]
  wchar_t *v97[4]; // [rsp+240h] [rbp+110h] BYREF
  void **v98; // [rsp+260h] [rbp+130h] BYREF
  __int128 v99; // [rsp+268h] [rbp+138h]
  __int64 v100; // [rsp+278h] [rbp+148h]
  int v101; // [rsp+280h] [rbp+150h]
  void **v102; // [rsp+288h] [rbp+158h] BYREF
  __int128 v103; // [rsp+290h] [rbp+160h]
  __int64 v104; // [rsp+2A0h] [rbp+170h]
  int v105; // [rsp+2A8h] [rbp+178h]
  _BYTE v106[32]; // [rsp+2B0h] [rbp+180h] BYREF
  _BYTE v107[40]; // [rsp+2D0h] [rbp+1A0h] BYREF
  __int64 v108; // [rsp+2F8h] [rbp+1C8h]
  __int64 v109; // [rsp+338h] [rbp+208h]
  unsigned int v110; // [rsp+358h] [rbp+228h]
  int v111; // [rsp+35Ch] [rbp+22Ch]
  unsigned int v112; // [rsp+360h] [rbp+230h]
  unsigned __int16 v113; // [rsp+364h] [rbp+234h]
  int v114; // [rsp+368h] [rbp+238h]
  _QWORD v115[2]; // [rsp+380h] [rbp+250h] BYREF
  _BYTE v116[320]; // [rsp+390h] [rbp+260h] BYREF

  v70 = a4;
  v71 = a3;
  v60 = a2;
  v69 = a8;
  hHandle = a9;
  v72 = a10;
  v59 = a11;
  v68 = a13;
  v58 = a14;
  CTpSettings::CTpSettings((CTpSettings *)v107);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v73);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v97);
  v56 = 0;
  v55 = 0;
  v16 = 0;
  v51 = 0;
  v50 = 0;
  v54 = 0;
  v62 = 0;
  v53 = 0;
  v63 = &CMemoryByteStream::`vftable';
  *(_OWORD *)v64 = 0;
  *(_QWORD *)v65 = 0;
  v66 = 0;
  v102 = &CMemoryByteStream::`vftable';
  v103 = 0;
  v104 = 0;
  v105 = 0;
  v115[0] = &CCompoundStream::`vftable';
  v115[1] = 0;
  memset_0(v116, 0, 0x100u);
  v98 = &CMemoryByteStream::`vftable';
  v99 = 0;
  v100 = 0;
  v101 = 0;
  CIStreamAdapter::CIStreamAdapter((CIStreamAdapter *)v106, (struct IWerByteStream *)&v98);
  v57 = 0;
  ppvObject = 0;
  memset_0(v74, 0, 0xB0u);
  v52 = 1;
  v61 = (unsigned __int64)a5;
  CTpSettings::Initialize((CTpSettings *)v107);
  v73[1] = v73[0];
  *v73[0] = 0;
  if ( v109 )
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v73, v109);
  v48 = v110;
  v17 = v113;
  v47 = v113;
  v18 = v112;
  if ( !v112 )
  {
    if ( a5 )
    {
      LODWORD(v19) = v108;
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
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    if ( !v20 )
    {
      v22 = -2147024843;
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_108;
      v24 = 13;
      v25 = 2147942453LL;
      goto LABEL_15;
    }
    FinalServerName = CTpTransport::GetFinalServerName(
                        (unsigned int)v107,
                        (_DWORD)v19,
                        (_DWORD)v20,
                        *((_DWORD *)this + 134),
                        (__int64)v97);
    v22 = FinalServerName;
    if ( FinalServerName < 0 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_108;
      v24 = 14;
      v25 = (unsigned int)FinalServerName;
      goto LABEL_15;
    }
    v17 = v47;
  }
  if ( a5 )
    (**(void (__fastcall ***)(struct ITpCallbacks *, _QWORD))a5)(a5, v18);
  v27 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
    goto LABEL_35;
  if ( (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_23254a82e49430a3085a8c6bb5d92414_Traceguids, v97[0]);
    v27 = WPP_GLOBAL_Control;
  }
  if ( v27 == (wchar_t *)&WPP_GLOBAL_Control )
    goto LABEL_35;
  if ( (v27[14] & 4) != 0 )
  {
    WPP_SF_S(*((_QWORD *)v27 + 2), 16, WPP_23254a82e49430a3085a8c6bb5d92414_Traceguids, v73[0]);
    v27 = WPP_GLOBAL_Control;
  }
  if ( v27 == (wchar_t *)&WPP_GLOBAL_Control )
  {
LABEL_35:
    v28 = v48;
  }
  else
  {
    v28 = v48;
    if ( (v27[14] & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v27 + 2), 17, WPP_23254a82e49430a3085a8c6bb5d92414_Traceguids, v48);
      v27 = WPP_GLOBAL_Control;
    }
    if ( v27 != (wchar_t *)&WPP_GLOBAL_Control && (v27[14] & 4) != 0 )
      WPP_SF_d(*((_QWORD *)v27 + 2), 18, WPP_23254a82e49430a3085a8c6bb5d92414_Traceguids, v17);
  }
  appended = CTpTransport::BuildRequestXML(this, a5, (struct CMemoryByteStream *)&v63, &v56, &v51);
  v22 = appended;
  if ( appended < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_108;
    v24 = 19;
    goto LABEL_40;
  }
  v30 = hHandle;
  if ( hHandle )
  {
    v31 = WaitForSingleObject(hHandle, 0);
    if ( !v31 )
      goto LABEL_53;
    if ( v31 == 258 )
      goto LABEL_46;
    if ( v31 != -1 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      goto LABEL_46;
    }
    MicrosoftTelemetryAssertTriggeredNoArgs();
    LastError = GetLastError();
    v33 = LastError == 0;
    if ( LastError > 0 )
      v33 = 0;
    if ( v33 )
    {
LABEL_53:
      v22 = -2147467260;
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_108;
      v24 = 20;
      goto LABEL_56;
    }
  }
LABEL_46:
  v53 = v65[0];
  CMemoryByteStream::OpenForReadOnly((CMemoryByteStream *)&v102, &v53, 4);
  appended = CCompoundStream::AppendStream((CCompoundStream *)v115, (struct IWerByteStream *)&v102);
  v22 = appended;
  if ( appended < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_108;
    v24 = 21;
    goto LABEL_40;
  }
  appended = CCompoundStream::AppendStream((CCompoundStream *)v115, (struct IWerByteStream *)&v63);
  v22 = appended;
  if ( appended < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_108;
    v24 = 22;
    goto LABEL_40;
  }
  if ( v60 )
  {
    appended = CCompoundStream::AppendStream((CCompoundStream *)v115, v60);
    v22 = appended;
    if ( appended < 0 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_108;
      v24 = 23;
      goto LABEL_40;
    }
  }
  *((_QWORD *)&v61 + 1) = CCompoundStream::GetSize((CCompoundStream *)v115);
  v74[0] = v97[0];
  v74[1] = v73[0];
  v74[2] = v115;
  v75 = v47;
  v76 = &v61;
  v77 = v28;
  v78 = v114;
  if ( (a6 & 1) != 0 || (v79 = 1, v111) )
    v79 = 0;
  v80 = a6;
  v81 = v68;
  v82 = v30;
  v83 = v69;
  v84 = a5;
  v85 = 0;
  v86 = a15;
  TickCount = GetTickCount();
  if ( (unsigned __int8)IsXerGetMachineIdPresent(v35) )
  {
    v52 = 0;
    v16 = XerTpUpload(v74);
    if ( v16 != -2147467263 )
      goto LABEL_73;
    v52 = 1;
  }
  v16 = TpUpload((struct _WER_TP_UPLOAD_STATE *)v74, v58);
LABEL_73:
  v54 = GetTickCount() - TickCount;
  if ( v16 < 0 )
  {
    v22 = v16;
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_108;
    v24 = 24;
    v25 = (unsigned int)v16;
    goto LABEL_15;
  }
  v36 = GetTickCount();
  v37 = ppvObject;
  ppvObject = 0;
  if ( v37 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v37 + 16LL))(v37);
  appended = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v22 = appended;
  if ( appended < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_108;
    v24 = 25;
    goto LABEL_40;
  }
  appended = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 2);
  v22 = appended;
  if ( appended < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_108;
    v24 = 26;
    goto LABEL_40;
  }
  appended = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 1, 2);
  v22 = appended;
  if ( appended < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_108;
    v24 = 27;
    goto LABEL_40;
  }
  v57 = 0;
  if ( !a5
    || ((*(int (__fastcall **)(struct ITpCallbacks *, _BYTE **))(*(_QWORD *)a5 + 88LL))(a5, &v57) >= 0
      ? (v38 = v57)
      : (v38 = 0, v57 = 0),
        !v38) )
  {
    CMemoryByteStream::OpenForReadOnly((CMemoryByteStream *)&v98, v94, v95);
    v57 = v106;
  }
  appended = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 24LL))(ppvObject);
  v22 = appended;
  if ( appended < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_108;
    v24 = 28;
LABEL_40:
    v25 = (unsigned int)appended;
LABEL_15:
    WPP_SF_d(*((_QWORD *)v23 + 2), v24, WPP_23254a82e49430a3085a8c6bb5d92414_Traceguids, v25);
    goto LABEL_108;
  }
  v22 = CTpResponseMessage::Parse((struct CTpResponseSection ***)v71, (__int64)ppvObject, v70);
  v50 = GetTickCount() - v36;
  v55 = v22;
  if ( (v22 & 0x80000000) == 0 )
  {
    v22 = 0;
  }
  else
  {
    if ( a5 )
      (*(void (__fastcall **)(struct ITpCallbacks *, _QWORD))(*(_QWORD *)a5 + 96LL))(a5, v22);
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v24 = 29;
LABEL_56:
      v25 = v22;
      goto LABEL_15;
    }
  }
LABEL_108:
  if ( a5 )
  {
    v39 = *(void (__fastcall **)(struct ITpCallbacks *, _QWORD, _QWORD, _QWORD, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, int, int, DWORD, unsigned __int64, wchar_t *, _QWORD, unsigned int))(*(_QWORD *)a5 + 112LL);
    v40 = v97[0];
    Size = CCompoundStream::GetSize((CCompoundStream *)v115);
    *(_QWORD *)v46 = v40;
    v42 = v59;
    v43 = v50;
    v39(a5, v51, v50, v87, v88, v89, v90, v91, v92, v93, v16, v54, Size, v59, *(_QWORD *)v46, v22);
  }
  else
  {
    v43 = v50;
    v42 = v59;
  }
  if ( v72 )
    CTpLogger::LogExchange(
      v72,
      v97[0],
      v73[0],
      v42,
      v88,
      v87,
      v56,
      v51,
      v64[1],
      v65[0],
      v60,
      v89,
      v55,
      v43,
      v91,
      v96,
      v92,
      v94,
      v95,
      v90,
      v81);
  v44 = ppvObject;
  ppvObject = 0;
  if ( v44 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v44 + 16LL))(v44);
  if ( v52 )
    TpCompleteUpload((struct _WER_TP_UPLOAD_STATE *)v74);
  else
    XerTpCompleteUpload(v74);
  utl::unique_ptr<IXmlWriter,tlx::release_delete>::~unique_ptr<IXmlWriter,tlx::release_delete>(&ppvObject);
  CIStreamAdapter::~CIStreamAdapter((CIStreamAdapter *)v106);
  CMemoryByteStream::~CMemoryByteStream((CMemoryByteStream *)&v98);
  v115[0] = &CCompoundStream::`vftable';
  CMemoryByteStream::~CMemoryByteStream((CMemoryByteStream *)&v102);
  CMemoryByteStream::~CMemoryByteStream((CMemoryByteStream *)&v63);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v97);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v73);
  CTpSettings::~CTpSettings((CTpSettings *)v107);
  return v22;
}

```

## disassembly

```asm
0x18003c24c  push    rbp
0x18003c24e  push    rbx
0x18003c24f  push    rsi
0x18003c250  push    rdi
0x18003c251  push    r12
0x18003c253  push    r13
0x18003c255  push    r14
0x18003c257  push    r15
0x18003c259  lea     rbp, [rsp-368h]
0x18003c261  sub     rsp, 498h
0x18003c268  mov     [rbp+3A0h+var_378], r9
0x18003c26c  mov     [rbp+3A0h+var_370], r8
0x18003c270  mov     [rbp+3A0h+var_3D8], rdx
0x18003c274  mov     r13, rcx
0x18003c277  mov     r14, [rbp+3A0h+arg_20]
0x18003c27e  mov     rax, [rbp+3A0h+arg_38]
0x18003c285  mov     [rbp+3A0h+var_380], rax
0x18003c289  mov     rax, [rbp+3A0h+arg_40]
0x18003c290  mov     [rbp+3A0h+hHandle], rax
0x18003c294  mov     rax, [rbp+3A0h+arg_48]
0x18003c29b  mov     [rbp+3A0h+var_368], rax
0x18003c29f  mov     rax, [rbp+3A0h+arg_50]
0x18003c2a6  mov     [rbp+3A0h+var_3E0], rax
0x18003c2aa  mov     rax, [rbp+3A0h+arg_60]
0x18003c2b1  mov     [rbp+3A0h+var_388], rax
0x18003c2b5  mov     rax, [rbp+3A0h+arg_68]
0x18003c2bc  mov     [rbp+3A0h+var_3E8], rax
0x18003c2c0  lea     rcx, [rbp+3A0h+var_200]; this
0x18003c2c7  call    ??0CTpSettings@@QEAA@XZ; CTpSettings::CTpSettings(void)
0x18003c2cc  nop
0x18003c2cd  lea     rcx, [rbp+3A0h+var_360]; void *
0x18003c2d1  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18003c2d6  nop
0x18003c2d7  lea     rcx, [rbp+3A0h+var_290]; void *
0x18003c2de  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18003c2e3  nop
0x18003c2e4  xor     esi, esi
0x18003c2e6  mov     [rbp+3A0h+var_3F8], esi
0x18003c2e9  mov     [rbp+3A0h+var_3FC], esi
0x18003c2ec  mov     r12d, esi
0x18003c2ef  mov     [rbp+3A0h+var_40C], esi
0x18003c2f2  mov     [rbp+3A0h+var_410], esi
0x18003c2f5  mov     [rbp+3A0h+var_400], esi
0x18003c2f8  xorps   xmm0, xmm0
0x18003c2fb  xor     eax, eax
0x18003c2fd  movups  [rbp+3A0h+var_3D0], xmm0
0x18003c301  mov     [rbp+3A0h+var_3C0], rax
0x18003c305  mov     [rbp+3A0h+var_404], esi
0x18003c308  lea     rbx, ??_7CMemoryByteStream@@6B@; const CMemoryByteStream::`vftable'
0x18003c30f  mov     [rbp+3A0h+var_3B8], rbx
0x18003c313  movdqu  xmmword ptr [rbp+3A0h+var_3B0], xmm0
0x18003c318  mov     qword ptr [rbp+3A0h+var_3A0], rsi
0x18003c31c  mov     [rbp+3A0h+var_398], esi
0x18003c31f  mov     [rbp+3A0h+var_248], rbx
0x18003c326  movdqu  [rbp+3A0h+var_240], xmm0
0x18003c32e  mov     [rbp+3A0h+var_230], rsi
0x18003c335  mov     [rbp+3A0h+var_228], esi
0x18003c33b  lea     rax, ??_7CCompoundStream@@6B@; const CCompoundStream::`vftable'
0x18003c342  mov     [rbp+3A0h+var_150], rax
0x18003c349  mov     [rbp+3A0h+var_148], rsi
0x18003c350  xor     edx, edx; Val
0x18003c352  mov     r8d, 100h; Size
0x18003c358  lea     rcx, [rbp+3A0h+var_140]; void *
0x18003c35f  call    memset_0
0x18003c364  nop
0x18003c365  mov     [rbp+3A0h+var_270], rbx
0x18003c36c  xorps   xmm0, xmm0
0x18003c36f  movdqu  [rbp+3A0h+var_268], xmm0
0x18003c377  mov     [rbp+3A0h+var_258], rsi
0x18003c37e  mov     [rbp+3A0h+var_250], esi
0x18003c384  lea     rdx, [rbp+3A0h+var_270]; struct IWerByteStream *
0x18003c38b  lea     rcx, [rbp+3A0h+var_220]; this
0x18003c392  call    ??0CIStreamAdapter@@QEAA@PEAUIWerByteStream@@@Z; CIStreamAdapter::CIStreamAdapter(IWerByteStream *)
0x18003c397  nop
0x18003c398  mov     [rbp+3A0h+var_3F0], rsi
0x18003c39c  mov     [rbp+3A0h+ppvObject], rsi
0x18003c3a0  xor     edx, edx; Val
0x18003c3a2  mov     r8d, 0B0h; Size
0x18003c3a8  lea     rcx, [rbp+3A0h+var_340]; void *
0x18003c3ac  call    memset_0
0x18003c3b1  mov     [rbp+3A0h+var_408], 1
0x18003c3b8  mov     qword ptr [rbp+3A0h+var_3D0], r14
0x18003c3bc  mov     qword ptr [rbp+3A0h+var_3D0+8], rsi
0x18003c3c0  mov     byte ptr [rbp+3A0h+var_3C0], sil
0x18003c3c4  lea     rcx, [rbp+3A0h+var_200]; this
0x18003c3cb  call    ?Initialize@CTpSettings@@QEAAXXZ; CTpSettings::Initialize(void)
0x18003c3d0  mov     rcx, [rbp+3A0h+var_360]
0x18003c3d4  mov     [rbp+3A0h+var_358], rcx
0x18003c3d8  mov     [rcx], si
0x18003c3db  mov     rdx, [rbp+3A0h+var_198]
0x18003c3e2  test    rdx, rdx
0x18003c3e5  jz      short loc_18003C3F0
0x18003c3e7  lea     rcx, [rbp+3A0h+var_360]
0x18003c3eb  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18003c3f0  mov     eax, [rbp+3A0h+var_178]
0x18003c3f6  mov     [rbp+3A0h+var_41C], eax
0x18003c3f9  movzx   esi, [rbp+3A0h+var_16C]
0x18003c400  mov     [rbp+3A0h+var_420], si
0x18003c404  mov     r15d, [rbp+3A0h+var_170]
0x18003c40b  test    r15d, r15d
0x18003c40e  jnz     loc_18003C50A
0x18003c414  test    r14, r14
0x18003c417  jz      short loc_18003C434
0x18003c419  mov     rdi, [rbp+3A0h+var_1D8]
0x18003c420  mov     rax, [r14]
0x18003c423  mov     rcx, r14
0x18003c426  mov     rax, [rax+78h]
0x18003c42a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c42f  mov     rbx, rax
0x18003c432  jmp     short loc_18003C468
0x18003c434  mov     rax, [r13+8]
0x18003c438  cmp     rax, [r13+10h]
0x18003c43c  jnz     short loc_18003C442
0x18003c43e  xor     ebx, ebx
0x18003c440  jmp     short loc_18003C449
0x18003c442  mov     rax, [rax]
0x18003c445  mov     rbx, [rax+10h]
0x18003c449  lea     rdi, aTelemetryMicro; "telemetry.microsoft.com"
0x18003c450  lea     rdx, aWatson_0; "watson"
0x18003c457  mov     rcx, rbx; String1
0x18003c45a  call    wcscmp_0
0x18003c45f  test    eax, eax
0x18003c461  jz      short loc_18003C468
0x18003c463  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003c468  test    rbx, rbx
0x18003c46b  jnz     short loc_18003C4B0
0x18003c46d  mov     esi, 80070035h
0x18003c472  lea     rbx, WPP_GLOBAL_Control
0x18003c479  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c480  cmp     rcx, rbx
0x18003c483  jz      loc_18003CA6E
0x18003c489  test    byte ptr [rcx+1Ch], 1
0x18003c48d  jz      loc_18003CA6E
0x18003c493  mov     edx, 0Dh
0x18003c498  mov     r9d, esi
0x18003c49b  lea     r8, WPP_23254a82e49430a3085a8c6bb5d92414_Traceguids
0x18003c4a2  mov     rcx, [rcx+10h]
0x18003c4a6  call    WPP_SF_d
0x18003c4ab  jmp     loc_18003CA6E
0x18003c4b0  lea     rax, [rbp+3A0h+var_290]
0x18003c4b7  mov     [rsp+4D0h+var_4B0], rax
0x18003c4bc  mov     r9d, [r13+218h]
0x18003c4c3  mov     r8, rbx
0x18003c4c6  mov     rdx, rdi
0x18003c4c9  lea     rcx, [rbp+3A0h+var_200]
0x18003c4d0  call    ?GetFinalServerName@CTpTransport@@SAJAEBVCTpSettings@@PEB_W1HAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CTpTransport::GetFinalServerName(CTpSettings const &,wchar_t const *,wchar_t const *,int,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18003c4d5  mov     esi, eax
0x18003c4d7  test    eax, eax
0x18003c4d9  jns     short loc_18003C506
0x18003c4db  lea     rbx, WPP_GLOBAL_Control
0x18003c4e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c4e9  cmp     rcx, rbx
0x18003c4ec  jz      loc_18003CA6E
0x18003c4f2  test    byte ptr [rcx+1Ch], 1
0x18003c4f6  jz      loc_18003CA6E
0x18003c4fc  mov     edx, 0Eh
0x18003c501  mov     r9d, eax
0x18003c504  jmp     short loc_18003C49B
0x18003c506  movzx   esi, [rbp+3A0h+var_420]
0x18003c50a  test    r14, r14
0x18003c50d  jz      short loc_18003C520
0x18003c50f  mov     rax, [r14]
0x18003c512  mov     edx, r15d
0x18003c515  mov     rcx, r14
0x18003c518  mov     rax, [rax]
0x18003c51b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c520  lea     rbx, WPP_GLOBAL_Control
0x18003c527  lea     rdi, WPP_23254a82e49430a3085a8c6bb5d92414_Traceguids
0x18003c52e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c535  cmp     rcx, rbx
0x18003c538  jz      loc_18003C5D6
0x18003c53e  test    byte ptr [rcx+1Ch], 4
0x18003c542  jz      short loc_18003C563
0x18003c544  mov     edx, 0Fh
0x18003c549  mov     r9, [rbp+3A0h+var_290]
0x18003c550  mov     r8, rdi
0x18003c553  mov     rcx, [rcx+10h]
0x18003c557  call    WPP_SF_S
0x18003c55c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c563  cmp     rcx, rbx
0x18003c566  jz      short loc_18003C5D6
0x18003c568  test    byte ptr [rcx+1Ch], 4
0x18003c56c  jz      short loc_18003C58A
0x18003c56e  mov     edx, 10h
0x18003c573  mov     r9, [rbp+3A0h+var_360]
0x18003c577  mov     r8, rdi
0x18003c57a  mov     rcx, [rcx+10h]
0x18003c57e  call    WPP_SF_S
0x18003c583  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c58a  cmp     rcx, rbx
0x18003c58d  jz      short loc_18003C5D6
0x18003c58f  mov     r15d, [rbp+3A0h+var_41C]
0x18003c593  test    byte ptr [rcx+1Ch], 4
0x18003c597  jz      short loc_18003C5B4
0x18003c599  mov     edx, 11h
0x18003c59e  mov     r9d, r15d
0x18003c5a1  mov     r8, rdi
0x18003c5a4  mov     rcx, [rcx+10h]
0x18003c5a8  call    WPP_SF_d
0x18003c5ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c5b4  cmp     rcx, rbx
0x18003c5b7  jz      short loc_18003C5DA
0x18003c5b9  test    byte ptr [rcx+1Ch], 4
0x18003c5bd  jz      short loc_18003C5DA
0x18003c5bf  movzx   r9d, si
0x18003c5c3  mov     edx, 12h
0x18003c5c8  mov     r8, rdi
0x18003c5cb  mov     rcx, [rcx+10h]
0x18003c5cf  call    WPP_SF_d
0x18003c5d4  jmp     short loc_18003C5DA
0x18003c5d6  mov     r15d, [rbp+3A0h+var_41C]
0x18003c5da  lea     rax, [rbp+3A0h+var_40C]
0x18003c5de  mov     [rsp+4D0h+var_4B0], rax; unsigned int *
0x18003c5e3  lea     r9, [rbp+3A0h+var_3F8]; int *
0x18003c5e7  lea     r8, [rbp+3A0h+var_3B8]; struct CMemoryByteStream *
0x18003c5eb  mov     rdx, r14; struct ITpCallbacks *
0x18003c5ee  mov     rcx, r13; this
0x18003c5f1  call    ?BuildRequestXML@CTpTransport@@SAJPEAVCTpRequestMessage@@PEAUITpCallbacks@@AEAVCMemoryByteStream@@AEAJAEAK@Z; CTpTransport::BuildRequestXML(CTpRequestMessage *,ITpCallbacks *,CMemoryByteStream &,long &,ulong &)
0x18003c5f6  mov     esi, eax
0x18003c5f8  test    eax, eax
0x18003c5fa  jns     short loc_18003C626
0x18003c5fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c603  cmp     rcx, rbx
0x18003c606  jz      loc_18003CA6E
0x18003c60c  test    byte ptr [rcx+1Ch], 1
0x18003c610  jz      loc_18003CA6E
0x18003c616  mov     edx, 13h
0x18003c61b  mov     r9d, eax
0x18003c61e  mov     r8, rdi
0x18003c621  jmp     loc_18003C4A2
0x18003c626  mov     r13, [rbp+3A0h+hHandle]
0x18003c62a  test    r13, r13
0x18003c62d  jz      short loc_18003C653
0x18003c62f  xor     edx, edx; dwMilliseconds
0x18003c631  mov     rcx, r13; hHandle
0x18003c634  call    cs:__imp_WaitForSingleObject
0x18003c63a  test    eax, eax
0x18003c63c  jz      loc_18003C6C7
0x18003c642  cmp     eax, 102h
0x18003c647  jz      short loc_18003C653
0x18003c649  cmp     eax, 0FFFFFFFFh
0x18003c64c  jz      short loc_18003C6AC
0x18003c64e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003c653  mov     eax, [rbp+3A0h+var_3A0]
0x18003c656  mov     [rbp+3A0h+var_404], eax
0x18003c659  mov     r8d, 4; unsigned int
0x18003c65f  lea     rdx, [rbp+3A0h+var_404]; void *
0x18003c663  lea     rcx, [rbp+3A0h+var_248]; this
0x18003c66a  call    ?OpenForReadOnly@CMemoryByteStream@@QEAAXPEBXK@Z; CMemoryByteStream::OpenForReadOnly(void const *,ulong)
0x18003c66f  lea     rdx, [rbp+3A0h+var_248]; struct IWerByteStream *
0x18003c676  lea     rcx, [rbp+3A0h+var_150]; this
0x18003c67d  call    ?AppendStream@CCompoundStream@@QEAAJPEAUIWerByteStream@@@Z; CCompoundStream::AppendStream(IWerByteStream *)
0x18003c682  mov     esi, eax
0x18003c684  test    eax, eax
0x18003c686  jns     short loc_18003C6F3
0x18003c688  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c68f  cmp     rcx, rbx
0x18003c692  jz      loc_18003CA6E
0x18003c698  test    byte ptr [rcx+1Ch], 1
0x18003c69c  jz      loc_18003CA6E
0x18003c6a2  mov     edx, 15h
0x18003c6a7  jmp     loc_18003C61B
0x18003c6ac  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003c6b1  call    cs:__imp_GetLastError
0x18003c6b7  test    eax, eax
0x18003c6b9  jle     short loc_18003C6C5
0x18003c6bb  movzx   eax, ax
0x18003c6be  or      eax, 80070000h
0x18003c6c3  test    eax, eax
0x18003c6c5  jnz     short loc_18003C653
0x18003c6c7  mov     esi, 80004004h
0x18003c6cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c6d3  cmp     rcx, rbx
0x18003c6d6  jz      loc_18003CA6E
0x18003c6dc  test    byte ptr [rcx+1Ch], 1
0x18003c6e0  jz      loc_18003CA6E
0x18003c6e6  mov     edx, 14h
0x18003c6eb  mov     r9d, esi
0x18003c6ee  jmp     loc_18003C61E
0x18003c6f3  lea     rdx, [rbp+3A0h+var_3B8]; struct IWerByteStream *
0x18003c6f7  lea     rcx, [rbp+3A0h+var_150]; this
0x18003c6fe  call    ?AppendStream@CCompoundStream@@QEAAJPEAUIWerByteStream@@@Z; CCompoundStream::AppendStream(IWerByteStream *)
0x18003c703  mov     esi, eax
0x18003c705  test    eax, eax
0x18003c707  jns     short loc_18003C72D
0x18003c709  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c710  cmp     rcx, rbx
0x18003c713  jz      loc_18003CA6E
0x18003c719  test    byte ptr [rcx+1Ch], 1
0x18003c71d  jz      loc_18003CA6E
0x18003c723  mov     edx, 16h
0x18003c728  jmp     loc_18003C61B
0x18003c72d  mov     rax, [rbp+3A0h+var_3D8]
0x18003c731  test    rax, rax
0x18003c734  jz      short loc_18003C76F
0x18003c736  mov     rdx, rax; struct IWerByteStream *
0x18003c739  lea     rcx, [rbp+3A0h+var_150]; this
0x18003c740  call    ?AppendStream@CCompoundStream@@QEAAJPEAUIWerByteStream@@@Z; CCompoundStream::AppendStream(IWerByteStream *)
0x18003c745  mov     esi, eax
0x18003c747  test    eax, eax
  ... truncated ...
```
