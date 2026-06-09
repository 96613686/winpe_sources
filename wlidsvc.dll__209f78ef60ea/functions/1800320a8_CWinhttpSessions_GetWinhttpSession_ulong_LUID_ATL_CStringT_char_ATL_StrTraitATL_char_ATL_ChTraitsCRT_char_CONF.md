# CWinhttpSessions::GetWinhttpSession(ulong,_LUID &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,CONFIGDATA &,CAutoRefPtr<CWinhttpSession> &)

- ea: `0x1800320a8`
- end: `0x18003248e`
- name: `?GetWinhttpSession@CWinhttpSessions@@QEAAJKAEAU_LUID@@AEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@AEAUCONFIGDATA@@AEAV?$CAutoRefPtr@VCWinhttpSession@@@@@Z`
- size: `998`
- prototype: `__int64 __usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, struct CONFIGDATA *, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18006ccc8`

## callees

- `0x180010cdc`
- `0x1800151c4`
- `0x180015fb0`
- `0x180019690`
- `0x18001cf20`
- `0x180030bf8`
- `0x180030cf0`
- `0x180030f6c`
- `0x180031800`
- `0x18003184c`
- `0x1800320a8`
- `0x180032494`
- `0x180032640`
- `0x1800365b0`
- `0x180089374`
- `0x1800a400c`
- `0x1800a716c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032471`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032471`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800320e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800320e0`
- `SspiCli!LsaFreeReturnBuffer` at `0x180032467`
- `SspiCli!LsaFreeReturnBuffer` at `0x180032467`
- `SspiCli!LsaGetLogonSessionData` at `0x18003218d`
- `SspiCli!LsaGetLogonSessionData` at `0x18003231d`
- `SspiCli!LsaGetLogonSessionData` at `0x18003218d`
- `SspiCli!LsaGetLogonSessionData` at `0x18003231d`

## string_xrefs

