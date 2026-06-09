# SIO_RAID5::BuildChildPacketsGenerateParity(SC_PACKET *,SC_SEQUENTIAL *)

- ea: `0x14004d8e8`
- end: `0x14004db20`
- name: `?BuildChildPacketsGenerateParity@SIO_RAID5@@QEAAJPEAVSC_PACKET@@PEAVSC_SEQUENTIAL@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(SIO_RAID5 *__hidden this, struct SC_PACKET *, struct SC_SEQUENTIAL *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x140009770`

## callees

- `0x1400057f0`
- `0x140005eb0`
- `0x140009f80`
- `0x14000aca0`
- `0x14000b0b0`
- `0x1400154c0`
- `0x140015b60`
- `0x14001b090`
- `0x1400268c0`
- `0x14004d8e8`
- `0x140068000`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004daf7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004daf7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004da2c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004da2c`

## pseudocode

```c
__int64 __fastcall SIO_RAID5::BuildChildPacketsGenerateParity(
        SIO_RAID5 *this,
        struct SC_PACKET *a2,
        struct SC_SEQUENTIAL *a3)
{
  int v5; // ebx
  char v6; // bl
  unsigned __int64 v7; // r13
  int v8; // edi
  struct SP_RESILIENCY_INFO *v9; // rax
  struct SC_PARITY_CONTEXT *v10; // rax
  struct SC_PARITY_CONTEXT *v11; // r15
  unsigned __int64 v12; // r13
  unsigned int i; // ebp
  SC_PACKET *v14; // rax
  SC_PACKET *v15; // rax
  SC_PACKET *v16; // rdi
  unsigned int v17; // eax
  __int64 v18; // r10
  __int64 v19; // r12
  PVOID v20; // rax
  _QWORD *v21; // rcx
  __int64 v22; // rdx

