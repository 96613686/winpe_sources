# Windows::Service::Task::Save(bool,wil::basic_zstring_view<wchar_t>)

- ea: `0x180069948`
- end: `0x180069fa2`
- name: `?Save@Task@Service@Windows@@QEAAX_NV?$basic_zstring_view@_W@wil@@@Z`
- size: `1626`
- prototype: `__int64 __fastcall(Windows::Service::Task *this)`
- caller_count: `6`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18006be90`
- `0x18006c0a0`
- `0x18006c1e0`
- `0x18006c350`
- `0x18006c6c0`
- `0x18006d7f0`

## callees

- `0x1800112d0`
- `0x180011680`
- `0x18001b064`
- `0x18001c6b4`
- `0x18002b918`
- `0x18002bbc0`
- `0x180041480`
- `0x180068d48`
- `0x180068ef4`
- `0x180069948`
- `0x180069fa8`
- `0x18006ce84`
- `0x18006da54`
- `0x18006ee60`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800699d6`
- `OLEAUT32!__imp_SysAllocString` at `0x180069aaf`
- `OLEAUT32!__imp_SysAllocString` at `0x180069b61`
- `OLEAUT32!__imp_SysAllocString` at `0x1800699d6`
- `OLEAUT32!__imp_SysAllocString` at `0x180069aaf`
- `OLEAUT32!__imp_SysAllocString` at `0x180069b61`
- `OLEAUT32!__imp_SysFreeString` at `0x180069c2d`
- `OLEAUT32!__imp_SysFreeString` at `0x180069ded`
- `OLEAUT32!__imp_SysFreeString` at `0x180069ea3`
- `OLEAUT32!__imp_SysFreeString` at `0x180069c2d`
- `OLEAUT32!__imp_SysFreeString` at `0x180069ded`
- `OLEAUT32!__imp_SysFreeString` at `0x180069ea3`
- `OLEAUT32!__imp_VariantInit` at `0x1800699c8`
- `OLEAUT32!__imp_VariantInit` at `0x180069aa1`
- `OLEAUT32!__imp_VariantInit` at `0x180069b29`
- `OLEAUT32!__imp_VariantInit` at `0x1800699c8`
- `OLEAUT32!__imp_VariantInit` at `0x180069aa1`
- `OLEAUT32!__imp_VariantInit` at `0x180069b29`
- `OLEAUT32!__imp_VariantClear` at `0x180069c39`
- `OLEAUT32!__imp_VariantClear` at `0x180069e75`
- `OLEAUT32!__imp_VariantClear` at `0x180069ecc`
- `OLEAUT32!__imp_VariantClear` at `0x180069c39`
- `OLEAUT32!__imp_VariantClear` at `0x180069e75`
- `OLEAUT32!__imp_VariantClear` at `0x180069ecc`

## string_xrefs

