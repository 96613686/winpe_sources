# CRegistryValueEventRequest::`vector deleting destructor'(uint)

- ea: `0x1800141b0`
- end: `0x1800141e0`
- name: `??_ECRegistryValueEventRequest@@UEAAPEAXI@Z`
- size: `48`
- prototype: `unsigned __int16 **__fastcall(unsigned __int16 **this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001415c`
- `0x1800141b0`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800141cc`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800141cc`

## pseudocode

```c
unsigned __int16 **__fastcall CRegistryValueEventRequest::`vector deleting destructor'(
        unsigned __int16 **this,
        char a2)
{
  CRegistryValueEventRequest::~CRegistryValueEventRequest(this);
  if ( (a2 & 1) != 0 )
    CWin32DefaultArena::WbemMemFree(this);
  return this;
}

```

## disassembly

```asm
0x1800141b0  mov     [rsp+arg_0], rbx
0x1800141b5  push    rdi
0x1800141b6  sub     rsp, 20h
0x1800141ba  mov     ebx, edx
0x1800141bc  mov     rdi, rcx
0x1800141bf  call    ??1CRegistryValueEventRequest@@UEAA@XZ; CRegistryValueEventRequest::~CRegistryValueEventRequest(void)
0x1800141c4  test    bl, 1
0x1800141c7  jz      short loc_1800141D2
0x1800141c9  mov     rcx, rdi
0x1800141cc  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800141d2  mov     rax, rdi
0x1800141d5  mov     rbx, [rsp+28h+arg_0]
0x1800141da  add     rsp, 20h
0x1800141de  pop     rdi
0x1800141df  retn
```
