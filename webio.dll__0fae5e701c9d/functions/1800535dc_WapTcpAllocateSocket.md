# WapTcpAllocateSocket

- ea: `0x1800535dc`
- end: `0x180053f54`
- name: `WapTcpAllocateSocket`
- size: `2424`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800522a0`
- `0x180052950`

## callees

- `0x18002e460`
- `0x1800452d4`
- `0x1800535dc`
- `0x18005dadc`
- `0x1800648a0`
- `0x180069814`
- `0x1800722f0`
- `0x180072c70`
- `0x18008e92c`
- `0x18009218c`
- `0x1800923bc`
- `0x180092500`
- `0x180092564`
- `0x180096158`
- `0x1800971ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180053eb1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180053eb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053ee8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053ee8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180053f43`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180053f43`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetFileCompletionNotificationModes` at `0x180053ce5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetFileCompletionNotificationModes` at `0x180053ce5`
- `WS2_32!WSASocketW` at `0x180053709`
- `WS2_32!WSASocketW` at `0x180053709`
- `WS2_32!WSAIoctl` at `0x180053a5b`
- `WS2_32!WSAIoctl` at `0x180053b6f`
- `WS2_32!WSAIoctl` at `0x180053c18`
- `WS2_32!WSAIoctl` at `0x180053d8c`
- `WS2_32!WSAIoctl` at `0x180053a5b`
- `WS2_32!WSAIoctl` at `0x180053b6f`
- `WS2_32!WSAIoctl` at `0x180053c18`
- `WS2_32!WSAIoctl` at `0x180053d8c`
- `WS2_32!__imp_bind` at `0x18005398f`
- `WS2_32!__imp_bind` at `0x18005398f`
- `WS2_32!__imp_closesocket` at `0x180053863`
- `WS2_32!__imp_closesocket` at `0x180053f29`
- `WS2_32!__imp_closesocket` at `0x180053863`
- `WS2_32!__imp_closesocket` at `0x180053f29`
- `WS2_32!__imp_getsockopt` at `0x180053cbb`
- `WS2_32!__imp_getsockopt` at `0x180053cbb`
- `WS2_32!__imp_htonl` at `0x1800537bb`
- `WS2_32!__imp_htonl` at `0x1800537bb`
- `WS2_32!__imp_setsockopt` at `0x1800537ea`
- `WS2_32!__imp_setsockopt` at `0x1800538e6`
- `WS2_32!__imp_setsockopt` at `0x1800539f5`
- `WS2_32!__imp_setsockopt` at `0x180053afd`
- `WS2_32!__imp_setsockopt` at `0x180053c69`
- `WS2_32!__imp_setsockopt` at `0x180053e1e`
- `WS2_32!__imp_setsockopt` at `0x1800537ea`
- `WS2_32!__imp_setsockopt` at `0x1800538e6`
- `WS2_32!__imp_setsockopt` at `0x1800539f5`
- `WS2_32!__imp_setsockopt` at `0x180053afd`
- `WS2_32!__imp_setsockopt` at `0x180053c69`
- `WS2_32!__imp_setsockopt` at `0x180053e1e`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1800536bc`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18005372f`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1800536bc`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18005372f`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x1800536a0`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x1800536a0`

## pseudocode

```c
__int64 __fastcall WapTcpAllocateSocket(__int64 a1, __int64 a2)
{
  NET_IF_COMPARTMENT_ID v4; // r14d
  int v5; // r15d
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // eax
  NET_IF_COMPARTMENT_ID v7; // ecx
  unsigned int Error; // ebx
  ADDRESS_FAMILY v9; // r12
  int v10; // edx
  int v11; // ecx
  void *v12; // rsi
  NTSTATUS v13; // eax
  u_long v14; // eax
  int v15; // ebx
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r9
  int v20; // edx
  int v21; // ecx
  int v22; // r8d
  unsigned int LastError; // eax
  sockaddr *v24; // r9
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  unsigned int v32; // eax
  __int64 v33; // rdx
  char v34; // cl
  unsigned int v35; // r14d
  unsigned __int8 v36; // cl
  int v37; // eax
  __int64 v38; // r8
  char v39; // r12
  __int64 v40; // rax
  unsigned int v41; // eax
  unsigned int v42; // eax
  __int64 v43; // rcx
  SOCKET v44; // r14
  struct _TP_IO *v45; // r15
  int v46; // edx
  int v47; // ecx
  __int64 v48; // [rsp+50h] [rbp-B0h] BYREF
  char v49[4]; // [rsp+58h] [rbp-A8h] BYREF
  int vInBuffer; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD cbBytesReturned; // [rsp+60h] [rbp-A0h] BYREF
  char optval[4]; // [rsp+64h] [rbp-9Ch] BYREF
  char v53[4]; // [rsp+68h] [rbp-98h] BYREF
  char v54[4]; // [rsp+6Ch] [rbp-94h] BYREF
  int optlen; // [rsp+70h] [rbp-90h] BYREF
  char v56[4]; // [rsp+74h] [rbp-8Ch] BYREF
  GUID v57; // [rsp+78h] [rbp-88h] BYREF
  __int64 v58; // [rsp+88h] [rbp-78h]
  sockaddr name; // [rsp+90h] [rbp-70h] BYREF
  __int128 v60; // [rsp+A0h] [rbp-60h]
  __int128 v61; // [rsp+B0h] [rbp-50h]
  __int128 v62; // [rsp+C0h] [rbp-40h]
  __int128 v63; // [rsp+D0h] [rbp-30h]
  __int128 v64; // [rsp+E0h] [rbp-20h]
  __int128 v65; // [rsp+F0h] [rbp-10h]
  __int128 v66; // [rsp+100h] [rbp+0h]
  char v67[640]; // [rsp+110h] [rbp+10h] BYREF

  cbBytesReturned = 0;
  v48 = 0;
  *(_DWORD *)optval = 0;
  memset_0(&name, 0, 0x80u);
  *(_DWORD *)v54 = 0;
  *(_DWORD *)v53 = 0;
  memset_0(v67, 0, 0x274u);
  optlen = 0;
  v49[0] = 0;
  v58 = 0;
  v57 = 0;
  v4 = 0;
  vInBuffer = 0;
  v5 = 0;
  *(_DWORD *)v56 = 1;
  if ( (xmmword_1800AD720 & 8) != 0 )
    WPP_SF_qq(1027, 28, (unsigned int)WPP_14086b36644f38024399eb8d606249d9_Traceguids, a1, a2);
  if ( *(_DWORD *)(a1 + 256) )
  {
    CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
    v7 = *(_DWORD *)(a1 + 256);
    v4 = CurrentThreadCompartmentId;
    if ( CurrentThreadCompartmentId != v7 )
    {
      v5 = 1;
      Error = SetCurrentThreadCompartmentId(v7);
      if ( Error )
        goto LABEL_28;
    }
  }
  Error = 0;
  v9 = *(_WORD *)(((unsigned __int64)*(unsigned int *)(a2 + 208) << 7) + *(_QWORD *)(*(_QWORD *)(a1 + 336) + 32LL));
  v12 = (void *)WSASocketW(v9, 1, 6, 0, 0, 0x81u);
  if ( v12 == (void *)-1LL )
    Error = WaWSAGetLastError(0);
  if ( v5 )
  {
    v13 = SetCurrentThreadCompartmentId(v4);
    if ( v13 )
      __fastfail(v13);
  }
  if ( Error )
    goto LABEL_24;
  if ( (Microsoft_Windows_WebIOEnableBits & 0x40) != 0 )
    McTemplateU0pxqx_EventWriteTransfer(v11, v10, *(_QWORD *)(a1 + 8), (_DWORD)v12, 0, 0);
  if ( (xmmword_1800AD720 & 8) != 0 )
    WPP_SF_d(1027, 29, WPP_14086b36644f38024399eb8d606249d9_Traceguids, *(unsigned int *)(a1 + 320));
  v14 = *(_DWORD *)(a1 + 320);
  if ( v14 )
  {
    if ( v9 == 2 )
    {
      v15 = 0;
      v14 = htonl(v14);
    }
    else
    {
      v15 = 41;
    }
    *(_DWORD *)optval = v14;
    if ( setsockopt((SOCKET)v12, v15, 31, optval, 4) == -1 )
    {
      v16 = WaWSAGetLastError(0);
      Error = v16;
      if ( (xmmword_1800AD710 & 8) == 0 )
        goto LABEL_24;
      v17 = 30;
      v18 = 31;
      goto LABEL_23;
    }
  }
  *(_DWORD *)v53 = 1;
  if ( setsockopt((SOCKET)v12, 0xFFFF, 12295, v53, 4) == -1 )
    goto LABEL_32;
  v24 = (sockaddr *)(a1 + 984);
  if ( *(_WORD *)(a1 + 984) )
  {
    v25 = *(_OWORD *)(a1 + 1000);
    name = *v24;
    v26 = *(_OWORD *)(a1 + 1016);
    v60 = v25;
    v27 = *(_OWORD *)(a1 + 1032);
    v61 = v26;
    v28 = *(_OWORD *)(a1 + 1048);
    v62 = v27;
    v29 = *(_OWORD *)(a1 + 1064);
    v63 = v28;
    v30 = *(_OWORD *)(a1 + 1080);
    v64 = v29;
    v31 = *(_OWORD *)(a1 + 1096);
    v65 = v30;
    v66 = v31;
    if ( (xmmword_1800AD720 & 8) != 0 )
      WPP_SF__SOCKADDR_q(v21, v20, v22, (_DWORD)v24, a1);
  }
  else
  {
    memset_0(name.sa_data, 0, 0x7Eu);
    name.sa_family = v9;
  }
  if ( bind((SOCKET)v12, &name, 128) == -1 )
  {
    v32 = WaWSAGetLastError(0);
    Error = v32;
    if ( (xmmword_1800AD710 & 8) == 0 )
      goto LABEL_24;
    v33 = 32;
    goto LABEL_41;
  }
  *(_DWORD *)v54 = 1;
  if ( setsockopt((SOCKET)v12, 6, 1, v54, 4) == -1 )
  {
    v32 = WaWSAGetLastError(0);
    Error = v32;
    if ( (xmmword_1800AD710 & 8) != 0 )
    {
      v33 = 33;
LABEL_41:
      WPP_SF_d(515, v33, WPP_14086b36644f38024399eb8d606249d9_Traceguids, v32);
      goto LABEL_24;
    }
    goto LABEL_24;
  }
  if ( *(_DWORD *)(a1 + 248) != 2
    && WSAIoctl((SOCKET)v12, 0x98000018, (LPVOID)(a1 + 248), 4u, 0, 0, &cbBytesReturned, 0, 0) == -1 )
  {
    v32 = WaWSAGetLastError(0);
    Error = v32;
    if ( (xmmword_1800AD710 & 8) != 0 )
    {
      v33 = 34;
      goto LABEL_41;
    }
LABEL_24:
    if ( v12 != (void *)-1LL )
    {
      if ( (Microsoft_Windows_WebIOEnableBits & 0x40) != 0 )
        McTemplateU0pxqqxt_EventWriteTransfer(v11, v10, *(_QWORD *)(a1 + 8), (_DWORD)v12, 9, Error, 0, 0);
      closesocket((SOCKET)v12);
    }
    goto LABEL_28;
  }
  v34 = *(_BYTE *)(a1 + 252);
  if ( v34 )
  {
    v35 = 3;
    if ( v9 != 2 )
      v35 = 39;
    v36 = 4 * v34;
    v49[0] = v36;
    if ( (xmmword_1800AD720 & 8) != 0 )
      WPP_SF_dd(1027, 35, WPP_14086b36644f38024399eb8d606249d9_Traceguids, v35, v36);
    if ( setsockopt((SOCKET)v12, v9 != 2 ? 0x29 : 0, v35, v49, 1) == -1 )
    {
      v16 = WaWSAGetLastError(0);
      Error = v16;
      if ( (xmmword_1800AD710 & 8) != 0 )
      {
        v17 = 36;
        v18 = v35;
LABEL_23:
        WPP_SF_dd(515, v17, WPP_14086b36644f38024399eb8d606249d9_Traceguids, v18, v16);
        goto LABEL_24;
      }
      goto LABEL_24;
    }
  }
  if ( *(_DWORD *)(a1 + 260)
    && WSAIoctl((SOCKET)v12, 0x98000004, (LPVOID)(a1 + 260), 0xCu, 0, 0, &cbBytesReturned, 0, 0) == -1 )
  {
    v32 = WaWSAGetLastError(0);
    Error = v32;
    if ( (xmmword_1800AD710 & 8) != 0 )
    {
      v33 = 37;
      goto LABEL_41;
    }
    goto LABEL_24;
  }
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 336) + 89LL) && !*(_DWORD *)(a2 + 208) )
  {
    BYTE2(vInBuffer) = -2;
    LOWORD(vInBuffer) = 300;
    goto LABEL_66;
  }
  v37 = *(_DWORD *)(a1 + 238);
  vInBuffer = v37;
  if ( (_WORD)v37 != 0xFFFF || BYTE2(v37) != 0xFF )
  {
LABEL_66:
    if ( WSAIoctl((SOCKET)v12, 0x98000011, &vInBuffer, 4u, 0, 0, &cbBytesReturned, 0, 0) == -1 )
    {
      v32 = WaWSAGetLastError(0);
      Error = v32;
      if ( (xmmword_1800AD710 & 8) != 0 )
      {
        v33 = 38;
        goto LABEL_41;
      }
      goto LABEL_24;
    }
  }
  if ( *(_DWORD *)(a1 + 244) != -1 && setsockopt((SOCKET)v12, 0xFFFF, 4097, (const char *)(a1 + 244), 4) == -1 )
  {
    v32 = WaWSAGetLastError(0);
    Error = v32;
    if ( (xmmword_1800AD710 & 8) != 0 )
    {
      v33 = 39;
      goto LABEL_41;
    }
    goto LABEL_24;
  }
  optlen = 628;
  if ( getsockopt((SOCKET)v12, 0xFFFF, 8197, v67, &optlen) == -1 )
  {
LABEL_32:
    LastError = WaWSAGetLastError(0);
LABEL_33:
    Error = LastError;
    goto LABEL_24;
  }
  v39 = 0;
  if ( (*(_DWORD *)v67 & 0x20000) != 0 )
  {
    v39 = 1;
    if ( !SetFileCompletionNotificationModes(v12, 1u) )
    {
      LastError = WaGetLastError();
      goto LABEL_33;
    }
  }
  if ( (xmmword_1800AD720 & 8) != 0 )
    WPP_SF_qq(
      1027,
      40,
      (unsigned int)WPP_14086b36644f38024399eb8d606249d9_Traceguids,
      *(_QWORD *)(*(_QWORD *)(a1 + 336) + 80LL),
      *(_QWORD *)(a1 + 288));
  v40 = *(_QWORD *)(a1 + 336);
  if ( *(_QWORD *)(v40 + 80) )
  {
    v57 = ASSOCIATE_NAMERES_CONTEXT;
    v58 = *(_QWORD *)(v40 + 80);
    if ( WSAIoctl((SOCKET)v12, 0x98000013, &v57, 0x18u, 0, 0, &cbBytesReturned, 0, 0) == -1 )
    {
      v41 = WaWSAGetLastError(0);
      Error = v41;
      if ( (xmmword_1800AD710 & 8) != 0 )
        WPP_SF_qD(
          515,
          41,
          WPP_14086b36644f38024399eb8d606249d9_Traceguids,
          *(_QWORD *)(*(_QWORD *)(a1 + 336) + 80LL),
          v41);
      goto LABEL_24;
    }
  }
  if ( *(_DWORD *)(a2 + 232) )
  {
    if ( (xmmword_1800AD720 & 8) != 0 )
      WPP_SF_(1027, 42, WPP_14086b36644f38024399eb8d606249d9_Traceguids);
    if ( setsockopt((SOCKET)v12, 6, 15, v56, 4) == -1 )
    {
      v42 = WaWSAGetLastError(0);
      if ( (xmmword_1800AD710 & 8) != 0 )
        WPP_SF_d(515, 43, WPP_14086b36644f38024399eb8d606249d9_Traceguids, v42);
    }
  }
  v43 = *(_QWORD *)(a1 + 288);
  if ( v43 )
  {
    v32 = WapTcpSetSocketProxyDetectionPolicy(v43, v12);
    Error = v32;
    if ( v32 )
    {
      if ( (xmmword_1800AD710 & 8) != 0 )
      {
        v33 = 44;
        goto LABEL_41;
      }
      goto LABEL_24;
    }
  }
  Error = WaTpRegisterCompletionRoutine(v12, WapTcpThreadPoolCompletionRoutine, v38, &v48);
  if ( Error )
    goto LABEL_24;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 696));
  v44 = *(_QWORD *)(a1 + 704);
  v45 = *(struct _TP_IO **)(a1 + 712);
  *(_QWORD *)(a1 + 712) = v48;
  *(_QWORD *)(a1 + 704) = v12;
  *(_BYTE *)(a1 + 981) = v39;
  ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 696));
  if ( v44 != -1 )
  {
    if ( (Microsoft_Windows_WebIOEnableBits & 0x40) != 0 )
      McTemplateU0pxqqxt_EventWriteTransfer(v47, v46, *(_QWORD *)(a1 + 8), v44, 8, 0, 0, 0);
    closesocket(v44);
  }
  Error = 0;
  if ( v45 )
    CloseThreadpoolIo(v45);
