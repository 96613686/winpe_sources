# IsFirstTimeEarlier(_SYSTEMTIME const *,_SYSTEMTIME const *)

- ea: `0x180023ba0`
- end: `0x180023bed`
- name: `?IsFirstTimeEarlier@@YAHPEBU_SYSTEMTIME@@0@Z`
- size: `77`
- prototype: `int(const struct _SYSTEMTIME *, const struct _SYSTEMTIME *)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180023794`
- `0x180027228`
- `0x180027924`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180023bde`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180023bde`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180023bc0`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180023bce`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180023bc0`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180023bce`

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
0x180023ba0  push    rbx
0x180023ba2  sub     rsp, 20h
0x180023ba6  mov     rbx, rdx
0x180023ba9  mov     qword ptr [rsp+28h+FileTime.dwLowDateTime], 0
0x180023bb2  lea     rdx, [rsp+28h+FileTime]; lpFileTime
0x180023bb7  mov     qword ptr [rsp+28h+FileTime2.dwLowDateTime], 0
0x180023bc0  call    cs:__imp_SystemTimeToFileTime
0x180023bc6  lea     rdx, [rsp+28h+FileTime2]; lpFileTime
0x180023bcb  mov     rcx, rbx; lpSystemTime
0x180023bce  call    cs:__imp_SystemTimeToFileTime
0x180023bd4  lea     rdx, [rsp+28h+FileTime2]; lpFileTime2
0x180023bd9  lea     rcx, [rsp+28h+FileTime]; lpFileTime1
0x180023bde  call    cs:__imp_CompareFileTime
0x180023be4  shr     eax, 1Fh
0x180023be7  add     rsp, 20h
0x180023beb  pop     rbx
0x180023bec  retn
```
