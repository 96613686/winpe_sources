# CFciTaskDialogCallback<CFciPropertiesShellExt,{CFciPropertiesShellExt::TaskDialogCallbackApply(HWND__ *,uint,unsigned __int64,__int64),0}>::Callback(HWND__ *,uint,unsigned __int64,__int64,__int64)

- ea: `0x1800065f0`
- end: `0x180006612`
- name: `?Callback@?$CFciTaskDialogCallback@VCFciPropertiesShellExt@@$H?TaskDialogCallbackApply@1@QEAAJPEAUHWND__@@I_K_J@ZA@@@SAJPEAUHWND__@@I_K_J2@Z`
- size: `34`
- prototype: `int __fastcall(HWND, unsigned int, unsigned __int64, __int64, CFciPropertiesShellExt *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000f6dc`

## pseudocode

```c
int __fastcall CFciTaskDialogCallback<CFciPropertiesShellExt,{public: long CFciPropertiesShellExt::TaskDialogCallbackApply(HWND__ *,unsigned int,unsigned __int64,__int64),0}>::Callback(
        HWND a1,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4,
        CFciPropertiesShellExt *a5)
{
  return CFciPropertiesShellExt::TaskDialogCallbackApply(a5, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800065f0  sub     rsp, 38h
0x1800065f4  mov     [rsp+38h+var_18], r9; __int64
0x1800065f9  mov     r9, r8; unsigned __int64
0x1800065fc  mov     r8d, edx; unsigned int
0x1800065ff  mov     rdx, rcx; HWND
0x180006602  mov     rcx, [rsp+38h+arg_20]; this
0x180006607  call    ?TaskDialogCallbackApply@CFciPropertiesShellExt@@QEAAJPEAUHWND__@@I_K_J@Z; CFciPropertiesShellExt::TaskDialogCallbackApply(HWND__ *,uint,unsigned __int64,__int64)
0x18000660c  nop
0x18000660d  add     rsp, 38h
0x180006611  retn
```
