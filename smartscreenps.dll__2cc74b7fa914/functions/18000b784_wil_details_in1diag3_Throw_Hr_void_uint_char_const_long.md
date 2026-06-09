# wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)

- ea: `0x18000b784`
- end: `0x18000b7a9`
- name: `?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000aa00`

## callees

- `0x180009ffc`

## string_xrefs

- `0x18000b78d`: `onecore\amcore\smartscreen\src\client\com\dll\main.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::Throw_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  wil::details::ReportFailure_Hr<0>(
    (_DWORD)this,
    73,
    (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\com\\dll\\main.cpp",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x18000b784  sub     rsp, 48h
0x18000b788  mov     rax, [rsp+48h]
0x18000b78d  lea     r8, aOnecoreAmcoreS_0; "onecore\\amcore\\smartscreen\\src\\clie"...
0x18000b794  mov     [rsp+48h+var_18], r9d
0x18000b799  mov     edx, 49h ; 'I'
0x18000b79e  mov     [rsp+48h+var_20], rax
0x18000b7a3  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
