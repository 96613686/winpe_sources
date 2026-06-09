# PgmCancelReceiveIrp

- ea: `0x14000f120`
- end: `0x14000f2d0`
- name: `PgmCancelReceiveIrp`
- size: `432`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140005524`
- `0x14000f120`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000f1ce`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000f254`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000f265`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000f1ce`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000f254`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000f265`
- `ntoskrnl!IofCompleteRequest` at `0x14000f1df`
- `ntoskrnl!IofCompleteRequest` at `0x14000f1df`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f1bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f245`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f1bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f245`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f161`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f161`

## pseudocode

```c
void __fastcall PgmCancelReceiveIrp(__int64 a1, IRP *a2)
{
  KSPIN_LOCK *FsContext; // rdi
  KIRQL v4; // al
  KSPIN_LOCK v5; // rcx
  KIRQL v6; // r8
  PVOID *v7; // rcx
  PVOID *v8; // rdx
  PVOID *v9; // rax
  PVOID **v10; // rcx
  __int64 v11; // r8

  FsContext = (KSPIN_LOCK *)a2->Tail.Overlay.CurrentStackLocation->FileObject->FsContext;
  if ( FsContext && *((_DWORD *)FsContext + 4) == 1381188947 )
  {
    v4 = KeAcquireSpinLockRaiseToDpc(FsContext + 45);
    v5 = FsContext[6];
    v6 = v4;
    if ( a2 == *(IRP **)(v5 + 232) )
    {
      a2->IoStatus.Information = *(unsigned int *)(v5 + 244);
      a2->IoStatus.Status = -1073741536;
      *(_DWORD *)(FsContext[6] + 240) = 0;
      *(_DWORD *)(FsContext[6] + 244) = 0;
      *(_QWORD *)(FsContext[6] + 232) = 0;
    }
    else
    {
      v7 = (PVOID *)(v5 + 200);
      v8 = v7;
      do
      {
        v8 = (PVOID *)*v8;
        if ( v8 == v7 )
        {
          KeReleaseSpinLock(FsContext + 45, v4);
          IoReleaseCancelSpinLock(a2->CancelIrql);
          return;
        }
      }
      while ( v8 != &a2->Tail.CompletionKey + 6 );
      v9 = (PVOID *)*v8;
      if ( *((PVOID **)*v8 + 1) != v8 || (v10 = (PVOID **)v8[1], *v10 != v8) )
        __fastfail(3u);
      *v10 = v9;
      v9[1] = v10;
      a2->IoStatus.Status = -1073741536;
      a2->IoStatus.Information = 0;
    }
    KeReleaseSpinLock(FsContext + 45, v6);
    IoReleaseCancelSpinLock(a2->CancelIrql);
    IofCompleteRequest(a2, 2);
  }
  else
  {
    IoReleaseCancelSpinLock(a2->CancelIrql);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    {
      if ( FsContext )
        v11 = *(_QWORD *)(FsContext[6] + 24);
      else
        v11 = 0;
      WPP_SF_qqq(
        WPP_GLOBAL_Control->AttachedDevice,
        176,
        WPP_9481eaf791d131fecb736b68b85870ad_Traceguids,
        a2,
        FsContext,
        v11);
    }
  }
}

