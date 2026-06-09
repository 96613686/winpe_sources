# SaveDIBSectionToFile

- ea: `0x1804dcb3c`
- end: `0x1804dcdc2`
- name: `SaveDIBSectionToFile`
- size: `646`
- prototype: `__int64 __fastcall(HGDIOBJ h)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1804dcdc8`

## callees

- `0x180233280`
- `0x1802342fc`
- `0x1804dcb3c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1804dcd4f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1804dcd4f`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1804dcd7a`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1804dcd7a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1804dcd90`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1804dcd90`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1804dcbee`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1804dcbee`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1804dcc57`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1804dcc83`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1804dccb4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1804dcd22`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1804dcd6f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1804dcc57`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1804dcc83`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1804dccb4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1804dcd22`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1804dcd6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1804dcd83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1804dcd83`
- `GDI32!CreateCompatibleDC` at `0x1804dccce`
- `GDI32!CreateCompatibleDC` at `0x1804dccce`
- `GDI32!SelectObject` at `0x1804dcce6`
- `GDI32!SelectObject` at `0x1804dcd30`
- `GDI32!SelectObject` at `0x1804dcce6`
- `GDI32!SelectObject` at `0x1804dcd30`
- `GDI32!DeleteDC` at `0x1804dcd39`
- `GDI32!DeleteDC` at `0x1804dcd39`
- `GDI32!GetObjectW` at `0x1804dcb8c`
- `GDI32!GetObjectW` at `0x1804dcb8c`
- `GDI32!GetDIBColorTable` at `0x1804dccfe`
- `GDI32!GetDIBColorTable` at `0x1804dccfe`

## pseudocode

```c
__int64 __fastcall SaveDIBSectionToFile(HGDIOBJ h, __int64 a2, const WCHAR *a3)
{
  HANDLE FileW; // rdi
  int v6; // ecx
  unsigned int v7; // ebx
  HDC CompatibleDC; // rax
  HDC v9; // rsi
  HGDIOBJ v10; // r15
  UINT DIBColorTable; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE pv[12]; // [rsp+50h] [rbp-B0h] BYREF
  int v15; // [rsp+5Ch] [rbp-A4h]
  LPCVOID lpBuffer; // [rsp+68h] [rbp-98h]
  _BYTE v17[8]; // [rsp+70h] [rbp-90h] BYREF
  int v18; // [rsp+78h] [rbp-88h]
  unsigned __int16 v19; // [rsp+7Eh] [rbp-82h]
  int v20; // [rsp+80h] [rbp-80h]
  DWORD nNumberOfBytesToWrite; // [rsp+84h] [rbp-7Ch]
  int v22; // [rsp+90h] [rbp-70h]
  _BYTE v23[40]; // [rsp+98h] [rbp-68h] BYREF
  __int16 Buffer; // [rsp+C0h] [rbp-40h] BYREF
  DWORD v25; // [rsp+C2h] [rbp-3Eh]
  LONG lDistanceToMove[2]; // [rsp+C6h] [rbp-3Ah]
  RGBQUAD prgbq; // [rsp+D0h] [rbp-30h] BYREF

  memset_0(pv, 0, 0x68u);
  if ( !GetObjectW(h, 104, pv) )
    return 0;
  if ( !nNumberOfBytesToWrite )
    nNumberOfBytesToWrite = v18 * v15;
  if ( v19 <= 8u && !v22 )
    v22 = 1 << v19;
  FileW = CreateFileW(a3, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
    return 0;
  *(_QWORD *)lDistanceToMove = 0;
  Buffer = 19778;
  v6 = 4 * v22 + 54;
  if ( v20 == 3 )
    v6 = 4 * v22 + 66;
  NumberOfBytesWritten = 0;
  lDistanceToMove[1] = (v6 + 15) & 0xFFFFFFF0;
  v25 = nNumberOfBytesToWrite + lDistanceToMove[1];
  v7 = WriteFile(FileW, &Buffer, 0xEu, &NumberOfBytesWritten, 0);
  if ( v7 )
  {
    v7 = WriteFile(FileW, v17, 0x28u, &NumberOfBytesWritten, 0);
    if ( v7 )
    {
      if ( v20 != 3 || (v7 = WriteFile(FileW, v23, 0xCu, &NumberOfBytesWritten, 0)) != 0 )
      {
        if ( !v22 )
          goto LABEL_19;
        v7 = 0;
        CompatibleDC = CreateCompatibleDC(0);
        v9 = CompatibleDC;
        if ( CompatibleDC )
        {
          v10 = SelectObject(CompatibleDC, h);
          DIBColorTable = GetDIBColorTable(v9, 0, 0x100u, &prgbq);
          if ( DIBColorTable == v22 )
            v7 = WriteFile(FileW, &prgbq, 4 * v22, &NumberOfBytesWritten, 0);
          SelectObject(v9, v10);
          DeleteDC(v9);
          if ( v7 )
          {
LABEL_19:
            SetFilePointer(FileW, lDistanceToMove[1], 0, 0);
            v7 = WriteFile(FileW, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
            SetEndOfFile(FileW);
          }
        }
      }
    }
  }
  CloseHandle(FileW);
  if ( !v7 )
    DeleteFileW(a3);
  return v7;
}

```

