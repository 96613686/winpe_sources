# Ssl::Handshake(void)

- ea: `0x10044d800`
- end: `0x10044efdc`
- name: `?Handshake@Ssl@@UEAAKXZ`
- size: `6108`
- prototype: `unsigned int __fastcall(Ssl *__hidden this)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x100405270`
- `0x100405390`
- `0x10041ec10`
- `0x100423460`
- `0x1004269b0`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x1004474f0`
- `0x100447640`
- `0x1004476e0`
- `0x100448700`
- `0x10044d800`
- `0x1004505f0`
- `0x10045a880`
- `0x10045aa30`
- `0x100486250`
- `0x100486af0`
- `0x100487cd6`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x10044d8a6`
- `KERNEL32!GetTickCount` at `0x10044e67f`
- `KERNEL32!GetTickCount` at `0x10044ef0c`
- `KERNEL32!GetTickCount` at `0x10044d8a6`
- `KERNEL32!GetTickCount` at `0x10044e67f`
- `KERNEL32!GetTickCount` at `0x10044ef0c`
- `KERNEL32!MultiByteToWideChar` at `0x10044df7a`
- `KERNEL32!MultiByteToWideChar` at `0x10044e034`
- `KERNEL32!MultiByteToWideChar` at `0x10044df7a`
- `KERNEL32!MultiByteToWideChar` at `0x10044e034`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10044d969`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10044d969`
- `sqldk!??_V@YAXPEAX@Z` at `0x10044e0b1`
- `sqldk!??_V@YAXPEAX@Z` at `0x10044e116`
- `sqldk!??_V@YAXPEAX@Z` at `0x10044e0b1`
- `sqldk!??_V@YAXPEAX@Z` at `0x10044e116`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10044dffe`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10044dffe`
- `sqldk!SystemThread_TlsIndex` at `0x10044d928`
- `sqldk!SystemThread_TlsIndex` at `0x10044d97e`
- `sqldk!SystemThread_TlsIndex` at `0x10044df8b`
- `sqldk!SystemThread_TlsOffset` at `0x10044d931`
- `sqldk!SystemThread_TlsOffset` at `0x10044d987`
- `sqldk!SystemThread_TlsOffset` at `0x10044df94`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044d94c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044d9a2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044dfaf`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044d94c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044d9a2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044dfaf`
- `api-ms-win-crt-convert-l1-1-0!mbstowcs_s` at `0x10044e7a4`
- `api-ms-win-crt-convert-l1-1-0!mbstowcs_s` at `0x10044ea08`
- `api-ms-win-crt-convert-l1-1-0!mbstowcs_s` at `0x10044e7a4`
- `api-ms-win-crt-convert-l1-1-0!mbstowcs_s` at `0x10044ea08`
- `api-ms-win-crt-string-l1-1-0!wmemcpy_s` at `0x10044e821`
- `api-ms-win-crt-string-l1-1-0!wmemcpy_s` at `0x10044ea85`
- `api-ms-win-crt-string-l1-1-0!wmemcpy_s` at `0x10044e821`
- `api-ms-win-crt-string-l1-1-0!wmemcpy_s` at `0x10044ea85`

## string_xrefs

