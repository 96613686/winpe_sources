# com::application_reputation_static::GetAppControlEnforcementLevel(Windows::Internal::Security::SmartScreen::AppControlEnforcementLevel *,uchar *)

- ea: `0x18000b260`
- end: `0x18000b2aa`
- name: `?GetAppControlEnforcementLevel@application_reputation_static@com@@UEAAJPEAW4AppControlEnforcementLevel@SmartScreen@Security@Internal@Windows@@PEAE@Z`
- size: `74`
- prototype: `int(com::application_reputation_static *__hidden this, enum Windows::Internal::Security::SmartScreen::AppControlEnforcementLevel *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180009204`
- `0x18000b260`
- `0x18000e010`

## string_xrefs

- `0x18000b275`: `onecore\amcore\smartscreen\src\client\apprep\src\com_api.h`

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
0x18000b260  push    rbx; int
0x18000b262  sub     rsp, 20h
0x18000b266  mov     ebx, [rcx+0D0h]
0x18000b26c  test    ebx, ebx
0x18000b26e  jns     short loc_18000B292
0x18000b270  mov     rcx, [rsp+28h]; this
0x18000b275  lea     r8, aOnecoreAmcoreS; "onecore\\amcore\\smartscreen\\src\\clie"...
0x18000b27c  mov     r9d, ebx; char *
0x18000b27f  mov     edx, 5Eh ; '^'; void *
0x18000b284  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b289  mov     eax, ebx
0x18000b28b  add     rsp, 20h
0x18000b28f  pop     rbx
0x18000b290  retn
0x18000b292  mov     rcx, [rcx+0C8h]
0x18000b299  mov     rax, [rcx]
0x18000b29c  mov     rax, [rax+40h]
0x18000b2a0  add     rsp, 20h
0x18000b2a4  pop     rbx
0x18000b2a5  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
