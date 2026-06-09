# OSDeploymentInformationFactory::RemoveDeploymentProgress(wchar_t const *)

- ea: `0x1400196b0`
- end: `0x1400197c5`
- name: `?RemoveDeploymentProgress@OSDeploymentInformationFactory@@UEAAJPEB_W@Z`
- size: `277`
- prototype: `__int64 __fastcall(OSDeploymentInformationFactory *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x140002ac0`
- `0x14000ca6c`
- `0x14000d4cc`
- `0x1400196b0`
- `0x1400199a0`
- `0x140019ddc`
- `0x140019f64`
- `0x14001a0dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140019716`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140019716`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400197a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400197a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OSDeploymentInformationFactory::RemoveDeploymentProgress(
        OSDeploymentInformationFactory *this,
        const wchar_t *a2)
{
  int v3; // eax
  unsigned int v4; // edi
  void *v5; // rbx
  int v6; // eax
  unsigned int IndexOf; // eax
  void *lpMem; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v10[6]; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  lpMem = 0;
  v3 = DuplicateString<wchar_t const *,wchar_t *>(a2, &lpMem);
  v4 = v3;
  v5 = lpMem;
  if ( v3 >= 0 )
  {
    v10[1] = (char *)this + 128;
    if ( this != (OSDeploymentInformationFactory *)-128LL )
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::GetImpl'::`2'::impl) )
    {
      v6 = LiveObjectMap<IDeploymentInformation *>::RemoveAndDisconnect((char *)this + 208, v5);
      v4 = v6;
      if ( v6 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x123,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\DeploymentInformation\\OSDeploymentIn"
                        "formationFactory.cpp",
          (const char *)(unsigned int)v6,
          (int)lpMem);
    }
    else
    {
      v10[0] = v5;
      IndexOf = CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::GetIndexOf(
                  (char *)this + 176,
                  v10);
      v4 = 0;
      if ( IndexOf >= *((_DWORD *)this + 49) )
        v4 = -2145124345;
      else
        CSusArrayList<CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::CMapEntryOps>::RemoveArraySection(
          (__int64)this + 176,
          IndexOf,
          IndexOf,
          1);
    }
    if ( this != (OSDeploymentInformationFactory *)-128LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11D,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\DeploymentInformation\\OSDeploymentInform"
                    "ationFactory.cpp",
      (const char *)(unsigned int)v3,
      (int)lpMem);
  }
  if ( v5 )
    SusFree(v5);
  return v4;
}

```

## disassembly

```asm
0x1400196b0  mov     [rsp+arg_10], rbx
0x1400196b5  push    rbp
0x1400196b6  push    rsi
0x1400196b7  push    rdi
0x1400196b8  sub     rsp, 40h
0x1400196bc  mov     rax, rdx
0x1400196bf  mov     rbp, rcx
0x1400196c2  mov     [rsp+58h+lpMem], 0; int
0x1400196cb  lea     rdx, [rsp+58h+lpMem]
0x1400196d0  mov     rcx, rax
0x1400196d3  call    ??$DuplicateString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x1400196d8  mov     edi, eax
0x1400196da  mov     rbx, [rsp+58h+lpMem]
0x1400196df  test    eax, eax
0x1400196e1  jns     short loc_140019701
0x1400196e3  mov     rcx, [rsp+58h]; this
0x1400196e8  mov     r9d, eax; char *
0x1400196eb  lea     r8, aCW1SSrcClientE_0; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1400196f2  mov     edx, 11Dh; void *
0x1400196f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400196fc  jmp     loc_1400197A9
0x140019701  lea     rsi, [rbp+80h]
0x140019708  mov     [rsp+58h+var_28], rsi
0x14001970d  test    rsi, rsi
0x140019710  jz      short loc_14001971D
0x140019712  lea     rcx, [rsi+8]; lpCriticalSection
0x140019716  call    cs:__imp_EnterCriticalSection
0x14001971c  nop
0x14001971d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::GetImpl(void)'::`2'::impl
0x140019724  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::__private_IsEnabled(void)
0x140019729  test    al, al
0x14001972b  jz      short loc_14001975D
0x14001972d  lea     rcx, [rbp+0D0h]
0x140019734  mov     rdx, rbx
0x140019737  call    ?RemoveAndDisconnect@?$LiveObjectMap@PEAUIDeploymentInformation@@@@QEAAJPEB_W@Z; LiveObjectMap<IDeploymentInformation *>::RemoveAndDisconnect(wchar_t const *)
0x14001973c  mov     edi, eax
0x14001973e  test    eax, eax
0x140019740  jns     short loc_140019799
0x140019742  mov     rcx, [rsp+58h]; this
0x140019747  mov     r9d, eax; char *
0x14001974a  lea     r8, aCW1SSrcClientE_0; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x140019751  mov     edx, 123h; void *
0x140019756  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001975b  jmp     short loc_140019799
0x14001975d  mov     [rsp+58h+var_30], rbx
0x140019762  lea     rdx, [rsp+58h+var_30]
0x140019767  lea     rcx, [rbp+0B0h]
0x14001976e  call    ?GetIndexOf@?$CSusMap@PEA_WPEAUIDeploymentInformation@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentInformation@@@@@@QEBAKAEBQEA_W@Z; CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::GetIndexOf(wchar_t * const &)
0x140019773  xor     edi, edi
0x140019775  cmp     eax, [rbp+0C4h]
0x14001977b  jnb     short loc_140019794
0x14001977d  lea     r9d, [rdi+1]
0x140019781  mov     r8d, eax
0x140019784  mov     edx, eax
0x140019786  lea     rcx, [rbp+0B0h]
0x14001978d  call    ?RemoveArraySection@?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentProgress@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentProgress@@@@@@VCMapEntryOps@2@@@IEAAXKKH@Z; CSusArrayList<CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::CMapEntryOps>::RemoveArraySection(ulong,ulong,int)
0x140019792  jmp     short loc_140019799
0x140019794  mov     edi, 80240007h
0x140019799  test    rsi, rsi
0x14001979c  jz      short loc_1400197A9
0x14001979e  lea     rcx, [rsi+8]; lpCriticalSection
0x1400197a2  call    cs:__imp_LeaveCriticalSection
0x1400197a8  nop
0x1400197a9  test    rbx, rbx
0x1400197ac  jz      short loc_1400197B6
0x1400197ae  mov     rcx, rbx; lpMem
0x1400197b1  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400197b6  mov     eax, edi
0x1400197b8  mov     rbx, [rsp+58h+arg_10]
0x1400197bd  add     rsp, 40h
0x1400197c1  pop     rdi
0x1400197c2  pop     rsi
0x1400197c3  pop     rbp
0x1400197c4  retn
```
