# BaseSrvSxsCreateActivationContextFromStructEx

- ea: `0x180003170`
- end: `0x180003e63`
- name: `BaseSrvSxsCreateActivationContextFromStructEx`
- size: `3315`
- prototype: `__int64 __fastcall(HANDLE SourceProcessHandle, void *, unsigned int *, union _LARGE_INTEGER, HANDLE *)`
- caller_count: `3`
- callee_count: `16`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001440`
- `0x180001d80`
- `0x1800048a0`

## callees

- `0x180001110`
- `0x180003170`
- `0x180003e70`
- `0x1800040f0`
- `0x1800041d0`
- `0x1800044b0`
- `0x180004cb0`
- `0x180004fa0`
- `0x180005920`
- `0x180005b70`
- `0x180006580`
- `0x180006598`
- `0x180006c07`
- `0x180006c13`
- `0x180006c30`
- `0x180007010`

## import_xrefs

- `ntdll!RtlInitializeSid` at `0x180003402`
- `ntdll!RtlInitializeSid` at `0x180003402`
- `ntdll!NtQueryInformationToken` at `0x18000342e`
- `ntdll!NtQueryInformationToken` at `0x1800034b5`
- `ntdll!NtQueryInformationToken` at `0x18000342e`
- `ntdll!NtQueryInformationToken` at `0x1800034b5`
- `ntdll!RtlFreeHeap` at `0x180003466`
- `ntdll!RtlFreeHeap` at `0x180003dd7`
- `ntdll!RtlFreeHeap` at `0x180003e2e`
- `ntdll!RtlFreeHeap` at `0x180003466`
- `ntdll!RtlFreeHeap` at `0x180003dd7`
- `ntdll!RtlFreeHeap` at `0x180003e2e`
- `ntdll!RtlSubAuthoritySid` at `0x180003445`
- `ntdll!RtlSubAuthoritySid` at `0x180003445`
- `ntdll!NtClose` at `0x180003550`
- `ntdll!NtClose` at `0x180003565`
- `ntdll!NtClose` at `0x180003628`
- `ntdll!NtClose` at `0x180003cfb`
- `ntdll!NtClose` at `0x180003d54`
- `ntdll!NtClose` at `0x180003550`
- `ntdll!NtClose` at `0x180003565`
- `ntdll!NtClose` at `0x180003628`
- `ntdll!NtClose` at `0x180003cfb`
- `ntdll!NtClose` at `0x180003d54`
- `ntdll!NtOpenThreadToken` at `0x180003382`
- `ntdll!NtOpenThreadToken` at `0x180003382`
- `ntdll!NtOpenProcessToken` at `0x1800034f5`
- `ntdll!NtOpenProcessToken` at `0x1800034f5`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18000372f`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18000372f`
- `ntdll!DbgPrintEx` at `0x1800039ba`
- `ntdll!DbgPrintEx` at `0x180003bc5`
- `ntdll!DbgPrintEx` at `0x1800039ba`
- `ntdll!DbgPrintEx` at `0x180003bc5`
- `ntdll!NtWriteVirtualMemory` at `0x180003c77`
- `ntdll!NtWriteVirtualMemory` at `0x180003cc2`
- `ntdll!NtWriteVirtualMemory` at `0x180003c77`
- `ntdll!NtWriteVirtualMemory` at `0x180003cc2`
- `ntdll!NtUnmapViewOfSection` at `0x180003659`
- `ntdll!NtUnmapViewOfSection` at `0x180003659`
- `ntdll!RtlAllocateHeap` at `0x1800033d3`
- `ntdll!RtlAllocateHeap` at `0x180003966`
- `ntdll!RtlAllocateHeap` at `0x1800033d3`
- `ntdll!RtlAllocateHeap` at `0x180003966`
- `ntdll!RtlLengthRequiredSid` at `0x1800033ae`
- `ntdll!RtlLengthRequiredSid` at `0x1800033ae`
- `ntdll!NtMapViewOfSection` at `0x180003c49`
- `ntdll!NtMapViewOfSection` at `0x180003c49`
- `CSRSRV!CsrRevertToSelf` at `0x180003793`
- `CSRSRV!CsrRevertToSelf` at `0x1800037b4`
- `CSRSRV!CsrRevertToSelf` at `0x180003d6d`
- `CSRSRV!CsrRevertToSelf` at `0x180003793`
- `CSRSRV!CsrRevertToSelf` at `0x1800037b4`
- `CSRSRV!CsrRevertToSelf` at `0x180003d6d`
- `CSRSRV!CsrImpersonateClient` at `0x180003747`
- `CSRSRV!CsrImpersonateClient` at `0x180003a1d`
- `CSRSRV!CsrImpersonateClient` at `0x180003747`
- `CSRSRV!CsrImpersonateClient` at `0x180003a1d`

## string_xrefs

- `0x1800039b0`: `SXS: BaseSrvSxsGetActivationContextGenerationFunction() returned STATUS_DLL_NOT_FOUND, propagating.\n`

## pseudocode

```c
__int64 __fastcall BaseSrvSxsCreateActivationContextFromStructEx(
        HANDLE SourceProcessHandle,
        void *a2,
        unsigned int *a3,
        union _LARGE_INTEGER a4,
        HANDLE *a5)
{
  HANDLE v7; // r13
  int v9; // r14d
  NTSTATUS TokenILValue; // ebx
  int v11; // esi
  char v12; // r15
  unsigned __int64 v13; // rax
  __int64 v14; // rcx
  unsigned __int64 v15; // rax
  ULONG v16; // r15d
  HANDLE *CsrClientThread; // rax
  BOOL v18; // r12d
  NTSTATUS v19; // eax
  void *v20; // r12
  PSID *Heap; // rax
  PSID *v22; // r14
  NTSTATUS v23; // ebx
  bool v24; // zf
  ULONG v25; // r14d
  NTSTATUS v26; // eax
  __int16 v27; // bx
  unsigned __int16 v28; // ax
  int v29; // eax
  __int64 v30; // rcx
  int v31; // eax
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  int v34; // ecx
  int v35; // eax
  __int64 v36; // rdx
  unsigned __int16 v37; // cx
  __int64 v38; // rax
  PVOID v39; // rax
  int ActivationContextGenerationFunction; // eax
  int v41; // ecx
  char v42; // r14
  int v43; // ecx
  int v44; // r8d
  unsigned int v45; // eax
  _DWORD *v46; // rcx
  __int64 v47; // rdx
  __int128 *v48; // rax
  __int128 v49; // xmm0
  __int128 v50; // xmm1
  __int128 v51; // xmm0
  __int128 v52; // xmm1
  __int128 v53; // xmm0
  __int128 v54; // xmm1
  __int128 v55; // xmm0
  __int128 v56; // xmm1
  __int16 v57; // ax
  HANDLE v58; // rsi
  void *v59; // rdx
  __int16 v60; // ax
  SIZE_T v61; // rax
  NTSTATUS v62; // eax
  int v63; // eax
  ULONG v64; // [rsp+50h] [rbp-B0h]
  ULONG TokenInformationLength; // [rsp+54h] [rbp-ACh] BYREF
  ULONG v66; // [rsp+58h] [rbp-A8h] BYREF
  PVOID BaseAddress; // [rsp+60h] [rbp-A0h] BYREF
  ULONG v68; // [rsp+68h] [rbp-98h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-90h] BYREF
  void *Src[2]; // [rsp+78h] [rbp-88h] BYREF
  ULONG ReturnLength; // [rsp+88h] [rbp-78h] BYREF
  HANDLE Handle; // [rsp+90h] [rbp-70h] BYREF
  union _LARGE_INTEGER SectionOffset; // [rsp+98h] [rbp-68h] BYREF
  ULONG_PTR ViewSize; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE v75; // [rsp+A8h] [rbp-58h]
  unsigned int (__fastcall *v76)(int *); // [rsp+B0h] [rbp-50h] BYREF
  HANDLE ProcessHandle; // [rsp+B8h] [rbp-48h]
  PVOID P; // [rsp+C0h] [rbp-40h]
  PVOID v79[2]; // [rsp+C8h] [rbp-38h] BYREF
  HANDLE *v80; // [rsp+D8h] [rbp-28h]
  HANDLE *v81; // [rsp+E0h] [rbp-20h]
  __int128 v82; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v83; // [rsp+F8h] [rbp-8h]
  __int128 v84; // [rsp+108h] [rbp+8h]
  __int64 v85; // [rsp+118h] [rbp+18h]
  _QWORD v86[2]; // [rsp+120h] [rbp+20h] BYREF
  HANDLE v87[2]; // [rsp+130h] [rbp+30h] BYREF
  HANDLE v88[2]; // [rsp+140h] [rbp+40h]
  _OWORD v89[4]; // [rsp+150h] [rbp+50h] BYREF
  __int128 v90; // [rsp+190h] [rbp+90h]
  __int128 v91; // [rsp+1A0h] [rbp+A0h]
  __int128 v92; // [rsp+1B0h] [rbp+B0h]
  __int128 v93; // [rsp+1C0h] [rbp+C0h]
  __int128 v94; // [rsp+1D0h] [rbp+D0h]
  __int128 v95; // [rsp+1E0h] [rbp+E0h]
  __int128 v96; // [rsp+1F0h] [rbp+F0h]
  __int128 v97; // [rsp+200h] [rbp+100h]
  __int128 v98; // [rsp+210h] [rbp+110h]
  __int128 v99; // [rsp+220h] [rbp+120h]
  int v100; // [rsp+230h] [rbp+130h] BYREF
  __int16 v101; // [rsp+234h] [rbp+134h]
  __int64 v102; // [rsp+238h] [rbp+138h]
  __int64 v103; // [rsp+240h] [rbp+140h]
  __int64 v104; // [rsp+248h] [rbp+148h]
  __int64 v105[2]; // [rsp+250h] [rbp+150h] BYREF
  int v106; // [rsp+260h] [rbp+160h]
  __int64 v107[3]; // [rsp+268h] [rbp+168h] BYREF
  __int64 v108; // [rsp+280h] [rbp+180h]
  int v109; // [rsp+288h] [rbp+188h]
  HANDLE SectionHandle; // [rsp+290h] [rbp+190h] BYREF
  __int64 v111; // [rsp+298h] [rbp+198h] BYREF
  unsigned int v112; // [rsp+2A0h] [rbp+1A0h]
  unsigned int v113; // [rsp+2A4h] [rbp+1A4h] BYREF
  __int64 v114; // [rsp+2A8h] [rbp+1A8h] BYREF
  _BYTE v115[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  PVOID v116; // [rsp+3B8h] [rbp+2B8h]
  __int16 v117; // [rsp+3C0h] [rbp+2C0h]
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+3D0h] [rbp+2D0h] BYREF

  v81 = a5;
  SectionOffset = a4;
  v7 = SourceProcessHandle;
  ProcessHandle = a2;
  v75 = SourceProcessHandle;
  if ( !a3 )
    return 3221225485LL;
  v9 = *a3;
  if ( (*a3 & 0xD) == 0 )
    return 0;
  TokenILValue = 0;
  BaseAddress = 0;
  memset_0(&v100, 0, 0x198u);
  ViewSize = 0;
  v76 = 0;
  P = 0;
  v92 = 0;
  v93 = 0;
  v94 = 0;
  v95 = 0;
  v96 = 0;
  v97 = 0;
  v98 = 0;
  v99 = 0;
  if ( (v9 & 0x1C1) != 0x41 || (v11 = 1, *((_QWORD *)a3 + 22) == -1) )
    v11 = 0;
  v64 = 0;
  v86[0] = a3 + 22;
  v12 = 0;
  v68 = 0;
  v86[1] = v79;
  v85 = 0;
  v13 = *((unsigned __int16 *)a3 + 4);
  memset(v89, 0, sizeof(v89));
  v90 = 0;
  v91 = 0;
  *(_OWORD *)v79 = 0;
  *(_OWORD *)v87 = 0;
  *(_OWORD *)v88 = 0;
  *(_OWORD *)Src = 0;
  v82 = 0;
  v83 = 0;
  v84 = 0;
  if ( (unsigned int)v13 < 4
    || (v14 = *((_QWORD *)a3 + 2), v15 = v13 >> 1, *(_WORD *)(v14 + 2 * v15 - 2))
    || *(_WORD *)(v14 + 2 * v15 - 4) )
  {
    TokenILValue = -1073741811;
    goto LABEL_154;
  }
  if ( !v11 )
  {
    ++BaseSrvActCtxGenCount;
    goto LABEL_62;
  }
  if ( a4.QuadPart && (*(_BYTE *)(a4.QuadPart + 24) & 1) != 0 )
  {
    ++BaseSrvActCtxGenCount;
    v11 = 0;
    goto LABEL_62;
  }
  if ( (v9 & 0x3000) == 0x3000 )
  {
    ++BaseSrvActCtxGenCount;
    v11 = 0;
    goto LABEL_62;
  }
  ++BaseSrvActCtxGenCount;
  TokenHandle = 0;
  Handle = 0;
  v16 = 0;
  CsrClientThread = (HANDLE *)NtCurrentTeb()->CsrClientThread;
  v18 = 0;
  v66 = 0;
  v80 = CsrClientThread;
  v19 = NtOpenThreadToken(CsrClientThread[8], 8u, 0, &TokenHandle);
  if ( v19 < 0 )
  {
    v24 = v19 == -1073741700;
  }
  else
  {
    v20 = TokenHandle;
    *(_DWORD *)IdentifierAuthority.Value = 0;
    *(_WORD *)&IdentifierAuthority.Value[4] = 4096;
    TokenInformationLength = RtlLengthRequiredSid(1u) + 16;
    Heap = (PSID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, TokenInformationLength);
    v22 = Heap;
    if ( Heap )
    {
      *Heap = Heap + 2;
      v23 = RtlInitializeSid(Heap + 2, &IdentifierAuthority, 1u);
      if ( v23 >= 0 )
      {
        v23 = NtQueryInformationToken(v20, TokenIntegrityLevel, v22, TokenInformationLength, &TokenInformationLength);
        if ( v23 >= 0 )
          v16 = *RtlSubAuthoritySid(*v22, 0);
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v22);
    }
    else
    {
      v23 = -1073741801;
    }
    if ( v23 < 0 )
      goto LABEL_36;
    TokenInformationLength = 0;
    ReturnLength = 0;
    if ( NtQueryInformationToken(TokenHandle, TokenImpersonationLevel, &TokenInformationLength, 4u, &ReturnLength) < 0 )
      goto LABEL_36;
    v18 = v23 >= 0;
    if ( TokenInformationLength == 2 )
      goto LABEL_30;
    v24 = TokenInformationLength == 3;
  }
  if ( !v24 )
  {
LABEL_36:
    TokenILValue = 0;
    goto LABEL_37;
  }
LABEL_30:
  if ( NtOpenProcessToken(*((HANDLE *)v80[7] + 10), 8u, &Handle) < 0 )
    goto LABEL_36;
  TokenILValue = GetTokenILValue(Handle, &v66);
  if ( TokenILValue < 0 )
    goto LABEL_36;
  if ( !v18 )
  {
    v25 = v66;
    v64 = v66;
    goto LABEL_38;
  }
  if ( v16 > v66 )
  {
LABEL_37:
    v25 = 0;
    v11 = 0;
    goto LABEL_38;
  }
  v25 = v16;
  v64 = v16;
LABEL_38:
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( Handle )
    NtClose(Handle);
  if ( v11 )
  {
    TokenILValue = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))BaseSrvSxsGetCacheKey)(
                     a3,
                     (union _LARGE_INTEGER)SectionOffset.QuadPart,
                     v89);
    if ( TokenILValue < 0
      || (TokenILValue = BaseSrvActivationContextCacheLookupEntry(
                           v89,
                           &SectionHandle,
                           a3 + 50,
                           a3 + 53,
                           a3 + 58,
                           a3 + 60,
                           Src,
                           &v68),
          (int)(TokenILValue + 0x80000000) >= 0)
      && TokenILValue != -1073741275 )
    {
LABEL_51:
      v12 = 0;
      goto LABEL_52;
    }
    if ( SectionHandle && v68 < v25 )
    {
      TokenILValue = BaseSrvActivationContextCacheRemoveEntry(v89);
      if ( ((TokenILValue + 0x80000000) & 0x80000000) == 0 && TokenILValue != -1073741275 )
        goto LABEL_51;
      v26 = NtClose(SectionHandle);
      SectionHandle = 0;
      TokenILValue = v26;
      if ( v26 < 0 )
        goto LABEL_51;
    }
    else
    {
      v27 = (__int16)Src[0];
      if ( LOWORD(Src[0]) )
      {
        v28 = *((_WORD *)a3 + 109);
        if ( v28 )
        {
          if ( LOWORD(Src[0]) < v28 )
          {
            memcpy_0(*((void **)a3 + 28), Src[1], LOWORD(Src[0]));
            *((_WORD *)a3 + 108) = v27;
            v12 = 0;
            TokenILValue = 0;
            v7 = v75;
            goto LABEL_62;
          }
          *((_WORD *)a3 + 108) = 0;
        }
      }
    }
    TokenILValue = 0;
  }
  v7 = v75;
  v12 = 0;
