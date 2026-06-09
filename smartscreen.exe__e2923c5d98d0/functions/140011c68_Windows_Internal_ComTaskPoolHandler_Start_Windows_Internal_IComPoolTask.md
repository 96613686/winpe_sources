# Windows::Internal::ComTaskPoolHandler::Start(Windows::Internal::IComPoolTask *)

- ea: `0x140011c68`
- end: `0x140011cab`
- name: `?Start@ComTaskPoolHandler@Internal@Windows@@QEAAJPEAUIComPoolTask@23@@Z`
- size: `67`
- prototype: `__int64 __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this, struct Windows::Internal::IComPoolTask *)`
- caller_count: `4`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140011bc0`
- `0x140034550`
- `0x140034600`
- `0x14003e1e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011c78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011c78`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x140011c9a`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x140011c9a`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPoolHandler::Start(
        Windows::Internal::ComTaskPoolHandler *this,
        struct Windows::Internal::IComPoolTask *a2)
{
  DWORD CurrentThreadId; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx

  CurrentThreadId = GetCurrentThreadId();
  v5 = *((unsigned int *)this + 1);
  v6 = *(unsigned int *)this;
  *((_DWORD *)this + 2) = CurrentThreadId;
  return SHTaskPoolQueueTask(v6, v5, CurrentThreadId, 0, a2, 0);
}

```

## disassembly

```asm
0x140011c68  mov     [rsp+arg_0], rbx
0x140011c6d  push    rdi
0x140011c6e  sub     rsp, 30h
0x140011c72  mov     rbx, rdx
0x140011c75  mov     rdi, rcx
0x140011c78  call    cs:__imp_GetCurrentThreadId
0x140011c7e  mov     edx, [rdi+4]
0x140011c81  xor     r9d, r9d
0x140011c84  mov     ecx, [rdi]
0x140011c86  mov     r8d, eax
0x140011c89  mov     [rsp+38h+var_10], 0
0x140011c92  mov     [rdi+8], eax
0x140011c95  mov     [rsp+38h+var_18], rbx
0x140011c9a  call    cs:__imp_SHTaskPoolQueueTask
0x140011ca0  mov     rbx, [rsp+38h+arg_0]
0x140011ca5  add     rsp, 30h
0x140011ca9  pop     rdi
0x140011caa  retn
```
