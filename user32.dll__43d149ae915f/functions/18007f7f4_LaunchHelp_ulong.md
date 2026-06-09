# LaunchHelp(ulong)

- ea: `0x18007f7f4`
- end: `0x18007f974`
- name: `?LaunchHelp@@YAHK@Z`
- size: `384`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800312fc`

## callees

- `0x18004c348`
- `0x18005b990`
- `0x18007f7f4`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `ntdll!NtClose` at `0x18007f933`
- `ntdll!NtClose` at `0x18007f93e`
- `ntdll!NtClose` at `0x18007f933`
- `ntdll!NtClose` at `0x18007f93e`
- `ntdll!swprintf_s` at `0x18007f8b0`
- `ntdll!swprintf_s` at `0x18007f8b0`
- `ntdll!RtlFreeHeap` at `0x18007f950`
- `ntdll!RtlFreeHeap` at `0x18007f950`
- `ntdll!RtlAllocateHeap` at `0x18007f85c`
- `ntdll!RtlAllocateHeap` at `0x18007f85c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18007f913`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18007f913`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18007f83f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18007f873`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18007f83f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18007f873`

## pseudocode

```c
__int64 __fastcall LaunchHelp(unsigned int a1)
{
  __int64 v1; // r15
  unsigned int v2; // edi
  __int64 v3; // rsi
  WCHAR *Heap; // rax
  unsigned __int16 *v5; // rbx
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  wchar_t Buffer[16]; // [rsp+E0h] [rbp-20h] BYREF

  v1 = a1;
  v2 = 0;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v3 = GetSystemWindowsDirectoryW(0, 0) + 1;
  Heap = (WCHAR *)RtlAllocateHeap(pUserHeap, 0, 2 * (v3 + 14));
  v5 = Heap;
  if ( Heap )
  {
    GetSystemWindowsDirectoryW(Heap, v3);
    StringCchCatW(v5, v3 + 14, L"\\winhlp32.exe");
    swprintf_s(Buffer, 0x10u, L"%ws -%wc", L"winhlp32.exe", aXpc[v1]);
    memset_0(&StartupInfo, 0, sizeof(StartupInfo));
    StartupInfo.cb = 104;
    StartupInfo.wShowWindow = 5;
    StartupInfo.dwFlags = 65;
    v2 = CreateProcessW(v5, Buffer, 0, 0, 0, 0x20u, 0, 0, &StartupInfo, &ProcessInformation);
    if ( v2 )
    {
      WaitForInputIdle(ProcessInformation.hProcess, 0x2710u);
      NtClose(ProcessInformation.hProcess);
      NtClose(ProcessInformation.hThread);
    }
    RtlFreeHeap(pUserHeap, 0, v5);
  }
  return v2;
}

```

## disassembly

