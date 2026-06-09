# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18003289c`
- end: `0x180032a28`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180032800`

## callees

- `0x18003289c`
- `0x180032a30`
- `0x180032b0c`
- `0x180032b7c`
- `0x180032bb4`
- `0x180033488`
- `0x180043894`
- `0x180049750`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x180032986`
- `KERNEL32!CreateThreadpoolTimer` at `0x180032986`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800328ea`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18003294e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800328ea`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18003294e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180032926`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800329c5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180032926`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800329c5`
- `KERNEL32!GetLastError` at `0x18003296b`
- `KERNEL32!GetLastError` at `0x18003296b`
- `KERNEL32!SetLastError` at `0x18003299f`
- `KERNEL32!SetLastError` at `0x18003299f`

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
0x18003289c  push    rbx
0x18003289e  push    rbp
0x18003289f  push    rsi
0x1800328a0  push    rdi
0x1800328a1  push    r14
0x1800328a3  push    r15
0x1800328a5  sub     rsp, 28h
0x1800328a9  cmp     byte ptr [rcx], 0
0x1800328ac  mov     r15, r9
0x1800328af  mov     ebx, r8d
0x1800328b2  mov     r14d, edx
0x1800328b5  mov     rdi, rcx
0x1800328b8  jz      loc_1800329D1
0x1800328be  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800328c3  test    al, al
0x1800328c5  jz      loc_1800329D1
0x1800328cb  mov     rsi, [rdi+18h]
0x1800328cf  cmp     ebx, 0FEh
0x1800328d5  jz      loc_1800329DF
0x1800328db  cmp     ebx, 0C8h
0x1800328e1  jnb     loc_1800329EC
0x1800328e7  mov     rcx, rsi; SRWLock
0x1800328ea  call    cs:__imp_AcquireSRWLockExclusive
0x1800328f1  nop     dword ptr [rax+rax+00h]
0x1800328f6  cmp     ebx, 7
0x1800328f9  ja      loc_180032A01
0x1800328ff  mov     eax, 0CCh
0x180032904  bt      eax, ebx
0x180032907  jnb     loc_180032A01
0x18003290d  mov     r8d, r14d
0x180032910  lea     rcx, [rsi+8]
0x180032914  mov     edx, ebx
0x180032916  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18003291b  mov     bl, [rsi+40h]
0x18003291e  test    rsi, rsi
0x180032921  jz      short loc_180032932
0x180032923  mov     rcx, rsi; SRWLock
0x180032926  call    cs:__imp_ReleaseSRWLockExclusive
0x18003292d  nop     dword ptr [rax+rax+00h]
0x180032932  test    bl, bl
0x180032934  jz      loc_1800329D1
0x18003293a  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18003293f  test    al, al
0x180032941  jnz     loc_1800329D1
0x180032947  lea     rsi, [rdi+20h]
0x18003294b  mov     rcx, rsi; SRWLock
0x18003294e  call    cs:__imp_AcquireSRWLockExclusive
0x180032955  nop     dword ptr [rax+rax+00h]
0x18003295a  cmp     byte ptr [rdi+41h], 0
0x18003295e  jnz     short loc_1800329BD
0x180032960  lea     rbp, [rdi+30h]
0x180032964  cmp     qword ptr [rbp+0], 0
0x180032969  jnz     short loc_1800329AB
0x18003296b  call    cs:__imp_GetLastError
0x180032972  nop     dword ptr [rax+rax+00h]
0x180032977  xor     r8d, r8d; pcbe
0x18003297a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180032981  mov     rdx, rdi; pv
0x180032984  mov     ebx, eax
0x180032986  call    cs:__imp_CreateThreadpoolTimer
0x18003298d  nop     dword ptr [rax+rax+00h]
0x180032992  mov     rdx, rax
0x180032995  mov     rcx, rbp
0x180032998  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18003299d  mov     ecx, ebx; dwErrCode
0x18003299f  call    cs:__imp_SetLastError
0x1800329a6  nop     dword ptr [rax+rax+00h]
0x1800329ab  mov     r8d, 493E0h
0x1800329b1  lea     rdx, [rdi+41h]
0x1800329b5  mov     rcx, rbp
0x1800329b8  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800329bd  test    rsi, rsi
0x1800329c0  jz      short loc_1800329D1
0x1800329c2  mov     rcx, rsi; SRWLock
0x1800329c5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800329cc  nop     dword ptr [rax+rax+00h]
0x1800329d1  add     rsp, 28h
0x1800329d5  pop     r15
0x1800329d7  pop     r14
0x1800329d9  pop     rdi
0x1800329da  pop     rsi
0x1800329db  pop     rbp
0x1800329dc  pop     rbx
0x1800329dd  retn
0x1800329df  mov     rcx, rsi; this
0x1800329e2  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800329e7  jmp     loc_18003293A
0x1800329ec  cmp     ebx, 100h
0x1800329f2  jl      short loc_1800329D1
0x1800329f4  cmp     ebx, 200h
0x1800329fa  jnb     short loc_1800329D1
0x1800329fc  jmp     loc_1800328E7
0x180032a01  lea     eax, [rbx-100h]
0x180032a07  cmp     eax, 7Fh
0x180032a0a  jbe     loc_18003290D
0x180032a10  mov     r9d, r15d
0x180032a13  lea     rcx, [rsi+48h]
0x180032a17  mov     r8d, r14d
0x180032a1a  mov     edx, ebx
0x180032a1c  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180032a21  mov     bl, al
0x180032a23  jmp     loc_18003291E
```
