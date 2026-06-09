# SxspGetAutoServicingWinSxSVersion(bool,_ASSEMBLY_IDENTITY *,ushort const * const,_ASSEMBLY_VERSION const *,bool &,bool &)

- ea: `0x180026a60`
- end: `0x18002714b`
- name: `?SxspGetAutoServicingWinSxSVersion@@YAH_NPEAU_ASSEMBLY_IDENTITY@@QEBGPEBT_ASSEMBLY_VERSION@@AEA_N4@Z`
- size: `1771`
- prototype: `int(bool, struct _ASSEMBLY_IDENTITY *, const unsigned __int16 *const, const union _ASSEMBLY_VERSION *, bool *, bool *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180025e00`

## callees

- `0x1800075a0`
- `0x18000a804`
- `0x18000c000`
- `0x18000df40`
- `0x18000dffc`
- `0x180017bc0`
- `0x18001d988`
- `0x18001e5c0`
- `0x180022f90`
- `0x180026a60`
- `0x18002c5b0`
- `0x18002da50`
- `0x18004d3b0`
- `0x18005b8a0`
- `0x180067548`
- `0x180067680`
- `0x18006a0f5`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x180026c77`
- `ntdll!RtlPopFrame` at `0x180026dba`
- `ntdll!RtlPopFrame` at `0x180026fcc`
- `ntdll!RtlPopFrame` at `0x180026ff6`
- `ntdll!RtlPopFrame` at `0x180026c77`
- `ntdll!RtlPopFrame` at `0x180026dba`
- `ntdll!RtlPopFrame` at `0x180026fcc`
- `ntdll!RtlPopFrame` at `0x180026ff6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026ceb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026d28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026d67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026fdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026ceb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026d28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026d67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026fdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027131`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026b62`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026b8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026c4a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026d1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026d5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026d9d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026df5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026e2e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026e65`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026eb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026ef8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026fa0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800270e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800270f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002710b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026b62`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026b8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026c4a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026d1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026d5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026d9d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026df5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026e2e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026e65`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026eb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026ef8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026fa0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800270e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800270f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002710b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026d06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026d45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026d87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026d06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026d45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026d87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026bff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026bff`

## string_xrefs

- `0x180026c99`: `SXS.DLL: KeyForm %S is missing in system install map.\n`
- `0x180026f6e`: `SXS.DLL: KeyForm %S Version %S is missing in system install map.\n`

## pseudocode

