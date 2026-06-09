# CINetEdge::ReadDataHere(uchar *,ulong,ulong *)

- ea: `0x1800113b0`
- end: `0x180011b71`
- name: `?ReadDataHere@CINetEdge@@IEAAJPEAEKPEAK@Z`
- size: `1985`
- prototype: `__int64 __fastcall(CINetEdge *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1800110d0`

## callees

- `0x180008610`
- `0x18000b2e0`
- `0x18000b490`
- `0x18000e7f0`
- `0x180010e30`
- `0x1800113b0`
- `0x180017340`
- `0x180018190`
- `0x18005d1e0`
- `0x1800786e8`
- `0x1800e0d80`
- `0x1800ed0a0`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800118d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180011992`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800118d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180011992`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011461`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800114a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001157b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800115ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800116a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011461`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800114a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001157b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800115ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800116a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001144c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011493`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011566`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800115d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011691`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001144c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011493`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011566`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800115d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011691`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800118b7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800118b7`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180011870`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180011870`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011650`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011975`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011984`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011975`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011984`
- `WININET!InternetReadFile` at `0x180011640`
- `WININET!InternetReadFile` at `0x180011640`
- `WININET!InternetQueryDataAvailable` at `0x180011513`
- `WININET!InternetQueryDataAvailable` at `0x180011513`

## pseudocode

