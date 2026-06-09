# Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeolocator>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeolocator>>)

- ea: `0x18001052c`
- end: `0x1800105c4`
- name: `??$ActivateInstance@V?$ComPtr@UIGeolocator@Geolocation@Devices@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIGeolocator@Geolocation@Devices@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800117d0`

## callees

- `0x180006844`
- `0x18001052c`
- `0x18001b0ea`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18001055c`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18001055c`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeolocator>>(
        __int64 a1,
        _QWORD *a2)
{
  int v4; // edi
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a2);
  *a2 = 0;
  v6 = 0;
  v4 = RoActivateInstance(a1, &v6);
  if ( v4 >= 0 )
  {
    if ( !memcmp_0(&GUID_a9c3bf62_4524_4989_8aa9_de019d2e551f, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *a2 = v6;
    }
    else
    {
      v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v6)(
             v6,
             &GUID_a9c3bf62_4524_4989_8aa9_de019d2e551f,
             a2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001052c  mov     [rsp+arg_0], rbx
0x180010531  push    rdi
0x180010532  sub     rsp, 20h
0x180010536  mov     rbx, rdx
0x180010539  mov     rdi, rcx
0x18001053c  mov     rcx, rdx
0x18001053f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180010544  mov     qword ptr [rbx], 0
0x18001054b  mov     [rsp+28h+arg_8], 0
0x180010554  lea     rdx, [rsp+28h+arg_8]
0x180010559  mov     rcx, rdi
0x18001055c  call    cs:__imp_RoActivateInstance
0x180010562  mov     edi, eax
0x180010564  test    eax, eax
0x180010566  js      short loc_1800105B7
0x180010568  mov     r8d, 10h; Size
0x18001056e  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180010575  lea     rcx, _GUID_a9c3bf62_4524_4989_8aa9_de019d2e551f; Buf1
0x18001057c  call    memcmp_0
0x180010581  mov     rcx, [rsp+28h+arg_8]
0x180010586  test    eax, eax
0x180010588  jnz     short loc_18001058F
0x18001058a  mov     [rbx], rcx
0x18001058d  jmp     short loc_1800105B7
0x18001058f  mov     rax, [rcx]
0x180010592  mov     r8, rbx
0x180010595  lea     rdx, _GUID_a9c3bf62_4524_4989_8aa9_de019d2e551f
0x18001059c  mov     rax, [rax]
0x18001059f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105a4  mov     edi, eax
0x1800105a6  mov     rcx, [rsp+28h+arg_8]
0x1800105ab  mov     rax, [rcx]
0x1800105ae  mov     rax, [rax+10h]
0x1800105b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105b7  mov     eax, edi
0x1800105b9  mov     rbx, [rsp+28h+arg_0]
0x1800105be  add     rsp, 20h
0x1800105c2  pop     rdi
0x1800105c3  retn
```
