# VMX_PARITY_IO_MANAGER::StartReadForUpdateParity(unsigned __int64,ulong,VMX_IO_OBJECT *,_ETHREAD *,ulong,_FILE_OBJECT *,uchar)

- ea: `0x140012244`
- end: `0x1400123f3`
- name: `?StartReadForUpdateParity@VMX_PARITY_IO_MANAGER@@QEAAX_KKPEAVVMX_IO_OBJECT@@PEAU_ETHREAD@@KPEAU_FILE_OBJECT@@E@Z`
- size: `431`
- prototype: `void __fastcall(VMX_PARITY_IO_MANAGER *__hidden this, unsigned __int64, unsigned int, struct VMX_IO_OBJECT *, struct _ETHREAD *, unsigned int, struct _FILE_OBJECT *, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140018340`

## callees

- `0x140002470`
- `0x14000b420`
- `0x140012244`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012291`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012291`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001230d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400123c8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001230d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400123c8`

## pseudocode

```c
void __fastcall VMX_PARITY_IO_MANAGER::StartReadForUpdateParity(
        VMX_PARITY_IO_MANAGER *this,
        unsigned __int64 a2,
        int a3,
        struct VMX_IO_OBJECT *a4,
        struct _ETHREAD *a5,
        unsigned int a6,
        struct _FILE_OBJECT *a7,
        char a8)
{
  unsigned __int64 v9; // r15
  unsigned __int64 v11; // rdx
  __int64 v13; // rdi
  KSPIN_LOCK *v14; // rbp
  KIRQL v15; // al
  __int64 v16; // rcx
  KIRQL v17; // r14
  _BYTE *v18; // rbx
  _QWORD *v19; // rcx
  __int64 v20; // rcx

  v9 = a2 / *((unsigned int *)this + 1);
  v11 = v9 % *(unsigned int *)this;
  v13 = *((_QWORD *)this + 3) + 16LL * (unsigned int)v11;
  v14 = (KSPIN_LOCK *)(*((_QWORD *)this + 2) + 8LL * (unsigned int)v11);
  v15 = KeAcquireSpinLockRaiseToDpc(v14);
  v16 = *(_QWORD *)(v13 + 8);
  v17 = v15;
  while ( v16 != v13 )
  {
    if ( v9 == *(_QWORD *)(v16 + 40) )
      goto LABEL_8;
    v16 = *(_QWORD *)(v16 + 8);
  }
  v18 = VMX_TRANSFER_PACKET::operator new(0xC8u);
  if ( !v18 )
  {
LABEL_8:
    KeReleaseSpinLock(v14, v17);
    return;
  }
  *((_QWORD *)v18 + 4) = 0;
  *((_QWORD *)v18 + 3) = 0;
  v18[83] = 0;
  *((_WORD *)v18 + 66) = 0;
  *(_QWORD *)v18 = &VMX_RAID5_PARITY_TRANSFER_PACKET::`vftable';
  if ( (int)VMX_TRANSFER_PACKET::AllocateMdl((VMX_TRANSFER_PACKET *)v18, *((_DWORD *)this + 1)) < 0 )
  {
    (**(void (__fastcall ***)(_BYTE *, __int64))v18)(v18, 1);
    goto LABEL_8;
  }
  *((_DWORD *)v18 + 2) = a3;
  *((_QWORD *)v18 + 5) = VmxpRaid5UpdateParityCompletionRoutine;
  *((_QWORD *)v18 + 7) = a5;
  *((_DWORD *)v18 + 16) = a6;
  *((_QWORD *)v18 + 9) = a7;
  v18[81] = a8;
  *((_QWORD *)v18 + 2) = a2;
  *((_QWORD *)v18 + 6) = a4;
  v18[82] = 1;
  *((_WORD *)v18 + 68) = 0;
  *((_QWORD *)v18 + 21) = v18 + 160;
  *((_QWORD *)v18 + 20) = v18 + 160;
  *((_QWORD *)v18 + 22) = this;
  *((_QWORD *)v18 + 23) = v9;
  v19 = *(_QWORD **)(v13 + 8);
  if ( *v19 != v13 )
    __fastfail(3u);
  *((_QWORD *)v18 + 19) = v19;
  *((_QWORD *)v18 + 18) = v13;
  *v19 = v18 + 144;
  *(_QWORD *)(v13 + 8) = v18 + 144;
  KeReleaseSpinLock(v14, v17);
  v20 = *((_QWORD *)v18 + 6);
  *((_DWORD *)v18 + 3) = 33685506;
  (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v20 + 8LL))(v20, v18);
}

```

## disassembly

```asm
0x140012244  mov     [rsp+arg_10], r8d
0x140012249  push    rbx
0x14001224a  push    rbp
0x14001224b  push    rsi
0x14001224c  push    rdi
0x14001224d  push    r12
0x14001224f  push    r13
0x140012251  push    r14
0x140012253  push    r15
0x140012255  sub     rsp, 28h
0x140012259  mov     r10d, [rcx+4]
0x14001225d  mov     r12, rdx
0x140012260  xor     edx, edx
0x140012262  mov     rax, r12
0x140012265  div     r10
0x140012268  mov     r10d, [rcx]
0x14001226b  xor     edx, edx
0x14001226d  mov     r15, rax
0x140012270  mov     rsi, rcx
0x140012273  div     r10
0x140012276  mov     r13, r9
0x140012279  mov     edi, edx
0x14001227b  shl     rdi, 4
0x14001227f  add     rdi, [rcx+18h]
0x140012283  mov     rcx, [rcx+10h]
0x140012287  mov     r8d, edx
0x14001228a  lea     rbp, [rcx+r8*8]
0x14001228e  mov     rcx, rbp; SpinLock
0x140012291  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012298  nop     dword ptr [rax+rax+00h]
0x14001229d  mov     rcx, [rdi+8]
0x1400122a1  mov     r14b, al
0x1400122a4  cmp     rcx, rdi
0x1400122a7  jz      short loc_1400122B5
0x1400122a9  cmp     r15, [rcx+28h]
0x1400122ad  jz      short loc_140012307
0x1400122af  mov     rcx, [rcx+8]
0x1400122b3  jmp     short loc_1400122A4
0x1400122b5  mov     ecx, 0C8h; unsigned __int64
0x1400122ba  call    ??2VMX_TRANSFER_PACKET@@SAPEAX_K@Z; VMX_TRANSFER_PACKET::operator new(unsigned __int64)
0x1400122bf  mov     rbx, rax
0x1400122c2  xor     eax, eax
0x1400122c4  test    rbx, rbx
0x1400122c7  jz      short loc_140012307
0x1400122c9  mov     [rbx+20h], rax
0x1400122cd  mov     rcx, rbx; this
0x1400122d0  mov     [rbx+18h], rax
0x1400122d4  mov     [rbx+53h], al
0x1400122d7  mov     [rbx+84h], ax
0x1400122de  lea     rax, ??_7VMX_RAID5_PARITY_TRANSFER_PACKET@@6B@; const VMX_RAID5_PARITY_TRANSFER_PACKET::`vftable'
0x1400122e5  mov     [rbx], rax
0x1400122e8  mov     edx, [rsi+4]; unsigned int
0x1400122eb  call    ?AllocateMdl@VMX_TRANSFER_PACKET@@QEAAJK@Z; VMX_TRANSFER_PACKET::AllocateMdl(ulong)
0x1400122f0  test    eax, eax
0x1400122f2  jns     short loc_14001232B
0x1400122f4  mov     rax, [rbx]
0x1400122f7  mov     edx, 1
0x1400122fc  mov     rcx, rbx
0x1400122ff  mov     rax, [rax]
0x140012302  call    _guard_dispatch_icall
0x140012307  mov     dl, r14b; NewIrql
0x14001230a  mov     rcx, rbp; SpinLock
0x14001230d  call    cs:__imp_KeReleaseSpinLock
0x140012314  nop     dword ptr [rax+rax+00h]
0x140012319  add     rsp, 28h
0x14001231d  pop     r15
0x14001231f  pop     r14
0x140012321  pop     r13
0x140012323  pop     r12
0x140012325  pop     rdi
0x140012326  pop     rsi
0x140012327  pop     rbp
0x140012328  pop     rbx
0x140012329  retn
0x14001232b  mov     eax, [rsp+68h+arg_10]
0x140012332  mov     [rbx+8], eax
0x140012335  lea     rax, ?VmxpRaid5UpdateParityCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5UpdateParityCompletionRoutine(VMX_TRANSFER_PACKET *)
0x14001233c  mov     [rbx+28h], rax
0x140012340  mov     rax, [rsp+68h+arg_20]
0x140012348  mov     [rbx+38h], rax
0x14001234c  mov     eax, [rsp+68h+arg_28]
0x140012353  mov     [rbx+40h], eax
0x140012356  mov     rax, [rsp+68h+arg_30]
0x14001235e  mov     [rbx+48h], rax
0x140012362  mov     al, [rsp+68h+arg_38]
0x140012369  mov     [rbx+51h], al
0x14001236c  lea     rax, [rbx+0A0h]
0x140012373  mov     [rbx+10h], r12
0x140012377  mov     [rbx+30h], r13
0x14001237b  mov     byte ptr [rbx+52h], 1
0x14001237f  mov     word ptr [rbx+88h], 0
0x140012388  mov     [rax+8], rax
0x14001238c  mov     [rax], rax
0x14001238f  mov     [rbx+0B0h], rsi
0x140012396  mov     [rbx+0B8h], r15
0x14001239d  mov     rcx, [rdi+8]
0x1400123a1  cmp     [rcx], rdi
0x1400123a4  jz      short loc_1400123AD
0x1400123a6  mov     ecx, 3
0x1400123ab  int     29h; Win8: RtlFailFast(ecx)
0x1400123ad  lea     rax, [rbx+90h]
0x1400123b4  mov     dl, r14b; NewIrql
0x1400123b7  mov     [rax+8], rcx
0x1400123bb  mov     [rax], rdi
0x1400123be  mov     [rcx], rax
0x1400123c1  mov     rcx, rbp; SpinLock
0x1400123c4  mov     [rdi+8], rax
0x1400123c8  call    cs:__imp_KeReleaseSpinLock
0x1400123cf  nop     dword ptr [rax+rax+00h]
0x1400123d4  mov     rcx, [rbx+30h]
0x1400123d8  mov     rdx, rbx
0x1400123db  mov     dword ptr [rbx+0Ch], 2020002h
0x1400123e2  mov     rax, [rcx]
0x1400123e5  mov     rax, [rax+8]
0x1400123e9  call    _guard_dispatch_icall
0x1400123ee  jmp     loc_140012319
```
