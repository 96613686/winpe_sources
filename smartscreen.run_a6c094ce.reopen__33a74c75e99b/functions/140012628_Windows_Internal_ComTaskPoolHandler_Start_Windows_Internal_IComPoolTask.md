# Windows::Internal::ComTaskPoolHandler::Start(Windows::Internal::IComPoolTask *)

- ea: `0x140012628`
- end: `0x140012678`
- name: `?Start@ComTaskPoolHandler@Internal@Windows@@QEAAJPEAUIComPoolTask@23@@Z`
- size: `80`
- prototype: `__int64 __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this, struct Windows::Internal::IComPoolTask *)`
- caller_count: `4`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140012580`
- `0x140035a60`
- `0x140035b10`
- `0x14003f900`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140012638`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140012638`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x140012660`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x140012660`

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
0x140012628  mov     [rsp+arg_0], rbx
0x14001262d  push    rdi
0x14001262e  sub     rsp, 30h
0x140012632  mov     rbx, rdx
0x140012635  mov     rdi, rcx
0x140012638  call    cs:__imp_GetCurrentThreadId
0x14001263f  nop     dword ptr [rax+rax+00h]
0x140012644  mov     edx, [rdi+4]
0x140012647  xor     r9d, r9d
0x14001264a  mov     ecx, [rdi]
0x14001264c  mov     r8d, eax
0x14001264f  mov     [rsp+38h+var_10], 0
0x140012658  mov     [rdi+8], eax
0x14001265b  mov     [rsp+38h+var_18], rbx
0x140012660  call    cs:__imp_SHTaskPoolQueueTask
0x140012667  nop     dword ptr [rax+rax+00h]
0x14001266c  mov     rbx, [rsp+38h+arg_0]
0x140012671  add     rsp, 30h
0x140012675  pop     rdi
0x140012676  retn
```
