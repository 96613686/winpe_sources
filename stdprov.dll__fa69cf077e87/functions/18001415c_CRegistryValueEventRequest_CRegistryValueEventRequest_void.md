# CRegistryValueEventRequest::~CRegistryValueEventRequest(void)

- ea: `0x18001415c`
- end: `0x180014187`
- name: `??1CRegistryValueEventRequest@@UEAA@XZ`
- size: `43`
- prototype: `void __fastcall(unsigned __int16 **this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800141b0`

## callees

- `0x18000b5ac`

## import_xrefs

- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x180014173`
- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x180014173`

## pseudocode

```c
void __fastcall CRegistryValueEventRequest::~CRegistryValueEventRequest(unsigned __int16 **this)
{
  WString::DeleteString((WString *)(this + 28), this[28]);
  CRegistryEventRequest::~CRegistryEventRequest((CRegistryEventRequest *)this);
}

```

## disassembly

```asm
0x18001415c  mov     [rsp+arg_0], rcx
0x180014161  push    rbx
0x180014162  sub     rsp, 20h
0x180014166  mov     rbx, rcx
0x180014169  add     rcx, 0E0h
0x180014170  mov     rdx, [rcx]
0x180014173  call    cs:__imp_?DeleteString@WString@@AEAAXPEAG@Z; WString::DeleteString(ushort *)
0x180014179  nop
0x18001417a  mov     rcx, rbx; this
0x18001417d  add     rsp, 20h
0x180014181  pop     rbx
0x180014182  jmp     ??1CRegistryEventRequest@@UEAA@XZ; CRegistryEventRequest::~CRegistryEventRequest(void)
```
