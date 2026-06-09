# WinHttpCloseHandle

- ea: `0x1800065a0`
- end: `0x180007142`
- name: `WinHttpCloseHandle`
- size: `2978`
- prototype: `BOOL __stdcall(HINTERNET hInternet)`
- caller_count: `31`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005f58`
- `0x180006210`
- `0x18000ec00`
- `0x180011000`
- `0x1800112b8`
- `0x180011b98`
- `0x180013e44`
- `0x1800237b4`
- `0x180046ee0`
- `0x18004763c`
- `0x18005e5b8`
- `0x18005fb00`
- `0x18005feac`
- `0x1800604c0`
- `0x180062570`
- `0x18007b4d4`
- `0x180082328`
- `0x180093a18`
- `0x18009d5dc`
- `0x18009d99c`
- `0x18009efe0`
- `0x18009fee0`
- `0x18009ff30`
- `0x1800a0354`
- `0x1800a5860`
- `0x1800b0c98`
- `0x1800b1860`
- `0x1800bc674`
- `0x1800bcc00`
- `0x1800bce80`
- `0x1800bdb10`

## callees

- `0x1800065a0`
- `0x180007148`
- `0x180010f50`
- `0x180028bd0`
- `0x180033404`
- `0x18003b0e0`
- `0x18003bc60`
- `0x1800a1d10`
- `0x1800db6b0`
- `0x1800db704`
- `0x1800db758`
- `0x1800dd2e4`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006ab1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007076`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006ab1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007076`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800069de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800069de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000697b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000697b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006aa9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000706e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006aa9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000706e`
- `ntdll!EtwEventActivityIdControl` at `0x180006727`
- `ntdll!EtwEventActivityIdControl` at `0x18000675f`
- `ntdll!EtwEventActivityIdControl` at `0x1800069c2`
- `ntdll!EtwEventActivityIdControl` at `0x180006ae7`
- `ntdll!EtwEventActivityIdControl` at `0x180006b97`
- `ntdll!EtwEventActivityIdControl` at `0x180006727`
- `ntdll!EtwEventActivityIdControl` at `0x18000675f`
- `ntdll!EtwEventActivityIdControl` at `0x1800069c2`
- `ntdll!EtwEventActivityIdControl` at `0x180006ae7`
- `ntdll!EtwEventActivityIdControl` at `0x180006b97`

## pseudocode

