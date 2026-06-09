# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x180029734`
- end: `0x18002976a`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `54`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180026958`

## callees

- `0x180008690`

## string_xrefs

- `0x180029753`: `base\diagnosis\pdi\scripteddiag\engine\common\sdiaglib.cpp`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (__int64)this,
    2010,
    (__int64)"base\\diagnosis\\pdi\\scripteddiag\\engine\\common\\sdiaglib.cpp",
    0,
    0,
    retaddr,
    v4);
}

```

## disassembly

```asm
0x180029734  sub     rsp, 48h
0x180029738  mov     rax, [rsp+48h]
0x18002973d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180029742  mov     [rsp+48h+var_20], rax; __int64
0x180029747  mov     [rsp+48h+var_28], 0; __int64
0x180029750  xor     r9d, r9d; int
0x180029753  lea     r8, aBaseDiagnosisP; "base\\diagnosis\\pdi\\scripteddiag\\eng"...
0x18002975a  mov     edx, 7DAh; int
0x18002975f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180029764  nop
0x180029765  add     rsp, 48h
0x180029769  retn
```
