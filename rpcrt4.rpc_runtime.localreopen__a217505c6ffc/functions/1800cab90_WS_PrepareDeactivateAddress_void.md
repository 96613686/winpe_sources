# WS_PrepareDeactivateAddress(void *)

- ea: `0x1800cab90`
- end: `0x1800cacb4`
- name: `?WS_PrepareDeactivateAddress@@YAJPEAX@Z`
- size: `292`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180022e80`
- `0x180064e3c`
- `0x1800cab90`

## import_xrefs

- `KERNELBASE!Sleep` at `0x1800cac53`
- `KERNELBASE!Sleep` at `0x1800cac53`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800cac8c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800cac8c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800cac74`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800cac74`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800cabe4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800cabe4`
- `WS2_32!__imp_closesocket` at `0x1800cac11`
- `WS2_32!__imp_closesocket` at `0x1800cac11`

## pseudocode

```c
__int64 __fastcall WS_PrepareDeactivateAddress(char *a1)
{
  void *v1; // rbx
  char *v2; // rdi
  SOCKET v3; // rcx
  char *v4; // r8
  int v6; // [rsp+28h] [rbp-20h]
  int v7; // [rsp+30h] [rbp-18h]

  v1 = a1;
  v2 = a1;
  if ( a1 )
  {
    do
    {
      CSpinLock::Lock((CSpinLock *)(v2 + 120));
      if ( *((_DWORD *)v2 + 16) != 2 )
      {
        LogEvent(0x44u, 0x64u, v2, v2, 0, v6, v7);
        SetThreadpoolTimer(**((PTP_TIMER **)v2 + 13), 0, 0, 0);
        v3 = *((_QWORD *)v2 + 25);
        *((_DWORD *)v2 + 48) = 0;
        *((_QWORD *)v2 + 25) = 0;
        if ( v3 )
          closesocket(v3);
      }
      v4 = (char *)*((_QWORD *)v2 + 11);
      _InterlockedExchange(
        (volatile __int32 *)v2 + 30,
        ((*((_DWORD *)v2 + 30) - 0x10000000) & 0xF0000000) != 0 ? *((_DWORD *)v2 + 30) - 0x10000000 : 0);
      v2 = v4;
    }
    while ( v4 );
    do
    {
      if ( *((_DWORD *)v1 + 16) != 2 )
      {
        while ( *((_DWORD *)v1 + 49) )
          Sleep(0xAu);
        WaitForThreadpoolTimerCallbacks(**((PTP_TIMER **)v1 + 13), 1);
        WaitForThreadpoolIoCallbacks(**((PTP_IO **)v1 + 83), 0);
      }
      v1 = (void *)*((_QWORD *)v1 + 11);
    }
    while ( v1 );
  }
  return 0;
}

```

## disassembly

```asm
0x1800cab90  mov     [rsp+arg_0], rbx
0x1800cab95  mov     [rsp+arg_8], rsi
0x1800cab9a  push    rdi
0x1800cab9b  sub     rsp, 40h
0x1800cab9f  mov     rbx, rcx
0x1800caba2  mov     rdi, rcx
0x1800caba5  test    rcx, rcx
0x1800caba8  jz      loc_1800CACA1
0x1800cabae  lea     rcx, [rdi+78h]; this
0x1800cabb2  call    ?Lock@CSpinLock@@QEAAXXZ; CSpinLock::Lock(void)
0x1800cabb7  cmp     dword ptr [rdi+40h], 2
0x1800cabbb  jz      short loc_1800CAC1D
0x1800cabbd  mov     r9, rdi; void *
0x1800cabc0  mov     [rsp+48h+var_28], 0; unsigned __int64
0x1800cabc9  mov     r8, rdi; void *
0x1800cabcc  mov     dl, 64h ; 'd'; unsigned __int8
0x1800cabce  mov     cl, 44h ; 'D'; unsigned __int8
0x1800cabd0  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x1800cabd5  mov     rcx, [rdi+68h]
0x1800cabd9  xor     r9d, r9d; msWindowLength
0x1800cabdc  xor     r8d, r8d; msPeriod
0x1800cabdf  xor     edx, edx; pftDueTime
0x1800cabe1  mov     rcx, [rcx]; pti
0x1800cabe4  call    cs:__imp_SetThreadpoolTimer
0x1800cabeb  nop     dword ptr [rax+rax+00h]
0x1800cabf0  mov     rcx, [rdi+0C8h]; s
0x1800cabf7  mov     dword ptr [rdi+0C0h], 0
0x1800cac01  mov     qword ptr [rdi+0C8h], 0
0x1800cac0c  test    rcx, rcx
0x1800cac0f  jz      short loc_1800CAC1D
0x1800cac11  call    cs:__imp_closesocket
0x1800cac18  nop     dword ptr [rax+rax+00h]
0x1800cac1d  mov     edx, [rdi+78h]
0x1800cac20  mov     r8, [rdi+58h]
0x1800cac24  add     edx, 0F0000000h
0x1800cac2a  mov     eax, edx
0x1800cac2c  and     eax, 0F0000000h
0x1800cac31  neg     eax
0x1800cac33  sbb     ecx, ecx
0x1800cac35  and     ecx, edx
0x1800cac37  xchg    ecx, [rdi+78h]
0x1800cac3a  mov     rdi, r8
0x1800cac3d  test    r8, r8
0x1800cac40  jnz     loc_1800CABAE
0x1800cac46  cmp     dword ptr [rbx+40h], 2
0x1800cac4a  jz      short loc_1800CAC98
0x1800cac4c  jmp     short loc_1800CAC5F
0x1800cac4e  mov     ecx, 0Ah; dwMilliseconds
0x1800cac53  call    cs:__imp_Sleep
0x1800cac5a  nop     dword ptr [rax+rax+00h]
0x1800cac5f  cmp     dword ptr [rbx+0C4h], 0
0x1800cac66  jnz     short loc_1800CAC4E
0x1800cac68  mov     rcx, [rbx+68h]
0x1800cac6c  mov     edx, 1; fCancelPendingCallbacks
0x1800cac71  mov     rcx, [rcx]; pti
0x1800cac74  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800cac7b  nop     dword ptr [rax+rax+00h]
0x1800cac80  mov     rcx, [rbx+298h]
0x1800cac87  xor     edx, edx; fCancelPendingCallbacks
0x1800cac89  mov     rcx, [rcx]; pio
0x1800cac8c  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x1800cac93  nop     dword ptr [rax+rax+00h]
0x1800cac98  mov     rbx, [rbx+58h]
0x1800cac9c  test    rbx, rbx
0x1800cac9f  jnz     short loc_1800CAC46
0x1800caca1  mov     rbx, [rsp+48h+arg_0]
0x1800caca6  xor     eax, eax
0x1800caca8  mov     rsi, [rsp+48h+arg_8]
0x1800cacad  add     rsp, 40h
0x1800cacb1  pop     rdi
0x1800cacb2  retn
```
