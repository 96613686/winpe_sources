# SIO_RAID5::BuildChildPacketsReconstruct(SC_PACKET *,SC_SEQUENTIAL *)

- ea: `0x14004db28`
- end: `0x14004df1d`
- name: `?BuildChildPacketsReconstruct@SIO_RAID5@@QEAAJPEAVSC_PACKET@@PEAVSC_SEQUENTIAL@@@Z`
- size: `1013`
- prototype: `__int64 __fastcall(SIO_RAID5 *__hidden this, struct SC_PACKET *, struct SC_SEQUENTIAL *)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x140009770`

## callees

- `0x140005eb0`
- `0x140009f80`
- `0x14000aca0`
- `0x140015320`
- `0x1400154c0`
- `0x14001af40`
- `0x14001b090`
- `0x14001cda0`
- `0x1400268c0`
- `0x14002f7e8`
- `0x14004db28`
- `0x14004f37c`
- `0x14004f91c`
- `0x1400565e0`
- `0x140068000`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004db90`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004db90`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004dc20`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004dc61`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004dc20`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004dc61`

## pseudocode

```c
__int64 __fastcall SIO_RAID5::BuildChildPacketsReconstruct(
        SIO_RAID5 *this,
        struct SC_PACKET *a2,
        struct SC_SEQUENTIAL *a3)
{
  struct SC_PACKET *v4; // rsi
  signed __int32 v5; // r12d
  unsigned __int64 v6; // rdx
  struct SC_SEQUENTIAL *v7; // r13
  _DWORD *v8; // r15
  unsigned int v9; // ebx
  struct SP_RESILIENCY_INFO *v11; // rax
  _QWORD *v12; // rbx
  _QWORD *i; // rdi
  __int64 v14; // rcx
  PVOID v15; // rax
  __int64 v16; // rcx
  unsigned int v18; // ebx
  __int64 v19; // rdi
  int v20; // eax
  unsigned int v21; // edi
  unsigned __int8 IsReadable; // al
  unsigned int v23; // r11d
  unsigned int v24; // eax
  struct SC_PACKET *v25; // r11
  unsigned __int64 v26; // r13
  unsigned int v27; // eax
  struct SC_PACKET **v28; // r11
  signed __int32 *v29; // rcx
  unsigned int j; // r12d
  SC_PACKET *v31; // rax
  SC_PACKET *v32; // rax
  SC_PACKET *v33; // rdi
  unsigned int v34; // [rsp+30h] [rbp-38h] BYREF
  unsigned int MirrorCopy; // [rsp+34h] [rbp-34h]
  unsigned __int64 v36; // [rsp+38h] [rbp-30h]
  unsigned int v37; // [rsp+40h] [rbp-28h]
  unsigned int v38; // [rsp+44h] [rbp-24h]
  unsigned int v39; // [rsp+48h] [rbp-20h]
  unsigned int v40; // [rsp+4Ch] [rbp-1Ch]
  _DWORD *v41; // [rsp+50h] [rbp-18h]
  __int64 v42; // [rsp+58h] [rbp-10h]
  signed __int32 v43; // [rsp+B0h] [rbp+48h] BYREF
  struct SC_PACKET *v44; // [rsp+B8h] [rbp+50h]
  struct SC_SEQUENTIAL *v45; // [rsp+C0h] [rbp+58h]
  unsigned int v46; // [rsp+C8h] [rbp+60h] BYREF

  v45 = a3;
  v44 = a2;
  v4 = a2;
  v5 = 0;
  v6 = *((_QWORD *)a2 + 17) >> *((_BYTE *)this + 42);
  v43 = 0;
  v34 = 0;
  v7 = a3;
  v36 = v6;
  if ( !SIO_RAID5::IsRowStable(this, v6) )
  {
    v8 = 0;
    v9 = -1058602983;
LABEL_3:
    if ( v7 )
      return v9;
LABEL_4:
    if ( !v8 )
      return v9;
LABEL_5:
    ExFreePoolWithTag(v8, 0);
    return v9;
  }
  if ( v7 )
  {
    v8 = (_DWORD *)*((_QWORD *)v7 + 4);
    v41 = v8;
  }
  else
  {
    v11 = SIO_RAID::Resiliency(this);
    v41 = SC_ENV::Allocate((unsigned int)(8 * *((_DWORD *)v11 + 4)) + 24LL, 0x70587053u, 0, 0);
    v8 = v41;
    if ( !v41 )
      return (unsigned int)-1073741670;
    v12 = (_QWORD *)((char *)v4 + 96);
    for ( i = (_QWORD *)*((_QWORD *)v4 + 12); i != v12; i = (_QWORD *)*i )
    {
      v14 = *(i - 10);
      if ( (*(_BYTE *)(v14 + 10) & 5) != 0 )
        v15 = *(PVOID *)(v14 + 24);
      else
        v15 = MmMapLockedPagesSpecifyCache((PMDL)v14, 0, MmCached, 0, 0, 0x40000020u);
      if ( !v15 )
        goto LABEL_22;
    }
    if ( (_QWORD *)*v12 == v12 )
    {
      v16 = *((_QWORD *)v4 + 15);
      if ( !((*(_BYTE *)(v16 + 10) & 5) != 0
           ? *(PVOID *)(v16 + 24)
           : MmMapLockedPagesSpecifyCache((PMDL)v16, 0, MmCached, 0, 0, 0x40000020u)) )
      {
LABEL_22:
        v9 = -1073741670;
        goto LABEL_5;
      }
    }
  }
  v46 = *((_DWORD *)v4 + 40);
  v38 = *((_DWORD *)v4 + 38);
  MirrorCopy = SIO_RAID5::GetMirrorCopy(this, v38);
  if ( MirrorCopy != -1 && MirrorCopy >= *((_DWORD *)SIO_RAID::Resiliency(this) + 2) )
  {
    v9 = -1073741811;
    goto LABEL_3;
  }
  v18 = 0;
  v19 = *(_QWORD *)(*((_QWORD *)this + 1) + 384LL);
  v42 = v19;
  v20 = *(_DWORD *)(v19 + 40) + *(_DWORD *)(v19 + 48);
  v39 = *(_DWORD *)(v19 + 40);
  v37 = v20;
  v40 = *((_DWORD *)SIO_RAID::Resiliency(this) + 4);
  if ( !v40 )
    goto LABEL_41;
  do
  {
    v21 = SIO_RAID5::UnRotate(this, v36, v18);
    if ( MirrorCopy == -1 )
    {
      IsReadable = SIO_RAID::IsReadable(this, v18);
      v23 = v40;
    }
    else
    {
      IsReadable = SIO_RAID::IsReadable(this, v18, MirrorCopy);
    }
    if ( !IsReadable )
      goto LABEL_38;
    v24 = SIO_RAID5::GetParityCopy(this, v38) - 1;
    if ( !v24 )
    {
      if ( v21 < v37 )
        goto LABEL_39;
LABEL_38:
      _bittestandset((signed __int32 *)&v46, v21);
      goto LABEL_39;
    }
    if ( v24 == 1 && v21 >= v39 && v21 != v37 )
      goto LABEL_38;
LABEL_39:
    ++v18;
  }
  while ( v18 < v23 );
  v4 = v44;
  v8 = v41;
  v7 = v45;
  v5 = v43;
  v19 = v42;
LABEL_41:
  v25 = (struct SC_PACKET *)*((_QWORD *)v4 + 12);
  if ( v25 == (struct SC_PACKET *)((char *)v4 + 96) )
  {
    _bittestandset((signed __int32 *)&v34, SIO_RAID5::UnRotate(this, v36, *((_DWORD *)v4 + 37)));
  }
  else
  {
    v26 = v36;
    do
    {
      v27 = SIO_RAID5::UnRotate(this, v26, *((_DWORD *)v25 - 13));
      v29 = (signed __int32 *)&v34;
      if ( !_bittest((const signed __int32 *)&v46, v27) )
        v29 = &v43;
      _bittestandset(v29, v27);
      v25 = *v28;
    }
    while ( v25 != (struct SC_PACKET *)((char *)v4 + 96) );
    v5 = v43;
    v7 = v45;
  }
  v9 = SC_PARITY::InitializeContext((PEX_SPIN_LOCK)v19, v34, v46, (struct SC_PARITY_CONTEXT *)v8, 0);
  if ( (v9 & 0x80000000) != 0 )
    goto LABEL_3;
  v43 = v8[2] | v5;
  for ( j = *((_DWORD *)v4 + 48); j < *((_DWORD *)SIO_RAID::Resiliency(this) + 4); ++j )
  {
    if ( _bittest(&v43, SIO_RAID5::UnRotate(this, v36, j)) )
    {
      if ( v7 )
      {
        v33 = *(SC_PACKET **)v7;
      }
      else
      {
        v31 = (SC_PACKET *)SC_PACKET::operator new(0xF8u, *((struct SC_PACKET **)v4 + 1));
        if ( !v31 || (v32 = SC_PACKET::SC_PACKET(v31), (v33 = v32) == 0) )
        {
          v9 = -1073741670;
          goto LABEL_4;
        }
        v9 = SC_BUFFER::Initialize((__int64)v32 + 112, 3, 0, *((_DWORD *)v4 + 36));
        if ( (v9 & 0x80000000) != 0 )
        {
          (**(void (__fastcall ***)(SC_PACKET *, __int64))v33)(v33, 1);
          goto LABEL_4;
        }
      }
      *((_QWORD *)v33 + 17) = *((_QWORD *)v4 + 17);
      *((_DWORD *)v33 + 36) = *((_DWORD *)v4 + 36);
      *((_DWORD *)v33 + 38) = MirrorCopy;
      *((_DWORD *)v33 + 37) = j;
      *((_BYTE *)v33 + 168) = 3;
      *((_QWORD *)v33 + 30) = this;
      SC_PACKET::Attach(v4, v33, 0);
      if ( v7 )
        return v9;
    }
  }
  if ( !v7 )
    *((_QWORD *)v4 + 24) = v8;
  return v9;
}

```

