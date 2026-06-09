# CPropertyBag::HrRemoveProperty(_GUID const *,_GUID const *,_XWIZARD_PROPERTY_KEY const *,void * * const,ulong * const,ulong * const,ulong * const)

- ea: `0x18002ad04`
- end: `0x18002ae79`
- name: `?HrRemoveProperty@CPropertyBag@@QEAAJPEBU_GUID@@0PEBU_XWIZARD_PROPERTY_KEY@@QEAPEAXQEAK33@Z`
- size: `373`
- prototype: `int(CPropertyBag *__hidden this, const struct _GUID *, const struct _GUID *, const struct _XWIZARD_PROPERTY_KEY *, void **const, unsigned int *const, unsigned int *const, unsigned int *const)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002a0a0`

## callees

- `0x18000ae04`
- `0x18002a854`
- `0x18002aadc`
- `0x18002ad04`
- `0x18002b424`
- `0x18002b6ec`
- `0x180032a02`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ae1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ae1e`

## pseudocode

```c
__int64 __fastcall CPropertyBag::HrRemoveProperty(
        CPropertyBag *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        const struct _XWIZARD_PROPERTY_KEY *a4,
        void **const a5,
        unsigned int *const a6,
        unsigned int *const a7,
        unsigned int *const a8)
{
  unsigned int Property; // ebp
  __int64 v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 i; // rdx
  __int64 v15; // rcx
  CPropertyBag *v16; // rcx
  const struct _XWIZARD_PROPERTY_KEY *v18; // [rsp+40h] [rbp-38h] BYREF
  _QWORD v19[6]; // [rsp+48h] [rbp-30h] BYREF

  Property = CPropertyBag::HrGetProperty(this, a2, a3, a4, a5, a6, a7, a8);
  if ( !Property )
  {
    v18 = a4;
    std::_Tree<std::_Tmap_traits<_XWIZARD_PROPERTY_KEY *,_XWIZARD_PROPERTY_ELEMENT *,CKey_Less,std::allocator<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>>,0>>::find(
      this,
      v19,
      &v18);
    v11 = v19[0];
    if ( v19[0] == **(_QWORD **)this )
    {
      memset_0(a4, 0, Property + 120);
    }
    else
    {
      v12 = v19[0];
      if ( *(_BYTE *)(v19[0] + 25LL) )
      {
        v13 = *(_QWORD *)(v19[0] + 16LL);
      }
      else
      {
        v13 = *(_QWORD *)v19[0];
        if ( *(_BYTE *)(*(_QWORD *)v19[0] + 25LL) )
        {
          for ( i = *(_QWORD *)(v19[0] + 8LL); !*(_BYTE *)(i + 25) && v12 == *(_QWORD *)i; i = *(_QWORD *)(i + 8) )
            v12 = i;
          v13 = v12;
          if ( !*(_BYTE *)(v12 + 25) )
            v13 = i;
        }
        else
        {
          while ( !*(_BYTE *)(*(_QWORD *)(v13 + 16) + 25LL) )
            v13 = *(_QWORD *)(v13 + 16);
        }
      }
      v15 = *(_QWORD *)(v13 + 32);
      *(_OWORD *)a4 = *(_OWORD *)v15;
      *((_OWORD *)a4 + 1) = *(_OWORD *)(v15 + 16);
      *((_OWORD *)a4 + 2) = *(_OWORD *)(v15 + 32);
      *((_OWORD *)a4 + 3) = *(_OWORD *)(v15 + 48);
      *((_OWORD *)a4 + 4) = *(_OWORD *)(v15 + 64);
      *((_OWORD *)a4 + 5) = *(_OWORD *)(v15 + 80);
      *((_OWORD *)a4 + 6) = *(_OWORD *)(v15 + 96);
      *((_QWORD *)a4 + 14) = *(_QWORD *)(v15 + 112);
    }
    CoTaskMemFree(*(LPVOID *)(v11 + 32));
    CPropertyBag::FreePropertyElement(v16, (LPVOID *)(v11 + 40));
    std::_Tree<std::_Tmap_traits<_XWIZARD_PROPERTY_KEY *,_XWIZARD_PROPERTY_ELEMENT *,CKey_Less,std::allocator<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>>,0>>::erase(
      this,
      v19,
      v11);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_68d45ddfb6663f942b433d9c5d20cdd0_Traceguids, Property);
  return Property;
}

