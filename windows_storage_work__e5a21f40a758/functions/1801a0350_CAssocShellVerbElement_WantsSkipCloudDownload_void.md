# CAssocShellVerbElement::WantsSkipCloudDownload(void)

- ea: `0x1801a0350`
- end: `0x1801a0659`
- name: `?WantsSkipCloudDownload@CAssocShellVerbElement@@AEAAJXZ`
- size: `777`
- prototype: `__int64 __fastcall(CAssocShellVerbElement *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18021ffc0`

## callees

- `0x180015ee0`
- `0x180016f60`
- `0x1800371a8`
- `0x1800432f0`
- `0x1800d13a0`
- `0x1800dd190`
- `0x18019f8a4`
- `0x18019fa78`
- `0x18019fb80`
- `0x1801a0350`
- `0x1801a0660`
- `0x18030b638`
- `0x1803a4cb0`
- `0x1805a1e9c`
- `0x1805d9cec`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801a04cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801a04da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801a04cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801a04da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a043a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a044a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a0541`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a05dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a05ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a05fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a0614`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a0626`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a0636`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a043a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a044a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a0541`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a05dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a05ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a05fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a0614`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a0626`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a0636`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CAssocShellVerbElement::WantsSkipCloudDownload(CAssocShellVerbElement *this)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rcx
  int v5; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64, _QWORD, __int64); // rbx
  __int64 v8; // rax
  int v9; // ebx
  int v11; // eax
  unsigned int *v12; // r8
  int v13; // ebx
  int v14; // eax
  void *v15; // rcx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64); // rbx
  __int64 v18; // rax
  int v19; // eax
  unsigned __int16 *v20; // rdx
  unsigned __int16 *v21; // rcx
  __int64 v22; // rdx
  int v23; // [rsp+20h] [rbp-39h]
  bool v24; // [rsp+30h] [rbp-29h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-21h] BYREF
  LPVOID v26; // [rsp+40h] [rbp-19h] BYREF
  unsigned __int16 *v27; // [rsp+48h] [rbp-11h] BYREF
  __int128 v28; // [rsp+50h] [rbp-9h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+7h] BYREF
  int v30; // [rsp+68h] [rbp+Fh]
  HKEY v31; // [rsp+70h] [rbp+17h] BYREF
  int v32; // [rsp+78h] [rbp+1Fh]
  void *v33; // [rsp+80h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v26 = 0;
  v2 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v26);
  if ( (int)CAssocShellVerbElement::QueryString((char *)this + 8, 33619975, 0, v2) >= 0 )
  {
    hKey = 0;
    v30 = -1;
    v31 = 0;
    v32 = -1;
    v33 = 0;
    v5 = _AllocString<CTCoAllocPolicy>(v4, v3, v26, &v33);
    if ( v5 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xBCB,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\assocelem.cpp",
        (const char *)(unsigned int)v5,
        v23);
LABEL_4:
      CAppPathReader::~CAppPathReader((CAppPathReader *)&hKey);
      goto LABEL_5;
    }
    v11 = CAppPathReader::_EnsureHKCUPathKey(&hKey);
    if ( v11 < 0 )
    {
      v13 = 0;
      if ( v11 == -2147024894 )
      {
LABEL_15:
        v14 = v32;
        if ( v32 == -1 )
        {
          v14 = CAppPathReader::_PathToAppPathKeyHandle((CAppPathReader *)&hKey, HKEY_LOCAL_MACHINE, &v31);
          v32 = v14;
        }
        if ( v14 >= 0 )
          v13 = SHRegValueExists(v31, L"SkipCloudDownload", v12);
        if ( !v13 )
          goto LABEL_4;
LABEL_20:
        if ( hKey )
          RegCloseKey(hKey);
        if ( v31 )
          RegCloseKey(v31);
        v15 = v33;
LABEL_40:
        CoTaskMemFree(v15);
LABEL_41:
        if ( v26 )
          CoTaskMemFree(v26);
        return 0;
      }
    }
    else
    {
      v13 = SHRegValueExists(hKey, L"SkipCloudDownload", v12);
    }
    if ( v13 )
      goto LABEL_20;
    goto LABEL_15;
  }
