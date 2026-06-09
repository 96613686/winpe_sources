# std::_Tree<std::_Tmap_traits<tagEnterprisePolicy,AllowInfo,std::less<tagEnterprisePolicy>,std::allocator<std::pair<tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(std::pair<tagEnterprisePolicy const,AllowInfo> &&)

- ea: `0x1800149f4`
- end: `0x180014b2a`
- name: `??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@W4tagEnterprisePolicy@@UAllowInfo@@U?$less@W4tagEnterprisePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@1@@Z`
- size: `310`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180012340`

## callees

- `0x18000f3a4`
- `0x18000fb34`
- `0x1800149f4`
- `0x180030cb4`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<enum tagEnterprisePolicy,AllowInfo,std::less<enum tagEnterprisePolicy>,std::allocator<std::pair<enum tagEnterprisePolicy const,AllowInfo>>,0>>::insert<0,0>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v5; // rbp
  __int64 v6; // rax
  char v7; // bl
  __int64 i; // rcx
  char *v9; // rax
  __int128 v11; // [rsp+20h] [rbp-48h]
  __int128 v12; // [rsp+40h] [rbp-28h] BYREF

  v5 = qword_18004EF50;
  v6 = *(_QWORD *)(qword_18004EF50 + 8);
  v11 = (unsigned __int64)v6;
  v7 = 0;
  for ( i = qword_18004EF50; !*(_BYTE *)(v6 + 25); v6 = *(_QWORD *)v6 )
  {
    *(_QWORD *)&v11 = v6;
    if ( *(_DWORD *)(v6 + 32) >= *(_DWORD *)a3 )
    {
      DWORD2(v11) = 1;
      i = v6;
    }
    else
    {
      DWORD2(v11) = 0;
      v6 += 16;
    }
  }
  if ( *(_BYTE *)(i + 25) || *(_DWORD *)a3 < *(_DWORD *)(i + 32) )
  {
    if ( qword_18004EF58 == 0x333333333333333LL )
      std::_Throw_tree_length_error();
    *(_QWORD *)&v12 = &qword_18004EF50;
    *((_QWORD *)&v12 + 1) = 0;
    v9 = (char *)operator new(0x50u);
    *((_DWORD *)v9 + 8) = *(_DWORD *)a3;
    *(_OWORD *)(v9 + 40) = 0;
    *((_QWORD *)v9 + 7) = 0;
    *((_QWORD *)v9 + 8) = 0;
    *(_OWORD *)(v9 + 40) = *(_OWORD *)(a3 + 8);
    *(_OWORD *)(v9 + 56) = *(_OWORD *)(a3 + 24);
    *(_QWORD *)(a3 + 24) = 0;
    *(_QWORD *)(a3 + 32) = 7;
    *(_WORD *)(a3 + 8) = 0;
    v9[72] = *(_BYTE *)(a3 + 40);
    *(_QWORD *)v9 = v5;
    *((_QWORD *)v9 + 1) = v5;
    *((_QWORD *)v9 + 2) = v5;
    *((_WORD *)v9 + 12) = 0;
    v12 = v11;
    i = std::_Tree_val<std::_Tree_simple_types<std::pair<enum tagUpdatePolicy const,AllowInfo>>>::_Insert_node(
          &qword_18004EF50,
          &v12,
          v9);
    v7 = 1;
  }
  *(_QWORD *)a2 = i;
  *(_BYTE *)(a2 + 8) = v7;
  return a2;
}

```

## disassembly

