# PgmDereferenceSessionCommon

- ea: `0x1400067f4`
- end: `0x14000698f`
- name: `PgmDereferenceSessionCommon`
- size: `411`
- prototype: `void __fastcall(__int64)`
- caller_count: `17`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400025d0`
- `0x140005958`
- `0x140005e3c`
- `0x14000b670`
- `0x14000dd10`
- `0x140011904`
- `0x140011fc0`
- `0x140013930`
- `0x140014540`
- `0x1400163e4`
- `0x140018020`
- `0x1400184d0`
- `0x140018b00`
- `0x1400192d0`
- `0x140019424`
- `0x14001a260`
- `0x14001a6d0`

## callees

- `0x1400052e4`
- `0x1400054d0`
- `0x140005b30`
- `0x1400067f4`
- `0x140007f1c`
- `0x14000dd10`
- `0x14001c9f4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400068fc`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400068fc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000682d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400068a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400068f0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000682d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400068a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400068f0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006813`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400068ba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006813`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400068ba`

## pseudocode

```c
void __fastcall PgmDereferenceSessionCommon(__int64 a1)
{
  KSPIN_LOCK *v1; // rdi
  KIRQL v3; // al
  bool v4; // zf
  KIRQL v5; // bp
  IRP *v6; // rsi
  KIRQL v7; // al
  __int64 v8; // r8
  _QWORD *v9; // rdx
  int v10; // r9d

  v1 = (KSPIN_LOCK *)(a1 + 360);
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 360));
  v4 = (*(_DWORD *)(a1 + 20))-- == 1;
  v5 = v3;
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        14,
        WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids,
        a1,
        *(_QWORD *)(a1 + 88));
    v6 = *(IRP **)(a1 + 88);
    if ( *(_QWORD *)(a1 + 48) )
      CleanupPendingNaks(a1, 0, 1);
    KeReleaseSpinLock(v1, v5);
    v7 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    v8 = *(_QWORD *)a1;
    if ( *(_QWORD *)(*(_QWORD *)a1 + 8LL) != a1 || (v9 = *(_QWORD **)(a1 + 8), *v9 != a1) )
      __fastfail(3u);
    *v9 = v8;
    *(_QWORD *)(v8 + 8) = v9;
    KeReleaseSpinLock(&SpinLock, v7);
    if ( KeGetCurrentIrql() )
    {
      if ( (int)PgmQueueForDelayedExecution((unsigned int)PgmCleanupSession, a1, 0, v10, 0) < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids, a1);
        if ( v6 )
        {
          *(_QWORD *)(a1 + 88) = 0;
          PgmIoComplete(v6);
        }
      }
    }
    else
    {
      PgmCleanupSession(a1);
    }
  }
  else
  {
    KeReleaseSpinLock(v1, v3);
  }
}

```

## disassembly

