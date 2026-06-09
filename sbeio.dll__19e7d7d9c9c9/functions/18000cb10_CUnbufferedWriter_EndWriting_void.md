# CUnbufferedWriter::EndWriting(void)

- ea: `0x18000cb10`
- end: `0x18000cc73`
- name: `?EndWriting@CUnbufferedWriter@@QEAAJXZ`
- size: `355`
- prototype: `__int64 __fastcall(CUnbufferedWriter *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180009630`

## callees

- `0x18000cb10`
- `0x18000d2b4`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x18000cbc9`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000cbc9`
- `KERNEL32!CloseHandle` at `0x18000cb51`
- `KERNEL32!CloseHandle` at `0x18000cb68`
- `KERNEL32!CloseHandle` at `0x18000cb51`
- `KERNEL32!CloseHandle` at `0x18000cb68`
- `KERNEL32!GetLastError` at `0x18000cbae`
- `KERNEL32!GetLastError` at `0x18000cc4c`
- `KERNEL32!GetLastError` at `0x18000cbae`
- `KERNEL32!GetLastError` at `0x18000cc4c`
- `KERNEL32!ReleaseMutex` at `0x18000cbf8`
- `KERNEL32!ReleaseMutex` at `0x18000cbf8`
- `KERNEL32!CreateFileW` at `0x18000cb9e`
- `KERNEL32!CreateFileW` at `0x18000cb9e`
- `KERNEL32!SetFilePointer` at `0x18000cc0f`
- `KERNEL32!SetFilePointer` at `0x18000cc0f`
- `KERNEL32!WriteFile` at `0x18000cc39`
- `KERNEL32!WriteFile` at `0x18000cc39`

## pseudocode

