# Windows::Internal::ComTaskPoolHandler::Start(Windows::Internal::IComPoolTask *)

- ea: `0x18007c898`
- end: `0x18007c8db`
- name: `?Start@ComTaskPoolHandler@Internal@Windows@@QEAAJPEAUIComPoolTask@23@@Z`
- size: `67`
- prototype: `__int64 __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this, struct Windows::Internal::IComPoolTask *)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18007a340`
- `0x18009f3f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007c8a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007c8a8`
- `SHCORE!SHTaskPoolQueueTask` at `0x18007c8ca`
- `SHCORE!SHTaskPoolQueueTask` at `0x18007c8ca`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPoolHandler::Start(
        Windows::Internal::ComTaskPoolHandler *this,
        struct Windows::Internal::IComPoolTask *a2)
{
  DWORD CurrentThreadId; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx

  CurrentThreadId = GetCurrentThreadId();
  v4 = *((unsigned int *)this + 1);
  v5 = *(unsigned int *)this;
  *((_DWORD *)this + 2) = CurrentThreadId;
  return SHTaskPoolQueueTask(v5, v4, CurrentThreadId, 0);
}

```

## disassembly

```asm
0x18007c898  mov     [rsp+arg_0], rbx
0x18007c89d  push    rdi
0x18007c89e  sub     rsp, 30h
0x18007c8a2  mov     rbx, rdx
0x18007c8a5  mov     rdi, rcx
0x18007c8a8  call    cs:__imp_GetCurrentThreadId
0x18007c8ae  mov     edx, [rdi+4]
0x18007c8b1  xor     r9d, r9d
0x18007c8b4  mov     ecx, [rdi]
0x18007c8b6  mov     r8d, eax
0x18007c8b9  mov     [rsp+38h+var_10], 0
0x18007c8c2  mov     [rdi+8], eax
0x18007c8c5  mov     [rsp+38h+var_18], rbx
0x18007c8ca  call    cs:__imp_SHTaskPoolQueueTask
0x18007c8d0  mov     rbx, [rsp+38h+arg_0]
0x18007c8d5  add     rsp, 30h
0x18007c8d9  pop     rdi
0x18007c8da  retn
```
