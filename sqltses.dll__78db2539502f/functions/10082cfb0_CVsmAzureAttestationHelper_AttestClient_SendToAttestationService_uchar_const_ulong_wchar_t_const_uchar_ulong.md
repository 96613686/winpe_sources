# CVsmAzureAttestationHelper::AttestClient::SendToAttestationService(uchar const *,ulong,wchar_t const *,uchar * *,ulong *)

- ea: `0x10082cfb0`
- end: `0x10082d963`
- name: `?SendToAttestationService@AttestClient@CVsmAzureAttestationHelper@@QEAAXPEBEKPEB_WPEAPEAEPEAK@Z`
- size: `2483`
- prototype: `void __fastcall(CVsmAzureAttestationHelper::AttestClient *__hidden this, const unsigned __int8 *, unsigned int, const wchar_t *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x10082cb80`

## callees

- `0x100401170`
- `0x10045f130`
- `0x10048b440`
- `0x10082bfa0`
- `0x10082c090`
- `0x10082c180`
- `0x10082c530`
- `0x10082cad0`
- `0x10082cfb0`
- `0x10082e040`
- `0x10082e180`
- `0x10082fe90`
- `0x100831a00`
- `0x100831fc0`
- `0x100832130`
- `0x100832390`

## import_xrefs

- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10082d406`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10082d406`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10082d116`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10082d30a`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10082d116`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10082d30a`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10082d6ab`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10082d6ab`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d142`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d161`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d207`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d211`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d330`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d34c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d875`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d87f`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d8bf`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d8ed`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d910`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d91b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d925`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d142`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d161`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d207`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d211`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d330`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d34c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d875`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d87f`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d8bf`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d8ed`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d910`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d91b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082d925`
- `sqldk!SystemThread_TlsIndex` at `0x10082d3c5`
- `sqldk!SystemThread_TlsIndex` at `0x10082d41e`
- `sqldk!SystemThread_TlsOffset` at `0x10082d3ce`
- `sqldk!SystemThread_TlsOffset` at `0x10082d427`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082d3e9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082d442`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082d3e9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082d442`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082d04f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082d18d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082d240`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082d378`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082d566`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082d60b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082d65a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082d711`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082d7ea`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082d855`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082d8e2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082d04f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082d18d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082d240`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082d378`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082d566`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082d60b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082d65a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082d711`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082d7ea`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082d855`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082d8e2`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x10082d2a1`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x10082d2a1`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10082d770`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10082d770`

## string_xrefs

- `0x10082d48b`: `content-type:application/json; charset=utf-8`
- `0x10082d171`: `AddAuthToken`
- `0x10082d595`: `https://go.microsoft.com/fwlink/?linkid=2158373`
- `0x10082d102`: `Sql\Ntdbms\msql\security\inc\SecureStringBuilder.h`
- `0x10082d2f7`: `Sql\Ntdbms\msql\security\inc\SecureStringBuilder.h`
- `0x10082d69d`: `Sql\Ntdbms\storeng\jsonparser\src\JSON_Reader.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
void __fastcall CVsmAzureAttestationHelper::AttestClient::SendToAttestationService(
        CVsmAzureAttestationHelper::AttestClient *this,
        unsigned __int8 *a2,
        unsigned int a3,
        const wchar_t *a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  bool v9; // cl
  unsigned int v10; // edi
  __int64 v11; // r8
  __int64 v12; // rax
  char v13; // al
  __int64 v14; // rdi
  void *v15; // rsi
  void *v16; // rbx
  unsigned __int64 v17; // rax
  char *v18; // rdi
  struct IMemObj *v19; // r15
  int v20; // eax
  signed int v21; // esi
  wchar_t *v22; // rcx
  wchar_t *v23; // rbx
  char *v24; // rcx
  bool v25; // cl
  unsigned int v26; // edi
  char *v27; // rbx
  unsigned int v28; // eax
  char v29; // al
  unsigned __int64 v30; // r15
  void *v31; // rsi
  _BYTE *v32; // rbx
  unsigned __int64 v33; // rdi
  _BYTE *v34; // rax
  __int64 v35; // rdi
  __int64 v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rdi
  __int64 v39; // rdx
  int v40; // ebx
  void *v41; // r15
  _BYTE *v42; // rdi
  __int64 v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  int v47; // eax
  struct IMemObj *v48; // rbx
  void *v49; // rax
  __int64 v50; // rax
  void *v51; // r14
  unsigned int v52; // eax
  _WORD *v53; // rbx
  void *v54; // r9
  unsigned __int8 *v55; // rcx
  JSONParserLib::JSONNode *v56; // rsi
  __int64 v57; // r12
  __int64 v58; // r12
  int v59; // eax
  __int64 v60; // rax
  unsigned int v61; // eax
  unsigned __int8 *v62; // rax
  unsigned int v63[2]; // [rsp+28h] [rbp-D8h]
  unsigned int v64[2]; // [rsp+28h] [rbp-D8h]
  int v65; // [rsp+68h] [rbp-98h]
  struct WinHttpClient::BaseHttpClient *v66; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *v67; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v68; // [rsp+80h] [rbp-80h] BYREF
  int v69; // [rsp+84h] [rbp-7Ch] BYREF
  char *v70; // [rsp+88h] [rbp-78h] BYREF
  void *v71; // [rsp+90h] [rbp-70h]
  _BYTE *v72; // [rsp+98h] [rbp-68h]
  void *v73; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 *v74; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v75; // [rsp+B0h] [rbp-50h] BYREF
  _WORD *v76; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int8 *v77; // [rsp+C0h] [rbp-40h] BYREF
  char *v78; // [rsp+C8h] [rbp-38h]
  void *v79; // [rsp+D0h] [rbp-30h] BYREF
  JSONParserLib::JSONNode *v80; // [rsp+D8h] [rbp-28h] BYREF
  void *Source; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v82; // [rsp+E8h] [rbp-18h]
  void *v83; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v84; // [rsp+F8h] [rbp-8h]
  char v85[8]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int8 **v86; // [rsp+108h] [rbp+8h]
  unsigned int *v87; // [rsp+110h] [rbp+10h]
  void *v88; // [rsp+118h] [rbp+18h] BYREF
  void **v89; // [rsp+120h] [rbp+20h] BYREF
  struct IMemObj *v90; // [rsp+128h] [rbp+28h]
  void (__fastcall ***v91)(_QWORD, __int64); // [rsp+130h] [rbp+30h]
  __int64 v92; // [rsp+138h] [rbp+38h]
  int v93; // [rsp+140h] [rbp+40h]
  char v94; // [rsp+144h] [rbp+44h]
  int v95; // [rsp+150h] [rbp+50h] BYREF
  __int64 v96; // [rsp+158h] [rbp+58h]
  int v97; // [rsp+160h] [rbp+60h] BYREF
  int v98; // [rsp+164h] [rbp+64h]
  __int64 v99; // [rsp+168h] [rbp+68h]
  int v100; // [rsp+170h] [rbp+70h] BYREF
  __int64 v101; // [rsp+178h] [rbp+78h]
  __int64 v102; // [rsp+180h] [rbp+80h]
  __int64 v103; // [rsp+188h] [rbp+88h]
  __int64 v104; // [rsp+190h] [rbp+90h]
  bool v105; // [rsp+1A0h] [rbp+A0h]
  _QWORD v106[3]; // [rsp+1B0h] [rbp+B0h]
  char v107[8]; // [rsp+1C8h] [rbp+C8h] BYREF
  char v108[8]; // [rsp+1D0h] [rbp+D0h] BYREF
  char *String[3]; // [rsp+1D8h] [rbp+D8h]

  v106[2] = -2;
  v75 = a3;
  v86 = a5;
  v87 = a6;
  v66 = 0;
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD, struct WinHttpClient::BaseHttpClient **))(**((_QWORD **)this + 1) + 8LL))(
          *((_QWORD *)this + 1),
          *(_QWORD *)this,
          &v66) )
    ex_raise(331, 96, 16, 52, L"HttpClientNewInstance", 0);
  v71 = 0;
  if ( a4 )
  {
    v106[0] = L"Authorization: Bearer ";
    v106[1] = a4;
    Source = 0;
    v82 = 0;
    v9 = 0;
    v10 = 0;
    do
    {
      if ( v10 >= 2 )
        break;
      v11 = v106[v10];
      v12 = -1;
      do
        ++v12;
      while ( *(_WORD *)(v11 + 2 * v12) );
      v13 = SecureStringBuilder<wchar_t>::Append(&Source, *(_QWORD *)this, v11, (unsigned int)v12);
      v9 = v13 == 0;
      ++v10;
    }
    while ( v13 );
    v14 = (unsigned int)v82;
    v15 = Source;
    if ( v9 )
    {
      v71 = 0;
      v16 = 0;
    }
    else
    {
      if ( Source )
      {
        v17 = 2LL * (unsigned int)(v82 + 1);
        if ( !is_mul_ok((unsigned int)(v82 + 1), 2u) )
          v17 = -1;
        v16 = operator new[](
                v17,
                *(struct IMemObj **)this,
                1,
                "Sql\\Ntdbms\\msql\\security\\inc\\SecureStringBuilder.h",
                106,
                6u);
        if ( v16 )
        {
          memcpy_s(v16, (unsigned int)(2 * v14 + 2), v15, (unsigned int)(2 * v14 + 2));
          operator delete[](0);
        }
        else
        {
          v16 = 0;
        }
      }
      else
      {
        v16 = 0;
      }
      v71 = v16;
    }
    if ( v15 )
    {
      memset(v15, 0, 2 * v14);
      operator delete[](v15);
    }
    if ( !v16 )
      ex_raise(331, 96, 16, 57, L"AddAuthToken", 0);
  }
  v18 = 0;
  v78 = 0;
  v74 = a2;
  v19 = *(struct IMemObj **)this;
  v67 = 0;
  v20 = CBase64Utils::Base64UrlEncode(v19, &v74, &v75, &v67);
  v21 = v20;
  if ( v20 )
  {
    if ( v20 > 0 )
      v21 = (unsigned __int16)v20 | 0x80070000;
    v22 = v67;
  }
  else
  {
    v70 = 0;
    v23 = v67;
    v21 = CAzureAttestationUtils::StringFromWString(v19, v67, &v70);
    if ( v21 < 0 )
    {
      v24 = v70;
    }
    else
    {
      v18 = v70;
      v24 = 0;
      v70 = 0;
      v78 = v18;
    }
    operator delete[](v24);
    v22 = v23;
  }
  operator delete[](v22);
  if ( v21 < 0 )
  {
    _mm_lfence();
    v63[0] = v21;
    ex_raise(331, 96, 16, 66, L"Base64UrlEncodeData", *(_QWORD *)v63);
    v18 = v78;
  }
  v72 = 0;
  String[0] = "{\"data\":\"";
  String[1] = v18;
  String[2] = "\"}";
  v83 = 0;
  v84 = 0;
  v25 = 0;
  v26 = 0;
  do
  {
    if ( v26 >= 3 )
      break;
    v27 = String[v26];
    v28 = v27 ? strnlen(String[v26], 0xFA000u) : 0;
    v29 = SecureStringBuilder<char>::Append(&v83, *(_QWORD *)this, v27, v28);
    v25 = v29 == 0;
    ++v26;
  }
  while ( v29 );
  v30 = (unsigned int)v84;
  v31 = v83;
  if ( v25 )
  {
    v72 = 0;
    v32 = 0;
  }
  else
  {
    if ( v83 )
    {
      v33 = (unsigned int)(v84 + 1);
      v34 = operator new[](
              v33,
              *(struct IMemObj **)this,
              1,
              "Sql\\Ntdbms\\msql\\security\\inc\\SecureStringBuilder.h",
              106,
              6u);
      v32 = v34;
      if ( v34 )
      {
        memcpy_s(v34, v33, v31, v33);
        operator delete[](0);
      }
      else
      {
        v32 = 0;
      }
    }
    else
    {
      v32 = 0;
    }
    v72 = v32;
  }
  if ( v31 )
  {
    memset(v31, 0, v30);
    operator delete[](v31);
  }
  if ( !v32 )
    ex_raise(331, 96, 16, 71, L"AddRequestBody", 0);
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v95, 1);
  v74 = (unsigned __int8 *)&v97;
  v100 = 536872437;
  v101 = 0;
  v103 = 0;
  v102 = 0;
  v104 = 0;
  v105 = 0;
  v35 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v36 = *(_QWORD *)(v35 + 256);
  if ( !v36 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v36 = *(_QWORD *)(v35 + 256);
  }
  v37 = *(_QWORD *)(v36 + 600);
  if ( v37 )
    v105 = (unsigned int)SOS_Task::PushWait(v37, &v100) == 0;
  v38 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v39 = *(_QWORD *)(v38 + 256);
  if ( !v39 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v39 = *(_QWORD *)(v38 + 256);
  }
  v99 = v39;
  v98 = (*(_DWORD *)(v39 + 800) >> 11) & 1;
  if ( v98 || (*(_BYTE *)(v39 + 800) & 4) == 0 )
  {
    v97 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v39 + 608) + 8LL))(*(_QWORD *)(v39 + 608));
  }
  else
  {
    v97 = 0;
  }
  v40 = 0;
  v41 = v71;
  v42 = v72;
  while ( 1 )
  {
    v43 = -1;
    do
      ++v43;
    while ( v42[v43] );
    LOBYTE(v65) = 0;
    v44 = *(_QWORD *)(*(__int64 (__fastcall **)(struct WinHttpClient::BaseHttpClient *, char *, _QWORD, bool, _DWORD, const wchar_t *, const wchar_t *, _QWORD, _QWORD, const wchar_t *, void *, _BYTE *, _DWORD, int))(*(_QWORD *)v66 + 8LL))(
                       v66,
                       v107,
                       *(_QWORD *)this,
                       *((_DWORD *)this + 12) != 11,
                       *((_DWORD *)this + 11),
                       L"Microsoft.SQL.VSM.Attestation",
                       L"POST",
                       *((_QWORD *)this + 3),
                       *((_QWORD *)this + 4),
                       L"content-type:application/json; charset=utf-8",
                       v41,
                       v42,
                       v43,
                       v65);
    ++v40;
    if ( !(_DWORD)v44 )
      break;
    if ( v40 >= 3 )
    {
      v64[0] = HIDWORD(v44);
      ex_raise(331, 96, 16, 53, L"HttpConnectAndSendRequest", *(_QWORD *)v64);
      break;
    }
  }
  v45 = *(_QWORD *)(*(__int64 (__fastcall **)(struct WinHttpClient::BaseHttpClient *, char *))(*(_QWORD *)v66 + 32LL))(
                     v66,
                     v108);
  if ( (_DWORD)v45 )
    CAzureAttestationUtils::GetDetailErrorMessage(
      *(struct IMemObj **)this,
      v66,
      L"Enclave attestation failed",
      *((const void **)this + 2),
      L"https://go.microsoft.com/fwlink/?linkid=2158373",
      0x36u,
      HIDWORD(v45));
  v73 = 0;
  v46 = *(_QWORD *)(*(__int64 (__fastcall **)(struct WinHttpClient::BaseHttpClient *, void **, _QWORD, void **, char *))(*(_QWORD *)v66 + 24LL))(
                     v66,
                     &v88,
                     *(_QWORD *)this,
                     &v73,
                     v85);
  if ( (_DWORD)v46 )
  {
    v64[0] = HIDWORD(v46);
    ex_raise(331, 96, 16, 55, L"HttpResponseBody", *(_QWORD *)v64);
  }
  if ( !v73 )
  {
    ex_raise(373, 13, 16, 56, *((_QWORD *)this + 2));
    goto LABEL_106;
  }
  v79 = 0;
  v47 = CAzureAttestationUtils::WStringFromString(*(struct IMemObj **)this, v73, &v79);
  if ( v47 < 0 )
  {
    _mm_lfence();
    v64[0] = v47;
    ex_raise(331, 96, 16, 67, L"ConvertResponse", *(_QWORD *)v64);
    v41 = v71;
    v42 = v72;
  }
  v80 = 0;
  v48 = *(struct IMemObj **)this;
  v89 = &JSONParserLib::JSONReader::`vftable';
  v90 = v48;
  v92 = 0;
  v93 = 0;
  v94 = 0;
  v69 = 44;
  v49 = operator new(0x18u, v48, "Sql\\Ntdbms\\storeng\\jsonparser\\src\\JSON_Reader.cpp", 44, 6u);
  v88 = v49;
  if ( v49 )
    v50 = JSONParserLib::CStackTemplate<void *>::CStackTemplate<void *>(v49, v48);
  else
    v50 = 0;
  v91 = (void (__fastcall ***)(_QWORD, __int64))v50;
  v51 = v79;
  v52 = JSONParserLib::JSONReader::Parse((JSONParserLib::JSONReader *)&v89, *(struct IMemObj **)this, v79, &v80, 0);
  if ( v52 )
  {
    v64[0] = v52;
    ex_raise(331, 96, 16, 68, L"ResponseParse", *(_QWORD *)v64);
  }
  v53 = 0;
  v76 = 0;
  v54 = *(void **)this;
  v67 = *(wchar_t **)this;
  v55 = 0;
  v74 = 0;
  v56 = v80;
  if ( !v80 )
    goto LABEL_94;
  if ( *(_DWORD *)v80 != 1 )
    goto LABEL_94;
  v57 = *((_QWORD *)v80 + 2);
  if ( !v57 )
    goto LABEL_94;
  v58 = *(_QWORD *)(v57 + 8);
  v59 = 4;
  if ( v58 )
  {
    while ( !*(_QWORD *)v58 || _wcsicmp(*(const wchar_t **)v58, L"data") )
    {
      v58 = *(_QWORD *)(v58 + 16);
      if ( !v58 )
      {
        v59 = 4;
        v55 = v74;
        goto LABEL_87;
      }
    }
    v59 = 0;
    v55 = *(unsigned __int8 **)(v58 + 8);
LABEL_87:
    v54 = v67;
  }
  if ( v59 )
    goto LABEL_95;
  if ( !v55 )
    goto LABEL_96;
  if ( *(_DWORD *)v55 != 3 )
  {
LABEL_94:
    v59 = 2;
    goto LABEL_95;
  }
  v59 = JSONParserLib::JSONStringUtils::AllocateAndCopyString(v54, *((_QWORD *)v55 + 2), &v76);
  v53 = v76;
  if ( v59 )
  {
LABEL_95:
    v64[0] = v59;
    ex_raise(331, 96, 16, 69, L"ExtractResponse", *(_QWORD *)v64);
  }
