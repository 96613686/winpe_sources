# ScNotifyServiceStatusChangeLight(SC_HANDLE__ *,ulong,_SERVICE_NOTIFY_2W *)

- ea: `0x180010720`
- end: `0x18001094d`
- name: `?ScNotifyServiceStatusChangeLight@@YAKPEAUSC_HANDLE__@@KPEAU_SERVICE_NOTIFY_2W@@@Z`
- size: `557`
- prototype: `unsigned int __fastcall(struct SC_HANDLE__ *, unsigned int, struct _SERVICE_NOTIFY_2W *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180013f34`

## callees

- `0x180010720`
- `0x180010a80`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180010833`
- `ntdll!RtlNtStatusToDosError` at `0x180010833`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180010827`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180010827`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010942`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010942`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001076a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001076a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180010789`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180010789`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010842`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010842`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800107a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800107a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001074e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001074e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800108a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001090a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800108a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001090a`

## pseudocode

```c
__int64 __fastcall ScNotifyServiceStatusChangeLight(struct SC_HANDLE__ *a1, int a2, struct _SERVICE_NOTIFY_2W *a3)
{
  HLOCAL v5; // rsi
  char *v7; // rax
  char *v8; // rbx
  HANDLE v9; // rbp
  char *v10; // r13
  _DWORD *i; // rax
  ULONG LastError; // edi
  NTSTATUS v13; // eax
  char *v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rdx
  HLOCAL hMem; // [rsp+A8h] [rbp+20h] BYREF

  v5 = 0;
  hMem = 0;
  v7 = (char *)LocalAlloc(0x40u, 0x90u);
  v8 = v7;
  if ( !v7 )
    return GetLastError();
  *(_DWORD *)v7 = 825320275;
  *((_QWORD *)v7 + 5) = a1;
  *((_DWORD *)v7 + 12) = GetCurrentThreadId();
  *((_QWORD *)v8 + 2) = v8 + 8;
  *((_QWORD *)v8 + 1) = v8 + 8;
  v9 = OpenThread(0x100010u, 0, *((_DWORD *)v8 + 12));
  if ( v9 )
  {
    v10 = v8;
    EnterCriticalSection(&SccCritsec);
    for ( i = off_180079780; i != (_DWORD *)&off_180079780; i = *(_DWORD **)i )
    {
      if ( *((_QWORD *)i + 4) == *((_QWORD *)v8 + 5)
        && i[10] == *((_DWORD *)v8 + 12)
        && *((struct _SERVICE_NOTIFY_2W **)i + 8) == a3
        && !*((_QWORD *)i + 2) )
      {
        if ( i[29] )
        {
          LastError = 1072;
          goto LABEL_10;
        }
        v10 = (char *)(i - 2);
        if ( i[14] != a2 )
          i[6] = 0;
        break;
      }
    }
    LastError = I_ScQueryServiceConfig(a1, 3, &hMem);
    if ( LastError )
    {
      v5 = hMem;
    }
    else
    {
      v5 = hMem;
      v13 = RtlSubscribeWnfStateChangeNotification(
              v10 + 24,
              *(_QWORD *)hMem,
              *((unsigned int *)v10 + 8),
              ScNotifyServiceStatusChangeCallback,
              v10,
              0,
              0,
              1);
      if ( v13 >= 0 )
      {
        v15 = 0;
        *((_QWORD *)v10 + 7) = v9;
        v9 = 0;
        *((_DWORD *)v10 + 16) = a2;
        *((_QWORD *)v10 + 9) = a3;
        if ( v10 != v8 )
          v15 = v8;
        v8 = v15;
        v16 = v10 + 8;
        if ( (_QWORD *)*v16 == v16 )
        {
          v17 = off_180079788;
          if ( *off_180079788 != (_UNKNOWN *)&off_180079780 )
            __fastfail(3u);
          *v16 = &off_180079780;
          *((_QWORD *)v10 + 2) = v17;
          *v17 = v16;
          off_180079788 = (_UNKNOWN **)(v10 + 8);
        }
      }
      else
      {
        LastError = RtlNtStatusToDosError(v13);
      }
    }
LABEL_10:
    LeaveCriticalSection(&SccCritsec);
    if ( !v8 )
      goto LABEL_11;
  }
  else
  {
    LastError = GetLastError();
  }
  LocalFree(v8);
LABEL_11:
  if ( v9 )
    CloseHandle(v9);
  if ( v5 )
    LocalFree(v5);
  return LastError;
}

```

## disassembly

