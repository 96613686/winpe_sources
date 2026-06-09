# CDescriptionManager::GetUDNs(_GUID const &,long *,ushort * * *)

- ea: `0x180024bf0`
- end: `0x180024eb3`
- name: `?GetUDNs@CDescriptionManager@@UEAAJAEBU_GUID@@PEAJPEAPEAPEAG@Z`
- size: `707`
- prototype: `__int64 __fastcall(CDescriptionManager *__hidden this, const struct _GUID *, int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001169c`
- `0x1800117bc`
- `0x1800117d0`
- `0x180013180`
- `0x180024bf0`
- `0x180025018`
- `0x180025330`
- `0x180025470`
- `0x180038ce4`
- `0x18003ae80`
- `0x18003fea4`
- `0x180055010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180024db0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180024db0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024c99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024c99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024cba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024cba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024cf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024d09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024cf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024d09`

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
  __int64 v17; // [rsp+20h] [rbp-20h] BYREF
  __int64 v18; // [rsp+28h] [rbp-18h] BYREF
  void *Block; // [rsp+30h] [rbp-10h] BYREF
  __int64 v20; // [rsp+38h] [rbp-8h] BYREF
  int v21; // [rsp+80h] [rbp+40h] BYREF

  if ( !a3 || !a4 )
    return 2147500035LL;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  ATL::CComSafeDeleteCriticalSection::Lock((CDescriptionManager *)((char *)this + 24));
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v20);
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v18);
  IsAllowedCOMCallLocality = HrIsAllowedCOMCallLocality(1);
  if ( IsAllowedCOMCallLocality >= 0 )
  {
    IsAllowedCOMCallLocality = CDescriptionManager::HrLoadDocumentAndRootNode(this, a2, &v20);
    if ( IsAllowedCOMCallLocality >= 0 )
      IsAllowedCOMCallLocality = HrSelectNodes(L"//ddd:UDN", &v20, &v18);
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
                SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v17);
                if ( (*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 72LL))(v18, &v17) )
                {
                  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v17);
                  v11 = v21;
                  goto LABEL_6;
                }
                Block = 0;
                IsAllowedCOMCallLocality = HrGetNodeText(&v17, &Block);
                if ( IsAllowedCOMCallLocality >= 0 )
                  IsAllowedCOMCallLocality = CUString::HrGetCOM((CUString *)&Block, (unsigned __int16 **)v10 + v16);
                ++v16;
                free(Block);
                ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v17);
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
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v18);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v20);
  LeaveCriticalSection(v8);
  return (unsigned int)IsAllowedCOMCallLocality;
}

