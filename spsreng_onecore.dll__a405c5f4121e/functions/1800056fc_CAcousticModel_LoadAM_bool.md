# CAcousticModel::LoadAM(bool)

- ea: `0x1800056fc`
- end: `0x180005eb1`
- name: `?LoadAM@CAcousticModel@@QEAAJ_N@Z`
- size: `1973`
- prototype: `__int64 __fastcall(CAcousticModel *this, char)`
- caller_count: `4`
- callee_count: `32`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800055f8`
- `0x180005fb8`
- `0x18000ff78`
- `0x180013e90`

## callees

- `0x1800034b0`
- `0x180004a80`
- `0x180004b08`
- `0x180004c18`
- `0x1800052f0`
- `0x180005454`
- `0x1800055cc`
- `0x1800056fc`
- `0x1800060c0`
- `0x1800061d0`
- `0x1800062a0`
- `0x180013e90`
- `0x180014014`
- `0x1800617d0`
- `0x18007218c`
- `0x180072298`
- `0x1800722e0`
- `0x180072e50`
- `0x180073db4`
- `0x1800747d0`
- `0x1800898d4`
- `0x18008a04c`
- `0x18008b194`
- `0x1800a42fc`
- `0x1800a5aa8`
- `0x1800a7e2c`
- `0x1800af148`
- `0x1800af344`
- `0x1800af360`
- `0x1800b15b4`
- `0x1800ff514`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180005b02`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180005b4a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180005b59`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180005b6b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180005b02`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180005b4a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180005b59`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180005b6b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180005b29`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180005b29`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180005b17`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180005b17`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005e71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005e71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005756`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005756`

## pseudocode

```c
__int64 __fastcall CAcousticModel::LoadAM(CAcousticModel *this, char a2)
{
  __int64 v4; // rsi
  LPCWSTR *v5; // r13
  unsigned int v6; // edx
  int Win32Error; // ebx
  CPhoneConfusionMatrix *v8; // rcx
  int i; // r14d
  CMvw *MvwObject; // rax
  char v11; // r15
  int AMFileName; // eax
  const WCHAR *v13; // rbx
  LPCWSTR *v14; // r14
  int AcousticModel; // eax
  const WCHAR *v16; // rbx
  unsigned __int16 *v17; // rax
  char v18; // r9
  unsigned __int16 *v19; // rdx
  CMllr_imp *v20; // rcx
  __int64 v21; // rdx
  CPhoneConfusionMatrix *v22; // rax
  __int16 *v23; // rdx
  CPhoneConfusionMatrix *v24; // rcx
  int j; // r14d
  int v26; // edx
  CAMCollection *v27; // rcx
  CMvw *v28; // r10
  struct CMllr *MllrObject; // r15
  CMllr_imp *v30; // rcx
  struct CMvw *v31; // r8
  CSREngine *v32; // rcx
  bool v34; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpFileName; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR v36; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID Buf1; // [rsp+88h] [rbp-78h] BYREF
  struct _GUID Buf2; // [rsp+98h] [rbp-68h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+B0h] [rbp-50h] BYREF

  lpFileName = 0;
  v36 = 0;
  v34 = 0;
  v4 = *(_QWORD *)(*((_QWORD *)this + 1) + 136LL);
  EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v4 + 64) + 600LL));
  CSREngine::StopCollectingAdaptationData(*((CSREngine **)this + 1));
  CSpDynamicString::_free((CAcousticModel *)((char *)this + 56));
  v5 = (LPCWSTR *)((char *)this + 64);
  CSpDynamicString::_free((CAcousticModel *)((char *)this + 64));
  CSpDynamicString::_free((CAcousticModel *)((char *)this + 72));
  CSpDynamicString::_free((CAcousticModel *)((char *)this + 80));
  CConfidence::RelinquishAllClassifiers((CConfidence *)(*(_QWORD *)(*(_QWORD *)(v4 + 64) + 520LL) + 552LL));
  Win32Error = CMvw::UnloadAcousticModel(*(CMvw **)(v4 + 88));
  if ( Win32Error < 0 )
    goto LABEL_84;
  v8 = *(CPhoneConfusionMatrix **)(*((_QWORD *)this + 1) + 936LL);
  if ( v8 )
  {
    CPhoneConfusionMatrix::`scalar deleting destructor'(v8, v6);
    *(_QWORD *)(*((_QWORD *)this + 1) + 936LL) = 0;
  }
  for ( i = 0; i < *((_DWORD *)this + 7); ++i )
  {
    CSpDynamicString::_free((CAcousticModel *)((char *)this + 24 * i + 96));
    CSpDynamicString::_free((CAcousticModel *)((char *)this + 24 * i + 104));
    MvwObject = CAMCollection::GetMvwObject((CAMCollection *)(v4 + 96), i);
    if ( MvwObject )
      CMvw::UnloadAcousticModel(MvwObject);
  }
  *((_DWORD *)this + 7) = 0;
  *((_BYTE *)this + 88) = a2;
  CSpDynamicString::_free((CAcousticModel *)((char *)this + 40));
  CSpDynamicString::_free((CAcousticModel *)((char *)this + 48));
  Win32Error = CAcousticModel::DetermineBaselineModel(
                 this,
                 *((_DWORD *)this + 9),
                 (unsigned int *)this + 4,
                 (unsigned __int16 **)this + 5,
                 (unsigned __int16 **)this + 6,
                 *((unsigned __int8 *)this + 32));
  if ( Win32Error < 0 )
    goto LABEL_84;
  v11 = 1;
  StringCchPrintfW(ExistingFileName, 0x105u, L"%s.am", *((_QWORD *)this + 6));
  if ( *(_DWORD *)(*((_QWORD *)this + 1) + 876LL) )
  {
    v14 = (LPCWSTR *)((char *)this + 56);
  }
  else
  {
    AMFileName = CAcousticModel::GetAMFileName(
                   this,
                   L"am",
                   *((_BYTE *)this + 88) == 0,
                   (unsigned __int16 **)&lpFileName);
    Win32Error = AMFileName;
    if ( AMFileName < 0 )
      goto LABEL_84;
    if ( AMFileName != 1 )
    {
      *((_BYTE *)this + 88) = 0;
      v13 = lpFileName;
      Buf2 = 0;
      Buf1 = 0;
      if ( (unsigned int)GetAMFileID(ExistingFileName, &Buf2)
        || (unsigned int)GetAMFileID(v13, &Buf1)
        || memcmp_0(&Buf1, &Buf2, 0x10u) )
      {
        (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v4 + 16) + 128LL))(
          *(_QWORD *)(v4 + 16),
          2135,
          2);
      }
      else
      {
        v11 = 0;
      }
    }
    v14 = (LPCWSTR *)((char *)this + 56);
    Win32Error = CAcousticModel::GetAMFileName(this, L"fpr", *((_BYTE *)this + 88) == 0, (unsigned __int16 **)this + 7);
    if ( Win32Error < 0 )
      goto LABEL_84;
    CArgParser::GetBool((CArgParser *)(v4 + 624), "backupprofile", &v34);
    if ( v34 )
    {
      Win32Error = CAcousticModel::GetAMFileName(this, L"am_bak", *((_BYTE *)this + 88) == 0, (unsigned __int16 **)&v36);
      if ( Win32Error < 0 )
        goto LABEL_84;
      Win32Error = CAcousticModel::GetAMFileName(
                     this,
                     L"fpr_bak",
                     *((_BYTE *)this + 88) == 0,
                     (unsigned __int16 **)this + 8);
      if ( Win32Error < 0 )
        goto LABEL_84;
    }
    if ( !v11 )
    {
      AcousticModel = CMvw::LoadAcousticModel(
                        *(CMvw **)(v4 + 88),
                        (struct CEngine *)v4,
                        (unsigned __int16 *)lpFileName,
                        *((_BYTE *)this + 88),
                        (unsigned __int16 *)v36,
                        ExistingFileName);
      if ( AcousticModel >= 0 )
      {
        if ( AcousticModel == 1 )
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v4 + 16) + 128LL))(
            *(_QWORD *)(v4 + 16),
            2135,
            2);
        goto LABEL_42;
      }
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v4 + 16) + 128LL))(*(_QWORD *)(v4 + 16), 2135, 2);
      CMvw::UnloadAcousticModel(*(CMvw **)(v4 + 88));
      v11 = 1;
    }
  }
  if ( *((_BYTE *)this + 88) || *(_DWORD *)(*((_QWORD *)this + 1) + 876LL) )
  {
    CSpDynamicString::operator=((CSpDynamicString *)&lpFileName, ExistingFileName);
    if ( !lpFileName )
    {
LABEL_51:
      Win32Error = -2147024882;
LABEL_84:
      CSpDynamicString::_free((CAcousticModel *)((char *)this + 40));
      goto LABEL_85;
    }
  }
  else
  {
    DeleteFileW(lpFileName);
    v16 = lpFileName;
    if ( !CopyFileW(ExistingFileName, lpFileName, 0) || !SetFileAttributesW(v16, 0x80u) )
    {
      Win32Error = HrFromLastWin32Error();
      if ( Win32Error < 0 )
        goto LABEL_84;
    }
    if ( *v14 )
      DeleteFileW(*v14);
    if ( *v5 )
      DeleteFileW(*v5);
    v17 = (unsigned __int16 *)v36;
    if ( !v36 )
      goto LABEL_39;
    DeleteFileW(v36);
  }
  v17 = (unsigned __int16 *)v36;
LABEL_39:
  v18 = *((_BYTE *)this + 88);
  v19 = ExistingFileName;
  if ( v18 )
    v19 = 0;
  Win32Error = CMvw::LoadAcousticModel(
                 *(CMvw **)(v4 + 88),
                 (struct CEngine *)v4,
                 (unsigned __int16 *)lpFileName,
                 v18,
                 v17,
                 v19);
  if ( Win32Error < 0 )
    goto LABEL_84;
LABEL_42:
  Win32Error = CDecoder::search_init_wfst_network(
                 *(CDecoder **)(v4 + 64),
                 *(struct CWFSTNetwork **)(*(_QWORD *)(v4 + 88) + 144LL));
  if ( Win32Error < 0 )
    goto LABEL_84;
  if ( *(_DWORD *)(*(_QWORD *)(v4 + 88) + 928LL) )
  {
    Win32Error = CDecoder::search_init_hlda_transform(*(CDecoder **)(v4 + 64));
    if ( Win32Error < 0 )
      goto LABEL_84;
  }
  Win32Error = CMllr_imp::AdaptInitAlignment(*(CMllr_imp **)(*(_QWORD *)(v4 + 144) + 16LL));
  if ( Win32Error < 0 )
    goto LABEL_84;
  Win32Error = CAptVTLN::InitAdaptation(*(CAptVTLN **)(v4 + 160));
  if ( Win32Error < 0 )
    goto LABEL_84;
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 144) + 16LL) + 1160LL) = -1;
  if ( *((_BYTE *)this + 88) )
  {
    if ( !*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v4 + 144) + 16LL) + 354LL) )
      goto LABEL_54;
  }
  else
  {
    Win32Error = CMvw::GenerateSISections(*(CMvw **)(v4 + 88), ExistingFileName);
    if ( Win32Error < 0 )
      goto LABEL_84;
  }
  Win32Error = CMllr_imp::AdaptInitAdaptation(*(CMllr_imp **)(*(_QWORD *)(v4 + 144) + 16LL));
  if ( Win32Error < 0 )
    goto LABEL_84;
LABEL_54:
  v20 = *(CMllr_imp **)(*(_QWORD *)(v4 + 144) + 16LL);
  if ( *((_BYTE *)v20 + 354) )
  {
    if ( !v11 )
      Win32Error = CMllr_imp::InitRegrBuf(v20, *v14, (unsigned __int16 *)*v5);
    if ( Win32Error < 0 )
      goto LABEL_84;
  }
  v21 = *((_QWORD *)this + 1);
  if ( !*(_QWORD *)(v21 + 936) && *(_QWORD *)(*(_QWORD *)(v4 + 88) + 872LL) )
  {
    v22 = (CPhoneConfusionMatrix *)CAllocOnSpecificHeapBase::operator_new(0xCA0u, *(struct CHeap **)(v21 + 128), 0);
    v24 = v22 ? CPhoneConfusionMatrix::CPhoneConfusionMatrix(v22, v23) : 0LL;
    *(_QWORD *)(*((_QWORD *)this + 1) + 936LL) = v24;
    if ( !*(_QWORD *)(*((_QWORD *)this + 1) + 936LL) )
      goto LABEL_51;
  }
  if ( *((_BYTE *)this + 32) && *((int *)this + 7) > 0 )
  {
    for ( j = 0; ; ++j )
    {
      v26 = *((_DWORD *)this + 7);
      if ( j >= v26 )
        break;
      *(_QWORD *)&Buf2.Data1 = 0;
      *(_QWORD *)&Buf1.Data1 = CAMCollection::GetMvwObject((CAMCollection *)(v4 + 96), j);
      if ( *(_QWORD *)&Buf1.Data1 )
      {
        MllrObject = CAMCollection::GetMllrObject(v27, j);
      }
      else
      {
        Win32Error = CAMCollection::AddOneModel(v27, j, (struct CMvw **)&Buf1, (struct CMllr **)&Buf2);
        if ( Win32Error < 0 )
          goto LABEL_84;
        v28 = *(CMvw **)&Buf1.Data1;
        MllrObject = *(struct CMllr **)&Buf2.Data1;
      }
      Win32Error = CMvw::LoadAcousticModel(
                     v28,
                     (struct CEngine *)v4,
                     *((unsigned __int16 **)this + 3 * j + 13),
                     1,
                     0,
                     0);
      if ( Win32Error < 0 )
        goto LABEL_84;
      Win32Error = CMllr_imp::AdaptInitAlignment(*((CMllr_imp **)MllrObject + 2));
      if ( Win32Error < 0 )
        goto LABEL_84;
      if ( *(_DWORD *)(*((_QWORD *)this + 1) + 876LL) == 1 )
      {
        v30 = (CMllr_imp *)*((_QWORD *)MllrObject + 2);
        if ( *((_BYTE *)v30 + 354) )
        {
          Win32Error = CMllr_imp::AdaptInitAdaptation(v30);
          if ( Win32Error < 0 )
            goto LABEL_84;
        }
      }
      *(_DWORD *)(*((_QWORD *)MllrObject + 2) + 1160LL) = j;
    }
  }
  else
  {
    *((_BYTE *)this + 32) = 0;
    v26 = 0;
  }
  CDecoder::search_set_autodetect(*(CDecoder **)(v4 + 64), v26);
  CDecoder::search_init_models_tp(*(CDecoder **)(v4 + 64), *(struct SMD_TP **)(*(_QWORD *)(v4 + 88) + 776LL), v31);
  if ( !*((_BYTE *)this + 32) )
  {
    v32 = (CSREngine *)*((_QWORD *)this + 1);
    if ( *((_BYTE *)v32 + 786) )
    {
      if ( (int)CSREngine::StartCollectingAdaptationData(v32) < 0 )
        *(_BYTE *)(*((_QWORD *)this + 1) + 786LL) = 0;
    }
  }
LABEL_85:
  LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v4 + 64) + 600LL));
  CSpDynamicString::_free((CSpDynamicString *)&v36);
  CSpDynamicString::_free((CSpDynamicString *)&lpFileName);
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x1800056fc  push    rbp
0x1800056fe  push    rbx
0x1800056ff  push    rsi
0x180005700  push    rdi
0x180005701  push    r12
0x180005703  push    r13
0x180005705  push    r14
0x180005707  push    r15
0x180005709  lea     rbp, [rsp-1D8h]
0x180005711  sub     rsp, 2D8h
0x180005718  mov     rax, cs:__security_cookie
0x18000571f  xor     rax, rsp
0x180005722  mov     [rbp+210h+var_50], rax
0x180005729  mov     r12b, dl
0x18000572c  mov     rdi, rcx
0x18000572f  xor     r15d, r15d
0x180005732  mov     [rsp+310h+lpFileName], r15
0x180005737  mov     [rbp+210h+var_290], r15
0x18000573b  mov     [rsp+310h+var_2A0], r15b
0x180005740  mov     rax, [rcx+8]
0x180005744  mov     rsi, [rax+88h]
0x18000574b  mov     rcx, [rsi+40h]
0x18000574f  add     rcx, 258h; lpCriticalSection
0x180005756  call    cs:__imp_EnterCriticalSection
0x18000575c  mov     rcx, [rdi+8]; this
0x180005760  call    ?StopCollectingAdaptationData@CSREngine@@AEAAXXZ; CSREngine::StopCollectingAdaptationData(void)
0x180005765  lea     rcx, [rdi+38h]; this
0x180005769  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x18000576e  lea     r13, [rdi+40h]
0x180005772  mov     rcx, r13; this
0x180005775  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x18000577a  lea     rcx, [rdi+48h]; this
0x18000577e  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x180005783  lea     rcx, [rdi+50h]; this
0x180005787  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x18000578c  mov     rax, [rsi+40h]
0x180005790  mov     rcx, [rax+208h]
0x180005797  add     rcx, 228h; this
0x18000579e  call    ?RelinquishAllClassifiers@CConfidence@@QEAAXXZ; CConfidence::RelinquishAllClassifiers(void)
0x1800057a3  mov     rcx, [rsi+58h]; this
0x1800057a7  call    ?UnloadAcousticModel@CMvw@@QEAAJXZ; CMvw::UnloadAcousticModel(void)
0x1800057ac  mov     ebx, eax
0x1800057ae  test    eax, eax
0x1800057b0  js      loc_180005E5D
0x1800057b6  mov     rax, [rdi+8]
0x1800057ba  mov     rcx, [rax+3A8h]; this
0x1800057c1  test    rcx, rcx
0x1800057c4  jz      short loc_1800057D6
0x1800057c6  call    ??_GCPhoneConfusionMatrix@@QEAAPEAXI@Z; CPhoneConfusionMatrix::`scalar deleting destructor'(uint)
0x1800057cb  mov     rax, [rdi+8]
0x1800057cf  mov     [rax+3A8h], r15
0x1800057d6  mov     r14d, r15d
0x1800057d9  cmp     [rdi+1Ch], r15d
0x1800057dd  jle     short loc_180005825
0x1800057df  movsxd  rax, r14d
0x1800057e2  lea     rbx, [rax+rax*2]
0x1800057e6  lea     rcx, [rdi+60h]
0x1800057ea  lea     rcx, [rcx+rbx*8]; this
0x1800057ee  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x1800057f3  lea     rcx, [rdi+68h]
0x1800057f7  lea     rcx, [rcx+rbx*8]; this
0x1800057fb  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x180005800  mov     edx, r14d; int
0x180005803  lea     rcx, [rsi+60h]; this
0x180005807  call    ?GetMvwObject@CAMCollection@@QEAAPEAVCMvw@@H@Z; CAMCollection::GetMvwObject(int)
0x18000580c  test    rax, rax
0x18000580f  jz      short loc_180005819
0x180005811  mov     rcx, rax; this
0x180005814  call    ?UnloadAcousticModel@CMvw@@QEAAJXZ; CMvw::UnloadAcousticModel(void)
0x180005819  inc     r14d
0x18000581c  cmp     r14d, [rdi+1Ch]
0x180005820  jl      short loc_1800057DF
0x180005822  xor     r15d, r15d
0x180005825  mov     [rdi+1Ch], r15d
0x180005829  mov     [rdi+58h], r12b
0x18000582d  lea     rcx, [rdi+28h]; this
0x180005831  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x180005836  lea     r14, [rdi+30h]
0x18000583a  mov     rcx, r14; this
0x18000583d  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x180005842  movzx   eax, byte ptr [rdi+20h]
0x180005846  lea     r8, [rdi+10h]; unsigned int *
0x18000584a  mov     dword ptr [rsp+310h+var_2E8], eax; int
0x18000584e  mov     [rsp+310h+var_2F0], r14; unsigned __int16 **
0x180005853  lea     r9, [rdi+28h]; unsigned __int16 **
0x180005857  mov     edx, [rdi+24h]; unsigned int
0x18000585a  mov     rcx, rdi; this
0x18000585d  call    ?DetermineBaselineModel@CAcousticModel@@AEAAJKPEAKPEAPEAG1H@Z; CAcousticModel::DetermineBaselineModel(ulong,ulong *,ushort * *,ushort * *,int)
0x180005862  mov     ebx, eax
0x180005864  xor     r12d, r12d
0x180005867  test    eax, eax
0x180005869  js      loc_180005E5D
0x18000586f  mov     r15b, 1
0x180005872  mov     r9, [r14]
0x180005875  lea     r8, aSAm; "%s.am"
0x18000587c  mov     edx, 105h; unsigned __int64
0x180005881  lea     rcx, [rbp+210h+ExistingFileName]; unsigned __int16 *
0x180005885  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000588a  mov     rax, [rdi+8]
0x18000588e  cmp     [rax+36Ch], r12d
0x180005895  jnz     loc_180005ADE
0x18000589b  cmp     [rdi+58h], r12b
0x18000589f  setz    r8b; bool
0x1800058a3  lea     r9, [rsp+310h+lpFileName]; unsigned __int16 **
0x1800058a8  lea     rdx, aAm; "am"
0x1800058af  mov     rcx, rdi; this
0x1800058b2  call    ?GetAMFileName@CAcousticModel@@AEAAJPEBG_NPEAPEAG@Z; CAcousticModel::GetAMFileName(ushort const *,bool,ushort * *)
0x1800058b7  mov     ebx, eax
0x1800058b9  test    eax, eax
0x1800058bb  js      loc_180005E5D
0x1800058c1  cmp     eax, 1
0x1800058c4  jz      loc_180005967
0x1800058ca  mov     [rdi+58h], r12b
0x1800058ce  mov     rbx, [rsp+310h+lpFileName]
0x1800058d3  xorps   xmm0, xmm0
0x1800058d6  movups  [rbp+210h+Buf2], xmm0
0x1800058da  xorps   xmm1, xmm1
0x1800058dd  movups  [rbp+210h+Buf1], xmm1
0x1800058e1  lea     rdx, [rbp+210h+Buf2]; struct _GUID *
0x1800058e5  lea     rcx, [rbp+210h+ExistingFileName]; lpFileName
0x1800058e9  call    ?GetAMFileID@@YAJPEBGPEAU_GUID@@@Z; GetAMFileID(ushort const *,_GUID *)
0x1800058ee  test    eax, eax
0x1800058f0  jnz     short loc_18000591D
0x1800058f2  lea     rdx, [rbp+210h+Buf1]; struct _GUID *
0x1800058f6  mov     rcx, rbx; lpFileName
0x1800058f9  call    ?GetAMFileID@@YAJPEBGPEAU_GUID@@@Z; GetAMFileID(ushort const *,_GUID *)
0x1800058fe  test    eax, eax
0x180005900  jnz     short loc_18000591D
0x180005902  lea     r8d, [r12+10h]; Size
0x180005907  lea     rdx, [rbp+210h+Buf2]; Buf2
0x18000590b  lea     rcx, [rbp+210h+Buf1]; Buf1
0x18000590f  call    memcmp_0
0x180005914  test    eax, eax
0x180005916  jnz     short loc_18000591D
0x180005918  mov     r15b, r12b
0x18000591b  jmp     short loc_180005967
0x18000591d  mov     rcx, [rsi+10h]
0x180005921  mov     rax, [rcx]
0x180005924  mov     [rsp+310h+var_2B8], r12d
0x180005929  mov     [rsp+310h+var_2C0], r12d
0x18000592e  mov     [rsp+310h+var_2C8], r12d
0x180005933  mov     [rsp+310h+var_2D0], r12d
0x180005938  mov     [rsp+310h+var_2D8], r12d
0x18000593d  mov     [rsp+310h+var_2E0], r12d
0x180005942  mov     dword ptr [rsp+310h+var_2E8], r12d
0x180005947  mov     dword ptr [rsp+310h+var_2F0], r12d
0x18000594c  mov     edx, 857h
0x180005951  mov     r9d, 4
0x180005957  lea     r8d, [r9-2]
0x18000595b  mov     rax, [rax+80h]
0x180005962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005967  cmp     [rdi+58h], r12b
0x18000596b  setz    r8b; bool
0x18000596f  lea     r14, [rdi+38h]
0x180005973  mov     r9, r14; unsigned __int16 **
0x180005976  lea     rdx, aFpr; "fpr"
0x18000597d  mov     rcx, rdi; this
0x180005980  call    ?GetAMFileName@CAcousticModel@@AEAAJPEBG_NPEAPEAG@Z; CAcousticModel::GetAMFileName(ushort const *,bool,ushort * *)
0x180005985  mov     ebx, eax
0x180005987  test    eax, eax
0x180005989  js      loc_180005E5D
0x18000598f  lea     rcx, [rsi+270h]; this
0x180005996  lea     r8, [rsp+310h+var_2A0]; bool *
0x18000599b  lea     rdx, aBackupprofile; "backupprofile"
0x1800059a2  call    ?GetBool@CArgParser@@QEAA_NPEBDPEA_N@Z; CArgParser::GetBool(char const *,bool *)
0x1800059a7  cmp     [rsp+310h+var_2A0], r12b
0x1800059ac  jz      short loc_1800059F7
0x1800059ae  cmp     [rdi+58h], r12b
0x1800059b2  setz    r8b; bool
0x1800059b6  lea     r9, [rbp+210h+var_290]; unsigned __int16 **
0x1800059ba  lea     rdx, aAmBak; "am_bak"
0x1800059c1  mov     rcx, rdi; this
0x1800059c4  call    ?GetAMFileName@CAcousticModel@@AEAAJPEBG_NPEAPEAG@Z; CAcousticModel::GetAMFileName(ushort const *,bool,ushort * *)
0x1800059c9  mov     ebx, eax
0x1800059cb  test    eax, eax
0x1800059cd  js      loc_180005E5D
0x1800059d3  cmp     [rdi+58h], r12b
0x1800059d7  setz    r8b; bool
0x1800059db  mov     r9, r13; unsigned __int16 **
0x1800059de  lea     rdx, aFprBak; "fpr_bak"
0x1800059e5  mov     rcx, rdi; this
0x1800059e8  call    ?GetAMFileName@CAcousticModel@@AEAAJPEBG_NPEAPEAG@Z; CAcousticModel::GetAMFileName(ushort const *,bool,ushort * *)
0x1800059ed  mov     ebx, eax
0x1800059ef  test    eax, eax
0x1800059f1  js      loc_180005E5D
0x1800059f7  test    r15b, r15b
0x1800059fa  jnz     loc_180005AE2
0x180005a00  mov     rax, [rbp+210h+var_290]
0x180005a04  lea     rcx, [rbp+210h+ExistingFileName]
0x180005a08  mov     [rsp+310h+var_2E8], rcx; unsigned __int16 *
0x180005a0d  mov     [rsp+310h+var_2F0], rax; unsigned __int16 *
0x180005a12  mov     r9b, [rdi+58h]; bool
0x180005a16  mov     r8, [rsp+310h+lpFileName]; unsigned __int16 *
0x180005a1b  mov     rdx, rsi; struct CEngine *
0x180005a1e  mov     rcx, [rsi+58h]; this
0x180005a22  call    ?LoadAcousticModel@CMvw@@QEAAJPEAVCEngine@@PEBG_N11@Z; CMvw::LoadAcousticModel(CEngine *,ushort const *,bool,ushort const *,ushort const *)
0x180005a27  test    eax, eax
0x180005a29  jns     short loc_180005A83
0x180005a2b  mov     rcx, [rsi+10h]
0x180005a2f  mov     rax, [rcx]
0x180005a32  mov     [rsp+310h+var_2B8], r12d
0x180005a37  mov     [rsp+310h+var_2C0], r12d
0x180005a3c  mov     [rsp+310h+var_2C8], r12d
0x180005a41  mov     [rsp+310h+var_2D0], r12d
0x180005a46  mov     [rsp+310h+var_2D8], r12d
0x180005a4b  mov     [rsp+310h+var_2E0], r12d
0x180005a50  mov     dword ptr [rsp+310h+var_2E8], r12d
0x180005a55  mov     dword ptr [rsp+310h+var_2F0], r12d
0x180005a5a  mov     edx, 857h
0x180005a5f  mov     r9d, 4
0x180005a65  lea     r8d, [r9-2]
0x180005a69  mov     rax, [rax+80h]
0x180005a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a75  mov     rcx, [rsi+58h]; this
0x180005a79  call    ?UnloadAcousticModel@CMvw@@QEAAJXZ; CMvw::UnloadAcousticModel(void)
0x180005a7e  mov     r15b, 1
0x180005a81  jmp     short loc_180005AE2
0x180005a83  cmp     eax, 1
0x180005a86  jnz     loc_180005BA9
0x180005a8c  mov     rcx, [rsi+10h]
0x180005a90  mov     rax, [rcx]
0x180005a93  mov     [rsp+310h+var_2B8], r12d
0x180005a98  mov     [rsp+310h+var_2C0], r12d
0x180005a9d  mov     [rsp+310h+var_2C8], r12d
0x180005aa2  mov     [rsp+310h+var_2D0], r12d
0x180005aa7  mov     [rsp+310h+var_2D8], r12d
0x180005aac  mov     [rsp+310h+var_2E0], r12d
0x180005ab1  mov     dword ptr [rsp+310h+var_2E8], r12d
0x180005ab6  mov     dword ptr [rsp+310h+var_2F0], 1
0x180005abe  mov     edx, 857h
0x180005ac3  mov     r9d, 4
0x180005ac9  lea     r8d, [r9-2]
0x180005acd  mov     rax, [rax+80h]
0x180005ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ad9  jmp     loc_180005BA9
0x180005ade  lea     r14, [rdi+38h]
0x180005ae2  cmp     [rdi+58h], r12b
0x180005ae6  jnz     loc_180005C48
0x180005aec  mov     rax, [rdi+8]
0x180005af0  cmp     [rax+36Ch], r12d
0x180005af7  jnz     loc_180005C48
0x180005afd  mov     rcx, [rsp+310h+lpFileName]; lpFileName
0x180005b02  call    cs:__imp_DeleteFileW
0x180005b08  mov     rbx, [rsp+310h+lpFileName]
0x180005b0d  xor     r8d, r8d; bFailIfExists
0x180005b10  mov     rdx, rbx; lpNewFileName
0x180005b13  lea     rcx, [rbp+210h+ExistingFileName]; lpExistingFileName
0x180005b17  call    cs:__imp_CopyFileW
0x180005b1d  test    eax, eax
0x180005b1f  jz      short loc_180005B33
0x180005b21  mov     edx, 80h; dwFileAttributes
0x180005b26  mov     rcx, rbx; lpFileName
0x180005b29  call    cs:__imp_SetFileAttributesW
0x180005b2f  test    eax, eax
0x180005b31  jnz     short loc_180005B42
0x180005b33  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180005b38  mov     ebx, eax
0x180005b3a  test    eax, eax
0x180005b3c  js      loc_180005E5D
0x180005b42  mov     rcx, [r14]; lpFileName
0x180005b45  test    rcx, rcx
0x180005b48  jz      short loc_180005B50
0x180005b4a  call    cs:__imp_DeleteFileW
0x180005b50  mov     rcx, [r13+0]; lpFileName
0x180005b54  test    rcx, rcx
0x180005b57  jz      short loc_180005B5F
0x180005b59  call    cs:__imp_DeleteFileW
0x180005b5f  mov     rax, [rbp+210h+var_290]
0x180005b63  test    rax, rax
0x180005b66  jz      short loc_180005B75
0x180005b68  mov     rcx, rax; lpFileName
0x180005b6b  call    cs:__imp_DeleteFileW
0x180005b71  mov     rax, [rbp+210h+var_290]
0x180005b75  mov     r9b, [rdi+58h]; bool
0x180005b79  lea     rdx, [rbp+210h+ExistingFileName]
0x180005b7d  test    r9b, r9b
0x180005b80  cmovnz  rdx, r12
0x180005b84  mov     [rsp+310h+var_2E8], rdx; unsigned __int16 *
0x180005b89  mov     [rsp+310h+var_2F0], rax; unsigned __int16 *
0x180005b8e  mov     r8, [rsp+310h+lpFileName]; unsigned __int16 *
0x180005b93  mov     rdx, rsi; struct CEngine *
0x180005b96  mov     rcx, [rsi+58h]; this
0x180005b9a  call    ?LoadAcousticModel@CMvw@@QEAAJPEAVCEngine@@PEBG_N11@Z; CMvw::LoadAcousticModel(CEngine *,ushort const *,bool,ushort const *,ushort const *)
0x180005b9f  mov     ebx, eax
0x180005ba1  test    eax, eax
0x180005ba3  js      loc_180005E5D
0x180005ba9  mov     rdx, [rsi+58h]
0x180005bad  mov     rdx, [rdx+90h]; struct CWFSTNetwork *
0x180005bb4  mov     rcx, [rsi+40h]; this
0x180005bb8  call    ?search_init_wfst_network@CDecoder@@QEAAJPEAVCWFSTNetwork@@@Z; CDecoder::search_init_wfst_network(CWFSTNetwork *)
0x180005bbd  mov     ebx, eax
0x180005bbf  test    eax, eax
0x180005bc1  js      loc_180005E5D
0x180005bc7  mov     rax, [rsi+58h]
0x180005bcb  cmp     [rax+3A0h], r12d
0x180005bd2  jz      short loc_180005BE7
0x180005bd4  mov     rcx, [rsi+40h]; this
0x180005bd8  call    ?search_init_hlda_transform@CDecoder@@QEAAJXZ; CDecoder::search_init_hlda_transform(void)
0x180005bdd  mov     ebx, eax
0x180005bdf  test    eax, eax
  ... truncated ...
```
