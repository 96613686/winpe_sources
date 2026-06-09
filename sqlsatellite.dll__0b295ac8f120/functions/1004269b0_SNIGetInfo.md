# SNIGetInfo

- ea: `0x1004269b0`
- end: `0x100427e54`
- name: `SNIGetInfo`
- size: `5284`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x100441290`
- `0x10044beb0`
- `0x10044d800`
- `0x100471d80`
- `0x100472580`
- `0x100473630`
- `0x1004740e0`
- `0x100480d40`

## callees

- `0x10041d520`
- `0x10041d950`
- `0x10041dcb0`
- `0x1004269b0`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x10044a0a0`
- `0x10044d700`
- `0x100486250`
- `0x100486af0`
- `0x100487cd6`

## import_xrefs

- `KERNEL32!GetModuleHandleA` at `0x100427729`
- `KERNEL32!GetModuleHandleA` at `0x100427729`
- `KERNEL32!GetProcAddress` at `0x10042774d`
- `KERNEL32!GetProcAddress` at `0x10042774d`
- `KERNEL32!GetLastError` at `0x100427765`
- `KERNEL32!GetLastError` at `0x100427765`
- `ADVAPI32!GetSecurityInfo` at `0x1004278a2`
- `ADVAPI32!GetSecurityInfo` at `0x1004278a2`

## string_xrefs

