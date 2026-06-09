# RpcServer::GetLastRunInfo(ushort const *,_SYSTEMTIME *,ulong *)

- ea: `0x180022b80`
- end: `0x1800230ad`
- name: `?GetLastRunInfo@RpcServer@@QEAAJPEBGPEAU_SYSTEMTIME@@PEAK@Z`
- size: `1325`
- prototype: `__int64 __fastcall(RpcServer *__hidden this, const unsigned __int16 *, struct _SYSTEMTIME *, unsigned int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180022b50`

## callees

- `0x18000dc30`
- `0x18000e4c0`
- `0x180016c00`
- `0x18001a430`
- `0x180022600`
- `0x180022b80`
- `0x1800230c0`
- `0x180023b60`
- `0x180031d90`
- `0x180039b6c`
- `0x180039d00`
- `0x18003c290`
- `0x1800438bc`
- `0x18005790c`
- `0x18007e68a`
- `0x18007e6d0`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022f01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022f99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022f01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022f99`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180022e79`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180022e79`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180022e9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180022ee1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180022f0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180022e9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180022ee1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180022f0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022e11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022e11`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180022e28`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180022e28`
- `RPCRT4!RpcImpersonateClient` at `0x180022dab`
- `RPCRT4!RpcImpersonateClient` at `0x180022dab`
- `RPCRT4!RpcRevertToSelf` at `0x180022e47`
- `RPCRT4!RpcRevertToSelf` at `0x180022e57`
- `RPCRT4!RpcRevertToSelf` at `0x180022e47`
- `RPCRT4!RpcRevertToSelf` at `0x180022e57`

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
    pExceptionObject[2] = &qword_1800A4718;
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
0x180022b80  push    rbp
0x180022b82  push    rbx
0x180022b83  push    rdi
0x180022b84  push    r12
0x180022b86  push    r13
0x180022b88  push    r14
0x180022b8a  push    r15
0x180022b8c  lea     rbp, [rsp-210h]
0x180022b94  sub     rsp, 310h
0x180022b9b  mov     rax, cs:__security_cookie
0x180022ba2  xor     rax, rsp
0x180022ba5  mov     [rbp+240h+var_40], rax
0x180022bac  mov     r15, r9
0x180022baf  mov     r14, r8
0x180022bb2  mov     rbx, rdx
0x180022bb5  mov     r13, rcx
0x180022bb8  xor     r12d, r12d
0x180022bbb  test    rdx, rdx
0x180022bbe  jz      loc_180023086
0x180022bc4  test    r8, r8
0x180022bc7  jz      loc_180023086
0x180022bcd  test    r9, r9
0x180022bd0  jz      loc_180023086
0x180022bd6  xorps   xmm0, xmm0
0x180022bd9  movdqu  xmmword ptr [r8], xmm0
0x180022bde  mov     dword ptr [r9], 41303h
0x180022be5  xor     edx, edx; Val
0x180022be7  mov     r8d, 20Ah; Size
0x180022bed  lea     rcx, [rbp+240h+psz]; void *
0x180022bf1  call    memset_0
0x180022bf6  mov     r11d, 7FFFFFFEh
0x180022bfc  mov     r8d, 105h
0x180022c02  cmp     [rbx], r12w
0x180022c06  jz      loc_180022D4F
0x180022c0c  cmp     word ptr [rbx], 5Ch ; '\'
0x180022c10  jz      short loc_180022C6A
0x180022c12  mov     ecx, r11d
0x180022c15  lea     rax, asc_1800A3DA8; "\\"
0x180022c1c  mov     r9d, r8d
0x180022c1f  lea     r10, [rbp+240h+psz]
0x180022c23  test    rcx, rcx
0x180022c26  jz      short loc_180022C45
0x180022c28  movzx   edx, word ptr [rax]
0x180022c2b  test    dx, dx
0x180022c2e  jz      short loc_180022C45
0x180022c30  add     rax, 2
0x180022c34  mov     [r10], dx
0x180022c38  add     r10, 2
0x180022c3c  dec     rcx
0x180022c3f  sub     r9, 1
0x180022c43  jnz     short loc_180022C23
0x180022c45  mov     rax, r9
0x180022c48  neg     rax
0x180022c4b  sbb     edx, edx
0x180022c4d  not     edx
0x180022c4f  and     edx, 8007007Ah
0x180022c55  lea     rcx, [r10-2]
0x180022c59  test    r9, r9
0x180022c5c  cmovnz  rcx, r10
0x180022c60  mov     [rcx], r12w
0x180022c64  jz      loc_180022D9D
0x180022c6a  mov     edx, r12d
0x180022c6d  mov     r9d, r12d
0x180022c70  cmp     r9d, r8d
0x180022c73  jge     short loc_180022CCA
0x180022c75  movsxd  r10, r9d
0x180022c78  movzx   edi, word ptr [rbx+r10*2]
0x180022c7d  test    di, di
0x180022c80  jz      short loc_180022CD4
0x180022c82  mov     ecx, edi
0x180022c84  sub     ecx, 20h ; ' '
0x180022c87  jz      short loc_180022CB7
0x180022c89  sub     ecx, 0Eh
0x180022c8c  jz      short loc_180022CA3
0x180022c8e  sub     ecx, 1
0x180022c91  jz      short loc_180022CCA
0x180022c93  sub     ecx, 0Bh
0x180022c96  jz      short loc_180022CCA
0x180022c98  cmp     ecx, 22h ; '"'
0x180022c9b  jnz     short loc_180022CC2
0x180022c9d  cmp     dx, 5Ch ; '\'
0x180022ca1  jmp     short loc_180022CC0
0x180022ca3  cmp     dx, 2Eh ; '.'
0x180022ca7  jz      short loc_180022CCA
0x180022ca9  cmp     dx, 5Ch ; '\'
0x180022cad  jnz     short loc_180022CC2
0x180022caf  cmp     [rbx+r10*2+2], dx
0x180022cb5  jmp     short loc_180022CC0
0x180022cb7  cmp     dx, 5Ch ; '\'
0x180022cbb  jz      short loc_180022CCA
0x180022cbd  test    dx, dx
0x180022cc0  jz      short loc_180022CCA
0x180022cc2  movzx   edx, di
0x180022cc5  inc     r9d
0x180022cc8  jmp     short loc_180022C70
0x180022cca  mov     edx, 8007007Bh
0x180022ccf  jmp     loc_180022D9D
0x180022cd4  cmp     dx, 5Ch ; '\'
0x180022cd8  jnz     short loc_180022CE0
0x180022cda  cmp     r9d, 1
0x180022cde  jg      short loc_180022CCA
0x180022ce0  mov     r9, r8
0x180022ce3  lea     rax, [rbp+240h+psz]
0x180022ce7  cmp     [rax], r12w
0x180022ceb  jz      short loc_180022CF7
0x180022ced  add     rax, 2
0x180022cf1  sub     r9, 1
0x180022cf5  jnz     short loc_180022CE7
0x180022cf7  mov     rax, r9
0x180022cfa  neg     rax
0x180022cfd  sbb     edx, edx
0x180022cff  not     edx
0x180022d01  and     edx, 80070057h
0x180022d07  mov     rax, r9
0x180022d0a  mov     rcx, r8
0x180022d0d  sub     rcx, r9
0x180022d10  neg     rax
0x180022d13  sbb     r10, r10
0x180022d16  and     r10, rcx
0x180022d19  test    r9, r9
0x180022d1c  jz      short loc_180022D9D
0x180022d1e  sub     r8, r10
0x180022d21  lea     r9, [rbp+240h+psz]
0x180022d25  lea     r9, [r9+r10*2]
0x180022d29  jz      short loc_180022D7C
0x180022d2b  test    r11, r11
0x180022d2e  jz      short loc_180022D7C
0x180022d30  movzx   eax, word ptr [rbx]
0x180022d33  test    ax, ax
0x180022d36  jz      short loc_180022D7C
0x180022d38  add     rbx, 2
0x180022d3c  mov     [r9], ax
0x180022d40  add     r9, 2
0x180022d44  dec     r11
0x180022d47  sub     r8, 1
0x180022d4b  jnz     short loc_180022D2B
0x180022d4d  jmp     short loc_180022D7C
0x180022d4f  lea     rax, asc_1800A3DA8; "\\"
0x180022d56  lea     r9, [rbp+240h+psz]
0x180022d5a  test    r11, r11
0x180022d5d  jz      short loc_180022D7C
0x180022d5f  movzx   ecx, word ptr [rax]
0x180022d62  test    cx, cx
0x180022d65  jz      short loc_180022D7C
0x180022d67  add     rax, 2
0x180022d6b  mov     [r9], cx
0x180022d6f  add     r9, 2
0x180022d73  dec     r11
0x180022d76  sub     r8, 1
0x180022d7a  jnz     short loc_180022D5A
0x180022d7c  mov     rax, r8
0x180022d7f  neg     rax
0x180022d82  sbb     edx, edx
0x180022d84  not     edx
0x180022d86  and     edx, 8007007Ah
0x180022d8c  lea     rcx, [r9-2]
0x180022d90  test    r8, r8
0x180022d93  cmovnz  rcx, r9
0x180022d97  mov     [rcx], r12w
0x180022d9b  jnz     short loc_180022DA4
0x180022d9d  mov     eax, edx
0x180022d9f  jmp     loc_18002308B
0x180022da4  mov     [rsp+340h+TokenHandle], r12
0x180022da9  xor     ecx, ecx; BindingHandle
0x180022dab  call    cs:__imp_RpcImpersonateClient
0x180022db1  mov     ebx, eax
0x180022db3  test    eax, eax
0x180022db5  jz      short loc_180022E11
0x180022db7  mov     r9d, eax; unsigned int
0x180022dba  lea     r8, aGetlastruninfo; "GetLastRunInfo"
0x180022dc1  lea     rdx, IMPERSONATION_FAILURE; struct _EVENT_DESCRIPTOR *
0x180022dc8  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x180022dcd  mov     byte ptr [rsp+340h+var_2E0], r12b
0x180022dd2  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180022dd9  mov     [rsp+340h+pExceptionObject], rax
0x180022dde  lea     rax, qword_1800A4718
0x180022de5  mov     [rsp+340h+var_2D8], rax
0x180022dea  mov     [rsp+70h], r12
0x180022def  mov     [rsp+340h+var_2C8], r12
0x180022df4  mov     [rbp+240h+var_2C0], ebx
0x180022df7  mov     [rbp+240h+var_2BC], 0FFFFFFFFFFFFFFFFh
0x180022dff  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180022e06  lea     rcx, [rsp+340h+pExceptionObject]; pExceptionObject
0x180022e0b  call    _CxxThrowException_0
0x180022e11  call    cs:__imp_GetCurrentThread
0x180022e17  mov     rcx, rax; ThreadHandle
0x180022e1a  lea     r9, [rsp+340h+TokenHandle]; TokenHandle
0x180022e1f  mov     edx, 8; DesiredAccess
0x180022e24  lea     r8d, [rdx-7]; OpenAsSelf
0x180022e28  call    cs:__imp_OpenThreadToken
0x180022e2e  test    eax, eax
0x180022e30  jnz     short loc_180022E57
0x180022e32  call    cs:__imp_GetLastError
0x180022e38  mov     ebx, eax
0x180022e3a  test    eax, eax
0x180022e3c  jle     short loc_180022E47
0x180022e3e  movzx   ebx, ax
0x180022e41  or      ebx, 80070000h
0x180022e47  call    cs:__imp_RpcRevertToSelf
0x180022e4d  test    ebx, ebx
0x180022e4f  js      loc_180023042
0x180022e55  jmp     short loc_180022E5D
0x180022e57  call    cs:__imp_RpcRevertToSelf
0x180022e5d  xor     r8d, r8d; unsigned __int16 *
0x180022e60  lea     rdx, [rbp+240h+psz]; psz
0x180022e64  lea     rcx, [rbp+240h+iid]; lpiid
0x180022e68  call    ??0JobMoniker@@QEAA@PEBG0@Z; JobMoniker::JobMoniker(ushort const *,ushort const *)
0x180022e6d  nop
0x180022e6e  lea     rbx, [r13+10h]
0x180022e72  mov     qword ptr [rbp+240h+var_290.wYear], rbx
0x180022e76  mov     rcx, rbx; SRWLock
0x180022e79  call    cs:__imp_AcquireSRWLockShared
0x180022e7f  nop
0x180022e80  mov     r8d, 1; DesiredAccess
0x180022e86  lea     rdx, [rbp+240h+psz]; psz
0x180022e8a  mov     rcx, [rsp+340h+TokenHandle]; ClientToken
0x180022e8f  call    ?TaskAccessCheck@@YAJPEAXPEBGK@Z; TaskAccessCheck(void *,ushort const *,ulong)
0x180022e94  mov     edi, eax
0x180022e96  test    eax, eax
0x180022e98  jns     short loc_180022EB4
0x180022e9a  mov     rcx, rbx; SRWLock
0x180022e9d  call    cs:__imp_ReleaseSRWLockShared
0x180022ea3  nop
0x180022ea4  lea     rcx, [rbp+240h+iid]; this
0x180022ea8  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x180022ead  mov     ebx, edi
0x180022eaf  jmp     loc_180023042
0x180022eb4  mov     [rsp+340h+var_318], r12
0x180022eb9  mov     [rsp+340h+var_320], r12
0x180022ebe  lea     r9, [rbp+240h+iid]
0x180022ec2  mov     r8d, 2
0x180022ec8  lea     rdx, [rbp+240h+psz]
0x180022ecc  mov     rcx, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; JobStore * JobStore::m_pCommonStore
0x180022ed3  call    ?LoadBucketFromRegistry@JobStore@@QEAAJPEBGW4StreamingFilters@Triggers@@AEAVJobMoniker@@PEAVTrigulator@3@PEAVActionCollection@Actions@@@Z; JobStore::LoadBucketFromRegistry(ushort const *,Triggers::StreamingFilters,JobMoniker &,Triggers::Trigulator *,Actions::ActionCollection *)
0x180022ed8  mov     edi, eax
0x180022eda  mov     rcx, rbx; SRWLock
0x180022edd  test    eax, eax
0x180022edf  jns     short loc_180022F0E
0x180022ee1  call    cs:__imp_ReleaseSRWLockShared
0x180022ee7  nop
0x180022ee8  lea     rcx, [rbp+240h+iid]; this
0x180022eec  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x180022ef1  nop
0x180022ef2  mov     rcx, [rsp+340h+TokenHandle]; hObject
0x180022ef7  lea     rax, [rcx-1]
0x180022efb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180022eff  ja      short loc_180022F07
0x180022f01  call    cs:__imp_CloseHandle
0x180022f07  mov     eax, edi
0x180022f09  jmp     loc_18002308B
0x180022f0e  call    cs:__imp_ReleaseSRWLockShared
0x180022f14  mov     [rsp+340h+var_2F0], r12
0x180022f19  mov     [rbp+240h+var_298], r12
0x180022f1d  mov     [rbp+240h+var_2A0], r12
0x180022f21  mov     [rsp+340h+var_300], r12d
0x180022f26  mov     rax, [rbp+240h+var_260]
0x180022f2a  lea     rdx, [rbp+240h+iid]; struct JobMoniker *
0x180022f2e  test    dword ptr [rax+10h], 2000000h
0x180022f35  jz      loc_180022FC2
0x180022f3b  mov     rax, cs:?s_singleton@UbpmProxySingleton@@0V1@A; UbpmProxySingleton UbpmProxySingleton::s_singleton
0x180022f42  lea     rcx, [rsp+340h+var_300]
0x180022f47  mov     [rsp+340h+var_318], rcx
0x180022f4c  lea     rcx, [rbp+240h+var_2A0]
0x180022f50  mov     [rsp+340h+var_320], rcx
0x180022f55  lea     r9, [rbp+240h+var_298]
0x180022f59  lea     r8, [rsp+340h+var_2F0]
0x180022f5e  lea     rcx, ?s_singleton@UbpmProxySingleton@@0V1@A; UbpmProxySingleton UbpmProxySingleton::s_singleton
0x180022f65  mov     rax, [rax+60h]
0x180022f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f6e  mov     ebx, eax
0x180022f70  cmp     eax, 80070490h
0x180022f75  jnz     short loc_180022FA9
0x180022f77  lea     rcx, [rbp+240h+var_260]
0x180022f7b  call    ?Release@?$AutoRef@VJobBucket@@@wmi@@QEAAXXZ; wmi::AutoRef<JobBucket>::Release(void)
0x180022f80  lea     rcx, [rbp+240h+var_270]; this
0x180022f84  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180022f89  nop
0x180022f8a  mov     rcx, [rsp+340h+TokenHandle]; hObject
0x180022f8f  lea     rdx, [rcx-1]
0x180022f93  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180022f97  ja      short loc_180022F9F
0x180022f99  call    cs:__imp_CloseHandle
0x180022f9f  mov     eax, 41303h
0x180022fa4  jmp     loc_18002308B
0x180022fa9  test    eax, eax
0x180022fab  jns     short loc_180022FBB
0x180022fad  lea     rcx, [rbp+240h+iid]; this
0x180022fb1  call    ??1JobMoniker@@QEAA@XZ; JobMoniker::~JobMoniker(void)
0x180022fb6  jmp     loc_180023042
0x180022fbb  mov     rax, [rsp+340h+var_2F0]
0x180022fc0  jmp     short loc_180023013
0x180022fc2  mov     [rsp+340h+pExceptionObject], 3
0x180022fcb  mov     [rsp+340h+var_2D8+4], r12
0x180022fd0  mov     [rsp+340h+var_2E0], r12
0x180022fd5  mov     [rsp+74h], r12
0x180022fda  mov     dword ptr [rsp+340h+var_2D8], r12d
0x180022fdf  mov     [rsp+340h+var_320], r12; HKEY *
0x180022fe4  mov     r9d, 20019h; unsigned int
0x180022fea  lea     r8, [rsp+340h+pExceptionObject]; struct DynamicTaskInfo *
0x180022fef  mov     rcx, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; this
  ... truncated ...
```
