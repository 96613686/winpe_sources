# ClusApi::Resource::RemoveDependency(std::shared_ptr<ClusApi::IResource> const &,wchar_t const *)

- ea: `0x180037cd0`
- end: `0x180037d2b`
- name: `?RemoveDependency@Resource@ClusApi@@UEAAJAEBV?$shared_ptr@UIResource@ClusApi@@@std@@PEB_W@Z`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180037cd0`
- `0x1800ab010`

## import_xrefs

- `CLUSAPI!RemoveClusterResourceDependencyEx` at `0x180037d07`
- `CLUSAPI!RemoveClusterResourceDependencyEx` at `0x180037d07`

## string_xrefs

- `0x180037cf6`: `cluswmiext!ClusApi::Resource::RemoveDependency`

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
0x180037cd0  mov     [rsp+arg_0], rbx
0x180037cd5  push    rdi
0x180037cd6  sub     rsp, 20h
0x180037cda  mov     rdi, rcx
0x180037cdd  mov     rbx, r8
0x180037ce0  mov     rcx, [rdx]
0x180037ce3  mov     rax, [rcx]
0x180037ce6  mov     rax, [rax+150h]
0x180037ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037cf2  mov     rcx, [rdi+38h]
0x180037cf6  lea     r8, aCluswmiextClus_25; "cluswmiext!ClusApi::Resource::RemoveDep"...
0x180037cfd  test    rbx, rbx
0x180037d00  mov     rdx, rax
0x180037d03  cmovnz  r8, rbx
0x180037d07  call    cs:__imp_RemoveClusterResourceDependencyEx
0x180037d0e  nop     dword ptr [rax+rax+00h]
0x180037d13  test    eax, eax
0x180037d15  jle     short loc_180037D1F
0x180037d17  movzx   eax, ax
0x180037d1a  or      eax, 80070000h
0x180037d1f  mov     rbx, [rsp+28h+arg_0]
0x180037d24  add     rsp, 20h
0x180037d28  pop     rdi
0x180037d29  retn
```
