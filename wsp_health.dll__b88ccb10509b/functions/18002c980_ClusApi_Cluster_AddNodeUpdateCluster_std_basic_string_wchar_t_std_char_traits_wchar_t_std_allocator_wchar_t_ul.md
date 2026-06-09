# ClusApi::Cluster::AddNodeUpdateCluster(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong *)

- ea: `0x18002c980`
- end: `0x18002c9dd`
- name: `?AddNodeUpdateCluster@Cluster@ClusApi@@UEAAJV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAK@Z`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180002ae0`
- `0x18000d618`
- `0x18000d6dc`

## import_xrefs

- `CLUSAPI!CCHlpAddNodeUpdateCluster` at `0x18002c9b3`
- `CLUSAPI!CCHlpAddNodeUpdateCluster` at `0x18002c9b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ClusApi::Cluster::AddNodeUpdateCluster(__int64 a1, __int64 a2)
{
  wchar_t *v3; // rax
  __int64 v4; // r9
  unsigned int *v5; // r8
  unsigned int updated; // ebx

  v3 = (wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
  updated = CCHlpAddNodeUpdateCluster(*(struct _HCLUSTER **)(v4 + 24), v3, v5);
  std::wstring::_Tidy_deallocate(a2);
  return updated;
}

```

## disassembly

```asm
0x18002c980  mov     [rsp+arg_18], rbx
0x18002c985  push    rdi
0x18002c986  sub     rsp, 30h
0x18002c98a  mov     rax, cs:__security_cookie
0x18002c991  xor     rax, rsp
0x18002c994  mov     [rsp+38h+var_10], rax
0x18002c999  mov     rdi, rdx
0x18002c99c  mov     r9, rcx
0x18002c99f  mov     [rsp+38h+var_18], rdx
0x18002c9a4  mov     rcx, rdx
0x18002c9a7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002c9ac  mov     rdx, rax
0x18002c9af  mov     rcx, [r9+18h]
0x18002c9b3  call    cs:__imp_?CCHlpAddNodeUpdateCluster@@YAJPEAU_HCLUSTER@@PEA_WPEAK@Z; CCHlpAddNodeUpdateCluster(_HCLUSTER *,wchar_t *,ulong *)
0x18002c9b9  mov     ebx, eax
0x18002c9bb  mov     rcx, rdi
0x18002c9be  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002c9c3  mov     eax, ebx
0x18002c9c5  mov     rcx, [rsp+38h+var_10]
0x18002c9ca  xor     rcx, rsp; StackCookie
0x18002c9cd  call    __security_check_cookie
0x18002c9d2  mov     rbx, [rsp+38h+arg_18]
0x18002c9d7  add     rsp, 30h
0x18002c9db  pop     rdi
0x18002c9dc  retn
```