## disassembly

```asm
0x14004db28  mov     [rsp-40h+arg_10], r8
0x14004db2d  mov     [rsp-40h+arg_8], rdx
0x14004db32  push    rbp
0x14004db33  push    rbx
0x14004db34  push    rsi
0x14004db35  push    rdi
0x14004db36  push    r12
0x14004db38  push    r13
0x14004db3a  push    r14
0x14004db3c  push    r15
0x14004db3e  mov     rbp, rsp
0x14004db41  sub     rsp, 68h
0x14004db45  mov     rax, [rdx+88h]
0x14004db4c  mov     r14, rcx
0x14004db4f  mov     cl, [rcx+2Ah]
0x14004db52  mov     rsi, rdx
0x14004db55  shr     rax, cl
0x14004db58  xor     r12d, r12d
0x14004db5b  mov     rdx, rax; unsigned __int64
0x14004db5e  mov     [rbp+arg_0], r12d
0x14004db62  mov     rcx, r14; this
0x14004db65  mov     [rbp+var_38], r12d
0x14004db69  mov     r13, r8
0x14004db6c  mov     [rbp+var_30], rax
0x14004db70  call    ?IsRowStable@SIO_RAID5@@QEAAE_K@Z; SIO_RAID5::IsRowStable(unsigned __int64)
0x14004db75  test    al, al
0x14004db77  jnz     short loc_14004DBB0
0x14004db79  xor     r15d, r15d
0x14004db7c  mov     ebx, 0C0E70019h
0x14004db81  test    r13, r13
0x14004db84  jnz     short loc_14004DB9C
0x14004db86  test    r15, r15
0x14004db89  jz      short loc_14004DB9C
0x14004db8b  xor     edx, edx; Tag
0x14004db8d  mov     rcx, r15; P
0x14004db90  call    cs:__imp_ExFreePoolWithTag
0x14004db97  nop     dword ptr [rax+rax+00h]
0x14004db9c  mov     eax, ebx
0x14004db9e  add     rsp, 68h
0x14004dba2  pop     r15
0x14004dba4  pop     r14
0x14004dba6  pop     r13
0x14004dba8  pop     r12
0x14004dbaa  pop     rdi
0x14004dbab  pop     rsi
0x14004dbac  pop     rbx
0x14004dbad  pop     rbp
0x14004dbae  retn
0x14004dbb0  test    r13, r13
0x14004dbb3  jnz     loc_14004DC7C
0x14004dbb9  mov     rcx, r14; this
0x14004dbbc  call    ?Resiliency@SIO_RAID@@UEAAPEAVSP_RESILIENCY_INFO@@XZ; SIO_RAID::Resiliency(void)
0x14004dbc1  xor     r9d, r9d; unsigned int
0x14004dbc4  xor     r8d, r8d; unsigned __int8
0x14004dbc7  mov     edx, 70587053h; unsigned int
0x14004dbcc  mov     ecx, [rax+10h]
0x14004dbcf  shl     ecx, 3
0x14004dbd2  add     rcx, 18h; unsigned __int64
0x14004dbd6  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x14004dbdb  mov     [rbp+var_18], rax
0x14004dbdf  mov     r15, rax
0x14004dbe2  test    rax, rax
0x14004dbe5  jnz     short loc_14004DBEE
0x14004dbe7  mov     ebx, 0C000009Ah
0x14004dbec  jmp     short loc_14004DB9C
0x14004dbee  lea     rbx, [rsi+60h]
0x14004dbf2  mov     rdi, [rbx]
0x14004dbf5  cmp     rdi, rbx
0x14004dbf8  jz      short loc_14004DC36
0x14004dbfa  mov     rcx, [rdi-50h]; MemoryDescriptorList
0x14004dbfe  test    byte ptr [rcx+0Ah], 5
0x14004dc02  jz      short loc_14004DC0A
0x14004dc04  mov     rax, [rcx+18h]
0x14004dc08  jmp     short loc_14004DC2C
0x14004dc0a  xor     r9d, r9d; RequestedAddress
0x14004dc0d  mov     [rsp+68h+Priority], 40000020h; Priority
0x14004dc15  xor     edx, edx; AccessMode
0x14004dc17  mov     [rsp+68h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x14004dc1c  lea     r8d, [r9+1]; CacheType
0x14004dc20  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004dc27  nop     dword ptr [rax+rax+00h]
0x14004dc2c  test    rax, rax
0x14004dc2f  jz      short loc_14004DC72
0x14004dc31  mov     rdi, [rdi]
0x14004dc34  jmp     short loc_14004DBF5
0x14004dc36  cmp     [rbx], rbx
0x14004dc39  jnz     short loc_14004DC84
0x14004dc3b  mov     rcx, [rsi+78h]; MemoryDescriptorList
0x14004dc3f  test    byte ptr [rcx+0Ah], 5
0x14004dc43  jz      short loc_14004DC4B
0x14004dc45  mov     rax, [rcx+18h]
0x14004dc49  jmp     short loc_14004DC6D
0x14004dc4b  xor     r9d, r9d; RequestedAddress
0x14004dc4e  mov     [rsp+68h+Priority], 40000020h; Priority
0x14004dc56  xor     edx, edx; AccessMode
0x14004dc58  mov     [rsp+68h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x14004dc5d  lea     r8d, [r9+1]; CacheType
0x14004dc61  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004dc68  nop     dword ptr [rax+rax+00h]
0x14004dc6d  test    rax, rax
0x14004dc70  jnz     short loc_14004DC84
0x14004dc72  mov     ebx, 0C000009Ah
0x14004dc77  jmp     loc_14004DB8B
0x14004dc7c  mov     r15, [r13+20h]
0x14004dc80  mov     [rbp+var_18], r15
0x14004dc84  mov     eax, [rsi+0A0h]
0x14004dc8a  mov     rcx, r14; this
0x14004dc8d  mov     [rbp+arg_18], eax
0x14004dc90  mov     eax, [rsi+98h]
0x14004dc96  mov     edx, eax; unsigned int
0x14004dc98  mov     [rbp+var_24], eax
0x14004dc9b  call    ?GetMirrorCopy@SIO_RAID5@@QEAAKK@Z; SIO_RAID5::GetMirrorCopy(ulong)
0x14004dca0  mov     [rbp+var_34], eax
0x14004dca3  mov     ebx, eax
0x14004dca5  cmp     eax, 0FFFFFFFFh
0x14004dca8  jz      short loc_14004DCC1
0x14004dcaa  mov     rcx, r14; this
0x14004dcad  call    ?Resiliency@SIO_RAID@@UEAAPEAVSP_RESILIENCY_INFO@@XZ; SIO_RAID::Resiliency(void)
0x14004dcb2  cmp     ebx, [rax+8]
0x14004dcb5  jb      short loc_14004DCC1
0x14004dcb7  mov     ebx, 0C000000Dh
0x14004dcbc  jmp     loc_14004DB81
0x14004dcc1  mov     rax, [r14+8]
0x14004dcc5  xor     ebx, ebx
0x14004dcc7  mov     rdi, [rax+180h]
0x14004dcce  mov     [rbp+var_10], rdi
0x14004dcd2  mov     ecx, [rdi+28h]
0x14004dcd5  mov     eax, [rdi+30h]
0x14004dcd8  add     eax, ecx
0x14004dcda  mov     [rbp+var_20], ecx
0x14004dcdd  mov     rcx, r14; this
0x14004dce0  mov     [rbp+var_28], eax
0x14004dce3  call    ?Resiliency@SIO_RAID@@UEAAPEAVSP_RESILIENCY_INFO@@XZ; SIO_RAID::Resiliency(void)
0x14004dce8  mov     r11d, [rax+10h]
0x14004dcec  mov     [rbp+var_1C], r11d
0x14004dcf0  test    r11d, r11d
0x14004dcf3  jz      loc_14004DD82
0x14004dcf9  mov     r13d, [rbp+var_28]
0x14004dcfd  mov     r12d, [rbp+var_24]
0x14004dd01  mov     esi, [rbp+var_20]
0x14004dd04  mov     r15d, [rbp+var_34]
0x14004dd08  mov     rdx, [rbp+var_30]; unsigned __int64
0x14004dd0c  mov     r8d, ebx; unsigned int
0x14004dd0f  mov     rcx, r14; this
0x14004dd12  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x14004dd17  mov     edi, eax
0x14004dd19  mov     edx, ebx; unsigned int
0x14004dd1b  mov     rcx, r14; this
0x14004dd1e  cmp     r15d, 0FFFFFFFFh
0x14004dd22  jnz     short loc_14004DD2F
0x14004dd24  call    ?IsReadable@SIO_RAID@@QEAAEK@Z; SIO_RAID::IsReadable(ulong)
0x14004dd29  mov     r11d, [rbp+var_1C]
0x14004dd2d  jmp     short loc_14004DD37
0x14004dd2f  mov     r8d, r15d; unsigned int
0x14004dd32  call    ?IsReadable@SIO_RAID@@QEAAEKK@Z; SIO_RAID::IsReadable(ulong,ulong)
0x14004dd37  test    al, al
0x14004dd39  jz      short loc_14004DD60
0x14004dd3b  mov     edx, r12d; unsigned int
0x14004dd3e  mov     rcx, r14; this
0x14004dd41  call    ?GetParityCopy@SIO_RAID5@@QEAAKK@Z; SIO_RAID5::GetParityCopy(ulong)
0x14004dd46  sub     eax, 1
0x14004dd49  jz      short loc_14004DD5B
0x14004dd4b  cmp     eax, 1
0x14004dd4e  jnz     short loc_14004DD67
0x14004dd50  cmp     edi, esi
0x14004dd52  jb      short loc_14004DD67
0x14004dd54  cmp     edi, r13d
0x14004dd57  jnz     short loc_14004DD60
0x14004dd59  jmp     short loc_14004DD67
0x14004dd5b  cmp     edi, r13d
0x14004dd5e  jb      short loc_14004DD67
0x14004dd60  lea     rax, [rbp+arg_18]
0x14004dd64  bts     [rax], edi
0x14004dd67  inc     ebx
0x14004dd69  cmp     ebx, r11d
0x14004dd6c  jb      short loc_14004DD08
0x14004dd6e  mov     rsi, [rbp+arg_8]
0x14004dd72  mov     r15, [rbp+var_18]
0x14004dd76  mov     r13, [rbp+arg_10]
0x14004dd7a  mov     r12d, [rbp+arg_0]
0x14004dd7e  mov     rdi, [rbp+var_10]
0x14004dd82  lea     rbx, [rsi+60h]
0x14004dd86  mov     r11, [rbx]
0x14004dd89  cmp     r11, rbx
0x14004dd8c  jz      short loc_14004DDC7
0x14004dd8e  mov     r13, [rbp+var_30]
0x14004dd92  mov     r8d, [r11-34h]; unsigned int
0x14004dd96  mov     rdx, r13; unsigned __int64
0x14004dd99  mov     rcx, r14; this
0x14004dd9c  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x14004dda1  lea     rcx, [rbp+arg_18]
0x14004dda5  bt      [rcx], eax
0x14004dda8  lea     rcx, [rbp+var_38]
0x14004ddac  jb      short loc_14004DDB2
0x14004ddae  lea     rcx, [rbp+arg_0]
0x14004ddb2  bts     [rcx], eax
0x14004ddb5  mov     r11, [r11]
0x14004ddb8  cmp     r11, rbx
0x14004ddbb  jnz     short loc_14004DD92
0x14004ddbd  mov     r12d, [rbp+arg_0]
0x14004ddc1  mov     r13, [rbp+arg_10]
0x14004ddc5  jmp     short loc_14004DDE1
0x14004ddc7  mov     rdx, [rbp+var_30]; unsigned __int64
0x14004ddcb  mov     rcx, r14; this
0x14004ddce  mov     r8d, [rsi+94h]; unsigned int
0x14004ddd5  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x14004ddda  lea     rcx, [rbp+var_38]
0x14004ddde  bts     [rcx], eax
0x14004dde1  mov     r8d, [rbp+arg_18]; unsigned int
0x14004dde5  mov     r9, r15; struct SC_PARITY_CONTEXT *
0x14004dde8  mov     edx, [rbp+var_38]; unsigned int
0x14004ddeb  mov     rcx, rdi; SpinLock
0x14004ddee  mov     byte ptr [rsp+68h+BugCheckOnFailure], 0; unsigned __int8
0x14004ddf3  call    ?InitializeContext@SC_PARITY@@QEAAJKKPEAVSC_PARITY_CONTEXT@@E@Z; SC_PARITY::InitializeContext(ulong,ulong,SC_PARITY_CONTEXT *,uchar)
0x14004ddf8  mov     ebx, eax
0x14004ddfa  test    eax, eax
0x14004ddfc  js      loc_14004DB81
0x14004de02  or      r12d, [r15+8]
0x14004de06  mov     [rbp+arg_0], r12d
0x14004de0a  mov     r12d, [rsi+0C0h]
0x14004de11  mov     rcx, r14; this
0x14004de14  call    ?Resiliency@SIO_RAID@@UEAAPEAVSP_RESILIENCY_INFO@@XZ; SIO_RAID::Resiliency(void)
0x14004de19  cmp     r12d, [rax+10h]
0x14004de1d  jnb     loc_14004DF08
0x14004de23  mov     rdx, [rbp+var_30]; unsigned __int64
0x14004de27  mov     r8d, r12d; unsigned int
0x14004de2a  mov     rcx, r14; this
0x14004de2d  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x14004de32  lea     rcx, [rbp+arg_0]
0x14004de36  bt      [rcx], eax
0x14004de39  jnb     loc_14004DEF6
0x14004de3f  test    r13, r13
0x14004de42  jnz     short loc_14004DEA3
0x14004de44  mov     rdx, [rsi+8]; struct SC_PACKET *
0x14004de48  mov     ecx, 0F8h; unsigned __int64
0x14004de4d  call    ??2SC_PACKET@@SAPEAX_KPEAV0@@Z; SC_PACKET::operator new(unsigned __int64,SC_PACKET *)
0x14004de52  test    rax, rax
0x14004de55  jz      loc_14004DEFE
0x14004de5b  mov     rcx, rax; this
0x14004de5e  call    ??0SC_PACKET@@QEAA@XZ; SC_PACKET::SC_PACKET(void)
0x14004de63  mov     rdi, rax
0x14004de66  test    rax, rax
0x14004de69  jz      loc_14004DEFE
0x14004de6f  mov     r9d, [rsi+90h]
0x14004de76  lea     rcx, [rax+70h]
0x14004de7a  xor     r8d, r8d
0x14004de7d  lea     edx, [r13+3]
0x14004de81  call    ?Initialize@SC_BUFFER@@QEAAJW4_SC_BUFFER_TYPE@@PEAXK@Z; SC_BUFFER::Initialize(_SC_BUFFER_TYPE,void *,ulong)
0x14004de86  mov     ebx, eax
0x14004de88  test    eax, eax
0x14004de8a  jns     short loc_14004DEA7
0x14004de8c  mov     rax, [rdi]
0x14004de8f  lea     edx, [r13+1]
0x14004de93  mov     rcx, rdi
0x14004de96  mov     rax, [rax]
0x14004de99  call    _guard_dispatch_icall
0x14004de9e  jmp     loc_14004DB86
0x14004dea3  mov     rdi, [r13+0]
0x14004dea7  mov     rax, [rsi+88h]
0x14004deae  xor     r8d, r8d; unsigned __int8
0x14004deb1  mov     [rdi+88h], rax
0x14004deb8  mov     rdx, rdi; struct SC_PACKET *
0x14004debb  mov     eax, [rsi+90h]
0x14004dec1  mov     rcx, rsi; this
0x14004dec4  mov     [rdi+90h], eax
0x14004deca  mov     eax, [rbp+var_34]
0x14004decd  mov     [rdi+98h], eax
0x14004ded3  mov     [rdi+94h], r12d
0x14004deda  mov     byte ptr [rdi+0A8h], 3
0x14004dee1  mov     [rdi+0F0h], r14
0x14004dee8  call    ?Attach@SC_PACKET@@QEAAXPEAV1@E@Z; SC_PACKET::Attach(SC_PACKET *,uchar)
0x14004deed  test    r13, r13
0x14004def0  jnz     loc_14004DB9C
0x14004def6  inc     r12d
0x14004def9  jmp     loc_14004DE11
0x14004defe  mov     ebx, 0C000009Ah
0x14004df03  jmp     loc_14004DB86
0x14004df08  test    r13, r13
0x14004df0b  jnz     loc_14004DB9C
0x14004df11  mov     [rsi+0C0h], r15
0x14004df18  jmp     loc_14004DB9C
```
