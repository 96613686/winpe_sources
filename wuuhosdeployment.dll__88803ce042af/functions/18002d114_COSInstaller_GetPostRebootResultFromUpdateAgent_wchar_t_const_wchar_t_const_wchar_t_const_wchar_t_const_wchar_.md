# COSInstaller::GetPostRebootResultFromUpdateAgent(wchar_t * const,wchar_t * const,wchar_t * const,wchar_t * const,wchar_t * const,wchar_t * const,wchar_t * const,wchar_t * const,bool *,tagPostRebootResultData *)

- ea: `0x18002d114`
- end: `0x18002d4db`
- name: `?GetPostRebootResultFromUpdateAgent@COSInstaller@@AEAAJQEA_W0000000PEA_NPEAUtagPostRebootResultData@@@Z`
- size: `967`
- prototype: `__int64 __fastcall(COSInstaller *__hidden this, wchar_t *const, wchar_t *const, wchar_t *const, wchar_t *const, wchar_t *const, wchar_t *const, wchar_t *const, wchar_t *const, bool *, struct tagPostRebootResultData *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002a220`

## callees

- `0x180003950`
- `0x180005f64`
- `0x18000956c`
- `0x180018f18`
- `0x1800199a4`
- `0x180019d44`
- `0x18001a8b8`
- `0x1800230c0`
- `0x18002d114`
- `0x18002d800`
- `0x18002ea14`
- `0x180042630`
- `0x180049260`
- `0x1800492e0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d293`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d485`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d293`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d485`

## string_xrefs

- `0x18002d196`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18002d200`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18002d45b`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18002d3c7`: `Update is not committed yet`
- `0x18002d398`: `Update status code is 0x%08lX`
- `0x18002d401`: `Failed to install the update`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall COSInstaller::GetPostRebootResultFromUpdateAgent(
        COSInstaller *this,
        wchar_t *const a2,
        wchar_t *const a3,
        wchar_t *const a4,
        wchar_t *const a5,
        wchar_t *const a6,
        wchar_t *const a7,
        wchar_t *const a8,
        wchar_t *const lpWideCharStr,
        bool *a10,
        struct tagPostRebootResultData *a11)
{
  __int64 v12; // rdx
  OSDeploymentHelper::CDeploymentSessionWrapper *v14; // rbx
  int v15; // eax
  int v16; // esi
  void *v17; // rdi
  wchar_t *v18; // rax
  unsigned int v19; // r8d
  unsigned int v20; // r9d
  int v21; // eax
  int v22; // ecx
  BOOL v23; // eax
  int v24; // eax
  __int64 v25; // rdx
  int v26; // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+20h] [rbp-E0h]
  int v28; // [rsp+38h] [rbp-C8h]
  unsigned int v29; // [rsp+50h] [rbp-B0h] BYREF
  void *lpMem; // [rsp+58h] [rbp-A8h] BYREF
  OSDeploymentHelper::CDeploymentSessionWrapper *v31; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v32; // [rsp+68h] [rbp-98h] BYREF
  struct tagDSFile **v33; // [rsp+70h] [rbp-90h] BYREF
  bool *v34; // [rsp+78h] [rbp-88h]
  _QWORD v35[2]; // [rsp+80h] [rbp-80h] BYREF
  char v36; // [rsp+90h] [rbp-70h]
  __int128 v37; // [rsp+98h] [rbp-68h] BYREF
  wchar_t *v38; // [rsp+A8h] [rbp-58h] BYREF
  const wchar_t *v39; // [rsp+B0h] [rbp-50h] BYREF
  const wchar_t *v40; // [rsp+B8h] [rbp-48h] BYREF
  wchar_t *v41; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v42[14]; // [rsp+D0h] [rbp-30h] BYREF
  HANDLE hObject; // [rsp+140h] [rbp+40h] BYREF
  __int64 v44; // [rsp+148h] [rbp+48h] BYREF
  wchar_t v45[8]; // [rsp+150h] [rbp+50h]
  __int64 v46; // [rsp+160h] [rbp+60h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v38 = a2;
  v41 = a3;
  v40 = a5;
  v39 = a6;
  v34 = a10;
  if ( !a10 )
  {
    v12 = 2297;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)0x80004003LL,
      v26);
    return 2147500035LL;
  }
  if ( !a11 )
  {
    v12 = 2298;
    goto LABEL_3;
  }
  v14 = 0;
  v31 = 0;
  memset(v42, 0, 0x68u);
  lpMem = 0;
  hObject = 0;
  v15 = ConvertWideToAnsi_Alloc(lpWideCharStr, (char **)&lpMem);
  v16 = v15;
  v17 = lpMem;
  if ( v15 >= 0 )
  {
    v42[0] = a7;
    v42[1] = v38;
    v42[2] = a8;
    v42[4] = lpMem;
    LODWORD(v42[8]) = 2;
    if ( a4 )
    {
      v18 = (wchar_t *)v42[6];
      if ( *a4 )
        v18 = a4;
      v42[6] = v18;
    }
    v44 = 0;
    *(GUID *)v45 = GUID_NULL;
    v46 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::GetImpl'::`2'::impl) )
    {
      v21 = OSDeploymentHelper::SandboxAccessMutexGuard::Acquire((wchar_t *)&v44, v38, v19);
    }
    else
    {
      if ( hObject )
      {
        CloseHandle(hObject);
        hObject = 0;
      }
      v21 = OSDeploymentHelper::CreateAndAcquireSandboxAccessMutex(
              v38,
              (const wchar_t *)&hObject,
              (void **)0x493E0,
              v20);
    }
    v22 = v21;
    if ( v21 < 0 )
    {
      v23 = v21 == -2147024638;
      *((_DWORD *)a11 + 2) = v23;
      *((_DWORD *)a11 + 9) = v23;
      v24 = -2145116138;
      if ( v22 == -2147024638 )
        v24 = -2145116140;
      *(_DWORD *)a11 = v24;
      v16 = 0;
      goto LABEL_32;
    }
    v35[0] = &hObject;
    v35[1] = &v38;
    v36 = 1;
    v32 = v42;
    v37 = xmmword_180076898;
    v33 = 0;
    v29 = 0;
    v16 = Microsoft::WRL::Details::MakeAndInitialize<OSDeploymentHelper::CDeploymentSessionWrapper,OSDeploymentHelper::CDeploymentSessionWrapper,wchar_t * const &,wchar_t * const &,wchar_t * const &,int,std::nullptr_t,_GUID,unsigned long const &,tagOptionalSessionInfo5 *>(
            &v31,
            &v41,
            &v40,
            &v39,
            &v29,
            &v33,
            (__int64)&v37,
            v28,
            (void **)&v32);
    v14 = v31;
    if ( v16 >= 0 )
    {
      *v34 = 1;
      v16 = (*(__int64 (__fastcall **)(__int64, struct tagPostRebootResultData *))(*((_QWORD *)v14 + 2) + 80LL))(
              (__int64)v14 + 16,
              a11);
      if ( v16 >= 0 )
      {
        WUTrace(0, 0, 4096, 4);
        if ( *(_DWORD *)a11 == -805306323 )
        {
          WUTrace(0, 0, 4096, 4);
          *((_DWORD *)a11 + 2) = 1;
          *((_DWORD *)a11 + 9) = 1;
          *(_DWORD *)a11 = -2145116140;
        }
        else if ( *(int *)a11 < 0 )
        {
          WUTrace(0, 0, 4096, 4);
        }
        v16 = 0;
        goto LABEL_31;
      }
      v27 = 0;
      WUTrace(0, 0, 4096, 4);
      v25 = 2401;
    }
    else
    {
      v25 = 2366;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)(unsigned int)v16,
      v27);
