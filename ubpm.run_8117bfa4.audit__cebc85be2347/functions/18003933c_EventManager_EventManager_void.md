# EventManager::~EventManager(void)

- ea: `0x18003933c`
- end: `0x180039375`
- name: `??1EventManager@@QEAA@XZ`
- size: `57`
- prototype: `void __fastcall(EventManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180039314`

## callees

- `0x18003933c`

## import_xrefs

- `ntdll!EtwEventUnregister` at `0x18003934d`
- `ntdll!EtwEventUnregister` at `0x18003934d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180039369`

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
0x18003933c  push    rbx
0x18003933e  sub     rsp, 20h
0x180039342  mov     rbx, rcx
0x180039345  mov     rcx, [rcx]
0x180039348  test    rcx, rcx
0x18003934b  jz      short loc_180039360
0x18003934d  call    cs:__imp_EtwEventUnregister
0x180039354  nop     dword ptr [rax+rax+00h]
0x180039359  mov     qword ptr [rbx], 0
0x180039360  lea     rcx, [rbx+8]
0x180039364  add     rsp, 20h
0x180039368  pop     rbx
0x180039369  jmp     cs:__imp_DeleteCriticalSection
```
