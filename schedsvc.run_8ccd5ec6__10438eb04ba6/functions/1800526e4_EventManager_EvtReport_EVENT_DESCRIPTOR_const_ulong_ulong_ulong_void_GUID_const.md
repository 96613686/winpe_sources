# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,ulong,ulong,void *,_GUID const *)

- ea: `0x1800526e4`
- end: `0x1800527c7`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KKKPEAXPEBU_GUID@@@Z`
- size: `227`
- prototype: `__int64 __fastcall(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, unsigned int, unsigned int, char, void *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180076c7c`

## callees

- `0x1800526e4`
- `0x180052888`
- `0x180082a40`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180052727`
- `ntdll!EtwEventEnabled` at `0x180052727`
- `ntdll!EtwEventWrite` at `0x18005277b`
- `ntdll!EtwEventWrite` at `0x18005277b`

## string_xrefs

- `0x180052790`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        int a3,
        int a4,
        char a5)
{
  EventManager *v5; // rbx
  __int64 v7; // rcx
  unsigned int v8; // eax
  EventManager *v9; // rcx
  int v10; // ebx
  _QWORD v11[6]; // [rsp+20h] [rbp-40h] BYREF
  int v12; // [rsp+80h] [rbp+20h] BYREF
  int v13; // [rsp+88h] [rbp+28h] BYREF

  v13 = a4;
  v12 = a3;
  v5 = g_pEventManager;
  if ( !*(_QWORD *)g_pEventManager )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(*(_QWORD *)g_pEventManager, ItSpEvt_PerfTrack_IdleEntryStats) )
    return 0;
  v7 = *(_QWORD *)v5;
  v11[0] = &v12;
  v11[1] = 4;
  v11[2] = &v13;
  v11[3] = 4;
  v11[4] = &a5;
  v11[5] = 4;
  v8 = EtwEventWrite(v7, ItSpEvt_PerfTrack_IdleEntryStats, 3, v11);
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
0x1800526e4  mov     [rsp-8+arg_0], rbx
0x1800526e9  mov     [rsp-8+arg_18], r9d
0x1800526ee  mov     [rsp-8+arg_10], r8d
0x1800526f3  push    rbp
0x1800526f4  mov     rbp, rsp
0x1800526f7  sub     rsp, 60h
0x1800526fb  mov     rax, cs:__security_cookie
0x180052702  xor     rax, rsp
0x180052705  mov     [rbp+var_10], rax
0x180052709  mov     rbx, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x180052710  mov     rcx, [rbx]
0x180052713  test    rcx, rcx
0x180052716  jnz     short loc_180052720
0x180052718  lea     eax, [rcx+1]
0x18005271b  jmp     loc_1800527AF
0x180052720  lea     rdx, ItSpEvt_PerfTrack_IdleEntryStats
0x180052727  call    cs:__imp_EtwEventEnabled
0x18005272e  nop     dword ptr [rax+rax+00h]
0x180052733  test    al, al
0x180052735  jz      short loc_1800527AD
0x180052737  mov     rcx, [rbx]
0x18005273a  lea     rax, [rbp+arg_10]
0x18005273e  mov     [rbp+var_40], rax
0x180052742  lea     r9, [rbp+var_40]
0x180052746  lea     rax, [rbp+arg_18]
0x18005274a  mov     [rbp+var_38], 4
0x180052752  mov     [rbp+var_30], rax
0x180052756  lea     rdx, ItSpEvt_PerfTrack_IdleEntryStats
0x18005275d  lea     rax, [rbp+arg_20]
0x180052761  mov     [rbp+var_28], 4
0x180052769  mov     r8d, 3
0x18005276f  mov     [rbp+var_20], rax
0x180052773  mov     [rbp+var_18], 4
0x18005277b  call    cs:__imp_EtwEventWrite
0x180052782  nop     dword ptr [rax+rax+00h]
0x180052787  mov     ebx, eax
0x180052789  test    eax, eax
0x18005278b  jz      short loc_1800527AD
0x18005278d  mov     r8d, eax; unsigned int
0x180052790  lea     rdx, aEventwriteErro; "EventWrite error"
0x180052797  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18005279c  test    ebx, ebx
0x18005279e  jle     short loc_1800527A9
0x1800527a0  movzx   ebx, bx
0x1800527a3  or      ebx, 80070000h
0x1800527a9  mov     eax, ebx
0x1800527ab  jmp     short loc_1800527AF
0x1800527ad  xor     eax, eax
0x1800527af  mov     rcx, [rbp+var_10]
0x1800527b3  xor     rcx, rsp; StackCookie
0x1800527b6  call    __security_check_cookie
0x1800527bb  mov     rbx, [rsp+60h+arg_0]
0x1800527c0  add     rsp, 60h
0x1800527c4  pop     rbp
0x1800527c5  retn
```
