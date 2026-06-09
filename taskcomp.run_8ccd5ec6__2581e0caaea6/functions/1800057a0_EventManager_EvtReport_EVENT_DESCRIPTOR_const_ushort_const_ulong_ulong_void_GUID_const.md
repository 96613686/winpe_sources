# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,ulong,void *,_GUID const *)

- ea: `0x1800057a0`
- end: `0x18000588e`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKKPEAXPEBU_GUID@@@Z`
- size: `238`
- prototype: `int(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, unsigned int, unsigned int, void *, const struct _GUID *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800111e0`
- `0x180012594`
- `0x180013a80`

## callees

- `0x1800057a0`
- `0x18000594c`
- `0x1800196d8`
- `0x180030700`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180005841`
- `ntdll!EtwEventWrite` at `0x180005841`
- `ntdll!EtwEventEnabled` at `0x1800057df`
- `ntdll!EtwEventEnabled` at `0x1800057df`

## string_xrefs

- `0x180005856`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        const unsigned __int16 *a3,
        int a4,
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
  if ( !(unsigned __int8)EtwEventEnabled(*(_QWORD *)g_pEventManager, COMPAT_TASK_STATUS_UPDATE_FAILED) )
    return 0;
  CreateDataDescriptor(&v12, a3);
  v14 = 4;
  v13 = &v17;
  v8 = *(_QWORD *)v5;
  v15 = &a5;
  v16 = 4;
  v9 = EtwEventWrite(v8, COMPAT_TASK_STATUS_UPDATE_FAILED, 3, &v12);
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
0x1800057a0  mov     [rsp+arg_0], rbx
0x1800057a5  mov     [rsp+arg_18], r9d
0x1800057aa  push    rdi
0x1800057ab  sub     rsp, 60h
0x1800057af  mov     rax, cs:__security_cookie
0x1800057b6  xor     rax, rsp
0x1800057b9  mov     [rsp+68h+var_18], rax
0x1800057be  mov     rbx, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x1800057c5  mov     rdi, r8
0x1800057c8  mov     rcx, [rbx]
0x1800057cb  test    rcx, rcx
0x1800057ce  jnz     short loc_1800057D8
0x1800057d0  lea     eax, [rcx+1]
0x1800057d3  jmp     loc_180005875
0x1800057d8  lea     rdx, COMPAT_TASK_STATUS_UPDATE_FAILED
0x1800057df  call    cs:__imp_EtwEventEnabled
0x1800057e6  nop     dword ptr [rax+rax+00h]
0x1800057eb  test    al, al
0x1800057ed  jz      loc_180005873
0x1800057f3  mov     rdx, rdi; unsigned __int16 *
0x1800057f6  lea     rcx, [rsp+68h+var_48]; struct _EVENT_DATA_DESCRIPTOR *
0x1800057fb  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x180005800  lea     rcx, [rsp+68h+arg_18]
0x180005808  mov     [rsp+68h+var_30], 4
0x180005811  mov     [rsp+68h+var_38], rcx
0x180005816  lea     rax, [rsp+68h+arg_20]
0x18000581e  mov     rcx, [rbx]
0x180005821  lea     r9, [rsp+68h+var_48]
0x180005826  mov     r8d, 3
0x18000582c  mov     [rsp+68h+var_28], rax
0x180005831  lea     rdx, COMPAT_TASK_STATUS_UPDATE_FAILED
0x180005838  mov     [rsp+68h+var_20], 4
0x180005841  call    cs:__imp_EtwEventWrite
0x180005848  nop     dword ptr [rax+rax+00h]
0x18000584d  mov     ebx, eax
0x18000584f  test    eax, eax
0x180005851  jz      short loc_180005873
0x180005853  mov     r8d, eax; unsigned int
0x180005856  lea     rdx, aEventwriteErro; "EventWrite error"
0x18000585d  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x180005862  test    ebx, ebx
0x180005864  jle     short loc_18000586F
0x180005866  movzx   ebx, bx
0x180005869  or      ebx, 80070000h
0x18000586f  mov     eax, ebx
0x180005871  jmp     short loc_180005875
0x180005873  xor     eax, eax
0x180005875  mov     rcx, [rsp+68h+var_18]
0x18000587a  xor     rcx, rsp; StackCookie
0x18000587d  call    __security_check_cookie
0x180005882  mov     rbx, [rsp+68h+arg_0]
0x180005887  add     rsp, 60h
0x18000588b  pop     rdi
0x18000588c  retn
```
