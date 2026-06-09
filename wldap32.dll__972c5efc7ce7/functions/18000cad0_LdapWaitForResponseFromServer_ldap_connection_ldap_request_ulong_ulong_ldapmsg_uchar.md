# LdapWaitForResponseFromServer(ldap_connection *,ldap_request *,ulong,ulong,ldapmsg * *,uchar)

- ea: `0x18000cad0`
- end: `0x18000cd8d`
- name: `?LdapWaitForResponseFromServer@@YAKPEAUldap_connection@@PEAUldap_request@@KKPEAPEAUldapmsg@@E@Z`
- size: `701`
- prototype: `unsigned int __fastcall(struct ldap_connection *, struct ldap_request *, unsigned int, unsigned int, struct ldapmsg **, char)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x18000bf40`
- `0x180012ab0`
- `0x1800164a0`
- `0x18001da40`
- `0x1800491d4`

## callees

- `0x180006d80`
- `0x18000cad0`
- `0x180018d50`
- `0x180028530`
- `0x180031f88`
- `0x1800327b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000cb12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000cbe8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ccf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000cd51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000cb12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000cbe8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ccf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000cd51`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000cb56`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000cbcc`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000cb56`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000cbcc`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x18000cd05`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x18000cd64`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x18000cd05`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x18000cd64`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadTimes` at `0x18000cb36`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadTimes` at `0x18000cc0c`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadTimes` at `0x18000cb36`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadTimes` at `0x18000cc0c`

## pseudocode

```c
__int64 __fastcall LdapWaitForResponseFromServer(
        struct ldap_connection *a1,
        struct ldap_request *a2,
        unsigned int a3,
        unsigned int a4,
        struct ldapmsg **a5,
        char a6)
{
  BOOL v7; // r14d
  HANDLE CurrentThread; // rax
  __int64 v12; // rsi
  unsigned int v13; // eax
  unsigned int v14; // ebx
  volatile signed __int64 *v15; // rax
  __int64 *v16; // rcx
  HANDLE v17; // rax
  __int64 v18; // rcx
  HANDLE v20; // rax
  HANDLE v21; // rax
  struct _FILETIME KernelTime; // [rsp+30h] [rbp-48h] BYREF
  struct _FILETIME UserTime; // [rsp+38h] [rbp-40h] BYREF
  LARGE_INTEGER v24; // [rsp+40h] [rbp-38h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp-30h] BYREF
  unsigned __int64 CycleTime; // [rsp+50h] [rbp-28h] BYREF
  struct _FILETIME ExitTime; // [rsp+58h] [rbp-20h] BYREF
  struct _FILETIME CreationTime; // [rsp+60h] [rbp-18h] BYREF

  CycleTime = 0;
  v7 = 0;
  PerformanceCount.QuadPart = 0;
  v24.QuadPart = 0;
  CreationTime = 0;
  ExitTime = 0;
  KernelTime = 0;
  UserTime = 0;
  CurrentThread = GetCurrentThread();
  if ( GetThreadTimes(CurrentThread, &CreationTime, &ExitTime, &KernelTime, &UserTime) )
    v12 = *(_QWORD *)&KernelTime + *(_QWORD *)&UserTime;
  else
    v12 = 0;
  QueryPerformanceCounter(&PerformanceCount);
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x20000000) != 0 )
  {
    v20 = GetCurrentThread();
    v7 = QueryThreadCycleTime(v20, &CycleTime);
  }
  if ( GlobalParallelRecvMode )
  {
    if ( a2 && a5 )
      v13 = LdapWaitForResponseFromServerParallelHelper(a1, a2, a3, a4, a5, a6);
    else
      v13 = LdapWaitForAnyResponseFromServerParallel(a1, a3, a4, a5, a6);
  }
  else
  {
    v13 = LdapWaitForResponseFromServerSerial(a1, a2, a3, a4, a5, a6);
  }
  v14 = v13;
  if ( v13 )
  {
    _InterlockedIncrement64(&qword_1800661E8);
    v15 = &qword_180066148;
    v16 = &qword_180066120;
  }
  else
  {
    _InterlockedIncrement64(&qword_180066218);
    v16 = &qword_180066118;
    v15 = &qword_180066140;
  }
  if ( a3 )
    v15 = v16;
  _InterlockedIncrement64(v15);
  QueryPerformanceCounter(&v24);
  ExitTime = 0;
  CreationTime = 0;
  UserTime = 0;
  KernelTime = 0;
  v17 = GetCurrentThread();
  if ( GetThreadTimes(v17, &ExitTime, &CreationTime, &UserTime, &KernelTime) )
    v18 = *(_QWORD *)&KernelTime + *(_QWORD *)&UserTime;
  else
    v18 = 0;
  _InterlockedAdd64(&qword_180066128, v24.QuadPart - PerformanceCount.QuadPart);
  _InterlockedIncrement64(&qword_180066130);
  _InterlockedAdd64(
    &qword_180066208,
    (unsigned __int64)(1000 * (v24.QuadPart - PerformanceCount.QuadPart)) / GlobalPerfFrequency.QuadPart);
  _InterlockedAdd64(&qword_180066220, v18 - v12);
  if ( v7 )
  {
    UserTime = 0;
    v21 = GetCurrentThread();
    if ( QueryThreadCycleTime(v21, (PULONG64)&UserTime) )
      _InterlockedAdd64(&qword_180066210, *(_QWORD *)&UserTime - CycleTime);
  }
  LogTelemetry();
  LogIncrementalPerformance();
  return v14;
}

```