```asm
0x18007f7f4  push    rbp
0x18007f7f6  push    rbx
0x18007f7f7  push    rsi
0x18007f7f8  push    rdi
0x18007f7f9  push    r14
0x18007f7fb  push    r15
0x18007f7fd  lea     rbp, [rsp-18h]
0x18007f802  sub     rsp, 118h
0x18007f809  mov     rax, cs:__security_cookie
0x18007f810  xor     rax, rsp
0x18007f813  mov     [rbp+40h+var_40], rax
0x18007f817  mov     r15d, ecx
0x18007f81a  xor     edi, edi
0x18007f81c  xor     edx, edx; Val
0x18007f81e  lea     rcx, [rsp+140h+StartupInfo]; void *
0x18007f823  lea     r8d, [rdi+68h]; Size
0x18007f827  call    memset_0
0x18007f82c  xorps   xmm0, xmm0
0x18007f82f  xor     eax, eax
0x18007f831  xor     edx, edx; uSize
0x18007f833  mov     qword ptr [rsp+140h+ProcessInformation.dwProcessId], rax
0x18007f838  xor     ecx, ecx; lpBuffer
0x18007f83a  movups  xmmword ptr [rsp+140h+ProcessInformation.hProcess], xmm0
0x18007f83f  call    cs:__imp_GetSystemWindowsDirectoryW
0x18007f845  mov     rcx, cs:pUserHeap; HeapHandle
0x18007f84c  xor     edx, edx; Flags
0x18007f84e  lea     esi, [rax+1]
0x18007f851  mov     r14d, esi
0x18007f854  add     r14, 0Eh
0x18007f858  lea     r8, [r14+r14]; Size
0x18007f85c  call    cs:__imp_RtlAllocateHeap
0x18007f862  mov     rbx, rax
0x18007f865  test    rax, rax
0x18007f868  jz      loc_18007F956
0x18007f86e  mov     edx, esi; uSize
0x18007f870  mov     rcx, rax; lpBuffer
0x18007f873  call    cs:__imp_GetSystemWindowsDirectoryW
0x18007f879  lea     r8, aWinhlp32Exe; "\\winhlp32.exe"
0x18007f880  mov     rdx, r14; unsigned __int64
0x18007f883  mov     rcx, rbx; unsigned __int16 *
0x18007f886  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18007f88b  lea     rax, aXpc; "xpc"
0x18007f892  movzx   ecx, word ptr [rax+r15*2]
0x18007f897  lea     r9, aWinhlp32Exe+2; "winhlp32.exe"
0x18007f89e  mov     [rsp+140h+bInheritHandles], ecx
0x18007f8a2  lea     r8, aWsWc; "%ws -%wc"
0x18007f8a9  lea     rcx, [rbp+40h+Buffer]; Buffer
0x18007f8ad  lea     edx, [rdi+10h]; BufferCount
0x18007f8b0  call    cs:__imp_swprintf_s
0x18007f8b6  xor     edx, edx; Val
0x18007f8b8  lea     r8d, [rdi+68h]; Size
0x18007f8bc  lea     rcx, [rsp+140h+StartupInfo]; void *
0x18007f8c1  call    memset_0
0x18007f8c6  lea     eax, [rdi+5]
0x18007f8c9  mov     [rsp+140h+StartupInfo.cb], 68h ; 'h'
0x18007f8d1  mov     [rbp+40h+StartupInfo.wShowWindow], ax
0x18007f8d5  lea     rdx, [rbp+40h+Buffer]; lpCommandLine
0x18007f8d9  lea     rax, [rsp+140h+ProcessInformation]
0x18007f8de  mov     [rbp+40h+StartupInfo.dwFlags], 41h ; 'A'
0x18007f8e5  mov     [rsp+140h+lpProcessInformation], rax; lpProcessInformation
0x18007f8ea  xor     r9d, r9d; lpThreadAttributes
0x18007f8ed  lea     rax, [rsp+140h+StartupInfo]
0x18007f8f2  xor     r8d, r8d; lpProcessAttributes
0x18007f8f5  mov     [rsp+140h+lpStartupInfo], rax; lpStartupInfo
0x18007f8fa  mov     rcx, rbx; lpApplicationName
0x18007f8fd  mov     [rsp+140h+lpCurrentDirectory], rdi; lpCurrentDirectory
0x18007f902  mov     [rsp+140h+lpEnvironment], rdi; lpEnvironment
0x18007f907  mov     [rsp+140h+dwCreationFlags], 20h ; ' '; dwCreationFlags
0x18007f90f  mov     [rsp+140h+bInheritHandles], edi; bInheritHandles
0x18007f913  call    cs:__imp_CreateProcessW
0x18007f919  mov     edi, eax
0x18007f91b  test    eax, eax
0x18007f91d  jz      short loc_18007F944
0x18007f91f  mov     rcx, [rsp+140h+ProcessInformation.hProcess]; hProcess
0x18007f924  mov     edx, 2710h; dwMilliseconds
0x18007f929  call    WaitForInputIdle
0x18007f92e  mov     rcx, [rsp+140h+ProcessInformation.hProcess]; Handle
0x18007f933  call    cs:__imp_NtClose
0x18007f939  mov     rcx, [rsp+140h+ProcessInformation.hThread]; Handle
0x18007f93e  call    cs:__imp_NtClose
0x18007f944  mov     rcx, cs:pUserHeap; HeapHandle
0x18007f94b  mov     r8, rbx; P
0x18007f94e  xor     edx, edx; Flags
0x18007f950  call    cs:__imp_RtlFreeHeap
0x18007f956  mov     eax, edi
0x18007f958  mov     rcx, [rbp+40h+var_40]
0x18007f95c  xor     rcx, rsp; StackCookie
0x18007f95f  call    __security_check_cookie
0x18007f964  add     rsp, 118h
0x18007f96b  pop     r15
0x18007f96d  pop     r14
0x18007f96f  pop     rdi
0x18007f970  pop     rsi
0x18007f971  pop     rbx
0x18007f972  pop     rbp
0x18007f973  retn
```
