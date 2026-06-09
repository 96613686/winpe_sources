# EventManager::~EventManager(void)

- ea: `0x180036cfc`
- end: `0x180036d2a`
- name: `??1EventManager@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(EventManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180036cd4`

## callees

- `0x180036cfc`

## import_xrefs

- `ntdll!EtwEventUnregister` at `0x180036d0d`
- `ntdll!EtwEventUnregister` at `0x180036d0d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036d23`

## pseudocode

```c
void __fastcall EventManager::~EventManager(EventManager *this)
{
  if ( *(_QWORD *)this )
  {
    EtwEventUnregister();
    *(_QWORD *)this = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x180036cfc  push    rbx
0x180036cfe  sub     rsp, 20h
0x180036d02  mov     rbx, rcx
0x180036d05  mov     rcx, [rcx]
0x180036d08  test    rcx, rcx
0x180036d0b  jz      short loc_180036D1A
0x180036d0d  call    cs:__imp_EtwEventUnregister
0x180036d13  mov     qword ptr [rbx], 0
0x180036d1a  lea     rcx, [rbx+8]
0x180036d1e  add     rsp, 20h
0x180036d22  pop     rbx
0x180036d23  jmp     cs:__imp_DeleteCriticalSection
```
