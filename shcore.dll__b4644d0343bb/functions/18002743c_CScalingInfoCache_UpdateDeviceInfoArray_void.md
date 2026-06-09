# CScalingInfoCache::_UpdateDeviceInfoArray(void)

- ea: `0x18002743c`
- end: `0x1800276d9`
- name: `?_UpdateDeviceInfoArray@CScalingInfoCache@@AEAAXXZ`
- size: `669`
- prototype: `void __fastcall(CScalingInfoCache *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180027ed0`
- `0x180071ca0`

## callees

- `0x18000ddd4`
- `0x18002743c`
- `0x1800278c0`
- `0x1800279f4`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002748d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002756c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002748d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002756c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027676`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027676`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002745a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002745a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002758d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800275cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002758d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800275cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027474`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027474`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800275b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800275b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CScalingInfoCache::_UpdateDeviceInfoArray(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rbx
  int v3; // r12d
  unsigned __int64 v4; // r13
  unsigned __int64 v5; // rdi
  char *v6; // r14
  PVOID Ptr; // rsi
  char *v8; // rax
  void *v9; // r13
  unsigned __int64 i; // rsi
  void *j; // rsi
  unsigned __int64 k; // rbx
  __int64 v13; // rsi
  char *v14; // rax
  PVOID v15; // [rsp+20h] [rbp-38h] BYREF
  __int64 v16; // [rsp+28h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-28h] BYREF
  __int64 v18; // [rsp+38h] [rbp-20h]
  __int64 v19; // [rsp+40h] [rbp-18h]
  __int64 v20; // [rsp+48h] [rbp-10h]

  v2 = this + 5;
  AcquireSRWLockExclusive(this + 5);
  CTSimpleArray<CScalingInfoCache::MONITOR_SCALE_INFO,4294967294,CTPolicyCoTaskMem<CScalingInfoCache::MONITOR_SCALE_INFO>,CSimpleArrayStandardCompareHelper<CScalingInfoCache::MONITOR_SCALE_INFO>,CSimpleArrayStandardMergeHelper<CScalingInfoCache::MONITOR_SCALE_INFO>>::RemoveAll(&this[11]);
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  pv = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  AcquireSRWLockShared(v2);
  v3 = CTSimpleArray<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>>>::_EnsureCapacity(
         &pv,
         (char *)this[8].Ptr + 3);
  v4 = 0;
  v5 = v18;
  v6 = (char *)pv;
  do
  {
    if ( v3 < 0 )
      break;
    Ptr = this[v4 + 2].Ptr;
    if ( Ptr )
    {
      v15 = this[v4 + 2].Ptr;
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 8LL))(Ptr);
      v3 = 0;
      if ( v5 != v20
        || (v3 = CTSimpleArray<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>>>::_EnsureCapacity(
                   &pv,
                   v5 + 1),
            v5 = v18,
            v6 = (char *)pv,
            v3 >= 0) )
      {
        v18 = ++v5;
        v8 = &v6[8 * v5 - 8];
        if ( v8 )
        {
          *(_QWORD *)v8 = 0;
          if ( v8 != (char *)&v15 )
          {
            *(_QWORD *)v8 = Ptr;
            Ptr = 0;
          }
        }
      }
      if ( Ptr )
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
    }
    ++v4;
  }
  while ( v4 < 3 );
  v9 = 0;
  while ( v9 < this[8].Ptr )
  {
    if ( v3 < 0 )
      break;
    v13 = *((_QWORD *)this[7].Ptr + 2 * (_QWORD)v9 + 1);
    v16 = v13;
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
    v3 = 0;
    if ( v5 == v20 )
    {
      v3 = CTSimpleArray<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>>>::_EnsureCapacity(
             &pv,
             v5 + 1);
      v5 = v18;
      v6 = (char *)pv;
      if ( v3 < 0 )
        continue;
    }
    v18 = ++v5;
    v14 = &v6[8 * v5 - 8];
    if ( v14 )
    {
      *(_QWORD *)v14 = 0;
      if ( v14 != (char *)&v16 )
      {
        *(_QWORD *)v14 = v13;
        v13 = 0;
      }
    }
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v9 = (char *)v9 + 1;
  }
  if ( v2 )
    ReleaseSRWLockShared(v2);
  if ( v3 >= 0 )
  {
    for ( i = 0; i < v5; ++i )
      (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)&v6[8 * i] + 96LL))(*(_QWORD *)&v6[8 * i], 0);
  }
  AcquireSRWLockShared(v2);
  for ( j = 0; j < this[16].Ptr; j = (char *)j + 1 )
    SetEvent(*((HANDLE *)this[15].Ptr + 2 * (_QWORD)j));
  if ( v2 )
    ReleaseSRWLockShared(v2);
  if ( v6 )
  {
    for ( k = 0; k < v5; ++k )
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v6[8 * k]);
    CoTaskMemFree(v6);
  }
}

