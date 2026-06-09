# DllInitialize

- ea: `0x140004880`
- end: `0x140004990`
- name: `DllInitialize`
- size: `272`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004880`
- `0x14000515c`
- `0x14000b178`
- `0x14000d044`
- `0x14000d078`

## import_xrefs

- `ntoskrnl!KeQueryTimeIncrement` at `0x1400048ee`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1400048ee`
- `ntoskrnl!MmAllocateMappingAddress` at `0x140004945`
- `ntoskrnl!MmAllocateMappingAddress` at `0x140004945`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400048a3`
- `ntoskrnl!KeInitializeSpinLock` at `0x140004907`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000492f`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400048a3`
- `ntoskrnl!KeInitializeSpinLock` at `0x140004907`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000492f`
- `NDIS!NdisRegisterTdiCallBack` at `0x140004977`
- `NDIS!NdisRegisterTdiCallBack` at `0x140004977`

## pseudocode

```c
__int64 DllInitialize()
{
  _security_init_cookie();
  if ( (int)wil_InitializeFeatureStaging() < 0 )
    return 3221225474LL;
  KeInitializeSpinLock(&TDIListLock);
  qword_140008378 = (__int64)&PnpHandlerClientList;
  PnpHandlerClientList = (__int64)&PnpHandlerClientList;
  qword_140008358 = (__int64)&PnpHandlerProviderList;
  PnpHandlerProviderList = (__int64)&PnpHandlerProviderList;
  qword_140008368 = (__int64)&PnpHandlerRequestList;
  PnpHandlerRequestList = (__int64)&PnpHandlerRequestList;
  CTEpTimeIncrement = KeQueryTimeIncrement();
  KeInitializeSpinLock(&CTEBlockSpinLock);
  qword_1400083A8 = (__int64)&CTEBlockListHead;
  CTEBlockListHead = (__int64)&CTEBlockListHead;
  KeInitializeSpinLock(&TdiMappingAddressLock);
  TdiMappingAddress = MmAllocateMappingAddress(0x1000u, 0x6D494454u);
  if ( TdiMappingAddress )
  {
    NdisRegisterTdiCallBack(TdiRegisterDeviceObject, TdiPnPHandler);
    TdiInitialize9FTriageBlock();
    return 0;
  }
  else
  {
    wil_UninitializeFeatureStaging();
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x140004880  sub     rsp, 28h
0x140004884  call    __security_init_cookie
0x140004889  call    wil_InitializeFeatureStaging
0x14000488e  test    eax, eax
0x140004890  jns     short loc_14000489C
0x140004892  mov     eax, 0C0000002h
0x140004897  jmp     loc_14000498A
0x14000489c  lea     rcx, TDIListLock; SpinLock
0x1400048a3  call    cs:__imp_KeInitializeSpinLock
0x1400048aa  nop     dword ptr [rax+rax+00h]
0x1400048af  lea     rax, PnpHandlerClientList
0x1400048b6  mov     cs:qword_140008378, rax
0x1400048bd  mov     cs:PnpHandlerClientList, rax
0x1400048c4  lea     rax, PnpHandlerProviderList
0x1400048cb  mov     cs:qword_140008358, rax
0x1400048d2  mov     cs:PnpHandlerProviderList, rax
0x1400048d9  lea     rax, PnpHandlerRequestList
0x1400048e0  mov     cs:qword_140008368, rax
0x1400048e7  mov     cs:PnpHandlerRequestList, rax
0x1400048ee  call    cs:__imp_KeQueryTimeIncrement
0x1400048f5  nop     dword ptr [rax+rax+00h]
0x1400048fa  lea     rcx, CTEBlockSpinLock; SpinLock
0x140004901  mov     cs:CTEpTimeIncrement, eax
0x140004907  call    cs:__imp_KeInitializeSpinLock
0x14000490e  nop     dword ptr [rax+rax+00h]
0x140004913  lea     rax, CTEBlockListHead
0x14000491a  lea     rcx, TdiMappingAddressLock; SpinLock
0x140004921  mov     cs:qword_1400083A8, rax
0x140004928  mov     cs:CTEBlockListHead, rax
0x14000492f  call    cs:__imp_KeInitializeSpinLock
0x140004936  nop     dword ptr [rax+rax+00h]
0x14000493b  mov     edx, 6D494454h; PoolTag
0x140004940  mov     ecx, 1000h; NumberOfBytes
0x140004945  call    cs:__imp_MmAllocateMappingAddress
0x14000494c  nop     dword ptr [rax+rax+00h]
0x140004951  mov     cs:TdiMappingAddress, rax
0x140004958  test    rax, rax
0x14000495b  jnz     short loc_140004969
0x14000495d  call    wil_UninitializeFeatureStaging
0x140004962  mov     eax, 0C000009Ah
0x140004967  jmp     short loc_14000498A
0x140004969  lea     rdx, TdiPnPHandler; PnPHandler
0x140004970  lea     rcx, TdiRegisterDeviceObject; RegisterCallback
0x140004977  call    cs:__imp_NdisRegisterTdiCallBack
0x14000497e  nop     dword ptr [rax+rax+00h]
0x140004983  call    TdiInitialize9FTriageBlock
0x140004988  xor     eax, eax
0x14000498a  add     rsp, 28h
0x14000498e  retn
```
