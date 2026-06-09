# CUpdate::EvaluateExtendedDynamicProperty(wchar_t *,tagVARIANT *)

- ea: `0x18004f8c0`
- end: `0x18004fcba`
- name: `?EvaluateExtendedDynamicProperty@CUpdate@@UEAAJPEA_WPEAUtagVARIANT@@@Z`
- size: `1018`
- prototype: `int(CUpdate *__hidden this, wchar_t *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006ac4`
- `0x1800459a4`
- `0x18004f8c0`
- `0x180099990`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004f977`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004f977`
- `OLEAUT32!__imp_SysAllocString` at `0x18004f98d`
- `OLEAUT32!__imp_SysAllocString` at `0x18004f98d`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fc04`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fc5d`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fc04`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fc5d`
- `OLEAUT32!__imp_SysStringLen` at `0x18004f90e`
- `OLEAUT32!__imp_SysStringLen` at `0x18004f90e`
- `OLEAUT32!__imp_VariantInit` at `0x18004f954`
- `OLEAUT32!__imp_VariantInit` at `0x18004f9ae`
- `OLEAUT32!__imp_VariantInit` at `0x18004fc0d`
- `OLEAUT32!__imp_VariantInit` at `0x18004f954`
- `OLEAUT32!__imp_VariantInit` at `0x18004f9ae`
- `OLEAUT32!__imp_VariantInit` at `0x18004fc0d`
- `OLEAUT32!__imp_VariantClear` at `0x18004fbfb`
- `OLEAUT32!__imp_VariantClear` at `0x18004fc54`
- `OLEAUT32!__imp_VariantClear` at `0x18004fc8b`
- `OLEAUT32!__imp_VariantClear` at `0x18004fbfb`
- `OLEAUT32!__imp_VariantClear` at `0x18004fc54`
- `OLEAUT32!__imp_VariantClear` at `0x18004fc8b`
- `OLEAUT32!__imp_VariantCopy` at `0x18004fc1a`
- `OLEAUT32!__imp_VariantCopy` at `0x18004fc1a`

## string_xrefs

- `0x18004f986`: `ContainsUpdateBootstrapper`
- `0x18004f95c`: `DoesUpdateRequireReboot`
- `0x18004fb8e`: `IsUpdateRebootless`
- `0x18004f929`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x18004fc41`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x18004fc79`: `C:\__w\1\s\src\Client\comapi\Update.cpp`

## pseudocode

