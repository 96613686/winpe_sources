# TdhpGetTraceEventInfoWBEM

- ea: `0x180029f04`
- end: `0x18002a3bb`
- name: `TdhpGetTraceEventInfoWBEM`
- size: `1207`
- prototype: `__int64 __fastcall(__int64, _QWORD *, int *, int *, int *, int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x18001443c`

## callees

- `0x180014fd8`
- `0x1800159ac`
- `0x180018a64`
- `0x18001d1d0`
- `0x18001ea64`
- `0x18001eb98`
- `0x18001ff2c`
- `0x18002949c`
- `0x18002996c`
- `0x1800299f4`
- `0x180029c44`
- `0x180029d04`
- `0x180029da4`
- `0x180029f04`
- `0x18002a3c4`
- `0x18002aa4c`
- `0x18004c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a1e2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a1e2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180029f97`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180029f97`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180029ffc`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180029ffc`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180029fe4`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180029fe4`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18002a042`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18002a042`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18002a2fa`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18002a2fa`

## string_xrefs

- `0x18002a2d1`: `XMLFragment`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TdhpGetTraceEventInfoWBEM(__int64 a1, _QWORD *a2, int *a3, int *a4, int *a5, int *a6)
{
  __int64 v7; // rsi
  SAFEARRAY *v8; // rcx
  int v9; // r12d
  int v10; // r13d
  int v11; // r14d
  int v12; // edi
  __int64 (__fastcall *v13)(__int64, const wchar_t *, __int64, __int128 *, __int128 *); // rbx
  int v14; // ebx
  HRESULT Element; // ebx
  int v16; // r12d
  _QWORD *v17; // rbx
  __int64 (__fastcall *v18)(__int64, BSTR, __int64); // rdi
  __int64 v19; // rax
  __int64 v20; // rsi
  int (__fastcall *v21)(__int64, const wchar_t *, _QWORD, __int128 *, _QWORD); // rdi
  __int64 v22; // rax
  __int16 v23; // si
  _QWORD *v24; // rdi
  char v25; // al
  __int16 ArraySize; // ax
  char HasEventMap; // al
  __int64 ClassName; // rax
  char ActivityIDOrRelatedActivityID; // al
  int v30; // ecx
  __int64 v31; // rsi
  __int64 (__fastcall *v32)(__int64, const wchar_t *, _QWORD, __int128 *, _QWORD); // rdi
  UINT v33; // eax
  unsigned int v34; // ebx
  __int64 v36; // [rsp+48h] [rbp-79h] BYREF
  int v37; // [rsp+50h] [rbp-71h]
  unsigned int v38; // [rsp+54h] [rbp-6Dh] BYREF
  LONG plLbound; // [rsp+58h] [rbp-69h] BYREF
  __int128 pv; // [rsp+60h] [rbp-61h] BYREF
  __int64 v41; // [rsp+70h] [rbp-51h]
  SAFEARRAY *psa; // [rsp+78h] [rbp-49h] BYREF
  LONG plUbound; // [rsp+80h] [rbp-41h] BYREF
  int v44; // [rsp+84h] [rbp-3Dh]
  BSTR bstr; // [rsp+88h] [rbp-39h]
  __int128 v46; // [rsp+90h] [rbp-31h] BYREF
  __int64 v47; // [rsp+A0h] [rbp-21h]
  __int64 v48; // [rsp+A8h] [rbp-19h]
  char v49[8]; // [rsp+B0h] [rbp-11h] BYREF
  __int128 v50; // [rsp+B8h] [rbp-9h] BYREF
  __int64 v51; // [rsp+C8h] [rbp+7h]

  v7 = a1;
  plLbound = 0;
  plUbound = 0;
  v8 = 0;
  v38 = 0;
  v9 = -1;
  v37 = -1;
  v44 = -1;
  v10 = 0;
  v11 = 0;
  v12 = 1;
  pv = 0;
  DWORD2(pv) = 1;
  LOWORD(pv) = 3;
  v50 = pv;
  v51 = 0;
  while ( 1 )
  {
    v13 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int128 *, __int128 *))(*(_QWORD *)v7 + 56LL);
    *(_QWORD *)&pv = 0;
    *((_QWORD *)&pv + 1) = &psa;
    psa = 0;
    if ( v8 )
      SafeArrayDestroy(v8);
    v14 = v13(v7, L"WmiDataId", 3, &v50, &pv);
    __1__out_ptr_t_V__unique_ptr_UtagSAFEARRAY__U__generic_delete_UtagSAFEARRAY__U__generic_deallocate__MP6AJPEAUtagSAFEARRAY___Z1_SafeArrayDestroy__YAJ0_ZPEAU1__tlx___tlx___utl__PEAUtagSAFEARRAY____V_utl__QEAA_XZ(&pv);
    if ( v14 )
      break;
    if ( SafeArrayGetLBound(psa, 1u, &plLbound) < 0 || SafeArrayGetUBound(psa, 1u, &plUbound) < 0 )
      goto LABEL_44;
    if ( plUbound < 0 )
      break;
    if ( plLbound != plUbound )
      goto LABEL_44;
    *(_QWORD *)&pv = 0;
    *((_QWORD *)&pv + 1) = &v36;
    v36 = 0;
    Element = SafeArrayGetElement(psa, &plLbound, &pv);
    utl::out_ptr_t<utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>,wchar_t *,>::~out_ptr_t<utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>,wchar_t *,>(&pv);
    if ( Element < 0 || !(unsigned __int8)utl::list<BSTR_INFO,utl::allocator<BSTR_INFO>>::emplace_back<,0>(a2) )
    {
      utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(&v36);
LABEL_44:
      v34 = 4210;
      goto LABEL_45;
    }
    utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::operator=(a2[1] + 16LL, &v36);
    ++v12;
    pv = 0;
    DWORD2(pv) = v12;
    LOWORD(pv) = 3;
    v50 = pv;
    v51 = 0;
    utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(&v36);
    v8 = psa;
  }
  v10 = v12 - 1;
  if ( (unsigned int)(v12 - 1) > 1 )
    v11 = 24 * v10 - 24;
  v16 = 0;
  v17 = (_QWORD *)*a2;
  while ( v17 != a2 )
  {
    bstr = (BSTR)v17[2];
    if ( (*(int (__fastcall **)(__int64, BSTR, _QWORD, _QWORD, unsigned int *, _QWORD))(*(_QWORD *)v7 + 32LL))(
           v7,
           bstr,
           0,
           0,
           &v38,
           0) < 0 )
      goto LABEL_43;
    v36 = 0;
    v18 = *(__int64 (__fastcall **)(__int64, BSTR, __int64))(*(_QWORD *)v7 + 88LL);
    v19 = utl::out_ptr<void,utl::unique_ptr<IWbemQualifierSet,tlx::release_delete>,>(&pv, &v36);
    LODWORD(v18) = v18(v7, bstr, v19);
    utl::out_ptr_t<utl::unique_ptr<IWbemQualifierSet,tlx::release_delete>,IWbemQualifierSet *,>::~out_ptr_t<utl::unique_ptr<IWbemQualifierSet,tlx::release_delete>,IWbemQualifierSet *,>(&pv);
    if ( (int)v18 < 0 )
      goto LABEL_42;
    TdhpGetTypeFromWBEM(v38, v36, (char *)v17 + 46, v17 + 6);
    v46 = 0;
    v47 = 0;
    v20 = v36;
    v21 = *(int (__fastcall **)(__int64, const wchar_t *, _QWORD, __int128 *, _QWORD))(*(_QWORD *)v36 + 24LL);
    tlx::unique_variant::reset((tlx::unique_variant *)&v46);
    if ( v21(v20, L"WmiSizeIs", 0, &v46, 0) >= 0 && (_WORD)v46 == 8 )
    {
      v22 = *((_QWORD *)&v46 + 1);
      v48 = *((_QWORD *)&v46 + 1);
      v23 = 0;
      v24 = (_QWORD *)*a2;
      while ( v24 != a2 )
      {
        if ( !(unsigned int)_o__wcsicmp(v24[2], v22) )
        {
          *((_WORD *)v17 + 27) = v23;
          v25 = 1;
          goto LABEL_27;
        }
        ++v23;
        v24 = (_QWORD *)*v24;
        v22 = v48;
      }
      v25 = 0;
LABEL_27:
      *((_BYTE *)v17 + 52) = v25;
    }
    if ( (v38 & 0x2000) != 0 )
      ArraySize = TdhpGetArraySize(v36);
    else
      ArraySize = 1;
    *((_WORD *)v17 + 25) = ArraySize;
    HasEventMap = TdhpHasEventMap(v38, v36);
    *((_BYTE *)v17 + 44) = HasEventMap;
    if ( HasEventMap )
    {
      ClassName = TdhpGetClassName(v49, a1, v17 + 5);
      utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::operator=(v17 + 4, ClassName);
      utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(v49);
      if ( *((_DWORD *)v17 + 10) == 2 )
      {
        tlx::unique_variant::reset((tlx::unique_variant *)&v46);
LABEL_42:
        std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(&v36);
LABEL_43:
        v9 = v37;
        goto LABEL_44;
      }
    }
    if ( (unsigned __int8)TdhpGetActivityIDOrRelatedActivityID(*((unsigned __int16 *)v17 + 23), v36, 1) )
    {
      v44 = v16;
    }
    else
    {
      ActivityIDOrRelatedActivityID = TdhpGetActivityIDOrRelatedActivityID(*((unsigned __int16 *)v17 + 23), v36, 0);
      v30 = v37;
      if ( ActivityIDOrRelatedActivityID )
        v30 = v16;
      v37 = v30;
    }
    v31 = v36;
    pv = 0;
    v41 = 0;
    v32 = *(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, __int128 *, _QWORD))(*(_QWORD *)v36 + 24LL);
    tlx::unique_variant::reset((tlx::unique_variant *)&pv);
    LODWORD(v32) = v32(v31, L"XMLFragment", 0, &pv, 0);
    tlx::unique_variant::reset((tlx::unique_variant *)&pv);
    *((_BYTE *)v17 + 45) = (_DWORD)v32 == 0;
    v33 = SysStringByteLen(bstr) + 2;
    *((_DWORD *)v17 + 6) = v33;
    v11 += v33;
    if ( *((_BYTE *)v17 + 44) )
      v11 += v33 + *((_DWORD *)v17 + 10);
    ++v16;
    tlx::unique_variant::reset((tlx::unique_variant *)&v46);
    std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(&v36);
    v17 = (_QWORD *)*v17;
    v7 = a1;
  }
  v34 = 0;
  v9 = v37;
LABEL_45:
  if ( a4 )
    *a4 = v44;
  if ( a5 )
    *a5 = v9;
  if ( a3 )
    *a3 = v10;
  if ( a6 )
    *a6 = v11;
  __1__unique_ptr_UtagSAFEARRAY__U__generic_delete_UtagSAFEARRAY__U__generic_deallocate__MP6AJPEAUtagSAFEARRAY___Z1_SafeArrayDestroy__YAJ0_ZPEAU1__tlx___tlx___utl__QEAA_XZ(&psa);
  return v34;
}

```

