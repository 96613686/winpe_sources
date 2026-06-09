# SyncDeviceControl

- ea: `0x180005230`
- end: `0x180005276`
- name: `SyncDeviceControl`
- size: `70`
- prototype: `DWORD __fastcall(void *, DWORD, void *, DWORD, LPVOID lpOutBuffer, DWORD nOutBufferSize, LPDWORD lpBytesReturned)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180004ef4`
- `0x180009c7c`
- `0x18000a270`
- `0x18000a35c`
- `0x18000a620`
- `0x18000cec8`

## callees

- `0x180005230`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000526e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000526e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000525c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000525c`

## pseudocode

```c
DWORD __fastcall SyncDeviceControl(
        void *a1,
        DWORD a2,
        void *a3,
        DWORD a4,
        LPVOID lpOutBuffer,
        DWORD nOutBufferSize,
        LPDWORD lpBytesReturned)
{
  if ( DeviceIoControl(a1, a2, a3, a4, lpOutBuffer, nOutBufferSize, lpBytesReturned, 0) )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180005230  push    rbx
0x180005232  sub     rsp, 40h
0x180005236  mov     rax, [rsp+48h+arg_30]
0x18000523e  xor     ebx, ebx
0x180005240  mov     [rsp+48h+lpOverlapped], rbx; lpOverlapped
0x180005245  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x18000524a  mov     eax, [rsp+48h+arg_28]
0x18000524e  mov     [rsp+48h+nOutBufferSize], eax; nOutBufferSize
0x180005252  mov     rax, [rsp+48h+arg_20]
0x180005257  mov     [rsp+48h+lpOutBuffer], rax; lpOutBuffer
0x18000525c  call    cs:__imp_DeviceIoControl
0x180005262  test    eax, eax
0x180005264  jz      short loc_18000526E
0x180005266  mov     eax, ebx
0x180005268  add     rsp, 40h
0x18000526c  pop     rbx
0x18000526d  retn
0x18000526e  call    cs:__imp_GetLastError
0x180005274  jmp     short loc_180005268
```