- `0x10044e03e`: `sql\common\dk\sni\src\sni.cpp`
- `0x10044e0d5`: `sql\common\dk\sni\src\sni.cpp`
- `0x10044dc45`: `SNIInitializeSecurityContext return value: %d{DWORD}\n`
- `0x10044dc73`: `ERR|SNIInitializeSecurityContext return value: %d{DWORD}\n`
- `0x10044e244`: `SNIAcceptSecurityContext return value: %d{DWORD}\n`
- `0x10044e269`: `ERR|SNIAcceptSecurityContext return value: %d{DWORD}\n`
- `0x10044d842`: `sql\common\dk\sni\src\SNI_SslProvider.cpp`
- `0x10044df3c`: `sql\common\dk\sni\src\SNI_SslProvider.cpp`
- `0x10044dfed`: `sql\common\dk\sni\src\SNI_SslProvider.cpp`
- `0x10044e107`: `sql\common\dk\sni\src\SNI_SslProvider.cpp`
- `0x10044e18d`: `sql\common\dk\sni\src\SNI_SslProvider.cpp`
- `0x10044e5a6`: `sql\common\dk\sni\src\SNI_SslProvider.cpp`
- `0x10044eef3`: `sql\common\dk\sni\src\SNI_SslProvider.cpp`
- `0x10044e413`: `Unspecified Protocol`
- `0x10044e3b7`: `CYLINK MEK`
- `0x10044dc17`: `SNIInitializeSecurityContext ContextAttribute dwSSPIOutFlags: %d{DWORD}\n`
- `0x10044e213`: `SNIAcceptSecurityContext ContextAttribute dwSSPIOutFlags: %d{DWORD}\n`
- `0x10044e592`: `SNISecurity Handshake failed. SslVersion: %hs `
- `0x10044e4ca`: `SNISecurity Handshake failed. PeerAddr: %hs `
- `0x10044e488`: `SNISecurity Handshake Handshake succeeded. Protocol: %hs (%d), Cipher: %hs (%d), Cipher Strength: %d, Hash: %hs (%d), Hash Strength: %d, PeerAddr: %ls\n`
- `0x10044ed2a`: `ERR|SNIBufferType for OutBuffer[0] is invalid: %d{ULONG}, expected: 2, SECBUFFER_TOKEN\n`
- `0x10044e719`: `ProtocolMismatch`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
__int64 __fastcall Ssl::Handshake(Ssl *this)
{
  unsigned int v2; // r13d
  __int64 v3; // rbx
  DWORD v4; // edx
  int v5; // eax
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rbx
  __int64 v11; // rdx
  int v12; // ecx
  int v13; // eax
  __int64 v14; // r9
  signed __int32 v15; // r8d
  __int64 v16; // rdx
  int v17; // eax
  __int64 v18; // rax
  int v19; // edx
  char *v20; // r10
  char *v21; // r11
  int v22; // eax
  struct _SecHandle *v23; // rcx
  int *v24; // rax
  int v25; // ebx
  char v26; // cl
  int v27; // eax
  signed __int32 v28; // edx
  __int64 v29; // r8
  int v30; // eax
  __int64 v31; // rax
  int v32; // ecx
  unsigned int v33; // r8d
  _BYTE *v34; // rcx
  BOOL v35; // r15d
  int v36; // r12d
  unsigned int v37; // edx
  unsigned int v38; // r8d
  int v39; // edx
  unsigned int v40; // r11d
  __int64 v41; // rbx
  unsigned __int8 *v42; // r10
  unsigned int v43; // ecx
  int v44; // eax
  unsigned int v45; // r8d
  unsigned int v46; // ecx
  unsigned __int8 *v47; // r9
  int v48; // ecx
  __int64 v49; // r8
  unsigned int v50; // ecx
  unsigned __int8 *v51; // r10
  unsigned int v52; // ecx
  unsigned int v53; // r11d
  int v54; // esi
  __int64 v55; // rbx
  __int64 v56; // rax
  __int64 v57; // rcx
  unsigned __int64 v58; // rbx
  unsigned __int64 v59; // rax
  WCHAR *v60; // rax
  WCHAR *v61; // r14
  const wchar_t *v62; // r9
  __int64 v63; // rbx
  SNI_Conn *v64; // rcx
  unsigned int v65; // esi
  void *v66; // rcx
  char v67; // al
  __int64 v68; // r9
  char *v69; // rdx
  char v70; // al
  int v71; // esi
  const char *v72; // r10
  const char *v73; // rdx
  const char *v74; // rcx
  int v75; // eax
  const wchar_t *v76; // r9
  __int64 v77; // rbx
  DWORD v78; // edx
  int v79; // r14d
  __int64 v80; // rax
  __int64 v81; // rcx
  rsize_t v82; // r15
  size_t v83; // rax
  __int64 v84; // rdx
  int v85; // eax
  __int64 v86; // rax
  __int64 v87; // rcx
  void (__fastcall *v88)(__int64, __int64, __int64); // rax
  __int64 v89; // rcx
  void (__fastcall *v90)(__int64, _QWORD, __int64); // rax
  int v91; // eax
  rsize_t v92; // r15
  size_t v93; // rax
  __int64 v94; // rdx
  int v95; // eax
  __int64 v96; // rax
  __int64 v97; // rcx
  __int64 Ex2; // rax
  __int64 v99; // rsi
  int v100; // ebx
  __int64 v101; // rdi
  DWORD v102; // edx
  int v103; // eax
  __int64 v104; // rax
  LPWSTR lpWideCharStr; // [rsp+28h] [rbp-E0h]
  int cchWideChar[2]; // [rsp+30h] [rbp-D8h]
  __int64 v108; // [rsp+38h] [rbp-D0h]
  __int64 v109; // [rsp+40h] [rbp-C8h]
  __int64 v110; // [rsp+48h] [rbp-C0h]
  __int64 v111; // [rsp+58h] [rbp-B0h]
  __int64 v112; // [rsp+60h] [rbp-A8h]
  int v113; // [rsp+78h] [rbp-90h] BYREF
  int cbMultiByte; // [rsp+7Ch] [rbp-8Ch] BYREF
  unsigned int v115; // [rsp+80h] [rbp-88h] BYREF
  int v116; // [rsp+84h] [rbp-84h] BYREF
  int v117; // [rsp+88h] [rbp-80h] BYREF
  int v118; // [rsp+8Ch] [rbp-7Ch]
  _DWORD *v119; // [rsp+90h] [rbp-78h]
  int v120; // [rsp+98h] [rbp-70h] BYREF
  __int64 v121; // [rsp+A0h] [rbp-68h]
  int v122; // [rsp+A8h] [rbp-60h] BYREF
  int v123; // [rsp+ACh] [rbp-5Ch]
  __int64 v124; // [rsp+B0h] [rbp-58h]
  int v125; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v126; // [rsp+C0h] [rbp-48h]
  __int64 v127; // [rsp+C8h] [rbp-40h]
  __int64 v128; // [rsp+D0h] [rbp-38h]
  __int64 v129; // [rsp+D8h] [rbp-30h]
  bool v130; // [rsp+E8h] [rbp-20h]
  LPCCH lpMultiByteStr; // [rsp+F8h] [rbp-10h] BYREF
  unsigned int v132; // [rsp+100h] [rbp-8h] BYREF
  int v133; // [rsp+104h] [rbp-4h]
  __int64 v134; // [rsp+108h] [rbp+0h]
  _DWORD v135[2]; // [rsp+110h] [rbp+8h] BYREF
  unsigned int *v136; // [rsp+118h] [rbp+10h]
  char *v137; // [rsp+120h] [rbp+18h]
  char *v138; // [rsp+128h] [rbp+20h]
  int v139; // [rsp+130h] [rbp+28h]
  __int128 v140; // [rsp+138h] [rbp+30h] BYREF
  __int64 v141; // [rsp+148h] [rbp+40h]
  const char *v142; // [rsp+150h] [rbp+48h]
  const char *v143; // [rsp+158h] [rbp+50h]
  int v144; // [rsp+160h] [rbp+58h]
  int v145; // [rsp+168h] [rbp+60h] BYREF
  unsigned int v146; // [rsp+16Ch] [rbp+64h]
  int v147; // [rsp+170h] [rbp+68h]
  int v148; // [rsp+174h] [rbp+6Ch]
  int v149; // [rsp+178h] [rbp+70h]
  _DWORD v150[8]; // [rsp+188h] [rbp+80h] BYREF
  _BYTE v151[112]; // [rsp+1A8h] [rbp+A0h] BYREF
  _WORD v152[2]; // [rsp+218h] [rbp+110h] BYREF
  int v153; // [rsp+21Ch] [rbp+114h]
  unsigned __int8 v154; // [rsp+220h] [rbp+118h]
  _BYTE Src[263]; // [rsp+221h] [rbp+119h] BYREF
  _DWORD v156[2]; // [rsp+328h] [rbp+220h] BYREF
  __int64 v157; // [rsp+330h] [rbp+228h]
  size_t Size; // [rsp+338h] [rbp+230h]
  __int64 v159; // [rsp+340h] [rbp+238h]
  int v160; // [rsp+348h] [rbp+240h]
  int v161; // [rsp+34Ch] [rbp+244h]
  char *v162; // [rsp+350h] [rbp+248h]
  char SrcBuf[32]; // [rsp+358h] [rbp+250h] BYREF
  wchar_t DstBuf[256]; // [rsp+378h] [rbp+270h] BYREF
  wchar_t S2[256]; // [rsp+578h] [rbp+470h] BYREF

  v141 = -2;
  v137 = "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp";
  v138 = "Ssl::Handshake";
  v139 = 2118;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
      "Ssl::Handshake",
      2118,
      L"API|SNI%u#\n",
      *((_DWORD *)this + 11));
  v2 = 0;
  v113 = 0;
  v3 = *((_QWORD *)this + 4);
  if ( (*(_BYTE *)(v3 + 12946) & 1) != 0 )
  {
    v4 = GetTickCount() - *(_DWORD *)(v3 + 80);
    if ( *(int *)(v3 + 12552) < 82 )
    {
      v5 = _InterlockedIncrement((volatile signed __int32 *)(v3 + 12552));
      if ( v5 < 82 )
      {
        v6 = 152LL * (v5 - 1);
        *(_DWORD *)(v6 + v3 + 88) = 2;
        *(_DWORD *)(v6 + v3 + 92) = v4;
        *(_QWORD *)(v6 + v3 + 96) = 0;
        *(_DWORD *)(v6 + v3 + 232) = 0;
      }
    }
  }
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v120, 1);
  *(_QWORD *)&v140 = &v122;
  v125 = 536871395;
  v126 = 0;
  v128 = 0;
  v127 = 0;
  v129 = 0;
  v130 = 0;
  v7 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v8 = *(_QWORD *)(v7 + 256);
  if ( !v8 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v8 = *(_QWORD *)(v7 + 256);
  }
  v9 = *(_QWORD *)(v8 + 600);
  if ( v9 )
    v130 = (unsigned int)SOS_Task::PushWait(v9, &v125) == 0;
  v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v11 = *(_QWORD *)(v10 + 256);
  if ( !v11 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v11 = *(_QWORD *)(v10 + 256);
  }
  v124 = v11;
  v123 = (*(_DWORD *)(v11 + 800) >> 11) & 1;
  if ( v123 || (*(_BYTE *)(v11 + 800) & 4) == 0 )
  {
    v122 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v11 + 608) + 8LL))(*(_QWORD *)(v11 + 608));
  }
  else
  {
    v122 = 0;
  }
  while ( 1 )
  {
    *((_DWORD *)this + 34) -= *((_DWORD *)this + 44) + *((_DWORD *)this + 45);
    CryptoBase::ProcessInputBuffer(this);
    v157 = *((_QWORD *)this + 16);
    v156[0] = *((_DWORD *)this + 34);
    v156[1] = 2;
    v159 = 0;
    Size = 0;
    if ( !*(_DWORD *)(*((_QWORD *)this + 4) + 4LL) || *((_DWORD *)this + 12) )
    {
      v118 = 2;
    }
    else
    {
      v161 = 18;
      v162 = (char *)this + 408;
      v160 = *((_DWORD *)this + 230);
      v118 = 3;
    }
    v117 = 0;
    v119 = v156;
    v134 = *((_QWORD *)this + 19);
    v133 = 2;
    v132 = Ssl::s_cbMaxToken;
    v135[1] = 1;
    v136 = &v132;
    v135[0] = 0;
    CryptoBase::SetLoginEvent(this, 2);
    if ( (*(_BYTE *)(*((_QWORD *)this + 4) + 12804LL) & 2) == 0 )
    {
      v28 = _InterlockedIncrement(&Ssl::s_cAcceptSecurityContext);
      v29 = *((_QWORD *)this + 4);
      if ( (*(_BYTE *)(v29 + 12946) & 1) != 0 && *(int *)(v29 + 12552) < 82 )
      {
        v30 = _InterlockedIncrement((volatile signed __int32 *)(v29 + 12552));
        if ( v30 < 82 )
        {
          v31 = 152LL * (v30 - 1);
          *(_DWORD *)(v31 + v29 + 88) = 4;
          *(_DWORD *)(v31 + v29 + 92) = v28;
          *(_QWORD *)(v31 + v29 + 96) = 0;
          *(_DWORD *)(v31 + v29 + 232) = 0;
        }
      }
      v115 = 0;
      v32 = *((_DWORD *)this + 16);
      if ( (v32 & 0x400000) == 0 )
        goto LABEL_123;
      v33 = *v119;
      v34 = (_BYTE *)*((_QWORD *)v119 + 1);
      v35 = 0;
      v36 = 0;
      lpMultiByteStr = 0;
      cbMultiByte = 0;
      if ( v33 < 5 )
        goto LABEL_94;
      if ( *v34 != 22 )
      {
        v35 = 1;
        goto LABEL_117;
      }
      v37 = (unsigned __int8)v34[4] | ((unsigned __int8)v34[3] << 8);
      if ( v33 < v37 + 5 )
        goto LABEL_94;
      if ( v34[5] != 1 )
        goto LABEL_117;
      v38 = (unsigned __int8)v34[8] + ((unsigned __int8)v34[6] << 16) + ((unsigned __int8)v34[7] << 8);
      if ( v37 < v38 )
      {
LABEL_94:
        v39 = -2147024883;
      }
      else
      {
        v39 = 0;
        v116 = 0;
        if ( v38 >= 2 )
        {
          v40 = ((unsigned __int8)v34[9] << 8) + (unsigned __int8)v34[10];
          if ( v40 >= 0x300 )
          {
            if ( v38 - 2 >= 0x20 )
            {
              if ( v38 == 34 )
              {
                v39 = -2146893018;
              }
              else
              {
                v41 = (unsigned __int8)v34[43];
                if ( (unsigned int)v41 <= 0x20 )
                {
                  if ( v38 - 35 >= (unsigned int)v41 )
                  {
                    v42 = &v34[v41 + 44];
                    v43 = v38 - 35 - v41;
                    if ( v43 >= 2 )
                    {
                      _mm_lfence();
                      v44 = v42[1];
                      v45 = v44 + (*v42 << 8);
                      if ( (v44 & 1) != 0 )
                      {
                        v39 = -2146893018;
                      }
                      else
                      {
                        v46 = v43 - 2;
                        if ( v46 >= v45 )
                        {
                          v47 = &v42[v45 + 2];
                          v48 = v46 - v45;
                          if ( v48 )
                          {
                            _mm_lfence();
                            v49 = *v47;
                            if ( *v47 )
                            {
                              v50 = v48 - 1;
                              if ( v50 >= (unsigned int)v49 )
                              {
                                v51 = &v47[v49];
                                v52 = v50 - v49;
                                if ( v40 < 0x301
                                  || v52 >= 2
                                  && (_mm_lfence(), v53 = (v51[1] << 8) | v51[2], v52 - 2 >= v53)
                                  && (_mm_lfence(),
                                      v39 = ParseTlsHelloExtensions(
                                              v51 + 3,
                                              v53,
                                              &v116,
                                              (unsigned __int8 **)&lpMultiByteStr,
                                              (unsigned int *)&cbMultiByte,
                                              &v115),
                                      v39 >= 0) )
                                {
                                  if ( !(_DWORD)v41 && !v116 )
                                    v36 = 1;
                                }
                                v35 = v39 >= 0;
                                if ( !v39 )
                                {
LABEL_97:
                                  if ( v35 && cbMultiByte && lpMultiByteStr )
                                  {
                                    v54 = MultiByteToWideChar(0, 0, lpMultiByteStr, cbMultiByte, 0, 0);
                                    v55 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                        + SystemThread_TlsOffset;
                                    v56 = *(_QWORD *)(v55 + 256);
                                    if ( !v56 )
                                    {
                                      SystemThread::MakeMiniSOSThread(0);
                                      v56 = *(_QWORD *)(v55 + 256);
                                    }
                                    v57 = *(_QWORD *)(*(_QWORD *)(v56 + 992) + 56LL);
                                    v58 = v54 + 1;
                                    v59 = 2 * v58;
                                    if ( !is_mul_ok(v58, 2u) )
                                      v59 = -1;
                                    v60 = (WCHAR *)operator new[](
                                                     v59,
                                                     *(struct IMemObj **)(v57 + 8),
                                                     1,
                                                     "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
                                                     2297,
                                                     6u);
                                    v61 = v60;
                                    if ( !v60 )
                                      goto LABEL_266;
                                    memset_0(v60, 0, 2 * v58);
                                    MultiByteToWideChar(0, 0, lpMultiByteStr, cbMultiByte, v61, v54);
                                    v63 = *((_QWORD *)this + 4);
                                    v142 = "sql\\common\\dk\\sni\\src\\sni.cpp";
                                    v64 = (SNI_Conn *)"SNI_Conn::SetSniServerName";
                                    v143 = "SNI_Conn::SetSniServerName";
                                    v144 = 1245;
                                    if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
                                      SNIXE_SNI_ENTER_ON(
                                        "sql\\common\\dk\\sni\\src\\sni.cpp",
                                        "SNI_Conn::SetSniServerName",
                                        1245,
                                        L"API|SNIm_SniServerName: \"%s\"\n",
                                        v61);
                                    v65 = 0;
                                    if ( !*(_QWORD *)(v63 + 12872) )
                                    {
                                      v65 = SNI_Conn::AllocAndSetName(v64, (wchar_t **)(v63 + 12872), v61, 1);
                                      if ( v65 )
                                      {
                                        v66 = *(void **)(v63 + 12872);
                                        if ( v66 )
                                        {
                                          operator delete[](v66);
                                          *(_QWORD *)(v63 + 12872) = 0;
                                        }
                                      }
                                    }
                                    v67 = g_XeSniPkg_enabledBitmap;
                                    if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
                                    {
                                      SNIXE_SNI_LEAVE_ON(
                                        "sql\\common\\dk\\sni\\src\\sni.cpp",
                                        "SNI_Conn::SetSniServerName",
                                        1245,
                                        v62);
                                      v67 = g_XeSniPkg_enabledBitmap;
                                    }
                                    if ( v65 && (v67 & 1) != 0 )
                                    {
                                      LODWORD(lpWideCharStr) = v65;
                                      SNIXE_SNI_TRACE_ON(
                                        "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
                                        "Ssl::Handshake",
                                        2324,
                                        L"SNILogging SNI Server Name failed. SetSniServerName returned: %d ",
                                        lpWideCharStr);
                                    }
                                    operator delete[](v61);
                                  }
LABEL_117:
                                  v32 = *((_DWORD *)this + 16);
                                  if ( (v32 & 0x40000) != 0 )
                                  {
                                    GetTlsVersion(*((unsigned __int8 **)v119 + 1), *v119, &v115);
                                    v32 = *((_DWORD *)this + 16);
                                    if ( v35 )
                                    {
                                      if ( v36
                                        && (v115 < ((*((_DWORD *)this + 16) >> 19) & 7u) + 768
                                         || v115 < 0x300
                                         || v115 > 0x303) )
                                      {
                                        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
                                        {
                                          LODWORD(lpWideCharStr) = v115;
                                          SNIXE_SNI_TRACE_ON(
                                            "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
                                            "Ssl::Handshake",
                                            2351,
                                            L"SNISecurity Handshake failed. SslVersion: %hs ",
                                            lpWideCharStr);
                                        }
                                        *((_DWORD *)this + 48) = 4;
                                        *((_DWORD *)this + 49) = 21;
                                        v25 = -2146893048;
                                        AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v122);
                                        goto LABEL_285;
                                      }
                                    }
                                  }
LABEL_123:
                                  v68 = 49212;
                                  if ( (v32 & 0x400) != 0 )
                                    v68 = 573502;
                                  v69 = 0;
                                  if ( *((_DWORD *)this + 12) )
                                    v69 = (char *)this + 392;
                                  LODWORD(lpWideCharStr) = 16;
                                  v25 = ((__int64 (__fastcall *)(_QWORD, char *, int *, __int64, LPWSTR, char *, _DWORD *, int *, _QWORD))Ssl::s_pfTable->AcceptSecurityContext)(
                                          0,
                                          v69,
                                          &v117,
                                          v68,
                                          lpWideCharStr,
                                          (char *)this + 392,
                                          v135,
                                          &v113,
                                          0);
                                  _InterlockedDecrement(&Ssl::s_cAcceptSecurityContext);
                                  v70 = g_XeSniPkg_enabledBitmap;
                                  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
                                  {
                                    LODWORD(lpWideCharStr) = v113;
                                    SNIXE_SNI_TRACE_ON(
                                      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
                                      "Ssl::Handshake",
                                      2399,
                                      L"SNIAcceptSecurityContext ContextAttribute dwSSPIOutFlags: %d{DWORD}\n",
                                      lpWideCharStr);
                                    v70 = g_XeSniPkg_enabledBitmap;
                                  }
                                  if ( v25 < 0 )
                                  {
                                    if ( (v70 & 2) == 0 )
                                    {
LABEL_135:
                                      if ( (v70 & 1) != 0 )
                                      {
                                        v71 = ((__int64 (__fastcall *)(char *, __int64, int *))Ssl::s_pfTable->QueryContextAttributesW)(
                                                (char *)this + 392,
                                                90,
                                                &v145);
                                        SNIGetInfo(*((_QWORD *)this + 4), 17, v151);
                                        if ( v25 )
                                        {
                                          if ( v25 != -2146893032
                                            && (unsigned int)(v25 - 590610) > 2
                                            && (g_XeSniPkg_enabledBitmap & 1) != 0 )
                                          {
                                            SNIXE_SNI_TRACE_ON(
                                              "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
                                              "Ssl::Handshake",
                                              2442,
                                              L"SNISecurity Handshake failed. PeerAddr: %hs ",
                                              v151);
                                          }
                                          goto LABEL_186;
                                        }
                                        if ( !v71 && (g_XeSniPkg_enabledBitmap & 1) != 0 )
                                        {
                                          switch ( v148 )
                                          {
                                            case 32771:
                                              v72 = "MD5";
                                              break;
                                            case 32772:
                                              v72 = "SHA";
                                              break;
                                            case 32773:
                                              v72 = "MAC";
                                              break;
                                            case 32780:
                                              v72 = "SHA 256";
                                              break;
                                            case 32781:
                                              v72 = "SHA 384";
                                              break;
                                            case 32782:
                                              v72 = "SHA 512";
                                              break;
                                            default:
                                              v72 = "Unspecified Hash";
                                              break;
                                          }
                                          if ( v146 > 0x660A )
                                          {
                                            if ( v146 > 0x6610 )
                                            {
                                              if ( v146 == 26129 )
                                              {
                                                v73 = "AES";
                                                goto LABEL_170;
                                              }
                                              if ( v146 == 26625 )
                                              {
                                                v73 = "RC4";
                                                goto LABEL_170;
                                              }
                                            }
                                            else
                                            {
                                              switch ( v146 )
                                              {
                                                case 0x6610u:
                                                  v73 = "AES 256";
                                                  goto LABEL_170;
                                                case 0x660Cu:
                                                  v73 = "CYLINK MEK";
                                                  goto LABEL_170;
                                                case 0x660Du:
                                                  v73 = "RC5";
                                                  goto LABEL_170;
                                                case 0x660Eu:
                                                  v73 = "AES 128";
                                                  goto LABEL_170;
                                              }
                                            }
                                          }
                                          else
                                          {
                                            switch ( v146 )
                                            {
                                              case 0x660Au:
                                                v73 = "SKIPJACK";
                                                goto LABEL_170;
                                              case 0x6601u:
                                                v73 = "DES";
                                                goto LABEL_170;
                                              case 0x6602u:
                                                v73 = "RC2";
                                                goto LABEL_170;
                                              case 0x6603u:
                                                v73 = "Triple DES";
LABEL_170:
                                                switch ( v145 )
                                                {
                                                  case 4:
                                                    v74 = "SSL2.0";
                                                    break;
                                                  case 16:
                                                    v74 = "SSL3.0";
                                                    break;
                                                  case 64:
                                                    v74 = "TLS1.0";
                                                    break;
                                                  case 256:
                                                    v74 = "TLS1.1";
                                                    break;
                                                  default:
                                                    v74 = "Unspecified Protocol";
                                                    if ( v145 == 1024 )
                                                      v74 = "TLS1.2";
                                                    break;
                                                }
                                                LODWORD(v112) = v149;
                                                LODWORD(v111) = v148;
                                                LODWORD(v110) = v147;
                                                LODWORD(v109) = v146;
                                                cchWideChar[0] = v145;
                                                SNIXE_SNI_TRACE_ON(
                                                  "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
                                                  "Ssl::Handshake",
                                                  2434,
                                                  L"SNISecurity Handshake Handshake succeeded. Protocol: %hs (%d), Cipher:"
                                                   " %hs (%d), Cipher Strength: %d, Hash: %hs (%d), Hash Strength: %d, PeerAddr: %ls\n",
                                                  v74,
                                                  *(_QWORD *)cchWideChar,
                                                  v73,
                                                  v109,
                                                  v110,
                                                  v72,
                                                  v111,
                                                  v112,
                                                  v151);
                                                goto LABEL_186;
                                            }
                                          }
                                          v73 = "Unspecified Cipher";
                                          goto LABEL_170;
                                        }
                                      }
LABEL_186:
                                      v27 = 20;
                                      goto LABEL_187;
                                    }
                                    _mm_lfence();
                                    LODWORD(lpWideCharStr) = v25;
                                    SNIXE_SNI_ERROR_ON(
                                      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
                                      "Ssl::Handshake",
                                      2401,
                                      L"ERR|SNIAcceptSecurityContext return value: %d{DWORD}\n",
                                      lpWideCharStr);
                                  }
                                  else
                                  {
                                    if ( (v70 & 1) == 0 )
                                      goto LABEL_186;
                                    _mm_lfence();
                                    LODWORD(lpWideCharStr) = v25;
                                    SNIXE_SNI_TRACE_ON(
                                      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
                                      "Ssl::Handshake",
                                      2401,
                                      L"SNIAcceptSecurityContext return value: %d{DWORD}\n",
                                      lpWideCharStr);
                                  }
                                  v70 = g_XeSniPkg_enabledBitmap;
                                  goto LABEL_135;
                                }
                              }
                              else
                              {
                                v39 = -2146893018;
                              }
                            }
                            else
                            {
                              v39 = -2146893018;
                            }
                          }
                          else
                          {
                            v39 = -2146893018;
                          }
                        }
                        else
                        {
                          v39 = -2146893018;
                        }
                      }
                    }
                    else
                    {
                      v39 = -2146893018;
                    }
                  }
                  else
                  {
                    v39 = -2146893018;
                  }
                }
                else
                {
                  v39 = -2146893018;
                }
              }
            }
            else
            {
              v39 = -2146893018;
            }
          }
          else
          {
            v39 = -2146893018;
          }
        }
        else
        {
          v39 = -2146893018;
        }
      }
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(lpWideCharStr) = v39;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
          "Ssl::Handshake",
          2281,
          L"SNIParsing SNI Server Name failed. ParseClientMessage returned: %d ",
          lpWideCharStr);
      }
      goto LABEL_97;
    }
    v12 = *((_DWORD *)this + 16);
    v13 = 49340;
    if ( (v12 & 0x7000) == 0 )
      v13 = 49212;
    v14 = v13 | ~(*((_DWORD *)this + 16) << 19) & 0x80000u;
    if ( (v12 & 0x20000) != 0 )
      LODWORD(v14) = v14 | 0x10000;
    v15 = _InterlockedIncrement(&Ssl::s_cInitializeSecurityContext);
    v16 = *(_QWORD *)(*((_QWORD *)this + 4) + 12952LL);
    if ( v16 )
    {
      if ( (*(_BYTE *)(v16 + 12946) & 1) != 0 && *(int *)(v16 + 12552) < 82 )
      {
        v17 = _InterlockedIncrement((volatile signed __int32 *)(v16 + 12552));
        if ( v17 < 82 )
        {
          v18 = 152LL * (v17 - 1);
          *(_DWORD *)(v18 + v16 + 88) = 5;
          *(_DWORD *)(v18 + v16 + 92) = v15;
          *(_QWORD *)(v18 + v16 + 96) = 0;
          *(_DWORD *)(v18 + v16 + 232) = 0;
        }
      }
    }
    v19 = *((_DWORD *)this + 12);
    v20 = (char *)this + 392;
    if ( v19 )
      v20 = 0;
    v21 = 0;
    if ( v19 )
      v21 = (char *)this + 392;
    v22 = *((_DWORD *)this + 16);
    if ( (v22 & 2) != 0 )
    {
      v23 = &Ssl::s_hClientCred;
      if ( (v22 & 1) != 0 )
        v23 = &Ssl::s_hClientCredValidate;
    }
    else
    {
      v23 = (struct _SecHandle *)((char *)this + 376);
    }
    v24 = &v117;
    if ( !v19 )
      v24 = 0;
    LODWORD(v109) = 0;
    cchWideChar[0] = 16;
    LODWORD(lpWideCharStr) = 0;
    v25 = ((__int64 (__fastcall *)(struct _SecHandle *, char *, _QWORD, __int64, LPWSTR, _QWORD, int *, __int64, char *, _DWORD *, int *, _QWORD))Ssl::s_pfTable->InitializeSecurityContextW)(
            v23,
            v21,
            *(_QWORD *)(*((_QWORD *)this + 4) + 12608LL),
            v14,
            lpWideCharStr,
            *(_QWORD *)cchWideChar,
            v24,
            v109,
            v20,
            v135,
            &v113,
            0);
    _InterlockedDecrement(&Ssl::s_cInitializeSecurityContext);
    v26 = g_XeSniPkg_enabledBitmap;
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(lpWideCharStr) = v113;
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
        "Ssl::Handshake",
        2244,
        L"SNIInitializeSecurityContext ContextAttribute dwSSPIOutFlags: %d{DWORD}\n",
        lpWideCharStr);
      v26 = g_XeSniPkg_enabledBitmap;
    }
    if ( v25 < 0 )
    {
      if ( (v26 & 2) != 0 )
      {
        _mm_lfence();
        LODWORD(lpWideCharStr) = v25;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
          "Ssl::Handshake",
          2246,
          L"ERR|SNIInitializeSecurityContext return value: %d{DWORD}\n",
          lpWideCharStr);
      }
