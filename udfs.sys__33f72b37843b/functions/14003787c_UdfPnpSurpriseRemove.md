# UdfPnpSurpriseRemove

- ea: `0x14003787c`
- end: `0x1400379ac`
- name: `UdfPnpSurpriseRemove`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400590b0`

## callees

- `0x1400030e0`
- `0x140008594`
- `0x14003787c`
- `0x14004ce50`
- `0x140052864`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140037968`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003797b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c0d9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c0ed`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037968`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003797b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c0d9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c0ed`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400378c0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400378c0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400378e7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400378e7`
- `ntoskrnl!IoSynchronousCallDriver` at `0x140037926`
- `ntoskrnl!IoSynchronousCallDriver` at `0x140037926`

## pseudocode

```c
__int64 __fastcall UdfPnpSurpriseRemove(void *a1, IRP *a2, __int64 a3)
{
  struct _ERESOURCE *v6; // r14
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  unsigned int v8; // esi

  v6 = (struct _ERESOURCE *)(a3 + 1480);
  UdfAcquireResource(a1, a3 + 1480, 0, 0);
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a3 + 1584));
  if ( *(_DWORD *)(a3 + 52) != 4 )
    *(_DWORD *)(a3 + 52) = 3;
  *(_QWORD *)(a3 + 1640) = 0;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a3 + 1584));
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                             + 6);
  CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
  CurrentStackLocation[-1].Control = 0;
  v8 = IoSynchronousCallDriver(*(_QWORD *)(a3 + 24), a2);
  UdfFlushVolume((__int64)a1, a3, 0, 0, 1, 1);
  if ( UdfCheckForDismount((__int64)a1, a3, 1) )
    ExReleaseResourceLite(v6);
  ExReleaseResourceLite(&Resource);
  UdfCompleteRequest(a1, a2, v8);
  return v8;
}

```

## disassembly

```asm
0x14003787c  mov     rax, rsp
0x14003787f  mov     [rax+8], rbx
0x140037883  mov     [rax+10h], rsi
0x140037887  mov     [rax+18h], r8
0x14003788b  push    rdi
0x14003788c  push    r14
0x14003788e  push    r15
0x140037890  sub     rsp, 40h
0x140037894  mov     rbx, r8
0x140037897  mov     r15, rdx
0x14003789a  mov     rdi, rcx
0x14003789d  mov     byte ptr [rax-28h], 1
0x1400378a1  lea     r14, [r8+5C8h]
0x1400378a8  xor     r9d, r9d
0x1400378ab  xor     r8d, r8d
0x1400378ae  mov     rdx, r14
0x1400378b1  call    UdfAcquireResource
0x1400378b6  lea     rsi, [rbx+630h]
0x1400378bd  mov     rcx, rsi; FastMutex
0x1400378c0  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400378c7  nop     dword ptr [rax+rax+00h]
0x1400378cc  cmp     dword ptr [rbx+34h], 4
0x1400378d0  jz      short loc_1400378D9
0x1400378d2  mov     dword ptr [rbx+34h], 3
0x1400378d9  mov     qword ptr [rbx+668h], 0
0x1400378e4  mov     rcx, rsi; FastMutex
0x1400378e7  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400378ee  nop     dword ptr [rax+rax+00h]
0x1400378f3  mov     rax, [r15+0B8h]
0x1400378fa  movups  xmm0, xmmword ptr [rax]
0x1400378fd  movups  xmmword ptr [rax-48h], xmm0
0x140037901  movups  xmm1, xmmword ptr [rax+10h]
0x140037905  movups  xmmword ptr [rax-38h], xmm1
0x140037909  movups  xmm0, xmmword ptr [rax+20h]
0x14003790d  movups  xmmword ptr [rax-28h], xmm0
0x140037911  movsd   xmm1, qword ptr [rax+30h]
0x140037916  movsd   qword ptr [rax-18h], xmm1
0x14003791b  mov     byte ptr [rax-45h], 0
0x14003791f  mov     rdx, r15
0x140037922  mov     rcx, [rbx+18h]
0x140037926  call    cs:__imp_IoSynchronousCallDriver
0x14003792d  nop     dword ptr [rax+rax+00h]
0x140037932  mov     esi, eax
0x140037934  mov     [rsp+58h+var_30], 1; char
0x140037939  mov     [rsp+58h+var_38], 1; char
0x14003793e  xor     r9d, r9d
0x140037941  xor     r8d, r8d
0x140037944  mov     rdx, rbx
0x140037947  mov     rcx, rdi; int
0x14003794a  call    UdfFlushVolume
0x14003794f  mov     r8b, 1
0x140037952  mov     rdx, rbx
0x140037955  mov     rcx, rdi
0x140037958  call    UdfCheckForDismount
0x14003795d  mov     [rsp+58h+var_28], al
0x140037961  test    al, al
0x140037963  jz      short loc_140037974
0x140037965  mov     rcx, r14; Resource
0x140037968  call    cs:__imp_ExReleaseResourceLite
0x14003796f  nop     dword ptr [rax+rax+00h]
0x140037974  lea     rcx, Resource; Resource
0x14003797b  call    cs:__imp_ExReleaseResourceLite
0x140037982  nop     dword ptr [rax+rax+00h]
0x140037987  mov     r8d, esi
0x14003798a  mov     rdx, r15
0x14003798d  mov     rcx, rdi
0x140037990  call    UdfCompleteRequest
0x140037995  mov     eax, esi
0x140037997  mov     rbx, [rsp+58h+arg_0]
0x14003799c  mov     rsi, [rsp+58h+arg_8]
0x1400379a1  add     rsp, 40h
0x1400379a5  pop     r15
0x1400379a7  pop     r14
0x1400379a9  pop     rdi
0x1400379aa  retn
0x14005c0bf  push    rbp
0x14005c0c1  sub     rsp, 30h
0x14005c0c5  mov     rbp, rdx
0x14005c0c8  cmp     byte ptr [rbp+30h], 0
0x14005c0cc  jz      short loc_14005C0E6
0x14005c0ce  mov     rcx, [rbp+70h]
0x14005c0d2  add     rcx, 5C8h; Resource
0x14005c0d9  call    cs:__imp_ExReleaseResourceLite
0x14005c0e0  nop     dword ptr [rax+rax+00h]
0x14005c0e5  nop
0x14005c0e6  lea     rcx, Resource; Resource
0x14005c0ed  call    cs:__imp_ExReleaseResourceLite
0x14005c0f4  nop     dword ptr [rax+rax+00h]
0x14005c0f9  nop
0x14005c0fa  add     rsp, 30h
0x14005c0fe  pop     rbp
0x14005c0ff  retn
```
