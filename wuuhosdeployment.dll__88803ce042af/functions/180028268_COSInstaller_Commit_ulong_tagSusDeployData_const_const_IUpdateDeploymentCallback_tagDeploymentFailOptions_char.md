# COSInstaller::Commit(ulong,tagSusDeployData const * const,IUpdateDeploymentCallback *,tagDeploymentFailOptions,char const *)

- ea: `0x180028268`
- end: `0x18002870a`
- name: `?Commit@COSInstaller@@AEAAJKQEBUtagSusDeployData@@PEAUIUpdateDeploymentCallback@@W4tagDeploymentFailOptions@@PEBD@Z`
- size: `1186`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180027430`

## callees

- `0x180003950`
- `0x180005f64`
- `0x18000956c`
- `0x18000a448`
- `0x18000b2bc`
- `0x18000c0b4`
- `0x180024660`
- `0x180026db4`
- `0x180028268`
- `0x180028ea8`
- `0x180029f08`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180028356`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180028555`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180028356`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180028555`
- `OLEAUT32!__imp_SysStringLen` at `0x180028360`
- `OLEAUT32!__imp_SysStringLen` at `0x180028360`

## string_xrefs

- `0x18002856e`: `Commit`
- `0x1800282c2`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x1800286ac`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x1800286c2`: `Leave deployment handler Commit`
- `0x180028389`: `Preparing to commit update ID: %ws.%d`
- `0x1800282e2`: `Enter deployment handler Commit. Count of updates = %lu`
- `0x180028447`: `Commit complete for update ID: %ws.%d Return code is 0x%08lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall COSInstaller::Commit(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, int a5, _BYTE *a6)
{
  __int64 v6; // rbx
  __int64 v8; // rsi
  unsigned int v9; // edi
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r13
  __int64 v13; // r12
  int v14; // esi
  int v15; // ebx
  void *v16; // rcx
  int v17; // eax
  int v18; // eax
  ULONGLONG v19; // rax
  unsigned __int64 v20; // rcx
  int v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+20h] [rbp-E0h]
  bool v24; // [rsp+50h] [rbp-B0h]
  _BYTE v28[80]; // [rsp+80h] [rbp-80h] BYREF
  char *v29; // [rsp+D0h] [rbp-30h]
  void *lpMem; // [rsp+D8h] [rbp-28h] BYREF
  int v31; // [rsp+E0h] [rbp-20h] BYREF
  int v32; // [rsp+E4h] [rbp-1Ch] BYREF
  void *v33; // [rsp+E8h] [rbp-18h] BYREF
  const char *v34; // [rsp+F0h] [rbp-10h] BYREF
  void *v35; // [rsp+F8h] [rbp-8h] BYREF
  void *v36; // [rsp+100h] [rbp+0h] BYREF
  __int128 v37; // [rsp+108h] [rbp+8h]
  _OWORD v38[2]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v39; // [rsp+138h] [rbp+38h]
  _BYTE v40[8]; // [rsp+140h] [rbp+40h] BYREF
  ULONGLONG UnbiasedTime; // [rsp+148h] [rbp+48h] BYREF
  ULONGLONG v42; // [rsp+150h] [rbp+50h] BYREF
  ULONGLONG v43; // [rsp+158h] [rbp+58h]
  unsigned int v44; // [rsp+160h] [rbp+60h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v6 = a3;
  v8 = a1;
  v9 = 0;
  LODWORD(v29) = 0;
  if ( !a4 )
  {
    v10 = -2147467261;
    v11 = 531;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)v10,
      v22);
    return v10;
  }
  v22 = 0;
  WUTrace(0, 0, 4096, 4);
  if ( !a2 )
  {
    v10 = -2145124316;
    v11 = 536;
    goto LABEL_3;
  }
  while ( 1 )
  {
    v12 = v6 + 296LL * v9;
    v13 = *(_QWORD *)(v12 + 56);
    v31 = 0;
    v32 = 0;
    v33 = 0;
    lpMem = 0;
    CWUPerfTimer::CWUPerfTimer((CWUPerfTimer *)v40);
    v43 = 0;
    QueryUnbiasedInterruptTime(&UnbiasedTime);
    v24 = SysStringLen(*(BSTR *)(v12 + 24)) != 0;
    Trace::GuidToString::GuidToString((Trace::GuidToString *)v28, (const struct _GUID *)(v13 + 4));
    WUTrace(0, 0, 4096, 4);
    if ( lpMem )
    {
      CSusBaseAllocTag<942762101>::operator delete(lpMem);
      lpMem = 0;
    }
    if ( v33 )
    {
      CSusBaseAllocTag<942762101>::operator delete(v33);
      v33 = 0;
    }
    v14 = COSInstaller::OrchestrateUpdate(v8, v12, 2, -1, 0, &v31, (__int64)&v32, (__int64)&v33, (__int64)&lpMem, 0);
    Trace::GuidToString::GuidToString((Trace::GuidToString *)v28, (const struct _GUID *)(v13 + 4));
    WUTrace(0, 0, 4096, ((v14 >> 31) & 0xFFFFFFFE) + 4);
    v23 = v14;
    v15 = COSInstaller::NotifyResult(a1, a4, v12);
    v34 = 0;
    v35 = 0;
    v16 = 0;
    v36 = 0;
    v37 = 0;
    memset(v38, 0, sizeof(v38));
    v39 = 0;
    if ( v12 != -112 && *(_BYTE *)(v12 + 112) )
    {
      v17 = DuplicateString<char const *,char *>(v12 + 112, &v35);
      if ( v17 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xFC,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\DeploymentMiscTelemetry.h",
          (const char *)(unsigned int)v17,
          v14);
      v16 = v36;
    }
    if ( a6 && *a6 )
    {
      if ( v16 )
      {
        CSusBaseAllocTag<942762101>::operator delete(v16);
        v36 = 0;
      }
      v18 = DuplicateString<char const *,char *>(a6, &v36);
      if ( v18 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x104,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\DeploymentMiscTelemetry.h",
          (const char *)(unsigned int)v18,
          v23);
    }
    QueryUnbiasedInterruptTime(&v42);
    v19 = v42 - UnbiasedTime + v43;
    v43 = v19;
    v34 = "Commit";
    if ( v40[0] )
      v20 = v19 / v44;
    else
      LODWORD(v20) = 0;
    *(_OWORD *)((char *)v38 + 4) = *(_OWORD *)(*(_QWORD *)(v12 + 56) + 4LL);
    BYTE9(v37) = v31 != 0;
    HIDWORD(v37) = v32;
    DWORD1(v37) = v9;
    LOBYTE(v38[0]) = v24;
    *(_QWORD *)((char *)&v38[1] + 4) = __PAIR64__(v14, v15);
    LODWORD(v39) = v20;
    OSDeploymentTelemetry::FirePerUpdateEvent((struct OSDeploymentEventSummary *)&v34);
    if ( v15 < 0 )
    {
      v23 = v15;
      WUTrace(0, 0, 4096, 2);
    }
    if ( v14 < 0 )
    {
      LODWORD(v29) = v14;
      if ( !a5 )
        break;
    }
    if ( v36 )
    {
      CSusBaseAllocTag<942762101>::operator delete(v36);
      v36 = 0;
    }
    if ( v35 )
    {
      CSusBaseAllocTag<942762101>::operator delete(v35);
      v35 = 0;
    }
    if ( lpMem )
    {
      CSusBaseAllocTag<942762101>::operator delete(lpMem);
      lpMem = 0;
    }
    if ( v33 )
      CSusBaseAllocTag<942762101>::operator delete(v33);
    if ( ++v9 >= a2 )
      goto LABEL_46;
    v6 = a3;
    v8 = a1;
  }
  if ( v36 )
  {
    CSusBaseAllocTag<942762101>::operator delete(v36);
    v36 = 0;
  }
  if ( v35 )
  {
    CSusBaseAllocTag<942762101>::operator delete(v35);
    v35 = 0;
  }
  if ( lpMem )
  {
    CSusBaseAllocTag<942762101>::operator delete(lpMem);
    lpMem = 0;
  }
  if ( v33 )
    CSusBaseAllocTag<942762101>::operator delete(v33);
