# JournalReader::_ReadNext(void)

- ea: `0x18000fc74`
- end: `0x18000fd48`
- name: `?_ReadNext@JournalReader@@AEAAJXZ`
- size: `212`
- prototype: `__int64 __fastcall(JournalReader *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002cb0`
- `0x18000f0b0`

## callees

- `0x18000cf80`
- `0x18000fc74`
- `0x1800306c2`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fcfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fcfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd25`
- `api-ms-win-core-file-l2-1-0!ReadDirectoryChangesW` at `0x18000fccb`
- `api-ms-win-core-file-l2-1-0!ReadDirectoryChangesW` at `0x18000fccb`

## pseudocode

```c
signed int __fastcall JournalReader::_ReadNext(JournalReader *this)
{
  DWORD LastError; // eax
  signed int result; // eax
  DWORD BytesReturned; // [rsp+50h] [rbp+8h] BYREF

  BytesReturned = 0;
  memset_0(*((void **)this + 7), 0, 0x22Au);
  if ( ReadDirectoryChangesW(
         *((HANDLE *)this + 6),
         *((LPVOID *)this + 7),
         0x22Au,
         0,
         0x111u,
         &BytesReturned,
         (LPOVERLAPPED)((char *)this + 16),
         0) )
  {
    return 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_880a4eb608c037d792798d7e53d23858_Traceguids, LastError);
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000fc74  push    rbx
0x18000fc76  sub     rsp, 40h
0x18000fc7a  mov     rbx, rcx
0x18000fc7d  mov     [rsp+48h+BytesReturned], 0
0x18000fc85  mov     rcx, [rcx+38h]; void *
0x18000fc89  xor     edx, edx; Val
0x18000fc8b  mov     r8d, 22Ah; Size
0x18000fc91  call    memset_0
0x18000fc96  mov     rdx, [rbx+38h]; lpBuffer
0x18000fc9a  lea     rax, [rbx+10h]
0x18000fc9e  mov     rcx, [rbx+30h]; hDirectory
0x18000fca2  xor     r9d, r9d; bWatchSubtree
0x18000fca5  mov     [rsp+48h+lpCompletionRoutine], 0; lpCompletionRoutine
0x18000fcae  mov     r8d, 22Ah; nBufferLength
0x18000fcb4  mov     [rsp+48h+lpOverlapped], rax; lpOverlapped
0x18000fcb9  lea     rax, [rsp+48h+BytesReturned]
0x18000fcbe  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x18000fcc3  mov     [rsp+48h+dwNotifyFilter], 111h; dwNotifyFilter
0x18000fccb  call    cs:__imp_ReadDirectoryChangesW
0x18000fcd2  nop     dword ptr [rax+rax+00h]
0x18000fcd7  test    eax, eax
0x18000fcd9  jnz     short loc_18000FD3F
0x18000fcdb  mov     rax, cs:WPP_GLOBAL_Control
0x18000fce2  lea     rcx, WPP_GLOBAL_Control
0x18000fce9  cmp     rax, rcx
0x18000fcec  jz      short loc_18000FD25
0x18000fcee  test    byte ptr [rax+1Ch], 2
0x18000fcf2  jz      short loc_18000FD25
0x18000fcf4  cmp     byte ptr [rax+19h], 2
0x18000fcf8  jb      short loc_18000FD25
0x18000fcfa  call    cs:__imp_GetLastError
0x18000fd01  nop     dword ptr [rax+rax+00h]
0x18000fd06  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd0d  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x18000fd14  mov     edx, 18h
0x18000fd19  mov     r9d, eax
0x18000fd1c  mov     rcx, [rcx+10h]
0x18000fd20  call    WPP_SF_d
0x18000fd25  call    cs:__imp_GetLastError
0x18000fd2c  nop     dword ptr [rax+rax+00h]
0x18000fd31  test    eax, eax
0x18000fd33  jle     short loc_18000FD41
0x18000fd35  movzx   eax, ax
0x18000fd38  or      eax, 80070000h
0x18000fd3d  jmp     short loc_18000FD41
0x18000fd3f  xor     eax, eax
0x18000fd41  add     rsp, 40h
0x18000fd45  pop     rbx
0x18000fd46  retn
```
