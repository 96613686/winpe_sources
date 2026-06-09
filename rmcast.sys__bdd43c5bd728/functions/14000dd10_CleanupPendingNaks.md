# CleanupPendingNaks

- ea: `0x14000dd10`
- end: `0x14000e034`
- name: `CleanupPendingNaks`
- size: `804`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400067f4`
- `0x140006998`
- `0x14000cdfc`
- `0x14000cf04`

## callees

- `0x1400067f4`
- `0x14000dd10`
- `0x14000f0a0`
- `0x140010a7c`
- `0x140015970`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000dfba`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000dfba`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000de87`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e002`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000de87`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e002`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000dd5a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000df7e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000dd5a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000df7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dfd8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dfd8`

## pseudocode

```c
void __fastcall CleanupPendingNaks(__int64 a1, __int64 a2, __int64 a3)
{
  KIRQL v3; // r14
  int v7; // edx
  int v8; // ecx
  __int64 v9; // rcx
  __int64 v10; // rcx
  _QWORD *v11; // rdx
  _QWORD **v12; // r8
  __int64 v13; // r9
  _QWORD *v14; // rax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  _QWORD *v17; // rcx
  __int64 v18; // r10
  _QWORD *v19; // rdx
  int v20; // esi
  __int64 v21; // rax
  int v22; // edi
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rcx
  void *v26; // rcx
  _QWORD v27[2]; // [rsp+50h] [rbp-20h] BYREF
  _QWORD v28[2]; // [rsp+60h] [rbp-10h] BYREF

  v3 = 0;
  v27[1] = v27;
  v27[0] = v27;
  v28[1] = v28;
  v28[0] = v28;
  if ( !a3 )
    v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 360));
  v7 = *(_DWORD *)(a1 + 32);
  v8 = v7 & 0x10000;
  if ( (v7 & 0x400) != 0 )
  {
    if ( v8 )
      goto LABEL_39;
    v9 = *(_QWORD *)(a1 + 48);
    *(_DWORD *)(a1 + 32) = v7 | 0x10000;
    PgmMoveList(v9 + 120, v9 + 152);
    v10 = *(_QWORD *)(a1 + 48);
    v11 = (_QWORD *)(v10 + 168);
  }
  else
  {
    if ( v8 )
    {
      PgmMoveList(*(_QWORD *)(a1 + 48) + 152LL, v27);
      PgmMoveList(*(_QWORD *)(a1 + 48) + 168LL, v28);
      *(_DWORD *)(a1 + 32) &= ~0x10000u;
    }
    PgmMoveList(*(_QWORD *)(a1 + 48) + 120LL, v27);
    v10 = *(_QWORD *)(a1 + 48);
    v11 = v28;
  }
  PgmMoveList(v10 + 136, v11);
  v13 = *(_QWORD *)(a1 + 48);
  if ( *(_QWORD *)(v13 + 216) )
  {
    v12 = (_QWORD **)(v13 + 184);
    while ( 1 )
    {
      v14 = *v12;
      if ( *v12 == v12 )
        break;
      v15 = (_QWORD *)(v13 + 184);
      if ( v14[1] != v13 + 184 )
        goto LABEL_28;
      v16 = *v14;
      if ( *(_QWORD **)(*v14 + 8LL) != v14
        || (*v15 = v16,
            *(_QWORD *)(v16 + 8) = v15,
            v17 = v14 - 2,
            v14[1] = v14,
            *v14 = v14,
            v18 = *(v14 - 2),
            *(_QWORD **)(v18 + 8) != v14 - 2)
        || (v19 = (_QWORD *)*(v14 - 1), (_QWORD *)*v19 != v17) )
      {
LABEL_28:
        __fastfail(3u);
      }
      *v19 = v18;
      *(_QWORD *)(v18 + 8) = v19;
      *(v14 - 1) = v17;
      *v17 = v17;
    }
  }
  v20 = 0;
  if ( !a3 )
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 360), v3);
  while ( (_QWORD *)v27[0] != v27 )
  {
    if ( *(_QWORD **)(v27[0] + 8LL) != v27 )
      goto LABEL_28;
    v21 = *(_QWORD *)v27[0];
    if ( *(_QWORD *)(*(_QWORD *)v27[0] + 8LL) != v27[0] )
      goto LABEL_28;
    v27[0] = *(_QWORD *)v27[0];
    *(_QWORD *)(v21 + 8) = v27;
    FreeNakContext(a1);
    ++v20;
  }
  v22 = 0;
  while ( (_QWORD *)v28[0] != v28 )
  {
    if ( *(_QWORD **)(v28[0] + 8LL) != v28 )
      goto LABEL_28;
    v23 = *(_QWORD *)v28[0];
    if ( *(_QWORD *)(*(_QWORD *)v28[0] + 8LL) != v28[0] )
      goto LABEL_28;
    v28[0] = *(_QWORD *)v28[0];
    *(_QWORD *)(v23 + 8) = v28;
    FreeNakContext(a1);
    ++v22;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_qdddddd(
      WPP_GLOBAL_Control->AttachedDevice,
      *(_QWORD *)(a1 + 48),
      v12,
      a1,
      *(_DWORD *)(*(_QWORD *)(a1 + 48) + 56LL),
      *(_DWORD *)(*(_QWORD *)(a1 + 48) + 272LL),
      v20,
      *(_DWORD *)(*(_QWORD *)(a1 + 48) + 260LL),
      v22,
      *(unsigned __int8 *)(a1 + 160));
  *(_DWORD *)(*(_QWORD *)(a1 + 48) + 272LL) = 0;
  if ( !a3 )
    v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 360));
  v24 = *(_DWORD *)(a1 + 32);
  if ( (v24 & 0x10000) == 0 )
  {
    if ( (v24 & 0x8000) != 0 )
    {
      *(_DWORD *)(*(_QWORD *)(a1 + 48) + 276LL) = 0;
      v25 = *(_QWORD *)(a1 + 48);
      *(_DWORD *)(a1 + 32) &= ~0x8000u;
      ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v25 + 320));
    }
    v26 = *(void **)(*(_QWORD *)(a1 + 48) + 216LL);
    if ( v26 )
    {
      ExFreePoolWithTag(v26, 0);
      *(_QWORD *)(*(_QWORD *)(a1 + 48) + 216LL) = 0;
    }
  }
LABEL_39:
  if ( !a3 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 360), v3);
    if ( a2 )
      PgmDereferenceSessionCommon(a1);
  }
}

```

