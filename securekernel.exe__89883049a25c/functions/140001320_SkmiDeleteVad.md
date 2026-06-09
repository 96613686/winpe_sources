# SkmiDeleteVad

- ea: `0x140001320`
- end: `0x1400014ac`
- name: `SkmiDeleteVad`
- size: `396`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `9`
- tags: ``

## callers

- `0x140014dd0`
- `0x14001c554`
- `0x14001e53c`
- `0x1400280b0`
- `0x14005b9e4`
- `0x14005bbe8`
- `0x14005dd8c`
- `0x1400603cc`
- `0x140066464`
- `0x14006b310`
- `0x1400871f0`
- `0x1400875cc`

## callees

- `0x140001320`
- `0x140002410`
- `0x1400024b0`
- `0x140002900`
- `0x14000b084`
- `0x1400202b0`
- `0x1400202ec`
- `0x140095cd8`
- `0x1400f2fc0`

## pseudocode

```c
__int64 __fastcall SkmiDeleteVad(__int64 a1, __int64 a2)
{
  _QWORD *StackBase; // rdx
  __int64 v5; // rdx
  unsigned __int8 CurrentIrql; // r14
  unsigned __int64 v7; // rcx
  __int64 v8; // rcx
  unsigned __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 result; // rax
  __int64 v17; // r8
  __int64 v18; // r9
  _QWORD *v19; // rcx
  __int64 v20; // rdx

  StackBase = KeGetPcr()->NtTib.StackBase;
  if ( StackBase )
  {
    v5 = StackBase[18];
    if ( v5 )
      --*(_WORD *)(v5 + xmmword_140167150);
  }
  SkAcquirePushLockExclusive(a1 + 112);
  CurrentIrql = KeGetCurrentIrql();
  __writecr8(2u);
  SkAcquireSpinLockSharedAtDpcLevel(a1 + 192);
  SkAcquireSpinLockExclusiveAtDpcLevel(a1 + 120);
  *(_QWORD *)(a2 + 48) |= 0x800000000000uLL;
  if ( (*(_DWORD *)a1 & 0x200) != 0 && *(_QWORD *)(a1 + 656) == a2 )
  {
    v7 = *(_QWORD *)a2;
    if ( *(_QWORD *)a2 )
    {
      for ( ; *(_QWORD *)(v7 + 8); v7 = *(_QWORD *)(v7 + 8) )
        ;
    }
    else
    {
      v8 = *(_QWORD *)(a2 + 16);
      v9 = a2;
      while ( 1 )
      {
        v7 = v8 & 0xFFFFFFFFFFFFFFFCuLL;
        if ( !v7 || *(_QWORD *)(v7 + 8) == v9 )
          break;
        v9 = v7;
        v8 = *(_QWORD *)(v7 + 16);
      }
    }
    *(_QWORD *)(a1 + 656) = v7;
  }
  RtlAvlRemoveNode((unsigned __int64 *)(a1 + 104), a2);
  v12 = _InterlockedDecrement((volatile signed __int32 *)(a2 + 36));
  if ( v12 <= 0 )
  {
    if ( !v12 )
      __fastfail(0xEu);
    __fastfail(0xEu);
  }
  *(_DWORD *)(a1 + 120) = 0;
  SkTrackSpinLockRelease(v11, v10);
  _InterlockedAdd((volatile signed __int32 *)(a1 + 192), 0xFFFFFFFF);
  SkTrackSpinLockRelease(v14, v13);
  LOBYTE(v15) = CurrentIrql;
  SkeLowerIrql(v15);
  result = RtlReleaseSRWLockExclusive(a1 + 112);
  v19 = KeGetPcr()->NtTib.StackBase;
  if ( v19 )
  {
    v20 = v19[18];
    if ( v20 )
    {
      result = xmmword_140167150;
      if ( (*(_WORD *)(v20 + xmmword_140167150))++ == 0xFFFF )
      {
        result = xmmword_140167160 + v19[17];
        if ( *(_QWORD *)(v20 + xmmword_140167160) != result )
        {
          result = *((_QWORD *)&xmmword_140167150 + 1);
          if ( !*(_WORD *)(v20 + *((_QWORD *)&xmmword_140167150 + 1)) )
            return SkiCheckForKernelApcDelivery(xmmword_140167160, v20, v17, v18);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140001320  mov     [rsp+arg_8], rbx
0x140001325  mov     [rsp+arg_10], rbp
0x14000132a  push    rsi
0x14000132b  push    rdi
0x14000132c  push    r12
0x14000132e  push    r14
0x140001330  push    r15
0x140001332  sub     rsp, 20h
0x140001336  mov     rbx, rdx
0x140001339  or      r12d, 0FFFFFFFFh
0x14000133d  mov     rdx, gs:8
0x140001346  xor     r15d, r15d
0x140001349  mov     rdi, rcx
0x14000134c  test    rdx, rdx
0x14000134f  jz      short loc_14000136A
0x140001351  mov     rdx, [rdx+90h]
0x140001358  test    rdx, rdx
0x14000135b  jz      short loc_14000136A
0x14000135d  mov     rax, qword ptr cs:xmmword_140167150
0x140001364  add     [rdx+rax], r12w
0x140001369  nop
0x14000136a  add     rcx, 70h ; 'p'
0x14000136e  call    SkAcquirePushLockExclusive
0x140001373  mov     r14, cr8
0x140001377  mov     eax, 2
0x14000137c  mov     cr8, rax
0x140001380  lea     rsi, [rdi+0C0h]
0x140001387  mov     rcx, rsi
0x14000138a  call    SkAcquireSpinLockSharedAtDpcLevel
0x14000138f  lea     rcx, [rdi+78h]
0x140001393  call    SkAcquireSpinLockExclusiveAtDpcLevel
0x140001398  mov     rax, 800000000000h
0x1400013a2  or      [rbx+30h], rax
0x1400013a6  test    dword ptr [rdi], 200h
0x1400013ac  jz      short loc_1400013F7
0x1400013ae  cmp     [rdi+290h], rbx
0x1400013b5  jnz     short loc_1400013F7
0x1400013b7  mov     rcx, [rbx]
0x1400013ba  test    rcx, rcx
0x1400013bd  jz      short loc_1400013D4
0x1400013bf  cmp     [rcx+8], r15
0x1400013c3  jz      short loc_1400013F0
0x1400013c5  mov     rax, [rcx+8]
0x1400013c9  mov     rcx, rax
0x1400013cc  cmp     [rax+8], r15
0x1400013d0  jnz     short loc_1400013C5
0x1400013d2  jmp     short loc_1400013F0
0x1400013d4  mov     rcx, [rbx+10h]
0x1400013d8  mov     rax, rbx
0x1400013db  jmp     short loc_1400013EA
0x1400013dd  cmp     [rcx+8], rax
0x1400013e1  jz      short loc_1400013F0
0x1400013e3  mov     rax, rcx
0x1400013e6  mov     rcx, [rcx+10h]
0x1400013ea  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1400013ee  jnz     short loc_1400013DD
0x1400013f0  mov     [rdi+290h], rcx
0x1400013f7  lea     rcx, [rdi+68h]
0x1400013fb  mov     rdx, rbx
0x1400013fe  call    RtlAvlRemoveNode
0x140001403  mov     eax, r12d
0x140001406  lock xadd [rbx+24h], eax
0x14000140b  add     eax, r12d
0x14000140e  test    eax, eax
0x140001410  jg      short loc_14000141D
0x140001412  mov     ecx, 0Eh
0x140001417  jnz     short loc_14000141B
0x140001419  int     29h; Win8: RtlFailFast(ecx)
0x14000141b  int     29h; Win8: RtlFailFast(ecx)
0x14000141d  mov     [rdi+78h], r15d
0x140001421  call    SkTrackSpinLockRelease
0x140001426  lock add [rsi], r12d
0x14000142a  call    SkTrackSpinLockRelease
0x14000142f  mov     cl, r14b
0x140001432  call    SkeLowerIrql
0x140001437  lea     rcx, [rdi+70h]
0x14000143b  call    RtlReleaseSRWLockExclusive
0x140001440  mov     rcx, gs:8
0x140001449  test    rcx, rcx
0x14000144c  jz      short loc_140001494
0x14000144e  mov     rdx, [rcx+90h]
0x140001455  test    rdx, rdx
0x140001458  jz      short loc_140001494
0x14000145a  nop
0x14000145b  mov     rax, qword ptr cs:xmmword_140167150
0x140001462  add     word ptr [rdx+rax], 1
0x140001467  jnz     short loc_140001494
0x140001469  mov     rax, [rcx+88h]
0x140001470  nop
0x140001471  mov     rcx, qword ptr cs:xmmword_140167160
0x140001478  add     rax, rcx
0x14000147b  cmp     [rdx+rcx], rax
0x14000147f  jz      short loc_140001494
0x140001481  mov     rax, qword ptr cs:xmmword_140167150+8
0x140001488  cmp     [rdx+rax], r15w
0x14000148d  jnz     short loc_140001494
0x14000148f  call    SkiCheckForKernelApcDelivery
0x140001494  mov     rbx, [rsp+48h+arg_8]
0x140001499  mov     rbp, [rsp+48h+arg_10]
0x14000149e  add     rsp, 20h
0x1400014a2  pop     r15
0x1400014a4  pop     r14
0x1400014a6  pop     r12
0x1400014a8  pop     rdi
0x1400014a9  pop     rsi
0x1400014aa  retn
```
