# bcpOpen(tagDBC *,ushort const *,uint,BCPFILE *)

- ea: `0x383973d50`
- end: `0x383973ff0`
- name: `?bcpOpen@@YAFPEAUtagDBC@@PEBGIPEAUBCPFILE@@@Z`
- size: `672`
- prototype: `__int16 __fastcall(struct tagDBC *, LPCWSTR lpFileName, unsigned int, struct BCPFILE *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x38396c5b0`
- `0x38396dd70`
- `0x383970430`

## callees

- `0x38386d3c0`
- `0x38391aed0`
- `0x383973d50`
- `0x383974000`

## import_xrefs

- `KERNEL32!GetLastError` at `0x383973e47`
- `KERNEL32!GetLastError` at `0x383973e47`
- `KERNEL32!CreateFileW` at `0x383973dd6`
- `KERNEL32!CreateFileW` at `0x383973dd6`
- `KERNEL32!GetFileSize` at `0x383973e3a`
- `KERNEL32!GetFileSize` at `0x383973e3a`
- `KERNEL32!CreateFileMappingA` at `0x383973f63`
- `KERNEL32!CreateFileMappingA` at `0x383973f63`
- `KERNEL32!MapViewOfFile` at `0x383973f83`
- `KERNEL32!MapViewOfFile` at `0x383973f83`

## pseudocode

```c
__int64 __fastcall bcpOpen(struct tagDBC *a1, LPCWSTR lpFileName, int a3, struct BCPFILE *a4)
{
  __int16 v4; // bx
  DWORD v6; // edx
  int v10; // r14d
  HANDLE FileW; // rax
  DWORD FileSize; // eax
  struct BCPFILE *v13; // rdx
  __int64 v14; // rsi
  __int64 v15; // rcx
  void *v16; // rax
  struct BCPFILE *v17; // rdx
  unsigned __int64 v18; // rax
  HANDLE FileMappingA; // rax
  LPVOID v20; // rax
  __int64 v21; // rdx
  DWORD FileSizeHigh; // [rsp+70h] [rbp+18h] BYREF

  v4 = 0;
  *(_QWORD *)a4 = 0;
  *((_QWORD *)a4 + 1) = 0;
  *((_QWORD *)a4 + 2) = 0;
  *((_QWORD *)a4 + 3) = 0;
  *((_QWORD *)a4 + 4) = 0;
  *((_QWORD *)a4 + 5) = 0;
  *((_QWORD *)a4 + 6) = 0;
  *((_QWORD *)a4 + 7) = 0;
  *((_QWORD *)a4 + 8) = 0;
  v6 = -1073741824;
  if ( a3 == 1 )
    v6 = 0x80000000;
  v10 = 0;
  FileW = CreateFileW(lpFileName, v6, 1u, 0, (unsigned int)(a3 == 1) + 2, 0x8000080u, 0);
  *(_QWORD *)a4 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    *(_QWORD *)a4 = 0;
    v4 = -1;
    if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
      bidTraceW(off_383B43238[0], 6498313, off_383B49120[0], 6346);
  }
  else
  {
    FileSize = GetFileSize(FileW, &FileSizeHigh);
    v14 = FileSize;
    if ( FileSize == -1 && GetLastError() )
    {
      v10 = 1;
      v15 = 0;
    }
    else
    {
      v15 = v14 + ((unsigned __int64)FileSizeHigh << 32);
    }
    *((_QWORD *)a4 + 4) = v15;
    if ( v10 == 1 )
    {
      bcpClose(a4, v13);
      v4 = -1;
      if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
        bidTraceW(off_383B43238[0], 6508553, off_383B49120[0], 6356);
    }
    else
    {
      *((_QWORD *)a4 + 5) = 0;
      *((_QWORD *)a4 + 6) = 0;
      *((_QWORD *)a4 + 7) = 0;
      if ( a3 != 2 || (v16 = SQLAllocateMemory(a1, 0x10000u), (*((_QWORD *)a4 + 3) = v16) != 0) )
      {
        *((_DWORD *)a4 + 16) = 0;
        if ( a3 == 1 )
        {
          v18 = *((_QWORD *)a4 + 4);
          if ( v18 )
          {
            if ( v18 < 0x2000000 )
            {
              FileMappingA = CreateFileMappingA(*(HANDLE *)a4, 0, 2u, 0, 0, 0);
              *((_QWORD *)a4 + 1) = FileMappingA;
              if ( FileMappingA )
              {
                v20 = MapViewOfFile(FileMappingA, 4u, 0, 0, 0);
                *((_QWORD *)a4 + 2) = v20;
                if ( v20 )
                  *((_DWORD *)a4 + 16) = 1;
              }
            }
          }
        }
      }
      else
      {
        bcpClose(a4, v17);
        v4 = -1;
        if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
          bidTraceW(off_383B43238[0], 6521865, off_383B49120[0], 6369);
      }
    }
  }
  if ( (bidGblFlags & 2) != 0 && (v4 || (bidGblFlags & 0x40) != 0) )
  {
    v21 = 6539265;
    if ( v4 )
      v21 = 6539297;
    bidTraceW(off_383B43238[0], v21, off_383B494E8[0], (unsigned int)v4);
  }
  return (unsigned __int16)v4;
}

```

