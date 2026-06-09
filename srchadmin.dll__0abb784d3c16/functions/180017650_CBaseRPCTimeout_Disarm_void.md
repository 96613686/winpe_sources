# CBaseRPCTimeout::Disarm(void)

- ea: `0x180017650`
- end: `0x180017691`
- name: `?Disarm@CBaseRPCTimeout@@QEAAXXZ`
- size: `65`
- prototype: `void __fastcall(CBaseRPCTimeout *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001754c`
- `0x180017644`
- `0x180018730`

## callees

- `0x180017650`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180017668`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180017668`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18001767d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18001767d`

## pseudocode

```c
void __fastcall CBaseRPCTimeout::Disarm(CBaseRPCTimeout *this)
{
  void *v2; // rdx

  if ( *((int *)this + 2) >= 0 )
  {
    *((_DWORD *)this + 2) = -2147467259;
    CoDisableCallCancellation(0);
    v2 = (void *)*((_QWORD *)this + 2);
    if ( v2 )
    {
      DeleteTimerQueueTimer(0, v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      *((_QWORD *)this + 2) = 0;
    }
  }
}

```

## disassembly

```asm
0x180017650  push    rbx
0x180017652  sub     rsp, 20h
0x180017656  cmp     dword ptr [rcx+8], 0
0x18001765a  mov     rbx, rcx
0x18001765d  jl      short loc_18001768B
0x18001765f  mov     dword ptr [rcx+8], 80004005h
0x180017666  xor     ecx, ecx; pReserved
0x180017668  call    cs:__imp_CoDisableCallCancellation
0x18001766e  mov     rdx, [rbx+10h]; Timer
0x180017672  test    rdx, rdx
0x180017675  jz      short loc_18001768B
0x180017677  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18001767b  xor     ecx, ecx; TimerQueue
0x18001767d  call    cs:__imp_DeleteTimerQueueTimer
0x180017683  mov     qword ptr [rbx+10h], 0
0x18001768b  add     rsp, 20h
0x18001768f  pop     rbx
0x180017690  retn
```
