# SxspGenerateNdpGACPath(ulong,_ASSEMBLY_IDENTITY const *,_PROBING_ATTRIBUTE_CACHE *,CGenericBaseStringBuffer<CUnicodeCharTraits> &)

- ea: `0x18002f290`
- end: `0x18002fa9c`
- name: `?SxspGenerateNdpGACPath@@YAHKPEBU_ASSEMBLY_IDENTITY@@PEAU_PROBING_ATTRIBUTE_CACHE@@AEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z`
- size: `2060`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180023320`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x180019740`
- `0x180023260`
- `0x18002f290`
- `0x18002faa4`
- `0x18005d2b0`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18002f44d`
- `ntdll!RtlCompareUnicodeString` at `0x18002f44d`
- `ntdll!RtlPopFrame` at `0x18002f63c`
- `ntdll!RtlPopFrame` at `0x18002f63c`
- `ntdll!RtlGetNtSystemRoot` at `0x18002f4d4`
- `ntdll!RtlGetNtSystemRoot` at `0x18002f4d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fa82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fa82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f3d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f4c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f663`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f69a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f6e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f778`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f792`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f7ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f86c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f8d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f942`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f9bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fa08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f3d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f4c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f663`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f69a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f6e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f778`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f792`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f7ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f86c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f8d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f942`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f9bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fa08`

## pseudocode

```c
__int64 __fastcall SxspGenerateNdpGACPath(__int64 a1, const struct _ASSEMBLY_IDENTITY *a2, int *a3, __int64 a4)
{
  const char *v7; // rcx
  int v8; // eax
  unsigned __int64 v9; // r14
  unsigned __int64 v10; // r10
  unsigned __int64 v11; // r8
  WCHAR *v12; // rdi
  unsigned __int64 v13; // rsi
  unsigned int i; // ebx
  unsigned __int64 v15; // r15
  __int16 v16; // r15
  bool v17; // cl
  unsigned int j; // ebx
  unsigned __int64 v19; // rsi
  __int64 v20; // rdi
  __int64 NtSystemRoot; // rax
  unsigned int v22; // ebx
  unsigned __int16 *v24; // rax
  unsigned __int16 *v25; // rax
  unsigned __int16 *v26; // rax
  unsigned __int64 v27; // rax
  __int64 v28; // r13
  DWORD LastError; // eax
  unsigned __int64 v30; // [rsp+C8h] [rbp-80h] BYREF
  unsigned __int64 v31; // [rsp+D0h] [rbp-78h] BYREF
  unsigned __int64 v32; // [rsp+D8h] [rbp-70h] BYREF
  unsigned __int64 v33; // [rsp+E0h] [rbp-68h] BYREF
  unsigned __int16 *v34; // [rsp+E8h] [rbp-60h] BYREF
  unsigned __int16 *v35; // [rsp+F0h] [rbp-58h] BYREF
  unsigned __int16 *v36; // [rsp+F8h] [rbp-50h] BYREF
  unsigned __int64 v37; // [rsp+100h] [rbp-48h] BYREF
  UNICODE_STRING String1; // [rsp+108h] [rbp-40h] BYREF
  UNICODE_STRING String2; // [rsp+118h] [rbp-30h] BYREF
  int v40; // [rsp+128h] [rbp-20h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+130h] [rbp-18h] BYREF
  __int64 v42; // [rsp+148h] [rbp+0h]
  int v43; // [rsp+150h] [rbp+8h]
  int *v44; // [rsp+158h] [rbp+10h]

  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006E1E8;
  v40 = 0;
  Frame.Previous = 0;
  v44 = &v40;
  Frame.Flags = 1;
  v42 = 544438355;
  v43 = 4332;
  CFrame::BaseEnter((CFrame *)&Frame);
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v37 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  *(_QWORD *)&String1.Length = 0;
  *(_QWORD *)&String2.Length = 0;
  if ( !a2 )
  {
    v43 = 4349;
    FusionpTraceParameterCheck(v7);
    SetLastError(0x57u);
    *v44 = 0;
    goto LABEL_32;
  }
  CGenericBaseStringBuffer<CUnicodeCharTraits>::Clear(a4);
  if ( a3 )
  {
    v8 = *a3;
    if ( (*a3 & 1) != 0 )
    {
      v9 = *((_QWORD *)a3 + 2);
      v34 = (unsigned __int16 *)*((_QWORD *)a3 + 1);
      v30 = v9;
    }
    else
    {
      SetLastError(0);
      if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                            1u,
                            a2,
                            (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_name,
                            (const unsigned __int16 **)&v34,
                            &v30) )
      {
        *v44 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180074E10);
        goto LABEL_32;
      }
      v24 = v34;
      *a3 |= 1u;
      v34 = v24;
      *((_QWORD *)a3 + 1) = v24;
      *((_QWORD *)a3 + 2) = v30;
      v8 = *a3;
    }
    if ( (v8 & 0x10) != 0 )
    {
      v10 = *((_QWORD *)a3 + 10);
      v35 = (unsigned __int16 *)*((_QWORD *)a3 + 9);
      v31 = v10;
    }
    else
    {
      SetLastError(0);
      if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                            1u,
                            a2,
                            (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_language,
                            (const unsigned __int16 **)&v35,
                            &v31) )
      {
        *v44 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180074DD0);
        goto LABEL_32;
      }
      v25 = v35;
      *a3 |= 0x10u;
      v35 = v25;
      *((_QWORD *)a3 + 9) = v25;
      *((_QWORD *)a3 + 10) = v31;
      v8 = *a3;
    }
    if ( (v8 & 8) != 0 )
    {
      v11 = *((_QWORD *)a3 + 8);
      v36 = (unsigned __int16 *)*((_QWORD *)a3 + 7);
      v32 = v11;
    }
    else
    {
      SetLastError(0);
      if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                            1u,
                            a2,
                            (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_publicKeyToken,
                            (const unsigned __int16 **)&v36,
                            &v32) )
      {
        *v44 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180074D90);
        goto LABEL_32;
      }
      v26 = v36;
      *a3 |= 8u;
      v36 = v26;
      *((_QWORD *)a3 + 7) = v26;
      *((_QWORD *)a3 + 8) = v32;
      v8 = *a3;
    }
    if ( (v8 & 2) != 0 )
    {
      v33 = *((_QWORD *)a3 + 4);
    }
    else
    {
      SetLastError(0);
      if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                            1u,
                            a2,
                            (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_version,
                            (const unsigned __int16 **)&String1,
                            &v33) )
      {
        *v44 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180074D50);
        goto LABEL_32;
      }
      v27 = v33;
      v28 = *(_QWORD *)&String1.Length;
      *a3 |= 2u;
      v33 = v27;
      *((_QWORD *)a3 + 4) = v27;
      v8 = *a3;
      *((_QWORD *)a3 + 3) = v28;
    }
    if ( (v8 & 4) != 0 )
    {
      v12 = (WCHAR *)*((_QWORD *)a3 + 5);
      v13 = *((_QWORD *)a3 + 6);
    }
    else
    {
      SetLastError(0);
      if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                            1u,
                            a2,
                            (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_processorArchitecture,
                            (const unsigned __int16 **)&String2,
                            &v37) )
      {
        *v44 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180074D10);
        goto LABEL_32;
      }
      v12 = *(WCHAR **)&String2.Length;
      v13 = v37;
      *a3 |= 4u;
      *((_QWORD *)a3 + 5) = v12;
      *((_QWORD *)a3 + 6) = v13;
    }
  }
  else
  {
    SetLastError(0);
    if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                          1u,
                          a2,
                          (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_name,
                          (const unsigned __int16 **)&v34,
                          &v30) )
    {
      *v44 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180074DF0);
      goto LABEL_32;
    }
    SetLastError(0);
    if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                          1u,
                          a2,
                          (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_language,
                          (const unsigned __int16 **)&v35,
                          &v31) )
    {
      *v44 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180074DB0);
      goto LABEL_32;
    }
    SetLastError(0);
    if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                          1u,
                          a2,
                          (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_publicKeyToken,
                          (const unsigned __int16 **)&v36,
                          &v32) )
    {
      *v44 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180074D70);
      goto LABEL_32;
    }
    SetLastError(0);
    if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                          1u,
                          a2,
                          (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_version,
                          (const unsigned __int16 **)&String1,
                          &v33) )
    {
      *v44 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180074D30);
      goto LABEL_32;
    }
    SetLastError(0);
    if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                          1u,
                          a2,
                          (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_processorArchitecture,
                          (const unsigned __int16 **)&String2,
                          &v37) )
    {
      *v44 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180074CF0);
      goto LABEL_32;
    }
    LOWORD(v13) = v37;
    v12 = *(WCHAR **)&String2.Length;
  }
  if ( v12 )
  {
    SetLastError(0);
    for ( i = 0; i < 0xB; ++i )
    {
      *(_QWORD *)&String1.Length = 0;
      v15 = 24LL * i;
      *(_QWORD *)&String2.Length = 0;
      String2.Buffer = v12;
      String1.Buffer = (PWSTR)&asc_180086772[v15];
      String1.Length = 2 * LOWORD(qword_180086780[v15 / 8]);
      String1.MaximumLength = String1.Length;
      *(_QWORD *)&String2.Length = (unsigned __int16)(2 * v13);
      *(_DWORD *)&String2.MaximumLength = (unsigned __int16)(2 * v13);
      if ( !RtlCompareUnicodeString(&String1, &String2, 1u) )
      {
        v16 = *(_WORD *)&byte_180086770[v15];
        v17 = 1;
        goto LABEL_18;
      }
    }
    v17 = i != 11;
    v16 = 0;
    if ( i == 11 )
      goto LABEL_30;
LABEL_18:
    if ( ((v16 - 4) & 0xFFF6) == 0 && v16 != 13 )
      goto LABEL_31;
LABEL_30:
    if ( v17 )
      goto LABEL_23;
  }
  else
  {
    v16 = -1;
LABEL_23:
    for ( j = 0; j < 0xA; ++j )
    {
      v19 = 32LL * j;
      if ( *(_WORD *)&byte_180089C00[v19] == v16 )
      {
        SetLastError(0);
        v20 = qword_180089C18[v19 / 8];
        NtSystemRoot = RtlGetNtSystemRoot();
        if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32AssignW(
                              a4,
                              11,
                              NtSystemRoot,
                              0xFFFFFFFFLL,
                              L"\\assembly\\",
                              -1,
                              &aG[v19],
                              v20,
                              L"\\",
                              1) )
        {
          *v44 = 0;
          FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180074CD0);
          goto LABEL_32;
        }
      }
    }
  }