```

## disassembly

```asm
0x180024bf0  mov     [rsp-28h+arg_0], rbx
0x180024bf5  mov     [rsp-28h+arg_8], rsi
0x180024bfa  push    rbp
0x180024bfb  push    rdi
0x180024bfc  push    r12
0x180024bfe  push    r14
0x180024c00  push    r15
0x180024c02  mov     rbp, rsp
0x180024c05  sub     rsp, 40h
0x180024c09  mov     r14, r9
0x180024c0c  mov     r15, r8
0x180024c0f  mov     rsi, rdx
0x180024c12  mov     rdi, rcx
0x180024c15  test    r8, r8
0x180024c18  jz      loc_180024EA9
0x180024c1e  test    r9, r9
0x180024c21  jz      loc_180024EA9
0x180024c27  lea     r12, [rcx+18h]
0x180024c2b  mov     rcx, r12; this
0x180024c2e  call    ?Lock@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Lock(void)
0x180024c33  lea     rcx, [rbp+var_8]; void *
0x180024c37  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180024c3c  lea     rcx, [rbp+var_18]; void *
0x180024c40  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180024c45  mov     ecx, 1
0x180024c4a  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x180024c4f  mov     ebx, eax
0x180024c51  test    eax, eax
0x180024c53  jns     loc_180024DD5
0x180024c59  mov     [rbp+arg_10], 0
0x180024c60  lea     rsi, WPP_GLOBAL_Control
0x180024c67  test    ebx, ebx
0x180024c69  jns     loc_180024D14
0x180024c6f  xor     edi, edi
0x180024c71  xor     eax, eax
0x180024c73  mov     [rbp+arg_10], eax
0x180024c76  mov     [r15], eax
0x180024c79  mov     [r14], rdi
0x180024c7c  test    ebx, ebx
0x180024c7e  jnz     loc_180024E6B
0x180024c84  lea     rcx, [rbp+var_18]
0x180024c88  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180024c8d  lea     rcx, [rbp+var_8]
0x180024c91  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180024c96  mov     rcx, r12; lpCriticalSection
0x180024c99  call    cs:__imp_LeaveCriticalSection
0x180024c9f  mov     eax, ebx
0x180024ca1  mov     rbx, [rsp+40h+arg_0]
0x180024ca6  mov     rsi, [rsp+40h+arg_8]
0x180024cab  add     rsp, 40h
0x180024caf  pop     r15
0x180024cb1  pop     r14
0x180024cb3  pop     r12
0x180024cb5  pop     rdi
0x180024cb6  pop     rbp
0x180024cb7  retn
0x180024cb8  mov     ecx, eax; cb
0x180024cba  call    cs:__imp_CoTaskMemAlloc
0x180024cc0  mov     rdi, rax
0x180024cc3  neg     rax
0x180024cc6  sbb     ebx, ebx
0x180024cc8  not     ebx
0x180024cca  and     ebx, 8007000Eh
0x180024cd0  test    rdi, rdi
0x180024cd3  jz      loc_180024E0E
0x180024cd9  test    ebx, ebx
0x180024cdb  jns     loc_180024E45
0x180024ce1  test    rdi, rdi
0x180024ce4  jz      short loc_180024C6F
0x180024ce6  xor     esi, esi
0x180024ce8  cmp     [rbp+arg_10], esi
0x180024ceb  jle     short loc_180024D06
0x180024ced  movsxd  rax, esi
0x180024cf0  mov     rcx, [rdi+rax*8]; pv
0x180024cf4  test    rcx, rcx
0x180024cf7  jz      short loc_180024CFF
0x180024cf9  call    cs:__imp_CoTaskMemFree
0x180024cff  inc     esi
0x180024d01  cmp     esi, [rbp+arg_10]
0x180024d04  jl      short loc_180024CED
0x180024d06  mov     rcx, rdi; pv
0x180024d09  call    cs:__imp_CoTaskMemFree
0x180024d0f  jmp     loc_180024C6F
0x180024d14  mov     rcx, [rbp+var_18]
0x180024d18  lea     rdx, [rbp+arg_10]
0x180024d1c  mov     rax, [rcx]
0x180024d1f  mov     rax, [rax+40h]
0x180024d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d28  mov     ebx, eax
0x180024d2a  test    eax, eax
0x180024d2c  js      loc_180024C6F
0x180024d32  mov     eax, [rbp+arg_10]
0x180024d35  xor     edi, edi
0x180024d37  test    eax, eax
0x180024d39  js      loc_180024E09
0x180024d3f  shl     rax, 3
0x180024d43  mov     ecx, 0FFFFFFFFh
0x180024d48  cmp     rax, rcx
0x180024d4b  jbe     loc_180024CB8
0x180024d51  mov     ebx, 80070216h
0x180024d56  jmp     loc_180024E0E
0x180024d5b  test    ebx, ebx
0x180024d5d  js      short loc_180024CE1
0x180024d5f  mov     eax, [rbp+arg_10]
0x180024d62  cmp     esi, eax
0x180024d64  jge     loc_180024C76
0x180024d6a  lea     rcx, [rbp+var_20]; void *
0x180024d6e  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180024d73  mov     rcx, [rbp+var_18]
0x180024d77  lea     rdx, [rbp+var_20]
0x180024d7b  mov     rax, [rcx]
0x180024d7e  mov     rax, [rax+48h]
0x180024d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d87  lea     rcx, [rbp+var_20]
0x180024d8b  test    eax, eax
0x180024d8d  jnz     loc_180024E5E
0x180024d93  lea     rdx, [rbp+Block]
0x180024d97  mov     [rbp+Block], 0
0x180024d9f  call    ?HrGetNodeText@@YAJAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAVCUString@@@Z; HrGetNodeText(SmartComPtr<IXMLDOMNode> &,CUString &)
0x180024da4  mov     ebx, eax
0x180024da6  test    eax, eax
0x180024da8  jns     short loc_180024DC1
0x180024daa  mov     rcx, [rbp+Block]; Block
0x180024dae  inc     esi
0x180024db0  call    cs:__imp_free
0x180024db6  lea     rcx, [rbp+var_20]
0x180024dba  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180024dbf  jmp     short loc_180024D5B
0x180024dc1  movsxd  rax, esi
0x180024dc4  lea     rcx, [rbp+Block]; this
0x180024dc8  lea     rdx, [rdi+rax*8]; unsigned __int16 **
0x180024dcc  call    ?HrGetCOM@CUString@@QEBAJPEAPEAG@Z; CUString::HrGetCOM(ushort * *)
0x180024dd1  mov     ebx, eax
0x180024dd3  jmp     short loc_180024DAA
0x180024dd5  lea     r8, [rbp+var_8]
0x180024dd9  mov     rdx, rsi
0x180024ddc  mov     rcx, rdi
0x180024ddf  call    ?HrLoadDocumentAndRootNode@CDescriptionManager@@AEAAJAEBU_GUID@@AEAV?$SmartComPtr@UIXMLDOMNode@@@@@Z; CDescriptionManager::HrLoadDocumentAndRootNode(_GUID const &,SmartComPtr<IXMLDOMNode> &)
0x180024de4  mov     ebx, eax
0x180024de6  test    eax, eax
0x180024de8  js      loc_180024C59
0x180024dee  lea     r8, [rbp+var_18]
0x180024df2  lea     rdx, [rbp+var_8]
0x180024df6  lea     rcx, aDddUdn; "//ddd:UDN"
0x180024dfd  call    ?HrSelectNodes@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAV?$SmartComPtr@UIXMLDOMNodeList@@@@@Z; HrSelectNodes(ushort const *,SmartComPtr<IXMLDOMNode> &,SmartComPtr<IXMLDOMNodeList> &)
0x180024e02  mov     ebx, eax
0x180024e04  jmp     loc_180024C59
0x180024e09  mov     ebx, 8007000Eh
0x180024e0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e15  cmp     rcx, rsi
0x180024e18  jz      loc_180024CD9
0x180024e1e  test    byte ptr [rcx+1Ch], 1
0x180024e22  jz      loc_180024CD9
0x180024e28  mov     rcx, [rcx+10h]
0x180024e2c  lea     r8, WPP_75c351f6869f3647f61a30e7f530184a_Traceguids
0x180024e33  mov     edx, 0Ah
0x180024e38  mov     r9d, ebx
0x180024e3b  call    WPP_SF_d
0x180024e40  jmp     loc_180024CD9
0x180024e45  movsxd  r8, [rbp+arg_10]
0x180024e49  xor     edx, edx; Val
0x180024e4b  shl     r8, 3; Size
0x180024e4f  mov     rcx, rdi; void *
0x180024e52  call    memset_0
0x180024e57  xor     esi, esi
0x180024e59  jmp     loc_180024D5B
0x180024e5e  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180024e63  mov     eax, [rbp+arg_10]
0x180024e66  jmp     loc_180024C76
0x180024e6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e72  lea     rax, WPP_GLOBAL_Control
0x180024e79  cmp     rcx, rax
0x180024e7c  jz      loc_180024C84
0x180024e82  test    byte ptr [rcx+1Ch], 1
0x180024e86  jz      loc_180024C84
0x180024e8c  mov     rcx, [rcx+10h]
0x180024e90  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x180024e97  mov     edx, 6Ah ; 'j'
0x180024e9c  mov     r9d, ebx
0x180024e9f  call    WPP_SF_d
0x180024ea4  jmp     loc_180024C84
0x180024ea9  mov     eax, 80004003h
0x180024eae  jmp     loc_180024CA1
```
