# CConsentUI::Static_UpSellTaskDialogCallbackProc(HWND__ *,uint,unsigned __int64,__int64,__int64)

- ea: `0x18000a880`
- end: `0x18000a8ee`
- name: `?Static_UpSellTaskDialogCallbackProc@CConsentUI@@CAJPEAUHWND__@@I_K_J2@Z`
- size: `110`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004430`
- `0x18000a880`
- `0x18000c8a0`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x18000a8cb`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x18000a8cb`

## pseudocode

```c
__int64 __fastcall CConsentUI::Static_UpSellTaskDialogCallbackProc(HWND a1, int a2, __int64 a3, __int64 a4, __int64 a5)
{
  if ( a2 )
  {
    if ( a2 == 3 )
      LaunchPrivacyURL();
  }
  else
  {
    SetWindowPos(a1, (HWND)-(__int64)(*(_DWORD *)(a5 + 320) != 0), 0, 0, 0, 0, 0x43u);
    CUIDlgBase::UICallback(a5, 16);
  }
  return 0;
}

```

## disassembly

```asm
0x18000a880  mov     [rsp+arg_0], rbx
0x18000a885  push    rdi
0x18000a886  sub     rsp, 40h
0x18000a88a  mov     rdi, rcx
0x18000a88d  test    edx, edx
0x18000a88f  jz      short loc_18000A89D
0x18000a891  cmp     edx, 3
0x18000a894  jnz     short loc_18000A8E1
0x18000a896  call    ?LaunchPrivacyURL@@YAJH@Z; LaunchPrivacyURL(int)
0x18000a89b  jmp     short loc_18000A8E1
0x18000a89d  mov     rbx, [rsp+48h+arg_20]
0x18000a8a2  mov     [rsp+48h+uFlags], 43h ; 'C'; uFlags
0x18000a8aa  mov     [rsp+48h+cy], 0; cy
0x18000a8b2  mov     [rsp+48h+var_28], 0; cx
0x18000a8ba  mov     eax, [rbx+140h]
0x18000a8c0  neg     eax
0x18000a8c2  sbb     rdx, rdx; hWndInsertAfter
0x18000a8c5  xor     r9d, r9d; Y
0x18000a8c8  xor     r8d, r8d; X
0x18000a8cb  call    cs:__imp_SetWindowPos
0x18000a8d1  mov     r8, rdi
0x18000a8d4  mov     edx, 10h
0x18000a8d9  mov     rcx, rbx
0x18000a8dc  call    ?UICallback@CUIDlgBase@@IEAAHW4_UICALLBACKTYPE@@_K@Z; CUIDlgBase::UICallback(_UICALLBACKTYPE,unsigned __int64)
0x18000a8e1  mov     rbx, [rsp+48h+arg_0]
0x18000a8e6  xor     eax, eax
0x18000a8e8  add     rsp, 40h
0x18000a8ec  pop     rdi
0x18000a8ed  retn
```
