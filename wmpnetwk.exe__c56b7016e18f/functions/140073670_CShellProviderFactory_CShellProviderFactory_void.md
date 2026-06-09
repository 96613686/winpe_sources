# CShellProviderFactory::~CShellProviderFactory(void)

- ea: `0x140073670`
- end: `0x1400737bd`
- name: `??1CShellProviderFactory@@QEAA@XZ`
- size: `333`
- prototype: `void __fastcall(CShellProviderFactory *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14007312c`

## callees

- `0x1400028cc`
- `0x140039ca8`
- `0x14003f17c`
- `0x14003fa7c`
- `0x140047798`
- `0x140073670`
- `0x14007b908`
- `0x14007ce14`
- `0x14008b67c`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140073713`
- `KERNEL32!EnterCriticalSection` at `0x140073713`
- `KERNEL32!LeaveCriticalSection` at `0x140073758`
- `KERNEL32!LeaveCriticalSection` at `0x140073758`
- `KERNEL32!DeleteCriticalSection` at `0x140073761`
- `KERNEL32!DeleteCriticalSection` at `0x140073761`

## pseudocode

```c
void __fastcall CShellProviderFactory::~CShellProviderFactory(CShellProviderFactory *this)
{
  struct IHMELibraryMonitorEventHandler *v2; // rdx
  int v3; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 281, &WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids);
  v2 = (struct IHMELibraryMonitorEventHandler *)*((_QWORD *)this + 9);
  if ( v2 )
  {
    if ( *((_BYTE *)this + 80) )
    {
      v3 = CHMESharedLibraryMonitor::RemoveObserver(*((CHMESharedLibraryMonitor **)this + 8), v2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v3 >> 31) & 0xFFFFFFFD) + 5 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          282,
          &WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids,
          (unsigned int)v3);
      }
    }
    CLibraryEventHandler::Shutdown(*((CLibraryEventHandler **)this + 9));
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 283, &WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids);
  }
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CComPtr<IWMCContentProvider>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>,ATL::CElementTraits<ATL::CComPtr<IWMCContentProvider>>>::RemoveAll((char *)this + 136);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 284, &WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids);
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CComPtr<IWMCContentProvider>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>,ATL::CElementTraits<ATL::CComPtr<IWMCContentProvider>>>::RemoveAll((char *)this + 136);
  ATL::CComPtrBase<IMFNetVRoot>::~CComPtrBase<IMFNetVRoot>((__int64 *)this + 16);
  ShellAggregateResultItem::~ShellAggregateResultItem((CShellProviderFactory *)((char *)this + 72));
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((CShellProviderFactory *)((char *)this + 16));
}

