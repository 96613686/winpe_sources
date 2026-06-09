# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,_WHESVC_ACTION_CONFIG_VALUE,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_WHESVC_ACTION_CONFIG_VALUE>>,0>>::_Clear_guard::~_Clear_guard(void)

- ea: `0x180026088`
- end: `0x180026154`
- name: `??1_Clear_guard@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WHESVC_ACTION_CONFIG_VALUE@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WHESVC_ACTION_CONFIG_VALUE@@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `204`
- prototype: `void __fastcall(unsigned __int64 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002615c`

## callees

- `0x180003304`
- `0x1800115e0`
- `0x180026088`
- `0x18002638c`

## pseudocode

```c
void __fastcall std::_Hash<std::_Umap_traits<std::wstring,_WHESVC_ACTION_CONFIG_VALUE,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,_WHESVC_ACTION_CONFIG_VALUE>>,0>>::_Clear_guard::~_Clear_guard(
        unsigned __int64 **a1)
{
  unsigned __int64 *v1; // rbx
  unsigned __int64 v2; // rcx
  char **v3; // rsi
  char *v4; // rdi
  void *v5; // rdi
  unsigned __int64 v6; // rcx

  v1 = *a1;
  if ( *a1 && v1[2] )
  {
    v2 = v1[1];
    if ( v1[7] >> 3 <= v1[2] )
    {
      **(_QWORD **)(v2 + 8) = 0;
      v3 = *(char ***)v2;
      if ( *(_QWORD *)v2 )
      {
        do
        {
          v4 = *v3;
          std::wstring::~wstring(v3 + 2);
          operator delete(v3, 0x48u);
          v3 = (char **)v4;
        }
        while ( v4 );
      }
      *(_QWORD *)v1[1] = v1[1];
      *(_QWORD *)(v1[1] + 8) = v1[1];
      v1[2] = 0;
      v5 = (void *)v1[3];
      v6 = (v1[4] - (unsigned __int64)v5 + 7) >> 3;
      if ( (unsigned __int64)v5 > v1[4] )
        v6 = 0;
      if ( v6 )
        memset64(v5, v1[1], v6);
    }
    else
    {
      std::_Hash<std::_Umap_traits<std::wstring,_WHESVC_ACTION_CONFIG_VALUE,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,_WHESVC_ACTION_CONFIG_VALUE>>,0>>::_Unchecked_erase(
        v1,
        *(_QWORD *)v2,
        v1[1]);
    }
  }
}

```

## disassembly

```asm
0x180026088  mov     [rsp+arg_0], rbx
0x18002608d  mov     [rsp+arg_8], rsi
0x180026092  push    rdi
0x180026093  sub     rsp, 20h
0x180026097  mov     rbx, [rcx]
0x18002609a  test    rbx, rbx
0x18002609d  jz      loc_180026144
0x1800260a3  cmp     qword ptr [rbx+10h], 0
0x1800260a8  jz      loc_180026144
0x1800260ae  mov     rax, [rbx+38h]
0x1800260b2  mov     rcx, [rbx+8]
0x1800260b6  shr     rax, 3
0x1800260ba  cmp     rax, [rbx+10h]
0x1800260be  jbe     short loc_1800260D0
0x1800260c0  mov     rdx, [rcx]
0x1800260c3  mov     r8, rcx
0x1800260c6  mov     rcx, rbx
0x1800260c9  call    ?_Unchecked_erase@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WHESVC_ACTION_CONFIG_VALUE@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WHESVC_ACTION_CONFIG_VALUE@@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WHESVC_ACTION_CONFIG_VALUE@@@std@@PEAX@2@PEAU32@QEAU32@@Z; std::_Hash<std::_Umap_traits<std::wstring,_WHESVC_ACTION_CONFIG_VALUE,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,_WHESVC_ACTION_CONFIG_VALUE>>,0>>::_Unchecked_erase(std::_List_node<std::pair<std::wstring const,_WHESVC_ACTION_CONFIG_VALUE>,void *> *,std::_List_node<std::pair<std::wstring const,_WHESVC_ACTION_CONFIG_VALUE>,void *> * const)
0x1800260ce  jmp     short loc_180026144
0x1800260d0  mov     rax, [rcx+8]
0x1800260d4  mov     qword ptr [rax], 0
0x1800260db  mov     rsi, [rcx]
0x1800260de  test    rsi, rsi
0x1800260e1  jz      short loc_180026104
0x1800260e3  mov     rdi, [rsi]
0x1800260e6  lea     rcx, [rsi+10h]
0x1800260ea  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800260ef  mov     edx, 48h ; 'H'; unsigned __int64
0x1800260f4  mov     rcx, rsi; void *
0x1800260f7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800260fc  mov     rsi, rdi
0x1800260ff  test    rdi, rdi
0x180026102  jnz     short loc_1800260E3
0x180026104  mov     rax, [rbx+8]
0x180026108  xor     edx, edx
0x18002610a  mov     [rax], rax
0x18002610d  mov     rax, [rbx+8]
0x180026111  mov     [rax+8], rax
0x180026115  mov     qword ptr [rbx+10h], 0
0x18002611d  mov     rdi, [rbx+18h]
0x180026121  mov     rcx, [rbx+20h]
0x180026125  sub     rcx, rdi
0x180026128  add     rcx, 7
0x18002612c  shr     rcx, 3
0x180026130  cmp     rdi, [rbx+20h]
0x180026134  cmova   rcx, rdx
0x180026138  test    rcx, rcx
0x18002613b  jz      short loc_180026144
0x18002613d  mov     rax, [rbx+8]
0x180026141  rep stosq
0x180026144  mov     rbx, [rsp+28h+arg_0]
0x180026149  mov     rsi, [rsp+28h+arg_8]
0x18002614e  add     rsp, 20h
0x180026152  pop     rdi
0x180026153  retn
```
