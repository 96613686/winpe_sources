# CBlbBackupAsync::WriteRegistryExcludes(void)

- ea: `0x14003b4e4`
- end: `0x14003b91d`
- name: `?WriteRegistryExcludes@CBlbBackupAsync@@AEAAJXZ`
- size: `1081`
- prototype: `__int64 __fastcall(CBlbBackupAsync *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140039ec0`

## callees

- `0x140006a64`
- `0x140006ca8`
- `0x140006d94`
- `0x140008ac8`
- `0x14000bb4c`
- `0x14000bfd8`
- `0x14000fe94`
- `0x140014260`
- `0x140014384`
- `0x140014798`
- `0x1400149e0`
- `0x140028eb8`
- `0x140035350`
- `0x140035468`
- `0x14003b4e4`
- `0x1400889f0`
- `0x1400f25c0`
- `0x1400f3bbc`
- `0x1400f4d48`
- `0x14010240c`
- `0x140119828`
- `0x14012149c`
- `0x1401296f0`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x14003b5ff`
- `KERNEL32!DeleteFileW` at `0x14003b5ff`
- `KERNEL32!GetLastError` at `0x14003b609`
- `KERNEL32!GetLastError` at `0x14003b609`
- `ole32!CoTaskMemFree` at `0x14003b839`
- `ole32!CoTaskMemFree` at `0x14003b850`
- `ole32!CoTaskMemFree` at `0x14003b85e`
- `ole32!CoTaskMemFree` at `0x14003b86c`
- `ole32!CoTaskMemFree` at `0x14003b839`
- `ole32!CoTaskMemFree` at `0x14003b850`
- `ole32!CoTaskMemFree` at `0x14003b85e`
- `ole32!CoTaskMemFree` at `0x14003b86c`
- `OLEAUT32!__imp_SysFreeString` at `0x14003b895`
- `OLEAUT32!__imp_SysFreeString` at `0x14003b901`
- `OLEAUT32!__imp_SysFreeString` at `0x14003b895`
- `OLEAUT32!__imp_SysFreeString` at `0x14003b901`

## string_xrefs

- `0x14003b555`: `base\stor\blb\engine\service\backup.cpp`
- `0x14003b549`: `m_wszBackupSetDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CBlbBackupAsync::WriteRegistryExcludes(CBlbBackupAsync *this)
{
  unsigned __int16 *v2; // r12
  WCHAR *v3; // rsi
  unsigned __int16 *v4; // r14
  signed int appended; // edi
  int File; // eax
  DWORD LastError; // eax
  int v8; // eax
  __int64 v9; // rcx
  WCHAR *v10; // rax
  CBlbFileVerifier *v11; // r15
  __int64 v12; // r8
  _QWORD *v13; // rbx
  unsigned __int64 v14; // r13
  unsigned int i; // esi
  BSTR *v16; // rbx
  unsigned __int16 *v18; // [rsp+30h] [rbp-39h] BYREF
  __int64 v19; // [rsp+38h] [rbp-31h] BYREF
  unsigned __int64 v20; // [rsp+40h] [rbp-29h]
  __int64 v21; // [rsp+48h] [rbp-21h]
  int v22; // [rsp+50h] [rbp-19h]
  void *v23[3]; // [rsp+58h] [rbp-11h] BYREF
  int v24; // [rsp+70h] [rbp+7h]
  LPCWSTR lpFileName; // [rsp+D0h] [rbp+67h] BYREF
  LPVOID pv; // [rsp+D8h] [rbp+6Fh] BYREF
  BSTR bstrString; // [rsp+E0h] [rbp+77h] BYREF
  unsigned __int16 *v28; // [rsp+E8h] [rbp+7Fh] BYREF

  v2 = 0;
  v28 = 0;
  v3 = 0;
  lpFileName = 0;
  v4 = 0;
  v18 = 0;
  pv = 0;
  bstrString = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  memset(v23, 0, sizeof(v23));
  v24 = 0;
  if ( !*((_QWORD *)this + 59) )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x1DECu, "m_wszBackupSetDirectory");
  if ( (*((_BYTE *)this + 340) & 4) == 0 )
    goto LABEL_19;
  appended = BlbAppendRegistryExcludesFile(*((unsigned __int16 **)this + 59), 0, 0, &v28);
  v2 = v28;
  if ( appended < 0 )
    goto LABEL_52;
  File = BlbFindFile(v28, (unsigned __int16 **)&lpFileName);
  appended = File;
  if ( File >= 0 )
  {
    v3 = (WCHAR *)lpFileName;
    if ( lpFileName && !DeleteFileW(lpFileName) )
    {
      LastError = GetLastError();
      appended = LastError;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          363,
          (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
          (_DWORD)v3,
          LastError);
      }
      if ( appended > 0 )
        appended = (unsigned __int16)appended | 0x80070000;
      goto LABEL_48;
    }
