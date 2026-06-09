# SNISecInitPackageEx

- ea: `0x10042a070`
- end: `0x10042a7cc`
- name: `SNISecInitPackageEx`
- size: `1884`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x100404a00`

## callees

- `0x100405270`
- `0x100405390`
- `0x10042a070`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x100456020`
- `0x100456580`
- `0x10045d370`
- `0x100486250`
- `0x100486af0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x10042a6b7`
- `KERNEL32!FreeLibrary` at `0x10042a6b7`
- `KERNEL32!SetLastError` at `0x10042a14b`
- `KERNEL32!SetLastError` at `0x10042a14b`
- `KERNEL32!GetProcAddress` at `0x10042a201`
- `KERNEL32!GetProcAddress` at `0x10042a201`
- `KERNEL32!GetLastError` at `0x10042a20f`
- `KERNEL32!GetLastError` at `0x10042a378`
- `KERNEL32!GetLastError` at `0x10042a20f`
- `KERNEL32!GetLastError` at `0x10042a378`
- `sqldk!?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z` at `0x10042a189`
- `sqldk!?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z` at `0x10042a189`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x10042a712`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x10042a712`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10042a2e8`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10042a2e8`
- `sqldk!SystemThread_TlsIndex` at `0x10042a2a7`
- `sqldk!SystemThread_TlsIndex` at `0x10042a2fd`
- `sqldk!SystemThread_TlsOffset` at `0x10042a2b0`
- `sqldk!SystemThread_TlsOffset` at `0x10042a306`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10042a2cb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10042a321`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10042a2cb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10042a321`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x10042a70b`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x10042a175`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x10042a175`

## string_xrefs

- `0x10042a0c1`: `sql\common\dk\sni\src\sni_sspi.cpp`
- `0x10042a4d0`: `sql\common\dk\sni\src\sni_sspi.cpp`
- `0x10042a4e3`: `sql\common\dk\sni\src\sni_sspi.cpp`
- `0x10042a58c`: `sql\common\dk\sni\src\sni_sspi.cpp`
- `0x10042a59d`: `sql\common\dk\sni\src\sni_sspi.cpp`
- `0x10042a629`: `sql\common\dk\sni\src\sni_sspi.cpp`
- `0x10042a63a`: `sql\common\dk\sni\src\sni_sspi.cpp`
- `0x10042a770`: `sql\common\dk\sni\src\sni_sspi.cpp`
- `0x10042a794`: `sql\common\dk\sni\src\sni_sspi.cpp`
- `0x10042a0f5`: `API|SNIpcbMaxToken: %p{DWORD*}, fInitializeSPN: %d{BOOL}fInitializeServerCredential: %d{BOOL}`
- `0x10042a1f7`: `InitSecurityInterfaceW`
- `0x10042a12c`: `secforwarder.dll`
- `0x10042a16c`: `secforwarder.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall SNISecInitPackageEx(_DWORD *a1, int a2, int a3)
{
  _DWORD *v5; // r13
  int v6; // edi
  __int64 v7; // rcx
  const char *v8; // rax
  HMODULE v9; // rax
  unsigned int v10; // ebx
  __int64 (*ProcAddress)(void); // rdi
  DWORD LastError; // eax
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rbx
  __int64 v17; // rdx
  struct _SECURITY_FUNCTION_TABLE_W *v18; // rax
  DWORD v19; // eax
  char v20; // r14
  __int64 v21; // rdi
  __int64 v22; // rsi
  unsigned int v23; // ecx
  unsigned int v24; // eax
  unsigned int v25; // eax
  const wchar_t *v26; // r9
  __int64 v28; // [rsp+20h] [rbp-E0h]
  __int64 v29; // [rsp+28h] [rbp-D8h]
  __int64 v30; // [rsp+30h] [rbp-D0h]
  int v31; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+68h] [rbp-98h]
  int v33; // [rsp+70h] [rbp-90h] BYREF
  int v34; // [rsp+74h] [rbp-8Ch]
  __int64 v35; // [rsp+78h] [rbp-88h]
  int v36; // [rsp+80h] [rbp-80h] BYREF
  __int64 v37; // [rsp+88h] [rbp-78h]
  __int64 v38; // [rsp+90h] [rbp-70h]
  __int64 v39; // [rsp+98h] [rbp-68h]
  __int64 v40; // [rsp+A0h] [rbp-60h]
  bool v41; // [rsp+B0h] [rbp-50h]
  __int64 v42; // [rsp+C0h] [rbp-40h] BYREF
  _DWORD *v43; // [rsp+C8h] [rbp-38h]
  __int64 v44; // [rsp+D0h] [rbp-30h]
  int *v45; // [rsp+D8h] [rbp-28h]
  _BYTE v46[8]; // [rsp+E0h] [rbp-20h] BYREF
  const char *v47; // [rsp+E8h] [rbp-18h]
  const char *v48; // [rsp+F0h] [rbp-10h]
  int v49; // [rsp+F8h] [rbp-8h]
  wchar_t v50[264]; // [rsp+100h] [rbp+0h] BYREF

  v44 = -2;
  v5 = a1;
  v43 = a1;
  v6 = 0;
  v47 = "sql\\common\\dk\\sni\\src\\sni_sspi.cpp";
  v48 = "SNISecInitPackageEx";
  v49 = 287;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\sni_sspi.cpp",
      "SNISecInitPackageEx",
      287,
      L"API|SNIpcbMaxToken: %p{DWORD*}, fInitializeSPN: %d{BOOL}fInitializeServerCredential: %d{BOOL}",
      a1,
      a2,
      a3);
  qword_100516B70 = -1;
  ghSspiCred.dwLower = -1;
  *v5 = 0;
  v7 = 261;
  v8 = "secforwarder.dll";
  while ( *v8 )
  {
    ++v8;
    if ( !--v7 )
    {
      SetLastError(0x7Bu);
      g_hSspiLib = 0;
      goto LABEL_8;
    }
  }
  FastDBCSToUnicode(0, "secforwarder.dll", -1, v50, 261);
  v9 = SOS_OS::SOSLoadLibraryW(v50, 1, 0, 0);
  g_hSspiLib = v9;
  if ( !v9 )
  {
LABEL_8:
    v10 = -1;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v30) = -1;
      LODWORD(v29) = 22;
      LODWORD(v28) = 10;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\sni_sspi.cpp",
        "SNISecInitPackageEx",
        337,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v28,
        v29,
        v30);
    }
    SNISetLastError(10, 0xFFFFFFFFLL, 50122);
    goto LABEL_56;
  }
  ProcAddress = GetProcAddress(v9, "InitSecurityInterfaceW");
  if ( !ProcAddress )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v30) = LastError;
      LODWORD(v29) = 0;
      LODWORD(v28) = 10;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\sni_sspi.cpp",
        "SNISecInitPackageEx",
        351,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v28,
        v29,
        v30);
    }
    SNISetLastError(10, v10, 50100);
    goto LABEL_55;
  }
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v31, 1);
  v45 = &v33;
  v36 = 536871395;
  v37 = 0;
  v39 = 0;
  v38 = 0;
  v40 = 0;
  v41 = 0;
  v13 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v14 = *(_QWORD *)(v13 + 256);
  if ( !v14 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v14 = *(_QWORD *)(v13 + 256);
  }
  v15 = *(_QWORD *)(v14 + 600);
  if ( v15 )
    v41 = (unsigned int)SOS_Task::PushWait(v15, &v36) == 0;
  v16 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v17 = *(_QWORD *)(v16 + 256);
  if ( !v17 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v17 = *(_QWORD *)(v16 + 256);
  }
  v35 = v17;
  v34 = (*(_DWORD *)(v17 + 800) >> 11) & 1;
  if ( v34 || (*(_BYTE *)(v17 + 800) & 4) == 0 )
  {
    v33 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v17 + 608) + 8LL))(*(_QWORD *)(v17 + 608));
  }
  else
  {
    v33 = 0;
  }
  v18 = (struct _SECURITY_FUNCTION_TABLE_W *)ProcAddress();
  g_pFuncs = v18;
  if ( !v18 )
  {
    v19 = GetLastError();
    v10 = v19;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v30) = v19;
      LODWORD(v29) = 0;
      LODWORD(v28) = 10;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\sni_sspi.cpp",
        "SNISecInitPackageEx",
        363,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v28,
        v29,
        v30);
    }
