# CDescriptionManager::GetSCPDText(_GUID const &,ushort const *,ushort const *,ushort * *,ushort * *)

- ea: `0x1800042f0`
- end: `0x1800046ff`
- name: `?GetSCPDText@CDescriptionManager@@UEAAJAEBU_GUID@@PEBG1PEAPEAG2@Z`
- size: `1039`
- prototype: `int(CDescriptionManager *__hidden this, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800042f0`
- `0x1800055a8`
- `0x1800056d8`
- `0x1800056f0`
- `0x1800071c0`
- `0x1800074dc`
- `0x180009d50`
- `0x18000a060`
- `0x18000e6a0`
- `0x18000f8a0`
- `0x18002bed8`
- `0x180031718`
- `0x18003b1cc`
- `0x18003bd3c`
- `0x18003cb60`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004399`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000440d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800045ba`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004399`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000440d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800045ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004677`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004677`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800044ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004508`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004642`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800044ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004508`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004642`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800044cc`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800044cc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800046a7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800046a7`

## string_xrefs

- `0x1800043e8`: `//ddd:service/ddd:SCPDURL[../ddd:serviceId = '`
- `0x180004527`: `//ddd:service/ddd:serviceType[../ddd:serviceId = '`

## pseudocode

```c
__int64 __fastcall CDescriptionManager::GetSCPDText(
        CDescriptionManager *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6)
{
  void *v9; // rdx
  unsigned __int16 *v10; // rdi
  int IsAllowedCOMCallLocality; // esi
  bool v12; // zf
  void *v14; // rbx
  int v15; // ebx
  __int64 v16; // rax
  __int64 (__fastcall *v17)(char *, struct _GUID *, const WCHAR *, _QWORD, void **, LPVOID *, int *, LPCCH *); // rax
  void *v18; // rbx
  int v19; // eax
  __int64 v20; // rax
  SIZE_T v21; // rsi
  unsigned __int16 *v22; // rax
  void *Block; // [rsp+50h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-31h] BYREF
  int cbMultiByte; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v26[8]; // [rsp+68h] [rbp-21h] BYREF
  LPCCH lpMultiByteStr; // [rsp+70h] [rbp-19h] BYREF
  _BYTE v28[8]; // [rsp+78h] [rbp-11h] BYREF
  struct _GUID v29; // [rsp+80h] [rbp-9h] BYREF

  if ( !a3 || !a4 || !a5 || !a6 )
    return 2147500035LL;
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(v26);
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(v28);
  pv = v9;
  v10 = (unsigned __int16 *)(unsigned int)v9;
  IsAllowedCOMCallLocality = HrIsAllowedCOMCallLocality((int)v9 + 1);
  if ( IsAllowedCOMCallLocality >= 0 )
  {
    IsAllowedCOMCallLocality = CDescriptionManager::HrLoadDocumentAndRootNode(this, a2, v26);
    if ( IsAllowedCOMCallLocality >= 0 )
    {
      Block = 0;
      IsAllowedCOMCallLocality = CUString::HrAssign(
                                   (CUString *)&Block,
                                   L"//ddd:service/ddd:SCPDURL[../ddd:serviceId = '");
      if ( IsAllowedCOMCallLocality < 0
        || (IsAllowedCOMCallLocality = CUString::HrAppend((CUString *)&Block, a4), IsAllowedCOMCallLocality < 0)
        || (IsAllowedCOMCallLocality = CUString::HrAppend((CUString *)&Block, L"']"), IsAllowedCOMCallLocality < 0) )
      {
        v14 = Block;
      }
      else
      {
        v14 = Block;
        v19 = HrSelectNodeText((OLECHAR *)Block);
        v10 = (unsigned __int16 *)pv;
        IsAllowedCOMCallLocality = v19;
      }
      free(v14);
      v15 = 0;
      v12 = IsAllowedCOMCallLocality == 0;
      if ( IsAllowedCOMCallLocality < 0 )
        goto LABEL_8;
      v29 = 0;
      IsAllowedCOMCallLocality = HrContentURLToGUID(v10, &v29);
      if ( IsAllowedCOMCallLocality >= 0 )
      {
        LODWORD(Block) = 0;
        v16 = *((_QWORD *)this + 1);
        pv = 0;
        v17 = *(__int64 (__fastcall **)(char *, struct _GUID *, const WCHAR *, _QWORD, void **, LPVOID *, int *, LPCCH *))(v16 + 24);
        cbMultiByte = 0;
        lpMultiByteStr = 0;
        IsAllowedCOMCallLocality = v17((char *)this + 8, &v29, &Format, 0, &Block, &pv, &cbMultiByte, &lpMultiByteStr);
        if ( IsAllowedCOMCallLocality >= 0 )
        {
          IsAllowedCOMCallLocality = HrCoTaskMemAllocArray(cbMultiByte + 1, 2, (void **)a5);
          if ( IsAllowedCOMCallLocality >= 0 )
          {
            if ( MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, cbMultiByte, *a5, cbMultiByte)
              || (IsAllowedCOMCallLocality = HrFromLastWin32Error(), IsAllowedCOMCallLocality >= 0) )
            {
              (*a5)[cbMultiByte] = 0;
            }
          }
          CoTaskMemFree((LPVOID)lpMultiByteStr);
          if ( (int)Block > 0 )
          {
            do
              CoTaskMemFree(*((LPVOID *)pv + v15++));
            while ( v15 < (int)Block );
          }
          CoTaskMemFree(pv);
          v12 = IsAllowedCOMCallLocality == 0;
          if ( IsAllowedCOMCallLocality < 0 )
            goto LABEL_8;
          SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&pv);
          Block = 0;
          IsAllowedCOMCallLocality = CUString::HrAssign(
                                       (CUString *)&Block,
                                       L"//ddd:service/ddd:serviceType[../ddd:serviceId = '");
          if ( IsAllowedCOMCallLocality < 0
            || (IsAllowedCOMCallLocality = CUString::HrAppend((CUString *)&Block, a4), IsAllowedCOMCallLocality < 0)
            || (IsAllowedCOMCallLocality = CUString::HrAppend((CUString *)&Block, L"']"), IsAllowedCOMCallLocality < 0) )
          {
            v18 = Block;
          }
          else
          {
            v18 = Block;
            IsAllowedCOMCallLocality = HrSelectNode(Block, v26, &pv);
            if ( IsAllowedCOMCallLocality >= 0 )
            {
              Block = 0;
              IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(LPVOID, void **))(*(_QWORD *)pv + 208LL))(
                                           pv,
                                           &Block);
              if ( IsAllowedCOMCallLocality >= 0 )
              {
                v20 = -1;
                do
                  ++v20;
                while ( *((_WORD *)Block + v20) );
                v21 = (unsigned int)(2 * v20 + 2);
                v22 = (unsigned __int16 *)CoTaskMemAlloc(v21);
                *a6 = v22;
                if ( v22 )
                  IsAllowedCOMCallLocality = StringCbCopyW(v22, (unsigned int)v21, (const unsigned __int16 *)Block);
                else
                  IsAllowedCOMCallLocality = -2147024882;
                SysFreeString((BSTR)Block);
              }
            }
          }
          free(v18);
          ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(&pv);
        }
      }
    }
  }
  v12 = IsAllowedCOMCallLocality == 0;
LABEL_8:
  if ( !v12 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      108,
      WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids,
      (unsigned int)IsAllowedCOMCallLocality);
  free(v10);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(v28);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(v26);
  return (unsigned int)IsAllowedCOMCallLocality;
}

```

