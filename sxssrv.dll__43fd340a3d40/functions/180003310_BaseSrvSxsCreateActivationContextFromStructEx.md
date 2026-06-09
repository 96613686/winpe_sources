# BaseSrvSxsCreateActivationContextFromStructEx

- ea: `0x180003310`
- end: `0x18000400b`
- name: `BaseSrvSxsCreateActivationContextFromStructEx`
- size: `3323`
- prototype: `__int64 __fastcall(HANDLE SourceProcessHandle, void *, unsigned int *, union _LARGE_INTEGER, HANDLE *)`
- caller_count: `3`
- callee_count: `16`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001450`
- `0x180001e00`
- `0x180004a60`

## callees

- `0x180001110`
- `0x180003310`
- `0x180004020`
- `0x1800042b0`
- `0x180004390`
- `0x180004660`
- `0x180004e60`
- `0x180005170`
- `0x180005a10`
- `0x180005c40`
- `0x180006654`
- `0x18000666c`
- `0x180006cc1`
- `0x180006ccd`
- `0x180006cf0`
- `0x180008010`

## import_xrefs

- `ntdll!RtlInitializeSid` at `0x180003598`
- `ntdll!RtlInitializeSid` at `0x180003598`
- `ntdll!NtQueryInformationToken` at `0x1800035c4`
- `ntdll!NtQueryInformationToken` at `0x18000364c`
- `ntdll!NtQueryInformationToken` at `0x1800035c4`
- `ntdll!NtQueryInformationToken` at `0x18000364c`
- `ntdll!RtlFreeHeap` at `0x1800035fc`
- `ntdll!RtlFreeHeap` at `0x180003f7f`
- `ntdll!RtlFreeHeap` at `0x180003fd6`
- `ntdll!RtlFreeHeap` at `0x1800035fc`
- `ntdll!RtlFreeHeap` at `0x180003f7f`
- `ntdll!RtlFreeHeap` at `0x180003fd6`
- `ntdll!RtlSubAuthoritySid` at `0x1800035db`
- `ntdll!RtlSubAuthoritySid` at `0x1800035db`
- `ntdll!NtClose` at `0x180003683`
- `ntdll!NtClose` at `0x180003698`
- `ntdll!NtClose` at `0x1800037f1`
- `ntdll!NtClose` at `0x180003e8d`
- `ntdll!NtClose` at `0x180003efc`
- `ntdll!NtClose` at `0x180003683`
- `ntdll!NtClose` at `0x180003698`
- `ntdll!NtClose` at `0x1800037f1`
- `ntdll!NtClose` at `0x180003e8d`
- `ntdll!NtClose` at `0x180003efc`
- `ntdll!NtOpenThreadToken` at `0x180003513`
- `ntdll!NtOpenThreadToken` at `0x180003513`
- `ntdll!NtOpenProcessToken` at `0x18000378e`
- `ntdll!NtOpenProcessToken` at `0x18000378e`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800038c9`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800038c9`
- `ntdll!DbgPrintEx` at `0x180003b4e`
- `ntdll!DbgPrintEx` at `0x180003e73`
- `ntdll!DbgPrintEx` at `0x180003b4e`
- `ntdll!DbgPrintEx` at `0x180003e73`
- `ntdll!NtWriteVirtualMemory` at `0x180003de4`
- `ntdll!NtWriteVirtualMemory` at `0x180003e30`
- `ntdll!NtWriteVirtualMemory` at `0x180003de4`
- `ntdll!NtWriteVirtualMemory` at `0x180003e30`
- `ntdll!NtUnmapViewOfSection` at `0x180003ed2`
- `ntdll!NtUnmapViewOfSection` at `0x180003ed2`
- `ntdll!RtlAllocateHeap` at `0x180003569`
- `ntdll!RtlAllocateHeap` at `0x180003af8`
- `ntdll!RtlAllocateHeap` at `0x180003569`
- `ntdll!RtlAllocateHeap` at `0x180003af8`
- `ntdll!RtlLengthRequiredSid` at `0x180003544`
- `ntdll!RtlLengthRequiredSid` at `0x180003544`
- `ntdll!NtMapViewOfSection` at `0x180003db4`
- `ntdll!NtMapViewOfSection` at `0x180003db4`
- `CSRSRV!CsrRevertToSelf` at `0x180003927`
- `CSRSRV!CsrRevertToSelf` at `0x180003949`
- `CSRSRV!CsrRevertToSelf` at `0x180003f15`
- `CSRSRV!CsrRevertToSelf` at `0x180003927`
- `CSRSRV!CsrRevertToSelf` at `0x180003949`
- `CSRSRV!CsrRevertToSelf` at `0x180003f15`
- `CSRSRV!CsrImpersonateClient` at `0x1800038e1`
- `CSRSRV!CsrImpersonateClient` at `0x180003bae`
- `CSRSRV!CsrImpersonateClient` at `0x1800038e1`
- `CSRSRV!CsrImpersonateClient` at `0x180003bae`

## string_xrefs

- `0x180003b40`: `SXS: BaseSrvSxsGetActivationContextGenerationFunction() returned STATUS_DLL_NOT_FOUND, propagating.\n`

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
  int v9; // esi
  int v10; // r12d
  char v11; // r15
  unsigned __int64 v12; // rax
  __int64 v13; // rcx
  unsigned __int64 v14; // rax
  NTSTATUS TokenILValue; // ebx
  ULONG v16; // r14d
  HANDLE *CsrClientThread; // r13
  NTSTATUS v18; // eax
  void *v19; // r15
  PSID *Heap; // rax
  PSID *v21; // rbx
  NTSTATUS v22; // esi
  int v23; // esi
  ULONG v24; // esi
  NTSTATUS v25; // eax
  __int16 v26; // bx
  unsigned __int16 v27; // ax
  char v28; // si
  int v29; // eax
  bool v30; // zf
  __int64 v31; // rcx
  int v32; // eax
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  int v35; // ecx
  int v36; // eax
  __int64 v37; // rdx
  unsigned __int16 v38; // cx
  __int64 v39; // rax
  PVOID v40; // rax
  int ActivationContextGenerationFunction; // eax
  int v42; // ecx
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
  HANDLE v58; // r14
  void *v59; // rdx
  __int16 v60; // ax
  SIZE_T v61; // rax
  NTSTATUS v62; // eax
  int v63; // eax
  ULONG TokenInformationLength; // [rsp+50h] [rbp-B0h] BYREF
  ULONG v65; // [rsp+54h] [rbp-ACh]
  ULONG v66; // [rsp+58h] [rbp-A8h] BYREF
  PVOID BaseAddress; // [rsp+60h] [rbp-A0h] BYREF
  ULONG v68; // [rsp+68h] [rbp-98h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-90h] BYREF
  void *Src[2]; // [rsp+78h] [rbp-88h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp-78h] BYREF
  union _LARGE_INTEGER SectionOffset; // [rsp+90h] [rbp-70h] BYREF
  ULONG_PTR ViewSize; // [rsp+98h] [rbp-68h] BYREF
  HANDLE v74; // [rsp+A0h] [rbp-60h]
  unsigned int (__fastcall *v75)(int *); // [rsp+A8h] [rbp-58h] BYREF
  HANDLE ProcessHandle; // [rsp+B0h] [rbp-50h]
  PVOID P; // [rsp+B8h] [rbp-48h]
  PVOID v78[2]; // [rsp+C0h] [rbp-40h] BYREF
  HANDLE *v79; // [rsp+D0h] [rbp-30h]
  __int128 v80; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v81; // [rsp+E8h] [rbp-18h]
  __int128 v82; // [rsp+F8h] [rbp-8h]
  __int64 v83; // [rsp+108h] [rbp+8h]
  _QWORD v84[2]; // [rsp+110h] [rbp+10h] BYREF
  HANDLE v85[2]; // [rsp+120h] [rbp+20h] BYREF
  HANDLE v86[2]; // [rsp+130h] [rbp+30h]
  _OWORD v87[4]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v88; // [rsp+180h] [rbp+80h]
  __int128 v89; // [rsp+190h] [rbp+90h]
  __int128 v90; // [rsp+1A0h] [rbp+A0h]
  __int128 v91; // [rsp+1B0h] [rbp+B0h]
  __int128 v92; // [rsp+1C0h] [rbp+C0h]
  __int128 v93; // [rsp+1D0h] [rbp+D0h]
  __int128 v94; // [rsp+1E0h] [rbp+E0h]
  __int128 v95; // [rsp+1F0h] [rbp+F0h]
  __int128 v96; // [rsp+200h] [rbp+100h]
  __int128 v97; // [rsp+210h] [rbp+110h]
  int v98; // [rsp+220h] [rbp+120h] BYREF
  __int16 v99; // [rsp+224h] [rbp+124h]
  __int64 v100; // [rsp+228h] [rbp+128h]
  __int64 v101; // [rsp+230h] [rbp+130h]
  __int64 v102; // [rsp+238h] [rbp+138h]
  __int64 v103[2]; // [rsp+240h] [rbp+140h] BYREF
  int v104; // [rsp+250h] [rbp+150h]
  __int64 v105[3]; // [rsp+258h] [rbp+158h] BYREF
  __int64 v106; // [rsp+270h] [rbp+170h]
  int v107; // [rsp+278h] [rbp+178h]
  HANDLE SectionHandle; // [rsp+280h] [rbp+180h] BYREF
  __int64 v109; // [rsp+288h] [rbp+188h] BYREF
  unsigned int v110; // [rsp+290h] [rbp+190h]
  unsigned int v111; // [rsp+294h] [rbp+194h] BYREF
  __int64 v112; // [rsp+298h] [rbp+198h] BYREF
  _BYTE v113[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  PVOID v114; // [rsp+3A8h] [rbp+2A8h]
  __int16 v115; // [rsp+3B0h] [rbp+2B0h]
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+3C0h] [rbp+2C0h] BYREF

  v79 = a5;
  SectionOffset = a4;
  v7 = SourceProcessHandle;
  ProcessHandle = a2;
  v74 = SourceProcessHandle;
  if ( !a3 )
    return 3221225485LL;
  v9 = *a3;
  if ( (*a3 & 0xD) == 0 )
    return 0;
  BaseAddress = 0;
  memset_0(&v98, 0, 0x198u);
  ViewSize = 0;
  v75 = 0;
  P = 0;
  v90 = 0;
  v91 = 0;
  v92 = 0;
  v93 = 0;
  v94 = 0;
  v95 = 0;
  v96 = 0;
  v97 = 0;
  if ( (v9 & 0x1C1) != 0x41 || (v10 = 1, *((_QWORD *)a3 + 22) == -1) )
    v10 = 0;
  v68 = 0;
  v84[0] = a3 + 22;
  v11 = 0;
  v84[1] = v78;
  v83 = 0;
  v12 = *((unsigned __int16 *)a3 + 4);
  memset(v87, 0, sizeof(v87));
  v88 = 0;
  v89 = 0;
  *(_OWORD *)v78 = 0;
  *(_OWORD *)v85 = 0;
  *(_OWORD *)v86 = 0;
  *(_OWORD *)Src = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  if ( (unsigned int)v12 < 4
    || (v13 = *((_QWORD *)a3 + 2), v14 = v12 >> 1, *(_WORD *)(v13 + 2 * v14 - 2))
    || *(_WORD *)(v13 + 2 * v14 - 4) )
  {
    TokenILValue = -1073741811;
    goto LABEL_153;
  }
  v65 = 0;
  TokenILValue = 0;
  if ( v10 )
  {
    if ( a4.QuadPart && (*(_BYTE *)(a4.QuadPart + 24) & 1) != 0 )
    {
      ++BaseSrvActCtxGenCount;
      v10 = 0;
      goto LABEL_61;
    }
    if ( (v9 & 0x3000) == 0x3000 )
    {
      ++BaseSrvActCtxGenCount;
      v10 = 0;
      goto LABEL_61;
    }
  }
  ++BaseSrvActCtxGenCount;
  if ( v10 )
  {
    TokenHandle = 0;
    Handle = 0;
    v16 = 0;
    CsrClientThread = (HANDLE *)NtCurrentTeb()->CsrClientThread;
    v66 = 0;
    v18 = NtOpenThreadToken(CsrClientThread[8], 8u, 0, &TokenHandle);
    if ( v18 < 0 )
    {
      if ( v18 != -1073741700 )
        goto LABEL_29;
      v23 = 0;
    }
    else
    {
      v19 = TokenHandle;
      *(_DWORD *)IdentifierAuthority.Value = 0;
      *(_WORD *)&IdentifierAuthority.Value[4] = 4096;
      TokenInformationLength = RtlLengthRequiredSid(1u) + 16;
      Heap = (PSID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, TokenInformationLength);
      v21 = Heap;
      if ( Heap )
      {
        *Heap = Heap + 2;
        v22 = RtlInitializeSid(Heap + 2, &IdentifierAuthority, 1u);
        if ( v22 >= 0 )
        {
          v22 = NtQueryInformationToken(v19, TokenIntegrityLevel, v21, TokenInformationLength, &TokenInformationLength);
          if ( v22 >= 0 )
            v16 = *RtlSubAuthoritySid(*v21, 0);
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v21);
      }
      else
      {
        v22 = -1073741801;
      }
      if ( v22 < 0 )
        goto LABEL_29;
      v23 = 1;
      TokenInformationLength = 0;
      *(_DWORD *)IdentifierAuthority.Value = 0;
      if ( NtQueryInformationToken(
             TokenHandle,
             TokenImpersonationLevel,
             &TokenInformationLength,
             4u,
             (PULONG)IdentifierAuthority.Value) < 0
        || TokenInformationLength != 2 && TokenInformationLength != 3 )
      {
        goto LABEL_29;
      }
    }
    if ( NtOpenProcessToken(*((HANDLE *)CsrClientThread[7] + 10), 8u, &Handle) >= 0 )
    {
      TokenILValue = GetTokenILValue(Handle, &v66);
      if ( TokenILValue >= 0 )
      {
        if ( v23 )
        {
          if ( v16 <= v66 )
          {
            v24 = v16;
            v65 = v16;
          }
          else
          {
            v10 = 0;
            v24 = 0;
          }
        }
        else
        {
          v24 = v66;
          v65 = v66;
        }
        goto LABEL_30;
      }
    }
LABEL_29:
    TokenILValue = 0;
    v10 = 0;
    v24 = 0;
LABEL_30:
    if ( TokenHandle )
      NtClose(TokenHandle);
    if ( Handle )
      NtClose(Handle);
    if ( v10 )
    {
      TokenILValue = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))BaseSrvSxsGetCacheKey)(
                       a3,
                       (union _LARGE_INTEGER)SectionOffset.QuadPart,
                       v87);
      if ( TokenILValue < 0 )
        goto LABEL_102;
      TokenILValue = BaseSrvActivationContextCacheLookupEntry(
                       v87,
                       &SectionHandle,
                       a3 + 50,
                       a3 + 53,
                       a3 + 58,
                       a3 + 60,
                       Src,
                       &v68);
      if ( (int)(TokenILValue + 0x80000000) >= 0 && TokenILValue != -1073741275 )
        goto LABEL_102;
      if ( SectionHandle && v68 < v24 )
      {
        TokenILValue = BaseSrvActivationContextCacheRemoveEntry(v87);
        if ( ((TokenILValue + 0x80000000) & 0x80000000) == 0 && TokenILValue != -1073741275 )
        {
          v11 = 0;
          goto LABEL_150;
        }
        v25 = NtClose(SectionHandle);
        SectionHandle = 0;
        TokenILValue = v25;
        if ( v25 < 0 )
        {
          v11 = 0;
          goto LABEL_150;
        }
      }
      else
      {
        v26 = (__int16)Src[0];
        if ( LOWORD(Src[0]) )
        {
          v27 = *((_WORD *)a3 + 109);
          if ( v27 )
          {
            if ( LOWORD(Src[0]) >= v27 )
            {
              *((_WORD *)a3 + 108) = 0;
            }
            else
            {
              memcpy_0(*((void **)a3 + 28), Src[1], LOWORD(Src[0]));
              *((_WORD *)a3 + 108) = v26;
            }
          }
        }
      }
      TokenILValue = 0;
    }
    v7 = v74;
    v11 = 0;
  }
LABEL_61:
  v28 = 0;
  if ( SectionHandle )
    goto LABEL_133;
  v29 = *a3;
  if ( (*a3 & 1) != 0 )
  {
    TokenILValue = BasepSxsCreateMemoryStream(v7, (__int64)v103);
    if ( TokenILValue < 0 )
      goto LABEL_150;
    v30 = *((_QWORD *)a3 + 22) == 1;
    v104 = 1;
    if ( v30 )
    {
      v33 = *((_OWORD *)a3 + 6);
      v80 = *((_OWORD *)a3 + 5);
      v34 = *((_OWORD *)a3 + 7);
      v81 = v33;
      *(_QWORD *)&v33 = *((_QWORD *)a3 + 16);
      v82 = v34;
      v83 = v33;
    }
    else
    {
      TokenILValue = RtlDosPathNameToNtPathName_U_WithStatus(*((_QWORD *)a3 + 12), v78, 0, 0);
      if ( TokenILValue < 0 )
        goto LABEL_150;
      v11 = CsrImpersonateClient(0);
      if ( !v11 )
        goto LABEL_149;
      v32 = BasepSxsCreateFileStreamEx(v31, v84, *a3, v85, &v80);
      TokenILValue = v32;
      if ( v32 >= 0 )
      {
        *a3 |= 2u;
        BYTE2(v80) = 5;
        if ( v10 )
          WORD1(v88) |= 1u;
      }
      else if ( !(unsigned int)BasepSxsIsStatusFileNotFoundEtc((unsigned int)v32) )
      {
        goto LABEL_150;
      }
      CsrRevertToSelf();
    }
    if ( (*(_BYTE *)a3 & 2) != 0 )
    {
      TokenILValue = BasepSxsCreateMemoryStream(v7, (__int64)v105);
      if ( TokenILValue < 0 )
        goto LABEL_102;
      if ( BYTE1(v80) && WORD4(v80) && (_QWORD)v81 )
      {
        v105[1] = v81;
        if ( BYTE1(v80) == 1 )
        {
          v104 = 2;
        }
        else if ( BYTE1(v80) == 2 )
        {
          v35 = v98;
          v104 = 3;
          goto LABEL_87;
        }
      }
    }
    v35 = v98;
  }
  else
  {
    v35 = v98 | 4;
    v98 |= 4u;
    if ( (v29 & 4) != 0 )
    {
      v35 |= 2u;
      v98 = v35;
    }
    v102 = *((_QWORD *)a3 + 20);
  }
LABEL_87:
  v36 = *a3;
  if ( (*a3 & 0x10) != 0 )
  {
    v35 |= 8u;
    v98 = v35;
  }
  if ( (v36 & 0x400) != 0 )
  {
    v35 |= 0x10u;
    v98 = v35;
  }
  if ( (v36 & 0x800) != 0 )
  {
    v35 |= 0x20u;
    v98 = v35;
  }
  if ( (v36 & 0x7000) == 0x7000 )
    v98 = v35 | 0x40;
  v37 = *((_QWORD *)a3 + 22);
  v38 = *((_WORD *)a3 + 109);
  v99 = *((_WORD *)a3 + 2);
  v100 = *((_QWORD *)a3 + 2);
  v39 = v106;
  if ( v37 != -1 )
    v39 = v37;
  v106 = v39;
  v101 = *((_QWORD *)a3 + 18);
  if ( !v38 )
  {
    if ( v37 != 1 )
      goto LABEL_105;
    v115 = 60;
    v40 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x78u);
    P = v40;
    if ( v40 )
    {
      Src[1] = v40;
      WORD1(Src[0]) = 120;
      goto LABEL_104;
    }
    TokenILValue = -1073741801;
LABEL_102:
    v11 = 0;
    goto LABEL_150;
  }
  v40 = (PVOID)*((_QWORD *)a3 + 28);
  *(_OWORD *)Src = *(_OWORD *)(a3 + 54);
  v115 = v38 >> 1;
LABEL_104:
  v114 = v40;
LABEL_105:
  ActivationContextGenerationFunction = BaseSrvSxsGetActivationContextGenerationFunction(&v75, &ViewSize);
  TokenILValue = ActivationContextGenerationFunction;
  if ( ActivationContextGenerationFunction == -1073741515 )
  {
    DbgPrintEx(
      0x33u,
      0,
      "SXS: BaseSrvSxsGetActivationContextGenerationFunction() returned STATUS_DLL_NOT_FOUND, propagating.\n");
    v11 = 0;
    goto LABEL_150;
  }
  v11 = 0;
  if ( ActivationContextGenerationFunction < 0 )
    goto LABEL_150;
  v42 = *((unsigned __int8 *)a3 + 25);
  if ( (_BYTE)v42 && *((_WORD *)a3 + 16) && *((_QWORD *)a3 + 5) )
  {
    v103[1] = *((_QWORD *)a3 + 5);
    v43 = v42 - 1;
    if ( v43 )
    {
      if ( v43 == 1 )
        v104 = 3;
    }
    else
    {
      v104 = 2;
    }
  }
  v11 = CsrImpersonateClient(0);
  if ( !v11 )
  {
LABEL_149:
    TokenILValue = -1073741659;
    goto LABEL_150;
  }
  if ( !v75(&v98) )
  {
    DbgPrintEx(0x33u, 3u, "SXS: Activation Context generation function failed.\n");
    TokenILValue = -1072365566;
    goto LABEL_150;
  }
  v44 = *a3;
  if ( (*a3 & 4) != 0 && ((v107 & 1) != 0 || (v107 & 2) != 0) )
  {
    TokenILValue = -1072365550;
    goto LABEL_150;
  }
  if ( v10 && ((v107 & 4) != 0 || (v107 & 8) != 0) )
    v10 = 0;
  v45 = v110;
  v46 = a3 + 60;
  v47 = 2;
  *((_QWORD *)a3 + 25) = v109;
  a3[52] = v45;
  a3[53] = v111;
  *((_QWORD *)a3 + 29) = v112;
  v48 = (__int128 *)v113;
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
  v28 = 1;
  *v46 = *(_DWORD *)v48;
  v57 = 2 * v115;
  *((_WORD *)a3 + 108) = 2 * v115;
  LOWORD(Src[0]) = v57;
  if ( !SectionHandle )
    goto LABEL_145;
  if ( v10 && (*((_QWORD *)a3 + 22) == 1 || (v44 & 2) == 0) )
  {
    TokenILValue = BaseSrvActivationContextCacheInsertEntry(v87, SectionHandle, &v109, &v111, &v112, v113, Src, v65);
    if ( TokenILValue < 0 )
    {
LABEL_150:
      if ( BaseAddress )
        NtUnmapViewOfSection(ProcessHandle, BaseAddress);
      goto LABEL_153;
    }
  }
  if ( SectionHandle )
  {
LABEL_133:
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
        goto LABEL_150;
      TokenILValue = NtWriteVirtualMemory(v58, *((PVOID *)a3 + 23), &BaseAddress, 8u, 0);
      if ( TokenILValue < 0 )
        goto LABEL_150;
      v59 = (void *)*((_QWORD *)a3 + 24);
      if ( v59 )
      {
        v60 = *((_WORD *)a3 + 2);
        if ( v60 == 10 || (v30 = v60 == 13, v61 = 8, v30) )
          v61 = 4;
        TokenILValue = NtWriteVirtualMemory(v58, v59, &BaseAddress, v61, 0);
        if ( TokenILValue < 0 )
          goto LABEL_150;
      }
    }
    if ( v79 )
    {
      *v79 = SectionHandle;
      SectionHandle = 0;
      goto LABEL_145;
    }
    v62 = NtClose(SectionHandle);
    SectionHandle = 0;
    TokenILValue = v62;
    if ( v62 >= 0 )
      goto LABEL_145;
    goto LABEL_150;
  }
LABEL_145:
  v63 = 0;
  if ( !v28 )
    v63 = TokenILValue;
  TokenILValue = v63;
  if ( v63 < 0 )
    goto LABEL_150;
  TokenILValue = 0;
  BaseAddress = 0;
LABEL_153:
  if ( SectionHandle )
    NtClose(SectionHandle);
  if ( v11 )
    CsrRevertToSelf();
  if ( (*(_BYTE *)a3 & 1) != 0 )
  {
    if ( v103[0] )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v103[0] + 16LL))(v103[0]);
      v103[0] = 0;
    }
    if ( v105[0] )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v105[0] + 16LL))(v105[0]);
      v105[0] = 0;
    }
  }
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( v85[0] )
    NtClose_0(v85[0]);
  if ( v86[0] )
    NtClose_0(v86[0]);
  if ( v86[1] )
    NtUnmapViewOfSection_0((HANDLE)0xFFFFFFFFFFFFFFFFLL, v86[1]);
  if ( v78[1] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v78[1]);
  return (unsigned int)TokenILValue;
}

```

