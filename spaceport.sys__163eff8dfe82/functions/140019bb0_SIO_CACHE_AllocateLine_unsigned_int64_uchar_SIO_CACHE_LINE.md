# SIO_CACHE::AllocateLine(unsigned __int64,uchar,SIO_CACHE_LINE * *)

- ea: `0x140019bb0`
- end: `0x14001a119`
- name: `?AllocateLine@SIO_CACHE@@IEAAJ_KEPEAPEAVSIO_CACHE_LINE@@@Z`
- size: `1385`
- prototype: `__int64 __fastcall(SIO_CACHE *__hidden this, unsigned __int64, unsigned __int8, struct SIO_CACHE_LINE **)`
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000dcb0`

## callees

- `0x140019bb0`
- `0x14001a120`
- `0x14001a1a0`
- `0x14001a270`
- `0x14001a330`
- `0x140025800`
- `0x140026130`
- `0x1400264b0`
- `0x140026b40`
- `0x140026db0`
- `0x14002a03c`
- `0x14002b012`
- `0x140045e40`
- `0x140046e9c`
- `0x140068150`
- `0x140068600`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140019ebb`
- `ntoskrnl!ExAllocatePool2` at `0x140019ebb`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140019e83`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140019e83`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140019c8e`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x14001a04c`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140019c8e`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x14001a04c`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x140019c12`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x140019c12`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140019beb`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140019beb`
- `ntoskrnl!RtlFindClearBits` at `0x140019cee`
- `ntoskrnl!RtlFindClearBits` at `0x140019d1d`
- `ntoskrnl!RtlFindClearBits` at `0x140019cee`
- `ntoskrnl!RtlFindClearBits` at `0x140019d1d`
- `ntoskrnl!RtlSetBit` at `0x14001a0a7`
- `ntoskrnl!RtlSetBit` at `0x14001a0a7`

## pseudocode

