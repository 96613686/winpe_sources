# WP_RECYCLER::StartScheduleBased(ushort const *)

- ea: `0x1800090e4`
- end: `0x1800094d1`
- name: `?StartScheduleBased@WP_RECYCLER@@QEAAJPEBG@Z`
- size: `1005`
- prototype: `__int64 __fastcall(WP_RECYCLER *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001180`

## callees

- `0x180001fd4`
- `0x1800090e4`
- `0x18000d2f0`

## import_xrefs

- `msvcrt!iswspace` at `0x18000924d`
- `msvcrt!iswspace` at `0x1800093a9`
- `msvcrt!iswspace` at `0x18000924d`
- `msvcrt!iswspace` at `0x1800093a9`
- `msvcrt!iswdigit` at `0x180009266`
- `msvcrt!iswdigit` at `0x18000929e`
- `msvcrt!iswdigit` at `0x1800092d1`
- `msvcrt!iswdigit` at `0x18000930a`
- `msvcrt!iswdigit` at `0x180009266`
- `msvcrt!iswdigit` at `0x18000929e`
- `msvcrt!iswdigit` at `0x1800092d1`
- `msvcrt!iswdigit` at `0x18000930a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800091aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800091aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009211`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000938f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009211`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000938f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000912c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000912c`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800091d2`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800091d2`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800091e6`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800093d9`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800091e6`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800093d9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800094af`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800094af`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x180009192`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x180009192`
- `iisutil!PuDbgPrint` at `0x180009175`
- `iisutil!PuDbgPrint` at `0x180009380`
- `iisutil!PuDbgPrint` at `0x180009479`
- `iisutil!PuDbgPrint` at `0x180009175`
- `iisutil!PuDbgPrint` at `0x180009380`
- `iisutil!PuDbgPrint` at `0x180009479`

## string_xrefs

- `0x18000916e`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`
- `0x180009379`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`
- `0x18000944d`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wprecycler.cxx`

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
          "Schedule recycling for %d:%d (in %d milliseconds)\n",
          v10,
          v13,
          DueTime);
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
      "WP_RECYCLER::StartScheduleBased() failed with error hr=0x%x\n",
      v6);
  LeaveCriticalSection((LPCRITICAL_SECTION)v3);
  return v6;
}

