# create_output_file

- ea: `0x1800b2fc0`
- end: `0x1800b30aa`
- name: `create_output_file`
- size: `234`
- prototype: `__int64 __fastcall(LPCSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800ac708`

## callees

- `0x1800b2fc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800b3080`
- `KERNEL32!GetLastError` at `0x1800b3080`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800b2fd3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800b2fd3`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800b3063`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800b3063`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x1800b3011`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x1800b3011`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x1800b2ff8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x1800b2ff8`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x1800b3024`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x1800b3024`

## pseudocode

```c
__int64 __fastcall create_output_file(LPCSTR lpFileName)
{
  _DWORD *Value; // rax
  _DWORD *v3; // rdi
  DWORD FileAttributesA; // eax
  HANDLE FileA; // rax
  DWORD LastError; // eax
  unsigned int v8; // ecx

  Value = TlsGetValue(dwUnZIPTlsIndex);
  v3 = Value;
  if ( !Value )
    return 4;
  if ( Value[1] )
  {
    FileAttributesA = GetFileAttributesA(lpFileName);
    if ( FileAttributesA != -1
      && (!SetFileAttributesA(lpFileName, FileAttributesA & 0xFFFFFFFE) || !DeleteFileA(lpFileName)) )
    {
      return 28;
    }
  }
  FileA = CreateFileA(lpFileName, 0xC0000000, 3u, 0, 2u, 0x8000020u, 0);
  *(_QWORD *)((char *)v3 + 72178) = FileA;
  if ( FileA != (HANDLE)-1LL )
    return 0;
  LastError = GetLastError();
  v8 = 28;
  if ( LastError == 206 )
    return 51;
  return v8;
}

```

## disassembly

```asm
0x1800b2fc0  mov     [rsp+arg_0], rbx
0x1800b2fc5  push    rdi
0x1800b2fc6  sub     rsp, 40h
0x1800b2fca  mov     rbx, rcx
0x1800b2fcd  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x1800b2fd3  call    cs:__imp_TlsGetValue
0x1800b2fda  nop     dword ptr [rax+rax+00h]
0x1800b2fdf  mov     rdi, rax
0x1800b2fe2  test    rax, rax
0x1800b2fe5  jnz     short loc_1800B2FEF
0x1800b2fe7  lea     eax, [rdi+4]
0x1800b2fea  jmp     loc_1800B309E
0x1800b2fef  cmp     dword ptr [rax+4], 0
0x1800b2ff3  jz      short loc_1800B303B
0x1800b2ff5  mov     rcx, rbx; lpFileName
0x1800b2ff8  call    cs:__imp_GetFileAttributesA
0x1800b2fff  nop     dword ptr [rax+rax+00h]
0x1800b3004  cmp     eax, 0FFFFFFFFh
0x1800b3007  jz      short loc_1800B303B
0x1800b3009  and     eax, 0FFFFFFFEh
0x1800b300c  mov     rcx, rbx; lpFileName
0x1800b300f  mov     edx, eax; dwFileAttributes
0x1800b3011  call    cs:__imp_SetFileAttributesA
0x1800b3018  nop     dword ptr [rax+rax+00h]
0x1800b301d  test    eax, eax
0x1800b301f  jz      short loc_1800B3034
0x1800b3021  mov     rcx, rbx; lpFileName
0x1800b3024  call    cs:__imp_DeleteFileA
0x1800b302b  nop     dword ptr [rax+rax+00h]
0x1800b3030  test    eax, eax
0x1800b3032  jnz     short loc_1800B303B
0x1800b3034  mov     eax, 1Ch
0x1800b3039  jmp     short loc_1800B309E
0x1800b303b  xor     r9d, r9d; lpSecurityAttributes
0x1800b303e  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800b3047  mov     [rsp+48h+dwFlagsAndAttributes], 8000020h; dwFlagsAndAttributes
0x1800b304f  mov     edx, 0C0000000h; dwDesiredAccess
0x1800b3054  mov     rcx, rbx; lpFileName
0x1800b3057  mov     [rsp+48h+dwCreationDisposition], 2; dwCreationDisposition
0x1800b305f  lea     r8d, [r9+3]; dwShareMode
0x1800b3063  call    cs:__imp_CreateFileA
0x1800b306a  nop     dword ptr [rax+rax+00h]
0x1800b306f  mov     [rdi+119F2h], rax
0x1800b3076  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b307a  jz      short loc_1800B3080
0x1800b307c  xor     eax, eax
0x1800b307e  jmp     short loc_1800B309E
0x1800b3080  call    cs:__imp_GetLastError
0x1800b3087  nop     dword ptr [rax+rax+00h]
0x1800b308c  mov     ecx, 1Ch
0x1800b3091  cmp     eax, 0CEh
0x1800b3096  lea     edx, [rcx+17h]
0x1800b3099  cmovz   ecx, edx
0x1800b309c  mov     eax, ecx
0x1800b309e  mov     rbx, [rsp+48h+arg_0]
0x1800b30a3  add     rsp, 40h
0x1800b30a7  pop     rdi
0x1800b30a8  retn
```
