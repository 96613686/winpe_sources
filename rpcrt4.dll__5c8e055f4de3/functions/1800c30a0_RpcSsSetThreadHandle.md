# RpcSsSetThreadHandle

- ea: `0x1800c30a0`
- end: `0x1800c3131`
- name: `RpcSsSetThreadHandle`
- size: `145`
- prototype: `void __stdcall(RPC_SS_THREAD_HANDLE Id)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800c2f10`

## callees

- `0x180022870`
- `0x1800a37e4`
- `0x1800c2bc8`
- `0x1800c2c88`
- `0x1800c30a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c30ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c311b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c30ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c311b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c30c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c310e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c30c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c310e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c30f7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c30f7`

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
0x1800c30a0  push    rbx
0x1800c30a2  push    rbp
0x1800c30a3  push    rsi
0x1800c30a4  push    rdi
0x1800c30a5  sub     rsp, 28h
0x1800c30a9  mov     rdi, rcx
0x1800c30ac  call    ?GetAllocContext@@YAPEAU_ALLOCATION_CONTEXT@@XZ; GetAllocContext(void)
0x1800c30b1  mov     rbx, rax
0x1800c30b4  cmp     rax, rdi
0x1800c30b7  jz      short loc_1800C3121
0x1800c30b9  test    rax, rax
0x1800c30bc  jz      short loc_1800C3105
0x1800c30be  lea     rsi, [rax+18h]
0x1800c30c2  xor     ebp, ebp
0x1800c30c4  mov     rcx, rsi; lpCriticalSection
0x1800c30c7  call    cs:__imp_EnterCriticalSection
0x1800c30cd  cmp     dword ptr [rbx+40h], 1
0x1800c30d1  jnz     short loc_1800C30E7
0x1800c30d3  mov     rcx, rbx
0x1800c30d6  call    NdrpReleaseMemory
0x1800c30db  xor     ecx, ecx; lpTlsValue
0x1800c30dd  mov     ebp, 1
0x1800c30e2  call    ?SetAllocContext@@YAXPEAU_ALLOCATION_CONTEXT@@@Z; SetAllocContext(_ALLOCATION_CONTEXT *)
0x1800c30e7  mov     rcx, rsi; lpCriticalSection
0x1800c30ea  call    cs:__imp_LeaveCriticalSection
0x1800c30f0  test    ebp, ebp
0x1800c30f2  jz      short loc_1800C3105
0x1800c30f4  mov     rcx, rsi; lpCriticalSection
0x1800c30f7  call    cs:__imp_DeleteCriticalSection
0x1800c30fd  mov     rcx, rbx; lpMem
0x1800c3100  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800c3105  test    rdi, rdi
0x1800c3108  jz      short loc_1800C3121
0x1800c310a  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800c310e  call    cs:__imp_EnterCriticalSection
0x1800c3114  inc     dword ptr [rdi+40h]
0x1800c3117  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800c311b  call    cs:__imp_LeaveCriticalSection
0x1800c3121  mov     rcx, rdi; lpTlsValue
0x1800c3124  add     rsp, 28h
0x1800c3128  pop     rdi
0x1800c3129  pop     rsi
0x1800c312a  pop     rbp
0x1800c312b  pop     rbx
0x1800c312c  jmp     ?SetAllocContext@@YAXPEAU_ALLOCATION_CONTEXT@@@Z; SetAllocContext(_ALLOCATION_CONTEXT *)
```
