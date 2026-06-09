# CDrNotify::NotifyConnect(ulong)

- ea: `0x1800072f0`
- end: `0x180007b7c`
- name: `?NotifyConnect@CDrNotify@@QEAAJK@Z`
- size: `2188`
- prototype: `int(CDrNotify *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x18000a5cc`

## callees

- `0x1800072f0`
- `0x180007b84`
- `0x180007da0`
- `0x18000b8f8`
- `0x18000bd04`
- `0x18000f75c`
- `0x18000f79c`
- `0x180017cbc`
- `0x18001a144`
- `0x18001a3f0`
- `0x18001a5d8`
- `0x18001a6d0`
- `0x18001a73c`
- `0x18001b3b4`
- `0x180047ebe`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000738b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000744d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000755c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007765`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000738b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000744d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000755c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007765`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b5a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180007997`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180007997`
- `WINSTA!WinStationQueryInformationW` at `0x18000737f`
- `WINSTA!WinStationQueryInformationW` at `0x18000737f`
- `WINSTA!WinStationVirtualOpenEx` at `0x18000743f`
- `WINSTA!WinStationVirtualOpenEx` at `0x1800074c6`
- `WINSTA!WinStationVirtualOpenEx` at `0x180007545`
- `WINSTA!WinStationVirtualOpenEx` at `0x180007665`
- `WINSTA!WinStationVirtualOpenEx` at `0x180007757`
- `WINSTA!WinStationVirtualOpenEx` at `0x18000743f`
- `WINSTA!WinStationVirtualOpenEx` at `0x1800074c6`
- `WINSTA!WinStationVirtualOpenEx` at `0x180007545`
- `WINSTA!WinStationVirtualOpenEx` at `0x180007665`
- `WINSTA!WinStationVirtualOpenEx` at `0x180007757`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x180007411`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x180007411`
- `WTSAPI32!WTSFreeMemory` at `0x180007426`
- `WTSAPI32!WTSFreeMemory` at `0x180007426`

## pseudocode