LABEL_62:
  if ( SectionHandle )
  {
    v42 = 0;
    goto LABEL_137;
  }
  v29 = *a3;
  if ( (*a3 & 1) != 0 )
  {
    TokenILValue = BasepSxsCreateMemoryStream(v7, (__int64)v105);
    if ( TokenILValue < 0 )
      goto LABEL_52;
    v24 = *((_QWORD *)a3 + 22) == 1;
    v106 = 1;
    if ( v24 )
    {
      v32 = *((_OWORD *)a3 + 6);
      v82 = *((_OWORD *)a3 + 5);
      v33 = *((_OWORD *)a3 + 7);
      v83 = v32;
      *(_QWORD *)&v32 = *((_QWORD *)a3 + 16);
      v84 = v33;
      v85 = v32;
    }
    else
    {
      TokenILValue = RtlDosPathNameToNtPathName_U_WithStatus(*((_QWORD *)a3 + 12), v79, 0, 0);
      if ( TokenILValue < 0 )
        goto LABEL_52;
      v12 = CsrImpersonateClient(0);
      if ( !v12 )
      {
        TokenILValue = -1073741659;
        goto LABEL_52;
      }
      v31 = BasepSxsCreateFileStreamEx(v30, v86, *a3, v87, &v82);
      TokenILValue = v31;
      if ( v31 >= 0 )
      {
        *a3 |= 2u;
        BYTE2(v82) = 5;
        if ( v11 )
          WORD1(v90) |= 1u;
      }
      else if ( !(unsigned int)BasepSxsIsStatusFileNotFoundEtc((unsigned int)v31) )
      {
        goto LABEL_52;
      }
      CsrRevertToSelf();
    }
    if ( (*(_BYTE *)a3 & 2) != 0 )
    {
      v12 = 0;
      TokenILValue = BasepSxsCreateMemoryStream(v7, (__int64)v107);
      if ( TokenILValue < 0 )
        goto LABEL_52;
      if ( BYTE1(v82) && WORD4(v82) && (_QWORD)v83 )
      {
        v107[1] = v83;
        if ( BYTE1(v82) == 1 )
        {
          v106 = 2;
        }
        else if ( BYTE1(v82) == 2 )
        {
          v34 = v100;
          v106 = 3;
          goto LABEL_89;
        }
      }
    }
    v34 = v100;
  }
  else
  {
    v34 = v100 | 4;
    v100 |= 4u;
    if ( (v29 & 4) != 0 )
    {
      v34 |= 2u;
      v100 = v34;
    }
    v104 = *((_QWORD *)a3 + 20);
  }
