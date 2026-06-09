# CDlpTransportBits::TransferFile(IDlpFile *,IDlpTask *,_ULARGE_INTEGER *,_ULARGE_INTEGER *,_ULARGE_INTEGER *)

- ea: `0x180078060`
- end: `0x1800787f6`
- name: `?TransferFile@CDlpTransportBits@@EEAAJPEAVIDlpFile@@PEAVIDlpTask@@PEAT_ULARGE_INTEGER@@22@Z`
- size: `1942`
- prototype: `__int64 __usercall@<rax>(CDlpTransportBits *__hidden this@<rcx>, struct IDlpFile *@<rdx>, struct IDlpTask *@<r8>, union _ULARGE_INTEGER *@<r9>, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x180049e50`
- `0x180078060`
- `0x18007da50`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180078479`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180078479`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180078669`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180078669`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007848b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800785cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078673`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007848b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800785cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078673`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007855e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007855e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007820c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180078569`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800787a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007820c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180078569`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800787a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800782cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078509`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800787e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800782cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078509`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800787e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800782b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800782b9`

## string_xrefs

- `0x180078651`: `Transfer thread has exited.`
- `0x180078543`: `Waiting for transfer thread to exit.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDlpTransportBits::TransferFile(
        CDlpTransportBits *this,
        struct IDlpFile *a2,
        struct IDlpTask *a3,
        union _ULARGE_INTEGER *a4,
        union _ULARGE_INTEGER *a5,
        union _ULARGE_INTEGER *a6)
{
  char *v9; // r12
  void *v10; // rbx
  signed int updated; // edi
  char *v12; // r15
  __int64 v13; // rax
  __int64 v14; // rcx
  int v15; // eax
  union _ULARGE_INTEGER *v16; // rsi
  char *v17; // r15
  char *v18; // r15
  struct _RTL_CRITICAL_SECTION *v19; // r12
  __int64 v20; // rax
  __int64 v21; // rcx
  int v22; // eax
  __int64 v24; // rax
  __int64 v25; // rcx
  int v26; // eax
  HANDLE v27; // rax
  signed int LastError; // eax
  char *v29; // rsi
  __int64 v30; // rax
  DWORD v31; // edi
  signed int v32; // eax
  __int64 v33; // rax
  signed int v34; // eax
  bool v35; // sf
  __int64 dwCreationFlags; // [rsp+20h] [rbp-79h]
  DWORD dwCreationFlagsa; // [rsp+20h] [rbp-79h]
  DWORD dwCreationFlagsb; // [rsp+20h] [rbp-79h]
  LPDWORD lpThreadId; // [rsp+28h] [rbp-71h]
  int lpThreadIda; // [rsp+28h] [rbp-71h]
  ULONGLONG v41; // [rsp+30h] [rbp-69h] BYREF
  __int128 v42; // [rsp+38h] [rbp-61h]
  __int64 v43; // [rsp+48h] [rbp-51h]
  HANDLE v44; // [rsp+50h] [rbp-49h]
  __int64 v45; // [rsp+58h] [rbp-41h] BYREF
  __int128 Parameter; // [rsp+60h] [rbp-39h] BYREF
  __int128 v47; // [rsp+70h] [rbp-29h]
  union _ULARGE_INTEGER *v48; // [rsp+80h] [rbp-19h]
  int v49; // [rsp+98h] [rbp-1h]
  int v50; // [rsp+F0h] [rbp+57h] BYREF
  DWORD ExitCode; // [rsp+F8h] [rbp+5Fh] BYREF
  struct IDlpTask *v52; // [rsp+100h] [rbp+67h]

