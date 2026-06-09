# WDiagMsmConnected(_WD_INTERFACE_CONTEXT *,void *,_WLAN_MSM_NOTIFICATION_DATA *)

- ea: `0x180029f20`
- end: `0x18002a2eb`
- name: `?WDiagMsmConnected@@YAKPEAU_WD_INTERFACE_CONTEXT@@PEAXPEAU_WLAN_MSM_NOTIFICATION_DATA@@@Z`
- size: `971`
- prototype: `unsigned int __fastcall(struct _WD_INTERFACE_CONTEXT *, void *, struct _WLAN_MSM_NOTIFICATION_DATA *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18001226c`

## callees

- `0x180011530`
- `0x18001e950`
- `0x180029f20`
- `0x18002bde8`
- `0x18002c96c`
- `0x1801c81ac`
- `0x1801c82e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a217`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a2a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a217`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a2a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029f8d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a0a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029f8d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a0a9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180029f9a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a0b6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180029f9a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a0b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029f81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a09c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a19e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a246`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029f81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a09c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a19e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a246`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180029f71`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180029f71`

## pseudocode

```c
__int64 __fastcall WDiagMsmConnected(
        struct _WD_INTERFACE_CONTEXT *a1,
        void *a2,
        struct _WLAN_MSM_NOTIFICATION_DATA *a3)
{
  ULONGLONG TickCount64; // r13
  DWORD CurrentThreadId; // edi
  struct _PM_PROFILE *v8; // r8
  struct _DOT11_SSID *v9; // r9
  struct _WD_CONNECTION_CONTEXT *MatchingConnection; // rax
  struct _WD_CONNECTION_CONTEXT *v11; // rsi
  PVOID *v12; // rcx
  unsigned int v13; // ebx
  char *v14; // rdi
  DWORD v15; // r14d
  char v16; // al
  char v17; // al
  enum _DOT11_BSS_TYPE v19; // [rsp+20h] [rbp-88h]
  int v20; // [rsp+28h] [rbp-80h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 96, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
  TickCount64 = GetTickCount64();
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
      (__int64)"WDiagMsmConnected",
      124);
  }
  *((_DWORD *)a1 + 862) |= 4u;
  *((_DWORD *)a1 + 864) = CurrentThreadId;
  *((_DWORD *)a1 + 865) = 2172;
  *((_QWORD *)a1 + 433) = "WDiagMsmConnected";
  MatchingConnection = FindMatchingConnection(a1, a2, v8, v9, v19, 1u, 2u);
  v11 = MatchingConnection;
  if ( MatchingConnection )
  {
    v14 = (char *)MatchingConnection + 3920;
    v15 = GetCurrentThreadId();
    EnterCriticalSection((LPCRITICAL_SECTION)(v14 + 8));
    WaitForSingleObject(*((HANDLE *)v14 + 11), 0xFFFFFFFF);
    if ( (v14[96] & 4) != 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
    {
      WPP_SF_qqdsddsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (char)v14,
        *((_DWORD *)v14 + 26),
        *((_QWORD *)v14 + 14),
        *((_DWORD *)v14 + 27),
        v15,
        (__int64)"WDiagMsmConnected",
        141);
    }
    *((_DWORD *)v14 + 24) |= 4u;
    *((_QWORD *)v14 + 14) = "WDiagMsmConnected";
    *((_DWORD *)v14 + 26) = v15;
    *((_DWORD *)v14 + 27) = 2189;
    WDiagGetTime((LPFILETIME)v11 + 211);
    *((_DWORD *)v11 + 299) |= 0x20u;
    *((_QWORD *)v11 + 213) = TickCount64;
    if ( a3 )
      *((_DWORD *)v11 + 304) = a3->wlanConnectionMode;
    if ( (v14[96] & 4) == 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
    {
      v16 = GetCurrentThreadId();
      WPP_SF_qqDsdDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (char)v14,
        v20,
        *((_QWORD *)v14 + 16),
        *((_DWORD *)v14 + 30),
        v16,
        (__int64)"WDiagMsmConnected",
        151);
    }
    *((_DWORD *)v14 + 30) = 2199;
    *((_DWORD *)v14 + 24) &= ~4u;
    *((_QWORD *)v14 + 16) = "WDiagMsmConnected";
    *((_DWORD *)v14 + 26) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 8));
    if ( (*((_BYTE *)a1 + 3448) & 4) == 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
    {
      v17 = GetCurrentThreadId();
      WPP_SF_qqDsdDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (_BYTE)a1 + 24,
        v20,
        *((_QWORD *)a1 + 435),
        *((_DWORD *)a1 + 868),
        v17,
        (__int64)"WDiagMsmConnected",
        152);
    }
    *((_DWORD *)a1 + 862) &= ~4u;
    *((_DWORD *)a1 + 868) = 2200;
    *((_QWORD *)a1 + 435) = "WDiagMsmConnected";
    *((_DWORD *)a1 + 864) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)a1 + 84);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    v13 = 0;
  }
  else
  {
    WDiagReleaseExLock(a1, (struct _WD_INTERFACE_CONTEXT *)((char *)a1 + 3352), "WDiagMsmConnected", 0x885u);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 97, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    v13 = 1168;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 57) & 0x200) != 0 )
    WPP_SF_(v12[27], 98, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
  return v13;
}

