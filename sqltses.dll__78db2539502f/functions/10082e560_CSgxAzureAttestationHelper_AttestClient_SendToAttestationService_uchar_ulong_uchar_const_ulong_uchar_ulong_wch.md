# CSgxAzureAttestationHelper::AttestClient::SendToAttestationService(uchar *,ulong,uchar const *,ulong,uchar *,ulong,wchar_t const *,uchar * *,ulong *)

- ea: `0x10082e560`
- end: `0x10082f306`
- name: `?SendToAttestationService@AttestClient@CSgxAzureAttestationHelper@@QEAAXPEAEKPEBEK0KPEB_WPEAPEAEPEAK@Z`
- size: `3494`
- prototype: `void __fastcall(CSgxAzureAttestationHelper::AttestClient *__hidden this, unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, const wchar_t *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x10082e2c0`

## callees

- `0x100401170`
- `0x10045f130`
- `0x10048b440`
- `0x10082bd70`
- `0x10082bfa0`
- `0x10082c090`
- `0x10082c180`
- `0x10082c530`
- `0x10082cad0`
- `0x10082e040`
- `0x10082e180`
- `0x10082e560`
- `0x10082fe90`
- `0x100831a00`
- `0x100831fc0`
- `0x100832130`

## import_xrefs

- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10082ecd6`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10082ecd6`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10082e789`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10082eabb`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10082ebc1`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10082e789`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10082eabb`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10082ebc1`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10082f00e`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10082f00e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082e7b5`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082e7d4`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082e87f`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082e889`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082e97d`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082e987`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082eae1`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082ebe7`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082ec04`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f201`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f20c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f24c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f27b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f2a1`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f2ac`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f2b7`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f2c1`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082e7b5`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082e7d4`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082e87f`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082e889`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082e97d`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082e987`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082eae1`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082ebe7`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082ec04`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f201`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f20c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f24c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f27b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f2a1`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f2ac`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f2b7`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082f2c1`
- `sqldk!SystemThread_TlsIndex` at `0x10082ec92`
- `sqldk!SystemThread_TlsIndex` at `0x10082ecee`
- `sqldk!SystemThread_TlsOffset` at `0x10082ec9b`
- `sqldk!SystemThread_TlsOffset` at `0x10082ecf7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082ecb6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082ed12`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082ecb6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082ed12`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082e63b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082e67a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082e6c7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082e80c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082e8c4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082e9c4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082ec3c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082ee6b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082ee95`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082ef45`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082efbc`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082f079`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082f16d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082f1e0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082f270`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082e63b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082e67a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082e6c7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082e80c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082e8c4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082e9c4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082ec3c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082ee6b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082ee95`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082ef45`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082efbc`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082f079`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082f16d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082f1e0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082f270`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x10082ea51`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x10082eb57`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x10082ea51`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x10082eb57`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10082f0d3`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10082f0d3`

## string_xrefs

