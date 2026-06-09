# CIndexerAutomaticMaintenanceTask::s_HandlerThreadProc(void *)

- ea: `0x180018730`
- end: `0x180018a65`
- name: `?s_HandlerThreadProc@CIndexerAutomaticMaintenanceTask@@CAKPEAX@Z`
- size: `821`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `22`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005cc0`
- `0x18000d4dc`
- `0x180017050`
- `0x1800172d0`
- `0x18001754c`
- `0x180017650`
- `0x18001844c`
- `0x1800186c4`
- `0x180018730`
- `0x18001cb38`
- `0x18001fc24`
- `0x18001fc94`
- `0x18001fcd0`
- `0x1800201cc`
- `0x180020430`
- `0x1800204fc`
- `0x18002055c`
- `0x1800208ec`
- `0x18002c5b4`
- `0x18002c64c`
- `0x18002c7bc`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800187c5`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800187f0`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800187c5`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800187f0`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800189aa`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800189aa`

## string_xrefs

- `0x180018779`: `SetupCompletedSuccessfully`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CIndexerAutomaticMaintenanceTask::s_HandlerThreadProc(_QWORD *a1)
{
  int RegDwordOrString; // ebx
  HANDLE Event; // rcx
  unsigned int v4; // edx
  struct IGatherManagerAdmin3 *v5; // rdx
  CMSSAdmin *v6; // rcx
  unsigned int v7; // edx
  DWORD v8; // eax
  int v10; // [rsp+30h] [rbp-D0h] BYREF
  int v11; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v12; // [rsp+38h] [rbp-C8h] BYREF
  int v13; // [rsp+3Ch] [rbp-C4h] BYREF
  _DWORD v14[8]; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v15[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v16[32]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v17[14]; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE Handles[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v19; // [rsp+120h] [rbp+20h]

  v12 = 0;
  RegDwordOrString = GetRegDwordOrString(
                       HKEY_LOCAL_MACHINE,
                       L"SOFTWARE\\Microsoft\\Windows Search",
                       L"SetupCompletedSuccessfully",
                       4u,
                       &v12,
                       0);
  if ( RegDwordOrString >= 0 && v12 == 1 )
  {
    *(_OWORD *)Handles = 0;
    v19 = a1[15];
    Handles[0] = CreateEventExW(0, 0, 0, 0x1F0003u);
    if ( Handles[0] || (RegDwordOrString = ResultFromKnownLastError(), RegDwordOrString >= 0) )
    {
      Event = CreateEventExW(0, 0, 0, 0x1F0003u);
      Handles[1] = Event;
      if ( Event )
      {
        RegDwordOrString = 0;
      }
      else
      {
        RegDwordOrString = ResultFromKnownLastError();
        Event = Handles[1];
      }
      if ( RegDwordOrString >= 0 )
      {
        v17[11] = 0;
        v17[0] = &CServiceMonitorCPL::`vftable';
        v17[12] = Handles[0];
        v17[13] = Event;
        RegDwordOrString = CServiceMonitorBase::InitializeServiceListening((CServiceMonitorBase *)v17, L"WSearch");
        if ( RegDwordOrString >= 0 )
        {
          if ( (unsigned int)CServiceMonitorBase::IsServiceRunning((CServiceMonitorBase *)v17) )
          {
            memset(v15, 0, sizeof(v15));
            CRPCTimeout::CRPCTimeout((CRPCTimeout *)v16, v4);
            RegDwordOrString = CMSSAdmin::InitGatherAdmin((CMSSAdmin *)v15, v5);
            v10 = RegDwordOrString;
            if ( RegDwordOrString >= 0 )
            {
              RegDwordOrString = CMSSAdmin::InitIndexerPlugin((CMSSAdmin *)v15);
              v10 = RegDwordOrString;
              if ( RegDwordOrString >= 0 )
              {
                v10 = 0;
                RegDwordOrString = CMSSAdmin::GetNumberOfIndexedDocs((CMSSAdmin *)v15, &v10);
                v10 = RegDwordOrString;
              }
            }
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56280751>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56280751>::GetImpl'::`2'::impl) )
              CMSSAdmin::TriggerStoreAppUsageReport(v6);
            CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)v16);
            v13 = 13;
            v11 = 0;
            SearchOptionsTelemetry::IndexerAMTaskState<enum INDEXER_AM_TASK_STATE,long &,enum INDEXER_STATE>(
              &v11,
              &v10,
              &v13);
            while ( RegDwordOrString >= 0 )
            {
              CMSSearchServiceState::CMSSearchServiceState((CMSSearchServiceState *)v14);
              CRPCTimeout::CRPCTimeout((CRPCTimeout *)v16, v7);
              RegDwordOrString = CMSSAdmin::GetIndexerState((CMSSAdmin *)v15, (struct CMSSearchServiceState *)v14, 1u);
              v10 = RegDwordOrString;
              CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)v16);
              v11 = 1;
              SearchOptionsTelemetry::IndexerAMTaskState<enum INDEXER_AM_TASK_STATE,long &,enum INDEXER_STATE &>(
                &v11,
                &v10,
                v14);
              if ( RegDwordOrString >= 0 )
              {
                if ( !v14[0] || v14[0] == 3 )
                {
                  v11 = 3;
                  SearchOptionsTelemetry::IndexerAMTaskState<enum INDEXER_AM_TASK_STATE,long &,enum INDEXER_STATE &>(
                    &v11,
                    &v10,
                    v14);
LABEL_26:
                  CMSSearchServiceState::~CMSSearchServiceState((CMSSearchServiceState *)v14);
                  break;
                }
                v11 = 2;
                SearchOptionsTelemetry::IndexerAMTaskState<enum INDEXER_AM_TASK_STATE,long &,enum INDEXER_STATE &>(
                  &v11,
                  &v10,
                  v14);
                v8 = WaitForMultipleObjectsEx(3u, Handles, 0, 0xEA60u, 0);
                if ( v8 == -1 )
                {
                  RegDwordOrString = ResultFromKnownLastError();
                }
                else if ( v8 != 258 )
                {
                  goto LABEL_26;
                }
              }
              CMSSearchServiceState::~CMSSearchServiceState((CMSSearchServiceState *)v14);
            }
            CMSSAdmin::~CMSSAdmin((CMSSAdmin *)v15);
          }
          CServiceMonitorBase::UninitializeServiceListening((CServiceMonitorBase *)v17);
        }
        SafeCloseHandle(&Handles[1]);
      }
      SafeCloseHandle(Handles);
    }
  }
  (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)a1[13] + 32LL))(a1[13], (unsigned int)RegDwordOrString);
  (*(void (__fastcall **)(_QWORD *))(*a1 + 16LL))(a1);
  return 0;
}