```

## disassembly

```asm
0x18002743c  push    rbp
0x18002743e  push    rbx
0x18002743f  push    rsi
0x180027440  push    rdi
0x180027441  push    r12
0x180027443  push    r13
0x180027445  push    r14
0x180027447  push    r15
0x180027449  mov     rbp, rsp
0x18002744c  sub     rsp, 58h
0x180027450  mov     r15, rcx
0x180027453  lea     rbx, [rcx+28h]
0x180027457  mov     rcx, rbx; SRWLock
0x18002745a  call    cs:__imp_AcquireSRWLockExclusive
0x180027460  lea     rcx, [r15+58h]
0x180027464  call    ?RemoveAll@?$CTSimpleArray@UMONITOR_SCALE_INFO@CScalingInfoCache@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UMONITOR_SCALE_INFO@CScalingInfoCache@@@@V?$CSimpleArrayStandardCompareHelper@UMONITOR_SCALE_INFO@CScalingInfoCache@@@@V?$CSimpleArrayStandardMergeHelper@UMONITOR_SCALE_INFO@CScalingInfoCache@@@@@@QEAAXXZ; CTSimpleArray<CScalingInfoCache::MONITOR_SCALE_INFO,4294967294,CTPolicyCoTaskMem<CScalingInfoCache::MONITOR_SCALE_INFO>,CSimpleArrayStandardCompareHelper<CScalingInfoCache::MONITOR_SCALE_INFO>,CSimpleArrayStandardMergeHelper<CScalingInfoCache::MONITOR_SCALE_INFO>>::RemoveAll(void)
0x180027469  xor     r12d, r12d
0x18002746c  test    rbx, rbx
0x18002746f  jz      short loc_18002747A
0x180027471  mov     rcx, rbx; SRWLock
0x180027474  call    cs:__imp_ReleaseSRWLockExclusive
0x18002747a  mov     [rbp+pv], r12
0x18002747e  mov     [rbp+var_20], r12
0x180027482  mov     [rbp+var_18], r12
0x180027486  mov     [rbp+var_10], r12
0x18002748a  mov     rcx, rbx; SRWLock
0x18002748d  call    cs:__imp_AcquireSRWLockShared
0x180027493  mov     [rbp+arg_0], rbx
0x180027497  mov     rdx, [r15+40h]
0x18002749b  add     rdx, 3
0x18002749f  lea     rcx, [rbp+pv]
0x1800274a3  call    ?_EnsureCapacity@?$CTSimpleArray@V?$ComPtr@UICurrentWindowChangeListener@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@UICurrentWindowChangeListener@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UICurrentWindowChangeListener@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@UICurrentWindowChangeListener@@@WRL@Microsoft@@@@@@QEAAJ_K0@Z; CTSimpleArray<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x1800274a8  mov     r12d, eax
0x1800274ab  xor     r13d, r13d
0x1800274ae  mov     rdi, [rbp+var_20]
0x1800274b2  mov     r14, [rbp+pv]
0x1800274b6  test    r12d, r12d
0x1800274b9  js      short loc_18002752D
0x1800274bb  mov     rsi, [r15+r13*8+10h]
0x1800274c0  test    rsi, rsi
0x1800274c3  jz      short loc_180027524
0x1800274c5  mov     [rbp+var_38], rsi
0x1800274c9  mov     rax, [rsi]
0x1800274cc  mov     rcx, rsi
0x1800274cf  mov     rax, [rax+8]
0x1800274d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274d8  nop
0x1800274d9  xor     r12d, r12d
0x1800274dc  cmp     rdi, [rbp+var_10]
0x1800274e0  jz      loc_18002768E
0x1800274e6  inc     rdi
0x1800274e9  mov     [rbp+var_20], rdi
0x1800274ed  lea     rax, [rdi-1]
0x1800274f1  lea     rax, [r14+rax*8]
0x1800274f5  test    rax, rax
0x1800274f8  jz      short loc_18002750F
0x1800274fa  mov     qword ptr [rax], 0
0x180027501  lea     rcx, [rbp+var_38]
0x180027505  cmp     rax, rcx
0x180027508  jz      short loc_18002750F
0x18002750a  mov     [rax], rsi
0x18002750d  xor     esi, esi
0x18002750f  test    rsi, rsi
0x180027512  jz      short loc_180027524
0x180027514  mov     rax, [rsi]
0x180027517  mov     rcx, rsi
0x18002751a  mov     rax, [rax+10h]
0x18002751e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027523  nop
0x180027524  inc     r13
0x180027527  cmp     r13, 3
0x18002752b  jb      short loc_1800274B6
0x18002752d  xor     r13d, r13d
0x180027530  cmp     [r15+40h], r13
0x180027534  ja      loc_1800275DA
0x18002753a  test    rbx, rbx
0x18002753d  jnz     loc_1800275CC
0x180027543  test    r12d, r12d
0x180027546  js      short loc_180027569
0x180027548  xor     esi, esi
0x18002754a  test    rdi, rdi
0x18002754d  jz      short loc_180027569
0x18002754f  mov     rcx, [r14+rsi*8]
0x180027553  mov     rax, [rcx]
0x180027556  xor     edx, edx
0x180027558  mov     rax, [rax+60h]
0x18002755c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027561  inc     rsi
0x180027564  cmp     rsi, rdi
0x180027567  jb      short loc_18002754F
0x180027569  mov     rcx, rbx; SRWLock
0x18002756c  call    cs:__imp_AcquireSRWLockShared
0x180027572  xor     r12d, r12d
0x180027575  mov     esi, r12d
0x180027578  cmp     [r15+80h], r12
0x18002757f  ja      loc_180027668
0x180027585  test    rbx, rbx
0x180027588  jz      short loc_180027594
0x18002758a  mov     rcx, rbx; SRWLock
0x18002758d  call    cs:__imp_ReleaseSRWLockShared
0x180027593  nop
0x180027594  test    r14, r14
0x180027597  jz      short loc_1800275BB
0x180027599  mov     rbx, r12
0x18002759c  test    rdi, rdi
0x18002759f  jz      short loc_1800275B2
0x1800275a1  lea     rcx, [r14+rbx*8]
0x1800275a5  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x1800275aa  inc     rbx
0x1800275ad  cmp     rbx, rdi
0x1800275b0  jb      short loc_1800275A1
0x1800275b2  mov     rcx, r14; pv
0x1800275b5  call    cs:__imp_CoTaskMemFree
0x1800275bb  add     rsp, 58h
0x1800275bf  pop     r15
0x1800275c1  pop     r14
0x1800275c3  pop     r13
0x1800275c5  pop     r12
0x1800275c7  pop     rdi
0x1800275c8  pop     rsi
0x1800275c9  pop     rbx
0x1800275ca  pop     rbp
0x1800275cb  retn
0x1800275cc  mov     rcx, rbx; SRWLock
0x1800275cf  call    cs:__imp_ReleaseSRWLockShared
0x1800275d5  jmp     loc_180027543
0x1800275da  test    r12d, r12d
0x1800275dd  js      loc_18002753A
0x1800275e3  mov     rcx, r13
0x1800275e6  add     rcx, rcx
0x1800275e9  mov     rax, [r15+38h]
0x1800275ed  mov     rsi, [rax+rcx*8+8]
0x1800275f2  mov     [rbp+var_30], rsi
0x1800275f6  test    rsi, rsi
0x1800275f9  jz      short loc_18002760B
0x1800275fb  mov     rax, [rsi]
0x1800275fe  mov     rcx, rsi
0x180027601  mov     rax, [rax+8]
0x180027605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002760a  nop
0x18002760b  xor     r12d, r12d
0x18002760e  cmp     rdi, [rbp+var_10]
0x180027612  jz      loc_1800276B3
0x180027618  inc     rdi
0x18002761b  mov     [rbp+var_20], rdi
0x18002761f  lea     rax, [rdi-1]
0x180027623  lea     rax, [r14+rax*8]
0x180027627  test    rax, rax
0x18002762a  jz      short loc_180027641
0x18002762c  mov     qword ptr [rax], 0
0x180027633  lea     rcx, [rbp+var_30]
0x180027637  cmp     rax, rcx
0x18002763a  jz      short loc_180027641
0x18002763c  mov     [rax], rsi
0x18002763f  xor     esi, esi
0x180027641  test    rsi, rsi
0x180027644  jz      short loc_180027656
0x180027646  mov     rax, [rsi]
0x180027649  mov     rcx, rsi
0x18002764c  mov     rax, [rax+10h]
0x180027650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027655  nop
0x180027656  inc     r13
0x180027659  cmp     r13, [r15+40h]
0x18002765d  jnb     loc_18002753A
0x180027663  jmp     loc_1800275DA
0x180027668  mov     rax, rsi
0x18002766b  add     rax, rax
0x18002766e  mov     rcx, [r15+78h]
0x180027672  mov     rcx, [rcx+rax*8]; hEvent
0x180027676  call    cs:__imp_SetEvent
0x18002767c  inc     rsi
0x18002767f  cmp     rsi, [r15+80h]
0x180027686  jnb     loc_180027585
0x18002768c  jmp     short loc_180027668
0x18002768e  lea     rdx, [rdi+1]
0x180027692  lea     rcx, [rbp+pv]
0x180027696  call    ?_EnsureCapacity@?$CTSimpleArray@V?$ComPtr@UICurrentWindowChangeListener@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@UICurrentWindowChangeListener@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UICurrentWindowChangeListener@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@UICurrentWindowChangeListener@@@WRL@Microsoft@@@@@@QEAAJ_K0@Z; CTSimpleArray<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18002769b  mov     r12d, eax
0x18002769e  mov     rdi, [rbp+var_20]
0x1800276a2  mov     r14, [rbp+pv]
0x1800276a6  test    eax, eax
0x1800276a8  js      loc_18002750F
0x1800276ae  jmp     loc_1800274E6
0x1800276b3  lea     rdx, [rdi+1]
0x1800276b7  lea     rcx, [rbp+pv]
0x1800276bb  call    ?_EnsureCapacity@?$CTSimpleArray@V?$ComPtr@UICurrentWindowChangeListener@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@UICurrentWindowChangeListener@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UICurrentWindowChangeListener@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@UICurrentWindowChangeListener@@@WRL@Microsoft@@@@@@QEAAJ_K0@Z; CTSimpleArray<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x1800276c0  mov     r12d, eax
0x1800276c3  mov     rdi, [rbp+var_20]
0x1800276c7  mov     r14, [rbp+pv]
0x1800276cb  test    eax, eax
0x1800276cd  js      loc_180027641
0x1800276d3  jmp     loc_180027618
```
