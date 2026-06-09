# VMX_IO_STRIPE::LaunchParallel(VMX_TRANSFER_PACKET *)

- ea: `0x140004670`
- end: `0x140004aba`
- name: `?LaunchParallel@VMX_IO_STRIPE@@QEAAEPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `1098`
- prototype: `unsigned __int8 __fastcall(VMX_IO_STRIPE *__hidden this, struct VMX_TRANSFER_PACKET *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004590`
- `0x140018bc0`

## callees

- `0x140004670`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400049e5`
- `ntoskrnl!ExAllocatePool2` at `0x1400049e5`
- `ntoskrnl!IoBuildPartialMdl` at `0x14000483e`
- `ntoskrnl!IoBuildPartialMdl` at `0x14000483e`
- `ntoskrnl!IoAllocateMdl` at `0x140004811`
- `ntoskrnl!IoAllocateMdl` at `0x140004811`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400046da`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400046da`
- `ntoskrnl!IoFreeMdl` at `0x1400047ea`
- `ntoskrnl!IoFreeMdl` at `0x1400047ea`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140004a81`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140004a81`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000478b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000478b`

## pseudocode

```c
unsigned __int8 __fastcall VMX_IO_STRIPE::LaunchParallel(VMX_IO_STRIPE *this, struct VMX_TRANSFER_PACKET *a2)
{
  unsigned __int64 v2; // r12
  int *v3; // rbp
  char *v4; // r14
  unsigned int v5; // r15d
  unsigned int v6; // r8d
  unsigned int v7; // r13d
  VMX_IO_STRIPE *v9; // rbx
  unsigned int v10; // esi
  __int64 v11; // r9
  __int64 v12; // rax
  int v13; // ecx
  unsigned int v14; // ebp
  unsigned __int64 v15; // r12
  __int64 v16; // rax
  ULONG v17; // r15d
  struct _LIST_ENTRY *Flink; // rcx
  _BYTE *v19; // rax
  _BYTE *v20; // rbx
  __int64 v21; // rax
  struct _MDL *Mdl; // rax
  _QWORD *v23; // rcx
  _BYTE *v24; // rax
  __int64 v25; // rax
  __int64 v26; // rcx
  struct _LIST_ENTRY *Pool2; // rax
  __int64 v29; // rax
  __int64 v30; // rcx
  int v31; // [rsp+40h] [rbp-68h]
  unsigned __int64 v32; // [rsp+48h] [rbp-60h]
  _OWORD v33[5]; // [rsp+50h] [rbp-58h] BYREF
  unsigned int v35; // [rsp+B8h] [rbp+10h]
  unsigned __int64 v36; // [rsp+C0h] [rbp+18h]
  _DWORD *v37; // [rsp+C8h] [rbp+20h]

  v2 = *((_QWORD *)a2 + 2);
  v3 = (int *)((char *)this + 68);
  v4 = 0;
  v5 = v2 & *((_DWORD *)this + 18);
  v6 = *((_DWORD *)a2 + 2);
  v7 = *((_DWORD *)this + 16) - v5;
  v35 = v5;
  v37 = (_DWORD *)((char *)this + 68);
  v9 = this;
  v33[0] = 0;
  if ( v6 > v7 )
  {
    v10 = ((v6 - v7) >> *v3) + (v6 - v7 != (v6 - v7) >> *v3 << *v3) + 1;
  }
  else
  {
    v10 = 1;
    v37 = (_DWORD *)((char *)this + 68);
  }
  KeInitializeSpinLock((PKSPIN_LOCK)a2 + 11);
  v11 = *((unsigned int *)a2 + 2);
  v12 = *((_QWORD *)a2 + 3);
  *((_DWORD *)a2 + 24) = 0;
  v31 = v11;
  *((_QWORD *)a2 + 13) = v11;
  *((_DWORD *)a2 + 32) = v10;
  if ( v12 && v10 > 1 )
    v4 = (char *)(*(_QWORD *)(v12 + 32) + *(unsigned int *)(v12 + 44));
  v13 = *v3;
  *((_QWORD *)&v33[0] + 1) = v33;
  v14 = 0;
  v15 = v2 >> v13;
  *(_QWORD *)&v33[0] = v33;
  while ( v14 < v10 )
  {
    v32 = *((unsigned int *)v9 + 14);
    if ( v14 )
    {
      v36 = (v15 / v32) << *v37;
      if ( v14 == v10 - 1 )
        v17 = v11;
      else
        v17 = *((_DWORD *)v9 + 16);
    }
    else
    {
      v16 = v5;
      v17 = v11;
      v36 = ((v15 / v32) << *v37) + v16;
      if ( v7 <= (unsigned int)v11 )
        v17 = v7;
    }
    Flink = WPP_MAIN_CB.Queue.ListEntry.Flink;
    if ( !WPP_MAIN_CB.Queue.ListEntry.Flink )
    {
      Pool2 = (struct _LIST_ENTRY *)ExAllocatePool2(66, 128, 538996054);
      WPP_MAIN_CB.Queue.ListEntry.Flink = Pool2;
      if ( !Pool2 )
        goto LABEL_34;
      ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)Pool2, 0, 0, 0x200u, 0x128u, 0x32506D56u, 0x20u);
      Flink = WPP_MAIN_CB.Queue.ListEntry.Flink;
    }
    v19 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)Flink);
    v20 = v19;
    if ( !v19 )
      goto LABEL_34;
    v19[80] = 2;
    *((_QWORD *)v19 + 4) = 0;
    *((_QWORD *)v19 + 3) = 0;
    v19[83] = 0;
    *((_WORD *)v19 + 66) = 0;
    *(_QWORD *)v19 = &VMX_RAID5_PARITY_TRANSFER_PACKET::`vftable';
    v21 = *((_QWORD *)a2 + 3);
    if ( v21 && v10 > 1 )
    {
      if ( v20[132] )
      {
        IoFreeMdl(0);
        v20[132] = 0;
      }
      Mdl = IoAllocateMdl(v4, v17, 0, 0, 0);
      *((_QWORD *)v20 + 3) = Mdl;
      if ( Mdl )
      {
        v20[132] = 1;
        IoBuildPartialMdl(*((PMDL *)a2 + 3), Mdl, v4, v17);
      }
      else
      {
        (**(void (__fastcall ***)(_BYTE *, __int64))v20)(v20, 1);
        v20 = 0;
      }
      if ( !v20 )
      {
LABEL_34:
        while ( 1 )
        {
          v29 = *(_QWORD *)&v33[0];
          if ( *(_OWORD **)&v33[0] == v33 )
            return 0;
          if ( *(_OWORD **)(*(_QWORD *)&v33[0] + 8LL) != v33 )
            goto LABEL_42;
          v30 = **(_QWORD **)&v33[0];
          if ( *(_QWORD *)(**(_QWORD **)&v33[0] + 8LL) != *(_QWORD *)&v33[0] )
            goto LABEL_42;
          *(_QWORD *)&v33[0] = **(_QWORD **)&v33[0];
          *(_QWORD *)(v30 + 8) = v33;
          if ( v29 != 112 )
            (**(void (__fastcall ***)(__int64, __int64))(v29 - 112))(v29 - 112, 1);
        }
      }
      v4 += v17;
    }
    else
    {
      *((_QWORD *)v20 + 3) = v21;
      *((_QWORD *)v20 + 4) = *((_QWORD *)a2 + 4);
    }
    *((_DWORD *)v20 + 2) = v17;
    *((_QWORD *)v20 + 2) = v36;
    *((_QWORD *)v20 + 5) = VmxpStripeTransferParallelCompletionRoutine;
    *((_QWORD *)v20 + 6) = *(_QWORD *)(*((_QWORD *)this + 6) + 8LL * (unsigned int)(v15 % v32));
    *((_QWORD *)v20 + 7) = *((_QWORD *)a2 + 7);
    *((_DWORD *)v20 + 16) = *((_DWORD *)a2 + 16);
    *((_QWORD *)v20 + 9) = *((_QWORD *)a2 + 9);
    v20[81] = *((_BYTE *)a2 + 81);
    v20[82] = *((_BYTE *)a2 + 82);
    *((_QWORD *)v20 + 22) = a2;
    *((_QWORD *)v20 + 23) = this;
    *((_DWORD *)v20 + 48) = v15 % v32;
    v23 = (_QWORD *)*((_QWORD *)&v33[0] + 1);
    if ( **((_OWORD ***)&v33[0] + 1) != v33 )
LABEL_42:
      __fastfail(3u);
    v24 = v20 + 112;
    LODWORD(v11) = v31 - v17;
    *((_QWORD *)v20 + 15) = *((_QWORD *)&v33[0] + 1);
    v5 = v35;
    *((_QWORD *)v20 + 14) = v33;
    ++v14;
    *v23 = v20 + 112;
    ++v15;
    v31 = v11;
    v9 = this;
    *((_QWORD *)&v33[0] + 1) = v24;
  }
  while ( 1 )
  {
    v25 = *(_QWORD *)&v33[0];
    if ( *(_OWORD **)&v33[0] == v33 )
      return 1;
    if ( *(_OWORD **)(*(_QWORD *)&v33[0] + 8LL) != v33 )
      goto LABEL_42;
    v26 = **(_QWORD **)&v33[0];
    if ( *(_QWORD *)(**(_QWORD **)&v33[0] + 8LL) != *(_QWORD *)&v33[0] )
      goto LABEL_42;
    *(_QWORD *)&v33[0] = **(_QWORD **)&v33[0];
    *(_QWORD *)(v26 + 8) = v33;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v25 - 112 + 48) + 8LL))(*(_QWORD *)(v25 - 112 + 48));
  }
}

```

