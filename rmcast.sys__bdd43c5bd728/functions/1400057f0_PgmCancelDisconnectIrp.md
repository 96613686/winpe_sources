# PgmCancelDisconnectIrp

- ea: `0x1400057f0`
- end: `0x140005950`
- name: `PgmCancelDisconnectIrp`
- size: `352`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400054d0`
- `0x140005524`
- `0x1400057f0`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140005884`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400058f1`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140005884`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400058f1`
- `ntoskrnl!IofCompleteRequest` at `0x1400058e0`
- `ntoskrnl!IofCompleteRequest` at `0x1400058e0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005875`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005875`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005831`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005831`

## pseudocode

```c
void __fastcall PgmCancelDisconnectIrp(__int64 a1, IRP *a2)
{
  PVOID FsContext; // rbx
  KIRQL v4; // al
  IRP *v5; // rsi
  __int64 v6; // rdx
  __int64 v7; // rax

  FsContext = a2->Tail.Overlay.CurrentStackLocation->FileObject->FsContext;
  if ( !FsContext || ((*((_DWORD *)FsContext + 4) - 1381188947) & 0xFEFFFFFF) != 0 )
  {
    IoReleaseCancelSpinLock(a2->CancelIrql);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    {
      if ( FsContext )
        v7 = *((_QWORD *)FsContext + 3);
      else
        v7 = 0;
      WPP_SF_qqq(
        WPP_GLOBAL_Control->AttachedDevice,
        28,
        WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids,
        a2,
        FsContext,
        v7);
    }
  }
  else
  {
    v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)FsContext + 45);
    v5 = (IRP *)*((_QWORD *)FsContext + 12);
    if ( v5 && v5 == a2 )
      *((_QWORD *)FsContext + 12) = 0;
    else
      v5 = 0;
    v6 = *((_QWORD *)FsContext + 5);
    if ( v6 )
      *(_QWORD *)(v6 + 312) = *(_QWORD *)(v6 + 296);
    KeReleaseSpinLock((PKSPIN_LOCK)FsContext + 45, v4);
    IoReleaseCancelSpinLock(a2->CancelIrql);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids, a2, v5);
    if ( v5 )
    {
      a2->IoStatus.Information = 0;
      a2->IoStatus.Status = -1073741536;
      IofCompleteRequest(a2, 2);
    }
  }
}

```

## disassembly

```asm
0x1400057f0  push    rbx
0x1400057f2  push    rbp
0x1400057f3  push    rsi
0x1400057f4  push    rdi
0x1400057f5  sub     rsp, 38h
0x1400057f9  mov     rax, [rdx+0B8h]
0x140005800  mov     rdi, rdx
0x140005803  mov     rcx, [rax+30h]
0x140005807  mov     rbx, [rcx+18h]
0x14000580b  test    rbx, rbx
0x14000580e  jz      loc_1400058EE
0x140005814  mov     eax, [rbx+10h]
0x140005817  sub     eax, 52534553h
0x14000581c  test    eax, 0FEFFFFFFh
0x140005821  jnz     loc_1400058EE
0x140005827  lea     rbp, [rbx+168h]
0x14000582e  mov     rcx, rbp; SpinLock
0x140005831  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005838  nop     dword ptr [rax+rax+00h]
0x14000583d  mov     rsi, [rbx+60h]
0x140005841  mov     cl, al
0x140005843  test    rsi, rsi
0x140005846  jz      short loc_140005857
0x140005848  cmp     rsi, rdi
0x14000584b  jnz     short loc_140005857
0x14000584d  mov     qword ptr [rbx+60h], 0
0x140005855  jmp     short loc_140005859
0x140005857  xor     esi, esi
0x140005859  mov     rdx, [rbx+28h]
0x14000585d  test    rdx, rdx
0x140005860  jz      short loc_140005870
0x140005862  mov     rax, [rdx+128h]
0x140005869  mov     [rdx+138h], rax
0x140005870  mov     dl, cl; NewIrql
0x140005872  mov     rcx, rbp; SpinLock
0x140005875  call    cs:__imp_KeReleaseSpinLock
0x14000587c  nop     dword ptr [rax+rax+00h]
0x140005881  mov     cl, [rdi+45h]; Irql
0x140005884  call    cs:__imp_IoReleaseCancelSpinLock
0x14000588b  nop     dword ptr [rax+rax+00h]
0x140005890  mov     rcx, cs:WPP_GLOBAL_Control
0x140005897  lea     rax, WPP_GLOBAL_Control
0x14000589e  cmp     rcx, rax
0x1400058a1  jz      short loc_1400058C7
0x1400058a3  mov     eax, [rcx+2Ch]
0x1400058a6  test    al, 10h
0x1400058a8  jz      short loc_1400058C7
0x1400058aa  mov     rcx, [rcx+18h]
0x1400058ae  lea     r8, WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids
0x1400058b5  mov     edx, 1Dh
0x1400058ba  mov     [rsp+58h+var_38], rsi
0x1400058bf  mov     r9, rdi
0x1400058c2  call    WPP_SF_qq
0x1400058c7  test    rsi, rsi
0x1400058ca  jz      short loc_140005946
0x1400058cc  mov     dl, 2; PriorityBoost
0x1400058ce  mov     qword ptr [rdi+38h], 0
0x1400058d6  mov     rcx, rdi; Irp
0x1400058d9  mov     dword ptr [rdi+30h], 0C0000120h
0x1400058e0  call    cs:__imp_IofCompleteRequest
0x1400058e7  nop     dword ptr [rax+rax+00h]
0x1400058ec  jmp     short loc_140005946
0x1400058ee  mov     cl, [rdx+45h]; Irql
0x1400058f1  call    cs:__imp_IoReleaseCancelSpinLock
0x1400058f8  nop     dword ptr [rax+rax+00h]
0x1400058fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140005904  lea     rax, WPP_GLOBAL_Control
0x14000590b  cmp     rcx, rax
0x14000590e  jz      short loc_140005946
0x140005910  mov     eax, [rcx+2Ch]
0x140005913  test    al, 2
0x140005915  jz      short loc_140005946
0x140005917  test    rbx, rbx
0x14000591a  jz      short loc_140005922
0x14000591c  mov     rax, [rbx+18h]
0x140005920  jmp     short loc_140005924
0x140005922  xor     eax, eax
0x140005924  mov     rcx, [rcx+18h]
0x140005928  lea     r8, WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids
0x14000592f  mov     [rsp+58h+var_30], rax
0x140005934  mov     edx, 1Ch
0x140005939  mov     r9, rdi
0x14000593c  mov     [rsp+58h+var_38], rbx
0x140005941  call    WPP_SF_qqq
0x140005946  add     rsp, 38h
0x14000594a  pop     rdi
0x14000594b  pop     rsi
0x14000594c  pop     rbp
0x14000594d  pop     rbx
0x14000594e  retn
```
