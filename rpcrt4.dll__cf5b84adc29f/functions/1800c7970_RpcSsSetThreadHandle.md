# RpcSsSetThreadHandle

- ea: `0x1800c7970`
- end: `0x1800c7a23`
- name: `RpcSsSetThreadHandle`
- size: `179`
- prototype: `void __stdcall(RPC_SS_THREAD_HANDLE Id)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800c77d0`

## callees

- `0x180023a40`
- `0x1800a6cd8`
- `0x1800c7440`
- `0x1800c7508`
- `0x1800c7970`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c79c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c7a07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c79c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c7a07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c799b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c79f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c799b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c79f4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c79d7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c79d7`

## pseudocode

```c
void __stdcall RpcSsSetThreadHandle(RPC_SS_THREAD_HANDLE Id)
{
  struct _ALLOCATION_CONTEXT *AllocContext; // rax
  struct _ALLOCATION_CONTEXT *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  int v5; // ebp

  AllocContext = GetAllocContext();
  v3 = AllocContext;
  if ( AllocContext != Id )
  {
    if ( AllocContext )
    {
      v4 = (struct _RTL_CRITICAL_SECTION *)((char *)AllocContext + 24);
      v5 = 0;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)AllocContext + 24));
      if ( *((_DWORD *)v3 + 16) == 1 )
      {
        NdrpReleaseMemory(v3);
        v5 = 1;
        SetAllocContext(0);
      }
      LeaveCriticalSection(v4);
      if ( v5 )
      {
        DeleteCriticalSection(v4);
        FreeWrapper(v3);
      }
    }
    if ( Id )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)Id + 24));
      ++*((_DWORD *)Id + 16);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)Id + 24));
    }
  }
  SetAllocContext((struct _ALLOCATION_CONTEXT *)Id);
}

```

## disassembly

```asm
0x1800c7970  push    rbx
0x1800c7972  push    rbp
0x1800c7973  push    rsi
0x1800c7974  push    rdi
0x1800c7975  sub     rsp, 28h
0x1800c7979  mov     rdi, rcx
0x1800c797c  call    ?GetAllocContext@@YAPEAU_ALLOCATION_CONTEXT@@XZ; GetAllocContext(void)
0x1800c7981  mov     rbx, rax
0x1800c7984  cmp     rax, rdi
0x1800c7987  jz      loc_1800C7A13
0x1800c798d  test    rax, rax
0x1800c7990  jz      short loc_1800C79EB
0x1800c7992  lea     rsi, [rax+18h]
0x1800c7996  xor     ebp, ebp
0x1800c7998  mov     rcx, rsi; lpCriticalSection
0x1800c799b  call    cs:__imp_EnterCriticalSection
0x1800c79a2  nop     dword ptr [rax+rax+00h]
0x1800c79a7  cmp     dword ptr [rbx+40h], 1
0x1800c79ab  jnz     short loc_1800C79C1
0x1800c79ad  mov     rcx, rbx
0x1800c79b0  call    NdrpReleaseMemory
0x1800c79b5  xor     ecx, ecx; lpTlsValue
0x1800c79b7  mov     ebp, 1
0x1800c79bc  call    ?SetAllocContext@@YAXPEAU_ALLOCATION_CONTEXT@@@Z; SetAllocContext(_ALLOCATION_CONTEXT *)
0x1800c79c1  mov     rcx, rsi; lpCriticalSection
0x1800c79c4  call    cs:__imp_LeaveCriticalSection
0x1800c79cb  nop     dword ptr [rax+rax+00h]
0x1800c79d0  test    ebp, ebp
0x1800c79d2  jz      short loc_1800C79EB
0x1800c79d4  mov     rcx, rsi; lpCriticalSection
0x1800c79d7  call    cs:__imp_DeleteCriticalSection
0x1800c79de  nop     dword ptr [rax+rax+00h]
0x1800c79e3  mov     rcx, rbx; lpMem
0x1800c79e6  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800c79eb  test    rdi, rdi
0x1800c79ee  jz      short loc_1800C7A13
0x1800c79f0  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800c79f4  call    cs:__imp_EnterCriticalSection
0x1800c79fb  nop     dword ptr [rax+rax+00h]
0x1800c7a00  inc     dword ptr [rdi+40h]
0x1800c7a03  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800c7a07  call    cs:__imp_LeaveCriticalSection
0x1800c7a0e  nop     dword ptr [rax+rax+00h]
0x1800c7a13  mov     rcx, rdi; lpTlsValue
0x1800c7a16  add     rsp, 28h
0x1800c7a1a  pop     rdi
0x1800c7a1b  pop     rsi
0x1800c7a1c  pop     rbp
0x1800c7a1d  pop     rbx
0x1800c7a1e  jmp     ?SetAllocContext@@YAXPEAU_ALLOCATION_CONTEXT@@@Z; SetAllocContext(_ALLOCATION_CONTEXT *)
```
