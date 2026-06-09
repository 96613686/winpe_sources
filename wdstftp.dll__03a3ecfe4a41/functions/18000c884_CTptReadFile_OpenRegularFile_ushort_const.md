# CTptReadFile::OpenRegularFile(ushort const *)

- ea: `0x18000c884`
- end: `0x18000c9bc`
- name: `?OpenRegularFile@CTptReadFile@@AEAAKPEBG@Z`
- size: `312`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000c5fc`

## callees

- `0x18000c884`
- `0x18003ce78`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000c89f`
- `KERNEL32!EnterCriticalSection` at `0x18000c89f`
- `KERNEL32!LeaveCriticalSection` at `0x18000c99e`
- `KERNEL32!LeaveCriticalSection` at `0x18000c99e`
- `KERNEL32!GetLastError` at `0x18000c8e8`
- `KERNEL32!GetLastError` at `0x18000c933`
- `KERNEL32!GetLastError` at `0x18000c96f`
- `KERNEL32!GetLastError` at `0x18000c8e8`
- `KERNEL32!GetLastError` at `0x18000c933`
- `KERNEL32!GetLastError` at `0x18000c96f`
- `KERNEL32!CreateFileW` at `0x18000c8d2`
- `KERNEL32!CreateFileW` at `0x18000c8d2`
- `KERNEL32!GetFileSize` at `0x18000c922`
- `KERNEL32!GetFileSize` at `0x18000c922`
- `KERNEL32!BindIoCompletionCallback` at `0x18000c95f`
- `KERNEL32!BindIoCompletionCallback` at `0x18000c95f`

## string_xrefs

- `0x18000c8fc`: `base\eco\wds\transport\lib\tptreadfile.cpp`
- `0x18000c981`: `base\eco\wds\transport\lib\tptreadfile.cpp`

## pseudocode

```c
__int64 __fastcall CTptReadFile::OpenRegularFile(LPCRITICAL_SECTION lpCriticalSection, LPCWSTR lpFileName)
{
  unsigned int v2; // edi
  HANDLE FileW; // rax
  DWORD LastError; // eax
  const char *v7; // rdx
  unsigned int v8; // r9d
  DWORD FileSize; // eax
  HANDLE OwningThread; // rcx
  DWORD v11; // eax
  const char *v12; // rdx
  unsigned int v13; // eax
  DWORD FileSizeHigh; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  FileSizeHigh = 0;
  EnterCriticalSection(lpCriticalSection);
  LODWORD(lpCriticalSection[1].DebugInfo) = 0;
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x48000000u, 0);
  lpCriticalSection[1].OwningThread = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v8 = 468;
    goto LABEL_3;
  }
  FileSize = GetFileSize(FileW, &FileSizeHigh);
  if ( FileSize == -1 )
  {
    LastError = GetLastError();
    v8 = 477;
LABEL_3:
    v2 = ElValidateWin32(LastError, v7, "base\\eco\\wds\\transport\\lib\\tptreadfile.cpp", v8);
    if ( !v2 )
      v2 = 31;
    goto LABEL_11;
  }
  OwningThread = lpCriticalSection[1].OwningThread;
  LODWORD(lpCriticalSection[1].LockSemaphore) = FileSize;
  HIDWORD(lpCriticalSection[1].LockSemaphore) = FileSizeHigh;
  if ( !BindIoCompletionCallback(OwningThread, CTptReadFile::_IOCompletionCallback, 0) )
  {
    v11 = GetLastError();
    v13 = ElValidateWin32(v11, v12, "base\\eco\\wds\\transport\\lib\\tptreadfile.cpp", 0x1EAu);
    if ( !v13 )
      v13 = 31;
    v2 = v13;
  }
LABEL_11:
  LeaveCriticalSection(lpCriticalSection);
  return v2;
}

```

## disassembly

