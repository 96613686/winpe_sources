# CVersionManagerServer::~CVersionManagerServer(void)

- ea: `0x180100664`
- end: `0x1801008e7`
- name: `??1CVersionManagerServer@@UEAA@XZ`
- size: `643`
- prototype: `void __fastcall(CVersionManagerServer *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x1801009b0`

## callees

- `0x18002fee0`
- `0x180031460`
- `0x180086954`
- `0x180100664`
- `0x180100954`
- `0x18010097c`
- `0x1801044a8`
- `0x1801046ac`
- `0x1801183a4`
- `0x18011a058`
- `0x18011a0bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180100868`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18010087b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18010088e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801008a1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180100868`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18010087b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18010088e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801008a1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180100712`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180100712`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1801006e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1801006e8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180100823`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180100823`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180100810`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180100810`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1801006cd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1801006ff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1801006cd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1801006ff`

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
0x180100664  push    rbx
0x180100666  push    rbp
0x180100667  push    rsi
0x180100668  push    rdi
0x180100669  push    r14
0x18010066b  sub     rsp, 30h
0x18010066f  lea     rax, ??_7CVersionManagerServer@@6B?$TUnknownMTBase@D@@@; const CVersionManagerServer::`vftable'{for `TUnknownMTBase<char>'}
0x180100676  xor     r14d, r14d
0x180100679  lea     rsi, [rcx+808h]
0x180100680  mov     [rcx], rax
0x180100683  lea     rax, ??_7CVersionManagerServer@@6BIVersionManager@@@; const CVersionManagerServer::`vftable'{for `IVersionManager'}
0x18010068a  mov     rbx, rcx
0x18010068d  lea     rbp, [rcx+7F0h]
0x180100694  mov     [rcx+10h], rax
0x180100698  cmp     [rcx+18h], r14b
0x18010069c  jz      loc_1801008AF
0x1801006a2  mov     rcx, rbp; this
0x1801006a5  call    ?Abort@CMutex@MutexUtils@@QEAAXXZ; MutexUtils::CMutex::Abort(void)
0x1801006aa  mov     rcx, rsi; this
0x1801006ad  call    ?Abort@CMutex@MutexUtils@@QEAAXXZ; MutexUtils::CMutex::Abort(void)
0x1801006b2  mov     rcx, [rbx+638h]; pti
0x1801006b9  test    rcx, rcx
0x1801006bc  jz      short loc_180100725
0x1801006be  lea     edx, [r14+1]; fCancelPendingCallbacks
0x1801006c2  mov     byte ptr [rbx+7D0h], 1
0x1801006c9  mov     byte ptr [rbx+1Ch], 1
0x1801006cd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1801006d4  nop     dword ptr [rax+rax+00h]
0x1801006d9  mov     rcx, [rbx+638h]; pti
0x1801006e0  xor     r9d, r9d; msWindowLength
0x1801006e3  xor     r8d, r8d; msPeriod
0x1801006e6  xor     edx, edx; pftDueTime
0x1801006e8  call    cs:__imp_SetThreadpoolTimer
0x1801006ef  nop     dword ptr [rax+rax+00h]
0x1801006f4  mov     rcx, [rbx+638h]; pti
0x1801006fb  lea     edx, [r14+1]; fCancelPendingCallbacks
0x1801006ff  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180100706  nop     dword ptr [rax+rax+00h]
0x18010070b  mov     rcx, [rbx+638h]; pti
0x180100712  call    cs:__imp_CloseThreadpoolTimer
0x180100719  nop     dword ptr [rax+rax+00h]
0x18010071e  mov     [rbx+638h], r14
0x180100725  mov     [rbx+18h], r14b
0x180100729  cmp     [rbx+640h], r14b
0x180100730  jz      short loc_180100739
0x180100732  mov     [rbx+640h], r14b
0x180100739  lea     rdi, [rbx+7D8h]
0x180100740  mov     rcx, rdi; this
0x180100743  call    ?Release@CSharedMem@@QEAAXXZ; CSharedMem::Release(void)
0x180100748  mov     rcx, [rbx+698h]; this
0x18010074f  test    rcx, rcx
0x180100752  jz      short loc_180100759
0x180100754  call    ??_GCFileInfoCache@@QEAAPEAXI@Z; CFileInfoCache::`scalar deleting destructor'(uint)
0x180100759  mov     rcx, [rbx+7C0h]; this
0x180100760  mov     [rbx+698h], r14
0x180100767  test    rcx, rcx
0x18010076a  jz      short loc_180100771
0x18010076c  call    ??_GCBlockListManager@@QEAAPEAXI@Z; CBlockListManager::`scalar deleting destructor'(uint)
0x180100771  mov     rcx, [rbx+7B0h]; this
0x180100778  mov     [rbx+7C0h], r14
0x18010077f  test    rcx, rcx
0x180100782  jz      short loc_1801007A7
0x180100784  xor     r9d, r9d; void *
0x180100787  xor     r8d, r8d; void (*)(unsigned __int8 *, unsigned int, void *)
0x18010078a  call    ?_RemoveCallback@CByteHashTable@@AEAAXHP6AXPEAEIPEAX@Z1@Z; CByteHashTable::_RemoveCallback(int,void (*)(uchar *,uint,void *),void *)
0x18010078f  mov     rcx, [rbx+7B0h]; void *
0x180100796  test    rcx, rcx
0x180100799  jz      short loc_1801007A0
0x18010079b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801007a0  mov     [rbx+7B0h], r14
0x1801007a7  mov     rcx, [rbx+7B8h]; this
0x1801007ae  test    rcx, rcx
0x1801007b1  jz      short loc_1801007FF
0x1801007b3  lea     rax, ?s_GroupEntryDestroyCallback@CBlockListManager@@CAXPEAUGROUP_ENTRY@@@Z; CBlockListManager::s_GroupEntryDestroyCallback(GROUP_ENTRY *)
0x1801007ba  mov     [rsp+58h+var_30], r14
0x1801007bf  lea     r9, [rsp+58h+var_38]; void *
0x1801007c4  mov     [rsp+58h+var_38], rax
0x1801007c9  lea     r8, ?s_DestroyCallback@?$CHashTable@UBLOCKLIST_ENTRY@@G@@CAXPEAEIPEAX@Z; void (*)(unsigned __int8 *, unsigned int, void *)
0x1801007d0  call    ?_RemoveCallback@CByteHashTable@@AEAAXHP6AXPEAEIPEAX@Z1@Z; CByteHashTable::_RemoveCallback(int,void (*)(uchar *,uint,void *),void *)
0x1801007d5  mov     rcx, [rbx+7B8h]; this
0x1801007dc  xor     r9d, r9d; void *
0x1801007df  xor     r8d, r8d; void (*)(unsigned __int8 *, unsigned int, void *)
0x1801007e2  call    ?_RemoveCallback@CByteHashTable@@AEAAXHP6AXPEAEIPEAX@Z1@Z; CByteHashTable::_RemoveCallback(int,void (*)(uchar *,uint,void *),void *)
0x1801007e7  mov     rcx, [rbx+7B8h]; void *
0x1801007ee  test    rcx, rcx
0x1801007f1  jz      short loc_1801007F8
0x1801007f3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801007f8  mov     [rbx+7B8h], r14
0x1801007ff  mov     rcx, [rbx+6A0h]; pwk
0x180100806  test    rcx, rcx
0x180100809  jz      short loc_180100836
0x18010080b  mov     edx, 1; fCancelPendingCallbacks
0x180100810  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180100817  nop     dword ptr [rax+rax+00h]
0x18010081c  mov     rcx, [rbx+6A0h]; pwk
0x180100823  call    cs:__imp_CloseThreadpoolWork
0x18010082a  nop     dword ptr [rax+rax+00h]
0x18010082f  mov     [rbx+6A0h], r14
0x180100836  cmp     [rbx+6A8h], r14b
0x18010083d  jz      short loc_180100858
0x18010083f  mov     [rbx+6A8h], r14b
0x180100846  jmp     short loc_180100858
0x180100848  mov     rcx, rbx; this
0x18010084b  call    ?_TelParamsDequeue@CVersionManagerServer@@AEAAPEAUTELEMETRY_PARAMS@1@XZ; CVersionManagerServer::_TelParamsDequeue(void)
0x180100850  mov     rcx, rax; struct CVersionManagerServer::TELEMETRY_PARAMS *
0x180100853  call    ?s_TelParamsFree@CVersionManagerServer@@CAXPEAUTELEMETRY_PARAMS@1@@Z; CVersionManagerServer::s_TelParamsFree(CVersionManagerServer::TELEMETRY_PARAMS *)
0x180100858  cmp     [rbx+730h], r14d
0x18010085f  jg      short loc_180100848
0x180100861  lea     rcx, [rbx+760h]; lpCriticalSection
0x180100868  call    cs:__imp_DeleteCriticalSection
0x18010086f  nop     dword ptr [rax+rax+00h]
0x180100874  lea     rcx, [rbx+738h]; lpCriticalSection
0x18010087b  call    cs:__imp_DeleteCriticalSection
0x180100882  nop     dword ptr [rax+rax+00h]
0x180100887  lea     rcx, [rbx+788h]; lpCriticalSection
0x18010088e  call    cs:__imp_DeleteCriticalSection
0x180100895  nop     dword ptr [rax+rax+00h]
0x18010089a  lea     rcx, [rbx+6F8h]; lpCriticalSection
0x1801008a1  call    cs:__imp_DeleteCriticalSection
0x1801008a8  nop     dword ptr [rax+rax+00h]
0x1801008ad  jmp     short loc_1801008B6
0x1801008af  lea     rdi, [rcx+7D8h]
0x1801008b6  mov     rcx, rsi; this
0x1801008b9  call    ??1CMutex@MutexUtils@@QEAA@XZ; MutexUtils::CMutex::~CMutex(void)
0x1801008be  mov     rcx, rbp; this
0x1801008c1  call    ??1CMutex@MutexUtils@@QEAA@XZ; MutexUtils::CMutex::~CMutex(void)
0x1801008c6  mov     rcx, rdi; this
0x1801008c9  call    ?Release@CSharedMem@@QEAAXXZ; CSharedMem::Release(void)
0x1801008ce  lea     rax, ??_7CIEEnterpriseModeFilter@@6B?$TUnknownMTBase@D@@@; const CIEEnterpriseModeFilter::`vftable'{for `TUnknownMTBase<char>'}
0x1801008d5  mov     [rbx], rax
0x1801008d8  add     rsp, 30h
0x1801008dc  pop     r14
0x1801008de  pop     rdi
0x1801008df  pop     rsi
0x1801008e0  pop     rbp
0x1801008e1  pop     rbx
0x1801008e2  jmp     DllRelease
```
