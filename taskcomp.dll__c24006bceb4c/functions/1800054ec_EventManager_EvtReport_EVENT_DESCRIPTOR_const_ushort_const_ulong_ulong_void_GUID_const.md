# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,ulong,void *,_GUID const *)

- ea: `0x1800054ec`
- end: `0x1800055c9`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKKPEAXPEBU_GUID@@@Z`
- size: `221`
- prototype: `__int64 __fastcall(EventManager *this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180010750`
- `0x180011a98`
- `0x180012ea0`

## callees

- `0x1800054ec`
- `0x18000567c`
- `0x180018550`
- `0x18002e5b0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180005583`
- `ntdll!EtwEventWrite` at `0x180005583`
- `ntdll!EtwEventEnabled` at `0x18000552b`
- `ntdll!EtwEventEnabled` at `0x18000552b`

## string_xrefs

- `0x180005592`: `EventWrite error`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned int a5)
{
  EventManager *v5; // rbx
  __int64 v8; // rcx
  unsigned int v9; // eax
  EventManager *v10; // rcx
  int v11; // ebx
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+20h] [rbp-48h] BYREF
  int *v13; // [rsp+30h] [rbp-38h]
  __int64 v14; // [rsp+38h] [rbp-30h]
  unsigned int *v15; // [rsp+40h] [rbp-28h]
  __int64 v16; // [rsp+48h] [rbp-20h]
  int v17; // [rsp+88h] [rbp+20h] BYREF

  v17 = a4;
  v5 = g_pEventManager;
  if ( !*(_QWORD *)g_pEventManager )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(*(_QWORD *)g_pEventManager, COMPAT_TASK_STATUS_UPDATE_FAILED, a3, a4) )
    return 0;
  CreateDataDescriptor(&v12, a3);
  v14 = 4;
  v13 = &v17;
  v8 = *(_QWORD *)v5;
  v15 = &a5;
  v16 = 4;
  v9 = ((__int64 (__fastcall *)(__int64, __int64 *, __int64, struct _EVENT_DATA_DESCRIPTOR *))EtwEventWrite)(
         v8,
         COMPAT_TASK_STATUS_UPDATE_FAILED,
         3,
         &v12);
  v11 = v9;
  if ( !v9 )
    return 0;
  EventManager::LogIt(v10, L"EventWrite error", v9);
  if ( v11 > 0 )
    return (unsigned __int16)v11 | 0x80070000;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800054ec  mov     [rsp+arg_0], rbx
0x1800054f1  mov     [rsp+arg_18], r9d
0x1800054f6  push    rdi
0x1800054f7  sub     rsp, 60h
0x1800054fb  mov     rax, cs:__security_cookie
0x180005502  xor     rax, rsp
0x180005505  mov     [rsp+68h+var_18], rax
0x18000550a  mov     rbx, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x180005511  mov     rdi, r8
0x180005514  mov     rcx, [rbx]
0x180005517  test    rcx, rcx
0x18000551a  jnz     short loc_180005524
0x18000551c  lea     eax, [rcx+1]
0x18000551f  jmp     loc_1800055B1
0x180005524  lea     rdx, COMPAT_TASK_STATUS_UPDATE_FAILED
0x18000552b  call    cs:__imp_EtwEventEnabled
0x180005531  test    al, al
0x180005533  jz      short loc_1800055AF
0x180005535  mov     rdx, rdi; unsigned __int16 *
0x180005538  lea     rcx, [rsp+68h+var_48]; struct _EVENT_DATA_DESCRIPTOR *
0x18000553d  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x180005542  lea     rcx, [rsp+68h+arg_18]
0x18000554a  mov     [rsp+68h+var_30], 4
0x180005553  mov     [rsp+68h+var_38], rcx
0x180005558  lea     rax, [rsp+68h+arg_20]
0x180005560  mov     rcx, [rbx]
0x180005563  lea     r9, [rsp+68h+var_48]
0x180005568  mov     r8d, 3
0x18000556e  mov     [rsp+68h+var_28], rax
0x180005573  lea     rdx, COMPAT_TASK_STATUS_UPDATE_FAILED
0x18000557a  mov     [rsp+68h+var_20], 4
0x180005583  call    cs:__imp_EtwEventWrite
0x180005589  mov     ebx, eax
0x18000558b  test    eax, eax
0x18000558d  jz      short loc_1800055AF
0x18000558f  mov     r8d, eax; unsigned int
0x180005592  lea     rdx, aEventwriteErro; "EventWrite error"
0x180005599  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18000559e  test    ebx, ebx
0x1800055a0  jle     short loc_1800055AB
0x1800055a2  movzx   ebx, bx
0x1800055a5  or      ebx, 80070000h
0x1800055ab  mov     eax, ebx
0x1800055ad  jmp     short loc_1800055B1
0x1800055af  xor     eax, eax
0x1800055b1  mov     rcx, [rsp+68h+var_18]
0x1800055b6  xor     rcx, rsp; StackCookie
0x1800055b9  call    __security_check_cookie
0x1800055be  mov     rbx, [rsp+68h+arg_0]
0x1800055c3  add     rsp, 60h
0x1800055c7  pop     rdi
0x1800055c8  retn
```
