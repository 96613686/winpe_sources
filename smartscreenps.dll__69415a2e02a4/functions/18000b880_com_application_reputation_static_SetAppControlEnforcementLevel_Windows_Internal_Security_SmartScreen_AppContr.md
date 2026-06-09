# com::application_reputation_static::SetAppControlEnforcementLevel(Windows::Internal::Security::SmartScreen::AppControlEnforcementLevel)

- ea: `0x18000b880`
- end: `0x18000b8ca`
- name: `?SetAppControlEnforcementLevel@application_reputation_static@com@@UEAAJW4AppControlEnforcementLevel@SmartScreen@Security@Internal@Windows@@@Z`
- size: `74`
- prototype: `int __high(enum Windows::Internal::Security::SmartScreen::AppControlEnforcementLevel)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180009204`
- `0x18000b880`
- `0x18000e010`

## string_xrefs

- `0x18000b895`: `onecore\amcore\smartscreen\src\client\apprep\src\com_api.h`

## pseudocode

```c
__int64 __fastcall com::application_reputation_static::SetAppControlEnforcementLevel(__int64 a1)
{
  int v1; // ebx
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *(_DWORD *)(a1 + 208);
  if ( v1 >= 0 )
    return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 200) + 72LL))(*(_QWORD *)(a1 + 200));
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x64,
    (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\apprep\\src\\com_api.h",
    (const char *)(unsigned int)v1,
    v3);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18000b880  push    rbx; int
0x18000b882  sub     rsp, 20h
0x18000b886  mov     ebx, [rcx+0D0h]
0x18000b88c  test    ebx, ebx
0x18000b88e  jns     short loc_18000B8B2
0x18000b890  mov     rcx, [rsp+28h]; this
0x18000b895  lea     r8, aOnecoreAmcoreS; "onecore\\amcore\\smartscreen\\src\\clie"...
0x18000b89c  mov     r9d, ebx; char *
0x18000b89f  mov     edx, 64h ; 'd'; void *
0x18000b8a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b8a9  mov     eax, ebx
0x18000b8ab  add     rsp, 20h
0x18000b8af  pop     rbx
0x18000b8b0  retn
0x18000b8b2  mov     rcx, [rcx+0C8h]
0x18000b8b9  mov     rax, [rcx]
0x18000b8bc  mov     rax, [rax+48h]
0x18000b8c0  add     rsp, 20h
0x18000b8c4  pop     rbx
0x18000b8c5  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
