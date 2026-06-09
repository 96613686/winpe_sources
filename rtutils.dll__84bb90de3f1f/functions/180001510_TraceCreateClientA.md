# TraceCreateClientA

- ea: `0x180001510`
- end: `0x180001638`
- name: `TraceCreateClientA`
- size: `296`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001100`

## callees

- `0x180001510`
- `0x180004456`
- `0x1800096bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x1800015f3`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x1800015f3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000152e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000152e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000151d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001607`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000151d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001607`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001615`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001615`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x1800015c1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x1800015c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800015cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800015cb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800015da`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800015da`

## pseudocode

```c
__int64 __fastcall TraceCreateClientA(volatile __int64 *a1)
{
  HANDLE ProcessHeap; // rax
  _DWORD *v3; // rax
  __int64 v4; // rbx
  DWORD LastError; // eax
  int v7; // eax
  DWORD v8; // esi
  HANDLE v9; // rax

  ProcessHeap = GetProcessHeap();
  v3 = HeapAlloc(ProcessHeap, 0, 0x440u);
  v4 = (__int64)v3;
  if ( !v3 )
    return 8;
  v3[14] = 0;
  *((_QWORD *)v3 + 32) = 0;
  *((_QWORD *)v3 + 33) = 0;
  *((_QWORD *)v3 + 134) = 0;
  *((_QWORD *)v3 + 135) = 0;
  v3[15] = 60;
  v3[70] = 0x100000;
  memset_0(v3 + 16, 0, 0x40u);
  memset_0((void *)(v4 + 128), 0, 0x80u);
  if ( ExpandEnvironmentStringsA("%windir%\\tracing", (LPSTR)(v4 + 284), 0x104u) )
  {
    v7 = lstrlenA((LPCSTR)(v4 + 284));
    _o_mbstowcs(v4 + 546, v4 + 284, v7 + 1);
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
0x180001510  mov     [rsp+arg_10], rbx
0x180001515  push    rdi
0x180001516  sub     rsp, 20h
0x18000151a  mov     rdi, rcx
0x18000151d  call    cs:__imp_GetProcessHeap
0x180001523  xor     edx, edx; dwFlags
0x180001525  mov     r8d, 440h; dwBytes
0x18000152b  mov     rcx, rax; hHeap
0x18000152e  call    cs:__imp_HeapAlloc
0x180001534  mov     rbx, rax
0x180001537  test    rax, rax
0x18000153a  jnz     short loc_18000154C
0x18000153c  mov     eax, 8
0x180001541  mov     rbx, [rsp+28h+arg_10]
0x180001546  add     rsp, 20h
0x18000154a  pop     rdi
0x18000154b  retn
0x18000154c  mov     [rsp+28h+arg_0], rbp
0x180001551  lea     rcx, [rax+40h]; void *
0x180001555  xor     ebp, ebp
0x180001557  mov     [rsp+28h+arg_8], rsi
0x18000155c  xor     edx, edx; Val
0x18000155e  mov     [rax+38h], ebp
0x180001561  mov     r8d, 40h ; '@'; Size
0x180001567  mov     [rax+100h], rbp
0x18000156e  mov     [rax+108h], rbp
0x180001575  mov     [rax+430h], rbp
0x18000157c  mov     [rax+438h], rbp
0x180001583  mov     dword ptr [rax+3Ch], 3Ch ; '<'
0x18000158a  mov     dword ptr [rax+118h], 100000h
0x180001594  call    memset_0
0x180001599  lea     rcx, [rbx+80h]; void *
0x1800015a0  xor     edx, edx; Val
0x1800015a2  mov     r8d, 80h; Size
0x1800015a8  call    memset_0
0x1800015ad  mov     r8d, 104h; nSize
0x1800015b3  lea     rdx, [rbx+11Ch]; lpDst
0x1800015ba  lea     rcx, Src; "%windir%\\tracing"
0x1800015c1  call    cs:__imp_ExpandEnvironmentStringsA
0x1800015c7  test    eax, eax
0x1800015c9  jnz     short loc_1800015D3
0x1800015cb  call    cs:__imp_GetLastError
0x1800015d1  jmp     short loc_180001601
0x1800015d3  lea     rcx, [rbx+11Ch]; lpString
0x1800015da  call    cs:__imp_lstrlenA
0x1800015e0  inc     eax
0x1800015e2  lea     rcx, [rbx+222h]
0x1800015e9  movsxd  r8, eax
0x1800015ec  lea     rdx, [rbx+11Ch]
0x1800015f3  call    cs:__imp__o_mbstowcs
0x1800015f9  mov     rcx, rbx; lpCriticalSection
0x1800015fc  call    CreateReadWriteLock
0x180001601  mov     esi, eax
0x180001603  test    eax, eax
0x180001605  jz      short loc_18000161E
0x180001607  call    cs:__imp_GetProcessHeap
0x18000160d  mov     r8, rbx; lpMem
0x180001610  xor     edx, edx; dwFlags
0x180001612  mov     rcx, rax; hHeap
0x180001615  call    cs:__imp_HeapFree
0x18000161b  mov     rbx, rbp
0x18000161e  xchg    rbx, [rdi]
0x180001621  mov     rbx, [rsp+28h+arg_10]
0x180001626  mov     eax, esi
0x180001628  mov     rsi, [rsp+28h+arg_8]
0x18000162d  mov     rbp, [rsp+28h+arg_0]
0x180001632  add     rsp, 20h
0x180001636  pop     rdi
0x180001637  retn
```
