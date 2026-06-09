# AsyncSstpDeviceControl

- ea: `0x180005110`
- end: `0x180005305`
- name: `AsyncSstpDeviceControl`
- size: `501`
- prototype: `__int64 __fastcall(DWORD dwIoControlCode, LPVOID lpInBuffer, DWORD nInBufferSize, LPVOID lpOutBuffer, DWORD, LPOVERLAPPED)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800012b0`
- `0x18000ca68`
- `0x18000da7c`

## callees

- `0x180005110`
- `0x1800089dc`
- `0x180008b90`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051c6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800051b6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800051b6`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000521d`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000521d`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180005176`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180005176`

## pseudocode

```c
__int64 __fastcall AsyncSstpDeviceControl(
        DWORD dwIoControlCode,
        LPVOID lpInBuffer,
        DWORD nInBufferSize,
        LPVOID lpOutBuffer,
        DWORD nOutBufferSize,
        LPOVERLAPPED lpOverlapped)
{
  DWORD LastError; // ebx
  int v12; // [rsp+40h] [rbp-838h] BYREF
  _BYTE v13[2044]; // [rsp+44h] [rbp-834h] BYREF

  v12 = 0;
  memset_0(v13, 0, sizeof(v13));
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v12) = 0;
    FormatRRASErrorString(&v12, L"Entering %ws", L"AsyncSstpDeviceControl");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v12);
  }
  StartThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 36));
  if ( DeviceIoControl(
         *((HANDLE *)SstpSvcGlobals + 35),
         dwIoControlCode,
         lpInBuffer,
         nInBufferSize,
         lpOutBuffer,
         nOutBufferSize,
         0,
         lpOverlapped)
    || (LastError = GetLastError(), LastError == 997)
    || !LastError )
  {
    LastError = 0;
  }
  else
  {
    CancelThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 36));
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v12) = 0;
      FormatRRASErrorString(&v12, L"AsyncSstpDeviceIoControl fails with [%d]", LastError);
      if ( (byte_18002E903 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v12);
    }
  }
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v12) = 0;
    FormatRRASErrorString(&v12, L"LEaving %ws", L"AsyncSstpDeviceControl");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v12);
  }
  return LastError;
}

