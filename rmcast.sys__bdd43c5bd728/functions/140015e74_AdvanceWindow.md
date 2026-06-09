# AdvanceWindow

- ea: `0x140015e74`
- end: `0x1400163dd`
- name: `AdvanceWindow`
- size: `1385`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x14001a334`

## callees

- `0x140015e74`
- `0x14001b078`
- `0x14001b118`
- `0x14001b180`
- `0x14001b214`
- `0x14001b52c`
- `0x14001b584`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400160b5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001623d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400160b5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001623d`

## pseudocode

```c
__int64 __fastcall AdvanceWindow(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  unsigned __int64 v5; // rsi
  unsigned __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r11
  unsigned __int64 v9; // r9
  unsigned __int64 v10; // rsi
  _QWORD *v11; // rax
  int v12; // ebp
  unsigned int v13; // r10d
  int v14; // edi
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  int v17; // ecx
  unsigned int v18; // r15d
  unsigned __int64 v19; // rcx
  unsigned int v20; // r12d
  __int64 v21; // rax
  unsigned __int64 v22; // r14
  _DWORD *v23; // rbp
  unsigned __int64 v24; // r8
  unsigned __int64 v25; // r13
  int v26; // edx
  unsigned __int64 v27; // rax
  unsigned __int64 *v28; // rcx
  void *v29; // rdx
  int v30; // edx
  int v31; // ecx
  int v32; // edx
  __int64 v33; // rcx
  int v34; // eax
  __int64 v35; // rax
  __int64 v36; // r14
  int v37; // r9d
  __int64 v38; // r11
  int v39; // edx
  int v40; // ecx
  int v41; // r10d
  int v42; // ecx
  int v43; // eax
  int v44; // edi
  int v45; // edx
  __int64 v46; // rcx
  _QWORD *v47; // rax
  __int64 v49; // rdx
  unsigned int v50; // esi
  unsigned int v51; // edi
  __int64 v52; // rcx
  unsigned __int64 v53; // rax
  unsigned __int64 v54; // rcx
  int v55; // ecx
  unsigned __int64 v57; // [rsp+98h] [rbp+10h]

  v3 = *(_QWORD *)(a1 + 40);
  v5 = *(_QWORD *)(v3 + 344);
  v6 = *(_QWORD *)(v3 + 296);
  if ( v6 > v5 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_ii(WPP_GLOBAL_Control->AttachedDevice, v6, a3, *(_QWORD *)(v3 + 296), *(_QWORD *)(v3 + 344));
    v6 = *(_QWORD *)(v3 + 296);
    v5 = v6 + *(_QWORD *)(v3 + 320);
    *(_QWORD *)(v3 + 344) = v5;
  }
  v7 = *(_QWORD *)(v3 + 328);
  v8 = *(_QWORD *)(v3 + 320);
  v9 = *(_QWORD *)(v3 + 352);
  v10 = v5 - v7 - v8;
  if ( v10 < v9 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      WPP_SF_ddiii(
        WPP_GLOBAL_Control->AttachedDevice,
        v6,
        v7,
        *(unsigned int *)(v3 + 160),
        *(_DWORD *)(v3 + 152) - 1,
        v6,
        v10,
        *(_QWORD *)(v3 + 352));
    return 0;
  }
  v11 = *(_QWORD **)(v3 + 264);
  v12 = *(_DWORD *)(v3 + 152);
  v13 = *(_DWORD *)(v3 + 160);
  v14 = v12 & -*(unsigned __int8 *)(a1 + 160);
  v15 = (_QWORD *)*v11;
  v16 = v14 - v13;
  if ( (_QWORD *)*v11 != v11 )
  {
    if ( v15 )
    {
      v17 = *((_DWORD *)v15 + 4);
      if ( v17 - v14 < 0 )
        v14 = v17;
    }
  }
  v18 = v14 - v13;
  if ( (*(_DWORD *)(*(_QWORD *)(v3 + 32) + 56LL) & 2) != 0 && (*(_DWORD *)(a1 + 32) & 0x1000) == 0 )
  {
    v19 = *(_QWORD *)(v3 + 96) >> 1;
    if ( (unsigned int)v16 <= v19 )
    {
LABEL_20:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        WPP_SF_ddidii(
          WPP_GLOBAL_Control->AttachedDevice,
          69,
          (unsigned int)(v12 - 1),
          v13,
          v12 - 1,
          *(_QWORD *)(v3 + 296),
          0,
          v10,
          *(_QWORD *)(v3 + 352));
      return 0;
    }
    if ( (unsigned int)v16 - v18 < v19 )
    {
      v18 = v16 - v19;
      v14 = v16 - v19 + v13;
    }
  }
  if ( !v18 )
    goto LABEL_20;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_iiii(WPP_GLOBAL_Control->AttachedDevice, v16, v7, v10, v9, v8, *(_QWORD *)(v3 + 328));
  v20 = 0;
  v21 = v3 + 216;
  v22 = *(_QWORD *)(v3 + 216);
  v23 = 0;
  v24 = 0;
  v25 = v10;
  while ( v22 != v21 )
  {
    v24 = v22;
    v25 = *(_QWORD *)(v22 + 48);
    v57 = v22;
    if ( *(_DWORD *)(v22 + 136) || v25 >= v10 || (v26 = *(_DWORD *)(v22 + 88), v26 - v14 >= 0) )
    {
      v30 = *(_DWORD *)(v22 + 88);
      v31 = *(_DWORD *)(v3 + 160) - v30;
      v14 = v30;
      if ( v31 > 0 )
        v14 = *(_DWORD *)(v3 + 160);
      v32 = v30 - *(_DWORD *)(v3 + 160);
      v18 = 0;
      if ( v31 <= 0 )
        v18 = v32;
      v20 = v18;
      break;
    }
    if ( *(_DWORD *)(v22 + 92) - v14 >= 0 )
    {
      v20 = v26 - *(_DWORD *)(v3 + 160);
      v23 = (_DWORD *)v22;
      if ( *(_DWORD *)(v3 + 160) - v26 > 0 )
        v20 = 0;
      break;
    }
    v27 = *(_QWORD *)v22;
    if ( *(_QWORD *)(*(_QWORD *)v22 + 8LL) != v22 )
      goto LABEL_71;
    v28 = *(unsigned __int64 **)(v22 + 8);
    if ( *v28 != v22 )
      goto LABEL_71;
    *v28 = v27;
    v29 = (void *)v22;
    *(_QWORD *)(v27 + 8) = v28;
    v22 = v27;
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v3 + 576), v29);
    v24 = v57;
    v21 = v3 + 216;
  }
  if ( !v24 )
  {
    v33 = *(_QWORD *)(v3 + 232);
    if ( v33 != v3 + 232 )
    {
      if ( *(_DWORD *)(v33 + 136) )
        goto LABEL_66;
      if ( *(_DWORD *)(v33 + 140) )
        goto LABEL_66;
      v34 = *(_DWORD *)(v33 + 128);
      if ( !v34 || *(_DWORD *)(v33 + 108) != v34 || *(_QWORD *)(v33 + 48) > v10 )
        goto LABEL_66;
      v23 = *(_DWORD **)(v3 + 232);
    }
  }
  if ( v23 )
  {
    v35 = *(_QWORD *)(v3 + 32);
    v36 = *((_QWORD *)v23 + 6);
    v37 = *(_DWORD *)(v35 + 248);
    v38 = *(_QWORD *)(v35 + 272);
    v39 = v23[22];
    v40 = v23[23];
    v24 = 20 * v38 * (v10 - v36) / (unsigned int)(8 * v37);
    v41 = v39 - v40;
    if ( v39 - v40 + (int)v24 <= 0 )
      v42 = 20 * v38 * (v10 - v36) / (unsigned int)(8 * v37);
    else
      v42 = v40 - v39 + 1;
    v43 = v39 - v14;
    v44 = v14 - v39;
    if ( v42 + v43 <= 0 )
      v44 = v42;
    v45 = v39 - *(_DWORD *)(v3 + 160);
    if ( v45 + v44 > 0 )
    {
      if ( v45 < 0 )
        v44 += v45;
    }
    else
    {
      v44 = 0;
    }
    v20 += v44;
    v25 = v36 + (unsigned int)(8 * v44 * v37) / (unsigned __int64)(20 * v38);
    if ( !v23[26] && v41 + v44 > 0 )
    {
      v46 = *(_QWORD *)v23;
      if ( *(_DWORD **)(*(_QWORD *)v23 + 8LL) != v23 || (v47 = (_QWORD *)*((_QWORD *)v23 + 1), (_DWORD *)*v47 != v23) )
LABEL_71:
        __fastfail(3u);
      *v47 = v46;
      *(_QWORD *)(v46 + 8) = v47;
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v3 + 576), v23);
    }
  }
LABEL_66:
  if ( !v20 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      WPP_SF_ddidii(
        WPP_GLOBAL_Control->AttachedDevice,
        71,
        (unsigned int)(*(_DWORD *)(v3 + 152) - 1),
        *(unsigned int *)(v3 + 160),
        *(_DWORD *)(v3 + 152) - 1,
        *(_QWORD *)(v3 + 296),
        v18,
        v10,
        *(_QWORD *)(v3 + 352));
    return 0;
  }
  v49 = *(unsigned int *)(v3 + 160);
  v50 = v18;
  if ( v20 <= v18 )
    v50 = v20;
  v51 = v49 + v50;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_dddddii(
      WPP_GLOBAL_Control->AttachedDevice,
      v49,
      v24,
      *(unsigned int *)(v3 + 120),
      v50,
      v18,
      v49,
      v49 + v50,
      *(_QWORD *)(v3 + 352),
      v25);
  *(_DWORD *)(v3 + 116) += v50;
  v52 = *(_DWORD *)(v3 + 108) * v50;
  *(_QWORD *)(v3 + 136) += v52;
  *(_QWORD *)(v3 + 120) += v52;
  v53 = *(_QWORD *)(v3 + 136);
  v54 = *(_QWORD *)(v3 + 88);
  if ( v53 >= v54 )
    *(_QWORD *)(v3 + 136) = v53 - v54;
  *(_DWORD *)(v3 + 160) = v51;
  v55 = *(unsigned __int8 *)(a1 + 160);
  *(_QWORD *)(v3 + 352) = v25;
  *(_DWORD *)(v3 + 164) = -v55 & (v51 + v55 - 1);
  *(_DWORD *)(*(_QWORD *)(v3 + 264) + 32LL) = *(_DWORD *)(*(_QWORD *)(v3 + 264) + 24LL)
                                            & (v51 >> *(_DWORD *)(*(_QWORD *)(v3 + 264) + 20LL));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_ddi(
      WPP_GLOBAL_Control->AttachedDevice,
      *(_QWORD *)(v3 + 296),
      (unsigned int)(*(_DWORD *)(v3 + 152) - 1),
      *(unsigned int *)(v3 + 160),
      *(_DWORD *)(v3 + 152) - 1,
      *(_QWORD *)(v3 + 296));
  return v50;
}

```

