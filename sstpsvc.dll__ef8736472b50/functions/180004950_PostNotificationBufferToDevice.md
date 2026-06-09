# PostNotificationBufferToDevice

- ea: `0x180004950`
- end: `0x180004bd4`
- name: `PostNotificationBufferToDevice`
- size: `644`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180003bc0`
- `0x18000aa44`

## callees

- `0x180002f80`
- `0x180004950`
- `0x1800089dc`
- `0x180008b90`
- `0x18001d1da`
- `0x18001d210`
- `0x18001d2a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a75`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180004a65`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180004a65`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180004a9c`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180004a9c`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180004a21`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180004a21`

## pseudocode

```c
__int64 __fastcall PostNotificationBufferToDevice(__int64 a1)
{
  __int64 v2; // r8
  DWORD LastError; // eax
  DWORD v4; // ebx
  int v6; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v7[2044]; // [rsp+54h] [rbp-ACh] BYREF
  int v8; // [rsp+850h] [rbp+750h] BYREF
  _BYTE v9[2044]; // [rsp+854h] [rbp+754h] BYREF

  v8 = 0;
  memset_0(v9, 0, sizeof(v9));
  *(_OWORD *)a1 = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_DWORD *)(a1 + 32) = 17769;
  v6 = 0;
  memset_0(v7, 0, sizeof(v7));
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v6) = 0;
    FormatRRASErrorString(&v6, L"Entering %ws", L"AsyncSstpDeviceControl");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v6);
  }
  StartThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 36));
  if ( DeviceIoControl(
         *((HANDLE *)SstpSvcGlobals + 35),
         0x128038u,
         0,
         0,
         (LPVOID)(a1 + 40),
         0x2010u,
         0,
         (LPOVERLAPPED)a1)
    || (LastError = GetLastError(), v4 = LastError, LastError == 997)
    || !LastError )
  {
    v4 = 0;
  }
  else
  {
    CancelThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 36));
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v6) = 0;
      FormatRRASErrorString(&v6, L"AsyncSstpDeviceIoControl fails with [%d]", v4);
      if ( (byte_18002E903 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v6);
    }
  }
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v6) = 0;
    FormatRRASErrorString(&v6, L"LEaving %ws", L"AsyncSstpDeviceControl");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v6);
  }
  if ( v4 )
  {
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v8) = 0;
      FormatRRASErrorString(&v8, L"Failure to queue mini-send buffers - %d", v4);
      if ( (byte_18002E903 & 8) != 0 )
      {
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v8);
        if ( (byte_18002E903 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasSSTPSvcTraceError,
            L"Freeing up the buffer");
      }
    }
    LOBYTE(v2) = 1;
    FreeBufferToPool((char *)SstpSvcGlobals + 312, a1, v2);
  }
  return v4;
}

