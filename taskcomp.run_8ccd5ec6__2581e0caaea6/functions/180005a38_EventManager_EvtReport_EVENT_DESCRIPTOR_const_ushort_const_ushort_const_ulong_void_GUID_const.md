# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ulong,void *,_GUID const *)

- ea: `0x180005a38`
- end: `0x180005b21`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBG1KPEAXPEBU_GUID@@@Z`
- size: `233`
- prototype: `int(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, void *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800130c0`

## callees

- `0x18000594c`
- `0x180005a38`
- `0x1800196d8`
- `0x180030700`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180005acf`
- `ntdll!EtwEventWrite` at `0x180005acf`
- `ntdll!EtwEventEnabled` at `0x180005a7a`
- `ntdll!EtwEventEnabled` at `0x180005a7a`

## string_xrefs

- `0x180005ae4`: `EventWrite error`

## pseudocode

```c
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
  if ( !(unsigned __int8)EtwEventEnabled(*(_QWORD *)g_pEventManager, COMPAT_TASK_SET_SD_FAILED) )
    return 0;
  CreateDataDescriptor(&v12, a3);
  CreateDataDescriptor(&v13, a4);
  v15 = 4;
  v14 = &a5;
  v9 = EtwEventWrite(*(_QWORD *)v5, COMPAT_TASK_SET_SD_FAILED, 3, &v12);
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
0x180005a38  mov     [rsp+arg_0], rbx
0x180005a3d  mov     [rsp+arg_8], rsi
0x180005a42  push    rdi
0x180005a43  sub     rsp, 60h
0x180005a47  mov     rax, cs:__security_cookie
0x180005a4e  xor     rax, rsp
0x180005a51  mov     [rsp+68h+var_18], rax
0x180005a56  mov     rbx, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x180005a5d  mov     rsi, r9
0x180005a60  mov     rdi, r8
0x180005a63  mov     rcx, [rbx]
0x180005a66  test    rcx, rcx
0x180005a69  jnz     short loc_180005A73
0x180005a6b  lea     eax, [rcx+1]
0x180005a6e  jmp     loc_180005B03
0x180005a73  lea     rdx, COMPAT_TASK_SET_SD_FAILED
0x180005a7a  call    cs:__imp_EtwEventEnabled
0x180005a81  nop     dword ptr [rax+rax+00h]
0x180005a86  test    al, al
0x180005a88  jz      short loc_180005B01
0x180005a8a  mov     rdx, rdi; unsigned __int16 *
0x180005a8d  lea     rcx, [rsp+68h+var_48]; struct _EVENT_DATA_DESCRIPTOR *
0x180005a92  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x180005a97  mov     rdx, rsi; unsigned __int16 *
0x180005a9a  lea     rcx, [rsp+68h+var_38]; struct _EVENT_DATA_DESCRIPTOR *
0x180005a9f  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x180005aa4  lea     rcx, [rsp+68h+arg_20]
0x180005aac  mov     [rsp+68h+var_20], 4
0x180005ab5  mov     [rsp+68h+var_28], rcx
0x180005aba  lea     r9, [rsp+68h+var_48]
0x180005abf  mov     rcx, [rbx]
0x180005ac2  lea     rdx, COMPAT_TASK_SET_SD_FAILED
0x180005ac9  mov     r8d, 3
0x180005acf  call    cs:__imp_EtwEventWrite
0x180005ad6  nop     dword ptr [rax+rax+00h]
0x180005adb  mov     ebx, eax
0x180005add  test    eax, eax
0x180005adf  jz      short loc_180005B01
0x180005ae1  mov     r8d, eax; unsigned int
0x180005ae4  lea     rdx, aEventwriteErro; "EventWrite error"
0x180005aeb  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x180005af0  test    ebx, ebx
0x180005af2  jle     short loc_180005AFD
0x180005af4  movzx   ebx, bx
0x180005af7  or      ebx, 80070000h
0x180005afd  mov     eax, ebx
0x180005aff  jmp     short loc_180005B03
0x180005b01  xor     eax, eax
0x180005b03  mov     rcx, [rsp+68h+var_18]
0x180005b08  xor     rcx, rsp; StackCookie
0x180005b0b  call    __security_check_cookie
0x180005b10  mov     rbx, [rsp+68h+arg_0]
0x180005b15  mov     rsi, [rsp+68h+arg_8]
0x180005b1a  add     rsp, 60h
0x180005b1e  pop     rdi
0x180005b1f  retn
```