  v52 = a3;
  v43 = 0;
  *(_QWORD *)&v42 = &CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable';
  v9 = (char *)this + 336;
  *((_QWORD *)&v42 + 1) = (char *)this + 336;
  v50 = 0;
  v10 = 0;
  v44 = 0;
  Parameter = 0;
  v47 = 0;
  v48 = 0;
  v45 = 0;
  v41 = 0;
  ExitCode = 0;
  if ( !a2 )
  {
    updated = -2147024809;
    v12 = (char *)this + 168;
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
      goto LABEL_26;
    v13 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v12 + 16LL))((char *)this + 168);
    v14 = 0;
    if ( !v13 )
      goto LABEL_7;
    dwCreationFlagsa = 2166;
    goto LABEL_5;
  }
  v16 = a5;
  if ( a4 )
  {
    if ( !a5 )
      goto LABEL_10;
  }
  else if ( a5 )
  {
LABEL_10:
    updated = -2147024809;
    v17 = (char *)this + 168;
    if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
    {
      v13 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v17 + 16LL))((char *)this + 168);
      v14 = 0;
      if ( v13 )
      {
        dwCreationFlagsa = 2167;
        goto LABEL_5;
      }
      goto LABEL_7;
    }
    goto LABEL_26;
  }
  if ( a6 )
  {
    v19 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 344);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 344));
    LODWORD(v43) = 1;
    updated = CDlpTransportBits::CheckInitialized(this, (enum WINDLP_STATE *)&v50);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
      {
LABEL_25:
        v9 = (char *)this + 336;
        goto LABEL_26;
      }
      v20 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
      v21 = 0;
      if ( !v20 )
      {
LABEL_24:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v21);
        goto LABEL_25;
      }
      lpThreadIda = updated;
      dwCreationFlagsb = 2176;
LABEL_22:
      v22 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v20,
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpTransportBits::TransferFile",
              dwCreationFlagsb,
              lpThreadIda,
              v41,
              v42);
      v21 = (unsigned int)v22;
      if ( v22 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v22);
      goto LABEL_24;
    }
    if ( v50 )
    {
      updated = -2147019873;
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
        goto LABEL_25;
      v20 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
      v21 = 0;
      if ( !v20 )
        goto LABEL_24;
      lpThreadIda = -2147019873;
      dwCreationFlagsb = 2177;
      goto LABEL_22;
    }
    updated = CDlpTransportBits::UpdateState(this, 1);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
        goto LABEL_92;
      v24 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
      v25 = 0;
      if ( !v24 )
        goto LABEL_41;
      LODWORD(lpThreadId) = updated;
      LODWORD(dwCreationFlags) = 2182;
      goto LABEL_39;
    }
    v45 = 0;
    v41 = 0;
    updated = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)a2 + 2) + 8LL))((char *)a2 + 16);
    if ( updated < 0 )
    {
      if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
      {
        v24 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
        v25 = 0;
        if ( v24 )
        {
          LODWORD(lpThreadId) = updated;
          LODWORD(dwCreationFlags) = 2188;
          goto LABEL_39;
        }
LABEL_41:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v25);
      }
