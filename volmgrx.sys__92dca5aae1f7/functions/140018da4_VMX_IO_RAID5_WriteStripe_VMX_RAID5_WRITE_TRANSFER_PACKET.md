# VMX_IO_RAID5::WriteStripe(VMX_RAID5_WRITE_TRANSFER_PACKET *)

- ea: `0x140018da4`
- end: `0x140018f5e`
- name: `?WriteStripe@VMX_IO_RAID5@@QEAAXPEAVVMX_RAID5_WRITE_TRANSFER_PACKET@@@Z`
- size: `442`
- prototype: `void __fastcall(VMX_IO_RAID5 *this, struct VMX_RAID5_WRITE_TRANSFER_PACKET *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ea38`
- `0x14000f068`
- `0x1400174d0`

## callees

- `0x140005aa0`
- `0x140018da4`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018df5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018df5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018e26`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018e26`

## pseudocode

```c
void __fastcall VMX_IO_RAID5::WriteStripe(VMX_IO_RAID5 *this, struct VMX_RAID5_WRITE_TRANSFER_PACKET *a2)
{
  unsigned __int64 v3; // r8
  unsigned __int64 v5; // rdx
  unsigned int v6; // r14d
  KIRQL v7; // al
  __int64 v8; // r9
  int v9; // r15d
  int v10; // edi
  __int64 v11; // rcx
  int v12; // edx
  __int64 v13; // rax
  __int64 v14; // r9
  int v15; // r10d
  char v16; // r8
  __int64 v17; // rax
  __int64 v18; // rcx
  unsigned __int8 v19; // r8

  v3 = *((unsigned int *)this + 14);
  v5 = (*((_QWORD *)a2 + 2) >> *((_DWORD *)this + 31)) % v3;
  v6 = v5;
  if ( !*((_BYTE *)this + 260) )
    v6 = v3 - v5 - 1;
  *((_QWORD *)a2 + 6) = *(_QWORD *)(*((_QWORD *)this + 6) + 8LL * *((unsigned int *)a2 + 60));
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 3);
  v8 = *((_QWORD *)this + 14);
  v9 = *(_DWORD *)(v8 + 24LL * *((unsigned int *)a2 + 60) + 16);
  v10 = *(_DWORD *)(v8 + 24LL * v6 + 16);
  KeReleaseSpinLock((PKSPIN_LOCK)this + 3, v7);
  v11 = *((_QWORD *)a2 + 2);
  v12 = *((_DWORD *)a2 + 2);
  *((_QWORD *)a2 + 40) = *((_QWORD *)a2 + 34);
  *((_QWORD *)a2 + 43) = *((_QWORD *)a2 + 6);
  v13 = *((_QWORD *)a2 + 9);
  *((_DWORD *)a2 + 76) = v12;
  *((_QWORD *)a2 + 39) = v11;
  v14 = *((_QWORD *)a2 + 7);
  *((_QWORD *)a2 + 44) = v14;
  v15 = *((_DWORD *)a2 + 16);
  *((_QWORD *)a2 + 46) = v13;
  LODWORD(v13) = *((_DWORD *)a2 + 60);
  *((_DWORD *)a2 + 90) = v15;
  v16 = *((_BYTE *)a2 + 81);
  *((_DWORD *)a2 + 134) = v13;
  v17 = *((_QWORD *)a2 + 32);
  *((_BYTE *)a2 + 560) = 0;
  *((_QWORD *)a2 + 69) = v17;
  *((_DWORD *)a2 + 144) = v12;
  *((_QWORD *)a2 + 73) = v11;
  *((_BYTE *)a2 + 377) = v16;
  *((_BYTE *)a2 + 378) = 1;
  *((_QWORD *)a2 + 65) = a2;
  *((_QWORD *)a2 + 66) = this;
  if ( v10 == 4 )
    v18 = 0;
  else
    v18 = *(_QWORD *)(*((_QWORD *)this + 6) + 8LL * v6);
  *((_QWORD *)a2 + 77) = v18;
  *((_QWORD *)a2 + 78) = v14;
  *((_DWORD *)a2 + 158) = v15;
  *((_QWORD *)a2 + 80) = 0;
  *((_BYTE *)a2 + 649) = v16;
  *((_BYTE *)a2 + 650) = 0;
  *((_QWORD *)a2 + 5) = VmxpRaid5WriteStripePhase1;
  *((_DWORD *)a2 + 72) = v9;
  *((_DWORD *)a2 + 192) = v6;
  if ( v9 )
  {
    *((_BYTE *)a2 + 560) = 1;
    v19 = 1;
  }
  else
  {
    v19 = (v16 & 8) != 0;
  }
  VMX_OVERLAPPED_IO_MANAGER::AcquireIoRegion((VMX_IO_RAID5 *)((char *)this + 136), a2, v19);
}

```

## disassembly