## disassembly

```asm
0x140004670  mov     [rsp+arg_0], rcx
0x140004675  push    rbx
0x140004676  push    rbp
0x140004677  push    rsi
0x140004678  push    rdi
0x140004679  push    r12
0x14000467b  push    r13
0x14000467d  push    r14
0x14000467f  push    r15
0x140004681  sub     rsp, 68h
0x140004685  mov     r12, [rdx+10h]
0x140004689  lea     rbp, [rcx+44h]
0x14000468d  mov     r15d, [rcx+48h]
0x140004691  xor     r14d, r14d
0x140004694  mov     r13d, [rcx+40h]
0x140004698  and     r15d, r12d
0x14000469b  mov     r8d, [rdx+8]
0x14000469f  sub     r13d, r15d
0x1400046a2  mov     [rsp+0A8h+arg_8], r15d
0x1400046aa  xorps   xmm0, xmm0
0x1400046ad  mov     [rsp+0A8h+arg_18], rbp
0x1400046b5  mov     rdi, rdx
0x1400046b8  mov     rbx, rcx
0x1400046bb  movups  [rsp+0A8h+var_58], xmm0
0x1400046c0  cmp     r8d, r13d
0x1400046c3  ja      loc_14000499A
0x1400046c9  mov     esi, 1
0x1400046ce  mov     [rsp+0A8h+arg_18], rbp
0x1400046d6  lea     rcx, [rdi+58h]; SpinLock
0x1400046da  call    cs:__imp_KeInitializeSpinLock
0x1400046e1  nop     dword ptr [rax+rax+00h]
0x1400046e6  mov     r9d, [rdi+8]
0x1400046ea  xor     r10d, r10d
0x1400046ed  mov     rax, [rdi+18h]
0x1400046f1  mov     [rdi+60h], r10d
0x1400046f5  mov     [rsp+0A8h+var_68], r9
0x1400046fa  mov     [rdi+68h], r9
0x1400046fe  mov     [rdi+80h], esi
0x140004704  test    rax, rax
0x140004707  jz      short loc_140004716
0x140004709  cmp     esi, 1
0x14000470c  jbe     short loc_140004716
0x14000470e  mov     r14d, [rax+2Ch]
0x140004712  add     r14, [rax+20h]
0x140004716  mov     ecx, [rbp+0]
0x140004719  lea     rax, [rsp+0A8h+var_58]
0x14000471e  mov     qword ptr [rsp+0A8h+var_58+8], rax
0x140004723  mov     ebp, r10d
0x140004726  lea     rax, [rsp+0A8h+var_58]
0x14000472b  shr     r12, cl
0x14000472e  mov     qword ptr [rsp+0A8h+var_58], rax
0x140004733  cmp     ebp, esi
0x140004735  jnb     loc_140004920
0x14000473b  mov     ecx, [rbx+38h]
0x14000473e  xor     edx, edx
0x140004740  mov     rax, r12
0x140004743  mov     [rsp+0A8h+var_60], rcx
0x140004748  div     rcx
0x14000474b  mov     r8, rax
0x14000474e  mov     rax, [rsp+0A8h+arg_18]
0x140004756  mov     ecx, [rax]
0x140004758  shl     r8, cl
0x14000475b  test    ebp, ebp
0x14000475d  jnz     loc_140004983
0x140004763  mov     eax, r15d
0x140004766  mov     r15d, r9d
0x140004769  add     rax, r8
0x14000476c  cmp     r13d, r9d
0x14000476f  mov     [rsp+0A8h+arg_10], rax
0x140004777  cmovbe  r15d, r13d
0x14000477b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue; Lookaside
0x140004782  test    rcx, rcx
0x140004785  jz      loc_1400049D5
0x14000478b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140004792  nop     dword ptr [rax+rax+00h]
0x140004797  mov     rbx, rax
0x14000479a  test    rax, rax
0x14000479d  jz      loc_140004A00
0x1400047a3  mov     byte ptr [rax+50h], 2
0x1400047a7  xor     r10d, r10d
0x1400047aa  mov     [rax+20h], r10
0x1400047ae  mov     [rax+18h], r10
0x1400047b2  mov     [rax+53h], r10b
0x1400047b6  mov     [rax+84h], r10w
0x1400047be  lea     rax, ??_7VMX_RAID5_PARITY_TRANSFER_PACKET@@6B@; const VMX_RAID5_PARITY_TRANSFER_PACKET::`vftable'
0x1400047c5  mov     [rbx], rax
0x1400047c8  mov     rax, [rdi+18h]
0x1400047cc  test    rax, rax
0x1400047cf  jz      loc_1400049BB
0x1400047d5  cmp     esi, 1
0x1400047d8  jbe     loc_1400049BB
0x1400047de  cmp     [rbx+84h], r10b
0x1400047e5  jz      short loc_140004800
0x1400047e7  mov     ecx, r10d; Mdl
0x1400047ea  call    cs:__imp_IoFreeMdl
0x1400047f1  nop     dword ptr [rax+rax+00h]
0x1400047f6  xor     r10d, r10d
0x1400047f9  mov     byte ptr [rbx+84h], 0
0x140004800  xor     r9d, r9d; ChargeQuota
0x140004803  mov     [rsp+0A8h+Irp], r10; Irp
0x140004808  xor     r8d, r8d; SecondaryBuffer
0x14000480b  mov     edx, r15d; Length
0x14000480e  mov     rcx, r14; VirtualAddress
0x140004811  call    cs:__imp_IoAllocateMdl
0x140004818  nop     dword ptr [rax+rax+00h]
0x14000481d  mov     [rbx+18h], rax
0x140004821  test    rax, rax
0x140004824  jz      loc_140004A99
0x14000482a  mov     byte ptr [rbx+84h], 1
0x140004831  mov     r9d, r15d; Length
0x140004834  mov     rcx, [rdi+18h]; SourceMdl
0x140004838  mov     r8, r14; VirtualAddress
0x14000483b  mov     rdx, rax; TargetMdl
0x14000483e  call    cs:__imp_IoBuildPartialMdl
0x140004845  nop     dword ptr [rax+rax+00h]
0x14000484a  test    rbx, rbx
0x14000484d  jz      loc_140004A00
0x140004853  mov     eax, r15d
0x140004856  add     r14, rax
0x140004859  mov     r8, [rsp+0A8h+arg_0]
0x140004861  xor     edx, edx
0x140004863  mov     [rbx+8], r15d
0x140004867  mov     rax, r12
0x14000486a  div     [rsp+0A8h+var_60]
0x14000486f  mov     rax, [rsp+0A8h+arg_10]
0x140004877  mov     [rbx+10h], rax
0x14000487b  lea     rax, ?VmxpStripeTransferParallelCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpStripeTransferParallelCompletionRoutine(VMX_TRANSFER_PACKET *)
0x140004882  mov     [rbx+28h], rax
0x140004886  mov     rax, [r8+30h]
0x14000488a  mov     ecx, edx
0x14000488c  mov     rcx, [rax+rcx*8]
0x140004890  mov     [rbx+30h], rcx
0x140004894  mov     rax, [rdi+38h]
0x140004898  mov     [rbx+38h], rax
0x14000489c  mov     eax, [rdi+40h]
0x14000489f  mov     [rbx+40h], eax
0x1400048a2  mov     rax, [rdi+48h]
0x1400048a6  mov     [rbx+48h], rax
0x1400048aa  movzx   eax, byte ptr [rdi+51h]
0x1400048ae  mov     [rbx+51h], al
0x1400048b1  movzx   eax, byte ptr [rdi+52h]
0x1400048b5  mov     [rbx+52h], al
0x1400048b8  lea     rax, [rsp+0A8h+var_58]
0x1400048bd  mov     [rbx+0B0h], rdi
0x1400048c4  mov     [rbx+0B8h], r8
0x1400048cb  mov     [rbx+0C0h], edx
0x1400048d1  mov     rcx, qword ptr [rsp+0A8h+var_58+8]
0x1400048d6  cmp     [rcx], rax
0x1400048d9  jnz     loc_140004AB3
0x1400048df  mov     r9, [rsp+0A8h+var_68]
0x1400048e4  lea     rax, [rbx+70h]
0x1400048e8  sub     r9d, r15d
0x1400048eb  mov     [rax+8], rcx
0x1400048ef  mov     r15d, [rsp+0A8h+arg_8]
0x1400048f7  lea     rdx, [rsp+0A8h+var_58]
0x1400048fc  mov     [rax], rdx
0x1400048ff  inc     ebp
0x140004901  mov     [rcx], rax
0x140004904  inc     r12
0x140004907  mov     [rsp+0A8h+var_68], r9
0x14000490c  mov     rbx, r8
0x14000490f  mov     qword ptr [rsp+0A8h+var_58+8], rax
0x140004914  jmp     loc_140004733
0x140004920  mov     rax, qword ptr [rsp+0A8h+var_58]
0x140004925  lea     rcx, [rsp+0A8h+var_58]
0x14000492a  cmp     rax, rcx
0x14000492d  jz      short loc_14000496F
0x14000492f  lea     rcx, [rsp+0A8h+var_58]
0x140004934  cmp     [rax+8], rcx
0x140004938  jnz     loc_140004AB3
0x14000493e  mov     rcx, [rax]
0x140004941  cmp     [rcx+8], rax
0x140004945  jnz     loc_140004AB3
0x14000494b  mov     qword ptr [rsp+0A8h+var_58], rcx
0x140004950  lea     rdx, [rsp+0A8h+var_58]
0x140004955  mov     [rcx+8], rdx
0x140004959  lea     rdx, [rax-70h]
0x14000495d  mov     rcx, [rdx+30h]
0x140004961  mov     rax, [rcx]
0x140004964  mov     rax, [rax+8]
0x140004968  call    _guard_dispatch_icall
0x14000496d  jmp     short loc_140004920
0x14000496f  mov     al, 1
0x140004971  add     rsp, 68h
0x140004975  pop     r15
0x140004977  pop     r14
0x140004979  pop     r13
0x14000497b  pop     r12
0x14000497d  pop     rdi
0x14000497e  pop     rsi
0x14000497f  pop     rbp
0x140004980  pop     rbx
0x140004981  retn
0x140004983  lea     eax, [rsi-1]
0x140004986  mov     [rsp+0A8h+arg_10], r8
0x14000498e  cmp     ebp, eax
0x140004990  jnz     short loc_1400049CC
0x140004992  mov     r15d, r9d
0x140004995  jmp     loc_14000477B
0x14000499a  mov     ecx, [rbp+0]
0x14000499d  xor     esi, esi
0x14000499f  sub     r8d, r13d
0x1400049a2  mov     edx, r8d
0x1400049a5  shr     edx, cl
0x1400049a7  mov     eax, edx
0x1400049a9  shl     eax, cl
0x1400049ab  cmp     r8d, eax
0x1400049ae  setnz   sil
0x1400049b2  inc     esi
0x1400049b4  add     esi, edx
0x1400049b6  jmp     loc_1400046D6
0x1400049bb  mov     [rbx+18h], rax
0x1400049bf  mov     rax, [rdi+20h]
0x1400049c3  mov     [rbx+20h], rax
0x1400049c7  jmp     loc_140004859
0x1400049cc  mov     r15d, [rbx+40h]
0x1400049d0  jmp     loc_14000477B
0x1400049d5  mov     edx, 80h
0x1400049da  mov     ecx, 42h ; 'B'
0x1400049df  mov     r8d, 20206D56h
0x1400049e5  call    cs:__imp_ExAllocatePool2
0x1400049ec  nop     dword ptr [rax+rax+00h]
0x1400049f1  mov     qword ptr cs:WPP_MAIN_CB.Queue, rax
0x1400049f8  test    rax, rax
0x1400049fb  jnz     short loc_140004A5B
0x1400049fd  nop     dword ptr [rax]
0x140004a00  mov     rax, qword ptr [rsp+0A8h+var_58]
0x140004a05  lea     rcx, [rsp+0A8h+var_58]
0x140004a0a  cmp     rax, rcx
0x140004a0d  jnz     short loc_140004A16
0x140004a0f  xor     al, al
0x140004a11  jmp     loc_140004971
0x140004a16  lea     rcx, [rsp+0A8h+var_58]
0x140004a1b  cmp     [rax+8], rcx
0x140004a1f  jnz     loc_140004AB3
0x140004a25  mov     rcx, [rax]
0x140004a28  cmp     [rcx+8], rax
0x140004a2c  jnz     loc_140004AB3
0x140004a32  mov     qword ptr [rsp+0A8h+var_58], rcx
0x140004a37  lea     rdx, [rsp+0A8h+var_58]
0x140004a3c  mov     [rcx+8], rdx
0x140004a40  lea     rcx, [rax-70h]
0x140004a44  test    rcx, rcx
0x140004a47  jz      short loc_140004A00
0x140004a49  mov     rax, [rcx]
0x140004a4c  mov     edx, 1
0x140004a51  mov     rax, [rax]
0x140004a54  call    _guard_dispatch_icall
0x140004a59  jmp     short loc_140004A00
0x140004a5b  mov     [rsp+0A8h+Depth], 20h ; ' '; Depth
0x140004a62  mov     r9d, 200h; Flags
0x140004a68  mov     [rsp+0A8h+Tag], 32506D56h; Tag
0x140004a70  xor     r8d, r8d; Free
0x140004a73  xor     edx, edx; Allocate
0x140004a75  mov     [rsp+0A8h+Irp], 128h; Size
0x140004a7e  mov     rcx, rax; Lookaside
0x140004a81  call    cs:__imp_ExInitializeNPagedLookasideList
0x140004a88  nop     dword ptr [rax+rax+00h]
0x140004a8d  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x140004a94  jmp     loc_14000478B
0x140004a99  mov     rax, [rbx]
0x140004a9c  mov     edx, 1
0x140004aa1  mov     rcx, rbx
0x140004aa4  mov     rax, [rax]
0x140004aa7  call    _guard_dispatch_icall
0x140004aac  xor     ebx, ebx
0x140004aae  jmp     loc_14000484A
0x140004ab3  mov     ecx, 3
0x140004ab8  int     29h; Win8: RtlFailFast(ecx)
```
