# VmxpMirrorRegenerationCompletionRoutine(VMX_TRANSFER_PACKET *)

- ea: `0x140013be0`
- end: `0x140013d97`
- name: `?VmxpMirrorRegenerationCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `439`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140003cf0`
- `0x140005aa0`
- `0x140013be0`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013c21`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013c21`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013c56`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013cad`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013d0c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013d36`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013c56`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013cad`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013d0c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013d36`
- `ntoskrnl!KeSetEvent` at `0x140013c6b`
- `ntoskrnl!KeSetEvent` at `0x140013c6b`

## pseudocode

```c
void __fastcall VmxpMirrorRegenerationCompletionRoutine(struct VMX_TRANSFER_PACKET *a1)
{
  __int64 v1; // rbx
  __int64 v2; // rsi
  int v3; // edi
  VMX_OVERLAPPED_IO_MANAGER *v4; // r12
  __int64 v5; // rbp
  KSPIN_LOCK *v6; // r14
  KIRQL v7; // al
  _QWORD *v8; // rbx
  KIRQL v9; // r15
  __int64 v10; // rcx
  _QWORD *v11; // rdx
  __int64 v12; // rdx
  _QWORD *v13; // rcx
  int v14; // r8d

  v1 = *((_QWORD *)a1 + 6);
  v2 = *((_QWORD *)a1 + 28);
  v3 = *((_DWORD *)a1 + 24);
  v4 = (VMX_OVERLAPPED_IO_MANAGER *)(v1 + 104);
  v5 = *(_QWORD *)(v2 + 112);
  *((_DWORD *)a1 + 42) = 0;
  VMX_OVERLAPPED_IO_MANAGER::ReleaseIoRegion(
    (VMX_OVERLAPPED_IO_MANAGER *)(v1 + 104),
    (struct VMX_OVERLAP_TRANSFER_PACKET *)v5);
  v6 = (KSPIN_LOCK *)(v1 + 24);
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 24));
  v8 = (_QWORD *)(v2 + 56);
  v9 = v7;
  if ( v3 < 0 )
    *(_BYTE *)(v2 + 66) = 1;
  else
    *v8 += *(unsigned int *)(v5 + 8);
  if ( *(_BYTE *)(v2 + 65) )
  {
    *(_WORD *)(v2 + 64) = 0;
    KeReleaseSpinLock(v6, v7);
    KeSetEvent((PRKEVENT)(v2 + 72), 0, 0);
    return;
  }
  if ( *(_BYTE *)(v2 + 66) )
  {
    v10 = *(_QWORD *)(v2 + 8);
    if ( *(_QWORD *)(v10 + 8) == v2 + 8 )
    {
      v11 = *(_QWORD **)(v2 + 16);
      if ( *v11 == v2 + 8 )
      {
        *v11 = v10;
        *(_QWORD *)(v10 + 8) = v11;
        KeReleaseSpinLock(v6, v7);
LABEL_10:
        (**(void (__fastcall ***)(__int64, __int64))v2)(v2, 1);
        return;
      }
    }
    goto LABEL_15;
  }
  if ( *v8 >= *(_QWORD *)(v2 + 48) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    v12 = *(_QWORD *)(v2 + 8);
    if ( *(_QWORD *)(v12 + 8) == v2 + 8 )
    {
      v13 = *(_QWORD **)(v2 + 16);
      if ( *v13 == v2 + 8 )
      {
        *v13 = v12;
        *(_QWORD *)(v12 + 8) = v13;
        KeReleaseSpinLock(v6, v9);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 24LL))(v2);
        goto LABEL_10;
      }
    }
LABEL_15:
    __fastfail(3u);
  }
  KeReleaseSpinLock(v6, v7);
  v14 = 0x10000;
  *(_QWORD *)(v5 + 16) = *v8;
  if ( (unsigned __int64)(*v8 + 0x10000LL) > *(_QWORD *)(v2 + 48) )
    v14 = *(_DWORD *)(v2 + 48) - *(_DWORD *)v8;
  *(_DWORD *)(v5 + 8) = v14;
  *(_QWORD *)(v5 + 40) = VmxpMirrorRegenerationPhase1;
  *(_QWORD *)(v5 + 56) = 0;
  VMX_OVERLAPPED_IO_MANAGER::AcquireIoRegion(v4, (struct VMX_OVERLAP_TRANSFER_PACKET *)v5, 1);
}

```

## disassembly

