# CDescriptionManager::GetUDNs(_GUID const &,long *,ushort * * *)

- ea: `0x1800254b0`
- end: `0x18002579a`
- name: `?GetUDNs@CDescriptionManager@@UEAAJAEBU_GUID@@PEAJPEAPEAPEAG@Z`
- size: `746`
- prototype: `__int64 __fastcall(CDescriptionManager *__hidden this, const struct _GUID *, int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003e08`
- `0x1800055a8`
- `0x1800056d8`
- `0x1800056f0`
- `0x1800071c0`
- `0x1800254b0`
- `0x180025fa4`
- `0x180026420`
- `0x18003b1cc`
- `0x18003d4b0`
- `0x180042774`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025691`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025691`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025559`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025559`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025581`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025581`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800255ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800255e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800255ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800255e0`

## pseudocode

```c
__int64 __fastcall CDescriptionManager::GetUDNs(
        CDescriptionManager *this,
        const struct _GUID *a2,
        int *a3,
        unsigned __int16 ***a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // r12
  signed int IsAllowedCOMCallLocality; // ebx
  void *v10; // rdi
  int v11; // eax
  int i; // esi
  void *v14; // rcx
  unsigned __int64 v15; // rax
  int v16; // esi
  _BYTE v17[8]; // [rsp+20h] [rbp-20h] BYREF
  __int64 v18; // [rsp+28h] [rbp-18h] BYREF
  void *Block; // [rsp+30h] [rbp-10h] BYREF
  _BYTE v20[8]; // [rsp+38h] [rbp-8h] BYREF
  int v21; // [rsp+80h] [rbp+40h] BYREF

  if ( !a3 || !a4 )
    return 2147500035LL;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  ATL::CComSafeDeleteCriticalSection::Lock((CDescriptionManager *)((char *)this + 24));
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(v20);
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v18);
  IsAllowedCOMCallLocality = HrIsAllowedCOMCallLocality(1);
  if ( IsAllowedCOMCallLocality >= 0 )
  {
    IsAllowedCOMCallLocality = CDescriptionManager::HrLoadDocumentAndRootNode(this, a2, v20);
    if ( IsAllowedCOMCallLocality >= 0 )
      IsAllowedCOMCallLocality = HrSelectNodes(L"//ddd:UDN", v20, &v18);
  }
  v21 = 0;
  if ( IsAllowedCOMCallLocality >= 0 )
  {
    IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 64LL))(v18, &v21);
    if ( IsAllowedCOMCallLocality >= 0 )
    {
      v10 = 0;
      if ( v21 < 0 )
      {
        IsAllowedCOMCallLocality = -2147024882;
      }
      else
      {
        v15 = 8LL * (unsigned int)v21;
        if ( v15 <= 0xFFFFFFFF )
        {
          v10 = CoTaskMemAlloc((unsigned int)v15);
          IsAllowedCOMCallLocality = v10 == 0 ? 0x8007000E : 0;
          if ( v10 )
          {
LABEL_9:
            if ( IsAllowedCOMCallLocality >= 0 )
            {
              memset_0(v10, 0, 8LL * v21);
              v16 = 0;
              while ( IsAllowedCOMCallLocality >= 0 )
              {
                v11 = v21;
                if ( v16 >= v21 )
                  goto LABEL_6;
                SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(v17);
                if ( (*(unsigned int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v18 + 72LL))(v18, v17) )
                {
                  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(v17);
                  v11 = v21;
                  goto LABEL_6;
                }
                Block = 0;
                IsAllowedCOMCallLocality = HrGetNodeText(v17, &Block);
                if ( IsAllowedCOMCallLocality >= 0 )
                  IsAllowedCOMCallLocality = CUString::HrGetCOM((CUString *)&Block, (unsigned __int16 **)v10 + v16);
                ++v16;
                free(Block);
                ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(v17);
              }
            }
            if ( v10 )
            {
              for ( i = 0; i < v21; ++i )
              {
                v14 = (void *)*((_QWORD *)v10 + i);
                if ( v14 )
                  CoTaskMemFree(v14);
              }
              CoTaskMemFree(v10);
            }
            goto LABEL_5;
          }
        }
        else
        {
          IsAllowedCOMCallLocality = -2147024362;
        }
      }
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_75c351f6869f3647f61a30e7f530184a_Traceguids,
          (unsigned int)IsAllowedCOMCallLocality);
      goto LABEL_9;
    }
  }
LABEL_5:
  v10 = 0;
  v11 = 0;
  v21 = 0;
LABEL_6:
  *a3 = v11;
  *a4 = (unsigned __int16 **)v10;
  if ( IsAllowedCOMCallLocality
    && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      106,
      WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids,
      (unsigned int)IsAllowedCOMCallLocality);
  }
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(&v18);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(v20);
  LeaveCriticalSection(v8);
  return (unsigned int)IsAllowedCOMCallLocality;
}

