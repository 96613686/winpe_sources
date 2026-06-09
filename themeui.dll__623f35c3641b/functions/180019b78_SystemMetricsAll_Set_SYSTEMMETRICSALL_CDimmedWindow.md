# SystemMetricsAll_Set(SYSTEMMETRICSALL *,CDimmedWindow *)

- ea: `0x180019b78`
- end: `0x18001a16a`
- name: `?SystemMetricsAll_Set@@YAJPEAUSYSTEMMETRICSALL@@PEAVCDimmedWindow@@@Z`
- size: `1522`
- prototype: `int(struct SYSTEMMETRICSALL *, struct CDimmedWindow *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180019a28`
- `0x180033614`

## callees

- `0x1800089c0`
- `0x180019b78`
- `0x18003188c`
- `0x180032f78`
- `0x1800358c0`
- `0x18003633c`
- `0x18003c1f4`
- `0x180043d14`
- `0x180046658`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019f23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019f23`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180019e6b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a010`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180019e6b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a010`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019ee8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a102`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019ee8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a102`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019edd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001a0ac`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019edd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001a0ac`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180019f07`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180019f07`
- `GDI32!SetMagicColors` at `0x180019f6f`
- `GDI32!SetMagicColors` at `0x180019f83`
- `GDI32!SetMagicColors` at `0x180019f97`
- `GDI32!SetMagicColors` at `0x180019f6f`
- `GDI32!SetMagicColors` at `0x180019f83`
- `GDI32!SetMagicColors` at `0x180019f97`
- `USER32!ReleaseDC` at `0x180019fa2`
- `USER32!ReleaseDC` at `0x180019fa2`
- `USER32!GetDC` at `0x180019f58`
- `USER32!GetDC` at `0x180019f58`
- `USER32!PostMessageW` at `0x18001a122`
- `USER32!PostMessageW` at `0x18001a122`
- `USER32!SetSysColors` at `0x180019fd5`
- `USER32!SetSysColors` at `0x180019fd5`
- `USER32!SendNotifyMessageW` at `0x18001a13b`
- `USER32!SendNotifyMessageW` at `0x18001a13b`
- `USER32!GetThreadDpiAwarenessContext` at `0x180019d1f`
- `USER32!GetThreadDpiAwarenessContext` at `0x180019d1f`

## string_xrefs

- `0x180019d4f`: `IconWidthSpacing=%d, IconHeightSpacing=%d, ThreadDpiAwarenessContext=0x%x`

## pseudocode

```c
__int64 __fastcall SystemMetricsAll_Set(struct SYSTEMMETRICSALL *a1, struct CDimmedWindow *a2)
{
  int v2; // ebx
  int v4; // ebx
  _QWORD *v6; // rcx
  __int64 ThreadDpiAwarenessContext; // rax
  int v8; // r8d
  __int64 v9; // rcx
  __int64 v10; // r9
  __int64 v11; // rax
  unsigned int i; // ebx
  HKEY v13; // rcx
  HDC DC; // rbx
  int j; // edx
  __int64 v16; // rcx
  int v17; // eax
  __int64 k; // rbx
  int v19; // edx
  __int64 v20; // rax
  DWORD dwOptionsa[2]; // [rsp+28h] [rbp-E0h]
  DWORD dwOptions[2]; // [rsp+28h] [rbp-E0h]
  REGSAM samDesired[2]; // [rsp+30h] [rbp-D8h]
  HKEY hKey; // [rsp+58h] [rbp-B0h] BYREF
  HKEY hKey_8[2]; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v27; // [rsp+70h] [rbp-98h] BYREF
  __int64 v28; // [rsp+80h] [rbp-88h] BYREF
  COLORREF aRgbValues[32]; // [rsp+88h] [rbp-80h] BYREF
  INT aElements[32]; // [rsp+108h] [rbp+0h] BYREF
  BYTE Data[16]; // [rsp+188h] [rbp+80h] BYREF
  unsigned __int16 v32[32]; // [rsp+198h] [rbp+90h] BYREF
  unsigned __int16 v33[256]; // [rsp+1D8h] [rbp+D0h] BYREF

  v2 = *(_DWORD *)a1;
  *(_OWORD *)hKey_8 = 0;
  v28 = 0;
  v4 = v2 & 8;
  v27 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_93c683883954366ac6f837c4447f2db7_Traceguids);
  SystemParametersInfoAsync(
    0x1023u,
    0,
    (void *)*((int *)a1 + 187),
    0,
    3u,
    a2,
    (void **)((unsigned __int64)hKey_8 & -(__int64)(v4 != 0)));
  if ( (*(_BYTE *)a1 & 1) == 0 || !*((_DWORD *)a1 + 184) || !*((_DWORD *)a1 + 185) )
  {
    if ( !v4 )
      goto LABEL_28;
    goto LABEL_24;
  }
  hKey = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_93c683883954366ac6f837c4447f2db7_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
      WPP_SF_(v6[2], 12, WPP_93c683883954366ac6f837c4447f2db7_Traceguids);
  }
  *((_DWORD *)a1 + 2) = 504;
  SystemParametersInfoAsync(
    0x2Au,
    0x1F8u,
    (char *)a1 + 8,
    0x1F8u,
    3u,
    a2,
    (void **)((unsigned __int64)&hKey_8[1] & -(__int64)(v4 != 0)));
  SystemParametersInfoAsync(
    0x22u,
    0x5Cu,
    (char *)a1 + 512,
    0x5Cu,
    3u,
    a2,
    (void **)((unsigned __int64)&v27 & -(__int64)(v4 != 0)));
  ThreadDpiAwarenessContext = GetThreadDpiAwarenessContext();
  v8 = *((_DWORD *)a1 + 184);
  dwOptionsa[0] = v8 + *((_DWORD *)a1 + 183);
  StringCchPrintfW(
    v33,
    0x100u,
    L"IconWidthSpacing=%d, IconHeightSpacing=%d, ThreadDpiAwarenessContext=0x%x",
    (unsigned int)(v8 + *((_DWORD *)a1 + 182)),
    *(_QWORD *)dwOptionsa,
    ThreadDpiAwarenessContext);
  ThemesTelemetry::SystemMetrics<unsigned short const (&)[21],unsigned short (&)[256]>(v9, v33);
  *(_DWORD *)Data = 11;
  *(_DWORD *)&Data[4] = 38;
  if ( 2.34375 != IconSpacingMetrics::GetIconMetricsRatio((IconSpacingMetrics *)Data) )
    SystemParametersInfoAsync(
      0xDu,
      *((_DWORD *)a1 + 182) + *((_DWORD *)a1 + 184),
      0,
      0,
      3u,
      a2,
      (void **)(((unsigned __int64)&v27 + 8) & -(__int64)(v4 != 0)));
  *(_DWORD *)Data = 12;
  *(_DWORD *)&Data[4] = 39;
  if ( 2.34375 != IconSpacingMetrics::GetIconMetricsRatio((IconSpacingMetrics *)Data) )
    SystemParametersInfoAsync(
      0x18u,
      *((_DWORD *)a1 + 183) + *((_DWORD *)a1 + 184),
      0,
      0,
      3u,
      a2,
      (void **)((unsigned __int64)&v28 & -(__int64)(v4 != 0)));
  if ( !RegCreateKeyExW(HKEY_CURRENT_USER, L"Control Panel\\Desktop\\WindowMetrics", 0, 0, 0, 0x20006u, 0, &hKey, 0) )
  {
    v10 = *((unsigned int *)a1 + 184);
    *(_OWORD *)Data = 0;
    StringCchPrintfW((unsigned __int16 *)Data, 8u, L"%d", v10);
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)&Data[2 * v11] );
    RegSetValueExW(hKey, L"Shell Icon Size", 0, 1u, Data, 2 * v11 + 2);
    RegCloseKey(hKey);
  }
  if ( v4 )
  {
    WaitForMultipleObjects(5u, (const HANDLE *)hKey_8, 1, 0x7530u);
LABEL_24:
    for ( i = 0; i < 5; ++i )
    {
      v13 = hKey_8[i];
      if ( v13 )
        CloseHandle(v13);
    }
  }
