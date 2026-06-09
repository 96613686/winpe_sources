# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,_GUID const *,void *,_GUID const *)

- ea: `0x18001b618`
- end: `0x18001b746`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@2PEAX2@Z`
- size: `302`
- prototype: `int(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const struct _GUID *, const struct _GUID *, void *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180008b30`
- `0x18001b5cc`

## callees

- `0x18001b618`
- `0x18001bdf0`
- `0x18001d0ec`
- `0x180040260`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18001b6a4`
- `ntdll!EtwEventActivityIdControl` at `0x18001b6e3`
- `ntdll!EtwEventActivityIdControl` at `0x18001b6a4`
- `ntdll!EtwEventActivityIdControl` at `0x18001b6e3`
- `ntdll!EtwEventWrite` at `0x18001b6be`
- `ntdll!EtwEventWrite` at `0x18001b6be`
- `ntdll!EtwEventEnabled` at `0x18001b64c`
- `ntdll!EtwEventEnabled` at `0x18001b64c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b68c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b68c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b6f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b6f3`

## string_xrefs

- `0x18001b727`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        const unsigned __int16 *a3,
        const struct _GUID *a4,
        const struct _GUID *a5)
{
  __int64 v7; // rcx
  signed int v10; // eax
  signed int v11; // edi
  EventManager *v12; // rcx
  _QWORD v14[2]; // [rsp+20h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+30h] [rbp-40h] BYREF
  const struct _GUID *v16; // [rsp+40h] [rbp-30h]
  __int64 v17; // [rsp+48h] [rbp-28h]
  const struct _GUID *v18; // [rsp+50h] [rbp-20h]
  __int64 v19; // [rsp+58h] [rbp-18h]

  v7 = *(_QWORD *)this;
  if ( !v7 )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(v7, a2) )
    return 0;
  CreateDataDescriptor(&v15, a3);
  v18 = a5;
  v16 = a4;
  v17 = 16;
  v19 = 16;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  EtwEventActivityIdControl(2, a4);
  v10 = EtwEventWrite(*(_QWORD *)this, a2, 3, &v15);
  v14[0] = 0;
  v14[1] = 0;
  v11 = v10;
  EtwEventActivityIdControl(2, v14);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( !v11 )
    return 0;
  EventManager::LogIt(v12, L"EventWrite error", v11);
  if ( v11 > 0 )
    return (unsigned __int16)v11 | 0x80070000;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001b618  push    rbp
0x18001b61a  push    rbx
0x18001b61b  push    rsi
0x18001b61c  push    rdi
0x18001b61d  push    r14
0x18001b61f  mov     rbp, rsp
0x18001b622  sub     rsp, 70h
0x18001b626  mov     rax, cs:__security_cookie
0x18001b62d  xor     rax, rsp
0x18001b630  mov     [rbp+var_10], rax
0x18001b634  mov     rsi, rcx
0x18001b637  mov     r14, r9
0x18001b63a  mov     rcx, [rcx]
0x18001b63d  mov     rbx, r8
0x18001b640  mov     rdi, rdx
0x18001b643  test    rcx, rcx
0x18001b646  jz      loc_18001B707
0x18001b64c  call    cs:__imp_EtwEventEnabled
0x18001b653  nop     dword ptr [rax+rax+00h]
0x18001b658  test    al, al
0x18001b65a  jz      loc_18001B703
0x18001b660  mov     rdx, rbx; unsigned __int16 *
0x18001b663  lea     rcx, [rbp+var_40]; struct _EVENT_DATA_DESCRIPTOR *
0x18001b667  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x18001b66c  mov     rax, [rbp+arg_20]
0x18001b670  lea     rcx, [rsi+8]; lpCriticalSection
0x18001b674  mov     [rbp+var_20], rax
0x18001b678  mov     [rbp+var_30], r14
0x18001b67c  mov     [rbp+var_28], 10h
0x18001b684  mov     [rbp+var_18], 10h
0x18001b68c  call    cs:__imp_EnterCriticalSection
0x18001b693  nop     dword ptr [rax+rax+00h]
0x18001b698  mov     rdx, r14
0x18001b69b  mov     r14d, 2
0x18001b6a1  mov     ecx, r14d
0x18001b6a4  call    cs:__imp_EtwEventActivityIdControl
0x18001b6ab  nop     dword ptr [rax+rax+00h]
0x18001b6b0  mov     rcx, [rsi]
0x18001b6b3  lea     r9, [rbp+var_40]
0x18001b6b7  lea     r8d, [r14+1]
0x18001b6bb  mov     rdx, rdi
0x18001b6be  call    cs:__imp_EtwEventWrite
0x18001b6c5  nop     dword ptr [rax+rax+00h]
0x18001b6ca  lea     rdx, [rbp+var_50]
0x18001b6ce  mov     [rbp+var_50], 0
0x18001b6d6  mov     ecx, r14d
0x18001b6d9  mov     [rbp+var_48], 0
0x18001b6e1  mov     edi, eax
0x18001b6e3  call    cs:__imp_EtwEventActivityIdControl
0x18001b6ea  nop     dword ptr [rax+rax+00h]
0x18001b6ef  lea     rcx, [rsi+8]; lpCriticalSection
0x18001b6f3  call    cs:__imp_LeaveCriticalSection
0x18001b6fa  nop     dword ptr [rax+rax+00h]
0x18001b6ff  test    edi, edi
0x18001b701  jnz     short loc_18001B724
0x18001b703  xor     eax, eax
0x18001b705  jmp     short loc_18001B70C
0x18001b707  mov     eax, 1
0x18001b70c  mov     rcx, [rbp+var_10]
0x18001b710  xor     rcx, rsp; StackCookie
0x18001b713  call    __security_check_cookie
0x18001b718  add     rsp, 70h
0x18001b71c  pop     r14
0x18001b71e  pop     rdi
0x18001b71f  pop     rsi
0x18001b720  pop     rbx
0x18001b721  pop     rbp
0x18001b722  retn
0x18001b724  mov     r8d, edi; unsigned int
0x18001b727  lea     rdx, aEventwriteErro; "EventWrite error"
0x18001b72e  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18001b733  test    edi, edi
0x18001b735  jg      short loc_18001B73B
0x18001b737  mov     eax, edi
0x18001b739  jmp     short loc_18001B70C
0x18001b73b  movzx   edi, di
0x18001b73e  or      edi, 80070000h
0x18001b744  jmp     short loc_18001B737
```
