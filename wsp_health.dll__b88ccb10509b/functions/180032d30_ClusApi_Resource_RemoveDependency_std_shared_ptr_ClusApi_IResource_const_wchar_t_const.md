# ClusApi::Resource::RemoveDependency(std::shared_ptr<ClusApi::IResource> const &,wchar_t const *)

- ea: `0x180032d30`
- end: `0x180032d84`
- name: `?RemoveDependency@Resource@ClusApi@@UEAAJAEBV?$shared_ptr@UIResource@ClusApi@@@std@@PEB_W@Z`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180032d30`
- `0x18008c010`

## import_xrefs

- `CLUSAPI!RemoveClusterResourceDependencyEx` at `0x180032d67`
- `CLUSAPI!RemoveClusterResourceDependencyEx` at `0x180032d67`

## string_xrefs

- `0x180032d56`: `cluswmiext!ClusApi::Resource::RemoveDependency`

## pseudocode

```c
__int64 __fastcall ClusApi::Resource::RemoveDependency(__int64 a1, _QWORD *a2, const wchar_t *a3)
{
  __int64 v5; // rax
  const wchar_t *v6; // r8
  __int64 result; // rax

  v5 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 336LL))(*a2);
  v6 = L"cluswmiext!ClusApi::Resource::RemoveDependency";
  if ( a3 )
    v6 = a3;
  result = RemoveClusterResourceDependencyEx(*(_QWORD *)(a1 + 56), v5, v6);
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180032d30  mov     [rsp+arg_0], rbx
0x180032d35  push    rdi
0x180032d36  sub     rsp, 20h
0x180032d3a  mov     rdi, rcx
0x180032d3d  mov     rbx, r8
0x180032d40  mov     rcx, [rdx]
0x180032d43  mov     rax, [rcx]
0x180032d46  mov     rax, [rax+150h]
0x180032d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032d52  mov     rcx, [rdi+38h]
0x180032d56  lea     r8, aCluswmiextClus_24; "cluswmiext!ClusApi::Resource::RemoveDep"...
0x180032d5d  test    rbx, rbx
0x180032d60  mov     rdx, rax
0x180032d63  cmovnz  r8, rbx
0x180032d67  call    cs:__imp_RemoveClusterResourceDependencyEx
0x180032d6d  test    eax, eax
0x180032d6f  jle     short loc_180032D79
0x180032d71  movzx   eax, ax
0x180032d74  or      eax, 80070000h
0x180032d79  mov     rbx, [rsp+28h+arg_0]
0x180032d7e  add     rsp, 20h
0x180032d82  pop     rdi
0x180032d83  retn
```
