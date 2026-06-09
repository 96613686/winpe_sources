# com::application_reputation_static::GetAppControlEnforcementLevel(Windows::Internal::Security::SmartScreen::AppControlEnforcementLevel *,uchar *)

- ea: `0x18000afb0`
- end: `0x18000aff9`
- name: `?GetAppControlEnforcementLevel@application_reputation_static@com@@UEAAJPEAW4AppControlEnforcementLevel@SmartScreen@Security@Internal@Windows@@PEAE@Z`
- size: `73`
- prototype: `__int64 __fastcall(com::application_reputation_static *this, enum Windows::Internal::Security::SmartScreen::AppControlEnforcementLevel *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180009094`
- `0x18000afb0`
- `0x18000e010`

## string_xrefs

- `0x18000afc5`: `onecore\amcore\smartscreen\src\client\apprep\src\com_api.h`

## pseudocode

```c
__int64 __fastcall com::application_reputation_static::GetAppControlEnforcementLevel(
        com::application_reputation_static *this,
        enum Windows::Internal::Security::SmartScreen::AppControlEnforcementLevel *a2,
        unsigned __int8 *a3)
{
  int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = *((_DWORD *)this + 52);
  if ( v3 >= 0 )
    return (*(__int64 (__fastcall **)(_QWORD, enum Windows::Internal::Security::SmartScreen::AppControlEnforcementLevel *, unsigned __int8 *))(**((_QWORD **)this + 25) + 64LL))(
             *((_QWORD *)this + 25),
             a2,
             a3);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5E,
    (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\apprep\\src\\com_api.h",
    (const char *)(unsigned int)v3,
    v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000afb0  push    rbx; int
0x18000afb2  sub     rsp, 20h
0x18000afb6  mov     ebx, [rcx+0D0h]
0x18000afbc  test    ebx, ebx
0x18000afbe  jns     short loc_18000AFE1
0x18000afc0  mov     rcx, [rsp+28h]; this
0x18000afc5  lea     r8, aOnecoreAmcoreS; "onecore\\amcore\\smartscreen\\src\\clie"...
0x18000afcc  mov     r9d, ebx; char *
0x18000afcf  mov     edx, 5Eh ; '^'; void *
0x18000afd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000afd9  mov     eax, ebx
0x18000afdb  add     rsp, 20h
0x18000afdf  pop     rbx
0x18000afe0  retn
0x18000afe1  mov     rcx, [rcx+0C8h]
0x18000afe8  mov     rax, [rcx]
0x18000afeb  mov     rax, [rax+40h]
0x18000afef  add     rsp, 20h
0x18000aff3  pop     rbx
0x18000aff4  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
