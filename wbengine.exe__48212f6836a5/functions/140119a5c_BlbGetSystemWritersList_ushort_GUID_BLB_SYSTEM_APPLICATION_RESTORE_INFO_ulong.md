# BlbGetSystemWritersList(ushort *,_GUID,_BLB_SYSTEM_APPLICATION_RESTORE_INFO * *,ulong *)

- ea: `0x140119a5c`
- end: `0x140119f02`
- name: `?BlbGetSystemWritersList@@YAJPEAGU_GUID@@PEAPEAU_BLB_SYSTEM_APPLICATION_RESTORE_INFO@@PEAK@Z`
- size: `1190`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _GUID *__struct_ptr, struct _BLB_SYSTEM_APPLICATION_RESTORE_INFO **, unsigned int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140076588`

## callees

- `0x140006a64`
- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000bfd8`
- `0x14000c248`
- `0x140014260`
- `0x1400889f0`
- `0x1400f2a28`
- `0x1400f2d74`
- `0x1400f5790`
- `0x140102560`
- `0x140119a5c`
- `0x14011a490`
- `0x14012458c`

## import_xrefs

- `KERNEL32!FindClose` at `0x140119eaf`
- `KERNEL32!FindClose` at `0x140119eaf`
- `ole32!CoTaskMemAlloc` at `0x140119d0a`
- `ole32!CoTaskMemAlloc` at `0x140119d0a`
- `ole32!CoTaskMemFree` at `0x140119c5a`
- `ole32!CoTaskMemFree` at `0x140119c68`
- `ole32!CoTaskMemFree` at `0x140119e84`
- `ole32!CoTaskMemFree` at `0x140119e99`
- `ole32!CoTaskMemFree` at `0x140119c5a`
- `ole32!CoTaskMemFree` at `0x140119c68`
- `ole32!CoTaskMemFree` at `0x140119e84`
- `ole32!CoTaskMemFree` at `0x140119e99`

## string_xrefs

- `0x140119af7`: `wszBackupSetDirectory`
- `0x140119b03`: `base\stor\blb\engine\blbengutils\blbwriterutils.cpp`
- `0x140119b20`: `base\stor\blb\engine\blbengutils\blbwriterutils.cpp`
- `0x140119b3d`: `base\stor\blb\engine\blbengutils\blbwriterutils.cpp`
- `0x140119b14`: `pcWriter`
- `0x140119b31`: `ppWriterInfoList`

## pseudocode

