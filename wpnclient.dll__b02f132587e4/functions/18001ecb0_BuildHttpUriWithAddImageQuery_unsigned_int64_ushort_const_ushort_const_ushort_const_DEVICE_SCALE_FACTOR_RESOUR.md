# BuildHttpUriWithAddImageQuery(unsigned __int64,ushort const *,ushort const *,ushort const *,DEVICE_SCALE_FACTOR *,RESOURCE_CONTRAST *,ushort * *)

- ea: `0x18001ecb0`
- end: `0x18001f03c`
- name: `?BuildHttpUriWithAddImageQuery@@YAJ_KPEBG11PEAW4DEVICE_SCALE_FACTOR@@PEAW4RESOURCE_CONTRAST@@PEAPEAG@Z`
- size: `908`
- prototype: `int(unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, enum DEVICE_SCALE_FACTOR *, enum RESOURCE_CONTRAST *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005670`
- `0x1800074d0`
- `0x180008910`
- `0x18000e7f0`
- `0x18001b848`
- `0x18001ecb0`
- `0x18001f044`
- `0x18001ff00`
- `0x180032010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001efda`
- `OLEAUT32!__imp_SysFreeString` at `0x18001efda`
- `urlmon!CreateUri` at `0x18001ed83`
- `urlmon!CreateUri` at `0x18001ed83`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall BuildHttpUriWithAddImageQuery(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        enum DEVICE_SCALE_FACTOR *a5,
        enum RESOURCE_CONTRAST *a6,
        unsigned __int16 **a7)
{
  unsigned __int16 *v9; // r14
  int v10; // eax
  const unsigned __int16 *v11; // rsi
  HRESULT v12; // eax
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, _QWORD, __int64 *); // rbx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64, _QWORD, _QWORD); // rbx
  int v22; // eax
  int v23; // eax
  __int64 v24; // rdx
  int v25; // eax
  unsigned int v26; // ebx
  int v28; // [rsp+20h] [rbp-61h]
  int v29; // [rsp+20h] [rbp-61h]
  __int64 v30; // [rsp+30h] [rbp-51h] BYREF
  int v31[2]; // [rsp+38h] [rbp-49h] BYREF
  __int64 v32; // [rsp+40h] [rbp-41h] BYREF
  IUri *ppURI; // [rsp+48h] [rbp-39h] BYREF
  int v34; // [rsp+50h] [rbp-31h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-29h] BYREF
  unsigned __int16 *v36; // [rsp+60h] [rbp-21h] BYREF
  unsigned __int16 *v37; // [rsp+68h] [rbp-19h] BYREF
  __int64 v38; // [rsp+70h] [rbp-11h]
  __int64 v39; // [rsp+78h] [rbp-9h]
  unsigned __int16 v40[8]; // [rsp+80h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+47h]

  v9 = 0;
  *a7 = 0;
  if ( a5 )
  {
    v10 = StringCchPrintfW(v40, 5u, L"%d", *(unsigned int *)a5);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x166,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
        (const char *)(unsigned int)v10,
        v28);
    v9 = v40;
  }
  if ( a6 )
  {
    if ( *(_DWORD *)a6 )
    {
      if ( *(_DWORD *)a6 == 2 )
      {
        v11 = L"black";
        goto LABEL_13;
      }
      if ( *(_DWORD *)a6 == 3 )
      {
        v11 = L"white";
        goto LABEL_13;
      }
    }
    v11 = L"standard";
  }
  else
  {
    v11 = 0;
  }