- `0x1004269f5`: `sql\common\dk\sni\src\sni.cpp`
- `0x100426bbb`: `sql\common\dk\sni\src\sni.cpp`
- `0x100427278`: `sql\common\dk\sni\src\sni.cpp`
- `0x1004272b3`: `sql\common\dk\sni\src\sni.cpp`
- `0x100427576`: `sql\common\dk\sni\src\sni.cpp`
- `0x100426ded`: `sql\common\dk\sni\src\sni_sspi.cpp`
- `0x100426f49`: `sql\common\dk\sni\src\sni_sspi.cpp`
- `0x100426e96`: `ERR|SNIUnexpected call to GetSecPkgName with IDCRL package outside of SNI_BASED_CLIENT build.\n`
- `0x100426f9c`: `ERR|SNIUnexpected call to GetMutualAuth with IDCRL package outside of SNI_BASED_CLIENT build.\n`
- `0x10042712c`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100427364`: `sql\common\dk\sni\src\tcp.cpp`
- `0x10042748f`: `sql\common\dk\sni\src\tcp.cpp`
- `0x1004275b0`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100427a94`: `sql\common\dk\sni\src\tcp.cpp`
- `0x1004276da`: `sql\common\dk\sni\src\np.cpp`
- `0x100427722`: `kernel32.dll`
- `0x1004276e5`: `Np::GetPeerProcessId`
- `0x100427746`: `GetNamedPipeClientProcessId`
- `0x10042773d`: `GetNamedPipeServerProcessId`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
__int64 __fastcall SNIGetInfo(__int64 a1, int a2, __int64 a3, const wchar_t *a4)
{
  int v7; // r14d
  DWORD LastError; // r15d
  SOS_UnfairRecursiveMutexExtendedGuarantee **v9; // rbx
  __int64 v10; // rax
  bool v11; // zf
  SOS_UnfairRecursiveMutexExtendedGuarantee **v12; // r13
  __int64 v13; // rbx
  _WORD *v14; // rcx
  __int64 v15; // rdx
  __int16 v16; // ax
  _WORD *v17; // rax
  SOS_UnfairRecursiveMutexExtendedGuarantee **v18; // rbx
  __int64 v19; // rcx
  SOS_UnfairRecursiveMutexExtendedGuarantee **v20; // rbx
  SOS_UnfairRecursiveMutexExtendedGuarantee **v21; // rbx
  __int64 v22; // rax
  __int64 i; // rcx
  SOS_UnfairRecursiveMutexExtendedGuarantee **v24; // rbx
  __int64 v25; // rcx
  __int64 mm; // rax
  SOS_UnfairRecursiveMutexExtendedGuarantee **v27; // rbx
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rsi
  __int64 v33; // rax
  __int64 v34; // rsi
  unsigned int v35; // edx
  unsigned int v36; // ecx
  SOS_UnfairRecursiveMutexExtendedGuarantee **v37; // r12
  const wchar_t *v38; // r9
  __int64 n; // r13
  __int64 v40; // rcx
  __int64 ii; // rax
  SOS_UnfairRecursiveMutexExtendedGuarantee **v42; // r15
  const wchar_t *v43; // r9
  __int64 v44; // rax
  int v45; // ecx
  __int64 v46; // rax
  __int64 j; // rcx
  SOS_UnfairRecursiveMutexExtendedGuarantee **v48; // r13
  const wchar_t *v49; // r9
  __int64 k; // r15
  __int64 v51; // rcx
  __int64 m; // rax
  const wchar_t *v53; // r9
  __int64 jj; // r15
  __int64 v55; // rcx
  __int64 kk; // rax
  __int64 v57; // rbx
  HMODULE ModuleHandleA; // rcx
  const CHAR *v59; // rdx
  FARPROC ProcAddress; // rax
  const wchar_t *v61; // r9
  __int64 v62; // rcx
  __int64 v63; // rax
  __int64 v64; // rcx
  __int64 v65; // rax
  SOS_UnfairRecursiveMutexExtendedGuarantee **v66; // rbx
  __int64 v67; // rsi
  unsigned int AGDynamicListenerResourceID; // eax
  const wchar_t *v69; // r9
  unsigned int v70; // r12d
  _QWORD *nn; // rbx
  __int64 v72; // rbx
  unsigned int v73; // esi
  PSID *ppsidGroup; // [rsp+20h] [rbp-E0h]
  PACL *ppDacl; // [rsp+28h] [rbp-D8h]
  PACL *ppSacl; // [rsp+30h] [rbp-D0h]
  unsigned int v78; // [rsp+58h] [rbp-A8h] BYREF
  char *v79; // [rsp+60h] [rbp-A0h]
  char *v80; // [rsp+68h] [rbp-98h]
  int v81; // [rsp+70h] [rbp-90h]
  __int64 v82; // [rsp+78h] [rbp-88h]
  const char *v83; // [rsp+80h] [rbp-80h] BYREF
  const char *v84; // [rsp+88h] [rbp-78h]
  int v85; // [rsp+90h] [rbp-70h]
  _SecPkgContext_CipherInfo v86; // [rsp+A0h] [rbp-60h] BYREF

  v82 = -2;
  v79 = "sql\\common\\dk\\sni\\src\\sni.cpp";
  v80 = "SNIGetInfo";
  v81 = 5051;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\sni.cpp",
      "SNIGetInfo",
      5051,
      L"API|SNIpConn: %p{SNI_Conn*}, QType: %d, pbQInfo: %p\n",
      a1,
      a2,
      a3);
  v7 = 0;
  LastError = 0;
  switch ( a2 )
  {
    case 1:
      v31 = *(_DWORD *)(a1 + 12752);
      goto LABEL_231;
    case 2:
      *(_QWORD *)a3 = *(_QWORD *)(a1 + 12736);
      goto LABEL_232;
    case 8:
      v9 = *(SOS_UnfairRecursiveMutexExtendedGuarantee ***)(a1 + 64);
      CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v9);
      v10 = *(_QWORD *)(a1 + 12616);
      v11 = v10 == 0;
      if ( v10 )
      {
        do
        {
          if ( *(_DWORD *)(v10 + 24) == 6 && *(_DWORD *)(v10 + 40) )
            break;
          v10 = *(_QWORD *)(v10 + 8);
        }
        while ( v10 );
        v11 = v10 == 0;
      }
      LOBYTE(v7) = !v11;
      *(_DWORD *)a3 = v7;
      SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v9[1]);
      goto LABEL_232;
    case 9:
      v21 = *(SOS_UnfairRecursiveMutexExtendedGuarantee ***)(a1 + 64);
      CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v21);
      v22 = *(_QWORD *)(a1 + 12616);
      for ( i = *(_QWORD *)(v22 + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)(v22 + 24) == 2 )
          break;
        v22 = i;
      }
      *(_DWORD *)a3 = *(_DWORD *)(v22 + 24);
      SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v21[1]);
      goto LABEL_232;
    case 10:
      *(_OWORD *)a3 = *(_OWORD *)(a1 + 28);
      goto LABEL_232;
    case 11:
      v18 = *(SOS_UnfairRecursiveMutexExtendedGuarantee ***)(a1 + 64);
      CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v18);
      v28 = *(_QWORD *)(a1 + 12616);
      v29 = v28;
      if ( !v28 )
        goto LABEL_46;
      while ( *(_DWORD *)(v29 + 24) != 2 )
      {
        v29 = *(_QWORD *)(v29 + 8);
        if ( !v29 )
        {
LABEL_46:
          LastError = 87;
          goto LABEL_198;
        }
      }
      do
      {
        v30 = v28;
        v28 = *(_QWORD *)(v28 + 8);
      }
      while ( v28 );
      *(_OWORD *)a3 = *(_OWORD *)(*(_QWORD *)(v30 + 32) + 28LL);
      goto LABEL_198;
    case 12:
      *(_DWORD *)a3 = *(_DWORD *)(*(_QWORD *)(a1 + 12808) + 20LL);
      goto LABEL_232;
    case 13:
      v35 = *(_DWORD *)(a1 + 12752);
      v36 = v35 + *(_DWORD *)(a1 + 12756);
      v31 = -1;
      if ( v36 >= v35 )
        v31 = v35 + *(_DWORD *)(a1 + 12756);
      LastError = v36 < v35 ? 0x80070216 : 0;
      goto LABEL_231;
    case 14:
      *(_QWORD *)a3 = *(unsigned __int16 *)(a1 + 12944);
      goto LABEL_232;
    case 15:
      v31 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 12748), 0, 0);
      goto LABEL_231;
    case 16:
      v31 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 12744), 0, 0);
      goto LABEL_231;
    case 17:
      *(_WORD *)a3 = 0;
      *(_DWORD *)(a3 + 100) = 0;
      v42 = *(SOS_UnfairRecursiveMutexExtendedGuarantee ***)(a1 + 64);
      CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v42);
      v44 = *(_QWORD *)(a1 + 12616);
      if ( !v44 )
        goto LABEL_125;
      while ( 2 )
      {
        v45 = *(_DWORD *)(v44 + 24);
        switch ( v45 )
        {
          case 7:
            v83 = "sql\\common\\dk\\sni\\src\\tcp.cpp";
            v84 = "Tcp::GetPeerAddress";
            v85 = 5867;
            if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
              SNIXE_SNI_ENTER_ON(
                "sql\\common\\dk\\sni\\src\\tcp.cpp",
                "Tcp::GetPeerAddress",
                5867,
                L"API|SNIpConn: %p{SNI_Conn*}, addrinfo: %p{PeerAddrInfo*}\n",
                a1,
                a3);
            v46 = *(_QWORD *)(a1 + 12616);
            for ( j = *(_QWORD *)(v46 + 8); j; j = *(_QWORD *)(j + 8) )
              v46 = j;
            *(_OWORD *)a3 = *(_OWORD *)(v46 + 76);
            *(_OWORD *)(a3 + 16) = *(_OWORD *)(v46 + 92);
            *(_OWORD *)(a3 + 32) = *(_OWORD *)(v46 + 108);
            *(_OWORD *)(a3 + 48) = *(_OWORD *)(v46 + 124);
            *(_OWORD *)(a3 + 64) = *(_OWORD *)(v46 + 140);
            *(_OWORD *)(a3 + 80) = *(_OWORD *)(v46 + 156);
            *(_QWORD *)(a3 + 96) = *(_QWORD *)(v46 + 172);
            if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
            {
              LODWORD(ppsidGroup) = 0;
              SNIXE_SNI_TRACE_ON(
                "sql\\common\\dk\\sni\\src\\tcp.cpp",
                "Tcp::GetPeerAddress",
                5880,
                L"RET|SNI%d{WINERR}\n",
                ppsidGroup);
            }
            if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
              SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "Tcp::GetPeerAddress", 5867, v43);
            break;
          case 4:
            *(_OWORD *)a3 = *(_OWORD *)L"<local machine>";
            *(_OWORD *)(a3 + 16) = *(_OWORD *)L"achine>";
            *(_DWORD *)(a3 + 100) = 15;
            break;
          case 1:
            *(_OWORD *)a3 = *(_OWORD *)L"<named pipe>";
            *(_QWORD *)(a3 + 16) = *(_QWORD *)L"ipe>";
            *(_WORD *)(a3 + 24) = aNamedPipe[12];
            *(_DWORD *)(a3 + 100) = 12;
            break;
          default:
            v44 = *(_QWORD *)(v44 + 8);
            if ( !v44 )
              break;
            continue;
        }
        break;
      }
