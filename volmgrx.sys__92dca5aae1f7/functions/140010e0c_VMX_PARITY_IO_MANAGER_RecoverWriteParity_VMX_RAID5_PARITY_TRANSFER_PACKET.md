# VMX_PARITY_IO_MANAGER::RecoverWriteParity(VMX_RAID5_PARITY_TRANSFER_PACKET *)

- ea: `0x140010e0c`
- end: `0x140010f46`
- name: `?RecoverWriteParity@VMX_PARITY_IO_MANAGER@@QEAAXPEAVVMX_RAID5_PARITY_TRANSFER_PACKET@@@Z`
- size: `314`
- prototype: `void __fastcall(VMX_PARITY_IO_MANAGER *__hidden this, struct VMX_RAID5_PARITY_TRANSFER_PACKET *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140017cd0`

## callees

- `0x140002470`
- `0x140005600`
- `0x140010e0c`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x140010ed0`
- `ntoskrnl!IoBuildPartialMdl` at `0x140010ed0`

## pseudocode

```c
void __fastcall VMX_PARITY_IO_MANAGER::RecoverWriteParity(
        VMX_PARITY_IO_MANAGER *this,
        struct VMX_RAID5_PARITY_TRANSFER_PACKET *a2)
{
  PMDL *v4; // rax
  PMDL *v5; // rbx
  void (__fastcall *v6)(struct VMX_RAID5_PARITY_TRANSFER_PACKET *); // rax
  struct _MDL *v7; // rcx

