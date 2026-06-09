# CWMCService::DestroyMediaDevices(void)

- ea: `0x14004d1e4`
- end: `0x14004d4f8`
- name: `?DestroyMediaDevices@CWMCService@@AEAAXXZ`
- size: `788`
- prototype: `void __fastcall(CWMCService *__hidden this)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140052250`
- `0x140053b70`

## callees

- `0x140003690`
- `0x14000c920`
- `0x140024688`
- `0x14003919c`
- `0x1400396dc`
- `0x1400398e4`
- `0x14003a8ec`
- `0x14003d9ec`
- `0x14003fad8`
- `0x140047798`
- `0x1400488f4`
- `0x14004b5bc`
- `0x14004d1e4`
- `0x14004d898`
- `0x140053ad4`
- `0x140054490`
- `0x14005480c`
- `0x14009e010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14004d2a1`
- `KERNEL32!EnterCriticalSection` at `0x14004d2a1`
- `KERNEL32!LeaveCriticalSection` at `0x14004d4a4`
- `KERNEL32!LeaveCriticalSection` at `0x14004d4a4`
- `OLEAUT32!__imp_SysFreeString` at `0x14004d383`
- `OLEAUT32!__imp_SysFreeString` at `0x14004d383`
- `ole32!CoCreateInstance` at `0x14004d24f`
- `ole32!CoCreateInstance` at `0x14004d24f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CWMCService::DestroyMediaDevices(CWMCService *this)
{
  HRESULT v2; // eax
  __int64 StartPosition; // rax
  const unsigned __int16 **v4; // r14
  const void **NextKey; // rax
  OLECHAR *v6; // rbx
  int v7; // r9d
  unsigned int v8; // edx
  __int64 *v9; // r14
  unsigned __int16 *v10; // rbx
  __int64 v11; // rax
  CWMCContentProviderEventHandler *v12; // rcx
  __int64 v13; // rcx
  LPVOID ppv; // [rsp+70h] [rbp+40h] BYREF
  unsigned __int16 *v15; // [rsp+78h] [rbp+48h] BYREF
  __int64 i; // [rsp+80h] [rbp+50h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 232, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
  ppv = 0;
  v2 = CoCreateInstance(&CLSID_UPnPRegistrar, 0, 0x17u, &GUID_204810b6_73b2_11d4_bf42_00b0d0118b56, &ppv);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v2 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_dq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      233,
      &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
      (unsigned int)v2,
      ppv);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  StartPosition = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,bool,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<bool>>::GetStartPosition((char *)this + 272);
  for ( i = StartPosition; i; StartPosition = i )
  {
    v4 = *(const unsigned __int16 ***)(StartPosition + 8);
    NextKey = (const void **)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ContentProviderInfo *,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<ContentProviderInfo *>>::GetNextKey(
                               (char *)this + 272,
                               &i);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      &v15,
      NextKey);
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v15);
    v6 = bstrString;
    if ( ppv )
    {
      if ( bstrString )
      {
        v7 = (*(__int64 (__fastcall **)(LPVOID, BSTR, _QWORD))(*(_QWORD *)ppv + 56LL))(ppv, bstrString, 0);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v7 >> 31) & 0xFFFFFFFD) + 5 )
        {
          WPP_SF_dS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            234,
            (unsigned int)&WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
            v7,
            (__int64)v6);
        }
      }
    }
    CNTService::LogEvent(this, &WMC_I_SERVICE_MEDIASERVER_REMOVED, v4[2], 0, 0);
    ContentProviderInfo::`scalar deleting destructor'((ContentProviderInfo *)v4, v8);
    SysFreeString(v6);
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v15);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 235, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
  }
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ContentProviderInfo *,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<ContentProviderInfo *>>::RemoveAll((char *)this + 272);
  while ( *((_QWORD *)this + 25) )
  {
    v9 = (__int64 *)*((_QWORD *)this + 23);
    if ( !v9 )
      ATL::AtlThrowImpl(-2147467259);
    v10 = (unsigned __int16 *)v9[2];
    v15 = v10;
    if ( v10 )
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v10 + 8LL))(v10);
    v11 = *v9;
    *((_QWORD *)this + 23) = *v9;
    if ( v11 )
      *(_QWORD *)(v11 + 8) = 0;
    else
      *((_QWORD *)this + 24) = 0;
    ATL::CAtlList<ATL::CComPtr<IWMCSecurityNotification>,ATL::CElementTraits<ATL::CComPtr<IWMCSecurityNotification>>>::FreeNode(
      (char *)this + 184,
      v9);
    (*(void (__fastcall **)(unsigned __int16 *, _QWORD))(*(_QWORD *)v10 + 72LL))(v10, *((_QWORD *)this + 44));
    ATL::CComPtrBase<INetworkConnection>::Release(&v15);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v15);
  }
  v12 = (CWMCContentProviderEventHandler *)*((_QWORD *)this + 44);
  if ( v12 )
  {
    CWMCContentProviderEventHandler::Shutdown(v12);
    v13 = *((_QWORD *)this + 44);
    if ( v13 )
    {
      *((_QWORD *)this + 44) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 236, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
}

```

## disassembly

```asm
0x14004d1e4  push    rbp
0x14004d1e6  push    rbx
0x14004d1e7  push    rsi
0x14004d1e8  push    rdi
0x14004d1e9  push    r13
0x14004d1eb  push    r14
0x14004d1ed  push    r15
0x14004d1ef  mov     rbp, rsp
0x14004d1f2  sub     rsp, 30h
0x14004d1f6  mov     rdi, rcx
0x14004d1f9  lea     rbx, WPP_GLOBAL_Control
0x14004d200  lea     r13, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x14004d207  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d20e  cmp     rcx, rbx
0x14004d211  jz      short loc_14004D22A
0x14004d213  test    byte ptr [rcx+1Ch], 1
0x14004d217  jz      short loc_14004D22A
0x14004d219  mov     edx, 0E8h
0x14004d21e  mov     r8, r13
0x14004d221  mov     rcx, [rcx+10h]
0x14004d225  call    WPP_SF_
0x14004d22a  mov     [rbp+arg_0], 0
0x14004d232  lea     rax, [rbp+arg_0]
0x14004d236  mov     [rsp+30h+ppv], rax; ppv
0x14004d23b  lea     r9, _GUID_204810b6_73b2_11d4_bf42_00b0d0118b56; riid
0x14004d242  xor     edx, edx; pUnkOuter
0x14004d244  lea     r8d, [rdx+17h]; dwClsContext
0x14004d248  lea     rcx, CLSID_UPnPRegistrar; rclsid
0x14004d24f  call    cs:__imp_CoCreateInstance
0x14004d255  mov     r9d, eax
0x14004d258  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d25f  cmp     rcx, rbx
0x14004d262  jz      short loc_14004D297
0x14004d264  test    byte ptr [rcx+1Ch], 2
0x14004d268  jz      short loc_14004D297
0x14004d26a  mov     edx, eax
0x14004d26c  sar     edx, 1Fh
0x14004d26f  and     edx, 0FFFFFFFDh
0x14004d272  add     edx, 5
0x14004d275  movzx   eax, byte ptr [rcx+19h]
0x14004d279  cmp     eax, edx
0x14004d27b  jb      short loc_14004D297
0x14004d27d  mov     edx, 0E9h
0x14004d282  mov     rax, [rbp+arg_0]
0x14004d286  mov     [rsp+30h+ppv], rax
0x14004d28b  mov     r8, r13
0x14004d28e  mov     rcx, [rcx+10h]
0x14004d292  call    WPP_SF_dq
0x14004d297  lea     r15, [rdi+0E8h]
0x14004d29e  mov     rcx, r15; lpCriticalSection
0x14004d2a1  call    cs:__imp_EnterCriticalSection
0x14004d2a7  lea     rsi, [rdi+110h]
0x14004d2ae  mov     rcx, rsi
0x14004d2b1  call    ?GetStartPosition@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@_NV?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@_N@2@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,bool,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<bool>>::GetStartPosition(void)
0x14004d2b6  mov     [rbp+arg_10], rax
0x14004d2ba  test    rax, rax
0x14004d2bd  jz      loc_14004D3A7
0x14004d2c3  mov     r14, [rax+8]
0x14004d2c7  lea     rdx, [rbp+arg_10]
0x14004d2cb  mov     rcx, rsi
0x14004d2ce  call    ?GetNextKey@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEAUContentProviderInfo@@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@PEAUContentProviderInfo@@@2@@ATL@@QEBAAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@2@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ContentProviderInfo *,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<ContentProviderInfo *>>::GetNextKey(__POSITION * &)
0x14004d2d3  mov     rdx, rax
0x14004d2d6  lea     rcx, [rbp+arg_8]
0x14004d2da  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x14004d2df  nop
0x14004d2e0  mov     rdx, [rbp+arg_8]; unsigned __int16 *
0x14004d2e4  lea     rcx, [rbp+bstrString]; this
0x14004d2e8  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x14004d2ed  nop
0x14004d2ee  mov     rbx, [rbp+bstrString]
0x14004d2f2  mov     rcx, [rbp+arg_0]
0x14004d2f6  test    rcx, rcx
0x14004d2f9  jz      short loc_14004D358
0x14004d2fb  test    rbx, rbx
0x14004d2fe  jz      short loc_14004D358
0x14004d300  mov     rax, [rcx]
0x14004d303  xor     r8d, r8d
0x14004d306  mov     rdx, rbx
0x14004d309  mov     rax, [rax+38h]
0x14004d30d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d312  mov     r9d, eax
0x14004d315  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d31c  lea     rax, WPP_GLOBAL_Control
0x14004d323  cmp     rcx, rax
0x14004d326  jz      short loc_14004D358
0x14004d328  test    byte ptr [rcx+1Ch], 2
0x14004d32c  jz      short loc_14004D358
0x14004d32e  mov     edx, r9d
0x14004d331  sar     edx, 1Fh
0x14004d334  and     edx, 0FFFFFFFDh
0x14004d337  add     edx, 5
0x14004d33a  movzx   eax, byte ptr [rcx+19h]
0x14004d33e  cmp     eax, edx
0x14004d340  jb      short loc_14004D358
0x14004d342  mov     edx, 0EAh
0x14004d347  mov     [rsp+30h+ppv], rbx
0x14004d34c  mov     r8, r13
0x14004d34f  mov     rcx, [rcx+10h]
0x14004d353  call    WPP_SF_dS
0x14004d358  mov     [rsp+30h+ppv], 0; unsigned __int16 *
0x14004d361  xor     r9d, r9d; unsigned __int16 *
0x14004d364  mov     r8, [r14+10h]; unsigned __int16 *
0x14004d368  lea     rdx, WMC_I_SERVICE_MEDIASERVER_REMOVED; struct _EVENT_DESCRIPTOR *
0x14004d36f  mov     rcx, rdi; this
0x14004d372  call    ?LogEvent@CNTService@@QEAAXAEBU_EVENT_DESCRIPTOR@@PEBG11@Z; CNTService::LogEvent(_EVENT_DESCRIPTOR const &,ushort const *,ushort const *,ushort const *)
0x14004d377  mov     rcx, r14; this
0x14004d37a  call    ??_GContentProviderInfo@@QEAAPEAXI@Z; ContentProviderInfo::`scalar deleting destructor'(uint)
0x14004d37f  nop
0x14004d380  mov     rcx, rbx; bstrString
0x14004d383  call    cs:__imp_SysFreeString
0x14004d389  nop
0x14004d38a  lea     rcx, [rbp+arg_8]
0x14004d38e  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14004d393  mov     rax, [rbp+arg_10]
0x14004d397  test    rax, rax
0x14004d39a  jnz     loc_14004D2C3
0x14004d3a0  lea     rbx, WPP_GLOBAL_Control
0x14004d3a7  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d3ae  cmp     rcx, rbx
0x14004d3b1  jz      short loc_14004D3D0
0x14004d3b3  test    byte ptr [rcx+1Ch], 2
0x14004d3b7  jz      short loc_14004D3D0
0x14004d3b9  cmp     byte ptr [rcx+19h], 5
0x14004d3bd  jb      short loc_14004D3D0
0x14004d3bf  mov     edx, 0EBh
0x14004d3c4  mov     r8, r13
0x14004d3c7  mov     rcx, [rcx+10h]
0x14004d3cb  call    WPP_SF_
0x14004d3d0  mov     rcx, rsi
0x14004d3d3  call    ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEAUContentProviderInfo@@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@PEAUContentProviderInfo@@@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ContentProviderInfo *,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<ContentProviderInfo *>>::RemoveAll(void)
0x14004d3d8  cmp     qword ptr [rdi+0C8h], 0
0x14004d3e0  jz      loc_14004D46D
0x14004d3e6  lea     rsi, [rdi+0B8h]
0x14004d3ed  mov     r14, [rsi]
0x14004d3f0  test    r14, r14
0x14004d3f3  jz      loc_14004D4ED
0x14004d3f9  mov     rbx, [r14+10h]
0x14004d3fd  mov     [rbp+arg_8], rbx
0x14004d401  test    rbx, rbx
0x14004d404  jz      short loc_14004D416
0x14004d406  mov     rax, [rbx]
0x14004d409  mov     rcx, rbx
0x14004d40c  mov     rax, [rax+8]
0x14004d410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d415  nop
0x14004d416  mov     rax, [r14]
0x14004d419  mov     [rsi], rax
0x14004d41c  test    rax, rax
0x14004d41f  jz      short loc_14004D42B
0x14004d421  mov     qword ptr [rax+8], 0
0x14004d429  jmp     short loc_14004D433
0x14004d42b  mov     qword ptr [rsi+8], 0
0x14004d433  mov     rdx, r14
0x14004d436  mov     rcx, rsi
0x14004d439  call    ?FreeNode@?$CAtlList@V?$CComPtr@UIWMCSecurityNotification@@@ATL@@V?$CElementTraits@V?$CComPtr@UIWMCSecurityNotification@@@ATL@@@2@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlList<ATL::CComPtr<IWMCSecurityNotification>,ATL::CElementTraits<ATL::CComPtr<IWMCSecurityNotification>>>::FreeNode(ATL::CAtlList<ATL::CComPtr<IWMCSecurityNotification>,ATL::CElementTraits<ATL::CComPtr<IWMCSecurityNotification>>>::CNode *)
0x14004d43e  nop
0x14004d43f  mov     rax, [rbx]
0x14004d442  mov     rdx, [rdi+160h]
0x14004d449  mov     rcx, rbx
0x14004d44c  mov     rax, [rax+48h]
0x14004d450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d455  lea     rcx, [rbp+arg_8]
0x14004d459  call    ?Release@?$CComPtrBase@UINetworkConnection@@@ATL@@QEAAXXZ; ATL::CComPtrBase<INetworkConnection>::Release(void)
0x14004d45e  nop
0x14004d45f  lea     rcx, [rbp+arg_8]
0x14004d463  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004d468  jmp     loc_14004D3D8
0x14004d46d  mov     rcx, [rdi+160h]; this
0x14004d474  test    rcx, rcx
0x14004d477  jz      short loc_14004D4A1
0x14004d479  call    ?Shutdown@CWMCContentProviderEventHandler@@QEAAXXZ; CWMCContentProviderEventHandler::Shutdown(void)
0x14004d47e  mov     rcx, [rdi+160h]
0x14004d485  test    rcx, rcx
0x14004d488  jz      short loc_14004D4A1
0x14004d48a  mov     qword ptr [rdi+160h], 0
0x14004d495  mov     rax, [rcx]
0x14004d498  mov     rax, [rax+10h]
0x14004d49c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d4a1  mov     rcx, r15; lpCriticalSection
0x14004d4a4  call    cs:__imp_LeaveCriticalSection
0x14004d4aa  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d4b1  lea     rax, WPP_GLOBAL_Control
0x14004d4b8  cmp     rcx, rax
0x14004d4bb  jz      short loc_14004D4D5
0x14004d4bd  test    byte ptr [rcx+1Ch], 1
0x14004d4c1  jz      short loc_14004D4D5
0x14004d4c3  mov     edx, 0ECh
0x14004d4c8  mov     r8, r13
0x14004d4cb  mov     rcx, [rcx+10h]
0x14004d4cf  call    WPP_SF_
0x14004d4d4  nop
0x14004d4d5  lea     rcx, [rbp+arg_0]
0x14004d4d9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004d4de  add     rsp, 30h
0x14004d4e2  pop     r15
0x14004d4e4  pop     r14
0x14004d4e6  pop     r13
0x14004d4e8  pop     rdi
0x14004d4e9  pop     rsi
0x14004d4ea  pop     rbx
0x14004d4eb  pop     rbp
0x14004d4ec  retn
0x14004d4ed  mov     ecx, 80004005h; int
0x14004d4f2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