```asm
0x18000c884  mov     [rsp+arg_8], rbx
0x18000c889  mov     [rsp+arg_10], rsi
0x18000c88e  push    rdi
0x18000c88f  sub     rsp, 40h
0x18000c893  xor     edi, edi
0x18000c895  mov     rbx, rdx
0x18000c898  and     [rsp+48h+FileSizeHigh], edi
0x18000c89c  mov     rsi, rcx
0x18000c89f  call    cs:__imp_EnterCriticalSection
0x18000c8a6  nop     dword ptr [rax+rax+00h]
0x18000c8ab  and     [rsp+48h+var_18], rdi
0x18000c8b0  lea     r8d, [rdi+1]; dwShareMode
0x18000c8b4  and     [rsi+28h], edi
0x18000c8b7  xor     r9d, r9d; lpSecurityAttributes
0x18000c8ba  mov     [rsp+48h+dwFlagsAndAttributes], 48000000h; dwFlagsAndAttributes
0x18000c8c2  mov     edx, 80000000h; dwDesiredAccess
0x18000c8c7  mov     rcx, rbx; lpFileName
0x18000c8ca  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18000c8d2  call    cs:__imp_CreateFileW
0x18000c8d9  nop     dword ptr [rax+rax+00h]
0x18000c8de  mov     [rsi+38h], rax
0x18000c8e2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c8e6  jnz     short loc_18000C91A
0x18000c8e8  call    cs:__imp_GetLastError
0x18000c8ef  nop     dword ptr [rax+rax+00h]
0x18000c8f4  mov     r9d, 1D4h; unsigned int
0x18000c8fa  mov     ecx, eax; unsigned int
0x18000c8fc  lea     r8, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\lib\\tptread"...
0x18000c903  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000c908  mov     edi, eax
0x18000c90a  test    eax, eax
0x18000c90c  jnz     loc_18000C99B
0x18000c912  lea     edi, [rax+1Fh]
0x18000c915  jmp     loc_18000C99B
0x18000c91a  lea     rdx, [rsp+48h+FileSizeHigh]; lpFileSizeHigh
0x18000c91f  mov     rcx, rax; hFile
0x18000c922  call    cs:__imp_GetFileSize
0x18000c929  nop     dword ptr [rax+rax+00h]
0x18000c92e  cmp     eax, 0FFFFFFFFh
0x18000c931  jnz     short loc_18000C947
0x18000c933  call    cs:__imp_GetLastError
0x18000c93a  nop     dword ptr [rax+rax+00h]
0x18000c93f  mov     r9d, 1DDh
0x18000c945  jmp     short loc_18000C8FA
0x18000c947  mov     rcx, [rsi+38h]; FileHandle
0x18000c94b  lea     rdx, ?_IOCompletionCallback@CTptReadFile@@SAXKKPEAU_OVERLAPPED@@@Z; Function
0x18000c952  mov     [rsi+40h], eax
0x18000c955  xor     r8d, r8d; Flags
0x18000c958  mov     eax, [rsp+48h+FileSizeHigh]
0x18000c95c  mov     [rsi+44h], eax
0x18000c95f  call    cs:__imp_BindIoCompletionCallback
0x18000c966  nop     dword ptr [rax+rax+00h]
0x18000c96b  test    eax, eax
0x18000c96d  jnz     short loc_18000C99B
0x18000c96f  call    cs:__imp_GetLastError
0x18000c976  nop     dword ptr [rax+rax+00h]
0x18000c97b  mov     r9d, 1EAh; unsigned int
0x18000c981  lea     r8, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\lib\\tptread"...
0x18000c988  mov     ecx, eax; unsigned int
0x18000c98a  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000c98f  mov     edi, 1Fh
0x18000c994  test    eax, eax
0x18000c996  cmovz   eax, edi
0x18000c999  mov     edi, eax
0x18000c99b  mov     rcx, rsi; lpCriticalSection
0x18000c99e  call    cs:__imp_LeaveCriticalSection
0x18000c9a5  nop     dword ptr [rax+rax+00h]
0x18000c9aa  mov     rbx, [rsp+48h+arg_8]
0x18000c9af  mov     eax, edi
0x18000c9b1  mov     rsi, [rsp+48h+arg_10]
0x18000c9b6  add     rsp, 40h
0x18000c9ba  pop     rdi
0x18000c9bb  retn
```
