# WARMUP_APPLICATION_CONTEXT::StartWarmupRequests(IHttpApplication2 *)

- ea: `0x180004a90`
- end: `0x180004bb1`
- name: `?StartWarmupRequests@WARMUP_APPLICATION_CONTEXT@@UEAAJPEAVIHttpApplication2@@@Z`
- size: `289`
- prototype: `__int64 __fastcall(WARMUP_APPLICATION_CONTEXT *__hidden this, struct IHttpApplication2 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004a90`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b17`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004b82`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180004b82`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180004ae3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180004ae3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b9e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180004b08`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180004b08`
- `iisutil!PuDbgPrint` at `0x180004b60`
- `iisutil!PuDbgPrint` at `0x180004b60`

## string_xrefs

- `0x180004b3c`: `Error %d creating preload thread.`
- `0x180004b59`: `servercommon\inetsrv\iis\iisrearc\iis70\appwarmup\warmupcontext.cxx`

## pseudocode

```c
__int64 __fastcall WARMUP_APPLICATION_CONTEXT::StartWarmupRequests(
        WARMUP_APPLICATION_CONTEXT *this,
        struct IHttpApplication2 *a2)
{
  __int64 result; // rax
  HANDLE *v5; // rcx
  HANDLE Thread; // rax
  signed int LastError; // eax
  unsigned int v8; // ebx
  HANDLE *v9; // rcx

  result = (*(__int64 (__fastcall **)(WARMUP_APPLICATION_CONTEXT *))(*(_QWORD *)this + 56LL))(this);
  if ( (_DWORD)result )
  {
    (*(void (__fastcall **)(struct IHttpApplication2 *))(*(_QWORD *)a2 + 32LL))(a2);
    v5 = (HANDLE *)g_pPreloadBlock;
    if ( g_pPreloadBlock && _InterlockedIncrement((volatile signed __int32 *)g_pPreloadBlock) == 1 )
      ResetEvent(v5[1]);
    Thread = CreateThread(0, 0, WARMUP_APPLICATION_CONTEXT::sm_WarmupThread, this, 0, 0);
    if ( Thread )
    {
      v8 = 0;
      CloseHandle(Thread);
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\appwarmup\\warmupcontext.cxx",
          125,
          "WARMUP_APPLICATION_CONTEXT::StartWarmupRequests",
          "Error %d creating preload thread.",
          v8);
      v9 = (HANDLE *)g_pPreloadBlock;
      if ( g_pPreloadBlock )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)g_pPreloadBlock, 0xFFFFFFFF) == 1 )
          SetEvent(v9[1]);
      }
      (*(void (__fastcall **)(struct IHttpApplication2 *))(*(_QWORD *)a2 + 40LL))(a2);
    }
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x180004a90  mov     [rsp+arg_8], rbx
0x180004a95  push    rdi
0x180004a96  sub     rsp, 30h
0x180004a9a  mov     rax, [rcx]
0x180004a9d  mov     rdi, rdx
0x180004aa0  mov     rbx, rcx
0x180004aa3  mov     rax, [rax+38h]
0x180004aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aac  test    eax, eax
0x180004aae  jz      loc_180004BA6
0x180004ab4  mov     rax, [rdi]
0x180004ab7  mov     rcx, rdi
0x180004aba  mov     rax, [rax+20h]
0x180004abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ac3  mov     rcx, cs:?g_pPreloadBlock@@3PEAVPRELOAD_BLOCK@@EA; PRELOAD_BLOCK * g_pPreloadBlock
0x180004aca  test    rcx, rcx
0x180004acd  jz      short loc_180004AE9
0x180004acf  mov     eax, 1
0x180004ad4  lock xadd [rcx], eax
0x180004ad8  inc     eax
0x180004ada  cmp     eax, 1
0x180004add  jnz     short loc_180004AE9
0x180004adf  mov     rcx, [rcx+8]; hEvent
0x180004ae3  call    cs:__imp_ResetEvent
0x180004ae9  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180004af2  lea     r8, ?sm_WarmupThread@WARMUP_APPLICATION_CONTEXT@@CAKPEAX@Z; lpStartAddress
0x180004af9  mov     r9, rbx; lpParameter
0x180004afc  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180004b04  xor     edx, edx; dwStackSize
0x180004b06  xor     ecx, ecx; lpThreadAttributes
0x180004b08  call    cs:__imp_CreateThread
0x180004b0e  test    rax, rax
0x180004b11  jnz     loc_180004B99
0x180004b17  call    cs:__imp_GetLastError
0x180004b1d  mov     ebx, eax
0x180004b1f  test    eax, eax
0x180004b21  jle     short loc_180004B2C
0x180004b23  movzx   ebx, ax
0x180004b26  or      ebx, 80070000h
0x180004b2c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004b33  jz      short loc_180004B66
0x180004b35  mov     rcx, cs:g_pDebug
0x180004b3c  lea     rax, aErrorDCreating; "Error %d creating preload thread."
0x180004b43  mov     dword ptr [rsp+38h+lpThreadId], ebx
0x180004b47  lea     r9, aWarmupApplicat; "WARMUP_APPLICATION_CONTEXT::StartWarmup"...
0x180004b4e  mov     r8d, 7Dh ; '}'
0x180004b54  mov     qword ptr [rsp+38h+dwCreationFlags], rax
0x180004b59  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004b60  call    cs:__imp_PuDbgPrint
0x180004b66  mov     rcx, cs:?g_pPreloadBlock@@3PEAVPRELOAD_BLOCK@@EA; PRELOAD_BLOCK * g_pPreloadBlock
0x180004b6d  test    rcx, rcx
0x180004b70  jz      short loc_180004B88
0x180004b72  or      eax, 0FFFFFFFFh
0x180004b75  lock xadd [rcx], eax
0x180004b79  cmp     eax, 1
0x180004b7c  jnz     short loc_180004B88
0x180004b7e  mov     rcx, [rcx+8]; hEvent
0x180004b82  call    cs:__imp_SetEvent
0x180004b88  mov     rax, [rdi]
0x180004b8b  mov     rcx, rdi
0x180004b8e  mov     rax, [rax+28h]
0x180004b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b97  jmp     short loc_180004BA4
0x180004b99  xor     ebx, ebx
0x180004b9b  mov     rcx, rax; hObject
0x180004b9e  call    cs:__imp_CloseHandle
0x180004ba4  mov     eax, ebx
0x180004ba6  mov     rbx, [rsp+38h+arg_8]
0x180004bab  add     rsp, 30h
0x180004baf  pop     rdi
0x180004bb0  retn
```