  *((_QWORD *)a2 + 13) = *((unsigned int *)a2 + 2);
  *((_DWORD *)a2 + 24) = 0;
  v4 = (PMDL *)VMX_TRANSFER_PACKET::operator new(0xD0u);
  v5 = v4;
  if ( !v4 )
    goto LABEL_4;
  v4[4] = 0;
  v4[3] = 0;
  *((_BYTE *)v4 + 83) = 0;
  *((_WORD *)v4 + 66) = 0;
  *v4 = (PMDL)&VMX_RAID5_PARITY_TRANSFER_PACKET::`vftable';
  if ( (int)VMX_TRANSFER_PACKET::AllocateMdl((VMX_TRANSFER_PACKET *)v4, (void *)0xFFF, *((_DWORD *)this + 2)) < 0 )
  {
    ((void (__fastcall *)(PMDL *, __int64))(*v5)->Next)(v5, 1);
LABEL_4:
    v6 = (void (__fastcall *)(struct VMX_RAID5_PARITY_TRANSFER_PACKET *))*((_QWORD *)a2 + 5);
    *((_DWORD *)a2 + 24) = -1073741670;
    *((_QWORD *)a2 + 13) = 0;
    v6(a2);
    return;
  }
  IoBuildPartialMdl(
    *((PMDL *)a2 + 3),
    v5[3],
    (PVOID)(*(_QWORD *)(*((_QWORD *)a2 + 3) + 32LL) + *(unsigned int *)(*((_QWORD *)a2 + 3) + 44LL)),
    *((_DWORD *)this + 2));
  *((_DWORD *)v5 + 2) = *((_DWORD *)this + 2);
  v5[2] = (PMDL)*((_QWORD *)a2 + 2);
  v5[5] = (PMDL)VmxpRaid5RecoverWriteParityPhase1;
  v7 = (struct _MDL *)*((_QWORD *)a2 + 6);
  v5[6] = v7;
  v5[7] = (PMDL)*((_QWORD *)a2 + 7);
  *((_DWORD *)v5 + 16) = *((_DWORD *)a2 + 16);
  v5[9] = (PMDL)*((_QWORD *)a2 + 9);
  *((_BYTE *)v5 + 81) = *((_BYTE *)a2 + 81);
  *((_BYTE *)v5 + 82) = 0;
  *((_BYTE *)v5 + 137) = 0;
  v5[25] = (PMDL)a2;
  *((_DWORD *)v5 + 3) = 33685517;
  (*(void (__fastcall **)(struct _MDL *, PMDL *))&v7->Next->Size)(v7, v5);
}

```

## disassembly

```asm
0x140010e0c  mov     [rsp+arg_0], rbx
0x140010e11  mov     [rsp+arg_8], rsi
0x140010e16  push    rdi
0x140010e17  sub     rsp, 20h
0x140010e1b  mov     eax, [rdx+8]
0x140010e1e  mov     rsi, rcx
0x140010e21  mov     ecx, 0D0h; unsigned __int64
0x140010e26  mov     [rdx+68h], rax
0x140010e2a  mov     rdi, rdx
0x140010e2d  mov     dword ptr [rdx+60h], 0
0x140010e34  call    ??2VMX_TRANSFER_PACKET@@SAPEAX_K@Z; VMX_TRANSFER_PACKET::operator new(unsigned __int64)
0x140010e39  mov     rbx, rax
0x140010e3c  test    rax, rax
0x140010e3f  jz      short loc_140010E90
0x140010e41  mov     qword ptr [rax+20h], 0
0x140010e49  mov     edx, 0FFFh; void *
0x140010e4e  mov     qword ptr [rax+18h], 0
0x140010e56  mov     rcx, rbx; this
0x140010e59  mov     byte ptr [rax+53h], 0
0x140010e5d  mov     word ptr [rax+84h], 0
0x140010e66  lea     rax, ??_7VMX_RAID5_PARITY_TRANSFER_PACKET@@6B@; const VMX_RAID5_PARITY_TRANSFER_PACKET::`vftable'
0x140010e6d  mov     [rbx], rax
0x140010e70  mov     r8d, [rsi+8]; unsigned int
0x140010e74  call    ?AllocateMdl@VMX_TRANSFER_PACKET@@QEAAJPEAXK@Z; VMX_TRANSFER_PACKET::AllocateMdl(void *,ulong)
0x140010e79  test    eax, eax
0x140010e7b  jns     short loc_140010EBC
0x140010e7d  mov     rax, [rbx]
0x140010e80  mov     edx, 1
0x140010e85  mov     rcx, rbx
0x140010e88  mov     rax, [rax]
0x140010e8b  call    _guard_dispatch_icall
0x140010e90  mov     rax, [rdi+28h]
0x140010e94  mov     rcx, rdi
0x140010e97  mov     dword ptr [rdi+60h], 0C000009Ah
0x140010e9e  mov     qword ptr [rdi+68h], 0
0x140010ea6  call    _guard_dispatch_icall
0x140010eab  mov     rbx, [rsp+28h+arg_0]
0x140010eb0  mov     rsi, [rsp+28h+arg_8]
0x140010eb5  add     rsp, 20h
0x140010eb9  pop     rdi
0x140010eba  retn
0x140010ebc  mov     rcx, [rdi+18h]; SourceMdl
0x140010ec0  mov     r9d, [rsi+8]; Length
0x140010ec4  mov     rdx, [rbx+18h]; TargetMdl
0x140010ec8  mov     r8d, [rcx+2Ch]
0x140010ecc  add     r8, [rcx+20h]; VirtualAddress
0x140010ed0  call    cs:__imp_IoBuildPartialMdl
0x140010ed7  nop     dword ptr [rax+rax+00h]
0x140010edc  mov     eax, [rsi+8]
0x140010edf  mov     rdx, rbx
0x140010ee2  mov     [rbx+8], eax
0x140010ee5  mov     rax, [rdi+10h]
0x140010ee9  mov     [rbx+10h], rax
0x140010eed  lea     rax, ?VmxpRaid5RecoverWriteParityPhase1@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5RecoverWriteParityPhase1(VMX_TRANSFER_PACKET *)
0x140010ef4  mov     [rbx+28h], rax
0x140010ef8  mov     rcx, [rdi+30h]
0x140010efc  mov     [rbx+30h], rcx
0x140010f00  mov     rax, [rdi+38h]
0x140010f04  mov     [rbx+38h], rax
0x140010f08  mov     eax, [rdi+40h]
0x140010f0b  mov     [rbx+40h], eax
0x140010f0e  mov     rax, [rdi+48h]
0x140010f12  mov     [rbx+48h], rax
0x140010f16  mov     al, [rdi+51h]
0x140010f19  mov     [rbx+51h], al
0x140010f1c  mov     byte ptr [rbx+52h], 0
0x140010f20  mov     byte ptr [rbx+89h], 0
0x140010f27  mov     [rbx+0C8h], rdi
0x140010f2e  mov     dword ptr [rbx+0Ch], 202000Dh
0x140010f35  mov     rax, [rcx]
0x140010f38  mov     rax, [rax+8]
0x140010f3c  call    _guard_dispatch_icall
0x140010f41  jmp     loc_140010EAB
```
