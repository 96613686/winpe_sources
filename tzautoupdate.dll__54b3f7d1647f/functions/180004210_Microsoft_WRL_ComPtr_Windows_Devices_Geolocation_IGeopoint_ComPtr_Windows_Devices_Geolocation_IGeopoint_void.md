# Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeopoint>::~ComPtr<Windows::Devices::Geolocation::IGeopoint>(void)

- ea: `0x180004210`
- end: `0x180004215`
- name: `??1?$ComPtr@UIGeopoint@Geolocation@Devices@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `18`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001bd7f`
- `0x18001bd95`
- `0x18001bdc1`
- `0x18001bfda`
- `0x18001bfec`
- `0x18001bffe`
- `0x18001c022`
- `0x18001c034`
- `0x18001c046`
- `0x18001c058`
- `0x18001c06a`
- `0x18001c07c`
- `0x18001c08e`
- `0x18001c40c`
- `0x18001c41e`
- `0x18001c5c7`
- `0x18001c5eb`
- `0x18001c5fd`

## callees

- `0x180006844`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeopoint>::~ComPtr<Windows::Devices::Geolocation::IGeopoint>(
        __int64 a1)
{
  return Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a1);
}

```

## disassembly

```asm
0x180004210  jmp     ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
```
