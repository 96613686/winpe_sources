# ClusApi::Cluster::AddNodeUpdateCluster(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong *)

- ea: `0x180030690`
- end: `0x1800306ed`
- name: `?AddNodeUpdateCluster@Cluster@ClusApi@@UEAAJV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAK@Z`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180002a70`
- `0x18000a6dc`
- `0x18000dd74`

## import_xrefs

- `CLUSAPI!CCHlpAddNodeUpdateCluster` at `0x1800306c3`
- `CLUSAPI!CCHlpAddNodeUpdateCluster` at `0x1800306c3`

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
0x180030690  mov     [rsp+arg_18], rbx
0x180030695  push    rdi
0x180030696  sub     rsp, 30h
0x18003069a  mov     rax, cs:__security_cookie
0x1800306a1  xor     rax, rsp
0x1800306a4  mov     [rsp+38h+var_10], rax
0x1800306a9  mov     rdi, rdx
0x1800306ac  mov     r9, rcx
0x1800306af  mov     [rsp+38h+var_18], rdx
0x1800306b4  mov     rcx, rdx
0x1800306b7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800306bc  mov     rdx, rax
0x1800306bf  mov     rcx, [r9+18h]
0x1800306c3  call    cs:__imp_?CCHlpAddNodeUpdateCluster@@YAJPEAU_HCLUSTER@@PEA_WPEAK@Z; CCHlpAddNodeUpdateCluster(_HCLUSTER *,wchar_t *,ulong *)
0x1800306c9  mov     ebx, eax
0x1800306cb  mov     rcx, rdi
0x1800306ce  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800306d3  mov     eax, ebx
0x1800306d5  mov     rcx, [rsp+38h+var_10]
0x1800306da  xor     rcx, rsp; StackCookie
0x1800306dd  call    __security_check_cookie
0x1800306e2  mov     rbx, [rsp+38h+arg_18]
0x1800306e7  add     rsp, 30h
0x1800306eb  pop     rdi
0x1800306ec  retn
```
