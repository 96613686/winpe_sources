# CHardwareManager::RegisterFrameworkChangeNotification(ulong,void *,ulong,uint,unsigned __int64 *,unsigned __int64 *)

- ea: `0x1800112c8`
- end: `0x1800118ce`
- name: `?RegisterFrameworkChangeNotification@CHardwareManager@@SA_NKPEAXKIPEA_K1@Z`
- size: `1542`
- prototype: `char __fastcall(DWORD dwProcessId, unsigned __int64, int, int, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003bc70`

## callees

- `0x18000b760`
- `0x180010bfc`
- `0x1800112c8`
- `0x1800119c4`
- `0x180020fe8`
- `0x180028af0`
- `0x180029820`
- `0x180035280`
- `0x180036800`
- `0x18005dc14`
- `0x18005ec64`
- `0x18006963c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800113b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011836`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800113b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011836`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011303`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011303`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800113a4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800113a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001143d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001143d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001149b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011632`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001163c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001164d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001165e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011671`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011716`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011720`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011731`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011740`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800117eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800117f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011804`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011813`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011822`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011861`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011870`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011885`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011896`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800118a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001149b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011632`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001163c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001164d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001165e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011671`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011716`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011720`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011731`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011740`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800117eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800117f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011804`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011813`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011822`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011861`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011870`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011885`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011896`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800118a7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001159a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800116af`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001159a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800116af`
- `api-ms-win-core-namedpipe-l1-1-0!CreatePipe` at `0x180011406`
- `api-ms-win-core-namedpipe-l1-1-0!CreatePipe` at `0x180011406`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180011452`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001147b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180011452`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001147b`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
char __fastcall CHardwareManager::RegisterFrameworkChangeNotification(
        DWORD dwProcessId,
        unsigned __int64 a2,
        int a3,
        int a4,
        unsigned __int64 *a5,
        unsigned __int64 *a6)
{
  RTL_SRWLOCK *v8; // rdi
  char v9; // r12
  unsigned __int64 *v10; // r15
  unsigned __int64 *v11; // r13
  __int64 *v12; // rcx
  __int64 *v13; // rax
  __int64 *v14; // rbx
  HANDLE EventW; // rax
  DWORD CurrentProcessId; // eax
  __int64 v18; // r15
  HANDLE v19; // rax
  __int64 v20; // r14
  _QWORD *v21; // rax
  winbio::scoped_handle **v22; // rcx
  std::_Ref_count_base *v23; // rax
  volatile signed __int32 *v24; // rsi
  char *v25; // rcx
  __int64 v26; // rbx
  BOOL v27; // eax
  winbio::scoped_handle *v28; // r8
  winbio::scoped_handle *v29; // rax
  winbio::scoped_handle *v30; // rcx
  struct CHardwareManager *v31; // rax
  __int64 v32; // rax
  __int64 v33; // rcx
  HANDLE v34; // rdi
  struct CHardwareManager *v35; // rax
  __int64 v36; // rsi
  struct CHardwareManager *v37; // rax
  HANDLE v38; // rcx
  winbio::scoped_handle *v39; // rax
  void *v40; // rdx
  __int64 v41; // rsi
  HANDLE hObject; // [rsp+40h] [rbp-D8h] BYREF
  winbio::scoped_handle *v43; // [rsp+48h] [rbp-D0h]
  HANDLE hSourceHandle; // [rsp+50h] [rbp-C8h] BYREF
  HANDLE v45; // [rsp+58h] [rbp-C0h] BYREF
  void *hReadPipe; // [rsp+60h] [rbp-B8h] BYREF
  void *hWritePipe; // [rsp+68h] [rbp-B0h] BYREF
  std::_Ref_count_base *v48; // [rsp+70h] [rbp-A8h]
  HANDLE TargetHandle; // [rsp+78h] [rbp-A0h] BYREF
  HANDLE v50; // [rsp+80h] [rbp-98h] BYREF
  PSRWLOCK SRWLock; // [rsp+88h] [rbp-90h] BYREF
  HANDLE v52; // [rsp+90h] [rbp-88h] BYREF
  unsigned __int64 v53; // [rsp+98h] [rbp-80h] BYREF
  winbio::scoped_handle *v54; // [rsp+A0h] [rbp-78h]
  std::_Ref_count_base *v55; // [rsp+A8h] [rbp-70h]
  HANDLE v56; // [rsp+B0h] [rbp-68h]
  RTL_SRWLOCK *v57; // [rsp+B8h] [rbp-60h] BYREF
  std::_Ref_count_base *v58[2]; // [rsp+C0h] [rbp-58h]
  _BYTE v59[8]; // [rsp+D0h] [rbp-48h] BYREF
  std::_Ref_count_base *v60; // [rsp+D8h] [rbp-40h]
  unsigned __int64 v61; // [rsp+128h] [rbp+10h] BYREF
  int v62; // [rsp+130h] [rbp+18h]
  int v63; // [rsp+138h] [rbp+20h]

  v63 = a4;
  v62 = a3;
  v61 = a2;
  v8 = (RTL_SRWLOCK *)((char *)CHardwareManager::Instance() + 8);
  SRWLock = v8;
  AcquireSRWLockExclusive(v8);
  v57 = v8;
  v9 = 0;
  if ( !dwProcessId || !a2 || (v10 = a5) == 0 || (v11 = a6) == 0 )
  {
LABEL_15:
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
    return 0;
  }
  v12 = (__int64 *)*((_QWORD *)CHardwareManager::Instance() + 9);
  v13 = (__int64 *)v12[1];
  HIDWORD(v54) = 0;
  v14 = v12;
  while ( !*((_BYTE *)v13 + 25) )
  {
    if ( v13[4] >= a2 )
    {
      v14 = v13;
      v13 = (__int64 *)*v13;
    }
    else
    {
      v13 = (__int64 *)v13[2];
    }
  }
  if ( *((_BYTE *)v14 + 25) || a2 < v14[4] )
    v14 = v12;
  if ( v14 != *((__int64 **)CHardwareManager::Instance() + 9) )
  {
    *v10 = 0;
    *v11 = 0;
    v9 = 1;
    goto LABEL_89;
  }
  hSourceHandle = (HANDLE)-1LL;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW )
    goto LABEL_15;
  winbio::scoped_handle::assign((winbio::scoped_handle *)&hSourceHandle, EventW);
  hReadPipe = (void *)-1LL;
  hWritePipe = (void *)-1LL;
  v45 = (HANDLE)-1LL;
  hObject = (HANDLE)-1LL;
  if ( !CreatePipe(&hReadPipe, &hWritePipe, 0, 0x14u) )
  {
LABEL_86:
    v38 = hSourceHandle;
    if ( hSourceHandle == (HANDLE)-1LL )
    {
LABEL_89:
      Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v57);
      return v9;
    }
