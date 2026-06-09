# VmxReadWrite

- ea: `0x140001330`
- end: `0x140001573`
- name: `VmxReadWrite`
- size: `579`
- prototype: `__int64 __fastcall(KSPIN_LOCK *, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140001330`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400014ba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400014ba`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400014dc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000155b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400014dc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000155b`
- `ntoskrnl!ExAllocatePool2` at `0x14000149b`
- `ntoskrnl!ExAllocatePool2` at `0x14000149b`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140001513`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140001513`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000138a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000138a`

## pseudocode

```c
__int64 __fastcall VmxReadWrite(KSPIN_LOCK *a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v5; // rdi
  __int64 v6; // r12
  KSPIN_LOCK v7; // r15
  struct _NPAGED_LOOKASIDE_LIST *DeviceExtension; // rcx
  _BYTE *v9; // rax
  _BYTE *v10; // rsi
  VMX_GLOBAL_DATA *v12; // rcx
  struct _NPAGED_LOOKASIDE_LIST *Pool2; // rax
  KSPIN_LOCK *v14; // r13
  KIRQL v15; // dl
  __int64 *v16; // r14
  __int64 **v17; // rcx

  v2 = *(_QWORD *)(a2 + 184);
  v5 = *(_QWORD *)(v2 + 24);
  if ( v5 >= 0 )
  {
    v6 = *(unsigned int *)(v2 + 8);
    v7 = *a1;
    if ( (unsigned __int64)(v5 + v6) <= *(_QWORD *)(*a1 + 16) )
    {
      DeviceExtension = (struct _NPAGED_LOOKASIDE_LIST *)WPP_MAIN_CB.DeviceExtension;
      if ( !WPP_MAIN_CB.DeviceExtension )
      {
        Pool2 = (struct _NPAGED_LOOKASIDE_LIST *)ExAllocatePool2(66, 128, 538996054);
        WPP_MAIN_CB.DeviceExtension = Pool2;
        if ( !Pool2 )
          goto LABEL_10;
        ExInitializeNPagedLookasideList(Pool2, 0, 0, 0x200u, 0xC0u, 0x31506D56u, 0x20u);
        DeviceExtension = (struct _NPAGED_LOOKASIDE_LIST *)WPP_MAIN_CB.DeviceExtension;
      }
      v9 = ExAllocateFromNPagedLookasideList(DeviceExtension);
      v10 = v9;
      if ( v9 )
      {
        v9[80] = 1;
        *((_QWORD *)v9 + 4) = 0;
        *((_QWORD *)v9 + 3) = 0;
        v9[83] = 0;
        *((_WORD *)v9 + 66) = 0;
        *(_QWORD *)v9 = &VMX_RAID5_PARITY_TRANSFER_PACKET::`vftable';
        goto LABEL_6;
      }
LABEL_10:
      v14 = a1 + 1;
      v15 = KeAcquireSpinLockRaiseToDpc(a1 + 1);
      if ( *((_BYTE *)a1 + 40) )
      {
        v16 = (__int64 *)(a1 + 3);
        *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
        v17 = (__int64 **)v16[1];
        if ( *v17 != v16 )
          __fastfail(3u);
        *(_QWORD *)(a2 + 176) = v17;
        *(_QWORD *)(a2 + 168) = v16;
        *v17 = (__int64 *)(a2 + 168);
        v16[1] = a2 + 168;
        KeReleaseSpinLock(v14, v15);
        return 259;
      }
      v10 = (_BYTE *)a1[2];
      *((_BYTE *)a1 + 40) = 1;
      KeReleaseSpinLock(a1 + 1, v15);
LABEL_6:
      *((_QWORD *)v10 + 3) = *(_QWORD *)(a2 + 8);
      *((_QWORD *)v10 + 5) = VmxpReadWriteCompletionRoutine;
      *((_QWORD *)v10 + 6) = v7;
      *((_QWORD *)v10 + 4) = a2;
      *((_QWORD *)v10 + 2) = v5;
      *((_DWORD *)v10 + 2) = v6;
      *((_QWORD *)v10 + 7) = *(_QWORD *)(a2 + 152);
      *((_DWORD *)v10 + 16) = *(_DWORD *)(a2 + 16);
      *((_QWORD *)v10 + 9) = *(_QWORD *)(a2 + 192);
      v10[81] = *(_BYTE *)(v2 + 2);
      v10[82] = *(_BYTE *)v2 == 3;
      *((_QWORD *)v10 + 22) = a1;
      *((_QWORD *)v10 + 23) = a2;
      *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
      (*(void (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)v10 + 6) + 8LL))(*((_QWORD *)v10 + 6), v10);
      return 259;
    }
  }
  v12 = Global;
  *(_QWORD *)(a2 + 56) = 0;
  *(_DWORD *)(a2 + 48) = -1073741811;
  (*((void (__fastcall **)(__int64))v12 + 9))(a2);
  return 3221225485LL;
}

```

## disassembly

```asm
0x140001330  mov     [rsp+arg_10], rbx
0x140001335  push    rbp
0x140001336  push    rdi
0x140001337  push    r12
0x140001339  push    r14
0x14000133b  push    r15
0x14000133d  sub     rsp, 40h
0x140001341  mov     rbx, [rdx+0B8h]
0x140001348  mov     rbp, rdx
0x14000134b  mov     r14, rcx
0x14000134e  mov     rdi, [rbx+18h]
0x140001352  test    rdi, rdi
0x140001355  js      loc_140001464
0x14000135b  mov     r12d, [rbx+8]
0x14000135f  mov     r15, [rcx]
0x140001362  lea     rax, [rdi+r12]
0x140001366  cmp     rax, [r15+10h]
0x14000136a  ja      loc_140001464
0x140001370  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension; Lookaside
0x140001377  mov     [rsp+68h+arg_0], rsi
0x14000137c  mov     [rsp+68h+arg_8], r13
0x140001381  test    rcx, rcx
0x140001384  jz      loc_14000148B
0x14000138a  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140001391  nop     dword ptr [rax+rax+00h]
0x140001396  mov     rsi, rax
0x140001399  test    rax, rax
0x14000139c  jz      loc_1400014B3
0x1400013a2  mov     byte ptr [rax+50h], 1
0x1400013a6  xor     eax, eax
0x1400013a8  mov     [rsi+20h], rax
0x1400013ac  mov     [rsi+18h], rax
0x1400013b0  mov     [rsi+53h], al
0x1400013b3  mov     [rsi+84h], ax
0x1400013ba  lea     rax, ??_7VMX_RAID5_PARITY_TRANSFER_PACKET@@6B@; const VMX_RAID5_PARITY_TRANSFER_PACKET::`vftable'
0x1400013c1  mov     [rsi], rax
0x1400013c4  mov     rax, [rbp+8]
0x1400013c8  mov     rdx, rsi
0x1400013cb  mov     [rsi+18h], rax
0x1400013cf  lea     rax, ?VmxpReadWriteCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpReadWriteCompletionRoutine(VMX_TRANSFER_PACKET *)
0x1400013d6  mov     [rsi+28h], rax
0x1400013da  mov     [rsi+30h], r15
0x1400013de  mov     [rsi+20h], rbp
0x1400013e2  mov     [rsi+10h], rdi
0x1400013e6  mov     [rsi+8], r12d
0x1400013ea  mov     rax, [rbp+98h]
0x1400013f1  mov     [rsi+38h], rax
0x1400013f5  mov     eax, [rbp+10h]
0x1400013f8  mov     [rsi+40h], eax
0x1400013fb  mov     rax, [rbp+0C0h]
0x140001402  mov     [rsi+48h], rax
0x140001406  movzx   eax, byte ptr [rbx+2]
0x14000140a  mov     [rsi+51h], al
0x14000140d  cmp     byte ptr [rbx], 3
0x140001410  setz    al
0x140001413  mov     [rsi+52h], al
0x140001416  mov     [rsi+0B0h], r14
0x14000141d  mov     [rsi+0B8h], rbp
0x140001424  mov     rax, [rbp+0B8h]
0x14000142b  or      byte ptr [rax+3], 1
0x14000142f  mov     rcx, [rsi+30h]
0x140001433  mov     rax, [rcx]
0x140001436  mov     rax, [rax+8]
0x14000143a  call    _guard_dispatch_icall
0x14000143f  mov     rsi, [rsp+68h+arg_0]
0x140001444  mov     eax, 103h
0x140001449  mov     r13, [rsp+68h+arg_8]
0x14000144e  mov     rbx, [rsp+68h+arg_10]
0x140001456  add     rsp, 40h
0x14000145a  pop     r15
0x14000145c  pop     r14
0x14000145e  pop     r12
0x140001460  pop     rdi
0x140001461  pop     rbp
0x140001462  retn
0x140001464  mov     rcx, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14000146b  xor     eax, eax
0x14000146d  mov     [rdx+38h], rax
0x140001471  mov     dword ptr [rdx+30h], 0C000000Dh
0x140001478  mov     rax, [rcx+48h]
0x14000147c  mov     rcx, rbp
0x14000147f  call    _guard_dispatch_icall
0x140001484  mov     eax, 0C000000Dh
0x140001489  jmp     short loc_14000144E
0x14000148b  mov     edx, 80h
0x140001490  mov     ecx, 42h ; 'B'
0x140001495  mov     r8d, 20206D56h
0x14000149b  call    cs:__imp_ExAllocatePool2
0x1400014a2  nop     dword ptr [rax+rax+00h]
0x1400014a7  mov     cs:WPP_MAIN_CB.DeviceExtension, rax
0x1400014ae  test    rax, rax
0x1400014b1  jnz     short loc_1400014ED
0x1400014b3  lea     r13, [r14+8]
0x1400014b7  mov     rcx, r13; SpinLock
0x1400014ba  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400014c1  nop     dword ptr [rax+rax+00h]
0x1400014c6  cmp     byte ptr [r14+28h], 0
0x1400014cb  movzx   edx, al; NewIrql
0x1400014ce  jnz     short loc_14000152B
0x1400014d0  mov     rsi, [r14+10h]
0x1400014d4  mov     rcx, r13; SpinLock
0x1400014d7  mov     byte ptr [r14+28h], 1
0x1400014dc  call    cs:__imp_KeReleaseSpinLock
0x1400014e3  nop     dword ptr [rax+rax+00h]
0x1400014e8  jmp     loc_1400013C4
0x1400014ed  mov     [rsp+68h+Depth], 20h ; ' '; Depth
0x1400014f4  mov     r9d, 200h; Flags
0x1400014fa  mov     [rsp+68h+Tag], 31506D56h; Tag
0x140001502  xor     r8d, r8d; Free
0x140001505  xor     edx, edx; Allocate
0x140001507  mov     [rsp+68h+Size], 0C0h; Size
0x140001510  mov     rcx, rax; Lookaside
0x140001513  call    cs:__imp_ExInitializeNPagedLookasideList
0x14000151a  nop     dword ptr [rax+rax+00h]
0x14000151f  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140001526  jmp     loc_14000138A
0x14000152b  mov     rcx, [rbp+0B8h]
0x140001532  add     r14, 18h
0x140001536  or      byte ptr [rcx+3], 1
0x14000153a  mov     rcx, [r14+8]
0x14000153e  cmp     [rcx], r14
0x140001541  jnz     short loc_14000156C
0x140001543  lea     rax, [rbp+0A8h]
0x14000154a  mov     [rax+8], rcx
0x14000154e  mov     [rax], r14
0x140001551  mov     [rcx], rax
0x140001554  mov     rcx, r13; SpinLock
0x140001557  mov     [r14+8], rax
0x14000155b  call    cs:__imp_KeReleaseSpinLock
0x140001562  nop     dword ptr [rax+rax+00h]
0x140001567  jmp     loc_14000143F
0x14000156c  mov     ecx, 3
0x140001571  int     29h; Win8: RtlFailFast(ecx)
```