## disassembly

```asm
0x180029f04  mov     rax, rsp
0x180029f07  mov     [rax+10h], rbx
0x180029f0b  mov     [rax+20h], r9
0x180029f0f  mov     [rax+18h], r8
0x180029f13  mov     [rax+8], rcx
0x180029f17  push    rbp
0x180029f18  push    rsi
0x180029f19  push    rdi
0x180029f1a  push    r12
0x180029f1c  push    r13
0x180029f1e  push    r14
0x180029f20  push    r15
0x180029f22  lea     rbp, [rax-4Fh]
0x180029f26  sub     rsp, 0D0h
0x180029f2d  mov     r15, rdx
0x180029f30  mov     rsi, rcx
0x180029f33  xor     edx, edx
0x180029f35  mov     [rbp+47h+plLbound], edx
0x180029f38  mov     [rbp+47h+plUbound], edx
0x180029f3b  mov     ecx, edx; psa
0x180029f3d  mov     [rbp+47h+var_B4], edx
0x180029f40  or      r12d, 0FFFFFFFFh
0x180029f44  mov     [rbp+47h+var_B8], r12d
0x180029f48  mov     [rbp+47h+var_84], r12d
0x180029f4c  mov     r13d, edx
0x180029f4f  mov     r14d, edx
0x180029f52  lea     r8d, [rdx+1]
0x180029f56  mov     edi, r8d
0x180029f59  xorps   xmm0, xmm0
0x180029f5c  xor     eax, eax
0x180029f5e  movups  [rbp+47h+pv], xmm0
0x180029f62  mov     dword ptr [rbp+47h+pv+8], r8d
0x180029f66  lea     r8d, [rdx+3]
0x180029f6a  mov     word ptr [rbp+47h+pv], r8w
0x180029f6f  movups  xmm0, [rbp+47h+pv]
0x180029f73  movups  [rbp+47h+var_50], xmm0
0x180029f77  mov     [rbp+47h+var_40], rax
0x180029f7b  mov     rax, [rsi]
0x180029f7e  mov     rbx, [rax+38h]
0x180029f82  mov     qword ptr [rbp+47h+pv], rdx
0x180029f86  lea     rax, [rbp+47h+psa]
0x180029f8a  mov     qword ptr [rbp+47h+pv+8], rax
0x180029f8e  mov     [rbp+47h+psa], rdx
0x180029f92  test    rcx, rcx
0x180029f95  jz      short loc_180029FA3
0x180029f97  call    cs:__imp_SafeArrayDestroy
0x180029f9d  mov     r8d, 3
0x180029fa3  lea     rax, [rbp+47h+pv]
0x180029fa7  mov     [rsp+100h+var_E0], rax
0x180029fac  lea     r9, [rbp+47h+var_50]
0x180029fb0  lea     rdx, aWmidataid; "WmiDataId"
0x180029fb7  mov     rcx, rsi
0x180029fba  mov     rax, rbx
0x180029fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029fc2  mov     ebx, eax
0x180029fc4  lea     rcx, [rbp+47h+pv]
0x180029fc8  call    ??1?$out_ptr_t@V?$unique_ptr@UtagSAFEARRAY@@U?$generic_delete@UtagSAFEARRAY@@U?$generic_deallocate@$MP6AJPEAUtagSAFEARRAY@@@Z1?SafeArrayDestroy@@YAJ0@ZPEAU1@@tlx@@@tlx@@@utl@@PEAUtagSAFEARRAY@@$$V@utl@@QEAA@XZ
0x180029fcd  test    ebx, ebx
0x180029fcf  mov     ebx, 1
0x180029fd4  jnz     loc_18002A0BB
0x180029fda  lea     r8, [rbp+47h+plLbound]; plLbound
0x180029fde  mov     edx, ebx; nDim
0x180029fe0  mov     rcx, [rbp+47h+psa]; psa
0x180029fe4  call    cs:__imp_SafeArrayGetLBound
0x180029fea  test    eax, eax
0x180029fec  js      loc_18002A355
0x180029ff2  lea     r8, [rbp+47h+plUbound]; plUbound
0x180029ff6  mov     edx, ebx; nDim
0x180029ff8  mov     rcx, [rbp+47h+psa]; psa
0x180029ffc  call    cs:__imp_SafeArrayGetUBound
0x18002a002  test    eax, eax
0x18002a004  js      loc_18002A355
0x18002a00a  mov     eax, [rbp+47h+plUbound]
0x18002a00d  test    eax, eax
0x18002a00f  js      loc_18002A0BB
0x18002a015  cmp     [rbp+47h+plLbound], eax
0x18002a018  jnz     loc_18002A355
0x18002a01e  mov     qword ptr [rbp+47h+pv], 0
0x18002a026  lea     rax, [rbp+47h+var_C0]
0x18002a02a  mov     qword ptr [rbp+47h+pv+8], rax
0x18002a02e  mov     [rbp+47h+var_C0], 0
0x18002a036  lea     r8, [rbp+47h+pv]; pv
0x18002a03a  lea     rdx, [rbp+47h+plLbound]; rgIndices
0x18002a03e  mov     rcx, [rbp+47h+psa]; psa
0x18002a042  call    cs:__imp_SafeArrayGetElement
0x18002a048  mov     ebx, eax
0x18002a04a  lea     rcx, [rbp+47h+pv]
0x18002a04e  call    ??1?$out_ptr_t@V?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@PEA_W$$V@utl@@QEAA@XZ; utl::out_ptr_t<utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>,wchar_t *,>::~out_ptr_t<utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>,wchar_t *,>(void)
0x18002a053  test    ebx, ebx
0x18002a055  js      short loc_18002A0AD
0x18002a057  mov     rcx, r15
0x18002a05a  call    ??$emplace_back@$$V$0A@@?$list@UBSTR_INFO@@V?$allocator@UBSTR_INFO@@@utl@@@utl@@QEAA_NXZ; utl::list<BSTR_INFO,utl::allocator<BSTR_INFO>>::emplace_back<,0>(void)
0x18002a05f  test    al, al
0x18002a061  jz      short loc_18002A0AD
0x18002a063  mov     rcx, [r15+8]
0x18002a067  add     rcx, 10h
0x18002a06b  lea     rdx, [rbp+47h+var_C0]
0x18002a06f  call    ??4?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::operator=(utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete> &&)
0x18002a074  inc     edi
0x18002a076  xorps   xmm0, xmm0
0x18002a079  xor     eax, eax
0x18002a07b  movups  [rbp+47h+pv], xmm0
0x18002a07f  mov     dword ptr [rbp+47h+pv+8], edi
0x18002a082  lea     ecx, [rax+3]
0x18002a085  mov     word ptr [rbp+47h+pv], cx
0x18002a089  movups  xmm0, [rbp+47h+pv]
0x18002a08d  movups  [rbp+47h+var_50], xmm0
0x18002a091  mov     [rbp+47h+var_40], rax
0x18002a095  lea     rcx, [rbp+47h+var_C0]
0x18002a099  call    ??1?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(void)
0x18002a09e  mov     rcx, [rbp+47h+psa]
0x18002a0a2  xor     edx, edx
0x18002a0a4  lea     r8d, [rdx+3]
0x18002a0a8  jmp     loc_180029F7B
0x18002a0ad  lea     rcx, [rbp+47h+var_C0]
0x18002a0b1  call    ??1?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(void)
0x18002a0b6  jmp     loc_18002A355
0x18002a0bb  lea     r13d, [rdi-1]
0x18002a0bf  cmp     r13d, ebx
0x18002a0c2  jbe     short loc_18002A0D7
0x18002a0c4  lea     eax, ds:0[r13*2]
0x18002a0cc  add     eax, r13d
0x18002a0cf  lea     r14d, ds:0FFFFFFFFFFFFFFE8h[rax*8]
0x18002a0d7  xor     r12d, r12d
0x18002a0da  mov     rbx, [r15]
0x18002a0dd  cmp     rbx, r15
0x18002a0e0  jz      loc_18002A3B2
0x18002a0e6  mov     rcx, [rbx+10h]
0x18002a0ea  mov     [rbp+47h+bstr], rcx
0x18002a0ee  mov     rax, [rsi]
0x18002a0f1  mov     qword ptr [rsp+28h], 0
0x18002a0fa  lea     rdx, [rbp+47h+var_B4]
0x18002a0fe  mov     [rsp+100h+var_E0], rdx
0x18002a103  xor     r9d, r9d
0x18002a106  xor     r8d, r8d
0x18002a109  mov     rdx, rcx
0x18002a10c  mov     rcx, rsi
0x18002a10f  mov     rax, [rax+20h]
0x18002a113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a118  test    eax, eax
0x18002a11a  js      loc_18002A351
0x18002a120  mov     [rbp+47h+var_C0], 0
0x18002a128  mov     rax, [rsi]
0x18002a12b  mov     rdi, [rax+58h]
0x18002a12f  lea     rdx, [rbp+47h+var_C0]
0x18002a133  lea     rcx, [rbp+47h+pv]
0x18002a137  call    ??$out_ptr@XV?$unique_ptr@UIWbemQualifierSet@@Urelease_delete@tlx@@@utl@@$$V@utl@@YA?A_PAEAV?$unique_ptr@UIWbemQualifierSet@@Urelease_delete@tlx@@@0@@Z
0x18002a13c  nop
0x18002a13d  mov     r8, rax
0x18002a140  mov     rdx, [rbp+47h+bstr]
0x18002a144  mov     rcx, rsi
0x18002a147  mov     rax, rdi
0x18002a14a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a14f  mov     edi, eax
0x18002a151  lea     rcx, [rbp+47h+pv]
0x18002a155  call    ??1?$out_ptr_t@V?$unique_ptr@UIWbemQualifierSet@@Urelease_delete@tlx@@@utl@@PEAUIWbemQualifierSet@@$$V@utl@@QEAA@XZ; utl::out_ptr_t<utl::unique_ptr<IWbemQualifierSet,tlx::release_delete>,IWbemQualifierSet *,>::~out_ptr_t<utl::unique_ptr<IWbemQualifierSet,tlx::release_delete>,IWbemQualifierSet *,>(void)
0x18002a15a  test    edi, edi
0x18002a15c  js      loc_18002A348
0x18002a162  lea     r8, [rbx+2Eh]
0x18002a166  lea     r9, [rbx+30h]
0x18002a16a  mov     rdx, [rbp+47h+var_C0]
0x18002a16e  mov     ecx, [rbp+47h+var_B4]
0x18002a171  call    TdhpGetTypeFromWBEM
0x18002a176  xorps   xmm0, xmm0
0x18002a179  xor     eax, eax
0x18002a17b  movups  [rbp+47h+var_78], xmm0
0x18002a17f  mov     [rbp+47h+var_68], rax
0x18002a183  mov     rsi, [rbp+47h+var_C0]
0x18002a187  mov     rax, [rsi]
0x18002a18a  mov     rdi, [rax+18h]
0x18002a18e  lea     rcx, [rbp+47h+var_78]; this
0x18002a192  call    ?reset@unique_variant@tlx@@QEAAXXZ; tlx::unique_variant::reset(void)
0x18002a197  mov     [rsp+100h+var_E0], 0
0x18002a1a0  lea     r9, [rbp+47h+var_78]
0x18002a1a4  xor     r8d, r8d
0x18002a1a7  lea     rdx, aWmisizeis; "WmiSizeIs"
0x18002a1ae  mov     rcx, rsi
0x18002a1b1  mov     rax, rdi
0x18002a1b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1b9  mov     ecx, 1
0x18002a1be  test    eax, eax
0x18002a1c0  js      short loc_18002A20A
0x18002a1c2  cmp     word ptr [rbp+47h+var_78], 8
0x18002a1c7  jnz     short loc_18002A20A
0x18002a1c9  mov     rax, qword ptr [rbp+47h+var_78+8]
0x18002a1cd  mov     [rbp+47h+var_60], rax
0x18002a1d1  xor     esi, esi
0x18002a1d3  mov     rdi, [r15]
0x18002a1d6  cmp     rdi, r15
0x18002a1d9  jz      short loc_18002A205
0x18002a1db  mov     rdx, rax
0x18002a1de  mov     rcx, [rdi+10h]
0x18002a1e2  call    cs:__imp__o__wcsicmp
0x18002a1e8  mov     ecx, 1
0x18002a1ed  test    eax, eax
0x18002a1ef  jz      short loc_18002A1FD
0x18002a1f1  add     si, cx
0x18002a1f4  mov     rdi, [rdi]
0x18002a1f7  mov     rax, [rbp+47h+var_60]
0x18002a1fb  jmp     short loc_18002A1D6
0x18002a1fd  mov     [rbx+36h], si
0x18002a201  mov     al, cl
0x18002a203  jmp     short loc_18002A207
0x18002a205  xor     al, al
0x18002a207  mov     [rbx+34h], al
0x18002a20a  test    [rbp+47h+var_B4], 2000h
0x18002a211  jz      short loc_18002A21E
0x18002a213  mov     rcx, [rbp+47h+var_C0]
0x18002a217  call    TdhpGetArraySize
0x18002a21c  jmp     short loc_18002A220
0x18002a21e  mov     eax, ecx
0x18002a220  mov     [rbx+32h], ax
0x18002a224  mov     rdx, [rbp+47h+var_C0]
0x18002a228  mov     ecx, [rbp+47h+var_B4]
0x18002a22b  call    TdhpHasEventMap
0x18002a230  mov     [rbx+2Ch], al
0x18002a233  test    al, al
0x18002a235  jz      short loc_18002A267
0x18002a237  lea     r8, [rbx+28h]
0x18002a23b  mov     rdx, [rbp+47h+arg_0]
0x18002a23f  lea     rcx, [rbp+47h+var_58]
0x18002a243  call    TdhpGetClassName
0x18002a248  lea     rcx, [rbx+20h]
0x18002a24c  mov     rdx, rax
0x18002a24f  call    ??4?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::operator=(utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete> &&)
0x18002a254  lea     rcx, [rbp+47h+var_58]
0x18002a258  call    ??1?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(void)
0x18002a25d  cmp     dword ptr [rbx+28h], 2
0x18002a261  jz      loc_18002A33E
0x18002a267  movzx   ecx, word ptr [rbx+2Eh]
0x18002a26b  mov     r8d, 1
0x18002a271  mov     rdx, [rbp+47h+var_C0]
0x18002a275  call    TdhpGetActivityIDOrRelatedActivityID
0x18002a27a  test    al, al
0x18002a27c  jz      short loc_18002A284
0x18002a27e  mov     [rbp+47h+var_84], r12d
0x18002a282  jmp     short loc_18002A2A0
0x18002a284  movzx   ecx, word ptr [rbx+2Eh]
0x18002a288  xor     r8d, r8d
0x18002a28b  mov     rdx, [rbp+47h+var_C0]
0x18002a28f  call    TdhpGetActivityIDOrRelatedActivityID
0x18002a294  mov     ecx, [rbp+47h+var_B8]
0x18002a297  test    al, al
0x18002a299  cmovnz  ecx, r12d
0x18002a29d  mov     [rbp+47h+var_B8], ecx
0x18002a2a0  mov     rsi, [rbp+47h+var_C0]
0x18002a2a4  xorps   xmm0, xmm0
0x18002a2a7  xor     eax, eax
0x18002a2a9  movups  [rbp+47h+pv], xmm0
0x18002a2ad  mov     [rbp+47h+var_98], rax
0x18002a2b1  mov     rax, [rsi]
0x18002a2b4  mov     rdi, [rax+18h]
0x18002a2b8  lea     rcx, [rbp+47h+pv]; this
0x18002a2bc  call    ?reset@unique_variant@tlx@@QEAAXXZ; tlx::unique_variant::reset(void)
0x18002a2c1  mov     [rsp+100h+var_E0], 0
0x18002a2ca  lea     r9, [rbp+47h+pv]
0x18002a2ce  xor     r8d, r8d
0x18002a2d1  lea     rdx, aXmlfragment; "XMLFragment"
0x18002a2d8  mov     rcx, rsi
0x18002a2db  mov     rax, rdi
0x18002a2de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a2e3  mov     edi, eax
0x18002a2e5  lea     rcx, [rbp+47h+pv]; this
0x18002a2e9  call    ?reset@unique_variant@tlx@@QEAAXXZ; tlx::unique_variant::reset(void)
0x18002a2ee  test    edi, edi
0x18002a2f0  setz    al
0x18002a2f3  mov     [rbx+2Dh], al
0x18002a2f6  mov     rcx, [rbp+47h+bstr]; bstr
0x18002a2fa  call    cs:__imp_SysStringByteLen
0x18002a300  add     eax, 2
0x18002a303  mov     [rbx+18h], eax
0x18002a306  add     r14d, eax
0x18002a309  mov     ecx, r14d
0x18002a30c  cmp     byte ptr [rbx+2Ch], 0
0x18002a310  jz      short loc_18002A31C
0x18002a312  mov     r14d, [rbx+28h]
0x18002a316  add     r14d, ecx
0x18002a319  add     r14d, eax
0x18002a31c  inc     r12d
0x18002a31f  lea     rcx, [rbp+47h+var_78]; this
0x18002a323  call    ?reset@unique_variant@tlx@@QEAAXXZ; tlx::unique_variant::reset(void)
0x18002a328  nop
0x18002a329  lea     rcx, [rbp+47h+var_C0]
0x18002a32d  call    ??1?$unique_ptr@UIUnknown@@UReleaseDelete@XmlReader@@@std@@QEAA@XZ; std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(void)
0x18002a332  mov     rbx, [rbx]
0x18002a335  mov     rsi, [rbp+47h+arg_0]
0x18002a339  jmp     loc_18002A0DD
0x18002a33e  lea     rcx, [rbp+47h+var_78]; this
0x18002a342  call    ?reset@unique_variant@tlx@@QEAAXXZ; tlx::unique_variant::reset(void)
0x18002a347  nop
0x18002a348  lea     rcx, [rbp+47h+var_C0]
0x18002a34c  call    ??1?$unique_ptr@UIUnknown@@UReleaseDelete@XmlReader@@@std@@QEAA@XZ; std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(void)
0x18002a351  mov     r12d, [rbp+47h+var_B8]
0x18002a355  mov     ebx, 1072h
0x18002a35a  mov     rax, [rbp+47h+arg_18]
0x18002a35e  test    rax, rax
0x18002a361  jz      short loc_18002A368
0x18002a363  mov     ecx, [rbp+47h+var_84]
0x18002a366  mov     [rax], ecx
0x18002a368  mov     rax, [rbp+47h+arg_20]
  ... truncated ...
```
