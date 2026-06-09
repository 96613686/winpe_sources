# PfXpProcessIdleTasks

- ea: `0x1800959a0`
- end: `0x180095b99`
- name: `PfXpProcessIdleTasks`
- size: `505`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180018ec0`
- `0x180069fa4`
- `0x1800959a0`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180095b45`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180095b45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180095b6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180095b6a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180095a5b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180095a5b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800959e6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800959e6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180095b35`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180095b35`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180095b28`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180095b28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095b78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095b78`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180095a9e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180095a9e`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x1800959d9`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x1800959d9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180095b61`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180095b61`

## pseudocode

```c
void __fastcall PfXpProcessIdleTasks(
        PTP_CALLBACK_INSTANCE Instance,
        struct _RTL_CRITICAL_SECTION *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  void *v6; // rdi
  int v7; // eax
  DWORD v8; // r15d
  unsigned int v9; // r14d
  unsigned int i; // esi
  HANDLE Handles[2]; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v12[24]; // [rsp+40h] [rbp-20h] BYREF

  memset(v12, 0, sizeof(v12));
  *(_OWORD *)Handles = 0;
  v6 = 0;
  CallbackMayRunLong(Instance);
  ResetEvent(Context[8].OwningThread);
  *(_QWORD *)&v12[12] = 0;
  *(_QWORD *)v12 = 0x1000000001LL;
  *(_DWORD *)&v12[8] = 8;
  v7 = PfSvServiceCommandSend(*(_QWORD *)&PfSvcGlobals + 1616LL, v12, 24);
  v8 = v7 == 0 ? 0x3E8 : 0;
  v9 = v7 == 0 ? 0x12C : 0;
  for ( i = 0; i < v9; ++i )
  {
    if ( !WaitForSingleObject(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 880LL), v8) )
      goto LABEL_11;
    *(_QWORD *)&v12[4] = 0x1000000010LL;
    if ( (unsigned int)PfSvServiceCommandSend(*(_QWORD *)&PfSvcGlobals + 1616LL, v12, 24) || *(_QWORD *)&v12[16] == -1 )
      break;
  }
  LODWORD(Context[3].SpinCount) = GetTickCount();
  if ( !(unsigned int)PfXpUpdateOptimalLayout(0) )
  {
    *(_QWORD *)&v12[8] = 1;
    *(_QWORD *)v12 = 0x20000000000001LL;
    *(_QWORD *)&v12[16] = 1;
    if ( !(unsigned int)PfSvServiceCommandSend(*(_QWORD *)&PfSvcGlobals + 1616LL, v12, 24) )
    {
      if ( *(_QWORD *)&v12[16] )
      {
        v6 = *(void **)&v12[16];
        Handles[1] = *(HANDLE *)&v12[16];
        Handles[0] = *(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 880LL);
        WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
      }
    }
  }
LABEL_11:
  SetEvent(Context[8].LockSemaphore);
  EnterCriticalSection(Context + 7);
  if ( ((__int64)Context[8].DebugInfo & 2) == 0 )
    SetThreadpoolWait(Wait, Context[8].OwningThread, 0);
  LeaveCriticalSection(Context + 7);
  if ( v6 )
    CloseHandle(v6);
}

```

## disassembly

