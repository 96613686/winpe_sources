# JournalReader::_ReadNext(void)

- ea: `0x18000f2dc`
- end: `0x18000f39d`
- name: `?_ReadNext@JournalReader@@AEAAJXZ`
- size: `193`
- prototype: `signed int __fastcall(JournalReader *this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002b90`
- `0x18000e7ac`

## callees

- `0x18000c760`
- `0x18000f2dc`
- `0x18002e572`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f35c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f35c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f381`
- `api-ms-win-core-file-l2-1-0!ReadDirectoryChangesW` at `0x18000f333`
- `api-ms-win-core-file-l2-1-0!ReadDirectoryChangesW` at `0x18000f333`

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
0x18000f2dc  push    rbx
0x18000f2de  sub     rsp, 40h
0x18000f2e2  mov     rbx, rcx
0x18000f2e5  mov     [rsp+48h+BytesReturned], 0
0x18000f2ed  mov     rcx, [rcx+38h]; void *
0x18000f2f1  xor     edx, edx; Val
0x18000f2f3  mov     r8d, 22Ah; Size
0x18000f2f9  call    memset_0
0x18000f2fe  mov     rdx, [rbx+38h]; lpBuffer
0x18000f302  lea     rax, [rbx+10h]
0x18000f306  mov     rcx, [rbx+30h]; hDirectory
0x18000f30a  xor     r9d, r9d; bWatchSubtree
0x18000f30d  mov     [rsp+48h+lpCompletionRoutine], 0; lpCompletionRoutine
0x18000f316  mov     r8d, 22Ah; nBufferLength
0x18000f31c  mov     [rsp+48h+lpOverlapped], rax; lpOverlapped
0x18000f321  lea     rax, [rsp+48h+BytesReturned]
0x18000f326  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x18000f32b  mov     [rsp+48h+dwNotifyFilter], 111h; dwNotifyFilter
0x18000f333  call    cs:__imp_ReadDirectoryChangesW
0x18000f339  test    eax, eax
0x18000f33b  jnz     short loc_18000F395
0x18000f33d  mov     rax, cs:WPP_GLOBAL_Control
0x18000f344  lea     rcx, WPP_GLOBAL_Control
0x18000f34b  cmp     rax, rcx
0x18000f34e  jz      short loc_18000F381
0x18000f350  test    byte ptr [rax+1Ch], 2
0x18000f354  jz      short loc_18000F381
0x18000f356  cmp     byte ptr [rax+19h], 2
0x18000f35a  jb      short loc_18000F381
0x18000f35c  call    cs:__imp_GetLastError
0x18000f362  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f369  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x18000f370  mov     edx, 18h
0x18000f375  mov     r9d, eax
0x18000f378  mov     rcx, [rcx+10h]
0x18000f37c  call    WPP_SF_d
0x18000f381  call    cs:__imp_GetLastError
0x18000f387  test    eax, eax
0x18000f389  jle     short loc_18000F397
0x18000f38b  movzx   eax, ax
0x18000f38e  or      eax, 80070000h
0x18000f393  jmp     short loc_18000F397
0x18000f395  xor     eax, eax
0x18000f397  add     rsp, 40h
0x18000f39b  pop     rbx
0x18000f39c  retn
```
