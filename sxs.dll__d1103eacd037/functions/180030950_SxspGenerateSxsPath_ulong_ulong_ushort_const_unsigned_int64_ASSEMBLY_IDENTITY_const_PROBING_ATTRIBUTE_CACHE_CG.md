# SxspGenerateSxsPath(ulong,ulong,ushort const *,unsigned __int64,_ASSEMBLY_IDENTITY const *,_PROBING_ATTRIBUTE_CACHE *,CGenericBaseStringBuffer<CUnicodeCharTraits> &)

- ea: `0x180030950`
- end: `0x180031255`
- name: `?SxspGenerateSxsPath@@YAHKKPEBG_KPEBU_ASSEMBLY_IDENTITY@@PEAU_PROBING_ATTRIBUTE_CACHE@@AEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z`
- size: `2309`
- prototype: `__int64 __fastcall(int, int, int, int, struct _ASSEMBLY_IDENTITY *, int, __int64)`
- caller_count: `3`
- callee_count: `22`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180011de0`
- `0x180060390`
- `0x180062568`

## callees

- `0x1800075a0`
- `0x18000a804`
- `0x18000df40`
- `0x18000dffc`
- `0x180013af0`
- `0x180014260`
- `0x180019740`
- `0x18001c320`
- `0x18001e5c0`
- `0x180022f90`
- `0x1800265b0`
- `0x18002faa4`
- `0x180030480`
- `0x180030950`
- `0x180032350`
- `0x18005b8a0`
- `0x18005d2b0`
- `0x180067548`
- `0x180067680`
- `0x18006a0f5`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x180030fbc`
- `ntdll!RtlPopFrame` at `0x180030fbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003123b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003123b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030afa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030b46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030b99`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030bd0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030c07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030c3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030d10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030d46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030d6d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030dcf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030e6b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030e8d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030eef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030f18`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031049`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031142`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030afa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030b46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030b99`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030bd0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030c07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030c3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030d10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030d46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030d6d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030dcf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030e6b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030e8d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030eef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030f18`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031049`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031142`

## string_xrefs

- `0x180030ea8`: `manifests`

## pseudocode

```c
__int64 __fastcall SxspGenerateSxsPath(
        __int64 a1,
        __int64 a2,
        const void *a3,
        size_t a4,
        struct _ASSEMBLY_IDENTITY *a5,
        int a6,
        __int64 a7)
{
  const char *v9; // rcx
  unsigned __int16 *v10; // rdi
  unsigned __int64 v11; // rsi
  __int64 v12; // r14
  unsigned int v13; // ebx
  DWORD v15; // ecx
  DWORD LastError; // eax
  bool v17; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v18; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v19; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v20; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v21; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v22; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v23; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v24; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v25; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v26; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v27; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v28[2]; // [rsp+B8h] [rbp-48h] BYREF
  char *v29; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v30[3]; // [rsp+D0h] [rbp-30h] BYREF
  int v31; // [rsp+E8h] [rbp-18h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v33; // [rsp+108h] [rbp+8h]
  int v34; // [rsp+110h] [rbp+10h]
  int *v35; // [rsp+118h] [rbp+18h]
  void **v36; // [rsp+120h] [rbp+20h] BYREF
  int v37; // [rsp+128h] [rbp+28h]
  void *v38; // [rsp+130h] [rbp+30h]
  __int64 v39; // [rsp+138h] [rbp+38h]
  __int64 v40; // [rsp+140h] [rbp+40h]
  __int16 v41; // [rsp+148h] [rbp+48h] BYREF
  void **v42; // [rsp+1D0h] [rbp+D0h] BYREF
  int v43; // [rsp+1D8h] [rbp+D8h]
  void *v44; // [rsp+1E0h] [rbp+E0h]
  __int64 v45; // [rsp+1E8h] [rbp+E8h]
  __int64 v46; // [rsp+1F0h] [rbp+F0h]
  _WORD v47[260]; // [rsp+1F8h] [rbp+F8h] BYREF
  void **v48; // [rsp+400h] [rbp+300h] BYREF
  int v49; // [rsp+408h] [rbp+308h]
  void *InlineBuffer; // [rsp+410h] [rbp+310h]
  __int64 v51; // [rsp+418h] [rbp+318h]
  __int64 v52; // [rsp+420h] [rbp+320h]
  __int16 v53; // [rsp+428h] [rbp+328h] BYREF
  char v54; // [rsp+630h] [rbp+530h] BYREF
  char v55; // [rsp+750h] [rbp+650h] BYREF

  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006E288;
  v31 = 0;
  v35 = &v31;
  Frame.Flags = 1;
  Frame.Previous = 0;
  v33 = 544438355;
  v34 = 531;
  CFrame::BaseEnter((CFrame *)&Frame);
  v19 = 0;
  v29 = &v54;
  v21 = 0;
  v48 = &CGenericStringBuffer<260,CUnicodeCharTraits>::`vftable';
  v25 = 0;
  v23 = 0;
  v27 = 0;
  v20 = 0;
  v26 = 0;
  v18 = 0;
  v24 = 0;
  v22 = 0;
  v28[0] = 0;
  v28[1] = 280;
  v49 = 0;
  InlineBuffer = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  InlineBuffer = (void *)CGenericStringBuffer<1,CUnicodeCharTraits>::GetInlineBuffer(&v48);
  v51 = ((__int64 (__fastcall *)(void ***))v48[3])(&v48);
  if ( (unsigned int)Feature_Servicing_SxS_NullTerminateFix__private_IsEnabledDeviceUsageNoInline() )
    memset_0(InlineBuffer, 0, 2 * v51);
  v37 = 0;
  v36 = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v38 = (void *)CGenericStringBuffer<1,CUnicodeCharTraits>::GetInlineBuffer(&v36);
  v39 = ((__int64 (__fastcall *)(void ***))v36[3])(&v36);
  if ( (unsigned int)Feature_Servicing_SxS_NullTerminateFix__private_IsEnabledDeviceUsageNoInline() )
    memset_0(v38, 0, 2 * v39);
  if ( !a5 )
  {
    v34 = 567;
LABEL_45:
    FusionpTraceParameterCheck(v9);
    v15 = 87;
LABEL_47:
    SetLastError(v15);
    *v35 = 0;
    goto LABEL_35;
  }
  if ( !a4 )
  {
    v34 = 569;
    goto LABEL_45;
  }
  SetLastError(0);
  if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                        0,
                        a5,
                        (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_name,
                        (const unsigned __int16 **)&v19,
                        &v20) )
  {
    *v35 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180076010);
    goto LABEL_35;
  }
  if ( !v19 || !v20 )
  {
    v15 = 1359;
    goto LABEL_47;
  }
  SetLastError(0);
  if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                        1u,
                        a5,
                        (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_version,
                        (const unsigned __int16 **)&v21,
                        &v18) )
  {
    *v35 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075FF0);
    goto LABEL_35;
  }
  v10 = v21;
  if ( !v21 || (v11 = v18) == 0 )
  {
    v34 = 623;
    goto LABEL_45;
  }
  SetLastError(0);
  if ( (unsigned int)SxspGetAssemblyIdentityAttributeValue(
                       1u,
                       a5,
                       (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_language,
                       (const unsigned __int16 **)&v23,
                       &v22) )
  {
    SetLastError(0);
    if ( (unsigned int)SxspGetAssemblyIdentityAttributeValue(
                         1u,
                         a5,
                         (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_processorArchitecture,
                         (const unsigned __int16 **)&v25,
                         &v24) )
    {
      SetLastError(0);
      if ( (unsigned int)SxspGetAssemblyIdentityAttributeValue(
                           1u,
                           a5,
                           (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_publicKeyToken,
                           (const unsigned __int16 **)&v27,
                           &v26) )
      {
        SetLastError(0);
        if ( (unsigned int)SxspGenerateKeyform(0, a5, (struct _LUNICODE_STRING *)v28) )
        {
          v42 = &CGenericStringBuffer<260,CUnicodeCharTraits>::`vftable';
          v12 = v28[0] >> 1;
          v43 = 0;
          v44 = 0;
          v45 = 0;
          v46 = 0;
          v47[0] = 0;
          v44 = (void *)CGenericStringBuffer<1,CUnicodeCharTraits>::GetInlineBuffer(&v42);
          v45 = ((__int64 (__fastcall *)(void ***))v42[3])(&v42);
          if ( (unsigned int)Feature_Servicing_SxS_NullTerminateFix__private_IsEnabledDeviceUsageNoInline() )
            memset_0(v44, 0, 2 * v45);
          v30[1] = 280;
          v18 = 0;
          v30[0] = 0;
          v30[2] = (unsigned __int64)&v55;
          v17 = 0;
          SetLastError(0);
          if ( (unsigned int)CFusionParser::ParseVersion((union _ASSEMBLY_VERSION *)&v18, v10, v11, &v17) )
          {
            if ( v17 )
            {
              SetLastError(0);
              if ( (unsigned int)SxspGenerateKeyform(1, a5, (struct _LUNICODE_STRING *)v30) )
              {
                SetLastError(0);
                if ( (unsigned int)SxspGetFusionRootInstalledPath(
                                     1,
                                     2,
                                     a3,
                                     a4,
                                     (__int64)a5,
                                     v30,
                                     v28,
                                     (unsigned __int16 *)&v18,
                                     (__int64)&v42) )
                {
                  if ( *(_WORD *)v44 )
                  {
                    SetLastError(0);
                    if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(
                                         a7,
                                         (char *)v44 + 2 * a4,
                                         v46 - a4) )
                    {
                      v31 = 1;
                      v42 = &CGenericStringBuffer<260,CUnicodeCharTraits>::`vftable';
                      if ( v44 != v47 )
                        CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(&v42);
                    }
                    else
                    {
                      *v35 = 0;
                      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075ED0);
                      CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(&v42);
                    }
                  }
                  else
                  {
                    v42 = &CGenericStringBuffer<260,CUnicodeCharTraits>::`vftable';
                    if ( v44 != v47 )
                      CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(&v42);
                    SetLastError(0);
                    if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32ResizeBuffer(a7, v12 + 2) )
                    {
                      SetLastError(0);
                      if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32AssignW(
                                           a7,
                                           5,
                                           a3,
                                           0,
                                           L"\\",
                                           0,
                                           L"manifests",
                                           0,
                                           0,
                                           0) )
                      {
                        SetLastError(0);
                        if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Append(
                                             a7,
                                             v29,
                                             v28[0] >> 1) )
                        {
                          SetLastError(0);
                          if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Append(a7, L"\\", 0) )
                          {
                            v31 = 1;
                          }
                          else
                          {
                            *v35 = 0;
                            FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075E90);
                          }
                        }
                        else
                        {
                          *v35 = 0;
                          FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075EB0);
                        }
                      }
                      else
                      {
                        *v35 = 0;
                        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18006FC50);
                      }
                    }
                    else
                    {
                      *v35 = 0;
                      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18006FC30);
                    }
                  }
                }
                else
                {
                  *v35 = 0;
                  FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075EF0);
                  CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(&v42);
                }
              }
              else
              {
                *v35 = 0;
                FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075F10);
                CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(&v42);
              }
            }
            else
            {
              SetLastError(0x36C1u);
              *v35 = 0;
              FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180075F30);
              CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(&v42);
            }
          }
          else
          {
            *v35 = 0;
            FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075F50);
            CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(&v42);
          }
        }
        else
        {
          *v35 = 0;
          FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075F70);
        }
      }
      else
      {
        *v35 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075F90);
      }
    }
    else
    {
      *v35 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075FB0);
    }
  }
  else
  {
    *v35 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075FD0);
  }
