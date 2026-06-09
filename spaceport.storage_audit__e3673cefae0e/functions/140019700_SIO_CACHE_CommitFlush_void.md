# SIO_CACHE::CommitFlush(void)

- ea: `0x140019700`
- end: `0x140019944`
- name: `?CommitFlush@SIO_CACHE@@IEAAXXZ`
- size: `580`
- prototype: `void __fastcall(SIO_CACHE *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x14001dd60`

## callees

- `0x140019700`
- `0x14001a250`
- `0x14001a270`
- `0x140025df0`
- `0x140026db0`
- `0x140029ee4`
- `0x1400458e0`
- `0x140046710`
- `0x140046ddc`
- `0x140046e5c`
- `0x140046fd0`
- `0x140068000`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140019908`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140019908`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140019746`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140019746`
- `ntoskrnl!RtlNumberOfSetBits` at `0x14001983e`
- `ntoskrnl!RtlNumberOfSetBits` at `0x14001983e`

## pseudocode

```c
void __fastcall SIO_CACHE::CommitFlush(SIO_CACHE *this)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int64 Child; // r13
  KIRQL v5; // r12
  _BYTE *v6; // rcx
  _QWORD *i; // rsi
  _BYTE *v8; // rbx
  struct SIO_CACHE_LINE *Line; // rdi
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rdx
  __int64 v13; // rax

  v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 80LL))(*((_QWORD *)this + 1));
  LOBYTE(v3) = 11;
  Child = SIO_SPACE::GetChild(v2, v3);
  v5 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)this + 86);
  v6 = (_BYTE *)*((_QWORD *)this + 54);
  for ( i = *(_QWORD **)v6; v6 != (char *)this + 432; i = (_QWORD *)*i )
  {
    v8 = v6 - 16;
    if ( (v6[48] & 4) != 0 )
    {
      if ( *((_DWORD *)v8 + 13) == 3 )
      {
        SIO_CACHE_STATE::MarkCommitted((SIO_CACHE_STATE *)(v8 + 48));
        SIO_CACHE::QueueLine(this, (struct SIO_CACHE_LINE *)v8);
      }
      if ( *((_DWORD *)v8 + 13) == 10 )
      {
        Line = SIO_CACHE::GetLine(this, *((_QWORD *)v8 + 4), 0);
        SIO_CACHE::FreeLine(this, (struct SIO_CACHE_LINE *)v8);
        SIO_CACHE_STATE::MarkUnlocked((struct SIO_CACHE_LINE *)((char *)Line + 48));
      }
    }
    else
    {
      if ( *((_DWORD *)v8 + 13) == 3 )
      {
        SIO_CACHE_STATE::MarkCommitted((SIO_CACHE_STATE *)(v8 + 48));
        SIO_CACHE::QueueLine(this, (struct SIO_CACHE_LINE *)v8);
        if ( *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels )
          SIO_CACHE_VERIFIER::LogMapping(
            *(SIO_CACHE_VERIFIER **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels,
            v10,
            *((unsigned int *)v8 + 13));
      }
      if ( *((_DWORD *)v8 + 13) == 7 )
      {
        SIO_CACHE_STATE::MarkDestaging((SIO_CACHE_STATE *)(v8 + 48), 0);
        SIO_CACHE::QueueLineDirty(this, (struct SIO_CACHE_LINE *)v8);
        if ( *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels )
          SIO_CACHE_VERIFIER::LogMapping(
            *(SIO_CACHE_VERIFIER **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels,
            v11,
            *((unsigned int *)v8 + 13));
      }
      if ( *((_DWORD *)v8 + 13) == 10 )
      {
        _InterlockedAdd64(
          (volatile signed __int64 *)(*((_QWORD *)this + 80) + 104LL),
          -(*((_DWORD *)this + 26) * RtlNumberOfSetBits((PRTL_BITMAP)(v8 + 72))));
        if ( *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels )
          SIO_CACHE_VERIFIER::LogMapping(
            *(SIO_CACHE_VERIFIER **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels,
            v12,
            0xFFFFFFFFFFFFFFFFuLL);
        SIO_CACHE::FreeLine(this, (struct SIO_CACHE_LINE *)v8);
      }
    }
    v6 = i;
  }
  v13 = *((_QWORD *)this + 61);
  if ( v13 != -1 && !*((_DWORD *)this + 135) && !*((_BYTE *)this + 512) && !*((_BYTE *)this + 513) )
  {
    *((_BYTE *)this + 514) = 0;
    if ( *(_DWORD *)(Child + 48) == 1
      && *(_QWORD *)(Child + 120)
       + v13
       - 1
       - (unsigned __int64)(*(_QWORD *)(Child + 120) + v13 - 1) % *(_QWORD *)(Child + 120) < *(_QWORD *)(Child + 112) )
    {
      *((_BYTE *)this + 512) = 1;
    }
  }
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)this + 86, v5);
  if ( *((_DWORD *)this + 153) == 4 && !*((_DWORD *)this + 154) )
    SIO_CACHE::ClearDirtyState(this);
}

```

