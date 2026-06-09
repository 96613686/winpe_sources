# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,void *,_GUID const *)

- ea: `0x1800527d0`
- end: `0x180052882`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEAXPEBU_GUID@@@Z`
- size: `178`
- prototype: `__int64 __fastcall(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, unsigned int, void *, const struct _GUID *)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800519e0`
- `0x18005d470`
- `0x180070b08`
- `0x180073408`

## callees

- `0x1800527d0`
- `0x180052888`
- `0x180082a40`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180052801`
- `ntdll!EtwEventEnabled` at `0x180052801`
- `ntdll!EtwEventWrite` at `0x180052835`
- `ntdll!EtwEventWrite` at `0x180052835`

## string_xrefs

- `0x18005284a`: `EventWrite error`

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
0x1800527d0  mov     [rsp+arg_18], rbx
0x1800527d5  mov     [rsp+arg_10], r8d
0x1800527da  push    rdi
0x1800527db  sub     rsp, 40h
0x1800527df  mov     rax, cs:__security_cookie
0x1800527e6  xor     rax, rsp
0x1800527e9  mov     [rsp+48h+var_18], rax
0x1800527ee  mov     rdi, rcx
0x1800527f1  mov     rbx, rdx
0x1800527f4  mov     rcx, [rcx]
0x1800527f7  test    rcx, rcx
0x1800527fa  jnz     short loc_180052801
0x1800527fc  lea     eax, [rcx+1]
0x1800527ff  jmp     short loc_180052869
0x180052801  call    cs:__imp_EtwEventEnabled
0x180052808  nop     dword ptr [rax+rax+00h]
0x18005280d  test    al, al
0x18005280f  jz      short loc_180052867
0x180052811  mov     rcx, [rdi]
0x180052814  lea     rax, [rsp+48h+arg_10]
0x180052819  lea     r9, [rsp+48h+var_28]
0x18005281e  mov     [rsp+48h+var_28], rax
0x180052823  mov     r8d, 1
0x180052829  mov     [rsp+48h+var_20], 4
0x180052832  mov     rdx, rbx
0x180052835  call    cs:__imp_EtwEventWrite
0x18005283c  nop     dword ptr [rax+rax+00h]
0x180052841  mov     ebx, eax
0x180052843  test    eax, eax
0x180052845  jz      short loc_180052867
0x180052847  mov     r8d, eax; unsigned int
0x18005284a  lea     rdx, aEventwriteErro; "EventWrite error"
0x180052851  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x180052856  test    ebx, ebx
0x180052858  jle     short loc_180052863
0x18005285a  movzx   ebx, bx
0x18005285d  or      ebx, 80070000h
0x180052863  mov     eax, ebx
0x180052865  jmp     short loc_180052869
0x180052867  xor     eax, eax
0x180052869  mov     rcx, [rsp+48h+var_18]
0x18005286e  xor     rcx, rsp; StackCookie
0x180052871  call    __security_check_cookie
0x180052876  mov     rbx, [rsp+48h+arg_18]
0x18005287b  add     rsp, 40h
0x18005287f  pop     rdi
0x180052880  retn
```
