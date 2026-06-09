# VMX_IO_MIRROR::CommitFaultTolerantObjects(VMX_IO_OBJECT *)

- ea: `0x14000ba90`
- end: `0x14000c0f9`
- name: `?CommitFaultTolerantObjects@VMX_IO_MIRROR@@UEAAXPEAVVMX_IO_OBJECT@@@Z`
- size: `1641`
- prototype: `void __fastcall(VMX_IO_MIRROR *__hidden this, struct VMX_IO_OBJECT *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x140007358`
- `0x14000ba90`
- `0x14000c100`
- `0x14000d078`
- `0x14000d140`
- `0x14000de34`
- `0x14000e088`
- `0x14000f9f8`
- `0x14001b9a0`
- `0x14001be80`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000bda3`
- `ntoskrnl!ExAllocatePool2` at `0x14000bebf`
- `ntoskrnl!ExAllocatePool2` at `0x14000bf80`
- `ntoskrnl!ExAllocatePool2` at `0x14000bfd6`
- `ntoskrnl!ExAllocatePool2` at `0x14000bda3`
- `ntoskrnl!ExAllocatePool2` at `0x14000bebf`
- `ntoskrnl!ExAllocatePool2` at `0x14000bf80`
- `ntoskrnl!ExAllocatePool2` at `0x14000bfd6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c0a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c0a3`

## pseudocode

```c
void __fastcall VMX_IO_MIRROR::CommitFaultTolerantObjects(VMX_IO_MIRROR *this, struct VMX_IO_OBJECT *a2)
{
  __int64 v4; // r8
  __int64 v5; // rax
  _QWORD *v6; // r12
  unsigned int v7; // esi
  __int64 v8; // rdi
  __int64 j; // rbp
  __int64 v10; // r8
  __int64 v11; // rdx
  int v12; // eax
  int v13; // ecx
  VMX_IO_MIRROR *v14; // rcx
  _QWORD *v15; // r12
  _DWORD *v16; // rdi
  __int64 v17; // rax
  unsigned int v18; // r15d
  unsigned int v19; // esi
  __int64 v20; // r13
  __int64 v21; // rax
  unsigned int v22; // eax
  unsigned int v23; // r13d
  void (__fastcall ***v24)(_QWORD, __int64); // rcx
  VMX_IO_MIRROR **v25; // rcx
  __int64 Pool2; // rax
  VMX_MIRROR_SYNCHRONIZATION_TASK *v27; // rdi
  VMX_IO_MIRROR **v28; // rdx
  char v29; // al
  unsigned int v30; // esi
  __int64 i; // rdi
  VMX_IO_MIRROR *v32; // rcx
  __int64 v33; // rax
  _QWORD *v34; // rdi
  VMX_IO_MIRROR **v35; // rdx
  unsigned int v36; // r9d
  unsigned int v37; // esi
  __int64 v38; // r8
  unsigned int v39; // edx
  bool v40; // zf
  unsigned int v41; // ecx
  unsigned int *v42; // r14
  unsigned int v43; // r11d
  unsigned int v44; // edx
  __int64 v45; // r9
  unsigned int k; // r10d
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rdi
  unsigned int v50; // r8d
  __int64 v51; // rax
  VMX_IO_MIRROR **v52; // r8
  __int64 v53; // rax
  unsigned int v54; // ecx
  unsigned int v55; // edx
  unsigned __int64 v56; // [rsp+20h] [rbp-58h]
  __int64 v57; // [rsp+30h] [rbp-48h]
  char v58; // [rsp+88h] [rbp+10h]
  _QWORD *v59; // [rsp+90h] [rbp+18h] BYREF
  unsigned int v60; // [rsp+98h] [rbp+20h] BYREF

  v60 = 0;
  LODWORD(v59) = 0;
  VMX_IO_OPERATOR::CommitFaultTolerantObjects(this, a2);
  if ( !a2
    || (LOBYTE(v4) = 1,
        v5 = (*(__int64 (__fastcall **)(struct VMX_IO_OBJECT *, _QWORD, __int64))(*(_QWORD *)a2 + 208LL))(
               a2,
               *((_QWORD *)this + 10),
               v4),
        v57 = v5,
        (v6 = (_QWORD *)v5) == 0) )
  {
    v30 = 0;
    for ( i = *((_QWORD *)this + 12); v30 < *((_DWORD *)this + 14); i += 40 )
    {
      if ( *(_BYTE *)(i + 20) && *(_DWORD *)(i + 16) == 3 )
      {
        VMX_IO_MIRROR::DetachFaultTolerantMember(this, v30, 0);
        VMX_IO_MIRROR::PropagateFaultTolerantChanges(v32);
      }
      ++v30;
    }
    *((_BYTE *)this + 157) = 0;
    v29 = 0;
    goto LABEL_60;
  }
  v58 = 0;
  if ( *(_BYTE *)(v5 + 156) )
  {
    *((_BYTE *)this + 156) = 1;
  }
  else if ( *((_BYTE *)this + 156) )
  {
    if ( *(_QWORD *)(v5 + 16) >= *((_QWORD *)this + 2) )
      *((_BYTE *)this + 156) = 0;
    else
      v58 = 1;
  }
  v7 = 0;
  v8 = *((_QWORD *)this + 12);
  for ( j = v5; v7 < *((_DWORD *)this + 14); v8 += 40 )
  {
    if ( !*(_BYTE *)(v8 + 21)
      && VMX_IO_MIRROR::FindFaultTolerantMember((VMX_IO_MIRROR *)v6, *(_QWORD *)v8, 1u, (unsigned int *)&v59) )
    {
      v10 = v6[12];
      v11 = 5LL * (unsigned int)v59;
      v12 = *(_DWORD *)(v10 + 40LL * (unsigned int)v59 + 16);
      if ( v12 == 4 )
      {
        *(_DWORD *)(v8 + 16) = 4;
        v13 = 4;
      }
      else
      {
        v13 = *(_DWORD *)(v8 + 16);
        if ( v13 != 4 )
        {
          if ( v12 == 2 )
          {
            *(_DWORD *)(v8 + 16) = 2;
            v13 = 2;
          }
          else if ( v12 == 3 )
          {
            *(_DWORD *)(v8 + 16) = 3;
            v13 = 3;
          }
          else if ( v13 == 3 )
          {
            *(_DWORD *)(v8 + 16) = 0;
            v13 = 0;
          }
        }
      }
      *(_DWORD *)(v8 + 28) = *(_DWORD *)(v10 + 8 * v11 + 28);
      *(_QWORD *)(v8 + 32) = *(_QWORD *)(v10 + 8 * v11 + 32);
      if ( !*(_DWORD *)(v10 + 8 * v11 + 16) && !v13 )
        *(_BYTE *)(v8 + 26) = *(_BYTE *)(v10 + 8 * v11 + 26);
    }
    *(_BYTE *)(v8 + 21) = 0;
    if ( *(_BYTE *)(v8 + 20) && (unsigned int)(*(_DWORD *)(v8 + 16) - 2) <= 1 )
    {
      VMX_IO_MIRROR::DetachFaultTolerantMember(this, v7, 0);
      VMX_IO_MIRROR::PropagateFaultTolerantChanges(v14);
    }
    ++v7;
  }
  v15 = v6 + 4;
  v59 = v15;
  while ( 1 )
  {
    v16 = (_DWORD *)*v15;
    if ( (_QWORD *)*v15 == v15 )
      break;
    if ( *((_QWORD **)v16 + 1) != v15 )
      goto LABEL_82;
    v17 = *(_QWORD *)v16;
    if ( *(_DWORD **)(*(_QWORD *)v16 + 8LL) != v16 )
      goto LABEL_82;
    *v15 = v17;
    *(_QWORD *)(v17 + 8) = v15;
    if ( v16[4] == 1 )
    {
      v18 = 0;
      v19 = 0;
      if ( v16[22] )
      {
        do
        {
          v20 = *((_QWORD *)v16 + 12);
          if ( VMX_IO_MIRROR::FindFaultTolerantMember(
                 this,
                 *(_QWORD *)(*(_QWORD *)(v57 + 96) + 40LL * *(unsigned int *)(v20 + 4LL * v18) + 8),
                 0,
                 &v60)
            && *(_DWORD *)(*((_QWORD *)this + 12) + 40LL * v60 + 16) == 2 )
          {
            v21 = v19++;
            *(_DWORD *)(v20 + 4 * v21) = v60;
          }
          v22 = v16[22];
          ++v18;
        }
        while ( v18 < v22 );
        v15 = v59;
        if ( v19 )
        {
          v23 = v19;
          if ( v19 < v22 )
          {
            do
            {
              v24 = *(void (__fastcall ****)(_QWORD, __int64))(*((_QWORD *)v16 + 14) + 8LL * v19);
              if ( v24 )
                (**v24)(v24, 1);
              *(_QWORD *)(*((_QWORD *)v16 + 14) + 8LL * v19++) = 0;
            }
            while ( v19 < v16[22] );
          }
          v16[22] = v23;
          goto LABEL_44;
        }
      }
      (**((void (__fastcall ***)(__int64, __int64))v16 - 1))((__int64)(v16 - 2), 1);
    }
    else
    {
LABEL_44:
      *((_QWORD *)v16 + 3) = this;
      *((_QWORD *)v16 + 5) = *((_QWORD *)this + 2);
      v25 = (VMX_IO_MIRROR **)*((_QWORD *)this + 5);
      if ( *v25 != (VMX_IO_MIRROR *)((char *)this + 32) )
        goto LABEL_82;
      *(_QWORD *)v16 = (char *)this + 32;
      *((_QWORD *)v16 + 1) = v25;
      *v25 = (VMX_IO_MIRROR *)v16;
      *((_QWORD *)this + 5) = v16;
    }
  }
  if ( v58 )
  {
    Pool2 = ExAllocatePool2(66, 112, 1632922966);
    v27 = (VMX_MIRROR_SYNCHRONIZATION_TASK *)Pool2;
    if ( Pool2 )
    {
      memset((void *)(Pool2 + 8), 0, 0x58u);
      *((_QWORD *)v27 + 12) = 0;
      *(_QWORD *)v27 = &VMX_MIRROR_SYNCHRONIZATION_TASK::`vftable';
      *((_QWORD *)v27 + 13) = 0;
      if ( (int)VMX_MIRROR_SYNCHRONIZATION_TASK::Initialize(v27, this, *(_QWORD *)(j + 16), *((_QWORD *)this + 2)) >= 0 )
      {
        v28 = (VMX_IO_MIRROR **)*((_QWORD *)this + 5);
        if ( *v28 == (VMX_IO_MIRROR *)((char *)this + 32) )
        {
          *((_QWORD *)v27 + 1) = (char *)this + 32;
          *((_QWORD *)v27 + 2) = v28;
          *v28 = (VMX_MIRROR_SYNCHRONIZATION_TASK *)((char *)v27 + 8);
          *((_QWORD *)this + 5) = (char *)v27 + 8;
          goto LABEL_53;
        }
LABEL_82:
        __fastfail(3u);
      }
      (**(void (__fastcall ***)(VMX_MIRROR_SYNCHRONIZATION_TASK *, __int64))v27)(v27, 1);
    }
  }
LABEL_53:
  *((_BYTE *)this + 157) = *(_BYTE *)(j + 157);
  v29 = *(_BYTE *)(j + 158);
LABEL_60:
  *((_BYTE *)this + 158) = v29;
  if ( *((_BYTE *)this + 156) )
  {
    if ( !VMX_IO_MIRROR::QuerySynchronizationTask(this) )
    {
      v33 = ExAllocatePool2(66, 112, 1632922966);
      v34 = (_QWORD *)v33;
      if ( v33 )
      {
        memset((void *)(v33 + 8), 0, 0x58u);
        *v34 = &VMX_MIRROR_SYNCHRONIZATION_TASK::`vftable';
        v34[12] = 0;
        v34[13] = 0;
        if ( (int)VMX_MIRROR_SYNCHRONIZATION_TASK::Initialize(
                    (VMX_MIRROR_SYNCHRONIZATION_TASK *)v34,
                    this,
                    0,
                    *((_QWORD *)this + 2)) < 0 )
        {
          (*(void (__fastcall **)(_QWORD *, __int64))*v34)(v34, 1);
        }
        else
        {
          v35 = (VMX_IO_MIRROR **)*((_QWORD *)this + 5);
          if ( *v35 != (VMX_IO_MIRROR *)((char *)this + 32) )
            goto LABEL_82;
          v34[1] = (char *)this + 32;
          v34[2] = v35;
          *v35 = (VMX_IO_MIRROR *)(v34 + 1);
          *((_QWORD *)this + 5) = v34 + 1;
        }
      }
    }
  }
  v36 = *((_DWORD *)this + 14);
  v37 = 0;
  v38 = *((_QWORD *)this + 12);
  v39 = 0;
  if ( v36 )
  {
    do
    {
      v40 = *(_DWORD *)(v38 + 16) == 3;
      v41 = v37 + 1;
      v38 += 40;
      if ( !v40 )
        v41 = v37;
      ++v39;
      v37 = v41;
    }
    while ( v39 < v36 );
    if ( v41 )
    {
      v42 = (unsigned int *)ExAllocatePool2(66, 4LL * v41, 538996054);
      if ( v42 )
      {
        v43 = *((_DWORD *)this + 14);
        v44 = 0;
        v45 = *((_QWORD *)this + 12);
        for ( k = 0; v44 < v43; v45 += 40 )
        {
          if ( *(_DWORD *)(v45 + 16) == 3 )
          {
            v47 = k++;
            v42[v47] = v44;
          }
          ++v44;
        }
        v48 = ExAllocatePool2(66, 144, 1632922966);
        v49 = v48;
        if ( v48 )
        {
          memset((void *)(v48 + 8), 0, 0x58u);
          *(_DWORD *)(v49 + 96) = 0;
          *(_QWORD *)v49 = &VMX_MIRROR_REGENERATION_TASK::`vftable';
          *(_QWORD *)(v49 + 104) = 0;
          *(_QWORD *)(v49 + 112) = 0;
          *(_QWORD *)(v49 + 120) = 0;
          *(_QWORD *)(v49 + 128) = 0;
          *(_BYTE *)(v49 + 140) = 0;
          if ( (int)VMX_MIRROR_REGENERATION_TASK::Initialize(
                      (VMX_MIRROR_REGENERATION_TASK *)v49,
                      this,
                      v37,
                      v42,
                      v56,
                      *((_QWORD *)this + 2)) >= 0 )
          {
            v50 = 0;
            do
            {
              v51 = v50++;
              *(_DWORD *)(*((_QWORD *)this + 12) + 40LL * v42[v51] + 16) = 2;
            }
            while ( v50 < v37 );
            v52 = (VMX_IO_MIRROR **)*((_QWORD *)this + 5);
            if ( *v52 != (VMX_IO_MIRROR *)((char *)this + 32) )
              goto LABEL_82;
            *(_QWORD *)(v49 + 8) = (char *)this + 32;
            *(_QWORD *)(v49 + 16) = v52;
            *v52 = (VMX_IO_MIRROR *)(v49 + 8);
            *((_QWORD *)this + 5) = v49 + 8;
            goto LABEL_86;
          }
          (**(void (__fastcall ***)(__int64, __int64))v49)(v49, 1);
        }
        ExFreePoolWithTag(v42, 0);
      }
    }
  }
LABEL_86:
  v53 = *((_QWORD *)this + 12);
  v54 = 0;
  v55 = *((_DWORD *)this + 14);
  *((_BYTE *)this + 159) = 0;
  while ( v54 < v55 )
  {
    if ( *(_BYTE *)(v53 + 20) && *(_DWORD *)(v53 + 16) != 4 )
    {
      *((_BYTE *)this + 159) = 1;
      return;
    }
    ++v54;
    v53 += 40;
  }
}

```

## disassembly

```asm
0x14000ba90  mov     rax, rsp
0x14000ba93  mov     [rax+8], rbx
0x14000ba97  push    rbp
0x14000ba98  push    rsi
0x14000ba99  push    rdi
0x14000ba9a  push    r12
0x14000ba9c  push    r13
0x14000ba9e  push    r14
0x14000baa0  push    r15
0x14000baa2  sub     rsp, 40h
0x14000baa6  xor     r13d, r13d
0x14000baa9  mov     rdi, rdx
0x14000baac  mov     [rax+20h], r13d
0x14000bab0  mov     rbx, rcx
0x14000bab3  mov     [rax+18h], r13d
0x14000bab7  call    ?CommitFaultTolerantObjects@VMX_IO_OPERATOR@@UEAAXPEAVVMX_IO_OBJECT@@@Z; VMX_IO_OPERATOR::CommitFaultTolerantObjects(VMX_IO_OBJECT *)
0x14000babc  lea     ebp, [r13+42h]
0x14000bac0  lea     r14d, [r13+2]
0x14000bac4  lea     r15d, [r13+1]
0x14000bac8  test    rdi, rdi
0x14000bacb  jz      loc_14000BE47
0x14000bad1  mov     rax, [rdi]
0x14000bad4  mov     r8b, r15b
0x14000bad7  mov     rdx, [rbx+50h]
0x14000badb  mov     rcx, rdi
0x14000bade  mov     rax, [rax+0D0h]
0x14000bae5  call    _guard_dispatch_icall
0x14000baea  mov     [rsp+78h+var_48], rax
0x14000baef  mov     r12, rax
0x14000baf2  test    rax, rax
0x14000baf5  jz      loc_14000BE47
0x14000bafb  mov     [rsp+78h+arg_8], r13b
0x14000bb03  cmp     [rax+9Ch], r13b
0x14000bb0a  jz      short loc_14000BB15
0x14000bb0c  mov     [rbx+9Ch], r15b
0x14000bb13  jmp     short loc_14000BB3A
0x14000bb15  cmp     [rbx+9Ch], r13b
0x14000bb1c  jz      short loc_14000BB3A
0x14000bb1e  mov     rax, [rbx+10h]
0x14000bb22  cmp     [r12+10h], rax
0x14000bb27  jnb     short loc_14000BB33
0x14000bb29  mov     [rsp+78h+arg_8], r15b
0x14000bb31  jmp     short loc_14000BB3A
0x14000bb33  mov     [rbx+9Ch], r13b
0x14000bb3a  mov     esi, r13d
0x14000bb3d  mov     rdi, [rbx+60h]
0x14000bb41  mov     rbp, r12
0x14000bb44  cmp     [rbx+38h], r13d
0x14000bb48  jbe     loc_14000BC24
0x14000bb4e  cmp     [rdi+15h], r13b
0x14000bb52  jnz     loc_14000BBED
0x14000bb58  mov     rdx, [rdi]; unsigned __int64
0x14000bb5b  lea     r9, [rsp+78h+arg_10]; unsigned int *
0x14000bb63  mov     r8b, r15b; unsigned __int8
0x14000bb66  mov     rcx, r12; this
0x14000bb69  call    ?FindFaultTolerantMember@VMX_IO_MIRROR@@QEAAE_KEPEAK@Z; VMX_IO_MIRROR::FindFaultTolerantMember(unsigned __int64,uchar,ulong *)
0x14000bb6e  test    al, al
0x14000bb70  jz      short loc_14000BBED
0x14000bb72  mov     eax, dword ptr [rsp+78h+arg_10]
0x14000bb79  mov     r9d, 4
0x14000bb7f  mov     r8, [r12+60h]
0x14000bb84  lea     rdx, [rax+rax*4]
0x14000bb88  mov     eax, [r8+rdx*8+10h]
0x14000bb8d  cmp     eax, r9d
0x14000bb90  jnz     short loc_14000BB9B
0x14000bb92  mov     [rdi+10h], r9d
0x14000bb96  mov     ecx, r9d
0x14000bb99  jmp     short loc_14000BBC9
0x14000bb9b  mov     ecx, [rdi+10h]
0x14000bb9e  cmp     ecx, r9d
0x14000bba1  jz      short loc_14000BBC9
0x14000bba3  cmp     eax, r14d
0x14000bba6  jnz     short loc_14000BBB1
0x14000bba8  mov     [rdi+10h], r14d
0x14000bbac  mov     ecx, r14d
0x14000bbaf  jmp     short loc_14000BBC9
0x14000bbb1  cmp     eax, 3
0x14000bbb4  jnz     short loc_14000BBBD
0x14000bbb6  mov     [rdi+10h], eax
0x14000bbb9  mov     ecx, eax
0x14000bbbb  jmp     short loc_14000BBC9
0x14000bbbd  cmp     ecx, 3
0x14000bbc0  jnz     short loc_14000BBC9
0x14000bbc2  mov     [rdi+10h], r13d
0x14000bbc6  mov     ecx, r13d
0x14000bbc9  mov     eax, [r8+rdx*8+1Ch]
0x14000bbce  mov     [rdi+1Ch], eax
0x14000bbd1  mov     rax, [r8+rdx*8+20h]
0x14000bbd6  mov     [rdi+20h], rax
0x14000bbda  cmp     [r8+rdx*8+10h], r13d
0x14000bbdf  jnz     short loc_14000BBED
0x14000bbe1  test    ecx, ecx
0x14000bbe3  jnz     short loc_14000BBED
0x14000bbe5  mov     al, [r8+rdx*8+1Ah]
0x14000bbea  mov     [rdi+1Ah], al
0x14000bbed  mov     [rdi+15h], r13b
0x14000bbf1  cmp     [rdi+14h], r13b
0x14000bbf5  jz      short loc_14000BC14
0x14000bbf7  mov     eax, [rdi+10h]
0x14000bbfa  sub     eax, r14d
0x14000bbfd  cmp     eax, r15d
0x14000bc00  ja      short loc_14000BC14
0x14000bc02  xor     r8d, r8d; unsigned __int8
0x14000bc05  mov     edx, esi; unsigned int
0x14000bc07  mov     rcx, rbx; this
0x14000bc0a  call    ?DetachFaultTolerantMember@VMX_IO_MIRROR@@QEAAEKE@Z; VMX_IO_MIRROR::DetachFaultTolerantMember(ulong,uchar)
0x14000bc0f  call    ?PropagateFaultTolerantChanges@VMX_IO_MIRROR@@QEAAXXZ; VMX_IO_MIRROR::PropagateFaultTolerantChanges(void)
0x14000bc14  add     esi, r15d
0x14000bc17  add     rdi, 28h ; '('
0x14000bc1b  cmp     esi, [rbx+38h]
0x14000bc1e  jb      loc_14000BB4E
0x14000bc24  add     r12, 20h ; ' '
0x14000bc28  mov     [rsp+78h+arg_10], r12
0x14000bc30  mov     rdi, [r12]
0x14000bc34  cmp     rdi, r12
0x14000bc37  jz      loc_14000BD87
0x14000bc3d  cmp     [rdi+8], r12
0x14000bc41  jnz     loc_14000C072
0x14000bc47  mov     rax, [rdi]
0x14000bc4a  cmp     [rax+8], rdi
0x14000bc4e  jnz     loc_14000C072
0x14000bc54  mov     [r12], rax
0x14000bc58  mov     [rax+8], r12
0x14000bc5c  cmp     [rdi+10h], r15d
0x14000bc60  jnz     loc_14000BD39
0x14000bc66  mov     r15d, r13d
0x14000bc69  mov     esi, r13d
0x14000bc6c  cmp     [rdi+58h], r13d
0x14000bc70  jbe     loc_14000BD69
0x14000bc76  mov     r12, [rsp+78h+var_48]
0x14000bc7b  mov     r13, [rdi+60h]
0x14000bc7f  lea     r9, [rsp+78h+arg_18]; unsigned int *
0x14000bc87  mov     rdx, [r12+60h]
0x14000bc8c  xor     r8d, r8d; unsigned __int8
0x14000bc8f  mov     eax, r15d
0x14000bc92  mov     ecx, [r13+rax*4+0]
0x14000bc97  lea     rax, [rcx+rcx*4]
0x14000bc9b  mov     rcx, rbx; this
0x14000bc9e  mov     rdx, [rdx+rax*8+8]; unsigned __int64
0x14000bca3  call    ?FindFaultTolerantMember@VMX_IO_MIRROR@@QEAAE_KEPEAK@Z; VMX_IO_MIRROR::FindFaultTolerantMember(unsigned __int64,uchar,ulong *)
0x14000bca8  test    al, al
0x14000bcaa  jz      short loc_14000BCCB
0x14000bcac  mov     edx, [rsp+78h+arg_18]
0x14000bcb3  mov     rax, [rbx+60h]
0x14000bcb7  lea     rcx, [rdx+rdx*4]
0x14000bcbb  cmp     [rax+rcx*8+10h], r14d
0x14000bcc0  jnz     short loc_14000BCCB
0x14000bcc2  mov     eax, esi
0x14000bcc4  inc     esi
0x14000bcc6  mov     [r13+rax*4+0], edx
0x14000bccb  mov     eax, [rdi+58h]
0x14000bcce  inc     r15d
0x14000bcd1  cmp     r15d, eax
0x14000bcd4  jb      short loc_14000BC7B
0x14000bcd6  mov     r12, [rsp+78h+arg_10]
0x14000bcde  xor     r13d, r13d
0x14000bce1  test    esi, esi
0x14000bce3  jz      loc_14000BD69
0x14000bce9  mov     r13d, esi
0x14000bcec  cmp     esi, eax
0x14000bcee  jnb     short loc_14000BD2C
0x14000bcf0  mov     rax, [rdi+70h]
0x14000bcf4  mov     r15d, esi
0x14000bcf7  mov     rcx, [rax+r15*8]
0x14000bcfb  test    rcx, rcx
0x14000bcfe  jz      short loc_14000BD10
0x14000bd00  mov     rax, [rcx]
0x14000bd03  mov     edx, 1
0x14000bd08  mov     rax, [rax]
0x14000bd0b  call    _guard_dispatch_icall
0x14000bd10  mov     rax, [rdi+70h]
0x14000bd14  mov     qword ptr [rax+r15*8], 0
0x14000bd1c  mov     r15d, 1
0x14000bd22  add     esi, r15d
0x14000bd25  cmp     esi, [rdi+58h]
0x14000bd28  jb      short loc_14000BCF0
0x14000bd2a  jmp     short loc_14000BD32
0x14000bd2c  mov     r15d, 1
0x14000bd32  mov     [rdi+58h], r13d
0x14000bd36  xor     r13d, r13d
0x14000bd39  mov     [rdi+18h], rbx
0x14000bd3d  mov     rax, [rbx+10h]
0x14000bd41  mov     [rdi+28h], rax
0x14000bd45  lea     rax, [rbx+20h]
0x14000bd49  mov     rcx, [rax+8]
0x14000bd4d  cmp     [rcx], rax
0x14000bd50  jnz     loc_14000C072
0x14000bd56  mov     [rdi], rax
0x14000bd59  mov     [rdi+8], rcx
0x14000bd5d  mov     [rcx], rdi
0x14000bd60  mov     [rax+8], rdi
0x14000bd64  jmp     loc_14000BC30
0x14000bd69  mov     rax, [rdi-8]
0x14000bd6d  lea     rcx, [rdi-8]
0x14000bd71  mov     r15d, 1
0x14000bd77  mov     edx, r15d
0x14000bd7a  mov     rax, [rax]
0x14000bd7d  call    _guard_dispatch_icall
0x14000bd82  jmp     loc_14000BC30
0x14000bd87  cmp     [rsp+78h+arg_8], r13b
0x14000bd8f  jz      loc_14000BE27
0x14000bd95  mov     edx, 70h ; 'p'
0x14000bd9a  mov     r8d, 61546D56h
0x14000bda0  lea     ecx, [rdx-2Eh]
0x14000bda3  call    cs:__imp_ExAllocatePool2
0x14000bdaa  nop     dword ptr [rax+rax+00h]
0x14000bdaf  mov     rdi, rax
0x14000bdb2  test    rax, rax
0x14000bdb5  jz      short loc_14000BE27
0x14000bdb7  xor     edx, edx; Val
0x14000bdb9  lea     rcx, [rax+8]; void *
0x14000bdbd  lea     r8d, [rdx+58h]; Size
0x14000bdc1  call    memset
0x14000bdc6  mov     [rdi+60h], r13
0x14000bdca  lea     rsi, ??_7VMX_MIRROR_SYNCHRONIZATION_TASK@@6B@; const VMX_MIRROR_SYNCHRONIZATION_TASK::`vftable'
0x14000bdd1  mov     [rdi], rsi
0x14000bdd4  mov     rdx, rbx; struct VMX_IO_MIRROR *
0x14000bdd7  mov     [rdi+68h], r13
0x14000bddb  mov     rcx, rdi; this
0x14000bdde  mov     r9, [rbx+10h]; unsigned __int64
0x14000bde2  mov     r8, [rbp+10h]; unsigned __int64
0x14000bde6  call    ?Initialize@VMX_MIRROR_SYNCHRONIZATION_TASK@@QEAAJPEAVVMX_IO_MIRROR@@_K1@Z; VMX_MIRROR_SYNCHRONIZATION_TASK::Initialize(VMX_IO_MIRROR *,unsigned __int64,unsigned __int64)
0x14000bdeb  test    eax, eax
0x14000bded  js      short loc_14000BE14
0x14000bdef  lea     rcx, [rbx+20h]
0x14000bdf3  mov     rdx, [rcx+8]
0x14000bdf7  cmp     [rdx], rcx
0x14000bdfa  jnz     loc_14000C072
0x14000be00  lea     rax, [rdi+8]
0x14000be04  mov     [rax], rcx
0x14000be07  mov     [rax+8], rdx
0x14000be0b  mov     [rdx], rax
0x14000be0e  mov     [rcx+8], rax
0x14000be12  jmp     short loc_14000BE2E
0x14000be14  mov     rax, [rdi]
0x14000be17  mov     edx, r15d
0x14000be1a  mov     rcx, rdi
0x14000be1d  mov     rax, [rax]
0x14000be20  call    _guard_dispatch_icall
0x14000be25  jmp     short loc_14000BE2E
0x14000be27  lea     rsi, ??_7VMX_MIRROR_SYNCHRONIZATION_TASK@@6B@; const VMX_MIRROR_SYNCHRONIZATION_TASK::`vftable'
0x14000be2e  mov     al, [rbp+9Dh]
0x14000be34  mov     [rbx+9Dh], al
0x14000be3a  mov     al, [rbp+9Eh]
0x14000be40  mov     ebp, 42h ; 'B'
0x14000be45  jmp     short loc_14000BE8F
0x14000be47  mov     esi, r13d
0x14000be4a  mov     rdi, [rbx+60h]
0x14000be4e  cmp     [rbx+38h], r13d
0x14000be52  jbe     short loc_14000BE7E
0x14000be54  cmp     [rdi+14h], r13b
0x14000be58  jz      short loc_14000BE72
0x14000be5a  cmp     dword ptr [rdi+10h], 3
0x14000be5e  jnz     short loc_14000BE72
0x14000be60  xor     r8d, r8d; unsigned __int8
0x14000be63  mov     edx, esi; unsigned int
0x14000be65  mov     rcx, rbx; this
0x14000be68  call    ?DetachFaultTolerantMember@VMX_IO_MIRROR@@QEAAEKE@Z; VMX_IO_MIRROR::DetachFaultTolerantMember(ulong,uchar)
0x14000be6d  call    ?PropagateFaultTolerantChanges@VMX_IO_MIRROR@@QEAAXXZ; VMX_IO_MIRROR::PropagateFaultTolerantChanges(void)
0x14000be72  add     esi, r15d
0x14000be75  add     rdi, 28h ; '('
0x14000be79  cmp     esi, [rbx+38h]
0x14000be7c  jb      short loc_14000BE54
0x14000be7e  mov     [rbx+9Dh], r13b
0x14000be85  lea     rsi, ??_7VMX_MIRROR_SYNCHRONIZATION_TASK@@6B@; const VMX_MIRROR_SYNCHRONIZATION_TASK::`vftable'
0x14000be8c  mov     al, r13b
0x14000be8f  mov     [rbx+9Eh], al
0x14000be95  cmp     [rbx+9Ch], r13b
0x14000be9c  jz      loc_14000BF39
0x14000bea2  mov     rcx, rbx; this
0x14000bea5  call    ?QuerySynchronizationTask@VMX_IO_MIRROR@@QEAAPEAVVMX_MIRROR_SYNCHRONIZATION_TASK@@XZ; VMX_IO_MIRROR::QuerySynchronizationTask(void)
0x14000beaa  test    rax, rax
0x14000bead  jnz     loc_14000BF39
0x14000beb3  lea     edx, [rax+70h]
0x14000beb6  mov     r8d, 61546D56h
0x14000bebc  mov     rcx, rbp
0x14000bebf  call    cs:__imp_ExAllocatePool2
0x14000bec6  nop     dword ptr [rax+rax+00h]
0x14000becb  mov     rdi, rax
0x14000bece  test    rax, rax
0x14000bed1  jz      short loc_14000BF39
0x14000bed3  xor     edx, edx; Val
0x14000bed5  lea     rcx, [rax+8]; void *
0x14000bed9  lea     r8d, [rdx+58h]; Size
0x14000bedd  call    memset
0x14000bee2  mov     [rdi], rsi
0x14000bee5  xor     r8d, r8d; unsigned __int64
0x14000bee8  mov     [rdi+60h], r13
0x14000beec  mov     rdx, rbx; struct VMX_IO_MIRROR *
0x14000beef  mov     [rdi+68h], r13
0x14000bef3  mov     rcx, rdi; this
0x14000bef6  mov     r9, [rbx+10h]; unsigned __int64
0x14000befa  call    ?Initialize@VMX_MIRROR_SYNCHRONIZATION_TASK@@QEAAJPEAVVMX_IO_MIRROR@@_K1@Z; VMX_MIRROR_SYNCHRONIZATION_TASK::Initialize(VMX_IO_MIRROR *,unsigned __int64,unsigned __int64)
0x14000beff  test    eax, eax
0x14000bf01  js      short loc_14000BF28
0x14000bf03  lea     rcx, [rbx+20h]
0x14000bf07  mov     rdx, [rcx+8]
0x14000bf0b  cmp     [rdx], rcx
0x14000bf0e  jnz     loc_14000C072
0x14000bf14  lea     rax, [rdi+8]
  ... truncated ...
```