- `0x180069f17`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x180069f3e`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x180069f50`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x180069a40`: `Microsoft\Windows\UpdateOrchestrator`
- `0x180069f2c`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x180069f65`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x180069f7a`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x180069f8f`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x180069d31`: `Task definition refreshed: {}`
- `0x180069c5d`: `Refreshing cached task definition after Registering newly created task`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
int __fastcall Windows::Service::Task::Save(__int64 **this, char a2, _OWORD *a3)
{
  wil::details::in1diag3 **v3; // rax
  _OWORD *v4; // r12
  char v5; // r15
  __int64 **v6; // rsi
  BSTR v7; // rax
  const char *v8; // r9
  struct ITaskServiceVtbl *lpVtbl; // rax
  int v10; // eax
  BSTR v11; // rax
  const char *v12; // r9
  __int64 v13; // rbx
  __int128 v14; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v16; // xmm8
  IRecordInfo *v17; // xmm9_8
  __int128 v18; // xmm10
  IRecordInfo *v19; // xmm11_8
  __int64 *v20; // r13
  const OLECHAR *v21; // rcx
  BSTR v22; // rax
  const char *v23; // r9
  OLECHAR *v24; // r14
  int v25; // eax
  __int64 *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  __int64 *v29; // rbx
  __int64 *v30; // rcx
  __int64 *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  BSTR v34; // rbx
  _QWORD *v35; // rax
  LONGLONG v36; // rcx
  const char *v37; // r9
  int v39; // [rsp+20h] [rbp-1E8h]
  __int128 v40; // [rsp+50h] [rbp-1B8h] BYREF
  VARIANTARG v41; // [rsp+60h] [rbp-1A8h] BYREF
  __int128 v42; // [rsp+80h] [rbp-188h]
  IRecordInfo *v43; // [rsp+90h] [rbp-178h]
  Windows::Service::Task *v44; // [rsp+A0h] [rbp-168h]
  _OWORD *v45; // [rsp+B0h] [rbp-158h]
  int Src[4]; // [rsp+C0h] [rbp-148h] BYREF
  IRecordInfo *v47; // [rsp+D0h] [rbp-138h]
  __int128 v48; // [rsp+E0h] [rbp-128h]
  IRecordInfo *v49; // [rsp+F0h] [rbp-118h]
  VARIANTARG v50; // [rsp+100h] [rbp-108h] BYREF
  VARIANTARG pvarg; // [rsp+118h] [rbp-F0h] BYREF
  BSTR bstrString; // [rsp+130h] [rbp-D8h] BYREF
  __int64 *v53; // [rsp+138h] [rbp-D0h] BYREF
  __int64 *v54; // [rsp+140h] [rbp-C8h]
  __int64 v55; // [rsp+148h] [rbp-C0h] BYREF
  struct ITaskService *v56; // [rsp+150h] [rbp-B8h] BYREF
  BSTR v57; // [rsp+158h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h] BYREF

  v3 = &retaddr;
  v4 = a3;
  v5 = a2;
  v6 = this;
  v44 = (Windows::Service::Task *)this;
  v45 = a3;
  LODWORD(bstrString) = 0;
  if ( *((_BYTE *)this + 40) )
  {
    VariantInit(&pvarg);
    v7 = SysAllocString(L"D:P(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FRFX;;;BA)");
    v53 = (__int64 *)v7;
    LODWORD(bstrString) = 1;
    if ( !v7 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x138D,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v8);
    pvarg.llVal = (LONGLONG)v7;
    pvarg.vt = 8;
    v56 = 0;
    Windows::Service::Task::TaskService((int)&v56);
    Windows::Service::Task::EnsureTaskFolderExists(v56);
    v57 = 0;
    wil::make_bstr(&v57, L"Microsoft\\Windows\\UpdateOrchestrator");
    v55 = 0;
    lpVtbl = v56->lpVtbl;
    v55 = 0;
    v10 = ((__int64 (__fastcall *)(struct ITaskService *, BSTR, __int64 *))lpVtbl->GetFolder)(v56, v57, &v55);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD9,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v10,
        v39);
    VariantInit(&v50);
    v11 = SysAllocString(L"S-1-5-18");
    v53 = (__int64 *)v11;
    LODWORD(bstrString) = 4;
    if ( !v11 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x138D,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v12);
    v50.llVal = (LONGLONG)v11;
    v50.vt = 8;
    v54 = 0;
    v13 = v55;
    v53 = *(__int64 **)(*(_QWORD *)v55 + 136LL);
    v54 = 0;
    v14 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v41);
    v16 = *(_OWORD *)&v41.vt;
    v17 = v41.pRecInfo;
    v18 = *(_OWORD *)&v50.vt;
    v19 = v50.pRecInfo;
    v20 = *v6;
    v21 = (const OLECHAR *)(v6 + 1);
    if ( (unsigned __int64)v6[4] > 7 )
      v21 = *(const OLECHAR **)v21;
    v22 = SysAllocString(v21);
    v24 = v22;
    *(_QWORD *)&v40 = v22;
    LODWORD(bstrString) = 8;
    if ( !v22 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x138D,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v23);
    v42 = v14;
    v43 = pRecInfo;
    v48 = v16;
    v49 = v17;
    *(_OWORD *)Src = v18;
    v47 = v19;
    v25 = ((__int64 (__fastcall *)(__int64, BSTR, __int64 *, __int64))v53)(v13, v22, v20, 6);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE8,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v25,
        (int)Src);
    SysFreeString(v24);
    VariantClear(&v41);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_SchedulerRefreshTaskBeforeProtect>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_SchedulerRefreshTaskBeforeProtect>::GetImpl'::`2'::impl)
      && *((_BYTE *)v6 + 41) )
    {
      try
      {
        *(_QWORD *)&v40 = L"Refreshing cached task definition after Registering newly created task";
        *((_QWORD *)&v40 + 1) = 70;
        SystemInterface::Log<>(&v40);
        v53 = 0;
        v27 = *v54;
        v53 = 0;
        v28 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v27 + 152))(v54, &v53);
        if ( v28 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF4,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
            (const char *)(unsigned int)v28,
            (int)Src);
        v29 = *v6;
        v30 = v53;
        *v6 = v53;
        if ( v30 )
          (*(void (__fastcall **)(__int64 *))(*v30 + 8))(v30);
        if ( v29 )
          (*(void (__fastcall **)(__int64 *))(*v29 + 16))(v29);
        bstrString = 0;
        v31 = *v6;
        v32 = **v6;
        bstrString = 0;
        v33 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v32 + 152))(v31, &bstrString);
        if ( v33 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF7,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
            (const char *)(unsigned int)v33,
            (int)Src);
        v34 = bstrString;
        *(_QWORD *)&v42 = L"Task definition refreshed: {}";
        *((_QWORD *)&v42 + 1) = 29;
        std::_Format_arg_index::_Format_arg_index((std::_Format_arg_index *)&v40);
        *((_QWORD *)&v40 + 1) = v34;
        *(_QWORD *)&v40 = 0xB000000000000000uLL;
        *(_QWORD *)&v41.vt = 1;
        v41.llVal = (LONGLONG)&v40;
        v35 = (_QWORD *)std::vformat<0>(Src);
        v36 = v35[2];
        if ( v35[3] > 7u )
          v35 = (_QWORD *)*v35;
        *(_QWORD *)&v41.vt = v35;
        v41.llVal = v36;
        SystemInterface::LogMessage(&v41, 1);
        std::wstring::~wstring(Src);
        *((_BYTE *)v6 + 41) = 0;
        if ( bstrString )
          SysFreeString(bstrString);
        v26 = v53;
        if ( v53 )
          (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0xFB,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
          v37);
        v5 = a2;
        v6 = (__int64 **)v44;
        v4 = v45;
      }
    }
    if ( v5 )
      Windows::Service::Task::Protect(v6);
    *(_OWORD *)&v41.vt = *v4;
    Windows::Service::Task::LogTaskModified(v26, v54, &v41);
    if ( v54 )
      (*(void (__fastcall **)(__int64 *))(*v54 + 16))(v54);
    VariantClear(&v50);
    if ( v55 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    if ( v57 )
      SysFreeString(v57);
    if ( v56 )
      ((void (__fastcall *)(struct ITaskService *))v56->lpVtbl->Release)(v56);
    LODWORD(v3) = VariantClear(&pvarg);
  }
  return (int)v3;
}

