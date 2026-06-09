# Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)

- ea: `0x180012330`
- end: `0x180012377`
- name: `??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z`
- size: `71`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012c20`
- `0x180012e70`
- `0x180014230`

## callees

- `0x180013880`
- `0x180016010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, __int64 *),
        __int64 *a2)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // rsi
  __int64 (__fastcall *v4)(_QWORD, GUID *, __int64 *); // rdi

  v2 = *a1;
  v4 = ***a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(a2);
  return v4(v2, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, a2);
}

```

## disassembly

```asm
0x180012330  mov     [rsp+arg_0], rbx
0x180012335  mov     [rsp+arg_8], rsi
0x18001233a  push    rdi
0x18001233b  sub     rsp, 20h
0x18001233f  mov     rsi, [rcx]
0x180012342  mov     rbx, rdx
0x180012345  mov     rcx, rdx
0x180012348  mov     rax, [rsi]
0x18001234b  mov     rdi, [rax]
0x18001234e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x180012353  mov     r8, rbx
0x180012356  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x18001235d  mov     rcx, rsi
0x180012360  mov     rax, rdi
0x180012363  mov     rbx, [rsp+28h+arg_0]
0x180012368  mov     rsi, [rsp+28h+arg_8]
0x18001236d  add     rsp, 20h
0x180012371  pop     rdi
0x180012372  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
