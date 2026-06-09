# EcbFileExtentsGetRetrievalPointers

- ea: `0x180021e98`
- end: `0x18002202b`
- name: `EcbFileExtentsGetRetrievalPointers`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001ff8c`

## callees

- `0x180020ee8`
- `0x180021e98`
- `0x1800b645a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021fb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ff3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021fb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ff3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021f9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021f9d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180021ede`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180021ede`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021f94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022012`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021f94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022012`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021f19`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021f19`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180021f6d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180021f6d`

## string_xrefs

- `0x180021fbf`: `ERROR: couldn't open file %ws: %x\n`

## pseudocode

```c
__int64 __fastcall EcbFileExtentsGetRetrievalPointers(const WCHAR *a1, _QWORD *a2)
{
  HANDLE FileW; // r14
  unsigned int v5; // ebp
  DWORD nOutBufferSize; // esi
  _DWORD *v7; // rax
  _DWORD *lpOutBuffer; // rdi
  __int64 LastError; // rbx
  DWORD BytesReturned; // [rsp+80h] [rbp+18h] BYREF
  __int64 InBuffer; // [rsp+88h] [rbp+20h] BYREF

  InBuffer = 0;
  BytesReturned = 0;
  FileW = CreateFileW(a1, 0, 7u, 0, 3u, 0x2000000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    EcbUtilsOut(2, "ERROR: couldn't open file %ws: %x\n", a1, LastError);
  }
  else
  {
    v5 = 0;
    InBuffer = 0;
    for ( nOutBufferSize = 32; ; nOutBufferSize *= 2 )
    {
      if ( v5 > 0xA )
      {
        LODWORD(LastError) = 13;
        goto LABEL_9;
      }
      v7 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, nOutBufferSize);
      lpOutBuffer = v7;
      if ( !v7 )
      {
        LODWORD(LastError) = 8;
        goto LABEL_9;
      }
      memset_0(v7, 0, nOutBufferSize);
      if ( DeviceIoControl(FileW, 0x90073u, &InBuffer, 8u, lpOutBuffer, nOutBufferSize, &BytesReturned, 0) )
        break;
      LODWORD(LastError) = GetLastError();
      if ( (_DWORD)LastError != 234 )
        goto LABEL_8;
      HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, lpOutBuffer);
      ++v5;
    }
    if ( *lpOutBuffer >= 0xFFFFFFFu || 16 * (unsigned __int64)(unsigned int)*lpOutBuffer > nOutBufferSize - 16 )
    {
      LODWORD(LastError) = 13;
LABEL_8:
      HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, lpOutBuffer);
      goto LABEL_9;
    }
    *a2 = lpOutBuffer;
    LODWORD(LastError) = 0;
LABEL_9:
    CloseHandle(FileW);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180021e98  mov     rax, rsp
0x180021e9b  mov     [rax+8], rbx
0x180021e9f  push    rbp
0x180021ea0  push    rsi
0x180021ea1  push    rdi
0x180021ea2  push    r14
0x180021ea4  push    r15
0x180021ea6  sub     rsp, 40h
0x180021eaa  mov     qword ptr [rax-38h], 0
0x180021eb2  xor     r9d, r9d; lpSecurityAttributes
0x180021eb5  mov     r15, rdx
0x180021eb8  mov     dword ptr [rax-40h], 2000000h
0x180021ebf  xor     edx, edx; dwDesiredAccess
0x180021ec1  mov     qword ptr [rax+20h], 0
0x180021ec9  mov     rdi, rcx
0x180021ecc  mov     dword ptr [rax+18h], 0
0x180021ed3  lea     r8d, [r9+7]; dwShareMode
0x180021ed7  mov     dword ptr [rax-48h], 3
0x180021ede  call    cs:__imp_CreateFileW
0x180021ee4  mov     r14, rax
0x180021ee7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180021eeb  jz      loc_180021FB6
0x180021ef1  xor     ebp, ebp
0x180021ef3  mov     [rsp+68h+InBuffer], rbp
0x180021efb  lea     esi, [rbp+20h]
0x180021efe  cmp     ebp, 0Ah
0x180021f01  ja      loc_180022021
0x180021f07  mov     rcx, cs:PfSvcGlobals
0x180021f0e  xor     edx, edx; dwFlags
0x180021f10  mov     r8d, esi; dwBytes
0x180021f13  mov     ebx, esi
0x180021f15  mov     rcx, [rcx+58h]; hHeap
0x180021f19  call    cs:__imp_HeapAlloc
0x180021f1f  mov     rdi, rax
0x180021f22  test    rax, rax
0x180021f25  jz      loc_180021FEC
0x180021f2b  mov     r8d, ebx; Size
0x180021f2e  xor     edx, edx; Val
0x180021f30  mov     rcx, rax; void *
0x180021f33  call    memset_0
0x180021f38  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x180021f41  lea     rax, [rsp+68h+BytesReturned]
0x180021f49  mov     [rsp+68h+lpBytesReturned], rax; lpBytesReturned
0x180021f4e  lea     r8, [rsp+68h+InBuffer]; lpInBuffer
0x180021f56  mov     [rsp+68h+nOutBufferSize], esi; nOutBufferSize
0x180021f5a  mov     r9d, 8; nInBufferSize
0x180021f60  mov     edx, 90073h; dwIoControlCode
0x180021f65  mov     [rsp+68h+lpOutBuffer], rdi; lpOutBuffer
0x180021f6a  mov     rcx, r14; hDevice
0x180021f6d  call    cs:__imp_DeviceIoControl
0x180021f73  test    eax, eax
0x180021f75  jz      short loc_180021FF3
0x180021f77  cmp     dword ptr [rdi], 0FFFFFFFh
0x180021f7d  jb      short loc_180021FD7
0x180021f7f  mov     ebx, 0Dh
0x180021f84  mov     rcx, cs:PfSvcGlobals
0x180021f8b  mov     r8, rdi; lpMem
0x180021f8e  xor     edx, edx; dwFlags
0x180021f90  mov     rcx, [rcx+58h]; hHeap
0x180021f94  call    cs:__imp_HeapFree
0x180021f9a  mov     rcx, r14; hObject
0x180021f9d  call    cs:__imp_CloseHandle
0x180021fa3  mov     eax, ebx
0x180021fa5  mov     rbx, [rsp+68h+arg_0]
0x180021faa  add     rsp, 40h
0x180021fae  pop     r15
0x180021fb0  pop     r14
0x180021fb2  pop     rdi
0x180021fb3  pop     rsi
0x180021fb4  pop     rbp
0x180021fb5  retn
0x180021fb6  call    cs:__imp_GetLastError
0x180021fbc  mov     r8, rdi
0x180021fbf  lea     rdx, aErrorCouldnTOp; "ERROR: couldn't open file %ws: %x\n"
0x180021fc6  mov     r9d, eax
0x180021fc9  mov     ecx, 2
0x180021fce  mov     ebx, eax
0x180021fd0  call    EcbUtilsOut
0x180021fd5  jmp     short loc_180021FA3
0x180021fd7  mov     edx, [rdi]
0x180021fd9  lea     ecx, [rsi-10h]
0x180021fdc  shl     rdx, 4
0x180021fe0  cmp     rdx, rcx
0x180021fe3  ja      short loc_180021F7F
0x180021fe5  mov     [r15], rdi
0x180021fe8  xor     ebx, ebx
0x180021fea  jmp     short loc_180021F9A
0x180021fec  mov     ebx, 8
0x180021ff1  jmp     short loc_180021F9A
0x180021ff3  call    cs:__imp_GetLastError
0x180021ff9  mov     ebx, eax
0x180021ffb  cmp     eax, 0EAh
0x180022000  jnz     short loc_180021F84
0x180022002  mov     rcx, cs:PfSvcGlobals
0x180022009  mov     r8, rdi; lpMem
0x18002200c  xor     edx, edx; dwFlags
0x18002200e  mov     rcx, [rcx+58h]; hHeap
0x180022012  call    cs:__imp_HeapFree
0x180022018  add     esi, esi
0x18002201a  inc     ebp
0x18002201c  jmp     loc_180021EFE
0x180022021  mov     ebx, 0Dh
0x180022026  jmp     loc_180021F9A
```
