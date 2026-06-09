# CSpVAMaster::LoadEngines(ISpAudioOrchestratorPolicy *,ISpAudioOrchestratorAnchor *,ISpAudioOrchestratorReader *,ISpAudioOrchestratorDisambiguator *)

- ea: `0x1801bb140`
- end: `0x1801bbf73`
- name: `?LoadEngines@CSpVAMaster@@UEAAJPEAUISpAudioOrchestratorPolicy@@PEAUISpAudioOrchestratorAnchor@@PEAUISpAudioOrchestratorReader@@PEAUISpAudioOrchestratorDisambiguator@@@Z`
- size: `3635`
- prototype: `__int64 __fastcall(CSpVAMaster *__hidden this, struct IUnknown *, struct IUnknown *, struct IUnknown *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000a590`
- `0x18000be70`
- `0x18000bec4`
- `0x18000e518`
- `0x180013ec0`
- `0x18001cfdc`
- `0x18003d910`
- `0x180043280`
- `0x180056060`
- `0x18005e0c8`
- `0x180079e30`
- `0x1801b9d44`
- `0x1801ba374`
- `0x1801baae0`
- `0x1801bb140`
- `0x1801bdb84`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801bb1b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801bb1b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801bbf23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801bbf23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801bb411`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801bbbbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801bb411`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801bbbbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bb22f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bb22f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801bbcbe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801bbcbe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801bbe23`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801bbe5f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801bbe97`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801bbe23`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801bbe5f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801bbe97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bbe31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bbe6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bbea9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bbe31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bbe6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bbea9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801bb3f9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801bb3f9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801bbbb2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801bbbb2`

## string_xrefs

- `0x1801bb41a`: `VaMaster test: Cannot open file! %d\n`
- `0x1801bbbc5`: `VaMaster test: WriteFile failed! %d \n`
- `0x1801bbaee`: `VAMaster: SW VA Engine load SID table, hr = 0x%x\n`
- `0x1801bbe8d`: `CLSID\{6fbd703b-fece-4348-b93d-6e92ac097f17}`
- `0x1801bbe15`: `CLSID\{EC774FA9-28D3-424A-90E4-69F984F1EEB7}`
- `0x1801bbe4e`: `CLSID\{76882AA2-2E80-48F1-A14E-4DB1FAC1F849}`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CSpVAMaster::LoadEngines(
        CSpVAMaster *this,
        struct IUnknown *a2,
        struct IUnknown *a3,
        struct IUnknown *a4,
        struct IUnknown *a5)
{
  int v9; // ebx
  _QWORD *v10; // r13
  void *v11; // rcx
  unsigned __int16 v12; // r12
  const wchar_t *v13; // rax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rdx
  int v20; // eax
  HANDLE FileW; // rax
  DWORD LastError; // eax
  int v23; // eax
  _QWORD *v24; // r12
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  __int64 **v35; // r12
  int ObjectFrom; // eax
  int v37; // eax
  int v38; // eax
  int v39; // eax
  int v40; // eax
  int v41; // eax
  int v42; // eax
  __int64 *v43; // rcx
  __int64 v44; // r8
  int v45; // eax
  int v46; // eax
  int v47; // eax
  int DiscreteDetectionAdditionalTime; // eax
  int v49; // eax
  _QWORD *v50; // r12
  int v51; // eax
  int v52; // eax
  int v53; // eax
  int v54; // eax
  int v55; // eax
  int v56; // eax
  _QWORD *v57; // r12
  int v58; // eax
  int v59; // eax
  int v60; // eax
  __int64 v61; // rax
  const char *v62; // rdx
  __int64 v63; // rdx
  LPCVOID *v64; // rdx
  DWORD v65; // eax
  __int64 v66; // rcx
  int v67; // eax
  HRESULT Instance; // eax
  __int64 v69; // rax
  _QWORD *v70; // r14
  unsigned __int16 v71; // r15
  int v72; // r11d
  BOOL v73; // eax
  int v74; // eax
  int v75; // eax
  int dwFlagsAndAttributes; // [rsp+28h] [rbp-99h]
  DWORD NumberOfBytesWritten[2]; // [rsp+50h] [rbp-71h] BYREF
  int v79; // [rsp+58h] [rbp-69h] BYREF
  struct ISpObjectToken *v80; // [rsp+60h] [rbp-61h] BYREF
  __int64 v81; // [rsp+68h] [rbp-59h] BYREF
  int v82; // [rsp+70h] [rbp-51h] BYREF
  int v83; // [rsp+74h] [rbp-4Dh] BYREF
  __int64 v84; // [rsp+78h] [rbp-49h] BYREF
  LPCWSTR lpFileName; // [rsp+80h] [rbp-41h] BYREF
  __int64 v86; // [rsp+88h] [rbp-39h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+90h] [rbp-31h]
  __int64 v88; // [rsp+98h] [rbp-29h]
  LPCVOID lpBuffer[2]; // [rsp+A0h] [rbp-21h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+B0h] [rbp-11h]
  unsigned __int64 v91; // [rsp+B8h] [rbp-9h]