```

## disassembly

```asm
0x180018730  mov     [rsp-8+arg_8], rbx
0x180018735  mov     [rsp-8+arg_10], rdi
0x18001873a  push    rbp
0x18001873b  lea     rbp, [rsp-30h]
0x180018740  sub     rsp, 130h
0x180018747  mov     rax, cs:__security_cookie
0x18001874e  xor     rax, rsp
0x180018751  mov     [rbp+30h+var_8], rax
0x180018755  mov     rdi, rcx
0x180018758  mov     [rsp+130h+var_F8], 0
0x180018760  mov     [rsp+130h+var_108], 0; unsigned __int16 **
0x180018769  lea     rax, [rsp+130h+var_F8]
0x18001876e  mov     qword ptr [rsp+130h+bAlertable], rax; unsigned int *
0x180018773  mov     r9d, 4; unsigned int
0x180018779  lea     r8, aSetupcompleted; "SetupCompletedSuccessfully"
0x180018780  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows Search"
0x180018787  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001878e  call    ?GetRegDwordOrString@@YAJPEAUHKEY__@@PEBG1KPEAKPEAPEAG@Z; GetRegDwordOrString(HKEY__ *,ushort const *,ushort const *,ulong,ulong *,ushort * *)
0x180018793  mov     ebx, eax
0x180018795  test    eax, eax
0x180018797  js      loc_180018A21
0x18001879d  cmp     [rsp+130h+var_F8], 1
0x1800187a2  jnz     loc_180018A21
0x1800187a8  xorps   xmm0, xmm0
0x1800187ab  movdqu  xmmword ptr [rbp+30h+Handles], xmm0
0x1800187b0  mov     rax, [rdi+78h]
0x1800187b4  mov     [rbp+30h+var_10], rax
0x1800187b8  mov     r9d, 1F0003h; dwDesiredAccess
0x1800187be  xor     r8d, r8d; dwFlags
0x1800187c1  xor     edx, edx; lpName
0x1800187c3  xor     ecx, ecx; lpEventAttributes
0x1800187c5  call    cs:__imp_CreateEventExW
0x1800187cb  mov     [rbp+30h+Handles], rax
0x1800187cf  test    rax, rax
0x1800187d2  jnz     short loc_1800187E3
0x1800187d4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800187d9  mov     ebx, eax
0x1800187db  test    eax, eax
0x1800187dd  js      loc_180018A21
0x1800187e3  mov     r9d, 1F0003h; dwDesiredAccess
0x1800187e9  xor     r8d, r8d; dwFlags
0x1800187ec  xor     edx, edx; lpName
0x1800187ee  xor     ecx, ecx; lpEventAttributes
0x1800187f0  call    cs:__imp_CreateEventExW
0x1800187f6  mov     rcx, rax
0x1800187f9  mov     [rbp+30h+Handles+8], rax
0x1800187fd  test    rax, rax
0x180018800  jnz     short loc_18001880F
0x180018802  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180018807  mov     ebx, eax
0x180018809  mov     rcx, [rbp+30h+Handles+8]
0x18001880d  jmp     short loc_180018811
0x18001880f  xor     ebx, ebx
0x180018811  test    ebx, ebx
0x180018813  js      loc_180018A18
0x180018819  mov     [rbp+30h+var_38], 0
0x180018821  lea     rax, ??_7CServiceMonitorCPL@@6B@; const CServiceMonitorCPL::`vftable'
0x180018828  mov     [rbp+30h+var_90], rax
0x18001882c  mov     rax, [rbp+30h+Handles]
0x180018830  mov     [rbp+30h+var_30], rax
0x180018834  mov     [rbp+30h+var_28], rcx
0x180018838  lea     rdx, ServiceName; "WSearch"
0x18001883f  lea     rcx, [rbp+30h+var_90]; this
0x180018843  call    ?InitializeServiceListening@CServiceMonitorBase@@QEAAJPEBG@Z; CServiceMonitorBase::InitializeServiceListening(ushort const *)
0x180018848  mov     ebx, eax
0x18001884a  test    eax, eax
0x18001884c  js      loc_180018A0F
0x180018852  lea     rcx, [rbp+30h+var_90]; this
0x180018856  call    ?IsServiceRunning@CServiceMonitorBase@@QEAAHXZ; CServiceMonitorBase::IsServiceRunning(void)
0x18001885b  test    eax, eax
0x18001885d  jz      loc_180018A06
0x180018863  xorps   xmm0, xmm0
0x180018866  movdqu  [rsp+130h+var_D0], xmm0
0x18001886c  xorps   xmm1, xmm1
0x18001886f  movdqu  [rsp+130h+var_C0], xmm1
0x180018875  lea     rcx, [rbp+30h+var_B0]; this
0x180018879  call    ??0CRPCTimeout@@QEAA@K@Z; CRPCTimeout::CRPCTimeout(ulong)
0x18001887e  nop
0x18001887f  lea     rcx, [rsp+130h+var_D0]; this
0x180018884  call    ?InitGatherAdmin@CMSSAdmin@@QEAAJPEAUIGatherManagerAdmin3@@@Z; CMSSAdmin::InitGatherAdmin(IGatherManagerAdmin3 *)
0x180018889  mov     ebx, eax
0x18001888b  mov     [rsp+130h+var_100], eax
0x18001888f  test    eax, eax
0x180018891  js      short loc_1800188C4
0x180018893  lea     rcx, [rsp+130h+var_D0]; this
0x180018898  call    ?InitIndexerPlugin@CMSSAdmin@@QEAAJXZ; CMSSAdmin::InitIndexerPlugin(void)
0x18001889d  mov     ebx, eax
0x18001889f  mov     [rsp+130h+var_100], eax
0x1800188a3  test    eax, eax
0x1800188a5  js      short loc_1800188C4
0x1800188a7  mov     [rsp+130h+var_100], 0
0x1800188af  lea     rdx, [rsp+130h+var_100]; int *
0x1800188b4  lea     rcx, [rsp+130h+var_D0]; this
0x1800188b9  call    ?GetNumberOfIndexedDocs@CMSSAdmin@@QEAAJPEAH@Z; CMSSAdmin::GetNumberOfIndexedDocs(int *)
0x1800188be  mov     ebx, eax
0x1800188c0  mov     [rsp+130h+var_100], eax
0x1800188c4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56280751@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56280751@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56280751> `wil::Feature<__WilFeatureTraits_Feature_56280751>::GetImpl(void)'::`2'::impl
0x1800188cb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56280751@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56280751>::__private_IsEnabled(void)
0x1800188d0  test    al, al
0x1800188d2  jnz     short loc_1800188DA
0x1800188d4  call    ?TriggerStoreAppUsageReport@CMSSAdmin@@QEAAXXZ; CMSSAdmin::TriggerStoreAppUsageReport(void)
0x1800188d9  nop
0x1800188da  lea     rcx, [rbp+30h+var_B0]; this
0x1800188de  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x1800188e3  mov     [rsp+130h+var_F4], 0Dh
0x1800188eb  mov     [rsp+130h+var_FC], 0
0x1800188f3  lea     r8, [rsp+130h+var_F4]
0x1800188f8  lea     rdx, [rsp+130h+var_100]
0x1800188fd  lea     rcx, [rsp+130h+var_FC]
0x180018902  call    ??$IndexerAMTaskState@W4INDEXER_AM_TASK_STATE@@AEAJW4INDEXER_STATE@@@SearchOptionsTelemetry@@SAX$$QEAW4INDEXER_AM_TASK_STATE@@AEAJ$$QEAW4INDEXER_STATE@@@Z; SearchOptionsTelemetry::IndexerAMTaskState<INDEXER_AM_TASK_STATE,long &,INDEXER_STATE>(INDEXER_AM_TASK_STATE &&,long &,INDEXER_STATE &&)
0x180018907  test    ebx, ebx
0x180018909  js      loc_1800189FC
0x18001890f  lea     rcx, [rsp+130h+var_F0]; this
0x180018914  call    ??0CMSSearchServiceState@@QEAA@XZ; CMSSearchServiceState::CMSSearchServiceState(void)
0x180018919  nop
0x18001891a  lea     rcx, [rbp+30h+var_B0]; this
0x18001891e  call    ??0CRPCTimeout@@QEAA@K@Z; CRPCTimeout::CRPCTimeout(ulong)
0x180018923  nop
0x180018924  mov     r8d, 1; unsigned int
0x18001892a  lea     rdx, [rsp+130h+var_F0]; struct CMSSearchServiceState *
0x18001892f  lea     rcx, [rsp+130h+var_D0]; this
0x180018934  call    ?GetIndexerState@CMSSAdmin@@QEAAJPEAVCMSSearchServiceState@@K@Z; CMSSAdmin::GetIndexerState(CMSSearchServiceState *,ulong)
0x180018939  mov     ebx, eax
0x18001893b  mov     [rsp+130h+var_100], eax
0x18001893f  lea     rcx, [rbp+30h+var_B0]; this
0x180018943  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x180018948  mov     [rsp+130h+var_FC], 1
0x180018950  lea     r8, [rsp+130h+var_F0]
0x180018955  lea     rdx, [rsp+130h+var_100]
0x18001895a  lea     rcx, [rsp+130h+var_FC]
0x18001895f  call    ??$IndexerAMTaskState@W4INDEXER_AM_TASK_STATE@@AEAJAEAW4INDEXER_STATE@@@SearchOptionsTelemetry@@SAX$$QEAW4INDEXER_AM_TASK_STATE@@AEAJAEAW4INDEXER_STATE@@@Z; SearchOptionsTelemetry::IndexerAMTaskState<INDEXER_AM_TASK_STATE,long &,INDEXER_STATE &>(INDEXER_AM_TASK_STATE &&,long &,INDEXER_STATE &)
0x180018964  test    ebx, ebx
0x180018966  js      short loc_1800189C5
0x180018968  mov     eax, [rsp+130h+var_F0]
0x18001896c  test    eax, eax
0x18001896e  jz      short loc_1800189D4
0x180018970  cmp     eax, 3
0x180018973  jz      short loc_1800189D4
0x180018975  mov     [rsp+130h+var_FC], 2
0x18001897d  lea     r8, [rsp+130h+var_F0]
0x180018982  lea     rdx, [rsp+130h+var_100]
0x180018987  lea     rcx, [rsp+130h+var_FC]
0x18001898c  call    ??$IndexerAMTaskState@W4INDEXER_AM_TASK_STATE@@AEAJAEAW4INDEXER_STATE@@@SearchOptionsTelemetry@@SAX$$QEAW4INDEXER_AM_TASK_STATE@@AEAJAEAW4INDEXER_STATE@@@Z; SearchOptionsTelemetry::IndexerAMTaskState<INDEXER_AM_TASK_STATE,long &,INDEXER_STATE &>(INDEXER_AM_TASK_STATE &&,long &,INDEXER_STATE &)
0x180018991  mov     [rsp+130h+bAlertable], 0; bAlertable
0x180018999  mov     r9d, 0EA60h; dwMilliseconds
0x18001899f  xor     r8d, r8d; bWaitAll
0x1800189a2  lea     rdx, [rbp+30h+Handles]; lpHandles
0x1800189a6  lea     ecx, [r8+3]; nCount
0x1800189aa  call    cs:__imp_WaitForMultipleObjectsEx
0x1800189b0  cmp     eax, 0FFFFFFFFh
0x1800189b3  jnz     short loc_1800189BE
0x1800189b5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800189ba  mov     ebx, eax
0x1800189bc  jmp     short loc_1800189C5
0x1800189be  cmp     eax, 102h
0x1800189c3  jnz     short loc_1800189F1
0x1800189c5  lea     rcx, [rsp+130h+var_F0]; this
0x1800189ca  call    ??1CMSSearchServiceState@@QEAA@XZ; CMSSearchServiceState::~CMSSearchServiceState(void)
0x1800189cf  jmp     loc_180018907
0x1800189d4  mov     [rsp+130h+var_FC], 3
0x1800189dc  lea     r8, [rsp+130h+var_F0]
0x1800189e1  lea     rdx, [rsp+130h+var_100]
0x1800189e6  lea     rcx, [rsp+130h+var_FC]
0x1800189eb  call    ??$IndexerAMTaskState@W4INDEXER_AM_TASK_STATE@@AEAJAEAW4INDEXER_STATE@@@SearchOptionsTelemetry@@SAX$$QEAW4INDEXER_AM_TASK_STATE@@AEAJAEAW4INDEXER_STATE@@@Z; SearchOptionsTelemetry::IndexerAMTaskState<INDEXER_AM_TASK_STATE,long &,INDEXER_STATE &>(INDEXER_AM_TASK_STATE &&,long &,INDEXER_STATE &)
0x1800189f0  nop
0x1800189f1  lea     rcx, [rsp+130h+var_F0]; this
0x1800189f6  call    ??1CMSSearchServiceState@@QEAA@XZ; CMSSearchServiceState::~CMSSearchServiceState(void)
0x1800189fb  nop
0x1800189fc  lea     rcx, [rsp+130h+var_D0]; this
0x180018a01  call    ??1CMSSAdmin@@QEAA@XZ; CMSSAdmin::~CMSSAdmin(void)
0x180018a06  lea     rcx, [rbp+30h+var_90]; this
0x180018a0a  call    ?UninitializeServiceListening@CServiceMonitorBase@@QEAAXXZ; CServiceMonitorBase::UninitializeServiceListening(void)
0x180018a0f  lea     rcx, [rbp+30h+Handles+8]; void **
0x180018a13  call    ?SafeCloseHandle@@YAHPEAPEAX@Z; SafeCloseHandle(void * *)
0x180018a18  lea     rcx, [rbp+30h+Handles]; void **
0x180018a1c  call    ?SafeCloseHandle@@YAHPEAPEAX@Z; SafeCloseHandle(void * *)
0x180018a21  mov     rcx, [rdi+68h]
0x180018a25  mov     rax, [rcx]
0x180018a28  mov     edx, ebx
0x180018a2a  mov     rax, [rax+20h]
0x180018a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a33  mov     rax, [rdi]
0x180018a36  mov     rcx, rdi
0x180018a39  mov     rax, [rax+10h]
0x180018a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a42  xor     eax, eax
0x180018a44  mov     rcx, [rbp+30h+var_8]
0x180018a48  xor     rcx, rsp; StackCookie
0x180018a4b  call    __security_check_cookie
0x180018a50  lea     r11, [rsp+130h+var_s0]
0x180018a58  mov     rbx, [r11+18h]
0x180018a5c  mov     rdi, [r11+20h]
0x180018a60  mov     rsp, r11
0x180018a63  pop     rbp
0x180018a64  retn
```
