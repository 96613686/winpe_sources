# UnifiedSessionResultWrapper::ProcessLocalResult(SPRESULTHEADER const *)

- ea: `0x1800703cc`
- end: `0x180070915`
- name: `?ProcessLocalResult@UnifiedSessionResultWrapper@@AEAAJPEBUSPRESULTHEADER@@@Z`
- size: `1353`
- prototype: `__int64 __fastcall(UnifiedSessionResultWrapper *__hidden this, const struct SPRESULTHEADER *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1801a6718`

## callees

- `0x18000bec4`
- `0x180020ed8`
- `0x180026508`
- `0x180029860`
- `0x18002ad5c`
- `0x18002b750`
- `0x18002d314`
- `0x18002d404`
- `0x18002f130`
- `0x180030a7c`
- `0x18003c550`
- `0x1800703cc`
- `0x18007091c`
- `0x180079e30`
- `0x18012c0c4`
- `0x1801a67a4`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180070429`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180070429`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007052c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800705d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800705e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070696`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800706ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070877`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007088d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800708bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800708d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007052c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800705d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800705e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070696`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800706ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070877`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007088d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800708bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800708d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall UnifiedSessionResultWrapper::ProcessLocalResult(
        UnifiedSessionResultWrapper *this,
        const struct SPRESULTHEADER *a2)
{
  __int64 v4; // r14
  HRESULT v5; // eax
  unsigned int v6; // ebx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rax
  int v11; // ebx
  void *v12; // rcx
  __int64 v13; // rax
  void *v14; // rcx
  void *v15; // rcx
  const WCHAR *v16; // rdx
  __int64 v17; // r8
  int v18; // eax
  void *v19; // rcx
  void *v20; // rcx
  char v21; // bl
  _QWORD *v22; // rax
  _QWORD *v23; // rax
  char v24; // si
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  int v28; // eax
  void *v29; // rcx
  void *v30; // rcx
  void *v31; // rcx
  void *v32; // rcx
  int ppv; // [rsp+20h] [rbp-C8h]
  LPVOID pv; // [rsp+40h] [rbp-A8h] BYREF
  LPVOID v35; // [rsp+48h] [rbp-A0h] BYREF
  LPVOID v36; // [rsp+50h] [rbp-98h] BYREF
  int v37; // [rsp+58h] [rbp-90h]
  _QWORD v38[2]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v39[8]; // [rsp+70h] [rbp-78h] BYREF
  _BYTE v40[8]; // [rsp+78h] [rbp-70h] BYREF
  LPVOID *p_pv; // [rsp+80h] [rbp-68h] BYREF
  int v42[2]; // [rsp+88h] [rbp-60h] BYREF
  char v43; // [rsp+90h] [rbp-58h]
  _BYTE v44[32]; // [rsp+A0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v37 = 0;
  v4 = *((unsigned int *)a2 + 17);
  v35 = 0;
  v5 = CoCreateInstance(&CLSID_SpPhraseBuilder, 0, 0x17u, &GUID_88a3342a_0bed_4834_922b_88d43173162f, &v35);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x96,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\unifiedsessionresultwrapper.cpp",
      (const char *)(unsigned int)v5,
      ppv);
    ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v35);
    return v6;
  }
  v8 = (*(__int64 (__fastcall **)(LPVOID, char *))(*(_QWORD *)v35 + 64LL))(v35, (char *)a2 + v4);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x97,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\unifiedsessionresultwrapper.cpp",
      (const char *)(unsigned int)v8,
      ppv);
    ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v35);
    return v9;
  }
  pv = 0;
  v10 = *(_QWORD *)v35;
  p_pv = &pv;
  *(_QWORD *)v42 = 0;
  v43 = 1;
  v11 = (*(__int64 (__fastcall **)(LPVOID, int *))(v10 + 24))(v35, v42);
  wil::details::out_param_t<wistd::unique_ptr<SPPHRASE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<SPPHRASE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9A,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\unifiedsessionresultwrapper.cpp",
      (const char *)(unsigned int)v11,
      ppv);
    v12 = pv;
    pv = 0;
    if ( v12 )
      CoTaskMemFree(v12);