```c
__int64 __fastcall SxspGetAutoServicingWinSxSVersion(
        char a1,
        struct _ASSEMBLY_IDENTITY *a2,
        const WCHAR *a3,
        const union _ASSEMBLY_VERSION *a4,
        bool *a5,
        bool *a6)
{
  HKEY v9; // rsi
  unsigned int v10; // edx
  unsigned int v11; // ecx
  LSTATUS v12; // eax
  unsigned int i; // edx
  HKEY v14; // rax
  HKEY v15; // rcx
  int v16; // ebx
  unsigned int v17; // edi
  DWORD v18; // ebx
  LSTATUS v19; // eax
  DWORD v20; // ebx
  LSTATUS v21; // eax
  DWORD v22; // eax
  HKEY v23; // rcx
  DWORD v24; // ebx
  LSTATUS v25; // eax
  unsigned int v27; // r9d
  DWORD LastError; // eax
  DWORD v29; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  bool v31; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v32; // [rsp+48h] [rbp-B8h] BYREF
  int v33; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v34; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v35[2]; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v36; // [rsp+68h] [rbp-98h] BYREF
  struct _ASSEMBLY_IDENTITY *v37; // [rsp+70h] [rbp-90h]
  HKEY v38; // [rsp+78h] [rbp-88h] BYREF
  int v39; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  int v41; // [rsp+90h] [rbp-70h] BYREF
  struct _TEB_ACTIVE_FRAME v42; // [rsp+98h] [rbp-68h] BYREF
  __int64 v43; // [rsp+B0h] [rbp-50h]
  int v44; // [rsp+B8h] [rbp-48h]
  int *v45; // [rsp+C0h] [rbp-40h]
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v47; // [rsp+E0h] [rbp-20h]
  int v48; // [rsp+E8h] [rbp-18h]
  int *v49; // [rsp+F0h] [rbp-10h]
  void **v50; // [rsp+100h] [rbp+0h] BYREF
  int v51; // [rsp+108h] [rbp+8h]
  unsigned __int16 *InlineBuffer; // [rsp+110h] [rbp+10h]
  __int64 v53; // [rsp+118h] [rbp+18h]
  char *v54; // [rsp+120h] [rbp+20h]
  __int16 v55; // [rsp+128h] [rbp+28h] BYREF

  v42.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006D700;
  v37 = a2;
  v45 = &v39;
  v39 = 0;
  v42.Flags = 1;
  v42.Previous = 0;
  v43 = 544438355;
  v44 = 1007;
  CFrame::BaseEnter((CFrame *)&v42);
  hKey = 0;
  v50 = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  v32 = 0;
  v9 = 0;
  v34 = 0;
  v36 = 0;
  v51 = 0;
  InlineBuffer = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  InlineBuffer = (unsigned __int16 *)CGenericStringBuffer<1,CUnicodeCharTraits>::GetInlineBuffer(&v50);
  v53 = ((__int64 (__fastcall *)(void ***))v50[3])(&v50);
  if ( (unsigned int)Feature_Servicing_SxS_NullTerminateFix__private_IsEnabledDeviceUsageNoInline() )
    memset_0(InlineBuffer, 0, 2 * v53);
  v31 = 0;
  v33 = 0;
  SetLastError(0);
  if ( !SxspOpenAssemblyWinnersKey(v11, v10, (struct CRegKey *)&hKey) )
  {
    *v45 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075D50);
    goto LABEL_20;
  }
  if ( !hKey )
  {
LABEL_19:
    v39 = 1;
    goto LABEL_20;
  }
  SetLastError(0);
  v41 = 0;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006D380;
  Frame.Flags = 1;
  v49 = &v41;
  Frame.Previous = 0;
  v47 = 544438355;
  v48 = 507;
  CFrame::BaseEnter((CFrame *)&Frame);
  v38 = 0;
  v35[0] = 2;
  v35[1] = 3;
  v12 = RegOpenKeyExW(hKey, a3, 0, 0x20119u, &v38);
  if ( !v12 )
    goto LABEL_11;
  for ( i = 0; i < 2; ++i )
  {
    if ( v35[i] == v12 )
    {
      v14 = 0;
      v38 = 0;
      goto LABEL_12;
    }
  }
  if ( i == 2 )
  {
    SetLastError(v12);
    FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_18007CA20);
  }
  else
  {
LABEL_11:
    v14 = v38;
LABEL_12:
    v15 = v32;
    if ( v14 )
      v15 = v14;
    v32 = v15;
    SetLastError(0);
    *v49 = 1;
  }
  v16 = *v49;
  if ( !g_FusionEnterExitTracingEnabled )
  {
    RtlPopFrame(&Frame);
    if ( v16 )
      goto LABEL_17;
LABEL_54:
    *v45 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075D30);
    goto LABEL_20;
  }
  if ( !v16 )
  {
    LastError = GetLastError();
    FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    RtlPopFrame(&Frame);
    goto LABEL_54;
  }
  FusionpTraceCallSuccessfulExit(0);
  RtlPopFrame(&Frame);
LABEL_17:
  if ( !v32 )
  {
    FusionpDbgPrintEx(0x80000002, "SXS.DLL: KeyForm %S is missing in system install map.\n", a3);
    goto LABEL_19;
  }
  SetLastError(0);
  if ( a1 )
  {
    if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Format(
                          &v50,
                          L"%u.%u",
                          *((unsigned __int16 *)a4 + 3),
                          *((unsigned __int16 *)a4 + 2)) )
    {
      *v45 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18006DAF8);
      goto LABEL_20;
    }
  }
  else
  {
    phkResult = (PHKEY)&v33;
    if ( !(unsigned int)FusionpRegQuerySzValueEx(0, v32, &qword_18007EBE0, &v50) )
    {
      *v45 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075D10);
      goto LABEL_20;
    }
  }
  SetLastError(0);
  if ( CRegKey::OpenSubKey((CRegKey *)&v32, (struct CRegKey *)&v34, InlineBuffer, v27, (unsigned int)phkResult) )
  {
    v9 = v34;
    if ( !v34 )
    {
      FusionpDbgPrintEx(
        0x80000002,
        "SXS.DLL: KeyForm %S Version %S is missing in system install map.\n",
        a3,
        InlineBuffer);
      goto LABEL_19;
    }
    SetLastError(0);
    if ( (unsigned int)FusionpRegQuerySzValueEx(0, v9, &qword_18007EBE0, &v50) )
    {
      if ( !v54 )
        goto LABEL_19;
      SetLastError(0);
      if ( (unsigned int)CFusionParser::ParseVersion(
                           (union _ASSEMBLY_VERSION *)&v36,
                           InlineBuffer,
                           (unsigned __int64)v54,
                           &v31) )
      {
        if ( !v31 )
          goto LABEL_19;
        *a5 = 1;
        if ( a1 )
        {
          if ( v36 < *(_QWORD *)a4 )
            goto LABEL_19;
        }
        SetLastError(0);
        if ( (unsigned int)SxspSetAssemblyIdentityAttributeValue(
                             1u,
                             v37,
                             (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_version,
                             InlineBuffer,
                             v54) )
        {
          *a6 = 1;
          goto LABEL_19;
        }
        *v45 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075C90);
      }
      else
      {
        *v45 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075CB0);
      }
    }
    else
    {
      *v45 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075CD0);
    }
  }
  else
  {
    *v45 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075CF0);
    v9 = v34;
  }
LABEL_20:
  v17 = v39;
  v50 = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  if ( InlineBuffer != (unsigned __int16 *)&v55 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(&v50);
  InlineBuffer = 0;
  v50 = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  v53 = 0;
  v18 = GetLastError();
  if ( (unsigned __int64)v9 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v19 = RegCloseKey(v9);
    if ( v19 )
      SetLastError(v19);
  }
  SetLastError(v18);
  v20 = GetLastError();
  if ( (unsigned __int64)v32 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v21 = RegCloseKey(v32);
    if ( v21 )
      SetLastError(v21);
  }
  SetLastError(v20);
  v22 = GetLastError();
  v23 = hKey;
  v24 = v22;
  hKey = 0;
  if ( (unsigned __int64)v23 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v25 = RegCloseKey(v23);
    if ( v25 )
      SetLastError(v25);
  }
  SetLastError(v24);
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v45 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      v29 = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(v29, 0);
    }
  }
  RtlPopFrame(&v42);
  return v17;
}

```

