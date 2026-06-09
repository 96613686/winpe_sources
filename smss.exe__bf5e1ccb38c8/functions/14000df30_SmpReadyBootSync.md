# SmpReadyBootSync

- ea: `0x14000df30`
- end: `0x14000dfba`
- name: `SmpReadyBootSync`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140005f64`

## callees

- `0x14000df30`
- `0x14000dfc0`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x14000df9f`
- `ntdll!NtDeviceIoControlFile` at `0x14000df9f`
- `ntdll!NtClose` at `0x14000dfac`
- `ntdll!NtClose` at `0x14000dfac`

## pseudocode

```c
__int64 SmpReadyBootSync()
{
  NTSTATUS ControlDeviceHandle; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF
  int InputBuffer; // [rsp+70h] [rbp+8h] BYREF
  HANDLE FileHandle; // [rsp+78h] [rbp+10h] BYREF

  FileHandle = 0;
  InputBuffer = 16;
  IoStatusBlock = 0;
  ControlDeviceHandle = SmpGetControlDeviceHandle(&FileHandle);
  if ( ControlDeviceHandle >= 0 )
  {
    ControlDeviceHandle = NtDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x2281DCu, &InputBuffer, 4u, 0, 0);
    NtClose(FileHandle);
  }
  return (unsigned int)ControlDeviceHandle;
}

```

## disassembly

```asm
0x14000df30  mov     rax, rsp
0x14000df33  push    rbx
0x14000df34  sub     rsp, 60h
0x14000df38  xorps   xmm0, xmm0
0x14000df3b  mov     qword ptr [rax+10h], 0
0x14000df43  lea     rcx, [rax+10h]
0x14000df47  mov     dword ptr [rax+8], 10h
0x14000df4e  movups  xmmword ptr [rax-18h], xmm0
0x14000df52  call    SmpGetControlDeviceHandle
0x14000df57  mov     ebx, eax
0x14000df59  test    eax, eax
0x14000df5b  js      short loc_14000DFB2
0x14000df5d  mov     rcx, [rsp+68h+FileHandle]; FileHandle
0x14000df62  lea     rax, [rsp+68h+arg_0]
0x14000df67  mov     [rsp+68h+OutputBufferLength], 0; OutputBufferLength
0x14000df6f  xor     r9d, r9d; ApcContext
0x14000df72  mov     [rsp+68h+OutputBuffer], 0; OutputBuffer
0x14000df7b  xor     r8d, r8d; ApcRoutine
0x14000df7e  mov     [rsp+68h+InputBufferLength], 4; InputBufferLength
0x14000df86  xor     edx, edx; Event
0x14000df88  mov     [rsp+68h+InputBuffer], rax; InputBuffer
0x14000df8d  lea     rax, [rsp+68h+var_18]
0x14000df92  mov     [rsp+68h+IoControlCode], 2281DCh; IoControlCode
0x14000df9a  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x14000df9f  call    cs:__imp_NtDeviceIoControlFile
0x14000dfa5  mov     rcx, [rsp+68h+FileHandle]; Handle
0x14000dfaa  mov     ebx, eax
0x14000dfac  call    cs:__imp_NtClose
0x14000dfb2  mov     eax, ebx
0x14000dfb4  add     rsp, 60h
0x14000dfb8  pop     rbx
0x14000dfb9  retn
```
