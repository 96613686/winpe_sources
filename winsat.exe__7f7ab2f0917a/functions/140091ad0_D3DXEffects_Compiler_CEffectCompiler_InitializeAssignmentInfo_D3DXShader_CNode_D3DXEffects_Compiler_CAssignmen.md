# D3DXEffects::Compiler::CEffectCompiler::InitializeAssignmentInfo(D3DXShader::CNode *,D3DXEffects::Compiler::CAssignmentInfo * *,ulong)

- ea: `0x140091ad0`
- end: `0x140091ecc`
- name: `?InitializeAssignmentInfo@CEffectCompiler@Compiler@D3DXEffects@@AEAAJPEAVCNode@D3DXShader@@PEAPEAVCAssignmentInfo@23@K@Z`
- size: `1020`
- prototype: `__int64 __fastcall(D3DXEffects::Compiler::CEffectCompiler *__hidden this, struct D3DXShader::CNode *, struct D3DXEffects::Compiler::CAssignmentInfo **, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140091ad0`
- `0x1400924ac`
- `0x140092d9c`

## callees

- `0x14008c0e0`
- `0x14008f8dc`
- `0x140091ad0`
- `0x14009516c`
- `0x1400a96b4`

## import_xrefs

- `msvcrt!_stricmp` at `0x140091b4b`
- `msvcrt!_stricmp` at `0x140091c35`
- `msvcrt!_stricmp` at `0x140091b4b`
- `msvcrt!_stricmp` at `0x140091c35`

## string_xrefs

- `0x140091b80`: `ID3DXEffectCompiler: Unrecognized state '%s'`
- `0x140091be7`: `ID3DXEffectCompiler: Max index for effect state '%s' is %d`
- `0x140091bbe`: `ID3DXEffectCompiler: State '%s' is not indexed`
- `0x140091c85`: `ID3DXEffectCompiler: DMAPOFFSET sampler state can only be used with D3DDMAPSAMPLER (i.e. sampler index 256)`
- `0x140091c09`: `ID3DXEffectCompiler: Index is required for state '%s'`
- `0x140091df7`: `ID3DXEffectCompiler: Unsupported sampler or stateblock expression (static usage not supported).`
- `0x140091caf`: `ID3DXEffectCompiler: Invalid sampler index %d`

## pseudocode

