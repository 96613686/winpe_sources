# CRegistryEventRequest::~CRegistryEventRequest(void)

- ea: `0x18000b5ac`
- end: `0x18000b628`
- name: `??1CRegistryEventRequest@@UEAA@XZ`
- size: `124`
- prototype: `void __fastcall(CRegistryEventRequest *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b570`
- `0x180013d50`
- `0x18001415c`
- `0x180015f34`
- `0x180015f5f`
- `0x180015f71`
- `0x18001650a`

## callees

- `0x18000b5ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b5cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b5cf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b5ef`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b5ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b5e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b5e1`
- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x18000b600`
- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x18000b611`
- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x18000b600`
- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x18000b611`
- `wbemcomn!??1CFlexArray@@QEAA@XZ` at `0x18000b621`

## pseudocode

```c
void __fastcall CRegistryEventRequest::~CRegistryEventRequest(CRegistryEventRequest *this)
{
  HKEY v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &CRegistryEventRequest::`vftable';
  v2 = (HKEY)*((_QWORD *)this + 18);
  if ( v2 )
    RegCloseKey(v2);
  v3 = (void *)*((_QWORD *)this + 19);
  if ( v3 )
    CloseHandle(v3);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  WString::DeleteString((CRegistryEventRequest *)((char *)this + 136), *((unsigned __int16 **)this + 17));
  WString::DeleteString((CRegistryEventRequest *)((char *)this + 128), *((unsigned __int16 **)this + 16));
  CFlexArray::~CFlexArray((CRegistryEventRequest *)((char *)this + 32));
}

```

## disassembly

```asm
0x18000b5ac  mov     [rsp+arg_0], rcx
0x18000b5b1  push    rbx
0x18000b5b2  sub     rsp, 20h
0x18000b5b6  mov     rbx, rcx
0x18000b5b9  lea     rax, ??_7CRegistryEventRequest@@6B@; const CRegistryEventRequest::`vftable'
0x18000b5c0  mov     [rcx], rax
0x18000b5c3  mov     rcx, [rcx+90h]; hKey
0x18000b5ca  test    rcx, rcx
0x18000b5cd  jz      short loc_18000B5D5
0x18000b5cf  call    cs:__imp_RegCloseKey
0x18000b5d5  mov     rcx, [rbx+98h]; hObject
0x18000b5dc  test    rcx, rcx
0x18000b5df  jz      short loc_18000B5E8
0x18000b5e1  call    cs:__imp_CloseHandle
0x18000b5e7  nop
0x18000b5e8  lea     rcx, [rbx+0B8h]; lpCriticalSection
0x18000b5ef  call    cs:__imp_DeleteCriticalSection
0x18000b5f5  nop
0x18000b5f6  lea     rcx, [rbx+88h]
0x18000b5fd  mov     rdx, [rcx]
0x18000b600  call    cs:__imp_?DeleteString@WString@@AEAAXPEAG@Z; WString::DeleteString(ushort *)
0x18000b606  nop
0x18000b607  lea     rcx, [rbx+80h]
0x18000b60e  mov     rdx, [rcx]
0x18000b611  call    cs:__imp_?DeleteString@WString@@AEAAXPEAG@Z; WString::DeleteString(ushort *)
0x18000b617  nop
0x18000b618  lea     rcx, [rbx+20h]
0x18000b61c  add     rsp, 20h
0x18000b620  pop     rbx
0x18000b621  jmp     cs:__imp_??1CFlexArray@@QEAA@XZ; CFlexArray::~CFlexArray(void)
```
