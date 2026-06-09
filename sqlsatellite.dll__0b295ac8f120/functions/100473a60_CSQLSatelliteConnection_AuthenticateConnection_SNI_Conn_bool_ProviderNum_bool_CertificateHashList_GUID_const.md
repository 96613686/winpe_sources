# CSQLSatelliteConnection::AuthenticateConnection(SNI_Conn *,bool,ProviderNum,bool,CertificateHashList *,_GUID const *)

- ea: `0x100473a60`
- end: `0x1004740da`
- name: `?AuthenticateConnection@CSQLSatelliteConnection@@QEAAKPEAVSNI_Conn@@_NW4ProviderNum@@1PEAVCertificateHashList@@PEBU_GUID@@@Z`
- size: `1658`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x100473340`

## callees

- `0x100405270`
- `0x100405390`
- `0x10040bbb0`
- `0x10041aa00`
- `0x10041abb0`
- `0x100427e60`
- `0x100428450`
- `0x100428e20`
- `0x10042c270`
- `0x10042c430`
- `0x100473a60`
- `0x1004740e0`
- `0x100480d40`

## import_xrefs

- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x100473b41`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x100473b41`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x100473e5f`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x100473e5f`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100473dba`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100473dba`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100473f3e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100473f8e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100473f3e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100473f8e`
- `sqldk!SystemThread_TlsIndex` at `0x100473d79`
- `sqldk!SystemThread_TlsIndex` at `0x100473dcf`
- `sqldk!SystemThread_TlsOffset` at `0x100473d82`
- `sqldk!SystemThread_TlsOffset` at `0x100473dd8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100473d9d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100473df3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100473d9d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100473df3`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x100473b3a`

## string_xrefs

- `0x100473ba1`: `sql\common\dk\sni\src\sni.cpp`
- `0x100473f2e`: `Sql\Ntdbms\extensibility\common\src\communisatellite.cpp`
- `0x100473f7e`: `Sql\Ntdbms\extensibility\common\src\communisatellite.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CSQLSatelliteConnection::AuthenticateConnection(
        CSQLSatelliteConnection *a1,
        CSQLSatelliteAuthorizeConnection *a2,
        unsigned __int8 a3,
        int a4,
        char a5,
        struct CertificateHashList *a6,
        __int64 a7)
{
  unsigned __int8 v8; // bl
  char v11; // r13
  void *v12; // rax
  int v13; // eax
  int v14; // r12d
  unsigned int v15; // esi
  const wchar_t *v16; // r9
  unsigned __int8 v17; // r12
  bool *v18; // r9
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rbx
  __int64 v23; // rdx
  int v24; // eax
  bool v25; // bl
  __int64 result; // rax
  int v27; // [rsp+20h] [rbp-E0h]
  char v28; // [rsp+40h] [rbp-C0h]
  _QWORD v29[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v30; // [rsp+60h] [rbp-A0h]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int64 v32; // [rsp+70h] [rbp-90h]
  int v33; // [rsp+78h] [rbp-88h]
  int v34; // [rsp+7Ch] [rbp-84h]
  __int128 v35; // [rsp+80h] [rbp-80h]
  __int128 v36; // [rsp+90h] [rbp-70h]
  __int128 v37; // [rsp+A0h] [rbp-60h]
  int v38; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v39; // [rsp+B8h] [rbp-48h]
  int v40; // [rsp+C0h] [rbp-40h] BYREF
  int v41; // [rsp+C4h] [rbp-3Ch]
  __int64 v42; // [rsp+C8h] [rbp-38h]
  int v43; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v44; // [rsp+D8h] [rbp-28h]
  __int64 v45; // [rsp+E0h] [rbp-20h]
  __int64 v46; // [rsp+E8h] [rbp-18h]
  __int64 v47; // [rsp+F0h] [rbp-10h]
  bool v48; // [rsp+100h] [rbp+0h]
  __int64 v49; // [rsp+110h] [rbp+10h]
  const char *v50; // [rsp+118h] [rbp+18h]
  const char *v51; // [rsp+120h] [rbp+20h]
  int v52; // [rsp+128h] [rbp+28h]
  char v53[8]; // [rsp+130h] [rbp+30h] BYREF
  int v54; // [rsp+138h] [rbp+38h]
  int v55; // [rsp+140h] [rbp+40h]
  CSQLSatelliteConnection ***v56; // [rsp+148h] [rbp+48h]
  char *v57; // [rsp+150h] [rbp+50h]
  __int64 v58; // [rsp+158h] [rbp+58h]
  CSQLSatelliteConnection **v59; // [rsp+160h] [rbp+60h] BYREF
  int v60; // [rsp+168h] [rbp+68h]
  int v61; // [rsp+16Ch] [rbp+6Ch]
  __int64 v62; // [rsp+170h] [rbp+70h]
  int v63; // [rsp+178h] [rbp+78h]
  int v64; // [rsp+17Ch] [rbp+7Ch]
  char v65; // [rsp+180h] [rbp+80h] BYREF
  __int64 v66; // [rsp+380h] [rbp+280h]
  __int64 v67; // [rsp+388h] [rbp+288h]
  CSQLSatelliteConnection *v68; // [rsp+390h] [rbp+290h] BYREF
  unsigned int v69; // [rsp+398h] [rbp+298h]
  int v70; // [rsp+39Ch] [rbp+29Ch]
  int v71; // [rsp+3A0h] [rbp+2A0h]
  int v72; // [rsp+3A4h] [rbp+2A4h]
  int v73; // [rsp+3A8h] [rbp+2A8h]
  char v74[8]; // [rsp+3C0h] [rbp+2C0h] BYREF
  int v75; // [rsp+3C8h] [rbp+2C8h]
  int v76; // [rsp+3D0h] [rbp+2D0h]
  CSQLSatelliteConnection ***v77; // [rsp+3D8h] [rbp+2D8h]
  char *v78; // [rsp+3E0h] [rbp+2E0h]
  __int64 v79; // [rsp+3E8h] [rbp+2E8h]
  CSQLSatelliteConnection **v80; // [rsp+3F0h] [rbp+2F0h] BYREF
  int v81; // [rsp+3F8h] [rbp+2F8h]
  int v82; // [rsp+3FCh] [rbp+2FCh]
  __int64 v83; // [rsp+400h] [rbp+300h]
  int v84; // [rsp+408h] [rbp+308h]
  int v85; // [rsp+40Ch] [rbp+30Ch]
  char v86; // [rsp+410h] [rbp+310h] BYREF
  __int64 v87; // [rsp+610h] [rbp+510h]
  __int64 v88; // [rsp+618h] [rbp+518h]
  CSQLSatelliteConnection *v89; // [rsp+620h] [rbp+520h] BYREF
  unsigned int v90; // [rsp+628h] [rbp+528h]
  int v91; // [rsp+62Ch] [rbp+52Ch]
  BOOL v92; // [rsp+630h] [rbp+530h]
  int v93; // [rsp+634h] [rbp+534h]
  bool v95; // [rsp+698h] [rbp+598h] BYREF

  v49 = -2;
  v8 = a3;
  v11 = a5;
  v28 = 0;
  v95 = 1;
  if ( !a3 )
    v11 = a5 ^ 1;
  v12 = &CSQLSatelliteConnection::sm_authSSLParams;
  if ( a4 == 3 )
    v12 = &CSQLSatelliteConnection::sm_authSSPIParams;
  v29[0] = v12;
  v13 = 0;
  v29[1] = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 5;
  v34 = 77;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  if ( a4 == 6 )
  {
    v14 = 256;
    if ( v11 )
    {
      *((_QWORD *)&v35 + 1) = (char *)a1 + 402;
      LODWORD(v36) = 0;
      v15 = -2146762476;
      if ( a1 != (CSQLSatelliteConnection *)-402LL )
        v15 = 0;
      if ( OsInfo::IsLinux(SOS_OS_OsInfo) )
        v14 = 264;
      HIDWORD(v32) = v14;
      if ( a1 == (CSQLSatelliteConnection *)-402LL )
        return v15;
      v8 = a3;
    }
    else
    {
      HIDWORD(v32) = 1280;
    }
  }
  else
  {
    if ( a4 == 3 )
      v13 = 64;
    HIDWORD(v32) = v13;
  }
  v15 = SNISetInfo(a2, 2, a1);
  if ( v15 )
    return v15;
  _InterlockedIncrement((volatile signed __int32 *)a1 + 8);
  v50 = "sql\\common\\dk\\sni\\src\\sni.cpp";
  v51 = "SNIAddProviderEx";
  v52 = 8402;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\sni.cpp",
      "SNIAddProviderEx",
      8402,
      L"API|SNI%u#{SNI_Conn}, pConn: %p{SNI_Conn*}, ProvNum: %d{ProviderNum}, pInfo: %p\n",
      *((_DWORD *)a2 + 19),
      a2,
      a4,
      v29);
  v15 = AddProvider((__int64)a2, a4, v29);
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNIAddProviderEx", 8402, v16);
  if ( v15 != 997 && v15 )
  {
    *((_DWORD *)a1 + 239) = v33;
    *((_DWORD *)a1 + 240) = v34;
    goto LABEL_25;
  }
  v28 = 1;
  if ( v15 != 997 )
  {
LABEL_25:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1 + 8, 0xFFFFFFFF) == 1 )
    {
      if ( *((_QWORD *)a1 + 2) )
        TList<SqlSatelliteConnectionList,CSQLSatelliteConnection,8,TListSLock>::RemoveElem(*((_QWORD *)a1 + 3), a1);
      (*(void (__fastcall **)(CSQLSatelliteConnection *))(*(_QWORD *)a1 + 24LL))(a1);
    }
    goto LABEL_29;
  }
  LOBYTE(v27) = 1;
  v24 = WaitableBase::Wait((char *)a1 + 264, 30000, (char *)a1 + 312, 0, v27);
  if ( v24 )
  {
    if ( v24 == 2 )
    {
      v15 = -2147467260;
    }
    else
    {
      v15 = 258;
      if ( v24 != 258 )
      {
        v15 = 14;
        if ( v24 != -1073741824 )
          v15 = 31;
      }
    }
  }
  else
  {
    v15 = *((_DWORD *)a1 + 238);
  }
