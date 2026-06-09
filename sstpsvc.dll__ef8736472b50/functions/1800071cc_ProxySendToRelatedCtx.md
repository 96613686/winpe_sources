# ProxySendToRelatedCtx

- ea: `0x1800071cc`
- end: `0x180007513`
- name: `ProxySendToRelatedCtx`
- size: `839`
- prototype: `__int64 __fastcall(LPOVERLAPPED Overlapped)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180001fe0`
- `0x180002320`
- `0x18000afb0`

## callees

- `0x1800011b0`
- `0x180002aac`
- `0x180002f80`
- `0x1800071cc`
- `0x180007520`
- `0x1800089dc`
- `0x180008b90`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007280`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007470`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007280`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007470`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800072a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000749f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800072a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000749f`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180007394`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180007394`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180007300`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180007300`
- `HTTPAPI!HttpSendResponseEntityBody` at `0x18000734b`
- `HTTPAPI!HttpSendResponseEntityBody` at `0x18000734b`
- `webio!__imp_WebSendHttpRequestEntity` at `0x180007432`
- `webio!__imp_WebSendHttpRequestEntity` at `0x180007432`

## pseudocode

```c
void __fastcall ProxySendToRelatedCtx(LPOVERLAPPED Overlapped)
{
  __int64 v2; // rbx
  __int64 v3; // r8
  void *hEvent_high; // rcx
  ULONG v5; // eax
  __int64 v6; // r8
  ULONG v7; // r14d
  unsigned int v8; // eax
  PHTTP_DATA_CHUNK EntityChunks; // [rsp+20h] [rbp-E0h]
  struct _HTTP_DATA_CHUNK v10; // [rsp+50h] [rbp-B0h] BYREF
  int v11; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v12[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v11 = 0;
  memset_0(v12, 0, sizeof(v12));
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v11) = 0;
    FormatRRASErrorString(&v11, L"Entering %ws", L"ProxySendToNetworkWorker");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v11);
  }
  if ( (unsigned int)IsProxyCall(Overlapped[1].hEvent) )
  {
    v2 = *((_QWORD *)Overlapped[1].hEvent + 78);
    EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 288));
    *(_DWORD *)(v2 + 252) |= 0x80u;
    if ( !*(_BYTE *)(v2 + 435) )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 288));
      if ( HIDWORD(Overlapped[2].hEvent) )
      {
        LODWORD(Overlapped[1].Internal) = 17778;
        *(_OWORD *)&Overlapped->Internal = 0;
        *(_OWORD *)&Overlapped->Offset = 0;
        hEvent_high = (void *)HIDWORD(Overlapped[2].hEvent);
        if ( *(_BYTE *)(v2 + 248) )
        {
          LODWORD(Overlapped[2].Internal) = 0;
          Overlapped[2].InternalHigh = (ULONG_PTR)&Overlapped[3];
          Overlapped[2].Pointer = hEvent_high;
          _InterlockedIncrement((volatile signed __int32 *)(v2 + 208));
          Overlapped[1].hEvent = (HANDLE)v2;
          v8 = WebSendHttpRequestEntity(
                 *(_QWORD *)(v2 + 448),
                 0,
                 &Overlapped[2],
                 1,
                 SstpWebSendRequestEntityCompletion,
                 Overlapped);
          if ( v8 != 997 )
            SstpWebSendRequestEntityCompletion(Overlapped, v8, 0);
        }
        else
        {
          v10.FromMemory.BufferLength = HIDWORD(Overlapped[2].hEvent);
          *(_QWORD *)&v10.DataChunkType = 0;
          *(ULONGLONG *)((char *)&v10.FromFragmentCacheEx.ByteRange.Length.QuadPart + 4) = 0;
          v10.FromFileHandle.ByteRange.StartingOffset.QuadPart = (ULONGLONG)&Overlapped[3];
          StartThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
          v5 = HttpSendResponseEntityBody(
                 *((HANDLE *)SstpSvcGlobals + 8),
                 *(_QWORD *)(v2 + 272),
                 2u,
                 1u,
                 &v10,
                 0,
                 0,
                 0,
                 Overlapped,
                 0);
          v7 = v5;
          if ( v5 != 997 )
          {
            if ( v5 )
            {
              LOBYTE(v6) = 1;
              FreeBufferToPool((char *)SstpSvcGlobals + 424, Overlapped, v6);
              CancelThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
              if ( (byte_18002E903 & 8) != 0 )
              {
                LOWORD(v11) = 0;
                LODWORD(EntityChunks) = v7;
                FormatRRASErrorString(
                  &v11,
                  L"CoId=%hs:HttpSendResponseEntityBody fails with error %d [%d]",
                  v2 + 552,
                  v7,
                  EntityChunks);
                if ( (byte_18002E903 & 8) != 0 )
                  McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v11);
              }
            }
          }
        }
      }
      else
      {
        LOBYTE(v3) = 1;
        FreeBufferToPool((char *)SstpSvcGlobals + 424, Overlapped, v3);
      }
      EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 288));
    }
    *(_DWORD *)(v2 + 252) &= ~0x80u;
    if ( *(_BYTE *)(v2 + 435) )
      InitiateCallContextCleanup(v2, 2u);
    else
      LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 288));
  }
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v11) = 0;
    FormatRRASErrorString(&v11, L"LEaving %ws", L"ProxySendToNetworkWorker");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v11);
  }
}

