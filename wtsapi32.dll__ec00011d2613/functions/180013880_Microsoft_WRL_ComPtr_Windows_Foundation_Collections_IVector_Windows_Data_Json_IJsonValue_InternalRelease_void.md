# Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)

- ea: `0x180013880`
- end: `0x1800138a5`
- name: `?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ`
- size: `37`
- prototype: ``
- caller_count: `15`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012290`
- `0x180012330`
- `0x180012380`
- `0x1800123bc`
- `0x18001247c`
- `0x180012520`
- `0x180012c20`
- `0x180012e70`
- `0x180013020`
- `0x180013600`
- `0x180013990`
- `0x180013e30`
- `0x180013fa0`
- `0x1800140f0`
- `0x180014230`

## callees

- `0x180013880`
- `0x180016010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(
        __int64 *a1)
{
  __int64 result; // rax
  __int64 v3; // rcx

  result = 0;
  v3 = *a1;
  if ( v3 )
  {
    *a1 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return result;
}

```

## disassembly

```asm
0x180013880  sub     rsp, 28h
0x180013884  mov     rdx, rcx
0x180013887  xor     eax, eax
0x180013889  mov     rcx, [rcx]
0x18001388c  test    rcx, rcx
0x18001388f  jz      short loc_1800138A0
0x180013891  mov     [rdx], rax
0x180013894  mov     rax, [rcx]
0x180013897  mov     rax, [rax+10h]
0x18001389b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138a0  add     rsp, 28h
0x1800138a4  retn
```
