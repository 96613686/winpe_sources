# VMX_IO_SPAN::LaunchParallel(VMX_TRANSFER_PACKET *)

- ea: `0x140004ba0`
- end: `0x140004f2d`
- name: `?LaunchParallel@VMX_IO_SPAN@@QEAAEPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `909`
- prototype: `unsigned __int8 __fastcall(VMX_IO_SPAN *__hidden this, struct VMX_TRANSFER_PACKET *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004ac0`
- `0x1400189c0`

## callees

- `0x140004ba0`
- `0x140005600`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140004e05`
- `ntoskrnl!ExAllocatePool2` at `0x140004e05`
- `ntoskrnl!IoBuildPartialMdl` at `0x140004ef4`
- `ntoskrnl!IoBuildPartialMdl` at `0x140004ef4`
- `ntoskrnl!KeInitializeSpinLock` at `0x140004bd2`
- `ntoskrnl!KeInitializeSpinLock` at `0x140004bd2`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140004eb2`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140004eb2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140004c68`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140004c68`

## pseudocode

```c
unsigned __int8 __fastcall VMX_IO_SPAN::LaunchParallel(VMX_IO_SPAN *this, struct VMX_TRANSFER_PACKET *a2)
{
  unsigned int v2; // esi
  bool v4; // r12
  unsigned __int64 v5; // rdi
  __int64 v7; // r14
  unsigned __int64 v8; // rbp
  __int64 v9; // rax
  unsigned __int64 v10; // rcx
  ULONG v11; // edi
  bool v12; // cc
  ULONG v13; // r13d
  struct _LIST_ENTRY *Flink; // rcx
  _BYTE *v15; // rax
  _BYTE *v16; // rdi
  __int64 v17; // rax
  _QWORD *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rcx
  struct _LIST_ENTRY *Pool2; // rax
  __int64 v24; // rax
  __int64 v25; // rcx
  _OWORD v26[5]; // [rsp+40h] [rbp-58h] BYREF
  char *VirtualAddress; // [rsp+A0h] [rbp+8h]

  v2 = 0;
  VirtualAddress = 0;
  v4 = 0;
  v5 = 0;
  v26[0] = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)a2 + 11);
  v7 = *((unsigned int *)a2 + 2);
  v8 = *((_QWORD *)a2 + 2);
  *((_QWORD *)a2 + 13) = v7;
  *((_DWORD *)a2 + 24) = 0;
  *((_DWORD *)a2 + 32) = 0;
  while ( v2 < *((_DWORD *)this + 14) )
  {
    v5 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 8LL * v2) + 16LL);
    if ( v8 < v5 )
    {
      v4 = v7 + v8 > v5;
      break;
    }
    v8 -= v5;
    ++v2;
  }
  v9 = *((_QWORD *)a2 + 3);
  if ( v9 && v4 )
    VirtualAddress = (char *)(*(_QWORD *)(v9 + 32) + *(unsigned int *)(v9 + 44));
  *((_QWORD *)&v26[0] + 1) = v26;
  *(_QWORD *)&v26[0] = v26;
  while ( 1 )
  {
    v10 = v5 - v8;
    v11 = v5 - v8;
    v12 = (unsigned int)v7 <= v10;
    v13 = v7;
    Flink = WPP_MAIN_CB.Queue.ListEntry.Flink;
    if ( !v12 )
      v13 = v11;
    if ( !WPP_MAIN_CB.Queue.ListEntry.Flink )
    {
      Pool2 = (struct _LIST_ENTRY *)ExAllocatePool2(66, 128, 538996054);
      WPP_MAIN_CB.Queue.ListEntry.Flink = Pool2;
      if ( !Pool2 )
        break;
      ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)Pool2, 0, 0, 0x200u, 0x128u, 0x32506D56u, 0x20u);
      Flink = WPP_MAIN_CB.Queue.ListEntry.Flink;
    }
    v15 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)Flink);
    v16 = v15;
    if ( !v15 )
      break;
    v15[80] = 2;
    *((_QWORD *)v15 + 4) = 0;
    *((_QWORD *)v15 + 3) = 0;
    v15[83] = 0;
    *((_WORD *)v15 + 66) = 0;
    *(_QWORD *)v15 = &VMX_RAID5_PARITY_TRANSFER_PACKET::`vftable';
    v17 = *((_QWORD *)a2 + 3);
    if ( !v17 || !v4 )
    {
      *((_QWORD *)v16 + 3) = v17;
      *((_QWORD *)v16 + 4) = *((_QWORD *)a2 + 4);
      goto LABEL_18;
    }
    if ( VMX_TRANSFER_PACKET::AllocateMdl((VMX_TRANSFER_PACKET *)v16, VirtualAddress, v13) < 0 )
    {
      (**(void (__fastcall ***)(_BYTE *, __int64))v16)(v16, 1);
      v16 = 0;
    }
    else
    {
      IoBuildPartialMdl(*((PMDL *)a2 + 3), *((PMDL *)v16 + 3), VirtualAddress, v13);
    }
    if ( !v16 )
      break;
    VirtualAddress += v13;
LABEL_18:
    *((_DWORD *)v16 + 2) = v13;
    *((_QWORD *)v16 + 5) = VmxpSpanTransferParallelCompletionRoutine;
    *((_QWORD *)v16 + 2) = v8;
    *((_QWORD *)v16 + 6) = *(_QWORD *)(*((_QWORD *)this + 6) + 8LL * v2);
    *((_QWORD *)v16 + 7) = *((_QWORD *)a2 + 7);
    *((_DWORD *)v16 + 16) = *((_DWORD *)a2 + 16);
    *((_QWORD *)v16 + 9) = *((_QWORD *)a2 + 9);
    v16[81] = *((_BYTE *)a2 + 81);
    v16[82] = *((_BYTE *)a2 + 82);
    *((_QWORD *)v16 + 22) = a2;
    *((_QWORD *)v16 + 23) = this;
    *((_DWORD *)v16 + 48) = v2;
    v18 = (_QWORD *)*((_QWORD *)&v26[0] + 1);
    if ( **((_OWORD ***)&v26[0] + 1) != v26 )
LABEL_38:
      __fastfail(3u);
    *((_QWORD *)v16 + 15) = *((_QWORD *)&v26[0] + 1);
    *((_QWORD *)v16 + 14) = v26;
    *v18 = v16 + 112;
    ++*((_DWORD *)a2 + 32);
    *((_QWORD *)&v26[0] + 1) = v16 + 112;
    if ( v13 == (_DWORD)v7 )
    {
      while ( 1 )
      {
        v19 = *(_QWORD *)&v26[0];
        if ( *(_OWORD **)&v26[0] == v26 )
          return 1;
        if ( *(_OWORD **)(*(_QWORD *)&v26[0] + 8LL) != v26 )
          goto LABEL_38;
        v20 = **(_QWORD **)&v26[0];
        if ( *(_QWORD *)(**(_QWORD **)&v26[0] + 8LL) != *(_QWORD *)&v26[0] )
          goto LABEL_38;
        *(_QWORD *)&v26[0] = **(_QWORD **)&v26[0];
        *(_QWORD *)(v20 + 8) = v26;
        v21 = *(_QWORD *)(v19 - 112 + 48);
        *(_DWORD *)(v19 - 112 + 12) = *((_DWORD *)a2 + 3);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
      }
    }
    LODWORD(v7) = v7 - *((_DWORD *)v16 + 2);
    v8 = 0;
    v5 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 8LL * ++v2) + 16LL);
  }
  while ( 1 )
  {
    v24 = *(_QWORD *)&v26[0];
    if ( *(_OWORD **)&v26[0] == v26 )
      return 0;
    if ( *(_OWORD **)(*(_QWORD *)&v26[0] + 8LL) != v26 )
      goto LABEL_38;
    v25 = **(_QWORD **)&v26[0];
    if ( *(_QWORD *)(**(_QWORD **)&v26[0] + 8LL) != *(_QWORD *)&v26[0] )
      goto LABEL_38;
    *(_QWORD *)&v26[0] = **(_QWORD **)&v26[0];
    *(_QWORD *)(v25 + 8) = v26;
    if ( v24 != 112 )
      (**(void (__fastcall ***)(__int64, __int64))(v24 - 112))(v24 - 112, 1);
  }
}

```

