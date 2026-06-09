# RpcServer::GetLastRunInfo(ushort const *,_SYSTEMTIME *,ulong *)

- ea: `0x18001eae0`
- end: `0x18001f056`
- name: `?GetLastRunInfo@RpcServer@@QEAAJPEBGPEAU_SYSTEMTIME@@PEAK@Z`
- size: `1398`
- prototype: `__int64 __fastcall(RpcServer *__hidden this, const unsigned __int16 *, struct _SYSTEMTIME *, unsigned int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001eab0`

## callees

- `0x180010390`
- `0x180011e40`
- `0x180013a90`
- `0x1800141e0`
- `0x1800170b0`
- `0x18001ea40`
- `0x18001eae0`
- `0x18001f060`
- `0x180024730`
- `0x18002f814`
- `0x18003de20`
- `0x1800457fc`
- `0x180045c4c`
- `0x18005a2bc`
- `0x1800829fa`
- `0x180082a40`
- `0x180088010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eda4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eda4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ee97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ef3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ee97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ef3b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001edfd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001edfd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001ee27`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001ee71`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001eeaa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001ee27`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001ee71`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001eeaa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ed77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ed77`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001ed94`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001ed94`
- `RPCRT4!RpcImpersonateClient` at `0x18001ed0b`
- `RPCRT4!RpcImpersonateClient` at `0x18001ed0b`
- `RPCRT4!RpcRevertToSelf` at `0x18001edbf`
- `RPCRT4!RpcRevertToSelf` at `0x18001edd5`
- `RPCRT4!RpcRevertToSelf` at `0x18001edbf`
- `RPCRT4!RpcRevertToSelf` at `0x18001edd5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RpcServer::GetLastRunInfo(
        RTL_SRWLOCK *this,
        const unsigned __int16 *a2,
        struct _SYSTEMTIME *a3,
        unsigned int *a4)
{
  const unsigned __int16 *v6; // rbx
  __int64 v8; // r11
  __int64 v9; // r8
  __int64 v10; // rcx
  const OLECHAR *v11; // rax
  __int64 v12; // r9
  OLECHAR *v13; // r10
  OLECHAR v14; // dx
  unsigned int v15; // edx
  OLECHAR *v16; // rcx
  unsigned __int16 v17; // dx
  int i; // r9d
  int v19; // edi
  bool v20; // zf
  __int64 v21; // r9
  OLECHAR *v22; // rax
  __int64 v23; // r10
  OLECHAR *v24; // r9
  unsigned __int16 v25; // ax
  const OLECHAR *v26; // rax
  OLECHAR v27; // cx
  OLECHAR *v28; // rcx
  RPC_STATUS v30; // eax
  EventManager *v31; // rcx
  RPC_STATUS v32; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int DynamicTaskInfo; // ebx
  int v36; // edi
  int v37; // edi
  RTL_SRWLOCK *v38; // rcx
  int v39; // eax
  __int64 v40; // rax
  HKEY *v41; // [rsp+20h] [rbp-E0h]
  const struct _GUID *v42; // [rsp+28h] [rbp-D8h]
  unsigned int v43; // [rsp+40h] [rbp-C0h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v45; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD pExceptionObject[5]; // [rsp+58h] [rbp-A8h] BYREF
  RPC_STATUS v47; // [rsp+80h] [rbp-80h]
  __int64 v48; // [rsp+84h] [rbp-7Ch]
  __int128 v49; // [rsp+90h] [rbp-70h] BYREF
  __int64 v50; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v51; // [rsp+A8h] [rbp-58h] BYREF
  struct _SYSTEMTIME v52; // [rsp+B0h] [rbp-50h] BYREF
  GUID iid; // [rsp+C0h] [rbp-40h] BYREF
  char v54[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v55; // [rsp+E0h] [rbp-20h] BYREF
  OLECHAR psz[264]; // [rsp+F0h] [rbp-10h] BYREF

  v6 = a2;
  if ( !a2 || !a3 || !a4 )
    return 2147942487LL;
  *a3 = 0;
  *a4 = 267011;
  memset_0(psz, 0, 0x20Au);
  v8 = 2147483646;
  v9 = 261;
  if ( !*v6 )
  {
    v26 = L"\\";
    v24 = psz;
    do
    {
      if ( !v8 )
        break;
      v27 = *v26;
      if ( !*v26 )
        break;
      ++v26;
      *v24++ = v27;
      --v8;
      --v9;
    }
    while ( v9 );
    goto LABEL_45;
  }
  if ( *v6 != 92 )
  {
    v10 = 2147483646;
    v11 = L"\\";
    v12 = 261;
    v13 = psz;
    do
    {
      if ( !v10 )
        break;
      v14 = *v11;
      if ( !*v11 )
        break;
      ++v11;
      *v13++ = v14;
      --v10;
      --v12;
    }
    while ( v12 );
    v15 = v12 == 0 ? 0x8007007A : 0;
    v16 = v13 - 1;
    if ( v12 )
      v16 = v13;
    *v16 = 0;
    if ( !v12 )
      return v15;
  }
  v17 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= 261 )
      return (unsigned int)-2147024773;
    v19 = v6[i];
    if ( !(_WORD)v19 )
      break;
    switch ( v19 )
    {
      case ' ':
        if ( v17 == 92 )
          return (unsigned int)-2147024773;
        v20 = v17 == 0;
LABEL_27:
        if ( v20 )
          return (unsigned int)-2147024773;
        break;
      case '.':
        if ( v17 == 46 )
          return (unsigned int)-2147024773;
        if ( v17 != 92 )
          break;
        v20 = v6[i + 1] == 92;
        goto LABEL_27;
      case '/':
      case ':':
        return (unsigned int)-2147024773;
      case '\\':
        v20 = v17 == 92;
        goto LABEL_27;
    }
    v17 = v6[i];
  }
  if ( v17 == 92 && i > 1 )
    return (unsigned int)-2147024773;
  v21 = 261;
  v22 = psz;
  do
  {
    if ( !*v22 )
      break;
    ++v22;
    --v21;
  }
  while ( v21 );
  v15 = v21 == 0 ? 0x80070057 : 0;
  v23 = (261 - v21) & -(__int64)(v21 != 0);
  if ( !v21 )
    return v15;
  v9 = 261 - v23;
  v24 = &psz[v23];
  if ( 261 != v23 )
  {
    do
    {
      if ( !v8 )
        break;
      v25 = *v6;
      if ( !*v6 )
        break;
      ++v6;
      *v24++ = v25;
      --v8;
      --v9;
    }
    while ( v9 );
  }
LABEL_45:
  v15 = v9 == 0 ? 0x8007007A : 0;
  v28 = v24 - 1;
  if ( v9 )
    v28 = v24;
  *v28 = 0;
  if ( !v9 )
    return v15;
  TokenHandle = 0;
  v30 = RpcImpersonateClient(0);
  v32 = v30;
  if ( v30 )
  {
    EventManager::EvtReport(v31, &IMPERSONATION_FAILURE, L"GetLastRunInfo", v30, v41, v42);
    LOBYTE(pExceptionObject[1]) = 0;
    pExceptionObject[0] = &wmi::GenericException::`vftable';
    pExceptionObject[2] = &qword_1800A8718;
    *(_OWORD *)&pExceptionObject[3] = 0u;
    v47 = v32;
    v48 = -1;
    throw (wmi::GenericException *)pExceptionObject;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    RpcRevertToSelf();
    goto LABEL_57;
  }
  LastError = GetLastError();
  DynamicTaskInfo = LastError;
  if ( LastError > 0 )
    DynamicTaskInfo = (unsigned __int16)LastError | 0x80070000;
  RpcRevertToSelf();
  if ( DynamicTaskInfo < 0 )
  {
LABEL_75:
    wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&TokenHandle);
    return (unsigned int)DynamicTaskInfo;
  }
