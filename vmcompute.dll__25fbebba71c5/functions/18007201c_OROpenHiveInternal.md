# OROpenHiveInternal

- ea: `0x18007201c`
- end: `0x18007223e`
- name: `OROpenHiveInternal`
- size: `546`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800650c8`
- `0x18007b1e4`

## callees

- `0x180003b26`
- `0x180003b32`
- `0x180071f88`
- `0x18007201c`
- `0x180073da0`
- `0x1800750a8`
- `0x180076278`
- `0x1800762b8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007218e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007218e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800721bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800721bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800720d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072146`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007219f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800720d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072146`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007219f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180072136`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180072136`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800720c0`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800720c0`

## string_xrefs

- `0x180072187`: `ntdll.dll`
- `0x1800721b3`: `RtlValidRelativeSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall OROpenHiveInternal(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  char v5; // r14
  HANDLE v7; // rsi
  char v8; // r15
  HANDLE v9; // rdi
  DWORD LastError; // ebx
  unsigned int v11; // r14d
  DWORD v12; // eax
  DWORD LowPart; // ebx
  void *v14; // rax
  HMODULE ModuleHandleW; // rax
  HANDLE hFile[2]; // [rsp+30h] [rbp-10h] BYREF
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp+40h] BYREF
  int v19; // [rsp+84h] [rbp+44h]
  union _LARGE_INTEGER FileSize; // [rsp+98h] [rbp+58h] BYREF

  v19 = HIDWORD(a1);
  hFile[0] = 0;
  v5 = a3;
  NumberOfBytesRead = 0;
  FileSize.QuadPart = 0;
  v7 = 0;
  *(_QWORD *)a4 = 0;
  v8 = 0;
  v9 = 0;
  if ( !a2 || (a3 & 0xFFFFFFFE) != 0 )
  {
    LastError = 87;
    goto LABEL_24;
  }
  LastError = ORStart();
  if ( !LastError )
  {
    v11 = v5 & 1;
    v12 = ORCreateFile(a2, 2 * (v11 ^ 1) + 1, 3, v11, hFile);
    v7 = hFile[0];
    LastError = v12;
    if ( !v12 )
    {
      v8 = 1;
      if ( GetFileSizeEx(hFile[0], &FileSize) || (LastError = GetLastError()) == 0 )
      {
        LowPart = FileSize.LowPart;
        if ( FileSize.LowPart <= 0x1000 || FileSize.HighPart )
        {
          LastError = 1009;
          goto LABEL_24;
        }
        v14 = o__aligned_malloc_0(FileSize.LowPart, 0x10u);
        hFile[0] = v14;
        v9 = v14;
        if ( !v14 )
        {
          LastError = 8;
          goto LABEL_24;
        }
        if ( ReadFile(v7, v14, LowPart, &NumberOfBytesRead, 0) || (LastError = GetLastError()) == 0 )
        {
          LastError = ValidateHiveAndRecoverFromLog(hFile, &FileSize, a2, v7);
          if ( !LastError )
          {
            if ( v11 )
            {
              ORCloseFile(v7);
              v7 = 0;
              v8 = 0;
            }
            ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
            if ( ModuleHandleW )
            {
              ORValidRelativeSecurityDescriptor = (__int64)GetProcAddress(
                                                             ModuleHandleW,
                                                             "RtlValidRelativeSecurityDescriptor");
              if ( ORValidRelativeSecurityDescriptor )
              {
                v9 = 0;
                LastError = OROpenHiveFromMemoryInternal(hFile[0]);
                if ( !LastError )
                {
                  v8 = 0;
                  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a4 + 16LL) + 128LL) = v7;
                }
                goto LABEL_24;
              }
            }
            LastError = GetLastError();
          }
          v9 = hFile[0];
        }
      }
    }
  }
LABEL_24:
  if ( v9 )
    aligned_free(v9);
  if ( v8 )
    ORCloseFile(v7);
  return LastError;
}

```

## disassembly

