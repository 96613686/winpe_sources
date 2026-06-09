# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,void *,_GUID const *)

- ea: `0x180036d30`
- end: `0x180036e3b`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@1PEAX2@Z`
- size: `267`
- prototype: `int(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const struct _GUID *, const unsigned __int16 *, void *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180003050`

## callees

- `0x18001f870`
- `0x1800207e8`
- `0x180036d30`
- `0x18003d810`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180036db9`
- `ntdll!EtwEventActivityIdControl` at `0x180036def`
- `ntdll!EtwEventActivityIdControl` at `0x180036db9`
- `ntdll!EtwEventActivityIdControl` at `0x180036def`
- `ntdll!EtwEventWrite` at `0x180036dd1`
- `ntdll!EtwEventWrite` at `0x180036dd1`
- `ntdll!EtwEventEnabled` at `0x180036d70`
- `ntdll!EtwEventEnabled` at `0x180036d70`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036da9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036da9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036df8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036df8`

## string_xrefs

- `0x180036e05`: `EventWrite error`

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
0x180036d30  push    rbp
0x180036d32  push    rbx
0x180036d33  push    rsi
0x180036d34  push    rdi
0x180036d35  push    r14
0x180036d37  mov     rbp, rsp
0x180036d3a  sub     rsp, 70h
0x180036d3e  mov     rax, cs:__security_cookie
0x180036d45  xor     rax, rsp
0x180036d48  mov     [rbp+var_10], rax
0x180036d4c  mov     r14, [rbp+arg_20]
0x180036d50  mov     rdi, rcx
0x180036d53  mov     rcx, [rcx]
0x180036d56  mov     rsi, r9
0x180036d59  mov     rbx, r8
0x180036d5c  test    rcx, rcx
0x180036d5f  jnz     short loc_180036D69
0x180036d61  lea     eax, [rcx+1]
0x180036d64  jmp     loc_180036E24
0x180036d69  lea     rdx, STOPPING_ON_REQUEST
0x180036d70  call    cs:__imp_EtwEventEnabled
0x180036d76  test    al, al
0x180036d78  jz      loc_180036E22
0x180036d7e  mov     rdx, rbx; unsigned __int16 *
0x180036d81  lea     rcx, [rbp+var_40]; struct _EVENT_DATA_DESCRIPTOR *
0x180036d85  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x180036d8a  mov     rdx, r14; unsigned __int16 *
0x180036d8d  mov     [rbp+var_30], rsi
0x180036d91  lea     rcx, [rbp+var_20]; struct _EVENT_DATA_DESCRIPTOR *
0x180036d95  mov     [rbp+var_28], 10h
0x180036d9d  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x180036da2  lea     rbx, [rdi+8]
0x180036da6  mov     rcx, rbx; lpCriticalSection
0x180036da9  call    cs:__imp_EnterCriticalSection
0x180036daf  mov     rdx, rsi
0x180036db2  mov     esi, 2
0x180036db7  mov     ecx, esi
0x180036db9  call    cs:__imp_EtwEventActivityIdControl
0x180036dbf  mov     rcx, [rdi]
0x180036dc2  lea     r9, [rbp+var_40]
0x180036dc6  lea     r8d, [rsi+1]
0x180036dca  lea     rdx, STOPPING_ON_REQUEST
0x180036dd1  call    cs:__imp_EtwEventWrite
0x180036dd7  lea     rdx, [rbp+var_50]
0x180036ddb  mov     [rbp+var_50], 0
0x180036de3  mov     ecx, esi
0x180036de5  mov     [rbp+var_48], 0
0x180036ded  mov     edi, eax
0x180036def  call    cs:__imp_EtwEventActivityIdControl
0x180036df5  mov     rcx, rbx; lpCriticalSection
0x180036df8  call    cs:__imp_LeaveCriticalSection
0x180036dfe  test    edi, edi
0x180036e00  jz      short loc_180036E22
0x180036e02  mov     r8d, edi; unsigned int
0x180036e05  lea     rdx, aEventwriteErro; "EventWrite error"
0x180036e0c  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x180036e11  test    edi, edi
0x180036e13  jle     short loc_180036E1E
0x180036e15  movzx   edi, di
0x180036e18  or      edi, 80070000h
0x180036e1e  mov     eax, edi
0x180036e20  jmp     short loc_180036E24
0x180036e22  xor     eax, eax
0x180036e24  mov     rcx, [rbp+var_10]
0x180036e28  xor     rcx, rsp; StackCookie
0x180036e2b  call    __security_check_cookie
0x180036e30  add     rsp, 70h
0x180036e34  pop     r14
0x180036e36  pop     rdi
0x180036e37  pop     rsi
0x180036e38  pop     rbx
0x180036e39  pop     rbp
0x180036e3a  retn
```
