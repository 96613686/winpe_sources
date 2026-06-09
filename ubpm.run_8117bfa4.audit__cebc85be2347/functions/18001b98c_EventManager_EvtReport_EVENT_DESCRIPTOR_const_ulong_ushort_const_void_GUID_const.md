# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,ushort const *,void *,_GUID const *)

- ea: `0x18001b98c`
- end: `0x18001ba5e`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEBGPEAXPEBU_GUID@@@Z`
- size: `210`
- prototype: `int(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, unsigned int, const unsigned __int16 *, void *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001b74c`

## callees

- `0x18001b98c`
- `0x18001bdf0`
- `0x18001d0ec`
- `0x180040260`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18001ba08`
- `ntdll!EtwEventWrite` at `0x18001ba08`
- `ntdll!EtwEventEnabled` at `0x18001b9c3`
- `ntdll!EtwEventEnabled` at `0x18001b9c3`

## string_xrefs

- `0x18001ba38`: `EventWrite error`

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
0x18001b98c  mov     [rsp+arg_8], rbx
0x18001b991  mov     [rsp+arg_10], r8d
0x18001b996  push    rdi
0x18001b997  sub     rsp, 50h
0x18001b99b  mov     rax, cs:__security_cookie
0x18001b9a2  xor     rax, rsp
0x18001b9a5  mov     [rsp+58h+var_18], rax
0x18001b9aa  mov     rbx, rcx
0x18001b9ad  mov     rdi, r9
0x18001b9b0  mov     rcx, [rcx]
0x18001b9b3  test    rcx, rcx
0x18001b9b6  jz      loc_18001BA4C
0x18001b9bc  lea     rdx, MSCHED_MAINTENANCE_STATE_CHANGED
0x18001b9c3  call    cs:__imp_EtwEventEnabled
0x18001b9ca  nop     dword ptr [rax+rax+00h]
0x18001b9cf  test    al, al
0x18001b9d1  jz      short loc_18001BA1A
0x18001b9d3  lea     rax, [rsp+58h+arg_10]
0x18001b9d8  mov     [rsp+58h+var_30], 4
0x18001b9e1  mov     rdx, rdi; unsigned __int16 *
0x18001b9e4  mov     [rsp+58h+var_38], rax
0x18001b9e9  lea     rcx, [rsp+58h+var_28]; struct _EVENT_DATA_DESCRIPTOR *
0x18001b9ee  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x18001b9f3  mov     rcx, [rbx]
0x18001b9f6  lea     rdx, MSCHED_MAINTENANCE_STATE_CHANGED
0x18001b9fd  lea     r9, [rsp+58h+var_38]
0x18001ba02  mov     r8d, 2
0x18001ba08  call    cs:__imp_EtwEventWrite
0x18001ba0f  nop     dword ptr [rax+rax+00h]
0x18001ba14  mov     ebx, eax
0x18001ba16  test    eax, eax
0x18001ba18  jnz     short loc_18001BA35
0x18001ba1a  xor     eax, eax
0x18001ba1c  mov     rcx, [rsp+58h+var_18]
0x18001ba21  xor     rcx, rsp; StackCookie
0x18001ba24  call    __security_check_cookie
0x18001ba29  mov     rbx, [rsp+58h+arg_8]
0x18001ba2e  add     rsp, 50h
0x18001ba32  pop     rdi
0x18001ba33  retn
0x18001ba35  mov     r8d, ebx; unsigned int
0x18001ba38  lea     rdx, aEventwriteErro; "EventWrite error"
0x18001ba3f  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18001ba44  test    ebx, ebx
0x18001ba46  jg      short loc_18001BA53
0x18001ba48  mov     eax, ebx
0x18001ba4a  jmp     short loc_18001BA1C
0x18001ba4c  mov     eax, 1
0x18001ba51  jmp     short loc_18001BA1C
0x18001ba53  movzx   ebx, bx
0x18001ba56  or      ebx, 80070000h
0x18001ba5c  jmp     short loc_18001BA48
```
