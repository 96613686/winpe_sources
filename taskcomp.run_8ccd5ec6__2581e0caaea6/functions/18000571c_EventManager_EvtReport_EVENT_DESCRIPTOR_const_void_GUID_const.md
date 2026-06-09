# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,void *,_GUID const *)

- ea: `0x18000571c`
- end: `0x180005798`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAXPEBU_GUID@@@Z`
- size: `124`
- prototype: `__int64 __fastcall(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, void *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011958`

## callees

- `0x18000571c`
- `0x18000594c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000575d`
- `ntdll!EtwEventWrite` at `0x18000575d`
- `ntdll!EtwEventEnabled` at `0x18000573d`
- `ntdll!EtwEventEnabled` at `0x18000573d`

## string_xrefs

- `0x180005772`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        void *a3,
        const struct _GUID *a4)
{
  EventManager *v4; // rbx
  unsigned int v6; // eax
  EventManager *v7; // rcx
  int v8; // ebx

  v4 = g_pEventManager;
  if ( !*(_QWORD *)g_pEventManager )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(*(_QWORD *)g_pEventManager, COMPAT_START) )
    return 0;
  v6 = EtwEventWrite(*(_QWORD *)v4, COMPAT_START, 0, 0);
  v8 = v6;
  if ( !v6 )
    return 0;
  EventManager::LogIt(v7, L"EventWrite error", v6);
  if ( v8 > 0 )
    return (unsigned __int16)v8 | 0x80070000;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000571c  push    rbx
0x18000571e  sub     rsp, 20h
0x180005722  mov     rbx, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x180005729  mov     rcx, [rbx]
0x18000572c  test    rcx, rcx
0x18000572f  jnz     short loc_180005736
0x180005731  lea     eax, [rcx+1]
0x180005734  jmp     short loc_180005791
0x180005736  lea     rdx, COMPAT_START
0x18000573d  call    cs:__imp_EtwEventEnabled
0x180005744  nop     dword ptr [rax+rax+00h]
0x180005749  test    al, al
0x18000574b  jz      short loc_18000578F
0x18000574d  mov     rcx, [rbx]
0x180005750  lea     rdx, COMPAT_START
0x180005757  xor     r9d, r9d
0x18000575a  xor     r8d, r8d
0x18000575d  call    cs:__imp_EtwEventWrite
0x180005764  nop     dword ptr [rax+rax+00h]
0x180005769  mov     ebx, eax
0x18000576b  test    eax, eax
0x18000576d  jz      short loc_18000578F
0x18000576f  mov     r8d, eax; unsigned int
0x180005772  lea     rdx, aEventwriteErro; "EventWrite error"
0x180005779  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18000577e  test    ebx, ebx
0x180005780  jle     short loc_18000578B
0x180005782  movzx   ebx, bx
0x180005785  or      ebx, 80070000h
0x18000578b  mov     eax, ebx
0x18000578d  jmp     short loc_180005791
0x18000578f  xor     eax, eax
0x180005791  add     rsp, 20h
0x180005795  pop     rbx
0x180005796  retn
```
