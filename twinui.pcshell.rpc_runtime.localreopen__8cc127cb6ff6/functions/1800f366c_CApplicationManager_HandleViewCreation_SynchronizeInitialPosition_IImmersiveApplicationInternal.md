# CApplicationManager::_HandleViewCreation_SynchronizeInitialPosition(IImmersiveApplicationInternal *)

- ea: `0x1800f366c`
- end: `0x1800f38f9`
- name: `?_HandleViewCreation_SynchronizeInitialPosition@CApplicationManager@@AEAAJPEAUIImmersiveApplicationInternal@@@Z`
- size: `653`
- prototype: `__int64 __fastcall(CApplicationManager *__hidden this, struct IImmersiveApplicationInternal *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180087240`

## callees

- `0x1800134f8`
- `0x1800f366c`
- `0x1800f4640`
- `0x1801d8e48`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f3693`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f3693`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800f3720`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800f3720`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f36c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f36c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800f3753`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800f38aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800f3753`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800f38aa`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x1800f377b`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x1800f377b`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800f37de`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800f3816`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800f37de`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800f3816`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f3761`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f3761`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800f37ae`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800f37ae`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800f37f3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800f382b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800f37f3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800f382b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800f38c4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800f38c4`
- `faultrep!ReportCoreHang` at `0x1800f38ed`
- `faultrep!ReportCoreHang` at `0x1800f38ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CApplicationManager::_HandleViewCreation_SynchronizeInitialPosition(
        CApplicationManager *this,
        struct IImmersiveApplicationInternal *a2)
{
  __int64 (__fastcall *v4)(struct IImmersiveApplicationInternal *, __int64 *); // rbx
  int v5; // edi
  __int64 v6; // rcx
  RTL_SRWLOCK *v8; // rbx
  __int64 (__fastcall *v9)(struct IImmersiveApplicationInternal *, __int64 *); // rdi
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // ebx
  DWORD WindowThreadProcessId; // eax
  HWND hWnd; // [rsp+40h] [rbp-20h] BYREF
  DWORD Parameter; // [rsp+48h] [rbp-18h] BYREF
  char v16; // [rsp+4Ch] [rbp-14h]
  HRESULT v17; // [rsp+50h] [rbp-10h]
  void *phNewTimer; // [rsp+58h] [rbp-8h] BYREF
  PSRWLOCK SRWLock; // [rsp+98h] [rbp+38h] BYREF
  __int64 v20; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v21; // [rsp+A8h] [rbp+48h] BYREF

  v21 = 0;
  AcquireSRWLockExclusive(CApplicationManagerUtility::g_pIAMGlobals);
  v4 = *(__int64 (__fastcall **)(struct IImmersiveApplicationInternal *, __int64 *))(*(_QWORD *)a2 + 504LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  v5 = v4(a2, &v21);
  ReleaseSRWLockExclusive(CApplicationManagerUtility::g_pIAMGlobals);
  if ( v5 >= 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 24LL))(v21);
    v20 = 0;
    v8 = CApplicationManagerUtility::g_pIAMGlobals;
    SRWLock = CApplicationManagerUtility::g_pIAMGlobals;
    AcquireSRWLockShared(CApplicationManagerUtility::g_pIAMGlobals);
    v9 = *(__int64 (__fastcall **)(struct IImmersiveApplicationInternal *, __int64 *))(*(_QWORD *)a2 + 496LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    v5 = v9(a2, &v20);
    if ( v8 )
      ReleaseSRWLockShared(v8);
    if ( v5 >= 0 )
    {
      Parameter = GetCurrentThreadId();
      v16 = 0;
      phNewTimer = 0;
      v17 = CoEnableCallCancellation(0);
      if ( v17 >= 0 )
        CreateTimerQueueTimer(&phNewTimer, 0, CBaseRPCTimeout::s_Callback, &Parameter, 0x2710u, 0x3E8u, 0);
      v5 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 176LL))(v20, 1);
      if ( v17 >= 0 )
      {
        v17 = -2147467259;
        CoDisableCallCancellation(0);
        if ( phNewTimer )
        {
          DeleteTimerQueueTimer(0, phNewTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
          phNewTimer = 0;
        }
      }
      if ( v16 )
      {
        hWnd = 0;
        CIAMGlobals::AcquireShared(v10, &SRWLock);
        v12 = (*(__int64 (__fastcall **)(__int64, HWND *))(*(_QWORD *)v20 + 24LL))(v20, &hWnd);
        if ( SRWLock )
          ReleaseSRWLockShared(SRWLock);
        if ( v12 >= 0 )
        {
          LODWORD(SRWLock) = 0;
          WindowThreadProcessId = GetWindowThreadProcessId(hWnd, (LPDWORD)&SRWLock);
          if ( (_DWORD)SRWLock )
          {
            if ( WindowThreadProcessId )
              ReportCoreHang(&SRWLock, 1, WindowThreadProcessId);
          }
        }
      }
      if ( v5 >= 0 )
        (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 76) + 88LL))(*((_QWORD *)this + 76), v20);
      if ( v17 >= 0 )
      {
        v17 = -2147467259;
        CoDisableCallCancellation(0);
        if ( phNewTimer )
          DeleteTimerQueueTimer(0, phNewTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      }
    }
    v11 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    if ( v5 >= 0 )
      CApplicationManager::UpdateMonitorForAppAsync(this, a2);
  }
  v6 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800f366c  mov     [rsp-28h+arg_0], rbx
0x1800f3671  push    rbp
0x1800f3672  push    rsi
0x1800f3673  push    rdi
0x1800f3674  push    r14
0x1800f3676  push    r15
0x1800f3678  mov     rbp, rsp
0x1800f367b  sub     rsp, 60h
0x1800f367f  mov     rsi, rdx
0x1800f3682  mov     r14, rcx
0x1800f3685  xor     r15d, r15d
0x1800f3688  mov     [rbp+arg_18], r15
0x1800f368c  mov     rcx, cs:?g_pIAMGlobals@CApplicationManagerUtility@@3PEAVCIAMGlobals@@EA; SRWLock
0x1800f3693  call    cs:__imp_AcquireSRWLockExclusive
0x1800f3699  mov     rax, [rsi]
0x1800f369c  mov     rbx, [rax+1F8h]
0x1800f36a3  lea     rcx, [rbp+arg_18]
0x1800f36a7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f36ac  lea     rdx, [rbp+arg_18]
0x1800f36b0  mov     rcx, rsi
0x1800f36b3  mov     rax, rbx
0x1800f36b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f36bb  mov     edi, eax
0x1800f36bd  mov     rcx, cs:?g_pIAMGlobals@CApplicationManagerUtility@@3PEAVCIAMGlobals@@EA; SRWLock
0x1800f36c4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f36ca  test    edi, edi
0x1800f36cc  jns     short loc_1800F36FE
0x1800f36ce  mov     rcx, [rbp+arg_18]
0x1800f36d2  test    rcx, rcx
0x1800f36d5  jz      short loc_1800F36E8
0x1800f36d7  mov     [rbp+arg_18], r15
0x1800f36db  mov     rax, [rcx]
0x1800f36de  mov     rax, [rax+10h]
0x1800f36e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f36e7  nop
0x1800f36e8  mov     eax, edi
0x1800f36ea  mov     rbx, [rsp+60h+arg_0]
0x1800f36f2  add     rsp, 60h
0x1800f36f6  pop     r15
0x1800f36f8  pop     r14
0x1800f36fa  pop     rdi
0x1800f36fb  pop     rsi
0x1800f36fc  pop     rbp
0x1800f36fd  retn
0x1800f36fe  mov     rcx, [rbp+arg_18]
0x1800f3702  mov     rax, [rcx]
0x1800f3705  mov     rax, [rax+18h]
0x1800f3709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f370e  mov     [rbp+arg_10], r15
0x1800f3712  mov     rbx, cs:?g_pIAMGlobals@CApplicationManagerUtility@@3PEAVCIAMGlobals@@EA; CIAMGlobals * CApplicationManagerUtility::g_pIAMGlobals
0x1800f3719  mov     [rbp+SRWLock], rbx
0x1800f371d  mov     rcx, rbx; SRWLock
0x1800f3720  call    cs:__imp_AcquireSRWLockShared
0x1800f3726  nop
0x1800f3727  mov     rax, [rsi]
0x1800f372a  mov     rdi, [rax+1F0h]
0x1800f3731  lea     rcx, [rbp+arg_10]
0x1800f3735  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f373a  lea     rdx, [rbp+arg_10]
0x1800f373e  mov     rcx, rsi
0x1800f3741  mov     rax, rdi
0x1800f3744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3749  mov     edi, eax
0x1800f374b  test    rbx, rbx
0x1800f374e  jz      short loc_1800F3759
0x1800f3750  mov     rcx, rbx; SRWLock
0x1800f3753  call    cs:__imp_ReleaseSRWLockShared
0x1800f3759  test    edi, edi
0x1800f375b  js      loc_1800F3832
0x1800f3761  call    cs:__imp_GetCurrentThreadId
0x1800f3767  mov     [rbp+Parameter], eax
0x1800f376a  mov     [rbp+var_14], r15b
0x1800f376e  mov     [rbp+var_10], 80004005h
0x1800f3775  mov     [rbp+phNewTimer], r15
0x1800f3779  xor     ecx, ecx; pReserved
0x1800f377b  call    cs:__imp_CoEnableCallCancellation
0x1800f3781  mov     [rbp+var_10], eax
0x1800f3784  test    eax, eax
0x1800f3786  js      short loc_1800F37B5
0x1800f3788  mov     [rsp+60h+Flags], r15d; Flags
0x1800f378d  mov     [rsp+60h+Period], 3E8h; Period
0x1800f3795  mov     [rsp+60h+DueTime], 2710h; DueTime
0x1800f379d  lea     r9, [rbp+Parameter]; Parameter
0x1800f37a1  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x1800f37a8  xor     edx, edx; TimerQueue
0x1800f37aa  lea     rcx, [rbp+phNewTimer]; phNewTimer
0x1800f37ae  call    cs:__imp_CreateTimerQueueTimer
0x1800f37b4  nop
0x1800f37b5  mov     rcx, [rbp+arg_10]
0x1800f37b9  mov     rax, [rcx]
0x1800f37bc  mov     edx, 1
0x1800f37c1  mov     rax, [rax+0B0h]
0x1800f37c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f37cd  mov     edi, eax
0x1800f37cf  cmp     [rbp+var_10], r15d
0x1800f37d3  jl      short loc_1800F37FD
0x1800f37d5  mov     [rbp+var_10], 80004005h
0x1800f37dc  xor     ecx, ecx; pReserved
0x1800f37de  call    cs:__imp_CoDisableCallCancellation
0x1800f37e4  mov     rdx, [rbp+phNewTimer]; Timer
0x1800f37e8  test    rdx, rdx
0x1800f37eb  jz      short loc_1800F37FD
0x1800f37ed  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800f37f1  xor     ecx, ecx; TimerQueue
0x1800f37f3  call    cs:__imp_DeleteTimerQueueTimer
0x1800f37f9  mov     [rbp+phNewTimer], r15
0x1800f37fd  cmp     [rbp+var_14], r15b
0x1800f3801  jnz     short loc_1800F387D
0x1800f3803  test    edi, edi
0x1800f3805  jns     short loc_1800F3864
0x1800f3807  cmp     [rbp+var_10], r15d
0x1800f380b  jl      short loc_1800F3832
0x1800f380d  mov     [rbp+var_10], 80004005h
0x1800f3814  xor     ecx, ecx; pReserved
0x1800f3816  call    cs:__imp_CoDisableCallCancellation
0x1800f381c  mov     rdx, [rbp+phNewTimer]; Timer
0x1800f3820  test    rdx, rdx
0x1800f3823  jz      short loc_1800F3832
0x1800f3825  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800f3829  xor     ecx, ecx; TimerQueue
0x1800f382b  call    cs:__imp_DeleteTimerQueueTimer
0x1800f3831  nop
0x1800f3832  mov     rcx, [rbp+arg_10]
0x1800f3836  test    rcx, rcx
0x1800f3839  jz      short loc_1800F384C
0x1800f383b  mov     [rbp+arg_10], r15
0x1800f383f  mov     rax, [rcx]
0x1800f3842  mov     rax, [rax+10h]
0x1800f3846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f384b  nop
0x1800f384c  test    edi, edi
0x1800f384e  js      loc_1800F36CE
0x1800f3854  mov     rdx, rsi; struct IImmersiveApplicationInternal *
0x1800f3857  mov     rcx, r14; this
0x1800f385a  call    ?UpdateMonitorForAppAsync@CApplicationManager@@AEAAXPEAUIImmersiveApplicationInternal@@@Z; CApplicationManager::UpdateMonitorForAppAsync(IImmersiveApplicationInternal *)
0x1800f385f  jmp     loc_1800F36CE
0x1800f3864  mov     rcx, [r14+260h]
0x1800f386b  mov     rax, [rcx]
0x1800f386e  mov     rdx, [rbp+arg_10]
0x1800f3872  mov     rax, [rax+58h]
0x1800f3876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f387b  jmp     short loc_1800F3807
0x1800f387d  mov     [rbp+hWnd], r15
0x1800f3881  lea     rdx, [rbp+SRWLock]
0x1800f3885  call    ?AcquireShared@CIAMGlobals@@QEAA?AVCAutoSRWSharedLock@@XZ; CIAMGlobals::AcquireShared(void)
0x1800f388a  nop
0x1800f388b  mov     rcx, [rbp+arg_10]
0x1800f388f  mov     rax, [rcx]
0x1800f3892  lea     rdx, [rbp+hWnd]
0x1800f3896  mov     rax, [rax+18h]
0x1800f389a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f389f  mov     ebx, eax
0x1800f38a1  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800f38a5  test    rcx, rcx
0x1800f38a8  jz      short loc_1800F38B0
0x1800f38aa  call    cs:__imp_ReleaseSRWLockShared
0x1800f38b0  test    ebx, ebx
0x1800f38b2  js      loc_1800F3803
0x1800f38b8  mov     dword ptr [rbp+SRWLock], r15d
0x1800f38bc  lea     rdx, [rbp+SRWLock]; lpdwProcessId
0x1800f38c0  mov     rcx, [rbp+hWnd]; hWnd
0x1800f38c4  call    cs:__imp_GetWindowThreadProcessId
0x1800f38ca  cmp     dword ptr [rbp+SRWLock], r15d
0x1800f38ce  jz      loc_1800F3803
0x1800f38d4  test    eax, eax
0x1800f38d6  jz      loc_1800F3803
0x1800f38dc  mov     r9d, 8
0x1800f38e2  mov     r8d, eax
0x1800f38e5  lea     edx, [r9-7]
0x1800f38e9  lea     rcx, [rbp+SRWLock]
0x1800f38ed  call    cs:__imp_ReportCoreHang
0x1800f38f3  jmp     loc_1800F3803
```