## disassembly

```asm
0x140019700  push    rbp
0x140019702  sub     rsp, 40h
0x140019706  mov     [rsp+48h+arg_8], rsi
0x14001970b  mov     rbp, rcx
0x14001970e  mov     rcx, [rcx+8]
0x140019712  mov     [rsp+48h+var_10], r12
0x140019717  mov     [rsp+48h+var_18], r13
0x14001971c  mov     [rsp+48h+var_20], r14
0x140019721  mov     rax, [rcx]
0x140019724  mov     [rsp+48h+var_28], r15
0x140019729  mov     rax, [rax+50h]
0x14001972d  call    _guard_dispatch_icall
0x140019732  mov     dl, 0Bh
0x140019734  mov     rcx, rax
0x140019737  call    ?GetChild@SIO_SPACE@@QEAAPEAV1@W4_SC_SPACE_USAGE@@@Z; SIO_SPACE::GetChild(_SC_SPACE_USAGE)
0x14001973c  lea     rcx, [rbp+158h]; SpinLock
0x140019743  mov     r13, rax
0x140019746  call    cs:__imp_ExAcquireSpinLockExclusive
0x14001974d  nop     dword ptr [rax+rax+00h]
0x140019752  lea     r14, [rbp+1B0h]
0x140019759  movzx   r12d, al
0x14001975d  mov     rcx, [r14]
0x140019760  mov     rsi, [rcx]
0x140019763  cmp     rcx, r14
0x140019766  jz      loc_14001989A
0x14001976c  mov     [rsp+48h+arg_0], rbx
0x140019771  mov     [rsp+48h+arg_10], rdi
0x140019776  test    byte ptr [rcx+30h], 4
0x14001977a  lea     rbx, [rcx-10h]
0x14001977e  jz      short loc_1400197CF
0x140019780  cmp     dword ptr [rbx+34h], 3
0x140019784  jnz     short loc_14001979A
0x140019786  lea     rcx, [rbx+30h]; this
0x14001978a  call    ?MarkCommitted@SIO_CACHE_STATE@@QEAAEXZ; SIO_CACHE_STATE::MarkCommitted(void)
0x14001978f  mov     rdx, rbx; struct SIO_CACHE_LINE *
0x140019792  mov     rcx, rbp; this
0x140019795  call    ?QueueLine@SIO_CACHE@@IEAAXPEAVSIO_CACHE_LINE@@@Z; SIO_CACHE::QueueLine(SIO_CACHE_LINE *)
0x14001979a  cmp     dword ptr [rbx+34h], 0Ah
0x14001979e  jnz     loc_140019881
0x1400197a4  mov     rdx, [rbx+20h]; unsigned __int64
0x1400197a8  xor     r8d, r8d; unsigned __int8
0x1400197ab  mov     rcx, rbp; this
0x1400197ae  call    ?GetLine@SIO_CACHE@@IEAAPEAVSIO_CACHE_LINE@@_KE@Z; SIO_CACHE::GetLine(unsigned __int64,uchar)
0x1400197b3  mov     rdx, rbx; struct SIO_CACHE_LINE *
0x1400197b6  mov     rcx, rbp; this
0x1400197b9  mov     rdi, rax
0x1400197bc  call    ?FreeLine@SIO_CACHE@@IEAAXPEAVSIO_CACHE_LINE@@@Z; SIO_CACHE::FreeLine(SIO_CACHE_LINE *)
0x1400197c1  lea     rcx, [rdi+30h]; this
0x1400197c5  call    ?MarkUnlocked@SIO_CACHE_STATE@@QEAAXXZ; SIO_CACHE_STATE::MarkUnlocked(void)
0x1400197ca  jmp     loc_140019881
0x1400197cf  cmp     dword ptr [rbx+34h], 3
0x1400197d3  lea     rdi, [rbx+30h]
0x1400197d7  jnz     short loc_140019801
0x1400197d9  mov     rcx, rdi; this
0x1400197dc  call    ?MarkCommitted@SIO_CACHE_STATE@@QEAAEXZ; SIO_CACHE_STATE::MarkCommitted(void)
0x1400197e1  mov     rdx, rbx; struct SIO_CACHE_LINE *
0x1400197e4  mov     rcx, rbp; this
0x1400197e7  call    ?QueueLine@SIO_CACHE@@IEAAXPEAVSIO_CACHE_LINE@@@Z; SIO_CACHE::QueueLine(SIO_CACHE_LINE *)
0x1400197ec  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h; this
0x1400197f3  test    rcx, rcx
0x1400197f6  jz      short loc_140019801
0x1400197f8  mov     r8d, [rbx+34h]; unsigned __int64
0x1400197fc  call    ?LogMapping@SIO_CACHE_VERIFIER@@QEAAX_K0@Z; SIO_CACHE_VERIFIER::LogMapping(unsigned __int64,unsigned __int64)
0x140019801  cmp     dword ptr [rbx+34h], 7
0x140019805  jnz     short loc_140019831
0x140019807  xor     edx, edx; __int64
0x140019809  mov     rcx, rdi; this
0x14001980c  call    ?MarkDestaging@SIO_CACHE_STATE@@QEAAE_J@Z; SIO_CACHE_STATE::MarkDestaging(__int64)
0x140019811  mov     rcx, rbp; this
0x140019814  mov     rdx, rbx; struct SIO_CACHE_LINE *
0x140019817  call    ?QueueLineDirty@SIO_CACHE@@IEAAXPEAVSIO_CACHE_LINE@@@Z; SIO_CACHE::QueueLineDirty(SIO_CACHE_LINE *)
0x14001981c  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h; this
0x140019823  test    rcx, rcx
0x140019826  jz      short loc_140019831
0x140019828  mov     r8d, [rbx+34h]; unsigned __int64
0x14001982c  call    ?LogMapping@SIO_CACHE_VERIFIER@@QEAAX_K0@Z; SIO_CACHE_VERIFIER::LogMapping(unsigned __int64,unsigned __int64)
0x140019831  cmp     dword ptr [rbx+34h], 0Ah
0x140019835  jnz     short loc_140019881
0x140019837  mov     edi, [rbp+68h]
0x14001983a  lea     rcx, [rbx+48h]; BitMapHeader
0x14001983e  call    cs:__imp_RtlNumberOfSetBits
0x140019845  nop     dword ptr [rax+rax+00h]
0x14001984a  imul    eax, edi
0x14001984d  neg     eax
0x14001984f  movsxd  rcx, eax
0x140019852  mov     rax, [rbp+280h]
0x140019859  lock add [rax+68h], rcx
0x14001985e  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h; this
0x140019865  test    rcx, rcx
0x140019868  jz      short loc_140019876
0x14001986a  mov     r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x140019871  call    ?LogMapping@SIO_CACHE_VERIFIER@@QEAAX_K0@Z; SIO_CACHE_VERIFIER::LogMapping(unsigned __int64,unsigned __int64)
0x140019876  mov     rdx, rbx; struct SIO_CACHE_LINE *
0x140019879  mov     rcx, rbp; this
0x14001987c  call    ?FreeLine@SIO_CACHE@@IEAAXPEAVSIO_CACHE_LINE@@@Z; SIO_CACHE::FreeLine(SIO_CACHE_LINE *)
0x140019881  mov     rcx, rsi
0x140019884  mov     rsi, [rsi]
0x140019887  cmp     rcx, r14
0x14001988a  jnz     loc_140019776
0x140019890  mov     rdi, [rsp+48h+arg_10]
0x140019895  mov     rbx, [rsp+48h+arg_0]
0x14001989a  mov     rax, [rbp+1E8h]
0x1400198a1  mov     r14, [rsp+48h+var_20]
0x1400198a6  mov     rsi, [rsp+48h+arg_8]
0x1400198ab  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400198af  jz      short loc_1400198FD
0x1400198b1  cmp     dword ptr [rbp+21Ch], 0
0x1400198b8  jnz     short loc_1400198FD
0x1400198ba  cmp     byte ptr [rbp+200h], 0
0x1400198c1  jnz     short loc_1400198FD
0x1400198c3  cmp     byte ptr [rbp+201h], 0
0x1400198ca  jnz     short loc_1400198FD
0x1400198cc  mov     byte ptr [rbp+202h], 0
0x1400198d3  cmp     dword ptr [r13+30h], 1
0x1400198d8  jnz     short loc_1400198FD
0x1400198da  mov     r8, [r13+78h]
0x1400198de  lea     r9, [rax-1]
0x1400198e2  add     r9, r8
0x1400198e5  xor     edx, edx
0x1400198e7  mov     rax, r9
0x1400198ea  div     r8
0x1400198ed  sub     r9, rdx
0x1400198f0  cmp     r9, [r13+70h]
0x1400198f4  jnb     short loc_1400198FD
0x1400198f6  mov     byte ptr [rbp+200h], 1
0x1400198fd  movzx   edx, r12b; OldIrql
0x140019901  lea     rcx, [rbp+158h]; SpinLock
0x140019908  call    cs:__imp_ExReleaseSpinLockExclusive
0x14001990f  nop     dword ptr [rax+rax+00h]
0x140019914  cmp     dword ptr [rbp+264h], 4
0x14001991b  mov     r15, [rsp+48h+var_28]
0x140019920  mov     r13, [rsp+48h+var_18]
0x140019925  mov     r12, [rsp+48h+var_10]
0x14001992a  jnz     short loc_14001993D
0x14001992c  cmp     dword ptr [rbp+268h], 0
0x140019933  jnz     short loc_14001993D
0x140019935  mov     rcx, rbp; this
0x140019938  call    ?ClearDirtyState@SIO_CACHE@@IEAAXXZ; SIO_CACHE::ClearDirtyState(void)
0x14001993d  add     rsp, 40h
0x140019941  pop     rbp
0x140019942  retn
```
