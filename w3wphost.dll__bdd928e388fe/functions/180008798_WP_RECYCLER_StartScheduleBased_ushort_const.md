# WP_RECYCLER::StartScheduleBased(ushort const *)

- ea: `0x180008798`
- end: `0x180008b14`
- name: `?StartScheduleBased@WP_RECYCLER@@QEAAJPEBG@Z`
- size: `892`
- prototype: `__int64 __fastcall(WP_RECYCLER *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001170`

## callees

- `0x180001ec8`
- `0x180008798`
- `0x18000c3d0`

## import_xrefs

- `msvcrt!iswspace` at `0x1800088d6`
- `msvcrt!iswspace` at `0x180008a08`
- `msvcrt!iswspace` at `0x1800088d6`
- `msvcrt!iswspace` at `0x180008a08`
- `msvcrt!iswdigit` at `0x1800088e9`
- `msvcrt!iswdigit` at `0x18000891b`
- `msvcrt!iswdigit` at `0x180008948`
- `msvcrt!iswdigit` at `0x18000897b`
- `msvcrt!iswdigit` at `0x1800088e9`
- `msvcrt!iswdigit` at `0x18000891b`
- `msvcrt!iswdigit` at `0x180008948`
- `msvcrt!iswdigit` at `0x18000897b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000884c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000884c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800088a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800089f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800088a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800089f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800087e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800087e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000886e`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000886e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000887c`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180008a2e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000887c`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180008a2e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180008af8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180008af8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x18000883a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x18000883a`
- `iisutil!PuDbgPrint` at `0x180008823`
- `iisutil!PuDbgPrint` at `0x1800089eb`
- `iisutil!PuDbgPrint` at `0x180008ac8`
- `iisutil!PuDbgPrint` at `0x180008823`
- `iisutil!PuDbgPrint` at `0x1800089eb`
- `iisutil!PuDbgPrint` at `0x180008ac8`

## string_xrefs

- `0x18000881c`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`
- `0x1800089e4`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`
- `0x180008a9c`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`

## pseudocode

```c
__int64 __fastcall WP_RECYCLER::StartScheduleBased(HANDLE *this, wint_t *a2)
{
  WP_RECYCLER *v3; // rsi
  HANDLE TimerQueue; // rax
  signed int LastError; // eax
  unsigned int v6; // ebx
  struct _FILETIME v7; // rbx
  wint_t v8; // cx
  WORD v10; // r15
  unsigned __int16 v11; // r14
  const unsigned __int16 *v12; // rdi
  WORD v13; // r14
  __int16 v14; // r12
  unsigned __int64 v15; // rax
  DWORD DueTime; // r12d
  struct _FILETIME FileTime; // [rsp+48h] [rbp-38h] BYREF
  struct _FILETIME v19; // [rsp+50h] [rbp-30h] BYREF
  void *phNewTimer; // [rsp+58h] [rbp-28h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-20h] BYREF

  phNewTimer = 0;
  SystemTime = 0;
  v19 = 0;
  FileTime = 0;
  v3 = (WP_RECYCLER *)this;
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wprecycler.cxx",
      196,
      "WP_RECYCLER::StartScheduleBased",
      "WP_RECYCLER::StartScheduleBased()\n");
  if ( *((_DWORD *)v3 + 40) )
    WP_RECYCLER::TerminateScheduleBased(v3);
  TimerQueue = CreateTimerQueue();
  *((_QWORD *)v3 + 19) = TimerQueue;
  if ( TimerQueue )
  {
    GetLocalTime(&SystemTime);
    SystemTimeToFileTime(&SystemTime, &FileTime);
    v7 = FileTime;
    while ( 1 )
    {
      v8 = *a2;
      if ( !*a2 )
      {
        *((_DWORD *)v3 + 40) = 1;
        LeaveCriticalSection((LPCRITICAL_SECTION)v3);
        return 0;
      }
      while ( iswspace(v8) )
        v8 = *++a2;
      v10 = 0;
      v11 = 0;
      if ( iswdigit(*a2) )
      {
        do
        {
          ++v11;
          v10 = *a2++ + 10 * v10 - 48;
        }
        while ( iswdigit(*a2) );
        v3 = (WP_RECYCLER *)this;
        if ( v11 > 2u || v10 > 0x17u )
          break;
      }
      if ( !*a2 )
        break;
      v12 = a2 + 1;
      v13 = 0;
      v14 = 0;
      if ( !iswdigit(*v12) )
        break;
      do
      {
        ++v14;
        v13 = *v12++ + 10 * v13 - 48;
      }
      while ( iswdigit(*v12) );
      v3 = (WP_RECYCLER *)this;
      if ( v14 != 2 || v13 > 0x3Bu )
        break;
      while ( iswspace(*v12) )
        ++v12;
      if ( *v12 )
        break;
      SystemTime.wHour = v10;
      SystemTime.wMinute = v13;
      *(_DWORD *)&SystemTime.wSecond = 0;
      SystemTimeToFileTime(&SystemTime, &v19);
      if ( *(_QWORD *)&v19 >= *(unsigned __int64 *)&v7 )
        v15 = (*(_QWORD *)&v19 - *(_QWORD *)&v7) / 0x2710uLL;
      else
        LODWORD(v15) = 86400000 - (*(_QWORD *)&v7 - *(_QWORD *)&v19) / 0x2710uLL;
      DueTime = 86400000;
      if ( (_DWORD)v15 )
        DueTime = v15;
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wprecycler.cxx",
          389,
          "WP_RECYCLER::StartScheduleBased",
          "Schedule recycling for %d:%d (in %d milliseconds)\n");
      if ( !CreateTimerQueueTimer(
              &phNewTimer,
              this[19],
              WP_RECYCLER::TimerCallbackForScheduleBased,
              this,
              DueTime,
              0x5265C00u,
              0x10u) )
        goto LABEL_6;
      a2 = (wint_t *)(v12 + 1);
    }
    v6 = -2147024809;
  }
  else
  {
LABEL_6:
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
  }
  WP_RECYCLER::TerminateScheduleBased(v3);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wprecycler.cxx",
      429,
      "WP_RECYCLER::StartScheduleBased",
      "WP_RECYCLER::StartScheduleBased() failed with error hr=0x%x\n");
  LeaveCriticalSection((LPCRITICAL_SECTION)v3);
  return v6;
}

```

