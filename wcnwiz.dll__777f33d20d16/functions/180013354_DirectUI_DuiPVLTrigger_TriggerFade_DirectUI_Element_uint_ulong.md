# DirectUI::DuiPVLTrigger::TriggerFade(DirectUI::Element *,uint,ulong *)

- ea: `0x180013354`
- end: `0x1800133a9`
- name: `?TriggerFade@DuiPVLTrigger@DirectUI@@QEAAJPEAVElement@2@IPEAK@Z`
- size: `85`
- prototype: `__int64 __fastcall(DirectUI::DuiPVLTrigger *__hidden this, struct DirectUI::Element *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001347c`
- `0x180017840`

## callees

- `0x180013354`
- `0x180031010`

## import_xrefs

- `DUI70!DuiCreateObject` at `0x18001337b`
- `DUI70!DuiCreateObject` at `0x18001337b`

## pseudocode

```c
int __fastcall DirectUI::DuiPVLTrigger::TriggerFade(
        void **this,
        struct DirectUI::Element *a2,
        __int64 a3,
        unsigned int *a4)
{
  int result; // eax

  if ( *this )
    return (*(__int64 (__fastcall **)(void *, struct DirectUI::Element *, __int64))(*(_QWORD *)*this + 64LL))(
             *this,
             a2,
             6);
  result = DuiCreateObject(&GUID_7627b482_f285_41e7_996d_368ed0052602, &GUID_0372c617_aeb1_4bcc_8703_dad13e0c7d8a, this);
  if ( result >= 0 )
    return (*(__int64 (__fastcall **)(void *, struct DirectUI::Element *, __int64))(*(_QWORD *)*this + 64LL))(
             *this,
             a2,
             6);
  return result;
}

```

## disassembly

```asm
0x180013354  mov     [rsp+arg_0], rbx
0x180013359  push    rdi
0x18001335a  sub     rsp, 30h
0x18001335e  cmp     qword ptr [rcx], 0
0x180013362  mov     rdi, rdx
0x180013365  mov     rbx, rcx
0x180013368  jnz     short loc_180013385
0x18001336a  mov     r8, rcx
0x18001336d  lea     rdx, _GUID_0372c617_aeb1_4bcc_8703_dad13e0c7d8a
0x180013374  lea     rcx, _GUID_7627b482_f285_41e7_996d_368ed0052602
0x18001337b  call    cs:__imp_?DuiCreateObject@@YAJAEBU_GUID@@0PEAPEAX@Z; DuiCreateObject(_GUID const &,_GUID const &,void * *)
0x180013381  test    eax, eax
0x180013383  js      short loc_18001339E
0x180013385  mov     rcx, [rbx]
0x180013388  xor     r9d, r9d
0x18001338b  mov     rdx, rdi
0x18001338e  mov     rax, [rcx]
0x180013391  lea     r8d, [r9+6]
0x180013395  mov     rax, [rax+40h]
0x180013399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001339e  mov     rbx, [rsp+38h+arg_0]
0x1800133a3  add     rsp, 30h
0x1800133a7  pop     rdi
0x1800133a8  retn
```
