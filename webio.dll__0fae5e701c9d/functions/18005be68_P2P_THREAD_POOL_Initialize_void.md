# P2P_THREAD_POOL::Initialize(void)

- ea: `0x18005be68`
- end: `0x18005bf62`
- name: `?Initialize@P2P_THREAD_POOL@@QEAAKXZ`
- size: `250`
- prototype: `unsigned int __fastcall(P2P_THREAD_POOL *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18005bdd4`

## callees

- `0x18005be68`
- `0x18006a1ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005bf10`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005bf10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bea6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bea6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005bf36`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005bf36`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18005bed7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18005bed7`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18005be92`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18005be92`

## pseudocode

```c
DWORD __fastcall P2P_THREAD_POOL::Initialize(P2P_THREAD_POOL *this)
{
  HANDLE IoCompletionPort; // rax
  __int64 i; // rdi
  HANDLE v5; // rax
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF
  HMODULE phModule; // [rsp+48h] [rbp+10h] BYREF

  phModule = 0;
  ThreadId = 0;
  IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
  *(_QWORD *)this = IoCompletionPort;
  if ( !IoCompletionPort )
    return GetLastError();
  for ( i = 0; !(_DWORD)i; i = 1 )
  {
    _InterlockedIncrement((volatile signed __int32 *)this + 14);
    if ( !GetModuleHandleExW(4u, (LPCWSTR)P2P_THREAD_POOL::WorkerThreadRoutine, &phModule) )
    {
      P2P_THREAD_POOL::Dereference(this);
      return GetLastError();
    }
    *((_QWORD *)this + 6) = phModule;
    v5 = CreateThread(0, 0, P2P_THREAD_POOL::WorkerThreadRoutine, this, 0, &ThreadId);
    *((_QWORD *)this + i + 1) = v5;
    if ( !v5 )
    {
      P2P_THREAD_POOL::Dereference(this);
      FreeLibrary(*((HMODULE *)this + 6));
      return GetLastError();
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18005be68  mov     [rsp+arg_10], rbx
0x18005be6d  push    rdi
0x18005be6e  sub     rsp, 30h
0x18005be72  mov     rbx, rcx
0x18005be75  mov     [rsp+38h+phModule], 0
0x18005be7e  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x18005be82  mov     [rsp+38h+ThreadId], 0
0x18005be8a  xor     r9d, r9d; NumberOfConcurrentThreads
0x18005be8d  xor     r8d, r8d; CompletionKey
0x18005be90  xor     edx, edx; ExistingCompletionPort
0x18005be92  call    cs:__imp_CreateIoCompletionPort
0x18005be99  nop     dword ptr [rax+rax+00h]
0x18005be9e  mov     [rbx], rax
0x18005bea1  test    rax, rax
0x18005bea4  jnz     short loc_18005BEB7
0x18005bea6  call    cs:__imp_GetLastError
0x18005bead  nop     dword ptr [rax+rax+00h]
0x18005beb2  jmp     loc_18005BF56
0x18005beb7  xor     edi, edi
0x18005beb9  cmp     edi, 1
0x18005bebc  jnb     loc_18005BF54
0x18005bec2  lock inc dword ptr [rbx+38h]
0x18005bec6  lea     r8, [rsp+38h+phModule]; phModule
0x18005becb  mov     ecx, 4; dwFlags
0x18005bed0  lea     rdx, ?WorkerThreadRoutine@P2P_THREAD_POOL@@CAKPEAX@Z; lpModuleName
0x18005bed7  call    cs:__imp_GetModuleHandleExW
0x18005bede  nop     dword ptr [rax+rax+00h]
0x18005bee3  test    eax, eax
0x18005bee5  jz      short loc_18005BF47
0x18005bee7  mov     rax, [rsp+38h+phModule]
0x18005beec  lea     r8, ?WorkerThreadRoutine@P2P_THREAD_POOL@@CAKPEAX@Z; lpStartAddress
0x18005bef3  mov     [rbx+30h], rax
0x18005bef7  mov     r9, rbx; lpParameter
0x18005befa  lea     rax, [rsp+38h+ThreadId]
0x18005beff  xor     edx, edx; dwStackSize
0x18005bf01  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18005bf06  xor     ecx, ecx; lpThreadAttributes
0x18005bf08  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18005bf10  call    cs:__imp_CreateThread
0x18005bf17  nop     dword ptr [rax+rax+00h]
0x18005bf1c  mov     [rbx+rdi*8+8], rax
0x18005bf21  test    rax, rax
0x18005bf24  jz      short loc_18005BF2A
0x18005bf26  inc     edi
0x18005bf28  jmp     short loc_18005BEB9
0x18005bf2a  mov     rcx, rbx; this
0x18005bf2d  call    ?Dereference@P2P_THREAD_POOL@@AEAAXXZ; P2P_THREAD_POOL::Dereference(void)
0x18005bf32  mov     rcx, [rbx+30h]; hLibModule
0x18005bf36  call    cs:__imp_FreeLibrary
0x18005bf3d  nop     dword ptr [rax+rax+00h]
0x18005bf42  jmp     loc_18005BEA6
0x18005bf47  mov     rcx, rbx; this
0x18005bf4a  call    ?Dereference@P2P_THREAD_POOL@@AEAAXXZ; P2P_THREAD_POOL::Dereference(void)
0x18005bf4f  jmp     loc_18005BEA6
0x18005bf54  xor     eax, eax
0x18005bf56  mov     rbx, [rsp+38h+arg_10]
0x18005bf5b  add     rsp, 30h
0x18005bf5f  pop     rdi
0x18005bf60  retn
```
