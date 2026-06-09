# std::_Hash<std::_Umap_traits<_WHESVC_SCENARIOS,_WNF_STATE_NAME,std::_Uhash_compare<_WHESVC_SCENARIOS,std::hash<_WHESVC_SCENARIOS>,std::equal_to<_WHESVC_SCENARIOS>>,std::allocator<std::pair<_WHESVC_SCENARIOS const,_WNF_STATE_NAME>>,0>>::clear(void)

- ea: `0x180017864`
- end: `0x180017911`
- name: `?clear@?$_Hash@V?$_Umap_traits@W4_WHESVC_SCENARIOS@@U_WNF_STATE_NAME@@V?$_Uhash_compare@W4_WHESVC_SCENARIOS@@U?$hash@W4_WHESVC_SCENARIOS@@@std@@U?$equal_to@W4_WHESVC_SCENARIOS@@@3@@std@@V?$allocator@U?$pair@$$CBW4_WHESVC_SCENARIOS@@U_WNF_STATE_NAME@@@std@@@4@$0A@@std@@@std@@QEAAXXZ`
- size: `173`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800159c8`

## callees

- `0x180003304`
- `0x180017180`
- `0x180017864`

## pseudocode

```c
void __fastcall std::_Hash<std::_Umap_traits<enum _WHESVC_SCENARIOS,_WNF_STATE_NAME,std::_Uhash_compare<enum _WHESVC_SCENARIOS,std::hash<enum _WHESVC_SCENARIOS>,std::equal_to<enum _WHESVC_SCENARIOS>>,std::allocator<std::pair<enum _WHESVC_SCENARIOS const,_WNF_STATE_NAME>>,0>>::clear(
        _QWORD *a1)
{
  _QWORD *v2; // rcx
  _QWORD *v3; // rcx
  _QWORD *v4; // rdi
  void *v5; // rdi
  unsigned __int64 v6; // rcx

  if ( a1[2] )
  {
    v2 = (_QWORD *)a1[1];
    if ( a1[7] >> 3 <= a1[2] )
    {
      *(_QWORD *)v2[1] = 0;
      v3 = (_QWORD *)*v2;
      if ( v3 )
      {
        do
        {
          v4 = (_QWORD *)*v3;
          operator delete(v3);
          v3 = v4;
        }
        while ( v4 );
      }
      *(_QWORD *)a1[1] = a1[1];
      *(_QWORD *)(a1[1] + 8LL) = a1[1];
      a1[2] = 0;
      v5 = (void *)a1[3];
      v6 = (unsigned __int64)(a1[4] - (_QWORD)v5 + 7LL) >> 3;
      if ( (unsigned __int64)v5 > a1[4] )
        v6 = 0;
      if ( v6 )
        memset64(v5, a1[1], v6);
    }
    else
    {
      std::_Hash<std::_Umap_traits<enum _WHESVC_SCENARIOS,_WNF_STATE_NAME,std::_Uhash_compare<enum _WHESVC_SCENARIOS,std::hash<enum _WHESVC_SCENARIOS>,std::equal_to<enum _WHESVC_SCENARIOS>>,std::allocator<std::pair<enum _WHESVC_SCENARIOS const,_WNF_STATE_NAME>>,0>>::_Unchecked_erase(
        a1,
        (_QWORD *)*v2,
        v2);
    }
  }
}

```

## disassembly

```asm
0x180017864  mov     [rsp+arg_0], rbx
0x180017869  push    rdi
0x18001786a  sub     rsp, 20h
0x18001786e  cmp     qword ptr [rcx+10h], 0
0x180017873  mov     rbx, rcx
0x180017876  jz      loc_180017906
0x18001787c  mov     rax, [rbx+38h]
0x180017880  mov     rcx, [rcx+8]
0x180017884  shr     rax, 3
0x180017888  cmp     rax, [rbx+10h]
0x18001788c  jbe     short loc_18001789E
0x18001788e  mov     rdx, [rcx]
0x180017891  mov     r8, rcx
0x180017894  mov     rcx, rbx
0x180017897  call    ?_Unchecked_erase@?$_Hash@V?$_Umap_traits@W4_WHESVC_SCENARIOS@@U_WNF_STATE_NAME@@V?$_Uhash_compare@W4_WHESVC_SCENARIOS@@U?$hash@W4_WHESVC_SCENARIOS@@@std@@U?$equal_to@W4_WHESVC_SCENARIOS@@@3@@std@@V?$allocator@U?$pair@$$CBW4_WHESVC_SCENARIOS@@U_WNF_STATE_NAME@@@std@@@4@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBW4_WHESVC_SCENARIOS@@U_WNF_STATE_NAME@@@std@@PEAX@2@PEAU32@QEAU32@@Z; std::_Hash<std::_Umap_traits<_WHESVC_SCENARIOS,_WNF_STATE_NAME,std::_Uhash_compare<_WHESVC_SCENARIOS,std::hash<_WHESVC_SCENARIOS>,std::equal_to<_WHESVC_SCENARIOS>>,std::allocator<std::pair<_WHESVC_SCENARIOS const,_WNF_STATE_NAME>>,0>>::_Unchecked_erase(std::_List_node<std::pair<_WHESVC_SCENARIOS const,_WNF_STATE_NAME>,void *> *,std::_List_node<std::pair<_WHESVC_SCENARIOS const,_WNF_STATE_NAME>,void *> * const)
0x18001789c  jmp     short loc_180017906
0x18001789e  mov     rax, [rcx+8]
0x1800178a2  mov     qword ptr [rax], 0
0x1800178a9  mov     rcx, [rcx]; void *
0x1800178ac  test    rcx, rcx
0x1800178af  jz      short loc_1800178C6
0x1800178b1  mov     rdi, [rcx]
0x1800178b4  mov     edx, 20h ; ' '; unsigned __int64
0x1800178b9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800178be  mov     rcx, rdi
0x1800178c1  test    rdi, rdi
0x1800178c4  jnz     short loc_1800178B1
0x1800178c6  mov     rax, [rbx+8]
0x1800178ca  xor     edx, edx
0x1800178cc  mov     [rax], rax
0x1800178cf  mov     rax, [rbx+8]
0x1800178d3  mov     [rax+8], rax
0x1800178d7  mov     qword ptr [rbx+10h], 0
0x1800178df  mov     rdi, [rbx+18h]
0x1800178e3  mov     rcx, [rbx+20h]
0x1800178e7  sub     rcx, rdi
0x1800178ea  add     rcx, 7
0x1800178ee  shr     rcx, 3
0x1800178f2  cmp     rdi, [rbx+20h]
0x1800178f6  cmova   rcx, rdx
0x1800178fa  test    rcx, rcx
0x1800178fd  jz      short loc_180017906
0x1800178ff  mov     rax, [rbx+8]
0x180017903  rep stosq
0x180017906  mov     rbx, [rsp+28h+arg_0]
0x18001790b  add     rsp, 20h
0x18001790f  pop     rdi
0x180017910  retn
```