LABEL_28:
  if ( (*(_BYTE *)a1 & 2) != 0 )
  {
    memset_0(v32, 0, sizeof(v32));
    hKey = 0;
    DC = GetDC(0);
    SetMagicColors(DC, 12639424, 8);
    SetMagicColors(DC, 15780518, 9);
    SetMagicColors(DC, 15793151, 246);
    ReleaseDC(0, DC);
    for ( j = 0; j < 31; ++j )
    {
      v16 = (unsigned int)j;
      v17 = *((_DWORD *)a1 + (unsigned int)j + 151) & 0xFFFFFF;
      aElements[j] = j;
      aRgbValues[v16] = v17;
    }
    SetSysColors(31, aElements, aRgbValues);
    if ( !RegCreateKeyExW(HKEY_CURRENT_USER, L"Control Panel\\Colors", 0, 0, 0, 0x20006u, 0, &hKey, 0) )
    {
      for ( k = 0; k != 31; ++k )
      {
        v19 = *((_DWORD *)a1 + k + 151);
        samDesired[0] = BYTE2(v19);
        dwOptions[0] = BYTE1(v19);
        StringCchPrintfW(v32, 0x20u, L"%d %d %d", (unsigned __int8)v19, *(_QWORD *)dwOptions, *(_QWORD *)samDesired);
        v20 = -1;
        do
          ++v20;
        while ( v32[v20] );
        RegSetValueExW(hKey, *((LPCWSTR *)&gc_rgSystemColorNames + 2 * k), 0, 1u, (const BYTE *)v32, 2 * v20 + 2);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            (unsigned int)WPP_93c683883954366ac6f837c4447f2db7_Traceguids,
            *((_QWORD *)&gc_rgSystemColorNames + 2 * k),
            (__int64)v32);
      }
      RegCloseKey(hKey);
    }
  }
  else
  {
    if ( (*(_BYTE *)a1 & 1) == 0 )
      return 0;
    PostMessageW(HWND_BROADCAST, 0x15u, 0, 0);
  }
  if ( (*(_BYTE *)a1 & 1) != 0 )
    SendNotifyMessageW(HWND_BROADCAST, 0x1Au, 0x2Au, 0);
  return 0;
}

