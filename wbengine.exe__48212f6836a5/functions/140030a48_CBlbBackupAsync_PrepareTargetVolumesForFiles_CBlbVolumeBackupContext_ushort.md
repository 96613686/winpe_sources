# CBlbBackupAsync::PrepareTargetVolumesForFiles(CBlbVolumeBackupContext *,ushort * *)

- ea: `0x140030a48`
- end: `0x140030ea2`
- name: `?PrepareTargetVolumesForFiles@CBlbBackupAsync@@AEAAJPEAVCBlbVolumeBackupContext@@PEAPEAG@Z`
- size: `1114`
- prototype: `__int64 __fastcall(CBlbBackupAsync *__hidden this, struct CBlbVolumeBackupContext *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, service_task`

## callers

- `0x1400167f4`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x140013008`
- `0x140014200`
- `0x140014384`
- `0x140020bf0`
- `0x1400278a4`
- `0x14002d79c`
- `0x140030a48`
- `0x14008632c`
- `0x14008863c`
- `0x140088d0c`
- `0x14008ba2c`
- `0x14008bb44`
- `0x1400f007c`
- `0x1400f07dc`
- `0x1400ff774`
- `0x14012365c`
- `0x1401244c0`

## import_xrefs

- `KERNEL32!SetVolumeLabelW` at `0x140030de1`
- `KERNEL32!SetVolumeLabelW` at `0x140030de1`
- `KERNEL32!GetLastError` at `0x140030deb`
- `KERNEL32!GetLastError` at `0x140030deb`
- `ole32!CoTaskMemFree` at `0x140030cbf`
- `ole32!CoTaskMemFree` at `0x140030cce`
- `ole32!CoTaskMemFree` at `0x140030cdd`
- `ole32!CoTaskMemFree` at `0x140030ceb`
- `ole32!CoTaskMemFree` at `0x140030cf9`
- `ole32!CoTaskMemFree` at `0x140030d07`
- `ole32!CoTaskMemFree` at `0x140030d15`
- `ole32!CoTaskMemFree` at `0x140030cbf`
- `ole32!CoTaskMemFree` at `0x140030cce`
- `ole32!CoTaskMemFree` at `0x140030cdd`
- `ole32!CoTaskMemFree` at `0x140030ceb`
- `ole32!CoTaskMemFree` at `0x140030cf9`
- `ole32!CoTaskMemFree` at `0x140030d07`
- `ole32!CoTaskMemFree` at `0x140030d15`

## string_xrefs

- `0x140030aeb`: `base\stor\blb\engine\service\backup.cpp`
- `0x140030b08`: `base\stor\blb\engine\service\backup.cpp`
- `0x140030b25`: `base\stor\blb\engine\service\backup.cpp`
- `0x140030b50`: `base\stor\blb\engine\service\backup.cpp`
- `0x140030e4f`: `base\stor\blb\engine\service\backup.cpp`
- `0x140030b19`: `pwszRestoreAccessPath`
- `0x140030e43`: `wszMountedVolume`

## pseudocode

```c
__int64 __fastcall CBlbBackupAsync::PrepareTargetVolumesForFiles(
        CBlbBackupAsync *this,
        struct CBlbVolumeBackupContext *a2,
        unsigned __int16 **a3)
{
  bool v6; // zf
  unsigned __int16 *v7; // r12
  unsigned __int16 *v8; // rsi
  void *v9; // r14
  int OriginalAccessPath; // ebx
  unsigned __int16 *v11; // r8
  unsigned int v12; // edx
  int v13; // eax
  int v14; // eax
  unsigned __int16 *v15; // r15
  int VHD; // eax
  void *v17; // rdi
  int v19; // eax
  char LastError; // al
  int v21; // eax
  PCWSTR v22; // [rsp+40h] [rbp-49h] BYREF
  unsigned __int16 *v23; // [rsp+48h] [rbp-41h] BYREF
  unsigned __int16 *v24; // [rsp+50h] [rbp-39h] BYREF
  LPCWSTR lpRootPathName; // [rsp+58h] [rbp-31h] BYREF
  unsigned __int64 v26; // [rsp+60h] [rbp-29h] BYREF
  unsigned __int16 *v27; // [rsp+68h] [rbp-21h] BYREF
  CBlbFileBackupAsync *v28; // [rsp+70h] [rbp-19h]
  struct _GUID Buf1; // [rsp+80h] [rbp-9h] BYREF
  unsigned __int64 v30[10]; // [rsp+90h] [rbp+7h] BYREF
  LPVOID pv; // [rsp+F0h] [rbp+67h] BYREF
  unsigned __int16 *v32; // [rsp+F8h] [rbp+6Fh] BYREF
  unsigned __int16 **v33; // [rsp+100h] [rbp+77h]
  LPVOID v34; // [rsp+108h] [rbp+7Fh]

  v33 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 453, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  v6 = *((_DWORD *)this + 84) == 1;
  v34 = 0;
  v7 = 0;
  v24 = 0;
  v8 = 0;
  v22 = 0;
  v9 = 0;
  v23 = 0;
  lpRootPathName = 0;
  v27 = 0;
  pv = 0;
  v26 = 0;
  v32 = 0;
  if ( v6 )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x29ADu, "m_eMediaType != BLB_MT_SHINY");
  if ( !a2 )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x29AEu, "pVolumeContext");
  if ( !a3 )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x29AFu, "pwszRestoreAccessPath");
  *a3 = 0;
  v28 = (CBlbFileBackupAsync *)*((_QWORD *)a2 + 27);
  if ( !v28 )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x29B3u, "pFileAsync");
  OriginalAccessPath = CBlbVolumeBackupContext::GetOriginalAccessPath(a2, &v27);
  if ( OriginalAccessPath < 0 )
    goto LABEL_26;
  if ( !*((_QWORD *)a2 + 28) )
  {
    v11 = (unsigned __int16 *)*((_QWORD *)this + 59);
    v12 = *((_DWORD *)a2 + 21);
    Buf1 = *(struct _GUID *)((char *)a2 + 68);
    OriginalAccessPath = BlbGetVhdPath(&Buf1, v12, v11, (unsigned __int16 **)&v22);
    if ( OriginalAccessPath >= 0 )
    {
      if ( (*((_BYTE *)a2 + 84) & 0x10) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 454, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, v22);
        }
        VHD = CBlbBackupAsync::MountVHD(this, v22, (unsigned __int16 **)a2 + 28);
        v15 = v32;
        goto LABEL_54;
      }
      OriginalAccessPath = BlbutilAppendString(*((const unsigned __int16 **)this + 43), L"\\", (unsigned __int16 **)&pv);
      if ( OriginalAccessPath >= 0 )
      {
        OriginalAccessPath = CBlbImpersonationHelper::ImpersonateCaller((CBlbBackupAsync *)((char *)this + 40), 0);
        if ( OriginalAccessPath >= 0 )
        {
          OriginalAccessPath = BlbQueryFileSystemSpace((unsigned __int16 *)pv, (unsigned __int64 *)&Buf1.Data1, v30);
          if ( OriginalAccessPath >= 0 )
          {
            CBlbImpersonationHelper::Revert((CBlbBackupAsync *)((char *)this + 40));
            v13 = BlbutilQueryVolumeName((struct _GUID *)((char *)a2 + 68), *((_DWORD *)a2 + 21), &v23, 0);
            v7 = v23;
            OriginalAccessPath = v13;
            if ( v13 >= 0 )
            {
              OriginalAccessPath = BlbutilQueryVolumeSpace(v23, &v26);
              if ( OriginalAccessPath >= 0 )
              {
                v14 = BlbQueryVolumeFileSystem(v7, &v32);
                v15 = v32;
                OriginalAccessPath = v14;
                if ( v14 < 0 )
                  goto LABEL_24;
                VHD = CBlbBackupAsync::CreateVHD(
                        this,
                        (unsigned __int16 *)v22,
                        v26,
                        *((unsigned __int16 **)a2 + 12),
                        0,
                        *((_DWORD *)a2 + 16),
                        v32,
                        (unsigned __int16 **)a2 + 28);
LABEL_54:
                OriginalAccessPath = VHD;
                if ( VHD >= 0 )
                  goto LABEL_57;
LABEL_24:
                v9 = pv;
LABEL_27:
                v17 = v34;
                goto LABEL_28;
              }
            }
          }
        }
      }
    }
    v9 = pv;