LABEL_28:
  if ( (xmmword_1800AD720 & 8) != 0 )
    WPP_SF_d(1027, 45, WPP_14086b36644f38024399eb8d606249d9_Traceguids, Error);
  return Error;
}

```

## disassembly

```asm
0x1800535dc  mov     [rsp-8+arg_10], rbx
0x1800535e1  push    rbp
0x1800535e2  push    rsi
0x1800535e3  push    rdi
0x1800535e4  push    r12
0x1800535e6  push    r13
0x1800535e8  push    r14
0x1800535ea  push    r15
0x1800535ec  lea     rbp, [rsp-2A0h]
0x1800535f4  sub     rsp, 3A0h
0x1800535fb  mov     rax, cs:__security_cookie
0x180053602  xor     rax, rsp
0x180053605  mov     [rbp+2D0h+var_40], rax
0x18005360c  xor     esi, esi
0x18005360e  mov     r13, rdx
0x180053611  mov     rdi, rcx
0x180053614  mov     [rsp+3D0h+cbBytesReturned], esi
0x180053618  xor     edx, edx; Val
0x18005361a  mov     [rsp+3D0h+var_380], rsi
0x18005361f  lea     rcx, [rbp+2D0h+name]; void *
0x180053623  mov     dword ptr [rsp+3D0h+optval], esi
0x180053627  mov     r8d, 80h; Size
0x18005362d  call    memset_0
0x180053632  xor     edx, edx; Val
0x180053634  mov     dword ptr [rsp+3D0h+var_364], esi
0x180053638  mov     r8d, 274h; Size
0x18005363e  mov     dword ptr [rsp+3D0h+var_368], esi
0x180053642  lea     rcx, [rbp+2D0h+var_2C0]; void *
0x180053646  call    memset_0
0x18005364b  xorps   xmm0, xmm0
0x18005364e  mov     [rsp+3D0h+optlen], esi
0x180053652  xor     eax, eax
0x180053654  mov     [rsp+3D0h+var_378], sil
0x180053659  lea     ebx, [rsi+1]
0x18005365c  mov     [rbp+2D0h+var_348], rax
0x180053660  movups  [rsp+3D0h+var_358], xmm0
0x180053665  mov     r14d, esi
0x180053668  mov     [rsp+3D0h+vInBuffer], esi
0x18005366c  mov     r15d, esi
0x18005366f  mov     dword ptr [rsp+3D0h+var_35C], ebx
0x180053673  test    byte ptr cs:xmmword_1800AD720, 8
0x18005367a  jz      short loc_180053698
0x18005367c  lea     edx, [rsi+1Ch]
0x18005367f  mov     qword ptr [rsp+3D0h+g], r13
0x180053684  mov     ecx, 403h
0x180053689  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x180053690  mov     r9, rdi
0x180053693  call    WPP_SF_qq
0x180053698  cmp     [rdi+100h], esi
0x18005369e  jz      short loc_1800536D2
0x1800536a0  call    cs:__imp_GetCurrentThreadCompartmentId
0x1800536a7  nop     dword ptr [rax+rax+00h]
0x1800536ac  mov     ecx, [rdi+100h]; CompartmentId
0x1800536b2  mov     r14d, eax
0x1800536b5  cmp     eax, ecx
0x1800536b7  jz      short loc_1800536D2
0x1800536b9  mov     r15d, ebx
0x1800536bc  call    cs:__imp_SetCurrentThreadCompartmentId
0x1800536c3  nop     dword ptr [rax+rax+00h]
0x1800536c8  mov     ebx, eax
0x1800536ca  test    eax, eax
0x1800536cc  jnz     loc_18005386F
0x1800536d2  mov     rax, [rdi+150h]
0x1800536d9  xor     r9d, r9d; lpProtocolInfo
0x1800536dc  mov     edx, [r13+0D0h]
0x1800536e3  mov     ebx, esi
0x1800536e5  shl     rdx, 7
0x1800536e9  mov     [rsp+3D0h+dwFlags], 81h; dwFlags
0x1800536f1  mov     rcx, [rax+20h]
0x1800536f5  lea     r8d, [r9+6]; protocol
0x1800536f9  mov     [rsp+3D0h+g], esi; g
0x1800536fd  movzx   r12d, word ptr [rdx+rcx]
0x180053702  lea     edx, [r9+1]; type
0x180053706  mov     ecx, r12d; af
0x180053709  call    cs:__imp_WSASocketW
0x180053710  nop     dword ptr [rax+rax+00h]
0x180053715  mov     rsi, rax
0x180053718  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005371c  jnz     short loc_180053727
0x18005371e  xor     ecx, ecx
0x180053720  call    WaWSAGetLastError
0x180053725  mov     ebx, eax
0x180053727  test    r15d, r15d
0x18005372a  jz      short loc_180053748
0x18005372c  mov     ecx, r14d; CompartmentId
0x18005372f  call    cs:__imp_SetCurrentThreadCompartmentId
0x180053736  nop     dword ptr [rax+rax+00h]
0x18005373b  xor     r15d, r15d
0x18005373e  test    eax, eax
0x180053740  jz      short loc_18005374B
0x180053742  mov     ecx, eax
0x180053744  int     29h; Win8: RtlFailFast(ecx)
0x180053746  jmp     short loc_18005374B
0x180053748  xor     r15d, r15d
0x18005374b  test    ebx, ebx
0x18005374d  jnz     loc_18005382F
0x180053753  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits, 40h
0x18005375a  jz      short loc_180053772
0x18005375c  mov     r8, [rdi+8]
0x180053760  mov     r9, rsi
0x180053763  mov     qword ptr [rsp+3D0h+dwFlags], r15
0x180053768  mov     [rsp+3D0h+g], r15d
0x18005376d  call    McTemplateU0pxqx_EventWriteTransfer
0x180053772  mov     r14d, 8
0x180053778  test    byte ptr cs:xmmword_1800AD720, r14b
0x18005377f  jz      short loc_18005379D
0x180053781  mov     r9d, [rdi+140h]
0x180053788  lea     edx, [r14+15h]
0x18005378c  mov     ecx, 403h
0x180053791  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x180053798  call    WPP_SF_d
0x18005379d  mov     eax, [rdi+140h]
0x1800537a3  mov     ebx, 2
0x1800537a8  test    eax, eax
0x1800537aa  jz      loc_1800538C3
0x1800537b0  cmp     r12w, bx
0x1800537b4  jnz     short loc_1800537C9
0x1800537b6  mov     ecx, eax; hostlong
0x1800537b8  mov     ebx, r15d
0x1800537bb  call    cs:__imp_htonl
0x1800537c2  nop     dword ptr [rax+rax+00h]
0x1800537c7  jmp     short loc_1800537CE
0x1800537c9  mov     ebx, 29h ; ')'
0x1800537ce  lea     r9, [rsp+3D0h+optval]; optval
0x1800537d3  mov     dword ptr [rsp+3D0h+optval], eax
0x1800537d7  mov     r8d, 1Fh; optname
0x1800537dd  mov     [rsp+3D0h+g], 4; optlen
0x1800537e5  mov     edx, ebx; level
0x1800537e7  mov     rcx, rsi; s
0x1800537ea  call    cs:__imp_setsockopt
0x1800537f1  nop     dword ptr [rax+rax+00h]
0x1800537f6  cmp     eax, 0FFFFFFFFh
0x1800537f9  jnz     loc_1800538BE
0x1800537ff  xor     ecx, ecx
0x180053801  call    WaWSAGetLastError
0x180053806  mov     ebx, eax
0x180053808  test    byte ptr cs:xmmword_1800AD710, r14b
0x18005380f  jz      short loc_18005382F
0x180053811  mov     edx, 1Eh
0x180053816  lea     r9d, [rdx+1]
0x18005381a  mov     ecx, 203h
0x18005381f  mov     [rsp+3D0h+g], eax
0x180053823  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x18005382a  call    WPP_SF_dd
0x18005382f  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180053833  jz      short loc_18005386F
0x180053835  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits, 40h
0x18005383c  jz      short loc_180053860
0x18005383e  mov     r8, [rdi+8]
0x180053842  mov     r9, rsi
0x180053845  mov     dword ptr [rsp+3D0h+lpOverlapped], r15d
0x18005384a  mov     [rsp+3D0h+lpcbBytesReturned], r15
0x18005384f  mov     [rsp+3D0h+dwFlags], ebx
0x180053853  mov     [rsp+3D0h+g], 9
0x18005385b  call    McTemplateU0pxqqxt_EventWriteTransfer
0x180053860  mov     rcx, rsi; s
0x180053863  call    cs:__imp_closesocket
0x18005386a  nop     dword ptr [rax+rax+00h]
0x18005386f  test    byte ptr cs:xmmword_1800AD720, 8
0x180053876  jz      short loc_180053891
0x180053878  mov     edx, 2Dh ; '-'
0x18005387d  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x180053884  mov     ecx, 403h
0x180053889  mov     r9d, ebx
0x18005388c  call    WPP_SF_d
0x180053891  mov     eax, ebx
0x180053893  mov     rcx, [rbp+2D0h+var_40]
0x18005389a  xor     rcx, rsp; StackCookie
0x18005389d  call    __security_check_cookie
0x1800538a2  mov     rbx, [rsp+3D0h+arg_10]
0x1800538aa  add     rsp, 3A0h
0x1800538b1  pop     r15
0x1800538b3  pop     r14
0x1800538b5  pop     r13
0x1800538b7  pop     r12
0x1800538b9  pop     rdi
0x1800538ba  pop     rsi
0x1800538bb  pop     rbp
0x1800538bc  retn
0x1800538be  mov     ebx, 2
0x1800538c3  lea     r9, [rsp+3D0h+var_368]; optval
0x1800538c8  mov     dword ptr [rsp+3D0h+var_368], 1
0x1800538d0  mov     edx, 0FFFFh; level
0x1800538d5  mov     [rsp+3D0h+g], 4; optlen
0x1800538dd  mov     r8d, 3007h; optname
0x1800538e3  mov     rcx, rsi; s
0x1800538e6  call    cs:__imp_setsockopt
0x1800538ed  nop     dword ptr [rax+rax+00h]
0x1800538f2  cmp     eax, 0FFFFFFFFh
0x1800538f5  jnz     short loc_180053905
0x1800538f7  xor     ecx, ecx
0x1800538f9  call    WaWSAGetLastError
0x1800538fe  mov     ebx, eax
0x180053900  jmp     loc_18005382F
0x180053905  lea     r9, [rdi+3D8h]
0x18005390c  cmp     [r9], r15w
0x180053910  jz      short loc_18005396E
0x180053912  movups  xmm0, xmmword ptr [r9]
0x180053916  movups  xmm1, xmmword ptr [r9+10h]
0x18005391b  movaps  xmmword ptr [rbp+2D0h+name.sa_family], xmm0
0x18005391f  movups  xmm0, xmmword ptr [r9+20h]
0x180053924  movaps  [rbp+2D0h+var_330], xmm1
0x180053928  movups  xmm1, xmmword ptr [r9+30h]
0x18005392d  movaps  [rbp+2D0h+var_320], xmm0
0x180053931  movups  xmm0, xmmword ptr [r9+40h]
0x180053936  movaps  [rbp+2D0h+var_310], xmm1
0x18005393a  movups  xmm1, xmmword ptr [r9+50h]
0x18005393f  movaps  [rbp+2D0h+var_300], xmm0
0x180053943  movups  xmm0, xmmword ptr [r9+60h]
0x180053948  movaps  [rbp+2D0h+var_2F0], xmm1
0x18005394c  movups  xmm1, xmmword ptr [r9+70h]
0x180053951  movaps  [rbp+2D0h+var_2E0], xmm0
0x180053955  movaps  [rbp+2D0h+var_2D0], xmm1
0x180053959  test    byte ptr cs:xmmword_1800AD720, r14b
0x180053960  jz      short loc_180053982
0x180053962  mov     qword ptr [rsp+3D0h+g], rdi
0x180053967  call    WPP_SF__SOCKADDR_q
0x18005396c  jmp     short loc_180053982
0x18005396e  xor     edx, edx; Val
0x180053970  lea     rcx, [rbp+2D0h+name.sa_data]; void *
0x180053974  lea     r8d, [rdx+7Eh]; Size
0x180053978  call    memset_0
0x18005397d  mov     [rbp+2D0h+name.sa_family], r12w
0x180053982  mov     r8d, 80h; namelen
0x180053988  lea     rdx, [rbp+2D0h+name]; name
0x18005398c  mov     rcx, rsi; s
0x18005398f  call    cs:__imp_bind
0x180053996  nop     dword ptr [rax+rax+00h]
0x18005399b  cmp     eax, 0FFFFFFFFh
0x18005399e  jnz     short loc_1800539D4
0x1800539a0  xor     ecx, ecx
0x1800539a2  call    WaWSAGetLastError
0x1800539a7  mov     ebx, eax
0x1800539a9  test    byte ptr cs:xmmword_1800AD710, r14b
0x1800539b0  jz      loc_18005382F
0x1800539b6  mov     edx, 20h ; ' '
0x1800539bb  mov     ecx, 203h
0x1800539c0  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x1800539c7  mov     r9d, eax
0x1800539ca  call    WPP_SF_d
0x1800539cf  jmp     loc_18005382F
0x1800539d4  mov     edx, 6; level
0x1800539d9  mov     dword ptr [rsp+3D0h+var_364], 1
0x1800539e1  lea     r9, [rsp+3D0h+var_364]; optval
0x1800539e6  mov     [rsp+3D0h+g], 4; optlen
0x1800539ee  mov     rcx, rsi; s
0x1800539f1  lea     r8d, [rdx-5]; optname
0x1800539f5  call    cs:__imp_setsockopt
0x1800539fc  nop     dword ptr [rax+rax+00h]
0x180053a01  cmp     eax, 0FFFFFFFFh
0x180053a04  jnz     short loc_180053A23
0x180053a06  xor     ecx, ecx
0x180053a08  call    WaWSAGetLastError
0x180053a0d  mov     ebx, eax
0x180053a0f  test    byte ptr cs:xmmword_1800AD710, r14b
0x180053a16  jz      loc_18005382F
0x180053a1c  mov     edx, 21h ; '!'
0x180053a21  jmp     short loc_1800539BB
0x180053a23  lea     r8, [rdi+0F8h]; lpvInBuffer
0x180053a2a  cmp     [r8], ebx
0x180053a2d  jz      short loc_180053A8C
0x180053a2f  mov     [rsp+3D0h+lpCompletionRoutine], r15; lpCompletionRoutine
0x180053a34  lea     rax, [rsp+3D0h+cbBytesReturned]
0x180053a39  mov     [rsp+3D0h+lpOverlapped], r15; lpOverlapped
0x180053a3e  mov     edx, 98000018h; dwIoControlCode
0x180053a43  mov     [rsp+3D0h+lpcbBytesReturned], rax; lpcbBytesReturned
0x180053a48  mov     r9d, 4; cbInBuffer
0x180053a4e  mov     [rsp+3D0h+dwFlags], r15d; cbOutBuffer
0x180053a53  mov     rcx, rsi; s
0x180053a56  mov     qword ptr [rsp+3D0h+g], r15; lpvOutBuffer
0x180053a5b  call    cs:__imp_WSAIoctl
0x180053a62  nop     dword ptr [rax+rax+00h]
0x180053a67  cmp     eax, 0FFFFFFFFh
0x180053a6a  jnz     short loc_180053A8C
0x180053a6c  xor     ecx, ecx
0x180053a6e  call    WaWSAGetLastError
0x180053a73  mov     ebx, eax
0x180053a75  test    byte ptr cs:xmmword_1800AD710, r14b
0x180053a7c  jz      loc_18005382F
0x180053a82  mov     edx, 22h ; '"'
0x180053a87  jmp     loc_1800539BB
0x180053a8c  mov     cl, [rdi+0FCh]
0x180053a92  mov     eax, 27h ; '''
0x180053a97  test    cl, cl
0x180053a99  jz      loc_180053B37
0x180053a9f  cmp     r12w, bx
0x180053aa3  lea     r14d, [rax-24h]
0x180053aa7  cmovnz  r14d, eax
0x180053aab  sub     r12w, bx
0x180053aaf  neg     r12w
0x180053ab3  sbb     ebx, ebx
0x180053ab5  and     ebx, 29h
0x180053ab8  shl     cl, 2
0x180053abb  mov     [rsp+3D0h+var_378], cl
0x180053abf  test    byte ptr cs:xmmword_1800AD720, 8
0x180053ac6  jz      short loc_180053AE8
0x180053ac8  movzx   eax, cl
0x180053acb  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x180053ad2  mov     ecx, 403h
0x180053ad7  mov     [rsp+3D0h+g], eax
  ... truncated ...
```
