# Sspi::Handshake(void)

- ea: `0x100441290`
- end: `0x1004428e1`
- name: `?Handshake@Sspi@@EEAAKXZ`
- size: `5713`
- prototype: `unsigned int __fastcall(Sspi *__hidden this)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x100405270`
- `0x100405390`
- `0x1004269b0`
- `0x100429de0`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x1004380d0`
- `0x10043eae0`
- `0x10043ee10`
- `0x100441290`
- `0x1004428f0`
- `0x1004474f0`
- `0x100447640`
- `0x1004476e0`
- `0x100448700`
- `0x100450540`
- `0x100486af0`

## import_xrefs

- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x100441b7f`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x100441b7f`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100441461`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100441461`
- `sqldk!?SOS_OS_UserLogRoutine@@3P6AXHHHKZZEA` at `0x100441a4d`
- `sqldk!??_V@YAXPEAX@Z` at `0x100441fe7`
- `sqldk!??_V@YAXPEAX@Z` at `0x100441fe7`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100442813`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100442813`
- `sqldk!SystemThread_TlsIndex` at `0x10044141f`
- `sqldk!SystemThread_TlsIndex` at `0x100441476`
- `sqldk!SystemThread_TlsIndex` at `0x100441a07`
- `sqldk!SystemThread_TlsOffset` at `0x100441428`
- `sqldk!SystemThread_TlsOffset` at `0x10044147f`
- `sqldk!SystemThread_TlsOffset` at `0x100441a10`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100441444`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044149b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100441a2b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100441444`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044149b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100441a2b`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x100441b78`
- `api-ms-win-crt-string-l1-1-0!_strnicmp` at `0x100441bd0`
- `api-ms-win-crt-string-l1-1-0!_strnicmp` at `0x100441bd0`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x100441c9a`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x100441c9a`

## string_xrefs

- `0x10044180b`: `ERR|SNIInitializeSecurityContext failed with %d{WINERR}, SPN is non-blank and connecting to loopback, calling InitializeSecurityContext again with blank SPN.\n`
- `0x1004412d2`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x1004415bb`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x1004416d9`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100441795`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10044181f`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x1004418ae`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x1004418f5`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100441944`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x1004419a8`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100441aaa`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100441cc5`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100441cfa`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100441dba`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100441e01`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100441e9a`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100441ecf`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100441f12`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100441f83`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100442064`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x1004420a4`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x1004420ff`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100442156`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10044216d`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100442528`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100442568`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x1004425d7`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100442689`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100442780`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x1004427e4`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x10044287e`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x1004428a3`: `sql\common\dk\sni\src\SNI_SspiProvider.cpp`
- `0x100441994`: `SNIInitializeSecurityContext return value: %d{DWORD}\n`
- `0x100441781`: `ERR|SNIInitializeSecurityContext return value: %d{DWORD}\n`
- `0x100441da6`: `SNIAcceptSecurityContext return value: %d{DWORD}\n`
- `0x100441e86`: `SNICompleteAuthToken return value: %d{DWORD}\n`
- `0x100441ce6`: `ERR|SNIAcceptSecurityContext return value: %d{DWORD}\n`
- `0x1004425c3`: `SNINo header, sequence, trailer, padding or signature. SSPI provider is used for authentication only and will be removed immediately.\n`
- `0x100441ebb`: `ERR|SNICompleteAuthToken return value: %d{DWORD}\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=37
__int64 __fastcall Sspi::Handshake(Sspi *this)
{
  unsigned int v2; // esi
  __int64 v3; // rcx
  SNI_Sec *v4; // r13
  const OLECHAR *v5; // r12
  int v6; // edx
  char v7; // r15
  unsigned int v8; // ebx
  __int64 v9; // r14
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // r14
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rax
  const wchar_t *v16; // r9
  __int64 v17; // rdx
  int v18; // ecx
  int v19; // edx
  int v20; // edx
  int v21; // edx
  int v22; // eax
  int v23; // eax
  int v24; // r13d
  unsigned int v25; // r13d
  __int64 v26; // rcx
  struct _SecHandle *v27; // rcx
  SNI_Sec *v28; // rax
  _DWORD *v29; // r14
  _DWORD *v30; // r15
  SNI_Sec *v31; // rdx
  int *v32; // rax
  int v33; // eax
  int v34; // ebx
  const WCHAR *v35; // rcx
  unsigned int v36; // eax
  __int64 v37; // rbx
  __int64 v38; // rax
  __int64 v39; // rcx
  int v40; // ebx
  int v41; // r8d
  int v42; // ecx
  int v43; // ecx
  int v44; // ecx
  int v45; // eax
  int v46; // eax
  int v47; // eax
  int v48; // ecx
  unsigned int v49; // r14d
  const char *v50; // rcx
  size_t v51; // r8
  int v52; // ebx
  int v53; // eax
  SNI_Sec *v54; // rdx
  int v55; // eax
  unsigned int v56; // eax
  void *v57; // rcx
  int v58; // edx
  char v59; // al
  unsigned int v60; // eax
  char v61; // al
  unsigned int v62; // r8d
  unsigned int v63; // r9d
  unsigned int v64; // eax
  unsigned int v65; // eax
  unsigned int v66; // ebx
  __int64 v67; // rbx
  void *v68; // rcx
  unsigned int *v70; // [rsp+28h] [rbp-E0h]
  __int64 v71; // [rsp+30h] [rbp-D8h]
  __int64 v72; // [rsp+38h] [rbp-D0h]
  char *v73; // [rsp+40h] [rbp-C8h]
  char v74; // [rsp+68h] [rbp-A0h]
  SNI_Sec *v75; // [rsp+70h] [rbp-98h]
  unsigned int v76; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v77; // [rsp+7Ch] [rbp-8Ch] BYREF
  int v78; // [rsp+80h] [rbp-88h] BYREF
  int v79; // [rsp+88h] [rbp-80h] BYREF
  __int64 v80; // [rsp+90h] [rbp-78h]
  int v81; // [rsp+98h] [rbp-70h] BYREF
  int v82; // [rsp+9Ch] [rbp-6Ch]
  __int64 v83; // [rsp+A0h] [rbp-68h]
  int v84; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v85; // [rsp+B0h] [rbp-58h]
  __int64 v86; // [rsp+B8h] [rbp-50h]
  __int64 v87; // [rsp+C0h] [rbp-48h]
  __int64 v88; // [rsp+C8h] [rbp-40h]
  bool v89; // [rsp+D8h] [rbp-30h]
  int *v90; // [rsp+E8h] [rbp-20h]
  int v91; // [rsp+F0h] [rbp-18h] BYREF
  int v92; // [rsp+F4h] [rbp-14h]
  int *v93; // [rsp+F8h] [rbp-10h]
  int v94; // [rsp+100h] [rbp-8h] BYREF
  char v95[8]; // [rsp+108h] [rbp+0h] BYREF
  _DWORD v96[2]; // [rsp+110h] [rbp+8h] BYREF
  _DWORD *v97; // [rsp+118h] [rbp+10h]
  _DWORD v98[2]; // [rsp+120h] [rbp+18h] BYREF
  __int64 v99; // [rsp+128h] [rbp+20h]
  int v100; // [rsp+130h] [rbp+28h] BYREF
  int v101; // [rsp+134h] [rbp+2Ch]
  _QWORD v102[6]; // [rsp+138h] [rbp+30h]
  int v103; // [rsp+168h] [rbp+60h]
  char v104[4]; // [rsp+170h] [rbp+68h] BYREF
  unsigned int v105; // [rsp+174h] [rbp+6Ch]
  unsigned int v106; // [rsp+178h] [rbp+70h]
  unsigned int v107; // [rsp+17Ch] [rbp+74h]
  wchar_t v108[8]; // [rsp+188h] [rbp+80h] BYREF
  __int128 v109; // [rsp+198h] [rbp+90h]
  __int128 v110; // [rsp+1A8h] [rbp+A0h]
  __int128 v111; // [rsp+1B8h] [rbp+B0h]
  __int128 v112; // [rsp+1C8h] [rbp+C0h]
  __int128 v113; // [rsp+1D8h] [rbp+D0h]
  __int64 v114; // [rsp+1E8h] [rbp+E0h]
  wchar_t String1[8]; // [rsp+1F8h] [rbp+F0h] BYREF
  __int128 v116; // [rsp+208h] [rbp+100h]
  __int128 v117; // [rsp+218h] [rbp+110h]
  __int128 v118; // [rsp+228h] [rbp+120h]
  __int128 v119; // [rsp+238h] [rbp+130h]
  __int128 v120; // [rsp+248h] [rbp+140h]
  __int64 v121; // [rsp+258h] [rbp+150h]
  char String2[8]; // [rsp+268h] [rbp+160h] BYREF

  v102[3] = -2;
  v102[4] = "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp";
  v102[5] = "Sspi::Handshake";
  v103 = 1704;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
      "Sspi::Handshake",
      1704,
      L"API|SNI%u#\n",
      *((_DWORD *)this + 11));
  v2 = 0;
  *((_DWORD *)this + 34) -= *((_DWORD *)this + 44) + *((_DWORD *)this + 45);
  CryptoBase::ProcessInputBuffer(this);
  v77 = 0;
  v3 = *((_QWORD *)this + 4);
  v4 = *(SNI_Sec **)(v3 + 12808);
  v75 = v4;
  v5 = (const OLECHAR *)*((_QWORD *)this + 26);
  v6 = 0;
  v94 = 0;
  if ( (*(_BYTE *)(v3 + 12804) & 2) == 0 )
  {
    v2 = SNIGetInfo(v3, 30, &v94);
    v6 = v94;
  }
  if ( (unsigned int)(*(_DWORD *)(*((_QWORD *)this + 25) + 20LL) - 1) <= 1 )
  {
    v7 = 1;
  }
  else
  {
    v7 = 0;
    if ( (*(_BYTE *)(*((_QWORD *)this + 4) + 12804LL) & 2) == 0 && v6 )
    {
      v74 = 1;
      goto LABEL_11;
    }
  }
  v74 = 0;
