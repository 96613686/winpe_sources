# CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)

- ea: `0x180003de8`
- end: `0x180004851`
- name: `?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z`
- size: `2665`
- prototype: `__int64 __fastcall(_QWORD *, __int64, DWORD, char, int, char)`
- caller_count: `44`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000681c`
- `0x180007374`
- `0x180007824`
- `0x180011178`
- `0x180014a00`
- `0x180016550`
- `0x180018b00`
- `0x180019008`
- `0x1800191e0`
- `0x18001a0d0`
- `0x18001a5f4`
- `0x18001a858`
- `0x18001a940`
- `0x18001b380`
- `0x18001bdd8`
- `0x18001c5dc`
- `0x18001d988`
- `0x18001dc3c`
- `0x18001dd84`
- `0x18001de8c`
- `0x18001e148`
- `0x18001e270`
- `0x18001e90c`
- `0x18001ea00`
- `0x18001fb80`
- `0x180020638`
- `0x18002131c`
- `0x180021bc4`
- `0x1800235e0`
- `0x180023834`
- `0x18002432c`
- `0x180024710`
- `0x180024a6c`
- `0x180025228`
- `0x1800298a0`
- `0x180029e60`
- `0x18002a4f8`
- `0x18002acd4`
- `0x18002b198`
- `0x18002e3a0`
- `0x180039394`
- `0x180040688`
- `0x180040a54`
- `0x180041418`

## callees

- `0x18000212c`
- `0x180003de8`
- `0x18003649c`
- `0x1800367b8`
- `0x1800368c4`
- `0x180037080`
- `0x1800372e8`
- `0x18003750c`
- `0x1800377c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1800040c3`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1800040c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004217`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004222`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000429a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004217`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004222`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000429a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003f4b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003f4b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180004032`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180004032`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180004203`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180004203`

## string_xrefs

- `0x180003e79`: `Channel not open`
- `0x180003eea`: `previous IOCTL hasn't yet completed`
- `0x180003fad`: `CreateEvent(NULL, TRUE, FALSE, NULL)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CVssIOCTLChannel::Call(_QWORD *a1, __int64 a2, DWORD a3, char a4, int a5, char a6)
{
  void *v8; // rcx
  HANDLE EventW; // rax
  unsigned int v10; // ecx
  LPVOID *v11; // r9
  unsigned int v12; // eax
  LPVOID *v13; // rdx
  unsigned int v14; // r8d
  LPVOID *v15; // rcx
  __int64 v16; // rax
  __int16 v17; // ax
  __int16 v18; // ax
  signed int LastError; // eax
  signed int v20; // edi
  int v21; // eax
  int v22; // edi
  __int64 v23; // rax
  __int16 v24; // ax
  LPVOID lpOutBuffer; // [rsp+20h] [rbp-E0h]
  DWORD nOutBufferSize[2]; // [rsp+28h] [rbp-D8h]
  LPDWORD lpBytesReturned; // [rsp+30h] [rbp-D0h]
  LPOVERLAPPED lpOverlapped; // [rsp+38h] [rbp-C8h]
  LPVOID *v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+70h] [rbp-90h]
  const unsigned __int16 *v32; // [rsp+78h] [rbp-88h] BYREF
  const wchar_t *v33; // [rsp+80h] [rbp-80h]
  const unsigned __int16 *v34; // [rsp+88h] [rbp-78h]
  int v35; // [rsp+90h] [rbp-70h]
  int v36; // [rsp+94h] [rbp-6Ch]
  int v37; // [rsp+98h] [rbp-68h]
  _BYTE v38[120]; // [rsp+A0h] [rbp-60h] BYREF
  int v39; // [rsp+118h] [rbp+18h]
  _QWORD *v40; // [rsp+120h] [rbp+20h]
  unsigned int *v41; // [rsp+128h] [rbp+28h]
  HANDLE v42; // [rsp+138h] [rbp+38h]
  int v43; // [rsp+190h] [rbp+90h]
  BOOL v44; // [rsp+190h] [rbp+90h]
  int v45; // [rsp+190h] [rbp+90h]
  unsigned int v46; // [rsp+190h] [rbp+90h]
  LPVOID v47; // [rsp+190h] [rbp+90h]
  LPVOID v48; // [rsp+190h] [rbp+90h]
  HANDLE v49; // [rsp+190h] [rbp+90h]
  int v53; // [rsp+1C0h] [rbp+C0h]
  int v54; // [rsp+1C0h] [rbp+C0h]
  LPVOID v55; // [rsp+1C0h] [rbp+C0h]
  __int64 v56; // [rsp+1C0h] [rbp+C0h]

  *(_DWORD *)(a2 + 8) = 0;
  if ( !*a1 )
  {
    *((_DWORD *)a1 + 11) = 0;
    *((_DWORD *)a1 + 16) = 0;
    v32 = L"base\\stor\\vss\\inc\\ichannel.hxx";
    v33 = L"CVssIOCTLChannel::Call";
    v34 = L"INCICHLH";
    v37 = 255;
    v35 = 381;
    v36 = 10;
    v39 = 0x1000000;
    memset_0(v38, 0, sizeof(v38));
    CVssFunctionTracer::TranslateGenericError(a2, &v32, 2147549183LL, L"Channel not open");
  }
  if ( *((_BYTE *)a1 + 41) )
  {
    v35 = 386;
    v36 = 10;
    v32 = L"base\\stor\\vss\\inc\\ichannel.hxx";
    v33 = L"CVssIOCTLChannel::Call";
    v34 = L"INCICHLH";
    v37 = 255;
    v39 = 0x1000000;
    memset_0(v38, 0, sizeof(v38));
    CVssFunctionTracer::Throw(a2, &v32, 2147942487LL, L"previous IOCTL hasn't yet completed");
  }
  *((_DWORD *)a1 + 16) = 0;
  v41 = (unsigned int *)(a1 + 9);
  *((_DWORD *)a1 + 18) = 0;
  if ( a6 )
  {
    v8 = (void *)a1[4];
    a1[1] = 0;
    a1[2] = 0;
    a1[3] = 0;
    a1[4] = v8;
    *((_BYTE *)a1 + 41) = 1;
    if ( v8 )
    {
      if ( !ResetEvent(v8) )
      {
        v35 = 418;
        v32 = L"base\\stor\\vss\\inc\\ichannel.hxx";
        v33 = L"CVssIOCTLChannel::Call";
        v34 = L"INCICHLH";
        v37 = 255;
        v36 = 10;
        v39 = 0x1000000;
        memset_0(v38, 0, sizeof(v38));
        CVssFunctionTracer::TranslateWin32Error(a2, &v32, L"ResetEvent(m_overlapped.hEvent)");
      }
    }
    else
    {
      EventW = CreateEventW(0, 1, 0, 0);
      a1[4] = EventW;
      if ( !EventW )
      {
        v35 = 407;
        v32 = L"base\\stor\\vss\\inc\\ichannel.hxx";
        v33 = L"CVssIOCTLChannel::Call";
        v34 = L"INCICHLH";
        v37 = 255;
        v36 = 10;
        v39 = 0x1000000;
        memset_0(v38, 0, sizeof(v38));
        CVssFunctionTracer::TranslateWin32Error(a2, &v32, L"CreateEvent(NULL, TRUE, FALSE, NULL)");
      }
      *((_BYTE *)a1 + 40) = 1;
    }
  }
  v10 = *((_DWORD *)a1 + 17);
  v11 = (LPVOID *)(a1 + 10);
  v12 = 0;
  v13 = (LPVOID *)(a1 + 10);
  while ( 1 )
  {
    v43 = v10;
    v14 = v10;
    v53 = v12;
    if ( v12 )
    {
      v14 = v10;
      v43 = v10;
LABEL_17:
      v15 = v11;
      v40 = v11;
      v30 = v11;
      if ( v12 <= v14 )
        goto LABEL_20;
      goto LABEL_18;
    }
    if ( v10 )
      goto LABEL_17;
    v12 = 4096;
    v40 = v13;
    v53 = 4096;
    v15 = v13;
    v30 = v13;
LABEL_18:
    v16 = _o_realloc(*v15, v12);
    if ( !v16 )
    {
      *((_DWORD *)a1 + 11) = 0;
      *((_DWORD *)a1 + 16) = 0;
      v32 = L"base\\stor\\vss\\inc\\ichannel.hxx";
      v33 = L"CVssIOCTLChannel::Call";
      v34 = L"INCICHLH";
      v35 = 442;
      v36 = 10;
      v37 = 255;
      v39 = 0x1000000;
      memset_0(v38, 0, sizeof(v38));
      CVssFunctionTracer::Throw(a2, &v32, 2147942414LL, L"Could not extend the output buffer");
    }
    *v40 = v16;
    *((_DWORD *)a1 + 17) = v53;
    v43 = v53;
LABEL_20:
    v32 = L"base\\stor\\vss\\inc\\ichannel.hxx";
    v33 = L"CVssIOCTLChannel::Call";
    v34 = L"INCICHLH";
    v35 = 451;
    v36 = 10;
    v37 = 255;
    v39 = 0x1000000;
    memset_0(v38, 0, sizeof(v38));
    v17 = 15;
    do
      --v17;
    while ( v17 );
    LODWORD(lpBytesReturned) = v43;
    nOutBufferSize[0] = *((_DWORD *)a1 + 11);
    CVssFunctionTracer::Trace(
      a2,
      &v32,
      L"IOCTL sent: %lx on device %s\n Input buffer size: %ld, Output buffer size: %ld",
      a3,
      a1[13],
      *(_QWORD *)nOutBufferSize,
      lpBytesReturned);
    v32 = L"base\\stor\\vss\\inc\\ichannel.hxx";
    v33 = L"CVssIOCTLChannel::Call";
    v34 = L"INCICHLH";
    v35 = 453;
    v36 = 10;
    v37 = 255;
    v39 = 0x1000000;
    memset_0(v38, 0, sizeof(v38));
    v18 = 15;
    do
      --v18;
    while ( v18 );
    CVssFunctionTracer::TraceBuffer(a2, &v32, *((unsigned int *)a1 + 11), a1[7]);
    v44 = DeviceIoControl(
            (HANDLE)*a1,
            a3,
            (LPVOID)a1[7],
            *((_DWORD *)a1 + 11),
            *v30,
            *((_DWORD *)a1 + 17),
            (LPDWORD)a1 + 18,
            (LPOVERLAPPED)((unsigned __int64)(a1 + 1) & -(__int64)(a6 != 0)));
    if ( v44 || GetLastError() != 122 && GetLastError() != 234 )
      break;
    v10 = *((_DWORD *)a1 + 17);
    v11 = (LPVOID *)(a1 + 10);
    v13 = v30;
    v12 = 2 * v10;
  }
  LastError = GetLastError();
  v20 = LastError;
  *((_DWORD *)a1 + 11) = 0;
  *((_DWORD *)a1 + 16) = 0;
  if ( v44 || a6 && LastError == 997 )
  {
    v22 = *((_DWORD *)a1 + 18);
    v49 = (HANDLE)*a1;
    v23 = a1[13];
    v36 = 10;
    v56 = v23;
    v32 = L"base\\stor\\vss\\inc\\ichannel.hxx";
    v33 = L"CVssIOCTLChannel::Call";
    v34 = L"INCICHLH";
    v35 = 549;
    v37 = 255;
    v39 = 0x1000000;
    memset_0(v38, 0, sizeof(v38));
    v24 = 15;
    do
      --v24;
    while ( v24 );
    LODWORD(lpBytesReturned) = v22;
    CVssFunctionTracer::Trace(
      a2,
      &v32,
      L"IOCTL %lx succeeded on device %s - 0x%08lx. \n Output buffer: size received = %ld",
      a3,
      v56,
      v49,
      lpBytesReturned);
    v32 = L"base\\stor\\vss\\inc\\ichannel.hxx";
    v33 = L"CVssIOCTLChannel::Call";
    v34 = L"INCICHLH";
    v35 = 551;
    v36 = 10;
    v37 = 255;
    v39 = 0x1000000;
    memset_0(v38, 0, sizeof(v38));
    CVssFunctionTracer::TraceBuffer(a2, &v32, *v41, *v30);
    v20 = 0;
  }
  else
  {
    if ( a4 )
    {
      if ( !a5 )
        goto LABEL_55;
      if ( a5 == 1 )
      {
        v48 = *v30;
        if ( LastError > 0 )
          v20 = (unsigned __int16)LastError | 0x80070000;
        v32 = L"base\\stor\\vss\\inc\\ichannel.hxx";
        v33 = L"CVssIOCTLChannel::Call";
        v34 = L"INCICHLH";
        v35 = 496;
        v36 = 1;
        v37 = 255;
        v39 = 0x1000000;
        memset_0(v38, 0, sizeof(v38));
        LODWORD(lpBytesReturned) = a3;
        CVssFunctionTracer::TranslateGenericError(
          a2,
          &v32,
          (unsigned int)v20,
          L"DeviceIoControl(%s - %p,0x%08lx,%p,%d,%p,%d,[%d])",
          a1[13],
          *a1,
          lpBytesReturned,
          a1[7],
          0,
          v48,
          *((_DWORD *)a1 + 17),
          *((_DWORD *)a1 + 18));
      }
      if ( a5 != 2 )
      {
        if ( a5 != 3 )
        {
          if ( a5 == 4 )
          {
            v21 = -2147212536;
            if ( v20 != 87 )
              v21 = -2147212538;
            v46 = v21;
            v55 = *v30;
            if ( v20 > 0 )
              v20 = (unsigned __int16)v20 | 0x80070000;
            v32 = L"base\\stor\\vss\\inc\\ichannel.hxx";
            v33 = L"CVssIOCTLChannel::Call";
            v34 = L"INCICHLH";
            v35 = 534;
            v36 = 2;
            v37 = 255;
            v39 = 0x1000000;
            memset_0(v38, 0, sizeof(v38));
            LODWORD(lpOverlapped) = a3;
            CVssFunctionTracer::TranslateInternalProviderError(
              a2,
              &v32,
              (unsigned int)v20,
              v46,
              L"DeviceIoControl(%s - %p,0x%08lx,%p,%d,%p,%d,[%d])",
              a1[13],
              *a1,
              lpOverlapped,
              a1[7],
              0,
              v55,
              *((_DWORD *)a1 + 17),
              *((_DWORD *)a1 + 18));
          }
          if ( (unsigned int)(a5 - 5) <= 1 )
          {
            v45 = *((_DWORD *)a1 + 18);
            v54 = *((_DWORD *)a1 + 17);
            v40 = *v30;
            v31 = a1[7];
            v42 = (HANDLE)*a1;
            v41 = (unsigned int *)a1[13];
            if ( LastError > 0 )
              v20 = (unsigned __int16)LastError | 0x80070000;
            v32 = L"base\\stor\\vss\\inc\\ichannel.hxx";
            v33 = L"CVssIOCTLChannel::Call";
            v34 = L"INCICHLH";
            v35 = 505;
            v36 = 1;
            v37 = 255;
            v39 = 0x1000000;
            memset_0(v38, 0, sizeof(v38));
            LODWORD(lpOverlapped) = a3;
            CVssFunctionTracer::TranslateInternalLovelaceError(
              a2,
              &v32,
              (unsigned int)v20,
              a5 == 5,
              L"DeviceIoControl(%s - %p,0x%08lx,%p,%d,%p,%d,[%d])",
              v41,
              v42,
              lpOverlapped,
              v31,
              0,
              v40,
              v54,
              v45);
          }
LABEL_55:
          v32 = L"base\\stor\\vss\\inc\\ichannel.hxx";
          v33 = L"CVssIOCTLChannel::Call";
          v34 = L"INCICHLH";
          v35 = 490;
          v36 = 10;
          v37 = 255;
          v39 = 0x1000000;
          memset_0(v38, 0, sizeof(v38));
          LODWORD(lpOverlapped) = v20;
          LODWORD(lpOutBuffer) = a3;
          CVssFunctionTracer::Throw(
            a2,
            &v32,
            2147549183LL,
            L"Could not send the IOCTL 0x%08lx on device %s - 0x%08lx. [0x%08lx]\n",
            lpOutBuffer,
            a1[13],
            *a1,
            lpOverlapped);
        }
        if ( LastError == 87 )
          v20 = 1460;
      }
      v47 = *v30;
      if ( v20 > 0 )
        v20 = (unsigned __int16)v20 | 0x80070000;
      v32 = L"base\\stor\\vss\\inc\\ichannel.hxx";
      v33 = L"CVssIOCTLChannel::Call";
      v34 = L"INCICHLH";
      v35 = 521;
      v36 = 2;
      v37 = 255;
      v39 = 0x1000000;
      memset_0(v38, 0, sizeof(v38));
      LODWORD(lpOverlapped) = a3;
      CVssFunctionTracer::TranslateInternalProviderError(
        a2,
        &v32,
        (unsigned int)v20,
        2147754758LL,
        L"DeviceIoControl(%s - %p,0x%08lx,%p,%d,%p,%d,[%d])",
        a1[13],
        *a1,
        lpOverlapped,
        a1[7],
        0,
        v47,
        *((_DWORD *)a1 + 17),
        *((_DWORD *)a1 + 18));
    }
    v32 = L"base\\stor\\vss\\inc\\ichannel.hxx";
    v33 = L"CVssIOCTLChannel::Call";
    v34 = L"INCICHLH";
    v35 = 544;
    v36 = 10;
    v37 = 255;
    v39 = 0x1000000;
    memset_0(v38, 0, sizeof(v38));
    LODWORD(lpBytesReturned) = v20;
    CVssFunctionTracer::Trace(
      a2,
      &v32,
      L"IOCTL %lx failed on device %s - 0x%08lx. Error code = 0x%08lx",
      a3,
      a1[13],
      *a1,
      lpBytesReturned);
    if ( v20 > 0 )
      v20 = (unsigned __int16)v20 | 0x80070000;
  }
  *(_DWORD *)(a2 + 8) = v20;
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180003de8  mov     [rsp-8+arg_18], r9b
0x180003ded  mov     [rsp-8+dwIoControlCode], r8d
0x180003df2  mov     [rsp-8+arg_8], rdx
0x180003df7  push    rbp
0x180003df8  push    rbx
0x180003df9  push    rsi
0x180003dfa  push    rdi
0x180003dfb  push    r12
0x180003dfd  push    r13
0x180003dff  push    r14
0x180003e01  push    r15
0x180003e03  lea     rbp, [rsp-48h]
0x180003e08  sub     rsp, 148h
0x180003e0f  xor     r10d, r10d
0x180003e12  mov     rdi, rdx
0x180003e15  mov     [rdx+8], r10d
0x180003e19  mov     rbx, rcx
0x180003e1c  cmp     [rcx], r10
0x180003e1f  jnz     short loc_180003E94
0x180003e21  mov     [rcx+2Ch], r10d
0x180003e25  lea     rsi, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x180003e2c  mov     [rcx+40h], r10d
0x180003e30  lea     r14, aCvssioctlchann_2; "CVssIOCTLChannel::Call"
0x180003e37  lea     r15, aIncichlh; "INCICHLH"
0x180003e3e  mov     [rsp+180h+var_108], rsi
0x180003e43  mov     r12d, 0FFh
0x180003e49  mov     [rbp+80h+var_100], r14
0x180003e4d  lea     rcx, [rbp+80h+var_E0]; void *
0x180003e51  mov     [rbp+80h+var_F8], r15
0x180003e55  xor     edx, edx; Val
0x180003e57  mov     [rbp+80h+var_E8], r12d
0x180003e5b  lea     r8d, [r10+78h]; Size
0x180003e5f  mov     [rbp+80h+var_F0], 17Dh
0x180003e66  mov     [rbp+80h+var_EC], 0Ah
0x180003e6d  mov     [rbp+80h+var_68], 1000000h
0x180003e74  call    memset_0
0x180003e79  lea     r9, aChannelNotOpen; "Channel not open"
0x180003e80  mov     r8d, 8000FFFFh
0x180003e86  lea     rdx, [rsp+180h+var_108]
0x180003e8b  mov     rcx, rdi
0x180003e8e  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x180003e94  cmp     [rcx+29h], r10b
0x180003e98  jz      short loc_180003F05
0x180003e9a  xor     edx, edx; Val
0x180003e9c  mov     [rbp+80h+var_F0], 182h
0x180003ea3  lea     rsi, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x180003eaa  mov     [rbp+80h+var_EC], 0Ah
0x180003eb1  lea     r14, aCvssioctlchann_2; "CVssIOCTLChannel::Call"
0x180003eb8  mov     [rsp+180h+var_108], rsi
0x180003ebd  lea     r15, aIncichlh; "INCICHLH"
0x180003ec4  mov     [rbp+80h+var_100], r14
0x180003ec8  mov     r12d, 0FFh
0x180003ece  mov     [rbp+80h+var_F8], r15
0x180003ed2  lea     r8d, [rdx+78h]; Size
0x180003ed6  mov     [rbp+80h+var_E8], r12d
0x180003eda  lea     rcx, [rbp+80h+var_E0]; void *
0x180003ede  mov     [rbp+80h+var_68], 1000000h
0x180003ee5  call    memset_0
0x180003eea  lea     r9, aPreviousIoctlH; "previous IOCTL hasn't yet completed"
0x180003ef1  mov     r8d, 80070057h
0x180003ef7  lea     rdx, [rsp+180h+var_108]
0x180003efc  mov     rcx, rdi
0x180003eff  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180003f05  lea     rax, [rcx+48h]
0x180003f09  mov     [rcx+40h], r10d
0x180003f0d  mov     [rbp+80h+var_58], rax
0x180003f11  mov     [rax], r10d
0x180003f14  cmp     [rbp+80h+arg_28], r10b
0x180003f1b  jz      loc_180003FC6
0x180003f21  mov     rcx, [rcx+20h]; hEvent
0x180003f25  mov     [rbx+8], r10
0x180003f29  mov     [rbx+10h], r10
0x180003f2d  mov     [rbx+18h], r10
0x180003f31  mov     [rbx+20h], rcx
0x180003f35  mov     byte ptr [rbx+29h], 1
0x180003f39  test    rcx, rcx
0x180003f3c  jnz     loc_180004032
0x180003f42  xor     r9d, r9d; lpName
0x180003f45  lea     edx, [rcx+1]; bManualReset
0x180003f48  xor     r8d, r8d; bInitialState
0x180003f4b  call    cs:__imp_CreateEventW
0x180003f51  xor     r10d, r10d
0x180003f54  mov     [rbx+20h], rax
0x180003f58  test    rax, rax
0x180003f5b  jnz     short loc_180003FC2
0x180003f5d  lea     rsi, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x180003f64  mov     [rbp+80h+var_F0], 197h
0x180003f6b  lea     r14, aCvssioctlchann_2; "CVssIOCTLChannel::Call"
0x180003f72  mov     [rsp+180h+var_108], rsi
0x180003f77  lea     r15, aIncichlh; "INCICHLH"
0x180003f7e  mov     [rbp+80h+var_100], r14
0x180003f82  mov     r12d, 0FFh
0x180003f88  mov     [rbp+80h+var_F8], r15
0x180003f8c  xor     edx, edx; Val
0x180003f8e  mov     [rbp+80h+var_E8], r12d
0x180003f92  lea     r8d, [rax+78h]; Size
0x180003f96  mov     [rbp+80h+var_EC], 0Ah
0x180003f9d  lea     rcx, [rbp+80h+var_E0]; void *
0x180003fa1  mov     [rbp+80h+var_68], 1000000h
0x180003fa8  call    memset_0
0x180003fad  lea     r8, aCreateeventNul; "CreateEvent(NULL, TRUE, FALSE, NULL)"
0x180003fb4  mov     rcx, rdi
0x180003fb7  lea     rdx, [rsp+180h+var_108]
0x180003fbc  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x180003fc2  mov     byte ptr [rbx+28h], 1
0x180003fc6  mov     ecx, [rbx+44h]
0x180003fc9  lea     r9, [rbx+50h]
0x180003fcd  mov     edi, 0Ah
0x180003fd2  lea     rsi, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x180003fd9  mov     eax, r10d
0x180003fdc  lea     r14, aCvssioctlchann_2; "CVssIOCTLChannel::Call"
0x180003fe3  mov     rdx, r9
0x180003fe6  lea     r15, aIncichlh; "INCICHLH"
0x180003fed  mov     r12d, 0FFh
0x180003ff3  lea     r13d, [rdi+6Eh]
0x180003ff7  mov     dword ptr [rbp+80h+arg_0], ecx
0x180003ffd  mov     r8d, ecx
0x180004000  mov     dword ptr [rbp+80h+arg_30], eax
0x180004006  test    eax, eax
0x180004008  jnz     loc_1800040A4
0x18000400e  test    ecx, ecx
0x180004010  jnz     loc_1800040AD
0x180004016  mov     eax, 1000h
0x18000401b  mov     [rbp+80h+var_60], rdx
0x18000401f  mov     dword ptr [rbp+80h+arg_30], eax
0x180004025  mov     rcx, rdx
0x180004028  mov     [rsp+180h+var_110], rdx
0x18000402d  jmp     loc_1800040BE
0x180004032  call    cs:__imp_ResetEvent
0x180004038  xor     r10d, r10d
0x18000403b  test    eax, eax
0x18000403d  jnz     short loc_180003FC6
0x18000403f  lea     rsi, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x180004046  mov     [rbp+80h+var_F0], 1A2h
0x18000404d  lea     r14, aCvssioctlchann_2; "CVssIOCTLChannel::Call"
0x180004054  mov     [rsp+180h+var_108], rsi
0x180004059  lea     r15, aIncichlh; "INCICHLH"
0x180004060  mov     [rbp+80h+var_100], r14
0x180004064  mov     r12d, 0FFh
0x18000406a  mov     [rbp+80h+var_F8], r15
0x18000406e  xor     edx, edx; Val
0x180004070  mov     [rbp+80h+var_E8], r12d
0x180004074  lea     r8d, [r10+78h]; Size
0x180004078  mov     [rbp+80h+var_EC], 0Ah
0x18000407f  lea     rcx, [rbp+80h+var_E0]; void *
0x180004083  mov     [rbp+80h+var_68], 1000000h
0x18000408a  call    memset_0
0x18000408f  lea     r8, aReseteventMOve; "ResetEvent(m_overlapped.hEvent)"
0x180004096  mov     rcx, rdi
0x180004099  lea     rdx, [rsp+180h+var_108]
0x18000409e  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x1800040a4  mov     r8d, ecx
0x1800040a7  mov     dword ptr [rbp+80h+arg_0], ecx
0x1800040ad  mov     rcx, r9
0x1800040b0  mov     [rbp+80h+var_60], rcx
0x1800040b4  mov     [rsp+180h+var_110], rcx
0x1800040b9  cmp     eax, r8d
0x1800040bc  jbe     short loc_1800040EE
0x1800040be  mov     rcx, [rcx]
0x1800040c1  mov     edx, eax
0x1800040c3  call    cs:__imp__o_realloc
0x1800040c9  xor     r10d, r10d
0x1800040cc  mov     rcx, rax
0x1800040cf  test    rax, rax
0x1800040d2  jz      loc_180004243
0x1800040d8  mov     rax, [rbp+80h+var_60]
0x1800040dc  mov     [rax], rcx
0x1800040df  mov     eax, dword ptr [rbp+80h+arg_30]
0x1800040e5  mov     [rbx+44h], eax
0x1800040e8  mov     dword ptr [rbp+80h+arg_0], eax
0x1800040ee  mov     r8, r13; Size
0x1800040f1  mov     [rsp+180h+var_108], rsi
0x1800040f6  xor     edx, edx; Val
0x1800040f8  mov     [rbp+80h+var_100], r14
0x1800040fc  lea     rcx, [rbp+80h+var_E0]; void *
0x180004100  mov     [rbp+80h+var_F8], r15
0x180004104  mov     [rbp+80h+var_F0], 1C3h
0x18000410b  mov     [rbp+80h+var_EC], edi
0x18000410e  mov     [rbp+80h+var_E8], r12d
0x180004112  mov     [rbp+80h+var_68], 1000000h
0x180004119  call    memset_0
0x18000411e  mov     eax, 0Fh
0x180004123  mov     ecx, 0FFFFh
0x180004128  add     ax, cx
0x18000412b  jnz     short loc_180004128
0x18000412d  mov     eax, dword ptr [rbp+80h+arg_0]
0x180004133  lea     r8, aIoctlSentLxOnD; "IOCTL sent: %lx on device %s\n Input bu"...
0x18000413a  mov     r9d, [rbp+80h+dwIoControlCode]
0x180004141  lea     rdx, [rsp+180h+var_108]
0x180004146  mov     rcx, [rbp+80h+arg_8]
0x18000414d  mov     dword ptr [rsp+180h+lpBytesReturned], eax
0x180004151  mov     eax, [rbx+2Ch]
0x180004154  mov     [rsp+180h+nOutBufferSize], eax
0x180004158  mov     rax, [rbx+68h]
0x18000415c  mov     [rsp+180h+lpOutBuffer], rax
0x180004161  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180004166  mov     r8, r13; Size
0x180004169  mov     [rsp+180h+var_108], rsi
0x18000416e  xor     edx, edx; Val
0x180004170  mov     [rbp+80h+var_100], r14
0x180004174  lea     rcx, [rbp+80h+var_E0]; void *
0x180004178  mov     [rbp+80h+var_F8], r15
0x18000417c  mov     [rbp+80h+var_F0], 1C5h
0x180004183  mov     [rbp+80h+var_EC], edi
0x180004186  mov     [rbp+80h+var_E8], r12d
0x18000418a  mov     [rbp+80h+var_68], 1000000h
0x180004191  call    memset_0
0x180004196  mov     eax, 0Fh
0x18000419b  mov     ecx, 0FFFFh
0x1800041a0  add     ax, cx
0x1800041a3  jnz     short loc_1800041A0
0x1800041a5  mov     r9, [rbx+38h]
0x1800041a9  lea     rdx, [rsp+180h+var_108]
0x1800041ae  mov     r8d, [rbx+2Ch]
0x1800041b2  mov     rcx, [rbp+80h+arg_8]
0x1800041b9  call    ?TraceBuffer@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@KPEAE@Z; CVssFunctionTracer::TraceBuffer(CVssDebugInfo,ulong,uchar *)
0x1800041be  mov     al, [rbp+80h+arg_28]
0x1800041c4  lea     rdx, [rbx+8]
0x1800041c8  mov     r9d, [rbx+2Ch]; nInBufferSize
0x1800041cc  neg     al
0x1800041ce  mov     r8, [rbx+38h]; lpInBuffer
0x1800041d2  lea     rax, [rbx+48h]
0x1800041d6  sbb     rcx, rcx
0x1800041d9  and     rcx, rdx
0x1800041dc  mov     edx, [rbp+80h+dwIoControlCode]; dwIoControlCode
0x1800041e2  mov     [rsp+180h+lpOverlapped], rcx; lpOverlapped
0x1800041e7  mov     rcx, [rbx]; hDevice
0x1800041ea  mov     [rsp+180h+lpBytesReturned], rax; lpBytesReturned
0x1800041ef  mov     eax, [rbx+44h]
0x1800041f2  mov     [rsp+180h+nOutBufferSize], eax; nOutBufferSize
0x1800041f6  mov     rax, [rsp+180h+var_110]
0x1800041fb  mov     rax, [rax]
0x1800041fe  mov     [rsp+180h+lpOutBuffer], rax; lpOutBuffer
0x180004203  call    cs:__imp_DeviceIoControl
0x180004209  mov     dword ptr [rbp+80h+arg_0], eax
0x18000420f  test    eax, eax
0x180004211  jnz     loc_18000429A
0x180004217  call    cs:__imp_GetLastError
0x18000421d  cmp     eax, 7Ah ; 'z'
0x180004220  jz      short loc_18000422F
0x180004222  call    cs:__imp_GetLastError
0x180004228  cmp     eax, 0EAh
0x18000422d  jnz     short loc_18000429A
0x18000422f  mov     ecx, [rbx+44h]
0x180004232  lea     r9, [rbx+50h]
0x180004236  mov     rdx, [rsp+180h+var_110]
0x18000423b  lea     eax, [rcx+rcx]
0x18000423e  jmp     loc_180003FF7
0x180004243  mov     r8, r13; Size
0x180004246  mov     [rbx+2Ch], r10d
0x18000424a  xor     edx, edx; Val
0x18000424c  mov     [rbx+40h], r10d
0x180004250  lea     rcx, [rbp+80h+var_E0]; void *
0x180004254  mov     [rsp+180h+var_108], rsi
0x180004259  mov     [rbp+80h+var_100], r14
0x18000425d  mov     [rbp+80h+var_F8], r15
0x180004261  mov     [rbp+80h+var_F0], 1BAh
0x180004268  mov     [rbp+80h+var_EC], edi
0x18000426b  mov     [rbp+80h+var_E8], r12d
0x18000426f  mov     [rbp+80h+var_68], 1000000h
0x180004276  call    memset_0
0x18000427b  mov     rcx, [rbp+80h+arg_8]
0x180004282  lea     r9, aCouldNotExtend; "Could not extend the output buffer"
0x180004289  mov     r8d, 8007000Eh
0x18000428f  lea     rdx, [rsp+180h+var_108]
0x180004294  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18000429a  call    cs:__imp_GetLastError
0x1800042a0  xor     r8d, r8d
0x1800042a3  mov     edi, eax
0x1800042a5  mov     [rbx+2Ch], r8d
0x1800042a9  mov     [rbx+40h], r8d
0x1800042ad  cmp     dword ptr [rbp+80h+arg_0], r8d
0x1800042b4  jnz     loc_18000474A
0x1800042ba  cmp     [rbp+80h+arg_28], r8b
0x1800042c1  jz      short loc_1800042CE
0x1800042c3  cmp     eax, 3E5h
0x1800042c8  jz      loc_18000474A
0x1800042ce  cmp     [rbp+80h+arg_18], r8b
0x1800042d5  jz      loc_1800046CC
0x1800042db  mov     edx, [rbp+80h+arg_20]
0x1800042e1  mov     ecx, edx
0x1800042e3  test    edx, edx
0x1800042e5  jz      loc_18000465A
0x1800042eb  sub     ecx, 1
0x1800042ee  jz      loc_1800045A8
0x1800042f4  sub     ecx, 1
0x1800042f7  jz      loc_1800044EB
0x1800042fd  sub     ecx, 1
0x180004300  jz      loc_1800044E0
0x180004306  sub     ecx, 1
0x180004309  jz      loc_18000440C
0x18000430f  sub     ecx, 1
0x180004312  jz      short loc_18000431D
0x180004314  cmp     ecx, 1
0x180004317  jnz     loc_18000465A
0x18000431d  mov     eax, [rbx+48h]
0x180004320  cmp     edx, 5
0x180004323  mov     dword ptr [rbp+80h+arg_0], eax
0x180004329  mov     eax, [rbx+44h]
0x18000432c  mov     dword ptr [rbp+80h+arg_30], eax
  ... truncated ...
```