LABEL_29:
  v17 = v8 + 1;
  if ( (g_XeSQLSatellitePkg_enabledBitmap & 0x8000) != 0 )
  {
    v54 = 0x20000;
    v55 = 0;
    v56 = &v59;
    v57 = &v65;
    v66 = 0;
    v58 = 0;
    v67 = 0;
    v59 = &v68;
    v60 = 36;
    v61 = 1;
    v68 = a1;
    v69 = v15;
    v70 = v17;
    v71 = *((_DWORD *)a1 + 239);
    v72 = *((_DWORD *)a1 + 240);
    v73 = a4;
    v62 = a7;
    v63 = 16;
    v64 = 6;
    XeSQLSatellitePkg::satellite_authentication_completion::Publish((XeSQLSatellitePkg::satellite_authentication_completion *)v53);
  }
  if ( v15 )
  {
    v25 = v95;
    goto LABEL_68;
  }
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v38, 1);
  v43 = 536871406;
  v44 = 0;
  v46 = 0;
  v45 = 0;
  v47 = 0;
  v48 = 0;
  v19 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v20 = *(_QWORD *)(v19 + 256);
  if ( !v20 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v20 = *(_QWORD *)(v19 + 256);
  }
  v21 = *(_QWORD *)(v20 + 600);
  if ( v21 )
    v48 = (unsigned int)SOS_Task::PushWait(v21, &v43) == 0;
  v22 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v23 = *(_QWORD *)(v22 + 256);
  if ( !v23 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v23 = *(_QWORD *)(v22 + 256);
  }
  v42 = v23;
  v41 = (*(_DWORD *)(v23 + 800) >> 11) & 1;
  if ( v41 || (*(_BYTE *)(v23 + 800) & 4) == 0 )
  {
    v40 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v23 + 608) + 8LL))(*(_QWORD *)(v23 + 608));
  }
  else
  {
    v40 = 0;
  }
  v15 = 0;
  if ( !a3 )
  {
    if ( v11 )
      goto LABEL_64;
    if ( a4 != 6 )
    {
      if ( a4 == 3 )
        v15 = CSQLSatelliteAuthorizeConnection::AuthorizeConnection(a2, 0, (bool)&v95, v18);
      else
        utassert_fail(
          1u,
          "false",
          "Sql\\Ntdbms\\extensibility\\common\\src\\communisatellite.cpp",
          4561,
          "Invalid provider type specified\n");
      goto LABEL_64;
    }
LABEL_57:
    v15 = CSQLSatelliteConnection::AuthorizeSSLConnection(a1, a2, a6, &v95);
    goto LABEL_64;
  }
  if ( a4 == 3 )
  {
    if ( v11 )
      v15 = CSQLSatelliteAuthorizeConnection::AuthorizeConnection(a2, (struct SNI_Conn *)a3, (bool)&v95, v18);
    goto LABEL_64;
  }
  if ( a4 != 6 )
  {
    utassert_fail(
      1u,
      "false",
      "Sql\\Ntdbms\\extensibility\\common\\src\\communisatellite.cpp",
      4539,
      "Invalid provider type specified\n");
    goto LABEL_64;
  }
  if ( !v11 )
    goto LABEL_57;
