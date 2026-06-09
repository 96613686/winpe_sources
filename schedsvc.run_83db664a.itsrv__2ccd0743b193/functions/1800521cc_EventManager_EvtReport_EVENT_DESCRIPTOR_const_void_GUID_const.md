# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,void *,_GUID const *)

- ea: `0x1800521cc`
- end: `0x180052249`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAXPEBU_GUID@@@Z`
- size: `125`
- prototype: `__int64 __fastcall(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, void *, const struct _GUID *)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002e520`
- `0x18005c550`
- `0x18005c660`
- `0x18005d6b0`
- `0x18005d6d0`
- `0x180077f90`

## callees

- `0x1800521cc`
- `0x180052888`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x1800521ed`
- `ntdll!EtwEventEnabled` at `0x1800521ed`
- `ntdll!EtwEventWrite` at `0x180052209`
- `ntdll!EtwEventWrite` at `0x180052209`

## string_xrefs

- `0x18005221e`: `EventWrite error`

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
0x1800521cc  mov     [rsp+arg_0], rbx
0x1800521d1  push    rdi
0x1800521d2  sub     rsp, 20h
0x1800521d6  mov     rdi, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x1800521dd  mov     rbx, rdx
0x1800521e0  mov     rcx, [rdi]
0x1800521e3  test    rcx, rcx
0x1800521e6  jnz     short loc_1800521ED
0x1800521e8  lea     eax, [rcx+1]
0x1800521eb  jmp     short loc_18005223D
0x1800521ed  call    cs:__imp_EtwEventEnabled
0x1800521f4  nop     dword ptr [rax+rax+00h]
0x1800521f9  test    al, al
0x1800521fb  jz      short loc_18005223B
0x1800521fd  mov     rcx, [rdi]
0x180052200  xor     r9d, r9d
0x180052203  xor     r8d, r8d
0x180052206  mov     rdx, rbx
0x180052209  call    cs:__imp_EtwEventWrite
0x180052210  nop     dword ptr [rax+rax+00h]
0x180052215  mov     ebx, eax
0x180052217  test    eax, eax
0x180052219  jz      short loc_18005223B
0x18005221b  mov     r8d, eax; unsigned int
0x18005221e  lea     rdx, aEventwriteErro; "EventWrite error"
0x180052225  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18005222a  test    ebx, ebx
0x18005222c  jle     short loc_180052237
0x18005222e  movzx   ebx, bx
0x180052231  or      ebx, 80070000h
0x180052237  mov     eax, ebx
0x180052239  jmp     short loc_18005223D
0x18005223b  xor     eax, eax
0x18005223d  mov     rbx, [rsp+28h+arg_0]
0x180052242  add     rsp, 20h
0x180052246  pop     rdi
0x180052247  retn
```
