# CSettingsWidgetFactory::CacheAccountsMetaData(AppInfo *,HWND__ * *)

- ea: `0x1802dfc0c`
- end: `0x1802dfe30`
- name: `?CacheAccountsMetaData@CSettingsWidgetFactory@@SAJPEAVAppInfo@@PEAPEAUHWND__@@@Z`
- size: `548`
- prototype: `__int64 __fastcall(struct AppInfo *, HWND *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1802dd4b8`

## callees

- `0x18000b7e8`
- `0x180047224`
- `0x18008275c`
- `0x18009f240`
- `0x1802dfad4`
- `0x1802dfc0c`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1802dfcca`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1802dfcca`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1802dfdc6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1802dfdc6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802dfd2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802dfd2f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1802dfd5a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1802dfd5a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1802dfc83`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1802dfdab`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1802dfc83`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1802dfdab`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802dfd12`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802dfd12`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1802dfd03`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1802dfd03`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnumWindows` at `0x1802dfc53`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnumWindows` at `0x1802dfc53`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x1802dfc3a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x1802dfc3a`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x1802dfca2`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x1802dfca2`

## pseudocode

```c
__int64 __fastcall CSettingsWidgetFactory::CacheAccountsMetaData(struct AppInfo *a1, HWND *a2)
{
  int Error; // esi
  bool v4; // zf
  HWND Ancestor; // rax
  DWORD TickCount; // r12d
  void *v8; // rbx
  HANDLE EventW; // r15
  HWND v10; // rcx
  void *v11; // rdi
  HANDLE CurrentProcess; // rax
  DWORD v13; // eax
  unsigned int v14; // eax
  DWORD v15; // eax
  LPARAM lParam; // [rsp+40h] [rbp-30h] BYREF
  HWND v18; // [rsp+48h] [rbp-28h]
  _BYTE Parameter[32]; // [rsp+50h] [rbp-20h] BYREF
  DWORD dwProcessId; // [rsp+B0h] [rbp+40h] BYREF
  HANDLE v21; // [rsp+B8h] [rbp+48h] BYREF
  __int64 v22; // [rsp+C0h] [rbp+50h] BYREF
  HANDLE TargetHandle; // [rsp+C8h] [rbp+58h] BYREF

  Error = 0;
  v4 = *((_DWORD *)a1 + 4) == 1;
  *a2 = 0;
  if ( v4 )
  {
    Ancestor = GetAncestor(*((HWND *)a1 + 3), 2u);
    v18 = 0;
    lParam = (LPARAM)Ancestor;
    EnumWindows(CheckForWABWindows, (LPARAM)&lParam);
    if ( v18 )
    {
      *a2 = v18;
      return (unsigned int)Error;
    }
    CImmersiveDebuggerAwareRPCTimeout::CImmersiveDebuggerAwareRPCTimeout(
      Parameter,
      *((const unsigned __int16 **)a1 + 22),
      0x3A98u);
    v22 = 0;
    TickCount = GetTickCount();
    Error = CoreQueryWindowService(
              *((_QWORD *)a1 + 3),
              &IID_IImmersiveAccountsSettings,
              &GUID_82cfe484_6292_4c11_8260_b36817031c9b,
              &v22);
    if ( Error < 0 )
      goto LABEL_25;
    v8 = 0;
    TargetHandle = (HANDLE)-1LL;
    v21 = 0;
    EventW = CreateEventW(0, 0, 0, 0);
    if ( EventW )
    {
      CAutoHandle<void *>::~CAutoHandle<void *>(&v21);
      v10 = (HWND)*((_QWORD *)a1 + 3);
      v8 = EventW;
      dwProcessId = 0;
      v21 = EventW;
      GetWindowThreadProcessId(v10, &dwProcessId);
      lParam = (LPARAM)OpenProcess(0x40u, 0, dwProcessId);
      v11 = (void *)lParam;
      if ( lParam )
        Error = 0;
      else
        Error = ResultFromKnownLastError();
      CurrentProcess = GetCurrentProcess();
      if ( !DuplicateHandle(CurrentProcess, EventW, v11, &TargetHandle, 2u, 0, 0) )
        Error = ResultFromKnownLastError();
      CAutoHandle<void *>::~CAutoHandle<void *>(&lParam);
    }
    else
    {
      Error = ResultFromKnownLastError();
    }
    if ( Error >= 0 )
    {
      dwProcessId = 0;
      Error = (*(__int64 (__fastcall **)(__int64, _QWORD, DWORD *))(*(_QWORD *)v22 + 24LL))(
                v22,
                (unsigned int)TargetHandle,
                &dwProcessId);
      CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)Parameter);
      if ( !dwProcessId )
      {
        v13 = GetTickCount();
        if ( Error >= 0 )
        {
          v14 = v13 - TickCount;
          if ( v14 >= 0x3A98 )
          {
LABEL_23:
            Error = -2147023436;
            goto LABEL_24;
          }
          v15 = WaitForSingleObject(v8, 15000 - v14);
          if ( v15 )
          {
            if ( v15 != 128 )
            {
              if ( v15 != 258 )
              {
                if ( v15 == -1 )
                  Error = ResultFromKnownLastError();
                else
                  Error = -2147418113;
                goto LABEL_24;
              }
              goto LABEL_23;
            }
            Error = -2147024161;
          }
        }
      }
    }