LABEL_26:
    v15 = v32;
    goto LABEL_27;
  }
  v15 = v32;
LABEL_57:
  v19 = BlbutilSlashTerminatePath(*((unsigned __int16 **)a2 + 28), (LPVOID *)&lpRootPathName);
  v8 = (unsigned __int16 *)lpRootPathName;
  OriginalAccessPath = v19;
  if ( v19 < 0 )
    goto LABEL_24;
  if ( !SetVolumeLabelW(lpRootPathName, *((LPCWSTR *)a2 + 12)) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_SSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        455,
        (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
        *((_QWORD *)a2 + 12),
        (__int64)v8,
        LastError);
    }
  }
  if ( !v8 )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x2A2Cu, "wszMountedVolume");
  OriginalAccessPath = CBlbFileBackupAsync::SetRestoreAccessPath(v28, v8);
  if ( OriginalAccessPath < 0 )
    goto LABEL_24;
  v21 = BlbutilSlashTerminatePath(v8, (LPVOID *)&v24);
  v9 = pv;
  OriginalAccessPath = v21;
  if ( v21 < 0 )
  {
    v17 = v24;
  }
  else
  {
    v17 = 0;
    *v33 = v24;
  }
LABEL_28:
  CBlbImpersonationHelper::Revert((CBlbBackupAsync *)((char *)this + 40));
  if ( OriginalAccessPath < 0 )
    CBlbAsync::SetResult((CBlbBackupAsync *)((char *)this + 24), -2139619131, OriginalAccessPath, 0);
  if ( v9 )
    CoTaskMemFree(v9);
  if ( v27 )
    CoTaskMemFree(v27);
  if ( v22 )
    CoTaskMemFree((LPVOID)v22);
  if ( v8 )
    CoTaskMemFree(v8);
  if ( v7 )
    CoTaskMemFree(v7);
  if ( v17 )
    CoTaskMemFree(v17);
  if ( v15 )
    CoTaskMemFree(v15);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 456, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  return (unsigned int)OriginalAccessPath;
}

