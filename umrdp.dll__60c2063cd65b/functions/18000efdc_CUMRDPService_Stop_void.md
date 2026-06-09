# CUMRDPService::Stop(void)

- ea: `0x18000efdc`
- end: `0x18000f3bc`
- name: `?Stop@CUMRDPService@@QEAAXXZ`
- size: `992`
- prototype: `void __fastcall(CUMRDPService *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000e8f0`
- `0x18000f750`

## callees

- `0x180002920`
- `0x18000a118`
- `0x18000b8f8`
- `0x18000bd04`
- `0x18000bd44`
- `0x18000e000`
- `0x18000e504`
- `0x18000e784`
- `0x18000efdc`
- `0x18000f75c`
- `0x1800130e8`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f138`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f202`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f349`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f35f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f378`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f138`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f202`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f349`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f35f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f378`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f0ef`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f0ef`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f304`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f304`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000eff9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f00b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000eff9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f00b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f27a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f2ab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f27a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f2ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f2e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f2fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f2e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f2fb`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x18000f2b8`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x18000f2b8`
- `ntdll!EtwEventUnregister` at `0x18000f31c`
- `ntdll!EtwEventUnregister` at `0x18000f31c`
- `KERNEL32!UnregisterWait` at `0x18000f336`
- `KERNEL32!UnregisterWait` at `0x18000f336`
- `RPCRT4!RpcServerUnregisterIf` at `0x18000f259`
- `RPCRT4!RpcServerUnregisterIf` at `0x18000f259`

## pseudocode

```c
void __fastcall CUMRDPService::Stop(CUMRDPService *this)
{
  void *v2; // rcx
  void *v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  HANDLE v7; // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v9; // eax
  __int64 v10; // rax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // r8d
  unsigned int v14; // eax
  unsigned int v15; // eax
  PVOID *v16; // rax
  PVOID *v17; // rdi
  CUmRdpDr **v18; // rax
  CUmRdpDr **v19; // rsi
  void *v20; // rcx
  void *v21; // rcx
  void *v22; // rcx
  void *v23; // rcx
  unsigned int v24; // [rsp+20h] [rbp-38h]

  v2 = (void *)*((_QWORD *)this + 34);
  if ( v2 )
    SetEvent(v2);
  v3 = (void *)*((_QWORD *)this + 38);
  if ( v3 )
    SetEvent(v3);
  if ( *((_QWORD *)this + 9) )
  {
    TCntPtr<CTSBufferResult>::SafeRelease((char *)this + 72);
    *((_QWORD *)this + 9) = 0;
  }
  v4 = *((_QWORD *)this + 36);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 36) = 0;
  }
  v5 = *((_QWORD *)this + 8);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 32LL))(v5);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 16LL))(*((_QWORD *)this + 8));
    *((_QWORD *)this + 8) = 0;
  }
  v6 = *((_QWORD *)this + 39);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 39) = 0;
  }
  v7 = g_hServiceStartupTSUSBDevnodesCleanupThread;
  if ( !g_hServiceStartupTSUSBDevnodesCleanupThread )
    goto LABEL_28;
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), 22, "\r7\n", CurrentThreadActivityIdPrefix);
    v7 = g_hServiceStartupTSUSBDevnodesCleanupThread;
  }
  if ( !WaitForSingleObject(v7, 0xFFFFFFFF) )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
    {
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), 23, "\r7\n", v9);
    }
    CloseHandle(g_hServiceStartupTSUSBDevnodesCleanupThread);
    g_hServiceStartupTSUSBDevnodesCleanupThread = 0;
    goto LABEL_28;
  }
  v10 = *(_QWORD *)&WPP_GLOBAL_Control;
  if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_33;
  if ( (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), 24, "\r7\n", v11);
LABEL_28:
    v10 = *(_QWORD *)&WPP_GLOBAL_Control;
  }
  if ( (unsigned int *)v10 != &WPP_GLOBAL_Control && (*(_BYTE *)(v10 + 28) & 1) != 0 && *(_BYTE *)(v10 + 25) >= 4u )
  {
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), 25, "\r7\n", v12);
  }
