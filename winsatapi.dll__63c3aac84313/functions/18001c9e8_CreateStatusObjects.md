# CreateStatusObjects

- ea: `0x18001c9e8`
- end: `0x18001ca7f`
- name: `CreateStatusObjects`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, installer_update`

## callers

- `0x180012af0`

## callees

- `0x18001c9e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ca50`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ca6b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ca50`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ca6b`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001ca0d`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001ca0d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001ca35`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001ca35`

## string_xrefs

- `0x18001ca3b`: `WinSAT.Status.Update`
- `0x18001ca56`: `WinSAT.Status.Read`

## pseudocode

```c
__int64 CreateStatusObjects()
{
  HANDLE FileMappingW; // rax

  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x80Cu, L"WinSAT.SharedMemory");
  qword_18004DEA0 = FileMappingW;
  if ( FileMappingW )
  {
    Src = MapViewOfFile(FileMappingW, 4u, 0, 0, 0x80Cu);
    qword_18004DEE0 = CreateEventW(0, 0, 0, L"WinSAT.Status.Update");
    hEvent = CreateEventW(0, 0, 0, L"WinSAT.Status.Read");
  }
  return 0;
}

```

## disassembly

```asm
0x18001c9e8  sub     rsp, 38h
0x18001c9ec  xor     r9d, r9d; dwMaximumSizeHigh
0x18001c9ef  lea     rax, Name; "WinSAT.SharedMemory"
0x18001c9f6  mov     [rsp+38h+lpName], rax; lpName
0x18001c9fb  xor     edx, edx; lpFileMappingAttributes
0x18001c9fd  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18001ca01  mov     [rsp+38h+dwMaximumSizeLow], 80Ch; dwMaximumSizeLow
0x18001ca09  lea     r8d, [r9+4]; flProtect
0x18001ca0d  call    cs:__imp_CreateFileMappingW
0x18001ca13  mov     cs:qword_18004DEA0, rax
0x18001ca1a  test    rax, rax
0x18001ca1d  jz      short loc_18001CA78
0x18001ca1f  xor     r9d, r9d; dwFileOffsetLow
0x18001ca22  mov     qword ptr [rsp+38h+dwMaximumSizeLow], 80Ch; dwNumberOfBytesToMap
0x18001ca2b  xor     r8d, r8d; dwFileOffsetHigh
0x18001ca2e  mov     rcx, rax; hFileMappingObject
0x18001ca31  lea     edx, [r9+4]; dwDesiredAccess
0x18001ca35  call    cs:__imp_MapViewOfFile
0x18001ca3b  lea     r9, aWinsatStatusUp; "WinSAT.Status.Update"
0x18001ca42  xor     r8d, r8d; bInitialState
0x18001ca45  xor     edx, edx; bManualReset
0x18001ca47  mov     cs:Src, rax
0x18001ca4e  xor     ecx, ecx; lpEventAttributes
0x18001ca50  call    cs:__imp_CreateEventW
0x18001ca56  lea     r9, aWinsatStatusRe; "WinSAT.Status.Read"
0x18001ca5d  xor     r8d, r8d; bInitialState
0x18001ca60  xor     edx, edx; bManualReset
0x18001ca62  mov     cs:qword_18004DEE0, rax
0x18001ca69  xor     ecx, ecx; lpEventAttributes
0x18001ca6b  call    cs:__imp_CreateEventW
0x18001ca71  mov     cs:hEvent, rax
0x18001ca78  xor     eax, eax
0x18001ca7a  add     rsp, 38h
0x18001ca7e  retn
```
