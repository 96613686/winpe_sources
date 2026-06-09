# OSDeploymentInformationFactory::RemoveDeploymentInformation(wchar_t const *)

- ea: `0x1400195a0`
- end: `0x1400196a6`
- name: `?RemoveDeploymentInformation@OSDeploymentInformationFactory@@UEAAJPEB_W@Z`
- size: `262`
- prototype: `__int64 __fastcall(OSDeploymentInformationFactory *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x140002ac0`
- `0x14000ca6c`
- `0x14000d4cc`
- `0x1400195a0`
- `0x1400199a0`
- `0x140019ddc`
- `0x140019f64`
- `0x14001a0dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140019603`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140019603`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140019683`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140019683`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OSDeploymentInformationFactory::RemoveDeploymentInformation(
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
    v10[1] = (char *)this + 16;
    if ( this != (OSDeploymentInformationFactory *)-16LL )
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::GetImpl'::`2'::impl) )
    {
      v6 = LiveObjectMap<IDeploymentInformation *>::RemoveAndDisconnect((char *)this + 96, v5);
      v4 = v6;
      if ( v6 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x112,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\DeploymentInformation\\OSDeploymentIn"
                        "formationFactory.cpp",
          (const char *)(unsigned int)v6,
          (int)lpMem);
    }
    else
    {
      v10[0] = v5;
      IndexOf = CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::GetIndexOf(
                  (char *)this + 64,
                  v10);
      v4 = 0;
      if ( IndexOf >= *((_DWORD *)this + 21) )
        v4 = -2145124345;
      else
        CSusArrayList<CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::CMapEntryOps>::RemoveArraySection(
          (__int64)this + 64,
          IndexOf,
          IndexOf,
          1);
    }
    if ( this != (OSDeploymentInformationFactory *)-16LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10C,
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
0x1400195a0  mov     [rsp+arg_10], rbx
0x1400195a5  push    rbp
0x1400195a6  push    rsi
0x1400195a7  push    rdi
0x1400195a8  sub     rsp, 40h
0x1400195ac  mov     rax, rdx
0x1400195af  mov     rbp, rcx
0x1400195b2  mov     [rsp+58h+lpMem], 0; int
0x1400195bb  lea     rdx, [rsp+58h+lpMem]
0x1400195c0  mov     rcx, rax
0x1400195c3  call    ??$DuplicateString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x1400195c8  mov     edi, eax
0x1400195ca  mov     rbx, [rsp+58h+lpMem]
0x1400195cf  test    eax, eax
0x1400195d1  jns     short loc_1400195F1
0x1400195d3  mov     rcx, [rsp+58h]; this
0x1400195d8  mov     r9d, eax; char *
0x1400195db  lea     r8, aCW1SSrcClientE_0; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1400195e2  mov     edx, 10Ch; void *
0x1400195e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400195ec  jmp     loc_14001968A
0x1400195f1  lea     rsi, [rbp+10h]
0x1400195f5  mov     [rsp+58h+var_28], rsi
0x1400195fa  test    rsi, rsi
0x1400195fd  jz      short loc_14001960A
0x1400195ff  lea     rcx, [rsi+8]; lpCriticalSection
0x140019603  call    cs:__imp_EnterCriticalSection
0x140019609  nop
0x14001960a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::GetImpl(void)'::`2'::impl
0x140019611  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::__private_IsEnabled(void)
0x140019616  test    al, al
0x140019618  jz      short loc_140019647
0x14001961a  lea     rcx, [rbp+60h]
0x14001961e  mov     rdx, rbx
0x140019621  call    ?RemoveAndDisconnect@?$LiveObjectMap@PEAUIDeploymentInformation@@@@QEAAJPEB_W@Z; LiveObjectMap<IDeploymentInformation *>::RemoveAndDisconnect(wchar_t const *)
0x140019626  mov     edi, eax
0x140019628  test    eax, eax
0x14001962a  jns     short loc_14001967A
0x14001962c  mov     rcx, [rsp+58h]; this
0x140019631  mov     r9d, eax; char *
0x140019634  lea     r8, aCW1SSrcClientE_0; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x14001963b  mov     edx, 112h; void *
0x140019640  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019645  jmp     short loc_14001967A
0x140019647  mov     [rsp+58h+var_30], rbx
0x14001964c  lea     rdx, [rsp+58h+var_30]
0x140019651  lea     rcx, [rbp+40h]
0x140019655  call    ?GetIndexOf@?$CSusMap@PEA_WPEAUIDeploymentInformation@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentInformation@@@@@@QEBAKAEBQEA_W@Z; CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::GetIndexOf(wchar_t * const &)
0x14001965a  xor     edi, edi
0x14001965c  cmp     eax, [rbp+54h]
0x14001965f  jnb     short loc_140019675
0x140019661  lea     r9d, [rdi+1]
0x140019665  mov     r8d, eax
0x140019668  mov     edx, eax
0x14001966a  lea     rcx, [rbp+40h]
0x14001966e  call    ?RemoveArraySection@?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentProgress@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentProgress@@@@@@VCMapEntryOps@2@@@IEAAXKKH@Z; CSusArrayList<CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::CMapEntryOps>::RemoveArraySection(ulong,ulong,int)
0x140019673  jmp     short loc_14001967A
0x140019675  mov     edi, 80240007h
0x14001967a  test    rsi, rsi
0x14001967d  jz      short loc_14001968A
0x14001967f  lea     rcx, [rsi+8]; lpCriticalSection
0x140019683  call    cs:__imp_LeaveCriticalSection
0x140019689  nop
0x14001968a  test    rbx, rbx
0x14001968d  jz      short loc_140019697
0x14001968f  mov     rcx, rbx; lpMem
0x140019692  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140019697  mov     eax, edi
0x140019699  mov     rbx, [rsp+58h+arg_10]
0x14001969e  add     rsp, 40h
0x1400196a2  pop     rdi
0x1400196a3  pop     rsi
0x1400196a4  pop     rbp
0x1400196a5  retn
```
