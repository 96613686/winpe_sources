# MgmDllStartup

- ea: `0x180012ce4`
- end: `0x180012d79`
- name: `MgmDllStartup`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007840`

## callees

- `0x180012ce4`
- `0x18001f952`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180012d06`
- `KERNEL32!GetProcessHeap` at `0x180012d06`
- `KERNEL32!InitializeCriticalSection` at `0x180012d2a`
- `KERNEL32!InitializeCriticalSection` at `0x180012d42`
- `KERNEL32!InitializeCriticalSection` at `0x180012d2a`
- `KERNEL32!InitializeCriticalSection` at `0x180012d42`
- `KERNEL32!DeleteCriticalSection` at `0x180012d6c`
- `KERNEL32!DeleteCriticalSection` at `0x180012d6c`

## pseudocode

```c
__int64 MgmDllStartup()
{
  memset_0(&ig, 0, 0x180u);
  dword_18002BA54 = 1;
  hHeap = GetProcessHeap();
  if ( hHeap )
  {
    lpMem = 0;
    InitializeCriticalSection(&CriticalSection);
    dword_18002B998 = 1;
    InitializeCriticalSection(&ig);
    dword_18002B908 = 103;
    return 1;
  }
  else
  {
    if ( dword_18002B998 )
      DeleteCriticalSection(&CriticalSection);
    return 0;
  }
}

```

## disassembly

```asm
0x180012ce4  sub     rsp, 28h
0x180012ce8  xor     edx, edx; Val
0x180012cea  mov     r8d, 180h; Size
0x180012cf0  lea     rcx, ig; void *
0x180012cf7  call    memset_0
0x180012cfc  mov     cs:dword_18002BA54, 1
0x180012d06  call    cs:__imp_GetProcessHeap
0x180012d0c  mov     cs:hHeap, rax
0x180012d13  test    rax, rax
0x180012d16  jz      short loc_180012D5C
0x180012d18  mov     cs:lpMem, 0
0x180012d23  lea     rcx, CriticalSection; lpCriticalSection
0x180012d2a  call    cs:__imp_InitializeCriticalSection
0x180012d30  nop
0x180012d31  mov     cs:dword_18002B998, 1
0x180012d3b  lea     rcx, ig; lpCriticalSection
0x180012d42  call    cs:__imp_InitializeCriticalSection
0x180012d48  nop
0x180012d49  mov     cs:dword_18002B908, 67h ; 'g'
0x180012d53  mov     eax, 1
0x180012d58  jmp     short loc_180012D74
0x180012d5a  jmp     short $+2
0x180012d5c  cmp     cs:dword_18002B998, 0
0x180012d63  jz      short loc_180012D72
0x180012d65  lea     rcx, CriticalSection; lpCriticalSection
0x180012d6c  call    cs:__imp_DeleteCriticalSection
0x180012d72  xor     eax, eax
0x180012d74  add     rsp, 28h
0x180012d78  retn
```