```asm
0x18007201c  mov     [rsp-38h+arg_8], rbx
0x180072021  mov     qword ptr [rsp-38h+NumberOfBytesRead], rcx
0x180072026  push    rbp
0x180072027  push    rsi
0x180072028  push    rdi
0x180072029  push    r12
0x18007202b  push    r13
0x18007202d  push    r14
0x18007202f  push    r15
0x180072031  mov     rbp, rsp
0x180072034  sub     rsp, 40h
0x180072038  xor     ebx, ebx
0x18007203a  mov     r13, r9
0x18007203d  mov     [rbp+hFile], rbx
0x180072041  mov     r14d, r8d
0x180072044  mov     [rbp+NumberOfBytesRead], ebx
0x180072047  mov     r12, rdx
0x18007204a  mov     qword ptr [rbp+FileSize], rbx
0x18007204e  mov     esi, ebx
0x180072050  mov     [r9], rbx
0x180072053  mov     r15b, bl
0x180072056  mov     edi, ebx
0x180072058  test    rdx, rdx
0x18007205b  jnz     short loc_180072067
0x18007205d  mov     ebx, 57h ; 'W'
0x180072062  jmp     loc_180072209
0x180072067  test    r14d, 0FFFFFFFEh
0x18007206e  jnz     short loc_18007205D
0x180072070  call    ORStart
0x180072075  mov     ebx, eax
0x180072077  test    eax, eax
0x180072079  jnz     loc_180072209
0x18007207f  and     r14d, 1
0x180072083  lea     rax, [rbp+hFile]
0x180072087  mov     edx, r14d
0x18007208a  mov     [rsp+40h+lpOverlapped], rax
0x18007208f  xor     edx, 1
0x180072092  lea     r8d, [rbx+3]
0x180072096  mov     r9d, r14d
0x180072099  mov     rcx, r12
0x18007209c  lea     edx, ds:1[rdx*2]
0x1800720a3  call    ORCreateFile
0x1800720a8  mov     rsi, [rbp+hFile]
0x1800720ac  mov     ebx, eax
0x1800720ae  test    eax, eax
0x1800720b0  jnz     loc_180072209
0x1800720b6  lea     rdx, [rbp+FileSize]; lpFileSize
0x1800720ba  mov     rcx, rsi; hFile
0x1800720bd  mov     r15b, 1
0x1800720c0  call    cs:__imp_GetFileSizeEx
0x1800720c7  nop     dword ptr [rax+rax+00h]
0x1800720cc  test    eax, eax
0x1800720ce  jnz     short loc_1800720E6
0x1800720d0  call    cs:__imp_GetLastError
0x1800720d7  nop     dword ptr [rax+rax+00h]
0x1800720dc  mov     ebx, eax
0x1800720de  test    eax, eax
0x1800720e0  jnz     loc_180072209
0x1800720e6  mov     rbx, qword ptr [rbp+FileSize]
0x1800720ea  cmp     ebx, 1000h
0x1800720f0  jbe     loc_180072204
0x1800720f6  cmp     dword ptr [rbp+FileSize+4], edi
0x1800720f9  jnz     loc_180072204
0x1800720ff  mov     edx, 10h; Alignment
0x180072104  mov     rcx, rbx; Size
0x180072107  call    _o__aligned_malloc_0
0x18007210c  mov     [rbp+hFile], rax
0x180072110  mov     rdi, rax
0x180072113  test    rax, rax
0x180072116  jnz     short loc_180072120
0x180072118  lea     ebx, [rax+8]
0x18007211b  jmp     loc_180072209
0x180072120  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180072124  mov     [rsp+40h+lpOverlapped], 0; lpOverlapped
0x18007212d  mov     r8d, ebx; nNumberOfBytesToRead
0x180072130  mov     rdx, rax; lpBuffer
0x180072133  mov     rcx, rsi; hFile
0x180072136  call    cs:__imp_ReadFile
0x18007213d  nop     dword ptr [rax+rax+00h]
0x180072142  test    eax, eax
0x180072144  jnz     short loc_18007215C
0x180072146  call    cs:__imp_GetLastError
0x18007214d  nop     dword ptr [rax+rax+00h]
0x180072152  mov     ebx, eax
0x180072154  test    eax, eax
0x180072156  jnz     loc_180072209
0x18007215c  mov     r9, rsi
0x18007215f  lea     rdx, [rbp+FileSize]
0x180072163  mov     r8, r12
0x180072166  lea     rcx, [rbp+hFile]
0x18007216a  call    ValidateHiveAndRecoverFromLog
0x18007216f  mov     ebx, eax
0x180072171  test    eax, eax
0x180072173  jnz     short loc_1800721AD
0x180072175  test    r14d, r14d
0x180072178  jz      short loc_180072187
0x18007217a  mov     rcx, rsi
0x18007217d  call    ORCloseFile
0x180072182  xor     esi, esi
0x180072184  xor     r15b, r15b
0x180072187  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18007218e  call    cs:__imp_GetModuleHandleW
0x180072195  nop     dword ptr [rax+rax+00h]
0x18007219a  test    rax, rax
0x18007219d  jnz     short loc_1800721B3
0x18007219f  call    cs:__imp_GetLastError
0x1800721a6  nop     dword ptr [rax+rax+00h]
0x1800721ab  mov     ebx, eax
0x1800721ad  mov     rdi, [rbp+hFile]
0x1800721b1  jmp     short loc_180072209
0x1800721b3  lea     rdx, aRtlvalidrelati; "RtlValidRelativeSecurityDescriptor"
0x1800721ba  mov     rcx, rax; hModule
0x1800721bd  call    cs:__imp_GetProcAddress
0x1800721c4  nop     dword ptr [rax+rax+00h]
0x1800721c9  mov     cs:ORValidRelativeSecurityDescriptor, rax
0x1800721d0  test    rax, rax
0x1800721d3  jz      short loc_18007219F
0x1800721d5  mov     rdx, qword ptr [rbp+FileSize]
0x1800721d9  mov     r9, r13
0x1800721dc  mov     rcx, [rbp+hFile]; Block
0x1800721e0  mov     r8, r12
0x1800721e3  call    OROpenHiveFromMemoryInternal
0x1800721e8  xor     edi, edi
0x1800721ea  mov     ebx, eax
0x1800721ec  test    eax, eax
0x1800721ee  jnz     short loc_180072209
0x1800721f0  mov     rax, [r13+0]
0x1800721f4  xor     r15b, r15b
0x1800721f7  mov     rcx, [rax+10h]
0x1800721fb  mov     [rcx+80h], rsi
0x180072202  jmp     short loc_180072209
0x180072204  mov     ebx, 3F1h
0x180072209  test    rdi, rdi
0x18007220c  jz      short loc_180072216
0x18007220e  mov     rcx, rdi; Block
0x180072211  call    _aligned_free
0x180072216  test    r15b, r15b
0x180072219  jz      short loc_180072223
0x18007221b  mov     rcx, rsi
0x18007221e  call    ORCloseFile
0x180072223  mov     eax, ebx
0x180072225  mov     rbx, [rsp+40h+arg_8]
0x18007222d  add     rsp, 40h
0x180072231  pop     r15
0x180072233  pop     r14
0x180072235  pop     r13
0x180072237  pop     r12
0x180072239  pop     rdi
0x18007223a  pop     rsi
0x18007223b  pop     rbp
0x18007223c  retn
```
