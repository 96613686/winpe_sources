# TraceCreateClientW

- ea: `0x180006e9c`
- end: `0x180006fbc`
- name: `TraceCreateClientW`
- size: `288`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005450`

## callees

- `0x180004456`
- `0x180006e9c`
- `0x1800096bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180006f7d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180006f7d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006ebf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006ebf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006eae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006f91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006eae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006f91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006f9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006f9f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180006f53`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180006f53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f5d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180006f68`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180006f68`

## pseudocode

```c
__int64 __fastcall TraceCreateClientW(volatile __int64 *a1)
{
  HANDLE ProcessHeap; // rax
  _DWORD *v3; // rax
  __int64 v4; // rbx
  DWORD LastError; // eax
  int v7; // eax
  DWORD v8; // edi
  HANDLE v9; // rax

  ProcessHeap = GetProcessHeap();
  v3 = HeapAlloc(ProcessHeap, 0, 0x440u);
  v4 = (__int64)v3;
  if ( !v3 )
    return 8;
  v3[15] = 60;
  v3[14] = 0;
  *((_QWORD *)v3 + 32) = 0;
  *((_QWORD *)v3 + 33) = 0;
  *((_QWORD *)v3 + 134) = 0;
  *((_QWORD *)v3 + 135) = 0;
  v3[70] = 0x100000;
  memset_0(v3 + 16, 0, 0x40u);
  memset_0((void *)(v4 + 128), 0, 0x80u);
  if ( ExpandEnvironmentStringsW(L"%windir%\\tracing", (LPWSTR)(v4 + 546), 0x104u) )
  {
    v7 = lstrlenW((LPCWSTR)(v4 + 546));
    _o_wcstombs(v4 + 284, v4 + 546, v7 + 1);
    LastError = CreateReadWriteLock((LPCRITICAL_SECTION)v4);
  }
  else
  {
    LastError = GetLastError();
  }
  v8 = LastError;
  if ( LastError )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, (LPVOID)v4);
    v4 = 0;
  }
  _InterlockedExchange64(a1, v4);
  return v8;
}

```

## disassembly

```asm
0x180006e9c  mov     [rsp+arg_0], rbx
0x180006ea1  mov     [rsp+arg_8], rsi
0x180006ea6  push    rdi
0x180006ea7  sub     rsp, 20h
0x180006eab  mov     rsi, rcx
0x180006eae  call    cs:__imp_GetProcessHeap
0x180006eb4  xor     edx, edx; dwFlags
0x180006eb6  mov     r8d, 440h; dwBytes
0x180006ebc  mov     rcx, rax; hHeap
0x180006ebf  call    cs:__imp_HeapAlloc
0x180006ec5  mov     rbx, rax
0x180006ec8  test    rax, rax
0x180006ecb  jnz     short loc_180006ED5
0x180006ecd  lea     eax, [rbx+8]
0x180006ed0  jmp     loc_180006FAC
0x180006ed5  xor     edx, edx; Val
0x180006ed7  mov     dword ptr [rax+3Ch], 3Ch ; '<'
0x180006ede  lea     rcx, [rax+40h]; void *
0x180006ee2  mov     dword ptr [rax+38h], 0
0x180006ee9  mov     qword ptr [rax+100h], 0
0x180006ef4  mov     qword ptr [rax+108h], 0
0x180006eff  lea     r8d, [rdx+40h]; Size
0x180006f03  mov     qword ptr [rax+430h], 0
0x180006f0e  mov     qword ptr [rax+438h], 0
0x180006f19  mov     dword ptr [rax+118h], 100000h
0x180006f23  call    memset_0
0x180006f28  lea     rcx, [rbx+80h]; void *
0x180006f2f  xor     edx, edx; Val
0x180006f31  mov     r8d, 80h; Size
0x180006f37  call    memset_0
0x180006f3c  lea     rdi, [rbx+222h]
0x180006f43  mov     r8d, 104h; nSize
0x180006f49  mov     rdx, rdi; lpDst
0x180006f4c  lea     rcx, aWindirTracing; "%windir%\\tracing"
0x180006f53  call    cs:__imp_ExpandEnvironmentStringsW
0x180006f59  test    eax, eax
0x180006f5b  jnz     short loc_180006F65
0x180006f5d  call    cs:__imp_GetLastError
0x180006f63  jmp     short loc_180006F8B
0x180006f65  mov     rcx, rdi; lpString
0x180006f68  call    cs:__imp_lstrlenW
0x180006f6e  lea     rcx, [rbx+11Ch]
0x180006f75  mov     rdx, rdi
0x180006f78  inc     eax
0x180006f7a  movsxd  r8, eax
0x180006f7d  call    cs:__imp__o_wcstombs
0x180006f83  mov     rcx, rbx; lpCriticalSection
0x180006f86  call    CreateReadWriteLock
0x180006f8b  mov     edi, eax
0x180006f8d  test    eax, eax
0x180006f8f  jz      short loc_180006FA7
0x180006f91  call    cs:__imp_GetProcessHeap
0x180006f97  mov     r8, rbx; lpMem
0x180006f9a  xor     edx, edx; dwFlags
0x180006f9c  mov     rcx, rax; hHeap
0x180006f9f  call    cs:__imp_HeapFree
0x180006fa5  xor     ebx, ebx
0x180006fa7  xchg    rbx, [rsi]
0x180006faa  mov     eax, edi
0x180006fac  mov     rbx, [rsp+28h+arg_0]
0x180006fb1  mov     rsi, [rsp+28h+arg_8]
0x180006fb6  add     rsp, 20h
0x180006fba  pop     rdi
0x180006fbb  retn
```
