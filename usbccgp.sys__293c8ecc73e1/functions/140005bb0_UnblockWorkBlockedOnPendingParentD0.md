# UnblockWorkBlockedOnPendingParentD0

- ea: `0x140005bb0`
- end: `0x140005d9a`
- name: `UnblockWorkBlockedOnPendingParentD0`
- size: `490`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400046c0`
- `0x140007c38`

## callees

- `0x140004b08`
- `0x140005bb0`
- `0x140005da0`
- `0x140005eb0`
- `0x140006834`
- `0x140013eb0`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x140005c6e`
- `ntoskrnl!KeReadStateEvent` at `0x140005c6e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005c07`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005c07`
- `ntoskrnl!KeGetCurrentIrql` at `0x140005bca`
- `ntoskrnl!KeGetCurrentIrql` at `0x140005bca`
- `ntoskrnl!PoFxNotifySurprisePowerOn` at `0x140005d2d`
- `ntoskrnl!PoFxNotifySurprisePowerOn` at `0x140005d2d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005c9d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005c9d`
- `ntoskrnl!KeSetEvent` at `0x140005c29`
- `ntoskrnl!KeSetEvent` at `0x140005c29`

## pseudocode

```c
void __fastcall UnblockWorkBlockedOnPendingParentD0(char *Context)
{
  char v2; // r12
  char v3; // r14
  __int64 v4; // r15
  KIRQL CurrentIrql; // si
  _DWORD *v6; // rcx
  KIRQL v7; // al
  KIRQL v8; // r13
  int v9; // ecx
  char v10; // di
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdi
  __int64 v14; // rdx
  int v15; // edx

  v2 = 0;
  v3 = 0;
  v4 = 0;
  CurrentIrql = KeGetCurrentIrql();
  UnblockAllPendedPdoD0Irps(Context);
  if ( *((_DWORD *)Context + 144) == 2 )
  {
    v6 = (_DWORD *)*((_QWORD *)Context + 16);
    if ( *v6 )
    {
      v13 = 0;
      do
      {
        v14 = *(_QWORD *)(*(_QWORD *)&v6[2 * v13 + 2] + 64LL);
        if ( Context[1362] )
          *(_BYTE *)(*(_QWORD *)(v14 + 392) + 59LL) = 0;
        if ( *(_DWORD *)(v14 + 24) != 1 )
        {
          *(_DWORD *)(v14 + 120) = 2;
          PoFxNotifySurprisePowerOn();
        }
        v6 = (_DWORD *)*((_QWORD *)Context + 16);
        v13 = (unsigned int)(v13 + 1);
      }
      while ( (unsigned int)v13 < *v6 );
    }
  }
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 43);
  *((_DWORD *)Context + 84) = 0;
  v8 = v7;
  KeSetEvent((PRKEVENT)Context + 13, 0, 0);
  v9 = *((_DWORD *)Context + 307);
  if ( (v9 & 4) != 0 )
  {
    v9 &= ~4u;
    *((_DWORD *)Context + 307) = v9;
    if ( CurrentIrql )
    {
      v9 |= 1u;
      *((_DWORD *)Context + 307) = v9;
    }
    else
    {
      v2 = 1;
    }
  }
  if ( (v9 & 8) != 0 )
  {
    v9 &= ~8u;
    v10 = 1;
    *((_DWORD *)Context + 307) = v9;
  }
  else
  {
    v10 = 0;
  }
  if ( (v9 & 0x10) != 0 )
  {
    *((_DWORD *)Context + 307) = v9 & 0xFFFFFFEF;
    if ( KeReadStateEvent((PRKEVENT)(Context + 416)) )
    {
      v4 = *((_QWORD *)Context + 154);
      v3 = 1;
      *((_QWORD *)Context + 154) = 0;
    }
    else
    {
      *((_DWORD *)Context + 307) |= 0x20u;
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)Context + 43, v8);
  if ( v2 )
  {
    LOBYTE(v11) = 1;
    EnableIdleTimer(Context, v11, 1464816203);
  }
  if ( v10 )
  {
    if ( Context[1362] )
    {
      if ( *((_DWORD *)Context + 144) != 2 )
      {
        FinishWaitWakeCompletionForFunctionSuspend(Context);
        goto LABEL_12;
      }
      v15 = -1073741536;
    }
    else
    {
      v15 = 0;
    }
    CompleteAllPdoWaitWakeIrps(Context, v15);
  }
LABEL_12:
  if ( v3 )
    IdleFinishCompletionWorker((__int64)Context, v4, v12);
}

