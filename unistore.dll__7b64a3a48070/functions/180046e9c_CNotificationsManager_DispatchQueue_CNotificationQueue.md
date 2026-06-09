# CNotificationsManager::DispatchQueue(CNotificationQueue *)

- ea: `0x180046e9c`
- end: `0x180047573`
- name: `?DispatchQueue@CNotificationsManager@@QEAAXPEAVCNotificationQueue@@@Z`
- size: `1751`
- prototype: `void __fastcall(CNotificationsManager *__hidden this, struct CNotificationQueue *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180045ef0`
- `0x180046b90`

## callees

- `0x180004440`
- `0x180004464`
- `0x1800068f0`
- `0x1800253f0`
- `0x180029494`
- `0x18003c174`
- `0x180046e9c`
- `0x180047990`
- `0x180047c40`
- `0x180078a40`
- `0x1800c50aa`
- `0x1800c50f0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046fc5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046fdf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047031`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004706a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800471f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047225`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004725a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800473d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004744d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046fc5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046fdf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047031`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004706a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800471f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047225`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004725a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800473d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004744d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046ff2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047040`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047079`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800471c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047234`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047269`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800472b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800473a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004741c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046ff2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047040`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047079`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800471c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047234`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047269`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800472b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800473a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004741c`
- `ntdll!RtlGetThreadWorkOnBehalfTicket` at `0x180046f6e`
- `ntdll!RtlGetThreadWorkOnBehalfTicket` at `0x180046f6e`

## string_xrefs

- `0x1800474dc`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\notificationsmanager.cpp`
- `0x1800474fd`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\notificationsmanager.cpp`

## pseudocode

