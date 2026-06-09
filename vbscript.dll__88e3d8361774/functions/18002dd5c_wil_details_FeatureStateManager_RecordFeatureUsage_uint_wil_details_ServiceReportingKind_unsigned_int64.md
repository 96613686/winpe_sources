# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18002dd5c`
- end: `0x18002deb5`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x1800400a0`

## callees

- `0x18002dd5c`
- `0x18002debc`
- `0x18002e000`
- `0x18002e038`
- `0x18002e8c4`
- `0x18002f0d8`
- `0x180042190`
- `0x180048210`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x18002de26`
- `KERNEL32!CreateThreadpoolTimer` at `0x18002de26`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002ddaa`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002ddfa`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002ddaa`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002ddfa`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002dde0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002de59`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002dde0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002de59`
- `KERNEL32!GetLastError` at `0x18002de11`
- `KERNEL32!GetLastError` at `0x18002de11`
- `KERNEL32!SetLastError` at `0x18002de39`
- `KERNEL32!SetLastError` at `0x18002de39`

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
LABEL_11:
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
      wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(v8 + 8, a3, a2);
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
      goto LABEL_11;
  }
}

```

## disassembly

```asm
0x18002dd5c  push    rbx
0x18002dd5e  push    rbp
0x18002dd5f  push    rsi
0x18002dd60  push    rdi
0x18002dd61  push    r14
0x18002dd63  push    r15
0x18002dd65  sub     rsp, 28h
0x18002dd69  cmp     byte ptr [rcx], 0
0x18002dd6c  mov     r15, r9
0x18002dd6f  mov     ebx, r8d
0x18002dd72  mov     r14d, edx
0x18002dd75  mov     rdi, rcx
0x18002dd78  jz      loc_18002DE5F
0x18002dd7e  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18002dd83  test    al, al
0x18002dd85  jz      loc_18002DE5F
0x18002dd8b  mov     rsi, [rdi+18h]
0x18002dd8f  cmp     ebx, 0FEh
0x18002dd95  jz      loc_18002DE6C
0x18002dd9b  cmp     ebx, 0C8h
0x18002dda1  jnb     loc_18002DE79
0x18002dda7  mov     rcx, rsi; SRWLock
0x18002ddaa  call    cs:__imp_AcquireSRWLockExclusive
0x18002ddb0  cmp     ebx, 7
0x18002ddb3  ja      loc_18002DE8E
0x18002ddb9  mov     eax, 0CCh
0x18002ddbe  bt      eax, ebx
0x18002ddc1  jnb     loc_18002DE8E
0x18002ddc7  mov     r8d, r14d
0x18002ddca  lea     rcx, [rsi+8]
0x18002ddce  mov     edx, ebx
0x18002ddd0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18002ddd5  mov     bl, [rsi+40h]
0x18002ddd8  test    rsi, rsi
0x18002dddb  jz      short loc_18002DDE6
0x18002dddd  mov     rcx, rsi; SRWLock
0x18002dde0  call    cs:__imp_ReleaseSRWLockExclusive
0x18002dde6  test    bl, bl
0x18002dde8  jz      short loc_18002DE5F
0x18002ddea  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002ddef  test    al, al
0x18002ddf1  jnz     short loc_18002DE5F
0x18002ddf3  lea     rsi, [rdi+20h]
0x18002ddf7  mov     rcx, rsi; SRWLock
0x18002ddfa  call    cs:__imp_AcquireSRWLockExclusive
0x18002de00  cmp     byte ptr [rdi+41h], 0
0x18002de04  jnz     short loc_18002DE51
0x18002de06  lea     rbp, [rdi+30h]
0x18002de0a  cmp     qword ptr [rbp+0], 0
0x18002de0f  jnz     short loc_18002DE3F
0x18002de11  call    cs:__imp_GetLastError
0x18002de17  xor     r8d, r8d; pcbe
0x18002de1a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002de21  mov     rdx, rdi; pv
0x18002de24  mov     ebx, eax
0x18002de26  call    cs:__imp_CreateThreadpoolTimer
0x18002de2c  mov     rdx, rax
0x18002de2f  mov     rcx, rbp
0x18002de32  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002de37  mov     ecx, ebx; dwErrCode
0x18002de39  call    cs:__imp_SetLastError
0x18002de3f  mov     r8d, 493E0h
0x18002de45  lea     rdx, [rdi+41h]
0x18002de49  mov     rcx, rbp
0x18002de4c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18002de51  test    rsi, rsi
0x18002de54  jz      short loc_18002DE5F
0x18002de56  mov     rcx, rsi; SRWLock
0x18002de59  call    cs:__imp_ReleaseSRWLockExclusive
0x18002de5f  add     rsp, 28h
0x18002de63  pop     r15
0x18002de65  pop     r14
0x18002de67  pop     rdi
0x18002de68  pop     rsi
0x18002de69  pop     rbp
0x18002de6a  pop     rbx
0x18002de6b  retn
0x18002de6c  mov     rcx, rsi; this
0x18002de6f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18002de74  jmp     loc_18002DDEA
0x18002de79  cmp     ebx, 100h
0x18002de7f  jl      short loc_18002DE5F
0x18002de81  cmp     ebx, 200h
0x18002de87  jnb     short loc_18002DE5F
0x18002de89  jmp     loc_18002DDA7
0x18002de8e  lea     eax, [rbx-100h]
0x18002de94  cmp     eax, 7Fh
0x18002de97  jbe     loc_18002DDC7
0x18002de9d  mov     r9d, r15d
0x18002dea0  lea     rcx, [rsi+48h]
0x18002dea4  mov     r8d, r14d
0x18002dea7  mov     edx, ebx
0x18002dea9  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18002deae  mov     bl, al
0x18002deb0  jmp     loc_18002DDD8
```
