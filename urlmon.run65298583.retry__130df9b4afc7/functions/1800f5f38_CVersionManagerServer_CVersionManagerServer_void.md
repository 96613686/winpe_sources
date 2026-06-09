# CVersionManagerServer::~CVersionManagerServer(void)

- ea: `0x1800f5f38`
- end: `0x1800f617f`
- name: `??1CVersionManagerServer@@UEAA@XZ`
- size: `583`
- prototype: `void __fastcall(CVersionManagerServer *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x1800f6230`

## callees

- `0x180030880`
- `0x18006d328`
- `0x180080f54`
- `0x1800f5f38`
- `0x1800f61e0`
- `0x1800f6208`
- `0x1800f9a1c`
- `0x1800f9bf8`
- `0x18010c93c`
- `0x18010e3c0`
- `0x18010e418`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f6118`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f6125`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f6132`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f613f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f6118`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f6125`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f6132`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f613f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800f5fd4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800f5fd4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800f5fb6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800f5fb6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f60d9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f60d9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800f60cc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800f60cc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800f5fa1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800f5fc7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800f5fa1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800f5fc7`

## pseudocode

```c
void __fastcall CVersionManagerServer::~CVersionManagerServer(CVersionManagerServer *this)
{
  MutexUtils::CMutex *v1; // rsi
  MutexUtils::CMutex *v3; // rbp
  struct _TP_TIMER *v4; // rcx
  CSharedMem *v5; // rdi
  unsigned int v6; // edx
  CFileInfoCache *v7; // rcx
  CBlockListManager *v8; // rcx
  CByteHashTable *v9; // rcx
  void *v10; // rcx
  CByteHashTable *v11; // rcx
  int v12; // edx
  void *v13; // rcx
  struct _TP_WORK *v14; // rcx
  struct CVersionManagerServer::TELEMETRY_PARAMS *v15; // rax
  _QWORD v16[7]; // [rsp+20h] [rbp-38h] BYREF

  v1 = (CVersionManagerServer *)((char *)this + 2056);
  *(_QWORD *)this = &CVersionManagerServer::`vftable'{for `TUnknownMTBase<char>'};
  v3 = (CVersionManagerServer *)((char *)this + 2032);
  *((_QWORD *)this + 2) = &CVersionManagerServer::`vftable'{for `IVersionManager'};
  if ( *((_BYTE *)this + 24) )
  {
    MutexUtils::CMutex::Abort((CVersionManagerServer *)((char *)this + 2032));
    MutexUtils::CMutex::Abort(v1);
    v4 = (struct _TP_TIMER *)*((_QWORD *)this + 199);
    if ( v4 )
    {
      *((_BYTE *)this + 2000) = 1;
      *((_BYTE *)this + 28) = 1;
      WaitForThreadpoolTimerCallbacks(v4, 1);
      SetThreadpoolTimer(*((PTP_TIMER *)this + 199), 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 199), 1);
      CloseThreadpoolTimer(*((PTP_TIMER *)this + 199));
      *((_QWORD *)this + 199) = 0;
    }
    *((_BYTE *)this + 24) = 0;
    if ( *((_BYTE *)this + 1600) )
      *((_BYTE *)this + 1600) = 0;
    v5 = (CVersionManagerServer *)((char *)this + 2008);
    CSharedMem::Release((CVersionManagerServer *)((char *)this + 2008));
    v7 = (CFileInfoCache *)*((_QWORD *)this + 211);
    if ( v7 )
      CFileInfoCache::`scalar deleting destructor'(v7, v6);
    v8 = (CBlockListManager *)*((_QWORD *)this + 248);
    *((_QWORD *)this + 211) = 0;
    if ( v8 )
      CBlockListManager::`scalar deleting destructor'(v8, v6);
    v9 = (CByteHashTable *)*((_QWORD *)this + 246);
    *((_QWORD *)this + 248) = 0;
    if ( v9 )
    {
      CByteHashTable::_RemoveCallback(v9, v6, 0, 0);
      v10 = (void *)*((_QWORD *)this + 246);
      if ( v10 )
        operator delete(v10);
      *((_QWORD *)this + 246) = 0;
    }
    v11 = (CByteHashTable *)*((_QWORD *)this + 247);
    if ( v11 )
    {
      v16[1] = 0;
      v16[0] = CBlockListManager::s_GroupEntryDestroyCallback;
      CByteHashTable::_RemoveCallback(v11, v6, CHashTable<BLOCKLIST_ENTRY,unsigned short>::s_DestroyCallback, v16);
      CByteHashTable::_RemoveCallback(*((CByteHashTable **)this + 247), v12, 0, 0);
      v13 = (void *)*((_QWORD *)this + 247);
      if ( v13 )
        operator delete(v13);
      *((_QWORD *)this + 247) = 0;
    }
    v14 = (struct _TP_WORK *)*((_QWORD *)this + 212);
    if ( v14 )
    {
      WaitForThreadpoolWorkCallbacks(v14, 1);
      CloseThreadpoolWork(*((PTP_WORK *)this + 212));
      *((_QWORD *)this + 212) = 0;
    }
    if ( *((_BYTE *)this + 1704) )
      *((_BYTE *)this + 1704) = 0;
    while ( *((int *)this + 460) > 0 )
    {
      v15 = CVersionManagerServer::_TelParamsDequeue(this);
      CVersionManagerServer::s_TelParamsFree(v15);
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1888));
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1848));
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1928));
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1784));
  }
  else
  {
    v5 = (CVersionManagerServer *)((char *)this + 2008);
  }
  MutexUtils::CMutex::~CMutex(v1);
  MutexUtils::CMutex::~CMutex(v3);
  CSharedMem::Release(v5);
  *(_QWORD *)this = &CIEEnterpriseModeFilter::`vftable'{for `TUnknownMTBase<char>'};
  DllRelease();
}

