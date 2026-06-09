# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ulong,void *,_GUID const *)

- ea: `0x180005750`
- end: `0x18000582c`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBG1KPEAXPEBU_GUID@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(EventManager *this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180012560`

## callees

- `0x18000567c`
- `0x180005750`
- `0x180018550`
- `0x18002e5b0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800057e1`
- `ntdll!EtwEventWrite` at `0x1800057e1`
- `ntdll!EtwEventEnabled` at `0x180005792`
- `ntdll!EtwEventEnabled` at `0x180005792`

## string_xrefs

- `0x1800057f0`: `EventWrite error`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5)
{
  EventManager *v5; // rbx
  unsigned int v9; // eax
  EventManager *v10; // rcx
  int v11; // ebx
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+20h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+30h] [rbp-38h] BYREF
  unsigned int *v14; // [rsp+40h] [rbp-28h]
  __int64 v15; // [rsp+48h] [rbp-20h]

  v5 = g_pEventManager;
  if ( !*(_QWORD *)g_pEventManager )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(*(_QWORD *)g_pEventManager, COMPAT_TASK_SET_SD_FAILED, a3, a4) )
    return 0;
  CreateDataDescriptor(&v12, a3);
  CreateDataDescriptor(&v13, a4);
  v15 = 4;
  v14 = &a5;
  v9 = ((__int64 (__fastcall *)(_QWORD, __int64 *, __int64, struct _EVENT_DATA_DESCRIPTOR *))EtwEventWrite)(
         *(_QWORD *)v5,
         COMPAT_TASK_SET_SD_FAILED,
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
0x180005750  mov     [rsp+arg_0], rbx
0x180005755  mov     [rsp+arg_8], rsi
0x18000575a  push    rdi
0x18000575b  sub     rsp, 60h
0x18000575f  mov     rax, cs:__security_cookie
0x180005766  xor     rax, rsp
0x180005769  mov     [rsp+68h+var_18], rax
0x18000576e  mov     rbx, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x180005775  mov     rsi, r9
0x180005778  mov     rdi, r8
0x18000577b  mov     rcx, [rbx]
0x18000577e  test    rcx, rcx
0x180005781  jnz     short loc_18000578B
0x180005783  lea     eax, [rcx+1]
0x180005786  jmp     loc_18000580F
0x18000578b  lea     rdx, COMPAT_TASK_SET_SD_FAILED
0x180005792  call    cs:__imp_EtwEventEnabled
0x180005798  test    al, al
0x18000579a  jz      short loc_18000580D
0x18000579c  mov     rdx, rdi; unsigned __int16 *
0x18000579f  lea     rcx, [rsp+68h+var_48]; struct _EVENT_DATA_DESCRIPTOR *
0x1800057a4  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x1800057a9  mov     rdx, rsi; unsigned __int16 *
0x1800057ac  lea     rcx, [rsp+68h+var_38]; struct _EVENT_DATA_DESCRIPTOR *
0x1800057b1  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x1800057b6  lea     rcx, [rsp+68h+arg_20]
0x1800057be  mov     [rsp+68h+var_20], 4
0x1800057c7  mov     [rsp+68h+var_28], rcx
0x1800057cc  lea     r9, [rsp+68h+var_48]
0x1800057d1  mov     rcx, [rbx]
0x1800057d4  lea     rdx, COMPAT_TASK_SET_SD_FAILED
0x1800057db  mov     r8d, 3
0x1800057e1  call    cs:__imp_EtwEventWrite
0x1800057e7  mov     ebx, eax
0x1800057e9  test    eax, eax
0x1800057eb  jz      short loc_18000580D
0x1800057ed  mov     r8d, eax; unsigned int
0x1800057f0  lea     rdx, aEventwriteErro; "EventWrite error"
0x1800057f7  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x1800057fc  test    ebx, ebx
0x1800057fe  jle     short loc_180005809
0x180005800  movzx   ebx, bx
0x180005803  or      ebx, 80070000h
0x180005809  mov     eax, ebx
0x18000580b  jmp     short loc_18000580F
0x18000580d  xor     eax, eax
0x18000580f  mov     rcx, [rsp+68h+var_18]
0x180005814  xor     rcx, rsp; StackCookie
0x180005817  call    __security_check_cookie
0x18000581c  mov     rbx, [rsp+68h+arg_0]
0x180005821  mov     rsi, [rsp+68h+arg_8]
0x180005826  add     rsp, 60h
0x18000582a  pop     rdi
0x18000582b  retn
```
