# com::application_reputation_static::SetAppReputationEnforcementLevel(Windows::Internal::Security::SmartScreen::Enforcementlevel)

- ea: `0x18000b620`
- end: `0x18000b669`
- name: `?SetAppReputationEnforcementLevel@application_reputation_static@com@@UEAAJW4Enforcementlevel@SmartScreen@Security@Internal@Windows@@@Z`
- size: `73`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180009094`
- `0x18000b620`
- `0x18000e010`

## string_xrefs

- `0x18000b635`: `onecore\amcore\smartscreen\src\client\apprep\src\com_api.h`

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
0x18000b620  push    rbx; int
0x18000b622  sub     rsp, 20h
0x18000b626  mov     ebx, [rcx+0D0h]
0x18000b62c  test    ebx, ebx
0x18000b62e  jns     short loc_18000B651
0x18000b630  mov     rcx, [rsp+28h]; this
0x18000b635  lea     r8, aOnecoreAmcoreS; "onecore\\amcore\\smartscreen\\src\\clie"...
0x18000b63c  mov     r9d, ebx; char *
0x18000b63f  mov     edx, 58h ; 'X'; void *
0x18000b644  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b649  mov     eax, ebx
0x18000b64b  add     rsp, 20h
0x18000b64f  pop     rbx
0x18000b650  retn
0x18000b651  mov     rcx, [rcx+0C8h]
0x18000b658  mov     rax, [rcx]
0x18000b65b  mov     rax, [rax+38h]
0x18000b65f  add     rsp, 20h
0x18000b663  pop     rbx
0x18000b664  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
