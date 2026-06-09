# pRemovePartialMessage(void)

- ea: `0x18001b38c`
- end: `0x18001b446`
- name: `?pRemovePartialMessage@@YAXXZ`
- size: `186`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b610`
- `0x18001b8f0`

## callees

- `0x18001b38c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b401`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b401`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b3ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b3ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b430`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b430`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b3c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b3c3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b3a4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b3a4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001b41d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001b41d`

## pseudocode

```c
void pRemovePartialMessage(void)
{
  LPVOID Value; // rbx
  __int64 v1; // rcx
  _QWORD *v2; // rdi
  __int64 v3; // rsi
  void *v4; // rbp
  HANDLE ProcessHeap; // rax

  if ( g_dwConstructMessageTLSIndex != -1 )
  {
    Value = TlsGetValue(g_dwConstructMessageTLSIndex);
    if ( Value )
    {
      EnterCriticalSection(&g_pBufferListLock);
      LODWORD(v1) = g_uiBufferListLen;
      v2 = g_pBuffersList;
      while ( (_DWORD)v1 )
      {
        v1 = (unsigned int)(v1 - 1);
        v3 = (unsigned int)v1;
        v4 = (void *)*((_QWORD *)g_pBuffersList + v1);
        if ( v4 == Value )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v4);
          v2[v3] = 0;
          break;
        }
      }
      TlsSetValue(g_dwConstructMessageTLSIndex, 0);
      LeaveCriticalSection(&g_pBufferListLock);
    }
  }
}

```

## disassembly

```asm
0x18001b38c  push    rbx
0x18001b38e  push    rbp
0x18001b38f  push    rsi
0x18001b390  push    rdi
0x18001b391  sub     rsp, 28h
0x18001b395  mov     ecx, cs:?g_dwConstructMessageTLSIndex@@3KA; dwTlsIndex
0x18001b39b  cmp     ecx, 0FFFFFFFFh
0x18001b39e  jz      loc_18001B43C
0x18001b3a4  call    cs:__imp_TlsGetValue
0x18001b3ab  nop     dword ptr [rax+rax+00h]
0x18001b3b0  mov     rbx, rax
0x18001b3b3  test    rax, rax
0x18001b3b6  jz      loc_18001B43C
0x18001b3bc  lea     rcx, ?g_pBufferListLock@@3VCWdsCritSection@@A; lpCriticalSection
0x18001b3c3  call    cs:__imp_EnterCriticalSection
0x18001b3ca  nop     dword ptr [rax+rax+00h]
0x18001b3cf  mov     ecx, cs:?g_uiBufferListLen@@3IA; uint g_uiBufferListLen
0x18001b3d5  mov     rdi, cs:?g_pBuffersList@@3PEAPEAXEA; void * * g_pBuffersList
0x18001b3dc  test    ecx, ecx
0x18001b3de  jz      short loc_18001B415
0x18001b3e0  dec     ecx
0x18001b3e2  mov     esi, ecx
0x18001b3e4  mov     rbp, [rdi+rcx*8]
0x18001b3e8  cmp     rbp, rbx
0x18001b3eb  jnz     short loc_18001B3DC
0x18001b3ed  call    cs:__imp_GetProcessHeap
0x18001b3f4  nop     dword ptr [rax+rax+00h]
0x18001b3f9  mov     r8, rbp; lpMem
0x18001b3fc  xor     edx, edx; dwFlags
0x18001b3fe  mov     rcx, rax; hHeap
0x18001b401  call    cs:__imp_HeapFree
0x18001b408  nop     dword ptr [rax+rax+00h]
0x18001b40d  mov     qword ptr [rdi+rsi*8], 0
0x18001b415  mov     ecx, cs:?g_dwConstructMessageTLSIndex@@3KA; dwTlsIndex
0x18001b41b  xor     edx, edx; lpTlsValue
0x18001b41d  call    cs:__imp_TlsSetValue
0x18001b424  nop     dword ptr [rax+rax+00h]
0x18001b429  lea     rcx, ?g_pBufferListLock@@3VCWdsCritSection@@A; lpCriticalSection
0x18001b430  call    cs:__imp_LeaveCriticalSection
0x18001b437  nop     dword ptr [rax+rax+00h]
0x18001b43c  add     rsp, 28h
0x18001b440  pop     rdi
0x18001b441  pop     rsi
0x18001b442  pop     rbp
0x18001b443  pop     rbx
0x18001b444  retn
```