LABEL_46:
  v10 = (unsigned int)v29;
  if ( (int)v29 >= 0 )
    v10 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x274,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)(unsigned int)v29,
      v23);
  WUTrace(0, 0, 4096, 4);
  return v10;
}

```

## disassembly

```asm
0x180028268  push    rbp
0x18002826a  push    rbx
0x18002826b  push    rsi
0x18002826c  push    rdi
0x18002826d  push    r12
0x18002826f  push    r13
0x180028271  push    r14
0x180028273  push    r15
0x180028275  lea     rbp, [rsp-78h]
0x18002827a  sub     rsp, 178h
0x180028281  mov     rax, cs:__security_cookie
0x180028288  xor     rax, rsp
0x18002828b  mov     [rbp+0B0h+var_48], rax
0x18002828f  mov     [rsp+1B0h+var_150], r9
0x180028294  mov     rbx, r8
0x180028297  mov     [rsp+1B0h+var_148], rbx
0x18002829c  mov     r14d, edx
0x18002829f  mov     rsi, rcx
0x1800282a2  mov     [rsp+1B0h+var_158], rcx
0x1800282a7  mov     r15, [rbp+0B0h+arg_28]
0x1800282ae  xor     edi, edi
0x1800282b0  mov     dword ptr [rbp+0B0h+var_E0], edi
0x1800282b3  test    r9, r9
0x1800282b6  jnz     short loc_1800282DD
0x1800282b8  mov     ebx, 80004003h
0x1800282bd  mov     edx, 213h; void *
0x1800282c2  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800282c9  mov     r9d, ebx; char *
0x1800282cc  mov     rcx, [rbp+0B8h]; this
0x1800282d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800282d8  jmp     loc_1800286E8
0x1800282dd  mov     dword ptr [rsp+1B0h+var_180], r14d
0x1800282e2  lea     rax, aEnterDeploymen_2; "Enter deployment handler Commit. Count "...
0x1800282e9  mov     [rsp+1B0h+var_188], rax
0x1800282ee  mov     qword ptr [rsp+1B0h+var_190], rdi
0x1800282f3  xor     edx, edx
0x1800282f5  xor     ecx, ecx
0x1800282f7  lea     r9d, [rdx+4]
0x1800282fb  mov     r8d, 1000h
0x180028301  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180028306  test    r14d, r14d
0x180028309  jnz     short loc_180028317
0x18002830b  mov     ebx, 80240024h
0x180028310  mov     edx, 218h
0x180028315  jmp     short loc_1800282C2
0x180028317  lea     rax, [rbp+0B0h+var_E0]
0x18002831b  mov     [rsp+1B0h+var_140], rax
0x180028320  mov     [rsp+1B0h+var_138], 1
0x180028325  mov     eax, edi
0x180028327  imul    r13, rax, 128h
0x18002832e  add     r13, rbx
0x180028331  mov     r12, [r13+38h]
0x180028335  xor     ebx, ebx
0x180028337  mov     [rbp+0B0h+var_D0], ebx
0x18002833a  mov     [rbp+0B0h+var_CC], ebx
0x18002833d  mov     [rbp+0B0h+var_C8], rbx
0x180028341  mov     [rbp+0B0h+lpMem], rbx
0x180028345  lea     rcx, [rbp+0B0h+var_70]; this
0x180028349  call    ??0CWUPerfTimer@@QEAA@XZ; CWUPerfTimer::CWUPerfTimer(void)
0x18002834e  mov     [rbp+0B0h+var_58], rbx
0x180028352  lea     rcx, [rbp+0B0h+UnbiasedTime]; UnbiasedTime
0x180028356  call    cs:__imp_QueryUnbiasedInterruptTime
0x18002835c  mov     rcx, [r13+18h]; pbstr
0x180028360  call    cs:__imp_SysStringLen
0x180028366  test    eax, eax
0x180028368  setnz   [rsp+1B0h+var_160]
0x18002836d  mov     ebx, [r12+14h]
0x180028372  lea     rdx, [r12+4]; struct _GUID *
0x180028377  lea     rcx, [rbp+0B0h+var_130]; this
0x18002837b  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180028380  mov     dword ptr [rsp+1B0h+var_178], ebx
0x180028384  mov     [rsp+1B0h+var_180], rax
0x180028389  lea     rax, aPreparingToCom; "Preparing to commit update ID: %ws.%d"
0x180028390  mov     [rsp+1B0h+var_188], rax
0x180028395  xor     ebx, ebx
0x180028397  mov     qword ptr [rsp+1B0h+var_190], rbx
0x18002839c  xor     edx, edx
0x18002839e  xor     ecx, ecx
0x1800283a0  lea     r9d, [rbx+4]
0x1800283a4  mov     r8d, 1000h
0x1800283aa  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800283af  mov     rcx, [rbp+0B0h+lpMem]; lpMem
0x1800283b3  test    rcx, rcx
0x1800283b6  jz      short loc_1800283C1
0x1800283b8  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x1800283bd  mov     [rbp+0B0h+lpMem], rbx
0x1800283c1  mov     rcx, [rbp+0B0h+var_C8]; lpMem
0x1800283c5  test    rcx, rcx
0x1800283c8  jz      short loc_1800283D3
0x1800283ca  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x1800283cf  mov     [rbp+0B0h+var_C8], rbx
0x1800283d3  mov     [rsp+1B0h+var_168], rbx
0x1800283d8  lea     rax, [rbp+0B0h+lpMem]
0x1800283dc  mov     [rsp+1B0h+var_170], rax
0x1800283e1  lea     rax, [rbp+0B0h+var_C8]
0x1800283e5  mov     [rsp+1B0h+var_178], rax
0x1800283ea  lea     rax, [rbp+0B0h+var_CC]
0x1800283ee  mov     [rsp+1B0h+var_180], rax
0x1800283f3  lea     rax, [rbp+0B0h+var_D0]
0x1800283f7  mov     [rsp+1B0h+var_188], rax
0x1800283fc  mov     qword ptr [rsp+1B0h+var_190], rbx
0x180028401  or      r9d, 0FFFFFFFFh
0x180028405  mov     r8d, 2
0x18002840b  mov     rdx, r13
0x18002840e  mov     rcx, rsi
0x180028411  call    ?OrchestrateUpdate@COSInstaller@@AEAAJAEBUtagSusDeployData@@W4tagUpdateDeploymentAction@@KPEAUIUpdateDeploymentCallback@@PEAHPEAW4tagAutoCommitStatus@@PEAPEA_W5PEB_W@Z; COSInstaller::OrchestrateUpdate(tagSusDeployData const &,tagUpdateDeploymentAction,ulong,IUpdateDeploymentCallback *,int *,tagAutoCommitStatus *,wchar_t * *,wchar_t * *,wchar_t const *)
0x180028416  mov     esi, eax
0x180028418  mov     ebx, [r12+14h]
0x18002841d  lea     rdx, [r12+4]; struct _GUID *
0x180028422  lea     rcx, [rbp+0B0h+var_130]; this
0x180028426  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18002842b  mov     r9d, esi
0x18002842e  sar     r9d, 1Fh
0x180028432  and     r9d, 0FFFFFFFEh
0x180028436  add     r9d, 4
0x18002843a  mov     dword ptr [rsp+1B0h+var_170], esi
0x18002843e  mov     dword ptr [rsp+1B0h+var_178], ebx
0x180028442  mov     [rsp+1B0h+var_180], rax
0x180028447  lea     rax, aCommitComplete; "Commit complete for update ID: %ws.%d R"...
0x18002844e  mov     [rsp+1B0h+var_188], rax
0x180028453  xor     eax, eax
0x180028455  mov     qword ptr [rsp+1B0h+var_190], rax
0x18002845a  xor     edx, edx
0x18002845c  xor     ecx, ecx
0x18002845e  mov     r8d, 1000h
0x180028464  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180028469  mov     rax, [rbp+0B0h+lpMem]
0x18002846d  mov     rcx, [rbp+0B0h+var_C8]
0x180028471  mov     edx, [rbp+0B0h+var_CC]
0x180028474  mov     r8d, [rbp+0B0h+var_D0]
0x180028478  mov     [rsp+1B0h+var_170], rax
0x18002847d  mov     [rsp+1B0h+var_178], rcx
0x180028482  mov     dword ptr [rsp+1B0h+var_180], edx
0x180028486  mov     dword ptr [rsp+1B0h+var_188], r8d
0x18002848b  mov     [rsp+1B0h+var_190], esi; int
0x18002848f  mov     r8, r13
0x180028492  mov     rdx, [rsp+1B0h+var_150]
0x180028497  mov     rcx, [rsp+1B0h+var_158]
0x18002849c  call    ?NotifyResult@COSInstaller@@AEAAJPEAUIUpdateDeploymentCallback@@AEBUtagSusDeployData@@W4tagDeploymentOperationNotifyType@@JHW4tagAutoCommitStatus@@PEB_W4@Z; COSInstaller::NotifyResult(IUpdateDeploymentCallback *,tagSusDeployData const &,tagDeploymentOperationNotifyType,long,int,tagAutoCommitStatus,wchar_t const *,wchar_t const *)
0x1800284a1  mov     ebx, eax
0x1800284a3  xor     eax, eax
0x1800284a5  mov     [rbp+0B0h+var_C0], rax
0x1800284a9  xor     edx, edx
0x1800284ab  mov     [rbp+0B0h+var_B8], rdx
0x1800284af  mov     ecx, edx; lpMem
0x1800284b1  mov     [rbp+0B0h+var_B0], rdx
0x1800284b5  xorps   xmm0, xmm0
0x1800284b8  movups  [rbp+0B0h+var_A8], xmm0
0x1800284bc  movups  [rbp+0B0h+var_98], xmm0
0x1800284c0  movups  [rbp+0B0h+var_88], xmm0
0x1800284c4  mov     [rbp+0B0h+var_78], rax
0x1800284c8  lea     r12, [r13+70h]
0x1800284cc  test    r12, r12
0x1800284cf  jz      short loc_18002850B
0x1800284d1  cmp     [r12], dl
0x1800284d5  jz      short loc_18002850B
0x1800284d7  lea     rdx, [rbp+0B0h+var_B8]
0x1800284db  mov     rcx, r12
0x1800284de  call    ??$DuplicateString@PEBDPEAD@@YAJPEBDPEAPEAD@Z; DuplicateString<char const *,char *>(char const *,char * *)
0x1800284e3  mov     rcx, [rbp+0B8h]; this
0x1800284ea  xor     r12d, r12d
0x1800284ed  test    eax, eax
0x1800284ef  jns     short loc_180028505
0x1800284f1  mov     r9d, eax; char *
0x1800284f4  lea     r8, aCW1SSrcClientI_1; "C:\\__w\\1\\s\\src\\Client\\inc\\Deploy"...
0x1800284fb  mov     edx, 0FCh; void *
0x180028500  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180028505  mov     rcx, [rbp+0B0h+var_B0]
0x180028509  jmp     short loc_18002850E
0x18002850b  xor     r12d, r12d
0x18002850e  test    r15, r15
0x180028511  jz      short loc_180028551
0x180028513  cmp     [r15], r12b
0x180028516  jz      short loc_180028551
0x180028518  test    rcx, rcx
0x18002851b  jz      short loc_180028526
0x18002851d  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180028522  mov     [rbp+0B0h+var_B0], r12
0x180028526  lea     rdx, [rbp+0B0h+var_B0]
0x18002852a  mov     rcx, r15
0x18002852d  call    ??$DuplicateString@PEBDPEAD@@YAJPEBDPEAPEAD@Z; DuplicateString<char const *,char *>(char const *,char * *)
0x180028532  mov     rcx, [rbp+0B8h]; this
0x180028539  test    eax, eax
0x18002853b  jns     short loc_180028551
0x18002853d  mov     r9d, eax; char *
0x180028540  lea     r8, aCW1SSrcClientI_1; "C:\\__w\\1\\s\\src\\Client\\inc\\Deploy"...
0x180028547  mov     edx, 104h; void *
0x18002854c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180028551  lea     rcx, [rbp+0B0h+var_60]; UnbiasedTime
0x180028555  call    cs:__imp_QueryUnbiasedInterruptTime
0x18002855b  mov     rcx, [rbp+0B0h+var_60]
0x18002855f  sub     rcx, [rbp+0B0h+UnbiasedTime]
0x180028563  mov     rax, [rbp+0B0h+var_58]
0x180028567  add     rax, rcx
0x18002856a  mov     [rbp+0B0h+var_58], rax
0x18002856e  lea     rcx, aCommit_0; "Commit"
0x180028575  mov     [rbp+0B0h+var_C0], rcx
0x180028579  cmp     [rbp+0B0h+var_70], r12b
0x18002857d  jz      short loc_18002858C
0x18002857f  mov     ecx, [rbp+0B0h+var_50]
0x180028582  xor     edx, edx
0x180028584  div     rcx
0x180028587  mov     rcx, rax
0x18002858a  jmp     short loc_18002858F
0x18002858c  mov     ecx, r12d
0x18002858f  mov     rax, [r13+38h]
0x180028593  movups  xmm0, xmmword ptr [rax+4]
0x180028597  movdqu  [rbp+0B0h+var_98+4], xmm0
0x18002859c  cmp     [rbp+0B0h+var_D0], r12d
0x1800285a0  setnz   byte ptr [rbp+0B0h+var_A8+9]
0x1800285a4  mov     eax, [rbp+0B0h+var_CC]
0x1800285a7  mov     dword ptr [rbp+0B0h+var_A8+0Ch], eax
0x1800285aa  mov     dword ptr [rbp+0B0h+var_A8+4], edi
0x1800285ad  mov     al, [rsp+1B0h+var_160]
0x1800285b1  mov     byte ptr [rbp+0B0h+var_98], al
0x1800285b4  mov     dword ptr [rbp+0B0h+var_88+4], ebx
0x1800285b7  mov     dword ptr [rbp+0B0h+var_88+8], esi
0x1800285ba  mov     dword ptr [rbp+0B0h+var_78], ecx
0x1800285bd  lea     rcx, [rbp+0B0h+var_C0]; struct OSDeploymentEventSummary *
0x1800285c1  call    ?FirePerUpdateEvent@OSDeploymentTelemetry@@SAXPEAUOSDeploymentEventSummary@@@Z; OSDeploymentTelemetry::FirePerUpdateEvent(OSDeploymentEventSummary *)
0x1800285c6  test    ebx, ebx
0x1800285c8  jns     short loc_1800285ED
0x1800285ca  lea     rax, aNotifyFailed; "Notify failed"
0x1800285d1  mov     [rsp+1B0h+var_188], rax
0x1800285d6  mov     [rsp+1B0h+var_190], ebx; int
0x1800285da  xor     edx, edx
0x1800285dc  xor     ecx, ecx
0x1800285de  lea     r9d, [rdx+2]
0x1800285e2  mov     r8d, 1000h
0x1800285e8  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800285ed  test    esi, esi
0x1800285ef  jns     short loc_1800285FD
0x1800285f1  mov     dword ptr [rbp+0B0h+var_E0], esi
0x1800285f4  cmp     [rbp+0B0h+arg_20], r12d
0x1800285fb  jz      short loc_180028657
0x1800285fd  mov     rcx, [rbp+0B0h+var_B0]; lpMem
0x180028601  test    rcx, rcx
0x180028604  jz      short loc_18002860F
0x180028606  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002860b  mov     [rbp+0B0h+var_B0], r12
0x18002860f  mov     rcx, [rbp+0B0h+var_B8]; lpMem
0x180028613  test    rcx, rcx
0x180028616  jz      short loc_180028621
0x180028618  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002861d  mov     [rbp+0B0h+var_B8], r12
0x180028621  mov     rcx, [rbp+0B0h+lpMem]; lpMem
0x180028625  test    rcx, rcx
0x180028628  jz      short loc_180028633
0x18002862a  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002862f  mov     [rbp+0B0h+lpMem], r12
0x180028633  mov     rcx, [rbp+0B0h+var_C8]; lpMem
0x180028637  test    rcx, rcx
0x18002863a  jz      short loc_180028641
0x18002863c  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180028641  inc     edi
0x180028643  cmp     edi, r14d
0x180028646  jnb     short loc_18002869B
0x180028648  mov     rbx, [rsp+1B0h+var_148]
0x18002864d  mov     rsi, [rsp+1B0h+var_158]
0x180028652  jmp     loc_180028325
0x180028657  mov     rcx, [rbp+0B0h+var_B0]; lpMem
0x18002865b  test    rcx, rcx
0x18002865e  jz      short loc_180028669
0x180028660  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180028665  mov     [rbp+0B0h+var_B0], r12
0x180028669  mov     rcx, [rbp+0B0h+var_B8]; lpMem
0x18002866d  test    rcx, rcx
0x180028670  jz      short loc_18002867B
0x180028672  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180028677  mov     [rbp+0B0h+var_B8], r12
0x18002867b  mov     rcx, [rbp+0B0h+lpMem]; lpMem
0x18002867f  test    rcx, rcx
0x180028682  jz      short loc_18002868D
0x180028684  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180028689  mov     [rbp+0B0h+lpMem], r12
0x18002868d  mov     rcx, [rbp+0B0h+var_C8]; lpMem
0x180028691  test    rcx, rcx
0x180028694  jz      short loc_18002869B
0x180028696  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002869b  mov     ebx, dword ptr [rbp+0B0h+var_E0]
0x18002869e  test    ebx, ebx
0x1800286a0  jns     short loc_1800286BF
0x1800286a2  mov     rcx, [rbp+0B8h]; this
0x1800286a9  mov     r9d, ebx; char *
0x1800286ac  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800286b3  mov     edx, 274h; void *
0x1800286b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800286bd  jmp     short loc_1800286C2
0x1800286bf  mov     ebx, r12d
0x1800286c2  lea     rax, aLeaveDeploymen_2; "Leave deployment handler Commit"
0x1800286c9  mov     [rsp+1B0h+var_188], rax
0x1800286ce  mov     ecx, dword ptr [rbp+0B0h+var_E0]
0x1800286d1  mov     [rsp+1B0h+var_190], ecx
0x1800286d5  xor     edx, edx
0x1800286d7  xor     ecx, ecx
0x1800286d9  lea     r9d, [rdx+4]
0x1800286dd  mov     r8d, 1000h
0x1800286e3  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800286e8  mov     eax, ebx
0x1800286ea  mov     rcx, [rbp+0B0h+var_48]
  ... truncated ...
```