LABEL_5:
  pv = 0;
  v6 = *((_QWORD *)this + 5);
  v7 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)(v6 + 8) + 24LL);
  v8 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
  v9 = v7(v6 + 8, 458756, 0, v8);
  if ( v9 < 0 )
  {
LABEL_6:
    if ( pv )
      CoTaskMemFree(pv);
    if ( v26 )
      CoTaskMemFree(v26);
    return (unsigned int)v9;
  }
  v27 = 0;
  v16 = *((_QWORD *)this + 5);
  v17 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)(v16 + 32) + 40LL);
  v18 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v27);
  v19 = v17(v16 + 32, v18);
  v9 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD9,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\assocelem.cpp",
      (const char *)(unsigned int)v19,
      v23);
    goto LABEL_27;
  }
  v20 = (unsigned __int16 *)pv;
  v21 = v27;
  if ( pv && (unsigned int)IsFileExtension(v27) )
  {
    v28 = 0;
    v9 = StateRepositoryFileTypeAssocReader::Init((StateRepositoryFileTypeAssocReader *)&v28, v20, v21);
    if ( v9 < 0 )
    {
      v22 = 3038;
LABEL_33:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\assocelem.cpp",
        (const char *)(unsigned int)v9,
        v23);
      StateRepositoryFileTypeAssocReader::~StateRepositoryFileTypeAssocReader((StateRepositoryFileTypeAssocReader *)&v28);
LABEL_27:
      if ( v27 )
        CoTaskMemFree(v27);
      goto LABEL_6;
    }
    v24 = 0;
    v9 = StateRepositoryFileTypeAssocReader::WantsSkipCloudDownload((StateRepositoryFileTypeAssocReader *)&v28, &v24);
    if ( v9 < 0 )
    {
      v22 = 3040;
      goto LABEL_33;
    }
    StateRepositoryFileTypeAssocReader::~StateRepositoryFileTypeAssocReader((StateRepositoryFileTypeAssocReader *)&v28);
    if ( v24 )
    {
      if ( v27 )
        CoTaskMemFree(v27);
      v15 = pv;
      if ( !pv )
        goto LABEL_41;
      goto LABEL_40;
    }
    v20 = (unsigned __int16 *)pv;
    v21 = v27;
  }
  if ( v21 )
  {
    CoTaskMemFree(v21);
    v20 = (unsigned __int16 *)pv;
  }
  if ( v20 )
    CoTaskMemFree(v20);
  if ( v26 )
    CoTaskMemFree(v26);
  return 2147943568LL;
}

