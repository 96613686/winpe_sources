# CFciPropertiesShellExt::TaskDialogCallbackMarkForElevation(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18000f79c`
- end: `0x18000f7c5`
- name: `?TaskDialogCallbackMarkForElevation@CFciPropertiesShellExt@@QEAAJPEAUHWND__@@I_K_J@Z`
- size: `41`
- prototype: `__int64 __fastcall(CFciPropertiesShellExt *this, HWND, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180006620`

## callees

- `0x18000f79c`

## import_xrefs

- `USER32!SendMessageW` at `0x18000f7b8`
- `USER32!SendMessageW` at `0x18000f7b8`

## pseudocode

```c
__int64 __fastcall CFciPropertiesShellExt::TaskDialogCallbackMarkForElevation(
        CFciPropertiesShellExt *this,
        HWND a2,
        int a3)
{
  if ( !a3 )
    SendMessageW(a2, 0x473u, 4u, 1);
  return 0;
}

```

## disassembly

```asm
0x18000f79c  sub     rsp, 28h
0x18000f7a0  mov     rax, rdx
0x18000f7a3  test    r8d, r8d
0x18000f7a6  jnz     short loc_18000F7BE
0x18000f7a8  mov     edx, 473h; Msg
0x18000f7ad  lea     r9d, [r8+1]; lParam
0x18000f7b1  lea     r8d, [r9+3]; wParam
0x18000f7b5  mov     rcx, rax; hWnd
0x18000f7b8  call    cs:__imp_SendMessageW
0x18000f7be  xor     eax, eax
0x18000f7c0  add     rsp, 28h
0x18000f7c4  retn
```
