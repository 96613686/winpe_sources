# RPC_THREAD_POOL::TrySubmitWork(void (*)(_TP_CALLBACK_INSTANCE *,void *),void *)

- ea: `0x18001e91c`
- end: `0x18001e95c`
- name: `?TrySubmitWork@RPC_THREAD_POOL@@SAJP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z1@Z`
- size: `64`
- prototype: `__int64 __fastcall(PTP_SIMPLE_CALLBACK pfns, PVOID pv)`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x180003800`
- `0x1800038a0`
- `0x180003a20`
- `0x180003a60`
- `0x180003bd0`
- `0x180007f88`
- `0x180009030`
- `0x1800091ec`
- `0x1800094a0`
- `0x180010900`
- `0x180010920`
- `0x180011930`
- `0x180013200`
- `0x1800189a0`
- `0x18001a568`
- `0x18001b2b0`

## callees

- `0x18001e7b4`
- `0x18001e91c`

## import_xrefs

- `KERNEL32!TrySubmitThreadpoolCallback` at `0x18001e942`
- `KERNEL32!TrySubmitThreadpoolCallback` at `0x18001e942`

## pseudocode

```c
__int64 __fastcall RPC_THREAD_POOL::TrySubmitWork(PTP_SIMPLE_CALLBACK pfns, PVOID pv)
{
  __int64 result; // rax

  result = RPC_THREAD_POOL::InitializeCallbackEnvironmentIfNecessary();
  if ( !(_DWORD)result )
    return !TrySubmitThreadpoolCallback(pfns, pv, RPC_THREAD_POOL::CallbackEnvironment) ? 0xE : 0;
  return result;
}

```

## disassembly

```asm
0x18001e91c  mov     [rsp+arg_0], rbx
0x18001e921  push    rdi
0x18001e922  sub     rsp, 20h
0x18001e926  mov     rbx, rdx
0x18001e929  mov     rdi, rcx
0x18001e92c  call    ?InitializeCallbackEnvironmentIfNecessary@RPC_THREAD_POOL@@CAJXZ; RPC_THREAD_POOL::InitializeCallbackEnvironmentIfNecessary(void)
0x18001e931  test    eax, eax
0x18001e933  jnz     short loc_18001E951
0x18001e935  mov     r8, cs:?CallbackEnvironment@RPC_THREAD_POOL@@0REAU_TP_CALLBACK_ENVIRON_V3@@EA; pcbe
0x18001e93c  mov     rdx, rbx; pv
0x18001e93f  mov     rcx, rdi; pfns
0x18001e942  call    cs:__imp_TrySubmitThreadpoolCallback
0x18001e948  neg     eax
0x18001e94a  sbb     eax, eax
0x18001e94c  not     eax
0x18001e94e  and     eax, 0Eh
0x18001e951  mov     rbx, [rsp+28h+arg_0]
0x18001e956  add     rsp, 20h
0x18001e95a  pop     rdi
0x18001e95b  retn
```
