# TdxReceiveDatagramTransportAddressCancelRoutine

- ea: `0x1400129a0`
- end: `0x140012a85`
- name: `TdxReceiveDatagramTransportAddressCancelRoutine`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400054ec`
- `0x1400129a0`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400129d4`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400129d4`
- `ntoskrnl!IofCompleteRequest` at `0x140012a3f`
- `ntoskrnl!IofCompleteRequest` at `0x140012a3f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400129c6`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400129c6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012a1f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012a6f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012a1f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012a6f`

## pseudocode

```c
void __fastcall TdxReceiveDatagramTransportAddressCancelRoutine(__int64 a1, IRP *a2)
{
  KIRQL CancelIrql; // si
  char *FsContext; // rbp
  PVOID *i; // rcx
  PVOID *v6; // rdx
  PVOID **v7; // rax

  CancelIrql = a2->CancelIrql;
  FsContext = (char *)a2->Tail.Overlay.CurrentStackLocation->FileObject->FsContext;
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)FsContext + 1);
  IoReleaseCancelSpinLock(2u);
  for ( i = (PVOID *)*((_QWORD *)FsContext + 42); ; i = (PVOID *)*i )
  {
    if ( i == (PVOID *)(FsContext + 336) )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)FsContext + 1, CancelIrql);
      return;
    }
    v6 = (PVOID *)*i;
    if ( i == &a2->Tail.CompletionKey + 6 )
      break;
  }
  if ( v6[1] != i || (v7 = (PVOID **)i[1], *v7 != i) )
    __fastfail(3u);
  *v7 = v6;
  v6[1] = v7;
  KeReleaseSpinLock((PKSPIN_LOCK)FsContext + 1, CancelIrql);
  a2->IoStatus.Status = -1073741536;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 2);
  DbgTdxDereferenceTransportAddress(FsContext, "minio\\netio\\session\\tdi\\address.c", 2622);
}

```

## disassembly

```asm
0x1400129a0  push    rbx
0x1400129a2  push    rbp
0x1400129a3  push    rsi
0x1400129a4  push    rdi
0x1400129a5  sub     rsp, 28h
0x1400129a9  mov     rax, [rdx+0B8h]
0x1400129b0  mov     rbx, rdx
0x1400129b3  mov     sil, [rdx+45h]
0x1400129b7  mov     rcx, [rax+30h]
0x1400129bb  mov     rbp, [rcx+18h]
0x1400129bf  lea     rdi, [rbp+8]
0x1400129c3  mov     rcx, rdi; SpinLock
0x1400129c6  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400129cd  nop     dword ptr [rax+rax+00h]
0x1400129d2  mov     cl, 2; Irql
0x1400129d4  call    cs:__imp_IoReleaseCancelSpinLock
0x1400129db  nop     dword ptr [rax+rax+00h]
0x1400129e0  lea     r8, [rbp+150h]
0x1400129e7  mov     rcx, [r8]
0x1400129ea  cmp     rcx, r8
0x1400129ed  jz      short loc_140012A69
0x1400129ef  mov     rdx, [rcx]
0x1400129f2  lea     rax, [rbx+0A8h]
0x1400129f9  cmp     rcx, rax
0x1400129fc  jz      short loc_140012A03
0x1400129fe  mov     rcx, rdx
0x140012a01  jmp     short loc_1400129EA
0x140012a03  cmp     [rdx+8], rcx
0x140012a07  jnz     short loc_140012A62
0x140012a09  mov     rax, [rcx+8]
0x140012a0d  cmp     [rax], rcx
0x140012a10  jnz     short loc_140012A62
0x140012a12  mov     [rax], rdx
0x140012a15  mov     rcx, rdi; SpinLock
0x140012a18  mov     [rdx+8], rax
0x140012a1c  mov     dl, sil; NewIrql
0x140012a1f  call    cs:__imp_KeReleaseSpinLock
0x140012a26  nop     dword ptr [rax+rax+00h]
0x140012a2b  mov     dl, 2; PriorityBoost
0x140012a2d  mov     dword ptr [rbx+30h], 0C0000120h
0x140012a34  mov     rcx, rbx; Irp
0x140012a37  mov     qword ptr [rbx+38h], 0
0x140012a3f  call    cs:__imp_IofCompleteRequest
0x140012a46  nop     dword ptr [rax+rax+00h]
0x140012a4b  mov     r8d, 0A3Eh
0x140012a51  lea     rdx, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x140012a58  mov     rcx, rbp
0x140012a5b  call    DbgTdxDereferenceTransportAddress
0x140012a60  jmp     short loc_140012A7B
0x140012a62  mov     ecx, 3
0x140012a67  int     29h; Win8: RtlFailFast(ecx)
0x140012a69  mov     dl, sil; NewIrql
0x140012a6c  mov     rcx, rdi; SpinLock
0x140012a6f  call    cs:__imp_KeReleaseSpinLock
0x140012a76  nop     dword ptr [rax+rax+00h]
0x140012a7b  add     rsp, 28h
0x140012a7f  pop     rdi
0x140012a80  pop     rsi
0x140012a81  pop     rbp
0x140012a82  pop     rbx
0x140012a83  retn
```
