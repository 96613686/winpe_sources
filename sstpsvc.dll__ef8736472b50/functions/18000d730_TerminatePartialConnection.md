# TerminatePartialConnection

- ea: `0x18000d730`
- end: `0x18000d970`
- name: `TerminatePartialConnection`
- size: `576`
- prototype: `__int64 __fastcall(HTTP_REQUEST_ID RequestId, LPOVERLAPPED Overlapped)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000adb8`

## callees

- `0x180002f80`
- `0x1800089dc`
- `0x180008b90`
- `0x18000d730`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000d8d8`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000d8d8`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000d811`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000d811`
- `HTTPAPI!HttpSendHttpResponse` at `0x18000d86c`
- `HTTPAPI!HttpSendHttpResponse` at `0x18000d86c`

## pseudocode

```c
__int64 __fastcall TerminatePartialConnection(HTTP_REQUEST_ID RequestId, LPOVERLAPPED Overlapped)
{
  PTP_IO *v4; // rcx
  ULONG v5; // eax
  ULONG v6; // ebx
  __int64 v7; // r8
  struct _HTTP_CACHE_POLICY CachePolicy; // [rsp+50h] [rbp-B0h] BYREF
  int v10; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v11[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  CachePolicy = 0;
  v10 = 0;
  memset_0(v11, 0, sizeof(v11));
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v10) = 0;
    FormatRRASErrorString(&v10, L"Entering %ws", L"TerminatePartialConnection");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v10);
  }
  *(_OWORD *)&Overlapped->Internal = 0;
  *(_OWORD *)&Overlapped->Offset = 0;
  LODWORD(Overlapped[1].Internal) = 17768;
  memset_0(&Overlapped[3], 0, 0x238u);
  v4 = (PTP_IO *)SstpSvcGlobals;
  HIDWORD(Overlapped[3].Internal) = 65537;
  LOWORD(Overlapped[3].InternalHigh) = 401;
  StartThreadpoolIo(v4[21]);
  CachePolicy.Policy = HttpCachePolicyNocache;
  v5 = HttpSendHttpResponse(
         *((HANDLE *)SstpSvcGlobals + 8),
         RequestId,
         1u,
         (PHTTP_RESPONSE)&Overlapped[3],
         &CachePolicy,
         0,
         0,
         0,
         Overlapped,
         0);
  v6 = v5;
  if ( v5 != 997 && v5 )
  {
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v10) = 0;
      FormatRRASErrorString(&v10, L"Terminate: SendResponse fails with error %d", v5);
      if ( (byte_18002E903 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v10);
    }
    CancelThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
    LOBYTE(v7) = 1;
    FreeBufferToPool((char *)SstpSvcGlobals + 424, Overlapped, v7);
  }
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v10) = 0;
    FormatRRASErrorString(&v10, L"LEaving %ws", L"TerminatePartialConnection");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v10);
  }
  return v6;
}

```

## disassembly