## disassembly

```asm
0x1804dcb3c  mov     [rsp-8+arg_8], rbx
0x1804dcb41  push    rbp
0x1804dcb42  push    rsi
0x1804dcb43  push    rdi
0x1804dcb44  push    r14
0x1804dcb46  push    r15
0x1804dcb48  lea     rbp, [rsp-3E0h]
0x1804dcb50  sub     rsp, 4E0h
0x1804dcb57  mov     rax, cs:__security_cookie
0x1804dcb5e  xor     rax, rsp
0x1804dcb61  mov     [rbp+400h+var_30], rax
0x1804dcb68  mov     r14, r8
0x1804dcb6b  mov     r15, rcx
0x1804dcb6e  mov     ebx, 68h ; 'h'
0x1804dcb73  lea     rcx, [rsp+500h+pv]; void *
0x1804dcb78  mov     r8d, ebx; Size
0x1804dcb7b  xor     edx, edx; Val
0x1804dcb7d  call    memset_0
0x1804dcb82  lea     r8, [rsp+500h+pv]; pv
0x1804dcb87  mov     edx, ebx; c
0x1804dcb89  mov     rcx, r15; h
0x1804dcb8c  call    cs:__imp_GetObjectW
0x1804dcb92  test    eax, eax
0x1804dcb94  jz      loc_1804DCD9A
0x1804dcb9a  cmp     [rbp+400h+nNumberOfBytesToWrite], 0
0x1804dcb9e  jnz     short loc_1804DCBAC
0x1804dcba0  mov     eax, [rsp+500h+var_4A4]
0x1804dcba4  imul    eax, [rsp+500h+var_488]
0x1804dcba9  mov     [rbp+400h+nNumberOfBytesToWrite], eax
0x1804dcbac  movzx   ecx, [rsp+500h+var_482]
0x1804dcbb1  cmp     cx, 8
0x1804dcbb5  ja      short loc_1804DCBC7
0x1804dcbb7  cmp     [rbp+400h+var_470], 0
0x1804dcbbb  jnz     short loc_1804DCBC7
0x1804dcbbd  mov     eax, 1
0x1804dcbc2  shl     eax, cl
0x1804dcbc4  mov     [rbp+400h+var_470], eax
0x1804dcbc7  mov     [rsp+500h+hTemplateFile], 0; hTemplateFile
0x1804dcbd0  xor     r9d, r9d; lpSecurityAttributes
0x1804dcbd3  mov     [rsp+500h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1804dcbdb  xor     r8d, r8d; dwShareMode
0x1804dcbde  mov     edx, 40000000h; dwDesiredAccess
0x1804dcbe3  mov     [rsp+500h+dwCreationDisposition], 2; dwCreationDisposition
0x1804dcbeb  mov     rcx, r14; lpFileName
0x1804dcbee  call    cs:__imp_CreateFileW
0x1804dcbf4  mov     rdi, rax
0x1804dcbf7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1804dcbfb  jz      loc_1804DCD9A
0x1804dcc01  cmp     [rbp+400h+var_480], 3
0x1804dcc05  mov     eax, 4D42h
0x1804dcc0a  mov     ecx, [rbp+400h+var_470]
0x1804dcc0d  mov     qword ptr [rbp+400h+lDistanceToMove], 0
0x1804dcc15  mov     [rbp+400h+Buffer], ax
0x1804dcc19  lea     ecx, ds:36h[rcx*4]
0x1804dcc20  jnz     short loc_1804DCC25
0x1804dcc22  add     ecx, 0Ch
0x1804dcc25  add     ecx, 0Fh
0x1804dcc28  mov     [rsp+500h+NumberOfBytesWritten], 0
0x1804dcc30  and     ecx, 0FFFFFFF0h
0x1804dcc33  mov     qword ptr [rsp+500h+dwCreationDisposition], 0; lpOverlapped
0x1804dcc3c  mov     [rbp+400h+lDistanceToMove+4], ecx
0x1804dcc3f  lea     r9, [rsp+500h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1804dcc44  add     ecx, [rbp+400h+nNumberOfBytesToWrite]
0x1804dcc47  lea     rdx, [rbp+400h+Buffer]; lpBuffer
0x1804dcc4b  mov     [rbp+400h+var_43E], ecx
0x1804dcc4e  mov     r8d, 0Eh; nNumberOfBytesToWrite
0x1804dcc54  mov     rcx, rdi; hFile
0x1804dcc57  call    cs:__imp_WriteFile
0x1804dcc5d  mov     ebx, eax
0x1804dcc5f  test    eax, eax
0x1804dcc61  jz      loc_1804DCD80
0x1804dcc67  lea     r9, [rsp+500h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1804dcc6c  mov     qword ptr [rsp+500h+dwCreationDisposition], 0; lpOverlapped
0x1804dcc75  mov     r8d, 28h ; '('; nNumberOfBytesToWrite
0x1804dcc7b  lea     rdx, [rsp+500h+var_490]; lpBuffer
0x1804dcc80  mov     rcx, rdi; hFile
0x1804dcc83  call    cs:__imp_WriteFile
0x1804dcc89  mov     ebx, eax
0x1804dcc8b  test    eax, eax
0x1804dcc8d  jz      loc_1804DCD80
0x1804dcc93  cmp     [rbp+400h+var_480], 3
0x1804dcc97  jnz     short loc_1804DCCC4
0x1804dcc99  lea     r9, [rsp+500h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1804dcc9e  mov     qword ptr [rsp+500h+dwCreationDisposition], 0; lpOverlapped
0x1804dcca7  mov     r8d, 0Ch; nNumberOfBytesToWrite
0x1804dccad  lea     rdx, [rbp+400h+var_468]; lpBuffer
0x1804dccb1  mov     rcx, rdi; hFile
0x1804dccb4  call    cs:__imp_WriteFile
0x1804dccba  mov     ebx, eax
0x1804dccbc  test    eax, eax
0x1804dccbe  jz      loc_1804DCD80
0x1804dccc4  cmp     [rbp+400h+var_470], 0
0x1804dccc8  jz      short loc_1804DCD43
0x1804dccca  xor     ecx, ecx; hdc
0x1804dcccc  xor     ebx, ebx
0x1804dccce  call    cs:__imp_CreateCompatibleDC
0x1804dccd4  mov     rsi, rax
0x1804dccd7  test    rax, rax
0x1804dccda  jz      loc_1804DCD80
0x1804dcce0  mov     rdx, r15; h
0x1804dcce3  mov     rcx, rax; hdc
0x1804dcce6  call    cs:__imp_SelectObject
0x1804dccec  lea     r9, [rbp+400h+prgbq]; prgbq
0x1804dccf0  xor     edx, edx; iStart
0x1804dccf2  mov     r8d, 100h; cEntries
0x1804dccf8  mov     rcx, rsi; hdc
0x1804dccfb  mov     r15, rax
0x1804dccfe  call    cs:__imp_GetDIBColorTable
0x1804dcd04  mov     r8d, [rbp+400h+var_470]
0x1804dcd08  cmp     eax, r8d
0x1804dcd0b  jnz     short loc_1804DCD2A
0x1804dcd0d  shl     r8d, 2; nNumberOfBytesToWrite
0x1804dcd11  lea     r9, [rsp+500h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1804dcd16  lea     rdx, [rbp+400h+prgbq]; lpBuffer
0x1804dcd1a  mov     qword ptr [rsp+500h+dwCreationDisposition], rbx; lpOverlapped
0x1804dcd1f  mov     rcx, rdi; hFile
0x1804dcd22  call    cs:__imp_WriteFile
0x1804dcd28  mov     ebx, eax
0x1804dcd2a  mov     rdx, r15; h
0x1804dcd2d  mov     rcx, rsi; hdc
0x1804dcd30  call    cs:__imp_SelectObject
0x1804dcd36  mov     rcx, rsi; hdc
0x1804dcd39  call    cs:__imp_DeleteDC
0x1804dcd3f  test    ebx, ebx
0x1804dcd41  jz      short loc_1804DCD80
0x1804dcd43  mov     edx, [rbp+400h+lDistanceToMove+4]; lDistanceToMove
0x1804dcd46  xor     r9d, r9d; dwMoveMethod
0x1804dcd49  xor     r8d, r8d; lpDistanceToMoveHigh
0x1804dcd4c  mov     rcx, rdi; hFile
0x1804dcd4f  call    cs:__imp_SetFilePointer
0x1804dcd55  mov     r8d, [rbp+400h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x1804dcd59  lea     r9, [rsp+500h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1804dcd5e  mov     rdx, [rsp+500h+lpBuffer]; lpBuffer
0x1804dcd63  mov     rcx, rdi; hFile
0x1804dcd66  mov     qword ptr [rsp+500h+dwCreationDisposition], 0; lpOverlapped
0x1804dcd6f  call    cs:__imp_WriteFile
0x1804dcd75  mov     rcx, rdi; hFile
0x1804dcd78  mov     ebx, eax
0x1804dcd7a  call    cs:__imp_SetEndOfFile
0x1804dcd80  mov     rcx, rdi; hObject
0x1804dcd83  call    cs:__imp_CloseHandle
0x1804dcd89  test    ebx, ebx
0x1804dcd8b  jnz     short loc_1804DCD96
0x1804dcd8d  mov     rcx, r14; lpFileName
0x1804dcd90  call    cs:__imp_DeleteFileW
0x1804dcd96  mov     eax, ebx
0x1804dcd98  jmp     short loc_1804DCD9C
0x1804dcd9a  xor     eax, eax
0x1804dcd9c  mov     rcx, [rbp+400h+var_30]
0x1804dcda3  xor     rcx, rsp; StackCookie
0x1804dcda6  call    __security_check_cookie
0x1804dcdab  mov     rbx, [rsp+500h+arg_8]
0x1804dcdb3  add     rsp, 4E0h
0x1804dcdba  pop     r15
0x1804dcdbc  pop     r14
0x1804dcdbe  pop     rdi
0x1804dcdbf  pop     rsi
0x1804dcdc0  pop     rbp
0x1804dcdc1  retn
```
