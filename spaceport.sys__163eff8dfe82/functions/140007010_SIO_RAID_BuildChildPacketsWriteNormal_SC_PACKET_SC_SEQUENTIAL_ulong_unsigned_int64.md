# SIO_RAID::BuildChildPacketsWriteNormal(SC_PACKET *,SC_SEQUENTIAL *,ulong,unsigned __int64)

- ea: `0x140007010`
- end: `0x1400073b4`
- name: `?BuildChildPacketsWriteNormal@SIO_RAID@@AEAAJPEAVSC_PACKET@@PEAVSC_SEQUENTIAL@@K_K@Z`
- size: `932`
- prototype: `__int64 __usercall@<rax>(SIO_RAID *__hidden this@<rcx>, struct SC_PACKET *@<rdx>, struct SC_SEQUENTIAL *@<r8>, unsigned int@<r9d>, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x140006c30`

## callees

- `0x1400057f0`
- `0x140007010`
- `0x140007fa0`
- `0x14000b170`
- `0x140012d50`
- `0x14001a410`
- `0x14004a0e8`
- `0x140068150`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x1400071b2`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400071b2`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x14000720c`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x14000720c`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400070c0`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400070c0`
- `ntoskrnl!MmUnmapReservedMapping` at `0x14000723d`
- `ntoskrnl!MmUnmapReservedMapping` at `0x14000723d`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000727e`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000727e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140007123`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400071e6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140007123`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400071e6`

## pseudocode