  v81 = 0;
  v80 = 0;
  v84 = 0;
  lpFileName = 0;
  v83 = 0;
  v79 = 0;
  v82 = 0;
  v88 = ((unsigned __int64)this + 48) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64);
  lpCriticalSection = (LPCRITICAL_SECTION)(v88 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(v88 + 8));
  if ( *((_DWORD *)this + 30) )
  {
    v9 = -2147483634;
    goto LABEL_157;
  }
  v10 = (_QWORD *)((char *)this + 208);
  if ( *((struct IUnknown **)this + 26) != a2 )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 26, a2);
  if ( *((struct IUnknown **)this + 27) != a3 )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 27, a3);
  if ( *((struct IUnknown **)this + 28) != a4 )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 28, a4);
  if ( *((struct IUnknown **)this + 29) != a5 )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 29, a5);
  v11 = (void *)*((_QWORD *)this + 22);
  if ( v11 )
  {
    CloseHandle(v11);
    *((_QWORD *)this + 22) = 0;
  }
  v12 = 1;
  if ( !*v10 )
  {
    v9 = -2147201023;
    dwFlagsAndAttributes = -2147201023;
    v13 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(241)";
LABEL_15:
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CSpVAMaster::LoadEngines",
      v13,
      dwFlagsAndAttributes);
    goto LABEL_132;
  }
  v14 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, LPCWSTR *))(*(_QWORD *)*v10 + 24LL))(
          *v10,
          L"VoiceActivationMetricsFile",
          &lpFileName);
  if ( v14 < 0 )
    DoTraceMessage(
      2,
      "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CSpVAMaster::LoadEngines",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(242)",
      v14);
  v15 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, int *))(*(_QWORD *)*v10 + 32LL))(
          *v10,
          L"SoftwareVoiceActivationInSKU",
          &v79);
  v9 = v15;
  if ( v15 < 0 )
  {
    dwFlagsAndAttributes = v15;
    v13 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(243)";
    goto LABEL_15;
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, int *))(*(_QWORD *)*v10 + 32LL))(
          *v10,
          L"HardwareVoiceActivationInSKU",
          &v82);
  v9 = v16;
  if ( v16 < 0 )
  {
    dwFlagsAndAttributes = v16;
    v13 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(244)";
    goto LABEL_15;
  }
  v17 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, int *))(*(_QWORD *)*v10 + 32LL))(
          *v10,
          L"SpeakerIDOn",
          &v83);
  if ( v17 < 0 )
    DoTraceMessage(
      2,
      "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CSpVAMaster::LoadEngines",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(245)",
      v17);
  v18 = (**(__int64 (__fastcall ***)(CSpVAMaster *, GUID *, __int64 *))this)(
          this,
          &GUID_bed3d04b_c290_40b1_93e3_e13447f5c676,
          &v81);
  v9 = v18;
  v19 = 0;
  if ( v18 < 0 )
  {
    dwFlagsAndAttributes = v18;
    v13 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(246)";
    goto LABEL_15;
  }
  if ( !v79 || (v20 = 1, !v82) )
    v20 = 0;
  *((_DWORD *)this + 66) = v20;
  *((_DWORD *)this + 68) = v83 != 0;
  if ( lpFileName )
  {
    FileW = CreateFileW(lpFileName, 0x40000000u, 1u, 0, 2u, 0x80u, 0);
    *((_QWORD *)this + 22) = FileW;
    if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastError = GetLastError();
      DoTraceMessage(8, "VaMaster test: Cannot open file! %d\n", LastError);
    }
  }
  v23 = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this + 2) + 24LL))((char *)this + 16, v19);
  v9 = v23;
  if ( v23 < 0 )
  {
    dwFlagsAndAttributes = v23;
    v13 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(260)";
    goto LABEL_15;
  }
  if ( !(unsigned int)CSpVAMaster::GetPolicy_MockHWVAEngine(this) )
  {
    if ( !*((_QWORD *)this + 14) )
    {
LABEL_55:
      NumberOfBytesWritten[0] = 0;
      if ( *((_QWORD *)this + 47) && v79 == 1 )
      {
        ATL::CComPtrBase<ISpCFGInterpreter>::Release(&v80);
        v34 = (*(__int64 (__fastcall **)(char *, __int64, _QWORD, struct ISpObjectToken **))(*((_QWORD *)this + 2) + 40LL))(
                (char *)this + 16,
                2,
                0,
                &v80);
        v9 = v34;
        if ( v34 < 0 )
        {
          dwFlagsAndAttributes = v34;
          v13 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(294)";
          goto LABEL_15;
        }
        v35 = (__int64 **)((char *)this + 384);
        ObjectFrom = SpCreateObjectFromToken<ISpVAEngine>(v80, (char *)this + 384);
        v9 = ObjectFrom;
        if ( ObjectFrom < 0 )
        {
          DoTraceMessage(
            2,
            "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
            (const wchar_t *)&NLInternal::s_tracingPrefix,
            L"CSpVAMaster::LoadEngines",
            L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(295)",
            ObjectFrom);
          goto LABEL_131;
        }
        v37 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64 *))**v35)(
                *v35,
                &GUID_5b559f40_e952_11d2_bb91_00c04f8ee6c0,
                &v84);
        v9 = v37;
        if ( v37 < 0 )
        {
          DoTraceMessage(
            2,
            "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
            (const wchar_t *)&NLInternal::s_tracingPrefix,
            L"CSpVAMaster::LoadEngines",
            L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(297)",
            v37);
          goto LABEL_131;
        }
        v38 = (*(__int64 (__fastcall **)(__int64 *, __int64))(**v35 + 24))(*v35, v81);
        v9 = v38;
        if ( v38 < 0 )
        {
          DoTraceMessage(
            2,
            "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
            (const wchar_t *)&NLInternal::s_tracingPrefix,
            L"CSpVAMaster::LoadEngines",
            L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(298)",
            v38);
          goto LABEL_131;
        }
        v39 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(**v35 + 32))(*v35, *v10);
        v9 = v39;
        if ( v39 < 0 )
        {
          DoTraceMessage(
            2,
            "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
            (const wchar_t *)&NLInternal::s_tracingPrefix,
            L"CSpVAMaster::LoadEngines",
            L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(299)",
            v39);
          goto LABEL_131;
        }
        v40 = (*(__int64 (__fastcall **)(__int64 *, __int64))(**v35 + 40))(*v35, 1);
        v9 = v40;
        if ( v40 < 0 )
        {
          DoTraceMessage(
            2,
            "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
            (const wchar_t *)&NLInternal::s_tracingPrefix,
            L"CSpVAMaster::LoadEngines",
            L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(300)",
            v40);
          goto LABEL_131;
        }
        v41 = (*(__int64 (__fastcall **)(__int64 *, char *))(**v35 + 88))(*v35, (char *)this + 252);
        v9 = v41;
        if ( v41 < 0 )
        {
          DoTraceMessage(
            2,
            "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
            (const wchar_t *)&NLInternal::s_tracingPrefix,
            L"CSpVAMaster::LoadEngines",
            L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(301)",
            v41);
          goto LABEL_131;
        }
        v42 = (*(__int64 (__fastcall **)(__int64 *, __int64))(**v35 + 96))(*v35, 1);
        v43 = *v35;
        v44 = **v35;
        if ( v42 >= 0 )
        {
          v47 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v44 + 96))(v43, 4);
          if ( v47 < 0 )
            DoTraceMessage(
              2,
              "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
              (const wchar_t *)&NLInternal::s_tracingPrefix,
              L"CSpVAMaster::LoadEngines",
              L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(313)",
              v47);
          DiscreteDetectionAdditionalTime = CSpVAMaster::GetDiscreteDetectionAdditionalTime(this);
          if ( DiscreteDetectionAdditionalTime < 0 )
            DoTraceMessage(
              2,
              "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
              (const wchar_t *)&NLInternal::s_tracingPrefix,
              L"CSpVAMaster::LoadEngines",
              L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(314)",
              DiscreteDetectionAdditionalTime);
          NumberOfBytesWritten[0] = 2;
        }
        else
        {
          v45 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(v44 + 24))(v43, 0);
          if ( v45 < 0 )
            DoTraceMessage(
              2,
              "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
              (const wchar_t *)&NLInternal::s_tracingPrefix,
              L"CSpVAMaster::LoadEngines",
              L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(305)",
              v45);
          v46 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(**v35 + 32))(*v35, 0);
          if ( v46 < 0 )
            DoTraceMessage(
              2,
              "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
              (const wchar_t *)&NLInternal::s_tracingPrefix,
              L"CSpVAMaster::LoadEngines",
              L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(306)",
              v46);
          ATL::CComPtrBase<ISpCFGInterpreter>::Release((char *)this + 384);
          DoTraceMessage(8, "VAMaster: segment SWKWS model not found, hr = 0x%x\n", v9);
        }
      }
      if ( *((_QWORD *)this + 13) )
      {
        v12 = 1;
        if ( v79 == 1 )
        {
          ATL::CComPtrBase<ISpCFGInterpreter>::Release(&v80);
          v49 = (*(__int64 (__fastcall **)(char *, __int64, _QWORD, struct ISpObjectToken **))(*((_QWORD *)this + 2)
                                                                                             + 40LL))(
                  (char *)this + 16,
                  2,
                  0,
                  &v80);
          v9 = v49;
          if ( v49 < 0 )
          {
            dwFlagsAndAttributes = v49;
            v13 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(322)";
            goto LABEL_15;
          }
          v50 = (_QWORD *)((char *)this + 184);
          v51 = SpCreateObjectFromToken<ISpVAEngine>(v80, (char *)this + 184);
          v9 = v51;
          if ( v51 < 0 )
          {
            DoTraceMessage(
              2,
              "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
              (const wchar_t *)&NLInternal::s_tracingPrefix,
              L"CSpVAMaster::LoadEngines",
              L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(323)",
              v51);
            goto LABEL_131;
          }
          v52 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v50)(
                  *v50,
                  &GUID_5b559f40_e952_11d2_bb91_00c04f8ee6c0,
                  &v84);
          v9 = v52;
          if ( v52 < 0 )
          {
            DoTraceMessage(
              2,
              "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
              (const wchar_t *)&NLInternal::s_tracingPrefix,
              L"CSpVAMaster::LoadEngines",
              L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(326)",
              v52);
            goto LABEL_131;
          }
          v53 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v50 + 24LL))(*v50, v81);
          v9 = v53;
          if ( v53 < 0 )
          {
            DoTraceMessage(
              2,
              "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
              (const wchar_t *)&NLInternal::s_tracingPrefix,
              L"CSpVAMaster::LoadEngines",
              L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(327)",
              v53);
            goto LABEL_131;
          }
          v54 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v50 + 32LL))(*v50, *v10);
          v9 = v54;
          if ( v54 < 0 )
          {
            DoTraceMessage(
              2,
              "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
              (const wchar_t *)&NLInternal::s_tracingPrefix,
              L"CSpVAMaster::LoadEngines",
              L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(328)",
              v54);
            goto LABEL_131;
          }
          v55 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v50 + 40LL))(*v50, NumberOfBytesWritten[0]);
          v9 = v55;
          if ( v55 < 0 )
          {
            DoTraceMessage(
              2,
              "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
              (const wchar_t *)&NLInternal::s_tracingPrefix,
              L"CSpVAMaster::LoadEngines",
              L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(329)",
              v55);
            goto LABEL_131;
          }
          v56 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v50 + 88LL))(*v50, (char *)this + 252);
          v9 = v56;
          if ( v56 < 0 )
          {
            DoTraceMessage(
              2,
              "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
              (const wchar_t *)&NLInternal::s_tracingPrefix,
              L"CSpVAMaster::LoadEngines",
              L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(330)",
              v56);
            goto LABEL_131;
          }
          SPTelemetry::LogEngineModelRevision(v80);
        }
      }
      v57 = (_QWORD *)((char *)this + 184);
      if ( !*((_QWORD *)this + 48) && *v57 && *((_DWORD *)this + 68) )
      {
        if ( (*(int (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v57 + 96LL))(*v57, 1) >= 0 )
        {
          DoTraceMessage(8, "VAMaster: SW VA Engine load SID table, hr = 0x%x\n", v9);
          v60 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v57 + 96LL))(*v57, 4);
          if ( v60 < 0 )
            DoTraceMessage(
              2,
              "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
              (const wchar_t *)&NLInternal::s_tracingPrefix,
              L"CSpVAMaster::LoadEngines",
              L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(349)",
              v60);
        }
        else
        {
          v58 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v57 + 24LL))(*v57, 0);
          if ( v58 < 0 )
            DoTraceMessage(
              2,
              "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
              (const wchar_t *)&NLInternal::s_tracingPrefix,
              L"CSpVAMaster::LoadEngines",
              L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(340)",
              v58);
          v59 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v57 + 32LL))(*v57, 0);
          if ( v59 < 0 )
            DoTraceMessage(
              2,
              "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
              (const wchar_t *)&NLInternal::s_tracingPrefix,
              L"CSpVAMaster::LoadEngines",
              L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(341)",
              v59);
          ATL::CComPtrBase<ISpCFGInterpreter>::Release((char *)this + 184);
          DoTraceMessage(8, "VAMaster: SW VA Engine failed to start, hr = 0x%x\n", v9);
        }
      }
      v61 = *((_QWORD *)this + 22);
      if ( v61 && v61 != -1 )
      {
        v62 = "DiscreteDetectionEnabled";
        if ( !*((_QWORD *)this + 48) )
          v62 = "DiscreteDetectionDisabled";
        std::string::string(lpBuffer, v62);
        LOBYTE(v63) = 10;
        std::string::push_back(lpBuffer, v63);
        NumberOfBytesWritten[0] = 0;
        v64 = lpBuffer;
        if ( v91 > 0xF )
          v64 = (LPCVOID *)lpBuffer[0];
        if ( !WriteFile(*((HANDLE *)this + 22), v64, nNumberOfBytesToWrite, NumberOfBytesWritten, 0) )
        {
          v65 = GetLastError();
          DoTraceMessage(8, "VaMaster test: WriteFile failed! %d \n", v65);
        }
        std::string::_Tidy_deallocate(lpBuffer);
      }
      if ( *((_QWORD *)this + 25)
        || (v66 = *v57, *((_QWORD *)this + 25) = *v57, *((_DWORD *)this + 64) = *((_DWORD *)this + 63), v66) )
      {
        if ( *((_DWORD *)this + 69) == -1
          && (v67 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 28) + 24LL))(
                      *((_QWORD *)this + 28),
                      5,
                      0),
              v9 = v67,
              v67 < 0) )
        {
          DoTraceMessage(
            2,
            "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
            (const wchar_t *)&NLInternal::s_tracingPrefix,
            L"CSpVAMaster::LoadEngines",
            L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(382)",
            v67);
        }
        else if ( (*((_DWORD *)this + 62) || *((_DWORD *)this + 63)) && !*((_QWORD *)this + 30) )
        {
          *(_QWORD *)NumberOfBytesWritten = 0;
          Instance = CoCreateInstance(
                       &CLSID_SpResourceManager,
                       0,
                       0x17u,
                       &GUID_2baeef81_2ca3_4331_98f3_26ec5abefb03,
                       (LPVOID *)NumberOfBytesWritten);
          v9 = Instance;
          if ( Instance >= 0 )
          {
            v74 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, _QWORD, char *))(**(_QWORD **)NumberOfBytesWritten
                                                                                    + 56LL))(
                    *(_QWORD *)NumberOfBytesWritten,
                    (char *)this + 40,
                    0,
                    0,
                    (char *)this + 240);
            v9 = v74;
            if ( v74 >= 0 )
            {
              v86 = 0;
              v75 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 30) + 32LL))(
                      *((_QWORD *)this + 30),
                      0,
                      &v86);
              v9 = v75;
              if ( v75 < 0 )
                DoTraceMessage(
                  2,
                  "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
                  (const wchar_t *)&NLInternal::s_tracingPrefix,
                  L"CSpVAMaster::LoadEngines",
                  L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(393)",
                  v75);
            }
            else
            {
              DoTraceMessage(
                2,
                "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
                (const wchar_t *)&NLInternal::s_tracingPrefix,
                L"CSpVAMaster::LoadEngines",
                L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(390)",
                v74);
            }
          }
          else
          {
            DoTraceMessage(
              2,
              "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
              (const wchar_t *)&NLInternal::s_tracingPrefix,
              L"CSpVAMaster::LoadEngines",
              L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(389)",
              Instance);
          }
          ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(NumberOfBytesWritten);
        }
      }
      else
      {
        v9 = -2147201023;
        DoTraceMessage(
          2,
          "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
          (const wchar_t *)&NLInternal::s_tracingPrefix,
          L"CSpVAMaster::LoadEngines",
          L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(372)",
          -2147201023);
      }
      goto LABEL_131;
    }
    v28 = (*(__int64 (__fastcall **)(char *, __int64, _QWORD, struct ISpObjectToken **))(*((_QWORD *)this + 2) + 40LL))(
            (char *)this + 16,
            4,
            0,
            &v80);
    v9 = v28;
    if ( v28 < 0 )
    {
      dwFlagsAndAttributes = v28;
      v13 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(278)";
      goto LABEL_15;
    }
    v24 = (_QWORD *)((char *)this + 192);
    v29 = SpCreateObjectFromToken<ISpVAEngine>(v80, (char *)this + 192);
    v9 = v29;
    if ( v29 < 0 )
    {
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        (const wchar_t *)&NLInternal::s_tracingPrefix,
        L"CSpVAMaster::LoadEngines",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(279)",
        v29);
      goto LABEL_131;
    }
    v30 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v24)(
            *v24,
            &GUID_5b559f40_e952_11d2_bb91_00c04f8ee6c0,
            &v84);
    v9 = v30;
    if ( v30 < 0 )
    {
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        (const wchar_t *)&NLInternal::s_tracingPrefix,
        L"CSpVAMaster::LoadEngines",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(281)",
        v30);
      goto LABEL_131;
    }
    v31 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v24 + 24LL))(*v24, v81);
    v9 = v31;
    if ( v31 < 0 )
    {
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        (const wchar_t *)&NLInternal::s_tracingPrefix,
        L"CSpVAMaster::LoadEngines",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(282)",
        v31);
      goto LABEL_131;
    }
    v32 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v24 + 32LL))(*v24, *v10);
    v9 = v32;
    if ( v32 < 0 )
    {
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        (const wchar_t *)&NLInternal::s_tracingPrefix,
        L"CSpVAMaster::LoadEngines",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(283)",
        v32);
      goto LABEL_131;
    }
    v33 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v24 + 88LL))(*v24, (char *)this + 248);
    v9 = v33;
    if ( v33 < 0 )
    {
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        (const wchar_t *)&NLInternal::s_tracingPrefix,
        L"CSpVAMaster::LoadEngines",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(284)",
        v33);
      goto LABEL_131;
    }
