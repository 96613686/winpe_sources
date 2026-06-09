# SystemTimeLess::operator()(_SYSTEMTIME const &,_SYSTEMTIME const &)

- ea: `0x1800486b0`
- end: `0x180048733`
- name: `??RSystemTimeLess@@QEAAHAEBU_SYSTEMTIME@@0@Z`
- size: `131`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180047fd0`
- `0x1800480bc`
- `0x1800481a0`
- `0x180048424`

## callees

- `0x1800486b0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18004870e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18004870e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800486da`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800486f0`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800486da`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800486f0`

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
0x1800486b0  mov     rax, rsp
0x1800486b3  mov     [rax+10h], rbx
0x1800486b7  mov     [rax+8], rcx
0x1800486bb  push    rdi
0x1800486bc  sub     rsp, 20h
0x1800486c0  mov     rcx, rdx; lpSystemTime
0x1800486c3  mov     qword ptr [rax+20h], 0
0x1800486cb  lea     rdx, [rax+20h]; lpFileTime
0x1800486cf  mov     qword ptr [rax+8], 0
0x1800486d7  mov     rdi, r8
0x1800486da  call    cs:__imp_SystemTimeToFileTime
0x1800486e1  nop     dword ptr [rax+rax+00h]
0x1800486e6  lea     rdx, [rsp+28h+FileTime]; lpFileTime
0x1800486eb  mov     rcx, rdi; lpSystemTime
0x1800486ee  mov     ebx, eax
0x1800486f0  call    cs:__imp_SystemTimeToFileTime
0x1800486f7  nop     dword ptr [rax+rax+00h]
0x1800486fc  test    ebx, ebx
0x1800486fe  jz      short loc_180048725
0x180048700  test    eax, eax
0x180048702  jz      short loc_180048725
0x180048704  lea     rdx, [rsp+28h+FileTime]; lpFileTime2
0x180048709  lea     rcx, [rsp+28h+FileTime1]; lpFileTime1
0x18004870e  call    cs:__imp_CompareFileTime
0x180048715  nop     dword ptr [rax+rax+00h]
0x18004871a  test    eax, eax
0x18004871c  jns     short loc_180048725
0x18004871e  mov     eax, 1
0x180048723  jmp     short loc_180048727
0x180048725  xor     eax, eax
0x180048727  mov     rbx, [rsp+28h+arg_8]
0x18004872c  add     rsp, 20h
0x180048730  pop     rdi
0x180048731  retn
```
