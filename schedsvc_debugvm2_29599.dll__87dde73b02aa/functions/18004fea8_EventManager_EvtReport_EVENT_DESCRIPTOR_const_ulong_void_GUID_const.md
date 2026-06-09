# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,void *,_GUID const *)

- ea: `0x18004fea8`
- end: `0x18004ff4d`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEAXPEBU_GUID@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, unsigned int, void *, const struct _GUID *)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18004f190`
- `0x18005a8ec`
- `0x18006d418`
- `0x18006fbd0`

## callees

- `0x18004fea8`
- `0x18004ff54`
- `0x18007e6d0`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18004fed9`
- `ntdll!EtwEventEnabled` at `0x18004fed9`
- `ntdll!EtwEventWrite` at `0x18004ff07`
- `ntdll!EtwEventWrite` at `0x18004ff07`

## string_xrefs

- `0x18004ff16`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(EventManager *this, const struct _EVENT_DESCRIPTOR *a2, int a3, void *a4)
{
  __int64 v6; // rcx
  __int64 v8; // rcx
  unsigned int v9; // eax
  EventManager *v10; // rcx
  int v11; // ebx
  _QWORD v12[2]; // [rsp+20h] [rbp-28h] BYREF
  int v13; // [rsp+60h] [rbp+18h] BYREF

  v13 = a3;
  v6 = *(_QWORD *)this;
  if ( !v6 )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(v6, a2) )
    return 0;
  v8 = *(_QWORD *)this;
  v12[0] = &v13;
  v12[1] = 4;
  v9 = EtwEventWrite(v8, a2, 1, v12);
  v11 = v9;
  if ( !v9 )
    return 0;
  EventManager::LogIt(v10, L"EventWrite error", v9);
  if ( v11 > 0 )
    return (unsigned __int16)v11 | 0x80070000;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18004fea8  mov     [rsp+arg_18], rbx
0x18004fead  mov     [rsp+arg_10], r8d
0x18004feb2  push    rdi
0x18004feb3  sub     rsp, 40h
0x18004feb7  mov     rax, cs:__security_cookie
0x18004febe  xor     rax, rsp
0x18004fec1  mov     [rsp+48h+var_18], rax
0x18004fec6  mov     rdi, rcx
0x18004fec9  mov     rbx, rdx
0x18004fecc  mov     rcx, [rcx]
0x18004fecf  test    rcx, rcx
0x18004fed2  jnz     short loc_18004FED9
0x18004fed4  lea     eax, [rcx+1]
0x18004fed7  jmp     short loc_18004FF35
0x18004fed9  call    cs:__imp_EtwEventEnabled
0x18004fedf  test    al, al
0x18004fee1  jz      short loc_18004FF33
0x18004fee3  mov     rcx, [rdi]
0x18004fee6  lea     rax, [rsp+48h+arg_10]
0x18004feeb  lea     r9, [rsp+48h+var_28]
0x18004fef0  mov     [rsp+48h+var_28], rax
0x18004fef5  mov     r8d, 1
0x18004fefb  mov     [rsp+48h+var_20], 4
0x18004ff04  mov     rdx, rbx
0x18004ff07  call    cs:__imp_EtwEventWrite
0x18004ff0d  mov     ebx, eax
0x18004ff0f  test    eax, eax
0x18004ff11  jz      short loc_18004FF33
0x18004ff13  mov     r8d, eax; unsigned int
0x18004ff16  lea     rdx, aEventwriteErro; "EventWrite error"
0x18004ff1d  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18004ff22  test    ebx, ebx
0x18004ff24  jle     short loc_18004FF2F
0x18004ff26  movzx   ebx, bx
0x18004ff29  or      ebx, 80070000h
0x18004ff2f  mov     eax, ebx
0x18004ff31  jmp     short loc_18004FF35
0x18004ff33  xor     eax, eax
0x18004ff35  mov     rcx, [rsp+48h+var_18]
0x18004ff3a  xor     rcx, rsp; StackCookie
0x18004ff3d  call    __security_check_cookie
0x18004ff42  mov     rbx, [rsp+48h+arg_18]
0x18004ff47  add     rsp, 40h
0x18004ff4b  pop     rdi
0x18004ff4c  retn
```
