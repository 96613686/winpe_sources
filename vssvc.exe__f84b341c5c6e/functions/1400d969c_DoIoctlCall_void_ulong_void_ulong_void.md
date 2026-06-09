# DoIoctlCall(void *,ulong,void *,ulong,void * *)

- ea: `0x1400d969c`
- end: `0x1400d97da`
- name: `?DoIoctlCall@@YAHPEAXK0KPEAPEAX@Z`
- size: `318`
- prototype: `__int64 __fastcall(HANDLE hDevice, DWORD dwIoControlCode, void *lpInBuffer, DWORD nInBufferSize, void **)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400d2d28`
- `0x1400d365c`
- `0x1400d4088`
- `0x1400d4e88`
- `0x1400d5a34`

## callees

- `0x140025abc`
- `0x1400d257c`
- `0x1400d969c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d97c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d97c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d9715`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d9715`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400d970b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400d970b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d96c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d97bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d96c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d97bb`

## pseudocode

```c
__int64 __fastcall DoIoctlCall(HANDLE hDevice, DWORD dwIoControlCode, void *lpInBuffer, DWORD nInBufferSize, void **a5)
{
  void *lpOutBuffer; // rdi
  DWORD v10; // esi
  DWORD LastError; // eax
  DWORD v12; // ebx
  unsigned int v13; // esi
  DWORD BytesReturned[18]; // [rsp+40h] [rbp-48h] BYREF

  BytesReturned[0] = 100;
  lpOutBuffer = 0;
  while ( 1 )
  {
    CoTaskMemFree(lpOutBuffer);
    lpOutBuffer = ASR_ALLOC(BytesReturned[0]);
    if ( !lpOutBuffer )
      break;
    v10 = BytesReturned[0];
    if ( DeviceIoControl(
           hDevice,
           dwIoControlCode,
           lpInBuffer,
           nInBufferSize,
           lpOutBuffer,
           BytesReturned[0],
           BytesReturned,
           0) )
    {
      v12 = 0;
      v13 = 1;
      if ( a5 )
      {
        *a5 = lpOutBuffer;
        lpOutBuffer = 0;
      }
      goto LABEL_16;
    }
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError != 234 && LastError != 122 )
    {
      v13 = 0;
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        WPP_SF_Ds(
          *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
          11,
          (unsigned int)WPP_f7ece1803a8e322538ac3179d1a80580_Traceguids,
          LastError,
          "dwLastError");
      }
      goto LABEL_16;
    }
    if ( BytesReturned[0] <= v10 )
      BytesReturned[0] = 2 * v10;
  }
  v13 = 0;
  v12 = 14;
  if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
  {
    WPP_SF_Ds(
      *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
      10,
      (unsigned int)WPP_f7ece1803a8e322538ac3179d1a80580_Traceguids,
      14,
      "pIoctlOutputBuffer");
  }
LABEL_16:
  CoTaskMemFree(lpOutBuffer);
  SetLastError(v12);
  return v13;
}

```

## disassembly