```

## disassembly

```asm
0x14000f120  mov     [rsp+arg_0], rbx
0x14000f125  mov     [rsp+arg_8], rsi
0x14000f12a  push    rdi
0x14000f12b  sub     rsp, 30h
0x14000f12f  mov     rax, [rdx+0B8h]
0x14000f136  mov     rbx, rdx
0x14000f139  mov     rcx, [rax+30h]
0x14000f13d  mov     rdi, [rcx+18h]
0x14000f141  test    rdi, rdi
0x14000f144  jz      loc_14000F262
0x14000f14a  cmp     dword ptr [rdi+10h], 52534553h
0x14000f151  jnz     loc_14000F262
0x14000f157  lea     rsi, [rdi+168h]
0x14000f15e  mov     rcx, rsi; SpinLock
0x14000f161  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f168  nop     dword ptr [rax+rax+00h]
0x14000f16d  mov     rcx, [rdi+30h]
0x14000f171  mov     r8b, al
0x14000f174  cmp     rbx, [rcx+0E8h]
0x14000f17b  jnz     short loc_14000F1F0
0x14000f17d  mov     ecx, [rcx+0F4h]
0x14000f183  mov     [rbx+38h], rcx
0x14000f187  mov     dword ptr [rbx+30h], 0C0000120h
0x14000f18e  mov     rcx, [rdi+30h]
0x14000f192  mov     dword ptr [rcx+0F0h], 0
0x14000f19c  mov     rcx, [rdi+30h]
0x14000f1a0  mov     dword ptr [rcx+0F4h], 0
0x14000f1aa  mov     rcx, [rdi+30h]
0x14000f1ae  mov     qword ptr [rcx+0E8h], 0
0x14000f1b9  mov     dl, r8b; NewIrql
0x14000f1bc  mov     rcx, rsi; SpinLock
0x14000f1bf  call    cs:__imp_KeReleaseSpinLock
0x14000f1c6  nop     dword ptr [rax+rax+00h]
0x14000f1cb  mov     cl, [rbx+45h]; Irql
0x14000f1ce  call    cs:__imp_IoReleaseCancelSpinLock
0x14000f1d5  nop     dword ptr [rax+rax+00h]
0x14000f1da  mov     dl, 2; PriorityBoost
0x14000f1dc  mov     rcx, rbx; Irp
0x14000f1df  call    cs:__imp_IofCompleteRequest
0x14000f1e6  nop     dword ptr [rax+rax+00h]
0x14000f1eb  jmp     loc_14000F2BF
0x14000f1f0  add     rcx, 0C8h
0x14000f1f7  mov     rdx, rcx
0x14000f1fa  mov     rdx, [rdx]
0x14000f1fd  cmp     rdx, rcx
0x14000f200  jz      short loc_14000F23F
0x14000f202  lea     rax, [rbx+0A8h]
0x14000f209  cmp     rdx, rax
0x14000f20c  jnz     short loc_14000F1FA
0x14000f20e  mov     rax, [rdx]
0x14000f211  cmp     [rax+8], rdx
0x14000f215  jnz     short loc_14000F238
0x14000f217  mov     rcx, [rdx+8]
0x14000f21b  cmp     [rcx], rdx
0x14000f21e  jnz     short loc_14000F238
0x14000f220  mov     [rcx], rax
0x14000f223  mov     [rax+8], rcx
0x14000f227  mov     dword ptr [rbx+30h], 0C0000120h
0x14000f22e  mov     qword ptr [rbx+38h], 0
0x14000f236  jmp     short loc_14000F1B9
0x14000f238  mov     ecx, 3
0x14000f23d  int     29h; Win8: RtlFailFast(ecx)
0x14000f23f  mov     dl, r8b; NewIrql
0x14000f242  mov     rcx, rsi; SpinLock
0x14000f245  call    cs:__imp_KeReleaseSpinLock
0x14000f24c  nop     dword ptr [rax+rax+00h]
0x14000f251  mov     cl, [rbx+45h]; Irql
0x14000f254  call    cs:__imp_IoReleaseCancelSpinLock
0x14000f25b  nop     dword ptr [rax+rax+00h]
0x14000f260  jmp     short loc_14000F2BF
0x14000f262  mov     cl, [rdx+45h]; Irql
0x14000f265  call    cs:__imp_IoReleaseCancelSpinLock
0x14000f26c  nop     dword ptr [rax+rax+00h]
0x14000f271  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f278  lea     rax, WPP_GLOBAL_Control
0x14000f27f  cmp     rcx, rax
0x14000f282  jz      short loc_14000F2BF
0x14000f284  mov     eax, [rcx+2Ch]
0x14000f287  test    al, 2
0x14000f289  jz      short loc_14000F2BF
0x14000f28b  test    rdi, rdi
0x14000f28e  jz      short loc_14000F29A
0x14000f290  mov     rax, [rdi+30h]
0x14000f294  mov     r8, [rax+18h]
0x14000f298  jmp     short loc_14000F29D
0x14000f29a  xor     r8d, r8d
0x14000f29d  mov     rcx, [rcx+18h]
0x14000f2a1  mov     edx, 0B0h
0x14000f2a6  mov     [rsp+38h+var_10], r8
0x14000f2ab  mov     r9, rbx
0x14000f2ae  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x14000f2b5  mov     [rsp+38h+var_18], rdi
0x14000f2ba  call    WPP_SF_qqq
0x14000f2bf  mov     rbx, [rsp+38h+arg_0]
0x14000f2c4  mov     rsi, [rsp+38h+arg_8]
0x14000f2c9  add     rsp, 30h
0x14000f2cd  pop     rdi
0x14000f2ce  retn
```