LABEL_89:
  v35 = *a3;
  if ( (*a3 & 0x10) != 0 )
  {
    v34 |= 8u;
    v100 = v34;
  }
  if ( (v35 & 0x400) != 0 )
  {
    v34 |= 0x10u;
    v100 = v34;
  }
  if ( (v35 & 0x800) != 0 )
  {
    v34 |= 0x20u;
    v100 = v34;
  }
  if ( (v35 & 0x7000) == 0x7000 )
    v100 = v34 | 0x40;
  v36 = *((_QWORD *)a3 + 22);
  v37 = *((_WORD *)a3 + 109);
  v101 = *((_WORD *)a3 + 2);
  v102 = *((_QWORD *)a3 + 2);
  v38 = v108;
  if ( v36 != -1 )
    v38 = v36;
  v108 = v38;
  v103 = *((_QWORD *)a3 + 18);
  if ( v37 )
  {
    v39 = (PVOID)*((_QWORD *)a3 + 28);
    *(_OWORD *)Src = *(_OWORD *)(a3 + 54);
    v117 = v37 >> 1;
LABEL_105:
    v116 = v39;
    goto LABEL_106;
  }
  if ( v36 == 1 )
  {
    v117 = 60;
    v39 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x78u);
    P = v39;
    if ( !v39 )
    {
      TokenILValue = -1073741801;
      v12 = 0;
      goto LABEL_52;
    }
    Src[1] = v39;
    WORD1(Src[0]) = 120;
    goto LABEL_105;
  }
