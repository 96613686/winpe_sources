# IsHostInProxyBypassList

- ea: `0x1800c1cc0`
- end: `0x1800c25ac`
- name: `IsHostInProxyBypassList`
- size: `2284`
- prototype: `BOOL __stdcall(INTERNET_SCHEME tScheme, LPCSTR lpszHost, DWORD cchHost)`
- caller_count: `0`
- callee_count: `27`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180009cf0`
- `0x18000c694`
- `0x18000c700`
- `0x18000c940`
- `0x180025980`
- `0x180027ec0`
- `0x18002a4c4`
- `0x1800701d0`
- `0x18007ad20`
- `0x1800bfb9c`
- `0x1800c14f4`
- `0x1800c1cc0`
- `0x1800c25b4`
- `0x1800c2d90`
- `0x1800ca5c0`
- `0x1800ca754`
- `0x1800da348`
- `0x1800da530`
- `0x1800e96f0`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x180154882`
- `0x1801e1790`
- `0x1801e285c`
- `0x1801e3c78`
- `0x1801e6990`
- `0x1801e6e08`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strlwr` at `0x1800c2020`
- `api-ms-win-crt-private-l1-1-0!_o__strlwr` at `0x1800c2020`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c204e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c204e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c202d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c202d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c2204`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c2219`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c2204`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c2219`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c21bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c21bc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c2378`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c2378`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c22a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c22a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c1d96`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c1d96`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c1e77`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c1ed5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c1e77`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c1ed5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800c1d9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800c1d9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c2227`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c2227`
- `ntdll!EtwEventActivityIdControl` at `0x1800c1dbd`
- `ntdll!EtwEventActivityIdControl` at `0x1800c21e8`
- `ntdll!EtwEventActivityIdControl` at `0x1800c1dbd`
- `ntdll!EtwEventActivityIdControl` at `0x1800c21e8`
- `ntdll!RtlGetLastNtStatus` at `0x1800c22b5`
- `ntdll!RtlGetLastNtStatus` at `0x1800c22b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1f53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c22ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1f53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c22ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c1e99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c1e99`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall IsHostInProxyBypassList(INTERNET_SCHEME tScheme, LPCSTR lpszHost, DWORD cchHost)
{
  DWORD v5; // esi
  unsigned int v6; // r13d
  HLOCAL v7; // r14
  __int64 ThreadInfo; // rax
  __int64 v9; // rcx
  struct _GUID *v10; // rax
  __int64 v11; // rdx
  struct _GUID *v12; // rax
  signed __int32 v13; // esi
  DWORD TickCount; // ebx
  int v15; // eax
  bool v16; // sf
  __int64 v17; // rdx
  int v18; // r8d
  __int64 v19; // r13
  LPSTR v20; // rcx
  unsigned int v21; // ebx
  WCHAR *v22; // rdi
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  int cchWideChar; // esi
  WCHAR *v27; // rbx
  SIZE_T v28; // r15
  WCHAR *v29; // rax
  WCHAR *v30; // r14
  signed int v31; // esi
  int v32; // eax
  CServerInfo *ServerInfo; // rdi
  char *v34; // r14
  int v35; // esi
  unsigned int v36; // ecx
  int v37; // eax
  __int64 v38; // rcx
  char *Heap; // rax
  CServerInfo *v40; // r15
  __int64 v41; // rbx
  void *v42; // rdi
  int v43; // eax
  int v44; // r14d
  int v45; // eax
  int ProxyForUrlW; // eax
  CServerInfo *v47; // rbx
  DWORD v48; // eax
  DWORD v49; // edi
  int v50; // eax
  bool v51; // sf
  __int64 v53; // rbx
  __int16 v54; // ax
  int LastError; // eax
  CServerInfo *v56; // rax
  CServerInfo *v57; // rbx
  CServerInfo *v58; // rax
  int v59; // eax
  unsigned int lpWideCharStr; // [rsp+20h] [rbp-99h]
  unsigned int v61[2]; // [rsp+60h] [rbp-59h] BYREF
  LPSTR v62; // [rsp+68h] [rbp-51h] BYREF
  int v63; // [rsp+70h] [rbp-49h]
  void *v64; // [rsp+78h] [rbp-41h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp-39h]
  INTERNET_SCHEME v66; // [rsp+88h] [rbp-31h]
  CServerInfo *v67; // [rsp+90h] [rbp-29h] BYREF
  struct _GUID v68; // [rsp+98h] [rbp-21h] BYREF
  struct _GUID v69; // [rsp+A8h] [rbp-11h] BYREF
  struct _GUID v70; // [rsp+B8h] [rbp-1h] BYREF
  int v71; // [rsp+C8h] [rbp+Fh]
  _UNKNOWN *retaddr; // [rsp+118h] [rbp+5Fh]

  v66 = tScheme;
  if ( (xmmword_180266B60 & 0x20) != 0 )
    WPP_SF_s(1029, 18, WPP_8242b5ef19193bb1e3a608dc6a3a83cc_Traceguids, lpszHost);
  v5 = 0;
  LODWORD(v64) = 0;
  v6 = 0;
  v71 = 0;
  v70 = 0;
  v7 = 0;
  hMem = 0;
  v67 = 0;
  if ( GlobalDataInitialized || (v5 = GlobalDataInitialize()) == 0 )
  {
    ThreadInfo = InternetGetThreadInfo(*(_QWORD *)&tScheme, lpszHost, *(_QWORD *)&cchHost);
    if ( !ThreadInfo )
    {
      v5 = 8;
      goto LABEL_76;
    }
    if ( *(_DWORD *)(ThreadInfo + 72) )
      goto LABEL_76;
    v9 = 16;
    v10 = &v70;
    v11 = 16;
    do
    {
      LOBYTE(v10->Data1) = 0;
      v10 = (struct _GUID *)((char *)v10 + 1);
      --v11;
    }
    while ( v11 );
    v71 = 0;
    v12 = &v70;
    v68 = 0;
    v69 = 0;
    do
    {
      LOBYTE(v12->Data1) = 0;
      v12 = (struct _GUID *)((char *)v12 + 1);
      --v9;
    }
    while ( v9 );
    WxEtwGetActivityId(&v69);
    v13 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
    TickCount = GetTickCount();
    v68.Data1 = (unsigned int)retaddr;
    *(_DWORD *)&v68.Data4[4] = GetCurrentProcessId();
    *(_DWORD *)&v68.Data2 = v13;
    *(_DWORD *)v68.Data4 = TickCount;
    HIDWORD(v62) = 0;
    v15 = EtwEventActivityIdControl(2, &v68);
    v16 = v15 < 0;
    if ( v15 > 0 )
      v16 = 1;
    if ( v16 )
      HIDWORD(v62) = 144;
    WxEtwTransferActivityId(&v68, &v69);
    v71 = 1;
    v70 = v69;
    if ( tScheme )
    {
      if ( tScheme == INTERNET_SCHEME_FTP )
      {
        v54 = 21;
        goto LABEL_101;
      }
      if ( tScheme != INTERNET_SCHEME_HTTP )
      {
        if ( tScheme != INTERNET_SCHEME_HTTPS )
        {
          v5 = 12006;
          goto LABEL_76;
        }
        v63 = 443;
LABEL_19:
        InternetInitializeAutoProxyDll(4u);
        v19 = -1;
        *(_DWORD *)&v68.Data2 = 0;
        v61[0] = 0;
        v20 = 0;
        v62 = 0;
        v21 = -2147024809;
        if ( lpszHost && *lpszHost )
        {
          *(_DWORD *)&v69.Data2 = 0;
          v22 = 0;
          v23 = MultiByteToWideChar(0xFDE9u, 0, lpszHost, -1, 0, 0);
          cchWideChar = v23;
          if ( v23 )
          {
            *(_DWORD *)&v69.Data2 = 0;
            v27 = 0;
            *(_QWORD *)&v68.Data1 = 0;
            v28 = (unsigned int)(2 * v23);
            v29 = (WCHAR *)CoTaskMemAlloc(v28);
            v30 = v29;
            if ( v29 )
            {
              memset_0(v29, 0, (unsigned int)v28);
              v27 = v30;
              *(_QWORD *)&v68.Data1 = v30;
              if ( MultiByteToWideChar(0xFDE9u, 0, lpszHost, -1, v30, cchWideChar) )
              {
                v27 = 0;
                v31 = 0;
                *(_QWORD *)&v68.Data1 = 0;
                v22 = v30;
              }
              else
              {
                LastError = WxGetLastError(v20, v17);
                v31 = LastError;
                if ( LastError > 0 )
                  v31 = (unsigned __int16)LastError | 0x80070000;
                *(_DWORD *)&v69.Data2 = 209;
                if ( v31 >= 0 )
                  v31 = -2147418113;
              }
            }
            else
            {
              v31 = -2147024882;
              *(_DWORD *)&v69.Data2 = 197;
            }
            if ( v27 )
              WxCoTaskAllocator::Free((void **)&v68);
            if ( v31 >= 0 )
            {
              v32 = HostWCharToCharEx(v22, 0xFFFFFFFF, 1, &v62, (int *)v61);
              v31 = v32;
              if ( v32 > 0 )
                v31 = (unsigned __int16)v32 | 0x80070000;
              v21 = -2147024809;
              if ( v31 < 0 )
              {
                v20 = v62;
                *(_DWORD *)&v68.Data2 = 137;
              }
              else
              {
                v20 = 0;
                hMem = v62;
              }
              goto LABEL_32;
            }
            v21 = -2147024809;
          }
          else
          {
            v59 = WxGetLastError(v25, v24);
            v31 = v59;
            if ( v59 > 0 )
              v31 = (unsigned __int16)v59 | 0x80070000;
            *(_DWORD *)&v69.Data2 = 182;
            if ( v31 >= 0 )
              v31 = -2147418113;
          }
          *(_DWORD *)&v68.Data2 = 132;
          goto LABEL_34;
        }
        v22 = 0;
        *(_DWORD *)&v68.Data2 = 127;
        v31 = -2147024809;
LABEL_32:
        if ( v20 )
          CoTaskMemFree(v20);
LABEL_34:
        if ( v22 )
          CoTaskMemFree(v22);
        if ( v31 < 0 )
        {
          if ( v31 == -2147024882 || (v31 = HostCharToAce(lpszHost, 0), v31 < 0) )
          {
            v5 = WX_WIN32_FROM_HR((unsigned int)v31);
            goto LABEL_130;
          }
        }
        ServerInfo = 0;
        *(_QWORD *)v68.Data4 = 0;
        v34 = (char *)String;
        if ( (BYTE1(xmmword_180266B60) & 8) != 0 )
          WPP_SF_slq((_DWORD)v20, v17, v18, (_DWORD)lpszHost, 3, (__int64)&v67);
        v67 = 0;
        if ( !lpszHost )
        {
LABEL_50:
          v61[0] = WX_WIN32_FROM_HR(v21);
          v5 = v61[0];
          if ( v61[0] )
            goto LABEL_55;
          if ( *(_DWORD *)v68.Data4 )
            _strlwr(v34);
          EnterCriticalSection(&stru_180269A28);
          ServerInfo = FindServerInfo(v34);
          if ( !ServerInfo )
          {
            v56 = (CServerInfo *)HeapAlloc(g_hWxProcessHeap, 0, 0x2B0u);
            v57 = v56;
            if ( v56 )
            {
              memset_0(v56, 0, 0x2B0u);
              v58 = CServerInfo::CServerInfo(v57, v34, v61, 3u, lpWideCharStr);
              ServerInfo = v58;
              if ( v58 )
              {
                v5 = v61[0];
                if ( v61[0] )
                {
                  CServerInfo::Dereference(v58);
                  ServerInfo = 0;
                }
                else
                {
                  CServerInfo::Reference(v58);
                }
                goto LABEL_54;
              }
            }
            else
            {
              ServerInfo = 0;
            }
            v5 = 8;
          }
LABEL_54:
          LeaveCriticalSection(&stru_180269A28);
LABEL_55:
          v67 = ServerInfo;
          if ( (BYTE1(xmmword_180266B60) & 8) != 0 )
            WPP_SF_d(1035, 11, WPP_dbd165539a8c3def9fa304381330cff9_Traceguids, v5);
          v62 = v34;
          if ( v34 != String && v34 )
            WxFreeHeapEx(&v62);
          if ( !v5 )
          {
            v40 = v67;
            v41 = 0;
            *(_QWORD *)&v69.Data1 = 0;
            v42 = 0;
            HIDWORD(v62) = 0;
            v6 = 0;
            v64 = 0;
            *(_QWORD *)&v68.Data1 = 0;
            v61[0] = 0;
            if ( hMem && (v43 = InetNewStringAtoW((LPCCH)hMem, -1), v41 = *(_QWORD *)&v69.Data1, v44 = v43, v43 < 0) )
            {
              HIDWORD(v62) = 163;
            }
            else
            {
              v45 = InetNewStringAtoW("/", -1);
              v42 = v64;
              v44 = v45;
              if ( v45 < 0 )
              {
                HIDWORD(v62) = 170;
              }
              else
              {
                ProxyForUrlW = InternalInternetSyncGetProxyForUrlW(511, 0, v40, v41, v64, v66, (_WORD)v63, 0, 0, 0, v61);
                v6 = v61[0];
                v44 = ProxyForUrlW;
                if ( ProxyForUrlW < 0 )
                  HIDWORD(v62) = 192;
              }
            }
            if ( *(_QWORD *)&v68.Data1 )
              WxCoTaskAllocator::Free((void **)&v68);
            if ( v42 )
              WxCoTaskAllocator::Free(&v64);
            if ( v41 )
              WxCoTaskAllocator::Free((void **)&v69);
            if ( v44 < 0 )
              v5 = WX_WIN32_FROM_HR((unsigned int)v44);
            v7 = hMem;
            goto LABEL_76;
          }
LABEL_130:
          v7 = hMem;
          v6 = (unsigned int)v64;
          goto LABEL_76;
        }
        do
          ++v19;
        while ( lpszHost[v19] );
        v35 = 0;
        if ( (_DWORD)v19 )
        {
          if ( (_DWORD)v19 != -1 )
          {
            v36 = v19 + 3;
            v37 = 256;
            if ( (unsigned int)(v19 + 3) > 0x100 )
            {
              if ( v36 > 0x400 )
              {
                v37 = 4096;
                if ( v36 <= 0x1000 )
                  v37 = 1024;
              }
            }
            else
            {
              v37 = 64;
            }
            v38 = -v37 & (unsigned int)(v37 + v19 + 2);
            if ( (unsigned int)(v38 - 1) > 0xFFFFFFE )
            {
              v35 = -2147024809;
              goto LABEL_49;
            }
            HIDWORD(v62) = 0;
            Heap = (char *)WxAllocateHeapEx(v38, (unsigned int)v38);
            if ( !Heap )
            {
              HIDWORD(v62) = 52;
              v35 = -2147024882;
              goto LABEL_49;
            }
            *Heap = 0;
            v34 = Heap;
          }
          memcpy_0(v34, lpszHost, (unsigned int)v19);
          v34[(unsigned int)v19] = 0;
          *(_DWORD *)v68.Data4 = v19;
        }
LABEL_49:
        v21 = v35;
        goto LABEL_50;
      }
    }
    else
    {
      v66 = INTERNET_SCHEME_HTTP;
    }
    v54 = 80;
LABEL_101:
    LOWORD(v63) = v54;
    goto LABEL_19;
  }
LABEL_76:
  v47 = v67;
  if ( v67 )
  {
    if ( (BYTE1(xmmword_180266B60) & 8) != 0 )
      WPP_SF_qs(
        1035,
        18,
        (unsigned int)WPP_dbd165539a8c3def9fa304381330cff9_Traceguids,
        (_DWORD)v67,
        *((_QWORD *)v67 + 5));
    CServerInfo::Dereference(v47);
    if ( (BYTE1(xmmword_180266B60) & 8) != 0 )
      WPP_SF_(1035, 19, WPP_dbd165539a8c3def9fa304381330cff9_Traceguids);
    v67 = 0;
  }
  v48 = GetLastError();
  v49 = v48;
  if ( qword_180269EA8 && v48 && v48 != 997 && v48 != 12150 && v48 != 12028 && v48 != 122 )
  {
    v53 = 16LL * (unsigned __int8)(_InterlockedExchangeAdd(&dword_180269EA4, 1u) + 1);
    GetSystemTimeAsFileTime((LPFILETIME)(v53 + qword_180269EA8));
    *(_DWORD *)(v53 + qword_180269EA8 + 8) = v49;
    *(_DWORD *)(v53 + qword_180269EA8 + 12) = RtlGetLastNtStatus();
  }
  if ( v71 )
  {
    HIDWORD(v62) = 0;
    v50 = EtwEventActivityIdControl(2, &v70);
    v51 = v50 < 0;
    if ( v50 > 0 )
      v51 = 1;
    if ( v51 )
      HIDWORD(v62) = 144;
  }
  SetLastError(v49);
  if ( (xmmword_180266B60 & 0x20) != 0 )
    WPP_SF_d(1029, 19, WPP_8242b5ef19193bb1e3a608dc6a3a83cc_Traceguids, v6);
  SetLastError(v5);
  if ( v7 )
    LocalFree(v7);
  return v6;
}

```

