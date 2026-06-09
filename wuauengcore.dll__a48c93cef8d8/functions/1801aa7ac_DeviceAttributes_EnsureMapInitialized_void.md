# DeviceAttributes::EnsureMapInitialized(void)

- ea: `0x1801aa7ac`
- end: `0x1801aaaac`
- name: `?EnsureMapInitialized@DeviceAttributes@@AEAAJXZ`
- size: `768`
- prototype: `__int64 __fastcall(DeviceAttributes *__hidden this)`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801aa13c`
- `0x1801aa6c0`
- `0x180223f3c`

## callees

- `0x18000def4`
- `0x180015b10`
- `0x1800bf440`
- `0x1801aa7ac`
- `0x1801aae3c`
- `0x1801f231c`
- `0x1802388b4`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801aa7f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801aa7f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801aa9fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801aa9fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801aa9d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801aa9eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801aa9d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801aa9eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801aa8aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801aa8e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801aa956`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801aa964`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801aaa56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801aaa7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801aa8aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801aa8e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801aa956`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801aa964`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801aaa56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801aaa7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801aa8d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801aa907`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801aa8d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801aa907`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall DeviceAttributes::EnsureMapInitialized(DeviceAttributes *this)
{
  char *v2; // rbx
  HRESULT v3; // edi
  __int64 v4; // r14
  __int64 v5; // r15
  WUSystemInterfaceHelper *v6; // rcx
  int WUSystemInterface; // eax
  __int64 v8; // rdx
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  unsigned int v11; // r14d
  const WCHAR *v12; // rcx
  __int64 v13; // rdx
  HRESULT v14; // eax
  const WCHAR *v15; // rcx
  __int64 v16; // rdx
  HSTRING v17; // r15
  HSTRING v18; // r12
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rcx
  unsigned int v22; // edi
  __int64 v24; // rdx
  LPVOID *v25; // [rsp+20h] [rbp-60h]
  unsigned int v26; // [rsp+48h] [rbp-38h] BYREF
  HSTRING v27; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-20h]
  LPVOID v30; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v2 = (char *)this + 32;
  string = (HSTRING)((char *)this + 32);
  if ( this != (DeviceAttributes *)-32LL )
    EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  v27 = 0;
  if ( *((_DWORD *)this + 5) )
  {
    v3 = 0;
    goto LABEL_28;
  }
  CSusArrayList<CSusMap<HSTRING__ *,HSTRING__ *,CSusSortedArrayListItemOpsHSTRING,CSusSortedArrayListItemOpsHSTRING>::_tagMapEntry,CSusMap<HSTRING__ *,HSTRING__ *,CSusSortedArrayListItemOpsHSTRING,CSusSortedArrayListItemOpsHSTRING>::CMapEntryOps>::RemoveArraySection(this);
  v26 = 0;
  v30 = 0;
  pv = 0;
  v4 = *((_QWORD *)this + 12);
  v5 = *((_QWORD *)this + 11);
  WUSystemInterface = WUSystemInterfaceHelper::LoadWUSystemInterface(v6);
  v3 = WUSystemInterface;
  if ( WUSystemInterface < 0 )
  {
    v8 = 313;
    v9 = (unsigned int)WUSystemInterface;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusyshelper\\wusyshelper.cpp",
      (const char *)v9,
      (int)v25);
    v10 = 392;
LABEL_37:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\DeviceAttributes\\DeviceAttributes.cpp",
      (const char *)(unsigned int)v3,
      (int)v25);
    goto LABEL_24;
  }
  v25 = &v30;
  v3 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, unsigned int *))(*(_QWORD *)g_WUSystemInterface + 232LL))(
         g_WUSystemInterface,
         v5,
         v4,
         &v26);
  v9 = (unsigned int)v3;
  if ( v3 < 0 )
  {
    v8 = 319;
    goto LABEL_9;
  }
  v11 = 0;
  if ( v26 )
  {
    while ( 1 )
    {
      WindowsDeleteString(0);
      string = 0;
      v12 = (const WCHAR *)*((_QWORD *)v30 + v11);
      v13 = -1;
      do
        ++v13;
      while ( v12[v13] );
      v14 = WindowsCreateString(v12, v13, &string);
      v3 = v14;
      if ( v14 < 0 )
        break;
      WindowsDeleteString(0);
      v27 = 0;
      v15 = (const WCHAR *)*((_QWORD *)pv + v11);
      v16 = -1;
      do
        ++v16;
      while ( v15[v16] );
      v3 = WindowsCreateString(v15, v16, &v27);
      if ( v3 < 0 )
      {
        v24 = 404;
        goto LABEL_33;
      }
      v17 = string;
      v18 = v27;
      v3 = CSusArrayList<tagSusFileRange,CSusArrayListItemOpNoop<tagSusFileRange>>::Grow(
             this,
             (unsigned int)(*((_DWORD *)this + 5) + 1));
      if ( v3 < 0 )
      {
        v24 = 406;
LABEL_33:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v24,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\DeviceAttributes\\DeviceAttributes.cpp",
          (const char *)(unsigned int)v3,
          (int)&v30);
        WindowsDeleteString(v27);
        v27 = 0;
        goto LABEL_35;
      }
      v19 = 2LL * *((unsigned int *)this + 5);
      v20 = *((_QWORD *)this + 1);
      *(_QWORD *)(v20 + 8 * v19) = v18;
      *(_QWORD *)(v20 + 8 * v19 + 8) = v17;
      ++*((_DWORD *)this + 5);
      string = 0;
      v27 = 0;
      WindowsDeleteString(0);
      v27 = 0;
      WindowsDeleteString(string);
      if ( ++v11 >= v26 )
        goto LABEL_19;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18F,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\DeviceAttributes\\DeviceAttributes.cpp",
      (const char *)(unsigned int)v14,
      (int)&v30);
LABEL_35:
    WindowsDeleteString(string);
    goto LABEL_24;
  }
LABEL_19:
  if ( *((_DWORD *)this + 5) > 1u )
  {
    qsort(
      *((void **)this + 1),
      *((unsigned int *)this + 5),
      0x10u,
      CSusSortedArrayList<CSusMap<HSTRING__ *,HSTRING__ *,CSusSortedArrayListItemOpsHSTRING,CSusSortedArrayListItemOpsHSTRING>::_tagMapEntry,CSusMap<HSTRING__ *,HSTRING__ *,CSusSortedArrayListItemOpsHSTRING,CSusSortedArrayListItemOpsHSTRING>::CMapEntryOps>::CompareWeights);
    v21 = 0;
    if ( *((_DWORD *)this + 5) != 1 )
    {
      while ( 1 )
      {
        v22 = v21 + 1;
        if ( !(unsigned int)CSusMap<HSTRING__ *,HSTRING__ *,CSusSortedArrayListItemOpsHSTRING,CSusSortedArrayListItemOpsHSTRING>::CMapEntryOps::Compare(
                              *((_QWORD *)this + 1) + 16 * v21,
                              *((_QWORD *)this + 1) + 16LL * (unsigned int)(v21 + 1)) )
          break;
        v21 = v22;
        if ( v22 >= *((_DWORD *)this + 5) - 1 )
          goto LABEL_23;
      }
      v3 = -2145124333;
      v10 = 412;
      goto LABEL_37;
    }
  }
LABEL_23:
  v3 = 0;
LABEL_24:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v30 )
  {
    CoTaskMemFree(v30);
    v30 = 0;
  }
LABEL_28:
  if ( v2 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 8));
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1801aa7ac  mov     [rsp-28h+arg_8], rbx
0x1801aa7b1  mov     [rsp-28h+arg_10], rsi
0x1801aa7b6  mov     [rsp-28h+arg_18], rdi
0x1801aa7bb  push    rbp
0x1801aa7bc  push    r12
0x1801aa7be  push    r13
0x1801aa7c0  push    r14
0x1801aa7c2  push    r15
0x1801aa7c4  mov     rbp, rsp
0x1801aa7c7  sub     rsp, 80h
0x1801aa7ce  mov     rax, cs:__security_cookie
0x1801aa7d5  xor     rax, rsp
0x1801aa7d8  mov     [rbp+var_10], rax
0x1801aa7dc  mov     rsi, rcx
0x1801aa7df  lea     rbx, [rcx+20h]
0x1801aa7e3  mov     [rbp+string], rbx
0x1801aa7e7  xor     r13d, r13d
0x1801aa7ea  test    rbx, rbx
0x1801aa7ed  jz      short loc_1801AA7FA
0x1801aa7ef  lea     rcx, [rbx+8]; lpCriticalSection
0x1801aa7f3  call    cs:__imp_EnterCriticalSection
0x1801aa7f9  nop
0x1801aa7fa  mov     [rbp+var_30], r13
0x1801aa7fe  mov     [rbp+var_40], r13
0x1801aa802  cmp     [rsi+14h], r13d
0x1801aa806  jz      short loc_1801AA810
0x1801aa808  mov     edi, r13d
0x1801aa80b  jmp     loc_1801AA9F5
0x1801aa810  mov     rcx, rsi
0x1801aa813  call    ?RemoveArraySection@?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEAUHSTRING__@@PEAU1@VCSusSortedArrayListItemOpsHSTRING@@V2@@@VCMapEntryOps@2@@@IEAAXKKH@Z; CSusArrayList<CSusMap<HSTRING__ *,HSTRING__ *,CSusSortedArrayListItemOpsHSTRING,CSusSortedArrayListItemOpsHSTRING>::_tagMapEntry,CSusMap<HSTRING__ *,HSTRING__ *,CSusSortedArrayListItemOpsHSTRING,CSusSortedArrayListItemOpsHSTRING>::CMapEntryOps>::RemoveArraySection(ulong,ulong,int)
0x1801aa818  mov     [rbp+var_38], r13d
0x1801aa81c  mov     [rbp+var_18], r13
0x1801aa820  mov     [rbp+pv], r13
0x1801aa824  mov     r14, [rsi+60h]
0x1801aa828  mov     r15, [rsi+58h]
0x1801aa82c  call    ?LoadWUSystemInterface@WUSystemInterfaceHelper@@YAJXZ; WUSystemInterfaceHelper::LoadWUSystemInterface(void)
0x1801aa831  mov     edi, eax
0x1801aa833  test    eax, eax
0x1801aa835  jns     short loc_1801AA841
0x1801aa837  mov     edx, 139h
0x1801aa83c  mov     r9d, eax
0x1801aa83f  jmp     short loc_1801AA881
0x1801aa841  mov     rcx, cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x1801aa848  mov     rax, [rcx]
0x1801aa84b  lea     rdx, [rbp+pv]
0x1801aa84f  mov     [rsp+80h+var_58], rdx
0x1801aa854  lea     rdx, [rbp+var_18]
0x1801aa858  mov     qword ptr [rsp+80h+var_60], rdx; int
0x1801aa85d  lea     r9, [rbp+var_38]
0x1801aa861  mov     r8, r14
0x1801aa864  mov     rdx, r15
0x1801aa867  mov     rax, [rax+0E8h]
0x1801aa86e  call    _guard_dispatch_icall
0x1801aa873  mov     edi, eax
0x1801aa875  mov     r9d, eax; char *
0x1801aa878  test    eax, eax
0x1801aa87a  jns     short loc_1801AA89B
0x1801aa87c  mov     edx, 13Fh; void *
0x1801aa881  lea     r8, aCW1SSrcClientL_30; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x1801aa888  mov     rcx, [rbp+28h]; this
0x1801aa88c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801aa891  mov     edx, 188h
0x1801aa896  jmp     loc_1801AAA93
0x1801aa89b  mov     r14d, r13d
0x1801aa89e  cmp     [rbp+var_38], r13d
0x1801aa8a2  jbe     loc_1801AA977
0x1801aa8a8  xor     ecx, ecx; string
0x1801aa8aa  call    cs:__imp_WindowsDeleteString
0x1801aa8b0  mov     [rbp+string], r13
0x1801aa8b4  mov     r15d, r14d
0x1801aa8b7  mov     rax, [rbp+var_18]
0x1801aa8bb  mov     rcx, [rax+r15*8]; sourceString
0x1801aa8bf  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1801aa8c3  inc     rdx; length
0x1801aa8c6  cmp     [rcx+rdx*2], r13w
0x1801aa8cb  jnz     short loc_1801AA8C3
0x1801aa8cd  lea     r8, [rbp+string]; string
0x1801aa8d1  call    cs:__imp_WindowsCreateString
0x1801aa8d7  mov     edi, eax
0x1801aa8d9  test    eax, eax
0x1801aa8db  js      loc_1801AAA62
0x1801aa8e1  xor     ecx, ecx; string
0x1801aa8e3  call    cs:__imp_WindowsDeleteString
0x1801aa8e9  mov     [rbp+var_30], r13
0x1801aa8ed  mov     rax, [rbp+pv]
0x1801aa8f1  mov     rcx, [rax+r15*8]; sourceString
0x1801aa8f5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1801aa8f9  inc     rdx; length
0x1801aa8fc  cmp     [rcx+rdx*2], r13w
0x1801aa901  jnz     short loc_1801AA8F9
0x1801aa903  lea     r8, [rbp+var_30]; string
0x1801aa907  call    cs:__imp_WindowsCreateString
0x1801aa90d  mov     edi, eax
0x1801aa90f  test    eax, eax
0x1801aa911  js      loc_1801AAA3A
0x1801aa917  mov     r15, [rbp+string]
0x1801aa91b  mov     r12, [rbp+var_30]
0x1801aa91f  mov     edx, [rsi+14h]
0x1801aa922  inc     edx
0x1801aa924  mov     rcx, rsi
0x1801aa927  call    ?Grow@?$CSusArrayList@UtagSusFileRange@@V?$CSusArrayListItemOpNoop@UtagSusFileRange@@@@@@QEAAJK@Z; CSusArrayList<tagSusFileRange,CSusArrayListItemOpNoop<tagSusFileRange>>::Grow(ulong)
0x1801aa92c  mov     edi, eax
0x1801aa92e  test    eax, eax
0x1801aa930  js      loc_1801AAA33
0x1801aa936  mov     ecx, [rsi+14h]
0x1801aa939  add     rcx, rcx
0x1801aa93c  mov     rax, [rsi+8]
0x1801aa940  mov     [rax+rcx*8], r12
0x1801aa944  mov     [rax+rcx*8+8], r15
0x1801aa949  inc     dword ptr [rsi+14h]
0x1801aa94c  mov     [rbp+string], r13
0x1801aa950  mov     [rbp+var_30], r13
0x1801aa954  xor     ecx, ecx; string
0x1801aa956  call    cs:__imp_WindowsDeleteString
0x1801aa95c  mov     [rbp+var_30], r13
0x1801aa960  mov     rcx, [rbp+string]; string
0x1801aa964  call    cs:__imp_WindowsDeleteString
0x1801aa96a  inc     r14d
0x1801aa96d  cmp     r14d, [rbp+var_38]
0x1801aa971  jb      loc_1801AA8A8
0x1801aa977  cmp     dword ptr [rsi+14h], 1
0x1801aa97b  jbe     short loc_1801AA9CC
0x1801aa97d  mov     edx, [rsi+14h]; NumOfElements
0x1801aa980  lea     r9, ?CompareWeights@?$CSusSortedArrayList@U_tagMapEntry@?$CSusMap@PEAUHSTRING__@@PEAU1@VCSusSortedArrayListItemOpsHSTRING@@V2@@@VCMapEntryOps@2@@@CAHPEBX0@Z; CompareFunction
0x1801aa987  mov     r8d, 10h; SizeOfElements
0x1801aa98d  mov     rcx, [rsi+8]; Base
0x1801aa991  call    qsort
0x1801aa996  mov     ecx, r13d
0x1801aa999  cmp     dword ptr [rsi+14h], 1
0x1801aa99d  jz      short loc_1801AA9CC
0x1801aa99f  lea     edi, [rcx+1]
0x1801aa9a2  mov     edx, edi
0x1801aa9a4  shl     rdx, 4
0x1801aa9a8  add     rdx, [rsi+8]
0x1801aa9ac  shl     rcx, 4
0x1801aa9b0  add     rcx, [rsi+8]
0x1801aa9b4  call    ?Compare@CMapEntryOps@?$CSusMap@PEAUHSTRING__@@PEAU1@VCSusSortedArrayListItemOpsHSTRING@@V2@@@SAHAEBU_tagMapEntry@2@0@Z; CSusMap<HSTRING__ *,HSTRING__ *,CSusSortedArrayListItemOpsHSTRING,CSusSortedArrayListItemOpsHSTRING>::CMapEntryOps::Compare(CSusMap<HSTRING__ *,HSTRING__ *,CSusSortedArrayListItemOpsHSTRING,CSusSortedArrayListItemOpsHSTRING>::_tagMapEntry const &,CSusMap<HSTRING__ *,HSTRING__ *,CSusSortedArrayListItemOpsHSTRING,CSusSortedArrayListItemOpsHSTRING>::_tagMapEntry const &)
0x1801aa9b9  test    eax, eax
0x1801aa9bb  jz      loc_1801AAA89
0x1801aa9c1  mov     ecx, edi
0x1801aa9c3  mov     eax, [rsi+14h]
0x1801aa9c6  dec     eax
0x1801aa9c8  cmp     edi, eax
0x1801aa9ca  jb      short loc_1801AA99F
0x1801aa9cc  mov     edi, r13d
0x1801aa9cf  mov     rcx, [rbp+pv]; pv
0x1801aa9d3  test    rcx, rcx
0x1801aa9d6  jz      short loc_1801AA9E2
0x1801aa9d8  call    cs:__imp_CoTaskMemFree
0x1801aa9de  mov     [rbp+pv], r13
0x1801aa9e2  mov     rcx, [rbp+var_18]; pv
0x1801aa9e6  test    rcx, rcx
0x1801aa9e9  jz      short loc_1801AA9F5
0x1801aa9eb  call    cs:__imp_CoTaskMemFree
0x1801aa9f1  mov     [rbp+var_18], r13
0x1801aa9f5  test    rbx, rbx
0x1801aa9f8  jz      short loc_1801AAA04
0x1801aa9fa  lea     rcx, [rbx+8]; lpCriticalSection
0x1801aa9fe  call    cs:__imp_LeaveCriticalSection
0x1801aaa04  mov     eax, edi
0x1801aaa06  mov     rcx, [rbp+var_10]
0x1801aaa0a  xor     rcx, rsp; StackCookie
0x1801aaa0d  call    __security_check_cookie
0x1801aaa12  lea     r11, [rsp+80h+var_s0]
0x1801aaa1a  mov     rbx, [r11+38h]
0x1801aaa1e  mov     rsi, [r11+40h]
0x1801aaa22  mov     rdi, [r11+48h]
0x1801aaa26  mov     rsp, r11
0x1801aaa29  pop     r15
0x1801aaa2b  pop     r14
0x1801aaa2d  pop     r13
0x1801aaa2f  pop     r12
0x1801aaa31  pop     rbp
0x1801aaa32  retn
0x1801aaa33  mov     edx, 196h
0x1801aaa38  jmp     short loc_1801AAA3F
0x1801aaa3a  mov     edx, 194h; void *
0x1801aaa3f  mov     rcx, [rbp+28h]; this
0x1801aaa43  mov     r9d, edi; char *
0x1801aaa46  lea     r8, aCW1SSrcClientE_123; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x1801aaa4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801aaa52  mov     rcx, [rbp+var_30]; string
0x1801aaa56  call    cs:__imp_WindowsDeleteString
0x1801aaa5c  mov     [rbp+var_30], r13
0x1801aaa60  jmp     short loc_1801AAA7A
0x1801aaa62  mov     rcx, [rbp+28h]; this
0x1801aaa66  mov     r9d, eax; char *
0x1801aaa69  lea     r8, aCW1SSrcClientE_123; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x1801aaa70  mov     edx, 18Fh; void *
0x1801aaa75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801aaa7a  mov     rcx, [rbp+string]; string
0x1801aaa7e  call    cs:__imp_WindowsDeleteString
0x1801aaa84  jmp     loc_1801AA9CF
0x1801aaa89  mov     edi, 80240013h
0x1801aaa8e  mov     edx, 19Ch; void *
0x1801aaa93  lea     r8, aCW1SSrcClientE_123; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x1801aaa9a  mov     r9d, edi; char *
0x1801aaa9d  mov     rcx, [rbp+28h]; this
0x1801aaaa1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801aaaa6  jmp     loc_1801AA9CF
```
