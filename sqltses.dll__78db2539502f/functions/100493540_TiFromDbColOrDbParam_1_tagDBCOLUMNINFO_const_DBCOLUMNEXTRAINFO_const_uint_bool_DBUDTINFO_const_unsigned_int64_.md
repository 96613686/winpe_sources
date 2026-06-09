# TiFromDbColOrDbParam<1>(tagDBCOLUMNINFO const &,DBCOLUMNEXTRAINFO const *,uint,bool,DBUDTINFO const *,unsigned __int64,CTypeInfo &)

- ea: `0x100493540`
- end: `0x100493d85`
- name: `??$TiFromDbColOrDbParam@$00@@YA?AW4EOledbMetadataError@@AEBUtagDBCOLUMNINFO@@PEBUDBCOLUMNEXTRAINFO@@I_NPEBUDBUDTINFO@@_KAEAVCTypeInfo@@@Z`
- size: `2117`
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
- `0x100493540`

## import_xrefs

- `sqldk!SystemThread_TlsIndex` at `0x100493aa2`
- `sqldk!SystemThread_TlsOffset` at `0x100493aab`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100493ac6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100493ac6`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1004938d5`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100493921`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1004938d5`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100493921`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1004938e4`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100493930`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1004938e4`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100493930`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1004938f7`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100493943`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1004938f7`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100493943`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TiFromDbColOrDbParam<1>(
        __int64 a1,
        __int64 a2,
        char a3,
        char a4,
        _QWORD *a5,
        unsigned __int64 a6,
        unsigned __int8 *a7)
{
  unsigned int v8; // ebx
  char *v9; // r12
  int v10; // esi
  int v11; // r11d
  char v12; // r10
  unsigned __int8 v13; // r13
  unsigned int v14; // edi
  int v15; // r14d
  unsigned __int8 v16; // bl
  int v17; // edx
  __int16 *v18; // r9
  int v19; // r8d
  struct CSessionTraceFlags *v20; // rax
  unsigned __int8 v21; // cl
  int v22; // edx
  struct CSessionTraceFlags *v23; // rax
  __int16 v25; // cx
  __int16 *v26; // r9
  __int64 v27; // r12
  __int64 v28; // rbx
  __int64 v29; // rdi
  unsigned int v30; // eax
  int v31; // r15d
  __int64 v32; // rcx
  unsigned __int8 *v33; // rbx
  __int64 *v34; // rcx
  __int64 v35; // rax
  __int64 *v36; // rcx
  __int64 v37; // rax
  bool v38; // al
  int v39; // ecx
  unsigned int CIDFromLCIDWithValidation; // edx
  unsigned int v41; // r9d
  int v42; // edx
  int v43; // ecx
  int v44; // r8d
  unsigned int v45; // edx
  int v46; // r9d
  bool v47; // [rsp+30h] [rbp-30h]
  char v48; // [rsp+31h] [rbp-2Fh]
  char v49; // [rsp+32h] [rbp-2Eh]
  int v50; // [rsp+34h] [rbp-2Ch]
  __int128 v51; // [rsp+40h] [rbp-20h] BYREF
  __int128 v52; // [rsp+50h] [rbp-10h]
  unsigned __int8 v53; // [rsp+A0h] [rbp+40h]
  unsigned int *v54; // [rsp+A8h] [rbp+48h] BYREF

  v54 = (unsigned int *)a2;
  v8 = *(_DWORD *)(a1 + 24);
  v47 = (v8 & 0x60) != 0;
  if ( !a2 || (v49 = 1, (*(_BYTE *)(a2 + 32) & 1) == 0) )
    v49 = 0;
  v9 = 0;
  v10 = 0;
  v50 = 0;
  v11 = 0;
  v12 = 0;
  v48 = 0;
  v53 = 0;
  v13 = 0;
  v14 = 7;
  v15 = 1;
  switch ( *(_WORD *)(a1 + 40) & 0xBFFF )
  {
    case 2:
      v16 = 52;
      goto LABEL_100;
    case 3:
      v16 = 56;
      goto LABEL_100;
    case 4:
      v16 = 59;
      goto LABEL_100;
    case 5:
      v16 = 62;
      goto LABEL_100;
    case 6:
      v16 = 60;
      goto LABEL_100;
    case 7:
      v16 = 61;
      v10 = 5;
      v17 = 0;
      goto LABEL_101;
    case 8:
    case 0x82:
      if ( (a3 & 1) != 0 && (v8 & 0x80u) != 0 && a6 == -1 )
      {
        v16 = -25;
        v17 = 1;
        a6 = 0xFFFF;
        goto LABEL_101;
      }
      v11 = 1;
      if ( (v8 & 0x80u) == 0 && a6 <= 0xFA0 )
      {
        v16 = (v8 >> 1) & 8 | 0xE7;
        v17 = 1;
        goto LABEL_90;
      }
      v16 = 99;
      goto LABEL_100;
    case 0xB:
      v16 = 104;
      goto LABEL_100;
    case 0xC:
      v16 = -25;
      v10 = 10;
      a6 = 8000;
      v17 = 1;
      v47 = 1;
      goto LABEL_101;
    case 0xE:
      v16 = 106;
      v48 = 1;
      v17 = 0;
      goto LABEL_91;
    case 0x10:
      v16 = 108;
      v10 = 1;
      v13 = 3;
      v53 = 0;
      v17 = 0;
      v12 = 1;
      v18 = &CTypeInfo::tiBit;
      goto LABEL_106;
    case 0x11:
      v16 = 48;
      goto LABEL_100;
    case 0x12:
      v16 = 108;
      v10 = 2;
      v13 = 5;
      v53 = 0;
      v17 = 0;
      v12 = 1;
      v18 = &CTypeInfo::tiBit;
      goto LABEL_106;
    case 0x13:
      v16 = 108;
      v10 = 3;
      v13 = 10;
      v53 = 0;
      v17 = 0;
      v12 = 1;
      v18 = &CTypeInfo::tiBit;
      goto LABEL_106;
    case 0x14:
      v16 = 127;
      goto LABEL_100;
    case 0x15:
      v16 = 108;
      v10 = 4;
      v13 = 20;
      v53 = 0;
      v17 = 0;
      v12 = 1;
      v18 = &CTypeInfo::tiBit;
      goto LABEL_106;
    case 0x40:
    case 0x87:
      v10 = 8;
      if ( (v8 & 0x40000000) != 0 )
      {
        v16 = 42;
        v14 = *(unsigned __int8 *)(a1 + 43);
        v17 = 0;
      }
      else if ( (a3 & 4) != 0 )
      {
        if ( *(_BYTE *)(a1 + 43) || (a3 & 8) == 0 )
        {
          v16 = 61;
          v17 = 0;
        }
        else
        {
          v16 = 58;
          v17 = 0;
        }
      }
      else
      {
        v16 = 42;
        v17 = 0;
      }
      goto LABEL_101;
    case 0x48:
      v16 = 36;
      goto LABEL_100;
    case 0x80:
      if ( (a3 & 1) != 0 )
      {
        if ( (v8 & 0x80u) != 0 )
        {
          if ( a6 == -1 )
          {
            v16 = -91;
            a6 = 0xFFFF;
            v17 = 1;
            goto LABEL_101;
          }
          goto LABEL_34;
        }
      }
      else if ( (v8 & 0x80u) != 0 )
      {
LABEL_34:
        v16 = 34;
        goto LABEL_100;
      }
      if ( a6 > 0x1F40 )
        goto LABEL_34;
      if ( (*(_DWORD *)(a1 + 24) & 0x210) == 0x210 && a6 == 8 )
      {
        v16 = -67;
        goto LABEL_100;
      }
      v16 = (v8 >> 1) & 8 | 0xA5;
      v17 = 1;
LABEL_90:
      if ( v12 )
      {
LABEL_91:
        v13 = *(_BYTE *)(a1 + 42);
        if ( !v13 )
          return 2;
        if ( v13 > 0x26u )
          return 4;
        v53 = *(_BYTE *)(a1 + 43);
        if ( v53 > v13 )
          return 3;
        v12 = v48;
        v18 = &CTypeInfo::tiBit;
      }
      else
      {
LABEL_20:
        if ( v16 == 108 )
        {
          v12 = 1;
          v18 = &CTypeInfo::tiBit;
        }
        else
        {
LABEL_101:
          v18 = &CTypeInfo::tiBit;
          if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsVarTime + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v16)) )
          {
            if ( v14 > 7 )
            {
              v25 = *(_WORD *)(a1 + 40) & 0xBFFF;
              if ( (unsigned __int16)(v25 - 145) <= 1u || (LOBYTE(v14) = 0, v25 == 135) )
                LOBYTE(v14) = 7;
            }
          }
        }
      }
LABEL_106:
      if ( (*(_BYTE *)(a1 + 24) & 1) != 0 )
      {
        v16 = -91;
        v17 = 1;
        v12 = 0;
LABEL_108:
        if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsVarTime + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v16)) )
        {
          CTypeInfo::Init((CTypeInfo *)&v51, v16);
          if ( !v47 )
            BYTE1(v51) |= 1u;
          switch ( (unsigned __int8)v51 )
          {
            case ')':
              v27 = 4LL * (unsigned __int8)v14 + 4604760;
              break;
            case '*':
              v27 = 4LL * (unsigned __int8)v14 + 4846464;
              break;
            case '+':
              v27 = 4LL * (unsigned __int8)v14 + 4610376;
              break;
            default:
LABEL_136:
              LOWORD(v52) = *(_WORD *)v9;
              BYTE2(v52) = v9[2];
              BYTE3(v52) = v14;
LABEL_148:
              v33 = a7;
              *(_OWORD *)a7 = v51;
              *((_OWORD *)v33 + 1) = v52;
LABEL_168:
              if ( v10 )
                *((_DWORD *)v33 + 1) = (unsigned __int8)v10;
              if ( *((_BYTE *)v26 + *((unsigned __int8 *)v26 + *v33 + 4566624) + 4570496) )
                v33[1] |= 2u;
              return 0;
          }
          v9 = (char *)v26 + v27;
          goto LABEL_136;
        }
        if ( v12 )
        {
          CTypeInfo::InitWithMaxLen((CTypeInfo *)&v51, v16, *((unsigned __int8 *)&qword_1008644E8[255] + v13 + 7));
          BYTE2(v52) = v13;
          BYTE3(v52) = v53;
          if ( !v47 )
            BYTE1(v51) |= 1u;
        }
        else
        {
          if ( !v17 )
          {
            CTypeInfo::Init((CTypeInfo *)&v51, v16);
            if ( !v47 )
              BYTE1(v51) |= 1u;
            if ( *((_BYTE *)v26 + *((unsigned __int8 *)v26 + (unsigned __int8)v51 + 4566624) + 4566976)
              || (((_BYTE)v51 - 35) & 0xBF) == 0 )
            {
              v38 = CTypeInfo::FCharacterOrEncryptedCharacter((CTypeInfo *)&v51);
              v39 = DWORD1(v52);
              if ( v38 )
                v39 = -1;
              DWORD1(v52) = v39;
            }
            goto LABEL_148;
          }
          CIDFromLCIDWithValidation = -1;
          if ( v11 )
          {
            if ( v54 )
            {
              v41 = v54[1];
              v42 = ((v41 & 1) << 12) | 0x2000;
              if ( (v41 & 2) == 0 )
                v42 = (v54[1] & 1) << 12;
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
              CIDFromLCIDWithValidation = MakeCIDFromLCIDWithValidation(*v54, v45);
            }
            v46 = 2 * a6;
          }
          else
          {
            v46 = a6;
          }
          LODWORD(v54) = CIDFromLCIDWithValidation;
          CTypeInfo::CTypeInfo((CTypeInfo *)&v51, v16, v47, v46, (const struct CDefaultCollation *)&v54);
          if ( v49 )
            BYTE1(v51) |= 0x20u;
        }
        v33 = a7;
        *(_OWORD *)a7 = v51;
        *((_OWORD *)v33 + 1) = v52;
LABEL_167:
        v26 = &CTypeInfo::tiBit;
        goto LABEL_168;
      }
      if ( v16 != 0xF0 )
        goto LABEL_108;
      v28 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v29 = *(_QWORD *)(v28 + 256);
      if ( !v29 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v29 = *(_QWORD *)(v28 + 256);
      }
      *((_QWORD *)&v51 + 1) = v29;
      v30 = *(_DWORD *)(v29 + 800);
      v31 = (v30 >> 11) & 1;
      DWORD1(v51) = v31;
      if ( (v30 & 4) != 0 && (v32 = *(_QWORD *)(v29 + 608)) != 0 )
      {
        LODWORD(v51) = 1;
        (*(void (__fastcall **)(__int64, __int64, __int64, __int16 *))(*(_QWORD *)v32 + 16LL))(v32, v29, 1, v18);
      }
      else
      {
        v15 = 0;
        LODWORD(v51) = 0;
      }
      if ( a5 )
      {
        v33 = a7;
        if ( (*(unsigned __int8 (__fastcall **)(struct ISqlTypeSystemExtender_IUdtProvider *, _QWORD, unsigned __int8 *))(*(_QWORD *)x_pIUdtProvider + 32LL))(
               x_pIUdtProvider,
               *a5,
               a7) )
        {
          if ( v15 )
          {
            v34 = *(__int64 **)(v29 + 608);
            v35 = *v34;
            if ( v31 == 1 )
              (*(void (__fastcall **)(__int64 *, __int64))(v35 + 24))(v34, v29);
            else
              (*(void (__fastcall **)(__int64 *, __int64))(v35 + 8))(v34, v29);
          }
          goto LABEL_167;
        }
      }
      if ( v15 )
      {
        v36 = *(__int64 **)(v29 + 608);
        v37 = *v36;
        if ( v31 == 1 )
        {
          (*(void (__fastcall **)(__int64 *, __int64))(v37 + 24))(v36, v29);
          return 5;
        }
        (*(void (__fastcall **)(__int64 *, __int64))(v37 + 8))(v36, v29);
      }
      return 5;
    case 0x81:
      if ( (a3 & 1) != 0 )
      {
        if ( (v8 & 0x80u) != 0 )
        {
          if ( a6 == -1 )
          {
            v16 = -89;
            v17 = 1;
            a6 = 0xFFFF;
            goto LABEL_101;
          }
          goto LABEL_42;
        }
      }
      else if ( (v8 & 0x80u) != 0 )
      {
        goto LABEL_42;
      }
      if ( a6 <= 0x1F40 )
      {
        v16 = (v8 >> 1) & 8 | 0xA7;
        v17 = 1;
        goto LABEL_90;
      }
LABEL_42:
      v16 = 35;
LABEL_100:
      v17 = 0;
      goto LABEL_101;
    case 0x83:
      v16 = 108;
      v48 = 1;
      v17 = 0;
      goto LABEL_91;
    case 0x84:
      v16 = -16;
      goto LABEL_100;
    case 0x85:
      v10 = 6;
      v16 = 40;
      if ( (a3 & 2) == 0 )
        v16 = 61;
      v17 = 0;
      goto LABEL_90;
    case 0x86:
      v10 = 7;
      v19 = a3 & 2;
      v16 = 41;
      if ( !v19 )
        v16 = 61;
      v14 = 0;
      if ( (v19 & 2) == 0 )
        v14 = 7;
      v17 = 0;
      goto LABEL_90;
    case 0x8B:
      if ( *(char *)(CGlobalTraceFlags::GetUlTraceFlags() + 913) < 0
        || (v20 = PSessTraceFlags()) != 0 && CSessionTraceFlags::CheckSessionTraceInternal(v20, 0x1C8Fu) )
      {
        v16 = -25;
        v22 = 1;
        v50 = 1;
        a6 = 384;
      }
      else
      {
        v16 = 108;
        v21 = *(_BYTE *)(a1 + 42);
        if ( (unsigned __int8)(v21 - 1) <= 0x25u && v21 >= *(_BYTE *)(a1 + 43) )
        {
          v12 = 1;
          v48 = 1;
          v22 = 0;
          goto LABEL_89;
        }
        if ( (*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 914) & 4) != 0
          || (v23 = PSessTraceFlags()) != 0 && CSessionTraceFlags::CheckSessionTraceInternal(v23, 0x1C92u) )
        {
          v13 = 38;
          v53 = 10;
          v22 = 0;
        }
        else
        {
          v16 = 62;
          v22 = 0;
        }
      }
      v12 = 0;
LABEL_89:
      v11 = v22;
      v17 = v50;
      goto LABEL_90;
    case 0x8D:
      v16 = -15;
      goto LABEL_100;
    case 0x90:
      v16 = 98;
      v10 = 11;
      v47 = 1;
      v17 = 0;
      goto LABEL_101;
    case 0x91:
      v10 = 12;
      v16 = 41;
      v14 = *(unsigned __int8 *)(a1 + 43);
      v17 = 0;
      goto LABEL_101;
    case 0x92:
      v10 = 13;
      v16 = 43;
      v14 = *(unsigned __int8 *)(a1 + 43);
      v17 = 0;
      goto LABEL_101;
    case 0xE8:
      v16 = 61;
      goto LABEL_18;
    case 0xE9:
      v16 = 58;
      goto LABEL_18;
    case 0xEA:
      v16 = 122;
      goto LABEL_18;
    case 0xEC:
      v16 = 98;
LABEL_18:
      if ( !a4 )
        return 1;
      v17 = 0;
      goto LABEL_20;
    default:
      return 1;
  }
}

```

