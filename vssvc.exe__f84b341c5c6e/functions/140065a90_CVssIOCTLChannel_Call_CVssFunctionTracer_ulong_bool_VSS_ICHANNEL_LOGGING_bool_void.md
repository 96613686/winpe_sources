# CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)

- ea: `0x140065a90`
- end: `0x140066497`
- name: `?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z`
- size: `2567`
- prototype: ``
- caller_count: `47`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14000a988`
- `0x14004229c`
- `0x14004c29c`
- `0x14005c4fc`
- `0x140060e40`
- `0x1400638d4`
- `0x140063f60`
- `0x1400664a0`
- `0x140067084`
- `0x140067464`
- `0x14006816c`
- `0x140068514`
- `0x14006871c`
- `0x14006911c`
- `0x140069564`
- `0x1400699d8`
- `0x14006ac58`
- `0x14006fbac`
- `0x140073c2c`
- `0x140074528`
- `0x140075294`
- `0x140077018`
- `0x140077a2c`
- `0x14007a590`
- `0x14007a974`
- `0x14007b750`
- `0x14007bd44`
- `0x14007c240`
- `0x14007c688`
- `0x14007c81c`
- `0x14007cb74`
- `0x14007cd08`
- `0x14007cf8c`
- `0x14007d6fc`
- `0x14007de48`
- `0x14007e6c4`
- `0x14008a2f0`
- `0x14008de40`
- `0x14008fffc`
- `0x1400901e4`
- `0x14009bcf8`
- `0x1400a1a6c`
- `0x1400bf9fc`
- `0x1400c4d6c`
- `0x1400c5028`
- `0x1400cb0f0`
- `0x1400d1cd8`

## callees

- `0x1400139c0`
- `0x140015e38`
- `0x140028b48`
- `0x140049ec4`
- `0x140065a90`
- `0x140067af4`
- `0x1400921dc`
- `0x1400cdf20`
- `0x1400ce338`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x140065d63`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x140065d63`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140065ce5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140065ce5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140065bff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140065bff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065e9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065ea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065f24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065e9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065ea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065f24`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140065e88`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140065e88`

## string_xrefs

- `0x140065c60`: `CreateEvent(NULL, TRUE, FALSE, NULL)`
- `0x140065b20`: `Channel not open`
- `0x140065b8f`: `previous IOCTL hasn't yet completed`

## pseudocode

