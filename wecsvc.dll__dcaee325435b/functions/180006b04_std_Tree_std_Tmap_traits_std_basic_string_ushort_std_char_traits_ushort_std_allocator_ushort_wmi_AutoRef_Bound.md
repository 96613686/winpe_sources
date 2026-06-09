# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,wmi::AutoRef<BoundSubscription>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,wmi::AutoRef<BoundSubscription>>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,wmi::AutoRef<BoundSubscription>>,void *> *,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,wmi::AutoRef<BoundSubscription>>,void *> *,std::integral_constant<bool,0>)

- ea: `0x180006b04`
- end: `0x180006b92`
- name: `??$_Copy_nodes@U?$integral_constant@_N$0A@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@PEAX@1@PEAU21@0U?$integral_constant@_N$0A@@1@@Z`
- size: `142`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64, char)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180006b04`
- `0x18000b910`
- `0x18000ec24`

## callees

- `0x180006a08`
- `0x180006b04`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<BoundSubscription>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        char a4)
{
  __int64 v8; // rsi
  __int64 v9; // rdi
  __int64 v10; // r9

  v8 = *a1;
  if ( !*(_BYTE *)(a2 + 25) )
  {
    v9 = std::_Tree_buy<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>>::_Buynode<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>> &>(
           a1,
           a2 + 32);
    *(_QWORD *)(v9 + 8) = a3;
    *(_BYTE *)(v9 + 24) = *(_BYTE *)(a2 + 24);
    if ( *(_BYTE *)(v8 + 25) )
      v8 = v9;
    try
    {
      *(_QWORD *)v9 = ((__int64 (*)(void))std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<BoundSubscription>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>)();
      LOBYTE(v10) = a4;
      *(_QWORD *)(v9 + 16) = std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<BoundSubscription>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(
                               a1,
                               *(_QWORD *)(a2 + 16),
                               v9,
                               v10);
    }
    catch ( ... )
    {
      std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<BoundSubscription>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>>,0>>::_Erase(
        a1,
        v8);
      throw;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180006b04  mov     [rsp+arg_10], rbx
0x180006b09  mov     [rsp+arg_0], rcx
0x180006b0e  push    rsi
0x180006b0f  push    rdi
0x180006b10  push    r12
0x180006b12  push    r14
0x180006b14  push    r15
0x180006b16  sub     rsp, 20h
0x180006b1a  mov     bl, r9b
0x180006b1d  mov     r12, r8
0x180006b20  mov     r15, rdx
0x180006b23  mov     r14, rcx
0x180006b26  mov     rsi, [rcx]
0x180006b29  cmp     byte ptr [rdx+19h], 0
0x180006b2d  jnz     short loc_180006B7D
0x180006b2f  add     rdx, 20h ; ' '
0x180006b33  call    ??$_Buynode@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@@?$_Tree_buy@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@PEAX@1@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@1@@Z; std::_Tree_buy<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>>::_Buynode<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>> &>(std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>> &)
0x180006b38  mov     rdi, rax
0x180006b3b  mov     [rax+8], r12
0x180006b3f  mov     al, [r15+18h]
0x180006b43  mov     [rdi+18h], al
0x180006b46  cmp     byte ptr [rsi+19h], 0
0x180006b4a  cmovnz  rsi, rdi
0x180006b4e  mov     [rsp+48h+arg_8], rsi
0x180006b53  mov     r9b, bl
0x180006b56  mov     r8, rdi
0x180006b59  mov     rdx, [r15]
0x180006b5c  mov     rcx, r14
0x180006b5f  call    ??$_Copy_nodes@U?$integral_constant@_N$0A@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@PEAX@1@PEAU21@0U?$integral_constant@_N$0A@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<BoundSubscription>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(std::_Tree_node<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>,void *> *,std::_Tree_node<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>,void *> *,std::integral_constant<bool,0>)
0x180006b64  mov     [rdi], rax
0x180006b67  mov     r9b, bl
0x180006b6a  mov     r8, rdi
0x180006b6d  mov     rdx, [r15+10h]
0x180006b71  mov     rcx, r14
0x180006b74  call    ??$_Copy_nodes@U?$integral_constant@_N$0A@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@PEAX@1@PEAU21@0U?$integral_constant@_N$0A@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<BoundSubscription>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(std::_Tree_node<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>,void *> *,std::_Tree_node<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>,void *> *,std::integral_constant<bool,0>)
0x180006b79  mov     [rdi+10h], rax
0x180006b7d  mov     rax, rsi
0x180006b80  mov     rbx, [rsp+48h+arg_10]
0x180006b85  add     rsp, 20h
0x180006b89  pop     r15
0x180006b8b  pop     r14
0x180006b8d  pop     r12
0x180006b8f  pop     rdi
0x180006b90  pop     rsi
0x180006b91  retn
```
