# BstrToFile

- ea: `0x180009078`
- end: `0x1800091f3`
- name: `BstrToFile`
- size: `379`
- prototype: `__int64 __fastcall(HANDLE hFile, void *Src)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180009a90`
- `0x180009be0`

## callees

- `0x1800031f4`
- `0x180003200`
- `0x180009078`
- `0x1800091fc`
- `0x180009968`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800090bf`
- `KERNEL32!GetLastError` at `0x1800090fa`
- `KERNEL32!GetLastError` at `0x18000915a`
- `KERNEL32!GetLastError` at `0x1800090bf`
- `KERNEL32!GetLastError` at `0x1800090fa`
- `KERNEL32!GetLastError` at `0x18000915a`
- `KERNEL32!ReadFile` at `0x180009119`
- `KERNEL32!ReadFile` at `0x180009119`
- `KERNEL32!WriteFile` at `0x180009195`
- `KERNEL32!WriteFile` at `0x180009195`
- `KERNEL32!SetFilePointer` at `0x1800090ef`
- `KERNEL32!SetFilePointer` at `0x180009173`
- `KERNEL32!SetFilePointer` at `0x1800090ef`
- `KERNEL32!SetFilePointer` at `0x180009173`
- `KERNEL32!GetFileSize` at `0x1800090b1`
- `KERNEL32!GetFileSize` at `0x1800090b1`
- `KERNEL32!SetLastError` at `0x1800091d4`
- `KERNEL32!SetLastError` at `0x1800091d4`
- `KERNEL32!SetEndOfFile` at `0x1800091a6`
- `KERNEL32!SetEndOfFile` at `0x1800091a6`

## pseudocode

```c
__int64 __fastcall BstrToFile(HANDLE hFile, void *Src)
{
  unsigned int v2; // esi
  void *v4; // rdi
  DWORD FileSize; // eax
  DWORD v7; // r14d
  DWORD LastError; // ebx
  void *v9; // r15
  DWORD v10; // eax
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-10h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+34h] [rbp-Ch] BYREF
  LPCVOID lpBuffer; // [rsp+38h] [rbp-8h]
  int v15; // [rsp+80h] [rbp+40h] BYREF
  int v16; // [rsp+88h] [rbp+48h] BYREF

  v2 = 0;
  NumberOfBytesRead = 0;
  nNumberOfBytesToWrite = 0;
  v4 = 0;
  v16 = 0;
  lpBuffer = 0;
  v15 = 0;
  FileSize = GetFileSize(hFile, 0);
  v7 = FileSize;
  if ( FileSize == -1 )
  {
    LastError = GetLastError();
LABEL_18:
    SetLastError(LastError);
    return v2;
  }
  v9 = operator new(FileSize);
  if ( !v9 )
  {
    LastError = 8;
    goto LABEL_18;
  }
  if ( SetFilePointer(hFile, 0, 0, 0) == -1
    || !ReadFile(hFile, v9, v7, &NumberOfBytesRead, 0)
    || !(unsigned int)GetFileFormat(v9, v7, &v16, &v15) )
  {
    goto LABEL_6;
  }
  if ( !(unsigned int)ConvertUnicodeToText(Src, (__int64)&nNumberOfBytesToWrite) || SetFilePointer(hFile, 0, 0, 0) == -1 )
  {
    v10 = GetLastError();
    v4 = (void *)lpBuffer;
    LastError = v10;
    goto LABEL_15;
  }
  v4 = (void *)lpBuffer;
  if ( !WriteFile(hFile, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesRead, 0) || !SetEndOfFile(hFile) )
  {
LABEL_6:
    LastError = GetLastError();
    goto LABEL_15;
  }
  LastError = 0;
  v2 = 1;
LABEL_15:
  operator delete(v9);
  if ( v4 )
    operator delete(v4);
  if ( !v2 )
    goto LABEL_18;
  return v2;
}

