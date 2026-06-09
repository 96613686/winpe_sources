# T2OSSvcLZDecompressFontBuffer

- ea: `0x180022fcc`
- end: `0x18002321b`
- name: `T2OSSvcLZDecompressFontBuffer`
- size: `591`
- prototype: `__int64 __usercall@<rax>(LPCVOID lpBuffer@<rcx>, DWORD nNumberOfBytesToWrite@<edx>, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800190a4`

## callees

- `0x180017ee0`
- `0x180019dc0`
- `0x18001ead8`
- `0x180021e28`
- `0x180021ed4`
- `0x180022fcc`
- `0x18002a566`
- `0x18002a590`

## import_xrefs

- `KERNEL32!CreateFileA` at `0x180023119`
- `KERNEL32!CreateFileA` at `0x180023119`
- `KERNEL32!CloseHandle` at `0x180023158`
- `KERNEL32!CloseHandle` at `0x180023160`
- `KERNEL32!CloseHandle` at `0x180023158`
- `KERNEL32!CloseHandle` at `0x180023160`
- `KERNEL32!GetFileSize` at `0x180023141`
- `KERNEL32!GetFileSize` at `0x180023141`
- `KERNEL32!GetTempPath2A` at `0x180023048`
- `KERNEL32!GetTempPath2A` at `0x180023048`
- `KERNEL32!DeleteFileA` at `0x1800230e8`
- `KERNEL32!DeleteFileA` at `0x180023134`
- `KERNEL32!DeleteFileA` at `0x18002317f`
- `KERNEL32!DeleteFileA` at `0x180023189`
- `KERNEL32!DeleteFileA` at `0x1800231ba`
- `KERNEL32!DeleteFileA` at `0x1800231c4`
- `KERNEL32!DeleteFileA` at `0x1800231d7`
- `KERNEL32!DeleteFileA` at `0x1800231e1`
- `KERNEL32!DeleteFileA` at `0x1800230e8`
- `KERNEL32!DeleteFileA` at `0x180023134`
- `KERNEL32!DeleteFileA` at `0x18002317f`
- `KERNEL32!DeleteFileA` at `0x180023189`
- `KERNEL32!DeleteFileA` at `0x1800231ba`
- `KERNEL32!DeleteFileA` at `0x1800231c4`
- `KERNEL32!DeleteFileA` at `0x1800231d7`
- `KERNEL32!DeleteFileA` at `0x1800231e1`
- `KERNEL32!GetTempFileNameA` at `0x18002306f`
- `KERNEL32!GetTempFileNameA` at `0x180023092`
- `KERNEL32!GetTempFileNameA` at `0x18002306f`
- `KERNEL32!GetTempFileNameA` at `0x180023092`

## pseudocode