```c
void __fastcall CNotificationsManager::DispatchQueue(
        CNotificationsManager *this,
        struct CNotificationQueue *a2,
        __int64 a3)
{
  struct CNotificationQueue *v4; // r13
  char *v5; // rdi
  __int64 v6; // rbx
  __int64 i; // rbx
  unsigned int v8; // r10d
  int v9; // edi
  _BYTE *v10; // r12
  _QWORD *v11; // r14
  unsigned __int64 v12; // r15
  int ThreadWorkOnBehalfTicket; // eax
  __int64 v14; // rax
  unsigned __int64 j; // rdx
  __int64 v16; // r8
  int *v17; // rsi
  int v18; // ebx
  CNotificationsManager *v19; // r13
  __int64 *v20; // r14
  __int64 *v21; // rbx
  int v22; // edi
  _QWORD *v23; // rsi
  int v24; // edi
  __int64 v25; // rdi
  __int64 v26; // r12
  unsigned __int64 v27; // rax
  __int64 v28; // r13
  __int64 v29; // r14
  _DWORD *v30; // rax
  __int64 v31; // r9
  __int64 v32; // rdx
  unsigned __int64 v33; // rdx
  int v34; // r10d
  __int64 v35; // r11
  __int64 k; // r8
  _DWORD *v37; // rcx
  int *v38; // rdx
  bool v39; // zf
  CNotificationsManager *v40; // rdx
  unsigned int v41; // r13d
  struct _RTL_CRITICAL_SECTION *v42; // r14
  int v43; // edi
  int v44; // ebx
  __int64 v45; // rdi
  __int64 v46; // rbx
  __int64 m; // rbx
  __int64 n; // r12
  int v49; // r8d
  int v50; // eax
  int v51; // eax
  int v52; // eax
  unsigned int v53; // [rsp+30h] [rbp-D0h]
  int v55; // [rsp+40h] [rbp-C0h]
  char *v56; // [rsp+48h] [rbp-B8h]
  void *Block; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE *v58; // [rsp+58h] [rbp-A8h]
  __int64 v59; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v60; // [rsp+70h] [rbp-90h]
  __int64 *v61; // [rsp+78h] [rbp-88h]
  __int64 *v62; // [rsp+80h] [rbp-80h]
  struct CNotificationQueue *v63; // [rsp+88h] [rbp-78h]
  _QWORD v64[200]; // [rsp+90h] [rbp-70h] BYREF

  v63 = a2;
  v4 = a2;
  utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>(
    &Block,
    a2,
    a3);
  v5 = (char *)Block;
  v6 = v58 - (_BYTE *)Block;
  v58 = Block;
  for ( i = v6 >> 3; i; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v5[8 * i]) )
    --i;
  utl::vector<ATL::CComPtr<CNotificationEvent>,utl::allocator<ATL::CComPtr<CNotificationEvent>>>::swap(v4, &Block);
  v9 = *((_DWORD *)v4 + 6);
  v10 = v58;
  v11 = Block;
  v55 = v9;
  v12 = (v58 - (_BYTE *)Block) >> 3;
  *((_DWORD *)v4 + 6) = 0;
  if ( !v12 && !v9 )
  {
    utl::vector<ATL::CComPtr<IUSObject>,utl::allocator<ATL::CComPtr<IUSObject>>>::_Uninit(&Block);
    return;
  }
  if ( g_perfStatEnabled )
  {
    _InterlockedAdd(&dword_18010DA38, v8);
    _InterlockedAdd(&dword_18010DA30, v12);
    do
      v51 = dword_18010DA34;
    while ( dword_18010DA34 < (unsigned int)v12
         && v51 != _InterlockedCompareExchange(&dword_18010DA34, v12, dword_18010DA34) );
  }
  v59 = 0;
  ThreadWorkOnBehalfTicket = RtlGetThreadWorkOnBehalfTicket(&v59, v8);
  if ( ThreadWorkOnBehalfTicket < 0 )
    Log_UnistoreHREvent_0(
      ThreadWorkOnBehalfTicket | 0x10000000u,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\notificationsmanager.cpp",
      670);
  v14 = v59;
  for ( j = 0; j < v12; ++j )
  {
    v16 = *(_QWORD *)(v11[j] + 24LL);
    if ( *(_DWORD *)v16 != 0x40000000 )
      *(_QWORD *)(v16 + 32) = v14;
  }
  if ( this )
  {
    v56 = (char *)this + 8;
    if ( this == (CNotificationsManager *)-8LL )
      v56 = 0;
    else
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
  else
  {
    v56 = 0;
  }
  v17 = (int *)*((_QWORD *)this + 9);
  v61 = (__int64 *)v17;
  EnterCriticalSection(&g_csShutdownLock);
  v18 = g_serviceShuttingDown;
  LeaveCriticalSection(&g_csShutdownLock);
  if ( !v18 )
  {
    v19 = this;
    while ( v17 != (int *)((char *)v19 + 72) )
    {
      if ( v17[7] > 0 )
      {
        CNotificationQueue::PushEvents((CNotificationQueue *)(v17 + 8));
      }
      else
      {
        v20 = (__int64 *)(v17 + 16);
        v21 = (__int64 *)*((_QWORD *)v17 + 8);
        v62 = (__int64 *)(v17 + 16);
        EnterCriticalSection(&g_csShutdownLock);
        v22 = g_serviceShuttingDown;
        LeaveCriticalSection(&g_csShutdownLock);
        if ( !v22 )
        {
          v23 = Block;
          while ( v21 != v20 )
          {
            if ( v21[12] )
            {
              EnterCriticalSection(&g_csShutdownLock);
              v24 = g_serviceShuttingDown;
              LeaveCriticalSection(&g_csShutdownLock);
              if ( v24 )
              {
                Log_UnistoreHREvent_0(
                  2147943515LL,
                  0,
                  "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\notificationsmanager.cpp",
                  521);
              }
              else
              {
                v25 = v21[12];
                if ( v25 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v21[12]);
                if ( !v55 )
                {
                  memset_0(v64, 0, sizeof(v64));
                  if ( !v12 )
                    goto LABEL_53;
                  v26 = 0;
                  v27 = 0;
                  v53 = 0;
                  v60 = 0;
                  while ( 1 )
                  {
                    v28 = *(_QWORD *)(v23[v27] + 24LL);
                    if ( (*(_DWORD *)v28 & *((_DWORD *)v21 + 9)) == 0 )
                    {
                      v41 = v53;
LABEL_73:
                      v40 = this;
                      goto LABEL_48;
                    }
                    if ( *(_DWORD *)v28 != 0x40000000 )
                    {
                      v29 = v21[3];
                      if ( (USObjectTypeToEventMask(*(unsigned int *)(v28 + 12)) & v29) == 0 )
                        goto LABEL_46;
                    }
                    v30 = (_DWORD *)v21[6];
                    if ( v30 != (_DWORD *)v21[7] && *(_DWORD *)v28 != 0x40000000 )
                      break;
LABEL_32:
                    v31 = v21[9];
                    v32 = v21[10];
                    if ( v31 != v32 && (*(_DWORD *)v28 == 16 || *(_DWORD *)v28 == 4) )
                    {
                      v33 = (v32 - v31) >> 2;
                      if ( !v33 )
                        goto LABEL_46;
                      v34 = 0;
                      v35 = 0;
                      while ( !v34 )
                      {
                        for ( k = 0; (unsigned int)k < *(_DWORD *)(v28 + 40); k = (unsigned int)(k + 1) )
                        {
                          if ( *(_DWORD *)(v31 + 4 * v35) == *(_DWORD *)(*(_QWORD *)(v28 + 48) + 4 * k) )
                          {
                            v34 = 1;
                            break;
                          }
                        }
                        v35 = (unsigned int)(v35 + 1);
                        if ( (unsigned int)v35 >= v33 )
                        {
                          if ( !v34 )
                            goto LABEL_46;
                          break;
                        }
                      }
                      v38 = (int *)(v28 + 72);
                      v37 = v21 + 4;
                    }
                    else
                    {
                      v37 = v21 + 4;
                      v38 = (int *)(v28 + 72);
                      if ( *(_DWORD *)(v28 + 72) == *((_DWORD *)v21 + 8) )
                        v39 = (v21[5] & 2) == 0;
                      else
                        v39 = (v21[5] & 4) == 0;
                      if ( v39 )
                        goto LABEL_46;
                    }
                    v49 = *v38;
                    v40 = this;
                    v50 = *((_DWORD *)this + 24);
                    if ( v49 != v50 || *v37 == v50 )
                    {
                      v53 |= v49 == *v37 ? 2u : 4u;
                      v64[v26] = v28;
                      v26 = (unsigned int)(v26 + 1);
                      if ( (_DWORD)v26 == 200 )
                      {
                        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
                        (*(void (__fastcall **)(__int64, _QWORD, __int64, _QWORD *))(*(_QWORD *)v25 + 24LL))(
                          v25,
                          v53,
                          200,
                          v64);
                        PerfIncrementCount(5, 200);
                        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
                        v41 = 0;
                        v53 = 0;
                        v26 = 0;
                        goto LABEL_73;
                      }
                    }
LABEL_47:
                    v41 = v53;
LABEL_48:
                    v27 = v60 + 1;
                    v60 = v27;
                    if ( v27 >= v12 )
                    {
                      if ( (_DWORD)v26 )
                      {
                        v42 = (struct _RTL_CRITICAL_SECTION *)((char *)v40 + 16);
                        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v40 + 16));
                        (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD *))(*(_QWORD *)v25 + 24LL))(
                          v25,
                          v41,
                          (unsigned int)v26,
                          v64);
                        if ( g_perfStatEnabled )
                        {
                          _InterlockedIncrement(&dword_18010DA44);
                          _InterlockedAdd(&dword_18010DA3C, v26);
                          do
                            v52 = dword_18010DA40;
                          while ( dword_18010DA40 < (unsigned int)v26
                               && v52 != _InterlockedCompareExchange(&dword_18010DA40, v26, dword_18010DA40) );
                        }
                        EnterCriticalSection(v42);
                      }
                      v19 = this;
                      goto LABEL_53;
                    }
                  }
                  while ( v30 != (_DWORD *)v21[7] )
                  {
                    if ( *v30 == *(_DWORD *)(v28 + 16) )
                      goto LABEL_32;
                    ++v30;
                  }
LABEL_46:
                  v40 = this;
                  goto LABEL_47;
                }
                LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v19 + 16));
                if ( g_perfStatEnabled )
                {
                  _InterlockedAdd(&dword_18010DA44, 1u);
                  _InterlockedIncrement(&dword_18010DA3C);
                  while ( !dword_18010DA40 && _InterlockedCompareExchange(&dword_18010DA40, 1, 0) )
                    ;
                }
                (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v25 + 24LL))(v25, 8, 0);
                EnterCriticalSection((LPCRITICAL_SECTION)((char *)v19 + 16));
LABEL_53:
                if ( v25 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
              }
            }
            v21 = (__int64 *)*v21;
            EnterCriticalSection(&g_csShutdownLock);
            v43 = g_serviceShuttingDown;
            LeaveCriticalSection(&g_csShutdownLock);
            v20 = v62;
            if ( v43 )
              break;
          }
          v17 = (int *)v61;
        }
      }
      v17 = *(int **)v17;
      v61 = (__int64 *)v17;
      EnterCriticalSection(&g_csShutdownLock);
      v44 = g_serviceShuttingDown;
      LeaveCriticalSection(&g_csShutdownLock);
      if ( v44 )
        break;
    }
    v10 = v58;
    v11 = Block;
    v4 = v63;
  }
  v45 = *(_QWORD *)v4;
  v46 = *((_QWORD *)v4 + 1) - *(_QWORD *)v4;
  *((_QWORD *)v4 + 1) = *(_QWORD *)v4;
  for ( m = v46 >> 3; m; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>((void *)(v45 + 8 * m)) )
    --m;
  *((_DWORD *)v4 + 6) = 0;
  if ( v56 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v56 + 8));
  if ( v11 != (_QWORD *)-1LL )
  {
    for ( n = (v10 - (_BYTE *)v11) >> 3;
          n;
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v11[n]) )
    {
      --n;
    }
    operator delete(v11);
  }
}

```

