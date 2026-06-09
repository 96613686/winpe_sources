# _UusExclusion::ParseVersionRangeFromValue_::_1_::catch$15

- ea: `0x18004a9cc`
- end: `0x18004aa3f`
- name: `_UusExclusion::ParseVersionRangeFromValue_::_1_::catch$15`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180027184`
- `0x180029344`
- `0x18003e270`
- `0x180044848`
- `0x180047a30`

## string_xrefs

- `0x18004aa00`: `JSON version value '%S' could not be parsed: %s`

## pseudocode

```c
void __fastcall __noreturn UusExclusion::ParseVersionRangeFromValue_::_1_::catch_15(__int64 a1, __int64 a2)
{
  const wchar_t *v3; // rax
  const char *v4; // rdx

  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 64) + 8LL))(*(_QWORD *)(a2 + 64));
  v3 = (const wchar_t *)std::wstring::c_str(a2 + 192);
  snprintf((char *const)(a2 + 224), 0x800u, "JSON version value '%S' could not be parsed: %s", v3, v4);
  std::runtime_error::runtime_error((std::runtime_error *)(a2 + 136), (const char *)(a2 + 224));
  throw (std::runtime_error *)(a2 + 136);
}

```

## disassembly

```asm
0x18004a9cc  mov     [rsp+arg_8], rdx
0x18004a9d1  push    rbp
0x18004a9d2  sub     rsp, 30h
0x18004a9d6  mov     rbp, rdx
0x18004a9d9  mov     rcx, [rbp+40h]
0x18004a9dd  mov     rax, [rcx]
0x18004a9e0  mov     rax, [rax+8]
0x18004a9e4  call    _guard_dispatch_icall
0x18004a9e9  mov     rdx, rax
0x18004a9ec  lea     rcx, [rbp+0C0h]
0x18004a9f3  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x18004a9f8  mov     [rsp+38h+var_18], rdx
0x18004a9fd  mov     r9, rax
0x18004aa00  lea     r8, aJsonVersionVal_0; "JSON version value '%S' could not be pa"...
0x18004aa07  mov     edx, 800h; BufferCount
0x18004aa0c  lea     rcx, [rbp+0E0h]; Buffer
0x18004aa13  call    snprintf
0x18004aa18  lea     rdx, [rbp+0E0h]; char *
0x18004aa1f  lea     rcx, [rbp+88h]; this
0x18004aa26  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18004aa2b  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18004aa32  lea     rcx, [rbp+88h]; pExceptionObject
0x18004aa39  call    _CxxThrowException
```