LABEL_35:
  v13 = v31;
  v36 = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  if ( v38 != &v41 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(&v36);
  v38 = 0;
  v39 = 0;
  v36 = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  v48 = &CGenericStringBuffer<260,CUnicodeCharTraits>::`vftable';
  if ( InlineBuffer != &v53 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(&v48);
  InlineBuffer = 0;
  v51 = 0;
  v48 = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v35 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      LastError = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v13;
}

```

## disassembly

```asm
0x180030950  mov     [rsp-8+arg_0], rbx
0x180030955  push    rbp
0x180030956  push    rsi
0x180030957  push    rdi
0x180030958  push    r12
0x18003095a  push    r13
0x18003095c  push    r14
0x18003095e  push    r15
0x180030960  lea     rbp, [rsp-780h]
0x180030968  sub     rsp, 880h
0x18003096f  mov     rax, cs:__security_cookie
0x180030976  xor     rax, rsp
0x180030979  mov     [rbp+7B0h+var_40], rax
0x180030980  mov     rbx, [rbp+7B0h+arg_20]
0x180030987  lea     rax, qword_18006E288
0x18003098e  mov     r12, [rbp+7B0h+arg_30]
0x180030995  lea     rcx, [rbp+7B0h+Frame]; this
0x180030999  mov     [rbp+7B0h+Frame.Context], rax
0x18003099d  xor     r14d, r14d
0x1800309a0  lea     rax, [rbp+7B0h+var_7C8]
0x1800309a4  mov     [rbp+7B0h+var_7C8], r14d
0x1800309a8  mov     [rbp+7B0h+var_798], rax
0x1800309ac  mov     r15, r9
0x1800309af  mov     r13, r8
0x1800309b2  mov     [rbp+7B0h+Frame.Flags], 1
0x1800309b9  mov     [rbp+7B0h+Frame.Previous], r14
0x1800309bd  mov     [rbp+7B0h+var_7A8], 20737853h
0x1800309c5  mov     [rbp+7B0h+var_7A0], 213h
0x1800309cc  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x1800309d1  lea     rax, [rbp+7B0h+var_280]
0x1800309d8  mov     [rsp+8B0h+var_840], r14
0x1800309dd  mov     [rbp+7B0h+var_7E8], rax
0x1800309e1  lea     rcx, [rbp+7B0h+var_4B0]
0x1800309e8  lea     rax, ??_7?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<260,CUnicodeCharTraits>::`vftable'
0x1800309ef  mov     [rbp+7B0h+var_830], r14
0x1800309f3  mov     [rbp+7B0h+var_4B0], rax
0x1800309fa  mov     [rbp+7B0h+var_810], r14
0x1800309fe  mov     [rbp+7B0h+var_820], r14
0x180030a02  mov     [rbp+7B0h+var_800], r14
0x180030a06  mov     [rsp+8B0h+var_838], r14
0x180030a0b  mov     [rbp+7B0h+var_808], r14
0x180030a0f  mov     [rsp+8B0h+var_848], r14
0x180030a14  mov     [rbp+7B0h+var_818], r14
0x180030a18  mov     [rbp+7B0h+var_828], r14
0x180030a1c  mov     [rbp+7B0h+var_7F8], r14
0x180030a20  mov     [rbp+7B0h+var_7F0], 118h
0x180030a28  mov     [rbp+7B0h+var_4A8], r14d
0x180030a2f  mov     [rbp+7B0h+var_4A0], r14
0x180030a36  mov     [rbp+7B0h+var_498], r14
0x180030a3d  mov     [rbp+7B0h+var_490], r14
0x180030a44  mov     [rbp+7B0h+var_488], r14w
0x180030a4c  call    ?GetInlineBuffer@?$CGenericStringBuffer@$00VCUnicodeCharTraits@@@@MEBAPEAGXZ; CGenericStringBuffer<1,CUnicodeCharTraits>::GetInlineBuffer(void)
0x180030a51  mov     [rbp+7B0h+var_4A0], rax
0x180030a58  lea     rcx, [rbp+7B0h+var_4B0]
0x180030a5f  mov     rax, [rbp+7B0h+var_4B0]
0x180030a66  mov     rax, [rax+18h]
0x180030a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a6f  mov     [rbp+7B0h+var_498], rax
0x180030a76  call    Feature_Servicing_SxS_NullTerminateFix__private_IsEnabledDeviceUsageNoInline
0x180030a7b  test    eax, eax
0x180030a7d  jz      short loc_180030A97
0x180030a7f  mov     r8, [rbp+7B0h+var_498]
0x180030a86  xor     edx, edx; Val
0x180030a88  mov     rcx, [rbp+7B0h+var_4A0]; void *
0x180030a8f  add     r8, r8; Size
0x180030a92  call    memset_0
0x180030a97  lea     rax, ??_7?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable'
0x180030a9e  mov     [rbp+7B0h+var_788], r14d
0x180030aa2  lea     rcx, [rbp+7B0h+var_790]
0x180030aa6  mov     [rbp+7B0h+var_790], rax
0x180030aaa  mov     [rbp+7B0h+var_780], r14
0x180030aae  mov     [rbp+7B0h+var_778], r14
0x180030ab2  mov     [rbp+7B0h+var_770], r14
0x180030ab6  mov     [rbp+7B0h+var_768], r14w
0x180030abb  call    ?GetInlineBuffer@?$CGenericStringBuffer@$00VCUnicodeCharTraits@@@@MEBAPEAGXZ; CGenericStringBuffer<1,CUnicodeCharTraits>::GetInlineBuffer(void)
0x180030ac0  mov     [rbp+7B0h+var_780], rax
0x180030ac4  lea     rcx, [rbp+7B0h+var_790]
0x180030ac8  mov     rax, [rbp+7B0h+var_790]
0x180030acc  mov     rax, [rax+18h]
0x180030ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ad5  mov     [rbp+7B0h+var_778], rax
0x180030ad9  call    Feature_Servicing_SxS_NullTerminateFix__private_IsEnabledDeviceUsageNoInline
0x180030ade  test    eax, eax
0x180030ae0  jnz     loc_180030E34
0x180030ae6  test    rbx, rbx
0x180030ae9  jz      loc_180031028
0x180030aef  test    r15, r15
0x180030af2  jz      loc_18003108C
0x180030af8  xor     ecx, ecx; dwErrCode
0x180030afa  call    cs:__imp_SetLastError
0x180030b01  nop     dword ptr [rax+rax+00h]
0x180030b06  lea     rax, [rsp+8B0h+var_838]
0x180030b0b  mov     rdx, rbx; struct _ASSEMBLY_IDENTITY *
0x180030b0e  lea     r9, [rsp+8B0h+var_840]; unsigned __int16 **
0x180030b13  mov     [rsp+8B0h+var_890], rax; unsigned __int64 *
0x180030b18  lea     r8, s_IdentityAttribute_name; struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *
0x180030b1f  xor     ecx, ecx; unsigned int
0x180030b21  call    ?SxspGetAssemblyIdentityAttributeValue@@YAHKPEBU_ASSEMBLY_IDENTITY@@PEBU_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE@@PEAPEBGPEA_K@Z; SxspGetAssemblyIdentityAttributeValue(ulong,_ASSEMBLY_IDENTITY const *,_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE const *,ushort const * *,unsigned __int64 *)
0x180030b26  test    eax, eax
0x180030b28  jz      loc_180031095
0x180030b2e  cmp     [rsp+8B0h+var_840], r14
0x180030b33  jz      loc_180031044
0x180030b39  cmp     [rsp+8B0h+var_838], r14
0x180030b3e  jz      loc_180031044
0x180030b44  xor     ecx, ecx; dwErrCode
0x180030b46  call    cs:__imp_SetLastError
0x180030b4d  nop     dword ptr [rax+rax+00h]
0x180030b52  lea     rax, [rsp+8B0h+var_848]
0x180030b57  mov     rdx, rbx; struct _ASSEMBLY_IDENTITY *
0x180030b5a  lea     r9, [rbp+7B0h+var_830]; unsigned __int16 **
0x180030b5e  mov     [rsp+8B0h+var_890], rax; unsigned __int64 *
0x180030b63  lea     r8, s_IdentityAttribute_version; struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *
0x180030b6a  mov     ecx, 1; unsigned int
0x180030b6f  call    ?SxspGetAssemblyIdentityAttributeValue@@YAHKPEBU_ASSEMBLY_IDENTITY@@PEBU_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE@@PEAPEBGPEA_K@Z; SxspGetAssemblyIdentityAttributeValue(ulong,_ASSEMBLY_IDENTITY const *,_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE const *,ushort const * *,unsigned __int64 *)
0x180030b74  test    eax, eax
0x180030b76  jz      loc_1800310AA
0x180030b7c  mov     rdi, [rbp+7B0h+var_830]
0x180030b80  test    rdi, rdi
0x180030b83  jz      loc_180031031
0x180030b89  mov     rsi, [rsp+8B0h+var_848]
0x180030b8e  test    rsi, rsi
0x180030b91  jz      loc_180031031
0x180030b97  xor     ecx, ecx; dwErrCode
0x180030b99  call    cs:__imp_SetLastError
0x180030ba0  nop     dword ptr [rax+rax+00h]
0x180030ba5  lea     rax, [rbp+7B0h+var_828]
0x180030ba9  mov     rdx, rbx; struct _ASSEMBLY_IDENTITY *
0x180030bac  lea     r9, [rbp+7B0h+var_820]; unsigned __int16 **
0x180030bb0  mov     [rsp+8B0h+var_890], rax; unsigned __int64 *
0x180030bb5  lea     r8, s_IdentityAttribute_language; struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *
0x180030bbc  mov     ecx, 1; unsigned int
0x180030bc1  call    ?SxspGetAssemblyIdentityAttributeValue@@YAHKPEBU_ASSEMBLY_IDENTITY@@PEBU_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE@@PEAPEBGPEA_K@Z; SxspGetAssemblyIdentityAttributeValue(ulong,_ASSEMBLY_IDENTITY const *,_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE const *,ushort const * *,unsigned __int64 *)
0x180030bc6  test    eax, eax
0x180030bc8  jz      loc_1800310BF
0x180030bce  xor     ecx, ecx; dwErrCode
0x180030bd0  call    cs:__imp_SetLastError
0x180030bd7  nop     dword ptr [rax+rax+00h]
0x180030bdc  lea     rax, [rbp+7B0h+var_818]
0x180030be0  mov     rdx, rbx; struct _ASSEMBLY_IDENTITY *
0x180030be3  lea     r9, [rbp+7B0h+var_810]; unsigned __int16 **
0x180030be7  mov     [rsp+8B0h+var_890], rax; unsigned __int64 *
0x180030bec  lea     r8, s_IdentityAttribute_processorArchitecture; struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *
0x180030bf3  mov     ecx, 1; unsigned int
0x180030bf8  call    ?SxspGetAssemblyIdentityAttributeValue@@YAHKPEBU_ASSEMBLY_IDENTITY@@PEBU_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE@@PEAPEBGPEA_K@Z; SxspGetAssemblyIdentityAttributeValue(ulong,_ASSEMBLY_IDENTITY const *,_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE const *,ushort const * *,unsigned __int64 *)
0x180030bfd  test    eax, eax
0x180030bff  jz      loc_1800310D4
0x180030c05  xor     ecx, ecx; dwErrCode
0x180030c07  call    cs:__imp_SetLastError
0x180030c0e  nop     dword ptr [rax+rax+00h]
0x180030c13  lea     rax, [rbp+7B0h+var_808]
0x180030c17  mov     rdx, rbx; struct _ASSEMBLY_IDENTITY *
0x180030c1a  lea     r9, [rbp+7B0h+var_800]; unsigned __int16 **
0x180030c1e  mov     [rsp+8B0h+var_890], rax; unsigned __int64 *
0x180030c23  lea     r8, s_IdentityAttribute_publicKeyToken; struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *
0x180030c2a  mov     ecx, 1; unsigned int
0x180030c2f  call    ?SxspGetAssemblyIdentityAttributeValue@@YAHKPEBU_ASSEMBLY_IDENTITY@@PEBU_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE@@PEAPEBGPEA_K@Z; SxspGetAssemblyIdentityAttributeValue(ulong,_ASSEMBLY_IDENTITY const *,_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE const *,ushort const * *,unsigned __int64 *)
0x180030c34  test    eax, eax
0x180030c36  jz      loc_1800310E9
0x180030c3c  xor     ecx, ecx; dwErrCode
0x180030c3e  call    cs:__imp_SetLastError
0x180030c45  nop     dword ptr [rax+rax+00h]
0x180030c4a  lea     r8, [rbp+7B0h+var_7F8]; struct _LUNICODE_STRING *
0x180030c4e  mov     rdx, rbx; struct _ASSEMBLY_IDENTITY *
0x180030c51  xor     ecx, ecx; unsigned int
0x180030c53  call    ?SxspGenerateKeyform@@YAHKPEBU_ASSEMBLY_IDENTITY@@PEAU_LUNICODE_STRING@@@Z; SxspGenerateKeyform(ulong,_ASSEMBLY_IDENTITY const *,_LUNICODE_STRING *)
0x180030c58  test    eax, eax
0x180030c5a  jz      loc_1800310FE
0x180030c60  mov     r14, [rbp+7B0h+var_7F8]
0x180030c64  lea     rcx, ??_7?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<260,CUnicodeCharTraits>::`vftable'
0x180030c6b  xor     eax, eax
0x180030c6d  mov     [rbp+7B0h+var_6E0], rcx
0x180030c74  lea     rcx, [rbp+7B0h+var_6E0]
0x180030c7b  shr     r14, 1
0x180030c7e  mov     [rbp+7B0h+var_6D8], eax
0x180030c84  mov     [rbp+7B0h+var_6D0], rax
0x180030c8b  mov     [rbp+7B0h+var_6C8], rax
0x180030c92  mov     [rbp+7B0h+var_6C0], rax
0x180030c99  mov     [rbp+7B0h+var_6B8], ax
0x180030ca0  call    ?GetInlineBuffer@?$CGenericStringBuffer@$00VCUnicodeCharTraits@@@@MEBAPEAGXZ; CGenericStringBuffer<1,CUnicodeCharTraits>::GetInlineBuffer(void)
0x180030ca5  mov     [rbp+7B0h+var_6D0], rax
0x180030cac  lea     rcx, [rbp+7B0h+var_6E0]
0x180030cb3  mov     rax, [rbp+7B0h+var_6E0]
0x180030cba  mov     rax, [rax+18h]
0x180030cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030cc3  mov     [rbp+7B0h+var_6C8], rax
0x180030cca  call    Feature_Servicing_SxS_NullTerminateFix__private_IsEnabledDeviceUsageNoInline
0x180030ccf  test    eax, eax
0x180030cd1  jz      short loc_180030CEB
0x180030cd3  mov     r8, [rbp+7B0h+var_6C8]
0x180030cda  xor     edx, edx; Val
0x180030cdc  mov     rcx, [rbp+7B0h+var_6D0]; void *
0x180030ce3  add     r8, r8; Size
0x180030ce6  call    memset_0
0x180030ceb  xor     eax, eax
0x180030ced  mov     [rbp+7B0h+var_7D8], 118h
0x180030cf5  mov     [rsp+8B0h+var_848], rax
0x180030cfa  xor     ecx, ecx; dwErrCode
0x180030cfc  mov     [rbp+7B0h+var_7E0], rax
0x180030d00  lea     rax, [rbp+7B0h+var_160]
0x180030d07  mov     [rbp+7B0h+var_7D0], rax
0x180030d0b  mov     [rsp+8B0h+var_850], 0
0x180030d10  call    cs:__imp_SetLastError
0x180030d17  nop     dword ptr [rax+rax+00h]
0x180030d1c  lea     r9, [rsp+8B0h+var_850]; bool *
0x180030d21  mov     r8, rsi; unsigned __int64
0x180030d24  mov     rdx, rdi; unsigned __int16 *
0x180030d27  lea     rcx, [rsp+8B0h+var_848]; union _ASSEMBLY_VERSION *
0x180030d2c  call    ?ParseVersion@CFusionParser@@SAHAEAT_ASSEMBLY_VERSION@@PEBG_KAEA_N@Z; CFusionParser::ParseVersion(_ASSEMBLY_VERSION &,ushort const *,unsigned __int64,bool &)
0x180030d31  test    eax, eax
0x180030d33  jz      loc_180031116
0x180030d39  cmp     [rsp+8B0h+var_850], 0
0x180030d3e  jz      loc_18003113D
0x180030d44  xor     ecx, ecx; dwErrCode
0x180030d46  call    cs:__imp_SetLastError
0x180030d4d  nop     dword ptr [rax+rax+00h]
0x180030d52  lea     r8, [rbp+7B0h+var_7E0]; struct _LUNICODE_STRING *
0x180030d56  mov     rdx, rbx; struct _ASSEMBLY_IDENTITY *
0x180030d59  mov     ecx, 1; unsigned int
0x180030d5e  call    ?SxspGenerateKeyform@@YAHKPEBU_ASSEMBLY_IDENTITY@@PEAU_LUNICODE_STRING@@@Z; SxspGenerateKeyform(ulong,_ASSEMBLY_IDENTITY const *,_LUNICODE_STRING *)
0x180030d63  test    eax, eax
0x180030d65  jz      loc_180031175
0x180030d6b  xor     ecx, ecx; dwErrCode
0x180030d6d  call    cs:__imp_SetLastError
0x180030d74  nop     dword ptr [rax+rax+00h]
0x180030d79  lea     rax, [rbp+7B0h+var_6E0]
0x180030d80  mov     r9, r15
0x180030d83  mov     [rsp+8B0h+var_870], rax
0x180030d88  mov     r8, r13
0x180030d8b  lea     rax, [rsp+8B0h+var_848]
0x180030d90  mov     edx, 2
0x180030d95  mov     [rsp+8B0h+var_878], rax
0x180030d9a  mov     cl, 1
0x180030d9c  lea     rax, [rbp+7B0h+var_7F8]
0x180030da0  mov     [rsp+8B0h+var_880], rax
0x180030da5  lea     rax, [rbp+7B0h+var_7E0]
0x180030da9  mov     [rsp+8B0h+var_888], rax
0x180030dae  mov     [rsp+8B0h+var_890], rbx
0x180030db3  call    SxspGetFusionRootInstalledPath
0x180030db8  test    eax, eax
0x180030dba  jz      loc_18003119C
0x180030dc0  mov     rdx, [rbp+7B0h+var_6D0]
0x180030dc7  cmp     word ptr [rdx], 0
0x180030dcb  jz      short loc_180030E4B
0x180030dcd  xor     ecx, ecx; dwErrCode
0x180030dcf  call    cs:__imp_SetLastError
0x180030dd6  nop     dword ptr [rax+rax+00h]
0x180030ddb  mov     rax, [rbp+7B0h+var_6D0]
0x180030de2  mov     rcx, r12
0x180030de5  mov     r8, [rbp+7B0h+var_6C0]
0x180030dec  sub     r8, r15
0x180030def  lea     rdx, [rax+r15*2]
0x180030df3  call    ?Win32Assign@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(ushort const *,unsigned __int64)
0x180030df8  test    eax, eax
0x180030dfa  jz      loc_18003105E
0x180030e00  mov     rdx, [rbp+7B0h+var_6D0]
0x180030e07  lea     rax, [rbp+7B0h+var_6B8]
0x180030e0e  mov     [rbp+7B0h+var_7C8], 1
0x180030e15  lea     rsi, ??_7?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<260,CUnicodeCharTraits>::`vftable'
0x180030e1c  mov     [rbp+7B0h+var_6E0], rsi
0x180030e23  cmp     rdx, rax
0x180030e26  jnz     loc_1800311C3
0x180030e2c  xor     r14d, r14d
0x180030e2f  jmp     loc_180030F41
0x180030e34  mov     r8, [rbp+7B0h+var_778]
0x180030e38  xor     edx, edx; Val
0x180030e3a  mov     rcx, [rbp+7B0h+var_780]; void *
0x180030e3e  add     r8, r8; Size
0x180030e41  call    memset_0
0x180030e46  jmp     loc_180030AE6
0x180030e4b  lea     rax, [rbp+7B0h+var_6B8]
0x180030e52  lea     rsi, ??_7?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<260,CUnicodeCharTraits>::`vftable'
0x180030e59  mov     [rbp+7B0h+var_6E0], rsi
0x180030e60  cmp     rdx, rax
0x180030e63  jnz     loc_1800311D4
0x180030e69  xor     ecx, ecx; dwErrCode
0x180030e6b  call    cs:__imp_SetLastError
0x180030e72  nop     dword ptr [rax+rax+00h]
0x180030e77  lea     rdx, [r14+2]
0x180030e7b  mov     rcx, r12
0x180030e7e  call    ?Win32ResizeBuffer@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAH_KW4EPreserveContents@@@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32ResizeBuffer(unsigned __int64,EPreserveContents)
0x180030e83  test    eax, eax
0x180030e85  jz      loc_180030FF5
0x180030e8b  xor     ecx, ecx; dwErrCode
0x180030e8d  call    cs:__imp_SetLastError
0x180030e94  nop     dword ptr [rax+rax+00h]
0x180030e99  xor     r14d, r14d
0x180030e9c  lea     rbx, asc_18007ED8C; "\\"
0x180030ea3  mov     [rsp+8B0h+var_858], r14d
0x180030ea8  lea     rax, aManifests; "manifests"
0x180030eaf  mov     [rsp+8B0h+var_860], rbx
0x180030eb4  xor     r9d, r9d
0x180030eb7  mov     [rsp+8B0h+var_868], r14
0x180030ebc  mov     r8, r13
0x180030ebf  mov     [rsp+8B0h+var_870], r14
0x180030ec4  mov     edx, 5
0x180030ec9  mov     [rsp+8B0h+var_878], r14
0x180030ece  mov     rcx, r12
0x180030ed1  mov     [rsp+8B0h+var_880], rax
0x180030ed6  mov     dword ptr [rsp+8B0h+var_888], r14d
0x180030edb  mov     [rsp+8B0h+var_890], rbx
  ... truncated ...
```
