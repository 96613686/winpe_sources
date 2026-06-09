# wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)

- ea: `0x18000bbb0`
- end: `0x18000bbd0`
- name: `?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a3a4`
- `0x18000a4ec`
- `0x18000a634`
- `0x18000ac90`

## callees

- `0x18000a23c`

## string_xrefs

- `0x18000bbb9`: `onecore\amcore\smartscreen\src\client\com\dll\main.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  wil::details::ReportFailure_Hr<0>(
    (_DWORD)this,
    (_DWORD)a2,
    (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\com\\dll\\main.cpp",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x18000bbb0  sub     rsp, 48h
0x18000bbb4  mov     rax, [rsp+48h]
0x18000bbb9  lea     r8, aOnecoreAmcoreS_0; "onecore\\amcore\\smartscreen\\src\\clie"...
0x18000bbc0  mov     [rsp+48h+var_18], r9d
0x18000bbc5  mov     [rsp+48h+var_20], rax
0x18000bbca  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
