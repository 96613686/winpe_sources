# CtrlHandle(ulong)

- ea: `0x140001840`
- end: `0x140001a17`
- name: `?CtrlHandle@@YAXK@Z`
- size: `471`
- prototype: `void __fastcall(DWORD CtrlType)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001840`
- `0x140001fa0`
- `0x140001ff8`
- `0x140004010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001897`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400018b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001909`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001922`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000199f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001897`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400018b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001909`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001922`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000199f`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140001a07`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140001a07`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140001887`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140001887`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400018fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400018fb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140001949`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140001949`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400019dc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400019dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400019e9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400019e9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000198b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400019cd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000198b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400019cd`
- `iisutil!PuDbgPrint` at `0x1400018e6`
- `iisutil!PuDbgPrint` at `0x1400018e6`

## string_xrefs

- `0x1400018da`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wp\w3wp.cxx`
- `0x140001878`: `hwebcore.dll`
- `0x1400018c0`: `\nError loading hwebcore dll '%ws'.  Error = %d\n`

## pseudocode

```c
void __fastcall CtrlHandle(DWORD CtrlType)
{
  DWORD v1; // ecx
  DWORD v2; // ecx
  HMODULE Library; // rax
  signed int v4; // ebx
  FARPROC ProcAddress; // rsi
  unsigned int v6; // edi
  DWORD v7; // [rsp+30h] [rbp-38h]
  DWORD LastError; // [rsp+30h] [rbp-38h]
  struct _FILETIME pftDueTime; // [rsp+78h] [rbp+10h] BYREF

  pftDueTime = 0;
  if ( !CtrlType || (v1 = CtrlType - 1) == 0 || (v2 = v1 - 1) == 0 || v2 - 3 <= 1 )
  {
    PrintResourceString(0x61ABu);
    Library = LoadLibraryExW(L"hwebcore.dll", 0, 0);
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "WebCoreShutdown");
      if ( ProcAddress )
      {
        v4 = 0;
        g_pTimer = CreateThreadpoolTimer(TimerCallback, 0, 0);
        if ( g_pTimer )
        {
          v6 = 0;
          pftDueTime = (struct _FILETIME)(-10000000LL * g_dwShutDownTimeout);
          SetThreadpoolTimer(g_pTimer, &pftDueTime, 0, 0);
        }
        else
        {
          v6 = 1;
        }
        if ( ((int (__fastcall *)(_QWORD))ProcAddress)(v6) < 0 )
          v4 = GetLastError() | 0x10000000;
      }
      else
      {
        v4 = GetLastError() | 0x10000000;
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          LastError = GetLastError();
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\w3wp.cxx",
            1049,
            "CtrlHandle",
            "\nCould not find entry point '%s'.  Error = %d\n",
            L"hwebcore.dll",
            LastError);
        }
      }
    }
    else
    {
      v4 = GetLastError() | 0x10000000;
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        v7 = GetLastError();
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\w3wp.cxx",
          1037,
          "CtrlHandle",
          "\nError loading hwebcore dll '%ws'.  Error = %d\n",
          L"hwebcore.dll",
          v7);
      }
    }
    if ( _InterlockedCompareExchange(&g_lShuttingDown, 1, 0) != 1 )
    {
      if ( g_pTimer )
      {
        SetThreadpoolTimer(g_pTimer, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(g_pTimer, 1);
        CloseThreadpoolTimer(g_pTimer);
        g_pTimer = 0;
      }
      if ( v4 < 0 )
        PrintErrorMessage(v4);
      ExitProcess(v4);
    }
  }
}

```

## disassembly

