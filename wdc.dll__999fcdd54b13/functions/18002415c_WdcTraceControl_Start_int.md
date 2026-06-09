# WdcTraceControl::Start(int)

- ea: `0x18002415c`
- end: `0x180024667`
- name: `?Start@WdcTraceControl@@QEAAJH@Z`
- size: `1291`
- prototype: `__int64 __fastcall(WdcTraceControl *__hidden this, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800713bc`

## callees

- `0x18000b854`
- `0x1800150d0`
- `0x180016880`
- `0x18002415c`
- `0x18002a3b4`
- `0x18002b190`
- `0x180030770`
- `0x180036504`
- `0x18003987c`
- `0x180086010`

## import_xrefs

- `KERNEL32!CreateThread` at `0x1800243de`
- `KERNEL32!CreateThread` at `0x1800244e3`
- `KERNEL32!CreateThread` at `0x180024558`
- `KERNEL32!CreateThread` at `0x1800245c5`
- `KERNEL32!CreateThread` at `0x1800243de`
- `KERNEL32!CreateThread` at `0x1800244e3`
- `KERNEL32!CreateThread` at `0x180024558`
- `KERNEL32!CreateThread` at `0x1800245c5`
- `KERNEL32!CloseHandle` at `0x18002464e`
- `KERNEL32!CloseHandle` at `0x18002464e`
- `KERNEL32!GetLastError` at `0x1800241e1`
- `KERNEL32!GetLastError` at `0x180024208`
- `KERNEL32!GetLastError` at `0x180024241`
- `KERNEL32!GetLastError` at `0x180024260`
- `KERNEL32!GetLastError` at `0x1800242f4`
- `KERNEL32!GetLastError` at `0x180024313`
- `KERNEL32!GetLastError` at `0x1800243ed`
- `KERNEL32!GetLastError` at `0x180024414`
- `KERNEL32!GetLastError` at `0x180024468`
- `KERNEL32!GetLastError` at `0x1800244a4`
- `KERNEL32!GetLastError` at `0x1800244f2`
- `KERNEL32!GetLastError` at `0x180024519`
- `KERNEL32!GetLastError` at `0x180024567`
- `KERNEL32!GetLastError` at `0x18002458e`
- `KERNEL32!GetLastError` at `0x1800245d4`
- `KERNEL32!GetLastError` at `0x1800245f3`
- `KERNEL32!GetLastError` at `0x1800241e1`
- `KERNEL32!GetLastError` at `0x180024208`
- `KERNEL32!GetLastError` at `0x180024241`
- `KERNEL32!GetLastError` at `0x180024260`
- `KERNEL32!GetLastError` at `0x1800242f4`
- `KERNEL32!GetLastError` at `0x180024313`
- `KERNEL32!GetLastError` at `0x1800243ed`
- `KERNEL32!GetLastError` at `0x180024414`
- `KERNEL32!GetLastError` at `0x180024468`
- `KERNEL32!GetLastError` at `0x1800244a4`
- `KERNEL32!GetLastError` at `0x1800244f2`
- `KERNEL32!GetLastError` at `0x180024519`
- `KERNEL32!GetLastError` at `0x180024567`
- `KERNEL32!GetLastError` at `0x18002458e`
- `KERNEL32!GetLastError` at `0x1800245d4`
- `KERNEL32!GetLastError` at `0x1800245f3`
- `KERNEL32!CreateEventW` at `0x1800241cc`
- `KERNEL32!CreateEventW` at `0x180024232`
- `KERNEL32!CreateEventW` at `0x1800242e5`
- `KERNEL32!CreateEventW` at `0x1800241cc`
- `KERNEL32!CreateEventW` at `0x180024232`
- `KERNEL32!CreateEventW` at `0x1800242e5`
- `KERNEL32!SetThreadPriority` at `0x180024496`
- `KERNEL32!SetThreadPriority` at `0x180024496`
- `KERNEL32!GetCurrentThread` at `0x180024488`
- `KERNEL32!GetCurrentThread` at `0x180024488`
- `USER32!SetTimer` at `0x18002445d`
- `USER32!SetTimer` at `0x18002445d`

