# WS_PrepareDeactivateAddress(void *)

- ea: `0x1800c61a0`
- end: `0x1800c62a5`
- name: `?WS_PrepareDeactivateAddress@@YAJPEAX@Z`
- size: `261`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180021ce0`
- `0x180060e18`
- `0x1800c61a0`

## import_xrefs

- `KERNELBASE!Sleep` at `0x1800c6257`
- `KERNELBASE!Sleep` at `0x1800c6257`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800c6284`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800c6284`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800c6272`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800c6272`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c61f4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c61f4`
- `WS2_32!__imp_closesocket` at `0x1800c621b`
- `WS2_32!__imp_closesocket` at `0x1800c621b`

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
0x1800c61a0  mov     [rsp+arg_0], rbx
0x1800c61a5  mov     [rsp+arg_8], rsi
0x1800c61aa  push    rdi
0x1800c61ab  sub     rsp, 40h
0x1800c61af  mov     rbx, rcx
0x1800c61b2  mov     rdi, rcx
0x1800c61b5  test    rcx, rcx
0x1800c61b8  jz      loc_1800C6293
0x1800c61be  lea     rcx, [rdi+78h]; this
0x1800c61c2  call    ?Lock@CSpinLock@@QEAAXXZ; CSpinLock::Lock(void)
0x1800c61c7  cmp     dword ptr [rdi+40h], 2
0x1800c61cb  jz      short loc_1800C6221
0x1800c61cd  mov     r9, rdi; void *
0x1800c61d0  mov     [rsp+48h+var_28], 0; unsigned __int64
0x1800c61d9  mov     r8, rdi; void *
0x1800c61dc  mov     dl, 64h ; 'd'; unsigned __int8
0x1800c61de  mov     cl, 44h ; 'D'; unsigned __int8
0x1800c61e0  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x1800c61e5  mov     rcx, [rdi+68h]
0x1800c61e9  xor     r9d, r9d; msWindowLength
0x1800c61ec  xor     r8d, r8d; msPeriod
0x1800c61ef  xor     edx, edx; pftDueTime
0x1800c61f1  mov     rcx, [rcx]; pti
0x1800c61f4  call    cs:__imp_SetThreadpoolTimer
0x1800c61fa  mov     rcx, [rdi+0C8h]; s
0x1800c6201  mov     dword ptr [rdi+0C0h], 0
0x1800c620b  mov     qword ptr [rdi+0C8h], 0
0x1800c6216  test    rcx, rcx
0x1800c6219  jz      short loc_1800C6221
0x1800c621b  call    cs:__imp_closesocket
0x1800c6221  mov     edx, [rdi+78h]
0x1800c6224  mov     r8, [rdi+58h]
0x1800c6228  add     edx, 0F0000000h
0x1800c622e  mov     eax, edx
0x1800c6230  and     eax, 0F0000000h
0x1800c6235  neg     eax
0x1800c6237  sbb     ecx, ecx
0x1800c6239  and     ecx, edx
0x1800c623b  xchg    ecx, [rdi+78h]
0x1800c623e  mov     rdi, r8
0x1800c6241  test    r8, r8
0x1800c6244  jnz     loc_1800C61BE
0x1800c624a  cmp     dword ptr [rbx+40h], 2
0x1800c624e  jz      short loc_1800C628A
0x1800c6250  jmp     short loc_1800C625D
0x1800c6252  mov     ecx, 0Ah; dwMilliseconds
0x1800c6257  call    cs:__imp_Sleep
0x1800c625d  cmp     dword ptr [rbx+0C4h], 0
0x1800c6264  jnz     short loc_1800C6252
0x1800c6266  mov     rcx, [rbx+68h]
0x1800c626a  mov     edx, 1; fCancelPendingCallbacks
0x1800c626f  mov     rcx, [rcx]; pti
0x1800c6272  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800c6278  mov     rcx, [rbx+298h]
0x1800c627f  xor     edx, edx; fCancelPendingCallbacks
0x1800c6281  mov     rcx, [rcx]; pio
0x1800c6284  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x1800c628a  mov     rbx, [rbx+58h]
0x1800c628e  test    rbx, rbx
0x1800c6291  jnz     short loc_1800C624A
0x1800c6293  mov     rbx, [rsp+48h+arg_0]
0x1800c6298  xor     eax, eax
0x1800c629a  mov     rsi, [rsp+48h+arg_8]
0x1800c629f  add     rsp, 40h
0x1800c62a3  pop     rdi
0x1800c62a4  retn
```