```asm
0x1800149f4  mov     r11, rsp
0x1800149f7  mov     [r11+8], rbx
0x1800149fb  mov     [r11+20h], rbp
0x1800149ff  push    rsi
0x180014a00  push    rdi
0x180014a01  push    r14
0x180014a03  sub     rsp, 50h
0x180014a07  mov     rsi, r8
0x180014a0a  mov     rdi, rdx
0x180014a0d  mov     rbp, cs:qword_18004EF50
0x180014a14  mov     rax, [rbp+8]
0x180014a18  mov     [r11-48h], rax
0x180014a1c  xor     ebx, ebx
0x180014a1e  mov     [r11-40h], rbx
0x180014a22  mov     rcx, rbp
0x180014a25  cmp     [rax+19h], bl
0x180014a28  jnz     short loc_180014A54
0x180014a2a  mov     edx, [r8]
0x180014a2d  mov     qword ptr [rsp+68h+var_48], rax
0x180014a32  cmp     [rax+20h], edx
0x180014a35  jge     short loc_180014A41
0x180014a37  mov     dword ptr [rsp+68h+var_48+8], ebx
0x180014a3b  add     rax, 10h
0x180014a3f  jmp     short loc_180014A4C
0x180014a41  mov     dword ptr [rsp+68h+var_48+8], 1
0x180014a49  mov     rcx, rax
0x180014a4c  mov     rax, [rax]
0x180014a4f  cmp     [rax+19h], bl
0x180014a52  jz      short loc_180014A2D
0x180014a54  cmp     [rcx+19h], bl
0x180014a57  jnz     short loc_180014A65
0x180014a59  mov     eax, [rcx+20h]
0x180014a5c  cmp     [r8], eax
0x180014a5f  jge     loc_180014B06
0x180014a65  mov     rax, 333333333333333h
0x180014a6f  cmp     cs:qword_18004EF58, rax
0x180014a76  jz      loc_180014B24
0x180014a7c  lea     r14, qword_18004EF50
0x180014a83  mov     qword ptr [rsp+68h+var_28], r14
0x180014a88  mov     qword ptr [rsp+68h+var_28+8], rbx
0x180014a8d  mov     ecx, 50h ; 'P'; Size
0x180014a92  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014a97  mov     r8, rax
0x180014a9a  mov     eax, [rsi]
0x180014a9c  mov     [r8+20h], eax
0x180014aa0  xorps   xmm0, xmm0
0x180014aa3  movups  xmmword ptr [r8+28h], xmm0
0x180014aa8  mov     [r8+38h], rbx
0x180014aac  mov     [r8+40h], rbx
0x180014ab0  movups  xmm0, xmmword ptr [rsi+8]
0x180014ab4  movups  xmmword ptr [r8+28h], xmm0
0x180014ab9  movups  xmm1, xmmword ptr [rsi+18h]
0x180014abd  movups  xmmword ptr [r8+38h], xmm1
0x180014ac2  mov     [rsi+18h], rbx
0x180014ac6  mov     qword ptr [rsi+20h], 7
0x180014ace  mov     [rsi+8], bx
0x180014ad2  mov     al, [rsi+28h]
0x180014ad5  mov     [r8+48h], al
0x180014ad9  mov     [r8], rbp
0x180014adc  mov     [r8+8], rbp
0x180014ae0  mov     [r8+10h], rbp
0x180014ae4  mov     [r8+18h], bx
0x180014ae9  movups  xmm0, [rsp+68h+var_48]
0x180014aee  movdqu  [rsp+68h+var_28], xmm0
0x180014af4  lea     rdx, [rsp+68h+var_28]
0x180014af9  mov     rcx, r14
0x180014afc  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<tagUpdatePolicy const,AllowInfo>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<tagUpdatePolicy const,AllowInfo>,void *> *>,std::_Tree_node<std::pair<tagUpdatePolicy const,AllowInfo>,void *> * const)
0x180014b01  mov     rcx, rax
0x180014b04  mov     bl, 1
0x180014b06  mov     [rdi], rcx
0x180014b09  mov     [rdi+8], bl
0x180014b0c  mov     rax, rdi
0x180014b0f  lea     r11, [rsp+68h+var_18]
0x180014b14  mov     rbx, [r11+20h]
0x180014b18  mov     rbp, [r11+38h]
0x180014b1c  mov     rsp, r11
0x180014b1f  pop     r14
0x180014b21  pop     rdi
0x180014b22  pop     rsi
0x180014b23  retn
0x180014b24  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
