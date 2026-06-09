# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ulong,void *,_GUID const *)

- ea: `0x180051830`
- end: `0x18005190e`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBG1KPEAXPEBU_GUID@@@Z`
- size: `222`
- prototype: `int(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, void *, const struct _GUID *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18004c2b0`
- `0x18006fed4`
- `0x180072244`

## callees

- `0x1800447d0`
- `0x180051830`
- `0x180052888`
- `0x180082a40`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18005186b`
- `ntdll!EtwEventEnabled` at `0x18005186b`
- `ntdll!EtwEventWrite` at `0x1800518bc`
- `ntdll!EtwEventWrite` at `0x1800518bc`

## string_xrefs

- `0x1800518d1`: `EventWrite error`

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
0x180051830  mov     [rsp+arg_0], rbx
0x180051835  push    rbp
0x180051836  push    rsi
0x180051837  push    rdi
0x180051838  sub     rsp, 60h
0x18005183c  mov     rax, cs:__security_cookie
0x180051843  xor     rax, rsp
0x180051846  mov     [rsp+78h+var_28], rax
0x18005184b  mov     rdi, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x180051852  mov     rbp, r9
0x180051855  mov     rsi, r8
0x180051858  mov     rbx, rdx
0x18005185b  mov     rcx, [rdi]
0x18005185e  test    rcx, rcx
0x180051861  jnz     short loc_18005186B
0x180051863  lea     eax, [rcx+1]
0x180051866  jmp     loc_1800518F0
0x18005186b  call    cs:__imp_EtwEventEnabled
0x180051872  nop     dword ptr [rax+rax+00h]
0x180051877  test    al, al
0x180051879  jz      short loc_1800518EE
0x18005187b  mov     rdx, rsi; unsigned __int16 *
0x18005187e  lea     rcx, [rsp+78h+var_58]; struct _EVENT_DATA_DESCRIPTOR *
0x180051883  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x180051888  mov     rdx, rbp; unsigned __int16 *
0x18005188b  lea     rcx, [rsp+78h+var_48]; struct _EVENT_DATA_DESCRIPTOR *
0x180051890  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x180051895  lea     rcx, [rsp+78h+arg_20]
0x18005189d  mov     [rsp+78h+var_30], 4
0x1800518a6  mov     [rsp+78h+var_38], rcx
0x1800518ab  lea     r9, [rsp+78h+var_58]
0x1800518b0  mov     rcx, [rdi]
0x1800518b3  mov     r8d, 3
0x1800518b9  mov     rdx, rbx
0x1800518bc  call    cs:__imp_EtwEventWrite
0x1800518c3  nop     dword ptr [rax+rax+00h]
0x1800518c8  mov     ebx, eax
0x1800518ca  test    eax, eax
0x1800518cc  jz      short loc_1800518EE
0x1800518ce  mov     r8d, eax; unsigned int
0x1800518d1  lea     rdx, aEventwriteErro; "EventWrite error"
0x1800518d8  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x1800518dd  test    ebx, ebx
0x1800518df  jle     short loc_1800518EA
0x1800518e1  movzx   ebx, bx
0x1800518e4  or      ebx, 80070000h
0x1800518ea  mov     eax, ebx
0x1800518ec  jmp     short loc_1800518F0
0x1800518ee  xor     eax, eax
0x1800518f0  mov     rcx, [rsp+78h+var_28]
0x1800518f5  xor     rcx, rsp; StackCookie
0x1800518f8  call    __security_check_cookie
0x1800518fd  mov     rbx, [rsp+78h+arg_0]
0x180051905  add     rsp, 60h
0x180051909  pop     rdi
0x18005190a  pop     rsi
0x18005190b  pop     rbp
0x18005190c  retn
```
