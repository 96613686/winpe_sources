# _BrainSettings::InitBool_::_1_::catch$4

- ea: `0x18004b050`
- end: `0x18004b0c0`
- name: `_BrainSettings::InitBool_::_1_::catch$4`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callees

- `0x180025a38`
- `0x180026924`
- `0x18003d5e0`
- `0x18004b050`

## string_xrefs

- `0x18004b076`: `Unexpected error parsing JSON value:`
- `0x18004b095`: `Unexpected error parsing JSON value: %s`

## pseudocode

```c
__int64 __fastcall BrainSettings::InitBool_::_1_::catch_4(wil *a1, __int64 a2)
{
  int v3; // eax
  const wchar_t *v4; // rbx
  const wchar_t *v5; // r8

  v3 = wil::ResultFromCaughtException(a1);
  v4 = *(const wchar_t **)(a2 + 56);
  v5 = v4;
  if ( *((_QWORD *)v4 + 3) > 7u )
    v5 = *(const wchar_t **)v4;
  uus::UndockedUpdateTelemetry::UusOneSettingsParseFailure("Unexpected error parsing JSON value:", v3, v5);
  if ( *((_QWORD *)v4 + 3) > 7u )
    v4 = *(const wchar_t **)v4;
  wil::details::in1diag3::Log_CaughtExceptionMsg(
    *(wil::details::in1diag3 **)(a2 + 88),
    (void *)0x8B,
    (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\BrainSettings.hpp",
    "Unexpected error parsing JSON value: %s",
    (const char *)v4);
  return 0;
}

```

## disassembly

```asm
0x18004b050  mov     [rsp+arg_8], rdx
0x18004b055  push    rbx
0x18004b056  push    rbp
0x18004b057  sub     rsp, 38h
0x18004b05b  mov     rbp, rdx
0x18004b05e  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18004b063  mov     rbx, [rbp+38h]
0x18004b067  mov     r8, rbx
0x18004b06a  cmp     qword ptr [rbx+18h], 7
0x18004b06f  jbe     short loc_18004B074
0x18004b071  mov     r8, [rbx]; wchar_t *
0x18004b074  mov     edx, eax; int
0x18004b076  lea     rcx, aUnexpectedErro_0; "Unexpected error parsing JSON value:"
0x18004b07d  call    ?UusOneSettingsParseFailure@UndockedUpdateTelemetry@uus@@SAXPEBDJPEB_W@Z; uus::UndockedUpdateTelemetry::UusOneSettingsParseFailure(char const *,long,wchar_t const *)
0x18004b082  cmp     qword ptr [rbx+18h], 7
0x18004b087  jbe     short loc_18004B08C
0x18004b089  mov     rbx, [rbx]
0x18004b08c  mov     rcx, [rbp+58h]; this
0x18004b090  mov     [rsp+48h+var_28], rbx; char *
0x18004b095  lea     r9, aUnexpectedErro; "Unexpected error parsing JSON value: %s"
0x18004b09c  lea     r8, aCW1SSrcBrainLi_1; "C:\\__w\\1\\s\\src\\brain\\lib\\BrainSe"...
0x18004b0a3  mov     edx, 8Bh; void *
0x18004b0a8  call    ?Log_CaughtExceptionMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Log_CaughtExceptionMsg(void *,uint,char const *,char const *,...)
0x18004b0ad  nop
0x18004b0ae  mov     rax, 0
0x18004b0b8  add     rsp, 38h
0x18004b0bc  pop     rbp
0x18004b0bd  pop     rbx
0x18004b0be  retn
```
