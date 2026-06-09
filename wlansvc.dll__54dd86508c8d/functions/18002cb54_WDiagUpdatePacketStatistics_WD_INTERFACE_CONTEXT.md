# WDiagUpdatePacketStatistics(_WD_INTERFACE_CONTEXT *)

- ea: `0x18002cb54`
- end: `0x18002d184`
- name: `?WDiagUpdatePacketStatistics@@YAKPEAU_WD_INTERFACE_CONTEXT@@@Z`
- size: `1584`
- prototype: `unsigned int __fastcall(struct _WD_INTERFACE_CONTEXT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18001f0b0`

## callees

- `0x18000a704`
- `0x180011530`
- `0x18001e950`
- `0x18002c96c`
- `0x18002cb54`
- `0x18002d18c`
- `0x180106340`
- `0x180107330`
- `0x1801c81ac`
- `0x1801c82e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cdf2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ce27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cdf2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ce27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cc1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cc8c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cc1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cc8c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002cc28`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002cc99`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002cc28`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002cc99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002cc0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002cc7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d0c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d13e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002cc0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002cc7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d0c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d13e`

## string_xrefs

- `0x18002cc32`: `WDiagUpdatePacketStatistics`
- `0x18002ccb8`: `WDiagUpdatePacketStatistics`
- `0x18002cfdb`: `WDiagUpdatePacketStatistics`

## pseudocode

```c
__int64 __fastcall WDiagUpdatePacketStatistics(struct _WD_INTERFACE_CONTEXT *a1)
{
  __int64 v2; // rdx
  DWORD CurrentThreadId; // edi
  struct _PM_PROFILE *v4; // r8
  struct _DOT11_SSID *v5; // r9
  struct _WD_CONNECTION_CONTEXT *MatchingConnection; // rax
  struct _WD_CONNECTION_CONTEXT *v7; // rsi
  char *v8; // rdi
  DWORD v9; // r15d
  unsigned int v10; // r8d
  __int64 v11; // rax
  PVOID *v12; // rax
  unsigned int v13; // ebx
  PVOID *v14; // rcx
  char v16; // al
  char v17; // al
  enum _DOT11_BSS_TYPE v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+28h] [rbp-D8h]
  _OWORD v20[10]; // [rsp+60h] [rbp-A0h] BYREF

  LODWORD(v20[0]) = 0;
  memset_0((char *)v20 + 4, 0, 0x9Cu);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 146, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
  v18 = 0;
  WDiagQueryDot11DataEx(a1, v2, v20, 0);
  if ( *((_QWORD *)&v20[0] + 1) )
  {
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
        (__int64)"WDiagUpdatePacketStatistics",
        208);
    }
    *((_DWORD *)a1 + 862) |= 4u;
    *((_DWORD *)a1 + 864) = CurrentThreadId;
    *((_DWORD *)a1 + 865) = 3280;
    *((_QWORD *)a1 + 433) = "WDiagUpdatePacketStatistics";
    MatchingConnection = FindMatchingConnection(a1, 0, v4, v5, v18, 0x40u, 1u);
    v7 = MatchingConnection;
    if ( !MatchingConnection )
    {
      WDiagReleaseExLock(a1, (struct _WD_INTERFACE_CONTEXT *)((char *)a1 + 3352), "WDiagUpdatePacketStatistics", 0xCDFu);
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 225)
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 148, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
      v13 = 1168;
      goto LABEL_17;
    }
    v8 = (char *)MatchingConnection + 3920;
    v9 = GetCurrentThreadId();
    EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
    WaitForSingleObject(*((HANDLE *)v8 + 11), 0xFFFFFFFF);
    if ( (v8[96] & 4) != 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
    {
      WPP_SF_qqdsddsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (char)v8,
        *((_DWORD *)v8 + 26),
        *((_QWORD *)v8 + 14),
        *((_DWORD *)v8 + 27),
        v9,
        (__int64)"WDiagUpdatePacketStatistics",
        231);
    }
    *((_DWORD *)v8 + 24) |= 4u;
    *((_DWORD *)v8 + 26) = v9;
    *((_QWORD *)v8 + 14) = "WDiagUpdatePacketStatistics";
    *((_DWORD *)v8 + 27) = 3303;
    if ( *((char *)v7 + 1196) < 0 )
    {
      WDiagReleaseExLock(v7, (struct _WDIAG_RW_LOCK *)v8, "WDiagUpdatePacketStatistics", 0xCEDu);
      WDiagReleaseExLock(a1, (struct _WD_INTERFACE_CONTEXT *)((char *)a1 + 3352), "WDiagUpdatePacketStatistics", 0xCEEu);
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 225)
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
      {
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 149, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
      v13 = 1229;
      goto LABEL_17;
    }
    v10 = *((_DWORD *)v7 + 712);
    *((_DWORD *)v7 + 712) = v10 + 1;
    v11 = 160LL * (v10 % 3);
    *(_OWORD *)((char *)v7 + v11 + 2856) = v20[0];
    *(_OWORD *)((char *)v7 + v11 + 2872) = v20[1];
    *(_OWORD *)((char *)v7 + v11 + 2888) = v20[2];
    *(_OWORD *)((char *)v7 + v11 + 2904) = v20[3];
    *(_OWORD *)((char *)v7 + v11 + 2920) = v20[4];
    *(_OWORD *)((char *)v7 + v11 + 2936) = v20[5];
    *(_OWORD *)((char *)v7 + v11 + 2952) = v20[6];
    *(_OWORD *)((char *)v7 + v11 + 2968) = v20[7];
    *(_OWORD *)((char *)v7 + v11 + 2984) = v20[8];
    *(_OWORD *)((char *)v7 + v11 + 3000) = v20[9];
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 120, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (v8[96] & 4) == 0 && v12 != &WPP_GLOBAL_Control && *((_BYTE *)v12 + 225) && (*((_BYTE *)v12 + 228) & 0x40) != 0 )
    {
      v16 = GetCurrentThreadId();
      WPP_SF_qqDsdDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (char)v8,
        v19,
        *((_QWORD *)v8 + 16),
        *((_DWORD *)v8 + 30),
        v16,
        (__int64)"WDiagUpdatePacketStatistics",
        3);
    }
    *((_DWORD *)v8 + 24) &= ~4u;
    *((_DWORD *)v8 + 30) = 3331;
    *((_QWORD *)v8 + 16) = "WDiagUpdatePacketStatistics";
    *((_DWORD *)v8 + 26) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
    if ( (*((_BYTE *)a1 + 3448) & 4) == 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
    {
      v17 = GetCurrentThreadId();
      WPP_SF_qqDsdDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (_BYTE)a1 + 24,
        v19,
        *((_QWORD *)a1 + 435),
        *((_DWORD *)a1 + 868),
        v17,
        (__int64)"WDiagUpdatePacketStatistics",
        4);
    }
    *((_DWORD *)a1 + 862) &= ~4u;
    *((_DWORD *)a1 + 868) = 3332;
    *((_QWORD *)a1 + 435) = "WDiagUpdatePacketStatistics";
    *((_DWORD *)a1 + 864) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)a1 + 84);
    v13 = 0;
    goto LABEL_16;
  }
  v13 = 0;
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v13;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 225) && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 147, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
LABEL_16:
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_17:
  if ( v14 != &WPP_GLOBAL_Control && (*((_DWORD *)v14 + 57) & 0x200) != 0 )
    WPP_SF_(v14[27], 151, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
  return v13;
}

