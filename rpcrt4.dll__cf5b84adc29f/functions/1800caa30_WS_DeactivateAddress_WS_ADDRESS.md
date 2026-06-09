# WS_DeactivateAddress(WS_ADDRESS *)

- ea: `0x1800caa30`
- end: `0x1800cab67`
- name: `?WS_DeactivateAddress@@YAXPEAUWS_ADDRESS@@@Z`
- size: `311`
- prototype: `void __fastcall(struct WS_ADDRESS *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18009c5b0`
- `0x1800cbf60`

## callees

- `0x180064e3c`
- `0x180081cf4`
- `0x180096d3c`
- `0x1800caa30`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800cab1f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800cab1f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800caafe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800caafe`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800caac7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800caac7`
- `WS2_32!__imp_closesocket` at `0x1800cab3b`
- `WS2_32!__imp_closesocket` at `0x1800cab4f`
- `WS2_32!__imp_closesocket` at `0x1800cab3b`
- `WS2_32!__imp_closesocket` at `0x1800cab4f`

## pseudocode

```c
void __fastcall WS_DeactivateAddress(struct WS_ADDRESS *a1)
{
  SOCKET v2; // r14
  SOCKET v3; // rbp
  signed __int32 v4; // r8d
  PTP_TIMER *v5; // rsi
  PTP_IO *v6; // rdi
  unsigned int v7; // edx
  unsigned int v8; // edx

  if ( *((_DWORD *)a1 + 3) == 1 || *((_DWORD *)a1 + 3) == 6 || *((_DWORD *)a1 + 3) == 9 || *((_DWORD *)a1 + 3) == 12 )
  {
    v2 = *((_QWORD *)a1 + 25);
    v3 = *((_QWORD *)a1 + 26);
    CSpinLock::Lock((struct WS_ADDRESS *)((char *)a1 + 120));
    *((_QWORD *)a1 + 25) = 0;
    *((_QWORD *)a1 + 26) = 0;
    v4 = _InterlockedIncrement((volatile signed __int32 *)a1 + 4);
    _InterlockedExchange(
      (volatile __int32 *)a1 + 30,
      ((*((_DWORD *)a1 + 30) - 0x10000000) & 0xF0000000) != 0 ? *((_DWORD *)a1 + 30) - 0x10000000 : 0);
    if ( v4 == 1 )
    {
      SetThreadpoolTimer(**((PTP_TIMER **)a1 + 13), 0, 0, 0);
      v5 = (PTP_TIMER *)*((_QWORD *)a1 + 13);
      v6 = (PTP_IO *)*((_QWORD *)a1 + 83);
      *((_QWORD *)a1 + 13) = 0;
      *((_QWORD *)a1 + 83) = 0;
      if ( v5 )
      {
        WaitForThreadpoolTimerCallbacks(*v5, 1);
        RPC_THREAD_POOL_TIMER::`scalar deleting destructor'((RPC_THREAD_POOL_TIMER *)v5, v7);
      }
      if ( v6 )
      {
        WaitForThreadpoolIoCallbacks(*v6, 1);
        RPC_THREAD_POOL_IO::`scalar deleting destructor'((RPC_THREAD_POOL_IO *)v6, v8);
      }
      if ( v2 )
        closesocket(v2);
      if ( v3 )
        closesocket(v3);
    }
  }
}

```

## disassembly

```asm
0x1800caa30  push    rbx
0x1800caa32  push    rbp
0x1800caa33  push    rsi
0x1800caa34  push    rdi
0x1800caa35  push    r14
0x1800caa37  sub     rsp, 20h
0x1800caa3b  mov     edx, [rcx+0Ch]
0x1800caa3e  mov     rbx, rcx
0x1800caa41  sub     edx, 1
0x1800caa44  jz      short loc_1800CAA59
0x1800caa46  sub     edx, 5
0x1800caa49  jz      short loc_1800CAA59
0x1800caa4b  sub     edx, 3
0x1800caa4e  jz      short loc_1800CAA59
0x1800caa50  cmp     edx, 3
0x1800caa53  jnz     loc_1800CAB5B
0x1800caa59  mov     r14, [rcx+0C8h]
0x1800caa60  mov     rbp, [rcx+0D0h]
0x1800caa67  add     rcx, 78h ; 'x'; this
0x1800caa6b  call    ?Lock@CSpinLock@@QEAAXXZ; CSpinLock::Lock(void)
0x1800caa70  mov     r8d, 1
0x1800caa76  mov     qword ptr [rbx+0C8h], 0
0x1800caa81  mov     qword ptr [rbx+0D0h], 0
0x1800caa8c  lock xadd [rbx+10h], r8d
0x1800caa92  mov     edx, [rbx+78h]
0x1800caa95  inc     r8d
0x1800caa98  add     edx, 0F0000000h
0x1800caa9e  mov     eax, edx
0x1800caaa0  and     eax, 0F0000000h
0x1800caaa5  neg     eax
0x1800caaa7  sbb     ecx, ecx
0x1800caaa9  and     ecx, edx
0x1800caaab  xchg    ecx, [rbx+78h]
0x1800caaae  cmp     r8d, 1
0x1800caab2  jnz     loc_1800CAB5B
0x1800caab8  mov     rcx, [rbx+68h]
0x1800caabc  xor     r9d, r9d; msWindowLength
0x1800caabf  xor     r8d, r8d; msPeriod
0x1800caac2  xor     edx, edx; pftDueTime
0x1800caac4  mov     rcx, [rcx]; pti
0x1800caac7  call    cs:__imp_SetThreadpoolTimer
0x1800caace  nop     dword ptr [rax+rax+00h]
0x1800caad3  mov     rsi, [rbx+68h]
0x1800caad7  mov     rdi, [rbx+298h]
0x1800caade  mov     qword ptr [rbx+68h], 0
0x1800caae6  mov     qword ptr [rbx+298h], 0
0x1800caaf1  test    rsi, rsi
0x1800caaf4  jz      short loc_1800CAB12
0x1800caaf6  mov     rcx, [rsi]; pti
0x1800caaf9  mov     edx, 1; fCancelPendingCallbacks
0x1800caafe  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800cab05  nop     dword ptr [rax+rax+00h]
0x1800cab0a  mov     rcx, rsi; this
0x1800cab0d  call    ??_GRPC_THREAD_POOL_TIMER@@QEAAPEAXI@Z; RPC_THREAD_POOL_TIMER::`scalar deleting destructor'(uint)
0x1800cab12  test    rdi, rdi
0x1800cab15  jz      short loc_1800CAB33
0x1800cab17  mov     rcx, [rdi]; pio
0x1800cab1a  mov     edx, 1; fCancelPendingCallbacks
0x1800cab1f  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x1800cab26  nop     dword ptr [rax+rax+00h]
0x1800cab2b  mov     rcx, rdi; this
0x1800cab2e  call    ??_GRPC_THREAD_POOL_IO@@QEAAPEAXI@Z; RPC_THREAD_POOL_IO::`scalar deleting destructor'(uint)
0x1800cab33  test    r14, r14
0x1800cab36  jz      short loc_1800CAB47
0x1800cab38  mov     rcx, r14; s
0x1800cab3b  call    cs:__imp_closesocket
0x1800cab42  nop     dword ptr [rax+rax+00h]
0x1800cab47  test    rbp, rbp
0x1800cab4a  jz      short loc_1800CAB5B
0x1800cab4c  mov     rcx, rbp; s
0x1800cab4f  call    cs:__imp_closesocket
0x1800cab56  nop     dword ptr [rax+rax+00h]
0x1800cab5b  add     rsp, 20h
0x1800cab5f  pop     r14
0x1800cab61  pop     rdi
0x1800cab62  pop     rsi
0x1800cab63  pop     rbp
0x1800cab64  pop     rbx
0x1800cab65  retn
```
