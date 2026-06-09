# VmxpDeletePendingPrimaryPackId(void)

- ea: `0x140008eec`
- end: `0x140008f33`
- name: `?VmxpDeletePendingPrimaryPackId@@YAJXZ`
- size: `71`
- prototype: `__int64(void)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x14002c3dc`
- `0x14002caf8`
- `0x14002e230`
- `0x14002f1e4`
- `0x140031180`
- `0x140038468`
- `0x14005dac0`
- `0x14005dcc4`

## callees

- `0x140008eec`
- `0x140008fd4`

## import_xrefs

- `ntoskrnl!RtlDeleteRegistryValue` at `0x140008f00`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x140008f00`

## string_xrefs

- `0x140008ef9`: `\Registry\Machine\System\CurrentControlSet\Services\VolMgrX`

## pseudocode

```c
NTSTATUS VmxpDeletePendingPrimaryPackId(void)
{
  NTSTATUS result; // eax
  const unsigned __int16 *v1; // rcx

  result = RtlDeleteRegistryValue(
             0,
             L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\VolMgrX",
             L"PendingPrimaryPackId");
  if ( result >= 0 )
  {
    VmxpFlushRegistryKey(v1);
    *(GUID *)((char *)Global + 232) = GUID_NULL;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140008eec  sub     rsp, 28h
0x140008ef0  lea     r8, ValueName; "PendingPrimaryPackId"
0x140008ef7  xor     ecx, ecx; RelativeTo
0x140008ef9  lea     rdx, Path; "\\Registry\\Machine\\System\\CurrentCon"...
0x140008f00  call    cs:__imp_RtlDeleteRegistryValue
0x140008f07  nop     dword ptr [rax+rax+00h]
0x140008f0c  test    eax, eax
0x140008f0e  js      short loc_140008F2D
0x140008f10  call    ?VmxpFlushRegistryKey@@YAXPEBG@Z; VmxpFlushRegistryKey(ushort const *)
0x140008f15  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x140008f1c  movups  xmm0, xmmword ptr cs:?GUID_NULL@@3U_GUID@@B.Data1; _GUID const GUID_NULL ...
0x140008f23  movdqu  xmmword ptr [rax+0E8h], xmm0
0x140008f2b  xor     eax, eax
0x140008f2d  add     rsp, 28h
0x140008f31  retn
```