LABEL_64:
  v25 = v95;
  if ( (g_XeSQLSatellitePkg_enabledBitmap & 0x10000) != 0 )
  {
    v75 = 0x20000;
    v76 = 0;
    v77 = &v80;
    v78 = &v86;
    v87 = 0;
    v79 = 0;
    v88 = 0;
    v80 = &v89;
    v81 = 32;
    v82 = 1;
    v89 = a1;
    v90 = v15;
    v91 = v17;
    v92 = v95;
    v93 = a4;
    v83 = a7;
    v84 = 16;
    v85 = 5;
    XeSQLSatellitePkg::satellite_authorization_completion::Publish((XeSQLSatellitePkg::satellite_authorization_completion *)v74);
  }
  AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v40);
  *(_DWORD *)(v39 + 616) &= ~v38;
LABEL_68:
  if ( !v28 )
    goto LABEL_71;
  if ( v15 )
    return v15;
  v15 = SNIRemoveProvider(a2);
LABEL_71:
  if ( v15 )
    return v15;
  result = 2153979936LL;
  if ( v25 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x100473a60  mov     [rsp-8+arg_10], r8b
0x100473a65  push    rbp
0x100473a66  push    rsi
0x100473a67  push    rdi
0x100473a68  push    r12
0x100473a6a  push    r13
0x100473a6c  push    r14
0x100473a6e  push    r15
0x100473a70  lea     rbp, [rsp-540h]
0x100473a78  sub     rsp, 640h
0x100473a7f  mov     [rbp+570h+var_560], 0FFFFFFFFFFFFFFFEh
0x100473a87  mov     [rsp+670h+arg_0], rbx
0x100473a8f  mov     r14d, r9d
0x100473a92  movzx   ebx, r8b
0x100473a96  mov     r15, rdx
0x100473a99  mov     rdi, rcx
0x100473a9c  movzx   r13d, [rbp+570h+arg_20]
0x100473aa4  mov     [rsp+670h+var_630], 0
0x100473aa9  mov     [rbp+570h+arg_18], 1
0x100473ab0  movzx   eax, r13b
0x100473ab4  xor     al, 1
0x100473ab6  movzx   eax, al
0x100473ab9  test    r8b, r8b
0x100473abc  cmovz   r13d, eax
0x100473ac0  lea     rcx, ?sm_authSSPIParams@CSQLSatelliteConnection@@2USNIAuthParams@@A; SNIAuthParams CSQLSatelliteConnection::sm_authSSPIParams
0x100473ac7  lea     rax, ?sm_authSSLParams@CSQLSatelliteConnection@@2USNIAuthParams@@A; SNIAuthParams CSQLSatelliteConnection::sm_authSSLParams
0x100473ace  cmp     r9d, 3
0x100473ad2  cmovz   rax, rcx
0x100473ad6  mov     [rsp+670h+var_620], rax
0x100473adb  xor     eax, eax
0x100473add  mov     [rsp+670h+var_618], rax
0x100473ae2  mov     [rsp+670h+var_610], eax
0x100473ae6  mov     [rsp+670h+var_608], rax
0x100473aeb  mov     [rsp+670h+var_600], rax
0x100473af0  mov     ecx, 5
0x100473af5  mov     [rsp+670h+var_5F8], ecx
0x100473af9  mov     [rsp+670h+var_5F4], 4Dh ; 'M'
0x100473b01  xorps   xmm0, xmm0
0x100473b04  movups  [rbp+570h+var_5F0], xmm0
0x100473b08  movups  [rbp+570h+var_5E0], xmm0
0x100473b0c  movups  [rbp+570h+var_5D0], xmm0
0x100473b10  cmp     r9d, 6
0x100473b14  jnz     short loc_100473B73
0x100473b16  mov     r12d, 100h
0x100473b1c  test    r13b, r13b
0x100473b1f  jz      short loc_100473B69
0x100473b21  lea     rbx, [rdi+192h]
0x100473b28  mov     qword ptr [rbp+570h+var_5F0+8], rbx
0x100473b2c  mov     dword ptr [rbp+570h+var_5E0], eax
0x100473b2f  mov     esi, 800B0114h
0x100473b34  test    rbx, rbx
0x100473b37  cmovnz  esi, eax
0x100473b3a  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x100473b41  call    cs:__imp_?IsLinux@OsInfo@@QEBA?B_NXZ; OsInfo::IsLinux(void)
0x100473b47  mov     ecx, 108h
0x100473b4c  test    al, al
0x100473b4e  cmovnz  r12d, ecx
0x100473b52  mov     dword ptr [rsp+670h+var_600+4], r12d
0x100473b57  test    rbx, rbx
0x100473b5a  jz      loc_1004740BD
0x100473b60  movzx   ebx, [rbp+570h+arg_10]
0x100473b67  jmp     short loc_100473B83
0x100473b69  mov     dword ptr [rsp+670h+var_600+4], 500h
0x100473b71  jmp     short loc_100473B83
0x100473b73  mov     ecx, 40h ; '@'
0x100473b78  cmp     r14d, 3
0x100473b7c  cmovz   eax, ecx
0x100473b7f  mov     dword ptr [rsp+670h+var_600+4], eax
0x100473b83  mov     r8, rdi
0x100473b86  mov     edx, 2
0x100473b8b  mov     rcx, r15
0x100473b8e  call    SNISetInfo
0x100473b93  mov     esi, eax
0x100473b95  test    eax, eax
0x100473b97  jnz     loc_1004740BD
0x100473b9d  lock inc dword ptr [rdi+20h]
0x100473ba1  lea     r12, aSqlCommonDkSni_13; "sql\\common\\dk\\sni\\src\\sni.cpp"
0x100473ba8  mov     [rbp+570h+var_558], r12
0x100473bac  lea     rcx, aSniaddprovider; "SNIAddProviderEx"
0x100473bb3  mov     [rbp+570h+var_550], rcx
0x100473bb7  mov     [rbp+570h+var_548], 20D2h
0x100473bbe  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100473bc5  jz      short loc_100473BFB
0x100473bc7  lea     rax, [rsp+670h+var_620]
0x100473bcc  mov     [rsp+670h+var_638], rax
0x100473bd1  mov     [rsp+670h+var_640], r14d
0x100473bd6  mov     [rsp+670h+var_648], r15
0x100473bdb  mov     eax, [r15+4Ch]
0x100473bdf  mov     dword ptr [rsp+670h+var_650], eax
0x100473be3  lea     r9, aApiSniUSniConn_0; "API|SNI%u#{SNI_Conn}, pConn: %p{SNI_Con"...
0x100473bea  mov     r8d, 20D2h; int
0x100473bf0  mov     rdx, rcx; char *
0x100473bf3  mov     rcx, r12; char *
0x100473bf6  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100473bfb  lea     r8, [rsp+670h+var_620]
0x100473c00  mov     edx, r14d
0x100473c03  mov     rcx, r15
0x100473c06  call    ?AddProvider@@YAKPEAVSNI_Conn@@W4ProviderNum@@PEAX@Z; AddProvider(SNI_Conn *,ProviderNum,void *)
0x100473c0b  mov     esi, eax
0x100473c0d  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100473c14  jz      short loc_100473C2B
0x100473c16  mov     r8d, 20D2h; int
0x100473c1c  lea     rdx, aSniaddprovider; "SNIAddProviderEx"
0x100473c23  mov     rcx, r12; char *
0x100473c26  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100473c2b  cmp     esi, 3E5h
0x100473c31  jz      loc_100473E33
0x100473c37  test    esi, esi
0x100473c39  jz      loc_100473E33
0x100473c3f  mov     eax, [rsp+670h+var_5F8]
0x100473c43  mov     [rdi+3BCh], eax
0x100473c49  mov     eax, [rsp+670h+var_5F4]
0x100473c4d  mov     [rdi+3C0h], eax
0x100473c53  mov     eax, 0FFFFFFFFh
0x100473c58  lock xadd [rdi+20h], eax
0x100473c5d  cmp     eax, 1
0x100473c60  jnz     short loc_100473C7E
0x100473c62  cmp     qword ptr [rdi+10h], 0
0x100473c67  jz      short loc_100473C75
0x100473c69  mov     rdx, rdi
0x100473c6c  mov     rcx, [rdi+18h]
0x100473c70  call    ?RemoveElem@?$TList@VSqlSatelliteConnectionList@@VCSQLSatelliteConnection@@$07UTListSLock@@@@QEAAXPEAVCSQLSatelliteConnection@@@Z; TList<SqlSatelliteConnectionList,CSQLSatelliteConnection,8,TListSLock>::RemoveElem(CSQLSatelliteConnection *)
0x100473c75  mov     rax, [rdi]
0x100473c78  mov     rcx, rdi
0x100473c7b  call    qword ptr [rax+18h]
0x100473c7e  lea     r12d, [rbx+1]
0x100473c82  mov     ecx, 1
0x100473c87  xor     ebx, ebx
0x100473c89  test    cs:?g_XeSQLSatellitePkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$0DM@@@@@A, 8000h; XBitmap<StaticStorage<60>> g_XeSQLSatellitePkg_enabledBitmap
0x100473c93  jz      loc_100473D38
0x100473c99  mov     [rbp+570h+var_538], 20000h
0x100473ca0  mov     [rbp+570h+var_530], ebx
0x100473ca3  lea     rax, [rbp+570h+var_510]
0x100473ca7  mov     [rbp+570h+var_528], rax
0x100473cab  lea     rax, [rbp+570h+var_4F0]
0x100473cb2  mov     [rbp+570h+var_520], rax
0x100473cb6  mov     [rbp+570h+var_2F0], rbx
0x100473cbd  mov     [rbp+570h+var_518], rbx
0x100473cc1  mov     [rbp+570h+var_2E8], rbx
0x100473cc8  lea     rax, [rbp+570h+var_2E0]
0x100473ccf  mov     [rbp+570h+var_510], rax
0x100473cd3  mov     [rbp+570h+var_508], 24h ; '$'
0x100473cda  mov     [rbp+570h+var_504], ecx
0x100473cdd  mov     [rbp+570h+var_2E0], rdi
0x100473ce4  mov     [rbp+570h+var_2D8], esi
0x100473cea  movzx   eax, r12b
0x100473cee  mov     [rbp+570h+var_2D4], eax
0x100473cf4  mov     eax, [rdi+3BCh]
0x100473cfa  mov     [rbp+570h+var_2D0], eax
0x100473d00  mov     eax, [rdi+3C0h]
0x100473d06  mov     [rbp+570h+var_2CC], eax
0x100473d0c  mov     [rbp+570h+var_2C8], r14d
0x100473d13  mov     rax, [rbp+570h+arg_30]
0x100473d1a  mov     [rbp+570h+var_500], rax
0x100473d1e  mov     [rbp+570h+var_4F8], 10h
0x100473d25  mov     [rbp+570h+var_4F4], 6
0x100473d2c  lea     rcx, [rbp+570h+var_540]; this
0x100473d30  call    ?Publish@satellite_authentication_completion@XeSQLSatellitePkg@@QEAAXXZ; XeSQLSatellitePkg::satellite_authentication_completion::Publish(void)
0x100473d35  lea     ecx, [rbx+1]
0x100473d38  test    esi, esi
0x100473d3a  jnz     loc_100474089
0x100473d40  mov     edx, ecx
0x100473d42  lea     rcx, [rbp+570h+var_5C0]
0x100473d46  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x100473d4b  nop
0x100473d4c  lea     rax, [rbp+570h+var_5B0]
0x100473d50  mov     [rsp+670h+var_628], rax
0x100473d55  mov     [rbp+570h+var_5A0], 200001EEh
0x100473d5c  mov     [rbp+570h+var_598], rbx
0x100473d60  mov     [rbp+570h+var_588], rbx
0x100473d64  mov     [rbp+570h+var_590], rbx
0x100473d68  mov     [rbp+570h+var_580], rbx
0x100473d6c  mov     [rbp+570h+var_570], sil
0x100473d70  mov     rdx, gs:58h
0x100473d79  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100473d80  mov     ecx, [rax]
0x100473d82  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100473d89  mov     ebx, [rax]
0x100473d8b  add     rbx, [rdx+rcx*8]
0x100473d8f  mov     rax, [rbx+100h]
0x100473d96  test    rax, rax
0x100473d99  jnz     short loc_100473DAA
0x100473d9b  xor     ecx, ecx
0x100473d9d  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100473da3  mov     rax, [rbx+100h]
0x100473daa  mov     rcx, [rax+258h]
0x100473db1  test    rcx, rcx
0x100473db4  jz      short loc_100473DC6
0x100473db6  lea     rdx, [rbp+570h+var_5A0]
0x100473dba  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x100473dc0  test    eax, eax
0x100473dc2  setz    [rbp+570h+var_570]
0x100473dc6  mov     rdx, gs:58h
0x100473dcf  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100473dd6  mov     ecx, [rax]
0x100473dd8  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100473ddf  mov     ebx, [rax]
0x100473de1  add     rbx, [rdx+rcx*8]
0x100473de5  mov     rdx, [rbx+100h]
0x100473dec  test    rdx, rdx
0x100473def  jnz     short loc_100473E00
0x100473df1  xor     ecx, ecx
0x100473df3  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100473df9  mov     rdx, [rbx+100h]
0x100473e00  mov     [rbp+570h+var_5A8], rdx
0x100473e04  mov     eax, [rdx+320h]
0x100473e0a  shr     eax, 0Bh
0x100473e0d  and     eax, 1
0x100473e10  mov     [rbp+570h+var_5AC], eax
0x100473e13  jnz     loc_100473EA7
0x100473e19  test    byte ptr [rdx+320h], 4
0x100473e20  jz      loc_100473EA7
0x100473e26  xor     ecx, ecx
0x100473e28  mov     [rbp+570h+var_5B0], ecx
0x100473e2b  lea     ebx, [rcx+1]
0x100473e2e  jmp     loc_100473EBE
0x100473e33  mov     [rsp+670h+var_630], 1
0x100473e38  cmp     esi, 3E5h
0x100473e3e  jnz     loc_100473C53
0x100473e44  lea     r8, [rdi+138h]
0x100473e4b  lea     rcx, [rdi+108h]
0x100473e52  mov     byte ptr [rsp+670h+var_650], 1
0x100473e57  xor     r9d, r9d
0x100473e5a  mov     edx, 7530h
0x100473e5f  call    cs:__imp_?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z; WaitableBase::Wait(ulong,SOS_WaitInfo const *,SOS_SYNC_WAIT_OPTIONS,bool)
0x100473e65  test    eax, eax
0x100473e67  jnz     short loc_100473E74
0x100473e69  mov     esi, [rdi+3B8h]
0x100473e6f  jmp     loc_100473C7E
0x100473e74  cmp     eax, 2
0x100473e77  jz      short loc_100473E9D
0x100473e79  mov     esi, 102h
0x100473e7e  cmp     eax, esi
0x100473e80  jz      loc_100473C7E
0x100473e86  mov     esi, 0Eh
0x100473e8b  mov     ecx, 1Fh
0x100473e90  cmp     eax, 0C0000000h
0x100473e95  cmovnz  esi, ecx
0x100473e98  jmp     loc_100473C7E
0x100473e9d  mov     esi, 80004004h
0x100473ea2  jmp     loc_100473C7E
0x100473ea7  mov     ebx, 1
0x100473eac  mov     [rbp+570h+var_5B0], ebx
0x100473eaf  mov     rcx, [rdx+260h]
0x100473eb6  mov     rax, [rcx]
0x100473eb9  call    qword ptr [rax+8]
0x100473ebc  xor     ecx, ecx
0x100473ebe  mov     esi, ecx
0x100473ec0  movzx   edx, [rbp+570h+arg_10]; struct SNI_Conn *
0x100473ec7  test    dl, dl
0x100473ec9  jz      short loc_100473F46
0x100473ecb  cmp     r14d, 3
0x100473ecf  jnz     short loc_100473EF0
0x100473ed1  test    r13b, r13b
0x100473ed4  jz      loc_100473F96
0x100473eda  lea     r8, [rbp+570h+arg_18]; bool
0x100473ee1  mov     rcx, r15; this
0x100473ee4  call    ?AuthorizeConnection@CSQLSatelliteAuthorizeConnection@@YAKPEAVSNI_Conn@@_NPEA_N@Z; CSQLSatelliteAuthorizeConnection::AuthorizeConnection(SNI_Conn *,bool,bool *)
0x100473ee9  mov     esi, eax
0x100473eeb  jmp     loc_100473F94
0x100473ef0  cmp     r14d, 6
0x100473ef4  jnz     short loc_100473F1C
0x100473ef6  test    r13b, r13b
0x100473ef9  jnz     loc_100473F96
0x100473eff  lea     r9, [rbp+570h+arg_18]; bool *
0x100473f06  mov     r8, [rbp+570h+arg_28]; struct CertificateHashList *
0x100473f0d  mov     rdx, r15; struct SNI_Conn *
0x100473f10  mov     rcx, rdi; this
0x100473f13  call    ?AuthorizeSSLConnection@CSQLSatelliteConnection@@QEAAKPEAVSNI_Conn@@PEAVCertificateHashList@@PEA_N@Z; CSQLSatelliteConnection::AuthorizeSSLConnection(SNI_Conn *,CertificateHashList *,bool *)
0x100473f18  mov     esi, eax
0x100473f1a  jmp     short loc_100473F94
0x100473f1c  lea     rax, aInvalidProvide; "Invalid provider type specified\n"
0x100473f23  mov     [rsp+670h+var_650], rax
0x100473f28  mov     r9d, 11BBh
0x100473f2e  lea     r8, aSqlNtdbmsExten_14; "Sql\\Ntdbms\\extensibility\\common\\src"...
0x100473f35  lea     rdx, aFalse_0; "false"
0x100473f3c  mov     ecx, ebx
0x100473f3e  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100473f44  jmp     short loc_100473F94
0x100473f46  test    r13b, r13b
0x100473f49  jnz     short loc_100473F96
0x100473f4b  cmp     r14d, 6
0x100473f4f  jz      short loc_100473EFF
0x100473f51  cmp     r14d, 3
0x100473f55  jnz     short loc_100473F6C
0x100473f57  lea     r8, [rbp+570h+arg_18]; bool
0x100473f5e  xor     edx, edx; struct SNI_Conn *
0x100473f60  mov     rcx, r15; this
0x100473f63  call    ?AuthorizeConnection@CSQLSatelliteAuthorizeConnection@@YAKPEAVSNI_Conn@@_NPEA_N@Z; CSQLSatelliteAuthorizeConnection::AuthorizeConnection(SNI_Conn *,bool,bool *)
0x100473f68  mov     esi, eax
0x100473f6a  jmp     short loc_100473F94
0x100473f6c  lea     rax, aInvalidProvide; "Invalid provider type specified\n"
0x100473f73  mov     [rsp+670h+var_650], rax
0x100473f78  mov     r9d, 11D1h
0x100473f7e  lea     r8, aSqlNtdbmsExten_14; "Sql\\Ntdbms\\extensibility\\common\\src"...
0x100473f85  lea     rdx, aFalse_0; "false"
0x100473f8c  mov     ecx, ebx
0x100473f8e  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100473f94  xor     ecx, ecx
0x100473f96  movzx   ebx, [rbp+570h+arg_18]
  ... truncated ...
```
