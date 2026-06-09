# ClusApi::Cluster::RemoveFromSharedVolumes(std::shared_ptr<ClusApi::IResource> const &)

- ea: `0x180037d40`
- end: `0x180037d77`
- name: `?RemoveFromSharedVolumes@Cluster@ClusApi@@UEAAJAEBV?$shared_ptr@UIResource@ClusApi@@@std@@@Z`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180037d40`
- `0x1800ab010`

## import_xrefs

- `CLUSAPI!RemoveResourceFromClusterSharedVolumes` at `0x180037d59`
- `CLUSAPI!RemoveResourceFromClusterSharedVolumes` at `0x180037d59`

## pseudocode

```c
signed int __fastcall ClusApi::Cluster::RemoveFromSharedVolumes(__int64 a1, _QWORD *a2)
{
  struct _HRESOURCE *v2; // rax
  signed int result; // eax

  v2 = (struct _HRESOURCE *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 336LL))(*a2);
  result = RemoveResourceFromClusterSharedVolumes(v2);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180037d40  sub     rsp, 28h
0x180037d44  mov     rcx, [rdx]
0x180037d47  mov     rax, [rcx]
0x180037d4a  mov     rax, [rax+150h]
0x180037d51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037d56  mov     rcx, rax; hResource
0x180037d59  call    cs:__imp_RemoveResourceFromClusterSharedVolumes
0x180037d60  nop     dword ptr [rax+rax+00h]
0x180037d65  test    eax, eax
0x180037d67  jle     short loc_180037D71
0x180037d69  movzx   eax, ax
0x180037d6c  or      eax, 80070000h
0x180037d71  add     rsp, 28h
0x180037d75  retn
```