LABEL_92:
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
      v49 = 1;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      *((_DWORD *)this + 55) = -21037378;
      *((_DWORD *)this + 54) = 0;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      if ( v49 )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
        v49 = 0;
      }
      goto LABEL_25;
    }
    *(_QWORD *)&Parameter = this;
    *((_QWORD *)&Parameter + 1) = a2;
    *(_QWORD *)&v47 = v52;
    *((_QWORD *)&v47 + 1) = a4;
    v48 = v16;
    *((_QWORD *)this + 76) = a2;
    v27 = CreateThread(0, 0, CDlpTransportBits::TransferFileThreadProc, &Parameter, 0, 0);
    v10 = v27;
    if ( !v27 )
    {
      v44 = 0;
      LastError = GetLastError();
      updated = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          updated = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        updated = -2147467259;
      }
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
        goto LABEL_92;
      v24 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
      v25 = 0;
      if ( updated >= 0 || !v24 )
        goto LABEL_41;
      LODWORD(lpThreadId) = updated;
      LODWORD(dwCreationFlags) = 2211;
      goto LABEL_39;
    }
    v44 = v27;
    if ( (_DWORD)v43 )
    {
      LeaveCriticalSection(v19);
      LODWORD(v43) = 0;
    }
    v29 = (char *)this + 168;
    if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
    {
      v30 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v29 + 16LL))((char *)this + 168);
      CDlpLogT<CEmptyType>::DlpLogFormat(v30, 2, L"Waiting for transfer thread to exit.");
    }
    v31 = WaitForSingleObject(v10, 0xFFFFFFFF);
    EnterCriticalSection(v19);
    LODWORD(v43) = 1;
    if ( v31 )
    {
      if ( v31 == -1 )
      {
        v32 = GetLastError();
        updated = v32;
        if ( v32 > 0 )
          updated = (unsigned __int16)v32 | 0x80070000;
        if ( updated >= 0 || !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v29 + 16LL))((char *)this + 168) )
          goto LABEL_92;
        v24 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v29 + 16LL))((char *)this + 168);
        v25 = 0;
        if ( !v24 )
          goto LABEL_41;
        LODWORD(lpThreadId) = updated;
        LODWORD(dwCreationFlags) = 2238;
        goto LABEL_39;
      }
      updated = -2147418113;
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v29 + 16LL))((char *)this + 168) )
        goto LABEL_92;
      v24 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v29 + 16LL))((char *)this + 168);
      v25 = 0;
      if ( !v24 )
        goto LABEL_41;
      LODWORD(lpThreadId) = -2147418113;
      LODWORD(dwCreationFlags) = 2243;
    }
    else
    {
      if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v29 + 16LL))((char *)this + 168) )
      {
        v33 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v29 + 16LL))((char *)this + 168);
        CDlpLogT<CEmptyType>::DlpLogFormat(v33, 2, L"Transfer thread has exited.");
      }
      if ( !GetExitCodeThread(v10, &ExitCode) )
      {
        v34 = GetLastError();
        updated = v34;
        if ( v34 )
        {
          if ( v34 > 0 )
            updated = (unsigned __int16)v34 | 0x80070000;
        }
        else
        {
          updated = -2147467259;
        }
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v29 + 16LL))((char *)this + 168) )
          goto LABEL_92;
        v24 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v29 + 16LL))((char *)this + 168);
        v25 = 0;
        if ( updated >= 0 || !v24 )
          goto LABEL_41;
        LODWORD(lpThreadId) = updated;
        LODWORD(dwCreationFlags) = 2233;
        goto LABEL_39;
      }
      updated = ExitCode;
      v35 = (ExitCode & 0x80000000) != 0;
      if ( (int)ExitCode > 0 )
      {
        updated = (unsigned __int16)ExitCode | 0x80070000;
        v35 = 1;
      }
      if ( v35 )
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v29 + 16LL))((char *)this + 168) )
          goto LABEL_92;
        v24 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v29 + 16LL))((char *)this + 168);
        v25 = 0;
        if ( !v24 )
          goto LABEL_41;
        LODWORD(lpThreadId) = updated;
        LODWORD(dwCreationFlags) = 2234;
      }
      else
      {
        updated = (*(__int64 (__fastcall **)(struct IDlpFile *, __int64 *, ULONGLONG *))(*(_QWORD *)a2 + 40LL))(
                    a2,
                    &v45,
                    &v41);
        if ( updated >= 0 )
        {
          a6->QuadPart = v41;
          goto LABEL_92;
        }
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v29 + 16LL))((char *)this + 168) )
          goto LABEL_92;
        v24 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v29 + 16LL))((char *)this + 168);
        v25 = 0;
        if ( !v24 )
          goto LABEL_41;
        LODWORD(lpThreadId) = updated;
        LODWORD(dwCreationFlags) = 2249;
      }
    }
