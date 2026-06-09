# GetServiceMainFunctions

- ea: `0x140003180`
- end: `0x1400039db`
- name: `GetServiceMainFunctions`
- size: `2139`
- prototype: `__int64 __fastcall(__int64, _QWORD *, FARPROC *, FARPROC *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x1400039f0`

## callees

- `0x140001c50`
- `0x140002e00`
- `0x140003180`
- `0x140004bd0`
- `0x140005542`
- `0x140006f58`
- `0x140008679`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000351d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000378d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003816`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000351d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000378d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003816`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400039b0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400039b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140003578`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000368c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000372a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140003578`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000368c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000372a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003787`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000379f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003787`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000379f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400034ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400034ed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400035c5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400035c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400035fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400035fd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000343f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000343f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x140003711`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x140003758`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x140003711`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x140003758`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003892`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003892`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003298`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000333c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003298`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000333c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000365b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400036c9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000365b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400036c9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1400032f8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140003396`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1400032f8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140003396`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1400033cc`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1400033cc`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x140003838`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1400038a5`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x140003838`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1400038a5`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x14000350f`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x140003808`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x14000350f`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x140003808`

## string_xrefs

- `0x140003291`: `ServiceDll`
- `0x140003335`: `ServiceManifest`
- `0x14000362b`: `ServiceMain`
- `0x1400036ae`: `ServiceMain`
- `0x1400037b4`: `ServiceMain`
- `0x140003851`: `SvchostPushServiceGlobalsEx`
- `0x14000386d`: `SvchostPushServiceGlobals`

## pseudocode

