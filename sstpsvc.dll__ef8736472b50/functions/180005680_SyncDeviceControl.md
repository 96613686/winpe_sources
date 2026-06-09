# SyncDeviceControl

- ea: `0x180005680`
- end: `0x1800056d3`
- name: `SyncDeviceControl`
- size: `83`
- prototype: `__int64 __fastcall(int, int, int, int, LPVOID, DWORD, LPDWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000530c`
- `0x18000a59c`
- `0x18000abe0`
- `0x18000accc`
- `0x18000afb0`
- `0x18000da7c`

## callees

- `0x180005680`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056c5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800056ac`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800056ac`

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
0x180005680  push    rbx
0x180005682  sub     rsp, 40h
0x180005686  mov     rax, [rsp+48h+arg_30]
0x18000568e  xor     ebx, ebx
0x180005690  mov     [rsp+48h+lpOverlapped], rbx; lpOverlapped
0x180005695  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x18000569a  mov     eax, [rsp+48h+arg_28]
0x18000569e  mov     [rsp+48h+nOutBufferSize], eax; nOutBufferSize
0x1800056a2  mov     rax, [rsp+48h+arg_20]
0x1800056a7  mov     [rsp+48h+lpOutBuffer], rax; lpOutBuffer
0x1800056ac  call    cs:__imp_DeviceIoControl
0x1800056b3  nop     dword ptr [rax+rax+00h]
0x1800056b8  test    eax, eax
0x1800056ba  jz      short loc_1800056C5
0x1800056bc  mov     eax, ebx
0x1800056be  add     rsp, 40h
0x1800056c2  pop     rbx
0x1800056c3  retn
0x1800056c5  call    cs:__imp_GetLastError
0x1800056cc  nop     dword ptr [rax+rax+00h]
0x1800056d1  jmp     short loc_1800056BE
```
