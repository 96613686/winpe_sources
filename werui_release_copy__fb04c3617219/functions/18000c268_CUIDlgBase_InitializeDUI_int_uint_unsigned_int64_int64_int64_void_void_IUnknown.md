# CUIDlgBase::InitializeDUI(int (*)(uint,unsigned __int64,__int64,__int64 *,void *),void *,IUnknown * *)

- ea: `0x18000c268`
- end: `0x18000c5b7`
- name: `?InitializeDUI@CUIDlgBase@@IEAAJP6AHI_K_JPEA_JPEAX@Z3PEAPEAUIUnknown@@@Z`
- size: `847`
- prototype: `__int64 __fastcall(CUIDlgBase *__hidden this, int (*)(unsigned int, unsigned __int64, __int64, __int64 *, void *), void *, struct IUnknown **)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a42c`
- `0x18000cbc8`

## callees

- `0x180003604`
- `0x180003fc4`
- `0x180004260`
- `0x180008ec8`
- `0x18000bda4`
- `0x18000bebc`
- `0x18000c268`
- `0x18000c70c`
- `0x18000c834`

## import_xrefs

- `DUI70!InitThread` at `0x18000c2fe`
- `DUI70!InitThread` at `0x18000c2fe`
- `DUI70!InitProcessPriv` at `0x18000c2bc`
- `DUI70!InitProcessPriv` at `0x18000c2bc`
- `DUI70!CreateDUIWrapper` at `0x18000c524`
- `DUI70!CreateDUIWrapper` at `0x18000c524`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x18000c517`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x18000c517`
- `DUI70!?FontSizeProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000c3e7`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x18000c3f7`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x18000c464`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x18000c4d3`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x18000c3f7`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x18000c464`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x18000c4d3`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x18000c3d2`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x18000c43f`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x18000c4ae`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x18000c3d2`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x18000c43f`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x18000c4ae`
- `DUI70!?WidthProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000c454`
- `DUI70!?HeightProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000c4c3`

## string_xrefs

- `0x18000c333`: `RICHED20.DLL`

## pseudocode

```c
__int64 __fastcall CUIDlgBase::InitializeDUI(
        CUIDlgBase *this,
        int (*a2)(unsigned int, unsigned __int64, __int64, __int64 *, void *),
        void *a3,
        struct IUnknown **a4)
{
  int inited; // eax
  __int64 v9; // r9
  __int64 v10; // r8
  int DUIWrapper; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 ModFromSystem; // rax
  DirectUI::Element *v15; // rbx
  struct DirectUI::Value *Int; // rax
  DirectUI::Value *v17; // rsi
  DirectUI::Element *v18; // rbx
  struct DirectUI::Value *v19; // rax
  DirectUI::Value *v20; // rsi
  DirectUI::Element *v21; // rbx
  struct DirectUI::Value *v22; // rax
  DirectUI::Value *v23; // rsi
  __int64 v24; // rax
  _BYTE v26[16]; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v27; // [rsp+70h] [rbp+8h] BYREF

  inited = InitActivationContext((void **)this + 7, (unsigned __int64 *)this + 8);
  LOBYTE(v9) = 1;
  LOBYTE(v10) = 1;
  *((_DWORD *)this + 18) = inited >= 0;
  DUIWrapper = InitProcessPriv(14, &_ImageBase, v10, v9, 1);
  if ( DUIWrapper < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 14;
LABEL_42:
      WPP_SF_d(v12[2], v13, WPP_8da448519d113fb3b57e053fb6502830_Traceguids, (unsigned int)DUIWrapper);
      return (unsigned int)DUIWrapper;
    }
    return (unsigned int)DUIWrapper;
  }
  *((_DWORD *)this + 12) = 1;
  DUIWrapper = InitThread(2);
  if ( DUIWrapper < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 15;
      goto LABEL_42;
    }
    return (unsigned int)DUIWrapper;
  }
  *((_DWORD *)this + 13) = 1;
  ModFromSystem = UtilLoadModFromSystem(v26, L"RICHED20.DLL");
  tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::operator=(
    &CCRichEdit::hRichEdit,
    ModFromSystem);
  tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(v26);
  if ( !CCRichEdit::hRichEdit )
  {
    DUIWrapper = -2147467259;
    goto LABEL_39;
  }
  DUIWrapper = DirectUI::ClassInfo<CCRichEdit,DirectUI::CCBase,DirectUI::StandardCreator<CCRichEdit>>::Register();
  if ( DUIWrapper < 0 )
  {
LABEL_39:
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 16;
      goto LABEL_42;
    }
    return (unsigned int)DUIWrapper;
  }
  v27 = 0;
  DUIWrapper = DirectUI::CreateAndInit<CCRichEdit,unsigned int>(2, 0, &v27, (char *)this + 80);
  if ( DUIWrapper < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 17;
      goto LABEL_42;
    }
    return (unsigned int)DUIWrapper;
  }
  v15 = (DirectUI::Element *)*((_QWORD *)this + 10);
  Int = (struct DirectUI::Value *)DirectUI::Value::CreateInt(14);
  v17 = Int;
  if ( !Int )
  {
    DUIWrapper = -2147024882;
LABEL_18:
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 18;
      goto LABEL_42;
    }
    return (unsigned int)DUIWrapper;
  }
  DUIWrapper = DirectUI::Element::SetValue(
                 v15,
                 (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::FontSizeProp,
                 1,
                 Int);
  DirectUI::Value::Release(v17);
  if ( DUIWrapper < 0 )
    goto LABEL_18;
  v18 = (DirectUI::Element *)*((_QWORD *)this + 10);
  v19 = (struct DirectUI::Value *)DirectUI::Value::CreateInt(100);
  v20 = v19;
  if ( !v19 )
  {
    DUIWrapper = -2147024882;
LABEL_24:
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 19;
      goto LABEL_42;
    }
    return (unsigned int)DUIWrapper;
  }
  DUIWrapper = DirectUI::Element::SetValue(
                 v18,
                 (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::WidthProp,
                 1,
                 v19);
  DirectUI::Value::Release(v20);
  if ( DUIWrapper < 0 )
    goto LABEL_24;
  v21 = (DirectUI::Element *)*((_QWORD *)this + 10);
  v22 = (struct DirectUI::Value *)DirectUI::Value::CreateInt(150);
  v23 = v22;
  if ( v22 )
  {
    DUIWrapper = DirectUI::Element::SetValue(
                   v21,
                   (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::HeightProp,
                   1,
                   v22);
    DirectUI::Value::Release(v23);
    if ( DUIWrapper >= 0 )
    {
      DirectUI::Element::EndDefer(*((DirectUI::Element **)this + 10), v27);
      DUIWrapper = CreateDUIWrapper(*((_QWORD *)this + 10), a4);
      if ( DUIWrapper >= 0 )
      {
        v24 = *((_QWORD *)this + 10);
        DUIWrapper = 0;
        *(_QWORD *)(v24 + 336) = a2;
        *(_QWORD *)(v24 + 344) = a3;
      }
      else
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v13 = 21;
          goto LABEL_42;
        }
      }
      return (unsigned int)DUIWrapper;
    }
  }
  else
  {
    DUIWrapper = -2147024882;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v13 = 20;
    goto LABEL_42;
  }
  return (unsigned int)DUIWrapper;
}

```