```asm
0x1400d969c  push    rbx
0x1400d969e  push    rbp
0x1400d969f  push    rsi
0x1400d96a0  push    rdi
0x1400d96a1  push    r12
0x1400d96a3  push    r14
0x1400d96a5  push    r15
0x1400d96a7  sub     rsp, 50h
0x1400d96ab  mov     ebp, r9d
0x1400d96ae  mov     r14, r8
0x1400d96b1  mov     r15d, edx
0x1400d96b4  mov     r12, rcx
0x1400d96b7  mov     [rsp+88h+BytesReturned], 64h ; 'd'
0x1400d96bf  xor     edi, edi
0x1400d96c1  mov     rcx, rdi; pv
0x1400d96c4  call    cs:__imp_CoTaskMemFree
0x1400d96ca  mov     ecx, [rsp+88h+BytesReturned]; Size
0x1400d96ce  call    ?ASR_ALLOC@@YAPEAXK@Z; ASR_ALLOC(ulong)
0x1400d96d3  mov     rdi, rax
0x1400d96d6  test    rax, rax
0x1400d96d9  jz      loc_1400D9778
0x1400d96df  mov     esi, [rsp+88h+BytesReturned]
0x1400d96e3  lea     rax, [rsp+88h+BytesReturned]
0x1400d96e8  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x1400d96f1  mov     r9d, ebp; nInBufferSize
0x1400d96f4  mov     [rsp+88h+lpBytesReturned], rax; lpBytesReturned
0x1400d96f9  mov     r8, r14; lpInBuffer
0x1400d96fc  mov     [rsp+88h+nOutBufferSize], esi; nOutBufferSize
0x1400d9700  mov     edx, r15d; dwIoControlCode
0x1400d9703  mov     rcx, r12; hDevice
0x1400d9706  mov     [rsp+88h+lpOutBuffer], rdi; lpOutBuffer
0x1400d970b  call    cs:__imp_DeviceIoControl
0x1400d9711  test    eax, eax
0x1400d9713  jnz     short loc_1400D975F
0x1400d9715  call    cs:__imp_GetLastError
0x1400d971b  mov     ebx, eax
0x1400d971d  cmp     eax, 0EAh
0x1400d9722  jz      short loc_1400D9729
0x1400d9724  cmp     eax, 7Ah ; 'z'
0x1400d9727  jnz     short loc_1400D9738
0x1400d9729  cmp     [rsp+88h+BytesReturned], esi
0x1400d972d  ja      short loc_1400D96C1
0x1400d972f  lea     eax, [rsi+rsi]
0x1400d9732  mov     [rsp+88h+BytesReturned], eax
0x1400d9736  jmp     short loc_1400D96C1
0x1400d9738  xor     esi, esi
0x1400d973a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d9741  lea     rax, WPP_GLOBAL_Control
0x1400d9748  cmp     rcx, rax
0x1400d974b  jz      short loc_1400D97B8
0x1400d974d  test    byte ptr [rcx+1Ch], 8
0x1400d9751  jz      short loc_1400D97B8
0x1400d9753  lea     edx, [rsi+0Bh]
0x1400d9756  lea     rax, aDwlasterror; "dwLastError"
0x1400d975d  jmp     short loc_1400D97A0
0x1400d975f  mov     rax, [rsp+88h+arg_20]
0x1400d9767  xor     ebx, ebx
0x1400d9769  lea     esi, [rbx+1]
0x1400d976c  test    rax, rax
0x1400d976f  jz      short loc_1400D97B8
0x1400d9771  mov     [rax], rdi
0x1400d9774  xor     edi, edi
0x1400d9776  jmp     short loc_1400D97B8
0x1400d9778  xor     esi, esi
0x1400d977a  lea     ebx, [rsi+0Eh]
0x1400d977d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d9784  lea     rax, WPP_GLOBAL_Control
0x1400d978b  cmp     rcx, rax
0x1400d978e  jz      short loc_1400D97B8
0x1400d9790  test    byte ptr [rcx+1Ch], 8
0x1400d9794  jz      short loc_1400D97B8
0x1400d9796  lea     edx, [rsi+0Ah]
0x1400d9799  lea     rax, aPioctloutputbu; "pIoctlOutputBuffer"
0x1400d97a0  mov     rcx, [rcx+10h]
0x1400d97a4  lea     r8, WPP_f7ece1803a8e322538ac3179d1a80580_Traceguids
0x1400d97ab  mov     r9d, ebx
0x1400d97ae  mov     [rsp+88h+lpOutBuffer], rax
0x1400d97b3  call    WPP_SF_Ds
0x1400d97b8  mov     rcx, rdi; pv
0x1400d97bb  call    cs:__imp_CoTaskMemFree
0x1400d97c1  mov     ecx, ebx; dwErrCode
0x1400d97c3  call    cs:__imp_SetLastError
0x1400d97c9  mov     eax, esi
0x1400d97cb  add     rsp, 50h
0x1400d97cf  pop     r15
0x1400d97d1  pop     r14
0x1400d97d3  pop     r12
0x1400d97d5  pop     rdi
0x1400d97d6  pop     rsi
0x1400d97d7  pop     rbp
0x1400d97d8  pop     rbx
0x1400d97d9  retn
```
