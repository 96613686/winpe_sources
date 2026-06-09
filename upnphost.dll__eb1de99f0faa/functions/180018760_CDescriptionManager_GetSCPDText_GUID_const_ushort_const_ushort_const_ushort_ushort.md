# CDescriptionManager::GetSCPDText(_GUID const &,ushort const *,ushort const *,ushort * *,ushort * *)

- ea: `0x180018760`
- end: `0x180018b38`
- name: `?GetSCPDText@CDescriptionManager@@UEAAJAEBU_GUID@@PEBG1PEAPEAG2@Z`
- size: `984`
- prototype: `__int64 __fastcall(CDescriptionManager *this, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x180010660`
- `0x18001169c`
- `0x1800117bc`
- `0x1800117d0`
- `0x180013180`
- `0x18001347c`
- `0x180015ab0`
- `0x180015d90`
- `0x180018760`
- `0x18001ab90`
- `0x18002aa74`
- `0x1800300e4`
- `0x180038ce4`
- `0x180039780`
- `0x18003a560`
- `0x180055010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018809`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018876`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018a0b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018809`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018876`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018a0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018abc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018abc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001894c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001895f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018a8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001894c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001895f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018a8d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001892f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001892f`
- `OLEAUT32!__imp_SysFreeString` at `0x180018ae6`
- `OLEAUT32!__imp_SysFreeString` at `0x180018ae6`

## string_xrefs

- `0x180018851`: `//ddd:service/ddd:SCPDURL[../ddd:serviceId = '`
- `0x180018978`: `//ddd:service/ddd:serviceType[../ddd:serviceId = '`

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
  __int64 v26; // [rsp+68h] [rbp-21h] BYREF
  LPCCH lpMultiByteStr; // [rsp+70h] [rbp-19h] BYREF
  __int64 v28; // [rsp+78h] [rbp-11h] BYREF
  struct _GUID v29; // [rsp+80h] [rbp-9h] BYREF

  if ( !a3 || !a4 || !a5 || !a6 )
    return 2147500035LL;
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v26);
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v28);
  pv = v9;
  v10 = (unsigned __int16 *)(unsigned int)v9;
  IsAllowedCOMCallLocality = HrIsAllowedCOMCallLocality((unsigned int)((_DWORD)v9 + 1));
  if ( IsAllowedCOMCallLocality >= 0 )
  {
    IsAllowedCOMCallLocality = CDescriptionManager::HrLoadDocumentAndRootNode(this, a2, &v26);
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
            IsAllowedCOMCallLocality = HrSelectNode(Block, &v26, &pv);
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
          ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&pv);
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
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v28);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v26);
  return (unsigned int)IsAllowedCOMCallLocality;
}