## disassembly

```asm
0x1800c1cc0  mov     [rsp-8+arg_10], rbx
0x1800c1cc5  push    rbp
0x1800c1cc6  push    rsi
0x1800c1cc7  push    rdi
0x1800c1cc8  push    r12
0x1800c1cca  push    r13
0x1800c1ccc  push    r14
0x1800c1cce  push    r15
0x1800c1cd0  lea     rbp, [rsp-27h]
0x1800c1cd5  sub     rsp, 0E0h
0x1800c1cdc  mov     rax, cs:__security_cookie
0x1800c1ce3  xor     rax, rsp
0x1800c1ce6  mov     [rbp+57h+var_40], rax
0x1800c1cea  mov     r12, rdx
0x1800c1ced  mov     [rbp+57h+var_88], ecx
0x1800c1cf0  mov     r15d, ecx
0x1800c1cf3  test    byte ptr cs:xmmword_180266B60, 20h
0x1800c1cfa  jnz     loc_1800C2484
0x1800c1d00  xor     ebx, ebx
0x1800c1d02  xor     eax, eax
0x1800c1d04  cmp     cs:GlobalDataInitialized, ebx
0x1800c1d0a  xorps   xmm0, xmm0
0x1800c1d0d  mov     esi, ebx
0x1800c1d0f  mov     dword ptr [rbp+57h+var_98], ebx
0x1800c1d12  mov     r13d, ebx
0x1800c1d15  mov     [rbp+57h+var_48], eax
0x1800c1d18  movups  [rbp+57h+var_58], xmm0
0x1800c1d1c  mov     r14d, ebx
0x1800c1d1f  mov     [rbp+57h+hMem], rbx
0x1800c1d23  mov     [rbp+57h+var_80], rbx
0x1800c1d27  jz      loc_1800C2175
0x1800c1d2d  call    InternetGetThreadInfo
0x1800c1d32  test    rax, rax
0x1800c1d35  jz      loc_1800C24A2
0x1800c1d3b  cmp     [rax+48h], ebx
0x1800c1d3e  jnz     loc_1800C2184
0x1800c1d44  mov     ecx, 10h
0x1800c1d49  lea     rax, [rbp+57h+var_58]
0x1800c1d4d  mov     edx, ecx
0x1800c1d4f  mov     [rax], bl
0x1800c1d51  inc     rax
0x1800c1d54  sub     rdx, 1
0x1800c1d58  jnz     short loc_1800C1D4F
0x1800c1d5a  xorps   xmm0, xmm0
0x1800c1d5d  mov     [rbp+57h+var_48], ebx
0x1800c1d60  xorps   xmm1, xmm1
0x1800c1d63  lea     rax, [rbp+57h+var_58]
0x1800c1d67  movups  xmmword ptr [rbp+57h+var_78.Data1], xmm0
0x1800c1d6b  movups  xmmword ptr [rbp+57h+var_68.Data1], xmm1
0x1800c1d6f  mov     [rax], bl
0x1800c1d71  inc     rax
0x1800c1d74  sub     rcx, 1
0x1800c1d78  jnz     short loc_1800C1D6F
0x1800c1d7a  lea     rcx, [rbp+57h+var_68]; struct _GUID *
0x1800c1d7e  call    ?WxEtwGetActivityId@@YAXPEAU_GUID@@@Z; WxEtwGetActivityId(_GUID *)
0x1800c1d83  mov     rdi, [rbp+5Fh]
0x1800c1d87  mov     esi, 1
0x1800c1d8c  lock xadd cs:?g_dwActivityIdCount@@3KC, esi; ulong volatile g_dwActivityIdCount
0x1800c1d94  inc     esi
0x1800c1d96  call    cs:__imp_GetTickCount
0x1800c1d9c  mov     ebx, eax
0x1800c1d9e  call    cs:__imp_GetCurrentProcessId
0x1800c1da4  mov     [rbp+57h+var_78.Data1], edi
0x1800c1da7  lea     rdx, [rbp+57h+var_78]
0x1800c1dab  mov     dword ptr [rbp+57h+var_78.Data4+4], eax
0x1800c1dae  mov     ecx, 2
0x1800c1db3  mov     dword ptr [rbp+57h+var_78.Data2], esi
0x1800c1db6  mov     dword ptr [rbp+57h+var_78.Data4], ebx
0x1800c1db9  mov     dword ptr [rbp+57h+var_A8+4], r13d
0x1800c1dbd  call    cs:__imp_EtwEventActivityIdControl
0x1800c1dc3  test    eax, eax
0x1800c1dc5  jle     short loc_1800C1DD1
0x1800c1dc7  movzx   eax, ax
0x1800c1dca  or      eax, 80070000h
0x1800c1dcf  test    eax, eax
0x1800c1dd1  js      loc_1800C24AC
0x1800c1dd7  lea     rdx, [rbp+57h+var_68]; struct _GUID *
0x1800c1ddb  lea     rcx, [rbp+57h+var_78]; struct _GUID *
0x1800c1ddf  call    ?WxEtwTransferActivityId@@YAXPEBU_GUID@@0@Z; WxEtwTransferActivityId(_GUID const *,_GUID const *)
0x1800c1de4  movups  xmm0, xmmword ptr [rbp+57h+var_68.Data1]
0x1800c1de8  mov     ecx, r15d
0x1800c1deb  mov     [rbp+57h+var_48], 1
0x1800c1df2  xor     r15d, r15d
0x1800c1df5  movdqu  [rbp+57h+var_58], xmm0
0x1800c1dfa  test    ecx, ecx
0x1800c1dfc  jz      loc_1800C22D9
0x1800c1e02  sub     ecx, 1
0x1800c1e05  jz      loc_1800C24B8
0x1800c1e0b  sub     ecx, 2
0x1800c1e0e  jz      loc_1800C22E0
0x1800c1e14  cmp     ecx, 1
0x1800c1e17  jnz     loc_1800C23FC
0x1800c1e1d  mov     [rbp+57h+var_A0], 1BBh
0x1800c1e24  mov     ecx, 4; dwReserved
0x1800c1e29  call    InternetInitializeAutoProxyDll
0x1800c1e2e  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800c1e32  mov     dword ptr [rbp+57h+var_78.Data2], r15d
0x1800c1e36  mov     [rbp+57h+var_B0], r15d
0x1800c1e3a  mov     rcx, r15
0x1800c1e3d  mov     [rbp-51h], rcx
0x1800c1e41  mov     ebx, 80070057h
0x1800c1e46  test    r12, r12
0x1800c1e49  jz      loc_1800C22FC
0x1800c1e4f  cmp     [r12], r15b
0x1800c1e53  jz      loc_1800C22FC
0x1800c1e59  mov     [rsp+110h+cchWideChar], r15d; cchWideChar
0x1800c1e5e  mov     r9d, r13d; cbMultiByte
0x1800c1e61  mov     r8, r12; lpMultiByteStr
0x1800c1e64  mov     [rsp+110h+lpWideCharStr], r15; lpWideCharStr
0x1800c1e69  xor     edx, edx; dwFlags
0x1800c1e6b  mov     dword ptr [rbp+57h+var_68.Data2], r15d
0x1800c1e6f  mov     ecx, 0FDE9h; CodePage
0x1800c1e74  mov     rdi, r15
0x1800c1e77  call    cs:__imp_MultiByteToWideChar
0x1800c1e7d  mov     esi, eax
0x1800c1e7f  test    eax, eax
0x1800c1e81  jz      loc_1800C2435
0x1800c1e87  add     eax, eax
0x1800c1e89  mov     dword ptr [rbp+57h+var_68.Data2], r15d
0x1800c1e8d  mov     rbx, r15
0x1800c1e90  mov     ecx, eax; cb
0x1800c1e92  mov     qword ptr [rbp+57h+var_78.Data1], rbx
0x1800c1e96  mov     r15d, eax
0x1800c1e99  call    cs:__imp_CoTaskMemAlloc
0x1800c1e9f  mov     r14, rax
0x1800c1ea2  test    rax, rax
0x1800c1ea5  jz      loc_1800C231B
0x1800c1eab  mov     r8d, r15d; Size
0x1800c1eae  xor     edx, edx; Val
0x1800c1eb0  mov     rcx, rax; void *
0x1800c1eb3  call    memset_0
0x1800c1eb8  mov     rbx, r14
0x1800c1ebb  mov     qword ptr [rbp+57h+var_78.Data1], rbx
0x1800c1ebf  mov     [rsp+110h+cchWideChar], esi; cchWideChar
0x1800c1ec3  mov     r9d, r13d; cbMultiByte
0x1800c1ec6  mov     r8, r12; lpMultiByteStr
0x1800c1ec9  mov     [rsp+110h+lpWideCharStr], rbx; lpWideCharStr
0x1800c1ece  xor     edx, edx; dwFlags
0x1800c1ed0  mov     ecx, 0FDE9h; CodePage
0x1800c1ed5  call    cs:__imp_MultiByteToWideChar
0x1800c1edb  xor     r15d, r15d
0x1800c1ede  test    eax, eax
0x1800c1ee0  jz      loc_1800C2336
0x1800c1ee6  mov     ebx, r15d
0x1800c1ee9  mov     esi, r15d
0x1800c1eec  mov     qword ptr [rbp+57h+var_78.Data1], rbx
0x1800c1ef0  mov     rdi, r14
0x1800c1ef3  test    rbx, rbx
0x1800c1ef6  jz      short loc_1800C1F01
0x1800c1ef8  lea     rcx, [rbp+57h+var_78]; void **
0x1800c1efc  call    ?Free@WxCoTaskAllocator@@SAXPEAPEAX@Z; WxCoTaskAllocator::Free(void * *)
0x1800c1f01  test    esi, esi
0x1800c1f03  js      loc_1800C24C2
0x1800c1f09  lea     rax, [rbp+57h+var_B0]
0x1800c1f0d  mov     r8d, 1
0x1800c1f13  lea     r9, [rbp+57h+var_A8]
0x1800c1f17  mov     [rsp+110h+lpWideCharStr], rax; unsigned int
0x1800c1f1c  or      edx, 0FFFFFFFFh; cchUnicodeChar
0x1800c1f1f  mov     rcx, rdi; lpUnicodeCharStr
0x1800c1f22  call    HostWCharToCharEx
0x1800c1f27  mov     esi, eax
0x1800c1f29  test    eax, eax
0x1800c1f2b  jle     short loc_1800C1F36
0x1800c1f2d  movzx   esi, ax
0x1800c1f30  or      esi, 80070000h
0x1800c1f36  mov     ebx, 80070057h
0x1800c1f3b  test    esi, esi
0x1800c1f3d  js      loc_1800C24C9
0x1800c1f43  mov     rax, [rbp+57h+var_A8]
0x1800c1f47  mov     rcx, r15; pv
0x1800c1f4a  mov     [rbp+57h+hMem], rax
0x1800c1f4e  test    rcx, rcx
0x1800c1f51  jz      short loc_1800C1F59
0x1800c1f53  call    cs:__imp_CoTaskMemFree
0x1800c1f59  test    rdi, rdi
0x1800c1f5c  jnz     loc_1800C22CB
0x1800c1f62  test    esi, esi
0x1800c1f64  js      loc_1800C24D9
0x1800c1f6a  mov     rdi, r15
0x1800c1f6d  mov     qword ptr [rbp+57h+var_78.Data4], r15
0x1800c1f71  lea     r14, String
0x1800c1f78  test    byte ptr cs:xmmword_180266B60+1, 8
0x1800c1f7f  jnz     loc_1800C2406
0x1800c1f85  mov     [rbp+57h+var_80], r15
0x1800c1f89  test    r12, r12
0x1800c1f8c  jz      short loc_1800C2007
0x1800c1f8e  inc     r13
0x1800c1f91  cmp     [r12+r13], r15b
0x1800c1f95  jnz     short loc_1800C1F8E
0x1800c1f97  mov     esi, r15d
0x1800c1f9a  test    r13d, r13d
0x1800c1f9d  jz      short loc_1800C2005
0x1800c1f9f  lea     ecx, [r13+1]
0x1800c1fa3  test    ecx, ecx
0x1800c1fa5  jz      short loc_1800C1FEC
0x1800c1fa7  add     ecx, 2
0x1800c1faa  mov     eax, 100h
0x1800c1faf  cmp     ecx, eax
0x1800c1fb1  ja      loc_1800C250F
0x1800c1fb7  mov     eax, 40h ; '@'
0x1800c1fbc  dec     ecx
0x1800c1fbe  add     ecx, eax
0x1800c1fc0  neg     eax
0x1800c1fc2  and     ecx, eax
0x1800c1fc4  lea     eax, [rcx-1]
0x1800c1fc7  cmp     eax, 0FFFFFFEh
0x1800c1fcc  ja      loc_1800C2360
0x1800c1fd2  mov     edx, ecx
0x1800c1fd4  mov     dword ptr [rbp+57h+var_A8+4], r15d
0x1800c1fd8  call    WxAllocateHeapEx
0x1800c1fdd  test    rax, rax
0x1800c1fe0  jz      loc_1800C2424
0x1800c1fe6  mov     [rax], r15b
0x1800c1fe9  mov     r14, rax
0x1800c1fec  mov     r8d, r13d; Size
0x1800c1fef  mov     rdx, r12; Src
0x1800c1ff2  mov     rcx, r14; void *
0x1800c1ff5  mov     ebx, r13d
0x1800c1ff8  call    memcpy_0
0x1800c1ffd  mov     [rbx+r14], r15b
0x1800c2001  mov     dword ptr [rbp+57h+var_78.Data4], r13d
0x1800c2005  mov     ebx, esi
0x1800c2007  mov     ecx, ebx
0x1800c2009  call    WX_WIN32_FROM_HR
0x1800c200e  mov     [rbp+57h+var_B0], eax
0x1800c2011  mov     esi, eax
0x1800c2013  test    eax, eax
0x1800c2015  jnz     short loc_1800C2054
0x1800c2017  cmp     dword ptr [rbp+57h+var_78.Data4], r15d
0x1800c201b  jz      short loc_1800C2026
0x1800c201d  mov     rcx, r14; String
0x1800c2020  call    cs:__imp__strlwr
0x1800c2026  lea     rcx, stru_180269A28; lpCriticalSection
0x1800c202d  call    cs:__imp_EnterCriticalSection
0x1800c2033  mov     rcx, r14; char *
0x1800c2036  call    ?FindServerInfo@@YAPEAVCServerInfo@@PEBD@Z; FindServerInfo(char const *)
0x1800c203b  mov     rdi, rax
0x1800c203e  test    rax, rax
0x1800c2041  jz      loc_1800C2367
0x1800c2047  lea     rcx, stru_180269A28; lpCriticalSection
0x1800c204e  call    cs:__imp_LeaveCriticalSection
0x1800c2054  mov     [rbp+57h+var_80], rdi
0x1800c2058  test    byte ptr cs:xmmword_180266B60+1, 8
0x1800c205f  jnz     loc_1800C2466
0x1800c2065  lea     rax, String
0x1800c206c  mov     [rbp+57h+var_A8], r14
0x1800c2070  cmp     r14, rax
0x1800c2073  jz      short loc_1800C207E
0x1800c2075  test    r14, r14
0x1800c2078  jnz     loc_1800C230D
0x1800c207e  test    esi, esi
0x1800c2080  jnz     loc_1800C2502
0x1800c2086  mov     rcx, [rbp+57h+hMem]; lpMultiByteStr
0x1800c208a  xor     r12d, r12d
0x1800c208d  mov     r15, [rbp+57h+var_80]
0x1800c2091  mov     ebx, r12d
0x1800c2094  mov     qword ptr [rbp+57h+var_68.Data1], rbx
0x1800c2098  mov     edi, r12d
0x1800c209b  mov     dword ptr [rbp+57h+var_A8+4], r12d
0x1800c209f  mov     r13d, r12d
0x1800c20a2  mov     [rbp+57h+var_98], r12
0x1800c20a6  mov     qword ptr [rbp+57h+var_78.Data1], r12
0x1800c20aa  mov     [rbp+57h+var_B0], r12d
0x1800c20ae  test    rcx, rcx
0x1800c20b1  jz      short loc_1800C20CE
0x1800c20b3  lea     r8, [rbp+57h+var_68]
0x1800c20b7  or      edx, 0FFFFFFFFh; cbMultiByte
0x1800c20ba  call    InetNewStringAtoW
0x1800c20bf  mov     rbx, qword ptr [rbp+57h+var_68.Data1]
0x1800c20c3  mov     r14d, eax
0x1800c20c6  test    eax, eax
0x1800c20c8  js      loc_1800C2538
0x1800c20ce  lea     r8, [rbp+57h+var_98]
0x1800c20d2  or      edx, 0FFFFFFFFh; cbMultiByte
0x1800c20d5  lea     rcx, MultiByteStr; "/"
0x1800c20dc  call    InetNewStringAtoW
0x1800c20e1  mov     rdi, [rbp+57h+var_98]
0x1800c20e5  mov     r14d, eax
0x1800c20e8  test    eax, eax
0x1800c20ea  js      loc_1800C2541
0x1800c20f0  lea     rax, [rbp+57h+var_B0]
0x1800c20f4  mov     r9, rbx
0x1800c20f7  mov     [rsp+110h+var_C0], rax
0x1800c20fc  mov     r8, r15
0x1800c20ff  mov     eax, [rbp+57h+var_A0]
0x1800c2102  xor     edx, edx
0x1800c2104  mov     [rsp+110h+var_C8], r12
0x1800c2109  mov     ecx, 1FFh
0x1800c210e  mov     [rsp+110h+var_D0], r12
0x1800c2113  mov     [rsp+110h+var_D8], r12
0x1800c2118  mov     [rsp+110h+var_E0], ax
0x1800c211d  mov     eax, [rbp+57h+var_88]
0x1800c2120  mov     [rsp+110h+cchWideChar], eax
0x1800c2124  mov     [rsp+110h+lpWideCharStr], rdi
0x1800c2129  call    ?InternalInternetSyncGetProxyForUrlW@@YAJKPEAVINTERNET_HANDLE_OBJECT@@PEAVCServerInfo@@PEBG2W4ProxyResolveScheme@@GPEAW43@PEAPEAGPEAGPEAH@Z; InternalInternetSyncGetProxyForUrlW(ulong,INTERNET_HANDLE_OBJECT *,CServerInfo *,ushort const *,ushort const *,ProxyResolveScheme,ushort,ProxyResolveScheme *,ushort * *,ushort *,int *)
0x1800c212e  mov     r13d, [rbp+57h+var_B0]
0x1800c2132  xor     r15d, r15d
0x1800c2135  mov     r14d, eax
0x1800c2138  test    eax, eax
0x1800c213a  js      loc_1800C2550
  ... truncated ...
```
