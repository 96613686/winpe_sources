# VmxpWritePendingPrimaryPackId(_GUID *)

- ea: `0x140009670`
- end: `0x14000970f`
- name: `?VmxpWritePendingPrimaryPackId@@YAJPEAU_GUID@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x14002c3dc`
- `0x14002caf8`
- `0x14002e230`

## callees

- `0x140008fd4`
- `0x140009670`

## import_xrefs

- `ntoskrnl!RtlWriteRegistryValue` at `0x1400096c3`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1400096c3`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400096d6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400096d6`
- `ntoskrnl!RtlStringFromGUID` at `0x14000968a`
- `ntoskrnl!RtlStringFromGUID` at `0x14000968a`

## string_xrefs

- `0x1400096aa`: `\Registry\Machine\System\CurrentControlSet\Services\VolMgrX`

## pseudocode

```c
NTSTATUS __fastcall VmxpWritePendingPrimaryPackId(struct _GUID *a1)
{
  NTSTATUS result; // eax
  NTSTATUS v3; // edi
  const unsigned __int16 *v4; // rcx
  struct _UNICODE_STRING GuidString; // [rsp+30h] [rbp-18h] BYREF

  GuidString = 0;
  result = RtlStringFromGUID(a1, &GuidString);
  if ( result >= 0 )
  {
    v3 = RtlWriteRegistryValue(
           0,
           L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\VolMgrX",
           L"PendingPrimaryPackId",
           1u,
           GuidString.Buffer,
           GuidString.MaximumLength);
    RtlFreeUnicodeString(&GuidString);
    if ( v3 >= 0 )
    {
      VmxpFlushRegistryKey(v4);
      *(struct _GUID *)((char *)Global + 232) = *a1;
      return 0;
    }
    else
    {
      return v3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140009670  mov     [rsp+arg_0], rbx
0x140009675  push    rdi
0x140009676  sub     rsp, 40h
0x14000967a  xorps   xmm0, xmm0
0x14000967d  lea     rdx, [rsp+48h+GuidString]; GuidString
0x140009682  movups  xmmword ptr [rsp+48h+GuidString.Length], xmm0
0x140009687  mov     rbx, rcx
0x14000968a  call    cs:__imp_RtlStringFromGUID
0x140009691  nop     dword ptr [rax+rax+00h]
0x140009696  test    eax, eax
0x140009698  js      short loc_140009703
0x14000969a  movzx   eax, [rsp+48h+GuidString.MaximumLength]
0x14000969f  lea     r8, ValueName; "PendingPrimaryPackId"
0x1400096a6  mov     [rsp+48h+ValueLength], eax; ValueLength
0x1400096aa  lea     rdx, Path; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400096b1  mov     rax, [rsp+48h+GuidString.Buffer]
0x1400096b6  mov     r9d, 1; ValueType
0x1400096bc  xor     ecx, ecx; RelativeTo
0x1400096be  mov     [rsp+48h+ValueData], rax; ValueData
0x1400096c3  call    cs:__imp_RtlWriteRegistryValue
0x1400096ca  nop     dword ptr [rax+rax+00h]
0x1400096cf  lea     rcx, [rsp+48h+GuidString]; UnicodeString
0x1400096d4  mov     edi, eax
0x1400096d6  call    cs:__imp_RtlFreeUnicodeString
0x1400096dd  nop     dword ptr [rax+rax+00h]
0x1400096e2  test    edi, edi
0x1400096e4  jns     short loc_1400096EA
0x1400096e6  mov     eax, edi
0x1400096e8  jmp     short loc_140009703
0x1400096ea  call    ?VmxpFlushRegistryKey@@YAXPEBG@Z; VmxpFlushRegistryKey(ushort const *)
0x1400096ef  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x1400096f6  movups  xmm0, xmmword ptr [rbx]
0x1400096f9  movdqu  xmmword ptr [rax+0E8h], xmm0
0x140009701  xor     eax, eax
0x140009703  mov     rbx, [rsp+48h+arg_0]
0x140009708  add     rsp, 40h
0x14000970c  pop     rdi
0x14000970d  retn
```
