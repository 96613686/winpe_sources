# VerifySettingElement(ushort const *,ushort const *,ushort const *,_ACTCTXCTB_CALLBACK_DATA *)

- ea: `0x18002bdb4`
- end: `0x18002c537`
- name: `?VerifySettingElement@@YAHPEBG00PEAT_ACTCTXCTB_CALLBACK_DATA@@@Z`
- size: `1923`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, union _ACTCTXCTB_CALLBACK_DATA *)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001f2c0`

## callees

- `0x1800075a0`
- `0x18000a804`
- `0x18000df40`
- `0x18000dffc`
- `0x180013150`
- `0x180013af0`
- `0x180017bc0`
- `0x18001c270`
- `0x18001d988`
- `0x180020820`
- `0x180022d40`
- `0x180022f60`
- `0x180022f90`
- `0x1800265b0`
- `0x180029380`
- `0x18002bcb4`
- `0x18002bdb4`
- `0x18002c540`
- `0x18002c5b0`
- `0x18002c760`
- `0x18002cc78`
- `0x18002d248`
- `0x18002d6ec`
- `0x18003eb88`
- `0x180058904`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c38b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c38b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bea5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bf1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bf48`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bf8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bfb9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c050`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c085`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c0af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c0f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c137`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c16b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c1cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c219`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c255`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c2cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c313`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c369`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c412`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bea5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bf1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bf48`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bf8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bfb9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c050`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c085`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c0af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c0f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c137`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c16b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c1cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c219`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c255`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c2cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c313`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c369`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c412`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c01e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c01e`

## pseudocode