```asm
0x140013be0  push    rbx
0x140013be2  push    rbp
0x140013be3  push    rsi
0x140013be4  push    rdi
0x140013be5  push    r12
0x140013be7  push    r14
0x140013be9  push    r15
0x140013beb  sub     rsp, 20h
0x140013bef  mov     rbx, [rcx+30h]
0x140013bf3  mov     rsi, [rcx+0E0h]
0x140013bfa  mov     edi, [rcx+60h]
0x140013bfd  lea     r12, [rbx+68h]
0x140013c01  mov     rbp, [rsi+70h]
0x140013c05  mov     dword ptr [rcx+0A8h], 0
0x140013c0f  mov     rdx, rbp; struct VMX_OVERLAP_TRANSFER_PACKET *
0x140013c12  mov     rcx, r12; this
0x140013c15  call    ?ReleaseIoRegion@VMX_OVERLAPPED_IO_MANAGER@@QEAAXPEAVVMX_OVERLAP_TRANSFER_PACKET@@@Z; VMX_OVERLAPPED_IO_MANAGER::ReleaseIoRegion(VMX_OVERLAP_TRANSFER_PACKET *)
0x140013c1a  lea     r14, [rbx+18h]
0x140013c1e  mov     rcx, r14; SpinLock
0x140013c21  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013c28  nop     dword ptr [rax+rax+00h]
0x140013c2d  lea     rbx, [rsi+38h]
0x140013c31  mov     r15b, al
0x140013c34  test    edi, edi
0x140013c36  js      short loc_140013C40
0x140013c38  mov     ecx, [rbp+8]
0x140013c3b  add     [rbx], rcx
0x140013c3e  jmp     short loc_140013C44
0x140013c40  mov     byte ptr [rsi+42h], 1
0x140013c44  cmp     byte ptr [rsi+41h], 0
0x140013c48  jz      short loc_140013C7C
0x140013c4a  mov     dl, r15b; NewIrql
0x140013c4d  mov     word ptr [rsi+40h], 0
0x140013c53  mov     rcx, r14; SpinLock
0x140013c56  call    cs:__imp_KeReleaseSpinLock
0x140013c5d  nop     dword ptr [rax+rax+00h]
0x140013c62  lea     rcx, [rsi+48h]; Event
0x140013c66  xor     r8d, r8d; Wait
0x140013c69  xor     edx, edx; Increment
0x140013c6b  call    cs:__imp_KeSetEvent
0x140013c72  nop     dword ptr [rax+rax+00h]
0x140013c77  jmp     loc_140013D87
0x140013c7c  cmp     byte ptr [rsi+42h], 0
0x140013c80  jz      short loc_140013CD1
0x140013c82  lea     rax, [rsi+8]
0x140013c86  mov     rcx, [rax]
0x140013c89  cmp     [rcx+8], rax
0x140013c8d  jnz     loc_140013D29
0x140013c93  mov     rdx, [rax+8]
0x140013c97  cmp     [rdx], rax
0x140013c9a  jnz     loc_140013D29
0x140013ca0  mov     [rdx], rcx
0x140013ca3  mov     [rcx+8], rdx
0x140013ca7  mov     dl, r15b; NewIrql
0x140013caa  mov     rcx, r14; SpinLock
0x140013cad  call    cs:__imp_KeReleaseSpinLock
0x140013cb4  nop     dword ptr [rax+rax+00h]
0x140013cb9  mov     rax, [rsi]
0x140013cbc  mov     edx, 1
0x140013cc1  mov     rcx, rsi
0x140013cc4  mov     rax, [rax]
0x140013cc7  call    _guard_dispatch_icall
0x140013ccc  jmp     loc_140013D87
0x140013cd1  mov     rax, [rsi+30h]
0x140013cd5  cmp     [rbx], rax
0x140013cd8  jb      short loc_140013D30
0x140013cda  mov     rax, [rsi]
0x140013cdd  mov     rcx, rsi
0x140013ce0  mov     rax, [rax+10h]
0x140013ce4  call    _guard_dispatch_icall
0x140013ce9  lea     rax, [rsi+8]
0x140013ced  mov     rdx, [rax]
0x140013cf0  cmp     [rdx+8], rax
0x140013cf4  jnz     short loc_140013D29
0x140013cf6  mov     rcx, [rax+8]
0x140013cfa  cmp     [rcx], rax
0x140013cfd  jnz     short loc_140013D29
0x140013cff  mov     [rcx], rdx
0x140013d02  mov     [rdx+8], rcx
0x140013d06  mov     dl, r15b; NewIrql
0x140013d09  mov     rcx, r14; SpinLock
0x140013d0c  call    cs:__imp_KeReleaseSpinLock
0x140013d13  nop     dword ptr [rax+rax+00h]
0x140013d18  mov     rax, [rsi]
0x140013d1b  mov     rcx, rsi
0x140013d1e  mov     rax, [rax+18h]
0x140013d22  call    _guard_dispatch_icall
0x140013d27  jmp     short loc_140013CB9
0x140013d29  mov     ecx, 3
0x140013d2e  int     29h; Win8: RtlFailFast(ecx)
0x140013d30  mov     dl, r15b; NewIrql
0x140013d33  mov     rcx, r14; SpinLock
0x140013d36  call    cs:__imp_KeReleaseSpinLock
0x140013d3d  nop     dword ptr [rax+rax+00h]
0x140013d42  mov     rax, [rbx]
0x140013d45  mov     r8d, 10000h
0x140013d4b  mov     [rbp+10h], rax
0x140013d4f  mov     rax, [rbx]
0x140013d52  add     rax, r8
0x140013d55  cmp     rax, [rsi+30h]
0x140013d59  jbe     short loc_140013D62
0x140013d5b  mov     r8d, [rsi+30h]
0x140013d5f  sub     r8d, [rbx]
0x140013d62  mov     [rbp+8], r8d
0x140013d66  lea     rax, ?VmxpMirrorRegenerationPhase1@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpMirrorRegenerationPhase1(VMX_TRANSFER_PACKET *)
0x140013d6d  mov     r8b, 1; unsigned __int8
0x140013d70  mov     [rbp+28h], rax
0x140013d74  mov     rdx, rbp; struct VMX_OVERLAP_TRANSFER_PACKET *
0x140013d77  mov     qword ptr [rbp+38h], 0
0x140013d7f  mov     rcx, r12; this
0x140013d82  call    ?AcquireIoRegion@VMX_OVERLAPPED_IO_MANAGER@@QEAAXPEAVVMX_OVERLAP_TRANSFER_PACKET@@E@Z; VMX_OVERLAPPED_IO_MANAGER::AcquireIoRegion(VMX_OVERLAP_TRANSFER_PACKET *,uchar)
0x140013d87  add     rsp, 20h
0x140013d8b  pop     r15
0x140013d8d  pop     r14
0x140013d8f  pop     r12
0x140013d91  pop     rdi
0x140013d92  pop     rsi
0x140013d93  pop     rbp
0x140013d94  pop     rbx
0x140013d95  retn
```
