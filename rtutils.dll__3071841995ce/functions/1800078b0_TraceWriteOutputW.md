# TraceWriteOutputW

- ea: `0x1800078b0`
- end: `0x180007a62`
- name: `TraceWriteOutputW`
- size: `434`
- prototype: `__int64 __fastcall(__int64, __int64, int, const WCHAR *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180005140`
- `0x18000570c`
- `0x1800070c4`

## callees

- `0x180002d90`
- `0x1800074e8`
- `0x1800078b0`
- `0x180009694`
- `0x180009810`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000797e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800079c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000797e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800079c7`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x180007a41`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x180007a41`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180007936`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180007967`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180007936`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180007967`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180007a09`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180007a09`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800078e5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800078e5`

## pseudocode

```c
__int64 __fastcall TraceWriteOutputW(__int64 a1, __int64 a2, int a3, const WCHAR *a4)
{
  BOOL v7; // edi
  DWORD v8; // esi
  int v9; // eax
  int v10; // ebp
  char *v11; // rcx
  DWORD FileSize; // ecx
  void *v14; // rcx
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+8h] BYREF
  int v16; // [rsp+64h] [rbp+Ch]
  DWORD NumberOfCharsWritten; // [rsp+70h] [rbp+18h] BYREF

  v16 = HIDWORD(a1);
  NumberOfCharsWritten = 0;
  NumberOfBytesWritten = 0;
  v7 = 1;
  v8 = 2 * lstrlenW(a4);
  if ( (a3 & 2) != 0 )
  {
    v9 = a3 & *(_DWORD *)(a2 + 272);
    v10 = a3 & *(_DWORD *)(a2 + 276);
  }
  else
  {
    v9 = 1;
    v10 = 1;
  }
  if ( (*(_BYTE *)(a2 + 56) & 2) != 0 )
  {
    if ( v9 )
    {
      v11 = *(char **)(a2 + 256);
      if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        if ( GetFileSize(v11, 0) > *(_DWORD *)(a2 + 280) - v8 )
        {
          ReleaseReadLock(a2);
          AcquireWriteLock(a2);
          FileSize = GetFileSize(*(HANDLE *)(a2 + 256), 0);
          if ( FileSize == -1 )
          {
LABEL_9:
            *(_DWORD *)(a2 + 40) = 0;
            LeaveCriticalSection((LPCRITICAL_SECTION)a2);
            AcquireReadLock(a2);
            return 0;
          }
          if ( FileSize <= *(_DWORD *)(a2 + 280) - v8 )
          {
            if ( (unsigned __int64)(*(_QWORD *)(a2 + 256) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
              goto LABEL_9;
          }
          else if ( TraceMoveClientFileW(a2) )
          {
            goto LABEL_9;
          }
          *(_DWORD *)(a2 + 40) = 0;
          LeaveCriticalSection((LPCRITICAL_SECTION)a2);
          AcquireReadLock(a2);
        }
        if ( *(_QWORD *)(a2 + 256) && *(_QWORD *)(a2 + 256) != -1 )
          v7 = WriteFile(*(HANDLE *)(a2 + 256), a4, v8, &NumberOfBytesWritten, 0);
      }
    }
  }
  if ( (*(_BYTE *)(a2 + 56) & 4) != 0 && v10 )
  {
    v14 = *(void **)(a2 + 264);
    if ( v14 )
    {
      NumberOfCharsWritten = v8 >> 1;
      v7 = WriteConsoleW(v14, a4, v8 >> 1, &NumberOfCharsWritten, 0);
    }
  }
  return v7 ? NumberOfBytesWritten : 0;
}

```

## disassembly