## disassembly

```asm
0x180008798  mov     [rsp-38h+arg_10], rbx
0x18000879d  push    rbp
0x18000879e  push    rsi
0x18000879f  push    rdi
0x1800087a0  push    r12
0x1800087a2  push    r13
0x1800087a4  push    r14
0x1800087a6  push    r15
0x1800087a8  mov     rbp, rsp
0x1800087ab  sub     rsp, 80h
0x1800087b2  mov     rax, cs:__security_cookie
0x1800087b9  xor     rax, rsp
0x1800087bc  mov     [rbp+var_10], rax
0x1800087c0  xor     r13d, r13d
0x1800087c3  mov     [rbp+Parameter], rcx
0x1800087c7  xorps   xmm0, xmm0
0x1800087ca  mov     [rbp+phNewTimer], r13
0x1800087ce  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1800087d2  mov     qword ptr [rbp+var_30.dwLowDateTime], r13
0x1800087d6  mov     rdi, rdx
0x1800087d9  mov     qword ptr [rbp+FileTime.dwLowDateTime], r13
0x1800087dd  mov     rsi, rcx
0x1800087e0  call    cs:__imp_EnterCriticalSection
0x1800087e6  mov     eax, cs:g_dwDebugFlags
0x1800087ec  test    al, 3
0x1800087ee  setnz   cl
0x1800087f1  bt      eax, 14h
0x1800087f5  setb    al
0x1800087f8  test    al, cl
0x1800087fa  jz      short loc_180008829
0x1800087fc  mov     rcx, cs:g_pDebug
0x180008803  lea     rax, aWpRecyclerStar; "WP_RECYCLER::StartScheduleBased()\n"
0x18000880a  lea     r9, aWpRecyclerStar_0; "WP_RECYCLER::StartScheduleBased"
0x180008811  mov     qword ptr [rsp+80h+DueTime], rax
0x180008816  mov     r8d, 0C4h
0x18000881c  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008823  call    cs:__imp_PuDbgPrint
0x180008829  cmp     [rsi+0A0h], r13d
0x180008830  jz      short loc_18000883A
0x180008832  mov     rcx, rsi; this
0x180008835  call    ?TerminateScheduleBased@WP_RECYCLER@@QEAAXXZ; WP_RECYCLER::TerminateScheduleBased(void)
0x18000883a  call    cs:__imp_CreateTimerQueue
0x180008840  mov     [rsi+98h], rax
0x180008847  test    rax, rax
0x18000884a  jnz     short loc_18000886A
0x18000884c  call    cs:__imp_GetLastError
0x180008852  mov     ebx, eax
0x180008854  test    eax, eax
0x180008856  jle     loc_1800089A0
0x18000885c  movzx   ebx, ax
0x18000885f  or      ebx, 80070000h
0x180008865  jmp     loc_1800089A0
0x18000886a  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18000886e  call    cs:__imp_GetLocalTime
0x180008874  lea     rdx, [rbp+FileTime]; lpFileTime
0x180008878  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18000887c  call    cs:__imp_SystemTimeToFileTime
0x180008882  mov     rbx, qword ptr [rbp+FileTime.dwLowDateTime]
0x180008886  mov     r12d, 2
0x18000888c  movzx   ecx, word ptr [rdi]
0x18000888f  test    cx, cx
0x180008892  jnz     short loc_1800088D6
0x180008894  mov     rcx, rsi; lpCriticalSection
0x180008897  mov     dword ptr [rsi+0A0h], 1
0x1800088a1  call    cs:__imp_LeaveCriticalSection
0x1800088a7  xor     eax, eax
0x1800088a9  mov     rcx, [rbp+var_10]
0x1800088ad  xor     rcx, rsp; StackCookie
0x1800088b0  call    __security_check_cookie
0x1800088b5  mov     rbx, [rsp+80h+arg_10]
0x1800088bd  add     rsp, 80h
0x1800088c4  pop     r15
0x1800088c6  pop     r14
0x1800088c8  pop     r13
0x1800088ca  pop     r12
0x1800088cc  pop     rdi
0x1800088cd  pop     rsi
0x1800088ce  pop     rbp
0x1800088cf  retn
0x1800088d0  add     rdi, r12
0x1800088d3  movzx   ecx, word ptr [rdi]; C
0x1800088d6  call    cs:__imp_iswspace
0x1800088dc  test    eax, eax
0x1800088de  jnz     short loc_1800088D0
0x1800088e0  movzx   ecx, word ptr [rdi]; C
0x1800088e3  mov     r15d, r13d
0x1800088e6  mov     r14d, r13d
0x1800088e9  call    cs:__imp_iswdigit
0x1800088ef  test    eax, eax
0x1800088f1  jz      short loc_180008936
0x1800088f3  mov     esi, 1
0x1800088f8  movzx   eax, r15w
0x1800088fc  add     r14w, si
0x180008900  shl     ax, 2
0x180008904  add     r15w, ax
0x180008908  add     r15w, r15w
0x18000890c  sub     r15w, 30h ; '0'
0x180008911  add     r15w, [rdi]
0x180008915  add     rdi, r12
0x180008918  movzx   ecx, word ptr [rdi]; C
0x18000891b  call    cs:__imp_iswdigit
0x180008921  test    eax, eax
0x180008923  jnz     short loc_1800088F8
0x180008925  mov     rsi, [rbp+Parameter]
0x180008929  cmp     r14w, r12w
0x18000892d  ja      short loc_18000899B
0x18000892f  cmp     r15w, 17h
0x180008934  ja      short loc_18000899B
0x180008936  cmp     [rdi], r13w
0x18000893a  jz      short loc_18000899B
0x18000893c  add     rdi, r12
0x18000893f  mov     r14d, r13d
0x180008942  mov     r12d, r13d
0x180008945  movzx   ecx, word ptr [rdi]; C
0x180008948  call    cs:__imp_iswdigit
0x18000894e  test    eax, eax
0x180008950  jz      short loc_18000899B
0x180008952  mov     esi, 1
0x180008957  movzx   eax, r14w
0x18000895b  add     r12w, si
0x18000895f  shl     ax, 2
0x180008963  add     r14w, ax
0x180008967  add     r14w, r14w
0x18000896b  sub     r14w, 30h ; '0'
0x180008970  add     r14w, [rdi]
0x180008974  add     rdi, 2
0x180008978  movzx   ecx, word ptr [rdi]; C
0x18000897b  call    cs:__imp_iswdigit
0x180008981  test    eax, eax
0x180008983  jnz     short loc_180008957
0x180008985  mov     rsi, [rbp+Parameter]
0x180008989  mov     eax, 2
0x18000898e  cmp     r12w, ax
0x180008992  jnz     short loc_18000899B
0x180008994  cmp     r14w, 3Bh ; ';'
0x180008999  jbe     short loc_180008A05
0x18000899b  mov     ebx, 80070057h
0x1800089a0  mov     rcx, rsi; this
0x1800089a3  call    ?TerminateScheduleBased@WP_RECYCLER@@QEAAXXZ; WP_RECYCLER::TerminateScheduleBased(void)
0x1800089a8  mov     eax, cs:g_dwDebugFlags
0x1800089ae  test    al, 3
0x1800089b0  setnz   r8b
0x1800089b4  bt      eax, 14h
0x1800089b8  setb    al
0x1800089bb  test    al, r8b
0x1800089be  jz      short loc_1800089F1
0x1800089c0  mov     rcx, cs:g_pDebug
0x1800089c7  lea     rax, aWpRecyclerStar_1; "WP_RECYCLER::StartScheduleBased() faile"...
0x1800089ce  mov     [rsp+80h+Period], ebx
0x1800089d2  lea     r9, aWpRecyclerStar_0; "WP_RECYCLER::StartScheduleBased"
0x1800089d9  mov     r8d, 1ADh
0x1800089df  mov     qword ptr [rsp+80h+DueTime], rax
0x1800089e4  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800089eb  call    cs:__imp_PuDbgPrint
0x1800089f1  mov     rcx, rsi; lpCriticalSection
0x1800089f4  call    cs:__imp_LeaveCriticalSection
0x1800089fa  mov     eax, ebx
0x1800089fc  jmp     loc_1800088A9
0x180008a01  add     rdi, 2
0x180008a05  movzx   ecx, word ptr [rdi]; C
0x180008a08  call    cs:__imp_iswspace
0x180008a0e  test    eax, eax
0x180008a10  jnz     short loc_180008A01
0x180008a12  cmp     [rdi], r13w
0x180008a16  jnz     short loc_18000899B
0x180008a18  lea     rdx, [rbp+var_30]; lpFileTime
0x180008a1c  mov     [rbp+SystemTime.wHour], r15w
0x180008a21  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180008a25  mov     [rbp+SystemTime.wMinute], r14w
0x180008a2a  mov     dword ptr [rbp+SystemTime.wSecond], r13d
0x180008a2e  call    cs:__imp_SystemTimeToFileTime
0x180008a34  mov     rcx, qword ptr [rbp+var_30.dwLowDateTime]
0x180008a38  mov     rax, 346DC5D63886594Bh
0x180008a42  cmp     rcx, rbx
0x180008a45  jnb     short loc_180008A5D
0x180008a47  mov     rdx, rbx
0x180008a4a  sub     rdx, rcx
0x180008a4d  mul     rdx
0x180008a50  mov     eax, 5265C00h
0x180008a55  shr     rdx, 0Bh
0x180008a59  sub     eax, edx
0x180008a5b  jmp     short loc_180008A6A
0x180008a5d  sub     rcx, rbx
0x180008a60  mul     rcx
0x180008a63  mov     rax, rdx
0x180008a66  shr     rax, 0Bh
0x180008a6a  test    eax, eax
0x180008a6c  mov     r12d, 5265C00h
0x180008a72  cmovnz  r12d, eax
0x180008a76  mov     eax, cs:g_dwDebugFlags
0x180008a7c  test    al, 3
0x180008a7e  setnz   cl
0x180008a81  bt      eax, 14h
0x180008a85  setb    al
0x180008a88  test    al, cl
0x180008a8a  jz      short loc_180008ACE
0x180008a8c  mov     [rsp+80h+var_48], r12d
0x180008a91  lea     r9, aWpRecyclerStar_0; "WP_RECYCLER::StartScheduleBased"
0x180008a98  movzx   eax, r14w
0x180008a9c  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008aa3  mov     [rsp+80h+Flags], eax
0x180008aa7  mov     r8d, 185h
0x180008aad  movzx   ecx, r15w
0x180008ab1  lea     rax, aScheduleRecycl; "Schedule recycling for %d:%d (in %d mil"...
0x180008ab8  mov     [rsp+80h+Period], ecx
0x180008abc  mov     rcx, cs:g_pDebug
0x180008ac3  mov     qword ptr [rsp+80h+DueTime], rax
0x180008ac8  call    cs:__imp_PuDbgPrint
0x180008ace  mov     rdx, [rsi+98h]; TimerQueue
0x180008ad5  lea     r8, ?TimerCallbackForScheduleBased@WP_RECYCLER@@SAXPEAXE@Z; Callback
0x180008adc  mov     [rsp+80h+Flags], 10h; Flags
0x180008ae4  lea     rcx, [rbp+phNewTimer]; phNewTimer
0x180008ae8  mov     [rsp+80h+Period], 5265C00h; Period
0x180008af0  mov     r9, rsi; Parameter
0x180008af3  mov     [rsp+80h+DueTime], r12d; DueTime
0x180008af8  call    cs:__imp_CreateTimerQueueTimer
0x180008afe  test    eax, eax
0x180008b00  jz      loc_18000884C
0x180008b06  mov     r12d, 2
0x180008b0c  add     rdi, r12
0x180008b0f  jmp     loc_18000888C
```