```

## disassembly

```asm
0x1801a0350  push    rbp
0x1801a0352  push    rbx
0x1801a0353  push    rsi
0x1801a0354  push    rdi
0x1801a0355  lea     rbp, [rsp-3Fh]
0x1801a035a  sub     rsp, 98h
0x1801a0361  mov     rax, cs:__security_cookie
0x1801a0368  xor     rax, rsp
0x1801a036b  mov     [rbp+57h+var_28], rax
0x1801a036f  mov     rsi, rcx
0x1801a0372  mov     [rbp+57h+var_70], 0
0x1801a037a  lea     rcx, [rbp+57h+var_70]
0x1801a037e  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1801a0383  lea     rcx, [rsi+8]
0x1801a0387  mov     r9, rax
0x1801a038a  xor     r8d, r8d
0x1801a038d  mov     edx, 2010007h
0x1801a0392  call    ?QueryString@CAssocShellVerbElement@@UEAAJW4ASSOCQUERY@@PEBGPEAPEAG@Z; CAssocShellVerbElement::QueryString(ASSOCQUERY,ushort const *,ushort * *)
0x1801a0397  test    eax, eax
0x1801a0399  js      short loc_1801A03F3
0x1801a039b  mov     [rbp+57h+hKey], 0
0x1801a03a3  or      eax, 0FFFFFFFFh
0x1801a03a6  mov     [rbp+57h+var_48], eax
0x1801a03a9  mov     [rbp+57h+var_40], 0
0x1801a03b1  mov     [rbp+57h+var_38], eax
0x1801a03b4  mov     [rbp+57h+var_30], 0
0x1801a03bc  lea     r9, [rbp+57h+var_30]
0x1801a03c0  mov     r8, [rbp+57h+var_70]
0x1801a03c4  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1801a03c9  mov     rcx, [rbp+5Fh]; this
0x1801a03cd  test    eax, eax
0x1801a03cf  jns     loc_1801A0457
0x1801a03d5  mov     r9d, eax; char *
0x1801a03d8  lea     r8, aOnecoreuapShel_124; "onecoreuap\\shell\\windows.storage\\sha"...
0x1801a03df  mov     edx, 0BCBh; void *
0x1801a03e4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801a03e9  nop
0x1801a03ea  lea     rcx, [rbp+57h+hKey]; this
0x1801a03ee  call    ??1CAppPathReader@@QEAA@XZ; CAppPathReader::~CAppPathReader(void)
0x1801a03f3  mov     [rbp+57h+pv], 0
0x1801a03fb  mov     rdi, [rsi+28h]
0x1801a03ff  mov     rax, [rdi+8]
0x1801a0403  mov     rbx, [rax+18h]
0x1801a0407  lea     rcx, [rbp+57h+pv]
0x1801a040b  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1801a0410  mov     r9, rax
0x1801a0413  xor     r8d, r8d
0x1801a0416  mov     edx, 70004h
0x1801a041b  lea     rcx, [rdi+8]
0x1801a041f  mov     rax, rbx
0x1801a0422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a0427  mov     ebx, eax
0x1801a0429  test    eax, eax
0x1801a042b  jns     loc_1801A04E9
0x1801a0431  mov     rcx, [rbp+57h+pv]; pv
0x1801a0435  test    rcx, rcx
0x1801a0438  jz      short loc_1801A0441
0x1801a043a  call    cs:__imp_CoTaskMemFree
0x1801a0440  nop
0x1801a0441  mov     rcx, [rbp+57h+var_70]; pv
0x1801a0445  test    rcx, rcx
0x1801a0448  jz      short loc_1801A0450
0x1801a044a  call    cs:__imp_CoTaskMemFree
0x1801a0450  mov     eax, ebx
0x1801a0452  jmp     loc_1801A0641
0x1801a0457  lea     rcx, [rbp+57h+hKey]; this
0x1801a045b  call    ?_EnsureHKCUPathKey@CAppPathReader@@AEAAJXZ; CAppPathReader::_EnsureHKCUPathKey(void)
0x1801a0460  test    eax, eax
0x1801a0462  js      short loc_1801A0478
0x1801a0464  lea     rdx, aSkipclouddownl; "SkipCloudDownload"
0x1801a046b  mov     rcx, [rbp+57h+hKey]; HKEY
0x1801a046f  call    ?SHRegValueExists@@YAHPEAUHKEY__@@PEBGPEAK@Z; SHRegValueExists(HKEY__ *,ushort const *,ulong *)
0x1801a0474  mov     ebx, eax
0x1801a0476  jmp     short loc_1801A0481
0x1801a0478  xor     ebx, ebx
0x1801a047a  cmp     eax, 80070002h
0x1801a047f  jz      short loc_1801A0485
0x1801a0481  test    ebx, ebx
0x1801a0483  jnz     short loc_1801A04C2
0x1801a0485  mov     eax, [rbp+57h+var_38]
0x1801a0488  cmp     eax, 0FFFFFFFFh
0x1801a048b  jnz     short loc_1801A04A4
0x1801a048d  lea     r8, [rbp+57h+var_40]; HKEY *
0x1801a0491  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1801a0498  lea     rcx, [rbp+57h+hKey]; this
0x1801a049c  call    ?_PathToAppPathKeyHandle@CAppPathReader@@AEAAJPEAUHKEY__@@PEAPEAU2@@Z; CAppPathReader::_PathToAppPathKeyHandle(HKEY__ *,HKEY__ * *)
0x1801a04a1  mov     [rbp+57h+var_38], eax
0x1801a04a4  test    eax, eax
0x1801a04a6  js      short loc_1801A04BA
0x1801a04a8  lea     rdx, aSkipclouddownl; "SkipCloudDownload"
0x1801a04af  mov     rcx, [rbp+57h+var_40]; HKEY
0x1801a04b3  call    ?SHRegValueExists@@YAHPEAUHKEY__@@PEBGPEAK@Z; SHRegValueExists(HKEY__ *,ushort const *,ulong *)
0x1801a04b8  mov     ebx, eax
0x1801a04ba  test    ebx, ebx
0x1801a04bc  jz      loc_1801A03EA
0x1801a04c2  mov     rcx, [rbp+57h+hKey]; hKey
0x1801a04c6  test    rcx, rcx
0x1801a04c9  jz      short loc_1801A04D1
0x1801a04cb  call    cs:__imp_RegCloseKey
0x1801a04d1  mov     rcx, [rbp+57h+var_40]; hKey
0x1801a04d5  test    rcx, rcx
0x1801a04d8  jz      short loc_1801A04E0
0x1801a04da  call    cs:__imp_RegCloseKey
0x1801a04e0  mov     rcx, [rbp+57h+var_30]
0x1801a04e4  jmp     loc_1801A05ED
0x1801a04e9  mov     [rbp+57h+var_68], 0
0x1801a04f1  mov     rdi, [rsi+28h]
0x1801a04f5  mov     rax, [rdi+20h]
0x1801a04f9  mov     rbx, [rax+28h]
0x1801a04fd  lea     rcx, [rbp+57h+var_68]
0x1801a0501  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1801a0506  mov     rdx, rax
0x1801a0509  lea     rcx, [rdi+20h]
0x1801a050d  mov     rax, rbx
0x1801a0510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a0515  mov     ebx, eax
0x1801a0517  test    eax, eax
0x1801a0519  jns     short loc_1801A054C
0x1801a051b  mov     rcx, [rbp+5Fh]; this
0x1801a051f  mov     r9d, eax; char *
0x1801a0522  lea     r8, aOnecoreuapShel_124; "onecoreuap\\shell\\windows.storage\\sha"...
0x1801a0529  mov     edx, 0BD9h; void *
0x1801a052e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a0533  nop
0x1801a0534  mov     rcx, [rbp+57h+var_68]; pv
0x1801a0538  test    rcx, rcx
0x1801a053b  jz      loc_1801A0431
0x1801a0541  call    cs:__imp_CoTaskMemFree
0x1801a0547  jmp     loc_1801A0431
0x1801a054c  mov     rdx, [rbp+57h+pv]
0x1801a0550  mov     rcx, [rbp+57h+var_68]; unsigned __int16 *
0x1801a0554  test    rdx, rdx
0x1801a0557  jz      loc_1801A060F
0x1801a055d  call    ?IsFileExtension@@YAHPEBG@Z; IsFileExtension(ushort const *)
0x1801a0562  test    eax, eax
0x1801a0564  jz      loc_1801A060F
0x1801a056a  xorps   xmm0, xmm0
0x1801a056d  movdqu  [rbp+57h+var_60], xmm0
0x1801a0572  mov     r8, rcx; unsigned __int16 *
0x1801a0575  lea     rcx, [rbp+57h+var_60]; this
0x1801a0579  call    ?Init@StateRepositoryFileTypeAssocReader@@QEAAJPEBG0@Z; StateRepositoryFileTypeAssocReader::Init(ushort const *,ushort const *)
0x1801a057e  mov     ebx, eax
0x1801a0580  test    eax, eax
0x1801a0582  jns     short loc_1801A05A7
0x1801a0584  mov     edx, 0BDEh; void *
0x1801a0589  lea     r8, aOnecoreuapShel_124; "onecoreuap\\shell\\windows.storage\\sha"...
0x1801a0590  mov     r9d, ebx; char *
0x1801a0593  mov     rcx, [rbp+5Fh]; this
0x1801a0597  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a059c  lea     rcx, [rbp+57h+var_60]; this
0x1801a05a0  call    ??1StateRepositoryFileTypeAssocReader@@QEAA@XZ; StateRepositoryFileTypeAssocReader::~StateRepositoryFileTypeAssocReader(void)
0x1801a05a5  jmp     short loc_1801A0534
0x1801a05a7  mov     [rbp+57h+var_80], 0
0x1801a05ab  lea     rdx, [rbp+57h+var_80]; bool *
0x1801a05af  lea     rcx, [rbp+57h+var_60]; this
0x1801a05b3  call    ?WantsSkipCloudDownload@StateRepositoryFileTypeAssocReader@@QEAAJPEA_N@Z; StateRepositoryFileTypeAssocReader::WantsSkipCloudDownload(bool *)
0x1801a05b8  mov     ebx, eax
0x1801a05ba  test    eax, eax
0x1801a05bc  jns     short loc_1801A05C5
0x1801a05be  mov     edx, 0BE0h
0x1801a05c3  jmp     short loc_1801A0589
0x1801a05c5  lea     rcx, [rbp+57h+var_60]; this
0x1801a05c9  call    ??1StateRepositoryFileTypeAssocReader@@QEAA@XZ; StateRepositoryFileTypeAssocReader::~StateRepositoryFileTypeAssocReader(void)
0x1801a05ce  cmp     [rbp+57h+var_80], 0
0x1801a05d2  jz      short loc_1801A0607
0x1801a05d4  mov     rcx, [rbp+57h+var_68]; pv
0x1801a05d8  test    rcx, rcx
0x1801a05db  jz      short loc_1801A05E4
0x1801a05dd  call    cs:__imp_CoTaskMemFree
0x1801a05e3  nop
0x1801a05e4  mov     rcx, [rbp+57h+pv]; pv
0x1801a05e8  test    rcx, rcx
0x1801a05eb  jz      short loc_1801A05F4
0x1801a05ed  call    cs:__imp_CoTaskMemFree
0x1801a05f3  nop
0x1801a05f4  mov     rcx, [rbp+57h+var_70]; pv
0x1801a05f8  test    rcx, rcx
0x1801a05fb  jz      short loc_1801A0603
0x1801a05fd  call    cs:__imp_CoTaskMemFree
0x1801a0603  xor     eax, eax
0x1801a0605  jmp     short loc_1801A0641
0x1801a0607  mov     rdx, [rbp+57h+pv]
0x1801a060b  mov     rcx, [rbp+57h+var_68]; pv
0x1801a060f  test    rcx, rcx
0x1801a0612  jz      short loc_1801A061E
0x1801a0614  call    cs:__imp_CoTaskMemFree
0x1801a061a  mov     rdx, [rbp+57h+pv]
0x1801a061e  test    rdx, rdx
0x1801a0621  jz      short loc_1801A062D
0x1801a0623  mov     rcx, rdx; pv
0x1801a0626  call    cs:__imp_CoTaskMemFree
0x1801a062c  nop
0x1801a062d  mov     rcx, [rbp+57h+var_70]; pv
0x1801a0631  test    rcx, rcx
0x1801a0634  jz      short loc_1801A063C
0x1801a0636  call    cs:__imp_CoTaskMemFree
0x1801a063c  mov     eax, 80070490h
0x1801a0641  mov     rcx, [rbp+57h+var_28]
0x1801a0645  xor     rcx, rsp; StackCookie
0x1801a0648  call    __security_check_cookie
0x1801a064d  add     rsp, 98h
0x1801a0654  pop     rdi
0x1801a0655  pop     rsi
0x1801a0656  pop     rbx
0x1801a0657  pop     rbp
0x1801a0658  retn
```
