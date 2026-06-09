# _BrainSettings::Load_::_1_::catch$41

- ea: `0x18004af5e`
- end: `0x18004afd1`
- name: `_BrainSettings::Load_::_1_::catch$41`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callees

- `0x180025a38`
- `0x180026924`
- `0x18003d5e0`
- `0x18004af5e`

## string_xrefs

- `0x18004af84`: `Unable to check if OneSettings JSON file exist:`
- `0x18004afa6`: `Unable to check if OneSettings JSON file exist: %s`

## pseudocode

```c
__int64 __fastcall BrainSettings::Load_::_1_::catch_41(wil *a1, __int64 a2)
{
  int v3; // eax
  const wchar_t *v4; // rbx
  const wchar_t *v5; // r8

  v3 = wil::ResultFromCaughtException(a1);
  v4 = *(const wchar_t **)(a2 + 88);
  v5 = v4;
  if ( *((_QWORD *)v4 + 3) > 7u )
    v5 = *(const wchar_t **)v4;
  uus::UndockedUpdateTelemetry::UusOneSettingsParseFailure("Unable to check if OneSettings JSON file exist:", v3, v5);
  if ( *((_QWORD *)v4 + 3) > 7u )
    v4 = *(const wchar_t **)v4;
  wil::details::in1diag3::Log_CaughtExceptionMsg(
    *(wil::details::in1diag3 **)(a2 + 440),
    (void *)0x4E,
    (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\BrainSettings.hpp",
    "Unable to check if OneSettings JSON file exist: %s",
    (const char *)v4);
  return 0;
}

```

## disassembly

```asm
0x18004af5e  mov     [rsp+arg_8], rdx
0x18004af63  push    rbx
0x18004af64  push    rbp
0x18004af65  sub     rsp, 38h
0x18004af69  mov     rbp, rdx
0x18004af6c  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18004af71  mov     rbx, [rbp+58h]
0x18004af75  mov     r8, rbx
0x18004af78  cmp     qword ptr [rbx+18h], 7
0x18004af7d  jbe     short loc_18004AF82
0x18004af7f  mov     r8, [rbx]; wchar_t *
0x18004af82  mov     edx, eax; int
0x18004af84  lea     rcx, aUnableToCheckI_0; "Unable to check if OneSettings JSON fil"...
0x18004af8b  call    ?UusOneSettingsParseFailure@UndockedUpdateTelemetry@uus@@SAXPEBDJPEB_W@Z; uus::UndockedUpdateTelemetry::UusOneSettingsParseFailure(char const *,long,wchar_t const *)
0x18004af90  cmp     qword ptr [rbx+18h], 7
0x18004af95  jbe     short loc_18004AF9A
0x18004af97  mov     rbx, [rbx]
0x18004af9a  mov     rcx, [rbp+1B8h]; this
0x18004afa1  mov     [rsp+48h+var_28], rbx; char *
0x18004afa6  lea     r9, aUnableToCheckI; "Unable to check if OneSettings JSON fil"...
0x18004afad  lea     r8, aCW1SSrcBrainLi_1; "C:\\__w\\1\\s\\src\\brain\\lib\\BrainSe"...
0x18004afb4  mov     edx, 4Eh ; 'N'; void *
0x18004afb9  call    ?Log_CaughtExceptionMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Log_CaughtExceptionMsg(void *,uint,char const *,char const *,...)
0x18004afbe  nop
0x18004afbf  mov     rax, 0
0x18004afc9  add     rsp, 38h
0x18004afcd  pop     rbp
0x18004afce  pop     rbx
0x18004afcf  retn
```