LABEL_49:
      v27 = 19;
      goto LABEL_187;
    }
    if ( (v26 & 1) == 0 )
      goto LABEL_49;
    _mm_lfence();
    LODWORD(lpWideCharStr) = v25;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
      "Ssl::Handshake",
      2246,
      L"SNIInitializeSecurityContext return value: %d{DWORD}\n",
      lpWideCharStr);
    v27 = 19;
LABEL_187:
    *((_DWORD *)this + 48) = 4;
    *((_DWORD *)this + 49) = v27;
    CryptoBase::SetLoginEvent(this, 2);
    v75 = *((_DWORD *)this + 12);
    if ( !v75 || v75 == 7 )
      *((_DWORD *)this + 12) = 1;
    if ( !v25 )
      break;
    if ( v25 != 590610 )
    {
      if ( (*((_DWORD *)this + 16) & 0x10000) != 0 && v25 == -2146893032 )
      {
        *((_DWORD *)this + 12) = 7;
        *((_DWORD *)this + 54) = 1;
        goto LABEL_199;
      }
      v81 = *((_QWORD *)this + 4);
      if ( *(_DWORD *)(v81 + 4) && v25 == -2146892953 )
      {
        strcpy(SrcBuf, "ProtocolMismatch");
        *((_DWORD *)this + 231) = 0x20000;
        strcpy((char *)this + 928, "ProtocolMismatch");
        if ( v81 )
        {
          memset_0(DstBuf, 0, sizeof(DstBuf));
          v82 = -1;
          v83 = -1;
          do
            ++v83;
          while ( SrcBuf[v83] );
          mbstowcs_s(0, DstBuf, 0xFFu, SrcBuf, v83);
          v84 = *((_QWORD *)this + 4);
          if ( (*(_BYTE *)(v84 + 12946) & 1) != 0 && *(int *)(v84 + 12552) < 82 )
          {
            v85 = _InterlockedIncrement((volatile signed __int32 *)(v84 + 12552));
            if ( v85 < 82 )
            {
              _mm_lfence();
              v86 = 152LL * (v85 - 1);
              *(_DWORD *)(v86 + v84 + 88) = 79;
              *(_DWORD *)(v86 + v84 + 232) = 2;
              do
                ++v82;
              while ( DstBuf[v82] );
              wmemcpy_s((wchar_t *)(v86 + v84 + 104), 0x3Fu, DstBuf, v82);
            }
          }
        }
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v108) = -2146892953;
          cchWideChar[0] = 0;
          LODWORD(lpWideCharStr) = 6;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
            "Ssl::Handshake",
            2677,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            lpWideCharStr,
            *(_QWORD *)cchWideChar,
            v108);
        }
        SNISetLastError(6, 2148074343LL, 50100);
        v87 = *((_QWORD *)this + 4);
        if ( v87 )
        {
          v88 = *(void (__fastcall **)(__int64, __int64, __int64))(v87 + 12656);
          if ( v88 )
            v88(v87, 2148074343LL, 50100);
        }
      }
      else
      {
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v108) = v25;
          cchWideChar[0] = 0;
          LODWORD(lpWideCharStr) = 6;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
            "Ssl::Handshake",
            2686,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            lpWideCharStr,
            *(_QWORD *)cchWideChar,
            v108);
        }
        SNISetLastError(6, (unsigned int)v25, 50100);
        v89 = *((_QWORD *)this + 4);
        if ( v89 )
        {
          v90 = *(void (__fastcall **)(__int64, _QWORD, __int64))(v89 + 12656);
          if ( v90 )
            v90(v89, (unsigned int)v25, 50100);
        }
      }
