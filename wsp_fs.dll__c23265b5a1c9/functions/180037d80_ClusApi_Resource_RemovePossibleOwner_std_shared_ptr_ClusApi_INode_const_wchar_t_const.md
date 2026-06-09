# ClusApi::Resource::RemovePossibleOwner(std::shared_ptr<ClusApi::INode> const &,wchar_t const *)

- ea: `0x180037d80`
- end: `0x180037ddb`
- name: `?RemovePossibleOwner@Resource@ClusApi@@UEAAJAEBV?$shared_ptr@UINode@ClusApi@@@std@@PEB_W@Z`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180037d80`
- `0x1800ab010`

## import_xrefs

- `CLUSAPI!RemoveClusterResourceNodeEx` at `0x180037db7`
- `CLUSAPI!RemoveClusterResourceNodeEx` at `0x180037db7`

## string_xrefs

- `0x180037da6`: `cluswmiext!ClusApi::Resource::RemovePossibleOwner`

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
0x180037d80  mov     [rsp+arg_0], rbx
0x180037d85  push    rdi
0x180037d86  sub     rsp, 20h
0x180037d8a  mov     rdi, rcx
0x180037d8d  mov     rbx, r8
0x180037d90  mov     rcx, [rdx]
0x180037d93  mov     rax, [rcx]
0x180037d96  mov     rax, [rax+98h]
0x180037d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037da2  mov     rcx, [rdi+38h]
0x180037da6  lea     r8, aCluswmiextClus_58; "cluswmiext!ClusApi::Resource::RemovePos"...
0x180037dad  test    rbx, rbx
0x180037db0  mov     rdx, rax
0x180037db3  cmovnz  r8, rbx
0x180037db7  call    cs:__imp_RemoveClusterResourceNodeEx
0x180037dbe  nop     dword ptr [rax+rax+00h]
0x180037dc3  test    eax, eax
0x180037dc5  jle     short loc_180037DCF
0x180037dc7  movzx   eax, ax
0x180037dca  or      eax, 80070000h
0x180037dcf  mov     rbx, [rsp+28h+arg_0]
0x180037dd4  add     rsp, 20h
0x180037dd8  pop     rdi
0x180037dd9  retn
```