LABEL_13:
  ppURI = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppURI);
  v12 = CreateUri(a2, 0x100u, 0, &ppURI);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x16D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)(unsigned int)v12,
      v28);
  v32 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
  v13 = ((__int64 (__fastcall *)(IUri *, GUID *, __int64 *))ppURI->lpVtbl->QueryInterface)(
          ppURI,
          &GUID_e982ce48_0b96_440c_bc37_0c869b27a29e,
          &v32);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x171,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)(unsigned int)v13,
      v28);
  v30 = 0;
  v14 = v32;
  v15 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v32 + 32LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  v16 = v15(v14, 0, 0, &v30);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x175,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)(unsigned int)v16,
      v28);
  v34 = 0;
  v36 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, int *, unsigned __int16 **))(*(_QWORD *)v30 + 104LL))(v30, &v34, &v36);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x17B,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)(unsigned int)v17,
      v28);
  v37 = 0;
  v38 = 0;
  v39 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v37);
  v38 = -1;
  v39 = -1;
  v18 = CreateQueryStringWithAttributes(v36, v9, v11, a4, &v37);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x17F,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)(unsigned int)v18,
      v29);
  v19 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v30 + 168LL))(v30, v37);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x182,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)(unsigned int)v19,
      v29);
  *(_QWORD *)v31 = 0;
  v20 = v30;
  v21 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v30 + 32LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v31);
  v22 = v21(v20, 256, 0, 0);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x187,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)(unsigned int)v22,
      (int)v31);
  bstrString = 0;
  v23 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**(_QWORD **)v31 + 56LL))(*(_QWORD *)v31, &bstrString);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18B,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)(unsigned int)v23,
      (int)v31);
  v25 = _AllocString<CTCoAllocPolicy>(retaddr, v24, bstrString, a7);
  v26 = v25;
  if ( v25 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18E,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)(unsigned int)v25,
      (int)v31);
  SysFreeString(bstrString);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v31);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v37);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppURI);
  return v26;
}

