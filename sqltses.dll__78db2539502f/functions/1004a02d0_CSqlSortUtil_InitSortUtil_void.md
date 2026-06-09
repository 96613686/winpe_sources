# CSqlSortUtil::InitSortUtil(void)

- ea: `0x1004a02d0`
- end: `0x1004a04f9`
- name: `?InitSortUtil@CSqlSortUtil@@SA_NXZ`
- size: `553`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x10049cd10`

## callees

- `0x10049f780`
- `0x1004a01d0`
- `0x1004a02d0`
- `0x1004a25f0`

## import_xrefs

- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x1004a04d6`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x1004a04d6`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x1004a049e`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x1004a049e`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004a048e`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004a04a7`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004a048e`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004a04a7`
- `sqldk!SystemThread_TlsIndex` at `0x1004a0456`
- `sqldk!SystemThread_TlsOffset` at `0x1004a045f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004a047a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004a047a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool CSqlSortUtil::InitSortUtil(void)
{
  int v0; // ebx
  __int64 v1; // rdi
  struct LOC_s *v2; // rdx
  int v3; // ebx
  __int64 v4; // rdi
  struct LOC_s *v5; // rdx
  int v6; // ebx
  __int64 v7; // rdi
  struct LOC_s *v8; // rdx
  int v9; // ebx
  __int64 v10; // rdi
  struct LOC_s *v11; // rdx
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rbx
  PerProcessGlobals *ClientProcessGlobals; // rax
  struct MemoryClerk **DefaultMemoryClerksForNode; // rbx
  struct MemoryClerk *v17; // rax
  char *v18; // r8
  char v20; // [rsp+50h] [rbp+8h] BYREF

  CAutoSortTableMutex::CAutoSortTableMutex((CAutoSortTableMutex *)&v20);
  v0 = 0;
  if ( dword_100947A28 > 0 )
  {
    v1 = 0;
    do
    {
      v2 = (struct LOC_s *)off_100947A40[v1];
      if ( v2 )
      {
        CSqlSortManager::ReleaseLocale((CSqlSortManager *)&x_SqlSortManager_80, v2);
        off_100947A40[v0] = 0;
      }
      ++v0;
      ++v1;
    }
    while ( v0 < dword_100947A28 );
  }
  v3 = 0;
  if ( dword_100C6FB48 > 0 )
  {
    v4 = 0;
    do
    {
      v5 = (struct LOC_s *)off_100C6FB60[v4];
      if ( v5 )
      {
        CSqlSortManager::ReleaseLocale((CSqlSortManager *)&x_SqlSortManager_90, v5);
        off_100C6FB60[v3] = 0;
      }
      ++v3;
      ++v4;
    }
    while ( v3 < dword_100C6FB48 );
  }
  v6 = 0;
  if ( dword_100AD9C18 > 0 )
  {
    v7 = 0;
    do
    {
      v8 = (struct LOC_s *)off_100AD9C30[v7];
      if ( v8 )
      {
        CSqlSortManager::ReleaseLocale((CSqlSortManager *)&x_SqlSortManager_100, v8);
        off_100AD9C30[v6] = 0;
      }
      ++v6;
      ++v7;
    }
    while ( v6 < dword_100AD9C18 );
  }
  v9 = 0;
  if ( dword_100C05D28 > 0 )
  {
    v10 = 0;
    do
    {
      v11 = (struct LOC_s *)off_100C05D40[v10];
      if ( v11 )
      {
        CSqlSortManager::ReleaseLocale((CSqlSortManager *)&x_SqlSortManager_140, v11);
        off_100C05D40[v9] = 0;
      }
      ++v9;
      ++v10;
    }
    while ( v9 < dword_100C05D28 );
  }
  qword_100CB5990 = 0;
  EventAutoInternal<SuspendQueueSLock>::Signal(&g_mutexSortTable, 0);
  v12 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v13 = *(_QWORD *)(v12 + 256);
  if ( !v13 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v13 = *(_QWORD *)(v12 + 256);
  }
  v14 = *(_QWORD *)(v13 + 992);
  ClientProcessGlobals = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals();
  DefaultMemoryClerksForNode = PerProcessGlobals::GetDefaultMemoryClerksForNode(
                                 ClientProcessGlobals,
                                 *(_WORD *)(v14 + 160));
  SOS_OS::GetClientProcessGlobals();
  v17 = DefaultMemoryClerksForNode[16];
  v18 = (char *)v17 + 64;
  if ( !v17 )
    v18 = 0;
  CSqlSortUtil::m_pmoSqlSort = (struct IMemObj *)MemoryObjectFactory::CreateMemObject(53, 4194306, v18);
  return CSqlSortUtil::m_pmoSqlSort != 0;
}