```c
__int64 __fastcall CUnbufferedWriter::EndWriting(CUnbufferedWriter *this)
{
  int v2; // ebx
  void *v3; // rcx
  void *v4; // rcx
  HANDLE FileW; // rax
  signed int LastError; // eax
  __int64 v7; // rsi
  __int64 v8; // r8
  __int64 v9; // rdx
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp+10h] BYREF
  LONG DistanceToMoveHigh; // [rsp+60h] [rbp+18h] BYREF

  NumberOfBytesWritten = 0;
  DistanceToMoveHigh = 0;
  v2 = CUnbufferedWriter::WaitForOutstandingOperations(this);
  if ( v2 < 0 )
    return (unsigned int)v2;
  *((_DWORD *)this + 16) = 1;
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 != (void *)-1LL )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 3) = -1;
  }
  v4 = (void *)*((_QWORD *)this + 4);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 4) = 0;
  }
  FileW = CreateFileW(*((LPCWSTR *)this + 2), 0xC0000000, 3u, 0, 3u, 0x8000000u, 0);
  *((_QWORD *)this + 3) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    *((_DWORD *)this + 13) = LastError;
    goto LABEL_18;
  }
  v7 = 0;
  WaitForSingleObjectEx(*((HANDLE *)this + 9), 0xFFFFFFFF, 1);
  if ( *((_DWORD *)this + 11) )
  {
    v8 = *((_QWORD *)this + 10);
    v9 = 0;
    do
    {
      if ( *(_DWORD *)(v8 + 48 * v9 + 44) == 1 )
        v7 = v8 + 48 * v9;
      v9 = (unsigned int)(v9 + 1);
    }
    while ( (unsigned int)v9 < *((_DWORD *)this + 11) );
  }
  ReleaseMutex(*((HANDLE *)this + 9));
  if ( SetFilePointer(*((HANDLE *)this + 3), 0, &DistanceToMoveHigh, 2u) == -1
    || v7
    && (!WriteFile(*((HANDLE *)this + 3), *(LPCVOID *)(v7 + 32), *(_DWORD *)(v7 + 40), &NumberOfBytesWritten, 0)
     || *(_DWORD *)(v7 + 40) != NumberOfBytesWritten) )
  {
    LastError = GetLastError();
LABEL_18:
    v2 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000cb10  mov     rax, rsp
0x18000cb13  mov     [rax+8], rbx
0x18000cb17  mov     [rax+20h], rsi
0x18000cb1b  push    rdi
0x18000cb1c  sub     rsp, 40h
0x18000cb20  mov     rdi, rcx
0x18000cb23  mov     dword ptr [rax+10h], 0
0x18000cb2a  mov     dword ptr [rax+18h], 0
0x18000cb31  call    ?WaitForOutstandingOperations@CUnbufferedWriter@@QEAAJXZ; CUnbufferedWriter::WaitForOutstandingOperations(void)
0x18000cb36  mov     ebx, eax
0x18000cb38  test    eax, eax
0x18000cb3a  js      loc_18000CC61
0x18000cb40  mov     dword ptr [rdi+40h], 1
0x18000cb47  mov     rcx, [rdi+18h]; hObject
0x18000cb4b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000cb4f  jz      short loc_18000CB5F
0x18000cb51  call    cs:__imp_CloseHandle
0x18000cb57  mov     qword ptr [rdi+18h], 0FFFFFFFFFFFFFFFFh
0x18000cb5f  mov     rcx, [rdi+20h]; hObject
0x18000cb63  test    rcx, rcx
0x18000cb66  jz      short loc_18000CB76
0x18000cb68  call    cs:__imp_CloseHandle
0x18000cb6e  mov     qword ptr [rdi+20h], 0
0x18000cb76  mov     rcx, [rdi+10h]; lpFileName
0x18000cb7a  mov     r8d, 3; dwShareMode
0x18000cb80  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18000cb89  xor     r9d, r9d; lpSecurityAttributes
0x18000cb8c  mov     [rsp+48h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x18000cb94  mov     edx, 0C0000000h; dwDesiredAccess
0x18000cb99  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000cb9e  call    cs:__imp_CreateFileW
0x18000cba4  mov     [rdi+18h], rax
0x18000cba8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000cbac  jnz     short loc_18000CBBC
0x18000cbae  call    cs:__imp_GetLastError
0x18000cbb4  mov     [rdi+34h], eax
0x18000cbb7  jmp     loc_18000CC52
0x18000cbbc  mov     rcx, [rdi+48h]; hHandle
0x18000cbc0  xor     esi, esi
0x18000cbc2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000cbc5  lea     r8d, [rsi+1]; bAlertable
0x18000cbc9  call    cs:__imp_WaitForSingleObjectEx
0x18000cbcf  cmp     [rdi+2Ch], esi
0x18000cbd2  jbe     short loc_18000CBF4
0x18000cbd4  mov     r8, [rdi+50h]
0x18000cbd8  xor     edx, edx
0x18000cbda  lea     rax, [rdx+rdx*2]
0x18000cbde  shl     rax, 4
0x18000cbe2  add     rax, r8
0x18000cbe5  cmp     dword ptr [rax+2Ch], 1
0x18000cbe9  cmovz   rsi, rax
0x18000cbed  inc     edx
0x18000cbef  cmp     edx, [rdi+2Ch]
0x18000cbf2  jb      short loc_18000CBDA
0x18000cbf4  mov     rcx, [rdi+48h]; hMutex
0x18000cbf8  call    cs:__imp_ReleaseMutex
0x18000cbfe  mov     rcx, [rdi+18h]; hFile
0x18000cc02  lea     r8, [rsp+48h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x18000cc07  mov     r9d, 2; dwMoveMethod
0x18000cc0d  xor     edx, edx; lDistanceToMove
0x18000cc0f  call    cs:__imp_SetFilePointer
0x18000cc15  cmp     eax, 0FFFFFFFFh
0x18000cc18  jz      short loc_18000CC4C
0x18000cc1a  test    rsi, rsi
0x18000cc1d  jz      short loc_18000CC61
0x18000cc1f  mov     r8d, [rsi+28h]; nNumberOfBytesToWrite
0x18000cc23  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000cc28  mov     rdx, [rsi+20h]; lpBuffer
0x18000cc2c  mov     rcx, [rdi+18h]; hFile
0x18000cc30  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; lpOverlapped
0x18000cc39  call    cs:__imp_WriteFile
0x18000cc3f  test    eax, eax
0x18000cc41  jz      short loc_18000CC4C
0x18000cc43  mov     eax, [rsp+48h+NumberOfBytesWritten]
0x18000cc47  cmp     [rsi+28h], eax
0x18000cc4a  jz      short loc_18000CC61
0x18000cc4c  call    cs:__imp_GetLastError
0x18000cc52  mov     ebx, eax
0x18000cc54  test    eax, eax
0x18000cc56  jle     short loc_18000CC61
0x18000cc58  movzx   ebx, ax
0x18000cc5b  or      ebx, 80070000h
0x18000cc61  mov     rsi, [rsp+48h+arg_18]
0x18000cc66  mov     eax, ebx
0x18000cc68  mov     rbx, [rsp+48h+arg_0]
0x18000cc6d  add     rsp, 40h
0x18000cc71  pop     rdi
0x18000cc72  retn
```