```c
__int64 __fastcall CUpdate::EvaluateExtendedDynamicProperty(CUpdate *this, wchar_t *a2, struct tagVARIANT *a3)
{
  unsigned int v6; // edi
  unsigned int v8; // ebx
  __int64 v9; // rdx
  OLECHAR *v10; // r14
  int UpdateDownloadStatus; // ebx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int64 v26; // rax
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int64 v35; // rax
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  HRESULT v41; // eax
  unsigned __int64 v42; // r9
  int lpString2; // [rsp+20h] [rbp-E0h]
  int lpString2a; // [rsp+20h] [rbp-E0h]
  __int128 v45; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v46; // [rsp+50h] [rbp-B0h]
  __int128 v47; // [rsp+60h] [rbp-A0h]
  __int128 v48; // [rsp+70h] [rbp-90h]
  __int128 v49; // [rsp+80h] [rbp-80h]
  __int128 v50; // [rsp+90h] [rbp-70h]
  __int128 v51; // [rsp+A0h] [rbp-60h]
  __int128 v52; // [rsp+B0h] [rbp-50h]
  __int128 v53; // [rsp+C0h] [rbp-40h]
  __int128 v54; // [rsp+D0h] [rbp-30h]
  __int128 v55; // [rsp+E0h] [rbp-20h]
  __int128 v56; // [rsp+F0h] [rbp-10h]
  __int128 v57; // [rsp+100h] [rbp+0h]
  __int128 v58; // [rsp+110h] [rbp+10h]
  __int64 v59; // [rsp+120h] [rbp+20h]
  int v60; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v61; // [rsp+138h] [rbp+38h]
  VARIANTARG v62; // [rsp+140h] [rbp+40h] BYREF
  VARIANTARG pvarg; // [rsp+158h] [rbp+58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v6 = 0;
  if ( (int)WUSystemInterfaceHelper::IsCapabilitySupported(this, (unsigned int)a2) < 0 )
    return 2149842999LL;
  if ( !SysStringLen(a2) )
  {
    v8 = -2147024809;
    v9 = 1563;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
      (const char *)v8,
      lpString2);
    return v8;
  }
  if ( !a3 )
  {
    v8 = -2147467261;
    v9 = 1564;
    goto LABEL_5;
  }
  VariantInit(&pvarg);
  if ( CompareStringW(0x7Fu, 0, a2, -1, L"DoesUpdateRequireReboot", -1) != 2 )
  {
    UpdateDownloadStatus = -2147024809;
    v12 = 1616;
    goto LABEL_33;
  }
  v10 = SysAllocString(L"ContainsUpdateBootstrapper");
  if ( !v10 )
  {
    UpdateDownloadStatus = -2147024882;
    v12 = 1573;
LABEL_33:
    v42 = (unsigned int)UpdateDownloadStatus;
    goto LABEL_34;
  }
  VariantInit(&v62);
  UpdateDownloadStatus = (*(__int64 (__fastcall **)(CUpdate *, OLECHAR *, VARIANTARG *))(*(_QWORD *)this + 480LL))(
                           this,
                           v10,
                           &v62);
  if ( UpdateDownloadStatus < 0 )
  {
    v13 = 1577;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
      (const char *)(unsigned int)UpdateDownloadStatus,
      lpString2a);
    VariantClear(&v62);
    SysFreeString(v10);
LABEL_35:
    v6 = UpdateDownloadStatus;
    goto LABEL_36;
  }
  if ( v62.vt != 11 || !v62.iVal )
  {
    UpdateDownloadStatus = -2145124297;
    v13 = 1580;
    goto LABEL_31;
  }
  v60 = 0;
  v14 = *((_OWORD *)this + 43);
  v45 = *((_OWORD *)this + 42);
  v15 = *((_OWORD *)this + 44);
  v46 = v14;
  v16 = *((_OWORD *)this + 45);
  v47 = v15;
  v17 = *((_OWORD *)this + 46);
  v48 = v16;
  v18 = *((_OWORD *)this + 47);
  v49 = v17;
  v19 = *((_OWORD *)this + 48);
  v50 = v18;
  v20 = *((_OWORD *)this + 50);
  v51 = v19;
  v52 = *((_OWORD *)this + 49);
  v21 = *((_OWORD *)this + 51);
  v53 = v20;
  v22 = *((_OWORD *)this + 52);
  v54 = v21;
  v23 = *((_OWORD *)this + 53);
  v55 = v22;
  v24 = *((_OWORD *)this + 54);
  v56 = v23;
  v25 = *((_OWORD *)this + 55);
  v26 = *((_QWORD *)this + 112);
  v57 = v24;
  v58 = v25;
  v59 = v26;
  UpdateDownloadStatus = CSusInternalWrapper::GetUpdateDownloadStatus((char *)this + 56, &v45, 1, &v60);
  if ( UpdateDownloadStatus < 0 )
  {
    v13 = 1586;
    goto LABEL_31;
  }
  if ( v60 != 5 )
  {
    v27 = *((_OWORD *)this + 43);
    v45 = *((_OWORD *)this + 42);
    v28 = *((_OWORD *)this + 44);
    v46 = v27;
    v29 = *((_OWORD *)this + 45);
    v47 = v28;
    v30 = *((_OWORD *)this + 46);
    v48 = v29;
    v31 = *((_OWORD *)this + 47);
    v49 = v30;
    v32 = *((_OWORD *)this + 48);
    v50 = v31;
    v33 = *((_OWORD *)this + 49);
    v51 = v32;
    v34 = *((_OWORD *)this + 50);
    v35 = *((_QWORD *)this + 112);
    v52 = v33;
    v36 = *((_OWORD *)this + 51);
    v53 = v34;
    v37 = *((_OWORD *)this + 52);
    v54 = v36;
    v38 = *((_OWORD *)this + 53);
    v55 = v37;
    v39 = *((_OWORD *)this + 54);
    v56 = v38;
    v40 = *((_OWORD *)this + 55);
    v57 = v39;
    v58 = v40;
    v59 = v35;
    UpdateDownloadStatus = CSusInternalWrapper::GetUpdateDownloadStatus((char *)this + 56, &v45, 0, &v60);
    if ( UpdateDownloadStatus < 0 )
    {
      v13 = 1591;
      goto LABEL_31;
    }
    if ( v60 != 1 )
    {
      UpdateDownloadStatus = -2145099769;
      v13 = 1593;
      goto LABEL_31;
    }
  }
  v61 = 0;
  lpString2a = 1;
  UpdateDownloadStatus = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD, const wchar_t *))(*((_QWORD *)this + 3)
                                                                                            + 112LL))(
                           (char *)this + 24,
                           0,
                           0,
                           L"IsUpdateRebootless");
  if ( UpdateDownloadStatus < 0 )
  {
    v13 = 1602;
    goto LABEL_31;
  }
  if ( v61 > 2 )
  {
    UpdateDownloadStatus = -2145120257;
    v13 = 1609;
    goto LABEL_31;
  }
  if ( !v61 )
  {
    UpdateDownloadStatus = -2145124248;
    v13 = 1610;
    goto LABEL_31;
  }
  pvarg.vt = 11;
  pvarg.iVal = (v61 != 2) - 1;
  VariantClear(&v62);
  SysFreeString(v10);
  VariantInit(a3);
  v41 = VariantCopy(a3, &pvarg);
  UpdateDownloadStatus = v41;
  if ( v41 < 0 )
  {
    v42 = (unsigned int)v41;
    v12 = 1620;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
      (const char *)v42,
      lpString2a);
    goto LABEL_35;
  }
LABEL_36:
  VariantClear(&pvarg);
  return v6;
}

```