```

## disassembly

```asm
0x180019b78  mov     rax, rsp
0x180019b7b  push    rbp
0x180019b7c  push    rbx
0x180019b7d  push    rsi
0x180019b7e  push    rdi
0x180019b7f  push    r13
0x180019b81  push    r14
0x180019b83  lea     rbp, [rax-328h]
0x180019b8a  sub     rsp, 3F8h
0x180019b91  movaps  xmmword ptr [rax-48h], xmm6
0x180019b95  mov     rax, cs:__security_cookie
0x180019b9c  xor     rax, rsp
0x180019b9f  mov     [rbp+320h+var_50], rax
0x180019ba6  mov     ebx, [rcx]
0x180019ba8  xorps   xmm0, xmm0
0x180019bab  xor     eax, eax
0x180019bad  mov     rsi, rdx
0x180019bb0  movups  xmmword ptr [rsp+420h+hKey+8], xmm0
0x180019bb5  mov     [rsp+420h+var_3A8], rax
0x180019bba  and     ebx, 8
0x180019bbd  movups  [rsp+420h+var_3C0+8], xmm0
0x180019bc2  mov     rdi, rcx
0x180019bc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180019bcc  lea     rax, WPP_GLOBAL_Control
0x180019bd3  cmp     rcx, rax
0x180019bd6  jz      short loc_180019BF3
0x180019bd8  test    byte ptr [rcx+1Ch], 8
0x180019bdc  jz      short loc_180019BF3
0x180019bde  mov     rcx, [rcx+10h]
0x180019be2  lea     r8, WPP_93c683883954366ac6f837c4447f2db7_Traceguids
0x180019be9  mov     edx, 0Ah
0x180019bee  call    WPP_SF_
0x180019bf3  movsxd  r8, dword ptr [rdi+2ECh]; void *
0x180019bfa  mov     eax, ebx
0x180019bfc  neg     eax
0x180019bfe  mov     r13d, 3
0x180019c04  lea     rax, [rsp+420h+hKey+8]
0x180019c09  sbb     rcx, rcx
0x180019c0c  xor     r9d, r9d; unsigned int
0x180019c0f  and     rcx, rax
0x180019c12  xor     edx, edx; unsigned int
0x180019c14  mov     [rsp+420h+lpSecurityAttributes], rcx; void **
0x180019c19  mov     ecx, 1023h; unsigned int
0x180019c1e  mov     qword ptr [rsp+420h+samDesired], rsi; struct CDimmedWindow *
0x180019c23  mov     [rsp+420h+dwOptions], r13d; unsigned int
0x180019c28  call    ?SystemParametersInfoAsync@@YAXIIPEAXKIPEAVCDimmedWindow@@PEAPEAX@Z; SystemParametersInfoAsync(uint,uint,void *,ulong,uint,CDimmedWindow *,void * *)
0x180019c2d  xor     r14d, r14d
0x180019c30  test    byte ptr [rdi], 1
0x180019c33  jz      loc_180019F0F
0x180019c39  cmp     [rdi+2E0h], r14d
0x180019c40  jz      loc_180019F0F
0x180019c46  cmp     [rdi+2E4h], r14d
0x180019c4d  jz      loc_180019F0F
0x180019c53  mov     [rsp+420h+hKey], r14
0x180019c58  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c5f  lea     rax, WPP_GLOBAL_Control
0x180019c66  cmp     rcx, rax
0x180019c69  jz      short loc_180019CB3
0x180019c6b  test    byte ptr [rcx+1Ch], 8
0x180019c6f  jz      short loc_180019C93
0x180019c71  mov     rcx, [rcx+10h]
0x180019c75  lea     edx, [r13+8]
0x180019c79  lea     r8, WPP_93c683883954366ac6f837c4447f2db7_Traceguids
0x180019c80  call    WPP_SF_
0x180019c85  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c8c  lea     rax, WPP_GLOBAL_Control
0x180019c93  cmp     rcx, rax
0x180019c96  jz      short loc_180019CB3
0x180019c98  test    byte ptr [rcx+1Ch], 8
0x180019c9c  jz      short loc_180019CB3
0x180019c9e  mov     rcx, [rcx+10h]
0x180019ca2  lea     r8, WPP_93c683883954366ac6f837c4447f2db7_Traceguids
0x180019ca9  mov     edx, 0Ch
0x180019cae  call    WPP_SF_
0x180019cb3  mov     edx, 1F8h; unsigned int
0x180019cb8  lea     r8, [rdi+8]; void *
0x180019cbc  mov     eax, ebx
0x180019cbe  mov     [r8], edx
0x180019cc1  neg     eax
0x180019cc3  mov     r9d, edx; unsigned int
0x180019cc6  lea     rax, [rsp+420h+var_3C0]
0x180019ccb  sbb     rcx, rcx
0x180019cce  and     rcx, rax
0x180019cd1  mov     [rsp+420h+lpSecurityAttributes], rcx; void **
0x180019cd6  mov     ecx, 2Ah ; '*'; unsigned int
0x180019cdb  mov     qword ptr [rsp+420h+samDesired], rsi; struct CDimmedWindow *
0x180019ce0  mov     [rsp+420h+dwOptions], r13d; unsigned int
0x180019ce5  call    ?SystemParametersInfoAsync@@YAXIIPEAXKIPEAVCDimmedWindow@@PEAPEAX@Z; SystemParametersInfoAsync(uint,uint,void *,ulong,uint,CDimmedWindow *,void * *)
0x180019cea  mov     edx, 5Ch ; '\'; unsigned int
0x180019cef  lea     r8, [rdi+200h]; void *
0x180019cf6  mov     eax, ebx
0x180019cf8  mov     r9d, edx; unsigned int
0x180019cfb  neg     eax
0x180019cfd  lea     rax, [rsp+420h+var_3C0+8]
0x180019d02  sbb     rcx, rcx
0x180019d05  and     rcx, rax
0x180019d08  mov     [rsp+420h+lpSecurityAttributes], rcx; void **
0x180019d0d  lea     ecx, [rdx-3Ah]; unsigned int
0x180019d10  mov     qword ptr [rsp+420h+samDesired], rsi; struct CDimmedWindow *
0x180019d15  mov     [rsp+420h+dwOptions], r13d; unsigned int
0x180019d1a  call    ?SystemParametersInfoAsync@@YAXIIPEAXKIPEAVCDimmedWindow@@PEAPEAX@Z; SystemParametersInfoAsync(uint,uint,void *,ulong,uint,CDimmedWindow *,void * *)
0x180019d1f  call    cs:__imp_GetThreadDpiAwarenessContext
0x180019d25  mov     r8d, [rdi+2E0h]
0x180019d2c  lea     rcx, [rbp+320h+var_250]; unsigned __int16 *
0x180019d33  mov     edx, [rdi+2DCh]
0x180019d39  mov     r9d, [rdi+2D8h]
0x180019d40  add     edx, r8d
0x180019d43  mov     qword ptr [rsp+420h+samDesired], rax
0x180019d48  add     r9d, r8d
0x180019d4b  mov     [rsp+420h+dwOptions], edx
0x180019d4f  lea     r8, aIconwidthspaci; "IconWidthSpacing=%d, IconHeightSpacing="...
0x180019d56  mov     edx, 100h; unsigned __int64
0x180019d5b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019d60  lea     rdx, [rbp+320h+var_250]
0x180019d67  call    ??$SystemMetrics@AEAY0BF@$$CBGAEAY0BAA@G@ThemesTelemetry@@SAXAEAY0BF@$$CBGAEAY0BAA@G@Z; ThemesTelemetry::SystemMetrics<ushort const (&)[21],ushort (&)[256]>(ushort const (&)[21],ushort (&)[256])
0x180019d6c  lea     rcx, [rbp+320h+Data]; this
0x180019d73  mov     dword ptr [rbp+320h+Data], 0Bh
0x180019d7d  mov     dword ptr [rbp+320h+Data+4], 26h ; '&'
0x180019d87  call    ?GetIconMetricsRatio@IconSpacingMetrics@@QEBANXZ; IconSpacingMetrics::GetIconMetricsRatio(void)
0x180019d8c  movsd   xmm6, cs:__real@4002c00000000000
0x180019d94  ucomisd xmm6, xmm0
0x180019d98  jp      short loc_180019D9C
0x180019d9a  jz      short loc_180019DD5
0x180019d9c  mov     edx, [rdi+2E0h]
0x180019da2  mov     eax, ebx
0x180019da4  neg     eax
0x180019da6  lea     rax, [rsp+420h+var_3B0]
0x180019dab  sbb     rcx, rcx
0x180019dae  add     edx, [rdi+2D8h]; unsigned int
0x180019db4  and     rcx, rax
0x180019db7  xor     r9d, r9d; unsigned int
0x180019dba  mov     [rsp+420h+lpSecurityAttributes], rcx; void **
0x180019dbf  xor     r8d, r8d; void *
0x180019dc2  mov     qword ptr [rsp+420h+samDesired], rsi; struct CDimmedWindow *
0x180019dc7  mov     [rsp+420h+dwOptions], r13d; unsigned int
0x180019dcc  lea     ecx, [r9+0Dh]; unsigned int
0x180019dd0  call    ?SystemParametersInfoAsync@@YAXIIPEAXKIPEAVCDimmedWindow@@PEAPEAX@Z; SystemParametersInfoAsync(uint,uint,void *,ulong,uint,CDimmedWindow *,void * *)
0x180019dd5  lea     rcx, [rbp+320h+Data]; this
0x180019ddc  mov     dword ptr [rbp+320h+Data], 0Ch
0x180019de6  mov     dword ptr [rbp+320h+Data+4], 27h ; '''
0x180019df0  call    ?GetIconMetricsRatio@IconSpacingMetrics@@QEBANXZ; IconSpacingMetrics::GetIconMetricsRatio(void)
0x180019df5  ucomisd xmm6, xmm0
0x180019df9  jp      short loc_180019DFD
0x180019dfb  jz      short loc_180019E36
0x180019dfd  mov     edx, [rdi+2E0h]
0x180019e03  mov     eax, ebx
0x180019e05  neg     eax
0x180019e07  lea     rax, [rsp+420h+var_3A8]
0x180019e0c  sbb     rcx, rcx
0x180019e0f  add     edx, [rdi+2DCh]; unsigned int
0x180019e15  and     rcx, rax
0x180019e18  xor     r9d, r9d; unsigned int
0x180019e1b  mov     [rsp+420h+lpSecurityAttributes], rcx; void **
0x180019e20  xor     r8d, r8d; void *
0x180019e23  mov     qword ptr [rsp+420h+samDesired], rsi; struct CDimmedWindow *
0x180019e28  mov     [rsp+420h+dwOptions], r13d; unsigned int
0x180019e2d  lea     ecx, [r9+18h]; unsigned int
0x180019e31  call    ?SystemParametersInfoAsync@@YAXIIPEAXKIPEAVCDimmedWindow@@PEAPEAX@Z; SystemParametersInfoAsync(uint,uint,void *,ulong,uint,CDimmedWindow *,void * *)
0x180019e36  mov     [rsp+40h], r14; lpdwDisposition
0x180019e3b  lea     rax, [rsp+420h+hKey]
0x180019e40  mov     [rsp+420h+phkResult], rax; phkResult
0x180019e45  lea     rdx, pszSubKey; "Control Panel\\Desktop\\WindowMetrics"
0x180019e4c  mov     [rsp+420h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180019e51  xor     r9d, r9d; lpClass
0x180019e54  mov     [rsp+420h+samDesired], 20006h; samDesired
0x180019e5c  xor     r8d, r8d; Reserved
0x180019e5f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180019e66  mov     [rsp+420h+dwOptions], r14d; dwOptions
0x180019e6b  call    cs:__imp_RegCreateKeyExW
0x180019e71  test    eax, eax
0x180019e73  jnz     short loc_180019EEE
0x180019e75  mov     r9d, [rdi+2E0h]
0x180019e7c  lea     r8, aD; "%d"
0x180019e83  xorps   xmm0, xmm0
0x180019e86  lea     edx, [rax+8]; unsigned __int64
0x180019e89  lea     rcx, [rbp+320h+Data]; unsigned __int16 *
0x180019e90  movups  xmmword ptr [rbp+320h+Data], xmm0
0x180019e97  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019e9c  lea     rcx, [rbp+320h+Data]
0x180019ea3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019ea7  inc     rax
0x180019eaa  cmp     [rcx+rax*2], r14w
0x180019eaf  jnz     short loc_180019EA7
0x180019eb1  mov     rcx, [rsp+420h+hKey]; hKey
0x180019eb6  lea     eax, ds:2[rax*2]
0x180019ebd  mov     [rsp+420h+samDesired], eax; cbData
0x180019ec1  lea     rdx, pszValue; "Shell Icon Size"
0x180019ec8  lea     rax, [rbp+320h+Data]
0x180019ecf  mov     r9d, 1; dwType
0x180019ed5  xor     r8d, r8d; Reserved
0x180019ed8  mov     qword ptr [rsp+420h+dwOptions], rax; lpData
0x180019edd  call    cs:__imp_RegSetValueExW
0x180019ee3  mov     rcx, [rsp+420h+hKey]; hKey
0x180019ee8  call    cs:__imp_RegCloseKey
0x180019eee  test    ebx, ebx
0x180019ef0  jz      short loc_180019F30
0x180019ef2  mov     r8d, 1; bWaitAll
0x180019ef8  lea     rdx, [rsp+420h+hKey+8]; lpHandles
0x180019efd  mov     r9d, 7530h; dwMilliseconds
0x180019f03  lea     ecx, [r8+4]; nCount
0x180019f07  call    cs:__imp_WaitForMultipleObjects
0x180019f0d  jmp     short loc_180019F13
0x180019f0f  test    ebx, ebx
0x180019f11  jz      short loc_180019F30
0x180019f13  mov     ebx, r14d
0x180019f16  movsxd  rax, ebx
0x180019f19  mov     rcx, [rsp+rax*8+420h+hKey+8]; hObject
0x180019f1e  test    rcx, rcx
0x180019f21  jz      short loc_180019F29
0x180019f23  call    cs:__imp_CloseHandle
0x180019f29  inc     ebx
0x180019f2b  cmp     ebx, 5
0x180019f2e  jb      short loc_180019F16
0x180019f30  test    byte ptr [rdi], 2
0x180019f33  mov     r13d, 0FFFFh
0x180019f39  jz      loc_18001A110
0x180019f3f  xor     edx, edx; Val
0x180019f41  lea     rcx, [rbp+320h+var_290]; void *
0x180019f48  lea     r8d, [rdx+40h]; Size
0x180019f4c  call    memset_0
0x180019f51  xor     ecx, ecx; hWnd
0x180019f53  mov     [rsp+420h+hKey], r14
0x180019f58  call    cs:__imp_GetDC
0x180019f5e  mov     edx, 0C0DCC0h
0x180019f63  mov     r8d, 8
0x180019f69  mov     rcx, rax
0x180019f6c  mov     rbx, rax
0x180019f6f  call    cs:__imp_SetMagicColors
0x180019f75  mov     edx, 0F0CAA6h
0x180019f7a  mov     r8d, 9
0x180019f80  mov     rcx, rbx
0x180019f83  call    cs:__imp_SetMagicColors
0x180019f89  mov     edx, 0F0FBFFh
0x180019f8e  mov     r8d, 0F6h
0x180019f94  mov     rcx, rbx
0x180019f97  call    cs:__imp_SetMagicColors
0x180019f9d  mov     rdx, rbx; hDC
0x180019fa0  xor     ecx, ecx; hWnd
0x180019fa2  call    cs:__imp_ReleaseDC
0x180019fa8  mov     edx, r14d
0x180019fab  mov     ecx, edx
0x180019fad  mov     eax, [rdi+rcx*4+25Ch]
0x180019fb4  and     eax, 0FFFFFFh
0x180019fb9  mov     [rbp+rcx*4+320h+aElements], edx
0x180019fbd  inc     edx
0x180019fbf  mov     [rbp+rcx*4+320h+aRgbValues], eax
0x180019fc3  cmp     edx, 1Fh
0x180019fc6  jl      short loc_180019FAB
0x180019fc8  lea     r8, [rbp+320h+aRgbValues]; lpaRgbValues
0x180019fcc  mov     ecx, 1Fh; cElements
0x180019fd1  lea     rdx, [rbp+320h+aElements]; lpaElements
0x180019fd5  call    cs:__imp_SetSysColors
0x180019fdb  mov     [rsp+40h], r14; lpdwDisposition
0x180019fe0  lea     rax, [rsp+420h+hKey]
0x180019fe5  mov     [rsp+420h+phkResult], rax; phkResult
0x180019fea  lea     rdx, aControlPanelCo; "Control Panel\\Colors"
0x180019ff1  mov     [rsp+420h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180019ff6  xor     r9d, r9d; lpClass
0x180019ff9  mov     [rsp+420h+samDesired], 20006h; samDesired
0x18001a001  xor     r8d, r8d; Reserved
0x18001a004  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001a00b  mov     [rsp+420h+dwOptions], r14d; dwOptions
0x18001a010  call    cs:__imp_RegCreateKeyExW
0x18001a016  test    eax, eax
0x18001a018  jnz     loc_18001A128
0x18001a01e  mov     rbx, r14
0x18001a021  lea     r13, WPP_GLOBAL_Control
0x18001a028  mov     edx, [rdi+rbx*4+25Ch]
0x18001a02f  lea     r8, aDDD; "%d %d %d"
0x18001a036  mov     eax, edx
0x18001a038  movzx   r9d, dl
0x18001a03c  shr     eax, 10h
0x18001a03f  movzx   ecx, al
0x18001a042  movzx   eax, dx
0x18001a045  mov     edx, 20h ; ' '; unsigned __int64
0x18001a04a  mov     [rsp+420h+samDesired], ecx
0x18001a04e  lea     rcx, [rbp+320h+var_290]; unsigned __int16 *
0x18001a055  shr     eax, 8
0x18001a058  mov     [rsp+420h+dwOptions], eax
0x18001a05c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a061  lea     rcx, [rbp+320h+var_290]
0x18001a068  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a06c  inc     rax
0x18001a06f  cmp     [rcx+rax*2], r14w
0x18001a074  jnz     short loc_18001A06C
0x18001a076  lea     eax, ds:2[rax*2]
0x18001a07d  mov     rsi, rbx
0x18001a080  mov     [rsp+420h+samDesired], eax; cbData
0x18001a084  lea     rcx, ?gc_rgSystemColorNames@@3QBUSYSTEM_COLOR_NAMES@@B; SYSTEM_COLOR_NAMES const near * const gc_rgSystemColorNames
0x18001a08b  add     rsi, rsi
0x18001a08e  lea     rax, [rbp+320h+var_290]
0x18001a095  mov     r9d, 1; dwType
0x18001a09b  mov     qword ptr [rsp+420h+dwOptions], rax; lpData
0x18001a0a0  xor     r8d, r8d; Reserved
0x18001a0a3  mov     rdx, [rcx+rsi*8]; lpValueName
0x18001a0a7  mov     rcx, [rsp+420h+hKey]; hKey
0x18001a0ac  call    cs:__imp_RegSetValueExW
0x18001a0b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a0b9  cmp     rcx, r13
0x18001a0bc  jz      short loc_18001A0F0
  ... truncated ...
```
