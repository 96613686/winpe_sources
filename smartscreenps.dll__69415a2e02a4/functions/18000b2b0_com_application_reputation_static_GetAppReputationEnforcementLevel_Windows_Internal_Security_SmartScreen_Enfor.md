# com::application_reputation_static::GetAppReputationEnforcementLevel(Windows::Internal::Security::SmartScreen::Enforcementlevel *,uchar *)

- ea: `0x18000b2b0`
- end: `0x18000b2fa`
- name: `?GetAppReputationEnforcementLevel@application_reputation_static@com@@UEAAJPEAW4Enforcementlevel@SmartScreen@Security@Internal@Windows@@PEAE@Z`
- size: `74`
- prototype: `int(com::application_reputation_static *__hidden this, enum Windows::Internal::Security::SmartScreen::Enforcementlevel *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180009204`
- `0x18000b2b0`
- `0x18000e010`

## string_xrefs

- `0x18000b2c5`: `onecore\amcore\smartscreen\src\client\apprep\src\com_api.h`

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
0x18000b2b0  push    rbx; int
0x18000b2b2  sub     rsp, 20h
0x18000b2b6  mov     ebx, [rcx+0D0h]
0x18000b2bc  test    ebx, ebx
0x18000b2be  jns     short loc_18000B2E2
0x18000b2c0  mov     rcx, [rsp+28h]; this
0x18000b2c5  lea     r8, aOnecoreAmcoreS; "onecore\\amcore\\smartscreen\\src\\clie"...
0x18000b2cc  mov     r9d, ebx; char *
0x18000b2cf  mov     edx, 52h ; 'R'; void *
0x18000b2d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b2d9  mov     eax, ebx
0x18000b2db  add     rsp, 20h
0x18000b2df  pop     rbx
0x18000b2e0  retn
0x18000b2e2  mov     rcx, [rcx+0C8h]
0x18000b2e9  mov     rax, [rcx]
0x18000b2ec  mov     rax, [rax+30h]
0x18000b2f0  add     rsp, 20h
0x18000b2f4  pop     rbx
0x18000b2f5  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
