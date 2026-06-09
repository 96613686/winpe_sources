# ABI::Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>)

- ea: `0x180012380`
- end: `0x1800123b6`
- name: `??$GetActivationFactory@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@ABI@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `54`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013600`
- `0x180013e30`

## callees

- `0x180013880`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800123af`

## pseudocode

```c
__int64 __fastcall ABI::Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(
        __int64 a1,
        __int64 *a2)
{
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(a2);
  return RoGetActivationFactory(a1, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, a2);
}

```

## disassembly

```asm
0x180012380  mov     [rsp+arg_0], rbx
0x180012385  push    rdi
0x180012386  sub     rsp, 20h
0x18001238a  mov     rdi, rcx
0x18001238d  mov     rbx, rdx
0x180012390  mov     rcx, rdx
0x180012393  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x180012398  mov     r8, rbx
0x18001239b  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x1800123a2  mov     rcx, rdi
0x1800123a5  mov     rbx, [rsp+28h+arg_0]
0x1800123aa  add     rsp, 20h
0x1800123ae  pop     rdi
0x1800123af  jmp     cs:__imp_RoGetActivationFactory
```
