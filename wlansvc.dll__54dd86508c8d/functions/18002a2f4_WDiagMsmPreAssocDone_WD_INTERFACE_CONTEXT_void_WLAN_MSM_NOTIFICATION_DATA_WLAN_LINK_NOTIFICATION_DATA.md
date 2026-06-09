# WDiagMsmPreAssocDone(_WD_INTERFACE_CONTEXT *,void *,_WLAN_MSM_NOTIFICATION_DATA *,_WLAN_LINK_NOTIFICATION_DATA *)

- ea: `0x18002a2f4`
- end: `0x18002a7df`
- name: `?WDiagMsmPreAssocDone@@YAKPEAU_WD_INTERFACE_CONTEXT@@PEAXPEAU_WLAN_MSM_NOTIFICATION_DATA@@PEAU_WLAN_LINK_NOTIFICATION_DATA@@@Z`
- size: `1259`
- prototype: `unsigned int __fastcall(struct _WD_INTERFACE_CONTEXT *, void *, struct _WLAN_MSM_NOTIFICATION_DATA *, struct _WLAN_LINK_NOTIFICATION_DATA *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x18001226c`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18001e950`
- `0x18002a2f4`
- `0x18002bde8`
- `0x18002c96c`
- `0x18002d18c`
- `0x180106340`
- `0x180107330`
- `0x1801c81ac`
- `0x1801c82e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a6e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a77e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a6e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a77e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a408`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a52f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a408`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a52f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a415`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a53c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a415`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a53c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a3fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a522`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a686`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a71c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a3fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a522`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a686`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a71c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002a377`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002a377`

## pseudocode