```c
__int64 __fastcall CINetEdge::ReadDataHere(CINetEdge *this, unsigned __int8 *a2, unsigned int a3, unsigned int *a4)
{
  unsigned int v6; // esi
  bool v7; // dl
  int v8; // edi
  unsigned int v9; // r12d
  int v10; // edi
  unsigned int v11; // eax
  int v12; // edx
  int v13; // edi
  DWORD v14; // r14d
  void *v15; // rcx
  unsigned __int8 *v16; // rdx
  int v17; // edx
  int v18; // r14d
  struct IInternetBindInfo *RefCountedBindInfo; // rax
  struct IInternetBindInfo *v20; // rdi
  RTL_SRWLOCK *v21; // r14
  RTL_SRWLOCK *v22; // r14
  volatile signed __int32 *Ptr; // rdi
  _QWORD *v24; // r14
  unsigned __int8 *v25; // r12
  _QWORD *v26; // r14
  int v27; // edx
  int v28; // ecx
  __int64 v29; // r9
  __int64 v30; // rdx
  struct ITransactionInternal *v31; // rcx
  unsigned int v33; // [rsp+30h] [rbp-D0h] BYREF
  struct ITransactionInternal *v34; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int8 *v35; // [rsp+40h] [rbp-C0h] BYREF
  CINetEdge *v36; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v37; // [rsp+50h] [rbp-B0h] BYREF
  CINetEdge *v38; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v39; // [rsp+60h] [rbp-A0h] BYREF
  CINetEdge *v40; // [rsp+68h] [rbp-98h] BYREF
  char v41; // [rsp+70h] [rbp-90h]
  struct _EVENT_DATA_DESCRIPTOR v42[2]; // [rsp+80h] [rbp-80h] BYREF
  CINetEdge **v43; // [rsp+A0h] [rbp-60h]
  __int64 v44; // [rsp+A8h] [rbp-58h]
  unsigned __int8 **v45; // [rsp+B0h] [rbp-50h]
  __int64 v46; // [rsp+B8h] [rbp-48h]
  struct ITransactionInternal **v47; // [rsp+C0h] [rbp-40h]
  __int64 v48; // [rsp+C8h] [rbp-38h]
  unsigned int *v49; // [rsp+D0h] [rbp-30h]
  __int64 v50; // [rsp+D8h] [rbp-28h]
  CINetEdge **v51; // [rsp+E0h] [rbp-20h]
  __int64 v52; // [rsp+E8h] [rbp-18h]

  v33 = a3;
  v35 = a2;
  v6 = -2147467259;
  *a4 = 0;
  v40 = this;
  v41 = 0;
  _InterlockedIncrement((volatile signed __int32 *)this + 300);
  if ( !CINetEdge::CAutoStateLock::AcquireLock((CINetEdge::CAutoStateLock *)&v40) )
    goto LABEL_81;
  if ( *((_DWORD *)this + 31) == -2146828287 )
  {
    v6 = 1;
LABEL_54:
    v21 = (RTL_SRWLOCK *)*((_QWORD *)this + 133);
    if ( v21 )
    {
      v22 = v21 + 1;
      AcquireSRWLockShared(v22);
      Ptr = (volatile signed __int32 *)v22[1].Ptr;
      if ( Ptr )
      {
        _InterlockedIncrement(Ptr + 4);
        ReleaseSRWLockShared(v22);
        v24 = *(_QWORD **)Ptr;
        if ( *((_DWORD *)Ptr + 2) )
        {
          v25 = v35;
          do
          {
            (*(void (__fastcall **)(_QWORD, _QWORD, unsigned __int8 *, _QWORD))(*(_QWORD *)*v24 + 48LL))(
              *v24,
              *((unsigned int *)this + 264),
              v25,
              *a4);
            ++v24;
          }
          while ( v24 != (_QWORD *)(*(_QWORD *)Ptr + 8LL * *((unsigned int *)Ptr + 2)) );
        }
        if ( _InterlockedExchangeAdd(Ptr + 4, 0xFFFFFFFF) == 1 )
        {
          v26 = *(_QWORD **)Ptr;
          if ( *((_DWORD *)Ptr + 2) )
          {
            do
            {
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 16LL))(*v26);
              ++v26;
            }
            while ( v26 != (_QWORD *)(*(_QWORD *)Ptr + 8LL * *((unsigned int *)Ptr + 2)) );
          }
          CoTaskMemFree(*(LPVOID *)Ptr);
          CoTaskMemFree((LPVOID)Ptr);
        }
      }
      else
      {
        ReleaseSRWLockShared(v22);
      }
    }
    goto LABEL_64;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
  v8 = *((_DWORD *)this + 123);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
  if ( v8 )
  {
    v6 = -2147483638;
    goto LABEL_51;
  }
  v6 = 0;
  v9 = 0;
  v34 = (struct ITransactionInternal *)*((_QWORD *)this + 52);
  *((_DWORD *)this + 31) = 0;
  while ( 1 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
    v10 = *((_DWORD *)this + 107);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
    if ( v10 )
      goto LABEL_18;
    (*(void (__fastcall **)(CINetEdge *))(*(_QWORD *)this + 400LL))(this);
    v11 = CINetEdge::CheckAndSetINetEdgeState((__int64)this, 34);
    if ( v11 != 1 )
      goto LABEL_36;
    if ( (unsigned int)CINetEdge::SetStatePending(this, 2147483658LL, 6) )
      break;
    if ( InternetQueryDataAvailable(*((HINTERNET *)this + 47), (LPDWORD)this + 106, 0, 0) )
    {
      v13 = *((_DWORD *)this + 106);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
      *((_DWORD *)this + 107) += v13;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
      CINetEdge::SetStatePending(this, 0, 6);
      if ( !*((_DWORD *)this + 106) )
      {
        *((_DWORD *)this + 31) = -2146828287;
        v6 = -2146828287;
      }
      v12 = 35;
    }
    else
    {
      if ( GetLastError() == 997 )
        break;
      CINetEdge::SetStatePending(this, 0, 6);
      v12 = 36;
      *((_DWORD *)this + 31) = -2146697209;
      v6 = -2146697209;
    }
    v11 = CINetEdge::CheckAndSetINetEdgeState((__int64)this, v12);
    if ( v11 != 1 )
    {
LABEL_36:
      v6 = CINetEdge::CheckTransitionStatusAndDispatchAbort(this, v11, v6);
      goto LABEL_81;
    }
    if ( v6 )
      goto LABEL_31;
LABEL_18:
    if ( !*((_DWORD *)this + 31) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
      v14 = *((_DWORD *)this + 107);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
      if ( v33 - v9 <= v14 )
        v14 = v33 - v9;
      v11 = CINetEdge::CheckAndSetINetEdgeState((__int64)this, 27);
      if ( v11 != 1 )
        goto LABEL_36;
      v15 = (void *)*((_QWORD *)this + 47);
      v16 = &v35[v9];
      *((_DWORD *)this + 110) = 0;
      if ( InternetReadFile(v15, v16, v14, (LPDWORD)this + 110) )
      {
        v18 = *((_DWORD *)this + 110);
        if ( v18 )
        {
          v6 = 0;
        }
        else
        {
          *((_DWORD *)this + 31) = -2146828287;
          v6 = -2146828287;
        }
        v9 += v18;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
        *((_DWORD *)this + 107) -= v18;
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
        v17 = 28;
        *((_QWORD *)this + 52) += *((unsigned int *)this + 110);
      }
      else
      {
        GetLastError();
        v17 = 29;
        *((_DWORD *)this + 31) = -2146697208;
        v6 = -2146697208;
      }
      v11 = CINetEdge::CheckAndSetINetEdgeState((__int64)this, v17);
      if ( v11 != 1 )
        goto LABEL_36;
      if ( v6 )
        goto LABEL_31;
    }
    if ( v9 >= v33 )
      goto LABEL_31;
  }
  v6 = -2147483638;
LABEL_31:
  if ( *((_QWORD *)this + 52) < 0xFFEFFFFF )
  {
    *a4 = v9;
  }
  else
  {
    *a4 = 0;
    RefCountedBindInfo = CINetEdge::GetRefCountedBindInfo(this, v7);
    v20 = RefCountedBindInfo;
    if ( RefCountedBindInfo )
    {
      if ( (unsigned int)CINetEdge::IsDownloading64BitEnabled(this, RefCountedBindInfo) )
      {
        if ( CINetEdge::IsFetchModeClient(this) )
          *a4 = v9;
      }
      else
      {
        *((_DWORD *)this + 31) = -2146697208;
        v6 = -2146697208;
      }
    }
    else
    {
      v6 = -2147467260;
    }
    if ( (unsigned __int64)v34 < 0xFFEFFFFF
      && (unsigned int)dword_180166000 > 5
      && (qword_180166010 & 0x20) != 0
      && (qword_180166018 & 0x20) == qword_180166018 )
    {
      v37 = *((_QWORD *)this + 52);
      v33 = v6;
      v49 = &v33;
      v47 = &v34;
      v36 = this;
      v45 = (unsigned __int8 **)&v37;
      v43 = &v36;
      v50 = 4;
      v48 = 8;
      v46 = 8;
      v44 = 8;
      tlgWriteTransfer_BrowserWriteTransfer(
        (__int64)&dword_180166000,
        (unsigned __int8 *)&word_18015215E,
        0,
        0,
        6u,
        v42);
    }
    if ( v20 )
      ((void (__fastcall *)(struct IInternetBindInfo *))v20->lpVtbl->Release)(v20);
  }
  if ( v6 == -2146828287 )
  {
    v6 = *a4 == 0;
    goto LABEL_54;
  }
  if ( (v6 & 0x80000000) == 0 )
    goto LABEL_54;
LABEL_51:
  InitOnceExecuteOnce(&stru_18016BB00, InitOnceDeviceFamily, 0, 0);
  if ( byte_18016AF34 && v6 == -2147483638 && *a4 )
    goto LABEL_54;
LABEL_64:
  v33 = 0;
  v34 = 0;
  if ( !(unsigned int)CINetEdge::GetTransactionInternal(this, v7, &v34) )
    (*(void (__fastcall **)(struct ITransactionInternal *, unsigned int *))(*(_QWORD *)v34 + 96LL))(v34, &v33);
  if ( (unsigned int)dword_180166000 > 5 )
  {
    v28 = qword_180166018;
    if ( (qword_180166010 & 0x20) != 0 && (qword_180166018 & 0x20) == qword_180166018 )
    {
      LODWORD(v36) = v33;
      v39 = *((_QWORD *)this + 52);
      LODWORD(v35) = *a4;
      v51 = &v36;
      v49 = (unsigned int *)&v37;
      v47 = (struct ITransactionInternal **)&v39;
      v45 = &v35;
      v43 = &v38;
      LODWORD(v37) = v6;
      v38 = this;
      v52 = 4;
      v50 = 4;
      v48 = 8;
      v46 = 4;
      v44 = 8;
      tlgWriteTransfer_BrowserWriteTransfer((__int64)&dword_180166000, (unsigned __int8 *)&unk_180152100, 0, 0, 7u, v42);
    }
  }
  if ( (Microsoft_Windows_URLMonEnableBits & 1) != 0 )
    McTemplateU0qzq_EventWriteTransfer(v28, v27, v33, *((_QWORD *)this + 23), *a4);
  if ( v6 != -2147483638 && *((_DWORD *)this + 31) )
  {
    v29 = *((_QWORD *)this + 51);
    if ( !v29 )
      v29 = *((_QWORD *)this + 50);
    v30 = v6;
    if ( v6 == 1 )
      v30 = 0;
    (*(void (__fastcall **)(CINetEdge *, __int64, _QWORD, __int64, _QWORD))(*(_QWORD *)this + 288LL))(
      this,
      v30,
      *((_QWORD *)this + 52),
      v29,
      0);
  }
  v31 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(struct ITransactionInternal *))(*(_QWORD *)v31 + 16LL))(v31);
  }
LABEL_81:
  CINetEdge::CAutoStateLock::~CAutoStateLock((CINetEdge::CAutoStateLock *)&v40);
  return v6;
}

```

