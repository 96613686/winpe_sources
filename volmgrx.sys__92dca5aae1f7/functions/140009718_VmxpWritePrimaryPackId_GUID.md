# VmxpWritePrimaryPackId(_GUID *)

- ea: `0x140009718`
- end: `0x1400097b7`
- name: `?VmxpWritePrimaryPackId@@YAJPEAU_GUID@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x14002c3dc`
- `0x14002caf8`
- `0x14002e230`
- `0x14002f1e4`
- `0x140038468`
- `0x14005dac0`
- `0x14005dcc4`

## callees

- `0x140008fd4`
- `0x140009718`

## import_xrefs

- `ntoskrnl!RtlWriteRegistryValue` at `0x14000976b`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14000976b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000977e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000977e`
- `ntoskrnl!RtlStringFromGUID` at `0x140009732`
- `ntoskrnl!RtlStringFromGUID` at `0x140009732`

## string_xrefs

- `0x140009752`: `\Registry\Machine\System\CurrentControlSet\Services\VolMgrX`

## pseudocode

```c
NTSTATUS __fastcall VmxpWritePrimaryPackId(struct _GUID *a1)
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
           L"PrimaryPackId",
           1u,
           GuidString.Buffer,
           GuidString.MaximumLength);
    RtlFreeUnicodeString(&GuidString);
    if ( v3 >= 0 )
    {
      VmxpFlushRegistryKey(v4);
      *(struct _GUID *)((char *)Global + 216) = *a1;
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
0x140009718  mov     [rsp+arg_0], rbx
0x14000971d  push    rdi
0x14000971e  sub     rsp, 40h
0x140009722  xorps   xmm0, xmm0
0x140009725  lea     rdx, [rsp+48h+GuidString]; GuidString
0x14000972a  movups  xmmword ptr [rsp+48h+GuidString.Length], xmm0
0x14000972f  mov     rbx, rcx
0x140009732  call    cs:__imp_RtlStringFromGUID
0x140009739  nop     dword ptr [rax+rax+00h]
0x14000973e  test    eax, eax
0x140009740  js      short loc_1400097AB
0x140009742  movzx   eax, [rsp+48h+GuidString.MaximumLength]
0x140009747  lea     r8, aPrimarypackid; "PrimaryPackId"
0x14000974e  mov     [rsp+48h+ValueLength], eax; ValueLength
0x140009752  lea     rdx, Path; "\\Registry\\Machine\\System\\CurrentCon"...
0x140009759  mov     rax, [rsp+48h+GuidString.Buffer]
0x14000975e  mov     r9d, 1; ValueType
0x140009764  xor     ecx, ecx; RelativeTo
0x140009766  mov     [rsp+48h+ValueData], rax; ValueData
0x14000976b  call    cs:__imp_RtlWriteRegistryValue
0x140009772  nop     dword ptr [rax+rax+00h]
0x140009777  lea     rcx, [rsp+48h+GuidString]; UnicodeString
0x14000977c  mov     edi, eax
0x14000977e  call    cs:__imp_RtlFreeUnicodeString
0x140009785  nop     dword ptr [rax+rax+00h]
0x14000978a  test    edi, edi
0x14000978c  jns     short loc_140009792
0x14000978e  mov     eax, edi
0x140009790  jmp     short loc_1400097AB
0x140009792  call    ?VmxpFlushRegistryKey@@YAXPEBG@Z; VmxpFlushRegistryKey(ushort const *)
0x140009797  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14000979e  movups  xmm0, xmmword ptr [rbx]
0x1400097a1  movdqu  xmmword ptr [rax+0D8h], xmm0
0x1400097a9  xor     eax, eax
0x1400097ab  mov     rbx, [rsp+48h+arg_0]
0x1400097b0  add     rsp, 40h
0x1400097b4  pop     rdi
0x1400097b5  retn
```
