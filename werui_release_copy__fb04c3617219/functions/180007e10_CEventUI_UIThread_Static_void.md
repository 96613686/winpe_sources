# CEventUI::UIThread_Static(void *)

- ea: `0x180007e10`
- end: `0x180007e3c`
- name: `?UIThread_Static@CEventUI@@CAKPEAX@Z`
- size: `44`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180006188`

## import_xrefs

- `ext-ms-win-ntuser-message-l1-1-0!RegisterWindowMessageW` at `0x180007e20`
- `ext-ms-win-ntuser-message-l1-1-0!RegisterWindowMessageW` at `0x180007e20`

## string_xrefs

- `0x180007e19`: `TaskbarCreated`

## pseudocode

```c
__int64 __fastcall CEventUI::UIThread_Static(CEventUI *Parameter)
{
  *((_DWORD *)Parameter + 190) = RegisterWindowMessageW(L"TaskbarCreated");
  CEventUI::CreateProgressDialog(Parameter);
  return 0;
}

```

## disassembly

```asm
0x180007e10  push    rbx
0x180007e12  sub     rsp, 20h
0x180007e16  mov     rbx, rcx
0x180007e19  lea     rcx, aTaskbarcreated; "TaskbarCreated"
0x180007e20  call    cs:__imp_RegisterWindowMessageW
0x180007e26  mov     rcx, rbx; this
0x180007e29  mov     [rbx+2F8h], eax
0x180007e2f  call    ?CreateProgressDialog@CEventUI@@AEAAJXZ; CEventUI::CreateProgressDialog(void)
0x180007e34  xor     eax, eax
0x180007e36  add     rsp, 20h
0x180007e3a  pop     rbx
0x180007e3b  retn
```
