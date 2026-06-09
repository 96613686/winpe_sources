# CUploadQueueManager::_ScheduleRetryTimer(void)

- ea: `0x1801b95f8`
- end: `0x1801b9a21`
- name: `?_ScheduleRetryTimer@CUploadQueueManager@@AEAAJXZ`
- size: `1065`
- prototype: `__int64 __fastcall(CUploadQueueManager *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801b949c`

## callees

- `0x1800150c0`
- `0x180038274`
- `0x180047224`
- `0x180074b74`
- `0x180091964`
- `0x18013d330`
- `0x18013d354`
- `0x18013df8c`
- `0x1801b8590`
- `0x1801b95f8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801b9637`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801b9637`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1801b98a0`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1801b98a0`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1801b966b`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1801b966b`
- `TimeBrokerClient!TbCreateEvent` at `0x1801b9784`
- `TimeBrokerClient!TbCreateEvent` at `0x1801b9784`
- `TimeBrokerClient!TbDeleteEvent` at `0x1801b99f2`
- `TimeBrokerClient!TbDeleteEvent` at `0x1801b99f2`
- `SystemEventsBrokerClient!SebCreateDisplayOnEvent` at `0x1801b97e3`
- `SystemEventsBrokerClient!SebCreateDisplayOnEvent` at `0x1801b97e3`
- `SystemEventsBrokerClient!SebDeleteEvent` at `0x1801b99b6`
- `SystemEventsBrokerClient!SebDeleteEvent` at `0x1801b99d4`
- `SystemEventsBrokerClient!SebDeleteEvent` at `0x1801b99b6`
- `SystemEventsBrokerClient!SebDeleteEvent` at `0x1801b99d4`
- `SystemEventsBrokerClient!SebRegisterWellKnownEvent` at `0x1801b97af`
- `SystemEventsBrokerClient!SebRegisterWellKnownEvent` at `0x1801b97af`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDisassociateWorkItem` at `0x1801b999c`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDisassociateWorkItem` at `0x1801b999c`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtAssociateActivationProxy` at `0x1801b984c`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtAssociateActivationProxy` at `0x1801b984c`

## pseudocode

```c
__int64 __fastcall CUploadQueueManager::_ScheduleRetryTimer(CUploadQueueManager *this)
{
  __int64 v2; // rax
  int Error; // ebx
  int v4; // eax
  int v5; // eax
  __int64 v6; // rdx
  char v7; // si
  char *v8; // rax
  char *v9; // rbx
  __int128 v10; // xmm0
  __int128 v11; // xmm2
  __int128 v12; // xmm1
  __int64 v13; // r8
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v16; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v17; // [rsp+50h] [rbp-B0h] BYREF
  __int128 *v18; // [rsp+60h] [rbp-A0h] BYREF
  char v19; // [rsp+68h] [rbp-98h]
  __int128 *v20; // [rsp+70h] [rbp-90h]
  char v21; // [rsp+78h] [rbp-88h]
  __m256i v22; // [rsp+80h] [rbp-80h] BYREF
  __int128 v23; // [rsp+A0h] [rbp-60h]
  __int128 v24; // [rsp+B0h] [rbp-50h]
  __int128 v25; // [rsp+C0h] [rbp-40h]
  __int128 v26; // [rsp+D0h] [rbp-30h]
  __int128 v27; // [rsp+E0h] [rbp-20h]
  __int128 v28; // [rsp+F0h] [rbp-10h]
  __int128 v29; // [rsp+100h] [rbp+0h]
  __int128 v30; // [rsp+110h] [rbp+10h]
  __int128 v31; // [rsp+120h] [rbp+20h]
  __int128 v32; // [rsp+130h] [rbp+30h]
  __int128 v33; // [rsp+140h] [rbp+40h]
  __int128 v34; // [rsp+150h] [rbp+50h]
  __int128 v35; // [rsp+160h] [rbp+60h]
  __int64 v36; // [rsp+170h] [rbp+70h]
  __m256i v37; // [rsp+180h] [rbp+80h] BYREF
  __int128 v38; // [rsp+1A0h] [rbp+A0h]
  __int128 v39; // [rsp+1B0h] [rbp+B0h]
  __int128 v40; // [rsp+1C0h] [rbp+C0h]
  __int128 v41; // [rsp+1D0h] [rbp+D0h]
  __int128 v42; // [rsp+1E0h] [rbp+E0h]
  __int128 v43; // [rsp+1F0h] [rbp+F0h]
  __int128 v44; // [rsp+200h] [rbp+100h]
  __int128 v45; // [rsp+210h] [rbp+110h]
  __int128 v46; // [rsp+220h] [rbp+120h]
  __int128 v47; // [rsp+230h] [rbp+130h]
  __int128 v48; // [rsp+240h] [rbp+140h]
  __int128 v49; // [rsp+250h] [rbp+150h]
  __int128 v50; // [rsp+260h] [rbp+160h]
  __int64 v51; // [rsp+270h] [rbp+170h]
  __int128 v52; // [rsp+280h] [rbp+180h] BYREF
  __int64 v53; // [rsp+290h] [rbp+190h] BYREF
  __int128 v54; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int128 v55; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int128 v56; // [rsp+2C0h] [rbp+1C0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v58[16]; // [rsp+2E0h] [rbp+1E0h] BYREF

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v2 = *((_QWORD *)this + 28) + *(_QWORD *)&SystemTimeAsFileTime;
  SystemTimeAsFileTime.dwLowDateTime += *((_DWORD *)this + 56);
  SystemTimeAsFileTime.dwHighDateTime = HIDWORD(v2);
  SystemTime = 0;
  if ( FileTimeToSystemTime(&SystemTimeAsFileTime, &SystemTime) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    memset_0(&v22, 0, 0xF8u);
    v22.m256i_i64[3] = 0x100000000LL;
    *(struct _SYSTEMTIME *)&v22.m256i_u64[1] = SystemTime;
    v56 = 0;
    LODWORD(v23) = 1440;
    v37 = v22;
    BYTE5(v24) = 0;
    v51 = v36;
    v38 = v23;
    v39 = v24;
    v40 = v25;
    v41 = v26;
    v42 = v27;
    v43 = v28;
    v44 = v29;
    v45 = v30;
    v46 = v31;
    v47 = v32;
    v48 = v33;
    v49 = v34;
    v50 = v35;
    Error = TbCreateEvent(0, &v37, &v56);
    if ( Error >= 0 )
    {
      v55 = 0;
      Error = SebRegisterWellKnownEvent(4, &v55, 0);
      if ( Error < 0 )
      {
LABEL_20:
        v52 = v56;
        TbDeleteEvent(0, &v52);
        return (unsigned int)Error;
      }
      v19 = 1;
      v18 = &v55;
      v54 = 0;
      Error = SebCreateDisplayOnEvent(&v54, 0);
      if ( Error < 0 )
      {
LABEL_19:
        v52 = v55;
        SebDeleteEvent(&v52, 0);
        goto LABEL_20;
      }
      v20 = &v54;
      v21 = 1;
      v53 = 0;
      v52 = 0;
      v4 = BiPtAssociateActivationProxy(&v52, &v53, &v56, &v18, 2, 0, 0);
      Error = ResultFromWin32FromStatus(v4);
      if ( Error < 0 )
      {
LABEL_18:
        v17 = v54;
        SebDeleteEvent(&v17, 0);
        goto LABEL_19;
      }
      v16 = 0;
      v5 = RtlSubscribeWnfStateChangeNotification(&v16, v53, 0, CUploadQueueManager::_TimerWnfCallback, this, 0, 0, 1);
      Error = ResultFromWin32FromStatus(v5);
      if ( Error < 0 )
        goto LABEL_17;
      v7 = 1;
      wil::AcquireSRWLockExclusive(&v17, (char *)this + 192);
      if ( !*((_BYTE *)this + 200) )
      {
        v8 = (char *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
        v9 = v8;
        if ( v8 )
        {
          v10 = v56;
          v11 = v55;
          v12 = v54;
          *(_QWORD *)v8 = v16;
          *(_OWORD *)(v8 + 8) = v10;
          *(_OWORD *)(v8 + 24) = v12;
          *(_OWORD *)(v8 + 40) = v11;
          *(_OWORD *)(v8 + 56) = v52;
        }
        else
        {
          v9 = 0;
        }
        CTSmartObj<CRetryTimerRegistration *,CTSmartPtr_PolicyComplete<CTContainer_PolicyNewMem>>::Release((char *)this + 208);
        *((_QWORD *)this + 26) = v9;
        if ( v9 )
        {
          *((_BYTE *)this + 200) = 1;
          Error = 0;
          v7 = 0;
          if ( (Microsoft_Windows_Immersive_ShellEnableBits & 0x100000) != 0 )
            McGenEventWrite_EventWriteTransfer(
              &MICROSOFT_TWINUI_PUBLISHER_Context,
              ConnectedSearch_RetryTimerScheduled,
              v13,
              1,
              v58);
        }
        else
        {
          Error = -2147024882;
        }
      }
      Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v17);
      if ( v7 )
      {
LABEL_17:
        LOBYTE(v6) = 1;
        BiPtDisassociateWorkItem(&v52, v6);
        goto LABEL_18;
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1801b95f8  mov     [rsp-8+arg_8], rbx
0x1801b95fd  mov     [rsp-8+arg_10], rsi
0x1801b9602  push    rbp
0x1801b9603  push    rdi
0x1801b9604  push    r14
0x1801b9606  lea     rbp, [rsp-200h]
0x1801b960e  sub     rsp, 300h
0x1801b9615  mov     rax, cs:__security_cookie
0x1801b961c  xor     rax, rsp
0x1801b961f  mov     [rbp+210h+var_20], rax
0x1801b9626  mov     rdi, rcx
0x1801b9629  mov     qword ptr [rsp+310h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1801b9632  lea     rcx, [rsp+310h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1801b9637  call    cs:__imp_GetSystemTimeAsFileTime
0x1801b963d  mov     rax, qword ptr [rsp+310h+SystemTimeAsFileTime.dwLowDateTime]
0x1801b9642  lea     rdx, [rbp+210h+SystemTime]; lpSystemTime
0x1801b9649  add     rax, [rdi+0E0h]
0x1801b9650  lea     rcx, [rsp+310h+SystemTimeAsFileTime]; lpFileTime
0x1801b9655  mov     [rsp+310h+SystemTimeAsFileTime.dwLowDateTime], eax
0x1801b9659  xorps   xmm0, xmm0
0x1801b965c  shr     rax, 20h
0x1801b9660  mov     [rsp+310h+SystemTimeAsFileTime.dwHighDateTime], eax
0x1801b9664  movups  xmmword ptr [rbp+210h+SystemTime.wYear], xmm0
0x1801b966b  call    cs:__imp_FileTimeToSystemTime
0x1801b9671  test    eax, eax
0x1801b9673  jnz     short loc_1801B9684
0x1801b9675  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1801b967a  mov     ebx, eax
0x1801b967c  test    eax, eax
0x1801b967e  js      loc_1801B99F8
0x1801b9684  xor     edx, edx; Val
0x1801b9686  lea     rcx, [rbp+210h+var_290]; void *
0x1801b968a  mov     r8d, 0F8h; Size
0x1801b9690  call    memset_0
0x1801b9695  movups  xmm0, xmmword ptr [rbp+210h+SystemTime.wYear]
0x1801b969c  mov     rax, [rbp+210h+var_1A0]
0x1801b96a0  lea     r8, [rbp+210h+var_50]
0x1801b96a7  mov     [rbp+210h+var_278], 0
0x1801b96ae  lea     rdx, [rbp+210h+var_190]
0x1801b96b5  movdqu  [rbp+210h+var_290+8], xmm0
0x1801b96ba  mov     [rbp+210h+var_274], 1
0x1801b96c1  xor     ecx, ecx
0x1801b96c3  movaps  xmm1, [rbp+210h+var_290]
0x1801b96c7  xorps   xmm0, xmm0
0x1801b96ca  movups  [rbp+210h+var_50], xmm0
0x1801b96d1  mov     dword ptr [rbp+210h+var_270], 5A0h
0x1801b96d8  movaps  xmm0, xmmword ptr [rbp-70h]
0x1801b96dc  movups  [rbp+210h+var_190], xmm1
0x1801b96e3  mov     [rbp+210h+var_25B], 0
0x1801b96e7  movaps  xmm1, [rbp+210h+var_270]
0x1801b96eb  movups  [rbp+210h+var_180], xmm0
0x1801b96f2  mov     [rbp+210h+var_A0], rax
0x1801b96f9  movaps  xmm0, xmmword ptr [rbp-50h]
0x1801b96fd  movups  [rbp+210h+var_170], xmm1
0x1801b9704  movaps  xmm1, [rbp+210h+var_250]
0x1801b9708  movups  [rbp+210h+var_160], xmm0
0x1801b970f  movaps  xmm0, [rbp+210h+var_240]
0x1801b9713  movups  [rbp+210h+var_150], xmm1
0x1801b971a  movaps  xmm1, [rbp+210h+var_230]
0x1801b971e  movups  [rbp+210h+var_140], xmm0
0x1801b9725  movaps  xmm0, [rbp+210h+var_220]
0x1801b9729  movups  [rbp+210h+var_130], xmm1
0x1801b9730  movaps  xmm1, [rbp+210h+var_210]
0x1801b9734  movups  [rbp+210h+var_120], xmm0
0x1801b973b  movaps  xmm0, [rbp+210h+var_200]
0x1801b973f  movups  [rbp+210h+var_110], xmm1
0x1801b9746  movaps  xmm1, [rbp+210h+var_1F0]
0x1801b974a  movups  [rbp+210h+var_100], xmm0
0x1801b9751  movaps  xmm0, [rbp+210h+var_1E0]
0x1801b9755  movups  [rbp+210h+var_F0], xmm1
0x1801b975c  movaps  xmm1, [rbp+210h+var_1D0]
0x1801b9760  movups  [rbp+210h+var_E0], xmm0
0x1801b9767  movaps  xmm0, [rbp+210h+var_1C0]
0x1801b976b  movups  [rbp+210h+var_D0], xmm1
0x1801b9772  movaps  xmm1, [rbp+210h+var_1B0]
0x1801b9776  movups  [rbp+210h+var_C0], xmm0
0x1801b977d  movups  [rbp+210h+var_B0], xmm1
0x1801b9784  call    cs:__imp_TbCreateEvent
0x1801b978a  mov     ebx, eax
0x1801b978c  test    eax, eax
0x1801b978e  js      loc_1801B99F8
0x1801b9794  xor     r9d, r9d
0x1801b9797  lea     rdx, [rbp+210h+var_60]
0x1801b979e  xorps   xmm0, xmm0
0x1801b97a1  xor     r8d, r8d
0x1801b97a4  movups  [rbp+210h+var_60], xmm0
0x1801b97ab  lea     ecx, [r9+4]
0x1801b97af  call    cs:__imp_SebRegisterWellKnownEvent
0x1801b97b5  mov     ebx, eax
0x1801b97b7  test    eax, eax
0x1801b97b9  js      loc_1801B99DA
0x1801b97bf  lea     rax, [rbp+210h+var_60]
0x1801b97c6  mov     [rsp+310h+var_2A8], 1
0x1801b97cb  xorps   xmm0, xmm0
0x1801b97ce  mov     [rsp+310h+var_2B0], rax
0x1801b97d3  xor     edx, edx
0x1801b97d5  lea     rcx, [rbp+210h+var_70]
0x1801b97dc  movups  [rbp+210h+var_70], xmm0
0x1801b97e3  call    cs:__imp_SebCreateDisplayOnEvent
0x1801b97e9  mov     ebx, eax
0x1801b97eb  test    eax, eax
0x1801b97ed  js      loc_1801B99BC
0x1801b97f3  lea     rax, [rbp+210h+var_70]
0x1801b97fa  mov     [rsp+310h+var_2E0], 0
0x1801b9803  xorps   xmm0, xmm0
0x1801b9806  mov     dword ptr [rsp+310h+var_2E8], 0
0x1801b980e  lea     r9, [rsp+310h+var_2B0]
0x1801b9813  mov     [rsp+310h+var_2A0], rax
0x1801b9818  lea     r8, [rbp+210h+var_50]
0x1801b981f  mov     dword ptr [rsp+310h+var_2F0], 2
0x1801b9827  lea     rdx, [rbp+210h+var_80]
0x1801b982e  mov     [rsp+310h+var_298], 1
0x1801b9833  lea     rcx, [rbp+210h+var_90]
0x1801b983a  mov     [rbp+210h+var_80], 0
0x1801b9845  movups  [rbp+210h+var_90], xmm0
0x1801b984c  call    cs:__imp_BiPtAssociateActivationProxy
0x1801b9852  mov     ecx, eax; int
0x1801b9854  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x1801b9859  mov     ebx, eax
0x1801b985b  test    eax, eax
0x1801b985d  js      loc_1801B99A2
0x1801b9863  mov     rdx, [rbp+210h+var_80]
0x1801b986a  lea     r9, ?_TimerWnfCallback@CUploadQueueManager@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; CUploadQueueManager::_TimerWnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x1801b9871  mov     [rsp+310h+var_2D8], 1
0x1801b9879  lea     rcx, [rsp+310h+var_2C8]
0x1801b987e  mov     dword ptr [rsp+310h+var_2E0], 0
0x1801b9886  xor     r8d, r8d
0x1801b9889  mov     [rsp+310h+var_2E8], 0
0x1801b9892  mov     [rsp+310h+var_2F0], rdi
0x1801b9897  mov     [rsp+310h+var_2C8], 0
0x1801b98a0  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1801b98a6  mov     ecx, eax; int
0x1801b98a8  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x1801b98ad  mov     ebx, eax
0x1801b98af  test    eax, eax
0x1801b98b1  js      loc_1801B9993
0x1801b98b7  lea     rdx, [rdi+0C0h]
0x1801b98be  mov     sil, 1
0x1801b98c1  lea     rcx, [rsp+310h+var_2C0]
0x1801b98c6  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1801b98cb  mov     al, [rdi+0C8h]
0x1801b98d1  test    al, al
0x1801b98d3  jnz     loc_1801B9984
0x1801b98d9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801b98e0  mov     ecx, 50h ; 'P'; unsigned __int64
0x1801b98e5  lea     r14, [rdi+0D0h]
0x1801b98ec  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1801b98f1  mov     rbx, rax
0x1801b98f4  test    rax, rax
0x1801b98f7  jz      short loc_1801B9933
0x1801b98f9  movaps  xmm0, [rbp+210h+var_50]
0x1801b9900  movaps  xmm2, [rbp+210h+var_60]
0x1801b9907  movaps  xmm1, [rbp+210h+var_70]
0x1801b990e  mov     rcx, [rsp+310h+var_2C8]
0x1801b9913  mov     [rax], rcx
0x1801b9916  movdqu  xmmword ptr [rax+8], xmm0
0x1801b991b  movdqu  xmmword ptr [rax+18h], xmm1
0x1801b9920  movdqu  xmmword ptr [rax+28h], xmm2
0x1801b9925  movups  xmm0, [rbp+210h+var_90]
0x1801b992c  movdqu  xmmword ptr [rax+38h], xmm0
0x1801b9931  jmp     short loc_1801B9935
0x1801b9933  xor     ebx, ebx
0x1801b9935  mov     rcx, r14
0x1801b9938  call    ?Release@?$CTSmartObj@PEAVCRetryTimerRegistration@@V?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyNewMem@@@@@@QEAAXXZ; CTSmartObj<CRetryTimerRegistration *,CTSmartPtr_PolicyComplete<CTContainer_PolicyNewMem>>::Release(void)
0x1801b993d  mov     [r14], rbx
0x1801b9940  test    rbx, rbx
0x1801b9943  jz      short loc_1801B997F
0x1801b9945  mov     [rdi+0C8h], sil
0x1801b994c  xor     ebx, ebx
0x1801b994e  xor     sil, sil
0x1801b9951  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits+2, 10h
0x1801b9958  jz      short loc_1801B9984
0x1801b995a  lea     rax, [rbp+210h+var_30]
0x1801b9961  lea     r9d, [rbx+1]
0x1801b9965  mov     [rsp+310h+var_2F0], rax
0x1801b996a  lea     rdx, ConnectedSearch_RetryTimerScheduled
0x1801b9971  lea     rcx, MICROSOFT_TWINUI_PUBLISHER_Context
0x1801b9978  call    McGenEventWrite_EventWriteTransfer
0x1801b997d  jmp     short loc_1801B9984
0x1801b997f  mov     ebx, 8007000Eh
0x1801b9984  lea     rcx, [rsp+310h+var_2C0]; this
0x1801b9989  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1801b998e  test    sil, sil
0x1801b9991  jz      short loc_1801B99F8
0x1801b9993  mov     dl, 1
0x1801b9995  lea     rcx, [rbp+210h+var_90]
0x1801b999c  call    cs:__imp_BiPtDisassociateWorkItem
0x1801b99a2  movaps  xmm0, [rbp+210h+var_70]
0x1801b99a9  lea     rcx, [rsp+310h+var_2C0]
0x1801b99ae  xor     edx, edx
0x1801b99b0  movdqa  [rsp+310h+var_2C0], xmm0
0x1801b99b6  call    cs:__imp_SebDeleteEvent
0x1801b99bc  movaps  xmm0, [rbp+210h+var_60]
0x1801b99c3  lea     rcx, [rbp+210h+var_90]
0x1801b99ca  xor     edx, edx
0x1801b99cc  movdqa  [rbp+210h+var_90], xmm0
0x1801b99d4  call    cs:__imp_SebDeleteEvent
0x1801b99da  movaps  xmm0, [rbp+210h+var_50]
0x1801b99e1  lea     rdx, [rbp+210h+var_90]
0x1801b99e8  xor     ecx, ecx
0x1801b99ea  movdqa  [rbp+210h+var_90], xmm0
0x1801b99f2  call    cs:__imp_TbDeleteEvent
0x1801b99f8  mov     eax, ebx
0x1801b99fa  mov     rcx, [rbp+210h+var_20]
0x1801b9a01  xor     rcx, rsp; StackCookie
0x1801b9a04  call    __security_check_cookie
0x1801b9a09  lea     r11, [rsp+310h+var_10]
0x1801b9a11  mov     rbx, [r11+28h]
0x1801b9a15  mov     rsi, [r11+30h]
0x1801b9a19  mov     rsp, r11
0x1801b9a1c  pop     r14
0x1801b9a1e  pop     rdi
0x1801b9a1f  pop     rbp
0x1801b9a20  retn
```
