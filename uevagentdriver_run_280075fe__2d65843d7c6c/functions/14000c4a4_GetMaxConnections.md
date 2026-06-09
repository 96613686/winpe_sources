# GetMaxConnections

- ea: `0x14000c4a4`
- end: `0x14000c554`
- name: `GetMaxConnections`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000c078`

## callees

- `0x140001118`
- `0x1400011b0`
- `0x14000b854`
- `0x14000c4a4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000c4df`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c4f7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c4df`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c4f7`

## string_xrefs

- `0x14000c4d3`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\UEV\Agent\Configuration`
- `0x14000c51b`: `UevFilter.GetMaxConnections: Max connections not configured, using default value\n`

## pseudocode

```c
__int64 GetMaxConnections()
{
  unsigned int v0; // ebx
  struct _UNICODE_STRING v2; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v4; // [rsp+50h] [rbp+8h] BYREF

  v4 = 0;
  DestinationString = 0;
  v2 = 0;
  DbgTrace(2, "UevFilter.GetMaxConnections: Entry\n");
  RtlInitUnicodeString(&DestinationString, L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\UEV\\Agent\\Configuration");
  RtlInitUnicodeString(&v2, L"MaxProcessEventConnections");
  if ( (int)ReadRegistryDword(&DestinationString, &v2, &v4) >= 0 )
  {
    v0 = v4;
  }
  else
  {
    DbgTrace(2, "UevFilter.GetMaxConnections: Max connections not configured, using default value\n");
    v0 = 2048;
  }
  DbgTraceFrmt(2, "UevFilter.GetMaxConnections: Exit, maxConnections = %d\n", v0);
  return v0;
}

```

## disassembly

```asm
0x14000c4a4  push    rbx
0x14000c4a6  sub     rsp, 40h
0x14000c4aa  xorps   xmm0, xmm0
0x14000c4ad  mov     [rsp+48h+arg_0], 0
0x14000c4b5  xorps   xmm1, xmm1
0x14000c4b8  lea     rdx, aUevfilterGetma_1; "UevFilter.GetMaxConnections: Entry\n"
0x14000c4bf  mov     ecx, 2
0x14000c4c4  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x14000c4c9  movups  xmmword ptr [rsp+48h+var_28.Length], xmm1
0x14000c4ce  call    DbgTrace
0x14000c4d3  lea     rdx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x14000c4da  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x14000c4df  call    cs:__imp_RtlInitUnicodeString
0x14000c4e6  nop     dword ptr [rax+rax+00h]
0x14000c4eb  lea     rdx, aMaxprocesseven; "MaxProcessEventConnections"
0x14000c4f2  lea     rcx, [rsp+48h+var_28]; DestinationString
0x14000c4f7  call    cs:__imp_RtlInitUnicodeString
0x14000c4fe  nop     dword ptr [rax+rax+00h]
0x14000c503  lea     r8, [rsp+48h+arg_0]
0x14000c508  lea     rdx, [rsp+48h+var_28]
0x14000c50d  lea     rcx, [rsp+48h+DestinationString]
0x14000c512  call    ReadRegistryDword
0x14000c517  test    eax, eax
0x14000c519  jns     short loc_14000C533
0x14000c51b  lea     rdx, aUevfilterGetma_0; "UevFilter.GetMaxConnections: Max connec"...
0x14000c522  mov     ecx, 2
0x14000c527  call    DbgTrace
0x14000c52c  mov     ebx, 800h
0x14000c531  jmp     short loc_14000C537
0x14000c533  mov     ebx, [rsp+48h+arg_0]
0x14000c537  mov     r8d, ebx
0x14000c53a  lea     rdx, aUevfilterGetma; "UevFilter.GetMaxConnections: Exit, maxC"...
0x14000c541  mov     ecx, 2
0x14000c546  call    DbgTraceFrmt
0x14000c54b  mov     eax, ebx
0x14000c54d  add     rsp, 40h
0x14000c551  pop     rbx
0x14000c552  retn
```