LABEL_54:
    *((_QWORD *)this + 25) = *v24;
    v12 = 1;
    *((_DWORD *)this + 64) = *((_DWORD *)this + 62);
    goto LABEL_55;
  }
  v24 = (_QWORD *)((char *)this + 192);
  CSpVAMaster::CreateMockHWVAEngine(this, (struct IUnknown **)this + 24);
  v25 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v24 + 24LL))(*v24, v81);
  v9 = v25;
  if ( v25 >= 0 )
  {
    v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v24 + 32LL))(*v24, *v10);
    v9 = v26;
    if ( v26 < 0 )
    {
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        (const wchar_t *)&NLInternal::s_tracingPrefix,
        L"CSpVAMaster::LoadEngines",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(269)",
        v26);
      goto LABEL_131;
    }
    v27 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v24 + 88LL))(*v24, (char *)this + 248);
    v9 = v27;
    if ( v27 < 0 )
    {
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        (const wchar_t *)&NLInternal::s_tracingPrefix,
        L"CSpVAMaster::LoadEngines",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(270)",
        v27);
      goto LABEL_131;
    }
    goto LABEL_54;
  }
  DoTraceMessage(
    2,
    "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
    (const wchar_t *)&NLInternal::s_tracingPrefix,
    L"CSpVAMaster::LoadEngines",
    L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vamaster.cpp(268)",
    v25);
