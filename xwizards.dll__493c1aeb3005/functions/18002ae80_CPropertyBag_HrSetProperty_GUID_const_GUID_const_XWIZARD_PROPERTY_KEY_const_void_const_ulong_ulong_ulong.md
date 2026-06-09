# CPropertyBag::HrSetProperty(_GUID const *,_GUID const *,_XWIZARD_PROPERTY_KEY const *,void * const,ulong,ulong,ulong)

- ea: `0x18002ae80`
- end: `0x18002b22f`
- name: `?HrSetProperty@CPropertyBag@@QEAAJPEBU_GUID@@0PEBU_XWIZARD_PROPERTY_KEY@@QEAXKKK@Z`
- size: `943`
- prototype: `__int64 __fastcall(CPropertyBag *__hidden this, const struct _GUID *, const struct _GUID *, const struct _XWIZARD_PROPERTY_KEY *, void *const Src, size_t Size, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002a180`

## callees

- `0x180002556`
- `0x18000ae04`
- `0x18002a200`
- `0x18002a398`
- `0x18002a7ec`
- `0x18002a854`
- `0x18002ae80`
- `0x18002b6ec`
- `0x18002b73c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002aecc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002af4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002afbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002aecc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002af4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002afbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b1ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b1e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b1ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b1e3`

## pseudocode