```

## disassembly

```asm
0x180004950  push    rbp
0x180004952  push    rbx
0x180004953  push    rdi
0x180004954  push    r14
0x180004956  lea     rbp, [rsp-0F68h]
0x18000495e  mov     eax, 1068h
0x180004963  call    _alloca_probe
0x180004968  sub     rsp, rax
0x18000496b  mov     rax, cs:__security_cookie
0x180004972  xor     rax, rsp
0x180004975  mov     [rbp+0F80h+var_30], rax
0x18000497c  mov     rdi, rcx
0x18000497f  xor     eax, eax
0x180004981  mov     ebx, 7FCh
0x180004986  mov     [rbp+0F80h+var_830], eax
0x18000498c  mov     r8d, ebx; Size
0x18000498f  lea     rcx, [rbp+0F80h+var_82C]; void *
0x180004996  xor     edx, edx; Val
0x180004998  call    memset_0
0x18000499d  xorps   xmm0, xmm0
0x1800049a0  lea     rcx, [rsp+1080h+var_102C]; void *
0x1800049a5  movups  xmmword ptr [rdi], xmm0
0x1800049a8  xor     eax, eax
0x1800049aa  mov     r8d, ebx; Size
0x1800049ad  movups  xmmword ptr [rdi+10h], xmm0
0x1800049b1  mov     [rdi+20h], rax
0x1800049b5  xor     edx, edx; Val
0x1800049b7  mov     dword ptr [rdi+20h], 4569h
0x1800049be  mov     [rsp+1080h+var_1030], eax
0x1800049c2  call    memset_0
0x1800049c7  test    cs:byte_18002E903, 10h
0x1800049ce  lea     r14, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800049d5  jz      short loc_180004A13
0x1800049d7  xor     eax, eax
0x1800049d9  lea     r8, aAsyncsstpdevic_0; "AsyncSstpDeviceControl"
0x1800049e0  lea     rdx, aEnteringWs; "Entering %ws"
0x1800049e7  mov     word ptr [rsp+1080h+var_1030], ax
0x1800049ec  lea     rcx, [rsp+1080h+var_1030]
0x1800049f1  call    FormatRRASErrorString
0x1800049f6  test    cs:byte_18002E903, 10h
0x1800049fd  jz      short loc_180004A13
0x1800049ff  lea     r8, [rsp+1080h+var_1030]
0x180004a04  mov     rcx, r14
0x180004a07  lea     rdx, RasSSTPSvcTraceInfo
0x180004a0e  call    McTemplateU0z_EventWriteTransfer
0x180004a13  mov     rcx, cs:SstpSvcGlobals
0x180004a1a  mov     rcx, [rcx+120h]; pio
0x180004a21  call    cs:__imp_StartThreadpoolIo
0x180004a28  nop     dword ptr [rax+rax+00h]
0x180004a2d  mov     rcx, cs:SstpSvcGlobals
0x180004a34  lea     rax, [rdi+28h]
0x180004a38  mov     [rsp+1080h+lpOverlapped], rdi; lpOverlapped
0x180004a3d  xor     r9d, r9d; nInBufferSize
0x180004a40  mov     [rsp+1080h+lpBytesReturned], 0; lpBytesReturned
0x180004a49  xor     r8d, r8d; lpInBuffer
0x180004a4c  mov     [rsp+1080h+nOutBufferSize], 2010h; nOutBufferSize
0x180004a54  mov     edx, 128038h; dwIoControlCode
0x180004a59  mov     rcx, [rcx+118h]; hDevice
0x180004a60  mov     [rsp+1080h+lpOutBuffer], rax; lpOutBuffer
0x180004a65  call    cs:__imp_DeviceIoControl
0x180004a6c  nop     dword ptr [rax+rax+00h]
0x180004a71  test    eax, eax
0x180004a73  jnz     short loc_180004AEB
0x180004a75  call    cs:__imp_GetLastError
0x180004a7c  nop     dword ptr [rax+rax+00h]
0x180004a81  mov     ebx, eax
0x180004a83  cmp     eax, 3E5h
0x180004a88  jz      short loc_180004AEB
0x180004a8a  test    eax, eax
0x180004a8c  jz      short loc_180004AEB
0x180004a8e  mov     rcx, cs:SstpSvcGlobals
0x180004a95  mov     rcx, [rcx+120h]; pio
0x180004a9c  call    cs:__imp_CancelThreadpoolIo
0x180004aa3  nop     dword ptr [rax+rax+00h]
0x180004aa8  test    cs:byte_18002E903, 8
0x180004aaf  jz      short loc_180004AED
0x180004ab1  xor     eax, eax
0x180004ab3  lea     rdx, aAsyncsstpdevic; "AsyncSstpDeviceIoControl fails with [%d"...
0x180004aba  mov     r8d, ebx
0x180004abd  mov     word ptr [rsp+1080h+var_1030], ax
0x180004ac2  lea     rcx, [rsp+1080h+var_1030]
0x180004ac7  call    FormatRRASErrorString
0x180004acc  test    cs:byte_18002E903, 8
0x180004ad3  jz      short loc_180004AED
0x180004ad5  lea     r8, [rsp+1080h+var_1030]
0x180004ada  mov     rcx, r14
0x180004add  lea     rdx, RasSSTPSvcTraceError
0x180004ae4  call    McTemplateU0z_EventWriteTransfer
0x180004ae9  jmp     short loc_180004AED
0x180004aeb  xor     ebx, ebx
0x180004aed  test    cs:byte_18002E903, 10h
0x180004af4  jz      short loc_180004B32
0x180004af6  xor     eax, eax
0x180004af8  lea     r8, aAsyncsstpdevic_0; "AsyncSstpDeviceControl"
0x180004aff  lea     rdx, aLeavingWs; "LEaving %ws"
0x180004b06  mov     word ptr [rsp+1080h+var_1030], ax
0x180004b0b  lea     rcx, [rsp+1080h+var_1030]
0x180004b10  call    FormatRRASErrorString
0x180004b15  test    cs:byte_18002E903, 10h
0x180004b1c  jz      short loc_180004B32
0x180004b1e  lea     r8, [rsp+1080h+var_1030]
0x180004b23  mov     rcx, r14
0x180004b26  lea     rdx, RasSSTPSvcTraceInfo
0x180004b2d  call    McTemplateU0z_EventWriteTransfer
0x180004b32  test    ebx, ebx
0x180004b34  jz      short loc_180004BB5
0x180004b36  test    cs:byte_18002E903, 8
0x180004b3d  jz      short loc_180004B9C
0x180004b3f  xor     eax, eax
0x180004b41  lea     rdx, aFailureToQueue; "Failure to queue mini-send buffers - %d"
0x180004b48  mov     r8d, ebx
0x180004b4b  mov     word ptr [rbp+0F80h+var_830], ax
0x180004b52  lea     rcx, [rbp+0F80h+var_830]
0x180004b59  call    FormatRRASErrorString
0x180004b5e  test    cs:byte_18002E903, 8
0x180004b65  jz      short loc_180004B9C
0x180004b67  lea     r8, [rbp+0F80h+var_830]
0x180004b6e  mov     rcx, r14
0x180004b71  lea     rdx, RasSSTPSvcTraceError
0x180004b78  call    McTemplateU0z_EventWriteTransfer
0x180004b7d  test    cs:byte_18002E903, 8
0x180004b84  jz      short loc_180004B9C
0x180004b86  lea     r8, aFreeingUpTheBu; "Freeing up the buffer"
0x180004b8d  mov     rcx, r14
0x180004b90  lea     rdx, RasSSTPSvcTraceError
0x180004b97  call    McTemplateU0z_EventWriteTransfer
0x180004b9c  mov     rcx, cs:SstpSvcGlobals
0x180004ba3  mov     r8b, 1
0x180004ba6  add     rcx, 138h
0x180004bad  mov     rdx, rdi
0x180004bb0  call    FreeBufferToPool
0x180004bb5  mov     eax, ebx
0x180004bb7  mov     rcx, [rbp+0F80h+var_30]
0x180004bbe  xor     rcx, rsp; StackCookie
0x180004bc1  call    __security_check_cookie
0x180004bc6  add     rsp, 1068h
0x180004bcd  pop     r14
0x180004bcf  pop     rdi
0x180004bd0  pop     rbx
0x180004bd1  pop     rbp
0x180004bd2  retn
```