LABEL_131:
  v12 = 1;
LABEL_132:
  v69 = *((_QWORD *)this + 25);
  v70 = (_QWORD *)((char *)this + 192);
  if ( v69 == *((_QWORD *)this + 23) )
  {
    v71 = 1;
    v12 = 2;
    if ( v69 != *v70 )
    {
LABEL_134:
      v72 = 1;
      goto LABEL_135;
    }
LABEL_144:
    *(_QWORD *)NumberOfBytesWritten = 0;
    if ( RegOpenKeyExW(
           HKEY_CLASSES_ROOT,
           L"CLSID\\{EC774FA9-28D3-424A-90E4-69F984F1EEB7}",
           0,
           0x20019u,
           (PHKEY)NumberOfBytesWritten) )
    {
      if ( RegOpenKeyExW(
             HKEY_CLASSES_ROOT,
             L"CLSID\\{76882AA2-2E80-48F1-A14E-4DB1FAC1F849}",
             0,
             0x20019u,
             (PHKEY)NumberOfBytesWritten) )
      {
        if ( !RegOpenKeyExW(
                HKEY_CLASSES_ROOT,
                L"CLSID\\{6fbd703b-fece-4348-b93d-6e92ac097f17}",
                0,
                0x20019u,
                (PHKEY)NumberOfBytesWritten) )
        {
          RegCloseKey(*(HKEY *)NumberOfBytesWritten);
          v71 = 8;
        }
      }
      else
      {
        RegCloseKey(*(HKEY *)NumberOfBytesWritten);
        v71 = 4;
      }
    }
    else
    {
      RegCloseKey(*(HKEY *)NumberOfBytesWritten);
      v71 = 2;
    }
    goto LABEL_134;
  }
  if ( v69 == *v70 )
  {
    v12 = 4;
    v71 = 1;
    goto LABEL_144;
  }
  v72 = 1;
  v71 = 1;
