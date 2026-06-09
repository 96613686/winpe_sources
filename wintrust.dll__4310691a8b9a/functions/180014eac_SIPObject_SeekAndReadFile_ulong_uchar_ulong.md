# SIPObject_::SeekAndReadFile(ulong,uchar *,ulong)

- ea: `0x180014eac`
- end: `0x180014f2e`
- name: `?SeekAndReadFile@SIPObject_@@IEAAHKPEAEK@Z`
- size: `130`
- prototype: `int(SIPObject_ *__hidden this, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180014f34`
- `0x18003e75c`

## callees

- `0x180014eac`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180014ee5`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180014ee5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180014f07`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180014f07`

## pseudocode

```c
_BOOL8 __fastcall SIPObject_::SeekAndReadFile(HANDLE *this, unsigned int a2, unsigned __int8 *a3, DWORD a4)
{
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp+10h] BYREF

  NumberOfBytesRead = 0;
  return SetFilePointerEx(this[1], (LARGE_INTEGER)a2, 0, 0)
      && ReadFile(this[1], a3, a4, &NumberOfBytesRead, 0)
      && NumberOfBytesRead == a4;
}

```

## disassembly

```asm
0x180014eac  mov     [rsp+arg_10], rbx
0x180014eb1  mov     [rsp+arg_18], rsi
0x180014eb6  push    rdi
0x180014eb7  sub     rsp, 30h
0x180014ebb  xor     eax, eax
0x180014ebd  mov     dword ptr [rsp+38h+liDistanceToMove], edx
0x180014ec1  mov     dword ptr [rsp+38h+liDistanceToMove+4], eax
0x180014ec5  mov     ebx, r9d
0x180014ec8  mov     rdx, qword ptr [rsp+38h+liDistanceToMove]; liDistanceToMove
0x180014ecd  mov     rsi, r8
0x180014ed0  mov     rdi, rcx
0x180014ed3  mov     [rsp+38h+NumberOfBytesRead], 0
0x180014edb  mov     rcx, [rcx+8]; hFile
0x180014edf  xor     r9d, r9d; dwMoveMethod
0x180014ee2  xor     r8d, r8d; lpNewFilePointer
0x180014ee5  call    cs:__imp_SetFilePointerEx
0x180014eeb  test    eax, eax
0x180014eed  jz      short loc_180014F11
0x180014eef  mov     rcx, [rdi+8]; hFile
0x180014ef3  lea     r9, [rsp+38h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180014ef8  mov     r8d, ebx; nNumberOfBytesToRead
0x180014efb  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180014f04  mov     rdx, rsi; lpBuffer
0x180014f07  call    cs:__imp_ReadFile
0x180014f0d  test    eax, eax
0x180014f0f  jnz     short loc_180014F23
0x180014f11  xor     eax, eax
0x180014f13  mov     rbx, [rsp+38h+arg_10]
0x180014f18  mov     rsi, [rsp+38h+arg_18]
0x180014f1d  add     rsp, 30h
0x180014f21  pop     rdi
0x180014f22  retn
0x180014f23  xor     eax, eax
0x180014f25  cmp     [rsp+38h+NumberOfBytesRead], ebx
0x180014f29  setz    al
0x180014f2c  jmp     short loc_180014F13
```