LABEL_31:
    wil::details::lambda_call__lambda_aaac948832a0183d23684ee84e848ef9___::_lambda_call__lambda_aaac948832a0183d23684ee84e848ef9___(v35);
LABEL_32:
    OSDeploymentHelper::SandboxAccessMutexGuard::~SandboxAccessMutexGuard((OSDeploymentHelper::SandboxAccessMutexGuard *)&v44);
    goto LABEL_33;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x902,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
    (const char *)(unsigned int)v15,
    v26);
LABEL_33:
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( v17 )
    CSusBaseAllocTag<942762101>::operator delete(v17);
  if ( v14 )
    (*(void (__fastcall **)(OSDeploymentHelper::CDeploymentSessionWrapper *))(*(_QWORD *)v14 + 16LL))(v14);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18002d114  mov     [rsp-8+arg_0], rbx
0x18002d119  push    rbp
0x18002d11a  push    rsi
0x18002d11b  push    rdi
0x18002d11c  push    r12
0x18002d11e  push    r13
0x18002d120  push    r14
0x18002d122  push    r15
0x18002d124  lea     rbp, [rsp-70h]
0x18002d129  sub     rsp, 170h
0x18002d130  mov     rax, cs:__security_cookie
0x18002d137  xor     rax, rsp
0x18002d13a  mov     [rbp+0A0h+var_38], rax
0x18002d13e  mov     r15, r9
0x18002d141  mov     r14, [rbp+0A0h+arg_50]
0x18002d148  mov     [rbp+0A0h+var_F8], rdx
0x18002d14c  mov     [rbp+0A0h+var_E0], r8
0x18002d150  mov     rax, [rbp+0A0h+arg_20]
0x18002d157  mov     [rbp+0A0h+var_E8], rax
0x18002d15b  mov     rax, [rbp+0A0h+arg_28]
0x18002d162  mov     [rbp+0A0h+var_F0], rax
0x18002d166  mov     r12, [rbp+0A0h+arg_30]
0x18002d16d  mov     r13, [rbp+0A0h+arg_38]
0x18002d174  mov     rdi, [rbp+0A0h+lpWideCharStr]
0x18002d17b  mov     rax, [rbp+0A0h+arg_48]
0x18002d182  mov     [rsp+1A0h+var_128], rax
0x18002d187  test    rax, rax
0x18002d18a  jnz     short loc_18002D1B3
0x18002d18c  mov     edx, 8F9h; void *
0x18002d191  mov     ebx, 80004003h
0x18002d196  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18002d19d  mov     r9d, ebx; char *
0x18002d1a0  mov     rcx, [rbp+0A8h]; this
0x18002d1a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d1ac  mov     eax, ebx
0x18002d1ae  jmp     loc_18002D4B4
0x18002d1b3  test    r14, r14
0x18002d1b6  jnz     short loc_18002D1BF
0x18002d1b8  mov     edx, 8FAh
0x18002d1bd  jmp     short loc_18002D191
0x18002d1bf  xor     ebx, ebx
0x18002d1c1  mov     [rsp+1A0h+var_140], rbx
0x18002d1c6  xor     edx, edx; Val
0x18002d1c8  lea     r8d, [rbx+68h]; Size
0x18002d1cc  lea     rcx, [rbp+0A0h+var_D0]; void *
0x18002d1d0  call    memset
0x18002d1d5  mov     [rsp+1A0h+lpMem], rbx
0x18002d1da  mov     [rbp+0A0h+hObject], rbx
0x18002d1de  lea     rdx, [rsp+1A0h+lpMem]; char **
0x18002d1e3  mov     rcx, rdi; lpWideCharStr
0x18002d1e6  call    ?ConvertWideToAnsi_Alloc@@YAJPEB_WPEAPEAD@Z; ConvertWideToAnsi_Alloc(wchar_t const *,char * *)
0x18002d1eb  mov     esi, eax
0x18002d1ed  mov     rdi, [rsp+1A0h+lpMem]
0x18002d1f2  test    eax, eax
0x18002d1f4  jns     short loc_18002D219
0x18002d1f6  mov     rcx, [rbp+0A8h]; this
0x18002d1fd  mov     r9d, eax; char *
0x18002d200  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18002d207  mov     edx, 902h; void *
0x18002d20c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d211  xor     r13d, r13d
0x18002d214  jmp     loc_18002D47C
0x18002d219  mov     [rbp+0A0h+var_D0], r12
0x18002d21d  mov     rax, [rbp+0A0h+var_F8]
0x18002d221  mov     [rbp+0A0h+var_C8], rax
0x18002d225  mov     [rbp+0A0h+var_C0], r13
0x18002d229  mov     [rbp+0A0h+var_B0], rdi
0x18002d22d  mov     [rbp+0A0h+var_90], 2
0x18002d234  xor     r13d, r13d
0x18002d237  test    r15, r15
0x18002d23a  jz      short loc_18002D24C
0x18002d23c  mov     rax, [rbp+0A0h+var_A0]
0x18002d240  cmp     [r15], r13w
0x18002d244  cmovnz  rax, r15
0x18002d248  mov     [rbp+0A0h+var_A0], rax
0x18002d24c  xorps   xmm0, xmm0
0x18002d24f  movups  xmmword ptr [rbp+0A0h+var_58], xmm0
0x18002d253  movups  [rbp+0A0h+var_48], xmm0
0x18002d257  mov     qword ptr [rbp+0A0h+var_58], r13
0x18002d25b  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18002d262  movdqu  xmmword ptr [rbp+0A0h+var_58+8], xmm1
0x18002d267  mov     qword ptr [rbp+0A0h+var_48+8], r13
0x18002d26b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::GetImpl(void)'::`2'::impl
0x18002d272  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::__private_IsEnabled(void)
0x18002d277  test    al, al
0x18002d279  jz      short loc_18002D28A
0x18002d27b  mov     rdx, [rbp+0A0h+var_F8]; wchar_t *
0x18002d27f  lea     rcx, [rbp+0A0h+var_58]; this
0x18002d283  call    ?Acquire@SandboxAccessMutexGuard@OSDeploymentHelper@@QEAAJPEB_WK@Z; OSDeploymentHelper::SandboxAccessMutexGuard::Acquire(wchar_t const *,ulong)
0x18002d288  jmp     short loc_18002D2B0
0x18002d28a  mov     rcx, [rbp+0A0h+hObject]; hObject
0x18002d28e  test    rcx, rcx
0x18002d291  jz      short loc_18002D29D
0x18002d293  call    cs:__imp_CloseHandle
0x18002d299  mov     [rbp+0A0h+hObject], r13
0x18002d29d  mov     r8d, 493E0h; void **
0x18002d2a3  lea     rdx, [rbp+0A0h+hObject]; wchar_t *
0x18002d2a7  mov     rcx, [rbp+0A0h+var_F8]; this
0x18002d2ab  call    ?CreateAndAcquireSandboxAccessMutex@OSDeploymentHelper@@YAJPEB_WPEAPEAXK@Z; OSDeploymentHelper::CreateAndAcquireSandboxAccessMutex(wchar_t const *,void * *,ulong)
0x18002d2b0  mov     ecx, eax
0x18002d2b2  test    eax, eax
0x18002d2b4  jns     short loc_18002D2E3
0x18002d2b6  mov     eax, r13d
0x18002d2b9  mov     r8d, 80070102h
0x18002d2bf  cmp     ecx, r8d
0x18002d2c2  setz    al
0x18002d2c5  mov     [r14+8], eax
0x18002d2c9  mov     [r14+24h], eax
0x18002d2cd  mov     eax, 80242016h
0x18002d2d2  lea     edx, [rax-2]
0x18002d2d5  cmovz   eax, edx
0x18002d2d8  mov     [r14], eax
0x18002d2db  mov     esi, r13d
0x18002d2de  jmp     loc_18002D472
0x18002d2e3  lea     rax, [rbp+0A0h+hObject]
0x18002d2e7  mov     [rbp+0A0h+var_120], rax
0x18002d2eb  lea     rax, [rbp+0A0h+var_F8]
0x18002d2ef  mov     [rbp+0A0h+var_118], rax
0x18002d2f3  mov     [rbp+0A0h+var_110], 1
0x18002d2f7  lea     rax, [rbp+0A0h+var_D0]
0x18002d2fb  mov     [rsp+1A0h+var_138], rax
0x18002d300  movups  xmm0, cs:xmmword_180076898
0x18002d307  movdqu  [rbp+0A0h+var_108], xmm0
0x18002d30c  mov     [rsp+1A0h+var_130], r13
0x18002d311  mov     [rsp+1A0h+var_150], r13d
0x18002d316  lea     rax, [rsp+1A0h+var_138]
0x18002d31b  mov     [rsp+1A0h+var_160], rax
0x18002d320  lea     rax, [rbp+0A0h+var_108]
0x18002d324  mov     [rsp+1A0h+var_170], rax
0x18002d329  lea     rax, [rsp+1A0h+var_130]
0x18002d32e  mov     [rsp+1A0h+var_178], rax
0x18002d333  lea     rax, [rsp+1A0h+var_150]
0x18002d338  mov     qword ptr [rsp+1A0h+var_180], rax
0x18002d33d  lea     r9, [rbp+0A0h+var_F0]
0x18002d341  lea     r8, [rbp+0A0h+var_E8]
0x18002d345  lea     rdx, [rbp+0A0h+var_E0]
0x18002d349  lea     rcx, [rsp+1A0h+var_140]
0x18002d34e  call    ??$MakeAndInitialize@VCDeploymentSessionWrapper@OSDeploymentHelper@@V12@AEBQEA_WAEBQEA_WAEBQEA_WH$$TU_GUID@@AEBKPEAUtagOptionalSessionInfo5@@@Details@WRL@Microsoft@@YAJPEAPEAVCDeploymentSessionWrapper@OSDeploymentHelper@@AEBQEA_W11$$QEAH$$QEA$$T$$QEAU_GUID@@AEBK$$QEAPEAUtagOptionalSessionInfo5@@@Z; Microsoft::WRL::Details::MakeAndInitialize<OSDeploymentHelper::CDeploymentSessionWrapper,OSDeploymentHelper::CDeploymentSessionWrapper,wchar_t * const &,wchar_t * const &,wchar_t * const &,int,std::nullptr_t,_GUID,ulong const &,tagOptionalSessionInfo5 *>(OSDeploymentHelper::CDeploymentSessionWrapper * *,wchar_t * const &,wchar_t * const &,wchar_t * const &,int &&,$$T$$QEAU_GUID &&,ulong const &,tagOptionalSessionInfo5 * &&)
0x18002d353  mov     esi, eax
0x18002d355  mov     rbx, [rsp+1A0h+var_140]
0x18002d35a  test    eax, eax
0x18002d35c  jns     short loc_18002D368
0x18002d35e  mov     edx, 93Eh
0x18002d363  jmp     loc_18002D451
0x18002d368  mov     rax, [rsp+1A0h+var_128]
0x18002d36d  mov     byte ptr [rax], 1
0x18002d370  lea     rcx, [rbx+10h]
0x18002d374  mov     rax, [rcx]
0x18002d377  mov     rdx, r14
0x18002d37a  mov     rax, [rax+50h]
0x18002d37e  call    _guard_dispatch_icall
0x18002d383  mov     esi, eax
0x18002d385  xor     edx, edx
0x18002d387  xor     ecx, ecx
0x18002d389  test    eax, eax
0x18002d38b  js      loc_18002D426
0x18002d391  mov     eax, [r14]
0x18002d394  mov     dword ptr [rsp+1A0h+var_170], eax
0x18002d398  lea     rax, aUpdateStatusCo; "Update status code is 0x%08lX"
0x18002d39f  mov     [rsp+1A0h+var_178], rax
0x18002d3a4  mov     qword ptr [rsp+1A0h+var_180], r13
0x18002d3a9  lea     r15d, [rdx+4]
0x18002d3ad  mov     r9d, r15d
0x18002d3b0  mov     r12d, 1000h
0x18002d3b6  mov     r8d, r12d
0x18002d3b9  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002d3be  cmp     dword ptr [r14], 0D000002Dh
0x18002d3c5  jnz     short loc_18002D3FC
0x18002d3c7  lea     rax, aUpdateIsNotCom; "Update is not committed yet"
0x18002d3ce  mov     [rsp+1A0h+var_178], rax
0x18002d3d3  mov     qword ptr [rsp+1A0h+var_180], r13
0x18002d3d8  mov     r9d, r15d
0x18002d3db  mov     r8d, r12d
0x18002d3de  xor     edx, edx
0x18002d3e0  xor     ecx, ecx
0x18002d3e2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002d3e7  lea     eax, [r15-3]
0x18002d3eb  mov     [r14+8], eax
0x18002d3ef  mov     [r14+24h], eax
0x18002d3f3  mov     dword ptr [r14], 80242014h
0x18002d3fa  jmp     short loc_18002D421
0x18002d3fc  cmp     [r14], r13d
0x18002d3ff  jge     short loc_18002D421
0x18002d401  lea     rax, aFailedToInstal; "Failed to install the update"
0x18002d408  mov     [rsp+1A0h+var_178], rax
0x18002d40d  mov     qword ptr [rsp+1A0h+var_180], r13
0x18002d412  mov     r9d, r15d
0x18002d415  mov     r8d, r12d
0x18002d418  xor     edx, edx
0x18002d41a  xor     ecx, ecx
0x18002d41c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002d421  mov     esi, r13d
0x18002d424  jmp     short loc_18002D468
0x18002d426  mov     dword ptr [rsp+1A0h+var_170], eax
0x18002d42a  lea     rax, aGetpostrebootr_0; "GetPostRebootResult call failed. Status"...
0x18002d431  mov     [rsp+1A0h+var_178], rax
0x18002d436  mov     qword ptr [rsp+1A0h+var_180], r13; int
0x18002d43b  mov     r9d, 4
0x18002d441  mov     r8d, 1000h
0x18002d447  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002d44c  mov     edx, 961h; void *
0x18002d451  mov     rcx, [rbp+0A8h]; this
0x18002d458  mov     r9d, esi; char *
0x18002d45b  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18002d462  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d467  nop
0x18002d468  lea     rcx, [rbp+0A0h+var_120]
0x18002d46c  call    wil__details__lambda_call__lambda_aaac948832a0183d23684ee84e848ef9______lambda_call__lambda_aaac948832a0183d23684ee84e848ef9___
0x18002d471  nop
0x18002d472  lea     rcx, [rbp+0A0h+var_58]; this
0x18002d476  call    ??1SandboxAccessMutexGuard@OSDeploymentHelper@@QEAA@XZ; OSDeploymentHelper::SandboxAccessMutexGuard::~SandboxAccessMutexGuard(void)
0x18002d47b  nop
0x18002d47c  mov     rcx, [rbp+0A0h+hObject]; hObject
0x18002d480  test    rcx, rcx
0x18002d483  jz      short loc_18002D48F
0x18002d485  call    cs:__imp_CloseHandle
0x18002d48b  mov     [rbp+0A0h+hObject], r13
0x18002d48f  test    rdi, rdi
0x18002d492  jz      short loc_18002D49D
0x18002d494  mov     rcx, rdi; lpMem
0x18002d497  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002d49c  nop
0x18002d49d  test    rbx, rbx
0x18002d4a0  jz      short loc_18002D4B2
0x18002d4a2  mov     rcx, [rbx]
0x18002d4a5  mov     rax, [rcx+10h]
0x18002d4a9  mov     rcx, rbx
0x18002d4ac  call    _guard_dispatch_icall
0x18002d4b1  nop
0x18002d4b2  mov     eax, esi
0x18002d4b4  mov     rcx, [rbp+0A0h+var_38]
0x18002d4b8  xor     rcx, rsp; StackCookie
0x18002d4bb  call    __security_check_cookie
0x18002d4c0  mov     rbx, [rsp+1A0h+arg_0]
0x18002d4c8  add     rsp, 170h
0x18002d4cf  pop     r15
0x18002d4d1  pop     r14
0x18002d4d3  pop     r13
0x18002d4d5  pop     r12
0x18002d4d7  pop     rdi
0x18002d4d8  pop     rsi
0x18002d4d9  pop     rbp
0x18002d4da  retn
```