```

## disassembly

```asm
0x1800071cc  push    rbp
0x1800071ce  push    rbx
0x1800071cf  push    rsi
0x1800071d0  push    rdi
0x1800071d1  push    r14
0x1800071d3  push    r15
0x1800071d5  lea     rbp, [rsp-788h]
0x1800071dd  sub     rsp, 888h
0x1800071e4  mov     rax, cs:__security_cookie
0x1800071eb  xor     rax, rsp
0x1800071ee  mov     [rbp+7B0h+var_40], rax
0x1800071f5  mov     rdi, rcx
0x1800071f8  xor     r15d, r15d
0x1800071fb  lea     rcx, [rsp+8B0h+var_83C]; void *
0x180007200  mov     [rsp+8B0h+var_840], r15d
0x180007205  xor     edx, edx; Val
0x180007207  mov     r8d, 7FCh; Size
0x18000720d  call    memset_0
0x180007212  test    cs:byte_18002E903, 10h
0x180007219  jz      short loc_18000725A
0x18000721b  lea     r8, aProxysendtonet; "ProxySendToNetworkWorker"
0x180007222  mov     word ptr [rsp+8B0h+var_840], r15w
0x180007228  lea     rdx, aEnteringWs; "Entering %ws"
0x18000722f  lea     rcx, [rsp+8B0h+var_840]
0x180007234  call    FormatRRASErrorString
0x180007239  test    cs:byte_18002E903, 10h
0x180007240  jz      short loc_18000725A
0x180007242  lea     r8, [rsp+8B0h+var_840]
0x180007247  lea     rdx, RasSSTPSvcTraceInfo
0x18000724e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007255  call    McTemplateU0z_EventWriteTransfer
0x18000725a  mov     rcx, [rdi+38h]
0x18000725e  call    IsProxyCall
0x180007263  test    eax, eax
0x180007265  jz      loc_1800074AB
0x18000726b  mov     rax, [rdi+38h]
0x18000726f  mov     rbx, [rax+270h]
0x180007276  lea     rsi, [rbx+120h]
0x18000727d  mov     rcx, rsi; lpCriticalSection
0x180007280  call    cs:__imp_EnterCriticalSection
0x180007287  nop     dword ptr [rax+rax+00h]
0x18000728c  bts     dword ptr [rbx+0FCh], 7
0x180007294  cmp     [rbx+1B3h], r15b
0x18000729b  jnz     loc_18000747C
0x1800072a1  mov     rcx, rsi; lpCriticalSection
0x1800072a4  call    cs:__imp_LeaveCriticalSection
0x1800072ab  nop     dword ptr [rax+rax+00h]
0x1800072b0  cmp     [rdi+5Ch], r15d
0x1800072b4  jbe     loc_180007454
0x1800072ba  mov     dword ptr [rdi+20h], 4572h
0x1800072c1  lea     rax, [rdi+60h]
0x1800072c5  xorps   xmm0, xmm0
0x1800072c8  movups  xmmword ptr [rdi], xmm0
0x1800072cb  movups  xmmword ptr [rdi+10h], xmm0
0x1800072cf  mov     ecx, [rdi+5Ch]
0x1800072d2  cmp     [rbx+0F8h], r15b
0x1800072d9  jnz     loc_1800073FA
0x1800072df  mov     dword ptr [rsp+8B0h+var_860.8+8], ecx
0x1800072e3  mov     rcx, cs:SstpSvcGlobals
0x1800072ea  mov     qword ptr [rsp+8B0h+var_860.DataChunkType], r15
0x1800072ef  mov     qword ptr [rsp+8B0h+var_860.8+0Ch], r15
0x1800072f4  mov     qword ptr [rsp+8B0h+var_860.8], rax
0x1800072f9  mov     rcx, [rcx+0A8h]; pio
0x180007300  call    cs:__imp_StartThreadpoolIo
0x180007307  nop     dword ptr [rax+rax+00h]
0x18000730c  mov     rcx, cs:SstpSvcGlobals
0x180007313  lea     rax, [rsp+8B0h+var_860]
0x180007318  mov     rdx, [rbx+110h]; RequestId
0x18000731f  mov     r9d, 1; EntityChunkCount
0x180007325  mov     [rsp+8B0h+LogData], r15; LogData
0x18000732a  mov     [rsp+8B0h+Overlapped], rdi; Overlapped
0x18000732f  mov     rcx, [rcx+40h]; RequestQueueHandle
0x180007333  mov     [rsp+8B0h+Reserved2], r15d; Reserved2
0x180007338  lea     r8d, [r9+1]; Flags
0x18000733c  mov     [rsp+8B0h+Reserved1], r15; Reserved1
0x180007341  mov     [rsp+8B0h+BytesSent], r15; BytesSent
0x180007346  mov     [rsp+8B0h+EntityChunks], rax; EntityChunks
0x18000734b  call    cs:__imp_HttpSendResponseEntityBody
0x180007352  nop     dword ptr [rax+rax+00h]
0x180007357  mov     r14d, eax
0x18000735a  cmp     eax, 3E5h
0x18000735f  jz      loc_18000746D
0x180007365  test    eax, eax
0x180007367  jz      loc_18000746D
0x18000736d  mov     rcx, cs:SstpSvcGlobals
0x180007374  mov     r8b, 1
0x180007377  add     rcx, 1A8h
0x18000737e  mov     rdx, rdi
0x180007381  call    FreeBufferToPool
0x180007386  mov     rcx, cs:SstpSvcGlobals
0x18000738d  mov     rcx, [rcx+0A8h]; pio
0x180007394  call    cs:__imp_CancelThreadpoolIo
0x18000739b  nop     dword ptr [rax+rax+00h]
0x1800073a0  test    cs:byte_18002E903, 8
0x1800073a7  jz      loc_18000746D
0x1800073ad  lea     r8, [rbx+228h]
0x1800073b4  mov     word ptr [rsp+8B0h+var_840], r15w
0x1800073ba  mov     r9d, r14d
0x1800073bd  mov     dword ptr [rsp+8B0h+EntityChunks], r14d
0x1800073c2  lea     rdx, aCoidHsHttpsend; "CoId=%hs:HttpSendResponseEntityBody fai"...
0x1800073c9  lea     rcx, [rsp+8B0h+var_840]
0x1800073ce  call    FormatRRASErrorString
0x1800073d3  test    cs:byte_18002E903, 8
0x1800073da  jz      loc_18000746D
0x1800073e0  lea     r8, [rsp+8B0h+var_840]
0x1800073e5  lea     rdx, RasSSTPSvcTraceError
0x1800073ec  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800073f3  call    McTemplateU0z_EventWriteTransfer
0x1800073f8  jmp     short loc_18000746D
0x1800073fa  lea     r8, [rdi+40h]
0x1800073fe  mov     [r8], r15d
0x180007401  mov     [r8+8], rax
0x180007405  mov     [r8+10h], rcx
0x180007409  lock inc dword ptr [rbx+0D0h]
0x180007410  xor     edx, edx
0x180007412  mov     [rdi+38h], rbx
0x180007416  mov     rcx, [rbx+1C0h]
0x18000741d  lea     rax, SstpWebSendRequestEntityCompletion
0x180007424  mov     [rsp+8B0h+BytesSent], rdi
0x180007429  mov     [rsp+8B0h+EntityChunks], rax
0x18000742e  lea     r9d, [rdx+1]
0x180007432  call    cs:__imp_WebSendHttpRequestEntity
0x180007439  nop     dword ptr [rax+rax+00h]
0x18000743e  cmp     eax, 3E5h
0x180007443  jz      short loc_18000746D
0x180007445  xor     r8d, r8d
0x180007448  mov     edx, eax
0x18000744a  mov     rcx, rdi
0x18000744d  call    SstpWebSendRequestEntityCompletion
0x180007452  jmp     short loc_18000746D
0x180007454  mov     rcx, cs:SstpSvcGlobals
0x18000745b  mov     r8b, 1
0x18000745e  add     rcx, 1A8h
0x180007465  mov     rdx, rdi
0x180007468  call    FreeBufferToPool
0x18000746d  mov     rcx, rsi; lpCriticalSection
0x180007470  call    cs:__imp_EnterCriticalSection
0x180007477  nop     dword ptr [rax+rax+00h]
0x18000747c  btr     dword ptr [rbx+0FCh], 7
0x180007484  cmp     [rbx+1B3h], r15b
0x18000748b  jz      short loc_18000749C
0x18000748d  mov     edx, 2
0x180007492  mov     rcx, rbx
0x180007495  call    InitiateCallContextCleanup
0x18000749a  jmp     short loc_1800074AB
0x18000749c  mov     rcx, rsi; lpCriticalSection
0x18000749f  call    cs:__imp_LeaveCriticalSection
0x1800074a6  nop     dword ptr [rax+rax+00h]
0x1800074ab  test    cs:byte_18002E903, 10h
0x1800074b2  jz      short loc_1800074F3
0x1800074b4  lea     r8, aProxysendtonet; "ProxySendToNetworkWorker"
0x1800074bb  mov     word ptr [rsp+8B0h+var_840], r15w
0x1800074c1  lea     rdx, aLeavingWs; "LEaving %ws"
0x1800074c8  lea     rcx, [rsp+8B0h+var_840]
0x1800074cd  call    FormatRRASErrorString
0x1800074d2  test    cs:byte_18002E903, 10h
0x1800074d9  jz      short loc_1800074F3
0x1800074db  lea     r8, [rsp+8B0h+var_840]
0x1800074e0  lea     rdx, RasSSTPSvcTraceInfo
0x1800074e7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800074ee  call    McTemplateU0z_EventWriteTransfer
0x1800074f3  mov     rcx, [rbp+7B0h+var_40]
0x1800074fa  xor     rcx, rsp; StackCookie
0x1800074fd  call    __security_check_cookie
0x180007502  add     rsp, 888h
0x180007509  pop     r15
0x18000750b  pop     r14
0x18000750d  pop     rdi
0x18000750e  pop     rsi
0x18000750f  pop     rbx
0x180007510  pop     rbp
0x180007511  retn
```
