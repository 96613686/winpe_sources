# CUpdateDownloader::ValidateDownloadTypeCompatibility(tagDownloadType,IUpdateCollection *)

- ea: `0x180065434`
- end: `0x180065804`
- name: `?ValidateDownloadTypeCompatibility@CUpdateDownloader@@AEAAJW4tagDownloadType@@PEAUIUpdateCollection@@@Z`
- size: `976`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180063558`
- `0x180063a64`

## callees

- `0x180006ac4`
- `0x180060288`
- `0x180065434`
- `0x180091568`
- `0x18009ae75`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800654cf`
- `OLEAUT32!__imp_SysAllocString` at `0x1800654cf`
- `OLEAUT32!__imp_SysFreeString` at `0x180065672`
- `OLEAUT32!__imp_SysFreeString` at `0x180065672`
- `OLEAUT32!__imp_VariantInit` at `0x1800655ba`
- `OLEAUT32!__imp_VariantInit` at `0x1800655ba`
- `OLEAUT32!__imp_VariantClear` at `0x18006560d`
- `OLEAUT32!__imp_VariantClear` at `0x18006574f`
- `OLEAUT32!__imp_VariantClear` at `0x18006560d`
- `OLEAUT32!__imp_VariantClear` at `0x18006574f`

## string_xrefs

