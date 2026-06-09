# CBlbSystemStateRestoreAsync::InitializeSSRHelper(void)

- ea: `0x140076c6c`
- end: `0x140077028`
- name: `?InitializeSSRHelper@CBlbSystemStateRestoreAsync@@QEAAJXZ`
- size: `956`
- prototype: `__int64 __fastcall(CBlbSystemStateRestoreAsync *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140075000`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x140076c6c`
- `0x1400820f8`
- `0x1400877b0`
- `0x14008d84c`
- `0x1400f007c`
- `0x1400f07dc`
- `0x1400f16ac`
- `0x1400f2f64`
- `0x1400f532c`
- `0x1400f59d0`
- `0x1400f5ca8`
- `0x14011acc0`
- `0x140137010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140076f16`
- `ole32!CoTaskMemFree` at `0x140076f25`
- `ole32!CoTaskMemFree` at `0x140076f34`
- `ole32!CoTaskMemFree` at `0x140076f4f`
- `ole32!CoTaskMemFree` at `0x140076f68`
- `ole32!CoTaskMemFree` at `0x140076f81`
- `ole32!CoTaskMemFree` at `0x140076f9a`
- `ole32!CoTaskMemFree` at `0x140076fc1`
- `ole32!CoTaskMemFree` at `0x140076fd4`
- `ole32!CoTaskMemFree` at `0x140076f16`
- `ole32!CoTaskMemFree` at `0x140076f25`
- `ole32!CoTaskMemFree` at `0x140076f34`
- `ole32!CoTaskMemFree` at `0x140076f4f`
- `ole32!CoTaskMemFree` at `0x140076f68`
- `ole32!CoTaskMemFree` at `0x140076f81`
- `ole32!CoTaskMemFree` at `0x140076f9a`
- `ole32!CoTaskMemFree` at `0x140076fc1`
- `ole32!CoTaskMemFree` at `0x140076fd4`

## string_xrefs

- `0x140076dda`: `base\stor\blb\engine\service\systemstaterestore.cpp`
- `0x140076dce`: `cNonWriterMetaDataFiles == 1`
- `0x140076d78`: `*_AdditionalFiles*.xml`
- `0x140076eac`: `*_AdditionalFiles*.xml`
- `0x140076ee4`: `*_AdditionalFiles*.xml`
- `0x140076d57`: `*_Writer*.xml`
- `0x140076e93`: `*_Writer*.xml`
- `0x140076ec5`: `*_Writer*.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBlbSystemStateRestoreAsync::InitializeSSRHelper(CBlbSystemStateRestoreAsync *this)
{
  unsigned __int16 *v2; // r14
  unsigned __int16 **v3; // rsi
  unsigned __int16 **v4; // r15
  unsigned int v5; // r12d
  int Path; // ebx
  int v7; // eax
  int AllMatchingFiles; // eax
  int v9; // eax
  int v10; // eax
  unsigned int i; // edi
  unsigned __int16 *v12; // rcx
  unsigned int j; // edi
  unsigned __int16 *v14; // rcx
  unsigned __int16 **v16; // [rsp+40h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-41h] BYREF
  unsigned __int16 *v18; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int16 *v19; // [rsp+58h] [rbp-31h] BYREF
  __int64 v20; // [rsp+60h] [rbp-29h]
  struct _BLBSRV_VOLUME_INFO *v21[2]; // [rsp+68h] [rbp-21h] BYREF
  LPVOID v22[2]; // [rsp+78h] [rbp-11h]
  LPVOID v23[2]; // [rsp+88h] [rbp-1h]
  struct _BLBSRV_COMPONENT_INFO *v24; // [rsp+98h] [rbp+Fh] BYREF
  unsigned __int8 v25; // [rsp+F0h] [rbp+67h] BYREF
  unsigned int v26; // [rsp+F8h] [rbp+6Fh] BYREF
  unsigned int v27; // [rsp+100h] [rbp+77h] BYREF
  unsigned __int16 **v28; // [rsp+108h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids);
  }
  v19 = 0;
  v2 = 0;
  pv = 0;
  v18 = 0;
  v3 = 0;
  v28 = 0;
  v4 = 0;
  v16 = 0;
  v5 = 0;
  v26 = 0;
  v27 = 0;
  v25 = 0;
  v20 = *((_QWORD *)this + 38);
  v24 = 0;
  *(_OWORD *)v21 = 0;
  *(_OWORD *)v22 = 0;
  *(_OWORD *)v23 = 0;
  Path = CBlbImpersonationHelper::ImpersonateCaller((CBlbSystemStateRestoreAsync *)((char *)this + 16), 0);
  if ( Path >= 0 )
  {
    Path = BlbutilCheckNetworkShare(*((const unsigned __int16 **)this + 34), 0, &v25);
    CBlbImpersonationHelper::Revert((CBlbSystemStateRestoreAsync *)((char *)this + 16));
    if ( Path >= 0 )
    {
      if ( v25 )
      {
        v10 = BlbCreateMetaDataDirectory(&v19);
        v2 = v19;
        Path = v10;
        if ( v10 < 0 )
          goto LABEL_25;
        Path = BlbutilGetPath(v19, L"*_Writer*.xml", (unsigned __int16 **)&pv);
        if ( Path < 0 )
          goto LABEL_25;
        Path = BlbutilGetPath(v2, L"*_AdditionalFiles*.xml", &v18);
        if ( Path < 0 )
          goto LABEL_25;
        Path = BlbCopyMetadataFilesMatchingPattern(
                 *((const unsigned __int16 **)this + 34),
                 v2,
                 L"*_Writer*.xml",
                 (CBlbSystemStateRestoreAsync *)((char *)this + 16));
        if ( Path < 0 )
          goto LABEL_25;
        v7 = BlbCopyMetadataFilesMatchingPattern(
               *((const unsigned __int16 **)this + 34),
               v2,
               L"*_AdditionalFiles*.xml",
               (CBlbSystemStateRestoreAsync *)((char *)this + 16));
      }
      else
      {
        Path = BlbutilGetPath(*((const unsigned __int16 **)this + 34), L"*_Writer*.xml", (unsigned __int16 **)&pv);
        if ( Path < 0 )
          goto LABEL_25;
        v7 = BlbutilGetPath(*((const unsigned __int16 **)this + 34), L"*_AdditionalFiles*.xml", &v18);
      }
      Path = v7;
      if ( v7 < 0 )
        goto LABEL_25;
      Path = BlbGetAllMatchingFiles((unsigned __int16 *)pv, &v28, &v26);
      if ( Path >= 0 )
      {
        AllMatchingFiles = BlbGetAllMatchingFiles(v18, &v16, &v27);
        v5 = v27;
        Path = AllMatchingFiles;
        if ( AllMatchingFiles >= 0 )
        {
          if ( v27 != 1 )
            BlbAssert(
              "base\\stor\\blb\\engine\\service\\systemstaterestore.cpp",
              0x898u,
              "cNonWriterMetaDataFiles == 1");
          v9 = BlbFillBackupInfo(
                 *((const struct _BLBCAT_BACKUP_SET_INFO **)this + 71),
                 (struct _BLBSRV_BACKUP_INFO *)v21);
          v4 = v16;
          Path = v9;
          v3 = v28;
          if ( v9 >= 0 )
          {
            Path = (*(__int64 (__fastcall **)(__int64, struct _BLBSRV_VOLUME_INFO **, unsigned __int16 **, _QWORD, unsigned __int16 *, _BYTE, bool))(*(_QWORD *)v20 + 128LL))(
                     v20,
                     v21,
                     v28,
                     (unsigned __int16)v26,
                     *v16,
                     *((_BYTE *)this + 460),
                     *((_DWORD *)this + 117) == 3);
            if ( Path >= 0 )
              Path = CBlbFileAsync::InitializeFileLogging(
                       (CBlbSystemStateRestoreAsync *)((char *)this + 136),
                       *(struct _FILETIME *)((char *)this + 404),
                       L"SystemStateRestore",
                       L"SystemStateRestore_Error");
          }
          goto LABEL_25;
        }
        v4 = v16;
      }
      v3 = v28;
    }
  }