```c
BOOL __stdcall WinHttpCloseHandle(HINTERNET hInternet)
{
  unsigned int v2; // r14d
  char *v3; // rbx
  unsigned int v4; // edi
  signed __int32 v5; // eax
  struct _GUID *v6; // rbx
  struct _GUID *v7; // rax
  __int64 v8; // rcx
  struct _GUID *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rcx
  struct _GUID *v12; // rax
  int v13; // eax
  bool v14; // sf
  int v15; // eax
  bool v16; // sf
  __int64 v17; // rbx
  unsigned int IsValid; // esi
  __int64 v19; // r8
  __int64 v20; // r9
  BOOL v21; // edi
  void *v22; // rbx
  DWORD LastError; // edi
  signed __int32 v24; // eax
  char v25; // al
  __int64 v26; // rbx
  __int64 v27; // r8
  unsigned int v28; // r14d
  __int64 v29; // r9
  BOOL v30; // esi
  unsigned __int64 v31; // rcx
  const struct _GUID *v32; // r9
  int v33; // eax
  bool v34; // sf
  __int64 v36; // rcx
  struct _GUID *v37; // rax
  struct _GUID *v38; // rax
  __int64 v39; // rcx
  signed __int32 v40; // esi
  DWORD v41; // ebx
  unsigned __int64 v42; // rcx
  const struct _GUID *v43; // r9
  int v44; // eax
  bool v45; // sf
  int v46; // edx
  int v47; // edx
  int v48; // eax
  bool v49; // sf
  signed __int32 v50; // esi
  DWORD TickCount; // ebx
  DWORD CurrentProcessId; // eax
  __int64 v53; // [rsp+20h] [rbp-69h]
  void *v54; // [rsp+30h] [rbp-59h] BYREF
  char *v55; // [rsp+38h] [rbp-51h] BYREF
  struct _GUID v56; // [rsp+40h] [rbp-49h] BYREF
  int v57; // [rsp+50h] [rbp-39h]
  struct _GUID v58; // [rsp+60h] [rbp-29h] BYREF
  struct _GUID v59; // [rsp+70h] [rbp-19h] BYREF
  struct _GUID v60; // [rsp+80h] [rbp-9h] BYREF
  _UNKNOWN *retaddr; // [rsp+E8h] [rbp+5Fh]

  v54 = 0;
  v2 = 0;
  v57 = 0;
  v56 = 0;
  v55 = 0;
  if ( !WinHttpEtwInitialized )
    goto LABEL_52;
  if ( hInternet )
  {
    if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
      WPP_SF_qqD(
        1041,
        10,
        (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids,
        (_DWORD)hInternet,
        (__int64)&v55);
    if ( (unsigned int)HANDLE_OBJECT::IsValid(hInternet, 1684826455) )
    {
      if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
      {
        v46 = 11;
        goto LABEL_133;
      }
    }
    else
    {
      v3 = (char *)hInternet;
      if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
        WPP_SF_q(1032, 19, WPP_989094c1a00a31c88345b82a0793d746_Traceguids);
      if ( *((_DWORD *)hInternet + 12) )
      {
        if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
          WPP_SF_qq(
            1032,
            20,
            (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids,
            *((_QWORD *)hInternet + 4),
            (__int64)hInternet);
        v4 = 6;
      }
      else
      {
        v4 = 0;
      }
      while ( 1 )
      {
        v5 = *((_DWORD *)hInternet + 11);
        if ( v5 <= 0 )
          break;
        if ( v5 == _InterlockedCompareExchange((volatile signed __int32 *)hInternet + 11, v5 + 1, v5) )
          goto LABEL_12;
      }
      v4 = 5;
LABEL_12:
      if ( (BYTE2(xmmword_180107A60) & 0x20) != 0 )
        WPP_SF_qqD(
          1045,
          21,
          (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids,
          *((_QWORD *)hInternet + 4),
          (__int64)hInternet);
      if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
        WPP_SF_d(1032, 22, WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v4, v53);
      if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
        WPP_SF_d(529, 12, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, v4, v53);
      if ( v4 == 6 || !v4 )
        goto LABEL_19;
      if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
      {
        v46 = 13;
LABEL_133:
        WPP_SF_qq(
          529,
          v46,
          (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids,
          (_DWORD)hInternet,
          (__int64)hInternet);
      }
    }
    v3 = 0;
    v4 = 6;
LABEL_19:
    v55 = v3;
    if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
    {
      WPP_SF_d(1041, 14, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, v4, v53);
      v3 = v55;
    }
    if ( v3 )
    {
      if ( v57 )
      {
        *(_DWORD *)&v58.Data2 = 0;
        v48 = EtwEventActivityIdControl(2, &v56);
        v49 = v48 < 0;
        if ( v48 > 0 )
          v49 = 1;
        if ( v49 )
          *(_DWORD *)&v58.Data2 = 144;
        v3 = v55;
      }
      v6 = (struct _GUID *)(v3 + 184);
      v7 = &v56;
      v8 = 16;
      do
      {
        LOBYTE(v7->Data1) = 0;
        v7 = (struct _GUID *)((char *)v7 + 1);
        --v8;
      }
      while ( v8 );
      v57 = 0;
      v9 = &v56;
      v59 = 0;
      v10 = 16;
      v60 = 0;
      do
      {
        LOBYTE(v9->Data1) = 0;
        v9 = (struct _GUID *)((char *)v9 + 1);
        --v10;
      }
      while ( v10 );
      v58 = 0;
      v11 = 16;
      v12 = &v60;
      do
      {
        LOBYTE(v12->Data1) = 0;
        v12 = (struct _GUID *)((char *)v12 + 1);
        --v11;
      }
      while ( v11 );
      v13 = EtwEventActivityIdControl(1, &v58);
      v14 = v13 < 0;
      if ( v13 > 0 )
        v14 = 1;
      if ( v14 )
        *(_DWORD *)&v58.Data2 = 128;
      else
        v60 = v58;
      if ( !v6 )
      {
        v50 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
        TickCount = GetTickCount();
        CurrentProcessId = GetCurrentProcessId();
        *(_DWORD *)v59.Data4 = TickCount;
        v6 = &v59;
        *(_DWORD *)&v59.Data4[4] = CurrentProcessId;
        v59.Data1 = (unsigned int)retaddr;
        *(_DWORD *)&v59.Data2 = v50;
      }
      *(_DWORD *)&v58.Data2 = 0;
      v15 = EtwEventActivityIdControl(2, v6);
      v16 = v15 < 0;
      if ( v15 > 0 )
        v16 = 1;
      if ( v16 )
        *(_DWORD *)&v58.Data2 = 144;
      v17 = (__int64)v55;
      v56 = v60;
      v57 = 1;
      if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
        WPP_SF_q(1041, 15, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids);
      IsValid = HANDLE_OBJECT::IsValid(v17, 1684826455);
      if ( !IsValid )
      {
        if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
          WPP_SF_q(1032, 23, WPP_989094c1a00a31c88345b82a0793d746_Traceguids);
        v20 = *(_QWORD *)(v17 + 32);
        v21 = _InterlockedDecrement((volatile signed __int32 *)(v17 + 44)) == 0;
        if ( (BYTE2(xmmword_180107A60) & 0x20) != 0 )
          WPP_SF_qqD(1045, 24, (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v20, v17);
        if ( v21 )
          (**(void (__fastcall ***)(__int64, __int64, __int64, __int64))v17)(v17, 1, v19, v20);
        if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
          WPP_SF_d(1032, 25, WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v21, v53);
      }
      if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
        WPP_SF_d(1041, 16, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, IsValid, v53);
    }
    goto LABEL_52;
  }
  v36 = 16;
  v37 = &v56;
  do
  {
    LOBYTE(v37->Data1) = 0;
    v37 = (struct _GUID *)((char *)v37 + 1);
    --v36;
  }
  while ( v36 );
  v57 = 0;
  v38 = &v56;
  v59 = 0;
  v39 = 16;
  v60 = 0;
  do
  {
    LOBYTE(v38->Data1) = 0;
    v38 = (struct _GUID *)((char *)v38 + 1);
    --v39;
  }
  while ( v39 );
  WxEtwGetActivityId(&v60);
  v40 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
  v41 = GetTickCount();
  *(_DWORD *)&v59.Data4[4] = GetCurrentProcessId();
  v59.Data1 = (unsigned int)retaddr;
  *(_DWORD *)&v59.Data2 = v40;
  *(_DWORD *)v59.Data4 = v41;
  if ( g_fEtwCorrelationProviderInitialized && Microsoft_Windows_Networking_CorrelationEnabled )
    EtwEx_tidActivityInfo(v42, &ActivityStart, &v59, v43, v53);
  *(_DWORD *)&v58.Data2 = 0;
  v44 = EtwEventActivityIdControl(2, &v59);
  v45 = v44 < 0;
  if ( v44 > 0 )
    v45 = 1;
  if ( v45 )
    *(_DWORD *)&v58.Data2 = 144;
  v57 = 1;
  v56 = v60;
LABEL_52:
  if ( (xmmword_180107A60 & 4) != 0 )
    WPP_SF_q(1026, 10, WPP_7824605398d33d290c3775842414c2fd_Traceguids);
  if ( !GlobalDataInitialized )
  {
    LastError = 5023;
    goto LABEL_137;
  }
  if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
    WPP_SF_qqD(
      1041,
      10,
      (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids,
      (_DWORD)hInternet,
      (__int64)&v54);
  if ( !hInternet || (unsigned int)HANDLE_OBJECT::IsValid(hInternet, 1684826455) )
  {
    if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
    {
      v47 = 11;
      goto LABEL_135;
    }
LABEL_108:
    v22 = 0;
    LastError = 6;
    goto LABEL_72;
  }
  v22 = hInternet;
  if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
    WPP_SF_q(1032, 19, WPP_989094c1a00a31c88345b82a0793d746_Traceguids);
  if ( *((_DWORD *)hInternet + 12) )
  {
    if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
      WPP_SF_qq(
        1032,
        20,
        (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids,
        *((_QWORD *)hInternet + 4),
        (__int64)hInternet);
    LastError = 6;
  }
  else
  {
    LastError = 0;
  }
  while ( 1 )
  {
    v24 = *((_DWORD *)hInternet + 11);
    if ( v24 <= 0 )
      break;
    if ( v24 == _InterlockedCompareExchange((volatile signed __int32 *)hInternet + 11, v24 + 1, v24) )
      goto LABEL_65;
  }
  LastError = 5;
LABEL_65:
  if ( (BYTE2(xmmword_180107A60) & 0x20) != 0 )
    WPP_SF_qqD(
      1045,
      21,
      (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids,
      *((_QWORD *)hInternet + 4),
      (__int64)hInternet);
  if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
    WPP_SF_d(1032, 22, WPP_989094c1a00a31c88345b82a0793d746_Traceguids, LastError, v53);
  v25 = BYTE2(xmmword_180107A50);
  if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
  {
    WPP_SF_d(529, 12, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, LastError, v53);
    v25 = BYTE2(xmmword_180107A50);
  }
  if ( LastError != 6 && LastError )
  {
    if ( (v25 & 2) != 0 )
    {
      v47 = 13;
LABEL_135:
      WPP_SF_qq(
        529,
        v47,
        (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids,
        (_DWORD)hInternet,
        (__int64)hInternet);
      goto LABEL_108;
    }
    goto LABEL_108;
  }
LABEL_72:
  v54 = v22;
  if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
  {
    WPP_SF_d(1041, 14, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, LastError, v53);
    v22 = v54;
  }
  if ( !LastError )
  {
    if ( (xmmword_180107A60 & 0x40) != 0 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v22 + 8LL))(v22);
      WPP_SF_qqD(
        1030,
        12,
        (unsigned int)WPP_7824605398d33d290c3775842414c2fd_Traceguids,
        (_DWORD)hInternet,
        (__int64)v54);
    }
    if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)v22 + 8LL))(v22) == 1952804425 )
      _InterlockedDecrement(&g_cSessionCount);
    v26 = (__int64)v54;
    if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
      WPP_SF_q(1041, 15, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids);
    v28 = HANDLE_OBJECT::IsValid(v26, 1684826455);
    if ( !v28 )
    {
      if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
        WPP_SF_q(1032, 23, WPP_989094c1a00a31c88345b82a0793d746_Traceguids);
      v29 = *(_QWORD *)(v26 + 32);
      v30 = _InterlockedDecrement((volatile signed __int32 *)(v26 + 44)) == 0;
      if ( (BYTE2(xmmword_180107A60) & 0x20) != 0 )
        WPP_SF_qqD(1045, 24, (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v29, v26);
      if ( v30 )
        (**(void (__fastcall ***)(__int64, __int64, __int64, __int64))v26)(v26, 1, v27, v29);
      if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
        WPP_SF_d(1032, 25, WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v30, v53);
    }
    if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
      WPP_SF_d(1041, 16, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, v28, v53);
    v54 = 0;
    v2 = _InternetCloseHandle(hInternet);
    if ( v2 || (LastError = GetLastError()) == 0 )
    {
      if ( (xmmword_180107A60 & 4) != 0 )
        WPP_SF_d(1026, 15, WPP_7824605398d33d290c3775842414c2fd_Traceguids, v2, v53);
      if ( v57 )
      {
        if ( g_fEtwCorrelationProviderInitialized && Microsoft_Windows_Networking_CorrelationEnabled )
          EtwEx_tidActivityInfo(v31, &ActivityStop, 0, v32, v53);
        HIDWORD(v55) = 0;
        v33 = EtwEventActivityIdControl(2, &v56);
        v34 = v33 < 0;
        if ( v33 > 0 )
          v34 = 1;
        if ( v34 )
          HIDWORD(v55) = 144;
      }
      goto LABEL_104;
    }
    goto LABEL_137;
  }
  if ( v22 )
  {
    DereferenceObject(v22);
    v54 = 0;
LABEL_137:
    if ( (xmmword_180107A50 & 4) != 0 )
      WPP_SF_d(514, 13, WPP_7824605398d33d290c3775842414c2fd_Traceguids, LastError, v53);
    goto LABEL_141;
  }
  if ( (xmmword_180107A50 & 4) != 0 )
  {
    WPP_SF_q(514, 11, WPP_7824605398d33d290c3775842414c2fd_Traceguids);
    goto LABEL_137;
  }
LABEL_141:
  if ( (xmmword_180107A60 & 4) != 0 )
    WPP_SF_d(1026, 14, WPP_7824605398d33d290c3775842414c2fd_Traceguids, v2, v53);
  if ( v57 )
    WxEtwEndActivity(0, &v56);
LABEL_104:
  SetLastError(LastError);
  return v2;
}

```