## disassembly

```asm
0x100493540  mov     [rsp-38h+arg_8], rdx
0x100493545  push    rbp
0x100493546  push    rsi
0x100493547  push    rdi
0x100493548  push    r12
0x10049354a  push    r13
0x10049354c  push    r14
0x10049354e  push    r15
0x100493550  mov     rbp, rsp
0x100493553  sub     rsp, 60h
0x100493557  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x10049355f  mov     [rsp+60h+arg_10], rbx
0x100493567  mov     r15, rcx
0x10049356a  mov     ebx, [rcx+18h]
0x10049356d  test    bl, 60h
0x100493570  setnz   [rbp+var_30]
0x100493574  test    rdx, rdx
0x100493577  jz      short loc_100493583
0x100493579  test    byte ptr [rdx+20h], 1
0x10049357d  mov     [rbp+var_2E], 1
0x100493581  jnz     short loc_100493587
0x100493583  mov     [rbp+var_2E], 0
0x100493587  xor     r12d, r12d
0x10049358a  mov     esi, r12d
0x10049358d  mov     [rbp+var_2C], r12d
0x100493591  mov     r11d, r12d
0x100493594  xor     r10b, r10b
0x100493597  mov     [rbp+var_2F], r10b
0x10049359b  mov     [rbp+arg_0], sil
0x10049359f  xor     r13b, r13b
0x1004935a2  lea     edi, [r12+7]
0x1004935a7  movzx   eax, word ptr [rcx+28h]
0x1004935ab  btr     eax, 0Eh
0x1004935af  add     eax, 0FFFFFFFEh; switch 235 cases
0x1004935b2  cmp     eax, 0EAh
0x1004935b7  ja      def_1004935DD; jumptable 00000001004935DD default case, cases 9,10,13,15,22-63,65-71,73-127,136-138,140,142,143,147-231,235
0x1004935bd  cdqe
0x1004935bf  lea     rdx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x1004935c6  movzx   eax, ds:(byte_100493E10 - 100400000h)[rdx+rax]
0x1004935ce  mov     ecx, ds:(jpt_1004935DD - 100400000h)[rdx+rax*4]
0x1004935d5  add     rcx, rdx
0x1004935d8  lea     r14d, [r12+1]
0x1004935dd  jmp     rcx; switch jump
0x1004935df  mov     bl, 34h ; '4'; jumptable 00000001004935DD case 2
0x1004935e1  jmp     loc_1004939D0
0x1004935e6  mov     bl, 38h ; '8'; jumptable 00000001004935DD case 3
0x1004935e8  jmp     loc_1004939D0
0x1004935ed  mov     bl, 7Fh; jumptable 00000001004935DD case 20
0x1004935ef  jmp     loc_1004939D0
0x1004935f4  mov     bl, 3Bh ; ';'; jumptable 00000001004935DD case 4
0x1004935f6  jmp     loc_1004939D0
0x1004935fb  mov     bl, 3Eh ; '>'; jumptable 00000001004935DD case 5
0x1004935fd  jmp     loc_1004939D0
0x100493602  mov     bl, 3Ch ; '<'; jumptable 00000001004935DD case 6
0x100493604  jmp     loc_1004939D0
0x100493609  mov     bl, 68h ; 'h'; jumptable 00000001004935DD case 11
0x10049360b  jmp     loc_1004939D0
0x100493610  mov     bl, 30h ; '0'; jumptable 00000001004935DD case 17
0x100493612  jmp     loc_1004939D0
0x100493617  mov     bl, 24h ; '$'; jumptable 00000001004935DD case 72
0x100493619  jmp     loc_1004939D0
0x10049361e  mov     bl, 3Dh ; '='; jumptable 00000001004935DD case 232
0x100493620  jmp     short loc_10049362C
0x100493622  mov     bl, 3Ah ; ':'; jumptable 00000001004935DD case 233
0x100493624  jmp     short loc_10049362C
0x100493626  mov     bl, 7Ah ; 'z'; jumptable 00000001004935DD case 234
0x100493628  jmp     short loc_10049362C
0x10049362a  mov     bl, 62h ; 'b'; jumptable 00000001004935DD case 236
0x10049362c  test    r9b, r9b
0x10049362f  jz      def_1004935DD; jumptable 00000001004935DD default case, cases 9,10,13,15,22-63,65-71,73-127,136-138,140,142,143,147-231,235
0x100493635  mov     edx, esi
0x100493637  cmp     bl, 6Ch ; 'l'
0x10049363a  jnz     loc_1004939D2
0x100493640  movzx   r10d, r14b
0x100493644  lea     r9, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10049364b  jmp     loc_100493A26
0x100493650  mov     bl, 6Ch ; 'l'; jumptable 00000001004935DD case 131
0x100493652  mov     [rbp+var_2F], r14b
0x100493656  mov     edx, esi
0x100493658  jmp     loc_100493980
0x10049365d  mov     bl, 6Ah ; 'j'; jumptable 00000001004935DD case 14
0x10049365f  mov     [rbp+var_2F], r14b
0x100493663  mov     edx, esi
0x100493665  jmp     loc_100493980
0x10049366a  test    r14b, r8b; jumptable 00000001004935DD case 128
0x10049366d  jz      short loc_10049368C
0x10049366f  test    bl, bl
0x100493671  jns     short loc_100493690
0x100493673  cmp     [rbp+arg_28], 0FFFFFFFFFFFFFFFFh
0x100493678  jnz     short loc_1004936C8
0x10049367a  mov     bl, 0A5h
0x10049367c  mov     [rbp+arg_28], 0FFFFh
0x100493684  mov     edx, r14d
0x100493687  jmp     loc_1004939D2
0x10049368c  test    bl, bl
0x10049368e  js      short loc_1004936C8
0x100493690  mov     rcx, [rbp+arg_28]
0x100493694  cmp     rcx, 1F40h
0x10049369b  ja      short loc_1004936C8
0x10049369d  mov     eax, ebx
0x10049369f  and     eax, 210h
0x1004936a4  cmp     eax, 210h
0x1004936a9  jnz     short loc_1004936B8
0x1004936ab  cmp     rcx, 8
0x1004936af  jnz     short loc_1004936B8
0x1004936b1  mov     bl, 0BDh
0x1004936b3  jmp     loc_1004939D0
0x1004936b8  shr     ebx, 1
0x1004936ba  and     bl, 8
0x1004936bd  or      bl, 0A5h
0x1004936c0  mov     edx, r14d
0x1004936c3  jmp     loc_100493977
0x1004936c8  mov     bl, 22h ; '"'
0x1004936ca  jmp     loc_1004939D0
0x1004936cf  test    r14b, r8b; jumptable 00000001004935DD case 129
0x1004936d2  jz      short loc_1004936F1
0x1004936d4  test    bl, bl
0x1004936d6  jns     short loc_1004936F5
0x1004936d8  cmp     [rbp+arg_28], 0FFFFFFFFFFFFFFFFh
0x1004936dd  jnz     short loc_10049370F
0x1004936df  mov     bl, 0A7h
0x1004936e1  mov     edx, r14d
0x1004936e4  mov     [rbp+arg_28], 0FFFFh
0x1004936ec  jmp     loc_1004939D2
0x1004936f1  test    bl, bl
0x1004936f3  js      short loc_10049370F
0x1004936f5  cmp     [rbp+arg_28], 1F40h
0x1004936fd  ja      short loc_10049370F
0x1004936ff  shr     ebx, 1
0x100493701  and     bl, 8
0x100493704  or      bl, 0A7h
0x100493707  mov     edx, r14d
0x10049370a  jmp     loc_100493977
0x10049370f  mov     bl, 23h ; '#'
0x100493711  jmp     loc_1004939D0
0x100493716  test    r14b, r8b; jumptable 00000001004935DD cases 8,130
0x100493719  jz      short loc_100493738
0x10049371b  test    bl, bl
0x10049371d  jns     short loc_100493738
0x10049371f  cmp     [rbp+arg_28], 0FFFFFFFFFFFFFFFFh
0x100493724  jnz     short loc_100493738
0x100493726  mov     bl, 0E7h
0x100493728  mov     edx, r14d
0x10049372b  mov     [rbp+arg_28], 0FFFFh
0x100493733  jmp     loc_1004939D2
0x100493738  mov     r11d, r14d
0x10049373b  test    bl, bl
0x10049373d  js      short loc_100493759
0x10049373f  cmp     [rbp+arg_28], 0FA0h
0x100493747  ja      short loc_100493759
0x100493749  shr     ebx, 1
0x10049374b  and     bl, 8
0x10049374e  or      bl, 0E7h
0x100493751  mov     edx, r14d
0x100493754  jmp     loc_100493977
0x100493759  mov     bl, 63h ; 'c'
0x10049375b  jmp     loc_1004939D0
0x100493760  mov     bl, 6Ch ; 'l'; jumptable 00000001004935DD case 16
0x100493762  mov     esi, r14d
0x100493765  mov     r13b, 3
0x100493768  mov     [rbp+arg_0], r10b
0x10049376c  mov     edx, r12d
0x10049376f  movzx   r10d, r14b
0x100493773  lea     r9, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10049377a  jmp     loc_100493A26
0x10049377f  mov     bl, 6Ch ; 'l'; jumptable 00000001004935DD case 18
0x100493781  mov     esi, 2
0x100493786  mov     r13b, 5
0x100493789  mov     [rbp+arg_0], r10b
0x10049378d  mov     edx, r12d
0x100493790  movzx   r10d, r14b
0x100493794  lea     r9, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10049379b  jmp     loc_100493A26
0x1004937a0  mov     bl, 6Ch ; 'l'; jumptable 00000001004935DD case 19
0x1004937a2  mov     esi, 3
0x1004937a7  mov     r13b, 0Ah
0x1004937aa  mov     [rbp+arg_0], r10b
0x1004937ae  mov     edx, r12d
0x1004937b1  movzx   r10d, r14b
0x1004937b5  lea     r9, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x1004937bc  jmp     loc_100493A26
0x1004937c1  mov     bl, 6Ch ; 'l'; jumptable 00000001004935DD case 21
0x1004937c3  mov     esi, 4
0x1004937c8  mov     r13b, 14h
0x1004937cb  mov     [rbp+arg_0], r10b
0x1004937cf  mov     edx, r12d
0x1004937d2  movzx   r10d, r14b
0x1004937d6  lea     r9, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x1004937dd  jmp     loc_100493A26
0x1004937e2  mov     bl, 3Dh ; '='; jumptable 00000001004935DD case 7
0x1004937e4  mov     esi, 5
0x1004937e9  mov     edx, r12d
0x1004937ec  jmp     loc_1004939D2
0x1004937f1  mov     edx, edi; jumptable 00000001004935DD case 134
0x1004937f3  mov     esi, edi
0x1004937f5  and     r8d, 2
0x1004937f9  mov     ebx, 29h ; ')'
0x1004937fe  mov     ecx, 3Dh ; '='
0x100493803  cmovz   ebx, ecx
0x100493806  mov     edi, r12d
0x100493809  bt      r8d, 1
0x10049380e  cmovnb  edi, edx
0x100493811  mov     edx, r12d
0x100493814  jmp     loc_100493977
0x100493819  mov     esi, 6; jumptable 00000001004935DD case 133
0x10049381e  test    r8b, 2
0x100493822  mov     ebx, 28h ; '('
0x100493827  mov     ecx, 3Dh ; '='
0x10049382c  cmovz   ebx, ecx
0x10049382f  mov     edx, r12d
0x100493832  jmp     loc_100493977
0x100493837  mov     esi, 0Ch; jumptable 00000001004935DD case 145
0x10049383c  mov     bl, 29h ; ')'
0x10049383e  movzx   edi, byte ptr [r15+2Bh]
0x100493843  mov     edx, r12d
0x100493846  jmp     loc_1004939D2
0x10049384b  mov     esi, 0Dh; jumptable 00000001004935DD case 146
0x100493850  mov     bl, 2Bh ; '+'
0x100493852  movzx   edi, byte ptr [r15+2Bh]
0x100493857  mov     edx, r12d
0x10049385a  jmp     loc_1004939D2
0x10049385f  mov     esi, 8; jumptable 00000001004935DD cases 64,135
0x100493864  bt      ebx, 1Eh
0x100493868  jnb     short loc_100493879
0x10049386a  mov     bl, 2Ah ; '*'
0x10049386c  movzx   edi, byte ptr [r15+2Bh]
0x100493871  mov     edx, r12d
0x100493874  jmp     loc_1004939D2
0x100493879  test    r8b, 4
0x10049387d  jz      short loc_10049389E
0x10049387f  cmp     [r15+2Bh], r10b
0x100493883  jnz     short loc_100493894
0x100493885  test    sil, r8b
0x100493888  jz      short loc_100493894
0x10049388a  mov     bl, 3Ah ; ':'
0x10049388c  mov     edx, r12d
0x10049388f  jmp     loc_1004939D2
0x100493894  mov     bl, 3Dh ; '='
0x100493896  mov     edx, r12d
0x100493899  jmp     loc_1004939D2
0x10049389e  mov     bl, 2Ah ; '*'
0x1004938a0  mov     edx, r12d
0x1004938a3  jmp     loc_1004939D2
0x1004938a8  mov     bl, 62h ; 'b'; jumptable 00000001004935DD case 144
0x1004938aa  mov     esi, 0Bh
0x1004938af  mov     [rbp+var_30], r14b
0x1004938b3  mov     edx, r12d
0x1004938b6  jmp     loc_1004939D2
0x1004938bb  mov     bl, 0E7h; jumptable 00000001004935DD case 12
0x1004938bd  mov     esi, 0Ah
0x1004938c2  mov     [rbp+arg_28], 1F40h
0x1004938ca  mov     edx, r14d
0x1004938cd  mov     [rbp+var_30], dl
0x1004938d0  jmp     loc_1004939D2
0x1004938d5  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; jumptable 00000001004935DD case 139
0x1004938db  cmp     [rax+391h], sil
0x1004938e2  jl      short loc_10049395E
0x1004938e4  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x1004938ea  test    rax, rax
0x1004938ed  jz      short loc_100493901
0x1004938ef  mov     edx, 1C8Fh
0x1004938f4  mov     rcx, rax
0x1004938f7  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x1004938fd  test    eax, eax
0x1004938ff  jnz     short loc_10049395E
0x100493901  mov     bl, 6Ch ; 'l'
0x100493903  movzx   ecx, byte ptr [r15+2Ah]
0x100493908  lea     eax, [rcx-1]
0x10049390b  cmp     al, 25h ; '%'
0x10049390d  ja      short loc_100493921
0x10049390f  cmp     cl, [r15+2Bh]
0x100493913  jb      short loc_100493921
0x100493915  movzx   r10d, r14b
0x100493919  mov     [rbp+var_2F], r14b
0x10049391d  mov     edx, esi
0x10049391f  jmp     short loc_100493971
0x100493921  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x100493927  test    byte ptr [rax+392h], 4
0x10049392e  jnz     short loc_100493953
0x100493930  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x100493936  test    rax, rax
0x100493939  jz      short loc_10049394D
0x10049393b  mov     edx, 1C92h
0x100493940  mov     rcx, rax
0x100493943  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100493949  test    eax, eax
0x10049394b  jnz     short loc_100493953
0x10049394d  mov     bl, 3Eh ; '>'
0x10049394f  mov     edx, esi
0x100493951  jmp     short loc_10049396E
0x100493953  mov     r13b, 26h ; '&'
0x100493956  mov     [rbp+arg_0], 0Ah
0x10049395a  mov     edx, esi
0x10049395c  jmp     short loc_10049396E
0x10049395e  mov     bl, 0E7h
0x100493960  mov     edx, r14d
0x100493963  mov     [rbp+var_2C], edx
0x100493966  mov     [rbp+arg_28], 180h
0x10049396e  xor     r10b, r10b
0x100493971  mov     r11d, edx
  ... truncated ...
```
