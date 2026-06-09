# COSInstaller::Install(tagOperationContext *,ulong,tagSusDeployData * const,IUpdateDeploymentCallback *,tagDeploymentFailOptions,char const *)

- ea: `0x1800276d0`
- end: `0x180027d72`
- name: `?Install@COSInstaller@@AEAAJPEAUtagOperationContext@@KQEAUtagSusDeployData@@PEAUIUpdateDeploymentCallback@@W4tagDeploymentFailOptions@@PEBD@Z`
- size: `1698`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180027430`

## callees

- `0x180003950`
- `0x180005f64`
- `0x18000956c`
- `0x18000a448`
- `0x18000a4f4`
- `0x18000b2bc`
- `0x18000c0b4`
- `0x180024660`
- `0x180026db4`
- `0x1800276d0`
- `0x180028ea8`
- `0x180029f08`
- `0x18002a83c`
- `0x18002daa8`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800278a6`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180027b57`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800278a6`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180027b57`
- `OLEAUT32!__imp_SysStringLen` at `0x1800278b0`
- `OLEAUT32!__imp_SysStringLen` at `0x1800278b0`

## string_xrefs

- `0x180027b7c`: `Install`
- `0x180027792`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x180027d1a`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x180027740`: `Enter Deployment handler install. Count of updates = %lu`
- `0x1800278e0`: `Skipping installing update ID: %ws as the dependent merged update failed to install`
- `0x18002782b`: `Merge updates complete`
- `0x18002793d`: `Preparing to install update ID: %ws.%d Update was %ws`
- `0x180027a2f`: `Install complete for update ID: %ws.%d Return code is 0x%08lX. Requires Reboot:%ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall COSInstaller::Install(
        COSInstaller *a1,
        __int64 a2,
        unsigned int a3,
        struct tagSusDeployData *a4,
        struct IUpdateDeploymentCallback *a5,
        int a6,
        _BYTE *a7)
{
  COSInstaller *v7; // rdi
  __int64 v8; // r15
  unsigned int v9; // ebx
  __int64 v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // rdx
  unsigned int v13; // r14d
  char *v14; // r13
  const struct tagDSGlobalUpdateId *v15; // rsi
  UINT v16; // eax
  UINT v17; // r12d
  int v18; // r15d
  _QWORD *v19; // rbx
  int v20; // edi
  void *v21; // rcx
  int v22; // eax
  int v23; // eax
  ULONGLONG v24; // rax
  unsigned __int64 v25; // rcx
  int v27; // [rsp+20h] [rbp-E0h]
  bool v28; // [rsp+50h] [rbp-B0h]
  _QWORD v31[7]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v32[112]; // [rsp+B0h] [rbp-50h] BYREF
  int v33; // [rsp+120h] [rbp+20h] BYREF
  struct tagSusDeployData *v34; // [rsp+128h] [rbp+28h] BYREF
  char v35; // [rsp+130h] [rbp+30h] BYREF
  bool v36; // [rsp+131h] [rbp+31h] BYREF
  unsigned int v37; // [rsp+138h] [rbp+38h] BYREF
  char *v38; // [rsp+140h] [rbp+40h] BYREF
  void *v39; // [rsp+148h] [rbp+48h] BYREF
  int v40; // [rsp+150h] [rbp+50h] BYREF
  void *v41; // [rsp+158h] [rbp+58h] BYREF
  void *lpMem; // [rsp+160h] [rbp+60h] BYREF
  const char *v43; // [rsp+170h] [rbp+70h] BYREF
  void *v44; // [rsp+178h] [rbp+78h] BYREF
  void *v45; // [rsp+180h] [rbp+80h] BYREF
  __int128 v46; // [rsp+188h] [rbp+88h]
  _OWORD v47[2]; // [rsp+198h] [rbp+98h] BYREF
  __int64 v48; // [rsp+1B8h] [rbp+B8h]
  _BYTE v49[8]; // [rsp+1C0h] [rbp+C0h] BYREF
  ULONGLONG UnbiasedTime; // [rsp+1C8h] [rbp+C8h] BYREF
  ULONGLONG v51; // [rsp+1D0h] [rbp+D0h] BYREF
  ULONGLONG v52; // [rsp+1D8h] [rbp+D8h]
  unsigned int v53; // [rsp+1E0h] [rbp+E0h]
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v7 = a1;
  v37 = a3;
  v34 = a4;
  v8 = (__int64)a5;
  LODWORD(v38) = 0;
  v36 = 0;
  v35 = 0;
  lpMem = 0;
  v27 = 0;
  WUTrace(0, 0, 4096, 4);
  if ( !a5 )
  {
    v9 = -2147467261;
    v10 = 225;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)v9,
      0);
    goto LABEL_67;
  }
  v11 = v37;
  if ( !v37 )
  {
    v9 = -2145124316;
    v10 = 228;
    goto LABEL_5;
  }
  v31[5] = 1;
  v31[0] = &v35;
  v31[1] = v7;
  v31[2] = &v37;
  v31[3] = &v34;
  v31[4] = &v38;
  if ( v37 > 1 )
  {
    LODWORD(v38) = COSInstaller::MergeUpdates(v7, v37, v34, a5, &v36, (wchar_t **)&lpMem);
    v27 = (int)v38;
    WUTrace(0, 0, 4096, (((int)v38 >> 31) & 0xFFFFFFFE) + 4);
    v9 = (unsigned int)v38;
    if ( (int)v38 < 0 )
    {
      v12 = 261;
      goto LABEL_64;
    }
    v11 = v37;
  }
  v13 = 0;
  if ( v11 )
  {
    while ( 1 )
    {
      v14 = (char *)v34 + 296 * v13;
      v33 = 0;
      v40 = 0;
      v15 = (const struct tagDSGlobalUpdateId *)(*((_QWORD *)v14 + 7) + 4LL);
      v41 = 0;
      v39 = 0;
      CWUPerfTimer::CWUPerfTimer((CWUPerfTimer *)v49);
      v52 = 0;
      QueryUnbiasedInterruptTime(&UnbiasedTime);
      v16 = SysStringLen(*((BSTR *)v14 + 3));
      v17 = v16;
      v28 = v16 != 0;
      if ( !v35 )
        goto LABEL_14;
      if ( v16 )
      {
        v18 = -2145079035;
        Trace::UpdateIdToString::UpdateIdToString((Trace::UpdateIdToString *)v32, v15);
        WUTrace(0, 0, 4096, 3);
      }
      else
      {
LABEL_14:
        Trace::GuidToString::GuidToString((Trace::GuidToString *)v32, (const struct _GUID *)v15);
        WUTrace(0, 0, 4096, 4);
        v19 = (_QWORD *)((unsigned __int64)lpMem & -(__int64)(v17 != 0));
        if ( v39 )
        {
          CSusBaseAllocTag<942762101>::operator delete(v39);
          v39 = 0;
        }
        if ( v41 )
        {
          CSusBaseAllocTag<942762101>::operator delete(v41);
          v41 = 0;
        }
        v18 = COSInstaller::OrchestrateUpdate(
                (__int64)v7,
                (__int64)v14,
                1,
                *(_DWORD *)(a2 + 16),
                v8,
                &v33,
                (__int64)&v40,
                (__int64)&v41,
                (__int64)&v39,
                v19);
        Trace::GuidToString::GuidToString((Trace::GuidToString *)v32, (const struct _GUID *)v15);
        WUTrace(0, 0, 4096, ((v18 >> 31) & 0xFFFFFFFE) + 4);
        v7 = a1;
      }
      v27 = v18;
      v20 = COSInstaller::NotifyResult(v7, a5, v14);
      v43 = 0;
      v44 = 0;
      v21 = 0;
      v45 = 0;
      v46 = 0;
      memset(v47, 0, sizeof(v47));
      v48 = 0;
      if ( v14 != (char *)-112LL && v14[112] )
      {
        v22 = DuplicateString<char const *,char *>(v14 + 112, &v44);
        if ( v22 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xFC,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\DeploymentMiscTelemetry.h",
            (const char *)(unsigned int)v22,
            v18);
        v21 = v45;
      }
      if ( a7 && *a7 )
      {
        if ( v21 )
        {
          CSusBaseAllocTag<942762101>::operator delete(v21);
          v45 = 0;
        }
        v23 = DuplicateString<char const *,char *>(a7, &v45);
        if ( v23 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x104,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\DeploymentMiscTelemetry.h",
            (const char *)(unsigned int)v23,
            v27);
      }
      QueryUnbiasedInterruptTime(&v51);
      v24 = v51 - UnbiasedTime + v52;
      v52 = v24;
      v43 = "Install";
      if ( v49[0] )
        v25 = v24 / v53;
      else
        LODWORD(v25) = 0;
      *(_OWORD *)((char *)v47 + 4) = *(_OWORD *)(*((_QWORD *)v14 + 7) + 4LL);
      BYTE9(v46) = v33 != 0;
      HIDWORD(v46) = v40;
      DWORD1(v46) = v13;
      LOBYTE(v47[0]) = v28;
      *(_QWORD *)((char *)&v47[1] + 4) = __PAIR64__(v18, v20);
      LODWORD(v48) = v25;
      OSDeploymentTelemetry::FirePerUpdateEvent((struct OSDeploymentEventSummary *)&v43);
      if ( v20 < 0 )
      {
        v27 = v20;
        WUTrace(0, 0, 4096, 2);
      }
      if ( v18 < 0 )
      {
        LODWORD(v38) = v18;
        if ( v17 )
          v35 = 1;
        if ( !a6 )
          break;
      }
      if ( v45 )
      {
        CSusBaseAllocTag<942762101>::operator delete(v45);
        v45 = 0;
      }
      if ( v44 )
      {
        CSusBaseAllocTag<942762101>::operator delete(v44);
        v44 = 0;
      }
      if ( v39 )
      {
        CSusBaseAllocTag<942762101>::operator delete(v39);
        v39 = 0;
      }
      if ( v41 )
      {
        CSusBaseAllocTag<942762101>::operator delete(v41);
        v41 = 0;
      }
      if ( ++v13 >= v37 )
        goto LABEL_57;
      v7 = a1;
      v8 = (__int64)a5;
    }
    if ( v45 )
    {
      CSusBaseAllocTag<942762101>::operator delete(v45);
      v45 = 0;
    }
    if ( v44 )
    {
      CSusBaseAllocTag<942762101>::operator delete(v44);
      v44 = 0;
    }
    if ( v39 )
    {
      CSusBaseAllocTag<942762101>::operator delete(v39);
      v39 = 0;
    }
    if ( v41 )
      CSusBaseAllocTag<942762101>::operator delete(v41);
  }