LABEL_106:
  ActivationContextGenerationFunction = BaseSrvSxsGetActivationContextGenerationFunction(&v76, &ViewSize);
  TokenILValue = ActivationContextGenerationFunction;
  if ( ActivationContextGenerationFunction == -1073741515 )
  {
    DbgPrintEx(
      0x33u,
      0,
      "SXS: BaseSrvSxsGetActivationContextGenerationFunction() returned STATUS_DLL_NOT_FOUND, propagating.\n");
    v12 = 0;
    goto LABEL_52;
  }
  v12 = 0;
  if ( ActivationContextGenerationFunction < 0 )
    goto LABEL_52;
  v41 = *((unsigned __int8 *)a3 + 25);
  v42 = 1;
  if ( (_BYTE)v41 && *((_WORD *)a3 + 16) && *((_QWORD *)a3 + 5) )
  {
    v105[1] = *((_QWORD *)a3 + 5);
    v43 = v41 - 1;
    if ( v43 )
    {
      if ( v43 == 1 )
        v106 = 3;
    }
    else
    {
      v106 = 2;
    }
  }
  v12 = CsrImpersonateClient(0);
  if ( !v12 )
  {
    TokenILValue = -1073741659;
    goto LABEL_52;
  }
  if ( !v76(&v100) )
  {
    DbgPrintEx(0x33u, 3u, "SXS: Activation Context generation function failed.\n");
    TokenILValue = -1072365566;
    goto LABEL_52;
  }
  v44 = *a3;
  if ( (*a3 & 4) != 0 && ((v109 & 1) != 0 || (v109 & 2) != 0) )
  {
    TokenILValue = -1072365550;
    goto LABEL_52;
  }
  if ( v11 && ((v109 & 4) != 0 || (v109 & 8) != 0) )
    v11 = 0;
  v45 = v112;
  v46 = a3 + 60;
  v47 = 2;
  *((_QWORD *)a3 + 25) = v111;
  a3[52] = v45;
  a3[53] = v113;
  *((_QWORD *)a3 + 29) = v114;
  v48 = (__int128 *)v115;
  do
  {
    v46 += 32;
    v49 = *v48;
    v50 = v48[1];
    v48 += 8;
    *((_OWORD *)v46 - 8) = v49;
    v51 = *(v48 - 6);
    *((_OWORD *)v46 - 7) = v50;
    v52 = *(v48 - 5);
    *((_OWORD *)v46 - 6) = v51;
    v53 = *(v48 - 4);
    *((_OWORD *)v46 - 5) = v52;
    v54 = *(v48 - 3);
    *((_OWORD *)v46 - 4) = v53;
    v55 = *(v48 - 2);
    *((_OWORD *)v46 - 3) = v54;
    v56 = *(v48 - 1);
    *((_OWORD *)v46 - 2) = v55;
    *((_OWORD *)v46 - 1) = v56;
    --v47;
  }
  while ( v47 );
  *v46 = *(_DWORD *)v48;
  v57 = 2 * v117;
  *((_WORD *)a3 + 108) = 2 * v117;
  LOWORD(Src[0]) = v57;
  if ( SectionHandle && v11 && (*((_QWORD *)a3 + 22) == 1 || (v44 & 2) == 0) )
  {
    TokenILValue = BaseSrvActivationContextCacheInsertEntry(v89, SectionHandle, &v111, &v113, &v114, v115, Src, v64);
    if ( TokenILValue < 0 )
      goto LABEL_52;
  }