## disassembly

```asm
0x140015e74  mov     [rsp+arg_10], rbx
0x140015e79  mov     [rsp+arg_0], rcx
0x140015e7e  push    rbp
0x140015e7f  push    rsi
0x140015e80  push    rdi
0x140015e81  push    r12
0x140015e83  push    r13
0x140015e85  push    r14
0x140015e87  push    r15
0x140015e89  sub     rsp, 50h
0x140015e8d  mov     rbx, [rcx+28h]
0x140015e91  lea     r12, WPP_GLOBAL_Control
0x140015e98  mov     r14, rcx
0x140015e9b  mov     rsi, [rbx+158h]
0x140015ea2  mov     rdx, [rbx+128h]
0x140015ea9  cmp     rdx, rsi
0x140015eac  jbe     short loc_140015EEA
0x140015eae  mov     rcx, cs:WPP_GLOBAL_Control
0x140015eb5  cmp     rcx, r12
0x140015eb8  jz      short loc_140015ED2
0x140015eba  mov     eax, [rcx+2Ch]
0x140015ebd  test    al, 20h
0x140015ebf  jz      short loc_140015ED2
0x140015ec1  mov     rcx, [rcx+18h]
0x140015ec5  mov     r9, rdx
0x140015ec8  mov     [rsp+88h+var_68], rsi
0x140015ecd  call    WPP_SF_ii
0x140015ed2  mov     rdx, [rbx+128h]
0x140015ed9  mov     rsi, [rbx+140h]
0x140015ee0  add     rsi, rdx
0x140015ee3  mov     [rbx+158h], rsi
0x140015eea  mov     r8, [rbx+148h]
0x140015ef1  mov     r11, [rbx+140h]
0x140015ef8  sub     rsi, r8
0x140015efb  mov     r9, [rbx+160h]
0x140015f02  sub     rsi, r11
0x140015f05  cmp     rsi, r9
0x140015f08  jnb     short loc_140015F55
0x140015f0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140015f11  cmp     rcx, r12
0x140015f14  jz      loc_1400162AE
0x140015f1a  mov     eax, [rcx+2Ch]
0x140015f1d  test    al, 10h
0x140015f1f  jz      loc_1400162AE
0x140015f25  mov     eax, [rbx+98h]
0x140015f2b  mov     rcx, [rcx+18h]
0x140015f2f  dec     eax
0x140015f31  mov     [rsp+88h+var_50], r9
0x140015f36  mov     r9d, [rbx+0A0h]
0x140015f3d  mov     [rsp+88h+var_58], rsi
0x140015f42  mov     [rsp+88h+var_60], rdx
0x140015f47  mov     dword ptr [rsp+88h+var_68], eax
0x140015f4b  call    WPP_SF_ddiii
0x140015f50  jmp     loc_1400162AE
0x140015f55  mov     rax, [rbx+108h]
0x140015f5c  movzx   edi, byte ptr [r14+0A0h]
0x140015f64  mov     ebp, [rbx+98h]
0x140015f6a  neg     edi
0x140015f6c  mov     r10d, [rbx+0A0h]
0x140015f73  and     edi, ebp
0x140015f75  mov     rcx, [rax]
0x140015f78  mov     edx, edi
0x140015f7a  sub     edx, r10d
0x140015f7d  cmp     rcx, rax
0x140015f80  jz      short loc_140015F8F
0x140015f82  test    rcx, rcx
0x140015f85  jz      short loc_140015F8F
0x140015f87  mov     ecx, [rcx+10h]
0x140015f8a  cmp     ecx, edi
0x140015f8c  cmovs   edi, ecx
0x140015f8f  mov     rax, [rbx+20h]
0x140015f93  mov     r15d, edi
0x140015f96  sub     r15d, r10d
0x140015f99  mov     ecx, [rax+38h]
0x140015f9c  test    cl, 2
0x140015f9f  jz      short loc_140015FCD
0x140015fa1  test    dword ptr [r14+20h], 1000h
0x140015fa9  jnz     short loc_140015FCD
0x140015fab  mov     rcx, [rbx+60h]
0x140015faf  shr     rcx, 1
0x140015fb2  mov     eax, edx
0x140015fb4  cmp     rax, rcx
0x140015fb7  jbe     short loc_140015FD2
0x140015fb9  mov     eax, edx
0x140015fbb  sub     eax, r15d
0x140015fbe  cmp     rax, rcx
0x140015fc1  jnb     short loc_140015FCD
0x140015fc3  mov     r15d, edx
0x140015fc6  sub     r15d, ecx
0x140015fc9  lea     edi, [r15+r10]
0x140015fcd  test    r15d, r15d
0x140015fd0  jnz     short loc_140016010
0x140015fd2  mov     rcx, cs:WPP_GLOBAL_Control
0x140015fd9  cmp     rcx, r12
0x140015fdc  jz      loc_1400162AE
0x140015fe2  mov     eax, [rcx+2Ch]
0x140015fe5  test    al, 10h
0x140015fe7  jz      loc_1400162AE
0x140015fed  mov     [rsp+88h+var_48], r9
0x140015ff2  lea     r8d, [rbp-1]
0x140015ff6  mov     [rsp+88h+var_50], rsi
0x140015ffb  mov     edx, 45h ; 'E'
0x140016000  mov     dword ptr [rsp+88h+var_58], 0
0x140016008  mov     r9d, r10d
0x14001600b  jmp     loc_140016294
0x140016010  mov     rcx, cs:WPP_GLOBAL_Control
0x140016017  cmp     rcx, r12
0x14001601a  jz      short loc_14001603E
0x14001601c  mov     eax, [rcx+2Ch]
0x14001601f  test    al, 20h
0x140016021  jz      short loc_14001603E
0x140016023  mov     rcx, [rcx+18h]
0x140016027  mov     [rsp+88h+var_58], r8
0x14001602c  mov     [rsp+88h+var_60], r11
0x140016031  mov     [rsp+88h+var_68], r9
0x140016036  mov     r9, rsi
0x140016039  call    WPP_SF_iiii
0x14001603e  xor     r12d, r12d
0x140016041  lea     rax, [rbx+0D8h]
0x140016048  mov     r14, [rax]
0x14001604b  xor     ebp, ebp
0x14001604d  xor     r8d, r8d
0x140016050  mov     r13, rsi
0x140016053  cmp     r14, rax
0x140016056  jz      loc_140016112
0x14001605c  mov     r8, r14
0x14001605f  mov     r13, [r14+30h]
0x140016063  mov     [rsp+88h+arg_8], r14
0x14001606b  cmp     [r14+88h], ebp
0x140016072  jnz     short loc_1400160EF
0x140016074  cmp     r13, rsi
0x140016077  jnb     short loc_1400160EF
0x140016079  mov     edx, [r14+58h]
0x14001607d  cmp     edx, edi
0x14001607f  jns     short loc_1400160EF
0x140016081  cmp     [r14+5Ch], edi
0x140016085  jns     short loc_1400160D2
0x140016087  mov     rax, [r14]
0x14001608a  cmp     [rax+8], r14
0x14001608e  jnz     loc_1400162B5
0x140016094  mov     rcx, [r14+8]
0x140016098  cmp     [rcx], r14
0x14001609b  jnz     loc_1400162B5
0x1400160a1  mov     [rcx], rax
0x1400160a4  mov     rdx, r8; Entry
0x1400160a7  mov     [rax+8], rcx
0x1400160ab  mov     r14, rax
0x1400160ae  lea     rcx, [rbx+240h]; Lookaside
0x1400160b5  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400160bc  nop     dword ptr [rax+rax+00h]
0x1400160c1  mov     r8, [rsp+88h+arg_8]
0x1400160c9  lea     rax, [rbx+0D8h]
0x1400160d0  jmp     short loc_140016053
0x1400160d2  mov     eax, [rbx+0A0h]
0x1400160d8  mov     r12d, edx
0x1400160db  sub     r12d, eax
0x1400160de  mov     ecx, eax
0x1400160e0  xor     eax, eax
0x1400160e2  sub     ecx, edx
0x1400160e4  test    ecx, ecx
0x1400160e6  mov     rbp, r14
0x1400160e9  cmovg   r12d, eax
0x1400160ed  jmp     short loc_140016112
0x1400160ef  mov     eax, [rbx+0A0h]
0x1400160f5  mov     ecx, eax
0x1400160f7  mov     edx, [r14+58h]
0x1400160fb  sub     ecx, edx
0x1400160fd  test    ecx, ecx
0x1400160ff  mov     edi, edx
0x140016101  cmovg   edi, eax
0x140016104  sub     edx, eax
0x140016106  xor     r15d, r15d
0x140016109  test    ecx, ecx
0x14001610b  cmovle  r15d, edx
0x14001610f  mov     r12d, r15d
0x140016112  test    r8, r8
0x140016115  jnz     short loc_140016164
0x140016117  lea     rax, [rbx+0E8h]
0x14001611e  mov     rcx, [rax]
0x140016121  cmp     rcx, rax
0x140016124  jz      short loc_140016164
0x140016126  cmp     [rcx+88h], r8d
0x14001612d  jnz     loc_140016249
0x140016133  cmp     [rcx+8Ch], r8d
0x14001613a  jnz     loc_140016249
0x140016140  mov     eax, [rcx+80h]
0x140016146  test    eax, eax
0x140016148  jz      loc_140016249
0x14001614e  cmp     [rcx+6Ch], eax
0x140016151  jnz     loc_140016249
0x140016157  cmp     [rcx+30h], rsi
0x14001615b  ja      loc_140016249
0x140016161  mov     rbp, rcx
0x140016164  test    rbp, rbp
0x140016167  jz      loc_140016249
0x14001616d  mov     rax, [rbx+20h]
0x140016171  xor     edx, edx
0x140016173  mov     r14, [rbp+30h]
0x140016177  mov     r9d, [rax+0F8h]
0x14001617e  mov     r11, [rax+110h]
0x140016185  mov     rax, rsi
0x140016188  sub     rax, r14
0x14001618b  imul    rax, r11
0x14001618f  lea     ecx, ds:0[r9*8]
0x140016197  lea     rax, [rax+rax*4]
0x14001619b  shl     rax, 2
0x14001619f  div     rcx
0x1400161a2  mov     edx, [rbp+58h]
0x1400161a5  mov     r10d, edx
0x1400161a8  mov     ecx, [rbp+5Ch]
0x1400161ab  mov     r8, rax
0x1400161ae  sub     r10d, ecx
0x1400161b1  add     eax, r10d
0x1400161b4  test    eax, eax
0x1400161b6  jle     short loc_1400161BE
0x1400161b8  sub     ecx, edx
0x1400161ba  inc     ecx
0x1400161bc  jmp     short loc_1400161C1
0x1400161be  mov     ecx, r8d
0x1400161c1  mov     eax, edx
0x1400161c3  sub     eax, edi
0x1400161c5  sub     edi, edx
0x1400161c7  add     eax, ecx
0x1400161c9  test    eax, eax
0x1400161cb  cmovle  edi, ecx
0x1400161ce  sub     edx, [rbx+0A0h]
0x1400161d4  lea     eax, [rdx+rdi]
0x1400161d7  test    eax, eax
0x1400161d9  jg      short loc_1400161DF
0x1400161db  xor     edi, edi
0x1400161dd  jmp     short loc_1400161E4
0x1400161df  test    edx, edx
0x1400161e1  cmovs   edi, eax
0x1400161e4  imul    r9d, edi
0x1400161e8  lea     rcx, [r11+r11*4]
0x1400161ec  shl     rcx, 2
0x1400161f0  xor     edx, edx
0x1400161f2  add     r12d, edi
0x1400161f5  shl     r9d, 3
0x1400161f9  mov     eax, r9d
0x1400161fc  div     rcx
0x1400161ff  cmp     dword ptr [rbp+68h], 0
0x140016203  lea     r13, [r14+rax]
0x140016207  jnz     short loc_140016249
0x140016209  lea     ecx, [r10+rdi]
0x14001620d  test    ecx, ecx
0x14001620f  jle     short loc_140016249
0x140016211  mov     rcx, [rbp+0]
0x140016215  cmp     [rcx+8], rbp
0x140016219  jnz     loc_1400162B5
0x14001621f  mov     rax, [rbp+8]
0x140016223  cmp     [rax], rbp
0x140016226  jnz     loc_1400162B5
0x14001622c  mov     [rax], rcx
0x14001622f  mov     rdx, rbp; Entry
0x140016232  mov     [rcx+8], rax
0x140016236  lea     rcx, [rbx+240h]; Lookaside
0x14001623d  call    cs:__imp_ExFreeToNPagedLookasideList
0x140016244  nop     dword ptr [rax+rax+00h]
0x140016249  test    r12d, r12d
0x14001624c  jnz     short loc_1400162BC
0x14001624e  mov     rcx, cs:WPP_GLOBAL_Control
0x140016255  lea     rbp, WPP_GLOBAL_Control
0x14001625c  cmp     rcx, rbp
0x14001625f  jz      short loc_1400162AE
0x140016261  mov     eax, [rcx+2Ch]
0x140016264  test    al, 10h
0x140016266  jz      short loc_1400162AE
0x140016268  mov     rax, [rbx+160h]
0x14001626f  lea     edx, [r12+47h]
0x140016274  mov     r8d, [rbx+98h]
0x14001627b  mov     r9d, [rbx+0A0h]
0x140016282  dec     r8d
0x140016285  mov     [rsp+88h+var_48], rax
0x14001628a  mov     [rsp+88h+var_50], rsi
0x14001628f  mov     dword ptr [rsp+88h+var_58], r15d
0x140016294  mov     rax, [rbx+128h]
0x14001629b  mov     rcx, [rcx+18h]
0x14001629f  mov     [rsp+88h+var_60], rax
0x1400162a4  mov     dword ptr [rsp+88h+var_68], r8d
0x1400162a9  call    WPP_SF_ddidii
0x1400162ae  xor     eax, eax
0x1400162b0  jmp     loc_1400163C4
0x1400162b5  mov     ecx, 3
0x1400162ba  int     29h; Win8: RtlFailFast(ecx)
0x1400162bc  mov     edx, [rbx+0A0h]
0x1400162c2  cmp     r12d, r15d
0x1400162c5  mov     esi, r15d
0x1400162c8  cmovbe  esi, r12d
0x1400162cc  lea     edi, [rdx+rsi]
0x1400162cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400162d6  lea     rbp, WPP_GLOBAL_Control
0x1400162dd  cmp     rcx, rbp
0x1400162e0  jz      short loc_140016318
0x1400162e2  mov     eax, [rcx+2Ch]
0x1400162e5  test    al, 20h
0x1400162e7  jz      short loc_140016318
0x1400162e9  mov     rax, [rbx+160h]
0x1400162f0  mov     r9d, [rbx+78h]
0x1400162f4  mov     rcx, [rcx+18h]
  ... truncated ...
```
