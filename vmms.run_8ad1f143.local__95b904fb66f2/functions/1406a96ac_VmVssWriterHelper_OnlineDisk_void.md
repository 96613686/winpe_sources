# VmVssWriterHelper::OnlineDisk(void *)

- ea: `0x1406a96ac`
- end: `0x1406a9992`
- name: `?OnlineDisk@VmVssWriterHelper@@SAJPEAX@Z`
- size: `742`
- prototype: `__int64 __fastcall(HANDLE VirtualDiskHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14017a5a0`

## callees

- `0x140034404`
- `0x14005c630`
- `0x1404828e0`
- `0x1406a96ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1406a994a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1406a994a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1406a96f5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1406a96f5`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1406a973a`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1406a973a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1406a97c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1406a9852`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1406a98df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1406a97c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1406a9852`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1406a98df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1406a995f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1406a995f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1406a9770`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1406a9770`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1406a97b4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1406a97b4`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1406a9842`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1406a98cf`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1406a9842`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1406a98cf`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x1406a9721`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x1406a9758`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x1406a9721`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x1406a9758`

## string_xrefs

- `0x1406a990a`: `ERROR VmVssWriterHelper::OnlineDisk\n	Failed to online device physical path '%s': (HRESULT = 0x%08lX)\n`
- `0x1406a97f8`: `ERROR VmVssWriterHelper::OnlineDisk\n	Failed to open device physical path '%s': (HRESULT = 0x%08lX)\n`
- `0x1406a9881`: `ERROR VmVssWriterHelper::OnlineDisk\n	Failed to get attributes of device physical path ' %s': (HRESULT = 0x%08lX)\n`
- `0x1406a9934`: `ERROR VmVssWriterHelper::OnlineDisk\n	Failed to get device physical path: (HRESULT = 0x%08lX)\n`

## pseudocode

```c
__int64 __fastcall VmVssWriterHelper::OnlineDisk(HANDLE VirtualDiskHandle)
{
  WCHAR *v2; // rsi
  DWORD VirtualDiskPhysicalPath; // ebx
  __int64 FileW; // r14
  WCHAR *v5; // rax
  signed int LastError; // eax
  signed int v7; // eax
  __int64 v8; // rax
  bool v9; // zf
  signed int v10; // eax
  ULONG DiskPathSizeInBytes; // [rsp+48h] [rbp-1h] BYREF
  DWORD BytesReturned; // [rsp+4Ch] [rbp+3h] BYREF
  __int128 InBuffer; // [rsp+50h] [rbp+7h] BYREF
  __int128 v15; // [rsp+60h] [rbp+17h]
  __int64 v16; // [rsp+70h] [rbp+27h]
  __int128 OutBuffer; // [rsp+78h] [rbp+2Fh] BYREF

  v16 = 0;
  InBuffer = 0;
  BytesReturned = 0;
  DiskPathSizeInBytes = 50;
  v15 = 0;
  OutBuffer = 0;
  v2 = (WCHAR *)malloc(0x32u);
  if ( v2 )
  {
    FileW = -1;
    while ( 1 )
    {
      VirtualDiskPhysicalPath = GetVirtualDiskPhysicalPath(VirtualDiskHandle, &DiskPathSizeInBytes, v2);
      if ( VirtualDiskPhysicalPath == 122 )
      {
        v5 = (WCHAR *)_o_realloc(v2, DiskPathSizeInBytes);
        if ( !v5 )
        {
          VirtualDiskPhysicalPath = -2147024882;
          goto LABEL_31;
        }
        v2 = v5;
        VirtualDiskPhysicalPath = GetVirtualDiskPhysicalPath(VirtualDiskHandle, &DiskPathSizeInBytes, v5);
      }
      if ( VirtualDiskPhysicalPath != 55 )
        break;
      Sleep(0x3E8u);
    }
    if ( VirtualDiskPhysicalPath )
    {
      if ( (int)VirtualDiskPhysicalPath > 0 )
        VirtualDiskPhysicalPath = (unsigned __int16)VirtualDiskPhysicalPath | 0x80070000;
      if ( (unsigned int)VmlIsDebugTraceEnabled(16482) )
        VmlDebugTrace(
          16482,
          L"ERROR VmVssWriterHelper::OnlineDisk\n\tFailed to get device physical path: (HRESULT = 0x%08lX)\n",
          VirtualDiskPhysicalPath);
    }
    else
    {
      FileW = (__int64)CreateFileW(v2, 0xC0000000, 3u, 0, 3u, 0, 0);
      if ( FileW == -1 )
      {
        LastError = GetLastError();
        VirtualDiskPhysicalPath = LastError;
        if ( LastError > 0 )
          VirtualDiskPhysicalPath = (unsigned __int16)LastError | 0x80070000;
        if ( (unsigned int)VmlIsDebugTraceEnabled(16482) )
          VmlDebugTrace(
            16482,
            L"ERROR VmVssWriterHelper::OnlineDisk\n\tFailed to open device physical path '%s': (HRESULT = 0x%08lX)\n",
            v2,
            VirtualDiskPhysicalPath);
      }
      else if ( DeviceIoControl((HANDLE)FileW, 0x700F0u, 0, 0, &OutBuffer, 0x10u, &BytesReturned, 0) )
      {
        VirtualDiskPhysicalPath = 0;
        v8 = BYTE8(OutBuffer) & 3;
        BYTE4(InBuffer) = 1;
        v9 = (v8 | (unsigned __int64)v15) == 0;
        *(_QWORD *)&v15 = v8 | v15;
        LODWORD(InBuffer) = 40;
        if ( !v9 && !DeviceIoControl((HANDLE)FileW, 0x7C0F4u, &InBuffer, 0x28u, 0, 0, &BytesReturned, 0) )
        {
          v10 = GetLastError();
          VirtualDiskPhysicalPath = v10;
          if ( v10 > 0 )
            VirtualDiskPhysicalPath = (unsigned __int16)v10 | 0x80070000;
          if ( (unsigned int)VmlIsDebugTraceEnabled(16482) )
            VmlDebugTrace(
              16482,
              L"ERROR VmVssWriterHelper::OnlineDisk\n"
               "\tFailed to online device physical path '%s': (HRESULT = 0x%08lX)\n",
              v2,
              VirtualDiskPhysicalPath);
        }
      }
      else
      {
        v7 = GetLastError();
        VirtualDiskPhysicalPath = v7;
        if ( v7 > 0 )
          VirtualDiskPhysicalPath = (unsigned __int16)v7 | 0x80070000;
        if ( (unsigned int)VmlIsDebugTraceEnabled(16482) )
          VmlDebugTrace(
            16482,
            L"ERROR VmVssWriterHelper::OnlineDisk\n"
             "\tFailed to get attributes of device physical path ' %s': (HRESULT = 0x%08lX)\n",
            v2,
            VirtualDiskPhysicalPath);
      }
    }
LABEL_31:
    free(v2);
    if ( FileW != -1 )
      CloseHandle((HANDLE)FileW);
  }
  else
  {
    return (DWORD)-2147024882;
  }
  return VirtualDiskPhysicalPath;
}

```