```asm
0x140018da4  push    rbx
0x140018da6  push    rbp
0x140018da7  push    rsi
0x140018da8  push    rdi
0x140018da9  push    r12
0x140018dab  push    r14
0x140018dad  push    r15
0x140018daf  sub     rsp, 20h
0x140018db3  mov     rax, [rdx+10h]
0x140018db7  mov     rbp, rcx
0x140018dba  mov     r8d, [rcx+38h]
0x140018dbe  mov     rsi, rdx
0x140018dc1  mov     ecx, [rcx+7Ch]
0x140018dc4  xor     edx, edx
0x140018dc6  shr     rax, cl
0x140018dc9  div     r8
0x140018dcc  cmp     byte ptr [rbp+104h], 0
0x140018dd3  mov     r14, rdx
0x140018dd6  jnz     short loc_140018DDF
0x140018dd8  sub     r8d, edx
0x140018ddb  lea     r14d, [r8-1]
0x140018ddf  mov     rax, [rbp+30h]
0x140018de3  mov     ecx, [rsi+0F0h]
0x140018de9  mov     rcx, [rax+rcx*8]
0x140018ded  mov     [rsi+30h], rcx
0x140018df1  lea     rcx, [rbp+18h]; SpinLock
0x140018df5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018dfc  nop     dword ptr [rax+rax+00h]
0x140018e01  mov     edx, [rsi+0F0h]
0x140018e07  lea     rcx, [rbp+18h]; SpinLock
0x140018e0b  mov     r9, [rbp+70h]
0x140018e0f  mov     r12d, r14d
0x140018e12  lea     r8, [rdx+rdx*2]
0x140018e16  mov     r15d, [r9+r8*8+10h]
0x140018e1b  lea     rdx, [r12+r12*2]
0x140018e1f  mov     edi, [r9+rdx*8+10h]
0x140018e24  mov     dl, al; NewIrql
0x140018e26  call    cs:__imp_KeReleaseSpinLock
0x140018e2d  nop     dword ptr [rax+rax+00h]
0x140018e32  mov     rax, [rsi+110h]
0x140018e39  mov     rcx, [rsi+10h]
0x140018e3d  mov     edx, [rsi+8]
0x140018e40  mov     [rsi+140h], rax
0x140018e47  mov     rax, [rsi+30h]
0x140018e4b  mov     [rsi+158h], rax
0x140018e52  mov     rax, [rsi+48h]
0x140018e56  mov     [rsi+130h], edx
0x140018e5c  mov     [rsi+138h], rcx
0x140018e63  mov     r9, [rsi+38h]
0x140018e67  mov     [rsi+160h], r9
0x140018e6e  mov     r10d, [rsi+40h]
0x140018e72  mov     [rsi+170h], rax
0x140018e79  mov     eax, [rsi+0F0h]
0x140018e7f  mov     [rsi+168h], r10d
0x140018e86  mov     r8b, [rsi+51h]
0x140018e8a  mov     [rsi+218h], eax
0x140018e90  mov     rax, [rsi+100h]
0x140018e97  mov     byte ptr [rsi+230h], 0
0x140018e9e  mov     [rsi+228h], rax
0x140018ea5  mov     [rsi+240h], edx
0x140018eab  mov     [rsi+248h], rcx
0x140018eb2  mov     [rsi+179h], r8b
0x140018eb9  mov     byte ptr [rsi+17Ah], 1
0x140018ec0  mov     [rsi+208h], rsi
0x140018ec7  mov     [rsi+210h], rbp
0x140018ece  cmp     edi, 4
0x140018ed1  jz      short loc_140018EDD
0x140018ed3  mov     rax, [rbp+30h]
0x140018ed7  mov     rcx, [rax+r12*8]
0x140018edb  jmp     short loc_140018EDF
0x140018edd  xor     ecx, ecx
0x140018edf  mov     [rsi+268h], rcx
0x140018ee6  lea     rax, ?VmxpRaid5WriteStripePhase1@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5WriteStripePhase1(VMX_TRANSFER_PACKET *)
0x140018eed  mov     [rsi+270h], r9
0x140018ef4  lea     rcx, [rbp+88h]; this
0x140018efb  mov     [rsi+278h], r10d
0x140018f02  mov     qword ptr [rsi+280h], 0
0x140018f0d  mov     [rsi+289h], r8b
0x140018f14  mov     byte ptr [rsi+28Ah], 0
0x140018f1b  mov     [rsi+28h], rax
0x140018f1f  mov     [rsi+120h], r15d
0x140018f26  mov     [rsi+300h], r14d
0x140018f2d  test    r15d, r15d
0x140018f30  jnz     short loc_140018F3C
0x140018f32  shr     r8b, 3
0x140018f36  and     r8b, 1
0x140018f3a  jmp     short loc_140018F46
0x140018f3c  mov     byte ptr [rsi+230h], 1
0x140018f43  mov     r8b, 1; unsigned __int8
0x140018f46  mov     rdx, rsi; struct VMX_OVERLAP_TRANSFER_PACKET *
0x140018f49  call    ?AcquireIoRegion@VMX_OVERLAPPED_IO_MANAGER@@QEAAXPEAVVMX_OVERLAP_TRANSFER_PACKET@@E@Z; VMX_OVERLAPPED_IO_MANAGER::AcquireIoRegion(VMX_OVERLAP_TRANSFER_PACKET *,uchar)
0x140018f4e  add     rsp, 20h
0x140018f52  pop     r15
0x140018f54  pop     r14
0x140018f56  pop     r12
0x140018f58  pop     rdi
0x140018f59  pop     rsi
0x140018f5a  pop     rbp
0x140018f5b  pop     rbx
0x140018f5c  retn
```
