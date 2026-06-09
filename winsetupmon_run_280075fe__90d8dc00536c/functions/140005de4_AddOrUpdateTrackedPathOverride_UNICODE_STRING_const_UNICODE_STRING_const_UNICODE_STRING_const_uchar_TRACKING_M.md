# AddOrUpdateTrackedPathOverride(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar,_TRACKING_MODE)

- ea: `0x140005de4`
- end: `0x14000656f`
- name: `?AddOrUpdateTrackedPathOverride@@YAJPEBU_UNICODE_STRING@@00EW4_TRACKING_MODE@@@Z`
- size: `1931`
- prototype: `int __high(const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, unsigned __int8, enum _TRACKING_MODE)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, installer_update`

## callers

- `0x140001a94`
- `0x14001e2ec`

## callees

- `0x140003944`
- `0x140005de4`
- `0x14000dd24`
- `0x14000e1d0`
- `0x14000fd40`

## import_xrefs

- `ntoskrnl!FsRtlDissectName` at `0x14000623b`
- `ntoskrnl!FsRtlDissectName` at `0x14000636a`
- `ntoskrnl!FsRtlDissectName` at `0x1400063f2`
- `ntoskrnl!FsRtlDissectName` at `0x14000652b`
- `ntoskrnl!FsRtlDissectName` at `0x14000623b`
- `ntoskrnl!FsRtlDissectName` at `0x14000636a`
- `ntoskrnl!FsRtlDissectName` at `0x1400063f2`
- `ntoskrnl!FsRtlDissectName` at `0x14000652b`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x140005f1e`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x140005f1e`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x14000624f`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x140006406`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x14000624f`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x140006406`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x1400062b4`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140006475`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x1400062b4`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140006475`
- `ntoskrnl!ExReleaseFastMutex` at `0x140005f58`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000655e`
- `ntoskrnl!ExReleaseFastMutex` at `0x140005f58`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000655e`
- `ntoskrnl!ExAcquireFastMutex` at `0x140005ee6`
- `ntoskrnl!ExAcquireFastMutex` at `0x140005ee6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005f7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005f99`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005fb7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005fd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005fed`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006009`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006027`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400060e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006100`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000611e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000613c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005f7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005f99`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005fb7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005fd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005fed`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006009`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006027`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400060e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006100`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000611e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000613c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400061a9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400062ef`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400064c0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400061a9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400062ef`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400064c0`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140005e89`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140005f01`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140006076`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000615f`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140005e89`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140005f01`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140006076`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000615f`

## string_xrefs

- `0x140005e3b`: `Failed to convert path [%wZ] to NT (0x%08X)`
- `0x140005f35`: `Path [%wZ] not being tracked; cannot add process [%wZ]`

## pseudocode

