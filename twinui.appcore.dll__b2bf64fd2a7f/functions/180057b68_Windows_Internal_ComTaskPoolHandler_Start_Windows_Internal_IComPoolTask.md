# Windows::Internal::ComTaskPoolHandler::Start(Windows::Internal::IComPoolTask *)

- ea: `0x180057b68`
- end: `0x180057bab`
- name: `?Start@ComTaskPoolHandler@Internal@Windows@@QEAAJPEAUIComPoolTask@23@@Z`
- size: `67`
- prototype: `__int64 __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this, struct Windows::Internal::IComPoolTask *)`
- caller_count: `5`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800540f0`
- `0x1800541a0`
- `0x180054250`
- `0x180054300`
- `0x18006b6c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057b78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057b78`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180057b9a`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180057b9a`

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
  return SHTaskPoolQueueTask(v5, v4, CurrentThreadId);
}

```

## disassembly

```asm
0x180057b68  mov     [rsp+arg_0], rbx
0x180057b6d  push    rdi
0x180057b6e  sub     rsp, 30h
0x180057b72  mov     rbx, rdx
0x180057b75  mov     rdi, rcx
0x180057b78  call    cs:__imp_GetCurrentThreadId
0x180057b7e  mov     edx, [rdi+4]
0x180057b81  xor     r9d, r9d
0x180057b84  mov     ecx, [rdi]
0x180057b86  mov     r8d, eax
0x180057b89  mov     [rsp+38h+var_10], 0
0x180057b92  mov     [rdi+8], eax
0x180057b95  mov     [rsp+38h+var_18], rbx
0x180057b9a  call    cs:__imp_SHTaskPoolQueueTask
0x180057ba0  mov     rbx, [rsp+38h+arg_0]
0x180057ba5  add     rsp, 30h
0x180057ba9  pop     rdi
0x180057baa  retn
```