```c
__int64 __fastcall D3DXEffects::Compiler::CEffectCompiler::InitializeAssignmentInfo(
        D3DXEffects::Compiler::CEffectCompiler *this,
        struct D3DXShader::CNode *a2,
        struct D3DXEffects::Compiler::CAssignmentInfo **a3,
        unsigned int a4)
{
  __int64 v4; // rdx
  __int64 v6; // rbx
  const struct LValue near *const *v7; // r14
  __int64 v9; // rsi
  const char *v10; // r8
  int RType; // ebx
  __int64 v12; // rcx
  unsigned int v13; // eax
  unsigned int v14; // r14d
  struct D3DXShader::D3DXTOKEN *v15; // r12
  int v16; // r15d
  const struct D3DX9MEMORY::CD3DXNEW *v17; // rdx
  __int64 v18; // r13
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  _QWORD *v22; // rsi
  unsigned __int8 *v23; // r9
  unsigned __int8 *v24; // rax
  int v25; // ecx
  int v26; // edx
  struct D3DXShader::CNode *v27; // rsi
  struct D3DXEffects::Compiler::CAssignmentInfo **v28; // r12
  unsigned int v29; // r9d
  _QWORD *v30; // rax
  _QWORD *v31; // rdx
  unsigned int v32; // ecx
  unsigned int v33; // eax
  struct D3DXEffects::Compiler::CAssignmentInfo **v34; // r12
  struct D3DXEffects::Compiler::CAssignmentInfo *v35; // rax
  unsigned int v37; // [rsp+50h] [rbp-20h] BYREF
  unsigned int v38; // [rsp+54h] [rbp-1Ch] BYREF
  int v39; // [rsp+58h] [rbp-18h] BYREF
  unsigned int v40; // [rsp+5Ch] [rbp-14h] BYREF
  __int64 v41; // [rsp+60h] [rbp-10h]
  unsigned int v42; // [rsp+B8h] [rbp+48h] BYREF
  struct D3DXEffects::Compiler::CAssignmentInfo **v43; // [rsp+C0h] [rbp+50h]
  unsigned int v44; // [rsp+C8h] [rbp+58h] BYREF

  v43 = a3;
  v4 = *((_QWORD *)a2 + 2);
  v41 = v4;
  v39 = 0;
  v44 = 0;
  v6 = *(_QWORD *)(v4 + 32);
  v42 = 0;
  v7 = (const struct LValue near *const *)&g_lvGeneral;
  v37 = 0;
  if ( a4 != -1 )
    v7 = &g_lvSampler;
  v38 = 0;
  v40 = 0;
  LODWORD(v9) = 0;
  if ( *v7 )
  {
    do
    {
      if ( !_stricmp((const char *)v7[5 * (unsigned int)v9], *(const char **)(v6 + 40)) )
        break;
      v9 = (unsigned int)(v9 + 1);
    }
    while ( v7[5 * v9] );
    v4 = v41;
  }
  v10 = (const char *)v7[5 * (unsigned int)v9];
  if ( !v10 )
  {
    D3DXShader::CTErrors::Error(
      (D3DXEffects::Compiler::CEffectCompiler *)((char *)this + 56),
      (struct D3DXShader::D3DXTOKEN *)(v6 + 32),
      0,
      "ID3DXEffectCompiler: Unrecognized state '%s'",
      *(_QWORD *)(v6 + 40));
    return (unsigned int)-2147467259;
  }
  v12 = *(_QWORD *)(v4 + 40);
  v13 = (unsigned int)v7[5 * (unsigned int)v9 + 3];
  if ( v12 )
  {
    if ( v13 == 1 )
    {
      D3DXShader::CTErrors::Error(
        (D3DXEffects::Compiler::CEffectCompiler *)((char *)this + 56),
        (struct D3DXShader::D3DXTOKEN *)(v6 + 32),
        0,
        "ID3DXEffectCompiler: State '%s' is not indexed",
        v7[5 * (unsigned int)v9]);
      return (unsigned int)-2147467259;
    }
    v14 = *(_DWORD *)(v12 + 40);
    if ( v13 && v13 <= v14 )
    {
      D3DXShader::CTErrors::Error(
        (D3DXEffects::Compiler::CEffectCompiler *)((char *)this + 56),
        (struct D3DXShader::D3DXTOKEN *)(v6 + 32),
        0,
        "ID3DXEffectCompiler: Max index for effect state '%s' is %d",
        v10,
        v13 - 1);
      return (unsigned int)-2147467259;
    }
  }
  else
  {
    v14 = 0;
    if ( v13 != 1 )
    {
      D3DXShader::CTErrors::Error(
        (D3DXEffects::Compiler::CEffectCompiler *)((char *)this + 56),
        (struct D3DXShader::D3DXTOKEN *)(v6 + 32),
        0,
        "ID3DXEffectCompiler: Index is required for state '%s'",
        v10);
      return (unsigned int)-2147467259;
    }
  }
  if ( a4 != -1 )
  {
    LODWORD(v9) = 0;
    if ( g_lvGeneral )
    {
      do
      {
        if ( !_stricmp(*((const char **)&g_lvGeneral + 5 * (unsigned int)v9), *(const char **)(v6 + 40)) )
          break;
        v9 = (unsigned int)(v9 + 1);
      }
      while ( *((_QWORD *)&g_lvGeneral + 5 * v9) );
      v4 = v41;
    }
    v14 = a4;
  }
  if ( *((_DWORD *)&g_lvGeneral + 10 * (unsigned int)v9 + 6) == 261 )
  {
    if ( v14 - 16 <= 0xF0 || v14 >= 0x105 )
    {
      if ( v14 != 256 )
      {
        D3DXShader::CTErrors::Error(
          (D3DXEffects::Compiler::CEffectCompiler *)((char *)this + 56),
          (struct D3DXShader::D3DXTOKEN *)(v6 + 32),
          0,
          "ID3DXEffectCompiler: Invalid sampler index %d",
          v14);
        return (unsigned int)-2147467259;
      }
    }
    else if ( *((_DWORD *)&g_lvGeneral + 10 * (unsigned int)v9 + 7) == 50331661 )
    {
      D3DXShader::CTErrors::Error(
        (D3DXEffects::Compiler::CEffectCompiler *)((char *)this + 56),
        (struct D3DXShader::D3DXTOKEN *)(v6 + 32),
        0,
        "ID3DXEffectCompiler: DMAPOFFSET sampler state can only be used with D3DDMAPSAMPLER (i.e. sampler index 256)");
      return (unsigned int)-2147467259;
    }
  }
  v15 = (struct D3DXShader::D3DXTOKEN *)(v6 + 32);
  RType = D3DXEffects::Compiler::CEffectCompiler::GetRType(
            this,
            *(struct D3DXShader::CNode **)(v4 + 48),
            (const struct LValue *)((char *)&g_lvGeneral + 40 * (unsigned int)v9),
            (enum _D3DXPARAMETER_TYPE *)&v39,
            &v44,
            &v42,
            &v37,
            &v38,
            &v40,
            (struct D3DXShader::D3DXTOKEN *)(v6 + 32));
  if ( RType >= 0 )
  {
    v16 = v39;
    RType = D3DXEffects::Compiler::CEffectCompiler::TypeCheck(
              (__int64)this,
              (_QWORD *)&g_lvGeneral + 5 * (unsigned int)v9,
              v39,
              v44,
              v42,
              v37,
              v38,
              v15);
    if ( RType >= 0 )
    {
      if ( v16 == 10 || v16 == 11 || v16 == 12 || v16 == 13 || v16 == 14 || v16 == 15925248 )
      {
        v18 = v41;
        v19 = *(_QWORD *)(v41 + 48);
        if ( *(_DWORD *)(v19 + 8) == 13 )
        {
          if ( *(_DWORD *)(v19 + 48) )
            goto LABEL_55;
          v20 = *(_QWORD *)(v19 + 56);
          if ( !v20 )
            goto LABEL_55;
          if ( *(_DWORD *)(v20 + 8) != 1 )
            goto LABEL_55;
          v21 = *(_QWORD *)(v20 + 16);
          if ( !v21 || *(_DWORD *)(v21 + 8) != 14 )
            goto LABEL_55;
          if ( *(_DWORD *)(v21 + 32) != 6 )
          {
            v27 = *(struct D3DXShader::CNode **)(v21 + 40);
LABEL_58:
            v28 = v43;
            while ( v27 )
            {
              v29 = v14;
              if ( v16 == 15925248 )
                v29 = -1;
              RType = D3DXEffects::Compiler::CEffectCompiler::InitializeAssignmentInfo(this, v27, v28, v29);
              if ( RType < 0 )
                break;
              v27 = (struct D3DXShader::CNode *)*((_QWORD *)v27 + 3);
            }
            return (unsigned int)RType;
          }
          if ( v16 == 15925248 )
          {
            v22 = (_QWORD *)*((_QWORD *)this + 193);
            if ( v22 )
            {
              v23 = *(unsigned __int8 **)(v21 + 64);
              while ( 1 )
              {
                v24 = v23;
                do
                {
                  v25 = v24[*v22 - (_QWORD)v23];
                  v26 = *v24 - v25;
                  if ( v26 )
                    break;
                  ++v24;
                }
                while ( v25 );
                if ( !v26 )
                  break;
                v22 = (_QWORD *)v22[2];
                if ( !v22 )
                  goto LABEL_55;
              }
              v27 = (struct D3DXShader::CNode *)v22[1];
              goto LABEL_58;
            }
LABEL_55:
            D3DXShader::CTErrors::Error(
              (D3DXEffects::Compiler::CEffectCompiler *)((char *)this + 56),
              v15,
              0,
              "ID3DXEffectCompiler: Unsupported sampler or stateblock expression (static usage not supported).");
            return (unsigned int)-2147467259;
          }
        }
      }
      else
      {
        v18 = v41;
      }
      v30 = operator new(0x38u, v17);
      v31 = v30;
      if ( v30 )
      {
        v30[1] = *(_QWORD *)(v18 + 48);
        v32 = v40;
        *(_DWORD *)v30 = v9;
        *((_DWORD *)v30 + 1) = v14;
        *((_DWORD *)v30 + 4) = v16;
        *((_DWORD *)v30 + 5) = v44;
        *((_DWORD *)v30 + 6) = v42;
        *((_DWORD *)v30 + 7) = v37;
        v33 = v38;
        v31[5] = v15;
        v34 = v43;
        *((_DWORD *)v31 + 8) = v33;
        *((_DWORD *)v31 + 9) = v32;
        v31[6] = 0;
        v35 = *v34;
        *v34 = (struct D3DXEffects::Compiler::CAssignmentInfo *)v31;
        *((_QWORD *)v35 + 6) = v31;
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  return (unsigned int)RType;
}

```

