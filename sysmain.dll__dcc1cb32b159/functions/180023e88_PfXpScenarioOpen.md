# PfXpScenarioOpen

- ea: `0x180023e88`
- end: `0x18002410a`
- name: `PfXpScenarioOpen`
- size: `642`
- prototype: `__int64 __fastcall(const WCHAR *, int, _QWORD *)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018d1c`
- `0x180033740`
- `0x180039e1c`
- `0x18003aa6c`
- `0x18003af4c`

## callees

- `0x1800211f4`
- `0x1800236e8`
- `0x180023e88`
- `0x180024110`
- `0x180025f6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800240b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800240d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800240b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800240d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023f6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023f82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023faf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024064`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023f6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023f82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023faf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024064`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180023fa6`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002405b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180023fa6`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002405b`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180023ff1`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180023ff1`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800240ff`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800240ff`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180023f53`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180023f53`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180024071`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180024071`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180023f1e`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180023f1e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023f04`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023f04`

## string_xrefs

- `0x180023ec8`: `// Reading file: %ws...\n`

## pseudocode

```c
__int64 __fastcall PfXpScenarioOpen(const WCHAR *a1, int a2, _QWORD *a3)
{
  void *v4; // r15
  _DWORD *v5; // rdi
  const WCHAR *v6; // rax
  HANDLE FileW; // rax
  void *v8; // r14
  DWORD FileSize; // ebx
  HANDLE FileMappingW; // rax
  DWORD LastError; // ebx
  UCHAR *v12; // rsi
  DWORD v14; // eax
  DWORD FileSizeHigh; // [rsp+44h] [rbp-2Ch] BYREF
  _DWORD *v16; // [rsp+48h] [rbp-28h]
  LPCVOID lpBaseAddress[2]; // [rsp+50h] [rbp-20h]
  __int64 v20; // [rsp+C8h] [rbp+58h] BYREF

  LODWORD(v20) = 0;
  v16 = 0;
  FileSizeHigh = 0;
  v4 = 0;
  *(_OWORD *)lpBaseAddress = 0;
  v5 = 0;
  v6 = (const WCHAR *)PFSV_PRINTF("// Reading file: %ws...\n", a1);
  FileW = CreateFileW(v6, dwDesiredAccess, dwShareMode, 0, 3u, 0, 0);
  v8 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v12 = (UCHAR *)lpBaseAddress[1];
    LastError = GetLastError();
    v8 = (void *)lpBaseAddress[0];
    goto LABEL_9;
  }
  FileSize = GetFileSize(FileW, &FileSizeHigh);
  if ( FileSize == -1 && GetLastError() )
  {
LABEL_5:
    LastError = GetLastError();
    goto LABEL_6;
  }
  if ( !FileSizeHigh )
  {
    LODWORD(v20) = FileSize;
    FileMappingW = CreateFileMappingW(v8, 0, flProtect, 0, 0, 0);
    v4 = FileMappingW;
    if ( FileMappingW )
    {
      v12 = (UCHAR *)MapViewOfFile(FileMappingW, dword_1800D25EC, 0, 0, 0);
      if ( v12 )
      {
        LastError = 0;
        goto LABEL_7;
      }
    }
    goto LABEL_5;
  }
  LastError = 24;
LABEL_6:
  CloseHandle(v8);
  v12 = (UCHAR *)lpBaseAddress[1];
  v8 = (void *)lpBaseAddress[0];
  if ( v4 )
LABEL_7:
    CloseHandle(v4);
  LODWORD(v4) = v20;
LABEL_9:
  if ( !LastError )
  {
    LODWORD(v20) = 0x10000000;
    v14 = PfsDecompressBuffer(v12, (__int64)&v20);
    v5 = v16;
    LastError = v14;
    if ( !v14 )
    {
      LODWORD(v20) = 0;
      if ( (unsigned __int8)PfXpVerifyScenarioBuffer(v16, 0, &v20) && v5[2] == 17 )
      {
        if ( a2 == 2 || v5[20] == a2 )
        {
          *a3 = v5;
          v5 = 0;
          LastError = 0;
        }
        else
        {
          LastError = 1629;
        }
      }
      else
      {
        UnmapViewOfFile(v12);
        CloseHandle(v8);
        DeleteFileW(a1);
        LastError = 11;
        v8 = 0;
        v12 = (UCHAR *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      }
    }
  }
  PfXpLogDecompressScenario((unsigned int)v4, 0, LastError);
  if ( v12 )
  {
    UnmapViewOfFile(v12);
    CloseHandle(v8);
  }
  if ( v5 )
    VirtualFree(v5, 0, 0x8000u);
  return LastError;
}

```

## disassembly

