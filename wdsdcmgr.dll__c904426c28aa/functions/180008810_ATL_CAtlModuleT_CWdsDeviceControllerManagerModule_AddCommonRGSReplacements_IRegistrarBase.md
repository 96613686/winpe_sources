# ATL::CAtlModuleT<CWdsDeviceControllerManagerModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180008810`
- end: `0x18000882f`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCWdsDeviceControllerManagerModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180015cc0`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CWdsDeviceControllerManagerModule>::AddCommonRGSReplacements(
        __int64 a1,
        __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const OLECHAR *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &word_18001870C);
}

```

## disassembly

```asm
0x180008810  mov     rax, [rdx]
0x180008813  lea     r8, word_18001870C
0x18000881a  mov     rcx, rdx
0x18000881d  lea     rdx, aAppid; "APPID"
0x180008824  mov     rax, [rax+18h]
0x180008828  jmp     cs:__guard_dispatch_icall_fptr
```
