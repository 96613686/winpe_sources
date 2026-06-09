# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,void *,_GUID const *)

- ea: `0x18001f560`
- end: `0x18001f5fa`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGPEAXPEBU_GUID@@@Z`
- size: `154`
- prototype: `int(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, void *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180006650`
- `0x18001f520`

## callees

- `0x18001f560`
- `0x18001f870`
- `0x1800207e8`
- `0x18003d810`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18001f5b0`
- `ntdll!EtwEventWrite` at `0x18001f5b0`
- `ntdll!EtwEventEnabled` at `0x18001f588`
- `ntdll!EtwEventEnabled` at `0x18001f588`

## string_xrefs

- `0x18001f5dd`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        const unsigned __int16 *a3,
        void *a4)
{
  __int64 v6; // rcx
  unsigned int v8; // eax
  EventManager *v9; // rcx
  int v10; // ebx
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+20h] [rbp-38h] BYREF

  v6 = *(_QWORD *)this;
  if ( !v6 )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(v6, a2) )
    return 0;
  CreateDataDescriptor(&v12, a3);
  v8 = EtwEventWrite(*(_QWORD *)this, a2, 1, &v12);
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
0x18001f560  push    rbx
0x18001f562  push    rsi
0x18001f563  push    rdi
0x18001f564  sub     rsp, 40h
0x18001f568  mov     rax, cs:__security_cookie
0x18001f56f  xor     rax, rsp
0x18001f572  mov     [rsp+58h+var_28], rax
0x18001f577  mov     rdi, rcx
0x18001f57a  mov     rsi, r8
0x18001f57d  mov     rcx, [rcx]
0x18001f580  mov     rbx, rdx
0x18001f583  test    rcx, rcx
0x18001f586  jz      short loc_18001F5D3
0x18001f588  call    cs:__imp_EtwEventEnabled
0x18001f58e  test    al, al
0x18001f590  jz      short loc_18001F5BC
0x18001f592  mov     rdx, rsi; unsigned __int16 *
0x18001f595  lea     rcx, [rsp+58h+var_38]; struct _EVENT_DATA_DESCRIPTOR *
0x18001f59a  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x18001f59f  mov     rcx, [rdi]
0x18001f5a2  lea     r9, [rsp+58h+var_38]
0x18001f5a7  mov     rdx, rbx
0x18001f5aa  mov     r8d, 1
0x18001f5b0  call    cs:__imp_EtwEventWrite
0x18001f5b6  mov     ebx, eax
0x18001f5b8  test    eax, eax
0x18001f5ba  jnz     short loc_18001F5DA
0x18001f5bc  xor     eax, eax
0x18001f5be  mov     rcx, [rsp+58h+var_28]
0x18001f5c3  xor     rcx, rsp; StackCookie
0x18001f5c6  call    __security_check_cookie
0x18001f5cb  add     rsp, 40h
0x18001f5cf  pop     rdi
0x18001f5d0  pop     rsi
0x18001f5d1  pop     rbx
0x18001f5d2  retn
0x18001f5d3  mov     eax, 1
0x18001f5d8  jmp     short loc_18001F5BE
0x18001f5da  mov     r8d, ebx; unsigned int
0x18001f5dd  lea     rdx, aEventwriteErro; "EventWrite error"
0x18001f5e4  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18001f5e9  test    ebx, ebx
0x18001f5eb  jle     short loc_18001F5F6
0x18001f5ed  movzx   ebx, bx
0x18001f5f0  or      ebx, 80070000h
0x18001f5f6  mov     eax, ebx
0x18001f5f8  jmp     short loc_18001F5BE
```
