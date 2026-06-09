# CBaseRPCTimeout::Disarm(void)

- ea: `0x1800283f0`
- end: `0x180028433`
- name: `?Disarm@CBaseRPCTimeout@@QEAAXXZ`
- size: `67`
- prototype: `void __fastcall(CBaseRPCTimeout *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011c10`
- `0x18002834c`
- `0x180028358`

## callees

- `0x1800283f0`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180028423`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180028423`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18002840e`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18002840e`

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
0x1800283f0  push    rbx
0x1800283f2  sub     rsp, 20h
0x1800283f6  cmp     dword ptr [rcx+8], 0
0x1800283fa  mov     rbx, rcx
0x1800283fd  jge     short loc_180028405
0x1800283ff  add     rsp, 20h
0x180028403  pop     rbx
0x180028404  retn
0x180028405  mov     dword ptr [rcx+8], 80004005h
0x18002840c  xor     ecx, ecx; pReserved
0x18002840e  call    cs:__imp_CoDisableCallCancellation
0x180028414  mov     rdx, [rbx+10h]; Timer
0x180028418  test    rdx, rdx
0x18002841b  jz      short loc_1800283FF
0x18002841d  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180028421  xor     ecx, ecx; TimerQueue
0x180028423  call    cs:__imp_DeleteTimerQueueTimer
0x180028429  mov     qword ptr [rbx+10h], 0
0x180028431  jmp     short loc_1800283FF
```