```c
__int64 __fastcall WDiagMsmPreAssocDone(
        struct _WD_INTERFACE_CONTEXT *a1,
        void *a2,
        struct _WLAN_MSM_NOTIFICATION_DATA *a3,
        struct _WLAN_LINK_NOTIFICATION_DATA *a4)
{
  ULONGLONG TickCount64; // rax
  __int64 v8; // rdx
  ULONGLONG v9; // r12
  DWORD CurrentThreadId; // esi
  struct _PM_PROFILE *v11; // r8
  struct _DOT11_SSID *v12; // r9
  struct _WD_CONNECTION_CONTEXT *MatchingConnection; // rax
  struct _WD_CONNECTION_CONTEXT *v14; // rsi
  PVOID *v15; // rcx
  unsigned int v16; // ebx
  char *v17; // rdi
  DWORD v18; // r15d
  __int128 v19; // xmm1
  char v20; // al
  char v21; // al
  enum _DOT11_BSS_TYPE v23; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+28h] [rbp-D8h]
  _OWORD v25[10]; // [rsp+60h] [rbp-A0h] BYREF

  LODWORD(v25[0]) = 0;
  memset_0((char *)v25 + 4, 0, 0x9Cu);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 39, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
  TickCount64 = GetTickCount64();
  v9 = TickCount64;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      40,
      &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids,
      (unsigned int)TickCount64);
  }
  v23 = 0;
  WDiagQueryDot11DataEx(a1, v8, v25, 0);
  if ( !a2 && a4 )
    a2 = (void *)*((_QWORD *)a4 + 1);
  CurrentThreadId = GetCurrentThreadId();
  EnterCriticalSection((LPCRITICAL_SECTION)a1 + 84);
  WaitForSingleObject(*((HANDLE *)a1 + 430), 0xFFFFFFFF);
  if ( (*((_BYTE *)a1 + 3448) & 4) != 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 225)
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
  {
    WPP_SF_qqdsddsd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      (_BYTE)a1 + 24,
      *((_DWORD *)a1 + 864),
      *((_QWORD *)a1 + 433),
      *((_DWORD *)a1 + 865),
      CurrentThreadId,
      (__int64)"WDiagMsmPreAssocDone",
      249);
  }
  *((_DWORD *)a1 + 862) |= 4u;
  *((_DWORD *)a1 + 864) = CurrentThreadId;
  *((_DWORD *)a1 + 865) = 1017;
  *((_QWORD *)a1 + 433) = "WDiagMsmPreAssocDone";
  MatchingConnection = FindMatchingConnection(a1, a2, v11, v12, v23, 1u, 2u);
  v14 = MatchingConnection;
  if ( MatchingConnection )
  {
    v17 = (char *)MatchingConnection + 3920;
    v18 = GetCurrentThreadId();
    EnterCriticalSection((LPCRITICAL_SECTION)(v17 + 8));
    WaitForSingleObject(*((HANDLE *)v17 + 11), 0xFFFFFFFF);
    if ( (v17[96] & 4) != 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
    {
      WPP_SF_qqdsddsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (char)v17,
        *((_DWORD *)v17 + 26),
        *((_QWORD *)v17 + 14),
        *((_DWORD *)v17 + 27),
        v18,
        (__int64)"WDiagMsmPreAssocDone",
        10);
    }
    *((_DWORD *)v17 + 24) |= 4u;
    *((_DWORD *)v17 + 26) = v18;
    *((_QWORD *)v17 + 14) = "WDiagMsmPreAssocDone";
    *((_DWORD *)v17 + 27) = 1034;
    WDiagGetTime((LPFILETIME)v14 + 180);
    *((_QWORD *)v14 + 182) = v9;
    *((_OWORD *)v14 + 80) = v25[0];
    *((_OWORD *)v14 + 81) = v25[1];
    *((_OWORD *)v14 + 82) = v25[2];
    *((_OWORD *)v14 + 83) = v25[3];
    *((_OWORD *)v14 + 84) = v25[4];
    *((_OWORD *)v14 + 85) = v25[5];
    *((_OWORD *)v14 + 86) = v25[6];
    *((_OWORD *)v14 + 87) = v25[7];
    *((_OWORD *)v14 + 88) = v25[8];
    v19 = v25[9];
    *((_DWORD *)v14 + 299) |= 2u;
    *((_OWORD *)v14 + 89) = v19;
    if ( (v17[96] & 4) == 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
    {
      v20 = GetCurrentThreadId();
      WPP_SF_qqDsdDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (char)v17,
        v24,
        *((_QWORD *)v17 + 16),
        *((_DWORD *)v17 + 30),
        v20,
        (__int64)"WDiagMsmPreAssocDone",
        18);
    }
    *((_DWORD *)v17 + 30) = 1042;
    *((_DWORD *)v17 + 24) &= ~4u;
    *((_QWORD *)v17 + 16) = "WDiagMsmPreAssocDone";
    *((_DWORD *)v17 + 26) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v17 + 8));
    if ( (*((_BYTE *)a1 + 3448) & 4) == 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
    {
      v21 = GetCurrentThreadId();
      WPP_SF_qqDsdDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (_BYTE)a1 + 24,
        v24,
        *((_QWORD *)a1 + 435),
        *((_DWORD *)a1 + 868),
        v21,
        (__int64)"WDiagMsmPreAssocDone",
        19);
    }
    *((_DWORD *)a1 + 862) &= ~4u;
    *((_DWORD *)a1 + 868) = 1043;
    *((_QWORD *)a1 + 435) = "WDiagMsmPreAssocDone";
    *((_DWORD *)a1 + 864) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)a1 + 84);
    v15 = (PVOID *)WPP_GLOBAL_Control;
    v16 = 0;
  }
  else
  {
    WDiagReleaseExLock(a1, (struct _WD_INTERFACE_CONTEXT *)((char *)a1 + 3352), "WDiagMsmPreAssocDone", 0x402u);
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 41, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    v16 = 1168;
  }
  if ( v15 != &WPP_GLOBAL_Control && (*((_DWORD *)v15 + 57) & 0x200) != 0 )
    WPP_SF_(v15[27], 42, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
  return v16;
}

```

## disassembly

