# Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Devices::Enumeration::IDeviceAccessInformationStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Devices::Enumeration::IDeviceAccessInformationStatics>>)

- ea: `0x180003348`
- end: `0x18000337e`
- name: `??$GetActivationFactory@V?$ComPtr@UIDeviceAccessInformationStatics@Enumeration@Devices@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIDeviceAccessInformationStatics@Enumeration@Devices@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000bf20`
- `0x1800140a0`

## callees

- `0x180006844`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180003377`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Devices::Enumeration::IDeviceAccessInformationStatics>>(
        __int64 a1,
        __int64 a2)
{
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a2);
  return RoGetActivationFactory(a1, &GUID_574bd3d3_5f30_45cd_8a94_724fe5973084, a2);
}

```

## disassembly

```asm
0x180003348  mov     [rsp+arg_0], rbx
0x18000334d  push    rdi
0x18000334e  sub     rsp, 20h
0x180003352  mov     rdi, rcx
0x180003355  mov     rbx, rdx
0x180003358  mov     rcx, rdx
0x18000335b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180003360  mov     r8, rbx
0x180003363  lea     rdx, _GUID_574bd3d3_5f30_45cd_8a94_724fe5973084
0x18000336a  mov     rcx, rdi
0x18000336d  mov     rbx, [rsp+28h+arg_0]
0x180003372  add     rsp, 20h
0x180003376  pop     rdi
0x180003377  jmp     cs:__imp_RoGetActivationFactory
```