```

## disassembly

```asm
0x180018760  mov     [rsp-8+arg_10], rbx
0x180018765  push    rbp
0x180018766  push    rsi
0x180018767  push    rdi
0x180018768  push    r12
0x18001876a  push    r13
0x18001876c  push    r14
0x18001876e  push    r15
0x180018770  lea     rbp, [rsp-17h]
0x180018775  sub     rsp, 0A0h
0x18001877c  mov     rax, cs:__security_cookie
0x180018783  xor     rax, rsp
0x180018786  mov     [rbp+47h+var_40], rax
0x18001878a  mov     r14, [rbp+47h+arg_20]
0x18001878e  mov     rbx, rdx
0x180018791  mov     r12, [rbp+47h+arg_28]
0x180018795  xor     edx, edx
0x180018797  mov     r15, r9
0x18001879a  mov     r13, rcx
0x18001879d  test    r8, r8
0x1800187a0  jz      loc_18001884A
0x1800187a6  test    r9, r9
0x1800187a9  jz      loc_18001884A
0x1800187af  test    r14, r14
0x1800187b2  jz      loc_18001884A
0x1800187b8  test    r12, r12
0x1800187bb  jz      loc_18001884A
0x1800187c1  lea     rcx, [rbp+47h+var_68]; void *
0x1800187c5  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x1800187ca  lea     rcx, [rbp+47h+var_58]; void *
0x1800187ce  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x1800187d3  lea     ecx, [rdx+1]
0x1800187d6  mov     [rbp+47h+pv], rdx
0x1800187da  mov     edi, edx
0x1800187dc  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x1800187e1  mov     esi, eax
0x1800187e3  test    eax, eax
0x1800187e5  js      short loc_1800187FE
0x1800187e7  lea     r8, [rbp+47h+var_68]
0x1800187eb  mov     rdx, rbx
0x1800187ee  mov     rcx, r13
0x1800187f1  call    ?HrLoadDocumentAndRootNode@CDescriptionManager@@AEAAJAEBU_GUID@@AEAV?$SmartComPtr@UIXMLDOMNode@@@@@Z; CDescriptionManager::HrLoadDocumentAndRootNode(_GUID const &,SmartComPtr<IXMLDOMNode> &)
0x1800187f6  xor     ebx, ebx
0x1800187f8  mov     esi, eax
0x1800187fa  test    eax, eax
0x1800187fc  jns     short loc_180018851
0x1800187fe  test    esi, esi
0x180018800  jnz     loc_180018AFA
0x180018806  mov     rcx, rdi; Block
0x180018809  call    cs:__imp_free
0x18001880f  lea     rcx, [rbp+47h+var_58]
0x180018813  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180018818  lea     rcx, [rbp+47h+var_68]
0x18001881c  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180018821  mov     eax, esi
0x180018823  mov     rcx, [rbp+47h+var_40]
0x180018827  xor     rcx, rsp; StackCookie
0x18001882a  call    __security_check_cookie
0x18001882f  mov     rbx, [rsp+0D0h+arg_10]
0x180018837  add     rsp, 0A0h
0x18001883e  pop     r15
0x180018840  pop     r14
0x180018842  pop     r13
0x180018844  pop     r12
0x180018846  pop     rdi
0x180018847  pop     rsi
0x180018848  pop     rbp
0x180018849  retn
0x18001884a  mov     eax, 80004003h
0x18001884f  jmp     short loc_180018823
0x180018851  lea     rdx, aDddServiceDddS_0; "//ddd:service/ddd:SCPDURL[../ddd:servic"...
0x180018858  mov     [rbp+47h+Block], rbx
0x18001885c  lea     rcx, [rbp+47h+Block]; this
0x180018860  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x180018865  mov     esi, eax
0x180018867  test    eax, eax
0x180018869  jns     loc_180018A33
0x18001886f  mov     rbx, [rbp+47h+Block]
0x180018873  mov     rcx, rbx; Block
0x180018876  call    cs:__imp_free
0x18001887c  xor     ebx, ebx
0x18001887e  test    esi, esi
0x180018880  js      loc_180018800
0x180018886  xorps   xmm0, xmm0
0x180018889  lea     rdx, [rbp+47h+var_50]; struct _GUID *
0x18001888d  mov     rcx, rdi; unsigned __int16 *
0x180018890  movups  xmmword ptr [rbp+47h+var_50.Data1], xmm0
0x180018894  call    ?HrContentURLToGUID@@YAJPEBGAEAU_GUID@@@Z; HrContentURLToGUID(ushort const *,_GUID &)
0x180018899  mov     esi, eax
0x18001889b  test    eax, eax
0x18001889d  js      loc_1800187FE
0x1800188a3  lea     rdx, [rbp+47h+lpMultiByteStr]
0x1800188a7  mov     dword ptr [rbp+47h+Block], ebx
0x1800188aa  mov     [rsp+0D0h+var_98], rdx
0x1800188af  lea     rcx, [r13+8]
0x1800188b3  mov     rax, [rcx]
0x1800188b6  lea     rdx, [rbp+47h+cbMultiByte]
0x1800188ba  mov     [rsp+0D0h+var_A0], rdx
0x1800188bf  lea     r8, Format
0x1800188c6  lea     rdx, [rbp+47h+pv]
0x1800188ca  mov     [rbp+47h+pv], rbx
0x1800188ce  mov     qword ptr [rsp+0D0h+cchWideChar], rdx
0x1800188d3  xor     r9d, r9d
0x1800188d6  mov     rax, [rax+18h]
0x1800188da  lea     rdx, [rbp+47h+Block]
0x1800188de  mov     [rsp+0D0h+lpWideCharStr], rdx
0x1800188e3  lea     rdx, [rbp+47h+var_50]
0x1800188e7  mov     [rbp+47h+cbMultiByte], ebx
0x1800188ea  mov     [rbp+47h+lpMultiByteStr], rbx
0x1800188ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188f3  mov     esi, eax
0x1800188f5  test    eax, eax
0x1800188f7  js      loc_1800187FE
0x1800188fd  mov     ecx, [rbp+47h+cbMultiByte]
0x180018900  lea     edx, [rbx+2]; int
0x180018903  inc     ecx; int
0x180018905  mov     r8, r14; void **
0x180018908  call    ?HrCoTaskMemAllocArray@@YAJJJPEAPEAX@Z; HrCoTaskMemAllocArray(long,long,void * *)
0x18001890d  mov     esi, eax
0x18001890f  test    eax, eax
0x180018911  js      short loc_180018948
0x180018913  mov     r9d, [rbp+47h+cbMultiByte]; cbMultiByte
0x180018917  xor     edx, edx; dwFlags
0x180018919  mov     rax, [r14]
0x18001891c  mov     ecx, 0FDE9h; CodePage
0x180018921  mov     r8, [rbp+47h+lpMultiByteStr]; lpMultiByteStr
0x180018925  mov     [rsp+0D0h+cchWideChar], r9d; cchWideChar
0x18001892a  mov     [rsp+0D0h+lpWideCharStr], rax; lpWideCharStr
0x18001892f  call    cs:__imp_MultiByteToWideChar
0x180018935  test    eax, eax
0x180018937  jz      loc_180018A1F
0x18001893d  movsxd  rdx, [rbp+47h+cbMultiByte]
0x180018941  mov     rcx, [r14]
0x180018944  mov     [rcx+rdx*2], bx
0x180018948  mov     rcx, [rbp+47h+lpMultiByteStr]; pv
0x18001894c  call    cs:__imp_CoTaskMemFree
0x180018952  cmp     dword ptr [rbp+47h+Block], ebx
0x180018955  jg      loc_180018A82
0x18001895b  mov     rcx, [rbp+47h+pv]; pv
0x18001895f  call    cs:__imp_CoTaskMemFree
0x180018965  xor     ebx, ebx
0x180018967  test    esi, esi
0x180018969  js      loc_180018800
0x18001896f  lea     rcx, [rbp+47h+pv]; void *
0x180018973  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180018978  lea     rdx, aDddServiceDddS; "//ddd:service/ddd:serviceType[../ddd:se"...
0x18001897f  mov     [rbp+47h+Block], rbx
0x180018983  lea     rcx, [rbp+47h+Block]; this
0x180018987  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x18001898c  mov     esi, eax
0x18001898e  test    eax, eax
0x180018990  js      loc_180018AF1
0x180018996  mov     rdx, r15; unsigned __int16 *
0x180018999  lea     rcx, [rbp+47h+Block]; this
0x18001899d  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x1800189a2  mov     esi, eax
0x1800189a4  test    eax, eax
0x1800189a6  js      loc_180018AF1
0x1800189ac  lea     rdx, asc_1800601A8; "']"
0x1800189b3  lea     rcx, [rbp+47h+Block]; this
0x1800189b7  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x1800189bc  mov     esi, eax
0x1800189be  test    eax, eax
0x1800189c0  js      loc_180018AF1
0x1800189c6  mov     rbx, [rbp+47h+Block]
0x1800189ca  lea     r8, [rbp+47h+pv]
0x1800189ce  mov     rcx, rbx
0x1800189d1  lea     rdx, [rbp+47h+var_68]
0x1800189d5  call    ?HrSelectNode@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@1@Z; HrSelectNode(ushort const *,SmartComPtr<IXMLDOMNode> &,SmartComPtr<IXMLDOMNode> &)
0x1800189da  xor     r14d, r14d
0x1800189dd  mov     esi, eax
0x1800189df  test    eax, eax
0x1800189e1  js      short loc_180018A08
0x1800189e3  mov     rcx, [rbp+47h+pv]
0x1800189e7  lea     rdx, [rbp+47h+Block]
0x1800189eb  mov     [rbp+47h+Block], r14
0x1800189ef  mov     rax, [rcx]
0x1800189f2  mov     rax, [rax+0D0h]
0x1800189f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189fe  mov     esi, eax
0x180018a00  test    eax, eax
0x180018a02  jns     loc_180018A9F
0x180018a08  mov     rcx, rbx; Block
0x180018a0b  call    cs:__imp_free
0x180018a11  lea     rcx, [rbp+47h+pv]
0x180018a15  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180018a1a  jmp     loc_1800187FE
0x180018a1f  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180018a24  mov     esi, eax
0x180018a26  test    eax, eax
0x180018a28  jns     loc_18001893D
0x180018a2e  jmp     loc_180018948
0x180018a33  mov     rdx, r15; unsigned __int16 *
0x180018a36  lea     rcx, [rbp+47h+Block]; this
0x180018a3a  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x180018a3f  mov     esi, eax
0x180018a41  test    eax, eax
0x180018a43  js      loc_18001886F
0x180018a49  lea     rdx, asc_1800601A8; "']"
0x180018a50  lea     rcx, [rbp+47h+Block]; this
0x180018a54  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x180018a59  mov     esi, eax
0x180018a5b  test    eax, eax
0x180018a5d  js      loc_18001886F
0x180018a63  mov     rbx, [rbp+47h+Block]
0x180018a67  lea     r8, [rbp+47h+pv]
0x180018a6b  mov     rcx, rbx; psz
0x180018a6e  lea     rdx, [rbp+47h+var_68]
0x180018a72  call    ?HrSelectNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAVCUString@@@Z; HrSelectNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString &)
0x180018a77  mov     rdi, [rbp+47h+pv]
0x180018a7b  mov     esi, eax
0x180018a7d  jmp     loc_180018873
0x180018a82  mov     rcx, [rbp+47h+pv]
0x180018a86  movsxd  rax, ebx
0x180018a89  mov     rcx, [rcx+rax*8]; pv
0x180018a8d  call    cs:__imp_CoTaskMemFree
0x180018a93  inc     ebx
0x180018a95  cmp     ebx, dword ptr [rbp+47h+Block]
0x180018a98  jl      short loc_180018A82
0x180018a9a  jmp     loc_18001895B
0x180018a9f  mov     rcx, [rbp+47h+Block]
0x180018aa3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018aa7  inc     rax
0x180018aaa  cmp     [rcx+rax*2], r14w
0x180018aaf  jnz     short loc_180018AA7
0x180018ab1  lea     eax, ds:2[rax*2]
0x180018ab8  mov     ecx, eax; cb
0x180018aba  mov     esi, eax
0x180018abc  call    cs:__imp_CoTaskMemAlloc
0x180018ac2  mov     [r12], rax
0x180018ac6  test    rax, rax
0x180018ac9  jz      short loc_180018ADD
0x180018acb  mov     r8, [rbp+47h+Block]; unsigned __int16 *
0x180018acf  mov     edx, esi; unsigned __int64
0x180018ad1  mov     rcx, rax; unsigned __int16 *
0x180018ad4  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180018ad9  mov     esi, eax
0x180018adb  jmp     short loc_180018AE2
0x180018add  mov     esi, 8007000Eh
0x180018ae2  mov     rcx, [rbp+47h+Block]; bstrString
0x180018ae6  call    cs:__imp_SysFreeString
0x180018aec  jmp     loc_180018A08
0x180018af1  mov     rbx, [rbp+47h+Block]
0x180018af5  jmp     loc_180018A08
0x180018afa  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b01  lea     rax, WPP_GLOBAL_Control
0x180018b08  cmp     rcx, rax
0x180018b0b  jz      loc_180018806
0x180018b11  test    byte ptr [rcx+1Ch], 1
0x180018b15  jz      loc_180018806
0x180018b1b  mov     rcx, [rcx+10h]
0x180018b1f  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x180018b26  mov     edx, 6Ch ; 'l'
0x180018b2b  mov     r9d, esi
0x180018b2e  call    WPP_SF_d
0x180018b33  jmp     loc_180018806
```
