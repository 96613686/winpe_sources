# CWMCService::OnContentProviderRemoved(IWMCContentProvider *)

- ea: `0x14004fba8`
- end: `0x14004fea7`
- name: `?OnContentProviderRemoved@CWMCService@@QEAAJPEAUIWMCContentProvider@@@Z`
- size: `767`
- prototype: `__int64 __fastcall(CWMCService *__hidden this, struct IWMCContentProvider *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14004fad0`

## callees

- `0x140003690`
- `0x14000c920`
- `0x140024688`
- `0x14003919c`
- `0x1400396dc`
- `0x1400398e4`
- `0x14003f17c`
- `0x14003f1bc`
- `0x14003fad8`
- `0x140047798`
- `0x1400488f4`
- `0x14004b5bc`
- `0x14004fba8`
- `0x140051984`
- `0x140054424`
- `0x140054490`
- `0x14005480c`
- `0x14009e010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14004fcaa`
- `KERNEL32!EnterCriticalSection` at `0x14004fcaa`
- `KERNEL32!LeaveCriticalSection` at `0x14004fe18`
- `KERNEL32!LeaveCriticalSection` at `0x14004fe18`
- `OLEAUT32!__imp_SysFreeString` at `0x14004fde3`
- `OLEAUT32!__imp_SysFreeString` at `0x14004fde3`
- `ole32!CoCreateInstance` at `0x14004fc41`
- `ole32!CoCreateInstance` at `0x14004fc41`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWMCService::OnContentProviderRemoved(CWMCService *this, struct IWMCContentProvider *a2)
{
  HRESULT v4; // eax
  __int64 v5; // rcx
  int v6; // edi
  PVOID *v7; // r10
  struct _RTL_CRITICAL_SECTION *v8; // r12
  char *v9; // r15
  __int64 StartPosition; // rsi
  __int64 v11; // r13
  OLECHAR *v12; // rbx
  int v13; // r9d
  unsigned int v14; // edx
  unsigned __int16 *v16; // [rsp+30h] [rbp-10h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-8h] BYREF
  LPVOID ppv; // [rsp+90h] [rbp+50h] BYREF
  __int64 v20; // [rsp+98h] [rbp+58h] BYREF

  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
    McTemplateU0pq_EventWriteTransfer(this, WMC_On_Content_Prov_Removed_Start, a2, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 250, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, a2);
  }
  ppv = 0;
  v4 = CoCreateInstance(&CLSID_UPnPRegistrar, 0, 0x17u, &GUID_204810b6_73b2_11d4_bf42_00b0d0118b56, &ppv);
  v6 = v4;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v4 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_dq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      251,
      &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
      (unsigned int)v4,
      ppv);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 >= 0 )
  {
    v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 232);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
    v9 = (char *)this + 272;
    StartPosition = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,bool,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<bool>>::GetStartPosition((char *)this + 272);
    v20 = StartPosition;
    while ( StartPosition )
    {
      v11 = *(_QWORD *)(StartPosition + 8);
      if ( *(struct IWMCContentProvider **)(v11 + 8) == a2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 252, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
        }
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
          &v16,
          (const void **)StartPosition);
        ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v16);
        v12 = bstrString;
        if ( bstrString )
        {
          v13 = (*(__int64 (__fastcall **)(LPVOID, BSTR, _QWORD))(*(_QWORD *)ppv + 56LL))(ppv, bstrString, 0);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v13 >> 31) & 0xFFFFFFFD) + 5 )
          {
            WPP_SF_dS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              253,
              (unsigned int)&WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
              v13,
              (__int64)v12);
          }
        }
        CNTService::LogEvent(this, &WMC_I_SERVICE_MEDIASERVER_REMOVED, *(const unsigned __int16 **)(v11 + 16), 0, 0);
        ContentProviderInfo::`scalar deleting destructor'((ContentProviderInfo *)v11, v14);
        ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ContentProviderInfo *,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<ContentProviderInfo *>>::RemoveAtPos(
          v9,
          StartPosition);
        StartPosition = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,bool,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<bool>>::GetStartPosition(v9);
        v20 = StartPosition;
        SysFreeString(v12);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v16);
      }
      else
      {
        ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ContentProviderInfo *,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<ContentProviderInfo *>>::GetNextKey(
          v9,
          &v20);
        StartPosition = v20;
      }
    }
    LeaveCriticalSection(v8);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
  {
    v5 = ((v6 >> 31) & 0xFFFFFFFD) + 5;
    if ( *((unsigned __int8 *)v7 + 25) >= (unsigned int)v5 )
      WPP_SF_d(v7[2], 255, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, (unsigned int)v6);
  }
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
    McTemplateU0pq_EventWriteTransfer(v5, WMC_On_Content_Prov_Removed_Stop, a2, (unsigned int)v6);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14004fba8  mov     [rsp-38h+arg_8], rbx
0x14004fbad  mov     [rsp-38h+arg_0], rcx
0x14004fbb2  push    rbp
0x14004fbb3  push    rsi
0x14004fbb4  push    rdi
0x14004fbb5  push    r12
0x14004fbb7  push    r13
0x14004fbb9  push    r14
0x14004fbbb  push    r15
0x14004fbbd  mov     rbp, rsp
0x14004fbc0  sub     rsp, 40h
0x14004fbc4  mov     r14, rdx
0x14004fbc7  mov     rbx, rcx
0x14004fbca  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 20h
0x14004fbd1  jz      short loc_14004FBE5
0x14004fbd3  xor     r9d, r9d
0x14004fbd6  mov     r8, rdx
0x14004fbd9  lea     rdx, WMC_On_Content_Prov_Removed_Start
0x14004fbe0  call    McTemplateU0pq_EventWriteTransfer
0x14004fbe5  lea     r13, WPP_GLOBAL_Control
0x14004fbec  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fbf3  cmp     rcx, r13
0x14004fbf6  jz      short loc_14004FC1C
0x14004fbf8  test    byte ptr [rcx+1Ch], 1
0x14004fbfc  jz      short loc_14004FC1C
0x14004fbfe  cmp     byte ptr [rcx+19h], 5
0x14004fc02  jb      short loc_14004FC1C
0x14004fc04  mov     edx, 0FAh
0x14004fc09  mov     r9, r14
0x14004fc0c  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x14004fc13  mov     rcx, [rcx+10h]
0x14004fc17  call    WPP_SF_q
0x14004fc1c  mov     [rbp+arg_10], 0
0x14004fc24  lea     rax, [rbp+arg_10]
0x14004fc28  mov     [rsp+40h+ppv], rax; ppv
0x14004fc2d  lea     r9, _GUID_204810b6_73b2_11d4_bf42_00b0d0118b56; riid
0x14004fc34  xor     edx, edx; pUnkOuter
0x14004fc36  lea     r8d, [rdx+17h]; dwClsContext
0x14004fc3a  lea     rcx, CLSID_UPnPRegistrar; rclsid
0x14004fc41  call    cs:__imp_CoCreateInstance
0x14004fc47  mov     edi, eax
0x14004fc49  mov     r10, cs:WPP_GLOBAL_Control
0x14004fc50  cmp     r10, r13
0x14004fc53  jz      short loc_14004FC98
0x14004fc55  test    byte ptr [r10+1Ch], 2
0x14004fc5a  jz      short loc_14004FC98
0x14004fc5c  mov     edx, eax
0x14004fc5e  sar     edx, 1Fh
0x14004fc61  and     edx, 0FFFFFFFDh
0x14004fc64  add     edx, 5
0x14004fc67  movzx   eax, byte ptr [r10+19h]
0x14004fc6c  cmp     eax, edx
0x14004fc6e  jb      short loc_14004FC98
0x14004fc70  mov     edx, 0FBh
0x14004fc75  mov     rax, [rbp+arg_10]
0x14004fc79  mov     [rsp+40h+ppv], rax
0x14004fc7e  mov     r9d, edi
0x14004fc81  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x14004fc88  mov     rcx, [r10+10h]
0x14004fc8c  call    WPP_SF_dq
0x14004fc91  mov     r10, cs:WPP_GLOBAL_Control
0x14004fc98  test    edi, edi
0x14004fc9a  js      loc_14004FE25
0x14004fca0  lea     r12, [rbx+0E8h]
0x14004fca7  mov     rcx, r12; lpCriticalSection
0x14004fcaa  call    cs:__imp_EnterCriticalSection
0x14004fcb0  lea     r15, [rbx+110h]
0x14004fcb7  mov     rcx, r15
0x14004fcba  call    ?GetStartPosition@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@_NV?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@_N@2@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,bool,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<bool>>::GetStartPosition(void)
0x14004fcbf  mov     rsi, rax
0x14004fcc2  mov     [rbp+arg_18], rax
0x14004fcc6  test    rax, rax
0x14004fcc9  jz      loc_14004FE15
0x14004fccf  test    rax, rax
0x14004fcd2  jz      loc_14004FE9C
0x14004fcd8  mov     r13, [rsi+8]
0x14004fcdc  cmp     [r13+8], r14
0x14004fce0  jnz     loc_14004FDF5
0x14004fce6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fced  lea     rax, WPP_GLOBAL_Control
0x14004fcf4  cmp     rcx, rax
0x14004fcf7  jz      short loc_14004FD1A
0x14004fcf9  test    byte ptr [rcx+1Ch], 2
0x14004fcfd  jz      short loc_14004FD1A
0x14004fcff  cmp     byte ptr [rcx+19h], 5
0x14004fd03  jb      short loc_14004FD1A
0x14004fd05  mov     edx, 0FCh
0x14004fd0a  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x14004fd11  mov     rcx, [rcx+10h]
0x14004fd15  call    WPP_SF_
0x14004fd1a  mov     rdx, rsi
0x14004fd1d  lea     rcx, [rbp+var_10]
0x14004fd21  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x14004fd26  nop
0x14004fd27  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x14004fd2b  lea     rcx, [rbp+bstrString]; this
0x14004fd2f  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x14004fd34  nop
0x14004fd35  mov     rbx, [rbp+bstrString]
0x14004fd39  test    rbx, rbx
0x14004fd3c  jz      short loc_14004FD9E
0x14004fd3e  mov     rcx, [rbp+arg_10]
0x14004fd42  mov     rax, [rcx]
0x14004fd45  xor     r8d, r8d
0x14004fd48  mov     rdx, rbx
0x14004fd4b  mov     rax, [rax+38h]
0x14004fd4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fd54  mov     r9d, eax
0x14004fd57  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fd5e  lea     rax, WPP_GLOBAL_Control
0x14004fd65  cmp     rcx, rax
0x14004fd68  jz      short loc_14004FD9E
0x14004fd6a  test    byte ptr [rcx+1Ch], 2
0x14004fd6e  jz      short loc_14004FD9E
0x14004fd70  mov     edx, r9d
0x14004fd73  sar     edx, 1Fh
0x14004fd76  and     edx, 0FFFFFFFDh
0x14004fd79  add     edx, 5
0x14004fd7c  movzx   eax, byte ptr [rcx+19h]
0x14004fd80  cmp     eax, edx
0x14004fd82  jb      short loc_14004FD9E
0x14004fd84  mov     edx, 0FDh
0x14004fd89  mov     [rsp+40h+ppv], rbx
0x14004fd8e  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x14004fd95  mov     rcx, [rcx+10h]
0x14004fd99  call    WPP_SF_dS
0x14004fd9e  mov     [rsp+40h+ppv], 0; unsigned __int16 *
0x14004fda7  xor     r9d, r9d; unsigned __int16 *
0x14004fdaa  mov     r8, [r13+10h]; unsigned __int16 *
0x14004fdae  lea     rdx, WMC_I_SERVICE_MEDIASERVER_REMOVED; struct _EVENT_DESCRIPTOR *
0x14004fdb5  mov     rcx, [rbp+arg_0]; this
0x14004fdb9  call    ?LogEvent@CNTService@@QEAAXAEBU_EVENT_DESCRIPTOR@@PEBG11@Z; CNTService::LogEvent(_EVENT_DESCRIPTOR const &,ushort const *,ushort const *,ushort const *)
0x14004fdbe  mov     rcx, r13; this
0x14004fdc1  call    ??_GContentProviderInfo@@QEAAPEAXI@Z; ContentProviderInfo::`scalar deleting destructor'(uint)
0x14004fdc6  mov     rdx, rsi
0x14004fdc9  mov     rcx, r15
0x14004fdcc  call    ?RemoveAtPos@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEAUContentProviderInfo@@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@PEAUContentProviderInfo@@@2@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ContentProviderInfo *,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<ContentProviderInfo *>>::RemoveAtPos(__POSITION *)
0x14004fdd1  mov     rcx, r15
0x14004fdd4  call    ?GetStartPosition@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@_NV?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@_N@2@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,bool,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<bool>>::GetStartPosition(void)
0x14004fdd9  mov     rsi, rax
0x14004fddc  mov     [rbp+arg_18], rax
0x14004fde0  mov     rcx, rbx; bstrString
0x14004fde3  call    cs:__imp_SysFreeString
0x14004fde9  nop
0x14004fdea  lea     rcx, [rbp+var_10]
0x14004fdee  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14004fdf3  jmp     short loc_14004FE05
0x14004fdf5  lea     rdx, [rbp+arg_18]
0x14004fdf9  mov     rcx, r15
0x14004fdfc  call    ?GetNextKey@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEAUContentProviderInfo@@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@PEAUContentProviderInfo@@@2@@ATL@@QEBAAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@2@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ContentProviderInfo *,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<ContentProviderInfo *>>::GetNextKey(__POSITION * &)
0x14004fe01  mov     rsi, [rbp+arg_18]
0x14004fe05  test    rsi, rsi
0x14004fe08  jnz     loc_14004FCD8
0x14004fe0e  lea     r13, WPP_GLOBAL_Control
0x14004fe15  mov     rcx, r12; lpCriticalSection
0x14004fe18  call    cs:__imp_LeaveCriticalSection
0x14004fe1e  mov     r10, cs:WPP_GLOBAL_Control
0x14004fe25  cmp     r10, r13
0x14004fe28  jz      short loc_14004FE5D
0x14004fe2a  test    byte ptr [r10+1Ch], 1
0x14004fe2f  jz      short loc_14004FE5D
0x14004fe31  mov     ecx, edi
0x14004fe33  sar     ecx, 1Fh
0x14004fe36  and     ecx, 0FFFFFFFDh
0x14004fe39  add     ecx, 5
0x14004fe3c  movzx   eax, byte ptr [r10+19h]
0x14004fe41  cmp     eax, ecx
0x14004fe43  jb      short loc_14004FE5D
0x14004fe45  mov     edx, 0FFh
0x14004fe4a  mov     r9d, edi
0x14004fe4d  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x14004fe54  mov     rcx, [r10+10h]
0x14004fe58  call    WPP_SF_d
0x14004fe5d  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 20h
0x14004fe64  jz      short loc_14004FE79
0x14004fe66  mov     r9d, edi
0x14004fe69  mov     r8, r14
0x14004fe6c  lea     rdx, WMC_On_Content_Prov_Removed_Stop
0x14004fe73  call    McTemplateU0pq_EventWriteTransfer
0x14004fe78  nop
0x14004fe79  lea     rcx, [rbp+arg_10]
0x14004fe7d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004fe82  mov     eax, edi
0x14004fe84  mov     rbx, [rsp+40h+arg_8]
0x14004fe8c  add     rsp, 40h
0x14004fe90  pop     r15
0x14004fe92  pop     r14
0x14004fe94  pop     r13
0x14004fe96  pop     r12
0x14004fe98  pop     rdi
0x14004fe99  pop     rsi
0x14004fe9a  pop     rbp
0x14004fe9b  retn
0x14004fe9c  mov     ecx, 80004005h; int
0x14004fea1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
