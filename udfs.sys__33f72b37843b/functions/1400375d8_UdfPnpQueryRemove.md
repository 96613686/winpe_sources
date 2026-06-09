# UdfPnpQueryRemove

- ea: `0x1400375d8`
- end: `0x14003776a`
- name: `UdfPnpQueryRemove`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400590b0`

## callees

- `0x1400030e0`
- `0x140008594`
- `0x140013128`
- `0x1400375d8`
- `0x14004ce50`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140037640`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003765f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003772d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037740`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037640`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003765f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003772d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037740`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140037674`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140037674`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003760d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140037694`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003760d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140037694`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003762d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400376b4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003762d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400376b4`
- `ntoskrnl!IoSynchronousCallDriver` at `0x1400376f7`
- `ntoskrnl!IoSynchronousCallDriver` at `0x1400376f7`

## pseudocode

```c
__int64 __fastcall UdfPnpQueryRemove(void *a1, IRP *a2, __int64 a3)
{
  struct _ERESOURCE *v3; // r15
  NTSTATUS v7; // edi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax

  v3 = (struct _ERESOURCE *)(a3 + 1480);
  UdfAcquireResource(a1, a3 + 1480, 0, 0);
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a3 + 1584));
  ++*(_DWORD *)(a3 + 256);
  *(_QWORD *)(a3 + 1640) = 0;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a3 + 1584));
  ExReleaseResourceLite(&Resource);
  v7 = UdfLockVolumeInternal((__int64)a1, a3, 0);
  ExReleaseResourceLite(v3);
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  UdfAcquireResource(a1, v3, 0, 0);
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a3 + 1584));
  --*(_DWORD *)(a3 + 256);
  *(_QWORD *)(a3 + 1640) = 0;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a3 + 1584));
  if ( v7 < 0
    || (CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation,
        *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction,
        *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter,
        *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                                   + 6),
        CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject,
        CurrentStackLocation[-1].Control = 0,
        v7 = IoSynchronousCallDriver(*(_QWORD *)(a3 + 24), a2),
        v7 < 0) )
  {
LABEL_6:
    ExReleaseResourceLite(v3);
    goto LABEL_7;
  }
  if ( UdfCheckForDismount((__int64)a1, a3, 1) )
  {
    if ( *(_DWORD *)(a3 + 256) )
      v7 = -2147483631;
    goto LABEL_6;
  }
LABEL_7:
  ExReleaseResourceLite(&Resource);
  UdfCompleteRequest(a1, a2, v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400375d8  push    rbx
0x1400375da  push    rbp
0x1400375db  push    rsi
0x1400375dc  push    rdi
0x1400375dd  push    r14
0x1400375df  push    r15
0x1400375e1  sub     rsp, 28h
0x1400375e5  lea     r15, [r8+5C8h]
0x1400375ec  mov     rsi, r8
0x1400375ef  mov     r14, rdx
0x1400375f2  xor     r9d, r9d
0x1400375f5  mov     rdx, r15
0x1400375f8  xor     r8d, r8d
0x1400375fb  mov     rbp, rcx
0x1400375fe  call    UdfAcquireResource
0x140037603  lea     rbx, [rsi+630h]
0x14003760a  mov     rcx, rbx; FastMutex
0x14003760d  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140037614  nop     dword ptr [rax+rax+00h]
0x140037619  inc     dword ptr [rsi+100h]
0x14003761f  mov     rcx, rbx; FastMutex
0x140037622  mov     qword ptr [rsi+668h], 0
0x14003762d  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140037634  nop     dword ptr [rax+rax+00h]
0x140037639  lea     rcx, Resource; Resource
0x140037640  call    cs:__imp_ExReleaseResourceLite
0x140037647  nop     dword ptr [rax+rax+00h]
0x14003764c  xor     r8d, r8d
0x14003764f  mov     rdx, rsi
0x140037652  mov     rcx, rbp
0x140037655  call    UdfLockVolumeInternal
0x14003765a  mov     rcx, r15; Resource
0x14003765d  mov     edi, eax
0x14003765f  call    cs:__imp_ExReleaseResourceLite
0x140037666  nop     dword ptr [rax+rax+00h]
0x14003766b  mov     dl, 1; Wait
0x14003766d  lea     rcx, Resource; Resource
0x140037674  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14003767b  nop     dword ptr [rax+rax+00h]
0x140037680  xor     r9d, r9d
0x140037683  xor     r8d, r8d
0x140037686  mov     rdx, r15
0x140037689  mov     rcx, rbp
0x14003768c  call    UdfAcquireResource
0x140037691  mov     rcx, rbx; FastMutex
0x140037694  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14003769b  nop     dword ptr [rax+rax+00h]
0x1400376a0  dec     dword ptr [rsi+100h]
0x1400376a6  mov     rcx, rbx; FastMutex
0x1400376a9  mov     qword ptr [rsi+668h], 0
0x1400376b4  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400376bb  nop     dword ptr [rax+rax+00h]
0x1400376c0  test    edi, edi
0x1400376c2  js      short loc_14003772A
0x1400376c4  mov     rax, [r14+0B8h]
0x1400376cb  mov     rdx, r14
0x1400376ce  movups  xmm0, xmmword ptr [rax]
0x1400376d1  movups  xmmword ptr [rax-48h], xmm0
0x1400376d5  movups  xmm1, xmmword ptr [rax+10h]
0x1400376d9  movups  xmmword ptr [rax-38h], xmm1
0x1400376dd  movups  xmm0, xmmword ptr [rax+20h]
0x1400376e1  movups  xmmword ptr [rax-28h], xmm0
0x1400376e5  movsd   xmm1, qword ptr [rax+30h]
0x1400376ea  movsd   qword ptr [rax-18h], xmm1
0x1400376ef  mov     byte ptr [rax-45h], 0
0x1400376f3  mov     rcx, [rsi+18h]
0x1400376f7  call    cs:__imp_IoSynchronousCallDriver
0x1400376fe  nop     dword ptr [rax+rax+00h]
0x140037703  mov     edi, eax
0x140037705  test    eax, eax
0x140037707  js      short loc_14003772A
0x140037709  mov     r8b, 1
0x14003770c  mov     rdx, rsi
0x14003770f  mov     rcx, rbp
0x140037712  call    UdfCheckForDismount
0x140037717  test    al, al
0x140037719  jz      short loc_140037739
0x14003771b  cmp     dword ptr [rsi+100h], 0
0x140037722  mov     eax, 80000011h
0x140037727  cmovnz  edi, eax
0x14003772a  mov     rcx, r15; Resource
0x14003772d  call    cs:__imp_ExReleaseResourceLite
0x140037734  nop     dword ptr [rax+rax+00h]
0x140037739  lea     rcx, Resource; Resource
0x140037740  call    cs:__imp_ExReleaseResourceLite
0x140037747  nop     dword ptr [rax+rax+00h]
0x14003774c  mov     r8d, edi
0x14003774f  mov     rdx, r14
0x140037752  mov     rcx, rbp
0x140037755  call    UdfCompleteRequest
0x14003775a  mov     eax, edi
0x14003775c  add     rsp, 28h
0x140037760  pop     r15
0x140037762  pop     r14
0x140037764  pop     rdi
0x140037765  pop     rsi
0x140037766  pop     rbp
0x140037767  pop     rbx
0x140037768  retn
```
