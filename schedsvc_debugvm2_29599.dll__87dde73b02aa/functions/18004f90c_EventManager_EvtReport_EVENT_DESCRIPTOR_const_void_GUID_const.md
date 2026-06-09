# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,void *,_GUID const *)

- ea: `0x18004f90c`
- end: `0x18004f97c`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAXPEBU_GUID@@@Z`
- size: `112`
- prototype: `__int64 __fastcall(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, void *, const struct _GUID *)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180038890`
- `0x180059bf8`
- `0x180059cf0`
- `0x18005ab10`
- `0x18005ab30`
- `0x180074200`

## callees

- `0x18004f90c`
- `0x18004ff54`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18004f92d`
- `ntdll!EtwEventEnabled` at `0x18004f92d`
- `ntdll!EtwEventWrite` at `0x18004f943`
- `ntdll!EtwEventWrite` at `0x18004f943`

## string_xrefs

- `0x18004f952`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        void *a3,
        const struct _GUID *a4)
{
  EventManager *v4; // rdi
  unsigned int v7; // eax
  EventManager *v8; // rcx
  int v9; // ebx

  v4 = g_pEventManager;
  if ( !*(_QWORD *)g_pEventManager )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(*(_QWORD *)g_pEventManager, a2) )
    return 0;
  v7 = EtwEventWrite(*(_QWORD *)v4, a2, 0, 0);
  v9 = v7;
  if ( !v7 )
    return 0;
  EventManager::LogIt(v8, L"EventWrite error", v7);
  if ( v9 > 0 )
    return (unsigned __int16)v9 | 0x80070000;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18004f90c  mov     [rsp+arg_0], rbx
0x18004f911  push    rdi
0x18004f912  sub     rsp, 20h
0x18004f916  mov     rdi, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x18004f91d  mov     rbx, rdx
0x18004f920  mov     rcx, [rdi]
0x18004f923  test    rcx, rcx
0x18004f926  jnz     short loc_18004F92D
0x18004f928  lea     eax, [rcx+1]
0x18004f92b  jmp     short loc_18004F971
0x18004f92d  call    cs:__imp_EtwEventEnabled
0x18004f933  test    al, al
0x18004f935  jz      short loc_18004F96F
0x18004f937  mov     rcx, [rdi]
0x18004f93a  xor     r9d, r9d
0x18004f93d  xor     r8d, r8d
0x18004f940  mov     rdx, rbx
0x18004f943  call    cs:__imp_EtwEventWrite
0x18004f949  mov     ebx, eax
0x18004f94b  test    eax, eax
0x18004f94d  jz      short loc_18004F96F
0x18004f94f  mov     r8d, eax; unsigned int
0x18004f952  lea     rdx, aEventwriteErro; "EventWrite error"
0x18004f959  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18004f95e  test    ebx, ebx
0x18004f960  jle     short loc_18004F96B
0x18004f962  movzx   ebx, bx
0x18004f965  or      ebx, 80070000h
0x18004f96b  mov     eax, ebx
0x18004f96d  jmp     short loc_18004F971
0x18004f96f  xor     eax, eax
0x18004f971  mov     rbx, [rsp+28h+arg_0]
0x18004f976  add     rsp, 20h
0x18004f97a  pop     rdi
0x18004f97b  retn
```