## disassembly

```asm
0x1800113b0  push    rbp
0x1800113b2  push    rbx
0x1800113b3  push    rsi
0x1800113b4  push    r13
0x1800113b6  lea     rbp, [rsp-28h]
0x1800113bb  sub     rsp, 128h
0x1800113c2  mov     rax, cs:__security_cookie
0x1800113c9  xor     rax, rsp
0x1800113cc  mov     [rbp+40h+var_50], rax
0x1800113d0  mov     r13, r9
0x1800113d3  mov     [rsp+140h+var_110], r8d
0x1800113d8  mov     [rsp+140h+var_100], rdx
0x1800113dd  mov     rbx, rcx
0x1800113e0  mov     esi, 80004005h
0x1800113e5  mov     dword ptr [r9], 0
0x1800113ec  mov     [rsp+140h+var_D8], rcx
0x1800113f1  mov     [rsp+140h+var_D0], 0
0x1800113f6  lock inc dword ptr [rcx+4B0h]
0x1800113fd  lea     rcx, [rsp+140h+var_D8]; this
0x180011402  call    ?AcquireLock@CAutoStateLock@CINetEdge@@QEAA_NXZ; CINetEdge::CAutoStateLock::AcquireLock(void)
0x180011407  test    al, al
0x180011409  jz      loc_180011B4B
0x18001140f  cmp     dword ptr [rbx+7Ch], 800A0001h
0x180011416  mov     [rsp+140h+var_20], rdi
0x18001141e  mov     [rsp+140h+var_28], r12
0x180011426  mov     [rsp+140h+var_30], r14
0x18001142e  mov     [rsp+140h+var_38], r15
0x180011436  jnz     short loc_180011442
0x180011438  mov     esi, 1
0x18001143d  jmp     loc_1800118A0
0x180011442  lea     r15, [rbx+3D8h]
0x180011449  mov     rcx, r15; lpCriticalSection
0x18001144c  call    cs:__imp_EnterCriticalSection
0x180011453  nop     dword ptr [rax+rax+00h]
0x180011458  mov     edi, [rbx+1ECh]
0x18001145e  mov     rcx, r15; lpCriticalSection
0x180011461  call    cs:__imp_LeaveCriticalSection
0x180011468  nop     dword ptr [rax+rax+00h]
0x18001146d  test    edi, edi
0x18001146f  jz      short loc_18001147B
0x180011471  mov     esi, 8000000Ah
0x180011476  jmp     loc_18001185C
0x18001147b  mov     r14, [rbx+1A0h]
0x180011482  xor     esi, esi
0x180011484  xor     r12d, r12d
0x180011487  mov     [rsp+140h+var_108], r14
0x18001148c  mov     [rbx+7Ch], esi
0x18001148f  nop
0x180011490  mov     rcx, r15; lpCriticalSection
0x180011493  call    cs:__imp_EnterCriticalSection
0x18001149a  nop     dword ptr [rax+rax+00h]
0x18001149f  mov     edi, [rbx+1ACh]
0x1800114a5  mov     rcx, r15; lpCriticalSection
0x1800114a8  call    cs:__imp_LeaveCriticalSection
0x1800114af  nop     dword ptr [rax+rax+00h]
0x1800114b4  test    edi, edi
0x1800114b6  jnz     loc_1800115CA
0x1800114bc  mov     rax, [rbx]
0x1800114bf  mov     rcx, rbx
0x1800114c2  mov     rax, [rax+190h]
0x1800114c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114ce  mov     edx, 22h ; '"'
0x1800114d3  mov     rcx, rbx
0x1800114d6  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x1800114db  cmp     eax, 1
0x1800114de  jnz     loc_18001172E
0x1800114e4  mov     edx, 8000000Ah
0x1800114e9  mov     r8d, 6
0x1800114ef  mov     rcx, rbx
0x1800114f2  call    ?SetStatePending@CINetEdge@@IEAAJJW4ePendingStateReason@1@H@Z; CINetEdge::SetStatePending(long,CINetEdge::ePendingStateReason,int)
0x1800114f7  test    eax, eax
0x1800114f9  jnz     loc_180011727
0x1800114ff  mov     rcx, [rbx+178h]; hFile
0x180011506  lea     rdx, [rbx+1A8h]; lpdwNumberOfBytesAvailable
0x18001150d  xor     r9d, r9d; dwContext
0x180011510  xor     r8d, r8d; dwFlags
0x180011513  call    cs:__imp_InternetQueryDataAvailable
0x18001151a  nop     dword ptr [rax+rax+00h]
0x18001151f  test    eax, eax
0x180011521  jnz     short loc_18001155D
0x180011523  call    cs:__imp_GetLastError
0x18001152a  nop     dword ptr [rax+rax+00h]
0x18001152f  cmp     eax, 3E5h
0x180011534  jz      loc_180011727
0x18001153a  xor     edx, edx
0x18001153c  mov     r8d, 6
0x180011542  mov     rcx, rbx
0x180011545  call    ?SetStatePending@CINetEdge@@IEAAJJW4ePendingStateReason@1@H@Z; CINetEdge::SetStatePending(long,CINetEdge::ePendingStateReason,int)
0x18001154a  mov     edx, 24h ; '$'
0x18001154f  mov     dword ptr [rbx+7Ch], 800C0007h
0x180011556  mov     esi, 800C0007h
0x18001155b  jmp     short loc_1800115B1
0x18001155d  mov     edi, [rbx+1A8h]
0x180011563  mov     rcx, r15; lpCriticalSection
0x180011566  call    cs:__imp_EnterCriticalSection
0x18001156d  nop     dword ptr [rax+rax+00h]
0x180011572  add     [rbx+1ACh], edi
0x180011578  mov     rcx, r15; lpCriticalSection
0x18001157b  call    cs:__imp_LeaveCriticalSection
0x180011582  nop     dword ptr [rax+rax+00h]
0x180011587  xor     edx, edx
0x180011589  mov     r8d, 6
0x18001158f  mov     rcx, rbx
0x180011592  call    ?SetStatePending@CINetEdge@@IEAAJJW4ePendingStateReason@1@H@Z; CINetEdge::SetStatePending(long,CINetEdge::ePendingStateReason,int)
0x180011597  cmp     dword ptr [rbx+1A8h], 0
0x18001159e  jnz     short loc_1800115AC
0x1800115a0  mov     dword ptr [rbx+7Ch], 800A0001h
0x1800115a7  mov     esi, 800A0001h
0x1800115ac  mov     edx, 23h ; '#'
0x1800115b1  mov     rcx, rbx
0x1800115b4  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x1800115b9  cmp     eax, 1
0x1800115bc  jnz     loc_18001172E
0x1800115c2  test    esi, esi
0x1800115c4  jnz     loc_1800116E1
0x1800115ca  cmp     dword ptr [rbx+7Ch], 0
0x1800115ce  jnz     loc_1800116D6
0x1800115d4  mov     rcx, r15; lpCriticalSection
0x1800115d7  call    cs:__imp_EnterCriticalSection
0x1800115de  nop     dword ptr [rax+rax+00h]
0x1800115e3  mov     r14d, [rbx+1ACh]
0x1800115ea  mov     rcx, r15; lpCriticalSection
0x1800115ed  call    cs:__imp_LeaveCriticalSection
0x1800115f4  nop     dword ptr [rax+rax+00h]
0x1800115f9  mov     eax, [rsp+140h+var_110]
0x1800115fd  mov     edx, 1Bh
0x180011602  sub     eax, r12d
0x180011605  mov     rcx, rbx
0x180011608  cmp     eax, r14d
0x18001160b  cmovbe  r14d, eax
0x18001160f  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x180011614  cmp     eax, 1
0x180011617  jnz     loc_18001172E
0x18001161d  mov     rcx, [rbx+178h]; hFile
0x180011624  lea     r9, [rbx+1B8h]; lpdwNumberOfBytesRead
0x18001162b  mov     edx, r12d
0x18001162e  mov     r8d, r14d; dwNumberOfBytesToRead
0x180011631  add     rdx, [rsp+140h+var_100]; lpBuffer
0x180011636  mov     dword ptr [rbx+1B8h], 0
0x180011640  call    cs:__imp_InternetReadFile
0x180011647  nop     dword ptr [rax+rax+00h]
0x18001164c  test    eax, eax
0x18001164e  jnz     short loc_18001166F
0x180011650  call    cs:__imp_GetLastError
0x180011657  nop     dword ptr [rax+rax+00h]
0x18001165c  mov     edx, 1Dh
0x180011661  mov     dword ptr [rbx+7Ch], 800C0008h
0x180011668  mov     esi, 800C0008h
0x18001166d  jmp     short loc_1800116C5
0x18001166f  mov     r14d, [rbx+1B8h]
0x180011676  test    r14d, r14d
0x180011679  jnz     short loc_180011689
0x18001167b  mov     dword ptr [rbx+7Ch], 800A0001h
0x180011682  mov     esi, 800A0001h
0x180011687  jmp     short loc_18001168B
0x180011689  xor     esi, esi
0x18001168b  mov     rcx, r15; lpCriticalSection
0x18001168e  add     r12d, r14d
0x180011691  call    cs:__imp_EnterCriticalSection
0x180011698  nop     dword ptr [rax+rax+00h]
0x18001169d  sub     [rbx+1ACh], r14d
0x1800116a4  mov     rcx, r15; lpCriticalSection
0x1800116a7  call    cs:__imp_LeaveCriticalSection
0x1800116ae  nop     dword ptr [rax+rax+00h]
0x1800116b3  mov     eax, [rbx+1B8h]
0x1800116b9  mov     edx, 1Ch
0x1800116be  add     [rbx+1A0h], rax
0x1800116c5  mov     rcx, rbx
0x1800116c8  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x1800116cd  cmp     eax, 1
0x1800116d0  jnz     short loc_18001172E
0x1800116d2  test    esi, esi
0x1800116d4  jnz     short loc_1800116E1
0x1800116d6  cmp     r12d, [rsp+140h+var_110]
0x1800116db  jb      loc_180011490
0x1800116e1  mov     eax, 0FFEFFFFFh
0x1800116e6  xor     r15d, r15d
0x1800116e9  cmp     [rbx+1A0h], rax
0x1800116f0  jb      loc_18001183E
0x1800116f6  mov     rcx, rbx; this
0x1800116f9  mov     [r13+0], r15d
0x1800116fd  call    ?GetRefCountedBindInfo@CINetEdge@@IEAAPEAUIInternetBindInfo@@_N@Z; CINetEdge::GetRefCountedBindInfo(bool)
0x180011702  mov     rdi, rax
0x180011705  test    rax, rax
0x180011708  jz      short loc_180011754
0x18001170a  mov     rdx, rax; struct IInternetBindInfo *
0x18001170d  mov     rcx, rbx; this
0x180011710  call    ?IsDownloading64BitEnabled@CINetEdge@@IEAAHPEAUIInternetBindInfo@@@Z; CINetEdge::IsDownloading64BitEnabled(IInternetBindInfo *)
0x180011715  test    eax, eax
0x180011717  jnz     short loc_180011742
0x180011719  mov     dword ptr [rbx+7Ch], 800C0008h
0x180011720  mov     esi, 800C0008h
0x180011725  jmp     short loc_180011759
0x180011727  mov     esi, 8000000Ah
0x18001172c  jmp     short loc_1800116E1
0x18001172e  mov     r8d, esi
0x180011731  mov     edx, eax
0x180011733  mov     rcx, rbx
0x180011736  call    ?CheckTransitionStatusAndDispatchAbort@CINetEdge@@IEAAJW4INetEdgeStateTransition@@J@Z; CINetEdge::CheckTransitionStatusAndDispatchAbort(INetEdgeStateTransition,long)
0x18001173b  mov     esi, eax
0x18001173d  jmp     loc_180011B2B
0x180011742  mov     rcx, rbx; this
0x180011745  call    ?IsFetchModeClient@CINetEdge@@IEAA_NXZ; CINetEdge::IsFetchModeClient(void)
0x18001174a  test    al, al
0x18001174c  jz      short loc_180011759
0x18001174e  mov     [r13+0], r12d
0x180011752  jmp     short loc_180011759
0x180011754  mov     esi, 80004004h
0x180011759  mov     r14, [rsp+140h+var_108]
0x18001175e  mov     eax, 0FFEFFFFFh
0x180011763  cmp     r14, rax
0x180011766  jnb     loc_180011828
0x18001176c  mov     eax, cs:dword_180166000
0x180011772  cmp     eax, 5
0x180011775  jbe     loc_180011828
0x18001177b  mov     rcx, cs:qword_180166018
0x180011782  mov     rax, cs:qword_180166010
0x180011789  test    al, 20h
0x18001178b  jz      loc_180011828
0x180011791  mov     rax, rcx
0x180011794  and     eax, 20h
0x180011797  cmp     rax, rcx
0x18001179a  jnz     loc_180011828
0x1800117a0  mov     rax, [rbx+1A0h]
0x1800117a7  lea     rdx, word_18015215E
0x1800117ae  mov     [rsp+140h+var_F0], rax
0x1800117b3  lea     rcx, dword_180166000
0x1800117ba  lea     rax, [rsp+140h+var_110]
0x1800117bf  mov     [rsp+140h+var_110], esi
0x1800117c3  mov     [rbp+40h+var_70], rax
0x1800117c7  xor     r9d, r9d
0x1800117ca  lea     rax, [rsp+140h+var_108]
0x1800117cf  mov     [rsp+140h+var_108], r14
0x1800117d4  mov     [rbp+40h+var_80], rax
0x1800117d8  xor     r8d, r8d
0x1800117db  lea     rax, [rsp+140h+var_F0]
0x1800117e0  mov     [rsp+140h+var_F8], rbx
0x1800117e5  mov     [rbp+40h+var_90], rax
0x1800117e9  lea     rax, [rsp+140h+var_F8]
0x1800117ee  mov     [rbp+40h+var_A0], rax
0x1800117f2  lea     rax, [rbp+40h+var_C0]
0x1800117f6  mov     [rsp+140h+var_118], rax
0x1800117fb  mov     dword ptr [rsp+140h+var_120], 6
0x180011803  mov     [rbp+40h+var_68], 4
0x18001180b  mov     [rbp+40h+var_78], 8
0x180011813  mov     [rbp+40h+var_88], 8
0x18001181b  mov     [rbp+40h+var_98], 8
0x180011823  call    _tlgWriteTransfer_BrowserWriteTransfer
0x180011828  test    rdi, rdi
0x18001182b  jz      short loc_180011842
0x18001182d  mov     rax, [rdi]
0x180011830  mov     rcx, rdi
0x180011833  mov     rax, [rax+10h]
0x180011837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001183c  jmp     short loc_180011842
0x18001183e  mov     [r13+0], r12d
0x180011842  cmp     esi, 800A0001h
0x180011848  jnz     short loc_180011858
0x18001184a  cmp     dword ptr [r13+0], 0
0x18001184f  mov     esi, r15d
0x180011852  setz    sil
0x180011856  jmp     short loc_1800118A0
0x180011858  test    esi, esi
0x18001185a  jns     short loc_1800118A0
0x18001185c  xor     r9d, r9d; Context
0x18001185f  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180011866  xor     r8d, r8d; Parameter
0x180011869  lea     rcx, stru_18016BB00; InitOnce
0x180011870  call    cs:__imp_InitOnceExecuteOnce
0x180011877  nop     dword ptr [rax+rax+00h]
0x18001187c  cmp     cs:byte_18016AF34, 0
0x180011883  jz      loc_18001199E
0x180011889  cmp     esi, 8000000Ah
0x18001188f  jnz     loc_18001199E
0x180011895  cmp     dword ptr [r13+0], 0
0x18001189a  jbe     loc_18001199E
0x1800118a0  mov     r14, [rbx+428h]
0x1800118a7  test    r14, r14
0x1800118aa  jz      loc_18001199E
0x1800118b0  add     r14, 8
0x1800118b4  mov     rcx, r14; SRWLock
0x1800118b7  call    cs:__imp_AcquireSRWLockShared
0x1800118be  nop     dword ptr [rax+rax+00h]
0x1800118c3  mov     rdi, [r14+8]
0x1800118c7  mov     rcx, r14; SRWLock
0x1800118ca  test    rdi, rdi
0x1800118cd  jz      loc_180011992
0x1800118d3  lock inc dword ptr [rdi+10h]
0x1800118d7  call    cs:__imp_ReleaseSRWLockShared
0x1800118de  nop     dword ptr [rax+rax+00h]
0x1800118e3  cmp     dword ptr [rdi+8], 0
0x1800118e7  mov     r14, [rdi]
0x1800118ea  jz      short loc_18001192F
0x1800118ec  mov     r12, [rsp+140h+var_100]
0x1800118f1  nop     dword ptr [rax+00h]
0x1800118f5  nop     word ptr [rax+rax+00000000h]
0x180011900  mov     rcx, [r14]
0x180011903  mov     r8, r12
0x180011906  mov     r9d, [r13+0]
0x18001190a  mov     edx, [rbx+420h]
  ... truncated ...
```
