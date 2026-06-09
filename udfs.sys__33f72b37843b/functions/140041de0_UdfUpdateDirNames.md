# UdfUpdateDirNames

- ea: `0x140041de0`
- end: `0x14004259e`
- name: `UdfUpdateDirNames`
- size: `1982`
- prototype: `int __fastcall(__int64, __int64, __int64, char)`
- caller_count: `8`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x140031144`
- `0x14003269c`
- `0x140033548`
- `0x140034450`
- `0x14003803c`
- `0x140040820`
- `0x1400413f0`
- `0x140041900`

## callees

- `0x14000a7f8`
- `0x14000ca10`
- `0x14000cad4`
- `0x140012034`
- `0x14001274c`
- `0x140013758`
- `0x14001c080`
- `0x1400401a0`
- `0x140040d34`
- `0x140041de0`
- `0x140055cd0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400420c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400420c7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004210c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004210c`
- `ntoskrnl!ExRaiseStatus` at `0x140041e3b`
- `ntoskrnl!ExRaiseStatus` at `0x140041e3b`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140041fa4`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140041fa4`
- `ntoskrnl!FsRtlLegalAnsiCharacterArray` at `0x1400422f3`

## pseudocode

```c
int __fastcall UdfUpdateDirNames(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  __int64 v4; // r10
  char v6; // r14
  int v9; // ecx
  __int16 v10; // ax
  __int16 v11; // ax
  int *v12; // rax
  unsigned __int16 v13; // r13
  unsigned __int8 v14; // si
  unsigned __int16 v15; // bx
  unsigned __int8 *v16; // r8
  char v17; // r10
  unsigned __int8 v18; // r9
  unsigned int v19; // edx
  __int64 v20; // rcx
  unsigned int v21; // eax
  __int16 v22; // ax
  unsigned __int8 *v23; // rdi
  __int64 v24; // rcx
  int *v25; // r9
  unsigned __int8 v26; // al
  unsigned __int16 v27; // r14
  int v28; // eax
  void *v29; // rcx
  char *PoolWithTag; // rax
  char *v31; // r14
  char *v32; // rcx
  __int16 v33; // ax
  __int16 v34; // ax
  __int64 v35; // rax
  int v36; // ebx
  _BYTE *v37; // r12
  char v38; // bl
  char *v39; // r11
  __int64 v40; // r9
  unsigned __int16 v41; // r10
  char *v42; // r9
  char v43; // cl
  char v44; // al
  __int64 v45; // rcx
  unsigned __int16 v47; // [rsp+88h] [rbp+10h]
  char v48; // [rsp+90h] [rbp+18h]

  v48 = a3;
  v4 = *(_QWORD *)(a2 + 32);
  *(_WORD *)(a2 + 112) = 0;
  v6 = a3;
  if ( !v4 )
  {
    v33 = UdfUnicodeDirectoryNames;
    *(_WORD *)(a2 + 64) = UdfUnicodeDirectoryNames;
    *(_WORD *)(a2 + 80) = v33;
    *(_WORD *)(a2 + 96) = v33;
    v34 = word_14002504A;
    *(_WORD *)(a2 + 66) = word_14002504A;
    *(_WORD *)(a2 + 82) = v34;
    *(_WORD *)(a2 + 98) = v34;
    v12 = off_140025050;
    *(_QWORD *)(a2 + 72) = off_140025050;
    *(_QWORD *)(a2 + 88) = v12;
    *(_QWORD *)(a2 + 104) = v12;
    LODWORD(v12) = 0;
    *(_WORD *)(a2 + 114) = 0;
    *(_QWORD *)(a2 + 120) = 0;
    return (int)v12;
  }
  v9 = *(_DWORD *)(a2 + 56);
  if ( (*(_BYTE *)(v4 + 18) & 8) != 0 )
  {
    if ( (v9 & 1) == 0 && !*(_BYTE *)(v4 + 19) )
    {
      *(_DWORD *)(a2 + 56) = v9 | 2;
      v10 = word_140025058;
      *(_WORD *)(a2 + 64) = word_140025058;
      *(_WORD *)(a2 + 80) = v10;
      *(_WORD *)(a2 + 96) = v10;
      v11 = word_14002505A;
      *(_WORD *)(a2 + 66) = word_14002505A;
      *(_WORD *)(a2 + 82) = v11;
      *(_WORD *)(a2 + 98) = v11;
      v12 = (int *)off_140025060;
      *(_QWORD *)(a2 + 72) = off_140025060;
      *(_QWORD *)(a2 + 88) = v12;
      *(_QWORD *)(a2 + 104) = v12;
      LODWORD(v12) = 0;
      *(_WORD *)(a2 + 114) = 0;
      *(_QWORD *)(a2 + 120) = 0;
      return (int)v12;
    }
LABEL_4:
    *(_DWORD *)(a1 + 24) = -1073741566;
    ExRaiseStatus(-1073741566);
  }
  if ( (v9 & 2) == 0 )
    goto LABEL_4;
  v35 = *(unsigned __int16 *)(v4 + 36);
  *(_DWORD *)(a2 + 56) = v9 | 1;
  v36 = *(unsigned __int8 *)(v4 + 19);
  if ( !(_BYTE)v36 )
    goto LABEL_4;
  v37 = (_BYTE *)(v35 + v4 + 38);
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000) != 0 )
  {
    WPP_SF_qDDD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      &WPP_GLOBAL_Control,
      a3,
      v35 + v4 + 38,
      v36,
      v36,
      *(unsigned __int8 *)(v4 + 19));
  }
  if ( (unsigned __int8)v36 <= 1u || *v37 != 8 && (*v37 != 16 || (v36 & 1) == 0) )
    goto LABEL_4;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 13, WPP_9347fa571a1230f8ec97dda486d24b3c_Traceguids);
  }
  v23 = v37 + 1;
  v38 = *v37;
  v39 = v37 + 1;
  v40 = *(unsigned __int8 *)(*(_QWORD *)(a2 + 32) + 19LL);
  v13 = (v40 - 1) * (16 / (char)*v37);
  if ( v13 < 0x18u )
    v13 = 24;
  v41 = 0;
  v42 = &v37[v40];
  while ( v39 < v42 )
  {
    if ( v38 == 16 )
    {
      v43 = v39[1];
      LOBYTE(v47) = v43;
      HIBYTE(v47) = *v39;
      v41 = v47;
    }
    else
    {
      v43 = *v39;
      v41 = *v39;
    }
    v44 = 20;
    if ( !a4 )
      v44 = 2;
    if ( v41 < 0xFFu && v43 >= 0 && ((unsigned __int8)v44 & *((_BYTE *)FsRtlLegalAnsiCharacterArray + v41)) == 0 )
    {
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000) != 0 )
      {
        WPP_SF_Dq(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          10,
          WPP_9347fa571a1230f8ec97dda486d24b3c_Traceguids,
          v41,
          v39);
      }
      goto LABEL_9;
    }
    v39 += (v38 == 16) + 1;
  }
  if ( v41 == 46 || v41 == 32 )
  {
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000) != 0 )
    {
      WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 11, WPP_9347fa571a1230f8ec97dda486d24b3c_Traceguids);
    }
    goto LABEL_9;
  }
  if ( (v13 & 0xFFFEu) > 0x1FE )
  {
LABEL_9:
    v13 += 10;
    v14 = 1;
    v15 = 3 * (v13 + 8);
    goto LABEL_10;
  }
  v15 = 2 * (v13 + 12);
  *(_QWORD *)(a2 + 104) = *(_QWORD *)(a2 + 72);
  v14 = 0;
