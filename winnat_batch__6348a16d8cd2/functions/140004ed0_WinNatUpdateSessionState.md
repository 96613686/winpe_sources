# WinNatUpdateSessionState

- ea: `0x140004ed0`
- end: `0x1400052c4`
- name: `WinNatUpdateSessionState`
- size: `1012`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140006c80`
- `0x14001d310`

## callees

- `0x140004ed0`
- `0x1400052d0`
- `0x140005714`
- `0x14000623c`
- `0x14000baf8`
- `0x14000c554`
- `0x14000caa0`
- `0x140019be8`
- `0x14001ab70`
- `0x14001b9e0`
- `0x14001ede0`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400052b3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400052b3`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140004f16`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140004f16`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000505c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000505c`
- `NETIO!RtlIndicateTimerWheelEntryTimerStart` at `0x140005284`
- `NETIO!RtlIndicateTimerWheelEntryTimerStart` at `0x140005284`

## pseudocode

```c
void __fastcall WinNatUpdateSessionState(__int64 a1, __int64 a2, unsigned int a3, unsigned __int8 a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // ecx
  int v12; // eax
  int v13; // ecx
  bool v14; // r15
  int v15; // r9d
  bool v16; // bp
  int v17; // ecx
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20; // r8d
  char v21; // dl
  int v22; // r9d
  int v23; // ecx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+70h] [rbp-D8h] BYREF
  _WORD v25[16]; // [rsp+88h] [rbp-C0h] BYREF
  _WORD v26[16]; // [rsp+A8h] [rbp-A0h] BYREF
  _OWORD v27[2]; // [rsp+C8h] [rbp-80h] BYREF
  _OWORD v28[2]; // [rsp+E8h] [rbp-60h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a2 + 240));
  if ( (*(_BYTE *)(a2 + 132) & 1) != 0 )
    goto LABEL_14;
  v11 = *(_DWORD *)(a2 + 120);
  if ( v11 == 6 )
  {
    WinNatUpdateTcpSessionState(a2, a3, a4);
    goto LABEL_4;
  }
  v17 = v11 - 1;
  if ( !v17 )
    goto LABEL_22;
  v18 = (unsigned int)(v17 - 16);
  if ( !(_DWORD)v18 )
  {
    WinNatUpdateUdpSessionState(a2, a4);
    goto LABEL_4;
  }
  if ( (_DWORD)v18 == 41 )
LABEL_22:
    WinNatUpdateIcmpSessionState(a2, a4);
  else
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v18, v8, v9, v10);
LABEL_4:
  if ( (Microsoft_Windows_WinNatEnableBits & 2) != 0 )
  {
    if ( dword_140026104 )
    {
      v19 = *(_QWORD *)(a2 + 88);
      memset(v26, 0, 28);
      memset(v28, 0, 28);
      memset(v25, 0, 28);
      memset(v27, 0, 28);
      WinNatCopyTransportAddrToSockAddr(v19, v26);
      WinNatCopyTransportAddrToSockAddr(*(_QWORD *)(a2 + 96), v28);
      WinNatCopyTransportAddrToSockAddr(*(_QWORD *)(a2 + 104), v25);
      WinNatCopyTransportAddrToSockAddr(*(_QWORD *)(a2 + 112), v27);
      if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 2) != 0 )
      {
        if ( (*(_BYTE *)(a2 + 132) & 1) != 0 )
          v21 = 0;
        else
          v21 = *(_DWORD *)(a2 + 136) - MEMORY[0xFFFFF78000000008] / 0x2710uLL / 0x3E8;
        v22 = 28;
        v23 = 28;
        if ( v25[0] == 2 )
          v23 = 16;
        if ( v26[0] == 2 )
          v22 = 16;
        McTemplateK0qbr0br0qbr3br3qqqq_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
          (unsigned int)WINNAT_SESSION_TIMER_UPDATE,
          v20,
          v22,
          (__int64)v26,
          (__int64)v28,
          v23,
          (__int64)v25,
          (__int64)v27,
          *(_DWORD *)(a2 + 120),
          v21,
          *(_DWORD *)(a2 + 248),
          *(_DWORD *)(a2 + 8));
      }
    }
  }
  v12 = *(_DWORD *)(a2 + 136);
  if ( !v12 )
    v12 = 1;
  v13 = *(_DWORD *)(a2 + 160);
  *(_DWORD *)(a2 + 164) = v12;
  v14 = !v13 || v12 - v13 < 0;
  v15 = *(_DWORD *)(a1 + 616);
  v16 = !v15 || *(_DWORD *)(a2 + 136) + -*(_DWORD *)(a1 + 620) - v15 < 0;
  if ( v14 || v16 )
  {
    RtlAcquireScalableWriteLockAtDpcLevel(a1 + 64, &LockHandle);
    if ( (*(_BYTE *)(a1 + 628) & 1) == 0 )
    {
      if ( v14 )
        RtlIndicateTimerWheelEntryTimerStart(*(_QWORD *)(a1 + 472), a2 + 144);
      if ( v16 )
      {
        WinNatIsTimerRestartNeeded(a1, a2);
        WinNatRestartSessionTimer(a1, *(unsigned int *)(a2 + 136));
      }
    }
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  }
LABEL_14:
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a2 + 240));
}

