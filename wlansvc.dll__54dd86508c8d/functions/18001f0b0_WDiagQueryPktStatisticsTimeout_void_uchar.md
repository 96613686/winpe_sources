# WDiagQueryPktStatisticsTimeout(void *,uchar)

- ea: `0x18001f0b0`
- end: `0x18001f786`
- name: `?WDiagQueryPktStatisticsTimeout@@YAXPEAXE@Z`
- size: `1750`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18001f0b0`
- `0x18001f790`
- `0x18001fc84`
- `0x18002cb54`
- `0x1801c81ac`
- `0x1801c82e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f1a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f262`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f33b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f381`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f1a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f262`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f33b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f381`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f105`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f204`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f3b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f105`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f204`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f3b2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f115`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f211`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f3c2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f115`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f211`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f3c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f0f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f1f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f3a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f501`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f575`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f5e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f739`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f0f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f1f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f3a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f501`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f575`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f5e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f739`

## pseudocode

```c
void __fastcall WDiagQueryPktStatisticsTimeout(PVOID a1)
{
  DWORD CurrentThreadId; // ebx
  PVOID *v2; // rcx
  struct _WD_INTERFACE_CONTEXT *v3; // r14
  struct _WD_INTERFACE_CONTEXT *v4; // rdi
  DWORD v5; // esi
  int v6; // eax
  unsigned int v7; // edx
  PVOID *v8; // rcx
  int v9; // eax
  unsigned int v10; // edx
  unsigned int updated; // eax
  DWORD v12; // ebx
  char v13; // al
  char v14; // al
  char v15; // al
  char v16; // al
  int v17; // [rsp+28h] [rbp-70h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 152, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
  CurrentThreadId = GetCurrentThreadId();
  EnterCriticalSection(&stru_1802A35F0);
  WaitForSingleObject(qword_1802A3640, 0xFFFFFFFF);
  if ( (dword_1802A3648 & 4) == 0 )
    goto LABEL_5;
  v2 = (PVOID *)WPP_GLOBAL_Control;
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
      (__int64)"WDiagQueryPktStatisticsTimeout",
      34);
LABEL_5:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  dword_1802A3648 |= 4u;
  *(_DWORD *)dword_1802A3654 = 3362;
  v3 = 0;
  v4 = qword_1802A3670;
  *(_DWORD *)dword_1802A3650 = CurrentThreadId;
  qword_1802A3658 = (__int64)"WDiagQueryPktStatisticsTimeout";
  if ( qword_1802A3670 == (struct _WD_INTERFACE_CONTEXT *)&qword_1802A3670 )
    goto LABEL_7;
  do
  {
    v5 = GetCurrentThreadId();
    EnterCriticalSection((LPCRITICAL_SECTION)v4 + 84);
    WaitForSingleObject(*((HANDLE *)v4 + 430), 0xFFFFFFFF);
    if ( (*((_BYTE *)v4 + 3448) & 4) != 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
    {
      WPP_SF_qqdsddsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (_BYTE)v4 + 24,
        *((_DWORD *)v4 + 864),
        *((_QWORD *)v4 + 433),
        *((_DWORD *)v4 + 865),
        v5,
        (__int64)"WDiagQueryPktStatisticsTimeout",
        43);
    }
    *((_DWORD *)v4 + 862) |= 4u;
    v6 = *((_DWORD *)v4 + 862);
    *((_DWORD *)v4 + 864) = v5;
    *((_DWORD *)v4 + 865) = 3371;
    *((_QWORD *)v4 + 433) = "WDiagQueryPktStatisticsTimeout";
    if ( !v4 || *((_DWORD *)v4 + 4) != 1347765833 )
    {
      *((_DWORD *)v4 + 868) = 3378;
      *((_DWORD *)v4 + 862) = v6 & 0xFFFFFFFB;
LABEL_16:
      *((_QWORD *)v4 + 435) = "WDiagQueryPktStatisticsTimeout";
      *((_DWORD *)v4 + 864) = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)v4 + 84);
      v2 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_17;
    }
    if ( (*((_BYTE *)v4 + 24) & 2) == 0 )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
      {
        WPP_SF_S_guid_(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v4 + 3488);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( (*((_BYTE *)v4 + 3448) & 4) == 0
        && v8 != &WPP_GLOBAL_Control
        && *((_BYTE *)v8 + 225)
        && (*((_BYTE *)v8 + 228) & 0x40) != 0 )
      {
        v13 = GetCurrentThreadId();
        WPP_SF_qqDsdDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          (_BYTE)v4 + 24,
          v17,
          *((_QWORD *)v4 + 435),
          *((_DWORD *)v4 + 868),
          v13,
          (__int64)"WDiagQueryPktStatisticsTimeout",
          63);
      }
      *((_DWORD *)v4 + 862) &= ~4u;
      *((_DWORD *)v4 + 868) = 3391;
      goto LABEL_16;
    }
    ++*((_DWORD *)v4 + 5);
    if ( (*((_BYTE *)v4 + 3448) & 4) == 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
    {
      v14 = GetCurrentThreadId();
      WPP_SF_qqDsdDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (_BYTE)v4 + 24,
        v17,
        *((_QWORD *)v4 + 435),
        *((_DWORD *)v4 + 868),
        v14,
        (__int64)"WDiagQueryPktStatisticsTimeout",
        70);
    }
    *((_DWORD *)v4 + 862) &= ~4u;
    *((_DWORD *)v4 + 868) = 3398;
    *((_QWORD *)v4 + 435) = "WDiagQueryPktStatisticsTimeout";
    *((_DWORD *)v4 + 864) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)v4 + 84);
    v9 = dword_1802A3648;
    if ( (dword_1802A3648 & 4) == 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
    {
      v15 = GetCurrentThreadId();
      WPP_SF_qqDsdDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (char)&qword_1802A35E8,
        v17,
        qword_1802A3668,
        dword_1802A3660[0],
        v15,
        (__int64)"WDiagQueryPktStatisticsTimeout",
        71);
      v9 = dword_1802A3648;
    }
    *(_DWORD *)dword_1802A3660 = 3399;
    dword_1802A3648 = v9 & 0xFFFFFFFB;
    qword_1802A3668 = (__int64)"WDiagQueryPktStatisticsTimeout";
    *(_DWORD *)dword_1802A3650 = 0;
    LeaveCriticalSection(&stru_1802A35F0);
    if ( v3 )
      WDiagDereferenceInterface(v3, v10);
    v3 = v4;
    updated = WDiagUpdatePacketStatistics(v4);
    if ( updated
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 154, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids, updated);
    }
    v12 = GetCurrentThreadId();
    EnterCriticalSection(&stru_1802A35F0);
    WaitForSingleObject(qword_1802A3640, 0xFFFFFFFF);
    if ( (dword_1802A3648 & 4) != 0 )
    {
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 225)
        || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) == 0 )
      {
        goto LABEL_35;
      }
      WPP_SF_qqdsddsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (char)&qword_1802A35E8,
        dword_1802A3650[0],
        qword_1802A3658,
        dword_1802A3654[0],
        v12,
        (__int64)"WDiagQueryPktStatisticsTimeout",
        90);
    }
    v2 = (PVOID *)WPP_GLOBAL_Control;
LABEL_35:
    dword_1802A3648 |= 4u;
    *(_DWORD *)dword_1802A3650 = v12;
    *(_DWORD *)dword_1802A3654 = 3418;
    qword_1802A3658 = (__int64)"WDiagQueryPktStatisticsTimeout";
LABEL_17:
    v4 = *(struct _WD_INTERFACE_CONTEXT **)v4;
  }
  while ( v4 != (struct _WD_INTERFACE_CONTEXT *)&qword_1802A3670 );
  if ( v3 )
  {
    WDiagDereferenceInterface(v3, v7);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_7:
  if ( (dword_1802A3648 & 4) == 0
    && v2 != &WPP_GLOBAL_Control
    && *((_BYTE *)v2 + 225)
    && (*((_BYTE *)v2 + 228) & 0x40) != 0 )
  {
    v16 = GetCurrentThreadId();
    WPP_SF_qqDsdDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      (char)&qword_1802A35E8,
      v17,
      qword_1802A3668,
      dword_1802A3660[0],
      v16,
      (__int64)"WDiagQueryPktStatisticsTimeout",
      100);
  }
  dword_1802A3648 &= ~4u;
  *(_DWORD *)dword_1802A3660 = 3428;
  qword_1802A3668 = (__int64)"WDiagQueryPktStatisticsTimeout";
  *(_DWORD *)dword_1802A3650 = 0;
  LeaveCriticalSection(&stru_1802A35F0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 155, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
}

```