LABEL_125:
      SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v42[1]);
      LastError = 0;
      goto LABEL_232;
    case 18:
      v48 = *(SOS_UnfairRecursiveMutexExtendedGuarantee ***)(a1 + 64);
      CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v48);
      for ( k = *(_QWORD *)(a1 + 12616); k; k = *(_QWORD *)(k + 8) )
      {
        if ( *(_DWORD *)(k + 24) == 7 )
        {
          v83 = "sql\\common\\dk\\sni\\src\\tcp.cpp";
          v84 = "Tcp::GetPeerPort";
          v85 = 5943;
          if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
            SNIXE_SNI_ENTER_ON(
              "sql\\common\\dk\\sni\\src\\tcp.cpp",
              "Tcp::GetPeerPort",
              5943,
              L"API|SNIpConn: %p{SNI_Conn*}, port: %p{USHORT*}\n",
              a1,
              a3);
          v51 = *(_QWORD *)(a1 + 12616);
          for ( m = *(_QWORD *)(v51 + 8); m; m = *(_QWORD *)(m + 8) )
            v51 = m;
          *(_WORD *)a3 = *(_WORD *)(v51 + 284);
          if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
            SNIXE_SNI_TRACE_ON(
              "sql\\common\\dk\\sni\\src\\tcp.cpp",
              "Tcp::GetPeerPort",
              5954,
              L"RET|SNI%d{WINERR}\n",
              0);
          if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
            SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "Tcp::GetPeerPort", 5943, v49);
        }
        else
        {
          *(_WORD *)a3 = 0;
        }
      }
      goto LABEL_138;
    case 19:
      SNITime::GetTime(a1 + 12768, *(_QWORD *)(a1 + 12784), a3);
      goto LABEL_232;
    case 20:
      SNITime::GetTime(a1 + 12768, *(_QWORD *)(a1 + 12792), a3);
      goto LABEL_232;
    case 21:
      v31 = *(_DWORD *)(a1 + 12816);
      goto LABEL_231;
    case 22:
      SNITime::GetTime(a1 + 12768, *(_QWORD *)(a1 + 12776), a3);
      goto LABEL_232;
    case 23:
      v37 = *(SOS_UnfairRecursiveMutexExtendedGuarantee ***)(a1 + 64);
      CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v37);
      for ( n = *(_QWORD *)(a1 + 12616); n; n = *(_QWORD *)(n + 8) )
      {
        if ( *(_DWORD *)(n + 24) == 7 )
        {
          v83 = "sql\\common\\dk\\sni\\src\\tcp.cpp";
          v84 = "Tcp::GetLocalAddress";
          v85 = 5888;
          if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
            SNIXE_SNI_ENTER_ON(
              "sql\\common\\dk\\sni\\src\\tcp.cpp",
              "Tcp::GetLocalAddress",
              5888,
              L"API|SNIpConn: %p{SNI_Conn*}, addrinfo: %p{PeerAddrInfo*}\n",
              a1,
              a3);
          v40 = *(_QWORD *)(a1 + 12616);
          for ( ii = *(_QWORD *)(v40 + 8); ii; ii = *(_QWORD *)(ii + 8) )
            v40 = ii;
          *(_OWORD *)a3 = *(_OWORD *)(v40 + 180);
          *(_OWORD *)(a3 + 16) = *(_OWORD *)(v40 + 196);
          *(_OWORD *)(a3 + 32) = *(_OWORD *)(v40 + 212);
          *(_OWORD *)(a3 + 48) = *(_OWORD *)(v40 + 228);
          *(_OWORD *)(a3 + 64) = *(_OWORD *)(v40 + 244);
          *(_OWORD *)(a3 + 80) = *(_OWORD *)(v40 + 260);
          *(_QWORD *)(a3 + 96) = *(_QWORD *)(v40 + 276);
          if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
          {
            LODWORD(ppsidGroup) = 0;
            SNIXE_SNI_TRACE_ON(
              "sql\\common\\dk\\sni\\src\\tcp.cpp",
              "Tcp::GetLocalAddress",
              5901,
              L"RET|SNI%d{WINERR}\n",
              ppsidGroup);
          }
          if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
            SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "Tcp::GetLocalAddress", 5888, v38);
          LastError = 0;
        }
        else
        {
          LastError = 87;
          if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
          {
            LODWORD(ppSacl) = 87;
            LODWORD(ppDacl) = 5;
            LODWORD(ppsidGroup) = 10;
            SNIXE_SNI_ERROR_ON(
              "sql\\common\\dk\\sni\\src\\sni.cpp",
              "SNIGetInfo",
              5288,
              L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
              ppsidGroup,
              ppDacl,
              ppSacl);
          }
          SNISetLastError(10, 87, 50105);
        }
      }
      SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v37[1]);
      goto LABEL_232;
    case 24:
      v48 = *(SOS_UnfairRecursiveMutexExtendedGuarantee ***)(a1 + 64);
      CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v48);
      for ( jj = *(_QWORD *)(a1 + 12616); jj; jj = *(_QWORD *)(jj + 8) )
      {
        if ( *(_DWORD *)(jj + 24) == 7 )
        {
          v83 = "sql\\common\\dk\\sni\\src\\tcp.cpp";
          v84 = "Tcp::GetLocalPort";
          v85 = 5924;
          if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
            SNIXE_SNI_ENTER_ON(
              "sql\\common\\dk\\sni\\src\\tcp.cpp",
              "Tcp::GetLocalPort",
              5924,
              L"API|SNIpConn: %p{SNI_Conn*}, port: %p{USHORT*}\n",
              a1,
              a3);
          v55 = *(_QWORD *)(a1 + 12616);
          for ( kk = *(_QWORD *)(v55 + 8); kk; kk = *(_QWORD *)(kk + 8) )
            v55 = kk;
          *(_WORD *)a3 = *(_WORD *)(v55 + 286);
          if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
            SNIXE_SNI_TRACE_ON(
              "sql\\common\\dk\\sni\\src\\tcp.cpp",
              "Tcp::GetLocalPort",
              5935,
              L"RET|SNI%d{WINERR}\n",
              0);
          if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
            SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "Tcp::GetLocalPort", 5924, v53);
        }
        else
        {
          *(_WORD *)a3 = 0;
        }
      }
LABEL_138:
      SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v48[1]);
      LastError = 0;
      goto LABEL_232;
    case 26:
      v32 = *(_QWORD *)(a1 + 12808);
      if ( !v32 )
      {
        LastError = 87;
        goto LABEL_232;
      }
      if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
        SNIXE_SNI_ENTER_ON(
          "sql\\common\\dk\\sni\\src\\sni_sspi.cpp",
          "SNI_Sec::GetSecPkgName",
          193,
          L"API|SNIppPkgName: %p{LPTSTR*}\n",
          a3);
      LastError = *(_DWORD *)(v32 + 48);
      if ( LastError )
      {
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(ppSacl) = *(_DWORD *)(v32 + 48);
          LODWORD(ppDacl) = 0;
          LODWORD(ppsidGroup) = 10;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\sni_sspi.cpp",
            "SNI_Sec::GetSecPkgName",
            199,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            ppsidGroup,
            ppDacl,
            ppSacl);
        }
        SNISetLastError(10, LastError, 50100);
        *(_QWORD *)a3 = 0;
      }
      else if ( *(_DWORD *)(v32 + 20) == 5 )
      {
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\sni_sspi.cpp",
            "SNI_Sec::GetSecPkgName",
            214,
            L"ERR|SNIUnexpected call to GetSecPkgName with IDCRL package outside of SNI_BASED_CLIENT build.\n");
        LastError = -1;
      }
      else
      {
        v33 = *(_QWORD *)(**(_QWORD **)(v32 + 40) + 16LL);
        *(_QWORD *)a3 = v33;
        if ( (g_XeSniPkg_enabledBitmap & 1) == 0 )
          goto LABEL_67;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\sni_sspi.cpp",
          "SNI_Sec::GetSecPkgName",
          222,
          L"SNISecPkgName:'%s'\n",
          v33);
      }
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(ppsidGroup) = LastError;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\sni_sspi.cpp",
          "SNI_Sec::GetSecPkgName",
          226,
          L"RET|SNI%d{WINERR}\n",
          ppsidGroup);
      }