```c
__int64 __fastcall AddOrUpdateTrackedPathOverride(
        const UNICODE_STRING *a1,
        const UNICODE_STRING *a2,
        const UNICODE_STRING *a3,
        char a4,
        unsigned int a5)
{
  int NtPath; // eax
  char *v9; // rdi
  int v10; // esi
  const UNICODE_STRING *v11; // r8
  BOOLEAN i; // dl
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  PUNICODE_PREFIX_TABLE_ENTRY v14; // r13
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  void *v18; // rcx
  struct _RTL_SPLAY_LINKS *Parent; // rbx
  struct _RTL_SPLAY_LINKS *v21; // r14
  const UNICODE_STRING *p_LeftChild; // rcx
  bool v23; // zf
  const UNICODE_STRING *p_RightChild; // rcx
  char v25; // al
  struct _RTL_SPLAY_LINKS *RightChild; // rcx
  struct _RTL_SPLAY_LINKS *v27; // rcx
  struct _RTL_SPLAY_LINKS *LeftChild; // rcx
  struct _RTL_SPLAY_LINKS *v29; // rcx
  char *PoolWithTag; // rax
  char *v31; // r14
  UNICODE_STRING v32; // xmm1
  BOOLEAN DoesNameContainWildCards; // bl
  __int64 v34; // rbx
  WCHAR v35; // ax
  SIZE_T v36; // r15
  PVOID v37; // rbx
  unsigned int v38; // ebx
  struct _UNICODE_STRING v39; // xmm0
  struct _UNICODE_STRING *v40; // rdx
  UNICODE_STRING v41; // xmm1
  BOOLEAN v42; // bl
  int v43; // ecx
  __int64 v44; // rbx
  WCHAR v45; // ax
  unsigned int v46; // eax
  SIZE_T v47; // r15
  PVOID v48; // rbx
  unsigned int v49; // ebx
  struct _UNICODE_STRING v50; // xmm0
  struct _UNICODE_STRING *v51; // rdx
  PVOID P[2]; // [rsp+20h] [rbp-50h] BYREF
  struct _UNICODE_STRING RemainingName; // [rsp+30h] [rbp-40h] BYREF
  UNICODE_STRING String2; // [rsp+40h] [rbp-30h] BYREF
  struct _UNICODE_STRING FirstName; // [rsp+50h] [rbp-20h] BYREF
  UNICODE_STRING Path; // [rsp+60h] [rbp-10h] BYREF

  String2 = 0;
  RemainingName = 0;
  *(_OWORD *)P = 0;
  NtPath = GetNtPath(a1, &String2, &RemainingName);
  v9 = 0;
  v10 = NtPath;
  if ( NtPath < 0 )
  {
    v11 = a1;
LABEL_3:
    WriteLogMessage(3, L"Failed to convert path [%wZ] to NT (0x%08X)", v11, (unsigned int)NtPath, P[0]);
    goto LABEL_29;
  }
  if ( String2.Length >= 2u && String2.Buffer[((unsigned __int64)String2.Length >> 1) - 1] == 92 )
    String2.Length -= 2;
  if ( a2 )
  {
    if ( RtlEqualUnicodeString(a2, &stru_1400123F0, 1u) )
    {
      v10 = Duplicate(&stru_1400123F0, (PUNICODE_STRING)P);
      if ( v10 < 0 )
      {
        WriteLogMessage(3, L"Failed to duplicate system process name");
        goto LABEL_29;
      }
    }
    else
    {
      NtPath = GetNtPath(a2, (PUNICODE_STRING)P, &RemainingName);
      v10 = NtPath;
      if ( NtPath < 0 )
      {
        v11 = a2;
        goto LABEL_3;
      }
    }
  }
  ExAcquireFastMutex(&stru_140019468);
  for ( i = 1; ; i = 0 )
  {
    UnicodePrefix = RtlNextUnicodePrefix(&g_TrackingInfo, i);
    v14 = UnicodePrefix;
    if ( !UnicodePrefix )
    {
      v10 = -1073741766;
      WriteLogMessage(3, L"Path [%wZ] not being tracked; cannot add process [%wZ]", a1, a2);
LABEL_18:
      a2 = 0;
LABEL_19:
      ExReleaseFastMutex(&stru_140019468);
      if ( v9 )
      {
        v15 = (void *)*((_QWORD *)v9 + 8);
        if ( v15 )
        {
          ExFreePoolWithTag(v15, 0x6E6D7377u);
          *((_QWORD *)v9 + 8) = a2;
        }
        v16 = (void *)*((_QWORD *)v9 + 6);
        if ( v16 )
        {
          ExFreePoolWithTag(v16, 0x6E6D7377u);
          *((_QWORD *)v9 + 6) = a2;
        }
        v17 = (void *)*((_QWORD *)v9 + 4);
        if ( v17 )
        {
          ExFreePoolWithTag(v17, 0x6E6D7377u);
          *((_QWORD *)v9 + 4) = a2;
        }
        v18 = (void *)*((_QWORD *)v9 + 2);
        if ( v18 )
        {
          ExFreePoolWithTag(v18, 0x6E6D7377u);
          *((_QWORD *)v9 + 2) = a2;
        }
        ExFreePoolWithTag(v9, 0x6E6D7377u);
      }
      goto LABEL_29;
    }
    if ( RtlEqualUnicodeString((PCUNICODE_STRING)&UnicodePrefix[1], &String2, 1u) )
      break;
  }
  Parent = v14[1].Links.Parent;
  v21 = 0;
  while ( Parent )
  {
    p_LeftChild = (const UNICODE_STRING *)&Parent->LeftChild;
    v23 = LOWORD(P[0]) == 0;
    if ( !LOWORD(P[0]) )
    {
      if ( !p_LeftChild->Length )
        goto LABEL_40;
      v23 = LOWORD(P[0]) == 0;
    }
    if ( !v23 && RtlEqualUnicodeString(p_LeftChild, (PCUNICODE_STRING)P, 1u) )
LABEL_40:
      LOBYTE(v9) = 1;
    p_RightChild = (const UNICODE_STRING *)&Parent[1].RightChild;
    if ( a3 )
    {
      if ( !RtlEqualUnicodeString(p_RightChild, a3, 1u) )
      {
LABEL_43:
        v25 = 0;
        goto LABEL_44;
      }
    }
    else if ( p_RightChild->Length )
    {
      goto LABEL_43;
    }
    v25 = 1;
LABEL_44:
    if ( !(_BYTE)v9 )
    {
      LOBYTE(v9) = 0;
LABEL_63:
      if ( !v14[1].Links.Parent )
        v14[1].Links.Parent = Parent;
      goto LABEL_65;
    }
    LOBYTE(v9) = 0;
    if ( !v25 )
      goto LABEL_63;
    if ( a4 == LOBYTE(Parent[3].Parent) && a5 == HIDWORD(Parent[3].Parent) )
      goto LABEL_120;
    if ( Parent == v14[1].Links.Parent )
      v14[1].Links.Parent = 0;
    RightChild = Parent[2].RightChild;
    if ( RightChild )
    {
      ExFreePoolWithTag(RightChild, 0x6E6D7377u);
      Parent[2].RightChild = 0;
    }
    v27 = Parent[2].Parent;
    if ( v27 )
    {
      ExFreePoolWithTag(v27, 0x6E6D7377u);
      Parent[2].Parent = 0;
    }
    LeftChild = Parent[1].LeftChild;
    if ( LeftChild )
    {
      ExFreePoolWithTag(LeftChild, 0x6E6D7377u);
      Parent[1].LeftChild = 0;
    }
    v29 = Parent->RightChild;
    if ( v29 )
    {
      ExFreePoolWithTag(v29, 0x6E6D7377u);
      Parent->RightChild = 0;
    }
    if ( v21 )
      v21->Parent = Parent->Parent;
LABEL_65:
    v21 = Parent;
    Parent = Parent->Parent;
  }
  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1025, 0x50u, 0x6E6D7377u);
  v31 = PoolWithTag;
  if ( ExPoolZeroingNativelySupported || !PoolWithTag )
  {
    v9 = PoolWithTag;
    if ( !PoolWithTag )
    {
      WriteLogMessage(3, L"Failed to allocate memory for the process list entry");
      v10 = -1073741670;
      goto LABEL_18;
    }
  }
  else
  {
    memset(PoolWithTag, 0, 0x50u);
    v9 = v31;
  }
  if ( LOWORD(P[0]) )
  {
    *(_OWORD *)(v31 + 8) = *(_OWORD *)P;
    *(_OWORD *)P = 0;
  }
  *((_DWORD *)v31 + 6) = 0;
  if ( a2 )
  {
    a2 = 0;
    DoesNameContainWildCards = 0;
    RemainingName = *(struct _UNICODE_STRING *)(v31 + 8);
    v32 = RemainingName;
    if ( !(unsigned __int16)_mm_cvtsi128_si32((__m128i)RemainingName) )
      goto LABEL_92;
    while ( 1 )
    {
      Path = v32;
      FirstName = 0;
      FsRtlDissectName(&Path, &FirstName, &RemainingName);
      if ( !DoesNameContainWildCards )
        DoesNameContainWildCards = FsRtlDoesNameContainWildCards(&FirstName);
      ++*((_DWORD *)v31 + 6);
      if ( !RemainingName.Length )
        break;
      v32 = RemainingName;
    }
    if ( DoesNameContainWildCards )
    {
      if ( (*((_WORD *)v9 + 4) & 0xFFFE) != 0 )
      {
        do
        {
          v34 = (unsigned int)a2;
          v35 = RtlUpcaseUnicodeChar(*(_WORD *)(*((_QWORD *)v31 + 2) + 2LL * (unsigned int)a2));
          LODWORD(a2) = (_DWORD)a2 + 1;
          *(_WORD *)(*((_QWORD *)v31 + 2) + 2 * v34) = v35;
        }
        while ( (unsigned int)a2 < *((unsigned __int16 *)v31 + 4) >> 1 );
      }
      v36 = 16LL * *((unsigned int *)v9 + 6);
      v37 = ExAllocatePoolWithTag((POOL_TYPE)1025, v36, 0x6E6D7377u);
      if ( !ExPoolZeroingNativelySupported && v37 )
        memset(v37, 0, v36);
      a2 = 0;
      *((_QWORD *)v9 + 4) = v37;
      if ( !v37 )
      {
        WriteLogMessage(3, L"Failed to allocate memory for the process ProcessParts array");
LABEL_88:
        v10 = -1073741670;
        goto LABEL_19;
      }
      v38 = 0;
      v39 = *(struct _UNICODE_STRING *)(v31 + 8);
      RemainingName = v39;
      if ( *((_DWORD *)v31 + 6) )
      {
        while ( 1 )
        {
          v40 = (struct _UNICODE_STRING *)(*((_QWORD *)v9 + 4) + 16LL * v38);
          Path = v39;
          FsRtlDissectName(&Path, v40, &RemainingName);
          if ( ++v38 >= *((_DWORD *)v31 + 6) )
            break;
          v39 = RemainingName;
        }
      }
    }
    else
    {
LABEL_92:
      *((_DWORD *)v31 + 6) = 0;
    }
  }
  if ( a3 )
  {
    v10 = Duplicate(a3, (PUNICODE_STRING)(v9 + 40));
    if ( v10 < 0 )
    {
      WriteLogMessage(3, L"Failed to duplicate the new Pattern");
      goto LABEL_19;
    }
  }
  *((_DWORD *)v9 + 14) = (_DWORD)a2;
  if ( a3 )
  {
    v42 = (unsigned __int8)a2;
    RemainingName = *(struct _UNICODE_STRING *)(v9 + 40);
    v41 = RemainingName;
    if ( (unsigned __int16)_mm_cvtsi128_si32((__m128i)RemainingName) )
    {
      while ( 1 )
      {
        Path = v41;
        FirstName = 0;
        FsRtlDissectName(&Path, &FirstName, &RemainingName);
        if ( !v42 )
          v42 = FsRtlDoesNameContainWildCards(&FirstName);
        v43 = *((_DWORD *)v9 + 14) + 1;
        *((_DWORD *)v9 + 14) = v43;
        if ( RemainingName.Length <= (unsigned __int16)a2 )
          break;
        v41 = RemainingName;
      }
    }
    else
    {
      v43 = (int)a2;
    }
    if ( a4 == (_BYTE)a2 )
    {
      if ( !v42 )
        goto LABEL_107;
      goto LABEL_108;
    }
    if ( v43 != 1 )
    {
      WriteLogMessage(3, L"Pattern cannot have multiple parts when it is a file");
      v10 = -1073741619;
      goto LABEL_19;
    }
LABEL_107:
    *((_DWORD *)v9 + 14) = (_DWORD)a2;
    if ( v42 )
    {
LABEL_108:
      if ( (*((_WORD *)v9 + 20) & 0xFFFE) != 0 )
      {
        do
        {
          v44 = (unsigned int)a2;
          v45 = RtlUpcaseUnicodeChar(*(_WORD *)(*((_QWORD *)v31 + 6) + 2LL * (unsigned int)a2));
          LODWORD(a2) = (_DWORD)a2 + 1;
          *(_WORD *)(*((_QWORD *)v31 + 6) + 2 * v44) = v45;
        }
        while ( (unsigned int)a2 < *((unsigned __int16 *)v31 + 20) >> 1 );
      }
    }
    v46 = *((_DWORD *)v9 + 14);
    v9[72] = a4;
    if ( v46 )
    {
      v47 = 16LL * v46;
      v48 = ExAllocatePoolWithTag((POOL_TYPE)1025, v47, 0x6E6D7377u);
      if ( !ExPoolZeroingNativelySupported && v48 )
        memset(v48, 0, v47);
      a2 = 0;
      *((_QWORD *)v9 + 8) = v48;
      if ( !v48 )
      {
        WriteLogMessage(3, L"Failed to allocate memory for the pattern PatternParts array");
        goto LABEL_88;
      }
      v49 = 0;
      v50 = *(struct _UNICODE_STRING *)(v9 + 40);
      RemainingName = v50;
      if ( *((_DWORD *)v9 + 14) )
      {
        while ( 1 )
        {
          v51 = (struct _UNICODE_STRING *)(*((_QWORD *)v9 + 8) + 16LL * v49);
          Path = v50;
          FsRtlDissectName(&Path, v51, &RemainingName);
          if ( ++v49 >= *((_DWORD *)v9 + 14) )
            break;
          v50 = RemainingName;
        }
      }
    }
  }
  *((_DWORD *)v9 + 19) = a5;
  *(_QWORD *)v31 = v14[1].Links.Parent;
  v14[1].Links.Parent = (struct _RTL_SPLAY_LINKS *)v9;
LABEL_120:
  ExReleaseFastMutex(&stru_140019468);
LABEL_29:
  if ( P[1] )
  {
    ExFreePoolWithTag(P[1], 0x6E6D7377u);
    P[1] = 0;
  }
  if ( String2.Buffer )
    ExFreePoolWithTag(String2.Buffer, 0x6E6D7377u);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140005de4  mov     [rsp-38h+arg_0], rbx
0x140005de9  mov     [rsp-38h+arg_18], r9b
0x140005dee  mov     [rsp-38h+SourceString], r8
0x140005df3  push    rbp
0x140005df4  push    rsi
0x140005df5  push    rdi
0x140005df6  push    r12
0x140005df8  push    r13
0x140005dfa  push    r14
0x140005dfc  push    r15
0x140005dfe  mov     rbp, rsp
0x140005e01  sub     rsp, 70h
0x140005e05  xorps   xmm0, xmm0
0x140005e08  mov     r12, r8
0x140005e0b  mov     r15, rdx
0x140005e0e  lea     r8, [rbp+RemainingName]; struct _UNICODE_STRING *
0x140005e12  xorps   xmm1, xmm1
0x140005e15  lea     rdx, [rbp+String2]; DestinationString
0x140005e19  movups  xmmword ptr [rbp+String2.Length], xmm0
0x140005e1d  mov     rbx, rcx
0x140005e20  movups  xmmword ptr [rbp+RemainingName.Length], xmm1
0x140005e24  movups  xmmword ptr [rbp+P], xmm0
0x140005e28  call    ?GetNtPath@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z; GetNtPath(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x140005e2d  xor     edi, edi
0x140005e2f  mov     esi, eax
0x140005e31  test    eax, eax
0x140005e33  jns     short loc_140005E51
0x140005e35  mov     r8, rbx
0x140005e38  mov     r9d, eax
0x140005e3b  lea     rdx, aFailedToConver; "Failed to convert path [%wZ] to NT (0x%"...
0x140005e42  mov     ecx, 3
0x140005e47  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140005e4c  jmp     loc_140005FFB
0x140005e51  movzx   edx, [rbp+String2.Length]
0x140005e55  cmp     edx, 2
0x140005e58  jb      short loc_140005E77
0x140005e5a  mov     rax, [rbp+String2.Buffer]
0x140005e5e  mov     ecx, edx
0x140005e60  shr     rcx, 1
0x140005e63  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x140005e69  jnz     short loc_140005E77
0x140005e6b  mov     eax, 0FFFEh
0x140005e70  add     dx, ax
0x140005e73  mov     [rbp+String2.Length], dx
0x140005e77  test    r15, r15
0x140005e7a  jz      short loc_140005EDF
0x140005e7c  mov     r8b, 1; CaseInSensitive
0x140005e7f  lea     rdx, stru_1400123F0; String2
0x140005e86  mov     rcx, r15; String1
0x140005e89  call    cs:__imp_RtlEqualUnicodeString
0x140005e90  nop     dword ptr [rax+rax+00h]
0x140005e95  lea     rdx, [rbp+P]; DestinationString
0x140005e99  test    al, al
0x140005e9b  jz      short loc_140005EC5
0x140005e9d  lea     rcx, stru_1400123F0; SourceString
0x140005ea4  call    ?Duplicate@@YAJPEBU_UNICODE_STRING@@PEAU1@@Z; Duplicate(_UNICODE_STRING const *,_UNICODE_STRING *)
0x140005ea9  mov     esi, eax
0x140005eab  test    eax, eax
0x140005ead  jns     short loc_140005EDF
0x140005eaf  lea     rdx, aFailedToDuplic_2; "Failed to duplicate system process name"
0x140005eb6  mov     ecx, 3
0x140005ebb  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140005ec0  jmp     loc_140005FFB
0x140005ec5  lea     r8, [rbp+RemainingName]; struct _UNICODE_STRING *
0x140005ec9  mov     rcx, r15; String2
0x140005ecc  call    ?GetNtPath@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z; GetNtPath(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x140005ed1  mov     esi, eax
0x140005ed3  test    eax, eax
0x140005ed5  jns     short loc_140005EDF
0x140005ed7  mov     r8, r15
0x140005eda  jmp     loc_140005E38
0x140005edf  lea     rcx, stru_140019468; FastMutex
0x140005ee6  call    cs:__imp_ExAcquireFastMutex
0x140005eed  nop     dword ptr [rax+rax+00h]
0x140005ef2  mov     dl, 1
0x140005ef4  jmp     short loc_140005F17
0x140005ef6  lea     rcx, [r13+38h]; String1
0x140005efa  mov     r8b, 1; CaseInSensitive
0x140005efd  lea     rdx, [rbp+String2]; String2
0x140005f01  call    cs:__imp_RtlEqualUnicodeString
0x140005f08  nop     dword ptr [rax+rax+00h]
0x140005f0d  test    al, al
0x140005f0f  jnz     loc_14000604E
0x140005f15  xor     edx, edx; Restart
0x140005f17  lea     rcx, ?g_TrackingInfo@@3U_TRACKED_PATHS_TABLE@@A; PrefixTable
0x140005f1e  call    cs:__imp_RtlNextUnicodePrefix
0x140005f25  nop     dword ptr [rax+rax+00h]
0x140005f2a  mov     r13, rax
0x140005f2d  test    rax, rax
0x140005f30  jnz     short loc_140005EF6
0x140005f32  mov     r9, r15
0x140005f35  lea     rdx, aPathWzNotBeing; "Path [%wZ] not being tracked; cannot ad"...
0x140005f3c  mov     r8, rbx
0x140005f3f  mov     ecx, 3
0x140005f44  mov     esi, 0C000003Ah
0x140005f49  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140005f4e  xor     r15d, r15d
0x140005f51  lea     rcx, stru_140019468; FastMutex
0x140005f58  call    cs:__imp_ExReleaseFastMutex
0x140005f5f  nop     dword ptr [rax+rax+00h]
0x140005f64  test    rdi, rdi
0x140005f67  jz      loc_140005FF9
0x140005f6d  mov     rcx, [rdi+40h]; P
0x140005f71  test    rcx, rcx
0x140005f74  jz      short loc_140005F8B
0x140005f76  mov     edx, 6E6D7377h; Tag
0x140005f7b  call    cs:__imp_ExFreePoolWithTag
0x140005f82  nop     dword ptr [rax+rax+00h]
0x140005f87  mov     [rdi+40h], r15
0x140005f8b  mov     rcx, [rdi+30h]; P
0x140005f8f  test    rcx, rcx
0x140005f92  jz      short loc_140005FA9
0x140005f94  mov     edx, 6E6D7377h; Tag
0x140005f99  call    cs:__imp_ExFreePoolWithTag
0x140005fa0  nop     dword ptr [rax+rax+00h]
0x140005fa5  mov     [rdi+30h], r15
0x140005fa9  mov     rcx, [rdi+20h]; P
0x140005fad  test    rcx, rcx
0x140005fb0  jz      short loc_140005FC7
0x140005fb2  mov     edx, 6E6D7377h; Tag
0x140005fb7  call    cs:__imp_ExFreePoolWithTag
0x140005fbe  nop     dword ptr [rax+rax+00h]
0x140005fc3  mov     [rdi+20h], r15
0x140005fc7  mov     rcx, [rdi+10h]; P
0x140005fcb  test    rcx, rcx
0x140005fce  jz      short loc_140005FE5
0x140005fd0  mov     edx, 6E6D7377h; Tag
0x140005fd5  call    cs:__imp_ExFreePoolWithTag
0x140005fdc  nop     dword ptr [rax+rax+00h]
0x140005fe1  mov     [rdi+10h], r15
0x140005fe5  mov     edx, 6E6D7377h; Tag
0x140005fea  mov     rcx, rdi; P
0x140005fed  call    cs:__imp_ExFreePoolWithTag
0x140005ff4  nop     dword ptr [rax+rax+00h]
0x140005ff9  xor     edi, edi
0x140005ffb  mov     rcx, [rbp+P+8]; P
0x140005fff  test    rcx, rcx
0x140006002  jz      short loc_140006019
0x140006004  mov     edx, 6E6D7377h; Tag
0x140006009  call    cs:__imp_ExFreePoolWithTag
0x140006010  nop     dword ptr [rax+rax+00h]
0x140006015  mov     [rbp+P+8], rdi
0x140006019  mov     rcx, [rbp+String2.Buffer]; P
0x14000601d  test    rcx, rcx
0x140006020  jz      short loc_140006033
0x140006022  mov     edx, 6E6D7377h; Tag
0x140006027  call    cs:__imp_ExFreePoolWithTag
0x14000602e  nop     dword ptr [rax+rax+00h]
0x140006033  mov     rbx, [rsp+70h+arg_0]
0x14000603b  mov     eax, esi
0x14000603d  add     rsp, 70h
0x140006041  pop     r15
0x140006043  pop     r14
0x140006045  pop     r13
0x140006047  pop     r12
0x140006049  pop     rdi
0x14000604a  pop     rsi
0x14000604b  pop     rbp
0x14000604c  retn
0x14000604e  mov     rbx, [r13+50h]
0x140006052  mov     r14, rdi
0x140006055  jmp     loc_14000618E
0x14000605a  lea     rcx, [rbx+8]; String1
0x14000605e  cmp     word ptr [rbp+P], di
0x140006062  jnz     short loc_14000606D
0x140006064  cmp     [rcx], di
0x140006067  jz      short loc_140006086
0x140006069  cmp     word ptr [rbp+P], di
0x14000606d  jbe     short loc_140006089
0x14000606f  mov     r8b, 1; CaseInSensitive
0x140006072  lea     rdx, [rbp+P]; String2
0x140006076  call    cs:__imp_RtlEqualUnicodeString
0x14000607d  nop     dword ptr [rax+rax+00h]
0x140006082  test    al, al
0x140006084  jz      short loc_140006089
0x140006086  mov     dil, 1
0x140006089  xor     edx, edx
0x14000608b  lea     rcx, [rbx+28h]; String1
0x14000608f  test    r12, r12
0x140006092  jnz     loc_140006159
0x140006098  cmp     [rcx], dx
0x14000609b  jz      loc_140006175
0x1400060a1  mov     al, dl
0x1400060a3  test    dil, dil
0x1400060a6  jz      loc_14000617C
0x1400060ac  xor     edi, edi
0x1400060ae  test    al, al
0x1400060b0  jz      loc_14000617E
0x1400060b6  mov     al, [rbp+arg_18]
0x1400060b9  cmp     al, [rbx+48h]
0x1400060bc  jnz     short loc_1400060CA
0x1400060be  mov     eax, [rbp+arg_20]
0x1400060c1  cmp     eax, [rbx+4Ch]
0x1400060c4  jz      loc_140006557
0x1400060ca  cmp     rbx, [r13+50h]
0x1400060ce  jnz     short loc_1400060D4
0x1400060d0  mov     [r13+50h], rdi
0x1400060d4  mov     rcx, [rbx+40h]; P
0x1400060d8  test    rcx, rcx
0x1400060db  jz      short loc_1400060F2
0x1400060dd  mov     edx, 6E6D7377h; Tag
0x1400060e2  call    cs:__imp_ExFreePoolWithTag
0x1400060e9  nop     dword ptr [rax+rax+00h]
0x1400060ee  mov     [rbx+40h], rdi
0x1400060f2  mov     rcx, [rbx+30h]; P
0x1400060f6  test    rcx, rcx
0x1400060f9  jz      short loc_140006110
0x1400060fb  mov     edx, 6E6D7377h; Tag
0x140006100  call    cs:__imp_ExFreePoolWithTag
0x140006107  nop     dword ptr [rax+rax+00h]
0x14000610c  mov     [rbx+30h], rdi
0x140006110  mov     rcx, [rbx+20h]; P
0x140006114  test    rcx, rcx
0x140006117  jz      short loc_14000612E
0x140006119  mov     edx, 6E6D7377h; Tag
0x14000611e  call    cs:__imp_ExFreePoolWithTag
0x140006125  nop     dword ptr [rax+rax+00h]
0x14000612a  mov     [rbx+20h], rdi
0x14000612e  mov     rcx, [rbx+10h]; P
0x140006132  test    rcx, rcx
0x140006135  jz      short loc_14000614C
0x140006137  mov     edx, 6E6D7377h; Tag
0x14000613c  call    cs:__imp_ExFreePoolWithTag
0x140006143  nop     dword ptr [rax+rax+00h]
0x140006148  mov     [rbx+10h], rdi
0x14000614c  test    r14, r14
0x14000614f  jz      short loc_140006188
0x140006151  mov     rax, [rbx]
0x140006154  mov     [r14], rax
0x140006157  jmp     short loc_140006188
0x140006159  mov     r8b, 1; CaseInSensitive
0x14000615c  mov     rdx, r12; String2
0x14000615f  call    cs:__imp_RtlEqualUnicodeString
0x140006166  nop     dword ptr [rax+rax+00h]
0x14000616b  xor     edx, edx
0x14000616d  test    al, al
0x14000616f  jz      loc_1400060A1
0x140006175  mov     al, 1
0x140006177  jmp     loc_1400060A3
0x14000617c  xor     edi, edi
0x14000617e  cmp     [r13+50h], rdi
0x140006182  jnz     short loc_140006188
0x140006184  mov     [r13+50h], rbx
0x140006188  mov     r14, rbx
0x14000618b  mov     rbx, [rbx]
0x14000618e  test    rbx, rbx
0x140006191  jnz     loc_14000605A
0x140006197  mov     ebx, 50h ; 'P'
0x14000619c  mov     r8d, 6E6D7377h; Tag
0x1400061a2  mov     edx, ebx; NumberOfBytes
0x1400061a4  mov     ecx, 401h; PoolType
0x1400061a9  call    cs:__imp_ExAllocatePoolWithTag
0x1400061b0  nop     dword ptr [rax+rax+00h]
0x1400061b5  cmp     cs:ExPoolZeroingNativelySupported, dil
0x1400061bc  mov     r14, rax
0x1400061bf  jnz     loc_14000626E
0x1400061c5  test    rax, rax
0x1400061c8  jz      loc_14000626E
0x1400061ce  mov     r8d, ebx; Size
0x1400061d1  xor     edx, edx; Val
0x1400061d3  mov     rcx, rax; void *
0x1400061d6  call    memset
0x1400061db  xor     eax, eax
0x1400061dd  mov     rdi, r14
0x1400061e0  mov     r12, r14
0x1400061e3  cmp     word ptr [rbp+P], ax
0x1400061e7  jbe     short loc_1400061FA
0x1400061e9  movups  xmm0, xmmword ptr [rbp+P]
0x1400061ed  xorps   xmm1, xmm1
0x1400061f0  movdqu  xmmword ptr [r14+8], xmm0
0x1400061f6  movups  xmmword ptr [rbp+P], xmm1
0x1400061fa  mov     [r14+18h], eax
0x1400061fe  test    r15, r15
0x140006201  jz      loc_140006388
0x140006207  movups  xmm1, xmmword ptr [r14+8]
0x14000620c  xor     r15d, r15d
0x14000620f  mov     bl, r15b
0x140006212  movd    eax, xmm1
0x140006216  movaps  xmmword ptr [rbp+RemainingName.Length], xmm1
0x14000621a  test    ax, ax
0x14000621d  jz      loc_140006384
0x140006223  xorps   xmm0, xmm0
0x140006226  movdqa  xmmword ptr [rbp+Path.Length], xmm1
0x14000622b  lea     r8, [rbp+RemainingName]; RemainingName
0x14000622f  lea     rdx, [rbp+FirstName]; FirstName
0x140006233  lea     rcx, [rbp+Path]; Path
0x140006237  movups  xmmword ptr [rbp+FirstName.Length], xmm0
0x14000623b  call    cs:__imp_FsRtlDissectName
0x140006242  nop     dword ptr [rax+rax+00h]
0x140006247  test    bl, bl
0x140006249  jnz     short loc_14000625D
0x14000624b  lea     rcx, [rbp+FirstName]; Name
0x14000624f  call    cs:__imp_FsRtlDoesNameContainWildCards
0x140006256  nop     dword ptr [rax+rax+00h]
0x14000625b  mov     bl, al
0x14000625d  inc     dword ptr [r14+18h]
0x140006261  cmp     [rbp+RemainingName.Length], r15w
0x140006266  jbe     short loc_140006295
0x140006268  movaps  xmm1, xmmword ptr [rbp+RemainingName.Length]
0x14000626c  jmp     short loc_140006223
  ... truncated ...
```
