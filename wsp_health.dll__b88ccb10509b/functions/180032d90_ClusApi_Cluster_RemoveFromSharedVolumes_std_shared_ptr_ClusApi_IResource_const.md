# ClusApi::Cluster::RemoveFromSharedVolumes(std::shared_ptr<ClusApi::IResource> const &)

- ea: `0x180032d90`
- end: `0x180032dc0`
- name: `?RemoveFromSharedVolumes@Cluster@ClusApi@@UEAAJAEBV?$shared_ptr@UIResource@ClusApi@@@std@@@Z`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180032d90`
- `0x18008c010`

## import_xrefs

- `CLUSAPI!RemoveResourceFromClusterSharedVolumes` at `0x180032da9`
- `CLUSAPI!RemoveResourceFromClusterSharedVolumes` at `0x180032da9`

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
0x180032d90  sub     rsp, 28h
0x180032d94  mov     rcx, [rdx]
0x180032d97  mov     rax, [rcx]
0x180032d9a  mov     rax, [rax+150h]
0x180032da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032da6  mov     rcx, rax; hResource
0x180032da9  call    cs:__imp_RemoveResourceFromClusterSharedVolumes
0x180032daf  test    eax, eax
0x180032db1  jle     short loc_180032DBB
0x180032db3  movzx   eax, ax
0x180032db6  or      eax, 80070000h
0x180032dbb  add     rsp, 28h
0x180032dbf  retn
```