LABEL_67:
      if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
        SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni_sspi.cpp", "SNI_Sec::GetSecPkgName", 193, a4);
      goto LABEL_232;
    case 27:
      v34 = *(_QWORD *)(a1 + 12808);
      if ( v34 )
      {
        if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
          SNIXE_SNI_ENTER_ON("sql\\common\\dk\\sni\\src\\sni_sspi.cpp", "SNI_Sec::GetMutualAuth", 235, L"API|SNI\n");
        *(_DWORD *)a3 = 0;
        if ( *(_DWORD *)(v34 + 20) == 5 )
        {
          if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            SNIXE_SNI_ERROR_ON(
              "sql\\common\\dk\\sni\\src\\sni_sspi.cpp",
              "SNI_Sec::GetMutualAuth",
              253,
              L"ERR|SNIUnexpected call to GetMutualAuth with IDCRL package outside of SNI_BASED_CLIENT build.\n");
          LastError = -1;
        }
        else
        {
          LastError = ((__int64 (__fastcall *)(__int64, __int64, unsigned int *))g_pFuncs->QueryContextAttributesW)(
                        v34,
                        14,
                        &v78);
          if ( LastError )
          {
            if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
            {
              LODWORD(ppsidGroup) = LastError;
              SNIXE_SNI_ERROR_ON(
                "sql\\common\\dk\\sni\\src\\sni_sspi.cpp",
                "SNI_Sec::GetMutualAuth",
                267,
                L"ERR|SNIdwRet: %d\n",
                ppsidGroup);
              if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
              {
                LODWORD(ppSacl) = LastError;
                LODWORD(ppDacl) = 0;
                LODWORD(ppsidGroup) = 10;
                SNIXE_SNI_ERROR_ON(
                  "sql\\common\\dk\\sni\\src\\sni_sspi.cpp",
                  "SNI_Sec::GetMutualAuth",
                  268,
                  L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
                  ppsidGroup,
                  ppDacl,
                  ppSacl);
              }
            }
            SNISetLastError(10, LastError, 50100);
          }
          else
          {
            *(_DWORD *)a3 = (v78 >> 1) & 1;
          }
        }
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          LODWORD(ppDacl) = LastError;
          LODWORD(ppsidGroup) = *(_DWORD *)a3;
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\src\\sni_sspi.cpp",
            "SNI_Sec::GetMutualAuth",
            272,
            L"RET|SNIfMutualAuth: %d, %d{WINERR}\n",
            ppsidGroup,
            ppDacl);
        }
        if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
          SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni_sspi.cpp", "SNI_Sec::GetMutualAuth", 235, a4);
      }
      else
      {
        LastError = 87;
      }
      goto LABEL_232;
    case 28:
      *(_WORD *)a3 = *(_WORD *)(a1 + 24);
      goto LABEL_232;
    case 29:
      *(_OWORD *)a3 = *(_OWORD *)(a1 + 24);
      *(_OWORD *)(a3 + 16) = *(_OWORD *)(a1 + 40);
      *(_DWORD *)(a3 + 32) = *(_DWORD *)(a1 + 56);
      goto LABEL_232;
    case 30:
      *(_DWORD *)a3 = 0;
      v18 = *(SOS_UnfairRecursiveMutexExtendedGuarantee ***)(a1 + 64);
      CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v18);
      v65 = *(_QWORD *)(a1 + 12616);
      if ( !v65 )
        goto LABEL_198;
      while ( *(_DWORD *)(v65 + 24) != 7 )
      {
        v65 = *(_QWORD *)(v65 + 8);
        if ( !v65 )
          goto LABEL_198;
      }
      *(_DWORD *)a3 = 1;
      goto LABEL_198;
    case 31:
      v66 = *(SOS_UnfairRecursiveMutexExtendedGuarantee ***)(a1 + 64);
      CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v66);
      *(_DWORD *)a3 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 12616) + 168LL))(*(_QWORD *)(a1 + 12616));
      SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v66[1]);
      goto LABEL_232;
    case 32:
      v24 = *(SOS_UnfairRecursiveMutexExtendedGuarantee ***)(a1 + 64);
      CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v24);
      v25 = *(_QWORD *)(a1 + 12616);
      for ( mm = *(_QWORD *)(v25 + 8); mm; mm = *(_QWORD *)(mm + 8) )
        v25 = mm;
      *(_DWORD *)a3 = *(_DWORD *)(v25 + 24);
      SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v24[1]);
      goto LABEL_232;
    case 33:
      v20 = *(SOS_UnfairRecursiveMutexExtendedGuarantee ***)(a1 + 64);
      CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v20);
      LOBYTE(v7) = (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 12616) + 216LL))(*(_QWORD *)(a1 + 12616)) != 0;
      *(_DWORD *)a3 = v7;
      SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v20[1]);
      goto LABEL_232;
    case 34:
      *(_OWORD *)a3 = *(_OWORD *)(a1 + 44);
      goto LABEL_232;
    case 35:
      v63 = *(_QWORD *)(a1 + 12808);
      if ( v63 && *(_DWORD *)(v63 + 16) )
      {
        *(_QWORD *)a3 = v63;
      }
      else
      {
        *(_QWORD *)a3 = 0;
        LastError = 87;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(ppSacl) = 87;
          LODWORD(ppDacl) = 5;
          LODWORD(ppsidGroup) = 10;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\sni.cpp",
            "SNIGetInfo",
            5520,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            ppsidGroup,
            ppDacl,
            ppSacl);
        }
        SNISetLastError(10, 87, 50105);
      }
      goto LABEL_232;
    case 37:
      LastError = 4317;
      if ( !a3 )
      {
        LastError = 87;
        goto LABEL_232;
      }
      *(_DWORD *)(a3 + 12) = 0;
      v12 = *(SOS_UnfairRecursiveMutexExtendedGuarantee ***)(a1 + 64);
      CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v12);
      v67 = *(_QWORD *)(a1 + 12616);
      if ( !v67 )
        goto LABEL_24;
      while ( *(_DWORD *)(v67 + 24) != 7 )
      {
        v67 = *(_QWORD *)(v67 + 8);
        if ( !v67 )
          goto LABEL_24;
      }
      v83 = "sql\\common\\dk\\sni\\src\\tcp.cpp";
      v84 = "Tcp::GetAGResourceID";
      v85 = 5850;
      if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
      {
        LODWORD(ppsidGroup) = *(_DWORD *)(v67 + 44);
        SNIXE_SNI_ENTER_ON(
          "sql\\common\\dk\\sni\\src\\tcp.cpp",
          "Tcp::GetAGResourceID",
          5850,
          L"API|SNI%u#\n",
          ppsidGroup);
      }
      AGDynamicListenerResourceID = SNI_ServiceBindings::GetAGDynamicListenerResourceID(
                                      (LPWSTR)(v67 + 180),
                                      (struct SNIResourceIDStruct *)a3);
      LastError = AGDynamicListenerResourceID;
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(ppsidGroup) = AGDynamicListenerResourceID;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\tcp.cpp",
          "Tcp::GetAGResourceID",
          5860,
          L"RET|SNI%d{WINERR}\n",
          ppsidGroup);
      }
      if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
        SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "Tcp::GetAGResourceID", 5850, v69);
      goto LABEL_24;
    case 38:
      *(_DWORD *)a3 = 0;
      goto LABEL_232;
    case 41:
      *(_DWORD *)a3 = 0;
      LastError = 87;
      v12 = *(SOS_UnfairRecursiveMutexExtendedGuarantee ***)(a1 + 64);
      CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v12);
      v57 = *(_QWORD *)(a1 + 12616);
      if ( !v57 )
        goto LABEL_24;
      while ( *(_DWORD *)(v57 + 24) != 1 )
      {
        v57 = *(_QWORD *)(v57 + 8);
        if ( !v57 )
          goto LABEL_24;
      }
      v83 = "sql\\common\\dk\\sni\\src\\np.cpp";
      v84 = "Np::GetPeerProcessId";
      v85 = 1513;
      if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
      {
        LODWORD(ppsidGroup) = *(_DWORD *)(v57 + 44);
        SNIXE_SNI_ENTER_ON(
          "sql\\common\\dk\\sni\\src\\np.cpp",
          "Np::GetPeerProcessId",
          1513,
          L"API|SNI%u#, ",
          ppsidGroup);
      }
      LastError = 0;
      ModuleHandleA = GetModuleHandleA("kernel32.dll");
      v59 = "GetNamedPipeServerProcessId";
      if ( (*(_BYTE *)(*(_QWORD *)(v57 + 32) + 12804LL) & 2) == 0 )
        v59 = "GetNamedPipeClientProcessId";
      ProcAddress = GetProcAddress(ModuleHandleA, v59);
      if ( !ProcAddress || !((unsigned int (__fastcall *)(_QWORD, __int64))ProcAddress)(*(_QWORD *)(v57 + 64), a3) )
        LastError = GetLastError();
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(ppsidGroup) = LastError;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\np.cpp",
          "Np::GetPeerProcessId",
          1544,
          L"RET|SNI%d{WINERR}\n",
          ppsidGroup);
      }
      if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
        SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\np.cpp", "Np::GetPeerProcessId", 1513, v61);
      goto LABEL_24;
    case 42:
      *(_QWORD *)a3 = 0;
      LastError = 87;
      v18 = *(SOS_UnfairRecursiveMutexExtendedGuarantee ***)(a1 + 64);
      CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v18);
      v64 = *(_QWORD *)(a1 + 12616);
      while ( 2 )
      {
        if ( v64 )
        {
          if ( *(_DWORD *)(v64 + 24) != 6 || !*(_DWORD *)(v64 + 40) )
          {
            v64 = *(_QWORD *)(v64 + 8);
            continue;
          }
          LastError = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v64 + 144LL))(v64, a3);
        }
        break;
      }
      goto LABEL_198;
    case 43:
      v18 = *(SOS_UnfairRecursiveMutexExtendedGuarantee ***)(a1 + 64);
      CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v18);
      v62 = *(_QWORD *)(a1 + 12616);
      if ( !v62 )
        goto LABEL_176;
      while ( *(_DWORD *)(v62 + 24) != 1 )
      {
        v62 = *(_QWORD *)(v62 + 8);
        if ( !v62 )
        {
LABEL_176:
          *(_QWORD *)a3 = 0;
          *(_QWORD *)(a3 + 8) = 0;
          LastError = 87;
          goto LABEL_198;
        }
      }
      LastError = GetSecurityInfo(
                    *(HANDLE *)(v62 + 64),
                    SE_KERNEL_OBJECT,
                    1u,
                    (PSID *)a3,
                    0,
                    0,
                    0,
                    (PSECURITY_DESCRIPTOR *)(a3 + 8));
