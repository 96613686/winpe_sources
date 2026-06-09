# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,ulong,ulong,void *,_GUID const *)

- ea: `0x18004fdcc`
- end: `0x18004fea2`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KKKPEAXPEBU_GUID@@@Z`
- size: `214`
- prototype: `__int64 __fastcall(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, unsigned int, unsigned int, char, void *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180073118`

## callees

- `0x18004fdcc`
- `0x18004ff54`
- `0x18007e6d0`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18004fe0f`
- `ntdll!EtwEventEnabled` at `0x18004fe0f`
- `ntdll!EtwEventWrite` at `0x18004fe5d`
- `ntdll!EtwEventWrite` at `0x18004fe5d`

## string_xrefs

- `0x18004fe6c`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        int a3,
        int a4,
        char a5)
{
  EventManager *v5; // rbx
  __int64 v7; // rcx
  unsigned int v8; // eax
  EventManager *v9; // rcx
  int v10; // ebx
  _QWORD v11[6]; // [rsp+20h] [rbp-40h] BYREF
  int v12; // [rsp+80h] [rbp+20h] BYREF
  int v13; // [rsp+88h] [rbp+28h] BYREF

  v13 = a4;
  v12 = a3;
  v5 = g_pEventManager;
  if ( !*(_QWORD *)g_pEventManager )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(*(_QWORD *)g_pEventManager, ItSpEvt_PerfTrack_IdleEntryStats) )
    return 0;
  v7 = *(_QWORD *)v5;
  v11[0] = &v12;
  v11[1] = 4;
  v11[2] = &v13;
  v11[3] = 4;
  v11[4] = &a5;
  v11[5] = 4;
  v8 = EtwEventWrite(v7, ItSpEvt_PerfTrack_IdleEntryStats, 3, v11);
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
0x18004fdcc  mov     [rsp-8+arg_0], rbx
0x18004fdd1  mov     [rsp-8+arg_18], r9d
0x18004fdd6  mov     [rsp-8+arg_10], r8d
0x18004fddb  push    rbp
0x18004fddc  mov     rbp, rsp
0x18004fddf  sub     rsp, 60h
0x18004fde3  mov     rax, cs:__security_cookie
0x18004fdea  xor     rax, rsp
0x18004fded  mov     [rbp+var_10], rax
0x18004fdf1  mov     rbx, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x18004fdf8  mov     rcx, [rbx]
0x18004fdfb  test    rcx, rcx
0x18004fdfe  jnz     short loc_18004FE08
0x18004fe00  lea     eax, [rcx+1]
0x18004fe03  jmp     loc_18004FE8B
0x18004fe08  lea     rdx, ItSpEvt_PerfTrack_IdleEntryStats
0x18004fe0f  call    cs:__imp_EtwEventEnabled
0x18004fe15  test    al, al
0x18004fe17  jz      short loc_18004FE89
0x18004fe19  mov     rcx, [rbx]
0x18004fe1c  lea     rax, [rbp+arg_10]
0x18004fe20  mov     [rbp+var_40], rax
0x18004fe24  lea     r9, [rbp+var_40]
0x18004fe28  lea     rax, [rbp+arg_18]
0x18004fe2c  mov     [rbp+var_38], 4
0x18004fe34  mov     [rbp+var_30], rax
0x18004fe38  lea     rdx, ItSpEvt_PerfTrack_IdleEntryStats
0x18004fe3f  lea     rax, [rbp+arg_20]
0x18004fe43  mov     [rbp+var_28], 4
0x18004fe4b  mov     r8d, 3
0x18004fe51  mov     [rbp+var_20], rax
0x18004fe55  mov     [rbp+var_18], 4
0x18004fe5d  call    cs:__imp_EtwEventWrite
0x18004fe63  mov     ebx, eax
0x18004fe65  test    eax, eax
0x18004fe67  jz      short loc_18004FE89
0x18004fe69  mov     r8d, eax; unsigned int
0x18004fe6c  lea     rdx, aEventwriteErro; "EventWrite error"
0x18004fe73  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18004fe78  test    ebx, ebx
0x18004fe7a  jle     short loc_18004FE85
0x18004fe7c  movzx   ebx, bx
0x18004fe7f  or      ebx, 80070000h
0x18004fe85  mov     eax, ebx
0x18004fe87  jmp     short loc_18004FE8B
0x18004fe89  xor     eax, eax
0x18004fe8b  mov     rcx, [rbp+var_10]
0x18004fe8f  xor     rcx, rsp; StackCookie
0x18004fe92  call    __security_check_cookie
0x18004fe97  mov     rbx, [rsp+60h+arg_0]
0x18004fe9c  add     rsp, 60h
0x18004fea0  pop     rbp
0x18004fea1  retn
```
