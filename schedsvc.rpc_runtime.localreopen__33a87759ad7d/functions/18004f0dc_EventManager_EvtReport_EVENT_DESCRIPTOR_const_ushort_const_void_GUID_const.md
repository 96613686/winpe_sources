# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,void *,_GUID const *)

- ea: `0x18004f0dc`
- end: `0x18004f187`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGPEAXPEBU_GUID@@@Z`
- size: `171`
- prototype: `int(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, void *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800329cc`
- `0x1800750c0`

## callees

- `0x180042530`
- `0x18004f0dc`
- `0x18004ff54`
- `0x18007e6d0`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18004f114`
- `ntdll!EtwEventEnabled` at `0x18004f114`
- `ntdll!EtwEventWrite` at `0x18004f13c`
- `ntdll!EtwEventWrite` at `0x18004f13c`

## string_xrefs

- `0x18004f14b`: `EventWrite error`

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
0x18004f0dc  mov     [rsp+arg_0], rbx
0x18004f0e1  mov     [rsp+arg_18], rsi
0x18004f0e6  push    rdi
0x18004f0e7  sub     rsp, 40h
0x18004f0eb  mov     rax, cs:__security_cookie
0x18004f0f2  xor     rax, rsp
0x18004f0f5  mov     [rsp+48h+var_18], rax
0x18004f0fa  mov     rdi, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x18004f101  mov     rsi, r8
0x18004f104  mov     rbx, rdx
0x18004f107  mov     rcx, [rdi]
0x18004f10a  test    rcx, rcx
0x18004f10d  jnz     short loc_18004F114
0x18004f10f  lea     eax, [rcx+1]
0x18004f112  jmp     short loc_18004F16A
0x18004f114  call    cs:__imp_EtwEventEnabled
0x18004f11a  test    al, al
0x18004f11c  jz      short loc_18004F168
0x18004f11e  mov     rdx, rsi; unsigned __int16 *
0x18004f121  lea     rcx, [rsp+48h+var_28]; struct _EVENT_DATA_DESCRIPTOR *
0x18004f126  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x18004f12b  mov     rcx, [rdi]
0x18004f12e  lea     r9, [rsp+48h+var_28]
0x18004f133  mov     rdx, rbx
0x18004f136  mov     r8d, 1
0x18004f13c  call    cs:__imp_EtwEventWrite
0x18004f142  mov     ebx, eax
0x18004f144  test    eax, eax
0x18004f146  jz      short loc_18004F168
0x18004f148  mov     r8d, eax; unsigned int
0x18004f14b  lea     rdx, aEventwriteErro; "EventWrite error"
0x18004f152  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18004f157  test    ebx, ebx
0x18004f159  jle     short loc_18004F164
0x18004f15b  movzx   ebx, bx
0x18004f15e  or      ebx, 80070000h
0x18004f164  mov     eax, ebx
0x18004f166  jmp     short loc_18004F16A
0x18004f168  xor     eax, eax
0x18004f16a  mov     rcx, [rsp+48h+var_18]
0x18004f16f  xor     rcx, rsp; StackCookie
0x18004f172  call    __security_check_cookie
0x18004f177  mov     rbx, [rsp+48h+arg_0]
0x18004f17c  mov     rsi, [rsp+48h+arg_18]
0x18004f181  add     rsp, 40h
0x18004f185  pop     rdi
0x18004f186  retn
```
