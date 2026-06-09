# UdfSeqCacheDeallocate

- ea: `0x140019f5c`
- end: `0x14001a057`
- name: `UdfSeqCacheDeallocate`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14002c164`

## callees

- `0x140004340`
- `0x14000a2e8`
- `0x140019f5c`
- `0x14004ce50`

## import_xrefs

- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140019fdc`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140019fff`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140019fdc`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140019fff`
- `ntoskrnl!ExDeleteResourceLite` at `0x140019fae`
- `ntoskrnl!ExDeleteResourceLite` at `0x140019fc1`
- `ntoskrnl!ExDeleteResourceLite` at `0x140019fae`
- `ntoskrnl!ExDeleteResourceLite` at `0x140019fc1`
- `ntoskrnl!IoFreeIrp` at `0x140019f96`
- `ntoskrnl!IoFreeIrp` at `0x140019f96`

## pseudocode

```c
__int64 __fastcall UdfSeqCacheDeallocate(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  IRP *v8; // rcx
  LARGE_MCB *v9; // rcx
  LARGE_MCB *v10; // rcx
  __int64 v11; // rcx
  __int64 result; // rax
  __int64 v13; // [rsp+60h] [rbp+18h] BYREF

  if ( a3 )
  {
    v13 = a3;
    UdfFreePool(a3 + 712);
    v8 = *(IRP **)(a3 + 648);
    if ( v8 )
      IoFreeIrp(v8);
    if ( a4 )
    {
      ExDeleteResourceLite((PERESOURCE)(a3 + 448));
      ExDeleteResourceLite((PERESOURCE)(a3 + 344));
    }
    v9 = *(LARGE_MCB **)(a3 + 728);
    if ( v9 )
    {
      FsRtlUninitializeLargeMcb(v9);
      UdfFreePool(a3 + 728);
    }
    v10 = *(LARGE_MCB **)(a3 + 736);
    if ( v10 )
    {
      FsRtlUninitializeLargeMcb(v10);
      UdfFreePool(a3 + 736);
    }
    *(_QWORD *)(a3 + 752) = 0;
    UdfAcquireResource(a1, a2 + 136, 0, 0);
    UdfFreePool(&v13);
    *(_DWORD *)(a2 + 48) &= ~0x200000u;
    return UdfReleaseDevice(v11, a2, 0);
  }
  return result;
}

```

## disassembly

```asm
0x140019f5c  test    r8, r8
0x140019f5f  jz      locret_14001A055
0x140019f65  mov     [rsp+arg_10], r8
0x140019f6a  push    rbx
0x140019f6b  push    rbp
0x140019f6c  push    rsi
0x140019f6d  push    rdi
0x140019f6e  sub     rsp, 28h
0x140019f72  mov     rbp, rcx
0x140019f75  mov     dil, r9b
0x140019f78  lea     rcx, [r8+2C8h]
0x140019f7f  mov     rbx, r8
0x140019f82  mov     rsi, rdx
0x140019f85  call    UdfFreePool
0x140019f8a  mov     rcx, [rbx+288h]; Irp
0x140019f91  test    rcx, rcx
0x140019f94  jz      short loc_140019FA2
0x140019f96  call    cs:__imp_IoFreeIrp
0x140019f9d  nop     dword ptr [rax+rax+00h]
0x140019fa2  test    dil, dil
0x140019fa5  jz      short loc_140019FCD
0x140019fa7  lea     rcx, [rbx+1C0h]; Resource
0x140019fae  call    cs:__imp_ExDeleteResourceLite
0x140019fb5  nop     dword ptr [rax+rax+00h]
0x140019fba  lea     rcx, [rbx+158h]; Resource
0x140019fc1  call    cs:__imp_ExDeleteResourceLite
0x140019fc8  nop     dword ptr [rax+rax+00h]
0x140019fcd  lea     rdi, [rbx+2D8h]
0x140019fd4  mov     rcx, [rdi]; Mcb
0x140019fd7  test    rcx, rcx
0x140019fda  jz      short loc_140019FF0
0x140019fdc  call    cs:__imp_FsRtlUninitializeLargeMcb
0x140019fe3  nop     dword ptr [rax+rax+00h]
0x140019fe8  mov     rcx, rdi
0x140019feb  call    UdfFreePool
0x140019ff0  lea     rdi, [rbx+2E0h]
0x140019ff7  mov     rcx, [rdi]; Mcb
0x140019ffa  test    rcx, rcx
0x140019ffd  jz      short loc_14001A013
0x140019fff  call    cs:__imp_FsRtlUninitializeLargeMcb
0x14001a006  nop     dword ptr [rax+rax+00h]
0x14001a00b  mov     rcx, rdi
0x14001a00e  call    UdfFreePool
0x14001a013  lea     rdx, [rsi+88h]
0x14001a01a  mov     qword ptr [rbx+2F0h], 0
0x14001a025  xor     r9d, r9d
0x14001a028  xor     r8d, r8d
0x14001a02b  mov     rcx, rbp
0x14001a02e  call    UdfAcquireResource
0x14001a033  lea     rcx, [rsp+48h+arg_10]
0x14001a038  call    UdfFreePool
0x14001a03d  btr     dword ptr [rsi+30h], 15h
0x14001a042  xor     r8d, r8d
0x14001a045  mov     rdx, rsi
0x14001a048  call    UdfReleaseDevice
0x14001a04d  add     rsp, 28h
0x14001a051  pop     rdi
0x14001a052  pop     rsi
0x14001a053  pop     rbp
0x14001a054  pop     rbx
0x14001a055  retn
```
