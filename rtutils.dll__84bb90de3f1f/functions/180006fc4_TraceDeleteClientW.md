# TraceDeleteClientW

- ea: `0x180006fc4`
- end: `0x1800070bd`
- name: `TraceDeleteClientW`
- size: `249`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004c10`
- `0x180005450`

## callees

- `0x180003000`
- `0x180005e98`
- `0x180005f3c`
- `0x180006fc4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007036`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007036`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007027`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007095`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007027`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007095`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800070a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800070a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007070`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007070`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000700f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000700f`

## pseudocode

```c
__int64 __fastcall TraceDeleteClientW(__int64 a1, volatile __int64 *a2)
{
  volatile __int64 v3; // rbx
  HKEY v4; // rcx
  void *v5; // rcx
  HANDLE ProcessHeap; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  HANDLE v10; // rax

  if ( !a2 )
    return 87;
  v3 = *a2;
  if ( !*a2 )
    return 87;
  _InterlockedExchange64(a2, 0);
  _InterlockedExchange((volatile __int32 *)(a1 + 4LL * *(unsigned int *)(v3 + 60) + 112), 0);
  if ( *(_QWORD *)(v3 + 48) )
    DeleteReadWriteLock((LPCRITICAL_SECTION)v3);
  v4 = *(HKEY *)(v3 + 1072);
  if ( v4 )
    RegCloseKey(v4);
  v5 = *(void **)(v3 + 1080);
  if ( v5 )
  {
    if ( (*(_BYTE *)(a1 + 56) & 0x10) != 0 )
    {
      ProcessHeap = GetProcessHeap();
      v7 = HeapAlloc(ProcessHeap, 0, 0x18u);
      if ( v7 )
      {
        v7[2] = *(_QWORD *)(v3 + 1080);
        v8 = (_QWORD *)(a1 + 96);
        v9 = *(_QWORD *)(a1 + 96);
        if ( *(_QWORD *)(v9 + 8) != a1 + 96 )
          __fastfail(3u);
        *v7 = v9;
        v7[1] = v8;
        *(_QWORD *)(v9 + 8) = v7;
        *v8 = v7;
      }
    }
    else
    {
      CloseHandle(v5);
    }
  }
  if ( (*(_BYTE *)(v3 + 56) & 4) != 0 )
    TraceCloseClientConsoleW(a1, v3);
  if ( (*(_BYTE *)(v3 + 56) & 2) != 0 )
    TraceCloseClientFileW(v3);
  v10 = GetProcessHeap();
  HeapFree(v10, 0, (LPVOID)v3);
  return 0;
}

```

## disassembly

```asm
0x180006fc4  mov     [rsp+arg_0], rbx
0x180006fc9  push    rdi
0x180006fca  sub     rsp, 20h
0x180006fce  mov     rdi, rcx
0x180006fd1  test    rdx, rdx
0x180006fd4  jz      loc_1800070AD
0x180006fda  mov     rbx, [rdx]
0x180006fdd  test    rbx, rbx
0x180006fe0  jz      loc_1800070AD
0x180006fe6  xor     eax, eax
0x180006fe8  xchg    rax, [rdx]
0x180006feb  mov     edx, [rbx+3Ch]
0x180006fee  xor     eax, eax
0x180006ff0  xchg    eax, [rcx+rdx*4+70h]
0x180006ff4  cmp     qword ptr [rbx+30h], 0
0x180006ff9  jz      short loc_180007003
0x180006ffb  mov     rcx, rbx; lpCriticalSection
0x180006ffe  call    DeleteReadWriteLock
0x180007003  mov     rcx, [rbx+430h]; hKey
0x18000700a  test    rcx, rcx
0x18000700d  jz      short loc_180007015
0x18000700f  call    cs:__imp_RegCloseKey
0x180007015  mov     rcx, [rbx+438h]; hObject
0x18000701c  test    rcx, rcx
0x18000701f  jz      short loc_180007076
0x180007021  test    byte ptr [rdi+38h], 10h
0x180007025  jz      short loc_180007070
0x180007027  call    cs:__imp_GetProcessHeap
0x18000702d  xor     edx, edx; dwFlags
0x18000702f  mov     rcx, rax; hHeap
0x180007032  lea     r8d, [rdx+18h]; dwBytes
0x180007036  call    cs:__imp_HeapAlloc
0x18000703c  test    rax, rax
0x18000703f  jz      short loc_180007076
0x180007041  mov     rcx, [rbx+438h]
0x180007048  mov     [rax+10h], rcx
0x18000704c  lea     rcx, [rdi+60h]
0x180007050  mov     rdx, [rcx]
0x180007053  cmp     [rdx+8], rcx
0x180007057  jz      short loc_180007060
0x180007059  mov     ecx, 3
0x18000705e  int     29h; Win8: RtlFailFast(ecx)
0x180007060  mov     [rax], rdx
0x180007063  mov     [rax+8], rcx
0x180007067  mov     [rdx+8], rax
0x18000706b  mov     [rcx], rax
0x18000706e  jmp     short loc_180007076
0x180007070  call    cs:__imp_CloseHandle
0x180007076  test    byte ptr [rbx+38h], 4
0x18000707a  jz      short loc_180007087
0x18000707c  mov     rdx, rbx
0x18000707f  mov     rcx, rdi
0x180007082  call    TraceCloseClientConsoleW
0x180007087  test    byte ptr [rbx+38h], 2
0x18000708b  jz      short loc_180007095
0x18000708d  mov     rcx, rbx
0x180007090  call    TraceCloseClientFileW
0x180007095  call    cs:__imp_GetProcessHeap
0x18000709b  mov     r8, rbx; lpMem
0x18000709e  xor     edx, edx; dwFlags
0x1800070a0  mov     rcx, rax; hHeap
0x1800070a3  call    cs:__imp_HeapFree
0x1800070a9  xor     eax, eax
0x1800070ab  jmp     short loc_1800070B2
0x1800070ad  mov     eax, 57h ; 'W'
0x1800070b2  mov     rbx, [rsp+28h+arg_0]
0x1800070b7  add     rsp, 20h
0x1800070bb  pop     rdi
0x1800070bc  retn
```
