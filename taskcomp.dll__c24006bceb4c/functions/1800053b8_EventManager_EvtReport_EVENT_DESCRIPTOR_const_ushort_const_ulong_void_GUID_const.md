# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)

- ea: `0x1800053b8`
- end: `0x18000546e`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z`
- size: `182`
- prototype: `__int64 __fastcall(EventManager *this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, __int64)`
- caller_count: `7`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180003500`
- `0x180004820`
- `0x180009afc`
- `0x180010750`
- `0x180010bd0`
- `0x180015280`
- `0x1800157e0`

## callees

- `0x1800053b8`
- `0x18000567c`
- `0x180018550`
- `0x18002e5b0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000542b`
- `ntdll!EtwEventWrite` at `0x18000542b`
- `ntdll!EtwEventEnabled` at `0x1800053ed`
- `ntdll!EtwEventEnabled` at `0x1800053ed`

## string_xrefs

- `0x18000543a`: `EventWrite error`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        const unsigned __int16 *a3,
        __int64 a4)
{
  EventManager *v4; // rdi
  unsigned int v8; // eax
  EventManager *v9; // rcx
  int v10; // ebx
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+20h] [rbp-48h] BYREF
  int *v12; // [rsp+30h] [rbp-38h]
  __int64 v13; // [rsp+38h] [rbp-30h]
  int v14; // [rsp+88h] [rbp+20h] BYREF

  v14 = a4;
  v4 = g_pEventManager;
  if ( !*(_QWORD *)g_pEventManager )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(*(_QWORD *)g_pEventManager, a2, a3, a4) )
    return 0;
  CreateDataDescriptor(&v11, a3);
  v13 = 4;
  v12 = &v14;
  v8 = ((__int64 (__fastcall *)(_QWORD, const struct _EVENT_DESCRIPTOR *, __int64, struct _EVENT_DATA_DESCRIPTOR *))EtwEventWrite)(
         *(_QWORD *)v4,
         a2,
         2,
         &v11);
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
0x1800053b8  mov     [rsp+arg_18], r9d
0x1800053bd  push    rbx
0x1800053be  push    rsi
0x1800053bf  push    rdi
0x1800053c0  sub     rsp, 50h
0x1800053c4  mov     rax, cs:__security_cookie
0x1800053cb  xor     rax, rsp
0x1800053ce  mov     [rsp+68h+var_28], rax
0x1800053d3  mov     rdi, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x1800053da  mov     rsi, r8
0x1800053dd  mov     rbx, rdx
0x1800053e0  mov     rcx, [rdi]
0x1800053e3  test    rcx, rcx
0x1800053e6  jnz     short loc_1800053ED
0x1800053e8  lea     eax, [rcx+1]
0x1800053eb  jmp     short loc_180005459
0x1800053ed  call    cs:__imp_EtwEventEnabled
0x1800053f3  test    al, al
0x1800053f5  jz      short loc_180005457
0x1800053f7  mov     rdx, rsi; unsigned __int16 *
0x1800053fa  lea     rcx, [rsp+68h+var_48]; struct _EVENT_DATA_DESCRIPTOR *
0x1800053ff  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x180005404  lea     rcx, [rsp+68h+arg_18]
0x18000540c  mov     [rsp+68h+var_30], 4
0x180005415  mov     [rsp+68h+var_38], rcx
0x18000541a  lea     r9, [rsp+68h+var_48]
0x18000541f  mov     rcx, [rdi]
0x180005422  mov     r8d, 2
0x180005428  mov     rdx, rbx
0x18000542b  call    cs:__imp_EtwEventWrite
0x180005431  mov     ebx, eax
0x180005433  test    eax, eax
0x180005435  jz      short loc_180005457
0x180005437  mov     r8d, eax; unsigned int
0x18000543a  lea     rdx, aEventwriteErro; "EventWrite error"
0x180005441  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x180005446  test    ebx, ebx
0x180005448  jle     short loc_180005453
0x18000544a  movzx   ebx, bx
0x18000544d  or      ebx, 80070000h
0x180005453  mov     eax, ebx
0x180005455  jmp     short loc_180005459
0x180005457  xor     eax, eax
0x180005459  mov     rcx, [rsp+68h+var_28]
0x18000545e  xor     rcx, rsp; StackCookie
0x180005461  call    __security_check_cookie
0x180005466  add     rsp, 50h
0x18000546a  pop     rdi
0x18000546b  pop     rsi
0x18000546c  pop     rbx
0x18000546d  retn
```
