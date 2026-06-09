# StorageCleanup::TriggerStorageCleanup(_STORAGE_TRIGGER_CLEANUP_PARAMETERS *,_STORAGE_TRIGGER_CLEANUP_PARAMETERS_EX *)

- ea: `0x180035128`
- end: `0x180035574`
- name: `?TriggerStorageCleanup@StorageCleanup@@QEAAJPEAU_STORAGE_TRIGGER_CLEANUP_PARAMETERS@@PEAU_STORAGE_TRIGGER_CLEANUP_PARAMETERS_EX@@@Z`
- size: `1100`
- prototype: `int(StorageCleanup *__hidden this, struct _STORAGE_TRIGGER_CLEANUP_PARAMETERS *, struct _STORAGE_TRIGGER_CLEANUP_PARAMETERS_EX *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002b1a0`

## callees

- `0x180001148`
- `0x180001248`
- `0x180001f7c`
- `0x18000d030`
- `0x18000ddb0`
- `0x180012c9c`
- `0x18001cf70`
- `0x18001dc9c`
- `0x18001dd2c`
- `0x18002fb98`
- `0x180030ab0`
- `0x180034d88`
- `0x180035128`
- `0x1800375c0`
- `0x18006a970`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180035308`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800353f9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180035308`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800353f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003553e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003553e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800353dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800353dc`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800352f3`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800352f3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800353ce`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800353ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035402`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035402`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall StorageCleanup::TriggerStorageCleanup(
        const wchar_t *this,
        struct _STORAGE_TRIGGER_CLEANUP_PARAMETERS *a2,
        struct _STORAGE_TRIGGER_CLEANUP_PARAMETERS_EX *a3)
{
  bool IsZero; // al
  struct _GUID *v7; // r9
  StorageReserveHelper *v8; // r14
  __int64 (*v9)[12]; // r8
  StorageCleanup *v10; // rcx
  int *v11; // rdi
  int v12; // eax
  StorageCleanup *v13; // rcx
  struct _PROCESS_INFORMATION *v14; // rdx
  signed int v15; // ebx
  __int64 (*v16)[12]; // r8
  HANDLE v17; // rax
  void *v18; // rbx
  signed int LastError; // eax
  int v20; // r9d
  signed int v22; // [rsp+80h] [rbp-80h] BYREF
  int v23; // [rsp+84h] [rbp-7Ch] BYREF
  int v24; // [rsp+88h] [rbp-78h] BYREF
  int v25; // [rsp+8Ch] [rbp-74h] BYREF
  int v26; // [rsp+90h] [rbp-70h] BYREF
  int v27; // [rsp+94h] [rbp-6Ch] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+98h] [rbp-68h] BYREF
  __int64 v29; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v30; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v31; // [rsp+C0h] [rbp-40h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v33; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v34; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v35; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v36; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 *v37; // [rsp+F0h] [rbp-10h] BYREF
  int v38; // [rsp+F8h] [rbp-8h]
  struct _STARTUPINFOW StartupInfo; // [rsp+100h] [rbp+0h] BYREF
  int v40; // [rsp+170h] [rbp+70h] BYREF
  char v41; // [rsp+174h] [rbp+74h]
  _BYTE v42[16]; // [rsp+178h] [rbp+78h] BYREF
  struct _GUID v43; // [rsp+188h] [rbp+88h] BYREF
  int Parameter; // [rsp+1A0h] [rbp+A0h] BYREF
  wchar_t v45[2]; // [rsp+1A4h] [rbp+A4h] BYREF
  _BYTE v46[516]; // [rsp+1A8h] [rbp+A8h] BYREF
  signed int v47; // [rsp+3ACh] [rbp+2ACh]
  unsigned __int16 v48[48]; // [rsp+3B0h] [rbp+2B0h] BYREF
  unsigned __int16 v49[48]; // [rsp+410h] [rbp+310h] BYREF

  v40 = 0;
  v41 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v40);
  if ( (unsigned int)dword_1800BF000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800BF000, 0x400000000000LL) )
  {
    if ( !v41 || (IsZero = _tlgGuidIsZero(&v43), v7 = &v43, IsZero) )
      v7 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_1800BF000,
      byte_1800A8009,
      v42,
      v7);
  }
  v31 = 0;
  v30 = 0;
  v29 = 0;
  memset_0(v49, -1, sizeof(v49));
  memset_0(v48, -1, sizeof(v48));
  v8 = (StorageReserveHelper *)(this + 6);
  SvcGetStorageDeviceSize(0, this + 6, 0, &v31, &v30);
  StorageReserveHelper::QueryStorageReserveEx((StorageReserveHelper *)(this + 6), v49, v9);
  Microsoft::WRL::Wrappers::CriticalSection::Lock(this + 288, &lpCriticalSection);
  if ( !a2 || !a3 )
  {
    v11 = (int *)((char *)a2 + 12);
LABEL_29:
    v15 = -2147024809;
    goto LABEL_30;
  }
  v11 = (int *)((char *)a2 + 12);
  if ( *((_DWORD *)a2 + 3) > 1u || *((_DWORD *)a2 + 1) || *((_DWORD *)a2 + 2) )
    goto LABEL_29;
  v12 = *((_DWORD *)a2 + 4);
  if ( v12 == 1 || v12 == 4 )
  {
    Parameter = *((_DWORD *)a2 + 4);
    *(_DWORD *)v45 = 0;
    memset_0(v46, 0, 0x208u);
    v15 = StringCchCopyW(v45, 0x104u, this + 6);
    if ( v15 >= 0 )
    {
      v17 = CreateThread(0, 0, StorageCleanup::TriggerStorageCleanupThreadProc, &Parameter, 0, 0);
      v18 = v17;
      if ( v17 )
      {
        WaitForSingleObject(v17, 0xFFFFFFFF);
        CloseHandle(v18);
        v15 = v47;
      }
      else
      {
        LastError = GetLastError();
        v15 = LastError;
        if ( LastError > 0 )
          v15 = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  else
  {
    if ( v12 == 3 )
    {
      memset(&ProcessInformation, 0, sizeof(ProcessInformation));
      memset_0(&StartupInfo, 0, sizeof(StartupInfo));
      if ( CreateProcessW(
             L"cleanmgr.exe",
             (LPWSTR)L" /autorunall",
             0,
             0,
             0,
             0x8000000u,
             0,
             0,
             &StartupInfo,
             &ProcessInformation) )
      {
        WaitForSingleObject(ProcessInformation.hProcess, 1000 * *(_DWORD *)a3);
      }
      v15 = StorageCleanup::CleanupKnownPaths(v13, a2);
      if ( v15 < 0 )
      {
        wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v14);
        goto LABEL_30;
      }
      wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v14);
LABEL_22:
      SvcGetStorageDeviceSize(0, v8, 0, 0, &v29);
      StorageReserveHelper::QueryStorageReserveEx(v8, v48, v16);
      goto LABEL_30;
    }
    v15 = 0;
    if ( v12 )
      goto LABEL_22;
    v15 = StorageCleanup::CleanupKnownPaths(v10, a2);
    if ( v15 >= 0 )
      goto LABEL_22;
  }
LABEL_30:
  v40 = 2;
  if ( (unsigned int)dword_1800BF000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800BF000, 0x400000000000LL) )
  {
    v33 = 0x1000000;
    v22 = v15;
    v37 = v48;
    v38 = 96;
    ProcessInformation.hProcess = v49;
    LODWORD(ProcessInformation.hThread) = 96;
    v34 = v29;
    v35 = v30;
    v36 = v31;
    v23 = *(_DWORD *)a3;
    v24 = *((_DWORD *)a2 + 4);
    v25 = *v11;
    v26 = *((_DWORD *)a2 + 2);
    v27 = *((_DWORD *)a2 + 1);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (unsigned int)&dword_1800BF000,
      (unsigned int)&dword_1800A7EC4,
      (unsigned int)v42,
      v20,
      (__int64)&v27,
      (__int64)&v26,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&v23,
      (__int64)&v36,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)&ProcessInformation,
      (__int64)&v37,
      (__int64)&v22,
      (__int64)&v33);
  }
  if ( lpCriticalSection )
  {
    LeaveCriticalSection(lpCriticalSection);
    lpCriticalSection = 0;
  }
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v40);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180035128  push    rbp
0x18003512a  push    rbx
0x18003512b  push    rsi
0x18003512c  push    rdi
0x18003512d  push    r12
0x18003512f  push    r14
0x180035131  push    r15
0x180035133  lea     rbp, [rsp-380h]
0x18003513b  sub     rsp, 480h
0x180035142  mov     rax, cs:__security_cookie
0x180035149  xor     rax, rsp
0x18003514c  mov     [rbp+3B0h+var_40], rax
0x180035153  mov     r15, r8
0x180035156  mov     rsi, rdx
0x180035159  mov     rbx, rcx
0x18003515c  xor     r12d, r12d
0x18003515f  mov     [rbp+3B0h+var_340], r12d
0x180035163  mov     [rbp+3B0h+var_33C], r12b
0x180035167  lea     rcx, [rbp+3B0h+var_340]
0x18003516b  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?StorageServiceProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x180035170  mov     eax, cs:dword_1800BF000
0x180035176  cmp     eax, 5
0x180035179  jbe     short loc_1800351CC
0x18003517b  mov     rdx, 400000000000h
0x180035185  lea     rcx, dword_1800BF000
0x18003518c  call    _tlgKeywordOn
0x180035191  test    al, al
0x180035193  jz      short loc_1800351CC
0x180035195  cmp     [rbp+3B0h+var_33C], r12b
0x180035199  jz      short loc_1800351B2
0x18003519b  lea     rcx, [rbp+3B0h+var_328]; struct _GUID *
0x1800351a2  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800351a7  test    al, al
0x1800351a9  lea     r9, [rbp+3B0h+var_328]
0x1800351b0  jz      short loc_1800351B5
0x1800351b2  mov     r9, r12
0x1800351b5  lea     r8, [rbp+3B0h+var_338]
0x1800351b9  lea     rdx, byte_1800A8009
0x1800351c0  lea     rcx, dword_1800BF000
0x1800351c7  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800351cc  mov     [rbp+3B0h+var_3F0], r12
0x1800351d0  mov     [rbp+3B0h+var_3F8], r12
0x1800351d4  mov     [rbp+3B0h+var_400], r12
0x1800351d8  mov     r14d, 60h ; '`'
0x1800351de  mov     r8d, r14d; Size
0x1800351e1  or      edi, 0FFFFFFFFh
0x1800351e4  mov     edx, edi; Val
0x1800351e6  lea     rcx, [rbp+3B0h+var_A0]; void *
0x1800351ed  call    memset_0
0x1800351f2  mov     r8d, r14d; Size
0x1800351f5  mov     edx, edi; Val
0x1800351f7  lea     rcx, [rbp+3B0h+var_100]; void *
0x1800351fe  call    memset_0
0x180035203  lea     r14, [rbx+0Ch]
0x180035207  lea     rax, [rbp+3B0h+var_3F8]
0x18003520b  mov     qword ptr [rsp+4B0h+bInheritHandles], rax
0x180035210  lea     r9, [rbp+3B0h+var_3F0]
0x180035214  xor     r8d, r8d
0x180035217  mov     rdx, r14
0x18003521a  xor     ecx, ecx
0x18003521c  call    SvcGetStorageDeviceSize
0x180035221  lea     rdx, [rbp+3B0h+var_A0]; unsigned __int16 *
0x180035228  mov     rcx, r14; this
0x18003522b  call    ?QueryStorageReserveEx@StorageReserveHelper@@YAJPEBGAEAY0M@_J@Z; StorageReserveHelper::QueryStorageReserveEx(ushort const *,__int64 (&)[12])
0x180035230  lea     rcx, [rbx+240h]
0x180035237  lea     rdx, [rbp+3B0h+lpCriticalSection]
0x18003523b  call    ?Lock@CriticalSection@Wrappers@WRL@Microsoft@@QEAA?AVSyncLockCriticalSection@Details@234@XZ; Microsoft::WRL::Wrappers::CriticalSection::Lock(void)
0x180035240  nop
0x180035241  test    rsi, rsi
0x180035244  jz      loc_180035410
0x18003524a  test    r15, r15
0x18003524d  jz      loc_180035410
0x180035253  lea     rdi, [rsi+0Ch]
0x180035257  cmp     dword ptr [rdi], 1
0x18003525a  ja      loc_180035414
0x180035260  cmp     [rsi+4], r12d
0x180035264  jnz     loc_180035414
0x18003526a  cmp     [rsi+8], r12d
0x18003526e  jnz     loc_180035414
0x180035274  mov     eax, [rsi+10h]
0x180035277  cmp     eax, 1
0x18003527a  jz      loc_180035377
0x180035280  cmp     eax, 4
0x180035283  jz      loc_180035377
0x180035289  cmp     eax, 3
0x18003528c  jnz     loc_180035331
0x180035292  xorps   xmm0, xmm0
0x180035295  xor     eax, eax
0x180035297  movups  xmmword ptr [rbp+3B0h+ProcessInformation.hProcess], xmm0
0x18003529b  mov     qword ptr [rbp+3B0h+ProcessInformation.dwProcessId], rax
0x18003529f  movups  xmmword ptr [rbp+3B0h+ProcessInformation.hProcess], xmm0
0x1800352a3  mov     qword ptr [rbp+3B0h+ProcessInformation.dwProcessId], rax
0x1800352a7  xor     edx, edx; Val
0x1800352a9  lea     r8d, [rax+68h]; Size
0x1800352ad  lea     rcx, [rbp+3B0h+StartupInfo]; void *
0x1800352b1  call    memset_0
0x1800352b6  lea     rax, [rbp+3B0h+ProcessInformation]
0x1800352ba  mov     [rsp+4B0h+lpProcessInformation], rax; lpProcessInformation
0x1800352bf  lea     rax, [rbp+3B0h+StartupInfo]
0x1800352c3  mov     [rsp+4B0h+lpStartupInfo], rax; lpStartupInfo
0x1800352c8  mov     [rsp+4B0h+lpCurrentDirectory], r12; lpCurrentDirectory
0x1800352cd  mov     [rsp+4B0h+lpEnvironment], r12; lpEnvironment
0x1800352d2  mov     [rsp+4B0h+dwCreationFlags], 8000000h; dwCreationFlags
0x1800352da  mov     [rsp+4B0h+bInheritHandles], r12d; bInheritHandles
0x1800352df  xor     r9d, r9d; lpThreadAttributes
0x1800352e2  xor     r8d, r8d; lpProcessAttributes
0x1800352e5  lea     rdx, aAutorunall; " /autorunall"
0x1800352ec  lea     rcx, pszMore; "cleanmgr.exe"
0x1800352f3  call    cs:__imp_CreateProcessW
0x1800352f9  test    eax, eax
0x1800352fb  jz      short loc_18003530E
0x1800352fd  imul    edx, [r15], 3E8h; dwMilliseconds
0x180035304  mov     rcx, [rbp+3B0h+ProcessInformation.hProcess]; hHandle
0x180035308  call    cs:__imp_WaitForSingleObject
0x18003530e  mov     rdx, rsi; struct _STORAGE_TRIGGER_CLEANUP_PARAMETERS *
0x180035311  call    ?CleanupKnownPaths@StorageCleanup@@AEAAJPEAU_STORAGE_TRIGGER_CLEANUP_PARAMETERS@@@Z; StorageCleanup::CleanupKnownPaths(_STORAGE_TRIGGER_CLEANUP_PARAMETERS *)
0x180035316  mov     ebx, eax
0x180035318  lea     rcx, [rbp+3B0h+ProcessInformation]; this
0x18003531c  test    eax, eax
0x18003531e  jns     short loc_18003532A
0x180035320  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x180035325  jmp     loc_180035419
0x18003532a  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x18003532f  jmp     short loc_18003534A
0x180035331  mov     ebx, r12d
0x180035334  test    eax, eax
0x180035336  jnz     short loc_18003534A
0x180035338  mov     rdx, rsi; struct _STORAGE_TRIGGER_CLEANUP_PARAMETERS *
0x18003533b  call    ?CleanupKnownPaths@StorageCleanup@@AEAAJPEAU_STORAGE_TRIGGER_CLEANUP_PARAMETERS@@@Z; StorageCleanup::CleanupKnownPaths(_STORAGE_TRIGGER_CLEANUP_PARAMETERS *)
0x180035340  mov     ebx, eax
0x180035342  test    eax, eax
0x180035344  js      loc_180035419
0x18003534a  lea     rax, [rbp+3B0h+var_400]
0x18003534e  mov     qword ptr [rsp+4B0h+bInheritHandles], rax
0x180035353  xor     r9d, r9d
0x180035356  xor     r8d, r8d
0x180035359  mov     rdx, r14
0x18003535c  xor     ecx, ecx
0x18003535e  call    SvcGetStorageDeviceSize
0x180035363  lea     rdx, [rbp+3B0h+var_100]; unsigned __int16 *
0x18003536a  mov     rcx, r14; this
0x18003536d  call    ?QueryStorageReserveEx@StorageReserveHelper@@YAJPEBGAEAY0M@_J@Z; StorageReserveHelper::QueryStorageReserveEx(ushort const *,__int64 (&)[12])
0x180035372  jmp     loc_180035419
0x180035377  mov     [rbp+3B0h+Parameter], eax
0x18003537d  mov     dword ptr [rbp+3B0h+var_30C], r12d
0x180035384  xor     edx, edx; Val
0x180035386  mov     r8d, 208h; Size
0x18003538c  lea     rcx, [rbp+3B0h+var_308]; void *
0x180035393  call    memset_0
0x180035398  mov     r8, r14; wchar_t *
0x18003539b  mov     edx, 104h; unsigned __int64
0x1800353a0  lea     rcx, [rbp+3B0h+var_30C]; wchar_t *
0x1800353a7  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800353ac  mov     ebx, eax
0x1800353ae  test    eax, eax
0x1800353b0  js      short loc_180035419
0x1800353b2  mov     qword ptr [rsp+4B0h+dwCreationFlags], r12; lpThreadId
0x1800353b7  mov     [rsp+4B0h+bInheritHandles], r12d; dwCreationFlags
0x1800353bc  lea     r9, [rbp+3B0h+Parameter]; lpParameter
0x1800353c3  lea     r8, ?TriggerStorageCleanupThreadProc@StorageCleanup@@CAKPEAX@Z; lpStartAddress
0x1800353ca  xor     edx, edx; dwStackSize
0x1800353cc  xor     ecx, ecx; lpThreadAttributes
0x1800353ce  call    cs:__imp_CreateThread
0x1800353d4  mov     rbx, rax
0x1800353d7  test    rax, rax
0x1800353da  jnz     short loc_1800353F3
0x1800353dc  call    cs:__imp_GetLastError
0x1800353e2  mov     ebx, eax
0x1800353e4  test    eax, eax
0x1800353e6  jle     short loc_180035419
0x1800353e8  movzx   ebx, ax
0x1800353eb  or      ebx, 80070000h
0x1800353f1  jmp     short loc_180035419
0x1800353f3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800353f6  mov     rcx, rbx; hHandle
0x1800353f9  call    cs:__imp_WaitForSingleObject
0x1800353ff  mov     rcx, rbx; hObject
0x180035402  call    cs:__imp_CloseHandle
0x180035408  mov     ebx, [rbp+3B0h+var_104]
0x18003540e  jmp     short loc_180035419
0x180035410  lea     rdi, [rsi+0Ch]
0x180035414  mov     ebx, 80070057h
0x180035419  mov     [rbp+3B0h+var_340], 2
0x180035420  mov     eax, cs:dword_1800BF000
0x180035426  cmp     eax, 5
0x180035429  jbe     loc_180035535
0x18003542f  mov     rdx, 400000000000h
0x180035439  lea     rcx, dword_1800BF000
0x180035440  call    _tlgKeywordOn
0x180035445  test    al, al
0x180035447  jz      loc_180035535
0x18003544d  mov     [rbp+3B0h+var_3E0], 1000000h
0x180035455  mov     [rbp+3B0h+var_430], ebx
0x180035458  lea     rax, [rbp+3B0h+var_100]
0x18003545f  mov     [rbp+3B0h+var_3C0], rax
0x180035463  mov     [rbp+3B0h+var_3B8], 60h ; '`'
0x18003546a  lea     rax, [rbp+3B0h+var_A0]
0x180035471  mov     [rbp+3B0h+ProcessInformation.hProcess], rax
0x180035475  mov     dword ptr [rbp+3B0h+ProcessInformation.hThread], 60h ; '`'
0x18003547c  mov     rax, [rbp+3B0h+var_400]
0x180035480  mov     [rbp+3B0h+var_3D8], rax
0x180035484  mov     rax, [rbp+3B0h+var_3F8]
0x180035488  mov     [rbp+3B0h+var_3D0], rax
0x18003548c  mov     rax, [rbp+3B0h+var_3F0]
0x180035490  mov     [rbp+3B0h+var_3C8], rax
0x180035494  mov     eax, [r15]
0x180035497  mov     [rbp+3B0h+var_42C], eax
0x18003549a  mov     eax, [rsi+10h]
0x18003549d  mov     [rbp+3B0h+var_428], eax
0x1800354a0  mov     eax, [rdi]
0x1800354a2  mov     [rbp+3B0h+var_424], eax
0x1800354a5  mov     eax, [rsi+8]
0x1800354a8  mov     [rbp+3B0h+var_420], eax
0x1800354ab  mov     eax, [rsi+4]
0x1800354ae  mov     [rbp+3B0h+var_41C], eax
0x1800354b1  lea     rax, [rbp+3B0h+var_3E0]
0x1800354b5  mov     [rsp+4B0h+var_438], rax
0x1800354ba  lea     rax, [rbp+3B0h+var_430]
0x1800354be  mov     [rsp+4B0h+var_440], rax
0x1800354c3  lea     rax, [rbp+3B0h+var_3C0]
0x1800354c7  mov     [rsp+4B0h+var_448], rax
0x1800354cc  lea     rax, [rbp+3B0h+ProcessInformation]
0x1800354d0  mov     [rsp+4B0h+var_450], rax
0x1800354d5  lea     rax, [rbp+3B0h+var_3D8]
0x1800354d9  mov     [rsp+4B0h+var_458], rax
0x1800354de  lea     rax, [rbp+3B0h+var_3D0]
0x1800354e2  mov     [rsp+4B0h+var_460], rax
0x1800354e7  lea     rax, [rbp+3B0h+var_3C8]
0x1800354eb  mov     [rsp+4B0h+lpProcessInformation], rax
0x1800354f0  lea     rax, [rbp+3B0h+var_42C]
0x1800354f4  mov     [rsp+4B0h+lpStartupInfo], rax
0x1800354f9  lea     rax, [rbp+3B0h+var_428]
0x1800354fd  mov     [rsp+4B0h+lpCurrentDirectory], rax
0x180035502  lea     rax, [rbp+3B0h+var_424]
0x180035506  mov     [rsp+4B0h+lpEnvironment], rax
0x18003550b  lea     rax, [rbp+3B0h+var_420]
0x18003550f  mov     qword ptr [rsp+4B0h+dwCreationFlags], rax
0x180035514  lea     rax, [rbp+3B0h+var_41C]
0x180035518  mov     qword ptr [rsp+4B0h+bInheritHandles], rax
0x18003551d  lea     r8, [rbp+3B0h+var_338]
0x180035521  lea     rdx, dword_1800A7EC4
0x180035528  lea     rcx, dword_1800BF000
0x18003552f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U2@U2@U_tlgWrapperPtrSize@@U3@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3333AEBU?$_tlgWrapperByVal@$07@@44AEBU_tlgWrapperPtrSize@@534@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperPtrSize,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperPtrSize const &,_tlgWrapperPtrSize const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180035534  nop
0x180035535  mov     rcx, [rbp+3B0h+lpCriticalSection]; lpCriticalSection
0x180035539  test    rcx, rcx
0x18003553c  jz      short loc_180035548
0x18003553e  call    cs:__imp_LeaveCriticalSection
0x180035544  mov     [rbp+3B0h+lpCriticalSection], r12
0x180035548  lea     rcx, [rbp+3B0h+var_340]
0x18003554c  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?StorageServiceProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x180035551  mov     eax, ebx
0x180035553  mov     rcx, [rbp+3B0h+var_40]
0x18003555a  xor     rcx, rsp; StackCookie
0x18003555d  call    __security_check_cookie
0x180035562  add     rsp, 480h
0x180035569  pop     r15
0x18003556b  pop     r14
0x18003556d  pop     r12
0x18003556f  pop     rdi
0x180035570  pop     rsi
0x180035571  pop     rbx
0x180035572  pop     rbp
0x180035573  retn
```
