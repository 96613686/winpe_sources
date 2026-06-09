# SaveDIBSectionToFile

- ea: `0x1805172b4`
- end: `0x18051759f`
- name: `SaveDIBSectionToFile`
- size: `747`
- prototype: `__int64 __fastcall(HGDIOBJ h)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1805175a8`

## callees

- `0x180249490`
- `0x18024a53c`
- `0x1805172b4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180517544`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180517544`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180517566`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180517566`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18051736c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18051736c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18051750d`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18051750d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1805173db`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18051740d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180517444`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1805174ce`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180517533`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1805173db`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18051740d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180517444`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1805174ce`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180517533`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180517553`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180517553`
- `GDI32!CreateCompatibleDC` at `0x180517468`
- `GDI32!CreateCompatibleDC` at `0x180517468`
- `GDI32!SelectObject` at `0x180517486`
- `GDI32!SelectObject` at `0x1805174e2`
- `GDI32!SelectObject` at `0x180517486`
- `GDI32!SelectObject` at `0x1805174e2`
- `GDI32!DeleteDC` at `0x1805174f1`
- `GDI32!DeleteDC` at `0x1805174f1`
- `GDI32!GetObjectW` at `0x180517304`
- `GDI32!GetObjectW` at `0x180517304`
- `GDI32!GetDIBColorTable` at `0x1805174a4`
- `GDI32!GetDIBColorTable` at `0x1805174a4`

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
0x1805172b4  mov     [rsp-8+arg_8], rbx
0x1805172b9  push    rbp
0x1805172ba  push    rsi
0x1805172bb  push    rdi
0x1805172bc  push    r14
0x1805172be  push    r15
0x1805172c0  lea     rbp, [rsp-3E0h]
0x1805172c8  sub     rsp, 4E0h
0x1805172cf  mov     rax, cs:__security_cookie
0x1805172d6  xor     rax, rsp
0x1805172d9  mov     [rbp+400h+var_30], rax
0x1805172e0  mov     r14, r8
0x1805172e3  mov     r15, rcx
0x1805172e6  mov     ebx, 68h ; 'h'
0x1805172eb  lea     rcx, [rsp+500h+pv]; void *
0x1805172f0  mov     r8d, ebx; Size
0x1805172f3  xor     edx, edx; Val
0x1805172f5  call    memset_0
0x1805172fa  lea     r8, [rsp+500h+pv]; pv
0x1805172ff  mov     edx, ebx; c
0x180517301  mov     rcx, r15; h
0x180517304  call    cs:__imp_GetObjectW
0x18051730b  nop     dword ptr [rax+rax+00h]
0x180517310  test    eax, eax
0x180517312  jz      loc_180517576
0x180517318  cmp     [rbp+400h+nNumberOfBytesToWrite], 0
0x18051731c  jnz     short loc_18051732A
0x18051731e  mov     eax, [rsp+500h+var_4A4]
0x180517322  imul    eax, [rsp+500h+var_488]
0x180517327  mov     [rbp+400h+nNumberOfBytesToWrite], eax
0x18051732a  movzx   ecx, [rsp+500h+var_482]
0x18051732f  cmp     cx, 8
0x180517333  ja      short loc_180517345
0x180517335  cmp     [rbp+400h+var_470], 0
0x180517339  jnz     short loc_180517345
0x18051733b  mov     eax, 1
0x180517340  shl     eax, cl
0x180517342  mov     [rbp+400h+var_470], eax
0x180517345  mov     [rsp+500h+hTemplateFile], 0; hTemplateFile
0x18051734e  xor     r9d, r9d; lpSecurityAttributes
0x180517351  mov     [rsp+500h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180517359  xor     r8d, r8d; dwShareMode
0x18051735c  mov     edx, 40000000h; dwDesiredAccess
0x180517361  mov     [rsp+500h+dwCreationDisposition], 2; dwCreationDisposition
0x180517369  mov     rcx, r14; lpFileName
0x18051736c  call    cs:__imp_CreateFileW
0x180517373  nop     dword ptr [rax+rax+00h]
0x180517378  mov     rdi, rax
0x18051737b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18051737f  jz      loc_180517576
0x180517385  cmp     [rbp+400h+var_480], 3
0x180517389  mov     eax, 4D42h
0x18051738e  mov     ecx, [rbp+400h+var_470]
0x180517391  mov     qword ptr [rbp+400h+lDistanceToMove], 0
0x180517399  mov     [rbp+400h+Buffer], ax
0x18051739d  lea     ecx, ds:36h[rcx*4]
0x1805173a4  jnz     short loc_1805173A9
0x1805173a6  add     ecx, 0Ch
0x1805173a9  add     ecx, 0Fh
0x1805173ac  mov     [rsp+500h+NumberOfBytesWritten], 0
0x1805173b4  and     ecx, 0FFFFFFF0h
0x1805173b7  mov     qword ptr [rsp+500h+dwCreationDisposition], 0; lpOverlapped
0x1805173c0  mov     [rbp+400h+lDistanceToMove+4], ecx
0x1805173c3  lea     r9, [rsp+500h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1805173c8  add     ecx, [rbp+400h+nNumberOfBytesToWrite]
0x1805173cb  lea     rdx, [rbp+400h+Buffer]; lpBuffer
0x1805173cf  mov     [rbp+400h+var_43E], ecx
0x1805173d2  mov     r8d, 0Eh; nNumberOfBytesToWrite
0x1805173d8  mov     rcx, rdi; hFile
0x1805173db  call    cs:__imp_WriteFile
0x1805173e2  nop     dword ptr [rax+rax+00h]
0x1805173e7  mov     ebx, eax
0x1805173e9  test    eax, eax
0x1805173eb  jz      loc_180517550
0x1805173f1  lea     r9, [rsp+500h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1805173f6  mov     qword ptr [rsp+500h+dwCreationDisposition], 0; lpOverlapped
0x1805173ff  mov     r8d, 28h ; '('; nNumberOfBytesToWrite
0x180517405  lea     rdx, [rsp+500h+var_490]; lpBuffer
0x18051740a  mov     rcx, rdi; hFile
0x18051740d  call    cs:__imp_WriteFile
0x180517414  nop     dword ptr [rax+rax+00h]
0x180517419  mov     ebx, eax
0x18051741b  test    eax, eax
0x18051741d  jz      loc_180517550
0x180517423  cmp     [rbp+400h+var_480], 3
0x180517427  jnz     short loc_18051745A
0x180517429  lea     r9, [rsp+500h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18051742e  mov     qword ptr [rsp+500h+dwCreationDisposition], 0; lpOverlapped
0x180517437  mov     r8d, 0Ch; nNumberOfBytesToWrite
0x18051743d  lea     rdx, [rbp+400h+var_468]; lpBuffer
0x180517441  mov     rcx, rdi; hFile
0x180517444  call    cs:__imp_WriteFile
0x18051744b  nop     dword ptr [rax+rax+00h]
0x180517450  mov     ebx, eax
0x180517452  test    eax, eax
0x180517454  jz      loc_180517550
0x18051745a  cmp     [rbp+400h+var_470], 0
0x18051745e  jz      loc_180517501
0x180517464  xor     ecx, ecx; hdc
0x180517466  xor     ebx, ebx
0x180517468  call    cs:__imp_CreateCompatibleDC
0x18051746f  nop     dword ptr [rax+rax+00h]
0x180517474  mov     rsi, rax
0x180517477  test    rax, rax
0x18051747a  jz      loc_180517550
0x180517480  mov     rdx, r15; h
0x180517483  mov     rcx, rax; hdc
0x180517486  call    cs:__imp_SelectObject
0x18051748d  nop     dword ptr [rax+rax+00h]
0x180517492  lea     r9, [rbp+400h+prgbq]; prgbq
0x180517496  xor     edx, edx; iStart
0x180517498  mov     r8d, 100h; cEntries
0x18051749e  mov     rcx, rsi; hdc
0x1805174a1  mov     r15, rax
0x1805174a4  call    cs:__imp_GetDIBColorTable
0x1805174ab  nop     dword ptr [rax+rax+00h]
0x1805174b0  mov     r8d, [rbp+400h+var_470]
0x1805174b4  cmp     eax, r8d
0x1805174b7  jnz     short loc_1805174DC
0x1805174b9  shl     r8d, 2; nNumberOfBytesToWrite
0x1805174bd  lea     r9, [rsp+500h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1805174c2  lea     rdx, [rbp+400h+prgbq]; lpBuffer
0x1805174c6  mov     qword ptr [rsp+500h+dwCreationDisposition], rbx; lpOverlapped
0x1805174cb  mov     rcx, rdi; hFile
0x1805174ce  call    cs:__imp_WriteFile
0x1805174d5  nop     dword ptr [rax+rax+00h]
0x1805174da  mov     ebx, eax
0x1805174dc  mov     rdx, r15; h
0x1805174df  mov     rcx, rsi; hdc
0x1805174e2  call    cs:__imp_SelectObject
0x1805174e9  nop     dword ptr [rax+rax+00h]
0x1805174ee  mov     rcx, rsi; hdc
0x1805174f1  call    cs:__imp_DeleteDC
0x1805174f8  nop     dword ptr [rax+rax+00h]
0x1805174fd  test    ebx, ebx
0x1805174ff  jz      short loc_180517550
0x180517501  mov     edx, [rbp+400h+lDistanceToMove+4]; lDistanceToMove
0x180517504  xor     r9d, r9d; dwMoveMethod
0x180517507  xor     r8d, r8d; lpDistanceToMoveHigh
0x18051750a  mov     rcx, rdi; hFile
0x18051750d  call    cs:__imp_SetFilePointer
0x180517514  nop     dword ptr [rax+rax+00h]
0x180517519  mov     r8d, [rbp+400h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x18051751d  lea     r9, [rsp+500h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180517522  mov     rdx, [rsp+500h+lpBuffer]; lpBuffer
0x180517527  mov     rcx, rdi; hFile
0x18051752a  mov     qword ptr [rsp+500h+dwCreationDisposition], 0; lpOverlapped
0x180517533  call    cs:__imp_WriteFile
0x18051753a  nop     dword ptr [rax+rax+00h]
0x18051753f  mov     rcx, rdi; hFile
0x180517542  mov     ebx, eax
0x180517544  call    cs:__imp_SetEndOfFile
0x18051754b  nop     dword ptr [rax+rax+00h]
0x180517550  mov     rcx, rdi; hObject
0x180517553  call    cs:__imp_CloseHandle
0x18051755a  nop     dword ptr [rax+rax+00h]
0x18051755f  test    ebx, ebx
0x180517561  jnz     short loc_180517572
0x180517563  mov     rcx, r14; lpFileName
0x180517566  call    cs:__imp_DeleteFileW
0x18051756d  nop     dword ptr [rax+rax+00h]
0x180517572  mov     eax, ebx
0x180517574  jmp     short loc_180517578
0x180517576  xor     eax, eax
0x180517578  mov     rcx, [rbp+400h+var_30]
0x18051757f  xor     rcx, rsp; StackCookie
0x180517582  call    __security_check_cookie
0x180517587  mov     rbx, [rsp+500h+arg_8]
0x18051758f  add     rsp, 4E0h
0x180517596  pop     r15
0x180517598  pop     r14
0x18051759a  pop     rdi
0x18051759b  pop     rsi
0x18051759c  pop     rbp
0x18051759d  retn
```
