# DllUnload

- ea: `0x1400049a0`
- end: `0x1400049f8`
- name: `DllUnload`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1400049a0`
- `0x14000b178`

## import_xrefs

- `ntoskrnl!MmFreeMappingAddress` at `0x1400049d4`
- `ntoskrnl!MmFreeMappingAddress` at `0x1400049d4`
- `NETIO!NetioDeregisterTriageDumpDataCallback` at `0x1400049ab`
- `NETIO!NetioDeregisterTriageDumpDataCallback` at `0x1400049ab`
- `NDIS!NdisDeregisterTdiCallBack` at `0x1400049b7`
- `NDIS!NdisDeregisterTdiCallBack` at `0x1400049b7`

## pseudocode

```c
__int64 DllUnload()
{
  NetioDeregisterTriageDumpDataCallback(qword_1400080C0);
  NdisDeregisterTdiCallBack();
  if ( TdiMappingAddress )
  {
    MmFreeMappingAddress(TdiMappingAddress, 0x6D494454u);
    TdiMappingAddress = 0;
  }
  wil_UninitializeFeatureStaging();
  return 0;
}

```

## disassembly

```asm
0x1400049a0  sub     rsp, 28h
0x1400049a4  lea     rcx, qword_1400080C0
0x1400049ab  call    cs:__imp_NetioDeregisterTriageDumpDataCallback
0x1400049b2  nop     dword ptr [rax+rax+00h]
0x1400049b7  call    cs:__imp_NdisDeregisterTdiCallBack
0x1400049be  nop     dword ptr [rax+rax+00h]
0x1400049c3  mov     rcx, cs:TdiMappingAddress; BaseAddress
0x1400049ca  test    rcx, rcx
0x1400049cd  jz      short loc_1400049EB
0x1400049cf  mov     edx, 6D494454h; PoolTag
0x1400049d4  call    cs:__imp_MmFreeMappingAddress
0x1400049db  nop     dword ptr [rax+rax+00h]
0x1400049e0  mov     cs:TdiMappingAddress, 0
0x1400049eb  call    wil_UninitializeFeatureStaging
0x1400049f0  xor     eax, eax
0x1400049f2  add     rsp, 28h
0x1400049f6  retn
```