## disassembly

```asm
0x18000c268  mov     [rsp+arg_8], rbx
0x18000c26d  mov     [rsp+arg_10], rbp
0x18000c272  push    rsi
0x18000c273  push    rdi
0x18000c274  push    r12
0x18000c276  push    r14
0x18000c278  push    r15
0x18000c27a  sub     rsp, 40h
0x18000c27e  mov     r14, rdx
0x18000c281  mov     rdi, rcx
0x18000c284  lea     rdx, [rcx+40h]; unsigned __int64 *
0x18000c288  mov     r15, r9
0x18000c28b  add     rcx, 38h ; '8'; void **
0x18000c28f  mov     rbp, r8
0x18000c292  call    ?InitActivationContext@@YAJPEAPEAXPEA_K@Z; InitActivationContext(void * *,unsigned __int64 *)
0x18000c297  mov     r12d, 1
0x18000c29d  lea     rdx, __ImageBase
0x18000c2a4  not     eax
0x18000c2a6  mov     [rsp+68h+var_48], r12b
0x18000c2ab  shr     eax, 1Fh
0x18000c2ae  mov     r9b, r12b
0x18000c2b1  mov     r8b, r12b
0x18000c2b4  mov     [rdi+48h], eax
0x18000c2b7  lea     ecx, [r12+0Dh]
0x18000c2bc  call    cs:__imp_InitProcessPriv
0x18000c2c2  mov     ebx, eax
0x18000c2c4  test    eax, eax
0x18000c2c6  jns     short loc_18000C2F3
0x18000c2c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2cf  lea     rax, WPP_GLOBAL_Control
0x18000c2d6  cmp     rcx, rax
0x18000c2d9  jz      loc_18000C59C
0x18000c2df  test    [rcx+1Ch], r12b
0x18000c2e3  jz      loc_18000C59C
0x18000c2e9  lea     edx, [r12+0Dh]
0x18000c2ee  jmp     loc_18000C589
0x18000c2f3  mov     esi, 2
0x18000c2f8  mov     [rdi+30h], r12d
0x18000c2fc  mov     ecx, esi
0x18000c2fe  call    cs:__imp_InitThread
0x18000c304  mov     ebx, eax
0x18000c306  test    eax, eax
0x18000c308  jns     short loc_18000C333
0x18000c30a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c311  lea     rax, WPP_GLOBAL_Control
0x18000c318  cmp     rcx, rax
0x18000c31b  jz      loc_18000C59C
0x18000c321  test    [rcx+1Ch], r12b
0x18000c325  jz      loc_18000C59C
0x18000c32b  lea     edx, [rsi+0Dh]
0x18000c32e  jmp     loc_18000C589
0x18000c333  lea     rdx, aRiched20Dll; "RICHED20.DLL"
0x18000c33a  mov     [rdi+34h], r12d
0x18000c33e  lea     rcx, [rsp+68h+var_38]
0x18000c343  call    ?UtilLoadModFromSystem@@YA?AV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEBG@Z; UtilLoadModFromSystem(ushort const *)
0x18000c348  mov     rdx, rax
0x18000c34b  lea     rcx, ?hRichEdit@CCRichEdit@@2V?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@A; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> CCRichEdit::hRichEdit
0x18000c352  call    ??4?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::operator=(tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> &&)
0x18000c357  lea     rcx, [rsp+68h+var_38]
0x18000c35c  call    ??1?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>(void)
0x18000c361  cmp     cs:?hRichEdit@CCRichEdit@@2V?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@A, 0; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> CCRichEdit::hRichEdit
0x18000c369  jz      loc_18000C566
0x18000c36f  call    ?Register@?$ClassInfo@VCCRichEdit@@VCCBase@DirectUI@@V?$StandardCreator@VCCRichEdit@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<CCRichEdit,DirectUI::CCBase,DirectUI::StandardCreator<CCRichEdit>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x18000c374  mov     ebx, eax
0x18000c376  test    eax, eax
0x18000c378  js      loc_18000C56B
0x18000c37e  lea     r9, [rdi+50h]
0x18000c382  mov     [rsp+68h+arg_0], 0
0x18000c38a  lea     r8, [rsp+68h+arg_0]
0x18000c38f  xor     edx, edx
0x18000c391  mov     ecx, esi
0x18000c393  call    ??$CreateAndInit@VCCRichEdit@@I@DirectUI@@YAJIPEAVElement@0@PEAKPEAPEAV10@@Z; DirectUI::CreateAndInit<CCRichEdit,uint>(uint,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18000c398  mov     ebx, eax
0x18000c39a  test    eax, eax
0x18000c39c  jns     short loc_18000C3C9
0x18000c39e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3a5  lea     rax, WPP_GLOBAL_Control
0x18000c3ac  cmp     rcx, rax
0x18000c3af  jz      loc_18000C59C
0x18000c3b5  test    [rcx+1Ch], r12b
0x18000c3b9  jz      loc_18000C59C
0x18000c3bf  mov     edx, 11h
0x18000c3c4  jmp     loc_18000C589
0x18000c3c9  mov     rbx, [rdi+50h]
0x18000c3cd  xor     edx, edx
0x18000c3cf  lea     ecx, [rdx+0Eh]
0x18000c3d2  call    cs:__imp_?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z; DirectUI::Value::CreateInt(int,DynamicScaleValue)
0x18000c3d8  mov     rsi, rax
0x18000c3db  test    rax, rax
0x18000c3de  jnz     short loc_18000C3E7
0x18000c3e0  mov     ebx, 8007000Eh
0x18000c3e5  jmp     short loc_18000C40B
0x18000c3e7  mov     rdx, cs:__imp_?FontSizeProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::FontSizeProp(void)
0x18000c3ee  mov     r9, rsi
0x18000c3f1  mov     r8d, r12d
0x18000c3f4  mov     rcx, rbx
0x18000c3f7  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x18000c3fd  mov     rcx, rsi; this
0x18000c400  mov     ebx, eax
0x18000c402  call    ?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000c407  test    ebx, ebx
0x18000c409  jns     short loc_18000C436
0x18000c40b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c412  lea     rax, WPP_GLOBAL_Control
0x18000c419  cmp     rcx, rax
0x18000c41c  jz      loc_18000C59C
0x18000c422  test    [rcx+1Ch], r12b
0x18000c426  jz      loc_18000C59C
0x18000c42c  mov     edx, 12h
0x18000c431  jmp     loc_18000C589
0x18000c436  mov     rbx, [rdi+50h]
0x18000c43a  xor     edx, edx
0x18000c43c  lea     ecx, [rdx+64h]
0x18000c43f  call    cs:__imp_?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z; DirectUI::Value::CreateInt(int,DynamicScaleValue)
0x18000c445  mov     rsi, rax
0x18000c448  test    rax, rax
0x18000c44b  jnz     short loc_18000C454
0x18000c44d  mov     ebx, 8007000Eh
0x18000c452  jmp     short loc_18000C478
0x18000c454  mov     rdx, cs:__imp_?WidthProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::WidthProp(void)
0x18000c45b  mov     r9, rsi
0x18000c45e  mov     r8d, r12d
0x18000c461  mov     rcx, rbx
0x18000c464  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x18000c46a  mov     rcx, rsi; this
0x18000c46d  mov     ebx, eax
0x18000c46f  call    ?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000c474  test    ebx, ebx
0x18000c476  jns     short loc_18000C4A3
0x18000c478  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c47f  lea     rax, WPP_GLOBAL_Control
0x18000c486  cmp     rcx, rax
0x18000c489  jz      loc_18000C59C
0x18000c48f  test    [rcx+1Ch], r12b
0x18000c493  jz      loc_18000C59C
0x18000c499  mov     edx, 13h
0x18000c49e  jmp     loc_18000C589
0x18000c4a3  mov     rbx, [rdi+50h]
0x18000c4a7  xor     edx, edx
0x18000c4a9  mov     ecx, 96h
0x18000c4ae  call    cs:__imp_?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z; DirectUI::Value::CreateInt(int,DynamicScaleValue)
0x18000c4b4  mov     rsi, rax
0x18000c4b7  test    rax, rax
0x18000c4ba  jnz     short loc_18000C4C3
0x18000c4bc  mov     ebx, 8007000Eh
0x18000c4c1  jmp     short loc_18000C4E7
0x18000c4c3  mov     rdx, cs:__imp_?HeightProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::HeightProp(void)
0x18000c4ca  mov     r9, rsi
0x18000c4cd  mov     r8d, r12d
0x18000c4d0  mov     rcx, rbx
0x18000c4d3  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x18000c4d9  mov     rcx, rsi; this
0x18000c4dc  mov     ebx, eax
0x18000c4de  call    ?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000c4e3  test    ebx, ebx
0x18000c4e5  jns     short loc_18000C50F
0x18000c4e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4ee  lea     rax, WPP_GLOBAL_Control
0x18000c4f5  cmp     rcx, rax
0x18000c4f8  jz      loc_18000C59C
0x18000c4fe  test    [rcx+1Ch], r12b
0x18000c502  jz      loc_18000C59C
0x18000c508  mov     edx, 14h
0x18000c50d  jmp     short loc_18000C589
0x18000c50f  mov     edx, [rsp+68h+arg_0]
0x18000c513  mov     rcx, [rdi+50h]
0x18000c517  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x18000c51d  mov     rcx, [rdi+50h]
0x18000c521  mov     rdx, r15
0x18000c524  call    cs:__imp_CreateDUIWrapper
0x18000c52a  mov     ebx, eax
0x18000c52c  test    eax, eax
0x18000c52e  jns     short loc_18000C550
0x18000c530  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c537  lea     rax, WPP_GLOBAL_Control
0x18000c53e  cmp     rcx, rax
0x18000c541  jz      short loc_18000C59C
0x18000c543  test    [rcx+1Ch], r12b
0x18000c547  jz      short loc_18000C59C
0x18000c549  mov     edx, 15h
0x18000c54e  jmp     short loc_18000C589
0x18000c550  mov     rax, [rdi+50h]
0x18000c554  xor     ebx, ebx
0x18000c556  mov     [rax+150h], r14
0x18000c55d  mov     [rax+158h], rbp
0x18000c564  jmp     short loc_18000C59C
0x18000c566  mov     ebx, 80004005h
0x18000c56b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c572  lea     rax, WPP_GLOBAL_Control
0x18000c579  cmp     rcx, rax
0x18000c57c  jz      short loc_18000C59C
0x18000c57e  test    [rcx+1Ch], r12b
0x18000c582  jz      short loc_18000C59C
0x18000c584  mov     edx, 10h
0x18000c589  mov     rcx, [rcx+10h]
0x18000c58d  lea     r8, WPP_8da448519d113fb3b57e053fb6502830_Traceguids
0x18000c594  mov     r9d, ebx
0x18000c597  call    WPP_SF_d
0x18000c59c  lea     r11, [rsp+68h+var_28]
0x18000c5a1  mov     eax, ebx
0x18000c5a3  mov     rbx, [r11+38h]
0x18000c5a7  mov     rbp, [r11+40h]
0x18000c5ab  mov     rsp, r11
0x18000c5ae  pop     r15
0x18000c5b0  pop     r14
0x18000c5b2  pop     r12
0x18000c5b4  pop     rdi
0x18000c5b5  pop     rsi
0x18000c5b6  retn
```
