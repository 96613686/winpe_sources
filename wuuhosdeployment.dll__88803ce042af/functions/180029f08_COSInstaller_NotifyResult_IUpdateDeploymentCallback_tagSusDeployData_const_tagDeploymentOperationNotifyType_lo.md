# COSInstaller::NotifyResult(IUpdateDeploymentCallback *,tagSusDeployData const &,tagDeploymentOperationNotifyType,long,int,tagAutoCommitStatus,wchar_t const *,wchar_t const *)

- ea: `0x180029f08`
- end: `0x18002a215`
- name: `?NotifyResult@COSInstaller@@AEAAJPEAUIUpdateDeploymentCallback@@AEBUtagSusDeployData@@W4tagDeploymentOperationNotifyType@@JHW4tagAutoCommitStatus@@PEB_W4@Z`
- size: `781`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800276d0`
- `0x180027d78`
- `0x180028268`

## callees

- `0x180003950`
- `0x18000956c`
- `0x18000a448`
- `0x18000af44`
- `0x180029f08`
- `0x18002b5a8`
- `0x180031804`
- `0x180032838`
- `0x180042630`
- `0x180049260`
- `0x1800492e0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18002a01a`
- `OLEAUT32!__imp_SysStringLen` at `0x18002a01a`

## string_xrefs

- `0x180029fa9`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18002a1a3`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18002a098`: `Update with ID: %ws.%d %ws require explicit commit call`
- `0x18002a14a`: `COSInstaller::NotifyResult`
- `0x18002a11a`: `(deploymentCompleteData.rgpszDriverRecoveryIds == nullptr && deploymentCompleteData.cDriverRecoveryIds == 0) || (deploymentCompleteData.rgpszDriverRecoveryIds != nullptr && deploymentCompleteData.cDriverRecoveryIds != 0)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall COSInstaller::NotifyResult(
        COSInstaller *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        wchar_t *a8,
        wchar_t *a9)
{
  int v12; // ebx
  __int64 v13; // rdx
  __int64 v14; // rdx
  unsigned int v15; // edx
  unsigned int v16; // ecx
  __int64 v17; // rax
  int v19; // [rsp+20h] [rbp-E0h]
  __int128 v20; // [rsp+50h] [rbp-B0h] BYREF
  int v21; // [rsp+60h] [rbp-A0h]
  __int64 v22; // [rsp+70h] [rbp-90h]
  wchar_t **v23; // [rsp+78h] [rbp-88h]
  int *v24; // [rsp+80h] [rbp-80h]
  char v25; // [rsp+88h] [rbp-78h]
  char v26[80]; // [rsp+90h] [rbp-70h] BYREF
  int v27; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t *v28[28]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v27 = 0;
  memset(v28, 0, 0xD8u);
  v22 = 0;
  v19 = 0;
  WUTrace(0, 0, 4096, 4);
  if ( !a2 )
  {
    v12 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53E,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)0x80004003LL,
      0);
    return (unsigned int)v12;
  }
  v23 = v28;
  v24 = &v27;
  v25 = 1;
  LODWORD(v28[0]) = 2;
  HIDWORD(v28[4]) = a5;
  LODWORD(v28[2]) = a6;
  if ( a5 == -2145116152 )
  {
    LODWORD(v28[1]) = 2;
  }
  else if ( a5 )
  {
    LODWORD(v28[1]) = 0;
  }
  else
  {
    LODWORD(v28[1]) = a6 != 0 ? 3 : 1;
    if ( SysStringLen(*(BSTR *)(a3 + 24)) )
      DuplicateString<wchar_t *,wchar_t *>(*(_QWORD *)(a3 + 24), &v28[19]);
    if ( a6 )
    {
      v13 = *(_QWORD *)(a3 + 56);
      if ( !a9 )
      {
        v12 = -2147467261;
        v14 = 1383;
        goto LABEL_21;
      }
      HIDWORD(v28[2]) = a7;
      LODWORD(v28[3]) = a7 == 2;
      Trace::GuidToString::GuidToString((Trace::GuidToString *)v26, (const struct _GUID *)(v13 + 4));
      WUTrace(0, 0, 4096, 4);
      v12 = COSInstaller::PopulateReportingCookieData(a1, (const struct tagSusDeployData *)a3, a9, a8, &v28[7]);
      v27 = v12;
      if ( v12 < 0 )
      {
        v14 = 1401;
        goto LABEL_21;
      }
    }
  }
  if ( v28[20] )
  {
    if ( !LODWORD(v28[21]) )
    {
LABEL_18:
      v19 = 0;
      WUTrace("COSInstaller::NotifyResult", 1416, 32, 3);
      WUTelemetryAssertTriggered(v16, v15);
    }
  }
  else if ( LODWORD(v28[21]) )
  {
    goto LABEL_18;
  }
  v17 = *(_QWORD *)(a3 + 56);
  v20 = *(_OWORD *)(v17 + 4);
  v21 = *(_DWORD *)(v17 + 20);
  v12 = (*(__int64 (__fastcall **)(__int64, __int128 *, wchar_t **, __int64))(*(_QWORD *)a2 + 24LL))(
          a2,
          &v20,
          v28,
          a3 + 32);
  v27 = v12;
  if ( v12 >= 0 )
  {
    v12 = 0;
    goto LABEL_23;
  }
  v14 = 1422;
