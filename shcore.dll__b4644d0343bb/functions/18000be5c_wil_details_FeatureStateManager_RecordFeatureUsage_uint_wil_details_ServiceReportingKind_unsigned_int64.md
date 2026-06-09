# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000be5c`
- end: `0x18000bfaf`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `339`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18004c040`

## callees

- `0x180009b08`
- `0x18000be5c`
- `0x18000bfb8`
- `0x18000c034`
- `0x18000ca10`
- `0x1800259a4`
- `0x180038edc`
- `0x18006d680`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000beb6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bf06`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000beb6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bf06`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000beec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bf1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000beec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bf1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bf61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bf61`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000bf4e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000bf4e`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  __int64 v8; // rsi
  int v9; // eax
  wil *v10; // rcx
  char v11; // bl
  DWORD LastError; // ebx
  PTP_TIMER ThreadpoolTimer; // rax

  if ( !*(_BYTE *)a1 || !wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
    return;
  v8 = *(_QWORD *)(a1 + 24);
  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(*(wil::details_abi::FeatureStateData **)(a1 + 24));
LABEL_13:
    if ( !wil::ProcessShutdownInProgress(v10) )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 32));
      if ( !*(_BYTE *)(a1 + 65) )
      {
        if ( !*(_QWORD *)(a1 + 48) )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                              (PVOID)a1,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            a1 + 48,
            ThreadpoolTimer);
          SetLastError(LastError);
        }
        wil::details::EnsureCoalescedTimer_SetTimer(a1 + 48, a1 + 65, 300000);
      }
      if ( a1 != -32 )
        ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 32));
    }
    return;
  }
  if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
  {
    AcquireSRWLockExclusive(*(PSRWLOCK *)(a1 + 24));
    if ( a3 <= 7 && (v9 = 204, _bittest(&v9, a3)) || a3 - 256 <= 0x7F )
    {
      wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage((wil::details_abi::RawUsageIndex *)(v8 + 8));
      v11 = *(_BYTE *)(v8 + 64);
    }
    else
    {
      v11 = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
              v8 + 72,
              a3,
              a2,
              a4);
    }
    if ( v8 )
      ReleaseSRWLockExclusive((PSRWLOCK)v8);
    if ( v11 )
      goto LABEL_13;
  }
}

```

## disassembly

```asm
0x18000be5c  push    rbx
0x18000be5e  push    rbp
0x18000be5f  push    rsi
0x18000be60  push    rdi
0x18000be61  push    r14
0x18000be63  push    r15
0x18000be65  sub     rsp, 28h
0x18000be69  mov     r15, r9
0x18000be6c  mov     ebx, r8d
0x18000be6f  mov     r14d, edx
0x18000be72  mov     rdi, rcx
0x18000be75  cmp     byte ptr [rcx], 0
0x18000be78  jz      loc_18000BF21
0x18000be7e  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000be83  test    al, al
0x18000be85  jz      loc_18000BF21
0x18000be8b  mov     rsi, [rdi+18h]
0x18000be8f  cmp     ebx, 0FEh
0x18000be95  jz      loc_18000BF7B
0x18000be9b  cmp     ebx, 0C8h
0x18000bea1  jb      short loc_18000BEB3
0x18000bea3  cmp     ebx, 100h
0x18000bea9  jl      short loc_18000BF21
0x18000beab  cmp     ebx, 200h
0x18000beb1  jnb     short loc_18000BF21
0x18000beb3  mov     rcx, rsi; SRWLock
0x18000beb6  call    cs:__imp_AcquireSRWLockExclusive
0x18000bebc  cmp     ebx, 7
0x18000bebf  ja      loc_18000BF88
0x18000bec5  mov     eax, 0CCh
0x18000beca  bt      eax, ebx
0x18000becd  jnb     loc_18000BF88
0x18000bed3  mov     r8d, r14d
0x18000bed6  mov     edx, ebx
0x18000bed8  lea     rcx, [rsi+8]; this
0x18000bedc  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000bee1  mov     bl, [rsi+40h]
0x18000bee4  test    rsi, rsi
0x18000bee7  jz      short loc_18000BEF2
0x18000bee9  mov     rcx, rsi; SRWLock
0x18000beec  call    cs:__imp_ReleaseSRWLockExclusive
0x18000bef2  test    bl, bl
0x18000bef4  jz      short loc_18000BF21
0x18000bef6  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000befb  test    al, al
0x18000befd  jnz     short loc_18000BF21
0x18000beff  lea     rsi, [rdi+20h]
0x18000bf03  mov     rcx, rsi; SRWLock
0x18000bf06  call    cs:__imp_AcquireSRWLockExclusive
0x18000bf0c  cmp     byte ptr [rdi+41h], 0
0x18000bf10  jz      short loc_18000BF2E
0x18000bf12  test    rsi, rsi
0x18000bf15  jz      short loc_18000BF21
0x18000bf17  mov     rcx, rsi; SRWLock
0x18000bf1a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000bf20  nop
0x18000bf21  add     rsp, 28h
0x18000bf25  pop     r15
0x18000bf27  pop     r14
0x18000bf29  pop     rdi
0x18000bf2a  pop     rsi
0x18000bf2b  pop     rbp
0x18000bf2c  pop     rbx
0x18000bf2d  retn
0x18000bf2e  lea     rbp, [rdi+30h]
0x18000bf32  cmp     qword ptr [rbp+0], 0
0x18000bf37  jnz     short loc_18000BF67
0x18000bf39  call    cs:__imp_GetLastError
0x18000bf3f  mov     ebx, eax
0x18000bf41  xor     r8d, r8d; pcbe
0x18000bf44  mov     rdx, rdi; pv
0x18000bf47  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000bf4e  call    cs:__imp_CreateThreadpoolTimer
0x18000bf54  mov     rdx, rax
0x18000bf57  mov     rcx, rbp
0x18000bf5a  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000bf5f  mov     ecx, ebx; dwErrCode
0x18000bf61  call    cs:__imp_SetLastError
0x18000bf67  mov     r8d, 493E0h
0x18000bf6d  lea     rdx, [rdi+41h]
0x18000bf71  mov     rcx, rbp
0x18000bf74  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000bf79  jmp     short loc_18000BF12
0x18000bf7b  mov     rcx, rsi; this
0x18000bf7e  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000bf83  jmp     loc_18000BEF6
0x18000bf88  lea     eax, [rbx-100h]
0x18000bf8e  cmp     eax, 7Fh
0x18000bf91  jbe     loc_18000BED3
0x18000bf97  mov     r9d, r15d
0x18000bf9a  lea     rcx, [rsi+48h]
0x18000bf9e  mov     r8d, r14d
0x18000bfa1  mov     edx, ebx
0x18000bfa3  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000bfa8  mov     bl, al
0x18000bfaa  jmp     loc_18000BEE4
```