```

## disassembly

```asm
0x140004ed0  push    rbx
0x140004ed2  push    rbp
0x140004ed3  push    rsi
0x140004ed4  push    rdi
0x140004ed5  push    r14
0x140004ed7  sub     rsp, 120h
0x140004ede  mov     rax, cs:__security_cookie
0x140004ee5  xor     rax, rsp
0x140004ee8  mov     [rsp+148h+var_40], rax
0x140004ef0  mov     r14, rcx
0x140004ef3  xorps   xmm0, xmm0
0x140004ef6  xor     eax, eax
0x140004ef8  lea     rcx, [rdx+0F0h]; SpinLock
0x140004eff  movups  xmmword ptr [rsp+148h+LockHandle.LockQueue.Next], xmm0
0x140004f04  mov     qword ptr [rsp+148h+LockHandle.OldIrql], rax
0x140004f0c  movzx   edi, r9b
0x140004f10  mov     ebp, r8d
0x140004f13  mov     rbx, rdx
0x140004f16  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140004f1d  nop     dword ptr [rax+rax+00h]
0x140004f22  test    byte ptr [rbx+84h], 1
0x140004f29  jnz     loc_140005055
0x140004f2f  mov     ecx, [rbx+78h]
0x140004f32  mov     [rsp+148h+arg_10], r12
0x140004f3a  mov     [rsp+148h+var_30], r13
0x140004f42  mov     [rsp+148h+var_38], r15
0x140004f4a  cmp     ecx, 6
0x140004f4d  jnz     loc_140005097
0x140004f53  movzx   r8d, dil
0x140004f57  mov     edx, ebp
0x140004f59  mov     rcx, rbx
0x140004f5c  call    WinNatUpdateTcpSessionState
0x140004f61  test    cs:Microsoft_Windows_WinNatEnableBits, 2
0x140004f68  mov     rbp, 0FFFFF78000000008h
0x140004f72  mov     r12, 346DC5D63886594Bh
0x140004f7c  mov     r13, 624DD2F1A9FBE77h
0x140004f86  jnz     loc_1400050D2
0x140004f8c  mov     eax, [rbx+88h]
0x140004f92  mov     ecx, 1
0x140004f97  test    eax, eax
0x140004f99  cmovz   eax, ecx
0x140004f9c  mov     ecx, [rbx+0A0h]
0x140004fa2  mov     [rbx+0A4h], eax
0x140004fa8  test    ecx, ecx
0x140004faa  jnz     loc_140005087
0x140004fb0  mov     r15b, 1
0x140004fb3  mov     rcx, [rbp+0]
0x140004fb7  mov     rdx, [rbp+0]
0x140004fbb  mov     r9d, [r14+268h]
0x140004fc2  mov     r10d, [rbx+88h]
0x140004fc9  test    r9d, r9d
0x140004fcc  jz      loc_140005251
0x140004fd2  mov     rax, r12
0x140004fd5  mul     rdx
0x140004fd8  mov     rax, r13
0x140004fdb  mov     r8, rdx
0x140004fde  shr     r8, 0Bh
0x140004fe2  mul     r8
0x140004fe5  mov     rax, r12
0x140004fe8  sub     r8, rdx
0x140004feb  shr     r8, 1
0x140004fee  add     r8, rdx
0x140004ff1  mul     rcx
0x140004ff4  shr     r8, 9
0x140004ff8  mov     rax, r13
0x140004ffb  mov     rcx, rdx
0x140004ffe  shr     rcx, 0Bh
0x140005002  mul     rcx
0x140005005  sub     rcx, rdx
0x140005008  shr     rcx, 1
0x14000500b  add     rcx, rdx
0x14000500e  shr     rcx, 9
0x140005012  sub     r8d, ecx
0x140005015  sub     r8d, [r14+26Ch]
0x14000501c  sub     r8d, r9d
0x14000501f  add     r8d, r10d
0x140005022  js      loc_140005251
0x140005028  xor     bpl, bpl
0x14000502b  mov     r13, [rsp+148h+var_30]
0x140005033  mov     r12, [rsp+148h+arg_10]
0x14000503b  test    r15b, r15b
0x14000503e  jnz     loc_140005259
0x140005044  test    bpl, bpl
0x140005047  jnz     loc_140005259
0x14000504d  mov     r15, [rsp+148h+var_38]
0x140005055  lea     rcx, [rbx+0F0h]; SpinLock
0x14000505c  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140005063  nop     dword ptr [rax+rax+00h]
0x140005068  mov     rcx, [rsp+148h+var_40]
0x140005070  xor     rcx, rsp; StackCookie
0x140005073  call    __security_check_cookie
0x140005078  add     rsp, 120h
0x14000507f  pop     r14
0x140005081  pop     rdi
0x140005082  pop     rsi
0x140005083  pop     rbp
0x140005084  pop     rbx
0x140005085  retn
0x140005087  cmp     eax, ecx
0x140005089  js      loc_140004FB0
0x14000508f  xor     r15b, r15b
0x140005092  jmp     loc_140004FB3
0x140005097  sub     ecx, 1
0x14000509a  jz      short loc_1400050C1
0x14000509c  sub     ecx, 10h
0x14000509f  jnz     short loc_1400050B2
0x1400050a1  movzx   edx, dil
0x1400050a5  mov     rcx, rbx
0x1400050a8  call    WinNatUpdateUdpSessionState
0x1400050ad  jmp     loc_140004F61
0x1400050b2  cmp     ecx, 29h ; ')'
0x1400050b5  jz      short loc_1400050C1
0x1400050b7  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400050bc  jmp     loc_140004F61
0x1400050c1  movzx   edx, dil
0x1400050c5  mov     rcx, rbx
0x1400050c8  call    WinNatUpdateIcmpSessionState
0x1400050cd  jmp     loc_140004F61
0x1400050d2  cmp     cs:dword_140026104, 0
0x1400050d9  jz      loc_140004F8C
0x1400050df  mov     rcx, [rbx+58h]
0x1400050e3  lea     rdx, [rsp+148h+var_A0]
0x1400050eb  xorps   xmm0, xmm0
0x1400050ee  xorps   xmm1, xmm1
0x1400050f1  movups  xmmword ptr [rsp+148h+var_A0], xmm0
0x1400050f9  xor     eax, eax
0x1400050fb  movups  [rsp+148h+var_60], xmm1
0x140005103  movups  xmmword ptr [rsp+148h+var_C0], xmm0
0x14000510b  movups  [rsp+148h+var_80], xmm1
0x140005113  movups  xmmword ptr [rsp+148h+var_A0+0Ch], xmm0
0x14000511b  movups  [rsp+148h+var_60+0Ch], xmm1
0x140005123  movups  xmmword ptr [rsp+148h+var_C0+0Ch], xmm0
0x14000512b  movups  [rsp+148h+var_80+0Ch], xmm1
0x140005133  call    WinNatCopyTransportAddrToSockAddr
0x140005138  mov     rcx, [rbx+60h]
0x14000513c  lea     rdx, [rsp+148h+var_60]
0x140005144  call    WinNatCopyTransportAddrToSockAddr
0x140005149  mov     rcx, [rbx+68h]
0x14000514d  lea     rdx, [rsp+148h+var_C0]
0x140005155  call    WinNatCopyTransportAddrToSockAddr
0x14000515a  mov     rcx, [rbx+70h]
0x14000515e  lea     rdx, [rsp+148h+var_80]
0x140005166  call    WinNatCopyTransportAddrToSockAddr
0x14000516b  cmp     cs:dword_140026104, 1
0x140005172  jnz     loc_140004F8C
0x140005178  test    cs:Microsoft_Windows_WinNatEnableBits, 2
0x14000517f  jz      loc_140004F8C
0x140005185  test    byte ptr [rbx+84h], 1
0x14000518c  jz      short loc_140005192
0x14000518e  xor     edx, edx
0x140005190  jmp     short loc_1400051BE
0x140005192  mov     rcx, [rbp+0]
0x140005196  mov     rax, r12
0x140005199  mul     rcx
0x14000519c  mov     rax, r13
0x14000519f  mov     rcx, rdx
0x1400051a2  shr     rcx, 0Bh
0x1400051a6  mul     rcx
0x1400051a9  sub     rcx, rdx
0x1400051ac  shr     rcx, 1
0x1400051af  add     rcx, rdx
0x1400051b2  mov     edx, [rbx+88h]
0x1400051b8  shr     rcx, 9
0x1400051bc  sub     edx, ecx
0x1400051be  cmp     [rsp+148h+var_C0], 2
0x1400051c7  mov     eax, 10h
0x1400051cc  mov     r9d, 1Ch
0x1400051d2  mov     ecx, r9d
0x1400051d5  cmovz   ecx, eax
0x1400051d8  cmp     [rsp+148h+var_A0], 2
0x1400051e1  cmovz   r9d, eax
0x1400051e5  mov     eax, [rbx+8]
0x1400051e8  mov     [rsp+148h+var_E8], eax
0x1400051ec  mov     eax, [rbx+0F8h]
0x1400051f2  mov     [rsp+148h+var_F0], eax
0x1400051f6  mov     eax, [rbx+78h]
0x1400051f9  mov     [rsp+148h+var_F8], edx
0x1400051fd  lea     rdx, WINNAT_SESSION_TIMER_UPDATE
0x140005204  mov     [rsp+148h+var_100], eax
0x140005208  lea     rax, [rsp+148h+var_80]
0x140005210  mov     [rsp+148h+var_108], rax
0x140005215  lea     rax, [rsp+148h+var_C0]
0x14000521d  mov     [rsp+148h+var_110], rax
0x140005222  lea     rax, [rsp+148h+var_60]
0x14000522a  mov     [rsp+148h+var_118], ecx
0x14000522e  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140005235  mov     [rsp+148h+var_120], rax
0x14000523a  lea     rax, [rsp+148h+var_A0]
0x140005242  mov     [rsp+148h+var_128], rax
0x140005247  call    McTemplateK0qbr0br0qbr3br3qqqq_EtwWriteTransfer
0x14000524c  jmp     loc_140004F8C
0x140005251  mov     bpl, 1
0x140005254  jmp     loc_14000502B
0x140005259  lea     rcx, [r14+40h]
0x14000525d  lea     rdx, [rsp+148h+LockHandle]
0x140005262  call    RtlAcquireScalableWriteLockAtDpcLevel
0x140005267  test    byte ptr [r14+274h], 1
0x14000526f  jnz     short loc_1400052AE
0x140005271  test    r15b, r15b
0x140005274  jz      short loc_140005290
0x140005276  mov     rcx, [r14+1D8h]
0x14000527d  lea     rdx, [rbx+90h]
0x140005284  call    cs:__imp_RtlIndicateTimerWheelEntryTimerStart
0x14000528b  nop     dword ptr [rax+rax+00h]
0x140005290  test    bpl, bpl
0x140005293  jz      short loc_1400052AE
0x140005295  mov     rdx, rbx
0x140005298  mov     rcx, r14
0x14000529b  call    WinNatIsTimerRestartNeeded
0x1400052a0  mov     edx, [rbx+88h]
0x1400052a6  mov     rcx, r14
0x1400052a9  call    WinNatRestartSessionTimer
0x1400052ae  lea     rcx, [rsp+148h+LockHandle]; LockHandle
0x1400052b3  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400052ba  nop     dword ptr [rax+rax+00h]
0x1400052bf  jmp     loc_14000504D
```
