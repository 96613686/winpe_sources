# GetWIMHeaderLock

- ea: `0x1800131c4`
- end: `0x18001329f`
- name: `GetWIMHeaderLock`
- size: `219`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180012ccc`
- `0x1800130c0`

## callees

- `0x1800131c4`
- `0x180060e5a`

## import_xrefs

- `KERNEL32!LockFileEx` at `0x180013229`
- `KERNEL32!LockFileEx` at `0x180013229`
- `KERNEL32!GetLastError` at `0x18001323b`
- `KERNEL32!GetLastError` at `0x18001323b`
- `KERNEL32!CloseHandle` at `0x180013277`
- `KERNEL32!CloseHandle` at `0x180013277`
- `KERNEL32!CreateEventW` at `0x1800131f6`
- `KERNEL32!CreateEventW` at `0x1800131f6`
- `KERNEL32!GetOverlappedResult` at `0x180013261`
- `KERNEL32!GetOverlappedResult` at `0x180013261`

## pseudocode

```c
__int64 __fastcall GetWIMHeaderLock(HANDLE hFile)
{
  unsigned int v2; // ebx
  BOOL OverlappedResult; // edi
  struct _OVERLAPPED Overlapped; // [rsp+30h] [rbp-28h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+68h] [rbp+10h] BYREF

  v2 = 0;
  memset_0(&Overlapped, 0, sizeof(Overlapped));
  Overlapped.hEvent = CreateEventW(0, 0, 0, 0);
  if ( Overlapped.hEvent )
  {
    OverlappedResult = LockFileEx(hFile, 2u, 0, 0xD0u, 0, &Overlapped);
    if ( !OverlappedResult && GetLastError() == 997 )
      OverlappedResult = GetOverlappedResult(hFile, &Overlapped, &NumberOfBytesTransferred, 1);
    CloseHandle(Overlapped.hEvent);
    LOBYTE(v2) = OverlappedResult;
  }
  return v2;
}

```

## disassembly

```asm
0x1800131c4  mov     rax, rsp
0x1800131c7  mov     [rax+8], rbx
0x1800131cb  mov     [rax+18h], rbp
0x1800131cf  mov     [rax+20h], rsi
0x1800131d3  push    rdi
0x1800131d4  sub     rsp, 50h
0x1800131d8  mov     rsi, rcx
0x1800131db  xor     ebx, ebx
0x1800131dd  xor     edx, edx; Val
0x1800131df  lea     rcx, [rax-28h]; void *
0x1800131e3  lea     r8d, [rbx+20h]; Size
0x1800131e7  call    memset_0
0x1800131ec  xor     r9d, r9d; lpName
0x1800131ef  xor     r8d, r8d; bInitialState
0x1800131f2  xor     edx, edx; bManualReset
0x1800131f4  xor     ecx, ecx; lpEventAttributes
0x1800131f6  call    cs:__imp_CreateEventW
0x1800131fd  nop     dword ptr [rax+rax+00h]
0x180013202  mov     [rsp+58h+Overlapped.hEvent], rax
0x180013207  test    rax, rax
0x18001320a  jz      short loc_180013288
0x18001320c  lea     rax, [rsp+58h+Overlapped]
0x180013211  mov     r9d, 0D0h; nNumberOfBytesToLockLow
0x180013217  mov     [rsp+58h+lpOverlapped], rax; lpOverlapped
0x18001321c  lea     edx, [rbx+2]; dwFlags
0x18001321f  xor     r8d, r8d; dwReserved
0x180013222  mov     [rsp+58h+nNumberOfBytesToLockHigh], ebx; nNumberOfBytesToLockHigh
0x180013226  mov     rcx, rsi; hFile
0x180013229  call    cs:__imp_LockFileEx
0x180013230  nop     dword ptr [rax+rax+00h]
0x180013235  mov     edi, eax
0x180013237  test    eax, eax
0x180013239  jnz     short loc_180013272
0x18001323b  call    cs:__imp_GetLastError
0x180013242  nop     dword ptr [rax+rax+00h]
0x180013247  cmp     eax, 3E5h
0x18001324c  jnz     short loc_180013272
0x18001324e  lea     ebp, [rbx+1]
0x180013251  mov     rcx, rsi; hFile
0x180013254  mov     r9d, ebp; bWait
0x180013257  lea     r8, [rsp+58h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18001325c  lea     rdx, [rsp+58h+Overlapped]; lpOverlapped
0x180013261  call    cs:__imp_GetOverlappedResult
0x180013268  nop     dword ptr [rax+rax+00h]
0x18001326d  test    eax, eax
0x18001326f  cmovnz  edi, ebp
0x180013272  mov     rcx, [rsp+58h+Overlapped.hEvent]; hObject
0x180013277  call    cs:__imp_CloseHandle
0x18001327e  nop     dword ptr [rax+rax+00h]
0x180013283  test    edi, edi
0x180013285  setnz   bl
0x180013288  mov     rbp, [rsp+58h+arg_10]
0x18001328d  mov     eax, ebx
0x18001328f  mov     rbx, [rsp+58h+arg_0]
0x180013294  mov     rsi, [rsp+58h+arg_18]
0x180013299  add     rsp, 50h
0x18001329d  pop     rdi
0x18001329e  retn
```