```

## disassembly

```asm
0x140073670  push    rbx
0x140073672  push    rbp
0x140073673  push    rsi
0x140073674  push    rdi
0x140073675  push    r15
0x140073677  sub     rsp, 20h
0x14007367b  mov     rbx, rcx
0x14007367e  mov     rcx, cs:WPP_GLOBAL_Control
0x140073685  lea     r15, WPP_GLOBAL_Control
0x14007368c  cmp     rcx, r15
0x14007368f  jz      short loc_1400736AC
0x140073691  test    byte ptr [rcx+1Ch], 1
0x140073695  jz      short loc_1400736AC
0x140073697  mov     rcx, [rcx+10h]
0x14007369b  lea     r8, WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids
0x1400736a2  mov     edx, 119h
0x1400736a7  call    WPP_SF_
0x1400736ac  lea     rdi, [rbx+48h]
0x1400736b0  mov     rdx, [rdi]; struct IHMELibraryMonitorEventHandler *
0x1400736b3  test    rdx, rdx
0x1400736b6  jz      short loc_14007370C
0x1400736b8  cmp     byte ptr [rbx+50h], 0
0x1400736bc  jz      short loc_140073704
0x1400736be  mov     rcx, [rbx+40h]; this
0x1400736c2  call    ?RemoveObserver@CHMESharedLibraryMonitor@@QEAAJPEAUIHMELibraryMonitorEventHandler@@@Z; CHMESharedLibraryMonitor::RemoveObserver(IHMELibraryMonitorEventHandler *)
0x1400736c7  mov     r9d, eax
0x1400736ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400736d1  cmp     rcx, r15
0x1400736d4  jz      short loc_140073704
0x1400736d6  test    byte ptr [rcx+1Ch], 2
0x1400736da  jz      short loc_140073704
0x1400736dc  mov     edx, eax
0x1400736de  movzx   eax, byte ptr [rcx+19h]
0x1400736e2  sar     edx, 1Fh
0x1400736e5  and     edx, 0FFFFFFFDh
0x1400736e8  add     edx, 5
0x1400736eb  cmp     eax, edx
0x1400736ed  jb      short loc_140073704
0x1400736ef  mov     rcx, [rcx+10h]
0x1400736f3  lea     r8, WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids
0x1400736fa  mov     edx, 11Ah
0x1400736ff  call    WPP_SF_d
0x140073704  mov     rcx, [rdi]; this
0x140073707  call    ?Shutdown@CLibraryEventHandler@@QEAAXXZ; CLibraryEventHandler::Shutdown(void)
0x14007370c  lea     rsi, [rbx+58h]
0x140073710  mov     rcx, rsi; lpCriticalSection
0x140073713  call    cs:__imp_EnterCriticalSection
0x140073719  mov     rcx, cs:WPP_GLOBAL_Control
0x140073720  cmp     rcx, r15
0x140073723  jz      short loc_140073746
0x140073725  test    byte ptr [rcx+1Ch], 2
0x140073729  jz      short loc_140073746
0x14007372b  cmp     byte ptr [rcx+19h], 5
0x14007372f  jb      short loc_140073746
0x140073731  mov     rcx, [rcx+10h]
0x140073735  lea     r8, WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids
0x14007373c  mov     edx, 11Bh
0x140073741  call    WPP_SF_
0x140073746  lea     rbp, [rbx+88h]
0x14007374d  mov     rcx, rbp
0x140073750  call    ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CComPtr@UIWMCContentProvider@@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$CComPtr@UIWMCContentProvider@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CComPtr<IWMCContentProvider>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>,ATL::CElementTraits<ATL::CComPtr<IWMCContentProvider>>>::RemoveAll(void)
0x140073755  mov     rcx, rsi; lpCriticalSection
0x140073758  call    cs:__imp_LeaveCriticalSection
0x14007375e  mov     rcx, rsi; lpCriticalSection
0x140073761  call    cs:__imp_DeleteCriticalSection
0x140073767  mov     rcx, cs:WPP_GLOBAL_Control
0x14007376e  cmp     rcx, r15
0x140073771  jz      short loc_14007378E
0x140073773  test    byte ptr [rcx+1Ch], 1
0x140073777  jz      short loc_14007378E
0x140073779  mov     rcx, [rcx+10h]
0x14007377d  lea     r8, WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids
0x140073784  mov     edx, 11Ch
0x140073789  call    WPP_SF_
0x14007378e  mov     rcx, rbp
0x140073791  call    ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CComPtr@UIWMCContentProvider@@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$CComPtr@UIWMCContentProvider@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CComPtr<IWMCContentProvider>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>,ATL::CElementTraits<ATL::CComPtr<IWMCContentProvider>>>::RemoveAll(void)
0x140073796  lea     rcx, [rbx+80h]
0x14007379d  call    ??1?$CComPtrBase@UIMFNetVRoot@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFNetVRoot>::~CComPtrBase<IMFNetVRoot>(void)
0x1400737a2  mov     rcx, rdi; this
0x1400737a5  call    ??1ShellAggregateResultItem@@QEAA@XZ; ShellAggregateResultItem::~ShellAggregateResultItem(void)
0x1400737aa  lea     rcx, [rbx+10h]; this
0x1400737ae  add     rsp, 20h
0x1400737b2  pop     r15
0x1400737b4  pop     rdi
0x1400737b5  pop     rsi
0x1400737b6  pop     rbp
0x1400737b7  pop     rbx
0x1400737b8  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