```c
__int64 __fastcall GetServiceMainFunctions(__int64 a1, _QWORD *a2, FARPROC *a3, FARPROC *a4)
{
  FARPROC *v4; // r14
  FARPROC *v6; // rsi
  __int64 v7; // rax
  __int64 v8; // r15
  char *v9; // r14
  DWORD LastError; // ebx
  __int64 v11; // rdi
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
  HKEY v37; // rdi
  WCHAR *v38; // rbx
  __int64 v39; // rax
  int v40; // r14d
  int v41; // eax
  int v42; // esi
  CHAR *v43; // rax
  CHAR *v44; // rdi
  const CHAR *v45; // rdx
  FARPROC ServiceDllFunction; // rax
  const WCHAR *v47; // rax
  char *v48; // rcx
  FARPROC v49; // rax
  LPCWSTR v50; // rax
  int v51; // ecx
  LSTATUS v53; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  FARPROC *v56; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pdwType; // [rsp+5Ch] [rbp-A4h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v61; // [rsp+78h] [rbp-88h] BYREF
  ACTCTXW pActCtx; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+C0h] [rbp-40h] BYREF
  void *v64; // [rsp+D0h] [rbp-30h]
  int v65; // [rsp+D8h] [rbp-28h]
  int v66; // [rsp+DCh] [rbp-24h]
  LPCWSTR v67; // [rsp+E0h] [rbp-20h]
  int v68; // [rsp+E8h] [rbp-18h]
  int v69; // [rsp+ECh] [rbp-14h]
  _QWORD **v70; // [rsp+F0h] [rbp-10h]
  __int64 v71; // [rsp+F8h] [rbp-8h]
  FARPROC **v72; // [rsp+100h] [rbp+0h]
  __int64 v73; // [rsp+108h] [rbp+8h]
  WCHAR DestStr[264]; // [rsp+110h] [rbp+10h] BYREF
  BYTE Data[2]; // [rsp+320h] [rbp+220h] BYREF
  WCHAR Dst[264]; // [rsp+530h] [rbp+430h] BYREF

  *(_QWORD *)&EventDescriptor.Id = a3;
  v61 = a2;
  v4 = a3;
  hKey = 0;
  v53 = 0;
  Type = 0;
  cbData = 0;
  v56 = a4;
  memset(&pActCtx.dwFlags, 0, 52);
  v6 = a4;
  pActCtx.cbSize = 56;
  memset_0(Dst, 0, 0x20Au);
  memset_0(DestStr, 0, 0x20Au);
  memset_0(Data, 0, 0x20Au);
  v7 = *(_QWORD *)(a1 + 8);
  v8 = -1;
  if ( v7 )
  {
    if ( *(_QWORD *)(v7 + 16) )
      goto LABEL_71;
    v47 = *(const WCHAR **)(v7 + 32);
    if ( !v47 || !*v47 )
      goto LABEL_71;
    pActCtx.lpSource = v47;
    v9 = (char *)CreateActCtxW(&pActCtx);
    if ( v9 == (char *)-1LL )
    {
      LastError = GetLastError();
      v11 = 10;
      goto LABEL_87;
    }
    v48 = *(char **)(*(_QWORD *)(a1 + 8) + 40LL);
    if ( (unsigned __int64)(v48 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      ReleaseActCtx(v48);
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 40LL) = v9;
  }
  else
  {
    v9 = 0;
    LastError = OpenServiceParametersKey(*(LPCWSTR *)a1, &hKey);
    if ( LastError )
    {
      v11 = 1;
      goto LABEL_87;
    }
    cbData = 522;
    LastError = RegQueryValueExW(hKey, L"ServiceDll", 0, &Type, Data, &cbData);
    if ( LastError )
    {
      v11 = 2;
      goto LABEL_87;
    }
    if ( Type != 2 )
    {
      LastError = 2;
      v11 = 3;
      goto LABEL_87;
    }
    if ( !*(_WORD *)Data )
    {
      LastError = 2;
      v11 = 4;
      goto LABEL_87;
    }
    v12 = Dst;
    ExpandEnvironmentStringsW((LPCWSTR)Data, Dst, 0x104u);
    SvchostCharLowerW(Dst);
    cbData = 522;
    v13 = RegQueryValueExW(hKey, L"ServiceManifest", 0, &Type, Data, &cbData);
    v53 = v13;
    LastError = v13;
    if ( v13 )
    {
      if ( (unsigned int)(v13 - 2) > 1 )
      {
        v11 = 5;
        goto LABEL_87;
      }
      DestStr[0] = 0;
    }
    else
    {
      if ( Type != 2 )
      {
        LastError = 2;
        v11 = 6;
        goto LABEL_87;
      }
      if ( !*(_WORD *)Data )
      {
        LastError = 2;
        v11 = 7;
        goto LABEL_87;
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
        v9 = (char *)CreateActCtxW(&pActCtx);
        if ( v9 == (char *)-1LL )
        {
          v11 = 8;
          LastError = GetLastError();
          goto LABEL_87;
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
        v11 = 9;
        goto LABEL_87;
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
      *(_QWORD *)(v17 + 40) = v9;
    }
    *(_QWORD *)(a1 + 8) = v17;
    if ( CustomServiceMainRoutinesAllowed )
    {
      v37 = hKey;
      *(_QWORD *)(a1 + 16) = 0;
      pdwType = 0;
      pcbData = 0;
      if ( !RegGetValueW(v37, 0, L"ServiceMain", 0xFFFFu, &pdwType, 0, &pcbData) && pdwType == 1 )
      {
        if ( pcbData )
        {
          v38 = (WCHAR *)HeapAlloc(g_hHeap, 0, pcbData);
          if ( v38 )
          {
            if ( !RegGetValueW(v37, 0, L"ServiceMain", 0xFFFFu, &pdwType, v38, &pcbData) )
            {
              v39 = -1;
              do
                v33 = v38[++v39] == 0;
              while ( !v33 );
              v40 = v39 + 1;
              v41 = WideCharToMultiByte(0, 0x400u, v38, v39 + 1, 0, 0, 0, 0);
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
              }
            }
            HeapFree(g_hHeap, 0, v38);
          }
        }
      }
    }
    v6 = v56;
  }
  v4 = *(FARPROC **)&EventDescriptor.Id;
LABEL_71:
  v45 = "ServiceMain";
  if ( *(_QWORD *)(a1 + 16) )
    v45 = *(const CHAR **)(a1 + 16);
  ServiceDllFunction = GetServiceDllFunction(*(_QWORD *)(a1 + 8), v45, (DWORD *)&v53);
  LastError = v53;
  *v61 = ServiceDllFunction;
  if ( LastError )
  {
    v11 = 11;
  }
  else
  {
    v49 = GetServiceDllFunction(*(_QWORD *)(a1 + 8), "SvchostPushServiceGlobalsEx", 0);
    *v6 = v49;
    if ( !v49 )
      *v4 = GetServiceDllFunction(*(_QWORD *)(a1 + 8), "SvchostPushServiceGlobals", 0);
    LastError = 0;
    v11 = 0;
  }
  v9 = 0;
LABEL_87:
  if ( hKey )
    RegCloseKey(hKey);
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    ReleaseActCtx(v9);
  if ( LastError && (unsigned int)dword_14000F000 > 5 )
  {
    v50 = *(LPCWSTR *)a1;
    if ( *(_QWORD *)a1 )
    {
      do
        v33 = v50[++v8] == 0;
      while ( !v33 );
      v51 = 2 * v8 + 2;
    }
    else
    {
      v50 = (LPCWSTR)"";
      v51 = 2;
    }
    v67 = v50;
    v68 = v51;
    v70 = &v61;
    v69 = 0;
    v61 = (_QWORD *)v11;
    v71 = 8;
    v73 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    v56 = (FARPROC *)LastError;
    v72 = &v56;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_14000F008;
    UserData.Size = *(unsigned __int16 *)off_14000F008;
    v64 = &unk_14000BA2D;
    UserData.Reserved = 2;
    v65 = 69;
    v66 = 1;
    v53 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
  }
  return LastError;
}

```

