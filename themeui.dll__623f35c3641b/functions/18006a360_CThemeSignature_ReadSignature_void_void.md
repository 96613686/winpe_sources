# CThemeSignature::ReadSignature(void *,void *)

- ea: `0x18006a360`
- end: `0x18006a4c0`
- name: `?ReadSignature@CThemeSignature@@IEAAJPEAX0@Z`
- size: `352`
- prototype: `int(CThemeSignature *__hidden this, void *, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18006a4c8`

## callees

- `0x180030f64`
- `0x1800358c0`
- `0x18006a360`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a3d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a44c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a492`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a3d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a44c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a492`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18006a403`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18006a471`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18006a403`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18006a471`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18006a392`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18006a392`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18006a3c9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18006a441`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18006a3c9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18006a441`

## pseudocode

```c
int __fastcall CThemeSignature::ReadSignature(CThemeSignature *this, void *a2, void *a3)
{
  int result; // eax
  bool v6; // cc
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-30h] BYREF
  DWORD FileSizeHigh[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v9; // [rsp+40h] [rbp-20h] BYREF
  __int128 Buffer; // [rsp+48h] [rbp-18h] BYREF

  FileSizeHigh[1] = 0;
  FileSizeHigh[0] = GetFileSize(a2, &FileSizeHigh[1]);
  if ( FileSizeHigh[0] == -1 )
    return ResultFromKnownLastError();
  v9 = -16;
  Buffer = 0;
  if ( SetFilePointer(a2, -16, (PLONG)&v9 + 1, 2u) == -1 )
  {
    result = GetLastError();
    v6 = result <= 0;
    if ( result )
      goto LABEL_15;
  }
  NumberOfBytesRead = 0;
  if ( !ReadFile(a2, &Buffer, 0x10u, &NumberOfBytesRead, 0) )
    goto LABEL_14;
  if ( NumberOfBytesRead != 16 || (_DWORD)Buffer != -2073484250 || *(_QWORD *)FileSizeHigh != *((_QWORD *)&Buffer + 1) )
    return -2147467259;
  v9 = -16 - DWORD1(Buffer);
  if ( SetFilePointer(a2, -16 - DWORD1(Buffer), (PLONG)&v9 + 1, 2u) != -1
    || (result = GetLastError(), v6 = result <= 0, !result) )
  {
    if ( ReadFile(a2, a3, 0x80u, &NumberOfBytesRead, 0) )
      return NumberOfBytesRead != 128 ? 0x80004005 : 0;
LABEL_14:
    result = GetLastError();
    v6 = result <= 0;
  }
LABEL_15:
  if ( !v6 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18006a360  mov     [rsp-18h+arg_0], rbx
0x18006a365  push    rbp
0x18006a366  push    rsi
0x18006a367  push    rdi
0x18006a368  mov     rbp, rsp
0x18006a36b  sub     rsp, 60h
0x18006a36f  mov     rax, cs:__security_cookie
0x18006a376  xor     rax, rsp
0x18006a379  mov     [rbp+var_8], rax
0x18006a37d  mov     rbx, rdx
0x18006a380  mov     qword ptr [rbp+FileSizeHigh], 0
0x18006a388  mov     rcx, rbx; hFile
0x18006a38b  lea     rdx, [rbp+FileSizeHigh+4]; lpFileSizeHigh
0x18006a38f  mov     rsi, r8
0x18006a392  call    cs:__imp_GetFileSize
0x18006a398  mov     [rbp+FileSizeHigh], eax
0x18006a39b  cmp     eax, 0FFFFFFFFh
0x18006a39e  jnz     short loc_18006A3AA
0x18006a3a0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006a3a5  jmp     loc_18006A4A4
0x18006a3aa  mov     rdi, 0FFFFFFFFFFFFFFF0h
0x18006a3b1  lea     r8, [rbp+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x18006a3b5  xorps   xmm0, xmm0
0x18006a3b8  mov     [rbp-20h], rdi
0x18006a3bc  mov     edx, edi; lDistanceToMove
0x18006a3be  mov     rcx, rbx; hFile
0x18006a3c1  movups  [rbp+Buffer], xmm0
0x18006a3c5  lea     r9d, [rdi+12h]; dwMoveMethod
0x18006a3c9  call    cs:__imp_SetFilePointer
0x18006a3cf  cmp     eax, 0FFFFFFFFh
0x18006a3d2  jnz     short loc_18006A3E2
0x18006a3d4  call    cs:__imp_GetLastError
0x18006a3da  test    eax, eax
0x18006a3dc  jnz     loc_18006A49A
0x18006a3e2  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18006a3e6  mov     [rbp+NumberOfBytesRead], 0
0x18006a3ed  mov     r8d, 10h; nNumberOfBytesToRead
0x18006a3f3  mov     [rsp+60h+lpOverlapped], 0; lpOverlapped
0x18006a3fc  lea     rdx, [rbp+Buffer]; lpBuffer
0x18006a400  mov     rcx, rbx; hFile
0x18006a403  call    cs:__imp_ReadFile
0x18006a409  test    eax, eax
0x18006a40b  jz      loc_18006A492
0x18006a411  cmp     [rbp+NumberOfBytesRead], 10h
0x18006a415  jnz     short loc_18006A48B
0x18006a417  cmp     dword ptr [rbp+Buffer], 84692426h
0x18006a41e  jnz     short loc_18006A48B
0x18006a420  mov     rax, qword ptr [rbp+Buffer+8]
0x18006a424  cmp     qword ptr [rbp+FileSizeHigh], rax
0x18006a428  jnz     short loc_18006A48B
0x18006a42a  sub     edi, dword ptr [rbp+Buffer+4]
0x18006a42d  lea     r8, [rbp+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x18006a431  movsxd  rdx, edi; lDistanceToMove
0x18006a434  mov     r9d, 2; dwMoveMethod
0x18006a43a  mov     rcx, rbx; hFile
0x18006a43d  mov     [rbp-20h], rdx
0x18006a441  call    cs:__imp_SetFilePointer
0x18006a447  cmp     eax, 0FFFFFFFFh
0x18006a44a  jnz     short loc_18006A456
0x18006a44c  call    cs:__imp_GetLastError
0x18006a452  test    eax, eax
0x18006a454  jnz     short loc_18006A49A
0x18006a456  mov     edi, 80h
0x18006a45b  mov     [rsp+60h+lpOverlapped], 0; lpOverlapped
0x18006a464  mov     r8d, edi; nNumberOfBytesToRead
0x18006a467  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18006a46b  mov     rdx, rsi; lpBuffer
0x18006a46e  mov     rcx, rbx; hFile
0x18006a471  call    cs:__imp_ReadFile
0x18006a477  test    eax, eax
0x18006a479  jz      short loc_18006A492
0x18006a47b  mov     eax, [rbp+NumberOfBytesRead]
0x18006a47e  sub     eax, edi
0x18006a480  neg     eax
0x18006a482  sbb     eax, eax
0x18006a484  and     eax, 80004005h
0x18006a489  jmp     short loc_18006A4A4
0x18006a48b  mov     eax, 80004005h
0x18006a490  jmp     short loc_18006A4A4
0x18006a492  call    cs:__imp_GetLastError
0x18006a498  test    eax, eax
0x18006a49a  jle     short loc_18006A4A4
0x18006a49c  movzx   eax, ax
0x18006a49f  or      eax, 80070000h
0x18006a4a4  mov     rcx, [rbp+var_8]
0x18006a4a8  xor     rcx, rsp; StackCookie
0x18006a4ab  call    __security_check_cookie
0x18006a4b0  mov     rbx, [rsp+60h+arg_0]
0x18006a4b8  add     rsp, 60h
0x18006a4bc  pop     rdi
0x18006a4bd  pop     rsi
0x18006a4be  pop     rbp
0x18006a4bf  retn
```
