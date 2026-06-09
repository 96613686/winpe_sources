# CVssSnapshotSetObject::GetComClientDetails(ulong,ushort *,ushort *)

- ea: `0x1400393a4`
- end: `0x140039b07`
- name: `?GetComClientDetails@CVssSnapshotSetObject@@AEAAJKPEAG0@Z`
- size: `1891`
- prototype: `int(CVssSnapshotSetObject *__hidden this, unsigned int, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140038a30`
- `0x1400a4864`
- `0x1400a53e4`
- `0x1400a5d84`

## callees

- `0x14000e640`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013cb0`
- `0x140015e38`
- `0x140025b00`
- `0x1400393a4`
- `0x14003a8f0`
- `0x14003ade4`
- `0x140091560`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003964a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400398c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039980`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003964a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400398c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039980`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140039497`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140039497`
- `VssTrace!__imp_VssTraceMessage` at `0x1400395aa`
- `VssTrace!__imp_VssTraceMessage` at `0x1400395aa`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400394f3`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400394f3`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400394e4`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400394e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400395cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400395cf`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14003963c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14003963c`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x140039783`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x140039783`

## string_xrefs

- `0x1400393e7`: `CVssSnapshotSetObject::GetComClientDetails`
- `0x140039678`: `CVssSnapshotSetObject::GetComClientDetails`
- `0x1400397bf`: `CVssSnapshotSetObject::GetComClientDetails`
- `0x1400398f7`: `CVssSnapshotSetObject::GetComClientDetails`
- `0x1400399ae`: `CVssSnapshotSetObject::GetComClientDetails`
- `0x140039a5b`: `CVssSnapshotSetObject::GetComClientDetails`
- `0x140039ab5`: `Bad usage of ClientDetails. Failed or No call to FindComClientDetails`
- `0x1400396e5`: `Fail to convert client process token to sid string winerr %d HRESULT 0x%08lx`
- `0x140039964`: `Fail to write to destination buffers winerr %d HRESULT 0x%08lx`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVssSnapshotSetObject::GetComClientDetails(
        PSID **this,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  int v7; // eax
  __int64 v8; // rcx
  int v9; // ebx
  __int16 v10; // bx
  __int64 i; // rdi
  void *v12; // rcx
  BOOL v13; // eax
  signed int LastError; // eax
  signed int v15; // edi
  unsigned int v16; // esi
  unsigned int v17; // r14d
  signed int v18; // eax
  signed int v19; // edi
  unsigned int v20; // esi
  unsigned int v21; // r14d
  signed int v22; // eax
  signed int v23; // edi
  unsigned int v24; // esi
  unsigned int v25; // r14d
  signed int v26; // eax
  signed int v27; // edi
  unsigned int v28; // esi
  unsigned int v29; // r14d
  unsigned int v30; // ebx
  LPDWORD cchReferencedDomainName; // [rsp+20h] [rbp-338h]
  LPDWORD cchReferencedDomainNamea; // [rsp+20h] [rbp-338h]
  PSID_NAME_USE peUse; // [rsp+28h] [rbp-330h]
  PSID_NAME_USE peUsea; // [rsp+28h] [rbp-330h]
  DWORD cchName; // [rsp+50h] [rbp-308h] BYREF
  enum _SID_NAME_USE v37[6]; // [rsp+58h] [rbp-300h] BYREF
  unsigned __int64 v38; // [rsp+70h] [rbp-2E8h] BYREF
  unsigned int v39; // [rsp+78h] [rbp-2E0h]
  const unsigned __int16 *v40; // [rsp+80h] [rbp-2D8h]
  const unsigned __int16 *v41; // [rsp+88h] [rbp-2D0h]
  unsigned int v42; // [rsp+90h] [rbp-2C8h]
  unsigned int v43; // [rsp+94h] [rbp-2C4h]
  const unsigned __int16 *v44; // [rsp+98h] [rbp-2C0h]
  unsigned int v45; // [rsp+A0h] [rbp-2B8h]
  DWORD TickCount; // [rsp+A4h] [rbp-2B4h]
  int v47; // [rsp+A8h] [rbp-2B0h]
  __int128 v48; // [rsp+B0h] [rbp-2A8h]
  __int128 v49; // [rsp+C0h] [rbp-298h]
  __int64 v50; // [rsp+D0h] [rbp-288h]
  void **v51; // [rsp+E0h] [rbp-278h] BYREF
  LPWSTR StringSid; // [rsp+E8h] [rbp-270h] BYREF
  const unsigned __int16 *v53; // [rsp+F0h] [rbp-268h] BYREF
  const unsigned __int16 *v54; // [rsp+F8h] [rbp-260h]
  const unsigned __int16 *v55; // [rsp+100h] [rbp-258h]
  int v56; // [rsp+108h] [rbp-250h]
  int v57; // [rsp+10Ch] [rbp-24Ch]
  int v58; // [rsp+110h] [rbp-248h]
  _BYTE v59[120]; // [rsp+118h] [rbp-240h] BYREF
  int v60; // [rsp+190h] [rbp-1C8h]
  int v61; // [rsp+198h] [rbp-1C0h] BYREF
  _com_error *v62; // [rsp+1A0h] [rbp-1B8h] BYREF
  const std::exception *v63; // [rsp+1A8h] [rbp-1B0h] BYREF
  WCHAR Name[8]; // [rsp+1B0h] [rbp-1A8h] BYREF
  const unsigned __int16 *v65; // [rsp+1C0h] [rbp-198h] BYREF
  int v66; // [rsp+1C8h] [rbp-190h]
  int v67; // [rsp+1CCh] [rbp-18Ch]
  int v68; // [rsp+1D0h] [rbp-188h]
  LPVOID pv[15]; // [rsp+1D8h] [rbp-180h] BYREF
  int v70; // [rsp+250h] [rbp-108h]
  WCHAR ReferencedDomainName[8]; // [rsp+260h] [rbp-F8h] BYREF
  _BYTE v72[144]; // [rsp+270h] [rbp-E8h] BYREF

  *(_QWORD *)Name = L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx";
  *(_QWORD *)&Name[4] = L"CVssSnapshotSetObject::GetComClientDetails";
  v65 = L"CORSNPSC";
  v66 = 2393;
  v67 = 1;
  v68 = 255;
  v70 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  v39 = 0;
  v44 = L"CVssSnapshotSetObject::GetComClientDetails";
  v40 = L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx";
  v41 = L"CORSNPSC";
  v42 = 2393;
  v43 = 1;
  TickCount = GetTickCount();
  v47 = 255;
  v38 = 0xFFFFFFFF00000000uLL;
  v50 = 0;
  v48 = 0;
  v49 = 0;
  *(_QWORD *)v37 = 0;
  if ( (int)VssGetTracingContextPerThread(v37) < 0 )
  {
    v8 = v50;
  }
  else
  {
    v7 = VssSetTracingContextPerThread(&v38);
    v8 = v50;
    if ( v7 >= 0 )
      v8 = *(_QWORD *)v37;
    v50 = v8;
  }
  if ( v8 )
    v45 = *(_DWORD *)(v8 + 48) + 1;
  else
    v45 = 0;
  v9 = 160;
  if ( v47 != 255 )
    v9 = v47;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v38) )
    VssTraceMessage(v40, v41, v42, v45, v43, v44, L"ENTER", v9, 0);
  v10 = 15;
  if ( HIBYTE(v70) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v12 = pv[i];
      if ( v12 )
      {
        CoTaskMemFree(v12);
        pv[i] = 0;
      }
    }
  }
  if ( this[316] && *((_DWORD *)this + 634) )
  {
    StringSid = 0;
    v51 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
    CVssAutoGenericValue_Storage<unsigned short *,0,void * (*)(void *),&void * LocalFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close(&v51);
    v13 = ConvertSidToStringSidW(*this[316], &StringSid);
    try
    {
      if ( !v13 )
      {
        LastError = GetLastError();
        v15 = LastError;
        if ( LastError > 0 )
        {
          v16 = (unsigned __int16)LastError | 0x80070000;
          v17 = v16;
        }
        else
        {
          v16 = LastError;
          v17 = LastError;
        }
        v53 = L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx";
        v54 = L"CVssSnapshotSetObject::GetComClientDetails";
        v55 = L"CORSNPSC";
        v56 = 2414;
        v57 = 1;
        v58 = 255;
        v60 = 0x1000000;
        memset_0(v59, 0, sizeof(v59));
        do
          --v10;
        while ( v10 );
        LODWORD(peUse) = v17;
        LODWORD(cchReferencedDomainName) = v15;
        CVssFunctionTracer::Throw(
          &v38,
          &v53,
          v16,
          L"Fail to convert client process token to sid string winerr %d HRESULT 0x%08lx",
          cchReferencedDomainName,
          peUse);
      }
      cchName = 80;
      wcscpy(ReferencedDomainName, L"Unknown");
      memset_0(v72, 0, sizeof(v72));
      wcscpy(Name, L"Unknown");
      memset_0(&v65, 0, 0x90u);
      v37[0] = 0;
      if ( !LookupAccountSidLocalW(*this[316], Name, &cchName, ReferencedDomainName, &cchName, v37) )
      {
        v18 = GetLastError();
        v19 = v18;
        if ( v18 > 0 )
        {
          v20 = (unsigned __int16)v18 | 0x80070000;
          v21 = v20;
        }
        else
        {
          v20 = v18;
          v21 = v18;
        }
        v53 = L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx";
        v54 = L"CVssSnapshotSetObject::GetComClientDetails";
        v55 = L"CORSNPSC";
        v56 = 2424;
        v57 = 1;
        v58 = 255;
        v60 = 0x1000000;
        memset_0(v59, 0, sizeof(v59));
        do
          --v10;
        while ( v10 );
        LODWORD(peUsea) = v21;
        LODWORD(cchReferencedDomainNamea) = v19;
        CVssFunctionTracer::Throw(
          &v38,
          &v53,
          v20,
          L"Fail to find client process account winerr %d HRESULT 0x%08lx",
          cchReferencedDomainNamea,
          peUsea);
      }
      if ( StringCchCatW(ReferencedDomainName, 0x50u, L"\\") < 0 || StringCchCatW(ReferencedDomainName, 0x50u, Name) < 0 )
      {
        v26 = GetLastError();
        v27 = v26;
        if ( v26 > 0 )
        {
          v28 = (unsigned __int16)v26 | 0x80070000;
          v29 = v28;
        }
        else
        {
          v28 = v26;
          v29 = v26;
        }
        v53 = L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx";
        v54 = L"CVssSnapshotSetObject::GetComClientDetails";
        v55 = L"CORSNPSC";
        v56 = 2430;
        v57 = 1;
        v58 = 255;
        v60 = 0x1000000;
        memset_0(v59, 0, sizeof(v59));
        do
          --v10;
        while ( v10 );
        LODWORD(peUsea) = v29;
        LODWORD(cchReferencedDomainNamea) = v27;
        CVssFunctionTracer::Throw(
          &v38,
          &v53,
          v28,
          L"Fail to construct user account winerr %d HRESULT 0x%08lx",
          cchReferencedDomainNamea,
          peUsea);
      }
      if ( (int)StringCchCopyW(a3, 0x50u, StringSid) < 0 || (int)StringCchCopyW(a4, 0x50u, ReferencedDomainName) < 0 )
      {
        v22 = GetLastError();
        v23 = v22;
        if ( v22 > 0 )
        {
          v24 = (unsigned __int16)v22 | 0x80070000;
          v25 = v24;
        }
        else
        {
          v24 = v22;
          v25 = v22;
        }
        v53 = L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx";
        v54 = L"CVssSnapshotSetObject::GetComClientDetails";
        v55 = L"CORSNPSC";
        v56 = 2438;
        v57 = 1;
        v58 = 255;
        v60 = 0x1000000;
        memset_0(v59, 0, sizeof(v59));
        do
          --v10;
        while ( v10 );
        LODWORD(peUsea) = v25;
        LODWORD(cchReferencedDomainNamea) = v23;
        CVssFunctionTracer::Throw(
          &v38,
          &v53,
          v24,
          L"Fail to write to destination buffers winerr %d HRESULT 0x%08lx",
          cchReferencedDomainNamea,
          peUsea);
      }
      CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(&v51);
    }
    catch ( long v61 )
    {
      CVssFunctionTracer::HandleHresultException(
        (CVssFunctionTracer *)&v38,
        v61,
        L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx",
        L"CORSNPSC",
        L"CVssSnapshotSetObject::GetComClientDetails",
        0x989u,
        v43);
    }
    catch ( _com_error *v62 )
    {
      CVssFunctionTracer::HandleComException(
        (CVssFunctionTracer *)&v38,
        v62,
        L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx",
        L"CORSNPSC",
        L"CVssSnapshotSetObject::GetComClientDetails",
        0x989u,
        v43);
    }
    catch ( std::bad_alloc )
    {
      CVssFunctionTracer::HandleStdBadAllocException(
        (CVssFunctionTracer *)&v38,
        L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx",
        L"CORSNPSC",
        L"CVssSnapshotSetObject::GetComClientDetails",
        0x989u,
        v43);
    }
    catch ( const std::exception *v63 )
    {
      CVssFunctionTracer::HandleStdGenericException(
        (CVssFunctionTracer *)&v38,
        v63,
        L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx",
        L"CORSNPSC",
        L"CVssSnapshotSetObject::GetComClientDetails",
        0x989u,
        v43);
    }
    v30 = v39;
    CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v38);
    return v30;
  }
  else
  {
    v53 = L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx";
    v54 = L"CVssSnapshotSetObject::GetComClientDetails";
    v55 = L"CORSNPSC";
    v56 = 2399;
    v57 = 1;
    v58 = 255;
    v60 = 0x1000000;
    memset_0(v59, 0, sizeof(v59));
    CVssFunctionTracer::Trace(&v38, &v53, L"Bad usage of ClientDetails. Failed or No call to FindComClientDetails");
    CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v38);
    return 1;
  }
}

