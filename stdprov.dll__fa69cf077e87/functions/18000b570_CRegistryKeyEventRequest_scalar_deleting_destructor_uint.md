# CRegistryKeyEventRequest::`scalar deleting destructor'(uint)

- ea: `0x18000b570`
- end: `0x18000b5a5`
- name: `??_GCRegistryKeyEventRequest@@UEAAPEAXI@Z`
- size: `53`
- prototype: `CRegistryKeyEventRequest *__fastcall(CRegistryKeyEventRequest *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000b570`
- `0x18000b5ac`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000b591`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000b591`

## pseudocode

```c
CRegistryKeyEventRequest *__fastcall CRegistryKeyEventRequest::`scalar deleting destructor'(
        CRegistryKeyEventRequest *this,
        char a2)
{
  CRegistryEventRequest::~CRegistryEventRequest(this);
  if ( (a2 & 1) != 0 )
    CWin32DefaultArena::WbemMemFree(this);
  return this;
}

```

## disassembly

```asm
0x18000b570  mov     [rsp+arg_8], rbx
0x18000b575  mov     [rsp+arg_0], rcx
0x18000b57a  push    rdi
0x18000b57b  sub     rsp, 20h
0x18000b57f  mov     ebx, edx
0x18000b581  mov     rdi, rcx
0x18000b584  call    ??1CRegistryEventRequest@@UEAA@XZ; CRegistryEventRequest::~CRegistryEventRequest(void)
0x18000b589  test    bl, 1
0x18000b58c  jz      short loc_18000B597
0x18000b58e  mov     rcx, rdi
0x18000b591  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000b597  mov     rax, rdi
0x18000b59a  mov     rbx, [rsp+28h+arg_8]
0x18000b59f  add     rsp, 20h
0x18000b5a3  pop     rdi
0x18000b5a4  retn
```
