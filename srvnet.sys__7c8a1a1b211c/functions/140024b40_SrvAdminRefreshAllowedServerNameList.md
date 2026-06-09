# SrvAdminRefreshAllowedServerNameList

- ea: `0x140024b40`
- end: `0x140024bb1`
- name: `SrvAdminRefreshAllowedServerNameList`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x14000fc18`

## callees

- `0x140024b40`
- `0x14004a490`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140024b4d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140024b4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024b6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024b6a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140024b9f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140024b9f`

## string_xrefs

- `0x140024b85`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanServer\Parameters`

## pseudocode

```c
void SrvAdminRefreshAllowedServerNameList()
{
  ExAcquireResourceExclusiveLite(&SrvAdminNameLock, 1u);
  if ( SrvAdminAllowedServerNameList )
    ExFreePoolWithTag(SrvAdminAllowedServerNameList, 0x52736652u);
  SrvLibGetMultiSZList(
    (unsigned int)&SrvAdminAllowedServerNameList,
    (unsigned int)L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
    (unsigned int)L"SrvAllowedServerNames",
    0,
    0);
  ExReleaseResourceLite(&SrvAdminNameLock);
}

```

## disassembly

```asm
0x140024b40  sub     rsp, 38h
0x140024b44  mov     dl, 1; Wait
0x140024b46  lea     rcx, SrvAdminNameLock; Resource
0x140024b4d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140024b54  nop     dword ptr [rax+rax+00h]
0x140024b59  mov     rcx, cs:SrvAdminAllowedServerNameList; P
0x140024b60  test    rcx, rcx
0x140024b63  jz      short loc_140024B76
0x140024b65  mov     edx, 52736652h; Tag
0x140024b6a  call    cs:__imp_ExFreePoolWithTag
0x140024b71  nop     dword ptr [rax+rax+00h]
0x140024b76  xor     r9d, r9d
0x140024b79  mov     [rsp+38h+var_18], 0
0x140024b7e  lea     r8, aSrvallowedserv; "SrvAllowedServerNames"
0x140024b85  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\System\\CurrentCon"...
0x140024b8c  lea     rcx, SrvAdminAllowedServerNameList
0x140024b93  call    SrvLibGetMultiSZList
0x140024b98  lea     rcx, SrvAdminNameLock; Resource
0x140024b9f  call    cs:__imp_ExReleaseResourceLite
0x140024ba6  nop     dword ptr [rax+rax+00h]
0x140024bab  add     rsp, 38h
0x140024baf  retn
```