LABEL_38:
    ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v35);
    return (unsigned int)v11;
  }
  v36 = 0;
  v13 = *(_QWORD *)v35;
  p_pv = &v36;
  *(_QWORD *)v42 = 0;
  v43 = 1;
  v11 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, __int64))(v13 + 40))(v35, 0xFFFFFFFFLL, 0xFFFFFFFFLL, 1);
  wil::details::out_param_t<wistd::unique_ptr<SPPHRASE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<SPPHRASE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\unifiedsessionresultwrapper.cpp",
      (const char *)(unsigned int)v11,
      (int)v42);
    v14 = v36;
    v36 = 0;
    if ( v14 )
      CoTaskMemFree(v14);
    v15 = pv;
    pv = 0;
    if ( v15 )
      CoTaskMemFree(v15);
    goto LABEL_38;
  }
  v16 = &cchOriginalDestLength;
  if ( v36 )
    v16 = (const WCHAR *)v36;
  v17 = -1;
  do
    ++v17;
  while ( v16[v17] );
  std::wstring::_Assign<unsigned short>((char *)this + 32, v16, v17);
  *((double *)this + 8) = *((float *)pv + 22);
  *((_DWORD *)this + 18) = 1;
  std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(v38);
  v18 = UnifiedSessionResultWrapper::PropertiesFromLocalResult(pv, v38);
  v11 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\unifiedsessionresultwrapper.cpp",
      (const char *)(unsigned int)v18,
      (int)v42);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v38);
    v19 = v36;
    v36 = 0;
    if ( v19 )
      CoTaskMemFree(v19);
    v20 = pv;
    pv = 0;
    if ( v20 )
      CoTaskMemFree(v20);
    goto LABEL_38;
  }
  std::wstring::wstring(v44, L"domain");
  v21 = 1;
  v37 = 1;
  v22 = (_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
                    v38,
                    v39,
                    v44);
  if ( *v22 == v38[0]
    || (std::wstring::wstring(&p_pv, L"intent"),
        v21 = 3,
        v23 = (_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
                          v38,
                          v40,
                          &p_pv),
        v24 = 1,
        *v23 == v38[0]) )
  {
    v24 = 0;
  }
  if ( (v21 & 2) != 0 )
  {
    v21 &= ~2u;
    std::wstring::_Tidy_deallocate(&p_pv);
  }
  if ( (v21 & 1) != 0 )
    std::wstring::_Tidy_deallocate(v44);
  if ( v24 )
  {
    std::wstring::wstring(v44, L"domain");
    v25 = std::map<std::wstring,std::wstring>::operator[](v38, v44);
    std::wstring::operator=((char *)this + 80, v25);
    std::wstring::_Tidy_deallocate(v44);
    v26 = std::wstring::_Append<unsigned short>((char *)this + 80);
    std::wstring::operator=((char *)this + 80, v26);
    std::wstring::wstring(v44, L"intent");
    std::map<std::wstring,std::wstring>::operator[](v38, v44);
    v27 = std::wstring::_Append<unsigned short>((char *)this + 80);
    std::wstring::operator=((char *)this + 80, v27);
    std::wstring::_Tidy_deallocate(v44);
    v28 = ActionUriFromProperties(v38, (char *)this + 112);
    v11 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAD,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\unifiedsessionresultwrapper.cpp",
        (const char *)(unsigned int)v28,
        (int)v42);
      std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v38);
      v29 = v36;
      v36 = 0;
      if ( v29 )
        CoTaskMemFree(v29);
      v30 = pv;
      pv = 0;
      if ( v30 )
        CoTaskMemFree(v30);
      goto LABEL_38;
    }
  }
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v38);
  v31 = v36;
  v36 = 0;
  if ( v31 )
    CoTaskMemFree(v31);
  v32 = pv;
  pv = 0;
  if ( v32 )
    CoTaskMemFree(v32);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v35);
  return 0;
}

