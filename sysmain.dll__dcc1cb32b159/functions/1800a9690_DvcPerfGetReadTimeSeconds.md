# DvcPerfGetReadTimeSeconds

- ea: `0x1800a9690`
- end: `0x1800a97bc`
- name: `DvcPerfGetReadTimeSeconds`
- size: `300`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, DWORD nNumberOfBytesToRead@<edx>, LARGE_INTEGER PerformanceCount)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800a93f4`

## callees

- `0x1800a9690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a96f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a975b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a97a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a96f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a975b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a97a4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800a9726`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800a9726`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800a96d4`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800a96d4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800a9751`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800a9751`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800a96ee`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800a9743`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800a96ee`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800a9743`

## pseudocode

```c
DWORD __fastcall DvcPerfGetReadTimeSeconds(
        HANDLE hFile,
        DWORD nNumberOfBytesToRead,
        LARGE_INTEGER *a3,
        void *a4,
        LARGE_INTEGER PerformanceCount)
{
  double *QuadPart; // rsi
  LARGE_INTEGER v9; // rdx
  DWORD result; // eax
  DWORD LowPart; // ebx
  double v12; // xmm6_8
  BOOL v13; // eax
  BOOL v14; // r14d
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-28h] BYREF
  LARGE_INTEGER v16; // [rsp+38h] [rbp-20h] BYREF

  QuadPart = (double *)PerformanceCount.QuadPart;
  NumberOfBytesRead = 0;
  v9 = *a3;
  *(_QWORD *)PerformanceCount.QuadPart = 0x4024000000000000LL;
  if ( !SetFilePointerEx(hFile, v9, 0, 0) )
    return GetLastError();
  PerformanceCount.QuadPart = 0;
  if ( QueryPerformanceCounter(&PerformanceCount) )
  {
    LowPart = PerformanceCount.LowPart;
    goto LABEL_6;
  }
  result = GetLastError();
  LowPart = 0;
  if ( !result )
  {
LABEL_6:
    v12 = 0.0;
    v13 = ReadFile(hFile, a4, nNumberOfBytesToRead, &NumberOfBytesRead, 0);
    PerformanceCount.QuadPart = 0;
    v14 = v13;
    v16.QuadPart = 0;
    if ( QueryPerformanceCounter(&v16) && QueryPerformanceFrequency(&PerformanceCount) )
    {
      if ( !PerformanceCount.QuadPart )
        return 13;
      result = 0;
      v12 = (double)(int)(v16.LowPart - LowPart) / (double)(int)PerformanceCount.LowPart;
    }
    else
    {
      result = GetLastError();
      if ( result )
        return result;
    }
    if ( v14 && NumberOfBytesRead == nNumberOfBytesToRead )
    {
      *QuadPart = v12;
      return result;
    }
    return GetLastError();
  }
  return result;
}

```

## disassembly

```asm
0x1800a9690  push    rbp
0x1800a9692  push    rbx
0x1800a9693  push    rsi
0x1800a9694  push    rdi
0x1800a9695  push    r14
0x1800a9697  push    r15
0x1800a9699  mov     rbp, rsp
0x1800a969c  sub     rsp, 58h
0x1800a96a0  mov     rsi, qword ptr [rbp+PerformanceCount]
0x1800a96a4  mov     rax, r8
0x1800a96a7  mov     r14, rcx
0x1800a96aa  movaps  [rsp+58h+var_18], xmm6
0x1800a96af  mov     rcx, 4024000000000000h
0x1800a96b9  mov     [rbp+NumberOfBytesRead], 0
0x1800a96c0  mov     r15, r9
0x1800a96c3  mov     edi, edx
0x1800a96c5  mov     rdx, [rax]; liDistanceToMove
0x1800a96c8  xor     r9d, r9d; dwMoveMethod
0x1800a96cb  mov     [rsi], rcx
0x1800a96ce  xor     r8d, r8d; lpNewFilePointer
0x1800a96d1  mov     rcx, r14; hFile
0x1800a96d4  call    cs:__imp_SetFilePointerEx
0x1800a96da  test    eax, eax
0x1800a96dc  jz      loc_1800A97A4
0x1800a96e2  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800a96e6  mov     qword ptr [rbp+PerformanceCount], 0
0x1800a96ee  call    cs:__imp_QueryPerformanceCounter
0x1800a96f4  test    eax, eax
0x1800a96f6  jnz     short loc_1800A9709
0x1800a96f8  call    cs:__imp_GetLastError
0x1800a96fe  xor     ebx, ebx
0x1800a9700  test    eax, eax
0x1800a9702  jz      short loc_1800A970D
0x1800a9704  jmp     loc_1800A97AA
0x1800a9709  mov     rbx, qword ptr [rbp+PerformanceCount]
0x1800a970d  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800a9711  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x1800a971a  mov     r8d, edi; nNumberOfBytesToRead
0x1800a971d  mov     rdx, r15; lpBuffer
0x1800a9720  mov     rcx, r14; hFile
0x1800a9723  xorps   xmm6, xmm6
0x1800a9726  call    cs:__imp_ReadFile
0x1800a972c  lea     rcx, [rbp+var_20]; lpPerformanceCount
0x1800a9730  mov     qword ptr [rbp+PerformanceCount], 0
0x1800a9738  mov     r14d, eax
0x1800a973b  mov     qword ptr [rbp+var_20], 0
0x1800a9743  call    cs:__imp_QueryPerformanceCounter
0x1800a9749  test    eax, eax
0x1800a974b  jz      short loc_1800A975B
0x1800a974d  lea     rcx, [rbp+PerformanceCount]; lpFrequency
0x1800a9751  call    cs:__imp_QueryPerformanceFrequency
0x1800a9757  test    eax, eax
0x1800a9759  jnz     short loc_1800A9767
0x1800a975b  call    cs:__imp_GetLastError
0x1800a9761  test    eax, eax
0x1800a9763  jnz     short loc_1800A97AA
0x1800a9765  jmp     short loc_1800A9794
0x1800a9767  mov     rax, qword ptr [rbp+PerformanceCount]
0x1800a976b  test    rax, rax
0x1800a976e  jnz     short loc_1800A9777
0x1800a9770  mov     eax, 0Dh
0x1800a9775  jmp     short loc_1800A97AA
0x1800a9777  mov     rcx, qword ptr [rbp+var_20]
0x1800a977b  xorps   xmm6, xmm6
0x1800a977e  sub     rcx, rbx
0x1800a9781  xorps   xmm0, xmm0
0x1800a9784  cvtsi2sd xmm0, rax
0x1800a9789  xor     eax, eax
0x1800a978b  cvtsi2sd xmm6, rcx
0x1800a9790  divsd   xmm6, xmm0
0x1800a9794  test    r14d, r14d
0x1800a9797  jz      short loc_1800A97A4
0x1800a9799  cmp     [rbp+NumberOfBytesRead], edi
0x1800a979c  jnz     short loc_1800A97A4
0x1800a979e  movsd   qword ptr [rsi], xmm6
0x1800a97a2  jmp     short loc_1800A97AA
0x1800a97a4  call    cs:__imp_GetLastError
0x1800a97aa  movaps  xmm6, [rsp+58h+var_18]
0x1800a97af  add     rsp, 58h
0x1800a97b3  pop     r15
0x1800a97b5  pop     r14
0x1800a97b7  pop     rdi
0x1800a97b8  pop     rsi
0x1800a97b9  pop     rbx
0x1800a97ba  pop     rbp
0x1800a97bb  retn
```