## disassembly

```asm
0x18000cad0  push    rbp
0x18000cad2  push    rbx
0x18000cad3  push    rsi
0x18000cad4  push    rdi
0x18000cad5  push    r12
0x18000cad7  push    r13
0x18000cad9  push    r14
0x18000cadb  push    r15
0x18000cadd  mov     rbp, rsp
0x18000cae0  sub     rsp, 78h
0x18000cae4  xor     r13d, r13d
0x18000cae7  mov     r15d, r9d
0x18000caea  mov     [rbp+CycleTime], r13
0x18000caee  mov     r14d, r13d
0x18000caf1  mov     qword ptr [rbp+PerformanceCount], r13
0x18000caf5  mov     edi, r8d
0x18000caf8  mov     qword ptr [rbp+var_38], r13
0x18000cafc  mov     rbx, rdx
0x18000caff  mov     qword ptr [rbp+CreationTime.dwLowDateTime], r13
0x18000cb03  mov     r12, rcx
0x18000cb06  mov     qword ptr [rbp+ExitTime.dwLowDateTime], r13
0x18000cb0a  mov     qword ptr [rbp+KernelTime.dwLowDateTime], r13
0x18000cb0e  mov     qword ptr [rbp+UserTime.dwLowDateTime], r13
0x18000cb12  call    cs:__imp_GetCurrentThread
0x18000cb19  nop     dword ptr [rax+rax+00h]
0x18000cb1e  mov     rcx, rax; hThread
0x18000cb21  lea     r9, [rbp+KernelTime]; lpKernelTime
0x18000cb25  lea     rax, [rbp+UserTime]
0x18000cb29  lea     r8, [rbp+ExitTime]; lpExitTime
0x18000cb2d  mov     [rsp+78h+lpUserTime], rax; lpUserTime
0x18000cb32  lea     rdx, [rbp+CreationTime]; lpCreationTime
0x18000cb36  call    cs:__imp_GetThreadTimes
0x18000cb3d  nop     dword ptr [rax+rax+00h]
0x18000cb42  test    eax, eax
0x18000cb44  jz      loc_18000CCCC
0x18000cb4a  mov     rsi, qword ptr [rbp+UserTime.dwLowDateTime]
0x18000cb4e  add     rsi, qword ptr [rbp+KernelTime.dwLowDateTime]
0x18000cb52  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000cb56  call    cs:__imp_QueryPerformanceCounter
0x18000cb5d  nop     dword ptr [rax+rax+00h]
0x18000cb62  cmp     cs:g_fTracingOn, r13d
0x18000cb69  jnz     loc_18000CCD4
0x18000cb6f  cmp     cs:GlobalParallelRecvMode, r13d
0x18000cb76  jnz     loc_18000CC8A
0x18000cb7c  movzx   ecx, [rbp+arg_28]
0x18000cb80  mov     r9d, r15d; unsigned int
0x18000cb83  mov     [rsp+78h+var_50], cl; unsigned __int8
0x18000cb87  mov     r8d, edi; unsigned int
0x18000cb8a  mov     rcx, [rbp+arg_20]
0x18000cb8e  mov     rdx, rbx; struct ldap_request *
0x18000cb91  mov     [rsp+78h+lpUserTime], rcx; struct ldapmsg **
0x18000cb96  mov     rcx, r12; struct ldap_connection *
0x18000cb99  call    ?LdapWaitForResponseFromServerSerial@@YAKPEAUldap_connection@@PEAUldap_request@@KKPEAPEAUldapmsg@@E@Z; LdapWaitForResponseFromServerSerial(ldap_connection *,ldap_request *,ulong,ulong,ldapmsg * *,uchar)
0x18000cb9e  mov     ebx, eax
0x18000cba0  test    eax, eax
0x18000cba2  jz      loc_18000CCB1
0x18000cba8  lock inc cs:qword_1800661E8
0x18000cbb0  lea     rax, qword_180066148
0x18000cbb7  lea     rcx, qword_180066120
0x18000cbbe  test    edi, edi
0x18000cbc0  cmovnz  rax, rcx
0x18000cbc4  lock inc qword ptr [rax]
0x18000cbc8  lea     rcx, [rbp+var_38]; lpPerformanceCount
0x18000cbcc  call    cs:__imp_QueryPerformanceCounter
0x18000cbd3  nop     dword ptr [rax+rax+00h]
0x18000cbd8  mov     qword ptr [rbp+ExitTime.dwLowDateTime], r13
0x18000cbdc  mov     qword ptr [rbp+CreationTime.dwLowDateTime], r13
0x18000cbe0  mov     qword ptr [rbp+UserTime.dwLowDateTime], r13
0x18000cbe4  mov     qword ptr [rbp+KernelTime.dwLowDateTime], r13
0x18000cbe8  call    cs:__imp_GetCurrentThread
0x18000cbef  nop     dword ptr [rax+rax+00h]
0x18000cbf4  mov     rcx, rax; hThread
0x18000cbf7  lea     r9, [rbp+UserTime]; lpKernelTime
0x18000cbfb  lea     rax, [rbp+KernelTime]
0x18000cbff  lea     r8, [rbp+CreationTime]; lpExitTime
0x18000cc03  mov     [rsp+78h+lpUserTime], rax; lpUserTime
0x18000cc08  lea     rdx, [rbp+ExitTime]; lpCreationTime
0x18000cc0c  call    cs:__imp_GetThreadTimes
0x18000cc13  nop     dword ptr [rax+rax+00h]
0x18000cc18  test    eax, eax
0x18000cc1a  jz      loc_18000CD45
0x18000cc20  mov     rcx, qword ptr [rbp+UserTime.dwLowDateTime]
0x18000cc24  add     rcx, qword ptr [rbp+KernelTime.dwLowDateTime]
0x18000cc28  mov     rax, qword ptr [rbp+var_38]
0x18000cc2c  sub     rax, qword ptr [rbp+PerformanceCount]
0x18000cc30  lock add cs:qword_180066128, rax
0x18000cc38  lock inc cs:qword_180066130
0x18000cc40  imul    rax, 3E8h
0x18000cc47  xor     edx, edx
0x18000cc49  div     qword ptr cs:?GlobalPerfFrequency@@3_KA; unsigned __int64 GlobalPerfFrequency ...
0x18000cc50  lock add cs:qword_180066208, rax
0x18000cc58  sub     rcx, rsi
0x18000cc5b  lock add cs:qword_180066220, rcx
0x18000cc63  test    r14d, r14d
0x18000cc66  jnz     loc_18000CD4D
0x18000cc6c  call    ?LogTelemetry@@YAXXZ; LogTelemetry(void)
0x18000cc71  call    ?LogIncrementalPerformance@@YAXXZ; LogIncrementalPerformance(void)
0x18000cc76  mov     eax, ebx
0x18000cc78  add     rsp, 78h
0x18000cc7c  pop     r15
0x18000cc7e  pop     r14
0x18000cc80  pop     r13
0x18000cc82  pop     r12
0x18000cc84  pop     rdi
0x18000cc85  pop     rsi
0x18000cc86  pop     rbx
0x18000cc87  pop     rbp
0x18000cc88  retn
0x18000cc8a  mov     r9, [rbp+arg_20]; struct ldapmsg **
0x18000cc8e  test    rbx, rbx
0x18000cc91  jnz     loc_18000CD19
0x18000cc97  movzx   eax, [rbp+arg_28]
0x18000cc9b  mov     r8d, r15d; unsigned int
0x18000cc9e  mov     edx, edi; unsigned int
0x18000cca0  mov     byte ptr [rsp+78h+lpUserTime], al; unsigned __int8
0x18000cca4  mov     rcx, r12; struct ldap_connection *
0x18000cca7  call    ?LdapWaitForAnyResponseFromServerParallel@@YAKPEAUldap_connection@@KKPEAPEAUldapmsg@@E@Z; LdapWaitForAnyResponseFromServerParallel(ldap_connection *,ulong,ulong,ldapmsg * *,uchar)
0x18000ccac  jmp     loc_18000CB9E
0x18000ccb1  lock inc cs:qword_180066218
0x18000ccb9  lea     rcx, qword_180066118
0x18000ccc0  lea     rax, qword_180066140
0x18000ccc7  jmp     loc_18000CBBE
0x18000cccc  mov     rsi, r13
0x18000cccf  jmp     loc_18000CB52
0x18000ccd4  cmp     cs:g_fProviderEnabled, r13d
0x18000ccdb  jz      loc_18000CB6F
0x18000cce1  test    cs:g_ulTraceFlags, 20000000h
0x18000ccec  jz      loc_18000CB6F
0x18000ccf2  call    cs:__imp_GetCurrentThread
0x18000ccf9  nop     dword ptr [rax+rax+00h]
0x18000ccfe  mov     rcx, rax; ThreadHandle
0x18000cd01  lea     rdx, [rbp+CycleTime]; CycleTime
0x18000cd05  call    cs:__imp_QueryThreadCycleTime
0x18000cd0c  nop     dword ptr [rax+rax+00h]
0x18000cd11  mov     r14d, eax
0x18000cd14  jmp     loc_18000CB6F
0x18000cd19  test    r9, r9
0x18000cd1c  jz      loc_18000CC97
0x18000cd22  movzx   eax, [rbp+arg_28]
0x18000cd26  mov     r8d, edi; unsigned int
0x18000cd29  mov     [rsp+78h+var_50], al; unsigned __int8
0x18000cd2d  mov     rdx, rbx; struct ldap_request *
0x18000cd30  mov     [rsp+78h+lpUserTime], r9; struct ldapmsg **
0x18000cd35  mov     rcx, r12; struct ldap_connection *
0x18000cd38  mov     r9d, r15d; unsigned int
0x18000cd3b  call    ?LdapWaitForResponseFromServerParallelHelper@@YAKPEAUldap_connection@@PEAUldap_request@@KKPEAPEAUldapmsg@@E@Z; LdapWaitForResponseFromServerParallelHelper(ldap_connection *,ldap_request *,ulong,ulong,ldapmsg * *,uchar)
0x18000cd40  jmp     loc_18000CB9E
0x18000cd45  mov     rcx, r13
0x18000cd48  jmp     loc_18000CC28
0x18000cd4d  mov     qword ptr [rbp+UserTime.dwLowDateTime], r13
0x18000cd51  call    cs:__imp_GetCurrentThread
0x18000cd58  nop     dword ptr [rax+rax+00h]
0x18000cd5d  mov     rcx, rax; ThreadHandle
0x18000cd60  lea     rdx, [rbp+UserTime]; CycleTime
0x18000cd64  call    cs:__imp_QueryThreadCycleTime
0x18000cd6b  nop     dword ptr [rax+rax+00h]
0x18000cd70  test    eax, eax
0x18000cd72  jz      loc_18000CC6C
0x18000cd78  mov     rax, qword ptr [rbp+UserTime.dwLowDateTime]
0x18000cd7c  sub     rax, [rbp+CycleTime]
0x18000cd80  lock add cs:qword_180066210, rax
0x18000cd88  jmp     loc_18000CC6C
```