## disassembly

```asm
0x180003310  push    rbp
0x180003312  push    rbx
0x180003313  push    rdi
0x180003314  push    r13
0x180003316  push    r14
0x180003318  lea     rbp, [rsp-2F0h]
0x180003320  sub     rsp, 3F0h
0x180003327  mov     rax, cs:__security_cookie
0x18000332e  xor     rax, rsp
0x180003331  mov     [rbp+310h+var_48], rax
0x180003338  mov     rax, [rbp+310h+arg_20]
0x18000333f  mov     r14, r9
0x180003342  mov     [rbp+310h+var_340], rax
0x180003346  mov     rdi, r8
0x180003349  mov     qword ptr [rbp+310h+var_380], r9
0x18000334d  mov     r13, rcx
0x180003350  mov     [rbp+310h+ProcessHandle], rdx
0x180003354  mov     [rbp+310h+var_370], rcx
0x180003358  test    r8, r8
0x18000335b  jnz     short loc_180003367
0x18000335d  mov     eax, 0C000000Dh
0x180003362  jmp     loc_180003FEC
0x180003367  mov     [rsp+410h+var_28], rsi
0x18000336f  mov     esi, [r8]
0x180003372  test    sil, 0Dh
0x180003376  jnz     short loc_18000337F
0x180003378  xor     eax, eax
0x18000337a  jmp     loc_180003FE4
0x18000337f  mov     [rsp+410h+var_30], r12
0x180003387  lea     rcx, [rbp+310h+var_1F0]; void *
0x18000338e  xor     edx, edx; Val
0x180003390  mov     [rsp+410h+var_38], r15
0x180003398  mov     r8d, 198h; Size
0x18000339e  mov     [rsp+410h+BaseAddress], 0
0x1800033a7  call    memset_0
0x1800033ac  xor     edx, edx
0x1800033ae  xorps   xmm0, xmm0
0x1800033b1  xorps   xmm1, xmm1
0x1800033b4  mov     [rbp+310h+var_378], rdx
0x1800033b8  mov     eax, esi
0x1800033ba  mov     [rbp+310h+var_368], rdx
0x1800033be  and     eax, 1C1h
0x1800033c3  mov     [rbp+310h+P], rdx
0x1800033c7  movups  [rbp+310h+var_270], xmm0
0x1800033ce  movups  [rbp+310h+var_260], xmm0
0x1800033d5  movups  [rbp+310h+var_250], xmm0
0x1800033dc  movups  [rbp+310h+var_240], xmm0
0x1800033e3  movups  [rbp+310h+var_230], xmm1
0x1800033ea  movups  [rbp+310h+var_220], xmm1
0x1800033f1  movups  [rbp+310h+var_210], xmm1
0x1800033f8  movups  [rbp+310h+var_200], xmm1
0x1800033ff  cmp     eax, 41h ; 'A'
0x180003402  jnz     short loc_180003414
0x180003404  cmp     qword ptr [rdi+0B0h], 0FFFFFFFFFFFFFFFFh
0x18000340c  mov     r12d, 1
0x180003412  jnz     short loc_180003417
0x180003414  mov     r12d, edx
0x180003417  lea     rax, [rdi+58h]
0x18000341b  mov     [rsp+410h+var_3A8], edx
0x18000341f  mov     [rbp+310h+var_300], rax
0x180003423  xor     r15b, r15b
0x180003426  lea     rax, [rbp+310h+var_350]
0x18000342a  mov     [rbp+310h+var_2F8], rax
0x18000342e  xor     eax, eax
0x180003430  mov     [rbp+310h+var_308], rax
0x180003434  movzx   eax, word ptr [rdi+8]
0x180003438  movups  [rbp+310h+var_2D0], xmm0
0x18000343c  movups  [rbp+310h+var_2C0], xmm0
0x180003440  movups  [rbp+310h+var_2B0], xmm0
0x180003444  movups  [rbp+310h+var_2A0], xmm0
0x180003448  movups  [rbp+310h+var_290], xmm0
0x18000344f  movups  [rbp+310h+var_280], xmm0
0x180003456  movups  xmmword ptr [rbp+310h+var_350], xmm0
0x18000345a  movups  xmmword ptr [rbp+310h+var_2F0], xmm0
0x18000345e  movups  xmmword ptr [rbp+310h+var_2E0], xmm0
0x180003462  movups  xmmword ptr [rsp+410h+Src], xmm0
0x180003467  movups  [rbp+310h+var_338], xmm1
0x18000346b  movups  [rbp+310h+var_328], xmm1
0x18000346f  movups  [rbp+310h+var_318], xmm1
0x180003473  cmp     eax, 4
0x180003476  jb      loc_180003EE0
0x18000347c  mov     rcx, [rdi+10h]
0x180003480  shr     rax, 1
0x180003483  cmp     [rcx+rax*2-2], dx
0x180003488  jnz     loc_180003EE0
0x18000348e  cmp     [rcx+rax*2-4], dx
0x180003493  jnz     loc_180003EE0
0x180003499  mov     [rsp+410h+var_3BC], edx
0x18000349d  mov     ebx, edx
0x18000349f  test    r12d, r12d
0x1800034a2  jz      short loc_1800034DA
0x1800034a4  test    r14, r14
0x1800034a7  jz      short loc_1800034BE
0x1800034a9  test    byte ptr [r14+18h], 1
0x1800034ae  jz      short loc_1800034BE
0x1800034b0  inc     cs:BaseSrvActCtxGenCount
0x1800034b6  mov     r12d, edx
0x1800034b9  jmp     loc_18000385F
0x1800034be  and     esi, 3000h
0x1800034c4  cmp     esi, 3000h
0x1800034ca  jnz     short loc_1800034DA
0x1800034cc  inc     cs:BaseSrvActCtxGenCount
0x1800034d2  mov     r12d, edx
0x1800034d5  jmp     loc_18000385F
0x1800034da  inc     cs:BaseSrvActCtxGenCount
0x1800034e0  test    r12d, r12d
0x1800034e3  jz      loc_18000385F
0x1800034e9  mov     [rsp+410h+TokenHandle], rdx
0x1800034ee  lea     r9, [rsp+410h+TokenHandle]; TokenHandle
0x1800034f3  mov     [rbp+310h+Handle], rdx
0x1800034f7  mov     r14d, edx
0x1800034fa  mov     r13, gs:70h
0x180003503  xor     r8d, r8d; OpenAsSelf
0x180003506  mov     [rsp+410h+var_3B8], edx
0x18000350a  mov     edx, 8; DesiredAccess
0x18000350f  mov     rcx, [r13+40h]; ThreadHandle
0x180003513  call    cs:__imp_NtOpenThreadToken
0x18000351a  nop     dword ptr [rax+rax+00h]
0x18000351f  test    eax, eax
0x180003521  js      loc_180003770
0x180003527  mov     r15, [rsp+410h+TokenHandle]
0x18000352c  mov     ecx, 1; SubAuthorityCount
0x180003531  mov     [rsp+410h+TokenInformationLength], ebx
0x180003535  mov     dword ptr [rbp+310h+IdentifierAuthority.Value], ebx
0x18000353b  mov     word ptr [rbp+310h+IdentifierAuthority.Value+4], 1000h
0x180003544  call    cs:__imp_RtlLengthRequiredSid
0x18000354b  nop     dword ptr [rax+rax+00h]
0x180003550  add     eax, 10h
0x180003553  xor     edx, edx; Flags
0x180003555  mov     [rsp+410h+TokenInformationLength], eax
0x180003559  mov     rcx, gs:60h
0x180003562  mov     r8d, eax; Size
0x180003565  mov     rcx, [rcx+30h]; HeapHandle
0x180003569  call    cs:__imp_RtlAllocateHeap
0x180003570  nop     dword ptr [rax+rax+00h]
0x180003575  mov     rbx, rax
0x180003578  test    rax, rax
0x18000357b  jnz     short loc_180003587
0x18000357d  mov     esi, 0C0000017h
0x180003582  jmp     loc_180003608
0x180003587  lea     rcx, [rax+10h]; Sid
0x18000358b  mov     r8b, 1; SubAuthorityCount
0x18000358e  lea     rdx, [rbp+310h+IdentifierAuthority]; IdentifierAuthority
0x180003595  mov     [rax], rcx
0x180003598  call    cs:__imp_RtlInitializeSid
0x18000359f  nop     dword ptr [rax+rax+00h]
0x1800035a4  mov     esi, eax
0x1800035a6  test    eax, eax
0x1800035a8  js      short loc_1800035EA
0x1800035aa  mov     r9d, [rsp+410h+TokenInformationLength]; TokenInformationLength
0x1800035af  lea     rax, [rsp+410h+TokenInformationLength]
0x1800035b4  mov     r8, rbx; TokenInformation
0x1800035b7  mov     [rsp+410h+ReturnLength], rax; ReturnLength
0x1800035bc  mov     edx, 19h; TokenInformationClass
0x1800035c1  mov     rcx, r15; TokenHandle
0x1800035c4  call    cs:__imp_NtQueryInformationToken
0x1800035cb  nop     dword ptr [rax+rax+00h]
0x1800035d0  mov     esi, eax
0x1800035d2  test    eax, eax
0x1800035d4  js      short loc_1800035EA
0x1800035d6  mov     rcx, [rbx]; Sid
0x1800035d9  xor     edx, edx; SubAuthority
0x1800035db  call    cs:__imp_RtlSubAuthoritySid
0x1800035e2  nop     dword ptr [rax+rax+00h]
0x1800035e7  mov     r14d, [rax]
0x1800035ea  mov     rcx, gs:60h
0x1800035f3  mov     r8, rbx; P
0x1800035f6  xor     edx, edx; Flags
0x1800035f8  mov     rcx, [rcx+30h]; HeapHandle
0x1800035fc  call    cs:__imp_RtlFreeHeap
0x180003603  nop     dword ptr [rax+rax+00h]
0x180003608  test    esi, esi
0x18000360a  js      short loc_180003672
0x18000360c  not     esi
0x18000360e  shr     esi, 1Fh
0x180003611  test    esi, esi
0x180003613  jz      loc_18000377D
0x180003619  mov     rcx, [rsp+410h+TokenHandle]; TokenHandle
0x18000361e  lea     rax, [rbp+310h+IdentifierAuthority]
0x180003625  mov     r9d, 4; TokenInformationLength
0x18000362b  mov     [rsp+410h+ReturnLength], rax; ReturnLength
0x180003630  lea     r8, [rsp+410h+TokenInformationLength]; TokenInformation
0x180003635  mov     [rsp+410h+TokenInformationLength], 0
0x18000363d  mov     edx, 9; TokenInformationClass
0x180003642  mov     dword ptr [rbp+310h+IdentifierAuthority.Value], 0
0x18000364c  call    cs:__imp_NtQueryInformationToken
0x180003653  nop     dword ptr [rax+rax+00h]
0x180003658  test    eax, eax
0x18000365a  js      short loc_180003672
0x18000365c  mov     eax, [rsp+410h+TokenInformationLength]
0x180003660  cmp     eax, 2
0x180003663  jz      loc_18000377D
0x180003669  cmp     eax, 3
0x18000366c  jz      loc_18000377D
0x180003672  xor     ebx, ebx
0x180003674  xor     r12d, r12d
0x180003677  mov     esi, ebx
0x180003679  mov     rcx, [rsp+410h+TokenHandle]; Handle
0x18000367e  test    rcx, rcx
0x180003681  jz      short loc_18000368F
0x180003683  call    cs:__imp_NtClose
0x18000368a  nop     dword ptr [rax+rax+00h]
0x18000368f  mov     rcx, [rbp+310h+Handle]; Handle
0x180003693  test    rcx, rcx
0x180003696  jz      short loc_1800036A4
0x180003698  call    cs:__imp_NtClose
0x18000369f  nop     dword ptr [rax+rax+00h]
0x1800036a4  test    r12d, r12d
0x1800036a7  jz      loc_180003858
0x1800036ad  mov     rdx, qword ptr [rbp+310h+var_380]
0x1800036b1  lea     r8, [rbp+310h+var_2D0]
0x1800036b5  mov     rcx, rdi
0x1800036b8  call    BaseSrvSxsGetCacheKey
0x1800036bd  mov     ebx, eax
0x1800036bf  test    eax, eax
0x1800036c1  js      loc_180003B12
0x1800036c7  lea     rdx, [rsp+410h+var_3A8]
0x1800036cc  mov     qword ptr [rsp+410h+InheritDisposition], rdx
0x1800036d1  lea     rax, [rdi+0F0h]
0x1800036d8  lea     rdx, [rsp+410h+Src]
0x1800036dd  mov     [rsp+410h+ViewSize], rdx
0x1800036e2  lea     rcx, [rdi+0E8h]
0x1800036e9  mov     [rsp+410h+SectionOffset], rax
0x1800036ee  lea     r9, [rdi+0D4h]
0x1800036f5  mov     [rsp+410h+ReturnLength], rcx
0x1800036fa  lea     r8, [rdi+0C8h]
0x180003701  lea     rcx, [rbp+310h+var_2D0]
0x180003705  lea     rdx, [rbp+310h+SectionHandle]
0x18000370c  call    BaseSrvActivationContextCacheLookupEntry
0x180003711  mov     r14d, 80000000h
0x180003717  mov     ebx, eax
0x180003719  add     eax, r14d
0x18000371c  test    r14d, eax
0x18000371f  jnz     short loc_18000372D
0x180003721  cmp     ebx, 0C0000225h
0x180003727  jnz     loc_180003B12
0x18000372d  cmp     [rbp+310h+SectionHandle], 0
0x180003735  jz      loc_180003816
0x18000373b  cmp     [rsp+410h+var_3A8], esi
0x18000373f  jnb     loc_180003816
0x180003745  lea     rcx, [rbp+310h+var_2D0]
0x180003749  call    BaseSrvActivationContextCacheRemoveEntry
0x18000374e  mov     ebx, eax
0x180003750  add     eax, r14d
0x180003753  test    r14d, eax
0x180003756  jnz     loc_1800037EA
0x18000375c  cmp     ebx, 0C0000225h
0x180003762  jz      loc_1800037EA
0x180003768  xor     r15b, r15b
0x18000376b  jmp     loc_180003EC4
0x180003770  cmp     eax, 0C000007Ch
0x180003775  jnz     loc_180003672
0x18000377b  xor     esi, esi
0x18000377d  mov     rcx, [r13+38h]
0x180003781  lea     r8, [rbp+310h+Handle]; TokenHandle
0x180003785  mov     edx, 8; DesiredAccess
0x18000378a  mov     rcx, [rcx+50h]; ProcessHandle
0x18000378e  call    cs:__imp_NtOpenProcessToken
0x180003795  nop     dword ptr [rax+rax+00h]
0x18000379a  test    eax, eax
0x18000379c  js      loc_180003672
0x1800037a2  mov     rcx, [rbp+310h+Handle]
0x1800037a6  lea     rdx, [rsp+410h+var_3B8]
0x1800037ab  call    GetTokenILValue
0x1800037b0  mov     ebx, eax
0x1800037b2  test    eax, eax
0x1800037b4  js      loc_180003672
0x1800037ba  test    esi, esi
0x1800037bc  jz      short loc_1800037DD
0x1800037be  cmp     r14d, [rsp+410h+var_3B8]
0x1800037c3  jbe     short loc_1800037D0
0x1800037c5  xor     r12d, r12d
0x1800037c8  mov     esi, r12d
0x1800037cb  jmp     loc_180003679
0x1800037d0  mov     esi, r14d
0x1800037d3  mov     [rsp+410h+var_3BC], r14d
0x1800037d8  jmp     loc_180003679
0x1800037dd  mov     esi, [rsp+410h+var_3B8]
0x1800037e1  mov     [rsp+410h+var_3BC], esi
0x1800037e5  jmp     loc_180003679
0x1800037ea  mov     rcx, [rbp+310h+SectionHandle]; Handle
0x1800037f1  call    cs:__imp_NtClose
0x1800037f8  nop     dword ptr [rax+rax+00h]
0x1800037fd  mov     [rbp+310h+SectionHandle], 0
0x180003808  mov     ebx, eax
0x18000380a  test    eax, eax
0x18000380c  jns     short loc_180003856
0x18000380e  xor     r15b, r15b
0x180003811  jmp     loc_180003EC4
0x180003816  movzx   ebx, word ptr [rsp+410h+Src]
0x18000381b  test    bx, bx
0x18000381e  jz      short loc_180003856
0x180003820  movzx   eax, word ptr [rdi+0DAh]
0x180003827  test    ax, ax
0x18000382a  jz      short loc_180003856
0x18000382c  cmp     bx, ax
0x18000382f  jnb     short loc_18000384D
0x180003831  mov     rdx, [rbp+310h+Src+8]; Src
0x180003835  mov     r8d, ebx; Size
0x180003838  mov     rcx, [rdi+0E0h]; void *
  ... truncated ...
```
