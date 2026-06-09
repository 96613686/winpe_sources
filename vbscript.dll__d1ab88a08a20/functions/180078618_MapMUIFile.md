# MapMUIFile

- ea: `0x180078618`
- end: `0x180078721`
- name: `MapMUIFile`
- size: `265`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180078774`
- `0x1800788a0`

## callees

- `0x180078618`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x1800786ca`
- `KERNEL32!MapViewOfFile` at `0x1800786ca`
- `KERNEL32!CreateFileMappingW` at `0x180078691`
- `KERNEL32!CreateFileMappingW` at `0x180078691`
- `KERNEL32!CreateFileW` at `0x18007865b`
- `KERNEL32!CreateFileW` at `0x18007865b`
- `KERNEL32!LoadLibraryExW` at `0x180078705`
- `KERNEL32!LoadLibraryExW` at `0x180078705`
- `KERNEL32!CloseHandle` at `0x1800786a3`
- `KERNEL32!CloseHandle` at `0x1800786dc`
- `KERNEL32!CloseHandle` at `0x1800786a3`
- `KERNEL32!CloseHandle` at `0x1800786dc`

## pseudocode

```c
HMODULE __fastcall MapMUIFile(const WCHAR *a1, int a2, int a3)
{
  HANDLE FileW; // rax
  void *v4; // rbx
  HANDLE FileMappingW; // rdi
  unsigned __int64 v6; // rbx

  if ( a1 )
  {
    if ( !a2 )
      return LoadLibraryExW(a1, 0, a3 != 0);
    FileW = CreateFileW(a1, 0x80000000, 5u, 0, 3u, 0, 0);
    v4 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      FileMappingW = CreateFileMappingW(FileW, 0, 8u, 0, 0, 0);
      CloseHandle(v4);
      if ( FileMappingW )
      {
        v6 = (unsigned __int64)MapViewOfFile(FileMappingW, 1u, 0, 0, 0);
        CloseHandle(FileMappingW);
        return (HMODULE)((v6 | 1) & -(__int64)(v6 != 0));
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180078618  mov     [rsp+arg_0], rbx
0x18007861d  push    rdi
0x18007861e  sub     rsp, 40h
0x180078622  mov     eax, r8d
0x180078625  test    rcx, rcx
0x180078628  jz      loc_180078713
0x18007862e  test    edx, edx
0x180078630  jz      loc_1800786FA
0x180078636  xor     r9d, r9d; lpSecurityAttributes
0x180078639  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180078642  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18007864a  mov     edx, 80000000h; dwDesiredAccess
0x18007864f  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180078657  lea     r8d, [r9+5]; dwShareMode
0x18007865b  call    cs:__imp_CreateFileW
0x180078662  nop     dword ptr [rax+rax+00h]
0x180078667  mov     rbx, rax
0x18007866a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007866e  jz      loc_180078713
0x180078674  xor     r9d, r9d; dwMaximumSizeHigh
0x180078677  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x180078680  xor     edx, edx; lpFileMappingAttributes
0x180078682  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18007868a  mov     rcx, rax; hFile
0x18007868d  lea     r8d, [r9+8]; flProtect
0x180078691  call    cs:__imp_CreateFileMappingW
0x180078698  nop     dword ptr [rax+rax+00h]
0x18007869d  mov     rcx, rbx; hObject
0x1800786a0  mov     rdi, rax
0x1800786a3  call    cs:__imp_CloseHandle
0x1800786aa  nop     dword ptr [rax+rax+00h]
0x1800786af  test    rdi, rdi
0x1800786b2  jz      short loc_180078713
0x1800786b4  xor     r9d, r9d; dwFileOffsetLow
0x1800786b7  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x1800786c0  xor     r8d, r8d; dwFileOffsetHigh
0x1800786c3  mov     rcx, rdi; hFileMappingObject
0x1800786c6  lea     edx, [r9+1]; dwDesiredAccess
0x1800786ca  call    cs:__imp_MapViewOfFile
0x1800786d1  nop     dword ptr [rax+rax+00h]
0x1800786d6  mov     rcx, rdi; hObject
0x1800786d9  mov     rbx, rax
0x1800786dc  call    cs:__imp_CloseHandle
0x1800786e3  nop     dword ptr [rax+rax+00h]
0x1800786e8  mov     rcx, rbx
0x1800786eb  or      rcx, 1; lpLibFileName
0x1800786ef  neg     rbx
0x1800786f2  sbb     rax, rax
0x1800786f5  and     rax, rcx
0x1800786f8  jmp     short loc_180078715
0x1800786fa  xor     r8d, r8d
0x1800786fd  test    eax, eax
0x1800786ff  setnz   r8b; dwFlags
0x180078703  xor     edx, edx; hFile
0x180078705  call    cs:__imp_LoadLibraryExW
0x18007870c  nop     dword ptr [rax+rax+00h]
0x180078711  jmp     short loc_180078715
0x180078713  xor     eax, eax
0x180078715  mov     rbx, [rsp+48h+arg_0]
0x18007871a  add     rsp, 40h
0x18007871e  pop     rdi
0x18007871f  retn
```
