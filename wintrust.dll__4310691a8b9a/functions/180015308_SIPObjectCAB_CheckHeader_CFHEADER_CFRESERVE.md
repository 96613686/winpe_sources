# SIPObjectCAB_::CheckHeader(CFHEADER *,CFRESERVE *)

- ea: `0x180015308`
- end: `0x18001543c`
- name: `?CheckHeader@SIPObjectCAB_@@AEAAHPEAUCFHEADER@@PEAUCFRESERVE@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(HANDLE *this, struct CFHEADER *lpBuffer, struct CFRESERVE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800151a8`

## callees

- `0x180014f98`
- `0x180015308`
- `0x180015610`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18001538f`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18001538f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180015334`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180015334`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001535e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800153c5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001535e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800153c5`

## pseudocode

```c
__int64 __fastcall SIPObjectCAB_::CheckHeader(HANDLE *this, struct CFHEADER *lpBuffer, struct CFRESERVE *a3)
{
  HANDLE v6; // rcx
  unsigned __int64 i; // rdi
  unsigned __int64 j; // rbx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp+8h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+58h] [rbp+20h] BYREF

  NumberOfBytesRead = 0;
  if ( SetFilePointer(this[1], 0, 0, 0) == -1 )
    return 0;
  if ( !ReadFile(this[1], lpBuffer, 0x24u, &NumberOfBytesRead, 0) )
    return 0;
  if ( NumberOfBytesRead != 36 )
    return 0;
  if ( *((int *)lpBuffer + 2) < 0 )
    return 0;
  v6 = this[1];
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(v6, &FileSize)
    || *((int *)lpBuffer + 2) > FileSize.QuadPart
    || (*((_BYTE *)lpBuffer + 30) & 4) != 0
    && (!ReadFile(this[1], a3, 4u, &NumberOfBytesRead, 0)
     || NumberOfBytesRead != 4
     || !(unsigned int)SIPObjectCAB_::SetFilePointerRelative((SIPObjectCAB_ *)this, *(unsigned __int16 *)a3)) )
  {
    return 0;
  }
  if ( (*((_BYTE *)lpBuffer + 30) & 1) != 0 )
  {
    for ( i = 0; i < 2; ++i )
    {
      if ( !(unsigned int)SIPObjectCAB_::SkipStringInFile((SIPObjectCAB_ *)this) )
        return 0;
    }
  }
  if ( (*((_BYTE *)lpBuffer + 30) & 2) != 0 )
  {
    for ( j = 0; j < 2; ++j )
    {
      if ( !(unsigned int)SIPObjectCAB_::SkipStringInFile((SIPObjectCAB_ *)this) )
        return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180015308  mov     [rsp+arg_8], rbx
0x18001530d  mov     [rsp+arg_10], rsi
0x180015312  push    rdi
0x180015313  sub     rsp, 30h
0x180015317  mov     rdi, r8
0x18001531a  mov     [rsp+38h+NumberOfBytesRead], 0
0x180015322  mov     rbx, rdx
0x180015325  mov     rsi, rcx
0x180015328  mov     rcx, [rcx+8]; hFile
0x18001532c  xor     r8d, r8d; lpDistanceToMoveHigh
0x18001532f  xor     edx, edx; lDistanceToMove
0x180015331  xor     r9d, r9d; dwMoveMethod
0x180015334  call    cs:__imp_SetFilePointer
0x18001533a  cmp     eax, 0FFFFFFFFh
0x18001533d  jz      loc_1800153F8
0x180015343  mov     rcx, [rsi+8]; hFile
0x180015347  lea     r9, [rsp+38h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001534c  mov     r8d, 24h ; '$'; nNumberOfBytesToRead
0x180015352  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18001535b  mov     rdx, rbx; lpBuffer
0x18001535e  call    cs:__imp_ReadFile
0x180015364  test    eax, eax
0x180015366  jz      loc_1800153F8
0x18001536c  cmp     [rsp+38h+NumberOfBytesRead], 24h ; '$'
0x180015371  jnz     loc_1800153F8
0x180015377  cmp     dword ptr [rbx+8], 0
0x18001537b  jl      short loc_1800153F8
0x18001537d  mov     rcx, [rsi+8]; hFile
0x180015381  lea     rdx, [rsp+38h+FileSize]; lpFileSize
0x180015386  mov     qword ptr [rsp+38h+FileSize], 0
0x18001538f  call    cs:__imp_GetFileSizeEx
0x180015395  test    eax, eax
0x180015397  jz      short loc_1800153F8
0x180015399  movsxd  rax, dword ptr [rbx+8]
0x18001539d  cmp     rax, qword ptr [rsp+38h+FileSize]
0x1800153a2  jg      short loc_1800153F8
0x1800153a4  test    byte ptr [rbx+1Eh], 4
0x1800153a8  jz      short loc_1800153E5
0x1800153aa  mov     rcx, [rsi+8]; hFile
0x1800153ae  lea     r9, [rsp+38h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800153b3  mov     r8d, 4; nNumberOfBytesToRead
0x1800153b9  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x1800153c2  mov     rdx, rdi; lpBuffer
0x1800153c5  call    cs:__imp_ReadFile
0x1800153cb  test    eax, eax
0x1800153cd  jz      short loc_1800153F8
0x1800153cf  cmp     [rsp+38h+NumberOfBytesRead], 4
0x1800153d4  jnz     short loc_1800153F8
0x1800153d6  movzx   edx, word ptr [rdi]; int
0x1800153d9  mov     rcx, rsi; this
0x1800153dc  call    ?SetFilePointerRelative@SIPObjectCAB_@@AEAAHJ@Z; SIPObjectCAB_::SetFilePointerRelative(long)
0x1800153e1  test    eax, eax
0x1800153e3  jz      short loc_1800153F8
0x1800153e5  test    byte ptr [rbx+1Eh], 1
0x1800153e9  jnz     short loc_18001540A
0x1800153eb  test    byte ptr [rbx+1Eh], 2
0x1800153ef  jnz     short loc_180015423
0x1800153f1  mov     eax, 1
0x1800153f6  jmp     short loc_1800153FA
0x1800153f8  xor     eax, eax
0x1800153fa  mov     rbx, [rsp+38h+arg_8]
0x1800153ff  mov     rsi, [rsp+38h+arg_10]
0x180015404  add     rsp, 30h
0x180015408  pop     rdi
0x180015409  retn
0x18001540a  xor     edi, edi
0x18001540c  cmp     rdi, 2
0x180015410  jnb     short loc_1800153EB
0x180015412  mov     rcx, rsi; this
0x180015415  call    ?SkipStringInFile@SIPObjectCAB_@@AEAAHXZ; SIPObjectCAB_::SkipStringInFile(void)
0x18001541a  test    eax, eax
0x18001541c  jz      short loc_1800153F8
0x18001541e  inc     rdi
0x180015421  jmp     short loc_18001540C
0x180015423  xor     ebx, ebx
0x180015425  cmp     rbx, 2
0x180015429  jnb     short loc_1800153F1
0x18001542b  mov     rcx, rsi; this
0x18001542e  call    ?SkipStringInFile@SIPObjectCAB_@@AEAAHXZ; SIPObjectCAB_::SkipStringInFile(void)
0x180015433  test    eax, eax
0x180015435  jz      short loc_1800153F8
0x180015437  inc     rbx
0x18001543a  jmp     short loc_180015425
```
