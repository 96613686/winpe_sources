# ClusApi::Resource::RemovePossibleOwner(std::shared_ptr<ClusApi::INode> const &,wchar_t const *)

- ea: `0x180033f40`
- end: `0x180033f9b`
- name: `?RemovePossibleOwner@Resource@ClusApi@@UEAAJAEBV?$shared_ptr@UINode@ClusApi@@@std@@PEB_W@Z`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180033f40`
- `0x18008e010`

## import_xrefs

- `CLUSAPI!RemoveClusterResourceNodeEx` at `0x180033f77`
- `CLUSAPI!RemoveClusterResourceNodeEx` at `0x180033f77`

## string_xrefs

- `0x180033f66`: `cluswmiext!ClusApi::Resource::RemovePossibleOwner`

## pseudocode

```c
__int64 __fastcall ClusApi::Resource::RemovePossibleOwner(__int64 a1, _QWORD *a2, const wchar_t *a3)
{
  __int64 v5; // rax
  const wchar_t *v6; // r8
  __int64 result; // rax

  v5 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 152LL))(*a2);
  v6 = L"cluswmiext!ClusApi::Resource::RemovePossibleOwner";
  if ( a3 )
    v6 = a3;
  result = RemoveClusterResourceNodeEx(*(_QWORD *)(a1 + 56), v5, v6);
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180033f40  mov     [rsp+arg_0], rbx
0x180033f45  push    rdi
0x180033f46  sub     rsp, 20h
0x180033f4a  mov     rdi, rcx
0x180033f4d  mov     rbx, r8
0x180033f50  mov     rcx, [rdx]
0x180033f53  mov     rax, [rcx]
0x180033f56  mov     rax, [rax+98h]
0x180033f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f62  mov     rcx, [rdi+38h]
0x180033f66  lea     r8, aCluswmiextClus_52; "cluswmiext!ClusApi::Resource::RemovePos"...
0x180033f6d  test    rbx, rbx
0x180033f70  mov     rdx, rax
0x180033f73  cmovnz  r8, rbx
0x180033f77  call    cs:__imp_RemoveClusterResourceNodeEx
0x180033f7e  nop     dword ptr [rax+rax+00h]
0x180033f83  test    eax, eax
0x180033f85  jle     short loc_180033F8F
0x180033f87  movzx   eax, ax
0x180033f8a  or      eax, 80070000h
0x180033f8f  mov     rbx, [rsp+28h+arg_0]
0x180033f94  add     rsp, 20h
0x180033f98  pop     rdi
0x180033f99  retn
```