LABEL_198:
      SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v18[1]);
      goto LABEL_232;
    case 44:
      v70 = 99304;
      v12 = *(SOS_UnfairRecursiveMutexExtendedGuarantee ***)(a1 + 64);
      CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v12);
      for ( nn = *(_QWORD **)(a1 + 12616); nn; nn = (_QWORD *)nn[1] )
      {
        if ( v70 >= (*(unsigned int (__fastcall **)(_QWORD *))(*nn + 104LL))(nn) )
          v70 = (*(__int64 (__fastcall **)(_QWORD *))(*nn + 104LL))(nn);
      }
      *(_DWORD *)a3 = v70;
      goto LABEL_24;
    case 45:
      v27 = *(SOS_UnfairRecursiveMutexExtendedGuarantee ***)(a1 + 64);
      CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v27);
      *(_DWORD *)a3 = *(_DWORD *)(*(_QWORD *)(a1 + 12616) + 24LL);
      SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v27[1]);
      goto LABEL_232;
    case 47:
      LastError = 87;
      v12 = *(SOS_UnfairRecursiveMutexExtendedGuarantee ***)(a1 + 64);
      CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v12);
      v72 = *(_QWORD *)(a1 + 12616);
      if ( !v72 )
        goto LABEL_24;
      break;
    case 48:
      v31 = (*(unsigned __int8 *)(a1 + 12804) >> 1) & 1;
