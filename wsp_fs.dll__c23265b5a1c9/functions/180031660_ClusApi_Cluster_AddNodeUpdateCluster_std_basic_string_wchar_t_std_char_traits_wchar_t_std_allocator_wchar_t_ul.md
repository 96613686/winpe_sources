# ClusApi::Cluster::AddNodeUpdateCluster(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong *)

- ea: `0x180031660`
- end: `0x1800316c4`
- name: `?AddNodeUpdateCluster@Cluster@ClusApi@@UEAAJV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAK@Z`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180002ad0`
- `0x18000aa10`
- `0x18000e14c`

## import_xrefs

- `CLUSAPI!CCHlpAddNodeUpdateCluster` at `0x180031693`
- `CLUSAPI!CCHlpAddNodeUpdateCluster` at `0x180031693`

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
0x180031660  mov     [rsp+arg_18], rbx
0x180031665  push    rdi
0x180031666  sub     rsp, 30h
0x18003166a  mov     rax, cs:__security_cookie
0x180031671  xor     rax, rsp
0x180031674  mov     [rsp+38h+var_10], rax
0x180031679  mov     rdi, rdx
0x18003167c  mov     r9, rcx
0x18003167f  mov     [rsp+38h+var_18], rdx
0x180031684  mov     rcx, rdx
0x180031687  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003168c  mov     rdx, rax
0x18003168f  mov     rcx, [r9+18h]
0x180031693  call    cs:__imp_?CCHlpAddNodeUpdateCluster@@YAJPEAU_HCLUSTER@@PEA_WPEAK@Z; CCHlpAddNodeUpdateCluster(_HCLUSTER *,wchar_t *,ulong *)
0x18003169a  nop     dword ptr [rax+rax+00h]
0x18003169f  mov     ebx, eax
0x1800316a1  mov     rcx, rdi
0x1800316a4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800316a9  mov     eax, ebx
0x1800316ab  mov     rcx, [rsp+38h+var_10]
0x1800316b0  xor     rcx, rsp; StackCookie
0x1800316b3  call    __security_check_cookie
0x1800316b8  mov     rbx, [rsp+38h+arg_18]
0x1800316bd  add     rsp, 30h
0x1800316c1  pop     rdi
0x1800316c2  retn
```
