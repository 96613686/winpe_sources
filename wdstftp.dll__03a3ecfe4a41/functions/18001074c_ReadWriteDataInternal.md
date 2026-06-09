# ReadWriteDataInternal

- ea: `0x18001074c`
- end: `0x180010931`
- name: `ReadWriteDataInternal`
- size: `485`
- prototype: `__int64 __fastcall(HANDLE hFile, LPVOID lpBuffer, DWORD nNumberOfBytesToRead, LPOVERLAPPED lpOverlapped, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180010938`

## callees

- `0x18001074c`
- `0x1800219c4`
- `0x180060e70`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180010786`
- `KERNEL32!WriteFile` at `0x180010786`
- `KERNEL32!GetLastError` at `0x18001079f`
- `KERNEL32!GetLastError` at `0x180010824`
- `KERNEL32!GetLastError` at `0x18001084d`
- `KERNEL32!GetLastError` at `0x1800108dc`
- `KERNEL32!GetLastError` at `0x1800108f9`
- `KERNEL32!GetLastError` at `0x18001079f`
- `KERNEL32!GetLastError` at `0x180010824`
- `KERNEL32!GetLastError` at `0x18001084d`
- `KERNEL32!GetLastError` at `0x1800108dc`
- `KERNEL32!GetLastError` at `0x1800108f9`
- `KERNEL32!GetHandleInformation` at `0x1800107c0`
- `KERNEL32!GetHandleInformation` at `0x1800107c0`
- `KERNEL32!ReadFile` at `0x180010814`
- `KERNEL32!ReadFile` at `0x180010814`
- `KERNEL32!SetLastError` at `0x1800107d3`
- `KERNEL32!SetLastError` at `0x1800107d3`
- `KERNEL32!GetOverlappedResult` at `0x18001088f`
- `KERNEL32!GetOverlappedResult` at `0x18001088f`

## string_xrefs

- `0x1800108b5`: `ReadWriteDataInternal`

## pseudocode

```c
__int64 __fastcall ReadWriteDataInternal(
        HANDLE hFile,
        LPVOID lpBuffer,
        DWORD nNumberOfBytesToRead,
        LPOVERLAPPED lpOverlapped,
        DWORD dwFlags)
{
  signed int v5; // ebx
  int File; // eax
  __int64 v11; // rdx
  DWORD LastError; // eax
  DWORD v13; // r15d
  signed int v14; // ecx
  signed int v15; // eax
  signed int v16; // eax
  __int64 v17; // r8
  signed int v19; // ecx
  signed int v20; // eax
  signed int v21; // eax
  DWORD NumberOfBytesRead[10]; // [rsp+30h] [rbp-28h] BYREF

  v5 = 0;
  NumberOfBytesRead[0] = 0;
  if ( dwFlags )
  {
    File = WriteFile(hFile, lpBuffer, nNumberOfBytesToRead, NumberOfBytesRead, lpOverlapped);
  }
  else if ( !g_useFileIOCallbacks
         || (LastError = GetLastError(), dwFlags = 0, v13 = LastError, GetHandleInformation(hFile, &dwFlags)) )
  {
    File = ReadFile(hFile, lpBuffer, nNumberOfBytesToRead, NumberOfBytesRead, lpOverlapped);
  }
  else
  {
    SetLastError(v13);
    File = ((__int64 (__fastcall *)(HANDLE, LPVOID, _QWORD, DWORD *, LPOVERLAPPED))qword_1800778C0)(
             hFile,
             lpBuffer,
             nNumberOfBytesToRead,
             NumberOfBytesRead,
             lpOverlapped);
  }
  if ( !File )
  {
    v14 = GetLastError();
    v15 = (unsigned __int16)v14 | 0x80070000;
    if ( v14 <= 0 )
      v15 = v14;
    if ( v15 >= 0 )
    {
      v5 = -2147467259;
    }
    else
    {
      v16 = GetLastError();
      v5 = (unsigned __int16)v16 | 0x80070000;
      if ( v16 <= 0 )
        v5 = v16;
    }
    if ( lpOverlapped && v5 == -2147023899 )
    {
      if ( GetOverlappedResult(hFile, lpOverlapped, NumberOfBytesRead, 1) )
      {
        v5 = 0;
      }
      else
      {
        v19 = GetLastError();
        v20 = (unsigned __int16)v19 | 0x80070000;
        if ( v19 <= 0 )
          v20 = v19;
        if ( v20 >= 0 )
        {
          v5 = -2147467259;
        }
        else
        {
          v21 = GetLastError();
          v5 = (unsigned __int16)v21 | 0x80070000;
          if ( v21 <= 0 )
            v5 = v21;
        }
        if ( v5 < 0 )
        {
          v17 = 135;
          goto LABEL_21;
        }
      }
    }
    else if ( v5 < 0 )
    {
      v17 = 142;
      goto LABEL_21;
    }
  }
  if ( nNumberOfBytesToRead != NumberOfBytesRead[0] )
  {
    v5 = -2147024883;
    v17 = 151;
LABEL_21:
    UtilReportError(L"ReadWriteDataInternal", v11, v17, (unsigned int)v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001074c  mov     rax, rsp
0x18001074f  mov     [rax+8], rbx
0x180010753  mov     [rax+10h], rbp
0x180010757  mov     [rax+18h], rsi
0x18001075b  push    rdi
0x18001075c  push    r14
0x18001075e  push    r15
0x180010760  sub     rsp, 40h
0x180010764  xor     ebx, ebx
0x180010766  mov     rdi, r9
0x180010769  and     [rax-28h], ebx
0x18001076c  mov     ebp, r8d
0x18001076f  mov     r14, rdx
0x180010772  mov     rsi, rcx
0x180010775  cmp     [rsp+58h+dwFlags], ebx
0x18001077c  jz      short loc_180010797
0x18001077e  mov     [rax-38h], r9
0x180010782  lea     r9, [rax-28h]; lpNumberOfBytesWritten
0x180010786  call    cs:__imp_WriteFile
0x18001078d  nop     dword ptr [rax+rax+00h]
0x180010792  jmp     loc_180010820
0x180010797  cmp     cs:g_useFileIOCallbacks, ebx
0x18001079d  jz      short loc_180010801
0x18001079f  call    cs:__imp_GetLastError
0x1800107a6  nop     dword ptr [rax+rax+00h]
0x1800107ab  and     [rsp+58h+dwFlags], ebx
0x1800107b2  lea     rdx, [rsp+58h+dwFlags]; lpdwFlags
0x1800107ba  mov     rcx, rsi; hObject
0x1800107bd  mov     r15d, eax
0x1800107c0  call    cs:__imp_GetHandleInformation
0x1800107c7  nop     dword ptr [rax+rax+00h]
0x1800107cc  test    eax, eax
0x1800107ce  jnz     short loc_180010801
0x1800107d0  mov     ecx, r15d; dwErrCode
0x1800107d3  call    cs:__imp_SetLastError
0x1800107da  nop     dword ptr [rax+rax+00h]
0x1800107df  mov     rax, cs:qword_1800778C0
0x1800107e6  lea     r9, [rsp+58h+NumberOfBytesRead]
0x1800107eb  mov     r8d, ebp
0x1800107ee  mov     [rsp+58h+lpOverlapped], rdi
0x1800107f3  mov     rdx, r14
0x1800107f6  mov     rcx, rsi
0x1800107f9  call    cs:__guard_dispatch_icall_fptr
0x1800107ff  jmp     short loc_180010820
0x180010801  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180010806  mov     [rsp+58h+lpOverlapped], rdi; lpOverlapped
0x18001080b  mov     r8d, ebp; nNumberOfBytesToRead
0x18001080e  mov     rdx, r14; lpBuffer
0x180010811  mov     rcx, rsi; hFile
0x180010814  call    cs:__imp_ReadFile
0x18001081b  nop     dword ptr [rax+rax+00h]
0x180010820  test    eax, eax
0x180010822  jnz     short loc_1800108A1
0x180010824  call    cs:__imp_GetLastError
0x18001082b  nop     dword ptr [rax+rax+00h]
0x180010830  mov     r14d, 80070000h
0x180010836  mov     r15d, 80004005h
0x18001083c  mov     ecx, eax
0x18001083e  movzx   eax, ax
0x180010841  or      eax, r14d
0x180010844  test    ecx, ecx
0x180010846  cmovle  eax, ecx
0x180010849  test    eax, eax
0x18001084b  jns     short loc_180010866
0x18001084d  call    cs:__imp_GetLastError
0x180010854  nop     dword ptr [rax+rax+00h]
0x180010859  movzx   ebx, ax
0x18001085c  or      ebx, r14d
0x18001085f  test    eax, eax
0x180010861  cmovle  ebx, eax
0x180010864  jmp     short loc_180010869
0x180010866  mov     ebx, r15d
0x180010869  test    rdi, rdi
0x18001086c  jz      loc_180010921
0x180010872  cmp     ebx, 800703E5h
0x180010878  jnz     loc_180010921
0x18001087e  mov     r9d, 1; bWait
0x180010884  lea     r8, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesTransferred
0x180010889  mov     rdx, rdi; lpOverlapped
0x18001088c  mov     rcx, rsi; hFile
0x18001088f  call    cs:__imp_GetOverlappedResult
0x180010896  nop     dword ptr [rax+rax+00h]
0x18001089b  test    eax, eax
0x18001089d  jz      short loc_1800108DC
0x18001089f  xor     ebx, ebx
0x1800108a1  cmp     ebp, [rsp+58h+NumberOfBytesRead]
0x1800108a5  jz      short loc_1800108C1
0x1800108a7  mov     ebx, 8007000Dh
0x1800108ac  mov     r8d, 97h
0x1800108b2  mov     r9d, ebx
0x1800108b5  lea     rcx, aReadwritedatai; "ReadWriteDataInternal"
0x1800108bc  call    UtilReportError
0x1800108c1  mov     rbp, [rsp+58h+arg_8]
0x1800108c6  mov     eax, ebx
0x1800108c8  mov     rbx, [rsp+58h+arg_0]
0x1800108cd  mov     rsi, [rsp+58h+arg_10]
0x1800108d2  add     rsp, 40h
0x1800108d6  pop     r15
0x1800108d8  pop     r14
0x1800108da  pop     rdi
0x1800108db  retn
0x1800108dc  call    cs:__imp_GetLastError
0x1800108e3  nop     dword ptr [rax+rax+00h]
0x1800108e8  mov     ecx, eax
0x1800108ea  movzx   eax, ax
0x1800108ed  or      eax, r14d
0x1800108f0  test    ecx, ecx
0x1800108f2  cmovle  eax, ecx
0x1800108f5  test    eax, eax
0x1800108f7  jns     short loc_180010912
0x1800108f9  call    cs:__imp_GetLastError
0x180010900  nop     dword ptr [rax+rax+00h]
0x180010905  movzx   ebx, ax
0x180010908  or      ebx, r14d
0x18001090b  test    eax, eax
0x18001090d  cmovle  ebx, eax
0x180010910  jmp     short loc_180010915
0x180010912  mov     ebx, r15d
0x180010915  test    ebx, ebx
0x180010917  jns     short loc_1800108A1
0x180010919  mov     r8d, 87h
0x18001091f  jmp     short loc_1800108B2
0x180010921  test    ebx, ebx
0x180010923  jns     loc_1800108A1
0x180010929  mov     r8d, 8Eh
0x18001092f  jmp     short loc_1800108B2
```
