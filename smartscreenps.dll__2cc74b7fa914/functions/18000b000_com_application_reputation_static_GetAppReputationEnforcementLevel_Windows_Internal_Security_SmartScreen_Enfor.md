# com::application_reputation_static::GetAppReputationEnforcementLevel(Windows::Internal::Security::SmartScreen::Enforcementlevel *,uchar *)

- ea: `0x18000b000`
- end: `0x18000b049`
- name: `?GetAppReputationEnforcementLevel@application_reputation_static@com@@UEAAJPEAW4Enforcementlevel@SmartScreen@Security@Internal@Windows@@PEAE@Z`
- size: `73`
- prototype: `__int64 __fastcall(com::application_reputation_static *this, enum Windows::Internal::Security::SmartScreen::Enforcementlevel *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180009094`
- `0x18000b000`
- `0x18000e010`

## string_xrefs

- `0x18000b015`: `onecore\amcore\smartscreen\src\client\apprep\src\com_api.h`

## pseudocode

```c
__int64 __fastcall com::application_reputation_static::GetAppReputationEnforcementLevel(
        com::application_reputation_static *this,
        enum Windows::Internal::Security::SmartScreen::Enforcementlevel *a2,
        unsigned __int8 *a3)
{
  int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = *((_DWORD *)this + 52);
  if ( v3 >= 0 )
    return (*(__int64 (__fastcall **)(_QWORD, enum Windows::Internal::Security::SmartScreen::Enforcementlevel *, unsigned __int8 *))(**((_QWORD **)this + 25) + 48LL))(
             *((_QWORD *)this + 25),
             a2,
             a3);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x52,
    (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\apprep\\src\\com_api.h",
    (const char *)(unsigned int)v3,
    v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000b000  push    rbx; int
0x18000b002  sub     rsp, 20h
0x18000b006  mov     ebx, [rcx+0D0h]
0x18000b00c  test    ebx, ebx
0x18000b00e  jns     short loc_18000B031
0x18000b010  mov     rcx, [rsp+28h]; this
0x18000b015  lea     r8, aOnecoreAmcoreS; "onecore\\amcore\\smartscreen\\src\\clie"...
0x18000b01c  mov     r9d, ebx; char *
0x18000b01f  mov     edx, 52h ; 'R'; void *
0x18000b024  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b029  mov     eax, ebx
0x18000b02b  add     rsp, 20h
0x18000b02f  pop     rbx
0x18000b030  retn
0x18000b031  mov     rcx, [rcx+0C8h]
0x18000b038  mov     rax, [rcx]
0x18000b03b  mov     rax, [rax+30h]
0x18000b03f  add     rsp, 20h
0x18000b043  pop     rbx
0x18000b044  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