LABEL_33:
  if ( (unsigned int)CUMRDPService::IsCleanupTSPrintersThreadCompleted(this, 0xFFFFFFFF) )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), 26, "\r7\n", v14);
    }
    CloseHandle(*((HANDLE *)this + 12));
    *((_QWORD *)this + 12) = 0;
  }
  else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
         && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), 27, "\r7\n", v15);
  }
  if ( *((_DWORD *)this + 14) )
  {
    RpcServerUnregisterIf(qword_18004B9E0, 0, 1u);
    *((_DWORD *)this + 14) = 0;
  }
  if ( *((_DWORD *)this + 66) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
    if ( *((_DWORD *)this + 54) )
    {
      v16 = (PVOID *)operator new(0x18u);
      v17 = v16;
      if ( v16 )
      {
        *v16 = 0;
        v16[2] = (char *)this + 176;
        v16[1] = (char *)this + 104;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
        while ( 1 )
        {
          v18 = (CUmRdpDr **)RtlEnumerateGenericTableWithoutSplaying((PRTL_GENERIC_TABLE)v17[1], v17);
          v19 = v18;
          if ( !v18 )
            break;
          _InterlockedIncrement((volatile signed __int32 *)*v18 + 4);
          CUmRdpDr::Shutdown(*v18);
          CUmRdpDr::Release(*v19);
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)v17[2]);
        operator delete(v17);
      }
    }
    *((_DWORD *)this + 66) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  }
  if ( *((_DWORD *)this + 13) )
  {
    if ( qword_18005DE60 )
    {
      EtwEventUnregister();
      qword_18005DE60 = 0;
    }
    *((_DWORD *)this + 13) = 0;
  }
  v20 = (void *)*((_QWORD *)this + 10);
  if ( v20 )
  {
    UnregisterWait(v20);
    *((_QWORD *)this + 10) = 0;
  }
  v21 = (void *)*((_QWORD *)this + 11);
  if ( v21 )
  {
    CloseHandle(v21);
    *((_QWORD *)this + 11) = 0;
  }
  v22 = (void *)*((_QWORD *)this + 34);
  if ( v22 )
  {
    CloseHandle(v22);
    *((_QWORD *)this + 34) = 0;
  }
  v23 = (void *)*((_QWORD *)this + 38);
  if ( v23 )
  {
    CloseHandle(v23);
    *((_QWORD *)this + 38) = 0;
  }
  g_svcsGlobals = 0;
  g_pService = 0;
  CUMRDPService::UpdateStatus(this, 1u, v13, 0, v24);
  CUMRDPService::~CUMRDPService(this);
  operator delete(this);
}

