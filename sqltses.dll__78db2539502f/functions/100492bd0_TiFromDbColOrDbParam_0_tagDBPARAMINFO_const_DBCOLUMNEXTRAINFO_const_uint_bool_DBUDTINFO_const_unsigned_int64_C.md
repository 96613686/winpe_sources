# TiFromDbColOrDbParam<0>(tagDBPARAMINFO const &,DBCOLUMNEXTRAINFO const *,uint,bool,DBUDTINFO const *,unsigned __int64,CTypeInfo &)

- ea: `0x100492bd0`
- end: `0x1004933c3`
- name: `??$TiFromDbColOrDbParam@$0A@@@YA?AW4EOledbMetadataError@@AEBUtagDBPARAMINFO@@PEBUDBCOLUMNEXTRAINFO@@I_NPEBUDBUDTINFO@@_KAEAVCTypeInfo@@@Z`
- size: `2035`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x100401450`
- `0x100401480`
- `0x100403530`
- `0x100431480`
- `0x100438180`
- `0x100492bd0`

## import_xrefs

- `sqldk!SystemThread_TlsIndex` at `0x100493095`
- `sqldk!SystemThread_TlsOffset` at `0x10049309e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004930b9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004930b9`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100492f3a`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100492f85`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100492f3a`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100492f85`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100492f49`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100492f94`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100492f49`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100492f94`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100492f5c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100492fa7`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100492f5c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100492fa7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TiFromDbColOrDbParam<0>(
        int *a1,
        __int64 a2,
        char a3,
        char a4,
        _QWORD *a5,
        unsigned __int64 a6,
        unsigned __int8 *a7)
{
  int *v8; // rdx
  int v9; // r10d
  bool v10; // r15
  char *v11; // r12
  int v12; // edi
  char v13; // r11
  unsigned __int8 v14; // r13
  unsigned int v15; // esi
  int v16; // r14d
  unsigned __int8 v17; // bl
  int v18; // r8d
  __int16 *v19; // r9
  int v20; // r8d
  struct CSessionTraceFlags *v21; // rax
  __int64 v22; // rcx
  struct CSessionTraceFlags *v23; // rax
  __int16 v25; // cx
  __int64 v26; // rbx
  __int64 v27; // rsi
  unsigned int v28; // eax
  int v29; // r15d
  __int64 v30; // rcx
  unsigned __int8 *v31; // rbx
  __int64 *v32; // rcx
  __int64 v33; // rax
  __int64 *v34; // rcx
  __int64 v35; // rax
  __int16 *v36; // r9
  __int64 v37; // r12
  bool v38; // al
  int v39; // ecx
  unsigned int CIDFromLCIDWithValidation; // edx
  unsigned int v41; // r9d
  int v42; // edx
  int v43; // ecx
  int v44; // r8d
  unsigned int v45; // edx
  int v46; // r9d
  unsigned __int8 v47; // [rsp+30h] [rbp-40h]
  char v48; // [rsp+31h] [rbp-3Fh]
  int v49; // [rsp+38h] [rbp-38h]
  __int128 v50; // [rsp+48h] [rbp-28h] BYREF
  __int128 v51; // [rsp+58h] [rbp-18h]
  int *v52; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int *v53; // [rsp+B8h] [rbp+48h]

  v53 = (unsigned int *)a2;
  v52 = a1;
  v8 = a1;
  v9 = *a1;
  v10 = (*a1 & 0x40) != 0;
  if ( !a2 || (v48 = 1, (*(_BYTE *)(a2 + 32) & 1) == 0) )
    v48 = 0;
  v11 = 0;
  v12 = 0;
  v49 = 0;
  v13 = 0;
  v47 = 0;
  v14 = 0;
  v15 = 7;
  v16 = 1;
  switch ( a1[10] & 0xBFFF )
  {
    case 2:
      v17 = 52;
      goto LABEL_95;
    case 3:
      v17 = 56;
      goto LABEL_95;
    case 4:
      v17 = 59;
      goto LABEL_95;
    case 5:
      v17 = 62;
      goto LABEL_95;
    case 6:
      v17 = 60;
      goto LABEL_95;
    case 7:
      v17 = 61;
      v12 = 5;
      v18 = 0;
      goto LABEL_96;
    case 8:
    case 0x82:
      if ( (a3 & 1) != 0 && (v9 & 0x80u) != 0 && a6 == -1 )
      {
        v17 = -25;
        a6 = 0xFFFF;
        v18 = 1;
        goto LABEL_96;
      }
      v49 = 1;
      if ( (v9 & 0x80u) == 0 && a6 <= 0xFA0 )
      {
        v17 = -25;
        v18 = 1;
        goto LABEL_96;
      }
      v17 = 99;
      goto LABEL_95;
    case 0xB:
      v17 = 104;
      goto LABEL_95;
    case 0xC:
      v17 = -25;
      v12 = 10;
      a6 = 8000;
      v10 = 1;
      v18 = 1;
      goto LABEL_96;
    case 0xE:
      v17 = 106;
      v13 = 1;
      v18 = 0;
      goto LABEL_87;
    case 0x10:
      v17 = 108;
      v12 = 1;
      v14 = 3;
      v47 = 0;
      v18 = 0;
      v13 = 1;
      v19 = &CTypeInfo::tiBit;
      goto LABEL_101;
    case 0x11:
      v17 = 48;
      goto LABEL_95;
    case 0x12:
      v17 = 108;
      v12 = 2;
      v14 = 5;
      v47 = 0;
      v18 = 0;
      v13 = 1;
      v19 = &CTypeInfo::tiBit;
      goto LABEL_101;
    case 0x13:
      v17 = 108;
      v12 = 3;
      v14 = 10;
      v47 = 0;
      v18 = 0;
      v13 = 1;
      v19 = &CTypeInfo::tiBit;
      goto LABEL_101;
    case 0x14:
      v17 = 127;
      goto LABEL_95;
    case 0x15:
      v17 = 108;
      v12 = 4;
      v14 = 20;
      v47 = 0;
      v18 = 0;
      v13 = 1;
      v19 = &CTypeInfo::tiBit;
      goto LABEL_101;
    case 0x40:
    case 0x87:
      v12 = 8;
      if ( (a3 & 4) != 0 )
      {
        if ( *((_BYTE *)a1 + 43) || (a3 & 8) == 0 )
        {
          v17 = 61;
          v18 = 0;
        }
        else
        {
          v17 = 58;
          v18 = 0;
        }
      }
      else
      {
        v17 = 42;
        v18 = 0;
      }
      goto LABEL_96;
    case 0x48:
      v17 = 36;
      goto LABEL_95;
    case 0x80:
      if ( (a3 & 1) != 0 )
      {
        if ( (v9 & 0x80u) != 0 )
        {
          if ( a6 == -1 )
          {
            v17 = -91;
            a6 = 0xFFFF;
            v18 = 1;
            goto LABEL_96;
          }
          goto LABEL_32;
        }
      }
      else if ( (v9 & 0x80u) != 0 )
      {
        goto LABEL_32;
      }
      if ( a6 <= 0x1F40 )
      {
        v17 = -91;
        v18 = 1;
        goto LABEL_96;
      }
LABEL_32:
      v17 = 34;
      goto LABEL_95;
    case 0x81:
      if ( (a3 & 1) != 0 )
      {
        if ( (v9 & 0x80u) != 0 )
        {
          if ( a6 == -1 )
          {
            v17 = -89;
            a6 = 0xFFFF;
            v18 = 1;
            goto LABEL_96;
          }
          goto LABEL_40;
        }
      }
      else if ( (v9 & 0x80u) != 0 )
      {
        goto LABEL_40;
      }
      if ( a6 <= 0x1F40 )
      {
        v17 = -89;
        v18 = 1;
        goto LABEL_96;
      }
LABEL_40:
      v17 = 35;
LABEL_95:
      v18 = 0;
      goto LABEL_96;
    case 0x83:
      v17 = 108;
      v13 = 1;
      v18 = 0;
      goto LABEL_87;
    case 0x84:
      v17 = -16;
      goto LABEL_95;
    case 0x85:
      v12 = 6;
      v17 = 40;
      if ( (a3 & 2) == 0 )
        v17 = 61;
      v18 = 0;
      goto LABEL_86;
    case 0x86:
      v12 = 7;
      v20 = a3 & 2;
      v17 = 41;
      if ( !v20 )
        v17 = 61;
      v15 = 0;
      if ( (v20 & 2) == 0 )
        v15 = 7;
      v18 = 0;
      goto LABEL_86;
    case 0x8B:
      if ( *(char *)(CGlobalTraceFlags::GetUlTraceFlags(a1, a1) + 913) < 0
        || (v21 = PSessTraceFlags()) != 0 && CSessionTraceFlags::CheckSessionTraceInternal(v21, 0x1C8Fu) )
      {
        v17 = -25;
        v18 = 1;
        a6 = 384;
      }
      else
      {
        v17 = 108;
        v8 = v52;
        v22 = *((unsigned __int8 *)v52 + 42);
        if ( (unsigned __int8)(v22 - 1) <= 0x25u && (unsigned __int8)v22 >= *((_BYTE *)v52 + 43) )
        {
          v13 = 1;
          v18 = 0;
          goto LABEL_85;
        }
        if ( (*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags(v22, v52) + 914) & 4) != 0
          || (v23 = PSessTraceFlags()) != 0 && CSessionTraceFlags::CheckSessionTraceInternal(v23, 0x1C92u) )
        {
          v14 = 38;
          v47 = 10;
          v18 = 0;
        }
        else
        {
          v17 = 62;
          v18 = 0;
        }
      }
      v8 = v52;
      v13 = 0;
LABEL_85:
      v49 = v18;
LABEL_86:
      if ( v13 )
      {
LABEL_87:
        v14 = *((_BYTE *)v8 + 42);
        if ( !v14 )
          return 2;
        if ( v14 > 0x26u )
          return 4;
        v47 = *((_BYTE *)v8 + 43);
        if ( v47 > v14 )
          return 3;
        goto LABEL_22;
      }
LABEL_20:
      if ( v17 == 108 )
      {
        v13 = 1;
LABEL_22:
        v19 = &CTypeInfo::tiBit;
        goto LABEL_101;
      }
LABEL_96:
      v19 = &CTypeInfo::tiBit;
      if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsVarTime + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v17)) )
      {
        if ( v15 > 7 )
        {
          v25 = v8[10] & 0xBFFF;
          if ( (unsigned __int16)(v25 - 145) <= 1u || (LOBYTE(v15) = 0, v25 == 135) )
            LOBYTE(v15) = 7;
        }
      }
