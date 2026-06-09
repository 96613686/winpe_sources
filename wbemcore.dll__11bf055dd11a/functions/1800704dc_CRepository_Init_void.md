# CRepository::Init(void)

- ea: `0x1800704dc`
- end: `0x1800708b4`
- name: `?Init@CRepository@@SAJXZ`
- size: `984`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180059524`
- `0x1800866b8`

## callees

- `0x18000b140`
- `0x18000b46c`
- `0x18003cfe0`
- `0x18006fa48`
- `0x1800704dc`
- `0x180070b44`
- `0x180070c74`
- `0x180086c50`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800707e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800707e5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180070814`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180070814`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180070796`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180070796`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x18007074c`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x18007074c`
- `wbemcomn!?GetRegistryPathCIMOM@CWbemInstallObject@@SAPEBGXZ` at `0x180070756`
- `wbemcomn!?GetRegistryPathCIMOM@CWbemInstallObject@@SAPEBGXZ` at `0x180070756`
- `wbemcomn!?GetRegistryPathRoot@CWbemInstallObject@@SAPEAUHKEY__@@XZ` at `0x18007075f`
- `wbemcomn!?GetRegistryPathRoot@CWbemInstallObject@@SAPEAUHKEY__@@XZ` at `0x18007075f`
- `wbemcomn!?CoCreateInstance@CWbemInstallObject@@SAJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@Z` at `0x1800705ca`
- `wbemcomn!?CoCreateInstance@CWbemInstallObject@@SAJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@Z` at `0x1800705ca`
- `wbemcomn!GetMemLogObject` at `0x18007056c`
- `wbemcomn!GetMemLogObject` at `0x1800705d6`
- `wbemcomn!GetMemLogObject` at `0x180070630`
- `wbemcomn!GetMemLogObject` at `0x18007083c`
- `wbemcomn!GetMemLogObject` at `0x18007056c`
- `wbemcomn!GetMemLogObject` at `0x1800705d6`
- `wbemcomn!GetMemLogObject` at `0x180070630`
- `wbemcomn!GetMemLogObject` at `0x18007083c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180070577`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800705e1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007063b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180070847`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180070577`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800705e1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007063b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180070847`

## string_xrefs

- `0x1800707da`: `Max Class Cache Size`
- `0x180070809`: `Max Class Cache Size`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 CRepository::Init(void)
{
  int DefaultRepDriverClsId; // ebx
  CMemoryLog *MemLogObject; // rax
  CClientCnt *v2; // rcx
  __int64 v3; // rdx
  CMemoryLog *v5; // rax
  struct IWmiDbController *v6; // rbx
  int v7; // edi
  CMemoryLog *v8; // rax
  int v9; // esi
  const WCHAR *RegistryPathCIMOM; // rdi
  HKEY RegistryPathRoot; // rax
  LSTATUS v12; // eax
  CMemoryLog *v13; // rax
  BYTE Data[4]; // [rsp+40h] [rbp-39h] BYREF
  struct IWmiDbController *v15; // [rsp+48h] [rbp-31h] BYREF
  __int64 v16; // [rsp+50h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-21h] BYREF
  DWORD cbData; // [rsp+60h] [rbp-19h] BYREF
  struct IWmiDbSession *v19; // [rsp+68h] [rbp-11h] BYREF
  struct IWmiDbHandle *v20; // [rsp+70h] [rbp-9h] BYREF
  struct IWmiDbController *v21; // [rsp+78h] [rbp-1h] BYREF
  HKEY v22; // [rsp+80h] [rbp+7h] BYREF
  GUID pclsid; // [rsp+88h] [rbp+Fh] BYREF

  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids);
  }
  v15 = 0;
  v16 = 0;
  v19 = 0;
  v20 = 0;
  pclsid = 0;
  DefaultRepDriverClsId = ConfigMgr::GetDefaultRepDriverClsId(&pclsid);
  if ( DefaultRepDriverClsId < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, DefaultRepDriverClsId);
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)DefaultRepDriverClsId;
    }
    v3 = 16;
