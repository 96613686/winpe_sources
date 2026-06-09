# SrvAdminRefreshPipeList

- ea: `0x140021780`
- end: `0x14002187a`
- name: `SrvAdminRefreshPipeList`
- size: `250`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x140021780`
- `0x14004a490`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140021798`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140021798`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021803`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002184a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021803`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002184a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002185d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002185d`

## string_xrefs

- `0x1400217ce`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanServer\Parameters`
- `0x140021825`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanServer\Parameters`

## pseudocode

```c
void SrvAdminRefreshPipeList()
{
  wchar_t **v0; // rdi
  wchar_t **v1; // rbx

  ExAcquireResourceExclusiveLite(&AnonymousLock, 1u);
  v0 = (wchar_t **)SrvAdminNoRemapPipeNames;
  v1 = (wchar_t **)SrvAdminClusterPipeNames;
  SrvAdminNoRemapPipeNames = 0;
  SrvAdminClusterPipeNames = 0;
  SrvLibGetMultiSZList(
    (unsigned int)&SrvAdminNoRemapPipeNames,
    (unsigned int)L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
    (unsigned int)L"NoRemapPipes",
    (unsigned int)StrDefaultNoRemapPipeNames,
    1);
  if ( v0 && v0 != StrDefaultNoRemapPipeNames )
    ExFreePoolWithTag(v0, 0x52736652u);
  SrvLibGetMultiSZList(
    (unsigned int)&SrvAdminClusterPipeNames,
    (unsigned int)L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
    (unsigned int)L"ClusterPipes",
    (unsigned int)StrDefaultClusterPipeNames,
    1);
  if ( v1 && v1 != StrDefaultClusterPipeNames )
    ExFreePoolWithTag(v1, 0x52736652u);
  ExReleaseResourceLite(&AnonymousLock);
}

```

## disassembly

```asm
0x140021780  mov     [rsp+arg_0], rbx
0x140021785  mov     [rsp+arg_8], rbp
0x14002178a  push    rdi
0x14002178b  sub     rsp, 30h
0x14002178f  mov     dl, 1; Wait
0x140021791  lea     rcx, AnonymousLock; Resource
0x140021798  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14002179f  nop     dword ptr [rax+rax+00h]
0x1400217a4  mov     rdi, cs:SrvAdminNoRemapPipeNames
0x1400217ab  lea     rbp, StrDefaultNoRemapPipeNames
0x1400217b2  mov     rbx, cs:SrvAdminClusterPipeNames
0x1400217b9  lea     r8, aNoremappipes; "NoRemapPipes"
0x1400217c0  mov     r9, rbp
0x1400217c3  mov     cs:SrvAdminNoRemapPipeNames, 0
0x1400217ce  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400217d5  mov     cs:SrvAdminClusterPipeNames, 0
0x1400217e0  lea     rcx, SrvAdminNoRemapPipeNames
0x1400217e7  mov     [rsp+38h+var_18], 1
0x1400217ec  call    SrvLibGetMultiSZList
0x1400217f1  test    rdi, rdi
0x1400217f4  jz      short loc_14002180F
0x1400217f6  cmp     rdi, rbp
0x1400217f9  jz      short loc_14002180F
0x1400217fb  mov     edx, 52736652h; Tag
0x140021800  mov     rcx, rdi; P
0x140021803  call    cs:__imp_ExFreePoolWithTag
0x14002180a  nop     dword ptr [rax+rax+00h]
0x14002180f  lea     rdi, StrDefaultClusterPipeNames
0x140021816  mov     [rsp+38h+var_18], 1
0x14002181b  mov     r9, rdi
0x14002181e  lea     r8, aClusterpipes; "ClusterPipes"
0x140021825  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\System\\CurrentCon"...
0x14002182c  lea     rcx, SrvAdminClusterPipeNames
0x140021833  call    SrvLibGetMultiSZList
0x140021838  test    rbx, rbx
0x14002183b  jz      short loc_140021856
0x14002183d  cmp     rbx, rdi
0x140021840  jz      short loc_140021856
0x140021842  mov     edx, 52736652h; Tag
0x140021847  mov     rcx, rbx; P
0x14002184a  call    cs:__imp_ExFreePoolWithTag
0x140021851  nop     dword ptr [rax+rax+00h]
0x140021856  lea     rcx, AnonymousLock; Resource
0x14002185d  call    cs:__imp_ExReleaseResourceLite
0x140021864  nop     dword ptr [rax+rax+00h]
0x140021869  mov     rbx, [rsp+38h+arg_0]
0x14002186e  mov     rbp, [rsp+38h+arg_8]
0x140021873  add     rsp, 30h
0x140021877  pop     rdi
0x140021878  retn
```
