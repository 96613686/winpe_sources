# UL_NATIVE_REQUEST::DoWork(ulong,ulong,ulong,_OVERLAPPED *)

- ea: `0x18000eef0`
- end: `0x18000f4fb`
- name: `?DoWork@UL_NATIVE_REQUEST@@QEAAXKKKPEAU_OVERLAPPED@@@Z`
- size: `1547`
- prototype: `void __fastcall(UL_NATIVE_REQUEST *__hidden this, unsigned int, unsigned int, unsigned int, ULONG)`
- caller_count: `4`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000edc0`
- `0x18000ee90`
- `0x18000eec0`
- `0x18000eef0`

## callees

- `0x18000eef0`
- `0x18000f510`
- `0x18000f660`
- `0x18000f73c`
- `0x18000f770`
- `0x180012050`
- `0x180014bfc`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f3cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f3e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f3cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f3e1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f119`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f119`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f169`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f4aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f4e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f169`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f4aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f4e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f0fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f0fd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f435`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f435`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f3f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f416`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f3f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f416`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x18000f15e`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x18000f495`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x18000f15e`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x18000f495`
- `W3TP!ThreadPoolPostCompletion` at `0x18000f2ce`
- `W3TP!ThreadPoolPostCompletion` at `0x18000f2ce`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000f04c`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000f04c`
- `iisutil!?QueryOutstandingAllocationCount@ALLOC_CACHE_HANDLER@@QEBAKXZ` at `0x18000f037`
- `iisutil!?QueryOutstandingAllocationCount@ALLOC_CACHE_HANDLER@@QEBAKXZ` at `0x18000f037`

## pseudocode

```c
void __fastcall UL_NATIVE_REQUEST::DoWork(
        UL_NATIVE_REQUEST *this,
        unsigned int j,
        int a3,
        int a4,
        __int64 BytesReturned)
{
  __int64 v5; // r14
  unsigned int v6; // ebp
  int i; // eax
  int v9; // ecx
  int v10; // ecx
  bool v11; // zf
  __int64 v12; // r8
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned int v15; // ecx
  unsigned int v16; // ebx
  unsigned int k; // edi
  UL_NATIVE_REQUEST *v18; // rax
  UL_NATIVE_REQUEST *v19; // rax
  WP_CONTEXT *v20; // rdi
  _QWORD *v21; // rbx
  RTL_SRWLOCK *v22; // r15
  void *v23; // rcx
  ULONG v24; // ebx
  int v25; // ecx
  int v26; // ecx
  void *v27; // rcx
  void *v28; // rcx
  char *v29; // rcx
  unsigned int v30; // r9d
  unsigned int v31; // ecx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // r9
  __int64 v35; // r8
  __int64 v36; // rax
  __int64 v37; // rcx
  _QWORD *v38; // rcx
  HTTP_REQUEST_ID v39; // rbx
  SIZE_T v40; // rdx
  HLOCAL v41; // rax
  void *v42; // rax
  ULONG v43; // eax
  ULONG v44; // [rsp+40h] [rbp-28h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-20h] BYREF

  v5 = BytesReturned;
  v6 = j;
  if ( BytesReturned )
  {
    if ( j == 1 )
    {
      *((_DWORD *)this + 4) = a3;
      *((_DWORD *)this + 5) = a4;
      *((_OWORD *)this + 194) = 0;
      *((_OWORD *)this + 195) = 0;
      goto LABEL_5;
    }
    if ( j == 2 )
    {
      *((_DWORD *)this + 6) = a3;
      *((_DWORD *)this + 7) = a4;
      *(_OWORD *)((char *)this + 3064) = 0;
      *(_OWORD *)((char *)this + 3080) = 0;
      goto LABEL_5;
    }
  }
  else
  {
LABEL_5:
    for ( i = 0; ; i = UL_NATIVE_REQUEST::DoStateClientCertificate(this) )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          if ( i )
            return;
          v9 = *((_DWORD *)this + 1);
          if ( v9 )
            break;
          LODWORD(BytesReturned) = 0;
          if ( *((_DWORD *)g_pwpContext + 194) )
          {
            *((_DWORD *)this + 1) = 3;
            goto LABEL_5;
          }
          *((_DWORD *)this + 1) = 1;
          _InterlockedIncrement((volatile signed __int32 *)&UL_NATIVE_REQUEST::sm_cRequestsPending);
          v20 = g_pwpContext;
          v21 = (_QWORD *)*((_QWORD *)g_pwpContext + 96);
          v22 = (RTL_SRWLOCK *)(*v21 + v21[1] * ((unsigned __int64)GetCurrentThreadId() % v21[2]));
          AcquireSRWLockShared(v22);
          v23 = (void *)*((_QWORD *)v20 + 95);
          if ( !v23 )
          {
            ReleaseSRWLockShared(v22);
LABEL_58:
            _InterlockedDecrement((volatile signed __int32 *)&UL_NATIVE_REQUEST::sm_cRequestsPending);
LABEL_59:
            *((_DWORD *)this + 1) = 3;
            goto LABEL_5;
          }
          v24 = HttpReceiveHttpRequest(
                  v23,
                  0,
                  1u,
                  *((PHTTP_REQUEST *)this + 368),
                  *((_DWORD *)this + 738),
                  (PULONG)&BytesReturned,
                  (LPOVERLAPPED)this + 97);
          ReleaseSRWLockShared(v22);
          if ( v24 == 997 )
          {
            i = 1;
          }
          else
          {
            if ( v24 )
            {
              if ( v24 != 234 )
                goto LABEL_58;
              *((_DWORD *)this + 4) = BytesReturned;
              *((_DWORD *)this + 5) = 234;
              goto LABEL_5;
            }
            v30 = *((_DWORD *)this + 756);
            v31 = BytesReturned;
            *((_DWORD *)this + 5) = 0;
            j = v30 / 0xA;
            *((_DWORD *)this + 4) = v31;
            if ( v30 != 10 * (v30 / 0xA)
              || !ThreadPoolPostCompletion(
                    v31,
                    (void (*)(unsigned int, unsigned int, struct _OVERLAPPED *))WP_CONTEXT::OnCompletion,
                    (struct _OVERLAPPED *)this + 97) )
            {
              goto LABEL_5;
            }
            i = 1;
          }
        }
        v10 = v9 - 1;
        if ( !v10 )
        {
          v11 = *((_DWORD *)this + 5) == 234;
          v44 = 0;
          SRWLock = 0;
          if ( v11 )
          {
            v38 = (_QWORD *)*((_QWORD *)this + 368);
            v39 = v38[2];
            if ( v38 != (_QWORD *)((char *)this + 32) )
            {
              LocalFree(v38);
              *((_QWORD *)this + 368) = 0;
            }
            v40 = *((unsigned int *)this + 4);
            *((_DWORD *)this + 738) = v40;
            v41 = LocalAlloc(0x40u, v40);
            *((_QWORD *)this + 368) = v41;
            if ( !v41 )
              goto LABEL_59;
            v42 = UL_APP_POOL::QueryAndLockHandle((WP_CONTEXT *)((char *)g_pwpContext + 760), (void **)&SRWLock);
            if ( v42 )
              v43 = HttpReceiveHttpRequest(
                      v42,
                      v39,
                      1u,
                      *((PHTTP_REQUEST *)this + 368),
                      *((_DWORD *)this + 738),
                      &v44,
                      0);
            else
              v43 = 6;
            *((_DWORD *)this + 5) = v43;
            ReleaseSRWLockShared(SRWLock);
          }
          if ( *((_DWORD *)this + 5) )
          {
            _InterlockedDecrement((volatile signed __int32 *)&UL_NATIVE_REQUEST::sm_cRequestsPending);
            UL_NATIVE_REQUEST::Reset(this);
          }
          else
          {
            v12 = *((_QWORD *)this + 368);
            v13 = *(_QWORD *)(v12 + 840);
            if ( v13 )
            {
              v36 = *(_QWORD *)(v13 + 32);
              if ( v36 )
              {
                *((_QWORD *)this + 376) = *(_QWORD *)(v36 + 16);
                v37 = *(_QWORD *)(v12 + 840);
                if ( !*(_DWORD *)(*(_QWORD *)(v37 + 32) + 4LL) )
                  *(_QWORD *)(v37 + 32) = 0;
              }
            }
            for ( j = 0; j < *(unsigned __int16 *)(v12 + 848); ++j )
            {
              v14 = *(_QWORD *)(v12 + 856);
              if ( !*(_DWORD *)(v14 + 16LL * j) )
                *((_QWORD *)this + 377) = *(_QWORD *)(*(_QWORD *)(v14 + 16LL * j + 8) + 16LL);
            }
            v15 = _InterlockedDecrement((volatile signed __int32 *)&UL_NATIVE_REQUEST::sm_cRequestsPending);
            if ( !UL_NATIVE_REQUEST::sm_fAddingRequests && v15 < UL_NATIVE_REQUEST::sm_cDesiredPendingRequests >> 1 )
            {
              v16 = UL_NATIVE_REQUEST::sm_cDesiredPendingRequests - v15;
              if ( !_InterlockedCompareExchange(&UL_NATIVE_REQUEST::sm_fAddingRequests, 1, 0) )
              {
                for ( k = 0; k < v16; ++k )
                {
                  if ( ALLOC_CACHE_HANDLER::QueryOutstandingAllocationCount(UL_NATIVE_REQUEST::sm_pachNativeRequests) >= UL_NATIVE_REQUEST::sm_cMaxRequests )
                    break;
                  v18 = (UL_NATIVE_REQUEST *)ALLOC_CACHE_HANDLER::Alloc(UL_NATIVE_REQUEST::sm_pachNativeRequests);
                  if ( !v18 )
                    break;
                  v19 = UL_NATIVE_REQUEST::UL_NATIVE_REQUEST(v18);
                  if ( !v19 )
                    break;
                  *((_QWORD *)v19 + 381) = (char *)v19 + 3152;
                  UL_NATIVE_REQUEST::DoWork(v19, 0, 0, 0, 0);
                }
                UL_NATIVE_REQUEST::sm_fAddingRequests = 0;
              }
            }
            *((_DWORD *)this + 1) = 2;
          }
          goto LABEL_5;
        }
        v26 = v10 - 1;
        if ( v26 )
          break;
        if ( *((_QWORD *)this + 1) )
        {
          if ( v6 == 2 )
          {
            v32 = 24;
            v33 = 28;
          }
          else
          {
            v32 = 16;
            v33 = 20;
          }
          v34 = *(unsigned int *)((char *)this + v33);
          v35 = *(unsigned int *)((char *)this + v32);
          _InterlockedDecrement((volatile signed __int32 *)this + 784);
          i = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, __int64, __int64))g_pfnIoCompletion)(
                v6,
                *((_QWORD *)this + 1),
                v35,
                v34,
                v5);
        }
        else
        {
          i = ((__int64 (__fastcall *)(UL_NATIVE_REQUEST *))g_pfnNewRequest)(this);
        }
        if ( i != 1 )
        {
          if ( UL_NATIVE_REQUEST::sm_cRequestsPending < 2 * UL_NATIVE_REQUEST::sm_cDesiredPendingRequests )
          {
            v27 = (void *)*((_QWORD *)this + 376);
            if ( v27 )
            {
              CloseHandle(v27);
              *((_QWORD *)this + 376) = 0;
            }
            v28 = (void *)*((_QWORD *)this + 377);
            if ( v28 )
            {
              CloseHandle(v28);
              *((_QWORD *)this + 377) = 0;
            }
            v29 = (char *)*((_QWORD *)this + 368);
            if ( v29 != (char *)this + 32 )
              LocalFree(v29);
            ++*((_DWORD *)this + 756);
            *((_QWORD *)this + 368) = (char *)this + 32;
            *((_DWORD *)this + 738) = 2912;
            *((_DWORD *)this + 1) = 0;
            *((_QWORD *)this + 1) = 0;
            *((_QWORD *)this + 2) = 0;
            *((_QWORD *)this + 3) = 0;
            *((_DWORD *)this + 784) = 0;
            *((_OWORD *)this + 194) = 0;
            *((_OWORD *)this + 195) = 0;
            *(_OWORD *)((char *)this + 3064) = 0;
            *(_OWORD *)((char *)this + 3080) = 0;
            goto LABEL_5;
          }
          UL_NATIVE_REQUEST::FreeWorkerRequest(this);
          i = 1;
        }
      }
      v25 = v26 - 1;
      if ( !v25 )
        break;
      if ( v25 != 1 )
        return;
    }
    UL_NATIVE_REQUEST::`scalar deleting destructor'(this, j);
  }
}

```