LABEL_137:
  if ( SectionHandle )
  {
    if ( *((_QWORD *)a3 + 23) )
    {
      v58 = ProcessHandle;
      ViewSize = 0;
      BaseAddress = 0;
      SectionOffset.QuadPart = 0;
      TokenILValue = NtMapViewOfSection(
                       SectionHandle,
                       ProcessHandle,
                       &BaseAddress,
                       0,
                       0,
                       &SectionOffset,
                       &ViewSize,
                       ViewShare,
                       0x400000u,
                       2u);
      if ( TokenILValue < 0 )
        goto LABEL_52;
      TokenILValue = NtWriteVirtualMemory(v58, *((PVOID *)a3 + 23), &BaseAddress, 8u, 0);
      if ( TokenILValue < 0 )
        goto LABEL_52;
      v59 = (void *)*((_QWORD *)a3 + 24);
      if ( v59 )
      {
        v60 = *((_WORD *)a3 + 2);
        if ( v60 == 10 || (v24 = v60 == 13, v61 = 8, v24) )
          v61 = 4;
        TokenILValue = NtWriteVirtualMemory(v58, v59, &BaseAddress, v61, 0);
        if ( TokenILValue < 0 )
          goto LABEL_52;
      }
    }
    if ( v81 )
    {
      *v81 = SectionHandle;
      SectionHandle = 0;
      goto LABEL_149;
    }
    v62 = NtClose(SectionHandle);
    SectionHandle = 0;
    TokenILValue = v62;
    if ( v62 >= 0 )
      goto LABEL_149;
LABEL_52:
    if ( BaseAddress )
      NtUnmapViewOfSection(ProcessHandle, BaseAddress);
    goto LABEL_154;
  }
LABEL_149:
  v63 = 0;
  if ( !v42 )
    v63 = TokenILValue;
  TokenILValue = v63;
  if ( v63 < 0 )
    goto LABEL_52;
  TokenILValue = 0;
  BaseAddress = 0;
LABEL_154:
  if ( SectionHandle )
    NtClose(SectionHandle);
  if ( v12 )
    CsrRevertToSelf();
  if ( (*(_BYTE *)a3 & 1) != 0 )
  {
    if ( v105[0] )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v105[0] + 16LL))(v105[0]);
      v105[0] = 0;
    }
    if ( v107[0] )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v107[0] + 16LL))(v107[0]);
      v107[0] = 0;
    }
  }
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( v87[0] )
    NtClose_0(v87[0]);
  if ( v88[0] )
    NtClose_0(v88[0]);
  if ( v88[1] )
    NtUnmapViewOfSection_0((HANDLE)0xFFFFFFFFFFFFFFFFLL, v88[1]);
  if ( v79[1] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v79[1]);
  return (unsigned int)TokenILValue;
}

