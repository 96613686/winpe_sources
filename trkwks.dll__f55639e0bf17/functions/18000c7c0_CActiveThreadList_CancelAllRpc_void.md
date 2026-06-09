# CActiveThreadList::CancelAllRpc(void)

- ea: `0x18000c7c0`
- end: `0x18000c82a`
- name: `?CancelAllRpc@CActiveThreadList@@QEAAXXZ`
- size: `106`
- prototype: `void __fastcall(CActiveThreadList *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800016f4`

## callees

- `0x18000c7c0`

## import_xrefs

- `RPCRT4!RpcCancelThread` at `0x18000c801`
- `RPCRT4!RpcCancelThread` at `0x18000c801`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c7d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c7d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c823`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c80a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c80a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18000c7f0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18000c7f0`

## pseudocode

```c
void __fastcall CActiveThreadList::CancelAllRpc(CActiveThreadList *this)
{
  CActiveThreadList *v1; // rdi
  __int64 i; // rbx
  HANDLE v3; // rax
  void *v4; // rsi

  v1 = g_pActiveThreadList;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pActiveThreadList + 16));
  for ( i = 0; (unsigned int)i < *((_DWORD *)v1 + 1); i = (unsigned int)(i + 1) )
  {
    v3 = OpenThread(0x1FFFFFu, 0, *(_DWORD *)(*((_QWORD *)v1 + 1) + 4 * i));
    v4 = v3;
    if ( v3 )
    {
      RpcCancelThread(v3);
      CloseHandle(v4);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 16));
}

```

## disassembly

```asm
0x18000c7c0  push    rbx
0x18000c7c2  push    rbp
0x18000c7c3  push    rsi
0x18000c7c4  push    rdi
0x18000c7c5  sub     rsp, 28h
0x18000c7c9  mov     rdi, cs:g_pActiveThreadList
0x18000c7d0  lea     rcx, [rdi+10h]; lpCriticalSection
0x18000c7d4  call    cs:__imp_EnterCriticalSection
0x18000c7da  xor     ebx, ebx
0x18000c7dc  cmp     [rdi+4], ebx
0x18000c7df  jbe     short loc_18000C817
0x18000c7e1  mov     r8, [rdi+8]
0x18000c7e5  xor     edx, edx; bInheritHandle
0x18000c7e7  mov     ecx, 1FFFFFh; dwDesiredAccess
0x18000c7ec  mov     r8d, [r8+rbx*4]; dwThreadId
0x18000c7f0  call    cs:__imp_OpenThread
0x18000c7f6  mov     rsi, rax
0x18000c7f9  test    rax, rax
0x18000c7fc  jz      short loc_18000C810
0x18000c7fe  mov     rcx, rax; Thread
0x18000c801  call    cs:__imp_RpcCancelThread
0x18000c807  mov     rcx, rsi; hObject
0x18000c80a  call    cs:__imp_CloseHandle
0x18000c810  inc     ebx
0x18000c812  cmp     ebx, [rdi+4]
0x18000c815  jb      short loc_18000C7E1
0x18000c817  lea     rcx, [rdi+10h]
0x18000c81b  add     rsp, 28h
0x18000c81f  pop     rdi
0x18000c820  pop     rsi
0x18000c821  pop     rbp
0x18000c822  pop     rbx
0x18000c823  jmp     cs:__imp_LeaveCriticalSection
```
