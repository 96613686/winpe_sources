# CRegistryEventRequest::`scalar deleting destructor'(uint)

- ea: `0x180013d50`
- end: `0x180013d80`
- name: `??_GCRegistryEventRequest@@UEAAPEAXI@Z`
- size: `48`
- prototype: `CRegistryEventRequest *__fastcall(CRegistryEventRequest *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000b5ac`
- `0x180013d50`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013d6c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013d6c`

## pseudocode

```c
CRegistryEventRequest *__fastcall CRegistryEventRequest::`scalar deleting destructor'(
        CRegistryEventRequest *this,
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
0x180013d50  mov     [rsp+arg_0], rbx
0x180013d55  push    rdi
0x180013d56  sub     rsp, 20h
0x180013d5a  mov     ebx, edx
0x180013d5c  mov     rdi, rcx
0x180013d5f  call    ??1CRegistryEventRequest@@UEAA@XZ; CRegistryEventRequest::~CRegistryEventRequest(void)
0x180013d64  test    bl, 1
0x180013d67  jz      short loc_180013D72
0x180013d69  mov     rcx, rdi
0x180013d6c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180013d72  mov     rax, rdi
0x180013d75  mov     rbx, [rsp+28h+arg_0]
0x180013d7a  add     rsp, 20h
0x180013d7e  pop     rdi
0x180013d7f  retn
```