- `0x10082e7e4`: `AddAuthToken`
- `0x10082eecd`: `https://go.microsoft.com/fwlink/?linkid=2158373`
- `0x10082e775`: `Sql\Ntdbms\msql\security\inc\SecureStringBuilder.h`
- `0x10082eaa8`: `Sql\Ntdbms\msql\security\inc\SecureStringBuilder.h`
- `0x10082ebae`: `Sql\Ntdbms\msql\security\inc\SecureStringBuilder.h`
- `0x10082ed67`: `Content-Type: application/json; charset=utf-8`
- `0x10082f0cc`: `token`
- `0x10082f14b`: `ConvertResponseToken`
- `0x10082f000`: `Sql\Ntdbms\storeng\jsonparser\src\JSON_Reader.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
void __fastcall CSgxAzureAttestationHelper::AttestClient::SendToAttestationService(
        CSgxAzureAttestationHelper::AttestClient *this,
        unsigned __int8 *a2,
        unsigned int a3,
        const unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7,
        const wchar_t *a8,
        unsigned __int8 **a9,
        unsigned int *a10)
{
  const wchar_t *v12; // rdi
  _DWORD *v13; // rbx
  int v14; // eax
  bool v15; // cl
  unsigned int v16; // edi
  __int64 v17; // r8
  __int64 v18; // rax
  char v19; // al
  __int64 v20; // rdi
  void *v21; // rsi
  void *v22; // rbx
  unsigned __int64 v23; // rax
  char *v24; // rbx
  struct IMemObj *v25; // r14
  int v26; // eax
  signed int v27; // esi
  wchar_t *v28; // rcx
  wchar_t *v29; // rdi
  char *v30; // rcx
  unsigned int v31; // r8d
  unsigned int v32; // r9d
  unsigned __int8 *v33; // rdi
  char *v34; // rdi
  struct IMemObj *v35; // r15
  int v36; // eax
  signed int v37; // r14d
  wchar_t *v38; // rcx
  wchar_t *v39; // rsi
  char *v40; // rcx
  bool v41; // cl
  unsigned int v42; // edi
  char *v43; // rbx
  unsigned int v44; // eax
  char v45; // al
  unsigned __int64 v46; // r14
  void *v47; // rsi
  void *v48; // rbx
  unsigned __int64 v49; // rdi
  void *v50; // rax
  bool v51; // cl
  unsigned int v52; // edi
  char *v53; // rbx
  unsigned int v54; // eax
  char v55; // al
  unsigned __int64 v56; // rdi
  void *v57; // rax
  __int64 v58; // rdi
  __int64 v59; // rax
  __int64 v60; // rcx
  __int64 v61; // rdi
  __int64 v62; // rdx
  int v63; // ebx
  void *v64; // r14
  void *v65; // rdi
  __int64 v66; // rax
  unsigned __int8 *v67; // rcx
  __int64 v68; // rcx
  __int64 v69; // rcx
  unsigned __int8 *v70; // rax
  int v71; // eax
  struct IMemObj *v72; // rbx
  void *v73; // rax
  __int64 v74; // rax
  void *v75; // rsi
  int v76; // eax
  void *v77; // rcx
  unsigned __int8 *v78; // rax
  JSONParserLib::JSONNode *v79; // rbx
  __int64 v80; // r15
  __int64 v81; // r15
  int v82; // r13d
  int v83; // eax
  char *v84; // rax
  __int64 v85; // rcx
  bool *v86; // [rsp+30h] [rbp-D0h]
  bool *v87; // [rsp+30h] [rbp-D0h]
  int v88; // [rsp+68h] [rbp-98h]
  void *v89; // [rsp+70h] [rbp-90h]
  struct WinHttpClient::BaseHttpClient *v90; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 *v91; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v92; // [rsp+88h] [rbp-78h] BYREF
  void *v93; // [rsp+90h] [rbp-70h]
  void *v94; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int8 *v95; // [rsp+A0h] [rbp-60h] BYREF
  char *v96; // [rsp+A8h] [rbp-58h] BYREF
  char *v97; // [rsp+B0h] [rbp-50h] BYREF
  char *v98; // [rsp+B8h] [rbp-48h]
  unsigned int v99; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t *v100; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t *v101; // [rsp+D0h] [rbp-30h] BYREF
  void *v102; // [rsp+D8h] [rbp-28h] BYREF
  JSONParserLib::JSONNode *v103; // [rsp+E0h] [rbp-20h] BYREF
  char *v104; // [rsp+E8h] [rbp-18h] BYREF
  wchar_t *v105; // [rsp+F0h] [rbp-10h] BYREF
  char *v106; // [rsp+F8h] [rbp-8h]
  unsigned int *v107; // [rsp+100h] [rbp+0h]
  unsigned __int8 **v108; // [rsp+108h] [rbp+8h]
  void *Source; // [rsp+110h] [rbp+10h] BYREF
  __int64 v110; // [rsp+118h] [rbp+18h]
  void *v111; // [rsp+120h] [rbp+20h] BYREF
  __int64 v112; // [rsp+128h] [rbp+28h]
  void *v113; // [rsp+130h] [rbp+30h] BYREF
  __int64 v114; // [rsp+138h] [rbp+38h]
  void *v115; // [rsp+140h] [rbp+40h] BYREF
  void **v116; // [rsp+148h] [rbp+48h] BYREF
  struct IMemObj *v117; // [rsp+150h] [rbp+50h]
  void (__fastcall ***v118)(_QWORD, __int64); // [rsp+158h] [rbp+58h]
  __int64 v119; // [rsp+160h] [rbp+60h]
  int v120; // [rsp+168h] [rbp+68h]
  char v121; // [rsp+16Ch] [rbp+6Ch]
  int v122; // [rsp+170h] [rbp+70h] BYREF
  __int64 v123; // [rsp+178h] [rbp+78h]
  int v124; // [rsp+180h] [rbp+80h] BYREF
  int v125; // [rsp+184h] [rbp+84h]
  __int64 v126; // [rsp+188h] [rbp+88h]
  int v127; // [rsp+190h] [rbp+90h] BYREF
  __int64 v128; // [rsp+198h] [rbp+98h]
  __int64 v129; // [rsp+1A0h] [rbp+A0h]
  __int64 v130; // [rsp+1A8h] [rbp+A8h]
  __int64 v131; // [rsp+1B0h] [rbp+B0h]
  bool v132; // [rsp+1C0h] [rbp+C0h]
  _QWORD v133[3]; // [rsp+1D0h] [rbp+D0h]
  _BYTE v134[8]; // [rsp+1E8h] [rbp+E8h] BYREF
  _BYTE v135[8]; // [rsp+1F0h] [rbp+F0h] BYREF
  char *String[5]; // [rsp+1F8h] [rbp+F8h]
  char *v137[5]; // [rsp+220h] [rbp+120h]

  v133[2] = -2;
  v91 = a2;
  v92 = a3;
  v95 = a6;
  v12 = a8;
  v108 = a9;
  v107 = a10;
  v13 = (_DWORD *)((char *)this + 48);
  v14 = CAzureAttestationUtils::CrackUri(
          *(struct IMemObj **)this,
          *((const void **)this + 2),
          (void **)this + 3,
          (void **)this + 4,
          (unsigned int *)this + 11,
          (unsigned int *)this + 12,
          (bool *)this + 40);
  if ( v14 < 0 )
  {
    _mm_lfence();
    LODWORD(v86) = v14;
    ex_raise(373, 10, 16, 50, L"Enclave attestation failed", *((_QWORD *)this + 2), v86);
  }
  if ( *v13 != 11 && *v13 != 2 )
    ex_raise(373, 11, 16, 66, L"Enclave attestation failed", *((_QWORD *)this + 2), L"http(s)");
  v90 = 0;
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD, struct WinHttpClient::BaseHttpClient **))(**((_QWORD **)this + 1) + 8LL))(
          *((_QWORD *)this + 1),
          *(_QWORD *)this,
          &v90) )
    ex_raise(373, 2, 16, 51, L"Enclave attestation failed", L"HttpClientNewInstance", 0);
  v93 = 0;
  if ( v12 )
  {
    v133[0] = L"Authorization: Bearer ";
    v133[1] = v12;
    Source = 0;
    v110 = 0;
    v15 = 0;
    v16 = 0;
    do
    {
      if ( v16 >= 2 )
        break;
      v17 = v133[v16];
      v18 = -1;
      do
        ++v18;
      while ( *(_WORD *)(v17 + 2 * v18) );
      v19 = SecureStringBuilder<wchar_t>::Append(&Source, *(_QWORD *)this, v17, (unsigned int)v18);
      v15 = v19 == 0;
      ++v16;
    }
    while ( v19 );
    v20 = (unsigned int)v110;
    v21 = Source;
    if ( v15 )
    {
      v93 = 0;
      v22 = 0;
    }
    else
    {
      if ( Source )
      {
        v23 = 2LL * (unsigned int)(v110 + 1);
        if ( !is_mul_ok((unsigned int)(v110 + 1), 2u) )
          v23 = -1;
        v22 = operator new[](
                v23,
                *(struct IMemObj **)this,
                1,
                "Sql\\Ntdbms\\msql\\security\\inc\\SecureStringBuilder.h",
                106,
                6u);
        if ( v22 )
        {
          memcpy_s(v22, (unsigned int)(2 * v20 + 2), v21, (unsigned int)(2 * v20 + 2));
          operator delete[](0);
        }
        else
        {
          v22 = 0;
        }
      }
      else
      {
        v22 = 0;
      }
      v93 = v22;
    }
    if ( v21 )
    {
      memset(v21, 0, 2 * v20);
      operator delete[](v21);
    }
    if ( !v22 )
      ex_raise(373, 2, 16, 52, L"Enclave attestation failed", L"AddAuthToken", 0);
  }
  v24 = 0;
  v98 = 0;
  v25 = *(struct IMemObj **)this;
  v100 = 0;
  v26 = CBase64Utils::Base64UrlEncode(v25, &v91, &v92, &v100);
  v27 = v26;
  if ( v26 )
  {
    if ( v26 > 0 )
      v27 = (unsigned __int16)v26 | 0x80070000;
    v28 = v100;
  }
  else
  {
    v96 = 0;
    v29 = v100;
    v27 = CAzureAttestationUtils::StringFromWString(v25, v100, &v96);
    if ( v27 < 0 )
    {
      v30 = v96;
    }
    else
    {
      v24 = v96;
      v30 = 0;
      v96 = 0;
      v98 = v24;
    }
    operator delete[](v30);
    v28 = v29;
  }
  operator delete[](v28);
  if ( v27 < 0 )
  {
    _mm_lfence();
    LODWORD(v86) = v27;
    ex_raise(373, 2, 16, 53, L"Enclave attestation failed", L"ParseQuote", v86);
    v24 = v98;
  }
  v31 = 0;
  v32 = a7;
  if ( a7 )
  {
    v33 = v95;
    do
    {
      *v33 ^= a4[v31 % a5];
      ++v31;
      ++v33;
    }
    while ( v31 < v32 );
  }
  v34 = 0;
  v106 = 0;
  v35 = *(struct IMemObj **)this;
  v101 = 0;
  v36 = CBase64Utils::Base64UrlEncode(v35, &v95, &a7, &v101);
  v37 = v36;
  if ( v36 )
  {
    if ( v36 > 0 )
      v37 = (unsigned __int16)v36 | 0x80070000;
    v38 = v101;
  }
  else
  {
    v97 = 0;
    v39 = v101;
    v37 = CAzureAttestationUtils::StringFromWString(v35, v101, &v97);
    if ( v37 < 0 )
    {
      v40 = v97;
    }
    else
    {
      v34 = v97;
      v40 = 0;
      v97 = 0;
      v106 = v34;
    }
    operator delete[](v40);
    v38 = v39;
  }
  operator delete[](v38);
  if ( v37 < 0 )
  {
    _mm_lfence();
    LODWORD(v86) = v37;
    ex_raise(373, 2, 16, 54, L"Enclave attestation failed", L"ParseEnclaveHeldData", v86);
    v24 = v98;
    v34 = v106;
  }
  if ( *((_BYTE *)this + 40) )
  {
    String[0] = "{\"EnclaveHeldData\":\"";
    String[1] = v34;
    String[2] = "\",\"Quote\":\"";
    String[3] = v24;
    String[4] = "\"}";
    v111 = 0;
    v112 = 0;
    v41 = 0;
    v42 = 0;
    do
    {
      if ( v42 >= 5 )
        break;
      v43 = String[v42];
      v44 = v43 ? strnlen(String[v42], 0xFA000u) : 0;
      v45 = SecureStringBuilder<char>::Append(&v111, *(_QWORD *)this, v43, v44);
      v41 = v45 == 0;
      ++v42;
    }
    while ( v45 );
    v46 = (unsigned int)v112;
    v47 = v111;
    if ( v41 )
    {
      v89 = 0;
      v48 = 0;
    }
    else
    {
      if ( v111 )
      {
        v49 = (unsigned int)(v112 + 1);
        v50 = operator new[](
                v49,
                *(struct IMemObj **)this,
                1,
                "Sql\\Ntdbms\\msql\\security\\inc\\SecureStringBuilder.h",
                106,
                6u);
        v48 = v50;
        if ( v50 )
        {
          memcpy_s(v50, v49, v47, v49);
          operator delete[](0);
        }
        else
        {
          v48 = 0;
        }
      }
      else
      {
        v48 = 0;
      }
      v89 = v48;
    }
  }
  else
  {
    v137[0] = "{\"RuntimeData\":{ \"DataType\":\"Binary\", \"Data\":\"";
    v137[1] = v34;
    v137[2] = "\"},\"Quote\":\"";
    v137[3] = v24;
    v137[4] = "\"}";
    v113 = 0;
    v114 = 0;
    v51 = 0;
    v52 = 0;
    do
    {
      if ( v52 >= 5 )
        break;
      v53 = v137[v52];
      v54 = v53 ? strnlen(v137[v52], 0xFA000u) : 0;
      v55 = SecureStringBuilder<char>::Append(&v113, *(_QWORD *)this, v53, v54);
      v51 = v55 == 0;
      ++v52;
    }
    while ( v55 );
    v46 = (unsigned int)v114;
    v47 = v113;
    if ( v51 )
    {
      v89 = 0;
      v48 = 0;
    }
    else
    {
      if ( v113 )
      {
        v56 = (unsigned int)(v114 + 1);
        v57 = operator new[](
                v56,
                *(struct IMemObj **)this,
                1,
                "Sql\\Ntdbms\\msql\\security\\inc\\SecureStringBuilder.h",
                106,
                6u);
        v48 = v57;
        if ( v57 )
        {
          memcpy_s(v57, v56, v47, v56);
          operator delete[](0);
        }
        else
        {
          v48 = 0;
        }
      }
      else
      {
        v48 = 0;
      }
      v89 = v48;
    }
  }
  if ( v47 )
  {
    memset(v47, 0, v46);
    operator delete[](v47);
  }
  if ( !v48 )
    ex_raise(373, 2, 16, 55, L"Enclave attestation failed", L"AddRequestBody", 0);
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v122, 1);
  v91 = (unsigned __int8 *)&v124;
  v127 = 536872438;
  v128 = 0;
  v130 = 0;
  v129 = 0;
  v131 = 0;
  v132 = 0;
  v58 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v59 = *(_QWORD *)(v58 + 256);
  if ( !v59 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v59 = *(_QWORD *)(v58 + 256);
  }
  v60 = *(_QWORD *)(v59 + 600);
  if ( v60 )
    v132 = (unsigned int)SOS_Task::PushWait(v60, &v127) == 0;
  v61 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v62 = *(_QWORD *)(v61 + 256);
  if ( !v62 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v62 = *(_QWORD *)(v61 + 256);
  }
  v126 = v62;
  v125 = (*(_DWORD *)(v62 + 800) >> 11) & 1;
  if ( v125 || (*(_BYTE *)(v62 + 800) & 4) == 0 )
  {
    v124 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v62 + 608) + 8LL))(*(_QWORD *)(v62 + 608));
  }
  else
  {
    v124 = 0;
  }
  v63 = 0;
  v64 = v93;
  v65 = v89;
  while ( 1 )
  {
    v66 = -1;
    do
      ++v66;
    while ( *((_BYTE *)v89 + v66) );
    LOBYTE(v88) = 1;
    v67 = *(unsigned __int8 **)(*(__int64 (__fastcall **)(struct WinHttpClient::BaseHttpClient *, _BYTE *, _QWORD, bool, _DWORD, const wchar_t *, const wchar_t *, _QWORD, _QWORD, const wchar_t *, void *, void *, _DWORD, int))(*(_QWORD *)v90 + 8LL))(
                                 v90,
                                 v134,
                                 *(_QWORD *)this,
                                 *((_DWORD *)this + 12) != 11,
                                 *((_DWORD *)this + 11),
                                 L"Microsoft.SQL.SGX.Attestation",
                                 L"POST",
                                 *((_QWORD *)this + 3),
                                 *((_QWORD *)this + 4),
                                 L"Content-Type: application/json; charset=utf-8",
                                 v64,
                                 v89,
                                 v66,
                                 v88);
    v91 = v67;
    ++v63;
    if ( !(_DWORD)v67 )
      break;
    if ( v63 >= 3 )
    {
      if ( HIDWORD(v67) == 12007 )
      {
        LODWORD(v87) = HIDWORD(v67);
        ex_raise(374, 33, 16, 56, L"Enclave attestation failed", *((_QWORD *)this + 2), v87);
      }
      else
      {
        LODWORD(v87) = HIDWORD(v91);
        ex_raise(373, 2, 16, 56, L"Enclave attestation failed", L"HttpConnectAndSendRequest", v87);
      }
      break;
    }
  }
  v68 = *(_QWORD *)(*(__int64 (__fastcall **)(struct WinHttpClient::BaseHttpClient *, _BYTE *))(*(_QWORD *)v90 + 32LL))(
                     v90,
                     v135);
  if ( (_DWORD)v68 )
    CAzureAttestationUtils::GetDetailErrorMessage(
      *(struct IMemObj **)this,
      v90,
      *((const void **)this + 2),
      L"Enclave attestation failed",
      L"https://go.microsoft.com/fwlink/?linkid=2158373",
      0x39u,
      HIDWORD(v68));
  v94 = 0;
  v69 = *(_QWORD *)(*(__int64 (__fastcall **)(struct WinHttpClient::BaseHttpClient *, void **, _QWORD, void **, unsigned int *))(*(_QWORD *)v90 + 24LL))(
                     v90,
                     &v115,
                     *(_QWORD *)this,
                     &v94,
                     &v99);
  if ( (_DWORD)v69 )
  {
    LODWORD(v87) = HIDWORD(v69);
    ex_raise(373, 2, 16, 58, L"Enclave attestation failed", L"HttpResponseBody", v87);
  }
  v70 = (unsigned __int8 *)v94;
  if ( !v94 )
  {
    ex_raise(373, 13, 16, 60, *((_QWORD *)this + 2));
    goto LABEL_145;
  }
  if ( *((_BYTE *)this + 40) )
  {
    v94 = 0;
    *v108 = v70;
    *v107 = v99;
    goto LABEL_145;
  }
  v102 = 0;
  v71 = CAzureAttestationUtils::WStringFromString(*(struct IMemObj **)this, v94, &v102);
  if ( v71 < 0 )
  {
    _mm_lfence();
    LODWORD(v87) = v71;
    ex_raise(373, 2, 16, 68, L"Enclave attestation failed", L"ConvertResponse", v87);
    v64 = v93;
    v65 = v89;
  }
  v103 = 0;
  v72 = *(struct IMemObj **)this;
  v116 = &JSONParserLib::JSONReader::`vftable';
  v117 = v72;
  v119 = 0;
  v120 = 0;
  v121 = 0;
  v92 = 44;
  v73 = operator new(0x18u, v72, "Sql\\Ntdbms\\storeng\\jsonparser\\src\\JSON_Reader.cpp", 44, 6u);
  v115 = v73;
  if ( v73 )
    v74 = JSONParserLib::CStackTemplate<void *>::CStackTemplate<void *>(v73, v72);
  else
    v74 = 0;
  v118 = (void (__fastcall ***)(_QWORD, __int64))v74;
  v75 = v102;
  v76 = JSONParserLib::JSONReader::Parse((JSONParserLib::JSONReader *)&v116, *(struct IMemObj **)this, v102, &v103, 0);
  if ( v76 )
  {
    LODWORD(v87) = v76;
    ex_raise(373, 2, 16, 69, L"Enclave attestation failed", L"ResponseParse", v87);
  }
  v105 = 0;
  v77 = *(void **)this;
  v95 = *(unsigned __int8 **)this;
  v78 = 0;
  v91 = 0;
  v79 = v103;
  if ( !v103 )
    goto LABEL_136;
  if ( *(_DWORD *)v103 != 1 )
    goto LABEL_136;
  v80 = *((_QWORD *)v103 + 2);
  if ( !v80 )
    goto LABEL_136;
  v81 = *(_QWORD *)(v80 + 8);
  v82 = 4;
  if ( v81 )
  {
    while ( !*(_QWORD *)v81 || _wcsicmp(*(const wchar_t **)v81, L"token") )
    {
      v81 = *(_QWORD *)(v81 + 16);
      if ( !v81 )
      {
        v78 = v91;
        goto LABEL_124;
      }
    }
    v82 = 0;
    v78 = *(unsigned __int8 **)(v81 + 8);
LABEL_124:
    v77 = v95;
  }
  if ( v82 )
    goto LABEL_137;
  if ( v78 )
  {
    if ( *(_DWORD *)v78 == 3 )
    {
      v82 = JSONParserLib::JSONStringUtils::AllocateAndCopyString(v77, *((_QWORD *)v78 + 2), &v105);
      if ( !v82 )
        goto LABEL_129;
LABEL_137:
      LODWORD(v87) = v82;
      ex_raise(373, 2, 16, 70, L"Enclave attestation failed", L"ExtractResponse", v87);
      goto LABEL_129;
    }
LABEL_136:
    v82 = 2;
    goto LABEL_137;
  }
