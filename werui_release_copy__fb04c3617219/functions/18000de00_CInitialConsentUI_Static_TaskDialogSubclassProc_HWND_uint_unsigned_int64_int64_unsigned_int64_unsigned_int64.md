# CInitialConsentUI::Static_TaskDialogSubclassProc(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64)

- ea: `0x18000de00`
- end: `0x18000de18`
- name: `?Static_TaskDialogSubclassProc@CInitialConsentUI@@CA_JPEAUHWND__@@I_K_J11@Z`
- size: `24`
- prototype: `LRESULT __stdcall(HWND hWnd, UINT uMsg, WPARAM wParam, LPARAM lParam, UINT_PTR uIdSubclass, DWORD_PTR dwRefData)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000df18`

## pseudocode

```c
LRESULT __fastcall CInitialConsentUI::Static_TaskDialogSubclassProc(
        HWND hWnd,
        UINT uMsg,
        WPARAM wParam,
        HWND lParam,
        UINT_PTR uIdSubclass,
        CInitialConsentUI *dwRefData)
{
  return CInitialConsentUI::TaskDialogSubclassProc(dwRefData, hWnd, uMsg, wParam, lParam);
}

```

## disassembly

```asm
0x18000de00  mov     [rsp+uIdSubclass], r9; LPARAM
0x18000de05  mov     r9, r8; unsigned __int64
0x18000de08  mov     r8d, edx; uMsg
0x18000de0b  mov     rdx, rcx; lParam
0x18000de0e  mov     rcx, [rsp+dwRefData]; this
0x18000de13  jmp     ?TaskDialogSubclassProc@CInitialConsentUI@@AEAA_JPEAUHWND__@@I_K_J@Z; CInitialConsentUI::TaskDialogSubclassProc(HWND__ *,uint,unsigned __int64,__int64)
```