```asm
0x1400067f4  mov     [rsp+arg_0], rbx
0x1400067f9  mov     [rsp+arg_8], rbp
0x1400067fe  push    rsi
0x1400067ff  push    rdi
0x140006800  push    r15
0x140006802  sub     rsp, 30h
0x140006806  lea     rdi, [rcx+168h]
0x14000680d  mov     rbx, rcx
0x140006810  mov     rcx, rdi; SpinLock
0x140006813  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000681a  nop     dword ptr [rax+rax+00h]
0x14000681f  add     dword ptr [rbx+14h], 0FFFFFFFFh
0x140006823  mov     bpl, al
0x140006826  jz      short loc_14000684D
0x140006828  mov     dl, al; NewIrql
0x14000682a  mov     rcx, rdi; SpinLock
0x14000682d  call    cs:__imp_KeReleaseSpinLock
0x140006834  nop     dword ptr [rax+rax+00h]
0x140006839  mov     rbx, [rsp+48h+arg_0]
0x14000683e  mov     rbp, [rsp+48h+arg_8]
0x140006843  add     rsp, 30h
0x140006847  pop     r15
0x140006849  pop     rdi
0x14000684a  pop     rsi
0x14000684b  retn
0x14000684d  mov     rcx, cs:WPP_GLOBAL_Control
0x140006854  lea     r15, WPP_GLOBAL_Control
0x14000685b  cmp     rcx, r15
0x14000685e  jz      short loc_140006888
0x140006860  mov     eax, [rcx+2Ch]
0x140006863  test    al, 4
0x140006865  jz      short loc_140006888
0x140006867  mov     rax, [rbx+58h]
0x14000686b  lea     r8, WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids
0x140006872  mov     rcx, [rcx+18h]
0x140006876  mov     edx, 0Eh
0x14000687b  mov     r9, rbx
0x14000687e  mov     [rsp+48h+var_28], rax
0x140006883  call    WPP_SF_qq
0x140006888  cmp     qword ptr [rbx+30h], 0
0x14000688d  mov     rsi, [rbx+58h]
0x140006891  jz      short loc_1400068A1
0x140006893  xor     edx, edx
0x140006895  mov     rcx, rbx
0x140006898  lea     r8d, [rdx+1]
0x14000689c  call    CleanupPendingNaks
0x1400068a1  mov     dl, bpl; NewIrql
0x1400068a4  mov     rcx, rdi; SpinLock
0x1400068a7  call    cs:__imp_KeReleaseSpinLock
0x1400068ae  nop     dword ptr [rax+rax+00h]
0x1400068b3  lea     rcx, SpinLock; SpinLock
0x1400068ba  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400068c1  nop     dword ptr [rax+rax+00h]
0x1400068c6  mov     r8, [rbx]
0x1400068c9  cmp     [r8+8], rbx
0x1400068cd  jnz     loc_140006988
0x1400068d3  mov     rdx, [rbx+8]
0x1400068d7  cmp     [rdx], rbx
0x1400068da  jnz     loc_140006988
0x1400068e0  mov     [rdx], r8
0x1400068e3  lea     rcx, SpinLock; SpinLock
0x1400068ea  mov     [r8+8], rdx
0x1400068ee  mov     dl, al; NewIrql
0x1400068f0  call    cs:__imp_KeReleaseSpinLock
0x1400068f7  nop     dword ptr [rax+rax+00h]
0x1400068fc  call    cs:__imp_KeGetCurrentIrql
0x140006903  nop     dword ptr [rax+rax+00h]
0x140006908  xor     r8d, r8d
0x14000690b  test    al, al
0x14000690d  jz      short loc_140006979
0x14000690f  mov     rdx, rbx
0x140006912  mov     byte ptr [rsp+48h+var_28], r8b
0x140006917  lea     rcx, PgmCleanupSession
0x14000691e  call    PgmQueueForDelayedExecution
0x140006923  test    eax, eax
0x140006925  jns     loc_140006839
0x14000692b  mov     rcx, cs:WPP_GLOBAL_Control
0x140006932  cmp     rcx, r15
0x140006935  jz      short loc_140006956
0x140006937  mov     eax, [rcx+2Ch]
0x14000693a  test    al, 2
0x14000693c  jz      short loc_140006956
0x14000693e  mov     rcx, [rcx+18h]
0x140006942  lea     r8, WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids
0x140006949  mov     edx, 0Fh
0x14000694e  mov     r9, rbx
0x140006951  call    WPP_SF_q
0x140006956  test    rsi, rsi
0x140006959  jz      loc_140006839
0x14000695f  xor     r8d, r8d
0x140006962  mov     qword ptr [rbx+58h], 0
0x14000696a  xor     edx, edx
0x14000696c  mov     rcx, rsi; Irp
0x14000696f  call    PgmIoComplete
0x140006974  jmp     loc_140006839
0x140006979  xor     edx, edx
0x14000697b  mov     rcx, rbx
0x14000697e  call    PgmCleanupSession
0x140006983  jmp     loc_140006839
0x140006988  mov     ecx, 3
0x14000698d  int     29h; Win8: RtlFailFast(ecx)
```