LABEL_87:
    CloseHandle(v38);
    goto LABEL_89;
  }
  winbio::scoped_handle::assign((winbio::scoped_handle *)&v45, hReadPipe);
  hReadPipe = (void *)-1LL;
  winbio::scoped_handle::assign((winbio::scoped_handle *)&hObject, hWritePipe);
  hWritePipe = (void *)-1LL;
  CurrentProcessId = GetCurrentProcessId();
  v18 = (__int64)OpenProcess(0x40u, 1, CurrentProcessId);
  if ( !v18 )
    v18 = -1;
  v52 = (HANDLE)v18;
  if ( v18 == -1 )
  {
LABEL_82:
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
    if ( v45 != (HANDLE)-1LL )
      CloseHandle(v45);
    goto LABEL_86;
  }
  v19 = OpenProcess(0x40u, 1, dwProcessId);
  v20 = (__int64)v19;
  if ( !v19 )
    v20 = -1;
  v56 = (HANDLE)v20;
  if ( v20 == -1 )
  {
    CloseHandle((HANDLE)v18);
    goto LABEL_82;
  }
  try
  {
    *(_OWORD *)v58 = 0;
    v21 = operator new(0x18u);
    *v21 = -1;
    v21[1] = -1;
    v21[2] = 0;
    v22 = (winbio::scoped_handle **)std::shared_ptr<CHardwareChangeSubscription>::shared_ptr<CHardwareChangeSubscription>(
                                      v59,
                                      v21);
    v43 = *v22;
    v23 = v43;
    v48 = v22[1];
    v24 = (volatile signed __int32 *)v48;
    *v22 = 0;
    v22[1] = 0;
    v58[0] = v23;
    v58[1] = (std::_Ref_count_base *)v24;
    if ( v60 )
      std::_Ref_count_base::_Decref(v60);
    v25 = (char *)CHardwareManager::Instance() + 72;
    v53 = v61;
    if ( v24 )
      _InterlockedAdd(v24 + 2, 1u);
    v54 = v43;
    v55 = (std::_Ref_count_base *)v24;
    std::_Tree<std::_Tmap_traits<void *,std::shared_ptr<CHardwareChangeSubscription>,std::less<void *>,std::allocator<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>>,0>>::_Emplace<std::pair<void *,std::shared_ptr<CHardwareChangeSubscription>>>(
      v25,
      v59,
      &v53);
    if ( v55 )
      std::_Ref_count_base::_Decref(v55);
    TargetHandle = (HANDLE)-1LL;
    v26 = (__int64)hSourceHandle;
    v27 = DuplicateHandle((HANDLE)v18, hSourceHandle, (HANDLE)v20, &TargetHandle, 0, 1, 2u);
  }
  catch ( std::bad_alloc )
  {
    v9 = 0;
    if ( v58[1] )
      std::_Ref_count_base::_Decref(v58[1]);
    CloseHandle(v56);
    CloseHandle(v52);
    goto LABEL_82;
  }
  if ( !v27 )
  {
    v28 = (winbio::scoped_handle *)*((_QWORD *)CHardwareManager::Instance() + 9);
    v29 = (winbio::scoped_handle *)*((_QWORD *)v28 + 1);
    v30 = v28;
    v43 = v28;
    while ( !*((_BYTE *)v29 + 25) )
    {
      if ( *((_QWORD *)v29 + 4) >= v61 )
      {
        v30 = v29;
        v43 = v29;
        v29 = *(winbio::scoped_handle **)v29;
      }
      else
      {
        v29 = (winbio::scoped_handle *)*((_QWORD *)v29 + 2);
      }
    }
    if ( *((_BYTE *)v30 + 25) || v61 < *((_QWORD *)v30 + 4) )
      v43 = v28;
    if ( v43 != *((winbio::scoped_handle **)CHardwareManager::Instance() + 9) )
    {
      v31 = CHardwareManager::Instance();
      v32 = std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>>>::_Extract(
              (char *)v31 + 72,
              v43);
      std::_Tree_node<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>,void *>>>(
        v33,
        v32);
    }
    if ( v24 )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v24);
    CloseHandle((HANDLE)v20);
    CloseHandle((HANDLE)v18);
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
    if ( v45 != (HANDLE)-1LL )
      CloseHandle(v45);
    if ( v26 != -1 )
      CloseHandle((HANDLE)v26);
    goto LABEL_15;
  }
  v50 = (HANDLE)-1LL;
  v34 = v45;
  if ( !DuplicateHandle((HANDLE)v18, v45, (HANDLE)v20, &v50, 0, 1, 2u) )
  {
    v35 = CHardwareManager::Instance();
    v36 = *(_QWORD *)std::_Tree<std::_Tmap_traits<void *,std::shared_ptr<CHardwareChangeSubscription>,std::less<void *>,std::allocator<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>>,0>>::find(
                       (char *)v35 + 72,
                       &SRWLock,
                       &v61);
    if ( v36 != *((_QWORD *)CHardwareManager::Instance() + 9) )
    {
      v37 = CHardwareManager::Instance();
      std::_Tree<std::_Tmap_traits<void *,std::shared_ptr<CHardwareChangeSubscription>,std::less<void *>,std::allocator<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>>>>,0>(
        (char *)v37 + 72,
        &v52,
        v36);
    }
    if ( v48 )
      std::_Ref_count_base::_Decref(v48);
    CloseHandle((HANDLE)v20);
    CloseHandle((HANDLE)v18);
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
    if ( v34 != (HANDLE)-1LL )
      CloseHandle(v34);
    if ( v26 == -1 )
      goto LABEL_89;
    v38 = (HANDLE)v26;
    goto LABEL_87;
  }
  v39 = v43;
  if ( v43 != (winbio::scoped_handle *)&hSourceHandle )
  {
    v40 = (void *)v26;
    v26 = -1;
    winbio::scoped_handle::assign(v43, v40);
    v39 = v43;
  }
  if ( (HANDLE *)((char *)v39 + 8) == &hObject )
  {
    v41 = (__int64)hObject;
  }
  else
  {
    v41 = -1;
    winbio::scoped_handle::assign((winbio::scoped_handle *)((char *)v39 + 8), hObject);
    v39 = v43;
  }
  *((_DWORD *)v39 + 4) = v62;
  *((_DWORD *)v39 + 5) = v63;
  *a5 = (unsigned __int64)TargetHandle;
  *a6 = (unsigned __int64)v50;
  if ( v48 )
    std::_Ref_count_base::_Decref(v48);
  CloseHandle((HANDLE)v20);
  CloseHandle((HANDLE)v18);
  if ( v41 != -1 )
    CloseHandle((HANDLE)v41);
  if ( v34 != (HANDLE)-1LL )
    CloseHandle(v34);
  if ( v26 != -1 )
    CloseHandle((HANDLE)v26);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return 1;
}

