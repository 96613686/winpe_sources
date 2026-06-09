# CExec::TrackProcess(ulong,std::shared_ptr<CExec::ProcessTracker> &&)

- ea: `0x1400e3b1c`
- end: `0x1400e3d50`
- name: `?TrackProcess@CExec@@YAXK$$QEAV?$shared_ptr@UProcessTracker@CExec@@@std@@@Z`
- size: `564`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400e0b10`

## callees

- `0x1400056fc`
- `0x14000ddac`
- `0x140038dd4`
- `0x1400392a8`
- `0x14005f52c`
- `0x1400e3b1c`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400e3d14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400e3d14`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400e3b8e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400e3b8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e3b6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e3b6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e3b59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e3b59`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1400e3b47`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1400e3b47`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400e3d00`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400e3d00`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1400e3b64`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1400e3b64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400e3b94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400e3b94`

## string_xrefs

- `0x1400e3d3e`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CExec::TrackProcess(unsigned int a1, __int64 a2)
{
  PVOID v4; // rsi
  const char *v5; // r9
  PTP_WAIT ThreadpoolWait; // r15
  struct _TP_WAIT *v7; // r14
  DWORD LastError; // ebx
  void *v9; // r14
  void **v10; // r15
  int v11; // esi
  void **inserted; // r8
  void **v13; // rax
  _DWORD *v14; // rbx
  __int64 v15; // rax
  void *v16; // rdx
  volatile signed __int32 *v17; // rbx
  void **v18; // [rsp+20h] [rbp-58h] BYREF
  unsigned __int64 v19; // [rsp+28h] [rbp-50h]
  __int64 v20; // [rsp+30h] [rbp-48h]
  RTL_SRWLOCK *v21; // [rsp+38h] [rbp-40h]
  char v22; // [rsp+40h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v4 = *(PVOID *)a2;
  ThreadpoolWait = CreateThreadpoolWait(CExec::ProcessExitCallback, *(PVOID *)a2, 0);
  v7 = (struct _TP_WAIT *)*((_QWORD *)v4 + 5);
  if ( v7 )
  {
    LastError = GetLastError();
    CloseThreadpoolWait(v7);
    SetLastError(LastError);
  }
  *((_QWORD *)v4 + 5) = ThreadpoolWait;
  if ( !*(_QWORD *)(*(_QWORD *)a2 + 40LL) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x11C,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      v5);
  AcquireSRWLockExclusive(&CExec::g_ContainerProcessesLock);
  dword_14015FED8 = GetCurrentThreadId();
  v21 = &CExec::g_ContainerProcessesLock;
  v22 = 1;
  v9 = CExec::g_ContainerProcesses;
  v10 = (void **)*((_QWORD *)CExec::g_ContainerProcesses + 1);
  v11 = 0;
  v20 = 0;
  inserted = (void **)CExec::g_ContainerProcesses;
  v13 = v10;
  while ( !*((_BYTE *)v13 + 25) )
  {
    v10 = v13;
    if ( *((_DWORD *)v13 + 8) >= a1 )
    {
      v11 = 1;
      inserted = v13;
      v13 = (void **)*v13;
    }
    else
    {
      v11 = 0;
      v13 = (void **)v13[2];
    }
  }
  if ( *((_BYTE *)inserted + 25) || a1 < *((_DWORD *)inserted + 8) )
  {
    if ( qword_14015FEC8 == 0x492492492492492LL )
      std::_Throw_tree_length_error();
    v18 = &CExec::g_ContainerProcesses;
    v14 = operator new(0x38u);
    v14[8] = a1;
    *((_QWORD *)v14 + 5) = 0;
    *((_QWORD *)v14 + 6) = 0;
    *(_QWORD *)v14 = v9;
    *((_QWORD *)v14 + 1) = v9;
    *((_QWORD *)v14 + 2) = v9;
    *((_WORD *)v14 + 12) = 0;
    v19 = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<TransportIoContext * const,std::shared_ptr<TransportIoContext>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<TransportIoContext * const,std::shared_ptr<TransportIoContext>>,void *>>>(&v18);
    v18 = v10;
    v19 = __PAIR64__(v20, v11);
    inserted = (void **)std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Schema::Responses::Service::PropertyResponse>>>::_Insert_node(
                          &CExec::g_ContainerProcesses,
                          &v18);
  }
  v15 = *(_QWORD *)(a2 + 8);
  if ( v15 )
    _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
  v16 = *(void **)(a2 + 8);
  inserted[5] = *(void **)a2;
  v17 = (volatile signed __int32 *)inserted[6];
  inserted[6] = v16;
  if ( v17 )
  {
    if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
      if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
    }
  }
  SetThreadpoolWait(*(PTP_WAIT *)(*(_QWORD *)a2 + 40LL), **(HANDLE **)a2, 0);
  dword_14015FED8 = 0;
  ReleaseSRWLockExclusive(&CExec::g_ContainerProcessesLock);
}

```