```c
__int64 __fastcall SIO_CACHE::AllocateLine(SIO_CACHE *this, unsigned __int64 a2, char a3, struct SIO_CACHE_LINE **a4)
{
  unsigned __int64 v6; // r12
  KIRQL v7; // r15
  int v8; // edi
  KIRQL v9; // r13
  __int64 v10; // r9
  unsigned __int64 v11; // rax
  __int64 v12; // r10
  int i; // r8d
  __int64 Pool2; // rsi
  ULONG ParityReservedCount; // r8d
  ULONG v16; // edi
  __int64 v17; // rax
  unsigned __int64 v18; // r13
  ULONG ClearBits; // eax
  ULONG v20; // ebp
  ULONG v21; // eax
  __int64 v22; // r13
  void *Object; // rax
  ULONG v24; // r8d
  unsigned __int64 v25; // r13
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 Child; // rdi
  struct SIO_CACHE_LINE *v29; // rdx
  __int64 v31; // rax
  _QWORD *v32; // rcx
  __int64 v33; // rdx
  _QWORD *v34; // rcx
  __int64 v35; // r9
  int v36; // r10d
  unsigned __int64 v37; // rdx
  bool v38; // zf
  SIO_CACHE_VERIFIER *v39; // rcx
  __int128 v40; // [rsp+20h] [rbp-58h]
  __int128 v41; // [rsp+30h] [rbp-48h]
  __int64 v42; // [rsp+80h] [rbp+8h]

  v6 = a2 - a2 % *((unsigned int *)this + 118);
  v7 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)this + 86);
  if ( *((_QWORD *)this + 61) != -1 && a3 && !*((_BYTE *)this + 512) && !*((_BYTE *)this + 514) )
  {
    *((_BYTE *)this + 514) = 1;
    SIO_CACHE::LogStatus(this, 11);
  }
  v8 = 0;
  v9 = ExAcquireSpinLockShared((PEX_SPIN_LOCK)this + 84);
  v10 = 0;
  v11 = v6 / *((unsigned int *)this + 118);
  if ( v11 < *((_QWORD *)this + 30) )
  {
    v12 = *((_QWORD *)this + 22);
    for ( i = *((_DWORD *)this + 62);
          ;
          v12 = *(_QWORD *)(v12 + 8 * ((unsigned int)(*((_DWORD *)this + 57) - 1) & (v11 >> i)) + 24) )
    {
      i -= *((_DWORD *)this + 58);
      if ( i <= 0 )
        break;
      if ( !v12 )
        goto LABEL_7;
    }
    if ( v12 )
      v10 = *(_QWORD *)(v12 + 8LL * ((unsigned int)v11 & (*((_DWORD *)this + 57) - 1)) + 24);
  }
LABEL_7:
  Pool2 = v10;
  if ( v10 )
  {
    if ( *(_DWORD *)(v10 + 52) == 1 )
    {
      ExReleaseSpinLockShared((PEX_SPIN_LOCK)this + 84, v9);
      goto LABEL_56;
    }
    if ( !SIO_CACHE_STATE::AddRef((SIO_CACHE_STATE *)(v10 + 48), 1u) )
    {
      Pool2 = 0;
      v8 = -1073740693;
      if ( *(_WORD *)(v35 + 66) != *((_WORD *)this + 296) )
        v8 = v36;
    }
  }
  ExReleaseSpinLockShared((PEX_SPIN_LOCK)this + 84, v9);
  if ( v8 < 0 )
    goto LABEL_27;
  if ( Pool2 )
  {
LABEL_50:
    *a4 = (struct SIO_CACHE_LINE *)Pool2;
    goto LABEL_28;
  }
  ParityReservedCount = SIO_CACHE::GetParityReservedCount(this);
  v16 = ParityReservedCount;
  v17 = *((_QWORD *)this + 61);
  if ( *((_DWORD *)this + 138) > ParityReservedCount )
    ParityReservedCount = *((_DWORD *)this + 138);
  *((_DWORD *)this + 138) = ParityReservedCount;
  if ( v17 == -1 || *((_BYTE *)this + 514) )
    LODWORD(v18) = -1;
  else
    v18 = (v17 - *((_QWORD *)this + 58)) / (unsigned __int64)*((unsigned int *)this + 118);
  ClearBits = RtlFindClearBits((PRTL_BITMAP)((char *)this + 520), 1u, ParityReservedCount);
  v20 = ClearBits;
  if ( ClearBits == -1
    || (ClearBits < v16 || ClearBits >= (unsigned int)v18)
    && ((v21 = RtlFindClearBits((PRTL_BITMAP)((char *)this + 520), 1u, v16), v20 = v21, v21 == -1) || v21 < v16)
    || v20 >= (unsigned int)v18 )
  {
    if ( *((_BYTE *)this + 595) )
    {
      if ( *((_BYTE *)this + 609) )
        goto LABEL_34;
      v38 = *((_BYTE *)this + 514) == 0;
      *((_BYTE *)this + 609) = 1;
      if ( !v38 )
        SIO_CACHE::LogStatus(this, 13);
    }
    if ( !*((_BYTE *)this + 609) )
    {
      v8 = -1058602970;
      goto LABEL_28;
    }
LABEL_34:
    v8 = *((_DWORD *)this + 143);
    if ( v8 < 0 )
      goto LABEL_28;
    goto LABEL_50;
  }
  v22 = *((unsigned int *)this + 118);
  v42 = *((_QWORD *)this + 58);
  if ( !*((_DWORD *)this + 28) )
  {
    Pool2 = ExAllocatePool2(64, *((unsigned int *)this + 42), 1482190931);
    if ( Pool2 )
      goto LABEL_23;
LABEL_30:
    v8 = -1073741670;
    goto LABEL_28;
  }
  Object = SC_SLAB_ALLOCATOR::AllocateObject((SIO_CACHE *)((char *)this + 112));
  Pool2 = (__int64)Object;
  if ( !Object )
    goto LABEL_30;
  memset(Object, 0, *((unsigned int *)this + 28));
LABEL_23:
  v24 = *((_DWORD *)this + 120);
  *(_QWORD *)(Pool2 + 32) = v6;
  v25 = v42 + v20 * v22;
  *(_QWORD *)(Pool2 + 40) = v25;
  *(_QWORD *)(Pool2 + 8) = Pool2;
  *(_QWORD *)Pool2 = Pool2;
  *(_QWORD *)(Pool2 + 24) = Pool2 + 16;
  *(_QWORD *)(Pool2 + 16) = Pool2 + 16;
  RtlInitializeBitMap_0((PRTL_BITMAP)(Pool2 + 72), (PULONG)(Pool2 + 88), v24);
  v26 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 80LL))(*((_QWORD *)this + 1));
  LOBYTE(v27) = 11;
  Child = SIO_SPACE::GetChild(v26, v27);
  if ( (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(Child + 392) + 104LL))(
         *(_QWORD *)(Child + 392),
         v25)
    && (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(Child + 392) + 104LL))(
         *(_QWORD *)(Child + 392),
         v25 + *((unsigned int *)this + 118) - 1LL) )
  {
    do
    {
      v41 = *(_OWORD *)(Pool2 + 48);
      if ( (v41 & 1) != 0 )
        break;
      if ( DWORD1(v41) == 10 )
        break;
      v40 = *(_OWORD *)(Pool2 + 48);
      LODWORD(v40) = v41 & 1 | ((v41 & 0xFFFFFFFE) + 2);
    }
    while ( (_QWORD)v41 != _InterlockedCompareExchange64((volatile signed __int64 *)(Pool2 + 48), v40, v41) );
  }
  else
  {
    SIO_CACHE_STATE::UpdateState(Pool2 + 48, 1);
  }
  SIO_CACHE::QueueLineActive(this, (struct SIO_CACHE_LINE *)Pool2);
  SIO_CACHE::QueueLineDirty(this, v29);
  v8 = SIO_CACHE::SetLine(this, (struct SIO_CACHE_LINE *)Pool2, v6, 0);
  if ( v8 >= 0 )
  {
    RtlSetBit((PRTL_BITMAP)((char *)this + 520), v20);
    ++*((_DWORD *)this + 134);
    if ( v25 >= *((_QWORD *)this + 61) )
      ++*((_DWORD *)this + 135);
    v39 = *(SIO_CACHE_VERIFIER **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
    *((_DWORD *)this + 138) = v20;
    if ( v39 )
      SIO_CACHE_VERIFIER::LogMapping(v39, v37, v25);
    if ( *(_DWORD *)(Pool2 + 52) != 1 )
      goto LABEL_50;
LABEL_56:
    v8 = -1058602988;
    goto LABEL_28;
  }
LABEL_27:
  if ( Pool2 )
  {
    v31 = *(_QWORD *)Pool2;
    if ( *(_QWORD *)(*(_QWORD *)Pool2 + 8LL) != Pool2
      || (v32 = *(_QWORD **)(Pool2 + 8), *v32 != Pool2)
      || (*v32 = v31, *(_QWORD *)(v31 + 8) = v32, v33 = *(_QWORD *)(Pool2 + 16), *(_QWORD *)(v33 + 8) != Pool2 + 16)
      || (v34 = *(_QWORD **)(Pool2 + 24), *v34 != Pool2 + 16) )
    {
      __fastfail(3u);
    }
    *v34 = v33;
    *(_QWORD *)(v33 + 8) = v34;
    SIO_CACHE_STATE::DecRef((SIO_CACHE_STATE *)(Pool2 + 48));
    SIO_CACHE::FreeLineObject(this, (struct SIO_CACHE_LINE *)Pool2);
  }
LABEL_28:
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)this + 86, v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140019bb0  mov     [rsp+arg_8], rbx
0x140019bb5  mov     [rsp+arg_18], r9
0x140019bba  push    rbp
0x140019bbb  push    rsi
0x140019bbc  push    rdi
0x140019bbd  push    r12
0x140019bbf  push    r13
0x140019bc1  push    r14
0x140019bc3  push    r15
0x140019bc5  sub     rsp, 40h
0x140019bc9  mov     r12, rdx
0x140019bcc  mov     rbx, rcx
0x140019bcf  mov     ecx, [rcx+1D8h]
0x140019bd5  mov     rax, r12
0x140019bd8  xor     edx, edx
0x140019bda  movzx   edi, r8b
0x140019bde  div     rcx
0x140019be1  lea     rcx, [rbx+158h]; SpinLock
0x140019be8  sub     r12, rdx
0x140019beb  call    cs:__imp_ExAcquireSpinLockExclusive
0x140019bf2  nop     dword ptr [rax+rax+00h]
0x140019bf7  cmp     qword ptr [rbx+1E8h], 0FFFFFFFFFFFFFFFFh
0x140019bff  movzx   r15d, al
0x140019c03  jnz     loc_14001A002
0x140019c09  lea     rcx, [rbx+150h]; SpinLock
0x140019c10  xor     edi, edi
0x140019c12  call    cs:__imp_ExAcquireSpinLockShared
0x140019c19  nop     dword ptr [rax+rax+00h]
0x140019c1e  mov     ecx, [rbx+1D8h]
0x140019c24  xor     edx, edx
0x140019c26  movzx   r13d, al
0x140019c2a  xor     r9d, r9d
0x140019c2d  mov     rax, r12
0x140019c30  div     rcx
0x140019c33  cmp     rax, [rbx+0F0h]
0x140019c3a  jnb     short loc_140019C71
0x140019c3c  mov     r10, [rbx+0B0h]
0x140019c43  mov     esi, [rbx+0E8h]
0x140019c49  mov     r8d, [rbx+0F8h]
0x140019c50  sub     r8d, esi
0x140019c53  test    r8d, r8d
0x140019c56  jg      loc_140019EED
0x140019c5c  test    r10, r10
0x140019c5f  jz      short loc_140019C71
0x140019c61  mov     ecx, [rbx+0E4h]
0x140019c67  dec     ecx
0x140019c69  and     rcx, rax
0x140019c6c  mov     r9, [r10+rcx*8+18h]
0x140019c71  mov     rsi, r9
0x140019c74  mov     r10d, 0C0E70026h
0x140019c7a  test    r9, r9
0x140019c7d  jnz     loc_140019FB2
0x140019c83  movzx   edx, r13b; OldIrql
0x140019c87  lea     rcx, [rbx+150h]; SpinLock
0x140019c8e  call    cs:__imp_ExReleaseSpinLockShared
0x140019c95  nop     dword ptr [rax+rax+00h]
0x140019c9a  test    edi, edi
0x140019c9c  js      loc_140019E6F
0x140019ca2  test    rsi, rsi
0x140019ca5  jnz     loc_140019FF2
0x140019cab  mov     rcx, rbx; this
0x140019cae  call    ?GetParityReservedCount@SIO_CACHE@@QEAAKXZ; SIO_CACHE::GetParityReservedCount(void)
0x140019cb3  mov     ecx, [rbx+228h]
0x140019cb9  mov     r8d, eax
0x140019cbc  cmp     ecx, eax
0x140019cbe  mov     edi, eax
0x140019cc0  mov     rax, [rbx+1E8h]
0x140019cc7  cmova   r8d, ecx; HintIndex
0x140019ccb  mov     [rbx+228h], r8d
0x140019cd2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140019cd6  jnz     loc_14001A062
0x140019cdc  mov     r13d, 0FFFFFFFFh
0x140019ce2  lea     rcx, [rbx+208h]; BitMapHeader
0x140019ce9  mov     edx, 1; NumberToFind
0x140019cee  call    cs:__imp_RtlFindClearBits
0x140019cf5  nop     dword ptr [rax+rax+00h]
0x140019cfa  mov     ebp, eax
0x140019cfc  cmp     eax, 0FFFFFFFFh
0x140019cff  jz      loc_14001A0D1
0x140019d05  cmp     eax, edi
0x140019d07  jb      short loc_140019D0E
0x140019d09  cmp     eax, r13d
0x140019d0c  jb      short loc_140019D3C
0x140019d0e  mov     r8d, edi; HintIndex
0x140019d11  lea     rcx, [rbx+208h]; BitMapHeader
0x140019d18  mov     edx, 1; NumberToFind
0x140019d1d  call    cs:__imp_RtlFindClearBits
0x140019d24  nop     dword ptr [rax+rax+00h]
0x140019d29  mov     ebp, eax
0x140019d2b  cmp     eax, 0FFFFFFFFh
0x140019d2e  jz      loc_14001A0D1
0x140019d34  cmp     eax, edi
0x140019d36  jb      loc_14001A0D1
0x140019d3c  cmp     ebp, r13d
0x140019d3f  jnb     loc_14001A0D1
0x140019d45  cmp     dword ptr [rbx+70h], 0
0x140019d49  mov     rax, [rbx+1D0h]
0x140019d50  mov     r13d, [rbx+1D8h]
0x140019d57  mov     [rsp+78h+arg_0], rax
0x140019d5f  jz      loc_140019EAA
0x140019d65  lea     rcx, [rbx+70h]; this
0x140019d69  call    ?AllocateObject@SC_SLAB_ALLOCATOR@@QEAAPEAXXZ; SC_SLAB_ALLOCATOR::AllocateObject(void)
0x140019d6e  mov     rsi, rax
0x140019d71  test    rax, rax
0x140019d74  jz      loc_140019ED3
0x140019d7a  mov     r8d, [rbx+70h]; Size
0x140019d7e  xor     edx, edx; Val
0x140019d80  mov     rcx, rax; void *
0x140019d83  call    memset
0x140019d88  mov     r8d, [rbx+1E0h]; SizeOfBitMap
0x140019d8f  lea     rdx, [rsi+58h]; BitMapBuffer
0x140019d93  mov     [rsi+20h], r12
0x140019d97  lea     rcx, [rsi+48h]; BitMapHeader
0x140019d9b  mov     eax, ebp
0x140019d9d  imul    r13, rax
0x140019da1  lea     rax, [rsi+10h]
0x140019da5  add     r13, [rsp+78h+arg_0]
0x140019dad  mov     [rsi+28h], r13
0x140019db1  mov     [rsi+8], rsi
0x140019db5  mov     [rsi], rsi
0x140019db8  mov     [rax+8], rax
0x140019dbc  mov     [rax], rax
0x140019dbf  call    RtlInitializeBitMap_0
0x140019dc4  mov     rcx, [rbx+8]
0x140019dc8  mov     rax, [rcx]
0x140019dcb  mov     rax, [rax+50h]
0x140019dcf  call    _guard_dispatch_icall
0x140019dd4  mov     dl, 0Bh
0x140019dd6  mov     rcx, rax
0x140019dd9  call    ?GetChild@SIO_SPACE@@QEAAPEAV1@W4_SC_SPACE_USAGE@@@Z; SIO_SPACE::GetChild(_SC_SPACE_USAGE)
0x140019dde  mov     rdi, rax
0x140019de1  mov     rcx, [rax+188h]
0x140019de8  mov     rdx, [rcx]
0x140019deb  mov     rax, [rdx+68h]
0x140019def  mov     rdx, r13
0x140019df2  call    _guard_dispatch_icall
0x140019df7  test    rax, rax
0x140019dfa  jz      loc_140019EDA
0x140019e00  mov     rcx, [rdi+188h]
0x140019e07  mov     edx, [rbx+1D8h]
0x140019e0d  dec     rdx
0x140019e10  add     rdx, r13
0x140019e13  mov     r8, [rcx]
0x140019e16  mov     rax, [r8+68h]
0x140019e1a  call    _guard_dispatch_icall
0x140019e1f  test    rax, rax
0x140019e22  jz      loc_140019EDA
0x140019e28  movups  xmm0, xmmword ptr [rsi+30h]
0x140019e2c  movq    rdx, xmm0
0x140019e31  movaps  [rsp+78h+var_48], xmm0
0x140019e36  mov     ecx, edx
0x140019e38  and     ecx, 1
0x140019e3b  jz      loc_14001A089
0x140019e41  mov     rdx, rsi; struct SIO_CACHE_LINE *
0x140019e44  mov     rcx, rbx; this
0x140019e47  call    ?QueueLineActive@SIO_CACHE@@IEAAXPEAVSIO_CACHE_LINE@@@Z; SIO_CACHE::QueueLineActive(SIO_CACHE_LINE *)
0x140019e4c  mov     rcx, rbx; this
0x140019e4f  call    ?QueueLineDirty@SIO_CACHE@@IEAAXPEAVSIO_CACHE_LINE@@@Z; SIO_CACHE::QueueLineDirty(SIO_CACHE_LINE *)
0x140019e54  xor     r9d, r9d; unsigned __int8
0x140019e57  mov     r8, r12; unsigned __int64
0x140019e5a  mov     rdx, rsi; struct SIO_CACHE_LINE *
0x140019e5d  mov     rcx, rbx; this
0x140019e60  call    ?SetLine@SIO_CACHE@@IEAAJPEAVSIO_CACHE_LINE@@_KE@Z; SIO_CACHE::SetLine(SIO_CACHE_LINE *,unsigned __int64,uchar)
0x140019e65  mov     edi, eax
0x140019e67  test    eax, eax
0x140019e69  jns     loc_14001A09E
0x140019e6f  test    rsi, rsi
0x140019e72  jnz     loc_140019F63
0x140019e78  movzx   edx, r15b; OldIrql
0x140019e7c  lea     rcx, [rbx+158h]; SpinLock
0x140019e83  call    cs:__imp_ExReleaseSpinLockExclusive
0x140019e8a  nop     dword ptr [rax+rax+00h]
0x140019e8f  mov     rbx, [rsp+78h+arg_8]
0x140019e97  mov     eax, edi
0x140019e99  add     rsp, 40h
0x140019e9d  pop     r15
0x140019e9f  pop     r14
0x140019ea1  pop     r13
0x140019ea3  pop     r12
0x140019ea5  pop     rdi
0x140019ea6  pop     rsi
0x140019ea7  pop     rbp
0x140019ea8  retn
0x140019eaa  mov     edx, [rbx+0A8h]
0x140019eb0  mov     ecx, 40h ; '@'
0x140019eb5  mov     r8d, 58587053h
0x140019ebb  call    cs:__imp_ExAllocatePool2
0x140019ec2  nop     dword ptr [rax+rax+00h]
0x140019ec7  mov     rsi, rax
0x140019eca  test    rax, rax
0x140019ecd  jnz     loc_140019D88
0x140019ed3  mov     edi, 0C000009Ah
0x140019ed8  jmp     short loc_140019E78
0x140019eda  mov     edx, 1
0x140019edf  lea     rcx, [rsi+30h]
0x140019ee3  call    ?UpdateState@SIO_CACHE_STATE@@AEAAXW4SIO_STATE@@@Z; SIO_CACHE_STATE::UpdateState(SIO_STATE)
0x140019ee8  jmp     loc_140019E41
0x140019eed  test    r10, r10
0x140019ef0  jz      loc_140019C71
0x140019ef6  mov     ecx, r8d
0x140019ef9  mov     rdx, rax
0x140019efc  shr     rdx, cl
0x140019eff  mov     ecx, [rbx+0E4h]
0x140019f05  dec     ecx
0x140019f07  and     rdx, rcx
0x140019f0a  mov     r10, [r10+rdx*8+18h]
0x140019f0f  jmp     loc_140019C50
0x140019f14  mov     edi, [rbx+23Ch]
0x140019f1a  test    edi, edi
0x140019f1c  js      loc_140019E78
0x140019f22  jmp     loc_140019FF2
0x140019f27  mov     ecx, 3
0x140019f2c  int     29h; Win8: RtlFailFast(ecx)
0x140019f2e  mov     rax, qword ptr [rsp+78h+var_48]
0x140019f33  and     edx, 0FFFFFFFEh
0x140019f36  movdqa  [rsp+78h+var_58], xmm0
0x140019f3c  add     edx, 2
0x140019f3f  or      edx, ecx
0x140019f41  mov     dword ptr [rsp+78h+var_58], edx
0x140019f45  mov     rcx, qword ptr [rsp+78h+var_58]
0x140019f4a  lock cmpxchg [rsi+30h], rcx
0x140019f50  mov     rcx, qword ptr [rsp+78h+var_48]
0x140019f55  cmp     rcx, rax
0x140019f58  jnz     loc_140019E28
0x140019f5e  jmp     loc_140019E41
0x140019f63  mov     rax, [rsi]
0x140019f66  cmp     [rax+8], rsi
0x140019f6a  jnz     short loc_140019F27
0x140019f6c  mov     rcx, [rsi+8]
0x140019f70  cmp     [rcx], rsi
0x140019f73  jnz     short loc_140019F27
0x140019f75  mov     [rcx], rax
0x140019f78  mov     [rax+8], rcx
0x140019f7c  lea     rax, [rsi+10h]
0x140019f80  mov     rdx, [rax]
0x140019f83  cmp     [rdx+8], rax
0x140019f87  jnz     short loc_140019F27
0x140019f89  mov     rcx, [rax+8]
0x140019f8d  cmp     [rcx], rax
0x140019f90  jnz     short loc_140019F27
0x140019f92  mov     [rcx], rdx
0x140019f95  mov     [rdx+8], rcx
0x140019f99  lea     rcx, [rsi+30h]; this
0x140019f9d  call    ?DecRef@SIO_CACHE_STATE@@QEAAXXZ; SIO_CACHE_STATE::DecRef(void)
0x140019fa2  mov     rdx, rsi; struct SIO_CACHE_LINE *
0x140019fa5  mov     rcx, rbx; this
0x140019fa8  call    ?FreeLineObject@SIO_CACHE@@IEAAXPEAVSIO_CACHE_LINE@@@Z; SIO_CACHE::FreeLineObject(SIO_CACHE_LINE *)
0x140019fad  jmp     loc_140019E78
0x140019fb2  cmp     dword ptr [r9+34h], 1
0x140019fb7  jz      loc_14001A041
0x140019fbd  lea     rcx, [r9+30h]; this
0x140019fc1  mov     dl, 1; unsigned __int8
0x140019fc3  call    ?AddRef@SIO_CACHE_STATE@@QEAAEE@Z; SIO_CACHE_STATE::AddRef(uchar)
0x140019fc8  test    al, al
0x140019fca  jnz     loc_140019C83
0x140019fd0  movzx   eax, word ptr [rbx+250h]
0x140019fd7  xor     esi, esi
0x140019fd9  cmp     [r9+42h], ax
0x140019fde  mov     edi, 0C000046Bh
0x140019fe3  cmovnz  edi, r10d
0x140019fe7  jmp     loc_140019C83
0x140019fec  cmp     dword ptr [rsi+34h], 1
0x140019ff0  jz      short loc_14001A058
0x140019ff2  mov     rax, [rsp+78h+arg_18]
0x140019ffa  mov     [rax], rsi
0x140019ffd  jmp     loc_140019E78
0x14001a002  test    dil, dil
0x14001a005  jz      loc_140019C09
0x14001a00b  cmp     byte ptr [rbx+200h], 0
0x14001a012  jnz     loc_140019C09
0x14001a018  cmp     byte ptr [rbx+202h], 0
0x14001a01f  jnz     loc_140019C09
0x14001a025  xor     r8d, r8d
0x14001a028  mov     byte ptr [rbx+202h], 1
0x14001a02f  mov     edx, 0Bh
0x14001a034  mov     rcx, rbx
0x14001a037  call    ?LogStatus@SIO_CACHE@@IEAAXW4SIO_CACHE_OPERATION@@J@Z; SIO_CACHE::LogStatus(SIO_CACHE_OPERATION,long)
0x14001a03c  jmp     loc_140019C09
0x14001a041  movzx   edx, r13b; OldIrql
0x14001a045  lea     rcx, [rbx+150h]; SpinLock
0x14001a04c  call    cs:__imp_ExReleaseSpinLockShared
0x14001a053  nop     dword ptr [rax+rax+00h]
0x14001a058  mov     edi, 0C0E70014h
0x14001a05d  jmp     loc_140019E78
0x14001a062  cmp     byte ptr [rbx+202h], 0
0x14001a069  jnz     loc_140019CDC
0x14001a06f  sub     rax, [rbx+1D0h]
0x14001a076  xor     edx, edx
0x14001a078  mov     ecx, [rbx+1D8h]
0x14001a07e  div     rcx
0x14001a081  mov     r13, rax
0x14001a084  jmp     loc_140019CE2
0x14001a089  mov     rax, rdx
0x14001a08c  shr     rax, 20h
0x14001a090  cmp     eax, 0Ah
0x14001a093  jz      loc_140019E41
0x14001a099  jmp     loc_140019F2E
0x14001a09e  mov     edx, ebp; BitNumber
0x14001a0a0  lea     rcx, [rbx+208h]; BitMapHeader
0x14001a0a7  call    cs:__imp_RtlSetBit
  ... truncated ...
```
