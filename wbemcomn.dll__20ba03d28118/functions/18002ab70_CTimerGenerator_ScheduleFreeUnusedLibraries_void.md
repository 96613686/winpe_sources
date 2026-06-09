# CTimerGenerator::ScheduleFreeUnusedLibraries(void)

- ea: `0x18002ab70`
- end: `0x18002abae`
- name: `?ScheduleFreeUnusedLibraries@CTimerGenerator@@QEAAXXZ`
- size: `62`
- prototype: `void __fastcall(CTimerGenerator *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002ab70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002ab82`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002ab82`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002ab99`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002ab99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002aba7`

## pseudocode

```c
void __fastcall CTimerGenerator::ScheduleFreeUnusedLibraries(CTimerGenerator *this)
{
  HANDLE v1; // rax
  void *v2; // rbx

  v1 = OpenEventW(2u, 0, L"Global\\WINMGMT_PROVIDER_CANSHUTDOWN");
  v2 = v1;
  if ( v1 )
  {
    SetEvent(v1);
    CloseHandle(v2);
  }
}

```

## disassembly

```asm
0x18002ab70  push    rbx
0x18002ab72  sub     rsp, 20h
0x18002ab76  xor     edx, edx; bInheritHandle
0x18002ab78  lea     r8, Name; "Global\\WINMGMT_PROVIDER_CANSHUTDOWN"
0x18002ab7f  lea     ecx, [rdx+2]; dwDesiredAccess
0x18002ab82  call    cs:__imp_OpenEventW
0x18002ab88  mov     rbx, rax
0x18002ab8b  test    rax, rax
0x18002ab8e  jnz     short loc_18002AB96
0x18002ab90  add     rsp, 20h
0x18002ab94  pop     rbx
0x18002ab95  retn
0x18002ab96  mov     rcx, rbx; hEvent
0x18002ab99  call    cs:__imp_SetEvent
0x18002ab9f  mov     rcx, rbx
0x18002aba2  add     rsp, 20h
0x18002aba6  pop     rbx
0x18002aba7  jmp     cs:__imp_CloseHandle
```
