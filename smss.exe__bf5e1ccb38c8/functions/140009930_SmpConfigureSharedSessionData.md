# SmpConfigureSharedSessionData

- ea: `0x140009930`
- end: `0x14000a12f`
- name: `SmpConfigureSharedSessionData`
- size: `2047`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000c638`

## callees

- `0x140009930`
- `0x14000d494`
- `0x14000d4c0`
- `0x14001cc11`
- `0x14001cc40`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x140009e05`
- `ntdll!RtlFreeHeap` at `0x140009fe5`
- `ntdll!RtlFreeHeap` at `0x140009e05`
- `ntdll!RtlFreeHeap` at `0x140009fe5`
- `ntdll!RtlQueryRegistryValuesEx` at `0x140009aae`
- `ntdll!RtlQueryRegistryValuesEx` at `0x140009aae`
- `ntdll!NtCreateSection` at `0x140009bbb`
- `ntdll!NtCreateSection` at `0x140009bbb`
- `ntdll!NtMapViewOfSection` at `0x140009c28`
- `ntdll!NtMapViewOfSection` at `0x14000a108`
- `ntdll!NtMapViewOfSection` at `0x140009c28`
- `ntdll!NtMapViewOfSection` at `0x14000a108`
- `ntdll!NtUnmapViewOfSection` at `0x14000a02d`
- `ntdll!NtUnmapViewOfSection` at `0x14000a02d`
- `ntdll!NtDuplicateObject` at `0x14000a063`
- `ntdll!NtDuplicateObject` at `0x14000a063`

## string_xrefs

- `0x140009bca`: `SmpConfigureSharedSessionData`
- `0x140009c37`: `SmpConfigureSharedSessionData`
- `0x14000a077`: `SmpConfigureSharedSessionData`

## pseudocode

