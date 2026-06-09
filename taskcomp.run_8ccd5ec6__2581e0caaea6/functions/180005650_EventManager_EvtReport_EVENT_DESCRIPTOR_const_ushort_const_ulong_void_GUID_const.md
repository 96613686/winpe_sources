# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)

- ea: `0x180005650`
- end: `0x180005713`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z`
- size: `195`
- prototype: `int(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, unsigned int, void *, const struct _GUID *)`
- caller_count: `7`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800036a0`
- `0x180004a40`
- `0x18000a044`
- `0x1800111e0`
- `0x180011600`
- `0x180016040`
- `0x180016620`

## callees

- `0x180005650`
- `0x18000594c`
- `0x1800196d8`
- `0x180030700`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800056c9`
- `ntdll!EtwEventWrite` at `0x1800056c9`
- `ntdll!EtwEventEnabled` at `0x180005685`
- `ntdll!EtwEventEnabled` at `0x180005685`

## string_xrefs

- `0x1800056de`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        const unsigned __int16 *a3,
        int a4)
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
  if ( !(unsigned __int8)EtwEventEnabled() )
    return 0;
  CreateDataDescriptor(&v11, a3);
  v13 = 4;
  v12 = &v14;
  v8 = EtwEventWrite(*(_QWORD *)v4, a2, 2, &v11);
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
0x180005650  mov     [rsp+arg_18], r9d
0x180005655  push    rbx
0x180005656  push    rsi
0x180005657  push    rdi
0x180005658  sub     rsp, 50h
0x18000565c  mov     rax, cs:__security_cookie
0x180005663  xor     rax, rsp
0x180005666  mov     [rsp+68h+var_28], rax
0x18000566b  mov     rdi, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x180005672  mov     rsi, r8
0x180005675  mov     rbx, rdx
0x180005678  mov     rcx, [rdi]
0x18000567b  test    rcx, rcx
0x18000567e  jnz     short loc_180005685
0x180005680  lea     eax, [rcx+1]
0x180005683  jmp     short loc_1800056FD
0x180005685  call    cs:__imp_EtwEventEnabled
0x18000568c  nop     dword ptr [rax+rax+00h]
0x180005691  test    al, al
0x180005693  jz      short loc_1800056FB
0x180005695  mov     rdx, rsi; unsigned __int16 *
0x180005698  lea     rcx, [rsp+68h+var_48]; struct _EVENT_DATA_DESCRIPTOR *
0x18000569d  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x1800056a2  lea     rcx, [rsp+68h+arg_18]
0x1800056aa  mov     [rsp+68h+var_30], 4
0x1800056b3  mov     [rsp+68h+var_38], rcx
0x1800056b8  lea     r9, [rsp+68h+var_48]
0x1800056bd  mov     rcx, [rdi]
0x1800056c0  mov     r8d, 2
0x1800056c6  mov     rdx, rbx
0x1800056c9  call    cs:__imp_EtwEventWrite
0x1800056d0  nop     dword ptr [rax+rax+00h]
0x1800056d5  mov     ebx, eax
0x1800056d7  test    eax, eax
0x1800056d9  jz      short loc_1800056FB
0x1800056db  mov     r8d, eax; unsigned int
0x1800056de  lea     rdx, aEventwriteErro; "EventWrite error"
0x1800056e5  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x1800056ea  test    ebx, ebx
0x1800056ec  jle     short loc_1800056F7
0x1800056ee  movzx   ebx, bx
0x1800056f1  or      ebx, 80070000h
0x1800056f7  mov     eax, ebx
0x1800056f9  jmp     short loc_1800056FD
0x1800056fb  xor     eax, eax
0x1800056fd  mov     rcx, [rsp+68h+var_28]
0x180005702  xor     rcx, rsp; StackCookie
0x180005705  call    __security_check_cookie
0x18000570a  add     rsp, 50h
0x18000570e  pop     rdi
0x18000570f  pop     rsi
0x180005710  pop     rbx
0x180005711  retn
```
