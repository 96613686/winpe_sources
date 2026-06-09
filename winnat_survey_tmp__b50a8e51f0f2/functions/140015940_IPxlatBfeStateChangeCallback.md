# IPxlatBfeStateChangeCallback

- ea: `0x140015940`
- end: `0x1400159ab`
- name: `IPxlatBfeStateChangeCallback`
- size: `107`
- prototype: `void __fastcall(void *context, FWPM_SERVICE_STATE newState)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task`

## callees

- `0x140015940`
- `0x140016368`
- `0x14002d008`

## import_xrefs

- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140015999`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140015999`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14001597f`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14001597f`

## pseudocode

```c
void __fastcall IPxlatBfeStateChangeCallback(void *context, FWPM_SERVICE_STATE newState)
{
  int v2; // eax

  if ( newState == FWPM_SERVICE_RUNNING )
  {
    LOBYTE(context) = 1;
    v2 = IPxlatConfigureCallouts(context);
    if ( v2 >= 0 )
    {
      ExEnterCriticalRegionAndAcquireResourceExclusive(&stru_1400268F0);
      IPxlatGlobalState = 1;
      ExReleaseResourceAndLeaveCriticalRegion(&stru_1400268F0);
    }
    else if ( (xmmword_1400262D0 & 2) != 0 )
    {
      WPP_SF_d(513, 10, WPP_24083f43286932c6336729c882afb6f6_Traceguids, (unsigned int)v2);
    }
  }
}

```

## disassembly

```asm
0x140015940  sub     rsp, 28h
0x140015944  cmp     edx, 3
0x140015947  jnz     short loc_1400159A5
0x140015949  mov     cl, 1
0x14001594b  call    IPxlatConfigureCallouts
0x140015950  test    eax, eax
0x140015952  jns     short loc_140015978
0x140015954  test    byte ptr cs:xmmword_1400262D0, 2
0x14001595b  jz      short loc_1400159A5
0x14001595d  mov     edx, 0Ah
0x140015962  lea     r8, WPP_24083f43286932c6336729c882afb6f6_Traceguids
0x140015969  mov     ecx, 201h
0x14001596e  mov     r9d, eax
0x140015971  call    WPP_SF_d
0x140015976  jmp     short loc_1400159A5
0x140015978  lea     rcx, stru_1400268F0; Resource
0x14001597f  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140015986  nop     dword ptr [rax+rax+00h]
0x14001598b  lea     rcx, stru_1400268F0; Resource
0x140015992  mov     cs:IPxlatGlobalState, 1
0x140015999  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x1400159a0  nop     dword ptr [rax+rax+00h]
0x1400159a5  add     rsp, 28h
0x1400159a9  retn
```
