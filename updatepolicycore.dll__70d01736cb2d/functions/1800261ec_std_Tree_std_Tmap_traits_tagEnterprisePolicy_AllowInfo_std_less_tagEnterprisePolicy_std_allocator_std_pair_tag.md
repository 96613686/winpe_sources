# std::_Tree<std::_Tmap_traits<tagEnterprisePolicy,AllowInfo,std::less<tagEnterprisePolicy>,std::allocator<std::pair<tagEnterprisePolicy const,AllowInfo>>,0>>::merge<std::_Tmap_traits<tagEnterprisePolicy,AllowInfo,std::less<tagEnterprisePolicy>,std::allocator<std::pair<tagEnterprisePolicy const,AllowInfo>>,0>>(std::_Tree<std::_Tmap_traits<tagEnterprisePolicy,AllowInfo,std::less<tagEnterprisePolicy>,std::allocator<std::pair<tagEnterprisePolicy const,AllowInfo>>,0>> &)

- ea: `0x1800261ec`
- end: `0x180026321`
- name: `??$merge@V?$_Tmap_traits@W4tagEnterprisePolicy@@UAllowInfo@@U?$less@W4tagEnterprisePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@?$_Tree@V?$_Tmap_traits@W4tagEnterprisePolicy@@UAllowInfo@@U?$less@W4tagEnterprisePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@std@@QEAAXAEAV01@@Z`
- size: `309`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800258e0`

## callees

- `0x18000f3a4`
- `0x18000fb34`
- `0x1800261ec`
- `0x180026494`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::merge<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>(
        __int64 *a1)
{
  __int64 v2; // rsi
  __int64 *v3; // rbx
  __int64 **v4; // rcx
  __int64 *v5; // r8
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 v8; // rcx
  __int64 v9; // rax
  int v10; // edx
  __int64 v11; // rax
  __int128 v12; // xmm0
  __int128 v13; // [rsp+20h] [rbp-38h] BYREF

  if ( a1 != &qword_18004EF50 )
  {
    v2 = *a1;
    v3 = *(__int64 **)qword_18004EF50;
    while ( !*((_BYTE *)v3 + 25) )
    {
      v4 = (__int64 **)v3[2];
      v5 = v3;
      if ( *((_BYTE *)v4 + 25) )
      {
        for ( i = (__int64 *)v3[1]; !*((_BYTE *)i + 25) && v3 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v3 = i;
        v3 = i;
      }
      else
      {
        v3 = (__int64 *)v3[2];
        for ( j = *v4; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v3 = j;
      }
      v8 = *a1;
      v9 = *(_QWORD *)(*a1 + 8);
      v13 = (unsigned __int64)v9;
      if ( !*(_BYTE *)(v9 + 25) )
      {
        v10 = *((_DWORD *)v5 + 8);
        do
        {
          *(_QWORD *)&v13 = v9;
          if ( *(_DWORD *)(v9 + 32) >= v10 )
          {
            DWORD2(v13) = 1;
            v8 = v9;
          }
          else
          {
            DWORD2(v13) = 0;
            v9 += 16;
          }
          v9 = *(_QWORD *)v9;
        }
        while ( !*(_BYTE *)(v9 + 25) );
      }
      if ( *(_BYTE *)(v8 + 25) || *((_DWORD *)v5 + 8) < *(_DWORD *)(v8 + 32) )
      {
        if ( a1[1] == 0x333333333333333LL )
          std::_Throw_tree_length_error();
        v11 = std::_Tree_val<std::_Tree_simple_types<std::pair<enum tagUpdatePolicy const,AllowInfo>>>::_Extract(
                &qword_18004EF50,
                v5);
        v12 = v13;
        *(_QWORD *)v11 = v2;
        *(_QWORD *)(v11 + 16) = v2;
        *(_BYTE *)(v11 + 24) = 0;
        v13 = v12;
        std::_Tree_val<std::_Tree_simple_types<std::pair<enum tagUpdatePolicy const,AllowInfo>>>::_Insert_node(
          a1,
          &v13,
          v11);
      }
    }
  }
}

```

## disassembly

