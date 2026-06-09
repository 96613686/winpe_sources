# SIPObjectCAB_::WriteHeader(void)

- ea: `0x18003e8a4`
- end: `0x18003e9d1`
- name: `?WriteHeader@SIPObjectCAB_@@AEAAHXZ`
- size: `301`
- prototype: `__int64 __fastcall(SIPObjectCAB_ *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18003e430`
- `0x18003e548`
- `0x18003e9d8`

## callees

- `0x18003e8a4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003e8c8`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003e8c8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003e8ed`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003e925`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003e96e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003e9a2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003e8ed`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003e925`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003e96e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003e9a2`

## pseudocode

```c
_BOOL8 __fastcall SIPObjectCAB_::WriteHeader(SIPObjectCAB_ *this)
{
  void *v2; // rcx
  unsigned __int16 *v3; // rdi
  __int64 v4; // rcx
  const void *v5; // rdx
  _BOOL8 result; // rax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp+8h] BYREF

  v2 = (void *)*((_QWORD *)this + 1);
  NumberOfBytesWritten = 0;
  result = 0;
  if ( SetFilePointer(v2, 0, 0, 0) != -1 )
  {
    if ( WriteFile(*((HANDLE *)this + 1), (char *)this + 80, 0x24u, &NumberOfBytesWritten, 0) )
    {
      if ( NumberOfBytesWritten == 36 )
      {
        if ( !*((_WORD *)this + 60)
          || (v3 = (unsigned __int16 *)((char *)this + 116),
              WriteFile(*((HANDLE *)this + 1), (char *)this + 116, 4u, &NumberOfBytesWritten, 0))
          && NumberOfBytesWritten == 4
          && ((v4 = *((_QWORD *)this + 16)) == 0
           || (*(_WORD *)(v4 + 2) = *((_WORD *)this + 75),
               WriteFile(*((HANDLE *)this + 1), *((LPCVOID *)this + 16), *v3, &NumberOfBytesWritten, 0))
           && NumberOfBytesWritten == *v3) )
        {
          v5 = (const void *)*((_QWORD *)this + 17);
          if ( !v5
            || WriteFile(*((HANDLE *)this + 1), v5, *((_DWORD *)this + 36), &NumberOfBytesWritten, 0)
            && NumberOfBytesWritten == *((_DWORD *)this + 36) )
          {
            return 1;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003e8a4  mov     [rsp+arg_8], rbx
0x18003e8a9  mov     [rsp+arg_10], rsi
0x18003e8ae  push    rdi
0x18003e8af  sub     rsp, 30h
0x18003e8b3  mov     rbx, rcx
0x18003e8b6  xor     esi, esi
0x18003e8b8  mov     rcx, [rcx+8]; hFile
0x18003e8bc  xor     r9d, r9d; dwMoveMethod
0x18003e8bf  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003e8c2  mov     [rsp+38h+NumberOfBytesWritten], esi
0x18003e8c6  xor     edx, edx; lDistanceToMove
0x18003e8c8  call    cs:__imp_SetFilePointer
0x18003e8ce  cmp     eax, 0FFFFFFFFh
0x18003e8d1  jz      loc_18003E9BF
0x18003e8d7  mov     rcx, [rbx+8]; hFile
0x18003e8db  lea     rdx, [rbx+50h]; lpBuffer
0x18003e8df  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003e8e4  mov     [rsp+38h+lpOverlapped], rsi; lpOverlapped
0x18003e8e9  lea     r8d, [rsi+24h]; nNumberOfBytesToWrite
0x18003e8ed  call    cs:__imp_WriteFile
0x18003e8f3  test    eax, eax
0x18003e8f5  jz      loc_18003E9BF
0x18003e8fb  cmp     [rsp+38h+NumberOfBytesWritten], 24h ; '$'
0x18003e900  jnz     loc_18003E9BF
0x18003e906  cmp     [rbx+78h], si
0x18003e90a  jz      short loc_18003E981
0x18003e90c  mov     rcx, [rbx+8]; hFile
0x18003e910  lea     rdi, [rbx+74h]
0x18003e914  mov     rdx, rdi; lpBuffer
0x18003e917  mov     [rsp+38h+lpOverlapped], rsi; lpOverlapped
0x18003e91c  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003e921  lea     r8d, [rsi+4]; nNumberOfBytesToWrite
0x18003e925  call    cs:__imp_WriteFile
0x18003e92b  test    eax, eax
0x18003e92d  jz      loc_18003E9BF
0x18003e933  cmp     [rsp+38h+NumberOfBytesWritten], 4
0x18003e938  jnz     loc_18003E9BF
0x18003e93e  mov     rcx, [rbx+80h]
0x18003e945  test    rcx, rcx
0x18003e948  jz      short loc_18003E981
0x18003e94a  movzx   eax, word ptr [rbx+96h]
0x18003e951  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003e956  mov     [rcx+2], ax
0x18003e95a  movzx   r8d, word ptr [rdi]; nNumberOfBytesToWrite
0x18003e95e  mov     rdx, [rbx+80h]; lpBuffer
0x18003e965  mov     rcx, [rbx+8]; hFile
0x18003e969  mov     [rsp+38h+lpOverlapped], rsi; lpOverlapped
0x18003e96e  call    cs:__imp_WriteFile
0x18003e974  test    eax, eax
0x18003e976  jz      short loc_18003E9BF
0x18003e978  movzx   eax, word ptr [rdi]
0x18003e97b  cmp     [rsp+38h+NumberOfBytesWritten], eax
0x18003e97f  jnz     short loc_18003E9BF
0x18003e981  mov     rdx, [rbx+88h]; lpBuffer
0x18003e988  test    rdx, rdx
0x18003e98b  jz      short loc_18003E9B8
0x18003e98d  mov     r8d, [rbx+90h]; nNumberOfBytesToWrite
0x18003e994  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003e999  mov     rcx, [rbx+8]; hFile
0x18003e99d  mov     [rsp+38h+lpOverlapped], rsi; lpOverlapped
0x18003e9a2  call    cs:__imp_WriteFile
0x18003e9a8  test    eax, eax
0x18003e9aa  jz      short loc_18003E9BF
0x18003e9ac  mov     eax, [rbx+90h]
0x18003e9b2  cmp     [rsp+38h+NumberOfBytesWritten], eax
0x18003e9b6  jnz     short loc_18003E9BF
0x18003e9b8  mov     eax, 1
0x18003e9bd  jmp     short loc_18003E9C1
0x18003e9bf  xor     eax, eax
0x18003e9c1  mov     rbx, [rsp+38h+arg_8]
0x18003e9c6  mov     rsi, [rsp+38h+arg_10]
0x18003e9cb  add     rsp, 30h
0x18003e9cf  pop     rdi
0x18003e9d0  retn
```