## disassembly

```asm
0x180046e9c  mov     [rsp-8+arg_10], rbx
0x180046ea1  push    rbp
0x180046ea2  push    rsi
0x180046ea3  push    rdi
0x180046ea4  push    r12
0x180046ea6  push    r13
0x180046ea8  push    r14
0x180046eaa  push    r15
0x180046eac  lea     rbp, [rsp-5E0h]
0x180046eb4  sub     rsp, 6E0h
0x180046ebb  mov     rax, cs:__security_cookie
0x180046ec2  xor     rax, rsp
0x180046ec5  mov     [rbp+610h+var_40], rax
0x180046ecc  mov     rsi, rcx
0x180046ecf  mov     [rsp+710h+var_6D8], rcx
0x180046ed4  lea     rcx, [rsp+710h+Block]
0x180046ed9  mov     [rbp+610h+var_688], rdx
0x180046edd  mov     r13, rdx
0x180046ee0  call    ??0?$vector@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>(void)
0x180046ee5  mov     rdi, [rsp+710h+Block]
0x180046eea  mov     r10d, 1
0x180046ef0  mov     rbx, [rsp+710h+var_6B8]
0x180046ef5  sub     rbx, rdi
0x180046ef8  mov     [rsp+710h+var_6B8], rdi
0x180046efd  sar     rbx, 3
0x180046f01  test    rbx, rbx
0x180046f04  jz      short loc_180046F1B
0x180046f06  dec     rbx
0x180046f09  lea     rcx, [rdi+rbx*8]; void *
0x180046f0d  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180046f12  test    rbx, rbx
0x180046f15  jnz     short loc_180046F06
0x180046f17  lea     r10d, [rbx+1]
0x180046f1b  lea     rdx, [rsp+710h+Block]
0x180046f20  mov     rcx, r13
0x180046f23  call    ?swap@?$vector@V?$CComPtr@VCNotificationEvent@@@ATL@@V?$allocator@V?$CComPtr@VCNotificationEvent@@@ATL@@@utl@@@utl@@QEAAXAEAV12@@Z; utl::vector<ATL::CComPtr<CNotificationEvent>,utl::allocator<ATL::CComPtr<CNotificationEvent>>>::swap(utl::vector<ATL::CComPtr<CNotificationEvent>,utl::allocator<ATL::CComPtr<CNotificationEvent>>> &)
0x180046f28  mov     edi, [r13+18h]
0x180046f2c  xor     ebx, ebx
0x180046f2e  mov     r12, [rsp+710h+var_6B8]
0x180046f33  mov     r14, [rsp+710h+Block]
0x180046f38  mov     r15, r12
0x180046f3b  sub     r15, r14
0x180046f3e  mov     [rsp+710h+var_6D0], edi
0x180046f42  sar     r15, 3
0x180046f46  mov     [r13+18h], ebx
0x180046f4a  test    r15, r15
0x180046f4d  jz      loc_18004716A
0x180046f53  mov     eax, cs:?g_perfStatEnabled@@3KC; ulong volatile g_perfStatEnabled
0x180046f59  test    eax, eax
0x180046f5b  jnz     loc_1800474A9
0x180046f61  mov     edx, r10d
0x180046f64  mov     [rsp+710h+var_6A8], rbx
0x180046f69  lea     rcx, [rsp+710h+var_6A8]
0x180046f6e  call    cs:__imp_RtlGetThreadWorkOnBehalfTicket
0x180046f74  test    eax, eax
0x180046f76  js      loc_1800474D8
0x180046f7c  mov     rax, [rsp+710h+var_6A8]
0x180046f81  mov     rdx, rbx
0x180046f84  test    r15, r15
0x180046f87  jz      short loc_180046FA6
0x180046f89  mov     rcx, [r14+rdx*8]
0x180046f8d  mov     r8, [rcx+18h]
0x180046f91  cmp     dword ptr [r8], 40000000h
0x180046f98  jz      short loc_180046F9E
0x180046f9a  mov     [r8+20h], rax
0x180046f9e  inc     rdx
0x180046fa1  cmp     rdx, r15
0x180046fa4  jb      short loc_180046F89
0x180046fa6  test    rsi, rsi
0x180046fa9  jz      loc_18004746F
0x180046faf  lea     rdi, [rsi+8]
0x180046fb3  mov     [rsp+710h+var_6C8], rdi
0x180046fb8  test    rdi, rdi
0x180046fbb  jz      loc_18004748F
0x180046fc1  lea     rcx, [rdi+8]; lpCriticalSection
0x180046fc5  call    cs:__imp_EnterCriticalSection
0x180046fcb  mov     edi, [rsp+710h+var_6D0]
0x180046fcf  mov     rsi, [rsi+48h]
0x180046fd3  lea     rcx, ?g_csShutdownLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x180046fda  mov     [rsp+710h+var_698], rsi
0x180046fdf  call    cs:__imp_EnterCriticalSection
0x180046fe5  mov     ebx, cs:?g_serviceShuttingDown@@3HA; int g_serviceShuttingDown
0x180046feb  lea     rcx, ?g_csShutdownLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x180046ff2  call    cs:__imp_LeaveCriticalSection
0x180046ff8  test    ebx, ebx
0x180046ffa  jnz     loc_180047285
0x180047000  mov     r13, [rsp+710h+var_6D8]
0x180047005  lea     r12, ?g_csShutdownLock@@3Vrecursive_mutex@utl@@A; utl::recursive_mutex g_csShutdownLock
0x18004700c  lea     rax, [r13+48h]
0x180047010  cmp     rsi, rax
0x180047013  jz      loc_180047277
0x180047019  cmp     dword ptr [rsi+1Ch], 0
0x18004701d  jg      loc_180047479
0x180047023  lea     r14, [rsi+40h]
0x180047027  mov     rcx, r12; lpCriticalSection
0x18004702a  mov     rbx, [r14]
0x18004702d  mov     [rbp+610h+var_690], r14
0x180047031  call    cs:__imp_EnterCriticalSection
0x180047037  mov     edi, cs:?g_serviceShuttingDown@@3HA; int g_serviceShuttingDown
0x18004703d  mov     rcx, r12; lpCriticalSection
0x180047040  call    cs:__imp_LeaveCriticalSection
0x180047046  test    edi, edi
0x180047048  jnz     loc_18004724B
0x18004704e  mov     rsi, [rsp+710h+Block]
0x180047053  cmp     rbx, r14
0x180047056  jz      loc_180047246
0x18004705c  cmp     qword ptr [rbx+60h], 0
0x180047061  jz      loc_18004721F
0x180047067  mov     rcx, r12; lpCriticalSection
0x18004706a  call    cs:__imp_EnterCriticalSection
0x180047070  mov     edi, cs:?g_serviceShuttingDown@@3HA; int g_serviceShuttingDown
0x180047076  mov     rcx, r12; lpCriticalSection
0x180047079  call    cs:__imp_LeaveCriticalSection
0x18004707f  test    edi, edi
0x180047081  jnz     loc_1800474F7
0x180047087  mov     rdi, [rbx+60h]
0x18004708b  test    rdi, rdi
0x18004708e  jz      short loc_18004709F
0x180047090  mov     rax, [rdi]
0x180047093  mov     rcx, rdi
0x180047096  mov     rax, [rax+8]
0x18004709a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004709f  cmp     [rsp+710h+var_6D0], 0
0x1800470a4  jnz     loc_180047418
0x1800470aa  xor     edx, edx; Val
0x1800470ac  lea     rcx, [rbp+610h+var_680]; void *
0x1800470b0  mov     r8d, 640h; Size
0x1800470b6  call    memset_0
0x1800470bb  test    r15, r15
0x1800470be  jz      loc_18004720B
0x1800470c4  xor     r12d, r12d
0x1800470c7  xor     eax, eax
0x1800470c9  mov     [rsp+710h+var_6E0], r12d
0x1800470ce  mov     [rsp+710h+var_6A0], rax
0x1800470d3  mov     rax, [rsi+rax*8]
0x1800470d7  mov     r13, [rax+18h]
0x1800470db  mov     eax, [r13+0]
0x1800470df  test    [rbx+24h], eax
0x1800470e2  jz      loc_180047332
0x1800470e8  cmp     eax, 40000000h
0x1800470ed  jz      short loc_180047105
0x1800470ef  mov     ecx, [r13+0Ch]
0x1800470f3  mov     r14, [rbx+18h]
0x1800470f7  call    USObjectTypeToEventMask
0x1800470fc  test    r14, rax
0x1800470ff  jz      loc_18004719D
0x180047105  mov     rax, [rbx+30h]
0x180047109  cmp     rax, [rbx+38h]
0x18004710d  jnz     loc_180047308
0x180047113  mov     r9, [rbx+48h]
0x180047117  mov     rdx, [rbx+50h]
0x18004711b  cmp     r9, rdx
0x18004711e  jz      short loc_180047181
0x180047120  cmp     dword ptr [r13+0], 10h
0x180047125  jnz     loc_180047499
0x18004712b  sub     rdx, r9
0x18004712e  sar     rdx, 2
0x180047132  test    rdx, rdx
0x180047135  jz      short loc_18004719D
0x180047137  xor     r10d, r10d
0x18004713a  xor     r11d, r11d
0x18004713d  test    r10d, r10d
0x180047140  jnz     loc_18004735F
0x180047146  xor     r8d, r8d
0x180047149  cmp     r8d, [r13+28h]
0x18004714d  jnb     loc_180047347
0x180047153  mov     rax, [r13+30h]
0x180047157  mov     ecx, [rax+r8*4]
0x18004715b  cmp     [r9+r11*4], ecx
0x18004715f  jz      loc_180047341
0x180047165  inc     r8d
0x180047168  jmp     short loc_180047149
0x18004716a  test    edi, edi
0x18004716c  jnz     loc_180046F53
0x180047172  lea     rcx, [rsp+710h+Block]
0x180047177  call    ?_Uninit@?$vector@V?$CComPtr@UIUSObject@@@ATL@@V?$allocator@V?$CComPtr@UIUSObject@@@ATL@@@utl@@@utl@@AEAAXXZ; utl::vector<ATL::CComPtr<IUSObject>,utl::allocator<ATL::CComPtr<IUSObject>>>::_Uninit(void)
0x18004717c  jmp     loc_1800472DE
0x180047181  lea     rcx, [rbx+20h]
0x180047185  mov     eax, [rcx]
0x180047187  lea     rdx, [r13+48h]
0x18004718b  cmp     [rdx], eax
0x18004718d  jz      loc_1800473ED
0x180047193  test    byte ptr [rbx+28h], 4
0x180047197  jnz     loc_180047367
0x18004719d  mov     rdx, [rsp+710h+var_6D8]
0x1800471a2  mov     r13d, [rsp+710h+var_6E0]
0x1800471a7  mov     rax, [rsp+710h+var_6A0]
0x1800471ac  inc     rax
0x1800471af  mov     [rsp+710h+var_6A0], rax
0x1800471b4  cmp     rax, r15
0x1800471b7  jb      loc_1800470D3
0x1800471bd  test    r12d, r12d
0x1800471c0  jz      short loc_1800471FF
0x1800471c2  lea     r14, [rdx+10h]
0x1800471c6  mov     rcx, r14; lpCriticalSection
0x1800471c9  call    cs:__imp_LeaveCriticalSection
0x1800471cf  mov     rax, [rdi]
0x1800471d2  lea     r9, [rbp+610h+var_680]
0x1800471d6  mov     r8d, r12d
0x1800471d9  mov     edx, r13d
0x1800471dc  mov     rcx, rdi
0x1800471df  mov     rax, [rax+18h]
0x1800471e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800471e8  mov     eax, cs:?g_perfStatEnabled@@3KC; ulong volatile g_perfStatEnabled
0x1800471ee  test    eax, eax
0x1800471f0  jnz     loc_180047545
0x1800471f6  mov     rcx, r14; lpCriticalSection
0x1800471f9  call    cs:__imp_EnterCriticalSection
0x1800471ff  mov     r13, [rsp+710h+var_6D8]
0x180047204  lea     r12, ?g_csShutdownLock@@3Vrecursive_mutex@utl@@A; utl::recursive_mutex g_csShutdownLock
0x18004720b  test    rdi, rdi
0x18004720e  jz      short loc_18004721F
0x180047210  mov     rax, [rdi]
0x180047213  mov     rcx, rdi
0x180047216  mov     rax, [rax+10h]
0x18004721a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004721f  mov     rbx, [rbx]
0x180047222  mov     rcx, r12; lpCriticalSection
0x180047225  call    cs:__imp_EnterCriticalSection
0x18004722b  mov     edi, cs:?g_serviceShuttingDown@@3HA; int g_serviceShuttingDown
0x180047231  mov     rcx, r12; lpCriticalSection
0x180047234  call    cs:__imp_LeaveCriticalSection
0x18004723a  mov     r14, [rbp+610h+var_690]
0x18004723e  test    edi, edi
0x180047240  jz      loc_180047053
0x180047246  mov     rsi, [rsp+710h+var_698]
0x18004724b  mov     edi, [rsp+710h+var_6D0]
0x18004724f  mov     rsi, [rsi]
0x180047252  mov     rcx, r12; lpCriticalSection
0x180047255  mov     [rsp+710h+var_698], rsi
0x18004725a  call    cs:__imp_EnterCriticalSection
0x180047260  mov     ebx, cs:?g_serviceShuttingDown@@3HA; int g_serviceShuttingDown
0x180047266  mov     rcx, r12; lpCriticalSection
0x180047269  call    cs:__imp_LeaveCriticalSection
0x18004726f  test    ebx, ebx
0x180047271  jz      loc_18004700C
0x180047277  mov     r12, [rsp+710h+var_6B8]
0x18004727c  mov     r14, [rsp+710h+Block]
0x180047281  mov     r13, [rbp+610h+var_688]
0x180047285  mov     rdi, [r13+0]
0x180047289  mov     rbx, [r13+8]
0x18004728d  sub     rbx, rdi
0x180047290  mov     [r13+8], rdi
0x180047294  sar     rbx, 3
0x180047298  test    rbx, rbx
0x18004729b  jnz     loc_180047407
0x1800472a1  mov     rax, [rsp+710h+var_6C8]
0x1800472a6  mov     [r13+18h], ebx
0x1800472aa  test    rax, rax
0x1800472ad  jz      short loc_1800472B9
0x1800472af  lea     rcx, [rax+8]; lpCriticalSection
0x1800472b3  call    cs:__imp_LeaveCriticalSection
0x1800472b9  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1800472bd  jz      short loc_1800472DE
0x1800472bf  sub     r12, r14
0x1800472c2  sar     r12, 3
0x1800472c6  test    r12, r12
0x1800472c9  jnz     loc_1800473F6
0x1800472cf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800472d6  mov     rcx, r14; Block
0x1800472d9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800472de  mov     rcx, [rbp+610h+var_40]
0x1800472e5  xor     rcx, rsp; StackCookie
0x1800472e8  call    __security_check_cookie
0x1800472ed  mov     rbx, [rsp+710h+arg_10]
0x1800472f5  add     rsp, 6E0h
0x1800472fc  pop     r15
0x1800472fe  pop     r14
0x180047300  pop     r13
0x180047302  pop     r12
0x180047304  pop     rdi
0x180047305  pop     rsi
0x180047306  pop     rbp
0x180047307  retn
0x180047308  cmp     dword ptr [r13+0], 40000000h
0x180047310  jz      loc_180047113
0x180047316  cmp     rax, [rbx+38h]
0x18004731a  jz      loc_18004719D
0x180047320  mov     ecx, [r13+10h]
0x180047324  cmp     [rax], ecx
0x180047326  jz      loc_180047113
0x18004732c  add     rax, 4
0x180047330  jmp     short loc_180047316
0x180047332  mov     r13d, [rsp+710h+var_6E0]
0x180047337  mov     rdx, [rsp+710h+var_6D8]
0x18004733c  jmp     loc_1800471A7
0x180047341  mov     r10d, 1
0x180047347  inc     r11d
0x18004734a  mov     eax, r11d
0x18004734d  cmp     rax, rdx
0x180047350  jb      loc_18004713D
0x180047356  test    r10d, r10d
0x180047359  jz      loc_18004719D
0x18004735f  lea     rdx, [r13+48h]
0x180047363  lea     rcx, [rbx+20h]
0x180047367  mov     r8d, [rdx]
0x18004736a  mov     rdx, [rsp+710h+var_6D8]
0x18004736f  mov     eax, [rdx+60h]
0x180047372  cmp     r8d, eax
0x180047375  jz      loc_180047462
  ... truncated ...
```