## disassembly

```asm
0x1406a96ac  mov     [rsp-8+arg_8], rbx
0x1406a96b1  mov     [rsp-8+arg_10], rsi
0x1406a96b6  push    rbp
0x1406a96b7  push    rdi
0x1406a96b8  push    r14
0x1406a96ba  lea     rbp, [rsp-47h]
0x1406a96bf  sub     rsp, 90h
0x1406a96c6  mov     rax, cs:__security_cookie
0x1406a96cd  xor     rax, rsp
0x1406a96d0  mov     [rbp+57h+var_18], rax
0x1406a96d4  xor     eax, eax
0x1406a96d6  xorps   xmm0, xmm0
0x1406a96d9  mov     rdi, rcx
0x1406a96dc  mov     [rbp+57h+var_30], rax
0x1406a96e0  movups  [rbp+57h+InBuffer], xmm0
0x1406a96e4  mov     [rbp+57h+BytesReturned], eax
0x1406a96e7  lea     ecx, [rax+32h]; Size
0x1406a96ea  mov     [rbp+57h+DiskPathSizeInBytes], ecx
0x1406a96ed  movups  [rbp+57h+var_40], xmm0
0x1406a96f1  movups  [rbp+57h+OutBuffer], xmm0
0x1406a96f5  call    cs:__imp_malloc
0x1406a96fc  nop     dword ptr [rax+rax+00h]
0x1406a9701  mov     rsi, rax
0x1406a9704  test    rax, rax
0x1406a9707  jnz     short loc_1406A9713
0x1406a9709  mov     ebx, 8007000Eh
0x1406a970e  jmp     loc_1406A996B
0x1406a9713  or      r14, 0FFFFFFFFFFFFFFFFh
0x1406a9717  mov     r8, rsi; DiskPath
0x1406a971a  lea     rdx, [rbp+57h+DiskPathSizeInBytes]; DiskPathSizeInBytes
0x1406a971e  mov     rcx, rdi; VirtualDiskHandle
0x1406a9721  call    cs:__imp_GetVirtualDiskPhysicalPath
0x1406a9728  nop     dword ptr [rax+rax+00h]
0x1406a972d  mov     ebx, eax
0x1406a972f  cmp     eax, 7Ah ; 'z'
0x1406a9732  jnz     short loc_1406A9766
0x1406a9734  mov     edx, [rbp+57h+DiskPathSizeInBytes]
0x1406a9737  mov     rcx, rsi
0x1406a973a  call    cs:__imp__o_realloc
0x1406a9741  nop     dword ptr [rax+rax+00h]
0x1406a9746  test    rax, rax
0x1406a9749  jz      short loc_1406A977E
0x1406a974b  mov     r8, rax; DiskPath
0x1406a974e  lea     rdx, [rbp+57h+DiskPathSizeInBytes]; DiskPathSizeInBytes
0x1406a9752  mov     rcx, rdi; VirtualDiskHandle
0x1406a9755  mov     rsi, rax
0x1406a9758  call    cs:__imp_GetVirtualDiskPhysicalPath
0x1406a975f  nop     dword ptr [rax+rax+00h]
0x1406a9764  mov     ebx, eax
0x1406a9766  cmp     ebx, 37h ; '7'
0x1406a9769  jnz     short loc_1406A9788
0x1406a976b  mov     ecx, 3E8h; dwMilliseconds
0x1406a9770  call    cs:__imp_Sleep
0x1406a9777  nop     dword ptr [rax+rax+00h]
0x1406a977c  jmp     short loc_1406A9717
0x1406a977e  mov     ebx, 8007000Eh
0x1406a9783  jmp     loc_1406A9942
0x1406a9788  test    ebx, ebx
0x1406a978a  jnz     loc_1406A9916
0x1406a9790  mov     [rsp+0A0h+hTemplateFile], 0; hTemplateFile
0x1406a9799  lea     r8d, [rbx+3]; dwShareMode
0x1406a979d  mov     [rsp+0A0h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x1406a97a1  xor     r9d, r9d; lpSecurityAttributes
0x1406a97a4  mov     edx, 0C0000000h; dwDesiredAccess
0x1406a97a9  mov     [rsp+0A0h+dwCreationDisposition], 3; dwCreationDisposition
0x1406a97b1  mov     rcx, rsi; lpFileName
0x1406a97b4  call    cs:__imp_CreateFileW
0x1406a97bb  nop     dword ptr [rax+rax+00h]
0x1406a97c0  mov     r14, rax
0x1406a97c3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1406a97c7  jnz     short loc_1406A9811
0x1406a97c9  call    cs:__imp_GetLastError
0x1406a97d0  nop     dword ptr [rax+rax+00h]
0x1406a97d5  mov     ebx, eax
0x1406a97d7  test    eax, eax
0x1406a97d9  jle     short loc_1406A97E4
0x1406a97db  movzx   ebx, ax
0x1406a97de  or      ebx, 80070000h
0x1406a97e4  mov     edi, 4062h
0x1406a97e9  mov     ecx, edi
0x1406a97eb  call    VmlIsDebugTraceEnabled
0x1406a97f0  test    eax, eax
0x1406a97f2  jz      loc_1406A9942
0x1406a97f8  lea     rdx, aErrorVmvsswrit_86; "ERROR VmVssWriterHelper::OnlineDisk\n\t"...
0x1406a97ff  mov     r9d, ebx
0x1406a9802  mov     r8, rsi
0x1406a9805  mov     ecx, edi
0x1406a9807  call    VmlDebugTrace
0x1406a980c  jmp     loc_1406A9942
0x1406a9811  mov     [rsp+0A0h+lpOverlapped], 0; lpOverlapped
0x1406a981a  lea     rax, [rbp+57h+BytesReturned]
0x1406a981e  mov     [rsp+0A0h+hTemplateFile], rax; lpBytesReturned
0x1406a9823  xor     r9d, r9d; nInBufferSize
0x1406a9826  lea     rax, [rbp+57h+OutBuffer]
0x1406a982a  mov     [rsp+0A0h+dwFlagsAndAttributes], 10h; nOutBufferSize
0x1406a9832  xor     r8d, r8d; lpInBuffer
0x1406a9835  mov     qword ptr [rsp+0A0h+dwCreationDisposition], rax; lpOutBuffer
0x1406a983a  mov     edx, 700F0h; dwIoControlCode
0x1406a983f  mov     rcx, r14; hDevice
0x1406a9842  call    cs:__imp_DeviceIoControl
0x1406a9849  nop     dword ptr [rax+rax+00h]
0x1406a984e  test    eax, eax
0x1406a9850  jnz     short loc_1406A988D
0x1406a9852  call    cs:__imp_GetLastError
0x1406a9859  nop     dword ptr [rax+rax+00h]
0x1406a985e  mov     ebx, eax
0x1406a9860  test    eax, eax
0x1406a9862  jle     short loc_1406A986D
0x1406a9864  movzx   ebx, ax
0x1406a9867  or      ebx, 80070000h
0x1406a986d  mov     edi, 4062h
0x1406a9872  mov     ecx, edi
0x1406a9874  call    VmlIsDebugTraceEnabled
0x1406a9879  test    eax, eax
0x1406a987b  jz      loc_1406A9942
0x1406a9881  lea     rdx, aErrorVmvsswrit_35; "ERROR VmVssWriterHelper::OnlineDisk\n\t"...
0x1406a9888  jmp     loc_1406A97FF
0x1406a988d  mov     rax, qword ptr [rbp+57h+OutBuffer+8]
0x1406a9891  xor     ebx, ebx
0x1406a9893  and     eax, 3
0x1406a9896  mov     byte ptr [rbp+57h+InBuffer+4], 1
0x1406a989a  or      qword ptr [rbp+57h+var_40], rax
0x1406a989e  lea     r9d, [rbx+28h]; nInBufferSize
0x1406a98a2  mov     dword ptr [rbp+57h+InBuffer], r9d
0x1406a98a6  jz      loc_1406A9942
0x1406a98ac  mov     [rsp+0A0h+lpOverlapped], rbx; lpOverlapped
0x1406a98b1  lea     rax, [rbp+57h+BytesReturned]
0x1406a98b5  mov     [rsp+0A0h+hTemplateFile], rax; lpBytesReturned
0x1406a98ba  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x1406a98be  mov     [rsp+0A0h+dwFlagsAndAttributes], ebx; nOutBufferSize
0x1406a98c2  mov     edx, 7C0F4h; dwIoControlCode
0x1406a98c7  mov     rcx, r14; hDevice
0x1406a98ca  mov     qword ptr [rsp+0A0h+dwCreationDisposition], rbx; lpOutBuffer
0x1406a98cf  call    cs:__imp_DeviceIoControl
0x1406a98d6  nop     dword ptr [rax+rax+00h]
0x1406a98db  test    eax, eax
0x1406a98dd  jnz     short loc_1406A9942
0x1406a98df  call    cs:__imp_GetLastError
0x1406a98e6  nop     dword ptr [rax+rax+00h]
0x1406a98eb  mov     ebx, eax
0x1406a98ed  test    eax, eax
0x1406a98ef  jle     short loc_1406A98FA
0x1406a98f1  movzx   ebx, ax
0x1406a98f4  or      ebx, 80070000h
0x1406a98fa  mov     edi, 4062h
0x1406a98ff  mov     ecx, edi
0x1406a9901  call    VmlIsDebugTraceEnabled
0x1406a9906  test    eax, eax
0x1406a9908  jz      short loc_1406A9942
0x1406a990a  lea     rdx, aErrorVmvsswrit_24; "ERROR VmVssWriterHelper::OnlineDisk\n\t"...
0x1406a9911  jmp     loc_1406A97FF
0x1406a9916  jle     short loc_1406A9921
0x1406a9918  movzx   ebx, bx
0x1406a991b  or      ebx, 80070000h
0x1406a9921  mov     edi, 4062h
0x1406a9926  mov     ecx, edi
0x1406a9928  call    VmlIsDebugTraceEnabled
0x1406a992d  test    eax, eax
0x1406a992f  jz      short loc_1406A9942
0x1406a9931  mov     r8d, ebx
0x1406a9934  lea     rdx, aErrorVmvsswrit_134; "ERROR VmVssWriterHelper::OnlineDisk\n\t"...
0x1406a993b  mov     ecx, edi
0x1406a993d  call    VmlDebugTrace
0x1406a9942  test    rsi, rsi
0x1406a9945  jz      short loc_1406A9956
0x1406a9947  mov     rcx, rsi; Block
0x1406a994a  call    cs:__imp_free
0x1406a9951  nop     dword ptr [rax+rax+00h]
0x1406a9956  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1406a995a  jz      short loc_1406A996B
0x1406a995c  mov     rcx, r14; hObject
0x1406a995f  call    cs:__imp_CloseHandle
0x1406a9966  nop     dword ptr [rax+rax+00h]
0x1406a996b  mov     eax, ebx
0x1406a996d  mov     rcx, [rbp+57h+var_18]
0x1406a9971  xor     rcx, rsp; StackCookie
0x1406a9974  call    __security_check_cookie
0x1406a9979  lea     r11, [rsp+0A0h+var_10]
0x1406a9981  mov     rbx, [r11+28h]
0x1406a9985  mov     rsi, [r11+30h]
0x1406a9989  mov     rsp, r11
0x1406a998c  pop     r14
0x1406a998e  pop     rdi
0x1406a998f  pop     rbp
0x1406a9990  retn
```
