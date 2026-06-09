# DcvPerfGetWriteTimeSeconds

- ea: `0x1800a8dd4`
- end: `0x1800a8ef0`
- name: `DcvPerfGetWriteTimeSeconds`
- size: `284`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, DWORD nNumberOfBytesToWrite@<edx>, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800a97c4`

## callees

- `0x1800a8dd4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8e26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8e8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8ed6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8e26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8e8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8ed6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a8e56`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a8e56`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800a8e02`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800a8e02`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800a8e80`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800a8e80`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800a8e1c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800a8e72`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800a8e1c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800a8e72`

## pseudocode

```c
__int64 __fastcall DcvPerfGetWriteTimeSeconds(
        HANDLE hFile,
        DWORD nNumberOfBytesToWrite,
        LARGE_INTEGER *a3,
        const void *a4,
        double *a5)
{
  DWORD LowPart; // ebx
  DWORD LastError; // ecx
  double v10; // xmm6_8
  BOOL v11; // eax
  BOOL v12; // esi
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-30h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp-28h] BYREF
  LARGE_INTEGER v16; // [rsp+40h] [rbp-20h] BYREF

  NumberOfBytesWritten = 0;
  if ( !SetFilePointerEx(hFile, *a3, 0, 0) )
    return GetLastError();
  PerformanceCount.QuadPart = 0;
  if ( QueryPerformanceCounter(&PerformanceCount) )
  {
    LowPart = PerformanceCount.LowPart;
  }
  else
  {
    LowPart = 0;
    LastError = GetLastError();
    if ( LastError )
      return LastError;
  }
  v10 = 0.0;
  v11 = WriteFile(hFile, a4, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
  PerformanceCount.QuadPart = 0;
  v12 = v11;
  v16.QuadPart = 0;
  if ( QueryPerformanceCounter(&v16) && QueryPerformanceFrequency(&PerformanceCount) )
  {
    if ( PerformanceCount.QuadPart )
    {
      LastError = 0;
      v10 = (double)(int)(v16.LowPart - LowPart) / (double)(int)PerformanceCount.LowPart;
LABEL_13:
      if ( v12 && NumberOfBytesWritten == nNumberOfBytesToWrite )
      {
        *a5 = v10;
        return LastError;
      }
      return GetLastError();
    }
    return 13;
  }
  else
  {
    LastError = GetLastError();
    if ( !LastError )
      goto LABEL_13;
  }
  return LastError;
}

```

## disassembly

```asm
0x1800a8dd4  push    rbp
0x1800a8dd6  push    rbx
0x1800a8dd7  push    rsi
0x1800a8dd8  push    rdi
0x1800a8dd9  push    r14
0x1800a8ddb  mov     rbp, rsp
0x1800a8dde  sub     rsp, 60h
0x1800a8de2  mov     rax, r8
0x1800a8de5  movaps  [rsp+60h+var_10], xmm6
0x1800a8dea  mov     r14, r9
0x1800a8ded  mov     [rbp+NumberOfBytesWritten], 0
0x1800a8df4  mov     edi, edx
0x1800a8df6  xor     r9d, r9d; dwMoveMethod
0x1800a8df9  xor     r8d, r8d; lpNewFilePointer
0x1800a8dfc  mov     rsi, rcx
0x1800a8dff  mov     rdx, [rax]; liDistanceToMove
0x1800a8e02  call    cs:__imp_SetFilePointerEx
0x1800a8e08  test    eax, eax
0x1800a8e0a  jz      loc_1800A8ED6
0x1800a8e10  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800a8e14  mov     qword ptr [rbp+PerformanceCount], 0
0x1800a8e1c  call    cs:__imp_QueryPerformanceCounter
0x1800a8e22  test    eax, eax
0x1800a8e24  jnz     short loc_1800A8E39
0x1800a8e26  call    cs:__imp_GetLastError
0x1800a8e2c  xor     ebx, ebx
0x1800a8e2e  mov     ecx, eax
0x1800a8e30  test    eax, eax
0x1800a8e32  jz      short loc_1800A8E3D
0x1800a8e34  jmp     loc_1800A8EDE
0x1800a8e39  mov     rbx, qword ptr [rbp+PerformanceCount]
0x1800a8e3d  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800a8e41  mov     [rsp+60h+lpOverlapped], 0; lpOverlapped
0x1800a8e4a  mov     r8d, edi; nNumberOfBytesToWrite
0x1800a8e4d  mov     rdx, r14; lpBuffer
0x1800a8e50  mov     rcx, rsi; hFile
0x1800a8e53  xorps   xmm6, xmm6
0x1800a8e56  call    cs:__imp_WriteFile
0x1800a8e5c  lea     rcx, [rbp+var_20]; lpPerformanceCount
0x1800a8e60  mov     qword ptr [rbp+PerformanceCount], 0
0x1800a8e68  mov     esi, eax
0x1800a8e6a  mov     qword ptr [rbp+var_20], 0
0x1800a8e72  call    cs:__imp_QueryPerformanceCounter
0x1800a8e78  test    eax, eax
0x1800a8e7a  jz      short loc_1800A8E8A
0x1800a8e7c  lea     rcx, [rbp+PerformanceCount]; lpFrequency
0x1800a8e80  call    cs:__imp_QueryPerformanceFrequency
0x1800a8e86  test    eax, eax
0x1800a8e88  jnz     short loc_1800A8E98
0x1800a8e8a  call    cs:__imp_GetLastError
0x1800a8e90  mov     ecx, eax
0x1800a8e92  test    eax, eax
0x1800a8e94  jnz     short loc_1800A8EDE
0x1800a8e96  jmp     short loc_1800A8EC3
0x1800a8e98  mov     rax, qword ptr [rbp+PerformanceCount]
0x1800a8e9c  test    rax, rax
0x1800a8e9f  jnz     short loc_1800A8EA6
0x1800a8ea1  lea     ecx, [rax+0Dh]
0x1800a8ea4  jmp     short loc_1800A8EDE
0x1800a8ea6  mov     rcx, qword ptr [rbp+var_20]
0x1800a8eaa  xorps   xmm6, xmm6
0x1800a8ead  sub     rcx, rbx
0x1800a8eb0  xorps   xmm0, xmm0
0x1800a8eb3  cvtsi2sd xmm0, rax
0x1800a8eb8  cvtsi2sd xmm6, rcx
0x1800a8ebd  xor     ecx, ecx
0x1800a8ebf  divsd   xmm6, xmm0
0x1800a8ec3  test    esi, esi
0x1800a8ec5  jz      short loc_1800A8ED6
0x1800a8ec7  cmp     [rbp+NumberOfBytesWritten], edi
0x1800a8eca  jnz     short loc_1800A8ED6
0x1800a8ecc  mov     rax, [rbp+arg_20]
0x1800a8ed0  movsd   qword ptr [rax], xmm6
0x1800a8ed4  jmp     short loc_1800A8EDE
0x1800a8ed6  call    cs:__imp_GetLastError
0x1800a8edc  mov     ecx, eax
0x1800a8ede  movaps  xmm6, [rsp+60h+var_10]
0x1800a8ee3  mov     eax, ecx
0x1800a8ee5  add     rsp, 60h
0x1800a8ee9  pop     r14
0x1800a8eeb  pop     rdi
0x1800a8eec  pop     rsi
0x1800a8eed  pop     rbx
0x1800a8eee  pop     rbp
0x1800a8eef  retn
```
