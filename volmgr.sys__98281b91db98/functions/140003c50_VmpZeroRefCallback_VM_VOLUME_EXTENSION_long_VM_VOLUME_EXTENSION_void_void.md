# VmpZeroRefCallback(VM_VOLUME_EXTENSION *,long (*)(VM_VOLUME_EXTENSION *,void *),void *)

- ea: `0x140003c50`
- end: `0x140003ce2`
- name: `?VmpZeroRefCallback@@YAJPEAVVM_VOLUME_EXTENSION@@P6AJ0PEAX@Z1@Z`
- size: `146`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, int (*)(struct VM_VOLUME_EXTENSION *, void *), void *)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000e888`
- `0x14000eba0`
- `0x14000f56c`
- `0x140010ad8`
- `0x140012710`
- `0x140015da0`
- `0x140016680`
- `0x140016aa0`

## callees

- `0x140003cf0`
- `0x140005090`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003c99`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003c99`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140003c89`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140003c89`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003cc0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003cc0`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003c79`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003c79`

## pseudocode

```c
__int64 __fastcall VmpZeroRefCallback(
        struct VM_VOLUME_EXTENSION *a1,
        __int64 (__fastcall *a2)(struct VM_VOLUME_EXTENSION *, void *),
        void *a3)
{
  KIRQL v6; // di

  KeWaitForSingleObject((char *)a1 + 56, Executive, 0, 0, 0);
  ExWaitForRundownProtectionReleaseCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)a1 + 14));
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 3);
  LODWORD(a3) = a2(a1, a3);
  KeReleaseSpinLock((PKSPIN_LOCK)a1 + 3, v6);
  VmpReleaseRundownExclusive(a1);
  return (unsigned int)a3;
}

```

## disassembly

```asm
0x140003c50  push    rbx
0x140003c52  push    rbp
0x140003c53  push    rsi
0x140003c54  push    rdi
0x140003c55  push    r14
0x140003c57  sub     rsp, 30h
0x140003c5b  mov     rbx, r8
0x140003c5e  mov     [rsp+58h+Timeout], 0; Timeout
0x140003c67  mov     rbp, rdx
0x140003c6a  mov     r14, rcx
0x140003c6d  add     rcx, 38h ; '8'; Object
0x140003c71  xor     r8d, r8d; WaitMode
0x140003c74  xor     edx, edx; WaitReason
0x140003c76  xor     r9d, r9d; Alertable
0x140003c79  call    cs:__imp_KeWaitForSingleObject
0x140003c80  nop     dword ptr [rax+rax+00h]
0x140003c85  mov     rcx, [r14+70h]; RunRef
0x140003c89  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x140003c90  nop     dword ptr [rax+rax+00h]
0x140003c95  lea     rcx, [r14+18h]; SpinLock
0x140003c99  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003ca0  nop     dword ptr [rax+rax+00h]
0x140003ca5  mov     rdx, rbx
0x140003ca8  mov     rcx, r14
0x140003cab  movzx   edi, al
0x140003cae  mov     rax, rbp
0x140003cb1  call    _guard_dispatch_icall
0x140003cb6  movzx   edx, dil; NewIrql
0x140003cba  lea     rcx, [r14+18h]; SpinLock
0x140003cbe  mov     ebx, eax
0x140003cc0  call    cs:__imp_KeReleaseSpinLock
0x140003cc7  nop     dword ptr [rax+rax+00h]
0x140003ccc  mov     rcx, r14; struct VM_VOLUME_EXTENSION *
0x140003ccf  call    ?VmpReleaseRundownExclusive@@YAXPEAVVM_VOLUME_EXTENSION@@@Z; VmpReleaseRundownExclusive(VM_VOLUME_EXTENSION *)
0x140003cd4  mov     eax, ebx
0x140003cd6  add     rsp, 30h
0x140003cda  pop     r14
0x140003cdc  pop     rdi
0x140003cdd  pop     rsi
0x140003cde  pop     rbp
0x140003cdf  pop     rbx
0x140003ce0  retn
```
