# CEventUI::UpdateUIStateProgress(EVENTUI_STATE,unsigned __int64,unsigned __int64)

- ea: `0x180008760`
- end: `0x1800087ac`
- name: `?UpdateUIStateProgress@CEventUI@@UEAAJW4EVENTUI_STATE@@_K1@Z`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180008760`
- `0x18000899c`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180008787`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180008787`

## pseudocode

```c
__int64 __fastcall CEventUI::UpdateUIStateProgress(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  if ( (unsigned int)(a2 - 3) > 1 )
    return 2147947423LL;
  if ( IsWindow(*(HWND *)(a1 + 112)) )
    CEventUI::UploadDlgUpdateState(a1, a2, a3, a4);
  return 0;
}

```

## disassembly

```asm
0x180008760  push    rbx
0x180008762  push    rbp
0x180008763  push    rsi
0x180008764  push    rdi
0x180008765  sub     rsp, 28h
0x180008769  lea     eax, [rdx-3]
0x18000876c  mov     rsi, r9
0x18000876f  mov     rbp, r8
0x180008772  mov     edi, edx
0x180008774  mov     rbx, rcx
0x180008777  cmp     eax, 1
0x18000877a  jbe     short loc_180008783
0x18000877c  mov     eax, 8007139Fh
0x180008781  jmp     short loc_1800087A3
0x180008783  mov     rcx, [rcx+70h]; hWnd
0x180008787  call    cs:__imp_IsWindow
0x18000878d  test    eax, eax
0x18000878f  jz      short loc_1800087A1
0x180008791  mov     r9, rsi
0x180008794  mov     r8, rbp
0x180008797  mov     edx, edi
0x180008799  mov     rcx, rbx
0x18000879c  call    ?UploadDlgUpdateState@CEventUI@@AEAAJW4EVENTUI_STATE@@_K1@Z; CEventUI::UploadDlgUpdateState(EVENTUI_STATE,unsigned __int64,unsigned __int64)
0x1800087a1  xor     eax, eax
0x1800087a3  add     rsp, 28h
0x1800087a7  pop     rdi
0x1800087a8  pop     rsi
0x1800087a9  pop     rbp
0x1800087aa  pop     rbx
0x1800087ab  retn
```
