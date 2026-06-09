# VidDeviceAddCoreTeardown

- ea: `0x140083544`
- end: `0x1400835e8`
- name: `VidDeviceAddCoreTeardown`
- size: `164`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140023b00`
- `0x140082cd0`
- `0x1400833b8`

## callees

- `0x140083544`
- `0x1400986c4`
- `0x14009baac`
- `0x14009df58`
- `0x1400c02ec`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x140083572`
- `ntoskrnl!RtlRbRemoveNode` at `0x140083572`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083586`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083586`

## pseudocode

```c
__int64 VidDeviceAddCoreTeardown()
{
  char *v0; // rdi
  unsigned __int64 i; // rax
  void *v2; // rbx

  v0 = (char *)VidDeviceExtension;
  VsmmMemReserveStatisticsDataTeardown();
  for ( i = *((_QWORD *)v0 + 201); ; i = *((_QWORD *)v0 + 201) )
  {
    if ( (i & 1) != 0 )
    {
      if ( i == 1 )
        break;
      v2 = (void *)(i ^ ((unsigned __int64)(v0 + 1600) | 1));
    }
    else
    {
      v2 = (void *)i;
    }
    if ( !v2 )
      break;
    RtlRbRemoveNode(v0 + 1600, v2);
    ExFreePoolWithTag(v2, 0x6D4D6456u);
  }
  VsmmNumaTopologyTeardown(v0);
  VidSynicPortUninitialize(v0 + 656);
  return VidStatisticsDataTeardown((PFAST_MUTEX)(v0 + 304));
}

```

## disassembly

```asm
0x140083544  mov     [rsp+arg_0], rbx
0x140083549  mov     [rsp+arg_8], rsi
0x14008354e  push    rdi
0x14008354f  sub     rsp, 20h
0x140083553  mov     rdi, cs:VidDeviceExtension
0x14008355a  call    VsmmMemReserveStatisticsDataTeardown
0x14008355f  lea     rsi, [rdi+640h]
0x140083566  mov     rax, [rsi+8]
0x14008356a  jmp     short loc_140083599
0x14008356c  mov     rdx, rbx
0x14008356f  mov     rcx, rsi
0x140083572  call    cs:__imp_RtlRbRemoveNode
0x140083579  nop     dword ptr [rax+rax+00h]
0x14008357e  mov     edx, 6D4D6456h; Tag
0x140083583  mov     rcx, rbx; P
0x140083586  call    cs:__imp_ExFreePoolWithTag
0x14008358d  nop     dword ptr [rax+rax+00h]
0x140083592  mov     rax, [rdi+648h]
0x140083599  test    al, 1
0x14008359b  jz      short loc_1400835AF
0x14008359d  cmp     rax, 1
0x1400835a1  jz      short loc_1400835B7
0x1400835a3  mov     rbx, rsi
0x1400835a6  or      rbx, 1
0x1400835aa  xor     rbx, rax
0x1400835ad  jmp     short loc_1400835B2
0x1400835af  mov     rbx, rax
0x1400835b2  test    rbx, rbx
0x1400835b5  jnz     short loc_14008356C
0x1400835b7  mov     rcx, rdi
0x1400835ba  call    VsmmNumaTopologyTeardown
0x1400835bf  lea     rcx, [rdi+290h]
0x1400835c6  call    VidSynicPortUninitialize
0x1400835cb  lea     rcx, [rdi+130h]; FastMutex
0x1400835d2  call    VidStatisticsDataTeardown
0x1400835d7  mov     rbx, [rsp+28h+arg_0]
0x1400835dc  mov     rsi, [rsp+28h+arg_8]
0x1400835e1  add     rsp, 20h
0x1400835e5  pop     rdi
0x1400835e6  retn
```