LABEL_11:
  v96[0] = 0;
  v96[1] = 1;
  v97 = v98;
  v98[0] = g_cbSspiMaxToken;
  v98[1] = 2;
  v99 = *((_QWORD *)this + 19);
  v91 = 0;
  v92 = 2;
  v93 = &v100;
  v8 = 0;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v79, 1);
  v90 = &v81;
  v84 = 536871395;
  v85 = 0;
  v87 = 0;
  v86 = 0;
  v88 = 0;
  v89 = 0;
  v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v10 = *(_QWORD *)(v9 + 256);
  if ( !v10 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v10 = *(_QWORD *)(v9 + 256);
  }
  v11 = *(_QWORD *)(v10 + 600);
  if ( v11 )
    v89 = (unsigned int)SOS_Task::PushWait(v11, &v84) == 0;
  v12 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v13 = *(_QWORD *)(v12 + 256);
  if ( !v13 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v13 = *(_QWORD *)(v12 + 256);
  }
  v83 = v13;
  v82 = (*(_DWORD *)(v13 + 800) >> 11) & 1;
  if ( v82 || (*(_BYTE *)(v13 + 800) & 4) == 0 )
  {
    v81 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v13 + 608) + 8LL))(*(_QWORD *)(v13 + 608));
  }
  else
  {
    v81 = 0;
  }
  CryptoBase::SetLoginEvent(this, 2);
  if ( !v7 )
  {
    v14 = *((_QWORD *)this + 4);
    if ( (*(_BYTE *)(v14 + 12804) & 2) != 0 || v74 && *((char *)this + 64) < 0 )
    {
      v15 = *(_QWORD *)(v14 + 12824);
      if ( v15 && (v102[0] = *(_QWORD *)(v15 + 8)) != 0 && (v100 = **(_DWORD **)(v14 + 12824)) != 0 )
      {
        v101 = 14;
        v2 = 0;
        v8 = 1;
      }
      else
      {
        if ( (*(_BYTE *)(v14 + 12804) & 2) == 0 )
        {
          *((_DWORD *)this + 48) = 4;
          *((_DWORD *)this + 49) = 44;
          v2 = -2146892986;
          if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
          {
            LODWORD(v70) = 3;
            SNIXE_SNI_ERROR_ON(
              "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
              "Sspi::Handshake",
              1807,
              L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
              v70,
              15,
              -2146892986);
          }
          SNISetLastError(3, 2148074310LL, 50115);
          *(_BYTE *)(*((_QWORD *)this + 4) + 12804LL) |= 8u;
          AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v81);
          goto LABEL_223;
        }
        v2 = 0;
      }
    }
  }
  v17 = *((_QWORD *)this + 25);
  if ( (*(_BYTE *)(*((_QWORD *)this + 4) + 12804LL) & 2) == 0 )
  {
    v39 = 2LL * v8;
    *(&v100 + 2 * v39) = *((_DWORD *)this + 34);
    *(&v101 + 2 * v39) = 2;
    v102[v39] = *((_QWORD *)this + 16);
    v40 = v8 + 1;
    v41 = 2;
    if ( !v17 )
      goto LABEL_103;
    v42 = *(_DWORD *)(v17 + 20);
    if ( v42 )
    {
      v43 = v42 - 1;
      if ( !v43 )
      {
        v41 = 131090;
        goto LABEL_103;
      }
      v44 = v43 - 1;
      if ( !v44 )
      {
        v41 = 131074;
        goto LABEL_103;
      }
      if ( v44 != 1 )
        goto LABEL_103;
    }
    v45 = 2;
    if ( (*((_DWORD *)this + 16) & 0x200) != 0 )
      v45 = 131074;
    v41 = v45;
LABEL_103:
    v46 = 0x80000;
    if ( (*((_DWORD *)this + 16) & 0x40) == 0 )
      v46 = 1;
    v47 = v41 | v46;
    v48 = *((_DWORD *)this + 16) & 0x20;
    if ( v48 )
      v47 |= 0xCu;
    v49 = v47 | 0xC;
    if ( !v48 )
      v49 = v47;
    v92 = v40;
    strcpy(String2, "NTLMSSP");
    if ( !OsInfo::IsLinux(SOS_OS_OsInfo) )
      goto LABEL_127;
    v50 = (const char *)*((_QWORD *)this + 16);
    if ( !v50 )
      goto LABEL_127;
    v51 = -1;
    do
      ++v51;
    while ( String2[v51] );
    if ( *((unsigned int *)this + 34) < v51 )
      goto LABEL_127;
    if ( _strnicmp(v50, String2, v51) )
      goto LABEL_127;
    *(_OWORD *)String1 = 0;
    v116 = 0;
    v117 = 0;
    v118 = 0;
    v119 = 0;
    v120 = 0;
    v121 = 0;
    *(_OWORD *)v108 = 0;
    v109 = 0;
    v110 = 0;
    v111 = 0;
    v112 = 0;
    v113 = 0;
    v114 = 0;
    v52 = SNIGetInfo(*((_QWORD *)this + 4), 23, String1);
    v53 = SNIGetInfo(*((_QWORD *)this + 4), 17, v108);
    if ( v52 || v53 || HIDWORD(v121) != HIDWORD(v114) || wcsncmp(String1, v108, SHIDWORD(v121)) )
    {
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
          "Sspi::Handshake",
          2083,
          L"ERR|SNINTLM authentication is not allowed on Linux\n");
      v34 = -2146893048;
    }
    else
    {
LABEL_127:
      v54 = 0;
      if ( *((_DWORD *)v4 + 4) )
        v54 = v4;
      v55 = ((__int64 (__fastcall *)(struct _SecHandle *, SNI_Sec *, int *, _QWORD, int, SNI_Sec *, _DWORD *, unsigned int *, char *))g_pFuncs->AcceptSecurityContext)(
              &ghSspiCred,
              v54,
              &v91,
              v49,
              16,
              v4,
              v96,
              &v77,
              v95);
      v34 = v55;
      if ( v55 >= 0 )
      {
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          _mm_lfence();
          LODWORD(v70) = v55;
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
            "Sspi::Handshake",
            2103,
            L"SNIAcceptSecurityContext return value: %d{DWORD}\n",
            v70);
        }
        goto LABEL_124;
      }
    }
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      _mm_lfence();
      LODWORD(v70) = v34;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
        "Sspi::Handshake",
        2103,
        L"ERR|SNIAcceptSecurityContext return value: %d{DWORD}\n",
        v70);
    }
