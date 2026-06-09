# std::map<tagEnterprisePolicy,AllowInfo,std::less<tagEnterprisePolicy>,std::allocator<std::pair<tagEnterprisePolicy const,AllowInfo>>>::map<tagEnterprisePolicy,AllowInfo,std::less<tagEnterprisePolicy>,std::allocator<std::pair<tagEnterprisePolicy const,AllowInfo>>>(std::initializer_list<std::pair<tagEnterprisePolicy const,AllowInfo>>)

- ea: `0x180014c44`
- end: `0x180014db5`
- name: `??0?$map@W4tagEnterprisePolicy@@UAllowInfo@@U?$less@W4tagEnterprisePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@4@@std@@QEAA@V?$initializer_list@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@1@@Z`
- size: `369`
- prototype: `__int64 *__fastcall(__int64, __m128i *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180001b20`

## callees

- `0x18000e7e4`
- `0x18000f3a4`
- `0x18000fb34`
- `0x180014c44`
- `0x180015268`
- `0x180030cb4`

## pseudocode

```c
__int64 *__fastcall std::map<enum tagEnterprisePolicy,AllowInfo>::map<enum tagEnterprisePolicy,AllowInfo>(
        __int64 a1,
        __m128i *a2)
{
  __int64 v3; // rcx
  _QWORD *v4; // r15
  __int64 v5; // r14
  unsigned __int64 v6; // rbp
  __int64 v7; // rax
  __int128 v8; // xmm6
  __int64 v9; // rdi
  _DWORD *v10; // rsi
  __int128 v12; // [rsp+40h] [rbp-78h] BYREF
  __int64 v13; // [rsp+50h] [rbp-68h]
  _BYTE v14[48]; // [rsp+60h] [rbp-58h] BYREF

  qword_18004EF50 = 0;
  qword_18004EF58 = 0;
  v4 = operator new(0x50u);
  *v4 = v4;
  v4[1] = v4;
  v4[2] = v4;
  *((_WORD *)v4 + 12) = 257;
  qword_18004EF50 = (__int64)v4;
  v5 = a2->m128i_i64[0];
  v6 = _mm_srli_si128(*a2, 8).m128i_u64[0];
  while ( v5 != v6 )
  {
    v7 = std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::_Find_hint<enum tagEnterprisePolicy>(
           v3,
           (__int64)v14,
           v4,
           (int *)v5);
    v8 = *(_OWORD *)v7;
    v13 = *(_QWORD *)(v7 + 16);
    if ( !(_BYTE)v13 )
    {
      if ( qword_18004EF58 == 0x333333333333333LL )
        std::_Throw_tree_length_error();
      v9 = qword_18004EF50;
      v10 = operator new(0x50u);
      v10[8] = *(_DWORD *)v5;
      std::wstring::wstring((__int64)(v10 + 10), v5 + 8);
      *((_BYTE *)v10 + 72) = *(_BYTE *)(v5 + 40);
      *(_QWORD *)v10 = v9;
      *((_QWORD *)v10 + 1) = v9;
      *((_QWORD *)v10 + 2) = v9;
      *((_WORD *)v10 + 12) = 0;
      v12 = v8;
      std::_Tree_val<std::_Tree_simple_types<std::pair<enum tagUpdatePolicy const,AllowInfo>>>::_Insert_node(
        &qword_18004EF50,
        &v12,
        v10);
    }
    v5 += 48;
  }
  return &qword_18004EF50;
}

```

## disassembly

