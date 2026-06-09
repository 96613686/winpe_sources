# WdcComponentData::NotifyEventStart(ushort const *)

- ea: `0x1800287e4`
- end: `0x180028a3e`
- name: `?NotifyEventStart@WdcComponentData@@AEAAJPEBG@Z`
- size: `602`
- prototype: `int(WdcComponentData *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180049170`
- `0x1800494f8`

## callees

- `0x18000b854`
- `0x1800287e4`
- `0x180086010`

## import_xrefs

- `KERNEL32!CreateThread` at `0x1800289a6`
- `KERNEL32!CreateThread` at `0x1800289a6`
- `KERNEL32!CloseHandle` at `0x180028899`
- `KERNEL32!CloseHandle` at `0x180028899`
- `KERNEL32!GetLastError` at `0x1800288cc`
- `KERNEL32!GetLastError` at `0x1800288f6`
- `KERNEL32!GetLastError` at `0x1800289b8`
- `KERNEL32!GetLastError` at `0x1800289da`
- `KERNEL32!GetLastError` at `0x1800288cc`
- `KERNEL32!GetLastError` at `0x1800288f6`
- `KERNEL32!GetLastError` at `0x1800289b8`
- `KERNEL32!GetLastError` at `0x1800289da`
- `KERNEL32!GetCurrentThreadId` at `0x18002886d`
- `KERNEL32!GetCurrentThreadId` at `0x18002886d`
- `KERNEL32!LeaveCriticalSection` at `0x180028a23`
- `KERNEL32!LeaveCriticalSection` at `0x180028a23`
- `KERNEL32!EnterCriticalSection` at `0x180028813`
- `KERNEL32!EnterCriticalSection` at `0x180028813`
- `KERNEL32!CreateEventW` at `0x1800288b4`
- `KERNEL32!CreateEventW` at `0x1800288b4`
- `USER32!SetTimer` at `0x180028867`
- `USER32!SetTimer` at `0x180028867`
- `USER32!KillTimer` at `0x18002884c`
- `USER32!KillTimer` at `0x18002884c`
- `OLEAUT32!__imp_SysAllocString` at `0x180028943`
- `OLEAUT32!__imp_SysAllocString` at `0x180028943`
- `OLEAUT32!__imp_SysFreeString` at `0x180028922`
- `OLEAUT32!__imp_SysFreeString` at `0x180028922`

## string_xrefs

- `0x180028a09`: `WdcComponentData::NotifyEventStart`
- `0x180028a10`: `base\diagnosis\pdui\perfmon\mmc\componentdata.cpp`

## pseudocode

