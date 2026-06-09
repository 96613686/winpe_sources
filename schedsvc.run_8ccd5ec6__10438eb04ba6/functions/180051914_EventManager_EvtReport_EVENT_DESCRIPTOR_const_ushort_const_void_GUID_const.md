# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,void *,_GUID const *)

- ea: `0x180051914`
- end: `0x1800519cc`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGPEAXPEBU_GUID@@@Z`
- size: `184`
- prototype: `int(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, void *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002dd30`
- `0x180078ffc`

## callees

- `0x1800447d0`
- `0x180051914`
- `0x180052888`
- `0x180082a40`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18005194c`
- `ntdll!EtwEventEnabled` at `0x18005194c`
- `ntdll!EtwEventWrite` at `0x18005197a`
- `ntdll!EtwEventWrite` at `0x18005197a`

## string_xrefs

- `0x18005198f`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        const unsigned __int16 *a3,
        void *a4)
{
  EventManager *v4; // rdi
  unsigned int v8; // eax
  EventManager *v9; // rcx
  int v10; // ebx
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+20h] [rbp-28h] BYREF

  v4 = g_pEventManager;
  if ( !*(_QWORD *)g_pEventManager )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(*(_QWORD *)g_pEventManager, a2) )
    return 0;
  CreateDataDescriptor(&v11, a3);
  v8 = EtwEventWrite(*(_QWORD *)v4, a2, 1, &v11);
  v10 = v8;
  if ( !v8 )
    return 0;
  EventManager::LogIt(v9, L"EventWrite error", v8);
  if ( v10 > 0 )
    return (unsigned __int16)v10 | 0x80070000;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180051914  mov     [rsp+arg_0], rbx
0x180051919  mov     [rsp+arg_18], rsi
0x18005191e  push    rdi
0x18005191f  sub     rsp, 40h
0x180051923  mov     rax, cs:__security_cookie
0x18005192a  xor     rax, rsp
0x18005192d  mov     [rsp+48h+var_18], rax
0x180051932  mov     rdi, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x180051939  mov     rsi, r8
0x18005193c  mov     rbx, rdx
0x18005193f  mov     rcx, [rdi]
0x180051942  test    rcx, rcx
0x180051945  jnz     short loc_18005194C
0x180051947  lea     eax, [rcx+1]
0x18005194a  jmp     short loc_1800519AE
0x18005194c  call    cs:__imp_EtwEventEnabled
0x180051953  nop     dword ptr [rax+rax+00h]
0x180051958  test    al, al
0x18005195a  jz      short loc_1800519AC
0x18005195c  mov     rdx, rsi; unsigned __int16 *
0x18005195f  lea     rcx, [rsp+48h+var_28]; struct _EVENT_DATA_DESCRIPTOR *
0x180051964  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x180051969  mov     rcx, [rdi]
0x18005196c  lea     r9, [rsp+48h+var_28]
0x180051971  mov     rdx, rbx
0x180051974  mov     r8d, 1
0x18005197a  call    cs:__imp_EtwEventWrite
0x180051981  nop     dword ptr [rax+rax+00h]
0x180051986  mov     ebx, eax
0x180051988  test    eax, eax
0x18005198a  jz      short loc_1800519AC
0x18005198c  mov     r8d, eax; unsigned int
0x18005198f  lea     rdx, aEventwriteErro; "EventWrite error"
0x180051996  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18005199b  test    ebx, ebx
0x18005199d  jle     short loc_1800519A8
0x18005199f  movzx   ebx, bx
0x1800519a2  or      ebx, 80070000h
0x1800519a8  mov     eax, ebx
0x1800519aa  jmp     short loc_1800519AE
0x1800519ac  xor     eax, eax
0x1800519ae  mov     rcx, [rsp+48h+var_18]
0x1800519b3  xor     rcx, rsp; StackCookie
0x1800519b6  call    __security_check_cookie
0x1800519bb  mov     rbx, [rsp+48h+arg_0]
0x1800519c0  mov     rsi, [rsp+48h+arg_18]
0x1800519c5  add     rsp, 40h
0x1800519c9  pop     rdi
0x1800519ca  retn
```
