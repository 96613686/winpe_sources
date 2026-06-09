# PfsBcCreateFile

- ea: `0x18001c020`
- end: `0x18001c228`
- name: `PfsBcCreateFile`
- size: `520`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, int, __int64, int)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001ad28`
- `0x18001b7b8`
- `0x18001b9cc`
- `0x180020370`
- `0x18009fe7c`
- `0x1800a0660`
- `0x1800a5524`
- `0x1800a7f00`

## callees

- `0x18001c020`

## import_xrefs

- `ntdll!RtlGetCompressionWorkSpaceSize` at `0x18001c05d`
- `ntdll!RtlGetCompressionWorkSpaceSize` at `0x18001c05d`
- `ntdll!RtlComputeCrc32` at `0x18001c169`
- `ntdll!RtlComputeCrc32` at `0x18001c169`
- `ntdll!RtlNtStatusToDosError` at `0x18001c069`
- `ntdll!RtlNtStatusToDosError` at `0x18001c069`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c194`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c194`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c1c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c1c3`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18001c1d6`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18001c1e9`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18001c1d6`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18001c1e9`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001c09f`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001c0c7`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001c09f`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001c0c7`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18001c18a`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18001c18a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001c12e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001c12e`

## pseudocode

```c
__int64 __fastcall PfsBcCreateFile(__int64 a1, const WCHAR *a2, int a3, __int64 a4, int a5)
{
  int CompressionWorkSpaceSize; // eax
  DWORD LastError; // edi
  ULONG v10; // eax
  void *v11; // rbx
  _DWORD *v12; // rbp
  HANDLE FileW; // rax
  void *v14; // r14
  _DWORD *v15; // r13
  int v16; // ebx
  ULONG v17; // eax
  char v18; // al
  int v19; // eax
  SIZE_T dwSize; // [rsp+40h] [rbp-68h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+48h] [rbp-60h] BYREF
  LPVOID v23; // [rsp+50h] [rbp-58h]
  ULONG v24; // [rsp+C8h] [rbp+20h] BYREF

  v24 = 0;
  LODWORD(dwSize) = 0;
  FileSize.QuadPart = 0;
  CompressionWorkSpaceSize = RtlGetCompressionWorkSpaceSize(4u, &v24, (PULONG)&dwSize);
  if ( CompressionWorkSpaceSize < 0 )
    return RtlNtStatusToDosError(CompressionWorkSpaceSize);
  if ( a3 )
  {
    v10 = v24;
  }
  else
  {
    v10 = dwSize;
    v24 = dwSize;
  }
  v23 = VirtualAlloc(0, v10, 0x1000u, 4u);
  v11 = v23;
  if ( !v23 )
    return 8;
  v12 = VirtualAlloc(0, 0xA0008u, 0x1000u, 4u);
  if ( !v12
    || (a3
      ? (FileW = CreateFileW(a2, 0xC0000000, 7u, 0, 2u, 0x8000000u, 0))
      : (*(_DWORD *)(a1 + 32) = 0x10000,
         *(_DWORD *)(a1 + 48) = 589832,
         FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x8000000u, 0)),
        v14 = FileW,
        FileW == (HANDLE)-1LL) )
  {
    LastError = GetLastError();
  }
  else
  {
    v15 = v12 + 0x4000;
    if ( a3 )
    {
      v16 = a5;
      *v15 = -482187696;
      v12[16385] = v16;
      v17 = RtlComputeCrc32(0, (PUCHAR)v12 + 0x10000, 8u);
      *(_DWORD *)(a1 + 56) = v16;
      *(_DWORD *)(a1 + 52) = v16;
      v11 = v23;
      *(_DWORD *)(a1 + 64) = v17;
      *(_DWORD *)(a1 + 48) = 8;
LABEL_26:
      v18 = a3 ^ *(_DWORD *)a1;
      *(_QWORD *)(a1 + 8) = v14;
      *(_QWORD *)(a1 + 24) = v12;
      v19 = *(_DWORD *)a1 ^ v18 & 1 | 2;
      *(_QWORD *)(a1 + 40) = v15;
      *(_DWORD *)a1 = v19;
      LastError = 0;
      *(_QWORD *)(a1 + 16) = v11;
      return LastError;
    }
    if ( GetFileSizeEx(FileW, &FileSize) )
    {
      if ( FileSize.HighPart )
      {
        LastError = 223;
      }
      else
      {
        if ( FileSize.LowPart >= 8uLL )
        {
          *(_DWORD *)(a1 + 60) = FileSize.LowPart;
          goto LABEL_26;
        }
        LastError = 11;
      }
    }
    else
    {
      LastError = GetLastError();
    }
    CloseHandle(v14);
  }
  VirtualFree(v11, 0, 0x8000u);
  if ( v12 )
    VirtualFree(v12, 0, 0x8000u);
  return LastError;
}

```

