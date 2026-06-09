# HTTP_USER_REQUEST::OnSendingRequest(void)

- ea: `0x180031ed0`
- end: `0x180032c72`
- name: `?OnSendingRequest@HTTP_USER_REQUEST@@EEAAXXZ`
- size: `3490`
- prototype: `void __fastcall(HTTP_USER_REQUEST *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800252ac`
- `0x180031ed0`
- `0x180032c78`
- `0x180032cac`
- `0x18004a21c`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800b4d48`
- `0x1800b73bc`
- `0x1800cf58c`
- `0x1800db704`
- `0x1800dd064`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031f29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032148`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032558`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031f29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032148`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032558`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031f7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800322bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800325e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032c67`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031f7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800322bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800325e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032c67`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800326e0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800326e0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800326f2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800326f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032af8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032af8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032b06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032b06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800326aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800326aa`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180032a11`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180032b29`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180032a11`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180032b29`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800327e8`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800327e8`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800325ac`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800325ac`
- `ntdll!RtlNtStatusToDosError` at `0x180032be5`
- `ntdll!RtlNtStatusToDosError` at `0x180032be5`
- `ntdll!EtwEventActivityIdControl` at `0x180032429`
- `ntdll!EtwEventActivityIdControl` at `0x180032465`
- `ntdll!EtwEventActivityIdControl` at `0x1800324d2`
- `ntdll!EtwEventActivityIdControl` at `0x180032429`
- `ntdll!EtwEventActivityIdControl` at `0x180032465`
- `ntdll!EtwEventActivityIdControl` at `0x1800324d2`
- `CRYPT32!CertFreeCertificateContext` at `0x1800329f1`
- `CRYPT32!CertFreeCertificateContext` at `0x1800329f1`
- `CRYPT32!CertFreeCertificateChain` at `0x1800329e6`
- `CRYPT32!CertFreeCertificateChain` at `0x1800329e6`
- `webio!__imp_WebQueryHttpRequestOption` at `0x180032038`
- `webio!__imp_WebQueryHttpRequestOption` at `0x18003266f`
- `webio!__imp_WebQueryHttpRequestOption` at `0x180032756`
- `webio!__imp_WebQueryHttpRequestOption` at `0x18003279b`
- `webio!__imp_WebQueryHttpRequestOption` at `0x1800327ce`
- `webio!__imp_WebQueryHttpRequestOption` at `0x18003281c`
- `webio!__imp_WebQueryHttpRequestOption` at `0x180032888`
- `webio!__imp_WebQueryHttpRequestOption` at `0x1800328f2`
- `webio!__imp_WebQueryHttpRequestOption` at `0x180032038`
- `webio!__imp_WebQueryHttpRequestOption` at `0x18003266f`
- `webio!__imp_WebQueryHttpRequestOption` at `0x180032756`
- `webio!__imp_WebQueryHttpRequestOption` at `0x18003279b`
- `webio!__imp_WebQueryHttpRequestOption` at `0x1800327ce`
- `webio!__imp_WebQueryHttpRequestOption` at `0x18003281c`
- `webio!__imp_WebQueryHttpRequestOption` at `0x180032888`
- `webio!__imp_WebQueryHttpRequestOption` at `0x1800328f2`
- `webio!__imp_WebSetHttpRequestHeader` at `0x18003253e`
- `webio!__imp_WebSetHttpRequestHeader` at `0x1800325ca`
- `webio!__imp_WebSetHttpRequestHeader` at `0x18003253e`
- `webio!__imp_WebSetHttpRequestHeader` at `0x1800325ca`

## string_xrefs

- `0x1800322d9`: `Sec-Token-Binding`

## pseudocode