```c
__int64 __fastcall VerifySettingElement(
        const unsigned __int16 *a1,
        WCHAR *a2,
        const unsigned __int16 *a3,
        union _ACTCTXCTB_CALLBACK_DATA *a4)
{
  DWORD v5; // esi
  __int64 v9; // rax
  int v10; // edi
  int v11; // eax
  struct _ASSEMBLY_IDENTITY *v12; // r14
  char **v13; // rcx
  DWORD v14; // ecx
  LSTATUS v15; // eax
  unsigned int i; // edx
  unsigned int v17; // r9d
  int v18; // edi
  unsigned __int64 v19; // rbx
  unsigned int v20; // r9d
  __int64 v21; // r9
  unsigned int v22; // r9d
  DWORD LastError; // ebx
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  WCHAR *v27; // rax
  const unsigned __int16 *v28; // r9
  unsigned int v29; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *phkResultc; // [rsp+20h] [rbp-E0h]
  const struct _UNICODE_STRING *v35; // [rsp+28h] [rbp-D8h]
  bool v36; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v37; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v39; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v41; // [rsp+68h] [rbp-98h] BYREF
  __int64 v42; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING lpMem; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v44[8]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v45; // [rsp+90h] [rbp-70h]
  unsigned __int64 v46; // [rsp+98h] [rbp-68h]
  __int64 v47; // [rsp+A0h] [rbp-60h]
  _QWORD v48[2]; // [rsp+A8h] [rbp-58h] BYREF
  char *v49; // [rsp+B8h] [rbp-48h]
  int v50; // [rsp+C0h] [rbp-40h] BYREF
  HKEY v51; // [rsp+C8h] [rbp-38h] BYREF
  int v52; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v53; // [rsp+D8h] [rbp-28h]
  __int64 *v54; // [rsp+E0h] [rbp-20h]
  __int64 v55; // [rsp+E8h] [rbp-18h]
  int v56; // [rsp+F0h] [rbp-10h]
  int *v57; // [rsp+F8h] [rbp-8h]
  _QWORD v58[2]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 *v59; // [rsp+110h] [rbp+10h]
  __int64 v60; // [rsp+118h] [rbp+18h]
  unsigned __int64 v61; // [rsp+120h] [rbp+20h]
  char v62; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v63[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 *v64; // [rsp+1C0h] [rbp+C0h]
  __int64 v65; // [rsp+1C8h] [rbp+C8h]
  char *v66; // [rsp+1D0h] [rbp+D0h]
  char v67; // [rsp+1D8h] [rbp+D8h] BYREF
  _QWORD v68[2]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 *v69; // [rsp+270h] [rbp+170h]
  __int64 v70; // [rsp+278h] [rbp+178h]
  char v71; // [rsp+288h] [rbp+188h] BYREF
  char v72; // [rsp+490h] [rbp+390h] BYREF

  v52 = 1;
  v54 = &qword_18006DFC8;
  v55 = 544438355;
  v5 = 0;
  v57 = &v50;
  v50 = 0;
  v53 = 0;
  v56 = 81;
  CFrame::BaseEnter((CFrame *)&v52);
  v51 = 0;
  v49 = &v72;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  *(_QWORD *)&lpMem.Length = 0;
  v48[0] = 0;
  v48[1] = 280;
  CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(v68);
  v39 = 0;
  v37 = 0;
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(v58);
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(v63);
  v9 = *((_QWORD *)a4 + 9);
  v38 = 0;
  v36 = 0;
  v10 = *(unsigned __int16 *)(v9 + 12);
  SetLastError(0);
  v11 = SxspCreateAssemblyIdentityFromTextualString(a1, &lpMem);
  v12 = *(struct _ASSEMBLY_IDENTITY **)&lpMem.Length;
  if ( !v11 )
  {
    v13 = off_1800703D0;
LABEL_3:
    *v57 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v13);
    goto LABEL_70;
  }
  if ( !v10 || v10 == 5 || v10 == 6 || v10 == 9 )
    goto LABEL_15;
  if ( v10 == 10 )
    goto LABEL_14;
  if ( v10 != 12 )
  {
    if ( v10 != 13 )
    {
      if ( v10 != 14 )
      {
        v14 = 87;
        goto LABEL_69;
      }
LABEL_14:
      LOWORD(v10) = 0;
      goto LABEL_15;
    }
    LOWORD(v10) = 5;
  }
LABEL_15:
  SetLastError(0);
  if ( !(unsigned int)FusionpFormatProcessorArchitecture((unsigned __int16)v10, v63) )
  {
    v13 = off_18007C240;
    goto LABEL_3;
  }
  SetLastError(0);
  if ( !(unsigned int)SxspSetAssemblyIdentityAttributeValue(
                        0,
                        v12,
                        (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_processorArchitecture,
                        v64,
                        v66) )
  {
    v13 = off_18007C220;
    goto LABEL_3;
  }
  SetLastError(0);
  if ( !(unsigned int)SxspGenerateKeyform(1, v12, (struct _LUNICODE_STRING *)v48) )
  {
    v13 = off_18007C200;
    goto LABEL_3;
  }
  SetLastError(0);
  if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(v68, v49, v48[0] >> 1) )
  {
    v13 = off_18007C1E0;
    goto LABEL_3;
  }
  if ( v51 )
    goto LABEL_66;
  *(_QWORD *)&lpMem.Length = 0x300000002LL;
  v15 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\SMI\\WinSxs Settings",
          0,
          0x20119u,
          &v51);
  if ( v15 )
  {
    for ( i = 0; i < 2; ++i )
    {
      if ( *((_DWORD *)&lpMem.Length + i) == v15 )
      {
        HIDWORD(v38) = v15;
        goto LABEL_30;
      }
    }
    if ( i == 2 )
    {
      SetLastError(v15);
      FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_18007C1C0);
      goto LABEL_70;
    }
  }
LABEL_30:
  if ( v51 )
  {
LABEL_66:
    SetLastError(0);
    if ( !CRegKey::OpenSubKey((CRegKey *)&v51, (struct CRegKey *)&v40, v69, v17, phkResult) )
    {
      v13 = off_18007C1A0;
      goto LABEL_3;
    }
    if ( v40 )
    {
      SetLastError(0);
      if ( !(unsigned int)CRegKey::EnumKey((CRegKey *)&v40, 0, (__int64)&v38) )
      {
        v13 = off_18007C180;
        goto LABEL_3;
      }
      v18 = v38;
      if ( !(_DWORD)v38 )
      {
        SetLastError(0);
        if ( !(unsigned int)CFusionParser::ParseVersion((union _ASSEMBLY_VERSION *)&v37, v59, v61, &v36) )
        {
          v13 = off_18007C160;
          goto LABEL_3;
        }
        v19 = v37;
        while ( !v18 )
        {
          ++v5;
          SetLastError(0);
          if ( !(unsigned int)CRegKey::EnumKey((CRegKey *)&v40, v5, (__int64)&v38) )
          {
            v13 = off_18007C140;
            goto LABEL_3;
          }
          v18 = v38;
          if ( !(_DWORD)v38 )
          {
            SetLastError(0);
            if ( !(unsigned int)CFusionParser::ParseVersion((union _ASSEMBLY_VERSION *)&v39, v59, v61, &v36) )
            {
              v13 = off_18007C120;
              goto LABEL_3;
            }
            if ( v39 > v19 && v36 != (_BYTE)v18 )
            {
              v19 = v39;
              v37 = v39;
            }
          }
        }
        SetLastError(0);
        LODWORD(v35) = (unsigned __int16)v37;
        phkResulta = WORD1(v37);
        if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Format(
                              v58,
                              L"%u.%u.%u.%u",
                              HIWORD(v37),
                              WORD2(v37)) )
        {
          v13 = off_18007C100;
          goto LABEL_3;
        }
        SetLastError(0);
        if ( !CRegKey::OpenSubKey((CRegKey *)&v40, (struct CRegKey *)&v41, v59, v20, phkResulta) )
        {
          v13 = off_18007C0E0;
          goto LABEL_3;
        }
        if ( v41 )
        {
          SetLastError(0);
          if ( !(unsigned int)CRegKey::GetValue(&v41, 1, L"targetNamespace", v44, (char *)&v38 + 4, 0) )
          {
            v13 = off_18007C0C0;
            goto LABEL_3;
          }
          v21 = -1;
          do
            ++v21;
          while ( a2[v21] );
          if ( !FusionpCompareStrings(v45, v46 >> 1, a2, v21 + 1, 0) )
          {
            SetLastError(0);
            if ( !CRegKey::OpenSubKey((CRegKey *)&v41, (struct CRegKey *)&v42, L"Settings", v22, phkResultb) )
            {
              v13 = off_18007C0A0;
              goto LABEL_3;
            }
            if ( v42 )
            {
              CFusionArray<unsigned char,unsigned char,0,32>::Win32Reset(v44);
              SetLastError(0);
              if ( !(unsigned int)CRegKey::GetValue(&v42, 1, a3, v44, (char *)&v38 + 4, 1) )
              {
                v13 = off_18007C080;
                goto LABEL_3;
              }
              if ( v46 )
              {
                v50 = 1;
                goto LABEL_70;
              }
            }
          }
        }
      }
    }
  }
  v14 = 14106;
LABEL_69:
  SetLastError(v14);
LABEL_70:
  if ( v12 )
    SxsDestroyAssemblyIdentity(v12);
  if ( !v50 )
  {
    LastError = GetLastError();
    if ( LastError == 14106 )
    {
      v24 = *((_QWORD *)a4 + 11);
      v25 = *((_QWORD *)a4 + 9);
      v26 = *(_QWORD *)(v24 + 24);
      v27 = *(WCHAR **)(v24 + 16);
      lpMem.Length = 2 * v26;
      lpMem.MaximumLength = 2 * v26;
      lpMem.Buffer = v27;
      FusionpLogActCtxGenError(
        0xC101004F,
        *(const unsigned __int16 **)(v25 + 1312),
        &lpMem,
        &g_strEmptyUnicodeString,
        &g_strEmptyUnicodeString,
        v35);
      TraceActCtxGenEvents(
        *(_DWORD *)(*((_QWORD *)a4 + 9) + 1304LL),
        *(const unsigned __int16 **)(*((_QWORD *)a4 + 11) + 16LL),
        0,
        v28,
        phkResultc,
        0x119u,
        4,
        0x68u);
    }
    SetLastError(LastError);
  }
  v29 = v50;
  v63[0] = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  if ( v64 != (unsigned __int16 *)&v67 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(v63);
  v64 = 0;
  v65 = 0;
  v63[0] = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  v58[0] = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  if ( v59 != (unsigned __int16 *)&v62 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(v58);
  v68[0] = &CGenericStringBuffer<260,CUnicodeCharTraits>::`vftable';
  v59 = 0;
  v60 = 0;
  v58[0] = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  if ( v69 != (unsigned __int16 *)&v71 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(v68);
  v69 = 0;
  v70 = 0;
  v68[0] = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  if ( v46 )
    operator delete(v45);
  CHandleTemplate<&void * hNull,COperatorFRegCloseKey>::~CHandleTemplate<&void * hNull,COperatorFRegCloseKey>(&v42);
  CHandleTemplate<&void * hNull,COperatorFRegCloseKey>::~CHandleTemplate<&void * hNull,COperatorFRegCloseKey>(&v41);
  CHandleTemplate<&void * hNull,COperatorFRegCloseKey>::~CHandleTemplate<&void * hNull,COperatorFRegCloseKey>(&v40);
  CHandleTemplate<&void * hNull,COperatorFRegCloseKey>::~CHandleTemplate<&void * hNull,COperatorFRegCloseKey>(&v51);
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v52);
  return v29;
}