```asm
0x1800959a0  push    rbp
0x1800959a2  push    rbx
0x1800959a3  push    rsi
0x1800959a4  push    rdi
0x1800959a5  push    r12
0x1800959a7  push    r14
0x1800959a9  push    r15
0x1800959ab  mov     rbp, rsp
0x1800959ae  sub     rsp, 60h
0x1800959b2  mov     rax, cs:__security_cookie
0x1800959b9  xor     rax, rsp
0x1800959bc  mov     [rbp+var_8], rax
0x1800959c0  xorps   xmm0, xmm0
0x1800959c3  xor     eax, eax
0x1800959c5  movups  [rbp+var_20], xmm0
0x1800959c9  mov     [rbp+var_10], rax
0x1800959cd  mov     r12, r8
0x1800959d0  movups  xmmword ptr [rbp+Handles], xmm0
0x1800959d4  mov     rbx, rdx
0x1800959d7  xor     edi, edi
0x1800959d9  call    cs:__imp_CallbackMayRunLong
0x1800959df  mov     rcx, [rbx+150h]; hEvent
0x1800959e6  call    cs:__imp_ResetEvent
0x1800959ec  mov     rcx, cs:PfSvcGlobals
0x1800959f3  lea     r8d, [rdi+18h]
0x1800959f7  add     rcx, 650h
0x1800959fe  mov     qword ptr [rbp+var_20+0Ch], rdi
0x180095a02  lea     rdx, [rbp+var_20]
0x180095a06  mov     dword ptr [rbp+var_10+4], edi
0x180095a09  mov     dword ptr [rbp+var_20], 1
0x180095a10  mov     dword ptr [rbp+var_20+4], 10h
0x180095a17  mov     dword ptr [rbp+var_20+8], 8
0x180095a1e  call    PfSvServiceCommandSend
0x180095a23  mov     ecx, eax
0x180095a25  neg     ecx
0x180095a27  sbb     r15d, r15d
0x180095a2a  not     r15d
0x180095a2d  and     r15d, 3E8h
0x180095a34  neg     eax
0x180095a36  sbb     r14d, r14d
0x180095a39  not     r14d
0x180095a3c  and     r14d, 12Ch
0x180095a43  xor     esi, esi
0x180095a45  cmp     esi, r14d
0x180095a48  jnb     short loc_180095A9E
0x180095a4a  mov     rcx, cs:PfSvcGlobals
0x180095a51  mov     edx, r15d; dwMilliseconds
0x180095a54  mov     rcx, [rcx+370h]; hHandle
0x180095a5b  call    cs:__imp_WaitForSingleObject
0x180095a61  test    eax, eax
0x180095a63  jz      loc_180095B2E
0x180095a69  mov     rcx, cs:PfSvcGlobals
0x180095a70  lea     rdx, [rbp+var_20]
0x180095a74  mov     eax, 10h
0x180095a79  add     rcx, 650h
0x180095a80  mov     dword ptr [rbp+var_20+4], eax
0x180095a83  mov     dword ptr [rbp+var_20+8], eax
0x180095a86  lea     r8d, [rax+8]
0x180095a8a  call    PfSvServiceCommandSend
0x180095a8f  test    eax, eax
0x180095a91  jnz     short loc_180095A9E
0x180095a93  cmp     [rbp+var_10], 0FFFFFFFFFFFFFFFFh
0x180095a98  jz      short loc_180095A9E
0x180095a9a  inc     esi
0x180095a9c  jmp     short loc_180095A45
0x180095a9e  call    cs:__imp_GetTickCount
0x180095aa4  xor     ecx, ecx
0x180095aa6  mov     [rbx+98h], eax
0x180095aac  call    PfXpUpdateOptimalLayout
0x180095ab1  test    eax, eax
0x180095ab3  jnz     short loc_180095B2E
0x180095ab5  mov     rcx, cs:PfSvcGlobals
0x180095abc  lea     rdx, [rbp+var_20]
0x180095ac0  mov     eax, 1
0x180095ac5  mov     qword ptr [rbp+var_20+8], 1
0x180095acd  add     rcx, 650h
0x180095ad4  mov     dword ptr [rbp+var_20], eax
0x180095ad7  mov     dword ptr [rbp+var_20+4], 200000h
0x180095ade  mov     [rbp+var_10], rax
0x180095ae2  lea     r8d, [rax+17h]
0x180095ae6  call    PfSvServiceCommandSend
0x180095aeb  test    eax, eax
0x180095aed  jnz     short loc_180095B2E
0x180095aef  mov     rax, [rbp+var_10]
0x180095af3  test    rax, rax
0x180095af6  jz      short loc_180095B2E
0x180095af8  mov     rdi, rax
0x180095afb  mov     [rsp+60h+bAlertable], 0; bAlertable
0x180095b03  mov     rax, cs:PfSvcGlobals
0x180095b0a  lea     rdx, [rbp+Handles]; lpHandles
0x180095b0e  xor     r8d, r8d; bWaitAll
0x180095b11  mov     [rbp+Handles+8], rdi
0x180095b15  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180095b19  mov     rcx, [rax+370h]
0x180095b20  mov     [rbp+Handles], rcx
0x180095b24  lea     ecx, [r8+2]; nCount
0x180095b28  call    cs:__imp_WaitForMultipleObjectsEx
0x180095b2e  mov     rcx, [rbx+158h]; hEvent
0x180095b35  call    cs:__imp_SetEvent
0x180095b3b  lea     rsi, [rbx+118h]
0x180095b42  mov     rcx, rsi; lpCriticalSection
0x180095b45  call    cs:__imp_EnterCriticalSection
0x180095b4b  test    byte ptr [rbx+140h], 2
0x180095b52  jnz     short loc_180095B67
0x180095b54  mov     rdx, [rbx+150h]; h
0x180095b5b  xor     r8d, r8d; pftTimeout
0x180095b5e  mov     rcx, r12; pwa
0x180095b61  call    cs:__imp_SetThreadpoolWait
0x180095b67  mov     rcx, rsi; lpCriticalSection
0x180095b6a  call    cs:__imp_LeaveCriticalSection
0x180095b70  test    rdi, rdi
0x180095b73  jz      short loc_180095B7E
0x180095b75  mov     rcx, rdi; hObject
0x180095b78  call    cs:__imp_CloseHandle
0x180095b7e  mov     rcx, [rbp+var_8]
0x180095b82  xor     rcx, rsp; StackCookie
0x180095b85  call    __security_check_cookie
0x180095b8a  add     rsp, 60h
0x180095b8e  pop     r15
0x180095b90  pop     r14
0x180095b92  pop     r12
0x180095b94  pop     rdi
0x180095b95  pop     rsi
0x180095b96  pop     rbx
0x180095b97  pop     rbp
0x180095b98  retn
```
