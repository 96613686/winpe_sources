# ClusApi::Resource::RemovePossibleOwner(std::shared_ptr<ClusApi::INode> const &,wchar_t const *)

- ea: `0x180036b00`
- end: `0x180036b54`
- name: `?RemovePossibleOwner@Resource@ClusApi@@UEAAJAEBV?$shared_ptr@UINode@ClusApi@@@std@@PEB_W@Z`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180036b00`
- `0x1800a9010`

## import_xrefs

- `CLUSAPI!RemoveClusterResourceNodeEx` at `0x180036b37`
- `CLUSAPI!RemoveClusterResourceNodeEx` at `0x180036b37`

## string_xrefs

- `0x180036b26`: `cluswmiext!ClusApi::Resource::RemovePossibleOwner`

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
0x180036b00  mov     [rsp+arg_0], rbx
0x180036b05  push    rdi
0x180036b06  sub     rsp, 20h
0x180036b0a  mov     rdi, rcx
0x180036b0d  mov     rbx, r8
0x180036b10  mov     rcx, [rdx]
0x180036b13  mov     rax, [rcx]
0x180036b16  mov     rax, [rax+98h]
0x180036b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b22  mov     rcx, [rdi+38h]
0x180036b26  lea     r8, aCluswmiextClus_58; "cluswmiext!ClusApi::Resource::RemovePos"...
0x180036b2d  test    rbx, rbx
0x180036b30  mov     rdx, rax
0x180036b33  cmovnz  r8, rbx
0x180036b37  call    cs:__imp_RemoveClusterResourceNodeEx
0x180036b3d  test    eax, eax
0x180036b3f  jle     short loc_180036B49
0x180036b41  movzx   eax, ax
0x180036b44  or      eax, 80070000h
0x180036b49  mov     rbx, [rsp+28h+arg_0]
0x180036b4e  add     rsp, 20h
0x180036b52  pop     rdi
0x180036b53  retn
```