```

## disassembly

```asm
0x18002cb54  push    rbp
0x18002cb56  push    rbx
0x18002cb57  push    rsi
0x18002cb58  push    rdi
0x18002cb59  push    r12
0x18002cb5b  push    r13
0x18002cb5d  push    r14
0x18002cb5f  push    r15
0x18002cb61  lea     rbp, [rsp-18h]
0x18002cb66  sub     rsp, 118h
0x18002cb6d  mov     rax, cs:__security_cookie
0x18002cb74  xor     rax, rsp
0x18002cb77  mov     [rbp+50h+var_50], rax
0x18002cb7b  mov     r14, rcx
0x18002cb7e  xor     r15d, r15d
0x18002cb81  lea     rcx, [rsp+150h+var_F0+4]; void *
0x18002cb86  mov     dword ptr [rsp+150h+var_F0], r15d
0x18002cb8b  xor     edx, edx; Val
0x18002cb8d  mov     r8d, 9Ch; Size
0x18002cb93  call    memset_0
0x18002cb98  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cb9f  lea     rax, WPP_GLOBAL_Control
0x18002cba6  cmp     rcx, rax
0x18002cba9  jz      short loc_18002CBCF
0x18002cbab  test    dword ptr [rcx+0E4h], 200h
0x18002cbb5  jz      short loc_18002CBCF
0x18002cbb7  mov     rcx, [rcx+0D8h]
0x18002cbbe  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x18002cbc5  mov     edx, 92h
0x18002cbca  call    WPP_SF_
0x18002cbcf  mov     [rsp+150h+var_108], r15
0x18002cbd4  lea     r8, [rsp+150h+var_F0]
0x18002cbd9  mov     qword ptr [rsp+150h+var_110], r15
0x18002cbde  xor     r9d, r9d
0x18002cbe1  mov     qword ptr [rsp+150h+var_118], r15
0x18002cbe6  mov     rcx, r14
0x18002cbe9  mov     qword ptr [rsp+150h+var_120], r15
0x18002cbee  mov     qword ptr [rsp+150h+var_128], r15
0x18002cbf3  mov     qword ptr [rsp+150h+var_130], r15; enum _DOT11_BSS_TYPE
0x18002cbf8  call    ?WDiagQueryDot11DataEx@@YAKPEAU_WD_INTERFACE_CONTEXT@@W4WDIAG_STATISTICS_QUERY_REASON@@PEAUWDIAG_PACKET_STATISTICS@@PEAU_DOT11_SSID@@PEAY05EPEAUWDIAG_SIGNAL_QUALITY@@PEAK666@Z; WDiagQueryDot11DataEx(_WD_INTERFACE_CONTEXT *,WDIAG_STATISTICS_QUERY_REASON,WDIAG_PACKET_STATISTICS *,_DOT11_SSID *,uchar (*)[6],WDIAG_SIGNAL_QUALITY *,ulong *,ulong *,ulong *,ulong *)
0x18002cbfd  cmp     qword ptr [rsp+150h+var_F0+8], r15
0x18002cc02  jz      loc_18002CE81
0x18002cc08  lea     rbx, [r14+0D18h]
0x18002cc0f  call    cs:__imp_GetCurrentThreadId
0x18002cc15  lea     rcx, [rbx+8]; lpCriticalSection
0x18002cc19  mov     edi, eax
0x18002cc1b  call    cs:__imp_EnterCriticalSection
0x18002cc21  mov     rcx, [rbx+58h]; hHandle
0x18002cc25  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002cc28  call    cs:__imp_WaitForSingleObject
0x18002cc2e  test    byte ptr [rbx+60h], 4
0x18002cc32  lea     r12, aWdiagupdatepac; "WDiagUpdatePacketStatistics"
0x18002cc39  mov     esi, 0CD0h
0x18002cc3e  jnz     loc_18002CEF7
0x18002cc44  or      dword ptr [rbx+60h], 4
0x18002cc48  xor     edx, edx; void *
0x18002cc4a  mov     [rsp+150h+var_120], 1; unsigned int
0x18002cc52  mov     rcx, r14; struct _WD_INTERFACE_CONTEXT *
0x18002cc55  mov     dword ptr [rsp+150h+var_128], 40h ; '@'; int
0x18002cc5d  mov     [rbx+68h], edi
0x18002cc60  mov     [rbx+6Ch], esi
0x18002cc63  mov     [rbx+70h], r12
0x18002cc67  call    ?FindMatchingConnection@@YAPEAU_WD_CONNECTION_CONTEXT@@PEAU_WD_INTERFACE_CONTEXT@@PEAXPEAU_PM_PROFILE@@PEAU_DOT11_SSID@@W4_DOT11_BSS_TYPE@@KK@Z; FindMatchingConnection(_WD_INTERFACE_CONTEXT *,void *,_PM_PROFILE *,_DOT11_SSID *,_DOT11_BSS_TYPE,ulong,ulong)
0x18002cc6c  mov     rsi, rax
0x18002cc6f  test    rax, rax
0x18002cc72  jz      loc_18002CEC6
0x18002cc78  lea     rdi, [rax+0F50h]
0x18002cc7f  call    cs:__imp_GetCurrentThreadId
0x18002cc85  lea     rcx, [rdi+8]; lpCriticalSection
0x18002cc89  mov     r15d, eax
0x18002cc8c  call    cs:__imp_EnterCriticalSection
0x18002cc92  mov     rcx, [rdi+58h]; hHandle
0x18002cc96  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002cc99  call    cs:__imp_WaitForSingleObject
0x18002cc9f  test    byte ptr [rdi+60h], 4
0x18002cca3  jnz     loc_18002CFA3
0x18002cca9  lea     r10, WPP_GLOBAL_Control
0x18002ccb0  or      dword ptr [rdi+60h], 4
0x18002ccb4  mov     [rdi+68h], r15d
0x18002ccb8  lea     r15, aWdiagupdatepac; "WDiagUpdatePacketStatistics"
0x18002ccbf  mov     [rdi+70h], r15
0x18002ccc3  mov     dword ptr [rdi+6Ch], 0CE7h
0x18002ccca  test    byte ptr [rsi+4ACh], 80h
0x18002ccd1  jnz     loc_18002D01D
0x18002ccd7  mov     r8d, [rsi+0B20h]
0x18002ccde  mov     eax, 0AAAAAAABh
0x18002cce3  mul     r8d
0x18002cce6  mov     ecx, r8d
0x18002cce9  shr     edx, 1
0x18002cceb  lea     eax, [rdx+rdx*2]
0x18002ccee  sub     ecx, eax
0x18002ccf0  lea     eax, [r8+1]
0x18002ccf4  mov     [rsi+0B20h], eax
0x18002ccfa  movups  xmm0, [rsp+150h+var_F0]
0x18002ccff  mov     r9d, ecx
0x18002cd02  lea     rax, [rcx+rcx*4]
0x18002cd06  shl     rax, 5
0x18002cd0a  movups  xmmword ptr [rax+rsi+0B28h], xmm0
0x18002cd12  movups  xmm1, [rsp+150h+var_E0]
0x18002cd17  movups  xmmword ptr [rax+rsi+0B38h], xmm1
0x18002cd1f  movups  xmm0, [rbp+50h+var_D0]
0x18002cd23  movups  xmmword ptr [rax+rsi+0B48h], xmm0
0x18002cd2b  movups  xmm1, [rbp+50h+var_C0]
0x18002cd2f  movups  xmmword ptr [rax+rsi+0B58h], xmm1
0x18002cd37  movups  xmm0, [rbp+50h+var_B0]
0x18002cd3b  movups  xmmword ptr [rax+rsi+0B68h], xmm0
0x18002cd43  movups  xmm1, [rbp+50h+var_A0]
0x18002cd47  movups  xmmword ptr [rax+rsi+0B78h], xmm1
0x18002cd4f  movups  xmm0, [rbp+50h+var_90]
0x18002cd53  movups  xmmword ptr [rax+rsi+0B88h], xmm0
0x18002cd5b  movups  xmm1, [rbp+50h+var_80]
0x18002cd5f  movups  xmmword ptr [rax+rsi+0B98h], xmm1
0x18002cd67  movups  xmm0, [rbp+50h+var_70]
0x18002cd6b  movups  xmmword ptr [rax+rsi+0BA8h], xmm0
0x18002cd73  movups  xmm1, [rbp+50h+var_60]
0x18002cd77  movups  xmmword ptr [rax+rsi+0BB8h], xmm1
0x18002cd7f  mov     rax, cs:WPP_GLOBAL_Control
0x18002cd86  cmp     rax, r10
0x18002cd89  jz      short loc_18002CDCB
0x18002cd8b  cmp     byte ptr [rax+0E1h], 3
0x18002cd92  jb      short loc_18002CDCB
0x18002cd94  test    byte ptr [rax+0E4h], 10h
0x18002cd9b  jz      short loc_18002CDCB
0x18002cd9d  mov     rcx, [rax+0D8h]
0x18002cda4  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x18002cdab  mov     [rsp+150h+var_130], r9d
0x18002cdb0  mov     edx, 78h ; 'x'
0x18002cdb5  mov     r9, rsi
0x18002cdb8  call    WPP_SF_qD
0x18002cdbd  mov     rax, cs:WPP_GLOBAL_Control
0x18002cdc4  lea     r10, WPP_GLOBAL_Control
0x18002cdcb  test    byte ptr [rdi+60h], 4
0x18002cdcf  jz      loc_18002D0A0
0x18002cdd5  and     dword ptr [rdi+60h], 0FFFFFFFBh
0x18002cdd9  lea     rcx, [rdi+8]; lpCriticalSection
0x18002cddd  mov     dword ptr [rdi+78h], 0D03h
0x18002cde4  mov     [rdi+80h], r15
0x18002cdeb  mov     dword ptr [rdi+68h], 0
0x18002cdf2  call    cs:__imp_LeaveCriticalSection
0x18002cdf8  test    byte ptr [rbx+60h], 4
0x18002cdfc  mov     esi, 0D04h
0x18002ce01  jz      loc_18002D10D
0x18002ce07  lea     rdi, WPP_GLOBAL_Control
0x18002ce0e  and     dword ptr [rbx+60h], 0FFFFFFFBh
0x18002ce12  lea     rcx, [rbx+8]; lpCriticalSection
0x18002ce16  mov     [rbx+78h], esi
0x18002ce19  mov     [rbx+80h], r15
0x18002ce20  mov     dword ptr [rbx+68h], 0
0x18002ce27  call    cs:__imp_LeaveCriticalSection
0x18002ce2d  xor     ebx, ebx
0x18002ce2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ce36  cmp     rcx, rdi
0x18002ce39  jz      short loc_18002CE5F
0x18002ce3b  test    dword ptr [rcx+0E4h], 200h
0x18002ce45  jz      short loc_18002CE5F
0x18002ce47  mov     rcx, [rcx+0D8h]
0x18002ce4e  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x18002ce55  mov     edx, 97h
0x18002ce5a  call    WPP_SF_
0x18002ce5f  mov     eax, ebx
0x18002ce61  mov     rcx, [rbp+50h+var_50]
0x18002ce65  xor     rcx, rsp; StackCookie
0x18002ce68  call    __security_check_cookie
0x18002ce6d  add     rsp, 118h
0x18002ce74  pop     r15
0x18002ce76  pop     r14
0x18002ce78  pop     r13
0x18002ce7a  pop     r12
0x18002ce7c  pop     rdi
0x18002ce7d  pop     rsi
0x18002ce7e  pop     rbx
0x18002ce7f  pop     rbp
0x18002ce80  retn
0x18002ce81  mov     ebx, r15d
0x18002ce84  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ce8b  lea     rdi, WPP_GLOBAL_Control
0x18002ce92  cmp     rcx, rdi
0x18002ce95  jz      short loc_18002CE5F
0x18002ce97  cmp     byte ptr [rcx+0E1h], 1
0x18002ce9e  jb      short loc_18002CE36
0x18002cea0  test    byte ptr [rcx+0E4h], 10h
0x18002cea7  jz      short loc_18002CE36
0x18002cea9  mov     rcx, [rcx+0D8h]
0x18002ceb0  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x18002ceb7  mov     edx, 93h
0x18002cebc  call    WPP_SF_
0x18002cec1  jmp     loc_18002CE2F
0x18002cec6  mov     r9d, 0CDFh; unsigned int
0x18002cecc  mov     r8, r12; char *
0x18002cecf  mov     rdx, rbx; struct _WDIAG_RW_LOCK *
0x18002ced2  mov     rcx, r14; void *
0x18002ced5  call    ?WDiagReleaseExLock@@YAXPEAXPEAU_WDIAG_RW_LOCK@@PEADK@Z; WDiagReleaseExLock(void *,_WDIAG_RW_LOCK *,char *,ulong)
0x18002ceda  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cee1  lea     rdi, WPP_GLOBAL_Control
0x18002cee8  cmp     rcx, rdi
0x18002ceeb  jnz     short loc_18002CF65
0x18002ceed  mov     ebx, 490h
0x18002cef2  jmp     loc_18002CE36
0x18002cef7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cefe  lea     rax, WPP_GLOBAL_Control
0x18002cf05  cmp     rcx, rax
0x18002cf08  jz      loc_18002CC44
0x18002cf0e  cmp     byte ptr [rcx+0E1h], 1
0x18002cf15  jb      loc_18002CC44
0x18002cf1b  test    byte ptr [rcx+0E4h], 40h
0x18002cf22  jz      loc_18002CC44
0x18002cf28  mov     eax, [rbx+6Ch]
0x18002cf2b  mov     r9, r14
0x18002cf2e  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18002cf35  mov     dword ptr [rsp+150h+var_100], esi; char
0x18002cf39  mov     [rsp+150h+var_108], r12; __int64
0x18002cf3e  mov     dword ptr [rsp+150h+var_110], edi; char
0x18002cf42  mov     dword ptr [rsp+150h+var_118], eax; char
0x18002cf46  mov     rax, [rbx+70h]
0x18002cf4a  mov     qword ptr [rsp+150h+var_120], rax; __int64
0x18002cf4f  mov     eax, [rbx+68h]
0x18002cf52  mov     dword ptr [rsp+150h+var_128], eax; char
0x18002cf56  mov     qword ptr [rsp+150h+var_130], rbx; char
0x18002cf5b  call    WPP_SF_qqdsddsd
0x18002cf60  jmp     loc_18002CC44
0x18002cf65  cmp     byte ptr [rcx+0E1h], 1
0x18002cf6c  jb      loc_18002CEED
0x18002cf72  test    byte ptr [rcx+0E4h], 10h
0x18002cf79  jz      loc_18002CEED
0x18002cf7f  mov     rcx, [rcx+0D8h]
0x18002cf86  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x18002cf8d  mov     edx, 94h
0x18002cf92  call    WPP_SF_
0x18002cf97  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cf9e  jmp     loc_18002CEED
0x18002cfa3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cfaa  lea     r10, WPP_GLOBAL_Control
0x18002cfb1  cmp     rcx, r10
0x18002cfb4  jz      loc_18002CCB0
0x18002cfba  cmp     byte ptr [rcx+0E1h], 1
0x18002cfc1  jb      loc_18002CCB0
0x18002cfc7  test    byte ptr [rcx+0E4h], 40h
0x18002cfce  jz      loc_18002CCB0
0x18002cfd4  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18002cfdb  lea     rax, aWdiagupdatepac; "WDiagUpdatePacketStatistics"
0x18002cfe2  mov     dword ptr [rsp+150h+var_100], 0CE7h; char
0x18002cfea  mov     r9, rsi
0x18002cfed  mov     [rsp+150h+var_108], rax; __int64
0x18002cff2  mov     eax, [rdi+6Ch]
0x18002cff5  mov     dword ptr [rsp+150h+var_110], r15d; char
0x18002cffa  mov     dword ptr [rsp+150h+var_118], eax; char
0x18002cffe  mov     rax, [rdi+70h]
0x18002d002  mov     qword ptr [rsp+150h+var_120], rax; __int64
0x18002d007  mov     eax, [rdi+68h]
0x18002d00a  mov     dword ptr [rsp+150h+var_128], eax; char
0x18002d00e  mov     qword ptr [rsp+150h+var_130], rdi; char
0x18002d013  call    WPP_SF_qqdsddsd
0x18002d018  jmp     loc_18002CCA9
0x18002d01d  mov     r9d, 0CEDh; unsigned int
0x18002d023  mov     r8, r15; char *
0x18002d026  mov     rdx, rdi; struct _WDIAG_RW_LOCK *
0x18002d029  mov     rcx, rsi; void *
0x18002d02c  call    ?WDiagReleaseExLock@@YAXPEAXPEAU_WDIAG_RW_LOCK@@PEADK@Z; WDiagReleaseExLock(void *,_WDIAG_RW_LOCK *,char *,ulong)
0x18002d031  mov     r9d, 0CEEh; unsigned int
0x18002d037  mov     r8, r15; char *
0x18002d03a  mov     rdx, rbx; struct _WDIAG_RW_LOCK *
0x18002d03d  mov     rcx, r14; void *
0x18002d040  call    ?WDiagReleaseExLock@@YAXPEAXPEAU_WDIAG_RW_LOCK@@PEADK@Z; WDiagReleaseExLock(void *,_WDIAG_RW_LOCK *,char *,ulong)
0x18002d045  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d04c  lea     rdi, WPP_GLOBAL_Control
0x18002d053  cmp     rcx, rdi
0x18002d056  jz      short loc_18002D096
0x18002d058  cmp     byte ptr [rcx+0E1h], 1
0x18002d05f  jb      short loc_18002D096
0x18002d061  test    byte ptr [rcx+0E4h], 10h
0x18002d068  jz      short loc_18002D096
0x18002d06a  mov     eax, [rsi+4ACh]
0x18002d070  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x18002d077  mov     rcx, [rcx+0D8h]
0x18002d07e  mov     edx, 95h
0x18002d083  mov     r9, rsi
0x18002d086  mov     [rsp+150h+var_130], eax
0x18002d08a  call    WPP_SF_qD
0x18002d08f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d096  mov     ebx, 4CDh
0x18002d09b  jmp     loc_18002CE36
0x18002d0a0  cmp     rax, r10
0x18002d0a3  jz      loc_18002CDD5
0x18002d0a9  cmp     byte ptr [rax+0E1h], 1
0x18002d0b0  jb      loc_18002CDD5
0x18002d0b6  test    byte ptr [rax+0E4h], 40h
0x18002d0bd  jz      loc_18002CDD5
0x18002d0c3  call    cs:__imp_GetCurrentThreadId
0x18002d0c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d0d0  mov     r9, rsi
0x18002d0d3  mov     dword ptr [rsp+150h+var_100], 0D03h; char
0x18002d0db  mov     [rsp+150h+var_108], r15; __int64
0x18002d0e0  mov     dword ptr [rsp+150h+var_110], eax; char
0x18002d0e4  mov     eax, [rdi+78h]
0x18002d0e7  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18002d0ee  mov     dword ptr [rsp+150h+var_118], eax; char
0x18002d0f2  mov     rax, [rdi+80h]
0x18002d0f9  mov     qword ptr [rsp+150h+var_120], rax; __int64
0x18002d0fe  mov     qword ptr [rsp+150h+var_130], rdi; char
0x18002d103  call    WPP_SF_qqDsdDsd
  ... truncated ...
```