LABEL_25:
  CBlbImpersonationHelper::Revert((CBlbSystemStateRestoreAsync *)((char *)this + 16));
  if ( v2 )
    CoTaskMemFree(v2);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v18 )
    CoTaskMemFree(v18);
  for ( i = 0; i < v26; ++i )
  {
    v12 = v3[i];
    if ( v12 )
    {
      CoTaskMemFree(v12);
      v3[i] = 0;
    }
  }
  if ( v3 )
    CoTaskMemFree(v3);
  for ( j = 0; j < v5; ++j )
  {
    v14 = v4[j];
    if ( v14 )
    {
      CoTaskMemFree(v14);
      v4[j] = 0;
    }
  }
  if ( v4 )
    CoTaskMemFree(v4);
  BlbFreeSrvVolumeInfo(&v21[1], (unsigned int)v21[0]);
  BlbFreeSrvComponentInfo(&v24, (unsigned int)v23[1]);
  if ( v22[1] )
  {
    CoTaskMemFree(v22[1]);
    v22[1] = 0;
  }
  if ( v23[0] )
  {
    CoTaskMemFree(v23[0]);
    v23[0] = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids);
  }
  return (unsigned int)Path;
}

```

## disassembly

```asm
0x140076c6c  push    rbp
0x140076c6e  push    rbx
0x140076c6f  push    rsi
0x140076c70  push    rdi
0x140076c71  push    r12
0x140076c73  push    r13
0x140076c75  push    r14
0x140076c77  push    r15
0x140076c79  lea     rbp, [rsp-1Fh]
0x140076c7e  sub     rsp, 0A8h
0x140076c85  mov     rdi, rcx
0x140076c88  mov     rcx, cs:WPP_GLOBAL_Control
0x140076c8f  lea     rax, WPP_GLOBAL_Control
0x140076c96  cmp     rcx, rax
0x140076c99  jz      short loc_140076CBC
0x140076c9b  test    byte ptr [rcx+1Ch], 1
0x140076c9f  jz      short loc_140076CBC
0x140076ca1  cmp     byte ptr [rcx+19h], 4
0x140076ca5  jb      short loc_140076CBC
0x140076ca7  mov     rcx, [rcx+10h]
0x140076cab  lea     r8, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids
0x140076cb2  mov     edx, 4Ch ; 'L'
0x140076cb7  call    WPP_SF_
0x140076cbc  xor     eax, eax
0x140076cbe  lea     r13, [rdi+10h]
0x140076cc2  xorps   xmm0, xmm0
0x140076cc5  mov     [rbp+57h+var_88], rax
0x140076cc9  mov     r14d, eax
0x140076ccc  mov     [rbp+57h+pv], rax
0x140076cd0  mov     [rbp+57h+var_90], rax
0x140076cd4  mov     esi, eax
0x140076cd6  mov     [rbp+57h+arg_18], rax
0x140076cda  mov     r15d, eax
0x140076cdd  mov     [rbp+57h+var_A0], rax
0x140076ce1  mov     r12d, eax
0x140076ce4  mov     [rbp+57h+arg_8], eax
0x140076ce7  xor     edx, edx; unsigned __int8
0x140076ce9  mov     [rbp+57h+arg_10], eax
0x140076cec  mov     rcx, r13; this
0x140076cef  mov     [rbp+57h+arg_0], al
0x140076cf2  mov     rax, [rdi+130h]
0x140076cf9  mov     [rbp+57h+var_80], rax
0x140076cfd  xor     eax, eax
0x140076cff  mov     [rbp+57h+var_48], rax
0x140076d03  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x140076d07  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x140076d0b  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x140076d0f  call    ?ImpersonateCaller@CBlbImpersonationHelper@@QEAAJE@Z; CBlbImpersonationHelper::ImpersonateCaller(uchar)
0x140076d14  mov     ebx, eax
0x140076d16  test    eax, eax
0x140076d18  js      loc_140076F03
0x140076d1e  mov     rcx, [rdi+110h]; unsigned __int16 *
0x140076d25  lea     r8, [rbp+57h+arg_0]; unsigned __int8 *
0x140076d29  xor     edx, edx; unsigned __int8
0x140076d2b  call    ?BlbutilCheckNetworkShare@@YAJPEBGEPEAE@Z; BlbutilCheckNetworkShare(ushort const *,uchar,uchar *)
0x140076d30  mov     rcx, r13; this
0x140076d33  mov     ebx, eax
0x140076d35  call    ?Revert@CBlbImpersonationHelper@@QEAAXXZ; CBlbImpersonationHelper::Revert(void)
0x140076d3a  test    ebx, ebx
0x140076d3c  js      loc_140076F03
0x140076d42  cmp     [rbp+57h+arg_0], sil
0x140076d46  jnz     loc_140076E79
0x140076d4c  mov     rcx, [rdi+110h]; unsigned __int16 *
0x140076d53  lea     r8, [rbp+57h+pv]; unsigned __int16 **
0x140076d57  lea     rdx, aWriterXml; "*_Writer*.xml"
0x140076d5e  call    ?BlbutilGetPath@@YAJPEBG0PEAPEAG@Z; BlbutilGetPath(ushort const *,ushort const *,ushort * *)
0x140076d63  mov     ebx, eax
0x140076d65  test    eax, eax
0x140076d67  js      loc_140076F03
0x140076d6d  mov     rcx, [rdi+110h]; unsigned __int16 *
0x140076d74  lea     r8, [rbp+57h+var_90]; unsigned __int16 **
0x140076d78  lea     rdx, aAdditionalfile_2; "*_AdditionalFiles*.xml"
0x140076d7f  call    ?BlbutilGetPath@@YAJPEBG0PEAPEAG@Z; BlbutilGetPath(ushort const *,ushort const *,ushort * *)
0x140076d84  mov     ebx, eax
0x140076d86  test    eax, eax
0x140076d88  js      loc_140076F03
0x140076d8e  mov     rcx, [rbp+57h+pv]; unsigned __int16 *
0x140076d92  lea     r8, [rbp+57h+arg_8]; unsigned int *
0x140076d96  lea     rdx, [rbp+57h+arg_18]; unsigned __int16 ***
0x140076d9a  call    ?BlbGetAllMatchingFiles@@YAJPEAGPEAPEAPEAGPEAK@Z; BlbGetAllMatchingFiles(ushort *,ushort * * *,ulong *)
0x140076d9f  mov     ebx, eax
0x140076da1  test    eax, eax
0x140076da3  js      loc_140076EFF
0x140076da9  mov     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x140076dad  lea     r8, [rbp+57h+arg_10]; unsigned int *
0x140076db1  lea     rdx, [rbp+57h+var_A0]; unsigned __int16 ***
0x140076db5  call    ?BlbGetAllMatchingFiles@@YAJPEAGPEAPEAPEAGPEAK@Z; BlbGetAllMatchingFiles(ushort *,ushort * * *,ulong *)
0x140076dba  mov     r12d, [rbp+57h+arg_10]
0x140076dbe  mov     ebx, eax
0x140076dc0  test    eax, eax
0x140076dc2  js      loc_140076EFB
0x140076dc8  cmp     r12d, 1
0x140076dcc  jz      short loc_140076DE6
0x140076dce  lea     r8, aCnonwritermeta; "cNonWriterMetaDataFiles == 1"
0x140076dd5  mov     edx, 898h; unsigned int
0x140076dda  lea     rcx, aBaseStorBlbEng_41; "base\\stor\\blb\\engine\\service\\syste"...
0x140076de1  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140076de6  mov     rcx, [rdi+238h]; struct _BLBCAT_BACKUP_SET_INFO *
0x140076ded  lea     rdx, [rbp+57h+var_78]; struct _BLBSRV_BACKUP_INFO *
0x140076df1  call    ?BlbFillBackupInfo@@YAJPEBU_BLBCAT_BACKUP_SET_INFO@@PEAU_BLBSRV_BACKUP_INFO@@@Z; BlbFillBackupInfo(_BLBCAT_BACKUP_SET_INFO const *,_BLBSRV_BACKUP_INFO *)
0x140076df6  mov     r15, [rbp+57h+var_A0]
0x140076dfa  mov     ebx, eax
0x140076dfc  mov     rsi, [rbp+57h+arg_18]
0x140076e00  test    eax, eax
0x140076e02  js      loc_140076F03
0x140076e08  cmp     dword ptr [rdi+1D4h], 3
0x140076e0f  mov     r8, rsi
0x140076e12  mov     rcx, [rbp+57h+var_80]
0x140076e16  movzx   r9d, word ptr [rbp+57h+arg_8]
0x140076e1b  setz    dl
0x140076e1e  mov     [rsp+0E0h+var_B0], dl
0x140076e22  mov     dl, [rdi+1CCh]
0x140076e28  mov     rax, [rcx]
0x140076e2b  mov     [rsp+0E0h+var_B8], dl
0x140076e2f  mov     rdx, [r15]
0x140076e32  mov     [rsp+0E0h+var_C0], rdx
0x140076e37  lea     rdx, [rbp+57h+var_78]
0x140076e3b  mov     rax, [rax+80h]
0x140076e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140076e47  mov     ebx, eax
0x140076e49  test    eax, eax
0x140076e4b  js      loc_140076F03
0x140076e51  mov     rdx, [rdi+194h]; struct _FILETIME
0x140076e58  lea     rcx, [rdi+88h]; this
0x140076e5f  lea     r9, aSystemstateres_0; "SystemStateRestore_Error"
0x140076e66  lea     r8, aSystemstateres; "SystemStateRestore"
0x140076e6d  call    ?InitializeFileLogging@CBlbFileAsync@@QEAAJU_FILETIME@@PEAG1@Z; CBlbFileAsync::InitializeFileLogging(_FILETIME,ushort *,ushort *)
0x140076e72  mov     ebx, eax
0x140076e74  jmp     loc_140076F03
0x140076e79  lea     rcx, [rbp+57h+var_88]; unsigned __int16 **
0x140076e7d  call    ?BlbCreateMetaDataDirectory@@YAJPEAPEAG@Z; BlbCreateMetaDataDirectory(ushort * *)
0x140076e82  mov     r14, [rbp+57h+var_88]
0x140076e86  mov     ebx, eax
0x140076e88  test    eax, eax
0x140076e8a  js      short loc_140076F03
0x140076e8c  lea     r8, [rbp+57h+pv]; unsigned __int16 **
0x140076e90  mov     rcx, r14; unsigned __int16 *
0x140076e93  lea     rdx, aWriterXml; "*_Writer*.xml"
0x140076e9a  call    ?BlbutilGetPath@@YAJPEBG0PEAPEAG@Z; BlbutilGetPath(ushort const *,ushort const *,ushort * *)
0x140076e9f  mov     ebx, eax
0x140076ea1  test    eax, eax
0x140076ea3  js      short loc_140076F03
0x140076ea5  lea     r8, [rbp+57h+var_90]; unsigned __int16 **
0x140076ea9  mov     rcx, r14; unsigned __int16 *
0x140076eac  lea     rdx, aAdditionalfile_2; "*_AdditionalFiles*.xml"
0x140076eb3  call    ?BlbutilGetPath@@YAJPEBG0PEAPEAG@Z; BlbutilGetPath(ushort const *,ushort const *,ushort * *)
0x140076eb8  mov     ebx, eax
0x140076eba  test    eax, eax
0x140076ebc  js      short loc_140076F03
0x140076ebe  mov     rcx, [rdi+110h]; unsigned __int16 *
0x140076ec5  lea     r8, aWriterXml; "*_Writer*.xml"
0x140076ecc  mov     r9, r13; this
0x140076ecf  mov     rdx, r14; unsigned __int16 *
0x140076ed2  call    ?BlbCopyMetadataFilesMatchingPattern@@YAJPEBG00PEAVCBlbImpersonationHelper@@E@Z; BlbCopyMetadataFilesMatchingPattern(ushort const *,ushort const *,ushort const *,CBlbImpersonationHelper *,uchar)
0x140076ed7  mov     ebx, eax
0x140076ed9  test    eax, eax
0x140076edb  js      short loc_140076F03
0x140076edd  mov     rcx, [rdi+110h]; unsigned __int16 *
0x140076ee4  lea     r8, aAdditionalfile_2; "*_AdditionalFiles*.xml"
0x140076eeb  mov     r9, r13; this
0x140076eee  mov     rdx, r14; unsigned __int16 *
0x140076ef1  call    ?BlbCopyMetadataFilesMatchingPattern@@YAJPEBG00PEAVCBlbImpersonationHelper@@E@Z; BlbCopyMetadataFilesMatchingPattern(ushort const *,ushort const *,ushort const *,CBlbImpersonationHelper *,uchar)
0x140076ef6  jmp     loc_140076D84
0x140076efb  mov     r15, [rbp+57h+var_A0]
0x140076eff  mov     rsi, [rbp+57h+arg_18]
0x140076f03  mov     rcx, r13; this
0x140076f06  call    ?Revert@CBlbImpersonationHelper@@QEAAXXZ; CBlbImpersonationHelper::Revert(void)
0x140076f0b  xor     r13d, r13d
0x140076f0e  test    r14, r14
0x140076f11  jz      short loc_140076F1C
0x140076f13  mov     rcx, r14; pv
0x140076f16  call    cs:__imp_CoTaskMemFree
0x140076f1c  mov     rcx, [rbp+57h+pv]; pv
0x140076f20  test    rcx, rcx
0x140076f23  jz      short loc_140076F2B
0x140076f25  call    cs:__imp_CoTaskMemFree
0x140076f2b  mov     rcx, [rbp+57h+var_90]; pv
0x140076f2f  test    rcx, rcx
0x140076f32  jz      short loc_140076F3A
0x140076f34  call    cs:__imp_CoTaskMemFree
0x140076f3a  mov     edi, r13d
0x140076f3d  cmp     [rbp+57h+arg_8], r13d
0x140076f41  jbe     short loc_140076F60
0x140076f43  mov     r14d, edi
0x140076f46  mov     rcx, [rsi+r14*8]; pv
0x140076f4a  test    rcx, rcx
0x140076f4d  jz      short loc_140076F59
0x140076f4f  call    cs:__imp_CoTaskMemFree
0x140076f55  mov     [rsi+r14*8], r13
0x140076f59  inc     edi
0x140076f5b  cmp     edi, [rbp+57h+arg_8]
0x140076f5e  jb      short loc_140076F43
0x140076f60  test    rsi, rsi
0x140076f63  jz      short loc_140076F6E
0x140076f65  mov     rcx, rsi; pv
0x140076f68  call    cs:__imp_CoTaskMemFree
0x140076f6e  mov     edi, r13d
0x140076f71  test    r12d, r12d
0x140076f74  jz      short loc_140076F92
0x140076f76  mov     esi, edi
0x140076f78  mov     rcx, [r15+rsi*8]; pv
0x140076f7c  test    rcx, rcx
0x140076f7f  jz      short loc_140076F8B
0x140076f81  call    cs:__imp_CoTaskMemFree
0x140076f87  mov     [r15+rsi*8], r13
0x140076f8b  inc     edi
0x140076f8d  cmp     edi, r12d
0x140076f90  jb      short loc_140076F76
0x140076f92  test    r15, r15
0x140076f95  jz      short loc_140076FA0
0x140076f97  mov     rcx, r15; pv
0x140076f9a  call    cs:__imp_CoTaskMemFree
0x140076fa0  mov     edx, dword ptr [rbp+57h+var_78]; unsigned int
0x140076fa3  lea     rcx, [rbp+57h+var_78+8]; struct _BLBSRV_VOLUME_INFO **
0x140076fa7  call    ?BlbFreeSrvVolumeInfo@@YAXAEAPEAU_BLBSRV_VOLUME_INFO@@K@Z; BlbFreeSrvVolumeInfo(_BLBSRV_VOLUME_INFO * &,ulong)
0x140076fac  mov     edx, dword ptr [rbp+57h+var_58+8]; unsigned int
0x140076faf  lea     rcx, [rbp+57h+var_48]; struct _BLBSRV_COMPONENT_INFO **
0x140076fb3  call    ?BlbFreeSrvComponentInfo@@YAXAEAPEAU_BLBSRV_COMPONENT_INFO@@K@Z; BlbFreeSrvComponentInfo(_BLBSRV_COMPONENT_INFO * &,ulong)
0x140076fb8  mov     rcx, [rbp+57h+var_68+8]; pv
0x140076fbc  test    rcx, rcx
0x140076fbf  jz      short loc_140076FCB
0x140076fc1  call    cs:__imp_CoTaskMemFree
0x140076fc7  mov     [rbp+57h+var_68+8], r13
0x140076fcb  mov     rcx, [rbp+57h+var_58]; pv
0x140076fcf  test    rcx, rcx
0x140076fd2  jz      short loc_140076FDE
0x140076fd4  call    cs:__imp_CoTaskMemFree
0x140076fda  mov     [rbp+57h+var_58], r13
0x140076fde  mov     rcx, cs:WPP_GLOBAL_Control
0x140076fe5  lea     rax, WPP_GLOBAL_Control
0x140076fec  cmp     rcx, rax
0x140076fef  jz      short loc_140077012
0x140076ff1  test    byte ptr [rcx+1Ch], 1
0x140076ff5  jz      short loc_140077012
0x140076ff7  cmp     byte ptr [rcx+19h], 4
0x140076ffb  jb      short loc_140077012
0x140076ffd  mov     rcx, [rcx+10h]
0x140077001  lea     r8, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids
0x140077008  mov     edx, 4Dh ; 'M'
0x14007700d  call    WPP_SF_
0x140077012  mov     eax, ebx
0x140077014  add     rsp, 0A8h
0x14007701b  pop     r15
0x14007701d  pop     r14
0x14007701f  pop     r13
0x140077021  pop     r12
0x140077023  pop     rdi
0x140077024  pop     rsi
0x140077025  pop     rbx
0x140077026  pop     rbp
0x140077027  retn
```
