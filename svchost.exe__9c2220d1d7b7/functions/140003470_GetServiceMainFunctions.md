# GetServiceMainFunctions

- ea: `0x140003470`
- end: `0x140003cc3`
- name: `GetServiceMainFunctions`
- size: `2131`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x140003cd0`

## callees

- `0x140001d10`
- `0x1400021c0`
- `0x1400030b0`
- `0x140003470`
- `0x140004f90`
- `0x140005922`
- `0x140007488`
- `0x140008cc9`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003829`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003a46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ae5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003829`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003a46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ae5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140003c91`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140003c91`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140003888`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400039d4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140003888`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400039d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003a3a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003a60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003a3a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003a60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400037ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400037ee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400038db`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400038db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140003919`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140003919`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000373b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000373b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1400039b1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x140003a08`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1400039b1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x140003a08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003b69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003b69`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003584`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003633`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003584`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003633`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1400035e9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14000368c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1400035e9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14000368c`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1400036c9`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1400036c9`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x140003b0d`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x140003b82`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x140003b0d`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x140003b82`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x140003815`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x140003ad1`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x140003815`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x140003ad1`

## string_xrefs

- `0x14000357d`: `ServiceDll`
- `0x14000362c`: `ServiceManifest`
- `0x14000395c`: `ServiceMain`
- `0x140003a7b`: `ServiceMain`
- `0x140003b2c`: `SvchostPushServiceGlobalsEx`
- `0x140003b48`: `SvchostPushServiceGlobals`

## pseudocode

```c
__int64 __fastcall GetServiceMainFunctions(__int64 a1, _QWORD *a2, _QWORD *a3, __int64 *a4)
{
  __int64 v4; // rdi
  _QWORD *v5; // r14
  __int64 *v7; // rsi
  __int64 v8; // rax
  __int64 v9; // r15
  char *v10; // r14
  DWORD LastError; // ebx
  WCHAR *v12; // r13
  LSTATUS v13; // eax
  __int64 v14; // r9
  __int64 v15; // rax
  WCHAR v16; // cx
  __int64 v17; // rsi
  __int64 *i; // r9
  char *v19; // rax
  signed __int64 v20; // r8
  int v21; // ecx
  int v22; // edx
  __int64 v23; // rax
  char *v24; // r8
  int v25; // ecx
  int v26; // edx
  unsigned __int16 **v27; // rax
  unsigned __int16 *v28; // rcx
  __int64 v29; // r8
  int v30; // eax
  int v31; // edx
  __int64 v32; // rdi
  bool v33; // zf
  __int64 v34; // rbx
  _QWORD *v35; // rax
  __int64 *v36; // rax
  HKEY v37; // rcx
  WCHAR *v38; // rbx
  __int64 v39; // rax
  int v40; // r14d
  int v41; // eax
  int v42; // esi
  CHAR *v43; // rax
  CHAR *v44; // rdi
  const char *v45; // rdx
  __int64 ServiceDllFunction; // rax
  const WCHAR *v47; // rax
  char *v48; // rcx
  __int64 v49; // rax
  LPCWSTR v50; // rax
  int v51; // ecx
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  LSTATUS v55; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD dwBytes[3]; // [rsp+4Ch] [rbp-B4h] BYREF
  _QWORD *v57; // [rsp+58h] [rbp-A8h]
  LPCWCH lpWideCharStr; // [rsp+60h] [rbp-A0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v60; // [rsp+78h] [rbp-88h] BYREF
  ACTCTXW pActCtx; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+C0h] [rbp-40h] BYREF
  void *v63; // [rsp+D0h] [rbp-30h]
  int v64; // [rsp+D8h] [rbp-28h]
  int v65; // [rsp+DCh] [rbp-24h]
  LPCWSTR v66; // [rsp+E0h] [rbp-20h]
  int v67; // [rsp+E8h] [rbp-18h]
  int v68; // [rsp+ECh] [rbp-14h]
  _QWORD **v69; // [rsp+F0h] [rbp-10h]
  __int64 v70; // [rsp+F8h] [rbp-8h]
  LPCWCH *p_lpWideCharStr; // [rsp+100h] [rbp+0h]
  __int64 v72; // [rsp+108h] [rbp+8h]
  WCHAR DestStr[264]; // [rsp+110h] [rbp+10h] BYREF
  BYTE Data[2]; // [rsp+320h] [rbp+220h] BYREF
  WCHAR Dst[264]; // [rsp+530h] [rbp+430h] BYREF

  v57 = a3;
  v4 = 0;
  v60 = a2;
  v5 = a3;
  *(_QWORD *)&dwBytes[1] = 0;
  v55 = 0;
  Type = 0;
  cbData = 0;
  *(_QWORD *)&EventDescriptor.Id = a4;
  memset(&pActCtx.dwFlags, 0, 52);
  v7 = a4;
  pActCtx.cbSize = 56;
  memset_0(Dst, 0, 0x20Au);
  memset_0(DestStr, 0, 0x20Au);
  memset_0(Data, 0, 0x20Au);
  v8 = *(_QWORD *)(a1 + 8);
  v9 = -1;
  if ( v8 )
  {
    if ( *(_QWORD *)(v8 + 16) )
      goto LABEL_68;
    v47 = *(const WCHAR **)(v8 + 32);
    if ( !v47 || !*v47 )
      goto LABEL_68;
    pActCtx.lpSource = v47;
    v10 = (char *)CreateActCtxW(&pActCtx);
    if ( v10 == (char *)-1LL )
    {
      LastError = GetLastError();
      v4 = 10;
      goto LABEL_83;
    }
    v48 = *(char **)(*(_QWORD *)(a1 + 8) + 40LL);
    if ( (unsigned __int64)(v48 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      ReleaseActCtx(v48);
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 40LL) = v10;
  }
  else
  {
    v10 = 0;
    LastError = OpenServiceParametersKey(*(LPCWSTR *)a1, (PHKEY)&dwBytes[1]);
    if ( LastError )
    {
      v4 = 1;
      goto LABEL_83;
    }
    cbData = 522;
    LastError = RegQueryValueExW(*(HKEY *)&dwBytes[1], L"ServiceDll", 0, &Type, Data, &cbData);
    if ( LastError )
    {
      v4 = 2;
      goto LABEL_83;
    }
    if ( Type != 2 )
    {
      LastError = 2;
      v4 = 3;
      goto LABEL_83;
    }
    if ( !*(_WORD *)Data )
    {
      LastError = 2;
      v4 = 4;
      goto LABEL_83;
    }
    v12 = Dst;
    ExpandEnvironmentStringsW((LPCWSTR)Data, Dst, 0x104u);
    SvchostCharLowerW(Dst);
    cbData = 522;
    v13 = RegQueryValueExW(*(HKEY *)&dwBytes[1], L"ServiceManifest", 0, &Type, Data, &cbData);
    v55 = v13;
    LastError = v13;
    if ( v13 )
    {
      if ( (unsigned int)(v13 - 2) > 1 )
      {
        v4 = 5;
        goto LABEL_83;
      }
      DestStr[0] = 0;
    }
    else
    {
      if ( Type != 2 )
      {
        LastError = 2;
        v4 = 6;
        goto LABEL_83;
      }
      if ( !*(_WORD *)Data )
      {
        LastError = 2;
        v4 = 7;
        goto LABEL_83;
      }
      ExpandEnvironmentStringsW((LPCWSTR)Data, DestStr, 0x104u);
      v14 = -1;
      do
        ++v14;
      while ( DestStr[v14] );
      LCMapStringW(0x400u, 0x100u, DestStr, v14 + 1, DestStr, v14 + 1);
      v15 = -1;
      do
        ++v15;
      while ( Dst[v15] );
      if ( v15 )
      {
        while ( 1 )
        {
          v16 = Dst[--v15];
          if ( v16 == 92 || v16 == 47 )
            break;
          if ( !v15 )
            goto LABEL_28;
        }
        v12 = &Dst[v15 + 1];
      }
    }
LABEL_28:
    v17 = 0;
    AcquireSRWLockShared(&ListLock);
    for ( i = (__int64 *)DllList; i != &DllList; v17 = 0 )
    {
      v19 = (char *)i[3];
      v20 = (char *)v12 - v19;
      do
      {
        v21 = *(unsigned __int16 *)&v19[v20];
        v22 = *(unsigned __int16 *)v19 - v21;
        if ( v22 )
          break;
        v19 += 2;
      }
      while ( v21 );
      if ( !v22 )
      {
        v23 = i[4];
        v24 = (char *)DestStr - v23;
        do
        {
          v25 = *(unsigned __int16 *)&v24[v23];
          v26 = *(unsigned __int16 *)v23 - v25;
          if ( v26 )
            break;
          v23 += 2;
        }
        while ( v25 );
        if ( !v26 )
        {
          v27 = (unsigned __int16 **)i[6];
          v17 = (__int64)i;
          v28 = *v27;
          v29 = *(_QWORD *)a1 - (_QWORD)*v27;
          do
          {
            v30 = *(unsigned __int16 *)((char *)v28 + v29);
            v31 = *v28 - v30;
            if ( v31 )
              break;
            ++v28;
          }
          while ( v30 );
          if ( !v31 )
            break;
        }
      }
      i = (__int64 *)*i;
    }
    ReleaseSRWLockShared(&ListLock);
    if ( !v17 )
    {
      if ( DestStr[0] )
      {
        pActCtx.lpSource = DestStr;
        v10 = (char *)CreateActCtxW(&pActCtx);
        if ( v10 == (char *)-1LL )
        {
          LastError = GetLastError();
          v4 = 8;
          goto LABEL_83;
        }
      }
      v32 = -1;
      do
        v33 = v12[++v32] == 0;
      while ( !v33 );
      v34 = -1;
      do
        v33 = DestStr[++v34] == 0;
      while ( !v33 );
      v35 = HeapAlloc(g_hHeap, 8u, 2 * (v34 + v32) + 60);
      v17 = (__int64)v35;
      if ( !v35 )
      {
        LastError = 8;
        v4 = 9;
        goto LABEL_83;
      }
      v35[4] = (char *)v35 + 2 * v32 + 58;
      v35[3] = v35 + 7;
      memcpy_0(v35 + 7, v12, 2 * v32);
      memcpy_0(*(void **)(v17 + 32), DestStr, 2 * v34);
      *(_QWORD *)(v17 + 48) = a1;
      AcquireSRWLockExclusive(&ListLock);
      v36 = (__int64 *)qword_14000F3B8;
      if ( *(__int64 **)qword_14000F3B8 != &DllList )
        __fastfail(3u);
      *(_QWORD *)v17 = &DllList;
      *(_QWORD *)(v17 + 8) = v36;
      *v36 = v17;
      qword_14000F3B8 = v17;
      ReleaseSRWLockExclusive(&ListLock);
      v4 = 0;
      *(_QWORD *)(v17 + 40) = v10;
    }
    v33 = CustomServiceMainRoutinesAllowed == 0;
    *(_QWORD *)(a1 + 8) = v17;
    if ( !v33 )
    {
      v37 = *(HKEY *)&dwBytes[1];
      lpWideCharStr = 0;
      *(_QWORD *)(a1 + 16) = 0;
      dwBytes[0] = 0;
      if ( !(unsigned int)RegQueryValueWithAlloc(v37, L"ServiceMain", (SIZE_T)dwBytes) )
      {
        v38 = (WCHAR *)lpWideCharStr;
        v39 = -1;
        do
          v33 = lpWideCharStr[++v39] == 0;
        while ( !v33 );
        v40 = v39 + 1;
        v41 = WideCharToMultiByte(0, 0x400u, lpWideCharStr, v39 + 1, 0, 0, 0, 0);
        v42 = v41;
        if ( v41 )
        {
          v43 = (CHAR *)HeapAlloc(g_hHeap, 0, v41);
          v44 = v43;
          if ( v43 )
          {
            if ( WideCharToMultiByte(0, 0x400u, v38, v40, v43, v42, 0, 0) )
            {
              *(_QWORD *)(a1 + 16) = v44;
            }
            else
            {
              HeapFree(g_hHeap, 0, v44);
              GetLastError();
            }
          }
          v4 = 0;
        }
        HeapFree(g_hHeap, 0, v38);
      }
    }
    v7 = *(__int64 **)&EventDescriptor.Id;
  }
  v5 = v57;
LABEL_68:
  v45 = "ServiceMain";
  if ( *(_QWORD *)(a1 + 16) )
    v45 = *(const char **)(a1 + 16);
  ServiceDllFunction = GetServiceDllFunction(*(_QWORD *)(a1 + 8), v45, &v55);
  LastError = v55;
  *v60 = ServiceDllFunction;
  if ( LastError )
  {
    v10 = 0;
    v4 = 11;
  }
  else
  {
    v49 = GetServiceDllFunction(*(_QWORD *)(a1 + 8), "SvchostPushServiceGlobalsEx", 0);
    *v7 = v49;
    if ( !v49 )
      *v5 = GetServiceDllFunction(*(_QWORD *)(a1 + 8), "SvchostPushServiceGlobals", 0);
    LastError = 0;
    v10 = 0;
  }
LABEL_83:
  if ( *(_QWORD *)&dwBytes[1] )
    RegCloseKey(*(HKEY *)&dwBytes[1]);
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    ReleaseActCtx(v10);
  if ( LastError && (unsigned int)dword_14000F000 > 5 )
  {
    v50 = *(LPCWSTR *)a1;
    if ( *(_QWORD *)a1 )
    {
      do
        v33 = v50[++v9] == 0;
      while ( !v33 );
      v51 = 2 * v9 + 2;
    }
    else
    {
      v50 = (LPCWSTR)"";
      v51 = 2;
    }
    v66 = v50;
    v67 = v51;
    v69 = &v60;
    v68 = 0;
    EventDescriptor.Keyword = 0;
    v60 = (_QWORD *)v4;
    v70 = 8;
    v72 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    lpWideCharStr = (LPCWCH)LastError;
    p_lpWideCharStr = &lpWideCharStr;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_14000F008;
    UserData.Size = *(unsigned __int16 *)off_14000F008;
    v63 = &unk_14000BA2D;
    UserData.Reserved = 2;
    v64 = 69;
    v65 = 1;
    dwBytes[0] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
  }
  return LastError;
}