```c
__int64 SmpConfigureSharedSessionData()
{
  __int64 result; // rax
  __int64 *v1; // rbx
  __int64 *v2; // rcx
  __int64 v3; // r8
  __int64 v4; // rax
  _QWORD *v5; // rcx
  __int64 v6; // rbx
  NTSTATUS v7; // eax
  unsigned int v8; // edi
  NTSTATUS v9; // eax
  unsigned int v10; // edi
  bool v11; // zf
  char *v12; // rbx
  __int64 Length; // rcx
  char *v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rdi
  char *v17; // rbx
  char *v18; // rdx
  char *v19; // r15
  _BYTE *v20; // rdx
  _BYTE *v21; // r14
  PVOID *v22; // rsi
  unsigned int v23; // edi
  char *v24; // rbx
  PVOID *v25; // r12
  __int64 v26; // rcx
  _WORD *v27; // r14
  PVOID *v28; // rcx
  PVOID *v29; // rax
  __int64 v30; // r12
  char *v31; // rdi
  unsigned int v32; // r14d
  __int64 *v33; // rsi
  __int64 v34; // rcx
  __int64 v35; // rcx
  unsigned int v36; // r14d
  char *v37; // rdi
  __int64 v38; // rcx
  __int64 v39; // rcx
  PVOID *v40; // rdi
  unsigned int v41; // esi
  PVOID *v42; // r14
  __int64 v43; // rcx
  char *v44; // r15
  PVOID *v45; // rcx
  PVOID *v46; // rax
  NTSTATUS v47; // eax
  unsigned int v48; // ebx
  __int64 v49; // r8
  __int64 v50; // rdx
  NTSTATUS v51; // eax
  ULONG_PTR ViewSize; // [rsp+50h] [rbp-B0h] BYREF
  union _LARGE_INTEGER MaximumSize; // [rsp+58h] [rbp-A8h] BYREF
  char *v54; // [rsp+60h] [rbp-A0h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  __int64 (__usercall *v56)@<rax>(wchar_t *@<rcx>, int, __int64); // [rsp+A0h] [rbp-60h] BYREF
  int v57; // [rsp+A8h] [rbp-58h]
  const wchar_t *v58; // [rsp+B0h] [rbp-50h]
  int *v59; // [rsp+B8h] [rbp-48h]
  int v60; // [rsp+C0h] [rbp-40h]
  __int64 v61; // [rsp+C8h] [rbp-38h]
  int v62; // [rsp+D0h] [rbp-30h]
  void *v63; // [rsp+D8h] [rbp-28h]
  int v64; // [rsp+E0h] [rbp-20h]
  const wchar_t *v65; // [rsp+E8h] [rbp-18h]
  int *v66; // [rsp+F0h] [rbp-10h]
  int v67; // [rsp+F8h] [rbp-8h]
  __int64 v68; // [rsp+100h] [rbp+0h]
  int v69; // [rsp+108h] [rbp+8h]
  void *v70; // [rsp+110h] [rbp+10h]
  int v71; // [rsp+118h] [rbp+18h]
  const wchar_t *v72; // [rsp+120h] [rbp+20h]
  int *v73; // [rsp+128h] [rbp+28h]
  int v74; // [rsp+130h] [rbp+30h]
  __int64 v75; // [rsp+138h] [rbp+38h]
  int v76; // [rsp+140h] [rbp+40h]
  __int64 (__fastcall *v77)(int, int, int, int, int, __int64); // [rsp+148h] [rbp+48h]
  int v78; // [rsp+150h] [rbp+50h]
  const wchar_t *v79; // [rsp+158h] [rbp+58h]
  int *v80; // [rsp+160h] [rbp+60h]
  int v81; // [rsp+168h] [rbp+68h]
  __int64 v82; // [rsp+170h] [rbp+70h]
  int v83; // [rsp+178h] [rbp+78h]
  __int64 v84; // [rsp+180h] [rbp+80h]
  int v85; // [rsp+188h] [rbp+88h]
  __int128 v86; // [rsp+190h] [rbp+90h]
  int v87; // [rsp+1A0h] [rbp+A0h]
  __int64 v88; // [rsp+1A8h] [rbp+A8h]
  int v89; // [rsp+1B0h] [rbp+B0h]

  v57 = 17;
  MaximumSize.QuadPart = 0;
  ViewSize = 0;
  v59 = &dword_140030398;
  v66 = &dword_140030398;
  v63 = &SmpBuildSubSystemLists;
  v56 = SmpConfigureSubSystems;
  v70 = &SmpBuildSubSystemLists;
  v58 = L"SubSystems";
  v73 = &dword_140030398;
  v65 = L"Required";
  v80 = &dword_140030398;
  v72 = L"Optional";
  v60 = 0;
  v77 = SmpConfigureExecute;
  v61 = 0;
  v79 = L"Execute";
  v62 = 0;
  memset(&ObjectAttributes, 0, 44);
  v64 = 16;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v71 = 16;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v78 = 2;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v84 = 0;
  v85 = 0;
  v86 = 0;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  qword_1400303A8 = (__int64)&qword_1400303A0;
  qword_1400303A0 = (__int64)&qword_1400303A0;
  qword_1400303B8 = (__int64)&BaseAddress;
  BaseAddress = &BaseAddress;
  qword_1400303C8 = (__int64)&qword_1400303C0;
  qword_1400303C0 = &qword_1400303C0;
  result = RtlQueryRegistryValuesEx(2, L"Session Manager", &v56);
  if ( (int)result >= 0 )
  {
    v1 = (__int64 *)qword_1400303A0;
    while ( v1 != &qword_1400303A0 )
    {
      v2 = v1;
      v1 = (__int64 *)*v1;
      SmpFreeSavedRegistryEntry(v2);
    }
    if ( qword_1400303C0 == &qword_1400303C0 )
    {
      SmpInitExecuteCmd = 0;
      v3 = 0;
    }
    else
    {
      v4 = qword_1400303C8;
      if ( *(PVOID **)qword_1400303C8 != &qword_1400303C0 )
        goto LABEL_42;
      v5 = *(_QWORD **)(qword_1400303C8 + 8);
      if ( *v5 != qword_1400303C8 )
        goto LABEL_42;
      qword_1400303C8 = *(_QWORD *)(qword_1400303C8 + 8);
      *v5 = &qword_1400303C0;
      v3 = *(unsigned __int16 *)(v4 + 16);
      SmpInitExecuteCmd = v4;
    }
    v6 = 16LL * (unsigned int)dword_140030398 + 104;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 2;
    ObjectAttributes.ObjectName = 0;
    MaximumSize.QuadPart = v3 + 6 + (unsigned int)dword_14003039C + v6 + SmpS0InitCmd.Length + SmpDefaultLibPath.Length;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v7 = NtCreateSection(&SmpSharedSection, 6u, &ObjectAttributes, &MaximumSize, 4u, 0x8400000u, 0);
    v8 = v7;
    if ( v7 < 0 )
    {
      SmpLogFailure("SmpConfigureSharedSessionData", 8354, (unsigned int)v7);
      return v8;
    }
    ViewSize = 0;
    v9 = NtMapViewOfSection(
           SmpSharedSection,
           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
           &SmpMappedView,
           0,
           0,
           0,
           &ViewSize,
           ViewUnmap,
           0,
           4u);
    v10 = v9;
    if ( v9 < 0 )
    {
      SmpLogFailure("SmpConfigureSharedSessionData", 8379, (unsigned int)v9);
      return v10;
    }
    v11 = SmpS0CommandOverride == 0;
    *(_DWORD *)SmpMappedView = 0;
    if ( !v11 )
      *(_DWORD *)SmpMappedView = 1;
    v12 = (char *)SmpMappedView + v6;
    *((_QWORD *)SmpMappedView + 1) = v12 - (_BYTE *)SmpMappedView;
    *((_WORD *)SmpMappedView + 8) = SmpDefaultLibPath.Length;
    memcpy_0(v12, SmpDefaultLibPath.Buffer, SmpDefaultLibPath.Length);
    Length = SmpDefaultLibPath.Length;
    *(_WORD *)&v12[SmpDefaultLibPath.Length] = 0;
    v14 = &v12[Length + 2];
    *((_QWORD *)SmpMappedView + 3) = v14 - (_BYTE *)SmpMappedView;
    *((_WORD *)SmpMappedView + 16) = SmpS0InitCmd.Length;
    memcpy_0(v14, SmpS0InitCmd.Buffer, SmpS0InitCmd.Length);
    v15 = SmpS0InitCmd.Length;
    v16 = SmpInitExecuteCmd;
    *(_WORD *)&v14[SmpS0InitCmd.Length] = 0;
    v17 = &v14[v15 + 2];
    *((_QWORD *)SmpMappedView + 5) = v17 - (_BYTE *)SmpMappedView;
    if ( v16 && *(_QWORD *)(v16 + 24) )
    {
      *((_WORD *)SmpMappedView + 24) = *(_WORD *)(v16 + 16);
      memcpy_0(v17, *(const void **)(v16 + 24), *(unsigned __int16 *)(v16 + 16));
      v18 = &v17[*(unsigned __int16 *)(v16 + 16)];
    }
    else
    {
      v18 = v17;
      *((_WORD *)SmpMappedView + 24) = 0;
    }
    v19 = v18 + 2;
    *(_WORD *)v18 = 0;
    v20 = SmpMappedView;
    v21 = v19;
    v22 = (PVOID *)BaseAddress;
    v23 = 0;
    v54 = v19;
    v24 = (char *)SmpMappedView + 104;
    if ( BaseAddress != &BaseAddress )
    {
      while ( 1 )
      {
        v25 = (PVOID *)*v22;
        v26 = 2LL * v23;
        *(_QWORD *)&v24[8 * v26] = v21 - v20;
        *(_WORD *)&v24[8 * v26 + 8] = *((_WORD *)v22 + 8);
        memcpy_0(v21, v22[3], *((unsigned __int16 *)v22 + 8));
        v27 = &v21[*((unsigned __int16 *)v22 + 8)];
        *v27 = 0;
        v28 = (PVOID *)*v22;
        if ( *((PVOID **)*v22 + 1) != v22 )
          break;
        v29 = (PVOID *)v22[1];
        if ( *v29 != v22 )
          break;
        *v29 = v28;
        v28[1] = v29;
        v21 = v27 + 1;
        ++v23;
        RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v22);
        v20 = SmpMappedView;
        v22 = v25;
        if ( v25 == &BaseAddress )
          goto LABEL_23;
      }
LABEL_42:
      __fastfail(3u);
    }
LABEL_23:
    *((_QWORD *)v20 + 7) = v24 - v20;
    *((_DWORD *)SmpMappedView + 16) = v23;
    *((_DWORD *)SmpMappedView + 17) = 0;
    if ( v23 )
    {
      v19 = v21;
      v24 += 16 * v23;
      v54 = v21;
    }
    v30 = SmpSubSystemsRequired;
    v31 = v19;
    v32 = 0;
    if ( (__int64 *)SmpSubSystemsRequired != &SmpSubSystemsRequired )
    {
      do
      {
        v33 = *(__int64 **)v30;
        v34 = 2LL * v32;
        *(_QWORD *)&v24[8 * v34] = v31 - (_BYTE *)SmpMappedView;
        *(_WORD *)&v24[8 * v34 + 8] = *(_WORD *)(v30 + 16);
        memcpy_0(v31, *(const void **)(v30 + 24), *(unsigned __int16 *)(v30 + 16));
        v35 = *(unsigned __int16 *)(v30 + 16);
        v36 = v32 + 1;
        *(_WORD *)&v31[v35] = 0;
        v37 = &v31[v35];
        v38 = 2LL * v36;
        *(_QWORD *)&v24[8 * v38] = v37 + 2 - (_BYTE *)SmpMappedView;
        *(_WORD *)&v24[8 * v38 + 8] = *(_WORD *)(v30 + 32);
        memcpy_0(v37 + 2, *(const void **)(v30 + 40), *(unsigned __int16 *)(v30 + 32));
        v39 = *(unsigned __int16 *)(v30 + 32);
        v32 = v36 + 1;
        v30 = (__int64)v33;
        *(_WORD *)&v37[v39 + 2] = 0;
        v31 = &v37[v39 + 4];
      }
      while ( v33 != &SmpSubSystemsRequired );
      v19 = v54;
    }
    *((_QWORD *)SmpMappedView + 9) = v24 - (_BYTE *)SmpMappedView;
    *((_DWORD *)SmpMappedView + 20) = v32;
    *((_DWORD *)SmpMappedView + 21) = 1;
    if ( v32 )
    {
      v19 = v31;
      v24 += 16 * v32;
    }
    v40 = (PVOID *)qword_1400303C0;
    v41 = 0;
    if ( qword_1400303C0 != &qword_1400303C0 )
    {
      while ( 1 )
      {
        v42 = (PVOID *)*v40;
        v43 = 2LL * v41;
        *(_QWORD *)&v24[8 * v43] = v19 - (_BYTE *)SmpMappedView;
        *(_WORD *)&v24[8 * v43 + 8] = *((_WORD *)v40 + 8);
        memcpy_0(v19, v40[3], *((unsigned __int16 *)v40 + 8));
        v44 = &v19[*((unsigned __int16 *)v40 + 8)];
        *(_WORD *)v44 = 0;
        v45 = (PVOID *)*v40;
        if ( *((PVOID **)*v40 + 1) != v40 )
          goto LABEL_42;
        v46 = (PVOID *)v40[1];
        if ( *v46 != v40 )
          goto LABEL_42;
        *v46 = v45;
        v45[1] = v46;
        ++v41;
        RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v40);
        v40 = v42;
        if ( v42 == &qword_1400303C0 )
          break;
        v19 = v44 + 2;
      }
    }
    *((_QWORD *)SmpMappedView + 11) = v24 - (_BYTE *)SmpMappedView;
    *((_DWORD *)SmpMappedView + 24) = v41;
    *((_DWORD *)SmpMappedView + 25) = 0;
    NtUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, SmpMappedView);
    v47 = NtDuplicateObject(
            (HANDLE)0xFFFFFFFFFFFFFFFFLL,
            SmpSharedSection,
            (HANDLE)0xFFFFFFFFFFFFFFFFLL,
            &SmpSharedSection,
            4u,
            2u,
            9u);
    v48 = v47;
    if ( v47 >= 0 )
    {
      ViewSize = 0;
      SmpMappedView = 0;
      v51 = NtMapViewOfSection(
              SmpSharedSection,
              (HANDLE)0xFFFFFFFFFFFFFFFFLL,
              &SmpMappedView,
              0,
              0,
              0,
              &ViewSize,
              ViewUnmap,
              0,
              2u);
      v48 = v51;
      if ( v51 >= 0 )
        return 0;
      v49 = (unsigned int)v51;
      v50 = 8500;
    }
    else
    {
      v49 = (unsigned int)v47;
      v50 = 8479;
    }
    SmpLogFailure("SmpConfigureSharedSessionData", v50, v49);
    return v48;
  }
  return result;
}

```

