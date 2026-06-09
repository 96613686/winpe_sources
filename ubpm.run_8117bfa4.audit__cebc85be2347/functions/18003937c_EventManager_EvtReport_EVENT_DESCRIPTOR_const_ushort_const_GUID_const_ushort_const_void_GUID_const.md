# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,void *,_GUID const *)

- ea: `0x18003937c`
- end: `0x1800394ac`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@1PEAX2@Z`
- size: `304`
- prototype: `int(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const struct _GUID *, const unsigned __int16 *, void *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000a230`

## callees

- `0x18001bdf0`
- `0x18001d0ec`
- `0x18003937c`
- `0x180040260`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180039411`
- `ntdll!EtwEventActivityIdControl` at `0x180039453`
- `ntdll!EtwEventActivityIdControl` at `0x180039411`
- `ntdll!EtwEventActivityIdControl` at `0x180039453`
- `ntdll!EtwEventWrite` at `0x18003942f`
- `ntdll!EtwEventWrite` at `0x18003942f`
- `ntdll!EtwEventEnabled` at `0x1800393bc`
- `ntdll!EtwEventEnabled` at `0x1800393bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800393fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800393fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039462`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039462`

## string_xrefs

- `0x180039475`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        const unsigned __int16 *a3,
        const struct _GUID *a4,
        unsigned __int16 *a5)
{
  __int64 v6; // rcx
  struct _RTL_CRITICAL_SECTION *v10; // rbx
  signed int v11; // eax
  signed int v12; // edi
  EventManager *v13; // rcx
  _QWORD v14[2]; // [rsp+20h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+30h] [rbp-40h] BYREF
  const struct _GUID *v16; // [rsp+40h] [rbp-30h]
  __int64 v17; // [rsp+48h] [rbp-28h]
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+50h] [rbp-20h] BYREF

  v6 = *(_QWORD *)this;
  if ( !v6 )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(v6, STOPPING_ON_REQUEST) )
    return 0;
  CreateDataDescriptor(&v15, a3);
  v16 = a4;
  v17 = 16;
  CreateDataDescriptor(&v18, a5);
  v10 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  EtwEventActivityIdControl(2, a4);
  v11 = EtwEventWrite(*(_QWORD *)this, STOPPING_ON_REQUEST, 3, &v15);
  v14[0] = 0;
  v14[1] = 0;
  v12 = v11;
  EtwEventActivityIdControl(2, v14);
  LeaveCriticalSection(v10);
  if ( !v12 )
    return 0;
  EventManager::LogIt(v13, L"EventWrite error", v12);
  if ( v12 > 0 )
    return (unsigned __int16)v12 | 0x80070000;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18003937c  push    rbp
0x18003937e  push    rbx
0x18003937f  push    rsi
0x180039380  push    rdi
0x180039381  push    r14
0x180039383  mov     rbp, rsp
0x180039386  sub     rsp, 70h
0x18003938a  mov     rax, cs:__security_cookie
0x180039391  xor     rax, rsp
0x180039394  mov     [rbp+var_10], rax
0x180039398  mov     r14, [rbp+arg_20]
0x18003939c  mov     rdi, rcx
0x18003939f  mov     rcx, [rcx]
0x1800393a2  mov     rsi, r9
0x1800393a5  mov     rbx, r8
0x1800393a8  test    rcx, rcx
0x1800393ab  jnz     short loc_1800393B5
0x1800393ad  lea     eax, [rcx+1]
0x1800393b0  jmp     loc_180039494
0x1800393b5  lea     rdx, STOPPING_ON_REQUEST
0x1800393bc  call    cs:__imp_EtwEventEnabled
0x1800393c3  nop     dword ptr [rax+rax+00h]
0x1800393c8  test    al, al
0x1800393ca  jz      loc_180039492
0x1800393d0  mov     rdx, rbx; unsigned __int16 *
0x1800393d3  lea     rcx, [rbp+var_40]; struct _EVENT_DATA_DESCRIPTOR *
0x1800393d7  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x1800393dc  mov     rdx, r14; unsigned __int16 *
0x1800393df  mov     [rbp+var_30], rsi
0x1800393e3  lea     rcx, [rbp+var_20]; struct _EVENT_DATA_DESCRIPTOR *
0x1800393e7  mov     [rbp+var_28], 10h
0x1800393ef  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x1800393f4  lea     rbx, [rdi+8]
0x1800393f8  mov     rcx, rbx; lpCriticalSection
0x1800393fb  call    cs:__imp_EnterCriticalSection
0x180039402  nop     dword ptr [rax+rax+00h]
0x180039407  mov     rdx, rsi
0x18003940a  mov     esi, 2
0x18003940f  mov     ecx, esi
0x180039411  call    cs:__imp_EtwEventActivityIdControl
0x180039418  nop     dword ptr [rax+rax+00h]
0x18003941d  mov     rcx, [rdi]
0x180039420  lea     r9, [rbp+var_40]
0x180039424  lea     r8d, [rsi+1]
0x180039428  lea     rdx, STOPPING_ON_REQUEST
0x18003942f  call    cs:__imp_EtwEventWrite
0x180039436  nop     dword ptr [rax+rax+00h]
0x18003943b  lea     rdx, [rbp+var_50]
0x18003943f  mov     [rbp+var_50], 0
0x180039447  mov     ecx, esi
0x180039449  mov     [rbp+var_48], 0
0x180039451  mov     edi, eax
0x180039453  call    cs:__imp_EtwEventActivityIdControl
0x18003945a  nop     dword ptr [rax+rax+00h]
0x18003945f  mov     rcx, rbx; lpCriticalSection
0x180039462  call    cs:__imp_LeaveCriticalSection
0x180039469  nop     dword ptr [rax+rax+00h]
0x18003946e  test    edi, edi
0x180039470  jz      short loc_180039492
0x180039472  mov     r8d, edi; unsigned int
0x180039475  lea     rdx, aEventwriteErro; "EventWrite error"
0x18003947c  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x180039481  test    edi, edi
0x180039483  jle     short loc_18003948E
0x180039485  movzx   edi, di
0x180039488  or      edi, 80070000h
0x18003948e  mov     eax, edi
0x180039490  jmp     short loc_180039494
0x180039492  xor     eax, eax
0x180039494  mov     rcx, [rbp+var_10]
0x180039498  xor     rcx, rsp; StackCookie
0x18003949b  call    __security_check_cookie
0x1800394a0  add     rsp, 70h
0x1800394a4  pop     r14
0x1800394a6  pop     rdi
0x1800394a7  pop     rsi
0x1800394a8  pop     rbx
0x1800394a9  pop     rbp
0x1800394aa  retn
```
