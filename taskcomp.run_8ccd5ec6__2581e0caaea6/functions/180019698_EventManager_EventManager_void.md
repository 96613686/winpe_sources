# EventManager::~EventManager(void)

- ea: `0x180019698`
- end: `0x1800196d1`
- name: `??1EventManager@@QEAA@XZ`
- size: `57`
- prototype: `void __fastcall(EventManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006498`

## callees

- `0x180019698`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800196c5`
- `ntdll!EtwEventUnregister` at `0x1800196a9`
- `ntdll!EtwEventUnregister` at `0x1800196a9`

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
0x180019698  push    rbx
0x18001969a  sub     rsp, 20h
0x18001969e  mov     rbx, rcx
0x1800196a1  mov     rcx, [rcx]
0x1800196a4  test    rcx, rcx
0x1800196a7  jz      short loc_1800196BC
0x1800196a9  call    cs:__imp_EtwEventUnregister
0x1800196b0  nop     dword ptr [rax+rax+00h]
0x1800196b5  mov     qword ptr [rbx], 0
0x1800196bc  lea     rcx, [rbx+8]
0x1800196c0  add     rsp, 20h
0x1800196c4  pop     rbx
0x1800196c5  jmp     cs:__imp_DeleteCriticalSection
```