LABEL_10:
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x100) != 0 )
  {
    v25 = (int *)"Ci ";
    if ( !v14 )
      v25 = &dword_1400205C4;
    WPP_SF_sddd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      v13,
      v15,
      (_DWORD)v25,
      v15,
      v13,
      *(_WORD *)(a2 + 136));
  }
  if ( v13 > *(_WORD *)(a2 + 66) || v14 && *(_QWORD *)(a2 + 72) == *(_QWORD *)(a2 + 104) || !*(_WORD *)(a2 + 114) )
  {
    v27 = 0;
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x100) != 0 )
    {
      WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 11, WPP_7471fb31cf8e3b538dce4a4ba670d992_Traceguids);
    }
    *(_WORD *)(a2 + 114) = 0;
    *(_QWORD *)(a2 + 120) = 0;
    v28 = *(unsigned __int16 *)(a2 + 136);
    if ( (unsigned __int16)v28 >= v15 )
      v27 = ((v28 - 24) / (v14 + 2)) & 0xFFFE;
    if ( v27 >= v13 )
    {
      *(_WORD *)(a2 + 66) = v27;
      *(_WORD *)(a2 + 82) = v27;
      *(_WORD *)(a2 + 98) = v27;
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x100) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          12,
          WPP_7471fb31cf8e3b538dce4a4ba670d992_Traceguids);
      }
      v31 = *(char **)(a2 + 128);
    }
    else
    {
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x100) != 0 )
      {
        WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 13, WPP_7471fb31cf8e3b538dce4a4ba670d992_Traceguids);
      }
      if ( (*(_DWORD *)(a2 + 56) & 0x40) != 0 )
      {
        v29 = *(void **)(a2 + 128);
        if ( v29 )
        {
          ExFreePoolWithTag(v29, 0);
          *(_QWORD *)(a2 + 128) = 0;
        }
        *(_DWORD *)(a2 + 56) &= ~0x40u;
        *(_WORD *)(a2 + 136) = 0;
      }
      *(_WORD *)(a2 + 66) = v13;
      *(_WORD *)(a2 + 82) = v13;
      *(_WORD *)(a2 + 98) = v13;
      PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1041, v15, 0x4E666455u);
      v31 = PoolWithTag;
      if ( !ExPoolZeroingNativelySupported && PoolWithTag )
        memset(PoolWithTag, 0, v15);
      *(_DWORD *)(a2 + 56) |= 0x40u;
      *(_QWORD *)(a2 + 128) = v31;
      *(_WORD *)(a2 + 136) = v15;
    }
    v32 = &v31[*(unsigned __int16 *)(a2 + 66)];
    *(_QWORD *)(a2 + 88) = v31;
    *(_QWORD *)(a2 + 104) = v31;
    *(_QWORD *)(a2 + 72) = v31;
    *(_QWORD *)(a2 + 88) = v32;
    if ( v14 )
    {
      v32 += *(unsigned __int16 *)(a2 + 82);
      *(_QWORD *)(a2 + 104) = v32;
    }
    v6 = v48;
    *(_QWORD *)(a2 + 120) = &v32[*(unsigned __int16 *)(a2 + 98)];
    *(_WORD *)(a2 + 114) = 24;
  }
  v16 = *(unsigned __int8 **)(a2 + 104);
  v17 = *v37;
  v18 = *(_BYTE *)(*(_QWORD *)(a2 + 32) + 19LL);
  if ( !v18 )
    v18 = *(v37 - 1);
  v19 = *(unsigned __int16 *)(a2 + 98);
  v20 = (unsigned __int16)((v18 - 1) * (16 / (char)*v37));
  if ( (unsigned __int16)v19 >= (unsigned __int16)v20 )
    v19 = (unsigned __int16)((v18 - 1) * (16 / (char)*v37));
  LOWORD(v21) = 0;
  *(_WORD *)(a2 + 96) = 0;
  if ( v17 == 16 )
  {
    if ( v19 )
    {
      do
      {
        v26 = v23[1];
        v23 += 2;
        *v16 = v26;
        v16 += 2;
        *(v16 - 1) = *(v23 - 2);
        *(_WORD *)(a2 + 96) += 2;
        v21 = *(unsigned __int16 *)(a2 + 96);
      }
      while ( v19 > v21 );
    }
  }
  else if ( v19 )
  {
    do
    {
      v22 = *v23++;
      *(_WORD *)v16 = v22;
      v16 += 2;
      *(_WORD *)(a2 + 96) += 2;
      v21 = *(unsigned __int16 *)(a2 + 96);
    }
    while ( v19 > v21 );
  }
  if ( v14 )
    UdfRenderNameToLegalUnicode(v20, a2 + 96, a2 + 64);
  else
    *(_WORD *)(a2 + 64) = v21;
  LODWORD(v12) = RtlUpcaseUnicodeString((PUNICODE_STRING)(a2 + 80), (PCUNICODE_STRING)(a2 + 64), 0);
  if ( v6 )
  {
    LODWORD(v12) = UdfIs8dot3Name(v24, a2 + 64);
    if ( !(_BYTE)v12 )
    {
      UdfGenerate8dot3Name(v45, a2 + 96, 0, a2 + 112);
      v12 = &WPP_GLOBAL_Control;
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x100) != 0 )
      {
        LODWORD(v12) = WPP_SF_Z(
                         *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                         14,
                         WPP_7471fb31cf8e3b538dce4a4ba670d992_Traceguids,
                         a2 + 112);
      }
    }
  }
  return (int)v12;
}

