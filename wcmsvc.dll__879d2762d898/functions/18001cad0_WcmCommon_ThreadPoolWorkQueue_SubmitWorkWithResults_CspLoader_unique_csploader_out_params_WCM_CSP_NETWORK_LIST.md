# WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults<CspLoader::unique_csploader_out_params<WCM_CSP_NETWORK_LIST>,`CspLoader::GetNetworkList(_GUID *,WCM_CSP_NETWORK_LIST * *)'::`6'::_lambda_1_>(`CspLoader::GetNetworkList(_GUID *,WCM_CSP_NETWORK_LIST * *)'::`6'::_lambda_1_ &&)

- ea: `0x18001cad0`
- end: `0x18001cc2f`
- name: `??$SubmitWorkWithResults@U?$unique_csploader_out_params@UWCM_CSP_NETWORK_LIST@@@CspLoader@@V_lambda_1_@?5??GetNetworkList@2@QEAAKPEAU_GUID@@PEAPEAUWCM_CSP_NETWORK_LIST@@@Z@@ThreadPoolWorkQueue@WcmCommon@@QEAA?AV?$shared_ptr@V?$ThreadPoolWaitableResult@U?$unique_csploader_out_params@UWCM_CSP_NETWORK_LIST@@@CspLoader@@@WcmCommon@@@std@@$$QEAV_lambda_1_@?5??GetNetworkList@CspLoader@@QEAAKPEAU_GUID@@PEAPEAUWCM_CSP_NETWORK_LIST@@@Z@@Z`
- size: `351`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001c9a8`

## callees

- `0x180010080`
- `0x180010560`
- `0x18001cad0`
- `0x18001cddc`
- `0x18001d53c`
- `0x18006de30`
- `0x18008534c`
- `0x180098260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cb0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cb0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cb38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cbee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cb38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cbee`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001cc03`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001cc03`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall Z::SubmitWorkWithResults<CspLoader::unique_csploader_out_params<WCM_CSP_NETWORK_LIST>,`CspLoader::GetNetworkList'::`6'::_lambda_1_,AKPEAU_GUID * const,WCM_CSP_NETWORK_LIST * *>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rdi
  char *v7; // r14
  char *v9; // [rsp+20h] [rbp-49h] BYREF
  std::_Ref_count_base *v10; // [rsp+28h] [rbp-41h]
  __int128 v11; // [rsp+30h] [rbp-39h]
  struct _RTL_CRITICAL_SECTION *v12; // [rsp+48h] [rbp-21h]
  _BYTE v13[80]; // [rsp+50h] [rbp-19h] BYREF

  v11 = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  v12 = v6;
  if ( *(_BYTE *)(a1 + 272) )
  {
    *a2 = 0;
    a2[1] = 0;
    if ( v6 )
      LeaveCriticalSection(v6);
  }
  else
  {
    v7 = (char *)operator new(0x88u);
    v9 = v7;
    *(_OWORD *)v7 = 0;
    *((_DWORD *)v7 + 2) = 1;
    *((_DWORD *)v7 + 3) = 1;
    *(_QWORD *)v7 = &std::_Ref_count_obj2<WcmCommon::ThreadPoolWaitableResult<CspLoader::unique_csploader_out_params<_WCM_CSP_PROFILE_LIST>>>::`vftable';
    ____0V_lambda_1___5__GetNetworkList_CspLoader__QEAAKPEAU_GUID__PEAPEAUWCM_CSP_NETWORK_LIST___Z____ThreadPoolWaitableResult_U__unique_csploader_out_params_UWCM_CSP_NETWORK_LIST___CspLoader___WcmCommon__QEAA___QEAV_lambda_1___5__GetNetworkList_CspLoader__QEAAKPEAU_GUID__PEAPEAUWCM_CSP_NETWORK_LIST___Z__Z(
      (__int64)(v7 + 16),
      a3);
    *(_QWORD *)&v11 = v7 + 16;
    *((_QWORD *)&v11 + 1) = v7;
    if ( *(_DWORD *)a1 == 1 )
    {
      _InterlockedIncrement((volatile signed __int32 *)v7 + 2);
      v9 = v7 + 16;
      v10 = (std::_Ref_count_base *)v7;
      std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(a1 + 192, &v9);
      if ( v10 )
        std::_Ref_count_base::_Decref(v10);
    }
    else
    {
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>();
      std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(
        (_QWORD *)(a1 + 232),
        (__int64)v13);
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(v13);
    }
    if ( v6 )
      LeaveCriticalSection(v6);
    _InterlockedIncrement64((volatile signed __int64 *)(a1 + 136));
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 128));
    *a2 = v7 + 16;
    a2[1] = v7;
  }
  return a2;
}

```

## disassembly

```asm
0x18001cad0  mov     [rsp-8+arg_10], rbx
0x18001cad5  mov     [rsp-8+arg_18], rsi
0x18001cada  push    rbp
0x18001cadb  push    rdi
0x18001cadc  push    r12
0x18001cade  push    r14
0x18001cae0  push    r15
0x18001cae2  lea     rbp, [rsp-37h]
0x18001cae7  sub     rsp, 0A0h
0x18001caee  mov     r12, r8
0x18001caf1  mov     rbx, rdx
0x18001caf4  mov     rsi, rcx
0x18001caf7  mov     [rbp+57h+var_78], rdx
0x18001cafb  xorps   xmm1, xmm1
0x18001cafe  movdqu  [rbp+57h+var_90], xmm1
0x18001cb03  lea     rdi, [rcx+8]
0x18001cb07  mov     rcx, rdi; lpCriticalSection
0x18001cb0a  call    cs:__imp_EnterCriticalSection
0x18001cb10  mov     [rbp+57h+var_78], rdi
0x18001cb14  cmp     byte ptr [rsi+110h], 0
0x18001cb1b  jz      short loc_18001CB43
0x18001cb1d  mov     qword ptr [rbx], 0
0x18001cb24  mov     qword ptr [rbx+8], 0
0x18001cb2c  test    rdi, rdi
0x18001cb2f  jz      loc_18001CC10
0x18001cb35  mov     rcx, rdi; lpCriticalSection
0x18001cb38  call    cs:__imp_LeaveCriticalSection
0x18001cb3e  jmp     loc_18001CC10
0x18001cb43  mov     ecx, 88h; Size
0x18001cb48  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cb4d  mov     r14, rax
0x18001cb50  mov     [rbp+57h+var_A0], rax
0x18001cb54  xorps   xmm0, xmm0
0x18001cb57  movups  xmmword ptr [rax], xmm0
0x18001cb5a  mov     dword ptr [rax+8], 1
0x18001cb61  mov     dword ptr [rax+0Ch], 1
0x18001cb68  lea     rax, ??_7?$_Ref_count_obj2@V?$ThreadPoolWaitableResult@U?$unique_csploader_out_params@U_WCM_CSP_PROFILE_LIST@@@CspLoader@@@WcmCommon@@@std@@6B@; const std::_Ref_count_obj2<WcmCommon::ThreadPoolWaitableResult<CspLoader::unique_csploader_out_params<_WCM_CSP_PROFILE_LIST>>>::`vftable'
0x18001cb6f  mov     [r14], rax
0x18001cb72  lea     r15, [r14+10h]
0x18001cb76  mov     rdx, r12
0x18001cb79  mov     rcx, r15
0x18001cb7c  call    ??$?0V_lambda_1_@?5??GetNetworkList@CspLoader@@QEAAKPEAU_GUID@@PEAPEAUWCM_CSP_NETWORK_LIST@@@Z@@?$ThreadPoolWaitableResult@U?$unique_csploader_out_params@UWCM_CSP_NETWORK_LIST@@@CspLoader@@@WcmCommon@@QEAA@$$QEAV_lambda_1_@?5??GetNetworkList@CspLoader@@QEAAKPEAU_GUID@@PEAPEAUWCM_CSP_NETWORK_LIST@@@Z@@Z; WcmCommon::ThreadPoolWaitableResult<CspLoader::unique_csploader_out_params<WCM_CSP_NETWORK_LIST>>::ThreadPoolWaitableResult<CspLoader::unique_csploader_out_params<WCM_CSP_NETWORK_LIST>>(`CspLoader::GetNetworkList(_GUID *,WCM_CSP_NETWORK_LIST * *)'::`6'::_lambda_1_ &&)
0x18001cb81  nop
0x18001cb82  mov     qword ptr [rbp+57h+var_90], r15
0x18001cb86  mov     qword ptr [rbp+57h+var_90+8], r14
0x18001cb8a  cmp     dword ptr [rsi], 1
0x18001cb8d  jnz     short loc_18001CBBD
0x18001cb8f  lea     rcx, [rsi+0C0h]
0x18001cb96  lock inc dword ptr [r14+8]
0x18001cb9b  mov     [rbp+57h+var_A0], r15
0x18001cb9f  mov     [rbp+57h+var_98], r14
0x18001cba3  lea     rdx, [rbp+57h+var_A0]
0x18001cba7  call    ?push_back@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@QEAAX$$QEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@Z; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> &&)
0x18001cbac  nop
0x18001cbad  mov     rcx, [rbp+57h+var_98]; this
0x18001cbb1  test    rcx, rcx
0x18001cbb4  jz      short loc_18001CBE6
0x18001cbb6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001cbbb  jmp     short loc_18001CBE6
0x18001cbbd  lea     rdx, [rbp+57h+var_90]
0x18001cbc1  lea     rcx, [rbp+57h+var_70]
0x18001cbc5  call    ??$?0AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@$0A@$0A@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@1@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<bool>> &)
0x18001cbca  nop
0x18001cbcb  lea     rdx, [rbp+57h+var_70]
0x18001cbcf  lea     rcx, [rsi+0E8h]
0x18001cbd6  call    ??$_Emplace_back_internal@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAX$$QEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &&)
0x18001cbdb  nop
0x18001cbdc  lea     rcx, [rbp+57h+var_70]
0x18001cbe0  call    ??1?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@XZ; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x18001cbe5  nop
0x18001cbe6  test    rdi, rdi
0x18001cbe9  jz      short loc_18001CBF4
0x18001cbeb  mov     rcx, rdi; lpCriticalSection
0x18001cbee  call    cs:__imp_LeaveCriticalSection
0x18001cbf4  lock inc qword ptr [rsi+88h]
0x18001cbfc  mov     rcx, [rsi+80h]; pwk
0x18001cc03  call    cs:__imp_SubmitThreadpoolWork
0x18001cc09  mov     [rbx], r15
0x18001cc0c  mov     [rbx+8], r14
0x18001cc10  mov     rax, rbx
0x18001cc13  lea     r11, [rsp+0C0h+var_20]
0x18001cc1b  mov     rbx, [r11+40h]
0x18001cc1f  mov     rsi, [r11+48h]
0x18001cc23  mov     rsp, r11
0x18001cc26  pop     r15
0x18001cc28  pop     r14
0x18001cc2a  pop     r12
0x18001cc2c  pop     rdi
0x18001cc2d  pop     rbp
0x18001cc2e  retn
```