LABEL_280:
      AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v122);
      goto LABEL_285;
    }
    if ( HIDWORD(Size) != 5 )
    {
      *((_DWORD *)this + 34) = 0;
      *((_DWORD *)this + 40) = 0;
      *((_DWORD *)this + 41) = v132;
      CryptoBase::FormatOutputBuffer(this);
      *((_DWORD *)this + 41) += *((_DWORD *)this + 46) + *((_DWORD *)this + 47);
LABEL_199:
      CryptoBase::SetLoginEvent(this, 3);
      AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v122);
      *(_DWORD *)(v121 + 616) &= ~v120;
      CryptoBase::SetLoginEvent(this, 3);
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
          "Ssl::Handshake",
          2702,
          L"RET|SNI%d{WINERR}\n",
          0);
      v77 = *((_QWORD *)this + 4);
      if ( (*(_BYTE *)(v77 + 12946) & 1) != 0 )
      {
        v78 = GetTickCount() - *(_DWORD *)(v77 + 80);
        if ( *(int *)(v77 + 12552) < 82 )
        {
          v79 = _InterlockedIncrement((volatile signed __int32 *)(v77 + 12552));
          if ( v79 < 82 )
          {
            v80 = 152LL * (v79 - 1);
            *(_DWORD *)(v80 + v77 + 88) = 3;
            *(_DWORD *)(v80 + v77 + 92) = v78;
            *(_QWORD *)(v80 + v77 + 96) = 0;
            *(_DWORD *)(v80 + v77 + 232) = 0;
          }
        }
      }
      goto LABEL_292;
    }
    memmove(
      *((void **)this + 16),
      (const void *)(*((_QWORD *)this + 16) + v156[0] - (unsigned __int64)(unsigned int)Size),
      (unsigned int)Size);
    *((_DWORD *)this + 34) = Size;
  }
  if ( !*(_DWORD *)(*((_QWORD *)this + 4) + 4LL) )
    goto LABEL_248;
  memset_0(v152, 0, 0x108u);
  strcpy((char *)&v140, "NoAlpnExtnFound");
  v25 = ((__int64 (__fastcall *)(char *, __int64, _WORD *))Ssl::s_pfTable->QueryContextAttributesW)(
          (char *)this + 392,
          35,
          v152);
  if ( !v25 )
  {
    *((_WORD *)this + 462) = v152[0];
    v91 = v153;
    *((_WORD *)this + 463) = v153;
    if ( v91 == 2 )
      memmove((char *)this + 928, Src, v154);
    else
      *((_OWORD *)this + 58) = v140;
    if ( *((_QWORD *)this + 4) )
    {
      memset_0(S2, 0, sizeof(S2));
      v92 = -1;
      v93 = -1;
      do
        ++v93;
      while ( *((_BYTE *)this + v93 + 928) );
      mbstowcs_s(0, S2, 0xFFu, (const char *)this + 928, v93);
      v94 = *((_QWORD *)this + 4);
      if ( (*(_BYTE *)(v94 + 12946) & 1) != 0 && *(int *)(v94 + 12552) < 82 )
      {
        v95 = _InterlockedIncrement((volatile signed __int32 *)(v94 + 12552));
        if ( v95 < 82 )
        {
          _mm_lfence();
          v96 = 152LL * (v95 - 1);
          *(_DWORD *)(v96 + v94 + 88) = 79;
          *(_DWORD *)(v96 + v94 + 232) = 2;
          do
            ++v92;
          while ( S2[v92] );
          wmemcpy_s((wchar_t *)(v96 + v94 + 104), 0x3Fu, S2, v92);
          goto LABEL_246;
        }
      }
    }
  }
  if ( v25 )
  {
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(lpWideCharStr) = v25;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
        "Ssl::Handshake",
        2471,
        L"ERR|SNIQueryContextAttributes return value: %d{DWORD}\n",
        lpWideCharStr);
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v108) = v25;
        cchWideChar[0] = 0;
        LODWORD(lpWideCharStr) = 6;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
          "Ssl::Handshake",
          2474,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          lpWideCharStr,
          *(_QWORD *)cchWideChar,
          v108);
      }
    }
    goto LABEL_284;
  }