```asm
0x18002a2f4  mov     [rsp-8+arg_10], rbx
0x18002a2f9  push    rbp
0x18002a2fa  push    rsi
0x18002a2fb  push    rdi
0x18002a2fc  push    r12
0x18002a2fe  push    r13
0x18002a300  push    r14
0x18002a302  push    r15
0x18002a304  lea     rbp, [rsp-10h]
0x18002a309  sub     rsp, 110h
0x18002a310  mov     rax, cs:__security_cookie
0x18002a317  xor     rax, rsp
0x18002a31a  mov     [rbp+40h+var_40], rax
0x18002a31e  mov     rdi, rdx
0x18002a321  mov     r14, rcx
0x18002a324  xor     r15d, r15d
0x18002a327  lea     rcx, [rsp+140h+var_E0+4]; void *
0x18002a32c  xor     edx, edx; Val
0x18002a32e  mov     dword ptr [rsp+140h+var_E0], r15d
0x18002a333  mov     r8d, 9Ch; Size
0x18002a339  mov     rbx, r9
0x18002a33c  call    memset_0
0x18002a341  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a348  lea     r13, WPP_GLOBAL_Control
0x18002a34f  cmp     rcx, r13
0x18002a352  jz      short loc_18002A377
0x18002a354  test    dword ptr [rcx+0E4h], 200h
0x18002a35e  jz      short loc_18002A377
0x18002a360  mov     rcx, [rcx+0D8h]
0x18002a367  lea     edx, [r15+27h]
0x18002a36b  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x18002a372  call    WPP_SF_
0x18002a377  call    cs:__imp_GetTickCount64
0x18002a37d  mov     r12, rax
0x18002a380  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a387  cmp     rcx, r13
0x18002a38a  jz      short loc_18002A3B9
0x18002a38c  cmp     byte ptr [rcx+0E1h], 3
0x18002a393  jb      short loc_18002A3B9
0x18002a395  test    byte ptr [rcx+0E4h], 10h
0x18002a39c  jz      short loc_18002A3B9
0x18002a39e  mov     rcx, [rcx+0D8h]
0x18002a3a5  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x18002a3ac  mov     r9d, r12d
0x18002a3af  mov     edx, 28h ; '('
0x18002a3b4  call    WPP_SF_d
0x18002a3b9  mov     [rsp+140h+var_F8], r15
0x18002a3be  lea     r8, [rsp+140h+var_E0]
0x18002a3c3  mov     qword ptr [rsp+140h+var_100], r15
0x18002a3c8  xor     r9d, r9d
0x18002a3cb  mov     qword ptr [rsp+140h+var_108], r15
0x18002a3d0  mov     rcx, r14
0x18002a3d3  mov     qword ptr [rsp+140h+var_110], r15
0x18002a3d8  mov     qword ptr [rsp+140h+var_118], r15
0x18002a3dd  mov     qword ptr [rsp+140h+var_120], r15
0x18002a3e2  call    ?WDiagQueryDot11DataEx@@YAKPEAU_WD_INTERFACE_CONTEXT@@W4WDIAG_STATISTICS_QUERY_REASON@@PEAUWDIAG_PACKET_STATISTICS@@PEAU_DOT11_SSID@@PEAY05EPEAUWDIAG_SIGNAL_QUALITY@@PEAK666@Z; WDiagQueryDot11DataEx(_WD_INTERFACE_CONTEXT *,WDIAG_STATISTICS_QUERY_REASON,WDIAG_PACKET_STATISTICS *,_DOT11_SSID *,uchar (*)[6],WDIAG_SIGNAL_QUALITY *,ulong *,ulong *,ulong *,ulong *)
0x18002a3e7  test    rdi, rdi
0x18002a3ea  jnz     short loc_18002A3F5
0x18002a3ec  test    rbx, rbx
0x18002a3ef  jz      short loc_18002A3F5
0x18002a3f1  mov     rdi, [rbx+8]
0x18002a3f5  lea     rbx, [r14+0D18h]
0x18002a3fc  call    cs:__imp_GetCurrentThreadId
0x18002a402  lea     rcx, [rbx+8]; lpCriticalSection
0x18002a406  mov     esi, eax
0x18002a408  call    cs:__imp_EnterCriticalSection
0x18002a40e  mov     rcx, [rbx+58h]; hHandle
0x18002a412  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002a415  call    cs:__imp_WaitForSingleObject
0x18002a41b  test    byte ptr [rbx+60h], 4
0x18002a41f  lea     rax, aWdiagmsmpreass; "WDiagMsmPreAssocDone"
0x18002a426  jz      short loc_18002A489
0x18002a428  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a42f  cmp     rcx, r13
0x18002a432  jz      short loc_18002A489
0x18002a434  cmp     byte ptr [rcx+0E1h], 1
0x18002a43b  jb      short loc_18002A489
0x18002a43d  test    byte ptr [rcx+0E4h], 40h
0x18002a444  jz      short loc_18002A489
0x18002a446  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18002a44d  mov     r9, r14
0x18002a450  mov     dword ptr [rsp+140h+var_F0], 3F9h; char
0x18002a458  mov     [rsp+140h+var_F8], rax; __int64
0x18002a45d  mov     eax, [rbx+6Ch]
0x18002a460  mov     dword ptr [rsp+140h+var_100], esi; char
0x18002a464  mov     dword ptr [rsp+140h+var_108], eax; char
0x18002a468  mov     rax, [rbx+70h]
0x18002a46c  mov     qword ptr [rsp+140h+var_110], rax; __int64
0x18002a471  mov     eax, [rbx+68h]
0x18002a474  mov     dword ptr [rsp+140h+var_118], eax; char
0x18002a478  mov     qword ptr [rsp+140h+var_120], rbx; enum _DOT11_BSS_TYPE
0x18002a47d  call    WPP_SF_qqdsddsd
0x18002a482  lea     rax, aWdiagmsmpreass; "WDiagMsmPreAssocDone"
0x18002a489  or      dword ptr [rbx+60h], 4
0x18002a48d  mov     rdx, rdi; void *
0x18002a490  mov     [rsp+140h+var_110], 2; unsigned int
0x18002a498  mov     rcx, r14; struct _WD_INTERFACE_CONTEXT *
0x18002a49b  mov     dword ptr [rsp+140h+var_118], 1; unsigned int
0x18002a4a3  mov     [rbx+68h], esi
0x18002a4a6  mov     dword ptr [rbx+6Ch], 3F9h
0x18002a4ad  mov     [rbx+70h], rax
0x18002a4b1  call    ?FindMatchingConnection@@YAPEAU_WD_CONNECTION_CONTEXT@@PEAU_WD_INTERFACE_CONTEXT@@PEAXPEAU_PM_PROFILE@@PEAU_DOT11_SSID@@W4_DOT11_BSS_TYPE@@KK@Z; FindMatchingConnection(_WD_INTERFACE_CONTEXT *,void *,_PM_PROFILE *,_DOT11_SSID *,_DOT11_BSS_TYPE,ulong,ulong)
0x18002a4b6  mov     rsi, rax
0x18002a4b9  test    rax, rax
0x18002a4bc  jnz     short loc_18002A51B
0x18002a4be  mov     r9d, 402h; unsigned int
0x18002a4c4  lea     r8, aWdiagmsmpreass; "WDiagMsmPreAssocDone"
0x18002a4cb  mov     rdx, rbx; struct _WDIAG_RW_LOCK *
0x18002a4ce  mov     rcx, r14; void *
0x18002a4d1  call    ?WDiagReleaseExLock@@YAXPEAXPEAU_WDIAG_RW_LOCK@@PEADK@Z; WDiagReleaseExLock(void *,_WDIAG_RW_LOCK *,char *,ulong)
0x18002a4d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a4dd  cmp     rcx, r13
0x18002a4e0  jz      short loc_18002A511
0x18002a4e2  cmp     byte ptr [rcx+0E1h], 1
0x18002a4e9  jb      short loc_18002A511
0x18002a4eb  test    byte ptr [rcx+0E4h], 10h
0x18002a4f2  jz      short loc_18002A511
0x18002a4f4  mov     rcx, [rcx+0D8h]
0x18002a4fb  lea     edx, [rsi+29h]
0x18002a4fe  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x18002a505  call    WPP_SF_
0x18002a50a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a511  mov     ebx, 490h
0x18002a516  jmp     loc_18002A78D
0x18002a51b  lea     rdi, [rax+0F50h]
0x18002a522  call    cs:__imp_GetCurrentThreadId
0x18002a528  lea     rcx, [rdi+8]; lpCriticalSection
0x18002a52c  mov     r15d, eax
0x18002a52f  call    cs:__imp_EnterCriticalSection
0x18002a535  mov     rcx, [rdi+58h]; hHandle
0x18002a539  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002a53c  call    cs:__imp_WaitForSingleObject
0x18002a542  test    byte ptr [rdi+60h], 4
0x18002a546  jz      short loc_18002A5B1
0x18002a548  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a54f  lea     rax, WPP_GLOBAL_Control
0x18002a556  cmp     rcx, rax
0x18002a559  jz      short loc_18002A5B1
0x18002a55b  cmp     byte ptr [rcx+0E1h], 1
0x18002a562  jb      short loc_18002A5B1
0x18002a564  test    byte ptr [rcx+0E4h], 40h
0x18002a56b  jz      short loc_18002A5B1
0x18002a56d  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18002a574  lea     rax, aWdiagmsmpreass; "WDiagMsmPreAssocDone"
0x18002a57b  mov     dword ptr [rsp+140h+var_F0], 40Ah; char
0x18002a583  mov     r9, rsi
0x18002a586  mov     [rsp+140h+var_F8], rax; __int64
0x18002a58b  mov     eax, [rdi+6Ch]
0x18002a58e  mov     dword ptr [rsp+140h+var_100], r15d; char
0x18002a593  mov     dword ptr [rsp+140h+var_108], eax; char
0x18002a597  mov     rax, [rdi+70h]
0x18002a59b  mov     qword ptr [rsp+140h+var_110], rax; __int64
0x18002a5a0  mov     eax, [rdi+68h]
0x18002a5a3  mov     dword ptr [rsp+140h+var_118], eax; int
0x18002a5a7  mov     qword ptr [rsp+140h+var_120], rdi; char
0x18002a5ac  call    WPP_SF_qqdsddsd
0x18002a5b1  or      dword ptr [rdi+60h], 4
0x18002a5b5  lea     rcx, [rsi+5A0h]; lpFileTime
0x18002a5bc  mov     [rdi+68h], r15d
0x18002a5c0  lea     r15, aWdiagmsmpreass; "WDiagMsmPreAssocDone"
0x18002a5c7  mov     [rdi+70h], r15
0x18002a5cb  mov     dword ptr [rdi+6Ch], 40Ah
0x18002a5d2  call    ?WDiagGetTime@@YAKPEAU_FILETIME@@@Z; WDiagGetTime(_FILETIME *)
0x18002a5d7  mov     [rsi+5B0h], r12
0x18002a5de  mov     r12d, 412h
0x18002a5e4  movups  xmm0, [rsp+140h+var_E0]
0x18002a5e9  movups  xmmword ptr [rsi+500h], xmm0
0x18002a5f0  movups  xmm1, [rsp+140h+var_D0]
0x18002a5f5  movups  xmmword ptr [rsi+510h], xmm1
0x18002a5fc  movups  xmm0, [rbp+40h+var_C0]
0x18002a600  movups  xmmword ptr [rsi+520h], xmm0
0x18002a607  movups  xmm1, [rbp+40h+var_B0]
0x18002a60b  movups  xmmword ptr [rsi+530h], xmm1
0x18002a612  movups  xmm0, [rbp+40h+var_A0]
0x18002a616  movups  xmmword ptr [rsi+540h], xmm0
0x18002a61d  movups  xmm1, [rbp+40h+var_90]
0x18002a621  movups  xmmword ptr [rsi+550h], xmm1
0x18002a628  movups  xmm0, [rbp+40h+var_80]
0x18002a62c  movups  xmmword ptr [rsi+560h], xmm0
0x18002a633  movups  xmm1, [rbp+40h+var_70]
0x18002a637  movups  xmmword ptr [rsi+570h], xmm1
0x18002a63e  movups  xmm0, [rbp+40h+var_60]
0x18002a642  movups  xmmword ptr [rsi+580h], xmm0
0x18002a649  movups  xmm1, [rbp+40h+var_50]
0x18002a64d  or      dword ptr [rsi+4ACh], 2
0x18002a654  movups  xmmword ptr [rsi+590h], xmm1
0x18002a65b  test    byte ptr [rdi+60h], 4
0x18002a65f  jnz     short loc_18002A6C8
0x18002a661  mov     rax, cs:WPP_GLOBAL_Control
0x18002a668  lea     rcx, WPP_GLOBAL_Control
0x18002a66f  cmp     rax, rcx
0x18002a672  jz      short loc_18002A6C8
0x18002a674  cmp     byte ptr [rax+0E1h], 1
0x18002a67b  jb      short loc_18002A6C8
0x18002a67d  test    byte ptr [rax+0E4h], 40h
0x18002a684  jz      short loc_18002A6C8
0x18002a686  call    cs:__imp_GetCurrentThreadId
0x18002a68c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a693  mov     r9, rsi
0x18002a696  mov     dword ptr [rsp+140h+var_F0], r12d; char
0x18002a69b  mov     [rsp+140h+var_F8], r15; __int64
0x18002a6a0  mov     dword ptr [rsp+140h+var_100], eax; char
0x18002a6a4  mov     eax, [rdi+78h]
0x18002a6a7  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18002a6ae  mov     dword ptr [rsp+140h+var_108], eax; char
0x18002a6b2  mov     rax, [rdi+80h]
0x18002a6b9  mov     qword ptr [rsp+140h+var_110], rax; __int64
0x18002a6be  mov     qword ptr [rsp+140h+var_120], rdi; char
0x18002a6c3  call    WPP_SF_qqDsdDsd
0x18002a6c8  mov     esi, 0FFFFFFFBh
0x18002a6cd  mov     [rdi+78h], r12d
0x18002a6d1  and     [rdi+60h], esi
0x18002a6d4  lea     rcx, [rdi+8]; lpCriticalSection
0x18002a6d8  mov     [rdi+80h], r15
0x18002a6df  mov     dword ptr [rdi+68h], 0
0x18002a6e6  call    cs:__imp_LeaveCriticalSection
0x18002a6ec  test    byte ptr [rbx+60h], 4
0x18002a6f0  mov     edi, 413h
0x18002a6f5  jnz     short loc_18002A75F
0x18002a6f7  mov     rax, cs:WPP_GLOBAL_Control
0x18002a6fe  lea     r13, WPP_GLOBAL_Control
0x18002a705  cmp     rax, r13
0x18002a708  jz      short loc_18002A766
0x18002a70a  cmp     byte ptr [rax+0E1h], 1
0x18002a711  jb      short loc_18002A766
0x18002a713  test    byte ptr [rax+0E4h], 40h
0x18002a71a  jz      short loc_18002A766
0x18002a71c  call    cs:__imp_GetCurrentThreadId
0x18002a722  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a729  mov     r9, r14
0x18002a72c  mov     dword ptr [rsp+140h+var_F0], edi; char
0x18002a730  mov     [rsp+140h+var_F8], r15; __int64
0x18002a735  mov     dword ptr [rsp+140h+var_100], eax; char
0x18002a739  mov     eax, [rbx+78h]
0x18002a73c  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18002a743  mov     dword ptr [rsp+140h+var_108], eax; char
0x18002a747  mov     rax, [rbx+80h]
0x18002a74e  mov     qword ptr [rsp+140h+var_110], rax; __int64
0x18002a753  mov     qword ptr [rsp+140h+var_120], rbx; char
0x18002a758  call    WPP_SF_qqDsdDsd
0x18002a75d  jmp     short loc_18002A766
0x18002a75f  lea     r13, WPP_GLOBAL_Control
0x18002a766  and     [rbx+60h], esi
0x18002a769  lea     rcx, [rbx+8]; lpCriticalSection
0x18002a76d  mov     [rbx+78h], edi
0x18002a770  mov     [rbx+80h], r15
0x18002a777  mov     dword ptr [rbx+68h], 0
0x18002a77e  call    cs:__imp_LeaveCriticalSection
0x18002a784  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a78b  xor     ebx, ebx
0x18002a78d  cmp     rcx, r13
0x18002a790  jz      short loc_18002A7B6
0x18002a792  test    dword ptr [rcx+0E4h], 200h
0x18002a79c  jz      short loc_18002A7B6
0x18002a79e  mov     rcx, [rcx+0D8h]
0x18002a7a5  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x18002a7ac  mov     edx, 2Ah ; '*'
0x18002a7b1  call    WPP_SF_
0x18002a7b6  mov     eax, ebx
0x18002a7b8  mov     rcx, [rbp+40h+var_40]
0x18002a7bc  xor     rcx, rsp; StackCookie
0x18002a7bf  call    __security_check_cookie
0x18002a7c4  mov     rbx, [rsp+140h+arg_10]
0x18002a7cc  add     rsp, 110h
0x18002a7d3  pop     r15
0x18002a7d5  pop     r14
0x18002a7d7  pop     r13
0x18002a7d9  pop     r12
0x18002a7db  pop     rdi
0x18002a7dc  pop     rsi
0x18002a7dd  pop     rbp
0x18002a7de  retn
```