```asm
0x180010720  push    rbx
0x180010722  push    rbp
0x180010723  push    rsi
0x180010724  push    rdi
0x180010725  push    r12
0x180010727  push    r13
0x180010729  push    r14
0x18001072b  push    r15
0x18001072d  sub     rsp, 48h
0x180010731  mov     r14d, edx
0x180010734  mov     rdi, rcx
0x180010737  xor     esi, esi
0x180010739  mov     edx, 90h; uBytes
0x18001073e  mov     ecx, 40h ; '@'; uFlags
0x180010743  mov     [rsp+88h+hMem], rsi
0x18001074b  mov     r15, r8
0x18001074e  call    cs:__imp_LocalAlloc
0x180010754  mov     rbx, rax
0x180010757  test    rax, rax
0x18001075a  jz      loc_1800108F2
0x180010760  mov     dword ptr [rax], 31316353h
0x180010766  mov     [rax+28h], rdi
0x18001076a  call    cs:__imp_GetCurrentThreadId
0x180010770  mov     [rbx+30h], eax
0x180010773  xor     edx, edx; bInheritHandle
0x180010775  lea     rax, [rbx+8]
0x180010779  mov     ecx, 100010h; dwDesiredAccess
0x18001077e  mov     [rax+8], rax
0x180010782  mov     [rax], rax
0x180010785  mov     r8d, [rbx+30h]; dwThreadId
0x180010789  call    cs:__imp_OpenThread
0x18001078f  mov     rbp, rax
0x180010792  test    rax, rax
0x180010795  jz      loc_1800108FF
0x18001079b  lea     rcx, ?SccCritsec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800107a2  mov     r13, rbx
0x1800107a5  call    cs:__imp_EnterCriticalSection
0x1800107ab  mov     rax, cs:off_180079780
0x1800107b2  lea     r12, off_180079780
0x1800107b9  nop     dword ptr [rax+00000000h]
0x1800107c0  cmp     rax, r12
0x1800107c3  jz      short loc_1800107D8
0x1800107c5  mov     rcx, [rbx+28h]
0x1800107c9  cmp     [rax+20h], rcx
0x1800107cd  jz      loc_180010872
0x1800107d3  mov     rax, [rax]
0x1800107d6  jmp     short loc_1800107C0
0x1800107d8  lea     r8, [rsp+88h+hMem]
0x1800107e0  mov     edx, 3
0x1800107e5  mov     rcx, rdi
0x1800107e8  call    I_ScQueryServiceConfig
0x1800107ed  mov     edi, eax
0x1800107ef  test    eax, eax
0x1800107f1  jnz     loc_180010932
0x1800107f7  mov     r8d, [r13+20h]
0x1800107fb  lea     rcx, [r13+18h]
0x1800107ff  mov     [rsp+88h+var_50], 1
0x180010807  lea     r9, ?ScNotifyServiceStatusChangeCallback@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; ScNotifyServiceStatusChangeCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18001080e  mov     [rsp+88h+var_58], esi
0x180010812  mov     [rsp+88h+var_60], rsi
0x180010817  mov     rsi, [rsp+88h+hMem]
0x18001081f  mov     [rsp+88h+var_68], r13
0x180010824  mov     rdx, [rsi]
0x180010827  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18001082d  test    eax, eax
0x18001082f  jns     short loc_1800108A9
0x180010831  mov     ecx, eax; Status
0x180010833  call    cs:__imp_RtlNtStatusToDosError
0x180010839  mov     edi, eax
0x18001083b  lea     rcx, ?SccCritsec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180010842  call    cs:__imp_LeaveCriticalSection
0x180010848  test    rbx, rbx
0x18001084b  jnz     loc_180010907
0x180010851  test    rbp, rbp
0x180010854  jnz     loc_18001093F
0x18001085a  test    rsi, rsi
0x18001085d  jnz     short loc_18001089E
0x18001085f  mov     eax, edi
0x180010861  add     rsp, 48h
0x180010865  pop     r15
0x180010867  pop     r14
0x180010869  pop     r13
0x18001086b  pop     r12
0x18001086d  pop     rdi
0x18001086e  pop     rsi
0x18001086f  pop     rbp
0x180010870  pop     rbx
0x180010871  retn
0x180010872  mov     ecx, [rbx+30h]
0x180010875  cmp     [rax+28h], ecx
0x180010878  jnz     loc_1800107D3
0x18001087e  cmp     [rax+40h], r15
0x180010882  jnz     loc_1800107D3
0x180010888  cmp     [rax+10h], rsi
0x18001088c  jnz     loc_1800107D3
0x180010892  cmp     [rax+74h], esi
0x180010895  jz      short loc_180010915
0x180010897  mov     edi, 430h
0x18001089c  jmp     short loc_18001083B
0x18001089e  mov     rcx, rsi; hMem
0x1800108a1  call    cs:__imp_LocalFree
0x1800108a7  jmp     short loc_18001085F
0x1800108a9  xor     eax, eax
0x1800108ab  mov     [r13+38h], rbp
0x1800108af  xor     ebp, ebp
0x1800108b1  mov     [r13+40h], r14d
0x1800108b5  cmp     r13, rbx
0x1800108b8  mov     [r13+48h], r15
0x1800108bc  cmovnz  rax, rbx
0x1800108c0  mov     rbx, rax
0x1800108c3  lea     rax, [r13+8]
0x1800108c7  cmp     [rax], rax
0x1800108ca  jnz     loc_18001083B
0x1800108d0  mov     rdx, cs:off_180079788
0x1800108d7  cmp     [rdx], r12
0x1800108da  jnz     short loc_18001092B
0x1800108dc  mov     [rax], r12
0x1800108df  mov     [rax+8], rdx
0x1800108e3  mov     [rdx], rax
0x1800108e6  mov     cs:off_180079788, rax
0x1800108ed  jmp     loc_18001083B
0x1800108f2  call    cs:__imp_GetLastError
0x1800108f8  mov     edi, eax
0x1800108fa  jmp     loc_18001085F
0x1800108ff  call    cs:__imp_GetLastError
0x180010905  mov     edi, eax
0x180010907  mov     rcx, rbx; hMem
0x18001090a  call    cs:__imp_LocalFree
0x180010910  jmp     loc_180010851
0x180010915  lea     r13, [rax-8]
0x180010919  cmp     [rax+38h], r14d
0x18001091d  jz      loc_1800107D8
0x180010923  mov     [rax+18h], esi
0x180010926  jmp     loc_1800107D8
0x18001092b  mov     ecx, 3
0x180010930  int     29h; Win8: RtlFailFast(ecx)
0x180010932  mov     rsi, [rsp+88h+hMem]
0x18001093a  jmp     loc_18001083B
0x18001093f  mov     rcx, rbp; hObject
0x180010942  call    cs:__imp_CloseHandle
0x180010948  jmp     loc_18001085A
```