```c
__int64 __fastcall WdcComponentData::NotifyEventStart(WdcComponentData *this, const unsigned __int16 *a2)
{
  int v4; // eax
  signed int v5; // ebx
  DWORD CurrentThreadId; // eax
  char *v7; // rcx
  HANDLE EventW; // rax
  signed int LastError; // eax
  signed int v10; // eax
  OLECHAR *v11; // rcx
  BSTR v12; // rax
  HANDLE v13; // rax
  signed int v14; // eax
  signed int v15; // eax
  __int64 dwCreationFlags; // [rsp+20h] [rbp-28h]
  DWORD dwCreationFlagsa; // [rsp+20h] [rbp-28h]
  DWORD ThreadId; // [rsp+50h] [rbp+8h] BYREF
  HWND hWnd; // [rsp+60h] [rbp+18h] BYREF

  hWnd = 0;
  ThreadId = 0;
  EnterCriticalSection(&g_cs);
  v4 = (*(__int64 (__fastcall **)(_QWORD, HWND *))(**((_QWORD **)this + 9) + 96LL))(*((_QWORD *)this + 9), &hWnd);
  v5 = v4;
  if ( v4 < 0 )
    goto LABEL_36;
  if ( *((_DWORD *)this + 32) )
    KillTimer(hWnd, (UINT_PTR)this + 128);
  SetTimer(hWnd, (UINT_PTR)this + 128, 0x7FFFFFFFu, WdcComponentData::NotifyEvent);
  CurrentThreadId = GetCurrentThreadId();
  v7 = (char *)*((_QWORD *)this + 17);
  *((_DWORD *)this + 32) = CurrentThreadId;
  *((_QWORD *)this + 26) = hWnd;
  *((_QWORD *)this + 25) = this;
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v7);
    *((_QWORD *)this + 17) = 0;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 17) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( !LastError )
      goto LABEL_34;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 < 0 )
      goto LABEL_35;
  }
  if ( *((_QWORD *)this + 17) == -1 )
  {
    v10 = GetLastError();
    v5 = v10;
    if ( !v10 )
      goto LABEL_34;
    if ( v10 > 0 )
      v5 = (unsigned __int16)v10 | 0x80070000;
    if ( v5 < 0 )
      goto LABEL_35;
  }
  v11 = (OLECHAR *)*((_QWORD *)this + 22);
  if ( v11 )
  {
    SysFreeString(v11);
    *((_QWORD *)this + 22) = 0;
  }
  if ( a2 && *a2 )
  {
    v12 = SysAllocString(a2);
    if ( !v12 )
    {
      v5 = -2147024882;
      dwCreationFlagsa = -2147024882;
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
        "WdcAssignString",
        0,
        L"FAILURE: 0x%08x",
        dwCreationFlagsa);
      LODWORD(dwCreationFlags) = -2147024882;
LABEL_37:
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\componentdata.cpp",
        "WdcComponentData::NotifyEventStart",
        0,
        L"FAILURE: 0x%08x",
        dwCreationFlags);
      goto LABEL_38;
    }
    *((_QWORD *)this + 22) = v12;
    v5 = 0;
  }
  v13 = CreateThread(
          0,
          0,
          (LPTHREAD_START_ROUTINE)WdcComponentData::NotifyEventListener,
          (char *)this + 128,
          0,
          &ThreadId);
  *((_QWORD *)this + 18) = v13;
  if ( !v13 )
  {
    v14 = GetLastError();
    v5 = v14;
    if ( !v14 )
      goto LABEL_34;
    if ( v14 > 0 )
      v5 = (unsigned __int16)v14 | 0x80070000;
    if ( v5 < 0 )
      goto LABEL_35;
  }
  if ( *((_QWORD *)this + 18) != -1 )
    goto LABEL_38;
  v15 = GetLastError();
  v5 = v15;
  if ( !v15 )
  {
LABEL_34:
    v5 = -2147467259;
LABEL_35:
    v4 = v5;
LABEL_36:
    LODWORD(dwCreationFlags) = v4;
    goto LABEL_37;
  }
  if ( v15 > 0 )
    v5 = (unsigned __int16)v15 | 0x80070000;
  if ( v5 < 0 )
    goto LABEL_35;
LABEL_38:
  LeaveCriticalSection(&g_cs);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800287e4  mov     rax, rsp
0x1800287e7  mov     [rax+10h], rbx
0x1800287eb  mov     [rax+20h], rbp
0x1800287ef  push    rsi
0x1800287f0  push    rdi
0x1800287f1  push    r15
0x1800287f3  sub     rsp, 30h
0x1800287f7  mov     rdi, rcx
0x1800287fa  mov     qword ptr [rax+18h], 0
0x180028802  lea     rcx, ?g_cs@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180028809  mov     dword ptr [rax+8], 0
0x180028810  mov     rbp, rdx
0x180028813  call    cs:__imp_EnterCriticalSection
0x180028819  mov     rcx, [rdi+48h]
0x18002881d  lea     rdx, [rsp+48h+hWnd]
0x180028822  mov     rax, [rcx]
0x180028825  mov     rax, [rax+60h]
0x180028829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002882e  mov     ebx, eax
0x180028830  test    eax, eax
0x180028832  js      loc_1800289FB
0x180028838  lea     rsi, [rdi+80h]
0x18002883f  cmp     dword ptr [rsi], 0
0x180028842  jz      short loc_180028852
0x180028844  mov     rcx, [rsp+48h+hWnd]; hWnd
0x180028849  mov     rdx, rsi; uIDEvent
0x18002884c  call    cs:__imp_KillTimer
0x180028852  mov     rcx, [rsp+48h+hWnd]; hWnd
0x180028857  lea     r9, ?NotifyEvent@WdcComponentData@@CAXPEAUHWND__@@I_KK@Z; lpTimerFunc
0x18002885e  mov     r8d, 7FFFFFFFh; uElapse
0x180028864  mov     rdx, rsi; nIDEvent
0x180028867  call    cs:__imp_SetTimer
0x18002886d  call    cs:__imp_GetCurrentThreadId
0x180028873  mov     rcx, [rdi+88h]; hObject
0x18002887a  mov     [rsi], eax
0x18002887c  mov     rax, [rsp+48h+hWnd]
0x180028881  mov     [rdi+0D0h], rax
0x180028888  lea     rax, [rcx-1]
0x18002888c  mov     [rdi+0C8h], rdi
0x180028893  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028897  ja      short loc_1800288AA
0x180028899  call    cs:__imp_CloseHandle
0x18002889f  mov     qword ptr [rdi+88h], 0
0x1800288aa  xor     r9d, r9d; lpName
0x1800288ad  xor     r8d, r8d; bInitialState
0x1800288b0  xor     edx, edx; bManualReset
0x1800288b2  xor     ecx, ecx; lpEventAttributes
0x1800288b4  call    cs:__imp_CreateEventW
0x1800288ba  mov     [rdi+88h], rax
0x1800288c1  mov     r15d, 80070000h
0x1800288c7  test    rax, rax
0x1800288ca  jnz     short loc_1800288EC
0x1800288cc  call    cs:__imp_GetLastError
0x1800288d2  mov     ebx, eax
0x1800288d4  test    eax, eax
0x1800288d6  jz      loc_1800289F4
0x1800288dc  jle     short loc_1800288E4
0x1800288de  movzx   ebx, ax
0x1800288e1  or      ebx, r15d
0x1800288e4  test    ebx, ebx
0x1800288e6  js      loc_1800289F9
0x1800288ec  cmp     qword ptr [rdi+88h], 0FFFFFFFFFFFFFFFFh
0x1800288f4  jnz     short loc_180028916
0x1800288f6  call    cs:__imp_GetLastError
0x1800288fc  mov     ebx, eax
0x1800288fe  test    eax, eax
0x180028900  jz      loc_1800289F4
0x180028906  jle     short loc_18002890E
0x180028908  movzx   ebx, ax
0x18002890b  or      ebx, r15d
0x18002890e  test    ebx, ebx
0x180028910  js      loc_1800289F9
0x180028916  mov     rcx, [rdi+0B0h]; bstrString
0x18002891d  test    rcx, rcx
0x180028920  jz      short loc_180028933
0x180028922  call    cs:__imp_SysFreeString
0x180028928  mov     qword ptr [rdi+0B0h], 0
0x180028933  test    rbp, rbp
0x180028936  jz      short loc_180028986
0x180028938  xor     eax, eax
0x18002893a  cmp     ax, [rbp+0]
0x18002893e  jz      short loc_180028986
0x180028940  mov     rcx, rbp; psz
0x180028943  call    cs:__imp_SysAllocString
0x180028949  test    rax, rax
0x18002894c  jnz     short loc_18002897D
0x18002894e  mov     ebx, 8007000Eh
0x180028953  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002895a  xor     r8d, r8d; int
0x18002895d  mov     dword ptr [rsp+48h+dwCreationFlags], ebx
0x180028961  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x180028968  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x18002896f  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180028974  mov     dword ptr [rsp+48h+dwCreationFlags], ebx
0x180028978  jmp     loc_1800289FF
0x18002897d  mov     [rdi+0B0h], rax
0x180028984  xor     ebx, ebx
0x180028986  lea     rax, [rsp+48h+ThreadId]
0x18002898b  mov     r9, rsi; lpParameter
0x18002898e  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x180028993  lea     r8, ?NotifyEventListener@WdcComponentData@@CAKPEAX@Z; lpStartAddress
0x18002899a  xor     edx, edx; dwStackSize
0x18002899c  mov     dword ptr [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x1800289a4  xor     ecx, ecx; lpThreadAttributes
0x1800289a6  call    cs:__imp_CreateThread
0x1800289ac  mov     [rdi+90h], rax
0x1800289b3  test    rax, rax
0x1800289b6  jnz     short loc_1800289D0
0x1800289b8  call    cs:__imp_GetLastError
0x1800289be  mov     ebx, eax
0x1800289c0  test    eax, eax
0x1800289c2  jz      short loc_1800289F4
0x1800289c4  jle     short loc_1800289CC
0x1800289c6  movzx   ebx, ax
0x1800289c9  or      ebx, r15d
0x1800289cc  test    ebx, ebx
0x1800289ce  js      short loc_1800289F9
0x1800289d0  cmp     qword ptr [rdi+90h], 0FFFFFFFFFFFFFFFFh
0x1800289d8  jnz     short loc_180028A1C
0x1800289da  call    cs:__imp_GetLastError
0x1800289e0  mov     ebx, eax
0x1800289e2  test    eax, eax
0x1800289e4  jz      short loc_1800289F4
0x1800289e6  jle     short loc_1800289EE
0x1800289e8  movzx   ebx, ax
0x1800289eb  or      ebx, r15d
0x1800289ee  test    ebx, ebx
0x1800289f0  jns     short loc_180028A1C
0x1800289f2  jmp     short loc_1800289F9
0x1800289f4  mov     ebx, 80004005h
0x1800289f9  mov     eax, ebx
0x1800289fb  mov     dword ptr [rsp+48h+dwCreationFlags], eax
0x1800289ff  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180028a06  xor     r8d, r8d; int
0x180028a09  lea     rdx, aWdccomponentda_8; "WdcComponentData::NotifyEventStart"
0x180028a10  lea     rcx, aBaseDiagnosisP_41; "base\\diagnosis\\pdui\\perfmon\\mmc\\co"...
0x180028a17  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180028a1c  lea     rcx, ?g_cs@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180028a23  call    cs:__imp_LeaveCriticalSection
0x180028a29  mov     rbp, [rsp+48h+arg_18]
0x180028a2e  mov     eax, ebx
0x180028a30  mov     rbx, [rsp+48h+arg_8]
0x180028a35  add     rsp, 30h
0x180028a39  pop     r15
0x180028a3b  pop     rdi
0x180028a3c  pop     rsi
0x180028a3d  retn
```