```

## disassembly

```asm
0x18001ecb0  mov     [rsp-8+arg_0], rbx
0x18001ecb5  mov     [rsp-8+arg_10], rsi
0x18001ecba  push    rbp
0x18001ecbb  push    rdi
0x18001ecbc  push    r12
0x18001ecbe  push    r14
0x18001ecc0  push    r15
0x18001ecc2  lea     rbp, [rsp-1Fh]
0x18001ecc7  sub     rsp, 0A0h
0x18001ecce  mov     rax, cs:__security_cookie
0x18001ecd5  xor     rax, rsp
0x18001ecd8  mov     [rbp+3Fh+var_30], rax
0x18001ecdc  mov     r12, r9
0x18001ecdf  mov     rbx, rdx
0x18001ece2  mov     r9, [rbp+3Fh+arg_20]
0x18001ece6  mov     r15, [rbp+3Fh+arg_30]
0x18001ecea  xor     r14d, r14d
0x18001eced  mov     [r15], r14
0x18001ecf0  test    r9, r9
0x18001ecf3  jz      short loc_18001ED2D
0x18001ecf5  mov     r9d, [r9]
0x18001ecf8  lea     r8, aD; "%d"
0x18001ecff  lea     edx, [r14+5]; unsigned __int64
0x18001ed03  lea     rcx, [rbp+3Fh+var_40]; unsigned __int16 *
0x18001ed07  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001ed0c  mov     rcx, [rbp+47h]; this
0x18001ed10  test    eax, eax
0x18001ed12  jns     short loc_18001ED29
0x18001ed14  mov     r9d, eax; char *
0x18001ed17  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001ed1e  mov     edx, 166h; void *
0x18001ed23  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ed29  lea     r14, [rbp+3Fh+var_40]
0x18001ed2d  mov     rcx, [rbp+3Fh+arg_28]
0x18001ed31  test    rcx, rcx
0x18001ed34  jz      short loc_18001ED61
0x18001ed36  mov     ecx, [rcx]
0x18001ed38  test    ecx, ecx
0x18001ed3a  jz      short loc_18001ED58
0x18001ed3c  sub     ecx, 2
0x18001ed3f  jz      short loc_18001ED4F
0x18001ed41  cmp     ecx, 1
0x18001ed44  jnz     short loc_18001ED58
0x18001ed46  lea     rsi, aWhite; "white"
0x18001ed4d  jmp     short loc_18001ED63
0x18001ed4f  lea     rsi, aBlack; "black"
0x18001ed56  jmp     short loc_18001ED63
0x18001ed58  lea     rsi, aStandard; "standard"
0x18001ed5f  jmp     short loc_18001ED63
0x18001ed61  xor     esi, esi
0x18001ed63  mov     [rbp+3Fh+ppURI], 0
0x18001ed6b  lea     rcx, [rbp+3Fh+ppURI]
0x18001ed6f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ed74  lea     r9, [rbp+3Fh+ppURI]; ppURI
0x18001ed78  xor     r8d, r8d; dwReserved
0x18001ed7b  mov     edx, 100h; dwFlags
0x18001ed80  mov     rcx, rbx; pwzURI
0x18001ed83  call    cs:__imp_CreateUri
0x18001ed89  mov     rcx, [rbp+47h]; this
0x18001ed8d  test    eax, eax
0x18001ed8f  jns     short loc_18001EDA6
0x18001ed91  mov     r9d, eax; char *
0x18001ed94  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001ed9b  mov     edx, 16Dh; void *
0x18001eda0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001eda6  mov     [rbp+3Fh+var_80], 0
0x18001edae  lea     rcx, [rbp+3Fh+var_80]
0x18001edb2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001edb7  nop
0x18001edb8  mov     rcx, [rbp+3Fh+ppURI]
0x18001edbc  mov     rax, [rcx]
0x18001edbf  lea     r8, [rbp+3Fh+var_80]
0x18001edc3  lea     rdx, _GUID_e982ce48_0b96_440c_bc37_0c869b27a29e
0x18001edca  mov     rax, [rax]
0x18001edcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edd2  nop
0x18001edd3  mov     rcx, [rbp+47h]; this
0x18001edd7  test    eax, eax
0x18001edd9  jns     short loc_18001EDF0
0x18001eddb  mov     r9d, eax; char *
0x18001edde  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001ede5  mov     edx, 171h; void *
0x18001edea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001edf0  mov     [rbp+3Fh+var_90], 0
0x18001edf8  mov     rdi, [rbp+3Fh+var_80]
0x18001edfc  mov     rax, [rdi]
0x18001edff  mov     rbx, [rax+20h]
0x18001ee03  lea     rcx, [rbp+3Fh+var_90]
0x18001ee07  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ee0c  lea     r9, [rbp+3Fh+var_90]
0x18001ee10  xor     r8d, r8d
0x18001ee13  xor     edx, edx
0x18001ee15  mov     rcx, rdi
0x18001ee18  mov     rax, rbx
0x18001ee1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee20  mov     rcx, [rbp+47h]; this
0x18001ee24  test    eax, eax
0x18001ee26  jns     short loc_18001EE3D
0x18001ee28  mov     r9d, eax; char *
0x18001ee2b  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001ee32  mov     edx, 175h; void *
0x18001ee37  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ee3d  mov     [rbp+3Fh+var_70], 0
0x18001ee44  mov     [rbp+3Fh+var_60], 0
0x18001ee4c  mov     rcx, [rbp+3Fh+var_90]
0x18001ee50  mov     rax, [rcx]
0x18001ee53  lea     r8, [rbp+3Fh+var_60]
0x18001ee57  lea     rdx, [rbp+3Fh+var_70]
0x18001ee5b  mov     rax, [rax+68h]
0x18001ee5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee64  mov     rcx, [rbp+47h]; this
0x18001ee68  test    eax, eax
0x18001ee6a  jns     short loc_18001EE81
0x18001ee6c  mov     r9d, eax; char *
0x18001ee6f  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001ee76  mov     edx, 17Bh; void *
0x18001ee7b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ee81  mov     [rbp+3Fh+var_58], 0
0x18001ee89  mov     [rbp+3Fh+var_50], 0
0x18001ee91  mov     [rbp+3Fh+var_48], 0
0x18001ee99  lea     rcx, [rbp+3Fh+var_58]
0x18001ee9d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001eea2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001eea6  mov     [rbp+3Fh+var_50], rax
0x18001eeaa  mov     [rbp+3Fh+var_48], rax
0x18001eeae  lea     rax, [rbp+3Fh+var_58]
0x18001eeb2  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18001eeb7  mov     r9, r12; unsigned __int16 *
0x18001eeba  mov     r8, rsi; unsigned __int16 *
0x18001eebd  mov     rdx, r14; unsigned __int16 *
0x18001eec0  mov     rcx, [rbp+3Fh+var_60]; unsigned __int16 *
0x18001eec4  call    ?CreateQueryStringWithAttributes@@YAJPEBG000PEAPEAG@Z; CreateQueryStringWithAttributes(ushort const *,ushort const *,ushort const *,ushort const *,ushort * *)
0x18001eec9  mov     rcx, [rbp+47h]; this
0x18001eecd  test    eax, eax
0x18001eecf  jns     short loc_18001EEE6
0x18001eed1  mov     r9d, eax; char *
0x18001eed4  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001eedb  mov     edx, 17Fh; void *
0x18001eee0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001eee6  mov     rcx, [rbp+3Fh+var_90]
0x18001eeea  mov     rax, [rcx]
0x18001eeed  mov     rdx, [rbp+3Fh+var_58]
0x18001eef1  mov     rax, [rax+0A8h]
0x18001eef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eefd  mov     rcx, [rbp+47h]; this
0x18001ef01  test    eax, eax
0x18001ef03  jns     short loc_18001EF1A
0x18001ef05  mov     r9d, eax; char *
0x18001ef08  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001ef0f  mov     edx, 182h; void *
0x18001ef14  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ef1a  mov     qword ptr [rbp+3Fh+var_88], 0
0x18001ef22  mov     rdi, [rbp+3Fh+var_90]
0x18001ef26  mov     rax, [rdi]
0x18001ef29  mov     rbx, [rax+20h]
0x18001ef2d  lea     rcx, [rbp+3Fh+var_88]
0x18001ef31  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ef36  lea     rax, [rbp+3Fh+var_88]
0x18001ef3a  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18001ef3f  xor     r9d, r9d
0x18001ef42  xor     r8d, r8d
0x18001ef45  mov     edx, 100h
0x18001ef4a  mov     rcx, rdi
0x18001ef4d  mov     rax, rbx
0x18001ef50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef55  mov     rcx, [rbp+47h]; this
0x18001ef59  test    eax, eax
0x18001ef5b  jns     short loc_18001EF72
0x18001ef5d  mov     r9d, eax; char *
0x18001ef60  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001ef67  mov     edx, 187h; void *
0x18001ef6c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ef72  mov     [rbp+3Fh+bstrString], 0
0x18001ef7a  mov     rcx, qword ptr [rbp+3Fh+var_88]
0x18001ef7e  mov     rax, [rcx]
0x18001ef81  lea     rdx, [rbp+3Fh+bstrString]
0x18001ef85  mov     rax, [rax+38h]
0x18001ef89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef8e  mov     rcx, [rbp+47h]; this
0x18001ef92  test    eax, eax
0x18001ef94  jns     short loc_18001EFAB
0x18001ef96  mov     r9d, eax; char *
0x18001ef99  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001efa0  mov     edx, 18Bh; void *
0x18001efa5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001efab  mov     r9, r15
0x18001efae  mov     r8, [rbp+3Fh+bstrString]
0x18001efb2  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18001efb7  mov     ebx, eax
0x18001efb9  mov     rcx, [rbp+47h]; this
0x18001efbd  test    eax, eax
0x18001efbf  jns     short loc_18001EFD6
0x18001efc1  mov     r9d, eax; char *
0x18001efc4  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001efcb  mov     edx, 18Eh; void *
0x18001efd0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001efd6  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x18001efda  call    cs:__imp_SysFreeString
0x18001efe0  nop
0x18001efe1  lea     rcx, [rbp+3Fh+var_88]
0x18001efe5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001efea  nop
0x18001efeb  lea     rcx, [rbp+3Fh+var_58]
0x18001efef  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001eff4  nop
0x18001eff5  lea     rcx, [rbp+3Fh+var_90]
0x18001eff9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001effe  nop
0x18001efff  lea     rcx, [rbp+3Fh+var_80]
0x18001f003  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f008  nop
0x18001f009  lea     rcx, [rbp+3Fh+ppURI]
0x18001f00d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f012  mov     eax, ebx
0x18001f014  mov     rcx, [rbp+3Fh+var_30]
0x18001f018  xor     rcx, rsp; StackCookie
0x18001f01b  call    __security_check_cookie
0x18001f020  lea     r11, [rsp+0C0h+var_20]
0x18001f028  mov     rbx, [r11+30h]
0x18001f02c  mov     rsi, [r11+40h]
0x18001f030  mov     rsp, r11
0x18001f033  pop     r15
0x18001f035  pop     r14
0x18001f037  pop     r12
0x18001f039  pop     rdi
0x18001f03a  pop     rbp
0x18001f03b  retn
```