LABEL_101:
      if ( v17 != 0xF0 )
      {
        if ( !*((_BYTE *)&CTypeInfo::sxm_rgfIsVarTime + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v17)) )
        {
          if ( v13 )
          {
            CTypeInfo::InitWithMaxLen((CTypeInfo *)&v50, v17, *((unsigned __int8 *)&qword_1008644E8[255] + v14 + 7));
            BYTE2(v51) = v14;
            BYTE3(v51) = v47;
            if ( !v10 )
              BYTE1(v50) |= 1u;
          }
          else
          {
            if ( !v18 )
            {
              CTypeInfo::Init((CTypeInfo *)&v50, v17);
              if ( !v10 )
                BYTE1(v50) |= 1u;
              if ( *((_BYTE *)v36 + *((unsigned __int8 *)v36 + (unsigned __int8)v50 + 4566624) + 4566976)
                || (((_BYTE)v50 - 35) & 0xBF) == 0 )
              {
                v38 = CTypeInfo::FCharacterOrEncryptedCharacter((CTypeInfo *)&v50);
                v39 = DWORD1(v51);
                if ( v38 )
                  v39 = -1;
                DWORD1(v51) = v39;
              }
              goto LABEL_141;
            }
            CIDFromLCIDWithValidation = -1;
            if ( v49 )
            {
              if ( v53 )
              {
                v41 = v53[1];
                v42 = ((v41 & 1) << 12) | 0x2000;
                if ( (v41 & 2) == 0 )
                  v42 = (v53[1] & 1) << 12;
                v43 = v42 | 0x4000;
                if ( (v41 & 0x10000) == 0 )
                  v43 = v42;
                v44 = v43 | 0x8000;
                if ( (v41 & 0x20000) == 0 )
                  v44 = v43;
                v45 = v44 | 0x10000;
                if ( (v41 & 0x800000) == 0 )
                  v45 = v44;
                if ( (v41 & 0x400000) != 0 )
                  v45 = 2048;
                CIDFromLCIDWithValidation = MakeCIDFromLCIDWithValidation(*v53, v45);
              }
              v46 = 2 * a6;
            }
            else
            {
              v46 = a6;
            }
            LODWORD(v52) = CIDFromLCIDWithValidation;
            CTypeInfo::CTypeInfo((CTypeInfo *)&v50, v17, v10, v46, (const struct CDefaultCollation *)&v52);
            if ( v48 )
              BYTE1(v50) |= 0x20u;
          }
          v31 = a7;
          *(_OWORD *)a7 = v50;
          *((_OWORD *)v31 + 1) = v51;
LABEL_160:
          v36 = &CTypeInfo::tiBit;
          goto LABEL_161;
        }
        CTypeInfo::Init((CTypeInfo *)&v50, v17);
        if ( !v10 )
          BYTE1(v50) |= 1u;
        switch ( (unsigned __int8)v50 )
        {
          case ')':
            v37 = 4LL * (unsigned __int8)v15 + 4604760;
            break;
          case '*':
            v37 = 4LL * (unsigned __int8)v15 + 4846464;
            break;
          case '+':
            v37 = 4LL * (unsigned __int8)v15 + 4610376;
            break;
          default:
LABEL_129:
            LOWORD(v51) = *(_WORD *)v11;
            BYTE2(v51) = v11[2];
            BYTE3(v51) = v15;
LABEL_141:
            v31 = a7;
            *(_OWORD *)a7 = v50;
            *((_OWORD *)v31 + 1) = v51;
LABEL_161:
            if ( v12 )
              *((_DWORD *)v31 + 1) = (unsigned __int8)v12;
            if ( *((_BYTE *)v36 + *((unsigned __int8 *)v36 + *v31 + 4566624) + 4570496) )
              v31[1] |= 2u;
            return 0;
        }
        v11 = (char *)v36 + v37;
        goto LABEL_129;
      }
      v26 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v27 = *(_QWORD *)(v26 + 256);
      if ( !v27 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v27 = *(_QWORD *)(v26 + 256);
      }
      *((_QWORD *)&v50 + 1) = v27;
      v28 = *(_DWORD *)(v27 + 800);
      v29 = (v28 >> 11) & 1;
      DWORD1(v50) = v29;
      if ( (v28 & 4) != 0 && (v30 = *(_QWORD *)(v27 + 608)) != 0 )
      {
        LODWORD(v50) = 1;
        (*(void (__fastcall **)(__int64, __int64, __int64, __int16 *))(*(_QWORD *)v30 + 16LL))(v30, v27, 1, v19);
      }
      else
      {
        v16 = 0;
        LODWORD(v50) = 0;
      }
      if ( a5 )
      {
        v31 = a7;
        if ( (*(unsigned __int8 (__fastcall **)(struct ISqlTypeSystemExtender_IUdtProvider *, _QWORD, unsigned __int8 *))(*(_QWORD *)x_pIUdtProvider + 32LL))(
               x_pIUdtProvider,
               *a5,
               a7) )
        {
          if ( v16 )
          {
            v32 = *(__int64 **)(v27 + 608);
            v33 = *v32;
            if ( v29 == 1 )
              (*(void (__fastcall **)(__int64 *, __int64))(v33 + 24))(v32, v27);
            else
              (*(void (__fastcall **)(__int64 *, __int64))(v33 + 8))(v32, v27);
          }
          goto LABEL_160;
        }
      }
      if ( v16 )
      {
        v34 = *(__int64 **)(v27 + 608);
        v35 = *v34;
        if ( v29 == 1 )
        {
          (*(void (__fastcall **)(__int64 *, __int64))(v35 + 24))(v34, v27);
          return 5;
        }
        (*(void (__fastcall **)(__int64 *, __int64))(v35 + 8))(v34, v27);
      }
      return 5;
    case 0x8D:
      v17 = -15;
      goto LABEL_95;
    case 0x90:
      v17 = 98;
      v12 = 11;
      v10 = 1;
      v18 = 0;
      goto LABEL_96;
    case 0x91:
      v12 = 12;
      v17 = 41;
      v15 = *((unsigned __int8 *)a1 + 43);
      v18 = 0;
      goto LABEL_96;
    case 0x92:
      v12 = 13;
      v17 = 43;
      v15 = *((unsigned __int8 *)a1 + 43);
      v18 = 0;
      goto LABEL_96;
    case 0xE8:
      v17 = 61;
      goto LABEL_18;
    case 0xE9:
      v17 = 58;
      goto LABEL_18;
    case 0xEA:
      v17 = 122;
      goto LABEL_18;
    case 0xEC:
      v17 = 98;