```

## disassembly

```asm
0x1800f5f38  push    rbx
0x1800f5f3a  push    rbp
0x1800f5f3b  push    rsi
0x1800f5f3c  push    rdi
0x1800f5f3d  push    r14
0x1800f5f3f  sub     rsp, 30h
0x1800f5f43  lea     rax, ??_7CVersionManagerServer@@6B?$TUnknownMTBase@D@@@; const CVersionManagerServer::`vftable'{for `TUnknownMTBase<char>'}
0x1800f5f4a  xor     r14d, r14d
0x1800f5f4d  lea     rsi, [rcx+808h]
0x1800f5f54  mov     [rcx], rax
0x1800f5f57  lea     rax, ??_7CVersionManagerServer@@6BIVersionManager@@@; const CVersionManagerServer::`vftable'{for `IVersionManager'}
0x1800f5f5e  mov     rbx, rcx
0x1800f5f61  lea     rbp, [rcx+7F0h]
0x1800f5f68  mov     [rcx+10h], rax
0x1800f5f6c  cmp     [rcx+18h], r14b
0x1800f5f70  jz      loc_1800F6147
0x1800f5f76  mov     rcx, rbp; this
0x1800f5f79  call    ?Abort@CMutex@MutexUtils@@QEAAXXZ; MutexUtils::CMutex::Abort(void)
0x1800f5f7e  mov     rcx, rsi; this
0x1800f5f81  call    ?Abort@CMutex@MutexUtils@@QEAAXXZ; MutexUtils::CMutex::Abort(void)
0x1800f5f86  mov     rcx, [rbx+638h]; pti
0x1800f5f8d  test    rcx, rcx
0x1800f5f90  jz      short loc_1800F5FE1
0x1800f5f92  lea     edx, [r14+1]; fCancelPendingCallbacks
0x1800f5f96  mov     byte ptr [rbx+7D0h], 1
0x1800f5f9d  mov     byte ptr [rbx+1Ch], 1
0x1800f5fa1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800f5fa7  mov     rcx, [rbx+638h]; pti
0x1800f5fae  xor     r9d, r9d; msWindowLength
0x1800f5fb1  xor     r8d, r8d; msPeriod
0x1800f5fb4  xor     edx, edx; pftDueTime
0x1800f5fb6  call    cs:__imp_SetThreadpoolTimer
0x1800f5fbc  mov     rcx, [rbx+638h]; pti
0x1800f5fc3  lea     edx, [r14+1]; fCancelPendingCallbacks
0x1800f5fc7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800f5fcd  mov     rcx, [rbx+638h]; pti
0x1800f5fd4  call    cs:__imp_CloseThreadpoolTimer
0x1800f5fda  mov     [rbx+638h], r14
0x1800f5fe1  mov     [rbx+18h], r14b
0x1800f5fe5  cmp     [rbx+640h], r14b
0x1800f5fec  jz      short loc_1800F5FF5
0x1800f5fee  mov     [rbx+640h], r14b
0x1800f5ff5  lea     rdi, [rbx+7D8h]
0x1800f5ffc  mov     rcx, rdi; this
0x1800f5fff  call    ?Release@CSharedMem@@QEAAXXZ; CSharedMem::Release(void)
0x1800f6004  mov     rcx, [rbx+698h]; this
0x1800f600b  test    rcx, rcx
0x1800f600e  jz      short loc_1800F6015
0x1800f6010  call    ??_GCFileInfoCache@@QEAAPEAXI@Z; CFileInfoCache::`scalar deleting destructor'(uint)
0x1800f6015  mov     rcx, [rbx+7C0h]; this
0x1800f601c  mov     [rbx+698h], r14
0x1800f6023  test    rcx, rcx
0x1800f6026  jz      short loc_1800F602D
0x1800f6028  call    ??_GCBlockListManager@@QEAAPEAXI@Z; CBlockListManager::`scalar deleting destructor'(uint)
0x1800f602d  mov     rcx, [rbx+7B0h]; this
0x1800f6034  mov     [rbx+7C0h], r14
0x1800f603b  test    rcx, rcx
0x1800f603e  jz      short loc_1800F6063
0x1800f6040  xor     r9d, r9d; void *
0x1800f6043  xor     r8d, r8d; void (*)(unsigned __int8 *, unsigned int, void *)
0x1800f6046  call    ?_RemoveCallback@CByteHashTable@@AEAAXHP6AXPEAEIPEAX@Z1@Z; CByteHashTable::_RemoveCallback(int,void (*)(uchar *,uint,void *),void *)
0x1800f604b  mov     rcx, [rbx+7B0h]; void *
0x1800f6052  test    rcx, rcx
0x1800f6055  jz      short loc_1800F605C
0x1800f6057  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800f605c  mov     [rbx+7B0h], r14
0x1800f6063  mov     rcx, [rbx+7B8h]; this
0x1800f606a  test    rcx, rcx
0x1800f606d  jz      short loc_1800F60BB
0x1800f606f  lea     rax, ?s_GroupEntryDestroyCallback@CBlockListManager@@CAXPEAUGROUP_ENTRY@@@Z; CBlockListManager::s_GroupEntryDestroyCallback(GROUP_ENTRY *)
0x1800f6076  mov     [rsp+58h+var_30], r14
0x1800f607b  lea     r9, [rsp+58h+var_38]; void *
0x1800f6080  mov     [rsp+58h+var_38], rax
0x1800f6085  lea     r8, ?s_DestroyCallback@?$CHashTable@UBLOCKLIST_ENTRY@@G@@CAXPEAEIPEAX@Z; void (*)(unsigned __int8 *, unsigned int, void *)
0x1800f608c  call    ?_RemoveCallback@CByteHashTable@@AEAAXHP6AXPEAEIPEAX@Z1@Z; CByteHashTable::_RemoveCallback(int,void (*)(uchar *,uint,void *),void *)
0x1800f6091  mov     rcx, [rbx+7B8h]; this
0x1800f6098  xor     r9d, r9d; void *
0x1800f609b  xor     r8d, r8d; void (*)(unsigned __int8 *, unsigned int, void *)
0x1800f609e  call    ?_RemoveCallback@CByteHashTable@@AEAAXHP6AXPEAEIPEAX@Z1@Z; CByteHashTable::_RemoveCallback(int,void (*)(uchar *,uint,void *),void *)
0x1800f60a3  mov     rcx, [rbx+7B8h]; void *
0x1800f60aa  test    rcx, rcx
0x1800f60ad  jz      short loc_1800F60B4
0x1800f60af  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800f60b4  mov     [rbx+7B8h], r14
0x1800f60bb  mov     rcx, [rbx+6A0h]; pwk
0x1800f60c2  test    rcx, rcx
0x1800f60c5  jz      short loc_1800F60E6
0x1800f60c7  mov     edx, 1; fCancelPendingCallbacks
0x1800f60cc  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800f60d2  mov     rcx, [rbx+6A0h]; pwk
0x1800f60d9  call    cs:__imp_CloseThreadpoolWork
0x1800f60df  mov     [rbx+6A0h], r14
0x1800f60e6  cmp     [rbx+6A8h], r14b
0x1800f60ed  jz      short loc_1800F6108
0x1800f60ef  mov     [rbx+6A8h], r14b
0x1800f60f6  jmp     short loc_1800F6108
0x1800f60f8  mov     rcx, rbx; this
0x1800f60fb  call    ?_TelParamsDequeue@CVersionManagerServer@@AEAAPEAUTELEMETRY_PARAMS@1@XZ; CVersionManagerServer::_TelParamsDequeue(void)
0x1800f6100  mov     rcx, rax; struct CVersionManagerServer::TELEMETRY_PARAMS *
0x1800f6103  call    ?s_TelParamsFree@CVersionManagerServer@@CAXPEAUTELEMETRY_PARAMS@1@@Z; CVersionManagerServer::s_TelParamsFree(CVersionManagerServer::TELEMETRY_PARAMS *)
0x1800f6108  cmp     [rbx+730h], r14d
0x1800f610f  jg      short loc_1800F60F8
0x1800f6111  lea     rcx, [rbx+760h]; lpCriticalSection
0x1800f6118  call    cs:__imp_DeleteCriticalSection
0x1800f611e  lea     rcx, [rbx+738h]; lpCriticalSection
0x1800f6125  call    cs:__imp_DeleteCriticalSection
0x1800f612b  lea     rcx, [rbx+788h]; lpCriticalSection
0x1800f6132  call    cs:__imp_DeleteCriticalSection
0x1800f6138  lea     rcx, [rbx+6F8h]; lpCriticalSection
0x1800f613f  call    cs:__imp_DeleteCriticalSection
0x1800f6145  jmp     short loc_1800F614E
0x1800f6147  lea     rdi, [rcx+7D8h]
0x1800f614e  mov     rcx, rsi; this
0x1800f6151  call    ??1CMutex@MutexUtils@@QEAA@XZ; MutexUtils::CMutex::~CMutex(void)
0x1800f6156  mov     rcx, rbp; this
0x1800f6159  call    ??1CMutex@MutexUtils@@QEAA@XZ; MutexUtils::CMutex::~CMutex(void)
0x1800f615e  mov     rcx, rdi; this
0x1800f6161  call    ?Release@CSharedMem@@QEAAXXZ; CSharedMem::Release(void)
0x1800f6166  lea     rax, ??_7CIEEnterpriseModeFilter@@6B?$TUnknownMTBase@D@@@; const CIEEnterpriseModeFilter::`vftable'{for `TUnknownMTBase<char>'}
0x1800f616d  mov     [rbx], rax
0x1800f6170  add     rsp, 30h
0x1800f6174  pop     r14
0x1800f6176  pop     rdi
0x1800f6177  pop     rsi
0x1800f6178  pop     rbp
0x1800f6179  pop     rbx
0x1800f617a  jmp     DllRelease
```
