# UdfInitializeAllocationSupport

- ea: `0x140048c24`
- end: `0x140049018`
- name: `UdfInitializeAllocationSupport`
- size: `1012`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140049f80`
- `0x14004d700`

## callees

- `0x14000c21c`
- `0x14000c4fc`
- `0x14000cad4`
- `0x14000e5d8`
- `0x14001093c`
- `0x140048c24`
- `0x140049020`

## import_xrefs

- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x140048d6f`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x140048d6f`
- `ntoskrnl!ExRaiseStatus` at `0x140048cc7`
- `ntoskrnl!ExRaiseStatus` at `0x140048cc7`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048fcf`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005a222`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048fcf`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005a222`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140048cae`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140048cae`
- `ntoskrnl!ExInitializeResourceLite` at `0x140048c81`
- `ntoskrnl!ExInitializeResourceLite` at `0x140048c81`
- `ntoskrnl!ExDeleteResourceLite` at `0x140048fea`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005a246`
- `ntoskrnl!ExDeleteResourceLite` at `0x140048fea`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005a246`

## pseudocode

```c
void __fastcall UdfInitializeAllocationSupport(__int64 a1, __int64 a2)
{
  __int64 v3; // r13
  unsigned int v4; // r12d
  unsigned int i; // esi
  __int64 v6; // rdi
  BOOLEAN v7; // dl
  int v8; // r14d
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // r15
  int v12; // eax
  unsigned int v13; // eax
  __int64 v14; // r9
  int v15; // r8d
  int v16; // edx
  unsigned int v17; // ecx
  unsigned int v18; // edx
  unsigned int v19; // r8d
  int v20; // ecx
  int v21; // eax
  char v22; // si
  unsigned int j; // edi
  __int64 v24; // r14
  __int64 Lbn; // [rsp+90h] [rbp+18h] BYREF

  v3 = a1;
  v4 = 0;
  if ( (*(_DWORD *)(a2 + 48) & 0x20000010) != 0 )
    return;
  for ( i = 0; i < 2; ++i )
  {
    v6 = 200LL * i;
    ExInitializeResourceLite((PERESOURCE)(v6 + a2 + 552));
    v7 = 0;
    if ( !v3 || (*(_DWORD *)(v3 + 28) & 4) != 0 )
      v7 = 1;
    if ( !ExAcquireResourceExclusiveLite((PERESOURCE)(v6 + a2 + 552), v7) )
    {
      *(_DWORD *)(v3 + 24) = -1073741608;
      ExRaiseStatus(-1073741608);
    }
    v4 = i;
    if ( i )
    {
      if ( (*(_DWORD *)(a2 + 48) & 0x4000000) == 0 )
        continue;
      *(_QWORD *)(v6 + a2 + 488) = *(_QWORD *)(a2 + 336);
      v9 = *(_QWORD *)(a2 + 336);
      if ( (*(_DWORD *)(v9 + 212) & 2) != 0 )
      {
        v8 = *(_DWORD *)(56LL * *(unsigned __int16 *)(*(_QWORD *)(a2 + 16) + 84LL) + *(_QWORD *)(a2 + 16) + 120);
      }
      else
      {
        Lbn = 0;
        FsRtlLookupLargeMcbEntry((PLARGE_MCB)(v9 + 232), 0, &Lbn, 0, 0, 0, 0);
        v8 = Lbn - *(_DWORD *)(*(_QWORD *)(v3 + 16) + 656LL);
      }
      v10 = *(_QWORD *)(*(_QWORD *)(a2 + 320) + 32LL) / (__int64)*(unsigned int *)(a2 + 68);
      *(_DWORD *)(v6 + a2 + 664) = v10;
      *(_DWORD *)(v6 + a2 + 660) = v10;
    }
    else
    {
      *(_QWORD *)(v6 + a2 + 488) = *(_QWORD *)(a2 + 296);
      v8 = *(_DWORD *)(56LL * *(unsigned __int16 *)(*(_QWORD *)(a2 + 16) + 92LL) + *(_QWORD *)(a2 + 16) + 120);
    }
    UdfMapOrPinBitmapLbnRange(v3, i, 0);
    v11 = *(_QWORD *)(v6 + a2 + 512);
    if ( (unsigned __int8)UdfVerifyDescriptor(v3, v11, 264, 24, v8, 1)
      && (v12 = *(_DWORD *)(v11 + 16), v12 == *(_DWORD *)(v6 + a2 + 664))
      && *(_DWORD *)(v11 + 20) >= (unsigned int)(v12 + 7) >> 3 )
    {
      v13 = UdfCountFreeBlocksInBitmap(v3, i);
      v14 = v13;
      *(_DWORD *)(v6 + a2 + 668) = v13;
      if ( !i )
      {
        if ( (*(_BYTE *)(a2 + 2128) & 0xC0) == 0xC0 )
        {
          v15 = *(_DWORD *)(v6 + a2 + 664);
          if ( v15 + *(_DWORD *)(56LL * *(unsigned __int16 *)(*(_QWORD *)(a2 + 16) + 92LL) + *(_QWORD *)(a2 + 16) + 104) > (unsigned int)(*(_DWORD *)(v6 + a2 + 684) - 1) )
            *(_DWORD *)(v6 + a2 + 680) = 0;
          v16 = *(_DWORD *)(*(_QWORD *)(a2 + 16) + 32LL);
          v17 = *(_DWORD *)(v6 + a2 + 680);
          if ( v17 >= v16 + 256 )
          {
            v17 = v17 - v16 - 256;
            *(_DWORD *)(v6 + a2 + 680) = v17;
          }
          *(_DWORD *)(v6 + a2 + 660) += v17;
          *(_DWORD *)(v6 + a2 + 664) = v15 + v17;
          *(_DWORD *)(v6 + a2 + 668) += *(_DWORD *)(v6 + a2 + 680);
          v14 = *(unsigned int *)(v6 + a2 + 668);
          *(_DWORD *)(v6 + a2 + 680) = 0;
        }
        if ( (*(_DWORD *)(a2 + 48) & 0x4000000) == 0 )
        {
          v18 = *(_DWORD *)(v6 + a2 + 664) / 0x64u;
          *(_DWORD *)(v6 + a2 + 496) = v18;
          if ( *(_DWORD *)(a2 + 88) )
          {
            v19 = v18 + *(_DWORD *)(*(_QWORD *)(v3 + 16) + 656LL);
            v20 = *(_DWORD *)(a2 + 92);
            if ( (v20 & v19) != 0 )
              *(_DWORD *)(v6 + a2 + 496) = v18 + (~v20 & (v20 + v19)) - v19;
          }
        }
      }
      a1 = *(_QWORD *)&WPP_GLOBAL_Control;
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
      {
        WPP_SF_dd(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          57,
          WPP_3702783af02333f5d52357996bb663b1_Traceguids,
          v14,
          *(_DWORD *)(v6 + a2 + 664));
      }
    }
    else
    {
      a1 = *(_QWORD *)&WPP_GLOBAL_Control;
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
      {
        WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 58, WPP_3702783af02333f5d52357996bb663b1_Traceguids);
      }
      *(_DWORD *)(a2 + 48) |= 0x10u;
    }
  }
  v21 = *(_DWORD *)(a2 + 48);
  if ( (v21 & 0x10) != 0 )
  {
    v22 = 1;
  }
  else
  {
    v22 = 0;
    *(_DWORD *)(a2 + 48) = v21 | 0x40;
  }
  for ( j = 0; j <= v4; ++j )
  {
    UdfUnpinCurrentBitmapPage(a1, a2, j);
    v24 = 200LL * j;
    ExReleaseResourceLite((PERESOURCE)(v24 + a2 + 552));
    if ( v22 )
      ExDeleteResourceLite((PERESOURCE)(v24 + a2 + 552));
  }
}