```

## disassembly

```asm
0x1800703cc  mov     [rsp+arg_10], rbx
0x1800703d1  mov     [rsp+arg_18], rsi
0x1800703d6  push    rdi
0x1800703d7  push    r14
0x1800703d9  push    r15
0x1800703db  sub     rsp, 0D0h
0x1800703e2  mov     rax, cs:__security_cookie
0x1800703e9  xor     rax, rsp
0x1800703ec  mov     [rsp+0E8h+var_28], rax
0x1800703f4  mov     rsi, rdx
0x1800703f7  mov     rdi, rcx
0x1800703fa  xor     r15d, r15d
0x1800703fd  mov     [rsp+0E8h+var_90], r15d
0x180070402  mov     r14d, [rdx+44h]
0x180070406  mov     [rsp+0E8h+var_A0], r15
0x18007040b  lea     rax, [rsp+0E8h+var_A0]
0x180070410  mov     [rsp+0E8h+ppv], rax; int
0x180070415  lea     r9, _GUID_88a3342a_0bed_4834_922b_88d43173162f; riid
0x18007041c  xor     edx, edx; pUnkOuter
0x18007041e  lea     r8d, [r15+17h]; dwClsContext
0x180070422  lea     rcx, CLSID_SpPhraseBuilder; rclsid
0x180070429  call    cs:__imp_CoCreateInstance
0x18007042f  mov     ebx, eax
0x180070431  test    eax, eax
0x180070433  jns     short loc_180070463
0x180070435  mov     rcx, [rsp+0E8h]; this
0x18007043d  mov     r9d, eax; char *
0x180070440  lea     r8, aOnecoreuapEndu_346; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180070447  mov     edx, 96h; void *
0x18007044c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180070451  nop
0x180070452  lea     rcx, [rsp+0E8h+var_A0]
0x180070457  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x18007045c  mov     eax, ebx
0x18007045e  jmp     loc_1800708EB
0x180070463  mov     rcx, [rsp+0E8h+var_A0]
0x180070468  mov     rax, [rcx]
0x18007046b  lea     rdx, [rsi+r14]
0x18007046f  mov     rax, [rax+40h]
0x180070473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070478  mov     ebx, eax
0x18007047a  test    eax, eax
0x18007047c  jns     short loc_1800704AC
0x18007047e  mov     rcx, [rsp+0E8h]; this
0x180070486  mov     r9d, eax; char *
0x180070489  lea     r8, aOnecoreuapEndu_346; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180070490  mov     edx, 97h; void *
0x180070495  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007049a  nop
0x18007049b  lea     rcx, [rsp+0E8h+var_A0]
0x1800704a0  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800704a5  mov     eax, ebx
0x1800704a7  jmp     loc_1800708EB
0x1800704ac  mov     [rsp+0E8h+pv], r15
0x1800704b1  mov     rcx, [rsp+0E8h+var_A0]
0x1800704b6  mov     rax, [rcx]
0x1800704b9  lea     rdx, [rsp+0E8h+pv]
0x1800704be  mov     [rsp+0E8h+var_68], rdx
0x1800704c6  mov     qword ptr [rsp+0E8h+var_60], r15
0x1800704ce  mov     r14d, 1
0x1800704d4  mov     [rsp+0E8h+var_58], r14b
0x1800704dc  lea     rdx, [rsp+0E8h+var_60]
0x1800704e4  mov     rax, [rax+18h]
0x1800704e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800704ed  mov     ebx, eax
0x1800704ef  lea     rcx, [rsp+0E8h+var_68]
0x1800704f7  call    ??1?$out_param_t@V?$unique_ptr@USPPHRASE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SPPHRASE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<SPPHRASE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800704fc  test    ebx, ebx
0x1800704fe  jns     short loc_180070544
0x180070500  mov     rcx, [rsp+0E8h]; this
0x180070508  mov     r9d, ebx; char *
0x18007050b  lea     r8, aOnecoreuapEndu_346; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180070512  mov     edx, 9Ah; void *
0x180070517  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007051c  nop
0x18007051d  mov     rcx, [rsp+0E8h+pv]; pv
0x180070522  mov     [rsp+0E8h+pv], r15
0x180070527  test    rcx, rcx
0x18007052a  jz      short loc_180070533
0x18007052c  call    cs:__imp_CoTaskMemFree
0x180070532  nop
0x180070533  lea     rcx, [rsp+0E8h+var_A0]
0x180070538  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x18007053d  mov     eax, ebx
0x18007053f  jmp     loc_1800708EB
0x180070544  mov     [rsp+0E8h+var_98], r15
0x180070549  mov     rcx, [rsp+0E8h+var_A0]
0x18007054e  mov     rax, [rcx]
0x180070551  lea     rdx, [rsp+0E8h+var_98]
0x180070556  mov     [rsp+0E8h+var_68], rdx
0x18007055e  mov     qword ptr [rsp+0E8h+var_60], r15
0x180070566  mov     [rsp+0E8h+var_58], r14b
0x18007056e  mov     [rsp+0E8h+var_C0], r15
0x180070573  lea     rdx, [rsp+0E8h+var_60]
0x18007057b  mov     [rsp+0E8h+ppv], rdx; int
0x180070580  mov     r9d, r14d
0x180070583  or      edx, 0FFFFFFFFh
0x180070586  mov     r8d, edx
0x180070589  mov     rax, [rax+28h]
0x18007058d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070592  mov     ebx, eax
0x180070594  lea     rcx, [rsp+0E8h+var_68]
0x18007059c  call    ??1?$out_param_t@V?$unique_ptr@USPPHRASE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SPPHRASE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<SPPHRASE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800705a1  test    ebx, ebx
0x1800705a3  jns     short loc_1800705FF
0x1800705a5  mov     rcx, [rsp+0E8h]; this
0x1800705ad  mov     r9d, ebx; char *
0x1800705b0  lea     r8, aOnecoreuapEndu_346; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1800705b7  mov     edx, 9Eh; void *
0x1800705bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800705c1  nop
0x1800705c2  mov     rcx, [rsp+0E8h+var_98]; pv
0x1800705c7  mov     [rsp+0E8h+var_98], r15
0x1800705cc  test    rcx, rcx
0x1800705cf  jz      short loc_1800705D8
0x1800705d1  call    cs:__imp_CoTaskMemFree
0x1800705d7  nop
0x1800705d8  mov     rcx, [rsp+0E8h+pv]; pv
0x1800705dd  mov     [rsp+0E8h+pv], r15
0x1800705e2  test    rcx, rcx
0x1800705e5  jz      short loc_1800705EE
0x1800705e7  call    cs:__imp_CoTaskMemFree
0x1800705ed  nop
0x1800705ee  lea     rcx, [rsp+0E8h+var_A0]
0x1800705f3  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800705f8  mov     eax, ebx
0x1800705fa  jmp     loc_1800708EB
0x1800705ff  lea     rdx, cchOriginalDestLength
0x180070606  mov     rax, [rsp+0E8h+var_98]
0x18007060b  test    rax, rax
0x18007060e  cmovnz  rdx, rax
0x180070612  or      r8, 0FFFFFFFFFFFFFFFFh
0x180070616  inc     r8
0x180070619  cmp     [rdx+r8*2], r15w
0x18007061e  jnz     short loc_180070616
0x180070620  lea     rcx, [rdi+20h]
0x180070624  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180070629  mov     rax, [rsp+0E8h+pv]
0x18007062e  movss   xmm0, dword ptr [rax+58h]
0x180070633  cvtps2pd xmm0, xmm0
0x180070636  movsd   qword ptr [rdi+40h], xmm0
0x18007063b  mov     [rdi+48h], r14d
0x18007063f  lea     rcx, [rsp+0E8h+var_88]
0x180070644  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x180070649  nop
0x18007064a  lea     rdx, [rsp+0E8h+var_88]
0x18007064f  mov     rcx, [rsp+0E8h+pv]
0x180070654  call    ?PropertiesFromLocalResult@UnifiedSessionResultWrapper@@CAJPEBUSPPHRASE@@AEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@_N@Z; UnifiedSessionResultWrapper::PropertiesFromLocalResult(SPPHRASE const *,std::map<std::wstring,std::wstring> &,bool)
0x180070659  mov     ebx, eax
0x18007065b  test    eax, eax
0x18007065d  jns     short loc_1800706C4
0x18007065f  mov     rcx, [rsp+0E8h]; this
0x180070667  mov     r9d, eax; char *
0x18007066a  lea     r8, aOnecoreuapEndu_346; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180070671  mov     edx, 0A5h; void *
0x180070676  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007067b  nop
0x18007067c  lea     rcx, [rsp+0E8h+var_88]
0x180070681  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x180070686  nop
0x180070687  mov     rcx, [rsp+0E8h+var_98]; pv
0x18007068c  mov     [rsp+0E8h+var_98], r15
0x180070691  test    rcx, rcx
0x180070694  jz      short loc_18007069D
0x180070696  call    cs:__imp_CoTaskMemFree
0x18007069c  nop
0x18007069d  mov     rcx, [rsp+0E8h+pv]; pv
0x1800706a2  mov     [rsp+0E8h+pv], r15
0x1800706a7  test    rcx, rcx
0x1800706aa  jz      short loc_1800706B3
0x1800706ac  call    cs:__imp_CoTaskMemFree
0x1800706b2  nop
0x1800706b3  lea     rcx, [rsp+0E8h+var_A0]
0x1800706b8  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800706bd  mov     eax, ebx
0x1800706bf  jmp     loc_1800708EB
0x1800706c4  lea     rdx, aDomain; "domain"
0x1800706cb  lea     rcx, [rsp+0E8h+var_48]
0x1800706d3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800706d8  nop
0x1800706d9  mov     ebx, r14d
0x1800706dc  mov     [rsp+0E8h+var_90], ebx
0x1800706e0  lea     r8, [rsp+0E8h+var_48]
0x1800706e8  lea     rdx, [rsp+0E8h+var_78]
0x1800706ed  lea     rcx, [rsp+0E8h+var_88]
0x1800706f2  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x1800706f7  mov     rcx, [rsp+0E8h+var_88]
0x1800706fc  cmp     [rax], rcx
0x1800706ff  jz      short loc_18007073E
0x180070701  lea     rdx, aIntent; "intent"
0x180070708  lea     rcx, [rsp+0E8h+var_68]
0x180070710  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180070715  mov     ebx, 3
0x18007071a  lea     r8, [rsp+0E8h+var_68]
0x180070722  lea     rdx, [rsp+0E8h+var_70]
0x180070727  lea     rcx, [rsp+0E8h+var_88]
0x18007072c  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x180070731  mov     rcx, [rsp+0E8h+var_88]
0x180070736  cmp     [rax], rcx
0x180070739  mov     sil, r14b
0x18007073c  jnz     short loc_180070741
0x18007073e  mov     sil, r15b
0x180070741  test    bl, 2
0x180070744  jz      short loc_180070757
0x180070746  and     ebx, 0FFFFFFFDh
0x180070749  lea     rcx, [rsp+0E8h+var_68]
0x180070751  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180070756  nop
0x180070757  test    r14b, bl
0x18007075a  jz      short loc_180070769
0x18007075c  lea     rcx, [rsp+0E8h+var_48]
0x180070764  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180070769  test    sil, sil
0x18007076c  jz      loc_1800708A2
0x180070772  lea     rdx, aDomain; "domain"
0x180070779  lea     rcx, [rsp+0E8h+var_48]
0x180070781  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180070786  nop
0x180070787  lea     rdx, [rsp+0E8h+var_48]
0x18007078f  lea     rcx, [rsp+0E8h+var_88]
0x180070794  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180070799  lea     rbx, [rdi+50h]
0x18007079d  mov     rdx, rax
0x1800707a0  mov     rcx, rbx
0x1800707a3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800707a8  nop
0x1800707a9  lea     rcx, [rsp+0E8h+var_48]
0x1800707b1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800707b6  mov     r8, r14
0x1800707b9  lea     rdx, asc_1802AC2D0; "/"
0x1800707c0  mov     rcx, rbx; Src
0x1800707c3  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800707c8  mov     rdx, rax
0x1800707cb  mov     rcx, rbx
0x1800707ce  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800707d3  lea     rdx, aIntent; "intent"
0x1800707da  lea     rcx, [rsp+0E8h+var_48]
0x1800707e2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800707e7  nop
0x1800707e8  lea     rdx, [rsp+0E8h+var_48]
0x1800707f0  lea     rcx, [rsp+0E8h+var_88]
0x1800707f5  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x1800707fa  mov     r8, [rax+10h]
0x1800707fe  cmp     qword ptr [rax+18h], 7
0x180070803  jbe     short loc_180070808
0x180070805  mov     rax, [rax]
0x180070808  mov     rdx, rax
0x18007080b  mov     rcx, rbx; Src
0x18007080e  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180070813  mov     rdx, rax
0x180070816  mov     rcx, rbx
0x180070819  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18007081e  nop
0x18007081f  lea     rcx, [rsp+0E8h+var_48]
0x180070827  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007082c  lea     rdx, [rdi+70h]
0x180070830  lea     rcx, [rsp+0E8h+var_88]
0x180070835  call    ActionUriFromProperties
0x18007083a  mov     ebx, eax
0x18007083c  test    eax, eax
0x18007083e  jns     short loc_1800708A2
0x180070840  mov     rcx, [rsp+0E8h]; this
0x180070848  mov     r9d, eax; char *
0x18007084b  lea     r8, aOnecoreuapEndu_346; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180070852  mov     edx, 0ADh; void *
0x180070857  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007085c  nop
0x18007085d  lea     rcx, [rsp+0E8h+var_88]
0x180070862  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x180070867  nop
0x180070868  mov     rcx, [rsp+0E8h+var_98]; pv
0x18007086d  mov     [rsp+0E8h+var_98], r15
0x180070872  test    rcx, rcx
0x180070875  jz      short loc_18007087E
0x180070877  call    cs:__imp_CoTaskMemFree
0x18007087d  nop
0x18007087e  mov     rcx, [rsp+0E8h+pv]; pv
0x180070883  mov     [rsp+0E8h+pv], r15
0x180070888  test    rcx, rcx
0x18007088b  jz      short loc_180070894
0x18007088d  call    cs:__imp_CoTaskMemFree
0x180070893  nop
0x180070894  lea     rcx, [rsp+0E8h+var_A0]
0x180070899  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x18007089e  mov     eax, ebx
0x1800708a0  jmp     short loc_1800708EB
0x1800708a2  lea     rcx, [rsp+0E8h+var_88]
0x1800708a7  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1800708ac  nop
0x1800708ad  mov     rcx, [rsp+0E8h+var_98]; pv
0x1800708b2  mov     [rsp+0E8h+var_98], r15
0x1800708b7  test    rcx, rcx
0x1800708ba  jz      short loc_1800708C3
0x1800708bc  call    cs:__imp_CoTaskMemFree
0x1800708c2  nop
0x1800708c3  mov     rcx, [rsp+0E8h+pv]; pv
0x1800708c8  mov     [rsp+0E8h+pv], r15
0x1800708cd  test    rcx, rcx
0x1800708d0  jz      short loc_1800708D9
0x1800708d2  call    cs:__imp_CoTaskMemFree
  ... truncated ...
```
