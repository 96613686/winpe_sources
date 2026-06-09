# std::_Tree<std::_Tmap_traits<tagUpdatePolicy,AllowInfo,std::less<tagUpdatePolicy>,std::allocator<std::pair<tagUpdatePolicy const,AllowInfo>>,0>>::~_Tree<std::_Tmap_traits<tagUpdatePolicy,AllowInfo,std::less<tagUpdatePolicy>,std::allocator<std::pair<tagUpdatePolicy const,AllowInfo>>,0>>(void)

- ea: `0x180014bd0`
- end: `0x180014c3b`
- name: `??1?$_Tree@V?$_Tmap_traits@W4tagUpdatePolicy@@UAllowInfo@@U?$less@W4tagUpdatePolicy@@@std@@V?$allocator@U?$pair@$$CBW4tagUpdatePolicy@@UAllowInfo@@@std@@@4@$0A@@std@@@std@@QEAA@XZ`
- size: `107`
- prototype: `void __fastcall(void **)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x18003840f`
- `0x180039680`
- `0x1800396a0`
- `0x1800396e0`
- `0x180039700`

## callees

- `0x180010260`
- `0x180014bd0`
- `0x180014dbc`
- `0x18003002c`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>::~_Tree<std::_Tmap_traits<enum tagUpdatePolicy,AllowInfo,std::less<enum tagUpdatePolicy>,std::allocator<std::pair<enum tagUpdatePolicy const,AllowInfo>>,0>>(
        void **a1)
{
  _QWORD *v2; // rdi
  _QWORD *v3; // rcx
  void *v4; // rbx

  v2 = (_QWORD *)*((_QWORD *)*a1 + 1);
  while ( !*((_BYTE *)v2 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<enum tagEnterprisePolicy const,AllowInfo>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<enum tagEnterprisePolicy const,AllowInfo>,void *>>>(
      (__int64)a1,
      (__int64)a1,
      v2[2]);
    v3 = v2;
    v4 = v2;
    v2 = (_QWORD *)*v2;
    std::wstring::~wstring(v3 + 5);
    operator delete(v4);
  }
  operator delete(*a1);
}

```

## disassembly

```asm
0x180014bd0  mov     [rsp+arg_8], rbx
0x180014bd5  mov     [rsp+arg_10], rsi
0x180014bda  push    rdi
0x180014bdb  sub     rsp, 20h
0x180014bdf  mov     rax, [rcx]
0x180014be2  mov     rsi, rcx
0x180014be5  mov     rdi, [rax+8]
0x180014be9  jmp     short loc_180014C19
0x180014beb  mov     r8, [rdi+10h]
0x180014bef  mov     rdx, rsi
0x180014bf2  mov     rcx, rsi
0x180014bf5  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<tagEnterprisePolicy const,AllowInfo>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<tagEnterprisePolicy const,AllowInfo>,void *>>>(std::allocator<std::_Tree_node<std::pair<tagEnterprisePolicy const,AllowInfo>,void *>> &,std::_Tree_node<std::pair<tagEnterprisePolicy const,AllowInfo>,void *> *)
0x180014bfa  mov     rcx, rdi
0x180014bfd  mov     rbx, rdi
0x180014c00  mov     rdi, [rdi]
0x180014c03  add     rcx, 28h ; '('; void *
0x180014c07  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014c0c  mov     edx, 50h ; 'P'
0x180014c11  mov     rcx, rbx; Block
0x180014c14  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014c19  cmp     byte ptr [rdi+19h], 0
0x180014c1d  jz      short loc_180014BEB
0x180014c1f  mov     rcx, [rsi]; Block
0x180014c22  mov     edx, 50h ; 'P'
0x180014c27  mov     rbx, [rsp+28h+arg_8]
0x180014c2c  mov     rsi, [rsp+28h+arg_10]
0x180014c31  add     rsp, 20h
0x180014c35  pop     rdi
0x180014c36  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