```c
__int64 __fastcall T2OSSvcLZDecompressFontBuffer(
        void *lpBuffer,
        DWORD nNumberOfBytesToWrite,
        LPVOID *a3,
        int *a4,
        __int64 a5)
{
  int v9; // eax
  HANDLE FileA; // rax
  void *v11; // rdi
  DWORD FileSize; // eax
  void *v13; // rax
  int v14; // edi
  CHAR TempFileName[272]; // [rsp+40h] [rbp-C0h] BYREF
  CHAR FileName[272]; // [rsp+150h] [rbp+50h] BYREF
  CHAR PathName[272]; // [rsp+260h] [rbp+160h] BYREF

  memset_0(TempFileName, 0, 0x104u);
  memset_0(PathName, 0, 0x104u);
  memset_0(FileName, 0, 0x104u);
  if ( !(unsigned int)GetTempPath2A(260, PathName)
    || !GetTempFileNameA(PathName, "UCMTP", 0, TempFileName)
    || !GetTempFileNameA(PathName, "CMPTP", 0, FileName) )
  {
    *(_DWORD *)(a5 + 944) = 513;
    return 0;
  }
  v9 = CopyEmbeddedFontDataToFile(lpBuffer, nNumberOfBytesToWrite, FileName);
  if ( v9 )
  {
    *(_DWORD *)(a5 + 944) = v9;
    return 0;
  }
  T2free(lpBuffer);
  if ( !(unsigned int)Expand(FileName, TempFileName) )
  {
    *(_DWORD *)(a5 + 944) = 0;
LABEL_8:
    DeleteFileA(FileName);
    return 0;
  }
  FileA = CreateFileA(TempFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v11 = FileA;
  if ( FileA == (HANDLE)-1LL )
  {
    *(_DWORD *)(a5 + 944) = 0;
LABEL_11:
    DeleteFileA(TempFileName);
    goto LABEL_8;
  }
  FileSize = GetFileSize(FileA, 0);
  *a4 = FileSize;
  if ( FileSize == -1 )
  {
    *(_DWORD *)(a5 + 944) = 0;
    CloseHandle(v11);
    goto LABEL_11;
  }
  CloseHandle(v11);
  v13 = (void *)T2malloc((unsigned int)*a4);
  *a3 = v13;
  if ( v13 )
  {
    v14 = CopyEmbeddedFontDataFromFile(v13, *a4, TempFileName);
    if ( !v14 )
    {
      DeleteFileA(TempFileName);
      DeleteFileA(FileName);
      return 1;
    }
    T2free(*a3);
    DeleteFileA(TempFileName);
    DeleteFileA(FileName);
    *(_DWORD *)(a5 + 944) = v14;
  }
  else
  {
    DeleteFileA(TempFileName);
    DeleteFileA(FileName);
    *(_DWORD *)(a5 + 944) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180022fcc  push    rbp
0x180022fce  push    rbx
0x180022fcf  push    rsi
0x180022fd0  push    rdi
0x180022fd1  push    r12
0x180022fd3  push    r14
0x180022fd5  push    r15
0x180022fd7  lea     rbp, [rsp-280h]
0x180022fdf  sub     rsp, 380h
0x180022fe6  mov     rax, cs:__security_cookie
0x180022fed  xor     rax, rsp
0x180022ff0  mov     [rbp+2B0h+var_40], rax
0x180022ff7  mov     rbx, [rbp+2B0h+arg_20]
0x180022ffe  mov     r14, r8
0x180023001  mov     r15d, edx
0x180023004  mov     rdi, rcx
0x180023007  mov     r12d, 104h
0x18002300d  lea     rcx, [rsp+3B0h+TempFileName]; void *
0x180023012  mov     r8d, r12d; Size
0x180023015  xor     edx, edx; Val
0x180023017  mov     rsi, r9
0x18002301a  call    memset_0
0x18002301f  mov     r8d, r12d; Size
0x180023022  lea     rcx, [rbp+2B0h+PathName]; void *
0x180023029  xor     edx, edx; Val
0x18002302b  call    memset_0
0x180023030  mov     r8d, r12d; Size
0x180023033  lea     rcx, [rbp+2B0h+FileName]; void *
0x180023037  xor     edx, edx; Val
0x180023039  call    memset_0
0x18002303e  lea     rdx, [rbp+2B0h+PathName]
0x180023045  mov     ecx, r12d
0x180023048  call    cs:__imp_GetTempPath2A
0x18002304e  xor     r12d, r12d
0x180023051  test    eax, eax
0x180023053  jz      loc_1800231EE
0x180023059  lea     r9, [rsp+3B0h+TempFileName]; lpTempFileName
0x18002305e  xor     r8d, r8d; uUnique
0x180023061  lea     rdx, PrefixString; "UCMTP"
0x180023068  lea     rcx, [rbp+2B0h+PathName]; lpPathName
0x18002306f  call    cs:__imp_GetTempFileNameA
0x180023075  test    eax, eax
0x180023077  jz      loc_1800231EE
0x18002307d  lea     r9, [rbp+2B0h+FileName]; lpTempFileName
0x180023081  xor     r8d, r8d; uUnique
0x180023084  lea     rdx, aCmptp; "CMPTP"
0x18002308b  lea     rcx, [rbp+2B0h+PathName]; lpPathName
0x180023092  call    cs:__imp_GetTempFileNameA
0x180023098  test    eax, eax
0x18002309a  jz      loc_1800231EE
0x1800230a0  lea     r9d, [r12+1]
0x1800230a5  mov     edx, r15d; nNumberOfBytesToWrite
0x1800230a8  lea     r8, [rbp+2B0h+FileName]; lpFileName
0x1800230ac  mov     rcx, rdi; lpBuffer
0x1800230af  call    CopyEmbeddedFontDataToFile
0x1800230b4  test    eax, eax
0x1800230b6  jz      short loc_1800230C3
0x1800230b8  mov     [rbx+3B0h], eax
0x1800230be  jmp     loc_1800231F8
0x1800230c3  mov     rcx, rdi; lpMem
0x1800230c6  call    T2free
0x1800230cb  lea     rdx, [rsp+3B0h+TempFileName]; LPSTR
0x1800230d0  lea     rcx, [rbp+2B0h+FileName]; lpFileName
0x1800230d4  call    Expand
0x1800230d9  test    eax, eax
0x1800230db  jnz     short loc_1800230F3
0x1800230dd  mov     [rbx+3B0h], r12d
0x1800230e4  lea     rcx, [rbp+2B0h+FileName]; lpFileName
0x1800230e8  call    cs:__imp_DeleteFileA
0x1800230ee  jmp     loc_1800231F8
0x1800230f3  xor     r9d, r9d; lpSecurityAttributes
0x1800230f6  mov     [rsp+3B0h+hTemplateFile], r12; hTemplateFile
0x1800230fb  mov     [rsp+3B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180023103  lea     rcx, [rsp+3B0h+TempFileName]; lpFileName
0x180023108  mov     edx, 80000000h; dwDesiredAccess
0x18002310d  mov     [rsp+3B0h+dwCreationDisposition], 3; dwCreationDisposition
0x180023115  lea     r8d, [r9+1]; dwShareMode
0x180023119  call    cs:__imp_CreateFileA
0x18002311f  mov     rdi, rax
0x180023122  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023126  jnz     short loc_18002313C
0x180023128  mov     [rbx+3B0h], r12d
0x18002312f  lea     rcx, [rsp+3B0h+TempFileName]; lpFileName
0x180023134  call    cs:__imp_DeleteFileA
0x18002313a  jmp     short loc_1800230E4
0x18002313c  xor     edx, edx; lpFileSizeHigh
0x18002313e  mov     rcx, rdi; hFile
0x180023141  call    cs:__imp_GetFileSize
0x180023147  mov     [rsi], eax
0x180023149  mov     rcx, rdi; hObject
0x18002314c  cmp     eax, 0FFFFFFFFh
0x18002314f  jnz     short loc_180023160
0x180023151  mov     [rbx+3B0h], r12d
0x180023158  call    cs:__imp_CloseHandle
0x18002315e  jmp     short loc_18002312F
0x180023160  call    cs:__imp_CloseHandle
0x180023166  mov     ecx, [rsi]; dwBytes
0x180023168  mov     edx, 1
0x18002316d  call    T2malloc
0x180023172  mov     [r14], rax
0x180023175  test    rax, rax
0x180023178  jnz     short loc_180023198
0x18002317a  lea     rcx, [rsp+3B0h+TempFileName]; lpFileName
0x18002317f  call    cs:__imp_DeleteFileA
0x180023185  lea     rcx, [rbp+2B0h+FileName]; lpFileName
0x180023189  call    cs:__imp_DeleteFileA
0x18002318f  mov     [rbx+3B0h], r12d
0x180023196  jmp     short loc_1800231F8
0x180023198  mov     edx, [rsi]; lBytes
0x18002319a  lea     r8, [rsp+3B0h+TempFileName]; lpFileName
0x18002319f  mov     rcx, rax; lpBuffer
0x1800231a2  call    CopyEmbeddedFontDataFromFile
0x1800231a7  mov     edi, eax
0x1800231a9  test    eax, eax
0x1800231ab  jz      short loc_1800231D2
0x1800231ad  mov     rcx, [r14]; lpMem
0x1800231b0  call    T2free
0x1800231b5  lea     rcx, [rsp+3B0h+TempFileName]; lpFileName
0x1800231ba  call    cs:__imp_DeleteFileA
0x1800231c0  lea     rcx, [rbp+2B0h+FileName]; lpFileName
0x1800231c4  call    cs:__imp_DeleteFileA
0x1800231ca  mov     [rbx+3B0h], edi
0x1800231d0  jmp     short loc_1800231F8
0x1800231d2  lea     rcx, [rsp+3B0h+TempFileName]; lpFileName
0x1800231d7  call    cs:__imp_DeleteFileA
0x1800231dd  lea     rcx, [rbp+2B0h+FileName]; lpFileName
0x1800231e1  call    cs:__imp_DeleteFileA
0x1800231e7  mov     eax, 1
0x1800231ec  jmp     short loc_1800231FA
0x1800231ee  mov     dword ptr [rbx+3B0h], 201h
0x1800231f8  xor     eax, eax
0x1800231fa  mov     rcx, [rbp+2B0h+var_40]
0x180023201  xor     rcx, rsp; StackCookie
0x180023204  call    __security_check_cookie
0x180023209  add     rsp, 380h
0x180023210  pop     r15
0x180023212  pop     r14
0x180023214  pop     r12
0x180023216  pop     rdi
0x180023217  pop     rsi
0x180023218  pop     rbx
0x180023219  pop     rbp
0x18002321a  retn
```
