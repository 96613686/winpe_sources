# ScNotifyServiceStatusChange(SC_HANDLE__ *,int,ulong,_SERVICE_NOTIFY_2W *)

- ea: `0x180013f34`
- end: `0x1800144b7`
- name: `?ScNotifyServiceStatusChange@@YAKPEAUSC_HANDLE__@@HKPEAU_SERVICE_NOTIFY_2W@@@Z`
- size: `1411`
- prototype: `unsigned int __fastcall(struct SC_HANDLE__ *, int, unsigned int, struct _SERVICE_NOTIFY_2W *)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013f00`
- `0x180013f20`

## callees

- `0x180010720`
- `0x180013f34`
- `0x1800144c0`
- `0x18003b770`
- `0x18003ba74`
- `0x18003bf3c`
- `0x18003c49c`
- `0x18003c8d8`
- `0x18004abac`
- `0x18004f91a`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180014059`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180014059`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180014482`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180014482`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014105`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014160`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014105`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014160`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014463`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014463`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800141b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800141f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800141b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800141f0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800141c1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800141c1`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x1800140fb`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x1800140fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800140d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800140d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014445`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014445`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014226`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014226`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001414d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001414d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014414`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014472`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014414`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014472`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180014368`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180014368`
- `RPCRT4!RpcSmDestroyClientContext` at `0x1800143fd`
- `RPCRT4!RpcSmDestroyClientContext` at `0x1800143fd`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800500c0`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800500dc`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800500c0`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800500dc`

## pseudocode

