# CThreadTask::Run(void)

- ea: `0x1800137e0`
- end: `0x180013850`
- name: `?Run@CThreadTask@@QEAAJXZ`
- size: `112`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `11`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180004290`
- `0x1800056c8`
- `0x180013650`
- `0x180013720`
- `0x180014fd0`
- `0x180018480`
- `0x1800293ac`
- `0x180029cdc`
- `0x180029dec`
- `0x180029eec`
- `0x18002e610`

## callees

- `0x1800137e0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001381e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001381e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800137fd`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800137fd`

## pseudocode

```c
signed int __fastcall CThreadTask::Run(volatile signed __int32 *Context)
{
  signed int result; // eax

  _InterlockedIncrement(Context + 2);
  if ( QueueUserWorkItem((LPTHREAD_START_ROUTINE)CThreadTask::_ThreadProc, (PVOID)Context, 0x10u) )
    return 0;
  if ( _InterlockedExchangeAdd(Context + 2, 0xFFFFFFFF) == 1 && Context )
    (**(void (__fastcall ***)(volatile signed __int32 *, __int64))Context)(Context, 1);
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800137e0  push    rbx
0x1800137e2  sub     rsp, 20h
0x1800137e6  mov     rbx, rcx
0x1800137e9  lock inc dword ptr [rcx+8]
0x1800137ed  mov     rdx, rcx; Context
0x1800137f0  mov     r8d, 10h; Flags
0x1800137f6  lea     rcx, ?_ThreadProc@CThreadTask@@CAKPEAX@Z; Function
0x1800137fd  call    cs:__imp_QueueUserWorkItem
0x180013803  test    eax, eax
0x180013805  jz      short loc_18001380F
0x180013807  xor     eax, eax
0x180013809  add     rsp, 20h
0x18001380d  pop     rbx
0x18001380e  retn
0x18001380f  mov     eax, 0FFFFFFFFh
0x180013814  lock xadd [rbx+8], eax
0x180013819  cmp     eax, 1
0x18001381c  jz      short loc_180013836
0x18001381e  call    cs:__imp_GetLastError
0x180013824  test    eax, eax
0x180013826  jle     short loc_180013809
0x180013828  movzx   eax, ax
0x18001382b  or      eax, 80070000h
0x180013830  add     rsp, 20h
0x180013834  pop     rbx
0x180013835  retn
0x180013836  test    rbx, rbx
0x180013839  jz      short loc_18001381E
0x18001383b  mov     rax, [rbx]
0x18001383e  mov     edx, 1
0x180013843  mov     rcx, rbx
0x180013846  mov     rax, [rax]
0x180013849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001384e  jmp     short loc_18001381E
```
