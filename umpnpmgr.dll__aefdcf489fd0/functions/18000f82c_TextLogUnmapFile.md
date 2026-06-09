# TextLogUnmapFile

- ea: `0x18000f82c`
- end: `0x18000f8cc`
- name: `TextLogUnmapFile`
- size: `160`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800027a0`
- `0x1800056d0`
- `0x18000b160`
- `0x18000b360`
- `0x18001725c`
- `0x1800177e0`

## callees

- `0x18000f82c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f87a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f898`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f87a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f898`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000f889`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000f889`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18000f84d`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18000f84d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000f868`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000f868`

## pseudocode

```c
BOOL __fastcall TextLogUnmapFile(__int64 a1)
{
  const void *v2; // rcx
  BOOL result; // eax
  void *v4; // rsi
  HANDLE v5; // rdi

  if ( *(_DWORD *)(a1 + 44) && *(_QWORD *)a1 != -1 )
    FlushFileBuffers(*(HANDLE *)a1);
  v2 = *(const void **)(a1 + 16);
  result = 1;
  v4 = *(void **)(a1 + 8);
  v5 = *(HANDLE *)a1;
  if ( v2 )
    result = UnmapViewOfFile(v2);
  if ( v4 && result )
    result = CloseHandle(v4);
  if ( v5 != (HANDLE)-1LL )
    result = SetEndOfFile(v5);
  if ( *(_QWORD *)a1 != -1 )
    result = CloseHandle(*(HANDLE *)a1);
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)a1 = -1;
  *(_DWORD *)(a1 + 44) = 0;
  return result;
}

```

## disassembly

```asm
0x18000f82c  mov     [rsp+arg_0], rbx
0x18000f831  mov     [rsp+arg_8], rsi
0x18000f836  push    rdi
0x18000f837  sub     rsp, 20h
0x18000f83b  cmp     dword ptr [rcx+2Ch], 0
0x18000f83f  mov     rbx, rcx
0x18000f842  jz      short loc_18000F853
0x18000f844  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x18000f848  jz      short loc_18000F853
0x18000f84a  mov     rcx, [rcx]; hFile
0x18000f84d  call    cs:__imp_FlushFileBuffers
0x18000f853  mov     rcx, [rbx+10h]; lpBaseAddress
0x18000f857  mov     eax, 1
0x18000f85c  mov     rsi, [rbx+8]
0x18000f860  mov     rdi, [rbx]
0x18000f863  test    rcx, rcx
0x18000f866  jz      short loc_18000F86E
0x18000f868  call    cs:__imp_UnmapViewOfFile
0x18000f86e  test    rsi, rsi
0x18000f871  jz      short loc_18000F880
0x18000f873  test    eax, eax
0x18000f875  jz      short loc_18000F880
0x18000f877  mov     rcx, rsi; hObject
0x18000f87a  call    cs:__imp_CloseHandle
0x18000f880  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000f884  jz      short loc_18000F88F
0x18000f886  mov     rcx, rdi; hFile
0x18000f889  call    cs:__imp_SetEndOfFile
0x18000f88f  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18000f893  jz      short loc_18000F89E
0x18000f895  mov     rcx, [rbx]; hObject
0x18000f898  call    cs:__imp_CloseHandle
0x18000f89e  mov     rsi, [rsp+28h+arg_8]
0x18000f8a3  mov     qword ptr [rbx+10h], 0
0x18000f8ab  mov     qword ptr [rbx+8], 0
0x18000f8b3  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18000f8ba  mov     dword ptr [rbx+2Ch], 0
0x18000f8c1  mov     rbx, [rsp+28h+arg_0]
0x18000f8c6  add     rsp, 20h
0x18000f8ca  pop     rdi
0x18000f8cb  retn
```