```

## disassembly

```asm
0x18002bdb4  push    rbp
0x18002bdb6  push    rbx
0x18002bdb7  push    rsi
0x18002bdb8  push    rdi
0x18002bdb9  push    r12
0x18002bdbb  push    r13
0x18002bdbd  push    r14
0x18002bdbf  push    r15
0x18002bdc1  lea     rbp, [rsp-4C8h]
0x18002bdc9  sub     rsp, 5C8h
0x18002bdd0  mov     rax, cs:__security_cookie
0x18002bdd7  xor     rax, rsp
0x18002bdda  mov     [rbp+500h+var_50], rax
0x18002bde1  lea     rax, qword_18006DFC8
0x18002bde8  mov     [rbp+500h+var_530], 1
0x18002bdef  mov     [rbp+500h+var_520], rax
0x18002bdf3  mov     rbx, rcx
0x18002bdf6  lea     rax, [rbp+500h+var_540]
0x18002bdfa  mov     [rbp+500h+var_518], 20737853h
0x18002be02  xor     esi, esi
0x18002be04  mov     [rbp+500h+var_508], rax
0x18002be08  lea     rcx, [rbp+500h+var_530]; this
0x18002be0c  mov     [rbp+500h+var_540], esi
0x18002be0f  mov     r13, r9
0x18002be12  mov     [rbp+500h+var_528], rsi
0x18002be16  mov     r12, r8
0x18002be19  mov     [rbp+500h+var_510], 51h ; 'Q'
0x18002be20  mov     r15, rdx
0x18002be23  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18002be28  lea     rax, [rbp+500h+var_170]
0x18002be2f  mov     [rbp+500h+var_538], rsi
0x18002be33  lea     rcx, [rbp+500h+var_3A0]; void *
0x18002be3a  mov     [rbp+500h+var_548], rax
0x18002be3e  mov     [rsp+600h+var_5A0], rsi
0x18002be43  mov     [rsp+600h+var_598], rsi
0x18002be48  mov     [rsp+600h+var_590], rsi
0x18002be4d  mov     [rbp+500h+var_570], rsi
0x18002be51  mov     [rbp+500h+var_568], rsi
0x18002be55  mov     [rbp+500h+var_560], rsi
0x18002be59  mov     dword ptr [rsp+600h+var_5B0+4], esi
0x18002be5d  mov     [rsp+600h+lpMem], rsi
0x18002be62  mov     [rbp+500h+var_558], rsi
0x18002be66  mov     [rbp+500h+var_550], 118h
0x18002be6e  call    ??0?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x18002be73  lea     rcx, [rbp+500h+var_500]
0x18002be77  mov     [rsp+600h+var_5A8], rsi
0x18002be7c  mov     [rsp+600h+var_5B8], rsi
0x18002be81  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x18002be86  lea     rcx, [rbp+500h+var_450]
0x18002be8d  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x18002be92  mov     rax, [r13+48h]
0x18002be96  xor     ecx, ecx; dwErrCode
0x18002be98  mov     dword ptr [rsp+600h+var_5B0], esi
0x18002be9c  mov     [rsp+600h+var_5C0], sil
0x18002bea1  movzx   edi, word ptr [rax+0Ch]
0x18002bea5  call    cs:__imp_SetLastError
0x18002beac  nop     dword ptr [rax+rax+00h]
0x18002beb1  lea     rdx, [rsp+600h+lpMem]
0x18002beb6  mov     rcx, rbx
0x18002beb9  call    SxspCreateAssemblyIdentityFromTextualString
0x18002bebe  mov     r14, [rsp+600h+lpMem]
0x18002bec3  test    eax, eax
0x18002bec5  jnz     short loc_18002BEDE
0x18002bec7  lea     rcx, off_1800703D0; struct _CALL_SITE_INFO *
0x18002bece  mov     rax, [rbp+500h+var_508]
0x18002bed2  mov     [rax], esi
0x18002bed4  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18002bed9  jmp     loc_18002C375
0x18002bede  mov     ecx, edi
0x18002bee0  mov     ebx, 2
0x18002bee5  test    edi, edi
0x18002bee7  jz      short loc_18002BF1C
0x18002bee9  sub     ecx, 5
0x18002beec  jz      short loc_18002BF1C
0x18002beee  sub     ecx, 1
0x18002bef1  jz      short loc_18002BF1C
0x18002bef3  sub     ecx, 3
0x18002bef6  jz      short loc_18002BF1C
0x18002bef8  sub     ecx, 1
0x18002befb  jz      short loc_18002BF1A
0x18002befd  sub     ecx, ebx
0x18002beff  jz      short loc_18002BF1C
0x18002bf01  sub     ecx, 1
0x18002bf04  jz      short loc_18002BF13
0x18002bf06  cmp     ecx, 1
0x18002bf09  jz      short loc_18002BF1A
0x18002bf0b  lea     ecx, [rbx+55h]
0x18002bf0e  jmp     loc_18002C369
0x18002bf13  mov     edi, 5
0x18002bf18  jmp     short loc_18002BF1C
0x18002bf1a  mov     edi, esi
0x18002bf1c  xor     ecx, ecx; dwErrCode
0x18002bf1e  call    cs:__imp_SetLastError
0x18002bf25  nop     dword ptr [rax+rax+00h]
0x18002bf2a  lea     rdx, [rbp+500h+var_450]
0x18002bf31  movzx   ecx, di
0x18002bf34  call    ?FusionpFormatProcessorArchitecture@@YAHGAEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; FusionpFormatProcessorArchitecture(ushort,CGenericBaseStringBuffer<CUnicodeCharTraits> &)
0x18002bf39  test    eax, eax
0x18002bf3b  jnz     short loc_18002BF46
0x18002bf3d  lea     rcx, off_18007C240; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18002bf44  jmp     short loc_18002BECE
0x18002bf46  xor     ecx, ecx; dwErrCode
0x18002bf48  call    cs:__imp_SetLastError
0x18002bf4f  nop     dword ptr [rax+rax+00h]
0x18002bf54  mov     rax, [rbp+500h+var_430]
0x18002bf5b  lea     r8, s_IdentityAttribute_processorArchitecture; struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *
0x18002bf62  mov     r9, [rbp+500h+var_440]; unsigned __int16 *
0x18002bf69  mov     rdx, r14; struct _ASSEMBLY_IDENTITY *
0x18002bf6c  xor     ecx, ecx; unsigned int
0x18002bf6e  mov     [rsp+600h+phkResult], rax; char *
0x18002bf73  call    ?SxspSetAssemblyIdentityAttributeValue@@YAHKPEAU_ASSEMBLY_IDENTITY@@PEBU_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE@@PEBG_K@Z; SxspSetAssemblyIdentityAttributeValue(ulong,_ASSEMBLY_IDENTITY *,_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE const *,ushort const *,unsigned __int64)
0x18002bf78  test    eax, eax
0x18002bf7a  jnz     short loc_18002BF88
0x18002bf7c  lea     rcx, off_18007C220; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18002bf83  jmp     loc_18002BECE
0x18002bf88  xor     ecx, ecx; dwErrCode
0x18002bf8a  call    cs:__imp_SetLastError
0x18002bf91  nop     dword ptr [rax+rax+00h]
0x18002bf96  lea     r8, [rbp+500h+var_558]; struct _LUNICODE_STRING *
0x18002bf9a  mov     rdx, r14; struct _ASSEMBLY_IDENTITY *
0x18002bf9d  mov     ecx, 1; unsigned int
0x18002bfa2  call    ?SxspGenerateKeyform@@YAHKPEBU_ASSEMBLY_IDENTITY@@PEAU_LUNICODE_STRING@@@Z; SxspGenerateKeyform(ulong,_ASSEMBLY_IDENTITY const *,_LUNICODE_STRING *)
0x18002bfa7  test    eax, eax
0x18002bfa9  jnz     short loc_18002BFB7
0x18002bfab  lea     rcx, off_18007C200; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18002bfb2  jmp     loc_18002BECE
0x18002bfb7  xor     ecx, ecx; dwErrCode
0x18002bfb9  call    cs:__imp_SetLastError
0x18002bfc0  nop     dword ptr [rax+rax+00h]
0x18002bfc5  mov     r8, [rbp+500h+var_558]
0x18002bfc9  lea     rcx, [rbp+500h+var_3A0]
0x18002bfd0  mov     rdx, [rbp+500h+var_548]
0x18002bfd4  shr     r8, 1
0x18002bfd7  call    ?Win32Assign@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(ushort const *,unsigned __int64)
0x18002bfdc  test    eax, eax
0x18002bfde  jnz     short loc_18002BFEC
0x18002bfe0  lea     rcx, off_18007C1E0; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18002bfe7  jmp     loc_18002BECE
0x18002bfec  cmp     [rbp+500h+var_538], rsi
0x18002bff0  jnz     short loc_18002C04E
0x18002bff2  lea     rax, [rbp+500h+var_538]
0x18002bff6  mov     dword ptr [rsp+600h+lpMem], ebx
0x18002bffa  mov     r9d, 20119h; samDesired
0x18002c000  mov     [rsp+600h+phkResult], rax; unsigned int
0x18002c005  xor     r8d, r8d; ulOptions
0x18002c008  mov     dword ptr [rsp+600h+lpMem+4], 3
0x18002c010  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002c017  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c01e  call    cs:__imp_RegOpenKeyExW
0x18002c025  nop     dword ptr [rax+rax+00h]
0x18002c02a  test    eax, eax
0x18002c02c  jz      short loc_18002C044
0x18002c02e  mov     edx, esi
0x18002c030  cmp     edx, ebx
0x18002c032  jnb     short loc_18002C081
0x18002c034  mov     ecx, edx
0x18002c036  cmp     dword ptr [rsp+rcx*4+600h+lpMem], eax
0x18002c03a  jz      short loc_18002C040
0x18002c03c  inc     edx
0x18002c03e  jmp     short loc_18002C030
0x18002c040  mov     dword ptr [rsp+600h+var_5B0+4], eax
0x18002c044  cmp     [rbp+500h+var_538], rsi
0x18002c048  jz      loc_18002C364
0x18002c04e  xor     ecx, ecx; dwErrCode
0x18002c050  call    cs:__imp_SetLastError
0x18002c057  nop     dword ptr [rax+rax+00h]
0x18002c05c  mov     r8, [rbp+500h+var_390]; unsigned __int16 *
0x18002c063  lea     rdx, [rsp+600h+var_5A0]; struct CRegKey *
0x18002c068  lea     rcx, [rbp+500h+var_538]; this
0x18002c06c  call    ?OpenSubKey@CRegKey@@QEBAHAEAV1@PEBGKK@Z; CRegKey::OpenSubKey(CRegKey &,ushort const *,ulong,ulong)
0x18002c071  test    eax, eax
0x18002c073  jnz     short loc_18002C0A2
0x18002c075  lea     rcx, off_18007C1A0; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18002c07c  jmp     loc_18002BECE
0x18002c081  jnz     short loc_18002C044
0x18002c083  mov     ecx, eax; dwErrCode
0x18002c085  call    cs:__imp_SetLastError
0x18002c08c  nop     dword ptr [rax+rax+00h]
0x18002c091  lea     rcx, off_18007C1C0; struct _CALL_SITE_INFO *
0x18002c098  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x18002c09d  jmp     loc_18002C375
0x18002c0a2  cmp     [rsp+600h+var_5A0], rsi
0x18002c0a7  jz      loc_18002C364
0x18002c0ad  xor     ecx, ecx; dwErrCode
0x18002c0af  call    cs:__imp_SetLastError
0x18002c0b6  nop     dword ptr [rax+rax+00h]
0x18002c0bb  lea     rax, [rsp+600h+var_5B0]
0x18002c0c0  xor     edx, edx; dwIndex
0x18002c0c2  lea     r8, [rbp+500h+var_500]
0x18002c0c6  mov     [rsp+600h+phkResult], rax; __int64
0x18002c0cb  lea     rcx, [rsp+600h+var_5A0]; this
0x18002c0d0  call    ?EnumKey@CRegKey@@QEBAHKAEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@PEAU_FILETIME@@PEAH@Z; CRegKey::EnumKey(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> &,_FILETIME *,int *)
0x18002c0d5  test    eax, eax
0x18002c0d7  jnz     short loc_18002C0E5
0x18002c0d9  lea     rcx, off_18007C180; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18002c0e0  jmp     loc_18002BECE
0x18002c0e5  mov     edi, dword ptr [rsp+600h+var_5B0]
0x18002c0e9  test    edi, edi
0x18002c0eb  jnz     loc_18002C364
0x18002c0f1  xor     ecx, ecx; dwErrCode
0x18002c0f3  call    cs:__imp_SetLastError
0x18002c0fa  nop     dword ptr [rax+rax+00h]
0x18002c0ff  mov     r8, [rbp+500h+var_4E0]; unsigned __int64
0x18002c103  lea     r9, [rsp+600h+var_5C0]; bool *
0x18002c108  mov     rdx, [rbp+500h+var_4F0]; unsigned __int16 *
0x18002c10c  lea     rcx, [rsp+600h+var_5B8]; union _ASSEMBLY_VERSION *
0x18002c111  call    ?ParseVersion@CFusionParser@@SAHAEAT_ASSEMBLY_VERSION@@PEBG_KAEA_N@Z; CFusionParser::ParseVersion(_ASSEMBLY_VERSION &,ushort const *,unsigned __int64,bool &)
0x18002c116  test    eax, eax
0x18002c118  jnz     short loc_18002C126
0x18002c11a  lea     rcx, off_18007C160; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18002c121  jmp     loc_18002BECE
0x18002c126  mov     rbx, [rsp+600h+var_5B8]
0x18002c12b  xor     ecx, ecx; dwErrCode
0x18002c12d  test    edi, edi
0x18002c12f  jnz     loc_18002C1CB
0x18002c135  inc     esi
0x18002c137  call    cs:__imp_SetLastError
0x18002c13e  nop     dword ptr [rax+rax+00h]
0x18002c143  lea     rax, [rsp+600h+var_5B0]
0x18002c148  mov     edx, esi; dwIndex
0x18002c14a  lea     r8, [rbp+500h+var_500]
0x18002c14e  mov     [rsp+600h+phkResult], rax; __int64
0x18002c153  lea     rcx, [rsp+600h+var_5A0]; this
0x18002c158  call    ?EnumKey@CRegKey@@QEBAHKAEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@PEAU_FILETIME@@PEAH@Z; CRegKey::EnumKey(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> &,_FILETIME *,int *)
0x18002c15d  test    eax, eax
0x18002c15f  jz      short loc_18002C1BD
0x18002c161  mov     edi, dword ptr [rsp+600h+var_5B0]
0x18002c165  test    edi, edi
0x18002c167  jnz     short loc_18002C12B
0x18002c169  xor     ecx, ecx; dwErrCode
0x18002c16b  call    cs:__imp_SetLastError
0x18002c172  nop     dword ptr [rax+rax+00h]
0x18002c177  mov     r8, [rbp+500h+var_4E0]; unsigned __int64
0x18002c17b  lea     r9, [rsp+600h+var_5C0]; bool *
0x18002c180  mov     rdx, [rbp+500h+var_4F0]; unsigned __int16 *
0x18002c184  lea     rcx, [rsp+600h+var_5A8]; union _ASSEMBLY_VERSION *
0x18002c189  call    ?ParseVersion@CFusionParser@@SAHAEAT_ASSEMBLY_VERSION@@PEBG_KAEA_N@Z; CFusionParser::ParseVersion(_ASSEMBLY_VERSION &,ushort const *,unsigned __int64,bool &)
0x18002c18e  test    eax, eax
0x18002c190  jz      short loc_18002C1AF
0x18002c192  cmp     [rsp+600h+var_5A8], rbx
0x18002c197  jbe     short loc_18002C12B
0x18002c199  cmp     [rsp+600h+var_5C0], dil
0x18002c19e  jz      short loc_18002C12B
0x18002c1a0  mov     rbx, [rsp+600h+var_5A8]
0x18002c1a5  mov     [rsp+600h+var_5B8], rbx
0x18002c1aa  jmp     loc_18002C12B
0x18002c1af  xor     esi, esi
0x18002c1b1  lea     rcx, off_18007C120; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18002c1b8  jmp     loc_18002BECE
0x18002c1bd  xor     esi, esi
0x18002c1bf  lea     rcx, off_18007C140; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18002c1c6  jmp     loc_18002BECE
0x18002c1cb  call    cs:__imp_SetLastError
0x18002c1d2  nop     dword ptr [rax+rax+00h]
0x18002c1d7  movzx   eax, word ptr [rsp+600h+var_5B8]
0x18002c1dc  lea     rdx, aUUUU; "%u.%u.%u.%u"
0x18002c1e3  movzx   ecx, word ptr [rsp+600h+var_5B8+2]
0x18002c1e8  movzx   r9d, word ptr [rsp+600h+var_5B8+4]
0x18002c1ee  movzx   r8d, word ptr [rsp+600h+var_5B8+6]
0x18002c1f4  mov     dword ptr [rsp+600h+var_5D8], eax
0x18002c1f8  mov     dword ptr [rsp+600h+phkResult], ecx; unsigned int
0x18002c1fc  lea     rcx, [rbp+500h+var_500]
0x18002c200  call    ?Win32Format@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBGZZ; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Format(ushort const *,...)
0x18002c205  xor     esi, esi
0x18002c207  test    eax, eax
0x18002c209  jnz     short loc_18002C217
0x18002c20b  lea     rcx, off_18007C100; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18002c212  jmp     loc_18002BECE
0x18002c217  xor     ecx, ecx; dwErrCode
0x18002c219  call    cs:__imp_SetLastError
0x18002c220  nop     dword ptr [rax+rax+00h]
0x18002c225  mov     r8, [rbp+500h+var_4F0]; unsigned __int16 *
0x18002c229  lea     rdx, [rsp+600h+var_598]; struct CRegKey *
0x18002c22e  lea     rcx, [rsp+600h+var_5A0]; this
0x18002c233  call    ?OpenSubKey@CRegKey@@QEBAHAEAV1@PEBGKK@Z; CRegKey::OpenSubKey(CRegKey &,ushort const *,ulong,ulong)
0x18002c238  test    eax, eax
0x18002c23a  jnz     short loc_18002C248
0x18002c23c  lea     rcx, off_18007C0E0; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18002c243  jmp     loc_18002BECE
0x18002c248  cmp     [rsp+600h+var_598], rsi
0x18002c24d  jz      loc_18002C364
0x18002c253  xor     ecx, ecx; dwErrCode
0x18002c255  call    cs:__imp_SetLastError
0x18002c25c  nop     dword ptr [rax+rax+00h]
0x18002c261  lea     rax, [rsp+600h+var_5B0+4]
0x18002c266  mov     qword ptr [rsp+600h+var_5D8], rsi
0x18002c26b  mov     ebx, 1
0x18002c270  mov     [rsp+600h+phkResult], rax
0x18002c275  mov     edx, ebx
0x18002c277  lea     r9, [rbp+500h+var_578]
0x18002c27b  lea     r8, aTargetnamespac; "targetNamespace"
0x18002c282  lea     rcx, [rsp+600h+var_598]
0x18002c287  call    ?GetValue@CRegKey@@QEAAHKPEBGAEAV?$CFusionArray@EE$0A@$0CA@@@AEAK_KZZ; CRegKey::GetValue(ulong,ushort const *,CFusionArray<uchar,uchar,0,32> &,ulong &,unsigned __int64,...)
0x18002c28c  test    eax, eax
0x18002c28e  jnz     short loc_18002C29C
0x18002c290  lea     rcx, off_18007C0C0; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18002c297  jmp     loc_18002BECE
0x18002c29c  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002c2a0  inc     r9
0x18002c2a3  cmp     [r15+r9*2], si
  ... truncated ...
```