LABEL_231:
      *(_DWORD *)a3 = v31;
      goto LABEL_232;
    case 49:
      v12 = *(SOS_UnfairRecursiveMutexExtendedGuarantee ***)(a1 + 64);
      CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v12);
      LastError = 3;
      v13 = *(_QWORD *)(a1 + 12616);
      while ( 2 )
      {
        if ( v13 )
        {
          if ( *(_DWORD *)(v13 + 24) != 6 || !*(_DWORD *)(v13 + 40) )
          {
            v13 = *(_QWORD *)(v13 + 8);
            continue;
          }
          LastError = ((__int64 (__fastcall *)(__int64, __int64, const char **))Ssl::s_pfTable->QueryContextAttributesW)(
                        v13 + 392,
                        90,
                        &v83);
          if ( !LastError )
          {
            *(_DWORD *)a3 = (_DWORD)v83;
            *(_DWORD *)(a3 + 8) = HIDWORD(v83);
            *(_DWORD *)(a3 + 4) = HIDWORD(v84);
            memset_0(&v86, 0, sizeof(v86));
            if ( !Ssl::GetSslCipherInfo((Ssl *)v13, &v86) )
            {
              *(_DWORD *)(a3 + 12) = v86.dwHashLen;
              v14 = (_WORD *)(a3 + 16);
              v15 = 64;
              do
              {
                if ( v15 == -2147483582 )
                  break;
                v16 = *(_WORD *)((char *)v14 + (_QWORD)&v86 - a3);
                if ( !v16 )
                  break;
                *v14++ = v16;
                --v15;
              }
              while ( v15 );
              v17 = v14 - 1;
              if ( v15 )
                v17 = v14;
              *v17 = 0;
            }
          }
        }
        break;
      }
      goto LABEL_24;
    case 56:
      v18 = *(SOS_UnfairRecursiveMutexExtendedGuarantee ***)(a1 + 64);
      CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v18);
      v19 = *(_QWORD *)(a1 + 12616);
      while ( 2 )
      {
        if ( v19 )
        {
          if ( *(_DWORD *)(v19 + 24) != 6 || !*(_DWORD *)(v19 + 40) )
          {
            v19 = *(_QWORD *)(v19 + 8);
            continue;
          }
          LastError = Ssl::GetSslCipherInfo((Ssl *)v19, (struct _SecPkgContext_CipherInfo *)a3);
        }
        break;
      }
      goto LABEL_198;
    default:
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        SNIXE_SNI_ERROR_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNIGetInfo", 5671, L"ERR|SNIQType is unknown\n");
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(ppSacl) = 87;
          LODWORD(ppDacl) = 0;
          LODWORD(ppsidGroup) = 10;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\sni.cpp",
            "SNIGetInfo",
            5672,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            ppsidGroup,
            ppDacl,
            ppSacl);
        }
      }
      SNISetLastError(10, 87, 50100);
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(ppsidGroup) = 87;
        SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNIGetInfo", 5674, L"RET|SNI%d{WINERR}\n", ppsidGroup);
      }
      LastError = 87;
      goto LABEL_240;
  }
  while ( *(_DWORD *)(v72 + 24) != 8 )
  {
    v72 = *(_QWORD *)(v72 + 8);
    if ( !v72 )
      goto LABEL_24;
  }
  if ( !*(_BYTE *)(v72 + 51) )
  {
    v73 = 4;
    goto LABEL_228;
  }
  if ( *(_BYTE *)(v72 + 51) == 1 )
  {
    v73 = 16;
LABEL_228:
    memmove((void *)a3, (const void *)(v72 + 52), v73);
    *(_DWORD *)(a3 + 16) = v73;
    *(_DWORD *)(a3 + 29) = *(_DWORD *)(v72 + 71);
    *(_DWORD *)(a3 + 36) = 4;
    *(_BYTE *)(a3 + 28) = *(_BYTE *)(v72 + 70) != 6;
    *(_DWORD *)(a3 + 20) = *(_BYTE *)(v72 + 68) != 6;
    *(_DWORD *)(a3 + 24) = *(_BYTE *)(v72 + 69) != 6;
    LastError = 0;
    goto LABEL_24;
  }
  LastError = 13;
LABEL_24:
  SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v12[1]);
LABEL_232:
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNIGetInfo", 5679, L"RET|SNIQInfo: %p\n", a3);
LABEL_240:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON(v79, v80, v81, a4);
  return LastError;
}

