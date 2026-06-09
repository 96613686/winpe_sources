# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,_GUID const *,void *,_GUID const *)

- ea: `0x18001f05c`
- end: `0x18001f165`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@2PEAX2@Z`
- size: `265`
- prototype: `int(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const struct _GUID *, const struct _GUID *, void *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180008030`
- `0x18001f010`

## callees

- `0x18001f05c`
- `0x18001f870`
- `0x1800207e8`
- `0x18003d810`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18001f0dc`
- `ntdll!EtwEventActivityIdControl` at `0x18001f10f`
- `ntdll!EtwEventActivityIdControl` at `0x18001f0dc`
- `ntdll!EtwEventActivityIdControl` at `0x18001f10f`
- `ntdll!EtwEventWrite` at `0x18001f0f0`
- `ntdll!EtwEventWrite` at `0x18001f0f0`
- `ntdll!EtwEventEnabled` at `0x18001f090`
- `ntdll!EtwEventEnabled` at `0x18001f090`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f0ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f0ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f119`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f119`

## string_xrefs

- `0x18001f146`: `EventWrite error`

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
0x18001f05c  push    rbp
0x18001f05e  push    rbx
0x18001f05f  push    rsi
0x18001f060  push    rdi
0x18001f061  push    r14
0x18001f063  mov     rbp, rsp
0x18001f066  sub     rsp, 70h
0x18001f06a  mov     rax, cs:__security_cookie
0x18001f071  xor     rax, rsp
0x18001f074  mov     [rbp+var_10], rax
0x18001f078  mov     rsi, rcx
0x18001f07b  mov     r14, r9
0x18001f07e  mov     rcx, [rcx]
0x18001f081  mov     rbx, r8
0x18001f084  mov     rdi, rdx
0x18001f087  test    rcx, rcx
0x18001f08a  jz      loc_18001F127
0x18001f090  call    cs:__imp_EtwEventEnabled
0x18001f096  test    al, al
0x18001f098  jz      loc_18001F123
0x18001f09e  mov     rdx, rbx; unsigned __int16 *
0x18001f0a1  lea     rcx, [rbp+var_40]; struct _EVENT_DATA_DESCRIPTOR *
0x18001f0a5  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x18001f0aa  mov     rax, [rbp+arg_20]
0x18001f0ae  lea     rcx, [rsi+8]; lpCriticalSection
0x18001f0b2  mov     [rbp+var_20], rax
0x18001f0b6  mov     [rbp+var_30], r14
0x18001f0ba  mov     [rbp+var_28], 10h
0x18001f0c2  mov     [rbp+var_18], 10h
0x18001f0ca  call    cs:__imp_EnterCriticalSection
0x18001f0d0  mov     rdx, r14
0x18001f0d3  mov     r14d, 2
0x18001f0d9  mov     ecx, r14d
0x18001f0dc  call    cs:__imp_EtwEventActivityIdControl
0x18001f0e2  mov     rcx, [rsi]
0x18001f0e5  lea     r9, [rbp+var_40]
0x18001f0e9  lea     r8d, [r14+1]
0x18001f0ed  mov     rdx, rdi
0x18001f0f0  call    cs:__imp_EtwEventWrite
0x18001f0f6  lea     rdx, [rbp+var_50]
0x18001f0fa  mov     [rbp+var_50], 0
0x18001f102  mov     ecx, r14d
0x18001f105  mov     [rbp+var_48], 0
0x18001f10d  mov     edi, eax
0x18001f10f  call    cs:__imp_EtwEventActivityIdControl
0x18001f115  lea     rcx, [rsi+8]; lpCriticalSection
0x18001f119  call    cs:__imp_LeaveCriticalSection
0x18001f11f  test    edi, edi
0x18001f121  jnz     short loc_18001F143
0x18001f123  xor     eax, eax
0x18001f125  jmp     short loc_18001F12C
0x18001f127  mov     eax, 1
0x18001f12c  mov     rcx, [rbp+var_10]
0x18001f130  xor     rcx, rsp; StackCookie
0x18001f133  call    __security_check_cookie
0x18001f138  add     rsp, 70h
0x18001f13c  pop     r14
0x18001f13e  pop     rdi
0x18001f13f  pop     rsi
0x18001f140  pop     rbx
0x18001f141  pop     rbp
0x18001f142  retn
0x18001f143  mov     r8d, edi; unsigned int
0x18001f146  lea     rdx, aEventwriteErro; "EventWrite error"
0x18001f14d  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18001f152  test    edi, edi
0x18001f154  jg      short loc_18001F15A
0x18001f156  mov     eax, edi
0x18001f158  jmp     short loc_18001F12C
0x18001f15a  movzx   edi, di
0x18001f15d  or      edi, 80070000h
0x18001f163  jmp     short loc_18001F156
```
