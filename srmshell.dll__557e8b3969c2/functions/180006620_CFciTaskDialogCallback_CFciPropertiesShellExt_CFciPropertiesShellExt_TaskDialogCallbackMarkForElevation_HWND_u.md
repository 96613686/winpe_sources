# CFciTaskDialogCallback<CFciPropertiesShellExt,{CFciPropertiesShellExt::TaskDialogCallbackMarkForElevation(HWND__ *,uint,unsigned __int64,__int64),0}>::Callback(HWND__ *,uint,unsigned __int64,__int64,__int64)

- ea: `0x180006620`
- end: `0x180006642`
- name: `?Callback@?$CFciTaskDialogCallback@VCFciPropertiesShellExt@@$H?TaskDialogCallbackMarkForElevation@1@QEAAJPEAUHWND__@@I_K_J@ZA@@@SAJPEAUHWND__@@I_K_J2@Z`
- size: `34`
- prototype: `int __fastcall(HWND, unsigned int, unsigned __int64, __int64, CFciPropertiesShellExt *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000f79c`

## pseudocode

```c
int __fastcall CFciTaskDialogCallback<CFciPropertiesShellExt,{public: long CFciPropertiesShellExt::TaskDialogCallbackMarkForElevation(HWND__ *,unsigned int,unsigned __int64,__int64),0}>::Callback(
        HWND a1,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4,
        CFciPropertiesShellExt *a5)
{
  return CFciPropertiesShellExt::TaskDialogCallbackMarkForElevation(a5, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180006620  sub     rsp, 38h
0x180006624  mov     [rsp+38h+var_18], r9; __int64
0x180006629  mov     r9, r8; unsigned __int64
0x18000662c  mov     r8d, edx; unsigned int
0x18000662f  mov     rdx, rcx; HWND
0x180006632  mov     rcx, [rsp+38h+arg_20]; this
0x180006637  call    ?TaskDialogCallbackMarkForElevation@CFciPropertiesShellExt@@QEAAJPEAUHWND__@@I_K_J@Z; CFciPropertiesShellExt::TaskDialogCallbackMarkForElevation(HWND__ *,uint,unsigned __int64,__int64)
0x18000663c  nop
0x18000663d  add     rsp, 38h
0x180006641  retn
```
