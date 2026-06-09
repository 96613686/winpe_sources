# CControlPanelNavLinkCommand::~CControlPanelNavLinkCommand(void)

- ea: `0x180054764`
- end: `0x1800547ab`
- name: `??1CControlPanelNavLinkCommand@@QEAA@XZ`
- size: `71`
- prototype: `void __fastcall(CControlPanelNavLinkCommand *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180054714`

## callees

- `0x180011734`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054771`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054789`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054771`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054789`

## pseudocode

```c
void __fastcall CControlPanelNavLinkCommand::~CControlPanelNavLinkCommand(LPVOID *this)
{
  void *v2; // rcx
  void *v3; // rcx

  CoTaskMemFree(this[1]);
  v2 = this[2];
  this[1] = 0;
  CoTaskMemFree(v2);
  v3 = this[5];
  this[2] = 0;
  operator delete(v3);
}

```

## disassembly

```asm
0x180054764  push    rbx
0x180054766  sub     rsp, 20h
0x18005476a  mov     rbx, rcx
0x18005476d  mov     rcx, [rcx+8]; pv
0x180054771  call    cs:__imp_CoTaskMemFree
0x180054778  nop     dword ptr [rax+rax+00h]
0x18005477d  mov     rcx, [rbx+10h]; pv
0x180054781  mov     qword ptr [rbx+8], 0
0x180054789  call    cs:__imp_CoTaskMemFree
0x180054790  nop     dword ptr [rax+rax+00h]
0x180054795  mov     rcx, [rbx+28h]; lpMem
0x180054799  mov     qword ptr [rbx+10h], 0
0x1800547a1  add     rsp, 20h
0x1800547a5  pop     rbx
0x1800547a6  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