LABEL_57:
  v9 = (unsigned int)v38;
  if ( (int)v38 >= 0 )
  {
    v9 = 0;
    goto LABEL_66;
  }
  if ( (_DWORD)v38 == -2145116147
    || (_DWORD)v38 == -2147024894
    || (_DWORD)v38 == -1047526943
    || (unsigned int)((_DWORD)v38 + 1047526898) <= 1
    || (_DWORD)v38 == -1047526903 )
  {
    goto LABEL_66;
  }
  v12 = 385;
LABEL_64:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
    (const char *)v9,
    v27);
LABEL_66:
  wil::details::lambda_call__lambda_7395df8b9930ce16049de7179146d5a9___::_lambda_call__lambda_7395df8b9930ce16049de7179146d5a9___(v31);
LABEL_67:
  if ( lpMem )
    CSusBaseAllocTag<942762101>::operator delete(lpMem);
  return v9;
}

```

## disassembly

```asm
0x1800276d0  push    rbp
0x1800276d2  push    rbx
0x1800276d3  push    rsi
0x1800276d4  push    rdi
0x1800276d5  push    r12
0x1800276d7  push    r13
0x1800276d9  push    r14
0x1800276db  push    r15
0x1800276dd  lea     rbp, [rsp-0F8h]
0x1800276e5  sub     rsp, 1F8h
0x1800276ec  mov     rax, cs:__security_cookie
0x1800276f3  xor     rax, rsp
0x1800276f6  mov     [rbp+130h+var_48], rax
0x1800276fd  mov     [rsp+230h+var_1C8], rdx
0x180027702  mov     rdi, rcx
0x180027705  mov     [rsp+230h+var_1D8], rcx
0x18002770a  mov     [rbp+130h+var_F8], r8d
0x18002770e  mov     [rbp+130h+var_108], r9
0x180027712  mov     r15, [rbp+130h+arg_20]
0x180027719  mov     [rsp+230h+var_1D0], r15
0x18002771e  mov     rbx, [rbp+130h+arg_30]
0x180027725  mov     [rsp+230h+var_1C0], rbx
0x18002772a  xor     esi, esi
0x18002772c  mov     dword ptr [rbp+130h+var_F0], esi
0x18002772f  mov     [rbp+130h+var_FF], sil
0x180027733  mov     [rbp+130h+var_100], sil
0x180027737  mov     [rbp+130h+lpMem], rsi
0x18002773b  mov     dword ptr [rsp+230h+var_200], r8d
0x180027740  lea     rax, aEnterDeploymen_1; "Enter Deployment handler install. Count"...
0x180027747  mov     [rsp+230h+var_208], rax
0x18002774c  mov     [rsp+230h+var_210], rsi; int
0x180027751  mov     ebx, 1000h
0x180027756  lea     r9d, [rsi+4]
0x18002775a  mov     r8d, ebx
0x18002775d  xor     edx, edx
0x18002775f  xor     ecx, ecx
0x180027761  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180027766  test    r15, r15
0x180027769  jnz     short loc_180027777
0x18002776b  mov     ebx, 80004003h
0x180027770  mov     edx, 0E1h
0x180027775  jmp     short loc_180027788
0x180027777  mov     eax, [rbp+130h+var_F8]
0x18002777a  test    eax, eax
0x18002777c  jnz     short loc_1800277A3
0x18002777e  mov     ebx, 80240024h
0x180027783  mov     edx, 0E4h; void *
0x180027788  mov     rcx, [rbp+138h]; this
0x18002778f  mov     r9d, ebx; char *
0x180027792  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180027799  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002779e  jmp     loc_180027D3F
0x1800277a3  xorps   xmm0, xmm0
0x1800277a6  movups  [rsp+230h+var_1B8], xmm0
0x1800277ab  movups  [rbp+130h+var_1A8], xmm0
0x1800277af  movups  [rbp+130h+var_198], xmm0
0x1800277b3  lea     rcx, [rbp+130h+var_100]
0x1800277b7  mov     qword ptr [rsp+230h+var_1B8], rcx
0x1800277bc  mov     qword ptr [rbp+130h+var_1B8+8], rdi
0x1800277c0  lea     rcx, [rbp+130h+var_F8]
0x1800277c4  mov     qword ptr [rbp+130h+var_1A8], rcx
0x1800277c8  lea     rcx, [rbp+130h+var_108]
0x1800277cc  mov     qword ptr [rbp+130h+var_1A8+8], rcx
0x1800277d0  lea     rcx, [rbp+130h+var_F0]
0x1800277d4  mov     qword ptr [rbp+130h+var_198], rcx
0x1800277d8  mov     byte ptr [rbp+130h+var_198+8], 1
0x1800277dc  cmp     eax, 1
0x1800277df  jbe     short loc_18002785B
0x1800277e1  mov     rcx, [rbp+130h+lpMem]; lpMem
0x1800277e5  test    rcx, rcx
0x1800277e8  jz      short loc_1800277F6
0x1800277ea  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x1800277ef  mov     [rbp+130h+lpMem], rsi
0x1800277f3  mov     eax, [rbp+130h+var_F8]
0x1800277f6  lea     rcx, [rbp+130h+lpMem]
0x1800277fa  mov     [rsp+230h+var_208], rcx; wchar_t **
0x1800277ff  lea     rcx, [rbp+130h+var_FF]
0x180027803  mov     [rsp+230h+var_210], rcx; bool *
0x180027808  mov     r9, r15; struct IUpdateDeploymentCallback *
0x18002780b  mov     r8, [rbp+130h+var_108]; struct tagSusDeployData *
0x18002780f  mov     edx, eax; unsigned int
0x180027811  mov     rcx, rdi; this
0x180027814  call    ?MergeUpdates@COSInstaller@@AEAAJKQEAUtagSusDeployData@@PEAUIUpdateDeploymentCallback@@PEA_NPEAPEA_W@Z; COSInstaller::MergeUpdates(ulong,tagSusDeployData * const,IUpdateDeploymentCallback *,bool *,wchar_t * *)
0x180027819  mov     dword ptr [rbp+130h+var_F0], eax
0x18002781c  mov     r9d, eax
0x18002781f  sar     r9d, 1Fh
0x180027823  and     r9d, 0FFFFFFFEh
0x180027827  add     r9d, 4
0x18002782b  lea     rcx, aMergeUpdatesCo; "Merge updates complete"
0x180027832  mov     [rsp+230h+var_208], rcx
0x180027837  mov     dword ptr [rsp+230h+var_210], eax
0x18002783b  mov     r8d, ebx
0x18002783e  xor     edx, edx
0x180027840  xor     ecx, ecx
0x180027842  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180027847  mov     ebx, dword ptr [rbp+130h+var_F0]
0x18002784a  test    ebx, ebx
0x18002784c  jns     short loc_180027858
0x18002784e  mov     edx, 105h
0x180027853  jmp     loc_180027D1A
0x180027858  mov     eax, [rbp+130h+var_F8]
0x18002785b  mov     r14d, esi
0x18002785e  test    eax, eax
0x180027860  jz      loc_180027CE3
0x180027866  mov     eax, r14d
0x180027869  imul    r13, rax, 128h
0x180027870  add     r13, [rbp+130h+var_108]
0x180027874  mov     [rbp+130h+var_110], esi
0x180027877  mov     [rbp+130h+var_E0], esi
0x18002787a  mov     rsi, [r13+38h]
0x18002787e  add     rsi, 4
0x180027882  xor     ebx, ebx
0x180027884  mov     [rbp+130h+var_D8], rbx
0x180027888  mov     [rbp+130h+var_E8], rbx
0x18002788c  lea     rcx, [rbp+130h+var_70]; this
0x180027893  call    ??0CWUPerfTimer@@QEAA@XZ; CWUPerfTimer::CWUPerfTimer(void)
0x180027898  mov     [rbp+130h+var_58], rbx
0x18002789f  lea     rcx, [rbp+130h+UnbiasedTime]; UnbiasedTime
0x1800278a6  call    cs:__imp_QueryUnbiasedInterruptTime
0x1800278ac  mov     rcx, [r13+18h]; pbstr
0x1800278b0  call    cs:__imp_SysStringLen
0x1800278b6  mov     r12d, eax
0x1800278b9  test    eax, eax
0x1800278bb  setnz   [rsp+230h+var_1E0]
0x1800278c0  cmp     [rbp+130h+var_100], bl
0x1800278c3  jz      short loc_18002790B
0x1800278c5  test    eax, eax
0x1800278c7  jz      short loc_18002790B
0x1800278c9  mov     r15d, 8024B105h
0x1800278cf  mov     rdx, rsi; struct tagDSGlobalUpdateId *
0x1800278d2  lea     rcx, [rbp+130h+var_180]; this
0x1800278d6  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x1800278db  mov     [rsp+230h+var_200], rax
0x1800278e0  lea     rax, aSkippingInstal; "Skipping installing update ID: %ws as t"...
0x1800278e7  mov     [rsp+230h+var_208], rax
0x1800278ec  xor     esi, esi
0x1800278ee  mov     [rsp+230h+var_210], rsi
0x1800278f3  xor     edx, edx
0x1800278f5  xor     ecx, ecx
0x1800278f7  lea     r9d, [rbx+3]
0x1800278fb  mov     r8d, 1000h
0x180027901  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180027906  jmp     loc_180027A56
0x18002790b  mov     ebx, [rsi+10h]
0x18002790e  mov     rdx, rsi; struct _GUID *
0x180027911  lea     rcx, [rbp+130h+var_180]; this
0x180027915  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18002791a  lea     rdx, aMerged; "merged"
0x180027921  lea     rcx, aNotMerged; "not merged"
0x180027928  test    r12d, r12d
0x18002792b  cmovnz  rcx, rdx
0x18002792f  mov     [rsp+230h+var_1F0], rcx
0x180027934  mov     dword ptr [rsp+230h+var_1F8], ebx
0x180027938  mov     [rsp+230h+var_200], rax
0x18002793d  lea     rax, aPreparingToIns; "Preparing to install update ID: %ws.%d "...
0x180027944  mov     [rsp+230h+var_208], rax
0x180027949  mov     [rsp+230h+var_210], 0
0x180027952  xor     edx, edx
0x180027954  xor     ecx, ecx
0x180027956  lea     r9d, [rdx+4]
0x18002795a  mov     r8d, 1000h
0x180027960  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180027965  mov     eax, r12d
0x180027968  neg     eax
0x18002796a  sbb     rbx, rbx
0x18002796d  and     rbx, [rbp+130h+lpMem]
0x180027971  mov     rcx, [rbp+130h+var_E8]; lpMem
0x180027975  test    rcx, rcx
0x180027978  jz      short loc_180027987
0x18002797a  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002797f  mov     [rbp+130h+var_E8], 0
0x180027987  mov     rcx, [rbp+130h+var_D8]; lpMem
0x18002798b  test    rcx, rcx
0x18002798e  jz      short loc_18002799D
0x180027990  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180027995  mov     [rbp+130h+var_D8], 0
0x18002799d  mov     [rsp+230h+var_1E8], rbx
0x1800279a2  lea     rax, [rbp+130h+var_E8]
0x1800279a6  mov     [rsp+230h+var_1F0], rax
0x1800279ab  lea     rax, [rbp+130h+var_D8]
0x1800279af  mov     [rsp+230h+var_1F8], rax
0x1800279b4  lea     rax, [rbp+130h+var_E0]
0x1800279b8  mov     [rsp+230h+var_200], rax
0x1800279bd  lea     rax, [rbp+130h+var_110]
0x1800279c1  mov     [rsp+230h+var_208], rax
0x1800279c6  mov     [rsp+230h+var_210], r15
0x1800279cb  mov     rax, [rsp+230h+var_1C8]
0x1800279d0  mov     r9d, [rax+10h]
0x1800279d4  mov     r8d, 1
0x1800279da  mov     rdx, r13
0x1800279dd  mov     rcx, rdi
0x1800279e0  call    ?OrchestrateUpdate@COSInstaller@@AEAAJAEBUtagSusDeployData@@W4tagUpdateDeploymentAction@@KPEAUIUpdateDeploymentCallback@@PEAHPEAW4tagAutoCommitStatus@@PEAPEA_W5PEB_W@Z; COSInstaller::OrchestrateUpdate(tagSusDeployData const &,tagUpdateDeploymentAction,ulong,IUpdateDeploymentCallback *,int *,tagAutoCommitStatus *,wchar_t * *,wchar_t * *,wchar_t const *)
0x1800279e5  mov     r15d, eax
0x1800279e8  lea     rax, aYes; "Yes"
0x1800279ef  lea     rdi, aNo; "No"
0x1800279f6  cmp     [rbp+130h+var_110], 0
0x1800279fa  cmovnz  rdi, rax
0x1800279fe  mov     ebx, [rsi+10h]
0x180027a01  mov     rdx, rsi; struct _GUID *
0x180027a04  lea     rcx, [rbp+130h+var_180]; this
0x180027a08  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180027a0d  mov     r9d, r15d
0x180027a10  sar     r9d, 1Fh
0x180027a14  and     r9d, 0FFFFFFFEh
0x180027a18  add     r9d, 4
0x180027a1c  mov     [rsp+230h+var_1E8], rdi
0x180027a21  mov     dword ptr [rsp+230h+var_1F0], r15d
0x180027a26  mov     dword ptr [rsp+230h+var_1F8], ebx
0x180027a2a  mov     [rsp+230h+var_200], rax
0x180027a2f  lea     rax, aInstallComplet; "Install complete for update ID: %ws.%d "...
0x180027a36  mov     [rsp+230h+var_208], rax
0x180027a3b  xor     esi, esi
0x180027a3d  mov     [rsp+230h+var_210], rsi
0x180027a42  xor     edx, edx
0x180027a44  xor     ecx, ecx
0x180027a46  mov     r8d, 1000h
0x180027a4c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180027a51  mov     rdi, [rsp+230h+var_1D8]
0x180027a56  mov     rax, [rbp+130h+var_E8]
0x180027a5a  mov     rcx, [rbp+130h+var_D8]
0x180027a5e  mov     edx, [rbp+130h+var_E0]
0x180027a61  mov     r8d, [rbp+130h+var_110]
0x180027a65  mov     [rsp+230h+var_1F0], rax
0x180027a6a  mov     [rsp+230h+var_1F8], rcx
0x180027a6f  mov     dword ptr [rsp+230h+var_200], edx
0x180027a73  mov     dword ptr [rsp+230h+var_208], r8d
0x180027a78  mov     dword ptr [rsp+230h+var_210], r15d; int
0x180027a7d  mov     r8, r13
0x180027a80  mov     rdx, [rsp+230h+var_1D0]
0x180027a85  mov     rcx, rdi
0x180027a88  call    ?NotifyResult@COSInstaller@@AEAAJPEAUIUpdateDeploymentCallback@@AEBUtagSusDeployData@@W4tagDeploymentOperationNotifyType@@JHW4tagAutoCommitStatus@@PEB_W4@Z; COSInstaller::NotifyResult(IUpdateDeploymentCallback *,tagSusDeployData const &,tagDeploymentOperationNotifyType,long,int,tagAutoCommitStatus,wchar_t const *,wchar_t const *)
0x180027a8d  mov     edi, eax
0x180027a8f  xor     eax, eax
0x180027a91  mov     [rbp+130h+var_C0], rax
0x180027a95  mov     [rbp+130h+var_B8], rsi
0x180027a99  mov     rcx, rsi
0x180027a9c  mov     [rbp+130h+var_B0], rcx
0x180027aa3  xorps   xmm0, xmm0
0x180027aa6  movups  [rbp+130h+var_A8], xmm0
0x180027aad  movups  [rbp+130h+var_98], xmm0
0x180027ab4  movups  [rbp+130h+var_88], xmm0
0x180027abb  mov     [rbp+130h+var_78], rax
0x180027ac2  lea     rbx, [r13+70h]
0x180027ac6  test    rbx, rbx
0x180027ac9  jz      short loc_180027B02
0x180027acb  cmp     [rbx], sil
0x180027ace  jz      short loc_180027B02
0x180027ad0  lea     rdx, [rbp+130h+var_B8]
0x180027ad4  mov     rcx, rbx
0x180027ad7  call    ??$DuplicateString@PEBDPEAD@@YAJPEBDPEAPEAD@Z; DuplicateString<char const *,char *>(char const *,char * *)
0x180027adc  mov     rcx, [rbp+138h]; this
0x180027ae3  test    eax, eax
0x180027ae5  jns     short loc_180027AFB
0x180027ae7  mov     r9d, eax; char *
0x180027aea  lea     r8, aCW1SSrcClientI_1; "C:\\__w\\1\\s\\src\\Client\\inc\\Deploy"...
0x180027af1  mov     edx, 0FCh; void *
0x180027af6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027afb  mov     rcx, [rbp+130h+var_B0]; lpMem
0x180027b02  mov     rbx, [rsp+230h+var_1C0]
0x180027b07  test    rbx, rbx
0x180027b0a  jz      short loc_180027B50
0x180027b0c  cmp     [rbx], sil
0x180027b0f  jz      short loc_180027B50
0x180027b11  test    rcx, rcx
0x180027b14  jz      short loc_180027B22
0x180027b16  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180027b1b  mov     [rbp+130h+var_B0], rsi
0x180027b22  lea     rdx, [rbp+130h+var_B0]
0x180027b29  mov     rcx, rbx
0x180027b2c  call    ??$DuplicateString@PEBDPEAD@@YAJPEBDPEAPEAD@Z; DuplicateString<char const *,char *>(char const *,char * *)
0x180027b31  mov     rcx, [rbp+138h]; this
0x180027b38  test    eax, eax
0x180027b3a  jns     short loc_180027B50
0x180027b3c  mov     r9d, eax; char *
0x180027b3f  lea     r8, aCW1SSrcClientI_1; "C:\\__w\\1\\s\\src\\Client\\inc\\Deploy"...
0x180027b46  mov     edx, 104h; void *
0x180027b4b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027b50  lea     rcx, [rbp+130h+var_60]; UnbiasedTime
0x180027b57  call    cs:__imp_QueryUnbiasedInterruptTime
0x180027b5d  mov     rcx, [rbp+130h+var_60]
0x180027b64  sub     rcx, [rbp+130h+UnbiasedTime]
0x180027b6b  mov     rax, [rbp+130h+var_58]
0x180027b72  add     rax, rcx
0x180027b75  mov     [rbp+130h+var_58], rax
0x180027b7c  lea     rcx, aInstall_0; "Install"
0x180027b83  mov     [rbp+130h+var_C0], rcx
0x180027b87  cmp     [rbp+130h+var_70], sil
0x180027b8e  jz      short loc_180027BA0
0x180027b90  mov     ecx, [rbp+130h+var_50]
0x180027b96  xor     edx, edx
0x180027b98  div     rcx
0x180027b9b  mov     rcx, rax
0x180027b9e  jmp     short loc_180027BA2
0x180027ba0  mov     ecx, esi
0x180027ba2  mov     rax, [r13+38h]
0x180027ba6  movups  xmm0, xmmword ptr [rax+4]
0x180027baa  movdqu  [rbp+130h+var_98+4], xmm0
0x180027bb2  cmp     [rbp+130h+var_110], esi
0x180027bb5  setnz   byte ptr [rbp+130h+var_A8+9]
0x180027bbc  mov     eax, [rbp+130h+var_E0]
  ... truncated ...
```