```asm
0x1800261ec  mov     [rsp+arg_8], rbx
0x1800261f1  mov     [rsp+arg_10], rbp
0x1800261f6  push    rsi
0x1800261f7  push    rdi
0x1800261f8  push    r14
0x1800261fa  sub     rsp, 40h
0x1800261fe  lea     r14, qword_18004EF50
0x180026205  mov     rdi, rcx
0x180026208  cmp     rcx, r14
0x18002620b  jz      loc_180026308
0x180026211  mov     rbx, cs:qword_18004EF50
0x180026218  xor     ebp, ebp
0x18002621a  mov     rsi, [rcx]
0x18002621d  mov     rbx, [rbx]
0x180026220  jmp     loc_1800262FE
0x180026225  mov     rcx, [rbx+10h]
0x180026229  mov     r8, rbx
0x18002622c  cmp     [rcx+19h], bpl
0x180026230  jz      short loc_180026250
0x180026232  mov     rax, [rbx+8]
0x180026236  jmp     short loc_180026245
0x180026238  cmp     rbx, [rax+10h]
0x18002623c  jnz     short loc_18002624B
0x18002623e  mov     rbx, rax
0x180026241  mov     rax, [rax+8]
0x180026245  cmp     [rax+19h], bpl
0x180026249  jz      short loc_180026238
0x18002624b  mov     rbx, rax
0x18002624e  jmp     short loc_18002626B
0x180026250  mov     rbx, rcx
0x180026253  mov     rcx, [rcx]
0x180026256  cmp     [rcx+19h], bpl
0x18002625a  jnz     short loc_18002626B
0x18002625c  mov     rax, [rcx]
0x18002625f  mov     rbx, rcx
0x180026262  mov     rcx, rax
0x180026265  cmp     [rax+19h], bpl
0x180026269  jz      short loc_18002625C
0x18002626b  mov     rcx, [rdi]
0x18002626e  mov     qword ptr [rsp+58h+var_38+8], rbp
0x180026273  mov     rax, [rcx+8]
0x180026277  mov     qword ptr [rsp+58h+var_38], rax
0x18002627c  cmp     [rax+19h], bpl
0x180026280  jnz     short loc_1800262AE
0x180026282  mov     edx, [r8+20h]
0x180026286  mov     qword ptr [rsp+58h+var_38], rax
0x18002628b  cmp     [rax+20h], edx
0x18002628e  jge     short loc_18002629A
0x180026290  mov     dword ptr [rsp+58h+var_38+8], ebp
0x180026294  add     rax, 10h
0x180026298  jmp     short loc_1800262A5
0x18002629a  mov     dword ptr [rsp+58h+var_38+8], 1
0x1800262a2  mov     rcx, rax
0x1800262a5  mov     rax, [rax]
0x1800262a8  cmp     [rax+19h], bpl
0x1800262ac  jz      short loc_180026286
0x1800262ae  cmp     [rcx+19h], bpl
0x1800262b2  jnz     short loc_1800262BD
0x1800262b4  mov     eax, [rcx+20h]
0x1800262b7  cmp     [r8+20h], eax
0x1800262bb  jge     short loc_1800262FE
0x1800262bd  mov     rax, 333333333333333h
0x1800262c7  cmp     [rdi+8], rax
0x1800262cb  jz      short loc_18002631B
0x1800262cd  mov     rdx, r8
0x1800262d0  mov     rcx, r14
0x1800262d3  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<tagUpdatePolicy const,AllowInfo>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<tagUpdatePolicy const,AllowInfo>>>,std::_Iterator_base0>)
0x1800262d8  movups  xmm0, [rsp+58h+var_38]
0x1800262dd  mov     r8, rax
0x1800262e0  lea     rdx, [rsp+58h+var_38]
0x1800262e5  mov     rcx, rdi
0x1800262e8  mov     [rax], rsi
0x1800262eb  mov     [rax+10h], rsi
0x1800262ef  mov     [rax+18h], bpl
0x1800262f3  movdqu  [rsp+58h+var_38], xmm0
0x1800262f9  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<tagUpdatePolicy const,AllowInfo>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<tagUpdatePolicy const,AllowInfo>,void *> *>,std::_Tree_node<std::pair<tagUpdatePolicy const,AllowInfo>,void *> * const)
0x1800262fe  cmp     [rbx+19h], bpl
0x180026302  jz      loc_180026225
0x180026308  mov     rbx, [rsp+58h+arg_8]
0x18002630d  mov     rbp, [rsp+58h+arg_10]
0x180026312  add     rsp, 40h
0x180026316  pop     r14
0x180026318  pop     rdi
0x180026319  pop     rsi
0x18002631a  retn
0x18002631b  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
