# Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)

- ea: `0x180013bc0`
- end: `0x180013c0a`
- name: `??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `74`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180019d04`
- `0x18001cfac`
- `0x18002e190`
- `0x18002ec5c`
- `0x18002f7e4`

## callees

- `0x180013bc0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013c03`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(
        __int64 a1,
        __int64 *a2)
{
  __int64 v4; // rcx

  v4 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return RoGetActivationFactory(a1, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, a2);
}

```

## disassembly

```asm
0x180013bc0  mov     [rsp+arg_0], rbx
0x180013bc5  push    rdi
0x180013bc6  sub     rsp, 20h
0x180013bca  mov     rbx, rdx
0x180013bcd  mov     rdi, rcx
0x180013bd0  mov     rcx, [rdx]
0x180013bd3  test    rcx, rcx
0x180013bd6  jz      short loc_180013BEC
0x180013bd8  mov     qword ptr [rdx], 0
0x180013bdf  mov     rax, [rcx]
0x180013be2  mov     rax, [rax+10h]
0x180013be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013beb  nop
0x180013bec  mov     r8, rbx
0x180013bef  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x180013bf6  mov     rcx, rdi
0x180013bf9  mov     rbx, [rsp+28h+arg_0]
0x180013bfe  add     rsp, 20h
0x180013c02  pop     rdi
0x180013c03  jmp     cs:__imp_RoGetActivationFactory
```