```asm
0x140001840  push    rbx
0x140001842  push    rbp
0x140001843  push    rsi
0x140001844  push    rdi
0x140001845  sub     rsp, 48h
0x140001849  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0
0x140001852  test    ecx, ecx
0x140001854  jz      short loc_14000186E
0x140001856  sub     ecx, 1
0x140001859  jz      short loc_14000186E
0x14000185b  sub     ecx, 1
0x14000185e  jz      short loc_14000186E
0x140001860  sub     ecx, 3
0x140001863  jz      short loc_14000186E
0x140001865  cmp     ecx, 1
0x140001868  jnz     loc_140001A0E
0x14000186e  mov     ecx, 61ABh; uID
0x140001873  call    ?PrintResourceString@@YAXK@Z; PrintResourceString(ulong)
0x140001878  lea     rdi, LibFileName; "hwebcore.dll"
0x14000187f  xor     r8d, r8d; dwFlags
0x140001882  mov     rcx, rdi; lpLibFileName
0x140001885  xor     edx, edx; hFile
0x140001887  call    cs:__imp_LoadLibraryExW
0x14000188d  mov     ebp, 1
0x140001892  test    rax, rax
0x140001895  jnz     short loc_1400018F1
0x140001897  call    cs:__imp_GetLastError
0x14000189d  mov     ebx, eax
0x14000189f  bts     ebx, 1Ch
0x1400018a3  test    byte ptr cs:g_dwDebugFlags, 3
0x1400018aa  jz      loc_1400019AB
0x1400018b0  call    cs:__imp_GetLastError
0x1400018b6  mov     [rsp+68h+var_38], eax
0x1400018ba  mov     r8d, 40Dh
0x1400018c0  lea     rax, aErrorLoadingHw_0; "\nError loading hwebcore dll '%ws'.  Er"...
0x1400018c7  mov     rcx, cs:g_pDebug
0x1400018ce  lea     r9, aCtrlhandle; "CtrlHandle"
0x1400018d5  mov     [rsp+68h+var_40], rdi
0x1400018da  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1400018e1  mov     [rsp+68h+var_48], rax
0x1400018e6  call    cs:__imp_PuDbgPrint
0x1400018ec  jmp     loc_1400019AB
0x1400018f1  lea     rdx, ProcName; "WebCoreShutdown"
0x1400018f8  mov     rcx, rax; hModule
0x1400018fb  call    cs:__imp_GetProcAddress
0x140001901  mov     rsi, rax
0x140001904  test    rax, rax
0x140001907  jnz     short loc_14000193B
0x140001909  call    cs:__imp_GetLastError
0x14000190f  mov     ebx, eax
0x140001911  bts     ebx, 1Ch
0x140001915  test    byte ptr cs:g_dwDebugFlags, 3
0x14000191c  jz      loc_1400019AB
0x140001922  call    cs:__imp_GetLastError
0x140001928  mov     [rsp+68h+var_38], eax
0x14000192c  mov     r8d, 419h
0x140001932  lea     rax, aCouldNotFindEn; "\nCould not find entry point '%s'.  Err"...
0x140001939  jmp     short loc_1400018C7
0x14000193b  xor     r8d, r8d; pcbe
0x14000193e  lea     rcx, ?TimerCallback@@YAXXZ; pfnti
0x140001945  xor     edx, edx; pv
0x140001947  xor     ebx, ebx
0x140001949  call    cs:__imp_CreateThreadpoolTimer
0x14000194f  mov     cs:?g_pTimer@@3PEAU_TP_TIMER@@EA, rax; _TP_TIMER * g_pTimer
0x140001956  mov     rcx, rax; pti
0x140001959  test    rax, rax
0x14000195c  jnz     short loc_140001962
0x14000195e  mov     edi, ebp
0x140001960  jmp     short loc_140001991
0x140001962  mov     eax, cs:?g_dwShutDownTimeout@@3KA; ulong g_dwShutDownTimeout
0x140001968  xor     edi, edi
0x14000196a  imul    rax, 0FFFFFFFFFF676980h
0x140001971  xor     r9d, r9d; msWindowLength
0x140001974  xor     r8d, r8d; msPeriod
0x140001977  mov     rdx, rax
0x14000197a  mov     [rsp+68h+pftDueTime.dwLowDateTime], eax
0x14000197e  shr     rdx, 20h
0x140001982  mov     [rsp+68h+pftDueTime.dwHighDateTime], edx
0x140001986  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x14000198b  call    cs:__imp_SetThreadpoolTimer
0x140001991  mov     ecx, edi
0x140001993  mov     rax, rsi
0x140001996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000199b  test    eax, eax
0x14000199d  jns     short loc_1400019AB
0x14000199f  call    cs:__imp_GetLastError
0x1400019a5  mov     ebx, eax
0x1400019a7  bts     ebx, 1Ch
0x1400019ab  xor     eax, eax
0x1400019ad  lock cmpxchg cs:?g_lShuttingDown@@3JC, ebp; long volatile g_lShuttingDown
0x1400019b5  cmp     eax, ebp
0x1400019b7  jz      short loc_140001A0E
0x1400019b9  mov     rcx, cs:?g_pTimer@@3PEAU_TP_TIMER@@EA; pti
0x1400019c0  test    rcx, rcx
0x1400019c3  jz      short loc_1400019FA
0x1400019c5  xor     r9d, r9d; msWindowLength
0x1400019c8  xor     r8d, r8d; msPeriod
0x1400019cb  xor     edx, edx; pftDueTime
0x1400019cd  call    cs:__imp_SetThreadpoolTimer
0x1400019d3  mov     rcx, cs:?g_pTimer@@3PEAU_TP_TIMER@@EA; pti
0x1400019da  mov     edx, ebp; fCancelPendingCallbacks
0x1400019dc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400019e2  mov     rcx, cs:?g_pTimer@@3PEAU_TP_TIMER@@EA; pti
0x1400019e9  call    cs:__imp_CloseThreadpoolTimer
0x1400019ef  mov     cs:?g_pTimer@@3PEAU_TP_TIMER@@EA, 0; _TP_TIMER * g_pTimer
0x1400019fa  test    ebx, ebx
0x1400019fc  jns     short loc_140001A05
0x1400019fe  mov     ecx, ebx; int
0x140001a00  call    ?PrintErrorMessage@@YAXJ@Z; PrintErrorMessage(long)
0x140001a05  mov     ecx, ebx; uExitCode
0x140001a07  call    cs:__imp_ExitProcess
0x140001a0e  add     rsp, 48h
0x140001a12  pop     rdi
0x140001a13  pop     rsi
0x140001a14  pop     rbp
0x140001a15  pop     rbx
0x140001a16  retn
```
