# CBlbRestoreAsync::InitializeExclusions(void)

- ea: `0x14005914c`
- end: `0x1400596d6`
- name: `?InitializeExclusions@CBlbRestoreAsync@@AEAAJXZ`
- size: `1418`
- prototype: `__int64 __fastcall(unsigned __int16 **this)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400563a0`

## callees

- `0x140006948`
- `0x14000bb24`
- `0x14000be04`
- `0x140014260`
- `0x1400142d8`
- `0x1400149e0`
- `0x140056300`
- `0x14005914c`
- `0x1400889f0`
- `0x14008ba2c`
- `0x1400d9278`
- `0x1400f2a28`
- `0x1400f2d74`
- `0x14010240c`
- `0x140102560`
- `0x14012458c`
- `0x140128d2c`
- `0x140128e78`
- `0x140128f80`
- `0x14012a330`
- `0x140137010`

## import_xrefs

- `KERNEL32!FindClose` at `0x14005964b`
- `KERNEL32!FindClose` at `0x14005964b`
- `ole32!CoTaskMemFree` at `0x14005927c`
- `ole32!CoTaskMemFree` at `0x1400595af`
- `ole32!CoTaskMemFree` at `0x1400595c0`
- `ole32!CoTaskMemFree` at `0x1400595fb`
- `ole32!CoTaskMemFree` at `0x14005960d`
- `ole32!CoTaskMemFree` at `0x14005961b`
- `ole32!CoTaskMemFree` at `0x140059629`
- `ole32!CoTaskMemFree` at `0x140059638`
- `ole32!CoTaskMemFree` at `0x140059659`
- `ole32!CoTaskMemFree` at `0x14005927c`
- `ole32!CoTaskMemFree` at `0x1400595af`
- `ole32!CoTaskMemFree` at `0x1400595c0`
- `ole32!CoTaskMemFree` at `0x1400595fb`
- `ole32!CoTaskMemFree` at `0x14005960d`
- `ole32!CoTaskMemFree` at `0x14005961b`
- `ole32!CoTaskMemFree` at `0x140059629`
- `ole32!CoTaskMemFree` at `0x140059638`
- `ole32!CoTaskMemFree` at `0x140059659`
- `OLEAUT32!__imp_SysFreeString` at `0x14005936d`
- `OLEAUT32!__imp_SysFreeString` at `0x140059499`
- `OLEAUT32!__imp_SysFreeString` at `0x14005936d`
- `OLEAUT32!__imp_SysFreeString` at `0x140059499`

## pseudocode