- `0x18003222e`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\transport.cpp`
- `0x180032255`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\transport.cpp`
- `0x1800323f2`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\transport.cpp`
- `0x180032416`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\transport.cpp`
- `0x1800321af`: `DisableWinHttpCache`
- `0x18003233f`: `DisableWinHttpCache`
- `0x180032221`: `WinHttp session not cached because of registry setting.`
- `0x1800323e5`: `WinHttp session not cached because of registry setting.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CWinhttpSessions::GetWinhttpSession(
        LPCRITICAL_SECTION lpCriticalSection,
        unsigned int a2,
        struct _LUID *a3,
        __int64 a4,
        struct CONFIGDATA *a5,
        __int64 a6)
{
  __int64 v10; // rcx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // r8
  __int64 i; // rax
  __int64 v13; // rbx
  unsigned int HighPart; // r10d
  __int64 j; // rdx
  int NewWinhttpSession; // edi
  __int64 v17; // rdx
  __int64 v18; // rcx
  NTSTATUS LogonSessionData; // eax
  void *v20; // rax
  int v21; // edx
  int v22; // r8d
  int v23; // r9d
  __int64 v24; // rsi
  void *v25; // rbx
  __int64 *v26; // rax
  __int64 v27; // rcx
  __int64 *v28; // rdi
  NTSTATUS v29; // eax
  __int64 v30; // rax
  __int64 v32; // [rsp+20h] [rbp-59h]
  __int64 v33; // [rsp+30h] [rbp-49h] BYREF
  PSECURITY_LOGON_SESSION_DATA ppLogonSessionData; // [rsp+38h] [rbp-41h] BYREF
  __int64 v35; // [rsp+40h] [rbp-39h] BYREF
  __int64 v36[3]; // [rsp+48h] [rbp-31h] BYREF
  char v37; // [rsp+60h] [rbp-19h]
  _QWORD v38[11]; // [rsp+68h] [rbp-11h] BYREF
  int v39; // [rsp+D0h] [rbp+57h] BYREF

  v36[1] = 0;
  ppLogonSessionData = 0;
  v36[2] = (__int64)lpCriticalSection;
  EnterCriticalSection(lpCriticalSection);
  v37 = 1;
  DebugInfo = lpCriticalSection[1].DebugInfo;
  if ( DebugInfo )
  {
    for ( i = *((_QWORD *)&DebugInfo->Type + a2 % LODWORD(lpCriticalSection[1].OwningThread)); i; i = *(_QWORD *)(i + 16) )
    {
      if ( *(_DWORD *)(i + 24) == a2 && *(_DWORD *)i == a2 )
      {
        v13 = *(_QWORD *)(i + 8);
        if ( *(_QWORD *)v13 )
        {
          HighPart = a3->HighPart;
          for ( j = *(_QWORD *)(*(_QWORD *)v13
                              + 8 * ((HighPart ^ (unsigned __int64)a3->LowPart) % *(unsigned int *)(v13 + 16)));
                j;
                j = *(_QWORD *)(j + 16) )
          {
            if ( *(_DWORD *)(j + 24) == (HighPart ^ a3->LowPart)
              && *(_DWORD *)(j + 4) == HighPart
              && *(_DWORD *)j == a3->LowPart )
            {
              NewWinhttpSession = 0;
              v17 = j + 8;
              v18 = a6;
              goto LABEL_15;
            }
          }
        }
        NewWinhttpSession = CWinhttpSessions::CreateNewWinhttpSession(v10, a4, a6);
        if ( NewWinhttpSession >= 0 )
        {
          LogonSessionData = LsaGetLogonSessionData(a3, &ppLogonSessionData);
          if ( LogonSessionData )
          {
            TracePrintW(
              2u,
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
              0x554u,
              L"LsaGetLogonSessionData failed 0x%x.",
              LogonSessionData);
          }
          else if ( (ppLogonSessionData->UserFlags & 0x8000) != 0 )
          {
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              v36,
              L"DisableWinHttpCache");
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &v35,
              L"Software\\Microsoft\\IdentityCRL");
            v39 = 0;
            Reg_QueryDWORD(-2147483646, &v35, v36, &v39);
            ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v35);
            ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v36);
            if ( v39 )
            {
              TracePrintW(
                5u,
                "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
                0x54Eu,
                L"WinHttp session not cached because of registry setting.");
            }
            else
            {
              v18 = ATL::CAtlMap<_LUID,ATL::CAutoPtr<ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CAutoRefPtr<CIdentityTokenBag>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CAutoRefPtr<CIdentityTokenBag>>>>,ATL::CElementTraits<_LUID>,ATL::CAutoPtrElementTraits<ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CAutoRefPtr<CIdentityTokenBag>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CAutoRefPtr<CIdentityTokenBag>>>>>::operator[](
                      v13,
                      a3);
              v17 = a6;
LABEL_15:
              CAutoRefPtr<CStoredIdentityLock>::operator=(v18, v17);
            }
          }
        }
        goto LABEL_43;
      }
    }
  }
  v20 = operator new(0x48u, (const struct std::nothrow_t *)std::nothrow);
  if ( v20 )
    v24 = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>(
            (_DWORD)v20,
            v21,
            v22,
            v23,
            (_DWORD)FLOAT_2_25);
  else
    v24 = 0;
  v33 = 0;
  if ( !v24 )
  {
    NewWinhttpSession = -2147024882;
LABEL_28:
    ATL::CAutoPtr<ATL::CAtlMap<_LUID,CAutoRefPtr<CWinhttpSession>,ATL::CElementTraits<_LUID>,ATL::CElementTraits<CAutoRefPtr<CWinhttpSession>>>>::Free(&v33);
    goto LABEL_43;
  }
  v25 = (void *)v24;
  v33 = v24;
  v26 = (__int64 *)ATL::CAtlMap<unsigned long,ATL::CAutoPtr<ATL::CAtlMap<_LUID,CAutoRefPtr<CWinhttpSession>,ATL::CElementTraits<_LUID>,ATL::CElementTraits<CAutoRefPtr<CWinhttpSession>>>>,ATL::CElementTraits<unsigned long>,ATL::CAutoPtrElementTraits<ATL::CAtlMap<_LUID,CAutoRefPtr<CWinhttpSession>,ATL::CElementTraits<_LUID>,ATL::CElementTraits<CAutoRefPtr<CWinhttpSession>>>>>::operator[](
                     &lpCriticalSection[1],
                     a2);
  v28 = v26;
  if ( *v26 != v24 )
  {
    ATL::CAutoPtr<ATL::CAtlMap<_LUID,CAutoRefPtr<CWinhttpSession>,ATL::CElementTraits<_LUID>,ATL::CElementTraits<CAutoRefPtr<CWinhttpSession>>>>::Free(v26);
    *v28 = v24;
    goto LABEL_33;
  }
  if ( v26 != &v33 )
  {
LABEL_33:
    v25 = 0;
    v33 = 0;
  }
  NewWinhttpSession = CWinhttpSessions::CreateNewWinhttpSession(v27, a4, a6);
  if ( NewWinhttpSession < 0 )
    goto LABEL_28;
  v29 = LsaGetLogonSessionData(a3, &ppLogonSessionData);
  if ( v29 )
  {
    LODWORD(v32) = v29;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
      0x52Bu,
      L"LsaGetLogonSessionData failed 0x%x.",
      v32);
  }
  else if ( (ppLogonSessionData->UserFlags & 0x8000) != 0 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v35,
      L"DisableWinHttpCache");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      v36,
      L"Software\\Microsoft\\IdentityCRL");
    v39 = 0;
    v38[0] = &ExecutionContext::`vftable';
    v38[1] = &ComFunctions::`vftable';
    v38[2] = &StringSrvPassthrough::`vftable';
    RegQueryDWORD((unsigned int)v38, -2147483646, (unsigned int)v36, (unsigned int)&v35, (__int64)&v39);
    ATL::CStringData::Release((ATL::CStringData *)(v36[0] - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v35 - 24));
    if ( v39 )
    {
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
        0x525u,
        L"WinHttp session not cached because of registry setting.");
    }
    else
    {
      v30 = ATL::CAtlMap<_LUID,ATL::CAutoPtr<ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CAutoRefPtr<CIdentityTokenBag>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CAutoRefPtr<CIdentityTokenBag>>>>,ATL::CElementTraits<_LUID>,ATL::CAutoPtrElementTraits<ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CAutoRefPtr<CIdentityTokenBag>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CAutoRefPtr<CIdentityTokenBag>>>>>::operator[](
              v24,
              a3);
      CAutoRefPtr<CStoredIdentityLock>::operator=(v30, a6);
    }
  }
  if ( v25 )
  {
    ATL::CAtlMap<_LUID,CAutoRefPtr<CWinhttpSession>,ATL::CElementTraits<_LUID>,ATL::CElementTraits<CAutoRefPtr<CWinhttpSession>>>::RemoveAll(v25);
    operator delete(v25);
  }