LABEL_10:
    WPP_SF_d(
      *((_QWORD *)v2 + 2),
      v3,
      WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
      (unsigned int)DefaultRepDriverClsId);
    return (unsigned int)DefaultRepDriverClsId;
  }
  DefaultRepDriverClsId = CWbemInstallObject::CoCreateInstance(&pclsid, 0, 1u, &IID_IWmiDbController, (void **)&v15);
  if ( DefaultRepDriverClsId < 0 )
  {
    v5 = GetMemLogObject();
    CMemoryLog::Write(v5, DefaultRepDriverClsId);
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)DefaultRepDriverClsId;
    }
    v3 = 17;
    goto LABEL_10;
  }
  v6 = v15;
  v21 = v15;
  v7 = (*(__int64 (__fastcall **)(struct IWmiDbController *, __int64, _QWORD, __int64 *))(*(_QWORD *)v15 + 32LL))(
         v15,
         1033,
         0,
         &v16);
  if ( v7 < 0 )
  {
    v8 = GetMemLogObject();
    CMemoryLog::Write(v8, v7);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
        (unsigned int)v7);
    }
    goto LABEL_32;
  }
  *(_WORD *)(*(_QWORD *)(v16 + 8) + 16LL) = 3;
  *(_DWORD *)(*(_QWORD *)(v16 + 8) + 24LL) = g_SecFlagTlsIndex;
  v9 = (*(__int64 (__fastcall **)(struct IWmiDbController *, __int64, _QWORD, __int64, struct IWmiDbSession **, struct IWmiDbHandle **))(*(_QWORD *)v15 + 24LL))(
         v15,
         v16,
         0,
         2,
         &v19,
         &v20);
  if ( v9 >= 0 )
  {
    CRepository::m_pEseSession = v19;
    CRepository::m_pEseRoot = v20;
  }
  (*(void (__fastcall **)(struct IWmiDbController *, __int64 *))(*(_QWORD *)v15 + 40LL))(v15, &v16);
  if ( v9 < 0
    || ((*(void (__fastcall **)(struct IWmiDbController *))(*(_QWORD *)v15 + 8LL))(v15),
        CRepository::m_pEseController = v15,
        v9 = CRepository::EnsureDefault(),
        v9 < 0)
    || (v9 = CRepository::UpgradeSystemClasses(), v9 < 0) )
  {
    v13 = GetMemLogObject();
    CMemoryLog::Write(v13, v9);
  }
  else
  {
    *(_DWORD *)Data = 0;
    hKey = 0;
    if ( (unsigned __int8)CWbemInstallObject::IsOffline() )
    {
      RegistryPathCIMOM = (const WCHAR *)CWbemInstallObject::GetRegistryPathCIMOM();
      RegistryPathRoot = (HKEY)CWbemInstallObject::GetRegistryPathRoot();
      v12 = RegOpenKeyExW(RegistryPathRoot, RegistryPathCIMOM, 0, 0x2001Fu, &hKey);
    }
    else
    {
      v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WBEM\\CIMOM", 0, 0x2001Fu, &hKey);
    }
    if ( v12 )
    {
      v7 = v12;
LABEL_32:
      CReleaseMe::release((CReleaseMe *)&v21);
      return (unsigned int)v7;
    }
    v22 = hKey;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"Max Class Cache Size", 0, 0, Data, &cbData) )
    {
      strcpy((char *)Data, "@KL");
      RegSetValueExW(hKey, L"Max Class Cache Size", 0, 4u, Data, 4u);
    }
    (*(void (__fastcall **)(struct IWmiDbController *, _QWORD))(*(_QWORD *)CRepository::m_pEseController + 64LL))(
      CRepository::m_pEseController,
      *(unsigned int *)Data);
    CRegCloseMe::~CRegCloseMe((CRegCloseMe *)&v22);
  }
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids, (unsigned int)v9);
  }
  if ( v6 )
    (*(void (__fastcall **)(struct IWmiDbController *))(*(_QWORD *)v6 + 16LL))(v6);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800704dc  push    rbp