```

## disassembly

```asm
0x180003170  push    rbp
0x180003172  push    rbx
0x180003173  push    rdi
0x180003174  push    r12
0x180003176  push    r13
0x180003178  lea     rbp, [rsp-300h]
0x180003180  sub     rsp, 400h
0x180003187  mov     rax, cs:__security_cookie
0x18000318e  xor     rax, rsp
0x180003191  mov     [rbp+320h+var_48], rax
0x180003198  mov     rax, [rbp+320h+arg_20]
0x18000319f  mov     r12, r9
0x1800031a2  mov     [rbp+320h+var_340], rax
0x1800031a6  mov     rdi, r8
0x1800031a9  mov     qword ptr [rbp+320h+var_388], r9
0x1800031ad  mov     r13, rcx
0x1800031b0  mov     [rbp+320h+ProcessHandle], rdx
0x1800031b4  mov     [rbp+320h+var_378], rcx
0x1800031b8  test    r8, r8
0x1800031bb  jnz     short loc_1800031C7
0x1800031bd  mov     eax, 0C000000Dh
0x1800031c2  jmp     loc_180003E44
0x1800031c7  mov     [rsp+420h+var_30], r14
0x1800031cf  mov     r14d, [r8]
0x1800031d2  test    r14b, 0Dh
0x1800031d6  jnz     short loc_1800031DF
0x1800031d8  xor     eax, eax
0x1800031da  jmp     loc_180003E3C
0x1800031df  xor     ebx, ebx
0x1800031e1  mov     [rsp+420h+var_28], rsi
0x1800031e9  xor     edx, edx; Val
0x1800031eb  mov     [rsp+420h+BaseAddress], rbx
0x1800031f0  mov     r8d, 198h; Size
0x1800031f6  mov     [rsp+420h+var_38], r15
0x1800031fe  lea     rcx, [rbp+320h+var_1F0]; void *
0x180003205  call    memset_0
0x18000320a  xorps   xmm0, xmm0
0x18000320d  mov     [rbp+320h+var_380], rbx
0x180003211  xorps   xmm1, xmm1
0x180003214  mov     [rbp+320h+var_370], rbx
0x180003218  mov     eax, r14d
0x18000321b  mov     [rbp+320h+P], rbx
0x18000321f  and     eax, 1C1h
0x180003224  movups  [rbp+320h+var_270], xmm0
0x18000322b  movups  [rbp+320h+var_260], xmm0
0x180003232  movups  [rbp+320h+var_250], xmm0
0x180003239  movups  [rbp+320h+var_240], xmm0
0x180003240  movups  [rbp+320h+var_230], xmm1
0x180003247  movups  [rbp+320h+var_220], xmm1
0x18000324e  movups  [rbp+320h+var_210], xmm1
0x180003255  movups  [rbp+320h+var_200], xmm1
0x18000325c  cmp     eax, 41h ; 'A'
0x18000325f  jnz     short loc_18000326E
0x180003261  cmp     qword ptr [rdi+0B0h], 0FFFFFFFFFFFFFFFFh
0x180003269  lea     esi, [rbx+1]
0x18000326c  jnz     short loc_180003270
0x18000326e  mov     esi, ebx
0x180003270  lea     rax, [rdi+58h]
0x180003274  mov     [rsp+420h+var_3D0], ebx
0x180003278  mov     [rbp+320h+var_300], rax
0x18000327c  xor     r15b, r15b
0x18000327f  lea     rax, [rbp+320h+var_358]
0x180003283  mov     [rsp+420h+var_3B8], ebx
0x180003287  mov     [rbp+320h+var_2F8], rax
0x18000328b  xor     eax, eax
0x18000328d  mov     [rbp+320h+var_308], rax
0x180003291  movzx   eax, word ptr [rdi+8]
0x180003295  movups  [rbp+320h+var_2D0], xmm0
0x180003299  movups  [rbp+320h+var_2C0], xmm0
0x18000329d  movups  [rbp+320h+var_2B0], xmm0
0x1800032a1  movups  [rbp+320h+var_2A0], xmm0
0x1800032a8  movups  [rbp+320h+var_290], xmm0
0x1800032af  movups  [rbp+320h+var_280], xmm0
0x1800032b6  movups  xmmword ptr [rbp+320h+var_358], xmm0
0x1800032ba  movups  xmmword ptr [rbp+320h+var_2F0], xmm0
0x1800032be  movups  xmmword ptr [rbp+320h+var_2E0], xmm0
0x1800032c2  movups  xmmword ptr [rsp+420h+Src], xmm0
0x1800032c7  movups  [rbp+320h+var_338], xmm1
0x1800032cb  movups  [rbp+320h+var_328], xmm1
0x1800032cf  movups  [rbp+320h+var_318], xmm1
0x1800032d3  cmp     eax, 4
0x1800032d6  jb      loc_180003D38
0x1800032dc  mov     rcx, [rdi+10h]
0x1800032e0  shr     rax, 1
0x1800032e3  cmp     [rcx+rax*2-2], bx
0x1800032e8  jnz     loc_180003D38
0x1800032ee  cmp     [rcx+rax*2-4], bx
0x1800032f3  jnz     loc_180003D38
0x1800032f9  test    esi, esi
0x1800032fb  jz      loc_1800036BF
0x180003301  test    r12, r12
0x180003304  jz      short loc_18000331F
0x180003306  test    byte ptr [r12+18h], 1
0x18000330c  jz      short loc_18000331F
0x18000330e  xor     r12d, r12d
0x180003311  inc     cs:BaseSrvActCtxGenCount
0x180003317  mov     esi, r12d
0x18000331a  jmp     loc_1800036C8
0x18000331f  and     r14d, 3000h
0x180003326  cmp     r14d, 3000h
0x18000332d  jnz     short loc_180003340
0x18000332f  xor     r12d, r12d
0x180003332  inc     cs:BaseSrvActCtxGenCount
0x180003338  mov     esi, r12d
0x18000333b  jmp     loc_1800036C8
0x180003340  inc     cs:BaseSrvActCtxGenCount
0x180003346  test    esi, esi
0x180003348  jz      loc_1800036C5
0x18000334e  xor     r13d, r13d
0x180003351  lea     r9, [rsp+420h+TokenHandle]; TokenHandle
0x180003356  mov     [rsp+420h+TokenHandle], r13
0x18000335b  xor     r8d, r8d; OpenAsSelf
0x18000335e  mov     [rbp+320h+Handle], r13
0x180003362  mov     r15d, r13d
0x180003365  mov     rax, gs:70h
0x18000336e  mov     r12d, r13d
0x180003371  lea     edx, [r13+8]; DesiredAccess
0x180003375  mov     [rsp+420h+var_3C8], r13d
0x18000337a  mov     [rbp+320h+var_348], rax
0x18000337e  mov     rcx, [rax+40h]; ThreadHandle
0x180003382  call    cs:__imp_NtOpenThreadToken
0x180003389  nop     dword ptr [rax+rax+00h]
0x18000338e  test    eax, eax
0x180003390  js      loc_1800034D9
0x180003396  mov     r12, [rsp+420h+TokenHandle]
0x18000339b  lea     ecx, [r13+1]; SubAuthorityCount
0x18000339f  mov     dword ptr [rbp+320h+IdentifierAuthority.Value], ebx
0x1800033a5  mov     word ptr [rbp+320h+IdentifierAuthority.Value+4], 1000h
0x1800033ae  call    cs:__imp_RtlLengthRequiredSid
0x1800033b5  nop     dword ptr [rax+rax+00h]
0x1800033ba  add     eax, 10h
0x1800033bd  xor     edx, edx; Flags
0x1800033bf  mov     [rsp+420h+TokenInformationLength], eax
0x1800033c3  mov     rcx, gs:60h
0x1800033cc  mov     r8d, eax; Size
0x1800033cf  mov     rcx, [rcx+30h]; HeapHandle
0x1800033d3  call    cs:__imp_RtlAllocateHeap
0x1800033da  nop     dword ptr [rax+rax+00h]
0x1800033df  mov     r14, rax
0x1800033e2  test    rax, rax
0x1800033e5  jnz     short loc_1800033F1
0x1800033e7  mov     ebx, 0C0000017h
0x1800033ec  jmp     loc_180003472
0x1800033f1  lea     rcx, [rax+10h]; Sid
0x1800033f5  mov     r8b, 1; SubAuthorityCount
0x1800033f8  lea     rdx, [rbp+320h+IdentifierAuthority]; IdentifierAuthority
0x1800033ff  mov     [rax], rcx
0x180003402  call    cs:__imp_RtlInitializeSid
0x180003409  nop     dword ptr [rax+rax+00h]
0x18000340e  mov     ebx, eax
0x180003410  test    eax, eax
0x180003412  js      short loc_180003454
0x180003414  mov     r9d, [rsp+420h+TokenInformationLength]; TokenInformationLength
0x180003419  lea     rax, [rsp+420h+TokenInformationLength]
0x18000341e  mov     r8, r14; TokenInformation
0x180003421  mov     [rsp+420h+ReturnLength], rax; ReturnLength
0x180003426  mov     edx, 19h; TokenInformationClass
0x18000342b  mov     rcx, r12; TokenHandle
0x18000342e  call    cs:__imp_NtQueryInformationToken
0x180003435  nop     dword ptr [rax+rax+00h]
0x18000343a  mov     ebx, eax
0x18000343c  test    eax, eax
0x18000343e  js      short loc_180003454
0x180003440  mov     rcx, [r14]; Sid
0x180003443  xor     edx, edx; SubAuthority
0x180003445  call    cs:__imp_RtlSubAuthoritySid
0x18000344c  nop     dword ptr [rax+rax+00h]
0x180003451  mov     r15d, [rax]
0x180003454  mov     rcx, gs:60h
0x18000345d  mov     r8, r14; P
0x180003460  xor     edx, edx; Flags
0x180003462  mov     rcx, [rcx+30h]; HeapHandle
0x180003466  call    cs:__imp_RtlFreeHeap
0x18000346d  nop     dword ptr [rax+rax+00h]
0x180003472  mov     r14d, ebx
0x180003475  not     r14d
0x180003478  shr     r14d, 1Fh
0x18000347c  test    ebx, ebx
0x18000347e  js      loc_18000353B
0x180003484  mov     r12d, r14d
0x180003487  test    r14d, r14d
0x18000348a  jz      short loc_1800034E0
0x18000348c  mov     rcx, [rsp+420h+TokenHandle]; TokenHandle
0x180003491  lea     rax, [rbp+320h+var_398]
0x180003495  xor     r12d, r12d
0x180003498  mov     [rsp+420h+ReturnLength], rax; ReturnLength
0x18000349d  lea     r8, [rsp+420h+TokenInformationLength]; TokenInformation
0x1800034a2  mov     [rsp+420h+TokenInformationLength], r12d
0x1800034a7  mov     [rbp+320h+var_398], r12d
0x1800034ab  lea     r9d, [r12+4]; TokenInformationLength
0x1800034b0  lea     edx, [r12+9]; TokenInformationClass
0x1800034b5  call    cs:__imp_NtQueryInformationToken
0x1800034bc  nop     dword ptr [rax+rax+00h]
0x1800034c1  test    eax, eax
0x1800034c3  js      short loc_18000353B
0x1800034c5  mov     ecx, [rsp+420h+TokenInformationLength]
0x1800034c9  mov     eax, r15d
0x1800034cc  mov     r12d, r14d
0x1800034cf  cmp     ecx, 2
0x1800034d2  jz      short loc_1800034E0
0x1800034d4  cmp     ecx, 3
0x1800034d7  jmp     short loc_1800034DE
0x1800034d9  cmp     eax, 0C000007Ch
0x1800034de  jnz     short loc_18000353B
0x1800034e0  mov     rcx, [rbp+320h+var_348]
0x1800034e4  lea     r8, [rbp+320h+Handle]; TokenHandle
0x1800034e8  mov     edx, 8; DesiredAccess
0x1800034ed  mov     rcx, [rcx+38h]
0x1800034f1  mov     rcx, [rcx+50h]; ProcessHandle
0x1800034f5  call    cs:__imp_NtOpenProcessToken
0x1800034fc  nop     dword ptr [rax+rax+00h]
0x180003501  test    eax, eax
0x180003503  js      short loc_18000353B
0x180003505  mov     rcx, [rbp+320h+Handle]
0x180003509  lea     rdx, [rsp+420h+var_3C8]
0x18000350e  call    GetTokenILValue
0x180003513  mov     ebx, eax
0x180003515  test    eax, eax
0x180003517  js      short loc_18000353B
0x180003519  test    r12d, r12d
0x18000351c  jz      short loc_18000352F
0x18000351e  cmp     r15d, [rsp+420h+var_3C8]
0x180003523  ja      short loc_18000353E
0x180003525  mov     r14d, r15d
0x180003528  mov     [rsp+420h+var_3D0], r15d
0x18000352d  jmp     short loc_180003546
0x18000352f  mov     r14d, [rsp+420h+var_3C8]
0x180003534  mov     [rsp+420h+var_3D0], r14d
0x180003539  jmp     short loc_180003546
0x18000353b  mov     ebx, r13d
0x18000353e  mov     r14d, [rsp+420h+var_3D0]
0x180003543  mov     esi, r13d
0x180003546  mov     rcx, [rsp+420h+TokenHandle]; Handle
0x18000354b  test    rcx, rcx
0x18000354e  jz      short loc_18000355C
0x180003550  call    cs:__imp_NtClose
0x180003557  nop     dword ptr [rax+rax+00h]
0x18000355c  mov     rcx, [rbp+320h+Handle]; Handle
0x180003560  test    rcx, rcx
0x180003563  jz      short loc_180003571
0x180003565  call    cs:__imp_NtClose
0x18000356c  nop     dword ptr [rax+rax+00h]
0x180003571  test    esi, esi
0x180003573  jz      loc_1800036B6
0x180003579  mov     rdx, qword ptr [rbp+320h+var_388]
0x18000357d  lea     r8, [rbp+320h+var_2D0]
0x180003581  mov     rcx, rdi
0x180003584  call    BaseSrvSxsGetCacheKey
0x180003589  mov     ebx, eax
0x18000358b  test    eax, eax
0x18000358d  js      loc_180003641
0x180003593  lea     rdx, [rsp+420h+var_3B8]
0x180003598  mov     qword ptr [rsp+420h+InheritDisposition], rdx
0x18000359d  lea     rax, [rdi+0F0h]
0x1800035a4  lea     rdx, [rsp+420h+Src]
0x1800035a9  mov     [rsp+420h+ViewSize], rdx
0x1800035ae  lea     rcx, [rdi+0E8h]
0x1800035b5  mov     [rsp+420h+SectionOffset], rax
0x1800035ba  lea     r9, [rdi+0D4h]
0x1800035c1  mov     [rsp+420h+ReturnLength], rcx
0x1800035c6  lea     r8, [rdi+0C8h]
0x1800035cd  lea     rcx, [rbp+320h+var_2D0]
0x1800035d1  lea     rdx, [rbp+320h+SectionHandle]
0x1800035d8  call    BaseSrvActivationContextCacheLookupEntry
0x1800035dd  mov     r15d, 80000000h
0x1800035e3  mov     ebx, eax
0x1800035e5  add     eax, r15d
0x1800035e8  test    r15d, eax
0x1800035eb  jnz     short loc_1800035F5
0x1800035ed  cmp     ebx, 0C0000225h
0x1800035f3  jnz     short loc_180003641
0x1800035f5  cmp     [rbp+320h+SectionHandle], 0
0x1800035fd  jz      short loc_18000366A
0x1800035ff  cmp     [rsp+420h+var_3B8], r14d
0x180003604  jnb     short loc_18000366A
0x180003606  lea     rcx, [rbp+320h+var_2D0]
0x18000360a  call    BaseSrvActivationContextCacheRemoveEntry
0x18000360f  mov     ebx, eax
0x180003611  add     eax, r15d
0x180003614  test    r15d, eax
0x180003617  jnz     short loc_180003621
0x180003619  cmp     ebx, 0C0000225h
0x18000361f  jnz     short loc_180003641
0x180003621  mov     rcx, [rbp+320h+SectionHandle]; Handle
0x180003628  call    cs:__imp_NtClose
0x18000362f  nop     dword ptr [rax+rax+00h]
0x180003634  mov     [rbp+320h+SectionHandle], r13
0x18000363b  mov     ebx, eax
0x18000363d  test    eax, eax
0x18000363f  jns     short loc_1800036B3
0x180003641  xor     r15b, r15b
0x180003644  xor     r12d, r12d
0x180003647  mov     rdx, [rsp+420h+BaseAddress]; BaseAddress
0x18000364c  test    rdx, rdx
0x18000364f  jz      loc_180003D40
0x180003655  mov     rcx, [rbp+320h+ProcessHandle]; ProcessHandle
0x180003659  call    cs:__imp_NtUnmapViewOfSection
0x180003660  nop     dword ptr [rax+rax+00h]
0x180003665  jmp     loc_180003D40
0x18000366a  movzx   ebx, word ptr [rsp+420h+Src]
  ... truncated ...
```
