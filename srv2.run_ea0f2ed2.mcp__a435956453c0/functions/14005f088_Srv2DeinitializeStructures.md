# Srv2DeinitializeStructures

- ea: `0x14005f088`
- end: `0x14005f171`
- name: `Srv2DeinitializeStructures`
- size: `233`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14005f440`
- `0x14005f538`

## callees

- `0x14002019c`
- `0x14005d648`
- `0x14005efec`
- `0x14005f088`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14005f0e7`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005f141`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005f0e7`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005f141`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14005f154`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14005f154`

## pseudocode

```c
__int64 Srv2DeinitializeStructures()
{
  __int64 i; // rbx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, &WPP_ce36e4dedee63ec6b47e75c75daf32d1_Traceguids);
  }
  if ( Srv2InstancesAreInitialized )
  {
    Srv2InstancesAreInitialized = 0;
    for ( i = 0; i != 6; ++i )
      ExDeleteResourceLite((PERESOURCE)((char *)&Srv2Instances + 112 * i));
  }
  Srv2ProviderList = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, &WPP_dab54e57c74a31246f7cfec710fd6d2e_Traceguids);
  }
  Srv2DeinitializeCryptoSupport();
  ExDeleteResourceLite((PERESOURCE)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels);
  ExDeleteLookasideListEx(&Srv2PagedBlockTypeBuffer8K);
  return Srv2DeinitializeWorkItemLookasides();
}

```

## disassembly

```asm
0x14005f088  mov     [rsp+arg_0], rbx
0x14005f08d  push    rsi
0x14005f08e  sub     rsp, 20h
0x14005f092  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005f099  lea     rsi, WPP_GLOBAL_Control
0x14005f0a0  cmp     rcx, rsi
0x14005f0a3  jz      short loc_14005F0C7
0x14005f0a5  mov     eax, [rcx+2Ch]
0x14005f0a8  test    al, 1
0x14005f0aa  jz      short loc_14005F0C7
0x14005f0ac  cmp     byte ptr [rcx+29h], 2
0x14005f0b0  jb      short loc_14005F0C7
0x14005f0b2  mov     rcx, [rcx+18h]
0x14005f0b6  lea     r8, WPP_ce36e4dedee63ec6b47e75c75daf32d1_Traceguids
0x14005f0bd  mov     edx, 1Bh
0x14005f0c2  call    WPP_SF_
0x14005f0c7  cmp     cs:Srv2InstancesAreInitialized, 0
0x14005f0ce  jz      short loc_14005F0FC
0x14005f0d0  mov     cs:Srv2InstancesAreInitialized, 0
0x14005f0d7  xor     ebx, ebx
0x14005f0d9  lea     rax, Srv2Instances
0x14005f0e0  imul    rcx, rbx, 70h ; 'p'
0x14005f0e4  add     rcx, rax; Resource
0x14005f0e7  call    cs:__imp_ExDeleteResourceLite
0x14005f0ee  nop     dword ptr [rax+rax+00h]
0x14005f0f3  inc     rbx
0x14005f0f6  cmp     rbx, 6
0x14005f0fa  jnz     short loc_14005F0D9
0x14005f0fc  mov     cs:Srv2ProviderList, 0
0x14005f107  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005f10e  cmp     rcx, rsi
0x14005f111  jz      short loc_14005F135
0x14005f113  mov     eax, [rcx+2Ch]
0x14005f116  test    al, al
0x14005f118  jns     short loc_14005F135
0x14005f11a  cmp     byte ptr [rcx+29h], 2
0x14005f11e  jb      short loc_14005F135
0x14005f120  mov     rcx, [rcx+18h]
0x14005f124  lea     r8, WPP_dab54e57c74a31246f7cfec710fd6d2e_Traceguids
0x14005f12b  mov     edx, 0Ch
0x14005f130  call    WPP_SF_
0x14005f135  call    Srv2DeinitializeCryptoSupport
0x14005f13a  lea     rcx, WPP_MAIN_CB.Queue+10h; Resource
0x14005f141  call    cs:__imp_ExDeleteResourceLite
0x14005f148  nop     dword ptr [rax+rax+00h]
0x14005f14d  lea     rcx, Srv2PagedBlockTypeBuffer8K; Lookaside
0x14005f154  call    cs:__imp_ExDeleteLookasideListEx
0x14005f15b  nop     dword ptr [rax+rax+00h]
0x14005f160  call    Srv2DeinitializeWorkItemLookasides
0x14005f165  mov     rbx, [rsp+28h+arg_0]
0x14005f16a  add     rsp, 20h
0x14005f16e  pop     rsi
0x14005f16f  retn
```