LABEL_24:
    CAutoHandle<void *>::~CAutoHandle<void *>(&v21);
LABEL_25:
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v22);
    CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)Parameter);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1802dfc0c  push    rbp
0x1802dfc0e  push    rbx
0x1802dfc0f  push    rsi
0x1802dfc10  push    rdi
0x1802dfc11  push    r12
0x1802dfc13  push    r14
0x1802dfc15  push    r15
0x1802dfc17  mov     rbp, rsp
0x1802dfc1a  sub     rsp, 70h
0x1802dfc1e  xor     esi, esi
0x1802dfc20  mov     rbx, rdx
0x1802dfc23  cmp     dword ptr [rcx+10h], 1
0x1802dfc27  mov     rdi, rcx
0x1802dfc2a  mov     [rdx], rsi
0x1802dfc2d  jnz     loc_1802DFE1F
0x1802dfc33  mov     rcx, [rcx+18h]; hwnd
0x1802dfc37  lea     edx, [rsi+2]; gaFlags
0x1802dfc3a  call    cs:__imp_GetAncestor
0x1802dfc40  lea     rdx, [rbp+lParam]; lParam
0x1802dfc44  mov     [rbp+var_28], rsi
0x1802dfc48  lea     rcx, CheckForWABWindows; lpEnumFunc
0x1802dfc4f  mov     [rbp+lParam], rax
0x1802dfc53  call    cs:__imp_EnumWindows
0x1802dfc59  mov     rax, [rbp+var_28]
0x1802dfc5d  test    rax, rax
0x1802dfc60  jnz     loc_1802DFE1C
0x1802dfc66  mov     rdx, [rdi+0B0h]; unsigned __int16 *
0x1802dfc6d  lea     rcx, [rbp+Parameter]; Parameter
0x1802dfc71  mov     r14d, 3A98h
0x1802dfc77  mov     r8d, r14d; unsigned int
0x1802dfc7a  call    ??0CImmersiveDebuggerAwareRPCTimeout@@QEAA@PEBGK@Z; CImmersiveDebuggerAwareRPCTimeout::CImmersiveDebuggerAwareRPCTimeout(ushort const *,ulong)
0x1802dfc7f  mov     [rbp+arg_10], rsi
0x1802dfc83  call    cs:__imp_GetTickCount
0x1802dfc89  mov     rcx, [rdi+18h]
0x1802dfc8d  lea     r9, [rbp+arg_10]
0x1802dfc91  lea     r8, _GUID_82cfe484_6292_4c11_8260_b36817031c9b
0x1802dfc98  mov     r12d, eax
0x1802dfc9b  lea     rdx, IID_IImmersiveAccountsSettings
0x1802dfca2  call    cs:__imp_CoreQueryWindowService
0x1802dfca8  mov     esi, eax
0x1802dfcaa  test    eax, eax
0x1802dfcac  js      loc_1802DFE08
0x1802dfcb2  xor     ebx, ebx
0x1802dfcb4  mov     [rbp+TargetHandle], 0FFFFFFFFFFFFFFFFh
0x1802dfcbc  xor     r9d, r9d; lpName
0x1802dfcbf  mov     [rbp+arg_8], rbx
0x1802dfcc3  xor     r8d, r8d; bInitialState
0x1802dfcc6  xor     edx, edx; bManualReset
0x1802dfcc8  xor     ecx, ecx; lpEventAttributes
0x1802dfcca  call    cs:__imp_CreateEventW
0x1802dfcd0  mov     r15, rax
0x1802dfcd3  test    rax, rax
0x1802dfcd6  jnz     short loc_1802DFCE4
0x1802dfcd8  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1802dfcdd  mov     esi, eax
0x1802dfcdf  jmp     loc_1802DFD74
0x1802dfce4  lea     rcx, [rbp+arg_8]
0x1802dfce8  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x1802dfced  mov     rcx, [rdi+18h]; hWnd
0x1802dfcf1  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x1802dfcf5  mov     rbx, r15
0x1802dfcf8  mov     [rbp+dwProcessId], 0
0x1802dfcff  mov     [rbp+arg_8], rbx
0x1802dfd03  call    cs:__imp_GetWindowThreadProcessId
0x1802dfd09  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x1802dfd0d  xor     edx, edx; bInheritHandle
0x1802dfd0f  lea     ecx, [rdx+40h]; dwDesiredAccess
0x1802dfd12  call    cs:__imp_OpenProcess
0x1802dfd18  mov     [rbp+lParam], rax
0x1802dfd1c  mov     rdi, rax
0x1802dfd1f  test    rax, rax
0x1802dfd22  jz      short loc_1802DFD28
0x1802dfd24  xor     esi, esi
0x1802dfd26  jmp     short loc_1802DFD2F
0x1802dfd28  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1802dfd2d  mov     esi, eax
0x1802dfd2f  call    cs:__imp_GetCurrentProcess
0x1802dfd35  mov     [rsp+70h+dwOptions], 0; dwOptions
0x1802dfd3d  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x1802dfd41  mov     rcx, rax; hSourceProcessHandle
0x1802dfd44  mov     [rsp+70h+bInheritHandle], 0; bInheritHandle
0x1802dfd4c  mov     r8, rdi; hTargetProcessHandle
0x1802dfd4f  mov     [rsp+70h+dwDesiredAccess], 2; dwDesiredAccess
0x1802dfd57  mov     rdx, r15; hSourceHandle
0x1802dfd5a  call    cs:__imp_DuplicateHandle
0x1802dfd60  test    eax, eax
0x1802dfd62  jnz     short loc_1802DFD6B
0x1802dfd64  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1802dfd69  mov     esi, eax
0x1802dfd6b  lea     rcx, [rbp+lParam]
0x1802dfd6f  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x1802dfd74  test    esi, esi
0x1802dfd76  js      loc_1802DFDFF
0x1802dfd7c  mov     rcx, [rbp+arg_10]
0x1802dfd80  lea     r8, [rbp+dwProcessId]
0x1802dfd84  mov     edx, dword ptr [rbp+TargetHandle]
0x1802dfd87  mov     [rbp+dwProcessId], 0
0x1802dfd8e  mov     rax, [rcx]
0x1802dfd91  mov     rax, [rax+18h]
0x1802dfd95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802dfd9a  lea     rcx, [rbp+Parameter]; this
0x1802dfd9e  mov     esi, eax
0x1802dfda0  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x1802dfda5  cmp     [rbp+dwProcessId], 0
0x1802dfda9  jnz     short loc_1802DFDFF
0x1802dfdab  call    cs:__imp_GetTickCount
0x1802dfdb1  test    esi, esi
0x1802dfdb3  js      short loc_1802DFDFF
0x1802dfdb5  sub     eax, r12d
0x1802dfdb8  cmp     eax, r14d
0x1802dfdbb  jnb     short loc_1802DFDFA
0x1802dfdbd  sub     r14d, eax
0x1802dfdc0  mov     rcx, rbx; hHandle
0x1802dfdc3  mov     edx, r14d; dwMilliseconds
0x1802dfdc6  call    cs:__imp_WaitForSingleObject
0x1802dfdcc  test    eax, eax
0x1802dfdce  jz      short loc_1802DFDFF
0x1802dfdd0  cmp     eax, 80h
0x1802dfdd5  jz      short loc_1802DFDF3
0x1802dfdd7  cmp     eax, 102h
0x1802dfddc  jz      short loc_1802DFDFA
0x1802dfdde  cmp     eax, 0FFFFFFFFh
0x1802dfde1  jz      short loc_1802DFDEA
0x1802dfde3  mov     esi, 8000FFFFh
0x1802dfde8  jmp     short loc_1802DFDFF
0x1802dfdea  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1802dfdef  mov     esi, eax
0x1802dfdf1  jmp     short loc_1802DFDFF
0x1802dfdf3  mov     esi, 800702DFh
0x1802dfdf8  jmp     short loc_1802DFDFF
0x1802dfdfa  mov     esi, 800705B4h
0x1802dfdff  lea     rcx, [rbp+arg_8]
0x1802dfe03  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x1802dfe08  lea     rcx, [rbp+arg_10]
0x1802dfe0c  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1802dfe11  lea     rcx, [rbp+Parameter]; this
0x1802dfe15  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x1802dfe1a  jmp     short loc_1802DFE1F
0x1802dfe1c  mov     [rbx], rax
0x1802dfe1f  mov     eax, esi
0x1802dfe21  add     rsp, 70h
0x1802dfe25  pop     r15
0x1802dfe27  pop     r14
0x1802dfe29  pop     r12
0x1802dfe2b  pop     rdi
0x1802dfe2c  pop     rsi
0x1802dfe2d  pop     rbx
0x1802dfe2e  pop     rbp
0x1802dfe2f  retn
```