```

## disassembly

```asm
0x1800254b0  mov     [rsp-28h+arg_0], rbx
0x1800254b5  mov     [rsp-28h+arg_8], rsi
0x1800254ba  push    rbp
0x1800254bb  push    rdi
0x1800254bc  push    r12
0x1800254be  push    r14
0x1800254c0  push    r15
0x1800254c2  mov     rbp, rsp
0x1800254c5  sub     rsp, 40h
0x1800254c9  mov     r14, r9
0x1800254cc  mov     r15, r8
0x1800254cf  mov     rsi, rdx
0x1800254d2  mov     rdi, rcx
0x1800254d5  test    r8, r8
0x1800254d8  jz      loc_180025790
0x1800254de  test    r9, r9
0x1800254e1  jz      loc_180025790
0x1800254e7  lea     r12, [rcx+18h]
0x1800254eb  mov     rcx, r12; this
0x1800254ee  call    ?Lock@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Lock(void)
0x1800254f3  lea     rcx, [rbp+var_8]; void *
0x1800254f7  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x1800254fc  lea     rcx, [rbp+var_18]; void *
0x180025500  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180025505  mov     ecx, 1
0x18002550a  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18002550f  mov     ebx, eax
0x180025511  test    eax, eax
0x180025513  jns     loc_1800256BC
0x180025519  mov     [rbp+arg_10], 0
0x180025520  lea     rsi, WPP_GLOBAL_Control
0x180025527  test    ebx, ebx
0x180025529  jns     loc_1800255F1
0x18002552f  xor     edi, edi
0x180025531  xor     eax, eax
0x180025533  mov     [rbp+arg_10], eax
0x180025536  mov     [r15], eax
0x180025539  mov     [r14], rdi
0x18002553c  test    ebx, ebx
0x18002553e  jnz     loc_180025752
0x180025544  lea     rcx, [rbp+var_18]
0x180025548  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18002554d  lea     rcx, [rbp+var_8]
0x180025551  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180025556  mov     rcx, r12; lpCriticalSection
0x180025559  call    cs:__imp_LeaveCriticalSection
0x180025560  nop     dword ptr [rax+rax+00h]
0x180025565  mov     eax, ebx
0x180025567  mov     rbx, [rsp+40h+arg_0]
0x18002556c  mov     rsi, [rsp+40h+arg_8]
0x180025571  add     rsp, 40h
0x180025575  pop     r15
0x180025577  pop     r14
0x180025579  pop     r12
0x18002557b  pop     rdi
0x18002557c  pop     rbp
0x18002557d  retn
0x18002557f  mov     ecx, eax; cb
0x180025581  call    cs:__imp_CoTaskMemAlloc
0x180025588  nop     dword ptr [rax+rax+00h]
0x18002558d  mov     rdi, rax
0x180025590  neg     rax
0x180025593  sbb     ebx, ebx
0x180025595  not     ebx
0x180025597  and     ebx, 8007000Eh
0x18002559d  test    rdi, rdi
0x1800255a0  jz      loc_1800256F5
0x1800255a6  test    ebx, ebx
0x1800255a8  jns     loc_18002572C
0x1800255ae  test    rdi, rdi
0x1800255b1  jz      loc_18002552F
0x1800255b7  xor     esi, esi
0x1800255b9  cmp     [rbp+arg_10], esi
0x1800255bc  jle     short loc_1800255DD
0x1800255be  movsxd  rax, esi
0x1800255c1  mov     rcx, [rdi+rax*8]; pv
0x1800255c5  test    rcx, rcx
0x1800255c8  jz      short loc_1800255D6
0x1800255ca  call    cs:__imp_CoTaskMemFree
0x1800255d1  nop     dword ptr [rax+rax+00h]
0x1800255d6  inc     esi
0x1800255d8  cmp     esi, [rbp+arg_10]
0x1800255db  jl      short loc_1800255BE
0x1800255dd  mov     rcx, rdi; pv
0x1800255e0  call    cs:__imp_CoTaskMemFree
0x1800255e7  nop     dword ptr [rax+rax+00h]
0x1800255ec  jmp     loc_18002552F
0x1800255f1  mov     rcx, [rbp+var_18]
0x1800255f5  lea     rdx, [rbp+arg_10]
0x1800255f9  mov     rax, [rcx]
0x1800255fc  mov     rax, [rax+40h]
0x180025600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025605  mov     ebx, eax
0x180025607  test    eax, eax
0x180025609  js      loc_18002552F
0x18002560f  mov     eax, [rbp+arg_10]
0x180025612  xor     edi, edi
0x180025614  test    eax, eax
0x180025616  js      loc_1800256F0
0x18002561c  shl     rax, 3
0x180025620  mov     ecx, 0FFFFFFFFh
0x180025625  cmp     rax, rcx
0x180025628  jbe     loc_18002557F
0x18002562e  mov     ebx, 80070216h
0x180025633  jmp     loc_1800256F5
0x180025638  test    ebx, ebx
0x18002563a  js      loc_1800255AE
0x180025640  mov     eax, [rbp+arg_10]
0x180025643  cmp     esi, eax
0x180025645  jge     loc_180025536
0x18002564b  lea     rcx, [rbp+var_20]; void *
0x18002564f  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180025654  mov     rcx, [rbp+var_18]
0x180025658  lea     rdx, [rbp+var_20]
0x18002565c  mov     rax, [rcx]
0x18002565f  mov     rax, [rax+48h]
0x180025663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025668  lea     rcx, [rbp+var_20]
0x18002566c  test    eax, eax
0x18002566e  jnz     loc_180025745
0x180025674  lea     rdx, [rbp+Block]
0x180025678  mov     [rbp+Block], 0
0x180025680  call    ?HrGetNodeText@@YAJAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAVCUString@@@Z; HrGetNodeText(SmartComPtr<IXMLDOMNode> &,CUString &)
0x180025685  mov     ebx, eax
0x180025687  test    eax, eax
0x180025689  jns     short loc_1800256A8
0x18002568b  mov     rcx, [rbp+Block]; Block
0x18002568f  inc     esi
0x180025691  call    cs:__imp_free
0x180025698  nop     dword ptr [rax+rax+00h]
0x18002569d  lea     rcx, [rbp+var_20]
0x1800256a1  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x1800256a6  jmp     short loc_180025638
0x1800256a8  movsxd  rax, esi
0x1800256ab  lea     rcx, [rbp+Block]; this
0x1800256af  lea     rdx, [rdi+rax*8]; unsigned __int16 **
0x1800256b3  call    ?HrGetCOM@CUString@@QEBAJPEAPEAG@Z; CUString::HrGetCOM(ushort * *)
0x1800256b8  mov     ebx, eax
0x1800256ba  jmp     short loc_18002568B
0x1800256bc  lea     r8, [rbp+var_8]
0x1800256c0  mov     rdx, rsi
0x1800256c3  mov     rcx, rdi
0x1800256c6  call    ?HrLoadDocumentAndRootNode@CDescriptionManager@@AEAAJAEBU_GUID@@AEAV?$SmartComPtr@UIXMLDOMNode@@@@@Z; CDescriptionManager::HrLoadDocumentAndRootNode(_GUID const &,SmartComPtr<IXMLDOMNode> &)
0x1800256cb  mov     ebx, eax
0x1800256cd  test    eax, eax
0x1800256cf  js      loc_180025519
0x1800256d5  lea     r8, [rbp+var_18]
0x1800256d9  lea     rdx, [rbp+var_8]
0x1800256dd  lea     rcx, aDddUdn; "//ddd:UDN"
0x1800256e4  call    ?HrSelectNodes@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAV?$SmartComPtr@UIXMLDOMNodeList@@@@@Z; HrSelectNodes(ushort const *,SmartComPtr<IXMLDOMNode> &,SmartComPtr<IXMLDOMNodeList> &)
0x1800256e9  mov     ebx, eax
0x1800256eb  jmp     loc_180025519
0x1800256f0  mov     ebx, 8007000Eh
0x1800256f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800256fc  cmp     rcx, rsi
0x1800256ff  jz      loc_1800255A6
0x180025705  test    byte ptr [rcx+1Ch], 1
0x180025709  jz      loc_1800255A6
0x18002570f  mov     rcx, [rcx+10h]
0x180025713  lea     r8, WPP_75c351f6869f3647f61a30e7f530184a_Traceguids
0x18002571a  mov     edx, 0Ah
0x18002571f  mov     r9d, ebx
0x180025722  call    WPP_SF_d
0x180025727  jmp     loc_1800255A6
0x18002572c  movsxd  r8, [rbp+arg_10]
0x180025730  xor     edx, edx; Val
0x180025732  shl     r8, 3; Size
0x180025736  mov     rcx, rdi; void *
0x180025739  call    memset_0
0x18002573e  xor     esi, esi
0x180025740  jmp     loc_180025638
0x180025745  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18002574a  mov     eax, [rbp+arg_10]
0x18002574d  jmp     loc_180025536
0x180025752  mov     rcx, cs:WPP_GLOBAL_Control
0x180025759  lea     rax, WPP_GLOBAL_Control
0x180025760  cmp     rcx, rax
0x180025763  jz      loc_180025544
0x180025769  test    byte ptr [rcx+1Ch], 1
0x18002576d  jz      loc_180025544
0x180025773  mov     rcx, [rcx+10h]
0x180025777  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18002577e  mov     edx, 6Ah ; 'j'
0x180025783  mov     r9d, ebx
0x180025786  call    WPP_SF_d
0x18002578b  jmp     loc_180025544
0x180025790  mov     eax, 80004003h
0x180025795  jmp     loc_180025567
```
