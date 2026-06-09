# CHardwareManager::Initialize(SERVICE_STATUS_HANDLE__ *)

- ea: `0x180045044`
- end: `0x1800456bb`
- name: `?Initialize@CHardwareManager@@SAXPEAUSERVICE_STATUS_HANDLE__@@@Z`
- size: `1655`
- prototype: `void __fastcall(struct SERVICE_STATUS_HANDLE__ *)`
- caller_count: `2`
- callee_count: `36`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001d378`
- `0x1800515c8`

## callees

- `0x180001314`
- `0x1800050e0`
- `0x1800055cc`
- `0x1800119c4`
- `0x180014110`
- `0x180014854`
- `0x180014894`
- `0x180023d88`
- `0x18002a5e4`
- `0x18002d3b4`
- `0x1800305f4`
- `0x180035d78`
- `0x18003c780`
- `0x18003f2dc`
- `0x18003f4b8`
- `0x180044b1c`
- `0x180044e74`
- `0x180045044`
- `0x180045a4c`
- `0x180051030`
- `0x180055878`
- `0x1800559c8`
- `0x180055f74`
- `0x180056378`
- `0x1800605a4`
- `0x180068f60`
- `0x180069cd4`
- `0x18006a20c`
- `0x18006e4c4`
- `0x180071de8`
- `0x180072410`
- `0x180072d58`
- `0x1800760f0`
- `0x1800b5134`
- `0x1800b53e4`
- `0x1800be44c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800455c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800455c3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180045590`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180045590`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800452dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800452dd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800452b1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800452b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045265`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045265`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x180045562`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x180045562`
- `ext-ms-win-biometrics-winbio-l1-2-0!WinBioIsLegacy` at `0x1800450a0`
- `ext-ms-win-biometrics-winbio-l1-2-0!WinBioIsLegacy` at `0x1800450a0`

## string_xrefs