```

## disassembly

```asm
0x18000efdc  push    rbx
0x18000efde  push    rbp
0x18000efdf  push    rsi
0x18000efe0  push    rdi
0x18000efe1  push    r14
0x18000efe3  sub     rsp, 30h
0x18000efe7  mov     rbx, rcx
0x18000efea  xor     r14d, r14d
0x18000efed  mov     rcx, [rcx+110h]; hEvent
0x18000eff4  test    rcx, rcx
0x18000eff7  jz      short loc_18000EFFF
0x18000eff9  call    cs:__imp_SetEvent
0x18000efff  mov     rcx, [rbx+130h]; hEvent
0x18000f006  test    rcx, rcx
0x18000f009  jz      short loc_18000F011
0x18000f00b  call    cs:__imp_SetEvent
0x18000f011  lea     rdi, [rbx+48h]
0x18000f015  cmp     [rdi], r14
0x18000f018  jz      short loc_18000F025
0x18000f01a  mov     rcx, rdi
0x18000f01d  call    ?SafeRelease@?$TCntPtr@VCTSBufferResult@@@@AEAAXXZ; TCntPtr<CTSBufferResult>::SafeRelease(void)
0x18000f022  mov     [rdi], r14
0x18000f025  mov     rcx, [rbx+120h]
0x18000f02c  test    rcx, rcx
0x18000f02f  jz      short loc_18000F044
0x18000f031  mov     rax, [rcx]
0x18000f034  mov     rax, [rax+10h]
0x18000f038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f03d  mov     [rbx+120h], r14
0x18000f044  mov     rcx, [rbx+40h]
0x18000f048  test    rcx, rcx
0x18000f04b  jz      short loc_18000F06D
0x18000f04d  mov     rax, [rcx]
0x18000f050  mov     rax, [rax+20h]
0x18000f054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f059  mov     rcx, [rbx+40h]
0x18000f05d  mov     rax, [rcx]
0x18000f060  mov     rax, [rax+10h]
0x18000f064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f069  mov     [rbx+40h], r14
0x18000f06d  mov     rcx, [rbx+138h]
0x18000f074  test    rcx, rcx
0x18000f077  jz      short loc_18000F08C
0x18000f079  mov     rax, [rcx]
0x18000f07c  mov     rax, [rax+10h]
0x18000f080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f085  mov     [rbx+138h], r14
0x18000f08c  mov     rcx, cs:?g_hServiceStartupTSUSBDevnodesCleanupThread@@3PEAXEA; void * g_hServiceStartupTSUSBDevnodesCleanupThread
0x18000f093  lea     rdi, WPP_GLOBAL_Control
0x18000f09a  lea     rbp, WPP_000a370d3c4f3de49ddf5e962b0a3f31_Traceguids; "\r7\n"
0x18000f0a1  mov     sil, 4
0x18000f0a4  test    rcx, rcx
0x18000f0a7  jz      loc_18000F17F
0x18000f0ad  mov     rax, cs:WPP_GLOBAL_Control
0x18000f0b4  cmp     rax, rdi
0x18000f0b7  jz      short loc_18000F0EC
0x18000f0b9  test    byte ptr [rax+1Ch], 1
0x18000f0bd  jz      short loc_18000F0EC
0x18000f0bf  cmp     [rax+19h], sil
0x18000f0c3  jb      short loc_18000F0EC
0x18000f0c5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000f0ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0d1  mov     edx, 16h
0x18000f0d6  mov     r9d, eax
0x18000f0d9  mov     r8, rbp
0x18000f0dc  mov     rcx, [rcx+10h]
0x18000f0e0  call    WPP_SF_D
0x18000f0e5  mov     rcx, cs:?g_hServiceStartupTSUSBDevnodesCleanupThread@@3PEAXEA; hHandle
0x18000f0ec  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000f0ef  call    cs:__imp_WaitForSingleObject
0x18000f0f5  test    eax, eax
0x18000f0f7  jnz     short loc_18000F147
0x18000f0f9  mov     rax, cs:WPP_GLOBAL_Control
0x18000f100  cmp     rax, rdi
0x18000f103  jz      short loc_18000F131
0x18000f105  test    byte ptr [rax+1Ch], 1
0x18000f109  jz      short loc_18000F131
0x18000f10b  cmp     [rax+19h], sil
0x18000f10f  jb      short loc_18000F131
0x18000f111  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000f116  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f11d  mov     edx, 17h
0x18000f122  mov     r9d, eax
0x18000f125  mov     r8, rbp
0x18000f128  mov     rcx, [rcx+10h]
0x18000f12c  call    WPP_SF_D
0x18000f131  mov     rcx, cs:?g_hServiceStartupTSUSBDevnodesCleanupThread@@3PEAXEA; hObject
0x18000f138  call    cs:__imp_CloseHandle
0x18000f13e  mov     cs:?g_hServiceStartupTSUSBDevnodesCleanupThread@@3PEAXEA, r14; void * g_hServiceStartupTSUSBDevnodesCleanupThread
0x18000f145  jmp     short loc_18000F17F
0x18000f147  mov     rax, cs:WPP_GLOBAL_Control
0x18000f14e  cmp     rax, rdi
0x18000f151  jz      short loc_18000F1B7
0x18000f153  test    byte ptr [rax+1Ch], 1
0x18000f157  jz      short loc_18000F186
0x18000f159  cmp     byte ptr [rax+19h], 2
0x18000f15d  jb      short loc_18000F186
0x18000f15f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000f164  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f16b  mov     edx, 18h
0x18000f170  mov     r9d, eax
0x18000f173  mov     r8, rbp
0x18000f176  mov     rcx, [rcx+10h]
0x18000f17a  call    WPP_SF_D
0x18000f17f  mov     rax, cs:WPP_GLOBAL_Control
0x18000f186  cmp     rax, rdi
0x18000f189  jz      short loc_18000F1B7
0x18000f18b  test    byte ptr [rax+1Ch], 1
0x18000f18f  jz      short loc_18000F1B7
0x18000f191  cmp     [rax+19h], sil
0x18000f195  jb      short loc_18000F1B7
0x18000f197  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000f19c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f1a3  mov     edx, 19h
0x18000f1a8  mov     r9d, eax
0x18000f1ab  mov     r8, rbp
0x18000f1ae  mov     rcx, [rcx+10h]
0x18000f1b2  call    WPP_SF_D
0x18000f1b7  or      edx, 0FFFFFFFFh; unsigned int
0x18000f1ba  mov     rcx, rbx; this
0x18000f1bd  call    ?IsCleanupTSPrintersThreadCompleted@CUMRDPService@@AEAAHK@Z; CUMRDPService::IsCleanupTSPrintersThreadCompleted(ulong)
0x18000f1c2  test    eax, eax
0x18000f1c4  jz      short loc_18000F20E
0x18000f1c6  mov     rax, cs:WPP_GLOBAL_Control
0x18000f1cd  cmp     rax, rdi
0x18000f1d0  jz      short loc_18000F1FE
0x18000f1d2  test    byte ptr [rax+1Ch], 1
0x18000f1d6  jz      short loc_18000F1FE
0x18000f1d8  cmp     [rax+19h], sil
0x18000f1dc  jb      short loc_18000F1FE
0x18000f1de  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000f1e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f1ea  mov     edx, 1Ah
0x18000f1ef  mov     r9d, eax
0x18000f1f2  mov     r8, rbp
0x18000f1f5  mov     rcx, [rcx+10h]
0x18000f1f9  call    WPP_SF_D
0x18000f1fe  mov     rcx, [rbx+60h]; hObject
0x18000f202  call    cs:__imp_CloseHandle
0x18000f208  mov     [rbx+60h], r14
0x18000f20c  jmp     short loc_18000F246
0x18000f20e  mov     rax, cs:WPP_GLOBAL_Control
0x18000f215  cmp     rax, rdi
0x18000f218  jz      short loc_18000F246
0x18000f21a  test    byte ptr [rax+1Ch], 1
0x18000f21e  jz      short loc_18000F246
0x18000f220  cmp     byte ptr [rax+19h], 2
0x18000f224  jb      short loc_18000F246
0x18000f226  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000f22b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f232  mov     edx, 1Bh
0x18000f237  mov     r9d, eax
0x18000f23a  mov     r8, rbp
0x18000f23d  mov     rcx, [rcx+10h]
0x18000f241  call    WPP_SF_D
0x18000f246  cmp     [rbx+38h], r14d
0x18000f24a  jz      short loc_18000F263
0x18000f24c  xor     edx, edx; MgrTypeUuid
0x18000f24e  lea     rcx, qword_18004B9E0; IfSpec
0x18000f255  lea     r8d, [rdx+1]; WaitForCallsToComplete
0x18000f259  call    cs:__imp_RpcServerUnregisterIf
0x18000f25f  mov     [rbx+38h], r14d
0x18000f263  cmp     [rbx+108h], r14d
0x18000f26a  jz      loc_18000F30A
0x18000f270  lea     rbp, [rbx+0E0h]
0x18000f277  mov     rcx, rbp; lpCriticalSection
0x18000f27a  call    cs:__imp_EnterCriticalSection
0x18000f280  lea     rsi, [rbx+68h]
0x18000f284  cmp     [rsi+70h], r14d
0x18000f288  jz      short loc_18000F2F1
0x18000f28a  mov     ecx, 18h; Size
0x18000f28f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f294  mov     rdi, rax
0x18000f297  test    rax, rax
0x18000f29a  jz      short loc_18000F2F1
0x18000f29c  lea     rcx, [rsi+48h]; lpCriticalSection
0x18000f2a0  mov     [rax], r14
0x18000f2a3  mov     [rax+10h], rcx
0x18000f2a7  mov     [rax+8], rsi
0x18000f2ab  call    cs:__imp_EnterCriticalSection
0x18000f2b1  mov     rcx, [rdi+8]; Table
0x18000f2b5  mov     rdx, rdi; RestartKey
0x18000f2b8  call    cs:__imp_RtlEnumerateGenericTableWithoutSplaying
0x18000f2be  mov     rsi, rax
0x18000f2c1  test    rax, rax
0x18000f2c4  jz      short loc_18000F2DF
0x18000f2c6  mov     rcx, [rax]
0x18000f2c9  lock inc dword ptr [rcx+10h]
0x18000f2cd  mov     rcx, [rax]; this
0x18000f2d0  call    ?Shutdown@CUmRdpDr@@QEAAHXZ; CUmRdpDr::Shutdown(void)
0x18000f2d5  mov     rcx, [rsi]; this
0x18000f2d8  call    ?Release@CUmRdpDr@@QEAAJXZ; CUmRdpDr::Release(void)
0x18000f2dd  jmp     short loc_18000F2B1
0x18000f2df  mov     rcx, [rdi+10h]; lpCriticalSection
0x18000f2e3  call    cs:__imp_LeaveCriticalSection
0x18000f2e9  mov     rcx, rdi; Block
0x18000f2ec  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f2f1  mov     rcx, rbp; lpCriticalSection
0x18000f2f4  mov     [rbx+108h], r14d
0x18000f2fb  call    cs:__imp_LeaveCriticalSection
0x18000f301  mov     rcx, rbp; lpCriticalSection
0x18000f304  call    cs:__imp_DeleteCriticalSection
0x18000f30a  cmp     [rbx+34h], r14d
0x18000f30e  jz      short loc_18000F32D
0x18000f310  mov     rcx, cs:qword_18005DE60
0x18000f317  test    rcx, rcx
0x18000f31a  jz      short loc_18000F329
0x18000f31c  call    cs:__imp_EtwEventUnregister
0x18000f322  mov     cs:qword_18005DE60, r14
0x18000f329  mov     [rbx+34h], r14d
0x18000f32d  mov     rcx, [rbx+50h]; WaitHandle
0x18000f331  test    rcx, rcx
0x18000f334  jz      short loc_18000F340
0x18000f336  call    cs:__imp_UnregisterWait
0x18000f33c  mov     [rbx+50h], r14
0x18000f340  mov     rcx, [rbx+58h]; hObject
0x18000f344  test    rcx, rcx
0x18000f347  jz      short loc_18000F353
0x18000f349  call    cs:__imp_CloseHandle
0x18000f34f  mov     [rbx+58h], r14
0x18000f353  mov     rcx, [rbx+110h]; hObject
0x18000f35a  test    rcx, rcx
0x18000f35d  jz      short loc_18000F36C
0x18000f35f  call    cs:__imp_CloseHandle
0x18000f365  mov     [rbx+110h], r14
0x18000f36c  mov     rcx, [rbx+130h]; hObject
0x18000f373  test    rcx, rcx
0x18000f376  jz      short loc_18000F385
0x18000f378  call    cs:__imp_CloseHandle
0x18000f37e  mov     [rbx+130h], r14
0x18000f385  xor     r9d, r9d; unsigned int
0x18000f388  mov     cs:?g_svcsGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA, r14; _SVCHOST_GLOBAL_DATA * g_svcsGlobals
0x18000f38f  mov     rcx, rbx; this
0x18000f392  mov     cs:?g_pService@@3PEAVCUMRDPService@@EA, r14; CUMRDPService * g_pService
0x18000f399  lea     edx, [r9+1]; unsigned int
0x18000f39d  call    ?UpdateStatus@CUMRDPService@@AEAAHKKKK@Z; CUMRDPService::UpdateStatus(ulong,ulong,ulong,ulong)
0x18000f3a2  mov     rcx, rbx; this
0x18000f3a5  call    ??1CUMRDPService@@QEAA@XZ; CUMRDPService::~CUMRDPService(void)
0x18000f3aa  mov     rcx, rbx; Block
0x18000f3ad  add     rsp, 30h
0x18000f3b1  pop     r14
0x18000f3b3  pop     rdi
0x18000f3b4  pop     rsi
0x18000f3b5  pop     rbp
0x18000f3b6  pop     rbx
0x18000f3b7  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
