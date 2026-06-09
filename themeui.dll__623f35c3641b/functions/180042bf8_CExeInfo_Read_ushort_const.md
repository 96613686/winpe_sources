# CExeInfo::Read(ushort const *)

- ea: `0x180042bf8`
- end: `0x180042e78`
- name: `?Read@CExeInfo@@QEAAHPEBG@Z`
- size: `640`
- prototype: `__int64 __fastcall(CExeInfo *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180046a70`

## callees

- `0x18000ab10`
- `0x1800358c0`
- `0x18003633c`
- `0x180042bf8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042e2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042e2f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180042e17`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180042e17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042e26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042e26`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180042dc8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180042dc8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180042c4e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180042c4e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180042c8a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180042cdd`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180042d3d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180042db2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180042dea`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180042c8a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180042cdd`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180042d3d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180042db2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180042dea`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180042cc5`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180042d1f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180042d90`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180042cc5`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180042d1f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180042d90`

## pseudocode

```c
_BOOL8 __fastcall CExeInfo::Read(CExeInfo *this, const unsigned __int16 *a2)
{
  BOOL v3; // r14d
  HANDLE FileW; // rdi
  CHAR *v6; // rax
  CHAR *v7; // r15
  _BYTE v9[4]; // [rsp+40h] [rbp-29h] BYREF
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-25h] BYREF
  int v11; // [rsp+48h] [rbp-21h] BYREF
  _WORD Buffer[30]; // [rsp+50h] [rbp-19h] BYREF
  LONG lDistanceToMove; // [rsp+8Ch] [rbp+23h]

  v3 = 0;
  FileW = CreateFileW(a2, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_21;
  memset_0(Buffer, 0, 0x40u);
  NumberOfBytesRead = 0;
  if ( ReadFile(FileW, Buffer, 0x40u, &NumberOfBytesRead, 0) )
  {
    if ( NumberOfBytesRead == 64 && Buffer[0] == 23117 )
    {
      if ( lDistanceToMove )
      {
        SetFilePointer(FileW, lDistanceToMove, 0, 0);
        if ( ReadFile(FileW, this, 0x40u, &NumberOfBytesRead, 0) )
        {
          if ( NumberOfBytesRead == 64 )
          {
            if ( *(_WORD *)this == 17744 )
            {
              StringCchCopyW((unsigned __int16 *)this + 32, 0x104u, a2);
              SetFilePointer(FileW, lDistanceToMove + 72, 0, 0);
              v11 = 0;
              if ( ReadFile(FileW, &v11, 4u, &NumberOfBytesRead, 0) && NumberOfBytesRead == 4 )
              {
                v3 = 1;
                *((_WORD *)this + 31) = ((unsigned __int8)v11 << 8) | BYTE2(v11);
              }
            }
            else if ( *(_WORD *)this == 17742 )
            {
              SetFilePointer(FileW, *((_DWORD *)this + 11), 0, 0);
              v9[0] = 0;
              if ( ReadFile(FileW, v9, 1u, &NumberOfBytesRead, 0) )
              {
                if ( NumberOfBytesRead == 1 )
                {
                  v6 = (CHAR *)LocalAlloc(0x40u, v9[0]);
                  v7 = v6;
                  if ( v6 )
                  {
                    if ( ReadFile(FileW, v6, v9[0], &NumberOfBytesRead, 0) && NumberOfBytesRead == v9[0] )
                      v3 = MultiByteToWideChar(0, 1u, v7, v9[0], (LPWSTR)this + 32, 260) != 0;
                    LocalFree(v7);
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  CloseHandle(FileW);
  if ( !v3 )
  {
LABEL_21:
    memset_0(this, 0, 0x40u);
    *((_WORD *)this + 32) = 0;
  }
  return v3;
}

```

## disassembly

```asm
0x180042bf8  mov     [rsp-8+arg_10], rbx
0x180042bfd  mov     [rsp-8+arg_18], rsi
0x180042c02  push    rbp
0x180042c03  push    rdi
0x180042c04  push    r13
0x180042c06  push    r14
0x180042c08  push    r15
0x180042c0a  lea     rbp, [rsp-37h]
0x180042c0f  sub     rsp, 0A0h
0x180042c16  mov     rax, cs:__security_cookie
0x180042c1d  xor     rax, rsp
0x180042c20  mov     [rbp+57h+var_30], rax
0x180042c24  mov     rsi, rdx
0x180042c27  xor     r14d, r14d
0x180042c2a  mov     rbx, rcx
0x180042c2d  mov     [rsp+0C0h+hTemplateFile], r14; hTemplateFile
0x180042c32  mov     [rsp+0C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180042c3a  xor     r9d, r9d; lpSecurityAttributes
0x180042c3d  mov     edx, 80000000h; dwDesiredAccess
0x180042c42  mov     rcx, rsi; lpFileName
0x180042c45  lea     r8d, [r14+3]; dwShareMode
0x180042c49  mov     [rsp+0C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x180042c4e  call    cs:__imp_CreateFileW
0x180042c54  lea     r13d, [r14+40h]
0x180042c58  mov     rdi, rax
0x180042c5b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180042c5f  jz      loc_180042E3A
0x180042c65  mov     r8d, r13d; Size
0x180042c68  lea     rcx, [rbp+57h+Buffer]; void *
0x180042c6c  xor     edx, edx; Val
0x180042c6e  call    memset_0
0x180042c73  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180042c77  mov     [rbp+57h+NumberOfBytesRead], r14d
0x180042c7b  mov     r8d, r13d; nNumberOfBytesToRead
0x180042c7e  mov     qword ptr [rsp+0C0h+dwCreationDisposition], r14; lpOverlapped
0x180042c83  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x180042c87  mov     rcx, rdi; hFile
0x180042c8a  call    cs:__imp_ReadFile
0x180042c90  test    eax, eax
0x180042c92  jz      loc_180042E2C
0x180042c98  cmp     [rbp+57h+NumberOfBytesRead], r13d
0x180042c9c  jnz     loc_180042E2C
0x180042ca2  mov     eax, 5A4Dh
0x180042ca7  cmp     [rbp+57h+Buffer], ax
0x180042cab  jnz     loc_180042E2C
0x180042cb1  mov     edx, [rbp+57h+lDistanceToMove]; lDistanceToMove
0x180042cb4  test    edx, edx
0x180042cb6  jz      loc_180042E2C
0x180042cbc  xor     r9d, r9d; dwMoveMethod
0x180042cbf  xor     r8d, r8d; lpDistanceToMoveHigh
0x180042cc2  mov     rcx, rdi; hFile
0x180042cc5  call    cs:__imp_SetFilePointer
0x180042ccb  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180042ccf  mov     qword ptr [rsp+0C0h+dwCreationDisposition], r14; lpOverlapped
0x180042cd4  mov     r8d, r13d; nNumberOfBytesToRead
0x180042cd7  mov     rdx, rbx; lpBuffer
0x180042cda  mov     rcx, rdi; hFile
0x180042cdd  call    cs:__imp_ReadFile
0x180042ce3  test    eax, eax
0x180042ce5  jz      loc_180042E2C
0x180042ceb  cmp     [rbp+57h+NumberOfBytesRead], r13d
0x180042cef  jnz     loc_180042E2C
0x180042cf5  mov     eax, 4550h
0x180042cfa  cmp     [rbx], ax
0x180042cfd  jnz     short loc_180042D76
0x180042cff  lea     rcx, [rbx+40h]; unsigned __int16 *
0x180042d03  mov     r8, rsi; unsigned __int16 *
0x180042d06  mov     edx, 104h; unsigned __int64
0x180042d0b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180042d10  mov     edx, [rbp+57h+lDistanceToMove]
0x180042d13  xor     r9d, r9d; dwMoveMethod
0x180042d16  add     edx, 48h ; 'H'; lDistanceToMove
0x180042d19  xor     r8d, r8d; lpDistanceToMoveHigh
0x180042d1c  mov     rcx, rdi; hFile
0x180042d1f  call    cs:__imp_SetFilePointer
0x180042d25  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180042d29  mov     [rbp+57h+var_78], r14d
0x180042d2d  lea     r8d, [r14+4]; nNumberOfBytesToRead
0x180042d31  mov     qword ptr [rsp+0C0h+dwCreationDisposition], r14; lpOverlapped
0x180042d36  lea     rdx, [rbp+57h+var_78]; lpBuffer
0x180042d3a  mov     rcx, rdi; hFile
0x180042d3d  call    cs:__imp_ReadFile
0x180042d43  test    eax, eax
0x180042d45  jz      loc_180042E2C
0x180042d4b  cmp     [rbp+57h+NumberOfBytesRead], 4
0x180042d4f  jnz     loc_180042E2C
0x180042d55  mov     eax, [rbp+57h+var_78]
0x180042d58  lea     r14d, [r13-3Fh]
0x180042d5c  shr     eax, 10h
0x180042d5f  movzx   ecx, al
0x180042d62  movzx   eax, byte ptr [rbp+57h+var_78]
0x180042d66  shl     ax, 8
0x180042d6a  or      cx, ax
0x180042d6d  mov     [rbx+3Eh], cx
0x180042d71  jmp     loc_180042E2C
0x180042d76  mov     eax, 454Eh
0x180042d7b  cmp     [rbx], ax
0x180042d7e  jnz     loc_180042E2C
0x180042d84  mov     edx, [rbx+2Ch]; lDistanceToMove
0x180042d87  xor     r9d, r9d; dwMoveMethod
0x180042d8a  xor     r8d, r8d; lpDistanceToMoveHigh
0x180042d8d  mov     rcx, rdi; hFile
0x180042d90  call    cs:__imp_SetFilePointer
0x180042d96  mov     esi, 1
0x180042d9b  mov     [rbp+57h+var_80], r14b
0x180042d9f  mov     r8d, esi; nNumberOfBytesToRead
0x180042da2  mov     qword ptr [rsp+0C0h+dwCreationDisposition], r14; lpOverlapped
0x180042da7  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180042dab  mov     rcx, rdi; hFile
0x180042dae  lea     rdx, [rbp+57h+var_80]; lpBuffer
0x180042db2  call    cs:__imp_ReadFile
0x180042db8  test    eax, eax
0x180042dba  jz      short loc_180042E2C
0x180042dbc  cmp     [rbp+57h+NumberOfBytesRead], esi
0x180042dbf  jnz     short loc_180042E2C
0x180042dc1  movzx   edx, [rbp+57h+var_80]; uBytes
0x180042dc5  mov     ecx, r13d; uFlags
0x180042dc8  call    cs:__imp_LocalAlloc
0x180042dce  mov     r15, rax
0x180042dd1  test    rax, rax
0x180042dd4  jz      short loc_180042E2C
0x180042dd6  movzx   r8d, [rbp+57h+var_80]; nNumberOfBytesToRead
0x180042ddb  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180042ddf  mov     rdx, rax; lpBuffer
0x180042de2  mov     qword ptr [rsp+0C0h+dwCreationDisposition], r14; lpOverlapped
0x180042de7  mov     rcx, rdi; hFile
0x180042dea  call    cs:__imp_ReadFile
0x180042df0  test    eax, eax
0x180042df2  jz      short loc_180042E23
0x180042df4  movzx   r9d, [rbp+57h+var_80]; cbMultiByte
0x180042df9  cmp     [rbp+57h+NumberOfBytesRead], r9d
0x180042dfd  jnz     short loc_180042E23
0x180042dff  lea     rax, [rbx+40h]
0x180042e03  mov     [rsp+0C0h+dwFlagsAndAttributes], 104h; cchWideChar
0x180042e0b  mov     r8, r15; lpMultiByteStr
0x180042e0e  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; lpWideCharStr
0x180042e13  mov     edx, esi; dwFlags
0x180042e15  xor     ecx, ecx; CodePage
0x180042e17  call    cs:__imp_MultiByteToWideChar
0x180042e1d  test    eax, eax
0x180042e1f  cmovnz  r14d, esi
0x180042e23  mov     rcx, r15; hMem
0x180042e26  call    cs:__imp_LocalFree
0x180042e2c  mov     rcx, rdi; hObject
0x180042e2f  call    cs:__imp_CloseHandle
0x180042e35  test    r14d, r14d
0x180042e38  jnz     short loc_180042E4D
0x180042e3a  mov     r8, r13; Size
0x180042e3d  xor     edx, edx; Val
0x180042e3f  mov     rcx, rbx; void *
0x180042e42  call    memset_0
0x180042e47  xor     ecx, ecx
0x180042e49  mov     [rbx+40h], cx
0x180042e4d  mov     eax, r14d
0x180042e50  mov     rcx, [rbp+57h+var_30]
0x180042e54  xor     rcx, rsp; StackCookie
0x180042e57  call    __security_check_cookie
0x180042e5c  lea     r11, [rsp+0C0h+var_20]
0x180042e64  mov     rbx, [r11+40h]
0x180042e68  mov     rsi, [r11+48h]
0x180042e6c  mov     rsp, r11
0x180042e6f  pop     r15
0x180042e71  pop     r14
0x180042e73  pop     r13
0x180042e75  pop     rdi
0x180042e76  pop     rbp
0x180042e77  retn
```
