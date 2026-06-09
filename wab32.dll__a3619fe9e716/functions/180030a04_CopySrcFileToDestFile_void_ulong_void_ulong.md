# CopySrcFileToDestFile(void *,ulong,void *,ulong)

- ea: `0x180030a04`
- end: `0x180030b31`
- name: `?CopySrcFileToDestFile@@YAHPEAXK0K@Z`
- size: `301`
- prototype: `__int64 __fastcall(HANDLE hFile, unsigned int, void *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180030300`

## callees

- `0x180030a04`
- `0x180033ae0`

## import_xrefs

- `KERNEL32!SetEndOfFile` at `0x180030a4d`
- `KERNEL32!SetEndOfFile` at `0x180030a4d`
- `KERNEL32!SetFilePointer` at `0x180030a39`
- `KERNEL32!SetFilePointer` at `0x180030a66`
- `KERNEL32!SetFilePointer` at `0x180030a39`
- `KERNEL32!SetFilePointer` at `0x180030a66`
- `KERNEL32!LocalAlloc` at `0x180030a93`
- `KERNEL32!LocalAlloc` at `0x180030a93`
- `KERNEL32!WriteFile` at `0x180030af0`
- `KERNEL32!WriteFile` at `0x180030af0`
- `KERNEL32!GetFileSize` at `0x180030a79`
- `KERNEL32!GetFileSize` at `0x180030a79`
- `KERNEL32!ReadFile` at `0x180030ac7`
- `KERNEL32!ReadFile` at `0x180030ac7`

## pseudocode

```c
__int64 __fastcall CopySrcFileToDestFile(HANDLE hFile, __int64 a2, void *a3)
{
  unsigned int v5; // ebp
  DWORD FileSize; // edi
  unsigned int v7; // esi
  DWORD v8; // ebx
  void *v10; // [rsp+30h] [rbp-38h] BYREF
  DWORD NumberOfBytesRead; // [rsp+88h] [rbp+20h] BYREF

  v5 = 0;
  NumberOfBytesRead = 0;
  v10 = 0;
  if ( SetFilePointer(a3, 0, 0, 0) != -1 )
  {
    if ( SetEndOfFile(a3) )
    {
      if ( SetFilePointer(hFile, 0, 0, 0) != -1 )
      {
        FileSize = GetFileSize(hFile, 0);
        if ( FileSize != -1 )
        {
          v7 = 0x2000;
          v10 = LocalAlloc(0x40u, 0x2000u);
          if ( v10 )
          {
            while ( FileSize )
            {
              v8 = FileSize;
              if ( FileSize >= v7 )
                v8 = v7;
              if ( !ReadFile(hFile, v10, v8, &NumberOfBytesRead, 0)
                || NumberOfBytesRead != v8
                || !WriteFile(a3, v10, v8, &NumberOfBytesRead, 0)
                || NumberOfBytesRead != v8 )
              {
                goto LABEL_15;
              }
              FileSize -= v8;
              v7 = v8;
            }
            v5 = 1;
          }
        }
      }
    }
  }
LABEL_15:
  LocalFreeAndNull(&v10);
  return v5;
}

```

## disassembly