- `0x18004508a`: `onecore\ds\security\biometrics\service\server\hardwaremanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CHardwareManager::Initialize(struct SERVICE_STATUS_HANDLE__ *a1)
{
  struct CHardwareManager *v2; // rax
  struct CHardwareManager *v3; // rax
  int IsSecureBioAvailable; // eax
  int v5; // edi
  int exists; // eax
  int v7; // ebx
  struct CHardwareManager *v8; // rax
  struct CHardwareManager *v9; // rax
  struct CHardwareManager *v10; // rax
  struct CHardwareManager *v11; // rax
  int WinBioRegistryLocation; // eax
  const WCHAR *v13; // rax
  PHKEY v14; // r8
  unsigned int v15; // eax
  wil::details::in1diag3 *v16; // rcx
  __int64 v17; // rdx
  struct CHardwareManager *v18; // rax
  int v19; // ebx
  struct CHardwareManager *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  struct CHardwareManager *v24; // rax
  int v25; // eax
  struct CHardwareManager *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // r8
  struct CHardwareManager *v29; // rax
  __int64 v30; // r9
  __int64 v31; // rcx
  __int64 v32; // rcx
  int v33; // r8d
  int BIPATimersForAllUsers; // eax
  struct handle_thread *v35; // rbx
  struct CHardwareManager *v36; // rax
  HANDLE IoCompletionPort; // rbx
  __int64 v38; // r9
  CHardwareManager *v39; // rax
  int v40; // r8d
  struct CHardwareManager *v41; // rax
  HKEY *phkResult; // [rsp+20h] [rbp-E0h]
  BYTE Data[8]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v45[4]; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID pExceptionObject[2]; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v47[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v48[360]; // [rsp+A0h] [rbp-60h] BYREF
  int v49; // [rsp+208h] [rbp+108h]
  __int16 v50; // [rsp+244h] [rbp+144h]
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  CHardwareManager::Instance();
  *((_QWORD *)CHardwareManager::Instance() + 8) = a1;
  if ( !(unsigned __int8)IsWinBioIsLegacyPresent() || !(unsigned int)WinBioIsLegacy() )
    goto LABEL_46;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
  {
    CHardwareManager::Instance();
    CHardwareManager::InitializeSecureBioAvailability();
    goto LABEL_46;
  }
  v2 = CHardwareManager::Instance();
  *((_WORD *)v2 + 105) |= 1u;
  v3 = CHardwareManager::Instance();
  IsSecureBioAvailable = BioTrustlet::IsSecureBioAvailable((unsigned __int16 *)v3 + 105);
  v5 = IsSecureBioAvailable;
  if ( IsSecureBioAvailable < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
      (const char *)(unsigned int)IsSecureBioAvailable,
      (int)phkResult);
  LOBYTE(hKey) = 1;
  exists = CHardwareManager::ExistsNgcVtl0Container((bool *)&hKey);
  v7 = exists;
  if ( exists < 0 )
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0xBB,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
      (const char *)(unsigned int)exists,
      (int)phkResult);
    v5 = v7;
  }
  if ( (_BYTE)hKey )
  {
    v8 = CHardwareManager::Instance();
    *((_WORD *)v8 + 105) &= ~1u;
    v9 = CHardwareManager::Instance();
    *((_WORD *)v9 + 105) |= 0x40u;
  }
  if ( *((int *)CHardwareManager::Instance() + 39) >= 3 )
  {
    v10 = CHardwareManager::Instance();
    *((_WORD *)v10 + 105) |= 0x20u;
    v11 = CHardwareManager::Instance();
    *((_WORD *)v11 + 105) &= ~1u;
  }
  if ( (unsigned int)dword_18010F170 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18010F170, 0x400000000000LL) )
  {
    *(_QWORD *)&pExceptionObject[0].Data1 = 50331648;
    *(_DWORD *)Data = v5;
    LOWORD(hKey) = *((_WORD *)CHardwareManager::Instance() + 105);
    phkResult = &hKey;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (unsigned __int16)hKey,
      (__int64)byte_1800ECFB5);
  }
  v47[0] = 0;
  v47[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v47[0]) = 0;
  WinBioRegistryLocation = GetWinBioRegistryLocation((__int64)v47);
  if ( WinBioRegistryLocation < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
      (const char *)(unsigned int)WinBioRegistryLocation,
      (int)phkResult);
    goto LABEL_25;
  }
  hKey = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v47);
  v15 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v13, 0, 0x2001Fu, v14);
  v16 = retaddr;
  if ( v15 )
  {
    v17 = 226;
  }
  else
  {
    *(_DWORD *)Data = *((unsigned __int16 *)CHardwareManager::Instance() + 105);
    v15 = RegSetValueExW(hKey, L"SecureBioAvailabilityInCensus", 0, 4u, Data, 4u);
    v16 = retaddr;
    if ( !v15 )
      goto LABEL_23;
    v17 = 238;
  }
  wil::details::in1diag3::_Log_Win32(
    v16,
    (void *)v17,
    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
    (const char *)v15,
    (unsigned int)phkResult);
LABEL_23:
  if ( hKey )
    RegCloseKey(hKey);
LABEL_25:
  if ( (*((_BYTE *)CHardwareManager::Instance() + 210) & 1) != 0 )
  {
    *((_BYTE *)CHardwareManager::Instance() + 152) = 1;
    v18 = CHardwareManager::Instance();
    v19 = BioTrustlet::Start((struct CHardwareManager *)((char *)v18 + 88));
    if ( v19 >= 0 )
    {
      v20 = CHardwareManager::Instance();
      v19 = BioTrustlet::WaitForTrustletStarted((void **)v20 + 11, v21, v22, v23, (unsigned int)phkResult);
      if ( v19 >= 0 )
      {
        v24 = CHardwareManager::Instance();
        v19 = BioTrustlet::ServerBind((struct CHardwareManager *)((char *)v24 + 88));
        if ( v19 >= 0 )
        {
          pExceptionObject[0] = *(struct _GUID *)&xmmword_1800DF158;
          v25 = StorageManagerImport(pExceptionObject);
          if ( v25 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x102,
              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
              (const char *)(unsigned int)v25,
              (int)phkResult);
        }
      }
    }
    CEtwEvent::CEtwEvent((CEtwEvent *)v48);
    v49 = v19;
    if ( v19 < 0 )
    {
      if ( (unsigned __int64)(*((_QWORD *)CHardwareManager::Instance() + 16) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        v29 = CHardwareManager::Instance();
        BioTrustlet::Terminate((struct CHardwareManager *)((char *)v29 + 88));
      }
      v50 = *((_WORD *)CHardwareManager::Instance() + 105);
      CEtwEvent::Write(v48, 1600, 1);
      if ( (unsigned int)dword_18010F170 > 2 )
      {
        *(_DWORD *)Data = v19;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_18010F170,
          (unsigned __int8 *)&unk_1800ECF80,
          0,
          v30,
          (__int64)Data);
      }
      v28 = 0;
    }
    else
    {
      CEtwEvent::Write(v48, 1601, 1);
      v26 = CHardwareManager::Instance();
      ++*((_DWORD *)v26 + 39);
      v28 = 1;
    }
    winbio::SetBioRegKeyValue(v27, 3, v28);
  }
  else
  {
    if ( (*((_BYTE *)CHardwareManager::Instance() + 210) & 1) != 0 )
      goto LABEL_42;
    CEtwEvent::CEtwEvent((CEtwEvent *)v48);
    v49 = -2147024846;
    v50 = *((_WORD *)CHardwareManager::Instance() + 105);
    CEtwEvent::Write(v48, 1600, 1);
    winbio::SetBioRegKeyValue(v32, 3, 0);
  }
  CEtwEvent::~CEtwEvent((CEtwEvent *)v48);
LABEL_42:
  v45[0] = 0;
  winbio::GetBioRegKeyValue(v31, 3, v45);
  if ( (unsigned int)dword_18010F170 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18010F170, 0x400000000000LL) )
  {
    *(_QWORD *)&pExceptionObject[0].Data1 = 50331648;
    *(_DWORD *)Data = v45[0];
    LODWORD(hKey) = v33;
    phkResult = &hKey;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (__int64)&dword_18010F170,
      (__int64)&byte_1800ECF3F);
  }
  std::wstring::_Tidy_deallocate(v47);
LABEL_46:
  BIPATimersForAllUsers = CHardwareManager::CreateBIPATimersForAllUsers();
  if ( BIPATimersForAllUsers < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x13F,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
      (const char *)(unsigned int)BIPATimersForAllUsers,
      (int)phkResult);
  v35 = (struct CHardwareManager *)((char *)CHardwareManager::Instance() + 56);
  v36 = CHardwareManager::Instance();
  if ( CThread::Create(hardwareMonitorThreadRoutine, v36, v35) < 0 )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
    throw (std::bad_alloc *)pExceptionObject;
  }
  IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 1u);
  *((_QWORD *)CHardwareManager::Instance() + 6) = IoCompletionPort;
  if ( !*((_QWORD *)CHardwareManager::Instance() + 6) )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
    throw (std::bad_alloc *)pExceptionObject;
  }
  pti = CreateThreadpoolTimer(CHardwareManager::WbioBoostTimerCallBack, 0, 0);
  if ( !pti && (unsigned int)dword_18010F170 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18010F170, 0x400000000000LL) )
  {
    *(_DWORD *)Data = GetLastError();
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18010F170,
      (unsigned __int8 *)byte_1800ECF0B,
      0,
      v38,
      (__int64)Data);
  }
  v39 = CHardwareManager::Instance();
  if ( (int)CHardwareManager::RegisterConnectedStandByExitNotification(v39) < 0
    && (unsigned int)dword_18010F170 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_18010F170, 0x400000000000LL) )
  {
    *(_QWORD *)&pExceptionObject[0].Data1 = 50331648;
    *(_DWORD *)Data = v40;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (__int64)&dword_18010F170,
      (unsigned __int8 *)byte_1800ECEB9,
      0,
      0,
      (__int64)Data,
      (__int64)pExceptionObject);
  }
  v41 = CHardwareManager::Instance();
  handle_thread::Start((struct CHardwareManager *)((char *)v41 + 56));
}

```

