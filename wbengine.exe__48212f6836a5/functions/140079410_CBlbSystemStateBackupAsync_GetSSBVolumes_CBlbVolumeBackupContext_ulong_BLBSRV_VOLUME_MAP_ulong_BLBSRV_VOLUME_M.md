# CBlbSystemStateBackupAsync::GetSSBVolumes(CBlbVolumeBackupContext *,ulong,_BLBSRV_VOLUME_MAP *,ulong,_BLBSRV_VOLUME_MAP * *,ulong *)

- ea: `0x140079410`
- end: `0x14007993b`
- name: `?GetSSBVolumes@CBlbSystemStateBackupAsync@@QEAAJPEAVCBlbVolumeBackupContext@@KPEAU_BLBSRV_VOLUME_MAP@@KPEAPEAU3@PEAK@Z`
- size: `1323`
- prototype: `__int64 __fastcall(CBlbSystemStateBackupAsync *__hidden this, struct CBlbVolumeBackupContext *, unsigned int, struct _BLBSRV_VOLUME_MAP *, unsigned int, struct _BLBSRV_VOLUME_MAP **, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x140019620`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000be04`
- `0x14000cbcc`
- `0x140014260`
- `0x1400278a4`
- `0x140079410`
- `0x1400889f0`
- `0x140088d0c`
- `0x14008acf4`
- `0x140107d30`
- `0x1401218b8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140079588`
- `ole32!CoTaskMemFree` at `0x1400796e7`
- `ole32!CoTaskMemFree` at `0x140079713`
- `ole32!CoTaskMemFree` at `0x140079836`
- `ole32!CoTaskMemFree` at `0x14007984e`
- `ole32!CoTaskMemFree` at `0x140079867`
- `ole32!CoTaskMemFree` at `0x140079884`
- `ole32!CoTaskMemFree` at `0x140079892`
- `ole32!CoTaskMemFree` at `0x1400798a1`
- `ole32!CoTaskMemFree` at `0x1400798c1`
- `ole32!CoTaskMemFree` at `0x140079588`
- `ole32!CoTaskMemFree` at `0x1400796e7`
- `ole32!CoTaskMemFree` at `0x140079713`
- `ole32!CoTaskMemFree` at `0x140079836`
- `ole32!CoTaskMemFree` at `0x14007984e`
- `ole32!CoTaskMemFree` at `0x140079867`
- `ole32!CoTaskMemFree` at `0x140079884`
- `ole32!CoTaskMemFree` at `0x140079892`
- `ole32!CoTaskMemFree` at `0x1400798a1`
- `ole32!CoTaskMemFree` at `0x1400798c1`
- `OLEAUT32!__imp_SysFreeString` at `0x140079664`
- `OLEAUT32!__imp_SysFreeString` at `0x140079664`

## string_xrefs

- `0x1400794ad`: `base\stor\blb\engine\service\systemstatebackup.cpp`
- `0x1400794c9`: `base\stor\blb\engine\service\systemstatebackup.cpp`
- `0x1400794e6`: `base\stor\blb\engine\service\systemstatebackup.cpp`
- `0x140079503`: `base\stor\blb\engine\service\systemstatebackup.cpp`
- `0x140079524`: `base\stor\blb\engine\service\systemstatebackup.cpp`
- `0x140079545`: `base\stor\blb\engine\service\systemstatebackup.cpp`
- `0x140079680`: `base\stor\blb\engine\service\systemstatebackup.cpp`
- `0x1400797fd`: `base\stor\blb\engine\service\systemstatebackup.cpp`

## pseudocode

```c
__int64 __fastcall CBlbSystemStateBackupAsync::GetSSBVolumes(
        CBlbSystemStateBackupAsync *this,
        struct CBlbVolumeBackupContext *a2,
        unsigned int a3,
        OLECHAR *a4,
        unsigned int a5,
        struct _BLBSRV_VOLUME_MAP **a6,
        unsigned int *a7)
{
  struct CBlbVolumeBackupContext *v9; // r15
  wchar_t *v10; // rbx
  unsigned __int16 *v11; // r13
  wchar_t *v12; // r14
  unsigned int v13; // r12d
  struct _BLBSRV_VOLUME_MAP **v14; // rdi
  unsigned int *v15; // rsi
  unsigned int v16; // edi
  unsigned int v17; // esi
  __int64 v18; // rsi
  char *v19; // r15
  int OriginalAccessPath; // ebx
  unsigned int v21; // edx
  wchar_t *v22; // rsi
  PVOID *v23; // rcx
  ATL::CComBSTR *v24; // rax
  char v25; // di
  int v26; // eax
  struct _BLBSRV_VOLUME_MAP *v27; // rdi
  int v28; // eax
  unsigned int i; // r15d
  CBlbVolumeBackupContext *v30; // rsi
  unsigned __int16 **v31; // rsi
  const unsigned __int16 *v32; // rcx
  unsigned int v33; // r15d
  __int64 v34; // r14
  void *v35; // rcx
  void *v36; // rcx
  void *v37; // rcx
  unsigned int v39; // [rsp+34h] [rbp-44h] BYREF
  wchar_t *String2; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int16 *v41; // [rsp+40h] [rbp-38h] BYREF
  wchar_t *String1; // [rsp+48h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-28h] BYREF
  struct _GUID v44; // [rsp+60h] [rbp-18h] BYREF
  CBlbSystemStateBackupAsync *v45; // [rsp+C0h] [rbp+48h] BYREF
  struct CBlbVolumeBackupContext *v46; // [rsp+C8h] [rbp+50h]
  unsigned int v47; // [rsp+D0h] [rbp+58h]
  BSTR bstrString; // [rsp+D8h] [rbp+60h] BYREF

  bstrString = a4;
  v47 = a3;
  v46 = a2;
  v45 = this;
  v9 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_1e8aac75371c3ff1f24a3207e3364e1d_Traceguids);
  }
  v10 = 0;
  pv = 0;
  v11 = 0;
  String2 = 0;
  v12 = 0;
  v41 = 0;
  v13 = 0;
  String1 = 0;
  v39 = 0;
  if ( !v9 )
    BlbAssert("base\\stor\\blb\\engine\\service\\systemstatebackup.cpp", 0x560u, "rgVolumeContext");
  if ( !a3 )
    BlbAssert("base\\stor\\blb\\engine\\service\\systemstatebackup.cpp", 0x561u, "cVolumeContext");
  if ( !a4 )
    BlbAssert("base\\stor\\blb\\engine\\service\\systemstatebackup.cpp", 0x562u, "rgVolumeMap");
  if ( !a5 )
    BlbAssert("base\\stor\\blb\\engine\\service\\systemstatebackup.cpp", 0x563u, "cVolumeMap");
  v14 = a6;
  if ( !a6 )
    BlbAssert("base\\stor\\blb\\engine\\service\\systemstatebackup.cpp", 0x564u, "prgVolumeSSB");
  v15 = a7;
  if ( !a7 )
    BlbAssert("base\\stor\\blb\\engine\\service\\systemstatebackup.cpp", 0x565u, "pcVolumeSSB");
  *v14 = 0;
  v16 = 0;
  *v15 = 0;
  while ( 1 )
  {
    v17 = v47;
    if ( v16 >= v47 )
    {
      if ( !v13 )
        BlbAssert("base\\stor\\blb\\engine\\service\\systemstatebackup.cpp", 0x596u, "cVolumeSSB");
      v26 = BlbutilMemalloc(&pv, v13, 0x18u);
      v27 = (struct _BLBSRV_VOLUME_MAP *)pv;
      OriginalAccessPath = v26;
      if ( v26 >= 0 )
      {
        v28 = 0;
        LODWORD(v45) = 0;
        for ( i = 0; i < v17; ++i )
        {
          v30 = (struct CBlbVolumeBackupContext *)((char *)v46 + 368 * i);
          if ( (*((_BYTE *)v30 + 84) & 0x20) == 0 || *((_DWORD *)v30 + 5) == 12 )
          {
            v28 = (int)v45;
          }
          else
          {
            if ( v11 )
            {
              CoTaskMemFree(v11);
              v41 = 0;
            }
            OriginalAccessPath = CBlbVolumeBackupContext::GetOriginalAccessPath(v30, &v41);
            if ( OriginalAccessPath < 0 )
            {
              v11 = v41;
              goto LABEL_59;
            }
            if ( v12 )
            {
              CoTaskMemFree(v12);
              String1 = 0;
            }
            v11 = v41;
            OriginalAccessPath = BlbutilSlashTerminatePath(v41, (LPVOID *)&String1);
            if ( OriginalAccessPath < 0 )
              goto LABEL_59;
            v12 = String1;
            OriginalAccessPath = BlbFindVolumeMap(String1, (struct _BLBSRV_VOLUME_MAP *)bstrString, a5, &v39);
            if ( OriginalAccessPath < 0 )
              goto LABEL_59;
            v31 = (unsigned __int16 **)((char *)v27 + 24 * (unsigned int)v45);
            v32 = *(const unsigned __int16 **)&bstrString[12 * v39];
            pv = (LPVOID)(3LL * v39);
            OriginalAccessPath = BlbutilDuplicateString(v32, v31, 0);
            if ( OriginalAccessPath < 0 )
              goto LABEL_59;
            OriginalAccessPath = BlbutilDuplicateString(
                                   *(const unsigned __int16 **)&bstrString[4 * (_QWORD)pv + 4],
                                   v31 + 1,
                                   0);
            if ( OriginalAccessPath < 0 )
              goto LABEL_59;
            OriginalAccessPath = BlbutilDuplicateString(
                                   *(const unsigned __int16 **)&bstrString[4 * (_QWORD)pv + 8],
                                   v31 + 2,
                                   0);
            if ( OriginalAccessPath < 0 )
              goto LABEL_59;
            v28 = (_DWORD)v45 + 1;
            LODWORD(v45) = (_DWORD)v45 + 1;
          }
          v17 = v47;
        }
        if ( v28 != v13 )
          BlbAssert("base\\stor\\blb\\engine\\service\\systemstatebackup.cpp", 0x5D7u, "iVolumeSSB == cVolumeSSB");
        *a6 = v27;
        v27 = 0;
        *a7 = v13;
      }
LABEL_59:
      if ( v27 )
      {
        v33 = 0;
        if ( v13 )
        {
          v34 = 0;
          do
          {
            v35 = (void *)*((_QWORD *)v27 + 3 * v34);
            if ( v35 )
            {
              CoTaskMemFree(v35);
              *((_QWORD *)v27 + 3 * v34) = 0;
            }
            v36 = (void *)*((_QWORD *)v27 + 3 * v34 + 1);
            if ( v36 )
            {
              CoTaskMemFree(v36);
              *((_QWORD *)v27 + 3 * v34 + 1) = 0;
            }
            v37 = (void *)*((_QWORD *)v27 + 3 * v34 + 2);
            if ( v37 )
            {
              CoTaskMemFree(v37);
              *((_QWORD *)v27 + 3 * v34 + 2) = 0;
            }
            ++v33;
            ++v34;
          }
          while ( v33 < v13 );
        }
        CoTaskMemFree(v27);
      }
      if ( v11 )
        CoTaskMemFree(v11);
      if ( String1 )
        CoTaskMemFree(String1);
LABEL_74:
      v22 = String2;
LABEL_75:
      v23 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_76;
    }
    v18 = 368LL * v16;
    if ( (*((_BYTE *)v9 + v18 + 84) & 0x20) != 0 && *(_DWORD *)((char *)v9 + v18 + 20) != 12 )
      break;
LABEL_27:
    ++v16;
  }
  LOBYTE(v45) = 0;
  if ( v10 )
  {
    CoTaskMemFree(v10);
    String2 = 0;
  }
  v19 = (char *)v9 + v18;
  v44 = *(struct _GUID *)(v19 + 68);
  OriginalAccessPath = BlbutilGetVolumeNameFromId(&v44, &String2);
  if ( OriginalAccessPath < 0 )
    goto LABEL_74;
  v21 = *(_DWORD *)((char *)v46 + v18 + 84);
  v22 = String2;
  OriginalAccessPath = BlbIsVolumeNameValid(String2, v21, (unsigned __int8 *)&v45);
  if ( OriginalAccessPath < 0 )
    goto LABEL_75;
  if ( (_BYTE)v45 )
  {
    v9 = v46;
    ++v13;
    v10 = v22;
    goto LABEL_27;
  }
  OriginalAccessPath = -2139619303;
  v23 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    v25 = 0;
  }
  else
  {
    v24 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, (const struct _GUID *)(v19 + 68));
    v25 = 1;
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      51,
      (unsigned int)WPP_1e8aac75371c3ff1f24a3207e3364e1d_Traceguids,
      *(_QWORD *)v24,
      25);
    v23 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (v25 & 1) != 0 )
  {
    SysFreeString(bstrString);
    goto LABEL_75;
  }
