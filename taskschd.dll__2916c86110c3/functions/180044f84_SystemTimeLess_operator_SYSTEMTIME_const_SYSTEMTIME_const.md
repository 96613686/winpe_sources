# SystemTimeLess::operator()(_SYSTEMTIME const &,_SYSTEMTIME const &)

- ea: `0x180044f84`
- end: `0x180044ff4`
- name: `??RSystemTimeLess@@QEAAHAEBU_SYSTEMTIME@@0@Z`
- size: `112`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800448f0`
- `0x1800449dc`
- `0x180044ac0`
- `0x180044d98`

## callees

- `0x180044f84`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180044fd6`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180044fd6`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180044fae`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180044fbe`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180044fae`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180044fbe`

## pseudocode

```c
_BOOL8 __fastcall SystemTimeLess::operator()(__int64 a1, const SYSTEMTIME *a2, const SYSTEMTIME *a3)
{
  BOOL v4; // ebx
  BOOL v5; // eax
  struct _FILETIME FileTime; // [rsp+30h] [rbp+8h] BYREF
  FILETIME FileTime1; // [rsp+48h] [rbp+20h] BYREF

  FileTime1 = 0;
  FileTime = 0;
  v4 = SystemTimeToFileTime(a2, &FileTime1);
  v5 = SystemTimeToFileTime(a3, &FileTime);
  return v4 && v5 && CompareFileTime(&FileTime1, &FileTime) < 0;
}

```

## disassembly

```asm
0x180044f84  mov     rax, rsp
0x180044f87  mov     [rax+10h], rbx
0x180044f8b  mov     [rax+8], rcx
0x180044f8f  push    rdi
0x180044f90  sub     rsp, 20h
0x180044f94  mov     rcx, rdx; lpSystemTime
0x180044f97  mov     qword ptr [rax+20h], 0
0x180044f9f  lea     rdx, [rax+20h]; lpFileTime
0x180044fa3  mov     qword ptr [rax+8], 0
0x180044fab  mov     rdi, r8
0x180044fae  call    cs:__imp_SystemTimeToFileTime
0x180044fb4  lea     rdx, [rsp+28h+FileTime]; lpFileTime
0x180044fb9  mov     rcx, rdi; lpSystemTime
0x180044fbc  mov     ebx, eax
0x180044fbe  call    cs:__imp_SystemTimeToFileTime
0x180044fc4  test    ebx, ebx
0x180044fc6  jz      short loc_180044FE7
0x180044fc8  test    eax, eax
0x180044fca  jz      short loc_180044FE7
0x180044fcc  lea     rdx, [rsp+28h+FileTime]; lpFileTime2
0x180044fd1  lea     rcx, [rsp+28h+FileTime1]; lpFileTime1
0x180044fd6  call    cs:__imp_CompareFileTime
0x180044fdc  test    eax, eax
0x180044fde  jns     short loc_180044FE7
0x180044fe0  mov     eax, 1
0x180044fe5  jmp     short loc_180044FE9
0x180044fe7  xor     eax, eax
0x180044fe9  mov     rbx, [rsp+28h+arg_8]
0x180044fee  add     rsp, 20h
0x180044ff2  pop     rdi
0x180044ff3  retn
```
