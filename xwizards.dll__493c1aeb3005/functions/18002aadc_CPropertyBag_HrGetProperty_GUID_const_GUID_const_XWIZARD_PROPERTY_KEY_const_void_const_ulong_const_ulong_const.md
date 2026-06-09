# CPropertyBag::HrGetProperty(_GUID const *,_GUID const *,_XWIZARD_PROPERTY_KEY const *,void * * const,ulong * const,ulong * const,ulong * const)

- ea: `0x18002aadc`
- end: `0x18002acfd`
- name: `?HrGetProperty@CPropertyBag@@QEAAJPEBU_GUID@@0PEBU_XWIZARD_PROPERTY_KEY@@QEAPEAXQEAK33@Z`
- size: `545`
- prototype: `__int64 __fastcall(CPropertyBag *__hidden this, const struct _GUID *, const struct _GUID *, const struct _XWIZARD_PROPERTY_KEY *, void **const, unsigned int *const, unsigned int *const, unsigned int *const)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029e30`
- `0x18002ad04`

## callees

- `0x180002556`
- `0x18000ae04`
- `0x18002aadc`
- `0x18002b6ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ac1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ac1e`

## pseudocode

```c
__int64 __fastcall CPropertyBag::HrGetProperty(
        unsigned int *const *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4,
        void **const a5,
        unsigned int *const a6,
        unsigned int *const a7,
        unsigned int *const a8)
{
  void **v8; // rdi
  unsigned int *v12; // rsi
  unsigned int *v13; // r14
  unsigned int *v14; // r15
  unsigned int *v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  unsigned int v20; // edi
  PVOID *v21; // rcx
  void *v22; // rax

  v8 = a5;
  if ( a5 )
    *a5 = 0;
  v12 = a6;
  if ( a6 )
    *a6 = 0;
  v13 = a7;
  if ( a7 )
    *a7 = 0;
  v14 = a8;
  if ( a8 )
    *a8 = 0;
  a5 = a4;
  std::_Tree<std::_Tmap_traits<_XWIZARD_PROPERTY_KEY *,_XWIZARD_PROPERTY_ELEMENT *,CKey_Less,std::allocator<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>>,0>>::find(
    this,
    &a6,
    &a5);
  v15 = a6;
  if ( a6 == *this )
  {
    v20 = 1;
    goto LABEL_37;
  }
  v16 = *((_QWORD *)a6 + 5);
  if ( (*(_BYTE *)(v16 + 4) & 0xF) != 0 )
    goto LABEL_24;
  v17 = *(_QWORD *)&GUID_NULL.Data1 - (_QWORD)*a4;
  if ( *(void **)&GUID_NULL.Data1 == *a4 )
    v17 = *(_QWORD *)GUID_NULL.Data4 - (_QWORD)a4[1];
  if ( !v17 )
    goto LABEL_24;
  v18 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&a3->Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&a3->Data1 )
    v18 = *(_QWORD *)a2->Data4 - *(_QWORD *)a3->Data4;
  if ( !v18 )
    goto LABEL_24;
  v19 = *(_QWORD *)&a3->Data1 - (_QWORD)*a4;
  if ( *(void **)&a3->Data1 == *a4 )
    v19 = *(_QWORD *)a3->Data4 - (_QWORD)a4[1];
  if ( !v19 )
  {
LABEL_24:
    if ( *(_QWORD *)(v16 + 16) && v8 )
    {
      v22 = CoTaskMemAlloc(*(unsigned int *)(v16 + 8));
      *v8 = v22;
      if ( !v22 )
      {
        v20 = -2147024882;
        v21 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v20;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            WPP_68d45ddfb6663f942b433d9c5d20cdd0_Traceguids,
            2147942414LL);
          v21 = (PVOID *)WPP_GLOBAL_Control;
        }
        goto LABEL_38;
      }
      memcpy_0(v22, *(const void **)(*((_QWORD *)v15 + 5) + 16LL), *(unsigned int *)(*((_QWORD *)v15 + 5) + 8LL));
    }
    v20 = 0;
    if ( v12 )
      *v12 = *(_DWORD *)(*((_QWORD *)v15 + 5) + 8LL) - 2;
    if ( v13 )
      *v13 = *(_DWORD *)(*((_QWORD *)v15 + 5) + 4LL);
    if ( v14 )
      *v14 = **((_DWORD **)v15 + 5);
    goto LABEL_37;
  }
  v20 = -2147024891;
  v21 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v20;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_68d45ddfb6663f942b433d9c5d20cdd0_Traceguids, 2147942405LL);
LABEL_37:
    v21 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_38:
  if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 0x10) != 0 )
    WPP_SF_d(v21[2], 21, WPP_68d45ddfb6663f942b433d9c5d20cdd0_Traceguids, v20);
  return v20;
}

```

