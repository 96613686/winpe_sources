# SDB_POOL_CONFIG::RebalancePhase1Transaction(unsigned __int64 *)

- ea: `0x140063c00`
- end: `0x1400641c8`
- name: `?RebalancePhase1Transaction@SDB_POOL_CONFIG@@QEAAJPEA_K@Z`
- size: `1480`
- prototype: `__int64 __fastcall(SDB_POOL_CONFIG *__hidden this, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x1400612c0`

## callees

- `0x14000ba20`
- `0x14000c630`
- `0x14000c840`
- `0x14000cbd0`
- `0x14000d2b0`
- `0x14000e530`
- `0x140012ce0`
- `0x140018360`
- `0x1400268c0`
- `0x14005c86c`
- `0x14005f664`
- `0x140062520`
- `0x140062bf0`
- `0x140063c00`
- `0x1400b3070`
- `0x1400b33a4`
- `0x1400b6b10`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140064183`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064183`

## pseudocode

```c
__int64 __fastcall SDB_POOL_CONFIG::RebalancePhase1Transaction(SDB_POOL_CONFIG *this, unsigned __int64 *a2)
{
  unsigned int v2; // r12d
  SDB_RECORD *v4; // rcx
  _QWORD *v5; // r13
  int v6; // esi
  __int64 v7; // rax
  __int64 v8; // rdi
  SDB_RECORD *v9; // rcx
  unsigned int v10; // r15d
  SDB_RECORD *i; // r8
  SDB_RECORD *RecordByType; // rax
  SDB_RECORD *v13; // rbx
  __int64 v14; // rbx
  unsigned __int64 v15; // rdi
  __int64 v16; // r15
  _QWORD *LastObject; // rax
  __int64 v18; // rdx
  __int64 v19; // r15
  unsigned __int64 v20; // rdi
  int v21; // esi
  __int64 v22; // rbx
  __int64 RecordByRecordId; // rax
  __int64 v24; // rax
  __int64 v25; // rbx
  __int64 v26; // rax
  __int64 v27; // rdx
  unsigned __int64 v28; // r15
  struct SC_ARRAY *Array; // rax
  struct SC_ARRAY *v30; // rcx
  __int64 v31; // r15
  __int64 v32; // rax
  struct SDB_RECORD *Space; // rax
  __int64 v34; // r15
  __int16 v35; // ax
  _QWORD *j; // r8
  __int64 v37; // rcx
  int v38; // eax
  struct _SP_PROVISIONING_INFO *v39; // rax
  struct SDB_RECORD *v40; // rax
  __int64 v41; // rax
  unsigned __int64 v42; // r8
  unsigned __int64 v43; // rdx
  __int64 v44; // rdx
  __int64 v45; // rax
  SDB_RECORD *v46; // rcx
  void *k; // r8
  void *v48; // rax
  void *v49; // rbx
  __int64 v51; // [rsp+30h] [rbp-89h]
  char *v52; // [rsp+38h] [rbp-81h]
  unsigned __int64 v53; // [rsp+40h] [rbp-79h]
  unsigned __int64 v54; // [rsp+48h] [rbp-71h]
  SDB_DRIVE *v55; // [rsp+58h] [rbp-61h]
  unsigned __int64 v56; // [rsp+60h] [rbp-59h] BYREF
  _QWORD v57[3]; // [rsp+70h] [rbp-49h] BYREF
  __int16 v58; // [rsp+88h] [rbp-31h]
  unsigned __int64 v59; // [rsp+A0h] [rbp-19h]
  int v60; // [rsp+B8h] [rbp-1h]
  __int16 v61; // [rsp+BCh] [rbp+3h]
  int v62; // [rsp+120h] [rbp+67h]
  unsigned __int64 *v63; // [rsp+128h] [rbp+6Fh]
  int v64; // [rsp+130h] [rbp+77h]
  int v65; // [rsp+138h] [rbp+7Fh]

  v63 = a2;
  v2 = 0;
  v60 = -1;
  *a2 = 0;
  v57[0] = &SDB_EXTENT::`vftable';
  v4 = (SDB_RECORD *)*((_QWORD *)this + 34);
  v5 = 0;
  v57[1] = 0;
  v6 = 0;
  v57[2] = 0;
  v58 = 0;
  v7 = *((_WORD *)v4 + 15) & 1;
  v61 = 0;
  v62 = 0;
  v8 = *((_QWORD *)v4 + v7 + 4);
  v51 = v8;
  if ( (*(_BYTE *)(v8 + 64) & 0x10) == 0 )
  {
    v62 = SDB_RECORD::PreTouch(v4, 0);
    v6 = v62;
    if ( v62 < 0 )
      goto LABEL_61;
    v9 = (SDB_RECORD *)*((_QWORD *)this + 34);
    v8 = *((_QWORD *)v9 + (*((_WORD *)v9 + 15) & 1) + 4);
    v51 = v8;
    SDB_RECORD::Touch(v9);
    *(_WORD *)(v8 + 64) |= 0x10u;
    if ( !*(_QWORD *)(v8 + 296) )
      *(_QWORD *)(v8 + 296) = MEMORY[0xFFFFF78000000014];
  }
  v10 = 0;
  for ( i = 0; ; i = v13 )
  {
    LOBYTE(a2) = 2;
    RecordByType = (SDB_RECORD *)SDB_POOL_CONFIG::GetRecordByType(this, a2, i);
    v13 = RecordByType;
    if ( !RecordByType )
      break;
    v62 = SDB_RECORD::PreTouch(RecordByType, 0);
    v6 = v62;
    if ( v62 < 0 )
      goto LABEL_61;
    ++v10;
  }
  v5 = SC_ENV::Allocate(8LL * v10, 0x58587053u, 0, 0);
  if ( v5 )
  {
    v65 = 0;
    LOBYTE(a2) = 2;
    v53 = 0;
    v64 = 0;
    v14 = SDB_POOL_CONFIG::GetRecordByType(this, a2, 0);
    if ( v14 )
    {
      v15 = 0;
      do
      {
        v16 = *(_QWORD *)(v14 + 8LL * (*(_WORD *)(v14 + 30) & 1) + 32);
        LastObject = SC_SPARSE::FindLastObject(*(SC_SPARSE **)(v16 + 192), &v56);
        v5[v2] = LastObject;
        if ( LastObject )
        {
          ++v2;
          v18 = LastObject[(*((_WORD *)LastObject + 15) & 1) + 4];
          if ( *(_QWORD *)(v16 + 280) - *(_QWORD *)(v18 + 48) - *(_QWORD *)(v18 + 32) > v15 )
            v15 = *(_QWORD *)(v16 + 280) - *(_QWORD *)(v18 + 48) - *(_QWORD *)(v18 + 32);
        }
        LOBYTE(v18) = 2;
        v14 = SDB_POOL_CONFIG::GetRecordByType(this, v18, v14);
      }
      while ( v14 );
      v53 = v15;
      v8 = v51;
    }
    *(_QWORD *)(v8 + 272) = 0;
    *(_QWORD *)(v8 + 288) = 0;
LABEL_19:
    while ( v2 )
    {
      v19 = 0;
      v20 = -1;
      v21 = v64;
      do
      {
        LOBYTE(a2) = 2;
        v22 = *(_QWORD *)(v5[v19] + 8LL * (*(_WORD *)(v5[v19] + 30LL) & 1) + 32);
        RecordByRecordId = SDB_POOL_CONFIG::FindRecordByRecordId(*(_QWORD *)(*(_QWORD *)(v22 + 16) + 16LL), a2);
        v24 = *(_QWORD *)(RecordByRecordId + 8LL * (*(_WORD *)(RecordByRecordId + 30) & 1) + 32);
        a2 = (unsigned __int64 *)(*(_QWORD *)(v24 + 280) - *(_QWORD *)(v22 + 48));
        if ( (unsigned __int64)a2 >= v20 )
        {
          if ( a2 == (unsigned __int64 *)v20 && !SDB_POOL_CONFIG::GetRandom(this, ++v65) )
            v21 = v19;
        }
        else
        {
          v20 = *(_QWORD *)(v24 + 280) - *(_QWORD *)(v22 + 48);
          v65 = 1;
          v21 = v19;
        }
        v19 = (unsigned int)(v19 + 1);
      }
      while ( (unsigned int)v19 < v2 );
      v64 = v21;
      v6 = v62;
      v54 = v20;
      v8 = v51;
      LOBYTE(a2) = 2;
      v52 = (char *)&v5[v64];
      v25 = *(_QWORD *)(*(_QWORD *)v52 + 8LL * (*(_WORD *)(*(_QWORD *)v52 + 30LL) & 1) + 32);
      v26 = SDB_POOL_CONFIG::FindRecordByRecordId(*(_QWORD *)(*(_QWORD *)(v25 + 16) + 16LL), a2);
      v27 = *(_QWORD *)(v26 + 8LL * (*(_WORD *)(v26 + 30) & 1) + 32);
      v55 = (SDB_DRIVE *)v27;
      v28 = *(_QWORD *)(v25 + 48) >> *(_DWORD *)(v27 + 220);
      if ( (__int64)(v28 - 1) < 0
        || (v56 = *(_QWORD *)(v27 + 192), Array = SC_SPARSE::GetArray((SC_SPARSE *)v56, v28), (v30 = Array) == 0)
        || Array == (struct SC_ARRAY *)(v56 + 8) )
      {
LABEL_37:
        --v2;
        *(_QWORD *)v52 = 0;
        *(_QWORD *)v52 = v5[v2];
        v5[v2] = 0;
      }
      else
      {
        v31 = v28 - *((_QWORD *)Array + 2);
        do
        {
          --v31;
          while ( v31 < 0 )
          {
            v30 = (struct SC_ARRAY *)*((_QWORD *)v30 + 1);
            if ( v30 == (struct SC_ARRAY *)(v56 + 8) )
              goto LABEL_37;
            v31 = (unsigned int)(*(_DWORD *)(v56 + 52) - 1);
          }
          v32 = *((_QWORD *)v30 + v31 + 3);
        }
        while ( !v32 );
        *(_QWORD *)v52 = v32;
      }
      Space = SDB_EXTENT::GetSpace((SDB_EXTENT *)v25);
      v34 = *((_QWORD *)Space + (*((_WORD *)Space + 15) & 1) + 4);
      if ( ((*(_BYTE *)(v34 + 66) - 1) & 0xF7) != 0 && SDB_EXTENT::SupportsSafeReallocation((SDB_EXTENT *)v25) )
      {
        if ( (*(_BYTE *)(v25 + 76) & 2) != 0 )
        {
          *(_QWORD *)(v51 + 272) += *(_QWORD *)(v25 + 32);
          *(_QWORD *)(v51 + 288) += *(_QWORD *)(v25 + 32);
          SDB_DRIVE::ChangeSlabBitmap(v55, *(_QWORD *)(v25 + 48), *(_QWORD *)(v25 + 32), 0);
        }
        if ( *(_DWORD *)(v25 + 72) == -1 )
        {
          v35 = *(_WORD *)(v25 + 78);
          if ( (v35 & 1) != 0 )
            *(_WORD *)(v25 + 78) = v35 & 0xFFFE;
          if ( ((*(_BYTE *)(v25 + 76) & 8) != 0 || v54 <= v53) && (*(_BYTE *)(v51 + 64) & 8) != 0 )
          {
            for ( j = SC_SPARSE::GetObject(*(SC_SPARSE **)(v34 + 232), *(_QWORD *)(v25 + 40) / *(_QWORD *)(v34 + 272));
                  j;
                  j = *(_QWORD **)(v37 + 80) )
            {
              v37 = j[(*((_WORD *)j + 15) & 1) + 4];
              if ( (*(_BYTE *)(v37 + 78) & 1) != 0 )
                goto LABEL_19;
            }
            v38 = SDB_POOL_CONFIG::PickDrive(this, (struct SDB_EXTENT *)v25, 1u, 1u, (struct SDB_EXTENT *)v57);
            v62 = v38;
            v6 = v38;
            if ( v38 == -1073740703 || v38 == -1073741823 )
            {
              v6 = 0;
              v62 = 0;
            }
            else
            {
              if ( v38 < 0 )
                goto LABEL_61;
              v39 = SDB_EXTENT::Provisioning((SDB_EXTENT *)v25);
              if ( SDB_POOL_CONFIG::IsBetterAllocation(
                     this,
                     (struct SDB_EXTENT *)v57,
                     (struct SDB_EXTENT *)v25,
                     *((_QWORD *)v39 + 1)) )
              {
                v40 = SDB_EXTENT::GetSpace((SDB_EXTENT *)v25);
                v41 = *((_QWORD *)v40 + (*((_WORD *)v40 + 15) & 1LL) + 4);
                *(_WORD *)(v41 + 352) |= 4u;
                v42 = *(_QWORD *)(v25 + 32);
                v43 = *(_QWORD *)(v25 + 48);
                *(_WORD *)(v25 + 78) |= 1u;
                SDB_DRIVE::ChangeSlabBitmap(v55, v43, v42, 0);
                LOBYTE(v44) = 2;
                v45 = SDB_POOL_CONFIG::FindRecordByRecordId(this, v44);
                SDB_DRIVE::ChangeSlabBitmap(
                  *(SDB_DRIVE **)(v45 + 8 * (*(_WORD *)(v45 + 30) & 1LL) + 32),
                  v59,
                  *(_QWORD *)(v25 + 32),
                  1u);
                *(_QWORD *)(v51 + 272) += *(_QWORD *)(v25 + 32);
              }
            }
          }
        }
      }
    }
    if ( !*(_QWORD *)(v8 + 272) )
    {
      v6 = SDB_RECORD::PreTouch(*((SDB_RECORD **)this + 34), 0);
      if ( v6 >= 0 )
      {
        v46 = (SDB_RECORD *)*((_QWORD *)this + 34);
        v8 = *((_QWORD *)v46 + (*((_WORD *)v46 + 15) & 1LL) + 4);
        SDB_RECORD::Touch(v46);
        *(_QWORD *)(v8 + 280) = 0;
        *(_WORD *)(v8 + 64) &= 0xFFE7u;
        *(_QWORD *)(v8 + 296) = 0;
      }
    }
  }
  else
  {
    v6 = -1073741670;
  }
