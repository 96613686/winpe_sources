# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,void *,_GUID const *)

- ea: `0x18001f468`
- end: `0x18001f51a`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBG1PEAXPEBU_GUID@@@Z`
- size: `178`
- prototype: `int(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const unsigned __int16 *, void *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001f440`

## callees

- `0x18001f468`
- `0x18001f870`
- `0x1800207e8`
- `0x18003d810`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18001f4d0`
- `ntdll!EtwEventWrite` at `0x18001f4d0`
- `ntdll!EtwEventEnabled` at `0x18001f497`
- `ntdll!EtwEventEnabled` at `0x18001f497`

## string_xrefs

- `0x18001f4fd`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v6; // rcx
  unsigned int v8; // eax
  EventManager *v9; // rcx
  int v10; // ebx
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+20h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+30h] [rbp-38h] BYREF

  v6 = *(_QWORD *)this;
  if ( !v6 )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(v6, NO_START_USER_NOT_LOGGED_ON) )
    return 0;
  CreateDataDescriptor(&v12, a3);
  CreateDataDescriptor(&v13, a4);
  v8 = EtwEventWrite(*(_QWORD *)this, NO_START_USER_NOT_LOGGED_ON, 2, &v12);
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
0x18001f468  push    rbx
0x18001f46a  push    rsi
0x18001f46b  push    rdi
0x18001f46c  sub     rsp, 50h
0x18001f470  mov     rax, cs:__security_cookie
0x18001f477  xor     rax, rsp
0x18001f47a  mov     [rsp+68h+var_28], rax
0x18001f47f  mov     rbx, rcx
0x18001f482  mov     rsi, r9
0x18001f485  mov     rcx, [rcx]
0x18001f488  mov     rdi, r8
0x18001f48b  test    rcx, rcx
0x18001f48e  jz      short loc_18001F4F3
0x18001f490  lea     rdx, NO_START_USER_NOT_LOGGED_ON
0x18001f497  call    cs:__imp_EtwEventEnabled
0x18001f49d  test    al, al
0x18001f49f  jz      short loc_18001F4DC
0x18001f4a1  mov     rdx, rdi; unsigned __int16 *
0x18001f4a4  lea     rcx, [rsp+68h+var_48]; struct _EVENT_DATA_DESCRIPTOR *
0x18001f4a9  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x18001f4ae  mov     rdx, rsi; unsigned __int16 *
0x18001f4b1  lea     rcx, [rsp+68h+var_38]; struct _EVENT_DATA_DESCRIPTOR *
0x18001f4b6  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x18001f4bb  mov     rcx, [rbx]
0x18001f4be  lea     rdx, NO_START_USER_NOT_LOGGED_ON
0x18001f4c5  lea     r9, [rsp+68h+var_48]
0x18001f4ca  mov     r8d, 2
0x18001f4d0  call    cs:__imp_EtwEventWrite
0x18001f4d6  mov     ebx, eax
0x18001f4d8  test    eax, eax
0x18001f4da  jnz     short loc_18001F4FA
0x18001f4dc  xor     eax, eax
0x18001f4de  mov     rcx, [rsp+68h+var_28]
0x18001f4e3  xor     rcx, rsp; StackCookie
0x18001f4e6  call    __security_check_cookie
0x18001f4eb  add     rsp, 50h
0x18001f4ef  pop     rdi
0x18001f4f0  pop     rsi
0x18001f4f1  pop     rbx
0x18001f4f2  retn
0x18001f4f3  mov     eax, 1
0x18001f4f8  jmp     short loc_18001F4DE
0x18001f4fa  mov     r8d, ebx; unsigned int
0x18001f4fd  lea     rdx, aEventwriteErro; "EventWrite error"
0x18001f504  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18001f509  test    ebx, ebx
0x18001f50b  jle     short loc_18001F516
0x18001f50d  movzx   ebx, bx
0x18001f510  or      ebx, 80070000h
0x18001f516  mov     eax, ebx
0x18001f518  jmp     short loc_18001F4DE
```
