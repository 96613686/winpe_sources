# COSInstaller::Revert(tagOperationContext *,ulong,tagSusDeployData * const,IUpdateDeploymentCallback *,tagDeploymentFailOptions,char const *)

- ea: `0x180027d78`
- end: `0x18002825f`
- name: `?Revert@COSInstaller@@AEAAJPEAUtagOperationContext@@KQEAUtagSusDeployData@@PEAUIUpdateDeploymentCallback@@W4tagDeploymentFailOptions@@PEBD@Z`
- size: `1255`
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
- `0x180027d78`
- `0x180028ea8`
- `0x180029f08`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180027e91`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800280a8`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180027e91`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800280a8`
- `OLEAUT32!__imp_SysStringLen` at `0x180027e9b`
- `OLEAUT32!__imp_SysStringLen` at `0x180027e9b`

## string_xrefs

- `0x180027e16`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x180028201`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x180027ec0`: `Preparing to revert update ID: %ws.%d`
- `0x180027dd9`: `Enter Deployment handler Revert. Count of updates = %lu`
- `0x180027f9e`: `Revert complete for update ID: %ws.%d Return code is 0x%08lX. Requires Reboot:%ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall COSInstaller::Revert(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        int a6,
        _BYTE *a7)
{
  __int64 v7; // rbx
  __int64 v10; // r14
  __int64 v11; // rdx
  unsigned int v12; // ebx
  unsigned int v13; // esi
  __int64 v14; // r13
  const struct _GUID *v15; // rdi
  int v16; // r14d
  int v17; // ebx
  void *v18; // rcx
  int v19; // eax
  int v20; // eax
  ULONGLONG v21; // rax
  unsigned __int64 v22; // rcx
  int v24; // [rsp+20h] [rbp-E0h]
  bool v25; // [rsp+50h] [rbp-B0h]
  _BYTE v29[80]; // [rsp+90h] [rbp-70h] BYREF
  int v30; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD v31[3]; // [rsp+E4h] [rbp-1Ch] BYREF
  int v32; // [rsp+F0h] [rbp-10h] BYREF
  void *lpMem; // [rsp+F8h] [rbp-8h] BYREF
  const char *v34; // [rsp+100h] [rbp+0h] BYREF
  void *v35; // [rsp+108h] [rbp+8h] BYREF
  void *v36; // [rsp+110h] [rbp+10h] BYREF
  __int128 v37; // [rsp+118h] [rbp+18h]
  _OWORD v38[2]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v39; // [rsp+148h] [rbp+48h]
  _BYTE v40[8]; // [rsp+150h] [rbp+50h] BYREF
  ULONGLONG UnbiasedTime; // [rsp+158h] [rbp+58h] BYREF
  ULONGLONG v42; // [rsp+160h] [rbp+60h] BYREF
  ULONGLONG v43; // [rsp+168h] [rbp+68h]
  unsigned int v44; // [rsp+170h] [rbp+70h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v7 = a4;
  v10 = a5;
  v31[0] = 0;
  v24 = 0;
  WUTrace(0, 0, 4096, 4);
  if ( !v7 )
  {
    v11 = 414;
LABEL_3:
    v12 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)0x80004003LL,
      0);
    return v12;
  }
  if ( !a5 )
  {
    v11 = 415;
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v11 = 416;
    goto LABEL_3;
  }
  v13 = 0;
  if ( a3 )
  {
    while ( 1 )
    {
      v14 = v7 + 296LL * v13;
      v15 = (const struct _GUID *)(*(_QWORD *)(v14 + 56) + 4LL);
      v30 = 0;
      v32 = 0;
      lpMem = 0;
      *(_QWORD *)&v31[1] = 0;
      CWUPerfTimer::CWUPerfTimer((CWUPerfTimer *)v40);
      v43 = 0;
      QueryUnbiasedInterruptTime(&UnbiasedTime);
      v25 = SysStringLen(*(BSTR *)(v14 + 24)) != 0;
      Trace::GuidToString::GuidToString((Trace::GuidToString *)v29, v15);
      WUTrace(0, 0, 4096, 4);
      if ( *(_QWORD *)&v31[1] )
      {
        CSusBaseAllocTag<942762101>::operator delete(*(void **)&v31[1]);
        *(_QWORD *)&v31[1] = 0;
      }
      if ( lpMem )
      {
        CSusBaseAllocTag<942762101>::operator delete(lpMem);
        lpMem = 0;
      }
      v16 = COSInstaller::OrchestrateUpdate(
              a1,
              v14,
              4,
              *(_DWORD *)(a2 + 16),
              v10,
              &v30,
              (__int64)&v32,
              (__int64)&lpMem,
              (__int64)&v31[1],
              0);
      Trace::GuidToString::GuidToString((Trace::GuidToString *)v29, v15);
      WUTrace(0, 0, 4096, ((v16 >> 31) & 0xFFFFFFFE) + 4);
      v24 = v16;
      v17 = COSInstaller::NotifyResult(a1, a5, v14);
      v34 = 0;
      v35 = 0;
      v18 = 0;
      v36 = 0;
      v37 = 0;
      memset(v38, 0, sizeof(v38));
      v39 = 0;
      if ( v14 != -112 && *(_BYTE *)(v14 + 112) )
      {
        v19 = DuplicateString<char const *,char *>(v14 + 112, &v35);
        if ( v19 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xFC,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\DeploymentMiscTelemetry.h",
            (const char *)(unsigned int)v19,
            v16);
        v18 = v36;
      }
      if ( a7 && *a7 )
      {
        if ( v18 )
        {
          CSusBaseAllocTag<942762101>::operator delete(v18);
          v36 = 0;
        }
        v20 = DuplicateString<char const *,char *>(a7, &v36);
        if ( v20 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x104,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\DeploymentMiscTelemetry.h",
            (const char *)(unsigned int)v20,
            v24);
      }
      QueryUnbiasedInterruptTime(&v42);
      v21 = v42 - UnbiasedTime + v43;
      v43 = v21;
      v34 = "Revert";
      LODWORD(v22) = 0;
      if ( v40[0] )
        v22 = v21 / v44;
      *(_OWORD *)((char *)v38 + 4) = *(_OWORD *)(*(_QWORD *)(v14 + 56) + 4LL);
      BYTE9(v37) = v30 != 0;
      HIDWORD(v37) = v32;
      DWORD1(v37) = v13;
      LOBYTE(v38[0]) = v25;
      *(_QWORD *)((char *)&v38[1] + 4) = __PAIR64__(v16, v17);
      LODWORD(v39) = v22;
      OSDeploymentTelemetry::FirePerUpdateEvent((struct OSDeploymentEventSummary *)&v34);
      if ( v17 < 0 )
      {
        v24 = v17;
        WUTrace(0, 0, 4096, 2);
      }
      if ( v16 < 0 )
      {
        v31[0] = v16;
        if ( !a6 )
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
      if ( *(_QWORD *)&v31[1] )
      {
        CSusBaseAllocTag<942762101>::operator delete(*(void **)&v31[1]);
        *(_QWORD *)&v31[1] = 0;
      }
      if ( lpMem )
        CSusBaseAllocTag<942762101>::operator delete(lpMem);
      if ( ++v13 >= a3 )
        goto LABEL_48;
      v7 = a4;
      v10 = a5;
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
    if ( *(_QWORD *)&v31[1] )
    {
      CSusBaseAllocTag<942762101>::operator delete(*(void **)&v31[1]);
      *(_QWORD *)&v31[1] = 0;
    }
    if ( lpMem )
      CSusBaseAllocTag<942762101>::operator delete(lpMem);
  }
LABEL_48:
  v12 = v31[0];
  if ( v31[0] >= 0 )
    v12 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FA,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)v31[0],
      v24);
  WUTrace(0, 0, 4096, 4);
  return v12;
}

```