```asm
0x180014c44  mov     rax, rsp
0x180014c47  mov     [rax+8], rbx
0x180014c4b  mov     [rax+18h], rbp
0x180014c4f  push    rsi
0x180014c50  push    rdi
0x180014c51  push    r13
0x180014c53  push    r14
0x180014c55  push    r15
0x180014c57  sub     rsp, 90h
0x180014c5e  movaps  xmmword ptr [rax-38h], xmm6
0x180014c62  mov     rbx, rdx
0x180014c65  mov     rax, [rsp+0B8h+var_98]
0x180014c6a  mov     [rsp+0B8h+var_98], rax
0x180014c6f  lea     r13, qword_18004EF50
0x180014c76  mov     [rsp+0B8h+var_98], r13
0x180014c7b  mov     cs:qword_18004EF50, 0
0x180014c86  mov     cs:qword_18004EF58, 0
0x180014c91  mov     ecx, 50h ; 'P'; Size
0x180014c96  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014c9b  mov     r15, rax
0x180014c9e  mov     [rax], rax
0x180014ca1  mov     [rax+8], rax
0x180014ca5  mov     [rax+10h], rax
0x180014ca9  mov     word ptr [rax+18h], 101h
0x180014caf  mov     cs:qword_18004EF50, rax
0x180014cb6  movaps  xmm0, xmmword ptr [rbx]
0x180014cb9  movq    r14, xmm0
0x180014cbe  psrldq  xmm0, 8
0x180014cc3  movq    rbp, xmm0
0x180014cc8  jmp     loc_180014D82
0x180014ccd  mov     r9, r14
0x180014cd0  mov     r8, r15
0x180014cd3  lea     rdx, [rsp+0B8h+var_58]
0x180014cd8  call    ??$_Find_hint@W4tagEnterprisePolicy@@@?$_Tree@V?$_Tmap_traits@W4tagEnterprisePolicy@@UAllowInfo@@U?$less@W4tagEnterprisePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@std@@IEBA?AU?$_Tree_find_hint_result@PEAU?$_Tree_node@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@PEAX@std@@@1@QEAU?$_Tree_node@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@PEAX@1@AEBW4tagEnterprisePolicy@@@Z; std::_Tree<std::_Tmap_traits<tagEnterprisePolicy,AllowInfo,std::less<tagEnterprisePolicy>,std::allocator<std::pair<tagEnterprisePolicy const,AllowInfo>>,0>>::_Find_hint<tagEnterprisePolicy>(std::_Tree_node<std::pair<tagEnterprisePolicy const,AllowInfo>,void *> * const,tagEnterprisePolicy const &)
0x180014cdd  movups  xmm6, xmmword ptr [rax]
0x180014ce0  movsd   xmm0, qword ptr [rax+10h]
0x180014ce5  movsd   [rsp+0B8h+var_68], xmm0
0x180014ceb  cmp     byte ptr [rsp+0B8h+var_68], 0
0x180014cf0  jnz     loc_180014D7E
0x180014cf6  mov     rax, 333333333333333h
0x180014d00  cmp     cs:qword_18004EF58, rax
0x180014d07  jz      loc_180014DAF
0x180014d0d  mov     rdi, cs:qword_18004EF50
0x180014d14  mov     [rsp+0B8h+var_90], r13
0x180014d19  mov     [rsp+0B8h+var_88], 0
0x180014d22  mov     ecx, 50h ; 'P'; Size
0x180014d27  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014d2c  mov     rsi, rax
0x180014d2f  mov     [rsp+0B8h+var_88], rax
0x180014d34  mov     ecx, [r14]
0x180014d37  mov     [rax+20h], ecx
0x180014d3a  lea     rdx, [r14+8]
0x180014d3e  lea     rcx, [rax+28h]
0x180014d42  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180014d47  mov     cl, [r14+28h]
0x180014d4b  mov     [rsi+48h], cl
0x180014d4e  mov     [rsi], rdi
0x180014d51  mov     [rsi+8], rdi
0x180014d55  mov     [rsi+10h], rdi
0x180014d59  mov     word ptr [rsi+18h], 0
0x180014d5f  mov     [rsp+0B8h+var_88], 0
0x180014d68  movdqu  [rsp+0B8h+var_78], xmm6
0x180014d6e  mov     r8, rsi
0x180014d71  lea     rdx, [rsp+0B8h+var_78]
0x180014d76  mov     rcx, r13
0x180014d79  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<tagUpdatePolicy const,AllowInfo>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<tagUpdatePolicy const,AllowInfo>,void *> *>,std::_Tree_node<std::pair<tagUpdatePolicy const,AllowInfo>,void *> * const)
0x180014d7e  add     r14, 30h ; '0'
0x180014d82  cmp     r14, rbp
0x180014d85  jnz     loc_180014CCD
0x180014d8b  mov     rax, r13
0x180014d8e  lea     r11, [rsp+0B8h+var_28]
0x180014d96  mov     rbx, [r11+30h]
0x180014d9a  mov     rbp, [r11+40h]
0x180014d9e  movaps  xmm6, xmmword ptr [r11-10h]
0x180014da3  mov     rsp, r11
0x180014da6  pop     r15
0x180014da8  pop     r14
0x180014daa  pop     r13
0x180014dac  pop     rdi
0x180014dad  pop     rsi
0x180014dae  retn
0x180014daf  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