## disassembly

```asm
0x18000eef0  push    rbp
0x18000eef2  push    rsi
0x18000eef3  push    r14
0x18000eef5  sub     rsp, 50h
0x18000eef9  mov     r14, [rsp+68h+arg_20]
0x18000ef01  mov     ebp, edx
0x18000ef03  mov     rsi, rcx
0x18000ef06  test    r14, r14
0x18000ef09  jz      short loc_18000EF38
0x18000ef0b  mov     eax, edx
0x18000ef0d  sub     eax, 1
0x18000ef10  jz      loc_18000F0A7
0x18000ef16  cmp     eax, 1
0x18000ef19  jnz     loc_18000F1AF
0x18000ef1f  xorps   xmm0, xmm0
0x18000ef22  mov     [rcx+18h], r8d
0x18000ef26  mov     [rcx+1Ch], r9d
0x18000ef2a  movups  xmmword ptr [rcx+0BF8h], xmm0
0x18000ef31  movups  xmmword ptr [rcx+0C08h], xmm0
0x18000ef38  mov     [rsp+68h+arg_0], rbx
0x18000ef3d  mov     [rsp+68h+arg_8], rdi
0x18000ef42  mov     [rsp+68h+arg_10], r12
0x18000ef4a  mov     r12d, 1
0x18000ef50  mov     [rsp+68h+arg_18], r15
0x18000ef58  xor     eax, eax
0x18000ef5a  test    eax, eax
0x18000ef5c  jnz     loc_18000F195
0x18000ef62  mov     ecx, [rsi+4]
0x18000ef65  test    ecx, ecx
0x18000ef67  jz      loc_18000F0C5
0x18000ef6d  sub     ecx, r12d
0x18000ef70  jnz     loc_18000F1B8
0x18000ef76  cmp     dword ptr [rsi+14h], 0EAh
0x18000ef7d  mov     [rsp+68h+var_28], ecx
0x18000ef81  mov     [rsp+68h+SRWLock], 0
0x18000ef8a  jz      loc_18000F402
0x18000ef90  cmp     dword ptr [rsi+14h], 0
0x18000ef94  jnz     loc_18000F399
0x18000ef9a  mov     r8, [rsi+0B80h]
0x18000efa1  mov     rax, [r8+348h]
0x18000efa8  test    rax, rax
0x18000efab  jnz     loc_18000F324
0x18000efb1  xor     edx, edx
0x18000efb3  xor     eax, eax
0x18000efb5  cmp     ax, [r8+350h]
0x18000efbd  jnb     short loc_18000EFE4
0x18000efbf  nop
0x18000efc0  mov     rax, [r8+358h]
0x18000efc7  mov     ecx, edx
0x18000efc9  add     rcx, rcx
0x18000efcc  cmp     dword ptr [rax+rcx*8], 0
0x18000efd0  jz      loc_18000F4B5
0x18000efd6  movzx   eax, word ptr [r8+350h]
0x18000efde  inc     edx
0x18000efe0  cmp     edx, eax
0x18000efe2  jb      short loc_18000EFC0
0x18000efe4  mov     ecx, 0FFFFFFFFh
0x18000efe9  lock xadd cs:?sm_cRequestsPending@UL_NATIVE_REQUEST@@0KA, ecx; ulong UL_NATIVE_REQUEST::sm_cRequestsPending
0x18000eff1  mov     ebx, cs:?sm_cDesiredPendingRequests@UL_NATIVE_REQUEST@@0KA; ulong UL_NATIVE_REQUEST::sm_cDesiredPendingRequests
0x18000eff7  dec     ecx
0x18000eff9  mov     eax, ebx
0x18000effb  shr     eax, 1
0x18000effd  cmp     cs:?sm_fAddingRequests@UL_NATIVE_REQUEST@@0HA, 0; int UL_NATIVE_REQUEST::sm_fAddingRequests
0x18000f004  jnz     loc_18000F09B
0x18000f00a  cmp     ecx, eax
0x18000f00c  jnb     loc_18000F09B
0x18000f012  sub     ebx, ecx
0x18000f014  xor     eax, eax
0x18000f016  lock cmpxchg cs:?sm_fAddingRequests@UL_NATIVE_REQUEST@@0HA, r12d; int UL_NATIVE_REQUEST::sm_fAddingRequests
0x18000f01f  jnz     short loc_18000F09B
0x18000f021  xor     edi, edi
0x18000f023  test    ebx, ebx
0x18000f025  jz      short loc_18000F091
0x18000f027  nop     word ptr [rax+rax+00000000h]
0x18000f030  mov     rcx, cs:?sm_pachNativeRequests@UL_NATIVE_REQUEST@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * UL_NATIVE_REQUEST::sm_pachNativeRequests
0x18000f037  call    cs:__imp_?QueryOutstandingAllocationCount@ALLOC_CACHE_HANDLER@@QEBAKXZ; ALLOC_CACHE_HANDLER::QueryOutstandingAllocationCount(void)
0x18000f03d  cmp     eax, cs:?sm_cMaxRequests@UL_NATIVE_REQUEST@@0KA; ulong UL_NATIVE_REQUEST::sm_cMaxRequests
0x18000f043  jnb     short loc_18000F091
0x18000f045  mov     rcx, cs:?sm_pachNativeRequests@UL_NATIVE_REQUEST@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * UL_NATIVE_REQUEST::sm_pachNativeRequests
0x18000f04c  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18000f052  test    rax, rax
0x18000f055  jz      short loc_18000F091
0x18000f057  mov     rcx, rax; this
0x18000f05a  call    ??0UL_NATIVE_REQUEST@@QEAA@XZ; UL_NATIVE_REQUEST::UL_NATIVE_REQUEST(void)
0x18000f05f  test    rax, rax
0x18000f062  jz      short loc_18000F091
0x18000f064  lea     rcx, [rax+0C50h]
0x18000f06b  mov     qword ptr [rsp+68h+RequestBufferLength], 0; ULONG
0x18000f074  mov     [rax+0BE8h], rcx
0x18000f07b  xor     r9d, r9d; unsigned int
0x18000f07e  mov     rcx, rax; this
0x18000f081  xor     r8d, r8d; unsigned int
0x18000f084  xor     edx, edx; unsigned int
0x18000f086  call    ?DoWork@UL_NATIVE_REQUEST@@QEAAXKKKPEAU_OVERLAPPED@@@Z; UL_NATIVE_REQUEST::DoWork(ulong,ulong,ulong,_OVERLAPPED *)
0x18000f08b  inc     edi
0x18000f08d  cmp     edi, ebx
0x18000f08f  jb      short loc_18000F030
0x18000f091  mov     cs:?sm_fAddingRequests@UL_NATIVE_REQUEST@@0HA, 0; int UL_NATIVE_REQUEST::sm_fAddingRequests
0x18000f09b  mov     dword ptr [rsi+4], 2
0x18000f0a2  jmp     loc_18000EF58
0x18000f0a7  xorps   xmm0, xmm0
0x18000f0aa  mov     [rcx+10h], r8d
0x18000f0ae  mov     [rcx+14h], r9d
0x18000f0b2  movups  xmmword ptr [rcx+0C20h], xmm0
0x18000f0b9  movups  xmmword ptr [rcx+0C30h], xmm0
0x18000f0c0  jmp     loc_18000EF38
0x18000f0c5  mov     rax, cs:?g_pwpContext@@3PEAVWP_CONTEXT@@EA; WP_CONTEXT * g_pwpContext
0x18000f0cc  mov     dword ptr [rsp+68h+arg_20], 0
0x18000f0d7  cmp     dword ptr [rax+308h], 0
0x18000f0de  jnz     loc_18000F38D
0x18000f0e4  mov     [rsi+4], r12d
0x18000f0e8  lock inc cs:?sm_cRequestsPending@UL_NATIVE_REQUEST@@0KA; ulong UL_NATIVE_REQUEST::sm_cRequestsPending
0x18000f0ef  mov     rdi, cs:?g_pwpContext@@3PEAVWP_CONTEXT@@EA; WP_CONTEXT * g_pwpContext
0x18000f0f6  mov     rbx, [rdi+300h]
0x18000f0fd  call    cs:__imp_GetCurrentThreadId
0x18000f103  mov     eax, eax
0x18000f105  xor     edx, edx
0x18000f107  div     qword ptr [rbx+10h]
0x18000f10b  mov     r15d, edx
0x18000f10e  imul    r15, [rbx+8]
0x18000f113  add     r15, [rbx]
0x18000f116  mov     rcx, r15; SRWLock
0x18000f119  call    cs:__imp_AcquireSRWLockShared
0x18000f11f  mov     rcx, [rdi+2F8h]; RequestQueueHandle
0x18000f126  test    rcx, rcx
0x18000f129  jz      loc_18000F4E0
0x18000f12f  mov     r9, [rsi+0B80h]; RequestBuffer
0x18000f136  lea     rax, [rsp+68h+arg_20]
0x18000f13e  lea     rdi, [rsi+0C20h]
0x18000f145  mov     r8d, r12d; Flags
0x18000f148  mov     [rsp+68h+Overlapped], rdi; Overlapped
0x18000f14d  xor     edx, edx; RequestId
0x18000f14f  mov     [rsp+68h+BytesReturned], rax; BytesReturned
0x18000f154  mov     eax, [rsi+0B88h]
0x18000f15a  mov     [rsp+68h+RequestBufferLength], eax; RequestBufferLength
0x18000f15e  call    cs:__imp_HttpReceiveHttpRequest
0x18000f164  mov     rcx, r15; SRWLock
0x18000f167  mov     ebx, eax
0x18000f169  call    cs:__imp_ReleaseSRWLockShared
0x18000f16f  cmp     ebx, 3E5h
0x18000f175  jnz     loc_18000F28F
0x18000f17b  mov     eax, r12d
0x18000f17e  jmp     loc_18000EF5A
0x18000f183  sub     ecx, r12d
0x18000f186  jz      loc_18000F4EE
0x18000f18c  cmp     ecx, r12d
0x18000f18f  jz      loc_18000F3AD
0x18000f195  mov     r15, [rsp+68h+arg_18]
0x18000f19d  mov     rdi, [rsp+68h+arg_8]
0x18000f1a2  mov     rbx, [rsp+68h+arg_0]
0x18000f1a7  mov     r12, [rsp+68h+arg_10]
0x18000f1af  add     rsp, 50h
0x18000f1b3  pop     r14
0x18000f1b5  pop     rsi
0x18000f1b6  pop     rbp
0x18000f1b7  retn
0x18000f1b8  sub     ecx, r12d
0x18000f1bb  jnz     short loc_18000F183
0x18000f1bd  cmp     qword ptr [rsi+8], 0
0x18000f1c2  jnz     loc_18000F2E4
0x18000f1c8  mov     rax, cs:?g_pfnNewRequest@@3P6A?AW4NREQ_STATUS@@PEAX@ZEA; NREQ_STATUS (*g_pfnNewRequest)(void *)
0x18000f1cf  mov     rcx, rsi
0x18000f1d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1d7  cmp     eax, r12d
0x18000f1da  jz      loc_18000EF5A
0x18000f1e0  mov     eax, cs:?sm_cDesiredPendingRequests@UL_NATIVE_REQUEST@@0KA; ulong UL_NATIVE_REQUEST::sm_cDesiredPendingRequests
0x18000f1e6  add     eax, eax
0x18000f1e8  cmp     cs:?sm_cRequestsPending@UL_NATIVE_REQUEST@@0KA, eax; ulong UL_NATIVE_REQUEST::sm_cRequestsPending
0x18000f1ee  jnb     loc_18000F35E
0x18000f1f4  mov     rcx, [rsi+0BC0h]; hObject
0x18000f1fb  test    rcx, rcx
0x18000f1fe  jnz     loc_18000F3CB
0x18000f204  mov     rcx, [rsi+0BC8h]; hObject
0x18000f20b  test    rcx, rcx
0x18000f20e  jnz     loc_18000F3E1
0x18000f214  mov     rcx, [rsi+0B80h]; hMem
0x18000f21b  lea     rbx, [rsi+20h]
0x18000f21f  cmp     rcx, rbx
0x18000f222  jnz     loc_18000F3F7
0x18000f228  inc     dword ptr [rsi+0BD0h]
0x18000f22e  xorps   xmm0, xmm0
0x18000f231  mov     [rsi+0B80h], rbx
0x18000f238  xorps   xmm1, xmm1
0x18000f23b  mov     dword ptr [rsi+0B88h], 0B60h
0x18000f245  mov     dword ptr [rsi+4], 0
0x18000f24c  mov     qword ptr [rsi+8], 0
0x18000f254  mov     qword ptr [rsi+10h], 0
0x18000f25c  mov     qword ptr [rsi+18h], 0
0x18000f264  mov     dword ptr [rsi+0C40h], 0
0x18000f26e  movups  xmmword ptr [rsi+0C20h], xmm0
0x18000f275  movups  xmmword ptr [rsi+0C30h], xmm0
0x18000f27c  movups  xmmword ptr [rsi+0BF8h], xmm1
0x18000f283  movups  xmmword ptr [rsi+0C08h], xmm1
0x18000f28a  jmp     loc_18000EF58
0x18000f28f  test    ebx, ebx
0x18000f291  jnz     loc_18000F36E
0x18000f297  mov     r9d, [rsi+0BD0h]
0x18000f29e  mov     eax, 0CCCCCCCDh
0x18000f2a3  mov     ecx, dword ptr [rsp+68h+arg_20]
0x18000f2aa  mul     r9d
0x18000f2ad  mov     [rsi+14h], ebx
0x18000f2b0  shr     edx, 3
0x18000f2b3  mov     [rsi+10h], ecx
0x18000f2b6  lea     eax, [rdx+rdx*4]
0x18000f2b9  add     eax, eax
0x18000f2bb  cmp     r9d, eax
0x18000f2be  jnz     loc_18000EF58
0x18000f2c4  mov     r8, rdi
0x18000f2c7  lea     rdx, ?OnCompletion@WP_CONTEXT@@SAXKKPEAU_OVERLAPPED@@@Z; WP_CONTEXT::OnCompletion(ulong,ulong,_OVERLAPPED *)
0x18000f2ce  call    cs:__imp_?ThreadPoolPostCompletion@@YAHKP6AXKKPEAU_OVERLAPPED@@@Z0@Z; ThreadPoolPostCompletion(ulong,void (*)(ulong,ulong,_OVERLAPPED *),_OVERLAPPED *)
0x18000f2d4  test    eax, eax
0x18000f2d6  jz      loc_18000EF58
0x18000f2dc  mov     eax, r12d
0x18000f2df  jmp     loc_18000EF5A
0x18000f2e4  cmp     ebp, 2
0x18000f2e7  jnz     loc_18000F3BA
0x18000f2ed  mov     r8d, 18h
0x18000f2f3  mov     r9d, 1Ch
0x18000f2f9  mov     r9d, [r9+rsi]
0x18000f2fd  mov     ecx, ebp
0x18000f2ff  mov     r8d, [r8+rsi]
0x18000f303  lock dec dword ptr [rsi+0C40h]
0x18000f30a  mov     rdx, [rsi+8]
0x18000f30e  mov     rax, cs:?g_pfnIoCompletion@@3P6A?AW4NREQ_STATUS@@KPEAXKKPEAU_OVERLAPPED@@@ZEA; NREQ_STATUS (*g_pfnIoCompletion)(ulong,void *,ulong,ulong,_OVERLAPPED *)
0x18000f315  mov     qword ptr [rsp+68h+RequestBufferLength], r14
0x18000f31a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f31f  jmp     loc_18000F1D7
0x18000f324  mov     rax, [rax+20h]
0x18000f328  test    rax, rax
0x18000f32b  jz      loc_18000EFB1
0x18000f331  mov     rax, [rax+10h]
0x18000f335  mov     [rsi+0BC0h], rax
0x18000f33c  mov     rcx, [r8+348h]
0x18000f343  mov     rax, [rcx+20h]
0x18000f347  cmp     dword ptr [rax+4], 0
0x18000f34b  jnz     loc_18000EFB1
0x18000f351  mov     qword ptr [rcx+20h], 0
0x18000f359  jmp     loc_18000EFB1
0x18000f35e  mov     rcx, rsi; this
0x18000f361  call    ?FreeWorkerRequest@UL_NATIVE_REQUEST@@SAXPEAV1@@Z; UL_NATIVE_REQUEST::FreeWorkerRequest(UL_NATIVE_REQUEST *)
0x18000f366  mov     eax, r12d
0x18000f369  jmp     loc_18000EF5A
0x18000f36e  cmp     ebx, 0EAh
0x18000f374  jz      loc_18000F4CA
0x18000f37a  lock dec cs:?sm_cRequestsPending@UL_NATIVE_REQUEST@@0KA; ulong UL_NATIVE_REQUEST::sm_cRequestsPending
0x18000f381  mov     dword ptr [rsi+4], 3
0x18000f388  jmp     loc_18000EF58
0x18000f38d  mov     dword ptr [rsi+4], 3
0x18000f394  jmp     loc_18000EF58
0x18000f399  lock dec cs:?sm_cRequestsPending@UL_NATIVE_REQUEST@@0KA; ulong UL_NATIVE_REQUEST::sm_cRequestsPending
0x18000f3a0  mov     rcx, rsi; this
0x18000f3a3  call    ?Reset@UL_NATIVE_REQUEST@@AEAAXXZ; UL_NATIVE_REQUEST::Reset(void)
0x18000f3a8  jmp     loc_18000EF58
0x18000f3ad  mov     rcx, rsi
0x18000f3b0  call    ?DoStateClientCertificate@UL_NATIVE_REQUEST@@AEAA?AW4NREQ_STATUS@@XZ; UL_NATIVE_REQUEST::DoStateClientCertificate(void)
0x18000f3b5  jmp     loc_18000EF5A
0x18000f3ba  mov     r8d, 10h
0x18000f3c0  mov     r9d, 14h
0x18000f3c6  jmp     loc_18000F2F9
0x18000f3cb  call    cs:__imp_CloseHandle
0x18000f3d1  mov     qword ptr [rsi+0BC0h], 0
0x18000f3dc  jmp     loc_18000F204
0x18000f3e1  call    cs:__imp_CloseHandle
0x18000f3e7  mov     qword ptr [rsi+0BC8h], 0
0x18000f3f2  jmp     loc_18000F214
0x18000f3f7  call    cs:__imp_LocalFree
0x18000f3fd  jmp     loc_18000F228
0x18000f402  mov     rcx, [rsi+0B80h]; hMem
0x18000f409  lea     rax, [rsi+20h]
0x18000f40d  mov     rbx, [rcx+10h]
0x18000f411  cmp     rcx, rax
0x18000f414  jz      short loc_18000F427
0x18000f416  call    cs:__imp_LocalFree
0x18000f41c  mov     qword ptr [rsi+0B80h], 0
0x18000f427  mov     edx, [rsi+10h]; uBytes
0x18000f42a  mov     ecx, 40h ; '@'; uFlags
0x18000f42f  mov     [rsi+0B88h], edx
0x18000f435  call    cs:__imp_LocalAlloc
0x18000f43b  mov     [rsi+0B80h], rax
0x18000f442  test    rax, rax
0x18000f445  jz      loc_18000F381
0x18000f44b  mov     rcx, cs:?g_pwpContext@@3PEAVWP_CONTEXT@@EA; WP_CONTEXT * g_pwpContext
0x18000f452  lea     rdx, [rsp+68h+SRWLock]; void **
0x18000f457  add     rcx, 2F8h; this
0x18000f45e  call    ?QueryAndLockHandle@UL_APP_POOL@@QEAAPEAXPEAPEAX@Z; UL_APP_POOL::QueryAndLockHandle(void * *)
0x18000f463  test    rax, rax
0x18000f466  jz      short loc_18000F49D
0x18000f468  mov     r9, [rsi+0B80h]; RequestBuffer
0x18000f46f  lea     rcx, [rsp+68h+var_28]
0x18000f474  mov     [rsp+68h+Overlapped], 0; Overlapped
0x18000f47d  mov     r8d, r12d; Flags
0x18000f480  mov     [rsp+68h+BytesReturned], rcx; BytesReturned
0x18000f485  mov     rdx, rbx; RequestId
0x18000f488  mov     ecx, [rsi+0B88h]
0x18000f48e  mov     [rsp+68h+RequestBufferLength], ecx; RequestBufferLength
0x18000f492  mov     rcx, rax; RequestQueueHandle
0x18000f495  call    cs:__imp_HttpReceiveHttpRequest
0x18000f49b  jmp     short loc_18000F4A2
0x18000f49d  mov     eax, 6
0x18000f4a2  mov     [rsi+14h], eax
  ... truncated ...
```