## disassembly

```asm
0x1800065a0  push    rbp
0x1800065a2  push    rbx
0x1800065a3  push    rsi
0x1800065a4  push    rdi
0x1800065a5  push    r12
0x1800065a7  push    r13
0x1800065a9  push    r14
0x1800065ab  push    r15
0x1800065ad  lea     rbp, [rsp-1Fh]
0x1800065b2  sub     rsp, 0A8h
0x1800065b9  mov     rax, cs:__security_cookie
0x1800065c0  xor     rax, rsp
0x1800065c3  mov     [rbp+57h+var_50], rax
0x1800065c7  xor     r13d, r13d
0x1800065ca  xor     eax, eax
0x1800065cc  cmp     cs:?WinHttpEtwInitialized@@3EA, al; uchar WinHttpEtwInitialized
0x1800065d2  xorps   xmm0, xmm0
0x1800065d5  mov     r15, rcx
0x1800065d8  mov     [rbp+57h+var_B0], r13
0x1800065dc  mov     r14d, r13d
0x1800065df  mov     [rbp+57h+var_90], eax
0x1800065e2  movups  xmmword ptr [rbp+57h+var_A0.Data1], xmm0
0x1800065e6  mov     [rbp+57h+var_A8], r13
0x1800065ea  mov     r12d, 0FFFFFFFFh
0x1800065f0  jz      loc_180006800
0x1800065f6  test    rcx, rcx
0x1800065f9  jz      loc_180006A3B
0x1800065ff  test    byte ptr cs:xmmword_180107A60+2, 2
0x180006606  jnz     loc_180006D0E
0x18000660c  mov     edx, 646C6957h
0x180006611  mov     rcx, r15
0x180006614  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x180006619  test    eax, eax
0x18000661b  jnz     loc_180006A07
0x180006621  mov     rbx, r15
0x180006624  test    byte ptr cs:xmmword_180107A60+1, 1
0x18000662b  jnz     loc_180006BBA
0x180006631  mov     eax, [r15+30h]
0x180006635  test    eax, eax
0x180006637  jnz     loc_180006E68
0x18000663d  mov     edi, r13d
0x180006640  mov     eax, [r15+2Ch]
0x180006644  test    eax, eax
0x180006646  jle     loc_180006F36
0x18000664c  lea     ecx, [rax+1]
0x18000664f  lock cmpxchg [r15+2Ch], ecx
0x180006655  jnz     short loc_180006640
0x180006657  test    byte ptr cs:xmmword_180107A60+2, 20h
0x18000665e  jnz     loc_180006EAE
0x180006664  test    byte ptr cs:xmmword_180107A60+1, 1
0x18000666b  jnz     loc_180006BF8
0x180006671  test    byte ptr cs:xmmword_180107A50+2, 2
0x180006678  jnz     loc_180006DAA
0x18000667e  cmp     edi, 6
0x180006681  jnz     loc_180006B15
0x180006687  mov     [rbp+57h+var_A8], rbx
0x18000668b  test    byte ptr cs:xmmword_180107A60+2, 2
0x180006692  jnz     loc_180006D66
0x180006698  test    rbx, rbx
0x18000669b  jz      loc_180006800
0x1800066a1  cmp     [rbp+57h+var_90], r13d
0x1800066a5  jnz     loc_180006B8A
0x1800066ab  add     rbx, 0B8h
0x1800066b2  lea     rax, [rbp+57h+var_A0]
0x1800066b6  mov     ecx, 10h
0x1800066bb  nop     dword ptr [rax+rax+00h]
0x1800066c0  mov     [rax], r13b
0x1800066c3  lea     rax, [rax+1]
0x1800066c7  sub     rcx, 1
0x1800066cb  jnz     short loc_1800066C0
0x1800066cd  xorps   xmm0, xmm0
0x1800066d0  mov     [rbp+57h+var_90], r13d
0x1800066d4  xorps   xmm1, xmm1
0x1800066d7  lea     rax, [rbp+57h+var_A0]
0x1800066db  movups  xmmword ptr [rbp+57h+var_70.Data1], xmm0
0x1800066df  mov     ecx, 10h
0x1800066e4  movups  xmmword ptr [rbp+57h+var_60.Data1], xmm1
0x1800066e8  nop     dword ptr [rax+rax+00000000h]
0x1800066f0  mov     [rax], r13b
0x1800066f3  lea     rax, [rax+1]
0x1800066f7  sub     rcx, 1
0x1800066fb  jnz     short loc_1800066F0
0x1800066fd  xorps   xmm0, xmm0
0x180006700  mov     dword ptr [rbp+57h+var_80+4], r13d
0x180006704  movups  xmmword ptr [rbp-29h], xmm0
0x180006708  mov     ecx, 10h
0x18000670d  lea     rax, [rbp+57h+var_60]
0x180006711  mov     [rax], r13b
0x180006714  lea     rax, [rax+1]
0x180006718  sub     rcx, 1
0x18000671c  jnz     short loc_180006711
0x18000671e  lea     rdx, [rbp+57h+var_80]
0x180006722  mov     ecx, 1
0x180006727  call    cs:__imp_EtwEventActivityIdControl
0x18000672d  test    eax, eax
0x18000672f  jle     short loc_18000673B
0x180006731  movzx   eax, ax
0x180006734  or      eax, 80070000h
0x180006739  test    eax, eax
0x18000673b  js      loc_180006EA2
0x180006741  movaps  xmm0, [rbp+57h+var_80]
0x180006745  movdqa  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x18000674a  test    rbx, rbx
0x18000674d  jz      loc_18000705B
0x180006753  mov     rdx, rbx
0x180006756  mov     dword ptr [rbp+57h+var_80+4], r13d
0x18000675a  mov     ecx, 2
0x18000675f  call    cs:__imp_EtwEventActivityIdControl
0x180006765  test    eax, eax
0x180006767  jle     short loc_180006773
0x180006769  movzx   eax, ax
0x18000676c  or      eax, 80070000h
0x180006771  test    eax, eax
0x180006773  js      loc_180007091
0x180006779  movaps  xmm0, xmmword ptr [rbp+57h+var_60.Data1]
0x18000677d  mov     rbx, [rbp+57h+var_A8]
0x180006781  movups  xmmword ptr [rbp+57h+var_A0.Data1], xmm0
0x180006785  mov     [rbp+57h+var_90], 1
0x18000678c  test    byte ptr cs:xmmword_180107A60+2, 2
0x180006793  jnz     loc_180006C9B
0x180006799  mov     edx, 646C6957h
0x18000679e  mov     rcx, rbx
0x1800067a1  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x1800067a6  mov     esi, eax
0x1800067a8  test    eax, eax
0x1800067aa  jnz     short loc_1800067F3
0x1800067ac  test    byte ptr cs:xmmword_180107A60+1, 1
0x1800067b3  jnz     loc_180006F6E
0x1800067b9  mov     r9, [rbx+20h]
0x1800067bd  mov     eax, r12d
0x1800067c0  lock xadd [rbx+2Ch], eax
0x1800067c5  sub     eax, 1
0x1800067c8  jz      loc_180006C34
0x1800067ce  mov     edi, r13d
0x1800067d1  test    byte ptr cs:xmmword_180107A60+2, 20h
0x1800067d8  jnz     loc_180006FE8
0x1800067de  test    edi, edi
0x1800067e0  jnz     loc_180006C48
0x1800067e6  test    byte ptr cs:xmmword_180107A60+1, 1
0x1800067ed  jnz     loc_180006FAC
0x1800067f3  test    byte ptr cs:xmmword_180107A60+2, 2
0x1800067fa  jnz     loc_180006B4E
0x180006800  test    byte ptr cs:xmmword_180107A60, 4
0x180006807  jnz     loc_18000709D
0x18000680d  cmp     cs:?GlobalDataInitialized@@3HA, r13d; int GlobalDataInitialized
0x180006814  jz      loc_180006DED
0x18000681a  test    byte ptr cs:xmmword_180107A60+2, 2
0x180006821  jnz     loc_180006D3A
0x180006827  test    r15, r15
0x18000682a  jz      loc_180006A21
0x180006830  mov     edx, 646C6957h
0x180006835  mov     rcx, r15
0x180006838  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x18000683d  test    eax, eax
0x18000683f  jnz     loc_180006A21
0x180006845  mov     rbx, r15
0x180006848  test    byte ptr cs:xmmword_180107A60+1, 1
0x18000684f  jnz     loc_180006BD9
0x180006855  mov     eax, [r15+30h]
0x180006859  test    eax, eax
0x18000685b  jnz     loc_180006E7F
0x180006861  mov     edi, r13d
0x180006864  mov     eax, [r15+2Ch]
0x180006868  test    eax, eax
0x18000686a  jle     loc_180006F64
0x180006870  lea     ecx, [rax+1]
0x180006873  lock cmpxchg [r15+2Ch], ecx
0x180006879  jnz     short loc_180006864
0x18000687b  test    byte ptr cs:xmmword_180107A60+2, 20h
0x180006882  jnz     loc_180006EDA
0x180006888  test    byte ptr cs:xmmword_180107A60+1, 1
0x18000688f  jnz     loc_180006C16
0x180006895  movzx   eax, byte ptr cs:xmmword_180107A50+2
0x18000689c  test    al, 2
0x18000689e  jnz     loc_180006DC8
0x1800068a4  cmp     edi, 6
0x1800068a7  jnz     loc_180006B34
0x1800068ad  mov     [rbp+57h+var_B0], rbx
0x1800068b1  test    byte ptr cs:xmmword_180107A60+2, 2
0x1800068b8  jnz     loc_180006D88
0x1800068be  test    edi, edi
0x1800068c0  jnz     loc_180006E16
0x1800068c6  test    byte ptr cs:xmmword_180107A60, 40h
0x1800068cd  jnz     loc_1800070EA
0x1800068d3  mov     rax, [rbx]
0x1800068d6  mov     rcx, rbx
0x1800068d9  mov     rax, [rax+8]
0x1800068dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068e2  cmp     eax, 74656E49h
0x1800068e7  jnz     short loc_1800068F0
0x1800068e9  lock dec cs:?g_cSessionCount@@3JA; long g_cSessionCount
0x1800068f0  mov     rbx, [rbp+57h+var_B0]
0x1800068f4  test    byte ptr cs:xmmword_180107A60+2, 2
0x1800068fb  jnz     loc_180006CF0
0x180006901  mov     edx, 646C6957h
0x180006906  mov     rcx, rbx
0x180006909  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x18000690e  mov     r14d, eax
0x180006911  test    eax, eax
0x180006913  jnz     short loc_18000695B
0x180006915  test    byte ptr cs:xmmword_180107A60+1, 1
0x18000691c  jnz     loc_180006F8D
0x180006922  mov     r9, [rbx+20h]
0x180006926  lock xadd [rbx+2Ch], r12d
0x18000692c  sub     r12d, 1
0x180006930  jz      loc_180006C3E
0x180006936  mov     esi, r13d
0x180006939  test    byte ptr cs:xmmword_180107A60+2, 20h
0x180006940  jnz     loc_18000700C
0x180006946  test    esi, esi
0x180006948  jnz     loc_180006C60
0x18000694e  test    byte ptr cs:xmmword_180107A60+1, 1
0x180006955  jnz     loc_180006FCA
0x18000695b  test    byte ptr cs:xmmword_180107A60+2, 2
0x180006962  jnz     loc_180006B6C
0x180006968  mov     rcx, r15; void *
0x18000696b  mov     [rbp+57h+var_B0], r13
0x18000696f  call    ?_InternetCloseHandle@@YAHPEAX@Z; _InternetCloseHandle(void *)
0x180006974  mov     r14d, eax
0x180006977  test    eax, eax
0x180006979  jnz     short loc_18000698B
0x18000697b  call    cs:__imp_GetLastError
0x180006981  mov     edi, eax
0x180006983  test    eax, eax
0x180006985  jnz     loc_180006DF2
0x18000698b  test    byte ptr cs:xmmword_180107A60, 4
0x180006992  jnz     loc_180007031
0x180006998  cmp     [rbp+57h+var_90], r13d
0x18000699c  jz      short loc_1800069DC
0x18000699e  cmp     cs:?g_fEtwCorrelationProviderInitialized@@3HA, r13d; int g_fEtwCorrelationProviderInitialized
0x1800069a5  jz      short loc_1800069B5
0x1800069a7  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1800069ad  test    eax, eax
0x1800069af  jnz     loc_180006CDC
0x1800069b5  lea     rdx, [rbp+57h+var_A0]
0x1800069b9  mov     dword ptr [rbp+57h+var_A8+4], r13d
0x1800069bd  mov     ecx, 2
0x1800069c2  call    cs:__imp_EtwEventActivityIdControl
0x1800069c8  test    eax, eax
0x1800069ca  jle     short loc_1800069D6
0x1800069cc  movzx   eax, ax
0x1800069cf  or      eax, 80070000h
0x1800069d4  test    eax, eax
0x1800069d6  js      loc_180006E96
0x1800069dc  mov     ecx, edi; dwErrCode
0x1800069de  call    cs:__imp_SetLastError
0x1800069e4  mov     eax, r14d
0x1800069e7  mov     rcx, [rbp+57h+var_50]
0x1800069eb  xor     rcx, rsp; StackCookie
0x1800069ee  call    __security_check_cookie
0x1800069f3  add     rsp, 0A8h
0x1800069fa  pop     r15
0x1800069fc  pop     r14
0x1800069fe  pop     r13
0x180006a00  pop     r12
0x180006a02  pop     rdi
0x180006a03  pop     rsi
0x180006a04  pop     rbx
0x180006a05  pop     rbp
0x180006a06  retn
0x180006a07  test    byte ptr cs:xmmword_180107A50+2, 2
0x180006a0e  jnz     loc_180006C78
0x180006a14  mov     rbx, r13
0x180006a17  mov     edi, 6
0x180006a1c  jmp     loc_180006687
0x180006a21  test    byte ptr cs:xmmword_180107A50+2, 2
0x180006a28  jnz     loc_180006CB9
0x180006a2e  mov     rbx, r13
0x180006a31  mov     edi, 6
0x180006a36  jmp     loc_1800068AD
0x180006a3b  mov     ecx, 10h
0x180006a40  lea     rax, [rbp+57h+var_A0]
0x180006a44  nop     dword ptr [rax+00h]
0x180006a48  nop     dword ptr [rax+rax+00000000h]
0x180006a50  mov     [rax], r13b
0x180006a53  lea     rax, [rax+1]
0x180006a57  sub     rcx, 1
0x180006a5b  jnz     short loc_180006A50
0x180006a5d  xorps   xmm0, xmm0
0x180006a60  mov     [rbp+57h+var_90], r13d
0x180006a64  xorps   xmm1, xmm1
0x180006a67  lea     rax, [rbp+57h+var_A0]
0x180006a6b  movups  xmmword ptr [rbp+57h+var_70.Data1], xmm0
0x180006a6f  mov     ecx, 10h
0x180006a74  movups  xmmword ptr [rbp+57h+var_60.Data1], xmm1
0x180006a78  nop     dword ptr [rax+rax+00000000h]
0x180006a80  mov     [rax], r13b
0x180006a83  lea     rax, [rax+1]
0x180006a87  sub     rcx, 1
0x180006a8b  jnz     short loc_180006A80
0x180006a8d  lea     rcx, [rbp+57h+var_60]; struct _GUID *
0x180006a91  call    ?WxEtwGetActivityId@@YAXPEAU_GUID@@@Z; WxEtwGetActivityId(_GUID *)
0x180006a96  mov     rdi, [rbp+5Fh]
0x180006a9a  mov     esi, 1
0x180006a9f  lock xadd cs:?g_dwActivityIdCount@@3KC, esi; ulong volatile g_dwActivityIdCount
0x180006aa7  inc     esi
0x180006aa9  call    cs:__imp_GetTickCount
0x180006aaf  mov     ebx, eax
0x180006ab1  call    cs:__imp_GetCurrentProcessId
0x180006ab7  cmp     cs:?g_fEtwCorrelationProviderInitialized@@3HA, r13d; int g_fEtwCorrelationProviderInitialized
  ... truncated ...
```