LABEL_61:
  *v63 = *(_QWORD *)(v8 + 272);
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  for ( k = 0; ; k = v49 )
  {
    LOBYTE(a2) = 2;
    v48 = (void *)SDB_POOL_CONFIG::GetRecordByType(this, a2, k);
    v49 = v48;
    if ( !v48 )
      break;
    SDB_RECORD::Abort(v48);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140063c00  mov     [rsp-8+arg_8], rdx
0x140063c05  push    rbp
0x140063c06  push    rbx
0x140063c07  push    rsi
0x140063c08  push    rdi
0x140063c09  push    r12
0x140063c0b  push    r13
0x140063c0d  push    r14
0x140063c0f  push    r15
0x140063c11  lea     rbp, [rsp-1Fh]
0x140063c16  sub     rsp, 0D8h
0x140063c1d  xor     r12d, r12d
0x140063c20  mov     [rbp+57h+var_58], 0FFFFFFFFh
0x140063c27  mov     [rdx], r12
0x140063c2a  lea     rax, ??_7SDB_EXTENT@@6B@; const SDB_EXTENT::`vftable'
0x140063c31  mov     [rbp+57h+var_A0], rax
0x140063c35  mov     r14, rcx
0x140063c38  mov     rcx, [rcx+110h]; this
0x140063c3f  mov     r13d, r12d
0x140063c42  mov     [rbp+57h+var_98], r12
0x140063c46  mov     esi, r12d
0x140063c49  mov     [rbp+57h+var_90], r12
0x140063c4d  mov     [rbp+57h+var_88], r12w
0x140063c52  movzx   eax, word ptr [rcx+1Eh]
0x140063c56  and     eax, 1
0x140063c59  mov     [rbp+57h+var_54], r12w
0x140063c5e  mov     [rbp+57h+arg_0], r12d
0x140063c62  mov     rdi, [rcx+rax*8+20h]
0x140063c67  mov     [rsp+110h+var_E0], rdi
0x140063c6c  test    byte ptr [rdi+40h], 10h
0x140063c70  jnz     short loc_140063CC5
0x140063c72  xor     edx, edx; struct SDB_OBJECT *
0x140063c74  call    ?PreTouch@SDB_RECORD@@QEAAJPEAVSDB_OBJECT@@@Z; SDB_RECORD::PreTouch(SDB_OBJECT *)
0x140063c79  mov     [rbp+57h+arg_0], eax
0x140063c7c  mov     esi, eax
0x140063c7e  test    eax, eax
0x140063c80  js      loc_14006416B
0x140063c86  mov     rcx, [r14+110h]; this
0x140063c8d  movzx   eax, word ptr [rcx+1Eh]
0x140063c91  and     eax, 1
0x140063c94  mov     rdi, [rcx+rax*8+20h]
0x140063c99  mov     [rsp+110h+var_E0], rdi
0x140063c9e  call    ?Touch@SDB_RECORD@@QEAAXXZ; SDB_RECORD::Touch(void)
0x140063ca3  or      word ptr [rdi+40h], 10h
0x140063ca8  cmp     [rdi+128h], r12
0x140063caf  jnz     short loc_140063CC5
0x140063cb1  mov     rax, 0FFFFF78000000014h
0x140063cbb  mov     rax, [rax]
0x140063cbe  mov     [rdi+128h], rax
0x140063cc5  mov     r15d, r12d
0x140063cc8  xor     r8d, r8d
0x140063ccb  mov     dl, 2
0x140063ccd  mov     rcx, r14
0x140063cd0  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x140063cd5  mov     rbx, rax
0x140063cd8  test    rax, rax
0x140063cdb  jz      short loc_140063CFC
0x140063cdd  xor     edx, edx; struct SDB_OBJECT *
0x140063cdf  mov     rcx, rax; this
0x140063ce2  call    ?PreTouch@SDB_RECORD@@QEAAJPEAVSDB_OBJECT@@@Z; SDB_RECORD::PreTouch(SDB_OBJECT *)
0x140063ce7  mov     [rbp+57h+arg_0], eax
0x140063cea  mov     esi, eax
0x140063cec  test    eax, eax
0x140063cee  js      loc_14006416B
0x140063cf4  inc     r15d
0x140063cf7  mov     r8, rbx
0x140063cfa  jmp     short loc_140063CCB
0x140063cfc  mov     ecx, r15d
0x140063cff  xor     r9d, r9d; unsigned int
0x140063d02  shl     rcx, 3; unsigned __int64
0x140063d06  xor     r8d, r8d; unsigned __int8
0x140063d09  mov     edx, 58587053h; unsigned int
0x140063d0e  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x140063d13  mov     r13, rax
0x140063d16  test    rax, rax
0x140063d19  jnz     short loc_140063D25
0x140063d1b  mov     esi, 0C000009Ah
0x140063d20  jmp     loc_14006416B
0x140063d25  xor     r8d, r8d
0x140063d28  mov     [rbp+57h+arg_18], r12d
0x140063d2c  mov     dl, 2
0x140063d2e  mov     [rbp+57h+var_D0], r12
0x140063d32  mov     rcx, r14
0x140063d35  mov     [rbp+57h+arg_10], r12d
0x140063d39  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x140063d3e  mov     rbx, rax
0x140063d41  test    rax, rax
0x140063d44  jz      short loc_140063DB5
0x140063d46  mov     rdi, r12
0x140063d49  movzx   ecx, word ptr [rbx+1Eh]
0x140063d4d  lea     rdx, [rbp+57h+var_B0]; unsigned __int64 *
0x140063d51  and     ecx, 1
0x140063d54  mov     r15, [rbx+rcx*8+20h]
0x140063d59  mov     rcx, [r15+0C0h]; this
0x140063d60  call    ?FindLastObject@SC_SPARSE@@QEAAPEAXPEA_K@Z; SC_SPARSE::FindLastObject(unsigned __int64 *)
0x140063d65  mov     ecx, r12d
0x140063d68  mov     [r13+rcx*8+0], rax
0x140063d6d  test    rax, rax
0x140063d70  jz      short loc_140063D97
0x140063d72  movzx   ecx, word ptr [rax+1Eh]
0x140063d76  inc     r12d
0x140063d79  and     ecx, 1
0x140063d7c  mov     rdx, [rax+rcx*8+20h]
0x140063d81  mov     rcx, [r15+118h]
0x140063d88  sub     rcx, [rdx+30h]
0x140063d8c  sub     rcx, [rdx+20h]
0x140063d90  cmp     rcx, rdi
0x140063d93  cmova   rdi, rcx
0x140063d97  mov     r8, rbx
0x140063d9a  mov     dl, 2
0x140063d9c  mov     rcx, r14
0x140063d9f  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x140063da4  mov     rbx, rax
0x140063da7  test    rax, rax
0x140063daa  jnz     short loc_140063D49
0x140063dac  mov     [rbp+57h+var_D0], rdi
0x140063db0  mov     rdi, [rsp+110h+var_E0]
0x140063db5  mov     qword ptr [rdi+110h], 0
0x140063dc0  mov     qword ptr [rdi+120h], 0
0x140063dcb  mov     r15d, 1
0x140063dd1  test    r12d, r12d
0x140063dd4  jz      loc_14006411C
0x140063dda  xor     r15d, r15d
0x140063ddd  mov     [rbp+57h+var_C8], 0FFFFFFFFFFFFFFFFh
0x140063de5  test    r12d, r12d
0x140063de8  jz      loc_140063E75
0x140063dee  mov     rdi, [rbp+57h+var_C8]
0x140063df2  mov     esi, [rbp+57h+arg_10]
0x140063df5  mov     rcx, [r13+r15*8+0]
0x140063dfa  mov     dl, 2
0x140063dfc  movzx   eax, word ptr [rcx+1Eh]
0x140063e00  and     eax, 1
0x140063e03  mov     rbx, [rcx+rax*8+20h]
0x140063e08  mov     rcx, [rbx+10h]
0x140063e0c  mov     r8d, [rbx+3Ch]
0x140063e10  mov     rcx, [rcx+10h]
0x140063e14  call    ?FindRecordByRecordId@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@K@Z; SDB_POOL_CONFIG::FindRecordByRecordId(_SDB_RECORD_TYPE,ulong)
0x140063e19  movzx   ecx, word ptr [rax+1Eh]
0x140063e1d  and     ecx, 1
0x140063e20  mov     rax, [rax+rcx*8+20h]
0x140063e25  mov     rdx, [rax+118h]
0x140063e2c  sub     rdx, [rbx+30h]
0x140063e30  cmp     rdx, rdi
0x140063e33  jnb     short loc_140063E44
0x140063e35  mov     rdi, rdx
0x140063e38  mov     [rbp+57h+arg_18], 1
0x140063e3f  mov     esi, r15d
0x140063e42  jmp     short loc_140063E5E
0x140063e44  jnz     short loc_140063E5E
0x140063e46  mov     ebx, [rbp+57h+arg_18]
0x140063e49  mov     rcx, r14; this
0x140063e4c  inc     ebx
0x140063e4e  mov     edx, ebx; unsigned int
0x140063e50  mov     [rbp+57h+arg_18], ebx
0x140063e53  call    ?GetRandom@SDB_POOL_CONFIG@@IEAAKK@Z; SDB_POOL_CONFIG::GetRandom(ulong)
0x140063e58  test    eax, eax
0x140063e5a  cmovz   esi, r15d
0x140063e5e  inc     r15d
0x140063e61  cmp     r15d, r12d
0x140063e64  jb      short loc_140063DF5
0x140063e66  mov     [rbp+57h+arg_10], esi
0x140063e69  mov     esi, [rbp+57h+arg_0]
0x140063e6c  mov     [rbp+57h+var_C8], rdi
0x140063e70  mov     rdi, [rsp+110h+var_E0]
0x140063e75  mov     eax, [rbp+57h+arg_10]
0x140063e78  mov     dl, 2
0x140063e7a  lea     rax, ds:0[rax*8]
0x140063e82  add     rax, r13
0x140063e85  mov     [rsp+110h+var_D8], rax
0x140063e8a  mov     rcx, [rax]
0x140063e8d  movzx   eax, word ptr [rcx+1Eh]
0x140063e91  and     eax, 1
0x140063e94  mov     rbx, [rcx+rax*8+20h]
0x140063e99  mov     rcx, [rbx+10h]
0x140063e9d  mov     r8d, [rbx+3Ch]
0x140063ea1  mov     rcx, [rcx+10h]
0x140063ea5  call    ?FindRecordByRecordId@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@K@Z; SDB_POOL_CONFIG::FindRecordByRecordId(_SDB_RECORD_TYPE,ulong)
0x140063eaa  mov     r15, [rbx+30h]
0x140063eae  movzx   ecx, word ptr [rax+1Eh]
0x140063eb2  and     ecx, 1
0x140063eb5  mov     rdx, [rax+rcx*8+20h]
0x140063eba  mov     [rbp+57h+var_B8], rdx
0x140063ebe  mov     ecx, [rdx+0DCh]
0x140063ec4  shr     r15, cl
0x140063ec7  xor     ecx, ecx
0x140063ec9  mov     [rbp+57h+var_C0], rcx
0x140063ecd  lea     rax, [r15-1]
0x140063ed1  test    rax, rax
0x140063ed4  js      short loc_140063F3B
0x140063ed6  mov     rax, [rdx+0C0h]
0x140063edd  mov     rdx, r15; unsigned __int64
0x140063ee0  mov     rcx, rax; this
0x140063ee3  mov     [rbp+57h+var_B0], rax
0x140063ee7  call    ?GetArray@SC_SPARSE@@AEAAPEAVSC_ARRAY@@_K@Z; SC_SPARSE::GetArray(unsigned __int64)
0x140063eec  mov     rcx, rax
0x140063eef  test    rax, rax
0x140063ef2  jz      short loc_140063F37
0x140063ef4  mov     rdx, [rbp+57h+var_B0]
0x140063ef8  lea     r8, [rdx+8]
0x140063efc  cmp     rax, r8
0x140063eff  jz      short loc_140063F37
0x140063f01  sub     r15, [rax+10h]
0x140063f05  dec     r15
0x140063f08  test    r15, r15
0x140063f0b  js      short loc_140063F21
0x140063f0d  mov     rax, [rcx+r15*8+18h]
0x140063f12  test    rax, rax
0x140063f15  jz      short loc_140063F05
0x140063f17  mov     rdx, [rsp+110h+var_D8]
0x140063f1c  mov     [rdx], rax
0x140063f1f  jmp     short loc_140063F5A
0x140063f21  mov     rcx, [rcx+8]
0x140063f25  cmp     rcx, r8
0x140063f28  jz      short loc_140063F33
0x140063f2a  mov     r15d, [rdx+34h]
0x140063f2e  dec     r15d
0x140063f31  jmp     short loc_140063F08
0x140063f33  xor     ecx, ecx
0x140063f35  jmp     short loc_140063F3B
0x140063f37  mov     rcx, [rbp+57h+var_C0]
0x140063f3b  mov     rdx, [rsp+110h+var_D8]
0x140063f40  dec     r12d
0x140063f43  mov     rax, rdx
0x140063f46  mov     [rdx], rcx
0x140063f49  mov     rax, [r13+r12*8+0]
0x140063f4e  mov     [rdx], rax
0x140063f51  mov     qword ptr [r13+r12*8+0], 0
0x140063f5a  mov     rcx, rbx; this
0x140063f5d  call    ?GetSpace@SDB_EXTENT@@QEAAPEAVSDB_RECORD@@XZ; SDB_EXTENT::GetSpace(void)
0x140063f62  movzx   ecx, word ptr [rax+1Eh]
0x140063f66  and     ecx, 1
0x140063f69  mov     r15, [rax+rcx*8+20h]
0x140063f6e  mov     al, [r15+42h]
0x140063f72  dec     al
0x140063f74  test    al, 0F7h
0x140063f76  jz      loc_140063DCB
0x140063f7c  mov     rcx, rbx; this
0x140063f7f  call    ?SupportsSafeReallocation@SDB_EXTENT@@QEAAEXZ; SDB_EXTENT::SupportsSafeReallocation(void)
0x140063f84  test    al, al
0x140063f86  jz      loc_140063DCB
0x140063f8c  test    byte ptr [rbx+4Ch], 2
0x140063f90  jz      short loc_140063FBC
0x140063f92  mov     rax, [rbx+20h]
0x140063f96  xor     r9d, r9d; unsigned __int8
0x140063f99  add     [rdi+110h], rax
0x140063fa0  mov     rax, [rbx+20h]
0x140063fa4  add     [rdi+120h], rax
0x140063fab  mov     r8, [rbx+20h]; unsigned __int64
0x140063faf  mov     rdx, [rbx+30h]; unsigned __int64
0x140063fb3  mov     rcx, [rbp+57h+var_B8]; this
0x140063fb7  call    ?ChangeSlabBitmap@SDB_DRIVE@@QEAAX_K0E@Z; SDB_DRIVE::ChangeSlabBitmap(unsigned __int64,unsigned __int64,uchar)
0x140063fbc  cmp     dword ptr [rbx+48h], 0FFFFFFFFh
0x140063fc0  jnz     loc_140063DCB
0x140063fc6  movzx   eax, word ptr [rbx+4Eh]
0x140063fca  test    al, 1
0x140063fcc  jz      short loc_140063FDA
0x140063fce  mov     ecx, 0FFFEh
0x140063fd3  and     ax, cx
0x140063fd6  mov     [rbx+4Eh], ax
0x140063fda  test    byte ptr [rbx+4Ch], 8
0x140063fde  jnz     short loc_140063FEE
0x140063fe0  mov     rax, [rbp+57h+var_D0]
0x140063fe4  cmp     [rbp+57h+var_C8], rax
0x140063fe8  ja      loc_140063DCB
0x140063fee  test    byte ptr [rdi+40h], 8
0x140063ff2  jz      loc_140063DCB
0x140063ff8  mov     rax, [rbx+28h]
0x140063ffc  xor     edx, edx
0x140063ffe  div     qword ptr [r15+110h]
0x140064005  mov     rcx, [r15+0E8h]; this
0x14006400c  mov     rdx, rax; unsigned __int64
0x14006400f  call    ?GetObject@SC_SPARSE@@QEAAPEAX_K@Z; SC_SPARSE::GetObject(unsigned __int64)
0x140064014  mov     r8, rax
0x140064017  mov     r15d, 1
0x14006401d  test    r8, r8
0x140064020  jz      short loc_140064043
0x140064022  movzx   ecx, word ptr [r8+1Eh]
0x140064027  and     cx, r15w
0x14006402b  movzx   eax, cx
0x14006402e  mov     rcx, [r8+rax*8+20h]
0x140064033  test    [rcx+4Eh], r15b
0x140064037  jnz     loc_140063DD1
0x14006403d  mov     r8, [rcx+50h]
0x140064041  jmp     short loc_14006401D
0x140064043  lea     rax, [rbp+57h+var_A0]
0x140064047  mov     r9b, r15b; unsigned __int8
0x14006404a  mov     r8b, r15b; unsigned __int8
0x14006404d  mov     [rsp+110h+var_F0], rax; struct SDB_EXTENT *
0x140064052  mov     rdx, rbx; struct SDB_EXTENT *
0x140064055  mov     rcx, r14; this
0x140064058  call    ?PickDrive@SDB_POOL_CONFIG@@QEAAJPEAVSDB_EXTENT@@EE0@Z; SDB_POOL_CONFIG::PickDrive(SDB_EXTENT *,uchar,uchar,SDB_EXTENT *)
0x14006405d  mov     [rbp+57h+arg_0], eax
0x140064060  mov     esi, eax
0x140064062  cmp     eax, 0C0000461h
0x140064067  jz      loc_140064112
0x14006406d  cmp     eax, 0C0000001h
0x140064072  jz      loc_140064112
0x140064078  test    eax, eax
0x14006407a  js      loc_14006416B
0x140064080  mov     rcx, rbx; this
  ... truncated ...
```