LABEL_43:
  if ( g_pPPCRL )
    CSessionAppSettingsMap::GetAppSettings((LPCRITICAL_SECTION)g_pPPCRL + 41, a5);
  if ( ppLogonSessionData )
    LsaFreeReturnBuffer(ppLogonSessionData);
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)NewWinhttpSession;
}

```

## disassembly

```asm
0x1800320a8  push    rbp
0x1800320aa  push    rbx
0x1800320ab  push    rsi
0x1800320ac  push    rdi
0x1800320ad  push    r12
0x1800320af  push    r13
0x1800320b1  push    r14
0x1800320b3  push    r15
0x1800320b5  lea     rbp, [rsp-0Fh]
0x1800320ba  sub     rsp, 88h
0x1800320c1  mov     r12, r9
0x1800320c4  mov     r14, r8
0x1800320c7  mov     edi, edx
0x1800320c9  mov     r13, rcx
0x1800320cc  mov     [rbp+47h+var_70], 0
0x1800320d4  mov     [rbp+47h+ppLogonSessionData], 0
0x1800320dc  mov     [rbp+47h+var_68], rcx
0x1800320e0  call    cs:__imp_EnterCriticalSection
0x1800320e6  mov     [rbp+47h+var_60], 1
0x1800320ea  mov     r8, [r13+28h]
0x1800320ee  test    r8, r8
0x1800320f1  jz      loc_18003226B
0x1800320f7  xor     edx, edx
0x1800320f9  mov     eax, edi
0x1800320fb  div     dword ptr [r13+38h]
0x1800320ff  mov     rax, [r8+rdx*8]
0x180032103  test    rax, rax
0x180032106  jz      loc_18003226B
0x18003210c  cmp     [rax+18h], edi
0x18003210f  jnz     short loc_180032156
0x180032111  cmp     [rax], edi
0x180032113  jnz     short loc_180032156
0x180032115  mov     rbx, [rax+8]
0x180032119  mov     r9, [rbx]
0x18003211c  test    r9, r9
0x18003211f  jz      short loc_180032170
0x180032121  mov     r10d, [r14+4]
0x180032125  mov     r11d, [r14]
0x180032128  mov     r8d, r11d
0x18003212b  xor     r8d, r10d
0x18003212e  xor     edx, edx
0x180032130  mov     eax, r8d
0x180032133  div     dword ptr [rbx+10h]
0x180032136  mov     rdx, [r9+rdx*8]
0x18003213a  test    rdx, rdx
0x18003213d  jz      short loc_180032170
0x18003213f  cmp     [rdx+18h], r8d
0x180032143  jnz     short loc_180032150
0x180032145  cmp     [rdx+4], r10d
0x180032149  jnz     short loc_180032150
0x18003214b  cmp     [rdx], r11d
0x18003214e  jz      short loc_18003215C
0x180032150  mov     rdx, [rdx+10h]
0x180032154  jmp     short loc_18003213A
0x180032156  mov     rax, [rax+10h]
0x18003215a  jmp     short loc_180032103
0x18003215c  xor     edi, edi
0x18003215e  add     rdx, 8
0x180032162  mov     rcx, [rbp+47h+arg_28]
0x180032166  call    ??4?$CAutoRefPtr@VCStoredIdentityLock@@@@QEAAAEAV0@AEBV0@@Z; CAutoRefPtr<CStoredIdentityLock>::operator=(CAutoRefPtr<CStoredIdentityLock> const &)
0x18003216b  jmp     loc_180032442
0x180032170  mov     r8, [rbp+47h+arg_28]
0x180032174  mov     rdx, r12
0x180032177  call    ?CreateNewWinhttpSession@CWinhttpSessions@@AEAAJAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@AEAV?$CAutoRefPtr@VCWinhttpSession@@@@@Z; CWinhttpSessions::CreateNewWinhttpSession(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,CAutoRefPtr<CWinhttpSession> &)
0x18003217c  mov     edi, eax
0x18003217e  test    eax, eax
0x180032180  js      loc_180032442
0x180032186  lea     rdx, [rbp+47h+ppLogonSessionData]; ppLogonSessionData
0x18003218a  mov     rcx, r14; LogonId
0x18003218d  call    cs:__imp_LsaGetLogonSessionData
0x180032193  test    eax, eax
0x180032195  jnz     loc_180032244
0x18003219b  mov     rcx, [rbp+47h+ppLogonSessionData]
0x18003219f  test    dword ptr [rcx+88h], 8000h
0x1800321a9  jz      loc_180032442
0x1800321af  lea     rdx, aDisablewinhttp; "DisableWinHttpCache"
0x1800321b6  lea     rcx, [rbp+47h+var_78]
0x1800321ba  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800321bf  nop
0x1800321c0  lea     rdx, SubKey; "Software\\Microsoft\\IdentityCRL"
0x1800321c7  lea     rcx, [rbp+47h+var_80]
0x1800321cb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800321d0  nop
0x1800321d1  mov     [rbp+47h+arg_0], 0
0x1800321d8  lea     r9, [rbp+47h+arg_0]
0x1800321dc  lea     r8, [rbp+47h+var_78]
0x1800321e0  lea     rdx, [rbp+47h+var_80]
0x1800321e4  mov     rcx, 0FFFFFFFF80000002h
0x1800321eb  call    ?Reg_QueryDWORD@@YAJPEAUHKEY__@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1AEAKH@Z; Reg_QueryDWORD(HKEY__ *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong &,int)
0x1800321f0  nop
0x1800321f1  lea     rcx, [rbp+47h+var_80]
0x1800321f5  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800321fa  nop
0x1800321fb  lea     rcx, [rbp+47h+var_78]
0x1800321ff  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180032204  cmp     [rbp+47h+arg_0], 0
0x180032208  jnz     short loc_180032221
0x18003220a  mov     rdx, r14
0x18003220d  mov     rcx, rbx
0x180032210  call    ??A?$CAtlMap@U_LUID@@V?$CAutoPtr@V?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CAutoRefPtr@VCIdentityTokenBag@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$CAutoRefPtr@VCIdentityTokenBag@@@@@2@@ATL@@@ATL@@V?$CElementTraits@U_LUID@@@3@V?$CAutoPtrElementTraits@V?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CAutoRefPtr@VCIdentityTokenBag@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$CAutoRefPtr@VCIdentityTokenBag@@@@@2@@ATL@@@3@@ATL@@QEAAAEAV?$CAutoPtr@V?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CAutoRefPtr@VCIdentityTokenBag@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$CAutoRefPtr@VCIdentityTokenBag@@@@@2@@ATL@@@1@AEBU_LUID@@@Z; ATL::CAtlMap<_LUID,ATL::CAutoPtr<ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CAutoRefPtr<CIdentityTokenBag>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CAutoRefPtr<CIdentityTokenBag>>>>,ATL::CElementTraits<_LUID>,ATL::CAutoPtrElementTraits<ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CAutoRefPtr<CIdentityTokenBag>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CAutoRefPtr<CIdentityTokenBag>>>>>::operator[](_LUID const &)
0x180032215  mov     rcx, rax
0x180032218  mov     rdx, [rbp+47h+arg_28]
0x18003221c  jmp     loc_180032166
0x180032221  lea     r9, aWinhttpSession; "WinHttp session not cached because of r"...
0x180032228  mov     r8d, 54Eh; unsigned int
0x18003222e  lea     rdx, aOnecoreuapDsEx_35; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180032235  mov     ecx, 5; unsigned __int8
0x18003223a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18003223f  jmp     loc_180032442
0x180032244  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180032248  lea     r9, aLsagetlogonses_0; "LsaGetLogonSessionData failed 0x%x."
0x18003224f  mov     r8d, 554h; unsigned int
0x180032255  lea     rdx, aOnecoreuapDsEx_35; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18003225c  mov     ecx, 2; unsigned __int8
0x180032261  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180032266  jmp     loc_180032442
0x18003226b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180032272  mov     ecx, 48h ; 'H'; unsigned __int64
0x180032277  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003227c  test    rax, rax
0x18003227f  jz      short loc_1800322AC
0x180032281  movss   xmm0, cs:__real@40100000
0x180032289  movss   dword ptr [rsp+0C0h+var_A0], xmm0
0x18003228f  movss   xmm3, cs:__real@3e800000
0x180032297  movss   xmm2, cs:__real@3f400000
0x18003229f  mov     rcx, rax
0x1800322a2  call    ??0?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@G@2@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA@IMMMI@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>(uint,float,float,float,uint)
0x1800322a7  mov     rsi, rax
0x1800322aa  jmp     short loc_1800322AE
0x1800322ac  xor     esi, esi
0x1800322ae  mov     [rbp+47h+var_90], 0
0x1800322b6  test    rsi, rsi
0x1800322b9  jnz     short loc_1800322CE
0x1800322bb  mov     edi, 8007000Eh
0x1800322c0  lea     rcx, [rbp+47h+var_90]
0x1800322c4  call    ?Free@?$CAutoPtr@V?$CAtlMap@U_LUID@@V?$CAutoRefPtr@VCWinhttpSession@@@@V?$CElementTraits@U_LUID@@@ATL@@V?$CElementTraits@V?$CAutoRefPtr@VCWinhttpSession@@@@@4@@ATL@@@ATL@@QEAAXXZ; ATL::CAutoPtr<ATL::CAtlMap<_LUID,CAutoRefPtr<CWinhttpSession>,ATL::CElementTraits<_LUID>,ATL::CElementTraits<CAutoRefPtr<CWinhttpSession>>>>::Free(void)
0x1800322c9  jmp     loc_180032442
0x1800322ce  mov     rbx, rsi
0x1800322d1  mov     [rbp+47h+var_90], rbx
0x1800322d5  mov     edx, edi
0x1800322d7  lea     rcx, [r13+28h]
0x1800322db  call    ??A?$CAtlMap@KV?$CAutoPtr@V?$CAtlMap@U_LUID@@V?$CAutoRefPtr@VCWinhttpSession@@@@V?$CElementTraits@U_LUID@@@ATL@@V?$CElementTraits@V?$CAutoRefPtr@VCWinhttpSession@@@@@4@@ATL@@@ATL@@V?$CElementTraits@K@2@V?$CAutoPtrElementTraits@V?$CAtlMap@U_LUID@@V?$CAutoRefPtr@VCWinhttpSession@@@@V?$CElementTraits@U_LUID@@@ATL@@V?$CElementTraits@V?$CAutoRefPtr@VCWinhttpSession@@@@@4@@ATL@@@2@@ATL@@QEAAAEAV?$CAutoPtr@V?$CAtlMap@U_LUID@@V?$CAutoRefPtr@VCWinhttpSession@@@@V?$CElementTraits@U_LUID@@@ATL@@V?$CElementTraits@V?$CAutoRefPtr@VCWinhttpSession@@@@@4@@ATL@@@1@K@Z; ATL::CAtlMap<ulong,ATL::CAutoPtr<ATL::CAtlMap<_LUID,CAutoRefPtr<CWinhttpSession>,ATL::CElementTraits<_LUID>,ATL::CElementTraits<CAutoRefPtr<CWinhttpSession>>>>,ATL::CElementTraits<ulong>,ATL::CAutoPtrElementTraits<ATL::CAtlMap<_LUID,CAutoRefPtr<CWinhttpSession>,ATL::CElementTraits<_LUID>,ATL::CElementTraits<CAutoRefPtr<CWinhttpSession>>>>>::operator[](ulong)
0x1800322e0  mov     rdi, rax
0x1800322e3  cmp     [rax], rsi
0x1800322e6  jnz     short loc_1800322F3
0x1800322e8  lea     rax, [rbp+47h+var_90]
0x1800322ec  cmp     rdi, rax
0x1800322ef  jnz     short loc_1800322FE
0x1800322f1  jmp     short loc_180032304
0x1800322f3  mov     rcx, rdi
0x1800322f6  call    ?Free@?$CAutoPtr@V?$CAtlMap@U_LUID@@V?$CAutoRefPtr@VCWinhttpSession@@@@V?$CElementTraits@U_LUID@@@ATL@@V?$CElementTraits@V?$CAutoRefPtr@VCWinhttpSession@@@@@4@@ATL@@@ATL@@QEAAXXZ; ATL::CAutoPtr<ATL::CAtlMap<_LUID,CAutoRefPtr<CWinhttpSession>,ATL::CElementTraits<_LUID>,ATL::CElementTraits<CAutoRefPtr<CWinhttpSession>>>>::Free(void)
0x1800322fb  mov     [rdi], rsi
0x1800322fe  xor     ebx, ebx
0x180032300  mov     [rbp+47h+var_90], rbx
0x180032304  mov     r8, [rbp+47h+arg_28]
0x180032308  mov     rdx, r12
0x18003230b  call    ?CreateNewWinhttpSession@CWinhttpSessions@@AEAAJAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@AEAV?$CAutoRefPtr@VCWinhttpSession@@@@@Z; CWinhttpSessions::CreateNewWinhttpSession(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,CAutoRefPtr<CWinhttpSession> &)
0x180032310  mov     edi, eax
0x180032312  test    eax, eax
0x180032314  js      short loc_1800322C0
0x180032316  lea     rdx, [rbp+47h+ppLogonSessionData]; ppLogonSessionData
0x18003231a  mov     rcx, r14; LogonId
0x18003231d  call    cs:__imp_LsaGetLogonSessionData
0x180032323  test    eax, eax
0x180032325  jnz     loc_180032405
0x18003232b  mov     rax, [rbp+47h+ppLogonSessionData]
0x18003232f  test    dword ptr [rax+88h], 8000h
0x180032339  jz      loc_180032428
0x18003233f  lea     rdx, aDisablewinhttp; "DisableWinHttpCache"
0x180032346  lea     rcx, [rbp+47h+var_80]
0x18003234a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18003234f  nop
0x180032350  lea     rdx, SubKey; "Software\\Microsoft\\IdentityCRL"
0x180032357  lea     rcx, [rbp+47h+var_78]
0x18003235b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180032360  nop
0x180032361  mov     [rbp+47h+arg_0], 0
0x180032368  lea     rax, ??_7ExecutionContext@@6B@; const ExecutionContext::`vftable'
0x18003236f  mov     [rbp+47h+var_58], rax
0x180032373  lea     rax, ??_7ComFunctions@@6B@; const ComFunctions::`vftable'
0x18003237a  mov     [rbp+47h+var_50], rax
0x18003237e  lea     rax, ??_7StringSrvPassthrough@@6B@; const StringSrvPassthrough::`vftable'
0x180032385  mov     [rbp+47h+var_48], rax
0x180032389  lea     rax, [rbp+47h+arg_0]
0x18003238d  mov     [rsp+0C0h+var_A0], rax
0x180032392  lea     r9, [rbp+47h+var_80]
0x180032396  lea     r8, [rbp+47h+var_78]
0x18003239a  mov     rdx, 0FFFFFFFF80000002h
0x1800323a1  lea     rcx, [rbp+47h+var_58]
0x1800323a5  call    ?RegQueryDWORD@@YAJPEAVIExecutionContext@@PEAUHKEY__@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@2PEAKH@Z; RegQueryDWORD(IExecutionContext *,HKEY__ *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong *,int)
0x1800323aa  nop
0x1800323ab  mov     rcx, [rbp+47h+var_78]
0x1800323af  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800323b3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800323b8  nop
0x1800323b9  mov     rcx, [rbp+47h+var_80]
0x1800323bd  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800323c1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800323c6  cmp     [rbp+47h+arg_0], 0
0x1800323ca  jnz     short loc_1800323E5
0x1800323cc  mov     rdx, r14
0x1800323cf  mov     rcx, rsi
0x1800323d2  call    ??A?$CAtlMap@U_LUID@@V?$CAutoPtr@V?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CAutoRefPtr@VCIdentityTokenBag@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$CAutoRefPtr@VCIdentityTokenBag@@@@@2@@ATL@@@ATL@@V?$CElementTraits@U_LUID@@@3@V?$CAutoPtrElementTraits@V?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CAutoRefPtr@VCIdentityTokenBag@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$CAutoRefPtr@VCIdentityTokenBag@@@@@2@@ATL@@@3@@ATL@@QEAAAEAV?$CAutoPtr@V?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CAutoRefPtr@VCIdentityTokenBag@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$CAutoRefPtr@VCIdentityTokenBag@@@@@2@@ATL@@@1@AEBU_LUID@@@Z; ATL::CAtlMap<_LUID,ATL::CAutoPtr<ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CAutoRefPtr<CIdentityTokenBag>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CAutoRefPtr<CIdentityTokenBag>>>>,ATL::CElementTraits<_LUID>,ATL::CAutoPtrElementTraits<ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CAutoRefPtr<CIdentityTokenBag>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CAutoRefPtr<CIdentityTokenBag>>>>>::operator[](_LUID const &)
0x1800323d7  mov     rcx, rax
0x1800323da  mov     rdx, [rbp+47h+arg_28]
0x1800323de  call    ??4?$CAutoRefPtr@VCStoredIdentityLock@@@@QEAAAEAV0@AEBV0@@Z; CAutoRefPtr<CStoredIdentityLock>::operator=(CAutoRefPtr<CStoredIdentityLock> const &)
0x1800323e3  jmp     short loc_180032428
0x1800323e5  lea     r9, aWinhttpSession; "WinHttp session not cached because of r"...
0x1800323ec  mov     r8d, 525h; unsigned int
0x1800323f2  lea     rdx, aOnecoreuapDsEx_35; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800323f9  mov     ecx, 5; unsigned __int8
0x1800323fe  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180032403  jmp     short loc_180032428
0x180032405  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180032409  lea     r9, aLsagetlogonses_0; "LsaGetLogonSessionData failed 0x%x."
0x180032410  mov     r8d, 52Bh; unsigned int
0x180032416  lea     rdx, aOnecoreuapDsEx_35; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18003241d  mov     ecx, 2; unsigned __int8
0x180032422  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180032427  nop
0x180032428  test    rbx, rbx
0x18003242b  jz      short loc_180032442
0x18003242d  mov     rcx, rbx
0x180032430  call    ?RemoveAll@?$CAtlMap@U_LUID@@V?$CAutoRefPtr@VCWinhttpSession@@@@V?$CElementTraits@U_LUID@@@ATL@@V?$CElementTraits@V?$CAutoRefPtr@VCWinhttpSession@@@@@4@@ATL@@QEAAXXZ; ATL::CAtlMap<_LUID,CAutoRefPtr<CWinhttpSession>,ATL::CElementTraits<_LUID>,ATL::CElementTraits<CAutoRefPtr<CWinhttpSession>>>::RemoveAll(void)
0x180032435  mov     edx, 48h ; 'H'
0x18003243a  mov     rcx, rbx; Block
0x18003243d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180032442  mov     rcx, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x180032449  test    rcx, rcx
0x18003244c  jz      short loc_18003245E
0x18003244e  add     rcx, 668h; lpCriticalSection
0x180032455  mov     rdx, [rbp+47h+arg_20]; struct CONFIGDATA *
0x180032459  call    ?GetAppSettings@CSessionAppSettingsMap@@QEAAJAEAUCONFIGDATA@@@Z; CSessionAppSettingsMap::GetAppSettings(CONFIGDATA &)
0x18003245e  mov     rcx, [rbp+47h+ppLogonSessionData]; Buffer
0x180032462  test    rcx, rcx
0x180032465  jz      short loc_18003246E
0x180032467  call    cs:__imp_LsaFreeReturnBuffer
0x18003246d  nop
0x18003246e  mov     rcx, r13; lpCriticalSection
0x180032471  call    cs:__imp_LeaveCriticalSection
0x180032477  nop
0x180032478  mov     eax, edi
0x18003247a  add     rsp, 88h
0x180032481  pop     r15
0x180032483  pop     r14
0x180032485  pop     r13
0x180032487  pop     r12
0x180032489  pop     rdi
0x18003248a  pop     rsi
0x18003248b  pop     rbx
0x18003248c  pop     rbp
0x18003248d  retn
```
