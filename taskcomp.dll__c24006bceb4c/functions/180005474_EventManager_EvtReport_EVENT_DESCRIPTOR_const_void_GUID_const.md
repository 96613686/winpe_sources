# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,void *,_GUID const *)

- ea: `0x180005474`
- end: `0x1800054e3`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAXPEBU_GUID@@@Z`
- size: `111`
- prototype: `__int64 __fastcall(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, void *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180010efc`

## callees

- `0x180005474`
- `0x18000567c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800054af`
- `ntdll!EtwEventWrite` at `0x1800054af`
- `ntdll!EtwEventEnabled` at `0x180005495`
- `ntdll!EtwEventEnabled` at `0x180005495`

## string_xrefs

- `0x1800054be`: `EventWrite error`

## pseudocode

```c

```

## disassembly

```asm
0x180005474  push    rbx
0x180005476  sub     rsp, 20h
0x18000547a  mov     rbx, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x180005481  mov     rcx, [rbx]
0x180005484  test    rcx, rcx
0x180005487  jnz     short loc_18000548E
0x180005489  lea     eax, [rcx+1]
0x18000548c  jmp     short loc_1800054DD
0x18000548e  lea     rdx, COMPAT_START
0x180005495  call    cs:__imp_EtwEventEnabled
0x18000549b  test    al, al
0x18000549d  jz      short loc_1800054DB
0x18000549f  mov     rcx, [rbx]
0x1800054a2  lea     rdx, COMPAT_START
0x1800054a9  xor     r9d, r9d
0x1800054ac  xor     r8d, r8d
0x1800054af  call    cs:__imp_EtwEventWrite
0x1800054b5  mov     ebx, eax
0x1800054b7  test    eax, eax
0x1800054b9  jz      short loc_1800054DB
0x1800054bb  mov     r8d, eax; unsigned int
0x1800054be  lea     rdx, aEventwriteErro; "EventWrite error"
0x1800054c5  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x1800054ca  test    ebx, ebx
0x1800054cc  jle     short loc_1800054D7
0x1800054ce  movzx   ebx, bx
0x1800054d1  or      ebx, 80070000h
0x1800054d7  mov     eax, ebx
0x1800054d9  jmp     short loc_1800054DD
0x1800054db  xor     eax, eax
0x1800054dd  add     rsp, 20h
0x1800054e1  pop     rbx
0x1800054e2  retn
```