LABEL_21:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
    (const char *)(unsigned int)v12,
    v19);
LABEL_23:
  if ( LODWORD(v28[0]) == 2 )
    ResetDeploymentComplete((struct tagUpdateDeploymentCompleteNotifyType *)&v28[1]);
  WUTrace(0, 0, 4096, 4);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180029f08  mov     [rsp-8+arg_18], rbx
0x180029f0d  push    rbp
0x180029f0e  push    rsi
0x180029f0f  push    rdi
0x180029f10  push    r12
0x180029f12  push    r13
0x180029f14  push    r14
0x180029f16  push    r15
0x180029f18  lea     rbp, [rsp-0E0h]
0x180029f20  sub     rsp, 1E0h
0x180029f27  mov     rax, cs:__security_cookie
0x180029f2e  xor     rax, rsp
0x180029f31  mov     [rbp+110h+var_40], rax
0x180029f38  mov     rdi, r8
0x180029f3b  mov     rsi, rdx
0x180029f3e  mov     r12, rcx
0x180029f41  mov     r15d, [rbp+110h+arg_30]
0x180029f48  mov     r13, [rbp+110h+arg_38]
0x180029f4f  mov     r14, [rbp+110h+arg_40]
0x180029f56  xor     ebx, ebx
0x180029f58  mov     [rbp+110h+var_130], ebx
0x180029f5b  xor     edx, edx; Val
0x180029f5d  mov     r8d, 0D8h; Size
0x180029f63  lea     rcx, [rbp+110h+var_120]; void *
0x180029f67  call    memset
0x180029f6c  mov     [rsp+210h+var_1A0], rbx
0x180029f71  lea     rax, aEnterDeploymen_0; "Enter deployment handler NotifyResult"
0x180029f78  mov     [rsp+210h+var_1E8], rax
0x180029f7d  mov     [rsp+210h+var_1F0], rbx; int
0x180029f82  xor     edx, edx
0x180029f84  xor     ecx, ecx
0x180029f86  lea     r9d, [rbx+4]
0x180029f8a  mov     r8d, 1000h
0x180029f90  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180029f95  test    rsi, rsi
0x180029f98  jnz     short loc_180029FBF
0x180029f9a  mov     rcx, [rbp+118h]; this
0x180029fa1  mov     ebx, 80004003h
0x180029fa6  mov     r9d, ebx; char *
0x180029fa9  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180029fb0  mov     edx, 53Eh; void *
0x180029fb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029fba  jmp     loc_18002A1E9
0x180029fbf  lea     rax, [rbp+110h+var_120]
0x180029fc3  mov     [rsp+210h+var_198], rax
0x180029fc8  lea     rax, [rbp+110h+var_130]
0x180029fcc  mov     [rbp+110h+var_190], rax
0x180029fd0  mov     [rbp+110h+var_188], 1
0x180029fd4  mov     edx, 2
0x180029fd9  mov     [rbp+110h+var_120], edx
0x180029fdc  mov     eax, [rbp+110h+arg_20]
0x180029fe2  mov     [rbp+110h+var_FC], eax
0x180029fe5  mov     ebx, [rbp+110h+arg_28]
0x180029feb  mov     [rbp+110h+var_110], ebx
0x180029fee  cmp     eax, 80242008h
0x180029ff3  jz      loc_18002A0ED
0x180029ff9  test    eax, eax
0x180029ffb  jz      short loc_18002A009
0x180029ffd  mov     [rbp+110h+var_118], 0
0x18002a004  jmp     loc_18002A0F0
0x18002a009  mov     eax, ebx
0x18002a00b  neg     eax
0x18002a00d  sbb     ecx, ecx
0x18002a00f  and     ecx, edx
0x18002a011  inc     ecx
0x18002a013  mov     [rbp+110h+var_118], ecx
0x18002a016  mov     rcx, [rdi+18h]; pbstr
0x18002a01a  call    cs:__imp_SysStringLen
0x18002a020  test    eax, eax
0x18002a022  jz      short loc_18002A034
0x18002a024  lea     rdx, [rbp+110h+var_88]
0x18002a02b  mov     rcx, [rdi+18h]
0x18002a02f  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18002a034  test    ebx, ebx
0x18002a036  jz      loc_18002A0F0
0x18002a03c  mov     rdx, [rdi+38h]
0x18002a040  test    r14, r14
0x18002a043  jnz     short loc_18002A054
0x18002a045  mov     ebx, 80004003h
0x18002a04a  mov     edx, 567h
0x18002a04f  jmp     loc_18002A199
0x18002a054  mov     [rbp+110h+var_10C], r15d
0x18002a058  xor     eax, eax
0x18002a05a  cmp     r15d, 2
0x18002a05e  setz    al
0x18002a061  mov     [rbp+110h+var_108], eax
0x18002a064  add     rdx, 4; struct _GUID *
0x18002a068  mov     ebx, [rdx+10h]
0x18002a06b  lea     rcx, [rbp+110h+var_180]; this
0x18002a06f  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18002a074  lea     rdx, aDoesNot; "does not"
0x18002a07b  lea     rcx, aDoes; "does"
0x18002a082  cmp     r15d, 1
0x18002a086  cmovz   rcx, rdx
0x18002a08a  mov     [rsp+210h+var_1D0], rcx
0x18002a08f  mov     dword ptr [rsp+210h+var_1D8], ebx
0x18002a093  mov     [rsp+210h+var_1E0], rax
0x18002a098  lea     rax, aUpdateWithIdWs; "Update with ID: %ws.%d %ws require expl"...
0x18002a09f  mov     [rsp+210h+var_1E8], rax
0x18002a0a4  mov     [rsp+210h+var_1F0], 0
0x18002a0ad  xor     edx, edx
0x18002a0af  xor     ecx, ecx
0x18002a0b1  lea     r9d, [rdx+4]
0x18002a0b5  mov     r8d, 1000h
0x18002a0bb  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002a0c0  lea     rax, [rbp+110h+var_E8]
0x18002a0c4  mov     [rsp+210h+var_1F0], rax; wchar_t **
0x18002a0c9  mov     r9, r13; wchar_t *
0x18002a0cc  mov     r8, r14; wchar_t *
0x18002a0cf  mov     rdx, rdi; struct tagSusDeployData *
0x18002a0d2  mov     rcx, r12; this
0x18002a0d5  call    ?PopulateReportingCookieData@COSInstaller@@AEAAJAEBUtagSusDeployData@@PEB_W1PEAPEA_W@Z; COSInstaller::PopulateReportingCookieData(tagSusDeployData const &,wchar_t const *,wchar_t const *,wchar_t * *)
0x18002a0da  mov     ebx, eax
0x18002a0dc  mov     [rbp+110h+var_130], eax
0x18002a0df  test    eax, eax
0x18002a0e1  jns     short loc_18002A0F0
0x18002a0e3  mov     edx, 579h
0x18002a0e8  jmp     loc_18002A199
0x18002a0ed  mov     [rbp+110h+var_118], edx
0x18002a0f0  cmp     [rbp+110h+var_80], 0
0x18002a0f8  jnz     short loc_18002A105
0x18002a0fa  cmp     [rbp+110h+var_78], 0
0x18002a101  jz      short loc_18002A15B
0x18002a103  jmp     short loc_18002A10E
0x18002a105  cmp     [rbp+110h+var_78], 0
0x18002a10c  jnz     short loc_18002A15B
0x18002a10e  lea     rax, aFailed; "Failed"
0x18002a115  mov     [rsp+210h+var_1D8], rax
0x18002a11a  lea     rax, aDeploymentcomp; "(deploymentCompleteData.rgpszDriverReco"...
0x18002a121  mov     [rsp+210h+var_1E0], rax
0x18002a126  lea     rax, aTelemetryasser; "TelemetryAssert (%ws): %ws"
0x18002a12d  mov     [rsp+210h+var_1E8], rax
0x18002a132  mov     [rsp+210h+var_1F0], 0; int
0x18002a13b  mov     edx, 588h
0x18002a140  mov     r9d, 3
0x18002a146  lea     r8d, [r9+1Dh]
0x18002a14a  lea     rcx, aCosinstallerNo; "COSInstaller::NotifyResult"
0x18002a151  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002a156  call    ?WUTelemetryAssertTriggered@@YAXII@Z; WUTelemetryAssertTriggered(uint,uint)
0x18002a15b  mov     rax, [rdi+38h]
0x18002a15f  movups  xmm0, xmmword ptr [rax+4]
0x18002a163  movaps  [rsp+210h+var_1C0], xmm0
0x18002a168  mov     eax, [rax+14h]
0x18002a16b  mov     [rsp+210h+var_1B0], eax
0x18002a16f  lea     r9, [rdi+20h]
0x18002a173  mov     rax, [rsi]
0x18002a176  lea     r8, [rbp+110h+var_120]
0x18002a17a  lea     rdx, [rsp+210h+var_1C0]
0x18002a17f  mov     rcx, rsi
0x18002a182  mov     rax, [rax+18h]
0x18002a186  call    _guard_dispatch_icall
0x18002a18b  mov     ebx, eax
0x18002a18d  mov     [rbp+110h+var_130], eax
0x18002a190  test    eax, eax
0x18002a192  jns     short loc_18002A1B1
0x18002a194  mov     edx, 58Eh; void *
0x18002a199  mov     rcx, [rbp+118h]; this
0x18002a1a0  mov     r9d, ebx; char *
0x18002a1a3  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18002a1aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a1af  jmp     short loc_18002A1B3
0x18002a1b1  xor     ebx, ebx
0x18002a1b3  cmp     [rbp+110h+var_120], 2
0x18002a1b7  jnz     short loc_18002A1C2
0x18002a1b9  lea     rcx, [rbp+110h+var_118]; struct tagUpdateDeploymentCompleteNotifyType *
0x18002a1bd  call    ?ResetDeploymentComplete@@YAXPEAUtagUpdateDeploymentCompleteNotifyType@@@Z; ResetDeploymentComplete(tagUpdateDeploymentCompleteNotifyType *)
0x18002a1c2  lea     rax, aLeaveDeploymen; "Leave deployment handler NotifyResult"
0x18002a1c9  mov     [rsp+210h+var_1E8], rax
0x18002a1ce  mov     ecx, [rbp+110h+var_130]
0x18002a1d1  mov     dword ptr [rsp+210h+var_1F0], ecx
0x18002a1d5  xor     edx, edx
0x18002a1d7  xor     ecx, ecx
0x18002a1d9  lea     r9d, [rdx+4]
0x18002a1dd  mov     r8d, 1000h
0x18002a1e3  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002a1e8  nop
0x18002a1e9  mov     eax, ebx
0x18002a1eb  mov     rcx, [rbp+110h+var_40]
0x18002a1f2  xor     rcx, rsp; StackCookie
0x18002a1f5  call    __security_check_cookie
0x18002a1fa  mov     rbx, [rsp+210h+arg_18]
0x18002a202  add     rsp, 1E0h
0x18002a209  pop     r15
0x18002a20b  pop     r14
0x18002a20d  pop     r13
0x18002a20f  pop     r12
0x18002a211  pop     rdi
0x18002a212  pop     rsi
0x18002a213  pop     rbp
0x18002a214  retn
```
