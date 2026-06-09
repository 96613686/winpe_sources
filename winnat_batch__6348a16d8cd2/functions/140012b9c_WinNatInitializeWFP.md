# WinNatInitializeWFP

- ea: `0x140012b9c`
- end: `0x140012cc1`
- name: `WinNatInitializeWFP`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140035078`

## callees

- `0x140012100`
- `0x140012478`
- `0x1400127b4`
- `0x140012b9c`
- `0x14001ede0`

## import_xrefs

- `ntoskrnl!ExInitializePushLock` at `0x140012bc0`
- `ntoskrnl!ExInitializePushLock` at `0x140012bc0`
- `NDIS!NdisAllocateNetBufferListPool` at `0x140012c6b`
- `NDIS!NdisAllocateNetBufferListPool` at `0x140012c6b`
- `NDIS!NdisAllocateGenericObject` at `0x140012c25`
- `NDIS!NdisAllocateGenericObject` at `0x140012c25`
- `fwpkclnt!FwpsInjectionHandleCreate0` at `0x140012bdb`
- `fwpkclnt!FwpsInjectionHandleCreate0` at `0x140012c00`
- `fwpkclnt!FwpsInjectionHandleCreate0` at `0x140012bdb`
- `fwpkclnt!FwpsInjectionHandleCreate0` at `0x140012c00`

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
0x140012b9c  push    rbx
0x140012b9e  sub     rsp, 40h
0x140012ba2  mov     rax, cs:__security_cookie
0x140012ba9  xor     rax, rsp
0x140012bac  mov     [rsp+48h+var_18], rax
0x140012bb1  xorps   xmm0, xmm0
0x140012bb4  lea     rcx, PushLock; PushLock
0x140012bbb  movups  xmmword ptr [rsp+48h+Parameters.Header.Type], xmm0
0x140012bc0  call    cs:__imp_ExInitializePushLock
0x140012bc7  nop     dword ptr [rax+rax+00h]
0x140012bcc  mov     ecx, 2; addressFamily
0x140012bd1  lea     r8, WinNatWFPInjectionHandleIpv4; injectionHandle
0x140012bd8  lea     edx, [rcx+2]; flags
0x140012bdb  call    cs:__imp_FwpsInjectionHandleCreate0
0x140012be2  nop     dword ptr [rax+rax+00h]
0x140012be7  mov     ebx, eax
0x140012be9  test    eax, eax
0x140012beb  js      loc_140012CA6
0x140012bf1  mov     ecx, 17h; addressFamily
0x140012bf6  lea     r8, WinNatWFPInjectionHandleIpv6; injectionHandle
0x140012bfd  lea     edx, [rcx-13h]; flags
0x140012c00  call    cs:__imp_FwpsInjectionHandleCreate0
0x140012c07  nop     dword ptr [rax+rax+00h]
0x140012c0c  mov     ebx, eax
0x140012c0e  test    eax, eax
0x140012c10  js      loc_140012CA6
0x140012c16  mov     rcx, cs:DriverObject; DriverObject
0x140012c1d  xor     r8d, r8d; Size
0x140012c20  mov     edx, 626E4E57h; Tag
0x140012c25  call    cs:__imp_NdisAllocateGenericObject
0x140012c2c  nop     dword ptr [rax+rax+00h]
0x140012c31  mov     cs:NdisObject, rax
0x140012c38  test    rax, rax
0x140012c3b  jnz     short loc_140012C44
0x140012c3d  mov     ebx, 0C000009Ah
0x140012c42  jmp     short loc_140012CA6
0x140012c44  mov     ecx, 10h
0x140012c49  mov     dword ptr [rsp+48h+Parameters.Header.Type], 100180h
0x140012c51  mov     [rsp+48h+Parameters.ContextSize], cx
0x140012c56  lea     rdx, [rsp+48h+Parameters]; Parameters
0x140012c5b  mov     rcx, rax; NdisHandle
0x140012c5e  mov     [rsp+48h+Parameters.PoolTag], 626E4E57h
0x140012c66  mov     [rsp+48h+Parameters.fAllocateNetBuffer], 1
0x140012c6b  call    cs:__imp_NdisAllocateNetBufferListPool
0x140012c72  nop     dword ptr [rax+rax+00h]
0x140012c77  mov     cs:WinNatNdisNblPoolHandle, rax
0x140012c7e  test    rax, rax
0x140012c81  jz      short loc_140012C3D
0x140012c83  cmp     cs:EnableXlat, 0
0x140012c8a  jnz     short loc_140012CAB
0x140012c8c  mov     cl, 1
0x140012c8e  call    WinNatConfigureCallouts
0x140012c93  mov     ebx, eax
0x140012c95  test    eax, eax
0x140012c97  js      short loc_140012CA6
0x140012c99  mov     cl, 1
0x140012c9b  call    WinNatConfigureSubLayers
0x140012ca0  mov     ebx, eax
0x140012ca2  test    eax, eax
0x140012ca4  jns     short loc_140012CAB
0x140012ca6  call    WinNatCleanupWFP
0x140012cab  mov     eax, ebx
0x140012cad  mov     rcx, [rsp+48h+var_18]
0x140012cb2  xor     rcx, rsp; StackCookie
0x140012cb5  call    __security_check_cookie
0x140012cba  add     rsp, 40h
0x140012cbe  pop     rbx
0x140012cbf  retn
```