## disassembly

```asm
0x1800042f0  mov     [rsp-8+arg_10], rbx
0x1800042f5  push    rbp
0x1800042f6  push    rsi
0x1800042f7  push    rdi
0x1800042f8  push    r12
0x1800042fa  push    r13
0x1800042fc  push    r14
0x1800042fe  push    r15
0x180004300  lea     rbp, [rsp-17h]
0x180004305  sub     rsp, 0A0h
0x18000430c  mov     rax, cs:__security_cookie
0x180004313  xor     rax, rsp
0x180004316  mov     [rbp+47h+var_40], rax
0x18000431a  mov     r14, [rbp+47h+arg_20]
0x18000431e  mov     rbx, rdx
0x180004321  mov     r12, [rbp+47h+arg_28]
0x180004325  xor     edx, edx
0x180004327  mov     r15, r9
0x18000432a  mov     r13, rcx
0x18000432d  test    r8, r8
0x180004330  jz      loc_1800043E1
0x180004336  test    r9, r9
0x180004339  jz      loc_1800043E1
0x18000433f  test    r14, r14
0x180004342  jz      loc_1800043E1
0x180004348  test    r12, r12
0x18000434b  jz      loc_1800043E1
0x180004351  lea     rcx, [rbp+47h+var_68]; void *
0x180004355  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18000435a  lea     rcx, [rbp+47h+var_58]; void *
0x18000435e  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180004363  lea     ecx, [rdx+1]
0x180004366  mov     [rbp+47h+pv], rdx
0x18000436a  mov     edi, edx
0x18000436c  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x180004371  mov     esi, eax
0x180004373  test    eax, eax
0x180004375  js      short loc_18000438E
0x180004377  lea     r8, [rbp+47h+var_68]
0x18000437b  mov     rdx, rbx
0x18000437e  mov     rcx, r13
0x180004381  call    ?HrLoadDocumentAndRootNode@CDescriptionManager@@AEAAJAEBU_GUID@@AEAV?$SmartComPtr@UIXMLDOMNode@@@@@Z; CDescriptionManager::HrLoadDocumentAndRootNode(_GUID const &,SmartComPtr<IXMLDOMNode> &)
0x180004386  xor     ebx, ebx
0x180004388  mov     esi, eax
0x18000438a  test    eax, eax
0x18000438c  jns     short loc_1800043E8
0x18000438e  test    esi, esi
0x180004390  jnz     loc_1800046C1
0x180004396  mov     rcx, rdi; Block
0x180004399  call    cs:__imp_free
0x1800043a0  nop     dword ptr [rax+rax+00h]
0x1800043a5  lea     rcx, [rbp+47h+var_58]
0x1800043a9  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x1800043ae  lea     rcx, [rbp+47h+var_68]
0x1800043b2  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x1800043b7  mov     eax, esi
0x1800043b9  mov     rcx, [rbp+47h+var_40]
0x1800043bd  xor     rcx, rsp; StackCookie
0x1800043c0  call    __security_check_cookie
0x1800043c5  mov     rbx, [rsp+0D0h+arg_10]
0x1800043cd  add     rsp, 0A0h
0x1800043d4  pop     r15
0x1800043d6  pop     r14
0x1800043d8  pop     r13
0x1800043da  pop     r12
0x1800043dc  pop     rdi
0x1800043dd  pop     rsi
0x1800043de  pop     rbp
0x1800043df  retn
0x1800043e1  mov     eax, 80004003h
0x1800043e6  jmp     short loc_1800043B9
0x1800043e8  lea     rdx, aDddServiceDddS_0; "//ddd:service/ddd:SCPDURL[../ddd:servic"...
0x1800043ef  mov     [rbp+47h+Block], rbx
0x1800043f3  lea     rcx, [rbp+47h+Block]; this
0x1800043f7  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x1800043fc  mov     esi, eax
0x1800043fe  test    eax, eax
0x180004400  jns     loc_1800045E8
0x180004406  mov     rbx, [rbp+47h+Block]
0x18000440a  mov     rcx, rbx; Block
0x18000440d  call    cs:__imp_free
0x180004414  nop     dword ptr [rax+rax+00h]
0x180004419  xor     ebx, ebx
0x18000441b  test    esi, esi
0x18000441d  js      loc_180004390
0x180004423  xorps   xmm0, xmm0
0x180004426  lea     rdx, [rbp+47h+var_50]; struct _GUID *
0x18000442a  mov     rcx, rdi; unsigned __int16 *
0x18000442d  movups  xmmword ptr [rbp+47h+var_50.Data1], xmm0
0x180004431  call    ?HrContentURLToGUID@@YAJPEBGAEAU_GUID@@@Z; HrContentURLToGUID(ushort const *,_GUID &)
0x180004436  mov     esi, eax
0x180004438  test    eax, eax
0x18000443a  js      loc_18000438E
0x180004440  lea     rdx, [rbp+47h+lpMultiByteStr]
0x180004444  mov     dword ptr [rbp+47h+Block], ebx
0x180004447  mov     [rsp+0D0h+var_98], rdx
0x18000444c  lea     rcx, [r13+8]
0x180004450  mov     rax, [rcx]
0x180004453  lea     rdx, [rbp+47h+cbMultiByte]
0x180004457  mov     [rsp+0D0h+var_A0], rdx
0x18000445c  lea     r8, Format
0x180004463  lea     rdx, [rbp+47h+pv]
0x180004467  mov     [rbp+47h+pv], rbx
0x18000446b  mov     qword ptr [rsp+0D0h+cchWideChar], rdx
0x180004470  xor     r9d, r9d
0x180004473  mov     rax, [rax+18h]
0x180004477  lea     rdx, [rbp+47h+Block]
0x18000447b  mov     [rsp+0D0h+lpWideCharStr], rdx
0x180004480  lea     rdx, [rbp+47h+var_50]
0x180004484  mov     [rbp+47h+cbMultiByte], ebx
0x180004487  mov     [rbp+47h+lpMultiByteStr], rbx
0x18000448b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004490  mov     esi, eax
0x180004492  test    eax, eax
0x180004494  js      loc_18000438E
0x18000449a  mov     ecx, [rbp+47h+cbMultiByte]
0x18000449d  lea     edx, [rbx+2]; int
0x1800044a0  inc     ecx; int
0x1800044a2  mov     r8, r14; void **
0x1800044a5  call    ?HrCoTaskMemAllocArray@@YAJJJPEAPEAX@Z; HrCoTaskMemAllocArray(long,long,void * *)
0x1800044aa  mov     esi, eax
0x1800044ac  test    eax, eax
0x1800044ae  js      short loc_1800044EB
0x1800044b0  mov     r9d, [rbp+47h+cbMultiByte]; cbMultiByte
0x1800044b4  xor     edx, edx; dwFlags
0x1800044b6  mov     rax, [r14]
0x1800044b9  mov     ecx, 0FDE9h; CodePage
0x1800044be  mov     r8, [rbp+47h+lpMultiByteStr]; lpMultiByteStr
0x1800044c2  mov     [rsp+0D0h+cchWideChar], r9d; cchWideChar
0x1800044c7  mov     [rsp+0D0h+lpWideCharStr], rax; lpWideCharStr
0x1800044cc  call    cs:__imp_MultiByteToWideChar
0x1800044d3  nop     dword ptr [rax+rax+00h]
0x1800044d8  test    eax, eax
0x1800044da  jz      loc_1800045D4
0x1800044e0  movsxd  rdx, [rbp+47h+cbMultiByte]
0x1800044e4  mov     rcx, [r14]
0x1800044e7  mov     [rcx+rdx*2], bx
0x1800044eb  mov     rcx, [rbp+47h+lpMultiByteStr]; pv
0x1800044ef  call    cs:__imp_CoTaskMemFree
0x1800044f6  nop     dword ptr [rax+rax+00h]
0x1800044fb  cmp     dword ptr [rbp+47h+Block], ebx
0x1800044fe  jg      loc_180004637
0x180004504  mov     rcx, [rbp+47h+pv]; pv
0x180004508  call    cs:__imp_CoTaskMemFree
0x18000450f  nop     dword ptr [rax+rax+00h]
0x180004514  xor     ebx, ebx
0x180004516  test    esi, esi
0x180004518  js      loc_180004390
0x18000451e  lea     rcx, [rbp+47h+pv]; void *
0x180004522  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180004527  lea     rdx, aDddServiceDddS; "//ddd:service/ddd:serviceType[../ddd:se"...
0x18000452e  mov     [rbp+47h+Block], rbx
0x180004532  lea     rcx, [rbp+47h+Block]; this
0x180004536  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x18000453b  mov     esi, eax
0x18000453d  test    eax, eax
0x18000453f  js      loc_1800046B8
0x180004545  mov     rdx, r15; unsigned __int16 *
0x180004548  lea     rcx, [rbp+47h+Block]; this
0x18000454c  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x180004551  mov     esi, eax
0x180004553  test    eax, eax
0x180004555  js      loc_1800046B8
0x18000455b  lea     rdx, asc_180063968; "']"
0x180004562  lea     rcx, [rbp+47h+Block]; this
0x180004566  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x18000456b  mov     esi, eax
0x18000456d  test    eax, eax
0x18000456f  js      loc_1800046B8
0x180004575  mov     rbx, [rbp+47h+Block]
0x180004579  lea     r8, [rbp+47h+pv]
0x18000457d  mov     rcx, rbx
0x180004580  lea     rdx, [rbp+47h+var_68]
0x180004584  call    ?HrSelectNode@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@1@Z; HrSelectNode(ushort const *,SmartComPtr<IXMLDOMNode> &,SmartComPtr<IXMLDOMNode> &)
0x180004589  xor     r14d, r14d
0x18000458c  mov     esi, eax
0x18000458e  test    eax, eax
0x180004590  js      short loc_1800045B7
0x180004592  mov     rcx, [rbp+47h+pv]
0x180004596  lea     rdx, [rbp+47h+Block]
0x18000459a  mov     [rbp+47h+Block], r14
0x18000459e  mov     rax, [rcx]
0x1800045a1  mov     rax, [rax+0D0h]
0x1800045a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045ad  mov     esi, eax
0x1800045af  test    eax, eax
0x1800045b1  jns     loc_18000465A
0x1800045b7  mov     rcx, rbx; Block
0x1800045ba  call    cs:__imp_free
0x1800045c1  nop     dword ptr [rax+rax+00h]
0x1800045c6  lea     rcx, [rbp+47h+pv]
0x1800045ca  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x1800045cf  jmp     loc_18000438E
0x1800045d4  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800045d9  mov     esi, eax
0x1800045db  test    eax, eax
0x1800045dd  jns     loc_1800044E0
0x1800045e3  jmp     loc_1800044EB
0x1800045e8  mov     rdx, r15; unsigned __int16 *
0x1800045eb  lea     rcx, [rbp+47h+Block]; this
0x1800045ef  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x1800045f4  mov     esi, eax
0x1800045f6  test    eax, eax
0x1800045f8  js      loc_180004406
0x1800045fe  lea     rdx, asc_180063968; "']"
0x180004605  lea     rcx, [rbp+47h+Block]; this
0x180004609  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x18000460e  mov     esi, eax
0x180004610  test    eax, eax
0x180004612  js      loc_180004406
0x180004618  mov     rbx, [rbp+47h+Block]
0x18000461c  lea     r8, [rbp+47h+pv]
0x180004620  mov     rcx, rbx; psz
0x180004623  lea     rdx, [rbp+47h+var_68]
0x180004627  call    ?HrSelectNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAVCUString@@@Z; HrSelectNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString &)
0x18000462c  mov     rdi, [rbp+47h+pv]
0x180004630  mov     esi, eax
0x180004632  jmp     loc_18000440A
0x180004637  mov     rcx, [rbp+47h+pv]
0x18000463b  movsxd  rax, ebx
0x18000463e  mov     rcx, [rcx+rax*8]; pv
0x180004642  call    cs:__imp_CoTaskMemFree
0x180004649  nop     dword ptr [rax+rax+00h]
0x18000464e  inc     ebx
0x180004650  cmp     ebx, dword ptr [rbp+47h+Block]
0x180004653  jl      short loc_180004637
0x180004655  jmp     loc_180004504
0x18000465a  mov     rcx, [rbp+47h+Block]
0x18000465e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004662  inc     rax
0x180004665  cmp     [rcx+rax*2], r14w
0x18000466a  jnz     short loc_180004662
0x18000466c  lea     eax, ds:2[rax*2]
0x180004673  mov     ecx, eax; cb
0x180004675  mov     esi, eax
0x180004677  call    cs:__imp_CoTaskMemAlloc
0x18000467e  nop     dword ptr [rax+rax+00h]
0x180004683  mov     [r12], rax
0x180004687  test    rax, rax
0x18000468a  jz      short loc_18000469E
0x18000468c  mov     r8, [rbp+47h+Block]; unsigned __int16 *
0x180004690  mov     edx, esi; unsigned __int64
0x180004692  mov     rcx, rax; unsigned __int16 *
0x180004695  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18000469a  mov     esi, eax
0x18000469c  jmp     short loc_1800046A3
0x18000469e  mov     esi, 8007000Eh
0x1800046a3  mov     rcx, [rbp+47h+Block]; bstrString
0x1800046a7  call    cs:__imp_SysFreeString
0x1800046ae  nop     dword ptr [rax+rax+00h]
0x1800046b3  jmp     loc_1800045B7
0x1800046b8  mov     rbx, [rbp+47h+Block]
0x1800046bc  jmp     loc_1800045B7
0x1800046c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046c8  lea     rax, WPP_GLOBAL_Control
0x1800046cf  cmp     rcx, rax
0x1800046d2  jz      loc_180004396
0x1800046d8  test    byte ptr [rcx+1Ch], 1
0x1800046dc  jz      loc_180004396
0x1800046e2  mov     rcx, [rcx+10h]
0x1800046e6  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x1800046ed  mov     edx, 6Ch ; 'l'
0x1800046f2  mov     r9d, esi
0x1800046f5  call    WPP_SF_d
0x1800046fa  jmp     loc_180004396
```
