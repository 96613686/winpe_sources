# _CUsbDevice::GetConfiguationDescriptor_::_1_::catch$1

- ea: `0x18001063e`
- end: `0x18001065f`
- name: `_CUsbDevice::GetConfiguationDescriptor_::_1_::catch$1`
- size: `33`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180002e7a`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001064f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001064f`

## pseudocode

```c
void __fastcall __noreturn CUsbDevice::GetConfiguationDescriptor_::_1_::catch_1(__int64 a1, __int64 a2)
{
  CloseHandle(*(HANDLE *)(a2 + 64));
  throw;
}

```

## disassembly

```asm
0x18001063e  mov     [rsp+arg_8], rdx
0x180010643  push    rbp
0x180010644  sub     rsp, 40h
0x180010648  mov     rbp, rdx
0x18001064b  mov     rcx, [rbp+40h]; hObject
0x18001064f  call    cs:__imp_CloseHandle
0x180010655  xor     edx, edx; pThrowInfo
0x180010657  xor     ecx, ecx; pExceptionObject
0x180010659  call    _CxxThrowException_0
```
