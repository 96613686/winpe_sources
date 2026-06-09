# CBlbBackupAsync::InitializePredefinedExclusions(void)

- ea: `0x14002a410`
- end: `0x14002a98d`
- name: `?InitializePredefinedExclusions@CBlbBackupAsync@@AEAAJXZ`
- size: `1405`
- prototype: `__int64 __fastcall(CBlbBackupAsync *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x140019fd0`

## callees

- `0x140006a64`
- `0x14000bb24`
- `0x14000be04`
- `0x14000efd0`
- `0x140014260`
- `0x140023e84`
- `0x14002771c`
- `0x1400278a4`
- `0x140027d94`
- `0x14002a410`
- `0x1400819b4`
- `0x14008650c`
- `0x14008863c`
- `0x140088d0c`
- `0x14008e440`
- `0x14011a224`
- `0x140137010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14002a4f1`
- `ole32!CoTaskMemFree` at `0x14002a66e`
- `ole32!CoTaskMemFree` at `0x14002a684`
- `ole32!CoTaskMemFree` at `0x14002a699`
- `ole32!CoTaskMemFree` at `0x14002a8a4`
- `ole32!CoTaskMemFree` at `0x14002a8b2`
- `ole32!CoTaskMemFree` at `0x14002a8c0`
- `ole32!CoTaskMemFree` at `0x14002a8ce`
- `ole32!CoTaskMemFree` at `0x14002a8e0`
- `ole32!CoTaskMemFree` at `0x14002a8f2`
- `ole32!CoTaskMemFree` at `0x14002a904`
- `ole32!CoTaskMemFree` at `0x14002a4f1`
- `ole32!CoTaskMemFree` at `0x14002a66e`
- `ole32!CoTaskMemFree` at `0x14002a684`
- `ole32!CoTaskMemFree` at `0x14002a699`
- `ole32!CoTaskMemFree` at `0x14002a8a4`
- `ole32!CoTaskMemFree` at `0x14002a8b2`
- `ole32!CoTaskMemFree` at `0x14002a8c0`
- `ole32!CoTaskMemFree` at `0x14002a8ce`
- `ole32!CoTaskMemFree` at `0x14002a8e0`
- `ole32!CoTaskMemFree` at `0x14002a8f2`
- `ole32!CoTaskMemFree` at `0x14002a904`
- `OLEAUT32!__imp_SysFreeString` at `0x14002a889`
- `OLEAUT32!__imp_SysFreeString` at `0x14002a889`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBlbBackupAsync::InitializePredefinedExclusions(struct _SPP_METADATA_PROP **this)
{
  unsigned int v2; // r13d
  int WriterInfo; // ebx
  void *v4; // r8
  unsigned __int16 *v5; // r14
  unsigned __int16 *v6; // rsi
  unsigned __int16 *v7; // r12
  unsigned int i; // edx
  unsigned int j; // r15d
  __int64 v10; // rcx
  unsigned int k; // r15d
  struct CBlbVolumeBackupContext *v12; // rdx
  CBlbFileBackupAsync *v13; // r13
  unsigned int v14; // r8d
  __int64 v15; // rcx
  struct _SPP_METADATA_PROP *v16; // rax
  unsigned __int16 *v17; // rsi
  int v18; // eax
  int v19; // eax
  ATL::CComBSTR *v20; // rax
  char v21; // di
  unsigned __int16 *v23; // [rsp+30h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-41h] BYREF
  unsigned __int16 *v25; // [rsp+40h] [rbp-39h] BYREF
  unsigned __int16 *v26; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int16 *v27; // [rsp+50h] [rbp-29h] BYREF
  struct _GUID v28; // [rsp+58h] [rbp-21h] BYREF
  void *v29[3]; // [rsp+68h] [rbp-11h] BYREF
  int v30; // [rsp+80h] [rbp+7h]
  BSTR bstrString; // [rsp+E0h] [rbp+67h] BYREF
  struct _SPP_METADATA_PROP *v32; // [rsp+E8h] [rbp+6Fh] BYREF
  unsigned __int16 *v33; // [rsp+F0h] [rbp+77h] BYREF
  unsigned __int16 *v34; // [rsp+F8h] [rbp+7Fh] BYREF

  v2 = 0;
  LODWORD(bstrString) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 853, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  WriterInfo = 0;
  v4 = 0;
  pv = 0;
  v28 = GUID_NULL;
  v5 = 0;
  v23 = 0;
  v6 = 0;
  v33 = 0;
  v7 = 0;
  v34 = 0;
  memset(v29, 0, sizeof(v29));
  v30 = 0;
  v27 = 0;
  v26 = 0;
  v25 = 0;
  for ( i = 0; i < *((_DWORD *)this + 92); ++i )
  {
    if ( (*((_BYTE *)this[27] + 368 * i + 84) & 0x40) != 0 )
    {
      while ( v2 < *((_DWORD *)this[57] + 2) )
      {
        if ( v4 )
        {
          CoTaskMemFree(v4);
          pv = 0;
        }
        WriterInfo = BlbGetWriterInfo(this[57], v2, &v28, (unsigned __int16 **)&pv);
        if ( WriterInfo < 0 )
          goto LABEL_62;
        for ( j = 0; j < *((_DWORD *)this + 92); ++j )
        {
          v10 = *((_QWORD *)this[27] + 46 * j + 27);
          if ( v10 )
          {
            WriterInfo = (*(__int64 (__fastcall **)(_QWORD, LPVOID))(**(_QWORD **)(v10 + 168) + 160LL))(
                           *(_QWORD *)(v10 + 168),
                           pv);
            if ( WriterInfo < 0 )
              goto LABEL_62;
          }
        }
        ++v2;
        v4 = pv;
      }
      if ( *((_BYTE *)this + 391) )
        CBlbApplicationBackupAsync::GetFileSpecsForComponents(this[104], v29, v4);
      for ( k = 0; k < *((_DWORD *)this + 92); ++k )
      {
        LODWORD(v32) = 0;
        *(_QWORD *)&v28.Data1 = 368LL * k;
        v12 = (struct _SPP_METADATA_PROP *)((char *)this[27] + *(_QWORD *)&v28.Data1);
        v13 = (CBlbFileBackupAsync *)*((_QWORD *)v12 + 27);
        if ( v13 )
        {
          WriterInfo = CBlbBackupAsync::GetVolumeMapIndex((CBlbBackupAsync *)this, v12, (unsigned int *)&v32);
          if ( WriterInfo < 0 )
            break;
          WriterInfo = CBlbFileBackupAsync::SetVolumeMap(
                         v13,
                         (struct _SPP_METADATA_PROP *)((char *)this[105] + 24 * (unsigned int)v32),
                         v14);
          if ( WriterInfo < 0 )
            break;
          WriterInfo = (*(__int64 (__fastcall **)(_QWORD *))(**((_QWORD **)v13 + 21) + 168LL))(*((_QWORD **)v13 + 21));
          if ( WriterInfo < 0 )
            break;
          WriterInfo = CBlbBackupAsync::ExcludeAppFileSpecsForVolume(
                         this,
                         (char *)this[27] + *(_QWORD *)&v28.Data1,
                         v29);
          if ( WriterInfo < 0 )
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              v21 = (char)bstrString;
            }
            else
            {
              v20 = ATL::CComBSTR::CComBSTR(
                      (ATL::CComBSTR *)&bstrString,
                      (const struct _GUID *)((char *)this[27] + *(_QWORD *)&v28.Data1 + 68));
              v21 = 1;
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                855,
                (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
                *(_QWORD *)v20,
                WriterInfo);
            }
            if ( (v21 & 1) != 0 )
              SysFreeString(bstrString);
            break;
          }
          v16 = this[125];
          v32 = v16;
          while ( v16 )
          {
            if ( v5 )
            {
              CoTaskMemFree(v5);
              v23 = 0;
            }
            if ( v7 )
            {
              CoTaskMemFree(v7);
              v7 = 0;
              v34 = 0;
            }
            if ( v6 )
            {
              CoTaskMemFree(v6);
              v33 = 0;
            }
            v17 = *(unsigned __int16 **)ATL::CAtlList<unsigned short *,ATL::CElementTraits<unsigned short *>>::GetNext(
                                          v15,
                                          &v32);
            v18 = BlbutilSplitFilePath(v17, &v23, &v33);
            WriterInfo = v18;
            if ( v18 < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  856,
                  (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
                  (_DWORD)v17,
                  v18);
              }
              v5 = v23;
              v6 = v33;
              goto LABEL_62;
            }
            v5 = v23;
            v19 = BlbutilSlashTerminatePath(v23, (LPVOID *)&v34);
            WriterInfo = v19;
            if ( v19 < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  857,
                  (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
                  (_DWORD)v5,
                  v19);
              }
              v6 = v33;
              v7 = v34;
              goto LABEL_62;
            }
            v6 = v33;
            v7 = v34;
            WriterInfo = CBlbFileAsync::AddExclusion(v13, v34, v33, 0);
            if ( WriterInfo < 0 )
              goto LABEL_62;
            v16 = v32;
          }
          WriterInfo = CBlbVolumeBackupContext::GetOriginalAccessPath(
                         (struct _SPP_METADATA_PROP *)((char *)this[27] + *(_QWORD *)&v28.Data1),
                         &v25);
          if ( WriterInfo < 0 )
            break;
          WriterInfo = BlbutilSlashTerminatePath(v25, (LPVOID *)&v26);
          if ( WriterInfo < 0 )
            break;
          WriterInfo = BlbutilAppendString(v26, L"System Volume Information\\Dedup", &v27);
          if ( WriterInfo < 0 )
            break;
          WriterInfo = CBlbFileAsync::AddExclusion(v13, v27, L"*", 1u);
          if ( WriterInfo < 0 )
            break;
        }
      }