```

## disassembly

```asm
0x1800090e4  mov     [rsp-38h+arg_10], rbx
0x1800090e9  push    rbp
0x1800090ea  push    rsi
0x1800090eb  push    rdi
0x1800090ec  push    r12
0x1800090ee  push    r13
0x1800090f0  push    r14
0x1800090f2  push    r15
0x1800090f4  mov     rbp, rsp
0x1800090f7  sub     rsp, 80h
0x1800090fe  mov     rax, cs:__security_cookie
0x180009105  xor     rax, rsp
0x180009108  mov     [rbp+var_10], rax
0x18000910c  xor     r13d, r13d
0x18000910f  mov     [rbp+Parameter], rcx
0x180009113  xorps   xmm0, xmm0
0x180009116  mov     [rbp+phNewTimer], r13
0x18000911a  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18000911e  mov     qword ptr [rbp+var_30.dwLowDateTime], r13
0x180009122  mov     rdi, rdx
0x180009125  mov     qword ptr [rbp+FileTime.dwLowDateTime], r13
0x180009129  mov     rsi, rcx
0x18000912c  call    cs:__imp_EnterCriticalSection
0x180009133  nop     dword ptr [rax+rax+00h]
0x180009138  mov     eax, cs:g_dwDebugFlags
0x18000913e  test    al, 3
0x180009140  setnz   cl
0x180009143  bt      eax, 14h
0x180009147  setb    al
0x18000914a  test    al, cl
0x18000914c  jz      short loc_180009181
0x18000914e  mov     rcx, cs:g_pDebug
0x180009155  lea     rax, aWpRecyclerStar; "WP_RECYCLER::StartScheduleBased()\n"
0x18000915c  lea     r9, aWpRecyclerStar_0; "WP_RECYCLER::StartScheduleBased"
0x180009163  mov     qword ptr [rsp+80h+DueTime], rax
0x180009168  mov     r8d, 0C4h
0x18000916e  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009175  call    cs:__imp_PuDbgPrint
0x18000917c  nop     dword ptr [rax+rax+00h]
0x180009181  cmp     [rsi+0A0h], r13d
0x180009188  jz      short loc_180009192
0x18000918a  mov     rcx, rsi; this
0x18000918d  call    ?TerminateScheduleBased@WP_RECYCLER@@QEAAXXZ; WP_RECYCLER::TerminateScheduleBased(void)
0x180009192  call    cs:__imp_CreateTimerQueue
0x180009199  nop     dword ptr [rax+rax+00h]
0x18000919e  mov     [rsi+98h], rax
0x1800091a5  test    rax, rax
0x1800091a8  jnz     short loc_1800091CE
0x1800091aa  call    cs:__imp_GetLastError
0x1800091b1  nop     dword ptr [rax+rax+00h]
0x1800091b6  mov     ebx, eax
0x1800091b8  test    eax, eax
0x1800091ba  jle     loc_180009335
0x1800091c0  movzx   ebx, ax
0x1800091c3  or      ebx, 80070000h
0x1800091c9  jmp     loc_180009335
0x1800091ce  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x1800091d2  call    cs:__imp_GetLocalTime
0x1800091d9  nop     dword ptr [rax+rax+00h]
0x1800091de  lea     rdx, [rbp+FileTime]; lpFileTime
0x1800091e2  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x1800091e6  call    cs:__imp_SystemTimeToFileTime
0x1800091ed  nop     dword ptr [rax+rax+00h]
0x1800091f2  mov     rbx, qword ptr [rbp+FileTime.dwLowDateTime]
0x1800091f6  mov     r12d, 2
0x1800091fc  movzx   ecx, word ptr [rdi]
0x1800091ff  test    cx, cx
0x180009202  jnz     short loc_18000924D
0x180009204  mov     rcx, rsi; lpCriticalSection
0x180009207  mov     dword ptr [rsi+0A0h], 1
0x180009211  call    cs:__imp_LeaveCriticalSection
0x180009218  nop     dword ptr [rax+rax+00h]
0x18000921d  xor     eax, eax
0x18000921f  mov     rcx, [rbp+var_10]
0x180009223  xor     rcx, rsp; StackCookie
0x180009226  call    __security_check_cookie
0x18000922b  mov     rbx, [rsp+80h+arg_10]
0x180009233  add     rsp, 80h
0x18000923a  pop     r15
0x18000923c  pop     r14
0x18000923e  pop     r13
0x180009240  pop     r12
0x180009242  pop     rdi
0x180009243  pop     rsi
0x180009244  pop     rbp
0x180009245  retn
0x180009247  add     rdi, r12
0x18000924a  movzx   ecx, word ptr [rdi]; C
0x18000924d  call    cs:__imp_iswspace
0x180009254  nop     dword ptr [rax+rax+00h]
0x180009259  test    eax, eax
0x18000925b  jnz     short loc_180009247
0x18000925d  movzx   ecx, word ptr [rdi]; C
0x180009260  mov     r15d, r13d
0x180009263  mov     r14d, r13d
0x180009266  call    cs:__imp_iswdigit
0x18000926d  nop     dword ptr [rax+rax+00h]
0x180009272  test    eax, eax
0x180009274  jz      short loc_1800092BF
0x180009276  mov     esi, 1
0x18000927b  movzx   eax, r15w
0x18000927f  add     r14w, si
0x180009283  shl     ax, 2
0x180009287  add     r15w, ax
0x18000928b  add     r15w, r15w
0x18000928f  sub     r15w, 30h ; '0'
0x180009294  add     r15w, [rdi]
0x180009298  add     rdi, r12
0x18000929b  movzx   ecx, word ptr [rdi]; C
0x18000929e  call    cs:__imp_iswdigit
0x1800092a5  nop     dword ptr [rax+rax+00h]
0x1800092aa  test    eax, eax
0x1800092ac  jnz     short loc_18000927B
0x1800092ae  mov     rsi, [rbp+Parameter]
0x1800092b2  cmp     r14w, r12w
0x1800092b6  ja      short loc_180009330
0x1800092b8  cmp     r15w, 17h
0x1800092bd  ja      short loc_180009330
0x1800092bf  cmp     [rdi], r13w
0x1800092c3  jz      short loc_180009330
0x1800092c5  add     rdi, r12
0x1800092c8  mov     r14d, r13d
0x1800092cb  mov     r12d, r13d
0x1800092ce  movzx   ecx, word ptr [rdi]; C
0x1800092d1  call    cs:__imp_iswdigit
0x1800092d8  nop     dword ptr [rax+rax+00h]
0x1800092dd  test    eax, eax
0x1800092df  jz      short loc_180009330
0x1800092e1  mov     esi, 1
0x1800092e6  movzx   eax, r14w
0x1800092ea  add     r12w, si
0x1800092ee  shl     ax, 2
0x1800092f2  add     r14w, ax
0x1800092f6  add     r14w, r14w
0x1800092fa  sub     r14w, 30h ; '0'
0x1800092ff  add     r14w, [rdi]
0x180009303  add     rdi, 2
0x180009307  movzx   ecx, word ptr [rdi]; C
0x18000930a  call    cs:__imp_iswdigit
0x180009311  nop     dword ptr [rax+rax+00h]
0x180009316  test    eax, eax
0x180009318  jnz     short loc_1800092E6
0x18000931a  mov     rsi, [rbp+Parameter]
0x18000931e  mov     eax, 2
0x180009323  cmp     r12w, ax
0x180009327  jnz     short loc_180009330
0x180009329  cmp     r14w, 3Bh ; ';'
0x18000932e  jbe     short loc_1800093A6
0x180009330  mov     ebx, 80070057h
0x180009335  mov     rcx, rsi; this
0x180009338  call    ?TerminateScheduleBased@WP_RECYCLER@@QEAAXXZ; WP_RECYCLER::TerminateScheduleBased(void)
0x18000933d  mov     eax, cs:g_dwDebugFlags
0x180009343  test    al, 3
0x180009345  setnz   r8b
0x180009349  bt      eax, 14h
0x18000934d  setb    al
0x180009350  test    al, r8b
0x180009353  jz      short loc_18000938C
0x180009355  mov     rcx, cs:g_pDebug
0x18000935c  lea     rax, aWpRecyclerStar_1; "WP_RECYCLER::StartScheduleBased() faile"...
0x180009363  mov     [rsp+80h+Period], ebx
0x180009367  lea     r9, aWpRecyclerStar_0; "WP_RECYCLER::StartScheduleBased"
0x18000936e  mov     r8d, 1ADh
0x180009374  mov     qword ptr [rsp+80h+DueTime], rax
0x180009379  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009380  call    cs:__imp_PuDbgPrint
0x180009387  nop     dword ptr [rax+rax+00h]
0x18000938c  mov     rcx, rsi; lpCriticalSection
0x18000938f  call    cs:__imp_LeaveCriticalSection
0x180009396  nop     dword ptr [rax+rax+00h]
0x18000939b  mov     eax, ebx
0x18000939d  jmp     loc_18000921F
0x1800093a2  add     rdi, 2
0x1800093a6  movzx   ecx, word ptr [rdi]; C
0x1800093a9  call    cs:__imp_iswspace
0x1800093b0  nop     dword ptr [rax+rax+00h]
0x1800093b5  test    eax, eax
0x1800093b7  jnz     short loc_1800093A2
0x1800093b9  cmp     [rdi], r13w
0x1800093bd  jnz     loc_180009330
0x1800093c3  lea     rdx, [rbp+var_30]; lpFileTime
0x1800093c7  mov     [rbp+SystemTime.wHour], r15w
0x1800093cc  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x1800093d0  mov     [rbp+SystemTime.wMinute], r14w
0x1800093d5  mov     dword ptr [rbp+SystemTime.wSecond], r13d
0x1800093d9  call    cs:__imp_SystemTimeToFileTime
0x1800093e0  nop     dword ptr [rax+rax+00h]
0x1800093e5  mov     rcx, qword ptr [rbp+var_30.dwLowDateTime]
0x1800093e9  mov     rax, 346DC5D63886594Bh
0x1800093f3  cmp     rcx, rbx
0x1800093f6  jnb     short loc_18000940E
0x1800093f8  mov     rdx, rbx
0x1800093fb  sub     rdx, rcx
0x1800093fe  mul     rdx
0x180009401  mov     eax, 5265C00h
0x180009406  shr     rdx, 0Bh
0x18000940a  sub     eax, edx
0x18000940c  jmp     short loc_18000941B
0x18000940e  sub     rcx, rbx
0x180009411  mul     rcx
0x180009414  mov     rax, rdx
0x180009417  shr     rax, 0Bh
0x18000941b  test    eax, eax
0x18000941d  mov     r12d, 5265C00h
0x180009423  cmovnz  r12d, eax
0x180009427  mov     eax, cs:g_dwDebugFlags
0x18000942d  test    al, 3
0x18000942f  setnz   cl
0x180009432  bt      eax, 14h
0x180009436  setb    al
0x180009439  test    al, cl
0x18000943b  jz      short loc_180009485
0x18000943d  mov     [rsp+80h+var_48], r12d
0x180009442  lea     r9, aWpRecyclerStar_0; "WP_RECYCLER::StartScheduleBased"
0x180009449  movzx   eax, r14w
0x18000944d  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009454  mov     [rsp+80h+Flags], eax
0x180009458  mov     r8d, 185h
0x18000945e  movzx   ecx, r15w
0x180009462  lea     rax, aScheduleRecycl; "Schedule recycling for %d:%d (in %d mil"...
0x180009469  mov     [rsp+80h+Period], ecx
0x18000946d  mov     rcx, cs:g_pDebug
0x180009474  mov     qword ptr [rsp+80h+DueTime], rax
0x180009479  call    cs:__imp_PuDbgPrint
0x180009480  nop     dword ptr [rax+rax+00h]
0x180009485  mov     rdx, [rsi+98h]; TimerQueue
0x18000948c  lea     r8, ?TimerCallbackForScheduleBased@WP_RECYCLER@@SAXPEAXE@Z; Callback
0x180009493  mov     [rsp+80h+Flags], 10h; Flags
0x18000949b  lea     rcx, [rbp+phNewTimer]; phNewTimer
0x18000949f  mov     [rsp+80h+Period], 5265C00h; Period
0x1800094a7  mov     r9, rsi; Parameter
0x1800094aa  mov     [rsp+80h+DueTime], r12d; DueTime
0x1800094af  call    cs:__imp_CreateTimerQueueTimer
0x1800094b6  nop     dword ptr [rax+rax+00h]
0x1800094bb  test    eax, eax
0x1800094bd  jz      loc_1800091AA
0x1800094c3  mov     r12d, 2
0x1800094c9  add     rdi, r12
0x1800094cc  jmp     loc_1800091FC
```