0x1800704de  push    rbx
0x1800704df  push    rsi
0x1800704e0  push    rdi
0x1800704e1  push    r12
0x1800704e3  push    r13
0x1800704e5  lea     rbp, [rsp-2Fh]
0x1800704ea  sub     rsp, 0A8h
0x1800704f1  mov     rax, cs:__security_cookie
0x1800704f8  xor     rax, rsp
0x1800704fb  mov     [rbp+57h+var_38], rax
0x1800704ff  lea     r12, WPP_GLOBAL_Control
0x180070506  lea     r13, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids
0x18007050d  mov     rcx, cs:WPP_GLOBAL_Control
0x180070514  cmp     rcx, r12
0x180070517  jz      short loc_180070536
0x180070519  test    byte ptr [rcx+1Ch], 1
0x18007051d  jz      short loc_180070536
0x18007051f  cmp     byte ptr [rcx+19h], 5
0x180070523  jb      short loc_180070536
0x180070525  mov     edx, 0Fh
0x18007052a  mov     r8, r13
0x18007052d  mov     rcx, [rcx+10h]
0x180070531  call    WPP_SF_
0x180070536  mov     [rbp+57h+var_88], 0
0x18007053e  mov     [rbp+57h+var_80], 0
0x180070546  mov     [rbp+57h+var_68], 0
0x18007054e  mov     [rbp+57h+var_60], 0
0x180070556  xorps   xmm0, xmm0
0x180070559  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x18007055d  lea     rcx, [rbp+57h+pclsid]; pclsid
0x180070561  call    ?GetDefaultRepDriverClsId@ConfigMgr@@SAJAEAU_GUID@@@Z; ConfigMgr::GetDefaultRepDriverClsId(_GUID &)
0x180070566  mov     ebx, eax
0x180070568  test    eax, eax
0x18007056a  jns     short loc_1800705B0
0x18007056c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180070572  mov     edx, ebx
0x180070574  mov     rcx, rax
0x180070577  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007057d  mov     rcx, cs:WPP_GLOBAL_Control
0x180070584  cmp     rcx, r12
0x180070587  jz      short loc_1800705A9
0x180070589  test    byte ptr [rcx+1Ch], 1
0x18007058d  jz      short loc_1800705A9
0x18007058f  cmp     byte ptr [rcx+19h], 2
0x180070593  jb      short loc_1800705A9
0x180070595  mov     edx, 10h
0x18007059a  mov     r9d, ebx
0x18007059d  mov     r8, r13
0x1800705a0  mov     rcx, [rcx+10h]
0x1800705a4  call    WPP_SF_d
0x1800705a9  mov     eax, ebx
0x1800705ab  jmp     loc_180070898
0x1800705b0  lea     rax, [rbp+57h+var_88]
0x1800705b4  mov     [rsp+0D0h+phkResult], rax
0x1800705b9  lea     r9, IID_IWmiDbController
0x1800705c0  xor     edx, edx
0x1800705c2  lea     r8d, [rdx+1]
0x1800705c6  lea     rcx, [rbp+57h+pclsid]
0x1800705ca  call    cs:__imp_?CoCreateInstance@CWbemInstallObject@@SAJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@Z; CWbemInstallObject::CoCreateInstance(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x1800705d0  mov     ebx, eax
0x1800705d2  test    eax, eax
0x1800705d4  jns     short loc_180070606
0x1800705d6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800705dc  mov     edx, ebx
0x1800705de  mov     rcx, rax
0x1800705e1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800705e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800705ee  cmp     rcx, r12
0x1800705f1  jz      short loc_1800705A9
0x1800705f3  test    byte ptr [rcx+1Ch], 1
0x1800705f7  jz      short loc_1800705A9
0x1800705f9  cmp     byte ptr [rcx+19h], 2
0x1800705fd  jb      short loc_1800705A9
0x1800705ff  mov     edx, 11h
0x180070604  jmp     short loc_18007059A
0x180070606  mov     rbx, [rbp+57h+var_88]
0x18007060a  mov     [rbp+57h+var_58], rbx
0x18007060e  mov     rcx, [rbp+57h+var_88]
0x180070612  mov     rax, [rcx]
0x180070615  lea     r9, [rbp+57h+var_80]
0x180070619  xor     r8d, r8d
0x18007061c  mov     edx, 409h
0x180070621  mov     rax, [rax+20h]
0x180070625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007062a  mov     edi, eax
0x18007062c  test    eax, eax
0x18007062e  jns     short loc_18007067E
0x180070630  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180070636  mov     edx, edi
0x180070638  mov     rcx, rax
0x18007063b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180070641  mov     rcx, cs:WPP_GLOBAL_Control
0x180070648  cmp     rcx, r12
0x18007064b  jz      loc_1800707A2
0x180070651  test    byte ptr [rcx+1Ch], 1
0x180070655  jz      loc_1800707A2
0x18007065b  cmp     byte ptr [rcx+19h], 2
0x18007065f  jb      loc_1800707A2
0x180070665  mov     edx, 12h
0x18007066a  mov     r9d, edi
0x18007066d  mov     r8, r13
0x180070670  mov     rcx, [rcx+10h]
0x180070674  call    WPP_SF_d
0x180070679  jmp     loc_1800707A2
0x18007067e  mov     rax, [rbp+57h+var_80]
0x180070682  mov     rcx, [rax+8]
0x180070686  mov     word ptr [rcx+10h], 3
0x18007068c  mov     rax, [rbp+57h+var_80]
0x180070690  mov     rcx, [rax+8]
0x180070694  mov     eax, cs:?g_SecFlagTlsIndex@@3VCTLS@@A; CTLS g_SecFlagTlsIndex
0x18007069a  mov     [rcx+18h], eax
0x18007069d  mov     rcx, [rbp+57h+var_88]
0x1800706a1  mov     rax, [rcx]
0x1800706a4  lea     rdx, [rbp+57h+var_60]
0x1800706a8  mov     [rsp+0D0h+lpcbData], rdx
0x1800706ad  lea     rdx, [rbp+57h+var_68]
0x1800706b1  mov     [rsp+0D0h+phkResult], rdx
0x1800706b6  mov     r9d, 2
0x1800706bc  xor     r8d, r8d
0x1800706bf  mov     rdx, [rbp+57h+var_80]
0x1800706c3  mov     rax, [rax+18h]
0x1800706c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800706cc  mov     esi, eax
0x1800706ce  test    eax, eax
0x1800706d0  js      short loc_1800706E8
0x1800706d2  mov     rcx, [rbp+57h+var_68]
0x1800706d6  mov     cs:?m_pEseSession@CRepository@@0PEAUIWmiDbSession@@EA, rcx; IWmiDbSession * CRepository::m_pEseSession
0x1800706dd  mov     rcx, [rbp+57h+var_60]
0x1800706e1  mov     cs:?m_pEseRoot@CRepository@@0PEAUIWmiDbHandle@@EA, rcx; IWmiDbHandle * CRepository::m_pEseRoot
0x1800706e8  mov     rcx, [rbp+57h+var_88]
0x1800706ec  mov     rdx, [rcx]
0x1800706ef  mov     rax, [rdx+28h]
0x1800706f3  lea     rdx, [rbp+57h+var_80]
0x1800706f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800706fc  test    esi, esi
0x1800706fe  js      loc_18007083C
0x180070704  mov     rcx, [rbp+57h+var_88]
0x180070708  mov     rax, [rcx]
0x18007070b  mov     rax, [rax+8]
0x18007070f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070714  mov     rax, [rbp+57h+var_88]
0x180070718  mov     cs:?m_pEseController@CRepository@@0PEAUIWmiDbController@@EA, rax; IWmiDbController * CRepository::m_pEseController
0x18007071f  call    ?EnsureDefault@CRepository@@CAJXZ; CRepository::EnsureDefault(void)
0x180070724  mov     esi, eax
0x180070726  test    eax, eax
0x180070728  js      loc_18007083C
0x18007072e  call    ?UpgradeSystemClasses@CRepository@@CAJXZ; CRepository::UpgradeSystemClasses(void)
0x180070733  mov     esi, eax
0x180070735  test    eax, eax
0x180070737  js      loc_18007083C
0x18007073d  mov     dword ptr [rbp+57h+Data], 0
0x180070744  mov     [rbp+57h+hKey], 0
0x18007074c  call    cs:__imp_?IsOffline@CWbemInstallObject@@SA_NXZ; CWbemInstallObject::IsOffline(void)
0x180070752  test    al, al
0x180070754  jz      short loc_180070776
0x180070756  call    cs:__imp_?GetRegistryPathCIMOM@CWbemInstallObject@@SAPEBGXZ; CWbemInstallObject::GetRegistryPathCIMOM(void)
0x18007075c  mov     rdi, rax
0x18007075f  call    cs:__imp_?GetRegistryPathRoot@CWbemInstallObject@@SAPEAUHKEY__@@XZ; CWbemInstallObject::GetRegistryPathRoot(void)
0x180070765  lea     rcx, [rbp+57h+hKey]
0x180070769  mov     [rsp+0D0h+phkResult], rcx
0x18007076e  mov     rdx, rdi
0x180070771  mov     rcx, rax
0x180070774  jmp     short loc_18007078D
0x180070776  lea     rax, [rbp+57h+hKey]
0x18007077a  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18007077f  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\WBEM\\CIMOM"
0x180070786  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007078d  mov     r9d, 2001Fh; samDesired
0x180070793  xor     r8d, r8d; ulOptions
0x180070796  call    cs:__imp_RegOpenKeyExW
0x18007079c  test    eax, eax
0x18007079e  jz      short loc_1800707B2
0x1800707a0  mov     edi, eax
0x1800707a2  lea     rcx, [rbp+57h+var_58]; this
0x1800707a6  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800707ab  mov     eax, edi
0x1800707ad  jmp     loc_180070898
0x1800707b2  mov     rax, [rbp+57h+hKey]
0x1800707b6  mov     [rbp+57h+var_50], rax
0x1800707ba  mov     edi, 4
0x1800707bf  mov     [rbp+57h+cbData], edi
0x1800707c2  lea     rax, [rbp+57h+cbData]
0x1800707c6  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x1800707cb  lea     rax, [rbp+57h+Data]
0x1800707cf  mov     [rsp+0D0h+phkResult], rax; lpData
0x1800707d4  xor     r9d, r9d; lpType
0x1800707d7  xor     r8d, r8d; lpReserved
0x1800707da  lea     rdx, ValueName; "Max Class Cache Size"
0x1800707e1  mov     rcx, [rbp+57h+hKey]; hKey
0x1800707e5  call    cs:__imp_RegQueryValueExW
0x1800707eb  test    eax, eax
0x1800707ed  jz      short loc_18007081A
0x1800707ef  mov     dword ptr [rbp+57h+Data], 4C4B40h
0x1800707f6  mov     dword ptr [rsp+0D0h+lpcbData], edi; cbData
0x1800707fa  lea     rax, [rbp+57h+Data]
0x1800707fe  mov     [rsp+0D0h+phkResult], rax; lpData
0x180070803  mov     r9d, edi; dwType
0x180070806  xor     r8d, r8d; Reserved
0x180070809  lea     rdx, ValueName; "Max Class Cache Size"
0x180070810  mov     rcx, [rbp+57h+hKey]; hKey
0x180070814  call    cs:__imp_RegSetValueExW
0x18007081a  mov     rcx, cs:?m_pEseController@CRepository@@0PEAUIWmiDbController@@EA; IWmiDbController * CRepository::m_pEseController
0x180070821  mov     rax, [rcx]
0x180070824  mov     edx, dword ptr [rbp+57h+Data]
0x180070827  mov     rax, [rax+40h]
0x18007082b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070830  nop
0x180070831  lea     rcx, [rbp+57h+var_50]; this
0x180070835  call    ??1CRegCloseMe@@QEAA@XZ; CRegCloseMe::~CRegCloseMe(void)
0x18007083a  jmp     short loc_18007084D
0x18007083c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180070842  mov     edx, esi
0x180070844  mov     rcx, rax
0x180070847  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007084d  mov     rcx, cs:WPP_GLOBAL_Control
0x180070854  cmp     rcx, r12
0x180070857  jz      short loc_18007087A
0x180070859  test    byte ptr [rcx+1Ch], 1
0x18007085d  jz      short loc_18007087A
0x18007085f  cmp     byte ptr [rcx+19h], 2
0x180070863  jb      short loc_18007087A
0x180070865  mov     edx, 13h
0x18007086a  mov     r9d, esi
0x18007086d  mov     r8, r13
0x180070870  mov     rcx, [rcx+10h]
0x180070874  call    WPP_SF_d
0x180070879  nop
0x18007087a  test    rbx, rbx
0x18007087d  jz      short loc_18007088E
0x18007087f  mov     rax, [rbx]
0x180070882  mov     rcx, rbx
0x180070885  mov     rax, [rax+10h]
0x180070889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007088e  mov     [rbp+57h+var_58], 0
0x180070896  mov     eax, esi
0x180070898  mov     rcx, [rbp+57h+var_38]
0x18007089c  xor     rcx, rsp; StackCookie
0x18007089f  call    __security_check_cookie
0x1800708a4  add     rsp, 0A8h
0x1800708ab  pop     r13
0x1800708ad  pop     r12
0x1800708af  pop     rdi
0x1800708b0  pop     rsi
0x1800708b1  pop     rbx
0x1800708b2  pop     rbp
0x1800708b3  retn
```
