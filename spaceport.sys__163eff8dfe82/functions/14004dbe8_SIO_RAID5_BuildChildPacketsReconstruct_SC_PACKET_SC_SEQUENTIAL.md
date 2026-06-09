# SIO_RAID5::BuildChildPacketsReconstruct(SC_PACKET *,SC_SEQUENTIAL *)

- ea: `0x14004dbe8`
- end: `0x14004dfdd`
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
- `0x14002f858`
- `0x14004dbe8`
- `0x14004f43c`
- `0x14004f9dc`
- `0x1400566e0`
- `0x140068150`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004dc50`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004dc50`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004dce0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004dd21`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004dce0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004dd21`

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
0x14004dbe8  mov     [rsp-40h+arg_10], r8
0x14004dbed  mov     [rsp-40h+arg_8], rdx
0x14004dbf2  push    rbp
0x14004dbf3  push    rbx
0x14004dbf4  push    rsi
0x14004dbf5  push    rdi
0x14004dbf6  push    r12
0x14004dbf8  push    r13
0x14004dbfa  push    r14
0x14004dbfc  push    r15
0x14004dbfe  mov     rbp, rsp
0x14004dc01  sub     rsp, 68h
0x14004dc05  mov     rax, [rdx+88h]
0x14004dc0c  mov     r14, rcx
0x14004dc0f  mov     cl, [rcx+2Ah]
0x14004dc12  mov     rsi, rdx
0x14004dc15  shr     rax, cl
0x14004dc18  xor     r12d, r12d
0x14004dc1b  mov     rdx, rax; unsigned __int64
0x14004dc1e  mov     [rbp+arg_0], r12d
0x14004dc22  mov     rcx, r14; this
0x14004dc25  mov     [rbp+var_38], r12d
0x14004dc29  mov     r13, r8
0x14004dc2c  mov     [rbp+var_30], rax
0x14004dc30  call    ?IsRowStable@SIO_RAID5@@QEAAE_K@Z; SIO_RAID5::IsRowStable(unsigned __int64)
0x14004dc35  test    al, al
0x14004dc37  jnz     short loc_14004DC70
0x14004dc39  xor     r15d, r15d
0x14004dc3c  mov     ebx, 0C0E70019h
0x14004dc41  test    r13, r13
0x14004dc44  jnz     short loc_14004DC5C
0x14004dc46  test    r15, r15
0x14004dc49  jz      short loc_14004DC5C
0x14004dc4b  xor     edx, edx; Tag
0x14004dc4d  mov     rcx, r15; P
0x14004dc50  call    cs:__imp_ExFreePoolWithTag
0x14004dc57  nop     dword ptr [rax+rax+00h]
0x14004dc5c  mov     eax, ebx
0x14004dc5e  add     rsp, 68h
0x14004dc62  pop     r15
0x14004dc64  pop     r14
0x14004dc66  pop     r13
0x14004dc68  pop     r12
0x14004dc6a  pop     rdi
0x14004dc6b  pop     rsi
0x14004dc6c  pop     rbx
0x14004dc6d  pop     rbp
0x14004dc6e  retn
0x14004dc70  test    r13, r13
0x14004dc73  jnz     loc_14004DD3C
0x14004dc79  mov     rcx, r14; this
0x14004dc7c  call    ?Resiliency@SIO_RAID@@UEAAPEAVSP_RESILIENCY_INFO@@XZ; SIO_RAID::Resiliency(void)
0x14004dc81  xor     r9d, r9d; unsigned int
0x14004dc84  xor     r8d, r8d; unsigned __int8
0x14004dc87  mov     edx, 70587053h; unsigned int
0x14004dc8c  mov     ecx, [rax+10h]
0x14004dc8f  shl     ecx, 3
0x14004dc92  add     rcx, 18h; unsigned __int64
0x14004dc96  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x14004dc9b  mov     [rbp+var_18], rax
0x14004dc9f  mov     r15, rax
0x14004dca2  test    rax, rax
0x14004dca5  jnz     short loc_14004DCAE
0x14004dca7  mov     ebx, 0C000009Ah
0x14004dcac  jmp     short loc_14004DC5C
0x14004dcae  lea     rbx, [rsi+60h]
0x14004dcb2  mov     rdi, [rbx]
0x14004dcb5  cmp     rdi, rbx
0x14004dcb8  jz      short loc_14004DCF6
0x14004dcba  mov     rcx, [rdi-50h]; MemoryDescriptorList
0x14004dcbe  test    byte ptr [rcx+0Ah], 5
0x14004dcc2  jz      short loc_14004DCCA
0x14004dcc4  mov     rax, [rcx+18h]
0x14004dcc8  jmp     short loc_14004DCEC
0x14004dcca  xor     r9d, r9d; RequestedAddress
0x14004dccd  mov     [rsp+68h+Priority], 40000020h; Priority
0x14004dcd5  xor     edx, edx; AccessMode
0x14004dcd7  mov     [rsp+68h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x14004dcdc  lea     r8d, [r9+1]; CacheType
0x14004dce0  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004dce7  nop     dword ptr [rax+rax+00h]
0x14004dcec  test    rax, rax
0x14004dcef  jz      short loc_14004DD32
0x14004dcf1  mov     rdi, [rdi]
0x14004dcf4  jmp     short loc_14004DCB5
0x14004dcf6  cmp     [rbx], rbx
0x14004dcf9  jnz     short loc_14004DD44
0x14004dcfb  mov     rcx, [rsi+78h]; MemoryDescriptorList
0x14004dcff  test    byte ptr [rcx+0Ah], 5
0x14004dd03  jz      short loc_14004DD0B
0x14004dd05  mov     rax, [rcx+18h]
0x14004dd09  jmp     short loc_14004DD2D
0x14004dd0b  xor     r9d, r9d; RequestedAddress
0x14004dd0e  mov     [rsp+68h+Priority], 40000020h; Priority
0x14004dd16  xor     edx, edx; AccessMode
0x14004dd18  mov     [rsp+68h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x14004dd1d  lea     r8d, [r9+1]; CacheType
0x14004dd21  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004dd28  nop     dword ptr [rax+rax+00h]
0x14004dd2d  test    rax, rax
0x14004dd30  jnz     short loc_14004DD44
0x14004dd32  mov     ebx, 0C000009Ah
0x14004dd37  jmp     loc_14004DC4B
0x14004dd3c  mov     r15, [r13+20h]
0x14004dd40  mov     [rbp+var_18], r15
0x14004dd44  mov     eax, [rsi+0A0h]
0x14004dd4a  mov     rcx, r14; this
0x14004dd4d  mov     [rbp+arg_18], eax
0x14004dd50  mov     eax, [rsi+98h]
0x14004dd56  mov     edx, eax; unsigned int
0x14004dd58  mov     [rbp+var_24], eax
0x14004dd5b  call    ?GetMirrorCopy@SIO_RAID5@@QEAAKK@Z; SIO_RAID5::GetMirrorCopy(ulong)
0x14004dd60  mov     [rbp+var_34], eax
0x14004dd63  mov     ebx, eax
0x14004dd65  cmp     eax, 0FFFFFFFFh
0x14004dd68  jz      short loc_14004DD81
0x14004dd6a  mov     rcx, r14; this
0x14004dd6d  call    ?Resiliency@SIO_RAID@@UEAAPEAVSP_RESILIENCY_INFO@@XZ; SIO_RAID::Resiliency(void)
0x14004dd72  cmp     ebx, [rax+8]
0x14004dd75  jb      short loc_14004DD81
0x14004dd77  mov     ebx, 0C000000Dh
0x14004dd7c  jmp     loc_14004DC41
0x14004dd81  mov     rax, [r14+8]
0x14004dd85  xor     ebx, ebx
0x14004dd87  mov     rdi, [rax+180h]
0x14004dd8e  mov     [rbp+var_10], rdi
0x14004dd92  mov     ecx, [rdi+28h]
0x14004dd95  mov     eax, [rdi+30h]
0x14004dd98  add     eax, ecx
0x14004dd9a  mov     [rbp+var_20], ecx
0x14004dd9d  mov     rcx, r14; this
0x14004dda0  mov     [rbp+var_28], eax
0x14004dda3  call    ?Resiliency@SIO_RAID@@UEAAPEAVSP_RESILIENCY_INFO@@XZ; SIO_RAID::Resiliency(void)
0x14004dda8  mov     r11d, [rax+10h]
0x14004ddac  mov     [rbp+var_1C], r11d
0x14004ddb0  test    r11d, r11d
0x14004ddb3  jz      loc_14004DE42
0x14004ddb9  mov     r13d, [rbp+var_28]
0x14004ddbd  mov     r12d, [rbp+var_24]
0x14004ddc1  mov     esi, [rbp+var_20]
0x14004ddc4  mov     r15d, [rbp+var_34]
0x14004ddc8  mov     rdx, [rbp+var_30]; unsigned __int64
0x14004ddcc  mov     r8d, ebx; unsigned int
0x14004ddcf  mov     rcx, r14; this
0x14004ddd2  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x14004ddd7  mov     edi, eax
0x14004ddd9  mov     edx, ebx; unsigned int
0x14004dddb  mov     rcx, r14; this
0x14004ddde  cmp     r15d, 0FFFFFFFFh
0x14004dde2  jnz     short loc_14004DDEF
0x14004dde4  call    ?IsReadable@SIO_RAID@@QEAAEK@Z; SIO_RAID::IsReadable(ulong)
0x14004dde9  mov     r11d, [rbp+var_1C]
0x14004dded  jmp     short loc_14004DDF7
0x14004ddef  mov     r8d, r15d; unsigned int
0x14004ddf2  call    ?IsReadable@SIO_RAID@@QEAAEKK@Z; SIO_RAID::IsReadable(ulong,ulong)
0x14004ddf7  test    al, al
0x14004ddf9  jz      short loc_14004DE20
0x14004ddfb  mov     edx, r12d; unsigned int
0x14004ddfe  mov     rcx, r14; this
0x14004de01  call    ?GetParityCopy@SIO_RAID5@@QEAAKK@Z; SIO_RAID5::GetParityCopy(ulong)
0x14004de06  sub     eax, 1
0x14004de09  jz      short loc_14004DE1B
0x14004de0b  cmp     eax, 1
0x14004de0e  jnz     short loc_14004DE27
0x14004de10  cmp     edi, esi
0x14004de12  jb      short loc_14004DE27
0x14004de14  cmp     edi, r13d
0x14004de17  jnz     short loc_14004DE20
0x14004de19  jmp     short loc_14004DE27
0x14004de1b  cmp     edi, r13d
0x14004de1e  jb      short loc_14004DE27
0x14004de20  lea     rax, [rbp+arg_18]
0x14004de24  bts     [rax], edi
0x14004de27  inc     ebx
0x14004de29  cmp     ebx, r11d
0x14004de2c  jb      short loc_14004DDC8
0x14004de2e  mov     rsi, [rbp+arg_8]
0x14004de32  mov     r15, [rbp+var_18]
0x14004de36  mov     r13, [rbp+arg_10]
0x14004de3a  mov     r12d, [rbp+arg_0]
0x14004de3e  mov     rdi, [rbp+var_10]
0x14004de42  lea     rbx, [rsi+60h]
0x14004de46  mov     r11, [rbx]
0x14004de49  cmp     r11, rbx
0x14004de4c  jz      short loc_14004DE87
0x14004de4e  mov     r13, [rbp+var_30]
0x14004de52  mov     r8d, [r11-34h]; unsigned int
0x14004de56  mov     rdx, r13; unsigned __int64
0x14004de59  mov     rcx, r14; this
0x14004de5c  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x14004de61  lea     rcx, [rbp+arg_18]
0x14004de65  bt      [rcx], eax
0x14004de68  lea     rcx, [rbp+var_38]
0x14004de6c  jb      short loc_14004DE72
0x14004de6e  lea     rcx, [rbp+arg_0]
0x14004de72  bts     [rcx], eax
0x14004de75  mov     r11, [r11]
0x14004de78  cmp     r11, rbx
0x14004de7b  jnz     short loc_14004DE52
0x14004de7d  mov     r12d, [rbp+arg_0]
0x14004de81  mov     r13, [rbp+arg_10]
0x14004de85  jmp     short loc_14004DEA1
0x14004de87  mov     rdx, [rbp+var_30]; unsigned __int64
0x14004de8b  mov     rcx, r14; this
0x14004de8e  mov     r8d, [rsi+94h]; unsigned int
0x14004de95  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x14004de9a  lea     rcx, [rbp+var_38]
0x14004de9e  bts     [rcx], eax
0x14004dea1  mov     r8d, [rbp+arg_18]; unsigned int
0x14004dea5  mov     r9, r15; struct SC_PARITY_CONTEXT *
0x14004dea8  mov     edx, [rbp+var_38]; unsigned int
0x14004deab  mov     rcx, rdi; SpinLock
0x14004deae  mov     byte ptr [rsp+68h+BugCheckOnFailure], 0; unsigned __int8
0x14004deb3  call    ?InitializeContext@SC_PARITY@@QEAAJKKPEAVSC_PARITY_CONTEXT@@E@Z; SC_PARITY::InitializeContext(ulong,ulong,SC_PARITY_CONTEXT *,uchar)
0x14004deb8  mov     ebx, eax
0x14004deba  test    eax, eax
0x14004debc  js      loc_14004DC41
0x14004dec2  or      r12d, [r15+8]
0x14004dec6  mov     [rbp+arg_0], r12d
0x14004deca  mov     r12d, [rsi+0C0h]
0x14004ded1  mov     rcx, r14; this
0x14004ded4  call    ?Resiliency@SIO_RAID@@UEAAPEAVSP_RESILIENCY_INFO@@XZ; SIO_RAID::Resiliency(void)
0x14004ded9  cmp     r12d, [rax+10h]
0x14004dedd  jnb     loc_14004DFC8
0x14004dee3  mov     rdx, [rbp+var_30]; unsigned __int64
0x14004dee7  mov     r8d, r12d; unsigned int
0x14004deea  mov     rcx, r14; this
0x14004deed  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x14004def2  lea     rcx, [rbp+arg_0]
0x14004def6  bt      [rcx], eax
0x14004def9  jnb     loc_14004DFB6
0x14004deff  test    r13, r13
0x14004df02  jnz     short loc_14004DF63
0x14004df04  mov     rdx, [rsi+8]; struct SC_PACKET *
0x14004df08  mov     ecx, 0F8h; unsigned __int64
0x14004df0d  call    ??2SC_PACKET@@SAPEAX_KPEAV0@@Z; SC_PACKET::operator new(unsigned __int64,SC_PACKET *)
0x14004df12  test    rax, rax
0x14004df15  jz      loc_14004DFBE
0x14004df1b  mov     rcx, rax; this
0x14004df1e  call    ??0SC_PACKET@@QEAA@XZ; SC_PACKET::SC_PACKET(void)
0x14004df23  mov     rdi, rax
0x14004df26  test    rax, rax
0x14004df29  jz      loc_14004DFBE
0x14004df2f  mov     r9d, [rsi+90h]
0x14004df36  lea     rcx, [rax+70h]
0x14004df3a  xor     r8d, r8d
0x14004df3d  lea     edx, [r13+3]
0x14004df41  call    ?Initialize@SC_BUFFER@@QEAAJW4_SC_BUFFER_TYPE@@PEAXK@Z; SC_BUFFER::Initialize(_SC_BUFFER_TYPE,void *,ulong)
0x14004df46  mov     ebx, eax
0x14004df48  test    eax, eax
0x14004df4a  jns     short loc_14004DF67
0x14004df4c  mov     rax, [rdi]
0x14004df4f  lea     edx, [r13+1]
0x14004df53  mov     rcx, rdi
0x14004df56  mov     rax, [rax]
0x14004df59  call    _guard_dispatch_icall
0x14004df5e  jmp     loc_14004DC46
0x14004df63  mov     rdi, [r13+0]
0x14004df67  mov     rax, [rsi+88h]
0x14004df6e  xor     r8d, r8d; unsigned __int8
0x14004df71  mov     [rdi+88h], rax
0x14004df78  mov     rdx, rdi; struct SC_PACKET *
0x14004df7b  mov     eax, [rsi+90h]
0x14004df81  mov     rcx, rsi; this
0x14004df84  mov     [rdi+90h], eax
0x14004df8a  mov     eax, [rbp+var_34]
0x14004df8d  mov     [rdi+98h], eax
0x14004df93  mov     [rdi+94h], r12d
0x14004df9a  mov     byte ptr [rdi+0A8h], 3
0x14004dfa1  mov     [rdi+0F0h], r14
0x14004dfa8  call    ?Attach@SC_PACKET@@QEAAXPEAV1@E@Z; SC_PACKET::Attach(SC_PACKET *,uchar)
0x14004dfad  test    r13, r13
0x14004dfb0  jnz     loc_14004DC5C
0x14004dfb6  inc     r12d
0x14004dfb9  jmp     loc_14004DED1
0x14004dfbe  mov     ebx, 0C000009Ah
0x14004dfc3  jmp     loc_14004DC46
0x14004dfc8  test    r13, r13
0x14004dfcb  jnz     loc_14004DC5C
0x14004dfd1  mov     [rsi+0C0h], r15
0x14004dfd8  jmp     loc_14004DC5C
```