LABEL_54:
    SNISetLastError(10, v10, 50100);
    AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v33);
    *(_DWORD *)(v32 + 616) &= ~v31;
LABEL_55:
    v6 = 0;
    goto LABEL_56;
  }
  v20 = 0;
  v21 = 0;
  while ( 1 )
  {
    v10 = ((__int64 (__fastcall *)(wchar_t * near *, __int64 *))v18->QuerySecurityPackageInfoW)((&g_rgszSSP)[v21], &v42);
    if ( !v10 )
    {
      *((_DWORD *)&g_rgfSSPIPackageAvailable + v21) = 1;
      v22 = v42;
      if ( v20 )
      {
        v23 = g_cbSspiMaxToken;
      }
      else
      {
        memmove(&g_szSSP, (&g_rgszSSP)[v21], *((int *)&g_rgcchSSP + v21));
        v23 = *(_DWORD *)(v22 + 8);
        g_cbSspiMaxToken = v23;
        v20 = 1;
      }
      if ( (v21 & 0xFFFFFFFFFFFFFFFDuLL) == 0 )
      {
        if ( *(_DWORD *)(v22 + 8) > v23 )
          v23 = *(_DWORD *)(v22 + 8);
        g_cbSspiMaxToken = v23;
      }
      ((void (__fastcall *)(__int64))g_pFuncs->FreeContextBuffer)(v22);
    }
    if ( ++v21 >= 3 )
      break;
    v18 = g_pFuncs;
  }
  v5 = v43;
  if ( !v20 )
  {
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v30) = v10;
      LODWORD(v29) = 0;
      LODWORD(v28) = 10;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\sni_sspi.cpp",
        "SNISecInitPackageEx",
        408,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v28,
        v29,
        v30);
    }
    goto LABEL_54;
  }
  if ( !a3
    || (v24 = ((__int64 (__fastcall *)(_QWORD, wchar_t near **, __int64, _QWORD, _QWORD, _QWORD, _QWORD, struct _SecHandle *, _BYTE *))g_pFuncs->AcquireCredentialsHandleW)(
                0,
                &g_szSSP,
                3,
                0,
                0,
                0,
                0,
                &ghSspiCred,
                v46),
        (v10 = v24) == 0) )
  {
    if ( !a2 || (v25 = SNI_Spn::SpnInit(), (v10 = v25) == 0) )
    {
      AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v33);
      *(_DWORD *)(v32 + 616) &= ~v31;
      *v5 = g_cbSspiMaxToken;
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\sni_sspi.cpp",
          "SNISecInitPackageEx",
          473,
          L"RET|SNI%d{WINERR}\n",
          0);
      goto LABEL_68;
    }
    scierrlog(0x65B7u, v25);
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v30) = v10;
      LODWORD(v29) = 0;
      LODWORD(v28) = 10;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\sni_sspi.cpp",
        "SNISecInitPackageEx",
        448,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v28,
        v29,
        v30);
    }
    goto LABEL_54;
  }
  v6 = 1;
  if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
  {
    LODWORD(v30) = v24;
    LODWORD(v29) = 0;
    LODWORD(v28) = 10;
    SNIXE_SNI_ERROR_ON(
      "sql\\common\\dk\\sni\\src\\sni_sspi.cpp",
      "SNISecInitPackageEx",
      429,
      L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
      v28,
      v29,
      v30);
  }
  SNISetLastError(10, v10, 50100);
  AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v33);
  *(_DWORD *)(v32 + 616) &= ~v31;