```c
__int64 __fastcall CPropertyBag::HrSetProperty(
        void *const *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        const struct _XWIZARD_PROPERTY_KEY *a4,
        _QWORD *Src,
        size_t Size,
        unsigned int a7,
        unsigned int a8)
{
  char *v11; // r15
  __int64 v12; // rsi
  char *v13; // rax
  unsigned int v14; // esi
  PVOID *v15; // rcx
  _DWORD *v16; // rax
  void *v17; // r14
  _OWORD *v18; // rax
  _OWORD *v19; // r12
  __int64 v20; // rcx
  _QWORD *v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rdx
  struct _XWIZARD_PROPERTY_ELEMENT **v24; // rsi
  struct _XWIZARD_PROPERTY_ELEMENT *v25; // rax
  CPropertyBag *v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // r9
  struct _XWIZARD_PROPERTY_ELEMENT **v32; // [rsp+30h] [rbp-58h] BYREF
  char *v33; // [rsp+38h] [rbp-50h]
  void *v34; // [rsp+40h] [rbp-48h]
  _QWORD v35[3]; // [rsp+48h] [rbp-40h] BYREF

  v11 = 0;
  v33 = 0;
  if ( !Src )
  {
    LODWORD(v12) = Size;
    goto LABEL_9;
  }
  v12 = (unsigned int)Size;
  if ( !(_DWORD)Size )
  {
LABEL_9:
    v16 = CoTaskMemAlloc(0x18u);
    v17 = v16;
    v34 = v16;
    if ( !v16 )
    {
      v14 = -2147024882;
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_41;
      v23 = 14;
LABEL_38:
      v30 = 2147942414LL;
LABEL_39:
      WPP_SF_d(v15[2], v23, WPP_68d45ddfb6663f942b433d9c5d20cdd0_Traceguids, v30);
LABEL_40:
      v15 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_41;
    }
    *((_QWORD *)v16 + 1) = 0;
    *((_QWORD *)v16 + 2) = 0;
    v16[1] = a7;
    *v16 = a8;
    if ( v11 )
    {
      v16[2] = v12 + 2;
      *((_QWORD *)v16 + 2) = v11;
    }
    Src = a4;
    std::_Tree<std::_Tmap_traits<_XWIZARD_PROPERTY_KEY *,_XWIZARD_PROPERTY_ELEMENT *,CKey_Less,std::allocator<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>>,0>>::find(
      this,
      &v32,
      &Src);
    if ( v32 == *(struct _XWIZARD_PROPERTY_ELEMENT ***)this )
    {
      v14 = 0;
      v18 = CoTaskMemAlloc(0x78u);
      v19 = v18;
      v32 = (struct _XWIZARD_PROPERTY_ELEMENT **)v18;
      if ( v18 )
      {
        *v18 = *(_OWORD *)a4;
        v18[1] = *((_OWORD *)a4 + 1);
        v18[2] = *((_OWORD *)a4 + 2);
        v18[3] = *((_OWORD *)a4 + 3);
        v18[4] = *((_OWORD *)a4 + 4);
        v18[5] = *((_OWORD *)a4 + 5);
        v18[6] = *((_OWORD *)a4 + 6);
        *((_QWORD *)v18 + 14) = *((_QWORD *)a4 + 14);
        std::_Tree<std::_Tmap_traits<_XWIZARD_PROPERTY_KEY *,_XWIZARD_PROPERTY_ELEMENT *,CKey_Less,std::allocator<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>>,0>>::lower_bound(
          this,
          &Src,
          &v32);
        v21 = Src;
        if ( Src == *(_QWORD **)this || (unsigned __int8)CKey_Less::operator()(v20, v19, Src[4]) )
        {
          try
          {
            v35[0] = v19;
            v35[1] = 0;
            v22 = std::_Tree_buy<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>>::_Buynode<std::pair<_XWIZARD_PROPERTY_KEY *,_XWIZARD_PROPERTY_ELEMENT *>>(
                    this,
                    v35);
            std::_Tree<std::_Tmap_traits<_XWIZARD_PROPERTY_KEY *,_XWIZARD_PROPERTY_ELEMENT *,CKey_Less,std::allocator<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>>,0>>::_Insert_hint<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *> &,std::_Tree_node<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>,void *> *>(
              (_DWORD)this,
              (unsigned int)&Src,
              (_DWORD)v21,
              v22 + 32,
              v22);
            v21 = Src;
          }
          catch ( std::bad_alloc )
          {
            LODWORD(Src) = -2147024882;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                16,
                WPP_68d45ddfb6663f942b433d9c5d20cdd0_Traceguids,
                2147942414LL);
            CoTaskMemFree(v32);
            v14 = (unsigned int)Src;
            v11 = v33;
            v17 = v34;
            goto LABEL_40;
          }
        }
        v21[5] = v17;
        goto LABEL_45;
      }
      v14 = -2147024882;
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
LABEL_41:
        if ( v11 )
        {
          CoTaskMemFree(v11);
          v15 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( !v17 )
          goto LABEL_46;
        CoTaskMemFree(v17);
        goto LABEL_45;
      }
      v23 = 17;
      goto LABEL_38;
    }
    v24 = v32 + 5;
    v25 = v32[5];
    v23 = 15;
    v26 = (CPropertyBag *)(*((_DWORD *)v25 + 1) & 0xF);
    if ( (*((_DWORD *)v25 + 1) & 0xF) == 0 || (_DWORD)v26 == 1 )
    {
      v27 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)a4;
      if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)a4 )
        v27 = *(_QWORD *)GUID_NULL.Data4 - *((_QWORD *)a4 + 1);
      if ( v27 )
      {
        v26 = (CPropertyBag *)a2;
        v28 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&a3->Data1;
        if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&a3->Data1 )
          v28 = *(_QWORD *)a2->Data4 - *(_QWORD *)a3->Data4;
        if ( v28 )
        {
          v29 = *(_QWORD *)&a3->Data1 - *(_QWORD *)a4;
          if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)a4 )
            v29 = *(_QWORD *)a3->Data4 - *((_QWORD *)a4 + 1);
          if ( v29 )
          {
            v14 = -2147024891;
            v15 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
              goto LABEL_41;
            v30 = 2147942405LL;
            goto LABEL_39;
          }
        }
      }
    }
    CPropertyBag::FreePropertyElement(v26, v24);
    *v24 = (struct _XWIZARD_PROPERTY_ELEMENT *)v17;
    v14 = 1;
LABEL_45:
    v15 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_46;
  }
  v13 = (char *)CoTaskMemAlloc((unsigned int)Size + 2LL);
  v11 = v13;
  v33 = v13;
  if ( v13 )
  {
    memcpy_0(v13, Src, (unsigned int)v12);
    *(_WORD *)&v11[v12] = 0;
    goto LABEL_9;
  }
  v14 = -2147024882;
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v14;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_68d45ddfb6663f942b433d9c5d20cdd0_Traceguids, 2147942414LL);
    goto LABEL_45;
  }
LABEL_46:
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 0x10) != 0 )
    WPP_SF_d(v15[2], 18, WPP_68d45ddfb6663f942b433d9c5d20cdd0_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x18002ae80  mov     [rsp+arg_0], rbx
0x18002ae85  mov     [rsp+arg_10], rsi
0x18002ae8a  mov     [rsp+arg_8], rdx
0x18002ae8f  push    rdi
0x18002ae90  push    r12
0x18002ae92  push    r13
0x18002ae94  push    r14
0x18002ae96  push    r15
0x18002ae98  sub     rsp, 60h
0x18002ae9c  mov     rbx, r9
0x18002ae9f  mov     r12, r8
0x18002aea2  mov     r13, rcx
0x18002aea5  xor     edi, edi
0x18002aea7  mov     r15d, edi
0x18002aeaa  mov     [rsp+88h+var_50], rdi
0x18002aeaf  cmp     [rsp+88h+Src], rdi
0x18002aeb7  jz      loc_18002AF3F
0x18002aebd  mov     esi, dword ptr [rsp+88h+Size]
0x18002aec4  test    esi, esi
0x18002aec6  jz      short loc_18002AF46
0x18002aec8  lea     rcx, [rsi+2]; cb
0x18002aecc  call    cs:__imp_CoTaskMemAlloc
0x18002aed2  mov     r15, rax
0x18002aed5  mov     [rsp+88h+var_50], rax
0x18002aeda  test    rax, rax
0x18002aedd  jz      short loc_18002AEF9
0x18002aedf  mov     r8d, esi; Size
0x18002aee2  mov     rdx, [rsp+88h+Src]; Src
0x18002aeea  mov     rcx, rax; void *
0x18002aeed  call    memcpy_0
0x18002aef2  mov     [rsi+r15], di
0x18002aef7  jmp     short loc_18002AF46
0x18002aef9  mov     esi, 8007000Eh
0x18002aefe  lea     rbx, WPP_GLOBAL_Control
0x18002af05  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af0c  cmp     rcx, rbx
0x18002af0f  jz      loc_18002B213
0x18002af15  test    byte ptr [rcx+1Ch], 4
0x18002af19  jz      loc_18002B1F0
0x18002af1f  mov     edx, 0Dh
0x18002af24  mov     r9d, 8007000Eh
0x18002af2a  lea     r8, WPP_68d45ddfb6663f942b433d9c5d20cdd0_Traceguids
0x18002af31  mov     rcx, [rcx+10h]
0x18002af35  call    WPP_SF_d
0x18002af3a  jmp     loc_18002B1E9
0x18002af3f  mov     esi, dword ptr [rsp+88h+Size]
0x18002af46  mov     ecx, 18h; cb
0x18002af4b  call    cs:__imp_CoTaskMemAlloc
0x18002af51  mov     r14, rax
0x18002af54  mov     [rsp+88h+var_48], rax
0x18002af59  test    rax, rax
0x18002af5c  jz      loc_18002B186
0x18002af62  mov     [rax+8], rdi
0x18002af66  mov     [rax+10h], rdi
0x18002af6a  mov     ecx, [rsp+88h+arg_30]
0x18002af71  mov     [rax+4], ecx
0x18002af74  mov     ecx, [rsp+88h+arg_38]
0x18002af7b  mov     [rax], ecx
0x18002af7d  test    r15, r15
0x18002af80  jz      short loc_18002AF8C
0x18002af82  lea     ecx, [rsi+2]
0x18002af85  mov     [rax+8], ecx
0x18002af88  mov     [rax+10h], r15
0x18002af8c  mov     [rsp+88h+Src], rbx
0x18002af94  lea     r8, [rsp+88h+Src]
0x18002af9c  lea     rdx, [rsp+88h+var_58]
0x18002afa1  mov     rcx, r13
0x18002afa4  call    ?find@?$_Tree@V?$_Tmap_traits@PEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@VCKey_Less@@V?$allocator@U?$pair@QEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@std@@@std@@@std@@@2@AEBQEAU_XWIZARD_PROPERTY_KEY@@@Z; std::_Tree<std::_Tmap_traits<_XWIZARD_PROPERTY_KEY *,_XWIZARD_PROPERTY_ELEMENT *,CKey_Less,std::allocator<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>>,0>>::find(_XWIZARD_PROPERTY_KEY * const &)
0x18002afa9  mov     rax, [rsp+88h+var_58]
0x18002afae  cmp     rax, [r13+0]
0x18002afb2  jnz     loc_18002B0E1
0x18002afb8  mov     esi, edi
0x18002afba  mov     ecx, 78h ; 'x'; cb
0x18002afbf  call    cs:__imp_CoTaskMemAlloc
0x18002afc5  mov     r12, rax
0x18002afc8  mov     [rsp+88h+var_58], rax
0x18002afcd  test    rax, rax
0x18002afd0  jz      loc_18002B0B1
0x18002afd6  movups  xmm0, xmmword ptr [rbx]
0x18002afd9  movups  xmmword ptr [rax], xmm0
0x18002afdc  movups  xmm1, xmmword ptr [rbx+10h]
0x18002afe0  movups  xmmword ptr [rax+10h], xmm1
0x18002afe4  movups  xmm0, xmmword ptr [rbx+20h]
0x18002afe8  movups  xmmword ptr [rax+20h], xmm0
0x18002afec  movups  xmm1, xmmword ptr [rbx+30h]
0x18002aff0  movups  xmmword ptr [rax+30h], xmm1
0x18002aff4  movups  xmm0, xmmword ptr [rbx+40h]
0x18002aff8  movups  xmmword ptr [rax+40h], xmm0
0x18002affc  movups  xmm1, xmmword ptr [rbx+50h]
0x18002b000  movups  xmmword ptr [rax+50h], xmm1
0x18002b004  movups  xmm0, xmmword ptr [rbx+60h]
0x18002b008  movups  xmmword ptr [rax+60h], xmm0
0x18002b00c  movsd   xmm1, qword ptr [rbx+70h]
0x18002b011  movsd   qword ptr [rax+70h], xmm1
0x18002b016  lea     r8, [rsp+88h+var_58]
0x18002b01b  lea     rdx, [rsp+88h+Src]
0x18002b023  mov     rcx, r13
0x18002b026  call    ?lower_bound@?$_Tree@V?$_Tmap_traits@PEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@VCKey_Less@@V?$allocator@U?$pair@QEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@std@@@std@@@std@@@2@AEBQEAU_XWIZARD_PROPERTY_KEY@@@Z; std::_Tree<std::_Tmap_traits<_XWIZARD_PROPERTY_KEY *,_XWIZARD_PROPERTY_ELEMENT *,CKey_Less,std::allocator<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>>,0>>::lower_bound(_XWIZARD_PROPERTY_KEY * const &)
0x18002b02b  mov     rbx, [rsp+88h+Src]
0x18002b033  cmp     rbx, [r13+0]
0x18002b037  jz      short loc_18002B049
0x18002b039  mov     r8, [rbx+20h]
0x18002b03d  mov     rdx, r12
0x18002b040  call    ??RCKey_Less@@QEBA_NPEAU_XWIZARD_PROPERTY_KEY@@0@Z; CKey_Less::operator()(_XWIZARD_PROPERTY_KEY *,_XWIZARD_PROPERTY_KEY *)
0x18002b045  test    al, al
0x18002b047  jz      short loc_18002B084
0x18002b049  mov     [rsp+88h+var_40], r12
0x18002b04e  mov     [rsp+88h+var_38], rdi
0x18002b053  lea     rdx, [rsp+88h+var_40]
0x18002b058  mov     rcx, r13
0x18002b05b  call    ??$_Buynode@U?$pair@PEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@std@@@?$_Tree_buy@U?$pair@QEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@std@@V?$allocator@U?$pair@QEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@std@@PEAX@1@$$QEAU?$pair@PEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@1@@Z; std::_Tree_buy<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>>::_Buynode<std::pair<_XWIZARD_PROPERTY_KEY *,_XWIZARD_PROPERTY_ELEMENT *>>(std::pair<_XWIZARD_PROPERTY_KEY *,_XWIZARD_PROPERTY_ELEMENT *> &&)
0x18002b060  lea     r9, [rax+20h]
0x18002b064  mov     [rsp+88h+var_68], rax
0x18002b069  mov     r8, rbx
0x18002b06c  lea     rdx, [rsp+88h+Src]
0x18002b074  mov     rcx, r13
0x18002b077  call    ??$_Insert_hint@AEAU?$pair@QEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@std@@PEAU?$_Tree_node@U?$pair@QEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@VCKey_Less@@V?$allocator@U?$pair@QEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@std@@@std@@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@std@@@std@@@std@@@1@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@std@@@std@@@std@@@1@AEAU?$pair@QEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@1@PEAU?$_Tree_node@U?$pair@QEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<_XWIZARD_PROPERTY_KEY *,_XWIZARD_PROPERTY_ELEMENT *,CKey_Less,std::allocator<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>>,0>>::_Insert_hint<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *> &,std::_Tree_node<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>,void *> *>(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>>>>,std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *> &,std::_Tree_node<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>,void *> *)
0x18002b07c  mov     rbx, [rsp+88h+Src]
0x18002b084  mov     [rbx+28h], r14
0x18002b088  lea     rbx, WPP_GLOBAL_Control
0x18002b08f  jmp     loc_18002B1E9
0x18002b094  lea     rbx, WPP_GLOBAL_Control
0x18002b09b  mov     esi, dword ptr [rsp+88h+Src]
0x18002b0a2  mov     r15, [rsp+88h+var_50]
0x18002b0a7  mov     r14, [rsp+88h+var_48]
0x18002b0ac  jmp     loc_18002B1BF
0x18002b0b1  mov     esi, 8007000Eh
0x18002b0b6  lea     rbx, WPP_GLOBAL_Control
0x18002b0bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b0c4  cmp     rcx, rbx
0x18002b0c7  jz      loc_18002B1C6
0x18002b0cd  test    byte ptr [rcx+1Ch], 4
0x18002b0d1  jz      loc_18002B1C6
0x18002b0d7  mov     edx, 11h
0x18002b0dc  jmp     loc_18002B1A9
0x18002b0e1  lea     rsi, [rax+28h]
0x18002b0e5  mov     rax, [rsi]
0x18002b0e8  mov     ecx, [rax+4]
0x18002b0eb  mov     edx, 0Fh
0x18002b0f0  and     ecx, edx; this
0x18002b0f2  jz      short loc_18002B0F9
0x18002b0f4  cmp     ecx, 1
0x18002b0f7  jnz     short loc_18002B171
0x18002b0f9  mov     rax, qword ptr cs:GUID_NULL.Data1
0x18002b100  sub     rax, [rbx]
0x18002b103  jnz     short loc_18002B110
0x18002b105  mov     rax, qword ptr cs:GUID_NULL.Data4
0x18002b10c  sub     rax, [rbx+8]
0x18002b110  test    rax, rax
0x18002b113  jz      short loc_18002B171
0x18002b115  mov     rcx, [rsp+88h+arg_8]
0x18002b11d  mov     rax, [rcx]
0x18002b120  sub     rax, [r12]
0x18002b124  jnz     short loc_18002B12F
0x18002b126  mov     rax, [rcx+8]
0x18002b12a  sub     rax, [r12+8]
0x18002b12f  test    rax, rax
0x18002b132  jz      short loc_18002B171
0x18002b134  mov     rax, [r12]
0x18002b138  sub     rax, [rbx]
0x18002b13b  jnz     short loc_18002B146
0x18002b13d  mov     rax, [r12+8]
0x18002b142  sub     rax, [rbx+8]
0x18002b146  test    rax, rax
0x18002b149  jz      short loc_18002B171
0x18002b14b  mov     esi, 80070005h
0x18002b150  lea     rbx, WPP_GLOBAL_Control
0x18002b157  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b15e  cmp     rcx, rbx
0x18002b161  jz      short loc_18002B1C6
0x18002b163  test    byte ptr [rcx+1Ch], 8
0x18002b167  jz      short loc_18002B1C6
0x18002b169  mov     r9d, 80070005h
0x18002b16f  jmp     short loc_18002B1AF
0x18002b171  mov     rdx, rsi; struct _XWIZARD_PROPERTY_ELEMENT **
0x18002b174  call    ?FreePropertyElement@CPropertyBag@@AEAAXPEAPEAU_XWIZARD_PROPERTY_ELEMENT@@@Z; CPropertyBag::FreePropertyElement(_XWIZARD_PROPERTY_ELEMENT * *)
0x18002b179  mov     [rsi], r14
0x18002b17c  mov     esi, 1
0x18002b181  jmp     loc_18002B088
0x18002b186  mov     esi, 8007000Eh
0x18002b18b  lea     rbx, WPP_GLOBAL_Control
0x18002b192  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b199  cmp     rcx, rbx
0x18002b19c  jz      short loc_18002B1C6
0x18002b19e  test    byte ptr [rcx+1Ch], 4
0x18002b1a2  jz      short loc_18002B1C6
0x18002b1a4  mov     edx, 0Eh
0x18002b1a9  mov     r9d, 8007000Eh
0x18002b1af  lea     r8, WPP_68d45ddfb6663f942b433d9c5d20cdd0_Traceguids
0x18002b1b6  mov     rcx, [rcx+10h]
0x18002b1ba  call    WPP_SF_d
0x18002b1bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b1c6  test    r15, r15
0x18002b1c9  jz      short loc_18002B1DB
0x18002b1cb  mov     rcx, r15; pv
0x18002b1ce  call    cs:__imp_CoTaskMemFree
0x18002b1d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b1db  test    r14, r14
0x18002b1de  jz      short loc_18002B1F0
0x18002b1e0  mov     rcx, r14; pv
0x18002b1e3  call    cs:__imp_CoTaskMemFree
0x18002b1e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b1f0  cmp     rcx, rbx
0x18002b1f3  jz      short loc_18002B213
0x18002b1f5  test    byte ptr [rcx+1Ch], 10h
0x18002b1f9  jz      short loc_18002B213
0x18002b1fb  mov     edx, 12h
0x18002b200  mov     r9d, esi
0x18002b203  lea     r8, WPP_68d45ddfb6663f942b433d9c5d20cdd0_Traceguids
0x18002b20a  mov     rcx, [rcx+10h]
0x18002b20e  call    WPP_SF_d
0x18002b213  mov     eax, esi
0x18002b215  lea     r11, [rsp+88h+var_28]
0x18002b21a  mov     rbx, [r11+30h]
0x18002b21e  mov     rsi, [r11+40h]
0x18002b222  mov     rsp, r11
0x18002b225  pop     r15
0x18002b227  pop     r14
0x18002b229  pop     r13
0x18002b22b  pop     r12
0x18002b22d  pop     rdi
0x18002b22e  retn
```
