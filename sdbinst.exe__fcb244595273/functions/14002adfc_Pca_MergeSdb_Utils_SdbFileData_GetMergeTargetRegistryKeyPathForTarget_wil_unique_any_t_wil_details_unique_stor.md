# Pca::MergeSdb::Utils::SdbFileData::GetMergeTargetRegistryKeyPathForTarget(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *)

- ea: `0x14002adfc`
- end: `0x14002ae5a`
- name: `?GetMergeTargetRegistryKeyPathForTarget@SdbFileData@Utils@MergeSdb@Pca@@SAKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z`
- size: `94`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140024958`
- `0x14002aa4c`

## callees

- `0x14001008c`
- `0x140021c68`
- `0x14002adfc`

## string_xrefs

- `0x14002ae0b`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates`
- `0x14002ae3d`: `Pca::MergeSdb::Utils::SdbFileData::GetMergeTargetRegistryKeyPathForTarget`
- `0x14002ae2c`: `Failed to concat the sdb merge target registry key path (%d)`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::SdbFileData::GetMergeTargetRegistryKeyPathForTarget(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF

  v6 = a2;
  v3 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short [71],unsigned short [2],unsigned short const *>(
         a1,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates",
         a3,
         &v6);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  if ( (v3 & 0x1FFF0000) == 0x70000 )
    v4 = (unsigned __int16)v3;
  AslLogCallPrintf(
    1,
    "Pca::MergeSdb::Utils::SdbFileData::GetMergeTargetRegistryKeyPathForTarget",
    1998,
    "Failed to concat the sdb merge target registry key path (%d)",
    v4);
  return v4;
}

```

## disassembly

```asm
0x14002adfc  mov     [rsp+arg_8], rdx
0x14002ae01  push    rbx
0x14002ae02  sub     rsp, 30h
0x14002ae06  lea     r9, [rsp+38h+arg_8]
0x14002ae0b  lea     rdx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14002ae12  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$$BY0EH@G$$BY01GPEBG@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEAY0EH@$$CBGAEAY01$$CBGAEBQEBG@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort [71],ushort [2],ushort const *>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const (&)[71],ushort const (&)[2],ushort const * const &)
0x14002ae17  mov     ebx, eax
0x14002ae19  test    eax, eax
0x14002ae1b  jns     short loc_14002AE52
0x14002ae1d  and     eax, 1FFF0000h
0x14002ae22  cmp     eax, 70000h
0x14002ae27  jnz     short loc_14002AE2C
0x14002ae29  movzx   ebx, bx
0x14002ae2c  lea     r9, aFailedToConcat_3; "Failed to concat the sdb merge target r"...
0x14002ae33  mov     [rsp+38h+var_18], ebx
0x14002ae37  mov     r8d, 7CEh
0x14002ae3d  lea     rdx, aPcaMergesdbUti_19; "Pca::MergeSdb::Utils::SdbFileData::GetM"...
0x14002ae44  mov     ecx, 1
0x14002ae49  call    AslLogCallPrintf
0x14002ae4e  mov     eax, ebx
0x14002ae50  jmp     short loc_14002AE54
0x14002ae52  xor     eax, eax
0x14002ae54  add     rsp, 30h
0x14002ae58  pop     rbx
0x14002ae59  retn
```