LABEL_57:
  JobMoniker::JobMoniker(&iid, psz, 0);
  *(_QWORD *)&v52.wYear = this + 2;
  AcquireSRWLockShared(this + 2);
  v36 = TaskAccessCheck(TokenHandle, psz, 1u);
  if ( v36 < 0 )
  {
    ReleaseSRWLockShared(this + 2);
    JobMoniker::~JobMoniker((JobMoniker *)&iid);
    DynamicTaskInfo = v36;
    goto LABEL_75;
  }
  v37 = JobStore::LoadBucketFromRegistry(JobStore::m_pCommonStore, psz, 2, &iid);
  v38 = this + 2;
  if ( v37 < 0 )
  {
    ReleaseSRWLockShared(v38);
    JobMoniker::~JobMoniker((JobMoniker *)&iid);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return (unsigned int)v37;
  }
  ReleaseSRWLockShared(v38);
  v45 = 0;
  v51 = 0;
  v50 = 0;
  v43 = 0;
  if ( (*(_DWORD *)(v55 + 16) & 0x2000000) == 0 )
  {
    pExceptionObject[0] = 3;
    memset(&pExceptionObject[1], 0, 28);
    DynamicTaskInfo = JobStore::GetDynamicTaskInfo(
                        JobStore::m_pCommonStore,
                        (struct JobMoniker *)&iid,
                        (struct DynamicTaskInfo *)pExceptionObject,
                        0x20019u,
                        0);
    if ( DynamicTaskInfo < 0 )
      goto LABEL_69;
    v40 = *(_QWORD *)((char *)&pExceptionObject[1] + 4);
    v45 = *(_QWORD *)((char *)&pExceptionObject[1] + 4);
    v43 = HIDWORD(pExceptionObject[2]);
    goto LABEL_73;
  }
  v39 = (*((__int64 (__fastcall **)(void ***, GUID *, __int64 *, __int64 *, __int64 *, unsigned int *))UbpmProxySingleton::s_singleton[0]
         + 12))(
          UbpmProxySingleton::s_singleton,
          &iid,
          &v45,
          &v51,
          &v50,
          &v43);
  DynamicTaskInfo = v39;
  if ( v39 != -2147023728 )
  {
    if ( v39 < 0 )
    {
LABEL_69:
      JobMoniker::~JobMoniker((JobMoniker *)&iid);
      goto LABEL_75;
    }
    v40 = v45;
LABEL_73:
    LOBYTE(v49) = 0;
    *((_QWORD *)&v49 + 1) = v40;
    LOBYTE(v52.wYear) = 0;
    *(_QWORD *)&v52.wHour = 0;
    if ( (unsigned __int8)TSTime::operator==(&v52, &v49) )
    {
      JobMoniker::~JobMoniker((JobMoniker *)&iid);
      DynamicTaskInfo = 267011;
      goto LABEL_75;
    }
    v49 = *(_OWORD *)TSTime::ToLocal(&v49, &v52);
    *a3 = *TSTime::ToSYSTEMTIME((TSTime *)&v49, &v52);
    *a4 = v43;
    goto LABEL_69;
  }
  wmi::AutoRef<JobBucket>::Release(&v55);
  _bstr_t::~_bstr_t((_bstr_t *)v54);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return 267011;
}

