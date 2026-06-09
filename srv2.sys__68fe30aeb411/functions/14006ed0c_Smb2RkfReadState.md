# Smb2RkfReadState

- ea: `0x14006ed0c`
- end: `0x14006f3e1`
- name: `Smb2RkfReadState`
- size: `1749`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x14006d158`
- `0x14006dd70`
- `0x14006f3e8`

## callees

- `0x14001a554`
- `0x1400224b8`
- `0x1400224fc`
- `0x140025750`
- `0x140033fe0`
- `0x140034050`
- `0x140038490`
- `0x14006e6d0`
- `0x14006ed0c`
- `0x14006fe54`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14006ee07`
- `ntoskrnl!ExAllocatePool2` at `0x14006ee07`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006efba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f047`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f160`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006efba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f047`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f160`

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
0x14006ed0c  push    rbp
0x14006ed0e  push    rbx
0x14006ed0f  push    rsi
0x14006ed10  push    rdi
0x14006ed11  push    r12
0x14006ed13  push    r13
0x14006ed15  push    r14
0x14006ed17  push    r15
0x14006ed19  lea     rbp, [rsp-58h]
0x14006ed1e  sub     rsp, 188h
0x14006ed25  mov     rax, cs:__security_cookie
0x14006ed2c  xor     rax, rsp
0x14006ed2f  mov     [rbp+90h+var_48], rax
0x14006ed33  mov     rax, [rbp+90h+arg_28]
0x14006ed3a  mov     rbx, rcx
0x14006ed3d  mov     rsi, [rbp+90h+arg_20]
0x14006ed44  xorps   xmm0, xmm0
0x14006ed47  mov     r15, [rbp+90h+arg_48]
0x14006ed4e  mov     rdi, r9
0x14006ed51  mov     r12, [rbp+90h+arg_58]
0x14006ed58  mov     [rbp+90h+var_A8], rax
0x14006ed5c  mov     rax, [rbp+90h+arg_30]
0x14006ed63  mov     [rbp+90h+var_D8], rax
0x14006ed67  mov     rax, [rbp+90h+arg_38]
0x14006ed6e  mov     [rbp+90h+var_108], rax
0x14006ed72  mov     rax, [rbp+90h+arg_40]
0x14006ed79  mov     [rbp+90h+var_D0], rax
0x14006ed7d  mov     rax, [rbp+90h+arg_50]
0x14006ed84  mov     [rbp+90h+var_C8], rax
0x14006ed88  mov     rax, [rbp+90h+arg_60]
0x14006ed8f  mov     [rbp+90h+var_60], rcx
0x14006ed93  xor     ecx, ecx
0x14006ed95  mov     [rbp+90h+var_C0], rax
0x14006ed99  mov     [rbp+90h+var_68], rdx
0x14006ed9d  mov     [rbp+90h+var_70], rsi
0x14006eda1  mov     [rbp+90h+var_100], r15
0x14006eda5  mov     [rbp+90h+var_B0], r12
0x14006eda9  movups  [rbp+90h+var_58], xmm0
0x14006edad  mov     [rbp+90h+pulResult], ecx
0x14006edb0  mov     [rbp+90h+var_78], rcx
0x14006edb4  mov     [rbp+90h+var_EC], ecx
0x14006edb7  mov     [r9], rcx
0x14006edba  call    Smb2GetMaxClusterDialect
0x14006edbf  mov     edx, 311h
0x14006edc4  mov     [rbp+90h+var_F8], ax
0x14006edc8  cmp     ax, dx
0x14006edcb  sbb     r14d, r14d
0x14006edce  add     r14d, 2
0x14006edd2  test    r8, r8
0x14006edd5  jz      short loc_14006EDDA
0x14006edd7  mov     [r8], r14d
0x14006edda  mov     r13d, 260h
0x14006ede0  lea     eax, [r13+78h]
0x14006ede4  cmp     eax, 78h ; 'x'
0x14006ede7  jb      loc_14006F3C8
0x14006eded  mov     [rsi], eax
0x14006edef  cmp     eax, 100000h
0x14006edf4  ja      loc_14006F3CE
0x14006edfa  mov     edx, eax
0x14006edfc  mov     ecx, 102h
0x14006ee01  mov     r8d, 6232534Ch
0x14006ee07  call    cs:__imp_ExAllocatePool2
0x14006ee0e  nop     dword ptr [rax+rax+00h]
0x14006ee13  mov     [rdi], rax
0x14006ee16  test    rax, rax
0x14006ee19  jz      loc_14006F3BE
0x14006ee1f  mov     ecx, [rsi]
0x14006ee21  lea     r8, [rbp+90h+var_58]
0x14006ee25  mov     rdx, [rbp+90h+var_68]
0x14006ee29  mov     r9d, 10h
0x14006ee2f  mov     [rsp+1C0h+var_190], rsi
0x14006ee34  mov     dword ptr [rsp+1C0h+var_198], ecx
0x14006ee38  mov     rcx, rbx
0x14006ee3b  mov     dword ptr [rbp+90h+var_58], r14d
0x14006ee3f  mov     qword ptr [rbp+90h+var_58+4], 3
0x14006ee47  mov     dword ptr [rbp+90h+var_58+0Ch], r13d
0x14006ee4b  mov     [rsp+1C0h+var_1A0], rax
0x14006ee50  call    Smb2RkfFsctl
0x14006ee55  mov     ebx, eax
0x14006ee57  test    eax, eax
0x14006ee59  js      loc_14006EFFF
0x14006ee5f  mov     rcx, [rdi]
0x14006ee62  mov     r8d, 0Fh
0x14006ee68  mov     edx, 311h
0x14006ee6d  lea     rax, [rcx+18h]
0x14006ee71  lea     r10d, [r8-1]
0x14006ee75  mov     r9, rax
0x14006ee78  lea     r13d, [r8-2]
0x14006ee7c  mov     r11, rax
0x14006ee7f  mov     [rbp+90h+var_80], rax
0x14006ee83  mov     [rbp+90h+var_88], rax
0x14006ee87  mov     [rbp+90h+var_90], rax
0x14006ee8b  mov     [rbp+90h+var_98], rax
0x14006ee8f  mov     [rbp+90h+var_A0], rax
0x14006ee93  mov     [rbp+90h+var_E0], rax
0x14006ee97  cmp     [rbp+90h+var_F8], dx
0x14006ee9b  jb      short loc_14006EEA5
0x14006ee9d  mov     edx, [rcx+70h]
0x14006eea0  mov     [rbp+90h+var_F0], edx
0x14006eea3  jmp     short loc_14006EEB0
0x14006eea5  mov     r15, [rbp+90h+var_100]
0x14006eea9  mov     [rbp+90h+var_F0], 60h ; '`'
0x14006eeb0  mov     rdx, rax
0x14006eeb3  mov     r11b, [r11+r13]; __annotation("TMF:",
0x14006eeb7  mov     r12d, 4
0x14006eebd  mov     r13d, [rcx+58h]
0x14006eec1  mov     esi, 18h
0x14006eec6  mov     [rbp+90h+var_110], r11b
0x14006eeca  movzx   eax, word ptr [r12+rax]
0x14006eecf  mov     r12d, 6
0x14006eed5  mov     esi, [rsi+rcx]
0x14006eed8  mov     [rbp+90h+var_F4], ax
0x14006eedc  mov     rax, [rbp+90h+var_E0]
0x14006eee0  mov     [rbp+90h+var_B8], esi
0x14006eee3  movzx   esi, word ptr [r12+rax]
0x14006eee8  mov     r12d, 8
0x14006eeee  mov     rax, [rbp+90h+var_A0]
0x14006eef2  mov     [rbp+90h+var_F6], si
0x14006eef6  mov     sil, [r12+rax]
0x14006eefa  mov     r12d, 9
0x14006ef00  mov     rax, [rbp+90h+var_98]
0x14006ef04  mov     [rbp+90h+var_109], sil
0x14006ef08  mov     sil, [r12+rax]
0x14006ef0c  mov     r12d, 0Ah
0x14006ef12  mov     rax, [rbp+90h+var_90]
0x14006ef16  mov     [rbp+90h+var_10A], sil
0x14006ef1a  mov     sil, [r12+rax]
0x14006ef1e  mov     r12d, 0Bh
0x14006ef24  mov     rax, [rbp+90h+var_88]
0x14006ef28  mov     [rbp+90h+var_10B], sil
0x14006ef2c  mov     sil, [r12+rax]
0x14006ef30  mov     r12d, 0Ch
0x14006ef36  mov     rax, [rbp+90h+var_80]
0x14006ef3a  mov     [rbp+90h+var_10C], sil
0x14006ef3e  mov     rsi, [rbp+90h+var_70]
0x14006ef42  mov     al, [r12+rax]
0x14006ef46  mov     r12, [rbp+90h+var_B0]
0x14006ef4a  mov     [rbp+90h+var_10D], al
0x14006ef4d  mov     al, [r9+r10]
0x14006ef51  mov     [rbp+90h+var_10E], al
0x14006ef54  mov     al, [rdx+r8]
0x14006ef58  mov     edx, [rcx+5Ch]
0x14006ef5b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ef62  mov     [rbp+90h+var_10F], al
0x14006ef65  lea     rax, WPP_GLOBAL_Control
0x14006ef6c  mov     dword ptr [rbp+90h+var_E0], edx
0x14006ef6f  cmp     rcx, rax
0x14006ef72  jz      short loc_14006EFA5
0x14006ef74  test    dword ptr [rcx+2Ch], 100000h
0x14006ef7b  jz      short loc_14006EFA5
0x14006ef7d  cmp     byte ptr [rcx+29h], 2
0x14006ef81  jb      short loc_14006EFA5
0x14006ef83  mov     eax, [rsi]
0x14006ef85  mov     r9d, ebx
0x14006ef88  mov     rcx, [rcx+18h]
0x14006ef8c  mov     dword ptr [rsp+1C0h+var_190], edx
0x14006ef90  mov     dword ptr [rsp+1C0h+var_198], r13d
0x14006ef95  mov     dword ptr [rsp+1C0h+var_1A0], eax
0x14006ef99  call    WPP_SF_DDDD
0x14006ef9e  mov     edx, dword ptr [rbp+90h+var_E0]
0x14006efa1  mov     r11b, [rbp+90h+var_110]
0x14006efa5  xor     ebx, ebx
0x14006efa7  test    r13d, r13d
0x14006efaa  jz      loc_14006F386
0x14006efb0  cmp     edx, r13d
0x14006efb3  jz      short loc_14006EFD2
0x14006efb5  mov     rcx, [rdi]; P
0x14006efb8  xor     edx, edx; Tag
0x14006efba  call    cs:__imp_ExFreePoolWithTag
0x14006efc1  nop     dword ptr [rax+rax+00h]
0x14006efc6  mov     [rdi], rbx
0x14006efc9  mov     rbx, [rbp+90h+var_60]
0x14006efcd  jmp     loc_14006EDE0
0x14006efd2  mov     edx, [rbp+90h+var_F0]
0x14006efd5  lea     rcx, [rdx+r13]
0x14006efd9  cmp     rcx, rdx
0x14006efdc  jb      short loc_14006EFFA
0x14006efde  mov     r9d, 0FFFFFFFFh
0x14006efe4  cmp     rcx, r9
0x14006efe7  ja      short loc_14006EFFA
0x14006efe9  mov     eax, [rsi]
0x14006efeb  cmp     rcx, rax
0x14006efee  ja      short loc_14006EFFA
0x14006eff0  cmp     r13d, 4
0x14006eff4  jnb     loc_14006F0C1
0x14006effa  mov     ebx, 0C000090Bh
0x14006efff  mov     r13, [rbp+90h+var_108]
0x14006f003  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006f00a  lea     rax, WPP_GLOBAL_Control
0x14006f011  cmp     rcx, rax
0x14006f014  jz      short loc_14006F03D
0x14006f016  test    dword ptr [rcx+2Ch], 100000h
0x14006f01d  jz      short loc_14006F03D
0x14006f01f  cmp     byte ptr [rcx+29h], 1
0x14006f023  jb      short loc_14006F03D
0x14006f025  mov     rcx, [rcx+18h]
0x14006f029  lea     r8, WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids
0x14006f030  mov     edx, 12h
0x14006f035  mov     r9d, ebx
0x14006f038  call    WPP_SF_d
0x14006f03d  mov     rcx, [rdi]; P
0x14006f040  test    rcx, rcx
0x14006f043  jz      short loc_14006F05A
0x14006f045  xor     edx, edx; Tag
0x14006f047  call    cs:__imp_ExFreePoolWithTag
0x14006f04e  nop     dword ptr [rax+rax+00h]
0x14006f053  mov     qword ptr [rdi], 0
0x14006f05a  mov     rax, [rbp+90h+var_D8]
0x14006f05e  mov     rcx, [rbp+90h+var_C8]
0x14006f062  mov     dword ptr [rsi], 0
0x14006f068  mov     qword ptr [rax], 0
0x14006f06f  mov     rax, [rbp+90h+var_D0]
0x14006f073  mov     dword ptr [r13+0], 0
0x14006f07b  mov     qword ptr [rax], 0
0x14006f082  mov     rax, [rbp+90h+var_C0]
0x14006f086  mov     qword ptr [r15], 0
0x14006f08d  mov     dword ptr [rcx], 0
0x14006f093  mov     dword ptr [r12], 0
0x14006f09b  mov     byte ptr [rax], 0
0x14006f09e  mov     eax, ebx
0x14006f0a0  mov     rcx, [rbp+90h+var_48]
0x14006f0a4  xor     rcx, rsp; StackCookie
0x14006f0a7  call    __security_check_cookie
0x14006f0ac  add     rsp, 188h
0x14006f0b3  pop     r15
0x14006f0b5  pop     r14
0x14006f0b7  pop     r13
0x14006f0b9  pop     r12
0x14006f0bb  pop     rdi
0x14006f0bc  pop     rsi
0x14006f0bd  pop     rbx
0x14006f0be  pop     rbp
0x14006f0bf  retn
0x14006f0c1  mov     rax, [rdi]
0x14006f0c4  lea     r15, [rdx+rax]
0x14006f0c8  cmp     dword ptr [r15], 100000h
0x14006f0cf  jz      loc_14006F194
0x14006f0d5  mov     rcx, [rbp+90h+var_D0]
0x14006f0d9  lea     r9, [rbp+90h+var_EC]
0x14006f0dd  mov     r13, [rbp+90h+var_108]
0x14006f0e1  lea     r8, [rbp+90h+var_78]
0x14006f0e5  mov     [rsp+1C0h+var_190], rcx
0x14006f0ea  mov     rdx, rax
0x14006f0ed  mov     rcx, [rbp+90h+var_D8]
0x14006f0f1  mov     [rsp+1C0h+var_198], r13
0x14006f0f6  mov     [rsp+1C0h+var_1A0], rcx
0x14006f0fb  mov     ecx, r14d
0x14006f0fe  call    Smb2RkfpConvertDeprecatedBlob
0x14006f103  mov     ebx, eax
0x14006f105  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006f10c  lea     rax, WPP_GLOBAL_Control
0x14006f113  mov     r14d, [rbp+90h+var_EC]
0x14006f117  cmp     rcx, rax
0x14006f11a  jz      short loc_14006F150
0x14006f11c  test    dword ptr [rcx+2Ch], 100000h
0x14006f123  jz      short loc_14006F150
0x14006f125  cmp     byte ptr [rcx+29h], 2
0x14006f129  jb      short loc_14006F150
0x14006f12b  mov     eax, [r13+0]
0x14006f12f  lea     r8, WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids
0x14006f136  mov     rcx, [rcx+18h]
0x14006f13a  mov     edx, 10h
0x14006f13f  mov     dword ptr [rsp+1C0h+var_198], eax
0x14006f143  mov     r9d, ebx
0x14006f146  mov     dword ptr [rsp+1C0h+var_1A0], r14d
0x14006f14b  call    WPP_SF_DDD
0x14006f150  xor     r15d, r15d
0x14006f153  test    ebx, ebx
0x14006f155  js      loc_14006F3D8
0x14006f15b  mov     rcx, [rdi]; P
0x14006f15e  xor     edx, edx; Tag
0x14006f160  call    cs:__imp_ExFreePoolWithTag
0x14006f167  nop     dword ptr [rax+rax+00h]
0x14006f16c  mov     rcx, [rbp+90h+var_100]
0x14006f170  mov     rax, [rbp+90h+var_78]
0x14006f174  mov     [rdi], rax
0x14006f177  mov     rax, [rbp+90h+var_C0]
0x14006f17b  mov     [rsi], r14d
0x14006f17e  mov     [rcx], r15
0x14006f181  mov     rcx, [rbp+90h+var_C8]
0x14006f185  mov     [rcx], r15d
0x14006f188  mov     [r12], r15d
0x14006f18c  mov     [rax], r15b
0x14006f18f  jmp     loc_14006F3AD
0x14006f194  cmp     r13d, 8
0x14006f198  jnb     short loc_14006F1A8
0x14006f19a  mov     r15, [rbp+90h+var_100]
0x14006f19e  mov     ebx, 0C000090Bh
0x14006f1a3  jmp     loc_14006EFFF
0x14006f1a8  mov     ecx, [r15+4]
0x14006f1ac  mov     eax, ecx
0x14006f1ae  sub     eax, 1
0x14006f1b1  jz      short loc_14006F20B
0x14006f1b3  cmp     eax, 1
0x14006f1b6  jnz     short loc_14006F19A
0x14006f1b8  cmp     r13d, 5Dh ; ']'
0x14006f1bc  jb      short loc_14006F19A
0x14006f1be  mov     rax, [rbp+90h+var_A8]
0x14006f1c2  mov     [rax], ecx
0x14006f1c4  mov     eax, [r15+4Ch]
  ... truncated ...
```
