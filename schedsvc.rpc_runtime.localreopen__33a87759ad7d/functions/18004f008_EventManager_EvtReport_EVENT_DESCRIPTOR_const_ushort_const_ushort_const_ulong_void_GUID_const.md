# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ulong,void *,_GUID const *)

- ea: `0x18004f008`
- end: `0x18004f0d6`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBG1KPEAXPEBU_GUID@@@Z`
- size: `206`
- prototype: `int(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, void *, const struct _GUID *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180049f00`
- `0x18006c840`
- `0x18006eae0`

## callees

- `0x180042530`
- `0x18004f008`
- `0x18004ff54`
- `0x18007e6d0`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18004f040`
- `ntdll!EtwEventEnabled` at `0x18004f040`
- `ntdll!EtwEventWrite` at `0x18004f08b`
- `ntdll!EtwEventWrite` at `0x18004f08b`

## string_xrefs

- `0x18004f09a`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5)
{
  EventManager *v5; // rdi
  unsigned int v10; // eax
  EventManager *v11; // rcx
  int v12; // ebx
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+20h] [rbp-58h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+30h] [rbp-48h] BYREF
  unsigned int *v15; // [rsp+40h] [rbp-38h]
  __int64 v16; // [rsp+48h] [rbp-30h]

  v5 = g_pEventManager;
  if ( !*(_QWORD *)g_pEventManager )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(*(_QWORD *)g_pEventManager, a2) )
    return 0;
  CreateDataDescriptor(&v13, a3);
  CreateDataDescriptor(&v14, a4);
  v16 = 4;
  v15 = &a5;
  v10 = EtwEventWrite(*(_QWORD *)v5, a2, 3, &v13);
  v12 = v10;
  if ( !v10 )
    return 0;
  EventManager::LogIt(v11, L"EventWrite error", v10);
  if ( v12 > 0 )
    return (unsigned __int16)v12 | 0x80070000;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18004f008  mov     [rsp+arg_0], rbx
0x18004f00d  push    rbp
0x18004f00e  push    rsi
0x18004f00f  push    rdi
0x18004f010  sub     rsp, 60h
0x18004f014  mov     rax, cs:__security_cookie
0x18004f01b  xor     rax, rsp
0x18004f01e  mov     [rsp+78h+var_28], rax
0x18004f023  mov     rdi, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x18004f02a  mov     rbp, r9
0x18004f02d  mov     rsi, r8
0x18004f030  mov     rbx, rdx
0x18004f033  mov     rcx, [rdi]
0x18004f036  test    rcx, rcx
0x18004f039  jnz     short loc_18004F040
0x18004f03b  lea     eax, [rcx+1]
0x18004f03e  jmp     short loc_18004F0B9
0x18004f040  call    cs:__imp_EtwEventEnabled
0x18004f046  test    al, al
0x18004f048  jz      short loc_18004F0B7
0x18004f04a  mov     rdx, rsi; unsigned __int16 *
0x18004f04d  lea     rcx, [rsp+78h+var_58]; struct _EVENT_DATA_DESCRIPTOR *
0x18004f052  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x18004f057  mov     rdx, rbp; unsigned __int16 *
0x18004f05a  lea     rcx, [rsp+78h+var_48]; struct _EVENT_DATA_DESCRIPTOR *
0x18004f05f  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x18004f064  lea     rcx, [rsp+78h+arg_20]
0x18004f06c  mov     [rsp+78h+var_30], 4
0x18004f075  mov     [rsp+78h+var_38], rcx
0x18004f07a  lea     r9, [rsp+78h+var_58]
0x18004f07f  mov     rcx, [rdi]
0x18004f082  mov     r8d, 3
0x18004f088  mov     rdx, rbx
0x18004f08b  call    cs:__imp_EtwEventWrite
0x18004f091  mov     ebx, eax
0x18004f093  test    eax, eax
0x18004f095  jz      short loc_18004F0B7
0x18004f097  mov     r8d, eax; unsigned int
0x18004f09a  lea     rdx, aEventwriteErro; "EventWrite error"
0x18004f0a1  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18004f0a6  test    ebx, ebx
0x18004f0a8  jle     short loc_18004F0B3
0x18004f0aa  movzx   ebx, bx
0x18004f0ad  or      ebx, 80070000h
0x18004f0b3  mov     eax, ebx
0x18004f0b5  jmp     short loc_18004F0B9
0x18004f0b7  xor     eax, eax
0x18004f0b9  mov     rcx, [rsp+78h+var_28]
0x18004f0be  xor     rcx, rsp; StackCookie
0x18004f0c1  call    __security_check_cookie
0x18004f0c6  mov     rbx, [rsp+78h+arg_0]
0x18004f0ce  add     rsp, 60h
0x18004f0d2  pop     rdi
0x18004f0d3  pop     rsi
0x18004f0d4  pop     rbp
0x18004f0d5  retn
```
