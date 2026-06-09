# WinNatInitializeWFP

- ea: `0x1400134dc`
- end: `0x140013601`
- name: `WinNatInitializeWFP`
- size: `293`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140036078`

## callees

- `0x140012a40`
- `0x140012db8`
- `0x1400130f4`
- `0x1400134dc`
- `0x14001f320`

## import_xrefs

- `ntoskrnl!ExInitializePushLock` at `0x140013500`
- `ntoskrnl!ExInitializePushLock` at `0x140013500`
- `NDIS!NdisAllocateNetBufferListPool` at `0x1400135ab`
- `NDIS!NdisAllocateNetBufferListPool` at `0x1400135ab`
- `NDIS!NdisAllocateGenericObject` at `0x140013565`
- `NDIS!NdisAllocateGenericObject` at `0x140013565`
- `fwpkclnt!FwpsInjectionHandleCreate0` at `0x14001351b`
- `fwpkclnt!FwpsInjectionHandleCreate0` at `0x140013540`
- `fwpkclnt!FwpsInjectionHandleCreate0` at `0x14001351b`
- `fwpkclnt!FwpsInjectionHandleCreate0` at `0x140013540`

## pseudocode

```c
__int64 WinNatInitializeWFP()
{
  NTSTATUS v0; // ebx
  struct _NDIS_GENERIC_OBJECT *GenericObject; // rax
  _NET_BUFFER_LIST_POOL_PARAMETERS Parameters; // [rsp+20h] [rbp-28h] BYREF

  Parameters = 0;
  ExInitializePushLock(&PushLock);
  v0 = FwpsInjectionHandleCreate0(2u, 4u, &WinNatWFPInjectionHandleIpv4);
  if ( v0 < 0 )
    goto LABEL_9;
  v0 = FwpsInjectionHandleCreate0(0x17u, 4u, &WinNatWFPInjectionHandleIpv6);
  if ( v0 < 0 )
    goto LABEL_9;
  GenericObject = NdisAllocateGenericObject(DriverObject, 0x626E4E57u, 0);
  NdisObject = GenericObject;
  if ( !GenericObject
    || (Parameters.Header = (NDIS_OBJECT_HEADER)1048960,
        Parameters.ContextSize = 16,
        Parameters.PoolTag = 1651396183,
        Parameters.fAllocateNetBuffer = 1,
        (WinNatNdisNblPoolHandle = NdisAllocateNetBufferListPool(GenericObject, &Parameters)) == 0) )
  {
    v0 = -1073741670;
LABEL_9:
    WinNatCleanupWFP();
    return (unsigned int)v0;
  }
  if ( !EnableXlat )
  {
    v0 = WinNatConfigureCallouts(1);
    if ( v0 < 0 )
      goto LABEL_9;
    v0 = WinNatConfigureSubLayers(1);
    if ( v0 < 0 )
      goto LABEL_9;
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1400134dc  push    rbx
0x1400134de  sub     rsp, 40h
0x1400134e2  mov     rax, cs:__security_cookie
0x1400134e9  xor     rax, rsp
0x1400134ec  mov     [rsp+48h+var_18], rax
0x1400134f1  xorps   xmm0, xmm0
0x1400134f4  lea     rcx, PushLock; PushLock
0x1400134fb  movups  xmmword ptr [rsp+48h+Parameters.Header.Type], xmm0
0x140013500  call    cs:__imp_ExInitializePushLock
0x140013507  nop     dword ptr [rax+rax+00h]
0x14001350c  mov     ecx, 2; addressFamily
0x140013511  lea     r8, WinNatWFPInjectionHandleIpv4; injectionHandle
0x140013518  lea     edx, [rcx+2]; flags
0x14001351b  call    cs:__imp_FwpsInjectionHandleCreate0
0x140013522  nop     dword ptr [rax+rax+00h]
0x140013527  mov     ebx, eax
0x140013529  test    eax, eax
0x14001352b  js      loc_1400135E6
0x140013531  mov     ecx, 17h; addressFamily
0x140013536  lea     r8, WinNatWFPInjectionHandleIpv6; injectionHandle
0x14001353d  lea     edx, [rcx-13h]; flags
0x140013540  call    cs:__imp_FwpsInjectionHandleCreate0
0x140013547  nop     dword ptr [rax+rax+00h]
0x14001354c  mov     ebx, eax
0x14001354e  test    eax, eax
0x140013550  js      loc_1400135E6
0x140013556  mov     rcx, cs:DriverObject; DriverObject
0x14001355d  xor     r8d, r8d; Size
0x140013560  mov     edx, 626E4E57h; Tag
0x140013565  call    cs:__imp_NdisAllocateGenericObject
0x14001356c  nop     dword ptr [rax+rax+00h]
0x140013571  mov     cs:NdisObject, rax
0x140013578  test    rax, rax
0x14001357b  jnz     short loc_140013584
0x14001357d  mov     ebx, 0C000009Ah
0x140013582  jmp     short loc_1400135E6
0x140013584  mov     ecx, 10h
0x140013589  mov     dword ptr [rsp+48h+Parameters.Header.Type], 100180h
0x140013591  mov     [rsp+48h+Parameters.ContextSize], cx
0x140013596  lea     rdx, [rsp+48h+Parameters]; Parameters
0x14001359b  mov     rcx, rax; NdisHandle
0x14001359e  mov     [rsp+48h+Parameters.PoolTag], 626E4E57h
0x1400135a6  mov     [rsp+48h+Parameters.fAllocateNetBuffer], 1
0x1400135ab  call    cs:__imp_NdisAllocateNetBufferListPool
0x1400135b2  nop     dword ptr [rax+rax+00h]
0x1400135b7  mov     cs:WinNatNdisNblPoolHandle, rax
0x1400135be  test    rax, rax
0x1400135c1  jz      short loc_14001357D
0x1400135c3  cmp     cs:EnableXlat, 0
0x1400135ca  jnz     short loc_1400135EB
0x1400135cc  mov     cl, 1
0x1400135ce  call    WinNatConfigureCallouts
0x1400135d3  mov     ebx, eax
0x1400135d5  test    eax, eax
0x1400135d7  js      short loc_1400135E6
0x1400135d9  mov     cl, 1
0x1400135db  call    WinNatConfigureSubLayers
0x1400135e0  mov     ebx, eax
0x1400135e2  test    eax, eax
0x1400135e4  jns     short loc_1400135EB
0x1400135e6  call    WinNatCleanupWFP
0x1400135eb  mov     eax, ebx
0x1400135ed  mov     rcx, [rsp+48h+var_18]
0x1400135f2  xor     rcx, rsp; StackCookie
0x1400135f5  call    __security_check_cookie
0x1400135fa  add     rsp, 40h
0x1400135fe  pop     rbx
0x1400135ff  retn
```