## disassembly

```asm
0x180027d78  push    rbp
0x180027d7a  push    rbx
0x180027d7b  push    rsi
0x180027d7c  push    rdi
0x180027d7d  push    r12
0x180027d7f  push    r13
0x180027d81  push    r14
0x180027d83  push    r15
0x180027d85  lea     rbp, [rsp-88h]
0x180027d8d  sub     rsp, 188h
0x180027d94  mov     rax, cs:__security_cookie
0x180027d9b  xor     rax, rsp
0x180027d9e  mov     [rbp+0C0h+var_48], rax
0x180027da2  mov     rbx, r9
0x180027da5  mov     [rsp+1C0h+var_148], rbx
0x180027daa  mov     r15d, r8d
0x180027dad  mov     rdi, rdx
0x180027db0  mov     [rsp+1C0h+var_158], rdx
0x180027db5  mov     [rsp+1C0h+var_168], rcx
0x180027dba  mov     r14, [rbp+0C0h+arg_20]
0x180027dc1  mov     [rsp+1C0h+var_160], r14
0x180027dc6  mov     r12, [rbp+0C0h+arg_30]
0x180027dcd  xor     r13d, r13d
0x180027dd0  mov     dword ptr [rbp+0C0h+var_DC], r13d
0x180027dd4  mov     dword ptr [rsp+1C0h+var_190], r8d
0x180027dd9  lea     rax, aEnterDeploymen; "Enter Deployment handler Revert. Count "...
0x180027de0  mov     [rsp+1C0h+var_198], rax
0x180027de5  mov     qword ptr [rsp+1C0h+var_1A0], r13; int
0x180027dea  xor     edx, edx
0x180027dec  xor     ecx, ecx
0x180027dee  lea     r9d, [r13+4]
0x180027df2  mov     r8d, 1000h
0x180027df8  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180027dfd  test    rbx, rbx
0x180027e00  jnz     short loc_180027E27
0x180027e02  mov     edx, 19Eh; void *
0x180027e07  mov     ebx, 80004003h
0x180027e0c  mov     rcx, [rbp+0C8h]; this
0x180027e13  mov     r9d, ebx; char *
0x180027e16  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180027e1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027e22  jmp     loc_18002823D
0x180027e27  test    r14, r14
0x180027e2a  jnz     short loc_180027E33
0x180027e2c  mov     edx, 19Fh
0x180027e31  jmp     short loc_180027E07
0x180027e33  test    rdi, rdi
0x180027e36  jnz     short loc_180027E3F
0x180027e38  mov     edx, 1A0h
0x180027e3d  jmp     short loc_180027E07
0x180027e3f  lea     rax, [rbp+0C0h+var_DC]
0x180027e43  mov     [rbp+0C0h+var_140], rax
0x180027e47  mov     [rbp+0C0h+var_138], 1
0x180027e4b  mov     esi, r13d
0x180027e4e  test    r15d, r15d
0x180027e51  jz      loc_1800281F0
0x180027e57  mov     eax, esi
0x180027e59  imul    r13, rax, 128h
0x180027e60  add     r13, rbx
0x180027e63  mov     rdi, [r13+38h]
0x180027e67  add     rdi, 4
0x180027e6b  mov     [rsp+1C0h+var_150], rdi
0x180027e70  xor     ebx, ebx
0x180027e72  mov     [rbp+0C0h+var_E0], ebx
0x180027e75  mov     [rbp+0C0h+var_D0], ebx
0x180027e78  mov     [rbp+0C0h+lpMem], rbx
0x180027e7c  mov     qword ptr [rbp+0C0h+var_DC+4], rbx
0x180027e80  lea     rcx, [rbp+0C0h+var_70]; this
0x180027e84  call    ??0CWUPerfTimer@@QEAA@XZ; CWUPerfTimer::CWUPerfTimer(void)
0x180027e89  mov     [rbp+0C0h+var_58], rbx
0x180027e8d  lea     rcx, [rbp+0C0h+UnbiasedTime]; UnbiasedTime
0x180027e91  call    cs:__imp_QueryUnbiasedInterruptTime
0x180027e97  mov     rcx, [r13+18h]; pbstr
0x180027e9b  call    cs:__imp_SysStringLen
0x180027ea1  test    eax, eax
0x180027ea3  setnz   [rsp+1C0h+var_170]
0x180027ea8  mov     ebx, [rdi+10h]
0x180027eab  mov     rdx, rdi; struct _GUID *
0x180027eae  lea     rcx, [rbp+0C0h+var_130]; this
0x180027eb2  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180027eb7  mov     dword ptr [rsp+1C0h+var_188], ebx
0x180027ebb  mov     [rsp+1C0h+var_190], rax
0x180027ec0  lea     rax, aPreparingToRev; "Preparing to revert update ID: %ws.%d"
0x180027ec7  mov     [rsp+1C0h+var_198], rax
0x180027ecc  xor     ebx, ebx
0x180027ece  mov     qword ptr [rsp+1C0h+var_1A0], rbx
0x180027ed3  lea     edi, [rbx+4]
0x180027ed6  mov     r9d, edi
0x180027ed9  xor     edx, edx
0x180027edb  xor     ecx, ecx
0x180027edd  mov     r8d, 1000h
0x180027ee3  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180027ee8  mov     rcx, qword ptr [rbp+0C0h+var_DC+4]; lpMem
0x180027eec  test    rcx, rcx
0x180027eef  jz      short loc_180027EFA
0x180027ef1  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180027ef6  mov     qword ptr [rbp+0C0h+var_DC+4], rbx
0x180027efa  mov     rcx, [rbp+0C0h+lpMem]; lpMem
0x180027efe  test    rcx, rcx
0x180027f01  jz      short loc_180027F0C
0x180027f03  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180027f08  mov     [rbp+0C0h+lpMem], rbx
0x180027f0c  mov     [rsp+1C0h+var_178], rbx
0x180027f11  lea     rax, [rbp+0C0h+var_DC+4]
0x180027f15  mov     [rsp+1C0h+var_180], rax
0x180027f1a  lea     rax, [rbp+0C0h+lpMem]
0x180027f1e  mov     [rsp+1C0h+var_188], rax
0x180027f23  lea     rax, [rbp+0C0h+var_D0]
0x180027f27  mov     [rsp+1C0h+var_190], rax
0x180027f2c  lea     rax, [rbp+0C0h+var_E0]
0x180027f30  mov     [rsp+1C0h+var_198], rax
0x180027f35  mov     qword ptr [rsp+1C0h+var_1A0], r14
0x180027f3a  mov     rax, [rsp+1C0h+var_158]
0x180027f3f  mov     r9d, [rax+10h]
0x180027f43  mov     r8d, edi
0x180027f46  mov     rdx, r13
0x180027f49  mov     rcx, [rsp+1C0h+var_168]
0x180027f4e  call    ?OrchestrateUpdate@COSInstaller@@AEAAJAEBUtagSusDeployData@@W4tagUpdateDeploymentAction@@KPEAUIUpdateDeploymentCallback@@PEAHPEAW4tagAutoCommitStatus@@PEAPEA_W5PEB_W@Z; COSInstaller::OrchestrateUpdate(tagSusDeployData const &,tagUpdateDeploymentAction,ulong,IUpdateDeploymentCallback *,int *,tagAutoCommitStatus *,wchar_t * *,wchar_t * *,wchar_t const *)
0x180027f53  mov     r14d, eax
0x180027f56  lea     rax, aYes; "Yes"
0x180027f5d  lea     rdi, aNo; "No"
0x180027f64  cmp     [rbp+0C0h+var_E0], ebx
0x180027f67  cmovnz  rdi, rax
0x180027f6b  mov     rdx, [rsp+1C0h+var_150]; struct _GUID *
0x180027f70  mov     ebx, [rdx+10h]
0x180027f73  lea     rcx, [rbp+0C0h+var_130]; this
0x180027f77  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180027f7c  mov     r9d, r14d
0x180027f7f  sar     r9d, 1Fh
0x180027f83  and     r9d, 0FFFFFFFEh
0x180027f87  add     r9d, 4
0x180027f8b  mov     [rsp+1C0h+var_178], rdi
0x180027f90  mov     dword ptr [rsp+1C0h+var_180], r14d
0x180027f95  mov     dword ptr [rsp+1C0h+var_188], ebx
0x180027f99  mov     [rsp+1C0h+var_190], rax
0x180027f9e  lea     rax, aRevertComplete; "Revert complete for update ID: %ws.%d R"...
0x180027fa5  mov     [rsp+1C0h+var_198], rax
0x180027faa  xor     edx, edx
0x180027fac  mov     qword ptr [rsp+1C0h+var_1A0], rdx
0x180027fb1  xor     ecx, ecx
0x180027fb3  mov     r8d, 1000h
0x180027fb9  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180027fbe  mov     rax, qword ptr [rbp+0C0h+var_DC+4]
0x180027fc2  mov     rcx, [rbp+0C0h+lpMem]
0x180027fc6  mov     edx, [rbp+0C0h+var_D0]
0x180027fc9  mov     r8d, [rbp+0C0h+var_E0]
0x180027fcd  mov     [rsp+1C0h+var_180], rax
0x180027fd2  mov     [rsp+1C0h+var_188], rcx
0x180027fd7  mov     dword ptr [rsp+1C0h+var_190], edx
0x180027fdb  mov     dword ptr [rsp+1C0h+var_198], r8d
0x180027fe0  mov     [rsp+1C0h+var_1A0], r14d; int
0x180027fe5  mov     r8, r13
0x180027fe8  mov     rdx, [rsp+1C0h+var_160]
0x180027fed  mov     rcx, [rsp+1C0h+var_168]
0x180027ff2  call    ?NotifyResult@COSInstaller@@AEAAJPEAUIUpdateDeploymentCallback@@AEBUtagSusDeployData@@W4tagDeploymentOperationNotifyType@@JHW4tagAutoCommitStatus@@PEB_W4@Z; COSInstaller::NotifyResult(IUpdateDeploymentCallback *,tagSusDeployData const &,tagDeploymentOperationNotifyType,long,int,tagAutoCommitStatus,wchar_t const *,wchar_t const *)
0x180027ff7  mov     ebx, eax
0x180027ff9  xor     eax, eax
0x180027ffb  mov     [rbp+0C0h+var_C0], rax
0x180027fff  xor     edx, edx
0x180028001  mov     [rbp+0C0h+var_B8], rdx
0x180028005  mov     ecx, edx
0x180028007  mov     [rbp+0C0h+var_B0], rdx
0x18002800b  xorps   xmm0, xmm0
0x18002800e  movups  [rbp+0C0h+var_A8], xmm0
0x180028012  movups  [rbp+0C0h+var_98], xmm0
0x180028016  movups  [rbp+0C0h+var_88], xmm0
0x18002801a  mov     [rbp+0C0h+var_78], rax
0x18002801e  lea     rdi, [r13+70h]
0x180028022  test    rdi, rdi
0x180028025  jz      short loc_18002805E
0x180028027  cmp     [rdi], dl
0x180028029  jz      short loc_18002805E
0x18002802b  lea     rdx, [rbp+0C0h+var_B8]
0x18002802f  mov     rcx, rdi
0x180028032  call    ??$DuplicateString@PEBDPEAD@@YAJPEBDPEAPEAD@Z; DuplicateString<char const *,char *>(char const *,char * *)
0x180028037  mov     rcx, [rbp+0C8h]; this
0x18002803e  xor     edx, edx
0x180028040  test    eax, eax
0x180028042  jns     short loc_18002805A
0x180028044  mov     r9d, eax; char *
0x180028047  lea     r8, aCW1SSrcClientI_1; "C:\\__w\\1\\s\\src\\Client\\inc\\Deploy"...
0x18002804e  mov     edx, 0FCh; void *
0x180028053  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180028058  xor     edx, edx
0x18002805a  mov     rcx, [rbp+0C0h+var_B0]; lpMem
0x18002805e  test    r12, r12
0x180028061  jz      short loc_1800280A4
0x180028063  cmp     [r12], dl
0x180028067  jz      short loc_1800280A4
0x180028069  test    rcx, rcx
0x18002806c  jz      short loc_180028079
0x18002806e  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180028073  xor     eax, eax
0x180028075  mov     [rbp+0C0h+var_B0], rax
0x180028079  lea     rdx, [rbp+0C0h+var_B0]
0x18002807d  mov     rcx, r12
0x180028080  call    ??$DuplicateString@PEBDPEAD@@YAJPEBDPEAPEAD@Z; DuplicateString<char const *,char *>(char const *,char * *)
0x180028085  mov     rcx, [rbp+0C8h]; this
0x18002808c  test    eax, eax
0x18002808e  jns     short loc_1800280A4
0x180028090  mov     r9d, eax; char *
0x180028093  lea     r8, aCW1SSrcClientI_1; "C:\\__w\\1\\s\\src\\Client\\inc\\Deploy"...
0x18002809a  mov     edx, 104h; void *
0x18002809f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800280a4  lea     rcx, [rbp+0C0h+var_60]; UnbiasedTime
0x1800280a8  call    cs:__imp_QueryUnbiasedInterruptTime
0x1800280ae  mov     rcx, [rbp+0C0h+var_60]
0x1800280b2  sub     rcx, [rbp+0C0h+UnbiasedTime]
0x1800280b6  mov     rax, [rbp+0C0h+var_58]
0x1800280ba  add     rax, rcx
0x1800280bd  mov     [rbp+0C0h+var_58], rax
0x1800280c1  lea     rcx, aRevert; "Revert"
0x1800280c8  mov     [rbp+0C0h+var_C0], rcx
0x1800280cc  xor     ecx, ecx
0x1800280ce  cmp     [rbp+0C0h+var_70], cl
0x1800280d1  jz      short loc_1800280DE
0x1800280d3  mov     ecx, [rbp+0C0h+var_50]
0x1800280d6  xor     edx, edx
0x1800280d8  div     rcx
0x1800280db  mov     rcx, rax
0x1800280de  mov     rax, [r13+38h]
0x1800280e2  movups  xmm0, xmmword ptr [rax+4]
0x1800280e6  movdqu  [rbp+0C0h+var_98+4], xmm0
0x1800280eb  xor     r13d, r13d
0x1800280ee  cmp     [rbp+0C0h+var_E0], r13d
0x1800280f2  setnz   byte ptr [rbp+0C0h+var_A8+9]
0x1800280f6  mov     eax, [rbp+0C0h+var_D0]
0x1800280f9  mov     dword ptr [rbp+0C0h+var_A8+0Ch], eax
0x1800280fc  mov     dword ptr [rbp+0C0h+var_A8+4], esi
0x1800280ff  mov     al, [rsp+1C0h+var_170]
0x180028103  mov     byte ptr [rbp+0C0h+var_98], al
0x180028106  mov     dword ptr [rbp+0C0h+var_88+4], ebx
0x180028109  mov     dword ptr [rbp+0C0h+var_88+8], r14d
0x18002810d  mov     dword ptr [rbp+0C0h+var_78], ecx
0x180028110  lea     rcx, [rbp+0C0h+var_C0]; struct OSDeploymentEventSummary *
0x180028114  call    ?FirePerUpdateEvent@OSDeploymentTelemetry@@SAXPEAUOSDeploymentEventSummary@@@Z; OSDeploymentTelemetry::FirePerUpdateEvent(OSDeploymentEventSummary *)
0x180028119  test    ebx, ebx
0x18002811b  jns     short loc_180028140
0x18002811d  lea     rax, aNotifyFailed; "Notify failed"
0x180028124  mov     [rsp+1C0h+var_198], rax
0x180028129  mov     [rsp+1C0h+var_1A0], ebx; int
0x18002812d  xor     edx, edx
0x18002812f  xor     ecx, ecx
0x180028131  lea     r9d, [r13+2]
0x180028135  mov     r8d, 1000h
0x18002813b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180028140  test    r14d, r14d
0x180028143  jns     short loc_180028152
0x180028145  mov     dword ptr [rbp+0C0h+var_DC], r14d
0x180028149  cmp     [rbp+0C0h+arg_28], r13d
0x180028150  jz      short loc_1800281AC
0x180028152  mov     rcx, [rbp+0C0h+var_B0]; lpMem
0x180028156  test    rcx, rcx
0x180028159  jz      short loc_180028164
0x18002815b  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180028160  mov     [rbp+0C0h+var_B0], r13
0x180028164  mov     rcx, [rbp+0C0h+var_B8]; lpMem
0x180028168  test    rcx, rcx
0x18002816b  jz      short loc_180028176
0x18002816d  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180028172  mov     [rbp+0C0h+var_B8], r13
0x180028176  mov     rcx, qword ptr [rbp+0C0h+var_DC+4]; lpMem
0x18002817a  test    rcx, rcx
0x18002817d  jz      short loc_180028188
0x18002817f  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180028184  mov     qword ptr [rbp+0C0h+var_DC+4], r13
0x180028188  mov     rcx, [rbp+0C0h+lpMem]; lpMem
0x18002818c  test    rcx, rcx
0x18002818f  jz      short loc_180028196
0x180028191  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180028196  inc     esi
0x180028198  cmp     esi, r15d
0x18002819b  jnb     short loc_1800281F0
0x18002819d  mov     rbx, [rsp+1C0h+var_148]
0x1800281a2  mov     r14, [rsp+1C0h+var_160]
0x1800281a7  jmp     loc_180027E57
0x1800281ac  mov     rcx, [rbp+0C0h+var_B0]; lpMem
0x1800281b0  test    rcx, rcx
0x1800281b3  jz      short loc_1800281BE
0x1800281b5  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x1800281ba  mov     [rbp+0C0h+var_B0], r13
0x1800281be  mov     rcx, [rbp+0C0h+var_B8]; lpMem
0x1800281c2  test    rcx, rcx
0x1800281c5  jz      short loc_1800281D0
0x1800281c7  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x1800281cc  mov     [rbp+0C0h+var_B8], r13
0x1800281d0  mov     rcx, qword ptr [rbp+0C0h+var_DC+4]; lpMem
0x1800281d4  test    rcx, rcx
0x1800281d7  jz      short loc_1800281E2
0x1800281d9  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x1800281de  mov     qword ptr [rbp+0C0h+var_DC+4], r13
0x1800281e2  mov     rcx, [rbp+0C0h+lpMem]; lpMem
0x1800281e6  test    rcx, rcx
0x1800281e9  jz      short loc_1800281F0
0x1800281eb  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x1800281f0  mov     ebx, dword ptr [rbp+0C0h+var_DC]
0x1800281f3  test    ebx, ebx
0x1800281f5  jns     short loc_180028214
0x1800281f7  mov     rcx, [rbp+0C8h]; this
0x1800281fe  mov     r9d, ebx; char *
  ... truncated ...
```