```

## disassembly

```asm
0x1800112c8  mov     [rsp+arg_18], r9d
0x1800112cd  mov     [rsp+arg_10], r8d
0x1800112d2  mov     [rsp+arg_8], rdx
0x1800112d7  push    rbx
0x1800112d8  push    rsi
0x1800112d9  push    rdi
0x1800112da  push    r12
0x1800112dc  push    r13
0x1800112de  push    r14
0x1800112e0  push    r15
0x1800112e2  sub     rsp, 0E0h
0x1800112e9  mov     rsi, rdx
0x1800112ec  mov     r14d, ecx
0x1800112ef  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800112f4  lea     rdi, [rax+8]
0x1800112f8  mov     [rsp+118h+SRWLock], rdi
0x180011300  mov     rcx, rdi; SRWLock
0x180011303  call    cs:__imp_AcquireSRWLockExclusive
0x180011309  mov     [rsp+118h+var_60], rdi
0x180011311  xor     r12d, r12d
0x180011314  test    r14d, r14d
0x180011317  jz      loc_1800113AF
0x18001131d  test    rsi, rsi
0x180011320  jz      loc_1800113AF
0x180011326  mov     r15, [rsp+118h+arg_20]
0x18001132e  test    r15, r15
0x180011331  jz      short loc_1800113AF
0x180011333  mov     r13, [rsp+118h+arg_28]
0x18001133b  test    r13, r13
0x18001133e  jz      short loc_1800113AF
0x180011340  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180011345  mov     rcx, [rax+48h]
0x180011349  mov     rax, [rcx+8]
0x18001134d  xor     edx, edx
0x18001134f  mov     [rsp+118h+var_74], edx
0x180011356  mov     rbx, rcx
0x180011359  jmp     short loc_18001136D
0x18001135b  cmp     [rax+20h], rsi
0x18001135f  jnb     short loc_180011367
0x180011361  mov     rax, [rax+10h]
0x180011365  jmp     short loc_18001136D
0x180011367  mov     rbx, rax
0x18001136a  mov     rax, [rax]
0x18001136d  cmp     [rax+19h], r12b
0x180011371  jz      short loc_18001135B
0x180011373  cmp     [rbx+19h], r12b
0x180011377  jnz     short loc_18001137F
0x180011379  cmp     rsi, [rbx+20h]
0x18001137d  jnb     short loc_180011382
0x18001137f  mov     rbx, rcx
0x180011382  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180011387  cmp     rbx, [rax+48h]
0x18001138b  jnz     loc_1800118AF
0x180011391  or      r13, 0FFFFFFFFFFFFFFFFh
0x180011395  mov     [rsp+118h+hSourceHandle], r13
0x18001139a  xor     r9d, r9d; lpName
0x18001139d  xor     r8d, r8d; bInitialState
0x1800113a0  xor     edx, edx; bManualReset
0x1800113a2  xor     ecx, ecx; lpEventAttributes
0x1800113a4  call    cs:__imp_CreateEventW
0x1800113aa  test    rax, rax
0x1800113ad  jnz     short loc_1800113D2
0x1800113af  test    rdi, rdi
0x1800113b2  jz      short loc_1800113BD
0x1800113b4  mov     rcx, rdi; SRWLock
0x1800113b7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800113bd  xor     al, al
0x1800113bf  add     rsp, 0E0h
0x1800113c6  pop     r15
0x1800113c8  pop     r14
0x1800113ca  pop     r13
0x1800113cc  pop     r12
0x1800113ce  pop     rdi
0x1800113cf  pop     rsi
0x1800113d0  pop     rbx
0x1800113d1  retn
0x1800113d2  mov     rdx, rax; void *
0x1800113d5  lea     rcx, [rsp+118h+hSourceHandle]; this
0x1800113da  call    ?assign@scoped_handle@winbio@@AEAAXPEAX@Z; winbio::scoped_handle::assign(void *)
0x1800113df  mov     [rsp+118h+hReadPipe], r13
0x1800113e4  mov     [rsp+118h+hWritePipe], r13
0x1800113e9  mov     [rsp+118h+var_C0], r13
0x1800113ee  mov     [rsp+118h+hObject], r13
0x1800113f3  mov     r9d, 14h; nSize
0x1800113f9  xor     r8d, r8d; lpPipeAttributes
0x1800113fc  lea     rdx, [rsp+118h+hWritePipe]; hWritePipe
0x180011401  lea     rcx, [rsp+118h+hReadPipe]; hReadPipe
0x180011406  call    cs:__imp_CreatePipe
0x18001140c  test    eax, eax
0x18001140e  jnz     short loc_180011415
0x180011410  jmp     loc_18001189D
0x180011415  mov     rdx, [rsp+118h+hReadPipe]; void *
0x18001141a  lea     rcx, [rsp+118h+var_C0]; this
0x18001141f  call    ?assign@scoped_handle@winbio@@AEAAXPEAX@Z; winbio::scoped_handle::assign(void *)
0x180011424  mov     [rsp+118h+hReadPipe], r13
0x180011429  mov     rdx, [rsp+118h+hWritePipe]; void *
0x18001142e  lea     rcx, [rsp+118h+hObject]; this
0x180011433  call    ?assign@scoped_handle@winbio@@AEAAXPEAX@Z; winbio::scoped_handle::assign(void *)
0x180011438  mov     [rsp+118h+hWritePipe], r13
0x18001143d  call    cs:__imp_GetCurrentProcessId
0x180011443  mov     r8d, eax; dwProcessId
0x180011446  mov     ebx, 1
0x18001144b  mov     edx, ebx; bInheritHandle
0x18001144d  lea     esi, [rbx+3Fh]
0x180011450  mov     ecx, esi; dwDesiredAccess
0x180011452  call    cs:__imp_OpenProcess
0x180011458  mov     r15, rax
0x18001145b  test    rax, rax
0x18001145e  cmovz   r15, r13
0x180011462  mov     [rsp+118h+var_88], r15
0x18001146a  cmp     r15, r13
0x18001146d  jnz     short loc_180011474
0x18001146f  jmp     loc_18001187B
0x180011474  mov     r8d, r14d; dwProcessId
0x180011477  mov     edx, ebx; bInheritHandle
0x180011479  mov     ecx, esi; dwDesiredAccess
0x18001147b  call    cs:__imp_OpenProcess
0x180011481  mov     r14, rax
0x180011484  test    rax, rax
0x180011487  cmovz   r14, r13
0x18001148b  mov     [rsp+118h+var_68], r14
0x180011493  cmp     r14, r13
0x180011496  jnz     short loc_1800114A3
0x180011498  mov     rcx, r15; hObject
0x18001149b  call    cs:__imp_CloseHandle
0x1800114a1  jmp     short loc_18001146F
0x1800114a3  xorps   xmm0, xmm0
0x1800114a6  movdqu  xmmword ptr [rsp+118h+var_58], xmm0
0x1800114af  mov     ecx, 18h; Size
0x1800114b4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800114b9  mov     [rax], r13
0x1800114bc  mov     [rax+8], r13
0x1800114c0  mov     [rax+10h], r12
0x1800114c4  mov     rdx, rax
0x1800114c7  lea     rcx, [rsp+118h+var_48]
0x1800114cf  call    ??$?0VCHardwareChangeSubscription@@$0A@@?$shared_ptr@VCHardwareChangeSubscription@@@std@@QEAA@PEAVCHardwareChangeSubscription@@@Z; std::shared_ptr<CHardwareChangeSubscription>::shared_ptr<CHardwareChangeSubscription>(CHardwareChangeSubscription *)
0x1800114d4  mov     rcx, rax
0x1800114d7  mov     rax, [rax]
0x1800114da  mov     [rsp+118h+var_D0], rax
0x1800114df  mov     rsi, [rcx+8]
0x1800114e3  mov     [rsp+118h+var_A8], rsi
0x1800114e8  mov     [rcx], r12
0x1800114eb  mov     [rcx+8], r12
0x1800114ef  mov     [rsp+118h+var_58], rax
0x1800114f7  mov     [rsp+118h+var_58+8], rsi
0x1800114ff  mov     rcx, [rsp+118h+var_40]; this
0x180011507  test    rcx, rcx
0x18001150a  jz      short loc_180011511
0x18001150c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180011511  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180011516  lea     rcx, [rax+48h]
0x18001151a  mov     rax, [rsp+118h+arg_8]
0x180011522  mov     [rsp+118h+var_80], rax
0x18001152a  test    rsi, rsi
0x18001152d  jz      short loc_180011533
0x18001152f  lock add [rsi+8], ebx
0x180011533  mov     rax, [rsp+118h+var_D0]
0x180011538  mov     [rsp+0A0h], rax
0x180011540  mov     [rsp+118h+var_70], rsi
0x180011548  lea     r8, [rsp+118h+var_80]
0x180011550  lea     rdx, [rsp+118h+var_48]
0x180011558  call    ??$_Emplace@U?$pair@PEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@PEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@U?$less@PEAX@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@PEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<void *,std::shared_ptr<CHardwareChangeSubscription>,std::less<void *>,std::allocator<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>>,0>>::_Emplace<std::pair<void *,std::shared_ptr<CHardwareChangeSubscription>>>(std::pair<void *,std::shared_ptr<CHardwareChangeSubscription>> &&)
0x18001155d  nop
0x18001155e  mov     rcx, [rsp+118h+var_70]; this
0x180011566  test    rcx, rcx
0x180011569  jz      short loc_180011571
0x18001156b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180011570  nop
0x180011571  mov     [rsp+118h+TargetHandle], r13
0x180011576  mov     [rsp+118h+dwOptions], 2; dwOptions
0x18001157e  mov     [rsp+118h+bInheritHandle], ebx; bInheritHandle
0x180011582  mov     [rsp+118h+dwDesiredAccess], r12d; dwDesiredAccess
0x180011587  lea     r9, [rsp+118h+TargetHandle]; lpTargetHandle
0x18001158c  mov     r8, r14; hTargetProcessHandle
0x18001158f  mov     rbx, [rsp+118h+hSourceHandle]
0x180011594  mov     rdx, rbx; hSourceHandle
0x180011597  mov     rcx, r15; hSourceProcessHandle
0x18001159a  call    cs:__imp_DuplicateHandle
0x1800115a0  test    eax, eax
0x1800115a2  jnz     loc_18001167C
0x1800115a8  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800115ad  mov     r8, [rax+48h]
0x1800115b1  mov     rax, [r8+8]
0x1800115b5  mov     rcx, r8
0x1800115b8  mov     [rsp+118h+var_D0], rcx
0x1800115bd  mov     rdx, [rsp+118h+arg_8]
0x1800115c5  cmp     [rax+19h], r12b
0x1800115c9  jnz     short loc_1800115E4
0x1800115cb  cmp     [rax+20h], rdx
0x1800115cf  jnb     short loc_1800115D7
0x1800115d1  mov     rax, [rax+10h]
0x1800115d5  jmp     short loc_1800115C5
0x1800115d7  mov     rcx, rax
0x1800115da  mov     [rsp+118h+var_D0], rax
0x1800115df  mov     rax, [rax]
0x1800115e2  jmp     short loc_1800115C5
0x1800115e4  cmp     [rcx+19h], r12b
0x1800115e8  jnz     short loc_1800115F0
0x1800115ea  cmp     rdx, [rcx+20h]
0x1800115ee  jnb     short loc_1800115F5
0x1800115f0  mov     [rsp+118h+var_D0], r8
0x1800115f5  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800115fa  mov     rcx, [rsp+118h+var_D0]
0x1800115ff  cmp     rcx, [rax+48h]
0x180011603  jz      short loc_180011621
0x180011605  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x18001160a  lea     rcx, [rax+48h]
0x18001160e  mov     rdx, [rsp+118h+var_D0]
0x180011613  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>>>,std::_Iterator_base0>)
0x180011618  mov     rdx, rax
0x18001161b  call    ??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@QEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@QEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_Tree_node<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>,void *>>>(std::allocator<std::_Tree_node<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>,void *>> &,std::_Tree_node<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>,void *> *)
0x180011620  nop
0x180011621  test    rsi, rsi
0x180011624  jz      short loc_18001162F
0x180011626  mov     rcx, rsi; this
0x180011629  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001162e  nop
0x18001162f  mov     rcx, r14; hObject
0x180011632  call    cs:__imp_CloseHandle
0x180011638  nop
0x180011639  mov     rcx, r15; hObject
0x18001163c  call    cs:__imp_CloseHandle
0x180011642  nop
0x180011643  mov     rcx, [rsp+118h+hObject]; hObject
0x180011648  cmp     rcx, r13
0x18001164b  jz      short loc_180011654
0x18001164d  call    cs:__imp_CloseHandle
0x180011653  nop
0x180011654  mov     rcx, [rsp+118h+var_C0]; hObject
0x180011659  cmp     rcx, r13
0x18001165c  jz      short loc_180011665
0x18001165e  call    cs:__imp_CloseHandle
0x180011664  nop
0x180011665  cmp     rbx, r13
0x180011668  jz      loc_1800113AF
0x18001166e  mov     rcx, rbx; hObject
0x180011671  call    cs:__imp_CloseHandle
0x180011677  jmp     loc_1800113AF
0x18001167c  mov     [rsp+118h+var_98], r13
0x180011684  mov     [rsp+118h+dwOptions], 2; dwOptions
0x18001168c  mov     [rsp+118h+bInheritHandle], 1; bInheritHandle
0x180011694  mov     [rsp+118h+dwDesiredAccess], r12d; dwDesiredAccess
0x180011699  lea     r9, [rsp+118h+var_98]; lpTargetHandle
0x1800116a1  mov     r8, r14; hTargetProcessHandle
0x1800116a4  mov     rdi, [rsp+118h+var_C0]
0x1800116a9  mov     rdx, rdi; hSourceHandle
0x1800116ac  mov     rcx, r15; hSourceProcessHandle
0x1800116af  call    cs:__imp_DuplicateHandle
0x1800116b5  test    eax, eax
0x1800116b7  jnz     loc_180011758
0x1800116bd  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800116c2  lea     rcx, [rax+48h]
0x1800116c6  lea     r8, [rsp+118h+arg_8]
0x1800116ce  lea     rdx, [rsp+118h+SRWLock]
0x1800116d6  call    ?find@?$_Tree@V?$_Tmap_traits@PEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@U?$less@PEAX@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@@std@@@std@@@std@@@2@AEBQEAX@Z; std::_Tree<std::_Tmap_traits<void *,std::shared_ptr<CHardwareChangeSubscription>,std::less<void *>,std::allocator<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>>,0>>::find(void * const &)
0x1800116db  mov     rsi, [rax]
0x1800116de  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800116e3  cmp     rsi, [rax+48h]
0x1800116e7  jz      short loc_180011703
0x1800116e9  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800116ee  lea     rcx, [rax+48h]
0x1800116f2  mov     r8, rsi
0x1800116f5  lea     rdx, [rsp+118h+var_88]
0x1800116fd  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@PEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@U?$less@PEAX@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAXV?$shared_ptr@VCHardwareChangeSubscription@@@std@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<void *,std::shared_ptr<CHardwareChangeSubscription>,std::less<void *>,std::allocator<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::shared_ptr<CHardwareChangeSubscription>>>>>)
0x180011702  nop
0x180011703  mov     rcx, [rsp+118h+var_A8]; this
0x180011708  test    rcx, rcx
0x18001170b  jz      short loc_180011713
0x18001170d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180011712  nop
0x180011713  mov     rcx, r14; hObject
0x180011716  call    cs:__imp_CloseHandle
0x18001171c  nop
0x18001171d  mov     rcx, r15; hObject
0x180011720  call    cs:__imp_CloseHandle
0x180011726  nop
0x180011727  mov     rcx, [rsp+118h+hObject]; hObject
0x18001172c  cmp     rcx, r13
0x18001172f  jz      short loc_180011738
0x180011731  call    cs:__imp_CloseHandle
0x180011737  nop
0x180011738  cmp     rdi, r13
0x18001173b  jz      short loc_180011747
0x18001173d  mov     rcx, rdi; hObject
0x180011740  call    cs:__imp_CloseHandle
0x180011746  nop
0x180011747  cmp     rbx, r13
0x18001174a  jz      loc_1800118B9
0x180011750  mov     rcx, rbx
0x180011753  jmp     loc_1800118A7
0x180011758  lea     rcx, [rsp+118h+hSourceHandle]
0x18001175d  mov     rax, [rsp+118h+var_D0]
0x180011762  cmp     rax, rcx
0x180011765  jz      short loc_18001177A
0x180011767  mov     rdx, rbx; void *
0x18001176a  mov     rbx, r13
0x18001176d  mov     rcx, rax; this
0x180011770  call    ?assign@scoped_handle@winbio@@AEAAXPEAX@Z; winbio::scoped_handle::assign(void *)
0x180011775  mov     rax, [rsp+118h+var_D0]
0x18001177a  lea     rcx, [rax+8]; this
  ... truncated ...
```