LABEL_39:
    v26 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v24,
            4,
            L"%s(%d): Result = 0x%X",
            L"CDlpTransportBits::TransferFile",
            dwCreationFlags,
            lpThreadId,
            v41,
            v42);
    v25 = (unsigned int)v26;
    if ( v26 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v26);
    goto LABEL_41;
  }
  updated = -2147024809;
  v18 = (char *)this + 168;
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
  {
    v13 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))((char *)this + 168);
    v14 = 0;
    if ( v13 )
    {
      dwCreationFlagsa = 2168;
LABEL_5:
      v15 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v13,
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpTransportBits::TransferFile",
              dwCreationFlagsa,
              -2147024809,
              v41,
              v42);
      v14 = (unsigned int)v15;
      if ( v15 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v15);
    }
LABEL_7:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v14);
  }
LABEL_26:
  *((_QWORD *)this + 76) = 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)updated);
  if ( v10 )
    CloseHandle(v10);
  if ( (_DWORD)v43 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 8));
    LODWORD(v43) = 0;
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180078060  mov     [rsp-8+arg_18], rbx
0x180078065  mov     [rsp-8+arg_10], r8
0x18007806a  push    rbp
0x18007806b  push    rsi
0x18007806c  push    rdi
0x18007806d  push    r12
0x18007806f  push    r13
0x180078071  push    r14
0x180078073  push    r15
0x180078075  lea     rbp, [rsp-17h]
0x18007807a  sub     rsp, 0B0h
0x180078081  mov     r13, r9
0x180078084  mov     r15, rdx
0x180078087  mov     r14, rcx
0x18007808a  xorps   xmm0, xmm0
0x18007808d  xor     eax, eax
0x18007808f  movups  [rbp+47h+var_A8], xmm0
0x180078093  mov     [rbp+47h+var_98], rax
0x180078097  lea     rax, ??_7?$CDlpAutoDelayLockT@V?$CDlpAutoExclusiveAcquireLockT@VCEmptyType@@@@@@6B@; const CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable'
0x18007809e  mov     qword ptr [rbp+47h+var_A8], rax
0x1800780a2  lea     r12, [rcx+150h]
0x1800780a9  mov     qword ptr [rbp+47h+var_A8+8], r12
0x1800780ad  xor     ecx, ecx
0x1800780af  mov     [rbp+47h+arg_0], ecx
0x1800780b2  mov     ebx, ecx
0x1800780b4  mov     [rbp+47h+var_90], rcx
0x1800780b8  xor     eax, eax
0x1800780ba  movups  [rbp+47h+Parameter], xmm0
0x1800780be  movups  [rbp+47h+var_70], xmm0
0x1800780c2  mov     [rbp+47h+var_60], rax
0x1800780c6  mov     [rbp+47h+var_88], rcx
0x1800780ca  mov     [rbp+47h+var_B0], rcx
0x1800780ce  mov     [rbp+47h+ExitCode], ecx
0x1800780d1  test    rdx, rdx
0x1800780d4  jnz     short loc_18007814E
0x1800780d6  mov     esi, 80070057h
0x1800780db  mov     edi, esi
0x1800780dd  lea     r15, [r14+0A8h]
0x1800780e4  mov     rax, [r15]
0x1800780e7  mov     rcx, r15
0x1800780ea  mov     rax, [rax+10h]
0x1800780ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800780f3  test    rax, rax
0x1800780f6  jz      loc_18007829E
0x1800780fc  mov     rax, [r15]
0x1800780ff  mov     rcx, r15
0x180078102  mov     rax, [rax+10h]
0x180078106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007810b  xor     ecx, ecx
0x18007810d  test    rax, rax
0x180078110  jz      short loc_180078144
0x180078112  mov     dword ptr [rsp+0E0h+lpThreadId], esi
0x180078116  mov     dword ptr [rsp+0E0h+dwCreationFlags], 876h
0x18007811e  lea     r9, aCdlptransportb_25; "CDlpTransportBits::TransferFile"
0x180078125  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18007812c  mov     edx, 4
0x180078131  mov     rcx, rax
0x180078134  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180078139  test    eax, eax
0x18007813b  mov     ecx, eax
0x18007813d  jns     short loc_180078144
0x18007813f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180078144  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180078149  jmp     loc_18007829E
0x18007814e  mov     rsi, [rbp+47h+arg_20]
0x180078152  test    r13, r13
0x180078155  jz      short loc_1800781A9
0x180078157  test    rsi, rsi
0x18007815a  jnz     short loc_1800781AE
0x18007815c  mov     esi, 80070057h
0x180078161  mov     edi, esi
0x180078163  lea     r15, [r14+0A8h]
0x18007816a  mov     rax, [r15]
0x18007816d  mov     rcx, r15
0x180078170  mov     rax, [rax+10h]
0x180078174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078179  test    rax, rax
0x18007817c  jz      loc_18007829E
0x180078182  mov     rax, [r15]
0x180078185  mov     rcx, r15
0x180078188  mov     rax, [rax+10h]
0x18007818c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078191  xor     ecx, ecx
0x180078193  test    rax, rax
0x180078196  jz      short loc_180078144
0x180078198  mov     dword ptr [rsp+0E0h+lpThreadId], esi
0x18007819c  mov     dword ptr [rsp+0E0h+dwCreationFlags], 877h
0x1800781a4  jmp     loc_18007811E
0x1800781a9  test    rsi, rsi
0x1800781ac  jnz     short loc_18007815C
0x1800781ae  cmp     [rbp+47h+arg_28], rcx
0x1800781b2  jnz     short loc_180078205
0x1800781b4  mov     esi, 80070057h
0x1800781b9  mov     edi, esi
0x1800781bb  lea     r15, [r14+0A8h]
0x1800781c2  mov     rax, [r15]
0x1800781c5  mov     rcx, r15
0x1800781c8  mov     rax, [rax+10h]
0x1800781cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800781d1  test    rax, rax
0x1800781d4  jz      loc_18007829E
0x1800781da  mov     rax, [r15]
0x1800781dd  mov     rcx, r15
0x1800781e0  mov     rax, [rax+10h]
0x1800781e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800781e9  xor     ecx, ecx
0x1800781eb  test    rax, rax
0x1800781ee  jz      loc_180078144
0x1800781f4  mov     dword ptr [rsp+0E0h+lpThreadId], esi
0x1800781f8  mov     dword ptr [rsp+0E0h+dwCreationFlags], 878h
0x180078200  jmp     loc_18007811E
0x180078205  add     r12, 8
0x180078209  mov     rcx, r12; lpCriticalSection
0x18007820c  call    cs:__imp_EnterCriticalSection
0x180078212  mov     dword ptr [rbp+47h+var_98], 1
0x180078219  lea     rdx, [rbp+47h+arg_0]; enum WINDLP_STATE *
0x18007821d  mov     rcx, r14; this
0x180078220  call    ?CheckInitialized@CDlpTransportBits@@AEAAJPEAW4WINDLP_STATE@@@Z; CDlpTransportBits::CheckInitialized(WINDLP_STATE *)
0x180078225  mov     edi, eax
0x180078227  test    eax, eax
0x180078229  jns     loc_1800782F6
0x18007822f  lea     rsi, [r14+0A8h]
0x180078236  mov     rdx, [rsi]
0x180078239  mov     rcx, rsi
0x18007823c  mov     rax, [rdx+10h]
0x180078240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078245  test    rax, rax
0x180078248  jz      short loc_180078297
0x18007824a  mov     rax, [rsi]
0x18007824d  mov     rcx, rsi
0x180078250  mov     rax, [rax+10h]
0x180078254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078259  xor     ecx, ecx
0x18007825b  test    rax, rax
0x18007825e  jz      short loc_180078292
0x180078260  mov     dword ptr [rsp+0E0h+lpThreadId], edi
0x180078264  mov     dword ptr [rsp+0E0h+dwCreationFlags], 880h
0x18007826c  lea     r9, aCdlptransportb_25; "CDlpTransportBits::TransferFile"
0x180078273  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18007827a  mov     edx, 4
0x18007827f  mov     rcx, rax
0x180078282  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180078287  test    eax, eax
0x180078289  mov     ecx, eax
0x18007828b  jns     short loc_180078292
0x18007828d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180078292  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180078297  lea     r12, [r14+150h]
0x18007829e  mov     qword ptr [r14+260h], 0
0x1800782a9  mov     ecx, edi
0x1800782ab  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800782b0  nop
0x1800782b1  test    rbx, rbx
0x1800782b4  jz      short loc_1800782C0
0x1800782b6  mov     rcx, rbx; hObject
0x1800782b9  call    cs:__imp_CloseHandle
0x1800782bf  nop
0x1800782c0  mov     eax, dword ptr [rbp+47h+var_98]
0x1800782c3  test    eax, eax
0x1800782c5  jz      short loc_1800782D9
0x1800782c7  lea     rcx, [r12+8]; lpCriticalSection
0x1800782cc  call    cs:__imp_LeaveCriticalSection
0x1800782d2  mov     dword ptr [rbp+47h+var_98], 0
0x1800782d9  mov     eax, edi
0x1800782db  mov     rbx, [rsp+0E0h+arg_18]
0x1800782e3  add     rsp, 0B0h
0x1800782ea  pop     r15
0x1800782ec  pop     r14
0x1800782ee  pop     r13
0x1800782f0  pop     r12
0x1800782f2  pop     rdi
0x1800782f3  pop     rsi
0x1800782f4  pop     rbp
0x1800782f5  retn
0x1800782f6  cmp     [rbp+47h+arg_0], 0
0x1800782fa  jz      short loc_18007834B
0x1800782fc  mov     edi, 8007139Fh
0x180078301  lea     rsi, [r14+0A8h]
0x180078308  mov     rax, [rsi]
0x18007830b  mov     rcx, rsi
0x18007830e  mov     rax, [rax+10h]
0x180078312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078317  test    rax, rax
0x18007831a  jz      loc_180078297
0x180078320  mov     rax, [rsi]
0x180078323  mov     rcx, rsi
0x180078326  mov     rax, [rax+10h]
0x18007832a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007832f  xor     ecx, ecx
0x180078331  test    rax, rax
0x180078334  jz      loc_180078292
0x18007833a  mov     dword ptr [rsp+0E0h+lpThreadId], edi
0x18007833e  mov     dword ptr [rsp+0E0h+dwCreationFlags], 881h
0x180078346  jmp     loc_18007826C
0x18007834b  xor     r8d, r8d
0x18007834e  lea     edx, [r8+1]
0x180078352  mov     rcx, r14
0x180078355  call    ?UpdateState@CDlpTransportBits@@AEAAJW4WINDLP_STATE@@PEAW42@@Z; CDlpTransportBits::UpdateState(WINDLP_STATE,WINDLP_STATE *)
0x18007835a  mov     edi, eax
0x18007835c  test    eax, eax
0x18007835e  jns     short loc_1800783D1
0x180078360  lea     rsi, [r14+0A8h]
0x180078367  mov     rax, [rsi]
0x18007836a  mov     rcx, rsi
0x18007836d  mov     rax, [rax+10h]
0x180078371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078376  test    rax, rax
0x180078379  jz      loc_18007879A
0x18007837f  mov     rax, [rsi]
0x180078382  mov     rcx, rsi
0x180078385  mov     rax, [rax+10h]
0x180078389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007838e  xor     ecx, ecx
0x180078390  test    rax, rax
0x180078393  jz      short loc_1800783C7
0x180078395  mov     dword ptr [rsp+0E0h+lpThreadId], edi
0x180078399  mov     dword ptr [rsp+0E0h+dwCreationFlags], 886h
0x1800783a1  lea     r9, aCdlptransportb_25; "CDlpTransportBits::TransferFile"
0x1800783a8  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800783af  mov     edx, 4
0x1800783b4  mov     rcx, rax
0x1800783b7  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1800783bc  test    eax, eax
0x1800783be  mov     ecx, eax
0x1800783c0  jns     short loc_1800783C7
0x1800783c2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800783c7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800783cc  jmp     loc_18007879A
0x1800783d1  xor     edx, edx
0x1800783d3  mov     [rbp+47h+var_88], rdx
0x1800783d7  xor     r8d, r8d
0x1800783da  mov     [rbp+47h+var_B0], r8
0x1800783de  lea     rcx, [r15+10h]
0x1800783e2  mov     rax, [rcx]
0x1800783e5  mov     rax, [rax+8]
0x1800783e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800783ee  mov     edi, eax
0x1800783f0  test    eax, eax
0x1800783f2  jns     short loc_18007843A
0x1800783f4  lea     rsi, [r14+0A8h]
0x1800783fb  mov     rax, [rsi]
0x1800783fe  mov     rcx, rsi
0x180078401  mov     rax, [rax+10h]
0x180078405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007840a  test    rax, rax
0x18007840d  jz      loc_18007879A
0x180078413  mov     rax, [rsi]
0x180078416  mov     rcx, rsi
0x180078419  mov     rax, [rax+10h]
0x18007841d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078422  xor     ecx, ecx
0x180078424  test    rax, rax
0x180078427  jz      short loc_1800783C7
0x180078429  mov     dword ptr [rsp+0E0h+lpThreadId], edi
0x18007842d  mov     dword ptr [rsp+0E0h+dwCreationFlags], 88Ch
0x180078435  jmp     loc_1800783A1
0x18007843a  mov     qword ptr [rbp+47h+Parameter], r14
0x18007843e  mov     qword ptr [rbp+47h+Parameter+8], r15
0x180078442  mov     rax, [rbp+47h+arg_10]
0x180078446  mov     qword ptr [rbp+47h+var_70], rax
0x18007844a  mov     qword ptr [rbp+47h+var_70+8], r13
0x18007844e  mov     [rbp+47h+var_60], rsi
0x180078452  mov     [r14+260h], r15
0x180078459  mov     [rsp+0E0h+lpThreadId], 0; lpThreadId
0x180078462  mov     dword ptr [rsp+0E0h+dwCreationFlags], 0; dwCreationFlags
0x18007846a  lea     r9, [rbp+47h+Parameter]; lpParameter
0x18007846e  lea     r8, ?TransferFileThreadProc@CDlpTransportBits@@SAKPEAX@Z; lpStartAddress
0x180078475  xor     edx, edx; dwStackSize
0x180078477  xor     ecx, ecx; lpThreadAttributes
0x180078479  call    cs:__imp_CreateThread
0x18007847f  mov     rbx, rax
0x180078482  test    rax, rax
0x180078485  jnz     short loc_1800784FB
0x180078487  mov     [rbp+47h+var_90], rax
0x18007848b  call    cs:__imp_GetLastError
0x180078491  mov     edi, eax
0x180078493  test    eax, eax
0x180078495  jnz     short loc_18007849E
0x180078497  mov     edi, 80004005h
0x18007849c  jmp     short loc_1800784A9
0x18007849e  jle     short loc_1800784A9
0x1800784a0  movzx   edi, ax
0x1800784a3  or      edi, 80070000h
0x1800784a9  lea     rsi, [r14+0A8h]
0x1800784b0  mov     rax, [rsi]
0x1800784b3  mov     rcx, rsi
0x1800784b6  mov     rax, [rax+10h]
0x1800784ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800784bf  test    rax, rax
0x1800784c2  jz      loc_18007879A
0x1800784c8  mov     rax, [rsi]
0x1800784cb  mov     rcx, rsi
0x1800784ce  mov     rax, [rax+10h]
0x1800784d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800784d7  xor     ecx, ecx
0x1800784d9  test    edi, edi
0x1800784db  jns     loc_1800783C7
0x1800784e1  test    rax, rax
0x1800784e4  jz      loc_1800783C7
0x1800784ea  mov     dword ptr [rsp+0E0h+lpThreadId], edi
  ... truncated ...
```