LABEL_135:
  v73 = *((_QWORD *)this + 47) && v79 == 1;
  if ( !*((_QWORD *)this + 13) || v79 != 1 )
    v72 = 0;
  SPTelemetry::VaInitializeEngineType(
    v12,
    v71,
    *((_QWORD *)this + 14) != 0,
    v72,
    v73,
    *v70 != 0,
    *((_QWORD *)this + 23) != 0,
    *((_QWORD *)this + 48) != 0,
    v9);
  if ( v9 < 0 )
    (*(void (__fastcall **)(CSpVAMaster *))(*(_QWORD *)this + 32LL))(this);
LABEL_157:
  LeaveCriticalSection(lpCriticalSection);
  SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&lpFileName);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v84);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v80);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v81);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1801bb140  push    rbp
0x1801bb142  push    rbx
0x1801bb143  push    rsi
0x1801bb144  push    rdi
0x1801bb145  push    r12
0x1801bb147  push    r13
0x1801bb149  push    r14
0x1801bb14b  push    r15
0x1801bb14d  lea     rbp, [rsp-17h]
0x1801bb152  sub     rsp, 0D8h
0x1801bb159  mov     rax, cs:__security_cookie
0x1801bb160  xor     rax, rsp
0x1801bb163  mov     [rbp+4Fh+var_50], rax
0x1801bb167  mov     r14, r9
0x1801bb16a  mov     rsi, r8
0x1801bb16d  mov     rbx, rdx
0x1801bb170  mov     rdi, rcx
0x1801bb173  mov     r15, [rbp+4Fh+arg_20]
0x1801bb177  xor     r12d, r12d
0x1801bb17a  mov     [rbp+4Fh+var_A8], r12
0x1801bb17e  mov     [rbp+4Fh+var_B0], r12
0x1801bb182  mov     [rbp+4Fh+var_98], r12
0x1801bb186  mov     [rbp+4Fh+lpFileName], r12
0x1801bb18a  mov     [rbp+4Fh+var_9C], r12d
0x1801bb18e  mov     [rbp+4Fh+var_B8], r12d
0x1801bb192  mov     [rbp+4Fh+var_A0], r12d
0x1801bb196  mov     rax, rcx
0x1801bb199  add     rcx, 30h ; '0'
0x1801bb19d  neg     rax
0x1801bb1a0  sbb     rdx, rdx
0x1801bb1a3  and     rdx, rcx
0x1801bb1a6  mov     [rbp+4Fh+var_78], rdx
0x1801bb1aa  lea     rax, [rdx+8]
0x1801bb1ae  mov     [rbp+4Fh+lpCriticalSection], rax
0x1801bb1b2  mov     rcx, rax; lpCriticalSection
0x1801bb1b5  call    cs:__imp_EnterCriticalSection
0x1801bb1bb  nop
0x1801bb1bc  cmp     [rdi+78h], r12d
0x1801bb1c0  jz      short loc_1801BB1CC
0x1801bb1c2  mov     ebx, 8000000Eh
0x1801bb1c7  jmp     loc_1801BBF1F
0x1801bb1cc  lea     r13, [rdi+0D0h]
0x1801bb1d3  cmp     [r13+0], rbx
0x1801bb1d7  jz      short loc_1801BB1E4
0x1801bb1d9  mov     rdx, rbx; struct IUnknown *
0x1801bb1dc  mov     rcx, r13; struct IUnknown **
0x1801bb1df  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1801bb1e4  lea     rcx, [rdi+0D8h]; struct IUnknown **
0x1801bb1eb  cmp     [rcx], rsi
0x1801bb1ee  jz      short loc_1801BB1F8
0x1801bb1f0  mov     rdx, rsi; struct IUnknown *
0x1801bb1f3  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1801bb1f8  lea     rax, [rdi+0E0h]
0x1801bb1ff  cmp     [rax], r14
0x1801bb202  jz      short loc_1801BB20F
0x1801bb204  mov     rdx, r14; struct IUnknown *
0x1801bb207  mov     rcx, rax; struct IUnknown **
0x1801bb20a  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1801bb20f  lea     rcx, [rdi+0E8h]; struct IUnknown **
0x1801bb216  cmp     [rcx], r15
0x1801bb219  jz      short loc_1801BB223
0x1801bb21b  mov     rdx, r15; struct IUnknown *
0x1801bb21e  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1801bb223  mov     rcx, [rdi+0B0h]; hObject
0x1801bb22a  test    rcx, rcx
0x1801bb22d  jz      short loc_1801BB23C
0x1801bb22f  call    cs:__imp_CloseHandle
0x1801bb235  mov     [rdi+0B0h], r12
0x1801bb23c  mov     rcx, [r13+0]
0x1801bb240  mov     r12d, 1
0x1801bb246  test    rcx, rcx
0x1801bb249  jnz     short loc_1801BB286
0x1801bb24b  mov     eax, 80045001h
0x1801bb250  mov     ebx, eax
0x1801bb252  mov     [rsp+110h+dwFlagsAndAttributes], eax
0x1801bb256  lea     rax, aOnecoreuapEndu_66; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801bb25d  lea     r9, aCspvamasterLoa; "CSpVAMaster::LoadEngines"
0x1801bb264  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x1801bb26b  lea     esi, [rcx+2]
0x1801bb26e  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x1801bb275  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x1801bb27a  mov     ecx, esi; int
0x1801bb27c  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1801bb281  jmp     loc_1801BBD02
0x1801bb286  mov     rax, [rcx]
0x1801bb289  lea     r8, [rbp+4Fh+lpFileName]
0x1801bb28d  lea     rdx, aVoiceactivatio_5; "VoiceActivationMetricsFile"
0x1801bb294  mov     rax, [rax+18h]
0x1801bb298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb29d  lea     r14, aCspvamasterLoa; "CSpVAMaster::LoadEngines"
0x1801bb2a4  lea     r15, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x1801bb2ab  mov     esi, 2
0x1801bb2b0  test    eax, eax
0x1801bb2b2  jns     short loc_1801BB2D8
0x1801bb2b4  mov     [rsp+110h+dwFlagsAndAttributes], eax
0x1801bb2b8  lea     rax, aOnecoreuapEndu_64; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801bb2bf  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x1801bb2c4  mov     r9, r14
0x1801bb2c7  mov     r8, r15
0x1801bb2ca  lea     rdx, aSignoredErrorF; "%SIgnored Error: function=%S, fileline="...
0x1801bb2d1  mov     ecx, esi; int
0x1801bb2d3  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1801bb2d8  mov     rcx, [r13+0]
0x1801bb2dc  mov     rax, [rcx]
0x1801bb2df  lea     r8, [rbp+4Fh+var_B8]
0x1801bb2e3  lea     rdx, aSoftwarevoicea; "SoftwareVoiceActivationInSKU"
0x1801bb2ea  mov     rax, [rax+20h]
0x1801bb2ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb2f3  mov     ebx, eax
0x1801bb2f5  test    eax, eax
0x1801bb2f7  jns     short loc_1801BB30F
0x1801bb2f9  mov     [rsp+110h+dwFlagsAndAttributes], eax
0x1801bb2fd  lea     rax, aOnecoreuapEndu_297; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801bb304  mov     r9, r14
0x1801bb307  mov     r8, r15
0x1801bb30a  jmp     loc_1801BB26E
0x1801bb30f  mov     rcx, [r13+0]
0x1801bb313  mov     rax, [rcx]
0x1801bb316  lea     r8, [rbp+4Fh+var_A0]
0x1801bb31a  lea     rdx, aHardwarevoicea_2; "HardwareVoiceActivationInSKU"
0x1801bb321  mov     rax, [rax+20h]
0x1801bb325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb32a  mov     ebx, eax
0x1801bb32c  test    eax, eax
0x1801bb32e  jns     short loc_1801BB33D
0x1801bb330  mov     [rsp+110h+dwFlagsAndAttributes], eax
0x1801bb334  lea     rax, aOnecoreuapEndu_191; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801bb33b  jmp     short loc_1801BB304
0x1801bb33d  mov     rcx, [r13+0]
0x1801bb341  mov     rax, [rcx]
0x1801bb344  lea     r8, [rbp+4Fh+var_9C]
0x1801bb348  lea     rdx, aSpeakeridon; "SpeakerIDOn"
0x1801bb34f  mov     rax, [rax+20h]
0x1801bb353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb358  test    eax, eax
0x1801bb35a  jns     short loc_1801BB380
0x1801bb35c  mov     [rsp+110h+dwFlagsAndAttributes], eax
0x1801bb360  lea     rax, aOnecoreuapEndu_55; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801bb367  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x1801bb36c  mov     r9, r14
0x1801bb36f  mov     r8, r15
0x1801bb372  lea     rdx, aSignoredErrorF; "%SIgnored Error: function=%S, fileline="...
0x1801bb379  mov     ecx, esi; int
0x1801bb37b  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1801bb380  mov     rax, [rdi]
0x1801bb383  lea     r8, [rbp+4Fh+var_A8]
0x1801bb387  lea     rdx, _GUID_bed3d04b_c290_40b1_93e3_e13447f5c676
0x1801bb38e  mov     rcx, rdi
0x1801bb391  mov     rax, [rax]
0x1801bb394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb399  mov     ebx, eax
0x1801bb39b  xor     edx, edx
0x1801bb39d  test    eax, eax
0x1801bb39f  jns     short loc_1801BB3B1
0x1801bb3a1  mov     [rsp+110h+dwFlagsAndAttributes], eax
0x1801bb3a5  lea     rax, aOnecoreuapEndu_82; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801bb3ac  jmp     loc_1801BB304
0x1801bb3b1  cmp     [rbp+4Fh+var_B8], edx
0x1801bb3b4  jz      short loc_1801BB3BE
0x1801bb3b6  cmp     [rbp+4Fh+var_A0], edx
0x1801bb3b9  mov     eax, r12d
0x1801bb3bc  jnz     short loc_1801BB3C0
0x1801bb3be  mov     eax, edx
0x1801bb3c0  mov     [rdi+108h], eax
0x1801bb3c6  mov     eax, edx
0x1801bb3c8  cmp     [rbp+4Fh+var_9C], edx
0x1801bb3cb  setnz   al
0x1801bb3ce  mov     [rdi+110h], eax
0x1801bb3d4  mov     rcx, [rbp+4Fh+lpFileName]; lpFileName
0x1801bb3d8  test    rcx, rcx
0x1801bb3db  jz      short loc_1801BB42B
0x1801bb3dd  mov     [rsp+110h+hTemplateFile], rdx; hTemplateFile
0x1801bb3e2  mov     [rsp+110h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1801bb3ea  mov     [rsp+110h+dwCreationDisposition], esi; dwCreationDisposition
0x1801bb3ee  xor     r9d, r9d; lpSecurityAttributes
0x1801bb3f1  mov     r8d, r12d; dwShareMode
0x1801bb3f4  mov     edx, 40000000h; dwDesiredAccess
0x1801bb3f9  call    cs:__imp_CreateFileW
0x1801bb3ff  mov     [rdi+0B0h], rax
0x1801bb406  inc     rax
0x1801bb409  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801bb40f  jnz     short loc_1801BB42B
0x1801bb411  call    cs:__imp_GetLastError
0x1801bb417  mov     r8d, eax
0x1801bb41a  lea     rdx, aVamasterTestCa; "VaMaster test: Cannot open file! %d\n"
0x1801bb421  mov     ecx, 8; int
0x1801bb426  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1801bb42b  lea     rcx, [rdi+10h]
0x1801bb42f  mov     rax, [rcx]
0x1801bb432  mov     rax, [rax+18h]
0x1801bb436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb43b  mov     ebx, eax
0x1801bb43d  test    eax, eax
0x1801bb43f  jns     short loc_1801BB451
0x1801bb441  mov     [rsp+110h+dwFlagsAndAttributes], eax
0x1801bb445  lea     rax, aOnecoreuapEndu_196; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801bb44c  jmp     loc_1801BB304
0x1801bb451  mov     rcx, rdi; this
0x1801bb454  call    ?GetPolicy_MockHWVAEngine@CSpVAMaster@@AEAAHXZ; CSpVAMaster::GetPolicy_MockHWVAEngine(void)
0x1801bb459  test    eax, eax
0x1801bb45b  jz      loc_1801BB50B
0x1801bb461  lea     r12, [rdi+0C0h]
0x1801bb468  mov     rdx, r12; struct IUnknown **
0x1801bb46b  mov     rcx, rdi; this
0x1801bb46e  call    ?CreateMockHWVAEngine@CSpVAMaster@@AEAAJAEAV?$CComPtr@UISpVAEngine@@@ATL@@@Z; CSpVAMaster::CreateMockHWVAEngine(ATL::CComPtr<ISpVAEngine> &)
0x1801bb473  mov     rcx, [r12]
0x1801bb477  mov     rax, [rcx]
0x1801bb47a  mov     rdx, [rbp+4Fh+var_A8]
0x1801bb47e  mov     rax, [rax+18h]
0x1801bb482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb487  mov     ebx, eax
0x1801bb489  test    eax, eax
0x1801bb48b  jns     short loc_1801BB4B6
0x1801bb48d  mov     [rsp+110h+dwFlagsAndAttributes], eax
0x1801bb491  lea     rax, aOnecoreuapEndu_273; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801bb498  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x1801bb49d  mov     r9, r14
0x1801bb4a0  mov     r8, r15
0x1801bb4a3  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x1801bb4aa  mov     ecx, esi; int
0x1801bb4ac  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1801bb4b1  jmp     loc_1801BBCFC
0x1801bb4b6  mov     rcx, [r12]
0x1801bb4ba  mov     rax, [rcx]
0x1801bb4bd  mov     rdx, [r13+0]
0x1801bb4c1  mov     rax, [rax+20h]
0x1801bb4c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb4ca  mov     ebx, eax
0x1801bb4cc  test    eax, eax
0x1801bb4ce  jns     short loc_1801BB4DD
0x1801bb4d0  mov     [rsp+110h+dwFlagsAndAttributes], eax
0x1801bb4d4  lea     rax, aOnecoreuapEndu_335; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801bb4db  jmp     short loc_1801BB498
0x1801bb4dd  mov     rcx, [r12]
0x1801bb4e1  lea     rdx, [rdi+0F8h]
0x1801bb4e8  mov     rax, [rcx]
0x1801bb4eb  mov     rax, [rax+58h]
0x1801bb4ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb4f4  mov     ebx, eax
0x1801bb4f6  test    eax, eax
0x1801bb4f8  jns     loc_1801BB621
0x1801bb4fe  mov     [rsp+110h+dwFlagsAndAttributes], eax
0x1801bb502  lea     rax, aOnecoreuapEndu_22; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801bb509  jmp     short loc_1801BB498
0x1801bb50b  cmp     qword ptr [rdi+70h], 0
0x1801bb510  jz      loc_1801BB63E
0x1801bb516  lea     rcx, [rdi+10h]
0x1801bb51a  mov     rax, [rcx]
0x1801bb51d  lea     r9, [rbp+4Fh+var_B0]
0x1801bb521  xor     r8d, r8d
0x1801bb524  lea     edx, [r8+4]
0x1801bb528  mov     rax, [rax+28h]
0x1801bb52c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb531  mov     ebx, eax
0x1801bb533  test    eax, eax
0x1801bb535  jns     short loc_1801BB547
0x1801bb537  mov     [rsp+110h+dwFlagsAndAttributes], eax
0x1801bb53b  lea     rax, aOnecoreuapEndu_111; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801bb542  jmp     loc_1801BB304
0x1801bb547  lea     r12, [rdi+0C0h]
0x1801bb54e  mov     rdx, r12
0x1801bb551  mov     rcx, [rbp+4Fh+var_B0]
0x1801bb555  call    ??$SpCreateObjectFromToken@UISpVAEngine@@@@YAJPEAUISpObjectToken@@PEAPEAUISpVAEngine@@PEAUIUnknown@@K@Z; SpCreateObjectFromToken<ISpVAEngine>(ISpObjectToken *,ISpVAEngine * *,IUnknown *,ulong)
0x1801bb55a  mov     ebx, eax
0x1801bb55c  test    eax, eax
0x1801bb55e  jns     short loc_1801BB570
0x1801bb560  mov     [rsp+110h+dwFlagsAndAttributes], eax
0x1801bb564  lea     rax, aOnecoreuapEndu_59; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801bb56b  jmp     loc_1801BB498
0x1801bb570  mov     rcx, [r12]
0x1801bb574  mov     rax, [rcx]
0x1801bb577  lea     r8, [rbp+4Fh+var_98]
0x1801bb57b  lea     rdx, _GUID_5b559f40_e952_11d2_bb91_00c04f8ee6c0
0x1801bb582  mov     rax, [rax]
0x1801bb585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb58a  mov     ebx, eax
0x1801bb58c  test    eax, eax
0x1801bb58e  jns     short loc_1801BB5A0
0x1801bb590  mov     [rsp+110h+dwFlagsAndAttributes], eax
0x1801bb594  lea     rax, aOnecoreuapEndu_49; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801bb59b  jmp     loc_1801BB498
0x1801bb5a0  mov     rcx, [r12]
0x1801bb5a4  mov     rax, [rcx]
0x1801bb5a7  mov     rdx, [rbp+4Fh+var_A8]
0x1801bb5ab  mov     rax, [rax+18h]
0x1801bb5af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb5b4  mov     ebx, eax
0x1801bb5b6  test    eax, eax
0x1801bb5b8  jns     short loc_1801BB5CA
0x1801bb5ba  mov     [rsp+110h+dwFlagsAndAttributes], eax
0x1801bb5be  lea     rax, aOnecoreuapEndu_304; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801bb5c5  jmp     loc_1801BB498
0x1801bb5ca  mov     rcx, [r12]
0x1801bb5ce  mov     rax, [rcx]
0x1801bb5d1  mov     rdx, [r13+0]
0x1801bb5d5  mov     rax, [rax+20h]
0x1801bb5d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb5de  mov     ebx, eax
0x1801bb5e0  test    eax, eax
0x1801bb5e2  jns     short loc_1801BB5F4
  ... truncated ...
```