```

## disassembly

```asm
0x140048c24  mov     rax, rsp
0x140048c27  mov     [rax+8], rbx
0x140048c2b  mov     [rax+20h], rsi
0x140048c2f  mov     [rax+10h], rdx
0x140048c33  push    rdi
0x140048c34  push    r12
0x140048c36  push    r13
0x140048c38  push    r14
0x140048c3a  push    r15
0x140048c3c  sub     rsp, 50h
0x140048c40  mov     rbx, rdx
0x140048c43  mov     r13, rcx
0x140048c46  xor     r15d, r15d
0x140048c49  mov     r12d, r15d
0x140048c4c  mov     [rax-30h], r15d
0x140048c50  test    dword ptr [rdx+30h], 20000010h
0x140048c57  jnz     loc_140048FFD
0x140048c5d  mov     esi, r15d
0x140048c60  mov     [rax-34h], r15d
0x140048c64  cmp     esi, 2
0x140048c67  jnb     loc_140048F99
0x140048c6d  mov     eax, esi
0x140048c6f  imul    rdi, rax, 0C8h
0x140048c76  lea     r14, [rdi+rbx]
0x140048c7a  lea     rcx, [r14+228h]; Resource
0x140048c81  call    cs:__imp_ExInitializeResourceLite
0x140048c88  nop     dword ptr [rax+rax+00h]
0x140048c8d  mov     dl, r15b
0x140048c90  mov     [rsp+78h+var_38], dl
0x140048c94  test    r13, r13
0x140048c97  jz      short loc_140048CA1
0x140048c99  mov     eax, [r13+1Ch]
0x140048c9d  test    al, 4
0x140048c9f  jz      short loc_140048CA7
0x140048ca1  mov     dl, 1; Wait
0x140048ca3  mov     [rsp+78h+var_38], dl
0x140048ca7  lea     rcx, [r14+228h]; Resource
0x140048cae  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140048cb5  nop     dword ptr [rax+rax+00h]
0x140048cba  test    al, al
0x140048cbc  jnz     short loc_140048CD4
0x140048cbe  mov     ecx, 0C00000D8h; Status
0x140048cc3  mov     [r13+18h], ecx
0x140048cc7  call    cs:__imp_ExRaiseStatus
0x140048cd4  mov     r12d, esi
0x140048cd7  mov     [rsp+78h+var_30], esi
0x140048cdb  test    esi, esi
0x140048cdd  jnz     short loc_140048D04
0x140048cdf  mov     rax, [rbx+128h]
0x140048ce6  mov     [rdi+rbx+1E8h], rax
0x140048cee  mov     rdx, [rbx+10h]
0x140048cf2  movzx   eax, word ptr [rdx+5Ch]
0x140048cf6  imul    rcx, rax, 38h ; '8'
0x140048cfa  mov     r14d, [rcx+rdx+78h]
0x140048cff  jmp     loc_140048DAF
0x140048d04  test    dword ptr [rbx+30h], 4000000h
0x140048d0b  jz      loc_140048F8E
0x140048d11  mov     rax, [rbx+150h]
0x140048d18  mov     [rdi+rbx+1E8h], rax
0x140048d20  mov     rcx, [rbx+150h]
0x140048d27  mov     eax, [rcx+0D4h]
0x140048d2d  test    al, 2
0x140048d2f  jz      short loc_140048D44
0x140048d31  mov     rdx, [rbx+10h]
0x140048d35  movzx   eax, word ptr [rdx+54h]
0x140048d39  imul    rcx, rax, 38h ; '8'
0x140048d3d  mov     r14d, [rcx+rdx+78h]
0x140048d42  jmp     short loc_140048D8E
0x140048d44  mov     [rsp+78h+Lbn], r15
0x140048d4c  add     rcx, 0E8h; Mcb
0x140048d53  mov     [rsp+78h+Index], r15; Index
0x140048d58  mov     [rsp+78h+SectorCountFromStartingLbn], r15; SectorCountFromStartingLbn
0x140048d5d  mov     [rsp+78h+StartingLbn], r15; StartingLbn
0x140048d62  xor     r9d, r9d; SectorCountFromLbn
0x140048d65  lea     r8, [rsp+78h+Lbn]; Lbn
0x140048d6d  xor     edx, edx; Vbn
0x140048d6f  call    cs:__imp_FsRtlLookupLargeMcbEntry
0x140048d76  nop     dword ptr [rax+rax+00h]
0x140048d7b  mov     rax, [r13+10h]
0x140048d7f  mov     r14, [rsp+78h+Lbn]
0x140048d87  sub     r14d, [rax+290h]
0x140048d8e  mov     rax, [rbx+140h]
0x140048d95  mov     ecx, [rbx+44h]
0x140048d98  mov     rax, [rax+20h]
0x140048d9c  cqo
0x140048d9e  idiv    rcx
0x140048da1  mov     [rdi+rbx+298h], eax
0x140048da8  mov     [rdi+rbx+294h], eax
0x140048daf  xor     r8d, r8d
0x140048db2  mov     edx, esi
0x140048db4  mov     rcx, r13
0x140048db7  call    UdfMapOrPinBitmapLbnRange
0x140048dbc  mov     r15, [rdi+rbx+200h]
0x140048dc4  mov     r8d, 108h
0x140048dca  mov     dword ptr [rsp+78h+SectorCountFromStartingLbn], 1
0x140048dd2  mov     dword ptr [rsp+78h+StartingLbn], r14d
0x140048dd7  mov     r9d, 18h
0x140048ddd  mov     rdx, r15
0x140048de0  mov     rcx, r13
0x140048de3  call    UdfVerifyDescriptor
0x140048de8  test    al, al
0x140048dea  jz      loc_140048F56
0x140048df0  mov     eax, [r15+10h]
0x140048df4  cmp     eax, [rdi+rbx+298h]
0x140048dfb  jnz     loc_140048F56
0x140048e01  add     eax, 7
0x140048e04  shr     eax, 3
0x140048e07  cmp     [r15+14h], eax
0x140048e0b  jb      loc_140048F56
0x140048e11  mov     edx, esi
0x140048e13  mov     rcx, r13
0x140048e16  call    UdfCountFreeBlocksInBitmap
0x140048e1b  mov     r9d, eax
0x140048e1e  mov     [rdi+rbx+29Ch], eax
0x140048e25  xor     r15d, r15d
0x140048e28  test    esi, esi
0x140048e2a  jnz     loc_140048F1A
0x140048e30  mov     eax, [rbx+850h]
0x140048e36  and     eax, 0C0h
0x140048e3b  cmp     al, 0C0h
0x140048e3d  jnz     loc_140048ECB
0x140048e43  mov     rdx, [rbx+10h]
0x140048e47  mov     r8d, [rdi+rbx+298h]
0x140048e4f  movzx   eax, word ptr [rdx+5Ch]
0x140048e53  imul    rcx, rax, 38h ; '8'
0x140048e57  mov     ecx, [rcx+rdx+68h]
0x140048e5b  add     ecx, r8d
0x140048e5e  mov     eax, [rdi+rbx+2ACh]
0x140048e65  dec     eax
0x140048e67  cmp     ecx, eax
0x140048e69  jbe     short loc_140048E73
0x140048e6b  mov     [rdi+rbx+2A8h], r15d
0x140048e73  mov     rax, [rbx+10h]
0x140048e77  mov     edx, [rax+20h]
0x140048e7a  mov     ecx, [rdi+rbx+2A8h]
0x140048e81  lea     eax, [rdx+100h]
0x140048e87  cmp     ecx, eax
0x140048e89  jb      short loc_140048E9A
0x140048e8b  sub     ecx, edx
0x140048e8d  add     ecx, 0FFFFFF00h
0x140048e93  mov     [rdi+rbx+2A8h], ecx
0x140048e9a  mov     eax, ecx
0x140048e9c  add     [rdi+rbx+294h], ecx
0x140048ea3  add     eax, r8d
0x140048ea6  mov     [rdi+rbx+298h], eax
0x140048ead  mov     eax, [rdi+rbx+2A8h]
0x140048eb4  add     [rdi+rbx+29Ch], eax
0x140048ebb  mov     r9d, [rdi+rbx+29Ch]
0x140048ec3  mov     [rdi+rbx+2A8h], r15d
0x140048ecb  test    dword ptr [rbx+30h], 4000000h
0x140048ed2  jnz     short loc_140048F1A
0x140048ed4  mov     eax, 51EB851Fh
0x140048ed9  mul     dword ptr [rdi+rbx+298h]
0x140048ee0  shr     edx, 5
0x140048ee3  mov     [rdi+rbx+1F0h], edx
0x140048eea  cmp     [rbx+58h], r15d
0x140048eee  jz      short loc_140048F1A
0x140048ef0  mov     rax, [r13+10h]
0x140048ef4  mov     r8d, [rax+290h]
0x140048efb  add     r8d, edx
0x140048efe  mov     ecx, [rbx+5Ch]
0x140048f01  test    r8d, ecx
0x140048f04  jz      short loc_140048F1A
0x140048f06  lea     eax, [rcx+r8]
0x140048f0a  not     ecx
0x140048f0c  and     eax, ecx
0x140048f0e  sub     eax, r8d
0x140048f11  add     eax, edx
0x140048f13  mov     [rdi+rbx+1F0h], eax
0x140048f1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140048f21  lea     rax, WPP_GLOBAL_Control
0x140048f28  cmp     rcx, rax
0x140048f2b  jz      short loc_140048F8C
0x140048f2d  mov     eax, [rcx+2Ch]
0x140048f30  test    al, 1
0x140048f32  jz      short loc_140048F8C
0x140048f34  mov     edx, 39h ; '9'
0x140048f39  mov     eax, [rdi+rbx+298h]
0x140048f40  mov     dword ptr [rsp+78h+StartingLbn], eax
0x140048f44  lea     r8, WPP_3702783af02333f5d52357996bb663b1_Traceguids
0x140048f4b  mov     rcx, [rcx+18h]
0x140048f4f  call    WPP_SF_dd
0x140048f54  jmp     short loc_140048F8C
0x140048f56  mov     rcx, cs:WPP_GLOBAL_Control
0x140048f5d  lea     rax, WPP_GLOBAL_Control
0x140048f64  cmp     rcx, rax
0x140048f67  jz      short loc_140048F85
0x140048f69  mov     eax, [rcx+2Ch]
0x140048f6c  test    al, 1
0x140048f6e  jz      short loc_140048F85
0x140048f70  mov     edx, 3Ah ; ':'
0x140048f75  lea     r8, WPP_3702783af02333f5d52357996bb663b1_Traceguids
0x140048f7c  mov     rcx, [rcx+18h]
0x140048f80  call    WPP_SF_
0x140048f85  or      dword ptr [rbx+30h], 10h
0x140048f89  xor     r15d, r15d
0x140048f8c  jmp     short $+2
0x140048f8e  inc     esi
0x140048f90  mov     [rsp+78h+var_34], esi
0x140048f94  jmp     loc_140048C64
0x140048f99  mov     eax, [rbx+30h]
0x140048f9c  test    al, 10h
0x140048f9e  jnz     short loc_140048FAB
0x140048fa0  mov     sil, r15b
0x140048fa3  or      eax, 40h
0x140048fa6  mov     [rbx+30h], eax
0x140048fa9  jmp     short loc_140048FAE
0x140048fab  mov     sil, 1
0x140048fae  mov     edi, r15d
0x140048fb1  mov     r8d, edi
0x140048fb4  mov     rdx, rbx
0x140048fb7  call    UdfUnpinCurrentBitmapPage
0x140048fbc  mov     eax, edi
0x140048fbe  imul    r14, rax, 0C8h
0x140048fc5  lea     rcx, [rbx+228h]
0x140048fcc  add     rcx, r14; Resource
0x140048fcf  call    cs:__imp_ExReleaseResourceLite
0x140048fd6  nop     dword ptr [rax+rax+00h]
0x140048fdb  test    sil, sil
0x140048fde  jz      short loc_140048FF6
0x140048fe0  lea     rcx, [rbx+228h]
0x140048fe7  add     rcx, r14; Resource
0x140048fea  call    cs:__imp_ExDeleteResourceLite
0x140048ff1  nop     dword ptr [rax+rax+00h]
0x140048ff6  inc     edi
0x140048ff8  cmp     edi, r12d
0x140048ffb  jbe     short loc_140048FB1
0x140048ffd  lea     r11, [rsp+78h+var_28]
0x140049002  mov     rbx, [r11+30h]
0x140049006  mov     rsi, [r11+48h]
0x14004900a  mov     rsp, r11
0x14004900d  pop     r15
0x14004900f  pop     r14
0x140049011  pop     r13
0x140049013  pop     r12
0x140049015  pop     rdi
0x140049016  retn
0x14005a1d5  push    rbx
0x14005a1d7  push    rbp
0x14005a1d8  push    rsi
0x14005a1d9  push    rdi
0x14005a1da  sub     rsp, 48h
0x14005a1de  mov     rbp, rdx
0x14005a1e1  mov     rdi, [rbp+88h]
0x14005a1e8  test    cl, cl
0x14005a1ea  jnz     short loc_14005A1FC
0x14005a1ec  mov     eax, [rdi+30h]
0x14005a1ef  test    al, 10h
0x14005a1f1  jnz     short loc_14005A1FC
0x14005a1f3  xor     sil, sil
0x14005a1f6  or      dword ptr [rdi+30h], 40h
0x14005a1fa  jmp     short loc_14005A1FF
0x14005a1fc  mov     sil, 1
0x14005a1ff  xor     ebx, ebx
0x14005a201  mov     [rbp+44h], ebx
0x14005a204  mov     r8d, ebx
0x14005a207  mov     rdx, rdi
0x14005a20a  call    UdfUnpinCurrentBitmapPage
0x14005a20f  mov     eax, ebx
0x14005a211  imul    rcx, rax, 0C8h
0x14005a218  add     rcx, 228h
0x14005a21f  add     rcx, rdi; Resource
0x14005a222  call    cs:__imp_ExReleaseResourceLite
0x14005a229  nop     dword ptr [rax+rax+00h]
0x14005a22e  test    sil, sil
0x14005a231  jz      short loc_14005A253
0x14005a233  mov     eax, ebx
0x14005a235  imul    rcx, rax, 0C8h
0x14005a23c  add     rcx, 228h
0x14005a243  add     rcx, rdi; Resource
0x14005a246  call    cs:__imp_ExDeleteResourceLite
0x14005a24d  nop     dword ptr [rax+rax+00h]
0x14005a252  nop
0x14005a253  inc     ebx
0x14005a255  cmp     ebx, [rbp+48h]
0x14005a258  jbe     short loc_14005A204
0x14005a25a  mov     [rbp+44h], ebx
0x14005a25d  add     rsp, 48h
0x14005a261  pop     rdi
0x14005a262  pop     rsi
0x14005a263  pop     rbp
0x14005a264  pop     rbx
0x14005a265  retn
```