LABEL_18:
      if ( !a4 )
        return 1;
      v18 = 0;
      goto LABEL_20;
    default:
      return 1;
  }
}

```

## disassembly

```asm
0x100492bd0  mov     [rsp-38h+arg_8], rdx
0x100492bd5  mov     [rsp-38h+arg_0], rcx
0x100492bda  push    rbp
0x100492bdb  push    rsi
0x100492bdc  push    rdi
0x100492bdd  push    r12
0x100492bdf  push    r13
0x100492be1  push    r14
0x100492be3  push    r15
0x100492be5  mov     rbp, rsp
0x100492be8  sub     rsp, 70h
0x100492bec  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x100492bf4  mov     [rsp+70h+arg_10], rbx
0x100492bfc  mov     rax, rdx
0x100492bff  mov     rdx, rcx
0x100492c02  mov     r10d, [rcx]
0x100492c05  mov     r15d, r10d
0x100492c08  shr     r15d, 6
0x100492c0c  and     r15b, 1
0x100492c10  test    rax, rax
0x100492c13  jz      short loc_100492C1F
0x100492c15  test    byte ptr [rax+20h], 1
0x100492c19  mov     [rbp+var_3F], 1
0x100492c1d  jnz     short loc_100492C23
0x100492c1f  mov     [rbp+var_3F], 0
0x100492c23  xor     r12d, r12d
0x100492c26  mov     edi, r12d
0x100492c29  mov     [rbp+var_38], r12d
0x100492c2d  xor     r11b, r11b
0x100492c30  mov     [rbp+var_40], dil
0x100492c34  xor     r13b, r13b
0x100492c37  lea     esi, [r12+7]
0x100492c3c  movzx   eax, word ptr [rcx+28h]
0x100492c40  btr     eax, 0Eh
0x100492c44  add     eax, 0FFFFFFFEh; switch 235 cases
0x100492c47  cmp     eax, 0EAh
0x100492c4c  ja      def_100492C72; jumptable 0000000100492C72 default case, cases 9,10,13,15,22-63,65-71,73-127,136-138,140,142,143,147-231,235
0x100492c52  cdqe
0x100492c54  lea     rbx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x100492c5b  movzx   eax, ds:(byte_10049344C - 100400000h)[rbx+rax]
0x100492c63  mov     ecx, ds:(jpt_100492C72 - 100400000h)[rbx+rax*4]
0x100492c6a  add     rcx, rbx
0x100492c6d  lea     r14d, [r12+1]
0x100492c72  jmp     rcx; switch jump
0x100492c74  mov     bl, 34h ; '4'; jumptable 0000000100492C72 case 2
0x100492c76  jmp     loc_10049302E
0x100492c7b  mov     bl, 38h ; '8'; jumptable 0000000100492C72 case 3
0x100492c7d  jmp     loc_10049302E
0x100492c82  mov     bl, 7Fh; jumptable 0000000100492C72 case 20
0x100492c84  jmp     loc_10049302E
0x100492c89  mov     bl, 3Bh ; ';'; jumptable 0000000100492C72 case 4
0x100492c8b  jmp     loc_10049302E
0x100492c90  mov     bl, 3Eh ; '>'; jumptable 0000000100492C72 case 5
0x100492c92  jmp     loc_10049302E
0x100492c97  mov     bl, 3Ch ; '<'; jumptable 0000000100492C72 case 6
0x100492c99  jmp     loc_10049302E
0x100492c9e  mov     bl, 68h ; 'h'; jumptable 0000000100492C72 case 11
0x100492ca0  jmp     loc_10049302E
0x100492ca5  mov     bl, 30h ; '0'; jumptable 0000000100492C72 case 17
0x100492ca7  jmp     loc_10049302E
0x100492cac  mov     bl, 24h ; '$'; jumptable 0000000100492C72 case 72
0x100492cae  jmp     loc_10049302E
0x100492cb3  mov     bl, 3Dh ; '='; jumptable 0000000100492C72 case 232
0x100492cb5  jmp     short loc_100492CC1
0x100492cb7  mov     bl, 3Ah ; ':'; jumptable 0000000100492C72 case 233
0x100492cb9  jmp     short loc_100492CC1
0x100492cbb  mov     bl, 7Ah ; 'z'; jumptable 0000000100492C72 case 234
0x100492cbd  jmp     short loc_100492CC1
0x100492cbf  mov     bl, 62h ; 'b'; jumptable 0000000100492C72 case 236
0x100492cc1  test    r9b, r9b
0x100492cc4  jz      def_100492C72; jumptable 0000000100492C72 default case, cases 9,10,13,15,22-63,65-71,73-127,136-138,140,142,143,147-231,235
0x100492cca  mov     r8d, edi
0x100492ccd  mov     r10d, esi
0x100492cd0  cmp     bl, 6Ch ; 'l'
0x100492cd3  jnz     loc_100493034
0x100492cd9  movzx   r11d, r14b
0x100492cdd  lea     r9, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x100492ce4  jmp     loc_100493083
0x100492ce9  mov     bl, 6Ch ; 'l'; jumptable 0000000100492C72 case 131
0x100492ceb  movzx   r11d, r14b
0x100492cef  mov     r8d, edi
0x100492cf2  jmp     loc_100492FE8
0x100492cf7  mov     bl, 6Ah ; 'j'; jumptable 0000000100492C72 case 14
0x100492cf9  movzx   r11d, r14b
0x100492cfd  mov     r8d, edi
0x100492d00  jmp     loc_100492FE8
0x100492d05  test    r14b, r8b; jumptable 0000000100492C72 case 128
0x100492d08  jz      short loc_100492D28
0x100492d0a  test    r10b, r10b
0x100492d0d  jns     short loc_100492D2D
0x100492d0f  cmp     [rbp+arg_28], 0FFFFFFFFFFFFFFFFh
0x100492d14  jnz     short loc_100492D41
0x100492d16  mov     bl, 0A5h
0x100492d18  mov     [rbp+arg_28], 0FFFFh
0x100492d20  mov     r8d, r14d
0x100492d23  jmp     loc_100493031
0x100492d28  test    r10b, r10b
0x100492d2b  js      short loc_100492D41
0x100492d2d  cmp     [rbp+arg_28], 1F40h
0x100492d35  ja      short loc_100492D41
0x100492d37  mov     bl, 0A5h
0x100492d39  mov     r8d, r14d
0x100492d3c  jmp     loc_100493031
0x100492d41  mov     bl, 22h ; '"'
0x100492d43  jmp     loc_10049302E
0x100492d48  test    r14b, r8b; jumptable 0000000100492C72 case 129
0x100492d4b  jz      short loc_100492D6B
0x100492d4d  test    r10b, r10b
0x100492d50  jns     short loc_100492D70
0x100492d52  cmp     [rbp+arg_28], 0FFFFFFFFFFFFFFFFh
0x100492d57  jnz     short loc_100492D84
0x100492d59  mov     bl, 0A7h
0x100492d5b  mov     [rbp+arg_28], 0FFFFh
0x100492d63  mov     r8d, r14d
0x100492d66  jmp     loc_100493031
0x100492d6b  test    r10b, r10b
0x100492d6e  js      short loc_100492D84
0x100492d70  cmp     [rbp+arg_28], 1F40h
0x100492d78  ja      short loc_100492D84
0x100492d7a  mov     bl, 0A7h
0x100492d7c  mov     r8d, r14d
0x100492d7f  jmp     loc_100493031
0x100492d84  mov     bl, 23h ; '#'
0x100492d86  jmp     loc_10049302E
0x100492d8b  test    r14b, r8b; jumptable 0000000100492C72 cases 8,130
0x100492d8e  jz      short loc_100492DAE
0x100492d90  test    r10b, r10b
0x100492d93  jns     short loc_100492DAE
0x100492d95  cmp     [rbp+arg_28], 0FFFFFFFFFFFFFFFFh
0x100492d9a  jnz     short loc_100492DAE
0x100492d9c  mov     bl, 0E7h
0x100492d9e  mov     [rbp+arg_28], 0FFFFh
0x100492da6  mov     r8d, r14d
0x100492da9  jmp     loc_100493031
0x100492dae  mov     [rbp+var_38], r14d
0x100492db2  test    r10b, r10b
0x100492db5  js      short loc_100492DCB
0x100492db7  cmp     [rbp+arg_28], 0FA0h
0x100492dbf  ja      short loc_100492DCB
0x100492dc1  mov     bl, 0E7h
0x100492dc3  mov     r8d, r14d
0x100492dc6  jmp     loc_100493031
0x100492dcb  mov     bl, 63h ; 'c'
0x100492dcd  jmp     loc_10049302E
0x100492dd2  mov     bl, 6Ch ; 'l'; jumptable 0000000100492C72 case 16
0x100492dd4  mov     edi, r14d
0x100492dd7  mov     r13b, 3
0x100492dda  mov     [rbp+var_40], r11b
0x100492dde  mov     r8d, r12d
0x100492de1  movzx   r11d, r14b
0x100492de5  lea     r9, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x100492dec  jmp     loc_100493083
0x100492df1  mov     bl, 6Ch ; 'l'; jumptable 0000000100492C72 case 18
0x100492df3  mov     edi, 2
0x100492df8  mov     r13b, 5
0x100492dfb  mov     [rbp+var_40], r11b
0x100492dff  mov     r8d, r12d
0x100492e02  movzx   r11d, r14b
0x100492e06  lea     r9, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x100492e0d  jmp     loc_100493083
0x100492e12  mov     bl, 6Ch ; 'l'; jumptable 0000000100492C72 case 19
0x100492e14  mov     edi, 3
0x100492e19  mov     r13b, 0Ah
0x100492e1c  mov     [rbp+var_40], r11b
0x100492e20  mov     r8d, r12d
0x100492e23  movzx   r11d, r14b
0x100492e27  lea     r9, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x100492e2e  jmp     loc_100493083
0x100492e33  mov     bl, 6Ch ; 'l'; jumptable 0000000100492C72 case 21
0x100492e35  mov     edi, 4
0x100492e3a  mov     r13b, 14h
0x100492e3d  mov     [rbp+var_40], r11b
0x100492e41  mov     r8d, r12d
0x100492e44  movzx   r11d, r14b
0x100492e48  lea     r9, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x100492e4f  jmp     loc_100493083
0x100492e54  mov     bl, 3Dh ; '='; jumptable 0000000100492C72 case 7
0x100492e56  mov     edi, 5
0x100492e5b  mov     r8d, r12d
0x100492e5e  jmp     loc_100493031
0x100492e63  mov     r10d, esi; jumptable 0000000100492C72 case 134
0x100492e66  mov     edi, esi
0x100492e68  and     r8d, 2
0x100492e6c  mov     ebx, 29h ; ')'
0x100492e71  mov     ecx, 3Dh ; '='
0x100492e76  cmovz   ebx, ecx
0x100492e79  mov     esi, r12d
0x100492e7c  bt      r8d, 1
0x100492e81  cmovnb  esi, edi
0x100492e84  mov     r8d, r12d
0x100492e87  jmp     loc_100492FDF
0x100492e8c  mov     edi, 6; jumptable 0000000100492C72 case 133
0x100492e91  test    r8b, 2
0x100492e95  mov     ebx, 28h ; '('
0x100492e9a  mov     ecx, 3Dh ; '='
0x100492e9f  cmovz   ebx, ecx
0x100492ea2  mov     r8d, r12d
0x100492ea5  jmp     loc_100492FDC
0x100492eaa  mov     edi, 0Ch; jumptable 0000000100492C72 case 145
0x100492eaf  mov     bl, 29h ; ')'
0x100492eb1  movzx   esi, byte ptr [rdx+2Bh]
0x100492eb5  mov     r8d, r12d
0x100492eb8  lea     r10d, [rdi-5]
0x100492ebc  jmp     loc_100493034
0x100492ec1  mov     edi, 0Dh; jumptable 0000000100492C72 case 146
0x100492ec6  mov     bl, 2Bh ; '+'
0x100492ec8  movzx   esi, byte ptr [rdx+2Bh]
0x100492ecc  mov     r8d, r12d
0x100492ecf  lea     r10d, [rdi-6]
0x100492ed3  jmp     loc_100493034
0x100492ed8  mov     edi, 8; jumptable 0000000100492C72 cases 64,135
0x100492edd  test    r8b, 4
0x100492ee1  jz      short loc_100492F02
0x100492ee3  cmp     [rdx+2Bh], r11b
0x100492ee7  jnz     short loc_100492EF8
0x100492ee9  test    dil, r8b
0x100492eec  jz      short loc_100492EF8
0x100492eee  mov     bl, 3Ah ; ':'
0x100492ef0  mov     r8d, r12d
0x100492ef3  jmp     loc_100493031
0x100492ef8  mov     bl, 3Dh ; '='
0x100492efa  mov     r8d, r12d
0x100492efd  jmp     loc_100493031
0x100492f02  mov     bl, 2Ah ; '*'
0x100492f04  mov     r8d, r12d
0x100492f07  jmp     loc_100493031
0x100492f0c  mov     bl, 62h ; 'b'; jumptable 0000000100492C72 case 144
0x100492f0e  mov     edi, 0Bh
0x100492f13  movzx   r15d, r14b
0x100492f17  mov     r8d, r12d
0x100492f1a  jmp     loc_100493031
0x100492f1f  mov     bl, 0E7h; jumptable 0000000100492C72 case 12
0x100492f21  mov     edi, 0Ah
0x100492f26  mov     [rbp+arg_28], 1F40h
0x100492f2e  movzx   r15d, r14b
0x100492f32  mov     r8d, r14d
0x100492f35  jmp     loc_100493031
0x100492f3a  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; jumptable 0000000100492C72 case 139
0x100492f40  cmp     [rax+391h], dil
0x100492f47  jl      short loc_100492FC4
0x100492f49  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x100492f4f  test    rax, rax
0x100492f52  jz      short loc_100492F66
0x100492f54  mov     edx, 1C8Fh
0x100492f59  mov     rcx, rax
0x100492f5c  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100492f62  test    eax, eax
0x100492f64  jnz     short loc_100492FC4
0x100492f66  mov     bl, 6Ch ; 'l'
0x100492f68  mov     rdx, [rbp+arg_0]
0x100492f6c  movzx   ecx, byte ptr [rdx+2Ah]
0x100492f70  lea     eax, [rcx-1]
0x100492f73  cmp     al, 25h ; '%'
0x100492f75  ja      short loc_100492F85
0x100492f77  cmp     cl, [rdx+2Bh]
0x100492f7a  jb      short loc_100492F85
0x100492f7c  movzx   r11d, r14b
0x100492f80  mov     r8d, edi
0x100492f83  jmp     short loc_100492FD8
0x100492f85  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x100492f8b  test    byte ptr [rax+392h], 4
0x100492f92  jnz     short loc_100492FB8
0x100492f94  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x100492f9a  test    rax, rax
0x100492f9d  jz      short loc_100492FB1
0x100492f9f  mov     edx, 1C92h
0x100492fa4  mov     rcx, rax
0x100492fa7  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100492fad  test    eax, eax
0x100492faf  jnz     short loc_100492FB8
0x100492fb1  mov     bl, 3Eh ; '>'
0x100492fb3  mov     r8d, edi
0x100492fb6  jmp     short loc_100492FD1
0x100492fb8  mov     r13b, 26h ; '&'
0x100492fbb  mov     [rbp+var_40], 0Ah
0x100492fbf  mov     r8d, edi
0x100492fc2  jmp     short loc_100492FD1
0x100492fc4  mov     bl, 0E7h
0x100492fc6  mov     r8d, r14d
0x100492fc9  mov     [rbp+arg_28], 180h
0x100492fd1  mov     rdx, [rbp+arg_0]
0x100492fd5  xor     r11b, r11b
0x100492fd8  mov     [rbp+var_38], r8d
0x100492fdc  mov     r10d, esi
0x100492fdf  test    r11b, r11b
0x100492fe2  jz      loc_100492CD0
0x100492fe8  movzx   r13d, byte ptr [rdx+2Ah]
0x100492fed  test    r13b, r13b
0x100492ff0  jnz     short loc_100492FFC
0x100492ff2  mov     eax, 2
0x100492ff7  jmp     loc_1004933AB
0x100492ffc  cmp     r13b, 26h ; '&'
0x100493000  jbe     short loc_10049300C
0x100493002  mov     eax, 4
0x100493007  jmp     loc_1004933AB
0x10049300c  movzx   r9d, byte ptr [rdx+2Bh]
0x100493011  mov     [rbp+var_40], r9b
0x100493015  cmp     r9b, r13b
0x100493018  jbe     loc_100492CDD
0x10049301e  mov     eax, 3
  ... truncated ...
```