## disassembly

```asm
0x383973d50  push    rbx
0x383973d52  sub     rsp, 50h
0x383973d56  xor     eax, eax
0x383973d58  xor     ebx, ebx
0x383973d5a  cmp     r8d, 1
0x383973d5e  mov     [r9], rax
0x383973d61  mov     [r9+8], rax
0x383973d65  mov     [r9+10h], rax
0x383973d69  mov     [r9+18h], rax
0x383973d6d  mov     [r9+20h], rax
0x383973d71  mov     [r9+28h], rax
0x383973d75  mov     [r9+30h], rax
0x383973d79  mov     [r9+38h], rax
0x383973d7d  mov     [rsp+58h+arg_0], rbp
0x383973d82  mov     [r9+40h], rax
0x383973d86  setz    al
0x383973d89  mov     r10, rdx
0x383973d8c  mov     [rsp+58h+arg_18], rdi
0x383973d91  add     eax, 2
0x383973d94  cmp     r8d, 1
0x383973d98  mov     [rsp+58h+var_10], r14
0x383973d9d  mov     edx, 0C0000000h
0x383973da2  mov     ebp, r8d
0x383973da5  mov     rdi, r9
0x383973da8  mov     [rsp+58h+hTemplateFile], rbx; hTemplateFile
0x383973dad  mov     [rsp+58h+var_18], r15
0x383973db2  mov     r15, rcx
0x383973db5  mov     ecx, 80000000h
0x383973dba  lea     r8d, [rbx+1]; dwShareMode
0x383973dbe  cmovz   edx, ecx; dwDesiredAccess
0x383973dc1  xor     r9d, r9d; lpSecurityAttributes
0x383973dc4  mov     rcx, r10; lpFileName
0x383973dc7  mov     [rsp+58h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x383973dcf  mov     r14d, ebx
0x383973dd2  mov     [rsp+58h+dwCreationDisposition], eax; dwCreationDisposition
0x383973dd6  call    cs:__imp_CreateFileW
0x383973ddc  mov     [rdi], rax
0x383973ddf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x383973de3  jnz     short loc_383973E2D
0x383973de5  or      eax, eax
0x383973de7  mov     [rdi], rbx
0x383973dea  test    byte ptr cs:_bidGblFlags, 2
0x383973df1  movzx   ebx, ax
0x383973df4  jz      loc_383973F95
0x383973dfa  mov     rcx, cs:off_383B43238; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383973e01  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383973e08  test    rax, rax
0x383973e0b  jz      loc_383973F95
0x383973e11  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383973e18  mov     r9d, 18CAh
0x383973e1e  mov     edx, 632809h
0x383973e23  call    _bidTraceW
0x383973e28  jmp     loc_383973F95
0x383973e2d  lea     rdx, [rsp+58h+FileSizeHigh]; lpFileSizeHigh
0x383973e32  mov     rcx, rax; hFile
0x383973e35  mov     [rsp+58h+arg_8], rsi
0x383973e3a  call    cs:__imp_GetFileSize
0x383973e40  mov     esi, eax
0x383973e42  cmp     eax, 0FFFFFFFFh
0x383973e45  jnz     short loc_383973E5C
0x383973e47  call    cs:__imp_GetLastError
0x383973e4d  test    eax, eax
0x383973e4f  jz      short loc_383973E5C
0x383973e51  mov     r14d, 1
0x383973e57  mov     rcx, rbx
0x383973e5a  jmp     short loc_383973E6A
0x383973e5c  mov     ecx, [rsp+58h+FileSizeHigh]
0x383973e60  mov     rax, rsi
0x383973e63  shl     rcx, 20h
0x383973e67  add     rcx, rsi
0x383973e6a  mov     rsi, [rsp+58h+arg_8]
0x383973e6f  mov     [rdi+20h], rcx
0x383973e73  cmp     r14d, 1
0x383973e77  jnz     short loc_383973EC7
0x383973e79  mov     rcx, rdi; struct tagDBC *
0x383973e7c  call    ?bcpClose@@YAFPEAUtagDBC@@PEAUBCPFILE@@@Z; bcpClose(tagDBC *,BCPFILE *)
0x383973e81  or      eax, 0FFFFFFFFh
0x383973e84  test    byte ptr cs:_bidGblFlags, 2
0x383973e8b  movzx   ebx, ax
0x383973e8e  jz      loc_383973F95
0x383973e94  mov     rcx, cs:off_383B43238; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383973e9b  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383973ea2  test    rax, rax
0x383973ea5  jz      loc_383973F95
0x383973eab  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383973eb2  mov     r9d, 18D4h
0x383973eb8  mov     edx, 635009h
0x383973ebd  call    _bidTraceW
0x383973ec2  jmp     loc_383973F95
0x383973ec7  mov     [rdi+28h], rbx
0x383973ecb  mov     [rdi+30h], rbx
0x383973ecf  mov     [rdi+38h], rbx
0x383973ed3  cmp     ebp, 2
0x383973ed6  jnz     short loc_383973F35
0x383973ed8  mov     edx, 10000h; unsigned __int64
0x383973edd  mov     rcx, r15; struct tagOBJBASE *
0x383973ee0  call    ?SQLAllocateMemory@@YAPEAXPEAUtagOBJBASE@@_K@Z; SQLAllocateMemory(tagOBJBASE *,unsigned __int64)
0x383973ee5  mov     [rdi+18h], rax
0x383973ee9  test    rax, rax
0x383973eec  jnz     short loc_383973F35
0x383973eee  mov     rcx, rdi; struct tagDBC *
0x383973ef1  call    ?bcpClose@@YAFPEAUtagDBC@@PEAUBCPFILE@@@Z; bcpClose(tagDBC *,BCPFILE *)
0x383973ef6  or      eax, 0FFFFFFFFh
0x383973ef9  test    byte ptr cs:_bidGblFlags, bpl
0x383973f00  movzx   ebx, ax
0x383973f03  jz      loc_383973F95
0x383973f09  mov     rcx, cs:off_383B43238; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383973f10  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383973f17  test    rax, rax
0x383973f1a  jz      short loc_383973F95
0x383973f1c  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383973f23  mov     r9d, 18E1h
0x383973f29  mov     edx, 638409h
0x383973f2e  call    _bidTraceW
0x383973f33  jmp     short loc_383973F95
0x383973f35  mov     [rdi+40h], ebx
0x383973f38  cmp     ebp, 1
0x383973f3b  jnz     short loc_383973F95
0x383973f3d  mov     rax, [rdi+20h]
0x383973f41  test    rax, rax
0x383973f44  jz      short loc_383973F95
0x383973f46  cmp     rax, 2000000h
0x383973f4c  jnb     short loc_383973F95
0x383973f4e  mov     rcx, [rdi]; hFile
0x383973f51  lea     r8d, [rbp+1]; flProtect
0x383973f55  xor     r9d, r9d; dwMaximumSizeHigh
0x383973f58  xor     edx, edx; lpFileMappingAttributes
0x383973f5a  mov     qword ptr [rsp+58h+dwFlagsAndAttributes], rbx; lpName
0x383973f5f  mov     [rsp+58h+dwCreationDisposition], ebx; dwMaximumSizeLow
0x383973f63  call    cs:__imp_CreateFileMappingA
0x383973f69  mov     [rdi+8], rax
0x383973f6d  test    rax, rax
0x383973f70  jz      short loc_383973F95
0x383973f72  lea     edx, [rbp+3]; dwDesiredAccess
0x383973f75  xor     r9d, r9d; dwFileOffsetLow
0x383973f78  xor     r8d, r8d; dwFileOffsetHigh
0x383973f7b  mov     rcx, rax; hFileMappingObject
0x383973f7e  mov     qword ptr [rsp+58h+dwCreationDisposition], rbx; dwNumberOfBytesToMap
0x383973f83  call    cs:__imp_MapViewOfFile
0x383973f89  mov     [rdi+10h], rax
0x383973f8d  test    rax, rax
0x383973f90  jz      short loc_383973F95
0x383973f92  mov     [rdi+40h], ebp
0x383973f95  test    byte ptr cs:_bidGblFlags, 2
0x383973f9c  mov     r15, [rsp+58h+var_18]
0x383973fa1  mov     r14, [rsp+58h+var_10]
0x383973fa6  mov     rdi, [rsp+58h+arg_18]
0x383973fab  mov     rbp, [rsp+58h+arg_0]
0x383973fb0  jz      short loc_383973FE7
0x383973fb2  mov     rcx, cs:off_383B43238; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383973fb9  mov     r8, cs:off_383B494E8; "<ODBC|DRIVER|RET> %d{SQLRETURN}\n"
0x383973fc0  test    bx, bx
0x383973fc3  jnz     short loc_383973FCE
0x383973fc5  test    byte ptr cs:_bidGblFlags, 40h
0x383973fcc  jz      short loc_383973FE7
0x383973fce  mov     eax, 63C821h
0x383973fd3  test    bx, bx
0x383973fd6  mov     edx, 63C801h
0x383973fdb  cmovnz  edx, eax
0x383973fde  movsx   r9d, bx
0x383973fe2  call    _bidTraceW
0x383973fe7  movzx   eax, bx
0x383973fea  add     rsp, 50h
0x383973fee  pop     rbx
0x383973fef  retn
```
