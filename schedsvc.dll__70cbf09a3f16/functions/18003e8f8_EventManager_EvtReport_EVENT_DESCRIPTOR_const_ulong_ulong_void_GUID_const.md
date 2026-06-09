# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,ulong,void *,_GUID const *)

- ea: `0x18003e8f8`
- end: `0x18003e9b9`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KKPEAXPEBU_GUID@@@Z`
- size: `193`
- prototype: `__int64 __fastcall(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, unsigned int, unsigned int, void *, const struct _GUID *)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18003d520`
- `0x18003df98`
- `0x180052f90`
- `0x180072968`
- `0x1800731dc`
- `0x180074390`

## callees

- `0x18003e8f8`
- `0x18004ff54`
- `0x18007e6d0`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18003e932`
- `ntdll!EtwEventEnabled` at `0x18003e932`
- `ntdll!EtwEventWrite` at `0x18003e973`
- `ntdll!EtwEventWrite` at `0x18003e973`

## string_xrefs

- `0x18003e982`: `EventWrite error`

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
0x18003e8f8  mov     [rsp+arg_0], rbx
0x18003e8fd  mov     [rsp+arg_18], r9d
0x18003e902  mov     [rsp+arg_10], r8d
0x18003e907  push    rdi
0x18003e908  sub     rsp, 50h
0x18003e90c  mov     rax, cs:__security_cookie
0x18003e913  xor     rax, rsp
0x18003e916  mov     [rsp+58h+var_18], rax
0x18003e91b  mov     rdi, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x18003e922  mov     rbx, rdx
0x18003e925  mov     rcx, [rdi]
0x18003e928  test    rcx, rcx
0x18003e92b  jnz     short loc_18003E932
0x18003e92d  lea     eax, [rcx+1]
0x18003e930  jmp     short loc_18003E9A1
0x18003e932  call    cs:__imp_EtwEventEnabled
0x18003e938  test    al, al
0x18003e93a  jz      short loc_18003E99F
0x18003e93c  mov     rcx, [rdi]
0x18003e93f  lea     rax, [rsp+58h+arg_10]
0x18003e944  mov     [rsp+58h+var_38], rax
0x18003e949  lea     r9, [rsp+58h+var_38]
0x18003e94e  lea     rax, [rsp+58h+arg_18]
0x18003e953  mov     [rsp+58h+var_30], 4
0x18003e95c  mov     r8d, 2
0x18003e962  mov     [rsp+58h+var_28], rax
0x18003e967  mov     rdx, rbx
0x18003e96a  mov     [rsp+58h+var_20], 4
0x18003e973  call    cs:__imp_EtwEventWrite
0x18003e979  mov     ebx, eax
0x18003e97b  test    eax, eax
0x18003e97d  jz      short loc_18003E99F
0x18003e97f  mov     r8d, eax; unsigned int
0x18003e982  lea     rdx, aEventwriteErro; "EventWrite error"
0x18003e989  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18003e98e  test    ebx, ebx
0x18003e990  jle     short loc_18003E99B
0x18003e992  movzx   ebx, bx
0x18003e995  or      ebx, 80070000h
0x18003e99b  mov     eax, ebx
0x18003e99d  jmp     short loc_18003E9A1
0x18003e99f  xor     eax, eax
0x18003e9a1  mov     rcx, [rsp+58h+var_18]
0x18003e9a6  xor     rcx, rsp; StackCookie
0x18003e9a9  call    __security_check_cookie
0x18003e9ae  mov     rbx, [rsp+58h+arg_0]
0x18003e9b3  add     rsp, 50h
0x18003e9b7  pop     rdi
0x18003e9b8  retn
```
