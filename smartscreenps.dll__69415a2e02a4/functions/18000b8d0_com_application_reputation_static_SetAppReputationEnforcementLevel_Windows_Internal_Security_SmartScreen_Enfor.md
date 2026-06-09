# com::application_reputation_static::SetAppReputationEnforcementLevel(Windows::Internal::Security::SmartScreen::Enforcementlevel)

- ea: `0x18000b8d0`
- end: `0x18000b91a`
- name: `?SetAppReputationEnforcementLevel@application_reputation_static@com@@UEAAJW4Enforcementlevel@SmartScreen@Security@Internal@Windows@@@Z`
- size: `74`
- prototype: `int __high(enum Windows::Internal::Security::SmartScreen::Enforcementlevel)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180009204`
- `0x18000b8d0`
- `0x18000e010`

## string_xrefs

- `0x18000b8e5`: `onecore\amcore\smartscreen\src\client\apprep\src\com_api.h`

## pseudocode

```c
__int64 __fastcall com::application_reputation_static::SetAppReputationEnforcementLevel(__int64 a1)
{
  int v1; // ebx
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *(_DWORD *)(a1 + 208);
  if ( v1 >= 0 )
    return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 200) + 56LL))(*(_QWORD *)(a1 + 200));
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x58,
    (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\apprep\\src\\com_api.h",
    (const char *)(unsigned int)v1,
    v3);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18000b8d0  push    rbx; int
0x18000b8d2  sub     rsp, 20h
0x18000b8d6  mov     ebx, [rcx+0D0h]
0x18000b8dc  test    ebx, ebx
0x18000b8de  jns     short loc_18000B902
0x18000b8e0  mov     rcx, [rsp+28h]; this
0x18000b8e5  lea     r8, aOnecoreAmcoreS; "onecore\\amcore\\smartscreen\\src\\clie"...
0x18000b8ec  mov     r9d, ebx; char *
0x18000b8ef  mov     edx, 58h ; 'X'; void *
0x18000b8f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b8f9  mov     eax, ebx
0x18000b8fb  add     rsp, 20h
0x18000b8ff  pop     rbx
0x18000b900  retn
0x18000b902  mov     rcx, [rcx+0C8h]
0x18000b909  mov     rax, [rcx]
0x18000b90c  mov     rax, [rax+38h]
0x18000b910  add     rsp, 20h
0x18000b914  pop     rbx
0x18000b915  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