```c
__int64 __fastcall CVssIOCTLChannel::Call(_QWORD *a1, __int64 a2, DWORD a3, char a4, int a5, char a6, __int64 a7)
{
  void *v9; // rcx
  HANDLE EventW; // rax
  unsigned int v11; // edx
  LPVOID *v12; // r8
  char *v13; // r9
  LPVOID *v14; // rax
  unsigned int i; // ecx
  __int64 v16; // rax
  _DWORD *v17; // rax
  signed int LastError; // edi
  _DWORD *v19; // rax
  int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rax
  LPVOID lpOutBuffer; // [rsp+20h] [rbp-E0h]
  DWORD nOutBufferSize[2]; // [rsp+28h] [rbp-D8h]
  HANDLE nOutBufferSizea; // [rsp+28h] [rbp-D8h]
  HANDLE nOutBufferSizeb; // [rsp+28h] [rbp-D8h]
  LPDWORD lpBytesReturned; // [rsp+30h] [rbp-D0h]
  LPOVERLAPPED lpOverlapped; // [rsp+38h] [rbp-C8h]
  LPVOID *v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+70h] [rbp-90h]
  int v33; // [rsp+78h] [rbp-88h]
  int v34; // [rsp+78h] [rbp-88h]
  const wchar_t *v35; // [rsp+80h] [rbp-80h] BYREF
  const wchar_t *v36; // [rsp+88h] [rbp-78h]
  const wchar_t *v37; // [rsp+90h] [rbp-70h]
  int v38; // [rsp+98h] [rbp-68h]
  int v39; // [rsp+9Ch] [rbp-64h]
  int v40; // [rsp+A0h] [rbp-60h]
  _BYTE v41[120]; // [rsp+A8h] [rbp-58h] BYREF
  int v42; // [rsp+120h] [rbp+20h]
  _DWORD *v43; // [rsp+128h] [rbp+28h]
  unsigned int *v44; // [rsp+130h] [rbp+30h]
  HANDLE v45; // [rsp+140h] [rbp+40h]
  int v46; // [rsp+1A0h] [rbp+A0h]
  BOOL v47; // [rsp+1A0h] [rbp+A0h]
  int v48; // [rsp+1A0h] [rbp+A0h]
  unsigned int v49; // [rsp+1A0h] [rbp+A0h]
  LPVOID v50; // [rsp+1A0h] [rbp+A0h]
  LPVOID v51; // [rsp+1A0h] [rbp+A0h]

  *(_DWORD *)(a2 + 8) = 0;
  if ( !*a1 )
  {
    *((_DWORD *)a1 + 11) = 0;
    *((_DWORD *)a1 + 16) = 0;
    v35 = L"base\\stor\\vss\\inc\\ichannel.hxx";
    v36 = L"CVssIOCTLChannel::Call";
    v37 = L"INCICHLH";
    v40 = 255;
    v38 = 381;
    v39 = 10;
    v42 = 0x1000000;
    memset_0(v41, 0, sizeof(v41));
    CVssFunctionTracer::TranslateGenericError(a2, &v35, 2147549183LL, L"Channel not open");
  }
  if ( *((_BYTE *)a1 + 41) )
  {
    v38 = 386;
    v39 = 10;
    v35 = L"base\\stor\\vss\\inc\\ichannel.hxx";
    v36 = L"CVssIOCTLChannel::Call";
    v37 = L"INCICHLH";
    v40 = 255;
    v42 = 0x1000000;
    memset_0(v41, 0, sizeof(v41));
    CVssFunctionTracer::Throw(a2, &v35, 2147942487LL, L"previous IOCTL hasn't yet completed");
  }
  *((_DWORD *)a1 + 16) = 0;
  v44 = (unsigned int *)(a1 + 9);
  *((_DWORD *)a1 + 18) = 0;
  if ( a6 )
  {
    v9 = (void *)a1[4];
    a1[1] = 0;
    a1[2] = 0;
    a1[3] = 0;
    a1[4] = v9;
    *((_BYTE *)a1 + 41) = 1;
    if ( v9 )
    {
      if ( !ResetEvent(v9) )
      {
        v38 = 418;
        v35 = L"base\\stor\\vss\\inc\\ichannel.hxx";
        v36 = L"CVssIOCTLChannel::Call";
        v37 = L"INCICHLH";
        v40 = 255;
        v39 = 10;
        v42 = 0x1000000;
        memset_0(v41, 0, sizeof(v41));
        CVssFunctionTracer::TranslateWin32Error(a2, &v35, L"ResetEvent(m_overlapped.hEvent)");
      }
    }
    else if ( a7 )
    {
      a1[4] = a7;
    }
    else
    {
      EventW = CreateEventW(0, 1, 0, 0);
      a1[4] = EventW;
      if ( !EventW )
      {
        v38 = 407;
        v35 = L"base\\stor\\vss\\inc\\ichannel.hxx";
        v36 = L"CVssIOCTLChannel::Call";
        v37 = L"INCICHLH";
        v40 = 255;
        v39 = 10;
        v42 = 0x1000000;
        memset_0(v41, 0, sizeof(v41));
        CVssFunctionTracer::TranslateWin32Error(a2, &v35, L"CreateEvent(NULL, TRUE, FALSE, NULL)");
      }
      *((_BYTE *)a1 + 40) = 1;
    }
  }
  v11 = *((_DWORD *)a1 + 17);
  v12 = (LPVOID *)(a1 + 10);
  v13 = (char *)a1 + 44;
  v14 = (LPVOID *)(a1 + 10);
  v43 = (_DWORD *)a1 + 11;
  for ( i = 0; ; i = 2 * v11 )
  {
    v46 = v11;
    v33 = i;
    if ( i )
    {
      v31 = v14;
LABEL_19:
      if ( i <= v11 )
        goto LABEL_22;
      goto LABEL_20;
    }
    v43 = v13;
    v14 = v12;
    v31 = v12;
    if ( v11 )
      goto LABEL_19;
    i = 4096;
    v33 = 4096;
LABEL_20:
    v16 = _o_realloc(*v14, i);
    if ( !v16 )
    {
      v17 = v43;
      *((_DWORD *)a1 + 16) = 0;
      v35 = L"base\\stor\\vss\\inc\\ichannel.hxx";
      v36 = L"CVssIOCTLChannel::Call";
      *v17 = 0;
      v37 = L"INCICHLH";
      v38 = 442;
      v39 = 10;
      v40 = 255;
      v42 = 0x1000000;
      memset_0(v41, 0, sizeof(v41));
      CVssFunctionTracer::Throw(a2, &v35, 2147942414LL, L"Could not extend the output buffer");
    }
    *v31 = (LPVOID)v16;
    *((_DWORD *)a1 + 17) = v33;
    v46 = v33;
LABEL_22:
    v35 = L"base\\stor\\vss\\inc\\ichannel.hxx";
    v43 = (_DWORD *)a1 + 11;
    v36 = L"CVssIOCTLChannel::Call";
    v37 = L"INCICHLH";
    v38 = 451;
    v39 = 10;
    v40 = 255;
    v42 = 0x1000000;
    memset_0(v41, 0, sizeof(v41));
    LODWORD(lpBytesReturned) = v46;
    nOutBufferSize[0] = *((_DWORD *)a1 + 11);
    CVssFunctionTracer::Trace(
      a2,
      &v35,
      L"IOCTL sent: %lx on device %s\n Input buffer size: %ld, Output buffer size: %ld",
      a3,
      a1[13],
      *(_QWORD *)nOutBufferSize,
      lpBytesReturned);
    v35 = L"base\\stor\\vss\\inc\\ichannel.hxx";
    v36 = L"CVssIOCTLChannel::Call";
    v37 = L"INCICHLH";
    v38 = 453;
    v39 = 10;
    v40 = 255;
    v42 = 0x1000000;
    memset_0(v41, 0, sizeof(v41));
    CVssFunctionTracer::TraceBuffer(a2, &v35, *((unsigned int *)a1 + 11), a1[7]);
    v47 = DeviceIoControl(
            (HANDLE)*a1,
            a3,
            (LPVOID)a1[7],
            *((_DWORD *)a1 + 11),
            *v31,
            *((_DWORD *)a1 + 17),
            (LPDWORD)a1 + 18,
            (LPOVERLAPPED)((unsigned __int64)(a1 + 1) & -(__int64)(a6 != 0)));
    if ( v47 || GetLastError() != 122 && GetLastError() != 234 )
      break;
    v11 = *((_DWORD *)a1 + 17);
    v12 = (LPVOID *)(a1 + 10);
    v14 = v31;
    v13 = (char *)a1 + 44;
  }
  LastError = GetLastError();
  v19 = v43;
  *((_DWORD *)a1 + 16) = 0;
  *v19 = 0;
  if ( v47 || a6 && LastError == 997 )
  {
    v35 = L"base\\stor\\vss\\inc\\ichannel.hxx";
    v39 = 10;
    v36 = L"CVssIOCTLChannel::Call";
    v37 = L"INCICHLH";
    v38 = 549;
    v40 = 255;
    v42 = 0x1000000;
    memset_0(v41, 0, sizeof(v41));
    LODWORD(lpBytesReturned) = *((_DWORD *)a1 + 18);
    nOutBufferSizeb = (HANDLE)*a1;
    v23 = a1[13];
    v22 = a2;
    CVssFunctionTracer::Trace(
      a2,
      &v35,
      L"IOCTL %lx succeeded on device %s - 0x%08lx. \n Output buffer: size received = %ld",
      a3,
      v23,
      nOutBufferSizeb,
      lpBytesReturned);
    v35 = L"base\\stor\\vss\\inc\\ichannel.hxx";
    v36 = L"CVssIOCTLChannel::Call";
    v37 = L"INCICHLH";
    v38 = 551;
    v39 = 10;
    v40 = 255;
    v42 = 0x1000000;
    memset_0(v41, 0, sizeof(v41));
    CVssFunctionTracer::TraceBuffer(a2, &v35, *v44, *v31);
    LastError = 0;
  }
  else
  {
    if ( a4 )
    {
      if ( !a5 )
        goto LABEL_53;
      if ( a5 == 1 )
      {
        v51 = *v31;
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v35 = L"base\\stor\\vss\\inc\\ichannel.hxx";
        v36 = L"CVssIOCTLChannel::Call";
        v37 = L"INCICHLH";
        v38 = 496;
        v39 = 1;
        v40 = 255;
        v42 = 0x1000000;
        memset_0(v41, 0, sizeof(v41));
        LODWORD(lpBytesReturned) = a3;
        CVssFunctionTracer::TranslateGenericError(
          a2,
          &v35,
          (unsigned int)LastError,
          L"DeviceIoControl(%s - %p,0x%08lx,%p,%d,%p,%d,[%d])",
          a1[13],
          *a1,
          lpBytesReturned,
          a1[7],
          0,
          v51,
          *((_DWORD *)a1 + 17),
          *((_DWORD *)a1 + 18));
      }
      if ( a5 != 2 )
      {
        if ( a5 != 3 )
        {
          if ( a5 == 4 )
          {
            v20 = -2147212536;
            if ( LastError != 87 )
              v20 = -2147212538;
            v49 = v20;
            v44 = (unsigned int *)*v31;
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            v35 = L"base\\stor\\vss\\inc\\ichannel.hxx";
            v36 = L"CVssIOCTLChannel::Call";
            v37 = L"INCICHLH";
            v38 = 534;
            v39 = 2;
            v40 = 255;
            v42 = 0x1000000;
            memset_0(v41, 0, sizeof(v41));
            LODWORD(lpOverlapped) = a3;
            CVssFunctionTracer::TranslateInternalProviderError(
              a2,
              &v35,
              (unsigned int)LastError,
              v49,
              L"DeviceIoControl(%s - %p,0x%08lx,%p,%d,%p,%d,[%d])",
              a1[13],
              *a1,
              lpOverlapped,
              a1[7],
              0,
              v44,
              *((_DWORD *)a1 + 17),
              *((_DWORD *)a1 + 18));
          }
          if ( (unsigned int)(a5 - 5) <= 1 )
          {
            v48 = *((_DWORD *)a1 + 18);
            v34 = *((_DWORD *)a1 + 17);
            v43 = *v31;
            v32 = a1[7];
            v45 = (HANDLE)*a1;
            v44 = (unsigned int *)a1[13];
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            v35 = L"base\\stor\\vss\\inc\\ichannel.hxx";
            v36 = L"CVssIOCTLChannel::Call";
            v37 = L"INCICHLH";
            v38 = 505;
            v39 = 1;
            v40 = 255;
            v42 = 0x1000000;
            memset_0(v41, 0, sizeof(v41));
            LODWORD(lpOverlapped) = a3;
            CVssFunctionTracer::TranslateInternalLovelaceError(
              a2,
              &v35,
              (unsigned int)LastError,
              a5 == 5,
              L"DeviceIoControl(%s - %p,0x%08lx,%p,%d,%p,%d,[%d])",
              v44,
              v45,
              lpOverlapped,
              v32,
              0,
              v43,
              v34,
              v48);
          }
LABEL_53:
          v35 = L"base\\stor\\vss\\inc\\ichannel.hxx";
          v36 = L"CVssIOCTLChannel::Call";
          v37 = L"INCICHLH";
          v38 = 490;
          v39 = 10;
          v40 = 255;
          v42 = 0x1000000;
          memset_0(v41, 0, sizeof(v41));
          LODWORD(lpOverlapped) = LastError;
          LODWORD(lpOutBuffer) = a3;
          CVssFunctionTracer::Throw(
            a2,
            &v35,
            2147549183LL,
            L"Could not send the IOCTL 0x%08lx on device %s - 0x%08lx. [0x%08lx]\n",
            lpOutBuffer,
            a1[13],
            *a1,
            lpOverlapped);
        }
        if ( LastError == 87 )
          LastError = 1460;
      }
      v50 = *v31;
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v35 = L"base\\stor\\vss\\inc\\ichannel.hxx";
      v36 = L"CVssIOCTLChannel::Call";
      v37 = L"INCICHLH";
      v38 = 521;
      v39 = 2;
      v40 = 255;
      v42 = 0x1000000;
      memset_0(v41, 0, sizeof(v41));
      LODWORD(lpOverlapped) = a3;
      CVssFunctionTracer::TranslateInternalProviderError(
        a2,
        &v35,
        (unsigned int)LastError,
        2147754758LL,
        L"DeviceIoControl(%s - %p,0x%08lx,%p,%d,%p,%d,[%d])",
        a1[13],
        *a1,
        lpOverlapped,
        a1[7],
        0,
        v50,
        *((_DWORD *)a1 + 17),
        *((_DWORD *)a1 + 18));
    }
    v35 = L"base\\stor\\vss\\inc\\ichannel.hxx";
    v36 = L"CVssIOCTLChannel::Call";
    v37 = L"INCICHLH";
    v38 = 544;
    v39 = 10;
    v40 = 255;
    v42 = 0x1000000;
    memset_0(v41, 0, sizeof(v41));
    LODWORD(lpBytesReturned) = LastError;
    nOutBufferSizea = (HANDLE)*a1;
    v21 = a1[13];
    v22 = a2;
    CVssFunctionTracer::Trace(
      a2,
      &v35,
      L"IOCTL %lx failed on device %s - 0x%08lx. Error code = 0x%08lx",
      a3,
      v21,
      nOutBufferSizea,
      lpBytesReturned);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
  }
  *(_DWORD *)(v22 + 8) = LastError;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140065a90  mov     [rsp-8+arg_18], r9b
0x140065a95  mov     [rsp-8+dwIoControlCode], r8d
0x140065a9a  mov     [rsp-8+arg_8], rdx
0x140065a9f  push    rbp
0x140065aa0  push    rbx
0x140065aa1  push    rsi
0x140065aa2  push    rdi
0x140065aa3  push    r12
0x140065aa5  push    r13
0x140065aa7  push    r14
0x140065aa9  push    r15
0x140065aab  lea     rbp, [rsp-58h]
0x140065ab0  sub     rsp, 158h
0x140065ab7  xor     r10d, r10d
0x140065aba  mov     rdi, rdx
0x140065abd  mov     [rdx+8], r10d
0x140065ac1  mov     rbx, rcx
0x140065ac4  cmp     [rcx], r10
0x140065ac7  jnz     short loc_140065B3A
0x140065ac9  mov     [rcx+2Ch], r10d
0x140065acd  lea     rsi, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x140065ad4  mov     [rcx+40h], r10d
0x140065ad8  lea     r14, aCvssioctlchann_1; "CVssIOCTLChannel::Call"
0x140065adf  lea     r15, aIncichlh; "INCICHLH"
0x140065ae6  mov     [rbp+90h+var_110], rsi
0x140065aea  mov     r12d, 0FFh
0x140065af0  mov     [rbp+90h+var_108], r14
0x140065af4  lea     rcx, [rbp+90h+var_E8]; void *
0x140065af8  mov     [rbp+90h+var_100], r15
0x140065afc  xor     edx, edx; Val
0x140065afe  mov     [rbp+90h+var_F0], r12d
0x140065b02  lea     r8d, [r10+78h]; Size
0x140065b06  mov     [rbp+90h+var_F8], 17Dh
0x140065b0d  mov     [rbp+90h+var_F4], 0Ah
0x140065b14  mov     [rbp+90h+var_70], 1000000h
0x140065b1b  call    memset_0
0x140065b20  lea     r9, aChannelNotOpen; "Channel not open"
0x140065b27  mov     r8d, 8000FFFFh
0x140065b2d  lea     rdx, [rbp+90h+var_110]
0x140065b31  mov     rcx, rdi
0x140065b34  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x140065b3a  cmp     [rcx+29h], r10b
0x140065b3e  jz      short loc_140065BA9
0x140065b40  xor     edx, edx; Val
0x140065b42  mov     [rbp+90h+var_F8], 182h
0x140065b49  lea     rsi, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x140065b50  mov     [rbp+90h+var_F4], 0Ah
0x140065b57  lea     r14, aCvssioctlchann_1; "CVssIOCTLChannel::Call"
0x140065b5e  mov     [rbp+90h+var_110], rsi
0x140065b62  lea     r15, aIncichlh; "INCICHLH"
0x140065b69  mov     [rbp+90h+var_108], r14
0x140065b6d  mov     r12d, 0FFh
0x140065b73  mov     [rbp+90h+var_100], r15
0x140065b77  lea     r8d, [rdx+78h]; Size
0x140065b7b  mov     [rbp+90h+var_F0], r12d
0x140065b7f  lea     rcx, [rbp+90h+var_E8]; void *
0x140065b83  mov     [rbp+90h+var_70], 1000000h
0x140065b8a  call    memset_0
0x140065b8f  lea     r9, aPreviousIoctlH; "previous IOCTL hasn't yet completed"
0x140065b96  mov     r8d, 80070057h
0x140065b9c  lea     rdx, [rbp+90h+var_110]
0x140065ba0  mov     rcx, rdi
0x140065ba3  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140065ba9  lea     rax, [rcx+48h]
0x140065bad  mov     [rcx+40h], r10d
0x140065bb1  mov     [rbp+90h+var_60], rax
0x140065bb5  mov     [rax], r10d
0x140065bb8  cmp     [rbp+90h+arg_28], r10b
0x140065bbf  jz      loc_140065C78
0x140065bc5  mov     rcx, [rcx+20h]; hEvent
0x140065bc9  mov     [rbx+8], r10
0x140065bcd  mov     [rbx+10h], r10
0x140065bd1  mov     [rbx+18h], r10
0x140065bd5  mov     [rbx+20h], rcx
0x140065bd9  mov     byte ptr [rbx+29h], 1
0x140065bdd  test    rcx, rcx
0x140065be0  jnz     loc_140065CE5
0x140065be6  mov     rax, [rbp+90h+arg_30]
0x140065bed  test    rax, rax
0x140065bf0  jnz     loc_140065CDF
0x140065bf6  xor     r9d, r9d; lpName
0x140065bf9  lea     edx, [rcx+1]; bManualReset
0x140065bfc  xor     r8d, r8d; bInitialState
0x140065bff  call    cs:__imp_CreateEventW
0x140065c05  xor     r10d, r10d
0x140065c08  mov     [rbx+20h], rax
0x140065c0c  test    rax, rax
0x140065c0f  jnz     short loc_140065C74
0x140065c11  lea     rsi, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x140065c18  mov     [rbp+90h+var_F8], 197h
0x140065c1f  lea     r14, aCvssioctlchann_1; "CVssIOCTLChannel::Call"
0x140065c26  mov     [rbp+90h+var_110], rsi
0x140065c2a  lea     r15, aIncichlh; "INCICHLH"
0x140065c31  mov     [rbp+90h+var_108], r14
0x140065c35  mov     r12d, 0FFh
0x140065c3b  mov     [rbp+90h+var_100], r15
0x140065c3f  xor     edx, edx; Val
0x140065c41  mov     [rbp+90h+var_F0], r12d
0x140065c45  lea     r8d, [rax+78h]; Size
0x140065c49  mov     [rbp+90h+var_F4], 0Ah
0x140065c50  lea     rcx, [rbp+90h+var_E8]; void *
0x140065c54  mov     [rbp+90h+var_70], 1000000h
0x140065c5b  call    memset_0
0x140065c60  lea     r8, aCreateeventNul_1; "CreateEvent(NULL, TRUE, FALSE, NULL)"
0x140065c67  mov     rcx, rdi
0x140065c6a  lea     rdx, [rbp+90h+var_110]
0x140065c6e  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x140065c74  mov     byte ptr [rbx+28h], 1
0x140065c78  mov     edx, [rbx+44h]
0x140065c7b  lea     r8, [rbx+50h]
0x140065c7f  lea     r9, [rbx+2Ch]
0x140065c83  mov     rax, r8
0x140065c86  mov     [rbp+90h+var_68], r9
0x140065c8a  lea     rsi, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x140065c91  mov     ecx, r10d
0x140065c94  lea     r14, aCvssioctlchann_1; "CVssIOCTLChannel::Call"
0x140065c9b  lea     r15, aIncichlh; "INCICHLH"
0x140065ca2  mov     r12d, 0FFh
0x140065ca8  mov     r13d, 78h ; 'x'
0x140065cae  mov     dword ptr [rbp+90h+arg_0], edx
0x140065cb4  mov     [rsp+190h+var_118], ecx
0x140065cb8  test    ecx, ecx
0x140065cba  jnz     loc_140065D55
0x140065cc0  mov     [rbp+90h+var_68], r9
0x140065cc4  mov     rax, r8
0x140065cc7  mov     [rsp+190h+var_120], rax
0x140065ccc  test    edx, edx
0x140065cce  jnz     loc_140065D5A
0x140065cd4  mov     ecx, 1000h
0x140065cd9  mov     [rsp+190h+var_118], ecx
0x140065cdd  jmp     short loc_140065D5E
0x140065cdf  mov     [rbx+20h], rax
0x140065ce3  jmp     short loc_140065C78
0x140065ce5  call    cs:__imp_ResetEvent
0x140065ceb  xor     r10d, r10d
0x140065cee  test    eax, eax
0x140065cf0  jnz     short loc_140065C78
0x140065cf2  lea     rsi, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x140065cf9  mov     [rbp+90h+var_F8], 1A2h
0x140065d00  lea     r14, aCvssioctlchann_1; "CVssIOCTLChannel::Call"
0x140065d07  mov     [rbp+90h+var_110], rsi
0x140065d0b  lea     r15, aIncichlh; "INCICHLH"
0x140065d12  mov     [rbp+90h+var_108], r14
0x140065d16  mov     r12d, 0FFh
0x140065d1c  mov     [rbp+90h+var_100], r15
0x140065d20  xor     edx, edx; Val
0x140065d22  mov     [rbp+90h+var_F0], r12d
0x140065d26  lea     r8d, [r10+78h]; Size
0x140065d2a  mov     [rbp+90h+var_F4], 0Ah
0x140065d31  lea     rcx, [rbp+90h+var_E8]; void *
0x140065d35  mov     [rbp+90h+var_70], 1000000h
0x140065d3c  call    memset_0
0x140065d41  lea     r8, aReseteventMOve; "ResetEvent(m_overlapped.hEvent)"
0x140065d48  mov     rcx, rdi
0x140065d4b  lea     rdx, [rbp+90h+var_110]
0x140065d4f  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x140065d55  mov     [rsp+190h+var_120], rax
0x140065d5a  cmp     ecx, edx
0x140065d5c  jbe     short loc_140065D8D
0x140065d5e  mov     edx, ecx
0x140065d60  mov     rcx, [rax]
0x140065d63  call    cs:__imp__o_realloc
0x140065d69  xor     r10d, r10d
0x140065d6c  mov     rcx, rax
0x140065d6f  test    rax, rax
0x140065d72  jz      loc_140065ECC
0x140065d78  mov     rax, [rsp+190h+var_120]
0x140065d7d  mov     [rax], rcx
0x140065d80  mov     eax, [rsp+190h+var_118]
0x140065d84  mov     [rbx+44h], eax
0x140065d87  mov     dword ptr [rbp+90h+arg_0], eax
0x140065d8d  lea     rax, [rbx+2Ch]
0x140065d91  mov     [rbp+90h+var_110], rsi
0x140065d95  mov     r8, r13; Size
0x140065d98  mov     [rbp+90h+var_68], rax
0x140065d9c  xor     edx, edx; Val
0x140065d9e  mov     [rbp+90h+var_108], r14
0x140065da2  lea     rcx, [rbp+90h+var_E8]; void *
0x140065da6  mov     [rbp+90h+var_100], r15
0x140065daa  mov     [rbp+90h+var_F8], 1C3h
0x140065db1  mov     [rbp+90h+var_F4], 0Ah
0x140065db8  mov     [rbp+90h+var_F0], r12d
0x140065dbc  mov     [rbp+90h+var_70], 1000000h
0x140065dc3  call    memset_0
0x140065dc8  mov     eax, dword ptr [rbp+90h+arg_0]
0x140065dce  lea     r8, aIoctlSentLxOnD; "IOCTL sent: %lx on device %s\n Input bu"...
0x140065dd5  mov     r9d, [rbp+90h+dwIoControlCode]
0x140065ddc  lea     rdx, [rbp+90h+var_110]
0x140065de0  mov     dword ptr [rsp+190h+lpBytesReturned], eax
0x140065de4  mov     rcx, rdi
0x140065de7  mov     eax, [rbx+2Ch]
0x140065dea  mov     [rsp+190h+nOutBufferSize], eax
0x140065dee  mov     rax, [rbx+68h]
0x140065df2  mov     [rsp+190h+lpOutBuffer], rax
0x140065df7  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140065dfc  mov     r8, r13; Size
0x140065dff  mov     [rbp+90h+var_110], rsi
0x140065e03  xor     edx, edx; Val
0x140065e05  mov     [rbp+90h+var_108], r14
0x140065e09  lea     rcx, [rbp+90h+var_E8]; void *
0x140065e0d  mov     [rbp+90h+var_100], r15
0x140065e11  mov     [rbp+90h+var_F8], 1C5h
0x140065e18  mov     [rbp+90h+var_F4], 0Ah
0x140065e1f  mov     [rbp+90h+var_F0], r12d
0x140065e23  mov     [rbp+90h+var_70], 1000000h
0x140065e2a  call    memset_0
0x140065e2f  mov     r9, [rbx+38h]
0x140065e33  lea     rdx, [rbp+90h+var_110]
0x140065e37  mov     r8d, [rbx+2Ch]
0x140065e3b  mov     rcx, rdi
0x140065e3e  call    ?TraceBuffer@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@KPEAE@Z; CVssFunctionTracer::TraceBuffer(CVssDebugInfo,ulong,uchar *)
0x140065e43  mov     al, [rbp+90h+arg_28]
0x140065e49  lea     rdx, [rbx+8]
0x140065e4d  mov     r9d, [rbx+2Ch]; nInBufferSize
0x140065e51  neg     al
0x140065e53  mov     r8, [rbx+38h]; lpInBuffer
0x140065e57  lea     rax, [rbx+48h]
0x140065e5b  sbb     rcx, rcx
0x140065e5e  and     rcx, rdx
0x140065e61  mov     edx, [rbp+90h+dwIoControlCode]; dwIoControlCode
0x140065e67  mov     [rsp+190h+lpOverlapped], rcx; lpOverlapped
0x140065e6c  mov     rcx, [rbx]; hDevice
0x140065e6f  mov     [rsp+190h+lpBytesReturned], rax; lpBytesReturned
0x140065e74  mov     eax, [rbx+44h]
0x140065e77  mov     [rsp+190h+nOutBufferSize], eax; nOutBufferSize
0x140065e7b  mov     rax, [rsp+190h+var_120]
0x140065e80  mov     rax, [rax]
0x140065e83  mov     [rsp+190h+lpOutBuffer], rax; lpOutBuffer
0x140065e88  call    cs:__imp_DeviceIoControl
0x140065e8e  mov     dword ptr [rbp+90h+arg_0], eax
0x140065e94  test    eax, eax
0x140065e96  jnz     loc_140065F24
0x140065e9c  call    cs:__imp_GetLastError
0x140065ea2  cmp     eax, 7Ah ; 'z'
0x140065ea5  jz      short loc_140065EB4
0x140065ea7  call    cs:__imp_GetLastError
0x140065ead  cmp     eax, 0EAh
0x140065eb2  jnz     short loc_140065F24
0x140065eb4  mov     edx, [rbx+44h]
0x140065eb7  lea     r8, [rbx+50h]
0x140065ebb  mov     rax, [rsp+190h+var_120]
0x140065ec0  lea     r9, [rbx+2Ch]
0x140065ec4  lea     ecx, [rdx+rdx]
0x140065ec7  jmp     loc_140065CAE
0x140065ecc  mov     rax, [rbp+90h+var_68]
0x140065ed0  lea     rcx, [rbp+90h+var_E8]; void *
0x140065ed4  mov     r8, r13; Size
0x140065ed7  mov     [rbx+40h], r10d
0x140065edb  xor     edx, edx; Val
0x140065edd  mov     [rbp+90h+var_110], rsi
0x140065ee1  mov     [rbp+90h+var_108], r14
0x140065ee5  mov     [rax], r10d
0x140065ee8  mov     [rbp+90h+var_100], r15
0x140065eec  mov     [rbp+90h+var_F8], 1BAh
0x140065ef3  mov     [rbp+90h+var_F4], 0Ah
0x140065efa  mov     [rbp+90h+var_F0], r12d
0x140065efe  mov     [rbp+90h+var_70], 1000000h
0x140065f05  call    memset_0
0x140065f0a  lea     r9, aCouldNotExtend; "Could not extend the output buffer"
0x140065f11  mov     r8d, 8007000Eh
0x140065f17  lea     rdx, [rbp+90h+var_110]
0x140065f1b  mov     rcx, rdi
0x140065f1e  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140065f24  call    cs:__imp_GetLastError
0x140065f2a  xor     r8d, r8d
0x140065f2d  mov     edi, eax
0x140065f2f  mov     rax, [rbp+90h+var_68]
0x140065f33  mov     [rbx+40h], r8d
0x140065f37  mov     [rax], r8d
0x140065f3a  cmp     dword ptr [rbp+90h+arg_0], r8d
0x140065f41  jnz     loc_1400663C5
0x140065f47  cmp     [rbp+90h+arg_28], r8b
0x140065f4e  jz      short loc_140065F5C
0x140065f50  cmp     edi, 3E5h
0x140065f56  jz      loc_1400663C5
0x140065f5c  cmp     [rbp+90h+arg_18], r8b
0x140065f63  jz      loc_140066346
0x140065f69  mov     edx, [rbp+90h+arg_20]
0x140065f6f  mov     ecx, edx
0x140065f71  test    edx, edx
0x140065f73  jz      loc_1400662D6
0x140065f79  sub     ecx, 1
0x140065f7c  jz      loc_140066226
0x140065f82  sub     ecx, 1
0x140065f85  jz      loc_14006616B
0x140065f8b  sub     ecx, 1
0x140065f8e  jz      loc_140066160
0x140065f94  sub     ecx, 1
0x140065f97  jz      loc_140066094
0x140065f9d  sub     ecx, 1
0x140065fa0  jz      short loc_140065FAB
0x140065fa2  cmp     ecx, 1
0x140065fa5  jnz     loc_1400662D6
0x140065fab  mov     eax, [rbx+48h]
0x140065fae  cmp     edx, 5
0x140065fb1  mov     dword ptr [rbp+90h+arg_0], eax
0x140065fb7  mov     eax, [rbx+44h]
0x140065fba  mov     [rsp+190h+var_118], eax
0x140065fbe  mov     rax, [rsp+190h+var_120]
0x140065fc3  mov     rax, [rax]
  ... truncated ...
```