## disassembly

```asm
0x140004ba0  push    rbx
0x140004ba2  push    rbp
0x140004ba3  push    rsi
0x140004ba4  push    rdi
0x140004ba5  push    r12
0x140004ba7  push    r13
0x140004ba9  push    r14
0x140004bab  push    r15
0x140004bad  sub     rsp, 58h
0x140004bb1  xor     esi, esi
0x140004bb3  mov     r15, rcx
0x140004bb6  xorps   xmm0, xmm0
0x140004bb9  mov     [rsp+98h+VirtualAddress], rsi
0x140004bc1  lea     rcx, [rdx+58h]; SpinLock
0x140004bc5  xor     r12b, r12b
0x140004bc8  mov     edi, esi
0x140004bca  mov     rbx, rdx
0x140004bcd  movups  [rsp+98h+var_58], xmm0
0x140004bd2  call    cs:__imp_KeInitializeSpinLock
0x140004bd9  nop     dword ptr [rax+rax+00h]
0x140004bde  mov     r14d, [rbx+8]
0x140004be2  mov     rbp, [rbx+10h]
0x140004be6  mov     [rbx+68h], r14
0x140004bea  mov     [rbx+60h], esi
0x140004bed  mov     [rbx+80h], esi
0x140004bf3  mov     edx, [r15+38h]
0x140004bf7  cmp     esi, edx
0x140004bf9  jnb     short loc_140004C1D
0x140004bfb  mov     rax, [r15+30h]
0x140004bff  mov     ecx, esi
0x140004c01  mov     rcx, [rax+rcx*8]
0x140004c05  mov     rdi, [rcx+10h]
0x140004c09  cmp     rbp, rdi
0x140004c0c  jnb     loc_140004DEB
0x140004c12  lea     rax, [r14+rbp]
0x140004c16  cmp     rax, rdi
0x140004c19  setnbe  r12b
0x140004c1d  mov     rax, [rbx+18h]
0x140004c21  test    rax, rax
0x140004c24  jz      short loc_140004C2F
0x140004c26  test    r12b, r12b
0x140004c29  jnz     loc_140004E78
0x140004c2f  lea     rax, [rsp+98h+var_58]
0x140004c34  mov     qword ptr [rsp+98h+var_58+8], rax
0x140004c39  lea     rax, [rsp+98h+var_58]
0x140004c3e  mov     qword ptr [rsp+98h+var_58], rax
0x140004c43  mov     rcx, rdi
0x140004c46  mov     eax, r14d
0x140004c49  sub     rcx, rbp
0x140004c4c  sub     edi, ebp
0x140004c4e  cmp     rax, rcx
0x140004c51  mov     r13d, r14d
0x140004c54  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue; Lookaside
0x140004c5b  cmova   r13d, edi
0x140004c5f  test    rcx, rcx
0x140004c62  jz      loc_140004DF5
0x140004c68  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140004c6f  nop     dword ptr [rax+rax+00h]
0x140004c74  mov     rdi, rax
0x140004c77  test    rax, rax
0x140004c7a  jz      loc_140004E20
0x140004c80  mov     byte ptr [rax+50h], 2
0x140004c84  xor     r8d, r8d
0x140004c87  mov     [rax+20h], r8
0x140004c8b  mov     [rax+18h], r8
0x140004c8f  mov     [rax+53h], r8b
0x140004c93  mov     [rax+84h], r8w
0x140004c9b  lea     rax, ??_7VMX_RAID5_PARITY_TRANSFER_PACKET@@6B@; const VMX_RAID5_PARITY_TRANSFER_PACKET::`vftable'
0x140004ca2  mov     [rdi], rax
0x140004ca5  mov     rax, [rbx+18h]
0x140004ca9  test    rax, rax
0x140004cac  jz      short loc_140004CB7
0x140004cae  test    r12b, r12b
0x140004cb1  jnz     loc_140004ECA
0x140004cb7  mov     [rdi+18h], rax
0x140004cbb  mov     rax, [rbx+20h]
0x140004cbf  mov     [rdi+20h], rax
0x140004cc3  jmp     short loc_140004CD9
0x140004cc5  test    rdi, rdi
0x140004cc8  jz      loc_140004E20
0x140004cce  mov     eax, r13d
0x140004cd1  add     [rsp+98h+VirtualAddress], rax
0x140004cd9  mov     [rdi+8], r13d
0x140004cdd  lea     rax, ?VmxpSpanTransferParallelCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpSpanTransferParallelCompletionRoutine(VMX_TRANSFER_PACKET *)
0x140004ce4  mov     [rdi+28h], rax
0x140004ce8  mov     [rdi+10h], rbp
0x140004cec  mov     rax, [r15+30h]
0x140004cf0  mov     ecx, esi
0x140004cf2  mov     rcx, [rax+rcx*8]
0x140004cf6  mov     [rdi+30h], rcx
0x140004cfa  mov     rax, [rbx+38h]
0x140004cfe  mov     [rdi+38h], rax
0x140004d02  mov     eax, [rbx+40h]
0x140004d05  mov     [rdi+40h], eax
0x140004d08  mov     rax, [rbx+48h]
0x140004d0c  mov     [rdi+48h], rax
0x140004d10  movzx   eax, byte ptr [rbx+51h]
0x140004d14  mov     [rdi+51h], al
0x140004d17  movzx   eax, byte ptr [rbx+52h]
0x140004d1b  mov     [rdi+52h], al
0x140004d1e  lea     rax, [rsp+98h+var_58]
0x140004d23  mov     [rdi+0B0h], rbx
0x140004d2a  mov     [rdi+0B8h], r15
0x140004d31  mov     [rdi+0C0h], esi
0x140004d37  mov     rcx, qword ptr [rsp+98h+var_58+8]
0x140004d3c  cmp     [rcx], rax
0x140004d3f  jnz     loc_140004F26
0x140004d45  lea     rax, [rdi+70h]
0x140004d49  mov     [rax+8], rcx
0x140004d4d  lea     rdx, [rsp+98h+var_58]
0x140004d52  mov     [rax], rdx
0x140004d55  mov     [rcx], rax
0x140004d58  inc     dword ptr [rbx+80h]
0x140004d5e  mov     qword ptr [rsp+98h+var_58+8], rax
0x140004d63  cmp     r13d, r14d
0x140004d66  jnz     short loc_140004DD1
0x140004d68  mov     rax, qword ptr [rsp+98h+var_58]
0x140004d6d  lea     rcx, [rsp+98h+var_58]
0x140004d72  cmp     rax, rcx
0x140004d75  jz      short loc_140004DBD
0x140004d77  lea     rcx, [rsp+98h+var_58]
0x140004d7c  cmp     [rax+8], rcx
0x140004d80  jnz     loc_140004F26
0x140004d86  mov     rcx, [rax]
0x140004d89  cmp     [rcx+8], rax
0x140004d8d  jnz     loc_140004F26
0x140004d93  mov     qword ptr [rsp+98h+var_58], rcx
0x140004d98  lea     rdx, [rsp+98h+var_58]
0x140004d9d  mov     [rcx+8], rdx
0x140004da1  lea     rdx, [rax-70h]
0x140004da5  mov     eax, [rbx+0Ch]
0x140004da8  mov     rcx, [rdx+30h]
0x140004dac  mov     [rdx+0Ch], eax
0x140004daf  mov     rax, [rcx]
0x140004db2  mov     rax, [rax+8]
0x140004db6  call    _guard_dispatch_icall
0x140004dbb  jmp     short loc_140004D68
0x140004dbd  mov     al, 1
0x140004dbf  add     rsp, 58h
0x140004dc3  pop     r15
0x140004dc5  pop     r14
0x140004dc7  pop     r13
0x140004dc9  pop     r12
0x140004dcb  pop     rdi
0x140004dcc  pop     rsi
0x140004dcd  pop     rbp
0x140004dce  pop     rbx
0x140004dcf  retn
0x140004dd1  sub     r14d, [rdi+8]
0x140004dd5  mov     rbp, r8
0x140004dd8  mov     rax, [r15+30h]
0x140004ddc  inc     esi
0x140004dde  mov     rcx, [rax+rsi*8]
0x140004de2  mov     rdi, [rcx+10h]
0x140004de6  jmp     loc_140004C43
0x140004deb  sub     rbp, rdi
0x140004dee  inc     esi
0x140004df0  jmp     loc_140004BF7
0x140004df5  mov     edx, 80h
0x140004dfa  mov     ecx, 42h ; 'B'
0x140004dff  mov     r8d, 20206D56h
0x140004e05  call    cs:__imp_ExAllocatePool2
0x140004e0c  nop     dword ptr [rax+rax+00h]
0x140004e11  mov     qword ptr cs:WPP_MAIN_CB.Queue, rax
0x140004e18  test    rax, rax
0x140004e1b  jnz     short loc_140004E8C
0x140004e1d  nop     dword ptr [rax]
0x140004e20  mov     rax, qword ptr [rsp+98h+var_58]
0x140004e25  lea     rcx, [rsp+98h+var_58]
0x140004e2a  cmp     rax, rcx
0x140004e2d  jnz     short loc_140004E33
0x140004e2f  xor     al, al
0x140004e31  jmp     short loc_140004DBF
0x140004e33  lea     rcx, [rsp+98h+var_58]
0x140004e38  cmp     [rax+8], rcx
0x140004e3c  jnz     loc_140004F26
0x140004e42  mov     rcx, [rax]
0x140004e45  cmp     [rcx+8], rax
0x140004e49  jnz     loc_140004F26
0x140004e4f  mov     qword ptr [rsp+98h+var_58], rcx
0x140004e54  lea     rdx, [rsp+98h+var_58]
0x140004e59  mov     [rcx+8], rdx
0x140004e5d  lea     rcx, [rax-70h]
0x140004e61  test    rcx, rcx
0x140004e64  jz      short loc_140004E20
0x140004e66  mov     rax, [rcx]
0x140004e69  mov     edx, 1
0x140004e6e  mov     rax, [rax]
0x140004e71  call    _guard_dispatch_icall
0x140004e76  jmp     short loc_140004E20
0x140004e78  mov     ecx, [rax+2Ch]
0x140004e7b  add     rcx, [rax+20h]
0x140004e7f  mov     [rsp+98h+VirtualAddress], rcx
0x140004e87  jmp     loc_140004C2F
0x140004e8c  mov     [rsp+98h+Depth], 20h ; ' '; Depth
0x140004e93  mov     r9d, 200h; Flags
0x140004e99  mov     [rsp+98h+Tag], 32506D56h; Tag
0x140004ea1  xor     r8d, r8d; Free
0x140004ea4  xor     edx, edx; Allocate
0x140004ea6  mov     [rsp+98h+Size], 128h; Size
0x140004eaf  mov     rcx, rax; Lookaside
0x140004eb2  call    cs:__imp_ExInitializeNPagedLookasideList
0x140004eb9  nop     dword ptr [rax+rax+00h]
0x140004ebe  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x140004ec5  jmp     loc_140004C68
0x140004eca  mov     rdx, [rsp+98h+VirtualAddress]; void *
0x140004ed2  mov     r8d, r13d; unsigned int
0x140004ed5  mov     rcx, rdi; this
0x140004ed8  call    ?AllocateMdl@VMX_TRANSFER_PACKET@@QEAAJPEAXK@Z; VMX_TRANSFER_PACKET::AllocateMdl(void *,ulong)
0x140004edd  test    eax, eax
0x140004edf  js      short loc_140004F08
0x140004ee1  mov     r8, [rsp+98h+VirtualAddress]; VirtualAddress
0x140004ee9  mov     r9d, r13d; Length
0x140004eec  mov     rdx, [rdi+18h]; TargetMdl
0x140004ef0  mov     rcx, [rbx+18h]; SourceMdl
0x140004ef4  call    cs:__imp_IoBuildPartialMdl
0x140004efb  nop     dword ptr [rax+rax+00h]
0x140004f00  xor     r8d, r8d
0x140004f03  jmp     loc_140004CC5
0x140004f08  mov     rax, [rdi]
0x140004f0b  mov     edx, 1
0x140004f10  mov     rcx, rdi
0x140004f13  mov     rax, [rax]
0x140004f16  call    _guard_dispatch_icall
0x140004f1b  xor     r8d, r8d
0x140004f1e  mov     edi, r8d
0x140004f21  jmp     loc_140004CC5
0x140004f26  mov     ecx, 3
0x140004f2b  int     29h; Win8: RtlFailFast(ecx)
```
