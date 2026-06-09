# WDiagProcessSCMNotification(ulong,ulong,void *,void *,ulong)

- ea: `0x180029074`
- end: `0x1800294f7`
- name: `?WDiagProcessSCMNotification@@YAKKKPEAX0K@Z`
- size: `1155`
- prototype: `unsigned int __fastcall(unsigned int, unsigned int, void *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180011558`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x180029074`
- `0x180029ed4`
- `0x18002bde8`
- `0x18005f3d0`
- `0x180106340`
- `0x1801c81ac`
- `0x1801c82e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800291a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800291a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800290c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800290c7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800290d7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800290d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002942d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002942d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800290b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800294a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800290b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800294a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002913a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002913a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002914c`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002914c`

## pseudocode

```c
__int64 __fastcall WDiagProcessSCMNotification(unsigned int a1, unsigned int a2, void *a3, void *a4)
{
  DWORD CurrentThreadId; // edi
  PVOID *v7; // rcx
  __int64 v9; // rdx
  unsigned int v10; // ebx
  struct _FILETIME *v11; // rcx
  char v12; // al
  int v13; // [rsp+28h] [rbp-80h]
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 10, &WPP_fec73b95d5a537674450248f38664378_Traceguids);
  CurrentThreadId = GetCurrentThreadId();
  EnterCriticalSection(&stru_1802A35F0);
  WaitForSingleObject(qword_1802A3640, 0xFFFFFFFF);
  if ( (dword_1802A3648 & 4) == 0 )
    goto LABEL_3;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 225)
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
  {
    WPP_SF_qqdsddsd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      (char)&qword_1802A35E8,
      dword_1802A3650[0],
      qword_1802A3658,
      dword_1802A3654[0],
      CurrentThreadId,
      (__int64)"WDiagProcessSCMNotification",
      155);
LABEL_3:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  dword_1802A3648 |= 4u;
  *(_DWORD *)dword_1802A3650 = CurrentThreadId;
  *(_DWORD *)dword_1802A3654 = 155;
  qword_1802A3658 = (__int64)"WDiagProcessSCMNotification";
  if ( a1 != 1 && a1 != 5 )
  {
    if ( a1 == 13 )
    {
      if ( !a2 || a2 == 2 )
        goto LABEL_33;
      if ( a2 != 4 )
      {
        if ( a2 == 6 || a2 == 7 || a2 == 18 )
        {
          WDiagGetTime(&stru_1802A36B8);
          v7 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u
            || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0 )
          {
            goto LABEL_9;
          }
          v9 = 12;
LABEL_37:
          WPP_SF_d(v7[27], v9, &WPP_fec73b95d5a537674450248f38664378_Traceguids, a2);
          goto LABEL_30;
        }
LABEL_33:
        if ( v7 == &WPP_GLOBAL_Control || *((_BYTE *)v7 + 225) < 3u || (*((_BYTE *)v7 + 228) & 4) == 0 )
          goto LABEL_9;
        v9 = 13;
        goto LABEL_37;
      }
      WDiagGetTime(&stru_1802A36B0);
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u
        || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0 )
      {
        goto LABEL_9;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 11, &WPP_fec73b95d5a537674450248f38664378_Traceguids);
    }
    else
    {
      if ( a1 == 14 )
      {
        v10 = a2 - 5;
        if ( v10 )
        {
          if ( v10 != 1 )
            goto LABEL_9;
          v11 = (struct _FILETIME *)&qword_1802A36C8;
        }
        else
        {
          v11 = &stru_1802A36C0;
        }
        WDiagGetTime(v11);
        goto LABEL_30;
      }
      if ( v7 == &WPP_GLOBAL_Control || *((_BYTE *)v7 + 225) < 3u || (*((_BYTE *)v7 + 228) & 4) == 0 )
        goto LABEL_9;
      WPP_SF_DD(v7[27], 15, &WPP_fec73b95d5a537674450248f38664378_Traceguids, a1);
    }
LABEL_30:
    v7 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_9;
  }
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
    GetLastError();
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 27), 14, &WPP_fec73b95d5a537674450248f38664378_Traceguids);
    goto LABEL_30;
  }
LABEL_9:
  if ( (dword_1802A3648 & 4) == 0
    && v7 != &WPP_GLOBAL_Control
    && *((_BYTE *)v7 + 225)
    && (*((_BYTE *)v7 + 228) & 0x40) != 0 )
  {
    v12 = GetCurrentThreadId();
    WPP_SF_qqDsdDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      (char)&qword_1802A35E8,
      v13,
      qword_1802A3668,
      dword_1802A3660[0],
      v12,
      (__int64)"WDiagProcessSCMNotification",
      251);
  }
  dword_1802A3648 &= ~4u;
  *(_DWORD *)dword_1802A3660 = 251;
  qword_1802A3668 = (__int64)"WDiagProcessSCMNotification";
  *(_DWORD *)dword_1802A3650 = 0;
  LeaveCriticalSection(&stru_1802A35F0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 16, &WPP_fec73b95d5a537674450248f38664378_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x180029074  mov     [rsp+arg_10], rbx
0x180029079  push    rbp
0x18002907a  push    rsi
0x18002907b  push    rdi
0x18002907c  push    r12
0x18002907e  push    r13
0x180029080  sub     rsp, 80h
0x180029087  mov     rax, cs:__security_cookie
0x18002908e  xor     rax, rsp
0x180029091  mov     [rsp+0A8h+var_38], rax
0x180029096  mov     ebx, edx
0x180029098  mov     esi, ecx
0x18002909a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800290a1  lea     rbp, WPP_GLOBAL_Control
0x1800290a8  lea     r12, WPP_fec73b95d5a537674450248f38664378_Traceguids
0x1800290af  cmp     rcx, rbp
0x1800290b2  jnz     loc_1800291FB
0x1800290b8  call    cs:__imp_GetCurrentThreadId
0x1800290be  lea     rcx, stru_1802A35F0; lpCriticalSection
0x1800290c5  mov     edi, eax
0x1800290c7  call    cs:__imp_EnterCriticalSection
0x1800290cd  mov     rcx, cs:qword_1802A3640; hHandle
0x1800290d4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800290d7  call    cs:__imp_WaitForSingleObject
0x1800290dd  test    byte ptr cs:dword_1802A3648, 4
0x1800290e4  lea     r13, aWdiagprocesssc; "WDiagProcessSCMNotification"
0x1800290eb  lea     rdx, qword_1802A35E8
0x1800290f2  jnz     loc_18002933E
0x1800290f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800290ff  or      cs:dword_1802A3648, 4
0x180029106  mov     eax, esi
0x180029108  mov     cs:dword_1802A3650, edi
0x18002910e  mov     cs:dword_1802A3654, 9Bh
0x180029118  mov     cs:qword_1802A3658, r13
0x18002911f  sub     eax, 1
0x180029122  jz      short loc_18002912D
0x180029124  sub     eax, 4
0x180029127  jnz     loc_180029224
0x18002912d  xorps   xmm0, xmm0
0x180029130  lea     rcx, [rsp+0A8h+SystemTime]; lpSystemTime
0x180029135  movups  xmmword ptr [rsp+0A8h+SystemTime.wYear], xmm0
0x18002913a  call    cs:__imp_GetSystemTime
0x180029140  lea     rdx, FileTime; lpFileTime
0x180029147  lea     rcx, [rsp+0A8h+SystemTime]; lpSystemTime
0x18002914c  call    cs:__imp_SystemTimeToFileTime
0x180029152  test    eax, eax
0x180029154  jz      loc_18002942D
0x18002915a  mov     rcx, cs:WPP_GLOBAL_Control
0x180029161  cmp     rcx, rbp
0x180029164  jnz     loc_180029438
0x18002916a  test    byte ptr cs:dword_1802A3648, 4
0x180029171  mov     ebx, 0FBh
0x180029176  jz      loc_180029480
0x18002917c  and     cs:dword_1802A3648, 0FFFFFFFBh
0x180029183  lea     rcx, stru_1802A35F0; lpCriticalSection
0x18002918a  mov     cs:dword_1802A3660, ebx
0x180029190  mov     cs:qword_1802A3668, r13
0x180029197  mov     cs:dword_1802A3650, 0
0x1800291a1  call    cs:__imp_LeaveCriticalSection
0x1800291a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800291ae  cmp     rcx, rbp
0x1800291b1  jnz     short loc_1800291D9
0x1800291b3  xor     eax, eax
0x1800291b5  mov     rcx, [rsp+0A8h+var_38]
0x1800291ba  xor     rcx, rsp; StackCookie
0x1800291bd  call    __security_check_cookie
0x1800291c2  mov     rbx, [rsp+0A8h+arg_10]
0x1800291ca  add     rsp, 80h
0x1800291d1  pop     r13
0x1800291d3  pop     r12
0x1800291d5  pop     rdi
0x1800291d6  pop     rsi
0x1800291d7  pop     rbp
0x1800291d8  retn
0x1800291d9  test    dword ptr [rcx+0E4h], 200h
0x1800291e3  jz      short loc_1800291B3
0x1800291e5  mov     rcx, [rcx+0D8h]
0x1800291ec  mov     edx, 10h
0x1800291f1  mov     r8, r12
0x1800291f4  call    WPP_SF_
0x1800291f9  jmp     short loc_1800291B3
0x1800291fb  test    dword ptr [rcx+0E4h], 200h
0x180029205  jz      loc_1800290B8
0x18002920b  mov     rcx, [rcx+0D8h]
0x180029212  mov     edx, 0Ah
0x180029217  mov     r8, r12
0x18002921a  call    WPP_SF_
0x18002921f  jmp     loc_1800290B8
0x180029224  sub     eax, 8
0x180029227  jnz     short loc_18002928E
0x180029229  mov     eax, ebx
0x18002922b  test    ebx, ebx
0x18002922d  jz      loc_180029302
0x180029233  sub     eax, 2
0x180029236  jz      loc_180029302
0x18002923c  sub     eax, 2
0x18002923f  jz      loc_1800293DE
0x180029245  sub     eax, 2
0x180029248  jnz     loc_1800292E1
0x18002924e  lea     rcx, stru_1802A36B8; lpFileTime
0x180029255  call    ?WDiagGetTime@@YAKPEAU_FILETIME@@@Z; WDiagGetTime(_FILETIME *)
0x18002925a  mov     rcx, cs:WPP_GLOBAL_Control
0x180029261  cmp     rcx, rbp
0x180029264  jz      loc_18002916A
0x18002926a  cmp     byte ptr [rcx+0E1h], 3
0x180029271  jb      loc_18002916A
0x180029277  test    byte ptr [rcx+0E4h], 4
0x18002927e  jz      loc_18002916A
0x180029284  mov     edx, 0Ch
0x180029289  jmp     loc_18002932A
0x18002928e  cmp     eax, 1
0x180029291  jz      loc_1800293B6
0x180029297  cmp     rcx, rbp
0x18002929a  jz      loc_18002916A
0x1800292a0  cmp     byte ptr [rcx+0E1h], 3
0x1800292a7  jb      loc_18002916A
0x1800292ad  test    byte ptr [rcx+0E4h], 4
0x1800292b4  jz      loc_18002916A
0x1800292ba  mov     rcx, [rcx+0D8h]
0x1800292c1  mov     edx, 0Fh
0x1800292c6  mov     r9d, esi
0x1800292c9  mov     dword ptr [rsp+0A8h+var_88], ebx
0x1800292cd  mov     r8, r12
0x1800292d0  call    WPP_SF_DD
0x1800292d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800292dc  jmp     loc_18002916A
0x1800292e1  sub     eax, 1
0x1800292e4  jz      loc_18002924E
0x1800292ea  sub     eax, 2
0x1800292ed  jz      short loc_180029302
0x1800292ef  sub     eax, 1
0x1800292f2  jz      short loc_180029302
0x1800292f4  sub     eax, 1
0x1800292f7  jz      short loc_180029302
0x1800292f9  cmp     eax, 7
0x1800292fc  jz      loc_18002924E
0x180029302  cmp     rcx, rbp
0x180029305  jz      loc_18002916A
0x18002930b  cmp     byte ptr [rcx+0E1h], 3
0x180029312  jb      loc_18002916A
0x180029318  test    byte ptr [rcx+0E4h], 4
0x18002931f  jz      loc_18002916A
0x180029325  mov     edx, 0Dh
0x18002932a  mov     rcx, [rcx+0D8h]
0x180029331  mov     r9d, ebx
0x180029334  mov     r8, r12
0x180029337  call    WPP_SF_d
0x18002933c  jmp     short loc_1800292D5
0x18002933e  mov     rcx, cs:WPP_GLOBAL_Control
0x180029345  cmp     rcx, rbp
0x180029348  jz      loc_1800290FF
0x18002934e  cmp     byte ptr [rcx+0E1h], 1
0x180029355  jb      loc_1800290FF
0x18002935b  test    byte ptr [rcx+0E4h], 40h
0x180029362  jz      loc_1800290FF
0x180029368  mov     eax, cs:dword_1802A3654
0x18002936e  lea     r9, ?g_WDiag@@3U_WDIAG_GLOBAL_CONTEXT@@A; _WDIAG_GLOBAL_CONTEXT g_WDiag
0x180029375  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18002937c  mov     dword ptr [rsp+0A8h+var_58], 9Bh; char
0x180029384  mov     [rsp+0A8h+var_60], r13; __int64
0x180029389  mov     dword ptr [rsp+0A8h+var_68], edi; char
0x18002938d  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x180029391  mov     rax, cs:qword_1802A3658
0x180029398  mov     [rsp+0A8h+var_78], rax; __int64
0x18002939d  mov     eax, cs:dword_1802A3650
0x1800293a3  mov     dword ptr [rsp+0A8h+var_80], eax; char
0x1800293a7  mov     qword ptr [rsp+0A8h+var_88], rdx; char
0x1800293ac  call    WPP_SF_qqdsddsd
0x1800293b1  jmp     loc_1800290F8
0x1800293b6  sub     ebx, 5
0x1800293b9  jz      short loc_1800293CD
0x1800293bb  cmp     ebx, 1
0x1800293be  jnz     loc_18002916A
0x1800293c4  lea     rcx, qword_1802A36C8
0x1800293cb  jmp     short loc_1800293D4
0x1800293cd  lea     rcx, stru_1802A36C0; lpFileTime
0x1800293d4  call    ?WDiagGetTime@@YAKPEAU_FILETIME@@@Z; WDiagGetTime(_FILETIME *)
0x1800293d9  jmp     loc_1800292D5
0x1800293de  lea     rcx, stru_1802A36B0; lpFileTime
0x1800293e5  call    ?WDiagGetTime@@YAKPEAU_FILETIME@@@Z; WDiagGetTime(_FILETIME *)
0x1800293ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800293f1  cmp     rcx, rbp
0x1800293f4  jz      loc_18002916A
0x1800293fa  cmp     byte ptr [rcx+0E1h], 3
0x180029401  jb      loc_18002916A
0x180029407  test    byte ptr [rcx+0E4h], 4
0x18002940e  jz      loc_18002916A
0x180029414  mov     rcx, [rcx+0D8h]
0x18002941b  mov     edx, 0Bh
0x180029420  mov     r8, r12
0x180029423  call    WPP_SF_
0x180029428  jmp     loc_1800292D5
0x18002942d  call    cs:__imp_GetLastError
0x180029433  jmp     loc_18002915A
0x180029438  cmp     byte ptr [rcx+0E1h], 3
0x18002943f  jb      loc_18002916A
0x180029445  test    byte ptr [rcx+0E4h], 4
0x18002944c  jz      loc_18002916A
0x180029452  mov     rcx, [rcx+0D8h]
0x180029459  lea     rax, aShutdown; "SHUTDOWN"
0x180029460  cmp     ebx, 1
0x180029463  lea     r9, aStop; "STOP"
0x18002946a  mov     edx, 0Eh
0x18002946f  mov     r8, r12
0x180029472  cmovnz  r9, rax
0x180029476  call    WPP_SF_s
0x18002947b  jmp     loc_1800292D5
0x180029480  cmp     rcx, rbp
0x180029483  jz      loc_18002917C
0x180029489  cmp     byte ptr [rcx+0E1h], 1
0x180029490  jb      loc_18002917C
0x180029496  test    byte ptr [rcx+0E4h], 40h
0x18002949d  jz      loc_18002917C
0x1800294a3  call    cs:__imp_GetCurrentThreadId
0x1800294a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800294b0  lea     r9, ?g_WDiag@@3U_WDIAG_GLOBAL_CONTEXT@@A; _WDIAG_GLOBAL_CONTEXT g_WDiag
0x1800294b7  mov     dword ptr [rsp+0A8h+var_58], ebx; char
0x1800294bb  mov     [rsp+0A8h+var_60], r13; __int64
0x1800294c0  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x1800294c4  mov     eax, cs:dword_1802A3660
0x1800294ca  mov     rcx, [rcx+0D8h]; LoggerHandle
0x1800294d1  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x1800294d5  mov     rax, cs:qword_1802A3668
0x1800294dc  mov     [rsp+0A8h+var_78], rax; __int64
0x1800294e1  lea     rax, qword_1802A35E8
0x1800294e8  mov     qword ptr [rsp+0A8h+var_88], rax; char
0x1800294ed  call    WPP_SF_qqDsdDsd
0x1800294f2  jmp     loc_18002917C
```