LABEL_76:
  if ( v22 )
  {
    CoTaskMemFree(v22);
    v23 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( OriginalAccessPath >= 0 )
  {
LABEL_83:
    if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 1) != 0 && *((_BYTE *)v23 + 25) >= 4u )
      WPP_SF_(v23[2], 53, WPP_1e8aac75371c3ff1f24a3207e3364e1d_Traceguids);
  }
  else if ( v23 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v23 + 28) & 1) != 0 && *((_BYTE *)v23 + 25) >= 2u )
    {
      WPP_SF_d(v23[2], 52, WPP_1e8aac75371c3ff1f24a3207e3364e1d_Traceguids);
      v23 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_83;
  }
  return (unsigned int)OriginalAccessPath;
}

```

## disassembly

```asm
0x140079410  mov     rax, rsp
0x140079413  mov     [rax+20h], r9
0x140079417  mov     [rax+18h], r8d
0x14007941b  mov     [rax+10h], rdx
0x14007941f  mov     [rax+8], rcx
0x140079423  push    rbp
0x140079424  push    rbx
0x140079425  push    rsi
0x140079426  push    rdi
0x140079427  push    r12
0x140079429  push    r13
0x14007942b  push    r14
0x14007942d  push    r15
0x14007942f  mov     rbp, rsp
0x140079432  sub     rsp, 78h
0x140079436  mov     rdi, r9
0x140079439  mov     [rbp+var_48], 0
0x140079440  mov     esi, r8d
0x140079443  mov     r15, rdx
0x140079446  mov     rcx, cs:WPP_GLOBAL_Control
0x14007944d  lea     rax, WPP_GLOBAL_Control
0x140079454  cmp     rcx, rax
0x140079457  jz      short loc_14007947A
0x140079459  test    byte ptr [rcx+1Ch], 1
0x14007945d  jz      short loc_14007947A
0x14007945f  cmp     byte ptr [rcx+19h], 4
0x140079463  jb      short loc_14007947A
0x140079465  mov     rcx, [rcx+10h]
0x140079469  lea     r8, WPP_1e8aac75371c3ff1f24a3207e3364e1d_Traceguids
0x140079470  mov     edx, 32h ; '2'
0x140079475  call    WPP_SF_
0x14007947a  xor     ebx, ebx
0x14007947c  mov     [rbp+pv], 0
0x140079484  xor     r13d, r13d
0x140079487  mov     [rbp+String2], rbx
0x14007948b  xor     r14d, r14d
0x14007948e  mov     [rbp+var_38], r13
0x140079492  xor     r12d, r12d
0x140079495  mov     [rbp+String1], r14
0x140079499  mov     [rbp+var_44], ebx
0x14007949c  test    r15, r15
0x14007949f  jnz     short loc_1400794B9
0x1400794a1  lea     r8, aRgvolumecontex; "rgVolumeContext"
0x1400794a8  mov     edx, 560h; unsigned int
0x1400794ad  lea     rcx, aBaseStorBlbEng_37; "base\\stor\\blb\\engine\\service\\syste"...
0x1400794b4  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400794b9  test    esi, esi
0x1400794bb  jnz     short loc_1400794D5
0x1400794bd  lea     r8, aCvolumecontext; "cVolumeContext"
0x1400794c4  mov     edx, 561h; unsigned int
0x1400794c9  lea     rcx, aBaseStorBlbEng_37; "base\\stor\\blb\\engine\\service\\syste"...
0x1400794d0  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400794d5  test    rdi, rdi
0x1400794d8  jnz     short loc_1400794F2
0x1400794da  lea     r8, aRgvolumemap; "rgVolumeMap"
0x1400794e1  mov     edx, 562h; unsigned int
0x1400794e6  lea     rcx, aBaseStorBlbEng_37; "base\\stor\\blb\\engine\\service\\syste"...
0x1400794ed  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400794f2  cmp     [rbp+arg_20], ebx
0x1400794f5  jnz     short loc_14007950F
0x1400794f7  lea     r8, aCvolumemap; "cVolumeMap"
0x1400794fe  mov     edx, 563h; unsigned int
0x140079503  lea     rcx, aBaseStorBlbEng_37; "base\\stor\\blb\\engine\\service\\syste"...
0x14007950a  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14007950f  mov     rdi, [rbp+arg_28]
0x140079513  test    rdi, rdi
0x140079516  jnz     short loc_140079530
0x140079518  lea     r8, aPrgvolumessb; "prgVolumeSSB"
0x14007951f  mov     edx, 564h; unsigned int
0x140079524  lea     rcx, aBaseStorBlbEng_37; "base\\stor\\blb\\engine\\service\\syste"...
0x14007952b  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140079530  mov     rsi, [rbp+arg_30]
0x140079534  test    rsi, rsi
0x140079537  jnz     short loc_140079551
0x140079539  lea     r8, aPcvolumessb; "pcVolumeSSB"
0x140079540  mov     edx, 565h; unsigned int
0x140079545  lea     rcx, aBaseStorBlbEng_37; "base\\stor\\blb\\engine\\service\\syste"...
0x14007954c  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140079551  mov     [rdi], rbx
0x140079554  xor     edi, edi
0x140079556  mov     [rsi], ebx
0x140079558  mov     esi, [rbp+arg_10]
0x14007955b  cmp     edi, esi
0x14007955d  jnb     loc_14007966F
0x140079563  mov     eax, edi
0x140079565  imul    rsi, rax, 170h
0x14007956c  test    byte ptr [rsi+r15+54h], 20h
0x140079572  jz      short loc_1400795E8
0x140079574  cmp     dword ptr [rsi+r15+14h], 0Ch
0x14007957a  jz      short loc_1400795E8
0x14007957c  mov     byte ptr [rbp+arg_0], r13b
0x140079580  test    rbx, rbx
0x140079583  jz      short loc_140079592
0x140079585  mov     rcx, rbx; pv
0x140079588  call    cs:__imp_CoTaskMemFree
0x14007958e  mov     [rbp+String2], r13
0x140079592  add     r15, rsi
0x140079595  lea     rdx, [rbp+String2]; unsigned __int16 **
0x140079599  lea     rcx, [rbp+var_18]; struct _GUID *
0x14007959d  movups  xmm0, xmmword ptr [r15+44h]
0x1400795a2  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x1400795a7  call    ?BlbutilGetVolumeNameFromId@@YAJU_GUID@@PEAPEAG@Z; BlbutilGetVolumeNameFromId(_GUID,ushort * *)
0x1400795ac  mov     ebx, eax
0x1400795ae  test    eax, eax
0x1400795b0  js      loc_1400798A7
0x1400795b6  mov     rdx, [rbp+arg_8]
0x1400795ba  lea     r8, [rbp+arg_0]; unsigned __int8 *
0x1400795be  mov     edx, [rsi+rdx+54h]; unsigned int
0x1400795c2  mov     rsi, [rbp+String2]
0x1400795c6  mov     rcx, rsi; String2
0x1400795c9  call    ?BlbIsVolumeNameValid@@YAJPEAGKPEAE@Z; BlbIsVolumeNameValid(ushort *,ulong,uchar *)
0x1400795ce  mov     ebx, eax
0x1400795d0  test    eax, eax
0x1400795d2  js      loc_1400798AB
0x1400795d8  cmp     byte ptr [rbp+arg_0], r13b
0x1400795dc  jz      short loc_1400795EF
0x1400795de  mov     r15, [rbp+arg_8]
0x1400795e2  inc     r12d
0x1400795e5  mov     rbx, rsi
0x1400795e8  inc     edi
0x1400795ea  jmp     loc_140079558
0x1400795ef  mov     ebx, 80780019h
0x1400795f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400795fb  lea     r14, WPP_GLOBAL_Control
0x140079602  cmp     rcx, r14
0x140079605  jz      short loc_140079653
0x140079607  test    byte ptr [rcx+1Ch], 1
0x14007960b  jz      short loc_140079653
0x14007960d  cmp     byte ptr [rcx+19h], 2
0x140079611  jb      short loc_140079653
0x140079613  lea     rdx, [r15+44h]; struct _GUID *
0x140079617  lea     rcx, [rbp+bstrString]; this
0x14007961b  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x140079620  mov     rcx, cs:WPP_GLOBAL_Control
0x140079627  lea     r8, WPP_1e8aac75371c3ff1f24a3207e3364e1d_Traceguids
0x14007962e  mov     edi, 1
0x140079633  mov     [rsp+78h+var_58], 80780019h
0x14007963b  mov     r9, [rax]
0x14007963e  mov     rcx, [rcx+10h]
0x140079642  lea     edx, [rdi+32h]
0x140079645  call    WPP_SF_Sd
0x14007964a  mov     rcx, cs:WPP_GLOBAL_Control
0x140079651  jmp     short loc_140079656
0x140079653  mov     edi, r13d
0x140079656  test    dil, 1
0x14007965a  jz      loc_1400798B9
0x140079660  mov     rcx, [rbp+bstrString]; bstrString
0x140079664  call    cs:__imp_SysFreeString
0x14007966a  jmp     loc_1400798B2
0x14007966f  test    r12d, r12d
0x140079672  jnz     short loc_14007968C
0x140079674  lea     r8, aCvolumessb; "cVolumeSSB"
0x14007967b  mov     edx, 596h; unsigned int
0x140079680  lea     rcx, aBaseStorBlbEng_37; "base\\stor\\blb\\engine\\service\\syste"...
0x140079687  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14007968c  mov     r8d, 18h; unsigned int
0x140079692  lea     rcx, [rbp+pv]; void **
0x140079696  mov     edx, r12d; unsigned int
0x140079699  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x14007969e  mov     rdi, [rbp+pv]
0x1400796a2  mov     ebx, eax
0x1400796a4  test    eax, eax
0x1400796a6  js      loc_140079819
0x1400796ac  xor     eax, eax
0x1400796ae  mov     dword ptr [rbp+arg_0], eax
0x1400796b1  xor     r15d, r15d
0x1400796b4  cmp     r15d, esi
0x1400796b7  jnb     loc_1400797EC
0x1400796bd  mov     eax, r15d
0x1400796c0  imul    rsi, rax, 170h
0x1400796c7  add     rsi, [rbp+arg_8]
0x1400796cb  test    byte ptr [rsi+54h], 20h
0x1400796cf  jz      loc_1400797D8
0x1400796d5  cmp     dword ptr [rsi+14h], 0Ch
0x1400796d9  jz      loc_1400797D8
0x1400796df  test    r13, r13
0x1400796e2  jz      short loc_1400796F5
0x1400796e4  mov     rcx, r13; pv
0x1400796e7  call    cs:__imp_CoTaskMemFree
0x1400796ed  mov     [rbp+var_38], 0
0x1400796f5  lea     rdx, [rbp+var_38]; unsigned __int16 **
0x1400796f9  mov     rcx, rsi; this
0x1400796fc  call    ?GetOriginalAccessPath@CBlbVolumeBackupContext@@QEAAJPEAPEAG@Z; CBlbVolumeBackupContext::GetOriginalAccessPath(ushort * *)
0x140079701  mov     ebx, eax
0x140079703  test    eax, eax
0x140079705  js      loc_1400797E6
0x14007970b  test    r14, r14
0x14007970e  jz      short loc_140079721
0x140079710  mov     rcx, r14; pv
0x140079713  call    cs:__imp_CoTaskMemFree
0x140079719  mov     [rbp+String1], 0
0x140079721  mov     r13, [rbp+var_38]
0x140079725  lea     rdx, [rbp+String1]; unsigned __int16 **
0x140079729  mov     rcx, r13; unsigned __int16 *
0x14007972c  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x140079731  mov     ebx, eax
0x140079733  test    eax, eax
0x140079735  js      loc_140079819
0x14007973b  mov     r14, [rbp+String1]
0x14007973f  lea     r9, [rbp+var_44]; unsigned int *
0x140079743  mov     r8d, [rbp+arg_20]; unsigned int
0x140079747  mov     rcx, r14; String1
0x14007974a  mov     rdx, [rbp+bstrString]; struct _BLBSRV_VOLUME_MAP *
0x14007974e  call    ?BlbFindVolumeMap@@YAJPEBGPEAU_BLBSRV_VOLUME_MAP@@KPEAK@Z; BlbFindVolumeMap(ushort const *,_BLBSRV_VOLUME_MAP *,ulong,ulong *)
0x140079753  mov     ebx, eax
0x140079755  test    eax, eax
0x140079757  js      loc_140079819
0x14007975d  mov     eax, dword ptr [rbp+arg_0]
0x140079760  xor     r8d, r8d; unsigned __int64
0x140079763  lea     rcx, [rax+rax*2]
0x140079767  mov     eax, [rbp+var_44]
0x14007976a  lea     rsi, [rdi+rcx*8]
0x14007976e  mov     rcx, [rbp+bstrString]
0x140079772  mov     rdx, rsi; unsigned __int16 **
0x140079775  lea     rax, [rax+rax*2]
0x140079779  mov     rcx, [rcx+rax*8]; unsigned __int16 *
0x14007977d  mov     [rbp+pv], rax
0x140079781  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x140079786  mov     ebx, eax
0x140079788  test    eax, eax
0x14007978a  js      loc_140079819
0x140079790  mov     rax, [rbp+bstrString]
0x140079794  lea     rdx, [rsi+8]; unsigned __int16 **
0x140079798  mov     rcx, [rbp+pv]
0x14007979c  xor     r8d, r8d; unsigned __int64
0x14007979f  mov     rcx, [rax+rcx*8+8]; unsigned __int16 *
0x1400797a4  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x1400797a9  mov     ebx, eax
0x1400797ab  test    eax, eax
0x1400797ad  js      short loc_140079819
0x1400797af  mov     rax, [rbp+pv]
0x1400797b3  lea     rdx, [rsi+10h]; unsigned __int16 **
0x1400797b7  mov     rcx, [rbp+bstrString]
0x1400797bb  xor     r8d, r8d; unsigned __int64
0x1400797be  mov     rcx, [rcx+rax*8+10h]; unsigned __int16 *
0x1400797c3  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x1400797c8  mov     ebx, eax
0x1400797ca  test    eax, eax
0x1400797cc  js      short loc_140079819
0x1400797ce  mov     eax, dword ptr [rbp+arg_0]
0x1400797d1  inc     eax
0x1400797d3  mov     dword ptr [rbp+arg_0], eax
0x1400797d6  jmp     short loc_1400797DB
0x1400797d8  mov     eax, dword ptr [rbp+arg_0]
0x1400797db  mov     esi, [rbp+arg_10]
0x1400797de  inc     r15d
0x1400797e1  jmp     loc_1400796B4
0x1400797e6  mov     r13, [rbp+var_38]
0x1400797ea  jmp     short loc_140079819
0x1400797ec  cmp     eax, r12d
0x1400797ef  jz      short loc_140079809
0x1400797f1  lea     r8, aIvolumessbCvol; "iVolumeSSB == cVolumeSSB"
0x1400797f8  mov     edx, 5D7h; unsigned int
0x1400797fd  lea     rcx, aBaseStorBlbEng_37; "base\\stor\\blb\\engine\\service\\syste"...
0x140079804  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140079809  mov     rax, [rbp+arg_28]
0x14007980d  mov     [rax], rdi
0x140079810  xor     edi, edi
0x140079812  mov     rax, [rbp+arg_30]
0x140079816  mov     [rax], r12d
0x140079819  test    rdi, rdi
0x14007981c  jz      short loc_14007988A
0x14007981e  xor     r15d, r15d
0x140079821  test    r12d, r12d
0x140079824  jz      short loc_140079881
0x140079826  xor     r14d, r14d
0x140079829  lea     rsi, [r14+r14*2]
0x14007982d  mov     rcx, [rdi+rsi*8]; pv
0x140079831  test    rcx, rcx
0x140079834  jz      short loc_140079844
0x140079836  call    cs:__imp_CoTaskMemFree
0x14007983c  mov     qword ptr [rdi+rsi*8], 0
0x140079844  mov     rcx, [rdi+rsi*8+8]; pv
0x140079849  test    rcx, rcx
0x14007984c  jz      short loc_14007985D
0x14007984e  call    cs:__imp_CoTaskMemFree
0x140079854  mov     qword ptr [rdi+rsi*8+8], 0
0x14007985d  mov     rcx, [rdi+rsi*8+10h]; pv
0x140079862  test    rcx, rcx
0x140079865  jz      short loc_140079876
0x140079867  call    cs:__imp_CoTaskMemFree
0x14007986d  mov     qword ptr [rdi+rsi*8+10h], 0
0x140079876  inc     r15d
0x140079879  inc     r14
0x14007987c  cmp     r15d, r12d
0x14007987f  jb      short loc_140079829
0x140079881  mov     rcx, rdi; pv
0x140079884  call    cs:__imp_CoTaskMemFree
0x14007988a  test    r13, r13
0x14007988d  jz      short loc_140079898
0x14007988f  mov     rcx, r13; pv
0x140079892  call    cs:__imp_CoTaskMemFree
0x140079898  mov     rcx, [rbp+String1]; pv
0x14007989c  test    rcx, rcx
0x14007989f  jz      short loc_1400798A7
0x1400798a1  call    cs:__imp_CoTaskMemFree
0x1400798a7  mov     rsi, [rbp+String2]
0x1400798ab  lea     r14, WPP_GLOBAL_Control
0x1400798b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400798b9  test    rsi, rsi
  ... truncated ...
```
