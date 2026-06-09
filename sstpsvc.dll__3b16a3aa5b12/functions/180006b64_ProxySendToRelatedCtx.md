# ProxySendToRelatedCtx

- ea: `0x180006b64`
- end: `0x180006e7a`
- name: `ProxySendToRelatedCtx`
- size: `790`
- prototype: `__int64 __fastcall(LPOVERLAPPED Overlapped)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180001ee0`
- `0x1800021f0`
- `0x18000a620`

## callees

- `0x180001160`
- `0x180002908`
- `0x180002d70`
- `0x180006b64`
- `0x180006e80`
- `0x18000827c`
- `0x180008360`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006c18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006de4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006c18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006de4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006c36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006e0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006c36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006e0d`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180006d14`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180006d14`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180006c8c`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180006c8c`
- `HTTPAPI!HttpSendResponseEntityBody` at `0x180006cd1`
- `HTTPAPI!HttpSendResponseEntityBody` at `0x180006cd1`
- `webio!__imp_WebSendHttpRequestEntity` at `0x180006dac`
- `webio!__imp_WebSendHttpRequestEntity` at `0x180006dac`

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
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v11) = 0;
    FormatRRASErrorString(&v11, L"Entering %ws", L"ProxySendToNetworkWorker");
    if ( (byte_18002D803 & 0x10) != 0 )
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
              if ( (byte_18002D803 & 8) != 0 )
              {
                LOWORD(v11) = 0;
                LODWORD(EntityChunks) = v7;
                FormatRRASErrorString(
                  &v11,
                  L"CoId=%hs:HttpSendResponseEntityBody fails with error %d [%d]",
                  v2 + 552,
                  v7,
                  EntityChunks);
                if ( (byte_18002D803 & 8) != 0 )
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
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v11) = 0;
    FormatRRASErrorString(&v11, L"LEaving %ws", L"ProxySendToNetworkWorker");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v11);
  }
}

```

## disassembly