```c
__int64 __fastcall ScNotifyServiceStatusChange(struct SC_HANDLE__ *a1, int a2, int a3, struct _SERVICE_NOTIFY_2W *a4)
{
  char *v7; // rsi
  const WCHAR *pfnNotifyCallback; // rdx
  DWORD LastError; // edi
  char *v10; // rax
  struct _SERVICE_NOTIFY_2W *v11; // r14
  bool v12; // cf
  DWORD CurrentThreadId; // eax
  unsigned int v14; // eax
  __int64 v15; // r13
  struct _SCC_SERVER_NOTIFY_LIST *v16; // rdx
  char *v17; // rax
  struct _SCC_SERVER_NOTIFY_LIST **v18; // rcx
  struct _SCC_SERVER_NOTIFY_LIST *v19; // r8
  int v20; // eax
  struct _FILETIME ExitTime; // [rsp+40h] [rbp-158h]
  HANDLE v23; // [rsp+48h] [rbp-150h]
  int v24; // [rsp+50h] [rbp-148h] BYREF
  int v25; // [rsp+54h] [rbp-144h] BYREF
  int v26; // [rsp+58h] [rbp-140h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-138h]
  char *v28; // [rsp+68h] [rbp-130h]
  int v29; // [rsp+70h] [rbp-128h]
  HMODULE phModule; // [rsp+78h] [rbp-120h] BYREF
  struct _SERVICE_NOTIFY_2W *v31; // [rsp+80h] [rbp-118h]
  struct _SCC_SERVER_NOTIFY_LIST *v32; // [rsp+88h] [rbp-110h] BYREF
  __int128 v33; // [rsp+90h] [rbp-108h] BYREF
  struct SC_HANDLE__ *v34; // [rsp+A0h] [rbp-F8h]
  struct _SCC_SERVER_NOTIFY_LIST *v35; // [rsp+A8h] [rbp-F0h]
  struct _SCC_SERVER_NOTIFY_LIST ***v36; // [rsp+B0h] [rbp-E8h]
  __int128 v37; // [rsp+C0h] [rbp-D8h]
  _FILETIME CreationTime[2]; // [rsp+D0h] [rbp-C8h] BYREF
  UUID Uuid; // [rsp+E0h] [rbp-B8h] BYREF
  __int64 v40; // [rsp+F0h] [rbp-A8h] BYREF
  int v41; // [rsp+F8h] [rbp-A0h]
  void (__stdcall *v42)(PVOID, PVOID, PVOID); // [rsp+FCh] [rbp-9Ch]
  char *v43; // [rsp+10Ch] [rbp-8Ch]
  unsigned int v44; // [rsp+144h] [rbp-54h]

  LODWORD(v23) = a2;
  *(_QWORD *)&v33 = a1;
  v34 = a1;
  v31 = a4;
  v7 = 0;
  hObject = 0;
  DWORD1(v37) = 0;
  memset_0(&v40, 0, 0x68u);
  Uuid = 0;
  v32 = 0;
  v25 = 0;
  v26 = 1;
  v24 = 0;
  phModule = 0;
  CreationTime[0].dwLowDateTime = 0;
  *(_QWORD *)&CreationTime[0].dwHighDateTime = 0;
  CreationTime[1].dwHighDateTime = 0;
  if ( !a1
    || (a3 & 0x3FF) == 0
    || (a3 & 0x27F) != 0 && (a3 & 0x180) != 0
    || !a4
    || a4->dwVersion - 1 > 1
    || a4->dwVersion < 2 && (a3 & 0x180) != 0
    || (pfnNotifyCallback = (const WCHAR *)a4->pfnNotifyCallback) == 0 )
  {
    LastError = 87;
    goto LABEL_34;
  }
  if ( !GetModuleHandleExW(4u, pfnNotifyCallback, &phModule) )
  {
    LastError = GetLastError();
    if ( LastError != 126 )
    {
LABEL_34:
      if ( !LastError )
        goto LABEL_38;
      goto LABEL_35;
    }
  }
  a4->dwNotificationStatus = 0;
  *(_OWORD *)&a4->ServiceStatus.dwServiceType = 0;
  *(_OWORD *)&a4->ServiceStatus.dwServiceSpecificExitCode = 0;
  a4->ServiceStatus.dwServiceFlags = 0;
  LODWORD(v28) = 0;
  ExitTime = 0;
  LastError = ScCheckProtocol(L"ncalrpc");
  if ( !LastError )
  {
    *(GUID *)&CreationTime[0].dwLowDateTime = g_SccClientProcessGuid;
    LastError = ScInitializeNotify();
    if ( LastError )
      goto LABEL_34;
    v10 = (char *)LocalAlloc(0x40u, 0x48u);
    v7 = v10;
    ExitTime = (struct _FILETIME)v10;
    if ( !v10 )
      goto LABEL_15;
    *(_DWORD *)v10 = 1802265198;
    v11 = (struct _SERVICE_NOTIFY_2W *)(v10 + 4);
    v28 = v10 + 4;
    v12 = (_DWORD)v23 != 0;
    LODWORD(v23) = -(int)v23;
    *((_DWORD *)v10 + 1) |= v12 ? 4 : 0;
    *((_DWORD *)v10 + 1) |= phModule == 0 ? 8 : 0;
    v35 = (struct _SCC_SERVER_NOTIFY_LIST *)(v10 + 16);
    v36 = (struct _SCC_SERVER_NOTIFY_LIST ***)(v10 + 24);
    *((_QWORD *)v10 + 3) = v10 + 16;
    *((_QWORD *)v10 + 2) = v10 + 16;
    CurrentThreadId = GetCurrentThreadId();
    hObject = OpenThread(0x10u, 0, CurrentThreadId);
    v23 = hObject;
    if ( !hObject )
    {
LABEL_15:
      LastError = GetLastError();
      goto LABEL_34;
    }
    LODWORD(v37) = a4->dwVersion;
    *((_QWORD *)&v37 + 1) = &v40;
    v40 = GetCurrentThreadId();
    v41 = a3;
    v42 = ScApcNotifyCallback;
    v43 = v7;
    EnterCriticalSection(&SccCritsec);
    v14 = g_dwNotifyBlockSequence;
    *((_DWORD *)v7 + 16) = g_dwNotifyBlockSequence;
    v44 = v14;
    g_dwNotifyBlockSequence = v14 + 1;
    v11->dwVersion |= 1u;
    v15 = v33;
    v33 = v37;
    LastError = RNotifyServiceStatusChange(
                  v15,
                  (unsigned int)&v33,
                  (unsigned int)CreationTime,
                  (unsigned int)&Uuid,
                  (__int64)&v24,
                  (__int64)(v7 + 48));
    v31 = v11;
    v11->dwVersion &= ~1u;
    if ( !LastError )
    {
      LastError = ScGetNotifyList(&Uuid, (struct _SCC_NOTIFY_BLOCK *)v7, v24, &v32, &v25);
      if ( LastError )
      {
LABEL_23:
        v11->dwVersion |= 1u;
        v20 = RCloseNotifyHandle(v7 + 48, &v26);
        v29 = v20;
        v11->dwVersion &= ~1u;
        if ( v20 )
          RpcSmDestroyClientContext((void **)v7 + 6);
        *((_QWORD *)v7 + 6) = 0;
        if ( LastError && !v26 )
        {
          LocalFree(v7);
          goto LABEL_31;
        }
LABEL_28:
        if ( !v7 || (v7[4] & 2) == 0 )
          goto LABEL_32;
        ScApcNotifyCallback(v7, 0, 0);
LABEL_31:
        v7 = 0;
LABEL_32:
        LeaveCriticalSection(&SccCritsec);
        goto LABEL_34;
      }
      v16 = v32;
      v17 = (char *)v32 + 8;
      v18 = (struct _SCC_SERVER_NOTIFY_LIST **)*((_QWORD *)v32 + 2);
      if ( *v18 != (struct _SCC_SERVER_NOTIFY_LIST *)((char *)v32 + 8) )
        __fastfail(LastError + 3);
      v19 = v35;
      *(_QWORD *)v35 = v17;
      *v36 = v18;
      *v18 = v19;
      *((_QWORD *)v17 + 1) = v19;
      *((_QWORD *)v7 + 4) = v16;
      *((_QWORD *)v7 + 5) = v15;
      *((_QWORD *)v7 + 1) = a4;
      *((_QWORD *)v7 + 7) = hObject;
    }
    if ( v25 != 1 )
      goto LABEL_28;
    goto LABEL_23;
  }
LABEL_35:
  if ( hObject )
    CloseHandle(hObject);
  LocalFree(v7);
LABEL_38:
  if ( phModule )
    FreeLibrary(phModule);
  return LastError;
}

```

