# TdxListenRequestComplete

- ea: `0x1400106c0`
- end: `0x140010741`
- name: `TdxListenRequestComplete`
- size: `129`
- prototype: `__int64 __fastcall(int, int, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400157cc`

## callees

- `0x1400054ec`
- `0x1400106c0`
- `0x140010748`
- `0x140012a8c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400106da`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400106da`

## pseudocode

```c
void __fastcall TdxListenRequestComplete(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  KIRQL NewIrql; // al
  IRP *v9; // r14

  NewIrql = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
  v9 = *(IRP **)(a1 + 536);
  *(_DWORD *)a1 &= ~0x10u;
  *(_QWORD *)(a1 + 536) = 0;
  TdxListenTransportAddressComplete(a1, a2, a3, a4, NewIrql);
  DbgTdxDereferenceTransportAddress(a1, "minio\\netio\\session\\tdi\\request.c", 140);
  if ( v9 )
    TdxReissueConnectWhileListenRequests(v9, a1);
}

```

## disassembly

```asm
0x1400106c0  push    rbx
0x1400106c2  push    rbp
0x1400106c3  push    rsi
0x1400106c4  push    rdi
0x1400106c5  push    r14
0x1400106c7  sub     rsp, 30h
0x1400106cb  mov     rbp, rcx
0x1400106ce  mov     rbx, r9
0x1400106d1  add     rcx, 8; SpinLock
0x1400106d5  mov     rdi, r8
0x1400106d8  mov     esi, edx
0x1400106da  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400106e1  nop     dword ptr [rax+rax+00h]
0x1400106e6  mov     r14, [rbp+218h]
0x1400106ed  mov     r9, rbx; int
0x1400106f0  and     dword ptr [rbp+0], 0FFFFFFEFh
0x1400106f4  mov     r8, rdi; int
0x1400106f7  mov     edx, esi; int
0x1400106f9  mov     [rsp+58h+NewIrql], al; NewIrql
0x1400106fd  mov     rcx, rbp; int
0x140010700  mov     qword ptr [rbp+218h], 0
0x14001070b  call    TdxListenTransportAddressComplete
0x140010710  mov     r8d, 8Ch
0x140010716  lea     rdx, aMinioNetioSess_0; "minio\\netio\\session\\tdi\\request.c"
0x14001071d  mov     rcx, rbp
0x140010720  call    DbgTdxDereferenceTransportAddress
0x140010725  test    r14, r14
0x140010728  jz      short loc_140010735
0x14001072a  mov     rdx, rbp
0x14001072d  mov     rcx, r14; Irp
0x140010730  call    TdxReissueConnectWhileListenRequests
0x140010735  add     rsp, 30h
0x140010739  pop     r14
0x14001073b  pop     rdi
0x14001073c  pop     rsi
0x14001073d  pop     rbp
0x14001073e  pop     rbx
0x14001073f  retn
```
