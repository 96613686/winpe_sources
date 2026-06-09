# VMX_IO_RAID5::CommitFaultTolerantObjects(VMX_IO_OBJECT *)

- ea: `0x14000c160`
- end: `0x14000c640`
- name: `?CommitFaultTolerantObjects@VMX_IO_RAID5@@UEAAXPEAVVMX_IO_OBJECT@@@Z`
- size: `1248`
- prototype: `void __fastcall(VMX_IO_RAID5 *__hidden this, struct VMX_IO_OBJECT *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000c100`
- `0x14000c160`
- `0x14000d0dc`
- `0x14000d180`
- `0x14000e464`
- `0x14000e5b4`
- `0x14000fa68`
- `0x140010a08`
- `0x14001b9a0`
- `0x14001be80`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000c376`
- `ntoskrnl!ExAllocatePool2` at `0x14000c491`
- `ntoskrnl!ExAllocatePool2` at `0x14000c55c`
- `ntoskrnl!ExAllocatePool2` at `0x14000c376`
- `ntoskrnl!ExAllocatePool2` at `0x14000c491`
- `ntoskrnl!ExAllocatePool2` at `0x14000c55c`

## pseudocode

```c
void __fastcall VMX_IO_RAID5::CommitFaultTolerantObjects(VMX_IO_RAID5 *this, struct VMX_IO_OBJECT *a2)
{
  __int64 v4; // r8
  __int64 v5; // rax
  VMX_IO_RAID5 **v6; // r14
  char v7; // r15
  unsigned int v8; // esi
  __int64 v9; // rdi
  __int64 j; // rbp
  int v11; // edx
  int v12; // eax
  VMX_IO_RAID5 *v13; // rcx
  VMX_IO_RAID5 **v14; // r14
  VMX_IO_RAID5 *v15; // rdi
  VMX_IO_RAID5 *v16; // rax
  _QWORD *v17; // rsi
  VMX_IO_RAID5 **v18; // rcx
  __int64 Pool2; // rax
  VMX_RAID5_SYNCHRONIZATION_TASK *v20; // rdi
  VMX_IO_RAID5 **v21; // rdx
  char v22; // al
  char v23; // al
  unsigned int v24; // esi
  __int64 i; // rdi
  VMX_IO_RAID5 *v26; // rcx
  __int64 v27; // rax
  _QWORD *v28; // rdi
  VMX_IO_RAID5 **v29; // rdx
  unsigned int v30; // r10d
  __int64 v31; // rsi
  __int64 v32; // r11
  int v33; // edx
  unsigned int v34; // r9d
  bool v35; // zf
  unsigned int v36; // eax
  int v37; // eax
  __int64 v38; // rax
  _QWORD *v39; // rdi
  unsigned __int64 v40; // r9
  VMX_IO_RAID5 **v41; // r8
  __int64 v42; // rax
  unsigned int v43; // ecx
  unsigned int v44; // edx
  unsigned int v45; // [rsp+78h] [rbp+10h] BYREF
  unsigned int v46; // [rsp+80h] [rbp+18h] BYREF

  v46 = 0;
  v45 = 0;
  VMX_IO_OPERATOR::CommitFaultTolerantObjects(this, a2);
  if ( !a2
    || (LOBYTE(v4) = 1,
        v5 = (*(__int64 (__fastcall **)(struct VMX_IO_OBJECT *, _QWORD, __int64))(*(_QWORD *)a2 + 208LL))(
               a2,
               *((_QWORD *)this + 10),
               v4),
        (v6 = (VMX_IO_RAID5 **)v5) == 0) )
  {
    v24 = 0;
    for ( i = *((_QWORD *)this + 14); v24 < *((_DWORD *)this + 14); i += 24 )
    {
      if ( *(_BYTE *)(i + 20) && *(_DWORD *)(i + 16) == 3 )
      {
        VMX_IO_RAID5::DetachFaultTolerantMember(this, v24, 0);
        VMX_IO_RAID5::PropagateFaultTolerantChanges(v26);
      }
      ++v24;
    }
    *((_BYTE *)this + 262) = 0;
    v23 = 0;
    goto LABEL_51;
  }
  v7 = 0;
  if ( *(_BYTE *)(v5 + 261) )
  {
    *((_BYTE *)this + 261) = 1;
  }
  else if ( *((_BYTE *)this + 261) )
  {
    if ( *(_QWORD *)(v5 + 16) >= *((_QWORD *)this + 2) )
      *((_BYTE *)this + 261) = 0;
    else
      v7 = 1;
  }
  v8 = 0;
  v9 = *((_QWORD *)this + 14);
  for ( j = v5; v8 < *((_DWORD *)this + 14); v9 += 24 )
  {
    if ( !*(_BYTE *)(v9 + 21) && VMX_IO_RAID5::FindFaultTolerantMember((VMX_IO_RAID5 *)v6, *(_QWORD *)v9, 1u, &v45) )
    {
      v11 = *((_DWORD *)v6[14] + 6 * v45 + 4);
      if ( v11 == 4 )
      {
        *(_DWORD *)(v9 + 16) = 4;
      }
      else
      {
        v12 = *(_DWORD *)(v9 + 16);
        if ( v12 != 4 )
        {
          if ( v11 == 2 )
          {
            *(_DWORD *)(v9 + 16) = 2;
          }
          else if ( v11 == 3 )
          {
            *(_DWORD *)(v9 + 16) = 3;
          }
          else if ( v12 == 3 )
          {
            *(_DWORD *)(v9 + 16) = 0;
          }
        }
      }
    }
    *(_BYTE *)(v9 + 21) = 0;
    if ( *(_BYTE *)(v9 + 20) && (unsigned int)(*(_DWORD *)(v9 + 16) - 2) <= 1 )
    {
      VMX_IO_RAID5::DetachFaultTolerantMember(this, v8, 0);
      VMX_IO_RAID5::PropagateFaultTolerantChanges(v13);
    }
    ++v8;
  }
  v14 = v6 + 4;
  while ( 1 )
  {
    v15 = *v14;
    if ( *v14 == (VMX_IO_RAID5 *)v14 )
      break;
    if ( *((VMX_IO_RAID5 ***)v15 + 1) != v14 )
      goto LABEL_68;
    v16 = *(VMX_IO_RAID5 **)v15;
    if ( *(VMX_IO_RAID5 **)(*(_QWORD *)v15 + 8LL) != v15 )
      goto LABEL_68;
    *v14 = v16;
    v17 = (_QWORD *)((char *)v15 - 8);
    *((_QWORD *)v16 + 1) = v14;
    if ( *((_DWORD *)v15 + 4) == 3 )
    {
      if ( VMX_IO_RAID5::FindFaultTolerantMember(
             this,
             *(_QWORD *)(*(_QWORD *)(j + 112) + 24LL * *((unsigned int *)v17 + 24) + 8),
             0,
             &v46)
        && *(_DWORD *)(*((_QWORD *)this + 14) + 24LL * v46 + 16) == 2 )
      {
        *((_DWORD *)v17 + 24) = v46;
        goto LABEL_34;
      }
      (*(void (__fastcall **)(__int64, __int64))*v17)((__int64)v15 - 8, 1);
    }
    else
    {
LABEL_34:
      v17[4] = this;
      v17[6] = *((_QWORD *)this + 2);
      v18 = (VMX_IO_RAID5 **)*((_QWORD *)this + 5);
      if ( *v18 != (VMX_IO_RAID5 *)((char *)this + 32) )
        goto LABEL_68;
      *(_QWORD *)v15 = (char *)this + 32;
      *((_QWORD *)v15 + 1) = v18;
      *v18 = v15;
      *((_QWORD *)this + 5) = v15;
    }
  }
  if ( v7 )
  {
    Pool2 = ExAllocatePool2(66, 112, 1632922966);
    v20 = (VMX_RAID5_SYNCHRONIZATION_TASK *)Pool2;
    if ( Pool2 )
    {
      memset((void *)(Pool2 + 8), 0, 0x58u);
      *((_QWORD *)v20 + 12) = 0;
      *(_QWORD *)v20 = &VMX_RAID5_SYNCHRONIZATION_TASK::`vftable';
      *((_QWORD *)v20 + 13) = 0;
      if ( (int)VMX_RAID5_SYNCHRONIZATION_TASK::Initialize(v20, this, *(_QWORD *)(j + 16), *((_QWORD *)this + 2)) >= 0 )
      {
        v21 = (VMX_IO_RAID5 **)*((_QWORD *)this + 5);
        if ( *v21 == (VMX_IO_RAID5 *)((char *)this + 32) )
        {
          *((_QWORD *)v20 + 1) = (char *)this + 32;
          *((_QWORD *)v20 + 2) = v21;
          *v21 = (VMX_RAID5_SYNCHRONIZATION_TASK *)((char *)v20 + 8);
          *((_QWORD *)this + 5) = (char *)v20 + 8;
          goto LABEL_42;
        }
LABEL_68:
        __fastfail(3u);
      }
      (**(void (__fastcall ***)(VMX_RAID5_SYNCHRONIZATION_TASK *, __int64))v20)(v20, 1);
    }
  }
LABEL_42:
  v22 = 0;
  if ( *(_QWORD *)(j + 104) == *((_QWORD *)this + 12) )
    v22 = *(_BYTE *)(j + 262);
  *((_BYTE *)this + 262) = v22;
  v23 = *(_BYTE *)(j + 263);
LABEL_51:
  *((_BYTE *)this + 263) = v23;
  if ( *((_BYTE *)this + 261) )
  {
    if ( !VMX_IO_RAID5::QuerySynchronizationTask(this) )
    {
      v27 = ExAllocatePool2(66, 112, 1632922966);
      v28 = (_QWORD *)v27;
      if ( v27 )
      {
        memset((void *)(v27 + 8), 0, 0x58u);
        *v28 = &VMX_RAID5_SYNCHRONIZATION_TASK::`vftable';
        v28[12] = 0;
        v28[13] = 0;
        if ( (int)VMX_RAID5_SYNCHRONIZATION_TASK::Initialize(
                    (VMX_RAID5_SYNCHRONIZATION_TASK *)v28,
                    this,
                    0,
                    *((_QWORD *)this + 2)) < 0 )
        {
          (*(void (__fastcall **)(_QWORD *, __int64))*v28)(v28, 1);
        }
        else
        {
          v29 = (VMX_IO_RAID5 **)*((_QWORD *)this + 5);
          if ( *v29 != (VMX_IO_RAID5 *)((char *)this + 32) )
            goto LABEL_68;
          v28[1] = (char *)this + 32;
          v28[2] = v29;
          *v29 = (VMX_IO_RAID5 *)(v28 + 1);
          *((_QWORD *)this + 5) = v28 + 1;
        }
      }
    }
  }
  v30 = *((_DWORD *)this + 14);
  LODWORD(v31) = 0;
  v32 = *((_QWORD *)this + 14);
  v33 = 0;
  v34 = 0;
  if ( v30 )
  {
    do
    {
      v35 = *(_DWORD *)(v32 + 16) == 3;
      v32 += 24;
      v36 = v34;
      if ( !v35 )
        v36 = v31;
      v31 = v36;
      v37 = v33 + 1;
      if ( !v35 )
        v37 = v33;
      ++v34;
      v33 = v37;
    }
    while ( v34 < v30 );
    if ( v37 )
    {
      v38 = ExAllocatePool2(66, 120, 1632922966);
      v39 = (_QWORD *)v38;
      if ( v38 )
      {
        memset((void *)(v38 + 8), 0, 0x58u);
        v39[13] = 0;
        *v39 = &VMX_RAID5_REGENERATION_TASK::`vftable';
        v39[14] = 0;
        if ( (int)VMX_RAID5_REGENERATION_TASK::Initialize(
                    (VMX_RAID5_REGENERATION_TASK *)v39,
                    this,
                    v31,
                    v40,
                    *((_QWORD *)this + 2)) < 0 )
        {
          (*(void (__fastcall **)(_QWORD *, __int64))*v39)(v39, 1);
        }
        else
        {
          *(_DWORD *)(*((_QWORD *)this + 14) + 24 * v31 + 16) = 2;
          v41 = (VMX_IO_RAID5 **)*((_QWORD *)this + 5);
          if ( *v41 != (VMX_IO_RAID5 *)((char *)this + 32) )
            goto LABEL_68;
          v39[1] = (char *)this + 32;
          v39[2] = v41;
          *v41 = (VMX_IO_RAID5 *)(v39 + 1);
          *((_QWORD *)this + 5) = v39 + 1;
        }
      }
    }
  }
  v42 = *((_QWORD *)this + 14);
  v43 = 0;
  v44 = *((_DWORD *)this + 14);
  *((_BYTE *)this + 264) = 0;
  while ( v43 < v44 )
  {
    if ( *(_BYTE *)(v42 + 20) && *(_DWORD *)(v42 + 16) != 4 )
    {
      *((_BYTE *)this + 264) = 1;
      return;
    }
    ++v43;
    v42 += 24;
  }
}

```

## disassembly

```asm
0x14000c160  mov     rax, rsp
0x14000c163  mov     [rax+8], rbx
0x14000c167  push    rbp
0x14000c168  push    rsi
0x14000c169  push    rdi
0x14000c16a  push    r12
0x14000c16c  push    r13
0x14000c16e  push    r14
0x14000c170  push    r15
0x14000c172  sub     rsp, 30h
0x14000c176  xor     r12d, r12d
0x14000c179  mov     rdi, rdx
0x14000c17c  mov     [rax+18h], r12d
0x14000c180  mov     rbx, rcx
0x14000c183  mov     [rax+10h], r12d
0x14000c187  call    ?CommitFaultTolerantObjects@VMX_IO_OPERATOR@@UEAAXPEAVVMX_IO_OBJECT@@@Z; VMX_IO_OPERATOR::CommitFaultTolerantObjects(VMX_IO_OBJECT *)
0x14000c18c  lea     rbp, ??_7VMX_RAID5_SYNCHRONIZATION_TASK@@6B@; const VMX_RAID5_SYNCHRONIZATION_TASK::`vftable'
0x14000c193  lea     r13d, [r12+1]
0x14000c198  test    rdi, rdi
0x14000c19b  jz      loc_14000C420
0x14000c1a1  mov     rax, [rdi]
0x14000c1a4  mov     r8b, r13b
0x14000c1a7  mov     rdx, [rbx+50h]
0x14000c1ab  mov     rcx, rdi
0x14000c1ae  mov     rax, [rax+0D0h]
0x14000c1b5  call    _guard_dispatch_icall
0x14000c1ba  mov     r14, rax
0x14000c1bd  test    rax, rax
0x14000c1c0  jz      loc_14000C420
0x14000c1c6  mov     r15b, r12b
0x14000c1c9  cmp     [rax+105h], r12b
0x14000c1d0  jz      short loc_14000C1DB
0x14000c1d2  mov     [rbx+105h], r13b
0x14000c1d9  jmp     short loc_14000C1FA
0x14000c1db  cmp     [rbx+105h], r12b
0x14000c1e2  jz      short loc_14000C1FA
0x14000c1e4  mov     rax, [rbx+10h]
0x14000c1e8  cmp     [r14+10h], rax
0x14000c1ec  jnb     short loc_14000C1F3
0x14000c1ee  mov     r15b, r13b
0x14000c1f1  jmp     short loc_14000C1FA
0x14000c1f3  mov     [rbx+105h], r12b
0x14000c1fa  mov     esi, r12d
0x14000c1fd  mov     rdi, [rbx+70h]
0x14000c201  mov     rbp, r14
0x14000c204  cmp     [rbx+38h], r12d
0x14000c208  jbe     loc_14000C2A1
0x14000c20e  cmp     [rdi+15h], r12b
0x14000c212  jnz     short loc_14000C26A
0x14000c214  mov     rdx, [rdi]; unsigned __int64
0x14000c217  lea     r9, [rsp+68h+arg_8]; unsigned int *
0x14000c21c  mov     r8b, r13b; unsigned __int8
0x14000c21f  mov     rcx, r14; this
0x14000c222  call    ?FindFaultTolerantMember@VMX_IO_RAID5@@QEAAE_KEPEAK@Z; VMX_IO_RAID5::FindFaultTolerantMember(unsigned __int64,uchar,ulong *)
0x14000c227  test    al, al
0x14000c229  jz      short loc_14000C26A
0x14000c22b  mov     eax, [rsp+68h+arg_8]
0x14000c22f  lea     rcx, [rax+rax*2]
0x14000c233  mov     rax, [r14+70h]
0x14000c237  mov     edx, [rax+rcx*8+10h]
0x14000c23b  cmp     edx, 4
0x14000c23e  jnz     short loc_14000C245
0x14000c240  mov     [rdi+10h], edx
0x14000c243  jmp     short loc_14000C26A
0x14000c245  mov     eax, [rdi+10h]
0x14000c248  cmp     eax, 4
0x14000c24b  jz      short loc_14000C26A
0x14000c24d  cmp     edx, 2
0x14000c250  jnz     short loc_14000C257
0x14000c252  mov     [rdi+10h], edx
0x14000c255  jmp     short loc_14000C26A
0x14000c257  cmp     edx, 3
0x14000c25a  jnz     short loc_14000C261
0x14000c25c  mov     [rdi+10h], edx
0x14000c25f  jmp     short loc_14000C26A
0x14000c261  cmp     eax, 3
0x14000c264  jnz     short loc_14000C26A
0x14000c266  mov     [rdi+10h], r12d
0x14000c26a  mov     [rdi+15h], r12b
0x14000c26e  cmp     [rdi+14h], r12b
0x14000c272  jz      short loc_14000C291
0x14000c274  mov     eax, [rdi+10h]
0x14000c277  sub     eax, 2
0x14000c27a  cmp     eax, r13d
0x14000c27d  ja      short loc_14000C291
0x14000c27f  xor     r8d, r8d; unsigned __int8
0x14000c282  mov     edx, esi; unsigned int
0x14000c284  mov     rcx, rbx; this
0x14000c287  call    ?DetachFaultTolerantMember@VMX_IO_RAID5@@QEAAEKE@Z; VMX_IO_RAID5::DetachFaultTolerantMember(ulong,uchar)
0x14000c28c  call    ?PropagateFaultTolerantChanges@VMX_IO_RAID5@@QEAAXXZ; VMX_IO_RAID5::PropagateFaultTolerantChanges(void)
0x14000c291  add     esi, r13d
0x14000c294  add     rdi, 18h
0x14000c298  cmp     esi, [rbx+38h]
0x14000c29b  jb      loc_14000C20E
0x14000c2a1  add     r14, 20h ; ' '
0x14000c2a5  mov     rdi, [r14]
0x14000c2a8  cmp     rdi, r14
0x14000c2ab  jz      loc_14000C35F
0x14000c2b1  cmp     [rdi+8], r14
0x14000c2b5  jnz     loc_14000C5CD
0x14000c2bb  mov     rax, [rdi]
0x14000c2be  cmp     [rax+8], rdi
0x14000c2c2  jnz     loc_14000C5CD
0x14000c2c8  mov     [r14], rax
0x14000c2cb  lea     rsi, [rdi-8]
0x14000c2cf  mov     [rax+8], r14
0x14000c2d3  cmp     dword ptr [rsi+18h], 3
0x14000c2d7  jnz     short loc_14000C32F
0x14000c2d9  mov     eax, [rsi+60h]
0x14000c2dc  lea     r9, [rsp+68h+arg_10]; unsigned int *
0x14000c2e4  mov     rdx, [rbp+70h]
0x14000c2e8  xor     r8d, r8d; unsigned __int8
0x14000c2eb  lea     rcx, [rax+rax*2]
0x14000c2ef  mov     rdx, [rdx+rcx*8+8]; unsigned __int64
0x14000c2f4  mov     rcx, rbx; this
0x14000c2f7  call    ?FindFaultTolerantMember@VMX_IO_RAID5@@QEAAE_KEPEAK@Z; VMX_IO_RAID5::FindFaultTolerantMember(unsigned __int64,uchar,ulong *)
0x14000c2fc  test    al, al
0x14000c2fe  jz      short loc_14000C316
0x14000c300  mov     ecx, [rsp+68h+arg_10]
0x14000c307  mov     rax, [rbx+70h]
0x14000c30b  lea     rdx, [rcx+rcx*2]
0x14000c30f  cmp     dword ptr [rax+rdx*8+10h], 2
0x14000c314  jz      short loc_14000C32C
0x14000c316  mov     rax, [rsi]
0x14000c319  mov     edx, r13d
0x14000c31c  mov     rcx, rsi
0x14000c31f  mov     rax, [rax]
0x14000c322  call    _guard_dispatch_icall
0x14000c327  jmp     loc_14000C2A5
0x14000c32c  mov     [rsi+60h], ecx
0x14000c32f  mov     [rsi+20h], rbx
0x14000c333  mov     rax, [rbx+10h]
0x14000c337  mov     [rsi+30h], rax
0x14000c33b  lea     rax, [rbx+20h]
0x14000c33f  mov     rcx, [rax+8]
0x14000c343  cmp     [rcx], rax
0x14000c346  jnz     loc_14000C5CD
0x14000c34c  mov     [rdi], rax
0x14000c34f  mov     [rdi+8], rcx
0x14000c353  mov     [rcx], rdi
0x14000c356  mov     [rax+8], rdi
0x14000c35a  jmp     loc_14000C2A5
0x14000c35f  test    r15b, r15b
0x14000c362  jz      loc_14000C3F8
0x14000c368  mov     edx, 70h ; 'p'
0x14000c36d  mov     r8d, 61546D56h
0x14000c373  lea     ecx, [rdx-2Eh]
0x14000c376  call    cs:__imp_ExAllocatePool2
0x14000c37d  nop     dword ptr [rax+rax+00h]
0x14000c382  mov     rdi, rax
0x14000c385  test    rax, rax
0x14000c388  jz      short loc_14000C3F8
0x14000c38a  xor     edx, edx; Val
0x14000c38c  lea     rcx, [rax+8]; void *
0x14000c390  lea     r8d, [rdx+58h]; Size
0x14000c394  call    memset
0x14000c399  mov     [rdi+60h], r12
0x14000c39d  lea     rax, ??_7VMX_RAID5_SYNCHRONIZATION_TASK@@6B@; const VMX_RAID5_SYNCHRONIZATION_TASK::`vftable'
0x14000c3a4  mov     [rdi], rax
0x14000c3a7  mov     rdx, rbx; struct VMX_IO_RAID5 *
0x14000c3aa  mov     [rdi+68h], r12
0x14000c3ae  mov     rcx, rdi; this
0x14000c3b1  mov     r9, [rbx+10h]; unsigned __int64
0x14000c3b5  mov     r8, [rbp+10h]; unsigned __int64
0x14000c3b9  call    ?Initialize@VMX_RAID5_SYNCHRONIZATION_TASK@@QEAAJPEAVVMX_IO_RAID5@@_K1@Z; VMX_RAID5_SYNCHRONIZATION_TASK::Initialize(VMX_IO_RAID5 *,unsigned __int64,unsigned __int64)
0x14000c3be  test    eax, eax
0x14000c3c0  js      short loc_14000C3E7
0x14000c3c2  lea     rcx, [rbx+20h]
0x14000c3c6  mov     rdx, [rcx+8]
0x14000c3ca  cmp     [rdx], rcx
0x14000c3cd  jnz     loc_14000C5CD
0x14000c3d3  lea     rax, [rdi+8]
0x14000c3d7  mov     [rax], rcx
0x14000c3da  mov     [rax+8], rdx
0x14000c3de  mov     [rdx], rax
0x14000c3e1  mov     [rcx+8], rax
0x14000c3e5  jmp     short loc_14000C3F8
0x14000c3e7  mov     rax, [rdi]
0x14000c3ea  mov     edx, r13d
0x14000c3ed  mov     rcx, rdi
0x14000c3f0  mov     rax, [rax]
0x14000c3f3  call    _guard_dispatch_icall
0x14000c3f8  mov     rax, [rbx+60h]
0x14000c3fc  cmp     [rbp+68h], rax
0x14000c400  mov     al, r12b
0x14000c403  jnz     short loc_14000C40B
0x14000c405  mov     al, [rbp+106h]
0x14000c40b  mov     [rbx+106h], al
0x14000c411  mov     al, [rbp+107h]
0x14000c417  lea     rbp, ??_7VMX_RAID5_SYNCHRONIZATION_TASK@@6B@; const VMX_RAID5_SYNCHRONIZATION_TASK::`vftable'
0x14000c41e  jmp     short loc_14000C461
0x14000c420  mov     esi, r12d
0x14000c423  mov     rdi, [rbx+70h]
0x14000c427  cmp     [rbx+38h], r12d
0x14000c42b  jbe     short loc_14000C457
0x14000c42d  cmp     [rdi+14h], r12b
0x14000c431  jz      short loc_14000C44B
0x14000c433  cmp     dword ptr [rdi+10h], 3
0x14000c437  jnz     short loc_14000C44B
0x14000c439  xor     r8d, r8d; unsigned __int8
0x14000c43c  mov     edx, esi; unsigned int
0x14000c43e  mov     rcx, rbx; this
0x14000c441  call    ?DetachFaultTolerantMember@VMX_IO_RAID5@@QEAAEKE@Z; VMX_IO_RAID5::DetachFaultTolerantMember(ulong,uchar)
0x14000c446  call    ?PropagateFaultTolerantChanges@VMX_IO_RAID5@@QEAAXXZ; VMX_IO_RAID5::PropagateFaultTolerantChanges(void)
0x14000c44b  add     esi, r13d
0x14000c44e  add     rdi, 18h
0x14000c452  cmp     esi, [rbx+38h]
0x14000c455  jb      short loc_14000C42D
0x14000c457  mov     [rbx+106h], r12b
0x14000c45e  mov     al, r12b
0x14000c461  mov     [rbx+107h], al
0x14000c467  cmp     [rbx+105h], r12b
0x14000c46e  jz      loc_14000C50B
0x14000c474  mov     rcx, rbx; this
0x14000c477  call    ?QuerySynchronizationTask@VMX_IO_RAID5@@QEAAPEAVVMX_RAID5_SYNCHRONIZATION_TASK@@XZ; VMX_IO_RAID5::QuerySynchronizationTask(void)
0x14000c47c  test    rax, rax
0x14000c47f  jnz     loc_14000C50B
0x14000c485  lea     edx, [rax+70h]
0x14000c488  mov     r8d, 61546D56h
0x14000c48e  lea     ecx, [rax+42h]
0x14000c491  call    cs:__imp_ExAllocatePool2
0x14000c498  nop     dword ptr [rax+rax+00h]
0x14000c49d  mov     rdi, rax
0x14000c4a0  test    rax, rax
0x14000c4a3  jz      short loc_14000C50B
0x14000c4a5  xor     edx, edx; Val
0x14000c4a7  lea     rcx, [rax+8]; void *
0x14000c4ab  lea     r8d, [rdx+58h]; Size
0x14000c4af  call    memset
0x14000c4b4  mov     [rdi], rbp
0x14000c4b7  xor     r8d, r8d; unsigned __int64
0x14000c4ba  mov     [rdi+60h], r12
0x14000c4be  mov     rdx, rbx; struct VMX_IO_RAID5 *
0x14000c4c1  mov     [rdi+68h], r12
0x14000c4c5  mov     rcx, rdi; this
0x14000c4c8  mov     r9, [rbx+10h]; unsigned __int64
0x14000c4cc  call    ?Initialize@VMX_RAID5_SYNCHRONIZATION_TASK@@QEAAJPEAVVMX_IO_RAID5@@_K1@Z; VMX_RAID5_SYNCHRONIZATION_TASK::Initialize(VMX_IO_RAID5 *,unsigned __int64,unsigned __int64)
0x14000c4d1  test    eax, eax
0x14000c4d3  js      short loc_14000C4FA
0x14000c4d5  lea     rcx, [rbx+20h]
0x14000c4d9  mov     rdx, [rcx+8]
0x14000c4dd  cmp     [rdx], rcx
0x14000c4e0  jnz     loc_14000C5CD
0x14000c4e6  lea     rax, [rdi+8]
0x14000c4ea  mov     [rax], rcx
0x14000c4ed  mov     [rax+8], rdx
0x14000c4f1  mov     [rdx], rax
0x14000c4f4  mov     [rcx+8], rax
0x14000c4f8  jmp     short loc_14000C50B
0x14000c4fa  mov     rax, [rdi]
0x14000c4fd  mov     edx, r13d
0x14000c500  mov     rcx, rdi
0x14000c503  mov     rax, [rax]
0x14000c506  call    _guard_dispatch_icall
0x14000c50b  mov     r10d, [rbx+38h]
0x14000c50f  mov     esi, r12d
0x14000c512  mov     r11, [rbx+70h]
0x14000c516  mov     edx, r12d
0x14000c519  mov     r9d, r12d
0x14000c51c  test    r10d, r10d
0x14000c51f  jz      loc_14000C5F9
0x14000c525  cmp     dword ptr [r11+10h], 3
0x14000c52a  lea     r11, [r11+18h]
0x14000c52e  mov     eax, r9d
0x14000c531  cmovnz  eax, esi
0x14000c534  mov     esi, eax
0x14000c536  lea     eax, [rdx+1]
0x14000c539  cmovnz  eax, edx
0x14000c53c  add     r9d, r13d
0x14000c53f  mov     edx, eax
0x14000c541  cmp     r9d, r10d
0x14000c544  jb      short loc_14000C525
0x14000c546  test    eax, eax
0x14000c548  jz      loc_14000C5F9
0x14000c54e  mov     edx, 78h ; 'x'
0x14000c553  mov     r8d, 61546D56h
0x14000c559  lea     ecx, [rdx-36h]
0x14000c55c  call    cs:__imp_ExAllocatePool2
0x14000c563  nop     dword ptr [rax+rax+00h]
0x14000c568  mov     rdi, rax
0x14000c56b  test    rax, rax
0x14000c56e  jz      loc_14000C5F9
0x14000c574  xor     edx, edx; Val
0x14000c576  lea     rcx, [rax+8]; void *
0x14000c57a  lea     r8d, [rdx+58h]; Size
0x14000c57e  call    memset
0x14000c583  lea     rax, ??_7VMX_RAID5_REGENERATION_TASK@@6B@; const VMX_RAID5_REGENERATION_TASK::`vftable'
0x14000c58a  mov     [rdi+68h], r12
0x14000c58e  mov     [rdi], rax
0x14000c591  mov     r8d, esi; unsigned int
0x14000c594  mov     [rdi+70h], r12
0x14000c598  mov     rdx, rbx; struct VMX_IO_RAID5 *
0x14000c59b  mov     rcx, [rbx+10h]
0x14000c59f  mov     [rsp+68h+var_48], rcx; unsigned __int64
0x14000c5a4  mov     rcx, rdi; this
0x14000c5a7  call    ?Initialize@VMX_RAID5_REGENERATION_TASK@@QEAAJPEAVVMX_IO_RAID5@@K_K1@Z; VMX_RAID5_REGENERATION_TASK::Initialize(VMX_IO_RAID5 *,ulong,unsigned __int64,unsigned __int64)
0x14000c5ac  test    eax, eax
0x14000c5ae  js      short loc_14000C5E8
0x14000c5b0  mov     rax, [rbx+70h]
0x14000c5b4  lea     rdx, [rsi+rsi*2]
  ... truncated ...
```
