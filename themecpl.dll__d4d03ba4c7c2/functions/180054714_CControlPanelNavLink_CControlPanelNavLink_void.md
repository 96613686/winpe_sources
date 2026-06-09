# CControlPanelNavLink::~CControlPanelNavLink(void)

- ea: `0x180054714`
- end: `0x18005475b`
- name: `??1CControlPanelNavLink@@QEAA@XZ`
- size: `71`
- prototype: `void __fastcall(CControlPanelNavLink *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800548a4`
- `0x180054968`
- `0x180054a90`

## callees

- `0x180054764`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054721`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054731`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054721`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054731`
- `USER32!DestroyIcon` at `0x180054741`
- `USER32!DestroyIcon` at `0x180054741`

## pseudocode

```c
void __fastcall CControlPanelNavLink::~CControlPanelNavLink(CControlPanelNavLink *this)
{
  CoTaskMemFree(*((LPVOID *)this + 1));
  CoTaskMemFree(*((LPVOID *)this + 2));
  DestroyIcon(*((HICON *)this + 3));
  CControlPanelNavLinkCommand::~CControlPanelNavLinkCommand((CControlPanelNavLink *)((char *)this + 32));
}

```

## disassembly

```asm
0x180054714  push    rbx
0x180054716  sub     rsp, 20h
0x18005471a  mov     rbx, rcx
0x18005471d  mov     rcx, [rcx+8]; pv
0x180054721  call    cs:__imp_CoTaskMemFree
0x180054728  nop     dword ptr [rax+rax+00h]
0x18005472d  mov     rcx, [rbx+10h]; pv
0x180054731  call    cs:__imp_CoTaskMemFree
0x180054738  nop     dword ptr [rax+rax+00h]
0x18005473d  mov     rcx, [rbx+18h]; hIcon
0x180054741  call    cs:__imp_DestroyIcon
0x180054748  nop     dword ptr [rax+rax+00h]
0x18005474d  lea     rcx, [rbx+20h]; this
0x180054751  add     rsp, 20h
0x180054755  pop     rbx
0x180054756  jmp     ??1CControlPanelNavLinkCommand@@QEAA@XZ; CControlPanelNavLinkCommand::~CControlPanelNavLinkCommand(void)
```