LABEL_124:
    v29 = (_DWORD *)((char *)this + 192);
    *((_DWORD *)this + 48) = 4;
    v30 = (_DWORD *)((char *)this + 196);
    *((_DWORD *)this + 49) = 14;
    goto LABEL_86;
  }
  v18 = 16386;
  if ( !v17 )
    goto LABEL_44;
  v19 = *(_DWORD *)(v17 + 20);
  if ( !v19 )
  {
LABEL_40:
    v22 = 8404994;
    if ( (*((_DWORD *)this + 16) & 0x200) != 0 )
      v22 = 81922;
    v18 = v22;
    goto LABEL_45;
  }
  v20 = v19 - 1;
  if ( !v20 )
  {
    v18 = 81938;
    goto LABEL_45;
  }
  v21 = v20 - 1;
  if ( !v21 )
  {
LABEL_44:
    v18 = 81922;
    goto LABEL_45;
  }
  if ( v21 == 1 )
    goto LABEL_40;
LABEL_45:
  v23 = *((_DWORD *)this + 16);
  v24 = 0x20000;
  if ( (v23 & 0x40) == 0 )
    v24 = 1;
  v25 = v18 | v24;
  if ( (v23 & 0x20) != 0 )
    v25 |= 0xCu;
  if ( *((_DWORD *)v75 + 4) )
  {
    v26 = 2LL * v8;
    *(&v100 + 2 * v26) = *((_DWORD *)this + 34);
    *(&v101 + 2 * v26) = 2;
    v102[v26] = *((_QWORD *)this + 16);
    ++v8;
  }
  else if ( (v23 & 0x10) == 0 )
  {
    v73 = (char *)v75 + 24;
    HIDWORD(v71) = 0;
    HIDWORD(v70) = 0;
    v36 = ((__int64 (__fastcall *)(_QWORD, wchar_t near **, __int64))g_pFuncs->AcquireCredentialsHandleW)(
            0,
            &g_szSSP,
            2);
    v2 = v36;
    if ( v36 )
    {
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
          "Sspi::Handshake",
          1899,
          L"ERR|SNIAcquireCredentialsHandle return value: %d{DWORD}\n",
          v36);
      *((_DWORD *)this + 48) = 4;
      *((_DWORD *)this + 49) = 12;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v70) = 3;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
          "Sspi::Handshake",
          1906,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v70,
          0,
          v2);
      }
      SNISetLastError(3, v2, 50100);
      AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v81);
      goto LABEL_223;
    }
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
        "Sspi::Handshake",
        1899,
        L"SNIAcquireCredentialsHandle return value: %d{DWORD}\n",
        0);
    *((_DWORD *)this + 48) = 4;
    *((_DWORD *)this + 49) = 12;
  }
  if ( (*((_BYTE *)this + 64) & 0x10) != 0 )
  {
    v27 = &ghSspiCred;
    v90 = (int *)&ghSspiCred;
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
        "Sspi::Handshake",
        1918,
        L"SNIUsing global credentials handle because flag SNI_SSPI_USE_GLOBAL_CREDENTIALS_HANDLE is set.\n");
      v27 = &ghSspiCred;
    }
    v28 = v75;
  }
  else
  {
    v28 = v75;
    v27 = (struct _SecHandle *)((char *)v75 + 24);
    v90 = (int *)((char *)v75 + 24);
  }
  v92 = v8;
  v29 = (_DWORD *)((char *)this + 192);
  v30 = (_DWORD *)((char *)this + 196);
  while ( 1 )
  {
    v31 = 0;
    if ( *((_DWORD *)v28 + 4) )
      v31 = v28;
    v32 = &v91;
    if ( !v8 )
      v32 = 0;
    LODWORD(v73) = 0;
    LODWORD(v71) = 16;
    LODWORD(v70) = 0;
    v33 = ((__int64 (__fastcall *)(struct _SecHandle *, SNI_Sec *, const OLECHAR *, _QWORD, unsigned int *, __int64, int *, char *, SNI_Sec *, _DWORD *, unsigned int *, char *))g_pFuncs->InitializeSecurityContextW)(
            v27,
            v31,
            v5,
            v25,
            v70,
            v71,
            v32,
            v73,
            v75,
            v96,
            &v77,
            v95);
    v34 = v33;
    if ( v33 >= 0 )
      break;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      _mm_lfence();
      LODWORD(v70) = v33;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
        "Sspi::Handshake",
        1944,
        L"ERR|SNIInitializeSecurityContext return value: %d{DWORD}\n",
        v70);
    }
    *v29 = 4;
    *v30 = 13;
    if ( !v5 )
      goto LABEL_85;
    if ( v5 == &word_1004A26DC )
      goto LABEL_85;
    if ( !*v5 )
      goto LABEL_85;
    v35 = *(const WCHAR **)(*((_QWORD *)this + 4) + 12600LL);
    if ( !*v35 || !(unsigned int)Tcp::FIsLoopBack(v35) )
      goto LABEL_85;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      _mm_lfence();
      LODWORD(v70) = v34;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
        "Sspi::Handshake",
        1986,
        L"ERR|SNIInitializeSecurityContext failed with %d{WINERR}, SPN is non-blank and connecting to loopback, calling In"
         "itializeSecurityContext again with blank SPN.\n",
        v70);
    }
    v5 = &word_1004A26DC;
    v8 = v92;
    v27 = (struct _SecHandle *)v90;
    v28 = v75;
  }
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    _mm_lfence();
    LODWORD(v70) = v33;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
      "Sspi::Handshake",
      1944,
      L"SNIInitializeSecurityContext return value: %d{DWORD}\n",
      v70);
  }
  *v29 = 4;
  *v30 = 13;
