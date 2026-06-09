# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,void *,_GUID const *)

- ea: `0x180005894`
- end: `0x180005946`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEAXPEBU_GUID@@@Z`
- size: `178`
- prototype: `__int64 __fastcall(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, unsigned int, void *, const struct _GUID *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180011958`
- `0x180012360`
- `0x180019064`

## callees

- `0x180005894`
- `0x18000594c`
- `0x180030700`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800058f9`
- `ntdll!EtwEventWrite` at `0x1800058f9`
- `ntdll!EtwEventEnabled` at `0x1800058c5`
- `ntdll!EtwEventEnabled` at `0x1800058c5`

## string_xrefs

- `0x18000590e`: `EventWrite error`

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
0x180005894  mov     [rsp+arg_18], rbx
0x180005899  mov     [rsp+arg_10], r8d
0x18000589e  push    rdi
0x18000589f  sub     rsp, 40h
0x1800058a3  mov     rax, cs:__security_cookie
0x1800058aa  xor     rax, rsp
0x1800058ad  mov     [rsp+48h+var_18], rax
0x1800058b2  mov     rdi, rcx
0x1800058b5  mov     rbx, rdx
0x1800058b8  mov     rcx, [rcx]
0x1800058bb  test    rcx, rcx
0x1800058be  jnz     short loc_1800058C5
0x1800058c0  lea     eax, [rcx+1]
0x1800058c3  jmp     short loc_18000592D
0x1800058c5  call    cs:__imp_EtwEventEnabled
0x1800058cc  nop     dword ptr [rax+rax+00h]
0x1800058d1  test    al, al
0x1800058d3  jz      short loc_18000592B
0x1800058d5  mov     rcx, [rdi]
0x1800058d8  lea     rax, [rsp+48h+arg_10]
0x1800058dd  lea     r9, [rsp+48h+var_28]
0x1800058e2  mov     [rsp+48h+var_28], rax
0x1800058e7  mov     r8d, 1
0x1800058ed  mov     [rsp+48h+var_20], 4
0x1800058f6  mov     rdx, rbx
0x1800058f9  call    cs:__imp_EtwEventWrite
0x180005900  nop     dword ptr [rax+rax+00h]
0x180005905  mov     ebx, eax
0x180005907  test    eax, eax
0x180005909  jz      short loc_18000592B
0x18000590b  mov     r8d, eax; unsigned int
0x18000590e  lea     rdx, aEventwriteErro; "EventWrite error"
0x180005915  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18000591a  test    ebx, ebx
0x18000591c  jle     short loc_180005927
0x18000591e  movzx   ebx, bx
0x180005921  or      ebx, 80070000h
0x180005927  mov     eax, ebx
0x180005929  jmp     short loc_18000592D
0x18000592b  xor     eax, eax
0x18000592d  mov     rcx, [rsp+48h+var_18]
0x180005932  xor     rcx, rsp; StackCookie
0x180005935  call    __security_check_cookie
0x18000593a  mov     rbx, [rsp+48h+arg_18]
0x18000593f  add     rsp, 40h
0x180005943  pop     rdi
0x180005944  retn
```