## disassembly

```asm
0x180045044  push    rbp
0x180045046  push    rbx
0x180045047  push    rdi
0x180045048  push    r12
0x18004504a  push    r14
0x18004504c  push    r15
0x18004504e  lea     rbp, [rsp-1C8h]
0x180045056  sub     rsp, 2C8h
0x18004505d  mov     rax, cs:__security_cookie
0x180045064  xor     rax, rsp
0x180045067  mov     [rbp+1F0h+var_40], rax
0x18004506e  mov     rbx, rcx
0x180045071  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180045076  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x18004507b  mov     [rax+40h], rbx
0x18004507f  call    IsWinBioIsLegacyPresent
0x180045084  mov     r14d, 1
0x18004508a  lea     r12, aOnecoreDsSecur_25; "onecore\\ds\\security\\biometrics\\serv"...
0x180045091  lea     r15, dword_18010F170
0x180045098  test    al, al
0x18004509a  jz      loc_18004550E
0x1800450a0  call    cs:__imp_WinBioIsLegacy
0x1800450a6  test    eax, eax
0x1800450a8  jz      loc_18004550E
0x1800450ae  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x1800450b5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x1800450ba  test    al, al
0x1800450bc  jz      short loc_1800450CD
0x1800450be  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800450c3  call    ?InitializeSecureBioAvailability@CHardwareManager@@SAXXZ; CHardwareManager::InitializeSecureBioAvailability(void)
0x1800450c8  jmp     loc_18004550E
0x1800450cd  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800450d2  or      [rax+0D2h], r14w
0x1800450da  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800450df  lea     rcx, [rax+0D2h]; unsigned __int16 *
0x1800450e6  call    ?IsSecureBioAvailable@BioTrustlet@@SAJAEAG@Z; BioTrustlet::IsSecureBioAvailable(ushort &)
0x1800450eb  mov     edi, eax
0x1800450ed  mov     rcx, [rbp+1F8h]; this
0x1800450f4  test    eax, eax
0x1800450f6  jns     short loc_180045108
0x1800450f8  mov     r9d, eax; char *
0x1800450fb  mov     r8, r12; unsigned int
0x1800450fe  mov     edx, 0B3h; void *
0x180045103  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180045108  mov     byte ptr [rsp+2F0h+hKey], r14b
0x18004510d  lea     rcx, [rsp+2F0h+hKey]; bool *
0x180045112  call    ?ExistsNgcVtl0Container@CHardwareManager@@SAJPEA_N@Z; CHardwareManager::ExistsNgcVtl0Container(bool *)
0x180045117  mov     ebx, eax
0x180045119  test    eax, eax
0x18004511b  jns     short loc_180045136
0x18004511d  mov     rcx, [rbp+1F8h]; this
0x180045124  mov     r9d, eax; char *
0x180045127  mov     r8, r12; unsigned int
0x18004512a  mov     edx, 0BBh; void *
0x18004512f  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180045134  mov     edi, ebx
0x180045136  mov     ebx, 0FFFEh
0x18004513b  cmp     byte ptr [rsp+2F0h+hKey], 0
0x180045140  jz      short loc_18004515B
0x180045142  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180045147  and     [rax+0D2h], bx
0x18004514e  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180045153  or      word ptr [rax+0D2h], 40h
0x18004515b  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180045160  cmp     dword ptr [rax+9Ch], 3
0x180045167  jl      short loc_180045182
0x180045169  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x18004516e  or      word ptr [rax+0D2h], 20h
0x180045176  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x18004517b  and     [rax+0D2h], bx
0x180045182  mov     eax, cs:dword_18010F170
0x180045188  cmp     eax, 5
0x18004518b  jbe     short loc_1800451EB
0x18004518d  mov     rdx, 400000000000h
0x180045197  mov     rcx, r15
0x18004519a  call    _tlgKeywordOn
0x18004519f  test    al, al
0x1800451a1  jz      short loc_1800451EB
0x1800451a3  mov     qword ptr [rsp+2F0h+pExceptionObject], 3000000h
0x1800451ac  mov     dword ptr [rsp+2F0h+Data], edi
0x1800451b0  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800451b5  movzx   ecx, word ptr [rax+0D2h]
0x1800451bc  mov     word ptr [rsp+2F0h+hKey], cx
0x1800451c1  lea     rax, [rsp+2F0h+pExceptionObject]
0x1800451c6  mov     [rsp+2F0h+var_2C0], rax
0x1800451cb  lea     rax, [rsp+2F0h+Data]
0x1800451d0  mov     qword ptr [rsp+2F0h+cbData], rax
0x1800451d5  lea     rax, [rsp+2F0h+hKey]
0x1800451da  mov     [rsp+2F0h+phkResult], rax; int
0x1800451df  lea     rdx, byte_1800ECFB5
0x1800451e6  call    ??$Write@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800451eb  xorps   xmm0, xmm0
0x1800451ee  movups  [rbp+1F0h+var_270], xmm0
0x1800451f2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800451fa  movdqu  [rbp+1F0h+var_260], xmm1
0x1800451ff  xor     eax, eax
0x180045201  mov     word ptr [rbp+1F0h+var_270], ax
0x180045205  lea     rcx, [rbp+1F0h+var_270]
0x180045209  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x18004520e  mov     rcx, [rbp+1F8h]; this
0x180045215  test    eax, eax
0x180045217  jns     short loc_18004522E
0x180045219  mov     r9d, eax; char *
0x18004521c  mov     r8, r12; unsigned int
0x18004521f  mov     edx, 0D6h; void *
0x180045224  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180045229  jmp     loc_1800452E3
0x18004522e  mov     [rsp+2F0h+hKey], 0
0x180045237  lea     rcx, [rsp+2F0h+hKey]
0x18004523c  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180045241  mov     r8, rax
0x180045244  lea     rcx, [rbp+1F0h+var_270]
0x180045248  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004524d  mov     rdx, rax; lpSubKey
0x180045250  mov     [rsp+2F0h+phkResult], r8; phkResult
0x180045255  mov     r9d, 2001Fh; samDesired
0x18004525b  xor     r8d, r8d; ulOptions
0x18004525e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180045265  call    cs:__imp_RegOpenKeyExW
0x18004526b  mov     rcx, [rbp+1F8h]
0x180045272  test    eax, eax
0x180045274  jz      short loc_18004527D
0x180045276  mov     edx, 0E2h
0x18004527b  jmp     short loc_1800452C7
0x18004527d  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180045282  movzx   ecx, word ptr [rax+0D2h]
0x180045289  mov     dword ptr [rsp+2F0h+Data], ecx
0x18004528d  mov     r9d, 4; dwType
0x180045293  mov     [rsp+2F0h+cbData], r9d; cbData
0x180045298  lea     rax, [rsp+2F0h+Data]
0x18004529d  mov     [rsp+2F0h+phkResult], rax; int
0x1800452a2  xor     r8d, r8d; Reserved
0x1800452a5  lea     rdx, aSecurebioavail; "SecureBioAvailabilityInCensus"
0x1800452ac  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1800452b1  call    cs:__imp_RegSetValueExW
0x1800452b7  mov     rcx, [rbp+1F8h]; this
0x1800452be  test    eax, eax
0x1800452c0  jz      short loc_1800452D3
0x1800452c2  mov     edx, 0EEh; void *
0x1800452c7  mov     r9d, eax; char *
0x1800452ca  mov     r8, r12; unsigned int
0x1800452cd  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800452d2  nop
0x1800452d3  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1800452d8  test    rcx, rcx
0x1800452db  jz      short loc_1800452E3
0x1800452dd  call    cs:__imp_RegCloseKey
0x1800452e3  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800452e8  test    [rax+0D2h], r14b
0x1800452ef  jz      loc_180045427
0x1800452f5  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800452fa  mov     [rax+98h], r14b
0x180045301  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180045306  lea     rcx, [rax+58h]; this
0x18004530a  call    ?Start@BioTrustlet@@QEAAJ_N@Z; BioTrustlet::Start(bool)
0x18004530f  mov     ebx, eax
0x180045311  test    eax, eax
0x180045313  js      short loc_18004536F
0x180045315  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x18004531a  lea     rcx, [rax+58h]; this
0x18004531e  call    ?WaitForTrustletStarted@BioTrustlet@@QEAAJK@Z; BioTrustlet::WaitForTrustletStarted(ulong)
0x180045323  mov     ebx, eax
0x180045325  test    eax, eax
0x180045327  js      short loc_18004536F
0x180045329  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x18004532e  lea     rcx, [rax+58h]; this
0x180045332  call    ?ServerBind@BioTrustlet@@QEAAJXZ; BioTrustlet::ServerBind(void)
0x180045337  mov     ebx, eax
0x180045339  test    eax, eax
0x18004533b  js      short loc_18004536F
0x18004533d  movups  xmm0, cs:xmmword_1800DF158
0x180045344  movdqu  [rsp+2F0h+pExceptionObject], xmm0
0x18004534a  lea     rcx, [rsp+2F0h+pExceptionObject]; struct _GUID
0x18004534f  call    ?StorageManagerImport@@YAJU_GUID@@@Z; StorageManagerImport(_GUID)
0x180045354  mov     rcx, [rbp+1F8h]; this
0x18004535b  test    eax, eax
0x18004535d  jns     short loc_18004536F
0x18004535f  mov     r9d, eax; char *
0x180045362  mov     r8, r12; unsigned int
0x180045365  mov     edx, 102h; void *
0x18004536a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004536f  lea     rcx, [rbp+1F0h+var_250]; this
0x180045373  call    ??0CEtwEvent@@QEAA@XZ; CEtwEvent::CEtwEvent(void)
0x180045378  nop
0x180045379  mov     [rbp+1F0h+var_E8], ebx
0x18004537f  test    ebx, ebx
0x180045381  js      short loc_1800453A5
0x180045383  mov     r8d, r14d
0x180045386  mov     edx, 641h
0x18004538b  lea     rcx, [rbp+1F0h+var_250]
0x18004538f  call    ?Write@CEtwEvent@@QEAAJKW4WBioEventLevel@@@Z; CEtwEvent::Write(ulong,WBioEventLevel)
0x180045394  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180045399  add     [rax+9Ch], r14d
0x1800453a0  mov     r8d, r14d
0x1800453a3  jmp     short loc_18004541A
0x1800453a5  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800453aa  mov     rcx, [rax+80h]
0x1800453b1  sub     rcx, r14
0x1800453b4  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800453b8  ja      short loc_1800453C8
0x1800453ba  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800453bf  lea     rcx, [rax+58h]; this
0x1800453c3  call    ?Terminate@BioTrustlet@@QEAAJXZ; BioTrustlet::Terminate(void)
0x1800453c8  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800453cd  movzx   ecx, word ptr [rax+0D2h]
0x1800453d4  mov     [rbp+1F0h+var_AC], cx
0x1800453db  mov     r8d, r14d
0x1800453de  mov     edx, 640h
0x1800453e3  lea     rcx, [rbp+1F0h+var_250]
0x1800453e7  call    ?Write@CEtwEvent@@QEAAJKW4WBioEventLevel@@@Z; CEtwEvent::Write(ulong,WBioEventLevel)
0x1800453ec  mov     eax, cs:dword_18010F170
0x1800453f2  cmp     eax, 2
0x1800453f5  jbe     short loc_180045417
0x1800453f7  mov     dword ptr [rsp+2F0h+Data], ebx
0x1800453fb  lea     rax, [rsp+2F0h+Data]
0x180045400  mov     [rsp+2F0h+phkResult], rax
0x180045405  xor     r8d, r8d
0x180045408  lea     rdx, unk_1800ECF80
0x18004540f  mov     rcx, r15
0x180045412  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180045417  xor     r8d, r8d
0x18004541a  mov     edx, 3
0x18004541f  call    ?SetBioRegKeyValue@winbio@@YAJPEAU_WINBIO_IDENTITY@@W4RegKeyName@1@K@Z; winbio::SetBioRegKeyValue(_WINBIO_IDENTITY *,winbio::RegKeyName,ulong)
0x180045424  nop
0x180045425  jmp     short loc_18004547A
0x180045427  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x18004542c  test    [rax+0D2h], r14b
0x180045433  jnz     short loc_180045483
0x180045435  lea     rcx, [rbp+1F0h+var_250]; this
0x180045439  call    ??0CEtwEvent@@QEAA@XZ; CEtwEvent::CEtwEvent(void)
0x18004543e  nop
0x18004543f  mov     [rbp+1F0h+var_E8], 80070032h
0x180045449  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x18004544e  movzx   ecx, word ptr [rax+0D2h]
0x180045455  mov     [rbp+1F0h+var_AC], cx
0x18004545c  mov     r8d, r14d
0x18004545f  mov     edx, 640h
0x180045464  lea     rcx, [rbp+1F0h+var_250]
0x180045468  call    ?Write@CEtwEvent@@QEAAJKW4WBioEventLevel@@@Z; CEtwEvent::Write(ulong,WBioEventLevel)
0x18004546d  xor     r8d, r8d
0x180045470  lea     edx, [r8+3]
0x180045474  call    ?SetBioRegKeyValue@winbio@@YAJPEAU_WINBIO_IDENTITY@@W4RegKeyName@1@K@Z; winbio::SetBioRegKeyValue(_WINBIO_IDENTITY *,winbio::RegKeyName,ulong)
0x180045479  nop
0x18004547a  lea     rcx, [rbp+1F0h+var_250]; this
0x18004547e  call    ??1CEtwEvent@@QEAA@XZ; CEtwEvent::~CEtwEvent(void)
0x180045483  mov     [rsp+2F0h+var_2A0], 0
0x18004548b  lea     r8, [rsp+2F0h+var_2A0]
0x180045490  mov     edx, 3
0x180045495  call    ?GetBioRegKeyValue@winbio@@YAJPEAU_WINBIO_IDENTITY@@W4RegKeyName@1@PEAK@Z; winbio::GetBioRegKeyValue(_WINBIO_IDENTITY *,winbio::RegKeyName,ulong *)
0x18004549a  mov     r8d, eax
0x18004549d  mov     ecx, cs:dword_18010F170
0x1800454a3  cmp     ecx, 5
0x1800454a6  jbe     short loc_180045505
0x1800454a8  mov     rdx, 400000000000h
0x1800454b2  mov     rcx, r15
0x1800454b5  call    _tlgKeywordOn
0x1800454ba  test    al, al
0x1800454bc  jz      short loc_180045505
0x1800454be  mov     qword ptr [rsp+2F0h+pExceptionObject], 3000000h
0x1800454c7  mov     ecx, [rsp+2F0h+var_2A0]
0x1800454cb  mov     dword ptr [rsp+2F0h+Data], ecx
0x1800454cf  mov     dword ptr [rsp+2F0h+hKey], r8d
0x1800454d4  lea     rax, [rsp+2F0h+pExceptionObject]
0x1800454d9  mov     [rsp+2F0h+var_2C0], rax
0x1800454de  lea     rax, [rsp+2F0h+Data]
0x1800454e3  mov     qword ptr [rsp+2F0h+cbData], rax
0x1800454e8  lea     rax, [rsp+2F0h+hKey]
0x1800454ed  mov     [rsp+2F0h+phkResult], rax; int
0x1800454f2  xor     r8d, r8d
0x1800454f5  lea     rdx, byte_1800ECF3F
0x1800454fc  mov     rcx, r15
0x1800454ff  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180045504  nop
0x180045505  lea     rcx, [rbp+1F0h+var_270]
0x180045509  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004550e  call    ?CreateBIPATimersForAllUsers@CHardwareManager@@CAJXZ; CHardwareManager::CreateBIPATimersForAllUsers(void)
0x180045513  test    eax, eax
0x180045515  jns     short loc_18004552E
0x180045517  mov     rcx, [rbp+1F8h]; this
0x18004551e  mov     r9d, eax; char *
0x180045521  mov     r8, r12; unsigned int
0x180045524  mov     edx, 13Fh; void *
0x180045529  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004552e  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180045533  lea     rbx, [rax+38h]
0x180045537  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x18004553c  mov     r8, rbx; struct handle_thread *
0x18004553f  mov     rdx, rax; void *
0x180045542  lea     rcx, _hardwareMonitorThreadRoutine; int (*)(struct thread_inside_functions *, void *)
0x180045549  call    ?Create@CThread@@SAJP6AJAEAVthread_inside_functions@@PEAX@Z1PEAVhandle_thread@@@Z; CThread::Create(long (*)(thread_inside_functions &,void *),void *,handle_thread *)
0x18004554e  test    eax, eax
0x180045550  js      loc_18004569F
0x180045556  mov     r9d, r14d; NumberOfConcurrentThreads
0x180045559  xor     r8d, r8d; CompletionKey
0x18004555c  xor     edx, edx; ExistingCompletionPort
0x18004555e  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x180045562  call    cs:__imp_CreateIoCompletionPort
0x180045568  mov     rbx, rax
0x18004556b  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180045570  mov     [rax+30h], rbx
  ... truncated ...
```
