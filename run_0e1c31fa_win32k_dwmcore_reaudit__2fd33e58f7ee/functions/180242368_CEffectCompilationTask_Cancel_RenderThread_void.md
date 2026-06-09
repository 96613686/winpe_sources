# CEffectCompilationTask::Cancel_RenderThread(void)

- ea: `0x180242368`
- end: `0x1802423b2`
- name: `?Cancel_RenderThread@CEffectCompilationTask@@AEAAXXZ`
- size: `74`
- prototype: `void __fastcall(CEffectCompilationTask *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18021de14`
- `0x1802344c8`

## callees

- `0x180154a90`
- `0x180242368`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180242389`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180242389`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18024237f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18024237f`

## pseudocode

```c
void __fastcall CEffectCompilationTask::Cancel_RenderThread(CEffectCompilationTask *this)
{
  struct _TP_WORK *v2; // rcx
  CEffectCompilationService *v3; // rcx

  v2 = (struct _TP_WORK *)*((_QWORD *)this + 8);
  if ( v2 )
  {
    WaitForThreadpoolWorkCallbacks(v2, 1);
    CloseThreadpoolWork(*((PTP_WORK *)this + 8));
    *((_QWORD *)this + 8) = 0;
  }
  v3 = (CEffectCompilationService *)*((_QWORD *)this + 2);
  *((_DWORD *)this + 18) = 1;
  CEffectCompilationService::OnTaskCompleted_AnyThread(v3, this, 1);
}

```

## disassembly

```asm
0x180242368  push    rbx
0x18024236a  sub     rsp, 20h
0x18024236e  mov     rbx, rcx
0x180242371  mov     rcx, [rcx+40h]; pwk
0x180242375  test    rcx, rcx
0x180242378  jz      short loc_180242397
0x18024237a  mov     edx, 1; fCancelPendingCallbacks
0x18024237f  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180242385  mov     rcx, [rbx+40h]; pwk
0x180242389  call    cs:__imp_CloseThreadpoolWork
0x18024238f  mov     qword ptr [rbx+40h], 0
0x180242397  mov     rcx, [rbx+10h]; this
0x18024239b  mov     r8b, 1; bool
0x18024239e  mov     rdx, rbx; struct CEffectCompilationTask *
0x1802423a1  mov     dword ptr [rbx+48h], 1
0x1802423a8  add     rsp, 20h
0x1802423ac  pop     rbx
0x1802423ad  jmp     ?OnTaskCompleted_AnyThread@CEffectCompilationService@@AEAAXPEAVCEffectCompilationTask@@_N@Z; CEffectCompilationService::OnTaskCompleted_AnyThread(CEffectCompilationTask *,bool)
```
