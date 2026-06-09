# PostNewHttpRequest

- ea: `0x18000c768`
- end: `0x18000ca62`
- name: `PostNewHttpRequest`
- size: `762`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000afb0`
- `0x18000bd24`

## callees

- `0x180002f50`
- `0x180002f80`
- `0x1800048c0`
- `0x1800089dc`
- `0x180008b90`
- `0x180009c3c`
- `0x18000c768`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000c9c8`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000c9c8`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000c90a`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000c90a`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x18000c951`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x18000c951`

## pseudocode

```c
__int64 PostNewHttpRequest()
{
  unsigned int v0; // ebx
  __int64 BufferFromPool; // rax
  __int64 v2; // rdi
  __int64 Overlapped; // rsi
  ULONG v4; // eax
  __int64 v5; // r8
  __int64 v7; // [rsp+40h] [rbp-C0h] BYREF
  int v8; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v9[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v7 = 0;
  v8 = 0;
  memset_0(v9, 0, sizeof(v9));
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v8) = 0;
    FormatRRASErrorString(&v8, L"Entering %ws", L"PostNewHttpRequest");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v8);
  }
  v0 = AllocateAndInitializeCallContext(0, &v7);
  if ( v0 )
  {
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v8) = 0;
      FormatRRASErrorString(&v8, L"CoId=%hs:Failure to allocate the callctx", v7 + 552);
      if ( (byte_18002E903 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v8);
    }
  }
  else
  {
    BufferFromPool = GetBufferFromPool((char *)SstpSvcGlobals + 424);
    v2 = v7;
    Overlapped = BufferFromPool;
    if ( BufferFromPool )
    {
      *(_QWORD *)(v7 + 256) = BufferFromPool;
      *(_DWORD *)(BufferFromPool + 32) = 17767;
      *(_OWORD *)BufferFromPool = 0;
      *(_OWORD *)(BufferFromPool + 16) = 0;
      *(_DWORD *)(BufferFromPool + 92) = 0;
      *(_QWORD *)(BufferFromPool + 56) = v2;
      _InterlockedIncrement((volatile signed __int32 *)(v2 + 208));
      StartThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
      memset_0((void *)(Overlapped + 96), 0, 0x360u);
      v4 = HttpReceiveHttpRequest(
             *((HANDLE *)SstpSvcGlobals + 8),
             0,
             0,
             (PHTTP_REQUEST)(Overlapped + 96),
             0x4000u,
             0,
             (LPOVERLAPPED)Overlapped);
      v0 = v4;
      if ( v4 == 997 || !v4 )
      {
        v0 = 0;
        goto LABEL_21;
      }
      if ( (byte_18002E903 & 8) != 0 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString(&v8, L"CoId=%hs:HttpReceiveRequest fails with %d", v2 + 552, v4);
        if ( (byte_18002E903 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v8);
      }
      CancelThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
      LOBYTE(v5) = 1;
      FreeBufferToPool((char *)SstpSvcGlobals + 424, Overlapped, v5);
    }
    else
    {
      if ( (byte_18002E903 & 8) != 0 )
      {
        LOWORD(v8) = 0;
        FormatRRASErrorString(&v8, L"CoId=%hs:Unable to allocate memory for the recv buffer", v7 + 552);
        if ( (byte_18002E903 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v8);
      }
      v0 = 8;
    }
    DereferenceRefCount(v2 + 208);
  }
LABEL_21:
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v8) = 0;
    FormatRRASErrorString(&v8, L"LEaving %ws", L"PostNewHttpRequest");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v8);
  }
  return v0;
}