```

## disassembly

```asm
0x140005bb0  push    rbx
0x140005bb2  push    rbp
0x140005bb3  push    rsi
0x140005bb4  push    rdi
0x140005bb5  push    r12
0x140005bb7  push    r13
0x140005bb9  push    r14
0x140005bbb  push    r15
0x140005bbd  sub     rsp, 28h
0x140005bc1  mov     rbx, rcx
0x140005bc4  xor     r12b, r12b
0x140005bc7  xor     r14b, r14b
0x140005bca  call    cs:__imp_KeGetCurrentIrql
0x140005bd1  nop     dword ptr [rax+rax+00h]
0x140005bd6  mov     rcx, rbx
0x140005bd9  xor     r15d, r15d
0x140005bdc  mov     sil, al
0x140005bdf  call    UnblockAllPendedPdoD0Irps
0x140005be4  cmp     dword ptr [rbx+240h], 2
0x140005beb  jnz     short loc_140005BFD
0x140005bed  mov     rcx, [rbx+80h]
0x140005bf4  cmp     [rcx], r15d
0x140005bf7  ja      loc_140005CE5
0x140005bfd  lea     rbp, [rbx+158h]
0x140005c04  mov     rcx, rbp; SpinLock
0x140005c07  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005c0e  nop     dword ptr [rax+rax+00h]
0x140005c13  lea     rcx, [rbx+138h]; Event
0x140005c1a  mov     [rbx+150h], r15d
0x140005c21  xor     r8d, r8d; Wait
0x140005c24  xor     edx, edx; Increment
0x140005c26  mov     r13b, al
0x140005c29  call    cs:__imp_KeSetEvent
0x140005c30  nop     dword ptr [rax+rax+00h]
0x140005c35  mov     ecx, [rbx+4CCh]
0x140005c3b  test    cl, 4
0x140005c3e  jnz     loc_140005D3B
0x140005c44  test    cl, 8
0x140005c47  jz      loc_140005D51
0x140005c4d  and     ecx, 0FFFFFFF7h
0x140005c50  mov     dil, 1
0x140005c53  mov     [rbx+4CCh], ecx
0x140005c59  test    cl, 10h
0x140005c5c  jz      short loc_140005C97
0x140005c5e  and     ecx, 0FFFFFFEFh
0x140005c61  mov     [rbx+4CCh], ecx
0x140005c67  lea     rcx, [rbx+1A0h]; Event
0x140005c6e  call    cs:__imp_KeReadStateEvent
0x140005c75  nop     dword ptr [rax+rax+00h]
0x140005c7a  test    eax, eax
0x140005c7c  jz      loc_140005D59
0x140005c82  mov     r15, [rbx+4D0h]
0x140005c89  mov     r14b, 1
0x140005c8c  mov     qword ptr [rbx+4D0h], 0
0x140005c97  mov     dl, r13b; NewIrql
0x140005c9a  mov     rcx, rbp; SpinLock
0x140005c9d  call    cs:__imp_KeReleaseSpinLock
0x140005ca4  nop     dword ptr [rax+rax+00h]
0x140005ca9  test    r12b, r12b
0x140005cac  jz      short loc_140005CBE
0x140005cae  mov     r8d, 574F524Bh
0x140005cb4  mov     dl, 1
0x140005cb6  mov     rcx, rbx
0x140005cb9  call    EnableIdleTimer
0x140005cbe  test    dil, dil
0x140005cc1  jnz     short loc_140005D11
0x140005cc3  test    r14b, r14b
0x140005cc6  jz      short loc_140005CD3
0x140005cc8  mov     rdx, r15
0x140005ccb  mov     rcx, rbx
0x140005cce  call    IdleFinishCompletionWorker
0x140005cd3  add     rsp, 28h
0x140005cd7  pop     r15
0x140005cd9  pop     r14
0x140005cdb  pop     r13
0x140005cdd  pop     r12
0x140005cdf  pop     rdi
0x140005ce0  pop     rsi
0x140005ce1  pop     rbp
0x140005ce2  pop     rbx
0x140005ce3  retn
0x140005ce5  xor     edi, edi
0x140005ce7  mov     rcx, [rcx+rdi*8+8]
0x140005cec  mov     rdx, [rcx+40h]
0x140005cf0  cmp     [rbx+552h], r12b
0x140005cf7  jnz     short loc_140005D65
0x140005cf9  cmp     dword ptr [rdx+18h], 1
0x140005cfd  jnz     short loc_140005D26
0x140005cff  mov     rcx, [rbx+80h]
0x140005d06  inc     edi
0x140005d08  cmp     edi, [rcx]
0x140005d0a  jb      short loc_140005CE7
0x140005d0c  jmp     loc_140005BFD
0x140005d11  cmp     byte ptr [rbx+552h], 0
0x140005d18  mov     rcx, rbx; Context
0x140005d1b  jnz     short loc_140005D80
0x140005d1d  xor     edx, edx
0x140005d1f  call    CompleteAllPdoWaitWakeIrps
0x140005d24  jmp     short loc_140005CC3
0x140005d26  mov     dword ptr [rdx+78h], 2
0x140005d2d  call    cs:__imp_PoFxNotifySurprisePowerOn
0x140005d34  nop     dword ptr [rax+rax+00h]
0x140005d39  jmp     short loc_140005CFF
0x140005d3b  and     ecx, 0FFFFFFFBh
0x140005d3e  mov     [rbx+4CCh], ecx
0x140005d44  test    sil, sil
0x140005d47  jnz     short loc_140005D72
0x140005d49  mov     r12b, 1
0x140005d4c  jmp     loc_140005C44
0x140005d51  xor     dil, dil
0x140005d54  jmp     loc_140005C59
0x140005d59  or      dword ptr [rbx+4CCh], 20h
0x140005d60  jmp     loc_140005C97
0x140005d65  mov     rax, [rdx+188h]
0x140005d6c  mov     [rax+3Bh], r12b
0x140005d70  jmp     short loc_140005CF9
0x140005d72  or      ecx, 1
0x140005d75  mov     [rbx+4CCh], ecx
0x140005d7b  jmp     loc_140005C44
0x140005d80  cmp     dword ptr [rbx+240h], 2
0x140005d87  jz      short loc_140005D93
0x140005d89  call    FinishWaitWakeCompletionForFunctionSuspend
0x140005d8e  jmp     loc_140005CC3
0x140005d93  mov     edx, 0C0000120h
0x140005d98  jmp     short loc_140005D1F
```