## pseudocode

```c
__int64 __fastcall WdcTraceControl::Start(WdcDataMonitor **this, int a2)
{
  WdcDataMonitor *v2; // rax
  char *v3; // r14
  int v6; // eax
  signed int v7; // ebx
  WdcDataMonitor *EventW; // rax
  signed int LastError; // eax
  signed int v10; // eax
  WdcDataMonitor *v11; // rax
  signed int v12; // eax
  signed int v13; // eax
  int v14; // eax
  signed int v15; // eax
  WdcDataMonitor *v16; // rax
  signed int v17; // eax
  signed int v18; // eax
  WdcDataMonitor *v19; // rax
  signed int v20; // eax
  signed int v21; // eax
  UINT_PTR v22; // rbx
  HWND v23; // rax
  signed int v24; // eax
  HANDLE CurrentThread; // rax
  signed int v26; // eax
  WdcDataMonitor *v27; // rax
  signed int v28; // eax
  signed int v29; // eax
  WdcDataMonitor *v30; // rax
  signed int v31; // eax
  signed int v32; // eax
  WdcDataMonitor *v33; // rax
  signed int v34; // eax
  signed int v35; // eax
  __int64 dwCreationFlags; // [rsp+20h] [rbp-10h]
  DWORD ThreadId; // [rsp+60h] [rbp+30h] BYREF
  int v39; // [rsp+70h] [rbp+40h] BYREF
  void *v40; // [rsp+78h] [rbp+48h] BYREF

  v2 = *this;
  v3 = 0;
  ThreadId = 0;
  v39 = 0;
  v40 = 0;
  v6 = (*((__int64 (__fastcall **)(WdcDataMonitor **))v2 + 1))(this);
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_95;
  WdcAdjustPrivilege();
  WdcLockObject::LockEnter((WdcLockObject *)this, &v39);
  if ( this[8] )
  {
    v7 = -2147467259;
    goto LABEL_97;
  }
  EventW = (WdcDataMonitor *)CreateEventW(0, 1, 0, 0);
  this[9] = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( !LastError )
      goto LABEL_26;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 < 0 )
      goto LABEL_27;
  }
  if ( this[9] == (WdcDataMonitor *)-1LL )
  {
    v10 = GetLastError();
    v7 = v10;
    if ( !v10 )
      goto LABEL_26;
    if ( v10 > 0 )
      v7 = (unsigned __int16)v10 | 0x80070000;
    if ( v7 < 0 )
      goto LABEL_27;
  }
  v11 = (WdcDataMonitor *)CreateEventW(0, 0, 0, 0);
  this[13] = v11;
  if ( !v11 )
  {
    v12 = GetLastError();
    v7 = v12;
    if ( !v12 )
      goto LABEL_26;
    if ( v12 > 0 )
      v7 = (unsigned __int16)v12 | 0x80070000;
    if ( v7 < 0 )
      goto LABEL_27;
  }
  if ( this[13] == (WdcDataMonitor *)-1LL )
  {
    v13 = GetLastError();
    v7 = v13;
    if ( !v13 )
      goto LABEL_26;
    if ( v13 > 0 )
      v7 = (unsigned __int16)v13 | 0x80070000;
    if ( v7 < 0 )
      goto LABEL_27;
  }
  v14 = WdcAcquireMutex(&v40);
  v7 = v14;
  if ( v14 < 0 )
  {
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\control.cpp",
      "WdcTraceControl::Start",
      0,
      L"FAILURE: 0x%08x",
      v14);
    v3 = (char *)v40;
    goto LABEL_97;
  }
  v15 = WdcTraceControl::TraceStart((WdcTraceControl *)this);
  v3 = (char *)v40;
  v7 = v15;
  WdcReleaseMutex(v40);
  if ( v7 < 0 )
    goto LABEL_27;
  v16 = (WdcDataMonitor *)CreateEventW(0, 1, 0, 0);
  this[10] = v16;
  if ( !v16 )
  {
    v17 = GetLastError();
    v7 = v17;
    if ( !v17 )
      goto LABEL_26;
    if ( v17 > 0 )
      v7 = (unsigned __int16)v17 | 0x80070000;
    if ( v7 < 0 )
      goto LABEL_27;
  }
  if ( this[10] == (WdcDataMonitor *)-1LL )
  {
    v18 = GetLastError();
    v7 = v18;
    if ( !v18 )
      goto LABEL_26;
    if ( v18 > 0 )
      v7 = (unsigned __int16)v18 | 0x80070000;
    if ( v7 < 0 )
      goto LABEL_27;
  }
  WdcDataMonitor::Start(this[16]);
  WdcDataMonitor::Start(this[17]);
  WdcDataMonitor::Start(this[18]);
  WdcDataMonitor::Start(this[19]);
  WdcDataMonitor::Start(this[20]);
  if ( !a2 )
  {
    WdcDataMonitor::Start(this[21]);
    WdcDataMonitor::Start(this[22]);
  }
  WdcDataMonitor::Start(this[24]);
  WdcDataMonitor::Start(this[25]);
  WdcDataMonitor::Start(this[26]);
  WdcDataMonitor::Start(this[27]);
  WdcDataMonitor::Start(this[23]);
  v19 = (WdcDataMonitor *)CreateThread(0, 0, WdcTraceControl::TraceThread, this, 0, &ThreadId);
  this[8] = v19;
  if ( v19 )
    goto LABEL_46;
  v20 = GetLastError();
  v7 = v20;
  if ( !v20 )
  {
LABEL_26:
    v7 = -2147467259;
LABEL_27:
    LODWORD(dwCreationFlags) = v7;
LABEL_96:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\control.cpp",
      "WdcTraceControl::Start",
      0,
      L"FAILURE: 0x%08x",
      dwCreationFlags);
    goto LABEL_97;
  }
  if ( v20 > 0 )
    v7 = (unsigned __int16)v20 | 0x80070000;
  if ( v7 < 0 )
    goto LABEL_27;
LABEL_46:
  if ( this[8] != (WdcDataMonitor *)-1LL )
    goto LABEL_51;
  v21 = GetLastError();
  v7 = v21;
  if ( !v21 )
    goto LABEL_26;
  if ( v21 > 0 )
    v7 = (unsigned __int16)v21 | 0x80070000;
  if ( v7 < 0 )
    goto LABEL_27;
LABEL_51:
  v22 = (UINT_PTR)this[15];
  v23 = (HWND)(*(__int64 (__fastcall **)(UINT_PTR))(*(_QWORD *)v22 + 360LL))(v22);
  if ( !SetTimer(v23, v22, 0x3E8u, WdcMonitor::UpdateTimer) )
  {
    v24 = GetLastError();
    v7 = v24;
    if ( !v24 )
      goto LABEL_93;
    if ( v24 > 0 )
      v7 = (unsigned __int16)v24 | 0x80070000;
    if ( v7 < 0 )
      goto LABEL_94;
  }
  CurrentThread = GetCurrentThread();
  if ( SetThreadPriority(CurrentThread, 1) )
  {
    v7 = 0;
  }
  else
  {
    v26 = GetLastError();
    v7 = v26;
    if ( !v26 )
      goto LABEL_93;
    if ( v26 > 0 )
      v7 = (unsigned __int16)v26 | 0x80070000;
    if ( v7 < 0 )
      goto LABEL_94;
  }
  v27 = (WdcDataMonitor *)CreateThread(
                            0,
                            0,
                            (LPTHREAD_START_ROUTINE)WdcTraceControl::AutoStopThread,
                            this,
                            0,
                            &ThreadId);
  this[11] = v27;
  if ( !v27 )
  {
    v28 = GetLastError();
    v7 = v28;
    if ( !v28 )
      goto LABEL_93;
    if ( v28 > 0 )
      v7 = (unsigned __int16)v28 | 0x80070000;
    if ( v7 < 0 )
      goto LABEL_94;
  }
  if ( this[11] == (WdcDataMonitor *)-1LL )
  {
    v29 = GetLastError();
    v7 = v29;
    if ( !v29 )
      goto LABEL_93;
    if ( v29 > 0 )
      v7 = (unsigned __int16)v29 | 0x80070000;
    if ( v7 < 0 )
      goto LABEL_94;
  }
  v30 = (WdcDataMonitor *)CreateThread(0, 0, WdcTraceControl::QueryThread, this, 0, &ThreadId);
  this[12] = v30;
  if ( !v30 )
  {
    v31 = GetLastError();
    v7 = v31;
    if ( !v31 )
      goto LABEL_93;
    if ( v31 > 0 )
      v7 = (unsigned __int16)v31 | 0x80070000;
    if ( v7 < 0 )
      goto LABEL_94;
  }
  if ( this[12] == (WdcDataMonitor *)-1LL )
  {
    v32 = GetLastError();
    v7 = v32;
    if ( !v32 )
      goto LABEL_93;
    if ( v32 > 0 )
      v7 = (unsigned __int16)v32 | 0x80070000;
    if ( v7 < 0 )
      goto LABEL_94;
  }
  v33 = (WdcDataMonitor *)CreateThread(0, 0, WdcTraceControl::IncrementThread, this, 0, &ThreadId);
  this[14] = v33;
  if ( v33 )
    goto LABEL_87;
  v34 = GetLastError();
  v7 = v34;
  if ( !v34 )
  {
LABEL_93:
    v7 = -2147467259;
LABEL_94:
    v6 = v7;
LABEL_95:
    LODWORD(dwCreationFlags) = v6;
    goto LABEL_96;
  }
  if ( v34 > 0 )
    v7 = (unsigned __int16)v34 | 0x80070000;
  if ( v7 < 0 )
    goto LABEL_94;
LABEL_87:
  if ( this[14] != (WdcDataMonitor *)-1LL )
    goto LABEL_97;
  v35 = GetLastError();
  v7 = v35;
  if ( !v35 )
    goto LABEL_93;
  if ( v35 > 0 )
    v7 = (unsigned __int16)v35 | 0x80070000;
  if ( v7 < 0 )
    goto LABEL_94;
LABEL_97:
  WdcLockObject::LockLeave((WdcLockObject *)this, &v39);
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v3);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002415c  mov     [rsp-28h+arg_8], rbx
0x180024161  push    rbp
0x180024162  push    rsi
0x180024163  push    rdi
0x180024164  push    r12
0x180024166  push    r14
0x180024168  mov     rbp, rsp
0x18002416b  sub     rsp, 30h
0x18002416f  mov     rax, [rcx]
0x180024172  xor     r14d, r14d
0x180024175  mov     esi, edx
0x180024177  mov     [rbp+ThreadId], 0
0x18002417e  mov     rdi, rcx
0x180024181  mov     [rbp+arg_10], 0
0x180024188  mov     [rbp+arg_18], r14
0x18002418c  mov     rax, [rax+8]
0x180024190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024195  mov     ebx, eax
0x180024197  test    eax, eax
0x180024199  js      loc_180024614
0x18002419f  call    ?WdcAdjustPrivilege@@YAJXZ; WdcAdjustPrivilege(void)
0x1800241a4  lea     rdx, [rbp+arg_10]; int *
0x1800241a8  mov     rcx, rdi; this
0x1800241ab  call    ?LockEnter@WdcLockObject@@QEAAXPEAH@Z; WdcLockObject::LockEnter(int *)
0x1800241b0  cmp     [rdi+40h], r14
0x1800241b4  jz      short loc_1800241C0
0x1800241b6  mov     ebx, 80004005h
0x1800241bb  jmp     loc_180024635
0x1800241c0  xor     r9d, r9d; lpName
0x1800241c3  xor     r8d, r8d; bInitialState
0x1800241c6  xor     ecx, ecx; lpEventAttributes
0x1800241c8  lea     edx, [r9+1]; bManualReset
0x1800241cc  call    cs:__imp_CreateEventW
0x1800241d2  mov     [rdi+48h], rax
0x1800241d6  mov     r12d, 80070000h
0x1800241dc  test    rax, rax
0x1800241df  jnz     short loc_180024201
0x1800241e1  call    cs:__imp_GetLastError
0x1800241e7  mov     ebx, eax
0x1800241e9  test    eax, eax
0x1800241eb  jz      loc_1800242B1
0x1800241f1  jle     short loc_1800241F9
0x1800241f3  movzx   ebx, ax
0x1800241f6  or      ebx, r12d
0x1800241f9  test    ebx, ebx
0x1800241fb  js      loc_1800242B6
0x180024201  cmp     qword ptr [rdi+48h], 0FFFFFFFFFFFFFFFFh
0x180024206  jnz     short loc_180024228
0x180024208  call    cs:__imp_GetLastError
0x18002420e  mov     ebx, eax
0x180024210  test    eax, eax
0x180024212  jz      loc_1800242B1
0x180024218  jle     short loc_180024220
0x18002421a  movzx   ebx, ax
0x18002421d  or      ebx, r12d
0x180024220  test    ebx, ebx
0x180024222  js      loc_1800242B6
0x180024228  xor     r9d, r9d; lpName
0x18002422b  xor     r8d, r8d; bInitialState
0x18002422e  xor     edx, edx; bManualReset
0x180024230  xor     ecx, ecx; lpEventAttributes
0x180024232  call    cs:__imp_CreateEventW
0x180024238  mov     [rdi+68h], rax
0x18002423c  test    rax, rax
0x18002423f  jnz     short loc_180024259
0x180024241  call    cs:__imp_GetLastError
0x180024247  mov     ebx, eax
0x180024249  test    eax, eax
0x18002424b  jz      short loc_1800242B1
0x18002424d  jle     short loc_180024255
0x18002424f  movzx   ebx, ax
0x180024252  or      ebx, r12d
0x180024255  test    ebx, ebx
0x180024257  js      short loc_1800242B6
0x180024259  cmp     qword ptr [rdi+68h], 0FFFFFFFFFFFFFFFFh
0x18002425e  jnz     short loc_180024278
0x180024260  call    cs:__imp_GetLastError
0x180024266  mov     ebx, eax
0x180024268  test    eax, eax
0x18002426a  jz      short loc_1800242B1
0x18002426c  jle     short loc_180024274
0x18002426e  movzx   ebx, ax
0x180024271  or      ebx, r12d
0x180024274  test    ebx, ebx
0x180024276  js      short loc_1800242B6
0x180024278  lea     rcx, [rbp+arg_18]; void **
0x18002427c  call    ?WdcAcquireMutex@@YAJPEAPEAX@Z; WdcAcquireMutex(void * *)
0x180024281  mov     ebx, eax
0x180024283  test    eax, eax
0x180024285  jns     short loc_1800242BF
0x180024287  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002428e  mov     dword ptr [rsp+30h+dwCreationFlags], eax
0x180024292  xor     r8d, r8d; int
0x180024295  lea     rdx, aWdctracecontro; "WdcTraceControl::Start"
0x18002429c  lea     rcx, aBaseDiagnosisP_37; "base\\diagnosis\\pdui\\perfmon\\mon\\co"...
0x1800242a3  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800242a8  mov     r14, [rbp+arg_18]
0x1800242ac  jmp     loc_180024635
0x1800242b1  mov     ebx, 80004005h
0x1800242b6  mov     dword ptr [rsp+30h+dwCreationFlags], ebx
0x1800242ba  jmp     loc_180024618
0x1800242bf  mov     rcx, rdi; this
0x1800242c2  call    ?TraceStart@WdcTraceControl@@AEAAJXZ; WdcTraceControl::TraceStart(void)
0x1800242c7  mov     r14, [rbp+arg_18]
0x1800242cb  mov     ebx, eax
0x1800242cd  mov     rcx, r14; void *
0x1800242d0  call    ?WdcReleaseMutex@@YAJPEAX@Z; WdcReleaseMutex(void *)
0x1800242d5  test    ebx, ebx
0x1800242d7  js      short loc_1800242B6
0x1800242d9  xor     r9d, r9d; lpName
0x1800242dc  xor     r8d, r8d; bInitialState
0x1800242df  xor     ecx, ecx; lpEventAttributes
0x1800242e1  lea     edx, [r9+1]; bManualReset
0x1800242e5  call    cs:__imp_CreateEventW
0x1800242eb  mov     [rdi+50h], rax
0x1800242ef  test    rax, rax
0x1800242f2  jnz     short loc_18002430C
0x1800242f4  call    cs:__imp_GetLastError
0x1800242fa  mov     ebx, eax
0x1800242fc  test    eax, eax
0x1800242fe  jz      short loc_1800242B1
0x180024300  jle     short loc_180024308
0x180024302  movzx   ebx, ax
0x180024305  or      ebx, r12d
0x180024308  test    ebx, ebx
0x18002430a  js      short loc_1800242B6
0x18002430c  cmp     qword ptr [rdi+50h], 0FFFFFFFFFFFFFFFFh
0x180024311  jnz     short loc_18002432B
0x180024313  call    cs:__imp_GetLastError
0x180024319  mov     ebx, eax
0x18002431b  test    eax, eax
0x18002431d  jz      short loc_1800242B1
0x18002431f  jle     short loc_180024327
0x180024321  movzx   ebx, ax
0x180024324  or      ebx, r12d
0x180024327  test    ebx, ebx
0x180024329  js      short loc_1800242B6
0x18002432b  mov     rcx, [rdi+80h]; this
0x180024332  call    ?Start@WdcDataMonitor@@QEAAJXZ; WdcDataMonitor::Start(void)
0x180024337  mov     rcx, [rdi+88h]; this
0x18002433e  call    ?Start@WdcDataMonitor@@QEAAJXZ; WdcDataMonitor::Start(void)
0x180024343  mov     rcx, [rdi+90h]; this
0x18002434a  call    ?Start@WdcDataMonitor@@QEAAJXZ; WdcDataMonitor::Start(void)
0x18002434f  mov     rcx, [rdi+98h]; this
0x180024356  call    ?Start@WdcDataMonitor@@QEAAJXZ; WdcDataMonitor::Start(void)
0x18002435b  mov     rcx, [rdi+0A0h]; this
0x180024362  call    ?Start@WdcDataMonitor@@QEAAJXZ; WdcDataMonitor::Start(void)
0x180024367  test    esi, esi
0x180024369  jnz     short loc_180024383
0x18002436b  mov     rcx, [rdi+0A8h]; this
0x180024372  call    ?Start@WdcDataMonitor@@QEAAJXZ; WdcDataMonitor::Start(void)
0x180024377  mov     rcx, [rdi+0B0h]; this
0x18002437e  call    ?Start@WdcDataMonitor@@QEAAJXZ; WdcDataMonitor::Start(void)
0x180024383  mov     rcx, [rdi+0C0h]; this
0x18002438a  call    ?Start@WdcDataMonitor@@QEAAJXZ; WdcDataMonitor::Start(void)
0x18002438f  mov     rcx, [rdi+0C8h]; this
0x180024396  call    ?Start@WdcDataMonitor@@QEAAJXZ; WdcDataMonitor::Start(void)
0x18002439b  mov     rcx, [rdi+0D0h]; this
0x1800243a2  call    ?Start@WdcDataMonitor@@QEAAJXZ; WdcDataMonitor::Start(void)
0x1800243a7  mov     rcx, [rdi+0D8h]; this
0x1800243ae  call    ?Start@WdcDataMonitor@@QEAAJXZ; WdcDataMonitor::Start(void)
0x1800243b3  mov     rcx, [rdi+0B8h]; this
0x1800243ba  call    ?Start@WdcDataMonitor@@QEAAJXZ; WdcDataMonitor::Start(void)
0x1800243bf  lea     rax, [rbp+ThreadId]
0x1800243c3  mov     r9, rdi; lpParameter
0x1800243c6  mov     [rsp+30h+lpThreadId], rax; lpThreadId
0x1800243cb  lea     r8, ?TraceThread@WdcTraceControl@@CAKPEAX@Z; lpStartAddress
0x1800243d2  xor     edx, edx; dwStackSize
0x1800243d4  mov     dword ptr [rsp+30h+dwCreationFlags], 0; dwCreationFlags
0x1800243dc  xor     ecx, ecx; lpThreadAttributes
0x1800243de  call    cs:__imp_CreateThread
0x1800243e4  mov     [rdi+40h], rax
0x1800243e8  test    rax, rax
0x1800243eb  jnz     short loc_18002440D
0x1800243ed  call    cs:__imp_GetLastError
0x1800243f3  mov     ebx, eax
0x1800243f5  test    eax, eax
0x1800243f7  jz      loc_1800242B1
0x1800243fd  jle     short loc_180024405
0x1800243ff  movzx   ebx, ax
0x180024402  or      ebx, r12d
0x180024405  test    ebx, ebx
0x180024407  js      loc_1800242B6
0x18002440d  cmp     qword ptr [rdi+40h], 0FFFFFFFFFFFFFFFFh
0x180024412  jnz     short loc_180024434
0x180024414  call    cs:__imp_GetLastError
0x18002441a  mov     ebx, eax
0x18002441c  test    eax, eax
0x18002441e  jz      loc_1800242B1
0x180024424  jle     short loc_18002442C
0x180024426  movzx   ebx, ax
0x180024429  or      ebx, r12d
0x18002442c  test    ebx, ebx
0x18002442e  js      loc_1800242B6
0x180024434  mov     rbx, [rdi+78h]
0x180024438  mov     rcx, rbx
0x18002443b  mov     rax, [rbx]
0x18002443e  mov     rax, [rax+168h]
0x180024445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002444a  lea     r9, ?UpdateTimer@WdcMonitor@@SAXPEAUHWND__@@I_KK@Z; lpTimerFunc
0x180024451  mov     r8d, 3E8h; uElapse
0x180024457  mov     rdx, rbx; nIDEvent
0x18002445a  mov     rcx, rax; hWnd
0x18002445d  call    cs:__imp_SetTimer
0x180024463  test    rax, rax
0x180024466  jnz     short loc_180024488
0x180024468  call    cs:__imp_GetLastError
0x18002446e  mov     ebx, eax
0x180024470  test    eax, eax
0x180024472  jz      loc_18002460D
0x180024478  jle     short loc_180024480
0x18002447a  movzx   ebx, ax
0x18002447d  or      ebx, r12d
0x180024480  test    ebx, ebx
0x180024482  js      loc_180024612
0x180024488  call    cs:__imp_GetCurrentThread
0x18002448e  mov     rcx, rax; hThread
0x180024491  mov     edx, 1; nPriority
0x180024496  call    cs:__imp_SetThreadPriority
0x18002449c  test    eax, eax
0x18002449e  jz      short loc_1800244A4
0x1800244a0  xor     ebx, ebx
0x1800244a2  jmp     short loc_1800244C4
0x1800244a4  call    cs:__imp_GetLastError
0x1800244aa  mov     ebx, eax
0x1800244ac  test    eax, eax
0x1800244ae  jz      loc_18002460D
0x1800244b4  jle     short loc_1800244BC
0x1800244b6  movzx   ebx, ax
0x1800244b9  or      ebx, r12d
0x1800244bc  test    ebx, ebx
0x1800244be  js      loc_180024612
0x1800244c4  lea     rax, [rbp+ThreadId]
0x1800244c8  mov     r9, rdi; lpParameter
0x1800244cb  mov     [rsp+30h+lpThreadId], rax; lpThreadId
0x1800244d0  lea     r8, ?AutoStopThread@WdcTraceControl@@CAKPEAX@Z; lpStartAddress
0x1800244d7  xor     edx, edx; dwStackSize
0x1800244d9  mov     dword ptr [rsp+30h+dwCreationFlags], 0; dwCreationFlags
0x1800244e1  xor     ecx, ecx; lpThreadAttributes
0x1800244e3  call    cs:__imp_CreateThread
0x1800244e9  mov     [rdi+58h], rax
0x1800244ed  test    rax, rax
0x1800244f0  jnz     short loc_180024512
0x1800244f2  call    cs:__imp_GetLastError
0x1800244f8  mov     ebx, eax
0x1800244fa  test    eax, eax
0x1800244fc  jz      loc_18002460D
0x180024502  jle     short loc_18002450A
0x180024504  movzx   ebx, ax
0x180024507  or      ebx, r12d
0x18002450a  test    ebx, ebx
0x18002450c  js      loc_180024612
0x180024512  cmp     qword ptr [rdi+58h], 0FFFFFFFFFFFFFFFFh
0x180024517  jnz     short loc_180024539
0x180024519  call    cs:__imp_GetLastError
0x18002451f  mov     ebx, eax
0x180024521  test    eax, eax
0x180024523  jz      loc_18002460D
0x180024529  jle     short loc_180024531
0x18002452b  movzx   ebx, ax
0x18002452e  or      ebx, r12d
0x180024531  test    ebx, ebx
0x180024533  js      loc_180024612
0x180024539  lea     rax, [rbp+ThreadId]
0x18002453d  mov     r9, rdi; lpParameter
0x180024540  mov     [rsp+30h+lpThreadId], rax; lpThreadId
0x180024545  lea     r8, ?QueryThread@WdcTraceControl@@CAKPEAX@Z; lpStartAddress
0x18002454c  xor     edx, edx; dwStackSize
0x18002454e  mov     dword ptr [rsp+30h+dwCreationFlags], 0; dwCreationFlags
0x180024556  xor     ecx, ecx; lpThreadAttributes
0x180024558  call    cs:__imp_CreateThread
0x18002455e  mov     [rdi+60h], rax
0x180024562  test    rax, rax
0x180024565  jnz     short loc_180024587
0x180024567  call    cs:__imp_GetLastError
0x18002456d  mov     ebx, eax
0x18002456f  test    eax, eax
0x180024571  jz      loc_18002460D
0x180024577  jle     short loc_18002457F
0x180024579  movzx   ebx, ax
0x18002457c  or      ebx, r12d
0x18002457f  test    ebx, ebx
0x180024581  js      loc_180024612
0x180024587  cmp     qword ptr [rdi+60h], 0FFFFFFFFFFFFFFFFh
0x18002458c  jnz     short loc_1800245A6
0x18002458e  call    cs:__imp_GetLastError
0x180024594  mov     ebx, eax
0x180024596  test    eax, eax
0x180024598  jz      short loc_18002460D
0x18002459a  jle     short loc_1800245A2
0x18002459c  movzx   ebx, ax
0x18002459f  or      ebx, r12d
0x1800245a2  test    ebx, ebx
0x1800245a4  js      short loc_180024612
0x1800245a6  lea     rax, [rbp+ThreadId]
0x1800245aa  mov     r9, rdi; lpParameter
0x1800245ad  mov     [rsp+30h+lpThreadId], rax; lpThreadId
0x1800245b2  lea     r8, ?IncrementThread@WdcTraceControl@@CAKPEAX@Z; lpStartAddress
0x1800245b9  xor     edx, edx; dwStackSize
0x1800245bb  mov     dword ptr [rsp+30h+dwCreationFlags], 0; dwCreationFlags
  ... truncated ...
```