## disassembly

```asm
0x180013f34  mov     [rsp+arg_8], rbx
0x180013f39  mov     [rsp+arg_10], rsi
0x180013f3e  push    rdi
0x180013f3f  push    r12
0x180013f41  push    r13
0x180013f43  push    r14
0x180013f45  push    r15
0x180013f47  sub     rsp, 170h
0x180013f4e  mov     rax, cs:__security_cookie
0x180013f55  xor     rax, rsp
0x180013f58  mov     [rsp+198h+var_38], rax
0x180013f60  mov     r15, r9
0x180013f63  mov     r13d, r8d
0x180013f66  mov     dword ptr [rsp+198h+var_150], edx
0x180013f6a  mov     r14, rcx
0x180013f6d  mov     qword ptr [rsp+198h+var_108], rcx
0x180013f75  mov     [rsp+198h+var_F8], rcx
0x180013f7d  mov     [rsp+198h+var_118], r9
0x180013f85  xor     ebx, ebx
0x180013f87  mov     esi, ebx
0x180013f89  mov     [rsp+198h+hObject], rbx
0x180013f8e  mov     dword ptr [rsp+198h+var_D8+4], ebx
0x180013f95  xor     edx, edx; Val
0x180013f97  lea     r8d, [rbx+68h]; Size
0x180013f9b  lea     rcx, [rsp+198h+var_A8]; void *
0x180013fa3  call    memset_0
0x180013fa8  xorps   xmm0, xmm0
0x180013fab  movups  xmmword ptr [rsp+198h+Uuid.Data1], xmm0
0x180013fb3  mov     [rsp+198h+var_110], rbx
0x180013fbb  mov     [rsp+198h+var_144], ebx
0x180013fbf  mov     [rsp+198h+var_140], 1
0x180013fc7  mov     [rsp+198h+var_148], ebx
0x180013fcb  mov     [rsp+198h+phModule], rbx
0x180013fd0  mov     [rsp+198h+CreationTime.dwLowDateTime], ebx
0x180013fd7  xor     eax, eax
0x180013fd9  mov     qword ptr [rsp+198h+CreationTime.dwHighDateTime], rax
0x180013fe1  mov     [rsp+198h+CreationTime.dwHighDateTime+8], eax
0x180013fe8  mov     [rsp+198h+var_168], 1
0x180013fed  test    r14, r14
0x180013ff0  jz      loc_18001444D
0x180013ff6  test    r13d, 3FFh
0x180013ffd  jz      loc_18001444D
0x180014003  mov     ecx, r13d
0x180014006  and     ecx, 180h
0x18001400c  test    r13d, 27Fh
0x180014013  jz      short loc_18001401D
0x180014015  test    ecx, ecx
0x180014017  jnz     loc_18001444D
0x18001401d  test    r15, r15
0x180014020  jz      loc_18001444D
0x180014026  mov     edx, [r15]
0x180014029  lea     eax, [rdx-1]
0x18001402c  cmp     eax, 1
0x18001402f  ja      loc_18001444D
0x180014035  cmp     edx, 2
0x180014038  jnb     short loc_180014042
0x18001403a  test    ecx, ecx
0x18001403c  jnz     loc_18001444D
0x180014042  mov     rdx, [r15+8]; lpModuleName
0x180014046  test    rdx, rdx
0x180014049  jz      loc_18001444D
0x18001404f  lea     r8, [rsp+198h+phModule]; phModule
0x180014054  mov     ecx, 4; dwFlags
0x180014059  call    cs:__imp_GetModuleHandleExW
0x18001405f  test    eax, eax
0x180014061  jnz     short loc_180014074
0x180014063  call    cs:__imp_GetLastError
0x180014069  mov     edi, eax
0x18001406b  cmp     eax, 7Eh ; '~'
0x18001406e  jnz     loc_180014452
0x180014074  mov     r12d, ebx
0x180014077  mov     [rsp+198h+var_160], ebx
0x18001407b  mov     [r15+18h], ebx
0x18001407f  xorps   xmm0, xmm0
0x180014082  xor     eax, eax
0x180014084  movups  xmmword ptr [r15+1Ch], xmm0
0x180014089  movups  xmmword ptr [r15+2Ch], xmm0
0x18001408e  mov     [r15+3Ch], eax
0x180014092  mov     dword ptr [rsp+198h+var_130], ebx
0x180014096  mov     qword ptr [rsp+198h+ExitTime.dwLowDateTime], rbx
0x18001409b  lea     r9, [rsp+198h+var_130]
0x1800140a0  mov     r8, r14
0x1800140a3  lea     rcx, Protseq; "ncalrpc"
0x1800140aa  call    ScCheckProtocol
0x1800140af  mov     edi, eax
0x1800140b1  test    eax, eax
0x1800140b3  jnz     short loc_18001410D
0x1800140b5  mov     r12d, dword ptr [rsp+198h+var_130]
0x1800140ba  mov     [rsp+198h+var_160], r12d
0x1800140bf  test    r12d, r12d
0x1800140c2  jnz     short loc_1800140D6
0x1800140c4  movups  xmm0, xmmword ptr cs:?g_SccClientProcessGuid@@3U_GUID@@A.Data1; _GUID g_SccClientProcessGuid ...
0x1800140cb  movdqu  xmmword ptr [rsp+198h+CreationTime.dwLowDateTime], xmm0
0x1800140d4  jmp     short loc_18001410D
0x1800140d6  call    cs:__imp_GetCurrentProcess
0x1800140dc  mov     rcx, rax; hProcess
0x1800140df  lea     rax, [rsp+198h+ExitTime]
0x1800140e4  mov     [rsp+198h+lpUserTime], rax; lpUserTime
0x1800140e9  lea     r9, [rsp+198h+ExitTime]; lpKernelTime
0x1800140ee  lea     r8, [rsp+198h+ExitTime]; lpExitTime
0x1800140f3  lea     rdx, [rsp+198h+CreationTime]; lpCreationTime
0x1800140fb  call    cs:__imp_GetProcessTimes
0x180014101  test    eax, eax
0x180014103  jnz     short loc_18001410D
0x180014105  call    cs:__imp_GetLastError
0x18001410b  mov     edi, eax
0x18001410d  test    edi, edi
0x18001410f  jnz     loc_180014456
0x180014115  test    r12d, r12d
0x180014118  jz      short loc_180014138
0x18001411a  test    r13d, 0FFFFFD80h
0x180014121  jnz     short loc_180014138
0x180014123  mov     r8, r15; struct _SERVICE_NOTIFY_2W *
0x180014126  mov     edx, r13d; unsigned int
0x180014129  mov     rcx, r14; struct SC_HANDLE__ *
0x18001412c  call    ?ScNotifyServiceStatusChangeLight@@YAKPEAUSC_HANDLE__@@KPEAU_SERVICE_NOTIFY_2W@@@Z; ScNotifyServiceStatusChangeLight(SC_HANDLE__ *,ulong,_SERVICE_NOTIFY_2W *)
0x180014131  mov     edi, eax
0x180014133  jmp     loc_180014452
0x180014138  call    ?ScInitializeNotify@@YAKXZ; ScInitializeNotify(void)
0x18001413d  mov     edi, eax
0x18001413f  test    eax, eax
0x180014141  jnz     loc_180014452
0x180014147  lea     edx, [rax+48h]; uBytes
0x18001414a  lea     ecx, [rax+40h]; uFlags
0x18001414d  call    cs:__imp_LocalAlloc
0x180014153  mov     rsi, rax
0x180014156  mov     qword ptr [rsp+198h+ExitTime.dwLowDateTime], rax
0x18001415b  test    rax, rax
0x18001415e  jnz     short loc_180014168
0x180014160  call    cs:__imp_GetLastError
0x180014166  jmp     short loc_180014131
0x180014168  mov     dword ptr [rax], 6B6C626Eh
0x18001416e  lea     r14, [rax+4]
0x180014172  mov     [rsp+198h+var_130], r14
0x180014177  neg     dword ptr [rsp+198h+var_150]
0x18001417b  sbb     eax, eax
0x18001417d  and     eax, 4
0x180014180  or      [r14], eax
0x180014183  mov     rax, [rsp+198h+phModule]
0x180014188  neg     rax
0x18001418b  sbb     ecx, ecx
0x18001418d  not     ecx
0x18001418f  and     ecx, 8
0x180014192  or      [r14], ecx
0x180014195  lea     rax, [rsi+10h]
0x180014199  mov     [rsp+198h+var_F0], rax
0x1800141a1  lea     rcx, [rax+8]
0x1800141a5  mov     [rsp+198h+var_E8], rcx
0x1800141ad  mov     [rcx], rax
0x1800141b0  mov     [rax], rax
0x1800141b3  call    cs:__imp_GetCurrentThreadId
0x1800141b9  mov     r8d, eax; dwThreadId
0x1800141bc  xor     edx, edx; bInheritHandle
0x1800141be  lea     ecx, [rdx+10h]; dwDesiredAccess
0x1800141c1  call    cs:__imp_OpenThread
0x1800141c7  mov     [rsp+198h+hObject], rax
0x1800141cc  mov     [rsp+198h+var_150], rax
0x1800141d1  test    rax, rax
0x1800141d4  jz      short loc_180014160
0x1800141d6  mov     eax, [r15]
0x1800141d9  mov     dword ptr [rsp+198h+var_D8], eax
0x1800141e0  lea     rax, [rsp+198h+var_A8]
0x1800141e8  mov     qword ptr [rsp+198h+var_D8+8], rax
0x1800141f0  call    cs:__imp_GetCurrentThreadId
0x1800141f6  mov     eax, eax
0x1800141f8  mov     [rsp+198h+var_A8], rax
0x180014200  mov     [rsp+198h+var_A0], r13d
0x180014208  lea     rax, ?ScApcNotifyCallback@@YAXPEAX00@Z; ScApcNotifyCallback(void *,void *,void *)
0x18001420f  mov     [rsp+198h+var_9C], rax
0x180014217  mov     [rsp+198h+var_8C], rsi
0x18001421f  lea     rcx, ?SccCritsec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180014226  call    cs:__imp_EnterCriticalSection
0x18001422c  mov     eax, cs:?g_dwNotifyBlockSequence@@3KA; ulong g_dwNotifyBlockSequence
0x180014232  mov     [rsi+40h], eax
0x180014235  mov     [rsp+198h+var_54], eax
0x18001423c  inc     eax
0x18001423e  mov     cs:?g_dwNotifyBlockSequence@@3KA, eax; ulong g_dwNotifyBlockSequence
0x180014244  or      dword ptr [r14], 1
0x180014248  mov     r13, qword ptr [rsp+198h+var_108]
0x180014250  movaps  xmm0, [rsp+198h+var_D8]
0x180014258  movdqa  [rsp+198h+var_108], xmm0
0x180014261  lea     rax, [rsi+30h]
0x180014265  mov     [rsp+198h+var_170], rax
0x18001426a  lea     rax, [rsp+198h+var_148]
0x18001426f  mov     [rsp+198h+lpUserTime], rax
0x180014274  lea     r9, [rsp+198h+Uuid]
0x18001427c  lea     r8, [rsp+198h+CreationTime]
0x180014284  lea     rdx, [rsp+198h+var_108]
0x18001428c  mov     rcx, r13
0x18001428f  call    RNotifyServiceStatusChange
0x180014294  mov     edi, eax
0x180014296  mov     [rsp+198h+var_164], eax
0x18001429a  jmp     short loc_1800142D4
0x18001429c  mov     ecx, eax; unsigned int
0x18001429e  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x1800142a3  mov     edi, eax
0x1800142a5  mov     [rsp+198h+var_164], eax
0x1800142a9  xor     ebx, ebx
0x1800142ab  mov     rsi, qword ptr [rsp+198h+ExitTime.dwLowDateTime]
0x1800142b0  mov     rax, [rsp+198h+var_150]
0x1800142b5  mov     [rsp+198h+hObject], rax
0x1800142ba  mov     r12d, [rsp+198h+var_160]
0x1800142bf  mov     r13, [rsp+198h+var_F8]
0x1800142c7  mov     r15, [rsp+198h+var_118]
0x1800142cf  mov     r14, [rsp+198h+var_130]
0x1800142d4  test    r12d, r12d
0x1800142d7  jz      short loc_180014304
0x1800142d9  cmp     edi, 8
0x1800142dc  jz      loc_180014363
0x1800142e2  cmp     edi, 0Eh
0x1800142e5  jz      short loc_180014363
0x1800142e7  cmp     edi, 6B9h
0x1800142ed  jz      short loc_180014363
0x1800142ef  cmp     edi, 7DEh
0x1800142f5  jnz     short loc_180014304
0x1800142f7  mov     edi, 0Eh
0x1800142fc  mov     [rsp+198h+var_164], edi
0x180014300  mov     [rsp+198h+var_168], bl
0x180014304  mov     [rsp+198h+var_118], r14
0x18001430c  and     dword ptr [r14], 0FFFFFFFEh
0x180014310  test    edi, edi
0x180014312  jnz     loc_1800143A5
0x180014318  lea     rax, [rsp+198h+var_144]
0x18001431d  mov     [rsp+198h+lpUserTime], rax; int *
0x180014322  lea     r9, [rsp+198h+var_110]; struct _SCC_SERVER_NOTIFY_LIST **
0x18001432a  mov     r8d, [rsp+198h+var_148]; int
0x18001432f  mov     rdx, rsi; struct _SCC_NOTIFY_BLOCK *
0x180014332  lea     rcx, [rsp+198h+Uuid]; Uuid
0x18001433a  call    ?ScGetNotifyList@@YAKPEAU_GUID@@PEAU_SCC_NOTIFY_BLOCK@@HPEAPEAU_SCC_SERVER_NOTIFY_LIST@@PEAH@Z; ScGetNotifyList(_GUID *,_SCC_NOTIFY_BLOCK *,int,_SCC_SERVER_NOTIFY_LIST * *,int *)
0x18001433f  mov     edi, eax
0x180014341  mov     [rsp+198h+var_164], eax
0x180014345  test    eax, eax
0x180014347  jnz     short loc_1800143AC
0x180014349  mov     rdx, [rsp+198h+var_110]
0x180014351  lea     rax, [rdx+8]
0x180014355  mov     rcx, [rax+8]
0x180014359  cmp     [rcx], rax
0x18001435c  jz      short loc_180014373
0x18001435e  lea     ecx, [rdi+3]
0x180014361  int     29h; Win8: RtlFailFast(ecx)
0x180014363  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180014368  call    cs:__imp_Sleep
0x18001436e  jmp     loc_180014250
0x180014373  mov     r8, [rsp+198h+var_F0]
0x18001437b  mov     [r8], rax
0x18001437e  mov     r9, [rsp+198h+var_E8]
0x180014386  mov     [r9], rcx
0x180014389  mov     [rcx], r8
0x18001438c  mov     [rax+8], r8
0x180014390  mov     [rsi+20h], rdx
0x180014394  mov     [rsi+28h], r13
0x180014398  mov     [rsi+8], r15
0x18001439c  mov     rcx, [rsp+198h+hObject]
0x1800143a1  mov     [rsi+38h], rcx
0x1800143a5  cmp     [rsp+198h+var_144], 1
0x1800143aa  jnz     short loc_180014423
0x1800143ac  or      dword ptr [r14], 1
0x1800143b0  lea     rcx, [rsi+30h]
0x1800143b4  lea     rdx, [rsp+198h+var_140]
0x1800143b9  call    RCloseNotifyHandle
0x1800143be  mov     [rsp+198h+var_128], eax
0x1800143c2  jmp     short loc_1800143F1
0x1800143c4  mov     ecx, eax; unsigned int
0x1800143c6  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x1800143cb  mov     [rsp+198h+var_128], eax
0x1800143cf  xor     ebx, ebx
0x1800143d1  mov     edi, [rsp+198h+var_164]
0x1800143d5  mov     rsi, qword ptr [rsp+198h+ExitTime.dwLowDateTime]
0x1800143da  mov     rcx, [rsp+198h+var_150]
0x1800143df  mov     [rsp+198h+hObject], rcx
0x1800143e4  mov     r12d, [rsp+198h+var_160]
0x1800143e9  mov     r14, [rsp+198h+var_118]
0x1800143f1  and     dword ptr [r14], 0FFFFFFFEh
0x1800143f5  test    eax, eax
0x1800143f7  jz      short loc_180014403
0x1800143f9  lea     rcx, [rsi+30h]; ContextHandle
0x1800143fd  call    cs:__imp_RpcSmDestroyClientContext
0x180014403  mov     [rsi+30h], rbx
0x180014407  test    edi, edi
0x180014409  jz      short loc_180014423
0x18001440b  cmp     [rsp+198h+var_140], ebx
0x18001440f  jnz     short loc_18001441C
0x180014411  mov     rcx, rsi; hMem
0x180014414  call    cs:__imp_LocalFree
0x18001441a  jmp     short loc_18001443B
0x18001441c  test    r12d, r12d
0x18001441f  cmovnz  rsi, rbx
0x180014423  test    rsi, rsi
0x180014426  jz      short loc_18001443E
0x180014428  test    byte ptr [rsi+4], 2
0x18001442c  jz      short loc_18001443E
0x18001442e  xor     r8d, r8d; SystemArgument2
0x180014431  xor     edx, edx; SystemArgument1
0x180014433  mov     rcx, rsi; NormalContext
0x180014436  call    ?ScApcNotifyCallback@@YAXPEAX00@Z; ScApcNotifyCallback(void *,void *,void *)
0x18001443b  mov     rsi, rbx
0x18001443e  lea     rcx, ?SccCritsec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180014445  call    cs:__imp_LeaveCriticalSection
0x18001444b  jmp     short loc_180014452
0x18001444d  mov     edi, 57h ; 'W'
  ... truncated ...
```
