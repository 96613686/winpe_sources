# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,void *,_GUID const *)

- ea: `0x1800525c0`
- end: `0x1800526dc`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@PEAX2@Z`
- size: `284`
- prototype: `int(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const struct _GUID *, void *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180052250`
- `0x180052a50`

## callees

- `0x1800447d0`
- `0x1800525c0`
- `0x180052888`
- `0x180082a40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052692`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052692`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005262c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005262c`
- `ntdll!EtwEventEnabled` at `0x1800525fc`
- `ntdll!EtwEventEnabled` at `0x1800525fc`
- `ntdll!EtwEventActivityIdControl` at `0x180052644`
- `ntdll!EtwEventActivityIdControl` at `0x180052682`
- `ntdll!EtwEventActivityIdControl` at `0x180052644`
- `ntdll!EtwEventActivityIdControl` at `0x180052682`
- `ntdll!EtwEventWrite` at `0x18005265d`
- `ntdll!EtwEventWrite` at `0x18005265d`

## string_xrefs

- `0x1800526a5`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        const unsigned __int16 *a3,
        const struct _GUID *a4)
{
  EventManager *v4; // rsi
  signed int v9; // eax
  signed int v10; // edi
  EventManager *v11; // rcx
  _QWORD v12[2]; // [rsp+20h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+30h] [rbp-30h] BYREF
  const struct _GUID *v14; // [rsp+40h] [rbp-20h]
  __int64 v15; // [rsp+48h] [rbp-18h]

  v4 = g_pEventManager;
  if ( !*(_QWORD *)g_pEventManager )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(*(_QWORD *)g_pEventManager, a2) )
    return 0;
  CreateDataDescriptor(&v13, a3);
  v14 = a4;
  v15 = 16;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v4 + 8));
  EtwEventActivityIdControl(2, a4);
  v9 = EtwEventWrite(*(_QWORD *)v4, a2, 2, &v13);
  v12[0] = 0;
  v12[1] = 0;
  v10 = v9;
  EtwEventActivityIdControl(2, v12);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v4 + 8));
  if ( !v10 )
    return 0;
  EventManager::LogIt(v11, L"EventWrite error", v10);
  if ( v10 > 0 )
    return (unsigned __int16)v10 | 0x80070000;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800525c0  push    rbp
0x1800525c2  push    rbx
0x1800525c3  push    rsi
0x1800525c4  push    rdi
0x1800525c5  push    r14
0x1800525c7  mov     rbp, rsp
0x1800525ca  sub     rsp, 60h
0x1800525ce  mov     rax, cs:__security_cookie
0x1800525d5  xor     rax, rsp
0x1800525d8  mov     [rbp+var_10], rax
0x1800525dc  mov     rsi, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x1800525e3  mov     r14, r9
0x1800525e6  mov     rbx, r8
0x1800525e9  mov     rdi, rdx
0x1800525ec  mov     rcx, [rsi]
0x1800525ef  test    rcx, rcx
0x1800525f2  jnz     short loc_1800525FC
0x1800525f4  lea     eax, [rcx+1]
0x1800525f7  jmp     loc_1800526C4
0x1800525fc  call    cs:__imp_EtwEventEnabled
0x180052603  nop     dword ptr [rax+rax+00h]
0x180052608  test    al, al
0x18005260a  jz      loc_1800526C2
0x180052610  mov     rdx, rbx; unsigned __int16 *
0x180052613  lea     rcx, [rbp+var_30]; struct _EVENT_DATA_DESCRIPTOR *
0x180052617  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x18005261c  lea     rcx, [rsi+8]; lpCriticalSection
0x180052620  mov     [rbp+var_20], r14
0x180052624  mov     [rbp+var_18], 10h
0x18005262c  call    cs:__imp_EnterCriticalSection
0x180052633  nop     dword ptr [rax+rax+00h]
0x180052638  mov     rdx, r14
0x18005263b  mov     r14d, 2
0x180052641  mov     ecx, r14d
0x180052644  call    cs:__imp_EtwEventActivityIdControl
0x18005264b  nop     dword ptr [rax+rax+00h]
0x180052650  mov     rcx, [rsi]
0x180052653  lea     r9, [rbp+var_30]
0x180052657  mov     r8d, r14d
0x18005265a  mov     rdx, rdi
0x18005265d  call    cs:__imp_EtwEventWrite
0x180052664  nop     dword ptr [rax+rax+00h]
0x180052669  lea     rdx, [rbp+var_40]
0x18005266d  mov     [rbp+var_40], 0
0x180052675  mov     ecx, r14d
0x180052678  mov     [rbp+var_38], 0
0x180052680  mov     edi, eax
0x180052682  call    cs:__imp_EtwEventActivityIdControl
0x180052689  nop     dword ptr [rax+rax+00h]
0x18005268e  lea     rcx, [rsi+8]; lpCriticalSection
0x180052692  call    cs:__imp_LeaveCriticalSection
0x180052699  nop     dword ptr [rax+rax+00h]
0x18005269e  test    edi, edi
0x1800526a0  jz      short loc_1800526C2
0x1800526a2  mov     r8d, edi; unsigned int
0x1800526a5  lea     rdx, aEventwriteErro; "EventWrite error"
0x1800526ac  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x1800526b1  test    edi, edi
0x1800526b3  jle     short loc_1800526BE
0x1800526b5  movzx   edi, di
0x1800526b8  or      edi, 80070000h
0x1800526be  mov     eax, edi
0x1800526c0  jmp     short loc_1800526C4
0x1800526c2  xor     eax, eax
0x1800526c4  mov     rcx, [rbp+var_10]
0x1800526c8  xor     rcx, rsp; StackCookie
0x1800526cb  call    __security_check_cookie
0x1800526d0  add     rsp, 60h
0x1800526d4  pop     r14
0x1800526d6  pop     rdi
0x1800526d7  pop     rsi
0x1800526d8  pop     rbx
0x1800526d9  pop     rbp
0x1800526da  retn
```
