# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,ushort const *,void *,_GUID const *)

- ea: `0x18001f374`
- end: `0x18001f439`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEBGPEAXPEBU_GUID@@@Z`
- size: `197`
- prototype: `int(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, unsigned int, const unsigned __int16 *, void *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001f16c`

## callees

- `0x18001f374`
- `0x18001f870`
- `0x1800207e8`
- `0x18003d810`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18001f3ea`
- `ntdll!EtwEventWrite` at `0x18001f3ea`
- `ntdll!EtwEventEnabled` at `0x18001f3ab`
- `ntdll!EtwEventEnabled` at `0x18001f3ab`

## string_xrefs

- `0x18001f413`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        int a3,
        const unsigned __int16 *a4)
{
  __int64 v6; // rcx
  unsigned int v7; // eax
  EventManager *v8; // rcx
  int v9; // ebx
  _QWORD v11[2]; // [rsp+20h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-28h] BYREF
  int v13; // [rsp+70h] [rbp+18h] BYREF

  v13 = a3;
  v6 = *(_QWORD *)this;
  if ( !v6 )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(v6, MSCHED_MAINTENANCE_STATE_CHANGED) )
    return 0;
  v11[1] = 4;
  v11[0] = &v13;
  CreateDataDescriptor(&v12, a4);
  v7 = EtwEventWrite(*(_QWORD *)this, MSCHED_MAINTENANCE_STATE_CHANGED, 2, v11);
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
0x18001f374  mov     [rsp+arg_8], rbx
0x18001f379  mov     [rsp+arg_10], r8d
0x18001f37e  push    rdi
0x18001f37f  sub     rsp, 50h
0x18001f383  mov     rax, cs:__security_cookie
0x18001f38a  xor     rax, rsp
0x18001f38d  mov     [rsp+58h+var_18], rax
0x18001f392  mov     rbx, rcx
0x18001f395  mov     rdi, r9
0x18001f398  mov     rcx, [rcx]
0x18001f39b  test    rcx, rcx
0x18001f39e  jz      loc_18001F427
0x18001f3a4  lea     rdx, MSCHED_MAINTENANCE_STATE_CHANGED
0x18001f3ab  call    cs:__imp_EtwEventEnabled
0x18001f3b1  test    al, al
0x18001f3b3  jz      short loc_18001F3F6
0x18001f3b5  lea     rax, [rsp+58h+arg_10]
0x18001f3ba  mov     [rsp+58h+var_30], 4
0x18001f3c3  mov     rdx, rdi; unsigned __int16 *
0x18001f3c6  mov     [rsp+58h+var_38], rax
0x18001f3cb  lea     rcx, [rsp+58h+var_28]; struct _EVENT_DATA_DESCRIPTOR *
0x18001f3d0  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x18001f3d5  mov     rcx, [rbx]
0x18001f3d8  lea     rdx, MSCHED_MAINTENANCE_STATE_CHANGED
0x18001f3df  lea     r9, [rsp+58h+var_38]
0x18001f3e4  mov     r8d, 2
0x18001f3ea  call    cs:__imp_EtwEventWrite
0x18001f3f0  mov     ebx, eax
0x18001f3f2  test    eax, eax
0x18001f3f4  jnz     short loc_18001F410
0x18001f3f6  xor     eax, eax
0x18001f3f8  mov     rcx, [rsp+58h+var_18]
0x18001f3fd  xor     rcx, rsp; StackCookie
0x18001f400  call    __security_check_cookie
0x18001f405  mov     rbx, [rsp+58h+arg_8]
0x18001f40a  add     rsp, 50h
0x18001f40e  pop     rdi
0x18001f40f  retn
0x18001f410  mov     r8d, ebx; unsigned int
0x18001f413  lea     rdx, aEventwriteErro; "EventWrite error"
0x18001f41a  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18001f41f  test    ebx, ebx
0x18001f421  jg      short loc_18001F42E
0x18001f423  mov     eax, ebx
0x18001f425  jmp     short loc_18001F3F8
0x18001f427  mov     eax, 1
0x18001f42c  jmp     short loc_18001F3F8
0x18001f42e  movzx   ebx, bx
0x18001f431  or      ebx, 80070000h
0x18001f437  jmp     short loc_18001F423
```
