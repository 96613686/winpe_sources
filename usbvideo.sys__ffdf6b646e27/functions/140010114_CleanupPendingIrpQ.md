# CleanupPendingIrpQ

- ea: `0x140010114`
- end: `0x1400101f2`
- name: `CleanupPendingIrpQ`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140010020`

## callees

- `0x140010114`
- `0x1400199e8`

## import_xrefs

- `ntoskrnl!IoCsqRemoveNextIrp` at `0x140010169`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x1400101c0`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x140010169`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x1400101c0`
- `ntoskrnl!IofCompleteRequest` at `0x140010158`
- `ntoskrnl!IofCompleteRequest` at `0x1400101af`
- `ntoskrnl!IofCompleteRequest` at `0x140010158`
- `ntoskrnl!IofCompleteRequest` at `0x1400101af`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010138`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001018f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010138`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001018f`

## pseudocode

```c
__int64 __fastcall CleanupPendingIrpQ(__int64 a1)
{
  struct _IO_CSQ *v2; // rsi
  PIRP v3; // rax
  IRP *v4; // rbx
  PIRP v5; // rax
  IRP *v6; // rbx

  v2 = (struct _IO_CSQ *)(a1 + 512);
  while ( 1 )
  {
    v3 = IoCsqRemoveNextIrp(v2, 0);
    v4 = v3;
    if ( !v3 )
      break;
    ExFreePoolWithTag(v3->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink, 0x56425355u);
    v4->IoStatus.Information = 0;
    v4->IoStatus.Status = -1073741536;
    IofCompleteRequest(v4, 0);
  }
  while ( 1 )
  {
    v5 = IoCsqRemoveNextIrp((PIO_CSQ)(a1 + 432), 0);
    v6 = v5;
    if ( !v5 )
      break;
    ExFreePoolWithTag(v5->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink, 0x56425355u);
    v6->IoStatus.Information = 0;
    v6->IoStatus.Status = -1073741536;
    IofCompleteRequest(v6, 0);
  }
  return FilterCreateQueue_CompleteQueue(a1, 3221225760LL);
}

```

## disassembly

```asm
0x140010114  mov     [rsp+arg_0], rbx
0x140010119  mov     [rsp+arg_8], rsi
0x14001011e  push    rdi
0x14001011f  sub     rsp, 20h
0x140010123  mov     rdi, rcx
0x140010126  lea     rsi, [rcx+200h]
0x14001012d  jmp     short loc_140010164
0x14001012f  mov     rcx, [rbx+78h]; P
0x140010133  mov     edx, 56425355h; Tag
0x140010138  call    cs:__imp_ExFreePoolWithTag
0x14001013f  nop     dword ptr [rax+rax+00h]
0x140010144  xor     edx, edx; PriorityBoost
0x140010146  mov     qword ptr [rbx+38h], 0
0x14001014e  mov     rcx, rbx; Irp
0x140010151  mov     dword ptr [rbx+30h], 0C0000120h
0x140010158  call    cs:__imp_IofCompleteRequest
0x14001015f  nop     dword ptr [rax+rax+00h]
0x140010164  xor     edx, edx; PeekContext
0x140010166  mov     rcx, rsi; Csq
0x140010169  call    cs:__imp_IoCsqRemoveNextIrp
0x140010170  nop     dword ptr [rax+rax+00h]
0x140010175  mov     rbx, rax
0x140010178  test    rax, rax
0x14001017b  jnz     short loc_14001012F
0x14001017d  lea     rsi, [rdi+1B0h]
0x140010184  jmp     short loc_1400101BB
0x140010186  mov     rcx, [rbx+78h]; P
0x14001018a  mov     edx, 56425355h; Tag
0x14001018f  call    cs:__imp_ExFreePoolWithTag
0x140010196  nop     dword ptr [rax+rax+00h]
0x14001019b  xor     edx, edx; PriorityBoost
0x14001019d  mov     qword ptr [rbx+38h], 0
0x1400101a5  mov     rcx, rbx; Irp
0x1400101a8  mov     dword ptr [rbx+30h], 0C0000120h
0x1400101af  call    cs:__imp_IofCompleteRequest
0x1400101b6  nop     dword ptr [rax+rax+00h]
0x1400101bb  xor     edx, edx; PeekContext
0x1400101bd  mov     rcx, rsi; Csq
0x1400101c0  call    cs:__imp_IoCsqRemoveNextIrp
0x1400101c7  nop     dword ptr [rax+rax+00h]
0x1400101cc  mov     rbx, rax
0x1400101cf  test    rax, rax
0x1400101d2  jnz     short loc_140010186
0x1400101d4  mov     edx, 0C0000120h
0x1400101d9  mov     rcx, rdi
0x1400101dc  call    FilterCreateQueue_CompleteQueue
0x1400101e1  mov     rbx, [rsp+28h+arg_0]
0x1400101e6  mov     rsi, [rsp+28h+arg_8]
0x1400101eb  add     rsp, 20h
0x1400101ef  pop     rdi
0x1400101f0  retn
```