## disassembly

```asm
0x140009930  push    rbp
0x140009932  push    rsi
0x140009933  push    rdi
0x140009934  push    r12
0x140009936  push    r13
0x140009938  lea     rbp, [rsp-0D0h]
0x140009940  sub     rsp, 1D0h
0x140009947  mov     rax, cs:__security_cookie
0x14000994e  xor     rax, rsp
0x140009951  mov     [rbp+0F0h+var_30], rax
0x140009958  xor     r13d, r13d
0x14000995b  mov     [rbp+0F0h+var_148], 11h
0x140009962  xor     eax, eax
0x140009964  mov     qword ptr [rsp+1F0h+MaximumSize], r13
0x140009969  lea     rdx, dword_140030398
0x140009970  mov     [rsp+1F0h+ViewSize], r13
0x140009975  xorps   xmm0, xmm0
0x140009978  mov     [rbp+0F0h+var_138], rdx
0x14000997c  lea     rcx, SmpBuildSubSystemLists
0x140009983  mov     [rbp+0F0h+var_100], rdx
0x140009987  lea     rax, SmpConfigureSubSystems
0x14000998e  mov     [rbp+0F0h+var_118], rcx
0x140009992  mov     [rbp+0F0h+var_150], rax
0x140009996  lea     rsi, qword_1400303A0
0x14000999d  lea     rax, aSubsystems; "SubSystems"
0x1400099a4  mov     [rbp+0F0h+var_E0], rcx
0x1400099a8  mov     [rbp+0F0h+var_140], rax
0x1400099ac  lea     r12, BaseAddress
0x1400099b3  lea     rax, aRequired; "Required"
0x1400099ba  mov     [rbp+0F0h+var_C8], rdx
0x1400099be  mov     [rbp+0F0h+var_108], rax
0x1400099c2  lea     rdi, qword_1400303C0
0x1400099c9  lea     rax, aOptional; "Optional"
0x1400099d0  mov     [rbp+0F0h+var_90], rdx
0x1400099d4  mov     [rbp+0F0h+var_D0], rax
0x1400099d8  lea     r8, [rbp+0F0h+var_150]
0x1400099dc  lea     rax, SmpConfigureExecute
0x1400099e3  mov     [rbp+0F0h+var_130], r13d
0x1400099e7  mov     [rbp+0F0h+var_A8], rax
0x1400099eb  lea     rdx, Path; "Session Manager"
0x1400099f2  lea     rax, aExecute; "Execute"
0x1400099f9  mov     [rbp+0F0h+var_128], r13
0x1400099fd  movups  xmmword ptr [rsp+1F0h+ObjectAttributes.ObjectName], xmm0
0x140009a02  xor     r9d, r9d
0x140009a05  mov     [rbp+0F0h+var_98], rax
0x140009a09  mov     ecx, 2
0x140009a0e  mov     [rbp+0F0h+var_120], r13d
0x140009a12  movups  xmmword ptr [rsp+1F0h+ObjectAttributes.Length], xmm0
0x140009a17  mov     [rbp+0F0h+var_110], 10h
0x140009a1e  movups  xmmword ptr [rbp+0F0h+ObjectAttributes+1Ch], xmm0
0x140009a22  mov     [rbp+0F0h+var_F8], r13d
0x140009a26  mov     [rbp+0F0h+var_F0], r13
0x140009a2a  mov     [rbp+0F0h+var_E8], r13d
0x140009a2e  mov     [rbp+0F0h+var_D8], 10h
0x140009a35  mov     [rbp+0F0h+var_C0], r13d
0x140009a39  mov     [rbp+0F0h+var_B8], r13
0x140009a3d  mov     [rbp+0F0h+var_B0], r13d
0x140009a41  mov     [rbp+0F0h+var_A0], 2
0x140009a48  mov     [rbp+0F0h+var_88], r13d
0x140009a4c  mov     [rbp+0F0h+var_80], r13
0x140009a50  mov     [rbp+0F0h+var_78], r13d
0x140009a54  mov     [rbp+0F0h+var_70], r13
0x140009a5b  mov     [rbp+0F0h+var_68], r13d
0x140009a62  movdqa  [rbp+0F0h+var_60], xmm0
0x140009a6a  mov     [rbp+0F0h+var_50], r13d
0x140009a71  mov     [rbp+0F0h+var_48], r13
0x140009a78  mov     [rbp+0F0h+var_40], r13d
0x140009a7f  mov     cs:qword_1400303A8, rsi
0x140009a86  mov     cs:qword_1400303A0, rsi
0x140009a8d  mov     cs:qword_1400303B8, r12
0x140009a94  mov     cs:BaseAddress, r12
0x140009a9b  mov     cs:qword_1400303C8, rdi
0x140009aa2  mov     cs:qword_1400303C0, rdi
0x140009aa9  mov     qword ptr [rsp+1F0h+SectionPageProtection], r13
0x140009aae  call    cs:__imp_RtlQueryRegistryValuesEx
0x140009ab4  test    eax, eax
0x140009ab6  js      loc_14000A09D
0x140009abc  mov     [rsp+1F0h+arg_0], rbx
0x140009ac4  mov     rbx, cs:qword_1400303A0
0x140009acb  cmp     rbx, rsi
0x140009ace  jz      short loc_140009AE0
0x140009ad0  mov     rcx, rbx
0x140009ad3  mov     rbx, [rbx]
0x140009ad6  call    SmpFreeSavedRegistryEntry
0x140009adb  cmp     rbx, rsi
0x140009ade  jnz     short loc_140009AD0
0x140009ae0  cmp     cs:qword_1400303C0, rdi
0x140009ae7  mov     [rsp+1F0h+arg_8], r14
0x140009aef  mov     [rsp+1F0h+arg_10], r15
0x140009af7  jnz     short loc_140009B05
0x140009af9  mov     cs:SmpInitExecuteCmd, r13
0x140009b00  mov     r8, r13
0x140009b03  jmp     short loc_140009B38
0x140009b05  mov     rax, cs:qword_1400303C8
0x140009b0c  cmp     [rax], rdi
0x140009b0f  jnz     loc_14000A128
0x140009b15  mov     rcx, [rax+8]
0x140009b19  cmp     [rcx], rax
0x140009b1c  jnz     loc_14000A128
0x140009b22  mov     cs:qword_1400303C8, rcx
0x140009b29  mov     [rcx], rdi
0x140009b2c  movzx   r8d, word ptr [rax+10h]
0x140009b31  mov     cs:SmpInitExecuteCmd, rax
0x140009b38  mov     ecx, cs:dword_14003039C
0x140009b3e  lea     r9, [rsp+1F0h+MaximumSize]; MaximumSize
0x140009b43  mov     ebx, cs:dword_140030398
0x140009b49  add     r8, 6
0x140009b4d  movzx   edx, cs:SmpS0InitCmd.Length
0x140009b54  xorps   xmm0, xmm0
0x140009b57  movzx   eax, cs:SmpDefaultLibPath.Length
0x140009b5e  mov     [rsp+1F0h+FileHandle], r13; FileHandle
0x140009b63  shl     rbx, 4
0x140009b67  add     rbx, 68h ; 'h'
0x140009b6b  mov     [rsp+1F0h+AllocationAttributes], 8400000h; AllocationAttributes
0x140009b73  add     rdx, rbx
0x140009b76  mov     [rsp+1F0h+ObjectAttributes.Length], 30h ; '0'
0x140009b7e  add     rdx, rcx
0x140009b81  mov     [rsp+1F0h+ObjectAttributes.RootDirectory], r13
0x140009b86  add     rax, rdx
0x140009b89  mov     [rbp+0F0h+ObjectAttributes.Attributes], 2
0x140009b90  add     rax, r8
0x140009b93  mov     [rsp+1F0h+ObjectAttributes.ObjectName], r13
0x140009b98  lea     r8, [rsp+1F0h+ObjectAttributes]; ObjectAttributes
0x140009b9d  mov     qword ptr [rsp+1F0h+MaximumSize], rax
0x140009ba2  mov     edx, 6; DesiredAccess
0x140009ba7  mov     [rsp+1F0h+SectionPageProtection], 4; SectionPageProtection
0x140009baf  lea     rcx, SmpSharedSection; SectionHandle
0x140009bb6  movdqu  xmmword ptr [rbp+0F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140009bbb  call    cs:__imp_NtCreateSection
0x140009bc1  mov     edi, eax
0x140009bc3  test    eax, eax
0x140009bc5  jns     short loc_140009BE2
0x140009bc7  mov     r8d, eax
0x140009bca  lea     rcx, aSmpconfiguresh; "SmpConfigureSharedSessionData"
0x140009bd1  mov     edx, 20A2h
0x140009bd6  call    SmpLogFailure
0x140009bdb  mov     eax, edi
0x140009bdd  jmp     loc_14000A085
0x140009be2  mov     rcx, cs:SmpSharedSection; SectionHandle
0x140009be9  lea     rax, [rsp+1F0h+ViewSize]
0x140009bee  mov     [rsp+1F0h+AccessProtection], 4; AccessProtection
0x140009bf6  lea     r8, SmpMappedView; BaseAddress
0x140009bfd  mov     [rsp+1F0h+AllocationType], r13d; AllocationType
0x140009c02  xor     r9d, r9d; ZeroBits
0x140009c05  mov     [rsp+1F0h+InheritDisposition], 2; InheritDisposition
0x140009c0d  mov     rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140009c14  mov     [rsp+1F0h+FileHandle], rax; ViewSize
0x140009c19  mov     qword ptr [rsp+1F0h+AllocationAttributes], r13; SectionOffset
0x140009c1e  mov     qword ptr [rsp+1F0h+SectionPageProtection], r13; CommitSize
0x140009c23  mov     [rsp+1F0h+ViewSize], r13
0x140009c28  call    cs:__imp_NtMapViewOfSection
0x140009c2e  mov     edi, eax
0x140009c30  test    eax, eax
0x140009c32  jns     short loc_140009C4F
0x140009c34  mov     r8d, eax
0x140009c37  lea     rcx, aSmpconfiguresh; "SmpConfigureSharedSessionData"
0x140009c3e  mov     edx, 20BBh
0x140009c43  call    SmpLogFailure
0x140009c48  mov     eax, edi
0x140009c4a  jmp     loc_14000A085
0x140009c4f  cmp     cs:SmpS0CommandOverride, r13d
0x140009c56  mov     rax, cs:SmpMappedView
0x140009c5d  mov     [rax], r13d
0x140009c60  jz      short loc_140009C6F
0x140009c62  mov     rax, cs:SmpMappedView
0x140009c69  mov     dword ptr [rax], 1
0x140009c6f  mov     rcx, cs:SmpMappedView
0x140009c76  add     rbx, rcx
0x140009c79  mov     rax, rbx
0x140009c7c  sub     rax, rcx
0x140009c7f  mov     [rcx+8], rax
0x140009c83  movzx   ecx, cs:SmpDefaultLibPath.Length
0x140009c8a  mov     rax, cs:SmpMappedView
0x140009c91  mov     [rax+10h], cx
0x140009c95  mov     rcx, rbx; void *
0x140009c98  movzx   r8d, cs:SmpDefaultLibPath.Length; MaxCount
0x140009ca0  mov     rdx, cs:SmpDefaultLibPath.Buffer; Src
0x140009ca7  call    memcpy_0
0x140009cac  movzx   ecx, cs:SmpDefaultLibPath.Length
0x140009cb3  mov     [rcx+rbx], r13w
0x140009cb8  add     rcx, 2
0x140009cbc  mov     rax, cs:SmpMappedView
0x140009cc3  add     rbx, rcx
0x140009cc6  mov     rcx, rbx
0x140009cc9  sub     rcx, rax
0x140009ccc  mov     [rax+18h], rcx
0x140009cd0  movzx   ecx, cs:SmpS0InitCmd.Length
0x140009cd7  mov     rax, cs:SmpMappedView
0x140009cde  mov     [rax+20h], cx
0x140009ce2  mov     rcx, rbx; void *
0x140009ce5  movzx   r8d, cs:SmpS0InitCmd.Length; MaxCount
0x140009ced  mov     rdx, cs:SmpS0InitCmd.Buffer; Src
0x140009cf4  call    memcpy_0
0x140009cf9  movzx   ecx, cs:SmpS0InitCmd.Length
0x140009d00  mov     rdi, cs:SmpInitExecuteCmd
0x140009d07  mov     [rcx+rbx], r13w
0x140009d0c  add     rcx, 2
0x140009d10  mov     rax, cs:SmpMappedView
0x140009d17  add     rbx, rcx
0x140009d1a  mov     rcx, rbx
0x140009d1d  sub     rcx, rax
0x140009d20  mov     [rax+28h], rcx
0x140009d24  test    rdi, rdi
0x140009d27  jz      short loc_140009D58
0x140009d29  cmp     [rdi+18h], r13
0x140009d2d  jz      short loc_140009D58
0x140009d2f  movzx   ecx, word ptr [rdi+10h]
0x140009d33  mov     rax, cs:SmpMappedView
0x140009d3a  mov     [rax+30h], cx
0x140009d3e  mov     rcx, rbx; void *
0x140009d41  movzx   r8d, word ptr [rdi+10h]; MaxCount
0x140009d46  mov     rdx, [rdi+18h]; Src
0x140009d4a  call    memcpy_0
0x140009d4f  movzx   edx, word ptr [rdi+10h]
0x140009d53  add     rdx, rbx
0x140009d56  jmp     short loc_140009D67
0x140009d58  mov     rax, cs:SmpMappedView
0x140009d5f  mov     rdx, rbx
0x140009d62  mov     [rax+30h], r13w
0x140009d67  lea     r15, [rdx+2]
0x140009d6b  mov     [rdx], r13w
0x140009d6f  mov     rdx, cs:SmpMappedView
0x140009d76  mov     r14, r15
0x140009d79  mov     rsi, cs:BaseAddress
0x140009d80  mov     edi, r13d
0x140009d83  mov     [rsp+1F0h+var_190], r15
0x140009d88  lea     rbx, [rdx+68h]
0x140009d8c  cmp     rsi, r12
0x140009d8f  jz      loc_140009E25
0x140009d95  mov     r12, [rsi]
0x140009d98  mov     rax, r14
0x140009d9b  sub     rax, rdx
0x140009d9e  mov     ecx, edi
0x140009da0  add     rcx, rcx
0x140009da3  mov     [rbx+rcx*8], rax
0x140009da7  movzx   eax, word ptr [rsi+10h]
0x140009dab  mov     [rbx+rcx*8+8], ax
0x140009db0  mov     rcx, r14; void *
0x140009db3  movzx   r8d, word ptr [rsi+10h]; MaxCount
0x140009db8  mov     rdx, [rsi+18h]; Src
0x140009dbc  call    memcpy_0
0x140009dc1  movzx   eax, word ptr [rsi+10h]
0x140009dc5  add     r14, rax
0x140009dc8  mov     [r14], r13w
0x140009dcc  mov     rcx, [rsi]
0x140009dcf  cmp     [rcx+8], rsi
0x140009dd3  jnz     loc_14000A128
0x140009dd9  mov     rax, [rsi+8]
0x140009ddd  cmp     [rax], rsi
0x140009de0  jnz     loc_14000A128
0x140009de6  mov     [rax], rcx
0x140009de9  mov     r8, rsi; BaseAddress
0x140009dec  mov     [rcx+8], rax
0x140009df0  xor     edx, edx; Flags
0x140009df2  mov     rcx, gs:60h
0x140009dfb  add     r14, 2
0x140009dff  inc     edi
0x140009e01  mov     rcx, [rcx+30h]; HeapHandle
0x140009e05  call    cs:__imp_RtlFreeHeap
0x140009e0b  mov     rdx, cs:SmpMappedView
0x140009e12  lea     rax, BaseAddress
0x140009e19  mov     rsi, r12
0x140009e1c  cmp     r12, rax
0x140009e1f  jnz     loc_140009D95
0x140009e25  mov     rax, rbx
0x140009e28  sub     rax, rdx
0x140009e2b  mov     [rdx+38h], rax
0x140009e2f  mov     rax, cs:SmpMappedView
0x140009e36  mov     [rax+40h], edi
0x140009e39  mov     rax, cs:SmpMappedView
0x140009e40  mov     [rax+44h], r13d
0x140009e44  test    edi, edi
0x140009e46  jz      short loc_140009E59
0x140009e48  mov     eax, edi
0x140009e4a  mov     r15, r14
0x140009e4d  shl     rax, 4
0x140009e51  add     rbx, rax
0x140009e54  mov     [rsp+1F0h+var_190], r14
0x140009e59  mov     r12, cs:SmpSubSystemsRequired
0x140009e60  lea     rax, SmpSubSystemsRequired
0x140009e67  mov     rdi, r15
0x140009e6a  mov     r14d, r13d
0x140009e6d  cmp     r12, rax
0x140009e70  jz      loc_140009F1F
0x140009e76  lea     r15, SmpSubSystemsRequired
0x140009e7d  mov     rsi, [r12]
0x140009e81  mov     rax, rdi
0x140009e84  sub     rax, cs:SmpMappedView
0x140009e8b  mov     ecx, r14d
0x140009e8e  add     rcx, rcx
0x140009e91  mov     [rbx+rcx*8], rax
0x140009e95  movzx   eax, word ptr [r12+10h]
0x140009e9b  mov     [rbx+rcx*8+8], ax
0x140009ea0  mov     rcx, rdi; void *
0x140009ea3  movzx   r8d, word ptr [r12+10h]; MaxCount
0x140009ea9  mov     rdx, [r12+18h]; Src
0x140009eae  call    memcpy_0
0x140009eb3  movzx   ecx, word ptr [r12+10h]
0x140009eb9  inc     r14d
0x140009ebc  mov     [rcx+rdi], r13w
  ... truncated ...
```