## disassembly

```asm
0x18004f8c0  mov     [rsp-8+arg_18], rbx
0x18004f8c5  push    rbp
0x18004f8c6  push    rsi
0x18004f8c7  push    rdi
0x18004f8c8  push    r12
0x18004f8ca  push    r13
0x18004f8cc  push    r14
0x18004f8ce  push    r15
0x18004f8d0  lea     rbp, [rsp-80h]
0x18004f8d5  sub     rsp, 180h
0x18004f8dc  mov     rax, cs:__security_cookie
0x18004f8e3  xor     rax, rsp
0x18004f8e6  mov     [rbp+0B0h+var_40], rax
0x18004f8ea  mov     r12, r8
0x18004f8ed  mov     rbx, rdx
0x18004f8f0  mov     r15, rcx
0x18004f8f3  call    ?IsCapabilitySupported@WUSystemInterfaceHelper@@YAJK@Z; WUSystemInterfaceHelper::IsCapabilitySupported(ulong)
0x18004f8f8  shr     eax, 1Fh
0x18004f8fb  xor     edi, edi
0x18004f8fd  test    al, al
0x18004f8ff  jz      short loc_18004F90B
0x18004f901  mov     eax, 80240037h
0x18004f906  jmp     loc_18004FC93
0x18004f90b  mov     rcx, rbx; pbstr
0x18004f90e  call    cs:__imp_SysStringLen
0x18004f914  test    eax, eax
0x18004f916  jnz     short loc_18004F93F
0x18004f918  mov     ebx, 80070057h
0x18004f91d  mov     edx, 61Bh; void *
0x18004f922  mov     rcx, [rbp+0B8h]; this
0x18004f929  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18004f930  mov     r9d, ebx; char *
0x18004f933  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f938  mov     eax, ebx
0x18004f93a  jmp     loc_18004FC93
0x18004f93f  test    r12, r12
0x18004f942  jnz     short loc_18004F950
0x18004f944  mov     ebx, 80004003h
0x18004f949  mov     edx, 61Ch
0x18004f94e  jmp     short loc_18004F922
0x18004f950  lea     rcx, [rbp+0B0h+pvarg]; pvarg
0x18004f954  call    cs:__imp_VariantInit
0x18004f95a  xor     edx, edx; dwCmpFlags
0x18004f95c  lea     rax, aDoesupdaterequ; "DoesUpdateRequireReboot"
0x18004f963  or      r9d, 0FFFFFFFFh; cchCount1
0x18004f967  mov     r8, rbx; lpString1
0x18004f96a  mov     [rsp+1B0h+cchCount2], r9d; cchCount2
0x18004f96f  mov     [rsp+1B0h+lpString2], rax; int
0x18004f974  lea     ecx, [rdx+7Fh]; Locale
0x18004f977  call    cs:__imp_CompareStringW
0x18004f97d  cmp     eax, 2
0x18004f980  jnz     loc_18004FC65
0x18004f986  lea     rcx, psz; "ContainsUpdateBootstrapper"
0x18004f98d  call    cs:__imp_SysAllocString
0x18004f993  mov     r14, rax
0x18004f996  test    rax, rax
0x18004f999  jnz     short loc_18004F9AA
0x18004f99b  mov     ebx, 8007000Eh
0x18004f9a0  mov     edx, 625h
0x18004f9a5  jmp     loc_18004FC6F
0x18004f9aa  lea     rcx, [rbp+0B0h+var_70]; pvarg
0x18004f9ae  call    cs:__imp_VariantInit
0x18004f9b4  mov     rax, [r15]
0x18004f9b7  lea     r8, [rbp+0B0h+var_70]
0x18004f9bb  mov     rdx, r14
0x18004f9be  mov     rcx, r15
0x18004f9c1  mov     rax, [rax+1E0h]
0x18004f9c8  call    _guard_dispatch_icall
0x18004f9cd  mov     ebx, eax
0x18004f9cf  test    eax, eax
0x18004f9d1  jns     short loc_18004F9DD
0x18004f9d3  mov     edx, 629h
0x18004f9d8  jmp     loc_18004FC3A
0x18004f9dd  mov     eax, 0Bh
0x18004f9e2  cmp     ax, word ptr [rbp+0B0h+var_70]
0x18004f9e6  jnz     loc_18004FC30
0x18004f9ec  cmp     di, word ptr [rbp+0B0h+var_70+8]
0x18004f9f0  jz      loc_18004FC30
0x18004f9f6  lea     rsi, [r15+2A0h]
0x18004f9fd  mov     [rbp+0B0h+var_80], edi
0x18004fa00  movups  xmm0, xmmword ptr [rsi]
0x18004fa03  lea     rcx, [rsp+1B0h+var_170]
0x18004fa08  movups  xmm1, xmmword ptr [rsi+10h]
0x18004fa0c  lea     edx, [rax+75h]
0x18004fa0f  movups  xmmword ptr [rcx], xmm0
0x18004fa12  lea     rax, [rdx+rsi]
0x18004fa16  movups  xmm0, xmmword ptr [rsi+20h]
0x18004fa1a  lea     r8d, [rdx-7Fh]
0x18004fa1e  movups  xmmword ptr [rcx+10h], xmm1
0x18004fa22  lea     r9, [rbp+0B0h+var_80]
0x18004fa26  movups  xmm1, xmmword ptr [rsi+30h]
0x18004fa2a  movups  xmmword ptr [rcx+20h], xmm0
0x18004fa2e  movups  xmm0, xmmword ptr [rsi+40h]
0x18004fa32  movups  xmmword ptr [rcx+30h], xmm1
0x18004fa36  movups  xmm1, xmmword ptr [rsi+50h]
0x18004fa3a  movups  xmmword ptr [rcx+40h], xmm0
0x18004fa3e  movups  xmm0, xmmword ptr [rsi+60h]
0x18004fa42  movups  xmmword ptr [rcx+50h], xmm1
0x18004fa46  movups  xmm1, xmmword ptr [rax]
0x18004fa49  movups  xmmword ptr [rcx+60h], xmm0
0x18004fa4d  add     rcx, rdx
0x18004fa50  lea     rdx, [rsp+1B0h+var_170]
0x18004fa55  movups  xmm0, xmmword ptr [rsi+70h]
0x18004fa59  movups  xmmword ptr [rcx-10h], xmm0
0x18004fa5d  movups  xmm0, xmmword ptr [rax+10h]
0x18004fa61  movups  xmmword ptr [rcx], xmm1
0x18004fa64  movups  xmm1, xmmword ptr [rax+20h]
0x18004fa68  movups  xmmword ptr [rcx+10h], xmm0
0x18004fa6c  movups  xmm0, xmmword ptr [rax+30h]
0x18004fa70  movups  xmmword ptr [rcx+20h], xmm1
0x18004fa74  movups  xmm1, xmmword ptr [rax+40h]
0x18004fa78  movups  xmmword ptr [rcx+30h], xmm0
0x18004fa7c  movups  xmm0, xmmword ptr [rax+50h]
0x18004fa80  mov     rax, [rax+60h]
0x18004fa84  movups  xmmword ptr [rcx+40h], xmm1
0x18004fa88  movups  xmmword ptr [rcx+50h], xmm0
0x18004fa8c  mov     [rcx+60h], rax
0x18004fa90  lea     rcx, [r15+38h]
0x18004fa94  call    ?GetUpdateDownloadStatus@CSusInternalWrapper@@QEAAJUtagMatchingUpdate@@W4tagDownloadType@@PEAW4tagDSDownloadStatus@@@Z; CSusInternalWrapper::GetUpdateDownloadStatus(tagMatchingUpdate,tagDownloadType,tagDSDownloadStatus *)
0x18004fa99  mov     ebx, eax
0x18004fa9b  test    eax, eax
0x18004fa9d  jns     short loc_18004FAA9
0x18004fa9f  mov     edx, 632h
0x18004faa4  jmp     loc_18004FC3A
0x18004faa9  cmp     [rbp+0B0h+var_80], 5
0x18004faad  jz      loc_18004FB75
0x18004fab3  movups  xmm0, xmmword ptr [rsi]
0x18004fab6  lea     rdx, [rsp+1B0h+var_170]
0x18004fabb  mov     eax, 80h
0x18004fac0  movups  xmm1, xmmword ptr [rsi+10h]
0x18004fac4  lea     r9, [rbp+0B0h+var_80]
0x18004fac8  xor     r8d, r8d
0x18004facb  movups  xmmword ptr [rdx], xmm0
0x18004face  lea     rcx, [r15+38h]
0x18004fad2  movups  xmm0, xmmword ptr [rsi+20h]
0x18004fad6  movups  xmmword ptr [rdx+10h], xmm1
0x18004fada  movups  xmm1, xmmword ptr [rsi+30h]
0x18004fade  movups  xmmword ptr [rdx+20h], xmm0
0x18004fae2  movups  xmm0, xmmword ptr [rsi+40h]
0x18004fae6  movups  xmmword ptr [rdx+30h], xmm1
0x18004faea  movups  xmm1, xmmword ptr [rsi+50h]
0x18004faee  movups  xmmword ptr [rdx+40h], xmm0
0x18004faf2  movups  xmm0, xmmword ptr [rsi+60h]
0x18004faf6  movups  xmmword ptr [rdx+50h], xmm1
0x18004fafa  movups  xmm1, xmmword ptr [rsi+70h]
0x18004fafe  add     rsi, rax
0x18004fb01  movups  xmmword ptr [rdx+60h], xmm0
0x18004fb05  add     rdx, rax
0x18004fb08  movups  xmm0, xmmword ptr [rsi]
0x18004fb0b  mov     rax, [rsi+60h]
0x18004fb0f  movups  xmmword ptr [rdx-10h], xmm1
0x18004fb13  movups  xmm1, xmmword ptr [rsi+10h]
0x18004fb17  movups  xmmword ptr [rdx], xmm0
0x18004fb1a  movups  xmm0, xmmword ptr [rsi+20h]
0x18004fb1e  movups  xmmword ptr [rdx+10h], xmm1
0x18004fb22  movups  xmm1, xmmword ptr [rsi+30h]
0x18004fb26  movups  xmmword ptr [rdx+20h], xmm0
0x18004fb2a  movups  xmm0, xmmword ptr [rsi+40h]
0x18004fb2e  movups  xmmword ptr [rdx+30h], xmm1
0x18004fb32  movups  xmm1, xmmword ptr [rsi+50h]
0x18004fb36  movups  xmmword ptr [rdx+40h], xmm0
0x18004fb3a  movups  xmmword ptr [rdx+50h], xmm1
0x18004fb3e  mov     [rdx+60h], rax
0x18004fb42  lea     rdx, [rsp+1B0h+var_170]
0x18004fb47  call    ?GetUpdateDownloadStatus@CSusInternalWrapper@@QEAAJUtagMatchingUpdate@@W4tagDownloadType@@PEAW4tagDSDownloadStatus@@@Z; CSusInternalWrapper::GetUpdateDownloadStatus(tagMatchingUpdate,tagDownloadType,tagDSDownloadStatus *)
0x18004fb4c  mov     ebx, eax
0x18004fb4e  test    eax, eax
0x18004fb50  jns     short loc_18004FB5C
0x18004fb52  mov     edx, 637h
0x18004fb57  jmp     loc_18004FC3A
0x18004fb5c  mov     esi, 1
0x18004fb61  cmp     [rbp+0B0h+var_80], esi
0x18004fb64  jz      short loc_18004FB7A
0x18004fb66  mov     ebx, 80246007h
0x18004fb6b  mov     edx, 639h
0x18004fb70  jmp     loc_18004FC3A
0x18004fb75  mov     esi, 1
0x18004fb7a  lea     rdx, [rbp+0B0h+var_78]
0x18004fb7e  mov     [rbp+0B0h+var_78], rdi
0x18004fb82  mov     qword ptr [rsp+1B0h+cchCount2], rdx
0x18004fb87  lea     rcx, [r15+18h]
0x18004fb8b  mov     rax, [rcx]
0x18004fb8e  lea     r9, aIsupdatereboot; "IsUpdateRebootless"
0x18004fb95  xor     r8d, r8d
0x18004fb98  mov     dword ptr [rsp+1B0h+lpString2], esi
0x18004fb9c  xor     edx, edx
0x18004fb9e  mov     rax, [rax+70h]
0x18004fba2  call    _guard_dispatch_icall
0x18004fba7  mov     ebx, eax
0x18004fba9  test    eax, eax
0x18004fbab  jns     short loc_18004FBB7
0x18004fbad  mov     edx, 642h
0x18004fbb2  jmp     loc_18004FC3A
0x18004fbb7  mov     rcx, [rbp+0B0h+var_78]
0x18004fbbb  cmp     rcx, 2
0x18004fbbf  jbe     short loc_18004FBCD
0x18004fbc1  mov     ebx, 80240FFFh
0x18004fbc6  mov     edx, 649h
0x18004fbcb  jmp     short loc_18004FC3A
0x18004fbcd  test    rcx, rcx
0x18004fbd0  jnz     short loc_18004FBDE
0x18004fbd2  mov     ebx, 80240068h
0x18004fbd7  mov     edx, 64Ah
0x18004fbdc  jmp     short loc_18004FC3A
0x18004fbde  mov     eax, 0Bh
0x18004fbe3  cmp     rcx, 2
0x18004fbe7  mov     word ptr [rbp+0B0h+pvarg], ax
0x18004fbeb  lea     rcx, [rbp+0B0h+var_70]; pvarg
0x18004fbef  mov     eax, edi
0x18004fbf1  setnz   al
0x18004fbf4  sub     ax, si
0x18004fbf7  mov     word ptr [rbp+0B0h+pvarg+8], ax
0x18004fbfb  call    cs:__imp_VariantClear
0x18004fc01  mov     rcx, r14; bstrString
0x18004fc04  call    cs:__imp_SysFreeString
0x18004fc0a  mov     rcx, r12; pvarg
0x18004fc0d  call    cs:__imp_VariantInit
0x18004fc13  lea     rdx, [rbp+0B0h+pvarg]; pvargSrc
0x18004fc17  mov     rcx, r12; pvargDest
0x18004fc1a  call    cs:__imp_VariantCopy
0x18004fc20  mov     ebx, eax
0x18004fc22  test    eax, eax
0x18004fc24  jns     short loc_18004FC87
0x18004fc26  mov     r9d, eax
0x18004fc29  mov     edx, 654h
0x18004fc2e  jmp     short loc_18004FC72
0x18004fc30  mov     ebx, 80240037h
0x18004fc35  mov     edx, 62Ch; void *
0x18004fc3a  mov     rcx, [rbp+0B8h]; this
0x18004fc41  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18004fc48  mov     r9d, ebx; char *
0x18004fc4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fc50  lea     rcx, [rbp+0B0h+var_70]; pvarg
0x18004fc54  call    cs:__imp_VariantClear
0x18004fc5a  mov     rcx, r14; bstrString
0x18004fc5d  call    cs:__imp_SysFreeString
0x18004fc63  jmp     short loc_18004FC85
0x18004fc65  mov     ebx, 80070057h
0x18004fc6a  mov     edx, 650h; void *
0x18004fc6f  mov     r9d, ebx; char *
0x18004fc72  mov     rcx, [rbp+0B8h]; this
0x18004fc79  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18004fc80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fc85  mov     edi, ebx
0x18004fc87  lea     rcx, [rbp+0B0h+pvarg]; pvarg
0x18004fc8b  call    cs:__imp_VariantClear
0x18004fc91  mov     eax, edi
0x18004fc93  mov     rcx, [rbp+0B0h+var_40]
0x18004fc97  xor     rcx, rsp; StackCookie
0x18004fc9a  call    __security_check_cookie
0x18004fc9f  mov     rbx, [rsp+1B0h+arg_18]
0x18004fca7  add     rsp, 180h
0x18004fcae  pop     r15
0x18004fcb0  pop     r14
0x18004fcb2  pop     r13
0x18004fcb4  pop     r12
0x18004fcb6  pop     rdi
0x18004fcb7  pop     rsi
0x18004fcb8  pop     rbp
0x18004fcb9  retn
```
