# std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_WHESVC_ACTION_CONFIG_VALUE>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_WHESVC_ACTION_CONFIG_VALUE>>>>>>(void)

- ea: `0x18001140c`
- end: `0x180011476`
- name: `??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WHESVC_ACTION_CONFIG_VALUE@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ`
- size: `106`
- prototype: `void __fastcall(char **)`
- caller_count: `12`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180011a44`
- `0x180011c90`
- `0x1800188fc`
- `0x18001b670`
- `0x18001c32c`
- `0x1800272bd`
- `0x180027678`
- `0x180027788`
- `0x180027d48`
- `0x180028480`
- `0x1800284b0`
- `0x1800284e0`

## callees

- `0x180003304`
- `0x18001140c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,_WHESVC_ACTION_CONFIG_VALUE>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,_WHESVC_ACTION_CONFIG_VALUE>>>>>>(
        char **a1)
{
  char *v1; // rdx
  unsigned __int64 v3; // rax
  char *v4; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v3 = (a1[2] - v1) & 0xFFFFFFFFFFFFFFF8uLL;
    if ( v3 < 0x1000 )
    {
      v4 = *a1;
    }
    else
    {
      v4 = (char *)*((_QWORD *)v1 - 1);
      if ( (unsigned __int64)(v1 - v4 - 8) > 0x1F )
        __fastfail(5u);
      v3 += 39LL;
    }
    operator delete(v4, v3);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x18001140c  push    rbx
0x18001140e  sub     rsp, 20h
0x180011412  mov     rdx, [rcx]
0x180011415  mov     rbx, rcx
0x180011418  test    rdx, rdx
0x18001141b  jz      short loc_180011470
0x18001141d  mov     rax, [rcx+10h]
0x180011421  sub     rax, rdx
0x180011424  and     rax, 0FFFFFFFFFFFFFFF8h
0x180011428  cmp     rax, 1000h
0x18001142e  jb      short loc_18001144E
0x180011430  mov     rcx, [rdx-8]
0x180011434  sub     rdx, rcx
0x180011437  sub     rdx, 8
0x18001143b  cmp     rdx, 1Fh
0x18001143f  ja      short loc_180011447
0x180011441  add     rax, 27h ; '''
0x180011445  jmp     short loc_180011451
0x180011447  mov     ecx, 5
0x18001144c  int     29h; Win8: RtlFailFast(ecx)
0x18001144e  mov     rcx, rdx; void *
0x180011451  mov     rdx, rax; unsigned __int64
0x180011454  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011459  mov     qword ptr [rbx], 0
0x180011460  mov     qword ptr [rbx+8], 0
0x180011468  mov     qword ptr [rbx+10h], 0
0x180011470  add     rsp, 20h
0x180011474  pop     rbx
0x180011475  retn
```