```c
__int64 __fastcall CDrNotify::NotifyConnect(HANDLE *this, DWORD a2)
{
  signed int v2; // ebx
  int v4; // r13d
  void *v5; // r15
  void *v6; // r12
  void *v7; // rsi
  signed int LastError; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int v10; // eax
  unsigned int v11; // eax
  signed int v12; // eax
  unsigned int v13; // eax
  signed int v14; // eax
  unsigned int v15; // eax
  __int64 v16; // rax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  int v20; // eax
  signed int v21; // eax
  unsigned int v22; // eax
  signed int v23; // eax
  unsigned int v24; // eax
  __int64 v25; // rcx
  int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // r8
  unsigned int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r8
  char IsSpoolerStopped; // al
  DWORD v35; // edi
  unsigned int v36; // eax
  _QWORD *v37; // rax
  _QWORD *v38; // r9
  CDrNotify *v39; // rax
  _QWORD *v40; // rdx
  unsigned int v41; // eax
  int v43; // [rsp+48h] [rbp-C0h]
  int v44; // [rsp+4Ch] [rbp-BCh]
  int v45; // [rsp+50h] [rbp-B8h]
  unsigned int v46; // [rsp+50h] [rbp-B8h]
  int v47; // [rsp+58h] [rbp-B0h]
  DWORD BytesReturned[2]; // [rsp+68h] [rbp-A0h] BYREF
  LPWSTR ppBuffer; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v51[124]; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v52; // [rsp+F4h] [rbp-14h]
  int v53; // [rsp+F8h] [rbp-10h]
  __int64 OutBuffer; // [rsp+AE8h] [rbp+9E0h] BYREF
  DWORD InBuffer; // [rsp+AF8h] [rbp+9F0h] BYREF
  __int64 v56; // [rsp+B00h] [rbp+9F8h]
  __int64 v57; // [rsp+B08h] [rbp+A00h]
  int v58; // [rsp+B10h] [rbp+A08h]
  unsigned int v59; // [rsp+B1Ch] [rbp+A14h]
  void *v60; // [rsp+B20h] [rbp+A18h]
  void *v61; // [rsp+B28h] [rbp+A20h]
  int v62; // [rsp+B30h] [rbp+A28h]
  void *v63; // [rsp+B38h] [rbp+A30h]
  int v64; // [rsp+B40h] [rbp+A38h]

  v2 = 0;
  v4 = 0;
  v5 = 0;
  BytesReturned[0] = 0;
  v43 = 0;
  v6 = 0;
  memset_0(v51, 0, 0xA68u);
  BytesReturned[1] = 0;
  ppBuffer = 0;
  if ( !(unsigned __int8)WinStationQueryInformationW(0, a2, 1, v51, 2664, &BytesReturned[1]) )
  {
    v7 = 0;
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        10,
        WPP_77790cbdc3803b5d7a2817979d0075b6_Traceguids,
        CurrentThreadActivityIdPrefix,
        v2);
    }
    goto LABEL_91;
  }
  if ( WTSQuerySessionInformationW(0, a2, WTSConnectState, &ppBuffer, BytesReturned) )
  {
    LOBYTE(v4) = *(_DWORD *)ppBuffer == 0;
    WTSFreeMemory(ppBuffer);
    ppBuffer = 0;
  }
  v7 = (void *)WinStationVirtualOpenEx(0, a2, "RDPDR", 0);
  if ( !v7 )
  {
    v10 = GetLastError();
    v2 = v10;
    if ( v10 > 0 )
      v2 = (unsigned __int16)v10 | 0x80070000;
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        11,
        WPP_77790cbdc3803b5d7a2817979d0075b6_Traceguids,
        v11,
        v2);
    }
    v4 = 0;
    goto LABEL_91;
  }
  v47 = 0;
  v6 = (void *)WinStationVirtualOpenEx(0, a2, "AUDIO_PLAYBACK_DVC", 79);
  if ( !v6 )
  {
    v12 = GetLastError();
    v2 = v12;
    if ( v12 > 0 )
      v2 = (unsigned __int16)v12 | 0x80070000;
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 3u )
    {
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        12,
        WPP_77790cbdc3803b5d7a2817979d0075b6_Traceguids,
        v13,
        v2);
    }
    v6 = (void *)WinStationVirtualOpenEx(0, a2, "AUDIO_PLAYBACK_DVC", 15);
    if ( !v6 )
    {
      v44 = 0;
      v14 = GetLastError();
      v2 = v14;
      if ( v14 > 0 )
        v2 = (unsigned __int16)v14 | 0x80070000;
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          15,
          WPP_77790cbdc3803b5d7a2817979d0075b6_Traceguids,
          v15,
          v2);
        v45 = IsSVCOnly(a2);
        goto LABEL_55;
      }
LABEL_53:
      v20 = IsSVCOnly(a2);
      v45 = v20;
      if ( !v44 )
        goto LABEL_55;
      goto LABEL_54;
    }
    goto LABEL_36;
  }
  v16 = *(_QWORD *)&WPP_GLOBAL_Control;
  if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_41;
  if ( (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
  {
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      13,
      WPP_77790cbdc3803b5d7a2817979d0075b6_Traceguids,
      v17);
LABEL_36:
    v16 = *(_QWORD *)&WPP_GLOBAL_Control;
  }
  if ( (unsigned int *)v16 != &WPP_GLOBAL_Control && (*(_BYTE *)(v16 + 28) & 1) != 0 && *(_BYTE *)(v16 + 25) >= 4u )
  {
    v18 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      14,
      WPP_77790cbdc3803b5d7a2817979d0075b6_Traceguids,
      v18);
  }
LABEL_41:
  v44 = 1;
  v5 = (void *)WinStationVirtualOpenEx(0, a2, "AUDIO_PLAYBACK_LOSSY_DVC", 143);
  if ( v5 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
    {
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        16,
        WPP_77790cbdc3803b5d7a2817979d0075b6_Traceguids,
        v19);
    }
    v47 = 1;
    v20 = IsSVCOnly(a2);
    v45 = v20;
  }
  else
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_53;
    }
    v21 = GetLastError();
    v46 = v21;
    if ( v21 > 0 )
      v46 = (unsigned __int16)v21 | 0x80070000;
    v22 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      17,
      WPP_77790cbdc3803b5d7a2817979d0075b6_Traceguids,
      v22,
      v46);
    v20 = IsSVCOnly(a2);
    v45 = v20;
  }
LABEL_54:
  if ( !v20 )
    goto LABEL_66;
LABEL_55:
  v6 = (void *)WinStationVirtualOpenEx(0, a2, "RDPSND", 0);
  if ( !v6 )
  {
    v23 = GetLastError();
    v2 = v23;
    if ( v23 > 0 )
      v2 = (unsigned __int16)v23 | 0x80070000;
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        18,
        WPP_77790cbdc3803b5d7a2817979d0075b6_Traceguids,
        v24,
        v2);
    }
LABEL_90:
    v4 = v43;
LABEL_91:
    if ( v2 < 0 && !v4 )
      v2 = 0;
    goto LABEL_98;
  }
  v25 = *(_QWORD *)&WPP_GLOBAL_Control;
  v26 = 0;
  v44 = 0;
  v47 = 0;
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 4u )
    {
LABEL_67:
      if ( (unsigned int *)v25 != &WPP_GLOBAL_Control )
      {
        if ( (*(_BYTE *)(v25 + 28) & 1) != 0 && *(_BYTE *)(v25 + 25) >= 4u )
        {
          v28 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dddd(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), v29, v30, v28, v45, v44, v47);
          v25 = *(_QWORD *)&WPP_GLOBAL_Control;
          v26 = v44;
        }
        if ( (unsigned int *)v25 != &WPP_GLOBAL_Control && (*(_BYTE *)(v25 + 28) & 1) != 0 && *(_BYTE *)(v25 + 25) >= 4u )
        {
          v31 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dqqq(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), v32, v33, v31, v7, v6, v5);
          v26 = v44;
        }
      }
      goto LABEL_75;
    }
    v27 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      19,
      WPP_77790cbdc3803b5d7a2817979d0075b6_Traceguids,
      v27);
LABEL_66:
    v26 = v44;
    v25 = *(_QWORD *)&WPP_GLOBAL_Control;
    goto LABEL_67;
  }
LABEL_75:
  v62 = v26;
  v64 = v47;
  InBuffer = a2;
  v56 = 0;
  v57 = 0;
  v58 = 1;
  v60 = v7;
  v59 = v59 & 0xFFFFFC00 | ((v53 & 0xF) << 6) | ((v52 & 0xE0000 | (v52 >> 9) & 0x700000) >> 17);
  v61 = v6;
  v63 = v5;
  IsSpoolerStopped = CDrNotify::IsSpoolerStopped((CDrNotify *)v59);
  OutBuffer = 0;
  v59 = v59 & 0xFFFFF7FF | ((IsSpoolerStopped & 1) << 11);
  if ( DeviceIoControl(this[7], 0x38A803u, &InBuffer, 0x50u, &OutBuffer, 8u, BytesReturned, 0) )
  {
    CTSCriticalSection::Lock((CTSCriticalSection *)(this + 11));
    CDrNotify::RemoveSessionEntryFromList((CDrNotify *)this, a2);
    v37 = operator new(0x20u);
    v38 = v37;
    if ( v37 )
    {
      *((_DWORD *)v37 + 4) = a2;
      v37[3] = OutBuffer;
      v39 = (CDrNotify *)this;
      v40 = this[10];
      *v38 = this + 9;
      v38[1] = v40;
      v43 = 1;
      *v40 = v38;
      ++*((_DWORD *)this + 16);
      this[10] = v38;
      if ( this != (HANDLE *)-88LL && *((_DWORD *)this + 24) )
      {
        PAL_System_CritSecLeave(this[11]);
        v39 = (CDrNotify *)this;
      }
      if ( v4 )
      {
        if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
          && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
        {
          v41 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_D(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
            23,
            WPP_77790cbdc3803b5d7a2817979d0075b6_Traceguids,
            v41);
          v39 = (CDrNotify *)this;
        }
        v2 = CDrNotify::NotifyLogon(v39, a2);
      }
      goto LABEL_90;
    }
    v2 = -2147024882;
    if ( this != (HANDLE *)-88LL && *((_DWORD *)this + 24) )
      PAL_System_CritSecLeave(this[11]);
  }
  else
  {
    v2 = -805306367;
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v35 = GetLastError();
      v36 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DDd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        22,
        WPP_77790cbdc3803b5d7a2817979d0075b6_Traceguids,
        v36,
        -805306367,
        v35);
    }
  }
LABEL_98:
  if ( v6 )
    CloseHandle(v6);
  if ( v5 )
    CloseHandle(v5);
  if ( v7 )
    CloseHandle(v7);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800072f0  mov     r11, rsp
0x1800072f3  push    rbp
0x1800072f4  push    rbx
0x1800072f5  push    rsi
0x1800072f6  lea     rbp, [r11-0A88h]
0x1800072fd  sub     rsp, 0B70h
0x180007304  mov     rax, cs:__security_cookie
0x18000730b  xor     rax, rsp
0x18000730e  mov     [rbp+0A80h+var_40], rax
0x180007315  mov     [r11+18h], rdi
0x180007319  xor     ebx, ebx
0x18000731b  mov     [r11-20h], r12
0x18000731f  mov     edi, edx
0x180007321  mov     [r11-28h], r13
0x180007325  xor     edx, edx; Val
0x180007327  mov     [r11-30h], r14
0x18000732b  mov     r8d, 0A68h; Size
0x180007331  mov     [rsp+0B80h+var_B28], rcx
0x180007336  mov     r13d, ebx
0x180007339  mov     [r11-38h], r15
0x18000733d  lea     rcx, [rsp+0B80h+var_B10]; void *
0x180007342  mov     r15d, ebx
0x180007345  mov     [rsp+0B80h+BytesReturned], ebx
0x180007349  mov     [rsp+0B80h+var_B40], ebx
0x18000734d  mov     r12d, ebx
0x180007350  call    memset_0
0x180007355  lea     rax, [rsp+0B80h+BytesReturned+4]
0x18000735a  mov     [rsp+0B80h+BytesReturned+4], ebx
0x18000735e  mov     qword ptr [rsp+0B80h+nOutBufferSize], rax
0x180007363  lea     r9, [rsp+0B80h+var_B10]
0x180007368  mov     r8d, 1
0x18000736e  mov     dword ptr [rsp+0B80h+pBytesReturned], 0A68h
0x180007376  mov     edx, edi
0x180007378  mov     [rsp+0B80h+ppBuffer], rbx
0x18000737d  xor     ecx, ecx
0x18000737f  call    cs:__imp_WinStationQueryInformationW
0x180007385  test    al, al
0x180007387  jnz     short loc_1800073F8
0x180007389  mov     esi, ebx
0x18000738b  call    cs:__imp_GetLastError
0x180007391  mov     ebx, eax
0x180007393  test    eax, eax
0x180007395  jle     short loc_1800073A0
0x180007397  movzx   ebx, ax
0x18000739a  or      ebx, 80070000h
0x1800073a0  mov     rax, cs:WPP_GLOBAL_Control
0x1800073a7  lea     r14, WPP_GLOBAL_Control
0x1800073ae  cmp     rax, r14
0x1800073b1  jz      loc_180007AE3
0x1800073b7  test    byte ptr [rax+1Ch], 1
0x1800073bb  jz      loc_180007AE3
0x1800073c1  cmp     byte ptr [rax+19h], 2
0x1800073c5  jb      loc_180007AE3
0x1800073cb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800073d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800073d7  lea     r8, WPP_77790cbdc3803b5d7a2817979d0075b6_Traceguids
0x1800073de  mov     edx, 0Ah
0x1800073e3  mov     dword ptr [rsp+0B80h+pBytesReturned], ebx
0x1800073e7  mov     r9d, eax
0x1800073ea  mov     rcx, [rcx+10h]
0x1800073ee  call    WPP_SF_Dd
0x1800073f3  jmp     loc_180007AE3
0x1800073f8  lea     rax, [rsp+0B80h+BytesReturned]
0x1800073fd  mov     r8d, 8; WTSInfoClass
0x180007403  lea     r9, [rsp+0B80h+ppBuffer]; ppBuffer
0x180007408  mov     [rsp+0B80h+pBytesReturned], rax; pBytesReturned
0x18000740d  mov     edx, edi; SessionId
0x18000740f  xor     ecx, ecx; hServer
0x180007411  call    cs:__imp_WTSQuerySessionInformationW
0x180007417  test    eax, eax
0x180007419  jz      short loc_180007431
0x18000741b  mov     rcx, [rsp+0B80h+ppBuffer]; pMemory
0x180007420  cmp     [rcx], ebx
0x180007422  setz    r13b
0x180007426  call    cs:__imp_WTSFreeMemory
0x18000742c  mov     [rsp+0B80h+ppBuffer], rbx
0x180007431  xor     r9d, r9d
0x180007434  lea     r8, aRdpdr; "RDPDR"
0x18000743b  mov     edx, edi
0x18000743d  xor     ecx, ecx
0x18000743f  call    cs:__imp_WinStationVirtualOpenEx
0x180007445  mov     rsi, rax
0x180007448  test    rax, rax
0x18000744b  jnz     short loc_1800074B1
0x18000744d  call    cs:__imp_GetLastError
0x180007453  mov     ebx, eax
0x180007455  test    eax, eax
0x180007457  jle     short loc_180007462
0x180007459  movzx   ebx, ax
0x18000745c  or      ebx, 80070000h
0x180007462  mov     rax, cs:WPP_GLOBAL_Control
0x180007469  lea     r14, WPP_GLOBAL_Control
0x180007470  cmp     rax, r14
0x180007473  jz      short loc_1800074A9
0x180007475  test    byte ptr [rax+1Ch], 1
0x180007479  jz      short loc_1800074A9
0x18000747b  cmp     byte ptr [rax+19h], 2
0x18000747f  jb      short loc_1800074A9
0x180007481  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180007486  mov     rcx, cs:WPP_GLOBAL_Control
0x18000748d  lea     r8, WPP_77790cbdc3803b5d7a2817979d0075b6_Traceguids
0x180007494  mov     edx, 0Bh
0x180007499  mov     dword ptr [rsp+0B80h+pBytesReturned], ebx
0x18000749d  mov     r9d, eax
0x1800074a0  mov     rcx, [rcx+10h]
0x1800074a4  call    WPP_SF_Dd
0x1800074a9  mov     r13d, r12d
0x1800074ac  jmp     loc_180007AE3
0x1800074b1  mov     r9d, 4Fh ; 'O'
0x1800074b7  mov     dword ptr [rsp+0B80h+var_B30], ebx
0x1800074bb  lea     r8, aAudioPlaybackD; "AUDIO_PLAYBACK_DVC"
0x1800074c2  mov     edx, edi
0x1800074c4  xor     ecx, ecx
0x1800074c6  call    cs:__imp_WinStationVirtualOpenEx
0x1800074cc  mov     r12, rax
0x1800074cf  test    rax, rax
0x1800074d2  jnz     loc_1800075CD
0x1800074d8  call    cs:__imp_GetLastError
0x1800074de  mov     ebx, eax
0x1800074e0  test    eax, eax
0x1800074e2  jle     short loc_1800074ED
0x1800074e4  movzx   ebx, ax
0x1800074e7  or      ebx, 80070000h
0x1800074ed  mov     rax, cs:WPP_GLOBAL_Control
0x1800074f4  lea     r14, WPP_GLOBAL_Control
0x1800074fb  cmp     rax, r14
0x1800074fe  jz      short loc_180007534
0x180007500  test    byte ptr [rax+1Ch], 1
0x180007504  jz      short loc_180007534
0x180007506  cmp     byte ptr [rax+19h], 3
0x18000750a  jb      short loc_180007534
0x18000750c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180007511  mov     rcx, cs:WPP_GLOBAL_Control
0x180007518  lea     r8, WPP_77790cbdc3803b5d7a2817979d0075b6_Traceguids
0x18000751f  mov     edx, 0Ch
0x180007524  mov     dword ptr [rsp+0B80h+pBytesReturned], ebx
0x180007528  mov     r9d, eax
0x18000752b  mov     rcx, [rcx+10h]
0x18000752f  call    WPP_SF_Dd
0x180007534  mov     r9d, 0Fh
0x18000753a  lea     r8, aAudioPlaybackD; "AUDIO_PLAYBACK_DVC"
0x180007541  mov     edx, edi
0x180007543  xor     ecx, ecx
0x180007545  call    cs:__imp_WinStationVirtualOpenEx
0x18000754b  mov     r12, rax
0x18000754e  test    rax, rax
0x180007551  jnz     loc_180007610
0x180007557  mov     [rsp+44h], r15d
0x18000755c  call    cs:__imp_GetLastError
0x180007562  mov     ebx, eax
0x180007564  test    eax, eax
0x180007566  jle     short loc_180007571
0x180007568  movzx   ebx, ax
0x18000756b  or      ebx, 80070000h
0x180007571  mov     rax, cs:WPP_GLOBAL_Control
0x180007578  cmp     rax, r14
0x18000757b  jz      loc_18000772F
0x180007581  test    byte ptr [rax+1Ch], 1
0x180007585  jz      loc_18000772F
0x18000758b  cmp     byte ptr [rax+19h], 2
0x18000758f  jb      loc_18000772F
0x180007595  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000759a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800075a1  lea     r8, WPP_77790cbdc3803b5d7a2817979d0075b6_Traceguids
0x1800075a8  mov     edx, 0Fh
0x1800075ad  mov     dword ptr [rsp+0B80h+pBytesReturned], ebx
0x1800075b1  mov     r9d, eax
0x1800075b4  mov     rcx, [rcx+10h]
0x1800075b8  call    WPP_SF_Dd
0x1800075bd  mov     ecx, edi; unsigned int
0x1800075bf  call    ?IsSVCOnly@@YAHK@Z; IsSVCOnly(ulong)
0x1800075c4  mov     dword ptr [rsp+0B80h+var_B38], eax
0x1800075c8  jmp     loc_180007749
0x1800075cd  mov     rax, cs:WPP_GLOBAL_Control
0x1800075d4  lea     r14, WPP_GLOBAL_Control
0x1800075db  cmp     rax, r14
0x1800075de  jz      short loc_18000764C
0x1800075e0  test    byte ptr [rax+1Ch], 1
0x1800075e4  jz      short loc_180007617
0x1800075e6  cmp     byte ptr [rax+19h], 4
0x1800075ea  jb      short loc_180007617
0x1800075ec  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800075f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800075f8  lea     r8, WPP_77790cbdc3803b5d7a2817979d0075b6_Traceguids
0x1800075ff  mov     edx, 0Dh
0x180007604  mov     r9d, eax
0x180007607  mov     rcx, [rcx+10h]
0x18000760b  call    WPP_SF_D
0x180007610  mov     rax, cs:WPP_GLOBAL_Control
0x180007617  cmp     rax, r14
0x18000761a  jz      short loc_18000764C
0x18000761c  test    byte ptr [rax+1Ch], 1
0x180007620  jz      short loc_18000764C
0x180007622  cmp     byte ptr [rax+19h], 4
0x180007626  jb      short loc_18000764C
0x180007628  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000762d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007634  lea     r8, WPP_77790cbdc3803b5d7a2817979d0075b6_Traceguids
0x18000763b  mov     edx, 0Eh
0x180007640  mov     r9d, eax
0x180007643  mov     rcx, [rcx+10h]
0x180007647  call    WPP_SF_D
0x18000764c  mov     r9d, 8Fh
0x180007652  mov     dword ptr [rsp+44h], 1
0x18000765a  lea     r8, aAudioPlaybackL; "AUDIO_PLAYBACK_LOSSY_DVC"
0x180007661  mov     edx, edi
0x180007663  xor     ecx, ecx
0x180007665  call    cs:__imp_WinStationVirtualOpenEx
0x18000766b  mov     r15, rax
0x18000766e  test    rax, rax
0x180007671  jz      short loc_1800076C4
0x180007673  mov     rax, cs:WPP_GLOBAL_Control
0x18000767a  cmp     rax, r14
0x18000767d  jz      short loc_1800076AF
0x18000767f  test    byte ptr [rax+1Ch], 1
0x180007683  jz      short loc_1800076AF
0x180007685  cmp     byte ptr [rax+19h], 4
0x180007689  jb      short loc_1800076AF
0x18000768b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180007690  mov     rcx, cs:WPP_GLOBAL_Control
0x180007697  lea     r8, WPP_77790cbdc3803b5d7a2817979d0075b6_Traceguids
0x18000769e  mov     edx, 10h
0x1800076a3  mov     r9d, eax
0x1800076a6  mov     rcx, [rcx+10h]
0x1800076aa  call    WPP_SF_D
0x1800076af  mov     ecx, edi; unsigned int
0x1800076b1  mov     dword ptr [rsp+0B80h+var_B30], 1
0x1800076b9  call    ?IsSVCOnly@@YAHK@Z; IsSVCOnly(ulong)
0x1800076be  mov     dword ptr [rsp+0B80h+var_B38], eax
0x1800076c2  jmp     short loc_180007741
0x1800076c4  mov     rax, cs:WPP_GLOBAL_Control
0x1800076cb  cmp     rax, r14
0x1800076ce  jz      short loc_18000772F
0x1800076d0  test    byte ptr [rax+1Ch], 1
0x1800076d4  jz      short loc_18000772F
0x1800076d6  cmp     byte ptr [rax+19h], 2
0x1800076da  jb      short loc_18000772F
0x1800076dc  call    cs:__imp_GetLastError
0x1800076e2  mov     dword ptr [rsp+0B80h+var_B38], eax
0x1800076e6  test    eax, eax
0x1800076e8  jle     short loc_1800076F6
0x1800076ea  movzx   eax, ax
0x1800076ed  or      eax, 80070000h
0x1800076f2  mov     dword ptr [rsp+0B80h+var_B38], eax
0x1800076f6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800076fb  mov     ecx, dword ptr [rsp+0B80h+var_B38]
0x1800076ff  lea     r8, WPP_77790cbdc3803b5d7a2817979d0075b6_Traceguids
0x180007706  mov     dword ptr [rsp+0B80h+pBytesReturned], ecx
0x18000770a  mov     edx, 11h
0x18000770f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007716  mov     r9d, eax
0x180007719  mov     rcx, [rcx+10h]
0x18000771d  call    WPP_SF_Dd
0x180007722  mov     ecx, edi; unsigned int
0x180007724  call    ?IsSVCOnly@@YAHK@Z; IsSVCOnly(ulong)
0x180007729  mov     dword ptr [rsp+0B80h+var_B38], eax
0x18000772d  jmp     short loc_180007741
0x18000772f  mov     ecx, edi; unsigned int
0x180007731  call    ?IsSVCOnly@@YAHK@Z; IsSVCOnly(ulong)
0x180007736  cmp     dword ptr [rsp+44h], 0
0x18000773b  mov     dword ptr [rsp+0B80h+var_B38], eax
0x18000773f  jz      short loc_180007749
0x180007741  test    eax, eax
0x180007743  jz      loc_180007815
0x180007749  xor     r9d, r9d
0x18000774c  lea     r8, aRdpsnd; "RDPSND"
0x180007753  mov     edx, edi
0x180007755  xor     ecx, ecx
0x180007757  call    cs:__imp_WinStationVirtualOpenEx
0x18000775d  mov     r12, rax
0x180007760  test    rax, rax
0x180007763  jnz     short loc_1800077CB
0x180007765  call    cs:__imp_GetLastError
0x18000776b  mov     ebx, eax
0x18000776d  test    eax, eax
0x18000776f  jle     short loc_18000777A
0x180007771  movzx   ebx, ax
0x180007774  or      ebx, 80070000h
0x18000777a  mov     rax, cs:WPP_GLOBAL_Control
0x180007781  cmp     rax, r14
0x180007784  jz      loc_180007ADE
0x18000778a  test    byte ptr [rax+1Ch], 1
0x18000778e  jz      loc_180007ADE
0x180007794  cmp     byte ptr [rax+19h], 2
0x180007798  jb      loc_180007ADE
0x18000779e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800077a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077aa  lea     r8, WPP_77790cbdc3803b5d7a2817979d0075b6_Traceguids
0x1800077b1  mov     edx, 12h
0x1800077b6  mov     dword ptr [rsp+0B80h+pBytesReturned], ebx
0x1800077ba  mov     r9d, eax
0x1800077bd  mov     rcx, [rcx+10h]
0x1800077c1  call    WPP_SF_Dd
0x1800077c6  jmp     loc_180007ADE
0x1800077cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077d2  xor     eax, eax
0x1800077d4  mov     [rsp+44h], eax
0x1800077d8  mov     dword ptr [rsp+0B80h+var_B30], eax
0x1800077dc  cmp     rcx, r14
0x1800077df  jz      loc_1800078AC
  ... truncated ...
```
