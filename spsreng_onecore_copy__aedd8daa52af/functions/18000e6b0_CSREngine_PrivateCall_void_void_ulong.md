# CSREngine::PrivateCall(void *,void *,ulong)

- ea: `0x18000e6b0`
- end: `0x18000ed0f`
- name: `?PrivateCall@CSREngine@@UEAAJPEAX0K@Z`
- size: `1631`
- prototype: `__int64 __fastcall(CSREngine *__hidden this, void *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180002e00`
- `0x180004810`
- `0x180004b08`
- `0x1800055f8`
- `0x180005fb8`
- `0x1800061d0`
- `0x1800062a0`
- `0x180006c7c`
- `0x18000aadc`
- `0x18000ba90`
- `0x18000e6b0`
- `0x1800115f4`
- `0x180011e44`
- `0x180011f8c`
- `0x180013ba0`
- `0x1800141c0`
- `0x180021188`
- `0x180078a7c`
- `0x18009c86c`
- `0x1800aa4c8`
- `0x1800b15b4`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e932`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e932`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSREngine::PrivateCall(CSREngine *this, void *a2, char *a3)
{
  unsigned int Description; // ebx
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  __int64 v12; // rdx
  int v13; // ecx
  __int64 v14; // rcx
  _OWORD *v15; // rax
  _OWORD *v16; // rdx
  CAcousticModel *v17; // rcx
  int v18; // eax
  unsigned int i; // ebp
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned __int16 *v25; // rcx
  const unsigned __int16 *v26; // r8
  CStreamPair *v27; // rcx
  CAcousticModel *v28; // rcx
  CAcousticModel *v29; // rax
  CAcousticModel *v30; // rax
  __int64 v31; // rax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  void *v37; // rsi
  CPhoneConfusionMatrix *v38; // rax
  __int16 *v39; // rdx
  CPhoneConfusionMatrix *v40; // rbp
  unsigned int v41; // edx
  __int64 v42; // rsi
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  unsigned int v46; // eax
  unsigned int v47; // eax
  float v48; // xmm6_4
  __int64 v49; // r14
  unsigned __int16 v50; // si
  unsigned __int16 j; // di
  CPPT *v52; // rcx
  struct CSLM *v54[2]; // [rsp+30h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+80h] [rbp+18h] BYREF

  pv = 0;
  if ( !a3 )
    return (unsigned int)-2147024809;
  Description = 0;
  v6 = *(_DWORD *)a3;
  if ( *(_DWORD *)a3 <= 0x10u )
  {
    if ( v6 == 16 )
    {
      v31 = *((_QWORD *)this + 87);
      if ( !v31 || (v26 = *(const unsigned __int16 **)(v31 + 56)) == 0 )
      {
        *((_WORD *)a3 + 2) = 0;
        return (unsigned int)-2147467259;
      }
      v25 = (unsigned __int16 *)(a3 + 4);
      goto LABEL_43;
    }
    if ( v6 <= 6 )
    {
      if ( v6 == 6 )
      {
        Description = SpGetDescription(*((struct ISpObjectToken **)this + 31), &pv, *((_WORD *)this + 128));
        if ( (Description & 0x80000000) == 0 )
        {
          StringCchCopyW((unsigned __int16 *)a3 + 2, 0x104u, (const unsigned __int16 *)pv);
          CoTaskMemFree(pv);
        }
        return Description;
      }
      if ( v6 )
      {
        v7 = v6 - 1;
        if ( v7 )
        {
          v8 = v7 - 1;
          if ( v8 )
          {
            v9 = v8 - 1;
            if ( v9 )
            {
              v10 = v9 - 1;
              if ( v10 )
              {
                if ( v10 != 1 )
                  return (unsigned int)-2147024809;
                return (unsigned int)CSREngine::SetProfileParameter(this, *((_DWORD *)a3 + 1), *((_DWORD *)a3 + 2));
              }
              else
              {
                return (unsigned int)CSREngine::GetProfileParameter(this, *((_DWORD *)a3 + 1), (unsigned int *)a3 + 2);
              }
            }
            else
            {
              v12 = *((_QWORD *)this + 87);
              v13 = *((_DWORD *)a3 + 2);
              *(_DWORD *)(v12 + 20) = *((_DWORD *)a3 + 1);
              *(_DWORD *)(v12 + 24) = v13;
              Description = CSREngine::SetProfileRegValue(this, L"Model Characteristic 1", *((_DWORD *)a3 + 1));
              if ( (Description & 0x80000000) != 0 )
                return Description;
              return (unsigned int)CSREngine::SetProfileRegValue(this, L"Model Characteristic 2", *((_DWORD *)a3 + 2));
            }
          }
          if ( a3 == (char *)-4LL || a3 == (char *)-8LL )
          {
            return (unsigned int)-2147467261;
          }
          else
          {
            v14 = *((_QWORD *)this + 87);
            *((_DWORD *)a3 + 1) = *(_DWORD *)(v14 + 20);
            *((_DWORD *)a3 + 2) = *(_DWORD *)(v14 + 24);
          }
          return Description;
        }
        if ( *((_DWORD *)this + 199) )
          return (unsigned int)-2147201004;
        if ( *(_BYTE *)(*((_QWORD *)this + 87) + 88LL) )
          return Description;
        v15 = *(_OWORD **)(*(_QWORD *)(*((_QWORD *)this + 17) + 88LL) + 128LL);
        if ( v15 )
        {
          *v15 = *(_OWORD *)(a3 + 4);
          v15[1] = *(_OWORD *)(a3 + 20);
          v15[2] = *(_OWORD *)(a3 + 36);
          v15[3] = *(_OWORD *)(a3 + 52);
          v15[4] = *(_OWORD *)(a3 + 68);
          v15[5] = *(_OWORD *)(a3 + 84);
          return Description;
        }
        return (unsigned int)-2147467259;
      }
      if ( *((_DWORD *)this + 199) )
        return (unsigned int)-2147201004;
      v16 = *(_OWORD **)(*(_QWORD *)(*((_QWORD *)this + 17) + 88LL) + 128LL);
      if ( v16 )
      {
LABEL_33:
        *(_OWORD *)(a3 + 4) = *v16;
        *(_OWORD *)(a3 + 20) = v16[1];
        *(_OWORD *)(a3 + 36) = v16[2];
        *(_OWORD *)(a3 + 52) = v16[3];
        *(_OWORD *)(a3 + 68) = v16[4];
        *(_OWORD *)(a3 + 84) = v16[5];
        return Description;
      }
      v17 = (CAcousticModel *)*((_QWORD *)this + 87);
      v18 = *((_DWORD *)v17 + 4);
      if ( v18 )
      {
        for ( i = 1; (i & v18) == 0; i *= 2 )
          ;
        Description = CAcousticModel::SetSampleRate(v17, i);
        if ( (Description & 0x80000000) != 0 )
          return Description;
        v16 = *(_OWORD **)(*(_QWORD *)(*((_QWORD *)this + 17) + 88LL) + 128LL);
        Description = v16 == 0 ? 0x80004005 : 0;
        if ( !v16 )
          return Description;
        goto LABEL_33;
      }
      return (unsigned int)-2147418113;
    }
    v20 = v6 - 7;
    if ( v20 )
    {
      v21 = v20 - 3;
      if ( !v21 )
      {
        if ( !*((_DWORD *)this + 199) )
        {
          v27 = *(CStreamPair **)(*((_QWORD *)this + 17) + 152LL);
          if ( v27 )
            CStreamPair::Reset(v27);
        }
        return Description;
      }
      v22 = v21 - 2;
      if ( !v22 )
        return (unsigned int)-2147418113;
      v23 = v22 - 1;
      if ( !v23 )
        return (unsigned int)CFEManager::LoadDefinitionFile(CFEManager::s_pFEManager, (const unsigned __int16 *)a3 + 2);
      v24 = v23 - 1;
      if ( !v24 )
      {
        *((_DWORD *)this + 214) = 1;
        return Description;
      }
      if ( v24 != 1 )
        return (unsigned int)-2147024809;
      v25 = (unsigned __int16 *)(a3 + 4);
      v26 = (const unsigned __int16 *)*((_QWORD *)this + 34);
LABEL_43:
      StringCchCopyW(v25, 0x104u, v26);
      return Description;
    }
    v28 = (CAcousticModel *)*((_QWORD *)this + 87);
    if ( v28 )
      CAcousticModel::`scalar deleting destructor'(v28, (unsigned int)a2);
    v29 = (CAcousticModel *)CAllocOnSpecificHeapBase::operator_new(0x1C8u, *((struct CHeap **)this + 16), 0);
    if ( v29 )
    {
      v30 = CAcousticModel::CAcousticModel(v29, this);
      *((_QWORD *)this + 87) = v30;
      if ( v30 )
      {
        Description = CAcousticModel::InitAM(v30, *((unsigned int *)a3 + 1), *((unsigned int *)a3 + 2), 1);
        if ( (Description & 0x80000000) == 0 )
          return Description;
LABEL_58:
        *((_DWORD *)this + 199) = 1;
        *((_DWORD *)this + 222) = 0;
        return Description;
      }
    }
    else
    {
      *((_QWORD *)this + 87) = 0;
    }
    Description = -2147024882;
    goto LABEL_58;
  }
  if ( v6 <= 0x1E )
  {
    if ( v6 == 30 )
    {
      *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 17) + 64LL) + 536LL) = *((_DWORD *)a3 + 1);
      return Description;
    }
    v32 = v6 - 17;
    if ( !v32 )
    {
      v54[0] = 0;
      Description = (*(__int64 (__fastcall **)(char *, struct CSLM **))(*((_QWORD *)this + 2) + 64LL))(
                      (char *)this + 16,
                      v54);
      StringCchCopyW((unsigned __int16 *)a3 + 2, 0x104u, (const unsigned __int16 *)v54[0]);
      CSpDynamicString::_free((CSpDynamicString *)v54);
      return Description;
    }
    v33 = v32 - 1;
    if ( !v33 )
    {
      Description = -2147467263;
      *((_QWORD *)a3 + 66) = 0;
      return Description;
    }
    v34 = v33 - 1;
    if ( v34 )
    {
      v35 = v34 - 1;
      if ( !v35 )
        return Description;
      v36 = v35 - 7;
      if ( !v36 )
      {
        *((_DWORD *)this + 217) = 1;
        return Description;
      }
      if ( v36 != 2 )
        return (unsigned int)-2147024809;
      v37 = (void *)*((_QWORD *)this + 16);
      if ( v37 )
      {
        v38 = (CPhoneConfusionMatrix *)CAllocOnSpecificHeapBase::operator_new(0xCA0u, *((struct CHeap **)this + 16), 0);
        if ( v38 )
        {
          v40 = CPhoneConfusionMatrix::CPhoneConfusionMatrix(v38, v39);
          if ( v40 )
          {
            v54[0] = 0;
            Description = CSREngine::FindFirstSLM(this, v54);
            if ( (Description & 0x80000000) == 0 )
            {
              (*(void (__fastcall **)(struct CSLM *))(*(_QWORD *)v54[0] + 8LL))(v54[0]);
              Description = -2147467263;
            }
            CPhoneConfusionMatrix::`scalar deleting destructor'(v40, v41);
          }
        }
        operator delete(v37);
      }
    }
    else
    {
      v42 = *((_QWORD *)a3 + 1);
      if ( v42 )
      {
        (*(void (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v42 + 56LL))(
          v42,
          ((unsigned __int64)this + 16) & -(__int64)(this != 0));
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      }
    }
    return Description;
  }
  v43 = v6 - 32;
  if ( !v43 )
    return (unsigned int)CSREngine::SetDefaultTrigramStoreSettings(this, (const struct CTrigramStoreSettings *)(a3 + 4));
  v44 = v43 - 1;
  if ( v44 )
  {
    v45 = v44 - 1;
    if ( v45 )
    {
      v46 = v45 - 9;
      if ( v46 )
      {
        v47 = v46 - 1;
        if ( !v47 )
        {
          *((float *)a3 + 1) = *(double *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 17) + 64LL) + 80LL) + 488LL);
          return Description;
        }
        if ( v47 != 1 )
          return (unsigned int)-2147024809;
        return (unsigned int)CDecoder::CheckLattice(this, *((struct LATTICE_HEADER **)a3 + 1), *((_DWORD *)a3 + 4));
      }
      v48 = *((float *)a3 + 1);
      *(double *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 17) + 64LL) + 80LL) + 488LL) = v48;
      v49 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 17) + 64LL) + 80LL) + 232LL;
      if ( *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 17) + 64LL) + 80LL) != -232 )
      {
        v50 = *(_WORD *)v49;
        for ( j = 0; j < v50; ++j )
        {
          v52 = *(CPPT **)(*(_QWORD *)(v49 + 16) + 16LL * j);
          if ( v52 )
          {
            Description = CPPT::ConstructWeightedCodebook(v52, v48);
            if ( (Description & 0x80000000) != 0 )
              break;
          }
        }
        return Description;
      }
      return (unsigned int)-2147467259;
    }
  }
  return Description;
}