## disassembly

```asm
0x140003180  push    rbp
0x140003182  push    rbx
0x140003183  push    rsi
0x140003184  push    rdi
0x140003185  push    r12
0x140003187  push    r13
0x140003189  push    r14
0x14000318b  push    r15
0x14000318d  lea     rbp, [rsp-658h]
0x140003195  sub     rsp, 758h
0x14000319c  mov     rax, cs:__security_cookie
0x1400031a3  xor     rax, rsp
0x1400031a6  mov     [rbp+690h+var_50], rax
0x1400031ad  xorps   xmm0, xmm0
0x1400031b0  mov     qword ptr [rsp+790h+EventDescriptor.Id], r8
0x1400031b5  xor     r13d, r13d
0x1400031b8  mov     [rsp+790h+var_718], rdx
0x1400031bd  mov     r14, r8
0x1400031c0  mov     [rsp+790h+hKey], r13
0x1400031c5  mov     r12, rcx
0x1400031c8  mov     [rsp+790h+var_750], r13d
0x1400031cd  xor     eax, eax
0x1400031cf  mov     [rsp+790h+Type], r13d
0x1400031d4  xor     edx, edx; Val
0x1400031d6  mov     dword ptr [rbp+690h+pActCtx.hModule+4], eax
0x1400031d9  mov     r8d, 20Ah; Size
0x1400031df  mov     [rsp+790h+cbData], r13d
0x1400031e4  lea     rcx, [rbp+690h+Dst]; void *
0x1400031eb  mov     [rsp+790h+var_740], r9
0x1400031f0  movups  xmmword ptr [rbp+690h+pActCtx.dwFlags], xmm0
0x1400031f4  mov     rsi, r9
0x1400031f7  mov     [rbp+690h+pActCtx.cbSize], 38h ; '8'
0x1400031fe  movups  xmmword ptr [rbp+690h+pActCtx+14h], xmm0
0x140003202  movups  xmmword ptr [rbp+690h+pActCtx.lpResourceName+4], xmm0
0x140003206  call    memset_0
0x14000320b  xor     edx, edx; Val
0x14000320d  lea     rcx, [rbp+690h+DestStr]; void *
0x140003211  mov     r8d, 20Ah; Size
0x140003217  call    memset_0
0x14000321c  xor     edx, edx; Val
0x14000321e  lea     rcx, [rbp+690h+Data]; void *
0x140003225  mov     r8d, 20Ah; Size
0x14000322b  call    memset_0
0x140003230  mov     rax, [r12+8]
0x140003235  mov     r15, 0FFFFFFFFFFFFFFFFh
0x14000323c  test    rax, rax
0x14000323f  jnz     loc_1400037EB
0x140003245  mov     rcx, [r12]; lpSubKey
0x140003249  lea     rdx, [rsp+790h+hKey]; phkResult
0x14000324e  mov     r14d, r13d
0x140003251  call    OpenServiceParametersKey
0x140003256  mov     ebx, eax
0x140003258  test    eax, eax
0x14000325a  jz      short loc_140003266
0x14000325c  mov     edi, 1
0x140003261  jmp     loc_140003888
0x140003266  mov     rcx, [rsp+790h+hKey]; hKey
0x14000326b  lea     rax, [rsp+790h+cbData]
0x140003270  mov     [rsp+790h+lpcbData], rax; lpcbData
0x140003275  lea     r9, [rsp+790h+Type]; lpType
0x14000327a  lea     rax, [rbp+690h+Data]
0x140003281  mov     [rsp+790h+cbData], 20Ah
0x140003289  xor     r8d, r8d; lpReserved
0x14000328c  mov     [rsp+790h+lpData], rax; lpData
0x140003291  lea     rdx, aServicedll; "ServiceDll"
0x140003298  call    cs:__imp_RegQueryValueExW
0x14000329e  mov     ebx, eax
0x1400032a0  test    eax, eax
0x1400032a2  jz      short loc_1400032AE
0x1400032a4  mov     edi, 2
0x1400032a9  jmp     loc_140003888
0x1400032ae  cmp     [rsp+790h+Type], 2
0x1400032b3  jz      short loc_1400032C4
0x1400032b5  mov     ebx, 2
0x1400032ba  mov     edi, 3
0x1400032bf  jmp     loc_140003888
0x1400032c4  cmp     word ptr [rbp+690h+Data], r13w
0x1400032cc  jnz     short loc_1400032DD
0x1400032ce  mov     ebx, 2
0x1400032d3  mov     edi, 4
0x1400032d8  jmp     loc_140003888
0x1400032dd  mov     r8d, 104h; nSize
0x1400032e3  lea     rdx, [rbp+690h+Dst]; lpDst
0x1400032ea  lea     rcx, [rbp+690h+Data]; lpSrc
0x1400032f1  lea     r13, [rbp+690h+Dst]
0x1400032f8  call    cs:__imp_ExpandEnvironmentStringsW
0x1400032fe  lea     rcx, [rbp+690h+Dst]; lpSrcStr
0x140003305  call    SvchostCharLowerW
0x14000330a  mov     rcx, [rsp+790h+hKey]; hKey
0x14000330f  lea     rax, [rsp+790h+cbData]
0x140003314  mov     [rsp+790h+lpcbData], rax; lpcbData
0x140003319  lea     r9, [rsp+790h+Type]; lpType
0x14000331e  lea     rax, [rbp+690h+Data]
0x140003325  mov     [rsp+790h+cbData], 20Ah
0x14000332d  xor     r8d, r8d; lpReserved
0x140003330  mov     [rsp+790h+lpData], rax; lpData
0x140003335  lea     rdx, aServicemanifes; "ServiceManifest"
0x14000333c  call    cs:__imp_RegQueryValueExW
0x140003342  mov     [rsp+790h+var_750], eax
0x140003346  mov     ebx, eax
0x140003348  test    eax, eax
0x14000334a  jnz     loc_14000341B
0x140003350  cmp     [rsp+790h+Type], 2
0x140003355  jz      short loc_140003369
0x140003357  mov     ebx, 2
0x14000335c  mov     edi, 6
0x140003361  xor     r13d, r13d
0x140003364  jmp     loc_140003888
0x140003369  cmp     word ptr [rbp+690h+Data], r14w
0x140003371  jnz     short loc_140003385
0x140003373  mov     ebx, 2
0x140003378  mov     edi, 7
0x14000337d  xor     r13d, r13d
0x140003380  jmp     loc_140003888
0x140003385  mov     r8d, 104h; nSize
0x14000338b  lea     rdx, [rbp+690h+DestStr]; lpDst
0x14000338f  lea     rcx, [rbp+690h+Data]; lpSrc
0x140003396  call    cs:__imp_ExpandEnvironmentStringsW
0x14000339c  lea     rax, [rbp+690h+DestStr]
0x1400033a0  mov     r9, r15
0x1400033a3  inc     r9
0x1400033a6  cmp     [rax+r9*2], r14w
0x1400033ab  jnz     short loc_1400033A3
0x1400033ad  inc     r9d; cchSrc
0x1400033b0  lea     rax, [rbp+690h+DestStr]
0x1400033b4  mov     dword ptr [rsp+790h+lpcbData], r9d; cchDest
0x1400033b9  lea     r8, [rbp+690h+DestStr]; lpSrcStr
0x1400033bd  mov     edx, 100h; dwMapFlags
0x1400033c2  mov     [rsp+790h+lpData], rax; lpDestStr
0x1400033c7  mov     ecx, 400h; Locale
0x1400033cc  call    cs:__imp_LCMapStringW
0x1400033d2  lea     rcx, [rbp+690h+Dst]
0x1400033d9  mov     rax, r15
0x1400033dc  nop     dword ptr [rax+00h]
0x1400033e0  inc     rax
0x1400033e3  cmp     [rcx+rax*2], r14w
0x1400033e8  jnz     short loc_1400033E0
0x1400033ea  test    rax, rax
0x1400033ed  jz      short loc_140003436
0x1400033ef  nop
0x1400033f0  dec     rax
0x1400033f3  lea     rdx, [rbp+690h+Dst]
0x1400033fa  movzx   ecx, word ptr [rdx+rax*2]
0x1400033fe  lea     rdx, [rdx+rax*2]
0x140003402  cmp     cx, 5Ch ; '\'
0x140003406  jz      short loc_140003415
0x140003408  cmp     cx, 2Fh ; '/'
0x14000340c  jz      short loc_140003415
0x14000340e  test    rax, rax
0x140003411  jnz     short loc_1400033F0
0x140003413  jmp     short loc_140003436
0x140003415  lea     r13, [rdx+2]
0x140003419  jmp     short loc_140003436
0x14000341b  add     eax, 0FFFFFFFEh
0x14000341e  cmp     eax, 1
0x140003421  jbe     short loc_140003430
0x140003423  mov     edi, 5
0x140003428  xor     r13d, r13d
0x14000342b  jmp     loc_140003888
0x140003430  xor     eax, eax
0x140003432  mov     [rbp+690h+DestStr], ax
0x140003436  lea     rcx, ListLock; SRWLock
0x14000343d  xor     esi, esi
0x14000343f  call    cs:__imp_AcquireSRWLockShared
0x140003445  mov     r9, cs:DllList
0x14000344c  lea     r10, DllList
0x140003453  cmp     r9, r10
0x140003456  jz      loc_1400034E6
0x14000345c  nop     dword ptr [rax+00h]
0x140003460  mov     rax, [r9+18h]
0x140003464  mov     r8, r13
0x140003467  sub     r8, rax
0x14000346a  nop     word ptr [rax+rax+00h]
0x140003470  movzx   edx, word ptr [rax]
0x140003473  movzx   ecx, word ptr [rax+r8]
0x140003478  sub     edx, ecx
0x14000347a  jnz     short loc_140003484
0x14000347c  add     rax, 2
0x140003480  test    ecx, ecx
0x140003482  jnz     short loc_140003470
0x140003484  test    edx, edx
0x140003486  jnz     short loc_1400034D8
0x140003488  mov     rax, [r9+20h]
0x14000348c  lea     r8, [rbp+690h+DestStr]
0x140003490  sub     r8, rax
0x140003493  movzx   edx, word ptr [rax]
0x140003496  movzx   ecx, word ptr [rax+r8]
0x14000349b  sub     edx, ecx
0x14000349d  jnz     short loc_1400034A7
0x14000349f  add     rax, 2
0x1400034a3  test    ecx, ecx
0x1400034a5  jnz     short loc_140003493
0x1400034a7  test    edx, edx
0x1400034a9  jnz     short loc_1400034D8
0x1400034ab  mov     rax, [r9+30h]
0x1400034af  mov     rsi, r9
0x1400034b2  mov     r8, [r12]
0x1400034b6  mov     rcx, [rax]
0x1400034b9  sub     r8, rcx
0x1400034bc  nop     dword ptr [rax+00h]
0x1400034c0  movzx   edx, word ptr [rcx]
0x1400034c3  movzx   eax, word ptr [rcx+r8]
0x1400034c8  sub     edx, eax
0x1400034ca  jnz     short loc_1400034D4
0x1400034cc  add     rcx, 2
0x1400034d0  test    eax, eax
0x1400034d2  jnz     short loc_1400034C0
0x1400034d4  test    edx, edx
0x1400034d6  jz      short loc_1400034E6
0x1400034d8  mov     r9, [r9]
0x1400034db  xor     esi, esi
0x1400034dd  cmp     r9, r10
0x1400034e0  jnz     loc_140003460
0x1400034e6  lea     rcx, ListLock; SRWLock
0x1400034ed  call    cs:__imp_ReleaseSRWLockShared
0x1400034f3  test    rsi, rsi
0x1400034f6  jnz     loc_140003607
0x1400034fc  cmp     [rbp+690h+DestStr], r14w
0x140003501  jz      short loc_140003532
0x140003503  lea     rax, [rbp+690h+DestStr]
0x140003507  lea     rcx, [rbp+690h+pActCtx]; pActCtx
0x14000350b  mov     [rbp+690h+pActCtx.lpSource], rax
0x14000350f  call    cs:__imp_CreateActCtxW
0x140003515  mov     r14, rax
0x140003518  cmp     rax, r15
0x14000351b  jnz     short loc_140003532
0x14000351d  call    cs:__imp_GetLastError
0x140003523  mov     edi, 8
0x140003528  xor     r13d, r13d
0x14000352b  mov     ebx, eax
0x14000352d  jmp     loc_140003888
0x140003532  mov     rdi, r15
0x140003535  nop     word ptr [rax+rax+00000000h]
0x140003540  cmp     word ptr [r13+rdi*2+2], 0
0x140003547  lea     rdi, [rdi+1]
0x14000354b  jnz     short loc_140003540
0x14000354d  lea     rax, [rbp+690h+DestStr]
0x140003551  mov     rbx, r15
0x140003554  cmp     word ptr [rax+rbx*2+2], 0
0x14000355a  lea     rbx, [rbx+1]
0x14000355e  jnz     short loc_140003554
0x140003560  mov     rcx, cs:g_hHeap; hHeap
0x140003567  lea     r8, [rbx+rdi]
0x14000356b  lea     r8, ds:3Ch[r8*2]; dwBytes
0x140003573  mov     edx, 8; dwFlags
0x140003578  call    cs:__imp_HeapAlloc
0x14000357e  mov     rsi, rax
0x140003581  test    rax, rax
0x140003584  jz      loc_140003769
0x14000358a  lea     r8, [rdi+rdi]; Size
0x14000358e  mov     rdx, r13; Src
0x140003591  lea     r9, [r8+3Ah]
0x140003595  add     r9, rax
0x140003598  lea     rcx, [rax+38h]; void *
0x14000359c  mov     [rax+20h], r9
0x1400035a0  mov     [rax+18h], rcx
0x1400035a4  call    memcpy_0
0x1400035a9  mov     rcx, [rsi+20h]; void *
0x1400035ad  lea     r8, [rbx+rbx]; Size
0x1400035b1  lea     rdx, [rbp+690h+DestStr]; Src
0x1400035b5  call    memcpy_0
0x1400035ba  lea     rcx, ListLock; SRWLock
0x1400035c1  mov     [rsi+30h], r12
0x1400035c5  call    cs:__imp_AcquireSRWLockExclusive
0x1400035cb  mov     rax, cs:qword_14000F3B8
0x1400035d2  lea     rcx, DllList
0x1400035d9  cmp     [rax], rcx
0x1400035dc  jz      short loc_1400035E5
0x1400035de  mov     ecx, 3
0x1400035e3  int     29h; Win8: RtlFailFast(ecx)
0x1400035e5  mov     [rsi], rcx
0x1400035e8  lea     rcx, ListLock; SRWLock
0x1400035ef  mov     [rsi+8], rax
0x1400035f3  mov     [rax], rsi
0x1400035f6  mov     cs:qword_14000F3B8, rsi
0x1400035fd  call    cs:__imp_ReleaseSRWLockExclusive
0x140003603  mov     [rsi+28h], r14
0x140003607  xor     r13d, r13d
0x14000360a  mov     [r12+8], rsi
0x14000360f  cmp     cs:CustomServiceMainRoutinesAllowed, r13d
0x140003616  jz      loc_1400037A5
0x14000361c  mov     rdi, [rsp+790h+hKey]
0x140003621  lea     rax, [rsp+790h+var_738]
0x140003626  mov     [rsp+790h+pcbData], rax; pcbData
0x14000362b  lea     r8, Value; "ServiceMain"
0x140003632  lea     rax, [rsp+790h+pdwType]
0x140003637  mov     [rsp+790h+lpcbData], r13; pvData
0x14000363c  mov     r9d, 0FFFFh; dwFlags
0x140003642  mov     [rsp+790h+lpData], rax; pdwType
0x140003647  xor     edx, edx; lpSubKey
0x140003649  mov     [r12+10h], r13
0x14000364e  mov     rcx, rdi; hkey
0x140003651  mov     [rsp+790h+pdwType], r13d
0x140003656  mov     [rsp+790h+var_738], r13d
0x14000365b  call    cs:__imp_RegGetValueW
0x140003661  test    eax, eax
0x140003663  jnz     loc_1400037A5
0x140003669  cmp     [rsp+790h+pdwType], 1
0x14000366e  jnz     loc_1400037A5
0x140003674  mov     eax, [rsp+790h+var_738]
  ... truncated ...
```
