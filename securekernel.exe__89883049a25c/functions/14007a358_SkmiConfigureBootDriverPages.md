# SkmiConfigureBootDriverPages

- ea: `0x14007a358`
- end: `0x14007af80`
- name: `SkmiConfigureBootDriverPages`
- size: `3112`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14005a0f8`

## callees

- `0x140003780`
- `0x140008ec4`
- `0x14000f0f0`
- `0x140011780`
- `0x140013200`
- `0x140025090`
- `0x140026960`
- `0x14002b534`
- `0x14003bee8`
- `0x140046628`
- `0x140050ba4`
- `0x1400765fc`
- `0x140076948`
- `0x1400776b0`
- `0x140079abc`
- `0x140079ee8`
- `0x140079fbc`
- `0x14007a358`
- `0x14007af88`
- `0x14007b060`
- `0x14007b40c`
- `0x14007b814`
- `0x14007c380`
- `0x140081290`
- `0x14008176c`
- `0x1400d64a4`
- `0x1400d64dc`
- `0x1400d7280`
- `0x1400f9780`
- `0x1400f9a80`
- `0x1400fb530`
- `0x1400fecc8`

## pseudocode

```c
__int64 SkmiConfigureBootDriverPages()
{
  __int64 v0; // rcx
  __int64 v1; // rdx
  __int64 v2; // r15
  unsigned __int64 v3; // r12
  unsigned __int64 v4; // r13
  unsigned __int64 v5; // rbx
  __int64 v6; // rsi
  char v7; // al
  int v8; // edx
  unsigned int v9; // r14d
  unsigned int v10; // ebx
  unsigned __int64 v11; // rdi
  __int64 result; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rsi
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // r14
  unsigned __int64 v20; // rdi
  _DWORD *Config; // rax
  __int64 v22; // rdx
  __int64 v23; // rax
  size_t v24; // rdi
  const void *v25; // rsi
  void *Pool; // rbx
  unsigned __int64 v27; // r14
  unsigned __int64 *v28; // rdx
  unsigned __int64 v29; // rax
  __int64 v30; // rcx
  __int64 *v31; // r15
  int v32; // esi
  unsigned __int64 v33; // rdi
  int v34; // eax
  __int64 v35; // r8
  int v36; // r9d
  __int64 v37; // rsi
  unsigned __int64 v38; // rbx
  unsigned __int64 v39; // rbx
  __int64 PteTrace; // rax
  __int64 v41; // r14
  PVOID *v42; // rsi
  PVOID StackBase; // rcx
  __int64 v44; // rdx
  __int64 v45; // rcx
  ULONG v46; // edx
  __int64 v47; // r12
  unsigned __int64 *v48; // r15
  unsigned int v49; // r13d
  __int64 *v50; // rdx
  __int64 v51; // rax
  __int64 v52; // r14
  PVOID *v53; // rsi
  PVOID v54; // rcx
  __int64 v55; // rdx
  __int64 v56; // rcx
  _WORD *v57; // rcx
  unsigned __int64 v58; // rax
  _WORD *v59; // rax
  __int64 v60; // r8
  ULONG_PTR v61; // rdi
  __int64 v62; // rdx
  int v63; // ecx
  __int64 v64; // r8
  __int64 v65; // rbx
  __int64 *v66; // r12
  __int64 v67; // rax
  __int64 v68; // rsi
  PVOID *v69; // rdi
  PVOID v70; // rcx
  __int64 v71; // rdx
  __int64 v72; // rcx
  unsigned int v73; // ebx
  __int64 LoaderAppliedHotPatchEntry; // rax
  unsigned int v75; // ecx
  __int64 v76; // [rsp+40h] [rbp-79h] BYREF
  __int64 v77; // [rsp+48h] [rbp-71h] BYREF
  ULONG BackTraceHash; // [rsp+50h] [rbp-69h] BYREF
  __int64 *v79; // [rsp+58h] [rbp-61h]
  unsigned __int64 v80; // [rsp+60h] [rbp-59h]
  unsigned __int64 v81; // [rsp+68h] [rbp-51h]
  __int64 *v82; // [rsp+70h] [rbp-49h]
  _WORD *v83; // [rsp+78h] [rbp-41h]
  __int64 v84; // [rsp+80h] [rbp-39h]
  ULONG v85[2]; // [rsp+88h] [rbp-31h] BYREF
  unsigned __int64 v86; // [rsp+90h] [rbp-29h]
  __int64 v87; // [rsp+98h] [rbp-21h]
  __int64 v88; // [rsp+A0h] [rbp-19h]
  unsigned __int64 v89; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v90; // [rsp+B0h] [rbp-9h]
  void *v91; // [rsp+C0h] [rbp+7h]
  size_t Size[9]; // [rsp+C8h] [rbp+Fh] BYREF
  _UNKNOWN *retaddr; // [rsp+118h] [rbp+5Fh]
  __int64 v94; // [rsp+120h] [rbp+67h] BYREF
  unsigned int v95; // [rsp+128h] [rbp+6Fh]
  unsigned int v96; // [rsp+130h] [rbp+77h]
  int v97; // [rsp+138h] [rbp+7Fh]

  v76 = 0;
  ExecuteHotpatchTestBootFunction();
  v83 = 0;
  v97 = 0;
  v0 = *(_QWORD *)(SkeLoaderBlock + 48);
  v90 = v0 + 0x8000000010LL;
  v1 = *(_QWORD *)(v0 + 0x80000000F0LL) + 0x8000000000LL;
  v2 = *(_QWORD *)(v0 + 0x8000000010LL) + 0x8000000000LL;
  v88 = v1;
  v87 = v2;
  if ( v2 == v0 + 0x8000000010LL )
  {
LABEL_132:
    if ( (SkmiPatchFlags & 1) == 0 || (result = SkmiBindBootDriverPatches(v1), (int)result >= 0) )
    {
      v75 = 0;
      if ( (SkmiFlags & 0x1000) != 0 )
        return (unsigned int)SkmiProcessDriverReadOnlyData(0);
      return v75;
    }
    return result;
  }
  while ( 1 )
  {
    v3 = *(_QWORD *)(v2 + 48);
    v80 = v3 + 0x8000000000LL;
    v4 = (((v3 + 0x8000000000LL) >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
    v81 = v4;
    v84 = ((v4 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
    v5 = ((v3 >> 9) & 0x7FFFFFFFF8LL) - 0xA0000000000LL;
    v79 = (__int64 *)v5;
    v82 = 0;
    v77 = 0;
    v6 = 0;
    RtlImageNtHeaderEx(1, v3 + 0x8000000000LL, 0, &v77);
    v7 = *(_BYTE *)(((v4 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL);
    v8 = 0;
    v95 = 0;
    if ( v7 < 0 )
    {
      if ( (((unsigned int)SkmiFlags >> 4) & 1) != 0 && (v3 & 0x1FFFFF) != 0 )
        return 3221225496LL;
      v8 = 1;
      v95 = 1;
      if ( (((unsigned int)SkmiFlags >> 4) & 1) != 0 )
      {
        v6 = ((v5 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
        v82 = (__int64 *)v6;
      }
    }
    v9 = ((*(_DWORD *)(v2 + 64) & 0xFFF) != 0) + (*(_DWORD *)(v2 + 64) >> 12);
    v96 = v9;
    if ( v8 )
    {
      v9 = (v9 + 511) & 0xFFFFFE00;
      v96 = v9;
    }
    v10 = SkmiHotPatchAddressReservePages;
    if ( SkmiNtosNar && SkmiHalNar )
    {
      if ( (SkmiDriverProxyReservePages || SkmiKernelScpReservePages) && v8 )
        return 3221225496LL;
      v10 = SkmiKernelScpReservePages + SkmiDriverProxyReservePages + SkmiHotPatchAddressReservePages;
    }
    v11 = (v9 + (unsigned __int64)v10) << 12;
    result = SkmiReserveNar(*(_QWORD *)(v2 + 48), (v9 + v10) << 12, v6 != 0 ? 0x80000 : 0, 1, 0, 0, (__int64)&v76);
    if ( (int)result < 0 )
      return result;
    *(_DWORD *)(v76 + 72) = v9;
    *(_WORD *)(v76 + 78) |= 0x100u;
    if ( v6 )
    {
      *(_WORD *)(v76 + 78) |= 8u;
      result = SkmiExpandSparseMapping(
                 qword_140156AE0 + ((*(_QWORD *)(v76 + 24) >> 20) & 0xFFFFFFELL),
                 qword_140156AE0
               + (((((unsigned __int64)*(unsigned int *)(v76 + 72) << 12) + *(_QWORD *)(v76 + 24) - 1LL) >> 20)
                & 0xFFFFFFE),
                 0,
                 0xFFFFFFFFLL);
      if ( (int)result < 0 )
        return result;
      v83 = (_WORD *)(qword_140156AE0 + ((v3 >> 20) & 0xFFFFFFE));
    }
    v15 = v77;
    if ( SkmiNtosNar )
    {
      if ( !SkmiHalNar )
      {
        SkmiHalNar = v76;
        *(_WORD *)(v76 + 76) = 1;
      }
    }
    else
    {
      v16 = *(_QWORD *)(v2 + 48);
      SkmiNtosNar = v76;
      SkmmNtoskrnlBase = v16;
      *(_WORD *)(v76 + 76) = 1;
      SkmiDriverProxyWrappedEndpointCall = 0;
      v17 = RtlLookupImageSectionByName(v15, "DRVPRX", v13, v14);
      if ( v17 )
        SkmiDriverProxyWrappedEndpointCall = *(unsigned int *)(v17 + 12)
                                           + *(_QWORD *)(SkmiNtosNar + 24)
                                           + *(unsigned int *)(*(unsigned int *)(v17 + 12) + v80);
    }
    if ( !v10 )
      goto LABEL_30;
    result = SkmiReserveAdditionalNtes(v76);
    if ( (int)result < 0 )
      return result;
    if ( (SkmiFlags & 0x10) != 0 )
      goto LABEL_30;
    v18 = v76;
    if ( v76 != SkmiNtosNar && v76 != SkmiHalNar )
    {
      SkmiSetKernelScpNte();
LABEL_30:
      v18 = v76;
    }
    v19 = *(unsigned int *)(v2 + 64);
    if ( (_DWORD)v19 != *(_DWORD *)(v15 + 80) )
      return 3221225595LL;
    if ( (SkmiFlags & 0x10) != 0 )
    {
      result = SkmiAdjustBootDriverPtes(v15, v4, v11, v95);
      if ( (int)result < 0 )
        return result;
      v18 = v76;
    }
    result = SkmiCaptureDriverIdentity(
               v18 + 80,
               v15,
               *(unsigned int *)(v2 + 216),
               *(unsigned int *)(v2 + 228),
               *(_QWORD *)(v2 + 192) + 0x8000000000LL);
    if ( (int)result < 0 )
      return result;
    v20 = v80;
    *(_WORD *)(v76 + 78) |= 0x10u;
    *(_QWORD *)(v76 + 80) = v76;
    **(_QWORD **)(v76 + 192) = v76;
    *(_QWORD *)(*(_QWORD *)(v76 + 192) + 40LL) = 0;
    *(_DWORD *)(*(_QWORD *)(v76 + 192) + 48LL) = 0;
    result = SkmiCaptureLoadConfig(v20, *(_QWORD *)(v2 + 48), v15, v76);
    if ( (int)result < 0 )
      return result;
    Config = (_DWORD *)LdrImageDirectoryEntryToLoadConfig(v20);
    if ( Config && *Config >= 0x94u && (Config[36] & 0x100000) != 0 )
      *(_WORD *)(v76 + 78) |= 0x2000u;
    if ( (SkmiFlags & 0x10) != 0 && *(_QWORD *)(v76 + 200) )
    {
      LODWORD(Size[0]) = 0;
      v91 = 0;
      v23 = RtlImageDirectoryEntryToData(v20, v22, 12, Size);
      v24 = LODWORD(Size[0]);
      v25 = (const void *)v23;
      if ( v23 && SLODWORD(Size[0]) > 0 )
        Pool = (void *)SkAllocatePool(512, LODWORD(Size[0]));
      else
        Pool = v91;
      if ( Pool )
      {
        memmove(Pool, v25, v24);
        *(_QWORD *)(*(_QWORD *)(v76 + 200) + 64LL) = Pool;
        *(_DWORD *)(*(_QWORD *)(v76 + 200) + 48LL) = v24;
        *(_QWORD *)(*(_QWORD *)(v76 + 200) + 72LL) = v3;
      }
      v15 = v77;
      v20 = v80;
      if ( SkmiNtosNar && _bittest16((const signed __int16 *)(SkmiNtosNar + 78), 0xDu) )
        *(_DWORD *)(*(_QWORD *)(v76 + 200) + 88LL) = (v96 << 12)
                                                   + (*(_DWORD *)(v76 + 136) << 12)
                                                   + (*(_DWORD *)(*(_QWORD *)(v76 + 192) + 52LL) << 12);
    }
    if ( (SkmiFlags & 0x10) != 0 )
    {
      if ( SkmiDriverProxyReservePages )
      {
        result = SkmiCopyDriverProxyEndpointInfoFromNtHeader(
                   v15,
                   v20,
                   *(_QWORD *)(v76 + 192) + 32LL,
                   *(_QWORD *)(v76 + 192) + 60LL);
        if ( (int)result < 0 )
          return result;
      }
    }
    v27 = (((v20 + v19 - 1) >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
    v86 = v27;
    if ( v4 <= v27 )
    {
      v28 = (unsigned __int64 *)v84;
      while ( 1 )
      {
        v29 = *v28;
        v30 = *v28 & 0x80;
        if ( v95 )
        {
          if ( !v30 )
            return 3221225496LL;
          v31 = v82;
          LODWORD(v94) = 1;
          v32 = 1;
          v33 = ((v29 >> 12) & 0xFFFFFFFFFFLL) + (((__int64)v4 >> 3) & 0x1FF);
          if ( v82 )
          {
            v34 = SKMI_GET_PROTECTION_FROM_VALID_PTE(v28, v28, 0xFFFFFFFFFFLL);
            v97 = v34;
            if ( (v34 & 2) != 0 )
            {
              v37 = SkmiProtectionToPte[v34];
              result = SkmiRegisterBootSlab(v33, (unsigned int)(v36 + 1));
              if ( (int)result < 0 )
                return result;
              LODWORD(v94) = 5;
              v38 = (v33 << 12) ^ (v37 ^ (v33 << 12)) & 0xFFF0000000000FFFuLL;
            }
            else
            {
              v38 = ((v35 & v33) << 12) | 0x921;
            }
            v39 = v38 | 0x280;
            PteTrace = SkmiGetPteTrace(0, (_DWORD)v31, 0, v39, *v31);
            v41 = PteTrace;
            if ( PteTrace )
            {
              v42 = (PVOID *)(PteTrace + 32);
              memset_0((void *)(PteTrace + 32), 0, 0x40u);
              if ( (SkmiFlags & 0x400000) != 0 )
              {
                StackBase = KeGetPcr()->NtTib.StackBase;
                if ( StackBase )
                {
                  if ( !RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v42, &BackTraceHash) )
                  {
                    *(_QWORD *)(v41 + 40) = retaddr;
                    *v42 = (PVOID)SkmiGetInstructionPointer(v45, v44);
                  }
                }
              }
            }
            v32 = v94;
            v27 = v86;
            *v31 = v39;
            v82 = v31 + 1;
          }
          else
          {
            v39 = ((v33 & 0xFFFFFFFFFFLL) << 12) | 0xB21;
          }
          v46 = v97 & 2;
          BackTraceHash = v46;
          v47 = (v46 != 0) + 1LL;
          if ( v33 > 0xFFFFFFFFFFLL )
            __fastfail(0x3Fu);
          v48 = (unsigned __int64 *)(8 * v33 - 0x180000000000LL);
          if ( v4 <= v27 )
          {
            v49 = v32 | 0x8000;
            while ( 1 )
            {
              v89 = v33;
              if ( !(unsigned int)SkmiClaimPhysicalPages((ULONG_PTR)&v89, 1, v49) )
                return 3221225496LL;
              if ( v32 == 5 )
                *v48 = *v48 & 0xFFE3FFFFFFFFFFFFuLL | (v47 << 50);
              v50 = v79;
              if ( !v82 )
              {
                v51 = SkmiGetPteTrace(0, (_DWORD)v79, 0, v39, *v79);
                v52 = v51;
                if ( v51 )
                {
                  v53 = (PVOID *)(v51 + 32);
                  memset_0((void *)(v51 + 32), 0, 0x40u);
                  if ( (SkmiFlags & 0x400000) != 0 )
                  {
                    v54 = KeGetPcr()->NtTib.StackBase;
                    if ( v54 )
                    {
                      if ( !RtlCaptureStackBackTrace((ULONG)v54, 8u, v53, v85) )
                      {
                        *(_QWORD *)(v52 + 40) = retaddr;
                        *v53 = (PVOID)SkmiGetInstructionPointer(v56, v55);
                      }
                    }
                  }
                  v32 = v94;
                }
                v50 = v79;
                v27 = v86;
                *v79 = v39;
                v39 = (v39 + 4096) ^ ((v39 + 4096) ^ v39) & 0xFFF0000000000FFFuLL;
              }
              v57 = v83;
              if ( v83 )
                ++*v83;
              v58 = v81 + 8;
              v81 = v58;
              v79 = v50 + 1;
              if ( (v58 & 0xFF8) != 0 )
              {
                ++v33;
                ++v48;
                if ( v58 <= v27 )
                  continue;
              }
              v46 = BackTraceHash;
              v4 = v58;
              goto LABEL_91;
            }
          }
          v57 = v83;
LABEL_91:
          v59 = v57 + 1;
          if ( !v57 )
            v59 = 0;
          v83 = v59;
          if ( (SkmiFlags & 0x10) != 0 )
          {
            if ( v46 )
            {
              v94 = 512;
              *(_QWORD *)v85 = (v39 >> 12) & 0xFFFFFFFFFFLL;
              result = ShvlpProtectPages(v85, &v94, 13, 1);
              if ( (int)result < 0 )
                return result;
            }
          }
          v2 = v87;
          v28 = (unsigned __int64 *)(v84 + 8);
          v84 += 8;
        }
        else
        {
          if ( v30 )
            return 3221225496LL;
          if ( (*(_QWORD *)v4 & 1) != 0 )
          {
            v60 = *(_QWORD *)v4 >> 12;
            v61 = v60 & 0xFFFFFFFFFFLL;
            v63 = SKMI_GET_PROTECTION_FROM_VALID_PTE(v4, v28, v60);
            v97 = v63;
            if ( (SkmiFlags & 0x10) != 0 && (v63 & 2) != 0 )
            {
              v65 = (v64 << 12) ^ (SkmiProtectionToPte[v63] ^ (v64 << 12)) & 0xFFF0000000000FFFuLL | 0x200;
              if ( (*(_DWORD *)(v2 + 104) & 0x800000) != 0 && (unsigned int)SkmiRelocateBootPage(v4, v62, 2) )
              {
                v65 = *(_QWORD *)v4 ^ (*(_QWORD *)v4 ^ v65) & 0xFFF0000000000FFFuLL;
              }
              else
              {
                v94 = v61;
                if ( !(unsigned int)SkmiClaimPhysicalPages((ULONG_PTR)&v94, 1, 0x48005u) )
                  return 3221225496LL;
                result = SkmiProtectSinglePage(v61);
                if ( (int)result < 0 )
                  return result;
              }
            }
            else
            {
              v94 = v61;
              if ( !(unsigned int)SkmiClaimPhysicalPages((ULONG_PTR)&v94, 1, 0x8001u) )
                return 3221225496LL;
              v65 = (v61 << 12) | 0xB21;
            }
          }
          else
          {
            v65 = (-(__int64)((SkmiFlags & 0x10) != 0) & 0x3FFFFFFFFFFFF5DFLL) + 2593;
          }
          v66 = v79;
          v67 = SkmiGetPteTrace(0, (_DWORD)v79, 0, v65, *v79);
          v68 = v67;
          if ( v67 )
          {
            v69 = (PVOID *)(v67 + 32);
            memset_0((void *)(v67 + 32), 0, 0x40u);
            if ( (SkmiFlags & 0x400000) != 0 )
            {
              v70 = KeGetPcr()->NtTib.StackBase;
              if ( v70 )
              {
                if ( !RtlCaptureStackBackTrace((ULONG)v70, 8u, v69, (PULONG)&v94) )
                {
                  *(_QWORD *)(v68 + 40) = retaddr;
                  *v69 = (PVOID)SkmiGetInstructionPointer(v72, v71);
                }
              }
            }
          }
          v28 = (unsigned __int64 *)v84;
          *v66 = v65;
          v4 += 8LL;
          v81 = v4;
          v79 = v66 + 1;
        }
        if ( v4 > v27 )
        {
          v20 = v80;
          break;
        }
      }
    }
    if ( (SkmiFlags & 0x10) != 0 )
      ++HIDWORD(qword_14014C6B8);
    v73 = v96;
    if ( v95 )
      v73 = (v96 + 511) & 0xFFFFFE00;
    if ( (SkmiPatchFlags & 1) != 0 )
    {
      LoaderAppliedHotPatchEntry = SkmiFindLoaderAppliedHotPatchEntry(v2, v88, 0);
      result = SkmiConfigureNormalBootDriverHpatPages(v2, v73, LoaderAppliedHotPatchEntry);
      if ( (int)result < 0 )
        return result;
      if ( v76 == SkmiNtosNar )
      {
LABEL_128:
        result = SkmiCaptureKernelScpData(v76, v20, v77);
        if ( (int)result < 0 )
          return result;
        *(_DWORD *)(*(_QWORD *)(v76 + 200) + 88LL) = SkmiNtKernelScpVa - v20;
        goto LABEL_130;
      }
      if ( v76 != SkmiHalNar )
      {
        result = SkmiConfigureNormalBootDriverProxyPages(v2, v73);
        if ( (int)result < 0 )
          return result;
      }
    }
    if ( v76 == SkmiNtosNar )
      goto LABEL_128;
LABEL_130:
    v2 = *(_QWORD *)v2 + 0x8000000000LL;
    v87 = v2;
    if ( v2 == v90 )
    {
      v1 = v88;
      goto LABEL_132;
    }
  }
}

```

## disassembly

```asm
0x14007a358  push    rbp
0x14007a35a  push    rbx
0x14007a35b  push    rsi
0x14007a35c  push    rdi
0x14007a35d  push    r12
0x14007a35f  push    r13
0x14007a361  push    r14
0x14007a363  push    r15
0x14007a365  lea     rbp, [rsp-1Fh]
0x14007a36a  sub     rsp, 0D8h
0x14007a371  xor     r12d, r12d
0x14007a374  mov     [rbp+57h+var_D0], r12
0x14007a378  call    ExecuteHotpatchTestBootFunction
0x14007a37d  mov     rax, cs:SkeLoaderBlock
0x14007a384  lea     r14d, [r12+1]
0x14007a389  mov     r8, 8000000000h
0x14007a393  mov     [rbp+57h+var_98], r12
0x14007a397  mov     rdx, 80000000F0h
0x14007a3a1  mov     [rbp+57h+arg_18], r12d
0x14007a3a5  mov     rcx, [rax+30h]
0x14007a3a9  mov     rax, 8000000010h
0x14007a3b3  add     rax, rcx
0x14007a3b6  mov     [rbp+57h+var_60], rax
0x14007a3ba  mov     rdx, [rcx+rdx]
0x14007a3be  mov     r15, [rax]
0x14007a3c1  add     rdx, r8
0x14007a3c4  add     r15, r8
0x14007a3c7  mov     [rbp+57h+var_70], rdx
0x14007a3cb  mov     [rbp+57h+var_78], r15
0x14007a3cf  cmp     r15, rax
0x14007a3d2  jz      loc_14007AF27
0x14007a3d8  mov     r12, [r15+30h]
0x14007a3dc  mov     r9, 7FFFFFFFF8h
0x14007a3e6  mov     r10, 0FFFFF68000000000h
0x14007a3f0  lea     rdx, [r12+r8]
0x14007a3f4  mov     r13, rdx
0x14007a3f7  mov     [rbp+57h+var_B0], rdx
0x14007a3fb  shr     r13, 9
0x14007a3ff  and     r13, r9
0x14007a402  mov     rax, r10
0x14007a405  add     r13, rax
0x14007a408  mov     rdi, r13
0x14007a40b  mov     [rbp+57h+var_A8], r13
0x14007a40f  shr     rdi, 9
0x14007a413  and     rdi, r9
0x14007a416  mov     rax, r10
0x14007a419  mov     rbx, r12
0x14007a41c  add     rdi, rax
0x14007a41f  shr     rbx, 9
0x14007a423  and     rbx, r9
0x14007a426  mov     [rbp+57h+var_90], rdi
0x14007a42a  mov     rax, 0FFFFF60000000000h
0x14007a434  add     rbx, rax
0x14007a437  lea     r9, [rbp+57h+var_C8]
0x14007a43b  xor     eax, eax
0x14007a43d  mov     [rbp+57h+var_B8], rbx
0x14007a441  xor     r8d, r8d
0x14007a444  mov     [rbp+57h+var_A0], rax
0x14007a448  mov     ecx, r14d
0x14007a44b  mov     [rbp+57h+var_C8], rax
0x14007a44f  mov     esi, eax
0x14007a451  call    RtlImageNtHeaderEx
0x14007a456  mov     al, [rdi]
0x14007a458  xor     r9d, r9d
0x14007a45b  mov     edx, r9d
0x14007a45e  mov     [rbp+57h+arg_8], edx
0x14007a461  test    al, al
0x14007a463  jns     short loc_14007A4B2
0x14007a465  mov     eax, cs:SkmiFlags
0x14007a46b  shr     eax, 4
0x14007a46e  and     eax, r14d
0x14007a471  jz      short loc_14007A480
0x14007a473  test    r12, 1FFFFFh
0x14007a47a  jnz     loc_14007AF72
0x14007a480  mov     edx, r14d
0x14007a483  mov     [rbp+57h+arg_8], edx
0x14007a486  test    eax, eax
0x14007a488  jz      short loc_14007A4B2
0x14007a48a  mov     rax, 7FFFFFFFF8h
0x14007a494  mov     rsi, rbx
0x14007a497  shr     rsi, 9
0x14007a49b  and     rsi, rax
0x14007a49e  mov     rax, 0FFFFF68000000000h
0x14007a4a8  mov     rax, rax
0x14007a4ab  add     rsi, rax
0x14007a4ae  mov     [rbp+57h+var_A0], rsi
0x14007a4b2  mov     ecx, [r15+40h]
0x14007a4b6  mov     eax, r9d
0x14007a4b9  test    ecx, 0FFFh
0x14007a4bf  setnz   al
0x14007a4c2  shr     ecx, 0Ch
0x14007a4c5  lea     r14d, [rax+rcx]
0x14007a4c9  mov     [rbp+57h+arg_10], r14d
0x14007a4cd  test    edx, edx
0x14007a4cf  jz      short loc_14007A4E3
0x14007a4d1  add     r14d, 1FFh
0x14007a4d8  and     r14d, 0FFFFFE00h
0x14007a4df  mov     [rbp+57h+arg_10], r14d
0x14007a4e3  cmp     cs:SkmiNtosNar, r9
0x14007a4ea  mov     ebx, cs:SkmiHotPatchAddressReservePages
0x14007a4f0  jz      short loc_14007A51E
0x14007a4f2  cmp     cs:SkmiHalNar, r9
0x14007a4f9  jz      short loc_14007A51E
0x14007a4fb  mov     ecx, cs:SkmiDriverProxyReservePages
0x14007a501  test    ecx, ecx
0x14007a503  jnz     short loc_14007A50E
0x14007a505  cmp     cs:SkmiKernelScpReservePages, r9d
0x14007a50c  jz      short loc_14007A516
0x14007a50e  test    edx, edx
0x14007a510  jnz     loc_14007AF72
0x14007a516  add     ecx, cs:SkmiKernelScpReservePages
0x14007a51c  add     ebx, ecx
0x14007a51e  mov     rcx, [r15+30h]; int
0x14007a522  mov     eax, r14d
0x14007a525  mov     edi, ebx
0x14007a527  add     rdi, rax
0x14007a52a  mov     rax, rsi
0x14007a52d  shl     rdi, 0Ch
0x14007a531  neg     rax
0x14007a534  mov     rdx, rdi; int
0x14007a537  lea     rax, [rbp+57h+var_D0]
0x14007a53b  mov     [rsp+110h+var_E0], rax; __int64
0x14007a540  sbb     r8d, r8d
0x14007a543  mov     qword ptr [rsp+110h+var_E8], r9; BackTraceHash
0x14007a548  and     r8d, 80000h; int
0x14007a54f  mov     [rsp+110h+var_F0], r9; __int64
0x14007a554  mov     r9d, 1; int
0x14007a55a  call    SkmiReserveNar
0x14007a55f  test    eax, eax
0x14007a561  js      loc_14007AF56
0x14007a567  mov     rax, [rbp+57h+var_D0]
0x14007a56b  mov     ecx, 100h
0x14007a570  mov     [rax+48h], r14d
0x14007a574  xor     r14d, r14d
0x14007a577  mov     rax, [rbp+57h+var_D0]
0x14007a57b  or      [rax+4Eh], cx
0x14007a57f  test    rsi, rsi
0x14007a582  jz      short loc_14007A5F0
0x14007a584  mov     rax, [rbp+57h+var_D0]
0x14007a588  lea     ecx, [r14+8]
0x14007a58c  mov     esi, 0FFFFFFEh
0x14007a591  or      r9d, 0FFFFFFFFh
0x14007a595  xor     r8d, r8d
0x14007a598  or      [rax+4Eh], cx
0x14007a59c  mov     rax, [rbp+57h+var_D0]
0x14007a5a0  mov     r10, [rax+18h]
0x14007a5a4  mov     ecx, [rax+48h]
0x14007a5a7  mov     rax, cs:qword_140156AE0
0x14007a5ae  shl     rcx, 0Ch
0x14007a5b2  lea     rdx, [r10-1]
0x14007a5b6  shr     r10, 14h
0x14007a5ba  add     rdx, rcx
0x14007a5bd  and     r10, rsi
0x14007a5c0  shr     rdx, 14h
0x14007a5c4  and     rdx, rsi
0x14007a5c7  add     rdx, rax
0x14007a5ca  lea     rcx, [rax+r10]
0x14007a5ce  call    SkmiExpandSparseMapping
0x14007a5d3  test    eax, eax
0x14007a5d5  js      loc_14007AF56
0x14007a5db  mov     rax, r12
0x14007a5de  shr     rax, 14h
0x14007a5e2  and     rax, rsi
0x14007a5e5  add     rax, cs:qword_140156AE0
0x14007a5ec  mov     [rbp+57h+var_98], rax
0x14007a5f0  cmp     cs:SkmiNtosNar, r14
0x14007a5f7  mov     rsi, [rbp+57h+var_C8]
0x14007a5fb  jnz     short loc_14007A655
0x14007a5fd  mov     rcx, [rbp+57h+var_D0]
0x14007a601  lea     rdx, aDrvprx; "DRVPRX"
0x14007a608  mov     rax, [r15+30h]
0x14007a60c  mov     cs:SkmiNtosNar, rcx
0x14007a613  mov     cs:SkmmNtoskrnlBase, rax
0x14007a61a  mov     word ptr [rcx+4Ch], 1
0x14007a620  mov     rcx, rsi
0x14007a623  mov     cs:SkmiDriverProxyWrappedEndpointCall, r14
0x14007a62a  call    RtlLookupImageSectionByName
0x14007a62f  test    rax, rax
0x14007a632  jz      short loc_14007A66F
0x14007a634  mov     ecx, [rax+0Ch]
0x14007a637  mov     rax, [rbp+57h+var_B0]
0x14007a63b  mov     edx, [rcx+rax]
0x14007a63e  mov     rax, cs:SkmiNtosNar
0x14007a645  add     rdx, [rax+18h]
0x14007a649  add     rdx, rcx
0x14007a64c  mov     cs:SkmiDriverProxyWrappedEndpointCall, rdx
0x14007a653  jmp     short loc_14007A66F
0x14007a655  cmp     cs:SkmiHalNar, r14
0x14007a65c  jnz     short loc_14007A66F
0x14007a65e  mov     rax, [rbp+57h+var_D0]
0x14007a662  mov     cs:SkmiHalNar, rax
0x14007a669  mov     word ptr [rax+4Ch], 1
0x14007a66f  test    ebx, ebx
0x14007a671  jz      short loc_14007A6AD
0x14007a673  mov     rcx, [rbp+57h+var_D0]
0x14007a677  call    SkmiReserveAdditionalNtes
0x14007a67c  xor     ebx, ebx
0x14007a67e  test    eax, eax
0x14007a680  js      loc_14007AF56
0x14007a686  mov     eax, cs:SkmiFlags
0x14007a68c  test    al, 10h
0x14007a68e  jnz     short loc_14007A6AF
0x14007a690  mov     rcx, [rbp+57h+var_D0]
0x14007a694  cmp     rcx, cs:SkmiNtosNar
0x14007a69b  jz      short loc_14007A6B3
0x14007a69d  cmp     rcx, cs:SkmiHalNar
0x14007a6a4  jz      short loc_14007A6B3
0x14007a6a6  call    SkmiSetKernelScpNte
0x14007a6ab  jmp     short loc_14007A6AF
0x14007a6ad  xor     ebx, ebx
0x14007a6af  mov     rcx, [rbp+57h+var_D0]
0x14007a6b3  mov     r14d, [r15+40h]
0x14007a6b7  cmp     r14d, [rsi+50h]
0x14007a6bb  jnz     loc_14007AF79
0x14007a6c1  mov     eax, cs:SkmiFlags
0x14007a6c7  test    al, 10h
0x14007a6c9  jz      short loc_14007A6E9
0x14007a6cb  mov     r9d, [rbp+57h+arg_8]
0x14007a6cf  mov     r8, rdi
0x14007a6d2  mov     rdx, r13
0x14007a6d5  mov     rcx, rsi
0x14007a6d8  call    SkmiAdjustBootDriverPtes
0x14007a6dd  test    eax, eax
0x14007a6df  js      loc_14007AF56
0x14007a6e5  mov     rcx, [rbp+57h+var_D0]
0x14007a6e9  mov     rax, [r15+0C0h]
0x14007a6f0  mov     rdx, 8000000000h
0x14007a6fa  mov     r9d, [r15+0E4h]
0x14007a701  add     rax, rdx
0x14007a704  mov     r8d, [r15+0D8h]
0x14007a70b  mov     rdx, rsi
0x14007a70e  add     rcx, 50h ; 'P'
0x14007a712  mov     [rsp+110h+var_F0], rax
0x14007a717  call    SkmiCaptureDriverIdentity
0x14007a71c  test    eax, eax
0x14007a71e  js      loc_14007AF56
0x14007a724  mov     rax, [rbp+57h+var_D0]
0x14007a728  mov     r8, rsi
0x14007a72b  mov     rdi, [rbp+57h+var_B0]
0x14007a72f  or      word ptr [rax+4Eh], 10h
0x14007a734  mov     rax, [rbp+57h+var_D0]
0x14007a738  mov     [rax+50h], rax
0x14007a73c  mov     rcx, [rbp+57h+var_D0]
0x14007a740  mov     rax, [rcx+0C0h]
0x14007a747  mov     [rax], rcx
0x14007a74a  mov     rax, [rbp+57h+var_D0]
0x14007a74e  mov     rcx, [rax+0C0h]
0x14007a755  mov     [rcx+28h], rbx
0x14007a759  mov     rax, [rbp+57h+var_D0]
0x14007a75d  mov     rcx, [rax+0C0h]
0x14007a764  mov     [rcx+30h], ebx
0x14007a767  mov     rcx, rdi
0x14007a76a  mov     r9, [rbp+57h+var_D0]
0x14007a76e  mov     rdx, [r15+30h]
0x14007a772  call    SkmiCaptureLoadConfig
0x14007a777  test    eax, eax
0x14007a779  js      loc_14007AF56
0x14007a77f  mov     rcx, rdi
0x14007a782  call    LdrImageDirectoryEntryToLoadConfig
0x14007a787  test    rax, rax
0x14007a78a  jz      short loc_14007A7AD
0x14007a78c  cmp     dword ptr [rax], 94h
0x14007a792  jb      short loc_14007A7AD
0x14007a794  test    dword ptr [rax+90h], 100000h
0x14007a79e  jz      short loc_14007A7AD
0x14007a7a0  mov     rax, [rbp+57h+var_D0]
0x14007a7a4  mov     ecx, 2000h
0x14007a7a9  or      [rax+4Eh], cx
0x14007a7ad  mov     eax, cs:SkmiFlags
0x14007a7b3  test    al, 10h
0x14007a7b5  jz      loc_14007A89D
0x14007a7bb  mov     rax, [rbp+57h+var_D0]
0x14007a7bf  cmp     [rax+0C8h], rbx
0x14007a7c6  jz      loc_14007A89D
0x14007a7cc  mov     r8d, 0Ch
0x14007a7d2  mov     dword ptr [rbp+57h+Size], ebx
0x14007a7d5  lea     r9, [rbp+57h+Size]
0x14007a7d9  mov     [rbp+57h+var_50], rbx
0x14007a7dd  mov     rcx, rdi
0x14007a7e0  call    RtlImageDirectoryEntryToData
0x14007a7e5  mov     edi, dword ptr [rbp+57h+Size]
0x14007a7e8  mov     rsi, rax
0x14007a7eb  test    rax, rax
0x14007a7ee  jz      short loc_14007A80B
0x14007a7f0  test    edi, edi
0x14007a7f2  jle     short loc_14007A80B
0x14007a7f4  mov     edx, edi
0x14007a7f6  mov     ecx, 200h
0x14007a7fb  mov     r8d, 434C6D4Dh
0x14007a801  call    SkAllocatePool
0x14007a806  mov     rbx, rax
0x14007a809  jmp     short loc_14007A80F
0x14007a80b  mov     rbx, [rbp+57h+var_50]
0x14007a80f  test    rbx, rbx
0x14007a812  jz      short loc_14007A84E
0x14007a814  mov     r8, rdi; Size
0x14007a817  mov     rdx, rsi; Src
0x14007a81a  mov     rcx, rbx; void *
0x14007a81d  call    memmove
0x14007a822  mov     rax, [rbp+57h+var_D0]
  ... truncated ...
```