LABEL_19:
    appended = BlbAppendRegistryExcludesFile(*((unsigned __int16 **)this + 59), (UUID *)((char *)this + 296), 0, &v18);
    v4 = v18;
    if ( appended >= 0 )
    {
      if ( (*((_BYTE *)this + 340) & 1) != 0 )
        v8 = BlbutilDuplicateString(v18, (unsigned __int16 **)&pv, 0);
      else
        v8 = BlbAppendRegistryExcludesFile(
               *((unsigned __int16 **)this + 59),
               (UUID *)((char *)this + 296),
               1u,
               (unsigned __int16 **)&pv);
      appended = v8;
      if ( v8 >= 0 )
      {
        v9 = *((_QWORD *)this + 57);
        if ( !v9 || (appended = BlbGetRegistryFNTBKeysToIgnore(v9, &v19), appended >= 0) )
        {
          appended = BlbConvertFilePathArrayToSpecsArray((char *)this + 1000, v23);
          if ( appended >= 0 )
          {
            appended = CExclusionHelper::GetExpandedRegistryExcludes(&v19, v23, &bstrString);
            if ( appended >= 0 )
            {
              appended = BlbSafeDumpFile(v4, pv, *((unsigned int *)this + 84), bstrString);
              if ( appended >= 0 && *((char *)this + 340) < 0 && *((_BYTE *)this + 276) )
              {
                v10 = (WCHAR *)operator new(0x40u);
                lpFileName = v10;
                v11 = v10 ? CBlbFileVerifier::CBlbFileVerifier((CBlbFileVerifier *)v10) : 0LL;
                appended = CBlbFileVerifier::Init(v11, v4);
                if ( appended >= 0 )
                {
                  v12 = -1;
                  do
                    ++v12;
                  while ( bstrString[v12] );
                  appended = CBlbFileVerifier::SetChecksumForData(v11, bstrString, 2 * v12 + 2);
                  if ( appended >= 0 )
                  {
                    v13 = (_QWORD *)((char *)this + 776);
                    v14 = v13[1];
                    if ( v14 >= v13[2]
                      && !(unsigned __int8)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(
                                             v13,
                                             v14 + 1) )
                    {
                      ATL::AtlThrowImpl(-2147024882);
                    }
                    *(_QWORD *)(*v13 + 8 * v14) = v11;
                    ++v13[1];
                  }
                }
              }
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 364, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
          }
        }
      }
      if ( pv )
        CoTaskMemFree(pv);
    }
    goto LABEL_48;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_SSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      362,
      (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
      (_DWORD)v2,
      *((_QWORD *)this + 59),
      File);
  }
  v3 = (WCHAR *)lpFileName;
LABEL_48:
  if ( v3 )
    CoTaskMemFree(v3);
  if ( v4 )
    CoTaskMemFree(v4);
