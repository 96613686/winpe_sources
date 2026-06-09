# UsbHelper_GetDeviceSpeed(ushort *,ushort,_USB_DEVICE_SPEED *)

- ea: `0x18000fb20`
- end: `0x18000fbf2`
- name: `?UsbHelper_GetDeviceSpeed@@YAKPEAGGPEAW4_USB_DEVICE_SPEED@@@Z`
- size: `210`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16, enum _USB_DEVICE_SPEED *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000f74c`

## callees

- `0x180002e4a`
- `0x180002e56`
- `0x18000fb20`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fbe1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fbe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb67`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000fb56`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000fb56`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000fbbe`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000fbbe`

## pseudocode

```c
__int64 __fastcall UsbHelper_GetDeviceSpeed(unsigned __int16 *a1, unsigned __int16 a2, enum _USB_DEVICE_SPEED *a3)
{
  int v4; // ebp
  HANDLE FileW; // rsi
  unsigned __int8 *v6; // rdi
  DWORD LastError; // ebx
  unsigned __int8 *lpOutBuffer; // rax
  DWORD BytesReturned; // [rsp+88h] [rbp+20h] BYREF

  v4 = a2;
  BytesReturned = 0;
  FileW = CreateFileW(a1, 0, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    v6 = 0;
LABEL_3:
    LastError = GetLastError();
    goto LABEL_8;
  }
  lpOutBuffer = (unsigned __int8 *)o_malloc_0(0x23u);
  v6 = lpOutBuffer;
  if ( lpOutBuffer )
  {
    *(_DWORD *)lpOutBuffer = v4;
    if ( !DeviceIoControl(FileW, 0x220448u, lpOutBuffer, 0x23u, lpOutBuffer, 0x23u, &BytesReturned, 0) )
      goto LABEL_3;
    *a3 = v6[23];
    LastError = 0;
  }
  else
  {
    LastError = 14;
  }
LABEL_8:
  free(v6);
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  return LastError;
}

```

## disassembly

```asm
0x18000fb20  mov     rax, rsp
0x18000fb23  push    rbx
0x18000fb24  push    rbp
0x18000fb25  push    rsi
0x18000fb26  push    rdi
0x18000fb27  sub     rsp, 48h
0x18000fb2b  mov     qword ptr [rax-38h], 0
0x18000fb33  mov     rbx, r8
0x18000fb36  mov     r8d, 3; dwShareMode
0x18000fb3c  movzx   ebp, dx
0x18000fb3f  mov     dword ptr [rax-40h], 0
0x18000fb46  xor     r9d, r9d; lpSecurityAttributes
0x18000fb49  xor     edx, edx; dwDesiredAccess
0x18000fb4b  mov     [rax-48h], r8d
0x18000fb4f  mov     dword ptr [rax+20h], 0
0x18000fb56  call    cs:__imp_CreateFileW
0x18000fb5c  mov     rsi, rax
0x18000fb5f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000fb63  jnz     short loc_18000FB71
0x18000fb65  xor     edi, edi
0x18000fb67  call    cs:__imp_GetLastError
0x18000fb6d  mov     ebx, eax
0x18000fb6f  jmp     short loc_18000FBD0
0x18000fb71  mov     ecx, 23h ; '#'; Size
0x18000fb76  call    _o_malloc_0
0x18000fb7b  mov     rdi, rax
0x18000fb7e  test    rax, rax
0x18000fb81  jnz     short loc_18000FB88
0x18000fb83  lea     ebx, [rax+0Eh]
0x18000fb86  jmp     short loc_18000FBD0
0x18000fb88  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x18000fb91  mov     r9d, 23h ; '#'; nInBufferSize
0x18000fb97  mov     [rax], ebp
0x18000fb99  mov     r8, rdi; lpInBuffer
0x18000fb9c  lea     rax, [rsp+68h+BytesReturned]
0x18000fba4  mov     edx, 220448h; dwIoControlCode
0x18000fba9  mov     [rsp+68h+lpBytesReturned], rax; lpBytesReturned
0x18000fbae  mov     rcx, rsi; hDevice
0x18000fbb1  mov     [rsp+68h+nOutBufferSize], 23h ; '#'; nOutBufferSize
0x18000fbb9  mov     [rsp+68h+lpOutBuffer], rdi; lpOutBuffer
0x18000fbbe  call    cs:__imp_DeviceIoControl
0x18000fbc4  test    eax, eax
0x18000fbc6  jz      short loc_18000FB67
0x18000fbc8  movzx   eax, byte ptr [rdi+17h]
0x18000fbcc  mov     [rbx], eax
0x18000fbce  xor     ebx, ebx
0x18000fbd0  mov     rcx, rdi; Block
0x18000fbd3  call    free
0x18000fbd8  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000fbdc  jz      short loc_18000FBE7
0x18000fbde  mov     rcx, rsi; hObject
0x18000fbe1  call    cs:__imp_CloseHandle
0x18000fbe7  mov     eax, ebx
0x18000fbe9  add     rsp, 48h
0x18000fbed  pop     rdi
0x18000fbee  pop     rsi
0x18000fbef  pop     rbp
0x18000fbf0  pop     rbx
0x18000fbf1  retn
```