## disassembly

```asm
0x1400e3b1c  mov     [rsp+arg_0], rbx
0x1400e3b21  mov     [rsp+arg_10], rbp
0x1400e3b26  push    rsi
0x1400e3b27  push    rdi
0x1400e3b28  push    r12
0x1400e3b2a  push    r14
0x1400e3b2c  push    r15
0x1400e3b2e  sub     rsp, 50h
0x1400e3b32  mov     rdi, rdx
0x1400e3b35  mov     ebp, ecx
0x1400e3b37  mov     rsi, [rdx]
0x1400e3b3a  xor     r8d, r8d; pcbe
0x1400e3b3d  mov     rdx, rsi; pv
0x1400e3b40  lea     rcx, ?ProcessExitCallback@CExec@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1400e3b47  call    cs:__imp_CreateThreadpoolWait
0x1400e3b4d  mov     r15, rax
0x1400e3b50  mov     r14, [rsi+28h]
0x1400e3b54  test    r14, r14
0x1400e3b57  jz      short loc_1400E3B72
0x1400e3b59  call    cs:__imp_GetLastError
0x1400e3b5f  mov     ebx, eax
0x1400e3b61  mov     rcx, r14; pwa
0x1400e3b64  call    cs:__imp_CloseThreadpoolWait
0x1400e3b6a  mov     ecx, ebx; dwErrCode
0x1400e3b6c  call    cs:__imp_SetLastError
0x1400e3b72  mov     [rsi+28h], r15
0x1400e3b76  mov     rax, [rdi]
0x1400e3b79  cmp     qword ptr [rax+28h], 0
0x1400e3b7e  jz      loc_1400E3D39
0x1400e3b84  lea     r12, ?g_ContainerProcessesLock@CExec@@3VVmSlimReaderWriterLock@Vml@@A; Vml::VmSlimReaderWriterLock CExec::g_ContainerProcessesLock
0x1400e3b8b  mov     rcx, r12; SRWLock
0x1400e3b8e  call    cs:__imp_AcquireSRWLockExclusive
0x1400e3b94  call    cs:__imp_GetCurrentThreadId
0x1400e3b9a  mov     cs:dword_14015FED8, eax
0x1400e3ba0  mov     [rsp+78h+var_40], r12
0x1400e3ba5  mov     [rsp+78h+var_38], 1
0x1400e3baa  mov     r14, cs:?g_ContainerProcesses@CExec@@3V?$map@KV?$shared_ptr@UProcessTracker@CExec@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@@2@@std@@A; std::map<ulong,std::shared_ptr<CExec::ProcessTracker>> CExec::g_ContainerProcesses
0x1400e3bb1  mov     r15, [r14+8]
0x1400e3bb5  xor     esi, esi
0x1400e3bb7  xor     eax, eax
0x1400e3bb9  mov     [rsp+78h+var_48], rax
0x1400e3bbe  mov     r8, r14
0x1400e3bc1  mov     rax, r15
0x1400e3bc4  cmp     [r15+19h], sil
0x1400e3bc8  jnz     short loc_1400E3BEB
0x1400e3bca  mov     r15, rax
0x1400e3bcd  cmp     [rax+20h], ebp
0x1400e3bd0  jnb     short loc_1400E3BDA
0x1400e3bd2  xor     esi, esi
0x1400e3bd4  mov     rax, [rax+10h]
0x1400e3bd8  jmp     short loc_1400E3BE5
0x1400e3bda  mov     esi, 1
0x1400e3bdf  mov     r8, rax
0x1400e3be2  mov     rax, [rax]
0x1400e3be5  cmp     byte ptr [rax+19h], 0
0x1400e3be9  jz      short loc_1400E3BCA
0x1400e3beb  cmp     byte ptr [r8+19h], 0
0x1400e3bf0  jnz     short loc_1400E3BFC
0x1400e3bf2  cmp     ebp, [r8+20h]
0x1400e3bf6  jnb     loc_1400E3C98
0x1400e3bfc  mov     rax, 492492492492492h
0x1400e3c06  cmp     cs:qword_14015FEC8, rax
0x1400e3c0d  jz      loc_1400E3D33
0x1400e3c13  lea     r12, ?g_ContainerProcesses@CExec@@3V?$map@KV?$shared_ptr@UProcessTracker@CExec@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@@2@@std@@A; std::map<ulong,std::shared_ptr<CExec::ProcessTracker>> CExec::g_ContainerProcesses
0x1400e3c1a  mov     [rsp+78h+var_58], r12
0x1400e3c1f  mov     [rsp+78h+var_50], 0
0x1400e3c28  mov     ecx, 38h ; '8'; Size
0x1400e3c2d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400e3c32  mov     rbx, rax
0x1400e3c35  mov     [rax+20h], ebp
0x1400e3c38  mov     qword ptr [rax+28h], 0
0x1400e3c40  mov     qword ptr [rax+30h], 0
0x1400e3c48  mov     [rax], r14
0x1400e3c4b  mov     [rax+8], r14
0x1400e3c4f  mov     [rax+10h], r14
0x1400e3c53  mov     word ptr [rax+18h], 0
0x1400e3c59  mov     [rsp+78h+var_50], 0
0x1400e3c62  lea     rcx, [rsp+78h+var_58]
0x1400e3c67  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@QEAVTransportIoContext@@V?$shared_ptr@VTransportIoContext@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<TransportIoContext * const,std::shared_ptr<TransportIoContext>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<TransportIoContext * const,std::shared_ptr<TransportIoContext>>,void *>>>(void)
0x1400e3c6c  mov     [rsp+78h+var_58], r15
0x1400e3c71  mov     dword ptr [rsp+78h+var_50], esi
0x1400e3c75  mov     rax, [rsp+78h+var_48]
0x1400e3c7a  mov     dword ptr [rsp+78h+var_50+4], eax
0x1400e3c7e  mov     r8, rbx
0x1400e3c81  lea     rdx, [rsp+78h+var_58]
0x1400e3c86  mov     rcx, r12
0x1400e3c89  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPropertyResponse@Service@Responses@Schema@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPropertyResponse@Service@Responses@Schema@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPropertyResponse@Service@Responses@Schema@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Schema::Responses::Service::PropertyResponse>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,Schema::Responses::Service::PropertyResponse>,void *> *>,std::_Tree_node<std::pair<std::wstring const,Schema::Responses::Service::PropertyResponse>,void *> * const)
0x1400e3c8e  mov     r8, rax
0x1400e3c91  lea     r12, ?g_ContainerProcessesLock@CExec@@3VVmSlimReaderWriterLock@Vml@@A; Vml::VmSlimReaderWriterLock CExec::g_ContainerProcessesLock
0x1400e3c98  mov     rax, [rdi+8]
0x1400e3c9c  test    rax, rax
0x1400e3c9f  jz      short loc_1400E3CA5
0x1400e3ca1  lock inc dword ptr [rax+8]
0x1400e3ca5  mov     rdx, [rdi+8]
0x1400e3ca9  mov     rcx, [rdi]
0x1400e3cac  mov     [r8+28h], rcx
0x1400e3cb0  mov     rbx, [r8+30h]
0x1400e3cb4  mov     [r8+30h], rdx
0x1400e3cb8  test    rbx, rbx
0x1400e3cbb  jz      short loc_1400E3CF3
0x1400e3cbd  or      esi, 0FFFFFFFFh
0x1400e3cc0  mov     eax, esi
0x1400e3cc2  lock xadd [rbx+8], eax
0x1400e3cc7  add     eax, esi
0x1400e3cc9  jnz     short loc_1400E3CF3
0x1400e3ccb  mov     rax, [rbx]
0x1400e3cce  mov     rcx, rbx
0x1400e3cd1  mov     rax, [rax]
0x1400e3cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400e3cd9  mov     eax, esi
0x1400e3cdb  lock xadd [rbx+0Ch], eax
0x1400e3ce0  add     eax, esi
0x1400e3ce2  jnz     short loc_1400E3CF3
0x1400e3ce4  mov     rax, [rbx]
0x1400e3ce7  mov     rcx, rbx
0x1400e3cea  mov     rax, [rax+8]
0x1400e3cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400e3cf3  mov     rcx, [rdi]
0x1400e3cf6  xor     r8d, r8d; pftTimeout
0x1400e3cf9  mov     rdx, [rcx]; h
0x1400e3cfc  mov     rcx, [rcx+28h]; pwa
0x1400e3d00  call    cs:__imp_SetThreadpoolWait
0x1400e3d06  nop
0x1400e3d07  mov     cs:dword_14015FED8, 0
0x1400e3d11  mov     rcx, r12; SRWLock
0x1400e3d14  call    cs:__imp_ReleaseSRWLockExclusive
0x1400e3d1a  lea     r11, [rsp+78h+var_28]
0x1400e3d1f  mov     rbx, [r11+30h]
0x1400e3d23  mov     rbp, [r11+40h]
0x1400e3d27  mov     rsp, r11
0x1400e3d2a  pop     r15
0x1400e3d2c  pop     r14
0x1400e3d2e  pop     r12
0x1400e3d30  pop     rdi
0x1400e3d31  pop     rsi
0x1400e3d32  retn
0x1400e3d33  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
0x1400e3d39  mov     rcx, [rsp+78h]; this
0x1400e3d3e  lea     r8, aOnecoreVmCompu_27; "onecore\\vm\\compute\\service\\cexec\\l"...
0x1400e3d45  mov     edx, 11Ch; void *
0x1400e3d4a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