```c
__int64 __fastcall CBlbRestoreAsync::InitializeExclusions(unsigned __int16 **this)
{
  CBlbRestoreAsync *v1; // rsi
  unsigned __int16 *v2; // r12
  unsigned __int16 *v3; // rdi
  unsigned __int16 *v4; // r14
  __int64 ExclusionHandler; // rax
  struct IExclusionHandler *v6; // r13
  int appended; // ebx
  PVOID *v8; // rcx
  unsigned int i; // r15d
  __int64 v10; // rsi
  unsigned __int16 *v11; // rax
  unsigned int v12; // edx
  const unsigned __int16 *v13; // rcx
  int v14; // eax
  __int64 *v15; // rax
  unsigned int v16; // ebx
  UUID *v17; // r15
  unsigned __int16 *v18; // rsi
  int v19; // eax
  PVOID *v20; // rcx
  unsigned __int64 j; // rbx
  LPVOID pv; // [rsp+30h] [rbp-79h] BYREF
  union _LARGE_INTEGER v24; // [rsp+38h] [rbp-71h] BYREF
  unsigned __int16 *v25; // [rsp+40h] [rbp-69h] BYREF
  unsigned __int16 *v26; // [rsp+48h] [rbp-61h] BYREF
  HANDLE hFindFile; // [rsp+50h] [rbp-59h] BYREF
  unsigned __int16 *v28; // [rsp+58h] [rbp-51h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-49h] BYREF
  _QWORD v30[3]; // [rsp+68h] [rbp-41h] BYREF
  int v31; // [rsp+80h] [rbp-29h]
  __int128 v32; // [rsp+88h] [rbp-21h] BYREF
  int v33; // [rsp+98h] [rbp-11h]
  __int64 v34; // [rsp+A0h] [rbp-9h]
  int v35; // [rsp+A8h] [rbp-1h]
  __int128 v36[5]; // [rsp+B0h] [rbp+7h] BYREF
  BSTR v38; // [rsp+118h] [rbp+6Fh] BYREF
  unsigned __int16 *v39; // [rsp+120h] [rbp+77h] BYREF
  unsigned __int16 *v40; // [rsp+128h] [rbp+7Fh] BYREF

  v1 = (CBlbRestoreAsync *)this;
  LODWORD(v38) = 0;
  v28 = 0;
  v26 = 0;
  v24.QuadPart = 0;
  v2 = 0;
  v25 = 0;
  v3 = 0;
  v39 = 0;
  hFindFile = (HANDLE)-1LL;
  pv = 0;
  memset(v30, 0, sizeof(v30));
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v4 = 0;
  v40 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
  }
  ExclusionHandler = DsmFsCreateExclusionHandler();
  v6 = (struct IExclusionHandler *)ExclusionHandler;
  if ( !ExclusionHandler )
  {
    appended = -2147024882;
    goto LABEL_76;
  }
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)ExclusionHandler + 8LL))(ExclusionHandler, *((_QWORD *)v1 + 56));
  CExclusionHelper::Init((CExclusionHelper *)&v32, v6);
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  for ( i = 0; i < *((_DWORD *)v1 + 83); ++i )
  {
    if ( v4 )
    {
      CoTaskMemFree(v4);
      v4 = 0;
      v40 = 0;
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    v10 = 96LL * i;
    v11 = this[33];
    v12 = *(_DWORD *)&v11[v10 + 38];
    if ( (v12 & 1) == 0 )
    {
      v13 = *(const unsigned __int16 **)&v11[v10 + 68];
      if ( v13 )
        v14 = BlbutilDuplicateString(v13, &v40, 0);
      else
        v14 = BlbutilQueryVolumeName((struct _GUID *)&v11[v10 + 30], v12, &v40, 0);
      appended = v14;
      if ( v14 < 0 )
      {
        v4 = v40;
        goto LABEL_72;
      }
      v4 = v40;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        v16 = (unsigned int)v38;
      }
      else
      {
        v15 = (__int64 *)ATL::CComBSTR::CComBSTR(
                           (ATL::CComBSTR *)&bstrString,
                           (const struct _GUID *)&this[33][v10 + 40]);
        v16 = (unsigned int)v38 | 1;
        LODWORD(v38) = (unsigned int)v38 | 1;
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          112,
          (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
          (_DWORD)v4,
          *v15);
      }
      if ( (v16 & 1) != 0 )
      {
        LODWORD(v38) = v16 & 0xFFFFFFFE;
        SysFreeString(bstrString);
      }
      v36[0] = *(_OWORD *)&this[33][v10 + 40];
      (*(void (__fastcall **)(struct IExclusionHandler *, unsigned __int16 *, __int128 *))(*(_QWORD *)v6 + 16LL))(
        v6,
        v4,
        v36);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    v1 = (CBlbRestoreAsync *)this;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 4u )
    WPP_SF_(v8[2], 113, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
  v17 = (UUID *)((char *)v1 + 208);
  appended = BlbAppendRegistryExcludesFile(*((unsigned __int16 **)v1 + 25), (UUID *)v1 + 13, 0, &v28);
  v18 = v28;
  if ( appended >= 0 )
  {
    v24.QuadPart = 0;
    v19 = BlbReadFileFromTarget(v28, &v26, &v24);
    if ( v19 >= 0 )
    {
      for ( j = 0; j < 2; ++j )
      {
        ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v38, off_140139C50[j]);
        ATL::CAtlArray<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::Add(v30, &v38);
        SysFreeString(v38);
      }
      CExclusionHelper::AddRegistryExclusions(&v32, v26, v30);
    }
    else
    {
      v20 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_48;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
LABEL_44:
        if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 1) != 0 && *((_BYTE *)v20 + 25) >= 4u )
          WPP_SF_(v20[2], 115, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
LABEL_48:
        appended = BlbAppendWriterMetadataFile(this[25], v17, 0, 0, &v25);
        v2 = v25;
        if ( appended >= 0 )
        {
          appended = BlbFindFirstFile(v25, (LPVOID *)&v39, &hFindFile, 0);
          if ( appended >= 0 )
          {
            while ( 1 )
            {
              v3 = v39;
              if ( !v39 )
                break;
              v24.QuadPart = 0;
              appended = BlbReadFileFromTarget(v39, (unsigned __int16 **)&pv, &v24);
              if ( appended < 0 )
                goto LABEL_60;
              CExclusionHelper::AddWriterMetadataExclusions((CExclusionHelper *)&v32, (const unsigned __int16 *)pv);
              CoTaskMemFree(pv);
              pv = 0;
              CoTaskMemFree(v3);
              v39 = 0;
              appended = BlbFindNextFile(v2, hFindFile, (LPVOID *)&v39, 0);
              if ( appended < 0 )
                goto LABEL_54;
            }
            this[47] = (unsigned __int16 *)v6;
            v6 = 0;
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                116,
                (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
                (_DWORD)v2,
                appended);
            }
LABEL_54:
            v3 = v39;
          }
        }
        goto LABEL_60;
      }
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        114,
        (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
        (_DWORD)v18,
        v19);
    }
    v20 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_44;
  }
LABEL_60:
  if ( v18 )
    CoTaskMemFree(v18);
  if ( v26 )
    CoTaskMemFree(v26);
  if ( v2 )
    CoTaskMemFree(v2);
  if ( v3 )
    CoTaskMemFree(v3);
  if ( pv )
    CoTaskMemFree(pv);
  if ( hFindFile != (HANDLE)-1LL )
    FindClose(hFindFile);
LABEL_72:
  if ( v4 )
    CoTaskMemFree(v4);
  if ( v6 )
    (**(void (__fastcall ***)(struct IExclusionHandler *, __int64))v6)(v6, 1);
LABEL_76:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
  }
  CExclusionHelper::~CExclusionHelper((CExclusionHelper *)&v32);
  ATL::CAtlArray<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::~CAtlArray<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>(v30);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14005914c  mov     [rsp-8+arg_0], rcx
0x140059151  push    rbp
0x140059152  push    rbx
0x140059153  push    rsi
0x140059154  push    rdi
0x140059155  push    r12
0x140059157  push    r13
0x140059159  push    r14
0x14005915b  push    r15
0x14005915d  lea     rbp, [rsp-1Fh]
0x140059162  sub     rsp, 0C8h
0x140059169  mov     rsi, rcx
0x14005916c  xor     ebx, ebx
0x14005916e  mov     dword ptr [rbp+57h+arg_8], ebx
0x140059171  mov     [rbp+57h+var_A8], rbx
0x140059175  mov     [rbp+57h+var_B8], rbx
0x140059179  mov     qword ptr [rbp+57h+var_C8], rbx
0x14005917d  mov     r12d, ebx
0x140059180  mov     [rbp+57h+var_C0], rbx
0x140059184  mov     edi, ebx
0x140059186  mov     [rbp+57h+arg_10], rbx
0x14005918a  mov     [rbp+57h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x140059192  mov     [rbp+57h+pv], rbx
0x140059196  mov     [rbp+57h+var_98], rbx
0x14005919a  mov     [rbp+57h+var_90], rbx
0x14005919e  mov     [rbp+57h+var_88], rbx
0x1400591a2  mov     [rbp+57h+var_80], ebx
0x1400591a5  xorps   xmm0, xmm0
0x1400591a8  movdqu  [rbp+57h+var_78], xmm0
0x1400591ad  mov     [rbp+57h+var_68], ebx
0x1400591b0  mov     [rbp+57h+var_60], rbx
0x1400591b4  mov     [rbp+57h+var_58], ebx
0x1400591b7  mov     r14d, ebx
0x1400591ba  mov     [rbp+57h+arg_18], rbx
0x1400591be  lea     rax, WPP_GLOBAL_Control
0x1400591c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400591cc  cmp     rcx, rax
0x1400591cf  jz      short loc_1400591F0
0x1400591d1  test    byte ptr [rcx+1Ch], 1
0x1400591d5  jz      short loc_1400591F0
0x1400591d7  cmp     byte ptr [rcx+19h], 4
0x1400591db  jb      short loc_1400591F0
0x1400591dd  lea     edx, [rbx+6Eh]
0x1400591e0  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x1400591e7  mov     rcx, [rcx+10h]
0x1400591eb  call    WPP_SF_
0x1400591f0  call    DsmFsCreateExclusionHandler
0x1400591f5  mov     r13, rax
0x1400591f8  test    rax, rax
0x1400591fb  jnz     short loc_140059207
0x1400591fd  mov     ebx, 8007000Eh
0x140059202  jmp     loc_140059678
0x140059207  mov     rax, [rax]
0x14005920a  mov     rdx, [rsi+1C0h]
0x140059211  mov     rcx, r13
0x140059214  mov     rax, [rax+8]
0x140059218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005921d  mov     rdx, r13; struct IExclusionHandler *
0x140059220  lea     rcx, [rbp+57h+var_78]; this
0x140059224  call    ?Init@CExclusionHelper@@QEAAXPEAVIExclusionHandler@@@Z; CExclusionHelper::Init(IExclusionHandler *)
0x140059229  mov     rcx, cs:WPP_GLOBAL_Control
0x140059230  lea     rax, WPP_GLOBAL_Control
0x140059237  cmp     rcx, rax
0x14005923a  jz      short loc_140059264
0x14005923c  test    byte ptr [rcx+1Ch], 1
0x140059240  jz      short loc_140059264
0x140059242  cmp     byte ptr [rcx+19h], 4
0x140059246  jb      short loc_140059264
0x140059248  mov     edx, 6Fh ; 'o'
0x14005924d  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x140059254  mov     rcx, [rcx+10h]
0x140059258  call    WPP_SF_
0x14005925d  mov     rcx, cs:WPP_GLOBAL_Control
0x140059264  mov     r15d, ebx
0x140059267  cmp     r15d, [rsi+14Ch]
0x14005926e  jnb     loc_1400593BD
0x140059274  test    r14, r14
0x140059277  jz      short loc_140059290
0x140059279  mov     rcx, r14; pv
0x14005927c  call    cs:__imp_CoTaskMemFree
0x140059282  mov     r14, rbx
0x140059285  mov     [rbp+57h+arg_18], rbx
0x140059289  mov     rcx, cs:WPP_GLOBAL_Control
0x140059290  mov     eax, r15d
0x140059293  lea     rsi, [rax+rax*2]
0x140059297  shl     rsi, 6
0x14005929b  mov     rax, [rbp+57h+arg_0]
0x14005929f  mov     rax, [rax+108h]
0x1400592a6  mov     edx, [rsi+rax+4Ch]; unsigned int
0x1400592aa  test    dl, 1
0x1400592ad  jnz     loc_1400593A8
0x1400592b3  mov     rcx, [rsi+rax+88h]; unsigned __int16 *
0x1400592bb  test    rcx, rcx
0x1400592be  jnz     short loc_1400592D5
0x1400592c0  lea     rcx, [rax+3Ch]
0x1400592c4  add     rcx, rsi; struct _GUID *
0x1400592c7  xor     r9d, r9d; unsigned __int8
0x1400592ca  lea     r8, [rbp+57h+arg_18]; unsigned __int16 **
0x1400592ce  call    ?BlbutilQueryVolumeName@@YAJPEAU_GUID@@KPEAPEAGE@Z; BlbutilQueryVolumeName(_GUID *,ulong,ushort * *,uchar)
0x1400592d3  jmp     short loc_1400592E1
0x1400592d5  xor     r8d, r8d; unsigned __int64
0x1400592d8  lea     rdx, [rbp+57h+arg_18]; unsigned __int16 **
0x1400592dc  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x1400592e1  mov     ebx, eax
0x1400592e3  test    eax, eax
0x1400592e5  js      loc_1400593B4
0x1400592eb  mov     r14, [rbp+57h+arg_18]
0x1400592ef  mov     rax, cs:WPP_GLOBAL_Control
0x1400592f6  lea     rcx, WPP_GLOBAL_Control
0x1400592fd  cmp     rax, rcx
0x140059300  jz      short loc_14005935B
0x140059302  test    byte ptr [rax+1Ch], 1
0x140059306  jz      short loc_14005935B
0x140059308  cmp     byte ptr [rax+19h], 4
0x14005930c  jb      short loc_14005935B
0x14005930e  mov     rax, [rbp+57h+arg_0]
0x140059312  mov     rdx, [rax+108h]
0x140059319  add     rdx, 50h ; 'P'
0x14005931d  add     rdx, rsi; struct _GUID *
0x140059320  lea     rcx, [rbp+57h+bstrString]; this
0x140059324  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x140059329  mov     ebx, dword ptr [rbp+57h+arg_8]
0x14005932c  or      ebx, 1
0x14005932f  mov     dword ptr [rbp+57h+arg_8], ebx
0x140059332  mov     edx, 70h ; 'p'
0x140059337  mov     rax, [rax]
0x14005933a  mov     [rsp+100h+var_E0], rax
0x14005933f  mov     r9, r14
0x140059342  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x140059349  mov     rcx, cs:WPP_GLOBAL_Control
0x140059350  mov     rcx, [rcx+10h]
0x140059354  call    WPP_SF_SS
0x140059359  jmp     short loc_14005935E
0x14005935b  mov     ebx, dword ptr [rbp+57h+arg_8]
0x14005935e  test    bl, 1
0x140059361  jz      short loc_140059373
0x140059363  and     ebx, 0FFFFFFFEh
0x140059366  mov     dword ptr [rbp+57h+arg_8], ebx
0x140059369  mov     rcx, [rbp+57h+bstrString]; bstrString
0x14005936d  call    cs:__imp_SysFreeString
0x140059373  mov     rax, [rbp+57h+arg_0]
0x140059377  mov     rax, [rax+108h]
0x14005937e  movups  xmm0, xmmword ptr [rsi+rax+50h]
0x140059383  movdqu  [rbp+57h+var_50], xmm0
0x140059388  mov     rax, [r13+0]
0x14005938c  lea     r8, [rbp+57h+var_50]
0x140059390  mov     rdx, r14
0x140059393  mov     rcx, r13
0x140059396  mov     rax, [rax+10h]
0x14005939a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005939f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400593a6  xor     ebx, ebx
0x1400593a8  inc     r15d
0x1400593ab  mov     rsi, [rbp+57h+arg_0]
0x1400593af  jmp     loc_140059267
0x1400593b4  mov     r14, [rbp+57h+arg_18]
0x1400593b8  jmp     loc_140059651
0x1400593bd  lea     rax, WPP_GLOBAL_Control
0x1400593c4  cmp     rcx, rax
0x1400593c7  jz      short loc_1400593EA
0x1400593c9  test    byte ptr [rcx+1Ch], 1
0x1400593cd  jz      short loc_1400593EA
0x1400593cf  cmp     byte ptr [rcx+19h], 4
0x1400593d3  jb      short loc_1400593EA
0x1400593d5  mov     edx, 71h ; 'q'
0x1400593da  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x1400593e1  mov     rcx, [rcx+10h]
0x1400593e5  call    WPP_SF_
0x1400593ea  lea     r15, [rsi+0D0h]
0x1400593f1  lea     r9, [rbp+57h+var_A8]; unsigned __int16 **
0x1400593f5  xor     r8d, r8d; unsigned __int8
0x1400593f8  mov     rdx, r15; Uuid
0x1400593fb  mov     rcx, [rsi+0C8h]; unsigned __int16 *
0x140059402  call    ?BlbAppendRegistryExcludesFile@@YAJPEAGPEAU_GUID@@EPEAPEAG@Z; BlbAppendRegistryExcludesFile(ushort *,_GUID *,uchar,ushort * *)
0x140059407  mov     ebx, eax
0x140059409  mov     rsi, [rbp+57h+var_A8]
0x14005940d  test    eax, eax
0x14005940f  js      loc_1400595F3
0x140059415  mov     qword ptr [rbp+57h+var_C8], 0
0x14005941d  lea     r8, [rbp+57h+var_C8]; union _LARGE_INTEGER *
0x140059421  lea     rdx, [rbp+57h+var_B8]; unsigned __int16 **
0x140059425  mov     rcx, rsi; unsigned __int16 *
0x140059428  call    ?BlbReadFileFromTarget@@YAJPEAGPEAPEAGPEAT_LARGE_INTEGER@@@Z; BlbReadFileFromTarget(ushort *,ushort * *,_LARGE_INTEGER *)
0x14005942d  test    eax, eax
0x14005942f  jns     short loc_140059472
0x140059431  mov     rcx, cs:WPP_GLOBAL_Control
0x140059438  lea     rdx, WPP_GLOBAL_Control
0x14005943f  cmp     rcx, rdx
0x140059442  jz      loc_1400594ED
0x140059448  test    byte ptr [rcx+1Ch], 1
0x14005944c  jz      short loc_1400594C0
0x14005944e  cmp     byte ptr [rcx+19h], 3
0x140059452  jb      short loc_1400594C0
0x140059454  mov     edx, 72h ; 'r'
0x140059459  mov     dword ptr [rsp+100h+var_E0], eax
0x14005945d  mov     r9, rsi
0x140059460  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x140059467  mov     rcx, [rcx+10h]
0x14005946b  call    WPP_SF_Sd
0x140059470  jmp     short loc_1400594B9
0x140059472  xor     ebx, ebx
0x140059474  lea     rdx, off_140139C50; "VSS Default Provider"
0x14005947b  mov     rdx, [rdx+rbx*8]; unsigned __int16 *
0x14005947f  lea     rcx, [rbp+57h+arg_8]; this
0x140059483  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x140059488  lea     rdx, [rbp+57h+arg_8]
0x14005948c  lea     rcx, [rbp+57h+var_98]
0x140059490  call    ?Add@?$CAtlArray@VCComBSTR@ATL@@V?$CElementTraits@VCComBSTR@ATL@@@2@@ATL@@QEAA_KAEBVCComBSTR@2@@Z; ATL::CAtlArray<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>>::Add(ATL::CComBSTR const &)
0x140059495  mov     rcx, [rbp+57h+arg_8]; bstrString
0x140059499  call    cs:__imp_SysFreeString
0x14005949f  inc     rbx
0x1400594a2  cmp     rbx, 2
0x1400594a6  jb      short loc_140059474
0x1400594a8  lea     r8, [rbp+57h+var_98]
0x1400594ac  mov     rdx, [rbp+57h+var_B8]
0x1400594b0  lea     rcx, [rbp+57h+var_78]
0x1400594b4  call    ?AddRegistryExclusions@CExclusionHelper@@QEAAXPEBGAEBV?$CAtlArray@VCComBSTR@ATL@@V?$CElementTraits@VCComBSTR@ATL@@@2@@ATL@@@Z; CExclusionHelper::AddRegistryExclusions(ushort const *,ATL::CAtlArray<ATL::CComBSTR,ATL::CElementTraits<ATL::CComBSTR>> const &)
0x1400594b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400594c0  lea     rax, WPP_GLOBAL_Control
0x1400594c7  cmp     rcx, rax
0x1400594ca  jz      short loc_1400594ED
0x1400594cc  test    byte ptr [rcx+1Ch], 1
0x1400594d0  jz      short loc_1400594ED
0x1400594d2  cmp     byte ptr [rcx+19h], 4
0x1400594d6  jb      short loc_1400594ED
0x1400594d8  mov     edx, 73h ; 's'
0x1400594dd  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x1400594e4  mov     rcx, [rcx+10h]
0x1400594e8  call    WPP_SF_
0x1400594ed  lea     rax, [rbp+57h+var_C0]
0x1400594f1  mov     [rsp+100h+var_E0], rax; unsigned __int16 **
0x1400594f6  xor     r9d, r9d; unsigned __int8
0x1400594f9  xor     r8d, r8d; UUID *
0x1400594fc  mov     rdx, r15; Uuid
0x1400594ff  mov     r15, [rbp+57h+arg_0]
0x140059503  mov     rcx, [r15+0C8h]; unsigned __int16 *
0x14005950a  call    ?BlbAppendWriterMetadataFile@@YAJPEAGPEAU_GUID@@1EPEAPEAG@Z; BlbAppendWriterMetadataFile(ushort *,_GUID *,_GUID *,uchar,ushort * *)
0x14005950f  mov     ebx, eax
0x140059511  mov     r12, [rbp+57h+var_C0]
0x140059515  test    eax, eax
0x140059517  js      loc_1400595F3
0x14005951d  xor     r9d, r9d; struct _WIN32_FIND_DATAW **
0x140059520  lea     r8, [rbp+57h+hFindFile]; void **
0x140059524  lea     rdx, [rbp+57h+arg_10]; unsigned __int16 **
0x140059528  mov     rcx, r12; unsigned __int16 *
0x14005952b  call    ?BlbFindFirstFile@@YAJPEAGPEAPEAGPEAPEAXPEAPEAU_WIN32_FIND_DATAW@@@Z; BlbFindFirstFile(ushort *,ushort * *,void * *,_WIN32_FIND_DATAW * *)
0x140059530  mov     ebx, eax
0x140059532  test    eax, eax
0x140059534  jns     short loc_140059577
0x140059536  mov     rcx, cs:WPP_GLOBAL_Control
0x14005953d  lea     rax, WPP_GLOBAL_Control
0x140059544  cmp     rcx, rax
0x140059547  jz      short loc_140059571
0x140059549  test    byte ptr [rcx+1Ch], 1
0x14005954d  jz      short loc_140059571
0x14005954f  cmp     byte ptr [rcx+19h], 2
0x140059553  jb      short loc_140059571
0x140059555  mov     edx, 74h ; 't'
0x14005955a  mov     dword ptr [rsp+100h+var_E0], ebx
0x14005955e  mov     r9, r12
0x140059561  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x140059568  mov     rcx, [rcx+10h]
0x14005956c  call    WPP_SF_Sd
0x140059571  mov     rdi, [rbp+57h+arg_10]
0x140059575  jmp     short loc_1400595F3
0x140059577  mov     rdi, [rbp+57h+arg_10]
0x14005957b  test    rdi, rdi
0x14005957e  jz      short loc_1400595E9
0x140059580  mov     qword ptr [rbp+57h+var_C8], 0
0x140059588  lea     r8, [rbp+57h+var_C8]; union _LARGE_INTEGER *
0x14005958c  lea     rdx, [rbp+57h+pv]; unsigned __int16 **
0x140059590  mov     rcx, rdi; unsigned __int16 *
0x140059593  call    ?BlbReadFileFromTarget@@YAJPEAGPEAPEAGPEAT_LARGE_INTEGER@@@Z; BlbReadFileFromTarget(ushort *,ushort * *,_LARGE_INTEGER *)
0x140059598  mov     ebx, eax
0x14005959a  test    eax, eax
0x14005959c  js      short loc_1400595F3
0x14005959e  mov     rdx, [rbp+57h+pv]; unsigned __int16 *
0x1400595a2  lea     rcx, [rbp+57h+var_78]; this
0x1400595a6  call    ?AddWriterMetadataExclusions@CExclusionHelper@@QEAAXPEBG@Z; CExclusionHelper::AddWriterMetadataExclusions(ushort const *)
0x1400595ab  mov     rcx, [rbp+57h+pv]; pv
0x1400595af  call    cs:__imp_CoTaskMemFree
0x1400595b5  mov     [rbp+57h+pv], 0
0x1400595bd  mov     rcx, rdi; pv
0x1400595c0  call    cs:__imp_CoTaskMemFree
0x1400595c6  mov     [rbp+57h+arg_10], 0
0x1400595ce  xor     r9d, r9d; struct _WIN32_FIND_DATAW **
0x1400595d1  lea     r8, [rbp+57h+arg_10]; unsigned __int16 **
0x1400595d5  mov     rdx, [rbp+57h+hFindFile]; hFindFile
0x1400595d9  mov     rcx, r12; unsigned __int16 *
0x1400595dc  call    ?BlbFindNextFile@@YAJPEAGPEAXPEAPEAGPEAPEAU_WIN32_FIND_DATAW@@@Z; BlbFindNextFile(ushort *,void *,ushort * *,_WIN32_FIND_DATAW * *)
0x1400595e1  mov     ebx, eax
0x1400595e3  test    eax, eax
0x1400595e5  jns     short loc_140059577
0x1400595e7  jmp     short loc_140059571
0x1400595e9  mov     [r15+178h], r13
0x1400595f0  xor     r13d, r13d
0x1400595f3  test    rsi, rsi
0x1400595f6  jz      short loc_140059601
0x1400595f8  mov     rcx, rsi; pv
0x1400595fb  call    cs:__imp_CoTaskMemFree
  ... truncated ...
```
