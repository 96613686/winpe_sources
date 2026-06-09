# LOG_WRITER::Flush(STRA *,int,void *)

- ea: `0x180004bec`
- end: `0x180004ccd`
- name: `?Flush@LOG_WRITER@@AEAAJPEAVSTRA@@HPEAX@Z`
- size: `225`
- prototype: `__int64 __fastcall(LOG_WRITER *this, struct STRA *, int, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180004b28`
- `0x180004fe4`

## callees

- `0x180004bec`
- `0x180004fe4`
- `0x180005880`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c70`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180004c66`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180004c66`

## pseudocode

```c
__int64 __fastcall LOG_WRITER::Flush(LOG_WRITER *this, struct STRA *a2, int a3, void *a4)
{
  unsigned int v5; // r8d
  void *v6; // rax
  unsigned int LogFileHandle; // ebx
  signed int LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp+10h] BYREF
  void *v13; // [rsp+68h] [rbp+20h] BYREF

  v13 = a4;
  NumberOfBytesWritten = 0;
  v5 = *((_DWORD *)a2 + 12);
  v6 = a4;
  if ( !v5 )
    return 0;
  if ( a4 != (void *)-1LL )
  {
    LogFileHandle = 0;
    if ( !a4 )
    {
      LogFileHandle = LOG_WRITER::GetLogFileHandle(this, &v13, v5, 0);
      if ( (LogFileHandle & 0x80000000) != 0 )
        goto LABEL_12;
      v6 = v13;
    }
    if ( !WriteFile(v6, *((LPCVOID *)a2 + 4), *((_DWORD *)a2 + 12), &NumberOfBytesWritten, 0) )
    {
      LastError = GetLastError();
      LogFileHandle = LastError;
      if ( LastError > 0 )
        LogFileHandle = (unsigned __int16)LastError | 0x80070000;
      LOG_WRITER::LogW3LogSvcEvent(this, 3221231476LL, *((_QWORD *)this + 6), LogFileHandle, 4);
    }
    goto LABEL_12;
  }
  LogFileHandle = -2147024890;
LABEL_12:
  if ( a3 )
  {
    **((_BYTE **)a2 + 4) = 0;
    *((_DWORD *)a2 + 12) = 0;
  }
  *((_QWORD *)this + 80) += NumberOfBytesWritten;
  return LogFileHandle;
}

```

## disassembly

```asm
0x180004bec  mov     [rsp+arg_0], rbx
0x180004bf1  mov     [rsp+arg_18], r9
0x180004bf6  push    rbp
0x180004bf7  push    rsi
0x180004bf8  push    rdi
0x180004bf9  sub     rsp, 30h
0x180004bfd  mov     ebp, r8d
0x180004c00  mov     [rsp+48h+NumberOfBytesWritten], 0
0x180004c08  mov     r8d, [rdx+30h]; unsigned int
0x180004c0c  mov     rax, r9
0x180004c0f  mov     rsi, rdx
0x180004c12  mov     rdi, rcx
0x180004c15  test    r8d, r8d
0x180004c18  jnz     short loc_180004C21
0x180004c1a  xor     eax, eax
0x180004c1c  jmp     loc_180004CC0
0x180004c21  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004c25  jnz     short loc_180004C2E
0x180004c27  mov     ebx, 80070006h
0x180004c2c  jmp     short loc_180004CA1
0x180004c2e  xor     ebx, ebx
0x180004c30  test    rax, rax
0x180004c33  jnz     short loc_180004C4D
0x180004c35  xor     r9d, r9d; int
0x180004c38  lea     rdx, [rsp+48h+arg_18]; void **
0x180004c3d  call    ?GetLogFileHandle@LOG_WRITER@@AEAAJPEAPEAXKH@Z; LOG_WRITER::GetLogFileHandle(void * *,ulong,int)
0x180004c42  mov     ebx, eax
0x180004c44  test    eax, eax
0x180004c46  js      short loc_180004CA1
0x180004c48  mov     rax, [rsp+48h+arg_18]
0x180004c4d  mov     r8d, [rsi+30h]; nNumberOfBytesToWrite
0x180004c51  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180004c56  mov     rdx, [rsi+20h]; lpBuffer
0x180004c5a  mov     rcx, rax; hFile
0x180004c5d  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x180004c66  call    cs:__imp_WriteFile
0x180004c6c  test    eax, eax
0x180004c6e  jnz     short loc_180004CA1
0x180004c70  call    cs:__imp_GetLastError
0x180004c76  mov     ebx, eax
0x180004c78  test    eax, eax
0x180004c7a  jle     short loc_180004C85
0x180004c7c  movzx   ebx, ax
0x180004c7f  or      ebx, 80070000h
0x180004c85  mov     r8, [rdi+30h]
0x180004c89  mov     r9d, ebx
0x180004c8c  mov     edx, 0C0001774h
0x180004c91  mov     dword ptr [rsp+48h+lpOverlapped], 4
0x180004c99  mov     rcx, rdi
0x180004c9c  call    ?LogW3LogSvcEvent@LOG_WRITER@@AEAAXKPEBGKW4LOG_SVC_EVENT@@@Z; LOG_WRITER::LogW3LogSvcEvent(ulong,ushort const *,ulong,LOG_SVC_EVENT)
0x180004ca1  test    ebp, ebp
0x180004ca3  jz      short loc_180004CB3
0x180004ca5  mov     rax, [rsi+20h]
0x180004ca9  mov     byte ptr [rax], 0
0x180004cac  mov     dword ptr [rsi+30h], 0
0x180004cb3  mov     eax, [rsp+48h+NumberOfBytesWritten]
0x180004cb7  add     [rdi+280h], rax
0x180004cbe  mov     eax, ebx
0x180004cc0  mov     rbx, [rsp+48h+arg_0]
0x180004cc5  add     rsp, 30h
0x180004cc9  pop     rdi
0x180004cca  pop     rsi
0x180004ccb  pop     rbp
0x180004ccc  retn
```