```asm
0x1800078b0  mov     rax, rsp
0x1800078b3  mov     [rax+10h], rbx
0x1800078b7  mov     [rax+8], rcx
0x1800078bb  push    rbp
0x1800078bc  push    rsi
0x1800078bd  push    rdi
0x1800078be  push    r14
0x1800078c0  push    r15
0x1800078c2  sub     rsp, 30h
0x1800078c6  mov     rcx, r9; lpString
0x1800078c9  mov     dword ptr [rax+18h], 0
0x1800078d0  mov     r15, r9
0x1800078d3  mov     dword ptr [rax+8], 0
0x1800078da  mov     r14d, r8d
0x1800078dd  mov     rbx, rdx
0x1800078e0  mov     edi, 1
0x1800078e5  call    cs:__imp_lstrlenW
0x1800078eb  mov     esi, eax
0x1800078ed  add     esi, esi
0x1800078ef  test    r14b, 2
0x1800078f3  jz      short loc_180007909
0x1800078f5  mov     eax, [rbx+110h]
0x1800078fb  mov     ebp, [rbx+114h]
0x180007901  and     eax, r14d
0x180007904  and     ebp, r14d
0x180007907  jmp     short loc_18000790D
0x180007909  mov     eax, edi
0x18000790b  mov     ebp, edi
0x18000790d  test    byte ptr [rbx+38h], 2
0x180007911  jz      loc_180007A11
0x180007917  test    eax, eax
0x180007919  jz      loc_180007A11
0x18000791f  mov     rcx, [rbx+100h]; hFile
0x180007926  lea     rax, [rcx-1]
0x18000792a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000792e  ja      loc_180007A11
0x180007934  xor     edx, edx; lpFileSizeHigh
0x180007936  call    cs:__imp_GetFileSize
0x18000793c  mov     ecx, eax
0x18000793e  mov     eax, [rbx+118h]
0x180007944  sub     eax, esi
0x180007946  cmp     ecx, eax
0x180007948  jbe     loc_1800079D5
0x18000794e  mov     rcx, rbx
0x180007951  call    ReleaseReadLock
0x180007956  mov     rcx, rbx
0x180007959  call    AcquireWriteLock
0x18000795e  mov     rcx, [rbx+100h]; hFile
0x180007965  xor     edx, edx; lpFileSizeHigh
0x180007967  call    cs:__imp_GetFileSize
0x18000796d  mov     ecx, eax
0x18000796f  cmp     eax, 0FFFFFFFFh
0x180007972  jnz     short loc_180007993
0x180007974  mov     rcx, rbx; lpCriticalSection
0x180007977  mov     dword ptr [rbx+28h], 0
0x18000797e  call    cs:__imp_LeaveCriticalSection
0x180007984  mov     rcx, rbx
0x180007987  call    AcquireReadLock
0x18000798c  xor     eax, eax
0x18000798e  jmp     loc_180007A51
0x180007993  mov     eax, [rbx+118h]
0x180007999  sub     eax, esi
0x18000799b  cmp     ecx, eax
0x18000799d  jbe     short loc_1800079AD
0x18000799f  mov     rcx, rbx
0x1800079a2  call    TraceMoveClientFileW
0x1800079a7  test    eax, eax
0x1800079a9  jz      short loc_1800079BD
0x1800079ab  jmp     short loc_180007974
0x1800079ad  mov     rax, [rbx+100h]
0x1800079b4  sub     rax, rdi
0x1800079b7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800079bb  ja      short loc_180007974
0x1800079bd  mov     rcx, rbx; lpCriticalSection
0x1800079c0  mov     dword ptr [rbx+28h], 0
0x1800079c7  call    cs:__imp_LeaveCriticalSection
0x1800079cd  mov     rcx, rbx
0x1800079d0  call    AcquireReadLock
0x1800079d5  mov     rax, [rbx+100h]
0x1800079dc  test    rax, rax
0x1800079df  jz      short loc_180007A11
0x1800079e1  mov     rax, [rbx+100h]
0x1800079e8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800079ec  jz      short loc_180007A11
0x1800079ee  mov     rcx, [rbx+100h]; hFile
0x1800079f5  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800079fa  mov     r8d, esi; nNumberOfBytesToWrite
0x1800079fd  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x180007a06  mov     rdx, r15; lpBuffer
0x180007a09  call    cs:__imp_WriteFile
0x180007a0f  mov     edi, eax
0x180007a11  test    byte ptr [rbx+38h], 4
0x180007a15  jz      short loc_180007A49
0x180007a17  test    ebp, ebp
0x180007a19  jz      short loc_180007A49
0x180007a1b  mov     rcx, [rbx+108h]; hConsoleOutput
0x180007a22  test    rcx, rcx
0x180007a25  jz      short loc_180007A49
0x180007a27  shr     esi, 1
0x180007a29  lea     r9, [rsp+58h+NumberOfCharsWritten]; lpNumberOfCharsWritten
0x180007a2e  mov     r8d, esi; nNumberOfCharsToWrite
0x180007a31  mov     [rsp+58h+NumberOfCharsWritten], esi
0x180007a35  mov     rdx, r15; lpBuffer
0x180007a38  mov     [rsp+58h+lpOverlapped], 0; lpReserved
0x180007a41  call    cs:__imp_WriteConsoleW
0x180007a47  mov     edi, eax
0x180007a49  neg     edi
0x180007a4b  sbb     eax, eax
0x180007a4d  and     eax, [rsp+58h+NumberOfBytesWritten]
0x180007a51  mov     rbx, [rsp+58h+arg_8]
0x180007a56  add     rsp, 30h
0x180007a5a  pop     r15
0x180007a5c  pop     r14
0x180007a5e  pop     rdi
0x180007a5f  pop     rsi
0x180007a60  pop     rbp
0x180007a61  retn
```
