# IssueSynchronousDeviceIoControl

- ea: `0x180004110`
- end: `0x180004269`
- name: `IssueSynchronousDeviceIoControl`
- size: `345`
- prototype: `DWORD __fastcall(HANDLE hFile, DWORD dwIoControlCode, LPVOID lpInBuffer, DWORD nInBufferSize, LPVOID lpOutBuffer, DWORD nOutBufferSize, LPDWORD lpNumberOfBytesTransferred)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x180003d30`
- `0x180004610`
- `0x180004b50`
- `0x1800061d0`
- `0x1800073d0`
- `0x180007b7c`
- `0x1800083d0`
- `0x1800085a8`
- `0x18000a184`
- `0x18000a3f8`
- `0x18000a634`
- `0x18000a8c0`
- `0x18000b620`
- `0x18000b6a0`
- `0x18000b780`
- `0x18000b8b0`

## callees

- `0x180004110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004164`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004164`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004228`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180004218`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180004218`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800041e2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800041e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000423d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000423d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004150`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004150`

## pseudocode

```c
DWORD __fastcall IssueSynchronousDeviceIoControl(
        HANDLE hFile,
        DWORD dwIoControlCode,
        LPVOID lpInBuffer,
        DWORD nInBufferSize,
        LPVOID lpOutBuffer,
        DWORD nOutBufferSize,
        LPDWORD lpNumberOfBytesTransferred)
{
  unsigned __int64 EventW; // rbx
  DWORD *lpBytesReturned; // r15
  DWORD LastError; // esi
  int v15; // [rsp+40h] [rbp-48h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+48h] [rbp-40h] BYREF

  v15 = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  EventW = (unsigned __int64)CreateEventW(0, 1, 0, 0);
  if ( !EventW )
    return GetLastError();
  lpBytesReturned = (DWORD *)&v15;
  Overlapped.Internal = 0;
  if ( lpNumberOfBytesTransferred )
    lpBytesReturned = lpNumberOfBytesTransferred;
  Overlapped.hEvent = (HANDLE)(EventW | 1);
  *(_OWORD *)&Overlapped.InternalHigh = 0;
  if ( DeviceIoControl(
         hFile,
         dwIoControlCode,
         lpInBuffer,
         nInBufferSize,
         lpOutBuffer,
         nOutBufferSize,
         lpBytesReturned,
         &Overlapped) )
  {
    goto LABEL_9;
  }
  LastError = GetLastError();
  if ( LastError == 997 )
  {
    if ( !GetOverlappedResult(hFile, &Overlapped, lpBytesReturned, 1) )
    {
      LastError = GetLastError();
      goto LABEL_10;
    }
LABEL_9:
    LastError = 0;
  }
LABEL_10:
  CloseHandle((HANDLE)EventW);
  return LastError;
}

```

## disassembly

```asm
0x180004110  mov     [rsp+arg_8], rbx
0x180004115  mov     [rsp+arg_10], rbp
0x18000411a  push    rsi
0x18000411b  push    rdi
0x18000411c  push    r14
0x18000411e  sub     rsp, 70h
0x180004122  xorps   xmm0, xmm0
0x180004125  mov     [rsp+88h+var_48], 0
0x18000412d  mov     esi, r9d
0x180004130  mov     rbp, r8
0x180004133  mov     r14d, edx
0x180004136  mov     rdi, rcx
0x180004139  xor     r9d, r9d; lpName
0x18000413c  xor     r8d, r8d; bInitialState
0x18000413f  mov     edx, 1; bManualReset
0x180004144  xor     ecx, ecx; lpEventAttributes
0x180004146  movups  xmmword ptr [rsp+88h+Overlapped.Internal], xmm0
0x18000414b  movups  xmmword ptr [rsp+88h+Overlapped.10h], xmm0
0x180004150  call    cs:__imp_CreateEventW
0x180004157  nop     dword ptr [rax+rax+00h]
0x18000415c  mov     rbx, rax
0x18000415f  test    rax, rax
0x180004162  jnz     short loc_180004175
0x180004164  call    cs:__imp_GetLastError
0x18000416b  nop     dword ptr [rax+rax+00h]
0x180004170  jmp     loc_180004253
0x180004175  mov     rax, [rsp+88h+lpNumberOfBytesTransferred]
0x18000417d  xorps   xmm0, xmm0
0x180004180  test    rax, rax
0x180004183  mov     [rsp+88h+arg_0], r15
0x18000418b  lea     r15, [rsp+88h+var_48]
0x180004190  mov     [rsp+88h+Overlapped.Internal], 0
0x180004199  cmovnz  r15, rax
0x18000419d  mov     r9d, esi; nInBufferSize
0x1800041a0  mov     rax, rbx
0x1800041a3  mov     r8, rbp; lpInBuffer
0x1800041a6  or      rax, 1
0x1800041aa  mov     edx, r14d; dwIoControlCode
0x1800041ad  mov     [rsp+88h+Overlapped.hEvent], rax
0x1800041b2  mov     rcx, rdi; hDevice
0x1800041b5  lea     rax, [rsp+88h+Overlapped]
0x1800041ba  mov     [rsp+88h+lpOverlapped], rax; lpOverlapped
0x1800041bf  mov     eax, [rsp+88h+arg_28]
0x1800041c6  mov     [rsp+88h+lpBytesReturned], r15; lpBytesReturned
0x1800041cb  mov     [rsp+88h+nOutBufferSize], eax; nOutBufferSize
0x1800041cf  mov     rax, [rsp+88h+arg_20]
0x1800041d7  mov     [rsp+88h+lpOutBuffer], rax; lpOutBuffer
0x1800041dc  movdqu  xmmword ptr [rsp+88h+Overlapped.InternalHigh], xmm0
0x1800041e2  call    cs:__imp_DeviceIoControl
0x1800041e9  nop     dword ptr [rax+rax+00h]
0x1800041ee  test    eax, eax
0x1800041f0  jnz     short loc_180004238
0x1800041f2  call    cs:__imp_GetLastError
0x1800041f9  nop     dword ptr [rax+rax+00h]
0x1800041fe  mov     esi, eax
0x180004200  cmp     eax, 3E5h
0x180004205  jnz     short loc_18000423A
0x180004207  mov     r9d, 1; bWait
0x18000420d  lea     rdx, [rsp+88h+Overlapped]; lpOverlapped
0x180004212  mov     r8, r15; lpNumberOfBytesTransferred
0x180004215  mov     rcx, rdi; hFile
0x180004218  call    cs:__imp_GetOverlappedResult
0x18000421f  nop     dword ptr [rax+rax+00h]
0x180004224  test    eax, eax
0x180004226  jnz     short loc_180004238
0x180004228  call    cs:__imp_GetLastError
0x18000422f  nop     dword ptr [rax+rax+00h]
0x180004234  mov     esi, eax
0x180004236  jmp     short loc_18000423A
0x180004238  xor     esi, esi
0x18000423a  mov     rcx, rbx; hObject
0x18000423d  call    cs:__imp_CloseHandle
0x180004244  nop     dword ptr [rax+rax+00h]
0x180004249  mov     r15, [rsp+88h+arg_0]
0x180004251  mov     eax, esi
0x180004253  lea     r11, [rsp+88h+var_18]
0x180004258  mov     rbx, [r11+28h]
0x18000425c  mov     rbp, [r11+30h]
0x180004260  mov     rsp, r11
0x180004263  pop     r14
0x180004265  pop     rdi
0x180004266  pop     rsi
0x180004267  retn
```