LABEL_52:
  if ( v2 )
    CoTaskMemFree(v2);
  CWsbStructUtil::FreeFileSpecInfo(v23);
  for ( i = 0; i < v20; ++i )
  {
    v16 = (BSTR *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                    &v19,
                    i);
    SysFreeString(*v16);
    *v16 = 0;
  }
  ATL::CAtlArray<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::SetCount(&v19, 0);
  if ( appended < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 365, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(v23);
  ATL::CAtlArray<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::~CAtlArray<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>((__int64)&v19);
  SysFreeString(bstrString);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14003b4e4  push    rbp
0x14003b4e6  push    rbx
0x14003b4e7  push    rsi
0x14003b4e8  push    rdi
0x14003b4e9  push    r12
0x14003b4eb  push    r13
0x14003b4ed  push    r14
0x14003b4ef  push    r15
0x14003b4f1  lea     rbp, [rsp-1Fh]
0x14003b4f6  sub     rsp, 88h
0x14003b4fd  mov     rbx, rcx
0x14003b500  xor     r13d, r13d
0x14003b503  mov     r12d, r13d
0x14003b506  mov     [rbp+57h+arg_18], r13
0x14003b50a  mov     esi, r13d
0x14003b50d  mov     [rbp+57h+lpFileName], r13
0x14003b511  mov     r14d, r13d
0x14003b514  mov     [rbp+57h+var_90], r13
0x14003b518  mov     [rbp+57h+pv], r13
0x14003b51c  mov     [rbp+57h+bstrString], r13
0x14003b520  mov     [rbp+57h+var_88], r13
0x14003b524  mov     [rbp+57h+var_80], r13
0x14003b528  mov     [rbp+57h+var_78], r13
0x14003b52c  mov     [rbp+57h+var_70], r13d
0x14003b530  mov     [rbp+57h+var_68], r13
0x14003b534  mov     [rbp+57h+var_60], r13
0x14003b538  mov     [rbp+57h+var_58], r13
0x14003b53c  mov     [rbp+57h+var_50], r13d
0x14003b540  cmp     [rcx+1D8h], r13
0x14003b547  jnz     short loc_14003B561
0x14003b549  lea     r8, aMWszbackupsetd; "m_wszBackupSetDirectory"
0x14003b550  mov     edx, 1DECh; unsigned int
0x14003b555  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x14003b55c  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14003b561  lea     r15, WPP_GLOBAL_Control
0x14003b568  test    byte ptr [rbx+154h], 4
0x14003b56f  jz      loc_14003B65B
0x14003b575  lea     r9, [rbp+57h+arg_18]; unsigned __int16 **
0x14003b579  xor     r8d, r8d; unsigned __int8
0x14003b57c  xor     edx, edx; Uuid
0x14003b57e  mov     rcx, [rbx+1D8h]; unsigned __int16 *
0x14003b585  call    ?BlbAppendRegistryExcludesFile@@YAJPEAGPEAU_GUID@@EPEAPEAG@Z; BlbAppendRegistryExcludesFile(ushort *,_GUID *,uchar,ushort * *)
0x14003b58a  mov     edi, eax
0x14003b58c  mov     r12, [rbp+57h+arg_18]
0x14003b590  test    eax, eax
0x14003b592  js      loc_14003B864
0x14003b598  lea     rdx, [rbp+57h+lpFileName]; unsigned __int16 **
0x14003b59c  mov     rcx, r12; unsigned __int16 *
0x14003b59f  call    ?BlbFindFile@@YAJPEAGPEAPEAG@Z; BlbFindFile(ushort *,ushort * *)
0x14003b5a4  mov     edi, eax
0x14003b5a6  test    eax, eax
0x14003b5a8  jns     short loc_14003B5F3
0x14003b5aa  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b5b1  cmp     rcx, r15
0x14003b5b4  jz      short loc_14003B5EA
0x14003b5b6  test    byte ptr [rcx+1Ch], 1
0x14003b5ba  jz      short loc_14003B5EA
0x14003b5bc  cmp     byte ptr [rcx+19h], 2
0x14003b5c0  jb      short loc_14003B5EA
0x14003b5c2  mov     edx, 16Ah
0x14003b5c7  mov     [rsp+0C0h+var_98], eax
0x14003b5cb  mov     rax, [rbx+1D8h]
0x14003b5d2  mov     [rsp+0C0h+var_A0], rax
0x14003b5d7  mov     r9, r12
0x14003b5da  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003b5e1  mov     rcx, [rcx+10h]
0x14003b5e5  call    WPP_SF_SSD
0x14003b5ea  mov     rsi, [rbp+57h+lpFileName]
0x14003b5ee  jmp     loc_14003B848
0x14003b5f3  mov     rsi, [rbp+57h+lpFileName]
0x14003b5f7  test    rsi, rsi
0x14003b5fa  jz      short loc_14003B65B
0x14003b5fc  mov     rcx, rsi; lpFileName
0x14003b5ff  call    cs:__imp_DeleteFileW
0x14003b605  test    eax, eax
0x14003b607  jnz     short loc_14003B65B
0x14003b609  call    cs:__imp_GetLastError
0x14003b60f  mov     edi, eax
0x14003b611  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b618  cmp     rcx, r15
0x14003b61b  jz      short loc_14003B645
0x14003b61d  test    byte ptr [rcx+1Ch], 1
0x14003b621  jz      short loc_14003B645
0x14003b623  cmp     byte ptr [rcx+19h], 2
0x14003b627  jb      short loc_14003B645
0x14003b629  mov     edx, 16Bh
0x14003b62e  mov     dword ptr [rsp+0C0h+var_A0], eax
0x14003b632  mov     r9, rsi
0x14003b635  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003b63c  mov     rcx, [rcx+10h]
0x14003b640  call    WPP_SF_Sd
0x14003b645  test    edi, edi
0x14003b647  jle     loc_14003B848
0x14003b64d  movzx   edi, di
0x14003b650  or      edi, 80070000h
0x14003b656  jmp     loc_14003B848
0x14003b65b  lea     r15, [rbx+128h]
0x14003b662  lea     r9, [rbp+57h+var_90]; unsigned __int16 **
0x14003b666  xor     r8d, r8d; unsigned __int8
0x14003b669  mov     rdx, r15; Uuid
0x14003b66c  mov     rcx, [rbx+1D8h]; unsigned __int16 *
0x14003b673  call    ?BlbAppendRegistryExcludesFile@@YAJPEAGPEAU_GUID@@EPEAPEAG@Z; BlbAppendRegistryExcludesFile(ushort *,_GUID *,uchar,ushort * *)
0x14003b678  mov     edi, eax
0x14003b67a  mov     r14, [rbp+57h+var_90]
0x14003b67e  test    eax, eax
0x14003b680  js      loc_14003B841
0x14003b686  test    byte ptr [rbx+154h], 1
0x14003b68d  jz      short loc_14003B6A0
0x14003b68f  xor     r8d, r8d; unsigned __int64
0x14003b692  lea     rdx, [rbp+57h+pv]; unsigned __int16 **
0x14003b696  mov     rcx, r14; unsigned __int16 *
0x14003b699  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14003b69e  jmp     short loc_14003B6B6
0x14003b6a0  lea     r9, [rbp+57h+pv]; unsigned __int16 **
0x14003b6a4  mov     r8b, 1; unsigned __int8
0x14003b6a7  mov     rdx, r15; Uuid
0x14003b6aa  mov     rcx, [rbx+1D8h]; unsigned __int16 *
0x14003b6b1  call    ?BlbAppendRegistryExcludesFile@@YAJPEAGPEAU_GUID@@EPEAPEAG@Z; BlbAppendRegistryExcludesFile(ushort *,_GUID *,uchar,ushort * *)
0x14003b6b6  test    eax, eax
0x14003b6b8  mov     edi, eax
0x14003b6ba  js      loc_14003B829
0x14003b6c0  mov     rcx, [rbx+1C8h]
0x14003b6c7  test    rcx, rcx
0x14003b6ca  jz      short loc_14003B6DF
0x14003b6cc  lea     rdx, [rbp+57h+var_88]
0x14003b6d0  call    ?BlbGetRegistryFNTBKeysToIgnore@@YAJPEAU_SPP_METADATA_PROP@@AEAV?$CAtlArray@VCComBSTR@ATL@@V?$CElementTraits@VCComBSTR@ATL@@@2@@ATL@@@Z; BlbGetRegistryFNTBKeysToIgnore(_SPP_METADATA_PROP *,ATL::CAtlArray<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>> &)
0x14003b6d5  mov     edi, eax
0x14003b6d7  test    eax, eax
0x14003b6d9  js      loc_14003B829
0x14003b6df  lea     rcx, [rbx+3E8h]
0x14003b6e6  lea     rdx, [rbp+57h+var_68]
0x14003b6ea  call    ?BlbConvertFilePathArrayToSpecsArray@@YAJAEAV?$CAtlList@PEAGV?$CElementTraits@PEAG@ATL@@@ATL@@AEAV?$CAtlArray@U_WSB_SPEC_INFO@@V?$CElementTraits@U_WSB_SPEC_INFO@@@ATL@@@2@@Z; BlbConvertFilePathArrayToSpecsArray(ATL::CAtlList<ushort *,ATL::CElementTraits<ushort *>> &,ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>> &)
0x14003b6ef  mov     edi, eax
0x14003b6f1  test    eax, eax
0x14003b6f3  jns     short loc_14003B73D
0x14003b6f5  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b6fc  lea     r15, WPP_GLOBAL_Control
0x14003b703  cmp     rcx, r15
0x14003b706  jz      loc_14003B830
0x14003b70c  test    byte ptr [rcx+1Ch], 1
0x14003b710  jz      loc_14003B830
0x14003b716  cmp     byte ptr [rcx+19h], 2
0x14003b71a  jb      loc_14003B830
0x14003b720  mov     edx, 16Ch
0x14003b725  mov     r9d, eax
0x14003b728  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003b72f  mov     rcx, [rcx+10h]
0x14003b733  call    WPP_SF_d
0x14003b738  jmp     loc_14003B830
0x14003b73d  lea     r8, [rbp+57h+bstrString]
0x14003b741  lea     rdx, [rbp+57h+var_68]
0x14003b745  lea     rcx, [rbp+57h+var_88]
0x14003b749  call    ?GetExpandedRegistryExcludes@CExclusionHelper@@SAJAEBV?$CAtlArray@VCComBSTR@ATL@@V?$CElementTraits@VCComBSTR@ATL@@@2@@ATL@@AEBV?$CAtlArray@U_WSB_SPEC_INFO@@V?$CElementTraits@U_WSB_SPEC_INFO@@@ATL@@@3@AEAVCComBSTR@3@@Z; CExclusionHelper::GetExpandedRegistryExcludes(ATL::CAtlArray<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>> const &,ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>> const &,ATL::CComBSTR &)
0x14003b74e  mov     edi, eax
0x14003b750  test    eax, eax
0x14003b752  js      loc_14003B829
0x14003b758  mov     r9, [rbp+57h+bstrString]
0x14003b75c  mov     r8d, [rbx+150h]
0x14003b763  mov     rdx, [rbp+57h+pv]
0x14003b767  mov     rcx, r14
0x14003b76a  call    ?BlbSafeDumpFile@@YAJPEBG0W4_BLB_MEDIA_TYPE@@0@Z; BlbSafeDumpFile(ushort const *,ushort const *,_BLB_MEDIA_TYPE,ushort const *)
0x14003b76f  mov     edi, eax
0x14003b771  test    eax, eax
0x14003b773  js      loc_14003B829
0x14003b779  test    byte ptr [rbx+154h], 80h
0x14003b780  jz      loc_14003B829
0x14003b786  cmp     [rbx+114h], r13b
0x14003b78d  jz      loc_14003B829
0x14003b793  mov     ecx, 40h ; '@'; Size
0x14003b798  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003b79d  mov     [rbp+57h+lpFileName], rax
0x14003b7a1  test    rax, rax
0x14003b7a4  jz      short loc_14003B7B3
0x14003b7a6  mov     rcx, rax; this
0x14003b7a9  call    ??0CBlbFileVerifier@@QEAA@XZ; CBlbFileVerifier::CBlbFileVerifier(void)
0x14003b7ae  mov     r15, rax
0x14003b7b1  jmp     short loc_14003B7B6
0x14003b7b3  mov     r15, r13
0x14003b7b6  mov     rdx, r14; unsigned __int16 *
0x14003b7b9  mov     rcx, r15; this
0x14003b7bc  call    ?Init@CBlbFileVerifier@@QEAAJPEAG@Z; CBlbFileVerifier::Init(ushort *)
0x14003b7c1  mov     edi, eax
0x14003b7c3  test    eax, eax
0x14003b7c5  js      short loc_14003B829
0x14003b7c7  mov     rdx, [rbp+57h+bstrString]; void *
0x14003b7cb  or      r8, 0FFFFFFFFFFFFFFFFh
0x14003b7cf  inc     r8
0x14003b7d2  cmp     [rdx+r8*2], r13w
0x14003b7d7  jnz     short loc_14003B7CF
0x14003b7d9  lea     r8, ds:2[r8*2]; unsigned __int64
0x14003b7e1  mov     rcx, r15; this
0x14003b7e4  call    ?SetChecksumForData@CBlbFileVerifier@@QEAAJPEAX_K@Z; CBlbFileVerifier::SetChecksumForData(void *,unsigned __int64)
0x14003b7e9  mov     edi, eax
0x14003b7eb  test    eax, eax
0x14003b7ed  js      short loc_14003B829
0x14003b7ef  add     rbx, 308h
0x14003b7f6  mov     r13, [rbx+8]
0x14003b7fa  cmp     r13, [rbx+10h]
0x14003b7fe  jb      short loc_14003B81B
0x14003b800  lea     rdx, [r13+1]
0x14003b804  mov     rcx, rbx
0x14003b807  call    ?GrowBuffer@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(unsigned __int64)
0x14003b80c  test    al, al
0x14003b80e  jnz     short loc_14003B81B
0x14003b810  mov     ecx, 8007000Eh; int
0x14003b815  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14003b81b  mov     rax, [rbx]
0x14003b81e  mov     [rax+r13*8], r15
0x14003b822  inc     qword ptr [rbx+8]
0x14003b826  xor     r13d, r13d
0x14003b829  lea     r15, WPP_GLOBAL_Control
0x14003b830  mov     rcx, [rbp+57h+pv]; pv
0x14003b834  test    rcx, rcx
0x14003b837  jz      short loc_14003B848
0x14003b839  call    cs:__imp_CoTaskMemFree
0x14003b83f  jmp     short loc_14003B848
0x14003b841  lea     r15, WPP_GLOBAL_Control
0x14003b848  test    rsi, rsi
0x14003b84b  jz      short loc_14003B856
0x14003b84d  mov     rcx, rsi; pv
0x14003b850  call    cs:__imp_CoTaskMemFree
0x14003b856  test    r14, r14
0x14003b859  jz      short loc_14003B864
0x14003b85b  mov     rcx, r14; pv
0x14003b85e  call    cs:__imp_CoTaskMemFree
0x14003b864  test    r12, r12
0x14003b867  jz      short loc_14003B872
0x14003b869  mov     rcx, r12; pv
0x14003b86c  call    cs:__imp_CoTaskMemFree
0x14003b872  lea     rcx, [rbp+57h+var_68]
0x14003b876  call    ?FreeFileSpecInfo@CWsbStructUtil@@SAXAEAV?$CAtlArray@U_WSB_SPEC_INFO@@V?$CElementTraits@U_WSB_SPEC_INFO@@@ATL@@@ATL@@@Z; CWsbStructUtil::FreeFileSpecInfo(ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>> &)
0x14003b87b  mov     esi, r13d
0x14003b87e  cmp     [rbp+57h+var_80], r13
0x14003b882  jbe     short loc_14003B8A8
0x14003b884  mov     edx, esi
0x14003b886  lea     rcx, [rbp+57h+var_88]
0x14003b88a  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x14003b88f  mov     rbx, rax
0x14003b892  mov     rcx, [rax]; bstrString
0x14003b895  call    cs:__imp_SysFreeString
0x14003b89b  mov     [rbx], r13
0x14003b89e  inc     esi
0x14003b8a0  mov     eax, esi
0x14003b8a2  cmp     rax, [rbp+57h+var_80]
0x14003b8a6  jb      short loc_14003B884
0x14003b8a8  xor     edx, edx
0x14003b8aa  lea     rcx, [rbp+57h+var_88]
0x14003b8ae  call    ?SetCount@?$CAtlArray@VCComBSTR@ATL@@V?$CElementTraits@VCComBSTR@ATL@@@2@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::SetCount(unsigned __int64,int)
0x14003b8b3  nop
0x14003b8b4  test    edi, edi
0x14003b8b6  jns     short loc_14003B8E9
0x14003b8b8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b8bf  cmp     rcx, r15
0x14003b8c2  jz      short loc_14003B8E9
0x14003b8c4  test    byte ptr [rcx+1Ch], 1
0x14003b8c8  jz      short loc_14003B8E9
0x14003b8ca  cmp     byte ptr [rcx+19h], 2
0x14003b8ce  jb      short loc_14003B8E9
0x14003b8d0  mov     edx, 16Dh
0x14003b8d5  mov     r9d, edi
0x14003b8d8  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003b8df  mov     rcx, [rcx+10h]
0x14003b8e3  call    WPP_SF_d
0x14003b8e8  nop
0x14003b8e9  lea     rcx, [rbp+57h+var_68]
0x14003b8ed  call    ??1?$CAtlArray@U_BLB_COMPONENT@@V?$CElementTraits@U_BLB_COMPONENT@@@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(void)
0x14003b8f2  nop
0x14003b8f3  lea     rcx, [rbp+57h+var_88]
0x14003b8f7  call    ??1?$CAtlArray@VCComBSTR@ATL@@V?$CElementTraits@VCComBSTR@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::~CAtlArray<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>(void)
0x14003b8fc  nop
0x14003b8fd  mov     rcx, [rbp+57h+bstrString]; bstrString
0x14003b901  call    cs:__imp_SysFreeString
0x14003b907  mov     eax, edi
0x14003b909  add     rsp, 88h
0x14003b910  pop     r15
0x14003b912  pop     r14
0x14003b914  pop     r13
0x14003b916  pop     r12
0x14003b918  pop     rdi
0x14003b919  pop     rsi
0x14003b91a  pop     rbx
0x14003b91b  pop     rbp
0x14003b91c  retn
```