```asm
0x180006b64  push    rbp
0x180006b66  push    rbx
0x180006b67  push    rsi
0x180006b68  push    rdi
0x180006b69  push    r14
0x180006b6b  push    r15
0x180006b6d  lea     rbp, [rsp-788h]
0x180006b75  sub     rsp, 888h
0x180006b7c  mov     rax, cs:__security_cookie
0x180006b83  xor     rax, rsp
0x180006b86  mov     [rbp+7B0h+var_40], rax
0x180006b8d  mov     rdi, rcx
0x180006b90  xor     r15d, r15d
0x180006b93  lea     rcx, [rsp+8B0h+var_83C]; void *
0x180006b98  mov     [rsp+8B0h+var_840], r15d
0x180006b9d  xor     edx, edx; Val
0x180006b9f  mov     r8d, 7FCh; Size
0x180006ba5  call    memset_0
0x180006baa  test    cs:byte_18002D803, 10h
0x180006bb1  jz      short loc_180006BF2
0x180006bb3  lea     r8, aProxysendtonet; "ProxySendToNetworkWorker"
0x180006bba  mov     word ptr [rsp+8B0h+var_840], r15w
0x180006bc0  lea     rdx, aEnteringWs; "Entering %ws"
0x180006bc7  lea     rcx, [rsp+8B0h+var_840]
0x180006bcc  call    FormatRRASErrorString
0x180006bd1  test    cs:byte_18002D803, 10h
0x180006bd8  jz      short loc_180006BF2
0x180006bda  lea     r8, [rsp+8B0h+var_840]
0x180006bdf  lea     rdx, RasSSTPSvcTraceInfo
0x180006be6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006bed  call    McTemplateU0z_EventWriteTransfer
0x180006bf2  mov     rcx, [rdi+38h]
0x180006bf6  call    IsProxyCall
0x180006bfb  test    eax, eax
0x180006bfd  jz      loc_180006E13
0x180006c03  mov     rax, [rdi+38h]
0x180006c07  mov     rbx, [rax+270h]
0x180006c0e  lea     rsi, [rbx+120h]
0x180006c15  mov     rcx, rsi; lpCriticalSection
0x180006c18  call    cs:__imp_EnterCriticalSection
0x180006c1e  bts     dword ptr [rbx+0FCh], 7
0x180006c26  cmp     [rbx+1B3h], r15b
0x180006c2d  jnz     loc_180006DEA
0x180006c33  mov     rcx, rsi; lpCriticalSection
0x180006c36  call    cs:__imp_LeaveCriticalSection
0x180006c3c  cmp     [rdi+5Ch], r15d
0x180006c40  jbe     loc_180006DC8
0x180006c46  mov     dword ptr [rdi+20h], 4572h
0x180006c4d  lea     rax, [rdi+60h]
0x180006c51  xorps   xmm0, xmm0
0x180006c54  movups  xmmword ptr [rdi], xmm0
0x180006c57  movups  xmmword ptr [rdi+10h], xmm0
0x180006c5b  mov     ecx, [rdi+5Ch]
0x180006c5e  cmp     [rbx+0F8h], r15b
0x180006c65  jnz     loc_180006D74
0x180006c6b  mov     dword ptr [rsp+8B0h+var_860.8+8], ecx
0x180006c6f  mov     rcx, cs:SstpSvcGlobals
0x180006c76  mov     qword ptr [rsp+8B0h+var_860.DataChunkType], r15
0x180006c7b  mov     qword ptr [rsp+8B0h+var_860.8+0Ch], r15
0x180006c80  mov     qword ptr [rsp+8B0h+var_860.8], rax
0x180006c85  mov     rcx, [rcx+0A8h]; pio
0x180006c8c  call    cs:__imp_StartThreadpoolIo
0x180006c92  mov     rcx, cs:SstpSvcGlobals
0x180006c99  lea     rax, [rsp+8B0h+var_860]
0x180006c9e  mov     rdx, [rbx+110h]; RequestId
0x180006ca5  mov     r9d, 1; EntityChunkCount
0x180006cab  mov     [rsp+8B0h+LogData], r15; LogData
0x180006cb0  mov     [rsp+8B0h+Overlapped], rdi; Overlapped
0x180006cb5  mov     rcx, [rcx+40h]; RequestQueueHandle
0x180006cb9  mov     [rsp+8B0h+Reserved2], r15d; Reserved2
0x180006cbe  lea     r8d, [r9+1]; Flags
0x180006cc2  mov     [rsp+8B0h+Reserved1], r15; Reserved1
0x180006cc7  mov     [rsp+8B0h+BytesSent], r15; BytesSent
0x180006ccc  mov     [rsp+8B0h+EntityChunks], rax; EntityChunks
0x180006cd1  call    cs:__imp_HttpSendResponseEntityBody
0x180006cd7  mov     r14d, eax
0x180006cda  cmp     eax, 3E5h
0x180006cdf  jz      loc_180006DE1
0x180006ce5  test    eax, eax
0x180006ce7  jz      loc_180006DE1
0x180006ced  mov     rcx, cs:SstpSvcGlobals
0x180006cf4  mov     r8b, 1
0x180006cf7  add     rcx, 1A8h
0x180006cfe  mov     rdx, rdi
0x180006d01  call    FreeBufferToPool
0x180006d06  mov     rcx, cs:SstpSvcGlobals
0x180006d0d  mov     rcx, [rcx+0A8h]; pio
0x180006d14  call    cs:__imp_CancelThreadpoolIo
0x180006d1a  test    cs:byte_18002D803, 8
0x180006d21  jz      loc_180006DE1
0x180006d27  lea     r8, [rbx+228h]
0x180006d2e  mov     word ptr [rsp+8B0h+var_840], r15w
0x180006d34  mov     r9d, r14d
0x180006d37  mov     dword ptr [rsp+8B0h+EntityChunks], r14d
0x180006d3c  lea     rdx, aCoidHsHttpsend; "CoId=%hs:HttpSendResponseEntityBody fai"...
0x180006d43  lea     rcx, [rsp+8B0h+var_840]
0x180006d48  call    FormatRRASErrorString
0x180006d4d  test    cs:byte_18002D803, 8
0x180006d54  jz      loc_180006DE1
0x180006d5a  lea     r8, [rsp+8B0h+var_840]
0x180006d5f  lea     rdx, RasSSTPSvcTraceError
0x180006d66  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006d6d  call    McTemplateU0z_EventWriteTransfer
0x180006d72  jmp     short loc_180006DE1
0x180006d74  lea     r8, [rdi+40h]
0x180006d78  mov     [r8], r15d
0x180006d7b  mov     [r8+8], rax
0x180006d7f  mov     [r8+10h], rcx
0x180006d83  lock inc dword ptr [rbx+0D0h]
0x180006d8a  xor     edx, edx
0x180006d8c  mov     [rdi+38h], rbx
0x180006d90  mov     rcx, [rbx+1C0h]
0x180006d97  lea     rax, SstpWebSendRequestEntityCompletion
0x180006d9e  mov     [rsp+8B0h+BytesSent], rdi
0x180006da3  mov     [rsp+8B0h+EntityChunks], rax
0x180006da8  lea     r9d, [rdx+1]
0x180006dac  call    cs:__imp_WebSendHttpRequestEntity
0x180006db2  cmp     eax, 3E5h
0x180006db7  jz      short loc_180006DE1
0x180006db9  xor     r8d, r8d
0x180006dbc  mov     edx, eax
0x180006dbe  mov     rcx, rdi
0x180006dc1  call    SstpWebSendRequestEntityCompletion
0x180006dc6  jmp     short loc_180006DE1
0x180006dc8  mov     rcx, cs:SstpSvcGlobals
0x180006dcf  mov     r8b, 1
0x180006dd2  add     rcx, 1A8h
0x180006dd9  mov     rdx, rdi
0x180006ddc  call    FreeBufferToPool
0x180006de1  mov     rcx, rsi; lpCriticalSection
0x180006de4  call    cs:__imp_EnterCriticalSection
0x180006dea  btr     dword ptr [rbx+0FCh], 7
0x180006df2  cmp     [rbx+1B3h], r15b
0x180006df9  jz      short loc_180006E0A
0x180006dfb  mov     edx, 2
0x180006e00  mov     rcx, rbx
0x180006e03  call    InitiateCallContextCleanup
0x180006e08  jmp     short loc_180006E13
0x180006e0a  mov     rcx, rsi; lpCriticalSection
0x180006e0d  call    cs:__imp_LeaveCriticalSection
0x180006e13  test    cs:byte_18002D803, 10h
0x180006e1a  jz      short loc_180006E5B
0x180006e1c  lea     r8, aProxysendtonet; "ProxySendToNetworkWorker"
0x180006e23  mov     word ptr [rsp+8B0h+var_840], r15w
0x180006e29  lea     rdx, aLeavingWs; "LEaving %ws"
0x180006e30  lea     rcx, [rsp+8B0h+var_840]
0x180006e35  call    FormatRRASErrorString
0x180006e3a  test    cs:byte_18002D803, 10h
0x180006e41  jz      short loc_180006E5B
0x180006e43  lea     r8, [rsp+8B0h+var_840]
0x180006e48  lea     rdx, RasSSTPSvcTraceInfo
0x180006e4f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006e56  call    McTemplateU0z_EventWriteTransfer
0x180006e5b  mov     rcx, [rbp+7B0h+var_40]
0x180006e62  xor     rcx, rsp; StackCookie
0x180006e65  call    __security_check_cookie
0x180006e6a  add     rsp, 888h
0x180006e71  pop     r15
0x180006e73  pop     r14
0x180006e75  pop     rdi
0x180006e76  pop     rsi
0x180006e77  pop     rbx
0x180006e78  pop     rbp
0x180006e79  retn
```