```

## disassembly

```asm
0x18001eae0  push    rbp
0x18001eae2  push    rbx
0x18001eae3  push    rdi
0x18001eae4  push    r12
0x18001eae6  push    r13
0x18001eae8  push    r14
0x18001eaea  push    r15
0x18001eaec  lea     rbp, [rsp-210h]
0x18001eaf4  sub     rsp, 310h
0x18001eafb  mov     rax, cs:__security_cookie
0x18001eb02  xor     rax, rsp
0x18001eb05  mov     [rbp+240h+var_40], rax
0x18001eb0c  mov     r15, r9
0x18001eb0f  mov     r14, r8
0x18001eb12  mov     rbx, rdx
0x18001eb15  mov     r13, rcx
0x18001eb18  xor     r12d, r12d
0x18001eb1b  test    rdx, rdx
0x18001eb1e  jz      loc_18001F02E
0x18001eb24  test    r8, r8
0x18001eb27  jz      loc_18001F02E
0x18001eb2d  test    r9, r9
0x18001eb30  jz      loc_18001F02E
0x18001eb36  xorps   xmm0, xmm0
0x18001eb39  movdqu  xmmword ptr [r8], xmm0
0x18001eb3e  mov     dword ptr [r9], 41303h
0x18001eb45  xor     edx, edx; Val
0x18001eb47  mov     r8d, 20Ah; Size
0x18001eb4d  lea     rcx, [rbp+240h+psz]; void *
0x18001eb51  call    memset_0
0x18001eb56  mov     r11d, 7FFFFFFEh
0x18001eb5c  mov     r8d, 105h
0x18001eb62  cmp     [rbx], r12w
0x18001eb66  jz      loc_18001ECAF
0x18001eb6c  cmp     word ptr [rbx], 5Ch ; '\'
0x18001eb70  jz      short loc_18001EBCA
0x18001eb72  mov     ecx, r11d
0x18001eb75  lea     rax, asc_1800A7EC0; "\\"
0x18001eb7c  mov     r9d, r8d
0x18001eb7f  lea     r10, [rbp+240h+psz]
0x18001eb83  test    rcx, rcx
0x18001eb86  jz      short loc_18001EBA5
0x18001eb88  movzx   edx, word ptr [rax]
0x18001eb8b  test    dx, dx
0x18001eb8e  jz      short loc_18001EBA5
0x18001eb90  add     rax, 2
0x18001eb94  mov     [r10], dx
0x18001eb98  add     r10, 2
0x18001eb9c  dec     rcx
0x18001eb9f  sub     r9, 1
0x18001eba3  jnz     short loc_18001EB83
0x18001eba5  mov     rax, r9
0x18001eba8  neg     rax
0x18001ebab  sbb     edx, edx
0x18001ebad  not     edx
0x18001ebaf  and     edx, 8007007Ah
0x18001ebb5  lea     rcx, [r10-2]
0x18001ebb9  test    r9, r9
0x18001ebbc  cmovnz  rcx, r10
0x18001ebc0  mov     [rcx], r12w
0x18001ebc4  jz      loc_18001ECFD
0x18001ebca  mov     edx, r12d
0x18001ebcd  mov     r9d, r12d
0x18001ebd0  cmp     r9d, r8d
0x18001ebd3  jge     short loc_18001EC2A
0x18001ebd5  movsxd  r10, r9d
0x18001ebd8  movzx   edi, word ptr [rbx+r10*2]
0x18001ebdd  test    di, di
0x18001ebe0  jz      short loc_18001EC34
0x18001ebe2  mov     ecx, edi
0x18001ebe4  sub     ecx, 20h ; ' '
0x18001ebe7  jz      short loc_18001EC17
0x18001ebe9  sub     ecx, 0Eh
0x18001ebec  jz      short loc_18001EC03
0x18001ebee  sub     ecx, 1
0x18001ebf1  jz      short loc_18001EC2A
0x18001ebf3  sub     ecx, 0Bh
0x18001ebf6  jz      short loc_18001EC2A
0x18001ebf8  cmp     ecx, 22h ; '"'
0x18001ebfb  jnz     short loc_18001EC22
0x18001ebfd  cmp     dx, 5Ch ; '\'
0x18001ec01  jmp     short loc_18001EC20
0x18001ec03  cmp     dx, 2Eh ; '.'
0x18001ec07  jz      short loc_18001EC2A
0x18001ec09  cmp     dx, 5Ch ; '\'
0x18001ec0d  jnz     short loc_18001EC22
0x18001ec0f  cmp     [rbx+r10*2+2], dx
0x18001ec15  jmp     short loc_18001EC20
0x18001ec17  cmp     dx, 5Ch ; '\'
0x18001ec1b  jz      short loc_18001EC2A
0x18001ec1d  test    dx, dx
0x18001ec20  jz      short loc_18001EC2A
0x18001ec22  movzx   edx, di
0x18001ec25  inc     r9d
0x18001ec28  jmp     short loc_18001EBD0
0x18001ec2a  mov     edx, 8007007Bh
0x18001ec2f  jmp     loc_18001ECFD
0x18001ec34  cmp     dx, 5Ch ; '\'
0x18001ec38  jnz     short loc_18001EC40
0x18001ec3a  cmp     r9d, 1
0x18001ec3e  jg      short loc_18001EC2A
0x18001ec40  mov     r9, r8
0x18001ec43  lea     rax, [rbp+240h+psz]
0x18001ec47  cmp     [rax], r12w
0x18001ec4b  jz      short loc_18001EC57
0x18001ec4d  add     rax, 2
0x18001ec51  sub     r9, 1
0x18001ec55  jnz     short loc_18001EC47
0x18001ec57  mov     rax, r9
0x18001ec5a  neg     rax
0x18001ec5d  sbb     edx, edx
0x18001ec5f  not     edx
0x18001ec61  and     edx, 80070057h
0x18001ec67  mov     rax, r9
0x18001ec6a  mov     rcx, r8
0x18001ec6d  sub     rcx, r9
0x18001ec70  neg     rax
0x18001ec73  sbb     r10, r10
0x18001ec76  and     r10, rcx
0x18001ec79  test    r9, r9
0x18001ec7c  jz      short loc_18001ECFD
0x18001ec7e  sub     r8, r10
0x18001ec81  lea     r9, [rbp+240h+psz]
0x18001ec85  lea     r9, [r9+r10*2]
0x18001ec89  jz      short loc_18001ECDC
0x18001ec8b  test    r11, r11
0x18001ec8e  jz      short loc_18001ECDC
0x18001ec90  movzx   eax, word ptr [rbx]
0x18001ec93  test    ax, ax
0x18001ec96  jz      short loc_18001ECDC
0x18001ec98  add     rbx, 2
0x18001ec9c  mov     [r9], ax
0x18001eca0  add     r9, 2
0x18001eca4  dec     r11
0x18001eca7  sub     r8, 1
0x18001ecab  jnz     short loc_18001EC8B
0x18001ecad  jmp     short loc_18001ECDC
0x18001ecaf  lea     rax, asc_1800A7EC0; "\\"
0x18001ecb6  lea     r9, [rbp+240h+psz]
0x18001ecba  test    r11, r11
0x18001ecbd  jz      short loc_18001ECDC
0x18001ecbf  movzx   ecx, word ptr [rax]
0x18001ecc2  test    cx, cx
0x18001ecc5  jz      short loc_18001ECDC
0x18001ecc7  add     rax, 2
0x18001eccb  mov     [r9], cx
0x18001eccf  add     r9, 2
0x18001ecd3  dec     r11
0x18001ecd6  sub     r8, 1
0x18001ecda  jnz     short loc_18001ECBA
0x18001ecdc  mov     rax, r8
0x18001ecdf  neg     rax
0x18001ece2  sbb     edx, edx
0x18001ece4  not     edx
0x18001ece6  and     edx, 8007007Ah
0x18001ecec  lea     rcx, [r9-2]
0x18001ecf0  test    r8, r8
0x18001ecf3  cmovnz  rcx, r9
0x18001ecf7  mov     [rcx], r12w
0x18001ecfb  jnz     short loc_18001ED04
0x18001ecfd  mov     eax, edx
0x18001ecff  jmp     loc_18001F033
0x18001ed04  mov     [rsp+340h+TokenHandle], r12
0x18001ed09  xor     ecx, ecx; BindingHandle
0x18001ed0b  call    cs:__imp_RpcImpersonateClient
0x18001ed12  nop     dword ptr [rax+rax+00h]
0x18001ed17  mov     ebx, eax
0x18001ed19  test    eax, eax
0x18001ed1b  jz      short loc_18001ED77
0x18001ed1d  mov     r9d, eax; unsigned int
0x18001ed20  lea     r8, aGetlastruninfo; "GetLastRunInfo"
0x18001ed27  lea     rdx, IMPERSONATION_FAILURE; struct _EVENT_DESCRIPTOR *
0x18001ed2e  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x18001ed33  mov     byte ptr [rsp+340h+var_2E0], r12b
0x18001ed38  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001ed3f  mov     [rsp+340h+pExceptionObject], rax
0x18001ed44  lea     rax, qword_1800A8718
0x18001ed4b  mov     [rsp+340h+var_2D8], rax
0x18001ed50  mov     [rsp+70h], r12
0x18001ed55  mov     [rsp+340h+var_2C8], r12
0x18001ed5a  mov     [rbp+240h+var_2C0], ebx
0x18001ed5d  mov     [rbp+240h+var_2BC], 0FFFFFFFFFFFFFFFFh
0x18001ed65  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001ed6c  lea     rcx, [rsp+340h+pExceptionObject]; pExceptionObject
0x18001ed71  call    _CxxThrowException_0
0x18001ed77  call    cs:__imp_GetCurrentThread
0x18001ed7e  nop     dword ptr [rax+rax+00h]
0x18001ed83  mov     rcx, rax; ThreadHandle
0x18001ed86  lea     r9, [rsp+340h+TokenHandle]; TokenHandle
0x18001ed8b  mov     edx, 8; DesiredAccess
0x18001ed90  lea     r8d, [rdx-7]; OpenAsSelf
0x18001ed94  call    cs:__imp_OpenThreadToken
0x18001ed9b  nop     dword ptr [rax+rax+00h]
0x18001eda0  test    eax, eax
0x18001eda2  jnz     short loc_18001EDD5
0x18001eda4  call    cs:__imp_GetLastError
0x18001edab  nop     dword ptr [rax+rax+00h]
0x18001edb0  mov     ebx, eax
0x18001edb2  test    eax, eax
0x18001edb4  jle     short loc_18001EDBF
0x18001edb6  movzx   ebx, ax
0x18001edb9  or      ebx, 80070000h
0x18001edbf  call    cs:__imp_RpcRevertToSelf
0x18001edc6  nop     dword ptr [rax+rax+00h]
0x18001edcb  test    ebx, ebx
0x18001edcd  js      loc_18001EFEA
0x18001edd3  jmp     short loc_18001EDE1
0x18001edd5  call    cs:__imp_RpcRevertToSelf
0x18001eddc  nop     dword ptr [rax+rax+00h]
0x18001ede1  xor     r8d, r8d; unsigned __int16 *
0x18001ede4  lea     rdx, [rbp+240h+psz]; psz
0x18001ede8  lea     rcx, [rbp+240h+iid]; lpiid
0x18001edec  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x18001edf1  nop
0x18001edf2  lea     rbx, [r13+10h]
0x18001edf6  mov     qword ptr [rbp+240h+var_290.wYear], rbx
0x18001edfa  mov     rcx, rbx; SRWLock
0x18001edfd  call    cs:__imp_AcquireSRWLockShared
0x18001ee04  nop     dword ptr [rax+rax+00h]
0x18001ee09  nop
0x18001ee0a  mov     r8d, 1; DesiredAccess
0x18001ee10  lea     rdx, [rbp+240h+psz]; psz
0x18001ee14  mov     rcx, [rsp+340h+TokenHandle]; ClientToken
0x18001ee19  call    ?TaskAccessCheck@@YAJPEAXPEBGK@Z; TaskAccessCheck(void *,ushort const *,ulong)
0x18001ee1e  mov     edi, eax
0x18001ee20  test    eax, eax
0x18001ee22  jns     short loc_18001EE44
0x18001ee24  mov     rcx, rbx; SRWLock
0x18001ee27  call    cs:__imp_ReleaseSRWLockShared
0x18001ee2e  nop     dword ptr [rax+rax+00h]
0x18001ee33  nop
0x18001ee34  lea     rcx, [rbp+240h+iid]; this
0x18001ee38  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x18001ee3d  mov     ebx, edi
0x18001ee3f  jmp     loc_18001EFEA
0x18001ee44  mov     [rsp+340h+var_318], r12
0x18001ee49  mov     [rsp+340h+var_320], r12
0x18001ee4e  lea     r9, [rbp+240h+iid]
0x18001ee52  mov     r8d, 2
0x18001ee58  lea     rdx, [rbp+240h+psz]
0x18001ee5c  mov     rcx, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; JobStore * JobStore::m_pCommonStore
0x18001ee63  call    ?LoadBucketFromRegistry@JobStore@@QEAAJPEBGW4StreamingFilters@Triggers@@AEAVJobMoniker@@PEAVTrigulator@3@PEAVActionCollection@Actions@@@Z; JobStore::LoadBucketFromRegistry(ushort const *,Triggers::StreamingFilters,JobMoniker &,Triggers::Trigulator *,Actions::ActionCollection *)
0x18001ee68  mov     edi, eax
0x18001ee6a  mov     rcx, rbx; SRWLock
0x18001ee6d  test    eax, eax
0x18001ee6f  jns     short loc_18001EEAA
0x18001ee71  call    cs:__imp_ReleaseSRWLockShared
0x18001ee78  nop     dword ptr [rax+rax+00h]
0x18001ee7d  nop
0x18001ee7e  lea     rcx, [rbp+240h+iid]; this
0x18001ee82  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x18001ee87  nop
0x18001ee88  mov     rcx, [rsp+340h+TokenHandle]; hObject
0x18001ee8d  lea     rax, [rcx-1]
0x18001ee91  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001ee95  ja      short loc_18001EEA3
0x18001ee97  call    cs:__imp_CloseHandle
0x18001ee9e  nop     dword ptr [rax+rax+00h]
0x18001eea3  mov     eax, edi
0x18001eea5  jmp     loc_18001F033
0x18001eeaa  call    cs:__imp_ReleaseSRWLockShared
0x18001eeb1  nop     dword ptr [rax+rax+00h]
0x18001eeb6  mov     [rsp+340h+var_2F0], r12
0x18001eebb  mov     [rbp+240h+var_298], r12
0x18001eebf  mov     [rbp+240h+var_2A0], r12
0x18001eec3  mov     [rsp+340h+var_300], r12d
0x18001eec8  mov     rax, [rbp+240h+var_260]
0x18001eecc  lea     rdx, [rbp+240h+iid]; struct JobMoniker *
0x18001eed0  test    dword ptr [rax+10h], 2000000h
0x18001eed7  jz      loc_18001EF6A
0x18001eedd  mov     rax, cs:?s_singleton@UbpmProxySingleton@@0V1@A; UbpmProxySingleton UbpmProxySingleton::s_singleton
0x18001eee4  lea     rcx, [rsp+340h+var_300]
0x18001eee9  mov     [rsp+340h+var_318], rcx
0x18001eeee  lea     rcx, [rbp+240h+var_2A0]
0x18001eef2  mov     [rsp+340h+var_320], rcx
0x18001eef7  lea     r9, [rbp+240h+var_298]
0x18001eefb  lea     r8, [rsp+340h+var_2F0]
0x18001ef00  lea     rcx, ?s_singleton@UbpmProxySingleton@@0V1@A; UbpmProxySingleton UbpmProxySingleton::s_singleton
0x18001ef07  mov     rax, [rax+60h]
0x18001ef0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef10  mov     ebx, eax
0x18001ef12  cmp     eax, 80070490h
0x18001ef17  jnz     short loc_18001EF51
0x18001ef19  lea     rcx, [rbp+240h+var_260]
0x18001ef1d  call    ?Release@?$AutoRef@VJobBucket@@@wmi@@QEAAXXZ; wmi::AutoRef<JobBucket>::Release(void)
0x18001ef22  lea     rcx, [rbp+240h+var_270]; this
0x18001ef26  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001ef2b  nop
0x18001ef2c  mov     rcx, [rsp+340h+TokenHandle]; hObject
0x18001ef31  lea     rdx, [rcx-1]
0x18001ef35  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001ef39  ja      short loc_18001EF47
0x18001ef3b  call    cs:__imp_CloseHandle
0x18001ef42  nop     dword ptr [rax+rax+00h]
0x18001ef47  mov     eax, 41303h
0x18001ef4c  jmp     loc_18001F033
0x18001ef51  test    eax, eax
0x18001ef53  jns     short loc_18001EF63
0x18001ef55  lea     rcx, [rbp+240h+iid]; this
0x18001ef59  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
  ... truncated ...
```
