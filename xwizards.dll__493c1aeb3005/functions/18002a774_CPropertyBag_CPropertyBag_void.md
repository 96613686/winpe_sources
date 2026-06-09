# CPropertyBag::~CPropertyBag(void)

- ea: `0x18002a774`
- end: `0x18002a7e6`
- name: `??1CPropertyBag@@QEAA@XZ`
- size: `114`
- prototype: `void __fastcall(CPropertyBag *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029d1c`

## callees

- `0x18002a750`
- `0x18002a774`
- `0x18002a854`
- `0x18002b36c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a790`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a790`

## pseudocode

```c
void __fastcall CPropertyBag::~CPropertyBag(__int64 **this)
{
  __int64 v2; // rbx
  CPropertyBag *v3; // rcx
  __int64 i; // rax

  v2 = **this;
  while ( (__int64 *)v2 != *this )
  {
    CoTaskMemFree(*(LPVOID *)(v2 + 32));
    CPropertyBag::FreePropertyElement(v3, (LPVOID *)(v2 + 40));
    if ( !*(_BYTE *)(v2 + 25) )
    {
      if ( *(_BYTE *)(*(_QWORD *)(v2 + 16) + 25LL) )
      {
        for ( i = *(_QWORD *)(v2 + 8); !*(_BYTE *)(i + 25) && v2 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
          v2 = i;
      }
      else
      {
        i = std::_Tree_val<std::_Tree_simple_types<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>>>::_Min();
      }
      v2 = i;
    }
  }
  std::_Tree<std::_Tmap_traits<_XWIZARD_PROPERTY_KEY *,_XWIZARD_PROPERTY_ELEMENT *,CKey_Less,std::allocator<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>>,0>>::~_Tree<std::_Tmap_traits<_XWIZARD_PROPERTY_KEY *,_XWIZARD_PROPERTY_ELEMENT *,CKey_Less,std::allocator<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>>,0>>(this);
}

```

## disassembly

```asm
0x18002a774  mov     [rsp+arg_0], rbx
0x18002a779  push    rdi
0x18002a77a  sub     rsp, 20h
0x18002a77e  mov     rbx, [rcx]
0x18002a781  mov     rdi, rcx
0x18002a784  mov     rbx, [rbx]
0x18002a787  cmp     rbx, [rdi]
0x18002a78a  jz      short loc_18002A7D4
0x18002a78c  mov     rcx, [rbx+20h]; pv
0x18002a790  call    cs:__imp_CoTaskMemFree
0x18002a796  lea     rdx, [rbx+28h]; struct _XWIZARD_PROPERTY_ELEMENT **
0x18002a79a  call    ?FreePropertyElement@CPropertyBag@@AEAAXPEAPEAU_XWIZARD_PROPERTY_ELEMENT@@@Z; CPropertyBag::FreePropertyElement(_XWIZARD_PROPERTY_ELEMENT * *)
0x18002a79f  cmp     byte ptr [rbx+19h], 0
0x18002a7a3  jnz     short loc_18002A787
0x18002a7a5  mov     rcx, [rbx+10h]
0x18002a7a9  cmp     byte ptr [rcx+19h], 0
0x18002a7ad  jnz     short loc_18002A7B6
0x18002a7af  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@QEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>>>::_Min(std::_Tree_node<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>,void *> *)
0x18002a7b4  jmp     short loc_18002A7CF
0x18002a7b6  mov     rax, [rbx+8]
0x18002a7ba  jmp     short loc_18002A7C9
0x18002a7bc  cmp     rbx, [rax+10h]
0x18002a7c0  jnz     short loc_18002A7CF
0x18002a7c2  mov     rbx, rax
0x18002a7c5  mov     rax, [rax+8]
0x18002a7c9  cmp     byte ptr [rax+19h], 0
0x18002a7cd  jz      short loc_18002A7BC
0x18002a7cf  mov     rbx, rax
0x18002a7d2  jmp     short loc_18002A787
0x18002a7d4  mov     rcx, rdi
0x18002a7d7  mov     rbx, [rsp+28h+arg_0]
0x18002a7dc  add     rsp, 20h
0x18002a7e0  pop     rdi
0x18002a7e1  jmp     ??1?$_Tree@V?$_Tmap_traits@PEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@VCKey_Less@@V?$allocator@U?$pair@QEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_XWIZARD_PROPERTY_KEY *,_XWIZARD_PROPERTY_ELEMENT *,CKey_Less,std::allocator<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>>,0>>::~_Tree<std::_Tmap_traits<_XWIZARD_PROPERTY_KEY *,_XWIZARD_PROPERTY_ELEMENT *,CKey_Less,std::allocator<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>>,0>>(void)
```