LABEL_96:
  v77 = 0;
  v68 = 0;
  v60 = -1;
  do
    ++v60;
  while ( v53[v60] );
  v69 = 2 * v60;
  v61 = CBase64Utils::Base64UrlDecode(*(_QWORD *)this, v53, &v69, &v77, &v68);
  if ( v61 )
  {
    v64[0] = v61;
    ex_raise(331, 96, 16, 70, L"DecodeResponse", *(_QWORD *)v64);
  }
  v62 = v77;
  v77 = 0;
  *v86 = v62;
  *v87 = v68;
  operator delete[](0);
  operator delete[](v53);
  v89 = &JSONParserLib::JSONReader::`vftable';
  v90 = 0;
  if ( v91 )
    (**v91)(v91, 1);
  if ( v56 )
    JSONParserLib::JSONNode::`scalar deleting destructor'(v56, 1u);
  operator delete[](v51);
LABEL_106:
  operator delete[](v73);
  AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v97);
  *(_DWORD *)(v96 + 616) &= ~v95;
  operator delete[](v42);
  operator delete[](v78);
  operator delete[](v41);
  if ( v66 )
    (**(void (__fastcall ***)(struct WinHttpClient::BaseHttpClient *, __int64))v66)(v66, 1);
}

```

## disassembly

```asm
0x10082cfb0  push    rbp
0x10082cfb2  push    rbx
0x10082cfb3  push    rsi
0x10082cfb4  push    rdi
0x10082cfb5  push    r12
0x10082cfb7  push    r13
0x10082cfb9  push    r14
0x10082cfbb  push    r15
0x10082cfbd  lea     rbp, [rsp-108h]
0x10082cfc5  sub     rsp, 208h
0x10082cfcc  mov     [rbp+140h+var_80], 0FFFFFFFFFFFFFFFEh
0x10082cfd7  mov     rax, cs:__security_cookie
0x10082cfde  xor     rax, rsp
0x10082cfe1  mov     [rbp+140h+var_50], rax
0x10082cfe8  mov     rdi, r9
0x10082cfeb  mov     r15, rdx
0x10082cfee  mov     r13, rcx
0x10082cff1  mov     [rbp+140h+var_190], r8d
0x10082cff5  mov     rax, [rbp+140h+arg_20]
0x10082cffc  mov     [rbp+140h+var_138], rax
0x10082d000  mov     rax, [rbp+140h+arg_28]
0x10082d007  mov     [rbp+140h+var_130], rax
0x10082d00b  xor     r12d, r12d
0x10082d00e  mov     [rsp+240h+var_1D0], r12
0x10082d013  mov     rcx, [rcx+8]
0x10082d017  mov     rax, [rcx]
0x10082d01a  lea     r8, [rsp+240h+var_1D0]
0x10082d01f  mov     rdx, [r13+0]
0x10082d023  call    qword ptr [rax+8]
0x10082d026  test    al, al
0x10082d028  jnz     short loc_10082D055
0x10082d02a  mov     qword ptr [rsp+240h+var_218], r12
0x10082d02f  lea     rax, aHttpclientnewi; "HttpClientNewInstance"
0x10082d036  mov     [rsp+240h+var_220], rax
0x10082d03b  lea     edx, [r12+60h]
0x10082d040  mov     ecx, 14Bh
0x10082d045  lea     r9d, [r12+34h]
0x10082d04a  lea     r8d, [r12+10h]
0x10082d04f  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10082d055  mov     [rbp+140h+var_1B0], r12
0x10082d059  mov     r14, 0FFFFFFFFFFFFFFFFh
0x10082d060  test    rdi, rdi
0x10082d063  jz      loc_10082D193
0x10082d069  lea     rax, aAuthorizationB; "Authorization: Bearer "
0x10082d070  mov     [rbp+140h+var_90], rax
0x10082d077  mov     [rbp+140h+var_88], rdi
0x10082d07e  mov     [rbp+140h+Source], r12
0x10082d082  mov     [rbp+140h+var_158], r12
0x10082d086  xor     cl, cl
0x10082d088  mov     edi, r12d
0x10082d08b  nop     dword ptr [rax+rax+00h]
0x10082d090  cmp     edi, 2
0x10082d093  jnb     short loc_10082D0C8
0x10082d095  mov     eax, edi
0x10082d097  mov     r8, [rbp+rax*8+140h+var_90]
0x10082d09f  mov     rax, r14
0x10082d0a2  inc     rax
0x10082d0a5  cmp     word ptr [r8+rax*2], 0
0x10082d0ab  jnz     short loc_10082D0A2
0x10082d0ad  mov     r9d, eax
0x10082d0b0  mov     rdx, [r13+0]
0x10082d0b4  lea     rcx, [rbp+140h+Source]
0x10082d0b8  call    ?Append@?$SecureStringBuilder@_W@@QEAA_NPEAVIMemObj@@PEB_WK@Z; SecureStringBuilder<wchar_t>::Append(IMemObj *,wchar_t const *,ulong)
0x10082d0bd  test    al, al
0x10082d0bf  setz    cl
0x10082d0c2  inc     edi
0x10082d0c4  test    al, al
0x10082d0c6  jnz     short loc_10082D090
0x10082d0c8  mov     edi, dword ptr [rbp+140h+var_158]
0x10082d0cb  mov     rsi, [rbp+140h+Source]
0x10082d0cf  test    cl, cl
0x10082d0d1  jz      short loc_10082D0DC
0x10082d0d3  mov     [rbp+140h+var_1B0], r12
0x10082d0d7  mov     rbx, r12
0x10082d0da  jmp     short loc_10082D14C
0x10082d0dc  test    rsi, rsi
0x10082d0df  jnz     short loc_10082D0E6
0x10082d0e1  mov     rbx, r12
0x10082d0e4  jmp     short loc_10082D148
0x10082d0e6  lea     ecx, [rdi+1]
0x10082d0e9  mov     eax, 2
0x10082d0ee  mul     rcx
0x10082d0f1  cmovo   rax, r14
0x10082d0f5  mov     byte ptr [rsp+240h+var_218], 6
0x10082d0fa  mov     dword ptr [rsp+240h+var_220], 6Ah ; 'j'
0x10082d102  lea     r9, aSqlNtdbmsMsqlS_0; "Sql\\Ntdbms\\msql\\security\\inc\\Secur"...
0x10082d109  mov     r8d, 1
0x10082d10f  mov     rdx, [r13+0]
0x10082d113  mov     rcx, rax
0x10082d116  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10082d11c  mov     rbx, rax
0x10082d11f  test    rax, rax
0x10082d122  jnz     short loc_10082D129
0x10082d124  mov     rbx, r12
0x10082d127  jmp     short loc_10082D148
0x10082d129  lea     eax, ds:2[rdi*2]
0x10082d130  mov     edx, eax; DestinationSize
0x10082d132  mov     r9d, eax; SourceSize
0x10082d135  mov     r8, rsi; Source
0x10082d138  mov     rcx, rbx; Destination
0x10082d13b  call    memcpy_s
0x10082d140  xor     ecx, ecx
0x10082d142  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10082d148  mov     [rbp+140h+var_1B0], rbx
0x10082d14c  test    rsi, rsi
0x10082d14f  jz      short loc_10082D167
0x10082d151  mov     rcx, rdi
0x10082d154  add     rcx, rcx
0x10082d157  mov     rdi, rsi
0x10082d15a  xor     eax, eax
0x10082d15c  rep stosb
0x10082d15e  mov     rcx, rsi
0x10082d161  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10082d167  test    rbx, rbx
0x10082d16a  jnz     short loc_10082D193
0x10082d16c  mov     qword ptr [rsp+240h+var_218], r12
0x10082d171  lea     rax, aAddauthtoken; "AddAuthToken"
0x10082d178  mov     [rsp+240h+var_220], rax
0x10082d17d  lea     edx, [rbx+60h]
0x10082d180  mov     ecx, 14Bh
0x10082d185  lea     r9d, [rbx+39h]
0x10082d189  lea     r8d, [rbx+10h]
0x10082d18d  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10082d193  mov     rdi, r12
0x10082d196  mov     [rbp+140h+var_178], r12
0x10082d19a  mov     [rbp+140h+var_198], r15
0x10082d19e  mov     r15, [r13+0]
0x10082d1a2  mov     [rsp+240h+var_1C8], r12
0x10082d1a7  lea     r9, [rsp+240h+var_1C8]; wchar_t **
0x10082d1ac  lea     r8, [rbp+140h+var_190]; unsigned int *
0x10082d1b0  lea     rdx, [rbp+140h+var_198]; unsigned __int8 **
0x10082d1b4  mov     rcx, r15; struct IMemObj *
0x10082d1b7  call    ?Base64UrlEncode@CBase64Utils@@SAKPEAVIMemObj@@AEBQEAEAEBKPEAPEA_W@Z; CBase64Utils::Base64UrlEncode(IMemObj *,uchar * const &,ulong const &,wchar_t * *)
0x10082d1bc  mov     esi, eax
0x10082d1be  test    eax, eax
0x10082d1c0  jz      short loc_10082D1D4
0x10082d1c2  jle     short loc_10082D1CD
0x10082d1c4  movzx   esi, ax
0x10082d1c7  or      esi, 80070000h
0x10082d1cd  mov     rcx, [rsp+240h+var_1C8]
0x10082d1d2  jmp     short loc_10082D211
0x10082d1d4  mov     [rbp+140h+var_1B8], r12
0x10082d1d8  lea     r8, [rbp+140h+var_1B8]; char **
0x10082d1dc  mov     rbx, [rsp+240h+var_1C8]
0x10082d1e1  mov     rdx, rbx; wchar_t *
0x10082d1e4  mov     rcx, r15; struct IMemObj *
0x10082d1e7  call    ?StringFromWString@CAzureAttestationUtils@@SAJPEAVIMemObj@@PEB_WPEAPEAD@Z; CAzureAttestationUtils::StringFromWString(IMemObj *,wchar_t const *,char * *)
0x10082d1ec  mov     esi, eax
0x10082d1ee  test    eax, eax
0x10082d1f0  js      short loc_10082D203
0x10082d1f2  mov     rdi, [rbp+140h+var_1B8]
0x10082d1f6  mov     rcx, r12
0x10082d1f9  mov     [rbp+140h+var_1B8], rcx
0x10082d1fd  mov     [rbp+140h+var_178], rdi
0x10082d201  jmp     short loc_10082D207
0x10082d203  mov     rcx, [rbp+140h+var_1B8]
0x10082d207  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10082d20d  nop
0x10082d20e  mov     rcx, rbx
0x10082d211  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10082d217  test    esi, esi
0x10082d219  jns     short loc_10082D24A
0x10082d21b  lfence
0x10082d21e  mov     [rsp+240h+var_218], esi
0x10082d222  lea     rax, aBase64urlencod; "Base64UrlEncodeData"
0x10082d229  mov     [rsp+240h+var_220], rax
0x10082d22e  mov     edx, 60h ; '`'
0x10082d233  mov     ecx, 14Bh
0x10082d238  lea     r9d, [rdx-1Eh]
0x10082d23c  lea     r8d, [rdx-50h]
0x10082d240  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10082d246  mov     rdi, [rbp+140h+var_178]
0x10082d24a  mov     [rbp+140h+var_1A8], r12
0x10082d24e  lea     rax, aData_1; "{\"data\":\""
0x10082d255  mov     [rbp+140h+String], rax
0x10082d25c  mov     [rbp+140h+var_60], rdi
0x10082d263  lea     rax, asc_1008A1E5C; "\"}"
0x10082d26a  mov     [rbp+140h+var_58], rax
0x10082d271  mov     [rbp+140h+var_150], r12
0x10082d275  mov     [rbp+140h+var_148], r12
0x10082d279  xor     cl, cl
0x10082d27b  mov     edi, r12d
0x10082d27e  xchg    ax, ax
0x10082d280  cmp     edi, 3
0x10082d283  jnb     short loc_10082D2C5
0x10082d285  mov     eax, edi
0x10082d287  mov     rbx, [rbp+rax*8+140h+String]
0x10082d28f  test    rbx, rbx
0x10082d292  jnz     short loc_10082D299
0x10082d294  mov     rax, r12
0x10082d297  jmp     short loc_10082D2A7
0x10082d299  mov     edx, 0FA000h; MaxCount
0x10082d29e  mov     rcx, rbx; String
0x10082d2a1  call    cs:__imp_strnlen
0x10082d2a7  mov     r9d, eax
0x10082d2aa  mov     r8, rbx
0x10082d2ad  mov     rdx, [r13+0]
0x10082d2b1  lea     rcx, [rbp+140h+var_150]
0x10082d2b5  call    ?Append@?$SecureStringBuilder@D@@QEAA_NPEAVIMemObj@@PEBDK@Z; SecureStringBuilder<char>::Append(IMemObj *,char const *,ulong)
0x10082d2ba  test    al, al
0x10082d2bc  setz    cl
0x10082d2bf  inc     edi
0x10082d2c1  test    al, al
0x10082d2c3  jnz     short loc_10082D280
0x10082d2c5  mov     r15d, dword ptr [rbp+140h+var_148]
0x10082d2c9  mov     rsi, [rbp+140h+var_150]
0x10082d2cd  test    cl, cl
0x10082d2cf  jz      short loc_10082D2DA
0x10082d2d1  mov     [rbp+140h+var_1A8], r12
0x10082d2d5  mov     rbx, r12
0x10082d2d8  jmp     short loc_10082D33A
0x10082d2da  test    rsi, rsi
0x10082d2dd  jnz     short loc_10082D2E4
0x10082d2df  mov     rbx, r12
0x10082d2e2  jmp     short loc_10082D336
0x10082d2e4  lea     eax, [r15+1]
0x10082d2e8  mov     edi, eax
0x10082d2ea  mov     byte ptr [rsp+240h+var_218], 6
0x10082d2ef  mov     dword ptr [rsp+240h+var_220], 6Ah ; 'j'
0x10082d2f7  lea     r9, aSqlNtdbmsMsqlS_0; "Sql\\Ntdbms\\msql\\security\\inc\\Secur"...
0x10082d2fe  mov     r8d, 1
0x10082d304  mov     rdx, [r13+0]
0x10082d308  mov     ecx, eax
0x10082d30a  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10082d310  mov     rbx, rax
0x10082d313  test    rax, rax
0x10082d316  jnz     short loc_10082D31D
0x10082d318  mov     rbx, r12
0x10082d31b  jmp     short loc_10082D336
0x10082d31d  mov     r9, rdi; SourceSize
0x10082d320  mov     r8, rsi; Source
0x10082d323  mov     rdx, rdi; DestinationSize
0x10082d326  mov     rcx, rax; Destination
0x10082d329  call    memcpy_s
0x10082d32e  xor     ecx, ecx
0x10082d330  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10082d336  mov     [rbp+140h+var_1A8], rbx
0x10082d33a  test    rsi, rsi
0x10082d33d  jz      short loc_10082D352
0x10082d33f  mov     rcx, r15
0x10082d342  mov     rdi, rsi
0x10082d345  xor     eax, eax
0x10082d347  rep stosb
0x10082d349  mov     rcx, rsi
0x10082d34c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10082d352  test    rbx, rbx
0x10082d355  jnz     short loc_10082D37E
0x10082d357  mov     qword ptr [rsp+240h+var_218], r12
0x10082d35c  lea     rax, aAddrequestbody; "AddRequestBody"
0x10082d363  mov     [rsp+240h+var_220], rax
0x10082d368  lea     edx, [rbx+60h]
0x10082d36b  mov     ecx, 14Bh
0x10082d370  lea     r9d, [rbx+47h]
0x10082d374  lea     r8d, [rbx+10h]
0x10082d378  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10082d37e  mov     edx, 1
0x10082d383  lea     rcx, [rbp+140h+var_F0]
0x10082d387  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x10082d38c  nop
0x10082d38d  lea     rax, [rbp+140h+var_E0]
0x10082d391  mov     [rbp+140h+var_198], rax
0x10082d395  mov     [rbp+140h+var_D0], 200005F5h
0x10082d39c  mov     [rbp+140h+var_C8], r12
0x10082d3a0  mov     [rbp+140h+var_B8], r12
0x10082d3a7  mov     [rbp+140h+var_C0], r12
0x10082d3ae  mov     [rbp+140h+var_B0], r12
0x10082d3b5  mov     [rbp+140h+var_A0], 0
0x10082d3bc  mov     rdx, gs:58h
0x10082d3c5  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10082d3cc  mov     ecx, [rax]
0x10082d3ce  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10082d3d5  mov     edi, [rax]
0x10082d3d7  add     rdi, [rdx+rcx*8]
0x10082d3db  mov     rax, [rdi+100h]
0x10082d3e2  test    rax, rax
0x10082d3e5  jnz     short loc_10082D3F6
0x10082d3e7  xor     ecx, ecx
0x10082d3e9  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10082d3ef  mov     rax, [rdi+100h]
0x10082d3f6  mov     rcx, [rax+258h]
0x10082d3fd  test    rcx, rcx
0x10082d400  jz      short loc_10082D415
0x10082d402  lea     rdx, [rbp+140h+var_D0]
0x10082d406  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x10082d40c  test    eax, eax
0x10082d40e  setz    [rbp+140h+var_A0]
0x10082d415  mov     rdx, gs:58h
0x10082d41e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10082d425  mov     ecx, [rax]
0x10082d427  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10082d42e  mov     edi, [rax]
0x10082d430  add     rdi, [rdx+rcx*8]
0x10082d434  mov     rdx, [rdi+100h]
0x10082d43b  test    rdx, rdx
0x10082d43e  jnz     short loc_10082D44F
0x10082d440  xor     ecx, ecx
0x10082d442  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10082d448  mov     rdx, [rdi+100h]
0x10082d44f  mov     [rbp+140h+var_D8], rdx
0x10082d453  mov     eax, [rdx+320h]
  ... truncated ...
```
