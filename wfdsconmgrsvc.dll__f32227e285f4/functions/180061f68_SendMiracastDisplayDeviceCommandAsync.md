# SendMiracastDisplayDeviceCommandAsync

- ea: `0x180061f68`
- end: `0x18006205b`
- name: `SendMiracastDisplayDeviceCommandAsync`
- size: `243`
- prototype: `signed int __fastcall(WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180043b80`

## callees

- `0x180061b70`
- `0x180061cc8`
- `0x180061f68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061fe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062026`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062033`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061fe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062026`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062033`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180061fa6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180061fa6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061f94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061f94`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006201c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006201c`
- `ntdll!RtlSetIoCompletionCallback` at `0x180061fd7`
- `ntdll!RtlSetIoCompletionCallback` at `0x180061fd7`

## pseudocode

```c
signed int __fastcall SendMiracastDisplayDeviceCommandAsync(WCHAR *a1, __int64 a2)
{
  DWORD v2; // ebp
  signed int result; // eax
  unsigned int v4; // ebx
  HANDLE ProcessHeap; // rax
  DWORD *v6; // rax
  DWORD *lpOverlapped; // rdi
  HANDLE v8; // rsi
  HANDLE v9; // rcx
  signed int v10; // eax
  signed int LastError; // eax
  HANDLE FileHandle; // [rsp+88h] [rbp+20h] BYREF

  FileHandle = 0;
  v2 = a2;
  result = CreateMiracastDisplayCommandChannel(a1, a2, &FileHandle);
  v4 = result;
  if ( result >= 0 )
  {
    ProcessHeap = GetProcessHeap();
    v6 = (DWORD *)HeapAlloc(ProcessHeap, 8u, 0x38u);
    lpOverlapped = v6;
    if ( !v6 )
      return -2147024882;
    v8 = FileHandle;
    v9 = FileHandle;
    *((_QWORD *)v6 + 4) = FileHandle;
    if ( RtlSetIoCompletionCallback(v9, lambda_68a0aeba6efd19ebb1d21c71924048c5_::_lambda_invoker_cdecl_, 0)
      || (v10 = GetLastError(), v4 = v10 | 0x10000000, v10 >= 0) )
    {
      if ( !DeviceIoControl(
              v8,
              v2,
              *((LPVOID *)lpOverlapped + 6),
              0,
              0,
              0,
              lpOverlapped + 10,
              (LPOVERLAPPED)lpOverlapped)
        && GetLastError() != 997 )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        SendMiracastDisplayDeviceCommandAsync_::_2_::AsyncCompletion::Free(lpOverlapped);
      }
    }
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180061f68  mov     rax, rsp
0x180061f6b  mov     [rax+20h], r9
0x180061f6f  push    rbx
0x180061f70  push    rbp
0x180061f71  push    rsi
0x180061f72  push    rdi
0x180061f73  sub     rsp, 48h
0x180061f77  lea     r8, [rax+20h]
0x180061f7b  mov     qword ptr [rax+20h], 0
0x180061f83  mov     ebp, edx
0x180061f85  call    CreateMiracastDisplayCommandChannel
0x180061f8a  mov     ebx, eax
0x180061f8c  test    eax, eax
0x180061f8e  js      loc_180062052
0x180061f94  call    cs:__imp_GetProcessHeap
0x180061f9a  mov     edx, 8; dwFlags
0x180061f9f  mov     rcx, rax; hHeap
0x180061fa2  lea     r8d, [rdx+30h]; dwBytes
0x180061fa6  call    cs:__imp_HeapAlloc
0x180061fac  mov     rdi, rax
0x180061faf  test    rax, rax
0x180061fb2  jnz     short loc_180061FBE
0x180061fb4  mov     ebx, 8007000Eh
0x180061fb9  jmp     loc_180062050
0x180061fbe  mov     rsi, [rsp+68h+FileHandle]
0x180061fc6  lea     rdx, _lambda_68a0aeba6efd19ebb1d21c71924048c5____lambda_invoker_cdecl_; Callback
0x180061fcd  mov     rcx, rsi; FileHandle
0x180061fd0  mov     [rax+20h], rsi
0x180061fd4  xor     r8d, r8d; Flags
0x180061fd7  call    cs:__imp_RtlSetIoCompletionCallback
0x180061fdd  test    eax, eax
0x180061fdf  jnz     short loc_180061FF1
0x180061fe1  call    cs:__imp_GetLastError
0x180061fe7  mov     ebx, eax
0x180061fe9  or      ebx, 10000000h
0x180061fef  jl      short loc_180062050
0x180061ff1  mov     r8, [rdi+30h]; lpInBuffer
0x180061ff5  lea     rax, [rdi+28h]
0x180061ff9  mov     [rsp+68h+lpOverlapped], rdi; lpOverlapped
0x180061ffe  xor     r9d, r9d; nInBufferSize
0x180062001  mov     [rsp+68h+lpBytesReturned], rax; lpBytesReturned
0x180062006  mov     edx, ebp; dwIoControlCode
0x180062008  mov     [rsp+68h+nOutBufferSize], 0; nOutBufferSize
0x180062010  mov     rcx, rsi; hDevice
0x180062013  mov     [rsp+68h+lpOutBuffer], 0; lpOutBuffer
0x18006201c  call    cs:__imp_DeviceIoControl
0x180062022  test    eax, eax
0x180062024  jnz     short loc_180062050
0x180062026  call    cs:__imp_GetLastError
0x18006202c  cmp     eax, 3E5h
0x180062031  jz      short loc_180062050
0x180062033  call    cs:__imp_GetLastError
0x180062039  mov     ebx, eax
0x18006203b  test    eax, eax
0x18006203d  jle     short loc_180062048
0x18006203f  movzx   ebx, ax
0x180062042  or      ebx, 80070000h
0x180062048  mov     rcx, rdi
0x18006204b  call    _SendMiracastDisplayDeviceCommandAsync____2___AsyncCompletion__Free
0x180062050  mov     eax, ebx
0x180062052  add     rsp, 48h
0x180062056  pop     rdi
0x180062057  pop     rsi
0x180062058  pop     rbp
0x180062059  pop     rbx
0x18006205a  retn
```
