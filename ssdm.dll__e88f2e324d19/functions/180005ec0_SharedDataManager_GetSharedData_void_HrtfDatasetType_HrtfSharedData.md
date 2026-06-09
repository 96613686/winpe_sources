# SharedDataManager::GetSharedData(void *,_HrtfDatasetType,_HrtfSharedData * *)

- ea: `0x180005ec0`
- end: `0x1800060e8`
- name: `?GetSharedData@SharedDataManager@@QEAAXPEAXW4_HrtfDatasetType@@PEAPEAU_HrtfSharedData@@@Z`
- size: `552`
- prototype: `void __fastcall(__int64, void *, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180007ab0`

## callees

- `0x180002a88`
- `0x180004c60`
- `0x180005098`
- `0x180005a9c`
- `0x180005b40`
- `0x180005ec0`
- `0x1800069f0`
- `0x180007484`
- `0x18000b1bc`
- `0x18000c334`
- `0x18000c9a8`
- `0x18000cfd8`
- `0x180010010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006076`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006076`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f6e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005ef1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005ef1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800060ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800060ab`

## pseudocode

```c
void __fastcall SharedDataManager::GetSharedData(__int64 a1, void *a2, unsigned int a3, _QWORD *a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 *Local; // rax
  struct HrtfPersonalizationParams *PersonalizationParamsFromDefaultConfiguration; // rbx
  _DWORD *v12; // rax
  __int64 v13; // r8
  _DWORD *v14; // r14
  volatile signed __int32 *v15; // rsi
  __int64 v16; // rcx
  int v17; // [rsp+20h] [rbp-49h]
  void **v18; // [rsp+30h] [rbp-39h] BYREF
  _QWORD v19[2]; // [rsp+38h] [rbp-31h] BYREF
  __int64 v20; // [rsp+48h] [rbp-21h]
  DWORD CurrentThreadId; // [rsp+50h] [rbp-19h]
  __int64 v22; // [rsp+58h] [rbp-11h]
  char v23; // [rsp+60h] [rbp-9h]
  __int64 v24; // [rsp+68h] [rbp-1h]
  unsigned int *v25; // [rsp+70h] [rbp+7h]
  _DWORD *v26; // [rsp+80h] [rbp+17h]
  __int64 v27; // [rsp+88h] [rbp+1Fh]
  __int64 v28; // [rsp+90h] [rbp+27h]
  struct HrtfPersonalizationParams *v29; // [rsp+98h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  unsigned int v31; // [rsp+D0h] [rbp+67h] BYREF

  v17 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)a1);
  v28 = a1;
  v31 = ProcessMonitor::Watch((ProcessMonitor *)(a1 + 64), a2);
  v18 = &wil::details::ThreadFailureCallbackFn<_lambda_6b1d65cd1938606b4159120d1307db23_>::`vftable';
  v19[0] = 0;
  v19[1] = &v18;
  v20 = 0;
  CurrentThreadId = 0;
  v22 = 0;
  v23 = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(v8) = 1;
    Local = (__int64 *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                         v9,
                         v8);
    v19[0] = Local;
    if ( Local )
    {
      v20 = *Local;
      *Local = (__int64)v19;
      CurrentThreadId = GetCurrentThreadId();
    }
  }
  else
  {
    v19[0] = 0;
  }
  v24 = a1;
  v25 = &v31;
  if ( *(_QWORD *)(a1 + 48) )
  {
    SharedDataManager::QueuePersonalizationUpdate((SharedDataManager *)a1);
  }
  else
  {
    PersonalizationParamsFromDefaultConfiguration = SharedDataManager::GetPersonalizationParamsFromDefaultConfiguration((SharedDataManager *)a1);
    v29 = PersonalizationParamsFromDefaultConfiguration;
    *(_DWORD *)PersonalizationParamsFromDefaultConfiguration = LODWORD(FInf._Float) ^ _xmm;
    Personalizer::Process((Personalizer *)(a1 + 40), PersonalizationParamsFromDefaultConfiguration);
    v12 = operator new(0x60u);
    v14 = v12;
    v26 = v12;
    if ( v12 )
    {
      v12[2] = 1;
      v12[3] = 1;
      *(_QWORD *)v12 = &std::_Ref_count_obj<HrtfSharedDataInstance>::`vftable';
      HrtfSharedDataInstance::HrtfSharedDataInstance(
        v12 + 4,
        PersonalizationParamsFromDefaultConfiguration,
        v13,
        (char *)PersonalizationParamsFromDefaultConfiguration + 56,
        0);
    }
    else
    {
      v14 = 0;
    }
    v17 = 1;
    v27 = 0;
    v26 = 0;
    v15 = *(volatile signed __int32 **)(a1 + 56);
    *(_QWORD *)(a1 + 56) = v14;
    *(_QWORD *)(a1 + 48) = v14 + 4;
    if ( v15 )
    {
      if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      }
    }
    HrtfPersonalizationParams::~HrtfPersonalizationParams(PersonalizationParamsFromDefaultConfiguration);
    operator delete(PersonalizationParamsFromDefaultConfiguration);
  }
  v16 = *(_QWORD *)(a1 + 48);
  if ( !v16 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\spatialsounddatamanager.cpp",
      (const char *)0x8000FFFFLL,
      v17);
  *a4 = HrtfSharedDataInstance::AcquireSharedDataForClient(v16, v31, a3);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v19);
  LeaveCriticalSection((LPCRITICAL_SECTION)a1);
}

```

## disassembly

```asm
0x180005ec0  mov     [rsp-8+arg_8], rbx
0x180005ec5  mov     [rsp-8+arg_10], rsi
0x180005eca  push    rbp
0x180005ecb  push    rdi
0x180005ecc  push    r12
0x180005ece  push    r14
0x180005ed0  push    r15
0x180005ed2  lea     rbp, [rsp-37h]
0x180005ed7  sub     rsp, 0A0h
0x180005ede  mov     r15, r9
0x180005ee1  mov     r12d, r8d
0x180005ee4  mov     rbx, rdx
0x180005ee7  mov     rdi, rcx
0x180005eea  mov     [rbp+57h+var_A0], 0
0x180005ef1  call    cs:__imp_EnterCriticalSection
0x180005ef7  mov     [rbp+57h+var_30], rdi
0x180005efb  lea     rcx, [rdi+40h]; this
0x180005eff  mov     rdx, rbx; void *
0x180005f02  call    ?Watch@ProcessMonitor@@QEAAKPEAX@Z; ProcessMonitor::Watch(void *)
0x180005f07  mov     [rbp+57h+arg_0], eax
0x180005f0a  lea     rax, ??_7?$ThreadFailureCallbackFn@V_lambda_6b1d65cd1938606b4159120d1307db23_@@@details@wil@@6B@; const wil::details::ThreadFailureCallbackFn<_lambda_6b1d65cd1938606b4159120d1307db23_>::`vftable'
0x180005f11  mov     [rbp+57h+var_90], rax
0x180005f15  mov     [rbp+57h+var_88], 0
0x180005f1d  lea     rax, [rbp+57h+var_90]
0x180005f21  mov     [rbp+57h+var_80], rax
0x180005f25  mov     [rbp+57h+var_78], 0
0x180005f2d  mov     [rbp+57h+var_70], 0
0x180005f34  mov     [rbp+57h+var_68], 0
0x180005f3c  mov     [rbp+57h+var_60], 0
0x180005f40  mov     esi, 1
0x180005f45  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005f4d  jz      short loc_180005F79
0x180005f4f  mov     dl, sil
0x180005f52  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180005f57  mov     [rbp+57h+var_88], rax
0x180005f5b  test    rax, rax
0x180005f5e  jz      short loc_180005F81
0x180005f60  mov     rcx, [rax]
0x180005f63  mov     [rbp+57h+var_78], rcx
0x180005f67  lea     rcx, [rbp+57h+var_88]
0x180005f6b  mov     [rax], rcx
0x180005f6e  call    cs:__imp_GetCurrentThreadId
0x180005f74  mov     [rbp+57h+var_70], eax
0x180005f77  jmp     short loc_180005F81
0x180005f79  mov     [rbp+57h+var_88], 0
0x180005f81  mov     [rbp+57h+var_58], rdi
0x180005f85  lea     rax, [rbp+57h+arg_0]
0x180005f89  mov     [rbp+57h+var_50], rax
0x180005f8d  mov     rcx, rdi; this
0x180005f90  cmp     qword ptr [rdi+30h], 0
0x180005f95  jnz     loc_18000607E
0x180005f9b  call    ?GetPersonalizationParamsFromDefaultConfiguration@SharedDataManager@@AEAAPEAUHrtfPersonalizationParams@@XZ; SharedDataManager::GetPersonalizationParamsFromDefaultConfiguration(void)
0x180005fa0  mov     rbx, rax
0x180005fa3  mov     [rbp+57h+var_28], rax
0x180005fa7  movss   xmm0, dword ptr cs:_FInf
0x180005faf  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x180005fb6  movss   dword ptr [rax], xmm0
0x180005fba  lea     rcx, [rdi+28h]; this
0x180005fbe  mov     rdx, rax; struct HrtfPersonalizationParams *
0x180005fc1  call    ?Process@Personalizer@@QEAAXPEAUHrtfPersonalizationParams@@@Z; Personalizer::Process(HrtfPersonalizationParams *)
0x180005fc6  nop
0x180005fc7  mov     ecx, 60h ; '`'; Size
0x180005fcc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005fd1  mov     r14, rax
0x180005fd4  mov     [rbp+57h+var_40], rax
0x180005fd8  test    rax, rax
0x180005fdb  jz      short loc_180006004
0x180005fdd  mov     [rax+8], esi
0x180005fe0  mov     [rax+0Ch], esi
0x180005fe3  lea     rax, ??_7?$_Ref_count_obj@VHrtfSharedDataInstance@@@std@@6B@; const std::_Ref_count_obj<HrtfSharedDataInstance>::`vftable'
0x180005fea  mov     [r14], rax
0x180005fed  lea     r9, [rbx+38h]
0x180005ff1  lea     rcx, [r14+10h]
0x180005ff5  movss   xmm2, dword ptr [rbx]
0x180005ff9  mov     rdx, rbx
0x180005ffc  call    ??0HrtfSharedDataInstance@@QEAA@AEBUHrtfDataDesc@@MAEBV?$vector@UHrtfDataDesc@@V?$allocator@UHrtfDataDesc@@@std@@@std@@@Z; HrtfSharedDataInstance::HrtfSharedDataInstance(HrtfDataDesc const &,float,std::vector<HrtfDataDesc> const &)
0x180006001  nop
0x180006002  jmp     short loc_180006007
0x180006004  xor     r14d, r14d
0x180006007  mov     [rbp+57h+var_A0], esi
0x18000600a  mov     [rbp+57h+var_38], 0
0x180006012  mov     [rbp+57h+var_40], 0
0x18000601a  mov     rsi, [rdi+38h]
0x18000601e  mov     [rdi+38h], r14
0x180006022  lea     rax, [r14+10h]
0x180006026  mov     [rdi+30h], rax
0x18000602a  test    rsi, rsi
0x18000602d  jz      short loc_18000606B
0x18000602f  or      r14d, 0FFFFFFFFh
0x180006033  mov     eax, r14d
0x180006036  lock xadd [rsi+8], eax
0x18000603b  add     eax, r14d
0x18000603e  jnz     short loc_18000606B
0x180006040  mov     rax, [rsi]
0x180006043  mov     rcx, rsi
0x180006046  mov     rax, [rax]
0x180006049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000604e  mov     eax, r14d
0x180006051  lock xadd [rsi+0Ch], eax
0x180006056  add     eax, r14d
0x180006059  jnz     short loc_18000606B
0x18000605b  mov     rax, [rsi]
0x18000605e  mov     rcx, rsi
0x180006061  mov     rax, [rax+8]
0x180006065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000606a  nop
0x18000606b  mov     rcx, rbx; this
0x18000606e  call    ??1HrtfPersonalizationParams@@QEAA@XZ; HrtfPersonalizationParams::~HrtfPersonalizationParams(void)
0x180006073  mov     rcx, rbx
0x180006076  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000607c  jmp     short loc_180006083
0x18000607e  call    ?QueuePersonalizationUpdate@SharedDataManager@@AEAAXXZ; SharedDataManager::QueuePersonalizationUpdate(void)
0x180006083  mov     rax, [rbp+5Fh]
0x180006087  mov     rcx, [rdi+30h]
0x18000608b  test    rcx, rcx
0x18000608e  jz      short loc_1800060CD
0x180006090  mov     r8d, r12d
0x180006093  mov     edx, [rbp+57h+arg_0]
0x180006096  call    ?AcquireSharedDataForClient@HrtfSharedDataInstance@@QEAAPEAU_HrtfSharedData@@KW4_HrtfDatasetType@@@Z; HrtfSharedDataInstance::AcquireSharedDataForClient(ulong,_HrtfDatasetType)
0x18000609b  mov     [r15], rax
0x18000609e  lea     rcx, [rbp+57h+var_88]; this
0x1800060a2  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800060a7  nop
0x1800060a8  mov     rcx, rdi; lpCriticalSection
0x1800060ab  call    cs:__imp_LeaveCriticalSection
0x1800060b1  lea     r11, [rsp+0C0h+var_20]
0x1800060b9  mov     rbx, [r11+38h]
0x1800060bd  mov     rsi, [r11+40h]
0x1800060c1  mov     rsp, r11
0x1800060c4  pop     r15
0x1800060c6  pop     r14
0x1800060c8  pop     r12
0x1800060ca  pop     rdi
0x1800060cb  pop     rbp
0x1800060cc  retn
0x1800060cd  mov     r9d, 8000FFFFh; char *
0x1800060d3  lea     r8, aAvcoreXaudioHr_3; "avcore\\xaudio\\hrtf\\ssdm\\lib\\spatia"...
0x1800060da  mov     edx, 66h ; 'f'; void *
0x1800060df  mov     rcx, rax; this
0x1800060e2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
