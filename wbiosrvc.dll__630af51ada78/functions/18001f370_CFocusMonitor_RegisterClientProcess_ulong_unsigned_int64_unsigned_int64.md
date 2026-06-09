# CFocusMonitor::RegisterClientProcess(ulong,unsigned __int64 *,unsigned __int64 *)

- ea: `0x18001f370`
- end: `0x18001f7e6`
- name: `?RegisterClientProcess@CFocusMonitor@@SA_NKPEA_K0@Z`
- size: `1142`
- prototype: `char __fastcall(DWORD dwProcessId, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001dbe0`
- `0x18001e740`
- `0x18001ed20`

## callees

- `0x18000b760`
- `0x180011a34`
- `0x18001f370`
- `0x180028af0`
- `0x18002a67c`
- `0x18002b7c0`
- `0x18002d3b4`
- `0x1800332c0`
- `0x180035280`
- `0x18003b93c`
- `0x1800605a4`
- `0x18006963c`
- `0x180069cd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f459`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f459`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f5fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f67a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f5fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f67a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f706`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f559`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f559`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f628`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f6a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f73c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f79d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f7a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f628`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f6a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f73c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f79d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f7a7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001f665`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001f6f1`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001f665`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001f6f1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001f56c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001f5d1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001f56c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001f5d1`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001f4a7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001f4a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall CFocusMonitor::RegisterClientProcess(DWORD dwProcessId, unsigned __int64 *a2, unsigned __int64 *a3)
{
  unsigned __int64 *v4; // r12
  struct CFocusMonitor *v6; // rax
  __int64 **v7; // rax
  __int64 *i; // rdx
  _QWORD *v9; // rax
  _OWORD *v10; // r14
  _OWORD *v11; // rdi
  HANDLE EventW; // rax
  char *v13; // r12
  __int64 v14; // rbx
  _DWORD *v15; // rax
  _QWORD *v16; // rcx
  void *v17; // r14
  DWORD CurrentProcessId; // eax
  __int64 v19; // rbx
  int v20; // r9d
  __int64 v22; // rdi
  int v23; // r9d
  int v24; // r9d
  struct CFocusMonitor *v25; // rax
  int v26; // r9d
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  HANDLE hObject; // [rsp+48h] [rbp-19h] BYREF
  HANDLE TargetHandle; // [rsp+50h] [rbp-11h] BYREF
  char *v32; // [rsp+58h] [rbp-9h] BYREF
  std::_Ref_count_base *v33; // [rsp+60h] [rbp-1h]
  __int128 v34; // [rsp+68h] [rbp+7h] BYREF
  DWORD pExceptionObject; // [rsp+78h] [rbp+17h] BYREF
  _QWORD v36[3]; // [rsp+80h] [rbp+1Fh] BYREF
  unsigned __int64 v38; // [rsp+E0h] [rbp+7Fh] BYREF

  v4 = a2;
  v6 = CFocusMonitor::Instance();
  winbio::lockable_object::lock_exclusive(v6, &v38);
  v34 = 0;
  v7 = (__int64 **)*((_QWORD *)CFocusMonitor::Instance() + 3);
  for ( i = *v7; i != (__int64 *)v7; i = (__int64 *)*i )
  {
    if ( *((_DWORD *)i + 4) == dwProcessId )
    {
      v9 = (_QWORD *)std::shared_ptr<CBiometricServiceProvider>::shared_ptr<CBiometricServiceProvider>(&v32, i + 3);
      v10 = (_OWORD *)*v9;
      *v9 = 0;
      *(_QWORD *)&v34 = v10;
      v11 = (_OWORD *)v9[1];
      v9[1] = 0;
      *((_QWORD *)&v34 + 1) = v11;
      if ( v33 )
        std::_Ref_count_base::_Decref(v33);
      ++*(_DWORD *)v10;
      goto LABEL_12;
    }
  }
  v11 = operator new(0x20u);
  hObject = v11;
  *v11 = 0;
  *((_DWORD *)v11 + 2) = 1;
  *((_DWORD *)v11 + 3) = 1;
  *(_QWORD *)v11 = &std::_Ref_count_obj2<CFocusClient>::`vftable';
  v10 = v11 + 1;
  *((_DWORD *)v11 + 4) = 1;
  *((_QWORD *)v11 + 3) = -1;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)&pExceptionObject);
    throw (std::bad_alloc *)&pExceptionObject;
  }
  *((_QWORD *)v11 + 3) = EventW;
  *(_QWORD *)&v34 = v11 + 1;
  *((_QWORD *)&v34 + 1) = v11;
  v13 = (char *)CFocusMonitor::Instance() + 24;
  pExceptionObject = dwProcessId;
  std::shared_ptr<CBiometricServiceProvider>::shared_ptr<CBiometricServiceProvider>(v36, &v34);
  if ( *((_QWORD *)v13 + 1) == 0x666666666666666LL )
    std::_Xlength_error("list too long");
  v14 = **(_QWORD **)v13;
  v32 = v13;
  v33 = 0;
  v15 = operator new(0x28u);
  v15[4] = pExceptionObject;
  *((_QWORD *)v15 + 3) = v36[0];
  *((_QWORD *)v15 + 4) = v36[1];
  ++*((_QWORD *)v13 + 1);
  v16 = *(_QWORD **)(v14 + 8);
  *(_QWORD *)v15 = v14;
  *((_QWORD *)v15 + 1) = v16;
  v33 = 0;
  *(_QWORD *)(v14 + 8) = v15;
  *v16 = v15;
  std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned long,std::shared_ptr<CFocusClient>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned long,std::shared_ptr<CFocusClient>>,void *>>>(&v32);
  v4 = a2;
LABEL_12:
  if ( *((_BYTE *)CFocusMonitor::Instance() + 16) )
  {
    v17 = (void *)*((_QWORD *)v10 + 1);
    if ( v11 )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v11);
    Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v38);
    CurrentProcessId = GetCurrentProcessId();
    v19 = (__int64)OpenProcess(0x40u, 1, CurrentProcessId);
    if ( !v19 )
      v19 = -1;
    v32 = (char *)v19;
    if ( v19 == -1 )
    {
      if ( (unsigned int)dword_18010F170 > 2 )
      {
        LODWORD(v38) = GetLastError();
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_18010F170,
          (unsigned int)word_1800EFA42,
          0,
          v20,
          (__int64)&v38);
      }
    }
    else
    {
      v22 = (__int64)OpenProcess(0x40u, 1, dwProcessId);
      if ( !v22 )
        v22 = -1;
      *(_QWORD *)&v34 = v22;
      if ( v22 == -1 )
      {
        if ( (unsigned int)dword_18010F170 > 2 )
        {
          LODWORD(v38) = GetLastError();
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_18010F170,
            (unsigned int)byte_1800EFA7B,
            0,
            v23,
            (__int64)&v38);
        }
      }
      else
      {
        TargetHandle = 0;
        hObject = (HANDLE)-1LL;
        v38 = -1;
        if ( DuplicateHandle((HANDLE)v19, v17, (HANDLE)v22, &TargetHandle, 0, 1, 2u) )
        {
          winbio::scoped_handle::assign((winbio::scoped_handle *)&hObject, TargetHandle);
          TargetHandle = (HANDLE)-1LL;
          v25 = CFocusMonitor::Instance();
          if ( DuplicateHandle((HANDLE)v19, *((HANDLE *)v25 + 5), (HANDLE)v22, &TargetHandle, 0, 1, 2u) )
          {
            winbio::scoped_handle::assign((winbio::scoped_handle *)&v38, TargetHandle);
            TargetHandle = (HANDLE)-1LL;
            *v4 = (unsigned __int64)hObject;
            *a3 = v38;
            if ( (unsigned int)dword_18010F170 > 4 )
            {
              LODWORD(hObject) = dwProcessId;
              LOBYTE(v38) = 1;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
                v27,
                (unsigned int)&word_1800EF936,
                v28,
                v29,
                (__int64)&v38,
                (__int64)&hObject);
            }
            CloseHandle((HANDLE)v22);
            CloseHandle((HANDLE)v19);
            return 1;
          }
          if ( (unsigned int)dword_18010F170 > 2 )
          {
            LODWORD(v38) = GetLastError();
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (unsigned int)&dword_18010F170,
              (unsigned int)byte_1800EFA03,
              0,
              v26,
              (__int64)&v38);
          }
          if ( hObject != (HANDLE)-1LL )
            CloseHandle(hObject);
        }
        else if ( (unsigned int)dword_18010F170 > 2 )
        {
          LODWORD(v38) = GetLastError();
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_18010F170,
            (unsigned int)&byte_1800EF9C7,
            0,
            v24,
            (__int64)&v38);
        }
        CloseHandle((HANDLE)v22);
      }
      CloseHandle((HANDLE)v19);
    }
    return 0;
  }
  *v4 = 0;
  *a3 = 0;
  if ( v11 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v11);
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v38);
  return 1;
}

```

## disassembly

```asm
0x18001f370  mov     rax, rsp
0x18001f373  mov     [rax+8], rbx
0x18001f377  mov     [rax+18h], rdi
0x18001f37b  mov     [rax+10h], rdx
0x18001f37f  push    rbp
0x18001f380  push    r12
0x18001f382  push    r13
0x18001f384  push    r14
0x18001f386  push    r15
0x18001f388  lea     rbp, [rax-5Fh]
0x18001f38c  sub     rsp, 90h
0x18001f393  mov     r13, r8
0x18001f396  mov     r12, rdx
0x18001f399  mov     r15d, ecx
0x18001f39c  xor     ebx, ebx
0x18001f39e  call    ?Instance@CFocusMonitor@@SAAEAV1@XZ; CFocusMonitor::Instance(void)
0x18001f3a3  lea     rdx, [rbp+57h+arg_18]
0x18001f3a7  mov     rcx, rax
0x18001f3aa  call    ?lock_exclusive@lockable_object@winbio@@QEBA?AVSyncLockExclusive@Details@Wrappers@WRL@Microsoft@@XZ; winbio::lockable_object::lock_exclusive(void)
0x18001f3af  nop
0x18001f3b0  xorps   xmm0, xmm0
0x18001f3b3  movdqu  [rbp+57h+var_50], xmm0
0x18001f3b8  call    ?Instance@CFocusMonitor@@SAAEAV1@XZ; CFocusMonitor::Instance(void)
0x18001f3bd  mov     rax, [rax+18h]
0x18001f3c1  mov     rdx, [rax]
0x18001f3c4  cmp     rdx, rax
0x18001f3c7  jz      short loc_18001F40D
0x18001f3c9  cmp     [rdx+10h], r15d
0x18001f3cd  jz      short loc_18001F3D4
0x18001f3cf  mov     rdx, [rdx]
0x18001f3d2  jmp     short loc_18001F3C4
0x18001f3d4  add     rdx, 18h
0x18001f3d8  lea     rcx, [rbp+57h+var_60]
0x18001f3dc  call    ??0?$shared_ptr@VCBiometricServiceProvider@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<CBiometricServiceProvider>::shared_ptr<CBiometricServiceProvider>(std::shared_ptr<CBiometricServiceProvider> const &)
0x18001f3e1  mov     r14, [rax]
0x18001f3e4  mov     [rax], rbx
0x18001f3e7  mov     qword ptr [rbp+57h+var_50], r14
0x18001f3eb  mov     rdi, [rax+8]
0x18001f3ef  mov     [rax+8], rbx
0x18001f3f3  mov     qword ptr [rbp+57h+var_50+8], rdi
0x18001f3f7  mov     rcx, [rbp+57h+var_58]; this
0x18001f3fb  test    rcx, rcx
0x18001f3fe  jz      short loc_18001F405
0x18001f400  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f405  inc     dword ptr [r14]
0x18001f408  jmp     loc_18001F510
0x18001f40d  mov     ecx, 20h ; ' '; Size
0x18001f412  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f417  mov     rdi, rax
0x18001f41a  mov     [rbp+57h+hObject], rax
0x18001f41e  xorps   xmm0, xmm0
0x18001f421  movups  xmmword ptr [rax], xmm0
0x18001f424  mov     dword ptr [rax+8], 1
0x18001f42b  mov     dword ptr [rax+0Ch], 1
0x18001f432  lea     rax, ??_7?$_Ref_count_obj2@VCFocusClient@@@std@@6B@; const std::_Ref_count_obj2<CFocusClient>::`vftable'
0x18001f439  mov     [rdi], rax
0x18001f43c  lea     r14, [rdi+10h]
0x18001f440  mov     dword ptr [r14], 1
0x18001f447  mov     qword ptr [r14+8], 0FFFFFFFFFFFFFFFFh
0x18001f44f  xor     r9d, r9d; lpName
0x18001f452  xor     r8d, r8d; bInitialState
0x18001f455  xor     edx, edx; bManualReset
0x18001f457  xor     ecx, ecx; lpEventAttributes
0x18001f459  call    cs:__imp_CreateEventW
0x18001f45f  test    rax, rax
0x18001f462  jz      loc_18001F7CC
0x18001f468  mov     [r14+8], rax
0x18001f46c  mov     qword ptr [rbp+57h+var_50], r14
0x18001f470  mov     qword ptr [rbp+57h+var_50+8], rdi
0x18001f474  call    ?Instance@CFocusMonitor@@SAAEAV1@XZ; CFocusMonitor::Instance(void)
0x18001f479  lea     r12, [rax+18h]
0x18001f47d  mov     [rbp+57h+pExceptionObject], r15d
0x18001f481  lea     rdx, [rbp+57h+var_50]
0x18001f485  lea     rcx, [rbp+57h+var_38]
0x18001f489  call    ??0?$shared_ptr@VCBiometricServiceProvider@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<CBiometricServiceProvider>::shared_ptr<CBiometricServiceProvider>(std::shared_ptr<CBiometricServiceProvider> const &)
0x18001f48e  nop
0x18001f48f  mov     rax, 666666666666666h
0x18001f499  cmp     [r12+8], rax
0x18001f49e  jnz     short loc_18001F4AE
0x18001f4a0  lea     rcx, aListTooLong; "list too long"
0x18001f4a7  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001f4ae  mov     rax, [r12]
0x18001f4b2  mov     rbx, [rax]
0x18001f4b5  mov     [rbp+57h+var_60], r12
0x18001f4b9  mov     [rbp+57h+var_58], 0
0x18001f4c1  mov     ecx, 28h ; '('; Size
0x18001f4c6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f4cb  mov     ecx, [rbp+57h+pExceptionObject]
0x18001f4ce  mov     [rax+10h], ecx
0x18001f4d1  mov     rcx, [rbp+57h+var_38]
0x18001f4d5  mov     [rax+18h], rcx
0x18001f4d9  mov     rcx, [rbp+57h+var_30]
0x18001f4dd  mov     [rax+20h], rcx
0x18001f4e1  inc     qword ptr [r12+8]
0x18001f4e6  mov     rcx, [rbx+8]
0x18001f4ea  mov     [rax], rbx
0x18001f4ed  mov     [rax+8], rcx
0x18001f4f1  mov     [rbp+57h+var_58], 0
0x18001f4f9  mov     [rbx+8], rax
0x18001f4fd  mov     [rcx], rax
0x18001f500  lea     rcx, [rbp+57h+var_60]
0x18001f504  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@KV?$shared_ptr@VCFocusClient@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<ulong,std::shared_ptr<CFocusClient>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<ulong,std::shared_ptr<CFocusClient>>,void *>>>(void)
0x18001f509  nop
0x18001f50a  mov     r12, [rbp+57h+arg_8]
0x18001f50e  xor     ebx, ebx
0x18001f510  call    ?Instance@CFocusMonitor@@SAAEAV1@XZ; CFocusMonitor::Instance(void)
0x18001f515  cmp     [rax+10h], bl
0x18001f518  jnz     short loc_18001F53E
0x18001f51a  mov     [r12], rbx
0x18001f51e  mov     [r13+0], rbx
0x18001f522  test    rdi, rdi
0x18001f525  jz      short loc_18001F530
0x18001f527  mov     rcx, rdi; this
0x18001f52a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f52f  nop
0x18001f530  lea     rcx, [rbp+57h+arg_18]; this
0x18001f534  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x18001f539  jmp     loc_18001F7AD
0x18001f53e  mov     r14, [r14+8]
0x18001f542  test    rdi, rdi
0x18001f545  jz      short loc_18001F550
0x18001f547  mov     rcx, rdi; this
0x18001f54a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f54f  nop
0x18001f550  lea     rcx, [rbp+57h+arg_18]; this
0x18001f554  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x18001f559  call    cs:__imp_GetCurrentProcessId
0x18001f55f  mov     r8d, eax; dwProcessId
0x18001f562  mov     edx, 1; bInheritHandle
0x18001f567  lea     edi, [rdx+3Fh]
0x18001f56a  mov     ecx, edi; dwDesiredAccess
0x18001f56c  call    cs:__imp_OpenProcess
0x18001f572  mov     rbx, rax
0x18001f575  test    rax, rax
0x18001f578  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001f57f  cmovz   rbx, rax
0x18001f583  mov     [rbp+57h+var_60], rbx
0x18001f587  cmp     rbx, rax
0x18001f58a  jnz     short loc_18001F5C7
0x18001f58c  mov     eax, cs:dword_18010F170
0x18001f592  cmp     eax, 2
0x18001f595  jbe     short loc_18001F5C0
0x18001f597  call    cs:__imp_GetLastError
0x18001f59d  mov     dword ptr [rbp+57h+arg_18], eax
0x18001f5a0  lea     rax, [rbp+57h+arg_18]
0x18001f5a4  mov     qword ptr [rsp+0B0h+dwDesiredAccess], rax
0x18001f5a9  xor     r8d, r8d
0x18001f5ac  lea     rdx, word_1800EFA42
0x18001f5b3  lea     rcx, dword_18010F170
0x18001f5ba  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001f5bf  nop
0x18001f5c0  xor     al, al
0x18001f5c2  jmp     loc_18001F7AF
0x18001f5c7  mov     r8d, r15d; dwProcessId
0x18001f5ca  mov     edx, 1; bInheritHandle
0x18001f5cf  mov     ecx, edi; dwDesiredAccess
0x18001f5d1  call    cs:__imp_OpenProcess
0x18001f5d7  mov     rdi, rax
0x18001f5da  test    rax, rax
0x18001f5dd  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001f5e4  cmovz   rdi, rax
0x18001f5e8  mov     qword ptr [rbp+57h+var_50], rdi
0x18001f5ec  cmp     rdi, rax
0x18001f5ef  jnz     short loc_18001F630
0x18001f5f1  mov     eax, cs:dword_18010F170
0x18001f5f7  cmp     eax, 2
0x18001f5fa  jbe     short loc_18001F625
0x18001f5fc  call    cs:__imp_GetLastError
0x18001f602  mov     dword ptr [rbp+57h+arg_18], eax
0x18001f605  lea     rax, [rbp+57h+arg_18]
0x18001f609  mov     qword ptr [rsp+0B0h+dwDesiredAccess], rax
0x18001f60e  xor     r8d, r8d
0x18001f611  lea     rdx, byte_1800EFA7B
0x18001f618  lea     rcx, dword_18010F170
0x18001f61f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001f624  nop
0x18001f625  mov     rcx, rbx; hObject
0x18001f628  call    cs:__imp_CloseHandle
0x18001f62e  jmp     short loc_18001F5C0
0x18001f630  mov     [rbp+57h+TargetHandle], 0
0x18001f638  mov     [rbp+57h+hObject], rax
0x18001f63c  mov     [rbp+57h+arg_18], rax
0x18001f640  mov     [rsp+0B0h+dwOptions], 2; dwOptions
0x18001f648  mov     [rsp+0B0h+bInheritHandle], 1; bInheritHandle
0x18001f650  mov     [rsp+0B0h+dwDesiredAccess], 0; dwDesiredAccess
0x18001f658  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x18001f65c  mov     r8, rdi; hTargetProcessHandle
0x18001f65f  mov     rdx, r14; hSourceHandle
0x18001f662  mov     rcx, rbx; hSourceProcessHandle
0x18001f665  call    cs:__imp_DuplicateHandle
0x18001f66b  test    eax, eax
0x18001f66d  jnz     short loc_18001F6B1
0x18001f66f  mov     eax, cs:dword_18010F170
0x18001f675  cmp     eax, 2
0x18001f678  jbe     short loc_18001F6A3
0x18001f67a  call    cs:__imp_GetLastError
0x18001f680  mov     dword ptr [rbp+57h+arg_18], eax
0x18001f683  lea     rax, [rbp+57h+arg_18]
0x18001f687  mov     qword ptr [rsp+0B0h+dwDesiredAccess], rax
0x18001f68c  xor     r8d, r8d
0x18001f68f  lea     rdx, byte_1800EF9C7
0x18001f696  lea     rcx, dword_18010F170
0x18001f69d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001f6a2  nop
0x18001f6a3  mov     rcx, rdi; hObject
0x18001f6a6  call    cs:__imp_CloseHandle
0x18001f6ac  jmp     loc_18001F625
0x18001f6b1  mov     rdx, [rbp+57h+TargetHandle]; void *
0x18001f6b5  lea     rcx, [rbp+57h+hObject]; this
0x18001f6b9  call    ?assign@scoped_handle@winbio@@AEAAXPEAX@Z; winbio::scoped_handle::assign(void *)
0x18001f6be  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001f6c2  mov     [rbp+57h+TargetHandle], r14
0x18001f6c6  call    ?Instance@CFocusMonitor@@SAAEAV1@XZ; CFocusMonitor::Instance(void)
0x18001f6cb  mov     [rsp+0B0h+dwOptions], 2; dwOptions
0x18001f6d3  mov     [rsp+0B0h+bInheritHandle], 1; bInheritHandle
0x18001f6db  mov     [rsp+0B0h+dwDesiredAccess], 0; dwDesiredAccess
0x18001f6e3  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x18001f6e7  mov     r8, rdi; hTargetProcessHandle
0x18001f6ea  mov     rdx, [rax+28h]; hSourceHandle
0x18001f6ee  mov     rcx, rbx; hSourceProcessHandle
0x18001f6f1  call    cs:__imp_DuplicateHandle
0x18001f6f7  test    eax, eax
0x18001f6f9  jnz     short loc_18001F747
0x18001f6fb  mov     eax, cs:dword_18010F170
0x18001f701  cmp     eax, 2
0x18001f704  jbe     short loc_18001F72F
0x18001f706  call    cs:__imp_GetLastError
0x18001f70c  mov     dword ptr [rbp+57h+arg_18], eax
0x18001f70f  lea     rax, [rbp+57h+arg_18]
0x18001f713  mov     qword ptr [rsp+0B0h+dwDesiredAccess], rax
0x18001f718  xor     r8d, r8d
0x18001f71b  lea     rdx, byte_1800EFA03
0x18001f722  lea     rcx, dword_18010F170
0x18001f729  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001f72e  nop
0x18001f72f  mov     rcx, [rbp+57h+hObject]; hObject
0x18001f733  cmp     rcx, r14
0x18001f736  jz      loc_18001F6A3
0x18001f73c  call    cs:__imp_CloseHandle
0x18001f742  jmp     loc_18001F6A3
0x18001f747  mov     rdx, [rbp+57h+TargetHandle]; void *
0x18001f74b  lea     rcx, [rbp+57h+arg_18]; this
0x18001f74f  call    ?assign@scoped_handle@winbio@@AEAAXPEAX@Z; winbio::scoped_handle::assign(void *)
0x18001f754  mov     [rbp+57h+TargetHandle], r14
0x18001f758  mov     rax, [rbp+57h+hObject]
0x18001f75c  mov     [r12], rax
0x18001f760  mov     rax, [rbp+57h+arg_18]
0x18001f764  mov     [r13+0], rax
0x18001f768  mov     eax, cs:dword_18010F170
0x18001f76e  cmp     eax, 4
0x18001f771  jbe     short loc_18001F79A
0x18001f773  mov     dword ptr [rbp+57h+hObject], r15d
0x18001f777  mov     byte ptr [rbp+57h+arg_18], 1
0x18001f77b  lea     rax, [rbp+57h+hObject]
0x18001f77f  mov     qword ptr [rsp+0B0h+bInheritHandle], rax
0x18001f784  lea     rax, [rbp+57h+arg_18]
0x18001f788  mov     qword ptr [rsp+0B0h+dwDesiredAccess], rax
0x18001f78d  lea     rdx, word_1800EF936
0x18001f794  call    ??$Write@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x18001f799  nop
0x18001f79a  mov     rcx, rdi; hObject
0x18001f79d  call    cs:__imp_CloseHandle
0x18001f7a3  nop
0x18001f7a4  mov     rcx, rbx; hObject
0x18001f7a7  call    cs:__imp_CloseHandle
0x18001f7ad  mov     al, 1
0x18001f7af  lea     r11, [rsp+0B0h+var_20]
0x18001f7b7  mov     rbx, [r11+30h]
0x18001f7bb  mov     rdi, [r11+40h]
0x18001f7bf  mov     rsp, r11
0x18001f7c2  pop     r15
0x18001f7c4  pop     r14
0x18001f7c6  pop     r13
0x18001f7c8  pop     r12
0x18001f7ca  pop     rbp
0x18001f7cb  retn
0x18001f7cc  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18001f7d0  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18001f7d5  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001f7dc  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001f7e0  call    _CxxThrowException_0
```