LABEL_246:
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(lpWideCharStr) = 0;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
      "Ssl::Handshake",
      2471,
      L"SNIQueryContextAttributes return value: %d{DWORD}\n",
      lpWideCharStr);
  }
LABEL_248:
  if ( !*(_DWORD *)(*((_QWORD *)this + 4) + 4LL) && (*((_DWORD *)this + 16) & 0x8000) == 0 && HIDWORD(Size) == 5 )
  {
    v25 = -2146893048;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
        "Ssl::Handshake",
        2491,
        L"ERR|SNIInBuffer has extra data\n");
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v108) = -2146893048;
        cchWideChar[0] = 0;
        LODWORD(lpWideCharStr) = 6;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
          "Ssl::Handshake",
          2492,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          lpWideCharStr,
          *(_QWORD *)cchWideChar,
          v108);
      }
    }
    goto LABEL_254;
  }
  v25 = ((__int64 (__fastcall *)(char *, __int64, _DWORD *))Ssl::s_pfTable->QueryContextAttributesW)(
          (char *)this + 392,
          4,
          v150);
  if ( v25 )
  {
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(lpWideCharStr) = v25;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
        "Ssl::Handshake",
        2503,
        L"ERR|SNIQueryContextAttributes return value: %d{DWORD}\n",
        lpWideCharStr);
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v108) = v25;
        cchWideChar[0] = 0;
        LODWORD(lpWideCharStr) = 6;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
          "Ssl::Handshake",
          2509,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          lpWideCharStr,
          *(_QWORD *)cchWideChar,
          v108);
      }
    }