## disassembly

```asm
0x18002aadc  mov     [rsp+arg_8], rdx
0x18002aae1  push    rbx
0x18002aae2  push    rbp
0x18002aae3  push    rsi
0x18002aae4  push    rdi
0x18002aae5  push    r12
0x18002aae7  push    r13
0x18002aae9  push    r14
0x18002aaeb  push    r15
0x18002aaed  sub     rsp, 28h
0x18002aaf1  mov     rdi, [rsp+68h+arg_20]
0x18002aaf9  xor     eax, eax
0x18002aafb  mov     rbp, r9
0x18002aafe  mov     r12, r8
0x18002ab01  mov     r13, rcx
0x18002ab04  test    rdi, rdi
0x18002ab07  jz      short loc_18002AB0C
0x18002ab09  mov     [rdi], rax
0x18002ab0c  mov     rsi, [rsp+68h+arg_28]
0x18002ab14  test    rsi, rsi
0x18002ab17  jz      short loc_18002AB1B
0x18002ab19  mov     [rsi], eax
0x18002ab1b  mov     r14, [rsp+68h+arg_30]
0x18002ab23  test    r14, r14
0x18002ab26  jz      short loc_18002AB2B
0x18002ab28  mov     [r14], eax
0x18002ab2b  mov     r15, [rsp+68h+arg_38]
0x18002ab33  test    r15, r15
0x18002ab36  jz      short loc_18002AB3B
0x18002ab38  mov     [r15], eax
0x18002ab3b  lea     r8, [rsp+68h+arg_20]
0x18002ab43  mov     [rsp+68h+arg_20], rbp
0x18002ab4b  lea     rdx, [rsp+68h+arg_28]
0x18002ab53  call    ?find@?$_Tree@V?$_Tmap_traits@PEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@VCKey_Less@@V?$allocator@U?$pair@QEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAU_XWIZARD_PROPERTY_KEY@@PEAU_XWIZARD_PROPERTY_ELEMENT@@@std@@@std@@@std@@@2@AEBQEAU_XWIZARD_PROPERTY_KEY@@@Z; std::_Tree<std::_Tmap_traits<_XWIZARD_PROPERTY_KEY *,_XWIZARD_PROPERTY_ELEMENT *,CKey_Less,std::allocator<std::pair<_XWIZARD_PROPERTY_KEY * const,_XWIZARD_PROPERTY_ELEMENT *>>,0>>::find(_XWIZARD_PROPERTY_KEY * const &)
0x18002ab58  mov     rbx, [rsp+68h+arg_28]
0x18002ab60  lea     r8, WPP_GLOBAL_Control
0x18002ab67  cmp     rbx, [r13+0]
0x18002ab6b  jz      loc_18002ACB4
0x18002ab71  mov     rcx, [rbx+28h]
0x18002ab75  test    byte ptr [rcx+4], 0Fh
0x18002ab79  jnz     loc_18002AC0F
0x18002ab7f  mov     rax, qword ptr cs:GUID_NULL.Data1
0x18002ab86  sub     rax, [rbp+0]
0x18002ab8a  jnz     short loc_18002AB97
0x18002ab8c  mov     rax, qword ptr cs:GUID_NULL.Data4
0x18002ab93  sub     rax, [rbp+8]
0x18002ab97  test    rax, rax
0x18002ab9a  jz      short loc_18002AC0F
0x18002ab9c  mov     rdx, [rsp+68h+arg_8]
0x18002aba1  mov     rax, [rdx]
0x18002aba4  sub     rax, [r12]
0x18002aba8  jnz     short loc_18002ABB3
0x18002abaa  mov     rax, [rdx+8]
0x18002abae  sub     rax, [r12+8]
0x18002abb3  test    rax, rax
0x18002abb6  jz      short loc_18002AC0F
0x18002abb8  mov     rax, [r12]
0x18002abbc  sub     rax, [rbp+0]
0x18002abc0  jnz     short loc_18002ABCB
0x18002abc2  mov     rax, [r12+8]
0x18002abc7  sub     rax, [rbp+8]
0x18002abcb  test    rax, rax
0x18002abce  jz      short loc_18002AC0F
0x18002abd0  mov     edi, 80070005h
0x18002abd5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002abdc  cmp     rcx, r8
0x18002abdf  jz      loc_18002ACEA
0x18002abe5  test    byte ptr [rcx+1Ch], 8
0x18002abe9  jz      loc_18002ACC0
0x18002abef  mov     rcx, [rcx+10h]
0x18002abf3  lea     r8, WPP_68d45ddfb6663f942b433d9c5d20cdd0_Traceguids
0x18002abfa  mov     edx, 13h
0x18002abff  mov     r9d, 80070005h
0x18002ac05  call    WPP_SF_d
0x18002ac0a  jmp     loc_18002ACB9
0x18002ac0f  cmp     qword ptr [rcx+10h], 0
0x18002ac14  jz      short loc_18002AC40
0x18002ac16  test    rdi, rdi
0x18002ac19  jz      short loc_18002AC40
0x18002ac1b  mov     ecx, [rcx+8]; cb
0x18002ac1e  call    cs:__imp_CoTaskMemAlloc
0x18002ac24  mov     [rdi], rax
0x18002ac27  test    rax, rax
0x18002ac2a  jz      short loc_18002AC72
0x18002ac2c  mov     rdx, [rbx+28h]
0x18002ac30  mov     rcx, rax; void *
0x18002ac33  mov     r8d, [rdx+8]; Size
0x18002ac37  mov     rdx, [rdx+10h]; Src
0x18002ac3b  call    memcpy_0
0x18002ac40  xor     edi, edi
0x18002ac42  test    rsi, rsi
0x18002ac45  jz      short loc_18002AC53
0x18002ac47  mov     rax, [rbx+28h]
0x18002ac4b  mov     ecx, [rax+8]
0x18002ac4e  sub     ecx, 2
0x18002ac51  mov     [rsi], ecx
0x18002ac53  test    r14, r14
0x18002ac56  jz      short loc_18002AC62
0x18002ac58  mov     rax, [rbx+28h]
0x18002ac5c  mov     ecx, [rax+4]
0x18002ac5f  mov     [r14], ecx
0x18002ac62  test    r15, r15
0x18002ac65  jz      short loc_18002ACB9
0x18002ac67  mov     rax, [rbx+28h]
0x18002ac6b  mov     ecx, [rax]
0x18002ac6d  mov     [r15], ecx
0x18002ac70  jmp     short loc_18002ACB9
0x18002ac72  mov     edi, 8007000Eh
0x18002ac77  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ac7e  lea     rbx, WPP_GLOBAL_Control
0x18002ac85  cmp     rcx, rbx
0x18002ac88  jz      short loc_18002ACEA
0x18002ac8a  test    byte ptr [rcx+1Ch], 4
0x18002ac8e  jz      short loc_18002ACC7
0x18002ac90  mov     rcx, [rcx+10h]
0x18002ac94  lea     r8, WPP_68d45ddfb6663f942b433d9c5d20cdd0_Traceguids
0x18002ac9b  mov     edx, 14h
0x18002aca0  mov     r9d, 8007000Eh
0x18002aca6  call    WPP_SF_d
0x18002acab  mov     rcx, cs:WPP_GLOBAL_Control
0x18002acb2  jmp     short loc_18002ACC7
0x18002acb4  mov     edi, 1
0x18002acb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002acc0  lea     rbx, WPP_GLOBAL_Control
0x18002acc7  cmp     rcx, rbx
0x18002acca  jz      short loc_18002ACEA
0x18002accc  test    byte ptr [rcx+1Ch], 10h
0x18002acd0  jz      short loc_18002ACEA
0x18002acd2  mov     rcx, [rcx+10h]
0x18002acd6  lea     r8, WPP_68d45ddfb6663f942b433d9c5d20cdd0_Traceguids
0x18002acdd  mov     edx, 15h
0x18002ace2  mov     r9d, edi
0x18002ace5  call    WPP_SF_d
0x18002acea  mov     eax, edi
0x18002acec  add     rsp, 28h
0x18002acf0  pop     r15
0x18002acf2  pop     r14
0x18002acf4  pop     r13
0x18002acf6  pop     r12
0x18002acf8  pop     rdi
0x18002acf9  pop     rsi
0x18002acfa  pop     rbp
0x18002acfb  pop     rbx
0x18002acfc  retn
```