```

## disassembly

```asm
0x180029f20  push    rbx
0x180029f22  push    rbp
0x180029f23  push    rsi
0x180029f24  push    rdi
0x180029f25  push    r12
0x180029f27  push    r13
0x180029f29  push    r14
0x180029f2b  push    r15
0x180029f2d  sub     rsp, 68h
0x180029f31  mov     r15, r8
0x180029f34  mov     rsi, rdx
0x180029f37  mov     rbp, rcx
0x180029f3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180029f41  lea     r14, WPP_GLOBAL_Control
0x180029f48  cmp     rcx, r14
0x180029f4b  jz      short loc_180029F71
0x180029f4d  test    dword ptr [rcx+0E4h], 200h
0x180029f57  jz      short loc_180029F71
0x180029f59  mov     rcx, [rcx+0D8h]
0x180029f60  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x180029f67  mov     edx, 60h ; '`'
0x180029f6c  call    WPP_SF_
0x180029f71  call    cs:__imp_GetTickCount64
0x180029f77  mov     r13, rax
0x180029f7a  lea     rbx, [rbp+0D18h]
0x180029f81  call    cs:__imp_GetCurrentThreadId
0x180029f87  lea     rcx, [rbx+8]; lpCriticalSection
0x180029f8b  mov     edi, eax
0x180029f8d  call    cs:__imp_EnterCriticalSection
0x180029f93  mov     rcx, [rbx+58h]; hHandle
0x180029f97  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180029f9a  call    cs:__imp_WaitForSingleObject
0x180029fa0  test    byte ptr [rbx+60h], 4
0x180029fa4  lea     r12, aWdiagmsmconnec; "WDiagMsmConnected"
0x180029fab  jz      short loc_18002A007
0x180029fad  mov     rcx, cs:WPP_GLOBAL_Control
0x180029fb4  cmp     rcx, r14
0x180029fb7  jz      short loc_18002A007
0x180029fb9  cmp     byte ptr [rcx+0E1h], 1
0x180029fc0  jb      short loc_18002A007
0x180029fc2  test    byte ptr [rcx+0E4h], 40h
0x180029fc9  jz      short loc_18002A007
0x180029fcb  mov     eax, [rbx+6Ch]
0x180029fce  mov     r9, rbp
0x180029fd1  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180029fd8  mov     dword ptr [rsp+0A8h+var_58], 87Ch; char
0x180029fe0  mov     [rsp+0A8h+var_60], r12; __int64
0x180029fe5  mov     dword ptr [rsp+0A8h+var_68], edi; char
0x180029fe9  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x180029fed  mov     rax, [rbx+70h]
0x180029ff1  mov     qword ptr [rsp+0A8h+var_78], rax; __int64
0x180029ff6  mov     eax, [rbx+68h]
0x180029ff9  mov     dword ptr [rsp+0A8h+var_80], eax; char
0x180029ffd  mov     qword ptr [rsp+0A8h+var_88], rbx; enum _DOT11_BSS_TYPE
0x18002a002  call    WPP_SF_qqdsddsd
0x18002a007  or      dword ptr [rbx+60h], 4
0x18002a00b  mov     rdx, rsi; void *
0x18002a00e  mov     [rsp+0A8h+var_78], 2; unsigned int
0x18002a016  mov     rcx, rbp; struct _WD_INTERFACE_CONTEXT *
0x18002a019  mov     dword ptr [rsp+0A8h+var_80], 1; unsigned int
0x18002a021  mov     [rbx+68h], edi
0x18002a024  mov     dword ptr [rbx+6Ch], 87Ch
0x18002a02b  mov     [rbx+70h], r12
0x18002a02f  call    ?FindMatchingConnection@@YAPEAU_WD_CONNECTION_CONTEXT@@PEAU_WD_INTERFACE_CONTEXT@@PEAXPEAU_PM_PROFILE@@PEAU_DOT11_SSID@@W4_DOT11_BSS_TYPE@@KK@Z; FindMatchingConnection(_WD_INTERFACE_CONTEXT *,void *,_PM_PROFILE *,_DOT11_SSID *,_DOT11_BSS_TYPE,ulong,ulong)
0x18002a034  mov     rsi, rax
0x18002a037  test    rax, rax
0x18002a03a  jnz     short loc_18002A095
0x18002a03c  mov     r9d, 885h; unsigned int
0x18002a042  mov     r8, r12; char *
0x18002a045  mov     rdx, rbx; struct _WDIAG_RW_LOCK *
0x18002a048  mov     rcx, rbp; void *
0x18002a04b  call    ?WDiagReleaseExLock@@YAXPEAXPEAU_WDIAG_RW_LOCK@@PEADK@Z; WDiagReleaseExLock(void *,_WDIAG_RW_LOCK *,char *,ulong)
0x18002a050  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a057  cmp     rcx, r14
0x18002a05a  jz      short loc_18002A08B
0x18002a05c  cmp     byte ptr [rcx+0E1h], 1
0x18002a063  jb      short loc_18002A08B
0x18002a065  test    byte ptr [rcx+0E4h], 10h
0x18002a06c  jz      short loc_18002A08B
0x18002a06e  mov     rcx, [rcx+0D8h]
0x18002a075  lea     edx, [rsi+61h]
0x18002a078  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x18002a07f  call    WPP_SF_
0x18002a084  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a08b  mov     ebx, 490h
0x18002a090  jmp     loc_18002A2AF
0x18002a095  lea     rdi, [rax+0F50h]
0x18002a09c  call    cs:__imp_GetCurrentThreadId
0x18002a0a2  lea     rcx, [rdi+8]; lpCriticalSection
0x18002a0a6  mov     r14d, eax
0x18002a0a9  call    cs:__imp_EnterCriticalSection
0x18002a0af  mov     rcx, [rdi+58h]; hHandle
0x18002a0b3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002a0b6  call    cs:__imp_WaitForSingleObject
0x18002a0bc  test    byte ptr [rdi+60h], 4
0x18002a0c0  jz      short loc_18002A12B
0x18002a0c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a0c9  lea     rax, WPP_GLOBAL_Control
0x18002a0d0  cmp     rcx, rax
0x18002a0d3  jz      short loc_18002A12B
0x18002a0d5  cmp     byte ptr [rcx+0E1h], 1
0x18002a0dc  jb      short loc_18002A12B
0x18002a0de  test    byte ptr [rcx+0E4h], 40h
0x18002a0e5  jz      short loc_18002A12B
0x18002a0e7  mov     eax, [rdi+6Ch]
0x18002a0ea  lea     rdx, aWdiagmsmconnec; "WDiagMsmConnected"
0x18002a0f1  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18002a0f8  mov     r9, rsi
0x18002a0fb  mov     dword ptr [rsp+0A8h+var_58], 88Dh; char
0x18002a103  mov     [rsp+0A8h+var_60], rdx; __int64
0x18002a108  mov     dword ptr [rsp+0A8h+var_68], r14d; char
0x18002a10d  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x18002a111  mov     rax, [rdi+70h]
0x18002a115  mov     qword ptr [rsp+0A8h+var_78], rax; __int64
0x18002a11a  mov     eax, [rdi+68h]
0x18002a11d  mov     dword ptr [rsp+0A8h+var_80], eax; int
0x18002a121  mov     qword ptr [rsp+0A8h+var_88], rdi; char
0x18002a126  call    WPP_SF_qqdsddsd
0x18002a12b  or      dword ptr [rdi+60h], 4
0x18002a12f  lea     rax, aWdiagmsmconnec; "WDiagMsmConnected"
0x18002a136  lea     rcx, [rsi+698h]; lpFileTime
0x18002a13d  mov     [rdi+70h], rax
0x18002a141  mov     [rdi+68h], r14d
0x18002a145  mov     dword ptr [rdi+6Ch], 88Dh
0x18002a14c  call    ?WDiagGetTime@@YAKPEAU_FILETIME@@@Z; WDiagGetTime(_FILETIME *)
0x18002a151  or      dword ptr [rsi+4ACh], 20h
0x18002a158  mov     [rsi+6A8h], r13
0x18002a15f  test    r15, r15
0x18002a162  jz      short loc_18002A16D
0x18002a164  mov     eax, [r15]
0x18002a167  mov     [rsi+4C0h], eax
0x18002a16d  test    byte ptr [rdi+60h], 4
0x18002a171  mov     r13d, 897h
0x18002a177  jnz     short loc_18002A1E9
0x18002a179  mov     rax, cs:WPP_GLOBAL_Control
0x18002a180  lea     r14, WPP_GLOBAL_Control
0x18002a187  cmp     rax, r14
0x18002a18a  jz      short loc_18002A1F0
0x18002a18c  cmp     byte ptr [rax+0E1h], 1
0x18002a193  jb      short loc_18002A1F0
0x18002a195  test    byte ptr [rax+0E4h], 40h
0x18002a19c  jz      short loc_18002A1F0
0x18002a19e  call    cs:__imp_GetCurrentThreadId
0x18002a1a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a1ab  lea     rdx, aWdiagmsmconnec; "WDiagMsmConnected"
0x18002a1b2  mov     dword ptr [rsp+0A8h+var_58], r13d; char
0x18002a1b7  mov     r9, rsi
0x18002a1ba  mov     [rsp+0A8h+var_60], rdx; __int64
0x18002a1bf  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x18002a1c3  mov     eax, [rdi+78h]
0x18002a1c6  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18002a1cd  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x18002a1d1  mov     rax, [rdi+80h]
0x18002a1d8  mov     qword ptr [rsp+0A8h+var_78], rax; __int64
0x18002a1dd  mov     qword ptr [rsp+0A8h+var_88], rdi; char
0x18002a1e2  call    WPP_SF_qqDsdDsd
0x18002a1e7  jmp     short loc_18002A1F0
0x18002a1e9  lea     r14, WPP_GLOBAL_Control
0x18002a1f0  mov     r15d, 0FFFFFFFBh
0x18002a1f6  mov     [rdi+78h], r13d
0x18002a1fa  and     [rdi+60h], r15d
0x18002a1fe  lea     rsi, aWdiagmsmconnec; "WDiagMsmConnected"
0x18002a205  lea     rcx, [rdi+8]; lpCriticalSection
0x18002a209  mov     [rdi+80h], rsi
0x18002a210  mov     dword ptr [rdi+68h], 0
0x18002a217  call    cs:__imp_LeaveCriticalSection
0x18002a21d  test    byte ptr [rbx+60h], 4
0x18002a221  mov     edi, 898h
0x18002a226  jnz     short loc_18002A287
0x18002a228  mov     rax, cs:WPP_GLOBAL_Control
0x18002a22f  cmp     rax, r14
0x18002a232  jz      short loc_18002A287
0x18002a234  cmp     byte ptr [rax+0E1h], 1
0x18002a23b  jb      short loc_18002A287
0x18002a23d  test    byte ptr [rax+0E4h], 40h
0x18002a244  jz      short loc_18002A287
0x18002a246  call    cs:__imp_GetCurrentThreadId
0x18002a24c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a253  mov     r9, rbp
0x18002a256  mov     dword ptr [rsp+0A8h+var_58], edi; char
0x18002a25a  mov     [rsp+0A8h+var_60], rsi; __int64
0x18002a25f  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x18002a263  mov     eax, [rbx+78h]
0x18002a266  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18002a26d  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x18002a271  mov     rax, [rbx+80h]
0x18002a278  mov     qword ptr [rsp+0A8h+var_78], rax; __int64
0x18002a27d  mov     qword ptr [rsp+0A8h+var_88], rbx; char
0x18002a282  call    WPP_SF_qqDsdDsd
0x18002a287  and     [rbx+60h], r15d
0x18002a28b  lea     rcx, [rbx+8]; lpCriticalSection
0x18002a28f  mov     [rbx+78h], edi
0x18002a292  mov     [rbx+80h], rsi
0x18002a299  mov     dword ptr [rbx+68h], 0
0x18002a2a0  call    cs:__imp_LeaveCriticalSection
0x18002a2a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a2ad  xor     ebx, ebx
0x18002a2af  cmp     rcx, r14
0x18002a2b2  jz      short loc_18002A2D8
0x18002a2b4  test    dword ptr [rcx+0E4h], 200h
0x18002a2be  jz      short loc_18002A2D8
0x18002a2c0  mov     rcx, [rcx+0D8h]
0x18002a2c7  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x18002a2ce  mov     edx, 62h ; 'b'
0x18002a2d3  call    WPP_SF_
0x18002a2d8  mov     eax, ebx
0x18002a2da  add     rsp, 68h
0x18002a2de  pop     r15
0x18002a2e0  pop     r14
0x18002a2e2  pop     r13
0x18002a2e4  pop     r12
0x18002a2e6  pop     rdi
0x18002a2e7  pop     rsi
0x18002a2e8  pop     rbp
0x18002a2e9  pop     rbx
0x18002a2ea  retn
```