LABEL_62:
      if ( pv )
        CoTaskMemFree(pv);
      if ( v5 )
        CoTaskMemFree(v5);
      if ( v7 )
        CoTaskMemFree(v7);
      if ( v6 )
        CoTaskMemFree(v6);
      if ( v25 )
        CoTaskMemFree(v25);
      if ( v26 )
        CoTaskMemFree(v26);
      if ( v27 )
        CoTaskMemFree(v27);
      goto LABEL_80;
    }
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_84;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 854, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
LABEL_80:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 858, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
LABEL_84:
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(v29);
  return (unsigned int)WriterInfo;
}

```

## disassembly

```asm
0x14002a410  push    rbp
0x14002a412  push    rbx
0x14002a413  push    rsi
0x14002a414  push    rdi
0x14002a415  push    r12
0x14002a417  push    r13
0x14002a419  push    r14
0x14002a41b  push    r15
0x14002a41d  lea     rbp, [rsp-1Fh]
0x14002a422  sub     rsp, 98h
0x14002a429  mov     rdi, rcx
0x14002a42c  xor     r13d, r13d
0x14002a42f  mov     dword ptr [rbp+57h+bstrString], r13d
0x14002a433  lea     rdx, WPP_GLOBAL_Control
0x14002a43a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a441  cmp     rcx, rdx
0x14002a444  jz      short loc_14002A467
0x14002a446  test    byte ptr [rcx+1Ch], 1
0x14002a44a  jz      short loc_14002A467
0x14002a44c  cmp     byte ptr [rcx+19h], 4
0x14002a450  jb      short loc_14002A467
0x14002a452  mov     edx, 355h
0x14002a457  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14002a45e  mov     rcx, [rcx+10h]
0x14002a462  call    WPP_SF_
0x14002a467  mov     ebx, r13d
0x14002a46a  mov     r8, r13
0x14002a46d  mov     [rbp+57h+pv], r13
0x14002a471  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14002a478  movdqu  xmmword ptr [rbp+57h+var_78.Data1], xmm0
0x14002a47d  mov     r14, r13
0x14002a480  mov     [rbp+57h+var_A0], r13
0x14002a484  mov     rsi, r13
0x14002a487  mov     [rbp+57h+arg_10], r13
0x14002a48b  mov     r12, r13
0x14002a48e  mov     [rbp+57h+arg_18], r13
0x14002a492  mov     [rbp+57h+var_68], r13
0x14002a496  mov     [rbp+57h+var_60], r13
0x14002a49a  mov     [rbp+57h+var_58], r13
0x14002a49e  mov     [rbp+57h+var_50], r13d
0x14002a4a2  mov     [rbp+57h+var_80], r13
0x14002a4a6  mov     [rbp+57h+var_88], r13
0x14002a4aa  mov     [rbp+57h+var_90], r13
0x14002a4ae  mov     edx, r13d
0x14002a4b1  cmp     edx, [rdi+170h]
0x14002a4b7  jnb     loc_14002A90C
0x14002a4bd  mov     eax, edx
0x14002a4bf  imul    rcx, rax, 170h
0x14002a4c6  mov     rax, [rdi+0D8h]
0x14002a4cd  test    byte ptr [rcx+rax+54h], 40h
0x14002a4d2  jnz     short loc_14002A4D8
0x14002a4d4  inc     edx
0x14002a4d6  jmp     short loc_14002A4B1
0x14002a4d8  mov     rax, [rdi+1C8h]
0x14002a4df  cmp     r13d, [rax+8]
0x14002a4e3  jnb     loc_14002A57F
0x14002a4e9  test    r8, r8
0x14002a4ec  jz      short loc_14002A4FF
0x14002a4ee  mov     rcx, r8; pv
0x14002a4f1  call    cs:__imp_CoTaskMemFree
0x14002a4f7  mov     [rbp+57h+pv], 0
0x14002a4ff  lea     r9, [rbp+57h+pv]; unsigned __int16 **
0x14002a503  lea     r8, [rbp+57h+var_78]; struct _GUID *
0x14002a507  mov     edx, r13d; unsigned int
0x14002a50a  mov     rcx, [rdi+1C8h]; struct _SPP_METADATA_PROP *
0x14002a511  call    ?BlbGetWriterInfo@@YAJPEAU_SPP_METADATA_PROP@@KPEAU_GUID@@PEAPEAG@Z; BlbGetWriterInfo(_SPP_METADATA_PROP *,ulong,_GUID *,ushort * *)
0x14002a516  mov     ebx, eax
0x14002a518  test    eax, eax
0x14002a51a  js      loc_14002A891
0x14002a520  xor     r15d, r15d
0x14002a523  cmp     r15d, [rdi+170h]
0x14002a52a  jnb     short loc_14002A573
0x14002a52c  mov     ecx, r15d
0x14002a52f  imul    rdx, rcx, 170h
0x14002a536  mov     rax, [rdi+0D8h]
0x14002a53d  mov     rcx, [rdx+rax+0D8h]
0x14002a545  test    rcx, rcx
0x14002a548  jz      short loc_14002A56E
0x14002a54a  mov     rcx, [rcx+0A8h]
0x14002a551  mov     rax, [rcx]
0x14002a554  mov     rdx, [rbp+57h+pv]
0x14002a558  mov     rax, [rax+0A0h]
0x14002a55f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a564  mov     ebx, eax
0x14002a566  test    eax, eax
0x14002a568  js      loc_14002A891
0x14002a56e  inc     r15d
0x14002a571  jmp     short loc_14002A523
0x14002a573  inc     r13d
0x14002a576  mov     r8, [rbp+57h+pv]
0x14002a57a  jmp     loc_14002A4D8
0x14002a57f  cmp     byte ptr [rdi+187h], 0
0x14002a586  jz      short loc_14002A598
0x14002a588  lea     rdx, [rbp+57h+var_68]
0x14002a58c  mov     rcx, [rdi+340h]
0x14002a593  call    ?GetFileSpecsForComponents@CBlbApplicationBackupAsync@@QEAAXAEAV?$CAtlArray@U_WSB_SPEC_INFO@@V?$CElementTraits@U_WSB_SPEC_INFO@@@ATL@@@ATL@@@Z; CBlbApplicationBackupAsync::GetFileSpecsForComponents(ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>> &)
0x14002a598  xor     r15d, r15d
0x14002a59b  cmp     r15d, [rdi+170h]
0x14002a5a2  jnb     loc_14002A891
0x14002a5a8  mov     dword ptr [rbp+57h+arg_8], 0
0x14002a5af  mov     eax, r15d
0x14002a5b2  imul    rcx, rax, 170h
0x14002a5b9  mov     qword ptr [rbp+57h+var_78.Data1], rcx
0x14002a5bd  mov     rdx, [rdi+0D8h]
0x14002a5c4  add     rdx, rcx; struct CBlbVolumeBackupContext *
0x14002a5c7  mov     r13, [rdx+0D8h]
0x14002a5ce  test    r13, r13
0x14002a5d1  jz      loc_14002A786
0x14002a5d7  lea     r8, [rbp+57h+arg_8]; unsigned int *
0x14002a5db  mov     rcx, rdi; this
0x14002a5de  call    ?GetVolumeMapIndex@CBlbBackupAsync@@AEAAJPEAVCBlbVolumeBackupContext@@PEAK@Z; CBlbBackupAsync::GetVolumeMapIndex(CBlbVolumeBackupContext *,ulong *)
0x14002a5e3  mov     ebx, eax
0x14002a5e5  test    eax, eax
0x14002a5e7  js      loc_14002A891
0x14002a5ed  mov     eax, dword ptr [rbp+57h+arg_8]
0x14002a5f0  lea     rcx, [rax+rax*2]
0x14002a5f4  mov     rax, [rdi+348h]
0x14002a5fb  lea     rdx, [rax+rcx*8]; struct _BLBSRV_VOLUME_MAP *
0x14002a5ff  mov     rcx, r13; this
0x14002a602  call    ?SetVolumeMap@CBlbFileBackupAsync@@QEAAJPEAU_BLBSRV_VOLUME_MAP@@K@Z; CBlbFileBackupAsync::SetVolumeMap(_BLBSRV_VOLUME_MAP *,ulong)
0x14002a607  mov     ebx, eax
0x14002a609  test    eax, eax
0x14002a60b  js      loc_14002A891
0x14002a611  mov     rcx, [r13+0A8h]
0x14002a618  mov     rax, [rcx]
0x14002a61b  mov     rax, [rax+0A8h]
0x14002a622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a627  mov     ebx, eax
0x14002a629  test    eax, eax
0x14002a62b  js      loc_14002A891
0x14002a631  mov     rdx, qword ptr [rbp+57h+var_78.Data1]
0x14002a635  add     rdx, [rdi+0D8h]
0x14002a63c  lea     r8, [rbp+57h+var_68]
0x14002a640  mov     rcx, rdi
0x14002a643  call    ?ExcludeAppFileSpecsForVolume@CBlbBackupAsync@@AEAAJPEAVCBlbVolumeBackupContext@@AEBV?$CAtlArray@U_WSB_SPEC_INFO@@V?$CElementTraits@U_WSB_SPEC_INFO@@@ATL@@@ATL@@@Z; CBlbBackupAsync::ExcludeAppFileSpecsForVolume(CBlbVolumeBackupContext *,ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>> const &)
0x14002a648  mov     ebx, eax
0x14002a64a  test    eax, eax
0x14002a64c  js      loc_14002A81B
0x14002a652  mov     rax, [rdi+3E8h]
0x14002a659  mov     [rbp+57h+arg_8], rax
0x14002a65d  test    rax, rax
0x14002a660  jz      loc_14002A713
0x14002a666  test    r14, r14
0x14002a669  jz      short loc_14002A67C
0x14002a66b  mov     rcx, r14; pv
0x14002a66e  call    cs:__imp_CoTaskMemFree
0x14002a674  mov     [rbp+57h+var_A0], 0
0x14002a67c  test    r12, r12
0x14002a67f  jz      short loc_14002A691
0x14002a681  mov     rcx, r12; pv
0x14002a684  call    cs:__imp_CoTaskMemFree
0x14002a68a  xor     r12d, r12d
0x14002a68d  mov     [rbp+57h+arg_18], r12
0x14002a691  test    rsi, rsi
0x14002a694  jz      short loc_14002A6A7
0x14002a696  mov     rcx, rsi; pv
0x14002a699  call    cs:__imp_CoTaskMemFree
0x14002a69f  mov     [rbp+57h+arg_10], 0
0x14002a6a7  lea     rdx, [rbp+57h+arg_8]
0x14002a6ab  call    ?GetNext@?$CAtlList@PEAGV?$CElementTraits@PEAG@ATL@@@ATL@@QEAAAEAPEAGAEAPEAU__POSITION@@@Z; ATL::CAtlList<ushort *,ATL::CElementTraits<ushort *>>::GetNext(__POSITION * &)
0x14002a6b0  mov     rsi, [rax]
0x14002a6b3  lea     r8, [rbp+57h+arg_10]; unsigned __int16 **
0x14002a6b7  lea     rdx, [rbp+57h+var_A0]; unsigned __int16 **
0x14002a6bb  mov     rcx, rsi; unsigned __int16 *
0x14002a6be  call    ?BlbutilSplitFilePath@@YAJPEAGPEAPEAG1@Z; BlbutilSplitFilePath(ushort *,ushort * *,ushort * *)
0x14002a6c3  mov     ebx, eax
0x14002a6c5  test    eax, eax
0x14002a6c7  js      loc_14002A7D6
0x14002a6cd  lea     rdx, [rbp+57h+arg_18]; unsigned __int16 **
0x14002a6d1  mov     r14, [rbp+57h+var_A0]
0x14002a6d5  mov     rcx, r14; unsigned __int16 *
0x14002a6d8  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x14002a6dd  mov     ebx, eax
0x14002a6df  test    eax, eax
0x14002a6e1  js      loc_14002A78E
0x14002a6e7  xor     r9d, r9d; unsigned __int8
0x14002a6ea  mov     rsi, [rbp+57h+arg_10]
0x14002a6ee  mov     r8, rsi; unsigned __int16 *
0x14002a6f1  mov     r12, [rbp+57h+arg_18]
0x14002a6f5  mov     rdx, r12; unsigned __int16 *
0x14002a6f8  mov     rcx, r13; this
0x14002a6fb  call    ?AddExclusion@CBlbFileAsync@@QEAAJPEAG0E@Z; CBlbFileAsync::AddExclusion(ushort *,ushort *,uchar)
0x14002a700  mov     ebx, eax
0x14002a702  test    eax, eax
0x14002a704  js      loc_14002A891
0x14002a70a  mov     rax, [rbp+57h+arg_8]
0x14002a70e  jmp     loc_14002A65D
0x14002a713  mov     rcx, qword ptr [rbp+57h+var_78.Data1]
0x14002a717  add     rcx, [rdi+0D8h]; this
0x14002a71e  lea     rdx, [rbp+57h+var_90]; unsigned __int16 **
0x14002a722  call    ?GetOriginalAccessPath@CBlbVolumeBackupContext@@QEAAJPEAPEAG@Z; CBlbVolumeBackupContext::GetOriginalAccessPath(ushort * *)
0x14002a727  mov     ebx, eax
0x14002a729  test    eax, eax
0x14002a72b  js      loc_14002A891
0x14002a731  lea     rdx, [rbp+57h+var_88]; unsigned __int16 **
0x14002a735  mov     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x14002a739  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x14002a73e  mov     ebx, eax
0x14002a740  test    eax, eax
0x14002a742  js      loc_14002A891
0x14002a748  lea     r8, [rbp+57h+var_80]; unsigned __int16 **
0x14002a74c  lea     rdx, aSystemVolumeIn_1; "System Volume Information\\Dedup"
0x14002a753  mov     rcx, [rbp+57h+var_88]; unsigned __int16 *
0x14002a757  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x14002a75c  mov     ebx, eax
0x14002a75e  test    eax, eax
0x14002a760  js      loc_14002A891
0x14002a766  mov     r9b, 1; unsigned __int8
0x14002a769  lea     r8, asc_14013BEE0; "*"
0x14002a770  mov     rdx, [rbp+57h+var_80]; unsigned __int16 *
0x14002a774  mov     rcx, r13; this
0x14002a777  call    ?AddExclusion@CBlbFileAsync@@QEAAJPEAG0E@Z; CBlbFileAsync::AddExclusion(ushort *,ushort *,uchar)
0x14002a77c  mov     ebx, eax
0x14002a77e  test    eax, eax
0x14002a780  js      loc_14002A891
0x14002a786  inc     r15d
0x14002a789  jmp     loc_14002A59B
0x14002a78e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a795  lea     r13, WPP_GLOBAL_Control
0x14002a79c  cmp     rcx, r13
0x14002a79f  jz      short loc_14002A7C9
0x14002a7a1  test    byte ptr [rcx+1Ch], 1
0x14002a7a5  jz      short loc_14002A7C9
0x14002a7a7  cmp     byte ptr [rcx+19h], 2
0x14002a7ab  jb      short loc_14002A7C9
0x14002a7ad  mov     edx, 359h
0x14002a7b2  mov     [rsp+0D0h+var_B0], eax
0x14002a7b6  mov     r9, r14
0x14002a7b9  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14002a7c0  mov     rcx, [rcx+10h]
0x14002a7c4  call    WPP_SF_Sd
0x14002a7c9  mov     rsi, [rbp+57h+arg_10]
0x14002a7cd  mov     r12, [rbp+57h+arg_18]
0x14002a7d1  jmp     loc_14002A898
0x14002a7d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a7dd  lea     r13, WPP_GLOBAL_Control
0x14002a7e4  cmp     rcx, r13
0x14002a7e7  jz      short loc_14002A811
0x14002a7e9  test    byte ptr [rcx+1Ch], 1
0x14002a7ed  jz      short loc_14002A811
0x14002a7ef  cmp     byte ptr [rcx+19h], 2
0x14002a7f3  jb      short loc_14002A811
0x14002a7f5  mov     edx, 358h
0x14002a7fa  mov     [rsp+0D0h+var_B0], eax
0x14002a7fe  mov     r9, rsi
0x14002a801  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14002a808  mov     rcx, [rcx+10h]
0x14002a80c  call    WPP_SF_Sd
0x14002a811  mov     r14, [rbp+57h+var_A0]
0x14002a815  mov     rsi, [rbp+57h+arg_10]
0x14002a819  jmp     short loc_14002A898
0x14002a81b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a822  lea     r13, WPP_GLOBAL_Control
0x14002a829  cmp     rcx, r13
0x14002a82c  jz      short loc_14002A87C
0x14002a82e  test    byte ptr [rcx+1Ch], 1
0x14002a832  jz      short loc_14002A87C
0x14002a834  cmp     byte ptr [rcx+19h], 2
0x14002a838  jb      short loc_14002A87C
0x14002a83a  mov     rdx, qword ptr [rbp+57h+var_78.Data1]
0x14002a83e  add     rdx, 44h ; 'D'
0x14002a842  add     rdx, [rdi+0D8h]; struct _GUID *
0x14002a849  lea     rcx, [rbp+57h+bstrString]; this
0x14002a84d  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x14002a852  mov     edi, 1
0x14002a857  mov     edx, 357h
0x14002a85c  mov     [rsp+0D0h+var_B0], ebx
0x14002a860  mov     r9, [rax]
0x14002a863  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14002a86a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a871  mov     rcx, [rcx+10h]
0x14002a875  call    WPP_SF_Sd
0x14002a87a  jmp     short loc_14002A87F
0x14002a87c  mov     edi, dword ptr [rbp+57h+bstrString]
0x14002a87f  test    dil, 1
0x14002a883  jz      short loc_14002A898
0x14002a885  mov     rcx, [rbp+57h+bstrString]; bstrString
0x14002a889  call    cs:__imp_SysFreeString
0x14002a88f  jmp     short loc_14002A898
0x14002a891  lea     r13, WPP_GLOBAL_Control
0x14002a898  mov     rax, [rbp+57h+pv]
0x14002a89c  test    rax, rax
0x14002a89f  jz      short loc_14002A8AA
0x14002a8a1  mov     rcx, rax; pv
0x14002a8a4  call    cs:__imp_CoTaskMemFree
0x14002a8aa  test    r14, r14
0x14002a8ad  jz      short loc_14002A8B8
0x14002a8af  mov     rcx, r14; pv
0x14002a8b2  call    cs:__imp_CoTaskMemFree
0x14002a8b8  test    r12, r12
0x14002a8bb  jz      short loc_14002A8C6
0x14002a8bd  mov     rcx, r12; pv
0x14002a8c0  call    cs:__imp_CoTaskMemFree
0x14002a8c6  test    rsi, rsi
0x14002a8c9  jz      short loc_14002A8D4
0x14002a8cb  mov     rcx, rsi; pv
0x14002a8ce  call    cs:__imp_CoTaskMemFree
0x14002a8d4  mov     r15, [rbp+57h+var_90]
0x14002a8d8  test    r15, r15
0x14002a8db  jz      short loc_14002A8E6
  ... truncated ...
```