LABEL_56:
  if ( ghSspiCred.dwLower != -1 && qword_100516B70 != -1 )
  {
    ((void (__fastcall *)(struct _SecHandle *))g_pFuncs->FreeCredentialsHandle)(&ghSspiCred);
    qword_100516B70 = -1;
    ghSspiCred.dwLower = -1;
  }
  if ( g_hSspiLib )
    FreeLibrary(g_hSspiLib);
  SNI_Spn::DoSpnTerminate(&ghSpnLib, &ghNetApiLib, &ghSecur, (struct _DsFunctionTable *)&gDsFunc);
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v28) = v10;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\sni_sspi.cpp",
      "SNISecInitPackageEx",
      500,
      L"RET|SNI%d{WINERR}\n",
      v28);
  }
  if ( v6 && OsInfo::IsLinux(SOS_OS_OsInfo) )
  {
    *v5 = g_cbSspiMaxToken;
LABEL_68:
    v10 = 0;
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni_sspi.cpp", "SNISecInitPackageEx", 287, v26);
  return v10;
}

```

## disassembly

```asm
0x10042a070  push    rbp
0x10042a072  push    rsi
0x10042a073  push    rdi
0x10042a074  push    r12
0x10042a076  push    r13
0x10042a078  push    r14
0x10042a07a  push    r15
0x10042a07c  lea     rbp, [rsp-220h]
0x10042a084  sub     rsp, 320h
0x10042a08b  mov     [rbp+250h+var_280], 0FFFFFFFFFFFFFFFEh
0x10042a093  mov     [rsp+350h+arg_18], rbx
0x10042a09b  mov     rax, cs:__security_cookie
0x10042a0a2  xor     rax, rsp
0x10042a0a5  mov     [rbp+250h+var_40], rax
0x10042a0ac  mov     r15d, r8d
0x10042a0af  mov     r12d, edx
0x10042a0b2  mov     r13, rcx
0x10042a0b5  mov     [rbp+250h+var_288], rcx
0x10042a0b9  xor     esi, esi
0x10042a0bb  mov     edi, esi
0x10042a0bd  mov     [rsp+350h+var_300], esi
0x10042a0c1  lea     r14, aSqlCommonDkSni_20; "sql\\common\\dk\\sni\\src\\sni_sspi.cpp"
0x10042a0c8  mov     [rbp+250h+var_268], r14
0x10042a0cc  lea     rax, aSnisecinitpack_0; "SNISecInitPackageEx"
0x10042a0d3  mov     [rbp+250h+var_260], rax
0x10042a0d7  mov     [rbp+250h+var_258], 11Fh
0x10042a0de  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10042a0e5  jz      short loc_10042A10D
0x10042a0e7  mov     dword ptr [rsp+350h+var_320], r8d
0x10042a0ec  mov     dword ptr [rsp+350h+var_328], edx
0x10042a0f0  mov     [rsp+350h+var_330], rcx
0x10042a0f5  lea     r9, aApiSnipcbmaxto; "API|SNIpcbMaxToken: %p{DWORD*}, fInitia"...
0x10042a0fc  mov     r8d, 11Fh; int
0x10042a102  mov     rdx, rax; char *
0x10042a105  mov     rcx, r14; char *
0x10042a108  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10042a10d  mov     cs:qword_100516B70, 0FFFFFFFFFFFFFFFFh
0x10042a118  mov     cs:?ghSspiCred@@3U_SecHandle@@A, 0FFFFFFFFFFFFFFFFh; _SecHandle ghSspiCred
0x10042a123  mov     [r13+0], esi
0x10042a127  mov     ecx, 105h
0x10042a12c  lea     rax, aSecforwarderDl; "secforwarder.dll"
0x10042a133  cmp     byte ptr [rax], 0
0x10042a136  jz      short loc_10042A15A
0x10042a138  inc     rax
0x10042a13b  sub     rcx, 1
0x10042a13f  jnz     short loc_10042A133
0x10042a141  test    rcx, rcx
0x10042a144  jnz     short loc_10042A15A
0x10042a146  mov     ecx, 7Bh ; '{'; dwErrCode
0x10042a14b  call    cs:__imp_SetLastError
0x10042a151  mov     cs:?g_hSspiLib@@3PEAUHINSTANCE__@@EA, rsi; HINSTANCE__ * g_hSspiLib
0x10042a158  jmp     short loc_10042A19B
0x10042a15a  mov     dword ptr [rsp+350h+var_330], 105h
0x10042a162  lea     r9, [rbp+250h+var_250]
0x10042a166  mov     r8d, 0FFFFFFFFh
0x10042a16c  lea     rdx, aSecforwarderDl; "secforwarder.dll"
0x10042a173  xor     ecx, ecx
0x10042a175  call    cs:__imp_?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z; FastDBCSToUnicode(uint,char const *,int,wchar_t *,int)
0x10042a17b  xor     r9d, r9d
0x10042a17e  xor     r8d, r8d
0x10042a181  lea     edx, [r9+1]
0x10042a185  lea     rcx, [rbp+250h+var_250]
0x10042a189  call    cs:__imp_?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z; SOS_OS::SOSLoadLibraryW(wchar_t const *,int,wchar_t const *,int)
0x10042a18f  mov     cs:?g_hSspiLib@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hSspiLib
0x10042a196  test    rax, rax
0x10042a199  jnz     short loc_10042A1F7
0x10042a19b  mov     ebx, 0FFFFFFFFh
0x10042a1a0  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10042a1a7  jz      short loc_10042A1D9
0x10042a1a9  mov     dword ptr [rsp+350h+var_320], ebx
0x10042a1ad  mov     dword ptr [rsp+350h+var_328], 16h
0x10042a1b5  mov     dword ptr [rsp+350h+var_330], 0Ah
0x10042a1bd  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10042a1c4  mov     r8d, 151h; int
0x10042a1ca  lea     rdx, aSnisecinitpack_0; "SNISecInitPackageEx"
0x10042a1d1  mov     rcx, r14; char *
0x10042a1d4  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10042a1d9  mov     r8d, 0C3CAh
0x10042a1df  mov     edx, ebx
0x10042a1e1  mov     ecx, 0Ah
0x10042a1e6  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10042a1eb  lea     r15, ?ghSspiCred@@3U_SecHandle@@A; _SecHandle ghSspiCred
0x10042a1f2  jmp     loc_10042A674
0x10042a1f7  lea     rdx, aInitsecurityin; "InitSecurityInterfaceW"
0x10042a1fe  mov     rcx, rax; hModule
0x10042a201  call    cs:__imp_GetProcAddress
0x10042a207  mov     rdi, rax
0x10042a20a  test    rax, rax
0x10042a20d  jnz     short loc_10042A26A
0x10042a20f  call    cs:__imp_GetLastError
0x10042a215  mov     ebx, eax
0x10042a217  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10042a21e  jz      short loc_10042A24C
0x10042a220  mov     dword ptr [rsp+350h+var_320], eax
0x10042a224  mov     dword ptr [rsp+350h+var_328], esi
0x10042a228  mov     dword ptr [rsp+350h+var_330], 0Ah
0x10042a230  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10042a237  mov     r8d, 15Fh; int
0x10042a23d  lea     rdx, aSnisecinitpack_0; "SNISecInitPackageEx"
0x10042a244  mov     rcx, r14; char *
0x10042a247  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10042a24c  mov     r8d, 0C3B4h
0x10042a252  mov     edx, ebx
0x10042a254  mov     ecx, 0Ah
0x10042a259  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10042a25e  lea     r15, ?ghSspiCred@@3U_SecHandle@@A; _SecHandle ghSspiCred
0x10042a265  jmp     loc_10042A670
0x10042a26a  mov     edx, 1
0x10042a26f  lea     rcx, [rsp+350h+var_2F0]
0x10042a274  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x10042a279  nop
0x10042a27a  lea     rax, [rsp+350h+var_2E0]
0x10042a27f  mov     [rbp+250h+var_278], rax
0x10042a283  mov     [rbp+250h+var_2D0], 200001E3h
0x10042a28a  mov     [rbp+250h+var_2C8], rsi
0x10042a28e  mov     [rbp+250h+var_2B8], rsi
0x10042a292  mov     [rbp+250h+var_2C0], rsi
0x10042a296  mov     [rbp+250h+var_2B0], rsi
0x10042a29a  mov     [rbp+250h+var_2A0], 0
0x10042a29e  mov     rdx, gs:58h
0x10042a2a7  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10042a2ae  mov     ecx, [rax]
0x10042a2b0  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10042a2b7  mov     ebx, [rax]
0x10042a2b9  add     rbx, [rdx+rcx*8]
0x10042a2bd  mov     rax, [rbx+100h]
0x10042a2c4  test    rax, rax
0x10042a2c7  jnz     short loc_10042A2D8
0x10042a2c9  xor     ecx, ecx
0x10042a2cb  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10042a2d1  mov     rax, [rbx+100h]
0x10042a2d8  mov     rcx, [rax+258h]
0x10042a2df  test    rcx, rcx
0x10042a2e2  jz      short loc_10042A2F4
0x10042a2e4  lea     rdx, [rbp+250h+var_2D0]
0x10042a2e8  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x10042a2ee  test    eax, eax
0x10042a2f0  setz    [rbp+250h+var_2A0]
0x10042a2f4  mov     rdx, gs:58h
0x10042a2fd  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10042a304  mov     ecx, [rax]
0x10042a306  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10042a30d  mov     ebx, [rax]
0x10042a30f  add     rbx, [rdx+rcx*8]
0x10042a313  mov     rdx, [rbx+100h]
0x10042a31a  test    rdx, rdx
0x10042a31d  jnz     short loc_10042A32E
0x10042a31f  xor     ecx, ecx
0x10042a321  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10042a327  mov     rdx, [rbx+100h]
0x10042a32e  mov     [rsp+350h+var_2D8], rdx
0x10042a333  mov     eax, [rdx+320h]
0x10042a339  shr     eax, 0Bh
0x10042a33c  and     eax, 1
0x10042a33f  mov     [rsp+350h+var_2DC], eax
0x10042a343  jnz     short loc_10042A354
0x10042a345  test    byte ptr [rdx+320h], 4
0x10042a34c  jz      short loc_10042A354
0x10042a34e  mov     [rsp+350h+var_2E0], esi
0x10042a352  jmp     short loc_10042A36A
0x10042a354  mov     [rsp+350h+var_2E0], 1
0x10042a35c  mov     rcx, [rdx+260h]
0x10042a363  mov     rax, [rcx]
0x10042a366  call    qword ptr [rax+8]
0x10042a369  nop
0x10042a36a  call    rdi
0x10042a36c  mov     cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA, rax; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x10042a373  test    rax, rax
0x10042a376  jnz     short loc_10042A3F0
0x10042a378  call    cs:__imp_GetLastError
0x10042a37e  mov     ebx, eax
0x10042a380  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10042a387  jz      short loc_10042A3B5
0x10042a389  mov     dword ptr [rsp+350h+var_320], eax
0x10042a38d  mov     dword ptr [rsp+350h+var_328], esi
0x10042a391  mov     dword ptr [rsp+350h+var_330], 0Ah
0x10042a399  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10042a3a0  mov     r8d, 16Bh; int
0x10042a3a6  lea     rdx, aSnisecinitpack_0; "SNISecInitPackageEx"
0x10042a3ad  mov     rcx, r14; char *
0x10042a3b0  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10042a3b5  mov     r8d, 0C3B4h
0x10042a3bb  mov     edx, ebx
0x10042a3bd  mov     ecx, 0Ah
0x10042a3c2  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10042a3c7  nop
0x10042a3c8  lea     rcx, [rsp+350h+var_2E0]; this
0x10042a3cd  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x10042a3d2  nop
0x10042a3d3  mov     ecx, [rsp+350h+var_2F0]
0x10042a3d7  not     ecx
0x10042a3d9  mov     rax, [rsp+350h+var_2E8]
0x10042a3de  and     [rax+268h], ecx
0x10042a3e4  lea     r15, ?ghSspiCred@@3U_SecHandle@@A; _SecHandle ghSspiCred
0x10042a3eb  jmp     loc_10042A670
0x10042a3f0  xor     r14b, r14b
0x10042a3f3  mov     rdi, rsi
0x10042a3f6  lea     r13, cs:100400000h
0x10042a3fd  nop     dword ptr [rax]
0x10042a400  lea     rdx, [rbp+250h+var_290]
0x10042a404  mov     rcx, ds:rva ?g_rgszSSP@@3PAPEA_WA[r13+rdi*8]; wchar_t * near * g_rgszSSP ...
0x10042a40c  call    qword ptr [rax+88h]
0x10042a412  mov     ebx, eax
0x10042a414  test    eax, eax
0x10042a416  jnz     short loc_10042A483
0x10042a418  mov     rva ?g_rgfSSPIPackageAvailable@@3PAHA[r13+rdi*4], 1; int near * g_rgfSSPIPackageAvailable ...
0x10042a424  mov     rsi, [rbp+250h+var_290]
0x10042a428  test    r14b, r14b
0x10042a42b  jnz     short loc_10042A457
0x10042a42d  movsxd  r8, ds:rva ?g_rgcchSSP@@3PAHA[r13+rdi*4]; Size
0x10042a435  mov     rdx, ds:rva ?g_rgszSSP@@3PAPEA_WA[r13+rdi*8]; Src
0x10042a43d  lea     rcx, ?g_szSSP@@3PA_WA; void *
0x10042a444  call    memmove
0x10042a449  mov     ecx, [rsi+8]
0x10042a44c  mov     cs:?g_cbSspiMaxToken@@3KA, ecx; ulong g_cbSspiMaxToken
0x10042a452  mov     r14b, 1
0x10042a455  jmp     short loc_10042A45D
0x10042a457  mov     ecx, cs:?g_cbSspiMaxToken@@3KA; ulong g_cbSspiMaxToken
0x10042a45d  test    rdi, 0FFFFFFFFFFFFFFFDh
0x10042a464  jnz     short loc_10042A473
0x10042a466  cmp     [rsi+8], ecx
0x10042a469  cmova   ecx, [rsi+8]
0x10042a46d  mov     cs:?g_cbSspiMaxToken@@3KA, ecx; ulong g_cbSspiMaxToken
0x10042a473  mov     rcx, rsi
0x10042a476  mov     rax, cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x10042a47d  call    qword ptr [rax+80h]
0x10042a483  inc     rdi
0x10042a486  cmp     rdi, 3
0x10042a48a  jge     short loc_10042A498
0x10042a48c  mov     rax, cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x10042a493  jmp     loc_10042A400
0x10042a498  test    r14b, r14b
0x10042a49b  mov     r13, [rbp+250h+var_288]
0x10042a49f  jnz     short loc_10042A50D
0x10042a4a1  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10042a4a8  jz      short loc_10042A4E1
0x10042a4aa  mov     dword ptr [rsp+350h+var_320], ebx
0x10042a4ae  xor     esi, esi
0x10042a4b0  mov     dword ptr [rsp+350h+var_328], esi
0x10042a4b4  mov     dword ptr [rsp+350h+var_330], 0Ah
0x10042a4bc  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10042a4c3  mov     r8d, 198h; int
0x10042a4c9  lea     rdx, aSnisecinitpack_0; "SNISecInitPackageEx"
0x10042a4d0  lea     r14, aSqlCommonDkSni_20; "sql\\common\\dk\\sni\\src\\sni_sspi.cpp"
0x10042a4d7  mov     rcx, r14; char *
0x10042a4da  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10042a4df  jmp     short loc_10042A4EA
0x10042a4e1  xor     esi, esi
0x10042a4e3  lea     r14, aSqlCommonDkSni_20; "sql\\common\\dk\\sni\\src\\sni_sspi.cpp"
0x10042a4ea  mov     r8d, 0C3B4h
0x10042a4f0  mov     edx, ebx
0x10042a4f2  mov     ecx, 0Ah
0x10042a4f7  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10042a4fc  nop
0x10042a4fd  lea     rcx, [rsp+350h+var_2E0]; this
0x10042a502  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x10042a507  nop
0x10042a508  jmp     loc_10042A3D3
0x10042a50d  xor     esi, esi
0x10042a50f  test    r15d, r15d
0x10042a512  lea     r15, ?ghSspiCred@@3U_SecHandle@@A; _SecHandle ghSspiCred
0x10042a519  jz      loc_10042A5D8
0x10042a51f  lea     rax, [rbp+250h+var_270]
0x10042a523  mov     [rsp+350h+var_310], rax
0x10042a528  mov     [rsp+350h+var_318], r15
0x10042a52d  mov     [rsp+350h+var_320], rsi
0x10042a532  mov     [rsp+350h+var_328], rsi
0x10042a537  mov     [rsp+350h+var_330], rsi
0x10042a53c  xor     r9d, r9d
0x10042a53f  lea     r8d, [rsi+3]
0x10042a543  lea     rdx, ?g_szSSP@@3PA_WA; wchar_t near * g_szSSP
0x10042a54a  xor     ecx, ecx
0x10042a54c  mov     rax, cs:?g_pFuncs@@3PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * g_pFuncs
0x10042a553  call    qword ptr [rax+18h]
0x10042a556  mov     ebx, eax
0x10042a558  test    eax, eax
0x10042a55a  jz      short loc_10042A5D8
0x10042a55c  lea     edi, [rsi+1]
0x10042a55f  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10042a566  jz      short loc_10042A59D
0x10042a568  mov     dword ptr [rsp+350h+var_320], eax
0x10042a56c  mov     dword ptr [rsp+350h+var_328], esi
0x10042a570  mov     dword ptr [rsp+350h+var_330], 0Ah
0x10042a578  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10042a57f  mov     r8d, 1ADh; int
0x10042a585  lea     rdx, aSnisecinitpack_0; "SNISecInitPackageEx"
0x10042a58c  lea     r14, aSqlCommonDkSni_20; "sql\\common\\dk\\sni\\src\\sni_sspi.cpp"
0x10042a593  mov     rcx, r14; char *
0x10042a596  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10042a59b  jmp     short loc_10042A5A4
0x10042a59d  lea     r14, aSqlCommonDkSni_20; "sql\\common\\dk\\sni\\src\\sni_sspi.cpp"
0x10042a5a4  mov     r8d, 0C3B4h
0x10042a5aa  mov     edx, ebx
0x10042a5ac  mov     ecx, 0Ah
0x10042a5b1  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10042a5b6  nop
0x10042a5b7  lea     rcx, [rsp+350h+var_2E0]; this
0x10042a5bc  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x10042a5c1  nop
0x10042a5c2  mov     ecx, [rsp+350h+var_2F0]
  ... truncated ...
```
