# EventManager::~EventManager(void)

- ea: `0x18001851c`
- end: `0x18001854a`
- name: `??1EventManager@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(EventManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800060e0`

## callees

- `0x18001851c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018543`
- `ntdll!EtwEventUnregister` at `0x18001852d`
- `ntdll!EtwEventUnregister` at `0x18001852d`

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
0x18001851c  push    rbx
0x18001851e  sub     rsp, 20h
0x180018522  mov     rbx, rcx
0x180018525  mov     rcx, [rcx]
0x180018528  test    rcx, rcx
0x18001852b  jz      short loc_18001853A
0x18001852d  call    cs:__imp_EtwEventUnregister
0x180018533  mov     qword ptr [rbx], 0
0x18001853a  lea     rcx, [rbx+8]
0x18001853e  add     rsp, 20h
0x180018542  pop     rbx
0x180018543  jmp     cs:__imp_DeleteCriticalSection
```
