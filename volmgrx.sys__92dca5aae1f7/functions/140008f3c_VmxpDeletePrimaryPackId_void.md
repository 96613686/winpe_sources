# VmxpDeletePrimaryPackId(void)

- ea: `0x140008f3c`
- end: `0x140008f83`
- name: `?VmxpDeletePrimaryPackId@@YAJXZ`
- size: `71`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x140031180`

## callees

- `0x140008f3c`
- `0x140008fd4`

## import_xrefs

- `ntoskrnl!RtlDeleteRegistryValue` at `0x140008f50`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x140008f50`

## string_xrefs

- `0x140008f49`: `\Registry\Machine\System\CurrentControlSet\Services\VolMgrX`

## pseudocode

```c
NTSTATUS VmxpDeletePrimaryPackId(void)
{
  NTSTATUS result; // eax
  const unsigned __int16 *v1; // rcx

  result = RtlDeleteRegistryValue(
             0,
             L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\VolMgrX",
             L"PrimaryPackId");
  if ( result >= 0 )
  {
    VmxpFlushRegistryKey(v1);
    *(GUID *)((char *)Global + 216) = GUID_NULL;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140008f3c  sub     rsp, 28h
0x140008f40  lea     r8, aPrimarypackid; "PrimaryPackId"
0x140008f47  xor     ecx, ecx; RelativeTo
0x140008f49  lea     rdx, Path; "\\Registry\\Machine\\System\\CurrentCon"...
0x140008f50  call    cs:__imp_RtlDeleteRegistryValue
0x140008f57  nop     dword ptr [rax+rax+00h]
0x140008f5c  test    eax, eax
0x140008f5e  js      short loc_140008F7D
0x140008f60  call    ?VmxpFlushRegistryKey@@YAXPEBG@Z; VmxpFlushRegistryKey(ushort const *)
0x140008f65  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x140008f6c  movups  xmm0, xmmword ptr cs:?GUID_NULL@@3U_GUID@@B.Data1; _GUID const GUID_NULL ...
0x140008f73  movdqu  xmmword ptr [rax+0D8h], xmm0
0x140008f7b  xor     eax, eax
0x140008f7d  add     rsp, 28h
0x140008f81  retn
```
