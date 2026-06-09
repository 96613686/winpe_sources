# InProcProxyEventManager::AddWinEventsForAutomationEvent(int,int,std::unordered_set<uint,std::hash<uint>,std::equal_to<uint>,std::allocator<uint>> &)

- ea: `0x18010b964`
- end: `0x18010bcce`
- name: `?AddWinEventsForAutomationEvent@InProcProxyEventManager@@AEAAXHHAEAV?$unordered_set@IU?$hash@I@std@@U?$equal_to@I@2@V?$allocator@I@2@@std@@@Z`
- size: `874`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18010b850`

## callees

- `0x18002f580`
- `0x180032724`
- `0x180033e04`
- `0x1800785b8`
- `0x1800785e8`
- `0x18010a350`
- `0x18010b964`
- `0x18020aeac`
- `0x1802dd010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18010ba1b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18010ba1b`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18010ba33`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18010ba33`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18010ba9c`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18010ba9c`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18010ba7f`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18010ba7f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18010babf`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18010babf`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18010bc38`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18010bc38`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18010ba4f`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18010ba4f`

## string_xrefs

- `0x18010b9b4`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18010bc23`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18010b9e1`: `onecore\windows\accessibletech\uiautomationcore\proxyeventmanager.cpp`
- `0x18010badd`: `onecore\windows\accessibletech\uiautomationcore\proxyeventmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall InProcProxyEventManager::AddWinEventsForAutomationEvent(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 **v4; // r14
  __int64 v5; // rbx
  __int64 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  SAFEARRAY *v9; // rcx
  HRESULT Vartype; // eax
  int v11; // ebx
  unsigned int v12; // r12d
  unsigned int v13; // edx
  _QWORD *v14; // r14
  _QWORD *v15; // rbx
  _DWORD *v16; // r13
  __int64 v17; // rsi
  unsigned __int64 i; // rcx
  __int64 v19; // r8
  __int64 v20; // rax
  __int64 v21; // rdi
  __int64 v22; // rbx
  __int64 *v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // rdx
  int v29; // [rsp+28h] [rbp-59h]
  LONG plUbound; // [rsp+38h] [rbp-49h] BYREF
  LONG plLbound; // [rsp+3Ch] [rbp-45h] BYREF
  SAFEARRAY *psa; // [rsp+40h] [rbp-41h] BYREF
  SAFEARRAY *v33; // [rsp+48h] [rbp-39h]
  int v34; // [rsp+50h] [rbp-31h]
  void *ppvData; // [rsp+58h] [rbp-29h] BYREF
  __int64 v36; // [rsp+60h] [rbp-21h]
  __int64 v37; // [rsp+68h] [rbp-19h]
  _QWORD *v38; // [rsp+70h] [rbp-11h]
  __int64 v39; // [rsp+78h] [rbp-9h]
  char v40[88]; // [rsp+80h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]
  __int64 pvt; // [rsp+E8h] [rbp+67h] BYREF
  unsigned int v43; // [rsp+F0h] [rbp+6Fh]
  unsigned int v44; // [rsp+F8h] [rbp+77h]
  _QWORD *v45; // [rsp+100h] [rbp+7Fh]

  v45 = a4;
  v44 = a3;
  v43 = a2;
  pvt = a1;
  v4 = (__int64 **)qword_18039E228;
  v37 = qword_18039E228;
  v5 = qword_18039E230;
  v36 = qword_18039E230;
  if ( qword_18039E228 != qword_18039E230 )
  {
    while ( 1 )
    {
      psa = 0;
      v6 = *v4;
      v7 = **v4;
      psa = 0;
      v8 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, SAFEARRAY **))(v7 + 120))(v6, a2, a3, &psa);
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x450,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxyeventmanager.cpp",
          (const char *)(unsigned int)v8,
          v29);
      v9 = psa;
      if ( psa )
        break;
LABEL_5:
      if ( v9 )
        SafeArrayDestroy(v9);
      v37 = (__int64)++v4;
      if ( v4 == (__int64 **)v5 )
        return;
      a3 = v44;
      a2 = v43;
    }
    v34 = 0;
    ppvData = 0;
    v33 = psa;
    if ( SafeArrayGetDim(psa) == 1 )
    {
      LOWORD(pvt) = 0;
      Vartype = SafeArrayGetVartype(v33, (VARTYPE *)&pvt);
      v11 = Vartype;
      if ( Vartype < 0 )
      {
        v27 = 95;
        goto LABEL_44;
      }
      if ( (_WORD)pvt == 19 )
      {
        plLbound = 0;
        plUbound = 0;
        Vartype = SafeArrayGetLBound(v33, 1u, &plLbound);
        v11 = Vartype;
        if ( Vartype < 0 )
        {
          v27 = 111;
        }
        else
        {
          Vartype = SafeArrayGetUBound(v33, 1u, &plUbound);
          v11 = Vartype;
          if ( Vartype < 0 )
          {
            v27 = 112;
          }
          else
          {
            v34 = plUbound - plLbound + 1;
            Vartype = SafeArrayAccessData(v33, &ppvData);
            v11 = Vartype;
            if ( Vartype >= 0 )
            {
              v11 = 0;
LABEL_16:
              if ( v11 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x455,
                  (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxyeventmanager.cpp",
                  (const char *)(unsigned int)v11,
                  v29);
              v12 = 0;
              v13 = v34;
              if ( !v34 )
              {
LABEL_38:
                if ( v33 )
                  SafeArrayUnaccessData(v33);
                v5 = v36;
                v9 = psa;
                goto LABEL_5;
              }
              v14 = v45;
              v15 = v45 + 1;
              while ( 1 )
              {
                v16 = (char *)ppvData + 4 * v12;
                v17 = 0xCBF29CE484222325uLL;
                for ( i = 0; i < 4; ++i )
                  v17 = 0x100000001B3LL * (*((unsigned __int8 *)v16 + i) ^ (unsigned __int64)v17);
                v19 = v14[3];
                v20 = *(_QWORD *)(v19 + 16 * (v17 & v14[6]) + 8);
                v21 = *v15;
                if ( v20 != *v15 )
                {
                  while ( *v16 != *(_DWORD *)(v20 + 16) )
                  {
                    if ( v20 == *(_QWORD *)(v19 + 16 * (v17 & v14[6])) )
                    {
                      v21 = v20;
                      goto LABEL_27;
                    }
                    v20 = *(_QWORD *)(v20 + 8);
                  }
                  goto LABEL_36;
                }
LABEL_27:
                std::_Hash<std::_Uset_traits<enum uiacore::instructions::InstructionType,std::_Uhash_compare<enum uiacore::instructions::InstructionType,std::hash<enum uiacore::instructions::InstructionType>,std::equal_to<enum uiacore::instructions::InstructionType>>,std::allocator<enum uiacore::instructions::InstructionType>,0>>::_Check_max_size(v14);
                v38 = v15;
                v39 = 0;
                v22 = std::_Allocate<16,std::_Default_allocate_traits>(24);
                v39 = v22;
                *(_DWORD *)(v22 + 16) = *v16;
                if ( (unsigned __int8)__Check_rehash_required_1____Hash_V___Umap_traits_HV__variant_UElementOperand__UConnectionBoundObjectOperand__U__PatternOperand_UIInvokeProvider____U__PatternOperand_UISelectionProvider____U__PatternOperand_UIValueProvider____U__PatternOperand_UIRangeValueProvider____U__PatternOperand_UIScrollProvider____U__PatternOperand_UIExpandCollapseProvider____U__PatternOperand_UIGridProvider____U__PatternOperand_UIGridItemProvider____U__PatternOperand_UIMultipleViewProvider____U__PatternOperand_UIWindowProvider____U__PatternOperand_UISelectionItemProvider____U__PatternOperand_UIDockProvider____U__PatternOperand_UITableProvider____U__PatternOperand_UITableItemProvider____U__PatternOperand_UITextProvider____U__PatternOperand_UITextRangeProvider____U__PatternOperand_UIToggleProvider____U__PatternOperand_UITransformProvider____U__PatternOperand_UIScrollItemProvider____U__PatternOperand_UILegacyIAccessibleProvider____U__PatternOperand_UIItemContainerProvider____U__PatternOperand_UIVirtualizedItemProvider____U__PatternOperand_UISynchronizedInputProvider____U__PatternOperand_UIAnnotationProvider____U__PatternOperand_UITextProvider2____U__PatternOperand_UIStylesProvider____U__PatternOperand_UISpreadsheetProvider____U__PatternOperand_UISpreadsheetItemProvider____U__PatternOperand_UITransformProvider2____U__PatternOperand_UITextChildProvider____U__PatternOperand_UIDragProvider____U__PatternOperand_UIDropTargetProvider____U__PatternOperand_UITextEditProvider____U__PatternOperand_UICustomNavigationProvider____U__PatternOperand_UISelectionProvider2____UBoolOperand__UStringOperand__U__NumberOperand_H__U__NumberOperand_I__U__NumberOperand_N__UCharOperand__UPointOperand__URectOperand__UGuidOperand__UArrayOperand__UStringMapOperand__UNullOperand__UNotSupportedOperand__UMixedAttributeOperand__UCacheRequestOperand__UByteArrayOperand___std__V___Uhash_compare_HU__hash_H_std__U__equal_to_H_2__2_V__allocator_U__pair___CBHV__variant_UElementOperand__UConnectionBoundObjectOperand__U__PatternOperand_UIInvokeProvider____U__PatternOperand_UISelectionProvider____U__PatternOperand_UIValueProvider____U__PatternOperand_UIRangeValueProvider____U__PatternOperand_UIScrollProvider____U__PatternOperand_UIExpandCollapseProvider____U__PatternOperand_UIGridProvider____U__PatternOperand_UIGridItemProvider____U__PatternOperand_UIMultipleViewProvider____U__PatternOperand_UIWindowProvider____U__PatternOperand_UISelectionItemProvider____U__PatternOperand_UIDockProvider____U__PatternOperand_UITableProvider____U__PatternOperand_UITableItemProvider____U__PatternOperand_UITextProvider____U__PatternOperand_UITextRangeProvider____U__PatternOperand_UIToggleProvider____U__PatternOperand_UITransformProvider____U__PatternOperand_UIScrollItemProvider____U__PatternOperand_UILegacyIAccessibleProvider____U__PatternOperand_UIItemContainerProvider____U__PatternOperand_UIVirtualizedItemProvider____U__PatternOperand_UISynchronizedInputProvider____U__PatternOperand_UIAnnotationProvider____U__PatternOperand_UITextProvider2____U__PatternOperand_UIStylesProvider____U__PatternOperand_UISpreadsheetProvider____U__PatternOperand_UISpreadsheetItemProvider____U__PatternOperand_UITransformProvider2____U__PatternOperand_UITextChildProvider____U__PatternOperand_UIDragProvider____U__PatternOperand_UIDropTargetProvider____U__PatternOperand_UITextEditProvider____U__PatternOperand_UICustomNavigationProvider____U__PatternOperand_UISelectionProvider2____UBoolOperand__UStringOperand__U__NumberOperand_H__U__NumberOperand_I__U__NumberOperand_N__UCharOperand__UPointOperand__URectOperand__UGuidOperand__UArrayOperand__UStringMapOperand__UNullOperand__UNotSupportedOperand__UMixedAttributeOperand__UCacheRequestOperand__UByteArrayOperand___std___std___2__0A__std___std__IEBA_NXZ(v14) )
                {
                  std::_Hash<std::_Uset_traits<unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<unsigned int>,0>>::_Rehash_for_1(v14);
                  v21 = *(_QWORD *)std::_Hash<std::_Uset_traits<unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<unsigned int>,0>>::_Find_last<unsigned int>(
                                     v14,
                                     v40,
                                     v22 + 16,
                                     v17);
                }
                v39 = 0;
                v23 = *(__int64 **)(v21 + 8);
                ++v14[2];
                *(_QWORD *)v22 = v21;
                *(_QWORD *)(v22 + 8) = v23;
                *v23 = v22;
                *(_QWORD *)(v21 + 8) = v22;
                v24 = 2 * (v17 & v14[6]);
                v25 = v14[3];
                v26 = *(_QWORD *)(v25 + 16 * (v17 & v14[6]));
                if ( v26 == v14[1] )
                {
                  *(_QWORD *)(v25 + 16 * (v17 & v14[6])) = v22;
                }
                else
                {
                  if ( v26 == v21 )
                  {
                    *(_QWORD *)(v25 + 16 * (v17 & v14[6])) = v22;
                    goto LABEL_35;
                  }
                  if ( *(__int64 **)(v25 + 16 * (v17 & v14[6]) + 8) != v23 )
                    goto LABEL_35;
                }
                *(_QWORD *)(v25 + 8 * v24 + 8) = v22;
LABEL_35:
                v13 = v34;
                v15 = v14 + 1;
LABEL_36:
                if ( ++v12 >= v13 )
                {
                  v4 = (__int64 **)v37;
                  goto LABEL_38;
                }
              }
            }
            v27 = 115;
          }
        }
LABEL_44:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v27,
          (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
          (const char *)(unsigned int)Vartype,
          v29);
        goto LABEL_16;
      }
      v28 = 106;
    }
    else
    {
      v28 = 92;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)0x80070057LL,
      v29);
    v11 = -2147024809;
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x18010b964  mov     rax, rsp
0x18010b967  mov     [rax+20h], r9
0x18010b96b  mov     [rax+18h], r8d
0x18010b96f  mov     [rax+10h], edx
0x18010b972  mov     [rax+8], rcx
0x18010b976  push    rbp
0x18010b977  push    rbx
0x18010b978  push    rsi
0x18010b979  push    rdi
0x18010b97a  push    r12
0x18010b97c  push    r13
0x18010b97e  push    r14
0x18010b980  push    r15
0x18010b982  lea     rbp, [rax-5Fh]
0x18010b986  sub     rsp, 98h
0x18010b98d  mov     r14, cs:qword_18039E228
0x18010b994  mov     [rbp+57h+var_70], r14
0x18010b998  mov     rbx, cs:qword_18039E230
0x18010b99f  mov     [rbp+57h+var_78], rbx
0x18010b9a3  cmp     r14, rbx
0x18010b9a6  jz      loc_18010BAEF
0x18010b9ac  xor     r15d, r15d
0x18010b9af  mov     esi, 80070057h
0x18010b9b4  lea     rdi, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x18010b9bb  mov     [rbp+57h+psa], r15
0x18010b9bf  mov     rcx, [r14]
0x18010b9c2  mov     rax, [rcx]
0x18010b9c5  mov     [rbp+57h+psa], r15
0x18010b9c9  lea     r9, [rbp+57h+psa]
0x18010b9cd  mov     rax, [rax+78h]
0x18010b9d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b9d6  mov     rcx, [rbp+5Fh]; this
0x18010b9da  test    eax, eax
0x18010b9dc  jns     short loc_18010B9F3
0x18010b9de  mov     r9d, eax; char *
0x18010b9e1  lea     r8, aOnecoreWindows_67; "onecore\\windows\\accessibletech\\uiaut"...
0x18010b9e8  mov     edx, 450h; void *
0x18010b9ed  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18010b9f3  mov     rcx, [rbp+57h+psa]; psa
0x18010b9f7  test    rcx, rcx
0x18010b9fa  jnz     short loc_18010BA23
0x18010b9fc  test    rcx, rcx
0x18010b9ff  jnz     short loc_18010BA1B
0x18010ba01  add     r14, 8
0x18010ba05  mov     [rbp+57h+var_70], r14
0x18010ba09  cmp     r14, rbx
0x18010ba0c  jz      loc_18010BAEF
0x18010ba12  mov     r8d, [rbp+57h+arg_10]
0x18010ba16  mov     edx, [rbp+57h+arg_8]
0x18010ba19  jmp     short loc_18010B9BB
0x18010ba1b  call    cs:__imp_SafeArrayDestroy
0x18010ba21  jmp     short loc_18010BA01
0x18010ba23  mov     [rbp+57h+var_90], r15
0x18010ba27  mov     [rbp+57h+var_88], r15d
0x18010ba2b  mov     [rbp+57h+ppvData], r15
0x18010ba2f  mov     [rbp+57h+var_90], rcx
0x18010ba33  call    cs:__imp_SafeArrayGetDim
0x18010ba39  cmp     eax, 1
0x18010ba3c  jnz     loc_18010BC73
0x18010ba42  mov     word ptr [rbp+57h+pvt], r15w
0x18010ba47  lea     rdx, [rbp+57h+pvt]; pvt
0x18010ba4b  mov     rcx, [rbp+57h+var_90]; psa
0x18010ba4f  call    cs:__imp_SafeArrayGetVartype
0x18010ba55  mov     ebx, eax
0x18010ba57  test    eax, eax
0x18010ba59  js      loc_18010BC5A
0x18010ba5f  cmp     word ptr [rbp+57h+pvt], 13h
0x18010ba64  jnz     loc_18010BC9C
0x18010ba6a  mov     [rbp+57h+plLbound], r15d
0x18010ba6e  mov     [rbp+57h+plUbound], r15d
0x18010ba72  lea     r8, [rbp+57h+plLbound]; plLbound
0x18010ba76  mov     edx, 1; nDim
0x18010ba7b  mov     rcx, [rbp+57h+var_90]; psa
0x18010ba7f  call    cs:__imp_SafeArrayGetLBound
0x18010ba85  mov     ebx, eax
0x18010ba87  test    eax, eax
0x18010ba89  js      loc_18010BC95
0x18010ba8f  lea     r8, [rbp+57h+plUbound]; plUbound
0x18010ba93  mov     edx, 1; nDim
0x18010ba98  mov     rcx, [rbp+57h+var_90]; psa
0x18010ba9c  call    cs:__imp_SafeArrayGetUBound
0x18010baa2  mov     ebx, eax
0x18010baa4  test    eax, eax
0x18010baa6  js      loc_18010BC8E
0x18010baac  mov     eax, [rbp+57h+plUbound]
0x18010baaf  sub     eax, [rbp+57h+plLbound]
0x18010bab2  inc     eax
0x18010bab4  mov     [rbp+57h+var_88], eax
0x18010bab7  lea     rdx, [rbp+57h+ppvData]; ppvData
0x18010babb  mov     rcx, [rbp+57h+var_90]; psa
0x18010babf  call    cs:__imp_SafeArrayAccessData
0x18010bac5  mov     ebx, eax
0x18010bac7  test    eax, eax
0x18010bac9  js      loc_18010BCA3
0x18010bacf  mov     ebx, r15d
0x18010bad2  mov     rcx, [rbp+5Fh]; this
0x18010bad6  test    ebx, ebx
0x18010bad8  jns     short loc_18010BB03
0x18010bada  mov     r9d, ebx; char *
0x18010badd  lea     r8, aOnecoreWindows_67; "onecore\\windows\\accessibletech\\uiaut"...
0x18010bae4  mov     edx, 455h; void *
0x18010bae9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18010baef  add     rsp, 98h
0x18010baf6  pop     r15
0x18010baf8  pop     r14
0x18010bafa  pop     r13
0x18010bafc  pop     r12
0x18010bafe  pop     rdi
0x18010baff  pop     rsi
0x18010bb00  pop     rbx
0x18010bb01  pop     rbp
0x18010bb02  retn
0x18010bb03  mov     r12d, r15d
0x18010bb06  mov     edx, [rbp+57h+var_88]
0x18010bb09  test    edx, edx
0x18010bb0b  jz      loc_18010BC2F
0x18010bb11  mov     r14, [rbp+57h+arg_18]
0x18010bb15  lea     rbx, [r14+8]
0x18010bb19  mov     ecx, r12d
0x18010bb1c  mov     rax, [rbp+57h+ppvData]
0x18010bb20  lea     r13, [rax+rcx*4]
0x18010bb24  mov     rsi, 0CBF29CE484222325h
0x18010bb2e  mov     rcx, r15
0x18010bb31  movzx   eax, byte ptr [rcx+r13]
0x18010bb36  xor     rsi, rax
0x18010bb39  mov     r8, 100000001B3h
0x18010bb43  imul    rsi, r8
0x18010bb47  inc     rcx
0x18010bb4a  cmp     rcx, 4
0x18010bb4e  jb      short loc_18010BB31
0x18010bb50  mov     rcx, [r14+30h]
0x18010bb54  and     rcx, rsi
0x18010bb57  add     rcx, rcx
0x18010bb5a  mov     r8, [r14+18h]
0x18010bb5e  mov     rax, [r8+rcx*8+8]
0x18010bb63  mov     rdi, [rbx]
0x18010bb66  cmp     rax, rdi
0x18010bb69  jz      short loc_18010BB88
0x18010bb6b  mov     r9, [r8+rcx*8]
0x18010bb6f  mov     ecx, [r13+0]
0x18010bb73  cmp     ecx, [rax+10h]
0x18010bb76  jz      loc_18010BC13
0x18010bb7c  cmp     rax, r9
0x18010bb7f  jnz     loc_18010BC4B
0x18010bb85  mov     rdi, rax
0x18010bb88  mov     rcx, r14
0x18010bb8b  call    ?_Check_max_size@?$_Hash@V?$_Uset_traits@W4InstructionType@instructions@uiacore@@V?$_Uhash_compare@W4InstructionType@instructions@uiacore@@U?$hash@W4InstructionType@instructions@uiacore@@@std@@U?$equal_to@W4InstructionType@instructions@uiacore@@@5@@std@@V?$allocator@W4InstructionType@instructions@uiacore@@@5@$0A@@std@@@std@@IEBAXXZ; std::_Hash<std::_Uset_traits<uiacore::instructions::InstructionType,std::_Uhash_compare<uiacore::instructions::InstructionType,std::hash<uiacore::instructions::InstructionType>,std::equal_to<uiacore::instructions::InstructionType>>,std::allocator<uiacore::instructions::InstructionType>,0>>::_Check_max_size(void)
0x18010bb90  mov     [rbp+57h+var_68], rbx
0x18010bb94  mov     [rbp+57h+var_60], r15
0x18010bb98  mov     ecx, 18h
0x18010bb9d  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18010bba2  mov     rbx, rax
0x18010bba5  mov     [rbp+57h+var_60], rax
0x18010bba9  mov     ecx, [r13+0]
0x18010bbad  mov     [rax+10h], ecx
0x18010bbb0  mov     rcx, r14
0x18010bbb3  call    ?_Check_rehash_required_1@?$_Hash@V?$_Umap_traits@HV?$variant@UElementOperand@@UConnectionBoundObjectOperand@@U?$PatternOperand@UIInvokeProvider@@@@U?$PatternOperand@UISelectionProvider@@@@U?$PatternOperand@UIValueProvider@@@@U?$PatternOperand@UIRangeValueProvider@@@@U?$PatternOperand@UIScrollProvider@@@@U?$PatternOperand@UIExpandCollapseProvider@@@@U?$PatternOperand@UIGridProvider@@@@U?$PatternOperand@UIGridItemProvider@@@@U?$PatternOperand@UIMultipleViewProvider@@@@U?$PatternOperand@UIWindowProvider@@@@U?$PatternOperand@UISelectionItemProvider@@@@U?$PatternOperand@UIDockProvider@@@@U?$PatternOperand@UITableProvider@@@@U?$PatternOperand@UITableItemProvider@@@@U?$PatternOperand@UITextProvider@@@@U?$PatternOperand@UITextRangeProvider@@@@U?$PatternOperand@UIToggleProvider@@@@U?$PatternOperand@UITransformProvider@@@@U?$PatternOperand@UIScrollItemProvider@@@@U?$PatternOperand@UILegacyIAccessibleProvider@@@@U?$PatternOperand@UIItemContainerProvider@@@@U?$PatternOperand@UIVirtualizedItemProvider@@@@U?$PatternOperand@UISynchronizedInputProvider@@@@U?$PatternOperand@UIAnnotationProvider@@@@U?$PatternOperand@UITextProvider2@@@@U?$PatternOperand@UIStylesProvider@@@@U?$PatternOperand@UISpreadsheetProvider@@@@U?$PatternOperand@UISpreadsheetItemProvider@@@@U?$PatternOperand@UITransformProvider2@@@@U?$PatternOperand@UITextChildProvider@@@@U?$PatternOperand@UIDragProvider@@@@U?$PatternOperand@UIDropTargetProvider@@@@U?$PatternOperand@UITextEditProvider@@@@U?$PatternOperand@UICustomNavigationProvider@@@@U?$PatternOperand@UISelectionProvider2@@@@UBoolOperand@@UStringOperand@@U?$NumberOperand@H@@U?$NumberOperand@I@@U?$NumberOperand@N@@UCharOperand@@UPointOperand@@URectOperand@@UGuidOperand@@UArrayOperand@@UStringMapOperand@@UNullOperand@@UNotSupportedOperand@@UMixedAttributeOperand@@UCacheRequestOperand@@UByteArrayOperand@@@std@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@2@V?$allocator@U?$pair@$$CBHV?$variant@UElementOperand@@UConnectionBoundObjectOperand@@U?$PatternOperand@UIInvokeProvider@@@@U?$PatternOperand@UISelectionProvider@@@@U?$PatternOperand@UIValueProvider@@@@U?$PatternOperand@UIRangeValueProvider@@@@U?$PatternOperand@UIScrollProvider@@@@U?$PatternOperand@UIExpandCollapseProvider@@@@U?$PatternOperand@UIGridProvider@@@@U?$PatternOperand@UIGridItemProvider@@@@U?$PatternOperand@UIMultipleViewProvider@@@@U?$PatternOperand@UIWindowProvider@@@@U?$PatternOperand@UISelectionItemProvider@@@@U?$PatternOperand@UIDockProvider@@@@U?$PatternOperand@UITableProvider@@@@U?$PatternOperand@UITableItemProvider@@@@U?$PatternOperand@UITextProvider@@@@U?$PatternOperand@UITextRangeProvider@@@@U?$PatternOperand@UIToggleProvider@@@@U?$PatternOperand@UITransformProvider@@@@U?$PatternOperand@UIScrollItemProvider@@@@U?$PatternOperand@UILegacyIAccessibleProvider@@@@U?$PatternOperand@UIItemContainerProvider@@@@U?$PatternOperand@UIVirtualizedItemProvider@@@@U?$PatternOperand@UISynchronizedInputProvider@@@@U?$PatternOperand@UIAnnotationProvider@@@@U?$PatternOperand@UITextProvider2@@@@U?$PatternOperand@UIStylesProvider@@@@U?$PatternOperand@UISpreadsheetProvider@@@@U?$PatternOperand@UISpreadsheetItemProvider@@@@U?$PatternOperand@UITransformProvider2@@@@U?$PatternOperand@UITextChildProvider@@@@U?$PatternOperand@UIDragProvider@@@@U?$PatternOperand@UIDropTargetProvider@@@@U?$PatternOperand@UITextEditProvider@@@@U?$PatternOperand@UICustomNavigationProvider@@@@U?$PatternOperand@UISelectionProvider2@@@@UBoolOperand@@UStringOperand@@U?$NumberOperand@H@@U?$NumberOperand@I@@U?$NumberOperand@N@@UCharOperand@@UPointOperand@@URectOperand@@UGuidOperand@@UArrayOperand@@UStringMapOperand@@UNullOperand@@UNotSupportedOperand@@UMixedAttributeOperand@@UCacheRequestOperand@@UByteArrayOperand@@@std@@@std@@@2@$0A@@std@@@std@@IEBA_NXZ
0x18010bbb8  test    al, al
0x18010bbba  jnz     loc_18010BCAA
0x18010bbc0  xor     r15d, r15d
0x18010bbc3  mov     [rbp+57h+var_60], r15
0x18010bbc7  mov     rdx, [rdi+8]
0x18010bbcb  inc     qword ptr [r14+10h]
0x18010bbcf  mov     [rbx], rdi
0x18010bbd2  mov     [rbx+8], rdx
0x18010bbd6  mov     [rdx], rbx
0x18010bbd9  mov     [rdi+8], rbx
0x18010bbdd  mov     rax, [r14+30h]
0x18010bbe1  and     rax, rsi
0x18010bbe4  add     rax, rax
0x18010bbe7  mov     rcx, [r14+18h]
0x18010bbeb  mov     r8, [rcx+rax*8]
0x18010bbef  cmp     r8, [r14+8]
0x18010bbf3  jz      short loc_18010BC03
0x18010bbf5  cmp     r8, rdi
0x18010bbf8  jz      short loc_18010BC54
0x18010bbfa  cmp     [rcx+rax*8+8], rdx
0x18010bbff  jz      short loc_18010BC07
0x18010bc01  jmp     short loc_18010BC0C
0x18010bc03  mov     [rcx+rax*8], rbx
0x18010bc07  mov     [rcx+rax*8+8], rbx
0x18010bc0c  mov     edx, [rbp+57h+var_88]
0x18010bc0f  lea     rbx, [r14+8]
0x18010bc13  inc     r12d
0x18010bc16  cmp     r12d, edx
0x18010bc19  jb      loc_18010BB19
0x18010bc1f  mov     r14, [rbp+57h+var_70]
0x18010bc23  lea     rdi, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x18010bc2a  mov     esi, 80070057h
0x18010bc2f  mov     rcx, [rbp+57h+var_90]; psa
0x18010bc33  test    rcx, rcx
0x18010bc36  jz      short loc_18010BC3E
0x18010bc38  call    cs:__imp_SafeArrayUnaccessData
0x18010bc3e  mov     rbx, [rbp+57h+var_78]
0x18010bc42  mov     rcx, [rbp+57h+psa]
0x18010bc46  jmp     loc_18010B9FC
0x18010bc4b  mov     rax, [rax+8]
0x18010bc4f  jmp     loc_18010BB73
0x18010bc54  mov     [rcx+rax*8], rbx
0x18010bc58  jmp     short loc_18010BC0C
0x18010bc5a  mov     edx, 5Fh ; '_'; void *
0x18010bc5f  mov     r8, rdi; unsigned int
0x18010bc62  mov     r9d, eax; char *
0x18010bc65  mov     rcx, [rbp+5Fh]; this
0x18010bc69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010bc6e  jmp     loc_18010BAD2
0x18010bc73  mov     edx, 5Ch ; '\'; void *
0x18010bc78  mov     r8, rdi; unsigned int
0x18010bc7b  mov     r9d, esi; char *
0x18010bc7e  mov     rcx, [rbp+5Fh]; this
0x18010bc82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010bc87  mov     ebx, esi
0x18010bc89  jmp     loc_18010BAD2
0x18010bc8e  mov     edx, 70h ; 'p'
0x18010bc93  jmp     short loc_18010BC5F
0x18010bc95  mov     edx, 6Fh ; 'o'
0x18010bc9a  jmp     short loc_18010BC5F
0x18010bc9c  mov     edx, 6Ah ; 'j'
0x18010bca1  jmp     short loc_18010BC78
0x18010bca3  mov     edx, 73h ; 's'
0x18010bca8  jmp     short loc_18010BC5F
0x18010bcaa  mov     rcx, r14
0x18010bcad  call    ?_Rehash_for_1@?$_Hash@V?$_Uset_traits@IV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@I@2@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Uset_traits<uint,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<uint>,0>>::_Rehash_for_1(void)
0x18010bcb2  mov     r9, rsi
0x18010bcb5  lea     r8, [rbx+10h]
0x18010bcb9  lea     rdx, [rbp+57h+var_58]
0x18010bcbd  mov     rcx, r14
0x18010bcc0  call    ??$_Find_last@I@?$_Hash@V?$_Uset_traits@IV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@I@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@IPEAX@std@@@1@AEBI_K@Z; std::_Hash<std::_Uset_traits<uint,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<uint>,0>>::_Find_last<uint>(uint const &,unsigned __int64)
0x18010bcc5  mov     rdi, [rax]
0x18010bcc8  jmp     loc_18010BBC0
```