LABEL_31:
  v40 = 1;
LABEL_32:
  v22 = v40;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v44 )
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
  return v22;
}

```

## disassembly

```asm
0x18002f290  mov     r11, rsp
0x18002f293  push    rbp
0x18002f294  push    rbx
0x18002f295  lea     rbp, [r11-58h]
0x18002f299  sub     rsp, 188h
0x18002f2a0  mov     rax, cs:__security_cookie
0x18002f2a7  xor     rax, rsp
0x18002f2aa  mov     [rbp+50h+var_38], rax
0x18002f2ae  mov     [r11-18h], rdi
0x18002f2b2  lea     rax, qword_18006E1E8
0x18002f2b9  mov     [r11-20h], r12
0x18002f2bd  lea     rcx, [rbp+50h+Frame]; this
0x18002f2c1  mov     [r11-38h], r15
0x18002f2c5  mov     r12, r9
0x18002f2c8  mov     [rbp+50h+Frame.Context], rax
0x18002f2cc  xor     r15d, r15d
0x18002f2cf  lea     rax, [rbp+50h+var_70]
0x18002f2d3  mov     [rbp+50h+var_70], r15d
0x18002f2d7  mov     [rbp+50h+Frame.Previous], r15
0x18002f2db  mov     rbx, r8
0x18002f2de  mov     [rbp+50h+var_40], rax
0x18002f2e2  mov     rdi, rdx
0x18002f2e5  mov     [rbp+50h+Frame.Flags], 1
0x18002f2ec  mov     [rbp+50h+var_50], 20737853h
0x18002f2f4  mov     [rbp+50h+var_48], 10ECh
0x18002f2fb  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18002f300  mov     [rbp+50h+var_D0], r15
0x18002f304  mov     [rbp+50h+var_C8], r15
0x18002f308  mov     [rbp+50h+var_C0], r15
0x18002f30c  mov     [rbp+50h+var_B8], r15
0x18002f310  mov     [rbp+50h+var_98], r15
0x18002f314  mov     [rbp+50h+var_B0], r15
0x18002f318  mov     [rbp+50h+var_A8], r15
0x18002f31c  mov     [rbp+50h+var_A0], r15
0x18002f320  mov     qword ptr [rbp+50h+String1.Length], r15
0x18002f324  mov     qword ptr [rbp+50h+String2.Length], r15
0x18002f328  test    rdi, rdi
0x18002f32b  jz      loc_18002F767
0x18002f331  mov     [rsp+190h+arg_0], rsi
0x18002f339  mov     rcx, r12
0x18002f33c  mov     [rsp+190h+var_20], r13
0x18002f344  mov     [rsp+190h+var_28], r14
0x18002f34c  call    ?Clear@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAX_N@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Clear(bool)
0x18002f351  test    rbx, rbx
0x18002f354  jz      loc_18002F661
0x18002f35a  mov     eax, [rbx]
0x18002f35c  test    al, 1
0x18002f35e  jz      loc_18002F790
0x18002f364  mov     r11, [rbx+8]
0x18002f368  mov     r14, [rbx+10h]
0x18002f36c  mov     [rbp+50h+var_B0], r11
0x18002f370  mov     [rbp+50h+var_D0], r14
0x18002f374  test    al, 10h
0x18002f376  jz      loc_18002F7FD
0x18002f37c  mov     r9, [rbx+48h]
0x18002f380  mov     r10, [rbx+50h]
0x18002f384  mov     [rbp+50h+var_A8], r9
0x18002f388  mov     [rbp+50h+var_C8], r10
0x18002f38c  test    al, 8
0x18002f38e  jz      loc_18002F86A
0x18002f394  mov     rdx, [rbx+38h]
0x18002f398  mov     r8, [rbx+40h]
0x18002f39c  mov     [rbp+50h+var_A0], rdx
0x18002f3a0  mov     [rbp+50h+var_C0], r8
0x18002f3a4  test    al, 2
0x18002f3a6  jz      loc_18002F8D7
0x18002f3ac  mov     rcx, [rbx+20h]
0x18002f3b0  mov     r13, [rbx+18h]
0x18002f3b4  mov     [rbp+50h+var_B8], rcx
0x18002f3b8  test    al, 4
0x18002f3ba  jz      loc_18002F940
0x18002f3c0  mov     rdi, [rbx+28h]
0x18002f3c4  mov     rsi, [rbx+30h]
0x18002f3c8  test    rdi, rdi
0x18002f3cb  jz      loc_18002F491
0x18002f3d1  xor     ecx, ecx; dwErrCode
0x18002f3d3  call    cs:__imp_SetLastError
0x18002f3da  nop     dword ptr [rax+rax+00h]
0x18002f3df  mov     ebx, r15d
0x18002f3e2  lea     r14, __ImageBase
0x18002f3e9  cmp     ebx, 0Bh
0x18002f3ec  jnb     loc_18002F5D8
0x18002f3f2  mov     eax, ebx
0x18002f3f4  lea     rdx, [rbp+50h+String2]; String2
0x18002f3f8  xorps   xmm0, xmm0
0x18002f3fb  xorps   xmm1, xmm1
0x18002f3fe  movups  xmmword ptr [rbp+50h+String1.Length], xmm0
0x18002f402  mov     r8b, 1; CaseInsensitive
0x18002f405  lea     rcx, [rax+rax*2]
0x18002f409  lea     r15, ds:0[rcx*8]
0x18002f411  movups  xmmword ptr [rbp+50h+String2.Length], xmm1
0x18002f415  lea     rax, rva asc_180086772[r14]; "x" ...
0x18002f41c  mov     [rbp+50h+String2.Buffer], rdi
0x18002f420  add     rax, r15
0x18002f423  lea     rcx, [rbp+50h+String1]; String1
0x18002f427  mov     [rbp+50h+String1.Buffer], rax
0x18002f42b  movzx   eax, word ptr [r15+r14+86780h]
0x18002f434  add     ax, ax
0x18002f437  mov     [rbp+50h+String1.Length], ax
0x18002f43b  mov     [rbp+50h+String1.MaximumLength], ax
0x18002f43f  movzx   eax, si
0x18002f442  add     ax, ax
0x18002f445  mov     [rbp+50h+String2.Length], ax
0x18002f449  mov     [rbp+50h+String2.MaximumLength], ax
0x18002f44d  call    cs:__imp_RtlCompareUnicodeString
0x18002f454  nop     dword ptr [rax+rax+00h]
0x18002f459  test    eax, eax
0x18002f45b  jnz     short loc_18002F48A
0x18002f45d  movzx   r15d, word ptr [r15+r14+86770h]
0x18002f466  mov     cl, 1
0x18002f468  lea     eax, [r15-4]
0x18002f46c  mov     edx, 0FFF6h
0x18002f471  test    dx, ax
0x18002f474  jnz     loc_18002F5E9
0x18002f47a  cmp     r15w, 0Dh
0x18002f47f  jz      loc_18002F5E9
0x18002f485  jmp     loc_18002F5F1
0x18002f48a  inc     ebx
0x18002f48c  jmp     loc_18002F3E9
0x18002f491  mov     r15d, 0FFFFh
0x18002f497  lea     r14, __ImageBase
0x18002f49e  xor     ebx, ebx
0x18002f4a0  cmp     ebx, 0Ah
0x18002f4a3  jnb     loc_18002F5F1
0x18002f4a9  mov     esi, ebx
0x18002f4ab  shl     rsi, 5
0x18002f4af  cmp     [rsi+r14+89C00h], r15w
0x18002f4b8  jz      short loc_18002F4BE
0x18002f4ba  inc     ebx
0x18002f4bc  jmp     short loc_18002F4A0
0x18002f4be  xor     ecx, ecx; dwErrCode
0x18002f4c0  call    cs:__imp_SetLastError
0x18002f4c7  nop     dword ptr [rax+rax+00h]
0x18002f4cc  mov     rdi, [rsi+r14+89C18h]
0x18002f4d4  call    cs:__imp_RtlGetNtSystemRoot
0x18002f4db  nop     dword ptr [rax+rax+00h]
0x18002f4e0  mov     rdx, [rbp+50h+var_C0]
0x18002f4e4  lea     r8, asc_18007EDA8; "_"
0x18002f4eb  mov     [rsp+0B8h], edx
0x18002f4f2  lea     rcx, rva aG[r14]; "G" ...
0x18002f4f9  mov     rdx, [rbp+50h+var_A0]
0x18002f4fd  add     rcx, rsi
0x18002f500  mov     qword ptr [rsp+190h+var_E0], rdx
0x18002f508  mov     r9d, 0FFFFFFFFh
0x18002f50e  mov     rdx, [rbp+50h+var_C8]
0x18002f512  mov     dword ptr [rsp+190h+var_E8], 1
0x18002f51d  mov     qword ptr [rsp+190h+var_F0], r8
0x18002f525  mov     dword ptr [rsp+190h+var_F8], edx
0x18002f52c  mov     rdx, [rbp+50h+var_A8]
0x18002f530  mov     qword ptr [rsp+190h+var_100], rdx
0x18002f538  mov     rdx, [rbp+50h+var_B8]
0x18002f53c  mov     dword ptr [rsp+190h+var_108], 1
0x18002f547  mov     qword ptr [rsp+190h+var_110], r8
0x18002f54f  lea     r8, asc_18007ED8C; "\\"
0x18002f556  mov     dword ptr [rsp+190h+var_118], edx
0x18002f55a  mov     rdx, [rbp+50h+var_D0]
0x18002f55e  mov     qword ptr [rsp+190h+var_120], r13
0x18002f563  mov     dword ptr [rsp+190h+var_128], 1
0x18002f56b  mov     qword ptr [rsp+190h+var_130], r8
0x18002f570  mov     dword ptr [rsp+190h+var_138], edx
0x18002f574  mov     rdx, [rbp+50h+var_B0]
0x18002f578  mov     qword ptr [rsp+190h+var_140], rdx
0x18002f57d  mov     edx, 0Bh
0x18002f582  mov     dword ptr [rsp+190h+var_148], 1
0x18002f58a  mov     qword ptr [rsp+190h+var_150], r8
0x18002f58f  mov     r8, rax
0x18002f592  mov     [rsp+190h+var_158], rdi
0x18002f597  mov     [rsp+190h+var_160], rcx
0x18002f59c  lea     rcx, aAssembly_0; "\\assembly\\"
0x18002f5a3  mov     dword ptr [rsp+190h+var_168], 0FFFFFFFFh
0x18002f5ab  mov     [rsp+190h+var_170], rcx
0x18002f5b0  mov     rcx, r12
0x18002f5b3  call    ?Win32AssignW@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHKZZ; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32AssignW(ulong,...)
0x18002f5b8  test    eax, eax
0x18002f5ba  jnz     loc_18002F4BA
0x18002f5c0  mov     rax, [rbp+50h+var_40]
0x18002f5c4  lea     rcx, off_180074CD0; struct _CALL_SITE_INFO *
0x18002f5cb  mov     dword ptr [rax], 0
0x18002f5d1  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18002f5d6  jmp     short loc_18002F5F8
0x18002f5d8  setnz   cl
0x18002f5db  xor     r15d, r15d
0x18002f5de  cmp     ebx, 0Bh
0x18002f5e1  jnz     loc_18002F468
0x18002f5e7  xor     eax, eax
0x18002f5e9  test    cl, cl
0x18002f5eb  jnz     loc_18002F49E
0x18002f5f1  mov     [rbp+50h+var_70], 1
0x18002f5f8  mov     r13, [rsp+190h+var_20]
0x18002f600  mov     rsi, [rsp+190h+arg_0]
0x18002f608  mov     r14, [rsp+190h+var_28]
0x18002f610  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18002f617  mov     ebx, [rbp+50h+var_70]
0x18002f61a  mov     r15, [rsp+190h+var_30]
0x18002f622  mov     r12, [rsp+190h+var_18]
0x18002f62a  mov     rdi, [rsp+180h]
0x18002f632  jnz     loc_18002FA6D
0x18002f638  lea     rcx, [rbp+50h+Frame]; Frame
0x18002f63c  call    cs:__imp_RtlPopFrame
0x18002f643  nop     dword ptr [rax+rax+00h]
0x18002f648  mov     eax, ebx
0x18002f64a  mov     rcx, [rbp+50h+var_38]
0x18002f64e  xor     rcx, rsp; StackCookie
0x18002f651  call    __security_check_cookie
0x18002f656  add     rsp, 188h
0x18002f65d  pop     rbx
0x18002f65e  pop     rbp
0x18002f65f  retn
0x18002f661  xor     ecx, ecx; dwErrCode
0x18002f663  call    cs:__imp_SetLastError
0x18002f66a  nop     dword ptr [rax+rax+00h]
0x18002f66f  lea     rax, [rbp+50h+var_D0]
0x18002f673  mov     rdx, rdi; struct _ASSEMBLY_IDENTITY *
0x18002f676  lea     r9, [rbp+50h+var_B0]; unsigned __int16 **
0x18002f67a  mov     [rsp+190h+var_170], rax; unsigned __int64 *
0x18002f67f  lea     r8, s_IdentityAttribute_name; struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *
0x18002f686  mov     ecx, 1; unsigned int
0x18002f68b  call    ?SxspGetAssemblyIdentityAttributeValue@@YAHKPEBU_ASSEMBLY_IDENTITY@@PEBU_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE@@PEAPEBGPEA_K@Z; SxspGetAssemblyIdentityAttributeValue(ulong,_ASSEMBLY_IDENTITY const *,_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE const *,ushort const * *,unsigned __int64 *)
0x18002f690  test    eax, eax
0x18002f692  jz      loc_18002F9A3
0x18002f698  xor     ecx, ecx; dwErrCode
0x18002f69a  call    cs:__imp_SetLastError
0x18002f6a1  nop     dword ptr [rax+rax+00h]
0x18002f6a6  lea     rax, [rbp+50h+var_C8]
0x18002f6aa  mov     rdx, rdi; struct _ASSEMBLY_IDENTITY *
0x18002f6ad  lea     r9, [rbp+50h+var_A8]; unsigned __int16 **
0x18002f6b1  mov     [rsp+190h+var_170], rax; unsigned __int64 *
0x18002f6b6  lea     r8, s_IdentityAttribute_language; struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *
0x18002f6bd  mov     ecx, 1; unsigned int
0x18002f6c2  call    ?SxspGetAssemblyIdentityAttributeValue@@YAHKPEBU_ASSEMBLY_IDENTITY@@PEBU_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE@@PEAPEBGPEA_K@Z; SxspGetAssemblyIdentityAttributeValue(ulong,_ASSEMBLY_IDENTITY const *,_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE const *,ushort const * *,unsigned __int64 *)
0x18002f6c7  test    eax, eax
0x18002f6c9  jnz     loc_18002F9BB
0x18002f6cf  mov     rax, [rbp+50h+var_40]
0x18002f6d3  lea     rcx, off_180074DB0; struct _CALL_SITE_INFO *
0x18002f6da  mov     [rax], r15d
0x18002f6dd  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18002f6e2  jmp     loc_18002F5F8
0x18002f6e7  xor     ecx, ecx; dwErrCode
0x18002f6e9  call    cs:__imp_SetLastError
0x18002f6f0  nop     dword ptr [rax+rax+00h]
0x18002f6f5  lea     rax, [rbp+50h+var_98]
0x18002f6f9  mov     rdx, rdi; struct _ASSEMBLY_IDENTITY *
0x18002f6fc  lea     r9, [rbp+50h+String2]; unsigned __int16 **
0x18002f700  mov     [rsp+190h+var_170], rax; unsigned __int64 *
0x18002f705  lea     r8, s_IdentityAttribute_processorArchitecture; struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *
0x18002f70c  mov     ecx, 1; unsigned int
0x18002f711  call    ?SxspGetAssemblyIdentityAttributeValue@@YAHKPEBU_ASSEMBLY_IDENTITY@@PEBU_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE@@PEAPEBGPEA_K@Z; SxspGetAssemblyIdentityAttributeValue(ulong,_ASSEMBLY_IDENTITY const *,_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE const *,ushort const * *,unsigned __int64 *)
0x18002f716  test    eax, eax
0x18002f718  jz      loc_18002FA55
0x18002f71e  mov     r14, [rbp+50h+var_D0]
0x18002f722  mov     r10, [rbp+50h+var_C8]
0x18002f726  mov     r8, [rbp+50h+var_C0]
0x18002f72a  mov     rcx, [rbp+50h+var_B8]
0x18002f72e  mov     r11, [rbp+50h+var_B0]
0x18002f732  mov     r9, [rbp+50h+var_A8]
0x18002f736  mov     rdx, [rbp+50h+var_A0]
0x18002f73a  mov     rsi, [rbp+50h+var_98]
0x18002f73e  mov     r13, qword ptr [rbp+50h+String1.Length]
0x18002f742  mov     rdi, qword ptr [rbp+50h+String2.Length]
0x18002f746  mov     [rbp+50h+var_D0], r14
0x18002f74a  mov     [rbp+50h+var_C8], r10
0x18002f74e  mov     [rbp+50h+var_C0], r8
0x18002f752  mov     [rbp+50h+var_B8], rcx
0x18002f756  mov     [rbp+50h+var_B0], r11
0x18002f75a  mov     [rbp+50h+var_A8], r9
0x18002f75e  mov     [rbp+50h+var_A0], rdx
0x18002f762  jmp     loc_18002F3C8
0x18002f767  mov     [rbp+50h+var_48], 10FDh
0x18002f76e  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18002f773  mov     ecx, 57h ; 'W'; dwErrCode
0x18002f778  call    cs:__imp_SetLastError
0x18002f77f  nop     dword ptr [rax+rax+00h]
0x18002f784  mov     rax, [rbp+50h+var_40]
0x18002f788  mov     [rax], r15d
0x18002f78b  jmp     loc_18002F610
0x18002f790  xor     ecx, ecx; dwErrCode
0x18002f792  call    cs:__imp_SetLastError
0x18002f799  nop     dword ptr [rax+rax+00h]
0x18002f79e  lea     rax, [rbp+50h+var_D0]
0x18002f7a2  mov     rdx, rdi; struct _ASSEMBLY_IDENTITY *
0x18002f7a5  lea     r9, [rbp+50h+var_B0]; unsigned __int16 **
0x18002f7a9  mov     [rsp+190h+var_170], rax; unsigned __int64 *
0x18002f7ae  lea     r8, s_IdentityAttribute_name; struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *
0x18002f7b5  mov     ecx, 1; unsigned int
0x18002f7ba  call    ?SxspGetAssemblyIdentityAttributeValue@@YAHKPEBU_ASSEMBLY_IDENTITY@@PEBU_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE@@PEAPEBGPEA_K@Z; SxspGetAssemblyIdentityAttributeValue(ulong,_ASSEMBLY_IDENTITY const *,_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE const *,ushort const * *,unsigned __int64 *)
0x18002f7bf  test    eax, eax
0x18002f7c1  jnz     short loc_18002F7DB
0x18002f7c3  mov     rax, [rbp+50h+var_40]
0x18002f7c7  lea     rcx, off_180074E10; struct _CALL_SITE_INFO *
0x18002f7ce  mov     [rax], r15d
0x18002f7d1  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18002f7d6  jmp     loc_18002F5F8
0x18002f7db  mov     rax, [rbp+50h+var_B0]
0x18002f7df  or      dword ptr [rbx], 1
0x18002f7e2  mov     [rbp+50h+var_B0], rax
0x18002f7e6  mov     [rbx+8], rax
0x18002f7ea  mov     rax, [rbp+50h+var_D0]
0x18002f7ee  mov     [rbp+50h+var_D0], rax
0x18002f7f2  mov     [rbx+10h], rax
0x18002f7f6  mov     eax, [rbx]
  ... truncated ...
```
