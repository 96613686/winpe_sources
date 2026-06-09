# ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)

- ea: `0x180012290`
- end: `0x180012328`
- name: `??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@ABI@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `152`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013600`
- `0x180013c70`

## callees

- `0x180012290`
- `0x180013880`
- `0x180015576`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800122c0`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800122c0`

## pseudocode

```c
__int64 __fastcall ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(
        __int64 a1,
        __int64 *a2)
{
  int v4; // edi
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(a2);
  *a2 = 0;
  v6 = 0;
  v4 = RoActivateInstance(a1, &v6);
  if ( v4 >= 0 )
  {
    if ( !memcmp_0(&GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *a2 = v6;
    }
    else
    {
      v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v6)(
             v6,
             &GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3,
             a2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180012290  mov     [rsp+arg_0], rbx
0x180012295  push    rdi
0x180012296  sub     rsp, 20h
0x18001229a  mov     rdi, rcx
0x18001229d  mov     rbx, rdx
0x1800122a0  mov     rcx, rdx
0x1800122a3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1800122a8  lea     rdx, [rsp+28h+arg_8]
0x1800122ad  mov     qword ptr [rbx], 0
0x1800122b4  mov     rcx, rdi
0x1800122b7  mov     [rsp+28h+arg_8], 0
0x1800122c0  call    cs:__imp_RoActivateInstance
0x1800122c6  mov     edi, eax
0x1800122c8  test    eax, eax
0x1800122ca  js      short loc_18001231B
0x1800122cc  mov     r8d, 10h; Size
0x1800122d2  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x1800122d9  lea     rcx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3; Buf1
0x1800122e0  call    memcmp_0
0x1800122e5  mov     rcx, [rsp+28h+arg_8]
0x1800122ea  test    eax, eax
0x1800122ec  jnz     short loc_1800122F3
0x1800122ee  mov     [rbx], rcx
0x1800122f1  jmp     short loc_18001231B
0x1800122f3  mov     rax, [rcx]
0x1800122f6  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x1800122fd  mov     r8, rbx
0x180012300  mov     rax, [rax]
0x180012303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012308  mov     rcx, [rsp+28h+arg_8]
0x18001230d  mov     edi, eax
0x18001230f  mov     rax, [rcx]
0x180012312  mov     rax, [rax+10h]
0x180012316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001231b  mov     rbx, [rsp+28h+arg_0]
0x180012320  mov     eax, edi
0x180012322  add     rsp, 20h
0x180012326  pop     rdi
0x180012327  retn
```