```asm
0x180023e88  mov     rax, rsp
0x180023e8b  mov     [rax+10h], rbx
0x180023e8f  mov     [rax+18h], r8
0x180023e93  mov     [rax+8], rcx
0x180023e97  push    rbp
0x180023e98  push    rsi
0x180023e99  push    rdi
0x180023e9a  push    r12
0x180023e9c  push    r13
0x180023e9e  push    r14
0x180023ea0  push    r15
0x180023ea2  mov     rbp, rsp
0x180023ea5  sub     rsp, 70h
0x180023ea9  xor     esi, esi
0x180023eab  movaps  xmmword ptr [rax-48h], xmm6
0x180023eaf  mov     r13d, edx
0x180023eb2  mov     dword ptr [rbp+arg_18], esi
0x180023eb5  mov     rdx, rcx
0x180023eb8  mov     [rbp+var_28], rsi
0x180023ebc  mov     rax, rcx
0x180023ebf  mov     [rbp+var_30], esi
0x180023ec2  xorps   xmm0, xmm0
0x180023ec5  mov     [rbp+FileSizeHigh], esi
0x180023ec8  lea     rcx, aReadingFileWs; "// Reading file: %ws...\n"
0x180023ecf  mov     r15d, esi
0x180023ed2  movups  xmmword ptr [rbp+lpBaseAddress], xmm0
0x180023ed6  mov     edi, esi
0x180023ed8  mov     r12d, esi
0x180023edb  call    PFSV_PRINTF
0x180023ee0  mov     r8d, cs:dwShareMode; dwShareMode
0x180023ee7  xor     r9d, r9d; lpSecurityAttributes
0x180023eea  mov     edx, cs:dwDesiredAccess; dwDesiredAccess
0x180023ef0  mov     rcx, rax; lpFileName
0x180023ef3  mov     [rsp+70h+hTemplateFile], rsi; hTemplateFile
0x180023ef8  mov     [rsp+70h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x180023efc  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x180023f04  call    cs:__imp_CreateFileW
0x180023f0a  mov     r14, rax
0x180023f0d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023f11  jz      loc_1800240D5
0x180023f17  lea     rdx, [rbp+FileSizeHigh]; lpFileSizeHigh
0x180023f1b  mov     rcx, rax; hFile
0x180023f1e  call    cs:__imp_GetFileSize
0x180023f24  mov     ebx, eax
0x180023f26  cmp     eax, 0FFFFFFFFh
0x180023f29  jz      loc_1800240B8
0x180023f2f  cmp     [rbp+FileSizeHigh], esi
0x180023f32  jnz     loc_1800240CB
0x180023f38  mov     r8d, cs:flProtect; flProtect
0x180023f3f  xor     r9d, r9d; dwMaximumSizeHigh
0x180023f42  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rsi; lpName
0x180023f47  xor     edx, edx; lpFileMappingAttributes
0x180023f49  mov     rcx, r14; hFile
0x180023f4c  mov     [rsp+70h+dwCreationDisposition], esi; dwMaximumSizeLow
0x180023f50  mov     dword ptr [rbp+arg_18], ebx
0x180023f53  call    cs:__imp_CreateFileMappingW
0x180023f59  mov     r15, rax
0x180023f5c  test    rax, rax
0x180023f5f  jnz     short loc_180023FDD
0x180023f61  call    cs:__imp_GetLastError
0x180023f67  mov     ebx, eax
0x180023f69  mov     rcx, r14; hObject
0x180023f6c  call    cs:__imp_CloseHandle
0x180023f72  mov     rsi, [rbp+lpBaseAddress+8]
0x180023f76  mov     r14, [rbp+lpBaseAddress]
0x180023f7a  test    r15, r15
0x180023f7d  jz      short loc_180023F88
0x180023f7f  mov     rcx, r15; hObject
0x180023f82  call    cs:__imp_CloseHandle
0x180023f88  mov     r15d, dword ptr [rbp+arg_18]
0x180023f8c  test    ebx, ebx
0x180023f8e  jz      short loc_18002400A
0x180023f90  mov     r8d, ebx
0x180023f93  mov     edx, r12d
0x180023f96  mov     ecx, r15d
0x180023f99  call    PfXpLogDecompressScenario
0x180023f9e  test    rsi, rsi
0x180023fa1  jz      short loc_180023FB5
0x180023fa3  mov     rcx, rsi; lpBaseAddress
0x180023fa6  call    cs:__imp_UnmapViewOfFile
0x180023fac  mov     rcx, r14; hObject
0x180023faf  call    cs:__imp_CloseHandle
0x180023fb5  test    rdi, rdi
0x180023fb8  jnz     loc_1800240F4
0x180023fbe  movaps  xmm6, [rsp+70h+var_10]
0x180023fc3  mov     eax, ebx
0x180023fc5  mov     rbx, [rsp+70h+arg_8]
0x180023fcd  add     rsp, 70h
0x180023fd1  pop     r15
0x180023fd3  pop     r14
0x180023fd5  pop     r13
0x180023fd7  pop     r12
0x180023fd9  pop     rdi
0x180023fda  pop     rsi
0x180023fdb  pop     rbp
0x180023fdc  retn
0x180023fdd  mov     edx, cs:dword_1800D25EC; dwDesiredAccess
0x180023fe3  xor     r9d, r9d; dwFileOffsetLow
0x180023fe6  xor     r8d, r8d; dwFileOffsetHigh
0x180023fe9  mov     qword ptr [rsp+70h+dwCreationDisposition], rsi; dwNumberOfBytesToMap
0x180023fee  mov     rcx, rax; hFileMappingObject
0x180023ff1  call    cs:__imp_MapViewOfFile
0x180023ff7  mov     rsi, rax
0x180023ffa  test    rax, rax
0x180023ffd  jz      loc_180023F61
0x180024003  xor     ebx, ebx
0x180024005  jmp     loc_180023F7F
0x18002400a  lea     rax, [rbp+arg_18]
0x18002400e  mov     dword ptr [rbp+arg_18], 10000000h
0x180024015  lea     r9, [rbp+var_30]
0x180024019  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; __int64
0x18002401e  lea     r8, [rbp+var_28]
0x180024022  mov     edx, r15d
0x180024025  mov     rcx, rsi; Buffer
0x180024028  call    PfsDecompressBuffer
0x18002402d  mov     rdi, [rbp+var_28]
0x180024031  mov     ebx, eax
0x180024033  test    eax, eax
0x180024035  jnz     short loc_180024093
0x180024037  mov     dword ptr [rbp+arg_18], r12d
0x18002403b  lea     r8, [rbp+arg_18]
0x18002403f  mov     r12d, [rbp+var_30]
0x180024043  mov     rcx, rdi
0x180024046  mov     edx, r12d
0x180024049  call    PfXpVerifyScenarioBuffer
0x18002404e  test    al, al
0x180024050  jz      short loc_180024058
0x180024052  cmp     dword ptr [rdi+8], 11h
0x180024056  jz      short loc_18002409C
0x180024058  mov     rcx, rsi; lpBaseAddress
0x18002405b  call    cs:__imp_UnmapViewOfFile
0x180024061  mov     rcx, r14; hObject
0x180024064  call    cs:__imp_CloseHandle
0x18002406a  mov     rcx, [rbp+lpFileName]; lpFileName
0x18002406e  xorps   xmm6, xmm6
0x180024071  call    cs:__imp_DeleteFileW
0x180024077  xorps   xmm0, xmm0
0x18002407a  mov     ebx, 0Bh
0x18002407f  psrldq  xmm0, 8
0x180024084  movq    r14, xmm6
0x180024089  movq    rsi, xmm0
0x18002408e  jmp     loc_180023F90
0x180024093  mov     r12d, [rbp+var_30]
0x180024097  jmp     loc_180023F90
0x18002409c  cmp     r13d, 2
0x1800240a0  jz      short loc_1800240A8
0x1800240a2  cmp     [rdi+50h], r13d
0x1800240a6  jnz     short loc_1800240EA
0x1800240a8  mov     rax, [rbp+arg_10]
0x1800240ac  mov     [rax], rdi
0x1800240af  xor     edi, edi
0x1800240b1  xor     ebx, ebx
0x1800240b3  jmp     loc_180023F90
0x1800240b8  call    cs:__imp_GetLastError
0x1800240be  test    eax, eax
0x1800240c0  jnz     loc_180023F61
0x1800240c6  jmp     loc_180023F2F
0x1800240cb  mov     ebx, 18h
0x1800240d0  jmp     loc_180023F69
0x1800240d5  call    cs:__imp_GetLastError
0x1800240db  mov     rsi, [rbp+lpBaseAddress+8]
0x1800240df  mov     ebx, eax
0x1800240e1  mov     r14, [rbp+lpBaseAddress]
0x1800240e5  jmp     loc_180023F8C
0x1800240ea  mov     ebx, 65Dh
0x1800240ef  jmp     loc_180023F90
0x1800240f4  xor     edx, edx; dwSize
0x1800240f6  mov     r8d, 8000h; dwFreeType
0x1800240fc  mov     rcx, rdi; lpAddress
0x1800240ff  call    cs:__imp_VirtualFree
0x180024105  jmp     loc_180023FBE
```