LABEL_284:
    SNISetLastError(6, (unsigned int)v25, 50100);
    *((_DWORD *)this + 48) = 4;
    *((_DWORD *)this + 49) = 21;
    AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v122);
    goto LABEL_285;
  }
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(lpWideCharStr) = 0;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
      "Ssl::Handshake",
      2503,
      L"SNIQueryContextAttributes return value: %d{DWORD}\n",
      lpWideCharStr);
  }
  *((_DWORD *)this + 18) = v150[0];
  *((_DWORD *)this + 19) = v150[1];
  *((_DWORD *)this + 23) = v150[2];
  *((_DWORD *)this + 34) = 0;
  *((_DWORD *)this + 40) = 0;
  *((_DWORD *)this + 41) = v132;
  v97 = *((_QWORD *)this + 4);
  if ( (*(_DWORD *)(v97 + 4) || (*((_DWORD *)this + 16) & 0x8000) != 0) && HIDWORD(Size) == 5 )
  {
    Ex2 = SNIPacketAllocateEx2(v97, 0);
    v99 = Ex2;
    *((_QWORD *)this + 7) = Ex2;
    if ( !Ex2 )
    {
LABEL_266:
      v25 = 14;
      *((_DWORD *)this + 12) = 4;
      AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v122);
      goto LABEL_285;
    }
    v100 = Size;
    memmove(
      (void *)(*(_QWORD *)(Ex2 + 168) + *(unsigned int *)(Ex2 + 184)),
      (const void *)(*((_QWORD *)this + 16) + v156[0] - (unsigned __int64)(unsigned int)Size),
      (unsigned int)Size);
    *(_DWORD *)(v99 + 176) = v100;
  }
  if ( !*((_DWORD *)this + 41) )
  {
    CryptoBase::FreeReadWriteBuffers(this);
    v25 = (*(__int64 (__fastcall **)(Ssl *))(*(_QWORD *)this + 296LL))(this);
    if ( v25 )
    {
      *((_DWORD *)this + 12) = 4;
      AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v122);
      goto LABEL_285;
    }
    *((_DWORD *)this + 54) = 3;
    *((_DWORD *)this + 12) = 3;
LABEL_278:
    if ( (*((_DWORD *)this + 16) & 0x100) != 0 )
      goto LABEL_199;
    v25 = Ssl::SetChannelBindings(this);
    if ( !v25 )
      goto LABEL_199;
    goto LABEL_280;
  }
  if ( v133 == 2 )
  {
    *((_DWORD *)this + 12) = 2;
    CryptoBase::FormatOutputBuffer(this);
    *((_DWORD *)this + 41) += *((_DWORD *)this + 46) + *((_DWORD *)this + 47);
    goto LABEL_278;
  }
  v25 = -2146893048;
  if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
  {
    LODWORD(lpWideCharStr) = v133;
    SNIXE_SNI_ERROR_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
      "Ssl::Handshake",
      2567,
      L"ERR|SNIBufferType for OutBuffer[0] is invalid: %d{ULONG}, expected: 2, SECBUFFER_TOKEN\n",
      lpWideCharStr);
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v108) = -2146893048;
      cchWideChar[0] = 0;
      LODWORD(lpWideCharStr) = 6;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
        "Ssl::Handshake",
        2568,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        lpWideCharStr,
        *(_QWORD *)cchWideChar,
        v108);
    }
  }
LABEL_254:
  SNISetLastError(6, 2148074248LL, 50100);
  AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v122);
LABEL_285:
  *(_DWORD *)(v121 + 616) &= ~v120;
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(lpWideCharStr) = v25;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
      "Ssl::Handshake",
      2709,
      L"RET|SNI%d{WINERR}\n",
      lpWideCharStr);
  }
  v101 = *((_QWORD *)this + 4);
  if ( (*(_BYTE *)(v101 + 12946) & 1) != 0 )
  {
    v102 = GetTickCount() - *(_DWORD *)(v101 + 80);
    if ( *(int *)(v101 + 12552) < 82 )
    {
      v103 = _InterlockedIncrement((volatile signed __int32 *)(v101 + 12552));
      if ( v103 < 82 )
      {
        v104 = 152LL * (v103 - 1);
        *(_DWORD *)(v104 + v101 + 88) = 3;
        *(_DWORD *)(v104 + v101 + 92) = v102;
        *(_QWORD *)(v104 + v101 + 96) = 0;
        *(_DWORD *)(v104 + v101 + 232) = 0;
      }
    }
  }
  v2 = v25;
LABEL_292:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON(v137, v138, v139, v76);
  return v2;
}