```

## disassembly

```asm
0x1004a02d0  push    rdi
0x1004a02d2  sub     rsp, 40h
0x1004a02d6  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x1004a02df  mov     [rsp+48h+arg_8], rbx
0x1004a02e4  mov     [rsp+48h+arg_10], rsi
0x1004a02e9  lea     rcx, [rsp+48h+arg_0]; this
0x1004a02ee  call    ??0CAutoSortTableMutex@@QEAA@XZ; CAutoSortTableMutex::CAutoSortTableMutex(void)
0x1004a02f3  nop
0x1004a02f4  xor     esi, esi
0x1004a02f6  mov     ebx, esi
0x1004a02f8  cmp     cs:dword_100947A28, ebx
0x1004a02fe  jle     short loc_1004A0348
0x1004a0300  mov     edi, esi
0x1004a0302  nop     dword ptr [rax+00h]
0x1004a0306  nop     word ptr [rax+rax+00000000h]
0x1004a0310  mov     rax, cs:off_100947A40
0x1004a0317  mov     rdx, [rdi+rax]; struct LOC_s *
0x1004a031b  test    rdx, rdx
0x1004a031e  jz      short loc_1004A033A
0x1004a0320  lea     rcx, ?x_SqlSortManager_80@@3VCSqlSortManager_80@@A; this
0x1004a0327  call    ?ReleaseLocale@CSqlSortManager@@IEAAXPEAULOC_s@@@Z; CSqlSortManager::ReleaseLocale(LOC_s *)
0x1004a032c  movsxd  rcx, ebx
0x1004a032f  mov     rax, cs:off_100947A40
0x1004a0336  mov     [rax+rcx*8], rsi
0x1004a033a  inc     ebx
0x1004a033c  add     rdi, 8
0x1004a0340  cmp     ebx, cs:dword_100947A28
0x1004a0346  jl      short loc_1004A0310
0x1004a0348  mov     ebx, esi
0x1004a034a  cmp     cs:dword_100C6FB48, ebx
0x1004a0350  jle     short loc_1004A0398
0x1004a0352  mov     rdi, rsi
0x1004a0355  nop     word ptr [rax+rax+00000000h]
0x1004a0360  mov     rax, cs:off_100C6FB60
0x1004a0367  mov     rdx, [rdi+rax]; struct LOC_s *
0x1004a036b  test    rdx, rdx
0x1004a036e  jz      short loc_1004A038A
0x1004a0370  lea     rcx, ?x_SqlSortManager_90@@3VCSqlSortManager_90@@A; this
0x1004a0377  call    ?ReleaseLocale@CSqlSortManager@@IEAAXPEAULOC_s@@@Z; CSqlSortManager::ReleaseLocale(LOC_s *)
0x1004a037c  movsxd  rcx, ebx
0x1004a037f  mov     rax, cs:off_100C6FB60
0x1004a0386  mov     [rax+rcx*8], rsi
0x1004a038a  inc     ebx
0x1004a038c  add     rdi, 8
0x1004a0390  cmp     ebx, cs:dword_100C6FB48
0x1004a0396  jl      short loc_1004A0360
0x1004a0398  mov     ebx, esi
0x1004a039a  cmp     cs:dword_100AD9C18, ebx
0x1004a03a0  jle     short loc_1004A03E8
0x1004a03a2  mov     rdi, rsi
0x1004a03a5  nop     word ptr [rax+rax+00000000h]
0x1004a03b0  mov     rax, cs:off_100AD9C30
0x1004a03b7  mov     rdx, [rdi+rax]; struct LOC_s *
0x1004a03bb  test    rdx, rdx
0x1004a03be  jz      short loc_1004A03DA
0x1004a03c0  lea     rcx, ?x_SqlSortManager_100@@3VCSqlSortManager_100@@A; this
0x1004a03c7  call    ?ReleaseLocale@CSqlSortManager@@IEAAXPEAULOC_s@@@Z; CSqlSortManager::ReleaseLocale(LOC_s *)
0x1004a03cc  movsxd  rcx, ebx
0x1004a03cf  mov     rax, cs:off_100AD9C30
0x1004a03d6  mov     [rax+rcx*8], rsi
0x1004a03da  inc     ebx
0x1004a03dc  add     rdi, 8
0x1004a03e0  cmp     ebx, cs:dword_100AD9C18
0x1004a03e6  jl      short loc_1004A03B0
0x1004a03e8  mov     ebx, esi
0x1004a03ea  cmp     cs:dword_100C05D28, ebx
0x1004a03f0  jle     short loc_1004A0438
0x1004a03f2  mov     rdi, rsi
0x1004a03f5  nop     word ptr [rax+rax+00000000h]
0x1004a0400  mov     rax, cs:off_100C05D40
0x1004a0407  mov     rdx, [rdi+rax]; struct LOC_s *
0x1004a040b  test    rdx, rdx
0x1004a040e  jz      short loc_1004A042A
0x1004a0410  lea     rcx, ?x_SqlSortManager_140@@3VCSqlSortManager_140@@A; this
0x1004a0417  call    ?ReleaseLocale@CSqlSortManager@@IEAAXPEAULOC_s@@@Z; CSqlSortManager::ReleaseLocale(LOC_s *)
0x1004a041c  movsxd  rcx, ebx
0x1004a041f  mov     rax, cs:off_100C05D40
0x1004a0426  mov     [rax+rcx*8], rsi
0x1004a042a  inc     ebx
0x1004a042c  add     rdi, 8
0x1004a0430  cmp     ebx, cs:dword_100C05D28
0x1004a0436  jl      short loc_1004A0400
0x1004a0438  mov     cs:qword_100CB5990, rsi
0x1004a043f  xor     edx, edx
0x1004a0441  lea     rcx, ?g_mutexSortTable@@3VSOS_Mutex@@A; SOS_Mutex g_mutexSortTable
0x1004a0448  call    ?Signal@?$EventAutoInternal@USuspendQueueSLock@@@@UEAAXW4SOS_EVENT_SIGNAL_OPTIONS@@@Z; EventAutoInternal<SuspendQueueSLock>::Signal(SOS_EVENT_SIGNAL_OPTIONS)
0x1004a044d  mov     rdx, gs:58h
0x1004a0456  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004a045d  mov     ecx, [rax]
0x1004a045f  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004a0466  mov     ebx, [rax]
0x1004a0468  add     rbx, [rdx+rcx*8]
0x1004a046c  mov     rax, [rbx+100h]
0x1004a0473  test    rax, rax
0x1004a0476  jnz     short loc_1004A0487
0x1004a0478  xor     ecx, ecx
0x1004a047a  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004a0480  mov     rax, [rbx+100h]
0x1004a0487  mov     rbx, [rax+3E0h]
0x1004a048e  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x1004a0494  mov     rcx, rax
0x1004a0497  movzx   edx, word ptr [rbx+0A0h]
0x1004a049e  call    cs:__imp_?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z; PerProcessGlobals::GetDefaultMemoryClerksForNode(ushort)
0x1004a04a4  mov     rbx, rax
0x1004a04a7  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x1004a04ad  mov     rax, [rbx+80h]
0x1004a04b4  mov     ecx, 80h
0x1004a04b9  lea     r9d, [rcx-7Ch]
0x1004a04bd  lea     r8, [rax+40h]
0x1004a04c1  test    rax, rax
0x1004a04c4  cmovz   r8, rsi
0x1004a04c8  mov     [rsp+48h+var_28], cx
0x1004a04cd  mov     edx, 400002h
0x1004a04d2  lea     ecx, [r9+31h]
0x1004a04d6  call    cs:__imp_?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z; MemoryObjectFactory::CreateMemObject(SOSHOST_MEMOBJ_ID,ulong,PageAllocator *,short,short)
0x1004a04dc  mov     cs:?m_pmoSqlSort@CSqlSortUtil@@0PEAVIMemObj@@EA, rax; IMemObj * CSqlSortUtil::m_pmoSqlSort
0x1004a04e3  test    rax, rax
0x1004a04e6  setnz   al
0x1004a04e9  mov     rbx, [rsp+48h+arg_8]
0x1004a04ee  mov     rsi, [rsp+48h+arg_10]
0x1004a04f3  add     rsp, 40h
0x1004a04f7  pop     rdi
0x1004a04f8  retn
```