LABEL_129:
  v104 = 0;
  v83 = CAzureAttestationUtils::StringFromWString(*(struct IMemObj **)this, v105, &v104);
  if ( v83 < 0 )
  {
    _mm_lfence();
    LODWORD(v87) = v83;
    ex_raise(373, 2, 16, 71, L"Enclave attestation failed", L"ConvertResponseToken", v87);
    v64 = v93;
    v65 = v89;
    v75 = v102;
    v79 = v103;
  }
  v84 = v104;
  if ( v104 )
  {
    v85 = -1;
    do
      ++v85;
    while ( v104[v85] );
  }
  else
  {
    LODWORD(v85) = 0;
  }
  *v107 = v85;
  v104 = 0;
  *v108 = (unsigned __int8 *)v84;
  operator delete[](0);
  operator delete[](v105);
  v116 = &JSONParserLib::JSONReader::`vftable';
  v117 = 0;
  if ( v118 )
    (**v118)(v118, 1);
  if ( v79 )
    JSONParserLib::JSONNode::`scalar deleting destructor'(v79, 1u);
  operator delete[](v75);
LABEL_145:
  operator delete[](v94);
  AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v124);
  *(_DWORD *)(v123 + 616) &= ~v122;
  operator delete[](v65);
  operator delete[](v106);
  operator delete[](v98);
  operator delete[](v64);
  if ( v90 )
    (**(void (__fastcall ***)(struct WinHttpClient::BaseHttpClient *, __int64))v90)(v90, 1);
}

