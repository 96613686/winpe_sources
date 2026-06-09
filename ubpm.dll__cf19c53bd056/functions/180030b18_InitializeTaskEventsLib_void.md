# InitializeTaskEventsLib(void * *)

- ea: `0x180030b18`
- end: `0x180030bdf`
- name: `?InitializeTaskEventsLib@@YAKPEAPEAX@Z`
- size: `199`
- prototype: `unsigned int __fastcall(void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180030ac8`

## callees

- `0x180007460`
- `0x1800207e8`
- `0x180030b18`
- `0x180032678`
- `0x180036cd4`

## import_xrefs

- `ntdll!EtwEventRegister` at `0x180030b63`
- `ntdll!EtwEventRegister` at `0x180030b63`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180030b49`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180030b49`

## string_xrefs

- `0x180030bc5`: `InitializeTaskEventsLib() --> (handle=0x%x, ret=%d)`

## pseudocode

```c
__int64 __fastcall InitializeTaskEventsLib(void **a1)
{
  char *v1; // rax
  EventManager *v2; // rbx
  int v3; // eax
  EventManager *v4; // rcx
  signed int v5; // edi
  unsigned int v6; // edx
  bool v7; // sf
  __int64 v8; // r8
  unsigned int v9; // r8d

  v1 = (char *)operator new(0x30u);
  v2 = (EventManager *)v1;
  if ( !v1 )
  {
    LOWORD(v5) = 14;
    goto LABEL_10;
  }
  *(_QWORD *)v1 = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v1 + 8), 0, 0);
  v3 = EtwEventRegister(TASKSCHED, 0, 0, v2);
  v5 = v3;
  if ( !*(_QWORD *)v2 || v3 )
  {
    EventManager::LogIt(v4, L"EventRegister error", v3);
    *(_QWORD *)v2 = 0;
    v7 = v5 < 0;
    if ( v5 > 0 )
    {
      v5 = (unsigned __int16)v5 | 0x80070000;
      v7 = v5 < 0;
    }
    if ( v7 )
    {
      EventManager::`scalar deleting destructor'(v2, v6);
LABEL_10:
      v2 = g_hTaskEventManager;
      v8 = (unsigned __int16)v5;
      goto LABEL_11;
    }
  }
  v8 = 0;
  g_hTaskEventManager = v2;
LABEL_11:
  TaskEventTrace(L"InitializeTaskEventsLib() --> (handle=0x%x, ret=%d)", v2, v8);
  return v9;
}

```

## disassembly

```asm
0x180030b18  mov     [rsp+arg_8], rbx
0x180030b1d  push    rdi
0x180030b1e  sub     rsp, 20h
0x180030b22  mov     ecx, 30h ; '0'; Size
0x180030b27  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030b2c  mov     [rsp+28h+arg_0], rax
0x180030b31  mov     rbx, rax
0x180030b34  test    rax, rax
0x180030b37  jz      short loc_180030BB2
0x180030b39  lea     rcx, [rax+8]; lpCriticalSection
0x180030b3d  mov     qword ptr [rax], 0
0x180030b44  xor     r8d, r8d; Flags
0x180030b47  xor     edx, edx; dwSpinCount
0x180030b49  call    cs:__imp_InitializeCriticalSectionEx
0x180030b4f  test    rbx, rbx
0x180030b52  jz      short loc_180030BB2
0x180030b54  mov     r9, rbx
0x180030b57  lea     rcx, TASKSCHED
0x180030b5e  xor     r8d, r8d
0x180030b61  xor     edx, edx
0x180030b63  call    cs:__imp_EtwEventRegister
0x180030b69  cmp     qword ptr [rbx], 0
0x180030b6d  mov     edi, eax
0x180030b6f  jz      short loc_180030B75
0x180030b71  test    eax, eax
0x180030b73  jz      short loc_180030B9C
0x180030b75  mov     r8d, edi; unsigned int
0x180030b78  lea     rdx, aEventregisterE; "EventRegister error"
0x180030b7f  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x180030b84  mov     qword ptr [rbx], 0
0x180030b8b  test    edi, edi
0x180030b8d  jle     short loc_180030B9A
0x180030b8f  movzx   edi, di
0x180030b92  or      edi, 80070000h
0x180030b98  test    edi, edi
0x180030b9a  js      short loc_180030BA8
0x180030b9c  xor     r8d, r8d
0x180030b9f  mov     cs:g_hTaskEventManager, rbx
0x180030ba6  jmp     short loc_180030BC2
0x180030ba8  mov     rcx, rbx; this
0x180030bab  call    ??_GEventManager@@QEAAPEAXI@Z; EventManager::`scalar deleting destructor'(uint)
0x180030bb0  jmp     short loc_180030BB7
0x180030bb2  mov     edi, 8007000Eh
0x180030bb7  mov     rbx, cs:g_hTaskEventManager
0x180030bbe  movzx   r8d, di
0x180030bc2  mov     rdx, rbx
0x180030bc5  lea     rcx, aInitializetask; "InitializeTaskEventsLib() --> (handle=0"...
0x180030bcc  call    TaskEventTrace
0x180030bd1  mov     rbx, [rsp+28h+arg_8]
0x180030bd6  mov     eax, r8d
0x180030bd9  add     rsp, 20h
0x180030bdd  pop     rdi
0x180030bde  retn
```
