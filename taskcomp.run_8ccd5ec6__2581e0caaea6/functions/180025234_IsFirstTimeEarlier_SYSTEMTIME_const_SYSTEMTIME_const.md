# IsFirstTimeEarlier(_SYSTEMTIME const *,_SYSTEMTIME const *)

- ea: `0x180025234`
- end: `0x180025294`
- name: `?IsFirstTimeEarlier@@YAHPEBU_SYSTEMTIME@@0@Z`
- size: `96`
- prototype: `int(const struct _SYSTEMTIME *, const struct _SYSTEMTIME *)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180024e04`
- `0x180028a3c`
- `0x180029158`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002527e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002527e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180025254`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180025268`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180025254`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180025268`

## pseudocode

```c
__int64 __fastcall IsFirstTimeEarlier(const struct _SYSTEMTIME *a1, const struct _SYSTEMTIME *a2)
{
  FILETIME FileTime2; // [rsp+40h] [rbp+18h] BYREF
  struct _FILETIME FileTime; // [rsp+48h] [rbp+20h] BYREF

  FileTime = 0;
  FileTime2 = 0;
  SystemTimeToFileTime(a1, &FileTime);
  SystemTimeToFileTime(a2, &FileTime2);
  return (unsigned int)CompareFileTime(&FileTime, &FileTime2) >> 31;
}

```

## disassembly

```asm
0x180025234  push    rbx
0x180025236  sub     rsp, 20h
0x18002523a  mov     rbx, rdx
0x18002523d  mov     qword ptr [rsp+28h+FileTime.dwLowDateTime], 0
0x180025246  lea     rdx, [rsp+28h+FileTime]; lpFileTime
0x18002524b  mov     qword ptr [rsp+28h+FileTime2.dwLowDateTime], 0
0x180025254  call    cs:__imp_SystemTimeToFileTime
0x18002525b  nop     dword ptr [rax+rax+00h]
0x180025260  lea     rdx, [rsp+28h+FileTime2]; lpFileTime
0x180025265  mov     rcx, rbx; lpSystemTime
0x180025268  call    cs:__imp_SystemTimeToFileTime
0x18002526f  nop     dword ptr [rax+rax+00h]
0x180025274  lea     rdx, [rsp+28h+FileTime2]; lpFileTime2
0x180025279  lea     rcx, [rsp+28h+FileTime]; lpFileTime1
0x18002527e  call    cs:__imp_CompareFileTime
0x180025285  nop     dword ptr [rax+rax+00h]
0x18002528a  shr     eax, 1Fh
0x18002528d  add     rsp, 20h
0x180025291  pop     rbx
0x180025292  retn
```