```

## disassembly

```asm
0x18000c768  push    rbp
0x18000c76a  push    rbx
0x18000c76b  push    rsi
0x18000c76c  push    rdi
0x18000c76d  push    r15
0x18000c76f  lea     rbp, [rsp-760h]
0x18000c777  sub     rsp, 860h
0x18000c77e  mov     rax, cs:__security_cookie
0x18000c785  xor     rax, rsp
0x18000c788  mov     [rbp+780h+var_30], rax
0x18000c78f  xor     eax, eax
0x18000c791  mov     [rsp+880h+var_840], 0
0x18000c79a  xor     edx, edx; Val
0x18000c79c  mov     [rsp+880h+var_830], eax
0x18000c7a0  mov     r8d, 7FCh; Size
0x18000c7a6  lea     rcx, [rsp+880h+var_82C]; void *
0x18000c7ab  call    memset_0
0x18000c7b0  test    cs:byte_18002E903, 10h
0x18000c7b7  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c7be  jz      short loc_18000C7FC
0x18000c7c0  xor     eax, eax
0x18000c7c2  lea     r8, aPostnewhttpreq; "PostNewHttpRequest"
0x18000c7c9  lea     rdx, aEnteringWs; "Entering %ws"
0x18000c7d0  mov     word ptr [rsp+880h+var_830], ax
0x18000c7d5  lea     rcx, [rsp+880h+var_830]
0x18000c7da  call    FormatRRASErrorString
0x18000c7df  test    cs:byte_18002E903, 10h
0x18000c7e6  jz      short loc_18000C7FC
0x18000c7e8  lea     r8, [rsp+880h+var_830]
0x18000c7ed  mov     rcx, r15
0x18000c7f0  lea     rdx, RasSSTPSvcTraceInfo
0x18000c7f7  call    McTemplateU0z_EventWriteTransfer
0x18000c7fc  lea     rdx, [rsp+880h+var_840]
0x18000c801  xor     ecx, ecx
0x18000c803  call    AllocateAndInitializeCallContext
0x18000c808  mov     ebx, eax
0x18000c80a  test    eax, eax
0x18000c80c  jz      short loc_18000C865
0x18000c80e  test    cs:byte_18002E903, 8
0x18000c815  jz      loc_18000C9FD
0x18000c81b  mov     r8, [rsp+880h+var_840]
0x18000c820  lea     rdx, aCoidHsFailureT; "CoId=%hs:Failure to allocate the callct"...
0x18000c827  xor     ecx, ecx
0x18000c829  add     r8, 228h
0x18000c830  mov     word ptr [rsp+880h+var_830], cx
0x18000c835  lea     rcx, [rsp+880h+var_830]
0x18000c83a  call    FormatRRASErrorString
0x18000c83f  test    cs:byte_18002E903, 8
0x18000c846  jz      loc_18000C9FD
0x18000c84c  lea     r8, [rsp+880h+var_830]
0x18000c851  mov     rcx, r15
0x18000c854  lea     rdx, RasSSTPSvcTraceError
0x18000c85b  call    McTemplateU0z_EventWriteTransfer
0x18000c860  jmp     loc_18000C9FD
0x18000c865  mov     rcx, cs:SstpSvcGlobals
0x18000c86c  add     rcx, 1A8h
0x18000c873  call    GetBufferFromPool
0x18000c878  mov     rdi, [rsp+880h+var_840]
0x18000c87d  mov     rsi, rax
0x18000c880  test    rax, rax
0x18000c883  jnz     short loc_18000C8D2
0x18000c885  test    cs:byte_18002E903, 8
0x18000c88c  jz      short loc_18000C8C8
0x18000c88e  lea     r8, [rdi+228h]
0x18000c895  mov     word ptr [rsp+880h+var_830], ax
0x18000c89a  lea     rdx, aCoidHsUnableTo_0; "CoId=%hs:Unable to allocate memory for "...
0x18000c8a1  lea     rcx, [rsp+880h+var_830]
0x18000c8a6  call    FormatRRASErrorString
0x18000c8ab  test    cs:byte_18002E903, 8
0x18000c8b2  jz      short loc_18000C8C8
0x18000c8b4  lea     r8, [rsp+880h+var_830]
0x18000c8b9  mov     rcx, r15
0x18000c8bc  lea     rdx, RasSSTPSvcTraceError
0x18000c8c3  call    McTemplateU0z_EventWriteTransfer
0x18000c8c8  mov     ebx, 8
0x18000c8cd  jmp     loc_18000C9ED
0x18000c8d2  mov     [rdi+100h], rsi
0x18000c8d9  xorps   xmm0, xmm0
0x18000c8dc  mov     dword ptr [rax+20h], 4567h
0x18000c8e3  movups  xmmword ptr [rax], xmm0
0x18000c8e6  movups  xmmword ptr [rax+10h], xmm0
0x18000c8ea  mov     dword ptr [rax+5Ch], 0
0x18000c8f1  mov     [rax+38h], rdi
0x18000c8f5  lock inc dword ptr [rdi+0D0h]
0x18000c8fc  mov     rcx, cs:SstpSvcGlobals
0x18000c903  mov     rcx, [rcx+0A8h]; pio
0x18000c90a  call    cs:__imp_StartThreadpoolIo
0x18000c911  nop     dword ptr [rax+rax+00h]
0x18000c916  xor     edx, edx; Val
0x18000c918  lea     rcx, [rsi+60h]; void *
0x18000c91c  mov     r8d, 360h; Size
0x18000c922  call    memset_0
0x18000c927  mov     rcx, cs:SstpSvcGlobals
0x18000c92e  lea     r9, [rsi+60h]; RequestBuffer
0x18000c932  mov     [rsp+880h+Overlapped], rsi; Overlapped
0x18000c937  xor     r8d, r8d; Flags
0x18000c93a  mov     [rsp+880h+BytesReturned], 0; BytesReturned
0x18000c943  xor     edx, edx; RequestId
0x18000c945  mov     [rsp+880h+RequestBufferLength], 4000h; RequestBufferLength
0x18000c94d  mov     rcx, [rcx+40h]; RequestQueueHandle
0x18000c951  call    cs:__imp_HttpReceiveHttpRequest
0x18000c958  nop     dword ptr [rax+rax+00h]
0x18000c95d  mov     ebx, eax
0x18000c95f  cmp     eax, 3E5h
0x18000c964  jz      loc_18000C9FB
0x18000c96a  test    eax, eax
0x18000c96c  jz      loc_18000C9FB
0x18000c972  test    cs:byte_18002E903, 8
0x18000c979  jz      short loc_18000C9BA
0x18000c97b  xor     eax, eax
0x18000c97d  lea     r8, [rdi+228h]
0x18000c984  mov     r9d, ebx
0x18000c987  mov     word ptr [rsp+880h+var_830], ax
0x18000c98c  lea     rdx, aCoidHsHttprece; "CoId=%hs:HttpReceiveRequest fails with "...
0x18000c993  lea     rcx, [rsp+880h+var_830]
0x18000c998  call    FormatRRASErrorString
0x18000c99d  test    cs:byte_18002E903, 8
0x18000c9a4  jz      short loc_18000C9BA
0x18000c9a6  lea     r8, [rsp+880h+var_830]
0x18000c9ab  mov     rcx, r15
0x18000c9ae  lea     rdx, RasSSTPSvcTraceError
0x18000c9b5  call    McTemplateU0z_EventWriteTransfer
0x18000c9ba  mov     rcx, cs:SstpSvcGlobals
0x18000c9c1  mov     rcx, [rcx+0A8h]; pio
0x18000c9c8  call    cs:__imp_CancelThreadpoolIo
0x18000c9cf  nop     dword ptr [rax+rax+00h]
0x18000c9d4  mov     rcx, cs:SstpSvcGlobals
0x18000c9db  mov     r8b, 1
0x18000c9de  add     rcx, 1A8h
0x18000c9e5  mov     rdx, rsi
0x18000c9e8  call    FreeBufferToPool
0x18000c9ed  lea     rcx, [rdi+0D0h]
0x18000c9f4  call    DereferenceRefCount
0x18000c9f9  jmp     short loc_18000C9FD
0x18000c9fb  xor     ebx, ebx
0x18000c9fd  test    cs:byte_18002E903, 10h
0x18000ca04  jz      short loc_18000CA42
0x18000ca06  xor     eax, eax
0x18000ca08  lea     r8, aPostnewhttpreq; "PostNewHttpRequest"
0x18000ca0f  lea     rdx, aLeavingWs; "LEaving %ws"
0x18000ca16  mov     word ptr [rsp+880h+var_830], ax
0x18000ca1b  lea     rcx, [rsp+880h+var_830]
0x18000ca20  call    FormatRRASErrorString
0x18000ca25  test    cs:byte_18002E903, 10h
0x18000ca2c  jz      short loc_18000CA42
0x18000ca2e  lea     r8, [rsp+880h+var_830]
0x18000ca33  mov     rcx, r15
0x18000ca36  lea     rdx, RasSSTPSvcTraceInfo
0x18000ca3d  call    McTemplateU0z_EventWriteTransfer
0x18000ca42  mov     eax, ebx
0x18000ca44  mov     rcx, [rbp+780h+var_30]
0x18000ca4b  xor     rcx, rsp; StackCookie
0x18000ca4e  call    __security_check_cookie
0x18000ca53  add     rsp, 860h
0x18000ca5a  pop     r15
0x18000ca5c  pop     rdi
0x18000ca5d  pop     rsi
0x18000ca5e  pop     rbx
0x18000ca5f  pop     rbp
0x18000ca60  retn
```
