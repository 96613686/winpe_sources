# ClusApi::Resource::RemovePossibleOwner(std::shared_ptr<ClusApi::INode> const &,wchar_t const *)

- ea: `0x180032dd0`
- end: `0x180032e24`
- name: `?RemovePossibleOwner@Resource@ClusApi@@UEAAJAEBV?$shared_ptr@UINode@ClusApi@@@std@@PEB_W@Z`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180032dd0`
- `0x18008c010`

## import_xrefs

- `CLUSAPI!RemoveClusterResourceNodeEx` at `0x180032e07`
- `CLUSAPI!RemoveClusterResourceNodeEx` at `0x180032e07`

## string_xrefs

- `0x180032df6`: `cluswmiext!ClusApi::Resource::RemovePossibleOwner`

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
0x180032dd0  mov     [rsp+arg_0], rbx
0x180032dd5  push    rdi
0x180032dd6  sub     rsp, 20h
0x180032dda  mov     rdi, rcx
0x180032ddd  mov     rbx, r8
0x180032de0  mov     rcx, [rdx]
0x180032de3  mov     rax, [rcx]
0x180032de6  mov     rax, [rax+98h]
0x180032ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032df2  mov     rcx, [rdi+38h]
0x180032df6  lea     r8, aCluswmiextClus_52; "cluswmiext!ClusApi::Resource::RemovePos"...
0x180032dfd  test    rbx, rbx
0x180032e00  mov     rdx, rax
0x180032e03  cmovnz  r8, rbx
0x180032e07  call    cs:__imp_RemoveClusterResourceNodeEx
0x180032e0d  test    eax, eax
0x180032e0f  jle     short loc_180032E19
0x180032e11  movzx   eax, ax
0x180032e14  or      eax, 80070000h
0x180032e19  mov     rbx, [rsp+28h+arg_0]
0x180032e1e  add     rsp, 20h
0x180032e22  pop     rdi
0x180032e23  retn
```