```

## disassembly

```asm
0x140030a48  mov     [rsp-8+arg_10], r8
0x140030a4d  push    rbp
0x140030a4e  push    rbx
0x140030a4f  push    rsi
0x140030a50  push    rdi
0x140030a51  push    r12
0x140030a53  push    r13
0x140030a55  push    r14
0x140030a57  push    r15
0x140030a59  lea     rbp, [rsp-1Fh]
0x140030a5e  sub     rsp, 0A8h
0x140030a65  mov     rbx, r8
0x140030a68  mov     rdi, rdx
0x140030a6b  mov     r13, rcx
0x140030a6e  mov     rcx, cs:WPP_GLOBAL_Control
0x140030a75  lea     rax, WPP_GLOBAL_Control
0x140030a7c  cmp     rcx, rax
0x140030a7f  jz      short loc_140030AA2
0x140030a81  test    byte ptr [rcx+1Ch], 1
0x140030a85  jz      short loc_140030AA2
0x140030a87  cmp     byte ptr [rcx+19h], 4
0x140030a8b  jb      short loc_140030AA2
0x140030a8d  mov     rcx, [rcx+10h]
0x140030a91  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140030a98  mov     edx, 1C5h
0x140030a9d  call    WPP_SF_
0x140030aa2  xor     r15d, r15d
0x140030aa5  cmp     dword ptr [r13+150h], 1
0x140030aad  mov     eax, r15d
0x140030ab0  mov     [rbp+57h+arg_18], rax
0x140030ab4  mov     r12d, r15d
0x140030ab7  mov     [rbp+57h+var_90], rax
0x140030abb  mov     esi, r15d
0x140030abe  mov     [rbp+57h+var_A0], r15
0x140030ac2  mov     r14d, r15d
0x140030ac5  mov     [rbp+57h+var_98], r15
0x140030ac9  mov     [rbp+57h+lpRootPathName], r15
0x140030acd  mov     [rbp+57h+var_78], r15
0x140030ad1  mov     [rbp+57h+pv], r15
0x140030ad5  mov     [rbp+57h+var_80], r15
0x140030ad9  mov     [rbp+57h+arg_8], r15
0x140030add  jnz     short loc_140030AF7
0x140030adf  lea     r8, aMEmediatypeBlb; "m_eMediaType != BLB_MT_SHINY"
0x140030ae6  mov     edx, 29ADh; unsigned int
0x140030aeb  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x140030af2  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140030af7  test    rdi, rdi
0x140030afa  jnz     short loc_140030B14
0x140030afc  lea     r8, aPvolumecontext; "pVolumeContext"
0x140030b03  mov     edx, 29AEh; unsigned int
0x140030b08  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x140030b0f  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140030b14  test    rbx, rbx
0x140030b17  jnz     short loc_140030B31
0x140030b19  lea     r8, aPwszrestoreacc; "pwszRestoreAccessPath"
0x140030b20  mov     edx, 29AFh; unsigned int
0x140030b25  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x140030b2c  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140030b31  mov     [rbx], r15
0x140030b34  mov     rax, [rdi+0D8h]
0x140030b3b  mov     [rbp+57h+var_70], rax
0x140030b3f  test    rax, rax
0x140030b42  jnz     short loc_140030B5C
0x140030b44  lea     r8, aPfileasync; "pFileAsync"
0x140030b4b  mov     edx, 29B3h; unsigned int
0x140030b50  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x140030b57  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140030b5c  lea     rdx, [rbp+57h+var_78]; unsigned __int16 **
0x140030b60  mov     rcx, rdi; this
0x140030b63  call    ?GetOriginalAccessPath@CBlbVolumeBackupContext@@QEAAJPEAPEAG@Z; CBlbVolumeBackupContext::GetOriginalAccessPath(ushort * *)
0x140030b68  mov     ebx, eax
0x140030b6a  test    eax, eax
0x140030b6c  js      loc_140030C8E
0x140030b72  lea     r14, [rdi+0E0h]
0x140030b79  cmp     [r14], r15
0x140030b7c  jnz     loc_140030DBC
0x140030b82  movups  xmm0, xmmword ptr [rdi+44h]
0x140030b86  mov     r8, [r13+1D8h]; unsigned __int16 *
0x140030b8d  lea     r9, [rbp+57h+var_A0]; unsigned __int16 **
0x140030b91  mov     edx, [rdi+54h]; unsigned int
0x140030b94  lea     rcx, [rbp+57h+Buf1]; Buf1
0x140030b98  movdqu  xmmword ptr [rbp+57h+Buf1.Data1], xmm0
0x140030b9d  call    ?BlbGetVhdPath@@YAJU_GUID@@KPEAGPEAPEAG@Z; BlbGetVhdPath(_GUID,ulong,ushort *,ushort * *)
0x140030ba2  mov     ebx, eax
0x140030ba4  test    eax, eax
0x140030ba6  js      loc_140030C8A
0x140030bac  test    byte ptr [rdi+54h], 10h
0x140030bb0  jnz     loc_140030D65
0x140030bb6  mov     rcx, [r13+158h]; unsigned __int16 *
0x140030bbd  lea     r8, [rbp+57h+pv]; unsigned __int16 **
0x140030bc1  lea     rdx, asc_14013C090; "\\"
0x140030bc8  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x140030bcd  mov     ebx, eax
0x140030bcf  test    eax, eax
0x140030bd1  js      loc_140030C8A
0x140030bd7  xor     edx, edx; unsigned __int8
0x140030bd9  lea     rcx, [r13+28h]; this
0x140030bdd  call    ?ImpersonateCaller@CBlbImpersonationHelper@@QEAAJE@Z; CBlbImpersonationHelper::ImpersonateCaller(uchar)
0x140030be2  mov     ebx, eax
0x140030be4  test    eax, eax
0x140030be6  js      loc_140030C8A
0x140030bec  mov     rcx, [rbp+57h+pv]; unsigned __int16 *
0x140030bf0  lea     r8, [rbp+57h+var_50]; unsigned __int64 *
0x140030bf4  lea     rdx, [rbp+57h+Buf1]; unsigned __int64 *
0x140030bf8  call    ?BlbQueryFileSystemSpace@@YAJPEAGPEA_K1@Z; BlbQueryFileSystemSpace(ushort *,unsigned __int64 *,unsigned __int64 *)
0x140030bfd  mov     ebx, eax
0x140030bff  test    eax, eax
0x140030c01  js      loc_140030C8A
0x140030c07  lea     rcx, [r13+28h]; this
0x140030c0b  call    ?Revert@CBlbImpersonationHelper@@QEAAXXZ; CBlbImpersonationHelper::Revert(void)
0x140030c10  mov     edx, [rdi+54h]; unsigned int
0x140030c13  lea     r8, [rbp+57h+var_98]; unsigned __int16 **
0x140030c17  xor     r9d, r9d; unsigned __int8
0x140030c1a  lea     rcx, [rdi+44h]; struct _GUID *
0x140030c1e  call    ?BlbutilQueryVolumeName@@YAJPEAU_GUID@@KPEAPEAGE@Z; BlbutilQueryVolumeName(_GUID *,ulong,ushort * *,uchar)
0x140030c23  mov     r12, [rbp+57h+var_98]
0x140030c27  mov     ebx, eax
0x140030c29  test    eax, eax
0x140030c2b  js      short loc_140030C8A
0x140030c2d  lea     rdx, [rbp+57h+var_80]; unsigned __int64 *
0x140030c31  mov     rcx, r12; unsigned __int16 *
0x140030c34  call    ?BlbutilQueryVolumeSpace@@YAJPEAGPEA_K@Z; BlbutilQueryVolumeSpace(ushort *,unsigned __int64 *)
0x140030c39  mov     ebx, eax
0x140030c3b  test    eax, eax
0x140030c3d  js      short loc_140030C8A
0x140030c3f  lea     rdx, [rbp+57h+arg_8]; unsigned __int16 **
0x140030c43  mov     rcx, r12; unsigned __int16 *
0x140030c46  call    ?BlbQueryVolumeFileSystem@@YAJPEAGPEAPEAG@Z; BlbQueryVolumeFileSystem(ushort *,ushort * *)
0x140030c4b  mov     r15, [rbp+57h+arg_8]
0x140030c4f  mov     ebx, eax
0x140030c51  test    eax, eax
0x140030c53  js      short loc_140030C84
0x140030c55  mov     eax, [rdi+40h]
0x140030c58  mov     rcx, r13; this
0x140030c5b  mov     r9, [rdi+60h]; unsigned __int16 *
0x140030c5f  mov     r8, [rbp+57h+var_80]; unsigned __int64
0x140030c63  mov     rdx, [rbp+57h+var_A0]; unsigned __int16 *
0x140030c67  mov     [rsp+0E0h+var_A8], r14; unsigned __int16 **
0x140030c6c  mov     [rsp+0E0h+var_B0], r15; unsigned __int16 *
0x140030c71  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x140030c75  mov     [rsp+0E0h+var_C0], sil; unsigned __int8
0x140030c7a  call    ?CreateVHD@CBlbBackupAsync@@QEAAJPEAG_K0EK0PEAPEAG@Z; CBlbBackupAsync::CreateVHD(ushort *,unsigned __int64,ushort *,uchar,ulong,ushort *,ushort * *)
0x140030c7f  jmp     loc_140030DB0
0x140030c84  mov     r14, [rbp+57h+pv]
0x140030c88  jmp     short loc_140030C92
0x140030c8a  mov     r14, [rbp+57h+pv]
0x140030c8e  mov     r15, [rbp+57h+arg_8]
0x140030c92  mov     rdi, [rbp+57h+arg_18]
0x140030c96  lea     rcx, [r13+28h]; this
0x140030c9a  call    ?Revert@CBlbImpersonationHelper@@QEAAXXZ; CBlbImpersonationHelper::Revert(void)
0x140030c9f  test    ebx, ebx
0x140030ca1  jns     short loc_140030CB7
0x140030ca3  lea     rcx, [r13+18h]; this
0x140030ca7  xor     r9d, r9d; unsigned __int8
0x140030caa  mov     r8d, ebx; int
0x140030cad  mov     edx, 807800C5h; int
0x140030cb2  call    ?SetResult@CBlbAsync@@QEAAXJJE@Z; CBlbAsync::SetResult(long,long,uchar)
0x140030cb7  test    r14, r14
0x140030cba  jz      short loc_140030CC5
0x140030cbc  mov     rcx, r14; pv
0x140030cbf  call    cs:__imp_CoTaskMemFree
0x140030cc5  mov     rcx, [rbp+57h+var_78]; pv
0x140030cc9  test    rcx, rcx
0x140030ccc  jz      short loc_140030CD4
0x140030cce  call    cs:__imp_CoTaskMemFree
0x140030cd4  mov     rcx, [rbp+57h+var_A0]; pv
0x140030cd8  test    rcx, rcx
0x140030cdb  jz      short loc_140030CE3
0x140030cdd  call    cs:__imp_CoTaskMemFree
0x140030ce3  test    rsi, rsi
0x140030ce6  jz      short loc_140030CF1
0x140030ce8  mov     rcx, rsi; pv
0x140030ceb  call    cs:__imp_CoTaskMemFree
0x140030cf1  test    r12, r12
0x140030cf4  jz      short loc_140030CFF
0x140030cf6  mov     rcx, r12; pv
0x140030cf9  call    cs:__imp_CoTaskMemFree
0x140030cff  test    rdi, rdi
0x140030d02  jz      short loc_140030D0D
0x140030d04  mov     rcx, rdi; pv
0x140030d07  call    cs:__imp_CoTaskMemFree
0x140030d0d  test    r15, r15
0x140030d10  jz      short loc_140030D1B
0x140030d12  mov     rcx, r15; pv
0x140030d15  call    cs:__imp_CoTaskMemFree
0x140030d1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140030d22  lea     rax, WPP_GLOBAL_Control
0x140030d29  cmp     rcx, rax
0x140030d2c  jz      short loc_140030D4F
0x140030d2e  test    byte ptr [rcx+1Ch], 1
0x140030d32  jz      short loc_140030D4F
0x140030d34  cmp     byte ptr [rcx+19h], 4
0x140030d38  jb      short loc_140030D4F
0x140030d3a  mov     rcx, [rcx+10h]
0x140030d3e  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140030d45  mov     edx, 1C8h
0x140030d4a  call    WPP_SF_
0x140030d4f  mov     eax, ebx
0x140030d51  add     rsp, 0A8h
0x140030d58  pop     r15
0x140030d5a  pop     r14
0x140030d5c  pop     r13
0x140030d5e  pop     r12
0x140030d60  pop     rdi
0x140030d61  pop     rsi
0x140030d62  pop     rbx
0x140030d63  pop     rbp
0x140030d64  retn
0x140030d65  mov     rcx, cs:WPP_GLOBAL_Control
0x140030d6c  lea     rax, WPP_GLOBAL_Control
0x140030d73  cmp     rcx, rax
0x140030d76  jz      short loc_140030D9D
0x140030d78  test    byte ptr [rcx+1Ch], 1
0x140030d7c  jz      short loc_140030D9D
0x140030d7e  cmp     byte ptr [rcx+19h], 4
0x140030d82  jb      short loc_140030D9D
0x140030d84  mov     r9, [rbp+57h+var_A0]
0x140030d88  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140030d8f  mov     rcx, [rcx+10h]
0x140030d93  mov     edx, 1C6h
0x140030d98  call    WPP_SF_S
0x140030d9d  mov     rdx, [rbp+57h+var_A0]; PCWSTR
0x140030da1  mov     r8, r14; unsigned __int16 **
0x140030da4  mov     rcx, r13; this
0x140030da7  call    ?MountVHD@CBlbBackupAsync@@QEAAJPEBGPEAPEAG@Z; CBlbBackupAsync::MountVHD(ushort const *,ushort * *)
0x140030dac  mov     r15, [rbp+57h+arg_8]
0x140030db0  mov     ebx, eax
0x140030db2  test    eax, eax
0x140030db4  js      loc_140030C84
0x140030dba  jmp     short loc_140030DC0
0x140030dbc  mov     r15, [rbp+57h+arg_8]
0x140030dc0  mov     rcx, [r14]; unsigned __int16 *
0x140030dc3  lea     rdx, [rbp+57h+lpRootPathName]; unsigned __int16 **
0x140030dc7  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x140030dcc  mov     rsi, [rbp+57h+lpRootPathName]
0x140030dd0  mov     ebx, eax
0x140030dd2  test    eax, eax
0x140030dd4  js      loc_140030C84
0x140030dda  mov     rdx, [rdi+60h]; lpVolumeName
0x140030dde  mov     rcx, rsi; lpRootPathName
0x140030de1  call    cs:__imp_SetVolumeLabelW
0x140030de7  test    eax, eax
0x140030de9  jnz     short loc_140030E3E
0x140030deb  call    cs:__imp_GetLastError
0x140030df1  test    eax, eax
0x140030df3  jle     short loc_140030DFD
0x140030df5  movzx   eax, ax
0x140030df8  or      eax, 80070000h
0x140030dfd  mov     rcx, cs:WPP_GLOBAL_Control
0x140030e04  lea     rdx, WPP_GLOBAL_Control
0x140030e0b  cmp     rcx, rdx
0x140030e0e  jz      short loc_140030E3E
0x140030e10  test    byte ptr [rcx+1Ch], 1
0x140030e14  jz      short loc_140030E3E
0x140030e16  cmp     byte ptr [rcx+19h], 3
0x140030e1a  jb      short loc_140030E3E
0x140030e1c  mov     r9, [rdi+60h]
0x140030e20  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140030e27  mov     rcx, [rcx+10h]
0x140030e2b  mov     edx, 1C7h
0x140030e30  mov     [rsp+0E0h+var_B8], eax
0x140030e34  mov     qword ptr [rsp+0E0h+var_C0], rsi
0x140030e39  call    WPP_SF_SSD
0x140030e3e  test    rsi, rsi
0x140030e41  jnz     short loc_140030E5B
0x140030e43  lea     r8, aWszmountedvolu_0; "wszMountedVolume"
0x140030e4a  mov     edx, 2A2Ch; unsigned int
0x140030e4f  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x140030e56  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140030e5b  mov     rcx, [rbp+57h+var_70]; this
0x140030e5f  mov     rdx, rsi; unsigned __int16 *
0x140030e62  call    ?SetRestoreAccessPath@CBlbFileBackupAsync@@QEAAJPEAG@Z; CBlbFileBackupAsync::SetRestoreAccessPath(ushort *)
0x140030e67  mov     ebx, eax
0x140030e69  test    eax, eax
0x140030e6b  js      loc_140030C84
0x140030e71  lea     rdx, [rbp+57h+var_90]; unsigned __int16 **
0x140030e75  mov     rcx, rsi; unsigned __int16 *
0x140030e78  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x140030e7d  mov     r14, [rbp+57h+pv]
0x140030e81  mov     ebx, eax
0x140030e83  test    eax, eax
0x140030e85  js      short loc_140030E99
0x140030e87  mov     rcx, [rbp+57h+arg_10]
0x140030e8b  xor     edi, edi
0x140030e8d  mov     rax, [rbp+57h+var_90]
0x140030e91  mov     [rcx], rax
0x140030e94  jmp     loc_140030C96
0x140030e99  mov     rdi, [rbp+57h+var_90]
0x140030e9d  jmp     loc_140030C96
```
