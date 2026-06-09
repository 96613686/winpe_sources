# TraceWriteOutputA

- ea: `0x180006794`
- end: `0x180006942`
- name: `TraceWriteOutputA`
- size: `430`
- prototype: `__int64 __fastcall(__int64, __int64, int, const CHAR *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800017c0`
- `0x1800046c0`
- `0x180006158`

## callees

- `0x180002d90`
- `0x180006514`
- `0x180006794`
- `0x180009694`
- `0x180009810`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006860`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800068a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006860`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800068a9`
- `api-ms-win-core-console-l1-1-0!WriteConsoleA` at `0x180006921`
- `api-ms-win-core-console-l1-1-0!WriteConsoleA` at `0x180006921`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180006818`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180006849`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180006818`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180006849`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800068eb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800068eb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800067c9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800067c9`

## pseudocode

```c
__int64 __fastcall TraceWriteOutputA(__int64 a1, __int64 a2, int a3, const CHAR *a4)
{
  BOOL v7; // edi
  DWORD v8; // ebp
  int v9; // eax
  int v10; // esi
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
  v8 = lstrlenA(a4);
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
          else if ( TraceMoveClientFileA(a2) )
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
      NumberOfCharsWritten = v8;
      v7 = WriteConsoleA(v14, a4, v8, &NumberOfCharsWritten, 0);
    }
  }
  return v7 ? NumberOfBytesWritten : 0;
}

```

## disassembly

```asm
0x180006794  mov     rax, rsp
0x180006797  mov     [rax+10h], rbx
0x18000679b  mov     [rax+8], rcx
0x18000679f  push    rbp
0x1800067a0  push    rsi
0x1800067a1  push    rdi
0x1800067a2  push    r14
0x1800067a4  push    r15
0x1800067a6  sub     rsp, 30h
0x1800067aa  mov     rcx, r9; lpString
0x1800067ad  mov     dword ptr [rax+18h], 0
0x1800067b4  mov     r15, r9
0x1800067b7  mov     dword ptr [rax+8], 0
0x1800067be  mov     r14d, r8d
0x1800067c1  mov     rbx, rdx
0x1800067c4  mov     edi, 1
0x1800067c9  call    cs:__imp_lstrlenA
0x1800067cf  mov     ebp, eax
0x1800067d1  test    r14b, 2
0x1800067d5  jz      short loc_1800067EB
0x1800067d7  mov     eax, [rbx+110h]
0x1800067dd  mov     esi, [rbx+114h]
0x1800067e3  and     eax, r14d
0x1800067e6  and     esi, r14d
0x1800067e9  jmp     short loc_1800067EF
0x1800067eb  mov     eax, edi
0x1800067ed  mov     esi, edi
0x1800067ef  test    byte ptr [rbx+38h], 2
0x1800067f3  jz      loc_1800068F3
0x1800067f9  test    eax, eax
0x1800067fb  jz      loc_1800068F3
0x180006801  mov     rcx, [rbx+100h]; hFile
0x180006808  lea     rax, [rcx-1]
0x18000680c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006810  ja      loc_1800068F3
0x180006816  xor     edx, edx; lpFileSizeHigh
0x180006818  call    cs:__imp_GetFileSize
0x18000681e  mov     ecx, eax
0x180006820  mov     eax, [rbx+118h]
0x180006826  sub     eax, ebp
0x180006828  cmp     ecx, eax
0x18000682a  jbe     loc_1800068B7
0x180006830  mov     rcx, rbx
0x180006833  call    ReleaseReadLock
0x180006838  mov     rcx, rbx
0x18000683b  call    AcquireWriteLock
0x180006840  mov     rcx, [rbx+100h]; hFile
0x180006847  xor     edx, edx; lpFileSizeHigh
0x180006849  call    cs:__imp_GetFileSize
0x18000684f  mov     ecx, eax
0x180006851  cmp     eax, 0FFFFFFFFh
0x180006854  jnz     short loc_180006875
0x180006856  mov     rcx, rbx; lpCriticalSection
0x180006859  mov     dword ptr [rbx+28h], 0
0x180006860  call    cs:__imp_LeaveCriticalSection
0x180006866  mov     rcx, rbx
0x180006869  call    AcquireReadLock
0x18000686e  xor     eax, eax
0x180006870  jmp     loc_180006931
0x180006875  mov     eax, [rbx+118h]
0x18000687b  sub     eax, ebp
0x18000687d  cmp     ecx, eax
0x18000687f  jbe     short loc_18000688F
0x180006881  mov     rcx, rbx
0x180006884  call    TraceMoveClientFileA
0x180006889  test    eax, eax
0x18000688b  jz      short loc_18000689F
0x18000688d  jmp     short loc_180006856
0x18000688f  mov     rax, [rbx+100h]
0x180006896  sub     rax, rdi
0x180006899  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000689d  ja      short loc_180006856
0x18000689f  mov     rcx, rbx; lpCriticalSection
0x1800068a2  mov     dword ptr [rbx+28h], 0
0x1800068a9  call    cs:__imp_LeaveCriticalSection
0x1800068af  mov     rcx, rbx
0x1800068b2  call    AcquireReadLock
0x1800068b7  mov     rax, [rbx+100h]
0x1800068be  test    rax, rax
0x1800068c1  jz      short loc_1800068F3
0x1800068c3  mov     rax, [rbx+100h]
0x1800068ca  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800068ce  jz      short loc_1800068F3
0x1800068d0  mov     rcx, [rbx+100h]; hFile
0x1800068d7  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800068dc  mov     r8d, ebp; nNumberOfBytesToWrite
0x1800068df  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x1800068e8  mov     rdx, r15; lpBuffer
0x1800068eb  call    cs:__imp_WriteFile
0x1800068f1  mov     edi, eax
0x1800068f3  test    byte ptr [rbx+38h], 4
0x1800068f7  jz      short loc_180006929
0x1800068f9  test    esi, esi
0x1800068fb  jz      short loc_180006929
0x1800068fd  mov     rcx, [rbx+108h]; hConsoleOutput
0x180006904  test    rcx, rcx
0x180006907  jz      short loc_180006929
0x180006909  lea     r9, [rsp+58h+NumberOfCharsWritten]; lpNumberOfCharsWritten
0x18000690e  mov     [rsp+58h+NumberOfCharsWritten], ebp
0x180006912  mov     r8d, ebp; nNumberOfCharsToWrite
0x180006915  mov     [rsp+58h+lpOverlapped], 0; lpReserved
0x18000691e  mov     rdx, r15; lpBuffer
0x180006921  call    cs:__imp_WriteConsoleA
0x180006927  mov     edi, eax
0x180006929  neg     edi
0x18000692b  sbb     eax, eax
0x18000692d  and     eax, [rsp+58h+NumberOfBytesWritten]
0x180006931  mov     rbx, [rsp+58h+arg_8]
0x180006936  add     rsp, 30h
0x18000693a  pop     r15
0x18000693c  pop     r14
0x18000693e  pop     rdi
0x18000693f  pop     rsi
0x180006940  pop     rbp
0x180006941  retn
```