```asm
0x18000d730  mov     [rsp-8+arg_10], rbx
0x18000d735  mov     [rsp-8+arg_18], rsi
0x18000d73a  push    rbp
0x18000d73b  push    rdi
0x18000d73c  push    r13
0x18000d73e  lea     rbp, [rsp-770h]
0x18000d746  sub     rsp, 870h
0x18000d74d  mov     rax, cs:__security_cookie
0x18000d754  xor     rax, rsp
0x18000d757  mov     [rbp+780h+var_20], rax
0x18000d75e  mov     rdi, rdx
0x18000d761  mov     qword ptr [rsp+880h+var_830.Policy], 0
0x18000d76a  mov     rsi, rcx
0x18000d76d  xor     eax, eax
0x18000d76f  xor     edx, edx; Val
0x18000d771  mov     [rsp+880h+var_820], eax
0x18000d775  lea     rcx, [rsp+880h+var_81C]; void *
0x18000d77a  mov     r8d, 7FCh; Size
0x18000d780  call    memset_0
0x18000d785  test    cs:byte_18002E903, 10h
0x18000d78c  jz      short loc_18000D7CE
0x18000d78e  xor     eax, eax
0x18000d790  lea     r8, aTerminateparti_0; "TerminatePartialConnection"
0x18000d797  lea     rdx, aEnteringWs; "Entering %ws"
0x18000d79e  mov     word ptr [rsp+880h+var_820], ax
0x18000d7a3  lea     rcx, [rsp+880h+var_820]
0x18000d7a8  call    FormatRRASErrorString
0x18000d7ad  test    cs:byte_18002E903, 10h
0x18000d7b4  jz      short loc_18000D7CE
0x18000d7b6  lea     r8, [rsp+880h+var_820]
0x18000d7bb  lea     rdx, RasSSTPSvcTraceInfo
0x18000d7c2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d7c9  call    McTemplateU0z_EventWriteTransfer
0x18000d7ce  xorps   xmm0, xmm0
0x18000d7d1  lea     rcx, [rdi+60h]; void *
0x18000d7d5  movups  xmmword ptr [rdi], xmm0
0x18000d7d8  xor     edx, edx; Val
0x18000d7da  mov     r8d, 238h; Size
0x18000d7e0  movups  xmmword ptr [rdi+10h], xmm0
0x18000d7e4  mov     dword ptr [rdi+20h], 4568h
0x18000d7eb  call    memset_0
0x18000d7f0  mov     rcx, cs:SstpSvcGlobals
0x18000d7f7  mov     r13d, 1
0x18000d7fd  mov     dword ptr [rdi+64h], 10001h
0x18000d804  mov     word ptr [rdi+68h], 191h
0x18000d80a  mov     rcx, [rcx+0A8h]; pio
0x18000d811  call    cs:__imp_StartThreadpoolIo
0x18000d818  nop     dword ptr [rax+rax+00h]
0x18000d81d  mov     rcx, cs:SstpSvcGlobals
0x18000d824  lea     rax, [rsp+880h+var_830]
0x18000d829  mov     [rsp+880h+LogData], 0; LogData
0x18000d832  lea     r9, [rdi+60h]; HttpResponse
0x18000d836  mov     [rsp+880h+Overlapped], rdi; Overlapped
0x18000d83b  mov     r8d, r13d; Flags
0x18000d83e  mov     [rsp+880h+Reserved2], 0; Reserved2
0x18000d846  mov     rdx, rsi; RequestId
0x18000d849  mov     [rsp+880h+var_830.Policy], 0
0x18000d851  mov     rcx, [rcx+40h]; RequestQueueHandle
0x18000d855  mov     [rsp+880h+Reserved1], 0; Reserved1
0x18000d85e  mov     [rsp+880h+BytesSent], 0; BytesSent
0x18000d867  mov     [rsp+880h+CachePolicy], rax; CachePolicy
0x18000d86c  call    cs:__imp_HttpSendHttpResponse
0x18000d873  nop     dword ptr [rax+rax+00h]
0x18000d878  mov     ebx, eax
0x18000d87a  cmp     eax, 3E5h
0x18000d87f  jz      short loc_18000D8FD
0x18000d881  test    eax, eax
0x18000d883  jz      short loc_18000D8FD
0x18000d885  test    cs:byte_18002E903, 8
0x18000d88c  jz      short loc_18000D8CA
0x18000d88e  xor     ecx, ecx
0x18000d890  lea     rdx, aTerminateSendr; "Terminate: SendResponse fails with erro"...
0x18000d897  mov     word ptr [rsp+880h+var_820], cx
0x18000d89c  mov     r8d, eax
0x18000d89f  lea     rcx, [rsp+880h+var_820]
0x18000d8a4  call    FormatRRASErrorString
0x18000d8a9  test    cs:byte_18002E903, 8
0x18000d8b0  jz      short loc_18000D8CA
0x18000d8b2  lea     r8, [rsp+880h+var_820]
0x18000d8b7  lea     rdx, RasSSTPSvcTraceError
0x18000d8be  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d8c5  call    McTemplateU0z_EventWriteTransfer
0x18000d8ca  mov     rcx, cs:SstpSvcGlobals
0x18000d8d1  mov     rcx, [rcx+0A8h]; pio
0x18000d8d8  call    cs:__imp_CancelThreadpoolIo
0x18000d8df  nop     dword ptr [rax+rax+00h]
0x18000d8e4  mov     rcx, cs:SstpSvcGlobals
0x18000d8eb  mov     r8b, r13b
0x18000d8ee  add     rcx, 1A8h
0x18000d8f5  mov     rdx, rdi
0x18000d8f8  call    FreeBufferToPool
0x18000d8fd  test    cs:byte_18002E903, 10h
0x18000d904  jz      short loc_18000D946
0x18000d906  xor     eax, eax
0x18000d908  lea     r8, aTerminateparti_0; "TerminatePartialConnection"
0x18000d90f  lea     rdx, aLeavingWs; "LEaving %ws"
0x18000d916  mov     word ptr [rsp+880h+var_820], ax
0x18000d91b  lea     rcx, [rsp+880h+var_820]
0x18000d920  call    FormatRRASErrorString
0x18000d925  test    cs:byte_18002E903, 10h
0x18000d92c  jz      short loc_18000D946
0x18000d92e  lea     r8, [rsp+880h+var_820]
0x18000d933  lea     rdx, RasSSTPSvcTraceInfo
0x18000d93a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d941  call    McTemplateU0z_EventWriteTransfer
0x18000d946  mov     eax, ebx
0x18000d948  mov     rcx, [rbp+780h+var_20]
0x18000d94f  xor     rcx, rsp; StackCookie
0x18000d952  call    __security_check_cookie
0x18000d957  lea     r11, [rsp+880h+var_10]
0x18000d95f  mov     rbx, [r11+30h]
0x18000d963  mov     rsi, [r11+38h]
0x18000d967  mov     rsp, r11
0x18000d96a  pop     r13
0x18000d96c  pop     rdi
0x18000d96d  pop     rbp
0x18000d96e  retn
```