```

## disassembly

```asm
0x18002ad04  mov     r11, rsp
0x18002ad07  push    rbx
0x18002ad08  push    rbp
0x18002ad09  push    rsi
0x18002ad0a  push    rdi
0x18002ad0b  sub     rsp, 58h
0x18002ad0f  mov     rax, [rsp+78h+arg_38]
0x18002ad17  mov     rdi, r9
0x18002ad1a  mov     [r11-40h], rax
0x18002ad1e  mov     rsi, rcx
0x18002ad21  mov     rax, [rsp+78h+arg_30]
0x18002ad29  mov     [r11-48h], rax
0x18002ad2d  mov     rax, [rsp+78h+arg_28]
0x18002ad35  mov     [r11-50h], rax
0x18002ad39  mov     rax, [rsp+78h+arg_20]
0x18002ad41  mov     [r11-58h], rax
0x18002ad45  call    ?HrGetProperty@CPropertyBag@@QEAAJPEBU_GUID@@0PEBU_XWIZARD_PROPERTY_KEY@@QEAPEAXQEAK33@Z; CPropertyBag::HrGetProperty(_GUID const *,_GUID const *,_XWIZARD_PROPERTY_KEY const *,void * * const,ulong * const,ulong * const,ulong * const)
0x18002ad4a  mov     ebp, eax
0x18002ad4c  test    eax, eax
0x18002ad4e  jnz     loc_18002AE3D
0x18002ad54  lea     r8, [rsp+78h+var_38]
0x18002ad59  mov     [rsp+78h+var_38], rdi
0x18002ad5e  lea     rdx, [rsp+78h+var_30]
0x18002ad63  mov     rcx, rsi
0x18002ad66  call    ?find@?$_Tree@V?$_Tmap_traits@PEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@VCKey_Less@@V?$allocator@U?$pair@QEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@std@@@std@@@std@@@2@AEBQEAU_XWIZARD_PROPERTY_KEY@@@Z; std::_Tree<std::_Tmap_traits<_XWIZARD_PROPERTY_KEY *,_XWIZARD_PROPERTY_ELEMENT *,CKey_Less,std::allocator<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>>,0>>::find(_XWIZARD_PROPERTY_KEY * const &)
0x18002ad6b  mov     rcx, [rsi]
0x18002ad6e  mov     rbx, [rsp+78h+var_30]
0x18002ad73  cmp     rbx, [rcx]
0x18002ad76  jnz     short loc_18002AD8B
0x18002ad78  xor     edx, edx; Val
0x18002ad7a  lea     r8d, [rbp+78h]; Size
0x18002ad7e  mov     rcx, rdi; void *
0x18002ad81  call    memset_0
0x18002ad86  jmp     loc_18002AE1A
0x18002ad8b  cmp     byte ptr [rbx+19h], 0
0x18002ad8f  mov     rcx, rbx
0x18002ad92  jz      short loc_18002AD9A
0x18002ad94  mov     rax, [rbx+10h]
0x18002ad98  jmp     short loc_18002ADD6
0x18002ad9a  mov     rax, [rbx]
0x18002ad9d  cmp     byte ptr [rax+19h], 0
0x18002ada1  jz      short loc_18002ADAD
0x18002ada3  mov     rdx, [rbx+8]
0x18002ada7  jmp     short loc_18002ADC5
0x18002ada9  mov     rax, [rax+10h]
0x18002adad  mov     rcx, [rax+10h]
0x18002adb1  cmp     byte ptr [rcx+19h], 0
0x18002adb5  jz      short loc_18002ADA9
0x18002adb7  jmp     short loc_18002ADD6
0x18002adb9  cmp     rcx, [rdx]
0x18002adbc  jnz     short loc_18002ADCB
0x18002adbe  mov     rcx, rdx
0x18002adc1  mov     rdx, [rdx+8]
0x18002adc5  cmp     byte ptr [rdx+19h], 0
0x18002adc9  jz      short loc_18002ADB9
0x18002adcb  cmp     byte ptr [rcx+19h], 0
0x18002adcf  mov     rax, rcx
0x18002add2  cmovz   rax, rdx
0x18002add6  mov     rcx, [rax+20h]
0x18002adda  movups  xmm0, xmmword ptr [rcx]
0x18002addd  movups  xmmword ptr [rdi], xmm0
0x18002ade0  movups  xmm1, xmmword ptr [rcx+10h]
0x18002ade4  movups  xmmword ptr [rdi+10h], xmm1
0x18002ade8  movups  xmm0, xmmword ptr [rcx+20h]
0x18002adec  movups  xmmword ptr [rdi+20h], xmm0
0x18002adf0  movups  xmm1, xmmword ptr [rcx+30h]
0x18002adf4  movups  xmmword ptr [rdi+30h], xmm1
0x18002adf8  movups  xmm0, xmmword ptr [rcx+40h]
0x18002adfc  movups  xmmword ptr [rdi+40h], xmm0
0x18002ae00  movups  xmm1, xmmword ptr [rcx+50h]
0x18002ae04  movups  xmmword ptr [rdi+50h], xmm1
0x18002ae08  movups  xmm0, xmmword ptr [rcx+60h]
0x18002ae0c  movups  xmmword ptr [rdi+60h], xmm0
0x18002ae10  movsd   xmm1, qword ptr [rcx+70h]
0x18002ae15  movsd   qword ptr [rdi+70h], xmm1
0x18002ae1a  mov     rcx, [rbx+20h]; pv
0x18002ae1e  call    cs:__imp_CoTaskMemFree
0x18002ae24  lea     rdx, [rbx+28h]; struct _XWIZARD_PROPERTY_ELEMENT **
0x18002ae28  call    ?FreePropertyElement@CPropertyBag@@AEAAXPEAPEAU_XWIZARD_PROPERTY_ELEMENT@@@Z; CPropertyBag::FreePropertyElement(_XWIZARD_PROPERTY_ELEMENT * *)
0x18002ae2d  mov     r8, rbx
0x18002ae30  lea     rdx, [rsp+78h+var_30]
0x18002ae35  mov     rcx, rsi
0x18002ae38  call    ?erase@?$_Tree@V?$_Tmap_traits@PEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@VCKey_Less@@V?$allocator@U?$pair@QEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<_XWIZARD_PROPERTY_KEY *,_XWIZARD_PROPERTY_ELEMENT *,CKey_Less,std::allocator<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>>>>)
0x18002ae3d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae44  lea     rax, WPP_GLOBAL_Control
0x18002ae4b  cmp     rcx, rax
0x18002ae4e  jz      short loc_18002AE6E
0x18002ae50  test    byte ptr [rcx+1Ch], 10h
0x18002ae54  jz      short loc_18002AE6E
0x18002ae56  mov     rcx, [rcx+10h]
0x18002ae5a  lea     r8, WPP_68d45ddfb6663f942b433d9c5d20cdd0_Traceguids
0x18002ae61  mov     edx, 16h
0x18002ae66  mov     r9d, ebp
0x18002ae69  call    WPP_SF_d
0x18002ae6e  mov     eax, ebp
0x18002ae70  add     rsp, 58h
0x18002ae74  pop     rdi
0x18002ae75  pop     rsi
0x18002ae76  pop     rbp
0x18002ae77  pop     rbx
0x18002ae78  retn
```
