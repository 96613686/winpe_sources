# CDlpTask::ResetActionProgress(IDlpAction *)

- ea: `0x18006ddf0`
- end: `0x18006e403`
- name: `?ResetActionProgress@CDlpTask@@UEAAJPEAVIDlpAction@@@Z`
- size: `1555`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this, struct IDlpAction *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x180049d6c`
- `0x1800681bc`
- `0x18006ddf0`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006e267`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006e267`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006e310`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006e310`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006de44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e132`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e28b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e2cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006de44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e132`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e28b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e2cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e157`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e2b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e2ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e350`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e3e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e157`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e2b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e2ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e350`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e3e3`

## string_xrefs

- `0x18006df8e`: `DlpTask: Skipping action progress reset due to task cancellation request.`
- `0x18006deba`: `CDlpTask::ResetActionProgress`
- `0x18006e3a2`: `CDlpTask::ResetActionProgress`
- `0x18006e1dd`: `DlpTask: Resetting action [%d] progress start time.`
- `0x18006e0b9`: `DlpTask: Skipping action progress reset due to action cancellation request.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpTask::ResetActionProgress(CDlpTask *this, struct IDlpAction *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  int v5; // ebx
  __int64 v6; // rax
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // r15
  char *v12; // r14
  __int64 (__fastcall *v13)(char *); // rax
  char *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rbx
  __int64 v19; // rbx
  __int64 v20; // rcx
  unsigned __int64 v21; // rax
  int v22; // eax
  int v24; // [rsp+20h] [rbp-49h]
  int v25; // [rsp+20h] [rbp-49h]
  int v26; // [rsp+28h] [rbp-41h]
  int v27; // [rsp+28h] [rbp-41h]
  struct _FILETIME v28; // [rsp+30h] [rbp-39h]
  _QWORD v29[3]; // [rsp+38h] [rbp-31h] BYREF
  __int64 v30; // [rsp+50h] [rbp-19h]
  __int64 v31; // [rsp+58h] [rbp-11h]
  int v32; // [rsp+70h] [rbp+7h]
  int v33; // [rsp+D0h] [rbp+67h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+D8h] [rbp+6Fh]
  __int64 v35; // [rsp+E0h] [rbp+77h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+E8h] [rbp+7Fh] BYREF

  v31 = 0;
  v29[2] = (char *)this + 744;
  v29[1] = &CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable';
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 752);
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 752);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 752));
  v30 = 1;
  v33 = 0;
  SystemTimeAsFileTime = 0;
  v35 = 0;
  v29[0] = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160) )
      goto LABEL_60;
    v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160);
    v7 = 0;
    if ( !v6 )
      goto LABEL_7;
    v26 = -2147024809;
    v24 = 2453;
    goto LABEL_5;
  }
  v5 = CDlpTask::CheckInitialized((CDlpTask *)((char *)this - 16), (enum WINDLP_STATE *)&v33);
  if ( v5 >= 0 )
  {
    if ( v33 == -1073741824 )
    {
      if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160) )
      {
        v9 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160);
        CDlpLogT<CEmptyType>::DlpLogFormat(
          v9,
          3u,
          (__int64)L"DlpTask: Skipping action progress reset due to task cancellation request.");
      }
LABEL_15:
      v5 = 0;
      goto LABEL_60;
    }
    if ( (unsigned int)(v33 - 3) > 2 )
    {
      v5 = -2147019873;
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160) )
        goto LABEL_60;
      v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160);
      v7 = 0;
      if ( !v6 )
        goto LABEL_7;
      v26 = -2147019873;
      v24 = 2471;
      goto LABEL_5;
    }
    v5 = (*(__int64 (__fastcall **)(struct IDlpAction *, int *))(*(_QWORD *)a2 + 24LL))(a2, &v33);
    if ( v5 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160) )
        goto LABEL_60;
      v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160);
      v7 = 0;
      if ( !v6 )
        goto LABEL_7;
      v26 = v5;
      v24 = 2475;
      goto LABEL_5;
    }
    if ( v33 == -1073741824 )
    {
      if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160) )
      {
        v10 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160);
        CDlpLogT<CEmptyType>::DlpLogFormat(
          v10,
          3u,
          (__int64)L"DlpTask: Skipping action progress reset due to action cancellation request.");
      }
      goto LABEL_15;
    }
    if ( (unsigned int)(v33 - 3) > 2 )
    {
      v5 = -2147019873;
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160) )
        goto LABEL_60;
      v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160);
      v7 = 0;
      if ( !v6 )
        goto LABEL_7;
      v26 = -2147019873;
      v24 = 2489;
LABEL_5:
      v8 = CDlpLogT<CEmptyType>::DlpLogFormat(
             v6,
             4u,
             (__int64)L"%s(%d): Result = 0x%X",
             L"CDlpTask::ResetActionProgress",
             v24,
             v26);
      v7 = (unsigned int)v8;
      if ( v8 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
      goto LABEL_7;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 872));
    v32 = 1;
    v11 = *((int *)this + 214);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 872));
    v32 = 0;
    v12 = (char *)this + 160;
    v13 = *(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL);
    v14 = (char *)this + 160;
    if ( a2 == *(struct IDlpAction **)(*((_QWORD *)this + 46) + 8 * v11) )
    {
      if ( v13(v14) )
      {
        v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v12 + 16LL))((char *)this + 160);
        CDlpLogT<CEmptyType>::DlpLogFormat(
          v17,
          2u,
          (__int64)L"DlpTask: Resetting action [%d] progress start time.",
          (unsigned int)v11);
      }
      v5 = (*(__int64 (__fastcall **)(struct IDlpAction *, _QWORD *, __int64 *, _QWORD))(*(_QWORD *)a2 + 72LL))(
             a2,
             v29,
             &v35,
             0);
      if ( v5 >= 0 )
      {
        *((_QWORD *)this + 179) = v35;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        v28 = SystemTimeAsFileTime;
        v18 = *(_QWORD *)(*((_QWORD *)this + 146) + 8 * v11);
        EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 16));
        v32 = 1;
        *(struct _FILETIME *)v18 = v28;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        if ( v32 )
        {
          LeaveCriticalSection((LPCRITICAL_SECTION)(v18 + 16));
          v32 = 0;
        }
        v19 = v35;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 952));
        v32 = 1;
        *((struct _FILETIME *)this + 115) = v28;
        *((_QWORD *)this + 116) = v19;
        *((_QWORD *)this + 117) = 0;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        if ( v32 )
        {
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 952));
          v32 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        *((_DWORD *)this + 357) = GetTickCount();
        v20 = v35;
        if ( v29[0] )
          v21 = (unsigned __int64)(100 * v35) / v29[0];
        else
          v21 = 0;
        *((_QWORD *)this + 181) = v21;
        *((_QWORD *)this + 180) = v20;
        if ( (_DWORD)v30 )
        {
          LeaveCriticalSection(lpCriticalSection);
          LODWORD(v30) = 0;
        }
        v5 = CDlpTask::NotifyActionStateChanged((CDlpTask *)((char *)this - 16), 0);
        if ( v5 >= 0 || !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v12 + 16LL))((char *)this + 160) )
          goto LABEL_59;
        v15 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v12 + 16LL))((char *)this + 160);
        v16 = 0;
        if ( !v15 )
          goto LABEL_58;
        v27 = v5;
        v25 = 2523;
        goto LABEL_56;
      }
      if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v12 + 16LL))((char *)this + 160) )
      {
        v15 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v12 + 16LL))((char *)this + 160);
        v16 = 0;
        if ( v15 )
        {
          v27 = v5;
          v25 = 2504;
LABEL_56:
          v22 = CDlpLogT<CEmptyType>::DlpLogFormat(
                  v15,
                  4u,
                  (__int64)L"%s(%d): Result = 0x%X",
                  L"CDlpTask::ResetActionProgress",
                  v25,
                  v27);
          v16 = (unsigned int)v22;
          if ( v22 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v22);
        }
LABEL_58:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v16);
      }
    }
    else
    {
      v5 = -2147024883;
      if ( v13(v14) )
      {
        v15 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v12 + 16LL))((char *)this + 160);
        v16 = 0;
        if ( v15 )
        {
          v27 = -2147024883;
          v25 = 2498;
          goto LABEL_56;
        }
        goto LABEL_58;
      }
    }
LABEL_59:
    v4 = lpCriticalSection;
    goto LABEL_60;
  }
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160) )
  {
    v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160);
    v7 = 0;
    if ( v6 )
    {
      v26 = v5;
      v24 = 2457;
      goto LABEL_5;
    }
LABEL_7:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  }
LABEL_60:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
  if ( (_DWORD)v30 )
  {
    LeaveCriticalSection(v4);
    LODWORD(v30) = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18006ddf0  push    rbp
0x18006ddf2  push    rbx
0x18006ddf3  push    rsi
0x18006ddf4  push    rdi
0x18006ddf5  push    r12
0x18006ddf7  push    r13
0x18006ddf9  push    r14
0x18006ddfb  push    r15
0x18006ddfd  lea     rbp, [rsp-1Fh]
0x18006de02  sub     rsp, 88h
0x18006de09  mov     rdi, rdx
0x18006de0c  mov     rsi, rcx
0x18006de0f  xor     r12d, r12d
0x18006de12  mov     [rbp+57h+var_68], r12
0x18006de16  xorps   xmm0, xmm0
0x18006de19  xor     eax, eax
0x18006de1b  movups  [rbp+57h+var_80], xmm0
0x18006de1f  mov     [rbp+57h+var_70], rax
0x18006de23  lea     rax, [rcx+2E8h]
0x18006de2a  mov     qword ptr [rbp+57h+var_80+8], rax
0x18006de2e  lea     rcx, ??_7?$CDlpAutoDelayLockT@V?$CDlpAutoExclusiveAcquireLockT@VCEmptyType@@@@@@6B@; const CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable'
0x18006de35  mov     qword ptr [rbp+57h+var_80], rcx
0x18006de39  lea     r14, [rax+8]
0x18006de3d  mov     [rbp+57h+lpCriticalSection], r14
0x18006de41  mov     rcx, r14; lpCriticalSection
0x18006de44  call    cs:__imp_EnterCriticalSection
0x18006de4a  mov     dword ptr [rbp+57h+var_70], 1
0x18006de51  mov     [rbp+57h+arg_0], r12d
0x18006de55  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r12
0x18006de59  mov     [rbp+57h+arg_10], r12
0x18006de5d  mov     [rbp+57h+var_88], r12
0x18006de61  test    rdi, rdi
0x18006de64  jnz     loc_18006DEEA
0x18006de6a  mov     ebx, 80070057h
0x18006de6f  mov     rax, [rsi+0A0h]
0x18006de76  lea     rcx, [rsi+0A0h]
0x18006de7d  mov     rax, [rax+10h]
0x18006de81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006de86  test    rax, rax
0x18006de89  jz      loc_18006E3D1
0x18006de8f  mov     rax, [rsi+0A0h]
0x18006de96  lea     rcx, [rsi+0A0h]
0x18006de9d  mov     rax, [rax+10h]
0x18006dea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dea6  mov     ecx, r12d
0x18006dea9  test    rax, rax
0x18006deac  jz      short loc_18006DEE0
0x18006deae  mov     [rsp+0C0h+var_98], ebx
0x18006deb2  mov     [rsp+0C0h+var_A0], 995h
0x18006deba  lea     r9, aCdlptaskReseta; "CDlpTask::ResetActionProgress"
0x18006dec1  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18006dec8  mov     edx, 4
0x18006decd  mov     rcx, rax
0x18006ded0  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18006ded5  test    eax, eax
0x18006ded7  mov     ecx, eax
0x18006ded9  jns     short loc_18006DEE0
0x18006dedb  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18006dee0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006dee5  jmp     loc_18006E3D1
0x18006deea  lea     rdx, [rbp+57h+arg_0]; enum WINDLP_STATE *
0x18006deee  lea     rcx, [rsi-10h]; this
0x18006def2  call    ?CheckInitialized@CDlpTask@@AEAAJPEAW4WINDLP_STATE@@@Z; CDlpTask::CheckInitialized(WINDLP_STATE *)
0x18006def7  mov     ebx, eax
0x18006def9  test    eax, eax
0x18006defb  jns     short loc_18006DF4D
0x18006defd  mov     rdx, [rsi+0A0h]
0x18006df04  lea     rcx, [rsi+0A0h]
0x18006df0b  mov     rax, [rdx+10h]
0x18006df0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006df14  test    rax, rax
0x18006df17  jz      loc_18006E3D1
0x18006df1d  mov     rax, [rsi+0A0h]
0x18006df24  lea     rcx, [rsi+0A0h]
0x18006df2b  mov     rax, [rax+10h]
0x18006df2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006df34  mov     ecx, r12d
0x18006df37  test    rax, rax
0x18006df3a  jz      short loc_18006DEE0
0x18006df3c  mov     [rsp+0C0h+var_98], ebx
0x18006df40  mov     [rsp+0C0h+var_A0], 999h
0x18006df48  jmp     loc_18006DEBA
0x18006df4d  mov     eax, [rbp+57h+arg_0]
0x18006df50  mov     r15d, 0C0000000h
0x18006df56  cmp     eax, r15d
0x18006df59  jnz     short loc_18006DFAA
0x18006df5b  mov     rax, [rsi+0A0h]
0x18006df62  lea     rcx, [rsi+0A0h]
0x18006df69  mov     rax, [rax+10h]
0x18006df6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006df72  test    rax, rax
0x18006df75  jz      short loc_18006DFA2
0x18006df77  mov     rax, [rsi+0A0h]
0x18006df7e  lea     rcx, [rsi+0A0h]
0x18006df85  mov     rax, [rax+10h]
0x18006df89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006df8e  lea     r8, aDlptaskSkippin_0; "DlpTask: Skipping action progress reset"...
0x18006df95  mov     rcx, rax
0x18006df98  mov     edx, 3
0x18006df9d  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18006dfa2  mov     ebx, r12d
0x18006dfa5  jmp     loc_18006E3D1
0x18006dfaa  add     eax, 0FFFFFFFDh
0x18006dfad  cmp     eax, 2
0x18006dfb0  jbe     short loc_18006E00D
0x18006dfb2  mov     edi, 8007139Fh
0x18006dfb7  mov     ebx, edi
0x18006dfb9  mov     rax, [rsi+0A0h]
0x18006dfc0  lea     rcx, [rsi+0A0h]
0x18006dfc7  mov     rax, [rax+10h]
0x18006dfcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dfd0  test    rax, rax
0x18006dfd3  jz      loc_18006E3D1
0x18006dfd9  mov     rax, [rsi+0A0h]
0x18006dfe0  lea     rcx, [rsi+0A0h]
0x18006dfe7  mov     rax, [rax+10h]
0x18006dfeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dff0  mov     ecx, r12d
0x18006dff3  test    rax, rax
0x18006dff6  jz      loc_18006DEE0
0x18006dffc  mov     [rsp+0C0h+var_98], edi
0x18006e000  mov     [rsp+0C0h+var_A0], 9A7h
0x18006e008  jmp     loc_18006DEBA
0x18006e00d  mov     rax, [rdi]
0x18006e010  lea     rdx, [rbp+57h+arg_0]
0x18006e014  mov     rcx, rdi
0x18006e017  mov     rax, [rax+18h]
0x18006e01b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e020  mov     ebx, eax
0x18006e022  test    eax, eax
0x18006e024  jns     short loc_18006E07A
0x18006e026  mov     rax, [rsi+0A0h]
0x18006e02d  lea     rcx, [rsi+0A0h]
0x18006e034  mov     rax, [rax+10h]
0x18006e038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e03d  test    rax, rax
0x18006e040  jz      loc_18006E3D1
0x18006e046  mov     rax, [rsi+0A0h]
0x18006e04d  lea     rcx, [rsi+0A0h]
0x18006e054  mov     rax, [rax+10h]
0x18006e058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e05d  mov     ecx, r12d
0x18006e060  test    rax, rax
0x18006e063  jz      loc_18006DEE0
0x18006e069  mov     [rsp+0C0h+var_98], ebx
0x18006e06d  mov     [rsp+0C0h+var_A0], 9ABh
0x18006e075  jmp     loc_18006DEBA
0x18006e07a  mov     eax, [rbp+57h+arg_0]
0x18006e07d  cmp     eax, r15d
0x18006e080  jnz     short loc_18006E0C5
0x18006e082  mov     rax, [rsi+0A0h]
0x18006e089  lea     rcx, [rsi+0A0h]
0x18006e090  mov     rax, [rax+10h]
0x18006e094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e099  test    rax, rax
0x18006e09c  jz      loc_18006DFA2
0x18006e0a2  mov     rax, [rsi+0A0h]
0x18006e0a9  lea     rcx, [rsi+0A0h]
0x18006e0b0  mov     rax, [rax+10h]
0x18006e0b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e0b9  lea     r8, aDlptaskSkippin; "DlpTask: Skipping action progress reset"...
0x18006e0c0  jmp     loc_18006DF95
0x18006e0c5  add     eax, 0FFFFFFFDh
0x18006e0c8  cmp     eax, 2
0x18006e0cb  jbe     short loc_18006E128
0x18006e0cd  mov     edi, 8007139Fh
0x18006e0d2  mov     ebx, edi
0x18006e0d4  mov     rax, [rsi+0A0h]
0x18006e0db  lea     rcx, [rsi+0A0h]
0x18006e0e2  mov     rax, [rax+10h]
0x18006e0e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e0eb  test    rax, rax
0x18006e0ee  jz      loc_18006E3D1
0x18006e0f4  mov     rax, [rsi+0A0h]
0x18006e0fb  lea     rcx, [rsi+0A0h]
0x18006e102  mov     rax, [rax+10h]
0x18006e106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e10b  mov     ecx, r12d
0x18006e10e  test    rax, rax
0x18006e111  jz      loc_18006DEE0
0x18006e117  mov     [rsp+0C0h+var_98], edi
0x18006e11b  mov     [rsp+0C0h+var_A0], 9B9h
0x18006e123  jmp     loc_18006DEBA
0x18006e128  lea     rbx, [rsi+368h]
0x18006e12f  mov     rcx, rbx; lpCriticalSection
0x18006e132  call    cs:__imp_EnterCriticalSection
0x18006e138  mov     [rbp+57h+var_50], 1
0x18006e13f  movsxd  r15, dword ptr [rsi+358h]
0x18006e146  xor     ecx, ecx
0x18006e148  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006e14d  mov     eax, [rbp+57h+var_50]
0x18006e150  test    eax, eax
0x18006e152  jz      short loc_18006E161
0x18006e154  mov     rcx, rbx; lpCriticalSection
0x18006e157  call    cs:__imp_LeaveCriticalSection
0x18006e15d  mov     [rbp+57h+var_50], r12d
0x18006e161  mov     rcx, [rsi+170h]
0x18006e168  lea     r14, [rsi+0A0h]
0x18006e16f  mov     rax, [r14]
0x18006e172  mov     rax, [rax+10h]
0x18006e176  cmp     rdi, [rcx+r15*8]
0x18006e17a  mov     rcx, r14
0x18006e17d  jz      short loc_18006E1C1
0x18006e17f  mov     ebx, 8007000Dh
0x18006e184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e189  xor     r12d, r12d
0x18006e18c  test    rax, rax
0x18006e18f  jz      loc_18006E3CD
0x18006e195  mov     rax, [r14]
0x18006e198  mov     rcx, r14
0x18006e19b  mov     rax, [rax+10h]
0x18006e19f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e1a4  mov     ecx, r12d
0x18006e1a7  test    rax, rax
0x18006e1aa  jz      loc_18006E3C8
0x18006e1b0  mov     [rsp+0C0h+var_98], ebx
0x18006e1b4  mov     [rsp+0C0h+var_A0], 9C2h
0x18006e1bc  jmp     loc_18006E3A2
0x18006e1c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e1c6  test    rax, rax
0x18006e1c9  jz      short loc_18006E1F1
0x18006e1cb  mov     rax, [r14]
0x18006e1ce  mov     rcx, r14
0x18006e1d1  mov     rax, [rax+10h]
0x18006e1d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e1da  mov     r9d, r15d
0x18006e1dd  lea     r8, aDlptaskResetti_0; "DlpTask: Resetting action [%d] progress"...
0x18006e1e4  mov     edx, 2
0x18006e1e9  mov     rcx, rax
0x18006e1ec  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18006e1f1  mov     rax, [rdi]
0x18006e1f4  xor     r9d, r9d
0x18006e1f7  lea     r8, [rbp+57h+arg_10]
0x18006e1fb  lea     rdx, [rbp+57h+var_88]
0x18006e1ff  mov     rcx, rdi
0x18006e202  mov     rax, [rax+48h]
0x18006e206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e20b  mov     ebx, eax
0x18006e20d  test    eax, eax
0x18006e20f  jns     short loc_18006E258
0x18006e211  mov     rax, [r14]
0x18006e214  mov     rcx, r14
0x18006e217  mov     rax, [rax+10h]
0x18006e21b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e220  xor     r12d, r12d
0x18006e223  test    rax, rax
0x18006e226  jz      loc_18006E3CD
0x18006e22c  mov     rax, [r14]
0x18006e22f  mov     rcx, r14
0x18006e232  mov     rax, [rax+10h]
0x18006e236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e23b  mov     ecx, r12d
0x18006e23e  test    rax, rax
0x18006e241  jz      loc_18006E3C8
0x18006e247  mov     [rsp+0C0h+var_98], ebx
0x18006e24b  mov     [rsp+0C0h+var_A0], 9C8h
0x18006e253  jmp     loc_18006E3A2
0x18006e258  mov     rax, [rbp+57h+arg_10]
0x18006e25c  mov     [rsi+598h], rax
0x18006e263  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18006e267  call    cs:__imp_GetSystemTimeAsFileTime
0x18006e26d  mov     eax, [rbp+57h+SystemTimeAsFileTime.dwHighDateTime]
0x18006e273  mov     dword ptr [rbp+57h+var_90+4], eax
0x18006e276  mov     eax, [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x18006e279  mov     dword ptr [rbp+57h+var_90], eax
0x18006e27c  mov     rax, [rsi+490h]
0x18006e283  mov     rbx, [rax+r15*8]
0x18006e287  lea     rcx, [rbx+10h]; lpCriticalSection
0x18006e28b  call    cs:__imp_EnterCriticalSection
0x18006e291  mov     [rbp+57h+var_50], 1
0x18006e298  mov     rdi, [rbp+57h+var_90]
0x18006e29c  mov     [rbx], rdi
0x18006e29f  xor     ecx, ecx
0x18006e2a1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006e2a6  mov     eax, [rbp+57h+var_50]
0x18006e2a9  xor     r12d, r12d
0x18006e2ac  test    eax, eax
0x18006e2ae  jz      short loc_18006E2BE
0x18006e2b0  lea     rcx, [rbx+10h]; lpCriticalSection
0x18006e2b4  call    cs:__imp_LeaveCriticalSection
0x18006e2ba  mov     [rbp+57h+var_50], r12d
0x18006e2be  mov     rbx, [rbp+57h+arg_10]
0x18006e2c2  lea     r15, [rsi+3B8h]
0x18006e2c9  mov     rcx, r15; lpCriticalSection
0x18006e2cc  call    cs:__imp_EnterCriticalSection
0x18006e2d2  mov     [rbp+57h+var_50], 1
0x18006e2d9  mov     [rsi+398h], rdi
0x18006e2e0  mov     [rsi+3A0h], rbx
0x18006e2e7  mov     [rsi+3A8h], r12
0x18006e2ee  xor     ecx, ecx
0x18006e2f0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006e2f5  mov     eax, [rbp+57h+var_50]
0x18006e2f8  test    eax, eax
0x18006e2fa  jz      short loc_18006E309
0x18006e2fc  mov     rcx, r15; lpCriticalSection
0x18006e2ff  call    cs:__imp_LeaveCriticalSection
0x18006e305  mov     [rbp+57h+var_50], r12d
0x18006e309  xor     ecx, ecx
0x18006e30b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006e310  call    cs:__imp_GetTickCount
  ... truncated ...
```