## disassembly

```asm
0x18001c020  mov     rax, rsp
0x18001c023  mov     [rax+20h], r9d
0x18001c027  push    rbx
0x18001c028  push    rbp
0x18001c029  push    rsi
0x18001c02a  push    rdi
0x18001c02b  push    r12
0x18001c02d  push    r13
0x18001c02f  push    r14
0x18001c031  push    r15
0x18001c033  sub     rsp, 68h
0x18001c037  xor     r13d, r13d
0x18001c03a  mov     r15d, r8d
0x18001c03d  mov     rdi, rdx
0x18001c040  mov     [rax+20h], r13d
0x18001c044  mov     rsi, rcx
0x18001c047  mov     [rax-68h], r13d
0x18001c04b  lea     r8, [rax-68h]; CompressFragmentWorkSpaceSize
0x18001c04f  mov     [rax-60h], r13
0x18001c053  lea     ebp, [r13+4]
0x18001c057  mov     ecx, ebp; CompressionFormatAndEngine
0x18001c059  lea     rdx, [rax+20h]; CompressBufferWorkSpaceSize
0x18001c05d  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x18001c063  test    eax, eax
0x18001c065  jns     short loc_18001C076
0x18001c067  mov     ecx, eax; Status
0x18001c069  call    cs:__imp_RtlNtStatusToDosError
0x18001c06f  mov     edi, eax
0x18001c071  jmp     loc_18001C215
0x18001c076  test    r15d, r15d
0x18001c079  jnz     short loc_18001C088
0x18001c07b  mov     eax, dword ptr [rsp+0A8h+dwSize]
0x18001c07f  mov     [rsp+0A8h+arg_18], eax
0x18001c086  jmp     short loc_18001C08F
0x18001c088  mov     eax, [rsp+0A8h+arg_18]
0x18001c08f  mov     r14d, 1000h
0x18001c095  mov     edx, eax; dwSize
0x18001c097  mov     r8d, r14d; flAllocationType
0x18001c09a  mov     r9d, ebp; flProtect
0x18001c09d  xor     ecx, ecx; lpAddress
0x18001c09f  call    cs:__imp_VirtualAlloc
0x18001c0a5  mov     [rsp+0A8h+var_58], rax
0x18001c0aa  mov     rbx, rax
0x18001c0ad  test    rax, rax
0x18001c0b0  jnz     short loc_18001C0BA
0x18001c0b2  lea     edi, [rax+8]
0x18001c0b5  jmp     loc_18001C215
0x18001c0ba  mov     r9d, ebp; flProtect
0x18001c0bd  mov     r8d, r14d; flAllocationType
0x18001c0c0  mov     edx, 0A0008h; dwSize
0x18001c0c5  xor     ecx, ecx; lpAddress
0x18001c0c7  call    cs:__imp_VirtualAlloc
0x18001c0cd  mov     rbp, rax
0x18001c0d0  test    rax, rax
0x18001c0d3  jnz     short loc_18001C0E2
0x18001c0d5  call    cs:__imp_GetLastError
0x18001c0db  mov     edi, eax
0x18001c0dd  jmp     loc_18001C1C9
0x18001c0e2  xor     r9d, r9d; lpSecurityAttributes
0x18001c0e5  mov     [rsp+0A8h+hTemplateFile], r13; hTemplateFile
0x18001c0ea  mov     [rsp+0A8h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x18001c0f2  mov     rcx, rdi; lpFileName
0x18001c0f5  test    r15d, r15d
0x18001c0f8  jnz     short loc_18001C11B
0x18001c0fa  mov     dword ptr [rsi+20h], 10000h
0x18001c101  lea     r8d, [r9+1]
0x18001c105  mov     dword ptr [rsi+30h], 90008h
0x18001c10c  mov     edx, 80000000h
0x18001c111  mov     [rsp+0A8h+dwCreationDisposition], 3
0x18001c119  jmp     short loc_18001C12E
0x18001c11b  mov     [rsp+0A8h+dwCreationDisposition], 2; dwCreationDisposition
0x18001c123  mov     edx, 0C0000000h; dwDesiredAccess
0x18001c128  mov     r8d, 7; dwShareMode
0x18001c12e  call    cs:__imp_CreateFileW
0x18001c134  mov     r14, rax
0x18001c137  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001c13b  jz      short loc_18001C0D5
0x18001c13d  lea     r13, [rbp+10000h]
0x18001c144  test    r15d, r15d
0x18001c147  jz      short loc_18001C182
0x18001c149  mov     ebx, [rsp+0A8h+arg_20]
0x18001c150  mov     edi, 8
0x18001c155  mov     r8d, edi; Length
0x18001c158  mov     dword ptr [r13+0], 0E3426650h
0x18001c160  mov     rdx, r13; Buffer
0x18001c163  mov     [r13+4], ebx
0x18001c167  xor     ecx, ecx; InitialCrc
0x18001c169  call    cs:__imp_RtlComputeCrc32
0x18001c16f  mov     [rsi+38h], ebx
0x18001c172  mov     [rsi+34h], ebx
0x18001c175  mov     rbx, [rsp+0A8h+var_58]
0x18001c17a  mov     [rsi+40h], eax
0x18001c17d  mov     [rsi+30h], edi
0x18001c180  jmp     short loc_18001C1F4
0x18001c182  lea     rdx, [rsp+0A8h+FileSize]; lpFileSize
0x18001c187  mov     rcx, r14; hFile
0x18001c18a  call    cs:__imp_GetFileSizeEx
0x18001c190  test    eax, eax
0x18001c192  jnz     short loc_18001C19E
0x18001c194  call    cs:__imp_GetLastError
0x18001c19a  mov     edi, eax
0x18001c19c  jmp     short loc_18001C1C0
0x18001c19e  cmp     dword ptr [rsp+0A8h+FileSize+4], 0
0x18001c1a3  jz      short loc_18001C1AC
0x18001c1a5  mov     edi, 0DFh
0x18001c1aa  jmp     short loc_18001C1C0
0x18001c1ac  mov     rax, qword ptr [rsp+0A8h+FileSize]
0x18001c1b1  mov     edi, 8
0x18001c1b6  cmp     rax, rdi
0x18001c1b9  jnb     short loc_18001C1F1
0x18001c1bb  mov     edi, 0Bh
0x18001c1c0  mov     rcx, r14; hObject
0x18001c1c3  call    cs:__imp_CloseHandle
0x18001c1c9  mov     esi, 8000h
0x18001c1ce  xor     edx, edx; dwSize
0x18001c1d0  mov     r8d, esi; dwFreeType
0x18001c1d3  mov     rcx, rbx; lpAddress
0x18001c1d6  call    cs:__imp_VirtualFree
0x18001c1dc  test    rbp, rbp
0x18001c1df  jz      short loc_18001C215
0x18001c1e1  mov     r8d, esi; dwFreeType
0x18001c1e4  xor     edx, edx; dwSize
0x18001c1e6  mov     rcx, rbp; lpAddress
0x18001c1e9  call    cs:__imp_VirtualFree
0x18001c1ef  jmp     short loc_18001C215
0x18001c1f1  mov     [rsi+3Ch], eax
0x18001c1f4  mov     eax, [rsi]
0x18001c1f6  xor     eax, r15d
0x18001c1f9  mov     [rsi+8], r14
0x18001c1fd  and     eax, 1
0x18001c200  mov     [rsi+18h], rbp
0x18001c204  xor     eax, [rsi]
0x18001c206  or      eax, 2
0x18001c209  mov     [rsi+28h], r13
0x18001c20d  mov     [rsi], eax
0x18001c20f  xor     edi, edi
0x18001c211  mov     [rsi+10h], rbx
0x18001c215  mov     eax, edi
0x18001c217  add     rsp, 68h
0x18001c21b  pop     r15
0x18001c21d  pop     r14
0x18001c21f  pop     r13
0x18001c221  pop     r12
0x18001c223  pop     rdi
0x18001c224  pop     rsi
0x18001c225  pop     rbp
0x18001c226  pop     rbx
0x18001c227  retn
```