```

## disassembly

```asm
0x1004269b0  push    rbp
0x1004269b2  push    rsi
0x1004269b3  push    rdi
0x1004269b4  push    r12
0x1004269b6  push    r13
0x1004269b8  push    r14
0x1004269ba  push    r15
0x1004269bc  lea     rbp, [rsp-260h]
0x1004269c4  sub     rsp, 360h
0x1004269cb  mov     [rsp+390h+var_318], 0FFFFFFFFFFFFFFFEh
0x1004269d4  mov     [rsp+390h+arg_18], rbx
0x1004269dc  mov     rax, cs:__security_cookie
0x1004269e3  xor     rax, rsp
0x1004269e6  mov     [rbp+290h+var_40], rax
0x1004269ed  mov     rdi, r8
0x1004269f0  mov     ebx, edx
0x1004269f2  mov     rsi, rcx
0x1004269f5  lea     r13, aSqlCommonDkSni_13; "sql\\common\\dk\\sni\\src\\sni.cpp"
0x1004269fc  mov     [rsp+390h+var_330], r13
0x100426a01  lea     r12, aSnigetinfo; "SNIGetInfo"
0x100426a08  mov     [rsp+390h+var_328], r12
0x100426a0d  mov     [rsp+390h+var_320], 13BBh
0x100426a15  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100426a1c  jz      short loc_100426A44
0x100426a1e  mov     [rsp+390h+ppSacl], r8
0x100426a23  mov     dword ptr [rsp+390h+ppDacl], edx
0x100426a27  mov     [rsp+390h+ppsidGroup], rcx
0x100426a2c  lea     r9, aApiSnipconnPSn_10; "API|SNIpConn: %p{SNI_Conn*}, QType: %d,"...
0x100426a33  mov     r8d, 13BBh; int
0x100426a39  mov     rdx, r12; char *
0x100426a3c  mov     rcx, r13; char *
0x100426a3f  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100426a44  xor     r14d, r14d
0x100426a47  mov     r15d, r14d
0x100426a4a  lea     eax, [rbx-1]; switch 56 cases
0x100426a4d  cmp     eax, 37h
0x100426a50  ja      def_100426A67; jumptable 0000000100426A67 default case, cases 3-7,25,36,39,40,46,50-55
0x100426a56  lea     rdx, cs:100400000h
0x100426a5d  mov     ecx, ds:(jpt_100426A67 - 100400000h)[rdx+rax*4]
0x100426a64  add     rcx, rdx
0x100426a67  jmp     rcx; switch jump
0x100426a69  mov     rbx, [rsi+40h]; jumptable 0000000100426A67 case 8
0x100426a6d  mov     [rsp+390h+var_350], rbx
0x100426a72  mov     dword ptr [rsp+390h+var_348], r14d
0x100426a77  mov     rcx, rbx; this
0x100426a7a  call    ?Enter@CCriticalSectionSOS@@QEAAXXZ; CCriticalSectionSOS::Enter(void)
0x100426a7f  mov     dword ptr [rsp+390h+var_348], 1
0x100426a87  mov     rax, [rsi+3148h]
0x100426a8e  test    rax, rax
0x100426a91  jz      short loc_100426AAB
0x100426a93  cmp     dword ptr [rax+18h], 6
0x100426a97  jnz     short loc_100426A9F
0x100426a99  cmp     dword ptr [rax+28h], 0
0x100426a9d  jnz     short loc_100426AA8
0x100426a9f  mov     rax, [rax+8]
0x100426aa3  test    rax, rax
0x100426aa6  jnz     short loc_100426A93
0x100426aa8  test    rax, rax
0x100426aab  setnz   r14b
0x100426aaf  mov     [rdi], r14d
0x100426ab2  mov     rcx, [rbx+8]; this
0x100426ab6  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x100426abb  jmp     loc_100427C5B
0x100426ac0  mov     r13, [rsi+40h]; jumptable 0000000100426A67 case 49
0x100426ac4  mov     [rsp+390h+var_350], r13
0x100426ac9  mov     dword ptr [rsp+390h+var_348], r14d
0x100426ace  mov     rcx, r13; this
0x100426ad1  call    ?Enter@CCriticalSectionSOS@@QEAAXXZ; CCriticalSectionSOS::Enter(void)
0x100426ad6  mov     dword ptr [rsp+390h+var_348], 1
0x100426ade  mov     r15d, 3
0x100426ae4  mov     rbx, [rsi+3148h]
0x100426aeb  test    rbx, rbx
0x100426aee  jz      loc_100426BB2
0x100426af4  cmp     dword ptr [rbx+18h], 6
0x100426af8  jnz     short loc_100426B00
0x100426afa  cmp     dword ptr [rbx+28h], 0
0x100426afe  jnz     short loc_100426B06
0x100426b00  mov     rbx, [rbx+8]
0x100426b04  jmp     short loc_100426AEB
0x100426b06  lea     rcx, [rbx+188h]
0x100426b0d  lea     r8, [rbp+290h+var_310]
0x100426b11  mov     edx, 5Ah ; 'Z'
0x100426b16  mov     rax, cs:?s_pfTable@Ssl@@0PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * Ssl::s_pfTable
0x100426b1d  call    qword ptr [rax+58h]
0x100426b20  mov     r15d, eax
0x100426b23  test    eax, eax
0x100426b25  jnz     loc_100426BB2
0x100426b2b  mov     eax, dword ptr [rbp+290h+var_310]
0x100426b2e  mov     [rdi], eax
0x100426b30  mov     eax, dword ptr [rbp+290h+var_310+4]
0x100426b33  mov     [rdi+8], eax
0x100426b36  mov     eax, [rbp+290h+var_304]
0x100426b39  mov     [rdi+4], eax
0x100426b3c  xor     edx, edx; Val
0x100426b3e  mov     r8d, 2A8h; Size
0x100426b44  lea     rcx, [rbp+290h+var_2F0]; void *
0x100426b48  call    memset_0
0x100426b4d  lea     rdx, [rbp+290h+var_2F0]; struct _SecPkgContext_CipherInfo *
0x100426b51  mov     rcx, rbx; this
0x100426b54  call    ?GetSslCipherInfo@Ssl@@QEAAKPEAU_SecPkgContext_CipherInfo@@@Z; Ssl::GetSslCipherInfo(_SecPkgContext_CipherInfo *)
0x100426b59  test    eax, eax
0x100426b5b  jnz     short loc_100426BB2
0x100426b5d  mov     eax, [rbp+290h+var_2F0.dwHashLen]
0x100426b63  mov     [rdi+0Ch], eax
0x100426b66  lea     rcx, [rdi+10h]
0x100426b6a  mov     edx, 40h ; '@'
0x100426b6f  lea     r8, [rbp+290h+var_2F0.szCipherSuite]
0x100426b73  sub     r8, rcx
0x100426b76  nop     word ptr [rax+rax+00000000h]
0x100426b80  lea     rax, [rdx+7FFFFFBEh]
0x100426b87  test    rax, rax
0x100426b8a  jz      short loc_100426BA3
0x100426b8c  movzx   eax, word ptr [r8+rcx]
0x100426b91  test    ax, ax
0x100426b94  jz      short loc_100426BA3
0x100426b96  mov     [rcx], ax
0x100426b99  add     rcx, 2
0x100426b9d  sub     rdx, 1
0x100426ba1  jnz     short loc_100426B80
0x100426ba3  lea     rax, [rcx-2]
0x100426ba7  test    rdx, rdx
0x100426baa  cmovnz  rax, rcx
0x100426bae  mov     [rax], r14w
0x100426bb2  mov     rcx, [r13+8]; this
0x100426bb6  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x100426bbb  lea     r13, aSqlCommonDkSni_13; "sql\\common\\dk\\sni\\src\\sni.cpp"
0x100426bc2  jmp     loc_100427C5B
0x100426bc7  mov     rbx, [rsi+40h]; jumptable 0000000100426A67 case 56
0x100426bcb  mov     [rsp+390h+var_350], rbx
0x100426bd0  mov     dword ptr [rsp+390h+var_348], r14d
0x100426bd5  mov     rcx, rbx; this
0x100426bd8  call    ?Enter@CCriticalSectionSOS@@QEAAXXZ; CCriticalSectionSOS::Enter(void)
0x100426bdd  mov     dword ptr [rsp+390h+var_348], 1
0x100426be5  mov     rcx, [rsi+3148h]; this
0x100426bec  test    rcx, rcx
0x100426bef  jz      short loc_100426C0E
0x100426bf1  cmp     dword ptr [rcx+18h], 6
0x100426bf5  jnz     short loc_100426BFD
0x100426bf7  cmp     dword ptr [rcx+28h], 0
0x100426bfb  jnz     short loc_100426C03
0x100426bfd  mov     rcx, [rcx+8]
0x100426c01  jmp     short loc_100426BEC
0x100426c03  mov     rdx, rdi; struct _SecPkgContext_CipherInfo *
0x100426c06  call    ?GetSslCipherInfo@Ssl@@QEAAKPEAU_SecPkgContext_CipherInfo@@@Z; Ssl::GetSslCipherInfo(_SecPkgContext_CipherInfo *)
0x100426c0b  mov     r15d, eax
0x100426c0e  mov     rcx, [rbx+8]; this
0x100426c12  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x100426c17  jmp     loc_100427C5B
0x100426c1c  mov     rbx, [rsi+40h]; jumptable 0000000100426A67 case 33
0x100426c20  mov     [rsp+390h+var_350], rbx
0x100426c25  mov     dword ptr [rsp+390h+var_348], r14d
0x100426c2a  mov     rcx, rbx; this
0x100426c2d  call    ?Enter@CCriticalSectionSOS@@QEAAXXZ; CCriticalSectionSOS::Enter(void)
0x100426c32  mov     dword ptr [rsp+390h+var_348], 1
0x100426c3a  mov     rcx, [rsi+3148h]
0x100426c41  mov     rax, [rcx]
0x100426c44  call    qword ptr [rax+0D8h]
0x100426c4a  test    al, al
0x100426c4c  setnz   r14b
0x100426c50  mov     [rdi], r14d
0x100426c53  mov     rcx, [rbx+8]; this
0x100426c57  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x100426c5c  jmp     loc_100427C5B
0x100426c61  mov     rbx, [rsi+40h]; jumptable 0000000100426A67 case 9
0x100426c65  mov     [rsp+390h+var_350], rbx
0x100426c6a  mov     dword ptr [rsp+390h+var_348], r14d
0x100426c6f  mov     rcx, rbx; this
0x100426c72  call    ?Enter@CCriticalSectionSOS@@QEAAXXZ; CCriticalSectionSOS::Enter(void)
0x100426c77  mov     dword ptr [rsp+390h+var_348], 1
0x100426c7f  mov     rax, [rsi+3148h]
0x100426c86  mov     rcx, [rax+8]
0x100426c8a  test    rcx, rcx
0x100426c8d  jz      short loc_100426CA2
0x100426c8f  nop
0x100426c90  cmp     dword ptr [rax+18h], 2
0x100426c94  jz      short loc_100426CA2
0x100426c96  mov     rax, rcx
0x100426c99  mov     rcx, [rcx+8]
0x100426c9d  test    rcx, rcx
0x100426ca0  jnz     short loc_100426C90
0x100426ca2  mov     eax, [rax+18h]
0x100426ca5  mov     [rdi], eax
0x100426ca7  mov     rcx, [rbx+8]; this
0x100426cab  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x100426cb0  jmp     loc_100427C5B
0x100426cb5  mov     rbx, [rsi+40h]; jumptable 0000000100426A67 case 32
0x100426cb9  mov     [rsp+390h+var_350], rbx
0x100426cbe  mov     dword ptr [rsp+390h+var_348], r14d
0x100426cc3  mov     rcx, rbx; this
0x100426cc6  call    ?Enter@CCriticalSectionSOS@@QEAAXXZ; CCriticalSectionSOS::Enter(void)
0x100426ccb  mov     dword ptr [rsp+390h+var_348], 1
0x100426cd3  mov     rcx, [rsi+3148h]
0x100426cda  mov     rax, [rcx+8]
0x100426cde  test    rax, rax
0x100426ce1  jz      short loc_100426CEF
0x100426ce3  mov     rcx, rax
0x100426ce6  mov     rax, [rax+8]
0x100426cea  test    rax, rax
0x100426ced  jnz     short loc_100426CE3
0x100426cef  mov     eax, [rcx+18h]
0x100426cf2  mov     [rdi], eax
0x100426cf4  mov     rcx, [rbx+8]; this
0x100426cf8  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x100426cfd  jmp     loc_100427C5B
0x100426d02  mov     rbx, [rsi+40h]; jumptable 0000000100426A67 case 45
0x100426d06  mov     [rsp+390h+var_350], rbx
0x100426d0b  mov     dword ptr [rsp+390h+var_348], r14d
0x100426d10  mov     rcx, rbx; this
0x100426d13  call    ?Enter@CCriticalSectionSOS@@QEAAXXZ; CCriticalSectionSOS::Enter(void)
0x100426d18  mov     dword ptr [rsp+390h+var_348], 1
0x100426d20  mov     rax, [rsi+3148h]
0x100426d27  mov     ecx, [rax+18h]
0x100426d2a  mov     [rdi], ecx
0x100426d2c  mov     rcx, [rbx+8]; this
0x100426d30  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x100426d35  jmp     loc_100427C5B
0x100426d3a  movups  xmm0, xmmword ptr [rsi+1Ch]; jumptable 0000000100426A67 case 10
0x100426d3e  movups  xmmword ptr [rdi], xmm0
0x100426d41  jmp     loc_100427C5B
0x100426d46  movups  xmm0, xmmword ptr [rsi+2Ch]; jumptable 0000000100426A67 case 34
0x100426d4a  movups  xmmword ptr [rdi], xmm0
0x100426d4d  jmp     loc_100427C5B
0x100426d52  mov     rbx, [rsi+40h]; jumptable 0000000100426A67 case 11
0x100426d56  mov     [rsp+390h+var_350], rbx
0x100426d5b  mov     dword ptr [rsp+390h+var_348], r14d
0x100426d60  mov     rcx, rbx; this
0x100426d63  call    ?Enter@CCriticalSectionSOS@@QEAAXXZ; CCriticalSectionSOS::Enter(void)
0x100426d68  mov     dword ptr [rsp+390h+var_348], 1
0x100426d70  mov     rcx, [rsi+3148h]
0x100426d77  mov     rax, rcx
0x100426d7a  test    rcx, rcx
0x100426d7d  jz      short loc_100426D8F
0x100426d7f  nop
0x100426d80  cmp     dword ptr [rax+18h], 2
0x100426d84  jz      short loc_100426DA3
0x100426d86  mov     rax, [rax+8]
0x100426d8a  test    rax, rax
0x100426d8d  jnz     short loc_100426D80
0x100426d8f  mov     r15d, 57h ; 'W'
0x100426d95  mov     rcx, [rbx+8]; this
0x100426d99  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x100426d9e  jmp     loc_100427C5B
0x100426da3  lea     rax, [rcx]
0x100426da6  mov     rcx, [rcx+8]
0x100426daa  test    rcx, rcx
0x100426dad  jnz     short loc_100426DA3
0x100426daf  mov     rax, [rax+20h]
0x100426db3  movups  xmm0, xmmword ptr [rax+1Ch]
0x100426db7  movups  xmmword ptr [rdi], xmm0
0x100426dba  jmp     short loc_100426D95
0x100426dbc  mov     eax, [rsi+31D0h]; jumptable 0000000100426A67 case 1
0x100426dc2  jmp     loc_100427C59
0x100426dc7  mov     rax, [rsi+3208h]; jumptable 0000000100426A67 case 12
0x100426dce  mov     ecx, [rax+14h]
0x100426dd1  mov     [rdi], ecx
0x100426dd3  jmp     loc_100427C5B
0x100426dd8  mov     rsi, [rsi+3208h]; jumptable 0000000100426A67 case 26
0x100426ddf  test    rsi, rsi
0x100426de2  jnz     short loc_100426DED
0x100426de4  lea     r15d, [rsi+57h]
0x100426de8  jmp     loc_100427C5B
0x100426ded  lea     rbx, aSqlCommonDkSni_20; "sql\\common\\dk\\sni\\src\\sni_sspi.cpp"
0x100426df4  mov     [rsp+390h+var_350], rbx
0x100426df9  lea     r12, aSniSecGetsecpk; "SNI_Sec::GetSecPkgName"
0x100426e00  mov     [rsp+390h+var_348], r12
0x100426e05  mov     [rsp+390h+var_340], 0C1h
0x100426e0d  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100426e14  jz      short loc_100426E33
0x100426e16  mov     [rsp+390h+ppsidGroup], rdi
0x100426e1b  lea     r9, aApiSnipppkgnam; "API|SNIppPkgName: %p{LPTSTR*}\n"
0x100426e22  mov     r8d, 0C1h; int
0x100426e28  mov     rdx, r12; char *
0x100426e2b  mov     rcx, rbx; char *
0x100426e2e  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100426e33  mov     r15d, [rsi+30h]
0x100426e37  test    r15d, r15d
0x100426e3a  jz      short loc_100426E87
0x100426e3c  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100426e43  jz      short loc_100426E6F
0x100426e45  mov     dword ptr [rsp+390h+ppSacl], r15d
0x100426e4a  mov     dword ptr [rsp+390h+ppDacl], r14d
0x100426e4f  mov     dword ptr [rsp+390h+ppsidGroup], 0Ah
0x100426e57  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100426e5e  mov     r8d, 0C7h; int
0x100426e64  mov     rdx, r12; char *
0x100426e67  mov     rcx, rbx; char *
0x100426e6a  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100426e6f  mov     r8d, 0C3B4h
0x100426e75  mov     edx, r15d
0x100426e78  mov     ecx, 0Ah
0x100426e7d  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100426e82  mov     [rdi], r14
0x100426e85  jmp     short loc_100426EEA
0x100426e87  cmp     dword ptr [rsi+14h], 5
0x100426e8b  jnz     short loc_100426EB6
0x100426e8d  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100426e94  jz      short loc_100426EAE
0x100426e96  lea     r9, aErrSniunexpect_0; "ERR|SNIUnexpected call to GetSecPkgName"...
0x100426e9d  mov     r8d, 0D6h; int
0x100426ea3  mov     rdx, r12; char *
  ... truncated ...
```