```

## disassembly

```asm
0x140041de0  mov     [rsp+arg_10], r8b
0x140041de5  push    rbp
0x140041de6  push    rsi
0x140041de7  push    rdi
0x140041de8  push    r14
0x140041dea  sub     rsp, 58h
0x140041dee  mov     r10, [rdx+20h]
0x140041df2  xor     eax, eax
0x140041df4  mov     [rdx+70h], ax
0x140041df8  movzx   esi, r9b
0x140041dfc  movzx   r14d, r8b
0x140041e00  mov     rbp, rdx
0x140041e03  mov     rdi, rcx
0x140041e06  test    r10, r10
0x140041e09  jz      loc_14004218B
0x140041e0f  test    byte ptr [r10+12h], 8
0x140041e14  mov     ecx, [rdx+38h]
0x140041e17  mov     [rsp+78h+arg_0], rbx
0x140041e1f  mov     [rsp+78h+var_28], r12
0x140041e24  jnz     short loc_140041E48
0x140041e26  test    cl, 2
0x140041e29  jnz     loc_1400421D9
0x140041e2f  mov     ecx, 0C0000102h; Status
0x140041e34  mov     dword ptr [rdi+18h], 0C0000102h
0x140041e3b  call    cs:__imp_ExRaiseStatus
0x140041e48  test    cl, 1
0x140041e4b  jnz     short loc_140041E2F
0x140041e4d  cmp     [r10+13h], al
0x140041e51  jnz     short loc_140041E2F
0x140041e53  or      ecx, 2
0x140041e56  mov     [rdx+38h], ecx
0x140041e59  movzx   eax, cs:word_140025058
0x140041e60  mov     [rdx+40h], ax
0x140041e64  mov     [rdx+50h], ax
0x140041e68  mov     [rdx+60h], ax
0x140041e6c  movzx   eax, cs:word_14002505A
0x140041e73  mov     [rdx+42h], ax
0x140041e77  mov     [rdx+52h], ax
0x140041e7b  mov     [rdx+62h], ax
0x140041e7f  mov     rax, cs:off_140025060
0x140041e86  mov     [rdx+48h], rax
0x140041e8a  mov     [rdx+58h], rax
0x140041e8e  mov     [rdx+68h], rax
0x140041e92  xor     eax, eax
0x140041e94  mov     [rdx+72h], ax
0x140041e98  mov     [rdx+78h], rax
0x140041e9c  jmp     loc_140041FB9
0x140041ea1  mov     rcx, cs:WPP_GLOBAL_Control
0x140041ea8  lea     rdx, WPP_GLOBAL_Control
0x140041eaf  cmp     rcx, rdx
0x140041eb2  jnz     loc_1400423F9
0x140041eb8  mov     r15d, 0FFFEh
0x140041ebe  add     r13w, 0Ah
0x140041ec3  mov     sil, 1
0x140041ec6  lea     ebx, [r13+8]
0x140041eca  movzx   eax, bx
0x140041ecd  add     ax, ax
0x140041ed0  add     bx, ax
0x140041ed3  mov     rcx, cs:WPP_GLOBAL_Control
0x140041eda  cmp     rcx, rdx
0x140041edd  jnz     loc_140041FD1
0x140041ee3  cmp     r13w, [rbp+42h]
0x140041ee8  ja      loc_140042059
0x140041eee  test    sil, sil
0x140041ef1  jnz     loc_14004246B
0x140041ef7  xor     eax, eax
0x140041ef9  cmp     ax, [rbp+72h]
0x140041efd  jz      loc_140042059
0x140041f03  mov     rax, [rbp+20h]
0x140041f07  mov     r8, [rbp+68h]
0x140041f0b  movsx   r10d, byte ptr [r12]
0x140041f10  mov     r15, [rsp+78h+var_38]
0x140041f15  movzx   r9d, byte ptr [rax+13h]
0x140041f1a  mov     r13, [rsp+78h+var_30]
0x140041f1f  test    r9b, r9b
0x140041f22  jz      loc_140042530
0x140041f28  mov     eax, 10h
0x140041f2d  movzx   ecx, r9b
0x140041f31  cdq
0x140041f32  dec     cx
0x140041f35  idiv    r10d
0x140041f38  movzx   edx, cx
0x140041f3b  movzx   eax, ax
0x140041f3e  imul    eax, edx
0x140041f41  movzx   edx, word ptr [rbp+62h]
0x140041f45  movzx   ecx, ax
0x140041f48  cmp     dx, cx
0x140041f4b  cmovnb  edx, ecx
0x140041f4e  xor     eax, eax
0x140041f50  mov     [rbp+60h], ax
0x140041f54  cmp     r10b, 10h
0x140041f58  jz      loc_140042024
0x140041f5e  test    edx, edx
0x140041f60  jz      short loc_140041F8C
0x140041f62  nop     dword ptr [rax+00h]
0x140041f66  nop     word ptr [rax+rax+00000000h]
0x140041f70  movzx   eax, byte ptr [rdi]
0x140041f73  lea     rdi, [rdi+1]
0x140041f77  mov     [r8], ax
0x140041f7b  lea     r8, [r8+2]
0x140041f7f  add     word ptr [rbp+60h], 2
0x140041f84  movzx   eax, word ptr [rbp+60h]
0x140041f88  cmp     edx, eax
0x140041f8a  ja      short loc_140041F70
0x140041f8c  test    sil, sil
0x140041f8f  jnz     loc_140042179
0x140041f95  mov     [rbp+40h], ax
0x140041f99  lea     rcx, [rbp+50h]; DestinationString
0x140041f9d  xor     r8d, r8d; AllocateDestinationString
0x140041fa0  lea     rdx, [rbp+40h]; SourceString
0x140041fa4  call    cs:__imp_RtlUpcaseUnicodeString
0x140041fab  nop     dword ptr [rax+rax+00h]
0x140041fb0  test    r14b, r14b
0x140041fb3  jnz     loc_14004253B
0x140041fb9  mov     rbx, [rsp+78h+arg_0]
0x140041fc1  mov     r12, [rsp+78h+var_28]
0x140041fc6  add     rsp, 58h
0x140041fca  pop     r14
0x140041fcc  pop     rdi
0x140041fcd  pop     rsi
0x140041fce  pop     rbp
0x140041fcf  retn
0x140041fd1  test    dword ptr [rcx+2Ch], 100h
0x140041fd8  jz      loc_140041EE3
0x140041fde  movzx   eax, word ptr [rbp+88h]
0x140041fe5  lea     r10, dword_1400205C4
0x140041fec  mov     rcx, [rcx+18h]
0x140041ff0  lea     r9, aCi; "Ci "
0x140041ff7  mov     [rsp+78h+var_48], eax
0x140041ffb  test    sil, sil
0x140041ffe  movzx   edx, r13w
0x140042002  movzx   r8d, bx
0x140042006  cmovz   r9, r10
0x14004200a  mov     [rsp+78h+var_50], edx
0x14004200e  mov     dword ptr [rsp+78h+var_58], r8d
0x140042013  call    WPP_SF_sddd
0x140042018  lea     rdx, WPP_GLOBAL_Control
0x14004201f  jmp     loc_140041EE3
0x140042024  test    edx, edx
0x140042026  jz      loc_140041F8C
0x14004202c  nop     dword ptr [rax+00h]
0x140042030  movzx   eax, byte ptr [rdi+1]
0x140042034  lea     rdi, [rdi+2]
0x140042038  mov     [r8], al
0x14004203b  lea     r8, [r8+2]
0x14004203f  movzx   eax, byte ptr [rdi-2]
0x140042043  mov     [r8-1], al
0x140042047  add     word ptr [rbp+60h], 2
0x14004204c  movzx   eax, word ptr [rbp+60h]
0x140042050  cmp     edx, eax
0x140042052  ja      short loc_140042030
0x140042054  jmp     loc_140041F8C
0x140042059  xor     r14d, r14d
0x14004205c  mov     rcx, cs:WPP_GLOBAL_Control
0x140042063  cmp     rcx, rdx
0x140042066  jz      short loc_140042075
0x140042068  test    dword ptr [rcx+2Ch], 100h
0x14004206f  jnz     loc_14004247E
0x140042075  xor     eax, eax
0x140042077  mov     [rbp+72h], ax
0x14004207b  mov     [rbp+78h], rax
0x14004207f  movzx   eax, word ptr [rbp+88h]
0x140042086  cmp     ax, bx
0x140042089  jnb     loc_14004249F
0x14004208f  cmp     r14w, r13w
0x140042093  jnb     loc_14004238A
0x140042099  mov     rcx, cs:WPP_GLOBAL_Control
0x1400420a0  cmp     rcx, rdx
0x1400420a3  jz      short loc_1400420B2
0x1400420a5  test    dword ptr [rcx+2Ch], 100h
0x1400420ac  jnz     loc_1400424EB
0x1400420b2  mov     eax, [rbp+38h]
0x1400420b5  test    al, 40h
0x1400420b7  jz      short loc_1400420EB
0x1400420b9  mov     rcx, [rbp+80h]; P
0x1400420c0  test    rcx, rcx
0x1400420c3  jz      short loc_1400420DE
0x1400420c5  xor     edx, edx; Tag
0x1400420c7  call    cs:__imp_ExFreePoolWithTag
0x1400420ce  nop     dword ptr [rax+rax+00h]
0x1400420d3  mov     qword ptr [rbp+80h], 0
0x1400420de  xor     eax, eax
0x1400420e0  and     dword ptr [rbp+38h], 0FFFFFFBFh
0x1400420e4  mov     [rbp+88h], ax
0x1400420eb  movzx   r15d, bx
0x1400420ef  mov     r8d, 4E666455h; Tag
0x1400420f5  mov     edx, r15d; NumberOfBytes
0x1400420f8  mov     [rbp+42h], r13w
0x1400420fd  mov     ecx, 411h; PoolType
0x140042102  mov     [rbp+52h], r13w
0x140042107  mov     [rbp+62h], r13w
0x14004210c  call    cs:__imp_ExAllocatePoolWithTag
0x140042113  nop     dword ptr [rax+rax+00h]
0x140042118  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14004211f  mov     r14, rax
0x140042122  jz      loc_140042505
0x140042128  or      dword ptr [rbp+38h], 40h
0x14004212c  mov     [rbp+80h], r14
0x140042133  mov     [rbp+88h], bx
0x14004213a  movzx   ecx, word ptr [rbp+42h]
0x14004213e  add     rcx, r14
0x140042141  mov     [rbp+58h], r14
0x140042145  mov     [rbp+68h], r14
0x140042149  mov     [rbp+48h], r14
0x14004214d  mov     [rbp+58h], rcx
0x140042151  test    sil, sil
0x140042154  jnz     loc_140042520
0x14004215a  movzx   eax, word ptr [rbp+62h]
0x14004215e  movzx   r14d, [rsp+78h+arg_10]
0x140042167  add     rax, rcx
0x14004216a  mov     [rbp+78h], rax
0x14004216e  mov     word ptr [rbp+72h], 18h
0x140042174  jmp     loc_140041F03
0x140042179  lea     r8, [rbp+40h]
0x14004217d  lea     rdx, [rbp+60h]
0x140042181  call    UdfRenderNameToLegalUnicode
0x140042186  jmp     loc_140041F99
0x14004218b  movzx   eax, cs:UdfUnicodeDirectoryNames
0x140042192  mov     [rdx+40h], ax
0x140042196  mov     [rdx+50h], ax
0x14004219a  mov     [rdx+60h], ax
0x14004219e  movzx   eax, cs:word_14002504A
0x1400421a5  mov     [rdx+42h], ax
0x1400421a9  mov     [rdx+52h], ax
0x1400421ad  mov     [rdx+62h], ax
0x1400421b1  mov     rax, cs:off_140025050
0x1400421b8  mov     [rdx+48h], rax
0x1400421bc  mov     [rdx+58h], rax
0x1400421c0  mov     [rdx+68h], rax
0x1400421c4  xor     eax, eax
0x1400421c6  mov     [rdx+72h], ax
0x1400421ca  mov     [rdx+78h], rax
0x1400421ce  add     rsp, 58h
0x1400421d2  pop     r14
0x1400421d4  pop     rdi
0x1400421d5  pop     rsi
0x1400421d6  pop     rbp
0x1400421d7  retn
0x1400421d9  movzx   eax, word ptr [r10+24h]
0x1400421de  or      ecx, 1
0x1400421e1  mov     [rdx+38h], ecx
0x1400421e4  movzx   ebx, byte ptr [r10+13h]
0x1400421e9  test    bl, bl
0x1400421eb  jz      loc_140041E2F
0x1400421f1  lea     r12, [r10+26h]
0x1400421f5  add     r12, rax
0x1400421f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400421ff  lea     rdx, WPP_GLOBAL_Control
0x140042206  cmp     rcx, rdx
0x140042209  jz      short loc_140042218
0x14004220b  test    dword ptr [rcx+2Ch], 4000h
0x140042212  jnz     loc_1400423B5
0x140042218  cmp     bl, 1
0x14004221b  jbe     loc_140041E2F
0x140042221  movzx   eax, byte ptr [r12]
0x140042226  cmp     al, 8
0x140042228  jz      short loc_14004223B
0x14004222a  cmp     al, 10h
0x14004222c  jnz     loc_140041E2F
0x140042232  test    bl, 1
0x140042235  jz      loc_140041E2F
0x14004223b  mov     rcx, cs:WPP_GLOBAL_Control
0x140042242  mov     [rsp+78h+var_30], r13
0x140042247  mov     [rsp+78h+var_38], r15
0x14004224c  cmp     rcx, rdx
0x14004224f  jz      short loc_14004225E
0x140042251  test    dword ptr [rcx+2Ch], 4000h
0x140042258  jnz     loc_1400423D9
0x14004225e  mov     rax, [rbp+20h]
0x140042262  lea     rdi, [r12+1]
0x140042267  movsx   ebx, byte ptr [r12]
0x14004226c  mov     r11, rdi
0x14004226f  mov     r15d, 2
0x140042275  movzx   r9d, byte ptr [rax+13h]
0x14004227a  mov     eax, 10h
0x14004227f  cdq
0x140042280  idiv    ebx
0x140042282  mov     edx, 0FFh
0x140042287  movzx   r13d, ax
0x14004228b  lea     eax, [r9-1]
0x14004228f  movzx   ecx, ax
0x140042292  mov     eax, 18h
0x140042297  imul    r13d, ecx
0x14004229b  cmp     ax, r13w
0x14004229f  cmova   r13w, ax
0x1400422a4  xor     r10d, r10d
0x1400422a7  mov     [rsp+78h+arg_8], r10w
0x1400422b0  add     r9, r12
0x1400422b3  cmp     r11, r9
0x1400422b6  jnb     short loc_140042332
0x1400422b8  cmp     bl, 10h
0x1400422bb  jnz     short loc_140042320
0x1400422bd  movzx   ecx, byte ptr [r11+1]
0x1400422c2  movzx   eax, byte ptr [r11]
0x1400422c6  mov     byte ptr [rsp+78h+arg_8], cl
0x1400422cd  mov     byte ptr [rsp+78h+arg_8+1], al
0x1400422d4  movzx   r10d, [rsp+78h+arg_8]
0x1400422dd  test    sil, sil
0x1400422e0  mov     eax, 14h
0x1400422e5  cmovz   eax, r15d
  ... truncated ...
```