  if ( a3 )
  {
    return (unsigned int)-1073741822;
  }
  else
  {
    v6 = *((_BYTE *)this + 42);
    v7 = *((_QWORD *)a2 + 17);
    v8 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 384LL) + 40LL);
    v9 = SIO_RAID::Resiliency(this);
    v10 = (struct SC_PARITY_CONTEXT *)SC_ENV::Allocate(
                                        (unsigned int)(8 * *((_DWORD *)v9 + 4)) + 24LL,
                                        0x70587053u,
                                        0,
                                        0);
    v11 = v10;
    if ( v10 )
    {
      v12 = v7 >> v6;
      v5 = 0;
      SC_PARITY::InitializeContext(*(SC_PARITY **)(*((_QWORD *)this + 1) + 384LL), (1 << v8) - 1, v10);
      for ( i = 0; i < *((_DWORD *)SIO_RAID::Resiliency(this) + 4); ++i )
      {
        v14 = (SC_PACKET *)SC_PACKET::operator new(0xF8u);
        if ( !v14 || (v15 = SC_PACKET::SC_PACKET(v14), (v16 = v15) == 0) )
        {
          v5 = -1073741670;
          goto LABEL_24;
        }
        if ( i == *((_DWORD *)a2 + 37) )
        {
          SC_PACKET::Reference(v15, a2);
        }
        else
        {
          v5 = SC_BUFFER::Initialize((__int64)v15 + 112, 3, 0, *((_DWORD *)a2 + 36));
          if ( v5 < 0 )
          {
            (**(void (__fastcall ***)(SC_PACKET *, __int64))v16)(v16, 1);
LABEL_24:
            ExFreePoolWithTag(v11, 0);
            return (unsigned int)v5;
          }
        }
        v17 = SIO_RAID5::UnRotate(this, v12, i);
        v18 = *((_QWORD *)v16 + 15);
        v19 = v17;
        if ( (*(_BYTE *)(v18 + 10) & 5) != 0 )
          v20 = *(PVOID *)(v18 + 24);
        else
          v20 = MmMapLockedPagesSpecifyCache((PMDL)v18, 0, MmCached, 0, 0, 0x40000020u);
        *((_QWORD *)v11 + v19 + 2) = v20;
        *((_QWORD *)v16 + 17) = *((_QWORD *)a2 + 17);
        *((_DWORD *)v16 + 36) = *((_DWORD *)a2 + 36);
        *((_DWORD *)v16 + 37) = i;
        *((_BYTE *)v16 + 168) = 3;
        *((_BYTE *)v16 + 170) = 1;
        *((_QWORD *)v16 + 30) = this;
        if ( i == *((_DWORD *)a2 + 37)
          || SIO_RAID5::UnRotate(this, v12, i) >= *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 384LL) + 40LL) )
        {
          v21 = (_QWORD *)((char *)a2 + 96);
          v22 = *((_QWORD *)a2 + 12);
          if ( *(struct SC_PACKET **)(v22 + 8) != (struct SC_PACKET *)((char *)a2 + 96) )
            __fastfail(3u);
          *((_QWORD *)v16 + 25) = v22;
          *((_QWORD *)v16 + 26) = v21;
          *(_QWORD *)(v22 + 8) = (char *)v16 + 200;
          *v21 = (char *)v16 + 200;
        }
        else
        {
          SC_PACKET::Attach(a2, v16, 0);
        }
      }
      *((_QWORD *)a2 + 24) = v11;
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14004d8e8  push    rbx
0x14004d8ea  push    rbp
0x14004d8eb  push    rsi
0x14004d8ec  push    rdi
0x14004d8ed  push    r12
0x14004d8ef  push    r13
0x14004d8f1  push    r14
0x14004d8f3  push    r15
0x14004d8f5  sub     rsp, 38h
0x14004d8f9  mov     rsi, rdx
0x14004d8fc  mov     r14, rcx
0x14004d8ff  test    r8, r8
0x14004d902  jz      short loc_14004D90E
0x14004d904  mov     ebx, 0C0000002h
0x14004d909  jmp     loc_14004DB0C
0x14004d90e  mov     rax, [rcx+8]
0x14004d912  mov     bl, [r14+2Ah]
0x14004d916  mov     r13, [rdx+88h]
0x14004d91d  mov     rcx, [rax+180h]
0x14004d924  mov     edi, [rcx+28h]
0x14004d927  mov     rcx, r14; this
0x14004d92a  call    ?Resiliency@SIO_RAID@@UEAAPEAVSP_RESILIENCY_INFO@@XZ; SIO_RAID::Resiliency(void)
0x14004d92f  xor     r9d, r9d; unsigned int
0x14004d932  xor     r8d, r8d; unsigned __int8
0x14004d935  mov     edx, 70587053h; unsigned int
0x14004d93a  mov     ecx, [rax+10h]
0x14004d93d  shl     ecx, 3
0x14004d940  add     rcx, 18h; unsigned __int64
0x14004d944  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x14004d949  mov     r15, rax
0x14004d94c  test    rax, rax
0x14004d94f  jnz     short loc_14004D95B
0x14004d951  mov     ebx, 0C000009Ah
0x14004d956  jmp     loc_14004DB0C
0x14004d95b  mov     cl, bl
0x14004d95d  mov     r8, r15; struct SC_PARITY_CONTEXT *
0x14004d960  shr     r13, cl
0x14004d963  xor     ebx, ebx
0x14004d965  mov     ecx, edi
0x14004d967  lea     edx, [rbx+1]
0x14004d96a  shl     edx, cl
0x14004d96c  mov     rcx, [r14+8]
0x14004d970  dec     edx; unsigned int
0x14004d972  mov     rcx, [rcx+180h]; this
0x14004d979  call    ?InitializeContext@SC_PARITY@@QEAAXKPEAVSC_PARITY_CONTEXT@@@Z; SC_PARITY::InitializeContext(ulong,SC_PARITY_CONTEXT *)
0x14004d97e  xor     ebp, ebp
0x14004d980  mov     rcx, r14; this
0x14004d983  call    ?Resiliency@SIO_RAID@@UEAAPEAVSP_RESILIENCY_INFO@@XZ; SIO_RAID::Resiliency(void)
0x14004d988  cmp     ebp, [rax+10h]
0x14004d98b  jnb     loc_14004DB05
0x14004d991  mov     ecx, 0F8h; NumberOfBytes
0x14004d996  call    ??2SC_PACKET@@SAPEAX_K@Z; SC_PACKET::operator new(unsigned __int64)
0x14004d99b  test    rax, rax
0x14004d99e  jz      loc_14004DAED
0x14004d9a4  mov     rcx, rax; this
0x14004d9a7  call    ??0SC_PACKET@@QEAA@XZ; SC_PACKET::SC_PACKET(void)
0x14004d9ac  mov     rdi, rax
0x14004d9af  test    rax, rax
0x14004d9b2  jz      loc_14004DAED
0x14004d9b8  cmp     ebp, [rsi+94h]
0x14004d9be  jnz     short loc_14004D9CD
0x14004d9c0  mov     rdx, rsi; struct SC_PACKET *
0x14004d9c3  mov     rcx, rax; this
0x14004d9c6  call    ?Reference@SC_PACKET@@QEAAXPEAV1@@Z; SC_PACKET::Reference(SC_PACKET *)
0x14004d9cb  jmp     short loc_14004D9EE
0x14004d9cd  mov     r9d, [rsi+90h]
0x14004d9d4  lea     rcx, [rax+70h]
0x14004d9d8  xor     r8d, r8d
0x14004d9db  lea     edx, [r8+3]
0x14004d9df  call    ?Initialize@SC_BUFFER@@QEAAJW4_SC_BUFFER_TYPE@@PEAXK@Z; SC_BUFFER::Initialize(_SC_BUFFER_TYPE,void *,ulong)
0x14004d9e4  mov     ebx, eax
0x14004d9e6  test    eax, eax
0x14004d9e8  js      loc_14004DAD8
0x14004d9ee  mov     r8d, ebp; unsigned int
0x14004d9f1  mov     rdx, r13; unsigned __int64
0x14004d9f4  mov     rcx, r14; this
0x14004d9f7  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x14004d9fc  mov     r10, [rdi+78h]
0x14004da00  mov     r12d, eax
0x14004da03  test    byte ptr [r10+0Ah], 5
0x14004da08  jz      short loc_14004DA10
0x14004da0a  mov     rax, [r10+18h]
0x14004da0e  jmp     short loc_14004DA38
0x14004da10  xor     r9d, r9d; RequestedAddress
0x14004da13  mov     [rsp+78h+Priority], 40000020h; Priority
0x14004da1b  xor     edx, edx; AccessMode
0x14004da1d  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14004da25  mov     rcx, r10; MemoryDescriptorList
0x14004da28  lea     r8d, [r9+1]; CacheType
0x14004da2c  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004da33  nop     dword ptr [rax+rax+00h]
0x14004da38  mov     [r15+r12*8+10h], rax
0x14004da3d  mov     rax, [rsi+88h]
0x14004da44  mov     [rdi+88h], rax
0x14004da4b  mov     eax, [rsi+90h]
0x14004da51  mov     [rdi+90h], eax
0x14004da57  mov     [rdi+94h], ebp
0x14004da5d  mov     byte ptr [rdi+0A8h], 3
0x14004da64  mov     byte ptr [rdi+0AAh], 1
0x14004da6b  mov     [rdi+0F0h], r14
0x14004da72  cmp     ebp, [rsi+94h]
0x14004da78  jz      short loc_14004DAA8
0x14004da7a  mov     r8d, ebp; unsigned int
0x14004da7d  mov     rdx, r13; unsigned __int64
0x14004da80  mov     rcx, r14; this
0x14004da83  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x14004da88  mov     rcx, [r14+8]
0x14004da8c  mov     rdx, [rcx+180h]
0x14004da93  cmp     eax, [rdx+28h]
0x14004da96  jnb     short loc_14004DAA8
0x14004da98  xor     r8d, r8d; unsigned __int8
0x14004da9b  mov     rdx, rdi; struct SC_PACKET *
0x14004da9e  mov     rcx, rsi; this
0x14004daa1  call    ?Attach@SC_PACKET@@QEAAXPEAV1@E@Z; SC_PACKET::Attach(SC_PACKET *,uchar)
0x14004daa6  jmp     short loc_14004DACA
0x14004daa8  lea     rcx, [rsi+60h]
0x14004daac  mov     rdx, [rcx]
0x14004daaf  cmp     [rdx+8], rcx
0x14004dab3  jnz     short loc_14004DAD1
0x14004dab5  lea     rax, [rdi+0C8h]
0x14004dabc  mov     [rax], rdx
0x14004dabf  mov     [rax+8], rcx
0x14004dac3  mov     [rdx+8], rax
0x14004dac7  mov     [rcx], rax
0x14004daca  inc     ebp
0x14004dacc  jmp     loc_14004D980
0x14004dad1  mov     ecx, 3
0x14004dad6  int     29h; Win8: RtlFailFast(ecx)
0x14004dad8  mov     rax, [rdi]
0x14004dadb  mov     edx, 1
0x14004dae0  mov     rcx, rdi
0x14004dae3  mov     rax, [rax]
0x14004dae6  call    _guard_dispatch_icall
0x14004daeb  jmp     short loc_14004DAF2
0x14004daed  mov     ebx, 0C000009Ah
0x14004daf2  xor     edx, edx; Tag
0x14004daf4  mov     rcx, r15; P
0x14004daf7  call    cs:__imp_ExFreePoolWithTag
0x14004dafe  nop     dword ptr [rax+rax+00h]
0x14004db03  jmp     short loc_14004DB0C
0x14004db05  mov     [rsi+0C0h], r15
0x14004db0c  mov     eax, ebx
0x14004db0e  add     rsp, 38h
0x14004db12  pop     r15
0x14004db14  pop     r14
0x14004db16  pop     r13
0x14004db18  pop     r12
0x14004db1a  pop     rdi
0x14004db1b  pop     rsi
0x14004db1c  pop     rbp
0x14004db1d  pop     rbx
0x14004db1e  retn
```
