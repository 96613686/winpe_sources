# Smb2RkfReadState

- ea: `0x14006ed5c`
- end: `0x14006f431`
- name: `Smb2RkfReadState`
- size: `1749`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x14006d1a8`
- `0x14006ddc0`
- `0x14006f438`

## callees

- `0x14001a554`
- `0x1400224b8`
- `0x1400224fc`
- `0x140025750`
- `0x140033fe0`
- `0x140034050`
- `0x140038490`
- `0x14006e720`
- `0x14006ed5c`
- `0x14006fea4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14006ee57`
- `ntoskrnl!ExAllocatePool2` at `0x14006ee57`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f00a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f097`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f1b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f00a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f097`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f1b0`

## pseudocode

```c
__int64 __fastcall Smb2RkfReadState(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        PVOID *a4,
        unsigned int *a5,
        _DWORD *a6,
        _QWORD *a7,
        _DWORD *a8,
        _QWORD *a9,
        _QWORD *a10,
        _DWORD *a11,
        _DWORD *a12,
        char *a13)
{
  __int64 v13; // rbx
  unsigned int *v14; // rsi
  _QWORD *v15; // r15
  _DWORD *v17; // r12
  unsigned int *v18; // r8
  unsigned int v19; // r14d
  unsigned __int64 v20; // r13
  unsigned int v21; // eax
  __int64 Pool2; // rax
  int v23; // ebx
  _DWORD *v24; // rcx
  __int64 v25; // r11
  unsigned __int8 v26; // r11
  __int64 v27; // rdx
  unsigned __int64 v28; // rcx
  unsigned __int64 v29; // r9
  _DWORD *v30; // r13
  _QWORD *v31; // rax
  _DWORD *v32; // rcx
  _QWORD *v33; // rax
  char *v34; // rax
  char *v36; // r15
  unsigned int v37; // r14d
  char *v38; // rax
  bool v39; // cf
  __int64 v40; // rax
  unsigned __int64 v41; // rdx
  unsigned __int64 v42; // rcx
  int v43; // eax
  __int64 v44; // rax
  unsigned __int64 v45; // rdx
  unsigned __int64 v46; // rcx
  int v47; // eax
  char v48; // r14
  char *v49; // rax
  _DWORD *v50; // rcx
  unsigned int v51; // [rsp+28h] [rbp-108h]
  unsigned __int8 v52; // [rsp+B0h] [rbp-80h]
  char v53; // [rsp+B1h] [rbp-7Fh]
  char v54; // [rsp+B2h] [rbp-7Eh]
  unsigned __int8 v55; // [rsp+B3h] [rbp-7Dh]
  char v56; // [rsp+B4h] [rbp-7Ch]
  char v57; // [rsp+B5h] [rbp-7Bh]
  char v58; // [rsp+B6h] [rbp-7Ah]
  char v59; // [rsp+B7h] [rbp-79h]
  unsigned __int16 MaxClusterDialect; // [rsp+C8h] [rbp-68h]
  __int16 v61; // [rsp+CAh] [rbp-66h]
  __int16 v62; // [rsp+CCh] [rbp-64h]
  unsigned int v63; // [rsp+D0h] [rbp-60h]
  unsigned int v64; // [rsp+D4h] [rbp-5Ch] BYREF
  ULONG pulResult; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v66; // [rsp+E0h] [rbp-50h]
  _QWORD *v67; // [rsp+E8h] [rbp-48h]
  _QWORD *v68; // [rsp+F0h] [rbp-40h]
  _DWORD *v69; // [rsp+F8h] [rbp-38h]
  char *v70; // [rsp+100h] [rbp-30h]
  int v71; // [rsp+108h] [rbp-28h]
  _DWORD *v72; // [rsp+110h] [rbp-20h]
  _DWORD *v73; // [rsp+118h] [rbp-18h]
  __int64 v74; // [rsp+120h] [rbp-10h]
  __int64 v75; // [rsp+128h] [rbp-8h]
  __int64 v76; // [rsp+130h] [rbp+0h]
  __int64 v77; // [rsp+138h] [rbp+8h]
  __int64 v78; // [rsp+140h] [rbp+10h]
  void *v79; // [rsp+148h] [rbp+18h] BYREF
  unsigned int *v80; // [rsp+150h] [rbp+20h]
  __int64 v81; // [rsp+158h] [rbp+28h]
  __int64 v82; // [rsp+160h] [rbp+30h]
  __int128 v83; // [rsp+168h] [rbp+38h] BYREF

  v13 = a1;
  v14 = a5;
  v15 = a10;
  v17 = a12;
  v73 = a6;
  v67 = a7;
  v68 = a9;
  v69 = a11;
  v82 = a1;
  v70 = a13;
  v81 = a2;
  v80 = a5;
  v72 = a12;
  v83 = 0;
  pulResult = 0;
  v79 = 0;
  v64 = 0;
  *a4 = 0;
  MaxClusterDialect = Smb2GetMaxClusterDialect(0);
  v19 = 2 - (MaxClusterDialect < 0x311u);
  if ( v18 )
    *v18 = v19;
  LODWORD(v20) = 608;
  while ( 1 )
  {
    v21 = v20 + 120;
    if ( (unsigned int)v20 >= 0xFFFFFF88 )
    {
      *v14 = -1;
LABEL_70:
      v23 = -1073741306;
      goto LABEL_23;
    }
    *v14 = v21;
    if ( v21 > 0x100000 )
      goto LABEL_70;
    Pool2 = ExAllocatePool2(258, v21, 1647465292);
    *a4 = (PVOID)Pool2;
    if ( !Pool2 )
    {
      v23 = -1073741670;
      goto LABEL_23;
    }
    v51 = *v14;
    LODWORD(v83) = 2 - (MaxClusterDialect < 0x311u);
    *(_QWORD *)((char *)&v83 + 4) = 3;
    HIDWORD(v83) = v20;
    v23 = Smb2RkfFsctl(v13, v81, &v83, 16, Pool2, v51, v14);
    if ( v23 < 0 )
      goto LABEL_23;
    v24 = *a4;
    v25 = (__int64)*a4 + 24;
    v78 = v25;
    v77 = v25;
    v76 = v25;
    v75 = v25;
    v74 = v25;
    v66 = v25;
    if ( MaxClusterDialect < 0x311u )
    {
      v15 = a10;
      v63 = 96;
    }
    else
    {
      v63 = v24[28];
    }
    v26 = *(_BYTE *)(v25 + 13);
    v20 = (unsigned int)v24[22];
    v52 = v26;
    v62 = *(_WORD *)(v78 + 4);
    v71 = v24[6];
    v61 = *(_WORD *)(v66 + 6);
    v59 = *(_BYTE *)(v74 + 8);
    v58 = *(_BYTE *)(v75 + 9);
    v57 = *(_BYTE *)(v76 + 10);
    v56 = *(_BYTE *)(v77 + 11);
    v14 = v80;
    v17 = v72;
    v55 = *(_BYTE *)(v78 + 12);
    v54 = *(_BYTE *)(v78 + 14);
    v27 = (unsigned int)v24[23];
    v53 = *(_BYTE *)(v78 + 15);
    LODWORD(v66) = v24[23];
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_DDDD(WPP_GLOBAL_Control->AttachedDevice, v27, 15, (unsigned int)v23, *v80, v20, v27);
      LODWORD(v27) = v66;
      v26 = v52;
    }
    if ( !(_DWORD)v20 )
    {
      v49 = v70;
      *v67 = 0;
      *a8 = 0;
      *v68 = 0;
      v50 = v69;
      *v15 = 0;
      *v50 = 0;
      *v17 = 0;
      *v49 = 0;
LABEL_66:
      *v73 = 1;
      return 0;
    }
    if ( (_DWORD)v27 == (_DWORD)v20 )
      break;
    ExFreePoolWithTag(*a4, 0);
    *a4 = 0;
    v13 = v82;
  }
  v28 = v63 + v20;
  if ( v28 < v63 || (v29 = 0xFFFFFFFFLL, v28 > 0xFFFFFFFF) || v28 > *v80 || (unsigned int)v20 < 4 )
  {
    v23 = -1073739509;
    goto LABEL_23;
  }
  v36 = (char *)*a4 + v63;
  if ( *(_DWORD *)v36 == 0x100000 )
  {
    if ( (unsigned int)v20 >= 8 )
    {
      if ( *((_DWORD *)v36 + 1) == 1 )
      {
        v39 = (unsigned int)v20 < 0x58;
      }
      else
      {
        if ( *((_DWORD *)v36 + 1) != 2 )
          goto LABEL_39;
        v39 = (unsigned int)v20 < 0x5D;
      }
      if ( !v39 )
      {
        *v73 = *((_DWORD *)v36 + 1);
        v40 = *((unsigned int *)v36 + 19);
        if ( (_DWORD)v40 )
        {
          if ( RtlULongLongToULong(24 * v40, &pulResult) < 0 )
            goto LABEL_39;
          v41 = *((unsigned int *)v36 + 18);
          v42 = v41 + pulResult;
          if ( v42 < v41 || v42 > v29 || v42 > v20 )
            goto LABEL_39;
          *v67 = &v36[v41];
          v43 = *((_DWORD *)v36 + 19);
        }
        else
        {
          v43 = 0;
          *v67 = 0;
        }
        *a8 = v43;
        v44 = *((unsigned int *)v36 + 21);
        if ( (_DWORD)v44 )
        {
          v45 = *((unsigned int *)v36 + 20);
          v46 = v45 + v44;
          if ( v45 + v44 < v45 || v46 > v29 || v46 > v20 )
            goto LABEL_39;
          *a10 = &v36[v45];
          v47 = *((_DWORD *)v36 + 21);
        }
        else
        {
          v47 = 0;
          *a10 = 0;
        }
        *v69 = v47;
        *v68 = v36 + 8;
        if ( *((_DWORD *)v36 + 1) < 2u )
        {
          *v17 = 0;
          v48 = 0;
        }
        else
        {
          *v17 = *((_DWORD *)v36 + 22);
          v48 = v36[92];
        }
        *v70 = v48;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_DDDDDDDDDDDDDDDDDDD(
            WPP_GLOBAL_Control->AttachedDevice,
            v26,
            v55,
            *v80,
            v20,
            v66,
            *((_DWORD *)v36 + 1),
            *((_DWORD *)v36 + 19),
            *((_DWORD *)v36 + 21),
            *v72,
            v48,
            v71,
            v62,
            v61,
            v59,
            v58,
            v57,
            v56,
            v55,
            v26,
            v54,
            v53);
        }
        return 0;
      }
    }
LABEL_39:
    v15 = a10;
    v23 = -1073739509;
LABEL_23:
    v30 = a8;
    goto LABEL_24;
  }
  v30 = a8;
  v23 = Smb2RkfpConvertDeprecatedBlob(v19, *a4, &v79, &v64, v67, a8, v68);
  v37 = v64;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_DDD(
      WPP_GLOBAL_Control->AttachedDevice,
      16,
      WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids,
      (unsigned int)v23,
      v64,
      *a8);
  }
  if ( v23 >= 0 )
  {
    ExFreePoolWithTag(*a4, 0);
    *a4 = v79;
    v38 = v70;
    *v14 = v37;
    *a10 = 0;
    *v69 = 0;
    *v17 = 0;
    *v38 = 0;
    goto LABEL_66;
  }
  v15 = a10;
LABEL_24:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids, (unsigned int)v23);
  }
  if ( *a4 )
  {
    ExFreePoolWithTag(*a4, 0);
    *a4 = 0;
  }
  v31 = v67;
  v32 = v69;
  *v14 = 0;
  *v31 = 0;
  v33 = v68;
  *v30 = 0;
  *v33 = 0;
  v34 = v70;
  *v15 = 0;
  *v32 = 0;
  *v17 = 0;
  *v34 = 0;
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x14006ed5c  push    rbp
0x14006ed5e  push    rbx
0x14006ed5f  push    rsi
0x14006ed60  push    rdi
0x14006ed61  push    r12
0x14006ed63  push    r13
0x14006ed65  push    r14
0x14006ed67  push    r15
0x14006ed69  lea     rbp, [rsp-58h]
0x14006ed6e  sub     rsp, 188h
0x14006ed75  mov     rax, cs:__security_cookie
0x14006ed7c  xor     rax, rsp
0x14006ed7f  mov     [rbp+90h+var_48], rax
0x14006ed83  mov     rax, [rbp+90h+arg_28]
0x14006ed8a  mov     rbx, rcx
0x14006ed8d  mov     rsi, [rbp+90h+arg_20]
0x14006ed94  xorps   xmm0, xmm0
0x14006ed97  mov     r15, [rbp+90h+arg_48]
0x14006ed9e  mov     rdi, r9
0x14006eda1  mov     r12, [rbp+90h+arg_58]
0x14006eda8  mov     [rbp+90h+var_A8], rax
0x14006edac  mov     rax, [rbp+90h+arg_30]
0x14006edb3  mov     [rbp+90h+var_D8], rax
0x14006edb7  mov     rax, [rbp+90h+arg_38]
0x14006edbe  mov     [rbp+90h+var_108], rax
0x14006edc2  mov     rax, [rbp+90h+arg_40]
0x14006edc9  mov     [rbp+90h+var_D0], rax
0x14006edcd  mov     rax, [rbp+90h+arg_50]
0x14006edd4  mov     [rbp+90h+var_C8], rax
0x14006edd8  mov     rax, [rbp+90h+arg_60]
0x14006eddf  mov     [rbp+90h+var_60], rcx
0x14006ede3  xor     ecx, ecx
0x14006ede5  mov     [rbp+90h+var_C0], rax
0x14006ede9  mov     [rbp+90h+var_68], rdx
0x14006eded  mov     [rbp+90h+var_70], rsi
0x14006edf1  mov     [rbp+90h+var_100], r15
0x14006edf5  mov     [rbp+90h+var_B0], r12
0x14006edf9  movups  [rbp+90h+var_58], xmm0
0x14006edfd  mov     [rbp+90h+pulResult], ecx
0x14006ee00  mov     [rbp+90h+var_78], rcx
0x14006ee04  mov     [rbp+90h+var_EC], ecx
0x14006ee07  mov     [r9], rcx
0x14006ee0a  call    Smb2GetMaxClusterDialect
0x14006ee0f  mov     edx, 311h
0x14006ee14  mov     [rbp+90h+var_F8], ax
0x14006ee18  cmp     ax, dx
0x14006ee1b  sbb     r14d, r14d
0x14006ee1e  add     r14d, 2
0x14006ee22  test    r8, r8
0x14006ee25  jz      short loc_14006EE2A
0x14006ee27  mov     [r8], r14d
0x14006ee2a  mov     r13d, 260h
0x14006ee30  lea     eax, [r13+78h]
0x14006ee34  cmp     eax, 78h ; 'x'
0x14006ee37  jb      loc_14006F418
0x14006ee3d  mov     [rsi], eax
0x14006ee3f  cmp     eax, 100000h
0x14006ee44  ja      loc_14006F41E
0x14006ee4a  mov     edx, eax
0x14006ee4c  mov     ecx, 102h
0x14006ee51  mov     r8d, 6232534Ch
0x14006ee57  call    cs:__imp_ExAllocatePool2
0x14006ee5e  nop     dword ptr [rax+rax+00h]
0x14006ee63  mov     [rdi], rax
0x14006ee66  test    rax, rax
0x14006ee69  jz      loc_14006F40E
0x14006ee6f  mov     ecx, [rsi]
0x14006ee71  lea     r8, [rbp+90h+var_58]
0x14006ee75  mov     rdx, [rbp+90h+var_68]
0x14006ee79  mov     r9d, 10h
0x14006ee7f  mov     [rsp+1C0h+var_190], rsi
0x14006ee84  mov     dword ptr [rsp+1C0h+var_198], ecx
0x14006ee88  mov     rcx, rbx
0x14006ee8b  mov     dword ptr [rbp+90h+var_58], r14d
0x14006ee8f  mov     qword ptr [rbp+90h+var_58+4], 3
0x14006ee97  mov     dword ptr [rbp+90h+var_58+0Ch], r13d
0x14006ee9b  mov     [rsp+1C0h+var_1A0], rax
0x14006eea0  call    Smb2RkfFsctl
0x14006eea5  mov     ebx, eax
0x14006eea7  test    eax, eax
0x14006eea9  js      loc_14006F04F
0x14006eeaf  mov     rcx, [rdi]
0x14006eeb2  mov     r8d, 0Fh
0x14006eeb8  mov     edx, 311h
0x14006eebd  lea     rax, [rcx+18h]
0x14006eec1  lea     r10d, [r8-1]
0x14006eec5  mov     r9, rax
0x14006eec8  lea     r13d, [r8-2]
0x14006eecc  mov     r11, rax
0x14006eecf  mov     [rbp+90h+var_80], rax
0x14006eed3  mov     [rbp+90h+var_88], rax
0x14006eed7  mov     [rbp+90h+var_90], rax
0x14006eedb  mov     [rbp+90h+var_98], rax
0x14006eedf  mov     [rbp+90h+var_A0], rax
0x14006eee3  mov     [rbp+90h+var_E0], rax
0x14006eee7  cmp     [rbp+90h+var_F8], dx
0x14006eeeb  jb      short loc_14006EEF5
0x14006eeed  mov     edx, [rcx+70h]
0x14006eef0  mov     [rbp+90h+var_F0], edx
0x14006eef3  jmp     short loc_14006EF00
0x14006eef5  mov     r15, [rbp+90h+var_100]
0x14006eef9  mov     [rbp+90h+var_F0], 60h ; '`'
0x14006ef00  mov     rdx, rax
0x14006ef03  mov     r11b, [r11+r13]; __annotation("TMF:",
0x14006ef07  mov     r12d, 4
0x14006ef0d  mov     r13d, [rcx+58h]
0x14006ef11  mov     esi, 18h
0x14006ef16  mov     [rbp+90h+var_110], r11b
0x14006ef1a  movzx   eax, word ptr [r12+rax]
0x14006ef1f  mov     r12d, 6
0x14006ef25  mov     esi, [rsi+rcx]
0x14006ef28  mov     [rbp+90h+var_F4], ax
0x14006ef2c  mov     rax, [rbp+90h+var_E0]
0x14006ef30  mov     [rbp+90h+var_B8], esi
0x14006ef33  movzx   esi, word ptr [r12+rax]
0x14006ef38  mov     r12d, 8
0x14006ef3e  mov     rax, [rbp+90h+var_A0]
0x14006ef42  mov     [rbp+90h+var_F6], si
0x14006ef46  mov     sil, [r12+rax]
0x14006ef4a  mov     r12d, 9
0x14006ef50  mov     rax, [rbp+90h+var_98]
0x14006ef54  mov     [rbp+90h+var_109], sil
0x14006ef58  mov     sil, [r12+rax]
0x14006ef5c  mov     r12d, 0Ah
0x14006ef62  mov     rax, [rbp+90h+var_90]
0x14006ef66  mov     [rbp+90h+var_10A], sil
0x14006ef6a  mov     sil, [r12+rax]
0x14006ef6e  mov     r12d, 0Bh
0x14006ef74  mov     rax, [rbp+90h+var_88]
0x14006ef78  mov     [rbp+90h+var_10B], sil
0x14006ef7c  mov     sil, [r12+rax]
0x14006ef80  mov     r12d, 0Ch
0x14006ef86  mov     rax, [rbp+90h+var_80]
0x14006ef8a  mov     [rbp+90h+var_10C], sil
0x14006ef8e  mov     rsi, [rbp+90h+var_70]
0x14006ef92  mov     al, [r12+rax]
0x14006ef96  mov     r12, [rbp+90h+var_B0]
0x14006ef9a  mov     [rbp+90h+var_10D], al
0x14006ef9d  mov     al, [r9+r10]
0x14006efa1  mov     [rbp+90h+var_10E], al
0x14006efa4  mov     al, [rdx+r8]
0x14006efa8  mov     edx, [rcx+5Ch]
0x14006efab  mov     rcx, cs:WPP_GLOBAL_Control
0x14006efb2  mov     [rbp+90h+var_10F], al
0x14006efb5  lea     rax, WPP_GLOBAL_Control
0x14006efbc  mov     dword ptr [rbp+90h+var_E0], edx
0x14006efbf  cmp     rcx, rax
0x14006efc2  jz      short loc_14006EFF5
0x14006efc4  test    dword ptr [rcx+2Ch], 100000h
0x14006efcb  jz      short loc_14006EFF5
0x14006efcd  cmp     byte ptr [rcx+29h], 2
0x14006efd1  jb      short loc_14006EFF5
0x14006efd3  mov     eax, [rsi]
0x14006efd5  mov     r9d, ebx
0x14006efd8  mov     rcx, [rcx+18h]
0x14006efdc  mov     dword ptr [rsp+1C0h+var_190], edx
0x14006efe0  mov     dword ptr [rsp+1C0h+var_198], r13d
0x14006efe5  mov     dword ptr [rsp+1C0h+var_1A0], eax
0x14006efe9  call    WPP_SF_DDDD
0x14006efee  mov     edx, dword ptr [rbp+90h+var_E0]
0x14006eff1  mov     r11b, [rbp+90h+var_110]
0x14006eff5  xor     ebx, ebx
0x14006eff7  test    r13d, r13d
0x14006effa  jz      loc_14006F3D6
0x14006f000  cmp     edx, r13d
0x14006f003  jz      short loc_14006F022
0x14006f005  mov     rcx, [rdi]; P
0x14006f008  xor     edx, edx; Tag
0x14006f00a  call    cs:__imp_ExFreePoolWithTag
0x14006f011  nop     dword ptr [rax+rax+00h]
0x14006f016  mov     [rdi], rbx
0x14006f019  mov     rbx, [rbp+90h+var_60]
0x14006f01d  jmp     loc_14006EE30
0x14006f022  mov     edx, [rbp+90h+var_F0]
0x14006f025  lea     rcx, [rdx+r13]
0x14006f029  cmp     rcx, rdx
0x14006f02c  jb      short loc_14006F04A
0x14006f02e  mov     r9d, 0FFFFFFFFh
0x14006f034  cmp     rcx, r9
0x14006f037  ja      short loc_14006F04A
0x14006f039  mov     eax, [rsi]
0x14006f03b  cmp     rcx, rax
0x14006f03e  ja      short loc_14006F04A
0x14006f040  cmp     r13d, 4
0x14006f044  jnb     loc_14006F111
0x14006f04a  mov     ebx, 0C000090Bh
0x14006f04f  mov     r13, [rbp+90h+var_108]
0x14006f053  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006f05a  lea     rax, WPP_GLOBAL_Control
0x14006f061  cmp     rcx, rax
0x14006f064  jz      short loc_14006F08D
0x14006f066  test    dword ptr [rcx+2Ch], 100000h
0x14006f06d  jz      short loc_14006F08D
0x14006f06f  cmp     byte ptr [rcx+29h], 1
0x14006f073  jb      short loc_14006F08D
0x14006f075  mov     rcx, [rcx+18h]
0x14006f079  lea     r8, WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids
0x14006f080  mov     edx, 12h
0x14006f085  mov     r9d, ebx
0x14006f088  call    WPP_SF_d
0x14006f08d  mov     rcx, [rdi]; P
0x14006f090  test    rcx, rcx
0x14006f093  jz      short loc_14006F0AA
0x14006f095  xor     edx, edx; Tag
0x14006f097  call    cs:__imp_ExFreePoolWithTag
0x14006f09e  nop     dword ptr [rax+rax+00h]
0x14006f0a3  mov     qword ptr [rdi], 0
0x14006f0aa  mov     rax, [rbp+90h+var_D8]
0x14006f0ae  mov     rcx, [rbp+90h+var_C8]
0x14006f0b2  mov     dword ptr [rsi], 0
0x14006f0b8  mov     qword ptr [rax], 0
0x14006f0bf  mov     rax, [rbp+90h+var_D0]
0x14006f0c3  mov     dword ptr [r13+0], 0
0x14006f0cb  mov     qword ptr [rax], 0
0x14006f0d2  mov     rax, [rbp+90h+var_C0]
0x14006f0d6  mov     qword ptr [r15], 0
0x14006f0dd  mov     dword ptr [rcx], 0
0x14006f0e3  mov     dword ptr [r12], 0
0x14006f0eb  mov     byte ptr [rax], 0
0x14006f0ee  mov     eax, ebx
0x14006f0f0  mov     rcx, [rbp+90h+var_48]
0x14006f0f4  xor     rcx, rsp; StackCookie
0x14006f0f7  call    __security_check_cookie
0x14006f0fc  add     rsp, 188h
0x14006f103  pop     r15
0x14006f105  pop     r14
0x14006f107  pop     r13
0x14006f109  pop     r12
0x14006f10b  pop     rdi
0x14006f10c  pop     rsi
0x14006f10d  pop     rbx
0x14006f10e  pop     rbp
0x14006f10f  retn
0x14006f111  mov     rax, [rdi]
0x14006f114  lea     r15, [rdx+rax]
0x14006f118  cmp     dword ptr [r15], 100000h
0x14006f11f  jz      loc_14006F1E4
0x14006f125  mov     rcx, [rbp+90h+var_D0]
0x14006f129  lea     r9, [rbp+90h+var_EC]
0x14006f12d  mov     r13, [rbp+90h+var_108]
0x14006f131  lea     r8, [rbp+90h+var_78]
0x14006f135  mov     [rsp+1C0h+var_190], rcx
0x14006f13a  mov     rdx, rax
0x14006f13d  mov     rcx, [rbp+90h+var_D8]
0x14006f141  mov     [rsp+1C0h+var_198], r13
0x14006f146  mov     [rsp+1C0h+var_1A0], rcx
0x14006f14b  mov     ecx, r14d
0x14006f14e  call    Smb2RkfpConvertDeprecatedBlob
0x14006f153  mov     ebx, eax
0x14006f155  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006f15c  lea     rax, WPP_GLOBAL_Control
0x14006f163  mov     r14d, [rbp+90h+var_EC]
0x14006f167  cmp     rcx, rax
0x14006f16a  jz      short loc_14006F1A0
0x14006f16c  test    dword ptr [rcx+2Ch], 100000h
0x14006f173  jz      short loc_14006F1A0
0x14006f175  cmp     byte ptr [rcx+29h], 2
0x14006f179  jb      short loc_14006F1A0
0x14006f17b  mov     eax, [r13+0]
0x14006f17f  lea     r8, WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids
0x14006f186  mov     rcx, [rcx+18h]
0x14006f18a  mov     edx, 10h
0x14006f18f  mov     dword ptr [rsp+1C0h+var_198], eax
0x14006f193  mov     r9d, ebx
0x14006f196  mov     dword ptr [rsp+1C0h+var_1A0], r14d
0x14006f19b  call    WPP_SF_DDD
0x14006f1a0  xor     r15d, r15d
0x14006f1a3  test    ebx, ebx
0x14006f1a5  js      loc_14006F428
0x14006f1ab  mov     rcx, [rdi]; P
0x14006f1ae  xor     edx, edx; Tag
0x14006f1b0  call    cs:__imp_ExFreePoolWithTag
0x14006f1b7  nop     dword ptr [rax+rax+00h]
0x14006f1bc  mov     rcx, [rbp+90h+var_100]
0x14006f1c0  mov     rax, [rbp+90h+var_78]
0x14006f1c4  mov     [rdi], rax
0x14006f1c7  mov     rax, [rbp+90h+var_C0]
0x14006f1cb  mov     [rsi], r14d
0x14006f1ce  mov     [rcx], r15
0x14006f1d1  mov     rcx, [rbp+90h+var_C8]
0x14006f1d5  mov     [rcx], r15d
0x14006f1d8  mov     [r12], r15d
0x14006f1dc  mov     [rax], r15b
0x14006f1df  jmp     loc_14006F3FD
0x14006f1e4  cmp     r13d, 8
0x14006f1e8  jnb     short loc_14006F1F8
0x14006f1ea  mov     r15, [rbp+90h+var_100]
0x14006f1ee  mov     ebx, 0C000090Bh
0x14006f1f3  jmp     loc_14006F04F
0x14006f1f8  mov     ecx, [r15+4]
0x14006f1fc  mov     eax, ecx
0x14006f1fe  sub     eax, 1
0x14006f201  jz      short loc_14006F25B
0x14006f203  cmp     eax, 1
0x14006f206  jnz     short loc_14006F1EA
0x14006f208  cmp     r13d, 5Dh ; ']'
0x14006f20c  jb      short loc_14006F1EA
0x14006f20e  mov     rax, [rbp+90h+var_A8]
0x14006f212  mov     [rax], ecx
0x14006f214  mov     eax, [r15+4Ch]
  ... truncated ...
```