```c
__int64 __fastcall BlbGetSystemWritersList(
        unsigned __int16 *a1,
        struct _GUID *a2,
        struct _BLB_SYSTEM_APPLICATION_RESTORE_INFO **a3,
        unsigned int *a4)
{
  unsigned int *v4; // r15
  void *v7; // rsi
  __int64 v8; // r13
  unsigned __int64 v9; // rdi
  struct _BLB_SYSTEM_APPLICATION_RESTORE_INFO *v10; // r12
  int appended; // ebx
  int FirstFile; // eax
  PVOID *v13; // rcx
  struct _BLB_SYSTEM_APPLICATION_RESTORE_INFO *v14; // r14
  struct _BLB_SYSTEM_APPLICATION_RESTORE_INFO *v15; // rax
  unsigned int i; // eax
  __int64 v17; // r15
  const unsigned __int16 ***v18; // rax
  struct _BLB_SYSTEM_APPLICATION_RESTORE_INFO **v19; // rax
  unsigned int v20; // r14d
  struct _BLB_SYSTEM_APPLICATION_RESTORE_INFO **v21; // rax
  unsigned __int8 v23[8]; // [rsp+30h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-51h] BYREF
  unsigned __int16 *v25; // [rsp+40h] [rbp-49h] BYREF
  struct _BLB_SYSTEM_APPLICATION_RESTORE_INFO *v26; // [rsp+48h] [rbp-41h] BYREF
  HANDLE hFindFile; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int16 *v28; // [rsp+58h] [rbp-31h] BYREF
  __int64 v29; // [rsp+60h] [rbp-29h] BYREF
  unsigned int v30[2]; // [rsp+68h] [rbp-21h]
  __int64 v31; // [rsp+70h] [rbp-19h]
  int v32; // [rsp+78h] [rbp-11h]
  union _LARGE_INTEGER v33; // [rsp+80h] [rbp-9h] BYREF
  UUID *Uuid; // [rsp+88h] [rbp-1h]
  unsigned int *v35; // [rsp+90h] [rbp+7h]
  struct _BLB_SYSTEM_APPLICATION_RESTORE_INFO **v36; // [rsp+98h] [rbp+Fh]

  v4 = a4;
  v35 = a4;
  v36 = a3;
  Uuid = a2;
  v25 = 0;
  v7 = 0;
  pv = 0;
  v28 = 0;
  v8 = -1;
  hFindFile = (HANDLE)-1LL;
  v33.QuadPart = 0;
  v29 = 0;
  v9 = 0;
  *(_QWORD *)v30 = 0;
  v31 = 0;
  v32 = 0;
  v10 = 0;
  v26 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_0f9b83d7e0133652f3df4ebbb4d53694_Traceguids);
  }
  if ( !a1 )
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbwriterutils.cpp", 0x8Du, "wszBackupSetDirectory");
  if ( !v4 )
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbwriterutils.cpp", 0x8Eu, "pcWriter");
  if ( !a3 )
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbwriterutils.cpp", 0x8Fu, "ppWriterInfoList");
  *v4 = 0;
  *a3 = 0;
  appended = BlbAppendWriterMetadataFile(a1, Uuid, 0, 0, &v25);
  if ( appended < 0 )
  {
LABEL_47:
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    FirstFile = BlbFindFirstFile(v25, &pv, &hFindFile, 0);
    appended = FirstFile;
    if ( FirstFile >= 0 )
    {
      v8 = (__int64)hFindFile;
      while ( 1 )
      {
        v7 = pv;
        if ( !pv )
          break;
        v33.QuadPart = 0;
        appended = BlbReadFileFromTarget((unsigned __int16 *)pv, &v28, &v33);
        if ( appended < 0 )
        {
          v13 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              14,
              (unsigned int)WPP_0f9b83d7e0133652f3df4ebbb4d53694_Traceguids,
              (_DWORD)v7,
              appended);
            goto LABEL_27;
          }
          v9 = *(_QWORD *)v30;
          goto LABEL_48;
        }
        v23[0] = 0;
        appended = BlbIsSystemWriter(v28, v23, &v26);
        if ( appended < 0 )
        {
          v9 = *(_QWORD *)v30;
          v10 = v26;
          goto LABEL_47;
        }
        if ( v23[0] )
        {
          ATL::CAtlArray<ATL::CComObject<CBlbComponentRestoreContext> *,ATL::CElementTraits<ATL::CComObject<CBlbComponentRestoreContext> *>>::Add(
            &v29,
            &v26);
          v10 = 0;
          v26 = 0;
        }
        else
        {
          v10 = v26;
        }
        CoTaskMemFree(v7);
        pv = 0;
        CoTaskMemFree(v28);
        v28 = 0;
        appended = BlbFindNextFile(v25, (HANDLE)v8, &pv, 0);
        if ( appended < 0 )
        {
          v7 = pv;
LABEL_27:
          v9 = *(_QWORD *)v30;
          goto LABEL_47;
        }
      }
      v14 = 0;
      v9 = *(_QWORD *)v30;
      if ( *(_QWORD *)v30 )
      {
        v15 = (struct _BLB_SYSTEM_APPLICATION_RESTORE_INFO *)CoTaskMemAlloc(24LL * *(_QWORD *)v30);
        v14 = v15;
        if ( !v15 )
        {
          appended = -2147024882;
          goto LABEL_47;
        }
        memset_0(v15, 0, 24 * v9);
        for ( i = 0; ; i = (_DWORD)pv + 1 )
        {
          LODWORD(pv) = i;
          v17 = i;
          if ( i >= v9 )
            break;
          *(_OWORD *)((char *)v14 + 24 * i + 8) = *(_OWORD *)(*(_QWORD *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                                                                           &v29,
                                                                           i)
                                                            + 8LL);
          v18 = (const unsigned __int16 ***)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                                              &v29,
                                              (unsigned int)v17);
          appended = BlbutilDuplicateString(**v18, (unsigned __int16 **)v14 + 3 * v17, 0);
          if ( appended < 0 )
          {
            BlbFreeAppInfo(v14, v9);
            goto LABEL_47;
          }
          v19 = (struct _BLB_SYSTEM_APPLICATION_RESTORE_INFO **)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                                                                  &v29,
                                                                  (unsigned int)v17);
          BlbFreeAppInfo(*v19, 1u);
          *(_QWORD *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                       &v29,
                       (unsigned int)v17) = 0;
        }
        v4 = v35;
      }
      *v4 = v9;
      *v36 = v14;
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_0f9b83d7e0133652f3df4ebbb4d53694_Traceguids);
        goto LABEL_47;
      }
    }
    else
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)WPP_0f9b83d7e0133652f3df4ebbb4d53694_Traceguids,
          (_DWORD)v25,
          FirstFile);
        v7 = pv;
        v8 = (__int64)hFindFile;
        v13 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_55;
      }
      v7 = pv;
      v8 = (__int64)hFindFile;
    }
  }
LABEL_48:
  v20 = 0;
  if ( v9 )
  {
    do
    {
      if ( *(_QWORD *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                        &v29,
                        v20) )
      {
        v21 = (struct _BLB_SYSTEM_APPLICATION_RESTORE_INFO **)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                                                                &v29,
                                                                v20);
        BlbFreeAppInfo(*v21, 1u);
      }
      ++v20;
    }
    while ( v20 < v9 );
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 )
  {
    BlbFreeAppInfo(v10, 1u);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_55:
  if ( v25 )
  {
    CoTaskMemFree(v25);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 )
  {
    CoTaskMemFree(v7);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 != -1 )
  {
    FindClose((HANDLE)v8);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 && *((_BYTE *)v13 + 25) >= 4u )
    WPP_SF_(v13[2], 16, WPP_0f9b83d7e0133652f3df4ebbb4d53694_Traceguids);
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(&v29);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140119a5c  push    rbp
0x140119a5e  push    rbx
0x140119a5f  push    rsi
0x140119a60  push    rdi
0x140119a61  push    r12
0x140119a63  push    r13
0x140119a65  push    r14
0x140119a67  push    r15
0x140119a69  lea     rbp, [rsp-1Fh]
0x140119a6e  sub     rsp, 0A8h
0x140119a75  mov     r15, r9
0x140119a78  mov     [rbp+57h+var_50], r9
0x140119a7c  mov     r14, r8
0x140119a7f  mov     [rbp+57h+var_48], r8
0x140119a83  mov     [rbp+57h+Uuid], rdx
0x140119a87  mov     rbx, rcx
0x140119a8a  mov     [rbp+57h+var_A0], 0
0x140119a92  xor     esi, esi
0x140119a94  mov     [rbp+57h+pv], rsi
0x140119a98  mov     [rbp+57h+var_88], rsi
0x140119a9c  or      r13, 0FFFFFFFFFFFFFFFFh
0x140119aa0  mov     [rbp+57h+hFindFile], r13
0x140119aa4  mov     qword ptr [rbp+57h+var_60], rsi
0x140119aa8  mov     [rbp+57h+var_80], rsi
0x140119aac  xor     edi, edi
0x140119aae  mov     qword ptr [rbp+57h+var_78], rdi
0x140119ab2  mov     [rbp+57h+var_70], rsi
0x140119ab6  mov     [rbp+57h+var_68], esi
0x140119ab9  xor     r12d, r12d
0x140119abc  mov     [rbp+57h+var_98], r12
0x140119ac0  lea     rax, WPP_GLOBAL_Control
0x140119ac7  mov     rcx, cs:WPP_GLOBAL_Control
0x140119ace  cmp     rcx, rax
0x140119ad1  jz      short loc_140119AF2
0x140119ad3  test    byte ptr [rcx+1Ch], 1
0x140119ad7  jz      short loc_140119AF2
0x140119ad9  cmp     byte ptr [rcx+19h], 4
0x140119add  jb      short loc_140119AF2
0x140119adf  lea     edx, [rsi+0Ch]
0x140119ae2  lea     r8, WPP_0f9b83d7e0133652f3df4ebbb4d53694_Traceguids
0x140119ae9  mov     rcx, [rcx+10h]
0x140119aed  call    WPP_SF_
0x140119af2  test    rbx, rbx
0x140119af5  jnz     short loc_140119B0F
0x140119af7  lea     r8, aWszbackupsetdi; "wszBackupSetDirectory"
0x140119afe  mov     edx, 8Dh; unsigned int
0x140119b03  lea     rcx, aBaseStorBlbEng_4; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x140119b0a  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140119b0f  test    r15, r15
0x140119b12  jnz     short loc_140119B2C
0x140119b14  lea     r8, aPcwriter; "pcWriter"
0x140119b1b  mov     edx, 8Eh; unsigned int
0x140119b20  lea     rcx, aBaseStorBlbEng_4; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x140119b27  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140119b2c  test    r14, r14
0x140119b2f  jnz     short loc_140119B49
0x140119b31  lea     r8, aPpwriterinfoli; "ppWriterInfoList"
0x140119b38  mov     edx, 8Fh; unsigned int
0x140119b3d  lea     rcx, aBaseStorBlbEng_4; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x140119b44  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140119b49  mov     [r15], r12d
0x140119b4c  mov     [r14], r12
0x140119b4f  lea     rax, [rbp+57h+var_A0]
0x140119b53  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 **
0x140119b58  xor     r9d, r9d; unsigned __int8
0x140119b5b  xor     r8d, r8d; UUID *
0x140119b5e  mov     rdx, [rbp+57h+Uuid]; Uuid
0x140119b62  mov     rcx, rbx; unsigned __int16 *
0x140119b65  call    ?BlbAppendWriterMetadataFile@@YAJPEAGPEAU_GUID@@1EPEAPEAG@Z; BlbAppendWriterMetadataFile(ushort *,_GUID *,_GUID *,uchar,ushort * *)
0x140119b6a  mov     ebx, eax
0x140119b6c  test    eax, eax
0x140119b6e  js      loc_140119E0A
0x140119b74  xor     r9d, r9d; struct _WIN32_FIND_DATAW **
0x140119b77  lea     r8, [rbp+57h+hFindFile]; void **
0x140119b7b  lea     rdx, [rbp+57h+pv]; unsigned __int16 **
0x140119b7f  mov     rcx, [rbp+57h+var_A0]; unsigned __int16 *
0x140119b83  call    ?BlbFindFirstFile@@YAJPEAGPEAPEAGPEAPEAXPEAPEAU_WIN32_FIND_DATAW@@@Z; BlbFindFirstFile(ushort *,ushort * *,void * *,_WIN32_FIND_DATAW * *)
0x140119b88  mov     ebx, eax
0x140119b8a  test    eax, eax
0x140119b8c  jns     short loc_140119BEB
0x140119b8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140119b95  lea     r14, WPP_GLOBAL_Control
0x140119b9c  cmp     rcx, r14
0x140119b9f  jz      short loc_140119BDE
0x140119ba1  test    byte ptr [rcx+1Ch], 1
0x140119ba5  jz      short loc_140119BDE
0x140119ba7  cmp     byte ptr [rcx+19h], 2
0x140119bab  jb      short loc_140119BDE
0x140119bad  mov     edx, 0Dh
0x140119bb2  mov     dword ptr [rsp+0E0h+var_C0], eax
0x140119bb6  mov     r9, [rbp+57h+var_A0]
0x140119bba  lea     r8, WPP_0f9b83d7e0133652f3df4ebbb4d53694_Traceguids
0x140119bc1  mov     rcx, [rcx+10h]
0x140119bc5  call    WPP_SF_Sd
0x140119bca  mov     rsi, [rbp+57h+pv]
0x140119bce  mov     r13, [rbp+57h+hFindFile]
0x140119bd2  mov     rcx, cs:WPP_GLOBAL_Control
0x140119bd9  jmp     loc_140119E79
0x140119bde  mov     rsi, [rbp+57h+pv]
0x140119be2  mov     r13, [rbp+57h+hFindFile]
0x140119be6  jmp     loc_140119E11
0x140119beb  mov     r13, [rbp+57h+hFindFile]
0x140119bef  xor     edi, edi
0x140119bf1  mov     rsi, [rbp+57h+pv]
0x140119bf5  test    rsi, rsi
0x140119bf8  jz      loc_140119CEF
0x140119bfe  mov     qword ptr [rbp+57h+var_60], rdi
0x140119c02  lea     r8, [rbp+57h+var_60]; union _LARGE_INTEGER *
0x140119c06  lea     rdx, [rbp+57h+var_88]; unsigned __int16 **
0x140119c0a  mov     rcx, rsi; unsigned __int16 *
0x140119c0d  call    ?BlbReadFileFromTarget@@YAJPEAGPEAPEAGPEAT_LARGE_INTEGER@@@Z; BlbReadFileFromTarget(ushort *,ushort * *,_LARGE_INTEGER *)
0x140119c12  mov     ebx, eax
0x140119c14  test    eax, eax
0x140119c16  js      loc_140119CA9
0x140119c1c  mov     [rbp+57h+var_B0], dil
0x140119c20  lea     r8, [rbp+57h+var_98]; struct _BLB_SYSTEM_APPLICATION_RESTORE_INFO **
0x140119c24  lea     rdx, [rbp+57h+var_B0]; unsigned __int8 *
0x140119c28  mov     rcx, [rbp+57h+var_88]; unsigned __int16 *
0x140119c2c  call    ?BlbIsSystemWriter@@YAJPEAGPEAEPEAPEAU_BLB_SYSTEM_APPLICATION_RESTORE_INFO@@@Z; BlbIsSystemWriter(ushort *,uchar *,_BLB_SYSTEM_APPLICATION_RESTORE_INFO * *)
0x140119c31  mov     ebx, eax
0x140119c33  test    eax, eax
0x140119c35  js      short loc_140119C9C
0x140119c37  cmp     [rbp+57h+var_B0], dil
0x140119c3b  jz      short loc_140119C53
0x140119c3d  lea     rdx, [rbp+57h+var_98]
0x140119c41  lea     rcx, [rbp+57h+var_80]
0x140119c45  call    ?Add@?$CAtlArray@PEAV?$CComObject@VCBlbComponentRestoreContext@@@ATL@@V?$CElementTraits@PEAV?$CComObject@VCBlbComponentRestoreContext@@@ATL@@@2@@ATL@@QEAA_KAEBQEAV?$CComObject@VCBlbComponentRestoreContext@@@2@@Z; ATL::CAtlArray<ATL::CComObject<CBlbComponentRestoreContext> *,ATL::CElementTraits<ATL::CComObject<CBlbComponentRestoreContext> *>>::Add(ATL::CComObject<CBlbComponentRestoreContext> * const &)
0x140119c4a  mov     r12, rdi
0x140119c4d  mov     [rbp+57h+var_98], rdi
0x140119c51  jmp     short loc_140119C57
0x140119c53  mov     r12, [rbp+57h+var_98]
0x140119c57  mov     rcx, rsi; pv
0x140119c5a  call    cs:__imp_CoTaskMemFree
0x140119c60  mov     [rbp+57h+pv], rdi
0x140119c64  mov     rcx, [rbp+57h+var_88]; pv
0x140119c68  call    cs:__imp_CoTaskMemFree
0x140119c6e  mov     [rbp+57h+var_88], rdi
0x140119c72  xor     r9d, r9d; struct _WIN32_FIND_DATAW **
0x140119c75  lea     r8, [rbp+57h+pv]; unsigned __int16 **
0x140119c79  mov     rdx, r13; hFindFile
0x140119c7c  mov     rcx, [rbp+57h+var_A0]; unsigned __int16 *
0x140119c80  call    ?BlbFindNextFile@@YAJPEAGPEAXPEAPEAGPEAPEAU_WIN32_FIND_DATAW@@@Z; BlbFindNextFile(ushort *,void *,ushort * *,_WIN32_FIND_DATAW * *)
0x140119c85  mov     ebx, eax
0x140119c87  test    eax, eax
0x140119c89  jns     loc_140119BF1
0x140119c8f  mov     rsi, [rbp+57h+pv]
0x140119c93  mov     rdi, qword ptr [rbp+57h+var_78]
0x140119c97  jmp     loc_140119E0A
0x140119c9c  mov     rdi, qword ptr [rbp+57h+var_78]
0x140119ca0  mov     r12, [rbp+57h+var_98]
0x140119ca4  jmp     loc_140119E0A
0x140119ca9  mov     rcx, cs:WPP_GLOBAL_Control
0x140119cb0  lea     rax, WPP_GLOBAL_Control
0x140119cb7  cmp     rcx, rax
0x140119cba  jz      short loc_140119CE6
0x140119cbc  test    byte ptr [rcx+1Ch], 1
0x140119cc0  jz      short loc_140119CE6
0x140119cc2  cmp     byte ptr [rcx+19h], 2
0x140119cc6  jb      short loc_140119CE6
0x140119cc8  mov     edx, 0Eh
0x140119ccd  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x140119cd1  mov     r9, rsi
0x140119cd4  lea     r8, WPP_0f9b83d7e0133652f3df4ebbb4d53694_Traceguids
0x140119cdb  mov     rcx, [rcx+10h]
0x140119cdf  call    WPP_SF_Sd
0x140119ce4  jmp     short loc_140119C93
0x140119ce6  mov     rdi, qword ptr [rbp+57h+var_78]
0x140119cea  jmp     loc_140119E11
0x140119cef  mov     r14, rdi
0x140119cf2  mov     rdi, qword ptr [rbp+57h+var_78]
0x140119cf6  test    rdi, rdi
0x140119cf9  jz      loc_140119DC9
0x140119cff  lea     r15, [rdi+rdi*2]
0x140119d03  shl     r15, 3
0x140119d07  mov     rcx, r15; cb
0x140119d0a  call    cs:__imp_CoTaskMemAlloc
0x140119d10  mov     r14, rax
0x140119d13  test    rax, rax
0x140119d16  jnz     short loc_140119D22
0x140119d18  mov     ebx, 8007000Eh
0x140119d1d  jmp     loc_140119E0A
0x140119d22  mov     r8, r15; Size
0x140119d25  xor     edx, edx; Val
0x140119d27  mov     rcx, r14; void *
0x140119d2a  call    memset_0
0x140119d2f  xor     eax, eax
0x140119d31  mov     dword ptr [rbp+57h+pv], eax
0x140119d34  mov     r15d, eax
0x140119d37  cmp     r15, rdi
0x140119d3a  jnb     loc_140119DC5
0x140119d40  mov     edx, r15d
0x140119d43  lea     rcx, [rbp+57h+var_80]
0x140119d47  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x140119d4c  lea     rcx, [r15+r15*2]
0x140119d50  lea     rbx, [r14+rcx*8]
0x140119d54  mov     rax, [rax]
0x140119d57  movups  xmm0, xmmword ptr [rax+8]
0x140119d5b  movdqu  xmmword ptr [rbx+8], xmm0
0x140119d60  mov     edx, r15d
0x140119d63  lea     rcx, [rbp+57h+var_80]
0x140119d67  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x140119d6c  mov     rcx, [rax]
0x140119d6f  xor     r8d, r8d; unsigned __int64
0x140119d72  mov     rdx, rbx; unsigned __int16 **
0x140119d75  mov     rcx, [rcx]; unsigned __int16 *
0x140119d78  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x140119d7d  mov     ebx, eax
0x140119d7f  test    eax, eax
0x140119d81  js      short loc_140119DB9
0x140119d83  mov     edx, r15d
0x140119d86  lea     rcx, [rbp+57h+var_80]
0x140119d8a  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x140119d8f  mov     edx, 1; unsigned int
0x140119d94  mov     rcx, [rax]; pv
0x140119d97  call    ?BlbFreeAppInfo@@YAXPEAU_BLB_SYSTEM_APPLICATION_RESTORE_INFO@@K@Z; BlbFreeAppInfo(_BLB_SYSTEM_APPLICATION_RESTORE_INFO *,ulong)
0x140119d9c  mov     edx, r15d
0x140119d9f  lea     rcx, [rbp+57h+var_80]
0x140119da3  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x140119da8  mov     qword ptr [rax], 0
0x140119daf  mov     eax, dword ptr [rbp+57h+pv]
0x140119db2  inc     eax
0x140119db4  jmp     loc_140119D31
0x140119db9  mov     edx, edi; unsigned int
0x140119dbb  mov     rcx, r14; pv
0x140119dbe  call    ?BlbFreeAppInfo@@YAXPEAU_BLB_SYSTEM_APPLICATION_RESTORE_INFO@@K@Z; BlbFreeAppInfo(_BLB_SYSTEM_APPLICATION_RESTORE_INFO *,ulong)
0x140119dc3  jmp     short loc_140119E0A
0x140119dc5  mov     r15, [rbp+57h+var_50]
0x140119dc9  mov     [r15], edi
0x140119dcc  mov     rax, [rbp+57h+var_48]
0x140119dd0  mov     [rax], r14
0x140119dd3  mov     rcx, cs:WPP_GLOBAL_Control
0x140119dda  lea     rax, WPP_GLOBAL_Control
0x140119de1  cmp     rcx, rax
0x140119de4  jz      short loc_140119E11
0x140119de6  test    byte ptr [rcx+1Ch], 1
0x140119dea  jz      short loc_140119E11
0x140119dec  cmp     byte ptr [rcx+19h], 4
0x140119df0  jb      short loc_140119E11
0x140119df2  mov     edx, 0Fh
0x140119df7  mov     r9d, [r15]
0x140119dfa  lea     r8, WPP_0f9b83d7e0133652f3df4ebbb4d53694_Traceguids
0x140119e01  mov     rcx, [rcx+10h]
0x140119e05  call    WPP_SF_d
0x140119e0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140119e11  xor     r14d, r14d
0x140119e14  test    rdi, rdi
0x140119e17  jz      short loc_140119E59
0x140119e19  mov     r15d, r14d
0x140119e1c  mov     edx, r14d
0x140119e1f  lea     rcx, [rbp+57h+var_80]
0x140119e23  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x140119e28  cmp     qword ptr [rax], 0
0x140119e2c  jz      short loc_140119E47
0x140119e2e  mov     edx, r15d
0x140119e31  lea     rcx, [rbp+57h+var_80]
0x140119e35  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x140119e3a  mov     edx, 1; unsigned int
0x140119e3f  mov     rcx, [rax]; pv
0x140119e42  call    ?BlbFreeAppInfo@@YAXPEAU_BLB_SYSTEM_APPLICATION_RESTORE_INFO@@K@Z; BlbFreeAppInfo(_BLB_SYSTEM_APPLICATION_RESTORE_INFO *,ulong)
0x140119e47  inc     r14d
0x140119e4a  mov     eax, r14d
0x140119e4d  cmp     rax, rdi
0x140119e50  jb      short loc_140119E19
0x140119e52  mov     rcx, cs:WPP_GLOBAL_Control
0x140119e59  test    r12, r12
0x140119e5c  jz      short loc_140119E72
0x140119e5e  mov     edx, 1; unsigned int
0x140119e63  mov     rcx, r12; pv
0x140119e66  call    ?BlbFreeAppInfo@@YAXPEAU_BLB_SYSTEM_APPLICATION_RESTORE_INFO@@K@Z; BlbFreeAppInfo(_BLB_SYSTEM_APPLICATION_RESTORE_INFO *,ulong)
0x140119e6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140119e72  lea     r14, WPP_GLOBAL_Control
0x140119e79  cmp     [rbp+57h+var_A0], 0
0x140119e7e  jz      short loc_140119E91
0x140119e80  mov     rcx, [rbp+57h+var_A0]; pv
0x140119e84  call    cs:__imp_CoTaskMemFree
0x140119e8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140119e91  test    rsi, rsi
0x140119e94  jz      short loc_140119EA6
0x140119e96  mov     rcx, rsi; pv
0x140119e99  call    cs:__imp_CoTaskMemFree
0x140119e9f  mov     rcx, cs:WPP_GLOBAL_Control
0x140119ea6  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x140119eaa  jz      short loc_140119EBC
0x140119eac  mov     rcx, r13; hFindFile
0x140119eaf  call    cs:__imp_FindClose
0x140119eb5  mov     rcx, cs:WPP_GLOBAL_Control
0x140119ebc  cmp     rcx, r14
0x140119ebf  jz      short loc_140119EE3
0x140119ec1  test    byte ptr [rcx+1Ch], 1
0x140119ec5  jz      short loc_140119EE3
0x140119ec7  cmp     byte ptr [rcx+19h], 4
0x140119ecb  jb      short loc_140119EE3
0x140119ecd  mov     edx, 10h
0x140119ed2  lea     r8, WPP_0f9b83d7e0133652f3df4ebbb4d53694_Traceguids
0x140119ed9  mov     rcx, [rcx+10h]
0x140119edd  call    WPP_SF_
0x140119ee2  nop
0x140119ee3  lea     rcx, [rbp+57h+var_80]
0x140119ee7  call    ??1?$CAtlArray@U_BLB_COMPONENT@@V?$CElementTraits@U_BLB_COMPONENT@@@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(void)
0x140119eec  mov     eax, ebx
  ... truncated ...
```