```

## disassembly

```asm
0x180009078  mov     [rsp-28h+arg_0], rbx
0x18000907d  mov     [rsp-28h+arg_8], rsi
0x180009082  push    rbp
0x180009083  push    rdi
0x180009084  push    r12
0x180009086  push    r14
0x180009088  push    r15
0x18000908a  mov     rbp, rsp
0x18000908d  sub     rsp, 40h
0x180009091  xor     esi, esi
0x180009093  mov     [rbp+NumberOfBytesRead], 0
0x18000909a  mov     r12, rdx
0x18000909d  mov     [rbp+nNumberOfBytesToWrite], esi
0x1800090a0  xor     edi, edi
0x1800090a2  mov     [rbp+arg_18], esi
0x1800090a5  xor     edx, edx; lpFileSizeHigh
0x1800090a7  mov     [rbp+lpBuffer], rdi
0x1800090ab  mov     [rbp+arg_10], esi
0x1800090ae  mov     rbx, rcx
0x1800090b1  call    cs:__imp_GetFileSize
0x1800090b7  mov     r14d, eax
0x1800090ba  cmp     eax, 0FFFFFFFFh
0x1800090bd  jnz     short loc_1800090CC
0x1800090bf  call    cs:__imp_GetLastError
0x1800090c5  mov     ebx, eax
0x1800090c7  jmp     loc_1800091D2
0x1800090cc  mov     rcx, r14; Size
0x1800090cf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800090d4  mov     r15, rax
0x1800090d7  test    rax, rax
0x1800090da  jnz     short loc_1800090E4
0x1800090dc  lea     ebx, [rax+8]
0x1800090df  jmp     loc_1800091D2
0x1800090e4  xor     r9d, r9d; dwMoveMethod
0x1800090e7  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800090ea  xor     edx, edx; lDistanceToMove
0x1800090ec  mov     rcx, rbx; hFile
0x1800090ef  call    cs:__imp_SetFilePointer
0x1800090f5  cmp     eax, 0FFFFFFFFh
0x1800090f8  jnz     short loc_180009107
0x1800090fa  call    cs:__imp_GetLastError
0x180009100  mov     ebx, eax
0x180009102  jmp     loc_1800091B9
0x180009107  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000910b  mov     [rsp+40h+lpOverlapped], rsi; lpOverlapped
0x180009110  mov     r8d, r14d; nNumberOfBytesToRead
0x180009113  mov     rdx, r15; lpBuffer
0x180009116  mov     rcx, rbx; hFile
0x180009119  call    cs:__imp_ReadFile
0x18000911f  test    eax, eax
0x180009121  jz      short loc_1800090FA
0x180009123  lea     r9, [rbp+arg_10]
0x180009127  mov     edx, r14d
0x18000912a  lea     r8, [rbp+arg_18]
0x18000912e  mov     rcx, r15
0x180009131  call    GetFileFormat
0x180009136  test    eax, eax
0x180009138  jz      short loc_1800090FA
0x18000913a  mov     r8d, [rbp+arg_10]
0x18000913e  lea     rax, [rbp+nNumberOfBytesToWrite]
0x180009142  mov     edx, [rbp+arg_18]
0x180009145  lea     r9, [rbp+lpBuffer]
0x180009149  mov     rcx, r12; Src
0x18000914c  mov     [rsp+40h+lpOverlapped], rax; __int64
0x180009151  call    ConvertUnicodeToText
0x180009156  test    eax, eax
0x180009158  jnz     short loc_180009168
0x18000915a  call    cs:__imp_GetLastError
0x180009160  mov     rdi, [rbp+lpBuffer]
0x180009164  mov     ebx, eax
0x180009166  jmp     short loc_1800091B9
0x180009168  xor     r9d, r9d; dwMoveMethod
0x18000916b  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000916e  xor     edx, edx; lDistanceToMove
0x180009170  mov     rcx, rbx; hFile
0x180009173  call    cs:__imp_SetFilePointer
0x180009179  cmp     eax, 0FFFFFFFFh
0x18000917c  jz      short loc_18000915A
0x18000917e  mov     rdi, [rbp+lpBuffer]
0x180009182  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesWritten
0x180009186  mov     r8d, [rbp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x18000918a  mov     rdx, rdi; lpBuffer
0x18000918d  mov     rcx, rbx; hFile
0x180009190  mov     [rsp+40h+lpOverlapped], rsi; lpOverlapped
0x180009195  call    cs:__imp_WriteFile
0x18000919b  test    eax, eax
0x18000919d  jz      loc_1800090FA
0x1800091a3  mov     rcx, rbx; hFile
0x1800091a6  call    cs:__imp_SetEndOfFile
0x1800091ac  test    eax, eax
0x1800091ae  jz      loc_1800090FA
0x1800091b4  xor     ebx, ebx
0x1800091b6  lea     esi, [rbx+1]
0x1800091b9  mov     rcx, r15; Block
0x1800091bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800091c1  test    rdi, rdi
0x1800091c4  jz      short loc_1800091CE
0x1800091c6  mov     rcx, rdi; Block
0x1800091c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800091ce  test    esi, esi
0x1800091d0  jnz     short loc_1800091DA
0x1800091d2  mov     ecx, ebx; dwErrCode
0x1800091d4  call    cs:__imp_SetLastError
0x1800091da  mov     rbx, [rsp+40h+arg_0]
0x1800091df  mov     eax, esi
0x1800091e1  mov     rsi, [rsp+40h+arg_8]
0x1800091e6  add     rsp, 40h
0x1800091ea  pop     r15
0x1800091ec  pop     r14
0x1800091ee  pop     r12
0x1800091f0  pop     rdi
0x1800091f1  pop     rbp
0x1800091f2  retn
```
