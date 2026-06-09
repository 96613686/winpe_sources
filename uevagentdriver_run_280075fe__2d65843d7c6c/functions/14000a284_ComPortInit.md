# ComPortInit

- ea: `0x14000a284`
- end: `0x14000a3bd`
- name: `ComPortInit`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000c614`

## callees

- `0x140001118`
- `0x1400011b0`
- `0x140001298`
- `0x14000a284`
- `0x14000b854`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x14000a2c3`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000a2c3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a2f4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a30c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a2f4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a30c`

## string_xrefs

- `0x14000a2a1`: `UevFilter.ComPortInit: Entry\n`
- `0x14000a2d7`: `UevFilter.ComPortInit: Failed resourse initialization, status = 0x%X\n`
- `0x14000a2e8`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\UEV\Agent\Configuration`
- `0x14000a330`: `UevFilter.ComPortInit: Send message timeout not configured, using default value\n`
- `0x14000a352`: `UevFilter.ComPortInit: Setting send message timeout to 0x%X ms\n`
- `0x14000a382`: `UevFilter.ComPortInit: Setting send message to not timeout\n`
- `0x14000a39c`: `UevFilter.ComPortInit: Exit, retStatus = 0x%X\n`

## pseudocode

```c
__int64 ComPortInit()
{
  NTSTATUS v0; // edi
  int v1; // ebx
  struct _UNICODE_STRING v3; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  int v5; // [rsp+50h] [rbp+8h] BYREF

  v5 = 0;
  DestinationString = 0;
  v3 = 0;
  DbgTrace(2, "UevFilter.ComPortInit: Entry\n");
  v0 = ExInitializeResourceLite(&comPortResource);
  if ( v0 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\UEV\\Agent\\Configuration");
    RtlInitUnicodeString(&v3, L"FilterSendMsgTimeout");
    if ( (int)ReadRegistryDword(&DestinationString, &v3, &v5) >= 0 )
    {
      v1 = v5;
    }
    else
    {
      DbgTrace(2, "UevFilter.ComPortInit: Send message timeout not configured, using default value\n");
      v1 = 10000;
    }
    if ( v1 )
    {
      DbgTraceFrmt(2, "UevFilter.ComPortInit: Setting send message timeout to 0x%X ms\n", v1);
      sendMsgTimeout = -10000LL * (unsigned int)(v1 + 500);
      pSendMsgTimeout = (PLARGE_INTEGER)&sendMsgTimeout;
    }
    else
    {
      DbgTrace(2, "UevFilter.ComPortInit: Setting send message to not timeout\n");
      pSendMsgTimeout = 0;
    }
  }
  else
  {
    DbgTraceFrmtErr("UevFilter.ComPortInit: Failed resourse initialization, status = 0x%X\n");
  }
  DbgTraceFrmt(2, "UevFilter.ComPortInit: Exit, retStatus = 0x%X\n", v0);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14000a284  mov     rax, rsp
0x14000a287  mov     [rax+10h], rbx
0x14000a28b  mov     [rax+18h], rsi
0x14000a28f  push    rdi
0x14000a290  sub     rsp, 40h
0x14000a294  xorps   xmm0, xmm0
0x14000a297  mov     dword ptr [rax+8], 0
0x14000a29e  xorps   xmm1, xmm1
0x14000a2a1  lea     rdx, aUevfilterCompo_12; "UevFilter.ComPortInit: Entry\n"
0x14000a2a8  mov     esi, 2
0x14000a2ad  mov     ecx, esi
0x14000a2af  movups  xmmword ptr [rax-18h], xmm0
0x14000a2b3  movups  xmmword ptr [rax-28h], xmm1
0x14000a2b7  call    DbgTrace
0x14000a2bc  lea     rcx, comPortResource; Resource
0x14000a2c3  call    cs:__imp_ExInitializeResourceLite
0x14000a2ca  nop     dword ptr [rax+rax+00h]
0x14000a2cf  mov     edi, eax
0x14000a2d1  test    eax, eax
0x14000a2d3  jns     short loc_14000A2E8
0x14000a2d5  mov     edx, eax
0x14000a2d7  lea     rcx, aUevfilterCompo_11; "UevFilter.ComPortInit: Failed resourse "...
0x14000a2de  call    DbgTraceFrmtErr
0x14000a2e3  jmp     loc_14000A399
0x14000a2e8  lea     rdx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x14000a2ef  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x14000a2f4  call    cs:__imp_RtlInitUnicodeString
0x14000a2fb  nop     dword ptr [rax+rax+00h]
0x14000a300  lea     rdx, aFiltersendmsgt; "FilterSendMsgTimeout"
0x14000a307  lea     rcx, [rsp+48h+var_28]; DestinationString
0x14000a30c  call    cs:__imp_RtlInitUnicodeString
0x14000a313  nop     dword ptr [rax+rax+00h]
0x14000a318  lea     r8, [rsp+48h+arg_0]
0x14000a31d  lea     rdx, [rsp+48h+var_28]
0x14000a322  lea     rcx, [rsp+48h+DestinationString]
0x14000a327  call    ReadRegistryDword
0x14000a32c  test    eax, eax
0x14000a32e  jns     short loc_14000A345
0x14000a330  lea     rdx, aUevfilterCompo_8; "UevFilter.ComPortInit: Send message tim"...
0x14000a337  mov     ecx, esi
0x14000a339  call    DbgTrace
0x14000a33e  mov     ebx, 2710h
0x14000a343  jmp     short loc_14000A349
0x14000a345  mov     ebx, [rsp+48h+arg_0]
0x14000a349  mov     ecx, esi
0x14000a34b  test    ebx, ebx
0x14000a34d  jz      short loc_14000A382
0x14000a34f  mov     r8d, ebx
0x14000a352  lea     rdx, aUevfilterCompo_9; "UevFilter.ComPortInit: Setting send mes"...
0x14000a359  call    DbgTraceFrmt
0x14000a35e  lea     ecx, [rbx+1F4h]
0x14000a364  imul    rax, rcx, 0FFFFFFFFFFFFD8F0h
0x14000a36b  mov     cs:sendMsgTimeout, rax
0x14000a372  lea     rax, sendMsgTimeout
0x14000a379  mov     cs:pSendMsgTimeout, rax
0x14000a380  jmp     short loc_14000A399
0x14000a382  lea     rdx, aUevfilterCompo_13; "UevFilter.ComPortInit: Setting send mes"...
0x14000a389  call    DbgTrace
0x14000a38e  mov     cs:pSendMsgTimeout, 0
0x14000a399  mov     r8d, edi
0x14000a39c  lea     rdx, aUevfilterCompo_16; "UevFilter.ComPortInit: Exit, retStatus "...
0x14000a3a3  mov     ecx, esi
0x14000a3a5  call    DbgTraceFrmt
0x14000a3aa  mov     rbx, [rsp+48h+arg_8]
0x14000a3af  mov     eax, edi
0x14000a3b1  mov     rsi, [rsp+48h+arg_10]
0x14000a3b6  add     rsp, 40h
0x14000a3ba  pop     rdi
0x14000a3bb  retn
```
