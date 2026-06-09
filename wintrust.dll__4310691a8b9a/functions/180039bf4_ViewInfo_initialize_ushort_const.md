# ViewInfo::initialize(ushort const *)

- ea: `0x180039bf4`
- end: `0x180039cd5`
- name: `?initialize@ViewInfo@@QEAA_NPEBG@Z`
- size: `225`
- prototype: `bool(ViewInfo *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800398f0`

## callees

- `0x180039bf4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180039c77`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180039c77`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180039c52`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180039c52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039cab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039cab`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180039c1d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180039c1d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x180039c9e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x180039c9e`

## pseudocode

```c
bool __fastcall ViewInfo::initialize(ViewInfo *this, const unsigned __int16 *a2)
{
  HANDLE FileW; // rax
  void *v5; // rsi
  DWORD FileSize; // ebx
  bool result; // al
  struct _SYSTEM_INFO v8; // [rsp+40h] [rbp-38h] BYREF
  DWORD FileSizeHigh; // [rsp+80h] [rbp+8h] BYREF

  memset(&v8, 0, sizeof(v8));
  GetSystemInfo(&v8);
  *((_DWORD *)this + 11) = v8.dwAllocationGranularity;
  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x8000080u, 0);
  v5 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return 0;
  FileSizeHigh = 0;
  FileSize = GetFileSize(FileW, &FileSizeHigh);
  *((_QWORD *)this + 1) = CreateFileMappingA(v5, 0, 0x8000002u, 0, 0, 0);
  CloseHandle(v5);
  if ( !*((_QWORD *)this + 1) )
    return 0;
  *(_DWORD *)this = FileSize;
  result = 1;
  *((_DWORD *)this + 5) = FileSize;
  return result;
}

```

## disassembly

```asm
0x180039bf4  mov     rax, rsp
0x180039bf7  mov     [rax+10h], rbx
0x180039bfb  mov     [rax+18h], rsi
0x180039bff  push    rdi
0x180039c00  sub     rsp, 70h
0x180039c04  xorps   xmm0, xmm0
0x180039c07  mov     rdi, rcx
0x180039c0a  lea     rcx, [rax-38h]; lpSystemInfo
0x180039c0e  mov     rbx, rdx
0x180039c11  movups  xmmword ptr [rax-38h], xmm0
0x180039c15  movups  xmmword ptr [rax-28h], xmm0
0x180039c19  movups  xmmword ptr [rax-18h], xmm0
0x180039c1d  call    cs:__imp_GetSystemInfo
0x180039c23  mov     eax, [rsp+78h+var_10]
0x180039c27  xor     r9d, r9d; lpSecurityAttributes
0x180039c2a  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180039c33  mov     edx, 80000000h; dwDesiredAccess
0x180039c38  mov     [rsp+78h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x180039c40  mov     rcx, rbx; lpFileName
0x180039c43  mov     [rdi+2Ch], eax
0x180039c46  lea     r8d, [r9+1]; dwShareMode
0x180039c4a  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180039c52  call    cs:__imp_CreateFileW
0x180039c58  mov     rsi, rax
0x180039c5b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180039c5f  jz      short loc_180039CC1
0x180039c61  lea     rdx, [rsp+78h+FileSizeHigh]; lpFileSizeHigh
0x180039c69  mov     [rsp+78h+FileSizeHigh], 0
0x180039c74  mov     rcx, rax; hFile
0x180039c77  call    cs:__imp_GetFileSize
0x180039c7d  xor     r9d, r9d; dwMaximumSizeHigh
0x180039c80  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], 0; lpName
0x180039c89  xor     edx, edx; lpFileMappingAttributes
0x180039c8b  mov     [rsp+78h+dwCreationDisposition], 0; dwMaximumSizeLow
0x180039c93  mov     r8d, 8000002h; flProtect
0x180039c99  mov     rcx, rsi; hFile
0x180039c9c  mov     ebx, eax
0x180039c9e  call    cs:__imp_CreateFileMappingA
0x180039ca4  mov     rcx, rsi; hObject
0x180039ca7  mov     [rdi+8], rax
0x180039cab  call    cs:__imp_CloseHandle
0x180039cb1  cmp     qword ptr [rdi+8], 0
0x180039cb6  jz      short loc_180039CC1
0x180039cb8  mov     [rdi], ebx
0x180039cba  mov     al, 1
0x180039cbc  mov     [rdi+14h], ebx
0x180039cbf  jmp     short loc_180039CC3
0x180039cc1  xor     al, al
0x180039cc3  lea     r11, [rsp+78h+var_8]
0x180039cc8  mov     rbx, [r11+18h]
0x180039ccc  mov     rsi, [r11+20h]
0x180039cd0  mov     rsp, r11
0x180039cd3  pop     rdi
0x180039cd4  retn
```
