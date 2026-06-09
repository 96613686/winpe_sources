# BlbComputeIncludeFilesInfo(_GUID,ushort *,ushort *,ushort *,ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>> &)

- ea: `0x14011f9a8`
- end: `0x14011ff34`
- name: `?BlbComputeIncludeFilesInfo@@YAJU_GUID@@PEAG11AEAV?$CAtlArray@U_WSB_SPEC_INFO@@V?$CElementTraits@U_WSB_SPEC_INFO@@@ATL@@@ATL@@@Z`
- size: `1420`
- prototype: `__int64 __fastcall(struct _GUID *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, __int64)`
- caller_count: `3`
- callee_count: `25`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x14000ed9c`
- `0x1400fb7b0`
- `0x1400fbb90`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000c2a8`
- `0x140012e74`
- `0x140014200`
- `0x140014260`
- `0x1400142d8`
- `0x140014448`
- `0x1400889f0`
- `0x140088d0c`
- `0x1400e2788`
- `0x1400e3240`
- `0x14011f408`
- `0x14011f9a8`
- `0x140120c58`
- `0x14012149c`
- `0x14012ad24`
- `0x14012b18c`
- `0x14012b1e8`
- `0x14012ba08`
- `0x14012bbf0`
- `0x14012bd80`
- `0x140134158`
- `0x140134cc6`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14011fb4b`
- `ole32!CoTaskMemFree` at `0x14011fb59`
- `ole32!CoTaskMemFree` at `0x14011fb68`
- `ole32!CoTaskMemFree` at `0x14011fb77`
- `ole32!CoTaskMemFree` at `0x14011fdd4`
- `ole32!CoTaskMemFree` at `0x14011fb4b`
- `ole32!CoTaskMemFree` at `0x14011fb59`
- `ole32!CoTaskMemFree` at `0x14011fb68`
- `ole32!CoTaskMemFree` at `0x14011fb77`
- `ole32!CoTaskMemFree` at `0x14011fdd4`
- `OLEAUT32!__imp_SysFreeString` at `0x14011fb33`
- `OLEAUT32!__imp_SysFreeString` at `0x14011fb3d`
- `OLEAUT32!__imp_SysFreeString` at `0x14011fbc7`
- `OLEAUT32!__imp_SysFreeString` at `0x14011fbd0`
- `OLEAUT32!__imp_SysFreeString` at `0x14011fcd5`
- `OLEAUT32!__imp_SysFreeString` at `0x14011fce3`
- `OLEAUT32!__imp_SysFreeString` at `0x14011fb33`
- `OLEAUT32!__imp_SysFreeString` at `0x14011fb3d`
- `OLEAUT32!__imp_SysFreeString` at `0x14011fbc7`
- `OLEAUT32!__imp_SysFreeString` at `0x14011fbd0`
- `OLEAUT32!__imp_SysFreeString` at `0x14011fcd5`
- `OLEAUT32!__imp_SysFreeString` at `0x14011fce3`

## string_xrefs

- `0x14011fa41`: `wszComponentName`
- `0x14011fa72`: `guidWriterId != GUID_NULL`
- `0x14011fa24`: `wszWriterMetadata`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall BlbComputeIncludeFilesInfo(
        struct _GUID *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        __int64 a5)
{
  CVssFileReadHelper *v9; // r15
  unsigned __int16 *v10; // rsi
  unsigned __int16 *v11; // rdi
  int CurrentNodeIncludeFileSpecs; // ebx
  int TargetForJunctionPointDirectory; // eax
  BSTR bstrString; // [rsp+30h] [rbp-41h] BYREF
  BSTR v16; // [rsp+38h] [rbp-39h] BYREF
  struct CVssFileReadHelper *v17; // [rsp+40h] [rbp-31h] BYREF
  _OWORD Buf1[2]; // [rsp+50h] [rbp-21h] BYREF
  LPVOID pv[2]; // [rsp+70h] [rbp-1h] BYREF
  __int64 v20; // [rsp+80h] [rbp+Fh]
  bool v21; // [rsp+D8h] [rbp+67h] BYREF
  unsigned __int16 *v22; // [rsp+E8h] [rbp+77h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_4201d197e4db3fa7a5843b9958eed2c5_Traceguids);
  }
  v9 = 0;
  v17 = 0;
  bstrString = 0;
  v16 = 0;
  v21 = 0;
  v10 = 0;
  v22 = 0;
  v11 = 0;
  if ( !a2 )
    BlbAssert("base\\stor\\blb\\wsbutil\\wsbsystemstateutils.cpp", 0x25Cu, "wszWriterMetadata");
  if ( !a4 )
    BlbAssert("base\\stor\\blb\\wsbutil\\wsbsystemstateutils.cpp", 0x25Du, "wszComponentName");
  if ( !memcmp_0(a1, &GUID_NULL, 0x10u) )
    BlbAssert("base\\stor\\blb\\wsbutil\\wsbsystemstateutils.cpp", 0x25Eu, "guidWriterId != GUID_NULL");
  ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::SetCount(a5, 0);
  *(_OWORD *)pv = 0;
  v20 = 0;
  Buf1[0] = xmmword_1401429A8;
  if ( !memcmp_0(Buf1, a1, 0x10u) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_4201d197e4db3fa7a5843b9958eed2c5_Traceguids, a4);
    }
    CBlbNonWriterFiles::CBlbNonWriterFiles((CBlbNonWriterFiles *)Buf1);
    CurrentNodeIncludeFileSpecs = CBlbNonWriterFiles::InitializeXML((CBlbNonWriterFiles *)Buf1, a2);
    if ( CurrentNodeIncludeFileSpecs >= 0 )
    {
      CurrentNodeIncludeFileSpecs = CBlbNonWriterFiles::SetComponentNode((CBlbNonWriterFiles *)Buf1, a4);
      if ( CurrentNodeIncludeFileSpecs >= 0 )
        CurrentNodeIncludeFileSpecs = CBlbNonWriterFiles::GetCurrentNodeIncludeFileSpecs(Buf1, a5);
    }
    CBlbNonWriterFiles::~CBlbNonWriterFiles((CBlbNonWriterFiles *)Buf1);
  }
  else
  {
    CurrentNodeIncludeFileSpecs = CVssRestore::GetReadHelper(a2, a1, a3, a4, &v17);
    if ( CurrentNodeIncludeFileSpecs >= 0 )
    {
      v9 = v17;
      while ( 1 )
      {
        CurrentNodeIncludeFileSpecs = CVssFileReadHelper::GetNextReadSpec(v9, &bstrString, &v16, &v21);
        v11 = 0;
        if ( CurrentNodeIncludeFileSpecs )
          break;
        *(_OWORD *)pv = 0;
        v20 = 0;
        CurrentNodeIncludeFileSpecs = BlbGetFileSpec(
                                        (struct ATL::CComBSTR *)&bstrString,
                                        (struct ATL::CComBSTR *)&v16,
                                        v21,
                                        (struct _WSB_SPEC_INFO *)pv);
        if ( CurrentNodeIncludeFileSpecs < 0 )
          break;
        SysFreeString(bstrString);
        bstrString = 0;
        SysFreeString(v16);
        v16 = 0;
        CurrentNodeIncludeFileSpecs = ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::Add(a5, pv);
        if ( CurrentNodeIncludeFileSpecs < 0 )
          break;
        if ( a4 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)pv[1], (__int64)a4);
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            (unsigned int)WPP_4201d197e4db3fa7a5843b9958eed2c5_Traceguids,
            pv[0],
            (__int64)pv[1]);
        }
        Buf1[0] = *a1;
        if ( !memcmp_0(Buf1, &g_guidDFSRWriter, 0x10u) && IsReparsePoint((const unsigned __int16 *)pv[0]) )
        {
          if ( v10 )
          {
            CoTaskMemFree(v10);
            v22 = 0;
          }
          TargetForJunctionPointDirectory = GetTargetForJunctionPointDirectory((LPCWSTR)pv[0], &v22);
          CurrentNodeIncludeFileSpecs = TargetForJunctionPointDirectory;
          if ( TargetForJunctionPointDirectory < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                19,
                (unsigned int)WPP_4201d197e4db3fa7a5843b9958eed2c5_Traceguids,
                pv[0],
                TargetForJunctionPointDirectory);
            }
            v10 = v22;
            break;
          }
          pv[0] = 0;
          v10 = v22;
          CurrentNodeIncludeFileSpecs = BlbutilSlashTerminatePath(v22, pv);
          if ( CurrentNodeIncludeFileSpecs < 0 )
            break;
          v11 = (unsigned __int16 *)pv[1];
          pv[1] = 0;
          CurrentNodeIncludeFileSpecs = BlbutilDuplicateString(v11, (unsigned __int16 **)&pv[1], 0);
          if ( CurrentNodeIncludeFileSpecs < 0 )
            break;
          v11 = 0;
          CurrentNodeIncludeFileSpecs = ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::Add(a5, pv);
          if ( CurrentNodeIncludeFileSpecs < 0 )
            break;
          if ( a4 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)pv[1], (__int64)a4);
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_SS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              21,
              (unsigned int)WPP_4201d197e4db3fa7a5843b9958eed2c5_Traceguids,
              pv[0],
              (__int64)pv[1]);
          }
        }
        *(_OWORD *)pv = 0;
        v20 = 0;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_4201d197e4db3fa7a5843b9958eed2c5_Traceguids);
      }
      v9 = v17;
    }
  }
  SysFreeString(bstrString);
  SysFreeString(v16);
  if ( v11 )
    CoTaskMemFree(v11);
  if ( v10 )
    CoTaskMemFree(v10);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  if ( pv[1] )
    CoTaskMemFree(pv[1]);
  if ( CurrentNodeIncludeFileSpecs < 0 )
    CWsbStructUtil::FreeFileSpecInfo(a5);
  if ( v9 )
    CVssFileReadHelper::`scalar deleting destructor'(v9);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_4201d197e4db3fa7a5843b9958eed2c5_Traceguids);
  }
  SysFreeString(0);
  SysFreeString(0);
  return (unsigned int)CurrentNodeIncludeFileSpecs;
}

