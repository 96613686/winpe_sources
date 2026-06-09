# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x18000d250`
- end: `0x18000d286`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `54`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180008410`

## callees

- `0x18000323c`

## string_xrefs

- `0x18000d26f`: `onecoreuap\base\appmodel\search\filters\xml\xmlcontentfilter.cpp`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (__int64)this,
    392,
    (__int64)"onecoreuap\\base\\appmodel\\search\\filters\\xml\\xmlcontentfilter.cpp",
    0,
    0,
    retaddr,
    v4);
}

```

## disassembly

```asm
0x18000d250  sub     rsp, 48h
0x18000d254  mov     rax, [rsp+48h]
0x18000d259  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18000d25e  mov     [rsp+48h+var_20], rax; __int64
0x18000d263  mov     [rsp+48h+var_28], 0; __int64
0x18000d26c  xor     r9d, r9d; int
0x18000d26f  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000d276  mov     edx, 188h; int
0x18000d27b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000d280  nop
0x18000d281  add     rsp, 48h
0x18000d285  retn
```