## disassembly

```asm
0x18001f0b0  push    rbx
0x18001f0b2  push    rbp
0x18001f0b3  push    rsi
0x18001f0b4  push    rdi
0x18001f0b5  push    r12
0x18001f0b7  push    r14
0x18001f0b9  push    r15
0x18001f0bb  sub     rsp, 60h
0x18001f0bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f0c6  lea     r15, WPP_GLOBAL_Control
0x18001f0cd  cmp     rcx, r15
0x18001f0d0  jz      short loc_18001F0F6
0x18001f0d2  test    dword ptr [rcx+0E4h], 200h
0x18001f0dc  jz      short loc_18001F0F6
0x18001f0de  mov     rcx, [rcx+0D8h]
0x18001f0e5  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x18001f0ec  mov     edx, 98h
0x18001f0f1  call    WPP_SF_
0x18001f0f6  call    cs:__imp_GetCurrentThreadId
0x18001f0fc  lea     rcx, stru_1802A35F0; lpCriticalSection
0x18001f103  mov     ebx, eax
0x18001f105  call    cs:__imp_EnterCriticalSection
0x18001f10b  mov     rcx, cs:qword_1802A3640; hHandle
0x18001f112  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001f115  call    cs:__imp_WaitForSingleObject
0x18001f11b  test    byte ptr cs:dword_1802A3648, 4
0x18001f122  lea     r12, aWdiagquerypkts; "WDiagQueryPktStatisticsTimeout"
0x18001f129  mov     edi, 0D22h
0x18001f12e  lea     rsi, qword_1802A35E8
0x18001f135  jnz     loc_18001F3FF
0x18001f13b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f142  or      cs:dword_1802A3648, 4
0x18001f149  lea     rax, qword_1802A3670
0x18001f150  mov     cs:dword_1802A3654, edi
0x18001f156  xor     r14d, r14d
0x18001f159  mov     rdi, cs:qword_1802A3670
0x18001f160  mov     cs:dword_1802A3650, ebx
0x18001f166  mov     cs:qword_1802A3658, r12
0x18001f16d  cmp     rdi, rax
0x18001f170  jnz     short loc_18001F1EE
0x18001f172  test    byte ptr cs:dword_1802A3648, 4
0x18001f179  mov     ebx, 0D64h
0x18001f17e  jz      loc_18001F716
0x18001f184  and     cs:dword_1802A3648, 0FFFFFFFBh
0x18001f18b  lea     rcx, stru_1802A35F0; lpCriticalSection
0x18001f192  mov     cs:dword_1802A3660, ebx
0x18001f198  mov     cs:qword_1802A3668, r12
0x18001f19f  mov     cs:dword_1802A3650, 0
0x18001f1a9  call    cs:__imp_LeaveCriticalSection
0x18001f1af  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f1b6  cmp     rcx, r15
0x18001f1b9  jz      short loc_18001F1DF
0x18001f1bb  test    dword ptr [rcx+0E4h], 200h
0x18001f1c5  jz      short loc_18001F1DF
0x18001f1c7  mov     rcx, [rcx+0D8h]
0x18001f1ce  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x18001f1d5  mov     edx, 9Bh
0x18001f1da  call    WPP_SF_
0x18001f1df  add     rsp, 60h
0x18001f1e3  pop     r15
0x18001f1e5  pop     r14
0x18001f1e7  pop     r12
0x18001f1e9  pop     rdi
0x18001f1ea  pop     rsi
0x18001f1eb  pop     rbp
0x18001f1ec  pop     rbx
0x18001f1ed  retn
0x18001f1ee  lea     rbx, [rdi+0D18h]
0x18001f1f5  call    cs:__imp_GetCurrentThreadId
0x18001f1fb  lea     rbp, [rbx+8]
0x18001f1ff  mov     esi, eax
0x18001f201  mov     rcx, rbp; lpCriticalSection
0x18001f204  call    cs:__imp_EnterCriticalSection
0x18001f20a  mov     rcx, [rbx+58h]; hHandle
0x18001f20e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001f211  call    cs:__imp_WaitForSingleObject
0x18001f217  test    byte ptr [rbx+60h], 4
0x18001f21b  jnz     loc_18001F473
0x18001f221  or      dword ptr [rbx+60h], 4
0x18001f225  mov     eax, [rbx+60h]
0x18001f228  mov     [rbx+68h], esi
0x18001f22b  mov     dword ptr [rbx+6Ch], 0D2Bh
0x18001f232  mov     [rbx+70h], r12
0x18001f236  test    rdi, rdi
0x18001f239  jz      short loc_18001F244
0x18001f23b  cmp     dword ptr [rdi+10h], 50554649h
0x18001f242  jz      short loc_18001F2A2
0x18001f244  and     eax, 0FFFFFFFBh
0x18001f247  mov     dword ptr [rbx+78h], 0D32h
0x18001f24e  mov     [rbx+60h], eax
0x18001f251  mov     [rbx+80h], r12
0x18001f258  mov     rcx, rbp; lpCriticalSection
0x18001f25b  mov     dword ptr [rbx+68h], 0
0x18001f262  call    cs:__imp_LeaveCriticalSection
0x18001f268  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f26f  mov     rdi, [rdi]
0x18001f272  lea     rax, qword_1802A3670
0x18001f279  cmp     rdi, rax
0x18001f27c  jnz     loc_18001F1EE
0x18001f282  test    r14, r14
0x18001f285  jz      short loc_18001F296
0x18001f287  mov     rcx, r14; struct _WD_INTERFACE_CONTEXT *
0x18001f28a  call    ?WDiagDereferenceInterface@@YAXPEAU_WD_INTERFACE_CONTEXT@@K@Z; WDiagDereferenceInterface(_WD_INTERFACE_CONTEXT *,ulong)
0x18001f28f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f296  lea     rsi, qword_1802A35E8
0x18001f29d  jmp     loc_18001F172
0x18001f2a2  test    byte ptr [rdi+18h], 2
0x18001f2a6  jnz     short loc_18001F312
0x18001f2a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f2af  cmp     rcx, r15
0x18001f2b2  jz      short loc_18001F2F8
0x18001f2b4  cmp     byte ptr [rcx+0E1h], 3
0x18001f2bb  jb      short loc_18001F2F8
0x18001f2bd  test    byte ptr [rcx+0E4h], 10h
0x18001f2c4  jz      short loc_18001F2F8
0x18001f2c6  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18001f2cd  lea     rax, [rdi+0DA0h]
0x18001f2d4  lea     r9, [rdi+0DC4h]
0x18001f2db  mov     qword ptr [rsp+98h+var_78], rax; __int64
0x18001f2e0  mov     edx, 99h
0x18001f2e5  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x18001f2ec  call    WPP_SF_S_guid_
0x18001f2f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f2f8  test    byte ptr [rbx+60h], 4
0x18001f2fc  jz      loc_18001F4DE
0x18001f302  and     dword ptr [rbx+60h], 0FFFFFFFBh
0x18001f306  mov     dword ptr [rbx+78h], 0D3Fh
0x18001f30d  jmp     loc_18001F251
0x18001f312  inc     dword ptr [rdi+14h]
0x18001f315  test    byte ptr [rbx+60h], 4
0x18001f319  jz      loc_18001F54B
0x18001f31f  and     dword ptr [rbx+60h], 0FFFFFFFBh
0x18001f323  mov     rcx, rbp; lpCriticalSection
0x18001f326  mov     dword ptr [rbx+78h], 0D46h
0x18001f32d  mov     [rbx+80h], r12
0x18001f334  mov     dword ptr [rbx+68h], 0
0x18001f33b  call    cs:__imp_LeaveCriticalSection
0x18001f341  mov     eax, cs:dword_1802A3648
0x18001f347  test    al, 4
0x18001f349  jz      loc_18001F5BF
0x18001f34f  lea     rsi, qword_1802A35E8
0x18001f356  and     eax, 0FFFFFFFBh
0x18001f359  mov     cs:dword_1802A3660, 0D47h
0x18001f363  lea     rcx, stru_1802A35F0; lpCriticalSection
0x18001f36a  mov     cs:dword_1802A3648, eax
0x18001f370  mov     cs:qword_1802A3668, r12
0x18001f377  mov     cs:dword_1802A3650, 0
0x18001f381  call    cs:__imp_LeaveCriticalSection
0x18001f387  test    r14, r14
0x18001f38a  jnz     loc_18001F647
0x18001f390  mov     rcx, rdi; struct _WD_INTERFACE_CONTEXT *
0x18001f393  mov     r14, rdi
0x18001f396  call    ?WDiagUpdatePacketStatistics@@YAKPEAU_WD_INTERFACE_CONTEXT@@@Z; WDiagUpdatePacketStatistics(_WD_INTERFACE_CONTEXT *)
0x18001f39b  test    eax, eax
0x18001f39d  jnz     loc_18001F654
0x18001f3a3  call    cs:__imp_GetCurrentThreadId
0x18001f3a9  lea     rcx, stru_1802A35F0; lpCriticalSection
0x18001f3b0  mov     ebx, eax
0x18001f3b2  call    cs:__imp_EnterCriticalSection
0x18001f3b8  mov     rcx, cs:qword_1802A3640; hHandle
0x18001f3bf  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001f3c2  call    cs:__imp_WaitForSingleObject
0x18001f3c8  test    byte ptr cs:dword_1802A3648, 4
0x18001f3cf  jnz     loc_18001F69E
0x18001f3d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f3dc  or      cs:dword_1802A3648, 4
0x18001f3e3  mov     cs:dword_1802A3650, ebx
0x18001f3e9  mov     cs:dword_1802A3654, 0D5Ah
0x18001f3f3  mov     cs:qword_1802A3658, r12
0x18001f3fa  jmp     loc_18001F26F
0x18001f3ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f406  cmp     rcx, r15
0x18001f409  jz      loc_18001F142
0x18001f40f  cmp     byte ptr [rcx+0E1h], 1
0x18001f416  jb      loc_18001F142
0x18001f41c  test    byte ptr [rcx+0E4h], 40h
0x18001f423  jz      loc_18001F142
0x18001f429  mov     eax, cs:dword_1802A3654
0x18001f42f  lea     r9, ?g_WDiag@@3U_WDIAG_GLOBAL_CONTEXT@@A; _WDIAG_GLOBAL_CONTEXT g_WDiag
0x18001f436  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18001f43d  mov     dword ptr [rsp+98h+var_48], edi; char
0x18001f441  mov     [rsp+98h+var_50], r12; __int64
0x18001f446  mov     dword ptr [rsp+98h+var_58], ebx; char
0x18001f44a  mov     dword ptr [rsp+98h+var_60], eax; char
0x18001f44e  mov     rax, cs:qword_1802A3658
0x18001f455  mov     [rsp+98h+var_68], rax; __int64
0x18001f45a  mov     eax, cs:dword_1802A3650
0x18001f460  mov     dword ptr [rsp+98h+var_70], eax; char
0x18001f464  mov     qword ptr [rsp+98h+var_78], rsi; char
0x18001f469  call    WPP_SF_qqdsddsd
0x18001f46e  jmp     loc_18001F13B
0x18001f473  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f47a  cmp     rcx, r15
0x18001f47d  jz      loc_18001F221
0x18001f483  cmp     byte ptr [rcx+0E1h], 1
0x18001f48a  jb      loc_18001F221
0x18001f490  test    byte ptr [rcx+0E4h], 40h
0x18001f497  jz      loc_18001F221
0x18001f49d  mov     eax, [rbx+6Ch]
0x18001f4a0  mov     r9, rdi
0x18001f4a3  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18001f4aa  mov     dword ptr [rsp+98h+var_48], 0D2Bh; char
0x18001f4b2  mov     [rsp+98h+var_50], r12; __int64
0x18001f4b7  mov     dword ptr [rsp+98h+var_58], esi; char
0x18001f4bb  mov     dword ptr [rsp+98h+var_60], eax; char
0x18001f4bf  mov     rax, [rbx+70h]
0x18001f4c3  mov     [rsp+98h+var_68], rax; __int64
0x18001f4c8  mov     eax, [rbx+68h]
0x18001f4cb  mov     dword ptr [rsp+98h+var_70], eax; char
0x18001f4cf  mov     qword ptr [rsp+98h+var_78], rbx; char
0x18001f4d4  call    WPP_SF_qqdsddsd
0x18001f4d9  jmp     loc_18001F221
0x18001f4de  cmp     rcx, r15
0x18001f4e1  jz      loc_18001F302
0x18001f4e7  cmp     byte ptr [rcx+0E1h], 1
0x18001f4ee  jb      loc_18001F302
0x18001f4f4  test    byte ptr [rcx+0E4h], 40h
0x18001f4fb  jz      loc_18001F302
0x18001f501  call    cs:__imp_GetCurrentThreadId
0x18001f507  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f50e  mov     r9, rdi
0x18001f511  mov     dword ptr [rsp+98h+var_48], 0D3Fh; char
0x18001f519  mov     [rsp+98h+var_50], r12; __int64
0x18001f51e  mov     dword ptr [rsp+98h+var_58], eax; char
0x18001f522  mov     eax, [rbx+78h]
0x18001f525  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18001f52c  mov     dword ptr [rsp+98h+var_60], eax; char
0x18001f530  mov     rax, [rbx+80h]
0x18001f537  mov     [rsp+98h+var_68], rax; __int64
0x18001f53c  mov     qword ptr [rsp+98h+var_78], rbx; char
0x18001f541  call    WPP_SF_qqDsdDsd
0x18001f546  jmp     loc_18001F302
0x18001f54b  mov     rax, cs:WPP_GLOBAL_Control
0x18001f552  cmp     rax, r15
0x18001f555  jz      loc_18001F31F
0x18001f55b  cmp     byte ptr [rax+0E1h], 1
0x18001f562  jb      loc_18001F31F
0x18001f568  test    byte ptr [rax+0E4h], 40h
0x18001f56f  jz      loc_18001F31F
0x18001f575  call    cs:__imp_GetCurrentThreadId
0x18001f57b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f582  mov     r9, rdi
0x18001f585  mov     dword ptr [rsp+98h+var_48], 0D46h; char
0x18001f58d  mov     [rsp+98h+var_50], r12; __int64
0x18001f592  mov     dword ptr [rsp+98h+var_58], eax; char
0x18001f596  mov     eax, [rbx+78h]
0x18001f599  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18001f5a0  mov     dword ptr [rsp+98h+var_60], eax; char
0x18001f5a4  mov     rax, [rbx+80h]
0x18001f5ab  mov     [rsp+98h+var_68], rax; __int64
0x18001f5b0  mov     qword ptr [rsp+98h+var_78], rbx; char
0x18001f5b5  call    WPP_SF_qqDsdDsd
0x18001f5ba  jmp     loc_18001F31F
0x18001f5bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f5c6  cmp     rcx, r15
0x18001f5c9  jz      loc_18001F34F
0x18001f5cf  cmp     byte ptr [rcx+0E1h], 1
0x18001f5d6  jb      loc_18001F34F
0x18001f5dc  test    byte ptr [rcx+0E4h], 40h
0x18001f5e3  jz      loc_18001F34F
0x18001f5e9  call    cs:__imp_GetCurrentThreadId
0x18001f5ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f5f6  lea     rsi, qword_1802A35E8
0x18001f5fd  mov     dword ptr [rsp+98h+var_48], 0D47h; char
0x18001f605  lea     r9, ?g_WDiag@@3U_WDIAG_GLOBAL_CONTEXT@@A; _WDIAG_GLOBAL_CONTEXT g_WDiag
0x18001f60c  mov     [rsp+98h+var_50], r12; __int64
0x18001f611  mov     dword ptr [rsp+98h+var_58], eax; char
0x18001f615  mov     eax, cs:dword_1802A3660
0x18001f61b  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18001f622  mov     dword ptr [rsp+98h+var_60], eax; char
0x18001f626  mov     rax, cs:qword_1802A3668
0x18001f62d  mov     [rsp+98h+var_68], rax; __int64
0x18001f632  mov     qword ptr [rsp+98h+var_78], rsi; char
0x18001f637  call    WPP_SF_qqDsdDsd
0x18001f63c  mov     eax, cs:dword_1802A3648
0x18001f642  jmp     loc_18001F356
0x18001f647  mov     rcx, r14; struct _WD_INTERFACE_CONTEXT *
0x18001f64a  call    ?WDiagDereferenceInterface@@YAXPEAU_WD_INTERFACE_CONTEXT@@K@Z; WDiagDereferenceInterface(_WD_INTERFACE_CONTEXT *,ulong)
0x18001f64f  jmp     loc_18001F390
0x18001f654  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f65b  cmp     rcx, r15
0x18001f65e  jz      loc_18001F3A3
0x18001f664  cmp     byte ptr [rcx+0E1h], 1
0x18001f66b  jb      loc_18001F3A3
0x18001f671  test    byte ptr [rcx+0E4h], 10h
0x18001f678  jz      loc_18001F3A3
0x18001f67e  mov     rcx, [rcx+0D8h]
0x18001f685  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x18001f68c  mov     edx, 9Ah
0x18001f691  mov     r9d, eax
0x18001f694  call    WPP_SF_d
0x18001f699  jmp     loc_18001F3A3
0x18001f69e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f6a5  cmp     rcx, r15
0x18001f6a8  jz      loc_18001F3DC
0x18001f6ae  cmp     byte ptr [rcx+0E1h], 1
0x18001f6b5  jb      loc_18001F3DC
0x18001f6bb  test    byte ptr [rcx+0E4h], 40h
0x18001f6c2  jz      loc_18001F3DC
0x18001f6c8  mov     eax, cs:dword_1802A3654
  ... truncated ...
```
