# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,void *,_GUID const *)

- ea: `0x1800055d0`
- end: `0x180005675`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEAXPEBU_GUID@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(EventManager *this, const struct _EVENT_DESCRIPTOR *, __int64, void *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180010efc`
- `0x180011880`
- `0x180017f74`

## callees

- `0x1800055d0`
- `0x18000567c`
- `0x18002e5b0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000562f`
- `ntdll!EtwEventWrite` at `0x18000562f`
- `ntdll!EtwEventEnabled` at `0x180005601`
- `ntdll!EtwEventEnabled` at `0x180005601`

## string_xrefs

- `0x18000563e`: `EventWrite error`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        __int64 a3,
        void *a4)
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
  if ( !(unsigned __int8)EtwEventEnabled(v6, a2, a3, a4) )
    return 0;
  v8 = *(_QWORD *)this;
  v12[0] = &v13;
  v12[1] = 4;
  v9 = ((__int64 (__fastcall *)(__int64, const struct _EVENT_DESCRIPTOR *, __int64, _QWORD *))EtwEventWrite)(
         v8,
         a2,
         1,
         v12);
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
0x1800055d0  mov     [rsp+arg_18], rbx
0x1800055d5  mov     [rsp+arg_10], r8d
0x1800055da  push    rdi
0x1800055db  sub     rsp, 40h
0x1800055df  mov     rax, cs:__security_cookie
0x1800055e6  xor     rax, rsp
0x1800055e9  mov     [rsp+48h+var_18], rax
0x1800055ee  mov     rdi, rcx
0x1800055f1  mov     rbx, rdx
0x1800055f4  mov     rcx, [rcx]
0x1800055f7  test    rcx, rcx
0x1800055fa  jnz     short loc_180005601
0x1800055fc  lea     eax, [rcx+1]
0x1800055ff  jmp     short loc_18000565D
0x180005601  call    cs:__imp_EtwEventEnabled
0x180005607  test    al, al
0x180005609  jz      short loc_18000565B
0x18000560b  mov     rcx, [rdi]
0x18000560e  lea     rax, [rsp+48h+arg_10]
0x180005613  lea     r9, [rsp+48h+var_28]
0x180005618  mov     [rsp+48h+var_28], rax
0x18000561d  mov     r8d, 1
0x180005623  mov     [rsp+48h+var_20], 4
0x18000562c  mov     rdx, rbx
0x18000562f  call    cs:__imp_EtwEventWrite
0x180005635  mov     ebx, eax
0x180005637  test    eax, eax
0x180005639  jz      short loc_18000565B
0x18000563b  mov     r8d, eax; unsigned int
0x18000563e  lea     rdx, aEventwriteErro; "EventWrite error"
0x180005645  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18000564a  test    ebx, ebx
0x18000564c  jle     short loc_180005657
0x18000564e  movzx   ebx, bx
0x180005651  or      ebx, 80070000h
0x180005657  mov     eax, ebx
0x180005659  jmp     short loc_18000565D
0x18000565b  xor     eax, eax
0x18000565d  mov     rcx, [rsp+48h+var_18]
0x180005662  xor     rcx, rsp; StackCookie
0x180005665  call    __security_check_cookie
0x18000566a  mov     rbx, [rsp+48h+arg_18]
0x18000566f  add     rsp, 40h
0x180005673  pop     rdi
0x180005674  retn
```
