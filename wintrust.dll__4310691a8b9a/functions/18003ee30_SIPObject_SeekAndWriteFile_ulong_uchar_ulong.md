# SIPObject_::SeekAndWriteFile(ulong,uchar *,ulong)

- ea: `0x18003ee30`
- end: `0x18003eeb2`
- name: `?SeekAndWriteFile@SIPObject_@@IEAAHKPEAEK@Z`
- size: `130`
- prototype: `int(SIPObject_ *__hidden this, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18003e75c`

## callees

- `0x18003ee30`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18003ee69`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18003ee69`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003ee8b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003ee8b`

## pseudocode

```c
_BOOL8 __fastcall SIPObject_::SeekAndWriteFile(HANDLE *this, unsigned int a2, unsigned __int8 *a3, DWORD a4)
{
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp+10h] BYREF

  NumberOfBytesWritten = 0;
  return SetFilePointerEx(this[1], (LARGE_INTEGER)a2, 0, 0)
      && WriteFile(this[1], a3, a4, &NumberOfBytesWritten, 0)
      && NumberOfBytesWritten == a4;
}

```

## disassembly

```asm
0x18003ee30  mov     [rsp+arg_10], rbx
0x18003ee35  mov     [rsp+arg_18], rsi
0x18003ee3a  push    rdi
0x18003ee3b  sub     rsp, 30h
0x18003ee3f  xor     eax, eax
0x18003ee41  mov     dword ptr [rsp+38h+liDistanceToMove], edx
0x18003ee45  mov     dword ptr [rsp+38h+liDistanceToMove+4], eax
0x18003ee49  mov     ebx, r9d
0x18003ee4c  mov     rdx, qword ptr [rsp+38h+liDistanceToMove]; liDistanceToMove
0x18003ee51  mov     rsi, r8
0x18003ee54  mov     rdi, rcx
0x18003ee57  mov     [rsp+38h+NumberOfBytesWritten], 0
0x18003ee5f  mov     rcx, [rcx+8]; hFile
0x18003ee63  xor     r9d, r9d; dwMoveMethod
0x18003ee66  xor     r8d, r8d; lpNewFilePointer
0x18003ee69  call    cs:__imp_SetFilePointerEx
0x18003ee6f  test    eax, eax
0x18003ee71  jz      short loc_18003EEA0
0x18003ee73  mov     rcx, [rdi+8]; hFile
0x18003ee77  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003ee7c  mov     r8d, ebx; nNumberOfBytesToWrite
0x18003ee7f  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18003ee88  mov     rdx, rsi; lpBuffer
0x18003ee8b  call    cs:__imp_WriteFile
0x18003ee91  test    eax, eax
0x18003ee93  jz      short loc_18003EEA0
0x18003ee95  xor     eax, eax
0x18003ee97  cmp     [rsp+38h+NumberOfBytesWritten], ebx
0x18003ee9b  setz    al
0x18003ee9e  jmp     short loc_18003EEA2
0x18003eea0  xor     eax, eax
0x18003eea2  mov     rbx, [rsp+38h+arg_10]
0x18003eea7  mov     rsi, [rsp+38h+arg_18]
0x18003eeac  add     rsp, 30h
0x18003eeb0  pop     rdi
0x18003eeb1  retn
```