```

## disassembly

```asm
0x10044d800  mov     rax, rsp
0x10044d803  push    rbp
0x10044d804  push    r12
0x10044d806  push    r13
0x10044d808  push    r14
0x10044d80a  push    r15
0x10044d80c  lea     rbp, [rax-6A8h]
0x10044d813  sub     rsp, 780h
0x10044d81a  mov     [rbp+6A0h+var_660], 0FFFFFFFFFFFFFFFEh
0x10044d822  mov     [rax+10h], rbx
0x10044d826  mov     [rax+18h], rsi
0x10044d82a  mov     [rax+20h], rdi
0x10044d82e  mov     rax, cs:__security_cookie
0x10044d835  xor     rax, rsp
0x10044d838  mov     [rbp+6A0h+var_30], rax
0x10044d83f  mov     rdi, rcx
0x10044d842  lea     r12, aSqlCommonDkSni_11; "sql\\common\\dk\\sni\\src\\SNI_SslProvi"...
0x10044d849  mov     [rbp+6A0h+var_688], r12
0x10044d84d  lea     r15, aSslHandshake; "Ssl::Handshake"
0x10044d854  mov     [rbp+6A0h+var_680], r15
0x10044d858  mov     [rbp+6A0h+var_678], 846h
0x10044d85f  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044d866  jz      short loc_10044D887
0x10044d868  mov     eax, [rcx+2Ch]
0x10044d86b  mov     dword ptr [rsp+7A0h+lpWideCharStr], eax
0x10044d86f  lea     r9, aApiSniU; "API|SNI%u#\n"
0x10044d876  mov     r8d, 846h; int
0x10044d87c  mov     rdx, r15; char *
0x10044d87f  mov     rcx, r12; char *
0x10044d882  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10044d887  xor     r13d, r13d
0x10044d88a  mov     [rsp+7A0h+var_730], r13d
0x10044d88f  mov     rbx, [rdi+20h]
0x10044d893  lea     esi, [r13+2]
0x10044d897  mov     r14d, 1
0x10044d89d  test    [rbx+3292h], r14b
0x10044d8a4  jz      short loc_10044D8EF
0x10044d8a6  call    cs:__imp_GetTickCount
0x10044d8ac  mov     edx, eax
0x10044d8ae  sub     edx, [rbx+50h]
0x10044d8b1  mov     ecx, [rbx+3108h]
0x10044d8b7  cmp     ecx, 52h ; 'R'
0x10044d8ba  jge     short loc_10044D8EF
0x10044d8bc  mov     eax, r14d
0x10044d8bf  lock xadd [rbx+3108h], eax
0x10044d8c7  inc     eax
0x10044d8c9  cmp     eax, 52h ; 'R'
0x10044d8cc  jge     short loc_10044D8EF
0x10044d8ce  dec     eax
0x10044d8d0  movsxd  rcx, eax
0x10044d8d3  imul    rax, rcx, 98h
0x10044d8da  mov     [rax+rbx+58h], esi
0x10044d8de  mov     [rax+rbx+5Ch], edx
0x10044d8e2  mov     [rax+rbx+60h], r13
0x10044d8e7  mov     [rax+rbx+0E8h], r13d
0x10044d8ef  mov     edx, r14d
0x10044d8f2  lea     rcx, [rbp+6A0h+var_710]
0x10044d8f6  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x10044d8fb  nop
0x10044d8fc  lea     rax, [rbp+6A0h+var_700]
0x10044d900  mov     qword ptr [rbp+6A0h+var_670], rax
0x10044d904  mov     [rbp+6A0h+var_6F0], 200001E3h
0x10044d90b  mov     [rbp+6A0h+var_6E8], r13
0x10044d90f  mov     [rbp+6A0h+var_6D8], r13
0x10044d913  mov     [rbp+6A0h+var_6E0], r13
0x10044d917  mov     [rbp+6A0h+var_6D0], r13
0x10044d91b  mov     [rbp+6A0h+var_6C0], 0
0x10044d91f  mov     rdx, gs:58h
0x10044d928  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044d92f  mov     ecx, [rax]
0x10044d931  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044d938  mov     ebx, [rax]
0x10044d93a  add     rbx, [rdx+rcx*8]
0x10044d93e  mov     rax, [rbx+100h]
0x10044d945  test    rax, rax
0x10044d948  jnz     short loc_10044D959
0x10044d94a  xor     ecx, ecx
0x10044d94c  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044d952  mov     rax, [rbx+100h]
0x10044d959  mov     rcx, [rax+258h]
0x10044d960  test    rcx, rcx
0x10044d963  jz      short loc_10044D975
0x10044d965  lea     rdx, [rbp+6A0h+var_6F0]
0x10044d969  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x10044d96f  test    eax, eax
0x10044d971  setz    [rbp+6A0h+var_6C0]
0x10044d975  mov     rdx, gs:58h
0x10044d97e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044d985  mov     ecx, [rax]
0x10044d987  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044d98e  mov     ebx, [rax]
0x10044d990  add     rbx, [rdx+rcx*8]
0x10044d994  mov     rdx, [rbx+100h]
0x10044d99b  test    rdx, rdx
0x10044d99e  jnz     short loc_10044D9AF
0x10044d9a0  xor     ecx, ecx
0x10044d9a2  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044d9a8  mov     rdx, [rbx+100h]
0x10044d9af  mov     [rbp+6A0h+var_6F8], rdx
0x10044d9b3  mov     eax, [rdx+320h]
0x10044d9b9  shr     eax, 0Bh
0x10044d9bc  and     eax, 1
0x10044d9bf  mov     [rbp+6A0h+var_6FC], eax
0x10044d9c2  jnz     short loc_10044D9D3
0x10044d9c4  test    byte ptr [rdx+320h], 4
0x10044d9cb  jz      short loc_10044D9D3
0x10044d9cd  mov     [rbp+6A0h+var_700], r13d
0x10044d9d1  jmp     short loc_10044D9E5
0x10044d9d3  mov     [rbp+6A0h+var_700], r14d
0x10044d9d7  mov     rcx, [rdx+260h]
0x10044d9de  mov     rax, [rcx]
0x10044d9e1  call    qword ptr [rax+8]
0x10044d9e4  nop
0x10044d9e5  mov     ebx, 0C03Ch
0x10044d9ea  nop     word ptr [rax+rax+00h]
0x10044d9f0  mov     eax, [rdi+0B4h]
0x10044d9f6  add     eax, [rdi+0B0h]
0x10044d9fc  sub     [rdi+88h], eax
0x10044da02  mov     rcx, rdi; this
0x10044da05  call    ?ProcessInputBuffer@CryptoBase@@IEAAXXZ; CryptoBase::ProcessInputBuffer(void)
0x10044da0a  mov     rax, [rdi+80h]
0x10044da11  mov     [rbp+6A0h+var_478], rax
0x10044da18  mov     eax, [rdi+88h]
0x10044da1e  mov     [rbp+6A0h+var_480], eax
0x10044da24  mov     [rbp+6A0h+var_47C], esi
0x10044da2a  mov     [rbp+6A0h+var_468], r13
0x10044da31  mov     [rbp+6A0h+Size], r13
0x10044da38  mov     rax, [rdi+20h]
0x10044da3c  cmp     dword ptr [rax+4], 0
0x10044da40  jz      short loc_10044DA75
0x10044da42  cmp     dword ptr [rdi+30h], 0
0x10044da46  jnz     short loc_10044DA75
0x10044da48  mov     [rbp+6A0h+var_45C], 12h
0x10044da52  lea     rax, [rdi+198h]
0x10044da59  mov     [rbp+6A0h+var_458], rax
0x10044da60  mov     eax, [rdi+398h]
0x10044da66  mov     [rbp+6A0h+var_460], eax
0x10044da6c  mov     [rbp+6A0h+var_71C], 3
0x10044da73  jmp     short loc_10044DA78
0x10044da75  mov     [rbp+6A0h+var_71C], esi
0x10044da78  lea     rax, [rbp+6A0h+var_480]
0x10044da7f  mov     [rbp+6A0h+var_720], r13d
0x10044da83  mov     [rbp+6A0h+var_718], rax
0x10044da87  mov     rax, [rdi+98h]
0x10044da8e  mov     [rbp+6A0h+var_6A0], rax
0x10044da92  mov     [rbp+6A0h+var_6A4], esi
0x10044da95  mov     eax, cs:?s_cbMaxToken@Ssl@@0KA; ulong Ssl::s_cbMaxToken
0x10044da9b  mov     [rbp+6A0h+var_6A8], eax
0x10044da9e  mov     [rbp+6A0h+var_694], r14d
0x10044daa2  lea     rax, [rbp+6A0h+var_6A8]
0x10044daa6  mov     [rbp+6A0h+var_690], rax
0x10044daaa  mov     [rbp+6A0h+var_698], r13d
0x10044daae  xor     r8d, r8d
0x10044dab1  mov     edx, esi
0x10044dab3  mov     rcx, rdi
0x10044dab6  call    ?SetLoginEvent@CryptoBase@@QEAAXW4SNIAuthTimerEvent@@W4SNIAuthTimerEventType@@@Z; CryptoBase::SetLoginEvent(SNIAuthTimerEvent,SNIAuthTimerEventType)
0x10044dabb  mov     rax, [rdi+20h]
0x10044dabf  test    byte ptr [rax+3204h], 2
0x10044dac6  jz      loc_10044DC95
0x10044dacc  mov     ecx, [rdi+40h]
0x10044dacf  mov     r9d, ecx
0x10044dad2  shl     r9d, 13h
0x10044dad6  not     r9d
0x10044dad9  and     r9d, 80000h
0x10044dae0  test    ecx, 7000h
0x10044dae6  mov     eax, 0C0BCh
0x10044daeb  cmovz   eax, ebx
0x10044daee  or      r9d, eax
0x10044daf1  bt      ecx, 11h
0x10044daf5  jnb     short loc_10044DAFC
0x10044daf7  bts     r9d, 10h
0x10044dafc  mov     r8d, r14d
0x10044daff  lock xadd cs:?s_cInitializeSecurityContext@Ssl@@2JC, r8d; long volatile Ssl::s_cInitializeSecurityContext
0x10044db08  inc     r8d
0x10044db0b  mov     rax, [rdi+20h]
0x10044db0f  mov     rdx, [rax+3298h]
0x10044db16  test    rdx, rdx
0x10044db19  jz      short loc_10044DB67
0x10044db1b  test    byte ptr [rdx+3292h], 1
0x10044db22  jz      short loc_10044DB67
0x10044db24  mov     eax, [rdx+3108h]
0x10044db2a  cmp     eax, 52h ; 'R'
0x10044db2d  jge     short loc_10044DB67
0x10044db2f  mov     eax, r14d
0x10044db32  lock xadd [rdx+3108h], eax
0x10044db3a  inc     eax
0x10044db3c  cmp     eax, 52h ; 'R'
0x10044db3f  jge     short loc_10044DB67
0x10044db41  dec     eax
0x10044db43  movsxd  rcx, eax
0x10044db46  imul    rax, rcx, 98h
0x10044db4d  mov     dword ptr [rax+rdx+58h], 5
0x10044db55  mov     [rax+rdx+5Ch], r8d
0x10044db5a  mov     [rax+rdx+60h], r13
0x10044db5f  mov     [rax+rdx+0E8h], r13d
0x10044db67  mov     edx, [rdi+30h]
0x10044db6a  lea     rax, [rdi+188h]
0x10044db71  mov     r10, rax
0x10044db74  test    edx, edx
0x10044db76  cmovnz  r10, r13
0x10044db7a  mov     r11, r13
0x10044db7d  cmovnz  r11, rax
0x10044db81  mov     eax, [rdi+40h]
0x10044db84  test    al, 2
0x10044db86  jz      short loc_10044DB9E
0x10044db88  test    al, 1
0x10044db8a  lea     rcx, ?s_hClientCred@Ssl@@0U_SecHandle@@A; _SecHandle Ssl::s_hClientCred
0x10044db91  lea     rax, ?s_hClientCredValidate@Ssl@@0U_SecHandle@@A; _SecHandle Ssl::s_hClientCredValidate
0x10044db98  cmovnz  rcx, rax
0x10044db9c  jmp     short loc_10044DBA5
0x10044db9e  lea     rcx, [rdi+178h]
0x10044dba5  lea     rax, [rbp+6A0h+var_720]
0x10044dba9  test    edx, edx
0x10044dbab  cmovz   rax, r13
0x10044dbaf  mov     r8, [rdi+20h]
0x10044dbb3  mov     [rsp+7A0h+var_748], r13
0x10044dbb8  lea     rdx, [rsp+7A0h+var_730]
0x10044dbbd  mov     [rsp+7A0h+var_750], rdx
0x10044dbc2  lea     rdx, [rbp+6A0h+var_698]
0x10044dbc6  mov     [rsp+7A0h+var_758], rdx
0x10044dbcb  mov     [rsp+7A0h+var_760], r10
0x10044dbd0  mov     dword ptr [rsp+7A0h+var_768], r13d
0x10044dbd5  mov     [rsp+7A0h+var_770], rax
0x10044dbda  mov     [rsp+7A0h+cchWideChar], 10h
0x10044dbe2  mov     dword ptr [rsp+7A0h+lpWideCharStr], r13d
0x10044dbe7  mov     r8, [r8+3140h]
0x10044dbee  mov     rdx, r11
0x10044dbf1  mov     rax, cs:?s_pfTable@Ssl@@0PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * Ssl::s_pfTable
0x10044dbf8  call    qword ptr [rax+30h]
0x10044dbfb  mov     ebx, eax
0x10044dbfd  lock dec cs:?s_cInitializeSecurityContext@Ssl@@2JC; long volatile Ssl::s_cInitializeSecurityContext
0x10044dc04  mov     ecx, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044dc0a  test    cl, 1
0x10044dc0d  jz      short loc_10044DC35
0x10044dc0f  mov     ecx, [rsp+7A0h+var_730]
0x10044dc13  mov     dword ptr [rsp+7A0h+lpWideCharStr], ecx
0x10044dc17  lea     r9, aSniinitializes_0; "SNIInitializeSecurityContext ContextAtt"...
0x10044dc1e  mov     r8d, 8C4h; int
0x10044dc24  mov     rdx, r15; char *
0x10044dc27  mov     rcx, r12; char *
0x10044dc2a  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10044dc2f  mov     ecx, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044dc35  test    ebx, ebx
0x10044dc37  js      short loc_10044DC67
0x10044dc39  test    cl, 1
0x10044dc3c  jz      short loc_10044DC8B
0x10044dc3e  lfence
0x10044dc41  mov     dword ptr [rsp+7A0h+lpWideCharStr], ebx
0x10044dc45  lea     r9, aSniinitializes; "SNIInitializeSecurityContext return val"...
0x10044dc4c  mov     r8d, 8C6h; int
0x10044dc52  mov     rdx, r15; char *
0x10044dc55  mov     rcx, r12; char *
0x10044dc58  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10044dc5d  mov     eax, 13h
0x10044dc62  jmp     loc_10044E4EC
0x10044dc67  test    cl, 2
0x10044dc6a  jz      short loc_10044DC8B
0x10044dc6c  lfence
0x10044dc6f  mov     dword ptr [rsp+7A0h+lpWideCharStr], ebx
0x10044dc73  lea     r9, aErrSniinitiali; "ERR|SNIInitializeSecurityContext return"...
0x10044dc7a  mov     r8d, 8C6h; int
0x10044dc80  mov     rdx, r15; char *
0x10044dc83  mov     rcx, r12; char *
0x10044dc86  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10044dc8b  mov     eax, 13h
0x10044dc90  jmp     loc_10044E4EC
0x10044dc95  mov     edx, r14d
0x10044dc98  lock xadd cs:?s_cAcceptSecurityContext@Ssl@@2JC, edx; long volatile Ssl::s_cAcceptSecurityContext
0x10044dca0  inc     edx
0x10044dca2  mov     r8, [rdi+20h]
0x10044dca6  test    byte ptr [r8+3292h], 1
0x10044dcae  jz      short loc_10044DCF6
0x10044dcb0  mov     eax, [r8+3108h]
0x10044dcb7  cmp     eax, 52h ; 'R'
0x10044dcba  jge     short loc_10044DCF6
0x10044dcbc  mov     eax, r14d
0x10044dcbf  lock xadd [r8+3108h], eax
0x10044dcc8  inc     eax
0x10044dcca  cmp     eax, 52h ; 'R'
0x10044dccd  jge     short loc_10044DCF6
0x10044dccf  dec     eax
0x10044dcd1  movsxd  rcx, eax
0x10044dcd4  imul    rax, rcx, 98h
0x10044dcdb  mov     dword ptr [rax+r8+58h], 4
0x10044dce4  mov     [rax+r8+5Ch], edx
0x10044dce9  mov     [rax+r8+60h], r13
0x10044dcee  mov     [rax+r8+0E8h], r13d
0x10044dcf6  mov     [rsp+7A0h+var_728], r13d
0x10044dcfb  mov     ecx, [rdi+40h]
0x10044dcfe  bt      ecx, 16h
0x10044dd02  jnb     loc_10044E194
0x10044dd08  mov     rcx, [rbp+6A0h+var_718]
0x10044dd0c  mov     r8d, [rcx]
0x10044dd0f  mov     rcx, [rcx+8]
0x10044dd13  mov     r15d, r13d
0x10044dd16  mov     r12d, r13d
0x10044dd19  mov     [rbp+6A0h+lpMultiByteStr], r13
0x10044dd1d  mov     [rsp+7A0h+cbMultiByte], r13d
0x10044dd22  cmp     r8d, 5
0x10044dd26  jb      loc_10044DF16
  ... truncated ...
```