```

## disassembly

```asm
0x180005110  push    rbx
0x180005112  push    rbp
0x180005113  push    rsi
0x180005114  push    rdi
0x180005115  push    r14
0x180005117  sub     rsp, 850h
0x18000511e  mov     rax, cs:__security_cookie
0x180005125  xor     rax, rsp
0x180005128  mov     [rsp+878h+var_38], rax
0x180005130  mov     r14, [rsp+878h+arg_28]
0x180005138  mov     esi, r8d
0x18000513b  mov     rdi, rdx
0x18000513e  mov     ebx, ecx
0x180005140  xor     eax, eax
0x180005142  lea     rcx, [rsp+878h+var_834]; void *
0x180005147  xor     edx, edx; Val
0x180005149  mov     [rsp+878h+var_838], eax
0x18000514d  mov     r8d, 7FCh; Size
0x180005153  mov     rbp, r9
0x180005156  call    memset_0
0x18000515b  test    cs:byte_18002E903, 10h
0x180005162  jnz     loc_180005273
0x180005168  mov     rcx, cs:SstpSvcGlobals
0x18000516f  mov     rcx, [rcx+120h]; pio
0x180005176  call    cs:__imp_StartThreadpoolIo
0x18000517d  nop     dword ptr [rax+rax+00h]
0x180005182  mov     rcx, cs:SstpSvcGlobals
0x180005189  mov     r9d, esi; nInBufferSize
0x18000518c  mov     eax, [rsp+878h+arg_20]
0x180005193  mov     r8, rdi; lpInBuffer
0x180005196  mov     [rsp+878h+lpOverlapped], r14; lpOverlapped
0x18000519b  mov     edx, ebx; dwIoControlCode
0x18000519d  mov     [rsp+878h+lpBytesReturned], 0; lpBytesReturned
0x1800051a6  mov     rcx, [rcx+118h]; hDevice
0x1800051ad  mov     [rsp+878h+nOutBufferSize], eax; nOutBufferSize
0x1800051b1  mov     [rsp+878h+lpOutBuffer], rbp; lpOutBuffer
0x1800051b6  call    cs:__imp_DeviceIoControl
0x1800051bd  nop     dword ptr [rax+rax+00h]
0x1800051c2  test    eax, eax
0x1800051c4  jnz     short loc_1800051DB
0x1800051c6  call    cs:__imp_GetLastError
0x1800051cd  nop     dword ptr [rax+rax+00h]
0x1800051d2  mov     ebx, eax
0x1800051d4  cmp     eax, 3E5h
0x1800051d9  jnz     short loc_18000520B
0x1800051db  xor     ebx, ebx
0x1800051dd  test    cs:byte_18002E903, 10h
0x1800051e4  jnz     loc_1800052BC
0x1800051ea  mov     eax, ebx
0x1800051ec  mov     rcx, [rsp+878h+var_38]
0x1800051f4  xor     rcx, rsp; StackCookie
0x1800051f7  call    __security_check_cookie
0x1800051fc  add     rsp, 850h
0x180005203  pop     r14
0x180005205  pop     rdi
0x180005206  pop     rsi
0x180005207  pop     rbp
0x180005208  pop     rbx
0x180005209  retn
0x18000520b  test    ebx, ebx
0x18000520d  jz      short loc_1800051DB
0x18000520f  mov     rcx, cs:SstpSvcGlobals
0x180005216  mov     rcx, [rcx+120h]; pio
0x18000521d  call    cs:__imp_CancelThreadpoolIo
0x180005224  nop     dword ptr [rax+rax+00h]
0x180005229  test    cs:byte_18002E903, 8
0x180005230  jz      short loc_1800051DD
0x180005232  xor     eax, eax
0x180005234  lea     rdx, aAsyncsstpdevic; "AsyncSstpDeviceIoControl fails with [%d"...
0x18000523b  mov     r8d, ebx
0x18000523e  mov     word ptr [rsp+878h+var_838], ax
0x180005243  lea     rcx, [rsp+878h+var_838]
0x180005248  call    FormatRRASErrorString
0x18000524d  test    cs:byte_18002E903, 8
0x180005254  jz      short loc_1800051DD
0x180005256  lea     r8, [rsp+878h+var_838]
0x18000525b  lea     rdx, RasSSTPSvcTraceError
0x180005262  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005269  call    McTemplateU0z_EventWriteTransfer
0x18000526e  jmp     loc_1800051DD
0x180005273  xor     eax, eax
0x180005275  lea     r8, aAsyncsstpdevic_0; "AsyncSstpDeviceControl"
0x18000527c  lea     rdx, aEnteringWs; "Entering %ws"
0x180005283  mov     word ptr [rsp+878h+var_838], ax
0x180005288  lea     rcx, [rsp+878h+var_838]
0x18000528d  call    FormatRRASErrorString
0x180005292  test    cs:byte_18002E903, 10h
0x180005299  jz      loc_180005168
0x18000529f  lea     r8, [rsp+878h+var_838]
0x1800052a4  lea     rdx, RasSSTPSvcTraceInfo
0x1800052ab  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800052b2  call    McTemplateU0z_EventWriteTransfer
0x1800052b7  jmp     loc_180005168
0x1800052bc  xor     eax, eax
0x1800052be  lea     r8, aAsyncsstpdevic_0; "AsyncSstpDeviceControl"
0x1800052c5  lea     rdx, aLeavingWs; "LEaving %ws"
0x1800052cc  mov     word ptr [rsp+878h+var_838], ax
0x1800052d1  lea     rcx, [rsp+878h+var_838]
0x1800052d6  call    FormatRRASErrorString
0x1800052db  test    cs:byte_18002E903, 10h
0x1800052e2  jz      loc_1800051EA
0x1800052e8  lea     r8, [rsp+878h+var_838]
0x1800052ed  lea     rdx, RasSSTPSvcTraceInfo
0x1800052f4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800052fb  call    McTemplateU0z_EventWriteTransfer
0x180005300  jmp     loc_1800051EA
```
