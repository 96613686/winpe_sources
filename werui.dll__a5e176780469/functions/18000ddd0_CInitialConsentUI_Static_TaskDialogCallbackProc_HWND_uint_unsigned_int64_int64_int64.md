# CInitialConsentUI::Static_TaskDialogCallbackProc(HWND__ *,uint,unsigned __int64,__int64,__int64)

- ea: `0x18000ddd0`
- end: `0x18000ddec`
- name: `?Static_TaskDialogCallbackProc@CInitialConsentUI@@CAJPEAUHWND__@@I_K_J2@Z`
- size: `28`
- prototype: `__int64 __usercall@<rax>(HWND@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000de20`

## pseudocode

```c
__int64 __fastcall CInitialConsentUI::Static_TaskDialogCallbackProc(
        HWND a1,
        int a2,
        __int64 a3,
        __int64 a4,
        HANDLE *a5)
{
  return CInitialConsentUI::TaskDialogCallbackProc(a5, a1, a2, a3);
}

```

## disassembly

```asm
0x18000ddd0  sub     rsp, 38h
0x18000ddd4  mov     r9, r8; unsigned __int64
0x18000ddd7  mov     r8d, edx; unsigned int
0x18000ddda  mov     rdx, rcx; HWND
0x18000dddd  mov     rcx, [rsp+38h+arg_20]; this
0x18000dde2  call    ?TaskDialogCallbackProc@CInitialConsentUI@@AEAAJPEAUHWND__@@I_K_J2@Z; CInitialConsentUI::TaskDialogCallbackProc(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x18000dde7  add     rsp, 38h
0x18000ddeb  retn
```