## disassembly

```asm
0x14000dd10  push    rbp
0x14000dd12  push    rbx
0x14000dd13  push    rsi
0x14000dd14  push    rdi
0x14000dd15  push    r12
0x14000dd17  push    r14
0x14000dd19  push    r15
0x14000dd1b  mov     rbp, rsp
0x14000dd1e  sub     rsp, 70h
0x14000dd22  lea     rax, [rbp+var_20]
0x14000dd26  xor     r14b, r14b
0x14000dd29  mov     [rbp+var_18], rax
0x14000dd2d  lea     rax, [rbp+var_20]
0x14000dd31  mov     [rbp+var_20], rax
0x14000dd35  lea     rax, [rbp+var_10]
0x14000dd39  mov     [rbp+var_8], rax
0x14000dd3d  lea     rax, [rbp+var_10]
0x14000dd41  mov     [rbp+var_10], rax
0x14000dd45  mov     r15, r8
0x14000dd48  mov     r12, rdx
0x14000dd4b  mov     rbx, rcx
0x14000dd4e  test    r8, r8
0x14000dd51  jnz     short loc_14000DD69
0x14000dd53  add     rcx, 168h; SpinLock
0x14000dd5a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000dd61  nop     dword ptr [rax+rax+00h]
0x14000dd66  mov     r14b, al
0x14000dd69  mov     edx, [rbx+20h]
0x14000dd6c  mov     eax, 10000h
0x14000dd71  mov     ecx, edx
0x14000dd73  and     ecx, eax
0x14000dd75  bt      edx, 0Ah
0x14000dd79  jnb     short loc_14000DDA9
0x14000dd7b  test    ecx, ecx
0x14000dd7d  jnz     loc_14000DFF3
0x14000dd83  mov     rcx, [rbx+30h]
0x14000dd87  or      edx, eax
0x14000dd89  mov     [rbx+20h], edx
0x14000dd8c  lea     rdx, [rcx+98h]
0x14000dd93  add     rcx, 78h ; 'x'
0x14000dd97  call    PgmMoveList
0x14000dd9c  mov     rcx, [rbx+30h]
0x14000dda0  lea     rdx, [rcx+0A8h]
0x14000dda7  jmp     short loc_14000DDF3
0x14000dda9  test    ecx, ecx
0x14000ddab  jz      short loc_14000DDDA
0x14000ddad  mov     rcx, [rbx+30h]
0x14000ddb1  lea     rdx, [rbp+var_20]
0x14000ddb5  add     rcx, 98h
0x14000ddbc  call    PgmMoveList
0x14000ddc1  mov     rcx, [rbx+30h]
0x14000ddc5  lea     rdx, [rbp+var_10]
0x14000ddc9  add     rcx, 0A8h
0x14000ddd0  call    PgmMoveList
0x14000ddd5  btr     dword ptr [rbx+20h], 10h
0x14000ddda  mov     rcx, [rbx+30h]
0x14000ddde  lea     rdx, [rbp+var_20]
0x14000dde2  add     rcx, 78h ; 'x'
0x14000dde6  call    PgmMoveList
0x14000ddeb  mov     rcx, [rbx+30h]
0x14000ddef  lea     rdx, [rbp+var_10]
0x14000ddf3  add     rcx, 88h
0x14000ddfa  call    PgmMoveList
0x14000ddff  mov     r9, [rbx+30h]
0x14000de03  cmp     qword ptr [r9+0D8h], 0
0x14000de0b  jz      short loc_14000DE76
0x14000de0d  lea     r8, [r9+0B8h]
0x14000de14  mov     rax, [r8]
0x14000de17  cmp     rax, r8
0x14000de1a  jz      short loc_14000DE76
0x14000de1c  lea     rcx, [r9+0B8h]
0x14000de23  cmp     [rax+8], rcx
0x14000de27  jnz     loc_14000DF05
0x14000de2d  mov     rdx, [rax]
0x14000de30  cmp     [rdx+8], rax
0x14000de34  jnz     loc_14000DF05
0x14000de3a  mov     [rcx], rdx
0x14000de3d  mov     [rdx+8], rcx
0x14000de41  lea     rcx, [rax-10h]
0x14000de45  mov     [rax+8], rax
0x14000de49  mov     [rax], rax
0x14000de4c  mov     r10, [rcx]
0x14000de4f  cmp     [r10+8], rcx
0x14000de53  jnz     loc_14000DF05
0x14000de59  mov     rdx, [rax-8]
0x14000de5d  cmp     [rdx], rcx
0x14000de60  jnz     loc_14000DF05
0x14000de66  mov     [rdx], r10
0x14000de69  mov     [r10+8], rdx
0x14000de6d  mov     [rax-8], rcx
0x14000de71  mov     [rcx], rcx
0x14000de74  jmp     short loc_14000DE14
0x14000de76  xor     esi, esi
0x14000de78  test    r15, r15
0x14000de7b  jnz     short loc_14000DE93
0x14000de7d  lea     rcx, [rbx+168h]; SpinLock
0x14000de84  mov     dl, r14b; NewIrql
0x14000de87  call    cs:__imp_KeReleaseSpinLock
0x14000de8e  nop     dword ptr [rax+rax+00h]
0x14000de93  mov     rdx, [rbp+var_20]
0x14000de97  lea     rax, [rbp+var_20]
0x14000de9b  cmp     rdx, rax
0x14000de9e  jz      short loc_14000DECB
0x14000dea0  lea     rax, [rbp+var_20]
0x14000dea4  cmp     [rdx+8], rax
0x14000dea8  jnz     short loc_14000DF05
0x14000deaa  mov     rax, [rdx]
0x14000dead  cmp     [rax+8], rdx
0x14000deb1  jnz     short loc_14000DF05
0x14000deb3  lea     rcx, [rbp+var_20]
0x14000deb7  mov     [rbp+var_20], rax
0x14000debb  mov     [rax+8], rcx
0x14000debf  mov     rcx, rbx
0x14000dec2  call    FreeNakContext
0x14000dec7  inc     esi
0x14000dec9  jmp     short loc_14000DE93
0x14000decb  xor     edi, edi
0x14000decd  mov     rdx, [rbp+var_10]
0x14000ded1  lea     rax, [rbp+var_10]
0x14000ded5  cmp     rdx, rax
0x14000ded8  jz      short loc_14000DF0C
0x14000deda  lea     rax, [rbp+var_10]
0x14000dede  cmp     [rdx+8], rax
0x14000dee2  jnz     short loc_14000DF05
0x14000dee4  mov     rax, [rdx]
0x14000dee7  cmp     [rax+8], rdx
0x14000deeb  jnz     short loc_14000DF05
0x14000deed  lea     rcx, [rbp+var_10]
0x14000def1  mov     [rbp+var_10], rax
0x14000def5  mov     [rax+8], rcx
0x14000def9  mov     rcx, rbx
0x14000defc  call    FreeNakContext
0x14000df01  inc     edi
0x14000df03  jmp     short loc_14000DECD
0x14000df05  mov     ecx, 3
0x14000df0a  int     29h; Win8: RtlFailFast(ecx)
0x14000df0c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000df13  lea     rax, WPP_GLOBAL_Control
0x14000df1a  cmp     rcx, rax
0x14000df1d  jz      short loc_14000DF64
0x14000df1f  mov     eax, [rcx+2Ch]
0x14000df22  test    al, 4
0x14000df24  jz      short loc_14000DF64
0x14000df26  mov     rdx, [rbx+30h]
0x14000df2a  mov     r9, rbx
0x14000df2d  movzx   eax, byte ptr [rbx+0A0h]
0x14000df34  mov     rcx, [rcx+18h]
0x14000df38  mov     [rsp+70h+var_28], eax
0x14000df3c  mov     eax, [rdx+104h]
0x14000df42  mov     [rsp+70h+var_30], edi
0x14000df46  mov     [rsp+70h+var_38], eax
0x14000df4a  mov     eax, [rdx+110h]
0x14000df50  mov     [rsp+70h+var_40], esi
0x14000df54  mov     [rsp+70h+var_48], eax
0x14000df58  mov     eax, [rdx+38h]
0x14000df5b  mov     [rsp+70h+var_50], eax
0x14000df5f  call    WPP_SF_qdddddd
0x14000df64  mov     rax, [rbx+30h]
0x14000df68  mov     dword ptr [rax+110h], 0
0x14000df72  test    r15, r15
0x14000df75  jnz     short loc_14000DF8D
0x14000df77  lea     rcx, [rbx+168h]; SpinLock
0x14000df7e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000df85  nop     dword ptr [rax+rax+00h]
0x14000df8a  mov     r14b, al
0x14000df8d  mov     eax, [rbx+20h]
0x14000df90  bt      eax, 10h
0x14000df94  jb      short loc_14000DFF3
0x14000df96  bt      eax, 0Fh
0x14000df9a  jnb     short loc_14000DFC6
0x14000df9c  mov     rax, [rbx+30h]
0x14000dfa0  mov     dword ptr [rax+114h], 0
0x14000dfaa  mov     rcx, [rbx+30h]
0x14000dfae  btr     dword ptr [rbx+20h], 0Fh
0x14000dfb3  add     rcx, 140h; Lookaside
0x14000dfba  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000dfc1  nop     dword ptr [rax+rax+00h]
0x14000dfc6  mov     rax, [rbx+30h]
0x14000dfca  mov     rcx, [rax+0D8h]; P
0x14000dfd1  test    rcx, rcx
0x14000dfd4  jz      short loc_14000DFF3
0x14000dfd6  xor     edx, edx; Tag
0x14000dfd8  call    cs:__imp_ExFreePoolWithTag
0x14000dfdf  nop     dword ptr [rax+rax+00h]
0x14000dfe4  mov     rax, [rbx+30h]
0x14000dfe8  mov     qword ptr [rax+0D8h], 0
0x14000dff3  test    r15, r15
0x14000dff6  jnz     short loc_14000E024
0x14000dff8  lea     rcx, [rbx+168h]; SpinLock
0x14000dfff  mov     dl, r14b; NewIrql
0x14000e002  call    cs:__imp_KeReleaseSpinLock
0x14000e009  nop     dword ptr [rax+rax+00h]
0x14000e00e  test    r12, r12
0x14000e011  jz      short loc_14000E024
0x14000e013  mov     edx, 52534553h
0x14000e018  lea     r8d, [r15+0Bh]
0x14000e01c  mov     rcx, rbx
0x14000e01f  call    PgmDereferenceSessionCommon
0x14000e024  add     rsp, 70h
0x14000e028  pop     r15
0x14000e02a  pop     r14
0x14000e02c  pop     r12
0x14000e02e  pop     rdi
0x14000e02f  pop     rsi
0x14000e030  pop     rbx
0x14000e031  pop     rbp
0x14000e032  retn
```