## disassembly

```asm
0x180026a60  mov     [rsp-8+arg_0], rbx
0x180026a65  push    rbp
0x180026a66  push    rsi
0x180026a67  push    rdi
0x180026a68  push    r12
0x180026a6a  push    r13
0x180026a6c  push    r14
0x180026a6e  push    r15
0x180026a70  lea     rbp, [rsp-0C0h]
0x180026a78  sub     rsp, 1C0h
0x180026a7f  mov     rax, cs:__security_cookie
0x180026a86  xor     rax, rsp
0x180026a89  mov     [rbp+0F0h+var_40], rax
0x180026a90  mov     r13, [rbp+0F0h+arg_20]
0x180026a97  lea     rax, qword_18006D700
0x180026a9e  mov     r12, [rbp+0F0h+arg_28]
0x180026aa5  movzx   r15d, cl
0x180026aa9  mov     [rbp+0F0h+var_158.Context], rax
0x180026aad  lea     rcx, [rbp+0F0h+var_158]; this
0x180026ab1  lea     rax, [rbp+0F0h+var_170]
0x180026ab5  mov     [rsp+1F0h+var_180], rdx
0x180026aba  xor     ebx, ebx
0x180026abc  mov     [rbp+0F0h+var_130], rax
0x180026ac0  mov     r14, r9
0x180026ac3  mov     [rbp+0F0h+var_170], ebx
0x180026ac6  mov     rdi, r8
0x180026ac9  mov     [rbp+0F0h+var_158.Flags], 1
0x180026ad0  mov     [rbp+0F0h+var_158.Previous], rbx
0x180026ad4  mov     [rbp+0F0h+var_140], 20737853h
0x180026adc  mov     [rbp+0F0h+var_138], 3EFh
0x180026ae3  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180026ae8  lea     rax, ??_7?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable'
0x180026aef  mov     [rbp+0F0h+hKey], rbx
0x180026af3  lea     rcx, [rbp+0F0h+var_F0]
0x180026af7  mov     [rbp+0F0h+var_F0], rax
0x180026afb  mov     [rsp+1F0h+var_1A8], rbx
0x180026b00  mov     esi, ebx
0x180026b02  mov     [rsp+1F0h+var_198], rbx
0x180026b07  mov     [rsp+1F0h+var_188], rbx
0x180026b0c  mov     [rbp+0F0h+var_E8], ebx
0x180026b0f  mov     [rbp+0F0h+var_E0], rbx
0x180026b13  mov     [rbp+0F0h+var_D8], rbx
0x180026b17  mov     [rbp+0F0h+var_D0], rbx
0x180026b1b  mov     [rbp+0F0h+var_C8], bx
0x180026b1f  call    ?GetInlineBuffer@?$CGenericStringBuffer@$00VCUnicodeCharTraits@@@@MEBAPEAGXZ; CGenericStringBuffer<1,CUnicodeCharTraits>::GetInlineBuffer(void)
0x180026b24  mov     [rbp+0F0h+var_E0], rax
0x180026b28  lea     rcx, [rbp+0F0h+var_F0]
0x180026b2c  mov     rax, [rbp+0F0h+var_F0]
0x180026b30  mov     rax, [rax+18h]
0x180026b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b39  mov     [rbp+0F0h+var_D8], rax
0x180026b3d  call    Feature_Servicing_SxS_NullTerminateFix__private_IsEnabledDeviceUsageNoInline
0x180026b42  test    eax, eax
0x180026b44  jz      short loc_180026B58
0x180026b46  mov     r8, [rbp+0F0h+var_D8]
0x180026b4a  xor     edx, edx; Val
0x180026b4c  mov     rcx, [rbp+0F0h+var_E0]; void *
0x180026b50  add     r8, r8; Size
0x180026b53  call    memset_0
0x180026b58  xor     ecx, ecx; dwErrCode
0x180026b5a  mov     [rsp+1F0h+var_1B0], bl
0x180026b5e  mov     [rsp+1F0h+var_1A0], ebx
0x180026b62  call    cs:__imp_SetLastError
0x180026b69  nop     dword ptr [rax+rax+00h]
0x180026b6e  lea     r8, [rbp+0F0h+hKey]; struct CRegKey *
0x180026b72  call    ?SxspOpenAssemblyWinnersKey@@YAHKKAEAVCRegKey@@@Z; SxspOpenAssemblyWinnersKey(ulong,ulong,CRegKey &)
0x180026b77  test    eax, eax
0x180026b79  jz      loc_180026F87
0x180026b7f  cmp     [rbp+0F0h+hKey], rbx
0x180026b83  jz      loc_180026CAA
0x180026b89  xor     ecx, ecx; dwErrCode
0x180026b8b  call    cs:__imp_SetLastError
0x180026b92  nop     dword ptr [rax+rax+00h]
0x180026b97  lea     rax, qword_18006D380
0x180026b9e  mov     [rbp+0F0h+var_160], ebx
0x180026ba1  mov     [rbp+0F0h+Frame.Context], rax
0x180026ba5  lea     rcx, [rbp+0F0h+Frame]; this
0x180026ba9  lea     rax, [rbp+0F0h+var_160]
0x180026bad  mov     [rbp+0F0h+Frame.Flags], 1
0x180026bb4  mov     [rbp+0F0h+var_100], rax
0x180026bb8  mov     [rbp+0F0h+Frame.Previous], rbx
0x180026bbc  mov     [rbp+0F0h+var_110], 20737853h
0x180026bc4  mov     [rbp+0F0h+var_108], 1FBh
0x180026bcb  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180026bd0  mov     rcx, [rbp+0F0h+hKey]; hKey
0x180026bd4  lea     rax, [rsp+1F0h+var_178]
0x180026bd9  mov     r9d, 20119h; samDesired
0x180026bdf  mov     [rsp+1F0h+phkResult], rax; unsigned int
0x180026be4  xor     r8d, r8d; ulOptions
0x180026be7  mov     [rsp+1F0h+var_178], rbx
0x180026bec  mov     rdx, rdi; lpSubKey
0x180026bef  mov     [rsp+1F0h+var_190], 2
0x180026bf7  mov     [rsp+1F0h+var_18C], 3
0x180026bff  call    cs:__imp_RegOpenKeyExW
0x180026c06  nop     dword ptr [rax+rax+00h]
0x180026c0b  test    eax, eax
0x180026c0d  jz      short loc_180026C32
0x180026c0f  mov     edx, ebx
0x180026c11  cmp     edx, 2
0x180026c14  jnb     short loc_180026C2C
0x180026c16  mov     ecx, edx
0x180026c18  cmp     [rsp+rcx*4+1F0h+var_190], eax
0x180026c1c  jnz     loc_180026F63
0x180026c22  mov     rax, rbx
0x180026c25  mov     [rsp+1F0h+var_178], rbx
0x180026c2a  jmp     short loc_180026C37
0x180026c2c  jz      loc_180026F9E
0x180026c32  mov     rax, [rsp+1F0h+var_178]
0x180026c37  mov     rcx, [rsp+1F0h+var_1A8]
0x180026c3c  test    rax, rax
0x180026c3f  cmovnz  rcx, rax
0x180026c43  mov     [rsp+1F0h+var_1A8], rcx
0x180026c48  xor     ecx, ecx; dwErrCode
0x180026c4a  call    cs:__imp_SetLastError
0x180026c51  nop     dword ptr [rax+rax+00h]
0x180026c56  mov     rax, [rbp+0F0h+var_100]
0x180026c5a  mov     dword ptr [rax], 1
0x180026c60  cmp     cs:g_FusionEnterExitTracingEnabled, sil
0x180026c67  mov     rax, [rbp+0F0h+var_100]
0x180026c6b  mov     ebx, [rax]
0x180026c6d  jnz     loc_180026FBD
0x180026c73  lea     rcx, [rbp+0F0h+Frame]; Frame
0x180026c77  call    cs:__imp_RtlPopFrame
0x180026c7e  nop     dword ptr [rax+rax+00h]
0x180026c83  test    ebx, ebx
0x180026c85  jz      loc_180027002
0x180026c8b  cmp     [rsp+1F0h+var_1A8], rsi
0x180026c90  jnz     loc_180026DF3
0x180026c96  mov     r8, rdi
0x180026c99  lea     rdx, aSxsDllKeyformS_0; "SXS.DLL: KeyForm %S is missing in syste"...
0x180026ca0  mov     ecx, 80000002h; unsigned int
0x180026ca5  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180026caa  mov     [rbp+0F0h+var_170], 1
0x180026cb1  xor     r14d, r14d
0x180026cb4  mov     rdx, [rbp+0F0h+var_E0]
0x180026cb8  lea     rax, ??_7?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable'
0x180026cbf  mov     edi, [rbp+0F0h+var_170]
0x180026cc2  mov     [rbp+0F0h+var_F0], rax
0x180026cc6  lea     rax, [rbp+0F0h+var_C8]
0x180026cca  cmp     rdx, rax
0x180026ccd  jz      short loc_180026CD8
0x180026ccf  lea     rcx, [rbp+0F0h+var_F0]
0x180026cd3  call    ?DeallocateBuffer@?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@MEBAXPEAG@Z; CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(ushort *)
0x180026cd8  lea     rax, ??_7?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@6B@; const CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable'
0x180026cdf  mov     [rbp+0F0h+var_E0], r14
0x180026ce3  mov     [rbp+0F0h+var_F0], rax
0x180026ce7  mov     [rbp+0F0h+var_D8], r14
0x180026ceb  call    cs:__imp_GetLastError
0x180026cf2  nop     dword ptr [rax+rax+00h]
0x180026cf7  mov     ebx, eax
0x180026cf9  lea     rax, [rsi-1]
0x180026cfd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026d01  ja      short loc_180026D1A
0x180026d03  mov     rcx, rsi; hKey
0x180026d06  call    cs:__imp_RegCloseKey
0x180026d0d  nop     dword ptr [rax+rax+00h]
0x180026d12  test    eax, eax
0x180026d14  jnz     loc_1800270E3
0x180026d1a  mov     ecx, ebx; dwErrCode
0x180026d1c  call    cs:__imp_SetLastError
0x180026d23  nop     dword ptr [rax+rax+00h]
0x180026d28  call    cs:__imp_GetLastError
0x180026d2f  nop     dword ptr [rax+rax+00h]
0x180026d34  mov     rcx, [rsp+1F0h+var_1A8]; hKey
0x180026d39  mov     ebx, eax
0x180026d3b  lea     rax, [rcx-1]
0x180026d3f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026d43  ja      short loc_180026D59
0x180026d45  call    cs:__imp_RegCloseKey
0x180026d4c  nop     dword ptr [rax+rax+00h]
0x180026d51  test    eax, eax
0x180026d53  jnz     loc_1800270F6
0x180026d59  mov     ecx, ebx; dwErrCode
0x180026d5b  call    cs:__imp_SetLastError
0x180026d62  nop     dword ptr [rax+rax+00h]
0x180026d67  call    cs:__imp_GetLastError
0x180026d6e  nop     dword ptr [rax+rax+00h]
0x180026d73  mov     rcx, [rbp+0F0h+hKey]; hKey
0x180026d77  mov     ebx, eax
0x180026d79  mov     [rbp+0F0h+hKey], r14
0x180026d7d  lea     rax, [rcx-1]
0x180026d81  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026d85  ja      short loc_180026D9B
0x180026d87  call    cs:__imp_RegCloseKey
0x180026d8e  nop     dword ptr [rax+rax+00h]
0x180026d93  test    eax, eax
0x180026d95  jnz     loc_180027109
0x180026d9b  mov     ecx, ebx; dwErrCode
0x180026d9d  call    cs:__imp_SetLastError
0x180026da4  nop     dword ptr [rax+rax+00h]
0x180026da9  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180026db0  jnz     loc_18002711C
0x180026db6  lea     rcx, [rbp+0F0h+var_158]; Frame
0x180026dba  call    cs:__imp_RtlPopFrame
0x180026dc1  nop     dword ptr [rax+rax+00h]
0x180026dc6  mov     eax, edi
0x180026dc8  mov     rcx, [rbp+0F0h+var_40]
0x180026dcf  xor     rcx, rsp; StackCookie
0x180026dd2  call    __security_check_cookie
0x180026dd7  mov     rbx, [rsp+1F0h+arg_0]
0x180026ddf  add     rsp, 1C0h
0x180026de6  pop     r15
0x180026de8  pop     r14
0x180026dea  pop     r13
0x180026dec  pop     r12
0x180026dee  pop     rdi
0x180026def  pop     rsi
0x180026df0  pop     rbp
0x180026df1  retn
0x180026df3  xor     ecx, ecx; dwErrCode
0x180026df5  call    cs:__imp_SetLastError
0x180026dfc  nop     dword ptr [rax+rax+00h]
0x180026e01  test    r15b, r15b
0x180026e04  jz      loc_18002701D
0x180026e0a  movzx   r9d, word ptr [r14+4]
0x180026e0f  lea     rdx, aUU; "%u.%u"
0x180026e16  movzx   r8d, word ptr [r14+6]
0x180026e1b  lea     rcx, [rbp+0F0h+var_F0]
0x180026e1f  call    ?Win32Format@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBGZZ; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Format(ushort const *,...)
0x180026e24  test    eax, eax
0x180026e26  jz      loc_180026F39
0x180026e2c  xor     ecx, ecx; dwErrCode
0x180026e2e  call    cs:__imp_SetLastError
0x180026e35  nop     dword ptr [rax+rax+00h]
0x180026e3a  mov     r8, [rbp+0F0h+var_E0]; unsigned __int16 *
0x180026e3e  lea     rdx, [rsp+1F0h+var_198]; struct CRegKey *
0x180026e43  lea     rcx, [rsp+1F0h+var_1A8]; this
0x180026e48  call    ?OpenSubKey@CRegKey@@QEBAHAEAV1@PEBGKK@Z; CRegKey::OpenSubKey(CRegKey &,ushort const *,ulong,ulong)
0x180026e4d  test    eax, eax
0x180026e4f  jz      loc_180027072
0x180026e55  mov     rsi, [rsp+1F0h+var_198]
0x180026e5a  test    rsi, rsi
0x180026e5d  jz      loc_180026F6A
0x180026e63  xor     ecx, ecx; dwErrCode
0x180026e65  call    cs:__imp_SetLastError
0x180026e6c  nop     dword ptr [rax+rax+00h]
0x180026e71  lea     rax, [rsp+1F0h+var_1A0]
0x180026e76  mov     [rsp+1F0h+var_1C0], 2
0x180026e7e  mov     [rsp+1F0h+var_1C8], 1
0x180026e87  lea     r9, [rbp+0F0h+var_F0]
0x180026e8b  lea     r8, qword_18007EBE0
0x180026e92  mov     [rsp+1F0h+phkResult], rax
0x180026e97  mov     rdx, rsi
0x180026e9a  xor     ecx, ecx
0x180026e9c  call    ?FusionpRegQuerySzValueEx@@YAHKPEAUHKEY__@@PEBGAEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@AEAK_KZZ; FusionpRegQuerySzValueEx(ulong,HKEY__ *,ushort const *,CGenericBaseStringBuffer<CUnicodeCharTraits> &,ulong &,unsigned __int64,...)
0x180026ea1  test    eax, eax
0x180026ea3  jz      loc_180027092
0x180026ea9  cmp     [rbp+0F0h+var_D0], 0
0x180026eae  jz      loc_180026CAA
0x180026eb4  xor     ecx, ecx; dwErrCode
0x180026eb6  call    cs:__imp_SetLastError
0x180026ebd  nop     dword ptr [rax+rax+00h]
0x180026ec2  mov     r8, [rbp+0F0h+var_D0]; unsigned __int64
0x180026ec6  lea     r9, [rsp+1F0h+var_1B0]; bool *
0x180026ecb  mov     rdx, [rbp+0F0h+var_E0]; unsigned __int16 *
0x180026ecf  lea     rcx, [rsp+1F0h+var_188]; union _ASSEMBLY_VERSION *
0x180026ed4  call    ?ParseVersion@CFusionParser@@SAHAEAT_ASSEMBLY_VERSION@@PEBG_KAEA_N@Z; CFusionParser::ParseVersion(_ASSEMBLY_VERSION &,ushort const *,unsigned __int64,bool &)
0x180026ed9  test    eax, eax
0x180026edb  jz      loc_1800270AD
0x180026ee1  cmp     [rsp+1F0h+var_1B0], 0
0x180026ee6  jz      loc_180026CAA
0x180026eec  mov     byte ptr [r13+0], 1
0x180026ef1  test    r15b, r15b
0x180026ef4  jnz     short loc_180026F54
0x180026ef6  xor     ecx, ecx; dwErrCode
0x180026ef8  call    cs:__imp_SetLastError
0x180026eff  nop     dword ptr [rax+rax+00h]
0x180026f04  mov     rax, [rbp+0F0h+var_D0]
0x180026f08  lea     r8, s_IdentityAttribute_version; struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *
0x180026f0f  mov     r9, [rbp+0F0h+var_E0]; unsigned __int16 *
0x180026f13  mov     ecx, 1; unsigned int
0x180026f18  mov     rdx, [rsp+1F0h+var_180]; struct _ASSEMBLY_IDENTITY *
0x180026f1d  mov     [rsp+1F0h+phkResult], rax; char *
0x180026f22  call    ?SxspSetAssemblyIdentityAttributeValue@@YAHKPEAU_ASSEMBLY_IDENTITY@@PEBU_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE@@PEBG_K@Z; SxspSetAssemblyIdentityAttributeValue(ulong,_ASSEMBLY_IDENTITY *,_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE const *,ushort const *,unsigned __int64)
0x180026f27  test    eax, eax
0x180026f29  jz      loc_1800270C8
0x180026f2f  mov     byte ptr [r12], 1
0x180026f34  jmp     loc_180026CAA
0x180026f39  mov     rax, [rbp+0F0h+var_130]
0x180026f3d  lea     rcx, off_18006DAF8; struct _CALL_SITE_INFO *
0x180026f44  xor     r14d, r14d
0x180026f47  mov     [rax], r14d
0x180026f4a  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180026f4f  jmp     loc_180026CB4
0x180026f54  mov     rax, [r14]
0x180026f57  cmp     [rsp+1F0h+var_188], rax
0x180026f5c  jnb     short loc_180026EF6
0x180026f5e  jmp     loc_180026CAA
0x180026f63  inc     edx
0x180026f65  jmp     loc_180026C11
0x180026f6a  mov     r9, [rbp+0F0h+var_E0]
0x180026f6e  lea     rdx, aSxsDllKeyformS; "SXS.DLL: KeyForm %S Version %S is missi"...
0x180026f75  mov     r8, rdi
0x180026f78  mov     ecx, 80000002h; unsigned int
0x180026f7d  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180026f82  jmp     loc_180026CAA
0x180026f87  mov     rax, [rbp+0F0h+var_130]
0x180026f8b  lea     rcx, off_180075D50; struct _CALL_SITE_INFO *
0x180026f92  mov     [rax], ebx
0x180026f94  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
  ... truncated ...
```
