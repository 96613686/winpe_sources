# TraceDeleteClientA

- ea: `0x180002c80`
- end: `0x180002d87`
- name: `TraceDeleteClientA`
- size: `263`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180001100`
- `0x180002e90`

## callees

- `0x180002c80`
- `0x180003000`
- `0x180005e98`
- `0x180005f3c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002cf7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002cf7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002ce6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002d56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002ce6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002d56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002d31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002d31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002cce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002cce`

## pseudocode

```c
__int64 __fastcall TraceDeleteClientA(__int64 a1, volatile __int64 *a2)
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
0x180002c80  mov     [rsp+arg_0], rbx
0x180002c85  push    rdi
0x180002c86  sub     rsp, 20h
0x180002c8a  mov     rdi, rcx
0x180002c8d  test    rdx, rdx
0x180002c90  jz      loc_180002D77
0x180002c96  mov     rbx, [rdx]
0x180002c99  test    rbx, rbx
0x180002c9c  jz      loc_180002D77
0x180002ca2  xor     eax, eax
0x180002ca4  xchg    rax, [rdx]
0x180002ca7  mov     eax, [rbx+3Ch]
0x180002caa  lea     rdx, [rcx+rax*4]
0x180002cae  xor     eax, eax
0x180002cb0  xchg    eax, [rdx+70h]
0x180002cb3  cmp     qword ptr [rbx+30h], 0
0x180002cb8  jz      short loc_180002CC2
0x180002cba  mov     rcx, rbx; lpCriticalSection
0x180002cbd  call    DeleteReadWriteLock
0x180002cc2  mov     rcx, [rbx+430h]; hKey
0x180002cc9  test    rcx, rcx
0x180002ccc  jz      short loc_180002CD4
0x180002cce  call    cs:__imp_RegCloseKey
0x180002cd4  mov     rcx, [rbx+438h]; hObject
0x180002cdb  test    rcx, rcx
0x180002cde  jz      short loc_180002D37
0x180002ce0  test    byte ptr [rdi+38h], 10h
0x180002ce4  jz      short loc_180002D31
0x180002ce6  call    cs:__imp_GetProcessHeap
0x180002cec  xor     edx, edx; dwFlags
0x180002cee  mov     r8d, 18h; dwBytes
0x180002cf4  mov     rcx, rax; hHeap
0x180002cf7  call    cs:__imp_HeapAlloc
0x180002cfd  test    rax, rax
0x180002d00  jz      short loc_180002D37
0x180002d02  mov     rcx, [rbx+438h]
0x180002d09  mov     [rax+10h], rcx
0x180002d0d  lea     rcx, [rdi+60h]
0x180002d11  mov     rdx, [rcx]
0x180002d14  cmp     [rdx+8], rcx
0x180002d18  jz      short loc_180002D21
0x180002d1a  mov     ecx, 3
0x180002d1f  int     29h; Win8: RtlFailFast(ecx)
0x180002d21  mov     [rax], rdx
0x180002d24  mov     [rax+8], rcx
0x180002d28  mov     [rdx+8], rax
0x180002d2c  mov     [rcx], rax
0x180002d2f  jmp     short loc_180002D37
0x180002d31  call    cs:__imp_CloseHandle
0x180002d37  test    byte ptr [rbx+38h], 4
0x180002d3b  jz      short loc_180002D48
0x180002d3d  mov     rdx, rbx
0x180002d40  mov     rcx, rdi
0x180002d43  call    TraceCloseClientConsoleW
0x180002d48  test    byte ptr [rbx+38h], 2
0x180002d4c  jz      short loc_180002D56
0x180002d4e  mov     rcx, rbx
0x180002d51  call    TraceCloseClientFileW
0x180002d56  call    cs:__imp_GetProcessHeap
0x180002d5c  mov     r8, rbx; lpMem
0x180002d5f  xor     edx, edx; dwFlags
0x180002d61  mov     rcx, rax; hHeap
0x180002d64  call    cs:__imp_HeapFree
0x180002d6a  xor     eax, eax
0x180002d6c  mov     rbx, [rsp+28h+arg_0]
0x180002d71  add     rsp, 20h
0x180002d75  pop     rdi
0x180002d76  retn
0x180002d77  mov     rbx, [rsp+28h+arg_0]
0x180002d7c  mov     eax, 57h ; 'W'
0x180002d81  add     rsp, 20h
0x180002d85  pop     rdi
0x180002d86  retn
```