```

## disassembly

```asm
0x10082e560  push    rbp
0x10082e562  push    rsi
0x10082e563  push    rdi
0x10082e564  push    r12
0x10082e566  push    r13
0x10082e568  push    r14
0x10082e56a  push    r15
0x10082e56c  lea     rbp, [rsp-150h]
0x10082e574  sub     rsp, 250h
0x10082e57b  mov     [rbp+180h+var_A0], 0FFFFFFFFFFFFFFFEh
0x10082e586  mov     [rsp+280h+arg_18], rbx
0x10082e58e  mov     rax, cs:__security_cookie
0x10082e595  xor     rax, rsp
0x10082e598  mov     [rbp+180h+var_38], rax
0x10082e59f  mov     r15, r9
0x10082e5a2  mov     r12, rcx
0x10082e5a5  mov     [rbp+180h+var_200], rdx
0x10082e5a9  mov     [rbp+180h+var_1F8], r8d
0x10082e5ad  mov     rax, [rbp+180h+arg_28]
0x10082e5b4  mov     [rbp+180h+var_1E0], rax
0x10082e5b8  mov     rdi, [rbp+180h+arg_38]
0x10082e5bf  mov     rax, [rbp+180h+arg_40]
0x10082e5c6  mov     [rbp+180h+var_178], rax
0x10082e5ca  mov     rax, [rbp+180h+arg_48]
0x10082e5d1  mov     [rbp+180h+var_180], rax
0x10082e5d5  lea     rax, [rcx+28h]
0x10082e5d9  lea     rbx, [rcx+30h]
0x10082e5dd  add     rcx, 2Ch ; ','
0x10082e5e1  lea     r9, [r12+20h]; void **
0x10082e5e6  lea     r8, [r12+18h]; void **
0x10082e5eb  mov     [rsp+280h+var_250], rax; bool *
0x10082e5f0  mov     [rsp+280h+var_258], rbx; unsigned int *
0x10082e5f5  mov     [rsp+280h+var_260], rcx; unsigned int *
0x10082e5fa  mov     rdx, [r12+10h]; void *
0x10082e5ff  mov     rcx, [r12]; struct IMemObj *
0x10082e603  call    ?CrackUri@CAzureAttestationUtils@@SAJPEAVIMemObj@@PEBXPEAPEAX2PEAK3PEA_N@Z; CAzureAttestationUtils::CrackUri(IMemObj *,void const *,void * *,void * *,ulong *,ulong *,bool *)
0x10082e608  lea     rsi, aEnclaveAttesta; "Enclave attestation failed"
0x10082e60f  test    eax, eax
0x10082e611  jns     short loc_10082E641
0x10082e613  lfence
0x10082e616  mov     dword ptr [rsp+280h+var_250], eax
0x10082e61a  mov     rax, [r12+10h]
0x10082e61f  mov     [rsp+280h+var_258], rax
0x10082e624  mov     [rsp+280h+var_260], rsi
0x10082e629  mov     edx, 0Ah
0x10082e62e  mov     ecx, 175h
0x10082e633  lea     r9d, [rdx+28h]
0x10082e637  lea     r8d, [rdx+6]
0x10082e63b  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10082e641  mov     eax, [rbx]
0x10082e643  cmp     eax, 0Bh
0x10082e646  jz      short loc_10082E680
0x10082e648  cmp     eax, 2
0x10082e64b  jz      short loc_10082E680
0x10082e64d  lea     rax, aHttpS; "http(s)"
0x10082e654  mov     [rsp+280h+var_250], rax
0x10082e659  mov     rax, [r12+10h]
0x10082e65e  mov     [rsp+280h+var_258], rax
0x10082e663  mov     [rsp+280h+var_260], rsi
0x10082e668  mov     edx, 0Bh
0x10082e66d  mov     ecx, 175h
0x10082e672  lea     r9d, [rdx+37h]
0x10082e676  lea     r8d, [rdx+5]
0x10082e67a  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10082e680  xor     r14d, r14d
0x10082e683  mov     [rsp+280h+var_208], r14
0x10082e688  mov     rcx, [r12+8]
0x10082e68d  mov     rax, [rcx]
0x10082e690  lea     r8, [rsp+280h+var_208]
0x10082e695  mov     rdx, [r12]
0x10082e699  call    qword ptr [rax+8]
0x10082e69c  test    al, al
0x10082e69e  jnz     short loc_10082E6CD
0x10082e6a0  mov     [rsp+280h+var_250], r14
0x10082e6a5  lea     rax, aHttpclientnewi; "HttpClientNewInstance"
0x10082e6ac  mov     [rsp+280h+var_258], rax
0x10082e6b1  mov     [rsp+280h+var_260], rsi
0x10082e6b6  lea     edx, [r14+2]
0x10082e6ba  mov     ecx, 175h
0x10082e6bf  lea     r9d, [r14+33h]
0x10082e6c3  lea     r8d, [r14+10h]
0x10082e6c7  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10082e6cd  mov     [rbp+180h+var_1F0], r14
0x10082e6d1  mov     r13, 0FFFFFFFFFFFFFFFFh
0x10082e6d8  test    rdi, rdi
0x10082e6db  jz      loc_10082E812
0x10082e6e1  lea     rax, aAuthorizationB; "Authorization: Bearer "
0x10082e6e8  mov     [rbp+180h+var_B0], rax
0x10082e6ef  mov     [rbp+180h+var_A8], rdi
0x10082e6f6  mov     [rbp+180h+Source], r14
0x10082e6fa  mov     [rbp+180h+var_168], r14
0x10082e6fe  xor     cl, cl
0x10082e700  mov     edi, r14d
0x10082e703  cmp     edi, 2
0x10082e706  jnb     short loc_10082E73B
0x10082e708  mov     eax, edi
0x10082e70a  mov     r8, [rbp+rax*8+180h+var_B0]
0x10082e712  mov     rax, r13
0x10082e715  inc     rax
0x10082e718  cmp     word ptr [r8+rax*2], 0
0x10082e71e  jnz     short loc_10082E715
0x10082e720  mov     r9d, eax
0x10082e723  mov     rdx, [r12]
0x10082e727  lea     rcx, [rbp+180h+Source]
0x10082e72b  call    ?Append@?$SecureStringBuilder@_W@@QEAA_NPEAVIMemObj@@PEB_WK@Z; SecureStringBuilder<wchar_t>::Append(IMemObj *,wchar_t const *,ulong)
0x10082e730  test    al, al
0x10082e732  setz    cl
0x10082e735  inc     edi
0x10082e737  test    al, al
0x10082e739  jnz     short loc_10082E703
0x10082e73b  mov     edi, dword ptr [rbp+180h+var_168]
0x10082e73e  mov     rsi, [rbp+180h+Source]
0x10082e742  test    cl, cl
0x10082e744  jz      short loc_10082E74F
0x10082e746  mov     [rbp+180h+var_1F0], r14
0x10082e74a  mov     rbx, r14
0x10082e74d  jmp     short loc_10082E7BF
0x10082e74f  test    rsi, rsi
0x10082e752  jnz     short loc_10082E759
0x10082e754  mov     rbx, r14
0x10082e757  jmp     short loc_10082E7BB
0x10082e759  lea     ecx, [rdi+1]
0x10082e75c  mov     eax, 2
0x10082e761  mul     rcx
0x10082e764  cmovo   rax, r13
0x10082e768  mov     byte ptr [rsp+280h+var_258], 6
0x10082e76d  mov     dword ptr [rsp+280h+var_260], 6Ah ; 'j'
0x10082e775  lea     r9, aSqlNtdbmsMsqlS_0; "Sql\\Ntdbms\\msql\\security\\inc\\Secur"...
0x10082e77c  mov     r8d, 1
0x10082e782  mov     rdx, [r12]
0x10082e786  mov     rcx, rax
0x10082e789  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10082e78f  mov     rbx, rax
0x10082e792  test    rax, rax
0x10082e795  jnz     short loc_10082E79C
0x10082e797  mov     rbx, r14
0x10082e79a  jmp     short loc_10082E7BB
0x10082e79c  lea     eax, ds:2[rdi*2]
0x10082e7a3  mov     edx, eax; DestinationSize
0x10082e7a5  mov     r9d, eax; SourceSize
0x10082e7a8  mov     r8, rsi; Source
0x10082e7ab  mov     rcx, rbx; Destination
0x10082e7ae  call    memcpy_s
0x10082e7b3  xor     ecx, ecx
0x10082e7b5  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10082e7bb  mov     [rbp+180h+var_1F0], rbx
0x10082e7bf  test    rsi, rsi
0x10082e7c2  jz      short loc_10082E7DA
0x10082e7c4  mov     rcx, rdi
0x10082e7c7  add     rcx, rcx
0x10082e7ca  mov     rdi, rsi
0x10082e7cd  xor     eax, eax
0x10082e7cf  rep stosb
0x10082e7d1  mov     rcx, rsi
0x10082e7d4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10082e7da  test    rbx, rbx
0x10082e7dd  jnz     short loc_10082E812
0x10082e7df  mov     [rsp+280h+var_250], r14
0x10082e7e4  lea     rax, aAddauthtoken; "AddAuthToken"
0x10082e7eb  mov     [rsp+280h+var_258], rax
0x10082e7f0  lea     rax, aEnclaveAttesta; "Enclave attestation failed"
0x10082e7f7  mov     [rsp+280h+var_260], rax
0x10082e7fc  lea     edx, [rbx+2]
0x10082e7ff  mov     ecx, 175h
0x10082e804  lea     r9d, [rbx+34h]
0x10082e808  lea     r8d, [rbx+10h]
0x10082e80c  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10082e812  mov     rbx, r14
0x10082e815  mov     [rbp+180h+var_1C8], rbx
0x10082e819  mov     r14, [r12]
0x10082e81d  xor     edi, edi
0x10082e81f  mov     [rbp+180h+var_1B8], rdi
0x10082e823  lea     r9, [rbp+180h+var_1B8]; wchar_t **
0x10082e827  lea     r8, [rbp+180h+var_1F8]; unsigned int *
0x10082e82b  lea     rdx, [rbp+180h+var_200]; unsigned __int8 **
0x10082e82f  mov     rcx, r14; struct IMemObj *
0x10082e832  call    ?Base64UrlEncode@CBase64Utils@@SAKPEAVIMemObj@@AEBQEAEAEBKPEAPEA_W@Z; CBase64Utils::Base64UrlEncode(IMemObj *,uchar * const &,ulong const &,wchar_t * *)
0x10082e837  mov     esi, eax
0x10082e839  test    eax, eax
0x10082e83b  jz      short loc_10082E84E
0x10082e83d  jle     short loc_10082E848
0x10082e83f  movzx   esi, ax
0x10082e842  or      esi, 80070000h
0x10082e848  mov     rcx, [rbp+180h+var_1B8]
0x10082e84c  jmp     short loc_10082E889
0x10082e84e  mov     [rbp+180h+var_1D8], rdi
0x10082e852  lea     r8, [rbp+180h+var_1D8]; char **
0x10082e856  mov     rdi, [rbp+180h+var_1B8]
0x10082e85a  mov     rdx, rdi; wchar_t *
0x10082e85d  mov     rcx, r14; struct IMemObj *
0x10082e860  call    ?StringFromWString@CAzureAttestationUtils@@SAJPEAVIMemObj@@PEB_WPEAPEAD@Z; CAzureAttestationUtils::StringFromWString(IMemObj *,wchar_t const *,char * *)
0x10082e865  mov     esi, eax
0x10082e867  test    eax, eax
0x10082e869  js      short loc_10082E87B
0x10082e86b  mov     rbx, [rbp+180h+var_1D8]
0x10082e86f  xor     ecx, ecx
0x10082e871  mov     [rbp+180h+var_1D8], rcx
0x10082e875  mov     [rbp+180h+var_1C8], rbx
0x10082e879  jmp     short loc_10082E87F
0x10082e87b  mov     rcx, [rbp+180h+var_1D8]
0x10082e87f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10082e885  nop
0x10082e886  mov     rcx, rdi
0x10082e889  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10082e88f  test    esi, esi
0x10082e891  jns     short loc_10082E8CE
0x10082e893  lfence
0x10082e896  mov     dword ptr [rsp+280h+var_250], esi
0x10082e89a  lea     rax, aParsequote; "ParseQuote"
0x10082e8a1  mov     [rsp+280h+var_258], rax
0x10082e8a6  lea     rax, aEnclaveAttesta; "Enclave attestation failed"
0x10082e8ad  mov     [rsp+280h+var_260], rax
0x10082e8b2  mov     edx, 2
0x10082e8b7  mov     ecx, 175h
0x10082e8bc  lea     r9d, [rdx+33h]
0x10082e8c0  lea     r8d, [rdx+0Eh]
0x10082e8c4  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10082e8ca  mov     rbx, [rbp+180h+var_1C8]
0x10082e8ce  xor     esi, esi
0x10082e8d0  mov     r8d, esi
0x10082e8d3  mov     r9d, [rbp+180h+arg_30]
0x10082e8da  test    r9d, r9d
0x10082e8dd  jz      short loc_10082E90B
0x10082e8df  mov     rdi, [rbp+180h+var_1E0]
0x10082e8e3  mov     r10d, [rbp+180h+arg_20]
0x10082e8ea  nop     word ptr [rax+rax+00h]
0x10082e8f0  xor     edx, edx
0x10082e8f2  mov     eax, r8d
0x10082e8f5  div     r10d
0x10082e8f8  movzx   eax, byte ptr [rdx+r15]
0x10082e8fd  xor     [rdi], al
0x10082e8ff  inc     r8d
0x10082e902  lea     rdi, [rdi+1]
0x10082e906  cmp     r8d, r9d
0x10082e909  jb      short loc_10082E8F0
0x10082e90b  mov     rdi, rsi
0x10082e90e  mov     [rbp+180h+var_188], rsi
0x10082e912  mov     r15, [r12]
0x10082e916  mov     [rbp+180h+var_1B0], rsi
0x10082e91a  lea     r9, [rbp+180h+var_1B0]; wchar_t **
0x10082e91e  lea     r8, [rbp+180h+arg_30]; unsigned int *
0x10082e925  lea     rdx, [rbp+180h+var_1E0]; unsigned __int8 **
0x10082e929  mov     rcx, r15; struct IMemObj *
0x10082e92c  call    ?Base64UrlEncode@CBase64Utils@@SAKPEAVIMemObj@@AEBQEAEAEBKPEAPEA_W@Z; CBase64Utils::Base64UrlEncode(IMemObj *,uchar * const &,ulong const &,wchar_t * *)
0x10082e931  mov     r14d, eax
0x10082e934  test    eax, eax
0x10082e936  jz      short loc_10082E94B
0x10082e938  jle     short loc_10082E945
0x10082e93a  movzx   r14d, ax
0x10082e93e  or      r14d, 80070000h
0x10082e945  mov     rcx, [rbp+180h+var_1B0]
0x10082e949  jmp     short loc_10082E987
0x10082e94b  mov     [rbp+180h+var_1D0], rsi
0x10082e94f  lea     r8, [rbp+180h+var_1D0]; char **
0x10082e953  mov     rsi, [rbp+180h+var_1B0]
0x10082e957  mov     rdx, rsi; wchar_t *
0x10082e95a  mov     rcx, r15; struct IMemObj *
0x10082e95d  call    ?StringFromWString@CAzureAttestationUtils@@SAJPEAVIMemObj@@PEB_WPEAPEAD@Z; CAzureAttestationUtils::StringFromWString(IMemObj *,wchar_t const *,char * *)
0x10082e962  mov     r14d, eax
0x10082e965  test    eax, eax
0x10082e967  js      short loc_10082E979
0x10082e969  mov     rdi, [rbp+180h+var_1D0]
0x10082e96d  xor     ecx, ecx
0x10082e96f  mov     [rbp+180h+var_1D0], rcx
0x10082e973  mov     [rbp+180h+var_188], rdi
0x10082e977  jmp     short loc_10082E97D
0x10082e979  mov     rcx, [rbp+180h+var_1D0]
0x10082e97d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10082e983  nop
0x10082e984  mov     rcx, rsi
0x10082e987  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10082e98d  test    r14d, r14d
0x10082e990  jns     short loc_10082E9D2
0x10082e992  lfence
0x10082e995  mov     dword ptr [rsp+280h+var_250], r14d
0x10082e99a  lea     rax, aParseenclavehe; "ParseEnclaveHeldData"
0x10082e9a1  mov     [rsp+280h+var_258], rax
0x10082e9a6  lea     rax, aEnclaveAttesta; "Enclave attestation failed"
0x10082e9ad  mov     [rsp+280h+var_260], rax
0x10082e9b2  mov     edx, 2
0x10082e9b7  mov     ecx, 175h
0x10082e9bc  lea     r9d, [rdx+34h]
0x10082e9c0  lea     r8d, [rdx+0Eh]
0x10082e9c4  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10082e9ca  mov     rbx, [rbp+180h+var_1C8]
0x10082e9ce  mov     rdi, [rbp+180h+var_188]
0x10082e9d2  xor     r15d, r15d
0x10082e9d5  mov     [rsp+280h+var_210], r15
0x10082e9da  cmp     [r12+28h], r15b
0x10082e9df  jz      loc_10082EAF1
0x10082e9e5  lea     rax, aEnclavehelddat; "{\"EnclaveHeldData\":\""
0x10082e9ec  mov     [rbp+180h+String], rax
0x10082e9f3  mov     [rbp+180h+var_80], rdi
0x10082e9fa  lea     rax, aQuote; "\",\"Quote\":\""
0x10082ea01  mov     [rbp+180h+var_78], rax
0x10082ea08  mov     [rbp+180h+var_70], rbx
0x10082ea0f  lea     rax, asc_1008A1E5C; "\"}"
0x10082ea16  mov     [rbp+180h+var_68], rax
0x10082ea1d  mov     [rbp+180h+var_160], r15
0x10082ea21  mov     [rbp+180h+var_158], r15
  ... truncated ...
```
