# DirectUI::DuiPVLTrigger::TriggerContentTransition(DirectUI::DynamicArray<DirectUI::Element *,0> *,DirectUI::DynamicArray<DirectUI::Element *,0> *,DirectUI::Element *,tagPOINT,int,ulong *)

- ea: `0x180011448`
- end: `0x1800114c7`
- name: `?TriggerContentTransition@DuiPVLTrigger@DirectUI@@QEAAJPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@0PEAVElement@2@UtagPOINT@@HPEAK@Z`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001177c`

## callees

- `0x180011448`
- `0x18001f010`

## import_xrefs

- `DUI70!DuiCreateObject` at `0x180011474`
- `DUI70!DuiCreateObject` at `0x180011474`

## pseudocode

```c
int __fastcall DirectUI::DuiPVLTrigger::TriggerContentTransition(
        void **a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7)
{
  int result; // eax

  if ( *a1 )
    return (*(__int64 (__fastcall **)(void *, __int64, __int64, __int64, __int64, int, __int64))(*(_QWORD *)*a1 + 144LL))(
             *a1,
             a2,
             a3,
             a4,
             a5,
             4,
             a7);
  result = DuiCreateObject(&GUID_7627b482_f285_41e7_996d_368ed0052602, &GUID_0372c617_aeb1_4bcc_8703_dad13e0c7d8a, a1);
  if ( result >= 0 )
    return (*(__int64 (__fastcall **)(void *, __int64, __int64, __int64, __int64, int, __int64))(*(_QWORD *)*a1 + 144LL))(
             *a1,
             a2,
             a3,
             a4,
             a5,
             4,
             a7);
  return result;
}

```

## disassembly

```asm
0x180011448  push    rbx
0x18001144a  push    rbp
0x18001144b  push    rsi
0x18001144c  push    rdi
0x18001144d  sub     rsp, 48h
0x180011451  cmp     qword ptr [rcx], 0
0x180011455  mov     rdi, r9
0x180011458  mov     rsi, r8
0x18001145b  mov     rbp, rdx
0x18001145e  mov     rbx, rcx
0x180011461  jnz     short loc_18001147E
0x180011463  mov     r8, rcx
0x180011466  lea     rdx, _GUID_0372c617_aeb1_4bcc_8703_dad13e0c7d8a
0x18001146d  lea     rcx, _GUID_7627b482_f285_41e7_996d_368ed0052602
0x180011474  call    cs:__imp_?DuiCreateObject@@YAJAEBU_GUID@@0PEAPEAX@Z; DuiCreateObject(_GUID const &,_GUID const &,void * *)
0x18001147a  test    eax, eax
0x18001147c  js      short loc_1800114BE
0x18001147e  mov     rcx, [rbx]
0x180011481  mov     r9, rdi
0x180011484  mov     r8, rsi
0x180011487  mov     rdx, rbp
0x18001148a  mov     rax, [rcx]
0x18001148d  mov     r10, [rax+90h]
0x180011494  mov     rax, [rsp+68h+arg_30]
0x18001149c  mov     [rsp+68h+var_38], rax
0x1800114a1  mov     rax, [rsp+68h+arg_20]
0x1800114a9  mov     [rsp+68h+var_40], 4
0x1800114b1  mov     [rsp+68h+var_48], rax
0x1800114b6  mov     rax, r10
0x1800114b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114be  add     rsp, 48h
0x1800114c2  pop     rdi
0x1800114c3  pop     rsi
0x1800114c4  pop     rbp
0x1800114c5  pop     rbx
0x1800114c6  retn
```