```c
__int64 __fastcall SIO_RAID::BuildChildPacketsWriteNormal(
        SIO_RAID *this,
        struct SC_PACKET *a2,
        struct SC_SEQUENTIAL *a3,
        ULONG a4,
        unsigned __int64 a5)
{
  __int64 v5; // rax
  int v7; // r15d
  __int64 v11; // rax
  unsigned int v12; // r15d
  SIO_LOG_PACKET *v13; // rax
  PMDL v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  int v17; // edi
  struct _MDL *MappedSystemVa; // rax
  char *v20; // r13
  __int64 v21; // rcx
  PVOID v22; // rax
  __int64 v23; // rcx
  int v24; // eax
  ULONG v25; // eax
  char v26; // al
  bool v27; // zf
  struct SC_PACKET **v28; // rdx
  struct _EPROCESS *Process; // rcx
  size_t BugCheckOnFailure; // [rsp+20h] [rbp-58h]
  int v32; // [rsp+80h] [rbp+8h] BYREF

  v5 = *(_QWORD *)this;
  v7 = a5;
  v32 = 0;
  v11 = (*(__int64 (__fastcall **)(SIO_RAID *, unsigned __int64, int *))(v5 + 128))(this, a5, &v32);
  v12 = v7 - *((_DWORD *)a2 + 34);
  a5 = v11;
  if ( a3 )
  {
    v17 = 0;
    v14 = *(PMDL *)a3;
    if ( a4 == *((_DWORD *)a2 + 36) )
      HIDWORD(v14[1].MappedSystemVa) |= *((_DWORD *)a2 + 19) & 4;
    v20 = (char *)a3 + 8;
    IoBuildPartialMdl(
      *((PMDL *)a2 + 15),
      *((PMDL *)a3 + 2),
      (PVOID)(v12 + *(_QWORD *)(*((_QWORD *)a2 + 15) + 32LL) + *(unsigned int *)(*((_QWORD *)a2 + 15) + 44LL)),
      a4);
    v21 = *((_QWORD *)a3 + 2);
    if ( (*(_BYTE *)(v21 + 10) & 5) != 0 )
      v22 = *(PVOID *)(v21 + 24);
    else
      v22 = MmMapLockedPagesSpecifyCache((PMDL)v21, 0, MmCached, 0, 0, 0x40000020u);
    if ( v22 )
    {
      LODWORD(BugCheckOnFailure) = a4;
      SC_BUFFER::Copy((SC_BUFFER *)&v14[2].Process, (struct SC_SEQUENTIAL *)((char *)a3 + 8), 0, 0, BugCheckOnFailure);
    }
    else
    {
      MmMapLockedPagesWithReservedMapping(*((PVOID *)a3 + 3), 0x704D7053u, *((PMDL *)a3 + 2), MmCached);
      LODWORD(BugCheckOnFailure) = a4;
      SC_BUFFER::Copy((SC_BUFFER *)&v14[2].Process, (struct SC_SEQUENTIAL *)((char *)a3 + 8), 0, 0, BugCheckOnFailure);
      MmUnmapReservedMapping(*((PVOID *)a3 + 3), 0x704D7053u, *((PMDL *)a3 + 2));
      v20 = (char *)a3 + 8;
    }
    if ( *(_DWORD *)v20 == 2 )
    {
      v23 = *((_QWORD *)v20 + 1);
      if ( (*(_BYTE *)(v23 + 10) & 0x20) != 0 )
        MmUnmapLockedPages(*(PVOID *)(v23 + 24), *((PMDL *)v20 + 1));
    }
    v24 = *((_DWORD *)a2 + 41);
    if ( v24 != -1 )
      HIDWORD(v14[3].Process) = v12 + v24;
  }
  else
  {
    v13 = (SIO_LOG_PACKET *)SC_PACKET::operator new(0x118u);
    if ( !v13 || (v14 = (PMDL)SIO_LOG_PACKET::SIO_LOG_PACKET(v13)) == 0 )
      return (unsigned int)-1073741670;
    if ( (*((_BYTE *)this + 43) > 1u
       || ((v15 = *((_QWORD *)this + 4)) == 0 ? (v16 = *((_QWORD *)this + 1) + 80LL) : (v16 = v15 + 88),
           *(_DWORD *)(v16 + 4)))
      && (unsigned int)MmMdlPageContentsState(*((_QWORD *)a2 + 15), 2) != 1 )
    {
      v17 = SC_PACKET::Copy((SC_PACKET *)v14, a2, v12, a4);
      if ( v17 < 0 )
        goto LABEL_18;
    }
    else
    {
      v17 = SC_PACKET::Split((SC_PACKET *)v14, a2, v12, a4, 0);
      if ( v17 < 0 )
      {
LABEL_18:
        ((void (__fastcall *)(PMDL, __int64))v14->Next->Next)(v14, 1);
        return (unsigned int)v17;
      }
      if ( (*((_BYTE *)this + 40) & 4) != 0 )
      {
        MappedSystemVa = (struct _MDL *)v14[2].MappedSystemVa;
        if ( !((MappedSystemVa->MdlFlags & 5) != 0
             ? MappedSystemVa->MappedSystemVa
             : MmMapLockedPagesSpecifyCache(MappedSystemVa, 0, MmCached, 0, 0, 0x40000020u)) )
        {
          v17 = -1073741670;
          goto LABEL_18;
        }
      }
    }
  }
  *(_QWORD *)&v14[2].ByteCount = a5;
  v25 = a4;
  if ( a4 > (unsigned int)(1LL << *((_BYTE *)this + 42)) )
    v25 = 1LL << *((_BYTE *)this + 42);
  LODWORD(v14[3].Next) = v25;
  HIDWORD(v14[3].Next) = v32;
  *(_DWORD *)(&v14[3].MdlFlags + 1) = *((_DWORD *)a2 + 39);
  v26 = 1;
  LOBYTE(v14[3].MappedSystemVa) = 4;
  v27 = (*((_DWORD *)a2 + 19) & 0x10000000) == 0;
  v14[5].Next = (struct _MDL *)this;
  if ( v27 )
    v26 = 4;
  HIDWORD(v14[5].MappedSystemVa) = a4;
  BYTE2(v14[3].MappedSystemVa) = v26;
  HIDWORD(v14[5].StartVa) = 1;
  *(_QWORD *)&v14->Size = *((_QWORD *)a2 + 1);
  v14->Process = a2;
  v28 = (struct SC_PACKET **)*((_QWORD *)a2 + 6);
  if ( *v28 != (struct SC_PACKET *)((char *)a2 + 40) )
    __fastfail(3u);
  *(_QWORD *)&v14[1].Size = (char *)a2 + 40;
  v14[1].Process = (struct _EPROCESS *)v28;
  *v28 = (struct SC_PACKET *)&v14[1].Size;
  *((_QWORD *)a2 + 6) = (char *)v14 + 56;
  ++*((_DWORD *)a2 + 18);
  if ( BYTE2(v14[3].MappedSystemVa) == 4 )
  {
    if ( (*((_BYTE *)this + 40) & 2) != 0 && v14[4].MappedSystemVa == &v14[4].MappedSystemVa )
    {
      Process = v14->Process;
      if ( Process )
      {
        while ( *((struct _EPROCESS **)Process + 27) == (struct _EPROCESS *)((char *)Process + 216) )
        {
          Process = (struct _EPROCESS *)*((_QWORD *)Process + 2);
          if ( !Process )
            goto LABEL_45;
        }
      }
      else
      {
LABEL_45:
        if ( SIO_RAID::AddPacketToRegionBucket(this, (struct SC_PACKET *)v14, 0) )
          return (unsigned int)v17;
      }
    }
    BYTE2(v14[3].MappedSystemVa) = 1;
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x140007010  mov     r11, rsp
0x140007013  push    rbx
0x140007014  push    rbp
0x140007015  push    rsi
0x140007016  push    rdi
0x140007017  push    r12
0x140007019  push    r13
0x14000701b  push    r14
0x14000701d  push    r15
0x14000701f  sub     rsp, 38h
0x140007023  mov     rax, [rcx]
0x140007026  mov     r12, r8
0x140007029  mov     r15, [rsp+78h+arg_20]
0x140007031  lea     r8, [r11+8]
0x140007035  mov     rsi, rdx
0x140007038  xor     r13d, r13d
0x14000703b  mov     rdx, r15
0x14000703e  mov     [r11+8], r13d
0x140007042  mov     rax, [rax+80h]
0x140007049  mov     ebp, r9d
0x14000704c  mov     r14, rcx
0x14000704f  call    _guard_dispatch_icall
0x140007054  sub     r15d, [rsi+88h]
0x14000705b  mov     [rsp+78h+arg_20], rax
0x140007063  test    r12, r12
0x140007066  jnz     loc_14000717C
0x14000706c  mov     ecx, 118h; NumberOfBytes
0x140007071  call    ??2SC_PACKET@@SAPEAX_K@Z; SC_PACKET::operator new(unsigned __int64)
0x140007076  test    rax, rax
0x140007079  jz      loc_140007172
0x14000707f  mov     rcx, rax; this
0x140007082  call    ??0SIO_LOG_PACKET@@QEAA@XZ; SIO_LOG_PACKET::SIO_LOG_PACKET(void)
0x140007087  mov     rbx, rax
0x14000708a  test    rax, rax
0x14000708d  jz      loc_140007172
0x140007093  cmp     byte ptr [r14+2Bh], 1
0x140007098  ja      short loc_1400070B7
0x14000709a  mov     rax, [r14+20h]
0x14000709e  test    rax, rax
0x1400070a1  jz      short loc_1400070A9
0x1400070a3  add     rax, 58h ; 'X'
0x1400070a7  jmp     short loc_1400070B1
0x1400070a9  mov     rax, [r14+8]
0x1400070ad  add     rax, 50h ; 'P'
0x1400070b1  cmp     [rax+4], r13d
0x1400070b5  jbe     short loc_1400070D1
0x1400070b7  mov     rcx, [rsi+78h]
0x1400070bb  mov     edx, 2
0x1400070c0  call    cs:__imp_MmMdlPageContentsState
0x1400070c7  nop     dword ptr [rax+rax+00h]
0x1400070cc  cmp     eax, 1
0x1400070cf  jnz     short loc_14000713F
0x1400070d1  mov     r9d, ebp; unsigned int
0x1400070d4  mov     byte ptr [rsp+78h+BugCheckOnFailure], r13b; unsigned __int8
0x1400070d9  mov     r8d, r15d; unsigned int
0x1400070dc  mov     rdx, rsi; struct SC_PACKET *
0x1400070df  mov     rcx, rbx; this
0x1400070e2  call    ?Split@SC_PACKET@@QEAAJPEAV1@KKE@Z; SC_PACKET::Split(SC_PACKET *,ulong,ulong,uchar)
0x1400070e7  mov     edi, eax
0x1400070e9  test    eax, eax
0x1400070eb  js      short loc_14000715A
0x1400070ed  test    byte ptr [r14+28h], 4
0x1400070f2  jz      loc_14000729E
0x1400070f8  mov     rax, [rbx+78h]
0x1400070fc  test    byte ptr [rax+0Ah], 5
0x140007100  jz      short loc_140007108
0x140007102  mov     rax, [rax+18h]
0x140007106  jmp     short loc_14000712F
0x140007108  mov     [rsp+78h+Priority], 40000020h; Priority
0x140007110  xor     r9d, r9d; RequestedAddress
0x140007113  xor     edx, edx; AccessMode
0x140007115  mov     dword ptr [rsp+78h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x14000711a  mov     r8d, 1; CacheType
0x140007120  mov     rcx, rax; MemoryDescriptorList
0x140007123  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000712a  nop     dword ptr [rax+rax+00h]
0x14000712f  test    rax, rax
0x140007132  jnz     loc_14000729E
0x140007138  mov     edi, 0C000009Ah
0x14000713d  jmp     short loc_14000715A
0x14000713f  mov     r9d, ebp; unsigned int
0x140007142  mov     r8d, r15d; unsigned int
0x140007145  mov     rdx, rsi; struct SC_PACKET *
0x140007148  mov     rcx, rbx; this
0x14000714b  call    ?Copy@SC_PACKET@@QEAAJPEAV1@KK@Z; SC_PACKET::Copy(SC_PACKET *,ulong,ulong)
0x140007150  mov     edi, eax
0x140007152  test    eax, eax
0x140007154  jns     loc_14000729E
0x14000715a  mov     rax, [rbx]
0x14000715d  mov     edx, 1
0x140007162  mov     rcx, rbx
0x140007165  mov     rax, [rax]
0x140007168  call    _guard_dispatch_icall
0x14000716d  jmp     loc_1400073A0
0x140007172  mov     edi, 0C000009Ah
0x140007177  jmp     loc_1400073A0
0x14000717c  mov     edi, r13d
0x14000717f  mov     rbx, [r12]
0x140007183  cmp     ebp, [rsi+90h]
0x140007189  jnz     short loc_140007194
0x14000718b  mov     eax, [rsi+4Ch]
0x14000718e  and     eax, 4
0x140007191  or      [rbx+4Ch], eax
0x140007194  mov     rcx, [rsi+78h]; SourceMdl
0x140007198  lea     r13, [r12+8]
0x14000719d  mov     rdx, [r13+8]; TargetMdl
0x1400071a1  mov     r9d, ebp; Length
0x1400071a4  mov     eax, r15d
0x1400071a7  mov     r8d, [rcx+2Ch]
0x1400071ab  add     r8, [rcx+20h]
0x1400071af  add     r8, rax; VirtualAddress
0x1400071b2  call    cs:__imp_IoBuildPartialMdl
0x1400071b9  nop     dword ptr [rax+rax+00h]
0x1400071be  mov     rcx, [r12+10h]; MemoryDescriptorList
0x1400071c3  test    byte ptr [rcx+0Ah], 5
0x1400071c7  jz      short loc_1400071CF
0x1400071c9  mov     rax, [rcx+18h]
0x1400071cd  jmp     short loc_1400071F2
0x1400071cf  mov     [rsp+78h+Priority], 40000020h; Priority
0x1400071d7  xor     r9d, r9d; RequestedAddress
0x1400071da  xor     edx, edx; AccessMode
0x1400071dc  mov     dword ptr [rsp+78h+BugCheckOnFailure], edi; BugCheckOnFailure
0x1400071e0  mov     r8d, 1; CacheType
0x1400071e6  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400071ed  nop     dword ptr [rax+rax+00h]
0x1400071f2  test    rax, rax
0x1400071f5  jnz     short loc_140007250
0x1400071f7  mov     r8, [r12+10h]; MemoryDescriptorList
0x1400071fc  mov     r9d, 1; CacheType
0x140007202  mov     rcx, [r12+18h]; MappingAddress
0x140007207  mov     edx, 704D7053h; PoolTag
0x14000720c  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x140007213  nop     dword ptr [rax+rax+00h]
0x140007218  lea     rcx, [rbx+70h]; this
0x14000721c  mov     dword ptr [rsp+78h+BugCheckOnFailure], ebp; Size
0x140007220  xor     r9d, r9d; unsigned int
0x140007223  xor     r8d, r8d; unsigned int
0x140007226  mov     rdx, r13; struct SC_BUFFER *
0x140007229  call    ?Copy@SC_BUFFER@@QEAAJPEAV1@KKK@Z; SC_BUFFER::Copy(SC_BUFFER *,ulong,ulong,ulong)
0x14000722e  mov     r8, [r12+10h]; MemoryDescriptorList
0x140007233  mov     edx, 704D7053h; PoolTag
0x140007238  mov     rcx, [r12+18h]; BaseAddress
0x14000723d  call    cs:__imp_MmUnmapReservedMapping
0x140007244  nop     dword ptr [rax+rax+00h]
0x140007249  lea     r13, [r12+8]
0x14000724e  jmp     short loc_140007266
0x140007250  lea     rcx, [rbx+70h]; this
0x140007254  mov     dword ptr [rsp+78h+BugCheckOnFailure], ebp; Size
0x140007258  xor     r9d, r9d; unsigned int
0x14000725b  xor     r8d, r8d; unsigned int
0x14000725e  mov     rdx, r13; struct SC_BUFFER *
0x140007261  call    ?Copy@SC_BUFFER@@QEAAJPEAV1@KKK@Z; SC_BUFFER::Copy(SC_BUFFER *,ulong,ulong,ulong)
0x140007266  cmp     dword ptr [r13+0], 2
0x14000726b  jnz     short loc_14000728A
0x14000726d  mov     rcx, [r13+8]
0x140007271  test    byte ptr [rcx+0Ah], 20h
0x140007275  jz      short loc_14000728A
0x140007277  mov     rdx, rcx; MemoryDescriptorList
0x14000727a  mov     rcx, [rcx+18h]; BaseAddress
0x14000727e  call    cs:__imp_MmUnmapLockedPages
0x140007285  nop     dword ptr [rax+rax+00h]
0x14000728a  mov     eax, [rsi+0A4h]
0x140007290  cmp     eax, 0FFFFFFFFh
0x140007293  jz      short loc_14000729E
0x140007295  add     eax, r15d
0x140007298  mov     [rbx+0A4h], eax
0x14000729e  mov     rax, [rsp+78h+arg_20]
0x1400072a6  mov     edx, 1
0x1400072ab  mov     [rbx+88h], rax
0x1400072b2  mov     eax, ebp
0x1400072b4  movzx   ecx, byte ptr [r14+2Ah]
0x1400072b9  shl     rdx, cl
0x1400072bc  mov     ecx, 4
0x1400072c1  cmp     ebp, edx
0x1400072c3  cmova   eax, edx
0x1400072c6  mov     [rbx+90h], eax
0x1400072cc  mov     eax, [rsp+78h+arg_0]
0x1400072d3  mov     [rbx+94h], eax
0x1400072d9  mov     eax, [rsi+9Ch]
0x1400072df  mov     [rbx+9Ch], eax
0x1400072e5  mov     eax, 1
0x1400072ea  mov     byte ptr [rbx+0A8h], 4
0x1400072f1  test    dword ptr [rsi+4Ch], 10000000h
0x1400072f8  mov     [rbx+0F0h], r14
0x1400072ff  cmovz   eax, ecx
0x140007302  mov     [rbx+10Ch], ebp
0x140007308  mov     [rbx+0AAh], al
0x14000730e  lea     rcx, [rsi+28h]
0x140007312  mov     dword ptr [rbx+114h], 1
0x14000731c  mov     rax, [rsi+8]
0x140007320  mov     [rbx+8], rax
0x140007324  mov     [rbx+10h], rsi
0x140007328  mov     rdx, [rcx+8]
0x14000732c  cmp     [rdx], rcx
0x14000732f  jz      short loc_140007338
0x140007331  mov     ecx, 3
0x140007336  int     29h; Win8: RtlFailFast(ecx)
0x140007338  lea     rax, [rbx+38h]
0x14000733c  mov     [rax], rcx
0x14000733f  mov     [rax+8], rdx
0x140007343  mov     [rdx], rax
0x140007346  mov     [rcx+8], rax
0x14000734a  inc     dword ptr [rsi+48h]
0x14000734d  cmp     byte ptr [rbx+0AAh], 4
0x140007354  jnz     short loc_1400073A0
0x140007356  test    byte ptr [r14+28h], 2
0x14000735b  jz      short loc_140007399
0x14000735d  lea     rax, [rbx+0D8h]
0x140007364  cmp     [rax], rax
0x140007367  jnz     short loc_140007399
0x140007369  mov     rcx, [rbx+10h]
0x14000736d  test    rcx, rcx
0x140007370  jz      short loc_140007387
0x140007372  lea     rax, [rcx+0D8h]
0x140007379  cmp     [rax], rax
0x14000737c  jnz     short loc_140007399
0x14000737e  mov     rcx, [rcx+10h]
0x140007382  test    rcx, rcx
0x140007385  jnz     short loc_140007372
0x140007387  xor     r8d, r8d; unsigned __int8
0x14000738a  mov     rdx, rbx; struct SC_PACKET *
0x14000738d  mov     rcx, r14; this
0x140007390  call    ?AddPacketToRegionBucket@SIO_RAID@@QEAAEPEAVSC_PACKET@@E@Z; SIO_RAID::AddPacketToRegionBucket(SC_PACKET *,uchar)
0x140007395  test    al, al
0x140007397  jnz     short loc_1400073A0
0x140007399  mov     byte ptr [rbx+0AAh], 1
0x1400073a0  mov     eax, edi
0x1400073a2  add     rsp, 38h
0x1400073a6  pop     r15
0x1400073a8  pop     r14
0x1400073aa  pop     r13
0x1400073ac  pop     r12
0x1400073ae  pop     rdi
0x1400073af  pop     rsi
0x1400073b0  pop     rbp
0x1400073b1  pop     rbx
0x1400073b2  retn
```