```

## disassembly

```asm
0x14011f9a8  mov     [rsp-8+arg_0], rbx
0x14011f9ad  push    rbp
0x14011f9ae  push    rsi
0x14011f9af  push    rdi
0x14011f9b0  push    r12
0x14011f9b2  push    r13
0x14011f9b4  push    r14
0x14011f9b6  push    r15
0x14011f9b8  lea     rbp, [rsp-1Fh]
0x14011f9bd  sub     rsp, 90h
0x14011f9c4  mov     r14, r9
0x14011f9c7  mov     r12, r8
0x14011f9ca  mov     rbx, rdx
0x14011f9cd  mov     r13, rcx
0x14011f9d0  lea     rax, WPP_GLOBAL_Control
0x14011f9d7  mov     rcx, cs:WPP_GLOBAL_Control
0x14011f9de  cmp     rcx, rax
0x14011f9e1  jz      short loc_14011FA04
0x14011f9e3  test    byte ptr [rcx+1Ch], 1
0x14011f9e7  jz      short loc_14011FA04
0x14011f9e9  cmp     byte ptr [rcx+19h], 4
0x14011f9ed  jb      short loc_14011FA04
0x14011f9ef  mov     edx, 0Eh
0x14011f9f4  lea     r8, WPP_4201d197e4db3fa7a5843b9958eed2c5_Traceguids
0x14011f9fb  mov     rcx, [rcx+10h]
0x14011f9ff  call    WPP_SF_
0x14011fa04  xor     r15d, r15d
0x14011fa07  mov     [rbp+4Fh+var_80], r15
0x14011fa0b  mov     [rbp+4Fh+bstrString], r15
0x14011fa0f  mov     [rbp+4Fh+var_88], r15
0x14011fa13  mov     [rbp+4Fh+arg_8], r15b
0x14011fa17  xor     esi, esi
0x14011fa19  mov     [rbp+4Fh+arg_18], rsi
0x14011fa1d  xor     edi, edi
0x14011fa1f  test    rbx, rbx
0x14011fa22  jnz     short loc_14011FA3C
0x14011fa24  lea     r8, aWszwritermetad_0; "wszWriterMetadata"
0x14011fa2b  mov     edx, 25Ch; unsigned int
0x14011fa30  lea     rcx, aBaseStorBlbWsb_1; "base\\stor\\blb\\wsbutil\\wsbsystemstat"...
0x14011fa37  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14011fa3c  test    r14, r14
0x14011fa3f  jnz     short loc_14011FA59
0x14011fa41  lea     r8, aWszcomponentna; "wszComponentName"
0x14011fa48  mov     edx, 25Dh; unsigned int
0x14011fa4d  lea     rcx, aBaseStorBlbWsb_1; "base\\stor\\blb\\wsbutil\\wsbsystemstat"...
0x14011fa54  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14011fa59  mov     r8d, 10h; Size
0x14011fa5f  lea     rdx, GUID_NULL; Buf2
0x14011fa66  mov     rcx, r13; Buf1
0x14011fa69  call    memcmp_0
0x14011fa6e  test    eax, eax
0x14011fa70  jnz     short loc_14011FA8B
0x14011fa72  lea     r8, aGuidwriteridGu; "guidWriterId != GUID_NULL"
0x14011fa79  mov     edx, 25Eh; unsigned int
0x14011fa7e  lea     rcx, aBaseStorBlbWsb_1; "base\\stor\\blb\\wsbutil\\wsbsystemstat"...
0x14011fa85  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14011fa8a  nop
0x14011fa8b  xor     edx, edx
0x14011fa8d  mov     rcx, [rbp+4Fh+arg_20]
0x14011fa91  call    ?SetCount@?$CAtlArray@U_WSB_SPEC_INFO@@V?$CElementTraits@U_WSB_SPEC_INFO@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::SetCount(unsigned __int64,int)
0x14011fa96  nop
0x14011fa97  xorps   xmm0, xmm0
0x14011fa9a  xor     eax, eax
0x14011fa9c  movups  xmmword ptr [rbp+4Fh+pv], xmm0
0x14011faa0  mov     [rbp+4Fh+var_40], rax
0x14011faa4  movups  xmm1, cs:xmmword_1401429A8
0x14011faab  movdqu  [rbp+4Fh+Buf1], xmm1
0x14011fab0  lea     r8d, [rax+10h]; Size
0x14011fab4  mov     rdx, r13; Buf2
0x14011fab7  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x14011fabb  call    memcmp_0
0x14011fac0  test    eax, eax
0x14011fac2  jnz     loc_14011FC1D
0x14011fac8  mov     rcx, cs:WPP_GLOBAL_Control
0x14011facf  lea     rax, WPP_GLOBAL_Control
0x14011fad6  cmp     rcx, rax
0x14011fad9  jz      short loc_14011FAFF
0x14011fadb  test    byte ptr [rcx+1Ch], 1
0x14011fadf  jz      short loc_14011FAFF
0x14011fae1  cmp     byte ptr [rcx+19h], 4
0x14011fae5  jb      short loc_14011FAFF
0x14011fae7  mov     edx, 0Fh
0x14011faec  mov     r9, r14
0x14011faef  lea     r8, WPP_4201d197e4db3fa7a5843b9958eed2c5_Traceguids
0x14011faf6  mov     rcx, [rcx+10h]
0x14011fafa  call    WPP_SF_S
0x14011faff  lea     rcx, [rbp+4Fh+Buf1]; this
0x14011fb03  call    ??0CBlbNonWriterFiles@@QEAA@XZ; CBlbNonWriterFiles::CBlbNonWriterFiles(void)
0x14011fb08  nop
0x14011fb09  mov     rdx, rbx; unsigned __int16 *
0x14011fb0c  lea     rcx, [rbp+4Fh+Buf1]; this
0x14011fb10  call    ?InitializeXML@CBlbNonWriterFiles@@QEAAJPEBG@Z; CBlbNonWriterFiles::InitializeXML(ushort const *)
0x14011fb15  mov     ebx, eax
0x14011fb17  test    eax, eax
0x14011fb19  jns     loc_14011FBF3
0x14011fb1f  lea     rcx, [rbp+4Fh+Buf1]; this
0x14011fb23  call    ??1CBlbNonWriterFiles@@QEAA@XZ; CBlbNonWriterFiles::~CBlbNonWriterFiles(void)
0x14011fb28  lea     r14, WPP_GLOBAL_Control
0x14011fb2f  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x14011fb33  call    cs:__imp_SysFreeString
0x14011fb39  mov     rcx, [rbp+4Fh+var_88]; bstrString
0x14011fb3d  call    cs:__imp_SysFreeString
0x14011fb43  test    rdi, rdi
0x14011fb46  jz      short loc_14011FB51
0x14011fb48  mov     rcx, rdi; pv
0x14011fb4b  call    cs:__imp_CoTaskMemFree
0x14011fb51  test    rsi, rsi
0x14011fb54  jz      short loc_14011FB5F
0x14011fb56  mov     rcx, rsi; pv
0x14011fb59  call    cs:__imp_CoTaskMemFree
0x14011fb5f  mov     rcx, [rbp+4Fh+pv]; pv
0x14011fb63  test    rcx, rcx
0x14011fb66  jz      short loc_14011FB6E
0x14011fb68  call    cs:__imp_CoTaskMemFree
0x14011fb6e  mov     rcx, [rbp+4Fh+pv+8]; pv
0x14011fb72  test    rcx, rcx
0x14011fb75  jz      short loc_14011FB7D
0x14011fb77  call    cs:__imp_CoTaskMemFree
0x14011fb7d  test    ebx, ebx
0x14011fb7f  jns     short loc_14011FB8A
0x14011fb81  mov     rcx, [rbp+4Fh+arg_20]
0x14011fb85  call    ?FreeFileSpecInfo@CWsbStructUtil@@SAXAEAV?$CAtlArray@U_WSB_SPEC_INFO@@V?$CElementTraits@U_WSB_SPEC_INFO@@@ATL@@@ATL@@@Z; CWsbStructUtil::FreeFileSpecInfo(ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>> &)
0x14011fb8a  test    r15, r15
0x14011fb8d  jz      short loc_14011FB97
0x14011fb8f  mov     rcx, r15; this
0x14011fb92  call    ??_GCVssFileReadHelper@@QEAAPEAXI@Z; CVssFileReadHelper::`scalar deleting destructor'(uint)
0x14011fb97  mov     rcx, cs:WPP_GLOBAL_Control
0x14011fb9e  cmp     rcx, r14
0x14011fba1  jz      short loc_14011FBC5
0x14011fba3  test    byte ptr [rcx+1Ch], 1
0x14011fba7  jz      short loc_14011FBC5
0x14011fba9  cmp     byte ptr [rcx+19h], 4
0x14011fbad  jb      short loc_14011FBC5
0x14011fbaf  mov     edx, 16h
0x14011fbb4  lea     r8, WPP_4201d197e4db3fa7a5843b9958eed2c5_Traceguids
0x14011fbbb  mov     rcx, [rcx+10h]
0x14011fbbf  call    WPP_SF_
0x14011fbc4  nop
0x14011fbc5  xor     ecx, ecx; bstrString
0x14011fbc7  call    cs:__imp_SysFreeString
0x14011fbcd  nop
0x14011fbce  xor     ecx, ecx; bstrString
0x14011fbd0  call    cs:__imp_SysFreeString
0x14011fbd6  mov     eax, ebx
0x14011fbd8  mov     rbx, [rsp+0C0h+arg_0]
0x14011fbe0  add     rsp, 90h
0x14011fbe7  pop     r15
0x14011fbe9  pop     r14
0x14011fbeb  pop     r13
0x14011fbed  pop     r12
0x14011fbef  pop     rdi
0x14011fbf0  pop     rsi
0x14011fbf1  pop     rbp
0x14011fbf2  retn
0x14011fbf3  mov     rdx, r14; unsigned __int16 *
0x14011fbf6  lea     rcx, [rbp+4Fh+Buf1]; this
0x14011fbfa  call    ?SetComponentNode@CBlbNonWriterFiles@@QEAAJPEBG@Z; CBlbNonWriterFiles::SetComponentNode(ushort const *)
0x14011fbff  mov     ebx, eax
0x14011fc01  test    eax, eax
0x14011fc03  js      loc_14011FB1F
0x14011fc09  mov     rdx, [rbp+4Fh+arg_20]
0x14011fc0d  lea     rcx, [rbp+4Fh+Buf1]
0x14011fc11  call    ?GetCurrentNodeIncludeFileSpecs@CBlbNonWriterFiles@@QEAAJAEAV?$CAtlArray@U_WSB_SPEC_INFO@@V?$CElementTraits@U_WSB_SPEC_INFO@@@ATL@@@ATL@@@Z; CBlbNonWriterFiles::GetCurrentNodeIncludeFileSpecs(ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>> &)
0x14011fc16  mov     ebx, eax
0x14011fc18  jmp     loc_14011FB1F
0x14011fc1d  lea     rax, [rbp+4Fh+var_80]
0x14011fc21  mov     [rsp+0C0h+var_A0], rax; struct CVssFileReadHelper **
0x14011fc26  mov     r9, r14; unsigned __int16 *
0x14011fc29  mov     r8, r12; unsigned __int16 *
0x14011fc2c  mov     rdx, r13; struct _GUID *
0x14011fc2f  mov     rcx, rbx; unsigned __int16 *
0x14011fc32  call    ?GetReadHelper@CVssRestore@@SAJPEBGPEAU_GUID@@00PEAPEAVCVssFileReadHelper@@@Z; CVssRestore::GetReadHelper(ushort const *,_GUID *,ushort const *,ushort const *,CVssFileReadHelper * *)
0x14011fc37  mov     ebx, eax
0x14011fc39  xor     r12d, r12d
0x14011fc3c  test    eax, eax
0x14011fc3e  jns     short loc_14011FC80
0x14011fc40  mov     rcx, cs:WPP_GLOBAL_Control
0x14011fc47  lea     r14, WPP_GLOBAL_Control
0x14011fc4e  cmp     rcx, r14
0x14011fc51  jz      short loc_14011FC77
0x14011fc53  test    byte ptr [rcx+1Ch], 1
0x14011fc57  jz      short loc_14011FC77
0x14011fc59  cmp     byte ptr [rcx+19h], 2
0x14011fc5d  jb      short loc_14011FC77
0x14011fc5f  lea     edx, [r12+10h]
0x14011fc64  mov     r9d, eax
0x14011fc67  lea     r8, WPP_4201d197e4db3fa7a5843b9958eed2c5_Traceguids
0x14011fc6e  mov     rcx, [rcx+10h]
0x14011fc72  call    WPP_SF_d
0x14011fc77  mov     r15, [rbp+4Fh+var_80]
0x14011fc7b  jmp     loc_14011FB2F
0x14011fc80  mov     r15, [rbp+4Fh+var_80]
0x14011fc84  lea     r9, [rbp+4Fh+arg_8]; bool *
0x14011fc88  lea     r8, [rbp+4Fh+var_88]; unsigned __int16 **
0x14011fc8c  lea     rdx, [rbp+4Fh+bstrString]; unsigned __int16 **
0x14011fc90  mov     rcx, r15; this
0x14011fc93  call    ?GetNextReadSpec@CVssFileReadHelper@@QEAAJPEAPEAG0PEA_N@Z; CVssFileReadHelper::GetNextReadSpec(ushort * *,ushort * *,bool *)
0x14011fc98  mov     ebx, eax
0x14011fc9a  mov     rdi, r12
0x14011fc9d  test    eax, eax
0x14011fc9f  jnz     loc_14011FB28
0x14011fca5  xorps   xmm0, xmm0
0x14011fca8  xor     eax, eax
0x14011fcaa  movups  xmmword ptr [rbp+4Fh+pv], xmm0
0x14011fcae  mov     [rbp+4Fh+var_40], rax
0x14011fcb2  lea     r9, [rbp+4Fh+pv]; struct _WSB_SPEC_INFO *
0x14011fcb6  mov     r8b, [rbp+4Fh+arg_8]; bool
0x14011fcba  lea     rdx, [rbp+4Fh+var_88]; struct ATL::CComBSTR *
0x14011fcbe  lea     rcx, [rbp+4Fh+bstrString]; struct ATL::CComBSTR *
0x14011fcc2  call    ?BlbGetFileSpec@@YAJAEAVCComBSTR@ATL@@0_NAEAU_WSB_SPEC_INFO@@@Z; BlbGetFileSpec(ATL::CComBSTR &,ATL::CComBSTR &,bool,_WSB_SPEC_INFO &)
0x14011fcc7  mov     ebx, eax
0x14011fcc9  test    eax, eax
0x14011fccb  js      loc_14011FB28
0x14011fcd1  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x14011fcd5  call    cs:__imp_SysFreeString
0x14011fcdb  mov     [rbp+4Fh+bstrString], r12
0x14011fcdf  mov     rcx, [rbp+4Fh+var_88]; bstrString
0x14011fce3  call    cs:__imp_SysFreeString
0x14011fce9  mov     [rbp+4Fh+var_88], r12
0x14011fced  lea     rdx, [rbp+4Fh+pv]
0x14011fcf1  mov     rcx, [rbp+4Fh+arg_20]
0x14011fcf5  call    ?Add@?$CAtlArray@U_WSB_SPEC_INFO@@V?$CElementTraits@U_WSB_SPEC_INFO@@@ATL@@@ATL@@QEAA_KAEBU_WSB_SPEC_INFO@@@Z; ATL::CAtlArray<_WSB_SPEC_INFO,ATL::CElementTraits<_WSB_SPEC_INFO>>::Add(_WSB_SPEC_INFO const &)
0x14011fcfa  mov     rbx, rax
0x14011fcfd  test    eax, eax
0x14011fcff  js      loc_14011FB28
0x14011fd05  test    r14, r14
0x14011fd08  jz      short loc_14011FD52
0x14011fd0a  mov     rcx, cs:WPP_GLOBAL_Control
0x14011fd11  lea     rax, WPP_GLOBAL_Control
0x14011fd18  cmp     rcx, rax
0x14011fd1b  jz      short loc_14011FD93
0x14011fd1d  test    byte ptr [rcx+1Ch], 1
0x14011fd21  jz      short loc_14011FD93
0x14011fd23  cmp     byte ptr [rcx+19h], 5
0x14011fd27  jb      short loc_14011FD93
0x14011fd29  mov     edx, 11h
0x14011fd2e  mov     [rsp+0C0h+var_98], r14; __int64
0x14011fd33  mov     rax, [rbp+4Fh+pv+8]
0x14011fd37  mov     [rsp+0C0h+var_A0], rax; __int64
0x14011fd3c  mov     r9, [rbp+4Fh+pv]
0x14011fd40  lea     r8, WPP_4201d197e4db3fa7a5843b9958eed2c5_Traceguids
0x14011fd47  mov     rcx, [rcx+10h]; LoggerHandle
0x14011fd4b  call    WPP_SF_SSS
0x14011fd50  jmp     short loc_14011FD93
0x14011fd52  mov     rcx, cs:WPP_GLOBAL_Control
0x14011fd59  lea     rax, WPP_GLOBAL_Control
0x14011fd60  cmp     rcx, rax
0x14011fd63  jz      short loc_14011FD93
0x14011fd65  test    byte ptr [rcx+1Ch], 1
0x14011fd69  jz      short loc_14011FD93
0x14011fd6b  cmp     byte ptr [rcx+19h], 5
0x14011fd6f  jb      short loc_14011FD93
0x14011fd71  mov     edx, 12h
0x14011fd76  mov     rax, [rbp+4Fh+pv+8]
0x14011fd7a  mov     [rsp+0C0h+var_A0], rax
0x14011fd7f  mov     r9, [rbp+4Fh+pv]
0x14011fd83  lea     r8, WPP_4201d197e4db3fa7a5843b9958eed2c5_Traceguids
0x14011fd8a  mov     rcx, [rcx+10h]
0x14011fd8e  call    WPP_SF_SS
0x14011fd93  movaps  xmm0, xmmword ptr [r13+0]
0x14011fd98  movdqa  [rbp+4Fh+Buf1], xmm0
0x14011fd9d  mov     r8d, 10h; Size
0x14011fda3  lea     rdx, ?g_guidDFSRWriter@@3U_GUID@@B; Buf2
0x14011fdaa  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x14011fdae  call    memcmp_0
0x14011fdb3  test    eax, eax
0x14011fdb5  jnz     loc_14011FEDC
0x14011fdbb  mov     rcx, [rbp+4Fh+pv]; unsigned __int16 *
0x14011fdbf  call    ?IsReparsePoint@@YA_NPEBG@Z; IsReparsePoint(ushort const *)
0x14011fdc4  test    al, al
0x14011fdc6  jz      loc_14011FEDC
0x14011fdcc  test    rsi, rsi
0x14011fdcf  jz      short loc_14011FDDE
0x14011fdd1  mov     rcx, rsi; pv
0x14011fdd4  call    cs:__imp_CoTaskMemFree
0x14011fdda  mov     [rbp+4Fh+arg_18], r12
0x14011fdde  lea     rdx, [rbp+4Fh+arg_18]; unsigned __int16 **
0x14011fde2  mov     rcx, [rbp+4Fh+pv]; lpFileName
0x14011fde6  call    ?GetTargetForJunctionPointDirectory@@YAJPEBGPEAPEAG@Z; GetTargetForJunctionPointDirectory(ushort const *,ushort * *)
0x14011fdeb  mov     ebx, eax
0x14011fded  test    eax, eax
0x14011fdef  js      loc_14011FEEE
0x14011fdf5  mov     [rbp+4Fh+pv], r12
0x14011fdf9  lea     rdx, [rbp+4Fh+pv]; unsigned __int16 **
0x14011fdfd  mov     rsi, [rbp+4Fh+arg_18]
0x14011fe01  mov     rcx, rsi; unsigned __int16 *
0x14011fe04  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x14011fe09  mov     ebx, eax
0x14011fe0b  test    eax, eax
0x14011fe0d  js      loc_14011FB28
0x14011fe13  mov     rdi, [rbp+4Fh+pv+8]
0x14011fe17  mov     [rbp+4Fh+pv+8], r12
0x14011fe1b  xor     r8d, r8d; unsigned __int64
0x14011fe1e  lea     rdx, [rbp+4Fh+pv+8]; unsigned __int16 **
0x14011fe22  mov     rcx, rdi; unsigned __int16 *
0x14011fe25  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14011fe2a  mov     ebx, eax
0x14011fe2c  test    eax, eax
0x14011fe2e  js      loc_14011FB28
0x14011fe34  mov     rdi, r12
  ... truncated ...
```