```c
void __fastcall HTTP_USER_REQUEST::OnSendingRequest(HTTP_USER_REQUEST *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // r14
  __int128 v5; // xmm6
  HGLOBAL v6; // r15
  int v7; // r12d
  __int64 v8; // r13
  __int64 v9; // rsi
  int v10; // esi
  const CERT_CONTEXT *v11; // rcx
  const CERT_CHAIN_CONTEXT *v12; // rcx
  void *v13; // rcx
  char *v14; // rcx
  _BYTE *v15; // rax
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  _QWORD *v25; // rdx
  __int128 v26; // xmm1
  __int64 v27; // rax
  __int64 v28; // rcx
  int *v29; // rax
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  WEBIO_REQUEST *v38; // rsi
  __int64 v39; // rax
  __int64 v40; // rbx
  unsigned int v41; // r8d
  signed int v42; // ebx
  __int64 v43; // rcx
  _BYTE *v44; // rax
  _BYTE *v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rcx
  char *v48; // rax
  int v49; // eax
  bool v50; // sf
  int v51; // eax
  bool v52; // sf
  struct _LIST_ENTRY *Flink; // rdx
  __int64 v54; // rcx
  void (__fastcall *v55)(__int64, struct _LIST_ENTRY *, __int64, _QWORD, _DWORD); // rax
  int v56; // eax
  bool v57; // sf
  HTTP_USER_REQUEST *v58; // rbx
  __int64 v59; // r14
  __int64 v60; // rbx
  __int64 v61; // rdi
  unsigned int v62; // eax
  ULONG v63; // esi
  struct _RTL_CRITICAL_SECTION *v64; // r15
  unsigned int i; // ebx
  unsigned int v66; // eax
  __int64 v67; // rcx
  unsigned int v68; // eax
  int v69; // ebx
  struct _LIST_ENTRY *Blink; // rcx
  __int64 v71; // rcx
  unsigned int v72; // r14d
  __int64 v73; // rcx
  __int64 v74; // rcx
  unsigned int v75; // eax
  HGLOBAL v76; // r15
  unsigned int v77; // eax
  int v78; // ecx
  HGLOBAL v79; // rax
  __int64 v80; // rcx
  unsigned int HttpRequestOption; // eax
  unsigned int v82; // eax
  _BYTE *v83; // rcx
  __int64 v84; // rdx
  int *v85; // rax
  __int128 v86; // xmm0
  __int128 v87; // xmm1
  __int128 v88; // xmm0
  __int128 v89; // xmm1
  __int128 v90; // xmm0
  __int128 v91; // xmm1
  __int128 v92; // xmm0
  __int128 v93; // xmm1
  __int128 v94; // xmm0
  __int128 v95; // xmm1
  __int64 v96; // rax
  int TokenBindings; // eax
  void *v98; // rsi
  int v99; // eax
  int v100; // eax
  HANDLE ProcessHeap; // rax
  __int64 v102; // rdx
  int v103; // r8d
  struct _RTL_CRITICAL_SECTION_DEBUG *v104; // [rsp+40h] [rbp-C0h]
  struct _RTL_CRITICAL_SECTION_DEBUG *v105; // [rsp+40h] [rbp-C0h]
  int v106; // [rsp+48h] [rbp-B8h]
  __int128 v107; // [rsp+50h] [rbp-B0h]
  _BYTE v108[688]; // [rsp+70h] [rbp-90h] BYREF
  SIZE_T dwBytes; // [rsp+320h] [rbp+220h] BYREF
  HTTP_USER_REQUEST *v110[2]; // [rsp+328h] [rbp+228h] BYREF
  unsigned __int16 v111[2]; // [rsp+338h] [rbp+238h] BYREF
  __int128 v112; // [rsp+340h] [rbp+240h] BYREF
  _BYTE v113[28]; // [rsp+350h] [rbp+250h] BYREF
  __int128 v114; // [rsp+370h] [rbp+270h] BYREF
  _OWORD v115[16]; // [rsp+380h] [rbp+280h] BYREF
  int v116; // [rsp+480h] [rbp+380h] BYREF
  char v117[4]; // [rsp+484h] [rbp+384h] BYREF
  __int128 v118; // [rsp+488h] [rbp+388h]
  __int128 v119; // [rsp+498h] [rbp+398h]
  __int128 v120; // [rsp+4A8h] [rbp+3A8h]
  __int128 v121; // [rsp+4B8h] [rbp+3B8h]
  __int128 v122; // [rsp+4C8h] [rbp+3C8h]
  __int128 v123; // [rsp+4D8h] [rbp+3D8h]
  __int128 v124; // [rsp+4E8h] [rbp+3E8h]
  __int128 v125; // [rsp+4F8h] [rbp+3F8h]
  __int128 v126; // [rsp+508h] [rbp+408h]
  __int128 v127; // [rsp+518h] [rbp+418h]
  __int128 v128; // [rsp+528h] [rbp+428h]
  __int128 v129; // [rsp+538h] [rbp+438h]
  __int128 v130; // [rsp+548h] [rbp+448h]
  __int128 v131; // [rsp+558h] [rbp+458h]
  __int128 v132; // [rsp+568h] [rbp+468h]
  __int128 v133; // [rsp+578h] [rbp+478h]
  char v134[32]; // [rsp+730h] [rbp+630h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 24);
  v110[0] = (HTTP_USER_REQUEST *)((char *)this - 24);
  if ( (xmmword_180107A60 & 2) != 0 )
    WPP_SF_q(1025, 62, WPP_29ecff532d3a35783d73db4432e82274_Traceguids);
  else
    v110[0] = (HTTP_USER_REQUEST *)((char *)this - 24);
  v3 = v2 + 6;
  EnterCriticalSection(v2 + 6);
  if ( !HIDWORD(v2[1].OwningThread) )
  {
    DebugInfo = v2[7].DebugInfo;
    v104 = DebugInfo;
    if ( DebugInfo )
    {
      (**(void (__fastcall ***)(PRTL_CRITICAL_SECTION_DEBUG))&DebugInfo->Type)(DebugInfo);
      LeaveCriticalSection(v2 + 6);
      v5 = 0;
      v107 = 0;
      *(_QWORD *)&v112 = 0;
      HIDWORD(v107) = 0;
      *(_QWORD *)&v114 = 0;
      memset_0(v108, 0, 0x2A8u);
      v6 = 0;
      v7 = 0;
      v106 = 0;
      v8 = 5;
      v9 = *(_QWORD *)&DebugInfo[2].EntryCount;
      if ( *(_DWORD *)(*((_QWORD *)this + 1) + 416LL) == 2 )
      {
        v71 = *(_QWORD *)(v9 + 184);
        v72 = 8;
        *(_QWORD *)v134 = 0;
        if ( (unsigned int)WebQueryHttpRequestOption(v71, 19, &v112, 8, v134) )
          *(_QWORD *)&v112 = 0;
        else
          v106 = 1;
        *(_QWORD *)&v114 = 0;
        v73 = *(_QWORD *)(v9 + 184);
        *(_QWORD *)v134 = 0;
        if ( (unsigned int)WebQueryHttpRequestOption(v73, 53, &v114, 8, v134) )
          *(_QWORD *)&v114 = 0;
        v74 = *(_QWORD *)(v9 + 184);
        dwBytes = 0;
        v75 = WebQueryHttpRequestOption(v74, 4, 0, 0, &dwBytes);
        if ( v75 == 234 )
        {
          v76 = GlobalAlloc(0, dwBytes);
          if ( v76 )
          {
            v77 = WebQueryHttpRequestOption(*(_QWORD *)(v9 + 184), 4, v76, dwBytes, &dwBytes);
            v72 = v77;
            if ( v77 )
            {
              v72 = SET_WINHTTP_ERROR_FROM_WIN32(v77);
              GlobalFree(v76);
              v79 = 0;
              v78 = 0;
            }
            else
            {
              v78 = dwBytes;
              v79 = v76;
            }
          }
          else
          {
            v79 = 0;
            v78 = 0;
          }
        }
        else
        {
          v72 = SET_WINHTTP_ERROR_FROM_WIN32(v75);
          v78 = 0;
          v79 = 0;
        }
        *(_QWORD *)v134 = 0;
        *(_OWORD *)v113 = 0;
        if ( !v72 )
          v7 = v78;
        v80 = *(_QWORD *)(v9 + 184);
        v6 = 0;
        *(_OWORD *)&v113[12] = 0;
        if ( !v72 )
          v6 = v79;
        HttpRequestOption = WebQueryHttpRequestOption(v80, 15, v113, 28, v134);
        if ( HttpRequestOption )
        {
          SET_WINHTTP_ERROR_FROM_WIN32(HttpRequestOption);
        }
        else
        {
          v5 = *(_OWORD *)&v113[12];
          v107 = *(_OWORD *)v113;
          HIDWORD(v107) = *(_DWORD *)&v113[12];
        }
        *(_QWORD *)v134 = 0;
        memset_0(&v116, 0, 0x2A8u);
        v82 = WebQueryHttpRequestOption(*(_QWORD *)(v9 + 184), 57, &v116, 680, v134);
        if ( v82 )
        {
          SET_WINHTTP_ERROR_FROM_WIN32(v82);
        }
        else
        {
          v83 = v108;
          v84 = 5;
          v85 = &v116;
          do
          {
            v83 += 128;
            v86 = *(_OWORD *)v85;
            v87 = *((_OWORD *)v85 + 1);
            v85 += 32;
            *((_OWORD *)v83 - 8) = v86;
            v88 = *((_OWORD *)v85 - 6);
            *((_OWORD *)v83 - 7) = v87;
            v89 = *((_OWORD *)v85 - 5);
            *((_OWORD *)v83 - 6) = v88;
            v90 = *((_OWORD *)v85 - 4);
            *((_OWORD *)v83 - 5) = v89;
            v91 = *((_OWORD *)v85 - 3);
            *((_OWORD *)v83 - 4) = v90;
            v92 = *((_OWORD *)v85 - 2);
            *((_OWORD *)v83 - 3) = v91;
            v93 = *((_OWORD *)v85 - 1);
            *((_OWORD *)v83 - 2) = v92;
            *((_OWORD *)v83 - 1) = v93;
            --v84;
          }
          while ( v84 );
          v94 = *(_OWORD *)v85;
          v95 = *((_OWORD *)v85 + 1);
          v96 = *((_QWORD *)v85 + 4);
          *(_OWORD *)v83 = v94;
          *((_OWORD *)v83 + 1) = v95;
          *((_QWORD *)v83 + 4) = v96;
        }
        DebugInfo = v104;
      }
      *(_QWORD *)v134 = 0;
      memset_0(v115, 0, sizeof(v115));
      memset_0(v117, 0, 0x104u);
      if ( (unsigned int)WebQueryHttpRequestOption(*(_QWORD *)(v9 + 184), 22, v115, 256, v134) )
      {
        memset_0(&v116, 0, 0x108u);
      }
      else
      {
        v118 = v115[0];
        v116 = 264;
        v119 = v115[1];
        v120 = v115[2];
        v121 = v115[3];
        v122 = v115[4];
        v123 = v115[5];
        v124 = v115[6];
        v125 = v115[7];
        v126 = v115[8];
        v127 = v115[9];
        v128 = v115[10];
        v129 = v115[11];
        v130 = v115[12];
        v131 = v115[13];
        v132 = v115[14];
        v133 = v115[15];
      }
      if ( (*(_BYTE *)(*((_QWORD *)this + 1) + 228LL) & 3) != 0 )
      {
        v67 = *(_QWORD *)(v9 + 184);
        *(_DWORD *)v111 = 0;
        *(_QWORD *)v134 = 0;
        v68 = WebQueryHttpRequestOption(v67, 41, v111, 4, v134);
        if ( v68 )
        {
          v10 = 0;
          SET_WINHTTP_ERROR_FROM_WIN32(v68);
        }
        else
        {
          v10 = *(_DWORD *)v111;
        }
      }
      else
      {
        v10 = 0;
      }
      EnterCriticalSection(v3);
      v11 = (const CERT_CONTEXT *)*((_QWORD *)this + 1323);
      if ( v11 )
        CertFreeCertificateContext(v11);
      v12 = (const CERT_CHAIN_CONTEXT *)*((_QWORD *)this + 1324);
      *((_QWORD *)this + 1323) = v112;
      if ( v12 )
        CertFreeCertificateChain(v12);
      v13 = (void *)*((_QWORD *)this + 1321);
      *((_QWORD *)this + 1324) = v114;
      if ( v13 )
        GlobalFree(v13);
      *((_QWORD *)this + 1321) = v6;
      v14 = (char *)this + 9872;
      *((_DWORD *)this + 2644) = v7;
      v15 = v108;
      *(_OWORD *)((char *)this + 9844) = v107;
      *((_OWORD *)this + 616) = v5;
      do
      {
        v14 += 128;
        v16 = *(_OWORD *)v15;
        v17 = *((_OWORD *)v15 + 1);
        v15 += 128;
        *((_OWORD *)v14 - 8) = v16;
        v18 = *((_OWORD *)v15 - 6);
        *((_OWORD *)v14 - 7) = v17;
        v19 = *((_OWORD *)v15 - 5);
        *((_OWORD *)v14 - 6) = v18;
        v20 = *((_OWORD *)v15 - 4);
        *((_OWORD *)v14 - 5) = v19;
        v21 = *((_OWORD *)v15 - 3);
        *((_OWORD *)v14 - 4) = v20;
        v22 = *((_OWORD *)v15 - 2);
        *((_OWORD *)v14 - 3) = v21;
        v23 = *((_OWORD *)v15 - 1);
        *((_OWORD *)v14 - 2) = v22;
        *((_OWORD *)v14 - 1) = v23;
        --v8;
      }
      while ( v8 );
      v24 = *(_OWORD *)v15;
      v25 = (_QWORD *)((char *)this + 8760);
      v26 = *((_OWORD *)v15 + 1);
      v27 = *((_QWORD *)v15 + 4);
      *(_OWORD *)v14 = v24;
      *((_OWORD *)v14 + 1) = v26;
      *((_QWORD *)v14 + 4) = v27;
      v28 = 2;
      *((_DWORD *)this + 2638) = v106;
      v29 = &v116;
      do
      {
        v25 += 16;
        v30 = *(_OWORD *)v29;
        v31 = *((_OWORD *)v29 + 1);
        v29 += 32;
        *((_OWORD *)v25 - 8) = v30;
        v32 = *((_OWORD *)v29 - 6);
        *((_OWORD *)v25 - 7) = v31;
        v33 = *((_OWORD *)v29 - 5);
        *((_OWORD *)v25 - 6) = v32;
        v34 = *((_OWORD *)v29 - 4);
        *((_OWORD *)v25 - 5) = v33;
        v35 = *((_OWORD *)v29 - 3);
        *((_OWORD *)v25 - 4) = v34;
        v36 = *((_OWORD *)v29 - 2);
        *((_OWORD *)v25 - 3) = v35;
        v37 = *((_OWORD *)v29 - 1);
        *((_OWORD *)v25 - 2) = v36;
        *((_OWORD *)v25 - 1) = v37;
        --v28;
      }
      while ( v28 );
      *v25 = *(_QWORD *)v29;
      *((_DWORD *)this + 2665) = v10;
      LeaveCriticalSection(v3);
      *((_DWORD *)this + 2460) = 1;
      v38 = *(WEBIO_REQUEST **)&DebugInfo[2].EntryCount;
      v39 = *((_QWORD *)this + 1);
      strcpy(v134, "Sec-Token-Binding");
      DWORD1(v112) = 0;
      dwBytes = 0;
      v40 = *(_QWORD *)(v39 + 24);
      *(_DWORD *)v111 = 0;
      if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40) != 1952804425 )
        v40 = *(_QWORD *)(v40 + 24);
      if ( !g_TokenBindingEnabled || !*(_DWORD *)(v40 + 768) )
      {
        v42 = 0;
        goto LABEL_25;
      }
      CWebIORequestHeadersShim::RemoveAll((CWebIORequestHeadersShim *)(*((_QWORD *)this + 1) + 680LL), v134, v41);
      v102 = *((_QWORD *)this + 1);
      v103 = *(_DWORD *)(v102 + 1024);
      if ( v103 )
      {
        TokenBindings = WEBIO_REQUEST::GenerateTokenBindings(
                          v38,
                          *(const unsigned __int16 **)(v102 + 1016),
                          v103 + 1,
                          (char **)&dwBytes,
                          (unsigned int *)v111);
        v42 = TokenBindings;
        if ( TokenBindings > 0 )
          v42 = (unsigned __int16)TokenBindings | 0x80070000;
        if ( v42 < 0 )
        {
          v98 = (void *)dwBytes;
          DWORD1(v112) = 13938;
          goto LABEL_108;
        }
      }
      else
      {
        v99 = WEBIO_REQUEST::GenerateTokenBindings(v38, 0, 0, (char **)&dwBytes, (unsigned int *)v111);
        v42 = v99;
        if ( v99 > 0 )
          v42 = (unsigned __int16)v99 | 0x80070000;
        if ( v42 < 0 )
        {
          v98 = (void *)dwBytes;
          DWORD1(v112) = 13946;
LABEL_108:
          if ( v98 )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v98);
          }
LABEL_25:
          if ( (v42 & 0x1FFF0000) == 0xC0000 )
          {
            v63 = (unsigned __int16)v42;
          }
          else
          {
            if ( v42 >= 0 )
              goto LABEL_27;
            if ( (v42 & 0x1FFF0000) == 0x70000 )
            {
              v63 = (unsigned __int16)v42;
              if ( !(_WORD)v42 )
                v63 = 317;
              goto LABEL_92;
            }
            if ( (v42 & 0x10000000) != 0 )
            {
              v63 = RtlNtStatusToDosError(v42 & 0xEFFFFFFF);
              if ( v63 )
              {
                if ( v63 != 317 )
                {
LABEL_92:
                  if ( (xmmword_180107A50 & 2) != 0 )
                    WPP_SF_qD(513, 63, WPP_29ecff532d3a35783d73db4432e82274_Traceguids, v110[0]);
                  goto LABEL_58;
                }
              }
            }
            v63 = v42;
          }
          if ( !v63 )
          {
LABEL_27:
            *((_DWORD *)this + 51) = 1;
            if ( ((__int64)DebugInfo[1].CriticalSection & 0x30) != 0 )
            {
              memset(v113, 0, 20);
              if ( !DebugInfo->Flags
                || (v69 = *(_DWORD *)&DebugInfo->CreatorBackTraceIndexHigh, GetCurrentThreadId() == v69) )
              {
                v43 = 16;
                v105 = DebugInfo;
                v44 = v113;
                do
                {
                  *v44++ = 0;
                  --v43;
                }
                while ( v43 );
                *(_DWORD *)&v113[16] = 0;
                v45 = v113;
                v114 = 0;
                v46 = 16;
                *(_OWORD *)v134 = 0;
                do
                {
                  *v45++ = 0;
                  --v46;
                }
                while ( v46 );
                v112 = 0;
                v47 = 16;
                v48 = v134;
                do
                {
                  *v48++ = 0;
                  --v47;
                }
                while ( v47 );
                v49 = EtwEventActivityIdControl(1, &v112);
                v50 = v49 < 0;
                if ( v49 > 0 )
                  v50 = 1;
                if ( v50 )
                  DWORD1(v112) = 128;
                else
                  *(_OWORD *)v134 = v112;
                DWORD1(v112) = 0;
                v51 = EtwEventActivityIdControl(2, &WinHttpEtwNullActivityId);
                v52 = v51 < 0;
                if ( v51 > 0 )
                  v52 = 1;
                if ( v52 )
                  DWORD1(v112) = 144;
                Flink = DebugInfo[1].ProcessLocksList.Flink;
                v54 = *((_QWORD *)this + 1);
                v55 = *(void (__fastcall **)(__int64, struct _LIST_ENTRY *, __int64, _QWORD, _DWORD))&DebugInfo[1].Type;
                *(_OWORD *)v113 = *(_OWORD *)v134;
                *(_DWORD *)&v113[16] = 1;
                v55(v54, Flink, 16, 0, 0);
                if ( *(_DWORD *)&v113[16] )
                {
                  DWORD1(v112) = 0;
                  v56 = EtwEventActivityIdControl(2, v113);
                  v57 = v56 < 0;
                  if ( v56 > 0 )
                    v57 = 1;
                  if ( v57 )
                    DWORD1(v112) = 144;
                }
                goto LABEL_48;
              }
              Blink = DebugInfo[1].ProcessLocksList.Blink;
              *(_DWORD *)&DebugInfo[2].CreatorBackTraceIndexHigh = 1;
              *(_DWORD *)&DebugInfo[3].Type = 16;
              DebugInfo[3].CriticalSection = 0;
              LODWORD(DebugInfo[3].ProcessLocksList.Flink) = 0;
              SetEvent(Blink);
              WaitForSingleObjectEx(*(HANDLE *)&DebugInfo[1].EntryCount, 0xFFFFFFFF, 0);
              *(_QWORD *)&DebugInfo[2].CreatorBackTraceIndexHigh = 0;
              DebugInfo[3].CriticalSection = 0;
              LODWORD(DebugInfo[3].ProcessLocksList.Flink) = 0;
            }
            v105 = DebugInfo;
LABEL_48:
            v58 = v110[0];
            if ( HTTP_USER_REQUEST::_IndicateGlobalCallback(
                   v110[0],
                   1u,
                   *(const unsigned __int16 **)(*(_QWORD *)&DebugInfo[2].EntryCount + 168LL)) )
            {
              v63 = 12191;
              if ( (xmmword_180107A50 & 2) != 0 )
                WPP_SF_qDD(513, 64, WPP_29ecff532d3a35783d73db4432e82274_Traceguids, v58);
              goto LABEL_126;
            }
            v59 = *(_QWORD *)&DebugInfo[2].EntryCount;
            v60 = *((_QWORD *)this + 1);
            *(_OWORD *)v110 = 0;
            v61 = *(_QWORD *)(v60 + 680);
            v62 = WebSetHttpRequestHeader(*(_QWORD *)(v59 + 184), 0, 0);
            v63 = v62;
            if ( v62 )
            {
              v63 = SET_WINHTTP_ERROR_FROM_WIN32(v62);
            }
            else
            {
              v64 = (struct _RTL_CRITICAL_SECTION *)(v60 + 712);
              EnterCriticalSection((LPCRITICAL_SECTION)(v60 + 712));
              for ( i = 0; i < *(_DWORD *)(v61 + 8); ++i )
              {
                v110[0] = *(HTTP_USER_REQUEST **)(*(_QWORD *)v61 + 16LL * i);
                v110[1] = *(HTTP_USER_REQUEST **)(*(_QWORD *)v61 + 16LL * i + 8);
                if ( CompareStringA(0x7Fu, 1u, (PCNZCH)v110[0], -1, "Content-Length", -1) != 2 )
                {
                  v66 = WebSetHttpRequestHeader(*(_QWORD *)(v59 + 184), 2, v110);
                  v63 = v66;
                  if ( v66 )
                  {
                    v63 = SET_WINHTTP_ERROR_FROM_WIN32(v66);
                    break;
                  }
                }
              }
              LeaveCriticalSection(v64);
            }
            DebugInfo = v105;
LABEL_58:
            if ( !v63 )
            {
LABEL_59:
              (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)&DebugInfo->Type + 8LL))(DebugInfo);
              return;
            }
LABEL_126:
            WEBIO_REQUEST::CancelRequest(*(WEBIO_REQUEST **)&DebugInfo[2].EntryCount, v63);
            goto LABEL_59;
          }
          goto LABEL_92;
        }
      }
      v98 = (void *)dwBytes;
      if ( *(_DWORD *)v111 )
      {
        v100 = HTTP_REQUEST_HANDLE_OBJECT::ModifyRequestHeader(
                 *((HTTP_REQUEST_HANDLE_OBJECT **)this + 1),
                 v134,
                 0x11u,
                 (const char *)dwBytes,
                 v111[0],
                 0,
                 0xA0000000);
        v42 = v100;
        if ( v100 > 0 )
          v42 = (unsigned __int16)v100 | 0x80070000;
        if ( v42 < 0 )
          DWORD1(v112) = 13964;
      }
      goto LABEL_108;
    }
  }
  LeaveCriticalSection(v2 + 6);
}

```

