# ClusApi::Resource::RemoveDependency(std::shared_ptr<ClusApi::IResource> const &,wchar_t const *)

- ea: `0x180033e90`
- end: `0x180033eeb`
- name: `?RemoveDependency@Resource@ClusApi@@UEAAJAEBV?$shared_ptr@UIResource@ClusApi@@@std@@PEB_W@Z`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180033e90`
- `0x18008e010`

## import_xrefs

- `CLUSAPI!RemoveClusterResourceDependencyEx` at `0x180033ec7`
- `CLUSAPI!RemoveClusterResourceDependencyEx` at `0x180033ec7`

## string_xrefs

- `0x180033eb6`: `cluswmiext!ClusApi::Resource::RemoveDependency`

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
0x180033e90  mov     [rsp+arg_0], rbx
0x180033e95  push    rdi
0x180033e96  sub     rsp, 20h
0x180033e9a  mov     rdi, rcx
0x180033e9d  mov     rbx, r8
0x180033ea0  mov     rcx, [rdx]
0x180033ea3  mov     rax, [rcx]
0x180033ea6  mov     rax, [rax+150h]
0x180033ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033eb2  mov     rcx, [rdi+38h]
0x180033eb6  lea     r8, aCluswmiextClus_24; "cluswmiext!ClusApi::Resource::RemoveDep"...
0x180033ebd  test    rbx, rbx
0x180033ec0  mov     rdx, rax
0x180033ec3  cmovnz  r8, rbx
0x180033ec7  call    cs:__imp_RemoveClusterResourceDependencyEx
0x180033ece  nop     dword ptr [rax+rax+00h]
0x180033ed3  test    eax, eax
0x180033ed5  jle     short loc_180033EDF
0x180033ed7  movzx   eax, ax
0x180033eda  or      eax, 80070000h
0x180033edf  mov     rbx, [rsp+28h+arg_0]
0x180033ee4  add     rsp, 20h
0x180033ee8  pop     rdi
0x180033ee9  retn
```
