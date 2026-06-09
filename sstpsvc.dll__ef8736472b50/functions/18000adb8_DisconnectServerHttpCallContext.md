# DisconnectServerHttpCallContext

- ea: `0x18000adb8`
- end: `0x18000afa4`
- name: `DisconnectServerHttpCallContext`
- size: `492`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180002aac`

## callees

- `0x180002aac`
- `0x1800089dc`
- `0x180008b90`
- `0x18000adb8`
- `0x18000d730`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000af5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000af5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae2a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae2a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae78`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000af4e`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000af4e`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000ae92`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000ae92`
- `HTTPAPI!HttpSendResponseEntityBody` at `0x18000aed5`
- `HTTPAPI!HttpSendResponseEntityBody` at `0x18000aed5`

## string_xrefs

- `0x18000af0b`: `CoId=%hs:SendResponse completes with %d`

## pseudocode

```c
ULONG __fastcall DisconnectServerHttpCallContext(__int64 a1)
{
  int v2; // eax
  struct _RTL_CRITICAL_SECTION *v3; // rcx
  struct _OVERLAPPED *v4; // rbx
  ULONG result; // eax
  int v6; // [rsp+50h] [rbp-818h] BYREF
  _BYTE v7[2044]; // [rsp+54h] [rbp-814h] BYREF

  v6 = 0;
  memset_0(v7, 0, sizeof(v7));
  v2 = *(_DWORD *)(a1 + 252);
  v3 = (struct _RTL_CRITICAL_SECTION *)(a1 + 288);
  if ( (v2 & 2) != 0 )
  {
    v4 = *(struct _OVERLAPPED **)(a1 + 256);
    *(_DWORD *)(a1 + 252) = v2 & 0xFFFFFFFD;
    *(_QWORD *)(a1 + 256) = 0;
    v4[1].hEvent = (HANDLE)a1;
    LeaveCriticalSection(v3);
    result = TerminatePartialConnection(*(_QWORD *)(a1 + 272), v4);
    if ( result && result != 997 )
    {
LABEL_11:
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
      *(_DWORD *)(a1 + 252) &= ~0x2000u;
      return InitiateCallContextCleanup(a1, 2);
    }
  }
  else
  {
    *(_DWORD *)(a1 + 200) = 17775;
    *(_OWORD *)(a1 + 168) = 0;
    *(_OWORD *)(a1 + 184) = 0;
    LeaveCriticalSection(v3);
    StartThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
    result = HttpSendResponseEntityBody(
               *((HANDLE *)SstpSvcGlobals + 8),
               *(_QWORD *)(a1 + 272),
               1u,
               0,
               0,
               0,
               0,
               0,
               (LPOVERLAPPED)(a1 + 168),
               0);
    if ( result != 997 && result )
    {
      if ( (byte_18002E903 & 8) != 0 )
      {
        LOWORD(v6) = 0;
        FormatRRASErrorString(&v6, L"CoId=%hs:SendResponse completes with %d", a1 + 552, result);
        if ( (byte_18002E903 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v6);
      }
      CancelThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
      goto LABEL_11;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000adb8  mov     [rsp+arg_8], rbx
0x18000adbd  mov     [rsp+arg_10], rsi
0x18000adc2  push    rdi
0x18000adc3  sub     rsp, 860h
0x18000adca  mov     rax, cs:__security_cookie
0x18000add1  xor     rax, rsp
0x18000add4  mov     [rsp+868h+var_18], rax
0x18000addc  mov     rdi, rcx
0x18000addf  xor     eax, eax
0x18000ade1  lea     rcx, [rsp+868h+var_814]; void *
0x18000ade6  mov     [rsp+868h+var_818], eax
0x18000adea  xor     edx, edx; Val
0x18000adec  mov     r8d, 7FCh; Size
0x18000adf2  call    memset_0
0x18000adf7  mov     eax, [rdi+0FCh]
0x18000adfd  lea     rsi, [rdi+120h]
0x18000ae04  mov     rcx, rsi; lpCriticalSection
0x18000ae07  test    al, 2
0x18000ae09  jz      short loc_18000AE5D
0x18000ae0b  mov     rbx, [rdi+100h]
0x18000ae12  and     eax, 0FFFFFFFDh
0x18000ae15  mov     [rdi+0FCh], eax
0x18000ae1b  mov     qword ptr [rdi+100h], 0
0x18000ae26  mov     [rbx+38h], rdi
0x18000ae2a  call    cs:__imp_LeaveCriticalSection
0x18000ae31  nop     dword ptr [rax+rax+00h]
0x18000ae36  mov     rcx, [rdi+110h]; RequestId
0x18000ae3d  mov     rdx, rbx; Overlapped
0x18000ae40  call    TerminatePartialConnection
0x18000ae45  test    eax, eax
0x18000ae47  jz      loc_18000AF7E
0x18000ae4d  cmp     eax, 3E5h
0x18000ae52  jz      loc_18000AF7E
0x18000ae58  jmp     loc_18000AF5A
0x18000ae5d  xorps   xmm0, xmm0
0x18000ae60  mov     dword ptr [rdi+0C8h], 456Fh
0x18000ae6a  lea     rbx, [rdi+0A8h]
0x18000ae71  movups  xmmword ptr [rbx], xmm0
0x18000ae74  movups  xmmword ptr [rbx+10h], xmm0
0x18000ae78  call    cs:__imp_LeaveCriticalSection
0x18000ae7f  nop     dword ptr [rax+rax+00h]
0x18000ae84  mov     rcx, cs:SstpSvcGlobals
0x18000ae8b  mov     rcx, [rcx+0A8h]; pio
0x18000ae92  call    cs:__imp_StartThreadpoolIo
0x18000ae99  nop     dword ptr [rax+rax+00h]
0x18000ae9e  mov     rcx, cs:SstpSvcGlobals
0x18000aea5  xor     r9d, r9d; EntityChunkCount
0x18000aea8  mov     rdx, [rdi+110h]; RequestId
0x18000aeaf  mov     [rsp+868h+LogData], r9; LogData
0x18000aeb4  mov     [rsp+868h+Overlapped], rbx; Overlapped
0x18000aeb9  mov     rcx, [rcx+40h]; RequestQueueHandle
0x18000aebd  lea     r8d, [r9+1]; Flags
0x18000aec1  mov     [rsp+868h+Reserved2], r9d; Reserved2
0x18000aec6  mov     [rsp+868h+Reserved1], r9; Reserved1
0x18000aecb  mov     [rsp+868h+BytesSent], r9; BytesSent
0x18000aed0  mov     [rsp+868h+EntityChunks], r9; EntityChunks
0x18000aed5  call    cs:__imp_HttpSendResponseEntityBody
0x18000aedc  nop     dword ptr [rax+rax+00h]
0x18000aee1  cmp     eax, 3E5h
0x18000aee6  jz      loc_18000AF7E
0x18000aeec  test    eax, eax
0x18000aeee  jz      loc_18000AF7E
0x18000aef4  test    cs:byte_18002E903, 8
0x18000aefb  jz      short loc_18000AF40
0x18000aefd  xor     ecx, ecx
0x18000aeff  lea     r8, [rdi+228h]
0x18000af06  mov     word ptr [rsp+868h+var_818], cx
0x18000af0b  lea     rdx, aCoidHsSendresp; "CoId=%hs:SendResponse completes with %d"
0x18000af12  lea     rcx, [rsp+868h+var_818]
0x18000af17  mov     r9d, eax
0x18000af1a  call    FormatRRASErrorString
0x18000af1f  test    cs:byte_18002E903, 8
0x18000af26  jz      short loc_18000AF40
0x18000af28  lea     r8, [rsp+868h+var_818]
0x18000af2d  lea     rdx, RasSSTPSvcTraceError
0x18000af34  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000af3b  call    McTemplateU0z_EventWriteTransfer
0x18000af40  mov     rcx, cs:SstpSvcGlobals
0x18000af47  mov     rcx, [rcx+0A8h]; pio
0x18000af4e  call    cs:__imp_CancelThreadpoolIo
0x18000af55  nop     dword ptr [rax+rax+00h]
0x18000af5a  mov     rcx, rsi; lpCriticalSection
0x18000af5d  call    cs:__imp_EnterCriticalSection
0x18000af64  nop     dword ptr [rax+rax+00h]
0x18000af69  btr     dword ptr [rdi+0FCh], 0Dh
0x18000af71  mov     edx, 2
0x18000af76  mov     rcx, rdi
0x18000af79  call    InitiateCallContextCleanup
0x18000af7e  mov     rcx, [rsp+868h+var_18]
0x18000af86  xor     rcx, rsp; StackCookie
0x18000af89  call    __security_check_cookie
0x18000af8e  lea     r11, [rsp+868h+var_8]
0x18000af96  mov     rbx, [r11+18h]
0x18000af9a  mov     rsi, [r11+20h]
0x18000af9e  mov     rsp, r11
0x18000afa1  pop     rdi
0x18000afa2  retn
```
