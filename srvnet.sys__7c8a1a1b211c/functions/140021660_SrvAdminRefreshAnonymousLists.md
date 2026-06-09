# SrvAdminRefreshAnonymousLists

- ea: `0x140021660`
- end: `0x140021771`
- name: `SrvAdminRefreshAnonymousLists`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x14000fc18`

## callees

- `0x140021660`
- `0x14004a490`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002166f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002166f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400216bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021709`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400216bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021709`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002175c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002175c`

## string_xrefs

- `0x140021697`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanServer\Parameters`
- `0x1400216e4`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanServer\Parameters`

## pseudocode

```c
__int64 SrvAdminRefreshAnonymousLists()
{
  PVOID v0; // rbx
  PVOID v1; // rbx

  ExAcquireResourceExclusiveLite(&AnonymousLock, 1u);
  v0 = SrvAdminNullSessionPipes;
  SrvAdminNullSessionPipes = 0;
  SrvLibGetMultiSZList(
    (unsigned int)&SrvAdminNullSessionPipes,
    (unsigned int)L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
    (unsigned int)L"NullSessionPipes",
    0,
    0);
  if ( v0 )
    ExFreePoolWithTag(v0, 0x52736652u);
  v1 = SrvAdminNullSessionShares;
  SrvAdminNullSessionShares = 0;
  SrvLibGetMultiSZList(
    (unsigned int)&SrvAdminNullSessionShares,
    (unsigned int)L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
    (unsigned int)L"NullSessionShares",
    0,
    0);
  if ( v1 )
    ExFreePoolWithTag(v1, 0x52736652u);
  SrvAdminNullSessionPipePermitted = 0;
  SrvAdminNullSessionSharePermitted = 0;
  if ( SrvAdminNullSessionShares )
    SrvAdminNullSessionSharePermitted = *(_QWORD *)SrvAdminNullSessionShares != 0;
  if ( SrvAdminNullSessionPipes && *(_QWORD *)SrvAdminNullSessionPipes )
    SrvAdminNullSessionPipePermitted = 1;
  ExReleaseResourceLite(&AnonymousLock);
  return 0;
}

```

## disassembly

```asm
0x140021660  push    rbx
0x140021662  sub     rsp, 30h
0x140021666  mov     dl, 1; Wait
0x140021668  lea     rcx, AnonymousLock; Resource
0x14002166f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140021676  nop     dword ptr [rax+rax+00h]
0x14002167b  mov     rbx, cs:SrvAdminNullSessionPipes
0x140021682  lea     r8, aNullsessionpip; "NullSessionPipes"
0x140021689  xor     r9d, r9d
0x14002168c  mov     cs:SrvAdminNullSessionPipes, 0
0x140021697  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\System\\CurrentCon"...
0x14002169e  mov     [rsp+38h+var_18], 0
0x1400216a3  lea     rcx, SrvAdminNullSessionPipes
0x1400216aa  call    SrvLibGetMultiSZList
0x1400216af  test    rbx, rbx
0x1400216b2  jz      short loc_1400216C8
0x1400216b4  mov     edx, 52736652h; Tag
0x1400216b9  mov     rcx, rbx; P
0x1400216bc  call    cs:__imp_ExFreePoolWithTag
0x1400216c3  nop     dword ptr [rax+rax+00h]
0x1400216c8  mov     rbx, cs:SrvAdminNullSessionShares
0x1400216cf  lea     r8, aNullsessionsha; "NullSessionShares"
0x1400216d6  xor     r9d, r9d
0x1400216d9  mov     cs:SrvAdminNullSessionShares, 0
0x1400216e4  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400216eb  mov     [rsp+38h+var_18], 0
0x1400216f0  lea     rcx, SrvAdminNullSessionShares
0x1400216f7  call    SrvLibGetMultiSZList
0x1400216fc  test    rbx, rbx
0x1400216ff  jz      short loc_140021715
0x140021701  mov     edx, 52736652h; Tag
0x140021706  mov     rcx, rbx; P
0x140021709  call    cs:__imp_ExFreePoolWithTag
0x140021710  nop     dword ptr [rax+rax+00h]
0x140021715  mov     rax, cs:SrvAdminNullSessionShares
0x14002171c  mov     cs:SrvAdminNullSessionPipePermitted, 0
0x140021723  mov     cs:SrvAdminNullSessionSharePermitted, 0
0x14002172a  test    rax, rax
0x14002172d  jz      short loc_14002173C
0x14002172f  cmp     qword ptr [rax], 0
0x140021733  jz      short loc_14002173C
0x140021735  mov     cs:SrvAdminNullSessionSharePermitted, 1
0x14002173c  mov     rax, cs:SrvAdminNullSessionPipes
0x140021743  test    rax, rax
0x140021746  jz      short loc_140021755
0x140021748  cmp     qword ptr [rax], 0
0x14002174c  jz      short loc_140021755
0x14002174e  mov     cs:SrvAdminNullSessionPipePermitted, 1
0x140021755  lea     rcx, AnonymousLock; Resource
0x14002175c  call    cs:__imp_ExReleaseResourceLite
0x140021763  nop     dword ptr [rax+rax+00h]
0x140021768  xor     eax, eax
0x14002176a  add     rsp, 30h
0x14002176e  pop     rbx
0x14002176f  retn
```