LABEL_85:
  v4 = v75;
LABEL_86:
  CryptoBase::SetLoginEvent(this, 2);
  if ( !*((_DWORD *)this + 12) )
    *((_DWORD *)this + 12) = 1;
  if ( v34 < 0 )
  {
    _mm_lfence();
    if ( v34 == -2146893056 )
    {
      v37 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v38 = *(_QWORD *)(v37 + 256);
      if ( !v38 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v38 = *(_QWORD *)(v37 + 256);
      }
      SOS_OS_UserLogRoutine(701, 17, 226, 0, *(_QWORD *)(*(_QWORD *)(v38 + 536) + 3336LL) + 320LL);
      v2 = -2146893056;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        _mm_lfence();
        LODWORD(v72) = -2146893056;
        LODWORD(v71) = 0;
        LODWORD(v70) = 3;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
          "Sspi::Handshake",
          2129,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v70,
          v71,
          v72);
      }
      SNISetLastError(3, 2148074240LL, 50100);
      AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v81);
    }
    else
    {
      v2 = v34;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        _mm_lfence();
        LODWORD(v72) = v34;
        LODWORD(v71) = 0;
        LODWORD(v70) = 3;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
          "Sspi::Handshake",
          2167,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v70,
          v71,
          v72);
      }
      SNISetLastError(3, (unsigned int)v34, 50100);
      AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v81);
    }
    goto LABEL_223;
  }
  *((_DWORD *)v4 + 4) = 1;
  if ( (unsigned int)(v34 - 590611) <= 1 )
  {
    if ( !g_pFuncs->CompleteAuthToken )
    {
      v2 = -1;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v72) = -1;
        LODWORD(v71) = 15;
        LODWORD(v70) = 3;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
          "Sspi::Handshake",
          2198,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v70,
          v71,
          v72);
      }
      SNISetLastError(3, 0xFFFFFFFFLL, 50115);
      *v29 = 4;
      *v30 = 16;
      AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v81);
      goto LABEL_223;
    }
    _mm_lfence();
    v56 = ((__int64 (__fastcall *)(SNI_Sec *, _DWORD *))g_pFuncs->CompleteAuthToken)(v4, v96);
    v2 = v56;
    if ( v56 )
    {
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        _mm_lfence();
        LODWORD(v70) = v56;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
          "Sspi::Handshake",
          2183,
          L"ERR|SNICompleteAuthToken return value: %d{DWORD}\n",
          v70);
      }
      _mm_lfence();
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        _mm_lfence();
        LODWORD(v72) = v2;
        LODWORD(v71) = 0;
        LODWORD(v70) = 3;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
          "Sspi::Handshake",
          2187,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v70,
          v71,
          v72);
      }
      SNISetLastError(3, v2, 50100);
      *v29 = 4;
      *v30 = 15;
      AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v81);
      goto LABEL_223;
    }
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      _mm_lfence();
      LODWORD(v70) = 0;
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
        "Sspi::Handshake",
        2183,
        L"SNICompleteAuthToken return value: %d{DWORD}\n",
        v70);
    }
  }
  *((_DWORD *)this + 41) = v98[0];
  if ( ((v34 - 590610) & 0xFFFFFFFD) != 0 )
  {
    v57 = (void *)*((_QWORD *)this + 26);
    if ( v57 )
      operator delete[](v57);
    v2 = Sspi::ValidateOutputContextAttributes(this, v77);
    if ( v2 )
    {
      AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v81);
      goto LABEL_223;
    }
    v76 = 0;
    v58 = *(_DWORD *)(*((_QWORD *)this + 25) + 20LL);
    if ( v58 )
    {
      if ( v58 == 1 || v58 == 2 )
      {
        _mm_lfence();
        v60 = ((__int64 (__fastcall *)(SNI_Sec *, _QWORD, char *))g_pFuncs->QueryContextAttributesW)(v4, 0, v104);
        v2 = v60;
        if ( v60 )
        {
          if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
          {
            _mm_lfence();
            LODWORD(v70) = v60;
            SNIXE_SNI_ERROR_ON(
              "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
              "Sspi::Handshake",
              2267,
              L"ERR|SNIQueryContextAttributes return value: %d{DWORD}\n",
              v70);
          }
          _mm_lfence();
          if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
          {
            _mm_lfence();
            LODWORD(v72) = v2;
            LODWORD(v71) = 0;
            LODWORD(v70) = 3;
            SNIXE_SNI_ERROR_ON(
              "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
              "Sspi::Handshake",
              2271,
              L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
              v70,
              v71,
              v72);
          }
          SNISetLastError(3, v2, 50100);
          *v29 = 4;
          *v30 = 17;
          AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v81);
          goto LABEL_223;
        }
        v61 = g_XeSniPkg_enabledBitmap;
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          _mm_lfence();
          LODWORD(v70) = 0;
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
            "Sspi::Handshake",
            2267,
            L"SNIQueryContextAttributes return value: %d{DWORD}\n",
            v70);
          v61 = g_XeSniPkg_enabledBitmap;
        }
        if ( *(_DWORD *)(*((_QWORD *)this + 25) + 20LL) == 1 )
        {
          if ( (v61 & 1) != 0 )
            SNIXE_SNI_TRACE_ON(
              "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
              "Sspi::Handshake",
              2282,
              L"SNISSPI provider will be used for encryption. Calculating trailer and padding sizes.\n");
          *((_DWORD *)this + 20) = 0;
          v62 = v107;
          *((_DWORD *)this + 19) = v107;
          v63 = v106;
          *((_DWORD *)this + 21) = v106;
          *((_DWORD *)this + 18) = 24;
          if ( (int)Sspi::ULongAdd3Args(this, 0x18u, v62, v63, &v76) < 0 )
          {
            v2 = 534;
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              LODWORD(v72) = 534;
              LODWORD(v71) = 0;
              LODWORD(v70) = 3;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Handshake",
                2306,
                L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
                v70,
                v71,
                v72);
            }
            SNISetLastError(3, 534, 50100);
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              _mm_lfence();
              LODWORD(v72) = *((_DWORD *)this + 21);
              LODWORD(v71) = *((_DWORD *)this + 19);
              LODWORD(v70) = *((_DWORD *)this + 18);
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Handshake",
                2315,
                L"ERR|SNIInvalid header, trailer and padding sizes in Sspi object. m_cbHeaderLength: %d{DWORD}, m_cbTraile"
                 "rLength: %d{DWORD}, m_cbPaddingLength: %d{DWORD}\n",
                v70,
                v71,
                v72);
            }
            *v29 = 4;
            *v30 = 71;
            AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v81);
            goto LABEL_223;
          }
          _mm_lfence();
          if ( v76 + *(_DWORD *)(*((_QWORD *)this + 4) + 12752LL) < v76 )
          {
            v2 = 534;
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              LODWORD(v72) = 534;
              LODWORD(v71) = 0;
              LODWORD(v70) = 3;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Handshake",
                2333,
                L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
                v70,
                v71,
                v72);
            }
            SNISetLastError(3, 534, 50100);
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              _mm_lfence();
              LODWORD(v73) = *(_DWORD *)(*((_QWORD *)this + 4) + 12752LL);
              LODWORD(v72) = *((_DWORD *)this + 21);
              LODWORD(v71) = *((_DWORD *)this + 19);
              LODWORD(v70) = *((_DWORD *)this + 18);
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Handshake",
                2343,
                L"ERR|SNIOverflow when calculating total packet buffer. m_cbHeaderLength: %d{DWORD}, m_cbTrailerLength: %d"
                 "{DWORD}, m_cbPaddingLength: %d{DWORD}, ConsBufferSize: %d{DWORD}\n",
                v70,
                v71,
                v72,
                v73);
            }
            *v29 = 4;
            *v30 = 72;
            AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v81);
            goto LABEL_223;
          }
        }
        else
        {
          if ( (v61 & 1) != 0 )
            SNIXE_SNI_TRACE_ON(
              "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
              "Sspi::Handshake",
              2357,
              L"SNISSPI provider will be used for signature. Calculating signature size.\n");
          v64 = v105;
          *((_DWORD *)this + 20) = v105;
          *((_QWORD *)this + 9) = 16;
          *((_DWORD *)this + 21) = 0;
          if ( v64 >= 0xFFFFFFF0 )
          {
            v76 = -1;
            v2 = 534;
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              LODWORD(v72) = 534;
              LODWORD(v71) = 0;
              LODWORD(v70) = 3;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Handshake",
                2376,
                L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
                v70,
                v71,
                v72);
            }
            SNISetLastError(3, 534, 50100);
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              LODWORD(v71) = *((_DWORD *)this + 20);
              LODWORD(v70) = *((_DWORD *)this + 18);
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Handshake",
                2382,
                L"ERR|SNIInvalid header and signature sizes in Sspi object. m_cbHeaderLength: %d{DWORD}, m_cbPaddingLength: %d{DWORD}\n",
                v70,
                v71);
            }
            *v29 = 4;
            *v30 = 73;
            AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v81);
            goto LABEL_223;
          }
          v76 = v64 + 16;
          if ( v64 + 16 + *(_DWORD *)(*((_QWORD *)this + 4) + 12752LL) < v64 + 16 )
          {
            v2 = 534;
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              LODWORD(v72) = 534;
              LODWORD(v71) = 0;
              LODWORD(v70) = 3;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Handshake",
                2400,
                L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
                v70,
                v71,
                v72);
            }
            SNISetLastError(3, 534, 50100);
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              LODWORD(v72) = *(_DWORD *)(*((_QWORD *)this + 4) + 12752LL);
              LODWORD(v71) = *((_DWORD *)this + 20);
              LODWORD(v70) = *((_DWORD *)this + 18);
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
                "Sspi::Handshake",
                2408,
                L"ERR|SNIOverflow when calculating total packet buffer. m_cbHeaderLength: %d{DWORD}, m_cbPaddingLength: %d"
                 "{DWORD}, ConsBufferSize: %d{DWORD}\n",
                v70,
                v71,
                v72);
            }
            *v29 = 4;
            *v30 = 74;
            AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v81);
            goto LABEL_223;
          }
        }
        *((_DWORD *)this + 23) = -1;
      }
      else if ( v58 == 3 )
      {
        *((_QWORD *)this + 9) = 4;
        *((_QWORD *)this + 10) = 0;
        *((_DWORD *)this + 23) = -1;
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
            "Sspi::Handshake",
            2257,
            L"SNIOnly header will be used. No sequence, trailer, padding or signature. SSPI provider is used for authentic"
             "ation followed by message-based plain text mode.\n");
      }
      else
      {
        v59 = g_XeSniPkg_enabledBitmap;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v70) = *(_DWORD *)(*((_QWORD *)this + 25) + 20LL);
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
            "Sspi::Handshake",
            2427,
            L"ERR|SNIInvalid crypto mode %d for SSPI provider encountered.\n",
            v70);
          v59 = g_XeSniPkg_enabledBitmap;
        }
        v2 = 87;
        if ( (v59 & 2) != 0 )
        {
          LODWORD(v72) = 87;
          LODWORD(v71) = 0;
          LODWORD(v70) = 3;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
            "Sspi::Handshake",
            2430,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            v70,
            v71,
            v72);
        }
        SNISetLastError(3, 87, 50100);
      }
    }
    else
    {
      *((_QWORD *)this + 9) = 0;
      *((_QWORD *)this + 10) = 0;
      *((_DWORD *)this + 23) = -1;
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
          "Sspi::Handshake",
          2245,
          L"SNINo header, sequence, trailer, padding or signature. SSPI provider is used for authentication only and will "
           "be removed immediately.\n");
    }
    if ( !*((_DWORD *)this + 41) || (*((_BYTE *)this + 64) & 4) != 0 )
    {
      CryptoBase::FreeReadWriteBuffers(this);
      v2 = (*(__int64 (__fastcall **)(Sspi *))(*(_QWORD *)this + 296LL))(this);
      if ( v2 )
      {
        *((_DWORD *)this + 12) = 4;
        AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v81);
LABEL_223:
        *(_DWORD *)(v80 + 616) &= ~v79;
        *((_DWORD *)this + 12) = 4;
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          LODWORD(v70) = v2;
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
            "Sspi::Handshake",
            2535,
            L"RET|SNI%d{WINERR}\n",
            v70);
        }
        goto LABEL_230;
      }
      *((_DWORD *)this + 54) = 3;
      *((_DWORD *)this + 12) = 3;
    }
    else
    {
      *((_DWORD *)this + 12) = 2;
    }
  }
  if ( *((_DWORD *)this + 12) != 3 )
  {
    if ( !*((_DWORD *)this + 41) )
    {
      *((_DWORD *)this + 12) = 4;
      v2 = 87;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v72) = 87;
        LODWORD(v71) = 0;
        LODWORD(v70) = 3;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
          "Sspi::Handshake",
          2478,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v70,
          v71,
          v72);
      }
      SNISetLastError(3, 87, 50100);
      *v29 = 4;
      *v30 = 75;
      AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v81);
      goto LABEL_223;
    }
    CryptoBase::FormatOutputBuffer(this);
    *((_DWORD *)this + 41) += *((_DWORD *)this + 46) + *((_DWORD *)this + 47);
    *((_DWORD *)this + 40) = 0;
    *((_DWORD *)this + 34) = 0;
  }
  _mm_lfence();
  SNI_Sec::SetPkgName(v4);
  if ( (unsigned int)(*((_DWORD *)this + 12) - 2) <= 1 )
  {
    if ( v74 )
    {
      if ( *((char *)this + 64) >= 0 )
      {
        v78 = 0;
        v65 = Sspi::CheckServiceBindings(this, (enum SNIAuthErrStates *)&v78);
        v66 = v65;
        *v29 = 4;
        *v30 = v78;
        if ( v65 )
        {
          *(_BYTE *)(*((_QWORD *)this + 4) + 12804LL) |= 8u;
          v2 = v65;
          if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
          {
            LODWORD(v72) = v65;
            LODWORD(v71) = 0;
            LODWORD(v70) = 10;
            SNIXE_SNI_ERROR_ON(
              "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
              "Sspi::Handshake",
              2509,
              L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
              v70,
              v71,
              v72);
          }
          SNISetLastError(10, v66, 50100);
          AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v81);
          goto LABEL_223;
        }
      }
    }
    v67 = *((_QWORD *)this + 4);
    v68 = *(void **)(v67 + 12824);
    if ( v68 )
    {
      Ssl::ReleaseChannelBindings(v68);
      operator delete(*(void **)(v67 + 12824), 0);
      *(_QWORD *)(v67 + 12824) = 0;
    }
  }
  CryptoBase::SetLoginEvent(this, 3);
  AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v81);
  *(_DWORD *)(v80 + 616) &= ~v79;
  CryptoBase::SetLoginEvent(this, 3);
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    _mm_lfence();
    LODWORD(v70) = v2;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp",
      "Sspi::Handshake",
      2527,
      L"RET|SNI%d{WINERR}\n",
      v70);
  }
  v2 = 0;
