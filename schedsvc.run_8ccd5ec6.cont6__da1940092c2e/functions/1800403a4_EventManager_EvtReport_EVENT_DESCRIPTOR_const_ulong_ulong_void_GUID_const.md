# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,ulong,void *,_GUID const *)

- ea: `0x1800403a4`
- end: `0x180040472`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KKPEAXPEBU_GUID@@@Z`
- size: `206`
- prototype: `__int64 __fastcall(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, unsigned int, unsigned int, void *, const struct _GUID *)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18003ee60`
- `0x18003f9a0`
- `0x18005571c`
- `0x1800763c8`
- `0x180076d40`
- `0x180078170`

## callees

- `0x1800403a4`
- `0x180052888`
- `0x180082a40`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x1800403de`
- `ntdll!EtwEventEnabled` at `0x1800403de`
- `ntdll!EtwEventWrite` at `0x180040425`
- `ntdll!EtwEventWrite` at `0x180040425`

## string_xrefs

- `0x18004043a`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(EventManager *this, const struct _EVENT_DESCRIPTOR *a2, int a3, int a4)
{
  EventManager *v4; // rdi
  __int64 v7; // rcx
  unsigned int v8; // eax
  EventManager *v9; // rcx
  int v10; // ebx
  _QWORD v11[4]; // [rsp+20h] [rbp-38h] BYREF
  int v12; // [rsp+70h] [rbp+18h] BYREF
  int v13; // [rsp+78h] [rbp+20h] BYREF

  v13 = a4;
  v12 = a3;
  v4 = g_pEventManager;
  if ( !*(_QWORD *)g_pEventManager )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(*(_QWORD *)g_pEventManager, a2) )
    return 0;
  v7 = *(_QWORD *)v4;
  v11[0] = &v12;
  v11[1] = 4;
  v11[2] = &v13;
  v11[3] = 4;
  v8 = EtwEventWrite(v7, a2, 2, v11);
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
0x1800403a4  mov     [rsp+arg_0], rbx
0x1800403a9  mov     [rsp+arg_18], r9d
0x1800403ae  mov     [rsp+arg_10], r8d
0x1800403b3  push    rdi
0x1800403b4  sub     rsp, 50h
0x1800403b8  mov     rax, cs:__security_cookie
0x1800403bf  xor     rax, rsp
0x1800403c2  mov     [rsp+58h+var_18], rax
0x1800403c7  mov     rdi, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x1800403ce  mov     rbx, rdx
0x1800403d1  mov     rcx, [rdi]
0x1800403d4  test    rcx, rcx
0x1800403d7  jnz     short loc_1800403DE
0x1800403d9  lea     eax, [rcx+1]
0x1800403dc  jmp     short loc_180040459
0x1800403de  call    cs:__imp_EtwEventEnabled
0x1800403e5  nop     dword ptr [rax+rax+00h]
0x1800403ea  test    al, al
0x1800403ec  jz      short loc_180040457
0x1800403ee  mov     rcx, [rdi]
0x1800403f1  lea     rax, [rsp+58h+arg_10]
0x1800403f6  mov     [rsp+58h+var_38], rax
0x1800403fb  lea     r9, [rsp+58h+var_38]
0x180040400  lea     rax, [rsp+58h+arg_18]
0x180040405  mov     [rsp+58h+var_30], 4
0x18004040e  mov     r8d, 2
0x180040414  mov     [rsp+58h+var_28], rax
0x180040419  mov     rdx, rbx
0x18004041c  mov     [rsp+58h+var_20], 4
0x180040425  call    cs:__imp_EtwEventWrite
0x18004042c  nop     dword ptr [rax+rax+00h]
0x180040431  mov     ebx, eax
0x180040433  test    eax, eax
0x180040435  jz      short loc_180040457
0x180040437  mov     r8d, eax; unsigned int
0x18004043a  lea     rdx, aEventwriteErro; "EventWrite error"
0x180040441  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x180040446  test    ebx, ebx
0x180040448  jle     short loc_180040453
0x18004044a  movzx   ebx, bx
0x18004044d  or      ebx, 80070000h
0x180040453  mov     eax, ebx
0x180040455  jmp     short loc_180040459
0x180040457  xor     eax, eax
0x180040459  mov     rcx, [rsp+58h+var_18]
0x18004045e  xor     rcx, rsp; StackCookie
0x180040461  call    __security_check_cookie
0x180040466  mov     rbx, [rsp+58h+arg_0]
0x18004046b  add     rsp, 50h
0x18004046f  pop     rdi
0x180040470  retn
```