```

## disassembly

```asm
0x140003470  push    rbp
0x140003472  push    rbx
0x140003473  push    rsi
0x140003474  push    rdi
0x140003475  push    r12
0x140003477  push    r13
0x140003479  push    r14
0x14000347b  push    r15
0x14000347d  lea     rbp, [rsp-658h]
0x140003485  sub     rsp, 758h
0x14000348c  mov     rax, cs:__security_cookie
0x140003493  xor     rax, rsp
0x140003496  mov     [rbp+690h+var_50], rax
0x14000349d  xorps   xmm0, xmm0
0x1400034a0  mov     [rsp+790h+var_738], r8
0x1400034a5  xor     edi, edi
0x1400034a7  mov     [rsp+790h+var_718], rdx
0x1400034ac  mov     r14, r8
0x1400034af  mov     qword ptr [rsp+790h+dwBytes+4], rdi
0x1400034b4  mov     r12, rcx
0x1400034b7  mov     [rsp+790h+var_748], edi
0x1400034bb  xor     eax, eax
0x1400034bd  mov     [rsp+790h+Type], edi
0x1400034c1  xor     edx, edx; Val
0x1400034c3  mov     dword ptr [rbp+690h+pActCtx.hModule+4], eax
0x1400034c6  mov     r8d, 20Ah; Size
0x1400034cc  mov     [rsp+790h+cbData], edi
0x1400034d0  lea     rcx, [rbp+690h+Dst]; void *
0x1400034d7  mov     qword ptr [rsp+790h+EventDescriptor.Id], r9
0x1400034dc  movups  xmmword ptr [rbp+690h+pActCtx.dwFlags], xmm0
0x1400034e0  mov     rsi, r9
0x1400034e3  mov     [rbp+690h+pActCtx.cbSize], 38h ; '8'
0x1400034ea  movups  xmmword ptr [rbp+690h+pActCtx+14h], xmm0
0x1400034ee  movups  xmmword ptr [rbp+690h+pActCtx.lpResourceName+4], xmm0
0x1400034f2  call    memset_0
0x1400034f7  xor     edx, edx; Val
0x1400034f9  lea     rcx, [rbp+690h+DestStr]; void *
0x1400034fd  mov     r8d, 20Ah; Size
0x140003503  call    memset_0
0x140003508  xor     edx, edx; Val
0x14000350a  lea     rcx, [rbp+690h+Data]; void *
0x140003511  mov     r8d, 20Ah; Size
0x140003517  call    memset_0
0x14000351c  mov     rax, [r12+8]
0x140003521  mov     r15, 0FFFFFFFFFFFFFFFFh
0x140003528  test    rax, rax
0x14000352b  jnz     loc_140003AB5
0x140003531  mov     rcx, [r12]; lpSubKey
0x140003535  lea     rdx, [rsp+790h+dwBytes+4]; phkResult
0x14000353a  mov     r14d, edi
0x14000353d  call    OpenServiceParametersKey
0x140003542  mov     ebx, eax
0x140003544  test    eax, eax
0x140003546  jz      short loc_140003552
0x140003548  mov     edi, 1
0x14000354d  jmp     loc_140003B5F
0x140003552  mov     rcx, qword ptr [rsp+790h+dwBytes+4]; hKey
0x140003557  lea     rax, [rsp+790h+cbData]
0x14000355c  mov     [rsp+790h+lpcbData], rax; lpcbData
0x140003561  lea     r9, [rsp+790h+Type]; lpType
0x140003566  lea     rax, [rbp+690h+Data]
0x14000356d  mov     [rsp+790h+cbData], 20Ah
0x140003575  xor     r8d, r8d; lpReserved
0x140003578  mov     [rsp+790h+lpData], rax; lpData
0x14000357d  lea     rdx, aServicedll; "ServiceDll"
0x140003584  call    cs:__imp_RegQueryValueExW
0x14000358b  nop     dword ptr [rax+rax+00h]
0x140003590  mov     ebx, eax
0x140003592  test    eax, eax
0x140003594  jz      short loc_1400035A0
0x140003596  mov     edi, 2
0x14000359b  jmp     loc_140003B5F
0x1400035a0  cmp     [rsp+790h+Type], 2
0x1400035a5  jz      short loc_1400035B6
0x1400035a7  mov     ebx, 2
0x1400035ac  mov     edi, 3
0x1400035b1  jmp     loc_140003B5F
0x1400035b6  cmp     word ptr [rbp+690h+Data], di
0x1400035bd  jnz     short loc_1400035CE
0x1400035bf  mov     ebx, 2
0x1400035c4  mov     edi, 4
0x1400035c9  jmp     loc_140003B5F
0x1400035ce  mov     r8d, 104h; nSize
0x1400035d4  lea     rdx, [rbp+690h+Dst]; lpDst
0x1400035db  lea     rcx, [rbp+690h+Data]; lpSrc
0x1400035e2  lea     r13, [rbp+690h+Dst]
0x1400035e9  call    cs:__imp_ExpandEnvironmentStringsW
0x1400035f0  nop     dword ptr [rax+rax+00h]
0x1400035f5  lea     rcx, [rbp+690h+Dst]; lpSrcStr
0x1400035fc  call    SvchostCharLowerW
0x140003601  mov     rcx, qword ptr [rsp+790h+dwBytes+4]; hKey
0x140003606  lea     rax, [rsp+790h+cbData]
0x14000360b  mov     [rsp+790h+lpcbData], rax; lpcbData
0x140003610  lea     r9, [rsp+790h+Type]; lpType
0x140003615  lea     rax, [rbp+690h+Data]
0x14000361c  mov     [rsp+790h+cbData], 20Ah
0x140003624  xor     r8d, r8d; lpReserved
0x140003627  mov     [rsp+790h+lpData], rax; lpData
0x14000362c  lea     rdx, aServicemanifes; "ServiceManifest"
0x140003633  call    cs:__imp_RegQueryValueExW
0x14000363a  nop     dword ptr [rax+rax+00h]
0x14000363f  mov     [rsp+790h+var_748], eax
0x140003643  mov     ebx, eax
0x140003645  test    eax, eax
0x140003647  jnz     loc_14000371B
0x14000364d  cmp     [rsp+790h+Type], 2
0x140003652  jz      short loc_140003663
0x140003654  mov     ebx, 2
0x140003659  mov     edi, 6
0x14000365e  jmp     loc_140003B5F
0x140003663  cmp     word ptr [rbp+690h+Data], di
0x14000366a  jnz     short loc_14000367B
0x14000366c  mov     ebx, 2
0x140003671  mov     edi, 7
0x140003676  jmp     loc_140003B5F
0x14000367b  mov     r8d, 104h; nSize
0x140003681  lea     rdx, [rbp+690h+DestStr]; lpDst
0x140003685  lea     rcx, [rbp+690h+Data]; lpSrc
0x14000368c  call    cs:__imp_ExpandEnvironmentStringsW
0x140003693  nop     dword ptr [rax+rax+00h]
0x140003698  lea     rax, [rbp+690h+DestStr]
0x14000369c  mov     r9, r15
0x14000369f  nop
0x1400036a0  inc     r9
0x1400036a3  cmp     [rax+r9*2], di
0x1400036a8  jnz     short loc_1400036A0
0x1400036aa  inc     r9d; cchSrc
0x1400036ad  lea     rax, [rbp+690h+DestStr]
0x1400036b1  mov     dword ptr [rsp+790h+lpcbData], r9d; cchDest
0x1400036b6  lea     r8, [rbp+690h+DestStr]; lpSrcStr
0x1400036ba  mov     edx, 100h; dwMapFlags
0x1400036bf  mov     [rsp+790h+lpData], rax; lpDestStr
0x1400036c4  mov     ecx, 400h; Locale
0x1400036c9  call    cs:__imp_LCMapStringW
0x1400036d0  nop     dword ptr [rax+rax+00h]
0x1400036d5  lea     rcx, [rbp+690h+Dst]
0x1400036dc  mov     rax, r15
0x1400036df  nop
0x1400036e0  inc     rax
0x1400036e3  cmp     [rcx+rax*2], di
0x1400036e7  jnz     short loc_1400036E0
0x1400036e9  test    rax, rax
0x1400036ec  jz      short loc_140003731
0x1400036ee  xchg    ax, ax
0x1400036f0  dec     rax
0x1400036f3  lea     rdx, [rbp+690h+Dst]
0x1400036fa  movzx   ecx, word ptr [rdx+rax*2]
0x1400036fe  lea     rdx, [rdx+rax*2]
0x140003702  cmp     cx, 5Ch ; '\'
0x140003706  jz      short loc_140003715
0x140003708  cmp     cx, 2Fh ; '/'
0x14000370c  jz      short loc_140003715
0x14000370e  test    rax, rax
0x140003711  jnz     short loc_1400036F0
0x140003713  jmp     short loc_140003731
0x140003715  lea     r13, [rdx+2]
0x140003719  jmp     short loc_140003731
0x14000371b  add     eax, 0FFFFFFFEh
0x14000371e  cmp     eax, 1
0x140003721  jbe     short loc_14000372D
0x140003723  mov     edi, 5
0x140003728  jmp     loc_140003B5F
0x14000372d  mov     [rbp+690h+DestStr], di
0x140003731  lea     rcx, ListLock; SRWLock
0x140003738  mov     rsi, rdi
0x14000373b  call    cs:__imp_AcquireSRWLockShared
0x140003742  nop     dword ptr [rax+rax+00h]
0x140003747  mov     r9, cs:DllList
0x14000374e  lea     r10, DllList
0x140003755  cmp     r9, r10
0x140003758  jz      loc_1400037E7
0x14000375e  xchg    ax, ax
0x140003760  mov     rax, [r9+18h]
0x140003764  mov     r8, r13
0x140003767  sub     r8, rax
0x14000376a  nop     word ptr [rax+rax+00h]
0x140003770  movzx   edx, word ptr [rax]
0x140003773  movzx   ecx, word ptr [rax+r8]
0x140003778  sub     edx, ecx
0x14000377a  jnz     short loc_140003784
0x14000377c  add     rax, 2
0x140003780  test    ecx, ecx
0x140003782  jnz     short loc_140003770
0x140003784  test    edx, edx
0x140003786  jnz     short loc_1400037D8
0x140003788  mov     rax, [r9+20h]
0x14000378c  lea     r8, [rbp+690h+DestStr]
0x140003790  sub     r8, rax
0x140003793  movzx   edx, word ptr [rax]
0x140003796  movzx   ecx, word ptr [rax+r8]
0x14000379b  sub     edx, ecx
0x14000379d  jnz     short loc_1400037A7
0x14000379f  add     rax, 2
0x1400037a3  test    ecx, ecx
0x1400037a5  jnz     short loc_140003793
0x1400037a7  test    edx, edx
0x1400037a9  jnz     short loc_1400037D8
0x1400037ab  mov     rax, [r9+30h]
0x1400037af  mov     rsi, r9
0x1400037b2  mov     r8, [r12]
0x1400037b6  mov     rcx, [rax]
0x1400037b9  sub     r8, rcx
0x1400037bc  nop     dword ptr [rax+00h]
0x1400037c0  movzx   edx, word ptr [rcx]
0x1400037c3  movzx   eax, word ptr [rcx+r8]
0x1400037c8  sub     edx, eax
0x1400037ca  jnz     short loc_1400037D4
0x1400037cc  add     rcx, 2
0x1400037d0  test    eax, eax
0x1400037d2  jnz     short loc_1400037C0
0x1400037d4  test    edx, edx
0x1400037d6  jz      short loc_1400037E7
0x1400037d8  mov     r9, [r9]
0x1400037db  mov     rsi, rdi
0x1400037de  cmp     r9, r10
0x1400037e1  jnz     loc_140003760
0x1400037e7  lea     rcx, ListLock; SRWLock
0x1400037ee  call    cs:__imp_ReleaseSRWLockShared
0x1400037f5  nop     dword ptr [rax+rax+00h]
0x1400037fa  test    rsi, rsi
0x1400037fd  jnz     loc_14000392B
0x140003803  cmp     [rbp+690h+DestStr], di
0x140003807  jz      short loc_140003841
0x140003809  lea     rax, [rbp+690h+DestStr]
0x14000380d  lea     rcx, [rbp+690h+pActCtx]; pActCtx
0x140003811  mov     [rbp+690h+pActCtx.lpSource], rax
0x140003815  call    cs:__imp_CreateActCtxW
0x14000381c  nop     dword ptr [rax+rax+00h]
0x140003821  mov     r14, rax
0x140003824  cmp     rax, r15
0x140003827  jnz     short loc_140003841
0x140003829  call    cs:__imp_GetLastError
0x140003830  nop     dword ptr [rax+rax+00h]
0x140003835  mov     ebx, eax
0x140003837  mov     edi, 8
0x14000383c  jmp     loc_140003B5F
0x140003841  mov     rdi, r15
0x140003844  nop     dword ptr [rax+00h]
0x140003848  nop     dword ptr [rax+rax+00000000h]
0x140003850  cmp     word ptr [r13+rdi*2+2], 0
0x140003857  lea     rdi, [rdi+1]
0x14000385b  jnz     short loc_140003850
0x14000385d  lea     rax, [rbp+690h+DestStr]
0x140003861  mov     rbx, r15
0x140003864  cmp     word ptr [rax+rbx*2+2], 0
0x14000386a  lea     rbx, [rbx+1]
0x14000386e  jnz     short loc_140003864
0x140003870  mov     rcx, cs:g_hHeap; hHeap
0x140003877  lea     r8, [rbx+rdi]
0x14000387b  lea     r8, ds:3Ch[r8*2]; dwBytes
0x140003883  mov     edx, 8; dwFlags
0x140003888  call    cs:__imp_HeapAlloc
0x14000388f  nop     dword ptr [rax+rax+00h]
0x140003894  mov     rsi, rax
0x140003897  test    rax, rax
0x14000389a  jz      loc_140003A1F
0x1400038a0  lea     r8, [rdi+rdi]; Size
0x1400038a4  mov     rdx, r13; Src
0x1400038a7  lea     r9, [r8+3Ah]
0x1400038ab  add     r9, rax
0x1400038ae  lea     rcx, [rax+38h]; void *
0x1400038b2  mov     [rax+20h], r9
0x1400038b6  mov     [rax+18h], rcx
0x1400038ba  call    memcpy_0
0x1400038bf  mov     rcx, [rsi+20h]; void *
0x1400038c3  lea     r8, [rbx+rbx]; Size
0x1400038c7  lea     rdx, [rbp+690h+DestStr]; Src
0x1400038cb  call    memcpy_0
0x1400038d0  lea     rcx, ListLock; SRWLock
0x1400038d7  mov     [rsi+30h], r12
0x1400038db  call    cs:__imp_AcquireSRWLockExclusive
0x1400038e2  nop     dword ptr [rax+rax+00h]
0x1400038e7  mov     rax, cs:qword_14000F3B8
0x1400038ee  lea     rcx, DllList
0x1400038f5  cmp     [rax], rcx
0x1400038f8  jz      short loc_140003901
0x1400038fa  mov     ecx, 3
0x1400038ff  int     29h; Win8: RtlFailFast(ecx)
0x140003901  mov     [rsi], rcx
0x140003904  lea     rcx, ListLock; SRWLock
0x14000390b  mov     [rsi+8], rax
0x14000390f  mov     [rax], rsi
0x140003912  mov     cs:qword_14000F3B8, rsi
0x140003919  call    cs:__imp_ReleaseSRWLockExclusive
0x140003920  nop     dword ptr [rax+rax+00h]
0x140003925  xor     edi, edi
0x140003927  mov     [rsi+28h], r14
0x14000392b  cmp     cs:CustomServiceMainRoutinesAllowed, 0
0x140003932  mov     [r12+8], rsi
0x140003937  jz      loc_140003A6C
0x14000393d  mov     rcx, qword ptr [rsp+790h+dwBytes+4]; hkey
0x140003942  lea     rax, [rsp+790h+dwBytes]
0x140003947  lea     r9, [rsp+790h+lpWideCharStr]
0x14000394c  mov     [rsp+790h+lpData], rax; dwBytes
0x140003951  mov     r8d, 1
0x140003957  mov     [rsp+790h+lpWideCharStr], rdi
0x14000395c  lea     rdx, Value; "ServiceMain"
0x140003963  mov     [r12+10h], rdi
0x140003968  mov     dword ptr [rsp+790h+dwBytes], edi
0x14000396c  call    RegQueryValueWithAlloc
  ... truncated ...
```
