# SlbNatFindAndDeleteExternalAddress

- ea: `0x140032314`
- end: `0x1400323e0`
- name: `SlbNatFindAndDeleteExternalAddress`
- size: `204`
- prototype: `__int64 __fastcall(wchar_t *Str2)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002f880`

## callees

- `0x14000d7f8`
- `0x1400310f8`
- `0x140032314`
- `0x1400344f8`
- `0x140034638`

## import_xrefs

- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140032384`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140032384`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140032324`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140032324`

## string_xrefs

- `0x1400323aa`: `Delete external address`

## pseudocode

```c
__int64 __fastcall SlbNatFindAndDeleteExternalAddress(wchar_t *Str2)
{
  __int64 Instance; // rax
  int v3; // ebx
  _QWORD *ExternalAddress; // rax
  __int64 v5; // rdx
  _QWORD *v6; // r8
  int v7; // edx
  int v8; // r8d

  ExEnterCriticalRegionAndAcquireResourceExclusive(&Resource);
  Instance = SlbNatFindInstance(Str2);
  if ( Instance && (ExternalAddress = (_QWORD *)SlbNatFindExternalAddress(Instance, *((unsigned int *)Str2 + 20))) != 0 )
  {
    v5 = *ExternalAddress;
    if ( *(_QWORD **)(*ExternalAddress + 8LL) != ExternalAddress
      || (v6 = (_QWORD *)ExternalAddress[1], (_QWORD *)*v6 != ExternalAddress) )
    {
      __fastfail(3u);
    }
    *v6 = v5;
    v3 = 0;
    *(_QWORD *)(v5 + 8) = v6;
    SlbNatDeleteExternalAddress(ExternalAddress);
  }
  else
  {
    v3 = -1073741275;
  }
  ExReleaseResourceAndLeaveCriticalRegion(&Resource);
  if ( v3 < 0 && dword_140026104 == 1 && (byte_140026BED & 0x10) != 0 )
    McTemplateK0qzqq_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
      v7,
      v8,
      3006,
      (__int64)L"Delete external address",
      0,
      v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140032314  push    rbx
0x140032316  sub     rsp, 40h
0x14003231a  mov     rbx, rcx
0x14003231d  lea     rcx, Resource; Resource
0x140032324  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x14003232b  nop     dword ptr [rax+rax+00h]
0x140032330  mov     rcx, rbx; Str2
0x140032333  call    SlbNatFindInstance
0x140032338  mov     r9, rax
0x14003233b  test    rax, rax
0x14003233e  jnz     short loc_140032347
0x140032340  mov     ebx, 0C0000225h
0x140032345  jmp     short loc_14003237D
0x140032347  mov     edx, [rbx+50h]
0x14003234a  mov     rcx, r9
0x14003234d  call    SlbNatFindExternalAddress
0x140032352  test    rax, rax
0x140032355  jz      short loc_140032340
0x140032357  mov     rdx, [rax]
0x14003235a  cmp     [rdx+8], rax
0x14003235e  jnz     short loc_1400323D9
0x140032360  mov     r8, [rax+8]
0x140032364  cmp     [r8], rax
0x140032367  jnz     short loc_1400323D9
0x140032369  mov     [r8], rdx
0x14003236c  xor     ebx, ebx
0x14003236e  mov     [rdx+8], r8
0x140032372  mov     rcx, rax; P
0x140032375  mov     rdx, r9
0x140032378  call    SlbNatDeleteExternalAddress
0x14003237d  lea     rcx, Resource; Resource
0x140032384  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14003238b  nop     dword ptr [rax+rax+00h]
0x140032390  test    ebx, ebx
0x140032392  jns     short loc_1400323D0
0x140032394  cmp     cs:dword_140026104, 1
0x14003239b  jnz     short loc_1400323D0
0x14003239d  test    cs:byte_140026BED, 10h
0x1400323a4  jz      short loc_1400323D0
0x1400323a6  mov     [rsp+48h+var_18], ebx
0x1400323aa  lea     rax, aDeleteExternal; "Delete external address"
0x1400323b1  mov     [rsp+48h+var_20], 0
0x1400323b9  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x1400323c0  mov     r9d, 0BBEh
0x1400323c6  mov     [rsp+48h+var_28], rax
0x1400323cb  call    McTemplateK0qzqq_EtwWriteTransfer
0x1400323d0  mov     eax, ebx
0x1400323d2  add     rsp, 40h
0x1400323d6  pop     rbx
0x1400323d7  retn
0x1400323d9  mov     ecx, 3
0x1400323de  int     29h; Win8: RtlFailFast(ecx)
```