## disassembly

```asm
0x140091ad0  mov     [rsp-38h+arg_0], rbx
0x140091ad5  mov     [rsp-38h+arg_10], r8
0x140091ada  push    rbp
0x140091adb  push    rsi
0x140091adc  push    rdi
0x140091add  push    r12
0x140091adf  push    r13
0x140091ae1  push    r14
0x140091ae3  push    r15
0x140091ae5  mov     rbp, rsp
0x140091ae8  sub     rsp, 70h
0x140091aec  mov     rdx, [rdx+10h]
0x140091af0  lea     r13, ?g_lvGeneral@@3QBULValue@@B; LValue const near * const g_lvGeneral
0x140091af7  xor     r12d, r12d
0x140091afa  mov     [rbp+var_10], rdx
0x140091afe  mov     r15d, r9d
0x140091b01  mov     [rbp+var_18], r12d
0x140091b05  or      r9d, 0FFFFFFFFh
0x140091b09  mov     [rbp+arg_18], r12d
0x140091b0d  mov     rbx, [rdx+20h]
0x140091b11  lea     rax, ?g_lvSampler@@3QBULValue@@B; LValue const near * const g_lvSampler
0x140091b18  cmp     r15d, r9d
0x140091b1b  mov     [rbp+arg_8], r12d
0x140091b1f  mov     r14, r13
0x140091b22  mov     [rbp+var_20], r12d
0x140091b26  cmovnz  r14, rax
0x140091b2a  mov     [rbp+var_1C], r12d
0x140091b2e  mov     rdi, rcx
0x140091b31  mov     [rbp+var_14], r12d
0x140091b35  mov     esi, r12d
0x140091b38  cmp     [r14], r12
0x140091b3b  jz      short loc_140091B69
0x140091b3d  mov     rdx, [rbx+28h]; String2
0x140091b41  mov     eax, esi
0x140091b43  lea     rcx, [rax+rax*4]
0x140091b47  mov     rcx, [r14+rcx*8]; String1
0x140091b4b  call    cs:__imp__stricmp
0x140091b51  test    eax, eax
0x140091b53  jz      short loc_140091B61
0x140091b55  inc     esi
0x140091b57  lea     rcx, [rsi+rsi*4]
0x140091b5b  cmp     [r14+rcx*8], r12
0x140091b5f  jnz     short loc_140091B3D
0x140091b61  mov     rdx, [rbp+var_10]
0x140091b65  or      r9d, 0FFFFFFFFh
0x140091b69  mov     eax, esi
0x140091b6b  lea     rax, [rax+rax*4]
0x140091b6f  mov     r8, [r14+rax*8]
0x140091b73  test    r8, r8
0x140091b76  jnz     short loc_140091BA2
0x140091b78  lea     rdx, [rbx+20h]; struct D3DXShader::D3DXTOKEN *
0x140091b7c  mov     rax, [rdx+8]
0x140091b80  lea     r9, aId3dxeffectcom_46; "ID3DXEffectCompiler: Unrecognized state"...
0x140091b87  mov     [rsp+70h+var_50], rax
0x140091b8c  lea     rcx, [rdi+38h]; this
0x140091b90  xor     r8d, r8d; unsigned int
0x140091b93  call    ?Error@CTErrors@D3DXShader@@QEAAJPEAUD3DXTOKEN@2@IPEBDZZ; D3DXShader::CTErrors::Error(D3DXShader::D3DXTOKEN *,uint,char const *,...)
0x140091b98  mov     ebx, 80004005h
0x140091b9d  jmp     loc_140091EB2
0x140091ba2  mov     rcx, [rdx+28h]
0x140091ba6  mov     eax, [r14+rax*8+18h]
0x140091bab  test    rcx, rcx
0x140091bae  jz      short loc_140091BF8
0x140091bb0  cmp     eax, 1
0x140091bb3  jnz     short loc_140091BC7
0x140091bb5  lea     rdx, [rbx+20h]
0x140091bb9  mov     [rsp+70h+var_50], r8
0x140091bbe  lea     r9, aId3dxeffectcom_54; "ID3DXEffectCompiler: State '%s' is not "...
0x140091bc5  jmp     short loc_140091B8C
0x140091bc7  mov     r14d, [rcx+28h]
0x140091bcb  test    eax, eax
0x140091bcd  jz      short loc_140091C15
0x140091bcf  cmp     eax, r14d
0x140091bd2  ja      short loc_140091C15
0x140091bd4  dec     eax
0x140091bd6  lea     rdx, [rbx+20h]; struct D3DXShader::D3DXTOKEN *
0x140091bda  mov     dword ptr [rsp+70h+var_48], eax
0x140091bde  lea     rcx, [rdi+38h]; this
0x140091be2  mov     [rsp+70h+var_50], r8
0x140091be7  lea     r9, aId3dxeffectcom_40; "ID3DXEffectCompiler: Max index for effe"...
0x140091bee  xor     r8d, r8d; unsigned int
0x140091bf1  call    ?Error@CTErrors@D3DXShader@@QEAAJPEAUD3DXTOKEN@2@IPEBDZZ; D3DXShader::CTErrors::Error(D3DXShader::D3DXTOKEN *,uint,char const *,...)
0x140091bf6  jmp     short loc_140091B98
0x140091bf8  mov     r14d, r12d
0x140091bfb  cmp     eax, 1
0x140091bfe  jz      short loc_140091C15
0x140091c00  lea     rdx, [rbx+20h]
0x140091c04  mov     [rsp+70h+var_50], r8
0x140091c09  lea     r9, aId3dxeffectcom_17; "ID3DXEffectCompiler: Index is required "...
0x140091c10  jmp     loc_140091B8C
0x140091c15  cmp     r15d, r9d
0x140091c18  jz      short loc_140091C53
0x140091c1a  cmp     cs:?g_lvGeneral@@3QBULValue@@B, r12; LValue const near * const g_lvGeneral
0x140091c21  mov     esi, r12d
0x140091c24  jz      short loc_140091C50
0x140091c26  mov     rdx, [rbx+28h]; String2
0x140091c2a  mov     eax, esi
0x140091c2c  lea     rcx, [rax+rax*4]
0x140091c30  mov     rcx, [r13+rcx*8+0]; String1
0x140091c35  call    cs:__imp__stricmp
0x140091c3b  test    eax, eax
0x140091c3d  jz      short loc_140091C4C
0x140091c3f  inc     esi
0x140091c41  lea     rcx, [rsi+rsi*4]
0x140091c45  cmp     [r13+rcx*8+0], r12
0x140091c4a  jnz     short loc_140091C26
0x140091c4c  mov     rdx, [rbp+var_10]
0x140091c50  mov     r14d, r15d
0x140091c53  mov     eax, esi
0x140091c55  mov     r8d, 105h
0x140091c5b  lea     rcx, [rax+rax*4]
0x140091c5f  cmp     [r13+rcx*8+18h], r8d
0x140091c64  jnz     short loc_140091CBB
0x140091c66  lea     eax, [r14-10h]
0x140091c6a  cmp     eax, 0F0h
0x140091c6f  jbe     short loc_140091C9D
0x140091c71  cmp     r14d, r8d
0x140091c74  jnb     short loc_140091C9D
0x140091c76  cmp     dword ptr [r13+rcx*8+1Ch], 300000Dh
0x140091c7f  jnz     short loc_140091CBB
0x140091c81  lea     rdx, [rbx+20h]; struct D3DXShader::D3DXTOKEN *
0x140091c85  lea     r9, aId3dxeffectcom_12; "ID3DXEffectCompiler: DMAPOFFSET sampler"...
0x140091c8c  xor     r8d, r8d; unsigned int
0x140091c8f  lea     rcx, [rdi+38h]; this
0x140091c93  call    ?Error@CTErrors@D3DXShader@@QEAAJPEAUD3DXTOKEN@2@IPEBDZZ; D3DXShader::CTErrors::Error(D3DXShader::D3DXTOKEN *,uint,char const *,...)
0x140091c98  jmp     loc_140091B98
0x140091c9d  cmp     r14d, 100h
0x140091ca4  jz      short loc_140091CBB
0x140091ca6  lea     rdx, [rbx+20h]
0x140091caa  mov     dword ptr [rsp+70h+var_50], r14d
0x140091caf  lea     r9, aId3dxeffectcom_10; "ID3DXEffectCompiler: Invalid sampler in"...
0x140091cb6  jmp     loc_140091B8C
0x140091cbb  mov     rdx, [rdx+30h]; struct D3DXShader::CNode *
0x140091cbf  lea     r13, [r13+rcx*8+0]
0x140091cc4  lea     rax, [rbp+var_14]
0x140091cc8  mov     r8, r13; struct LValue *
0x140091ccb  lea     r12, [rbx+20h]
0x140091ccf  mov     rcx, rdi; this
0x140091cd2  mov     [rsp+70h+var_28], r12; struct D3DXShader::D3DXTOKEN *
0x140091cd7  lea     r9, [rbp+var_18]; enum _D3DXPARAMETER_TYPE *
0x140091cdb  mov     [rsp+70h+var_30], rax; unsigned int *
0x140091ce0  lea     rax, [rbp+var_1C]
0x140091ce4  mov     [rsp+70h+var_38], rax; unsigned int *
0x140091ce9  lea     rax, [rbp+var_20]
0x140091ced  mov     [rsp+70h+var_40], rax; unsigned int *
0x140091cf2  lea     rax, [rbp+arg_8]
0x140091cf6  mov     [rsp+70h+var_48], rax; unsigned int *
0x140091cfb  lea     rax, [rbp+arg_18]
0x140091cff  mov     [rsp+70h+var_50], rax; unsigned int *
0x140091d04  call    ?GetRType@CEffectCompiler@Compiler@D3DXEffects@@AEAAJPEAVCNode@D3DXShader@@PEBULValue@@PEAW4_D3DXPARAMETER_TYPE@@PEAI3333PEAUD3DXTOKEN@5@@Z; D3DXEffects::Compiler::CEffectCompiler::GetRType(D3DXShader::CNode *,LValue const *,_D3DXPARAMETER_TYPE *,uint *,uint *,uint *,uint *,uint *,D3DXShader::D3DXTOKEN *)
0x140091d09  mov     ebx, eax
0x140091d0b  test    eax, eax
0x140091d0d  js      loc_140091EB2
0x140091d13  mov     eax, [rbp+var_1C]
0x140091d16  mov     rdx, r13
0x140091d19  mov     r15d, [rbp+var_18]
0x140091d1d  mov     rcx, rdi
0x140091d20  mov     r9d, [rbp+arg_18]
0x140091d24  mov     r8d, r15d
0x140091d27  mov     [rsp+70h+var_38], r12
0x140091d2c  mov     dword ptr [rsp+70h+var_40], eax
0x140091d30  mov     eax, [rbp+var_20]
0x140091d33  mov     dword ptr [rsp+70h+var_48], eax
0x140091d37  mov     eax, [rbp+arg_8]
0x140091d3a  mov     dword ptr [rsp+70h+var_50], eax
0x140091d3e  call    ?TypeCheck@CEffectCompiler@Compiler@D3DXEffects@@AEAAJPEBULValue@@W4_D3DXPARAMETER_TYPE@@IIIIPEAUD3DXTOKEN@D3DXShader@@@Z; D3DXEffects::Compiler::CEffectCompiler::TypeCheck(LValue const *,_D3DXPARAMETER_TYPE,uint,uint,uint,uint,D3DXShader::D3DXTOKEN *)
0x140091d43  mov     ebx, eax
0x140091d45  test    eax, eax
0x140091d47  js      loc_140091EB2
0x140091d4d  mov     ecx, r15d
0x140091d50  sub     ecx, 0Ah
0x140091d53  jz      short loc_140091D75
0x140091d55  sub     ecx, 1
0x140091d58  jz      short loc_140091D75
0x140091d5a  sub     ecx, 1
0x140091d5d  jz      short loc_140091D75
0x140091d5f  sub     ecx, 1
0x140091d62  jz      short loc_140091D75
0x140091d64  sub     ecx, 1
0x140091d67  jz      short loc_140091D75
0x140091d69  cmp     ecx, 0F2FFF2h
0x140091d6f  jnz     loc_140091E49
0x140091d75  mov     r13, [rbp+var_10]
0x140091d79  mov     rax, [r13+30h]
0x140091d7d  cmp     dword ptr [rax+8], 0Dh
0x140091d81  jnz     loc_140091E4D
0x140091d87  cmp     dword ptr [rax+30h], 0
0x140091d8b  jnz     short loc_140091DF7
0x140091d8d  mov     rax, [rax+38h]
0x140091d91  test    rax, rax
0x140091d94  jz      short loc_140091DF7
0x140091d96  cmp     dword ptr [rax+8], 1
0x140091d9a  jnz     short loc_140091DF7
0x140091d9c  mov     rax, [rax+10h]
0x140091da0  test    rax, rax
0x140091da3  jz      short loc_140091DF7
0x140091da5  cmp     dword ptr [rax+8], 0Eh
0x140091da9  jnz     short loc_140091DF7
0x140091dab  cmp     dword ptr [rax+20h], 6
0x140091daf  jnz     short loc_140091E0C
0x140091db1  cmp     r15d, 0F30000h
0x140091db8  jnz     loc_140091E4D
0x140091dbe  mov     rsi, [rdi+608h]
0x140091dc5  test    rsi, rsi
0x140091dc8  jz      short loc_140091DF7
0x140091dca  mov     r9, [rax+40h]
0x140091dce  mov     r8, [rsi]
0x140091dd1  mov     rax, r9
0x140091dd4  sub     r8, r9
0x140091dd7  movzx   edx, byte ptr [rax]
0x140091dda  movzx   ecx, byte ptr [rax+r8]
0x140091ddf  sub     edx, ecx
0x140091de1  jnz     short loc_140091DEA
0x140091de3  inc     rax
0x140091de6  test    ecx, ecx
0x140091de8  jnz     short loc_140091DD7
0x140091dea  test    edx, edx
0x140091dec  jz      short loc_140091E06
0x140091dee  mov     rsi, [rsi+10h]
0x140091df2  test    rsi, rsi
0x140091df5  jnz     short loc_140091DCE
0x140091df7  lea     r9, aId3dxeffectcom_8; "ID3DXEffectCompiler: Unsupported sample"...
0x140091dfe  mov     rdx, r12
0x140091e01  jmp     loc_140091C8C
0x140091e06  mov     rsi, [rsi+8]
0x140091e0a  jmp     short loc_140091E10
0x140091e0c  mov     rsi, [rax+28h]
0x140091e10  mov     r12, [rbp+arg_10]
0x140091e14  or      r13d, 0FFFFFFFFh
0x140091e18  test    rsi, rsi
0x140091e1b  jz      loc_140091EB2
0x140091e21  mov     r9d, r14d
0x140091e24  cmp     r15d, 0F30000h
0x140091e2b  mov     r8, r12; struct D3DXEffects::Compiler::CAssignmentInfo **
0x140091e2e  mov     rdx, rsi; struct D3DXShader::CNode *
0x140091e31  cmovz   r9d, r13d; unsigned int
0x140091e35  mov     rcx, rdi; this
0x140091e38  call    ?InitializeAssignmentInfo@CEffectCompiler@Compiler@D3DXEffects@@AEAAJPEAVCNode@D3DXShader@@PEAPEAVCAssignmentInfo@23@K@Z; D3DXEffects::Compiler::CEffectCompiler::InitializeAssignmentInfo(D3DXShader::CNode *,D3DXEffects::Compiler::CAssignmentInfo * *,ulong)
0x140091e3d  mov     ebx, eax
0x140091e3f  test    eax, eax
0x140091e41  js      short loc_140091EB2
0x140091e43  mov     rsi, [rsi+18h]
0x140091e47  jmp     short loc_140091E18
0x140091e49  mov     r13, [rbp+var_10]
0x140091e4d  mov     ecx, 38h ; '8'; unsigned __int64
0x140091e52  call    ??2@YAPEAX_KAEBVCD3DXNEW@D3DX9MEMORY@@@Z; operator new(unsigned __int64,D3DX9MEMORY::CD3DXNEW const &)
0x140091e57  mov     rdx, rax
0x140091e5a  test    rax, rax
0x140091e5d  jz      short loc_140091EAD
0x140091e5f  mov     rcx, [r13+30h]
0x140091e63  mov     [rax+8], rcx
0x140091e67  mov     ecx, [rbp+var_14]
0x140091e6a  mov     [rax], esi
0x140091e6c  mov     [rax+4], r14d
0x140091e70  mov     [rax+10h], r15d
0x140091e74  mov     eax, [rbp+arg_18]
0x140091e77  mov     [rdx+14h], eax
0x140091e7a  mov     eax, [rbp+arg_8]
0x140091e7d  mov     [rdx+18h], eax
0x140091e80  mov     eax, [rbp+var_20]
0x140091e83  mov     [rdx+1Ch], eax
0x140091e86  mov     eax, [rbp+var_1C]
0x140091e89  mov     [rdx+28h], r12
0x140091e8d  mov     r12, [rbp+arg_10]
0x140091e91  mov     [rdx+20h], eax
0x140091e94  mov     [rdx+24h], ecx
0x140091e97  mov     qword ptr [rdx+30h], 0
0x140091e9f  mov     rax, [r12]
0x140091ea3  mov     [r12], rdx
0x140091ea7  mov     [rax+30h], rdx
0x140091eab  jmp     short loc_140091EB2
0x140091ead  mov     ebx, 8007000Eh
0x140091eb2  mov     eax, ebx
0x140091eb4  mov     rbx, [rsp+70h+arg_0]
0x140091ebc  add     rsp, 70h
0x140091ec0  pop     r15
0x140091ec2  pop     r14
0x140091ec4  pop     r13
0x140091ec6  pop     r12
0x140091ec8  pop     rdi
0x140091ec9  pop     rsi
0x140091eca  pop     rbp
0x140091ecb  retn
```