- `0x1800654c8`: `ContainsUpdateBootstrapper`
- `0x180065487`: `C:\__w\1\s\src\Client\comapi\UpdateDownloader.cpp`
- `0x1800654f1`: `C:\__w\1\s\src\Client\comapi\UpdateDownloader.cpp`
- `0x1800656db`: `C:\__w\1\s\src\Client\comapi\UpdateDownloader.cpp`
- `0x18006571c`: `C:\__w\1\s\src\Client\comapi\UpdateDownloader.cpp`
- `0x180065739`: `C:\__w\1\s\src\Client\comapi\UpdateDownloader.cpp`
- `0x180065761`: `C:\__w\1\s\src\Client\comapi\UpdateDownloader.cpp`
- `0x1800657a4`: `C:\__w\1\s\src\Client\comapi\UpdateDownloader.cpp`
- `0x1800657d6`: `C:\__w\1\s\src\Client\comapi\UpdateDownloader.cpp`
- `0x180065708`: `Update %ws does NOT have ContainsUpdateBootstrapper property.`
- `0x1800656c7`: `Update %ws does NOT support bootstrapper download, handler id is %lu.`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall CUpdateDownloader::ValidateDownloadTypeCompatibility(__int64 a1, int a2, __int64 a3)
{
  int v5; // ebx
  __int64 v6; // rdx
  OLECHAR *v7; // rbx
  int v8; // edi
  unsigned int v9; // esi
  int v10; // eax
  int v11; // eax
  int v12; // eax
  const char *v13; // rax
  const char *updated; // rax
  __int64 v15; // rdx
  int v16; // [rsp+28h] [rbp-E0h]
  _BYTE v17[112]; // [rsp+58h] [rbp-B0h] BYREF
  int v18; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v19; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v20; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v21; // [rsp+E0h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v23[36]; // [rsp+108h] [rbp+0h] BYREF
  int v24; // [rsp+12Ch] [rbp+24h]
  wil::details::in1diag3 *retaddr; // [rsp+220h] [rbp+118h]

  if ( !a2 )
    return 0;
  if ( !a3 )
  {
    v5 = -2147024809;
    v6 = 1087;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateDownloader.cpp",
      (const char *)(unsigned int)v5,
      v16);
    return (unsigned int)v5;
  }
  v18 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a3 + 80LL))(a3, &v18);
  if ( v5 < 0 )
  {
    v6 = 1096;
    goto LABEL_5;
  }
  v7 = SysAllocString(L"ContainsUpdateBootstrapper");
  if ( !v7 )
  {
    v8 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44C,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateDownloader.cpp",
      (const char *)0x8007000ELL,
      v16);
    goto LABEL_27;
  }
  v9 = 0;
  if ( v18 <= 0 )
  {
LABEL_26:
    v8 = 0;
    goto LABEL_27;
  }
  while ( 1 )
  {
    v21 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a3 + 56LL))(a3, v9, &v21);
    v8 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x451,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateDownloader.cpp",
        (const char *)(unsigned int)v10,
        v16);
      goto LABEL_45;
    }
    v20 = 0;
    v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v21)(
           v21,
           &GUID_e5f74104_b7f7_4d6a_a70a_9d066c2b59e6,
           &v20);
    if ( v8 < 0 )
    {
      v15 = 1108;
      goto LABEL_40;
    }
    memset_0(v23, 0, 0xE8u);
    v8 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v20 + 32LL))(v20, v23);
    if ( v8 < 0 )
    {
      v15 = 1111;
LABEL_40:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateDownloader.cpp",
        (const char *)(unsigned int)v8,
        v16);
      goto LABEL_41;
    }
    v19 = 0;
    v11 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v21)(
            v21,
            &GUID_769355a3_c5a0_497c_a606_560a36d2121c,
            &v19);
    v8 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45B,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateDownloader.cpp",
        (const char *)(unsigned int)v11,
        v16);
      goto LABEL_35;
    }
    VariantInit(&pvarg);
    v12 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, VARIANTARG *))(*(_QWORD *)v19 + 480LL))(v19, v7, &pvarg);
    v8 = v12;
    if ( v12 < 0 )
      break;
    if ( pvarg.vt != 11 || !pvarg.iVal )
    {
      updated = (const char *)Trace::UpdateIdToString::UpdateIdToString(
                                (Trace::UpdateIdToString *)v17,
                                (const struct tagDSGlobalUpdateId *)v23);
      v8 = -2145124297;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x465,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateDownloader.cpp",
        (const char *)0x80240037LL,
        (int)"Update %ws does NOT have ContainsUpdateBootstrapper property.",
        updated);
      goto LABEL_33;
    }
    if ( v24 != 12 )
    {
      v13 = (const char *)Trace::UpdateIdToString::UpdateIdToString(
                            (Trace::UpdateIdToString *)v17,
                            (const struct tagDSGlobalUpdateId *)v23);
      v8 = -2145124297;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x46C,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateDownloader.cpp",
        (const char *)0x80240037LL,
        (int)"Update %ws does NOT support bootstrapper download, handler id is %lu.",
        v13,
        v24);
      goto LABEL_33;
    }
    VariantClear(&pvarg);
    if ( v19 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      v19 = 0;
    }
    if ( v20 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      v20 = 0;
    }
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    if ( (int)++v9 >= v18 )
      goto LABEL_26;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x45F,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateDownloader.cpp",
    (const char *)(unsigned int)v12,
    v16);
LABEL_33:
  VariantClear(&pvarg);