```

## disassembly

```asm
0x1400393a4  mov     r11, rsp
0x1400393a7  push    rbx
0x1400393a8  push    rsi
0x1400393a9  push    rdi
0x1400393aa  push    r12
0x1400393ac  push    r13
0x1400393ae  push    r14
0x1400393b0  push    r15
0x1400393b2  sub     rsp, 320h
0x1400393b9  movaps  xmmword ptr [r11-48h], xmm6
0x1400393be  mov     rax, cs:__security_cookie
0x1400393c5  xor     rax, rsp
0x1400393c8  mov     [rsp+358h+var_58], rax
0x1400393d0  mov     r15, r9
0x1400393d3  mov     r14, r8
0x1400393d6  mov     rsi, rcx
0x1400393d9  lea     rdi, aBaseStorVssMod; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x1400393e0  mov     [r11-1A8h], rdi
0x1400393e7  lea     rax, aCvsssnapshotse_0; "CVssSnapshotSetObject::GetComClientDeta"...
0x1400393ee  mov     [r11-1A0h], rax
0x1400393f5  lea     rax, aCorsnpsc; "CORSNPSC"
0x1400393fc  mov     [r11-198h], rax
0x140039403  mov     [rsp+358h+var_190], 959h
0x14003940e  mov     r13d, 1
0x140039414  mov     [r11-18Ch], r13d
0x14003941b  mov     [rsp+358h+var_188], 0FFh
0x140039426  xor     r12d, r12d
0x140039429  mov     [rsp+358h+var_108], 1000000h
0x140039434  xor     edx, edx; Val
0x140039436  lea     r8d, [r13+77h]; Size
0x14003943a  lea     rcx, [r11-180h]; void *
0x140039441  call    memset_0
0x140039446  mov     [rsp+358h+var_2E0], r12d
0x14003944b  mov     rax, qword ptr [rsp+358h+Name+8]
0x140039453  mov     [rsp+358h+var_2C0], rax
0x14003945b  mov     rax, qword ptr [rsp+358h+Name]
0x140039463  mov     [rsp+358h+var_2D8], rax
0x14003946b  mov     rax, [rsp+358h+var_198]
0x140039473  mov     [rsp+358h+var_2D0], rax
0x14003947b  mov     eax, [rsp+358h+var_190]
0x140039482  mov     [rsp+358h+var_2C8], eax
0x140039489  mov     eax, [rsp+358h+var_18C]
0x140039490  mov     [rsp+358h+var_2C4], eax
0x140039497  call    cs:__imp_GetTickCount
0x14003949d  mov     [rsp+358h+var_2B4], eax
0x1400394a4  mov     [rsp+358h+var_2E4], 0FFFFFFFFh
0x1400394ac  mov     eax, [rsp+358h+var_188]
0x1400394b3  mov     [rsp+358h+var_2B0], eax
0x1400394ba  mov     [rsp+358h+var_2E8], r12d
0x1400394bf  mov     [rsp+358h+var_288], r12
0x1400394c7  xorps   xmm0, xmm0
0x1400394ca  movups  [rsp+358h+var_2A8], xmm0
0x1400394d2  movups  [rsp+358h+var_298], xmm0
0x1400394da  mov     qword ptr [rsp+358h+var_300], r12
0x1400394df  lea     rcx, [rsp+358h+var_300]
0x1400394e4  call    cs:__imp_VssGetTracingContextPerThread
0x1400394ea  test    eax, eax
0x1400394ec  js      short loc_140039513
0x1400394ee  lea     rcx, [rsp+358h+var_2E8]
0x1400394f3  call    cs:__imp_VssSetTracingContextPerThread
0x1400394f9  mov     rcx, [rsp+358h+var_288]
0x140039501  test    eax, eax
0x140039503  cmovns  rcx, qword ptr [rsp+358h+var_300]
0x140039509  mov     [rsp+358h+var_288], rcx
0x140039511  jmp     short loc_14003951B
0x140039513  mov     rcx, [rsp+358h+var_288]
0x14003951b  test    rcx, rcx
0x14003951e  jz      short loc_14003952F
0x140039520  mov     eax, [rcx+30h]
0x140039523  add     eax, r13d
0x140039526  mov     [rsp+358h+var_2B8], eax
0x14003952d  jmp     short loc_140039537
0x14003952f  mov     [rsp+358h+var_2B8], r12d
0x140039537  mov     ebx, 0A0h
0x14003953c  cmp     [rsp+358h+var_2B0], 0FFh
0x140039547  cmovnz  ebx, [rsp+358h+var_2B0]
0x14003954f  lea     rcx, [rsp+358h+var_2E8]; this
0x140039554  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x140039559  test    eax, eax
0x14003955b  jz      short loc_1400395B0
0x14003955d  mov     [rsp+358h+var_318], r12
0x140039562  mov     [rsp+358h+var_320], ebx
0x140039566  lea     rax, aEnter; "ENTER"
0x14003956d  mov     [rsp+358h+var_328], rax
0x140039572  mov     rax, [rsp+358h+var_2C0]
0x14003957a  mov     [rsp+358h+peUse], rax
0x14003957f  mov     eax, [rsp+358h+var_2C4]
0x140039586  mov     dword ptr [rsp+358h+cchReferencedDomainName], eax
0x14003958a  mov     r9d, [rsp+358h+var_2B8]
0x140039592  mov     r8d, [rsp+358h+var_2C8]
0x14003959a  mov     rdx, [rsp+358h+var_2D0]
0x1400395a2  mov     rcx, [rsp+358h+var_2D8]
0x1400395aa  call    cs:__imp_VssTraceMessage
0x1400395b0  mov     ebx, 0Fh
0x1400395b5  cmp     byte ptr [rsp+358h+var_108+3], r12b
0x1400395bd  jz      short loc_1400395EC
0x1400395bf  mov     rdi, r12
0x1400395c2  mov     rcx, [rsp+rdi*8+358h+pv]; pv
0x1400395ca  test    rcx, rcx
0x1400395cd  jz      short loc_1400395DD
0x1400395cf  call    cs:__imp_CoTaskMemFree
0x1400395d5  mov     [rsp+rdi*8+358h+pv], r12
0x1400395dd  add     rdi, r13
0x1400395e0  cmp     rdi, rbx
0x1400395e3  jnz     short loc_1400395C2
0x1400395e5  lea     rdi, aBaseStorVssMod; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x1400395ec  cmp     [rsi+9E0h], r12
0x1400395f3  jz      loc_140039A53
0x1400395f9  cmp     [rsi+9E8h], r12d
0x140039600  jz      loc_140039A53
0x140039606  mov     [rsp+358h+StringSid], r12
0x14003960e  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x140039615  mov     [rsp+358h+var_278], rax
0x14003961d  lea     rcx, [rsp+358h+var_278]
0x140039625  call    ?Close@?$CVssAutoGenericValue_Storage@PEAG$0A@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZP6AAEAPEAGAEAPEAG@Z$1?Identity@?$DTyper@PEAG@@SAAEAPEAG1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<ushort *,0,void * (*)(void *),&LocalFree(void *),ushort * & (*)(ushort * &),&DTyper<ushort *>::Identity(ushort * &)>::Close(void)
0x14003962a  mov     rcx, [rsi+9E0h]
0x140039631  lea     rdx, [rsp+358h+StringSid]; StringSid
0x140039639  mov     rcx, [rcx]; Sid
0x14003963c  call    cs:__imp_ConvertSidToStringSidW
0x140039642  test    eax, eax
0x140039644  jnz     loc_140039701
0x14003964a  call    cs:__imp_GetLastError
0x140039650  mov     edi, eax
0x140039652  test    eax, eax
0x140039654  jg      short loc_14003965D
0x140039656  mov     esi, eax
0x140039658  mov     r14d, eax
0x14003965b  jmp     short loc_140039669
0x14003965d  movzx   esi, di
0x140039660  or      esi, 80070000h
0x140039666  mov     r14d, esi
0x140039669  lea     rax, aBaseStorVssMod; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x140039670  mov     [rsp+358h+var_268], rax
0x140039678  lea     rax, aCvsssnapshotse_0; "CVssSnapshotSetObject::GetComClientDeta"...
0x14003967f  mov     [rsp+358h+var_260], rax
0x140039687  lea     rax, aCorsnpsc; "CORSNPSC"
0x14003968e  mov     [rsp+358h+var_258], rax
0x140039696  mov     [rsp+358h+var_250], 96Eh
0x1400396a1  mov     [rsp+358h+var_24C], r13d
0x1400396a9  mov     [rsp+358h+var_248], 0FFh
0x1400396b4  mov     [rsp+358h+var_1C8], 1000000h
0x1400396bf  xor     edx, edx; Val
0x1400396c1  lea     r8d, [rdx+78h]; Size
0x1400396c5  lea     rcx, [rsp+358h+var_240]; void *
0x1400396cd  call    memset_0
0x1400396d2  mov     eax, 0FFFFh
0x1400396d7  add     bx, ax
0x1400396da  jnz     short loc_1400396D7
0x1400396dc  mov     dword ptr [rsp+358h+peUse], r14d
0x1400396e1  mov     dword ptr [rsp+358h+cchReferencedDomainName], edi
0x1400396e5  lea     r9, aFailToConvertC; "Fail to convert client process token to"...
0x1400396ec  mov     r8d, esi
0x1400396ef  lea     rdx, [rsp+358h+var_268]
0x1400396f7  lea     rcx, [rsp+358h+var_2E8]
0x1400396fc  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140039701  mov     [rsp+358h+cchName], 50h ; 'P'
0x140039709  movups  xmm6, xmmword ptr cs:aUnknown_0; "Unknown"
0x140039710  movdqu  xmmword ptr [rsp+358h+ReferencedDomainName], xmm6
0x140039719  mov     edi, 90h
0x14003971e  mov     r8d, edi; Size
0x140039721  xor     edx, edx; Val
0x140039723  lea     rcx, [rsp+358h+var_E8]; void *
0x14003972b  call    memset_0
0x140039730  movdqu  xmmword ptr [rsp+358h+Name], xmm6
0x140039739  mov     r8d, edi; Size
0x14003973c  xor     edx, edx; Val
0x14003973e  lea     rcx, [rsp+358h+var_198]; void *
0x140039746  call    memset_0
0x14003974b  mov     [rsp+358h+var_300], r12d
0x140039750  mov     rcx, [rsi+9E0h]
0x140039757  lea     rax, [rsp+358h+var_300]
0x14003975c  mov     [rsp+358h+peUse], rax; peUse
0x140039761  lea     rax, [rsp+358h+cchName]
0x140039766  mov     [rsp+358h+cchReferencedDomainName], rax; cchReferencedDomainName
0x14003976b  lea     r9, [rsp+358h+ReferencedDomainName]; ReferencedDomainName
0x140039773  lea     r8, [rsp+358h+cchName]; cchName
0x140039778  lea     rdx, [rsp+358h+Name]; Name
0x140039780  mov     rcx, [rcx]; Sid
0x140039783  call    cs:__imp_LookupAccountSidLocalW
0x140039789  test    eax, eax
0x14003978b  jnz     loc_140039848
0x140039791  call    cs:__imp_GetLastError
0x140039797  mov     edi, eax
0x140039799  test    eax, eax
0x14003979b  jg      short loc_1400397A4
0x14003979d  mov     esi, eax
0x14003979f  mov     r14d, eax
0x1400397a2  jmp     short loc_1400397B0
0x1400397a4  movzx   esi, di
0x1400397a7  or      esi, 80070000h
0x1400397ad  mov     r14d, esi
0x1400397b0  lea     rax, aBaseStorVssMod; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x1400397b7  mov     [rsp+358h+var_268], rax
0x1400397bf  lea     rax, aCvsssnapshotse_0; "CVssSnapshotSetObject::GetComClientDeta"...
0x1400397c6  mov     [rsp+358h+var_260], rax
0x1400397ce  lea     rax, aCorsnpsc; "CORSNPSC"
0x1400397d5  mov     [rsp+358h+var_258], rax
0x1400397dd  mov     [rsp+358h+var_250], 978h
0x1400397e8  mov     [rsp+358h+var_24C], r13d
0x1400397f0  mov     [rsp+358h+var_248], 0FFh
0x1400397fb  mov     [rsp+358h+var_1C8], 1000000h
0x140039806  xor     edx, edx; Val
0x140039808  lea     r8d, [rdx+78h]; Size
0x14003980c  lea     rcx, [rsp+358h+var_240]; void *
0x140039814  call    memset_0
0x140039819  mov     eax, 0FFFFh
0x14003981e  add     bx, ax
0x140039821  jnz     short loc_14003981E
0x140039823  mov     dword ptr [rsp+358h+peUse], r14d
0x140039828  mov     dword ptr [rsp+358h+cchReferencedDomainName], edi
0x14003982c  lea     r9, aFailToFindClie_0; "Fail to find client process account win"...
0x140039833  mov     r8d, esi
0x140039836  lea     rdx, [rsp+358h+var_268]
0x14003983e  lea     rcx, [rsp+358h+var_2E8]
0x140039843  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140039848  lea     r8, pszSrc; "\\"
0x14003984f  mov     edi, 50h ; 'P'
0x140039854  mov     edx, edi; unsigned __int64
0x140039856  lea     rcx, [rsp+358h+ReferencedDomainName]; unsigned __int16 *
0x14003985e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140039863  test    eax, eax
0x140039865  js      loc_140039980
0x14003986b  lea     r8, [rsp+358h+Name]; unsigned __int16 *
0x140039873  mov     edx, edi; unsigned __int64
0x140039875  lea     rcx, [rsp+358h+ReferencedDomainName]; unsigned __int16 *
0x14003987d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140039882  test    eax, eax
0x140039884  js      loc_140039980
0x14003988a  mov     r8, [rsp+358h+StringSid]; unsigned __int16 *
0x140039892  mov     edx, edi; unsigned __int64
0x140039894  mov     rcx, r14; unsigned __int16 *
0x140039897  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14003989c  test    eax, eax
0x14003989e  js      short loc_1400398C9
0x1400398a0  lea     r8, [rsp+358h+ReferencedDomainName]; unsigned __int16 *
0x1400398a8  mov     edx, edi; unsigned __int64
0x1400398aa  mov     rcx, r15; unsigned __int16 *
0x1400398ad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400398b2  test    eax, eax
0x1400398b4  js      short loc_1400398C9
0x1400398b6  lea     rcx, [rsp+358h+var_278]
0x1400398be  call    ??1?$CVssAutoLocalPtr@PEAX@@UEAA@XZ; CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(void)
0x1400398c3  nop
0x1400398c4  jmp     loc_140039A3E
0x1400398c9  call    cs:__imp_GetLastError
0x1400398cf  mov     edi, eax
0x1400398d1  test    eax, eax
0x1400398d3  jg      short loc_1400398DC
0x1400398d5  mov     esi, eax
0x1400398d7  mov     r14d, eax
0x1400398da  jmp     short loc_1400398E8
0x1400398dc  movzx   esi, di
0x1400398df  or      esi, 80070000h
0x1400398e5  mov     r14d, esi
0x1400398e8  lea     rax, aBaseStorVssMod; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x1400398ef  mov     [rsp+358h+var_268], rax
0x1400398f7  lea     rax, aCvsssnapshotse_0; "CVssSnapshotSetObject::GetComClientDeta"...
0x1400398fe  mov     [rsp+358h+var_260], rax
0x140039906  lea     rax, aCorsnpsc; "CORSNPSC"
0x14003990d  mov     [rsp+358h+var_258], rax
0x140039915  mov     [rsp+358h+var_250], 986h
0x140039920  mov     [rsp+358h+var_24C], r13d
0x140039928  mov     [rsp+358h+var_248], 0FFh
0x140039933  mov     [rsp+358h+var_1C8], 1000000h
0x14003993e  xor     edx, edx; Val
0x140039940  lea     r8d, [rdx+78h]; Size
0x140039944  lea     rcx, [rsp+358h+var_240]; void *
0x14003994c  call    memset_0
0x140039951  mov     eax, 0FFFFh
0x140039956  add     bx, ax
0x140039959  jnz     short loc_140039956
0x14003995b  mov     dword ptr [rsp+358h+peUse], r14d
0x140039960  mov     dword ptr [rsp+358h+cchReferencedDomainName], edi
0x140039964  lea     r9, aFailToWriteToD; "Fail to write to destination buffers wi"...
0x14003996b  mov     r8d, esi
0x14003996e  lea     rdx, [rsp+358h+var_268]
0x140039976  lea     rcx, [rsp+358h+var_2E8]
0x14003997b  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140039980  call    cs:__imp_GetLastError
0x140039986  mov     edi, eax
0x140039988  test    eax, eax
0x14003998a  jg      short loc_140039993
0x14003998c  mov     esi, eax
0x14003998e  mov     r14d, eax
0x140039991  jmp     short loc_14003999F
0x140039993  movzx   esi, di
0x140039996  or      esi, 80070000h
0x14003999c  mov     r14d, esi
0x14003999f  lea     rax, aBaseStorVssMod; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x1400399a6  mov     [rsp+358h+var_268], rax
0x1400399ae  lea     rax, aCvsssnapshotse_0; "CVssSnapshotSetObject::GetComClientDeta"...
0x1400399b5  mov     [rsp+358h+var_260], rax
0x1400399bd  lea     rax, aCorsnpsc; "CORSNPSC"
0x1400399c4  mov     [rsp+358h+var_258], rax
0x1400399cc  mov     [rsp+358h+var_250], 97Eh
0x1400399d7  mov     [rsp+358h+var_24C], r13d
0x1400399df  mov     [rsp+358h+var_248], 0FFh
0x1400399ea  mov     [rsp+358h+var_1C8], 1000000h
0x1400399f5  xor     edx, edx; Val
0x1400399f7  lea     r8d, [rdx+78h]; Size
  ... truncated ...
```
