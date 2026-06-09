# CtrlHandle(ulong)

- ea: `0x140001840`
- end: `0x140001a6f`
- name: `?CtrlHandle@@YAXK@Z`
- size: `559`
- prototype: `void __fastcall(DWORD CtrlType)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001840`
- `0x1400020c0`
- `0x140002118`
- `0x140004010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000189d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400018bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001927`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001946`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400019d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000189d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400018bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001927`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001946`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400019d8`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140001a58`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140001a58`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140001887`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140001887`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140001913`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140001913`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140001976`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140001976`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140001a21`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140001a21`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140001a34`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140001a34`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400019be`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140001a0c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400019be`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140001a0c`
- `iisutil!PuDbgPrint` at `0x1400018f8`
- `iisutil!PuDbgPrint` at `0x1400018f8`

## string_xrefs

- `0x1400018ec`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wp\w3wp.cxx`
- `0x140001878`: `hwebcore.dll`
- `0x1400018d2`: `\nError loading hwebcore dll '%ws'.  Error = %d\n`

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
0x140001868  jnz     loc_140001A65
0x14000186e  mov     ecx, 61ABh; uID
0x140001873  call    ?PrintResourceString@@YAXK@Z; PrintResourceString(ulong)
0x140001878  lea     rdi, LibFileName; "hwebcore.dll"
0x14000187f  xor     r8d, r8d; dwFlags
0x140001882  mov     rcx, rdi; lpLibFileName
0x140001885  xor     edx, edx; hFile
0x140001887  call    cs:__imp_LoadLibraryExW
0x14000188e  nop     dword ptr [rax+rax+00h]
0x140001893  mov     ebp, 1
0x140001898  test    rax, rax
0x14000189b  jnz     short loc_140001909
0x14000189d  call    cs:__imp_GetLastError
0x1400018a4  nop     dword ptr [rax+rax+00h]
0x1400018a9  mov     ebx, eax
0x1400018ab  bts     ebx, 1Ch
0x1400018af  test    byte ptr cs:g_dwDebugFlags, 3
0x1400018b6  jz      loc_1400019EA
0x1400018bc  call    cs:__imp_GetLastError
0x1400018c3  nop     dword ptr [rax+rax+00h]
0x1400018c8  mov     [rsp+68h+var_38], eax
0x1400018cc  mov     r8d, 40Dh
0x1400018d2  lea     rax, aErrorLoadingHw_0; "\nError loading hwebcore dll '%ws'.  Er"...
0x1400018d9  mov     rcx, cs:g_pDebug
0x1400018e0  lea     r9, aCtrlhandle; "CtrlHandle"
0x1400018e7  mov     [rsp+68h+var_40], rdi
0x1400018ec  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1400018f3  mov     [rsp+68h+var_48], rax
0x1400018f8  call    cs:__imp_PuDbgPrint
0x1400018ff  nop     dword ptr [rax+rax+00h]
0x140001904  jmp     loc_1400019EA
0x140001909  lea     rdx, ProcName; "WebCoreShutdown"
0x140001910  mov     rcx, rax; hModule
0x140001913  call    cs:__imp_GetProcAddress
0x14000191a  nop     dword ptr [rax+rax+00h]
0x14000191f  mov     rsi, rax
0x140001922  test    rax, rax
0x140001925  jnz     short loc_140001968
0x140001927  call    cs:__imp_GetLastError
0x14000192e  nop     dword ptr [rax+rax+00h]
0x140001933  mov     ebx, eax
0x140001935  bts     ebx, 1Ch
0x140001939  test    byte ptr cs:g_dwDebugFlags, 3
0x140001940  jz      loc_1400019EA
0x140001946  call    cs:__imp_GetLastError
0x14000194d  nop     dword ptr [rax+rax+00h]
0x140001952  mov     [rsp+68h+var_38], eax
0x140001956  mov     r8d, 419h
0x14000195c  lea     rax, aCouldNotFindEn; "\nCould not find entry point '%s'.  Err"...
0x140001963  jmp     loc_1400018D9
0x140001968  xor     r8d, r8d; pcbe
0x14000196b  lea     rcx, ?TimerCallback@@YAXXZ; pfnti
0x140001972  xor     edx, edx; pv
0x140001974  xor     ebx, ebx
0x140001976  call    cs:__imp_CreateThreadpoolTimer
0x14000197d  nop     dword ptr [rax+rax+00h]
0x140001982  mov     cs:?g_pTimer@@3PEAU_TP_TIMER@@EA, rax; _TP_TIMER * g_pTimer
0x140001989  mov     rcx, rax; pti
0x14000198c  test    rax, rax
0x14000198f  jnz     short loc_140001995
0x140001991  mov     edi, ebp
0x140001993  jmp     short loc_1400019CA
0x140001995  mov     eax, cs:?g_dwShutDownTimeout@@3KA; ulong g_dwShutDownTimeout
0x14000199b  xor     edi, edi
0x14000199d  imul    rax, 0FFFFFFFFFF676980h
0x1400019a4  xor     r9d, r9d; msWindowLength
0x1400019a7  xor     r8d, r8d; msPeriod
0x1400019aa  mov     rdx, rax
0x1400019ad  mov     [rsp+68h+pftDueTime.dwLowDateTime], eax
0x1400019b1  shr     rdx, 20h
0x1400019b5  mov     [rsp+68h+pftDueTime.dwHighDateTime], edx
0x1400019b9  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1400019be  call    cs:__imp_SetThreadpoolTimer
0x1400019c5  nop     dword ptr [rax+rax+00h]
0x1400019ca  mov     ecx, edi
0x1400019cc  mov     rax, rsi
0x1400019cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400019d4  test    eax, eax
0x1400019d6  jns     short loc_1400019EA
0x1400019d8  call    cs:__imp_GetLastError
0x1400019df  nop     dword ptr [rax+rax+00h]
0x1400019e4  mov     ebx, eax
0x1400019e6  bts     ebx, 1Ch
0x1400019ea  xor     eax, eax
0x1400019ec  lock cmpxchg cs:?g_lShuttingDown@@3JC, ebp; long volatile g_lShuttingDown
0x1400019f4  cmp     eax, ebp
0x1400019f6  jz      short loc_140001A65
0x1400019f8  mov     rcx, cs:?g_pTimer@@3PEAU_TP_TIMER@@EA; pti
0x1400019ff  test    rcx, rcx
0x140001a02  jz      short loc_140001A4B
0x140001a04  xor     r9d, r9d; msWindowLength
0x140001a07  xor     r8d, r8d; msPeriod
0x140001a0a  xor     edx, edx; pftDueTime
0x140001a0c  call    cs:__imp_SetThreadpoolTimer
0x140001a13  nop     dword ptr [rax+rax+00h]
0x140001a18  mov     rcx, cs:?g_pTimer@@3PEAU_TP_TIMER@@EA; pti
0x140001a1f  mov     edx, ebp; fCancelPendingCallbacks
0x140001a21  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140001a28  nop     dword ptr [rax+rax+00h]
0x140001a2d  mov     rcx, cs:?g_pTimer@@3PEAU_TP_TIMER@@EA; pti
0x140001a34  call    cs:__imp_CloseThreadpoolTimer
0x140001a3b  nop     dword ptr [rax+rax+00h]
0x140001a40  mov     cs:?g_pTimer@@3PEAU_TP_TIMER@@EA, 0; _TP_TIMER * g_pTimer
0x140001a4b  test    ebx, ebx
0x140001a4d  jns     short loc_140001A56
0x140001a4f  mov     ecx, ebx; int
0x140001a51  call    ?PrintErrorMessage@@YAXJ@Z; PrintErrorMessage(long)
0x140001a56  mov     ecx, ebx; uExitCode
0x140001a58  call    cs:__imp_ExitProcess
0x140001a65  add     rsp, 48h
0x140001a69  pop     rdi
0x140001a6a  pop     rsi
0x140001a6b  pop     rbp
0x140001a6c  pop     rbx
0x140001a6d  retn
```
