# IPxlatBfeStateChangeCallback

- ea: `0x1400162c0`
- end: `0x14001632b`
- name: `IPxlatBfeStateChangeCallback`
- size: `107`
- prototype: `void __stdcall(void *context, FWPM_SERVICE_STATE newState)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task`

## callees

- `0x1400162c0`
- `0x140017034`
- `0x14002e008`

## import_xrefs

- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140016319`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140016319`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400162ff`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400162ff`

## pseudocode

```c
void __fastcall IPxlatBfeStateChangeCallback(void *context, FWPM_SERVICE_STATE newState)
{
  int v2; // eax

  if ( newState == FWPM_SERVICE_RUNNING )
  {
    v2 = IPxlatConfigureCallouts(1);
    if ( v2 >= 0 )
    {
      ExEnterCriticalRegionAndAcquireResourceExclusive(&stru_1400278F0);
      IPxlatGlobalState = 1;
      ExReleaseResourceAndLeaveCriticalRegion(&stru_1400278F0);
    }
    else if ( (xmmword_1400272D0 & 2) != 0 )
    {
      WPP_SF_d(513, 10, WPP_00475dad78ff34078f24129d9bdcf001_Traceguids, (unsigned int)v2);
    }
  }
}

```

## disassembly

```asm
0x1400162c0  sub     rsp, 28h
0x1400162c4  cmp     edx, 3
0x1400162c7  jnz     short loc_140016325
0x1400162c9  mov     cl, 1
0x1400162cb  call    IPxlatConfigureCallouts
0x1400162d0  test    eax, eax
0x1400162d2  jns     short loc_1400162F8
0x1400162d4  test    byte ptr cs:xmmword_1400272D0, 2
0x1400162db  jz      short loc_140016325
0x1400162dd  mov     edx, 0Ah
0x1400162e2  lea     r8, WPP_00475dad78ff34078f24129d9bdcf001_Traceguids
0x1400162e9  mov     ecx, 201h
0x1400162ee  mov     r9d, eax
0x1400162f1  call    WPP_SF_d
0x1400162f6  jmp     short loc_140016325
0x1400162f8  lea     rcx, stru_1400278F0; Resource
0x1400162ff  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140016306  nop     dword ptr [rax+rax+00h]
0x14001630b  lea     rcx, stru_1400278F0; Resource
0x140016312  mov     cs:IPxlatGlobalState, 1
0x140016319  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140016320  nop     dword ptr [rax+rax+00h]
0x140016325  add     rsp, 28h
0x140016329  retn
```