LABEL_35:
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
LABEL_41:
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
LABEL_45:
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
LABEL_27:
  if ( v7 )
    SysFreeString(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180065434  mov     rax, rsp
0x180065437  mov     [rax+8], rbx
0x18006543b  mov     [rax+10h], rsi
0x18006543f  mov     [rax+20h], rdi
0x180065443  push    rbp
0x180065444  push    r14
0x180065446  push    r15
0x180065448  lea     rbp, [rax-118h]
0x18006544f  sub     rsp, 200h
0x180065456  mov     rax, cs:__security_cookie
0x18006545d  xor     rax, rsp
0x180065460  mov     [rbp+110h+var_20], rax
0x180065467  mov     r14, r8
0x18006546a  xor     r15d, r15d
0x18006546d  test    edx, edx
0x18006546f  jnz     short loc_180065478
0x180065471  xor     eax, eax
0x180065473  jmp     loc_18006567A
0x180065478  test    r14, r14
0x18006547b  jnz     short loc_1800654A4
0x18006547d  mov     ebx, 80070057h
0x180065482  mov     edx, 43Fh; void *
0x180065487  lea     r8, aCW1SSrcClientC_16; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18006548e  mov     r9d, ebx; char *
0x180065491  mov     rcx, [rbp+118h]; this
0x180065498  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006549d  mov     eax, ebx
0x18006549f  jmp     loc_18006567A
0x1800654a4  mov     [rbp+110h+var_150], r15d
0x1800654a8  mov     rax, [r8]
0x1800654ab  lea     rdx, [rbp+110h+var_150]
0x1800654af  mov     rcx, r14
0x1800654b2  mov     rax, [rax+50h]
0x1800654b6  call    _guard_dispatch_icall
0x1800654bb  mov     ebx, eax
0x1800654bd  test    eax, eax
0x1800654bf  jns     short loc_1800654C8
0x1800654c1  mov     edx, 448h
0x1800654c6  jmp     short loc_180065487
0x1800654c8  lea     rcx, psz; "ContainsUpdateBootstrapper"
0x1800654cf  call    cs:__imp_SysAllocString
0x1800654d5  mov     rbx, rax
0x1800654d8  mov     [rsp+210h+var_1D0], rax
0x1800654dd  test    rax, rax
0x1800654e0  jnz     short loc_180065507
0x1800654e2  mov     rcx, [rbp+118h]; this
0x1800654e9  mov     edi, 8007000Eh
0x1800654ee  mov     r9d, edi; char *
0x1800654f1  lea     r8, aCW1SSrcClientC_16; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x1800654f8  mov     edx, 44Ch; void *
0x1800654fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065502  jmp     loc_18006566A
0x180065507  mov     esi, r15d
0x18006550a  cmp     [rbp+110h+var_150], r15d
0x18006550e  jle     loc_180065667
0x180065514  mov     [rbp+110h+var_138], r15
0x180065518  mov     rax, [r14]
0x18006551b  lea     r8, [rbp+110h+var_138]
0x18006551f  mov     edx, esi
0x180065521  mov     rcx, r14
0x180065524  mov     rax, [rax+38h]
0x180065528  call    _guard_dispatch_icall
0x18006552d  mov     edi, eax
0x18006552f  test    eax, eax
0x180065531  js      loc_1800657CC
0x180065537  mov     [rbp+110h+var_140], r15
0x18006553b  mov     rcx, [rbp+110h+var_138]
0x18006553f  mov     rax, [rcx]
0x180065542  lea     r8, [rbp+110h+var_140]
0x180065546  lea     rdx, _GUID_e5f74104_b7f7_4d6a_a70a_9d066c2b59e6
0x18006554d  mov     rax, [rax]
0x180065550  call    _guard_dispatch_icall
0x180065555  mov     edi, eax
0x180065557  test    eax, eax
0x180065559  js      loc_180065795
0x18006555f  xor     edx, edx; Val
0x180065561  mov     r8d, 0E8h; Size
0x180065567  lea     rcx, [rbp+110h+var_110]; void *
0x18006556b  call    memset_0
0x180065570  mov     rcx, [rbp+110h+var_140]
0x180065574  mov     rax, [rcx]
0x180065577  lea     rdx, [rbp+110h+var_110]
0x18006557b  mov     rax, [rax+20h]
0x18006557f  call    _guard_dispatch_icall
0x180065584  mov     edi, eax
0x180065586  test    eax, eax
0x180065588  js      loc_18006578E
0x18006558e  mov     [rbp+110h+var_148], r15
0x180065592  mov     rcx, [rbp+110h+var_138]
0x180065596  mov     rax, [rcx]
0x180065599  lea     r8, [rbp+110h+var_148]
0x18006559d  lea     rdx, _GUID_769355a3_c5a0_497c_a606_560a36d2121c
0x1800655a4  mov     rax, [rax]
0x1800655a7  call    _guard_dispatch_icall
0x1800655ac  mov     edi, eax
0x1800655ae  test    eax, eax
0x1800655b0  js      loc_180065757
0x1800655b6  lea     rcx, [rbp+110h+pvarg]; pvarg
0x1800655ba  call    cs:__imp_VariantInit
0x1800655c0  nop
0x1800655c1  mov     rcx, [rbp+110h+var_148]
0x1800655c5  mov     rax, [rcx]
0x1800655c8  lea     r8, [rbp+110h+pvarg]
0x1800655cc  mov     rdx, rbx
0x1800655cf  mov     rax, [rax+1E0h]
0x1800655d6  call    _guard_dispatch_icall
0x1800655db  mov     edi, eax
0x1800655dd  test    eax, eax
0x1800655df  js      loc_18006572F
0x1800655e5  mov     eax, 0Bh
0x1800655ea  cmp     ax, word ptr [rbp+110h+pvarg]
0x1800655ee  jnz     loc_1800656EE
0x1800655f4  cmp     r15w, word ptr [rbp+110h+pvarg+8]
0x1800655f9  jz      loc_1800656EE
0x1800655ff  cmp     [rbp+110h+var_EC], 0Ch
0x180065603  jnz     loc_1800656A6
0x180065609  lea     rcx, [rbp+110h+pvarg]; pvarg
0x18006560d  call    cs:__imp_VariantClear
0x180065613  nop
0x180065614  mov     rcx, [rbp+110h+var_148]
0x180065618  test    rcx, rcx
0x18006561b  jz      short loc_18006562D
0x18006561d  mov     rax, [rcx]
0x180065620  mov     rax, [rax+10h]
0x180065624  call    _guard_dispatch_icall
0x180065629  mov     [rbp+110h+var_148], r15
0x18006562d  mov     rcx, [rbp+110h+var_140]
0x180065631  test    rcx, rcx
0x180065634  jz      short loc_180065646
0x180065636  mov     rax, [rcx]
0x180065639  mov     rax, [rax+10h]
0x18006563d  call    _guard_dispatch_icall
0x180065642  mov     [rbp+110h+var_140], r15
0x180065646  mov     rcx, [rbp+110h+var_138]
0x18006564a  test    rcx, rcx
0x18006564d  jz      short loc_18006565C
0x18006564f  mov     rax, [rcx]
0x180065652  mov     rax, [rax+10h]
0x180065656  call    _guard_dispatch_icall
0x18006565b  nop
0x18006565c  inc     esi
0x18006565e  cmp     esi, [rbp+110h+var_150]
0x180065661  jl      loc_180065514
0x180065667  mov     edi, r15d
0x18006566a  test    rbx, rbx
0x18006566d  jz      short loc_180065678
0x18006566f  mov     rcx, rbx; bstrString
0x180065672  call    cs:__imp_SysFreeString
0x180065678  mov     eax, edi
0x18006567a  mov     rcx, [rbp+110h+var_20]
0x180065681  xor     rcx, rsp; StackCookie
0x180065684  call    __security_check_cookie
0x180065689  lea     r11, [rsp+210h+var_10]
0x180065691  mov     rbx, [r11+20h]
0x180065695  mov     rsi, [r11+28h]
0x180065699  mov     rdi, [r11+38h]
0x18006569d  mov     rsp, r11
0x1800656a0  pop     r15
0x1800656a2  pop     r14
0x1800656a4  pop     rbp
0x1800656a5  retn
0x1800656a6  lea     rdx, [rbp+110h+var_110]; struct tagDSGlobalUpdateId *
0x1800656aa  lea     rcx, [rsp+210h+var_1C0]; this
0x1800656af  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x1800656b4  mov     rcx, [rbp+118h]; this
0x1800656bb  mov     edx, [rbp+110h+var_EC]
0x1800656be  mov     [rsp+210h+var_1E0], edx
0x1800656c2  mov     [rsp+210h+var_1E8], rax; char *
0x1800656c7  lea     rax, aUpdateWsDoesNo_0; "Update %ws does NOT support bootstrappe"...
0x1800656ce  mov     qword ptr [rsp+210h+var_1F0], rax; int
0x1800656d3  mov     edi, 80240037h
0x1800656d8  mov     r9d, edi; char *
0x1800656db  lea     r8, aCW1SSrcClientC_16; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x1800656e2  mov     edx, 46Ch; void *
0x1800656e7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800656ec  jmp     short loc_18006574B
0x1800656ee  lea     rdx, [rbp+110h+var_110]; struct tagDSGlobalUpdateId *
0x1800656f2  lea     rcx, [rsp+210h+var_1C0]; this
0x1800656f7  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x1800656fc  mov     rcx, [rbp+118h]; this
0x180065703  mov     [rsp+210h+var_1E8], rax; char *
0x180065708  lea     rax, aUpdateWsDoesNo; "Update %ws does NOT have ContainsUpdate"...
0x18006570f  mov     qword ptr [rsp+210h+var_1F0], rax; int
0x180065714  mov     edi, 80240037h
0x180065719  mov     r9d, edi; char *
0x18006571c  lea     r8, aCW1SSrcClientC_16; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180065723  mov     edx, 465h; void *
0x180065728  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18006572d  jmp     short loc_18006574B
0x18006572f  mov     rcx, [rbp+118h]; this
0x180065736  mov     r9d, eax; char *
0x180065739  lea     r8, aCW1SSrcClientC_16; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180065740  mov     edx, 45Fh; void *
0x180065745  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006574a  nop
0x18006574b  lea     rcx, [rbp+110h+pvarg]; pvarg
0x18006574f  call    cs:__imp_VariantClear
0x180065755  jmp     short loc_180065773
0x180065757  mov     rcx, [rbp+118h]; this
0x18006575e  mov     r9d, eax; char *
0x180065761  lea     r8, aCW1SSrcClientC_16; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180065768  mov     edx, 45Bh; void *
0x18006576d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065772  nop
0x180065773  mov     rcx, [rbp+110h+var_148]
0x180065777  test    rcx, rcx
0x18006577a  jz      short loc_18006578C
0x18006577c  mov     rax, [rcx]
0x18006577f  mov     rax, [rax+10h]
0x180065783  call    _guard_dispatch_icall
0x180065788  mov     [rbp+110h+var_148], r15
0x18006578c  jmp     short loc_1800657B1
0x18006578e  mov     edx, 457h
0x180065793  jmp     short loc_18006579A
0x180065795  mov     edx, 454h; void *
0x18006579a  mov     rcx, [rbp+118h]; this
0x1800657a1  mov     r9d, edi; char *
0x1800657a4  lea     r8, aCW1SSrcClientC_16; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x1800657ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800657b0  nop
0x1800657b1  mov     rcx, [rbp+110h+var_140]
0x1800657b5  test    rcx, rcx
0x1800657b8  jz      short loc_1800657CA
0x1800657ba  mov     rax, [rcx]
0x1800657bd  mov     rax, [rax+10h]
0x1800657c1  call    _guard_dispatch_icall
0x1800657c6  mov     [rbp+110h+var_140], r15
0x1800657ca  jmp     short loc_1800657E8
0x1800657cc  mov     rcx, [rbp+118h]; this
0x1800657d3  mov     r9d, eax; char *
0x1800657d6  lea     r8, aCW1SSrcClientC_16; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x1800657dd  mov     edx, 451h; void *
0x1800657e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800657e7  nop
0x1800657e8  mov     rcx, [rbp+110h+var_138]
0x1800657ec  test    rcx, rcx
0x1800657ef  jz      short loc_1800657FE
0x1800657f1  mov     rax, [rcx]
0x1800657f4  mov     rax, [rax+10h]
0x1800657f8  call    _guard_dispatch_icall
0x1800657fd  nop
0x1800657fe  jmp     loc_18006566A
```
