# SrvAdminDeleteAlias

- ea: `0x140023a2c`
- end: `0x140023acc`
- name: `SrvAdminDeleteAlias`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140027150`

## callees

- `0x140007360`
- `0x14000a968`
- `0x140023a2c`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140023a3e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140023a3e`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140023a64`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140023a64`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023ab0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023ab0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140023a8b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140023a8b`

## pseudocode

```c
__int64 __fastcall SrvAdminDeleteAlias(__int64 a1)
{
  unsigned int *v2; // rax
  unsigned int *v3; // rbx

  ExAcquireResourceExclusiveLite(&AliasLock, 1u);
  v2 = (unsigned int *)SrvAdminLookupAlias(a1);
  v3 = v2;
  if ( v2 )
  {
    RtlDeleteElementGenericTableAvl(&AliasTableAvl, v2);
    if ( v3 == (unsigned int *)DefaultAlias )
      DefaultAlias = 0;
  }
  ExReleaseResourceLite(&AliasLock);
  if ( !v3 )
    return 3221225524LL;
  SrvNetUpdateMemStatistics(*(v3 - 3), *(v3 - 4), 0);
  ExFreePoolWithTag(v3 - 4, 0);
  return 0;
}

```

## disassembly

```asm
0x140023a2c  push    rbx
0x140023a2e  sub     rsp, 20h
0x140023a32  mov     rbx, rcx
0x140023a35  mov     dl, 1; Wait
0x140023a37  lea     rcx, AliasLock; Resource
0x140023a3e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140023a45  nop     dword ptr [rax+rax+00h]
0x140023a4a  mov     rcx, rbx
0x140023a4d  call    SrvAdminLookupAlias
0x140023a52  mov     rbx, rax
0x140023a55  test    rax, rax
0x140023a58  jz      short loc_140023A84
0x140023a5a  mov     rdx, rax; Buffer
0x140023a5d  lea     rcx, AliasTableAvl; Table
0x140023a64  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140023a6b  nop     dword ptr [rax+rax+00h]
0x140023a70  cmp     rbx, cs:DefaultAlias
0x140023a77  jnz     short loc_140023A84
0x140023a79  mov     cs:DefaultAlias, 0
0x140023a84  lea     rcx, AliasLock; Resource
0x140023a8b  call    cs:__imp_ExReleaseResourceLite
0x140023a92  nop     dword ptr [rax+rax+00h]
0x140023a97  test    rbx, rbx
0x140023a9a  jz      short loc_140023AC0
0x140023a9c  mov     ecx, [rbx-0Ch]
0x140023a9f  xor     r8d, r8d
0x140023aa2  mov     edx, [rbx-10h]
0x140023aa5  call    SrvNetUpdateMemStatistics
0x140023aaa  xor     edx, edx; Tag
0x140023aac  lea     rcx, [rbx-10h]; P
0x140023ab0  call    cs:__imp_ExFreePoolWithTag
0x140023ab7  nop     dword ptr [rax+rax+00h]
0x140023abc  xor     eax, eax
0x140023abe  jmp     short loc_140023AC5
0x140023ac0  mov     eax, 0C0000034h
0x140023ac5  add     rsp, 20h
0x140023ac9  pop     rbx
0x140023aca  retn
```