```asm
0x180030a04  mov     rax, rsp
0x180030a07  mov     [rax+8], rbx
0x180030a0b  mov     [rax+10h], rbp
0x180030a0f  mov     [rax+20h], r9d
0x180030a13  push    rsi
0x180030a14  push    rdi
0x180030a15  push    r12
0x180030a17  push    r14
0x180030a19  push    r15
0x180030a1b  sub     rsp, 40h
0x180030a1f  mov     r12, r8
0x180030a22  mov     r15, rcx
0x180030a25  xor     ebp, ebp
0x180030a27  mov     rcx, r12; hFile
0x180030a2a  xor     r9d, r9d; dwMoveMethod
0x180030a2d  mov     [rax+20h], ebp
0x180030a30  xor     r8d, r8d; lpDistanceToMoveHigh
0x180030a33  mov     [rax-38h], rbp
0x180030a37  xor     edx, edx; lDistanceToMove
0x180030a39  call    cs:__imp_SetFilePointer
0x180030a3f  or      ebx, 0FFFFFFFFh
0x180030a42  cmp     eax, ebx
0x180030a44  jz      loc_180030B0E
0x180030a4a  mov     rcx, r12; hFile
0x180030a4d  call    cs:__imp_SetEndOfFile
0x180030a53  test    eax, eax
0x180030a55  jz      loc_180030B0E
0x180030a5b  xor     r9d, r9d; dwMoveMethod
0x180030a5e  xor     r8d, r8d; lpDistanceToMoveHigh
0x180030a61  xor     edx, edx; lDistanceToMove
0x180030a63  mov     rcx, r15; hFile
0x180030a66  call    cs:__imp_SetFilePointer
0x180030a6c  cmp     eax, ebx
0x180030a6e  jz      loc_180030B0E
0x180030a74  xor     edx, edx; lpFileSizeHigh
0x180030a76  mov     rcx, r15; hFile
0x180030a79  call    cs:__imp_GetFileSize
0x180030a7f  mov     edi, eax
0x180030a81  cmp     eax, ebx
0x180030a83  jz      loc_180030B0E
0x180030a89  mov     esi, 2000h
0x180030a8e  lea     ecx, [rbp+40h]; uFlags
0x180030a91  mov     edx, esi; uBytes
0x180030a93  call    cs:__imp_LocalAlloc
0x180030a99  mov     [rsp+68h+var_38], rax
0x180030a9e  mov     r14, rax
0x180030aa1  test    rax, rax
0x180030aa4  jz      short loc_180030B0E
0x180030aa6  test    edi, edi
0x180030aa8  jz      short loc_180030B09
0x180030aaa  cmp     edi, esi
0x180030aac  mov     [rsp+68h+lpOverlapped], rbp; lpOverlapped
0x180030ab1  mov     ebx, edi
0x180030ab3  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180030abb  cmovnb  ebx, esi
0x180030abe  mov     rdx, r14; lpBuffer
0x180030ac1  mov     r8d, ebx; nNumberOfBytesToRead
0x180030ac4  mov     rcx, r15; hFile
0x180030ac7  call    cs:__imp_ReadFile
0x180030acd  test    eax, eax
0x180030acf  jz      short loc_180030B0E
0x180030ad1  cmp     [rsp+68h+NumberOfBytesRead], ebx
0x180030ad8  jnz     short loc_180030B0E
0x180030ada  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesWritten
0x180030ae2  mov     [rsp+68h+lpOverlapped], rbp; lpOverlapped
0x180030ae7  mov     r8d, ebx; nNumberOfBytesToWrite
0x180030aea  mov     rdx, r14; lpBuffer
0x180030aed  mov     rcx, r12; hFile
0x180030af0  call    cs:__imp_WriteFile
0x180030af6  test    eax, eax
0x180030af8  jz      short loc_180030B0E
0x180030afa  cmp     [rsp+68h+NumberOfBytesRead], ebx
0x180030b01  jnz     short loc_180030B0E
0x180030b03  sub     edi, ebx
0x180030b05  mov     esi, ebx
0x180030b07  jmp     short loc_180030AA6
0x180030b09  mov     ebp, 1
0x180030b0e  lea     rcx, [rsp+68h+var_38]; void **
0x180030b13  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z
0x180030b18  mov     rbx, [rsp+68h+arg_0]
0x180030b1d  mov     eax, ebp
0x180030b1f  mov     rbp, [rsp+68h+arg_8]
0x180030b24  add     rsp, 40h
0x180030b28  pop     r15
0x180030b2a  pop     r14
0x180030b2c  pop     r12
0x180030b2e  pop     rdi
0x180030b2f  pop     rsi
0x180030b30  retn
```