```

## disassembly

```asm
0x18000e6b0  mov     rax, rsp
0x18000e6b3  mov     [rax+8], rbx
0x18000e6b7  mov     [rax+10h], rbp
0x18000e6bb  push    rsi
0x18000e6bc  push    rdi
0x18000e6bd  push    r14
0x18000e6bf  sub     rsp, 50h
0x18000e6c3  movaps  xmmword ptr [rax-28h], xmm6
0x18000e6c7  mov     rsi, r8
0x18000e6ca  mov     rdi, rcx
0x18000e6cd  mov     qword ptr [rax+18h], 0
0x18000e6d5  test    r8, r8
0x18000e6d8  jnz     short loc_18000E6E4
0x18000e6da  mov     ebx, 80070057h
0x18000e6df  jmp     loc_18000ECF5
0x18000e6e4  xor     ebx, ebx
0x18000e6e6  mov     eax, [r8]
0x18000e6e9  cmp     eax, 10h
0x18000e6ec  ja      loc_18000EA96
0x18000e6f2  jz      loc_18000EA68
0x18000e6f8  cmp     eax, 6
0x18000e6fb  ja      loc_18000E93D
0x18000e701  jz      loc_18000E8EE
0x18000e707  test    eax, eax
0x18000e709  jz      loc_18000E83E
0x18000e70f  sub     eax, 1
0x18000e712  jz      loc_18000E7C7
0x18000e718  sub     eax, 1
0x18000e71b  jz      short loc_18000E798
0x18000e71d  sub     eax, 1
0x18000e720  jz      short loc_18000E74E
0x18000e722  sub     eax, 1
0x18000e725  jz      short loc_18000E73D
0x18000e727  cmp     eax, 1
0x18000e72a  jnz     short loc_18000E6DA
0x18000e72c  mov     r8d, [r8+8]; unsigned int
0x18000e730  mov     edx, [rsi+4]; int
0x18000e733  call    ?SetProfileParameter@CSREngine@@AEAAJHK@Z; CSREngine::SetProfileParameter(int,ulong)
0x18000e738  jmp     loc_18000ECF3
0x18000e73d  add     r8, 8; unsigned int *
0x18000e741  mov     edx, [rsi+4]; int
0x18000e744  call    ?GetProfileParameter@CSREngine@@AEAAJHPEAK@Z; CSREngine::GetProfileParameter(int,ulong *)
0x18000e749  jmp     loc_18000ECF3
0x18000e74e  mov     rdx, [rcx+2B8h]
0x18000e755  mov     ecx, [r8+8]
0x18000e759  mov     eax, [r8+4]
0x18000e75d  mov     [rdx+14h], eax
0x18000e760  mov     [rdx+18h], ecx
0x18000e763  mov     r8d, [r8+4]; unsigned int
0x18000e767  lea     rdx, aModelCharacter_0; "Model Characteristic 1"
0x18000e76e  mov     rcx, rdi; this
0x18000e771  call    ?SetProfileRegValue@CSREngine@@AEAAJPEBGK@Z; CSREngine::SetProfileRegValue(ushort const *,ulong)
0x18000e776  mov     ebx, eax
0x18000e778  test    eax, eax
0x18000e77a  js      loc_18000ECF5
0x18000e780  mov     r8d, [rsi+8]; unsigned int
0x18000e784  lea     rdx, aModelCharacter; "Model Characteristic 2"
0x18000e78b  mov     rcx, rdi; this
0x18000e78e  call    ?SetProfileRegValue@CSREngine@@AEAAJPEBGK@Z; CSREngine::SetProfileRegValue(ushort const *,ulong)
0x18000e793  jmp     loc_18000ECF3
0x18000e798  lea     rdx, [r8+4]
0x18000e79c  test    rdx, rdx
0x18000e79f  jz      short loc_18000E7BD
0x18000e7a1  add     rsi, 8
0x18000e7a5  jz      short loc_18000E7BD
0x18000e7a7  mov     rcx, [rcx+2B8h]
0x18000e7ae  mov     eax, [rcx+14h]
0x18000e7b1  mov     [rdx], eax
0x18000e7b3  mov     eax, [rcx+18h]
0x18000e7b6  mov     [rsi], eax
0x18000e7b8  jmp     loc_18000ECF5
0x18000e7bd  mov     ebx, 80004003h
0x18000e7c2  jmp     loc_18000ECF5
0x18000e7c7  cmp     [rcx+31Ch], ebx
0x18000e7cd  jz      short loc_18000E7D9
0x18000e7cf  mov     ebx, 80045014h
0x18000e7d4  jmp     loc_18000ECF5
0x18000e7d9  mov     rax, [rcx+2B8h]
0x18000e7e0  cmp     [rax+58h], bl
0x18000e7e3  jnz     loc_18000ECF5
0x18000e7e9  mov     rax, [rcx+88h]
0x18000e7f0  mov     rcx, [rax+58h]
0x18000e7f4  mov     rax, [rcx+80h]
0x18000e7fb  test    rax, rax
0x18000e7fe  jz      loc_18000EA8C
0x18000e804  movups  xmm0, xmmword ptr [r8+4]
0x18000e809  movups  xmmword ptr [rax], xmm0
0x18000e80c  movups  xmm1, xmmword ptr [r8+14h]
0x18000e811  movups  xmmword ptr [rax+10h], xmm1
0x18000e815  movups  xmm0, xmmword ptr [r8+24h]
0x18000e81a  movups  xmmword ptr [rax+20h], xmm0
0x18000e81e  movups  xmm1, xmmword ptr [r8+34h]
0x18000e823  movups  xmmword ptr [rax+30h], xmm1
0x18000e827  movups  xmm0, xmmword ptr [r8+44h]
0x18000e82c  movups  xmmword ptr [rax+40h], xmm0
0x18000e830  movups  xmm1, xmmword ptr [r8+54h]
0x18000e835  movups  xmmword ptr [rax+50h], xmm1
0x18000e839  jmp     loc_18000ECF5
0x18000e83e  cmp     [rcx+31Ch], ebx
0x18000e844  jnz     short loc_18000E7CF
0x18000e846  mov     rax, [rcx+88h]
0x18000e84d  mov     rcx, [rax+58h]
0x18000e851  mov     rdx, [rcx+80h]
0x18000e858  test    rdx, rdx
0x18000e85b  jnz     short loc_18000E8BA
0x18000e85d  mov     rcx, [rdi+2B8h]; this
0x18000e864  mov     eax, [rcx+10h]
0x18000e867  test    eax, eax
0x18000e869  jz      loc_18000E9A1
0x18000e86f  lea     ebp, [rdx+1]
0x18000e872  test    bpl, al
0x18000e875  jnz     short loc_18000E87D
0x18000e877  add     ebp, ebp
0x18000e879  test    eax, ebp
0x18000e87b  jz      short loc_18000E877
0x18000e87d  mov     edx, ebp; unsigned int
0x18000e87f  call    ?SetSampleRate@CAcousticModel@@QEAAJK@Z; CAcousticModel::SetSampleRate(ulong)
0x18000e884  mov     ebx, eax
0x18000e886  test    eax, eax
0x18000e888  js      loc_18000ECF5
0x18000e88e  mov     rax, [rdi+88h]
0x18000e895  mov     rcx, [rax+58h]
0x18000e899  mov     rdx, [rcx+80h]
0x18000e8a0  mov     rax, rdx
0x18000e8a3  neg     rax
0x18000e8a6  sbb     ecx, ecx
0x18000e8a8  not     ecx
0x18000e8aa  mov     ebx, 80004005h
0x18000e8af  and     ebx, ecx
0x18000e8b1  test    rdx, rdx
0x18000e8b4  jz      loc_18000ECF5
0x18000e8ba  movups  xmm0, xmmword ptr [rdx]
0x18000e8bd  movups  xmmword ptr [rsi+4], xmm0
0x18000e8c1  movups  xmm1, xmmword ptr [rdx+10h]
0x18000e8c5  movups  xmmword ptr [rsi+14h], xmm1
0x18000e8c9  movups  xmm0, xmmword ptr [rdx+20h]
0x18000e8cd  movups  xmmword ptr [rsi+24h], xmm0
0x18000e8d1  movups  xmm1, xmmword ptr [rdx+30h]
0x18000e8d5  movups  xmmword ptr [rsi+34h], xmm1
0x18000e8d9  movups  xmm0, xmmword ptr [rdx+40h]
0x18000e8dd  movups  xmmword ptr [rsi+44h], xmm0
0x18000e8e1  movups  xmm1, xmmword ptr [rdx+50h]
0x18000e8e5  movups  xmmword ptr [rsi+54h], xmm1
0x18000e8e9  jmp     loc_18000ECF5
0x18000e8ee  movzx   r8d, word ptr [rcx+100h]; unsigned __int16
0x18000e8f6  lea     rdx, [rsp+68h+pv]; unsigned __int16 **
0x18000e8fe  mov     rcx, [rcx+0F8h]; struct ISpObjectToken *
0x18000e905  call    ?SpGetDescription@@YAJPEAUISpObjectToken@@PEAPEAGG@Z; SpGetDescription(ISpObjectToken *,ushort * *,ushort)
0x18000e90a  mov     ebx, eax
0x18000e90c  test    eax, eax
0x18000e90e  js      loc_18000ECF5
0x18000e914  lea     rcx, [rsi+4]; unsigned __int16 *
0x18000e918  mov     r8, [rsp+68h+pv]; unsigned __int16 *
0x18000e920  mov     edx, 104h; unsigned __int64
0x18000e925  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e92a  mov     rcx, [rsp+68h+pv]; pv
0x18000e932  call    cs:__imp_CoTaskMemFree
0x18000e938  jmp     loc_18000ECF5
0x18000e93d  sub     eax, 7
0x18000e940  jz      loc_18000E9D8
0x18000e946  sub     eax, 3
0x18000e949  jz      short loc_18000E9AB
0x18000e94b  sub     eax, 2
0x18000e94e  jz      short loc_18000E9A1
0x18000e950  sub     eax, 1
0x18000e953  jz      short loc_18000E98C
0x18000e955  sub     eax, 1
0x18000e958  jz      short loc_18000E97D
0x18000e95a  cmp     eax, 1
0x18000e95d  jnz     loc_18000E6DA
0x18000e963  lea     rcx, [r8+4]; unsigned __int16 *
0x18000e967  mov     r8, [rdi+110h]; unsigned __int16 *
0x18000e96e  mov     edx, 104h; unsigned __int64
0x18000e973  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e978  jmp     loc_18000ECF5
0x18000e97d  mov     dword ptr [rcx+358h], 1
0x18000e987  jmp     loc_18000ECF5
0x18000e98c  lea     rdx, [r8+4]; unsigned __int16 *
0x18000e990  mov     rcx, cs:?s_pFEManager@CFEManager@@0PEAV1@EA; lpCriticalSection
0x18000e997  call    ?LoadDefinitionFile@CFEManager@@QEAAJPEBG@Z; CFEManager::LoadDefinitionFile(ushort const *)
0x18000e99c  jmp     loc_18000ECF3
0x18000e9a1  mov     ebx, 8000FFFFh
0x18000e9a6  jmp     loc_18000ECF5
0x18000e9ab  cmp     [rcx+31Ch], ebx
0x18000e9b1  jnz     loc_18000ECF5
0x18000e9b7  mov     rax, [rcx+88h]
0x18000e9be  mov     rcx, [rax+98h]; this
0x18000e9c5  test    rcx, rcx
0x18000e9c8  jz      loc_18000ECF5
0x18000e9ce  call    ?Reset@CStreamPair@@QEAAJXZ; CStreamPair::Reset(void)
0x18000e9d3  jmp     loc_18000ECF5
0x18000e9d8  mov     rcx, [rcx+2B8h]; this
0x18000e9df  mov     ebx, [rcx+24h]
0x18000e9e2  test    rcx, rcx
0x18000e9e5  jz      short loc_18000E9EC
0x18000e9e7  call    ??_GCAcousticModel@@QEAAPEAXI@Z; CAcousticModel::`scalar deleting destructor'(uint)
0x18000e9ec  xor     r8d, r8d; bool
0x18000e9ef  mov     rdx, [rdi+80h]; struct CHeap *
0x18000e9f6  mov     ecx, 1C8h; unsigned __int64
0x18000e9fb  call    ?operator_new@CAllocOnSpecificHeapBase@@SAPEAX_KPEAVCHeap@@_N@Z; CAllocOnSpecificHeapBase::operator_new(unsigned __int64,CHeap *,bool)
0x18000ea00  mov     ebp, 1
0x18000ea05  test    rax, rax
0x18000ea08  jz      short loc_18000EA43
0x18000ea0a  mov     rdx, rdi; struct CSREngine *
0x18000ea0d  mov     rcx, rax; this
0x18000ea10  call    ??0CAcousticModel@@QEAA@PEAVCSREngine@@@Z; CAcousticModel::CAcousticModel(CSREngine *)
0x18000ea15  mov     [rdi+2B8h], rax
0x18000ea1c  test    rax, rax
0x18000ea1f  jz      short loc_18000EA4E
0x18000ea21  mov     [rsp+68h+var_40], ebx
0x18000ea25  mov     r9d, ebp
0x18000ea28  mov     r8d, [rsi+8]
0x18000ea2c  mov     edx, [rsi+4]
0x18000ea2f  mov     rcx, rax
0x18000ea32  call    ?InitAM@CAcousticModel@@QEAAJW4MSAM_AGE@@W4MSAM_GENDER@@W4MSAM_AUTOD@@W4MSAM_USAGE@@K@Z; CAcousticModel::InitAM(MSAM_AGE,MSAM_GENDER,MSAM_AUTOD,MSAM_USAGE,ulong)
0x18000ea37  mov     ebx, eax
0x18000ea39  test    eax, eax
0x18000ea3b  jns     loc_18000ECF5
0x18000ea41  jmp     short loc_18000EA53
0x18000ea43  mov     qword ptr [rdi+2B8h], 0
0x18000ea4e  mov     ebx, 8007000Eh
0x18000ea53  mov     [rdi+31Ch], ebp
0x18000ea59  mov     dword ptr [rdi+378h], 0
0x18000ea63  jmp     loc_18000ECF5
0x18000ea68  mov     rax, [rcx+2B8h]
0x18000ea6f  test    rax, rax
0x18000ea72  jz      short loc_18000EA86
0x18000ea74  mov     r8, [rax+38h]
0x18000ea78  test    r8, r8
0x18000ea7b  jz      short loc_18000EA86
0x18000ea7d  lea     rcx, [rsi+4]
0x18000ea81  jmp     loc_18000E96E
0x18000ea86  xor     eax, eax
0x18000ea88  mov     [rsi+4], ax
0x18000ea8c  mov     ebx, 80004005h
0x18000ea91  jmp     loc_18000ECF5
0x18000ea96  cmp     eax, 1Eh
0x18000ea99  ja      loc_18000EC0D
0x18000ea9f  jz      loc_18000EBF3
0x18000eaa5  sub     eax, 11h
0x18000eaa8  jz      loc_18000EBB4
0x18000eaae  sub     eax, 1
0x18000eab1  jz      loc_18000EB9F
0x18000eab7  sub     eax, 1
0x18000eaba  jz      loc_18000EB62
0x18000eac0  sub     eax, 1
0x18000eac3  jz      loc_18000ECF5
0x18000eac9  sub     eax, 7
0x18000eacc  jz      loc_18000EB53
0x18000ead2  cmp     eax, 2
0x18000ead5  jnz     loc_18000E6DA
0x18000eadb  mov     rsi, [rcx+80h]
0x18000eae2  test    rsi, rsi
0x18000eae5  jz      loc_18000ECF5
0x18000eaeb  xor     r8d, r8d; bool
0x18000eaee  mov     rdx, rsi; struct CHeap *
0x18000eaf1  mov     ecx, 0CA0h; unsigned __int64
0x18000eaf6  call    ?operator_new@CAllocOnSpecificHeapBase@@SAPEAX_KPEAVCHeap@@_N@Z; CAllocOnSpecificHeapBase::operator_new(unsigned __int64,CHeap *,bool)
0x18000eafb  test    rax, rax
0x18000eafe  jz      short loc_18000EB46
0x18000eb00  mov     rcx, rax; this
0x18000eb03  call    ??0CPhoneConfusionMatrix@@QEAA@PEAF@Z; CPhoneConfusionMatrix::CPhoneConfusionMatrix(short *)
0x18000eb08  mov     rbp, rax
0x18000eb0b  test    rax, rax
0x18000eb0e  jz      short loc_18000EB46
0x18000eb10  mov     [rsp+68h+var_38], rbx
0x18000eb15  lea     rdx, [rsp+68h+var_38]; struct CSLM **
0x18000eb1a  mov     rcx, rdi; this
0x18000eb1d  call    ?FindFirstSLM@CSREngine@@QEAAJPEAPEAVCSLM@@@Z; CSREngine::FindFirstSLM(CSLM * *)
0x18000eb22  mov     ebx, eax
0x18000eb24  test    eax, eax
0x18000eb26  js      short loc_18000EB3E
0x18000eb28  mov     rcx, [rsp+68h+var_38]
0x18000eb2d  mov     rdx, [rcx]
0x18000eb30  mov     rax, [rdx+8]
0x18000eb34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb39  mov     ebx, 80004001h
0x18000eb3e  mov     rcx, rbp; this
0x18000eb41  call    ??_GCPhoneConfusionMatrix@@QEAAPEAXI@Z; CPhoneConfusionMatrix::`scalar deleting destructor'(uint)
0x18000eb46  mov     rcx, rsi; void *
0x18000eb49  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000eb4e  jmp     loc_18000ECF5
0x18000eb53  mov     dword ptr [rcx+364h], 1
0x18000eb5d  jmp     loc_18000ECF5
0x18000eb62  mov     rsi, [r8+8]
0x18000eb66  test    rsi, rsi
0x18000eb69  jz      loc_18000ECF5
0x18000eb6f  mov     r8, [rsi]
0x18000eb72  lea     rax, [rcx+10h]
0x18000eb76  neg     rdi
0x18000eb79  sbb     rdx, rdx
0x18000eb7c  and     rdx, rax
0x18000eb7f  mov     rcx, rsi
0x18000eb82  mov     rax, [r8+38h]
0x18000eb86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb8b  mov     rax, [rsi]
0x18000eb8e  mov     rcx, rsi
0x18000eb91  mov     rax, [rax+10h]
0x18000eb95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb9a  jmp     loc_18000ECF5
  ... truncated ...
```