```

## disassembly

```asm
0x180069948  mov     rax, rsp
0x18006994b  mov     [rax+10h], dl
0x18006994e  push    rbx
0x18006994f  push    rsi
0x180069950  push    rdi
0x180069951  push    r12
0x180069953  push    r13
0x180069955  push    r14
0x180069957  push    r15
0x180069959  sub     rsp, 1D0h
0x180069960  movaps  xmmword ptr [rax-48h], xmm6
0x180069964  movaps  xmmword ptr [rax-58h], xmm7
0x180069968  movaps  xmmword ptr [rax-68h], xmm8
0x18006996d  movaps  xmmword ptr [rax-78h], xmm9
0x180069972  movaps  xmmword ptr [rax-88h], xmm10
0x18006997a  movaps  xmmword ptr [rax-98h], xmm11
0x180069982  mov     rax, cs:__security_cookie
0x180069989  xor     rax, rsp
0x18006998c  mov     [rsp+208h+var_A8], rax
0x180069994  mov     r12, r8
0x180069997  mov     r15b, dl
0x18006999a  mov     rsi, rcx
0x18006999d  mov     [rsp+208h+var_168], rcx
0x1800699a5  mov     [rsp+208h+var_158], r8
0x1800699ad  xor     edi, edi
0x1800699af  mov     dword ptr [rsp+208h+bstrString], edi
0x1800699b6  cmp     [rcx+28h], dil
0x1800699ba  jz      loc_180069ED2
0x1800699c0  lea     rcx, [rsp+208h+pvarg]; pvarg
0x1800699c8  call    cs:__imp_VariantInit
0x1800699ce  nop
0x1800699cf  lea     rcx, psz; "D:P(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FRFX;;"...
0x1800699d6  call    cs:__imp_SysAllocString
0x1800699dc  mov     [rsp+208h+var_D0], rax
0x1800699e4  mov     dword ptr [rsp+208h+bstrString], 1
0x1800699ef  mov     rcx, [rsp+208h]; this
0x1800699f7  test    rax, rax
0x1800699fa  jz      loc_180069F17
0x180069a00  mov     qword ptr [rsp+208h+pvarg+8], rax
0x180069a08  mov     ebx, 8
0x180069a0d  mov     word ptr [rsp+208h+pvarg], bx
0x180069a15  mov     [rsp+208h+var_B8], rdi
0x180069a1d  lea     rcx, [rsp+208h+var_B8]; int
0x180069a25  call    ?TaskService@Task@Service@Windows@@CA?AV?$com_ptr_t@UITaskService@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::Service::Task::TaskService(void)
0x180069a2a  nop
0x180069a2b  mov     rcx, [rsp+208h+var_B8]; struct ITaskService *
0x180069a33  call    ?EnsureTaskFolderExists@Task@Service@Windows@@CAXPEAUITaskService@@@Z; Windows::Service::Task::EnsureTaskFolderExists(ITaskService *)
0x180069a38  mov     [rsp+208h+var_B0], rdi
0x180069a40  lea     rdx, sourceString; "Microsoft\\Windows\\UpdateOrchestrator"
0x180069a47  lea     rcx, [rsp+208h+var_B0]
0x180069a4f  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x180069a54  nop
0x180069a55  mov     [rsp+208h+var_C0], rdi
0x180069a5d  mov     rcx, [rsp+208h+var_B8]
0x180069a65  mov     rax, [rcx]
0x180069a68  mov     [rsp+208h+var_C0], rdi
0x180069a70  lea     r8, [rsp+208h+var_C0]
0x180069a78  mov     rdx, [rsp+208h+var_B0]
0x180069a80  mov     rax, [rax+38h]
0x180069a84  call    _guard_dispatch_icall
0x180069a89  mov     rcx, [rsp+208h]; this
0x180069a91  test    eax, eax
0x180069a93  js      loc_180069F29
0x180069a99  lea     rcx, [rsp+208h+var_108]; pvarg
0x180069aa1  call    cs:__imp_VariantInit
0x180069aa7  nop
0x180069aa8  lea     rcx, aS1518; "S-1-5-18"
0x180069aaf  call    cs:__imp_SysAllocString
0x180069ab5  mov     [rsp+208h+var_D0], rax
0x180069abd  mov     dword ptr [rsp+208h+bstrString], 4
0x180069ac8  mov     rcx, [rsp+208h]; this
0x180069ad0  test    rax, rax
0x180069ad3  jz      loc_180069F3E
0x180069ad9  mov     qword ptr [rsp+208h+var_108+8], rax
0x180069ae1  mov     word ptr [rsp+208h+var_108], bx
0x180069ae9  mov     [rsp+208h+var_C8], rdi
0x180069af1  mov     rbx, [rsp+208h+var_C0]
0x180069af9  mov     rax, [rbx]
0x180069afc  mov     rax, [rax+88h]
0x180069b03  mov     [rsp+208h+var_D0], rax
0x180069b0b  mov     [rsp+208h+var_C8], rdi
0x180069b13  movups  xmm6, xmmword ptr [rsp+208h+pvarg]
0x180069b1b  movsd   xmm7, qword ptr [rsp+208h+pvarg+10h]
0x180069b24  lea     rcx, [rsp+208h+var_1A8]; pvarg
0x180069b29  call    cs:__imp_VariantInit
0x180069b2f  nop
0x180069b30  movups  xmm8, xmmword ptr [rsp+208h+var_1A8]
0x180069b36  movsd   xmm9, qword ptr [rsp+208h+var_1A8+10h]
0x180069b3d  movups  xmm10, xmmword ptr [rsp+208h+var_108]
0x180069b46  movsd   xmm11, qword ptr [rsp+208h+var_108+10h]
0x180069b50  mov     r13, [rsi]
0x180069b53  lea     rcx, [rsi+8]
0x180069b57  cmp     qword ptr [rcx+18h], 7
0x180069b5c  jbe     short loc_180069B61
0x180069b5e  mov     rcx, [rcx]; psz
0x180069b61  call    cs:__imp_SysAllocString
0x180069b67  mov     r14, rax
0x180069b6a  mov     [rsp+208h+var_1B8], rax
0x180069b6f  mov     dword ptr [rsp+208h+bstrString], 8
0x180069b7a  mov     rcx, [rsp+208h]; this
0x180069b82  test    rax, rax
0x180069b85  jz      loc_180069F50
0x180069b8b  movaps  [rsp+208h+var_188], xmm6
0x180069b93  movsd   [rsp+208h+var_178], xmm7
0x180069b9c  movaps  [rsp+208h+var_128], xmm8
0x180069ba5  movsd   [rsp+208h+var_118], xmm9
0x180069baf  movaps  xmmword ptr [rsp+208h+Src], xmm10
0x180069bb8  movsd   [rsp+208h+var_138], xmm11
0x180069bc2  lea     rax, [rsp+208h+var_C8]
0x180069bca  mov     [rsp+208h+var_1C8], rax
0x180069bcf  lea     rax, [rsp+208h+var_188]
0x180069bd7  mov     [rsp+208h+var_1D0], rax
0x180069bdc  mov     [rsp+208h+var_1D8], 5
0x180069be4  lea     rax, [rsp+208h+var_128]
0x180069bec  mov     [rsp+208h+var_1E0], rax
0x180069bf1  lea     rax, [rsp+208h+Src]
0x180069bf9  mov     qword ptr [rsp+208h+var_1E8], rax; int
0x180069bfe  mov     r9d, 6
0x180069c04  mov     r8, r13
0x180069c07  mov     rdx, r14
0x180069c0a  mov     rcx, rbx
0x180069c0d  mov     rax, [rsp+208h+var_D0]
0x180069c15  call    _guard_dispatch_icall
0x180069c1a  mov     rcx, [rsp+208h]; this
0x180069c22  test    eax, eax
0x180069c24  js      loc_180069F62
0x180069c2a  mov     rcx, r14; bstrString
0x180069c2d  call    cs:__imp_SysFreeString
0x180069c33  nop
0x180069c34  lea     rcx, [rsp+208h+var_1A8]; pvarg
0x180069c39  call    cs:__imp_VariantClear
0x180069c3f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_SchedulerRefreshTaskBeforeProtect@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_SchedulerRefreshTaskBeforeProtect@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_SchedulerRefreshTaskBeforeProtect> `wil::Feature<__WilFeatureTraits_Feature_Containment_SchedulerRefreshTaskBeforeProtect>::GetImpl(void)'::`2'::impl
0x180069c46  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_SchedulerRefreshTaskBeforeProtect@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_SchedulerRefreshTaskBeforeProtect>::__private_IsEnabled(void)
0x180069c4b  test    al, al
0x180069c4d  jz      loc_180069E28
0x180069c53  cmp     [rsi+29h], dil
0x180069c57  jz      loc_180069E28
0x180069c5d  lea     rax, aRefreshingCach; "Refreshing cached task definition after"...
0x180069c64  mov     [rsp+208h+var_1B8], rax
0x180069c69  mov     [rsp+208h+var_1B0], 46h ; 'F'
0x180069c72  lea     rcx, [rsp+208h+var_1B8]
0x180069c77  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x180069c7c  mov     [rsp+208h+var_D0], rdi
0x180069c84  mov     rcx, [rsp+208h+var_C8]
0x180069c8c  mov     rax, [rcx]
0x180069c8f  mov     [rsp+208h+var_D0], rdi
0x180069c97  lea     rdx, [rsp+208h+var_D0]
0x180069c9f  mov     rax, [rax+98h]
0x180069ca6  call    _guard_dispatch_icall
0x180069cab  mov     rcx, [rsp+208h]; this
0x180069cb3  test    eax, eax
0x180069cb5  js      loc_180069F77
0x180069cbb  mov     rbx, [rsi]
0x180069cbe  mov     rcx, [rsp+208h+var_D0]
0x180069cc6  mov     [rsi], rcx
0x180069cc9  test    rcx, rcx
0x180069ccc  jz      short loc_180069CDA
0x180069cce  mov     rax, [rcx]
0x180069cd1  mov     rax, [rax+8]
0x180069cd5  call    _guard_dispatch_icall
0x180069cda  test    rbx, rbx
0x180069cdd  jz      short loc_180069CEF
0x180069cdf  mov     rax, [rbx]
0x180069ce2  mov     rcx, rbx
0x180069ce5  mov     rax, [rax+10h]
0x180069ce9  call    _guard_dispatch_icall
0x180069cee  nop
0x180069cef  mov     [rsp+208h+bstrString], rdi
0x180069cf7  mov     rcx, [rsi]
0x180069cfa  mov     rax, [rcx]
0x180069cfd  mov     [rsp+208h+bstrString], rdi
0x180069d05  lea     rdx, [rsp+208h+bstrString]
0x180069d0d  mov     rax, [rax+98h]
0x180069d14  call    _guard_dispatch_icall
0x180069d19  mov     rcx, [rsp+208h]; this
0x180069d21  test    eax, eax
0x180069d23  js      loc_180069F8C
0x180069d29  mov     rbx, [rsp+208h+bstrString]
0x180069d31  lea     rax, aTaskDefinition; "Task definition refreshed: {}"
0x180069d38  mov     qword ptr [rsp+208h+var_188], rax
0x180069d40  mov     qword ptr [rsp+208h+var_188+8], 1Dh
0x180069d4c  lea     rcx, [rsp+208h+var_1B8]; this
0x180069d51  call    ??0_Format_arg_index@std@@QEAA@XZ; std::_Format_arg_index::_Format_arg_index(void)
0x180069d56  mov     [rsp+208h+var_1B0], rbx
0x180069d5b  mov     rax, 0B000000000000000h
0x180069d65  mov     [rsp+208h+var_1B8], rax
0x180069d6a  mov     ebx, 1
0x180069d6f  mov     qword ptr [rsp+208h+var_1A8], rbx
0x180069d74  lea     rax, [rsp+208h+var_1B8]
0x180069d79  mov     qword ptr [rsp+208h+var_1A8+8], rax
0x180069d7e  movaps  xmm0, [rsp+208h+var_188]
0x180069d86  movdqa  [rsp+208h+var_188], xmm0
0x180069d8f  lea     r8, [rsp+208h+var_1A8]
0x180069d94  lea     rdx, [rsp+208h+var_188]
0x180069d9c  lea     rcx, [rsp+208h+Src]; Src
0x180069da4  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@_W@std@@@0@@Z; std::vformat<0>(std::wstring_view,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,wchar_t>>)
0x180069da9  nop
0x180069daa  mov     rcx, [rax+10h]
0x180069dae  cmp     qword ptr [rax+18h], 7
0x180069db3  jbe     short loc_180069DB8
0x180069db5  mov     rax, [rax]
0x180069db8  mov     qword ptr [rsp+208h+var_1A8], rax
0x180069dbd  mov     qword ptr [rsp+208h+var_1A8+8], rcx
0x180069dc2  mov     edx, ebx
0x180069dc4  lea     rcx, [rsp+208h+var_1A8]
0x180069dc9  call    ?LogMessage@SystemInterface@@YAXV?$basic_zstring_view@_W@wil@@W4LoggingLevel@Telemetry@1@@Z; SystemInterface::LogMessage(wil::basic_zstring_view<wchar_t>,SystemInterface::Telemetry::LoggingLevel)
0x180069dce  nop
0x180069dcf  lea     rcx, [rsp+208h+Src]; void *
0x180069dd7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180069ddc  mov     [rsi+29h], dil
0x180069de0  mov     rcx, [rsp+208h+bstrString]; bstrString
0x180069de8  test    rcx, rcx
0x180069deb  jz      short loc_180069DF4
0x180069ded  call    cs:__imp_SysFreeString
0x180069df3  nop
0x180069df4  mov     rcx, [rsp+208h+var_D0]
0x180069dfc  test    rcx, rcx
0x180069dff  jz      short loc_180069E0E
0x180069e01  mov     rax, [rcx]
0x180069e04  mov     rax, [rax+10h]
0x180069e08  call    _guard_dispatch_icall
0x180069e0d  nop
0x180069e0e  jmp     short loc_180069E28
0x180069e10  mov     r15b, [rsp+208h+arg_8]
0x180069e18  mov     rsi, [rsp+208h+var_168]
0x180069e20  mov     r12, [rsp+208h+var_158]
0x180069e28  test    r15b, r15b
0x180069e2b  jz      short loc_180069E35
0x180069e2d  mov     rcx, rsi; this
0x180069e30  call    ?Protect@Task@Service@Windows@@AEAAXXZ; Windows::Service::Task::Protect(void)
0x180069e35  movaps  xmm0, xmmword ptr [r12]
0x180069e3a  movdqa  xmmword ptr [rsp+208h+var_1A8], xmm0
0x180069e40  lea     r8, [rsp+208h+var_1A8]
0x180069e45  mov     rdx, [rsp+208h+var_C8]
0x180069e4d  call    ?LogTaskModified@Task@Service@Windows@@AEAAXPEAUIRegisteredTask@@V?$basic_zstring_view@_W@wil@@@Z; Windows::Service::Task::LogTaskModified(IRegisteredTask *,wil::basic_zstring_view<wchar_t>)
0x180069e52  nop
0x180069e53  mov     rcx, [rsp+208h+var_C8]
0x180069e5b  test    rcx, rcx
0x180069e5e  jz      short loc_180069E6D
0x180069e60  mov     rax, [rcx]
0x180069e63  mov     rax, [rax+10h]
0x180069e67  call    _guard_dispatch_icall
0x180069e6c  nop
0x180069e6d  lea     rcx, [rsp+208h+var_108]; pvarg
0x180069e75  call    cs:__imp_VariantClear
0x180069e7b  nop
0x180069e7c  mov     rcx, [rsp+208h+var_C0]
0x180069e84  test    rcx, rcx
0x180069e87  jz      short loc_180069E96
0x180069e89  mov     rax, [rcx]
0x180069e8c  mov     rax, [rax+10h]
0x180069e90  call    _guard_dispatch_icall
0x180069e95  nop
0x180069e96  mov     rcx, [rsp+208h+var_B0]; bstrString
0x180069e9e  test    rcx, rcx
0x180069ea1  jz      short loc_180069EAA
0x180069ea3  call    cs:__imp_SysFreeString
0x180069ea9  nop
0x180069eaa  mov     rcx, [rsp+208h+var_B8]
0x180069eb2  test    rcx, rcx
0x180069eb5  jz      short loc_180069EC4
0x180069eb7  mov     rax, [rcx]
0x180069eba  mov     rax, [rax+10h]
0x180069ebe  call    _guard_dispatch_icall
0x180069ec3  nop
0x180069ec4  lea     rcx, [rsp+208h+pvarg]; pvarg
0x180069ecc  call    cs:__imp_VariantClear
0x180069ed2  mov     rcx, [rsp+208h+var_A8]
0x180069eda  xor     rcx, rsp; StackCookie
0x180069edd  call    __security_check_cookie
0x180069ee2  lea     r11, [rsp+208h+var_38]
0x180069eea  movaps  xmm6, xmmword ptr [r11-10h]
0x180069eef  movaps  xmm7, xmmword ptr [r11-20h]
0x180069ef4  movaps  xmm8, xmmword ptr [r11-30h]
0x180069ef9  movaps  xmm9, xmmword ptr [r11-40h]
0x180069efe  movaps  xmm10, xmmword ptr [r11-50h]
0x180069f03  movaps  xmm11, xmmword ptr [r11-60h]
0x180069f08  mov     rsp, r11
0x180069f0b  pop     r15
0x180069f0d  pop     r14
0x180069f0f  pop     r13
0x180069f11  pop     r12
0x180069f13  pop     rdi
0x180069f14  pop     rsi
0x180069f15  pop     rbx
0x180069f16  retn
0x180069f17  lea     r8, aCW1SPackagesMi_4; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180069f1e  mov     edx, 138Dh; void *
0x180069f23  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180069f29  mov     r9d, eax; char *
0x180069f2c  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180069f33  mov     edx, 0D9h; void *
0x180069f38  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180069f3e  lea     r8, aCW1SPackagesMi_4; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180069f45  mov     edx, 138Dh; void *
0x180069f4a  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180069f50  lea     r8, aCW1SPackagesMi_4; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180069f57  mov     edx, 138Dh; void *
0x180069f5c  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180069f62  mov     r9d, eax; char *
  ... truncated ...
```
