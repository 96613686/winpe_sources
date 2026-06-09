# UdfPnpRemove

- ea: `0x140037770`
- end: `0x140037876`
- name: `UdfPnpRemove`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400590b0`

## callees

- `0x1400030e0`
- `0x140008594`
- `0x1400133ac`
- `0x140037770`
- `0x14004ce50`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14003783b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003784e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003783b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003784e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400377b2`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400377b2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400377d9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400377d9`
- `ntoskrnl!IoSynchronousCallDriver` at `0x140037818`
- `ntoskrnl!IoSynchronousCallDriver` at `0x140037818`

## pseudocode

```c
__int64 __fastcall UdfPnpRemove(void *a1, IRP *a2, __int64 a3)
{
  struct _ERESOURCE *v3; // rbp
  __int64 v7; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  unsigned int v9; // edi

  v3 = (struct _ERESOURCE *)(a3 + 1480);
  UdfAcquireResource(a1, a3 + 1480, 0, 0);
  if ( (int)UdfUnlockVolumeInternal(v7, a3, 0) < 0 )
  {
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a3 + 1584));
    if ( *(_DWORD *)(a3 + 52) != 4 )
      *(_DWORD *)(a3 + 52) = 3;
    *(_QWORD *)(a3 + 1640) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a3 + 1584));
  }
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                             + 6);
  CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
  CurrentStackLocation[-1].Control = 0;
  v9 = IoSynchronousCallDriver(*(_QWORD *)(a3 + 24), a2);
  if ( UdfCheckForDismount((__int64)a1, a3, 1) )
    ExReleaseResourceLite(v3);
  ExReleaseResourceLite(&Resource);
  UdfCompleteRequest(a1, a2, v9);
  return v9;
}

```

## disassembly

```asm
0x140037770  push    rbx
0x140037772  push    rbp
0x140037773  push    rsi
0x140037774  push    rdi
0x140037775  push    r14
0x140037777  sub     rsp, 20h
0x14003777b  lea     rbp, [r8+5C8h]
0x140037782  mov     rbx, r8
0x140037785  mov     r14, rdx
0x140037788  xor     r9d, r9d
0x14003778b  mov     rdx, rbp
0x14003778e  xor     r8d, r8d
0x140037791  mov     rsi, rcx
0x140037794  call    UdfAcquireResource
0x140037799  xor     r8d, r8d
0x14003779c  mov     rdx, rbx
0x14003779f  call    UdfUnlockVolumeInternal
0x1400377a4  test    eax, eax
0x1400377a6  jns     short loc_1400377E5
0x1400377a8  lea     rdi, [rbx+630h]
0x1400377af  mov     rcx, rdi; FastMutex
0x1400377b2  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400377b9  nop     dword ptr [rax+rax+00h]
0x1400377be  cmp     dword ptr [rbx+34h], 4
0x1400377c2  jz      short loc_1400377CB
0x1400377c4  mov     dword ptr [rbx+34h], 3
0x1400377cb  mov     rcx, rdi; FastMutex
0x1400377ce  mov     qword ptr [rbx+668h], 0
0x1400377d9  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400377e0  nop     dword ptr [rax+rax+00h]
0x1400377e5  mov     rax, [r14+0B8h]
0x1400377ec  mov     rdx, r14
0x1400377ef  movups  xmm0, xmmword ptr [rax]
0x1400377f2  movups  xmmword ptr [rax-48h], xmm0
0x1400377f6  movups  xmm1, xmmword ptr [rax+10h]
0x1400377fa  movups  xmmword ptr [rax-38h], xmm1
0x1400377fe  movups  xmm0, xmmword ptr [rax+20h]
0x140037802  movups  xmmword ptr [rax-28h], xmm0
0x140037806  movsd   xmm1, qword ptr [rax+30h]
0x14003780b  movsd   qword ptr [rax-18h], xmm1
0x140037810  mov     byte ptr [rax-45h], 0
0x140037814  mov     rcx, [rbx+18h]
0x140037818  call    cs:__imp_IoSynchronousCallDriver
0x14003781f  nop     dword ptr [rax+rax+00h]
0x140037824  mov     r8b, 1
0x140037827  mov     rdx, rbx
0x14003782a  mov     rcx, rsi
0x14003782d  mov     edi, eax
0x14003782f  call    UdfCheckForDismount
0x140037834  test    al, al
0x140037836  jz      short loc_140037847
0x140037838  mov     rcx, rbp; Resource
0x14003783b  call    cs:__imp_ExReleaseResourceLite
0x140037842  nop     dword ptr [rax+rax+00h]
0x140037847  lea     rcx, Resource; Resource
0x14003784e  call    cs:__imp_ExReleaseResourceLite
0x140037855  nop     dword ptr [rax+rax+00h]
0x14003785a  mov     r8d, edi
0x14003785d  mov     rdx, r14
0x140037860  mov     rcx, rsi
0x140037863  call    UdfCompleteRequest
0x140037868  mov     eax, edi
0x14003786a  add     rsp, 20h
0x14003786e  pop     r14
0x140037870  pop     rdi
0x140037871  pop     rsi
0x140037872  pop     rbp
0x140037873  pop     rbx
0x140037874  retn
```