LABEL_230:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\SNI_SspiProvider.cpp", "Sspi::Handshake", 1704, v16);
  return v2;
}

```

## disassembly

```asm
0x100441290  mov     rax, rsp
0x100441293  push    rbp
0x100441294  push    r12
0x100441296  push    r13
0x100441298  push    r14
0x10044129a  push    r15
0x10044129c  lea     rbp, [rax-198h]
0x1004412a3  sub     rsp, 270h
0x1004412aa  mov     [rbp+190h+var_148], 0FFFFFFFFFFFFFFFEh
0x1004412b2  mov     [rax+10h], rbx
0x1004412b6  mov     [rax+18h], rsi
0x1004412ba  mov     [rax+20h], rdi
0x1004412be  mov     rax, cs:__security_cookie
0x1004412c5  xor     rax, rsp
0x1004412c8  mov     [rbp+190h+var_28], rax
0x1004412cf  mov     rdi, rcx
0x1004412d2  lea     rcx, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x1004412d9  mov     [rbp+190h+var_140], rcx
0x1004412dd  lea     rdx, aSspiHandshake; "Sspi::Handshake"
0x1004412e4  mov     [rbp+190h+var_138], rdx
0x1004412e8  mov     [rbp+190h+var_130], 6A8h
0x1004412ef  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004412f6  jz      short loc_100441311
0x1004412f8  mov     eax, [rdi+2Ch]
0x1004412fb  mov     dword ptr [rsp+290h+var_270], eax
0x1004412ff  lea     r9, aApiSniU; "API|SNI%u#\n"
0x100441306  mov     r8d, 6A8h; int
0x10044130c  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100441311  xor     r14d, r14d
0x100441314  mov     esi, r14d
0x100441317  mov     eax, [rdi+0B4h]
0x10044131d  add     eax, [rdi+0B0h]
0x100441323  sub     [rdi+88h], eax
0x100441329  mov     rcx, rdi; this
0x10044132c  call    ?ProcessInputBuffer@CryptoBase@@IEAAXXZ; CryptoBase::ProcessInputBuffer(void)
0x100441331  mov     [rsp+290h+var_21C], r14d
0x100441336  mov     rcx, [rdi+20h]
0x10044133a  mov     r13, [rcx+3208h]
0x100441341  mov     [rsp+290h+var_228], r13
0x100441346  mov     r12, [rdi+0D0h]
0x10044134d  mov     edx, r14d
0x100441350  mov     [rbp+190h+var_198], edx
0x100441353  test    byte ptr [rcx+3204h], 2
0x10044135a  jnz     short loc_10044136E
0x10044135c  lea     r8, [rbp+190h+var_198]
0x100441360  lea     edx, [r14+1Eh]
0x100441364  call    SNIGetInfo
0x100441369  mov     esi, eax
0x10044136b  mov     edx, [rbp+190h+var_198]
0x10044136e  mov     rax, [rdi+0C8h]
0x100441375  mov     ecx, [rax+14h]
0x100441378  dec     ecx
0x10044137a  cmp     ecx, 1
0x10044137d  jbe     short loc_10044139A
0x10044137f  xor     r15b, r15b
0x100441382  mov     rax, [rdi+20h]
0x100441386  test    byte ptr [rax+3204h], 2
0x10044138d  jnz     short loc_10044139D
0x10044138f  test    edx, edx
0x100441391  jz      short loc_10044139D
0x100441393  mov     byte ptr [rsp+290h+var_230], 1
0x100441398  jmp     short loc_1004413A2
0x10044139a  mov     r15b, 1
0x10044139d  mov     byte ptr [rsp+290h+var_230], r14b
0x1004413a2  mov     [rbp+190h+var_188], r14d
0x1004413a6  mov     ecx, 1
0x1004413ab  mov     [rbp+190h+var_184], ecx
0x1004413ae  lea     rax, [rbp+190h+var_178]
0x1004413b2  mov     [rbp+190h+var_180], rax
0x1004413b6  mov     eax, cs:?g_cbSspiMaxToken@@3KA; ulong g_cbSspiMaxToken
0x1004413bc  mov     [rbp+190h+var_178], eax
0x1004413bf  mov     [rbp+190h+var_174], 2
0x1004413c6  mov     rax, [rdi+98h]
0x1004413cd  mov     [rbp+190h+var_170], rax
0x1004413d1  mov     [rbp+190h+var_1A8], r14d
0x1004413d5  mov     [rbp+190h+var_1A4], 2
0x1004413dc  lea     rax, [rbp+190h+var_168]
0x1004413e0  mov     [rbp+190h+var_1A0], rax
0x1004413e4  mov     ebx, r14d
0x1004413e7  mov     edx, ecx
0x1004413e9  lea     rcx, [rbp+190h+var_210]
0x1004413ed  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x1004413f2  nop
0x1004413f3  lea     rax, [rbp+190h+var_200]
0x1004413f7  mov     [rbp+190h+var_1B0], rax
0x1004413fb  mov     [rbp+190h+var_1F0], 200001E3h
0x100441402  mov     [rbp+190h+var_1E8], r14
0x100441406  mov     [rbp+190h+var_1D8], r14
0x10044140a  mov     [rbp+190h+var_1E0], r14
0x10044140e  mov     [rbp+190h+var_1D0], r14
0x100441412  mov     [rbp+190h+var_1C0], 0
0x100441416  mov     rdx, gs:58h
0x10044141f  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100441426  mov     ecx, [rax]
0x100441428  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044142f  mov     r14d, [rax]
0x100441432  add     r14, [rdx+rcx*8]
0x100441436  mov     rax, [r14+100h]
0x10044143d  test    rax, rax
0x100441440  jnz     short loc_100441451
0x100441442  xor     ecx, ecx
0x100441444  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044144a  mov     rax, [r14+100h]
0x100441451  mov     rcx, [rax+258h]
0x100441458  test    rcx, rcx
0x10044145b  jz      short loc_10044146D
0x10044145d  lea     rdx, [rbp+190h+var_1F0]
0x100441461  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x100441467  test    eax, eax
0x100441469  setz    [rbp+190h+var_1C0]
0x10044146d  mov     rdx, gs:58h
0x100441476  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044147d  mov     ecx, [rax]
0x10044147f  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100441486  mov     r14d, [rax]
0x100441489  add     r14, [rdx+rcx*8]
0x10044148d  mov     rdx, [r14+100h]
0x100441494  test    rdx, rdx
0x100441497  jnz     short loc_1004414A8
0x100441499  xor     ecx, ecx
0x10044149b  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004414a1  mov     rdx, [r14+100h]
0x1004414a8  mov     [rbp+190h+var_1F8], rdx
0x1004414ac  mov     eax, [rdx+320h]
0x1004414b2  shr     eax, 0Bh
0x1004414b5  and     eax, 1
0x1004414b8  mov     [rbp+190h+var_1FC], eax
0x1004414bb  jnz     short loc_1004414CF
0x1004414bd  test    byte ptr [rdx+320h], 4
0x1004414c4  jz      short loc_1004414CF
0x1004414c6  xor     r14d, r14d
0x1004414c9  mov     [rbp+190h+var_200], r14d
0x1004414cd  jmp     short loc_1004414E9
0x1004414cf  mov     r8d, 1
0x1004414d5  mov     [rbp+190h+var_200], r8d
0x1004414d9  mov     rcx, [rdx+260h]
0x1004414e0  mov     rax, [rcx]
0x1004414e3  call    qword ptr [rax+8]
0x1004414e6  xor     r14d, r14d
0x1004414e9  xor     r8d, r8d
0x1004414ec  lea     edx, [r8+2]
0x1004414f0  mov     rcx, rdi
0x1004414f3  call    ?SetLoginEvent@CryptoBase@@QEAAXW4SNIAuthTimerEvent@@W4SNIAuthTimerEventType@@@Z; CryptoBase::SetLoginEvent(SNIAuthTimerEvent,SNIAuthTimerEventType)
0x1004414f8  test    r15b, r15b
0x1004414fb  jnz     loc_1004415F6
0x100441501  mov     rdx, [rdi+20h]
0x100441505  test    byte ptr [rdx+3204h], 2
0x10044150c  jnz     short loc_100441523
0x10044150e  cmp     byte ptr [rsp+290h+var_230], r15b
0x100441513  jz      loc_1004415F6
0x100441519  test    byte ptr [rdi+40h], 80h
0x10044151d  jz      loc_1004415F6
0x100441523  mov     rax, [rdx+3218h]
0x10044152a  test    rax, rax
0x10044152d  jz      short loc_100441564
0x10044152f  mov     rax, [rax+8]
0x100441533  mov     [rbp+190h+var_160], rax
0x100441537  test    rax, rax
0x10044153a  jz      short loc_100441564
0x10044153c  mov     rax, [rdx+3218h]
0x100441543  mov     ecx, [rax]
0x100441545  mov     [rbp+190h+var_168], ecx
0x100441548  test    ecx, ecx
0x10044154a  jz      short loc_100441564
0x10044154c  mov     [rbp+190h+var_164], 0Eh
0x100441553  mov     esi, r14d
0x100441556  mov     r9d, 1
0x10044155c  mov     ebx, r9d
0x10044155f  jmp     loc_1004415FC
0x100441564  test    byte ptr [rdx+3204h], 2
0x10044156b  jnz     loc_1004415F3
0x100441571  mov     dword ptr [rdi+0C0h], 4
0x10044157b  mov     dword ptr [rdi+0C4h], 2Ch ; ','
0x100441585  mov     esi, 80090346h
0x10044158a  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100441591  jz      short loc_1004415C7
0x100441593  mov     dword ptr [rsp+290h+var_260], esi
0x100441597  mov     dword ptr [rsp+290h+var_268], 0Fh
0x10044159f  mov     dword ptr [rsp+290h+var_270], 3
0x1004415a7  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x1004415ae  mov     r8d, 70Fh; int
0x1004415b4  lea     rdx, aSspiHandshake; "Sspi::Handshake"
0x1004415bb  lea     rcx, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x1004415c2  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x1004415c7  mov     r8d, 0C3C3h
0x1004415cd  mov     edx, esi
0x1004415cf  mov     ecx, 3
0x1004415d4  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1004415d9  mov     rax, [rdi+20h]
0x1004415dd  or      byte ptr [rax+3204h], 8
0x1004415e4  lea     rcx, [rbp+190h+var_200]; this
0x1004415e8  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x1004415ed  nop
0x1004415ee  jmp     loc_1004427A9
0x1004415f3  mov     esi, r14d
0x1004415f6  mov     r9d, 1
0x1004415fc  mov     rdx, [rdi+0C8h]
0x100441603  mov     rax, [rdi+20h]
0x100441607  test    byte ptr [rax+3204h], 2
0x10044160e  jz      loc_100441AD8
0x100441614  mov     ecx, 4002h
0x100441619  test    rdx, rdx
0x10044161c  jz      short loc_100441653
0x10044161e  mov     edx, [rdx+14h]
0x100441621  test    edx, edx
0x100441623  jz      short loc_100441634
0x100441625  sub     edx, 1
0x100441628  jz      short loc_10044164C
0x10044162a  sub     edx, 1
0x10044162d  jz      short loc_100441653
0x10044162f  cmp     edx, 1
0x100441632  jnz     short loc_100441658
0x100441634  test    dword ptr [rdi+40h], 200h
0x10044163b  mov     eax, 804002h
0x100441640  mov     ecx, 14002h
0x100441645  cmovnz  eax, ecx
0x100441648  mov     ecx, eax
0x10044164a  jmp     short loc_100441658
0x10044164c  mov     ecx, 14012h
0x100441651  jmp     short loc_100441658
0x100441653  mov     ecx, 14002h
0x100441658  mov     eax, [rdi+40h]
0x10044165b  test    al, 40h
0x10044165d  mov     r13d, 20000h
0x100441663  cmovz   r13d, r9d
0x100441667  or      r13d, ecx
0x10044166a  test    al, 20h
0x10044166c  jz      short loc_100441672
0x10044166e  or      r13d, 0Ch
0x100441672  mov     r8, [rsp+290h+var_228]
0x100441677  cmp     dword ptr [r8+10h], 0
0x10044167c  jz      loc_100441843
0x100441682  mov     ecx, ebx
0x100441684  add     rcx, rcx
0x100441687  mov     eax, [rdi+88h]
0x10044168d  mov     [rbp+rcx*8+190h+var_168], eax
0x100441691  mov     [rbp+rcx*8+190h+var_164], 2
0x100441699  mov     rax, [rdi+80h]
0x1004416a0  mov     [rbp+rcx*8+190h+var_160], rax
0x1004416a5  inc     ebx
0x1004416a7  test    byte ptr [rdi+40h], 10h
0x1004416ab  jz      loc_100441972
0x1004416b1  lea     rcx, ?ghSspiCred@@3U_SecHandle@@A; _SecHandle ghSspiCred
0x1004416b8  mov     [rbp+190h+var_1B0], rcx
0x1004416bc  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004416c3  jz      short loc_1004416EC
0x1004416c5  lea     r9, aSniusingGlobal; "SNIUsing global credentials handle beca"...
0x1004416cc  mov     r8d, 77Eh; int
0x1004416d2  lea     rdx, aSspiHandshake; "Sspi::Handshake"
0x1004416d9  lea     rcx, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x1004416e0  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004416e5  lea     rcx, ?ghSspiCred@@3U_SecHandle@@A; _SecHandle ghSspiCred
0x1004416ec  mov     rax, [rsp+290h+var_228]
0x1004416f1  mov     [rbp+190h+var_1A4], ebx
0x1004416f4  lea     r14, [rdi+0C0h]
0x1004416fb  lea     r15, [rdi+0C4h]
0x100441702  xor     r9d, r9d
0x100441705  mov     edx, r9d
0x100441708  cmp     [rax+10h], r9d
0x10044170c  cmovnz  rdx, rax
0x100441710  lea     rax, [rbp+190h+var_1A8]
0x100441714  test    ebx, ebx
0x100441716  cmovz   rax, r9
0x10044171a  lea     r8, [rbp+190h+var_190]
0x10044171e  mov     qword ptr [rsp+290h+var_238], r8
0x100441723  lea     r8, [rsp+290h+var_21C]
0x100441728  mov     [rsp+290h+var_240], r8
0x10044172d  lea     r8, [rbp+190h+var_188]
0x100441731  mov     [rsp+290h+var_248], r8
0x100441736  mov     r8, [rsp+290h+var_228]
0x10044173b  mov     [rsp+290h+var_250], r8
0x100441740  mov     dword ptr [rsp+290h+var_258], r9d
0x100441745  mov     [rsp+290h+var_260], rax
0x10044174a  mov     dword ptr [rsp+290h+var_268], 10h
0x100441752  mov     dword ptr [rsp+290h+var_270], r9d
0x100441757  mov     r9d, r13d
0x10044175a  mov     r8, r12
0x10044175d  mov     rax, cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x100441764  call    qword ptr [rax+30h]
0x100441767  mov     ebx, eax
0x100441769  test    eax, eax
0x10044176b  jns     loc_100441984
0x100441771  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100441778  jz      short loc_1004417A1
0x10044177a  lfence
0x10044177d  mov     dword ptr [rsp+290h+var_270], eax
0x100441781  lea     r9, aErrSniinitiali; "ERR|SNIInitializeSecurityContext return"...
0x100441788  mov     r8d, 798h; int
0x10044178e  lea     rdx, aSspiHandshake; "Sspi::Handshake"
0x100441795  lea     rcx, aSqlCommonDkSni_18; "sql\\common\\dk\\sni\\src\\SNI_SspiProv"...
0x10044179c  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x1004417a1  mov     rdx, r14
0x1004417a4  mov     rcx, r15
0x1004417a7  mov     eax, 0Dh
0x1004417ac  mov     dword ptr [rdx], 4
0x1004417b2  mov     [rcx], eax
0x1004417b4  test    r12, r12
0x1004417b7  jz      loc_1004419C2
0x1004417bd  lea     rax, word_1004A26DC
0x1004417c4  cmp     r12, rax
  ... truncated ...
```