## disassembly

```asm
0x180031ed0  push    rbp
0x180031ed2  push    rbx
0x180031ed3  push    rsi
0x180031ed4  push    rdi
0x180031ed5  lea     rbp, [rsp-678h]
0x180031edd  sub     rsp, 778h
0x180031ee4  mov     rax, cs:__security_cookie
0x180031eeb  xor     rax, rsp
0x180031eee  mov     [rbp+690h+var_40], rax
0x180031ef5  mov     rdi, rcx
0x180031ef8  test    byte ptr cs:xmmword_180107A60, 2
0x180031eff  lea     rsi, [rcx-18h]
0x180031f03  mov     [rbp+690h+var_468], rsi
0x180031f0a  jnz     loc_180032688
0x180031f10  mov     [rbp+690h+var_468], rsi
0x180031f17  lea     rbx, [rsi+0F0h]
0x180031f1e  mov     [rsp+790h+arg_18], r14
0x180031f26  mov     rcx, rbx; lpCriticalSection
0x180031f29  call    cs:__imp_EnterCriticalSection
0x180031f2f  cmp     dword ptr [rsi+3Ch], 0
0x180031f33  jnz     loc_180032C64
0x180031f39  mov     r14, [rsi+118h]
0x180031f40  mov     [rsp+790h+var_750], r14
0x180031f45  test    r14, r14
0x180031f48  jz      loc_180032C64
0x180031f4e  mov     rax, [r14]
0x180031f51  mov     rcx, r14
0x180031f54  mov     [rsp+790h+arg_8], r12
0x180031f5c  mov     [rsp+790h+arg_10], r13
0x180031f64  mov     [rsp+790h+var_20], r15
0x180031f6c  mov     rax, [rax]
0x180031f6f  movaps  [rsp+790h+var_30], xmm6
0x180031f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f7c  mov     rcx, rbx; lpCriticalSection
0x180031f7f  call    cs:__imp_LeaveCriticalSection
0x180031f85  xorps   xmm6, xmm6
0x180031f88  lea     rcx, [rsp+790h+var_720]; void *
0x180031f8d  xor     esi, esi
0x180031f8f  xor     edx, edx; Val
0x180031f91  movups  [rsp+790h+var_740], xmm6
0x180031f96  mov     r8d, 2A8h; Size
0x180031f9c  mov     qword ptr [rbp+690h+var_450], rsi
0x180031fa3  movups  [rsp+790h+var_740+0Ch], xmm6
0x180031fa8  mov     qword ptr [rbp+690h+var_420], rsi
0x180031faf  call    memset_0
0x180031fb4  mov     rax, [rdi+8]
0x180031fb8  mov     r15d, esi
0x180031fbb  mov     r12d, esi
0x180031fbe  mov     [rsp+790h+var_748], esi
0x180031fc2  mov     [rsp+790h+var_744], esi
0x180031fc6  mov     r13d, 5
0x180031fcc  mov     rsi, [r14+80h]
0x180031fd3  cmp     dword ptr [rax+1A0h], 2
0x180031fda  jz      loc_180032727
0x180031fe0  xor     edx, edx; Val
0x180031fe2  mov     qword ptr [rbp+690h+var_60], 0
0x180031fed  mov     r8d, 100h; Size
0x180031ff3  lea     rcx, [rbp+690h+var_410]; void *
0x180031ffa  call    memset_0
0x180031fff  xor     edx, edx; Val
0x180032001  lea     rcx, [rbp+690h+var_30C]; void *
0x180032008  mov     r8d, 104h; Size
0x18003200e  call    memset_0
0x180032013  mov     rcx, [rsi+0B8h]
0x18003201a  lea     rax, [rbp+690h+var_60]
0x180032021  mov     r9d, 100h
0x180032027  mov     [rsp+790h+lpString2], rax
0x18003202c  lea     r8, [rbp+690h+var_410]
0x180032033  mov     edx, 16h
0x180032038  call    cs:__imp_WebQueryHttpRequestOption
0x18003203e  test    eax, eax
0x180032040  jnz     loc_180032B52
0x180032046  movaps  xmm0, [rbp+690h+var_410]
0x18003204d  movaps  xmm1, [rbp+690h+var_400]
0x180032054  movups  [rbp+690h+var_308], xmm0
0x18003205b  mov     [rbp+690h+var_310], 108h
0x180032065  movaps  xmm0, [rbp+690h+var_3F0]
0x18003206c  movups  [rbp+690h+var_2F8], xmm1
0x180032073  movaps  xmm1, [rbp+690h+var_3E0]
0x18003207a  movups  [rbp+690h+var_2E8], xmm0
0x180032081  movaps  xmm0, [rbp+690h+var_3D0]
0x180032088  movups  [rbp+690h+var_2D8], xmm1
0x18003208f  movaps  xmm1, [rbp+690h+var_3C0]
0x180032096  movups  [rbp+690h+var_2C8], xmm0
0x18003209d  movaps  xmm0, [rbp+690h+var_3B0]
0x1800320a4  movups  [rbp+690h+var_2B8], xmm1
0x1800320ab  movaps  xmm1, [rbp+690h+var_3A0]
0x1800320b2  movups  [rbp+690h+var_2A8], xmm0
0x1800320b9  movaps  xmm0, [rbp+690h+var_390]
0x1800320c0  movups  [rbp+690h+var_298], xmm1
0x1800320c7  movaps  xmm1, [rbp+690h+var_380]
0x1800320ce  movups  [rbp+690h+var_288], xmm0
0x1800320d5  movaps  xmm0, [rbp+690h+var_370]
0x1800320dc  movups  [rbp+690h+var_278], xmm1
0x1800320e3  movaps  xmm1, [rbp+690h+var_360]
0x1800320ea  movups  [rbp+690h+var_268], xmm0
0x1800320f1  movaps  xmm0, [rbp+690h+var_350]
0x1800320f8  movups  [rbp+690h+var_258], xmm1
0x1800320ff  movaps  xmm1, [rbp+690h+var_340]
0x180032106  movups  [rbp+690h+var_248], xmm0
0x18003210d  movaps  xmm0, [rbp+690h+var_330]
0x180032114  movups  [rbp+690h+var_238], xmm1
0x18003211b  movaps  xmm1, [rbp+690h+var_320]
0x180032122  movups  [rbp+690h+var_228], xmm0
0x180032129  movups  [rbp+690h+var_218], xmm1
0x180032130  mov     rax, [rdi+8]
0x180032134  test    byte ptr [rax+0E4h], 3
0x18003213b  jnz     loc_18003263B
0x180032141  mov     esi, [rsp+790h+var_744]
0x180032145  mov     rcx, rbx; lpCriticalSection
0x180032148  call    cs:__imp_EnterCriticalSection
0x18003214e  mov     rcx, [rdi+2958h]; pCertContext
0x180032155  test    rcx, rcx
0x180032158  jnz     loc_1800329F1
0x18003215e  mov     rcx, [rdi+2960h]; pChainContext
0x180032165  mov     rax, qword ptr [rbp+690h+var_450]
0x18003216c  mov     [rdi+2958h], rax
0x180032173  test    rcx, rcx
0x180032176  jnz     loc_1800329E6
0x18003217c  mov     rcx, [rdi+2948h]; hMem
0x180032183  mov     rax, qword ptr [rbp+690h+var_420]
0x18003218a  mov     [rdi+2960h], rax
0x180032191  test    rcx, rcx
0x180032194  jnz     loc_180032A11
0x18003219a  movups  xmm0, [rsp+790h+var_740]
0x18003219f  mov     [rdi+2948h], r15
0x1800321a6  lea     rcx, [rdi+2690h]
0x1800321ad  mov     [rdi+2950h], r12d
0x1800321b4  lea     rax, [rsp+790h+var_720]
0x1800321b9  movups  xmmword ptr [rdi+2674h], xmm0
0x1800321c0  movups  xmmword ptr [rdi+2680h], xmm6
0x1800321c7  movaps  xmm6, [rsp+790h+var_30]
0x1800321cf  lea     rcx, [rcx+80h]
0x1800321d6  movups  xmm0, xmmword ptr [rax]
0x1800321d9  movups  xmm1, xmmword ptr [rax+10h]
0x1800321dd  lea     rax, [rax+80h]
0x1800321e4  movups  xmmword ptr [rcx-80h], xmm0
0x1800321e8  movups  xmm0, xmmword ptr [rax-60h]
0x1800321ec  movups  xmmword ptr [rcx-70h], xmm1
0x1800321f0  movups  xmm1, xmmword ptr [rax-50h]
0x1800321f4  movups  xmmword ptr [rcx-60h], xmm0
0x1800321f8  movups  xmm0, xmmword ptr [rax-40h]
0x1800321fc  movups  xmmword ptr [rcx-50h], xmm1
0x180032200  movups  xmm1, xmmword ptr [rax-30h]
0x180032204  movups  xmmword ptr [rcx-40h], xmm0
0x180032208  movups  xmm0, xmmword ptr [rax-20h]
0x18003220c  movups  xmmword ptr [rcx-30h], xmm1
0x180032210  movups  xmm1, xmmword ptr [rax-10h]
0x180032214  movups  xmmword ptr [rcx-20h], xmm0
0x180032218  movups  xmmword ptr [rcx-10h], xmm1
0x18003221c  sub     r13, 1
0x180032220  jnz     short loc_1800321CF
0x180032222  movups  xmm0, xmmword ptr [rax]
0x180032225  mov     r13, [rsp+790h+arg_10]
0x18003222d  lea     rdx, [rdi+2238h]
0x180032234  movups  xmm1, xmmword ptr [rax+10h]
0x180032238  mov     rax, [rax+20h]
0x18003223c  movups  xmmword ptr [rcx], xmm0
0x18003223f  movups  xmmword ptr [rcx+10h], xmm1
0x180032243  mov     [rcx+20h], rax
0x180032247  mov     ecx, 2
0x18003224c  mov     eax, [rsp+790h+var_748]
0x180032250  mov     [rdi+2938h], eax
0x180032256  lea     rax, [rbp+690h+var_310]
0x18003225d  lea     rdx, [rdx+80h]
0x180032264  movups  xmm0, xmmword ptr [rax]
0x180032267  movups  xmm1, xmmword ptr [rax+10h]
0x18003226b  lea     rax, [rax+80h]
0x180032272  movups  xmmword ptr [rdx-80h], xmm0
0x180032276  movups  xmm0, xmmword ptr [rax-60h]
0x18003227a  movups  xmmword ptr [rdx-70h], xmm1
0x18003227e  movups  xmm1, xmmword ptr [rax-50h]
0x180032282  movups  xmmword ptr [rdx-60h], xmm0
0x180032286  movups  xmm0, xmmword ptr [rax-40h]
0x18003228a  movups  xmmword ptr [rdx-50h], xmm1
0x18003228e  movups  xmm1, xmmword ptr [rax-30h]
0x180032292  movups  xmmword ptr [rdx-40h], xmm0
0x180032296  movups  xmm0, xmmword ptr [rax-20h]
0x18003229a  movups  xmmword ptr [rdx-30h], xmm1
0x18003229e  movups  xmm1, xmmword ptr [rax-10h]
0x1800322a2  movups  xmmword ptr [rdx-20h], xmm0
0x1800322a6  movups  xmmword ptr [rdx-10h], xmm1
0x1800322aa  sub     rcx, 1
0x1800322ae  jnz     short loc_18003225D
0x1800322b0  mov     rax, [rax]
0x1800322b3  mov     rcx, rbx; lpCriticalSection
0x1800322b6  mov     [rdx], rax
0x1800322b9  mov     [rdi+29A4h], esi
0x1800322bf  call    cs:__imp_LeaveCriticalSection
0x1800322c5  mov     dword ptr [rdi+2670h], 1
0x1800322cf  xor     r12d, r12d
0x1800322d2  movzx   eax, word ptr cs:aSecTokenBindin+10h; "g"
0x1800322d9  movups  xmm0, xmmword ptr cs:aSecTokenBindin; "Sec-Token-Binding"
0x1800322e0  mov     rsi, [r14+80h]
0x1800322e7  mov     word ptr [rbp+690h+var_60+10h], ax
0x1800322ee  mov     rax, [rdi+8]
0x1800322f2  movups  xmmword ptr [rbp+690h+var_60], xmm0
0x1800322f9  mov     dword ptr [rbp+690h+var_450+4], r12d
0x180032300  mov     [rbp+690h+dwBytes], r12
0x180032307  mov     rbx, [rax+18h]
0x18003230b  mov     rcx, rbx
0x18003230e  mov     dword ptr [rbp+690h+var_458], r12d
0x180032315  mov     rax, [rbx]
0x180032318  mov     rax, [rax+8]
0x18003231c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032321  cmp     eax, 74656E49h
0x180032326  jz      short loc_18003232C
0x180032328  mov     rbx, [rbx+18h]
0x18003232c  cmp     cs:?g_TokenBindingEnabled@@3HA, r12d; int g_TokenBindingEnabled
0x180032333  jz      short loc_180032342
0x180032335  cmp     [rbx+300h], r12d
0x18003233c  jnz     loc_180032B79
0x180032342  mov     ebx, r12d
0x180032345  mov     eax, ebx
0x180032347  and     eax, 1FFF0000h
0x18003234c  cmp     eax, 0C0000h
0x180032351  jz      loc_180032717
0x180032357  test    ebx, ebx
0x180032359  js      loc_18003298F
0x18003235f  mov     dword ptr [rdi+0CCh], 1
0x180032369  test    byte ptr [r14+38h], 30h
0x18003236e  jz      loc_18003270D
0x180032374  xor     eax, eax
0x180032376  xorps   xmm0, xmm0
0x180032379  movups  [rbp+690h+var_440], xmm0
0x180032380  mov     [rbp+690h+var_430], eax
0x180032386  cmp     [r14+28h], eax
0x18003238a  jnz     loc_1800326A6
0x180032390  mov     ecx, 10h
0x180032395  mov     [rsp+790h+var_750], r14
0x18003239a  lea     rax, [rbp+690h+var_440]
0x1800323a1  mov     [rax], r12b
0x1800323a4  lea     rax, [rax+1]
0x1800323a8  sub     rcx, 1
0x1800323ac  jnz     short loc_1800323A1
0x1800323ae  xorps   xmm0, xmm0
0x1800323b1  mov     [rbp+690h+var_430], r12d
0x1800323b8  xorps   xmm1, xmm1
0x1800323bb  lea     rax, [rbp+690h+var_440]
0x1800323c2  movups  [rbp+690h+var_420], xmm0
0x1800323c9  mov     ecx, 10h
0x1800323ce  movups  xmmword ptr [rbp+690h+var_60], xmm1
0x1800323d5  nop     word ptr [rax+rax+00000000h]
0x1800323e0  mov     [rax], r12b
0x1800323e3  lea     rax, [rax+1]
0x1800323e7  sub     rcx, 1
0x1800323eb  jnz     short loc_1800323E0
0x1800323ed  xorps   xmm0, xmm0
0x1800323f0  mov     dword ptr [rbp+690h+var_450+4], r12d
0x1800323f7  movups  [rbp+690h+var_450], xmm0
0x1800323fe  mov     ecx, 10h
0x180032403  lea     rax, [rbp+690h+var_60]
0x18003240a  nop     word ptr [rax+rax+00h]
0x180032410  mov     [rax], r12b
0x180032413  lea     rax, [rax+1]
0x180032417  sub     rcx, 1
0x18003241b  jnz     short loc_180032410
0x18003241d  lea     rdx, [rbp+690h+var_450]
0x180032424  mov     ecx, 1
0x180032429  call    cs:__imp_EtwEventActivityIdControl
0x18003242f  test    eax, eax
0x180032431  jle     short loc_18003243D
0x180032433  movzx   eax, ax
0x180032436  or      eax, 80070000h
0x18003243b  test    eax, eax
0x18003243d  js      loc_180032A2B
0x180032443  movaps  xmm0, [rbp+690h+var_450]
0x18003244a  movdqa  xmmword ptr [rbp+690h+var_60], xmm0
0x180032452  lea     rdx, ?WinHttpEtwNullActivityId@@3U_GUID@@B; _GUID const WinHttpEtwNullActivityId
0x180032459  mov     dword ptr [rbp+690h+var_450+4], r12d
0x180032460  mov     ecx, 2
0x180032465  call    cs:__imp_EtwEventActivityIdControl
0x18003246b  test    eax, eax
0x18003246d  jle     short loc_180032479
0x18003246f  movzx   eax, ax
0x180032472  or      eax, 80070000h
0x180032477  test    eax, eax
0x180032479  js      loc_180032C05
0x18003247f  movaps  xmm0, xmmword ptr [rbp+690h+var_60]
0x180032486  xor     r9d, r9d
0x180032489  mov     rdx, [r14+40h]
0x18003248d  mov     r8d, 10h
0x180032493  mov     rcx, [rdi+8]
0x180032497  mov     rax, [r14+30h]
0x18003249b  movups  [rbp+690h+var_440], xmm0
0x1800324a2  mov     [rbp+690h+var_430], 1
0x1800324ac  mov     dword ptr [rsp+790h+lpString2], r12d
0x1800324b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324b6  cmp     [rbp+690h+var_430], r12d
0x1800324bd  jz      short loc_1800324EC
0x1800324bf  lea     rdx, [rbp+690h+var_440]
0x1800324c6  mov     dword ptr [rbp+690h+var_450+4], r12d
0x1800324cd  mov     ecx, 2
0x1800324d2  call    cs:__imp_EtwEventActivityIdControl
0x1800324d8  test    eax, eax
0x1800324da  jle     short loc_1800324E6
0x1800324dc  movzx   eax, ax
0x1800324df  or      eax, 80070000h
0x1800324e4  test    eax, eax
0x1800324e6  js      loc_180032A1C
  ... truncated ...
```
